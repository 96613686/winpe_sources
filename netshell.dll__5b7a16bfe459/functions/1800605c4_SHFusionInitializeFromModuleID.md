# SHFusionInitializeFromModuleID

- ea: `0x1800605c4`
- end: `0x1800606d3`
- name: `SHFusionInitializeFromModuleID`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006043c`

## callees

- `0x18001e1e0`
- `0x1800605c4`
- `0x1800607c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180060641`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180060641`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006062a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006062a`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180060673`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180060673`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180060691`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180060691`

## pseudocode

```c
_BOOL8 SHFusionInitializeFromModuleID()
{
  HMODULE ModuleHandleW; // rbx
  unsigned __int16 v1; // di
  HANDLE v2; // rax
  ACTCTXW pActCtx; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( g_hActCtx != (HANDLE)-1LL )
    return 1;
  ModuleHandleW = hModule;
  v1 = dword_180089D28;
  memset(&pActCtx, 0, sizeof(pActCtx));
  if ( !hModule )
    ModuleHandleW = GetModuleHandleW(0);
  GetModuleFileNameW(ModuleHandleW, Filename, 0x104u);
  pActCtx.lpResourceName = (LPCWSTR)v1;
  pActCtx.cbSize = 56;
  pActCtx.lpSource = Filename;
  pActCtx.dwFlags = 136;
  pActCtx.hModule = ModuleHandleW;
  v2 = CreateActCtxW(&pActCtx);
  if ( v2 != (HANDLE)-1LL )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hActCtx, (signed __int64)v2, -1) != -1 )
      ReleaseActCtx(v2);
    DelayLoadCC();
  }
  return g_hActCtx != (HANDLE)-1LL;
}

```

## disassembly

```asm
0x1800605c4  mov     [rsp-8+arg_0], rbx
0x1800605c9  mov     [rsp-8+arg_8], rdi
0x1800605ce  push    rbp
0x1800605cf  lea     rbp, [rsp-180h]
0x1800605d7  sub     rsp, 280h
0x1800605de  mov     rax, cs:__security_cookie
0x1800605e5  xor     rax, rsp
0x1800605e8  mov     [rbp+180h+var_10], rax
0x1800605ef  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x1800605f7  jnz     loc_1800606AA
0x1800605fd  mov     rbx, cs:hModule
0x180060604  xorps   xmm0, xmm0
0x180060607  mov     edi, cs:dword_180089D28
0x18006060d  xor     eax, eax
0x18006060f  mov     [rsp+280h+pActCtx.hModule], rax
0x180060614  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x180060619  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18006061e  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x180060623  test    rbx, rbx
0x180060626  jnz     short loc_180060633
0x180060628  xor     ecx, ecx; lpModuleName
0x18006062a  call    cs:__imp_GetModuleHandleW
0x180060630  mov     rbx, rax
0x180060633  mov     r8d, 104h; nSize
0x180060639  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18006063e  mov     rcx, rbx; hModule
0x180060641  call    cs:__imp_GetModuleFileNameW
0x180060647  movzx   ecx, di
0x18006064a  lea     rax, [rsp+280h+Filename]
0x18006064f  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x180060654  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x180060659  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x180060661  mov     [rsp+280h+pActCtx.lpSource], rax
0x180060666  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x18006066e  mov     [rsp+280h+pActCtx.hModule], rbx
0x180060673  call    cs:__imp_CreateActCtxW
0x180060679  mov     rcx, rax; hActCtx
0x18006067c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180060680  jz      short loc_18006069C
0x180060682  or      rax, 0FFFFFFFFFFFFFFFFh
0x180060686  lock cmpxchg cs:g_hActCtx, rcx
0x18006068f  jz      short loc_180060697
0x180060691  call    cs:__imp_ReleaseActCtx
0x180060697  call    DelayLoadCC
0x18006069c  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x1800606a4  jnz     short loc_1800606AA
0x1800606a6  xor     eax, eax
0x1800606a8  jmp     short loc_1800606AF
0x1800606aa  mov     eax, 1
0x1800606af  mov     rcx, [rbp+180h+var_10]
0x1800606b6  xor     rcx, rsp; StackCookie
0x1800606b9  call    __security_check_cookie
0x1800606be  lea     r11, [rsp+280h+var_s0]
0x1800606c6  mov     rbx, [r11+10h]
0x1800606ca  mov     rdi, [r11+18h]
0x1800606ce  mov     rsp, r11
0x1800606d1  pop     rbp
0x1800606d2  retn
```
