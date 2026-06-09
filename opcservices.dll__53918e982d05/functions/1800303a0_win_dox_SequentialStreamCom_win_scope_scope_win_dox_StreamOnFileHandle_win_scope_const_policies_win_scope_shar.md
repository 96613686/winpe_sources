# win_dox::SequentialStreamCom<win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>,IStream>::Read_Safe(void *,ulong,ulong *)

- ea: `0x1800303a0`
- end: `0x180030615`
- name: `?Read_Safe@?$SequentialStreamCom@V?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIStream@@@win_dox@@AEAAXPEAXKPEAK@Z`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180030360`

## callees

- `0x180011fe8`
- `0x1800120a4`
- `0x1800124f4`
- `0x18002db70`
- `0x1800303a0`
- `0x18003085c`
- `0x180058f20`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003056c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003056c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003045f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003045f`

## string_xrefs

- `0x1800304a0`: `ReadFileEx failed`
- `0x180030528`: `Access mode for StreamOnFileHandle does not permit Read.`
- `0x180030579`: `File must not be opened with overlapped flag.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall win_dox::SequentialStreamCom<win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>,IStream>::Read_Safe(
        __int64 a1,
        void *a2,
        __int64 a3,
        DWORD *a4)
{
  unsigned __int64 v5; // r14
  __int64 *v7; // rbx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rax
  DWORD v11; // ecx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h]
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v16[3]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v17[64]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+E0h] [rbp-20h] BYREF

  v14 = -2;
  v5 = (unsigned int)a3;
  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 78, L"IStream", L"Read", L"pv", 0);
  DWORD1(v16[0]) = 0;
  v7 = *(__int64 **)(a1 + 16);
  if ( *((_DWORD *)v7 + 6) > 1u )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x4Au,
      0x80004001,
      (struct win_musl::TStringEllipseBase *)L"Access mode for StreamOnFileHandle does not permit Read.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  NumberOfBytesRead = 0;
  v8 = *v7;
  v16[0] = 0u;
  v16[1] = v8;
  *(_OWORD *)&Overlapped.Internal = 0u;
  *(_OWORD *)&Overlapped.Offset = v8;
  v9 = win_dox::StreamOnFileHandle::Size((win_dox::StreamOnFileHandle *)v7);
  if ( v9 <= *v7 )
  {
    v11 = NumberOfBytesRead;
  }
  else
  {
    v10 = v9 - *v7;
    if ( v5 >= v10 )
      LODWORD(v5) = v10;
    LODWORD(v9) = ReadFile((HANDLE)v7[2], a2, v5, &NumberOfBytesRead, &Overlapped);
    if ( !(_DWORD)v9 )
    {
      LODWORD(v9) = GetLastError();
      if ( (_DWORD)v9 == 997 )
      {
        win_musl::DebugLogHelper(
          "(no filename)",
          &word_180139126,
          121,
          1024,
          -2147418113,
          L"File must not be opened with overlapped flag.");
        std::string::string(v16, "Program has entered an unexpected state");
        std::logic_error::logic_error(v17, v16);
        throw (std::logic_error *)v17;
      }
      if ( (_DWORD)v9 != 234 && (_DWORD)v9 != 109 && (_DWORD)v9 != 38 )
      {
        if ( (int)v9 > 0 )
          LODWORD(v9) = (unsigned __int16)v9 | 0x80070000;
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x80u,
          v9,
          (struct win_musl::TStringEllipseBase *)L"ReadFileEx failed");
        throw (SplException::THResultException *)pExceptionObject;
      }
    }
    v11 = NumberOfBytesRead;
    *v7 += NumberOfBytesRead;
  }
  if ( a4 )
    *a4 = v11;
  return v9;
}

```

## disassembly

