# win_dox::OpcPart::GetContentType(void)

- ea: `0x1800a17e4`
- end: `0x1800a18f8`
- name: `?GetContentType@OpcPart@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `276`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009f9ec`
- `0x18009ff64`
- `0x1800a0fe8`
- `0x1800a1900`
- `0x1800a3b88`
- `0x1800a4cc4`
- `0x1800a9188`

## callees

- `0x180012468`
- `0x180017320`
- `0x18002db70`
- `0x1800a17e4`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a18ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a18ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcPart::GetContentType(__int64 **a1, __int64 a2)
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
  v5 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v4 + 48))(v3, pv);
  if ( v5 < 0 )
  {
    memset_0(v9, 0, sizeof(v9));
    StringCchPrintfW(v9, 0x200u, L"Call to GetContentType failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x7Au,
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
0x1800a17e4  mov     rax, rsp
0x1800a17e7  push    rdi
0x1800a17e8  sub     rsp, 510h
0x1800a17ef  mov     [rsp+518h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x1800a17f8  mov     [rax+18h], rbx
0x1800a17fc  mov     rax, cs:__security_cookie
0x1800a1803  xor     rax, rsp
0x1800a1806  mov     [rsp+518h+var_18], rax
0x1800a180e  mov     rbx, rdx
0x1800a1811  mov     [rsp+518h+pv], rdx
0x1800a1816  mov     [rsp+518h+pv], 0
0x1800a181f  mov     rcx, [rcx]
0x1800a1822  mov     rax, [rcx]
0x1800a1825  mov     [rsp+518h+pv], 0
0x1800a182e  lea     rdx, [rsp+518h+pv]
0x1800a1833  mov     rax, [rax+30h]
0x1800a1837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a183c  mov     edi, eax
0x1800a183e  test    eax, eax
0x1800a1840  jns     short loc_1800A18B6
0x1800a1842  xor     edx, edx; Val
0x1800a1844  mov     r8d, 400h; Size
0x1800a184a  lea     rcx, [rsp+518h+var_418]; void *
0x1800a1852  call    memset_0
0x1800a1857  mov     r9d, edi
0x1800a185a  lea     r8, aCallToGetconte; "Call to GetContentType failed with HRes"...
0x1800a1861  mov     edx, 200h; unsigned __int64
0x1800a1866  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x1800a186e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800a1873  lea     rax, [rsp+518h+var_418]
0x1800a187b  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x1800a1880  mov     [rsp+518h+var_4F0], edi; unsigned int
0x1800a1884  mov     [rsp+518h+var_4F8], 7Ah ; 'z'; unsigned int
0x1800a188c  lea     r9, word_180139126
0x1800a1893  lea     r8, aNoFilename; "(no filename)"
0x1800a189a  lea     rcx, [rsp+518h+pExceptionObject]; this
0x1800a189f  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a18a4  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a18ab  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x1800a18b0  call    _CxxThrowException_0
0x1800a18b6  mov     rdx, [rsp+518h+pv]
0x1800a18bb  mov     rcx, rbx
0x1800a18be  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800a18c3  nop
0x1800a18c4  mov     rcx, [rsp+518h+pv]; pv
0x1800a18c9  test    rcx, rcx
0x1800a18cc  jz      short loc_1800A18D4
0x1800a18ce  call    cs:__imp_CoTaskMemFree
0x1800a18d4  mov     rax, rbx
0x1800a18d7  mov     rcx, [rsp+518h+var_18]
0x1800a18df  xor     rcx, rsp; StackCookie
0x1800a18e2  call    __security_check_cookie
0x1800a18e7  mov     rbx, [rsp+518h+arg_10]
0x1800a18ef  add     rsp, 510h
0x1800a18f6  pop     rdi
0x1800a18f7  retn
```
