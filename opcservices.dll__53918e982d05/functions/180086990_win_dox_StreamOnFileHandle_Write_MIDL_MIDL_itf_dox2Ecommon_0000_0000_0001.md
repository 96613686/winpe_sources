# win_dox::StreamOnFileHandle::Write(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)

- ea: `0x180086990`
- end: `0x180086bae`
- name: `?Write@StreamOnFileHandle@win_dox@@QEAAIU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z`
- size: `542`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180086910`
- `0x1800e0460`
- `0x1800f8130`

## callees

- `0x180011fe8`
- `0x1800120a4`
- `0x1800124f4`
- `0x18002db70`
- `0x180086990`
- `0x180086bb4`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086b0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086b0e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180086a3f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180086a3f`

## string_xrefs

- `0x180086a80`: `WriteFile failed`
- `0x180086b1b`: `File must not be opened with overlapped flag.`
- `0x180086aca`: `Access mode for StreamOnFileHandle does not permit Write.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::StreamOnFileHandle::Write(__int64 a1, __int64 a2, unsigned __int64 a3, unsigned int a4)
{
  void *v6; // rcx
  __int64 result; // rax
  signed int LastError; // eax
  DWORD NumberOfBytesWritten[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 Overlapped; // [rsp+50h] [rbp-B8h]
  struct _OVERLAPPED Overlapped_8; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v12[2]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v13; // [rsp+88h] [rbp-80h]
  _BYTE v14[64]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+E8h] [rbp-20h] BYREF

  Overlapped = -2;
  if ( *(_DWORD *)(a1 + 24) != 1 && *(_DWORD *)(a1 + 24) != 2 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x92u,
      0x80004001,
      (struct win_musl::TStringEllipseBase *)L"Access mode for StreamOnFileHandle does not permit Write.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  win_dox::SetFilePosition(*(win_dox **)(a1 + 16), *(void **)a1, a3, a4);
  NumberOfBytesWritten[0] = 0;
  v6 = *(void **)a1;
  v12[0] = 0;
  v12[1] = 0;
  v13 = (unsigned __int64)v6;
  *(_OWORD *)&Overlapped_8.Internal = 0u;
  *(_OWORD *)&Overlapped_8.Offset = (unsigned __int64)v6;
  if ( !WriteFile(*(HANDLE *)(a1 + 16), *(LPCVOID *)(a2 + 8), *(_DWORD *)a2, NumberOfBytesWritten, &Overlapped_8) )
  {
    LastError = GetLastError();
    if ( LastError == 997 )
    {
      win_musl::DebugLogHelper(
        "(no filename)",
        &word_180139126,
        173,
        1024,
        -2147418113,
        L"File must not be opened with overlapped flag.");
      std::string::string(v12, "Program has entered an unexpected state");
      std::logic_error::logic_error(v14, v12);
      throw (std::logic_error *)v14;
    }
    if ( LastError != 234 && LastError != 109 && LastError != 38 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xB4u,
        LastError,
        (struct win_musl::TStringEllipseBase *)L"WriteFile failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  result = NumberOfBytesWritten[0];
  *(_QWORD *)a1 += NumberOfBytesWritten[0];
  return result;
}

```

## disassembly

