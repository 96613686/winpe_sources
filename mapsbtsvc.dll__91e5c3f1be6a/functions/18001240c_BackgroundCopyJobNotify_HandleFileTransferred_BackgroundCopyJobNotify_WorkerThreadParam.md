# BackgroundCopyJobNotify::HandleFileTransferred(BackgroundCopyJobNotify::WorkerThreadParam *)

- ea: `0x18001240c`
- end: `0x180012893`
- name: `?HandleFileTransferred@BackgroundCopyJobNotify@@CAJPEAUWorkerThreadParam@1@@Z`
- size: `1159`
- prototype: `__int64 __fastcall(struct BackgroundCopyJobNotify::WorkerThreadParam *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800128a0`

## callees

- `0x180001e70`
- `0x1800033d4`
- `0x1800043e4`
- `0x180004680`
- `0x1800047cc`
- `0x180005b9c`
- `0x1800098e4`
- `0x18000b3a4`
- `0x18000c99c`
- `0x18000f308`
- `0x180011130`
- `0x18001240c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012533`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012589`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001262a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800127eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012533`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012589`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001262a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800127eb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800127b0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800127b0`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x1800127e0`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x1800127e0`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18001275f`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18001275f`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800124bc`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18001279c`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800124bc`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18001279c`

## string_xrefs

- `0x1800124a6`: `BackgroundCopyJobNotify::HandleFileTransferred`
- `0x18001274a`: `Processing file | JobType: %d | ThreadParam: %p | RequestId: %ls | Path: %ls`

## pseudocode

