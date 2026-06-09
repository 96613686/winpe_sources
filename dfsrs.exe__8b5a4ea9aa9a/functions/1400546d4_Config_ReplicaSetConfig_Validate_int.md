# Config::ReplicaSetConfig::Validate(int)

- ea: `0x1400546d4`
- end: `0x140054e6e`
- name: `?Validate@ReplicaSetConfig@Config@@QEBAPEAVFrsStatus@@H@Z`
- size: `1946`
- prototype: `struct FrsStatus *__fastcall(Config::ReplicaSetConfig *__hidden this, int)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x140061238`
- `0x1401ec574`

## callees

- `0x14000cb00`
- `0x14000cd1c`
- `0x14000e34c`
- `0x14001a8f8`
- `0x14001afd0`
- `0x14001c030`
- `0x14003c928`
- `0x14003d368`
- `0x140046fec`
- `0x14004779c`
- `0x140047e14`
- `0x140047e4c`
- `0x140047fd8`
- `0x1400480d0`
- `0x140052ae8`
- `0x1400546d4`
- `0x14005e8cc`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140054828`
- `KERNEL32!GetCurrentThreadId` at `0x140054893`
- `KERNEL32!GetCurrentThreadId` at `0x140054b7f`
- `KERNEL32!GetCurrentThreadId` at `0x140054bd7`
- `KERNEL32!GetCurrentThreadId` at `0x140054cc1`
- `KERNEL32!GetCurrentThreadId` at `0x140054dd4`
- `KERNEL32!GetCurrentThreadId` at `0x140054dfb`
- `KERNEL32!GetCurrentThreadId` at `0x140054828`
- `KERNEL32!GetCurrentThreadId` at `0x140054893`
- `KERNEL32!GetCurrentThreadId` at `0x140054b7f`
- `KERNEL32!GetCurrentThreadId` at `0x140054bd7`
- `KERNEL32!GetCurrentThreadId` at `0x140054cc1`
- `KERNEL32!GetCurrentThreadId` at `0x140054dd4`
- `KERNEL32!GetCurrentThreadId` at `0x140054dfb`

## string_xrefs

- `0x1400547ac`: `Config::ReplicaSetConfig::Validate`
- `0x140054c3d`: `Config::ReplicaSetConfig::Validate`
- `0x140054d54`: `Config::ReplicaSetConfig::Validate`
- `0x140054cec`: `Config::ReplicaSetConfig::Validate`
- `0x140054e22`: `Config::ReplicaSetConfig::Validate`
- `0x140054cf8`: `base\fs\remotefs\frs\src\config\replica.cpp`
- `0x140054e2e`: `base\fs\remotefs\frs\src\config\replica.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct FrsStatus *__fastcall Config::ReplicaSetConfig::Validate(Config::ReplicaSetConfig *this, unsigned int a2)
{
  Config::ParamBlock **v3; // rsi
  struct FrsStatus *v4; // rdi
  __int64 v5; // rbx
  int v6; // eax
  __int64 v7; // rdx
  int v8; // eax
  const unsigned __int16 *v9; // rax
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // rdx
  const unsigned __int16 *v16; // rax
  __int64 v17; // r9
  __int64 v18; // rcx
  const unsigned __int16 *v19; // rax
  __int64 v20; // r9
  __int64 v21; // rcx
  unsigned int i; // r15d
  __int64 v23; // r14
  const unsigned __int16 *v24; // rax
  __int64 v25; // rcx
  Config::ConnectionList *v26; // r12
  unsigned int j; // r13d
  __int64 v28; // r15
  Config::ParamBlock *v29; // rax
  const unsigned __int16 *v30; // rax
  __int64 v31; // rcx
  const unsigned __int16 *v32; // rax
  __int64 v33; // rcx
  const unsigned __int16 *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rax
  const unsigned __int16 *v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rcx
  const unsigned __int16 *v41; // rax
  __int64 v42; // rcx
  int v44; // [rsp+30h] [rbp-D0h]
  DWORD CurrentThreadId; // [rsp+38h] [rbp-C8h]
  DWORD v46; // [rsp+38h] [rbp-C8h]
  DWORD v47; // [rsp+38h] [rbp-C8h]
  struct FrsStatus *v48; // [rsp+40h] [rbp-C0h]
  const wchar_t *v49; // [rsp+50h] [rbp-B0h] BYREF
  int v50; // [rsp+58h] [rbp-A8h]
  int v51; // [rsp+5Ch] [rbp-A4h]
  const wchar_t *v52; // [rsp+60h] [rbp-A0h]
  _BYTE v53[40]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v54; // [rsp+98h] [rbp-68h] BYREF
  __int64 v55; // [rsp+A0h] [rbp-60h]
  _BYTE v56[32]; // [rsp+C0h] [rbp-40h] BYREF
  char v57[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v58; // [rsp+E8h] [rbp-18h]
  __int64 v59; // [rsp+F0h] [rbp-10h]
  _QWORD v60[14]; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v62; // [rsp+198h] [rbp+98h] BYREF
  __int64 v63; // [rsp+1A0h] [rbp+A0h] BYREF
  struct FrsStatus *v64; // [rsp+1A8h] [rbp+A8h] BYREF

  v62 = a2;
  Config::ParamList::ParamList((Config::ParamList *)v53);
  Config::ParamList::ParamList((Config::ParamList *)v56);
  v3 = (Config::ParamBlock **)((char *)this + 144);
  v4 = Config::ParamBlock::CheckParameters(*v3, (struct Config::ParamList *)v53, (struct Config::ParamList *)v56);
  v64 = v4;
  v5 = 0;
  if ( v4 )
  {
    if ( (unsigned int)((v55 - v54) >> 3) )
    {
      v16 = Config::StringParam::Get((Config::ParamBlock *)((char *)*v3 + 240));
      Config::ParamBlock::LogParamErrors(v18, v53, 5, v17 + 368, v16);
      v48 = v4;
      CurrentThreadId = GetCurrentThreadId();
      v44 = 1825;
LABEL_50:
      v13 = *(unsigned int *)v4;
      v14 = *((unsigned int *)v4 + 2);
      v15 = *((unsigned int *)v4 + 1);
      goto LABEL_51;
    }
    if ( (unsigned int)((v59 - v58) >> 3) )
    {
      v19 = Config::StringParam::Get((Config::ParamBlock *)((char *)*v3 + 240));
      Config::ParamBlock::LogParamWarnings(v21, v56, 5, v20 + 368, v19);
      PtrList<Config::VolumeConfig>::DeleteAll(v57);
    }
LABEL_15:
    for ( i = 0; ; i = v62 + 1 )
    {
      v62 = i;
      if ( i >= (*(unsigned int (__fastcall **)(__int64))(*((_QWORD *)*v3 + 113) + 40LL))((__int64)*v3 + 904)
        || !(unsigned int)IsConfigParamFrsStatusValid(v4) )
      {
        break;
      }
      CLEAR_ERROR(&v64);
      v23 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*((_QWORD *)*v3 + 113) + 48LL))((__int64)*v3 + 904, i);
      if ( Config::ConnectionList::Find(
             (Config::ParamBlock *)((char *)*v3 + 904),
             (const struct _GUID *)(v23 + 136),
             i + 1) )
      {
        *(_DWORD *)(v23 + 132) |= 0x20u;
        v63 = v23 + 104;
        std::vector<ReplicaSetManager *>::push_back(&v54, &v63);
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v49 = L"Config::ReplicaSetConfig::Validate";
          v50 = 1854;
          v51 = 4;
          v52 = L"CREP";
          v63 = v23 + 152;
          dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v49, L"Duplicate memberId:%ws", &v63);
        }
        v41 = Config::StringParam::Get((Config::StringParam *)(*((_QWORD *)this + 18) + 240LL));
        Config::ParamBlock::LogParamErrors(v42, v53, 6, v23 + 152, v41);
        v48 = 0;
        CurrentThreadId = GetCurrentThreadId();
        v44 = 1862;
        goto LABEL_10;
      }
      v4 = Config::ParamBlock::CheckParameters(
             (Config::ParamBlock *)v23,
             (struct Config::ParamList *)v53,
             (struct Config::ParamList *)v56);
      v64 = v4;
      if ( v4 )
      {
        if ( (unsigned int)((v55 - v54) >> 3) )
        {
          v32 = Config::StringParam::Get((Config::StringParam *)(*((_QWORD *)this + 18) + 240LL));
          Config::ParamBlock::LogParamErrors(v33, v53, 6, v23 + 152, v32);
          v48 = v4;
          CurrentThreadId = GetCurrentThreadId();
          v44 = 1874;
          goto LABEL_50;
        }
        if ( (unsigned int)((v59 - v58) >> 3) )
        {
          v24 = Config::StringParam::Get((Config::ParamBlock *)((char *)*v3 + 240));
          Config::ParamBlock::LogParamWarnings(v25, v56, 6, v23 + 152, v24);
          PtrList<Config::VolumeConfig>::DeleteAll(v57);
        }
      }
      Config::Member::ScopedMemberConnectionList::ScopedMemberConnectionList(
        (Config::Member::ScopedMemberConnectionList *)v60,
        (const struct Member *)v23);
      v26 = (Config::ConnectionList *)(v60[0] + 392LL);
      for ( j = 0;
            j < (*(unsigned int (__fastcall **)(Config::ConnectionList *))(*(_QWORD *)v26 + 40LL))(v26)
         && (unsigned int)IsConfigParamFrsStatusValid(v4);
            j = v63 )
      {
        CLEAR_ERROR(&v64);
        v28 = (*(__int64 (__fastcall **)(Config::ConnectionList *, _QWORD))(*(_QWORD *)v26 + 48LL))(v26, j);
        LODWORD(v63) = j + 1;
        if ( Config::ConnectionList::Find(v26, (const struct _GUID *)(v28 + 136), j + 1) )
        {
          *(_DWORD *)(v28 + 132) |= 0x20u;
          v63 = v28 + 104;
          std::vector<ReplicaSetManager *>::push_back(&v54, &v63);
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v49 = L"Config::ReplicaSetConfig::Validate";
            v50 = 1907;
            v51 = 4;
            v52 = L"CREP";
            v63 = v28 + 152;
            dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v49, L"Duplicate connId:%ws", &v63);
          }
          v38 = Config::StringParam::Get((Config::StringParam *)(*((_QWORD *)this + 18) + 240LL));
          Config::ParamBlock::LogParamErrors(v39, v53, 6, v23 + 152, v38);
          v47 = GetCurrentThreadId();
          v37 = FrsStatusList::PushNewError(
                  v40,
                  9109,
                  0,
                  3,
                  "base\\fs\\remotefs\\frs\\src\\config\\replica.cpp",
                  "Config::ReplicaSetConfig::Validate",
                  1914,
                  v47,
                  0);
          goto LABEL_42;
        }
        v29 = (Config::ParamBlock *)(*(__int64 (__fastcall **)(Config::ConnectionList *, _QWORD))(*(_QWORD *)v26 + 48LL))(
                                      v26,
                                      j);
        v4 = Config::ParamBlock::CheckParameters(v29, (struct Config::ParamList *)v53, (struct Config::ParamList *)v56);
        v64 = v4;
        if ( v4 )
        {
          if ( (unsigned int)((v55 - v54) >> 3) )
          {
            v34 = Config::StringParam::Get((Config::StringParam *)(*((_QWORD *)this + 18) + 240LL));
            Config::ParamBlock::LogParamErrors(v35, v53, 7, v28 + 152, v34);
            v46 = GetCurrentThreadId();
            v37 = FrsStatusList::PushNewError(
                    v36,
                    *((unsigned int *)v4 + 1),
                    *((unsigned int *)v4 + 2),
                    *(unsigned int *)v4,
                    "base\\fs\\remotefs\\frs\\src\\config\\replica.cpp",
                    "Config::ReplicaSetConfig::Validate",
                    1926,
                    v46,
                    v4);
LABEL_42:
            v5 = v37;
            Config::Member::ScopedMemberConnectionList::~ScopedMemberConnectionList((Config::Member::ScopedMemberConnectionList *)v60);
            goto LABEL_52;
          }
          if ( (unsigned int)((v59 - v58) >> 3) )
          {
            v30 = Config::StringParam::Get((Config::ParamBlock *)((char *)*v3 + 240));
            Config::ParamBlock::LogParamWarnings(v31, v56, 7, v28 + 152, v30);
            PtrList<Config::VolumeConfig>::DeleteAll(v57);
          }
        }
      }
      if ( (unsigned int)IsConfigParamFrsStatusValid(v4) )
      {
        CLEAR_ERROR(&v64);
        v4 = v64;
      }
      Config::Member::ScopedMemberConnectionList::~ScopedMemberConnectionList((Config::Member::ScopedMemberConnectionList *)v60);
    }
    if ( !v4 )
      goto LABEL_52;
    v48 = v4;
    CurrentThreadId = GetCurrentThreadId();
    v44 = 1946;
    goto LABEL_50;
  }
  v6 = Config::BoolParam::Get((Config::ParamBlock *)((char *)*v3 + 528));
  if ( !v6 )
    goto LABEL_15;
  v8 = v6 - 1;
  if ( !v8 || (unsigned int)(v8 - 1) < 2 )
    goto LABEL_15;
  *(_DWORD *)(v7 + 556) |= 8u;
  v63 = (__int64)*v3 + 528;
  std::vector<ReplicaSetManager *>::push_back(&v54, &v63);
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v49 = L"Config::ReplicaSetConfig::Validate";
    v50 = 1802;
    v51 = 4;
    v52 = L"CREP";
    v62 = Config::BoolParam::Get((Config::ParamBlock *)((char *)*v3 + 528));
    dbgobj::DbgPrint<unsigned short,unsigned int>(&v49, L"Invalid replication group type:%d", &v62);
  }
  v9 = Config::StringParam::Get((Config::ParamBlock *)((char *)*v3 + 240));
  Config::ParamBlock::LogParamErrors(v11, v53, 5, v10 + 368, v9);
  v48 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v44 = 1809;
