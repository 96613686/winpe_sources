# CCorSvcMgr::Uninstall(ushort *,__MIDL___MIDL_itf_mscorsvc_0001_0004_0001,ushort *,__MIDL___MIDL_itf_mscorsvc_0000_0005_0001)

- ea: `0x18001dcb0`
- end: `0x18001ee13`
- name: `?Uninstall@CCorSvcMgr@@UEAAJPEAGW4__MIDL___MIDL_itf_mscorsvc_0001_0004_0001@@0W4__MIDL___MIDL_itf_mscorsvc_0000_0005_0001@@@Z`
- size: `4451`
- prototype: `int __high(unsigned __int16 *, enum __MIDL___MIDL_itf_mscorsvc_0001_0004_0001, unsigned __int16 *, enum __MIDL___MIDL_itf_mscorsvc_0000_0005_0001)`
- caller_count: `0`
- callee_count: `51`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001d80`
- `0x180002024`
- `0x180002504`
- `0x180005df0`
- `0x1800064a8`
- `0x180006a2c`
- `0x180006aa8`
- `0x180006c58`
- `0x180006c60`
- `0x1800087cc`
- `0x180008a04`
- `0x180009100`
- `0x1800097e0`
- `0x18000b33c`
- `0x18000c588`
- `0x18000c8a8`
- `0x18000ce8c`
- `0x18000d09c`
- `0x180013954`
- `0x180013b9c`
- `0x18001c3c4`
- `0x18001dcb0`
- `0x180024e00`
- `0x180026438`
- `0x1800289bc`
- `0x18002ce48`
- `0x18002cfd4`
- `0x18002d3c0`
- `0x18002d554`
- `0x18002d624`
- `0x18002d7ac`
- `0x18002db70`
- `0x18002dc24`
- `0x18002ff30`
- `0x1800304ec`
- `0x180030568`
- `0x180030ab8`
- `0x180030d84`
- `0x180031690`
- `0x180031e08`
- `0x180032ef4`
- `0x18003303c`
- `0x180034fd4`
- `0x1800363a8`
- `0x1800366a8`
- `0x1800368fc`
- `0x18003691c`
- `0x180037eb8`
- `0x18003dc30`
- `0x18003dc50`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x18001e95d`
- `KERNEL32!GetFileAttributesW` at `0x18001e95d`
- `KERNEL32!HeapFree` at `0x18001decf`
- `KERNEL32!HeapFree` at `0x18001e189`
- `KERNEL32!HeapFree` at `0x18001e761`
- `KERNEL32!HeapFree` at `0x18001decf`
- `KERNEL32!HeapFree` at `0x18001e189`
- `KERNEL32!HeapFree` at `0x18001e761`
- `KERNEL32!GetProcessHeap` at `0x18001deba`
- `KERNEL32!GetProcessHeap` at `0x18001e174`
- `KERNEL32!GetProcessHeap` at `0x18001e74c`
- `KERNEL32!GetProcessHeap` at `0x18001deba`
- `KERNEL32!GetProcessHeap` at `0x18001e174`
- `KERNEL32!GetProcessHeap` at `0x18001e74c`

## string_xrefs

