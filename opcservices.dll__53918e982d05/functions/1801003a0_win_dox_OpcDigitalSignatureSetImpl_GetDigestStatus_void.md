# win_dox::OpcDigitalSignatureSetImpl::GetDigestStatus(void *)

- ea: `0x1801003a0`
- end: `0x18010047e`
- name: `?GetDigestStatus@OpcDigitalSignatureSetImpl@win_dox@@AEAA_NPEAX@Z`
- size: `222`
- prototype: `bool(win_dox::OpcDigitalSignatureSetImpl *__hidden this, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800a4630`
- `0x18010021c`

## callees

- `0x180012468`
- `0x18002db70`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801003a0`
- `0x1801178f0`

## import_xrefs

- `CRYPTXML!CryptXmlGetStatus` at `0x1801003d1`
- `CRYPTXML!CryptXmlGetStatus` at `0x1801003d1`

## string_xrefs

- `0x1801003f5`: `Call to CryptXmlGetStatus failed with HResult 0x%X.`

## pseudocode

```c
bool __fastcall win_dox::OpcDigitalSignatureSetImpl::GetDigestStatus(
        win_dox::OpcDigitalSignatureSetImpl *this,
        void *a2)
{
  HRESULT Status; // ebx
  CRYPT_XML_STATUS pStatus; // [rsp+40h] [rbp-4C8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-4B8h] BYREF
  wchar_t v6[512]; // [rsp+F0h] [rbp-418h] BYREF

  *(_QWORD *)&pStatus.cbSize = 0;
  pStatus.dwInfoStatus = 0;
  Status = CryptXmlGetStatus(a2, &pStatus);
  if ( Status < 0 )
  {
    memset_0(v6, 0, sizeof(v6));
    StringCchPrintfW(v6, 0x200u, L"Call to CryptXmlGetStatus failed with HResult 0x%X.", (unsigned int)Status);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x173u,
      Status,
      (struct win_musl::TStringEllipseBase *)v6);
    throw (SplException::THResultException *)pExceptionObject;
  }
  return !pStatus.dwErrorStatus && (pStatus.dwInfoStatus & 8) != 0;
}

```

## disassembly

```asm
0x1801003a0  push    rbx
0x1801003a2  sub     rsp, 500h
0x1801003a9  mov     rax, cs:__security_cookie
0x1801003b0  xor     rax, rsp
0x1801003b3  mov     [rsp+508h+var_18], rax
0x1801003bb  xor     ecx, ecx
0x1801003bd  mov     rax, rdx
0x1801003c0  mov     qword ptr [rsp+508h+pStatus.cbSize], rcx
0x1801003c5  lea     rdx, [rsp+508h+pStatus]; pStatus
0x1801003ca  mov     [rsp+508h+pStatus.dwInfoStatus], ecx
0x1801003ce  mov     rcx, rax; hCryptXml
0x1801003d1  call    cs:__imp_CryptXmlGetStatus
0x1801003d7  mov     ebx, eax
0x1801003d9  test    eax, eax
0x1801003db  jns     short loc_180100451
0x1801003dd  xor     edx, edx; Val
0x1801003df  lea     rcx, [rsp+508h+var_418]; void *
0x1801003e7  mov     r8d, 400h; Size
0x1801003ed  call    memset_0
0x1801003f2  mov     r9d, ebx
0x1801003f5  lea     r8, aCallToCryptxml; "Call to CryptXmlGetStatus failed with H"...
0x1801003fc  mov     edx, 200h; unsigned __int64
0x180100401  lea     rcx, [rsp+508h+var_418]; wchar_t *
0x180100409  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18010040e  lea     rax, [rsp+508h+var_418]
0x180100416  mov     [rsp+508h+var_4D8], rax; struct win_musl::TStringEllipseBase *
0x18010041b  lea     r9, word_180139126
0x180100422  mov     [rsp+508h+var_4E0], ebx; unsigned int
0x180100426  lea     r8, aNoFilename; "(no filename)"
0x18010042d  lea     rcx, [rsp+508h+pExceptionObject]; this
0x180100432  mov     [rsp+508h+var_4E8], 173h; unsigned int
0x18010043a  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18010043f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180100446  lea     rcx, [rsp+508h+pExceptionObject]; pExceptionObject
0x18010044b  call    _CxxThrowException_0
0x180100451  cmp     [rsp+508h+pStatus.dwErrorStatus], 0
0x180100456  jnz     short loc_180100463
0x180100458  mov     eax, [rsp+508h+pStatus.dwInfoStatus]
0x18010045c  shr     eax, 3
0x18010045f  and     al, 1
0x180100461  jmp     short loc_180100465
0x180100463  xor     al, al
0x180100465  mov     rcx, [rsp+508h+var_18]
0x18010046d  xor     rcx, rsp; StackCookie
0x180100470  call    __security_check_cookie
0x180100475  add     rsp, 500h
0x18010047c  pop     rbx
0x18010047d  retn
```
