# UsnConsumer::ProcessRename(USN_RECORD_V2 const &,Guid const &,UID const &,_FILETIME const &,Usn const &,int,int,int,ID_RECORD &)

- ea: `0x1400a2d5c`
- end: `0x1400a32cd`
- name: `?ProcessRename@UsnConsumer@@AEAAPEAVFrsStatus@@AEBUUSN_RECORD_V2@@AEBVGuid@@AEBVUID@@AEBU_FILETIME@@AEBVUsn@@HHHAEAVID_RECORD@@@Z`
- size: `1393`
- prototype: `struct FrsStatus *__fastcall(UsnConsumer *__hidden this, const struct USN_RECORD_V2 *, const struct Guid *, const struct UID *, const struct _FILETIME *, const struct Usn *, int, int, int, struct ID_RECORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x1400a32d4`

## callees

- `0x1400036a0`
- `0x14002a6d0`
- `0x14002c1c0`
- `0x14006d538`
- `0x1400a0e34`
- `0x1400a1490`
- `0x1400a2794`
- `0x1400a2d5c`
- `0x1400a40d4`
- `0x1400a48c4`
- `0x1400a58f0`
- `0x1400a6460`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400a2dca`
- `KERNEL32!GetCurrentThreadId` at `0x1400a2e2d`
- `KERNEL32!GetCurrentThreadId` at `0x1400a2ea8`
- `KERNEL32!GetCurrentThreadId` at `0x1400a2f81`
- `KERNEL32!GetCurrentThreadId` at `0x1400a301a`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3066`
- `KERNEL32!GetCurrentThreadId` at `0x1400a309f`
- `KERNEL32!GetCurrentThreadId` at `0x1400a30de`
- `KERNEL32!GetCurrentThreadId` at `0x1400a314a`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3180`
- `KERNEL32!GetCurrentThreadId` at `0x1400a31c6`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3268`
- `KERNEL32!GetCurrentThreadId` at `0x1400a2dca`
- `KERNEL32!GetCurrentThreadId` at `0x1400a2e2d`
- `KERNEL32!GetCurrentThreadId` at `0x1400a2ea8`
- `KERNEL32!GetCurrentThreadId` at `0x1400a2f81`
- `KERNEL32!GetCurrentThreadId` at `0x1400a301a`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3066`
- `KERNEL32!GetCurrentThreadId` at `0x1400a309f`
- `KERNEL32!GetCurrentThreadId` at `0x1400a30de`
- `KERNEL32!GetCurrentThreadId` at `0x1400a314a`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3180`
- `KERNEL32!GetCurrentThreadId` at `0x1400a31c6`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3268`

## string_xrefs

- `0x1400a3200`: `UsnConsumer::ProcessRename`
- `0x1400a2de7`: `UsnConsumer::ProcessRename`
- `0x1400a2e95`: `UsnConsumer::ProcessRename`
- `0x1400a3214`: `Content set root was moved: %?`

## pseudocode

```c
struct FrsStatus *__fastcall UsnConsumer::ProcessRename(
        __int64 **this,
        const struct USN_RECORD_V2 *a2,
        const struct Guid *a3,
        const struct UID *a4,
        const struct _FILETIME *a5,
        const struct Usn *a6,
        int a7,
        int a8,
        int a9,
        struct ID_RECORD *a10)
{
  struct FrsStatus *IdRecord; // rbx
  __int64 v14; // rcx
  __int64 v16; // r9
  struct FrsStatus *v17; // rbx
  __int64 v18; // rcx
  __int64 *v19; // rcx
  __int64 v20; // rax
  DWORD v21; // eax
  __int64 v22; // rax
  __int128 v23; // xmm0
  __int64 v24; // r8
  struct FrsStatus *v25; // r12
  DWORD v26; // eax
  __int64 v27; // rcx
  struct FrsStatus *v28; // rbx
  __int64 v29; // rcx
  struct FrsStatus *v30; // rbx
  __int64 v31; // rcx
  struct FrsStatus *v32; // rbx
  __int64 v33; // rcx
  struct FrsStatus *v34; // rbx
  __int64 v35; // rcx
  struct FrsStatus *v36; // rbx
  __int64 v37; // rcx
  struct FrsStatus *v38; // rbx
  __int64 v39; // rcx
  struct FrsStatus *v40; // rbx
  __int64 v41; // rcx
  struct FrsStatus *updated; // rbx
  __int64 v43; // rcx
  DWORD CurrentThreadId; // [rsp+38h] [rbp-C8h]
  DWORD v46; // [rsp+38h] [rbp-C8h]
  DWORD v47; // [rsp+38h] [rbp-C8h]
  DWORD v48; // [rsp+38h] [rbp-C8h]
  DWORD v49; // [rsp+38h] [rbp-C8h]
  DWORD v50; // [rsp+38h] [rbp-C8h]
  DWORD v51; // [rsp+38h] [rbp-C8h]
  DWORD v52; // [rsp+38h] [rbp-C8h]
  DWORD v53; // [rsp+38h] [rbp-C8h]
  DWORD v54; // [rsp+38h] [rbp-C8h]
  int v55; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v56; // [rsp+58h] [rbp-A8h] BYREF
  DWORDLONG ParentFileReferenceNumber; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v58; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v59; // [rsp+78h] [rbp-88h]
  __int128 v60; // [rsp+80h] [rbp-80h] BYREF
  __int64 v61; // [rsp+90h] [rbp-70h]
  __int128 v62; // [rsp+98h] [rbp-68h] BYREF
  __int64 v63; // [rsp+A8h] [rbp-58h]
  __int128 v64; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v65; // [rsp+C0h] [rbp-40h]
  __int128 v66; // [rsp+F8h] [rbp-8h]
  struct _FILETIME v67; // [rsp+12Ch] [rbp+2Ch] BYREF
  char v68; // [rsp+370h] [rbp+270h]