```asm
0x1800303a0  push    rbp
0x1800303a2  push    rbx
0x1800303a3  push    rsi
0x1800303a4  push    rdi
0x1800303a5  push    r14
0x1800303a7  lea     rbp, [rsp-90h]
0x1800303af  sub     rsp, 190h
0x1800303b6  mov     [rsp+1B0h+var_168], 0FFFFFFFFFFFFFFFEh
0x1800303bf  mov     rax, cs:__security_cookie
0x1800303c6  xor     rax, rsp
0x1800303c9  mov     [rbp+0B0h+var_30], rax
0x1800303d0  mov     rdi, r9
0x1800303d3  mov     r14d, r8d
0x1800303d6  mov     rsi, rdx
0x1800303d9  test    rdx, rdx
0x1800303dc  jz      loc_1800304E0
0x1800303e2  xor     eax, eax
0x1800303e4  mov     dword ptr [rsp+1B0h+var_140+4], eax
0x1800303e8  mov     rbx, [rcx+10h]
0x1800303ec  cmp     dword ptr [rbx+18h], 1
0x1800303f0  jnz     loc_18003051F
0x1800303f6  mov     [rsp+1B0h+NumberOfBytesRead], eax
0x1800303fa  mov     rcx, [rbx]
0x1800303fd  mov     qword ptr [rsp+1B0h+var_140], rax
0x180030402  mov     qword ptr [rsp+1B0h+var_140+8], rax
0x180030407  mov     qword ptr [rbp+0B0h+var_130+8], rax
0x18003040b  mov     rax, rcx
0x18003040e  shr     rax, 20h
0x180030412  mov     dword ptr [rbp+0B0h+var_130], ecx
0x180030415  mov     dword ptr [rbp+0B0h+var_130+4], eax
0x180030418  movups  xmm0, [rsp+1B0h+var_140]
0x18003041d  movups  xmmword ptr [rsp+1B0h+Overlapped.Internal], xmm0
0x180030422  movups  xmm1, [rbp+0B0h+var_130]
0x180030426  movups  xmmword ptr [rsp+1B0h+Overlapped.10h], xmm1
0x18003042b  mov     rcx, rbx; this
0x18003042e  call    ?Size@StreamOnFileHandle@win_dox@@IEAA_KXZ; win_dox::StreamOnFileHandle::Size(void)
0x180030433  cmp     rax, [rbx]
0x180030436  jbe     loc_18003060C
0x18003043c  sub     rax, [rbx]
0x18003043f  cmp     r14, rax
0x180030442  cmovnb  r14d, eax
0x180030446  lea     rax, [rsp+1B0h+Overlapped]
0x18003044b  mov     [rsp+1B0h+lpOverlapped], rax; lpOverlapped
0x180030450  lea     r9, [rsp+1B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180030455  mov     r8d, r14d; nNumberOfBytesToRead
0x180030458  mov     rdx, rsi; lpBuffer
0x18003045b  mov     rcx, [rbx+10h]; hFile
0x18003045f  call    cs:__imp_ReadFile
0x180030465  test    eax, eax
0x180030467  jz      loc_18003056C
0x18003046d  mov     ecx, [rsp+1B0h+NumberOfBytesRead]
0x180030471  add     [rbx], rcx
0x180030474  test    rdi, rdi
0x180030477  jz      short loc_18003047B
0x180030479  mov     [rdi], ecx
0x18003047b  mov     rcx, [rbp+0B0h+var_30]
0x180030482  xor     rcx, rsp; StackCookie
0x180030485  call    __security_check_cookie
0x18003048a  add     rsp, 190h
0x180030491  pop     r14
0x180030493  pop     rdi
0x180030494  pop     rsi
0x180030495  pop     rbx
0x180030496  pop     rbp
0x180030497  retn
0x180030498  test    eax, eax
0x18003049a  jg      loc_1800305FF
0x1800304a0  lea     rcx, aReadfileexFail; "ReadFileEx failed"
0x1800304a7  mov     [rsp+1B0h+var_180], rcx; struct win_musl::TStringEllipseBase *
0x1800304ac  mov     [rsp+1B0h+var_188], eax; unsigned int
0x1800304b0  mov     dword ptr [rsp+1B0h+lpOverlapped], 80h; unsigned int
0x1800304b8  lea     r9, word_180139126
0x1800304bf  lea     r8, aNoFilename; "(no filename)"
0x1800304c6  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x1800304ca  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800304cf  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800304d6  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x1800304da  call    _CxxThrowException_0
0x1800304e0  mov     [rsp+1B0h+var_178], 0
0x1800304e8  lea     rax, aPv; "pv"
0x1800304ef  mov     [rsp+1B0h+var_180], rax
0x1800304f4  lea     rax, aRead; "Read"
0x1800304fb  mov     qword ptr [rsp+1B0h+var_188], rax
0x180030500  lea     rax, aIstream; "IStream"
0x180030507  mov     [rsp+1B0h+lpOverlapped], rax
0x18003050c  mov     r9d, 4Eh ; 'N'
0x180030512  lea     rdx, aNoFilename; "(no filename)"
0x180030519  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x18003051f  cmp     [rbx+18h], eax
0x180030522  jz      loc_1800303F6
0x180030528  lea     rax, aAccessModeForS; "Access mode for StreamOnFileHandle does"...
0x18003052f  mov     [rsp+1B0h+var_180], rax; struct win_musl::TStringEllipseBase *
0x180030534  mov     [rsp+1B0h+var_188], 80004001h; unsigned int
0x18003053c  mov     dword ptr [rsp+1B0h+lpOverlapped], 4Ah ; 'J'; unsigned int
0x180030544  lea     r9, word_180139126
0x18003054b  lea     r8, aNoFilename; "(no filename)"
0x180030552  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x180030556  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18003055b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180030562  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x180030566  call    _CxxThrowException_0
0x18003056c  call    cs:__imp_GetLastError
0x180030572  cmp     eax, 3E5h
0x180030577  jnz     short loc_1800305DD
0x180030579  lea     rax, aFileMustNotBeO; "File must not be opened with overlapped"...
0x180030580  mov     qword ptr [rsp+1B0h+var_188], rax
0x180030585  mov     dword ptr [rsp+1B0h+lpOverlapped], 8000FFFFh
0x18003058d  mov     r9d, 400h
0x180030593  mov     r8d, 79h ; 'y'
0x180030599  lea     rdx, word_180139126
0x1800305a0  lea     rcx, aNoFilename; "(no filename)"
0x1800305a7  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x1800305ac  lea     rdx, aProgramHasEnte; "Program has entered an unexpected state"
0x1800305b3  lea     rcx, [rsp+1B0h+var_140]
0x1800305b8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x1800305bd  nop
0x1800305be  lea     rdx, [rsp+1B0h+var_140]
0x1800305c3  lea     rcx, [rbp+0B0h+var_110]
0x1800305c7  call    ??0logic_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::logic_error::logic_error(std::string const &)
0x1800305cc  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x1800305d3  lea     rcx, [rbp+0B0h+var_110]; pExceptionObject
0x1800305d7  call    _CxxThrowException_0
0x1800305dd  cmp     eax, 0EAh
0x1800305e2  jz      loc_18003046D
0x1800305e8  cmp     eax, 6Dh ; 'm'
0x1800305eb  jz      loc_18003046D
0x1800305f1  cmp     eax, 26h ; '&'
0x1800305f4  jz      loc_18003046D
0x1800305fa  jmp     loc_180030498
0x1800305ff  movzx   eax, ax
0x180030602  or      eax, 80070000h
0x180030607  jmp     loc_1800304A0
0x18003060c  mov     ecx, [rsp+1B0h+NumberOfBytesRead]
0x180030610  jmp     loc_180030474
```
