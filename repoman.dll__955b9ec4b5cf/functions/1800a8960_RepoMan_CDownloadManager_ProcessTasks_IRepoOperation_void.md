# RepoMan::CDownloadManager::ProcessTasks(IRepoOperation *,void *)

- ea: `0x1800a8960`
- end: `0x1800a9a54`
- name: `?ProcessTasks@CDownloadManager@RepoMan@@UEAAJPEAUIRepoOperation@@PEAX@Z`
- size: `4340`
- prototype: `__int64 __fastcall(RepoMan::CDownloadManager *__hidden this, struct IRepoOperation *, void *)`
- caller_count: `0`
- callee_count: `42`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002010`
- `0x1800028e8`
- `0x180003710`
- `0x1800038ac`
- `0x180008574`
- `0x180008770`
- `0x180009368`
- `0x1800136dc`
- `0x180013b14`
- `0x1800245b4`
- `0x180024a68`
- `0x180024b44`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x180045350`
- `0x18007ad5c`
- `0x1800a5528`
- `0x1800a7e38`
- `0x1800a82d8`
- `0x1800a8960`
- `0x1800b06c4`
- `0x1800b1a90`
- `0x1800b1ce0`
- `0x1800b1de0`
- `0x1800b1eec`
- `0x1800b2cc8`
- `0x1800b2da8`
- `0x1800b3584`
- `0x1800b36e0`
- `0x1800b6e58`
- `0x1800b7c70`
- `0x1800b825c`
- `0x1800dfffc`
- `0x18018aed8`
- `0x18018cd40`
- `0x18018f7a4`
- `0x180198350`
- `0x180198860`
- `0x180198f88`
- `0x1801992c8`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800a9992`
- `KERNEL32!GetLastError` at `0x1800a9992`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x1800a8c78`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x1800a8c78`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a8f54`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a8fc9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a92cf`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a8f54`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a8fc9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a92cf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a8b74`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a91fa`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a983f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a9884`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a8b74`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a91fa`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a983f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a9884`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800a8b6d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800a91f3`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800a9350`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800a8b6d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800a91f3`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800a9350`
- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x1800a9860`
- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x1800a9860`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x1800a900b`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x1800a900b`

## string_xrefs