  if ( !a7 )
  {
    IdRecord = UsnConsumer::CreateIdRecord((UsnConsumer *)this, a2, a3, a4, a5, a6);
    if ( IdRecord )
    {
      CurrentThreadId = GetCurrentThreadId();
      return (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v14,
                                   *((unsigned int *)IdRecord + 1),
                                   *((unsigned int *)IdRecord + 2),
                                   *(unsigned int *)IdRecord,
                                   "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                                   "UsnConsumer::ProcessRename",
                                   3460,
                                   CurrentThreadId,
                                   IdRecord);
    }
    return 0;
  }
  if ( a9 )
  {
    v17 = UsnConsumer::DeleteCreateIdRecords((UsnConsumer *)this, a2, a10, a3, a4, a5, a6);
    if ( v17 )
    {
      v46 = GetCurrentThreadId();
      return (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v18,
                                   *((unsigned int *)v17 + 1),
                                   *((unsigned int *)v17 + 2),
                                   *(unsigned int *)v17,
                                   "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                                   "UsnConsumer::ProcessRename",
                                   3473,
                                   v46,
                                   v17);
    }
    return 0;
  }
  ParentFileReferenceNumber = a2->ParentFileReferenceNumber;
  ID_RECORD::ID_RECORD((ID_RECORD *)&v64);
  v19 = this[13];
  v55 = 0;
  v20 = *v19;
  v56 = 0;
  *(_QWORD *)&v58 = (*(__int64 (__fastcall **)(__int64 *, int *, DWORDLONG *, __int128 *, __int64 *))(v20 + 40))(
                      v19,
                      &v55,
                      &ParentFileReferenceNumber,
                      &v64,
                      &v56);
  if ( (_QWORD)v58 )
  {
    v21 = GetCurrentThreadId();
    v16 = FrsStatusList::PushNewError(
            v58,
            *(unsigned int *)(v58 + 4),
            *(unsigned int *)(v58 + 8),
            *(unsigned int *)v58,
            "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
            "UsnConsumer::ProcessRename",
            3481,
            v21,
            v58);
    if ( v16 )
      return (struct FrsStatus *)v16;
  }
  else
  {
    v16 = 0;
  }
  if ( !v55 )
  {
    if ( *((_QWORD *)a10 + 2) == 1 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        *((_QWORD *)&v58 + 1) = 0x400000E08LL;
        *(_QWORD *)&v58 = L"UsnConsumer::ProcessRename";
        v59 = L"USNC";
        dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v58, L"Content set root was moved: %?", a10, 0);
      }
      v61 = 0;
      v60 = 0;
      updated = UsnConsumer::UpdateIdRecord((UsnConsumer *)this, a2, a10, (const struct UID *)&v60, 0);
      if ( updated )
      {
        v54 = GetCurrentThreadId();
        return (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v43,
                                     *((unsigned int *)updated + 1),
                                     *((unsigned int *)updated + 2),
                                     *(unsigned int *)updated,
                                     "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                                     "UsnConsumer::ProcessRename",
                                     3593,
                                     v54,
                                     updated);
      }
    }
    else
    {
      v40 = UsnConsumer::TombstoneIdRecord((UsnConsumer *)this, a2, a10, 0);
      if ( v40 )
      {
        v53 = GetCurrentThreadId();
        return (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v41,
                                     *((unsigned int *)v40 + 1),
                                     *((unsigned int *)v40 + 2),
                                     *(unsigned int *)v40,
                                     "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                                     "UsnConsumer::ProcessRename",
                                     3589,
                                     v53,
                                     v40);
      }
    }
    return 0;
  }
  v22 = v66 - *((_QWORD *)a10 + 9);
  if ( (_QWORD)v66 == *((_QWORD *)a10 + 9) )
    v22 = *((_QWORD *)&v66 + 1) - *((_QWORD *)a10 + 10);
  if ( v22 )
  {
    if ( (v68 & 2) != 0 )
    {
      v38 = UsnConsumer::TombstoneIdRecord((UsnConsumer *)this, a2, a10, 0);
      if ( v38 )
      {
        v52 = GetCurrentThreadId();
        return (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v39,
                                     *((unsigned int *)v38 + 1),
                                     *((unsigned int *)v38 + 2),
                                     *(unsigned int *)v38,
                                     "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                                     "UsnConsumer::ProcessRename",
                                     3580,
                                     v52,
                                     v38);
      }
    }
    else
    {
      v58 = v66;
      v36 = UsnConsumer::DeleteCreateIdRecords(
              (UsnConsumer *)this,
              a2,
              a10,
              (const struct Guid *)&v58,
              (const struct UID *)&v64,
              &v67,
              a6);
      if ( v36 )
      {
        v51 = GetCurrentThreadId();
        return (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v37,
                                     *((unsigned int *)v36 + 1),
                                     *((unsigned int *)v36 + 2),
                                     *(unsigned int *)v36,
                                     "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                                     "UsnConsumer::ProcessRename",
                                     3578,
                                     v51,
                                     v36);
      }
    }
    return 0;
  }
  if ( a8 )
  {
    v34 = UsnConsumer::TombstoneIdRecord((UsnConsumer *)this, a2, a10, 0);
    if ( v34 )
    {
      v50 = GetCurrentThreadId();
      return (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v35,
                                   *((unsigned int *)v34 + 1),
                                   *((unsigned int *)v34 + 2),
                                   *(unsigned int *)v34,
                                   "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                                   "UsnConsumer::ProcessRename",
                                   3562,
                                   v50,
                                   v34);
    }
    return 0;
  }
  if ( (*((_BYTE *)a10 + 704) & 2) != 0 )
  {
    if ( (v68 & 2) != 0 )
      return (struct FrsStatus *)v16;
    v30 = UsnConsumer::Validate((UsnConsumer *)this, a10, (const struct ID_RECORD *)&v64, a2);
    if ( v30 )
    {
      v48 = GetCurrentThreadId();
      return (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v31,
                                   *((unsigned int *)v30 + 1),
                                   *((unsigned int *)v30 + 2),
                                   *(unsigned int *)v30,
                                   "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                                   "UsnConsumer::ProcessRename",
                                   3546,
                                   v48,
                                   v30);
    }
    return 0;
  }
  if ( (v68 & 2) != 0 )
  {
    v32 = UsnConsumer::Mark((UsnConsumer *)this, a10, a2);
    if ( v32 )
    {
      v49 = GetCurrentThreadId();
      return (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v33,
                                   *((unsigned int *)v32 + 1),
                                   *((unsigned int *)v32 + 2),
                                   *(unsigned int *)v32,
                                   "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                                   "UsnConsumer::ProcessRename",
                                   3558,
                                   v49,
                                   v32);
    }
    return 0;
  }
  v23 = *((_OWORD *)a10 + 3);
  v61 = *((_QWORD *)a10 + 8);
  v60 = v23;
  v63 = v65;
  v62 = v64;
  v25 = UsnConsumer::UpdateIdRecord((UsnConsumer *)this, a2, a10, (const struct UID *)&v62, a6);
  if ( !v25
    || (v26 = GetCurrentThreadId(),
        (v16 = FrsStatusList::PushNewError(
                 v27,
                 *((unsigned int *)v25 + 1),
                 *((unsigned int *)v25 + 2),
                 *(unsigned int *)v25,
                 "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                 "UsnConsumer::ProcessRename",
                 3502,
                 v26,
                 v25)) == 0) )
  {
    if ( !(unsigned __int8)GVSN::operator==(&v60, &v62, v24) && (a2->FileAttributes & 0x10) != 0 )
    {
      v28 = UsnConsumer::SendDirToWalker((UsnConsumer *)this, (const struct _GUID *)a3, a2, a10, 1, 0, 0);
      if ( v28 )
      {
        v47 = GetCurrentThreadId();
        return (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v29,
                                     *((unsigned int *)v28 + 1),
                                     *((unsigned int *)v28 + 2),
                                     *(unsigned int *)v28,
                                     "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                                     "UsnConsumer::ProcessRename",
                                     3535,
                                     v47,
                                     v28);
      }
      return 0;
    }
  }
  return (struct FrsStatus *)v16;
}

