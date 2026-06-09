# win_dox::OpcRelationship::GetId(void)

- ea: `0x1800aad2c`
- end: `0x1800aae40`
- name: `?GetId@OpcRelationship@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `276`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a8a60`
- `0x1800a8bb4`
- `0x1800a97a8`
- `0x1800aa35c`
- `0x180105f30`
- `0x18010605c`

## callees

- `0x180012468`
- `0x180017320`
- `0x18002db70`
- `0x1800aad2c`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aae16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aae16`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcRelationship::GetId(__int64 **a1, __int64 a2)
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
  v5 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v4 + 24))(v3, pv);
  if ( v5 < 0 )
  {
    memset_0(v9, 0, sizeof(v9));
    StringCchPrintfW(v9, 0x200u, L"Call to GetId failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x47u,
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
0x1800aad2c  mov     rax, rsp
0x1800aad2f  push    rdi
0x1800aad30  sub     rsp, 510h
0x1800aad37  mov     [rsp+518h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x1800aad40  mov     [rax+18h], rbx
0x1800aad44  mov     rax, cs:__security_cookie
0x1800aad4b  xor     rax, rsp
0x1800aad4e  mov     [rsp+518h+var_18], rax
0x1800aad56  mov     rbx, rdx
0x1800aad59  mov     [rsp+518h+pv], rdx
0x1800aad5e  mov     [rsp+518h+pv], 0
0x1800aad67  mov     rcx, [rcx]
0x1800aad6a  mov     rax, [rcx]
0x1800aad6d  mov     [rsp+518h+pv], 0
0x1800aad76  lea     rdx, [rsp+518h+pv]
0x1800aad7b  mov     rax, [rax+18h]
0x1800aad7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aad84  mov     edi, eax
0x1800aad86  test    eax, eax
0x1800aad88  jns     short loc_1800AADFE
0x1800aad8a  xor     edx, edx; Val
0x1800aad8c  mov     r8d, 400h; Size
0x1800aad92  lea     rcx, [rsp+518h+var_418]; void *
0x1800aad9a  call    memset_0
0x1800aad9f  mov     r9d, edi
0x1800aada2  lea     r8, aCallToGetidFai; "Call to GetId failed with HResult 0x%X."
0x1800aada9  mov     edx, 200h; unsigned __int64
0x1800aadae  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x1800aadb6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800aadbb  lea     rax, [rsp+518h+var_418]
0x1800aadc3  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x1800aadc8  mov     [rsp+518h+var_4F0], edi; unsigned int
0x1800aadcc  mov     [rsp+518h+var_4F8], 47h ; 'G'; unsigned int
0x1800aadd4  lea     r9, word_180139126
0x1800aaddb  lea     r8, aNoFilename; "(no filename)"
0x1800aade2  lea     rcx, [rsp+518h+pExceptionObject]; this
0x1800aade7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800aadec  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800aadf3  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x1800aadf8  call    _CxxThrowException_0
0x1800aadfe  mov     rdx, [rsp+518h+pv]
0x1800aae03  mov     rcx, rbx
0x1800aae06  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800aae0b  nop
0x1800aae0c  mov     rcx, [rsp+518h+pv]; pv
0x1800aae11  test    rcx, rcx
0x1800aae14  jz      short loc_1800AAE1C
0x1800aae16  call    cs:__imp_CoTaskMemFree
0x1800aae1c  mov     rax, rbx
0x1800aae1f  mov     rcx, [rsp+518h+var_18]
0x1800aae27  xor     rcx, rsp; StackCookie
0x1800aae2a  call    __security_check_cookie
0x1800aae2f  mov     rbx, [rsp+518h+arg_10]
0x1800aae37  add     rsp, 510h
0x1800aae3e  pop     rdi
0x1800aae3f  retn
```
