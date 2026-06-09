# PdbHelper::CreateSession(PdbManager *)

- ea: `0x140070418`
- end: `0x14007062e`
- name: `?CreateSession@PdbHelper@@QEAAPEAVFrsStatus@@PEAVPdbManager@@@Z`
- size: `534`
- prototype: `struct FrsStatus *__fastcall(JET_SESID *psesid, struct PdbManager *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140070224`

## callees

- `0x14000cb00`
- `0x14000ee94`
- `0x14006c740`
- `0x140070418`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14007049f`
- `KERNEL32!GetCurrentThreadId` at `0x140070509`
- `KERNEL32!GetCurrentThreadId` at `0x1400705cc`
- `KERNEL32!GetCurrentThreadId` at `0x14007049f`
- `KERNEL32!GetCurrentThreadId` at `0x140070509`
- `KERNEL32!GetCurrentThreadId` at `0x1400705cc`
- `ESENT!JetEndSession` at `0x140070556`
- `ESENT!JetEndSession` at `0x140070556`
- `ESENT!JetOpenDatabaseA` at `0x1400704e6`
- `ESENT!JetOpenDatabaseA` at `0x1400704e6`
- `ESENT!JetAttachDatabaseA` at `0x140070480`
- `ESENT!JetAttachDatabaseA` at `0x140070480`
- `ESENT!JetBeginSessionA` at `0x14007044c`
- `ESENT!JetBeginSessionA` at `0x14007044c`

## string_xrefs

- `0x140070528`: `PdbHelper::CreateSession`
- `0x1400705ea`: `PdbHelper::CreateSession`
- `0x140070585`: `PdbHelper::CreateSession`

## pseudocode

```c
struct FrsStatus *__fastcall PdbHelper::CreateSession(JET_SESID *psesid, struct PdbManager *a2)
{
  __int64 v3; // rdi
  __int64 v4; // rsi
  JET_ERR v5; // ebp
  __int64 v6; // r8
  __int64 v7; // rax
  JET_ERR v8; // ebp
  __int64 v9; // r8
  DWORD v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  JET_ERR v14; // esi
  DWORD v15; // eax
  __int64 v16; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v18; // rcx
  const wchar_t *v20; // [rsp+50h] [rbp-28h] BYREF
  int v21; // [rsp+58h] [rbp-20h]
  int v22; // [rsp+5Ch] [rbp-1Ch]
  const wchar_t *v23; // [rsp+60h] [rbp-18h]
  JET_ERR v24; // [rsp+80h] [rbp+8h] BYREF

  v3 = 0;
  v4 = *(_QWORD *)(*(_QWORD *)a2 + 40LL);
  psesid[2] = (JET_SESID)a2;
  v5 = JetBeginSessionA(*(_QWORD *)(*(_QWORD *)a2 + 48LL), psesid, 0, 0);
  if ( v5 < 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v18,
                                 (unsigned int)v5,
                                 0,
                                 2,
                                 "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                 "PdbHelper::CreateSession",
                                 813,
                                 CurrentThreadId,
                                 0);
  }
  v7 = FrsStringImpl<char,unsigned short>::FrsStringImpl<char,unsigned short>(&v24, v4 + 18, v6);
  v8 = JetAttachDatabaseA(*psesid, (JET_PCSTR)(*(_QWORD *)v7 + 17LL), 0);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v24);
  if ( v8 >= 0 )
  {
    v13 = FrsStringImpl<char,unsigned short>::FrsStringImpl<char,unsigned short>(&v24, v4 + 18, v9);
    v14 = JetOpenDatabaseA(*psesid, (JET_PCSTR)(*(_QWORD *)v13 + 17LL), 0, (JET_DBID *)psesid + 2, 0);
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v24);
    if ( v14 >= 0 )
      return (struct FrsStatus *)v3;
    v15 = GetCurrentThreadId();
    v12 = FrsStatusList::PushNewError(
            v16,
            (unsigned int)v14,
            0,
            2,
            "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
            "PdbHelper::CreateSession",
            799,
            v15,
            0);
  }
  else
  {
    v10 = GetCurrentThreadId();
    v12 = FrsStatusList::PushNewError(
            v11,
            (unsigned int)v8,
            0,
            2,
            "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
            "PdbHelper::CreateSession",
            802,
            v10,
            0);
  }
  v3 = v12;
  v24 = JetEndSession(*psesid, 0);
  if ( v24 < 0 && g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v21 = 808;
    v20 = L"PdbHelper::CreateSession";
    v22 = 4;
    v23 = L"PDBX";
    dbgobj::DbgPrint<unsigned short,unsigned int>(&v20, L"Ignoring second jet error. Error:%d", &v24);
  }
  *psesid = -1;
  return (struct FrsStatus *)v3;
}