```

## disassembly

```asm
0x1400a2d5c  push    rbp
0x1400a2d5e  push    rbx
0x1400a2d5f  push    rsi
0x1400a2d60  push    rdi
0x1400a2d61  push    r12
0x1400a2d63  push    r13
0x1400a2d65  push    r14
0x1400a2d67  push    r15
0x1400a2d69  lea     rbp, [rsp-298h]
0x1400a2d71  sub     rsp, 398h
0x1400a2d78  mov     rax, cs:__security_cookie
0x1400a2d7f  xor     rax, rsp
0x1400a2d82  mov     [rbp+2D0h+var_50], rax
0x1400a2d89  mov     rax, [rbp+2D0h+arg_20]
0x1400a2d90  xor     r14d, r14d
0x1400a2d93  mov     r13, r8
0x1400a2d96  mov     r12, [rbp+2D0h+arg_28]
0x1400a2d9d  mov     rdi, rdx
0x1400a2da0  mov     rbx, [rbp+2D0h+arg_48]
0x1400a2da7  mov     rsi, rcx
0x1400a2daa  cmp     [rbp+2D0h+arg_30], r14d
0x1400a2db1  jnz     short loc_1400A2E02
0x1400a2db3  mov     [rsp+3D0h+var_3A8], r12; struct Usn *
0x1400a2db8  mov     [rsp+3D0h+var_3B0], rax; struct _FILETIME *
0x1400a2dbd  call    ?CreateIdRecord@UsnConsumer@@AEAAPEAVFrsStatus@@AEBUUSN_RECORD_V2@@AEBVGuid@@AEBVUID@@AEBU_FILETIME@@AEBVUsn@@@Z; UsnConsumer::CreateIdRecord(USN_RECORD_V2 const &,Guid const &,UID const &,_FILETIME const &,Usn const &)
0x1400a2dc2  mov     rbx, rax
0x1400a2dc5  test    rax, rax
0x1400a2dc8  jz      short loc_1400A2DFA
0x1400a2dca  call    cs:__imp_GetCurrentThreadId
0x1400a2dd1  nop     dword ptr [rax+rax+00h]
0x1400a2dd6  mov     [rsp+3D0h+var_390], rbx
0x1400a2ddb  mov     [rsp+3D0h+var_398], eax
0x1400a2ddf  mov     dword ptr [rsp+3D0h+var_3A0], 0D84h
0x1400a2de7  lea     r14, aUsnconsumerPro_1; "UsnConsumer::ProcessRename"
0x1400a2dee  lea     r15, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a2df5  jmp     loc_1400A3285
0x1400a2dfa  mov     r9, r14
0x1400a2dfd  jmp     loc_1400A32A6
0x1400a2e02  cmp     [rbp+2D0h+arg_40], r14d
0x1400a2e09  jz      short loc_1400A2E4C
0x1400a2e0b  mov     [rsp+3D0h+var_3A0], r12; struct Usn *
0x1400a2e10  mov     r8, rbx; struct ID_RECORD *
0x1400a2e13  mov     [rsp+3D0h+var_3A8], rax; struct _FILETIME *
0x1400a2e18  mov     [rsp+3D0h+var_3B0], r9; struct UID *
0x1400a2e1d  mov     r9, r13; struct Guid *
0x1400a2e20  call    ?DeleteCreateIdRecords@UsnConsumer@@AEAAPEAVFrsStatus@@AEBUUSN_RECORD_V2@@AEAVID_RECORD@@AEBVGuid@@AEBVUID@@AEBU_FILETIME@@AEBVUsn@@@Z; UsnConsumer::DeleteCreateIdRecords(USN_RECORD_V2 const &,ID_RECORD &,Guid const &,UID const &,_FILETIME const &,Usn const &)
0x1400a2e25  mov     rbx, rax
0x1400a2e28  test    rax, rax
0x1400a2e2b  jz      short loc_1400A2DFA
0x1400a2e2d  call    cs:__imp_GetCurrentThreadId
0x1400a2e34  nop     dword ptr [rax+rax+00h]
0x1400a2e39  mov     [rsp+3D0h+var_390], rbx
0x1400a2e3e  mov     [rsp+3D0h+var_398], eax
0x1400a2e42  mov     dword ptr [rsp+3D0h+var_3A0], 0D91h
0x1400a2e4a  jmp     short loc_1400A2DE7
0x1400a2e4c  mov     rax, [rdx+10h]
0x1400a2e50  lea     rcx, [rbp+2D0h+var_320]; this
0x1400a2e54  mov     [rsp+3D0h+var_370], rax
0x1400a2e59  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x1400a2e5e  mov     rcx, [rsi+68h]
0x1400a2e62  lea     rdx, [rsp+3D0h+var_378]
0x1400a2e67  mov     [rsp+3D0h+var_380], r14d
0x1400a2e6c  lea     r9, [rbp+2D0h+var_320]
0x1400a2e70  mov     [rsp+3D0h+var_3B0], rdx; struct Usn *
0x1400a2e75  lea     r8, [rsp+3D0h+var_370]
0x1400a2e7a  lea     rdx, [rsp+3D0h+var_380]
0x1400a2e7f  mov     rax, [rcx]
0x1400a2e82  mov     [rsp+3D0h+var_378], r14
0x1400a2e87  mov     rax, [rax+28h]
0x1400a2e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a2e90  mov     qword ptr [rsp+3D0h+var_368], rax
0x1400a2e95  lea     r14, aUsnconsumerPro_1; "UsnConsumer::ProcessRename"
0x1400a2e9c  lea     r15, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a2ea3  test    rax, rax
0x1400a2ea6  jz      short loc_1400A2EF1
0x1400a2ea8  call    cs:__imp_GetCurrentThreadId
0x1400a2eaf  nop     dword ptr [rax+rax+00h]
0x1400a2eb4  mov     rcx, qword ptr [rsp+3D0h+var_368]
0x1400a2eb9  mov     [rsp+3D0h+var_390], rcx
0x1400a2ebe  mov     [rsp+3D0h+var_398], eax
0x1400a2ec2  mov     dword ptr [rsp+3D0h+var_3A0], 0D99h
0x1400a2eca  mov     r9d, [rcx]
0x1400a2ecd  mov     r8d, [rcx+8]
0x1400a2ed1  mov     edx, [rcx+4]
0x1400a2ed4  mov     [rsp+3D0h+var_3A8], r14
0x1400a2ed9  mov     [rsp+3D0h+var_3B0], r15
0x1400a2ede  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a2ee3  mov     r9, rax
0x1400a2ee6  test    rax, rax
0x1400a2ee9  jnz     loc_1400A32A6
0x1400a2eef  jmp     short loc_1400A2EF4
0x1400a2ef1  xor     r9d, r9d
0x1400a2ef4  cmp     [rsp+3D0h+var_380], 0
0x1400a2ef9  jz      loc_1400A31A2
0x1400a2eff  mov     rax, qword ptr [rbp+2D0h+var_2D8]
0x1400a2f03  sub     rax, [rbx+48h]
0x1400a2f07  jnz     short loc_1400A2F11
0x1400a2f09  mov     rax, qword ptr [rbp+2D0h+var_2D8+8]
0x1400a2f0d  sub     rax, [rbx+50h]
0x1400a2f11  test    rax, rax
0x1400a2f14  jnz     loc_1400A3100
0x1400a2f1a  cmp     [rbp+2D0h+arg_38], eax
0x1400a2f20  jnz     loc_1400A30C1
0x1400a2f26  mov     al, 2
0x1400a2f28  test    [rbx+2C0h], al
0x1400a2f2e  jnz     loc_1400A303C
0x1400a2f34  mov     rcx, rsi; this
0x1400a2f37  test    [rbp+2D0h+var_60], al
0x1400a2f3d  jnz     loc_1400A3088
0x1400a2f43  movups  xmm0, xmmword ptr [rbx+30h]
0x1400a2f47  mov     rax, [rbx+40h]
0x1400a2f4b  lea     r9, [rbp+2D0h+var_338]; struct UID *
0x1400a2f4f  mov     [rbp+2D0h+var_340], rax
0x1400a2f53  mov     r8, rbx; struct ID_RECORD *
0x1400a2f56  mov     rax, [rbp+2D0h+var_310]
0x1400a2f5a  mov     rdx, rdi; struct USN_RECORD_V2 *
0x1400a2f5d  movdqu  [rbp+2D0h+var_350], xmm0
0x1400a2f62  mov     [rbp+2D0h+var_328], rax
0x1400a2f66  movaps  xmm0, [rbp+2D0h+var_320]
0x1400a2f6a  movdqu  [rbp+2D0h+var_338], xmm0
0x1400a2f6f  mov     [rsp+3D0h+var_3B0], r12; struct Usn *
0x1400a2f74  call    ?UpdateIdRecord@UsnConsumer@@AEAAPEAVFrsStatus@@AEBUUSN_RECORD_V2@@AEAVID_RECORD@@AEBVUID@@PEBVUsn@@@Z; UsnConsumer::UpdateIdRecord(USN_RECORD_V2 const &,ID_RECORD &,UID const &,Usn const *)
0x1400a2f79  mov     r12, rax
0x1400a2f7c  test    rax, rax
0x1400a2f7f  jz      short loc_1400A2FC9
0x1400a2f81  call    cs:__imp_GetCurrentThreadId
0x1400a2f88  nop     dword ptr [rax+rax+00h]
0x1400a2f8d  mov     r9d, [r12]
0x1400a2f91  mov     r8d, [r12+8]
0x1400a2f96  mov     edx, [r12+4]
0x1400a2f9b  mov     [rsp+3D0h+var_390], r12
0x1400a2fa0  mov     [rsp+3D0h+var_398], eax
0x1400a2fa4  mov     dword ptr [rsp+3D0h+var_3A0], 0DAEh
0x1400a2fac  mov     [rsp+3D0h+var_3A8], r14
0x1400a2fb1  mov     [rsp+3D0h+var_3B0], r15
0x1400a2fb6  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a2fbb  mov     r9, rax
0x1400a2fbe  test    rax, rax
0x1400a2fc1  jnz     loc_1400A32A6
0x1400a2fc7  jmp     short loc_1400A2FCC
0x1400a2fc9  xor     r9d, r9d
0x1400a2fcc  lea     rdx, [rbp+2D0h+var_338]
0x1400a2fd0  lea     rcx, [rbp+2D0h+var_350]
0x1400a2fd4  call    ??8GVSN@@QEBA_NAEBV0@@Z; GVSN::operator==(GVSN const &)
0x1400a2fd9  test    al, al
0x1400a2fdb  jnz     loc_1400A32A6
0x1400a2fe1  test    byte ptr [rdi+34h], 10h
0x1400a2fe5  jz      loc_1400A32A6
0x1400a2feb  and     dword ptr [rsp+3D0h+var_3A0], 0
0x1400a2ff0  mov     r9, rbx; struct UID *
0x1400a2ff3  and     dword ptr [rsp+3D0h+var_3A8], 0
0x1400a2ff8  mov     r8, rdi; struct USN_RECORD_V2 *
0x1400a2ffb  mov     rdx, r13; struct _GUID *
0x1400a2ffe  mov     dword ptr [rsp+3D0h+var_3B0], 1; int
0x1400a3006  mov     rcx, rsi; this
0x1400a3009  call    ?SendDirToWalker@UsnConsumer@@AEAAPEAVFrsStatus@@AEBU_GUID@@AEBUUSN_RECORD_V2@@AEBVUID@@HHH@Z; UsnConsumer::SendDirToWalker(_GUID const &,USN_RECORD_V2 const &,UID const &,int,int,int)
0x1400a300e  mov     rbx, rax
0x1400a3011  test    rax, rax
0x1400a3014  jz      loc_1400A32A3
0x1400a301a  call    cs:__imp_GetCurrentThreadId
0x1400a3021  nop     dword ptr [rax+rax+00h]
0x1400a3026  mov     [rsp+3D0h+var_390], rbx
0x1400a302b  mov     [rsp+3D0h+var_398], eax
0x1400a302f  mov     dword ptr [rsp+3D0h+var_3A0], 0DCFh
0x1400a3037  jmp     loc_1400A3285
0x1400a303c  test    [rbp+2D0h+var_60], al
0x1400a3042  jnz     loc_1400A32A6
0x1400a3048  mov     r9, rdi; struct USN_RECORD_V2 *
0x1400a304b  lea     r8, [rbp+2D0h+var_320]; struct ID_RECORD *
0x1400a304f  mov     rdx, rbx; struct ID_RECORD *
0x1400a3052  mov     rcx, rsi; this
0x1400a3055  call    ?Validate@UsnConsumer@@AEAAPEAVFrsStatus@@AEAVID_RECORD@@AEBV3@AEBUUSN_RECORD_V2@@@Z; UsnConsumer::Validate(ID_RECORD &,ID_RECORD const &,USN_RECORD_V2 const &)
0x1400a305a  mov     rbx, rax
0x1400a305d  test    rax, rax
0x1400a3060  jz      loc_1400A32A3
0x1400a3066  call    cs:__imp_GetCurrentThreadId
0x1400a306d  nop     dword ptr [rax+rax+00h]
0x1400a3072  mov     [rsp+3D0h+var_390], rbx
0x1400a3077  mov     [rsp+3D0h+var_398], eax
0x1400a307b  mov     dword ptr [rsp+3D0h+var_3A0], 0DDAh
0x1400a3083  jmp     loc_1400A3285
0x1400a3088  mov     r8, rdi; struct USN_RECORD_V2 *
0x1400a308b  mov     rdx, rbx; struct ID_RECORD *
0x1400a308e  call    ?Mark@UsnConsumer@@AEAAPEAVFrsStatus@@AEAVID_RECORD@@AEBUUSN_RECORD_V2@@@Z; UsnConsumer::Mark(ID_RECORD &,USN_RECORD_V2 const &)
0x1400a3093  mov     rbx, rax
0x1400a3096  test    rax, rax
0x1400a3099  jz      loc_1400A32A3
0x1400a309f  call    cs:__imp_GetCurrentThreadId
0x1400a30a6  nop     dword ptr [rax+rax+00h]
0x1400a30ab  mov     [rsp+3D0h+var_390], rbx
0x1400a30b0  mov     [rsp+3D0h+var_398], eax
0x1400a30b4  mov     dword ptr [rsp+3D0h+var_3A0], 0DE6h
0x1400a30bc  jmp     loc_1400A3285
0x1400a30c1  xor     r9d, r9d; int
0x1400a30c4  mov     r8, rbx; struct ID_RECORD *
0x1400a30c7  mov     rdx, rdi; struct USN_RECORD_V2 *
0x1400a30ca  mov     rcx, rsi; this
0x1400a30cd  call    ?TombstoneIdRecord@UsnConsumer@@AEAAPEAVFrsStatus@@AEBUUSN_RECORD_V2@@AEAVID_RECORD@@H@Z; UsnConsumer::TombstoneIdRecord(USN_RECORD_V2 const &,ID_RECORD &,int)
0x1400a30d2  mov     rbx, rax
0x1400a30d5  test    rax, rax
0x1400a30d8  jz      loc_1400A32A3
0x1400a30de  call    cs:__imp_GetCurrentThreadId
0x1400a30e5  nop     dword ptr [rax+rax+00h]
0x1400a30ea  mov     [rsp+3D0h+var_390], rbx
0x1400a30ef  mov     [rsp+3D0h+var_398], eax
0x1400a30f3  mov     dword ptr [rsp+3D0h+var_3A0], 0DEAh
0x1400a30fb  jmp     loc_1400A3285
0x1400a3100  mov     al, 2
0x1400a3102  mov     r8, rbx; struct ID_RECORD *
0x1400a3105  mov     rdx, rdi; struct USN_RECORD_V2 *
0x1400a3108  mov     rcx, rsi; this
0x1400a310b  test    [rbp+2D0h+var_60], al
0x1400a3111  jnz     short loc_1400A316C
0x1400a3113  movups  xmm0, [rbp+2D0h+var_2D8]
0x1400a3117  lea     rax, [rbp+2D0h+var_2A4]
0x1400a311b  mov     [rsp+3D0h+var_3A0], r12; struct Usn *
0x1400a3120  mov     [rsp+3D0h+var_3A8], rax; struct _FILETIME *
0x1400a3125  lea     r9, [rsp+3D0h+var_368]; struct Guid *
0x1400a312a  lea     rax, [rbp+2D0h+var_320]
0x1400a312e  mov     [rsp+3D0h+var_3B0], rax; struct UID *
0x1400a3133  movdqu  [rsp+3D0h+var_368], xmm0
0x1400a3139  call    ?DeleteCreateIdRecords@UsnConsumer@@AEAAPEAVFrsStatus@@AEBUUSN_RECORD_V2@@AEAVID_RECORD@@AEBVGuid@@AEBVUID@@AEBU_FILETIME@@AEBVUsn@@@Z; UsnConsumer::DeleteCreateIdRecords(USN_RECORD_V2 const &,ID_RECORD &,Guid const &,UID const &,_FILETIME const &,Usn const &)
0x1400a313e  mov     rbx, rax
0x1400a3141  test    rax, rax
0x1400a3144  jz      loc_1400A32A3
0x1400a314a  call    cs:__imp_GetCurrentThreadId
0x1400a3151  nop     dword ptr [rax+rax+00h]
0x1400a3156  mov     [rsp+3D0h+var_390], rbx
0x1400a315b  mov     [rsp+3D0h+var_398], eax
0x1400a315f  mov     dword ptr [rsp+3D0h+var_3A0], 0DFAh
0x1400a3167  jmp     loc_1400A3285
0x1400a316c  xor     r9d, r9d; int
0x1400a316f  call    ?TombstoneIdRecord@UsnConsumer@@AEAAPEAVFrsStatus@@AEBUUSN_RECORD_V2@@AEAVID_RECORD@@H@Z; UsnConsumer::TombstoneIdRecord(USN_RECORD_V2 const &,ID_RECORD &,int)
0x1400a3174  mov     rbx, rax
0x1400a3177  test    rax, rax
0x1400a317a  jz      loc_1400A32A3
0x1400a3180  call    cs:__imp_GetCurrentThreadId
0x1400a3187  nop     dword ptr [rax+rax+00h]
0x1400a318c  mov     [rsp+3D0h+var_390], rbx
0x1400a3191  mov     [rsp+3D0h+var_398], eax
0x1400a3195  mov     dword ptr [rsp+3D0h+var_3A0], 0DFCh
0x1400a319d  jmp     loc_1400A3285
0x1400a31a2  cmp     qword ptr [rbx+10h], 1
0x1400a31a7  jz      short loc_1400A31E8
0x1400a31a9  xor     r9d, r9d; int
0x1400a31ac  mov     r8, rbx; struct ID_RECORD *
0x1400a31af  mov     rdx, rdi; struct USN_RECORD_V2 *
0x1400a31b2  mov     rcx, rsi; this
0x1400a31b5  call    ?TombstoneIdRecord@UsnConsumer@@AEAAPEAVFrsStatus@@AEBUUSN_RECORD_V2@@AEAVID_RECORD@@H@Z; UsnConsumer::TombstoneIdRecord(USN_RECORD_V2 const &,ID_RECORD &,int)
0x1400a31ba  mov     rbx, rax
0x1400a31bd  test    rax, rax
0x1400a31c0  jz      loc_1400A32A3
0x1400a31c6  call    cs:__imp_GetCurrentThreadId
0x1400a31cd  nop     dword ptr [rax+rax+00h]
0x1400a31d2  mov     [rsp+3D0h+var_390], rbx
0x1400a31d7  mov     [rsp+3D0h+var_398], eax
0x1400a31db  mov     dword ptr [rsp+3D0h+var_3A0], 0E05h
0x1400a31e3  jmp     loc_1400A3285
0x1400a31e8  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400a31ef  test    rax, rax
0x1400a31f2  jz      short loc_1400A323C
0x1400a31f4  cmp     dword ptr [rax+40h], 0
0x1400a31f8  jz      short loc_1400A323C
0x1400a31fa  cmp     dword ptr [rax+38h], 4
0x1400a31fe  jl      short loc_1400A323C
0x1400a3200  lea     rax, aUsnconsumerPro_0; "UsnConsumer::ProcessRename"
0x1400a3207  mov     dword ptr [rsp+3D0h+var_368+8], 0E08h
0x1400a320f  mov     qword ptr [rsp+3D0h+var_368], rax
0x1400a3214  lea     rdx, aContentSetRoot_1; "Content set root was moved: %?"
0x1400a321b  lea     rax, aUsnc; "USNC"
0x1400a3222  mov     dword ptr [rsp+3D0h+var_368+0Ch], 4
0x1400a322a  mov     r8, rbx
0x1400a322d  mov     [rsp+3D0h+var_358], rax
0x1400a3232  lea     rcx, [rsp+3D0h+var_368]
0x1400a3237  call    ??$DbgPrint@GVID_RECORD@@@dbgobj@@QEAA_KPEBGAEBVID_RECORD@@@Z; dbgobj::DbgPrint<ushort,ID_RECORD>(ushort const *,ID_RECORD const &)
0x1400a323c  and     [rbp+2D0h+var_340], 0
0x1400a3241  lea     r9, [rbp+2D0h+var_350]; struct UID *
0x1400a3245  and     [rsp+3D0h+var_3B0], 0
0x1400a324b  xorps   xmm0, xmm0
0x1400a324e  mov     r8, rbx; struct ID_RECORD *
0x1400a3251  mov     rdx, rdi; struct USN_RECORD_V2 *
0x1400a3254  mov     rcx, rsi; this
0x1400a3257  movups  [rbp+2D0h+var_350], xmm0
0x1400a325b  call    ?UpdateIdRecord@UsnConsumer@@AEAAPEAVFrsStatus@@AEBUUSN_RECORD_V2@@AEAVID_RECORD@@AEBVUID@@PEBVUsn@@@Z; UsnConsumer::UpdateIdRecord(USN_RECORD_V2 const &,ID_RECORD &,UID const &,Usn const *)
0x1400a3260  mov     rbx, rax
0x1400a3263  test    rax, rax
0x1400a3266  jz      short loc_1400A32A3
0x1400a3268  call    cs:__imp_GetCurrentThreadId
0x1400a326f  nop     dword ptr [rax+rax+00h]
0x1400a3274  mov     [rsp+3D0h+var_390], rbx
0x1400a3279  mov     [rsp+3D0h+var_398], eax
0x1400a327d  mov     dword ptr [rsp+3D0h+var_3A0], 0E09h
0x1400a3285  mov     r9d, [rbx]
0x1400a3288  mov     r8d, [rbx+8]
0x1400a328c  mov     edx, [rbx+4]
0x1400a328f  mov     [rsp+3D0h+var_3A8], r14
0x1400a3294  mov     [rsp+3D0h+var_3B0], r15
0x1400a3299  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a329e  mov     r9, rax
0x1400a32a1  jmp     short loc_1400A32A6
  ... truncated ...
```