```asm
0x180086990  mov     rax, rsp
0x180086993  push    rbp
0x180086994  lea     rbp, [rax-98h]
0x18008699b  sub     rsp, 190h
0x1800869a2  mov     [rsp+190h+Overlapped.Internal], 0FFFFFFFFFFFFFFFEh
0x1800869ab  mov     [rax+18h], rbx
0x1800869af  mov     [rax+20h], rdi
0x1800869b3  mov     rax, cs:__security_cookie
0x1800869ba  xor     rax, rsp
0x1800869bd  mov     [rbp+90h+var_10], rax
0x1800869c4  mov     rdi, rdx
0x1800869c7  mov     rbx, rcx
0x1800869ca  cmp     dword ptr [rcx+18h], 1
0x1800869ce  jnz     loc_180086AC0
0x1800869d4  mov     rdx, [rcx]; void *
0x1800869d7  mov     rcx, [rcx+10h]; this
0x1800869db  call    ?SetFilePosition@win_dox@@YA_KPEAX_KK@Z; win_dox::SetFilePosition(void *,unsigned __int64,ulong)
0x1800869e0  mov     [rsp+190h+NumberOfBytesWritten], 0
0x1800869e8  mov     rcx, [rbx]
0x1800869eb  mov     qword ptr [rsp+190h+var_128+8], 0
0x1800869f4  mov     [rsp+190h+var_118], 0
0x1800869fd  mov     qword ptr [rbp+90h+var_110+8], 0
0x180086a05  mov     rax, rcx
0x180086a08  shr     rax, 20h
0x180086a0c  mov     dword ptr [rbp+90h+var_110], ecx
0x180086a0f  mov     dword ptr [rbp+90h+var_110+4], eax
0x180086a12  movups  xmm0, [rsp+190h+var_128+8]
0x180086a17  movups  xmmword ptr [rsp+190h+Overlapped.InternalHigh], xmm0
0x180086a1c  movups  xmm1, [rbp+90h+var_110]
0x180086a20  movups  xmmword ptr [rsp+190h+Overlapped.hEvent], xmm1
0x180086a25  lea     rax, [rsp+190h+Overlapped.InternalHigh]
0x180086a2a  mov     [rsp+190h+lpOverlapped], rax; lpOverlapped
0x180086a2f  lea     r9, [rsp+190h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180086a34  mov     r8d, [rdi]; nNumberOfBytesToWrite
0x180086a37  mov     rdx, [rdi+8]; lpBuffer
0x180086a3b  mov     rcx, [rbx+10h]; hFile
0x180086a3f  call    cs:__imp_WriteFile
0x180086a45  test    eax, eax
0x180086a47  jz      loc_180086B0E
0x180086a4d  mov     eax, [rsp+190h+NumberOfBytesWritten]
0x180086a51  add     [rbx], rax
0x180086a54  mov     rcx, [rbp+90h+var_10]
0x180086a5b  xor     rcx, rsp; StackCookie
0x180086a5e  call    __security_check_cookie
0x180086a63  lea     r11, [rsp+190h+var_s0]
0x180086a6b  mov     rbx, [r11+20h]
0x180086a6f  mov     rdi, [r11+28h]
0x180086a73  mov     rsp, r11
0x180086a76  pop     rbp
0x180086a77  retn
0x180086a78  test    eax, eax
0x180086a7a  jg      loc_180086BA1
0x180086a80  lea     rcx, aWritefileFaile_0; "WriteFile failed"
0x180086a87  mov     [rsp+190h+var_160], rcx; struct win_musl::TStringEllipseBase *
0x180086a8c  mov     [rsp+190h+var_168], eax; unsigned int
0x180086a90  mov     dword ptr [rsp+190h+lpOverlapped], 0B4h; unsigned int
0x180086a98  lea     r9, word_180139126
0x180086a9f  lea     r8, aNoFilename; "(no filename)"
0x180086aa6  lea     rcx, [rbp+90h+pExceptionObject]; this
0x180086aaa  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180086aaf  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180086ab6  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x180086aba  call    _CxxThrowException_0
0x180086ac0  cmp     dword ptr [rcx+18h], 2
0x180086ac4  jz      loc_1800869D4
0x180086aca  lea     rax, aAccessModeForS_0; "Access mode for StreamOnFileHandle does"...
0x180086ad1  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x180086ad6  mov     [rsp+190h+var_168], 80004001h; unsigned int
0x180086ade  mov     dword ptr [rsp+190h+lpOverlapped], 92h; unsigned int
0x180086ae6  lea     r9, word_180139126
0x180086aed  lea     r8, aNoFilename; "(no filename)"
0x180086af4  lea     rcx, [rbp+90h+pExceptionObject]; this
0x180086af8  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180086afd  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180086b04  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x180086b08  call    _CxxThrowException_0
0x180086b0e  call    cs:__imp_GetLastError
0x180086b14  cmp     eax, 3E5h
0x180086b19  jnz     short loc_180086B7F
0x180086b1b  lea     rax, aFileMustNotBeO; "File must not be opened with overlapped"...
0x180086b22  mov     qword ptr [rsp+190h+var_168], rax
0x180086b27  mov     dword ptr [rsp+190h+lpOverlapped], 8000FFFFh
0x180086b2f  mov     r9d, 400h
0x180086b35  mov     r8d, 0ADh
0x180086b3b  lea     rdx, word_180139126
0x180086b42  lea     rcx, aNoFilename; "(no filename)"
0x180086b49  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x180086b4e  lea     rdx, aProgramHasEnte; "Program has entered an unexpected state"
0x180086b55  lea     rcx, [rsp+190h+var_128+8]
0x180086b5a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x180086b5f  nop
0x180086b60  lea     rdx, [rsp+190h+var_128+8]
0x180086b65  lea     rcx, [rbp+90h+var_F0]
0x180086b69  call    ??0logic_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::logic_error::logic_error(std::string const &)
0x180086b6e  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x180086b75  lea     rcx, [rbp+90h+var_F0]; pExceptionObject
0x180086b79  call    _CxxThrowException_0
0x180086b7f  cmp     eax, 0EAh
0x180086b84  jz      loc_180086A4D
0x180086b8a  cmp     eax, 6Dh ; 'm'
0x180086b8d  jz      loc_180086A4D
0x180086b93  cmp     eax, 26h ; '&'
0x180086b96  jz      loc_180086A4D
0x180086b9c  jmp     loc_180086A78
0x180086ba1  movzx   eax, ax
0x180086ba4  or      eax, 80070000h
0x180086ba9  jmp     loc_180086A80
```