```

## disassembly

```asm
0x140070418  mov     [rsp+arg_8], rbx
0x14007041d  mov     [rsp+arg_10], rbp
0x140070422  mov     [rsp+arg_18], rsi
0x140070427  push    rdi
0x140070428  sub     rsp, 70h
0x14007042c  mov     rax, [rdx]
0x14007042f  mov     rbx, rcx
0x140070432  xor     r9d, r9d; szPassword
0x140070435  xor     r8d, r8d; szUserName
0x140070438  xor     edi, edi
0x14007043a  mov     rsi, [rax+28h]
0x14007043e  mov     [rcx+10h], rdx
0x140070442  mov     rax, [rdx]
0x140070445  mov     rdx, rcx; psesid
0x140070448  mov     rcx, [rax+30h]; instance
0x14007044c  call    cs:__imp_JetBeginSessionA
0x140070453  nop     dword ptr [rax+rax+00h]
0x140070458  mov     ebp, eax
0x14007045a  test    eax, eax
0x14007045c  js      loc_1400705CC
0x140070462  lea     rdx, [rsi+12h]
0x140070466  lea     rcx, [rsp+78h+arg_0]
0x14007046e  call    ??0?$FrsStringImpl@DG@@QEAA@PEBG@Z; FrsStringImpl<char,ushort>::FrsStringImpl<char,ushort>(ushort const *)
0x140070473  mov     rcx, [rbx]; sesid
0x140070476  xor     r8d, r8d; grbit
0x140070479  mov     rdx, [rax]
0x14007047c  add     rdx, 11h; szFilename
0x140070480  call    cs:__imp_JetAttachDatabaseA
0x140070487  nop     dword ptr [rax+rax+00h]
0x14007048c  lea     rcx, [rsp+78h+arg_0]
0x140070494  mov     ebp, eax
0x140070496  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14007049b  test    ebp, ebp
0x14007049d  jns     short loc_1400704C0
0x14007049f  call    cs:__imp_GetCurrentThreadId
0x1400704a6  nop     dword ptr [rax+rax+00h]
0x1400704ab  and     [rsp+78h+var_38], rdi
0x1400704b0  mov     edx, ebp
0x1400704b2  mov     [rsp+78h+var_40], eax
0x1400704b6  mov     [rsp+78h+var_48], 322h
0x1400704be  jmp     short loc_140070528
0x1400704c0  lea     rdx, [rsi+12h]
0x1400704c4  lea     rcx, [rsp+78h+arg_0]
0x1400704cc  call    ??0?$FrsStringImpl@DG@@QEAA@PEBG@Z; FrsStringImpl<char,ushort>::FrsStringImpl<char,ushort>(ushort const *)
0x1400704d1  mov     rcx, [rbx]; sesid
0x1400704d4  lea     r9, [rbx+8]; pdbid
0x1400704d8  and     dword ptr [rsp+78h+var_58], edi
0x1400704dc  xor     r8d, r8d; szConnect
0x1400704df  mov     rdx, [rax]
0x1400704e2  add     rdx, 11h; szFilename
0x1400704e6  call    cs:__imp_JetOpenDatabaseA
0x1400704ed  nop     dword ptr [rax+rax+00h]
0x1400704f2  lea     rcx, [rsp+78h+arg_0]
0x1400704fa  mov     esi, eax
0x1400704fc  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140070501  test    esi, esi
0x140070503  jns     loc_140070614
0x140070509  call    cs:__imp_GetCurrentThreadId
0x140070510  nop     dword ptr [rax+rax+00h]
0x140070515  and     [rsp+78h+var_38], rdi
0x14007051a  mov     edx, esi
0x14007051c  mov     [rsp+78h+var_40], eax
0x140070520  mov     [rsp+78h+var_48], 31Fh
0x140070528  lea     rax, aPdbhelperCreat_0; "PdbHelper::CreateSession"
0x14007052f  mov     r9d, 2
0x140070535  mov     [rsp+78h+var_50], rax
0x14007053a  xor     r8d, r8d
0x14007053d  lea     rax, aBaseFsRemotefs_80; "base\\fs\\remotefs\\frs\\src\\db\\pdb.c"...
0x140070544  mov     [rsp+78h+var_58], rax
0x140070549  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14007054e  mov     rcx, [rbx]; sesid
0x140070551  xor     edx, edx; grbit
0x140070553  mov     rdi, rax
0x140070556  call    cs:__imp_JetEndSession
0x14007055d  nop     dword ptr [rax+rax+00h]
0x140070562  mov     [rsp+78h+arg_0], eax
0x140070569  test    eax, eax
0x14007056b  jns     short loc_1400705C6
0x14007056d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140070574  test    rax, rax
0x140070577  jz      short loc_1400705C6
0x140070579  cmp     dword ptr [rax+40h], 0
0x14007057d  jz      short loc_1400705C6
0x14007057f  cmp     dword ptr [rax+38h], 4
0x140070583  jl      short loc_1400705C6
0x140070585  lea     rax, aPdbhelperCreat; "PdbHelper::CreateSession"
0x14007058c  mov     [rsp+78h+var_20], 328h
0x140070594  mov     [rsp+78h+var_28], rax
0x140070599  lea     r8, [rsp+78h+arg_0]
0x1400705a1  lea     rax, aPdbx; "PDBX"
0x1400705a8  mov     [rsp+78h+var_1C], 4
0x1400705b0  lea     rdx, aIgnoringSecond; "Ignoring second jet error. Error:%d"
0x1400705b7  mov     [rsp+78h+var_18], rax
0x1400705bc  lea     rcx, [rsp+78h+var_28]
0x1400705c1  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x1400705c6  or      qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1400705ca  jmp     short loc_140070614
0x1400705cc  call    cs:__imp_GetCurrentThreadId
0x1400705d3  nop     dword ptr [rax+rax+00h]
0x1400705d8  and     [rsp+78h+var_38], rdi
0x1400705dd  mov     r9d, 2
0x1400705e3  mov     [rsp+78h+var_40], eax
0x1400705e7  xor     r8d, r8d
0x1400705ea  lea     rax, aPdbhelperCreat_0; "PdbHelper::CreateSession"
0x1400705f1  mov     [rsp+78h+var_48], 32Dh
0x1400705f9  mov     [rsp+78h+var_50], rax
0x1400705fe  mov     edx, ebp
0x140070600  lea     rax, aBaseFsRemotefs_80; "base\\fs\\remotefs\\frs\\src\\db\\pdb.c"...
0x140070607  mov     [rsp+78h+var_58], rax
0x14007060c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140070611  mov     rdi, rax
0x140070614  lea     r11, [rsp+78h+var_8]
0x140070619  mov     rax, rdi
0x14007061c  mov     rbx, [r11+18h]
0x140070620  mov     rbp, [r11+20h]
0x140070624  mov     rsi, [r11+28h]
0x140070628  mov     rsp, r11
0x14007062b  pop     rdi
0x14007062c  retn
```
