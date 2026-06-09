# Config::AdConfig::ReadServiceName(FrsStringImpl<ushort,char> &)

- ea: `0x1401ef600`
- end: `0x1401ef972`
- name: `?ReadServiceName@AdConfig@Config@@QEAAPEAVFrsStatus@@AEAV?$FrsStringImpl@GD@@@Z`
- size: `882`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x140202a50`

## callees

- `0x14000c910`
- `0x14000cd1c`
- `0x140010680`
- `0x14002179c`
- `0x1401b9494`
- `0x1401de184`
- `0x1401de240`
- `0x1401de77c`
- `0x1401de7cc`
- `0x1401e4584`
- `0x1401e684c`
- `0x1401ef600`
- `0x1401f3320`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401ef6f1`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef79d`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef8b4`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef903`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef6f1`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef79d`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef8b4`
- `KERNEL32!GetCurrentThreadId` at `0x1401ef903`

## string_xrefs

- `0x1401ef8a3`: `Failed to get RootDSE, check access rights`
- `0x1401ef6e0`: `Failed in searching dsServiceName attribute`
- `0x1401ef70e`: `Config::AdConfig::ReadServiceName`
- `0x1401ef7ba`: `Config::AdConfig::ReadServiceName`
- `0x1401ef8d1`: `Config::AdConfig::ReadServiceName`
- `0x1401ef628`: `dsServiceName`
- `0x1401ef6b8`: `Config::AdConfig::ReadServiceName`
- `0x1401ef764`: `Config::AdConfig::ReadServiceName`
- `0x1401ef811`: `Config::AdConfig::ReadServiceName`
- `0x1401ef87b`: `Config::AdConfig::ReadServiceName`
- `0x1401ef78c`: `Missing dsServiceName attribute`
- `0x1401ef84e`: `dsServiceName:%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Config::AdConfig::ReadServiceName(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  struct FrsStatus *started; // r14
  __int64 v6; // rcx
  Config::AdStrAttr *Attr; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  const unsigned __int16 *Value; // rax
  DWORD v11; // eax
  __int64 v12; // rcx
  int v14; // [rsp+38h] [rbp-D0h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C8h]
  DWORD v16; // [rsp+40h] [rbp-C8h]
  unsigned __int16 *v17; // [rsp+48h] [rbp-C0h]
  const wchar_t *v18; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+60h] [rbp-A8h]
  const wchar_t *v20; // [rsp+68h] [rbp-A0h]
  _BYTE v21[96]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v22[368]; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int16 *v23; // [rsp+268h] [rbp+160h] BYREF

  v23 = L"dsServiceName";
  Config::AdQuery::AdQuery((Config::AdQuery *)v22);
  Config::AdObject::AdObject((Config::AdObject *)v21);
  v4 = 0;
  started = Config::AdQuery::StartSearch(
              (Config::AdQuery *)v22,
              *(struct Config::AdSession **)(a1 + 40),
              &pServiceName,
              0,
              (const unsigned __int16 **)&v23,
              1u,
              0,
              0,
              L"(objectCategory=*)",
              0x8CA0u);
  if ( started )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v18 = L"Config::AdConfig::ReadServiceName";
      v19 = 0x200001DEBLL;
      v20 = L"CFAD";
      dbgobj::DbgPrint<unsigned short>(&v18, L"Failed in searching dsServiceName attribute");
    }
    v17 = (unsigned __int16 *)started;
    CurrentThreadId = GetCurrentThreadId();
    v14 = 7661;
    goto LABEL_24;
  }
  if ( Config::AdQuery::GetFirstObject((Config::AdQuery *)v22, (struct Config::AdObject *)v21) )
  {
    Attr = Config::AdAttrList::FindAttr((Config::AdAttrList *)v21, L"dsServiceName");
    if ( !Attr )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v18 = L"Config::AdConfig::ReadServiceName";
        v19 = 0x200001DF6LL;
        v20 = L"CFAD";
        dbgobj::DbgPrint<unsigned short>(&v18, L"Missing dsServiceName attribute");
      }
      v16 = GetCurrentThreadId();
      v9 = FrsStatusList::PushNewError(
             v8,
             1168,
             0,
             1,
             "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
             "Config::AdConfig::ReadServiceName",
             7671,
             v16,
             0);
      goto LABEL_25;
    }
    Value = Config::AdStrAttr::GetValue(Attr);
    FrsStringImpl<unsigned short,char>::Set(a2, Value);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v18 = L"Config::AdConfig::ReadServiceName";
      v19 = 0x400001DFCLL;
      v20 = L"CFAD";
      v23 = (unsigned __int16 *)(*(_QWORD *)a2 + 18LL);
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v18, L"dsServiceName:%ws", &v23);
    }
  }
  else
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v18 = L"Config::AdConfig::ReadServiceName";
      v19 = 0x200001E03LL;
      v20 = L"CFAD";
      dbgobj::DbgPrint<unsigned short>(&v18, L"Failed to get RootDSE, check access rights");
    }
    v11 = GetCurrentThreadId();
    started = (struct FrsStatus *)FrsStatusList::PushNewError(
                                    v12,
                                    5,
                                    0,
                                    1,
                                    "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
                                    "Config::AdConfig::ReadServiceName",
                                    7684,
                                    v11,
                                    0);
    if ( started )
    {
      v17 = (unsigned __int16 *)started;
      CurrentThreadId = GetCurrentThreadId();
      v14 = 7687;
LABEL_24:
      v9 = FrsStatusList::PushNewError(
             v6,
             *((unsigned int *)started + 1),
             *((unsigned int *)started + 2),
             *(unsigned int *)started,
             "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
             "Config::AdConfig::ReadServiceName",
             v14,
             CurrentThreadId,
             v17);
LABEL_25:
      v4 = v9;
    }
  }
  Config::AdObject::~AdObject((Config::AdObject *)v21);
  Config::AdQuery::~AdQuery((Config::AdQuery *)v22);
  return v4;
}

```

