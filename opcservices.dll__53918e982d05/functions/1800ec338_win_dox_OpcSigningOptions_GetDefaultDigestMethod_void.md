# win_dox::OpcSigningOptions::GetDefaultDigestMethod(void)

- ea: `0x1800ec338`
- end: `0x1800ec44c`
- name: `?GetDefaultDigestMethod@OpcSigningOptions@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `276`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a2494`
- `0x1800a3810`
- `0x1800c23a4`

## callees

- `0x180012468`
- `0x180017320`
- `0x18002db70`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1800ec338`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec422`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec422`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcSigningOptions::GetDefaultDigestMethod(__int64 **a1, __int64 a2)
{
  __int64 *v3; // rcx
  __int64 v4; // rax
  signed int v5; // edi
  LPVOID pv[4]; // [rsp+40h] [rbp-4D8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-4B8h] BYREF
  wchar_t v9[512]; // [rsp+100h] [rbp-418h] BYREF

  pv[2] = (LPVOID)-2LL;
  pv[0] = 0;
  v3 = *a1;
  v4 = *v3;
  pv[0] = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v4 + 56))(v3, pv);
  if ( v5 < 0 )
  {
    memset_0(v9, 0, sizeof(v9));
    StringCchPrintfW(v9, 0x200u, L"Call to GetDefaultDigestMethod failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x7Cu,
      v5,
      (struct win_musl::TStringEllipseBase *)v9);
    throw (SplException::THResultException *)pExceptionObject;
  }
  std::wstring::wstring(a2, pv[0]);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return a2;
}

```

## disassembly

```asm
0x1800ec338  mov     rax, rsp
0x1800ec33b  push    rdi
0x1800ec33c  sub     rsp, 510h
0x1800ec343  mov     [rsp+518h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x1800ec34c  mov     [rax+18h], rbx
0x1800ec350  mov     rax, cs:__security_cookie
0x1800ec357  xor     rax, rsp
0x1800ec35a  mov     [rsp+518h+var_18], rax
0x1800ec362  mov     rbx, rdx
0x1800ec365  mov     [rsp+518h+pv], rdx
0x1800ec36a  mov     [rsp+518h+pv], 0
0x1800ec373  mov     rcx, [rcx]
0x1800ec376  mov     rax, [rcx]
0x1800ec379  mov     [rsp+518h+pv], 0
0x1800ec382  lea     rdx, [rsp+518h+pv]
0x1800ec387  mov     rax, [rax+38h]
0x1800ec38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec390  mov     edi, eax
0x1800ec392  test    eax, eax
0x1800ec394  jns     short loc_1800EC40A
0x1800ec396  xor     edx, edx; Val
0x1800ec398  mov     r8d, 400h; Size
0x1800ec39e  lea     rcx, [rsp+518h+var_418]; void *
0x1800ec3a6  call    memset_0
0x1800ec3ab  mov     r9d, edi
0x1800ec3ae  lea     r8, aCallToGetdefau; "Call to GetDefaultDigestMethod failed w"...
0x1800ec3b5  mov     edx, 200h; unsigned __int64
0x1800ec3ba  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x1800ec3c2  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ec3c7  lea     rax, [rsp+518h+var_418]
0x1800ec3cf  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x1800ec3d4  mov     [rsp+518h+var_4F0], edi; unsigned int
0x1800ec3d8  mov     [rsp+518h+var_4F8], 7Ch ; '|'; unsigned int
0x1800ec3e0  lea     r9, word_180139126
0x1800ec3e7  lea     r8, aNoFilename; "(no filename)"
0x1800ec3ee  lea     rcx, [rsp+518h+pExceptionObject]; this
0x1800ec3f3  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800ec3f8  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800ec3ff  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x1800ec404  call    _CxxThrowException_0
0x1800ec40a  mov     rdx, [rsp+518h+pv]
0x1800ec40f  mov     rcx, rbx
0x1800ec412  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800ec417  nop
0x1800ec418  mov     rcx, [rsp+518h+pv]; pv
0x1800ec41d  test    rcx, rcx
0x1800ec420  jz      short loc_1800EC428
0x1800ec422  call    cs:__imp_CoTaskMemFree
0x1800ec428  mov     rax, rbx
0x1800ec42b  mov     rcx, [rsp+518h+var_18]
0x1800ec433  xor     rcx, rsp; StackCookie
0x1800ec436  call    __security_check_cookie
0x1800ec43b  mov     rbx, [rsp+518h+arg_10]
0x1800ec443  add     rsp, 510h
0x1800ec44a  pop     rdi
0x1800ec44b  retn
```