```c
__int64 __fastcall BackgroundCopyJobNotify::HandleFileTransferred(
        struct BackgroundCopyJobNotify::WorkerThreadParam *a1)
{
  __int64 v2; // rbx
  int v3; // eax
  int v4; // r8d
  int v5; // ecx
  unsigned int v6; // ebx
  __int64 (__fastcall *v7)(__int64, LPVOID *); // rsi
  __int64 (__fastcall *v8)(__int64, LPCWSTR *); // r14
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, unsigned int *, LPVOID *); // rsi
  void *v11; // rbx
  int v12; // ebx
  _QWORD *v13; // rdx
  unsigned __int16 *v14; // r14
  __int64 v15; // rax
  std::_Ref_count_base *v16; // rsi
  std::_Ref_count_base *v17; // rcx
  std::_Ref_count_base *v18; // rdi
  int v19; // eax
  signed int LastError; // eax
  std::_Ref_count_base *v21; // rdi
  bool v23; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v25; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v26; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v28; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v29; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v30; // [rsp+78h] [rbp-88h] BYREF
  __int64 v31; // [rsp+80h] [rbp-80h] BYREF
  __int64 v32; // [rsp+88h] [rbp-78h] BYREF
  __int64 v33; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v34; // [rsp+98h] [rbp-68h] BYREF
  __int64 v35; // [rsp+A0h] [rbp-60h] BYREF
  std::_Ref_count_base *v36[2]; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v37[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v38; // [rsp+C8h] [rbp-38h]
  _QWORD v39[7]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v40; // [rsp+108h] [rbp+8h]

  *(_OWORD *)v37 = 0;
  v38 = 0;
  v30 = 0;
  v2 = *((_QWORD *)a1 + 1);
  v35 = v2;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  v33 = 0;
  v32 = 0;
  v31 = 0;
  v34 = 0;
  *(_OWORD *)v36 = 0;
  pv = 0;
  lpFileName = 0;
  v26 = 0;
  v25 = 0;
  v23 = 0;
  v3 = ATL::CComPtrBase<IBackgroundCopyFile>::QueryInterface<IBackgroundCopyFile2>(&v35, &v33);
  if ( v3 < 0 )
  {
    v4 = 230;
LABEL_5:
    v5 = v3;
LABEL_6:
    v6 = ZTraceReportPropagationNoThis(v5, "BackgroundCopyJobNotify::HandleFileTransferred", v4);
LABEL_34:
    if ( !DeleteFileW(lpFileName) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2143748092;
      }
      ZTraceReportIgnoreNoThis(LastError, "BackgroundCopyJobNotify::HandleFileTransferred", 280);
    }
    goto LABEL_40;
  }
  v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v2)(
         v2,
         &GUID_659cdeaa_489e_11d9_a9cd_000d56965251,
         &v32);
  if ( v3 < 0 )
  {
    v4 = 231;
    goto LABEL_5;
  }
  v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v2)(
         v2,
         &GUID_85c1657f_dafc_40e8_8834_df18ea25717e,
         &v31);
  if ( v3 < 0 )
  {
    v4 = 232;
    goto LABEL_5;
  }
  v7 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v2 + 24LL);
  pv = 0;
  v3 = v7(v2, &pv);
  if ( v3 < 0 )
  {
    v4 = 234;
    goto LABEL_5;
  }
  v8 = *(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v32 + 64LL);
  lpFileName = 0;
  v3 = v8(v32, &lpFileName);
  if ( v3 < 0 )
  {
    v4 = 236;
    goto LABEL_5;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v2 + 40LL))(v2, v37);
  if ( v3 < 0 )
  {
    v4 = 238;
    goto LABEL_5;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 **))(*(_QWORD *)v31 + 112LL))(v31, 1, &v30);
  if ( v3 < 0 )
  {
    v4 = 240;
    goto LABEL_5;
  }
  v9 = v33;
  v10 = *(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *))(*(_QWORD *)v33 + 48LL);
  v11 = v26;
  if ( v26 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v28);
    CoTaskMemFree(v11);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v28);
  }
  v26 = 0;
  v3 = v10(v9, &v25, &v26);
  if ( v3 < 0 )
  {
    v4 = 242;
    goto LABEL_5;
  }
  v28 = 0;
  v39[0] = off_1800163D8;
  v39[1] = v26;
  v40 = v39;
  v12 = MapsBackgroundTransferJob::GenerateRequestId(pv, v25, v39, &v28);
  if ( v40 )
  {
    v13 = v39;
    LOBYTE(v13) = v40 != v39;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v40 + 32LL))(v40, v13);
  }
  if ( v12 < 0 )
  {
    v4 = 255;
    v5 = v12;
    goto LABEL_6;
  }
  v6 = 0;
  v14 = v28;
  v34 = v28;
  v15 = std::weak_ptr<MapsBackgroundTransferJob>::lock((char *)a1 + 24, &v28);
  v16 = *(std::_Ref_count_base **)v15;
  v17 = *(std::_Ref_count_base **)(v15 + 8);
  *(_QWORD *)v15 = 0;
  *(_QWORD *)(v15 + 8) = 0;
  v36[0] = v16;
  v36[1] = v17;
  v18 = v29;
  if ( v29 && _InterlockedExchangeAdd((volatile signed __int32 *)v29 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(std::_Ref_count_base *))v18)(v18);
    std::_Ref_count_base::_Decwref(v18);
  }
  if ( !v16 )
    goto LABEL_34;
  ZTraceHelperNoThis(
    5,
    "BackgroundCopyJobNotify::HandleFileTransferred",
    261,
    "Processing file | JobType: %d | ThreadParam: %p | RequestId: %ls | Path: %ls",
    *((_DWORD *)v16 + 10),
    a1,
    v14,
    lpFileName);
  v19 = MapsBackgroundTransferJob::SingleRequestFinished(v16, v14, lpFileName, v37[0], v30, &v23);
  if ( v19 < 0 )
    v6 = ZTraceReportPropagationNoThis(v19, "BackgroundCopyJobNotify::HandleFileTransferred", 268);
  if ( !v23 )
    goto LABEL_34;
LABEL_40:
  CoTaskMemFree(v30);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpFileName);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
  v21 = v36[1];
  if ( v36[1] && _InterlockedExchangeAdd((volatile signed __int32 *)v36[1] + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(std::_Ref_count_base *))v21)(v21);
    std::_Ref_count_base::_Decwref(v21);
  }
  std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v34);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
  return v6;
}

```

## disassembly

