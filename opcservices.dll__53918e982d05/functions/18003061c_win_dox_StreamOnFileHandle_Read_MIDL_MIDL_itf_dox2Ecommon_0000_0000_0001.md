# win_dox::StreamOnFileHandle::Read(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)

- ea: `0x18003061c`
- end: `0x180030854`
- name: `?Read@StreamOnFileHandle@win_dox@@QEAAIU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z`
- size: `568`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800302c0`
- `0x180058e5c`
- `0x1800b6090`
- `0x1800b6508`

## callees

- `0x180011fe8`
- `0x1800120a4`
- `0x1800124f4`
- `0x18002db70`
- `0x18003061c`
- `0x18003085c`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800307ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800307ab`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800306da`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800306da`

## string_xrefs

- `0x18003071d`: `ReadFileEx failed`
- `0x180030767`: `Access mode for StreamOnFileHandle does not permit Read.`
- `0x1800307b8`: `File must not be opened with overlapped flag.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::StreamOnFileHandle::Read(__int64 *a1, LPVOID *a2)
{
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rax
  DWORD v8; // ecx
  signed int LastError; // eax
  DWORD NumberOfBytesRead[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 Overlapped; // [rsp+50h] [rbp-B8h]
  struct _OVERLAPPED Overlapped_8; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v14[2]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v15; // [rsp+88h] [rbp-80h]
  _BYTE v16[64]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+E8h] [rbp-20h] BYREF

  Overlapped = -2;
  if ( *((_DWORD *)a1 + 6) > 1u )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x4Au,
      0x80004001,
      (struct win_musl::TStringEllipseBase *)L"Access mode for StreamOnFileHandle does not permit Read.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  NumberOfBytesRead[0] = 0;
  v4 = *a1;
  v14[0] = 0;
  v14[1] = 0;
  v15 = v4;
  *(_OWORD *)&Overlapped_8.Internal = 0u;
  *(_OWORD *)&Overlapped_8.Offset = v4;
  v5 = win_dox::StreamOnFileHandle::Size((win_dox::StreamOnFileHandle *)a1);
  if ( v5 <= *a1 )
  {
    return NumberOfBytesRead[0];
  }
  else
  {
    v6 = *(unsigned int *)a2;
    v7 = v5 - *a1;
    if ( v6 >= v7 )
      LODWORD(v6) = v7;
    if ( !ReadFile((HANDLE)a1[2], a2[1], v6, NumberOfBytesRead, &Overlapped_8) )
    {
      LastError = GetLastError();
      if ( LastError == 997 )
      {
        win_musl::DebugLogHelper(
          "(no filename)",
          &word_180139126,
          121,
          1024,
          -2147418113,
          L"File must not be opened with overlapped flag.");
        std::string::string(v14, "Program has entered an unexpected state");
        std::logic_error::logic_error(v16, v14);
        throw (std::logic_error *)v16;
      }
      if ( LastError != 234 && LastError != 109 && LastError != 38 )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x80u,
          LastError,
          (struct win_musl::TStringEllipseBase *)L"ReadFileEx failed");
        throw (SplException::THResultException *)pExceptionObject;
      }
    }
    v8 = NumberOfBytesRead[0];
    *a1 += NumberOfBytesRead[0];
  }
  return v8;
}

```

## disassembly

