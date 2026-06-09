# win_dox::OpcSignaturePartReference::GetContentType(void)

- ea: `0x1800edbec`
- end: `0x1800edd00`
- name: `?GetContentType@OpcSignaturePartReference@win_dox@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a4cc4`

## callees

- `0x180012468`
- `0x180017320`
- `0x18002db70`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1800edbec`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800edcd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800edcd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcSignaturePartReference::GetContentType(__int64 **a1, __int64 a2)
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
  v5 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v4 + 32))(v3, pv);
  if ( v5 < 0 )
  {
    memset_0(v9, 0, sizeof(v9));
    StringCchPrintfW(v9, 0x200u, L"Call to GetContentType failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x52u,
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
0x1800edbec  mov     rax, rsp
0x1800edbef  push    rdi
0x1800edbf0  sub     rsp, 510h
0x1800edbf7  mov     [rsp+518h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x1800edc00  mov     [rax+18h], rbx
0x1800edc04  mov     rax, cs:__security_cookie
0x1800edc0b  xor     rax, rsp
0x1800edc0e  mov     [rsp+518h+var_18], rax
0x1800edc16  mov     rbx, rdx
0x1800edc19  mov     [rsp+518h+pv], rdx
0x1800edc1e  mov     [rsp+518h+pv], 0
0x1800edc27  mov     rcx, [rcx]
0x1800edc2a  mov     rax, [rcx]
0x1800edc2d  mov     [rsp+518h+pv], 0
0x1800edc36  lea     rdx, [rsp+518h+pv]
0x1800edc3b  mov     rax, [rax+20h]
0x1800edc3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edc44  mov     edi, eax
0x1800edc46  test    eax, eax
0x1800edc48  jns     short loc_1800EDCBE
0x1800edc4a  xor     edx, edx; Val
0x1800edc4c  mov     r8d, 400h; Size
0x1800edc52  lea     rcx, [rsp+518h+var_418]; void *
0x1800edc5a  call    memset_0
0x1800edc5f  mov     r9d, edi
0x1800edc62  lea     r8, aCallToGetconte; "Call to GetContentType failed with HRes"...
0x1800edc69  mov     edx, 200h; unsigned __int64
0x1800edc6e  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x1800edc76  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800edc7b  lea     rax, [rsp+518h+var_418]
0x1800edc83  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x1800edc88  mov     [rsp+518h+var_4F0], edi; unsigned int
0x1800edc8c  mov     [rsp+518h+var_4F8], 52h ; 'R'; unsigned int
0x1800edc94  lea     r9, word_180139126
0x1800edc9b  lea     r8, aNoFilename; "(no filename)"
0x1800edca2  lea     rcx, [rsp+518h+pExceptionObject]; this
0x1800edca7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800edcac  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800edcb3  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x1800edcb8  call    _CxxThrowException_0
0x1800edcbe  mov     rdx, [rsp+518h+pv]
0x1800edcc3  mov     rcx, rbx
0x1800edcc6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800edccb  nop
0x1800edccc  mov     rcx, [rsp+518h+pv]; pv
0x1800edcd1  test    rcx, rcx
0x1800edcd4  jz      short loc_1800EDCDC
0x1800edcd6  call    cs:__imp_CoTaskMemFree
0x1800edcdc  mov     rax, rbx
0x1800edcdf  mov     rcx, [rsp+518h+var_18]
0x1800edce7  xor     rcx, rsp; StackCookie
0x1800edcea  call    __security_check_cookie
0x1800edcef  mov     rbx, [rsp+518h+arg_10]
0x1800edcf7  add     rsp, 510h
0x1800edcfe  pop     rdi
0x1800edcff  retn
```
