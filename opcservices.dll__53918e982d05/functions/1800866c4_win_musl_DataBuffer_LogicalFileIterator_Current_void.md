# win_musl::DataBuffer::LogicalFileIterator::Current(void)

- ea: `0x1800866c4`
- end: `0x18008689f`
- name: `?Current@LogicalFileIterator@DataBuffer@win_musl@@QEAA?AU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@XZ`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180035a70`

## callees

- `0x180012468`
- `0x18002db70`
- `0x1800866c4`
- `0x180086cec`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18008672f`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18008672f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800867d4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800867d4`

## string_xrefs

- `0x180086756`: `Call to ::SetFilePointerEx failed with HResult 0x%X.`
- `0x1800867fb`: `Call to ::ReadFile failed with HResult 0x%X.`

## pseudocode

```c
_QWORD *__fastcall win_musl::DataBuffer::LogicalFileIterator::Current(__int64 a1, _QWORD *a2)
{
  LARGE_INTEGER v4; // rdx
  void *v5; // rcx
  unsigned int v6; // eax
  int v7; // edx
  signed int v8; // esi
  __int64 v9; // r8
  void *v10; // rdx
  DWORD v11; // r8d
  unsigned int File; // eax
  int v13; // edx
  signed int v14; // esi
  LARGE_INTEGER NewFilePointer[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v18[512]; // [rsp+F0h] [rbp-10h] BYREF

  v4 = *(LARGE_INTEGER *)(a1 + 16);
  if ( v4.QuadPart == *(_QWORD *)(a1 + 24) )
  {
    *a2 = 0;
    a2[1] = 0;
  }
  else
  {
    if ( *(_QWORD *)(a1 + 32) != v4.QuadPart )
    {
      v5 = *(void **)(a1 + 8);
      NewFilePointer[0].QuadPart = 0;
      v6 = SetFilePointerEx(v5, v4, NewFilePointer, 0);
      v8 = win_musl::HResultFromBool((win_musl *)v6, v7);
      if ( v8 < 0 )
      {
        memset_0(v18, 0, sizeof(v18));
        StringCchPrintfW(v18, 0x200u, L"Call to ::SetFilePointerEx failed with HResult 0x%X.", (unsigned int)v8);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x31Cu,
          v8,
          (struct win_musl::TStringEllipseBase *)v18);
        throw (SplException::THResultException *)pExceptionObject;
      }
      v9 = *(_QWORD *)(a1 + 48);
      v10 = *(void **)(v9 + 8);
      if ( v10 )
        v11 = *(_QWORD *)(v9 + 16) - (_DWORD)v10;
      else
        v11 = 0;
      File = ReadFile(*(HANDLE *)(a1 + 8), v10, v11, (LPDWORD)(a1 + 56), 0);
      v14 = win_musl::HResultFromBool((win_musl *)File, v13);
      if ( v14 < 0 )
      {
        memset_0(v18, 0, sizeof(v18));
        StringCchPrintfW(v18, 0x200u, L"Call to ::ReadFile failed with HResult 0x%X.", (unsigned int)v14);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x326u,
          v14,
          (struct win_musl::TStringEllipseBase *)v18);
        throw (SplException::THResultException *)pExceptionObject;
      }
      *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 16);
    }
    NewFilePointer[0].QuadPart = *(unsigned int *)(a1 + 56);
    NewFilePointer[1] = *(LARGE_INTEGER *)(*(_QWORD *)(a1 + 48) + 8LL);
    *(_OWORD *)a2 = *(_OWORD *)&NewFilePointer[0].LowPart;
  }
  return a2;
}

