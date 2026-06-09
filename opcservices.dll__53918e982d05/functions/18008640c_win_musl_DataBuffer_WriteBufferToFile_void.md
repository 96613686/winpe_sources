# win_musl::DataBuffer::WriteBufferToFile(void)

- ea: `0x18008640c`
- end: `0x180086562`
- name: `?WriteBufferToFile@DataBuffer@win_musl@@AEAAXXZ`
- size: `342`
- prototype: `void __fastcall(win_musl::DataBuffer *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180037e74`

## callees

- `0x180012468`
- `0x18002db70`
- `0x180036b24`
- `0x18008640c`
- `0x180086cec`
- `0x1800a9638`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008646b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008646b`

## string_xrefs

- `0x180086484`: `WriteFile did not write expected data to temporary file`
- `0x1800864e2`: `Call to ::WriteFile failed with HResult 0x%X.`

## pseudocode

```c
void __fastcall win_musl::DataBuffer::WriteBufferToFile(win_musl::DataBuffer *this)
{
  _QWORD *v2; // rbx
  DWORD *v3; // rdx
  void *v4; // rcx
  DWORD v5; // esi
  unsigned int v6; // eax
  int v7; // edx
  signed int v8; // ebp
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-4F8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-4D8h] BYREF
  wchar_t v11[512]; // [rsp+100h] [rbp-438h] BYREF

  if ( *((_QWORD *)this + 8) == -1 )
    win_musl::DataBuffer::CreateAFile(this);
  v2 = (_QWORD *)*((_QWORD *)this + 1);
  while ( 1 )
  {
    v2 = (_QWORD *)*v2;
    if ( v2 == *((_QWORD **)this + 1) )
      break;
    v3 = (DWORD *)v2[3];
    v4 = (void *)*((_QWORD *)this + 8);
    v5 = *v3;
    NumberOfBytesWritten = 0;
    v6 = WriteFile(v4, v3 + 1, v5, &NumberOfBytesWritten, 0);
    v8 = win_musl::HResultFromBool((win_musl *)v6, v7);
    if ( v8 < 0 )
    {
      memset_0(v11, 0, sizeof(v11));
      StringCchPrintfW(v11, 0x200u, L"Call to ::WriteFile failed with HResult 0x%X.", (unsigned int)v8);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x147u,
        v8,
        (struct win_musl::TStringEllipseBase *)v11);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( NumberOfBytesWritten != v5 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x14Bu,
        0x8000FFFF,
        (struct win_musl::TStringEllipseBase *)L"WriteFile did not write expected data to temporary file");
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  std::list<win_scope::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>>>::clear(this);
}

```

## disassembly

```asm
0x18008640c  push    rbx
0x18008640e  push    rbp
0x18008640f  push    rsi
0x180086410  push    rdi
0x180086411  sub     rsp, 518h
0x180086418  mov     rax, cs:__security_cookie
0x18008641f  xor     rax, rsp
0x180086422  mov     [rsp+538h+var_38], rax
0x18008642a  cmp     qword ptr [rcx+40h], 0FFFFFFFFFFFFFFFFh
0x18008642f  mov     rdi, rcx
0x180086432  jnz     short loc_180086439
0x180086434  call    ?CreateAFile@DataBuffer@win_musl@@AEAAXXZ; win_musl::DataBuffer::CreateAFile(void)
0x180086439  mov     rbx, [rdi+8]
0x18008643d  mov     rbx, [rbx]
0x180086440  cmp     rbx, [rdi+8]
0x180086444  jz      loc_18008653E
0x18008644a  mov     rdx, [rbx+18h]
0x18008644e  lea     r9, [rsp+538h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180086453  mov     rcx, [rdi+40h]; hFile
0x180086457  xor     eax, eax
0x180086459  mov     [rsp+538h+lpOverlapped], rax; lpOverlapped
0x18008645e  mov     esi, [rdx]
0x180086460  add     rdx, 4; lpBuffer
0x180086464  mov     r8d, esi; nNumberOfBytesToWrite
0x180086467  mov     [rsp+538h+NumberOfBytesWritten], eax
0x18008646b  call    cs:__imp_WriteFile
0x180086471  mov     ecx, eax; this
0x180086473  call    ?HResultFromBool@win_musl@@YAJH@Z; win_musl::HResultFromBool(int)
0x180086478  mov     ebp, eax
0x18008647a  test    eax, eax
0x18008647c  js      short loc_1800864CA
0x18008647e  cmp     [rsp+538h+NumberOfBytesWritten], esi
0x180086482  jz      short loc_18008643D
0x180086484  lea     rax, aWritefileDidNo; "WriteFile did not write expected data t"...
0x18008648b  mov     [rsp+538h+var_508], rax; struct win_musl::TStringEllipseBase *
0x180086490  lea     r9, word_180139126
0x180086497  mov     [rsp+538h+var_510], 8000FFFFh; unsigned int
0x18008649f  lea     r8, aNoFilename; "(no filename)"
0x1800864a6  lea     rcx, [rsp+538h+pExceptionObject]; this
0x1800864ab  mov     dword ptr [rsp+538h+lpOverlapped], 14Bh; unsigned int
0x1800864b3  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800864b8  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800864bf  lea     rcx, [rsp+538h+pExceptionObject]; pExceptionObject
0x1800864c4  call    _CxxThrowException_0
0x1800864ca  xor     edx, edx; Val
0x1800864cc  lea     rcx, [rsp+538h+var_438]; void *
0x1800864d4  mov     r8d, 400h; Size
0x1800864da  call    memset_0
0x1800864df  mov     r9d, ebp
0x1800864e2  lea     r8, aCallToWritefil; "Call to ::WriteFile failed with HResult"...
0x1800864e9  mov     edx, 200h; unsigned __int64
0x1800864ee  lea     rcx, [rsp+538h+var_438]; wchar_t *
0x1800864f6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800864fb  lea     rax, [rsp+538h+var_438]
0x180086503  mov     [rsp+538h+var_508], rax; struct win_musl::TStringEllipseBase *
0x180086508  lea     r9, word_180139126
0x18008650f  mov     [rsp+538h+var_510], ebp; unsigned int
0x180086513  lea     r8, aNoFilename; "(no filename)"
0x18008651a  lea     rcx, [rsp+538h+pExceptionObject]; this
0x18008651f  mov     dword ptr [rsp+538h+lpOverlapped], 147h; unsigned int
0x180086527  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18008652c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180086533  lea     rcx, [rsp+538h+pExceptionObject]; pExceptionObject
0x180086538  call    _CxxThrowException_0
0x18008653e  mov     rcx, rdi
0x180086541  call    ?clear@?$list@V?$scope@PEAUBufferObject@DataBuffer@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$allocator@V?$scope@PEAUBufferObject@DataBuffer@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@QEAAXXZ; std::list<win_scope::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>>>::clear(void)
0x180086546  mov     rcx, [rsp+538h+var_38]
0x18008654e  xor     rcx, rsp; StackCookie
0x180086551  call    __security_check_cookie
0x180086556  add     rsp, 518h
0x18008655d  pop     rdi
0x18008655e  pop     rsi
0x18008655f  pop     rbp
0x180086560  pop     rbx
0x180086561  retn
```
