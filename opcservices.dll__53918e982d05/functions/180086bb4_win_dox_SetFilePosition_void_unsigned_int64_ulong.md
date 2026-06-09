# win_dox::SetFilePosition(void *,unsigned __int64,ulong)

- ea: `0x180086bb4`
- end: `0x180086ce3`
- name: `?SetFilePosition@win_dox@@YA_KPEAX_KK@Z`
- size: `303`
- prototype: `unsigned __int64 __fastcall(win_dox *__hidden this, void *, unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180086990`
- `0x1800e0300`

## callees

- `0x180012468`
- `0x18002db70`
- `0x180086bb4`
- `0x180086cec`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180086be7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180086be7`

## string_xrefs

- `0x180086c41`: `Call to SetFilePointerEx failed with HResult 0x%X.`
- `0x180086c9d`: `SetFilePosition SetFilePointerEx requestedPosition and currentPosition do not match`

## pseudocode

```c
LARGE_INTEGER __fastcall win_dox::SetFilePosition(win_dox *this, void *a2)
{
  unsigned int v3; // eax
  int v4; // edx
  signed int v5; // edi
  LARGE_INTEGER result; // rax
  LARGE_INTEGER NewFilePointer; // [rsp+40h] [rbp-4C8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-4B8h] BYREF
  wchar_t v9[512]; // [rsp+F0h] [rbp-418h] BYREF

  NewFilePointer.QuadPart = 0;
  v3 = SetFilePointerEx(this, (LARGE_INTEGER)a2, &NewFilePointer, 0);
  v5 = win_musl::HResultFromBool((win_musl *)v3, v4);
  if ( v5 < 0 )
  {
    memset_0(v9, 0, sizeof(v9));
    StringCchPrintfW(v9, 0x200u, L"Call to SetFilePointerEx failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x20u,
      v5,
      (struct win_musl::TStringEllipseBase *)v9);
    throw (SplException::THResultException *)pExceptionObject;
  }
  result = NewFilePointer;
  if ( (void *)NewFilePointer.QuadPart != a2 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x24u,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"SetFilePosition SetFilePointerEx requestedPosition and currentPosition do not match");
    throw (SplException::THResultException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180086bb4  mov     [rsp+arg_10], rbx
0x180086bb9  push    rdi
0x180086bba  sub     rsp, 500h
0x180086bc1  mov     rax, cs:__security_cookie
0x180086bc8  xor     rax, rsp
0x180086bcb  mov     [rsp+508h+var_18], rax
0x180086bd3  xor     r9d, r9d; dwMoveMethod
0x180086bd6  mov     qword ptr [rsp+508h+NewFilePointer], 0
0x180086bdf  lea     r8, [rsp+508h+NewFilePointer]; lpNewFilePointer
0x180086be4  mov     rbx, rdx
0x180086be7  call    cs:__imp_SetFilePointerEx
0x180086bed  mov     ecx, eax; this
0x180086bef  call    ?HResultFromBool@win_musl@@YAJH@Z; win_musl::HResultFromBool(int)
0x180086bf4  mov     edi, eax
0x180086bf6  test    eax, eax
0x180086bf8  js      short loc_180086C29
0x180086bfa  mov     rax, qword ptr [rsp+508h+NewFilePointer]
0x180086bff  cmp     rax, rbx
0x180086c02  jnz     loc_180086C9D
0x180086c08  mov     rcx, [rsp+508h+var_18]
0x180086c10  xor     rcx, rsp; StackCookie
0x180086c13  call    __security_check_cookie
0x180086c18  mov     rbx, [rsp+508h+arg_10]
0x180086c20  add     rsp, 500h
0x180086c27  pop     rdi
0x180086c28  retn
0x180086c29  xor     edx, edx; Val
0x180086c2b  lea     rcx, [rsp+508h+var_418]; void *
0x180086c33  mov     r8d, 400h; Size
0x180086c39  call    memset_0
0x180086c3e  mov     r9d, edi
0x180086c41  lea     r8, aCallToSetfilep_0; "Call to SetFilePointerEx failed with HR"...
0x180086c48  mov     edx, 200h; unsigned __int64
0x180086c4d  lea     rcx, [rsp+508h+var_418]; wchar_t *
0x180086c55  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180086c5a  lea     rax, [rsp+508h+var_418]
0x180086c62  mov     [rsp+508h+var_4D8], rax; struct win_musl::TStringEllipseBase *
0x180086c67  lea     r9, word_180139126
0x180086c6e  mov     [rsp+508h+var_4E0], edi; unsigned int
0x180086c72  lea     r8, aNoFilename; "(no filename)"
0x180086c79  lea     rcx, [rsp+508h+pExceptionObject]; this
0x180086c7e  mov     [rsp+508h+var_4E8], 20h ; ' '; unsigned int
0x180086c86  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180086c8b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180086c92  lea     rcx, [rsp+508h+pExceptionObject]; pExceptionObject
0x180086c97  call    _CxxThrowException_0
0x180086c9d  lea     rax, aSetfilepositio; "SetFilePosition SetFilePointerEx reques"...
0x180086ca4  mov     [rsp+508h+var_4D8], rax; struct win_musl::TStringEllipseBase *
0x180086ca9  lea     r9, word_180139126
0x180086cb0  mov     [rsp+508h+var_4E0], 8000FFFFh; unsigned int
0x180086cb8  lea     r8, aNoFilename; "(no filename)"
0x180086cbf  lea     rcx, [rsp+508h+pExceptionObject]; this
0x180086cc4  mov     [rsp+508h+var_4E8], 24h ; '$'; unsigned int
0x180086ccc  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180086cd1  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180086cd8  lea     rcx, [rsp+508h+pExceptionObject]; pExceptionObject
0x180086cdd  call    _CxxThrowException_0
```
