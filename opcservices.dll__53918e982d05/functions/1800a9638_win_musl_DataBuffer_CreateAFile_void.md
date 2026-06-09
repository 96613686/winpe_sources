# win_musl::DataBuffer::CreateAFile(void)

- ea: `0x1800a9638`
- end: `0x1800a979f`
- name: `?CreateAFile@DataBuffer@win_musl@@AEAAXXZ`
- size: `359`
- prototype: `void __fastcall(win_musl::DataBuffer *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18008640c`
- `0x180086568`

## callees

- `0x1800147d0`
- `0x18002db70`
- `0x180053328`
- `0x180062410`
- `0x18006554c`
- `0x1800a9638`
- `0x1800ab2a0`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a96d2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a96d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a96ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a96ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall win_musl::DataBuffer::CreateAFile(win_musl::DataBuffer *this)
{
  __int64 TemporaryFileName; // rax
  __int64 v3; // rdx
  const WCHAR **v4; // rbx
  const WCHAR *v5; // rcx
  __int64 FileW; // rax
  void *v7; // rcx
  unsigned int LastErrorAsFailHR; // eax
  _BYTE v9[40]; // [rsp+48h] [rbp-E0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+70h] [rbp-B8h] BYREF

  TemporaryFileName = win_musl::CreateTemporaryFileName(v9);
  std::wstring::assign((char *)this + 24, TemporaryFileName, 0, -1);
  LOBYTE(v3) = 1;
  std::wstring::_Tidy(v9, v3, 0);
  v4 = (const WCHAR **)((char *)this + 32);
  if ( *((_QWORD *)this + 7) < 8u )
    v5 = (const WCHAR *)((char *)this + 32);
  else
    v5 = *v4;
  FileW = (__int64)CreateFileW(v5, 0xC0000000, 7u, 0, 1u, 0xC000100u, 0);
  if ( FileW == -1 )
    FileW = -1;
  v7 = (void *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = FileW;
  if ( v7 != (void *)-1LL )
    CloseHandle(v7);
  if ( *((_QWORD *)this + 8) == -1 )
  {
    LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR((win_musl::detail *)v7);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x170u,
      LastErrorAsFailHR,
      (struct win_musl::TStringEllipseBase *)L"Unspecified error");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
  {
    if ( *((_QWORD *)this + 7) >= 8u )
      v4 = (const WCHAR **)*v4;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_b1a0d9529acd3e179f8746edc331057b_Traceguids, v4);
  }
}

```

## disassembly

```asm
0x1800a9638  mov     rax, rsp
0x1800a963b  push    rdi
0x1800a963c  sub     rsp, 120h
0x1800a9643  mov     [rsp+128h+var_E8], 0FFFFFFFFFFFFFFFEh
0x1800a964c  mov     [rax+10h], rbx
0x1800a9650  mov     [rax+18h], rsi
0x1800a9654  mov     rax, cs:__security_cookie
0x1800a965b  xor     rax, rsp
0x1800a965e  mov     [rsp+128h+var_18], rax
0x1800a9666  mov     rdi, rcx
0x1800a9669  lea     rcx, [rsp+128h+var_E0]
0x1800a966e  call    ?CreateTemporaryFileName@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_musl::CreateTemporaryFileName(void)
0x1800a9673  nop
0x1800a9674  lea     rcx, [rdi+18h]
0x1800a9678  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800a967c  mov     r9, rsi
0x1800a967f  xor     r8d, r8d
0x1800a9682  mov     rdx, rax
0x1800a9685  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800a968a  nop
0x1800a968b  xor     r8d, r8d
0x1800a968e  mov     dl, 1
0x1800a9690  lea     rcx, [rsp+128h+var_E0]
0x1800a9695  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800a969a  lea     rbx, [rdi+20h]
0x1800a969e  cmp     qword ptr [rdi+38h], 8
0x1800a96a3  jb      short loc_1800A96AA
0x1800a96a5  mov     rcx, [rbx]
0x1800a96a8  jmp     short loc_1800A96AD
0x1800a96aa  mov     rcx, rbx; lpFileName
0x1800a96ad  mov     [rsp+128h+hTemplateFile], 0; hTemplateFile
0x1800a96b6  mov     [rsp+128h+dwFlagsAndAttributes], 0C000100h; dwFlagsAndAttributes
0x1800a96be  mov     [rsp+128h+dwCreationDisposition], 1; dwCreationDisposition
0x1800a96c6  xor     r9d, r9d; lpSecurityAttributes
0x1800a96c9  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a96ce  lea     r8d, [r9+7]; dwShareMode
0x1800a96d2  call    cs:__imp_CreateFileW
0x1800a96d8  cmp     rax, rsi
0x1800a96db  cmovz   rax, rsi
0x1800a96df  mov     rcx, [rdi+40h]; hObject
0x1800a96e3  mov     [rdi+40h], rax
0x1800a96e7  cmp     rcx, rsi
0x1800a96ea  jz      short loc_1800A96F2
0x1800a96ec  call    cs:__imp_CloseHandle
0x1800a96f2  cmp     [rdi+40h], rsi
0x1800a96f6  jz      short loc_1800A9758
0x1800a96f8  lea     rax, WPP_GLOBAL_Control
0x1800a96ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9706  cmp     rcx, rax
0x1800a9709  jz      short loc_1800A9733
0x1800a970b  test    byte ptr [rcx+44h], 4
0x1800a970f  jz      short loc_1800A9733
0x1800a9711  cmp     qword ptr [rdi+38h], 8
0x1800a9716  jb      short loc_1800A971B
0x1800a9718  mov     rbx, [rbx]
0x1800a971b  mov     edx, 0Ah
0x1800a9720  mov     r9, rbx
0x1800a9723  lea     r8, WPP_b1a0d9529acd3e179f8746edc331057b_Traceguids
0x1800a972a  mov     rcx, [rcx+38h]
0x1800a972e  call    WPP_SF_S
0x1800a9733  mov     rcx, [rsp+128h+var_18]
0x1800a973b  xor     rcx, rsp; StackCookie
0x1800a973e  call    __security_check_cookie
0x1800a9743  lea     r11, [rsp+128h+var_8]
0x1800a974b  mov     rbx, [r11+18h]
0x1800a974f  mov     rsi, [r11+20h]
0x1800a9753  mov     rsp, r11
0x1800a9756  pop     rdi
0x1800a9757  retn
0x1800a9758  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800a975d  lea     rcx, aUnspecifiedErr; "Unspecified error"
0x1800a9764  mov     [rsp+128h+hTemplateFile], rcx; struct win_musl::TStringEllipseBase *
0x1800a9769  mov     [rsp+128h+dwFlagsAndAttributes], eax; unsigned int
0x1800a976d  mov     [rsp+128h+dwCreationDisposition], 170h; unsigned int
0x1800a9775  lea     r9, word_180139126
0x1800a977c  lea     r8, aNoFilename; "(no filename)"
0x1800a9783  lea     rcx, [rsp+128h+pExceptionObject]; this
0x1800a9788  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a978d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a9794  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x1800a9799  call    _CxxThrowException_0
```
