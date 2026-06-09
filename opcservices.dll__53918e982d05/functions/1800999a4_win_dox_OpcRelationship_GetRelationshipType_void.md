# win_dox::OpcRelationship::GetRelationshipType(void)

- ea: `0x1800999a4`
- end: `0x180099ab8`
- name: `?GetRelationshipType@OpcRelationship@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `276`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a8a60`
- `0x1800a8bb4`
- `0x1800a97a8`
- `0x1800f509c`
- `0x18010605c`

## callees

- `0x180012468`
- `0x180017320`
- `0x18002db70`
- `0x1800999a4`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099a8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099a8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcRelationship::GetRelationshipType(__int64 **a1, __int64 a2)
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
    StringCchPrintfW(v9, 0x200u, L"Call to GetRelationshipType failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x58u,
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
0x1800999a4  mov     rax, rsp
0x1800999a7  push    rdi
0x1800999a8  sub     rsp, 510h
0x1800999af  mov     [rsp+518h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x1800999b8  mov     [rax+18h], rbx
0x1800999bc  mov     rax, cs:__security_cookie
0x1800999c3  xor     rax, rsp
0x1800999c6  mov     [rsp+518h+var_18], rax
0x1800999ce  mov     rbx, rdx
0x1800999d1  mov     [rsp+518h+pv], rdx
0x1800999d6  mov     [rsp+518h+pv], 0
0x1800999df  mov     rcx, [rcx]
0x1800999e2  mov     rax, [rcx]
0x1800999e5  mov     [rsp+518h+pv], 0
0x1800999ee  lea     rdx, [rsp+518h+pv]
0x1800999f3  mov     rax, [rax+20h]
0x1800999f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800999fc  mov     edi, eax
0x1800999fe  test    eax, eax
0x180099a00  jns     short loc_180099A76
0x180099a02  xor     edx, edx; Val
0x180099a04  mov     r8d, 400h; Size
0x180099a0a  lea     rcx, [rsp+518h+var_418]; void *
0x180099a12  call    memset_0
0x180099a17  mov     r9d, edi
0x180099a1a  lea     r8, aCallToGetrelat; "Call to GetRelationshipType failed with"...
0x180099a21  mov     edx, 200h; unsigned __int64
0x180099a26  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x180099a2e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180099a33  lea     rax, [rsp+518h+var_418]
0x180099a3b  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x180099a40  mov     [rsp+518h+var_4F0], edi; unsigned int
0x180099a44  mov     [rsp+518h+var_4F8], 58h ; 'X'; unsigned int
0x180099a4c  lea     r9, word_180139126
0x180099a53  lea     r8, aNoFilename; "(no filename)"
0x180099a5a  lea     rcx, [rsp+518h+pExceptionObject]; this
0x180099a5f  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180099a64  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180099a6b  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x180099a70  call    _CxxThrowException_0
0x180099a76  mov     rdx, [rsp+518h+pv]
0x180099a7b  mov     rcx, rbx
0x180099a7e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180099a83  nop
0x180099a84  mov     rcx, [rsp+518h+pv]; pv
0x180099a89  test    rcx, rcx
0x180099a8c  jz      short loc_180099A94
0x180099a8e  call    cs:__imp_CoTaskMemFree
0x180099a94  mov     rax, rbx
0x180099a97  mov     rcx, [rsp+518h+var_18]
0x180099a9f  xor     rcx, rsp; StackCookie
0x180099aa2  call    __security_check_cookie
0x180099aa7  mov     rbx, [rsp+518h+arg_10]
0x180099aaf  add     rsp, 510h
0x180099ab6  pop     rdi
0x180099ab7  retn
```
