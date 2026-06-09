# UtilGetWindowsDirectory(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x18003b2e8`
- end: `0x18003b3a1`
- name: `?UtilGetWindowsDirectory@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001f0c0`
- `0x18002a28c`

## callees

- `0x180002890`
- `0x180007118`
- `0x180009e04`
- `0x18000be60`
- `0x18003b2e8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18003b314`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18003b314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b364`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b364`

## pseudocode

```c
signed int __fastcall UtilGetWindowsDirectory(__int64 a1)
{
  UINT WindowsDirectoryW; // eax
  UINT v3; // edi
  signed int result; // eax
  WCHAR Buffer[64]; // [rsp+20h] [rbp-98h] BYREF

  WindowsDirectoryW = GetWindowsDirectoryW(Buffer, 0x40u);
  v3 = WindowsDirectoryW;
  if ( WindowsDirectoryW - 1 > 0x3F )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result >= 0 )
      return -2147467259;
  }
  else
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(a1, WindowsDirectoryW + 1);
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                            a1,
                            Buffer,
                            v3) )
      return (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                a1,
                                92) == 0
           ? 0x8007000E
           : 0;
    else
      return -2147024882;
  }
  return result;
}

```

## disassembly

```asm
0x18003b2e8  mov     [rsp+arg_8], rbx
0x18003b2ed  push    rdi
0x18003b2ee  sub     rsp, 0B0h
0x18003b2f5  mov     rax, cs:__security_cookie
0x18003b2fc  xor     rax, rsp
0x18003b2ff  mov     [rsp+0B8h+var_18], rax
0x18003b307  mov     rbx, rcx
0x18003b30a  mov     edx, 40h ; '@'; uSize
0x18003b30f  lea     rcx, [rsp+0B8h+Buffer]; lpBuffer
0x18003b314  call    cs:__imp_GetWindowsDirectoryW
0x18003b31a  mov     edi, eax
0x18003b31c  lea     ecx, [rdi-1]
0x18003b31f  cmp     ecx, 3Fh ; '?'
0x18003b322  ja      short loc_18003B364
0x18003b324  lea     edx, [rdi+1]
0x18003b327  mov     rcx, rbx
0x18003b32a  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x18003b32f  mov     r8d, edi
0x18003b332  lea     rdx, [rsp+0B8h+Buffer]
0x18003b337  mov     rcx, rbx
0x18003b33a  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18003b33f  test    al, al
0x18003b341  jz      short loc_18003B35D
0x18003b343  mov     edx, 5Ch ; '\'
0x18003b348  mov     rcx, rbx
0x18003b34b  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18003b350  neg     al
0x18003b352  sbb     eax, eax
0x18003b354  not     eax
0x18003b356  and     eax, 8007000Eh
0x18003b35b  jmp     short loc_18003B380
0x18003b35d  mov     eax, 8007000Eh
0x18003b362  jmp     short loc_18003B380
0x18003b364  call    cs:__imp_GetLastError
0x18003b36a  test    eax, eax
0x18003b36c  jle     short loc_18003B376
0x18003b36e  movzx   eax, ax
0x18003b371  or      eax, 80070000h
0x18003b376  test    eax, eax
0x18003b378  mov     ecx, 80004005h
0x18003b37d  cmovns  eax, ecx
0x18003b380  mov     rcx, [rsp+0B8h+var_18]
0x18003b388  xor     rcx, rsp; StackCookie
0x18003b38b  call    __security_check_cookie
0x18003b390  mov     rbx, [rsp+0B8h+arg_8]
0x18003b398  add     rsp, 0B0h
0x18003b39f  pop     rdi
0x18003b3a0  retn
```
