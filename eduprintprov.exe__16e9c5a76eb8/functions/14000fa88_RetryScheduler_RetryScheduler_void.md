# RetryScheduler::RetryScheduler(void)

- ea: `0x14000fa88`
- end: `0x140010090`
- name: `??0RetryScheduler@@QEAA@XZ`
- size: `1544`
- prototype: `RetryScheduler *__fastcall(RetryScheduler *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000d2a4`

## callees

- `0x140002630`
- `0x14000315c`
- `0x140003168`
- `0x14000452c`
- `0x14000466c`
- `0x140004e30`
- `0x14000b8ac`
- `0x14000b8f4`
- `0x14000b940`
- `0x14000cc6c`
- `0x14000fa88`
- `0x140010098`
- `0x14001011c`
- `0x1400101bc`
- `0x140010300`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fb34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fb34`
- `OLEAUT32!__imp_VariantInit` at `0x14000fdcd`
- `OLEAUT32!__imp_VariantInit` at `0x14000fde5`
- `OLEAUT32!__imp_VariantInit` at `0x14000fdfe`
- `OLEAUT32!__imp_VariantInit` at `0x14000fe15`
- `OLEAUT32!__imp_VariantInit` at `0x14000fdcd`
- `OLEAUT32!__imp_VariantInit` at `0x14000fde5`
- `OLEAUT32!__imp_VariantInit` at `0x14000fdfe`
- `OLEAUT32!__imp_VariantInit` at `0x14000fe15`
- `OLEAUT32!__imp_VariantClear` at `0x14000fe83`
- `OLEAUT32!__imp_VariantClear` at `0x14000fe8f`
- `OLEAUT32!__imp_VariantClear` at `0x14000fe9b`
- `OLEAUT32!__imp_VariantClear` at `0x14000fea7`
- `OLEAUT32!__imp_VariantClear` at `0x14000fe83`
- `OLEAUT32!__imp_VariantClear` at `0x14000fe8f`
- `OLEAUT32!__imp_VariantClear` at `0x14000fe9b`
- `OLEAUT32!__imp_VariantClear` at `0x14000fea7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000fda8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000fda8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000fd58`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000fd58`
- `SspiCli!GetUserNameExW` at `0x14000fb23`
- `SspiCli!GetUserNameExW` at `0x14000fbfd`
- `SspiCli!GetUserNameExW` at `0x14000fb23`
- `SspiCli!GetUserNameExW` at `0x14000fbfd`

## pseudocode