- `0x1800a89ad`: `CDownloadManager.ProcessTasks`
- `0x1800a8b88`: `CDownloadManager.ProcessTasks.ValidateSufficientFreeDiskSpace`
- `0x1800a8d73`: `CDownloadManager.ProcessTasks.HandleRemoveTasks`
- `0x1800a99ba`: `Insufficient free space to complete stage operation.`
- `0x1800a9129`: `useWofcompression`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
__int64 __fastcall RepoMan::CDownloadManager::ProcessTasks(
        RepoMan::CDownloadManager *this,
        struct IRepoOperation *a2,
        _QWORD *a3)
{
  _QWORD *v3; // r15
  _QWORD *v5; // rdi
  RepoMan *v6; // rcx
  const char *v7; // r9
  RepoMan *v8; // rcx
  const char *v9; // r9
  _BYTE *v10; // rax
  size_t v11; // r8
  void **v12; // rdx
  void *v13; // rcx
  __int64 v14; // rbx
  ULARGE_INTEGER v15; // rcx
  RepoMan *v16; // rcx
  const char *v17; // r9
  int v18; // edx
  int v19; // r9d
  __int64 v20; // rax
  ULARGE_INTEGER v21; // rcx
  RepoMan *v22; // rcx
  const char *v23; // r9
  unsigned __int64 v24; // rcx
  RepoMan *v25; // rcx
  const char *v26; // r9
  RepoMan *v27; // rcx
  const char *v28; // r9
  __int64 v29; // rcx
  ULARGE_INTEGER v30; // rcx
  _QWORD *v31; // rax
  _QWORD *v32; // rax
  char *WOFCompression; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rcx
  int v37; // eax
  ULARGE_INTEGER v38; // rcx
  void *v39; // rcx
  __int128 v40; // rdi
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // rax
  __int64 v43; // rbx
  __int64 v44; // rbx
  __int64 v45; // rdi
  __int64 v46; // rdx
  void *v47; // rcx
  __int64 v48; // rcx
  char v49; // al
  __int64 v50; // rcx
  int v51; // ecx
  __int64 v52; // rdx
  __int64 *v53; // rbx
  struct IRepoOperation *v54; // r15
  __int64 v55; // r14
  __int64 v56; // rsi
  __int64 v57; // rdi
  int v58; // r10d
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rcx
  void (__fastcall ***v66)(_QWORD, __int64); // r8
  __int64 **v67; // rax
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 k; // rbx
  _BYTE *v71; // rcx
  __int64 v72; // r15
  ULARGE_INTEGER v73; // rbx
  __int64 v74; // r14
  void (__fastcall ***v75)(_QWORD, ULARGE_INTEGER); // rcx
  __int64 v76; // r14
  __int64 v77; // rcx
  __int64 v78; // rbx
  unsigned int (__fastcall *v79)(__int64, __int64 *); // rdi
  RepoMan *v80; // rcx
  const char *v81; // r9
  __int64 v82; // rcx
  void *v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rcx
  __int64 v86; // rcx
  int v87; // r8d
  __int64 result; // rax
  __int64 LastError; // r9
  __int64 v90; // rdx
  __int64 v91; // rax
  __int64 v92; // rbx
  ULARGE_INTEGER v93; // rcx
  void *v94; // rcx
  __int64 v95; // rcx
  __int64 v96; // [rsp+0h] [rbp-508h] BYREF
  uintptr_t Reserved; // [rsp+20h] [rbp-4E8h]
  unsigned int *ThrdAddr; // [rsp+28h] [rbp-4E0h]
  int v99; // [rsp+38h] [rbp-4D0h]
  char v100; // [rsp+50h] [rbp-4B8h] BYREF
  unsigned __int64 v101; // [rsp+58h] [rbp-4B0h] BYREF
  ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+60h] [rbp-4A8h] BYREF
  char v103; // [rsp+68h] [rbp-4A0h]
  __int64 v104; // [rsp+70h] [rbp-498h] BYREF
  struct IRepoOperation *v105; // [rsp+78h] [rbp-490h] BYREF
  __int64 v106; // [rsp+80h] [rbp-488h] BYREF
  __int64 v107; // [rsp+88h] [rbp-480h] BYREF
  __int128 v108; // [rsp+90h] [rbp-478h] BYREF
  _QWORD *v109; // [rsp+A0h] [rbp-468h]
  __int64 v110; // [rsp+A8h] [rbp-460h] BYREF
  RepoMan::CDownloadManager *v111; // [rsp+B0h] [rbp-458h]
  __int128 v112; // [rsp+B8h] [rbp-450h] BYREF
  __int64 v113; // [rsp+C8h] [rbp-440h]
  __int64 v114; // [rsp+D0h] [rbp-438h]
  _QWORD *v115; // [rsp+D8h] [rbp-430h]
  _QWORD v116[2]; // [rsp+E0h] [rbp-428h] BYREF
  void *v117; // [rsp+F0h] [rbp-418h]
  RepoMan::CDownloadManager *v118; // [rsp+F8h] [rbp-410h]
  char v119[8]; // [rsp+100h] [rbp-408h] BYREF
  __int64 v120; // [rsp+108h] [rbp-400h]
  unsigned __int64 v121; // [rsp+110h] [rbp-3F8h]
  __int64 v122; // [rsp+118h] [rbp-3F0h]
  __int64 v123; // [rsp+120h] [rbp-3E8h]
  int v124; // [rsp+128h] [rbp-3E0h]
  uintptr_t v125; // [rsp+130h] [rbp-3D8h] BYREF
  unsigned int v126; // [rsp+138h] [rbp-3D0h] BYREF
  _QWORD v127[2]; // [rsp+140h] [rbp-3C8h] BYREF
  int v128; // [rsp+150h] [rbp-3B8h] BYREF
  __int64 v129; // [rsp+158h] [rbp-3B0h]
  __int64 v130; // [rsp+160h] [rbp-3A8h]
  __int128 v131; // [rsp+168h] [rbp-3A0h]
  __int128 v132; // [rsp+178h] [rbp-390h]
  __int128 v133; // [rsp+188h] [rbp-380h]
  __int64 v134; // [rsp+198h] [rbp-370h]
  void *v135[2]; // [rsp+1A0h] [rbp-368h] BYREF
  __int128 v136; // [rsp+1B0h] [rbp-358h]
  __int64 v137; // [rsp+1C0h] [rbp-348h]
  _QWORD v138[2]; // [rsp+1C8h] [rbp-340h] BYREF
  __int128 v139; // [rsp+1D8h] [rbp-330h]
  __int128 v140; // [rsp+1E8h] [rbp-320h]
  __int128 v141; // [rsp+1F8h] [rbp-310h]
  __int64 v142; // [rsp+208h] [rbp-300h]
  char v143; // [rsp+210h] [rbp-2F8h]
  _QWORD v144[3]; // [rsp+220h] [rbp-2E8h] BYREF
  _QWORD v145[11]; // [rsp+238h] [rbp-2D0h] BYREF
  char v146; // [rsp+290h] [rbp-278h] BYREF
  RepoMan::Exception *v147; // [rsp+298h] [rbp-270h] BYREF
  _BYTE v148[80]; // [rsp+2A0h] [rbp-268h] BYREF
  void *v149[2]; // [rsp+2F0h] [rbp-218h] BYREF
  _BYTE v150[32]; // [rsp+300h] [rbp-208h] BYREF
  _BYTE v151[16]; // [rsp+320h] [rbp-1E8h] BYREF
  char v152[8]; // [rsp+330h] [rbp-1D8h] BYREF
  _BYTE v153[128]; // [rsp+338h] [rbp-1D0h] BYREF
  _QWORD v154[13]; // [rsp+3B8h] [rbp-150h] BYREF
  _BYTE v155[48]; // [rsp+420h] [rbp-E8h] BYREF
  void *Block[2]; // [rsp+450h] [rbp-B8h] BYREF
  __m128i si128; // [rsp+460h] [rbp-A8h]
  __int128 v158; // [rsp+470h] [rbp-98h] BYREF
  __m128i v159; // [rsp+480h] [rbp-88h]
  _BYTE v160[40]; // [rsp+490h] [rbp-78h] BYREF
  __int64 v161; // [rsp+4B8h] [rbp-50h]

  v3 = a3;
  v115 = a3;
  v118 = this;
  v111 = this;
  v105 = a2;
  v114 = 2;
  RepoMan::Tracer::Tracer(v160, 2, "CDownloadManager.ProcessTasks");
  try
  {
    if ( !v105 || !v3 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        1392,
        (unsigned int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp",
        (unsigned int)"invalid argument",
        -2147024809,
        8);
    v106 = 0;
    v5 = (_QWORD *)((char *)this + 48);
    v109 = (_QWORD *)((char *)this + 48);
    v6 = (RepoMan *)(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(*((_QWORD *)this + 6) + 8LL) + 24LL))(
                      *((_QWORD *)this + 6) + 8LL,
                      &v106);
    RepoMan::RaiseExceptionIfFailed(v6, 1394, (int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp", v7);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v106 + 32LL))(v106) )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        1395,
        (unsigned int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp",
        (unsigned int)"user cancelled.",
        -1941503743,
        8);
    v117 = (void *)(*(__int64 (__fastcall **)(struct IRepoOperation *))(*(_QWORD *)v105 + 24LL))(v105);
    v116[0] = v3;
    v110 = 0;
    v8 = (RepoMan *)(*(unsigned int (__fastcall **)(struct IRepoOperation *, __int64 *))(*(_QWORD *)v105 + 48LL))(
                      v105,
                      &v110);
    RepoMan::RaiseExceptionIfFailed(v8, 1401, (int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp", v9);
    v10 = (_BYTE *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v110 + 24LL))(v110);
    *(_OWORD *)Block = 0;
    si128 = 0;
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    std::string::_Construct<1,char const *>(Block, v10, v11);
    v158 = 0;
    v159 = 0;
    v12 = Block;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v12 = (void **)Block[0];
    std::string::_Construct<2,char const *>(&v158, v12, si128.m128i_u64[0]);
    if ( si128.m128i_i64[1] > 0xFuLL )
    {
      v13 = Block[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v13 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v13 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v13);
    }
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v151);
    std::operator<<<std::char_traits<char>>(
      (__int64)v152,
      (__int64)"CDownloadManager.ProcessTasks.ValidateSufficientFreeDiskSpace");
    std::stringbuf::str(v153, Block);
    RepoMan::Logger::CreateValue((unsigned int)&TotalNumberOfFreeBytes, 1, 8, (unsigned int)Block, 0);
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v154);
    v154[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v154);
    v14 = v161;
    (*(void (__fastcall **)(__int64, ULARGE_INTEGER *))(*(_QWORD *)v161 + 48LL))(v161, &TotalNumberOfFreeBytes);
    v15 = TotalNumberOfFreeBytes;
    if ( TotalNumberOfFreeBytes.QuadPart )
    {
      TotalNumberOfFreeBytes.QuadPart = 0;
      (*(void (__fastcall **)(ULARGE_INTEGER))(*(_QWORD *)v15.QuadPart + 8LL))(v15);
    }
    v101 = 0;
    TotalNumberOfFreeBytes.QuadPart = 0;
    if ( !GetDiskFreeSpaceExW(0, 0, 0, &TotalNumberOfFreeBytes) )
    {
      LastError = GetLastError();
      RepoMan::RaiseException<RepoMan::Win32Exception,unsigned long>(631, v90, "GetDiskFreeSpaceEx failed", LastError);
    }
    *(ULARGE_INTEGER *)&v108 = TotalNumberOfFreeBytes;
    v16 = (RepoMan *)(*(unsigned int (__fastcall **)(struct IRepoOperation *, unsigned __int64 *))(*(_QWORD *)v105
                                                                                                 + 144LL))(
                       v105,
                       &v101);
    RepoMan::RaiseExceptionIfFailed(v16, 1407, (int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp", v17);
    v20 = RepoMan::Logger::Message<char const (&)[7],unsigned __int64 &,char const (&)[12],unsigned __int64 &>(
            (unsigned int)&TotalNumberOfFreeBytes,
            v18,
            (unsigned int)&v108,
            v19,
            (__int64)&v101);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 48LL))(v14, v20);
    v21 = TotalNumberOfFreeBytes;
    if ( TotalNumberOfFreeBytes.QuadPart )
    {
      TotalNumberOfFreeBytes.QuadPart = 0;
      (*(void (__fastcall **)(ULARGE_INTEGER))(*(_QWORD *)v21.QuadPart + 8LL))(v21);
    }
    if ( v101 >= (unsigned __int64)v108 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        1409,
        (unsigned int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp",
        (unsigned int)"Insufficient free space to complete stage operation.",
        -1941503888,
        8);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v106 + 32LL))(v106) )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        1412,
        (unsigned int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp",
        (unsigned int)"user cancelled.",
        -1941503743,
        8);
    v104 = 0;
    v22 = (RepoMan *)(*(unsigned int (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v5 + 48LL))(*v5, &v104);
    RepoMan::RaiseExceptionIfFailed(v22, 1414, (int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp", v23);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v151);
    std::operator<<<std::char_traits<char>>((__int64)v152, (__int64)"CDownloadManager.ProcessTasks.HandleRemoveTasks");
    std::stringbuf::str(v153, Block);
    RepoMan::Logger::CreateValue((unsigned int)&v101, 1, 8, (unsigned int)Block, 0);
    std::string::_Tidy_deallocate(Block);
    Block[0] = (void *)19937;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v154);
    v154[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v154);
    (*(void (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v14 + 48LL))(v14, &v101);
    v24 = v101;
    if ( v101 )
    {
      v101 = 0;
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v24 + 8LL))(v24);
    }
    LODWORD(v101) = 0;
    v25 = (RepoMan *)(*(unsigned int (__fastcall **)(struct IRepoOperation *, unsigned __int64 *))(*(_QWORD *)v105 + 80LL))(
                       v105,
                       &v101);
    RepoMan::RaiseExceptionIfFailed(v25, 1421, (int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp", v26);
    TotalNumberOfFreeBytes.QuadPart = 0;
    v27 = (RepoMan *)(*(unsigned int (__fastcall **)(struct IRepoOperation *, __int64, _QWORD, ULARGE_INTEGER *))(*(_QWORD *)v105 + 72LL))(
                       v105,
                       1,
                       17 - (unsigned int)((_DWORD)v101 != 2),
                       &TotalNumberOfFreeBytes);
    RepoMan::RaiseExceptionIfFailed(v27, 1432, (int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp", v28);
    ___DoTasks_V_lambda_2___BB___ProcessTasks_CDownloadManager_RepoMan__UEAAJPEAUIRepoOperation__PEAX_Z____DownloadManagerBase___V_RepoMan__QEAAXAEAV__ComPtr_UIRepoFileTasks___1_PEAUIRepoFileTasks__V_lambda_2___BB___ProcessTasks_CDownloadManager_1_UEAAJPEAUIRepoOperation__PEAX_Z__Z(
      v29,
      (__int64)&v104,
      TotalNumberOfFreeBytes.QuadPart,
      &v106);
    v30 = TotalNumberOfFreeBytes;
    if ( TotalNumberOfFreeBytes.QuadPart )
    {
      TotalNumberOfFreeBytes.QuadPart = 0;
      (*(void (__fastcall **)(ULARGE_INTEGER))(*(_QWORD *)v30.QuadPart + 16LL))(v30);
    }
    v128 = 0;
    v129 = 0;
    v130 = 0;
    v131 = 0;
    v132 = 0;
    v133 = 0;
    v134 = 0;
    Mtx_init_in_situ((_Mtx_t)&v128, 2);
    *(_OWORD *)v135 = 0;
    v136 = 0u;
    v137 = 0;
    v31 = malloc(0x10u);
    if ( !v31 )
      std::_Xbad_alloc();
    v31[1] = 0;
    v135[0] = v31;
    *v31 = v135;
    v138[0] = 0;
    v138[1] = 0;
    v139 = 0;
    v140 = 0;
    v141 = 0;
    v142 = 0;
    __ExceptionPtrCreate(v138);
    v143 = 1;
    v32 = malloc(8u);
    if ( !v32 )
      std::_Xbad_alloc();
    *v32 = &v128;
    *(_QWORD *)&v108 = v32;
    v125 = _beginthreadex(
             0,
             0,
             (_beginthreadex_proc_type)std::thread::_Invoke<Z::tuple<`RepoMan::CDownloadManager::ProcessTasks'::`3'::_lambda_3_,EAAJPEAUIRepoOperation,void *>,std,0>,
             v32,
             0,
             &v126);
    if ( !v125 )
    {
      v126 = 0;
      std::_Throw_Cpp_error(6);
    }
    v100 = 0;
    RepoMan::Task::Telemetry::Telemetry((RepoMan::Task::Telemetry *)v148);
    Block[0] = &v128;
    Block[1] = &v125;
    si128.m128i_i64[0] = (__int64)&v100;
    si128.m128i_i64[1] = (__int64)v148;
    Z::Z((__int64)v155, Block);
    v107 = 0;
    if ( (unsigned __int8)RepoMan::CRepoMan::FlightValue(*v5, 6) )
    {
      try
      {
        WOFCompression = (char *)RepoMan::FileSystem::GetWOFCompression(&v108);
        v34 = 0;
        if ( &v146 != WOFCompression )
        {
          v34 = *(_QWORD *)WOFCompression;
          *(_QWORD *)WOFCompression = 0;
        }
        v35 = v107;
        v107 = v34;
        if ( v35 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        v36 = v108;
        if ( (_QWORD)v108 )
        {
          *(_QWORD *)&v108 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        }
        *(_OWORD *)Block = 0;
        si128 = 0;
        std::string::_Construct<1,char const *>(Block, "useWofcompression", 0x11u);
        v37 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v107 + 24LL))(v107);
        RepoMan::Logger::CreateValue((unsigned int)&TotalNumberOfFreeBytes, 3, 11, (unsigned int)Block, v37 == 1);
        (*(void (__fastcall **)(__int64, ULARGE_INTEGER *))(*(_QWORD *)v14 + 48LL))(v14, &TotalNumberOfFreeBytes);
        v38 = TotalNumberOfFreeBytes;
        if ( TotalNumberOfFreeBytes.QuadPart )
        {
          TotalNumberOfFreeBytes.QuadPart = 0;
          (*(void (__fastcall **)(ULARGE_INTEGER))(*(_QWORD *)v38.QuadPart + 8LL))(v38);
        }
        if ( si128.m128i_i64[1] > 0xFuLL )
        {
          v39 = Block[0];
          if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
          {
            v39 = (void *)*((_QWORD *)Block[0] - 1);
            if ( (unsigned __int64)((char *)Block[0] - (char *)v39 - 8) > 0x1F )
              _invoke_watson(0, 0, 0, 0, 0);
          }
          free(v39);
        }
      }
      catch ( RepoMan::Exception *v147 )
      {
        LODWORD(v101) = *((_DWORD *)v147 + 8);
        v91 = RepoMan::Logger::Message<char const (&)[43],unsigned int,char const (&)[2]>(&v108, &v96, &v101);
        v92 = v161;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v161 + 48LL))(v161, v91);
        *(_OWORD *)Block = 0;
        si128 = 0u;
        std::string::_Construct<1,char const *>(Block, "useWofcompression", 0x11u);
        RepoMan::Logger::CreateValue((unsigned int)&TotalNumberOfFreeBytes, 3, 11, (unsigned int)Block, 0);
        (*(void (__fastcall **)(__int64, ULARGE_INTEGER *))(*(_QWORD *)v92 + 48LL))(v92, &TotalNumberOfFreeBytes);
        v93 = TotalNumberOfFreeBytes;
        if ( TotalNumberOfFreeBytes.QuadPart )
        {
          TotalNumberOfFreeBytes.QuadPart = 0;
          (*(void (__fastcall **)(ULARGE_INTEGER))(*(_QWORD *)v93.QuadPart + 8LL))(v93);
        }
        if ( si128.m128i_i64[1] > 0xFuLL )
        {
          v94 = Block[0];
          if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
          {
            if ( (unsigned __int64)Block[0] - *((_QWORD *)Block[0] - 1) - 8 > 0x1F )
              _invoke_watson(0, 0, 0, 0, 0);
            v94 = (void *)*((_QWORD *)Block[0] - 1);
          }
          free(v94);
        }
        v95 = v108;
        if ( (_QWORD)v108 )
        {
          *(_QWORD *)&v108 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 8LL))(v95);
        }
        v114 = 2;
        v3 = (_QWORD *)v116[0];
        v115 = (_QWORD *)v116[0];
        v118 = v111;
      }
    }
    *((_QWORD *)&v40 + 1) = 0;
    while ( 1 )
    {
      *(_QWORD *)&v108 = &v104;
      *((_QWORD *)&v108 + 1) = &v105;
      std::deque<std::function<void (void)>>::deque<std::function<void (void)>>(v119);
      v124 = 0;
      v41 = v121;
      if ( v121 <= v123 + 1 )
      {
        std::deque<std::function<void (void)>>::_Growmap(v119);
        v41 = v121;
      }
      v42 = v41 - 1;
      v43 = (v41 - 1) & v122;
      v122 = v43;
      if ( !v43 )
        v43 = v41;
      v44 = v43 - 1;
      v45 = v42 & v44;
      v46 = v120;
      if ( !*(_QWORD *)(v120 + 8 * (v42 & v44)) )
      {
        v47 = malloc(0x40u);
        if ( !v47 )
          std::_Xbad_alloc();
        *(_QWORD *)(v120 + 8 * v45) = v47;
        v41 = v121;
        v46 = v120;
      }
      v48 = *(_QWORD *)(v46 + 8 * (v44 & (v41 - 1)));
      *(_QWORD *)v48 = std::X$$V::Z::_Func_impl_no_alloc<`RepoMan::CDownloadManager::ProcessTasks'::`25'::_lambda_5_,EAAJPEAUIRepoOperation,void *>::`vftable';
      *(_OWORD *)(v48 + 8) = v108;
      *(_QWORD *)(v48 + 56) = v48;
      v122 = v44;
      if ( !++v123 )
        _invoke_watson(0, 0, 0, 0, 0);
      v49 = RepoMan::CRepoMan::FlightValue(*v109, 4);
      *(_QWORD *)&v40 = v117;
      if ( v49 )
      {
        Block[0] = v117;
        Block[1] = v3;
        si128.m128i_i8[0] = *((_QWORD *)&v40 + 1) == 0;
        Z::Execute<`RepoMan::CDownloadManager::PrepareForHardlinking'::`2'::_lambda_1_,RepoMan::AX_KPEAVSchema * const,bool>(
          v3[1660],
          Block);
      }
      RepoMan::CDownloadManager::PrepareRanges(v50, v40, v105, v3);
      RepoMan::CDownloadManager::PrepareGroups(
        v51,
        (unsigned int)v127,
        v40,
        (_DWORD)v3,
        Reserved,
        (_DWORD)ThrdAddr,
        *((_QWORD *)&v40 + 1) == 0,
        v99,
        (__int64)&v107);
      v111 = 0;
      v112 = 0;
      v113 = 0;
      v53 = *(__int64 **)v127[0];
      *((_QWORD *)&v112 + 1) = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      while ( !*((_BYTE *)v53 + 25) )
      {
        v54 = v105;
        v55 = v106;
        v56 = v104;
        v57 = v53[4];
        v58 = (unsigned __int8)RepoMan::CRepoMan::FlightValue(*v109, 1) ^ 1;
        v59 = *((_QWORD *)v118 + 7);
        v60 = *v109;
        v144[0] = v57;
        v144[1] = &v128;
        v144[2] = v56;
        v61 = v53[7];
        v53[7] = 0;
        v62 = v53[6];
        v53[6] = 0;
        v63 = v53[5];
        v53[5] = 0;
        v145[0] = v63;
        v145[1] = v62;
        v145[2] = v61;
        v145[3] = &v100;
        v145[4] = v148;
        v145[5] = v115;
        v145[6] = &v158;
        v145[7] = v55;
        v145[8] = v54;
        v145[9] = v59;
        v145[10] = v60;
        ___async_V_lambda_1___1__ProcessGroup_CDownloadManager_RepoMan__QEAA_AV__future__K_std___JPEAVStreamHarvester_4_PEAUIRepoFileTasks__PEAU__atomic__N_6_PEAVTelemetry_Task_4_PEAVSchema_4_PEAVFolder_4_PEAUIRepoProgress__PEAUIRepoOperation____QEAV__vector_VTask_RepoMan__V__allocator_VTask_RepoMan___std___6__Z___V_std__YA_AV__future__K_0_W4launch_0___QEAV_lambda_1___1__ProcessGroup_CDownloadManager_RepoMan__QEAA_AV10__JPEAVStreamHarvester_6_PEAUIRepoFileTasks__PEAU__atomic__N_0_PEAVTelemetry_Task_6_PEAVSchema_6_PEAVFolder_6_PEAUIRepoProgress__PEAUIRepoOperation____QEAV__vector_VTask_RepoMan__V__allocator_VTask_RepoMan___std___0__Z__Z(
          (__int64)v116,
          v58 + 1,
          v144);
        std::vector<RepoMan::Task>::~vector<RepoMan::Task>(v145);
        v52 = *((_QWORD *)&v112 + 1);
        if ( *((_QWORD *)&v112 + 1) == v113 )
        {
          std::vector<std::future<unsigned __int64>>::_Emplace_reallocate<std::future<unsigned __int64>>(
            &v112,
            *((_QWORD *)&v112 + 1),
            v116);
          v65 = v116[0];
        }
        else
        {
          v64 = v116[0];
          v65 = 0;
          v116[0] = 0;
          **((_QWORD **)&v112 + 1) = v64;
          *(_BYTE *)(v52 + 8) = 1;
          *((_QWORD *)&v112 + 1) += 16LL;
        }
        if ( v65 && _InterlockedExchangeAdd((volatile signed __int32 *)(v65 + 8), 0xFFFFFFFF) == 1 )
        {
          v66 = *(void (__fastcall ****)(_QWORD, __int64))(v65 + 208);
          if ( v66 )
            (**v66)(*(_QWORD *)(v65 + 208), v65);
          else
            (**(void (__fastcall ***)(__int64, __int64))v65)(v65, 1);
        }
        v67 = (__int64 **)v53[2];
        if ( *((_BYTE *)v67 + 25) )
        {
          for ( i = (__int64 *)v53[1]; !*((_BYTE *)i + 25) && v53 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v53 = i;
          v53 = i;
        }
        else
        {
          v53 = (__int64 *)v53[2];
          for ( j = *v67; !*((_BYTE *)j + 25); j = (__int64 *)*j )
            v53 = j;
        }
      }
      v40 = v112;
      for ( k = v112; k != *((_QWORD *)&v40 + 1); k += 16 )
      {
        v71 = *(_BYTE **)k;
        if ( !*(_QWORD *)k || *(_BYTE *)(k + 8) && v71[192] )
          std::_Throw_future_error2(4);
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v71 + 8LL))(v71);
        *(_QWORD *)&v40 = v112;
      }
      v72 = *((_QWORD *)&v112 + 1);
      *((_QWORD *)&v40 + 1) = v111;
      while ( (_QWORD)v40 != v72 )
      {
        v73 = *(ULARGE_INTEGER *)v40;
        *(_QWORD *)v40 = 0;
        TotalNumberOfFreeBytes = v73;
        v103 = 1;
        if ( !v73.QuadPart || *(_BYTE *)(v73.QuadPart + 192) )
          std::_Throw_future_error2(4);
        LOBYTE(v52) = 1;
        v74 = *(_QWORD *)(*(__int64 (__fastcall **)(ULARGE_INTEGER, __int64))(*(_QWORD *)v73.QuadPart + 16LL))(v73, v52);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v73.QuadPart + 8), 0xFFFFFFFF) == 1 )
        {
          v75 = *(void (__fastcall ****)(_QWORD, ULARGE_INTEGER))(v73.QuadPart + 208);
          if ( v75 )
            (**v75)(v75, v73);
          else
            (**(void (__fastcall ***)(ULARGE_INTEGER, __int64))v73.QuadPart)(v73, 1);
        }
        *((_QWORD *)&v40 + 1) += v74;
        *(_QWORD *)&v40 = v40 + 16;
      }
      v76 = v114 - 1;
      if ( !*((_QWORD *)&v40 + 1) )
        v76 = 0;
      v114 = v76;
      std::vector<std::future<unsigned __int64>>::~vector<std::future<unsigned __int64>>(&v112);
      std::_Tree<std::_Tmap_traits<__int64,std::vector<RepoMan::Task>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::vector<RepoMan::Task>>>,0>>::~_Tree<std::_Tmap_traits<__int64,std::vector<RepoMan::Task>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::vector<RepoMan::Task>>>,0>>(v127);
      RepoMan::Meta::ScopeGuard::~ScopeGuard((RepoMan::Meta::ScopeGuard *)v119);
      v77 = v104;
      if ( v104 )
      {
        v104 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
        v77 = v104;
      }
      if ( !v76 )
        break;
      v78 = *v109;
      v79 = *(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v109 + 48LL);
      if ( v77 )
      {
        v104 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
      }
      v80 = (RepoMan *)v79(v78, &v104);
      RepoMan::RaiseExceptionIfFailed(v80, 1544, (int)"src\\repoman\\src\\repoman\\DownloadManagers.hpp", v81);
      v3 = v115;
    }
    v150[28] = 1;
    v82 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
    }
    RepoMan::Meta::ScopeGuard::~ScopeGuard((RepoMan::Meta::ScopeGuard *)v155);
    std::_Tree<std::_Tmap_traits<enum RepoMan::Task::Telemetry::Scenario,std::string,std::less<enum RepoMan::Task::Telemetry::Scenario>,std::allocator<std::pair<enum RepoMan::Task::Telemetry::Scenario const,std::string>>,0>>::~_Tree<std::_Tmap_traits<enum RepoMan::Task::Telemetry::Scenario,std::string,std::less<enum RepoMan::Task::Telemetry::Scenario>,std::allocator<std::pair<enum RepoMan::Task::Telemetry::Scenario const,std::string>>,0>>(v150);
    std::_Tree_val<std::_Tree_simple_types<std::pair<enum RepoMan::Task::Telemetry::Scenario const,std::map<long,unsigned __int64>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum RepoMan::Task::Telemetry::Scenario const,std::map<long,unsigned __int64>>,void *>>>(
      (__int64)v149,
      (__int64)v149,
      *((void ***)v149[0] + 1));
    free(v149[0]);
    *(__m128i *)v149 = _mm_load_si128((const __m128i *)&_xmm);
    if ( v126 )
      terminate();
    std::deque<RepoMan::ComPtr<IStream>>::_Tidy(v135);
    v83 = v135[0];
    v135[0] = 0;
    free(v83);
    v135[1] = (void *)19937;
    v136 = 0;
    v137 = 0;
    v84 = v104;
    if ( v104 )
    {
      v104 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
    }
    std::string::_Tidy_deallocate(&v158);
    *(_QWORD *)&v158 = 19937;
    v159 = _mm_load_si128((const __m128i *)&_xmm);
    v85 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    }
    v86 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
    }
    RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v160);
    result = 0;
  }
  catch ( ... )
  {
    RepoMan::Lippincott((RepoMan *)"src\\repoman\\src\\repoman\\DownloadManagers.hpp", (const char *)0x610, v87);
  }
  return result;
}

