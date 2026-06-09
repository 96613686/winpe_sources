# win_dox::OpcSigningOptions::GetSignatureMethod(void)

- ea: `0x1800bf000`
- end: `0x1800bf114`
- name: `?GetSignatureMethod@OpcSigningOptions@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `276`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a2494`
- `0x1800a3810`
- `0x1800bed54`

## callees

- `0x180012468`
- `0x180017320`
- `0x18002db70`
- `0x1800bf000`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf0ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf0ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcSigningOptions::GetSignatureMethod(__int64 **a1, __int64 a2)
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
  v5 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v4 + 40))(v3, pv);
  if ( v5 < 0 )
  {
    memset_0(v9, 0, sizeof(v9));
    StringCchPrintfW(v9, 0x200u, L"Call to GetSignatureMethod failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x61u,
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
0x1800bf000  mov     rax, rsp
0x1800bf003  push    rdi
0x1800bf004  sub     rsp, 510h
0x1800bf00b  mov     [rsp+518h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x1800bf014  mov     [rax+18h], rbx
0x1800bf018  mov     rax, cs:__security_cookie
0x1800bf01f  xor     rax, rsp
0x1800bf022  mov     [rsp+518h+var_18], rax
0x1800bf02a  mov     rbx, rdx
0x1800bf02d  mov     [rsp+518h+pv], rdx
0x1800bf032  mov     [rsp+518h+pv], 0
0x1800bf03b  mov     rcx, [rcx]
0x1800bf03e  mov     rax, [rcx]
0x1800bf041  mov     [rsp+518h+pv], 0
0x1800bf04a  lea     rdx, [rsp+518h+pv]
0x1800bf04f  mov     rax, [rax+28h]
0x1800bf053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf058  mov     edi, eax
0x1800bf05a  test    eax, eax
0x1800bf05c  jns     short loc_1800BF0D2
0x1800bf05e  xor     edx, edx; Val
0x1800bf060  mov     r8d, 400h; Size
0x1800bf066  lea     rcx, [rsp+518h+var_418]; void *
0x1800bf06e  call    memset_0
0x1800bf073  mov     r9d, edi
0x1800bf076  lea     r8, aCallToGetsigna; "Call to GetSignatureMethod failed with "...
0x1800bf07d  mov     edx, 200h; unsigned __int64
0x1800bf082  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x1800bf08a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800bf08f  lea     rax, [rsp+518h+var_418]
0x1800bf097  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x1800bf09c  mov     [rsp+518h+var_4F0], edi; unsigned int
0x1800bf0a0  mov     [rsp+518h+var_4F8], 61h ; 'a'; unsigned int
0x1800bf0a8  lea     r9, word_180139126
0x1800bf0af  lea     r8, aNoFilename; "(no filename)"
0x1800bf0b6  lea     rcx, [rsp+518h+pExceptionObject]; this
0x1800bf0bb  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800bf0c0  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800bf0c7  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x1800bf0cc  call    _CxxThrowException_0
0x1800bf0d2  mov     rdx, [rsp+518h+pv]
0x1800bf0d7  mov     rcx, rbx
0x1800bf0da  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800bf0df  nop
0x1800bf0e0  mov     rcx, [rsp+518h+pv]; pv
0x1800bf0e5  test    rcx, rcx
0x1800bf0e8  jz      short loc_1800BF0F0
0x1800bf0ea  call    cs:__imp_CoTaskMemFree
0x1800bf0f0  mov     rax, rbx
0x1800bf0f3  mov     rcx, [rsp+518h+var_18]
0x1800bf0fb  xor     rcx, rsp; StackCookie
0x1800bf0fe  call    __security_check_cookie
0x1800bf103  mov     rbx, [rsp+518h+arg_10]
0x1800bf10b  add     rsp, 510h
0x1800bf112  pop     rdi
0x1800bf113  retn
```
