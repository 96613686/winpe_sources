# UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)

- ea: `0x180016f80`
- end: `0x180017099`
- name: `?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z`
- size: `281`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180016c20`
- `0x180019160`
- `0x18001f0c0`
- `0x18002fe98`

## callees

- `0x180002890`
- `0x180007118`
- `0x180009e04`
- `0x18000be60`
- `0x180016f80`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016fb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016fb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016fc8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016fc8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180016ff8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180016ff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017058`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x180016fe6`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x180016fe6`

## string_xrefs

- `0x180016fc1`: `GetSystemWow64Directory2W`
- `0x180016fb1`: `api-ms-win-core-wow64-l1-1-1.dll`

## pseudocode

```c
signed int __fastcall UtilGetSystemDirectory2(__int64 a1, unsigned __int16 a2)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  UINT SystemWow64DirectoryW; // eax
  unsigned __int64 v7; // rbx
  signed int result; // eax
  WCHAR Buffer[64]; // [rsp+20h] [rbp-98h] BYREF

  if ( a2 )
  {
    ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-wow64-l1-1-1.dll");
    ProcAddress = GetProcAddress(ModuleHandleW, "GetSystemWow64Directory2W");
    if ( ProcAddress )
      SystemWow64DirectoryW = ((__int64 (__fastcall *)(WCHAR *, __int64, _QWORD))ProcAddress)(Buffer, 64, a2);
    else
      SystemWow64DirectoryW = GetSystemWow64DirectoryW(Buffer, 0x40u);
  }
  else
  {
    SystemWow64DirectoryW = GetSystemDirectoryW(Buffer, 0x40u);
  }
  if ( SystemWow64DirectoryW - 1 > 0x3F )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result >= 0 )
      return -2147467259;
  }
  else
  {
    v7 = -1;
    do
      ++v7;
    while ( Buffer[v7] );
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(a1, v7 + 1);
    if ( utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a1, Buffer, v7) )
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
0x180016f80  mov     [rsp+arg_10], rbx
0x180016f85  mov     [rsp+arg_18], rsi
0x180016f8a  push    rdi
0x180016f8b  sub     rsp, 0B0h
0x180016f92  mov     rax, cs:__security_cookie
0x180016f99  xor     rax, rsp
0x180016f9c  mov     [rsp+0B8h+var_18], rax
0x180016fa4  xor     esi, esi
0x180016fa6  movzx   ebx, dx
0x180016fa9  mov     rdi, rcx
0x180016fac  test    dx, dx
0x180016faf  jz      short loc_180016FEE
0x180016fb1  lea     rcx, aApiMsWinCoreWo_1; "api-ms-win-core-wow64-l1-1-1.dll"
0x180016fb8  call    cs:__imp_GetModuleHandleW
0x180016fbe  mov     rcx, rax; hModule
0x180016fc1  lea     rdx, aGetsystemwow64; "GetSystemWow64Directory2W"
0x180016fc8  call    cs:__imp_GetProcAddress
0x180016fce  lea     edx, [rsi+40h]; uSize
0x180016fd1  lea     rcx, [rsp+0B8h+Buffer]; lpBuffer
0x180016fd6  test    rax, rax
0x180016fd9  jz      short loc_180016FE6
0x180016fdb  movzx   r8d, bx
0x180016fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fe4  jmp     short loc_180016FFE
0x180016fe6  call    cs:__imp_GetSystemWow64DirectoryW
0x180016fec  jmp     short loc_180016FFE
0x180016fee  mov     edx, 40h ; '@'; uSize
0x180016ff3  lea     rcx, [rsp+0B8h+Buffer]; lpBuffer
0x180016ff8  call    cs:__imp_GetSystemDirectoryW
0x180016ffe  dec     eax
0x180017000  cmp     eax, 3Fh ; '?'
0x180017003  ja      short loc_180017058
0x180017005  lea     rax, [rsp+0B8h+Buffer]
0x18001700a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001700e  inc     rbx
0x180017011  cmp     [rax+rbx*2], si
0x180017015  jnz     short loc_18001700E
0x180017017  lea     rdx, [rbx+1]
0x18001701b  mov     rcx, rdi
0x18001701e  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x180017023  mov     r8, rbx
0x180017026  lea     rdx, [rsp+0B8h+Buffer]
0x18001702b  mov     rcx, rdi
0x18001702e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180017033  test    al, al
0x180017035  jz      short loc_180017051
0x180017037  mov     edx, 5Ch ; '\'
0x18001703c  mov     rcx, rdi
0x18001703f  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x180017044  neg     al
0x180017046  sbb     eax, eax
0x180017048  not     eax
0x18001704a  and     eax, 8007000Eh
0x18001704f  jmp     short loc_180017074
0x180017051  mov     eax, 8007000Eh
0x180017056  jmp     short loc_180017074
0x180017058  call    cs:__imp_GetLastError
0x18001705e  test    eax, eax
0x180017060  jle     short loc_18001706A
0x180017062  movzx   eax, ax
0x180017065  or      eax, 80070000h
0x18001706a  test    eax, eax
0x18001706c  mov     ecx, 80004005h
0x180017071  cmovns  eax, ecx
0x180017074  mov     rcx, [rsp+0B8h+var_18]
0x18001707c  xor     rcx, rsp; StackCookie
0x18001707f  call    __security_check_cookie
0x180017084  lea     r11, [rsp+0B8h+var_8]
0x18001708c  mov     rbx, [r11+20h]
0x180017090  mov     rsi, [r11+28h]
0x180017094  mov     rsp, r11
0x180017097  pop     rdi
0x180017098  retn
```
