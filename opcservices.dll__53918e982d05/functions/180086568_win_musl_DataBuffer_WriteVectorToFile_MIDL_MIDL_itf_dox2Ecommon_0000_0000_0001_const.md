# win_musl::DataBuffer::WriteVectorToFile(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 const &)

- ea: `0x180086568`
- end: `0x1800866bd`
- name: `?WriteVectorToFile@DataBuffer@win_musl@@AEAAXAEBU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z`
- size: `341`
- prototype: `void __fastcall(win_musl::DataBuffer *__hidden this, const struct __MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180037e74`
- `0x180038820`

## callees

- `0x180012468`
- `0x18002db70`
- `0x180086568`
- `0x180086cec`
- `0x1800a9638`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800865bf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800865bf`

## string_xrefs

- `0x180086652`: `WriteFile did not write expected data to temporary file`
- `0x1800865ea`: `Call to ::WriteFile failed with HResult 0x%X.`

## pseudocode

```c
void __fastcall win_musl::DataBuffer::WriteVectorToFile(win_musl::DataBuffer *this, DWORD *a2)
{
  DWORD v4; // r8d
  const void *v5; // rdx
  void *v6; // rcx
  unsigned int v7; // eax
  int v8; // edx
  signed int v9; // esi
  DWORD v10; // ecx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-4C8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-4B8h] BYREF
  wchar_t v13[512]; // [rsp+F0h] [rbp-418h] BYREF

  if ( *((_QWORD *)this + 8) == -1 )
    win_musl::DataBuffer::CreateAFile(this);
  v4 = *a2;
  v5 = (const void *)*((_QWORD *)a2 + 1);
  v6 = (void *)*((_QWORD *)this + 8);
  NumberOfBytesWritten = 0;
  v7 = WriteFile(v6, v5, v4, &NumberOfBytesWritten, 0);
  v9 = win_musl::HResultFromBool((win_musl *)v7, v8);
  if ( v9 < 0 )
  {
    memset_0(v13, 0, sizeof(v13));
    StringCchPrintfW(v13, 0x200u, L"Call to ::WriteFile failed with HResult 0x%X.", (unsigned int)v9);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x114u,
      v9,
      (struct win_musl::TStringEllipseBase *)v13);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v10 = NumberOfBytesWritten;
  *((_QWORD *)this + 9) += NumberOfBytesWritten;
  if ( v10 != *a2 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x11Au,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"WriteFile did not write expected data to temporary file");
    throw (SplException::THResultException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180086568  mov     [rsp+arg_10], rbx
0x18008656d  mov     [rsp+arg_18], rsi
0x180086572  push    rdi
0x180086573  sub     rsp, 500h
0x18008657a  mov     rax, cs:__security_cookie
0x180086581  xor     rax, rsp
0x180086584  mov     [rsp+508h+var_18], rax
0x18008658c  cmp     qword ptr [rcx+40h], 0FFFFFFFFFFFFFFFFh
0x180086591  mov     rdi, rdx
0x180086594  mov     rbx, rcx
0x180086597  jnz     short loc_18008659E
0x180086599  call    ?CreateAFile@DataBuffer@win_musl@@AEAAXXZ; win_musl::DataBuffer::CreateAFile(void)
0x18008659e  mov     r8d, [rdi]; nNumberOfBytesToWrite
0x1800865a1  lea     r9, [rsp+508h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800865a6  mov     rdx, [rdi+8]; lpBuffer
0x1800865aa  mov     rcx, [rbx+40h]; hFile
0x1800865ae  mov     [rsp+508h+NumberOfBytesWritten], 0
0x1800865b6  mov     [rsp+508h+lpOverlapped], 0; lpOverlapped
0x1800865bf  call    cs:__imp_WriteFile
0x1800865c5  mov     ecx, eax; this
0x1800865c7  call    ?HResultFromBool@win_musl@@YAJH@Z; win_musl::HResultFromBool(int)
0x1800865cc  mov     esi, eax
0x1800865ce  test    eax, eax
0x1800865d0  jns     short loc_180086646
0x1800865d2  xor     edx, edx; Val
0x1800865d4  lea     rcx, [rsp+508h+var_418]; void *
0x1800865dc  mov     r8d, 400h; Size
0x1800865e2  call    memset_0
0x1800865e7  mov     r9d, esi
0x1800865ea  lea     r8, aCallToWritefil; "Call to ::WriteFile failed with HResult"...
0x1800865f1  mov     edx, 200h; unsigned __int64
0x1800865f6  lea     rcx, [rsp+508h+var_418]; wchar_t *
0x1800865fe  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180086603  lea     rax, [rsp+508h+var_418]
0x18008660b  mov     [rsp+508h+var_4D8], rax; struct win_musl::TStringEllipseBase *
0x180086610  lea     r9, word_180139126
0x180086617  mov     [rsp+508h+var_4E0], esi; unsigned int
0x18008661b  lea     r8, aNoFilename; "(no filename)"
0x180086622  lea     rcx, [rsp+508h+pExceptionObject]; this
0x180086627  mov     dword ptr [rsp+508h+lpOverlapped], 114h; unsigned int
0x18008662f  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180086634  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18008663b  lea     rcx, [rsp+508h+pExceptionObject]; pExceptionObject
0x180086640  call    _CxxThrowException_0
0x180086646  mov     ecx, [rsp+508h+NumberOfBytesWritten]
0x18008664a  add     [rbx+48h], rcx
0x18008664e  cmp     ecx, [rdi]
0x180086650  jz      short loc_180086698
0x180086652  lea     rax, aWritefileDidNo; "WriteFile did not write expected data t"...
0x180086659  mov     [rsp+508h+var_4D8], rax; struct win_musl::TStringEllipseBase *
0x18008665e  lea     r9, word_180139126
0x180086665  mov     [rsp+508h+var_4E0], 8000FFFFh; unsigned int
0x18008666d  lea     r8, aNoFilename; "(no filename)"
0x180086674  lea     rcx, [rsp+508h+pExceptionObject]; this
0x180086679  mov     dword ptr [rsp+508h+lpOverlapped], 11Ah; unsigned int
0x180086681  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180086686  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18008668d  lea     rcx, [rsp+508h+pExceptionObject]; pExceptionObject
0x180086692  call    _CxxThrowException_0
0x180086698  mov     rcx, [rsp+508h+var_18]
0x1800866a0  xor     rcx, rsp; StackCookie
0x1800866a3  call    __security_check_cookie
0x1800866a8  lea     r11, [rsp+508h+var_8]
0x1800866b0  mov     rbx, [r11+20h]
0x1800866b4  mov     rsi, [r11+28h]
0x1800866b8  mov     rsp, r11
0x1800866bb  pop     rdi
0x1800866bc  retn
```