## disassembly

```asm
0x1401ef600  mov     rax, rsp
0x1401ef603  mov     [rax+10h], rbx
0x1401ef607  mov     [rax+18h], rsi
0x1401ef60b  mov     [rax+20h], rdi
0x1401ef60f  push    rbp
0x1401ef610  push    r14
0x1401ef612  push    r15
0x1401ef614  lea     rbp, [rax-158h]
0x1401ef61b  sub     rsp, 240h
0x1401ef622  mov     rsi, rdx
0x1401ef625  mov     rbx, rcx
0x1401ef628  lea     r15, aDsservicename; "dsServiceName"
0x1401ef62f  mov     [rbp+150h+arg_0], r15
0x1401ef636  lea     rcx, [rbp+150h+var_180]; this
0x1401ef63a  call    ??0AdQuery@Config@@QEAA@XZ; Config::AdQuery::AdQuery(void)
0x1401ef63f  nop
0x1401ef640  lea     rcx, [rsp+250h+var_1E0]; this
0x1401ef645  call    ??0AdObject@Config@@QEAA@XZ; Config::AdObject::AdObject(void)
0x1401ef64a  nop
0x1401ef64b  mov     [rsp+250h+var_208], 8CA0h; unsigned int
0x1401ef653  lea     rax, aObjectcategory_6; "(objectCategory=*)"
0x1401ef65a  mov     [rsp+250h+var_210], rax; unsigned __int16 *
0x1401ef65f  xor     edi, edi
0x1401ef661  mov     [rsp+250h+var_218], edi; unsigned int
0x1401ef665  mov     [rsp+250h+var_220], rdi; unsigned __int16 **
0x1401ef66a  mov     [rsp+250h+var_228], 1; unsigned int
0x1401ef672  lea     rax, [rbp+150h+arg_0]
0x1401ef679  mov     [rsp+250h+var_230], rax; unsigned __int16 **
0x1401ef67e  xor     r9d, r9d; unsigned int
0x1401ef681  lea     r8, pServiceName; unsigned __int16 *
0x1401ef688  mov     rdx, [rbx+28h]; struct Config::AdSession *
0x1401ef68c  lea     rcx, [rbp+150h+var_180]; this
0x1401ef690  call    ?StartSearch@AdQuery@Config@@QEAAPEAVFrsStatus@@PEAVAdSession@2@PEBGKPEAPEBGK2K1K@Z; Config::AdQuery::StartSearch(Config::AdSession *,ushort const *,ulong,ushort const * *,ulong,ushort const * *,ulong,ushort const *,ulong)
0x1401ef695  mov     r14, rax
0x1401ef698  test    rax, rax
0x1401ef69b  jz      loc_1401EF721
0x1401ef6a1  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ef6a8  test    rcx, rcx
0x1401ef6ab  jz      short loc_1401EF6F1
0x1401ef6ad  cmp     [rcx+40h], edi
0x1401ef6b0  jz      short loc_1401EF6F1
0x1401ef6b2  cmp     dword ptr [rcx+38h], 2
0x1401ef6b6  jl      short loc_1401EF6F1
0x1401ef6b8  lea     rax, aConfigAdconfig_8; "Config::AdConfig::ReadServiceName"
0x1401ef6bf  mov     [rsp+250h+var_200], rax
0x1401ef6c4  mov     dword ptr [rsp+250h+var_1F8], 1DEBh
0x1401ef6cc  mov     dword ptr [rsp+250h+var_1F8+4], 2
0x1401ef6d4  lea     rax, aCfad; "CFAD"
0x1401ef6db  mov     [rsp+250h+var_1F0], rax
0x1401ef6e0  lea     rdx, aFailedInSearch; "Failed in searching dsServiceName attri"...
0x1401ef6e7  lea     rcx, [rsp+250h+var_200]
0x1401ef6ec  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1401ef6f1  call    cs:__imp_GetCurrentThreadId
0x1401ef6f8  nop     dword ptr [rax+rax+00h]
0x1401ef6fd  mov     [rsp+250h+var_210], r14
0x1401ef702  mov     [rsp+250h+var_218], eax
0x1401ef706  mov     dword ptr [rsp+250h+var_220], 1DEDh
0x1401ef70e  lea     rbx, aConfigAdconfig_34; "Config::AdConfig::ReadServiceName"
0x1401ef715  lea     rsi, aBaseFsRemotefs_10; "base\\fs\\remotefs\\frs\\src\\ad\\ad.cp"...
0x1401ef71c  jmp     loc_1401EF920
0x1401ef721  lea     rdx, [rsp+250h+var_1E0]; struct Config::AdObject *
0x1401ef726  lea     rcx, [rbp+150h+var_180]; this
0x1401ef72a  call    ?GetFirstObject@AdQuery@Config@@QEAAHPEAVAdObject@2@@Z; Config::AdQuery::GetFirstObject(Config::AdObject *)
0x1401ef72f  test    eax, eax
0x1401ef731  jz      loc_1401EF864
0x1401ef737  mov     rdx, r15; unsigned __int16 *
0x1401ef73a  lea     rcx, [rsp+250h+var_1E0]; this
0x1401ef73f  call    ?FindAttr@AdAttrList@Config@@QEBAPEAVAdAttr@2@PEBG@Z; Config::AdAttrList::FindAttr(ushort const *)
0x1401ef744  test    rax, rax
0x1401ef747  jnz     loc_1401EF7DB
0x1401ef74d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ef754  test    rax, rax
0x1401ef757  jz      short loc_1401EF79D
0x1401ef759  cmp     [rax+40h], edi
0x1401ef75c  jz      short loc_1401EF79D
0x1401ef75e  cmp     dword ptr [rax+38h], 2
0x1401ef762  jl      short loc_1401EF79D
0x1401ef764  lea     rax, aConfigAdconfig_8; "Config::AdConfig::ReadServiceName"
0x1401ef76b  mov     [rsp+250h+var_200], rax
0x1401ef770  mov     dword ptr [rsp+250h+var_1F8], 1DF6h
0x1401ef778  mov     dword ptr [rsp+250h+var_1F8+4], 2
0x1401ef780  lea     rax, aCfad; "CFAD"
0x1401ef787  mov     [rsp+250h+var_1F0], rax
0x1401ef78c  lea     rdx, aMissingDsservi; "Missing dsServiceName attribute"
0x1401ef793  lea     rcx, [rsp+250h+var_200]
0x1401ef798  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1401ef79d  call    cs:__imp_GetCurrentThreadId
0x1401ef7a4  nop     dword ptr [rax+rax+00h]
0x1401ef7a9  mov     [rsp+250h+var_210], rdi
0x1401ef7ae  mov     [rsp+250h+var_218], eax
0x1401ef7b2  mov     dword ptr [rsp+250h+var_220], 1DF7h
0x1401ef7ba  lea     rbx, aConfigAdconfig_34; "Config::AdConfig::ReadServiceName"
0x1401ef7c1  lea     rsi, aBaseFsRemotefs_10; "base\\fs\\remotefs\\frs\\src\\ad\\ad.cp"...
0x1401ef7c8  mov     r9d, 1
0x1401ef7ce  xor     r8d, r8d
0x1401ef7d1  mov     edx, 490h
0x1401ef7d6  jmp     loc_1401EF92B
0x1401ef7db  mov     rcx, rax; this
0x1401ef7de  call    ?GetValue@AdStrAttr@Config@@QEBAPEBGXZ; Config::AdStrAttr::GetValue(void)
0x1401ef7e3  mov     rdx, rax
0x1401ef7e6  mov     rcx, rsi
0x1401ef7e9  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401ef7ee  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ef7f5  test    rax, rax
0x1401ef7f8  jz      loc_1401EF93D
0x1401ef7fe  cmp     [rax+40h], edi
0x1401ef801  jz      loc_1401EF93D
0x1401ef807  cmp     dword ptr [rax+38h], 4
0x1401ef80b  jl      loc_1401EF93D
0x1401ef811  lea     rax, aConfigAdconfig_8; "Config::AdConfig::ReadServiceName"
0x1401ef818  mov     [rsp+250h+var_200], rax
0x1401ef81d  mov     dword ptr [rsp+250h+var_1F8], 1DFCh
0x1401ef825  mov     dword ptr [rsp+250h+var_1F8+4], 4
0x1401ef82d  lea     rax, aCfad; "CFAD"
0x1401ef834  mov     [rsp+250h+var_1F0], rax
0x1401ef839  mov     rax, [rsi]
0x1401ef83c  add     rax, 12h
0x1401ef840  mov     [rbp+150h+arg_0], rax
0x1401ef847  lea     r8, [rbp+150h+arg_0]
0x1401ef84e  lea     rdx, aDsservicenameW; "dsServiceName:%ws"
0x1401ef855  lea     rcx, [rsp+250h+var_200]
0x1401ef85a  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1401ef85f  jmp     loc_1401EF93D
0x1401ef864  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ef86b  test    rax, rax
0x1401ef86e  jz      short loc_1401EF8B4
0x1401ef870  cmp     [rax+40h], edi
0x1401ef873  jz      short loc_1401EF8B4
0x1401ef875  cmp     dword ptr [rax+38h], 2
0x1401ef879  jl      short loc_1401EF8B4
0x1401ef87b  lea     rax, aConfigAdconfig_8; "Config::AdConfig::ReadServiceName"
0x1401ef882  mov     [rsp+250h+var_200], rax
0x1401ef887  mov     dword ptr [rsp+250h+var_1F8], 1E03h
0x1401ef88f  mov     dword ptr [rsp+250h+var_1F8+4], 2
0x1401ef897  lea     rax, aCfad; "CFAD"
0x1401ef89e  mov     [rsp+250h+var_1F0], rax
0x1401ef8a3  lea     rdx, aFailedToGetRoo; "Failed to get RootDSE, check access rig"...
0x1401ef8aa  lea     rcx, [rsp+250h+var_200]
0x1401ef8af  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1401ef8b4  call    cs:__imp_GetCurrentThreadId
0x1401ef8bb  nop     dword ptr [rax+rax+00h]
0x1401ef8c0  mov     [rsp+250h+var_210], rdi
0x1401ef8c5  mov     [rsp+250h+var_218], eax
0x1401ef8c9  mov     dword ptr [rsp+250h+var_220], 1E04h
0x1401ef8d1  lea     rbx, aConfigAdconfig_34; "Config::AdConfig::ReadServiceName"
0x1401ef8d8  mov     qword ptr [rsp+250h+var_228], rbx
0x1401ef8dd  lea     rsi, aBaseFsRemotefs_10; "base\\fs\\remotefs\\frs\\src\\ad\\ad.cp"...
0x1401ef8e4  mov     [rsp+250h+var_230], rsi
0x1401ef8e9  mov     r9d, 1
0x1401ef8ef  xor     r8d, r8d
0x1401ef8f2  lea     edx, [r9+4]
0x1401ef8f6  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401ef8fb  mov     r14, rax
0x1401ef8fe  test    rax, rax
0x1401ef901  jz      short loc_1401EF93D
0x1401ef903  call    cs:__imp_GetCurrentThreadId
0x1401ef90a  nop     dword ptr [rax+rax+00h]
0x1401ef90f  mov     [rsp+250h+var_210], r14
0x1401ef914  mov     [rsp+250h+var_218], eax
0x1401ef918  mov     dword ptr [rsp+250h+var_220], 1E07h
0x1401ef920  mov     r9d, [r14]
0x1401ef923  mov     r8d, [r14+8]
0x1401ef927  mov     edx, [r14+4]
0x1401ef92b  mov     qword ptr [rsp+250h+var_228], rbx
0x1401ef930  mov     [rsp+250h+var_230], rsi
0x1401ef935  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401ef93a  mov     rdi, rax
0x1401ef93d  lea     rcx, [rsp+250h+var_1E0]; this
0x1401ef942  call    ??1AdObject@Config@@QEAA@XZ; Config::AdObject::~AdObject(void)
0x1401ef947  nop
0x1401ef948  lea     rcx, [rbp+150h+var_180]; this
0x1401ef94c  call    ??1AdQuery@Config@@UEAA@XZ; Config::AdQuery::~AdQuery(void)
0x1401ef951  mov     rax, rdi
0x1401ef954  lea     r11, [rsp+250h+var_10]
0x1401ef95c  mov     rbx, [r11+28h]
0x1401ef960  mov     rsi, [r11+30h]
0x1401ef964  mov     rdi, [r11+38h]
0x1401ef968  mov     rsp, r11
0x1401ef96b  pop     r15
0x1401ef96d  pop     r14
0x1401ef96f  pop     rbp
0x1401ef970  retn
```