```asm
0x18001240c  push    rbp
0x18001240e  push    rbx
0x18001240f  push    rsi
0x180012410  push    rdi
0x180012411  push    r12
0x180012413  push    r13
0x180012415  push    r14
0x180012417  push    r15
0x180012419  lea     rbp, [rsp-28h]
0x18001241e  sub     rsp, 128h
0x180012425  mov     rax, cs:__security_cookie
0x18001242c  xor     rax, rsp
0x18001242f  mov     [rbp+60h+var_50], rax
0x180012433  mov     r15, rcx
0x180012436  xorps   xmm0, xmm0
0x180012439  xor     eax, eax
0x18001243b  movups  xmmword ptr [rbp+60h+var_A8], xmm0
0x18001243f  mov     [rbp+60h+var_98], rax
0x180012443  xor     r12d, r12d
0x180012446  mov     [rsp+160h+var_E8], r12
0x18001244b  mov     rbx, [rcx+8]
0x18001244f  mov     [rbp+60h+var_C0], rbx
0x180012453  test    rbx, rbx
0x180012456  jz      short loc_180012468
0x180012458  mov     rax, [rbx]
0x18001245b  mov     rcx, rbx
0x18001245e  mov     rax, [rax+8]
0x180012462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012467  nop
0x180012468  mov     [rbp+60h+var_D0], r12
0x18001246c  mov     [rbp+60h+var_D8], r12
0x180012470  mov     [rbp+60h+var_E0], r12
0x180012474  mov     [rbp+60h+var_C8], r12
0x180012478  xorps   xmm0, xmm0
0x18001247b  movdqu  xmmword ptr [rbp+60h+var_B8], xmm0
0x180012480  mov     [rsp+160h+pv], r12
0x180012485  mov     [rsp+160h+lpFileName], r12
0x18001248a  mov     [rsp+160h+var_108], r12
0x18001248f  mov     [rsp+160h+var_110], r12d
0x180012494  mov     [rsp+160h+var_120], r12b
0x180012499  lea     rdx, [rbp+60h+var_D0]
0x18001249d  lea     rcx, [rbp+60h+var_C0]
0x1800124a1  call    ??$QueryInterface@UIBackgroundCopyFile2@@@?$CComPtrBase@UIBackgroundCopyFile@@@ATL@@QEBAJPEAPEAUIBackgroundCopyFile2@@@Z; ATL::CComPtrBase<IBackgroundCopyFile>::QueryInterface<IBackgroundCopyFile2>(IBackgroundCopyFile2 * *)
0x1800124a6  lea     r13, aBackgroundcopy; "BackgroundCopyJobNotify::HandleFileTran"...
0x1800124ad  test    eax, eax
0x1800124af  jns     short loc_1800124C9
0x1800124b1  mov     r8d, 0E6h
0x1800124b7  mov     ecx, eax
0x1800124b9  mov     rdx, r13
0x1800124bc  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800124c2  mov     ebx, eax
0x1800124c4  jmp     loc_1800127AB
0x1800124c9  mov     rax, [rbx]
0x1800124cc  lea     r8, [rbp+60h+var_D8]
0x1800124d0  lea     rdx, _GUID_659cdeaa_489e_11d9_a9cd_000d56965251
0x1800124d7  mov     rcx, rbx
0x1800124da  mov     rax, [rax]
0x1800124dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124e2  nop
0x1800124e3  test    eax, eax
0x1800124e5  jns     short loc_1800124EF
0x1800124e7  mov     r8d, 0E7h
0x1800124ed  jmp     short loc_1800124B7
0x1800124ef  mov     rax, [rbx]
0x1800124f2  lea     r8, [rbp+60h+var_E0]
0x1800124f6  lea     rdx, _GUID_85c1657f_dafc_40e8_8834_df18ea25717e
0x1800124fd  mov     rcx, rbx
0x180012500  mov     rax, [rax]
0x180012503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012508  nop
0x180012509  test    eax, eax
0x18001250b  jns     short loc_180012515
0x18001250d  mov     r8d, 0E8h
0x180012513  jmp     short loc_1800124B7
0x180012515  mov     rax, [rbx]
0x180012518  mov     rsi, [rax+18h]
0x18001251c  mov     rdi, [rsp+160h+pv]
0x180012521  test    rdi, rdi
0x180012524  jz      short loc_180012543
0x180012526  lea     rcx, [rsp+160h+var_F8]; this
0x18001252b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180012530  mov     rcx, rdi; pv
0x180012533  call    cs:__imp_CoTaskMemFree
0x180012539  lea     rcx, [rsp+160h+var_F8]; this
0x18001253e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180012543  mov     [rsp+160h+pv], r12
0x180012548  lea     rdx, [rsp+160h+pv]
0x18001254d  mov     rcx, rbx
0x180012550  mov     rax, rsi
0x180012553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012558  test    eax, eax
0x18001255a  jns     short loc_180012567
0x18001255c  mov     r8d, 0EAh
0x180012562  jmp     loc_1800124B7
0x180012567  mov     rsi, [rbp+60h+var_D8]
0x18001256b  mov     rax, [rsi]
0x18001256e  mov     r14, [rax+40h]
0x180012572  mov     rdi, [rsp+160h+lpFileName]
0x180012577  test    rdi, rdi
0x18001257a  jz      short loc_180012599
0x18001257c  lea     rcx, [rsp+160h+var_F8]; this
0x180012581  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180012586  mov     rcx, rdi; pv
0x180012589  call    cs:__imp_CoTaskMemFree
0x18001258f  lea     rcx, [rsp+160h+var_F8]; this
0x180012594  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180012599  mov     [rsp+160h+lpFileName], r12
0x18001259e  lea     rdx, [rsp+160h+lpFileName]
0x1800125a3  mov     rcx, rsi
0x1800125a6  mov     rax, r14
0x1800125a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125ae  test    eax, eax
0x1800125b0  jns     short loc_1800125BD
0x1800125b2  mov     r8d, 0ECh
0x1800125b8  jmp     loc_1800124B7
0x1800125bd  mov     rax, [rbx]
0x1800125c0  lea     rdx, [rbp+60h+var_A8]
0x1800125c4  mov     rcx, rbx
0x1800125c7  mov     rax, [rax+28h]
0x1800125cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125d0  test    eax, eax
0x1800125d2  jns     short loc_1800125DF
0x1800125d4  mov     r8d, 0EEh
0x1800125da  jmp     loc_1800124B7
0x1800125df  mov     rcx, [rbp+60h+var_E0]
0x1800125e3  mov     rax, [rcx]
0x1800125e6  lea     r8, [rsp+160h+var_E8]
0x1800125eb  mov     edx, 1
0x1800125f0  mov     rax, [rax+70h]
0x1800125f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125f9  test    eax, eax
0x1800125fb  jns     short loc_180012608
0x1800125fd  mov     r8d, 0F0h
0x180012603  jmp     loc_1800124B7
0x180012608  mov     rdi, [rbp+60h+var_D0]
0x18001260c  mov     rax, [rdi]
0x18001260f  mov     rsi, [rax+30h]
0x180012613  mov     rbx, [rsp+160h+var_108]
0x180012618  test    rbx, rbx
0x18001261b  jz      short loc_18001263A
0x18001261d  lea     rcx, [rsp+160h+var_F8]; this
0x180012622  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180012627  mov     rcx, rbx; pv
0x18001262a  call    cs:__imp_CoTaskMemFree
0x180012630  lea     rcx, [rsp+160h+var_F8]; this
0x180012635  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001263a  mov     [rsp+160h+var_108], r12
0x18001263f  lea     r8, [rsp+160h+var_108]
0x180012644  lea     rdx, [rsp+160h+var_110]
0x180012649  mov     rcx, rdi
0x18001264c  mov     rax, rsi
0x18001264f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012654  test    eax, eax
0x180012656  jns     short loc_180012663
0x180012658  mov     r8d, 0F2h
0x18001265e  jmp     loc_1800124B7
0x180012663  mov     [rsp+160h+var_F8], r12
0x180012668  mov     rax, [rsp+160h+var_108]
0x18001266d  lea     rcx, off_1800163D8
0x180012674  mov     [rbp+60h+var_90], rcx
0x180012678  mov     [rbp+60h+var_88], rax
0x18001267c  lea     rax, [rbp+60h+var_90]
0x180012680  mov     [rbp+60h+var_58], rax
0x180012684  lea     r9, [rsp+160h+var_F8]
0x180012689  lea     r8, [rbp+60h+var_90]
0x18001268d  mov     edx, [rsp+160h+var_110]
0x180012691  mov     rcx, [rsp+160h+pv]
0x180012696  call    ?GenerateRequestId@MapsBackgroundTransferJob@@CAJPEBGKAEBV?$function@$$A6AJKPEA_K0@Z@std@@PEAPEAG@Z; MapsBackgroundTransferJob::GenerateRequestId(ushort const *,ulong,std::function<long (ulong,unsigned __int64 *,unsigned __int64 *)> const &,ushort * *)
0x18001269b  mov     ebx, eax
0x18001269d  mov     rcx, [rbp+60h+var_58]
0x1800126a1  test    rcx, rcx
0x1800126a4  jz      short loc_1800126BC
0x1800126a6  mov     rax, [rcx]
0x1800126a9  lea     rdx, [rbp+60h+var_90]
0x1800126ad  cmp     rcx, rdx
0x1800126b0  setnz   dl
0x1800126b3  mov     rax, [rax+20h]
0x1800126b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126bc  test    ebx, ebx
0x1800126be  jns     short loc_1800126CD
0x1800126c0  mov     r8d, 0FFh
0x1800126c6  mov     ecx, ebx
0x1800126c8  jmp     loc_1800124B9
0x1800126cd  mov     ebx, r12d
0x1800126d0  mov     r14, [rsp+160h+var_F8]
0x1800126d5  mov     [rbp+60h+var_C8], r14
0x1800126d9  lea     rcx, [r15+18h]
0x1800126dd  lea     rdx, [rsp+160h+var_F8]
0x1800126e2  call    ?lock@?$weak_ptr@VMapsBackgroundTransferJob@@@std@@QEBA?AV?$shared_ptr@VMapsBackgroundTransferJob@@@2@XZ; std::weak_ptr<MapsBackgroundTransferJob>::lock(void)
0x1800126e7  mov     rsi, [rax]
0x1800126ea  mov     rcx, [rax+8]
0x1800126ee  mov     [rax], r12
0x1800126f1  mov     [rax+8], r12
0x1800126f5  mov     [rbp+60h+var_B8], rsi
0x1800126f9  mov     [rbp+60h+var_B8+8], rcx
0x1800126fd  mov     rdi, [rsp+160h+var_F0]
0x180012702  test    rdi, rdi
0x180012705  jz      short loc_18001272A
0x180012707  or      eax, 0FFFFFFFFh
0x18001270a  lock xadd [rdi+8], eax
0x18001270f  cmp     eax, 1
0x180012712  jnz     short loc_18001272A
0x180012714  mov     rax, [rdi]
0x180012717  mov     rcx, rdi
0x18001271a  mov     rax, [rax]
0x18001271d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012722  mov     rcx, rdi; this
0x180012725  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18001272a  test    rsi, rsi
0x18001272d  jz      short loc_1800127AB
0x18001272f  mov     rax, [rsp+160h+lpFileName]
0x180012734  mov     [rsp+160h+var_128], rax
0x180012739  mov     [rsp+160h+var_130], r14
0x18001273e  mov     [rsp+160h+var_138], r15
0x180012743  mov     eax, [rsi+28h]
0x180012746  mov     dword ptr [rsp+160h+var_140], eax
0x18001274a  lea     r9, aProcessingFile; "Processing file | JobType: %d | ThreadP"...
0x180012751  mov     r8d, 105h
0x180012757  mov     rdx, r13
0x18001275a  mov     ecx, 5
0x18001275f  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180012765  mov     rax, [rsp+160h+var_E8]
0x18001276a  lea     rcx, [rsp+160h+var_120]
0x18001276f  mov     [rsp+160h+var_138], rcx; bool *
0x180012774  mov     [rsp+160h+var_140], rax; unsigned __int16 *
0x180012779  mov     r9, [rbp+60h+var_A8]; unsigned __int64
0x18001277d  mov     r8, [rsp+160h+lpFileName]; unsigned __int16 *
0x180012782  mov     rdx, r14; unsigned __int16 *
0x180012785  mov     rcx, rsi; this
0x180012788  call    ?SingleRequestFinished@MapsBackgroundTransferJob@@AEAAJPEBG0_KPEAGPEA_N@Z; MapsBackgroundTransferJob::SingleRequestFinished(ushort const *,ushort const *,unsigned __int64,ushort *,bool *)
0x18001278d  test    eax, eax
0x18001278f  jns     short loc_1800127A4
0x180012791  mov     r8d, 10Ch
0x180012797  mov     rdx, r13
0x18001279a  mov     ecx, eax
0x18001279c  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800127a2  mov     ebx, eax
0x1800127a4  cmp     [rsp+160h+var_120], r12b
0x1800127a9  jnz     short loc_1800127E6
0x1800127ab  mov     rcx, [rsp+160h+lpFileName]; lpFileName
0x1800127b0  call    cs:__imp_DeleteFileW
0x1800127b6  test    eax, eax
0x1800127b8  jnz     short loc_1800127E6
0x1800127ba  call    cs:__imp_GetLastError
0x1800127c0  test    eax, eax
0x1800127c2  jz      short loc_1800127D0
0x1800127c4  jle     short loc_1800127D5
0x1800127c6  movzx   eax, ax
0x1800127c9  or      eax, 80070000h
0x1800127ce  jmp     short loc_1800127D5
0x1800127d0  mov     eax, 80390004h
0x1800127d5  mov     r8d, 118h
0x1800127db  mov     rdx, r13
0x1800127de  mov     ecx, eax
0x1800127e0  call    cs:__imp_?ZTraceReportIgnoreNoThis@@YAXHPEBDH@Z; ZTraceReportIgnoreNoThis(int,char const *,int)
0x1800127e6  mov     rcx, [rsp+160h+var_E8]; pv
0x1800127eb  call    cs:__imp_CoTaskMemFree
0x1800127f1  nop
0x1800127f2  lea     rcx, [rsp+160h+var_108]
0x1800127f7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800127fc  nop
0x1800127fd  lea     rcx, [rsp+160h+lpFileName]
0x180012802  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012807  nop
0x180012808  lea     rcx, [rsp+160h+pv]
0x18001280d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012812  nop
0x180012813  mov     rdi, [rbp+60h+var_B8+8]
0x180012817  test    rdi, rdi
0x18001281a  jz      short loc_180012840
0x18001281c  or      eax, 0FFFFFFFFh
0x18001281f  lock xadd [rdi+8], eax
0x180012824  cmp     eax, 1
0x180012827  jnz     short loc_180012840
0x180012829  mov     rax, [rdi]
0x18001282c  mov     rcx, rdi
0x18001282f  mov     rax, [rax]
0x180012832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012837  mov     rcx, rdi; this
0x18001283a  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18001283f  nop
0x180012840  lea     rcx, [rbp+60h+var_C8]
0x180012844  call    ??1?$unique_ptr@$$BY0A@U_BG_FILE_RANGE@@U?$default_delete@$$BY0A@U_BG_FILE_RANGE@@@std@@@std@@QEAA@XZ; std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(void)
0x180012849  nop
0x18001284a  lea     rcx, [rbp+60h+var_E0]
0x18001284e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180012853  nop
0x180012854  lea     rcx, [rbp+60h+var_D8]
0x180012858  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001285d  nop
0x18001285e  lea     rcx, [rbp+60h+var_D0]
0x180012862  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180012867  nop
0x180012868  lea     rcx, [rbp+60h+var_C0]
0x18001286c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180012871  mov     eax, ebx
0x180012873  mov     rcx, [rbp+60h+var_50]
0x180012877  xor     rcx, rsp; StackCookie
0x18001287a  call    __security_check_cookie
0x18001287f  add     rsp, 128h
  ... truncated ...
```