```

## disassembly

```asm
0x1800a8960  mov     r11, rsp
0x1800a8963  push    rbx
0x1800a8964  push    rsi
0x1800a8965  push    rdi
0x1800a8966  push    r12
0x1800a8968  push    r13
0x1800a896a  push    r14
0x1800a896c  push    r15
0x1800a896e  sub     rsp, 4D0h
0x1800a8975  mov     rax, cs:__security_cookie
0x1800a897c  xor     rax, rsp
0x1800a897f  mov     [rsp+508h+var_48], rax
0x1800a8987  mov     r15, r8
0x1800a898a  mov     [rsp+508h+var_430], r8
0x1800a8992  mov     rbx, rcx
0x1800a8995  mov     [rsp+508h+var_410], rcx
0x1800a899d  mov     [rsp+508h+var_458], rcx
0x1800a89a5  mov     [rsp+508h+var_490], rdx
0x1800a89aa  xor     r12d, r12d
0x1800a89ad  lea     r8, aCdownloadmanag_10; "CDownloadManager.ProcessTasks"
0x1800a89b4  lea     r14d, [r12+2]
0x1800a89b9  mov     [rsp+508h+var_438], r14
0x1800a89c1  mov     edx, r14d
0x1800a89c4  lea     rcx, [r11-78h]
0x1800a89c8  call    ??0Tracer@RepoMan@@QEAA@W4Verbosity@ILogger@1@QEBD@Z; RepoMan::Tracer::Tracer(RepoMan::ILogger::Verbosity,char const * const)
0x1800a89cd  nop
0x1800a89ce  cmp     [rsp+508h+var_490], r12
0x1800a89d3  jz      loc_1800A9A2C
0x1800a89d9  test    r15, r15
0x1800a89dc  jz      loc_1800A9A2C
0x1800a89e2  mov     [rsp+508h+var_488], r12
0x1800a89ea  lea     rdi, [rbx+30h]
0x1800a89ee  mov     [rsp+508h+var_468], rdi
0x1800a89f6  mov     rcx, [rdi]
0x1800a89f9  add     rcx, 8
0x1800a89fd  mov     rax, [rcx]
0x1800a8a00  lea     rdx, [rsp+508h+var_488]
0x1800a8a08  mov     rax, [rax+18h]
0x1800a8a0c  call    cs:__guard_dispatch_icall_fptr
0x1800a8a12  mov     ecx, eax; this
0x1800a8a14  lea     r13, aSrcRepomanSrcR_2; "src\\repoman\\src\\repoman\\DownloadMan"...
0x1800a8a1b  mov     r8, r13; int
0x1800a8a1e  mov     edx, 572h; int
0x1800a8a23  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800a8a28  mov     rcx, [rsp+508h+var_488]
0x1800a8a30  mov     rax, [rcx]
0x1800a8a33  mov     rax, [rax+20h]
0x1800a8a37  call    cs:__guard_dispatch_icall_fptr
0x1800a8a3d  test    eax, eax
0x1800a8a3f  jnz     loc_1800A996F
0x1800a8a45  mov     rcx, [rsp+508h+var_490]
0x1800a8a4a  mov     rax, [rcx]
0x1800a8a4d  mov     rax, [rax+18h]
0x1800a8a51  call    cs:__guard_dispatch_icall_fptr
0x1800a8a57  mov     [rsp+508h+var_418], rax
0x1800a8a5f  mov     [rsp+508h+var_428], r15
0x1800a8a67  mov     [rsp+508h+var_460], r12
0x1800a8a6f  mov     rcx, [rsp+508h+var_490]
0x1800a8a74  mov     rdx, [rcx]
0x1800a8a77  mov     rax, [rdx+30h]
0x1800a8a7b  lea     rdx, [rsp+508h+var_460]
0x1800a8a83  call    cs:__guard_dispatch_icall_fptr
0x1800a8a89  mov     ecx, eax; this
0x1800a8a8b  mov     r8, r13; int
0x1800a8a8e  mov     edx, 579h; int
0x1800a8a93  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800a8a98  mov     rcx, [rsp+508h+var_460]
0x1800a8aa0  mov     rax, [rcx]
0x1800a8aa3  mov     rax, [rax+18h]
0x1800a8aa7  call    cs:__guard_dispatch_icall_fptr
0x1800a8aad  xorps   xmm0, xmm0
0x1800a8ab0  movups  xmmword ptr [rsp+508h+Block], xmm0
0x1800a8ab8  xorps   xmm1, xmm1
0x1800a8abb  movdqu  [rsp+508h+var_A8], xmm1
0x1800a8ac4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a8ac8  inc     r8
0x1800a8acb  cmp     [rax+r8], r12b
0x1800a8acf  jnz     short loc_1800A8AC8
0x1800a8ad1  mov     rdx, rax
0x1800a8ad4  lea     rcx, [rsp+508h+Block]
0x1800a8adc  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800a8ae1  nop
0x1800a8ae2  xorps   xmm0, xmm0
0x1800a8ae5  movups  [rsp+508h+var_98], xmm0
0x1800a8aed  xorps   xmm1, xmm1
0x1800a8af0  movdqu  [rsp+508h+var_88], xmm1
0x1800a8af9  lea     rdx, [rsp+508h+Block]
0x1800a8b01  cmp     qword ptr [rsp+508h+var_A8+8], 0Fh
0x1800a8b0a  cmova   rdx, [rsp+508h+Block]
0x1800a8b13  mov     r8, qword ptr [rsp+508h+var_A8]
0x1800a8b1b  lea     rcx, [rsp+508h+var_98]
0x1800a8b23  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800a8b28  nop
0x1800a8b29  mov     rax, qword ptr [rsp+508h+var_A8+8]
0x1800a8b31  cmp     rax, 0Fh
0x1800a8b35  jbe     short loc_1800A8B7B
0x1800a8b37  mov     rcx, [rsp+508h+Block]; Block
0x1800a8b3f  mov     rdx, rcx
0x1800a8b42  inc     rax
0x1800a8b45  cmp     rax, 1000h
0x1800a8b4b  jb      short loc_1800A8B74
0x1800a8b4d  mov     rcx, [rcx-8]
0x1800a8b51  sub     rdx, rcx
0x1800a8b54  lea     rax, [rdx-8]
0x1800a8b58  cmp     rax, 1Fh
0x1800a8b5c  jbe     short loc_1800A8B74
0x1800a8b5e  mov     [rsp+508h+Reserved], r12; Reserved
0x1800a8b63  xor     r9d, r9d; LineNo
0x1800a8b66  xor     r8d, r8d; FileName
0x1800a8b69  xor     edx, edx; FunctionName
0x1800a8b6b  xor     ecx, ecx; Expression
0x1800a8b6d  call    cs:__imp__invoke_watson
0x1800a8b74  call    cs:__imp_free
0x1800a8b7a  nop
0x1800a8b7b  lea     rcx, [rsp+508h+var_1E8]
0x1800a8b83  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x1800a8b88  lea     rdx, aCdownloadmanag_5; "CDownloadManager.ProcessTasks.ValidateS"...
0x1800a8b8f  lea     rcx, [rsp+508h+var_1D8]
0x1800a8b97  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800a8b9c  lea     rdx, [rsp+508h+Block]
0x1800a8ba4  lea     rcx, [rsp+508h+var_1D0]
0x1800a8bac  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEGBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1800a8bb1  mov     [rsp+508h+Reserved], r12
0x1800a8bb6  lea     r9, [rsp+508h+Block]
0x1800a8bbe  mov     edx, 1
0x1800a8bc3  lea     r8d, [rdx+7]
0x1800a8bc7  lea     rcx, [rsp+508h+TotalNumberOfFreeBytes]
0x1800a8bcc  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x1800a8bd1  lea     rcx, [rsp+508h+Block]
0x1800a8bd9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800a8bde  mov     esi, 4DE1h
0x1800a8be3  mov     [rsp+508h+Block], rsi
0x1800a8beb  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x1800a8bf3  movdqu  [rsp+508h+var_A8], xmm0
0x1800a8bfc  lea     rcx, [rsp+508h+var_150]
0x1800a8c04  call    ??1?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x1800a8c09  nop
0x1800a8c0a  lea     rax, ??_7ios_base@std@@6B@; const std::ios_base::`vftable'
0x1800a8c11  mov     [rsp+508h+var_150], rax
0x1800a8c19  lea     rcx, [rsp+508h+var_150]; this
0x1800a8c21  call    ?_Ios_base_dtor@ios_base@std@@CAXPEAV12@@Z; std::ios_base::_Ios_base_dtor(std::ios_base *)
0x1800a8c26  nop
0x1800a8c27  mov     rbx, [rsp+508h+var_50]
0x1800a8c2f  mov     rax, [rbx]
0x1800a8c32  lea     rdx, [rsp+508h+TotalNumberOfFreeBytes]
0x1800a8c37  mov     rcx, rbx
0x1800a8c3a  mov     rax, [rax+30h]
0x1800a8c3e  call    cs:__guard_dispatch_icall_fptr
0x1800a8c44  nop
0x1800a8c45  mov     rcx, qword ptr [rsp+508h+TotalNumberOfFreeBytes]
0x1800a8c4a  test    rcx, rcx
0x1800a8c4d  jz      short loc_1800A8C62
0x1800a8c4f  mov     qword ptr [rsp+508h+TotalNumberOfFreeBytes], r12
0x1800a8c54  mov     rax, [rcx]
0x1800a8c57  mov     rax, [rax+8]
0x1800a8c5b  call    cs:__guard_dispatch_icall_fptr
0x1800a8c61  nop
0x1800a8c62  mov     [rsp+508h+var_4B0], r12
0x1800a8c67  mov     qword ptr [rsp+508h+TotalNumberOfFreeBytes], r12
0x1800a8c6c  lea     r9, [rsp+508h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x1800a8c71  xor     r8d, r8d; lpTotalNumberOfBytes
0x1800a8c74  xor     edx, edx; lpFreeBytesAvailableToCaller
0x1800a8c76  xor     ecx, ecx; lpDirectoryName
0x1800a8c78  call    cs:__imp_GetDiskFreeSpaceExW
0x1800a8c7e  test    eax, eax
0x1800a8c80  jz      loc_1800A9992
0x1800a8c86  mov     rax, qword ptr [rsp+508h+TotalNumberOfFreeBytes]
0x1800a8c8b  mov     qword ptr [rsp+508h+var_478], rax
0x1800a8c93  mov     rcx, [rsp+508h+var_490]
0x1800a8c98  mov     rax, [rcx]
0x1800a8c9b  lea     rdx, [rsp+508h+var_4B0]
0x1800a8ca0  mov     rax, [rax+90h]
0x1800a8ca7  call    cs:__guard_dispatch_icall_fptr
0x1800a8cad  mov     ecx, eax; this
0x1800a8caf  mov     r8, r13; int
0x1800a8cb2  mov     edx, 57Fh; int
0x1800a8cb7  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800a8cbc  lea     rax, [rsp+508h+var_4B0]
0x1800a8cc1  mov     [rsp+508h+Reserved], rax
0x1800a8cc6  lea     r8, [rsp+508h+var_478]
0x1800a8cce  lea     rcx, [rsp+508h+TotalNumberOfFreeBytes]
0x1800a8cd3  call    ??$Message@AEAY06$$CBDAEA_KAEAY0M@$$CBDAEA_K@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@1@AEAY06$$CBDAEA_KAEAY0M@$$CBD1@Z; RepoMan::Logger::Message<char const (&)[7],unsigned __int64 &,char const (&)[12],unsigned __int64 &>(char const (&)[7],unsigned __int64 &,char const (&)[12],unsigned __int64 &)
0x1800a8cd8  mov     rcx, [rbx]
0x1800a8cdb  mov     r8, [rcx+30h]
0x1800a8cdf  mov     rdx, rax
0x1800a8ce2  mov     rcx, rbx
0x1800a8ce5  mov     rax, r8
0x1800a8ce8  call    cs:__guard_dispatch_icall_fptr
0x1800a8cee  nop
0x1800a8cef  mov     rcx, qword ptr [rsp+508h+TotalNumberOfFreeBytes]
0x1800a8cf4  test    rcx, rcx
0x1800a8cf7  jz      short loc_1800A8D0C
0x1800a8cf9  mov     qword ptr [rsp+508h+TotalNumberOfFreeBytes], r12
0x1800a8cfe  mov     rax, [rcx]
0x1800a8d01  mov     rax, [rax+8]
0x1800a8d05  call    cs:__guard_dispatch_icall_fptr
0x1800a8d0b  nop
0x1800a8d0c  mov     rax, qword ptr [rsp+508h+var_478]
0x1800a8d14  cmp     [rsp+508h+var_4B0], rax
0x1800a8d19  jnb     loc_1800A99AC
0x1800a8d1f  mov     rcx, [rsp+508h+var_488]
0x1800a8d27  mov     rax, [rcx]
0x1800a8d2a  mov     rax, [rax+20h]
0x1800a8d2e  call    cs:__guard_dispatch_icall_fptr
0x1800a8d34  test    eax, eax
0x1800a8d36  jnz     loc_1800A99CE
0x1800a8d3c  mov     [rsp+508h+var_498], r12
0x1800a8d41  mov     rcx, [rdi]
0x1800a8d44  mov     rax, [rcx]
0x1800a8d47  lea     rdx, [rsp+508h+var_498]
0x1800a8d4c  mov     rax, [rax+30h]
0x1800a8d50  call    cs:__guard_dispatch_icall_fptr
0x1800a8d56  mov     ecx, eax; this
0x1800a8d58  mov     r8, r13; int
0x1800a8d5b  mov     edx, 586h; int
0x1800a8d60  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800a8d65  nop
0x1800a8d66  lea     rcx, [rsp+508h+var_1E8]
0x1800a8d6e  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x1800a8d73  lea     rdx, aCdownloadmanag_9; "CDownloadManager.ProcessTasks.HandleRem"...
0x1800a8d7a  lea     rcx, [rsp+508h+var_1D8]
0x1800a8d82  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800a8d87  lea     rdx, [rsp+508h+Block]
0x1800a8d8f  lea     rcx, [rsp+508h+var_1D0]
0x1800a8d97  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEGBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1800a8d9c  mov     [rsp+508h+Reserved], r12
0x1800a8da1  lea     r9, [rsp+508h+Block]
0x1800a8da9  mov     edx, 1
0x1800a8dae  lea     r8d, [rdx+7]
0x1800a8db2  lea     rcx, [rsp+508h+var_4B0]
0x1800a8db7  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x1800a8dbc  lea     rcx, [rsp+508h+Block]
0x1800a8dc4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800a8dc9  mov     [rsp+508h+Block], rsi
0x1800a8dd1  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x1800a8dd9  movdqu  [rsp+508h+var_A8], xmm0
0x1800a8de2  lea     rcx, [rsp+508h+var_150]
0x1800a8dea  call    ??1?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x1800a8def  nop
0x1800a8df0  lea     rax, ??_7ios_base@std@@6B@; const std::ios_base::`vftable'
0x1800a8df7  mov     [rsp+508h+var_150], rax
0x1800a8dff  lea     rcx, [rsp+508h+var_150]; this
0x1800a8e07  call    ?_Ios_base_dtor@ios_base@std@@CAXPEAV12@@Z; std::ios_base::_Ios_base_dtor(std::ios_base *)
0x1800a8e0c  nop
0x1800a8e0d  mov     rax, [rbx]
0x1800a8e10  lea     rdx, [rsp+508h+var_4B0]
0x1800a8e15  mov     rcx, rbx
0x1800a8e18  mov     rax, [rax+30h]
0x1800a8e1c  call    cs:__guard_dispatch_icall_fptr
0x1800a8e22  nop
0x1800a8e23  mov     rcx, [rsp+508h+var_4B0]
0x1800a8e28  test    rcx, rcx
0x1800a8e2b  jz      short loc_1800A8E40
0x1800a8e2d  mov     [rsp+508h+var_4B0], r12
0x1800a8e32  mov     rax, [rcx]
0x1800a8e35  mov     rax, [rax+8]
0x1800a8e39  call    cs:__guard_dispatch_icall_fptr
0x1800a8e3f  nop
0x1800a8e40  mov     dword ptr [rsp+508h+var_4B0], r12d
0x1800a8e45  mov     rcx, [rsp+508h+var_490]
0x1800a8e4a  mov     rax, [rcx]
0x1800a8e4d  lea     rdx, [rsp+508h+var_4B0]
0x1800a8e52  mov     rax, [rax+50h]
0x1800a8e56  call    cs:__guard_dispatch_icall_fptr
0x1800a8e5c  mov     ecx, eax; this
0x1800a8e5e  mov     r8, r13; int
0x1800a8e61  mov     edx, 58Dh; int
0x1800a8e66  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800a8e6b  mov     eax, r14d
0x1800a8e6e  sub     eax, dword ptr [rsp+508h+var_4B0]
0x1800a8e72  neg     eax
0x1800a8e74  sbb     r8d, r8d
0x1800a8e77  add     r8d, 11h
0x1800a8e7b  mov     qword ptr [rsp+508h+TotalNumberOfFreeBytes], r12
0x1800a8e80  mov     rcx, [rsp+508h+var_490]
0x1800a8e85  mov     rax, [rcx]
0x1800a8e88  lea     r9, [rsp+508h+TotalNumberOfFreeBytes]
0x1800a8e8d  mov     edx, 1
0x1800a8e92  mov     rax, [rax+48h]
0x1800a8e96  call    cs:__guard_dispatch_icall_fptr
0x1800a8e9c  mov     ecx, eax; this
0x1800a8e9e  mov     r8, r13; int
0x1800a8ea1  mov     edx, 598h; int
0x1800a8ea6  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800a8eab  lea     r9, [rsp+508h+var_488]
0x1800a8eb3  mov     r8, qword ptr [rsp+508h+TotalNumberOfFreeBytes]
0x1800a8eb8  lea     rdx, [rsp+508h+var_498]
0x1800a8ebd  call    ??$DoTasks@V_lambda_2_@?BB@??ProcessTasks@CDownloadManager@RepoMan@@UEAAJPEAUIRepoOperation@@PEAX@Z@@?$DownloadManagerBase@$$V@RepoMan@@QEAAXAEAV?$ComPtr@UIRepoFileTasks@@@1@PEAUIRepoFileTasks@@V_lambda_2_@?BB@??ProcessTasks@CDownloadManager@1@UEAAJPEAUIRepoOperation@@PEAX@Z@@Z; RepoMan::DownloadManagerBase<>::DoTasks<`RepoMan::CDownloadManager::ProcessTasks(IRepoOperation *,void *)'::`17'::_lambda_2_>(RepoMan::ComPtr<IRepoFileTasks> &,IRepoFileTasks *,`RepoMan::CDownloadManager::ProcessTasks(IRepoOperation *,void *)'::`17'::_lambda_2_)
0x1800a8ec2  nop
0x1800a8ec3  mov     rcx, qword ptr [rsp+508h+TotalNumberOfFreeBytes]
0x1800a8ec8  test    rcx, rcx
0x1800a8ecb  jz      short loc_1800A8EE0
0x1800a8ecd  mov     qword ptr [rsp+508h+TotalNumberOfFreeBytes], r12
0x1800a8ed2  mov     rax, [rcx]
0x1800a8ed5  mov     rax, [rax+10h]
0x1800a8ed9  call    cs:__guard_dispatch_icall_fptr
0x1800a8edf  nop
0x1800a8ee0  mov     [rsp+508h+var_3B8], r12d
0x1800a8ee8  mov     [rsp+508h+var_3B0], r12
0x1800a8ef0  mov     [rsp+508h+var_3A8], r12
  ... truncated ...
```