```c
RetryScheduler *__fastcall RetryScheduler::RetryScheduler(RetryScheduler *this)
{
  char *v2; // rdi
  _QWORD *v3; // rsi
  LPVOID *v4; // r13
  __int64 *v5; // r12
  const char *v6; // r9
  size_t v7; // r14
  _QWORD *v8; // rax
  void *v9; // rax
  void *v10; // rcx
  LONGLONG v11; // rbx
  __int64 v12; // r8
  const char *v13; // r9
  const void *v14; // r9
  unsigned __int64 v15; // rdx
  char *v16; // r14
  __int64 v17; // rbx
  _QWORD *v18; // rax
  __int64 v19; // r8
  _QWORD *v20; // rdi
  bool v21; // cc
  _QWORD *v22; // rcx
  _WORD *v23; // rax
  _WORD *v24; // rcx
  _WORD *v25; // rbx
  unsigned __int64 v26; // rdx
  const void *v27; // r9
  __int64 v28; // rcx
  __int64 v29; // r14
  _WORD *v30; // rbx
  HRESULT v31; // eax
  LPVOID v32; // rcx
  HRESULT Instance; // eax
  LPVOID v34; // rdi
  __int64 (__fastcall *v35)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v36; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v38; // xmm8
  IRecordInfo *v39; // xmm9_8
  __int128 v40; // xmm6
  IRecordInfo *v41; // xmm7_8
  int v42; // eax
  LPVOID v43; // rdi
  __int64 (__fastcall *v44)(LPVOID, __int64, char *); // r14
  __int64 v45; // rcx
  _bstr_t *v46; // rax
  __int64 v47; // rdx
  int v48; // eax
  __int64 v49; // rbx
  __int64 (__fastcall *v50)(__int64, __int64, __int64 *); // rdi
  __int64 v51; // rcx
  _bstr_t *v52; // rax
  __int64 v53; // rdx
  int v54; // ebx
  __int64 v55; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  VARIANTARG lpNameBuffer; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG v60; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v61; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG v63; // [rsp+90h] [rbp-70h] BYREF
  int v64[4]; // [rsp+B0h] [rbp-50h] BYREF
  IRecordInfo *v65; // [rsp+C0h] [rbp-40h]
  __int128 v66; // [rsp+D0h] [rbp-30h] BYREF
  IRecordInfo *v67; // [rsp+E0h] [rbp-20h]
  __int128 v68; // [rsp+F0h] [rbp-10h] BYREF
  IRecordInfo *v69; // [rsp+100h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]
  _QWORD *nSize; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v72; // [rsp+1C0h] [rbp+C0h] BYREF

  *(_BYTE *)this = 0;
  v2 = (char *)this + 8;
  *(_OWORD *)((char *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 7;
  *((_WORD *)this + 4) = 0;
  v3 = (_QWORD *)((char *)this + 40);
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 7;
  *((_WORD *)this + 20) = 0;
  v4 = (LPVOID *)((char *)this + 72);
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  v5 = (__int64 *)((char *)this + 88);
  *((_QWORD *)this + 11) = 0;
  LODWORD(nSize) = 0;
  if ( !GetUserNameExW(NameSamCompatible, 0, (PULONG)&nSize) && GetLastError() != 234 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
      v6);
  memset(&lpNameBuffer, 0, sizeof(lpNameBuffer));
  if ( (_DWORD)nSize )
  {
    v7 = 2LL * (unsigned int)nSize;
    if ( v7 )
    {
      if ( v7 < 0x1000 )
      {
        v8 = operator new(v7);
      }
      else
      {
        if ( v7 + 39 < v7 )
          __scrt_throw_std_bad_array_new_length();
        v9 = operator new(v7 + 39);
        v10 = v9;
        if ( !v9 )
          __fastfail(5u);
        v8 = (_QWORD *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v8 - 1) = v10;
      }
    }
    else
    {
      v8 = 0;
    }
    *(_QWORD *)&lpNameBuffer.vt = v8;
    v11 = (LONGLONG)v8 + v7;
    lpNameBuffer.pRecInfo = (IRecordInfo *)((char *)v8 + v7);
    memset_0(v8, 0, v7);
    lpNameBuffer.llVal = v11;
    v72 = 0;
    std::_Tidy_guard<std::vector<unsigned short>>::~_Tidy_guard<std::vector<unsigned short>>(&v72);
  }
  if ( !GetUserNameExW(NameSamCompatible, *(LPWSTR *)&lpNameBuffer.vt, (PULONG)&nSize) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
      v13);
  v14 = *(const void **)&lpNameBuffer.vt;
  v15 = (lpNameBuffer.llVal - *(_QWORD *)&lpNameBuffer.vt) >> 1;
  if ( v15 > *((_QWORD *)v2 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      v2,
      v15,
      v12,
      *(_QWORD *)&lpNameBuffer.vt);
  }
  else
  {
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v16 = v2;
    else
      v16 = *(char **)v2;
    *((_QWORD *)v2 + 2) = v15;
    v17 = 2 * v15;
    memmove_0(v16, v14, 2 * v15);
    *(_WORD *)&v16[v17] = 0;
  }
  std::vector<unsigned short>::~vector<unsigned short>(&lpNameBuffer);
  v18 = (_QWORD *)std::wstring::wstring(&v63, v2);
  v20 = v18;
  nSize = v18;
  v21 = v18[3] <= 7u;
  if ( v18[3] <= 7u )
    v22 = v18;
  else
    v22 = (_QWORD *)*v18;
  v23 = (_WORD *)v22 + v18[2];
  if ( v21 )
    v24 = v20;
  else
    v24 = (_WORD *)*v20;
  while ( v24 != v23 )
  {
    if ( *v24 == 92 )
      *v24 = 95;
    ++v24;
  }
  if ( v3[3] < 0x12u )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      v3,
      18,
      v19,
      L"EduPrintProvRetry_");
  }
  else
  {
    v25 = (_WORD *)*v3;
    v3[2] = 18;
    memmove_0(v25, L"EduPrintProvRetry_", 0x24u);
    v25[18] = 0;
  }
  v26 = v20[2];
  if ( v20[3] <= 7u )
    v27 = v20;
  else
    v27 = (const void *)*v20;
  v28 = v3[2];
  if ( v26 > v3[3] - v28 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
      v3,
      v20[2]);
  }
  else
  {
    v29 = v28 + v26;
    v3[2] = v28 + v26;
    if ( v3[3] <= 7u )
      v30 = v3;
    else
      v30 = (_WORD *)*v3;
    memmove_0(&v30[v28], v27, 2 * v26);
    v30[v29] = 0;
  }
  std::wstring::~wstring(v20);
  v31 = CoInitializeEx(0, 0);
  if ( v31 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
      (const char *)(unsigned int)v31,
      ppv);
  *(_BYTE *)this = 1;
  v32 = *v4;
  *v4 = 0;
  if ( v32 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, v4);
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  v34 = *v4;
  v35 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)*v4 + 80LL);
  VariantInit(&pvarg);
  v36 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v61);
  v38 = *(_OWORD *)&v61.vt;
  v39 = v61.pRecInfo;
  VariantInit(&v60);
  v40 = *(_OWORD *)&v60.vt;
  v41 = v60.pRecInfo;
  VariantInit(&lpNameBuffer);
  *(_OWORD *)v64 = v36;
  v65 = pRecInfo;
  v66 = v38;
  v67 = v39;
  v68 = v40;
  v69 = v41;
  v63 = lpNameBuffer;
  v42 = v35(v34, &v63, &v68, &v66);
  if ( v42 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
      (const char *)(unsigned int)v42,
      (int)v64);
  VariantClear(&lpNameBuffer);
  VariantClear(&v60);
  VariantClear(&v61);
  VariantClear(&pvarg);
  v43 = *v4;
  v44 = *(__int64 (__fastcall **)(LPVOID, __int64, char *))(*(_QWORD *)*v4 + 56LL);
  v45 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  v46 = _bstr_t::_bstr_t((_bstr_t *)&nSize, L"\\");
  if ( *(_QWORD *)v46 )
    v47 = **(_QWORD **)v46;
  else
    v47 = 0;
  v48 = v44(v43, v47, (char *)this + 80);
  if ( v48 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
      (const char *)(unsigned int)v48,
      (int)v64);
  _bstr_t::~_bstr_t((_bstr_t *)&nSize);
  v49 = *((_QWORD *)this + 10);
  v50 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v49 + 104LL);
  v51 = *v5;
  *v5 = 0;
  if ( v51 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  if ( v3[3] > 7u )
    v3 = (_QWORD *)*v3;
  v52 = _bstr_t::_bstr_t((_bstr_t *)&nSize, (const unsigned __int16 *)v3);
  if ( *(_QWORD *)v52 )
    v53 = **(_QWORD **)v52;
  else
    v53 = 0;
  v54 = v50(v49, v53, v5);
  _bstr_t::~_bstr_t((_bstr_t *)&nSize);
  if ( v54 < 0 )
  {
    if ( v54 != -2147024894 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x3D,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v54,
        (int)v64);
    v55 = *v5;
    *v5 = 0;
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  }
  return this;
}

```