- `0x18001dfc8`: `ngennicupdatelock.dat`
- `0x18001df0a`: `Uninstalling all assemblies...\n`
- `0x18001e940`: `Uninstalling all assemblies is not supported\n`
- `0x18001ea4f`: `Native image used by one or more roots, cannot be uninstalled\n`
- `0x18001ea5e`: `Uninstalling native image %s\n`
- `0x18001eb18`: `The specified assembly is not directly installed.\n`
- `0x18001eded`: `You may need to uninstall these assembly roots in order to delete the native image for %s\n`
- `0x18001ecbe`: `Uninstalling assembly %s\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=79
__int64 __fastcall CCorSvcMgr::Uninstall(
        struct Root *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        void *a4,
        char a5)
{
  unsigned int v7; // ebx
  char v8; // r13
  void *v9; // rdi
  int v10; // ecx
  HANDLE ProcessHeap; // rax
  struct Root *v12; // r14
  Logger *v13; // rdi
  bool v14; // dl
  unsigned __int16 *ConfigValue; // rsi
  struct RootList *RootList; // rax
  __int64 v17; // rcx
  unsigned int v18; // edi
  char *v19; // r12
  char v20; // r13
  __int64 PooledSvcWorker; // rax
  CCorSvcMgr::WorkerPoolItem *v22; // r14
  int v23; // esi
  int v24; // eax
  bool v25; // r8
  HANDLE v26; // rax
  bool v27; // r8
  BOOL v28; // eax
  unsigned __int16 v29; // r8
  __m128i v30; // xmm2
  __int64 v31; // xmm4_8
  int v32; // r8d
  __int64 v33; // rdx
  __m128i v34; // xmm6
  __int64 v35; // xmm7_8
  BOOL v36; // eax
  __int16 v37; // ax
  void *v38; // rdi
  HANDLE v39; // rax
  struct RootList *v40; // rax
  __int64 RootArray; // rax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  unsigned int v45; // esi
  __int64 v46; // r13
  unsigned int v47; // edi
  SString *v48; // r12
  __int64 v49; // r14
  const unsigned __int16 *v50; // rdx
  int v51; // r14d
  LogicalImage *APrimaryImage; // r14
  const unsigned __int16 *v53; // rdx
  unsigned int v54; // edi
  Logger *v55; // rcx
  __int64 v56; // r8
  const wchar_t *v57; // rdx
  struct RootList *v58; // rax
  RootList *v59; // rsi
  CCorSvcMgr *v60; // rcx
  int v61; // r14d
  bool IsNativeImageReferencedByStore; // al
  struct RootList *v63; // rax
  unsigned int v64; // eax
  struct RootList *v65; // rax
  Logger *v66; // rsi
  _QWORD *v67; // rax
  char v68; // si
  unsigned int v69; // r12d
  __int64 v70; // r13
  Image *v71; // rdi
  Image *v72; // rax
  struct Root *v73; // rax
  unsigned int v74; // esi
  char i; // si
  __int64 MatchingConfiguration; // rax
  __int64 v77; // rsi
  __int64 v78; // r8
  struct Exception *v80; // rdx
  Exception *v81; // rcx
  bool v82; // dl
  unsigned int CurrentExceptionCode; // eax
  int v84; // edx
  __int64 *v85; // rcx
  __int64 *v86; // rcx
  IErrorInfo *v87; // rax
  IErrorInfo *v88; // rbx
  int v89; // [rsp+20h] [rbp-858h]
  char v90; // [rsp+50h] [rbp-828h]
  bool v91[7]; // [rsp+51h] [rbp-827h] BYREF
  struct Root *v92; // [rsp+58h] [rbp-820h]
  unsigned int v93; // [rsp+60h] [rbp-818h]
  __int64 *v94; // [rsp+68h] [rbp-810h]
  LPVOID lpMem; // [rsp+70h] [rbp-808h] BYREF
  struct Root *v96; // [rsp+78h] [rbp-800h] BYREF
  int v97; // [rsp+80h] [rbp-7F8h]
  unsigned int v98; // [rsp+84h] [rbp-7F4h]
  __int64 *v99; // [rsp+88h] [rbp-7F0h] BYREF
  BOOL v100; // [rsp+90h] [rbp-7E8h]
  Image *v101; // [rsp+98h] [rbp-7E0h] BYREF
  __int64 v102; // [rsp+A0h] [rbp-7D8h] BYREF
  __int64 v103; // [rsp+A8h] [rbp-7D0h]
  __int64 v104; // [rsp+B0h] [rbp-7C8h]
  _QWORD v105[2]; // [rsp+B8h] [rbp-7C0h] BYREF
  __m128i v106; // [rsp+C8h] [rbp-7B0h] BYREF
  __int64 v107; // [rsp+D8h] [rbp-7A0h]
  unsigned int v108; // [rsp+E0h] [rbp-798h]
  unsigned int v109; // [rsp+E4h] [rbp-794h]
  int v110; // [rsp+E8h] [rbp-790h]
  unsigned int v111; // [rsp+ECh] [rbp-78Ch]
  unsigned int v112; // [rsp+F0h] [rbp-788h]
  unsigned int v113; // [rsp+F8h] [rbp-780h]
  int v114; // [rsp+100h] [rbp-778h] BYREF
  __int64 v115; // [rsp+108h] [rbp-770h]
  LPVOID v116; // [rsp+110h] [rbp-768h] BYREF
  int v117; // [rsp+118h] [rbp-760h]
  int v118; // [rsp+120h] [rbp-758h] BYREF
  __int64 v119; // [rsp+128h] [rbp-750h]
  int v120; // [rsp+130h] [rbp-748h]
  _DWORD v121[2]; // [rsp+138h] [rbp-740h] BYREF
  int v122; // [rsp+140h] [rbp-738h]
  void *v123; // [rsp+148h] [rbp-730h]
  __m128i v124; // [rsp+150h] [rbp-728h] BYREF
  __int64 v125; // [rsp+160h] [rbp-718h]
  struct Exception *v126; // [rsp+168h] [rbp-710h] BYREF
  BOOL v127; // [rsp+170h] [rbp-708h]
  _DWORD v128[2]; // [rsp+178h] [rbp-700h] BYREF
  int v129; // [rsp+180h] [rbp-6F8h]
  unsigned __int16 *v130; // [rsp+188h] [rbp-6F0h]
  void *v131; // [rsp+190h] [rbp-6E8h] BYREF
  int v132; // [rsp+198h] [rbp-6E0h]
  __int64 v133; // [rsp+1A0h] [rbp-6D8h]
  void *v134; // [rsp+1A8h] [rbp-6D0h]
  int v135; // [rsp+1B0h] [rbp-6C8h]
  _DWORD v136[2]; // [rsp+1B8h] [rbp-6C0h] BYREF
  int v137; // [rsp+1C0h] [rbp-6B8h]
  void *v138; // [rsp+1C8h] [rbp-6B0h]
  __int64 v139; // [rsp+1D0h] [rbp-6A8h] BYREF
  int v140; // [rsp+1D8h] [rbp-6A0h]
  void *v141; // [rsp+1E0h] [rbp-698h]
  _QWORD v142[4]; // [rsp+1E8h] [rbp-690h] BYREF
  int v143; // [rsp+208h] [rbp-670h]
  __int64 v144; // [rsp+210h] [rbp-668h]
  int v145; // [rsp+218h] [rbp-660h]
  _BYTE v146[24]; // [rsp+220h] [rbp-658h] BYREF
  __m128i v147; // [rsp+238h] [rbp-640h]
  __int64 v148; // [rsp+248h] [rbp-630h]
  __m128i v149; // [rsp+250h] [rbp-628h]
  __int64 v150; // [rsp+260h] [rbp-618h]
  __m128i v151; // [rsp+268h] [rbp-610h]
  __int64 v152; // [rsp+278h] [rbp-600h]
  __m128i v153; // [rsp+280h] [rbp-5F8h]
  __int64 v154; // [rsp+290h] [rbp-5E8h]
  __int128 v155; // [rsp+2A0h] [rbp-5D8h] BYREF
  __int64 v156; // [rsp+2B0h] [rbp-5C8h] BYREF
  __int64 v157; // [rsp+2B8h] [rbp-5C0h] BYREF
  unsigned int v158; // [rsp+2C0h] [rbp-5B8h] BYREF
  unsigned int v159; // [rsp+2C4h] [rbp-5B4h]
  unsigned int v160; // [rsp+2C8h] [rbp-5B0h]
  LPVOID v161; // [rsp+2D0h] [rbp-5A8h]
  __int16 v162; // [rsp+2D8h] [rbp-5A0h] BYREF
  _DWORD v163[4]; // [rsp+4E0h] [rbp-398h] BYREF
  char *v164; // [rsp+4F0h] [rbp-388h]
  char v165; // [rsp+4F8h] [rbp-380h] BYREF
  _DWORD v166[2]; // [rsp+5F0h] [rbp-288h] BYREF
  int v167; // [rsp+5F8h] [rbp-280h]
  void *v168; // [rsp+600h] [rbp-278h]
  __int16 v169; // [rsp+608h] [rbp-270h] BYREF

  lpMem = a4;
  v92 = a1;
  v96 = a1;
  v94 = (__int64 *)a1;
  v7 = 0;
  v97 = 0;
  v98 = 0;
  v118 = 0;
  v119 = 0;
  try
  {
    try
    {
      v101 = (Image *)&v118;
      v167 = 0;
      v168 = &v169;
      v166[1] = 512;
      v166[0] = 2;
      v169 = 0;
      SString::Set((SString *)v166, a2);
      v121[0] = 4;
      v121[1] = 4;
      v123 = (void *)L"*";
      v122 = 276;
      v97 = 1;
      if ( !(unsigned int)SString::Equals((SString *)v166, (const struct SString *)v121) || (v8 = 1, a3 != 1) )
        v8 = 0;
      v97 = 0;
      if ( (v122 & 8) != 0 )
        operator delete(v123);
      if ( v8 )
      {
        if ( (unsigned int)Helpers::IsUsingPrivateStore() )
          goto LABEL_20;
        if ( !`Helpers::IsUsingZapSet'::`2'::initialized )
        {
          lpMem = 0;
          CLRConfig::GetConfigValue(
            (const struct CLRConfig::ConfigStringInfo *)&CLRConfig::EXTERNAL_ZapSet,
            (unsigned __int16 **)&lpMem);
          v9 = lpMem;
          v142[3] = lpMem;
          v10 = 0;
          v143 = 0;
          if ( lpMem )
          {
            v10 = 1;
            v143 = 1;
          }
          `Helpers::IsUsingZapSet'::`2'::isUsingZapSet = lpMem != 0;
          `Helpers::IsUsingZapSet'::`2'::initialized = 1;
          if ( v10 )
          {
            if ( lpMem )
            {
              ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
              if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
              {
                ProcessHeap = GetProcessHeap();
                `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
              }
              HeapFree(ProcessHeap, 0, v9);
            }
            v143 = 0;
          }
        }
        if ( `Helpers::IsUsingZapSet'::`2'::isUsingZapSet )
        {
LABEL_20:
          if ( CCorSvcMgr::corSvcMgrCount == 1 && (a5 & 4) == 0 )
          {
            v12 = v92;
            v13 = (struct Root *)((char *)v92 + 200);
            Logger::Printf((struct Root *)((char *)v92 + 200), L"Uninstalling all assemblies...\n");
            ConfigValue = CLRConfig::GetConfigValue((const struct CLRConfig::ConfigStringInfo *)&CLRConfig::INTERNAL_NGenUninstallKeep);
            v134 = ConfigValue;
            v135 = 0;
            if ( ConfigValue )
            {
              v135 = 1;
            }
            else if ( !CLRConfig::GetConfigValue(
                         (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_NGenStressDelete,
                         v14,
                         v91) )
            {
              RootList = GetRootList(0);
              RootList::GetRootArray(RootList);
              lpMem = v105;
              v105[1] = -1;
              v105[0] = &MachineWideMutexHolder::`vftable';
              GetRootList(0);
              if ( *(void (__fastcall **)(MachineWideMutexHolder *__hidden, const unsigned __int16 *, void *, int *))v105[0] == MachineWideMutexHolder::Acquire )
                MachineWideMutexHolder::Acquire((MachineWideMutexHolder *)v105, L"ngennicupdatelock.dat", 0, 0);
              else
                (*(void (__fastcall **)(_QWORD *, const unsigned __int16 *, _QWORD, _QWORD))v105[0])(
                  v105,
                  L"ngennicupdatelock.dat",
                  0,
                  0);
              v116 = 0;
              v117 = 0;
              LODWORD(v101) = 0;
              CCorSvcMgr::GetNativeImageRuntimeVersions(v17, &v116, &v101);
              v18 = 0;
              v93 = 0;
              v19 = (char *)v116;
              while ( v18 < (unsigned int)v101 )
              {
                v20 = 0;
                v114 = 0;
                v115 = 0;
                try
                {
                  try
                  {
                    lpMem = &v114;
                    v155 = *(_OWORD *)((char *)v12 + 264);
                    PooledSvcWorker = CCorSvcMgr::GetPooledSvcWorker(
                                        (char *)v12 - 8,
                                        *((_QWORD *)v12 + 161),
                                        (unsigned __int64)(v94 + 2) & -(__int64)(v12 != (struct Root *)8),
                                        &v155,
                                        &v19[64 * (unsigned __int64)v18],
                                        0);
                    v22 = (CCorSvcMgr::WorkerPoolItem *)PooledSvcWorker;
                    v144 = PooledSvcWorker;
                    v23 = 0;
                    v145 = 0;
                    if ( PooledSvcWorker )
                    {
                      v23 = 1;
                      v145 = 1;
                    }
                    v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(PooledSvcWorker + 24) + 40LL))(
                            *(_QWORD *)(PooledSvcWorker + 24),
                            0,
                            0);
                    if ( v24 < 0 )
                      ThrowHR(v24);
                    if ( v23 )
                    {
                      CCorSvcMgr::WorkerPoolItem::~WorkerPoolItem(v22);
                      operator delete(v22);
                      v145 = 0;
                    }
                  }
                  catch ( Exception *v156 )
                  {
                    Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v114);
                    v115 = v156;
                    throw;
                  }
                }
                catch ( ... )
                {
                  v142[1] = 0;
                  v142[0] = &DelegatingException::`vftable';
                  v142[2] = -1;
                  v126 = (struct Exception *)v115;
                  v127 = v115 != 0;
                  Exception::HandlerState::SetupCatch((Exception::HandlerState *)&v114, 516, v25);
                  v80 = (struct Exception *)v142;
                  if ( v126 )
                    v80 = v126;
                  CCorSvcMgr::HandlePerRuntimeException(
                    (struct Root *)((char *)v96 - 8),
                    v80,
                    L"Error while deleting native images",
                    (const unsigned __int16 *)v116 + 32 * (unsigned __int64)v93,
                    0);
                  v81 = (Exception *)v142;
                  if ( v126 )
                    v81 = v126;
                  if ( !(unsigned int)Exception::IsTerminal(v81) )
                  {
                    if ( CLRConfig::GetConfigValue(
                           (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_legacyCorruptedStateExceptionsPolicy,
                           v82,
                           v91)
                      || (CurrentExceptionCode = GetCurrentExceptionCode(),
                          !(unsigned int)IsProcessCorruptedStateException(CurrentExceptionCode, v84)) )
                    {
                      Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2,1>::~Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2,1>((__int64 *)&v126);
                      DelegatingException::~DelegatingException((DelegatingException *)v142);
                      v19 = (char *)v116;
                      v18 = v93;
                      v20 = v114;
                      v12 = v96;
                      v92 = v96;
                      goto LABEL_36;
                    }
                  }
                  v127 = 0;
                  throw;
                }
                v12 = v92;
LABEL_36:
                if ( (v20 & 2) != 0 )
                  HandleStackOverflowAfterCatch();
                v93 = ++v18;
              }
              DeleteRootList();
              RootList::DeleteRootList();
              if ( v117 )
              {
                if ( v19 )
                {
                  v26 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
                  if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
                  {
                    v26 = GetProcessHeap();
                    `ClrFreeInProcessHeap'::`2'::ProcessHeap = v26;
                  }
                  HeapFree(v26, 0, v19);
                }
                v117 = 0;
              }
              v94 = v105;
              FileLockHolder::~FileLockHolder((FileLockHolder *)v105);
LABEL_120:
              if ( v135 )
              {
                operator delete(v134);
                v135 = 0;
              }
              goto LABEL_176;
            }
            v163[0] = 0;
            v163[2] = 0;
            v164 = &v165;
            v163[1] = 240;
            if ( ConfigValue )
            {
              Logger::Printf(v13, L"(Keeping following assemblies: %s)\n", ConfigValue);
              v160 = 0;
              v161 = &v162;
              v159 = 512;
              v158 = 2;
              v162 = 0;
              SString::Set((SString *)&v158, ConfigValue);
              SString::ConvertToUnicode((SString *)&v158);
              v160 |= 0x100u;
              if ( (~(v160 >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v158) )
                SString::ConvertToUnicode((SString *)&v158);
              if ( (v160 & 0x10) != 0 )
                SBuffer::ReallocateBuffer(&v158, v159, 1);
              v124.m128i_i64[0] = (__int64)v161;
              v124.m128i_i32[2] = (v160 & 1) == 0;
              while ( 1 )
              {
                if ( (~(v160 >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v158) )
                  SString::ConvertToUnicode((SString *)&v158);
                if ( (v160 & 0x10) != 0 )
                  SBuffer::ReallocateBuffer(&v158, v159, 1);
                if ( (v160 & 2) != 0 )
                {
                  v28 = (v160 & 7) == 7 && !SString::s_IsANSIMultibyte;
                  if ( !v28 && !(unsigned int)SString::ScanASCII((SString *)&v158) )
                    SString::ConvertToUnicode((SString *)&v158);
                }
                v153.m128i_i64[0] = (__int64)v161 + (int)(((v158 >> ((v160 & 1) == 0)) - 1) << ((v160 & 1) == 0));
                v153.m128i_i32[2] = (v160 & 1) == 0;
                if ( !(unsigned int)((v124.m128i_i64[0] - v153.m128i_i64[0]) >> v124.m128i_i8[8]) )
                  break;
                if ( !(unsigned int)SString::Skip((SString *)&v158, (struct SString::CIterator *)&v124, 0x20u)
                  && !(unsigned int)SString::Skip((SString *)&v158, (struct SString::CIterator *)&v124, 0x3Bu) )
                {
                  v106 = v124;
                  v107 = v125;
                  v149.m128i_i64[0] = 0;
                  if ( (unsigned int)SString::Find((SString *)&v158, (struct SString::CIterator *)&v106, v29) )
                  {
                    v30 = v106;
                    v151.m128i_i64[1] = v106.m128i_i64[1];
                    v31 = v107;
                    v152 = v107;
                    v32 = _mm_cvtsi128_si32(_mm_srli_si128(v106, 8));
                    v33 = v106.m128i_i64[0];
                    v151.m128i_i64[0] = v106.m128i_i64[0] + (1 << v32);
                    v34 = v151;
                    v149 = v151;
                    v35 = v107;
                    v150 = v107;
                  }
                  else
                  {
                    if ( (~(v160 >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v158) )
                      SString::ConvertToUnicode((SString *)&v158);
                    if ( (v160 & 0x10) != 0 )
                      SBuffer::ReallocateBuffer(&v158, v159, 1);
                    if ( (v160 & 2) != 0 )
                    {
                      v36 = (v160 & 7) == 7 && !SString::s_IsANSIMultibyte;
                      if ( !v36 && !(unsigned int)SString::ScanASCII((SString *)&v158) )
                        SString::ConvertToUnicode((SString *)&v158);
                    }
                    v147.m128i_i64[0] = (__int64)v161 + (int)(((v158 >> ((v160 & 1) == 0)) - 1) << ((v160 & 1) == 0));
                    v147.m128i_i32[2] = (v160 & 1) == 0;
                    v30 = v147;
                    v106 = v147;
                    v31 = v148;
                    v107 = v148;
                    v34 = v147;
                    v149 = v147;
                    v35 = v148;
                    v150 = v148;
                    v32 = v147.m128i_i32[2];
                    v33 = v147.m128i_i64[0];
                  }
                  while ( 1 )
                  {
                    v37 = v32 ? *(_WORD *)((-1 << v32) + v33) : *(char *)(v33 - 1);
                    if ( v37 != 32 )
                      break;
                    v153 = v30;
                    v154 = v31;
                    v33 += -1 << v32;
                    v106.m128i_i64[0] = v33;
                    v30 = v106;
                  }
                  v94 = &v102;
                  v128[0] = 2;
                  v128[1] = 2;
                  v129 = 16;
                  v130 = (unsigned __int16 *)&SString::s_EmptyBuffer;
                  SString::Set(
                    (SString *)v128,
                    (const struct SString *)&v158,
                    (const struct SString::CIterator *)&v124,
                    (const struct SString::CIterator *)&v106);
                  SString::ConvertToUnicode((SString *)v128);
                  v102 = 0x200000002LL;
                  LODWORD(v103) = 16;
                  v104 = (__int64)&SString::s_EmptyBuffer;
                  SString::Set((SString *)&v102, v130);
                  SArray<SString,0>::Append((SBuffer *)v163, (struct SBuffer *)&v102);
                  if ( (v129 & 8) != 0 )
                    operator delete(v130);
                  v124 = v34;
                  v125 = v35;
                }
              }
              if ( (v160 & 8) != 0 )
              {
                v38 = v161;
                if ( v161 )
                {
                  v39 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
                  if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
                  {
                    v39 = GetProcessHeap();
                    `ClrFreeInProcessHeap'::`2'::ProcessHeap = v39;
                  }
                  HeapFree(v39, 0, v38);
                }
              }
            }
            v40 = GetRootList(0);
            RootArray = RootList::GetRootArray(v40);
            v94 = (__int64 *)RootArray;
            v45 = 0;
            v110 = 0;
            while ( v45 < *(_DWORD *)RootArray >> 3 )
            {
              v46 = *(_QWORD *)(*(_QWORD *)(RootArray + 16) + 8LL * v45);
              v47 = 0;
              v108 = 0;
              while ( v47 < v163[0] / 0x18u )
              {
                v48 = (SString *)&v164[24 * v47];
                v49 = *(_QWORD *)(v46 + 24);
                if ( v49 )
                {
                  SString::ConvertToUnicode(*(SString **)(v46 + 24));
                  v50 = *(const unsigned __int16 **)(v49 + 16);
                }
                else
                {
                  v50 = 0;
                }
                v136[0] = 2;
                v136[1] = 2;
                v137 = 16;
                v138 = (void *)&SString::s_EmptyBuffer;
                SString::Set((SString *)v136, v50);
                v51 = SString::EqualsCaseInsensitive(v48, (const struct SString *)v136);
                if ( (v137 & 8) != 0 )
                  operator delete(v138);
                if ( v51 )
                  goto LABEL_118;
                APrimaryImage = Root::GetAPrimaryImage((Root *)v46);
                if ( APrimaryImage )
                {
                  if ( v48 )
                  {
                    SString::ConvertToUnicode(v48);
                    v53 = (const unsigned __int16 *)*((_QWORD *)v48 + 2);
                  }
                  else
                  {
                    v53 = 0;
                  }
                  if ( LogicalImage::DisplayNamePartialNameMatch(APrimaryImage, v53) )
                    goto LABEL_118;
                }
                v108 = ++v47;
              }
              v54 = 0;
              v109 = 0;
              while ( v54 < *(_DWORD *)(v46 + 48) >> 3 )
              {
                Node::SetStatus(*(_QWORD *)(*(_QWORD *)(v46 + 64) + 8LL * v54++), 0);
                v109 = v54;
              }
              Root::SetStatus(v46, 3);
              WorkQueue::AppendJobToPrimaryList((struct Root *)((char *)v92 + 96), (struct Root *)v46);
LABEL_118:
              v110 = ++v45;
              RootArray = (__int64)v94;
            }
            SArray<SString,0>::~SArray<SString,0>(v163, v42, v43, v44);
            goto LABEL_120;
          }
        }
        v55 = (struct Root *)((char *)v92 + 200);
        v56 = 0;
        v57 = L"Uninstalling all assemblies is not supported\n";
LABEL_123:
        Logger::Log(v55, v57, v56);
        goto LABEL_176;
      }
      if ( (a5 & 4) != 0 )
      {
        if ( GetFileAttributesW(a2) == -1 )
          ThrowHR(-2147024894);
        v58 = GetRootList(*((unsigned __int8 *)v92 + 336));
        v59 = v58;
        if ( !*((_BYTE *)v92 + 336) )
          RootList::GetRootArray(v58);
        RootList::DisableRegAccess(v59);
        v139 = 0x200000002LL;
        v140 = 16;
        v141 = (void *)&SString::s_EmptyBuffer;
        SString::Set((SString *)&v139, a2);
        v61 = ParseNIPath(
                (const unsigned __int16 **)&v139,
                &v96,
                (__int64)v92 + 200,
                *((_BYTE *)v92 + 336),
                *((unsigned __int16 **)v92 + 36));
        if ( (v140 & 8) != 0 )
          operator delete(v141);
        if ( v61 < 0 )
          ThrowHR(v61);
        IsNativeImageReferencedByStore = CCorSvcMgr::IsNativeImageReferencedByStore(
                                           v60,
                                           **(struct LogicalImage ***)(**((_QWORD **)v96 + 8) + 48LL));
        v55 = (struct Root *)((char *)v92 + 200);
        if ( !IsNativeImageReferencedByStore )
        {
          Logger::Printf(v55, L"Uninstalling native image %s\n", a2);
          WorkQueue::AppendJobToPrimaryList((struct Root *)((char *)v92 + 96), v96);
          goto LABEL_176;
        }
        v56 = 1;
        v57 = L"Native image used by one or more roots, cannot be uninstalled\n";
        goto LABEL_123;
      }
      v131 = 0;
      v132 = 0;
      v133 = 0;
      v63 = GetRootList(0);
      RootList::GetRootArrayForName(v63, &v131, a2, a5 & 1);
      v64 = (unsigned int)v131;
      if ( ((unsigned int)v131 & 0xFFFFFFF8) == 0 )
      {
        SArray<Root *,1>::SArray<Root *,1>(v146);
        v65 = GetRootList(0);
        RootList::GetRootArrayForDependency(v65, v146, a2, a5 & 1);
        if ( (unsigned int)SArray<Root *,1>::GetCount(v146) )
        {
          v66 = (struct Root *)((char *)v92 + 200);
          Logger::Printf((struct Root *)((char *)v92 + 200), L"The specified assembly is not directly installed.\n");
          Logger::Printf(
            (struct Root *)((char *)v92 + 200),
            L"However, %s is specified as a dependency of the following assemblies:\n",
            a2);
          while ( 1 )
          {
            v111 = v7;
            if ( v7 >= (unsigned int)SArray<Root *,1>::GetCount(v146) )
              break;
            v67 = (_QWORD *)SArray<Root *,1>::operator[](v146, v7);
            Root::Dump(*v67, *(_QWORD *)v66);
            ++v7;
          }
          Logger::Printf(
            v66,
            L"You may need to uninstall these assembly roots in order to delete the native image for %s\n",
            a2);
        }
        ThrowHR(-2147024894);
      }
      v68 = 0;
      v90 = 0;
      v69 = 0;
      v120 = 0;
      while ( v69 < v64 >> 3 )
      {
        v70 = *(_QWORD *)(v133 + 8LL * v69);
        v71 = 0;
        v99 = 0;
        v100 = 0;
        if ( lpMem )
        {
          v72 = (Image *)operator new(0x18u);
          v94 = (__int64 *)v72;
          if ( v72 )
            v71 = Image::Image(v72, (const unsigned __int16 *)lpMem, 0);
          else
            v71 = 0;
          v99 = (__int64 *)v71;
          if ( v71 )
            v100 = 1;
          if ( a3 == 1 )
            a3 = 0;
          v112 = a3;
        }
        v73 = v92;
        if ( *((_QWORD *)v92 + 36) )
        {
          if ( a3 == 1 )
            a3 = 0;
          v112 = a3;
        }
        if ( a3 == 1 )
        {
          v74 = 0;
          v113 = 0;
          while ( v74 < *(_DWORD *)(v70 + 48) >> 3 )
          {
            Node::SetStatus(*(_QWORD *)(*(_QWORD *)(v70 + 64) + 8LL * v74++), 0);
            v113 = v74;
          }
        }
        else
        {
          for ( i = 0; ; i = 1 )
          {
            LOBYTE(v89) = 1;
            MatchingConfiguration = Root::FindMatchingConfiguration(v70, a3, v71, *((_QWORD *)v73 + 36), v89);
            if ( !MatchingConfiguration )
              break;
            Node::SetStatus(MatchingConfiguration, 0);
            v73 = v92;
          }
          if ( !i )
          {
            v68 = v90;
            goto LABEL_167;
          }
        }
        v77 = *(_QWORD *)(v70 + 24);
        if ( v77 )
        {
          SString::ConvertToUnicode(*(SString **)(v70 + 24));
          v78 = *(_QWORD *)(v77 + 16);
        }
        else
        {
          v78 = 0;
        }
        Logger::Printf((struct Root *)((char *)v92 + 200), L"Uninstalling assembly %s\n", v78);
        v68 = 1;
        v90 = 1;
        Root::SetStatus(v70, 3);
        WorkQueue::AppendJobToPrimaryList((struct Root *)((char *)v92 + 96), (struct Root *)v70);
LABEL_167:
        if ( v100 )
        {
          v96 = (struct Root *)v71;
          if ( v71 )
          {
            v101 = v71;
            if ( (v71[8] & 8) != 0 )
              operator delete(*((void **)v71 + 2));
            operator delete(v71);
          }
          v100 = 0;
        }
        v120 = ++v69;
        v64 = (unsigned int)v131;
      }
      if ( !v68 )
        ThrowHR(-2147024894);
      WriteBuffer::~WriteBuffer(&v131);
LABEL_176:
      if ( (v167 & 8) != 0 )
        operator delete(v168);
    }
    catch ( Exception *v157 )
    {
      Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v118);
      v119 = v157;
      throw;
    }
  }
  catch ( ... )
  {
    v103 = 0;
    v102 = (__int64)&DelegatingException::`vftable';
    v104 = -1;
    v99 = (__int64 *)v119;
    v100 = v119 != 0;
    Exception::HandlerState::SetupCatch((Exception::HandlerState *)&v118, 654, v27);
    v85 = &v102;
    if ( v99 )
      v85 = v99;
    v98 = (*(__int64 (__fastcall **)(__int64 *))(*v85 + 16))(v85);
    RetailAssertIfExpectedClean();
    v86 = &v102;
    if ( v99 )
      v86 = v99;
    v87 = (IErrorInfo *)(*(__int64 (__fastcall **)(__int64 *))(*v86 + 32))(v86);
    v88 = v87;
    if ( v87 )
    {
      SetErrorInfo(0, v87);
      ((void (__fastcall *)(IErrorInfo *))v88->lpVtbl->Release)(v88);
    }
    Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2,1>::~Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2,1>((__int64 *)&v99);
    DelegatingException::~DelegatingException((DelegatingException *)&v102);
  }
  if ( (v118 & 2) != 0 && g_fpHandleStackOverflowAfterCatch )
    g_fpHandleStackOverflowAfterCatch();
  return v98;
}

```

## disassembly

```asm
0x18001dcb0  mov     r11, rsp
0x18001dcb3  push    rbx
0x18001dcb4  push    rsi
0x18001dcb5  push    rdi
0x18001dcb6  push    r12
0x18001dcb8  push    r13
0x18001dcba  push    r14
0x18001dcbc  push    r15
0x18001dcbe  sub     rsp, 840h
0x18001dcc5  movaps  xmmword ptr [r11-48h], xmm6
0x18001dcca  movaps  xmmword ptr [r11-58h], xmm7
0x18001dccf  mov     rax, cs:__security_cookie
0x18001dcd6  xor     rax, rsp
0x18001dcd9  mov     [rsp+878h+var_68], rax
0x18001dce1  mov     [rsp+878h+lpMem], r9
0x18001dce6  mov     r14d, r8d
0x18001dce9  mov     rdi, rdx
0x18001dcec  mov     [rsp+878h+var_820], rcx
0x18001dcf1  mov     [rsp+878h+var_800], rcx
0x18001dcf6  mov     [rsp+878h+var_810], rcx
0x18001dcfb  xor     ebx, ebx
0x18001dcfd  mov     [rsp+878h+var_7F8], ebx
0x18001dd04  mov     [rsp+878h+var_7F4], ebx
0x18001dd0b  mov     [rsp+878h+var_758], ebx
0x18001dd12  mov     [r11-750h], rbx
0x18001dd19  lea     rax, [r11-758h]
0x18001dd20  mov     [r11-7E0h], rax
0x18001dd27  mov     esi, [rsp+878h+arg_20]
0x18001dd2e  mov     r12d, esi
0x18001dd31  shr     r12d, 2
0x18001dd35  lea     r15d, [rbx+1]
0x18001dd39  and     r12b, r15b
0x18001dd3c  mov     [rsp+878h+var_288], ebx
0x18001dd43  mov     [rsp+878h+var_284], ebx
0x18001dd4a  mov     [rsp+878h+var_280], ebx
0x18001dd51  mov     [r11-278h], rbx
0x18001dd58  lea     rax, [r11-270h]
0x18001dd5f  mov     [r11-278h], rax
0x18001dd66  mov     [rsp+878h+var_284], 200h
0x18001dd71  mov     [rsp+878h+var_288], 2
0x18001dd7c  mov     rax, [r11-278h]
0x18001dd83  mov     [rax], bx
0x18001dd86  lea     rcx, [r11-288h]; this
0x18001dd8d  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18001dd92  nop
0x18001dd93  lea     ecx, [rbx+4]
0x18001dd96  mov     [rsp+878h+var_740], ecx
0x18001dd9d  mov     [rsp+878h+var_73C], ecx
0x18001dda4  mov     [rsp+878h+var_738], 10h
0x18001ddaf  lea     rax, asc_180052DBC; "*"
0x18001ddb6  mov     [rsp+878h+var_730], rax
0x18001ddbe  mov     eax, [rsp+878h+var_738]
0x18001ddc5  and     eax, 0FFFFFFF8h
0x18001ddc8  mov     [rsp+878h+var_738], eax
0x18001ddcf  or      eax, ecx
0x18001ddd1  mov     [rsp+878h+var_738], eax
0x18001ddd8  bts     eax, 8
0x18001dddc  mov     [rsp+878h+var_738], eax
0x18001dde3  mov     [rsp+878h+var_7F8], r15d
0x18001ddeb  lea     rdx, [rsp+878h+var_740]; struct SString *
0x18001ddf3  lea     rcx, [rsp+878h+var_288]; this
0x18001ddfb  call    ?Equals@SString@@QEBAHAEBV1@@Z; SString::Equals(SString const &)
0x18001de00  test    eax, eax
0x18001de02  jz      short loc_18001DE0C
0x18001de04  cmp     r14d, r15d
0x18001de07  mov     r13b, r15b
0x18001de0a  jz      short loc_18001DE0F
0x18001de0c  mov     r13b, bl
0x18001de0f  mov     eax, r15d
0x18001de12  and     eax, 0FFFFFFFEh
0x18001de15  mov     [rsp+878h+var_7F8], eax
0x18001de1c  test    byte ptr [rsp+878h+var_738], 8
0x18001de24  jz      short loc_18001DE33
0x18001de26  mov     rcx, [rsp+878h+var_730]; lpMem
0x18001de2e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001de33  test    r13b, r13b
0x18001de36  jz      loc_18001E951
0x18001de3c  call    ?IsUsingPrivateStore@Helpers@@SAHXZ; Helpers::IsUsingPrivateStore(void)
0x18001de41  test    eax, eax
0x18001de43  jnz     loc_18001DEE8
0x18001de49  cmp     cs:?initialized@?1??IsUsingZapSet@Helpers@@SAHXZ@4HA, ebx; int `Helpers::IsUsingZapSet(void)'::`2'::initialized
0x18001de4f  jnz     loc_18001DEDC
0x18001de55  mov     [rsp+878h+lpMem], rbx
0x18001de5a  lea     rdx, [rsp+878h+lpMem]; unsigned __int16 **
0x18001de5f  lea     rcx, ?EXTERNAL_ZapSet@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x18001de66  call    ?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)
0x18001de6b  mov     rdi, [rsp+878h+lpMem]
0x18001de70  mov     [rsp+878h+var_678], rdi
0x18001de78  mov     ecx, ebx
0x18001de7a  mov     [rsp+878h+var_670], ebx
0x18001de81  test    rdi, rdi
0x18001de84  jz      short loc_18001DE90
0x18001de86  mov     ecx, r15d
0x18001de89  mov     [rsp+878h+var_670], ecx
0x18001de90  mov     eax, ebx
0x18001de92  test    rdi, rdi
0x18001de95  setnz   al
0x18001de98  mov     cs:?isUsingZapSet@?1??IsUsingZapSet@Helpers@@SAHXZ@4HA, eax; int `Helpers::IsUsingZapSet(void)'::`2'::isUsingZapSet
0x18001de9e  mov     cs:?initialized@?1??IsUsingZapSet@Helpers@@SAHXZ@4HA, r15d; int `Helpers::IsUsingZapSet(void)'::`2'::initialized
0x18001dea5  test    ecx, ecx
0x18001dea7  jz      short loc_18001DEDC
0x18001dea9  test    rdi, rdi
0x18001deac  jz      short loc_18001DED5
0x18001deae  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001deb5  test    rax, rax
0x18001deb8  jnz     short loc_18001DEC7
0x18001deba  call    cs:__imp_GetProcessHeap
0x18001dec0  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001dec7  mov     r8, rdi; lpMem
0x18001deca  xor     edx, edx; dwFlags
0x18001decc  mov     rcx, rax; hHeap
0x18001decf  call    cs:__imp_HeapFree
0x18001ded5  mov     [rsp+878h+var_670], ebx
0x18001dedc  cmp     cs:?isUsingZapSet@?1??IsUsingZapSet@Helpers@@SAHXZ@4HA, ebx; int `Helpers::IsUsingZapSet(void)'::`2'::isUsingZapSet
0x18001dee2  jz      loc_18001E931
0x18001dee8  cmp     cs:?corSvcMgrCount@CCorSvcMgr@@0JA, r15d; long CCorSvcMgr::corSvcMgrCount
0x18001deef  jnz     loc_18001E931
0x18001def5  test    r12b, r12b
0x18001def8  jnz     loc_18001E931
0x18001defe  mov     r14, [rsp+878h+var_820]
0x18001df03  lea     rdi, [r14+0C8h]
0x18001df0a  lea     rdx, aUninstallingAl_0; "Uninstalling all assemblies...\n"
0x18001df11  mov     rcx, rdi; this
0x18001df14  call    ?Printf@Logger@@QEAAXPEBGZZ; Logger::Printf(ushort const *,...)
0x18001df19  lea     rcx, ?INTERNAL_NGenUninstallKeep@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x18001df20  call    ?GetConfigValue@CLRConfig@@SAPEAGAEBUConfigStringInfo@1@@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &)
0x18001df25  mov     rsi, rax
0x18001df28  mov     [rsp+878h+var_6D0], rax
0x18001df30  mov     [rsp+878h+var_6C8], ebx
0x18001df37  test    rax, rax
0x18001df3a  jz      short loc_18001DF44
0x18001df3c  mov     [rsp+878h+var_6C8], r15d
0x18001df44  test    rsi, rsi
0x18001df47  jnz     loc_18001E1B5
0x18001df4d  lea     r8, [rsp+878h+var_827]; bool *
0x18001df52  lea     rcx, ?EXTERNAL_NGenStressDelete@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x18001df59  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x18001df5e  test    eax, eax
0x18001df60  jnz     loc_18001E1B5
0x18001df66  xor     ecx, ecx; int
0x18001df68  call    ?GetRootList@@YAPEAVRootList@@H@Z; GetRootList(int)
0x18001df6d  mov     rcx, rax
0x18001df70  call    ?GetRootArray@RootList@@QEAAPEAV?$ArrayOfPointers@VRoot@@@@XZ; RootList::GetRootArray(void)
0x18001df75  lea     rax, [rsp+878h+var_7C0]
0x18001df7d  mov     [rsp+878h+lpMem], rax
0x18001df82  lea     rax, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x18001df89  mov     [rsp+878h+var_7C0], rax
0x18001df91  or      [rsp+878h+var_7B8], 0FFFFFFFFFFFFFFFFh
0x18001df9a  lea     rax, ??_7MachineWideMutexHolder@@6B@; const MachineWideMutexHolder::`vftable'
0x18001dfa1  mov     [rsp+878h+var_7C0], rax
0x18001dfa9  xor     ecx, ecx; int
0x18001dfab  call    ?GetRootList@@YAPEAVRootList@@H@Z; GetRootList(int)
0x18001dfb0  mov     rax, [rsp+878h+var_7C0]
0x18001dfb8  mov     rax, [rax]
0x18001dfbb  lea     rcx, ?Acquire@MachineWideMutexHolder@@UEAAXPEBGPEAXPEAH@Z; MachineWideMutexHolder::Acquire(ushort const *,void *,int *)
0x18001dfc2  xor     r9d, r9d; int *
0x18001dfc5  xor     r8d, r8d; void *
0x18001dfc8  lea     rdx, aNgennicupdatel; "ngennicupdatelock.dat"
0x18001dfcf  cmp     rax, rcx
0x18001dfd2  lea     rcx, [rsp+878h+var_7C0]; this
0x18001dfda  jnz     short loc_18001DFE3
0x18001dfdc  call    ?Acquire@MachineWideMutexHolder@@UEAAXPEBGPEAXPEAH@Z; MachineWideMutexHolder::Acquire(ushort const *,void *,int *)
0x18001dfe1  jmp     short loc_18001DFEA
0x18001dfe3  call    cs:__guard_dispatch_icall_fptr
0x18001dfe9  nop
0x18001dfea  mov     [rsp+878h+var_768], rbx
0x18001dff2  mov     [rsp+878h+var_760], ebx
0x18001dff9  mov     dword ptr [rsp+878h+var_7E0], ebx
0x18001e000  lea     r8, [rsp+878h+var_7E0]
0x18001e008  lea     rdx, [rsp+878h+var_768]
0x18001e010  call    ?GetNativeImageRuntimeVersions@CCorSvcMgr@@AEAAXAEAV?$NewArrayHolder@VVersionStr@@@@AEAI@Z; CCorSvcMgr::GetNativeImageRuntimeVersions(NewArrayHolder<VersionStr> &,uint &)
0x18001e015  mov     edi, ebx
0x18001e017  mov     [rsp+878h+var_818], ebx
0x18001e01b  mov     r12, [rsp+878h+var_768]
0x18001e023  cmp     edi, dword ptr [rsp+878h+var_7E0]
0x18001e02a  jnb     loc_18001E14F
0x18001e030  mov     r13d, ebx
0x18001e033  mov     [rsp+878h+var_778], ebx
0x18001e03a  mov     [rsp+878h+var_770], rbx
0x18001e042  lea     rax, [rsp+878h+var_778]
0x18001e04a  mov     [rsp+878h+lpMem], rax
0x18001e04f  lea     rcx, [r14-8]
0x18001e053  movups  xmm0, xmmword ptr [r14+108h]
0x18001e05b  movdqu  [rsp+878h+var_5D8], xmm0
0x18001e064  mov     r9d, edi
0x18001e067  shl     r9, 6
0x18001e06b  add     r9, r12
0x18001e06e  mov     rax, rcx
0x18001e071  mov     rdx, [rsp+878h+var_810]
0x18001e076  add     rdx, 10h
0x18001e07a  neg     rax
0x18001e07d  sbb     r8, r8
0x18001e080  and     r8, rdx
0x18001e083  mov     [rsp+878h+var_830], rbx
0x18001e088  mov     [rsp+878h+var_840], rbx
0x18001e08d  mov     [rsp+878h+var_850], rbx
0x18001e092  mov     [rsp+878h+var_858], r9
0x18001e097  lea     r9, [rsp+878h+var_5D8]
0x18001e09f  mov     rdx, [r14+508h]
0x18001e0a6  call    ?GetPooledSvcWorker@CCorSvcMgr@@AEAAPEAVWorkerPoolItem@1@PEAXPEAUICorSvcLogger@@U_NGenPrivateAttributes@@PEBG3HPEAGW4__MIDL___MIDL_itf_mscorsvc_0001_0004_0001@@PEAVLogicalImage@@@Z; CCorSvcMgr::GetPooledSvcWorker(void *,ICorSvcLogger *,_NGenPrivateAttributes,ushort const *,ushort const *,int,ushort *,__MIDL___MIDL_itf_mscorsvc_0001_0004_0001,LogicalImage *)
0x18001e0ab  mov     r14, rax
0x18001e0ae  mov     [rsp+878h+var_668], rax
0x18001e0b6  mov     esi, ebx
0x18001e0b8  mov     [rsp+878h+var_660], ebx
0x18001e0bf  test    rax, rax
0x18001e0c2  jz      short loc_18001E0CF
0x18001e0c4  mov     esi, r15d
0x18001e0c7  mov     [rsp+878h+var_660], r15d
0x18001e0cf  mov     rcx, [rax+18h]
0x18001e0d3  mov     rax, [rcx]
0x18001e0d6  xor     r8d, r8d
0x18001e0d9  xor     edx, edx
0x18001e0db  mov     rax, [rax+28h]
0x18001e0df  call    cs:__guard_dispatch_icall_fptr
0x18001e0e5  test    eax, eax
0x18001e0e7  js      loc_18001EDCF
0x18001e0ed  test    esi, esi
0x18001e0ef  jz      short loc_18001E10D
0x18001e0f1  mov     rcx, r14; this
0x18001e0f4  call    ??1WorkerPoolItem@CCorSvcMgr@@QEAA@XZ; CCorSvcMgr::WorkerPoolItem::~WorkerPoolItem(void)
0x18001e0f9  mov     edx, 40h ; '@'; unsigned __int64
0x18001e0fe  mov     rcx, r14; void *
0x18001e101  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e106  mov     [rsp+878h+var_660], ebx
0x18001e10d  mov     r14, [rsp+878h+var_820]
0x18001e112  jmp     short loc_18001E138
0x18001e114  xor     ebx, ebx
0x18001e116  lea     r15d, [rbx+1]
0x18001e11a  mov     r12, [rsp+878h+var_768]
0x18001e122  mov     edi, [rsp+878h+var_818]
0x18001e126  mov     r13d, [rsp+878h+var_778]
0x18001e12e  mov     r14, [rsp+878h+var_800]
0x18001e133  mov     [rsp+878h+var_820], r14
0x18001e138  test    r13b, 2
0x18001e13c  jz      short loc_18001E143
0x18001e13e  call    ?HandleStackOverflowAfterCatch@@YAXXZ; HandleStackOverflowAfterCatch(void)
0x18001e143  add     edi, r15d
0x18001e146  mov     [rsp+878h+var_818], edi
0x18001e14a  jmp     loc_18001E023
0x18001e14f  call    ?DeleteRootList@@YAXXZ; DeleteRootList(void)
0x18001e154  call    ?DeleteRootList@RootList@@SAXXZ; RootList::DeleteRootList(void)
0x18001e159  nop
0x18001e15a  cmp     [rsp+878h+var_760], ebx
0x18001e161  jz      short loc_18001E196
0x18001e163  test    r12, r12
0x18001e166  jz      short loc_18001E18F
0x18001e168  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001e16f  test    rax, rax
0x18001e172  jnz     short loc_18001E181
0x18001e174  call    cs:__imp_GetProcessHeap
0x18001e17a  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001e181  mov     r8, r12; lpMem
0x18001e184  xor     edx, edx; dwFlags
0x18001e186  mov     rcx, rax; hHeap
0x18001e189  call    cs:__imp_HeapFree
0x18001e18f  mov     [rsp+878h+var_760], ebx
0x18001e196  lea     rax, [rsp+878h+var_7C0]
0x18001e19e  mov     [rsp+878h+var_810], rax
0x18001e1a3  lea     rcx, [rsp+878h+var_7C0]; this
0x18001e1ab  call    ??1FileLockHolder@@QEAA@XZ; FileLockHolder::~FileLockHolder(void)
0x18001e1b0  jmp     loc_18001E90F
0x18001e1b5  mov     [rsp+878h+var_398], ebx
0x18001e1bc  mov     [rsp+878h+var_394], ebx
0x18001e1c3  mov     [rsp+878h+var_390], ebx
0x18001e1ca  mov     [rsp+878h+var_388], rbx
0x18001e1d2  lea     rax, [rsp+878h+var_380]
0x18001e1da  mov     [rsp+878h+var_388], rax
0x18001e1e2  mov     [rsp+878h+var_394], 0F0h
0x18001e1ed  test    rsi, rsi
0x18001e1f0  jz      loc_18001E767
0x18001e1f6  mov     r8, rsi
0x18001e1f9  lea     rdx, aKeepingFollowi; "(Keeping following assemblies: %s)\n"
0x18001e200  mov     rcx, rdi; this
0x18001e203  call    ?Printf@Logger@@QEAAXPEBGZZ; Logger::Printf(ushort const *,...)
0x18001e208  mov     [rsp+878h+var_5B8], ebx
0x18001e20f  mov     [rsp+878h+var_5B4], ebx
0x18001e216  mov     [rsp+878h+var_5B0], ebx
0x18001e21d  mov     [rsp+878h+var_5A8], rbx
0x18001e225  lea     rax, [rsp+878h+var_5A0]
0x18001e22d  mov     [rsp+878h+var_5A8], rax
0x18001e235  mov     [rsp+878h+var_5B4], 200h
0x18001e240  mov     r14d, 2
0x18001e246  mov     [rsp+878h+var_5B8], r14d
0x18001e24e  mov     rax, [rsp+878h+var_5A8]
0x18001e256  mov     [rax], bx
0x18001e259  mov     rdx, rsi; unsigned __int16 *
0x18001e25c  lea     rcx, [rsp+878h+var_5B8]; this
0x18001e264  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18001e269  nop
0x18001e26a  lea     rcx, [rsp+878h+var_5B8]; this
0x18001e272  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001e277  mov     eax, [rsp+878h+var_5B0]
0x18001e27e  bts     eax, 8
0x18001e282  mov     [rsp+878h+var_5B0], eax
0x18001e289  shr     eax, 1
0x18001e28b  not     eax
0x18001e28d  test    r15b, al
0x18001e290  jz      short loc_18001E294
0x18001e292  jmp     short loc_18001E2B2
0x18001e294  lea     rcx, [rsp+878h+var_5B8]; this
  ... truncated ...
```