LABEL_10:
  v13 = 3;
  v14 = 0;
  v15 = 9109;
LABEL_51:
  v5 = FrsStatusList::PushNewError(
         v12,
         v15,
         v14,
         v13,
         "base\\fs\\remotefs\\frs\\src\\config\\replica.cpp",
         "Config::ReplicaSetConfig::Validate",
         v44,
         CurrentThreadId,
         v48);
LABEL_52:
  Config::ParamList::~ParamList((Config::ParamList *)v56);
  Config::ParamList::~ParamList((Config::ParamList *)v53);
  return (struct FrsStatus *)v5;
}

```

## disassembly

```asm
0x1400546d4  mov     [rsp-8+arg_8], edx
0x1400546d8  mov     [rsp-8+arg_0], rcx
0x1400546dd  push    rbp
0x1400546de  push    rbx
0x1400546df  push    rsi
0x1400546e0  push    rdi
0x1400546e1  push    r12
0x1400546e3  push    r13
0x1400546e5  push    r14
0x1400546e7  push    r15
0x1400546e9  lea     rbp, [rsp-48h]
0x1400546ee  sub     rsp, 148h
0x1400546f5  mov     rsi, rcx
0x1400546f8  lea     rcx, [rsp+180h+var_110]; this
0x1400546fd  call    ??0ParamList@Config@@QEAA@XZ; Config::ParamList::ParamList(void)
0x140054702  nop
0x140054703  lea     rcx, [rbp+80h+var_C0]; this
0x140054707  call    ??0ParamList@Config@@QEAA@XZ; Config::ParamList::ParamList(void)
0x14005470c  nop
0x14005470d  add     rsi, 90h
0x140054714  lea     r8, [rbp+80h+var_C0]; struct Config::ParamList *
0x140054718  lea     rdx, [rsp+180h+var_110]; struct Config::ParamList *
0x14005471d  mov     rcx, [rsi]; this
0x140054720  call    ?CheckParameters@ParamBlock@Config@@QEBAPEAVFrsStatus@@PEAVParamList@2@0@Z; Config::ParamBlock::CheckParameters(Config::ParamList *,Config::ParamList *)
0x140054725  mov     rdi, rax
0x140054728  mov     [rbp+80h+arg_18], rax
0x14005472f  xor     ebx, ebx
0x140054731  test    rax, rax
0x140054734  jnz     loc_140054858
0x14005473a  mov     rdx, [rsi]
0x14005473d  lea     rcx, [rdx+210h]; this
0x140054744  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x140054749  test    eax, eax
0x14005474b  jz      loc_1400548F8
0x140054751  sub     eax, 1
0x140054754  jz      loc_1400548F8
0x14005475a  sub     eax, 1
0x14005475d  jz      loc_1400548F8
0x140054763  cmp     eax, 1
0x140054766  jz      loc_1400548F8
0x14005476c  or      dword ptr [rdx+22Ch], 8
0x140054773  mov     rax, [rsi]
0x140054776  mov     edi, 210h
0x14005477b  add     rax, rdi
0x14005477e  mov     [rbp+80h+arg_10], rax
0x140054785  lea     rdx, [rbp+80h+arg_10]
0x14005478c  lea     rcx, [rbp+80h+var_E8]
0x140054790  call    ?push_back@?$vector@PEAVReplicaSetManager@@V?$allocator@PEAVReplicaSetManager@@@std@@@std@@QEAAXAEBQEAVReplicaSetManager@@@Z; std::vector<ReplicaSetManager *>::push_back(ReplicaSetManager * const &)
0x140054795  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14005479c  test    rax, rax
0x14005479f  jz      short loc_1400547FD
0x1400547a1  cmp     [rax+40h], ebx
0x1400547a4  jz      short loc_1400547FD
0x1400547a6  cmp     dword ptr [rax+38h], 4
0x1400547aa  jl      short loc_1400547FD
0x1400547ac  lea     rax, aConfigReplicas_0; "Config::ReplicaSetConfig::Validate"
0x1400547b3  mov     [rsp+180h+var_130], rax
0x1400547b8  mov     [rsp+180h+var_128], 70Ah
0x1400547c0  mov     [rsp+180h+var_124], 4
0x1400547c8  lea     rax, aCrep; "CREP"
0x1400547cf  mov     [rsp+180h+var_120], rax
0x1400547d4  mov     rcx, [rsi]
0x1400547d7  add     rcx, rdi; this
0x1400547da  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x1400547df  mov     [rbp+80h+arg_8], eax
0x1400547e5  lea     r8, [rbp+80h+arg_8]
0x1400547ec  lea     rdx, aInvalidReplica_0; "Invalid replication group type:%d"
0x1400547f3  lea     rcx, [rsp+180h+var_130]
0x1400547f8  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x1400547fd  mov     r9, [rsi]
0x140054800  lea     rcx, [r9+0F0h]; this
0x140054807  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
0x14005480c  add     r9, 170h
0x140054813  mov     [rsp+180h+var_160], rax
0x140054818  mov     r8d, 5
0x14005481e  lea     rdx, [rsp+180h+var_110]
0x140054823  call    ?LogParamErrors@ParamBlock@Config@@IEBAXPEAVParamList@2@W4_FRS_XML_BLOCK_TYPE@@PEBG2@Z; Config::ParamBlock::LogParamErrors(Config::ParamList *,_FRS_XML_BLOCK_TYPE,ushort const *,ushort const *)
0x140054828  call    cs:__imp_GetCurrentThreadId
0x14005482f  nop     dword ptr [rax+rax+00h]
0x140054834  mov     [rsp+180h+var_140], rbx
0x140054839  mov     [rsp+180h+var_148], eax
0x14005483d  mov     [rsp+180h+var_150], 711h
0x140054845  mov     r9d, 3
0x14005484b  xor     r8d, r8d
0x14005484e  mov     edx, 2395h
0x140054853  jmp     loc_140054E22
0x140054858  mov     rax, [rbp+80h+var_E0]
0x14005485c  sub     rax, [rbp+80h+var_E8]
0x140054860  sar     rax, 3
0x140054864  test    eax, eax
0x140054866  jz      short loc_1400548B5
0x140054868  mov     r9, [rsi]
0x14005486b  lea     rcx, [r9+0F0h]; this
0x140054872  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
0x140054877  add     r9, 170h
0x14005487e  mov     [rsp+180h+var_160], rax
0x140054883  mov     r8d, 5
0x140054889  lea     rdx, [rsp+180h+var_110]
0x14005488e  call    ?LogParamErrors@ParamBlock@Config@@IEBAXPEAVParamList@2@W4_FRS_XML_BLOCK_TYPE@@PEBG2@Z; Config::ParamBlock::LogParamErrors(Config::ParamList *,_FRS_XML_BLOCK_TYPE,ushort const *,ushort const *)
0x140054893  call    cs:__imp_GetCurrentThreadId
0x14005489a  nop     dword ptr [rax+rax+00h]
0x14005489f  mov     [rsp+180h+var_140], rdi
0x1400548a4  mov     [rsp+180h+var_148], eax
0x1400548a8  mov     [rsp+180h+var_150], 721h
0x1400548b0  jmp     loc_140054E18
0x1400548b5  mov     rax, [rbp+80h+var_90]
0x1400548b9  sub     rax, [rbp+80h+var_98]
0x1400548bd  sar     rax, 3
0x1400548c1  test    eax, eax
0x1400548c3  jz      short loc_1400548F8
0x1400548c5  mov     r9, [rsi]
0x1400548c8  lea     rcx, [r9+0F0h]; this
0x1400548cf  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
0x1400548d4  add     r9, 170h
0x1400548db  mov     [rsp+180h+var_160], rax
0x1400548e0  mov     r8d, 5
0x1400548e6  lea     rdx, [rbp+80h+var_C0]
0x1400548ea  call    ?LogParamWarnings@ParamBlock@Config@@IEBAXPEAVParamList@2@W4_FRS_XML_BLOCK_TYPE@@PEBG2@Z; Config::ParamBlock::LogParamWarnings(Config::ParamList *,_FRS_XML_BLOCK_TYPE,ushort const *,ushort const *)
0x1400548ef  lea     rcx, [rbp+80h+var_A0]
0x1400548f3  call    ?DeleteAll@?$PtrList@VVolumeConfig@Config@@@@QEAAXXZ; PtrList<Config::VolumeConfig>::DeleteAll(void)
0x1400548f8  mov     r15d, ebx
0x1400548fb  mov     r12d, 0F0h
0x140054901  mov     [rbp+80h+arg_8], r15d
0x140054908  mov     rcx, [rsi]
0x14005490b  add     rcx, 388h
0x140054912  mov     rax, [rcx]
0x140054915  mov     rax, [rax+28h]
0x140054919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005491e  cmp     r15d, eax
0x140054921  jnb     loc_140054DF6
0x140054927  mov     rcx, rdi; struct FrsStatus *
0x14005492a  call    ?IsConfigParamFrsStatusValid@@YAHPEAVFrsStatus@@@Z; IsConfigParamFrsStatusValid(FrsStatus *)
0x14005492f  test    eax, eax
0x140054931  jz      loc_140054DF6
0x140054937  lea     rcx, [rbp+80h+arg_18]; struct FrsStatus **
0x14005493e  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x140054943  mov     rcx, [rsi]
0x140054946  add     rcx, 388h
0x14005494d  mov     rax, [rcx]
0x140054950  mov     edx, r15d
0x140054953  mov     rax, [rax+30h]
0x140054957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005495c  mov     r14, rax
0x14005495f  mov     rcx, [rsi]
0x140054962  add     rcx, 388h; this
0x140054969  lea     rdx, [rax+88h]; struct _GUID *
0x140054970  lea     r8d, [r15+1]; unsigned int
0x140054974  call    ?Find@ConnectionList@Config@@QEBAPEAVConnection@2@PEBU_GUID@@K@Z; Config::ConnectionList::Find(_GUID const *,ulong)
0x140054979  test    rax, rax
0x14005497c  jnz     loc_140054D1A
0x140054982  lea     r8, [rbp+80h+var_C0]; struct Config::ParamList *
0x140054986  lea     rdx, [rsp+180h+var_110]; struct Config::ParamList *
0x14005498b  mov     rcx, r14; this
0x14005498e  call    ?CheckParameters@ParamBlock@Config@@QEBAPEAVFrsStatus@@PEAVParamList@2@0@Z; Config::ParamBlock::CheckParameters(Config::ParamList *,Config::ParamList *)
0x140054993  mov     rdi, rax
0x140054996  mov     [rbp+80h+arg_18], rax
0x14005499d  test    rax, rax
0x1400549a0  jz      short loc_1400549F5
0x1400549a2  mov     rax, [rbp+80h+var_E0]
0x1400549a6  sub     rax, [rbp+80h+var_E8]
0x1400549aa  sar     rax, 3
0x1400549ae  test    eax, eax
0x1400549b0  jnz     loc_140054B4D
0x1400549b6  mov     rax, [rbp+80h+var_90]
0x1400549ba  sub     rax, [rbp+80h+var_98]
0x1400549be  sar     rax, 3
0x1400549c2  test    eax, eax
0x1400549c4  jz      short loc_1400549F5
0x1400549c6  mov     rcx, [rsi]
0x1400549c9  add     rcx, r12; this
0x1400549cc  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
0x1400549d1  lea     r9, [r14+98h]
0x1400549d8  mov     [rsp+180h+var_160], rax
0x1400549dd  mov     r8d, 6
0x1400549e3  lea     rdx, [rbp+80h+var_C0]
0x1400549e7  call    ?LogParamWarnings@ParamBlock@Config@@IEBAXPEAVParamList@2@W4_FRS_XML_BLOCK_TYPE@@PEBG2@Z; Config::ParamBlock::LogParamWarnings(Config::ParamList *,_FRS_XML_BLOCK_TYPE,ushort const *,ushort const *)
0x1400549ec  lea     rcx, [rbp+80h+var_A0]
0x1400549f0  call    ?DeleteAll@?$PtrList@VVolumeConfig@Config@@@@QEAAXXZ; PtrList<Config::VolumeConfig>::DeleteAll(void)
0x1400549f5  mov     rdx, r14; struct Member *
0x1400549f8  lea     rcx, [rbp+80h+var_70]; this
0x1400549fc  call    ??0ScopedMemberConnectionList@Member@Config@@QEAA@PEBV12@@Z; Config::Member::ScopedMemberConnectionList::ScopedMemberConnectionList(Config::Member const *)
0x140054a01  nop
0x140054a02  mov     r12, [rbp+80h+var_70]
0x140054a06  add     r12, 188h
0x140054a0d  mov     r13d, ebx
0x140054a10  mov     rax, [r12]
0x140054a14  mov     rcx, r12
0x140054a17  mov     rax, [rax+28h]
0x140054a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054a20  cmp     r13d, eax
0x140054a23  jnb     loc_140054B16
0x140054a29  mov     rcx, rdi; struct FrsStatus *
0x140054a2c  call    ?IsConfigParamFrsStatusValid@@YAHPEAVFrsStatus@@@Z; IsConfigParamFrsStatusValid(FrsStatus *)
0x140054a31  test    eax, eax
0x140054a33  jz      loc_140054B16
0x140054a39  lea     rcx, [rbp+80h+arg_18]; struct FrsStatus **
0x140054a40  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x140054a45  mov     rax, [r12]
0x140054a49  mov     edx, r13d
0x140054a4c  mov     rcx, r12
0x140054a4f  mov     rax, [rax+30h]
0x140054a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054a58  mov     r15, rax
0x140054a5b  lea     eax, [r13+1]
0x140054a5f  mov     dword ptr [rbp+80h+arg_10], eax
0x140054a65  lea     rdx, [r15+88h]; struct _GUID *
0x140054a6c  mov     r8d, eax; unsigned int
0x140054a6f  mov     rcx, r12; this
0x140054a72  call    ?Find@ConnectionList@Config@@QEBAPEAVConnection@2@PEBU_GUID@@K@Z; Config::ConnectionList::Find(_GUID const *,ulong)
0x140054a77  test    rax, rax
0x140054a7a  jnz     loc_140054C03
0x140054a80  mov     rcx, [r12]
0x140054a84  mov     rax, [rcx+30h]
0x140054a88  mov     edx, r13d
0x140054a8b  mov     rcx, r12
0x140054a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054a93  lea     r8, [rbp+80h+var_C0]; struct Config::ParamList *
0x140054a97  lea     rdx, [rsp+180h+var_110]; struct Config::ParamList *
0x140054a9c  mov     rcx, rax; this
0x140054a9f  call    ?CheckParameters@ParamBlock@Config@@QEBAPEAVFrsStatus@@PEAVParamList@2@0@Z; Config::ParamBlock::CheckParameters(Config::ParamList *,Config::ParamList *)
0x140054aa4  mov     rdi, rax
0x140054aa7  mov     [rbp+80h+arg_18], rax
0x140054aae  test    rax, rax
0x140054ab1  jz      short loc_140054B0A
0x140054ab3  mov     rax, [rbp+80h+var_E0]
0x140054ab7  sub     rax, [rbp+80h+var_E8]
0x140054abb  sar     rax, 3
0x140054abf  test    eax, eax
0x140054ac1  jnz     loc_140054BA1
0x140054ac7  mov     rax, [rbp+80h+var_90]
0x140054acb  sub     rax, [rbp+80h+var_98]
0x140054acf  sar     rax, 3
0x140054ad3  test    eax, eax
0x140054ad5  jz      short loc_140054B0A
0x140054ad7  mov     rcx, [rsi]
0x140054ada  add     rcx, 0F0h; this
0x140054ae1  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
0x140054ae6  lea     r9, [r15+98h]
0x140054aed  mov     [rsp+180h+var_160], rax
0x140054af2  mov     r8d, 7
0x140054af8  lea     rdx, [rbp+80h+var_C0]
0x140054afc  call    ?LogParamWarnings@ParamBlock@Config@@IEBAXPEAVParamList@2@W4_FRS_XML_BLOCK_TYPE@@PEBG2@Z; Config::ParamBlock::LogParamWarnings(Config::ParamList *,_FRS_XML_BLOCK_TYPE,ushort const *,ushort const *)
0x140054b01  lea     rcx, [rbp+80h+var_A0]
0x140054b05  call    ?DeleteAll@?$PtrList@VVolumeConfig@Config@@@@QEAAXXZ; PtrList<Config::VolumeConfig>::DeleteAll(void)
0x140054b0a  mov     r13d, dword ptr [rbp+80h+arg_10]
0x140054b11  jmp     loc_140054A10
0x140054b16  mov     rcx, rdi; struct FrsStatus *
0x140054b19  call    ?IsConfigParamFrsStatusValid@@YAHPEAVFrsStatus@@@Z; IsConfigParamFrsStatusValid(FrsStatus *)
0x140054b1e  test    eax, eax
0x140054b20  jz      short loc_140054B35
0x140054b22  lea     rcx, [rbp+80h+arg_18]; struct FrsStatus **
0x140054b29  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x140054b2e  mov     rdi, [rbp+80h+arg_18]
0x140054b35  lea     rcx, [rbp+80h+var_70]; this
0x140054b39  call    ??1ScopedMemberConnectionList@Member@Config@@QEAA@XZ; Config::Member::ScopedMemberConnectionList::~ScopedMemberConnectionList(void)
0x140054b3e  mov     r15d, [rbp+80h+arg_8]
0x140054b45  inc     r15d
0x140054b48  jmp     loc_1400548FB
0x140054b4d  mov     rcx, [rbp+80h+arg_0]
0x140054b54  mov     rcx, [rcx+90h]
0x140054b5b  add     rcx, r12; this
0x140054b5e  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
0x140054b63  lea     r9, [r14+98h]
0x140054b6a  mov     [rsp+180h+var_160], rax
0x140054b6f  mov     r8d, 6
0x140054b75  lea     rdx, [rsp+180h+var_110]
0x140054b7a  call    ?LogParamErrors@ParamBlock@Config@@IEBAXPEAVParamList@2@W4_FRS_XML_BLOCK_TYPE@@PEBG2@Z; Config::ParamBlock::LogParamErrors(Config::ParamList *,_FRS_XML_BLOCK_TYPE,ushort const *,ushort const *)
0x140054b7f  call    cs:__imp_GetCurrentThreadId
0x140054b86  nop     dword ptr [rax+rax+00h]
0x140054b8b  mov     [rsp+180h+var_140], rdi
0x140054b90  mov     [rsp+180h+var_148], eax
0x140054b94  mov     [rsp+180h+var_150], 752h
0x140054b9c  jmp     loc_140054E18
0x140054ba1  mov     rcx, [rbp+80h+arg_0]
0x140054ba8  mov     rcx, [rcx+90h]
0x140054baf  add     rcx, 0F0h; this
0x140054bb6  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
0x140054bbb  lea     r9, [r15+98h]
0x140054bc2  mov     [rsp+180h+var_160], rax
0x140054bc7  mov     r8d, 7
0x140054bcd  lea     rdx, [rsp+180h+var_110]
0x140054bd2  call    ?LogParamErrors@ParamBlock@Config@@IEBAXPEAVParamList@2@W4_FRS_XML_BLOCK_TYPE@@PEBG2@Z; Config::ParamBlock::LogParamErrors(Config::ParamList *,_FRS_XML_BLOCK_TYPE,ushort const *,ushort const *)
0x140054bd7  call    cs:__imp_GetCurrentThreadId
0x140054bde  nop     dword ptr [rax+rax+00h]
0x140054be3  mov     [rsp+180h+var_140], rdi
0x140054be8  mov     [rsp+180h+var_148], eax
0x140054bec  mov     [rsp+180h+var_150], 786h
0x140054bf4  mov     r9d, [rdi]
0x140054bf7  mov     r8d, [rdi+8]
0x140054bfb  mov     edx, [rdi+4]
0x140054bfe  jmp     loc_140054CEC
0x140054c03  or      dword ptr [r15+84h], 20h
0x140054c0b  lea     rax, [r15+68h]
0x140054c0f  mov     [rbp+80h+arg_10], rax
0x140054c16  lea     rdx, [rbp+80h+arg_10]
0x140054c1d  lea     rcx, [rbp+80h+var_E8]
0x140054c21  call    ?push_back@?$vector@PEAVReplicaSetManager@@V?$allocator@PEAVReplicaSetManager@@@std@@@std@@QEAAXAEBQEAVReplicaSetManager@@@Z; std::vector<ReplicaSetManager *>::push_back(ReplicaSetManager * const &)
0x140054c26  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140054c2d  test    rax, rax
0x140054c30  jz      short loc_140054C8B
  ... truncated ...
```