## disassembly

```asm
0x14000fa88  mov     rax, rsp
0x14000fa8b  mov     [rax+20h], rbx
0x14000fa8f  mov     [rax+8], rcx
0x14000fa93  push    rbp
0x14000fa94  push    rsi
0x14000fa95  push    rdi
0x14000fa96  push    r12
0x14000fa98  push    r13
0x14000fa9a  push    r14
0x14000fa9c  push    r15
0x14000fa9e  lea     rbp, [rsp-70h]
0x14000faa3  sub     rsp, 170h
0x14000faaa  movaps  xmmword ptr [rax-48h], xmm6
0x14000faae  movaps  xmmword ptr [rax-58h], xmm7
0x14000fab2  movaps  xmmword ptr [rax-68h], xmm8
0x14000fab7  movaps  xmmword ptr [rax-78h], xmm9
0x14000fabc  movaps  xmmword ptr [rax-88h], xmm10
0x14000fac4  movaps  xmmword ptr [rax-98h], xmm11
0x14000facc  mov     r15, rcx
0x14000facf  xor     ebx, ebx
0x14000fad1  mov     [rcx], bl
0x14000fad3  lea     rdi, [rcx+8]
0x14000fad7  xorps   xmm0, xmm0
0x14000fada  movups  xmmword ptr [rdi], xmm0
0x14000fadd  mov     [rdi+10h], rbx
0x14000fae1  lea     ecx, [rbx+7]
0x14000fae4  mov     [rdi+18h], rcx
0x14000fae8  mov     [rdi], bx
0x14000faeb  lea     rsi, [r15+28h]
0x14000faef  movups  xmmword ptr [rsi], xmm0
0x14000faf2  mov     [rsi+10h], rbx
0x14000faf6  mov     [rsi+18h], rcx
0x14000fafa  mov     [rsi], bx
0x14000fafd  lea     r13, [r15+48h]
0x14000fb01  mov     [r13+0], rbx
0x14000fb05  mov     [r15+50h], rbx
0x14000fb09  lea     r12, [r15+58h]
0x14000fb0d  mov     [r12], rbx
0x14000fb11  mov     dword ptr [rbp+0A0h+nSize], ebx
0x14000fb17  lea     r8, [rbp+0A0h+nSize]; nSize
0x14000fb1e  xor     edx, edx; lpNameBuffer
0x14000fb20  lea     ecx, [rbx+2]; NameFormat
0x14000fb23  call    cs:__imp_GetUserNameExW
0x14000fb29  test    al, al
0x14000fb2b  jnz     short loc_14000FB47
0x14000fb2d  mov     rbx, [rbp+0A8h]
0x14000fb34  call    cs:__imp_GetLastError
0x14000fb3a  cmp     eax, 0EAh
0x14000fb3f  jnz     loc_14001000C
0x14000fb45  xor     ebx, ebx
0x14000fb47  mov     r14d, dword ptr [rbp+0A0h+nSize]
0x14000fb4e  xorps   xmm0, xmm0
0x14000fb51  movdqu  xmmword ptr [rsp+1A0h+lpNameBuffer], xmm0
0x14000fb57  mov     [rsp+1A0h+var_160], rbx
0x14000fb5c  test    r14, r14
0x14000fb5f  jz      loc_14000FBE5
0x14000fb65  add     r14, r14
0x14000fb68  jnz     short loc_14000FB6F
0x14000fb6a  mov     rax, rbx
0x14000fb6d  jmp     short loc_14000FBAD
0x14000fb6f  cmp     r14, 1000h
0x14000fb76  jb      short loc_14000FBA5
0x14000fb78  lea     rcx, [r14+27h]; Size
0x14000fb7c  cmp     rcx, r14
0x14000fb7f  jbe     loc_140010021
0x14000fb85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000fb8a  mov     rcx, rax
0x14000fb8d  test    rax, rax
0x14000fb90  jnz     short loc_14000FB97
0x14000fb92  lea     ecx, [rax+5]
0x14000fb95  int     29h; Win8: RtlFailFast(ecx)
0x14000fb97  add     rax, 27h ; '''
0x14000fb9b  and     rax, 0FFFFFFFFFFFFFFE0h
0x14000fb9f  mov     [rax-8], rcx
0x14000fba3  jmp     short loc_14000FBAD
0x14000fba5  mov     rcx, r14; Size
0x14000fba8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000fbad  mov     [rsp+1A0h+lpNameBuffer], rax
0x14000fbb2  lea     rbx, [r14+rax]
0x14000fbb6  mov     [rsp+1A0h+var_160], rbx
0x14000fbbb  mov     r8, r14; Size
0x14000fbbe  xor     edx, edx; Val
0x14000fbc0  mov     rcx, rax; void *
0x14000fbc3  call    memset_0
0x14000fbc8  mov     [rsp+1A0h+lpNameBuffer+8], rbx
0x14000fbcd  mov     [rbp+0A0h+arg_10], 0
0x14000fbd8  lea     rcx, [rbp+0A0h+arg_10]
0x14000fbdf  call    ??1?$_Tidy_guard@V?$vector@GV?$allocator@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<ushort>>::~_Tidy_guard<std::vector<ushort>>(void)
0x14000fbe4  nop
0x14000fbe5  mov     rbx, [rbp+0A8h]
0x14000fbec  lea     r8, [rbp+0A0h+nSize]; nSize
0x14000fbf3  mov     rdx, [rsp+1A0h+lpNameBuffer]; lpNameBuffer
0x14000fbf8  mov     ecx, 2; NameFormat
0x14000fbfd  call    cs:__imp_GetUserNameExW
0x14000fc03  test    al, al
0x14000fc05  jz      loc_140010027
0x14000fc0b  mov     rdx, [rsp+1A0h+lpNameBuffer+8]
0x14000fc10  mov     r9, [rsp+1A0h+lpNameBuffer]
0x14000fc15  sub     rdx, r9
0x14000fc18  sar     rdx, 1
0x14000fc1b  cmp     rdx, [rdi+18h]
0x14000fc1f  ja      short loc_14000FC4F
0x14000fc21  cmp     qword ptr [rdi+18h], 7
0x14000fc26  jbe     short loc_14000FC2D
0x14000fc28  mov     r14, [rdi]
0x14000fc2b  jmp     short loc_14000FC30
0x14000fc2d  mov     r14, rdi
0x14000fc30  mov     [rdi+10h], rdx
0x14000fc34  lea     rbx, [rdx+rdx]
0x14000fc38  mov     r8, rbx; Size
0x14000fc3b  mov     rdx, r9; Src
0x14000fc3e  mov     rcx, r14; void *
0x14000fc41  call    memmove_0
0x14000fc46  xor     eax, eax
0x14000fc48  mov     [r14+rbx], ax
0x14000fc4d  jmp     short loc_14000FC58
0x14000fc4f  mov     rcx, rdi
0x14000fc52  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14000fc57  nop
0x14000fc58  lea     rcx, [rsp+1A0h+lpNameBuffer]
0x14000fc5d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x14000fc62  mov     rdx, rdi
0x14000fc65  lea     rcx, [rbp+0A0h+var_110]
0x14000fc69  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000fc6e  mov     rdi, rax
0x14000fc71  mov     [rbp+0A0h+nSize], rax
0x14000fc78  cmp     qword ptr [rax+18h], 7
0x14000fc7d  jbe     short loc_14000FC84
0x14000fc7f  mov     rcx, [rax]
0x14000fc82  jmp     short loc_14000FC87
0x14000fc84  mov     rcx, rdi
0x14000fc87  mov     rax, [rax+10h]
0x14000fc8b  lea     rax, [rcx+rax*2]
0x14000fc8f  jbe     short loc_14000FC96
0x14000fc91  mov     rcx, [rdi]
0x14000fc94  jmp     short loc_14000FCAA
0x14000fc96  mov     rcx, rdi
0x14000fc99  jmp     short loc_14000FCAA
0x14000fc9b  cmp     word ptr [rcx], 5Ch ; '\'
0x14000fc9f  jnz     short loc_14000FCA6
0x14000fca1  mov     word ptr [rcx], 5Fh ; '_'
0x14000fca6  add     rcx, 2
0x14000fcaa  cmp     rcx, rax
0x14000fcad  jnz     short loc_14000FC9B
0x14000fcaf  mov     edx, 12h
0x14000fcb4  cmp     [rsi+18h], rdx
0x14000fcb8  jb      short loc_14000FCDC
0x14000fcba  mov     rbx, [rsi]
0x14000fcbd  mov     [rsi+10h], rdx
0x14000fcc1  lea     r8d, [rdx+12h]; Size
0x14000fcc5  lea     rdx, aEduprintprovre; "EduPrintProvRetry_"
0x14000fccc  mov     rcx, rbx; void *
0x14000fccf  call    memmove_0
0x14000fcd4  xor     eax, eax
0x14000fcd6  mov     [rbx+24h], ax
0x14000fcda  jmp     short loc_14000FCEB
0x14000fcdc  lea     r9, aEduprintprovre; "EduPrintProvRetry_"
0x14000fce3  mov     rcx, rsi
0x14000fce6  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14000fceb  mov     rdx, [rdi+10h]
0x14000fcef  cmp     qword ptr [rdi+18h], 7
0x14000fcf4  jbe     short loc_14000FCFB
0x14000fcf6  mov     r9, [rdi]
0x14000fcf9  jmp     short loc_14000FCFE
0x14000fcfb  mov     r9, rdi
0x14000fcfe  mov     rcx, [rsi+10h]
0x14000fd02  mov     rax, [rsi+18h]
0x14000fd06  sub     rax, rcx
0x14000fd09  cmp     rdx, rax
0x14000fd0c  ja      short loc_14000FD3E
0x14000fd0e  lea     r14, [rcx+rdx]
0x14000fd12  mov     [rsi+10h], r14
0x14000fd16  cmp     qword ptr [rsi+18h], 7
0x14000fd1b  jbe     short loc_14000FD22
0x14000fd1d  mov     rbx, [rsi]
0x14000fd20  jmp     short loc_14000FD25
0x14000fd22  mov     rbx, rsi
0x14000fd25  lea     r8, [rdx+rdx]; Size
0x14000fd29  lea     rcx, [rbx+rcx*2]; void *
0x14000fd2d  mov     rdx, r9; Src
0x14000fd30  call    memmove_0
0x14000fd35  xor     eax, eax
0x14000fd37  mov     [rbx+r14*2], ax
0x14000fd3c  jmp     short loc_14000FD4C
0x14000fd3e  mov     qword ptr [rsp+1A0h+ppv], rdx; int
0x14000fd43  mov     rcx, rsi; Src
0x14000fd46  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x14000fd4b  nop
0x14000fd4c  mov     rcx, rdi
0x14000fd4f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000fd54  xor     edx, edx; dwCoInit
0x14000fd56  xor     ecx, ecx; pvReserved
0x14000fd58  call    cs:__imp_CoInitializeEx
0x14000fd5e  mov     rcx, [rbp+0A8h]; this
0x14000fd65  test    eax, eax
0x14000fd67  js      loc_14001003C
0x14000fd6d  mov     byte ptr [r15], 1
0x14000fd71  mov     rcx, [r13+0]
0x14000fd75  mov     qword ptr [r13+0], 0
0x14000fd7d  test    rcx, rcx
0x14000fd80  jz      short loc_14000FD8F
0x14000fd82  mov     rax, [rcx]
0x14000fd85  mov     rax, [rax+10h]
0x14000fd89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fd8e  nop
0x14000fd8f  mov     qword ptr [rsp+1A0h+ppv], r13; int
0x14000fd94  lea     r9, IID_ITaskService; riid
0x14000fd9b  xor     edx, edx; pUnkOuter
0x14000fd9d  lea     r8d, [rdx+1]; dwClsContext
0x14000fda1  lea     rcx, CLSID_TaskScheduler; rclsid
0x14000fda8  call    cs:__imp_CoCreateInstance
0x14000fdae  mov     rcx, [rbp+0A8h]; this
0x14000fdb5  test    eax, eax
0x14000fdb7  js      loc_140010051
0x14000fdbd  mov     rdi, [r13+0]
0x14000fdc1  mov     rax, [rdi]
0x14000fdc4  mov     rbx, [rax+50h]
0x14000fdc8  lea     rcx, [rsp+1A0h+pvarg]; pvarg
0x14000fdcd  call    cs:__imp_VariantInit
0x14000fdd3  nop
0x14000fdd4  movups  xmm10, xmmword ptr [rsp+1A0h+pvarg]
0x14000fdda  movsd   xmm11, qword ptr [rbp+0A0h+pvarg+10h]
0x14000fde0  lea     rcx, [rsp+1A0h+var_140]; pvarg
0x14000fde5  call    cs:__imp_VariantInit
0x14000fdeb  nop
0x14000fdec  movups  xmm8, xmmword ptr [rsp+1A0h+var_140]
0x14000fdf2  movsd   xmm9, qword ptr [rsp+1A0h+var_140+10h]
0x14000fdf9  lea     rcx, [rsp+1A0h+var_158]; pvarg
0x14000fdfe  call    cs:__imp_VariantInit
0x14000fe04  nop
0x14000fe05  movups  xmm6, xmmword ptr [rsp+1A0h+var_158]
0x14000fe0a  movsd   xmm7, qword ptr [rsp+1A0h+var_158+10h]
0x14000fe10  lea     rcx, [rsp+1A0h+lpNameBuffer]; pvarg
0x14000fe15  call    cs:__imp_VariantInit
0x14000fe1b  nop
0x14000fe1c  movups  xmm0, xmmword ptr [rsp+1A0h+lpNameBuffer]
0x14000fe21  movsd   xmm1, [rsp+1A0h+var_160]
0x14000fe27  movaps  xmmword ptr [rbp+0A0h+var_F0], xmm10
0x14000fe2c  movsd   [rbp+0A0h+var_E0], xmm11
0x14000fe32  movaps  [rbp+0A0h+var_D0], xmm8
0x14000fe37  movsd   [rbp+0A0h+var_C0], xmm9
0x14000fe3d  movaps  [rbp+0A0h+var_B0], xmm6
0x14000fe41  movsd   [rbp+0A0h+var_A0], xmm7
0x14000fe46  movaps  [rbp+0A0h+var_110], xmm0
0x14000fe4a  movsd   [rbp+0A0h+var_100], xmm1
0x14000fe4f  lea     rax, [rbp+0A0h+var_F0]
0x14000fe53  mov     qword ptr [rsp+1A0h+ppv], rax; int
0x14000fe58  lea     r9, [rbp+0A0h+var_D0]
0x14000fe5c  lea     r8, [rbp+0A0h+var_B0]
0x14000fe60  lea     rdx, [rbp+0A0h+var_110]
0x14000fe64  mov     rcx, rdi
0x14000fe67  mov     rax, rbx
0x14000fe6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe6f  mov     rcx, [rbp+0A8h]; this
0x14000fe76  test    eax, eax
0x14000fe78  js      loc_140010066
0x14000fe7e  lea     rcx, [rsp+1A0h+lpNameBuffer]; pvarg
0x14000fe83  call    cs:__imp_VariantClear
0x14000fe89  nop
0x14000fe8a  lea     rcx, [rsp+1A0h+var_158]; pvarg
0x14000fe8f  call    cs:__imp_VariantClear
0x14000fe95  nop
0x14000fe96  lea     rcx, [rsp+1A0h+var_140]; pvarg
0x14000fe9b  call    cs:__imp_VariantClear
0x14000fea1  nop
0x14000fea2  lea     rcx, [rsp+1A0h+pvarg]; pvarg
0x14000fea7  call    cs:__imp_VariantClear
0x14000fead  mov     rdi, [r13+0]
0x14000feb1  mov     rax, [rdi]
0x14000feb4  mov     r14, [rax+38h]
0x14000feb8  lea     rbx, [r15+50h]
0x14000febc  mov     rcx, [rbx]
0x14000febf  xor     r13d, r13d
0x14000fec2  mov     [rbx], r13
0x14000fec5  test    rcx, rcx
0x14000fec8  jz      short loc_14000FED7
0x14000feca  mov     rax, [rcx]
0x14000fecd  mov     rax, [rax+10h]
0x14000fed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fed6  nop
0x14000fed7  lea     rdx, asc_140015CDC; "\\"
0x14000fede  lea     rcx, [rbp+0A0h+nSize]; this
0x14000fee5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000feea  nop
0x14000feeb  mov     rcx, [rax]
0x14000feee  test    rcx, rcx
0x14000fef1  jz      short loc_14000FEF8
0x14000fef3  mov     rdx, [rcx]
0x14000fef6  jmp     short loc_14000FEFB
0x14000fef8  mov     rdx, r13
0x14000fefb  mov     r8, rbx
0x14000fefe  mov     rcx, rdi
0x14000ff01  mov     rax, r14
0x14000ff04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff09  mov     rcx, [rbp+0A8h]; this
0x14000ff10  test    eax, eax
0x14000ff12  js      loc_14001007B
0x14000ff18  lea     rcx, [rbp+0A0h+nSize]; this
0x14000ff1f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14000ff24  mov     rbx, [rbx]
  ... truncated ...
```
