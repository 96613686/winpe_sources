# win_dox::OpcRelationshipSelector::GetSelectionCriterion(void)

- ea: `0x1800a6190`
- end: `0x1800a62a4`
- name: `?GetSelectionCriterion@OpcRelationshipSelector@win_dox@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `276`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a5080`
- `0x1800a5d1c`
- `0x1800a73f0`

## callees

- `0x180012468`
- `0x180017320`
- `0x18002db70`
- `0x1800a6190`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a627a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a627a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcRelationshipSelector::GetSelectionCriterion(__int64 **a1, __int64 a2)
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
    StringCchPrintfW(v9, 0x200u, L"Call to GetSelectionCriterion failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x53u,
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
0x1800a6190  mov     rax, rsp
0x1800a6193  push    rdi
0x1800a6194  sub     rsp, 510h
0x1800a619b  mov     [rsp+518h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x1800a61a4  mov     [rax+18h], rbx
0x1800a61a8  mov     rax, cs:__security_cookie
0x1800a61af  xor     rax, rsp
0x1800a61b2  mov     [rsp+518h+var_18], rax
0x1800a61ba  mov     rbx, rdx
0x1800a61bd  mov     [rsp+518h+pv], rdx
0x1800a61c2  mov     [rsp+518h+pv], 0
0x1800a61cb  mov     rcx, [rcx]
0x1800a61ce  mov     rax, [rcx]
0x1800a61d1  mov     [rsp+518h+pv], 0
0x1800a61da  lea     rdx, [rsp+518h+pv]
0x1800a61df  mov     rax, [rax+20h]
0x1800a61e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a61e8  mov     edi, eax
0x1800a61ea  test    eax, eax
0x1800a61ec  jns     short loc_1800A6262
0x1800a61ee  xor     edx, edx; Val
0x1800a61f0  mov     r8d, 400h; Size
0x1800a61f6  lea     rcx, [rsp+518h+var_418]; void *
0x1800a61fe  call    memset_0
0x1800a6203  mov     r9d, edi
0x1800a6206  lea     r8, aCallToGetselec_0; "Call to GetSelectionCriterion failed wi"...
0x1800a620d  mov     edx, 200h; unsigned __int64
0x1800a6212  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x1800a621a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800a621f  lea     rax, [rsp+518h+var_418]
0x1800a6227  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x1800a622c  mov     [rsp+518h+var_4F0], edi; unsigned int
0x1800a6230  mov     [rsp+518h+var_4F8], 53h ; 'S'; unsigned int
0x1800a6238  lea     r9, word_180139126
0x1800a623f  lea     r8, aNoFilename; "(no filename)"
0x1800a6246  lea     rcx, [rsp+518h+pExceptionObject]; this
0x1800a624b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a6250  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a6257  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x1800a625c  call    _CxxThrowException_0
0x1800a6262  mov     rdx, [rsp+518h+pv]
0x1800a6267  mov     rcx, rbx
0x1800a626a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800a626f  nop
0x1800a6270  mov     rcx, [rsp+518h+pv]; pv
0x1800a6275  test    rcx, rcx
0x1800a6278  jz      short loc_1800A6280
0x1800a627a  call    cs:__imp_CoTaskMemFree
0x1800a6280  mov     rax, rbx
0x1800a6283  mov     rcx, [rsp+518h+var_18]
0x1800a628b  xor     rcx, rsp; StackCookie
0x1800a628e  call    __security_check_cookie
0x1800a6293  mov     rbx, [rsp+518h+arg_10]
0x1800a629b  add     rsp, 510h
0x1800a62a2  pop     rdi
0x1800a62a3  retn
```