```asm
0x18003061c  mov     rax, rsp
0x18003061f  push    rbp
0x180030620  lea     rbp, [rax-98h]
0x180030627  sub     rsp, 190h
0x18003062e  mov     [rsp+190h+Overlapped.Internal], 0FFFFFFFFFFFFFFFEh
0x180030637  mov     [rax+18h], rbx
0x18003063b  mov     [rax+20h], rdi
0x18003063f  mov     rax, cs:__security_cookie
0x180030646  xor     rax, rsp
0x180030649  mov     [rbp+90h+var_10], rax
0x180030650  mov     rdi, rdx
0x180030653  mov     rbx, rcx
0x180030656  cmp     dword ptr [rcx+18h], 1
0x18003065a  jnz     loc_18003075D
0x180030660  mov     [rsp+190h+NumberOfBytesRead], 0
0x180030668  mov     rcx, [rcx]
0x18003066b  mov     qword ptr [rsp+190h+var_128+8], 0
0x180030674  mov     [rsp+190h+var_118], 0
0x18003067d  mov     qword ptr [rbp+90h+var_110+8], 0
0x180030685  mov     rax, rcx
0x180030688  shr     rax, 20h
0x18003068c  mov     dword ptr [rbp+90h+var_110], ecx
0x18003068f  mov     dword ptr [rbp+90h+var_110+4], eax
0x180030692  movups  xmm0, [rsp+190h+var_128+8]
0x180030697  movups  xmmword ptr [rsp+190h+Overlapped.InternalHigh], xmm0
0x18003069c  movups  xmm1, [rbp+90h+var_110]
0x1800306a0  movups  xmmword ptr [rsp+190h+Overlapped.hEvent], xmm1
0x1800306a5  mov     rcx, rbx; this
0x1800306a8  call    ?Size@StreamOnFileHandle@win_dox@@IEAA_KXZ; win_dox::StreamOnFileHandle::Size(void)
0x1800306ad  cmp     rax, [rbx]
0x1800306b0  jbe     loc_18003084B
0x1800306b6  mov     r8d, [rdi]
0x1800306b9  sub     rax, [rbx]
0x1800306bc  cmp     r8, rax
0x1800306bf  cmovnb  r8d, eax; nNumberOfBytesToRead
0x1800306c3  lea     rax, [rsp+190h+Overlapped.InternalHigh]
0x1800306c8  mov     [rsp+190h+lpOverlapped], rax; lpOverlapped
0x1800306cd  lea     r9, [rsp+190h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800306d2  mov     rdx, [rdi+8]; lpBuffer
0x1800306d6  mov     rcx, [rbx+10h]; hFile
0x1800306da  call    cs:__imp_ReadFile
0x1800306e0  test    eax, eax
0x1800306e2  jz      loc_1800307AB
0x1800306e8  mov     ecx, [rsp+190h+NumberOfBytesRead]
0x1800306ec  add     [rbx], rcx
0x1800306ef  mov     eax, ecx
0x1800306f1  mov     rcx, [rbp+90h+var_10]
0x1800306f8  xor     rcx, rsp; StackCookie
0x1800306fb  call    __security_check_cookie
0x180030700  lea     r11, [rsp+190h+var_s0]
0x180030708  mov     rbx, [r11+20h]
0x18003070c  mov     rdi, [r11+28h]
0x180030710  mov     rsp, r11
0x180030713  pop     rbp
0x180030714  retn
0x180030715  test    eax, eax
0x180030717  jg      loc_18003083E
0x18003071d  lea     rcx, aReadfileexFail; "ReadFileEx failed"
0x180030724  mov     [rsp+190h+var_160], rcx; struct win_musl::TStringEllipseBase *
0x180030729  mov     [rsp+190h+var_168], eax; unsigned int
0x18003072d  mov     dword ptr [rsp+190h+lpOverlapped], 80h; unsigned int
0x180030735  lea     r9, word_180139126
0x18003073c  lea     r8, aNoFilename; "(no filename)"
0x180030743  lea     rcx, [rbp+90h+pExceptionObject]; this
0x180030747  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18003074c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180030753  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x180030757  call    _CxxThrowException_0
0x18003075d  cmp     dword ptr [rcx+18h], 0
0x180030761  jz      loc_180030660
0x180030767  lea     rax, aAccessModeForS; "Access mode for StreamOnFileHandle does"...
0x18003076e  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x180030773  mov     [rsp+190h+var_168], 80004001h; unsigned int
0x18003077b  mov     dword ptr [rsp+190h+lpOverlapped], 4Ah ; 'J'; unsigned int
0x180030783  lea     r9, word_180139126
0x18003078a  lea     r8, aNoFilename; "(no filename)"
0x180030791  lea     rcx, [rbp+90h+pExceptionObject]; this
0x180030795  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18003079a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800307a1  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800307a5  call    _CxxThrowException_0
0x1800307ab  call    cs:__imp_GetLastError
0x1800307b1  cmp     eax, 3E5h
0x1800307b6  jnz     short loc_18003081C
0x1800307b8  lea     rax, aFileMustNotBeO; "File must not be opened with overlapped"...
0x1800307bf  mov     qword ptr [rsp+190h+var_168], rax
0x1800307c4  mov     dword ptr [rsp+190h+lpOverlapped], 8000FFFFh
0x1800307cc  mov     r9d, 400h
0x1800307d2  mov     r8d, 79h ; 'y'
0x1800307d8  lea     rdx, word_180139126
0x1800307df  lea     rcx, aNoFilename; "(no filename)"
0x1800307e6  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x1800307eb  lea     rdx, aProgramHasEnte; "Program has entered an unexpected state"
0x1800307f2  lea     rcx, [rsp+190h+var_128+8]
0x1800307f7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x1800307fc  nop
0x1800307fd  lea     rdx, [rsp+190h+var_128+8]
0x180030802  lea     rcx, [rbp+90h+var_F0]
0x180030806  call    ??0logic_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::logic_error::logic_error(std::string const &)
0x18003080b  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x180030812  lea     rcx, [rbp+90h+var_F0]; pExceptionObject
0x180030816  call    _CxxThrowException_0
0x18003081c  cmp     eax, 0EAh
0x180030821  jz      loc_1800306E8
0x180030827  cmp     eax, 6Dh ; 'm'
0x18003082a  jz      loc_1800306E8
0x180030830  cmp     eax, 26h ; '&'
0x180030833  jz      loc_1800306E8
0x180030839  jmp     loc_180030715
0x18003083e  movzx   eax, ax
0x180030841  or      eax, 80070000h
0x180030846  jmp     loc_18003071D
0x18003084b  mov     ecx, [rsp+190h+NumberOfBytesRead]
0x18003084f  jmp     loc_1800306EF
```