```

## disassembly

```asm
0x1800866c4  mov     [rsp-8+arg_10], rbx
0x1800866c9  push    rbp
0x1800866ca  push    rsi
0x1800866cb  push    rdi
0x1800866cc  lea     rbp, [rsp-400h]
0x1800866d4  sub     rsp, 500h
0x1800866db  mov     rax, cs:__security_cookie
0x1800866e2  xor     rax, rsp
0x1800866e5  mov     [rbp+410h+var_20], rax
0x1800866ec  mov     rdi, rdx
0x1800866ef  mov     rbx, rcx
0x1800866f2  mov     rdx, [rcx+10h]; liDistanceToMove
0x1800866f6  cmp     rdx, [rcx+18h]
0x1800866fa  jnz     short loc_180086710
0x1800866fc  mov     qword ptr [rdi], 0
0x180086703  mov     qword ptr [rdi+8], 0
0x18008670b  jmp     loc_18008687A
0x180086710  cmp     [rcx+20h], rdx
0x180086714  jz      loc_180086857
0x18008671a  mov     rcx, [rcx+8]; hFile
0x18008671e  lea     r8, [rsp+510h+NewFilePointer]; lpNewFilePointer
0x180086723  xor     r9d, r9d; dwMoveMethod
0x180086726  mov     qword ptr [rsp+510h+NewFilePointer], 0
0x18008672f  call    cs:__imp_SetFilePointerEx
0x180086735  mov     ecx, eax; this
0x180086737  call    ?HResultFromBool@win_musl@@YAJH@Z; win_musl::HResultFromBool(int)
0x18008673c  mov     esi, eax
0x18008673e  test    eax, eax
0x180086740  jns     short loc_1800867AA
0x180086742  xor     edx, edx; Val
0x180086744  lea     rcx, [rbp+410h+var_420]; void *
0x180086748  mov     r8d, 400h; Size
0x18008674e  call    memset_0
0x180086753  mov     r9d, esi
0x180086756  lea     r8, aCallToSetfilep; "Call to ::SetFilePointerEx failed with "...
0x18008675d  mov     edx, 200h; unsigned __int64
0x180086762  lea     rcx, [rbp+410h+var_420]; wchar_t *
0x180086766  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008676b  lea     rax, [rbp+410h+var_420]
0x18008676f  mov     [rsp+510h+var_4E0], rax; struct win_musl::TStringEllipseBase *
0x180086774  lea     r9, word_180139126
0x18008677b  mov     [rsp+510h+var_4E8], esi; unsigned int
0x18008677f  lea     r8, aNoFilename; "(no filename)"
0x180086786  lea     rcx, [rsp+510h+pExceptionObject]; this
0x18008678b  mov     dword ptr [rsp+510h+lpOverlapped], 31Ch; unsigned int
0x180086793  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180086798  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18008679f  lea     rcx, [rsp+510h+pExceptionObject]; pExceptionObject
0x1800867a4  call    _CxxThrowException_0
0x1800867aa  mov     r8, [rbx+30h]
0x1800867ae  mov     rdx, [r8+8]; lpBuffer
0x1800867b2  test    rdx, rdx
0x1800867b5  jnz     short loc_1800867BC
0x1800867b7  xor     r8d, r8d
0x1800867ba  jmp     short loc_1800867C3
0x1800867bc  mov     r8, [r8+10h]
0x1800867c0  sub     r8, rdx; nNumberOfBytesToRead
0x1800867c3  mov     rcx, [rbx+8]; hFile
0x1800867c7  lea     r9, [rbx+38h]; lpNumberOfBytesRead
0x1800867cb  mov     [rsp+510h+lpOverlapped], 0; lpOverlapped
0x1800867d4  call    cs:__imp_ReadFile
0x1800867da  mov     ecx, eax; this
0x1800867dc  call    ?HResultFromBool@win_musl@@YAJH@Z; win_musl::HResultFromBool(int)
0x1800867e1  mov     esi, eax
0x1800867e3  test    eax, eax
0x1800867e5  jns     short loc_18008684F
0x1800867e7  xor     edx, edx; Val
0x1800867e9  lea     rcx, [rbp+410h+var_420]; void *
0x1800867ed  mov     r8d, 400h; Size
0x1800867f3  call    memset_0
0x1800867f8  mov     r9d, esi
0x1800867fb  lea     r8, aCallToReadfile; "Call to ::ReadFile failed with HResult "...
0x180086802  mov     edx, 200h; unsigned __int64
0x180086807  lea     rcx, [rbp+410h+var_420]; wchar_t *
0x18008680b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180086810  lea     rax, [rbp+410h+var_420]
0x180086814  mov     [rsp+510h+var_4E0], rax; struct win_musl::TStringEllipseBase *
0x180086819  lea     r9, word_180139126
0x180086820  mov     [rsp+510h+var_4E8], esi; unsigned int
0x180086824  lea     r8, aNoFilename; "(no filename)"
0x18008682b  lea     rcx, [rsp+510h+pExceptionObject]; this
0x180086830  mov     dword ptr [rsp+510h+lpOverlapped], 326h; unsigned int
0x180086838  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18008683d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180086844  lea     rcx, [rsp+510h+pExceptionObject]; pExceptionObject
0x180086849  call    _CxxThrowException_0
0x18008684f  mov     rax, [rbx+10h]
0x180086853  mov     [rbx+20h], rax
0x180086857  mov     eax, [rbx+38h]
0x18008685a  mov     dword ptr [rsp+510h+NewFilePointer], eax
0x18008685e  xor     eax, eax
0x180086860  mov     dword ptr [rsp+510h+NewFilePointer+4], eax
0x180086864  mov     rax, [rbx+30h]
0x180086868  mov     rcx, [rax+8]
0x18008686c  mov     qword ptr [rsp+510h+NewFilePointer+8], rcx
0x180086871  movups  xmm0, xmmword ptr [rsp+510h+NewFilePointer]
0x180086876  movdqu  xmmword ptr [rdi], xmm0
0x18008687a  mov     rax, rdi
0x18008687d  mov     rcx, [rbp+410h+var_20]
0x180086884  xor     rcx, rsp; StackCookie
0x180086887  call    __security_check_cookie
0x18008688c  mov     rbx, [rsp+510h+arg_10]
0x180086894  add     rsp, 500h
0x18008689b  pop     rdi
0x18008689c  pop     rsi
0x18008689d  pop     rbp
0x18008689e  retn
```
