# SHFusionInitializeFromModuleID

- ea: `0x18001b5c8`
- end: `0x18001b6cd`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800067c0`
- `0x18001b538`

## callees

- `0x180002270`
- `0x18001b5c8`
- `0x18001b72c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001b63b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001b63b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b624`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b624`
- `KERNEL32!ReleaseActCtx` at `0x18001b68b`
- `KERNEL32!ReleaseActCtx` at `0x18001b68b`
- `KERNEL32!CreateActCtxW` at `0x18001b66d`
- `KERNEL32!CreateActCtxW` at `0x18001b66d`

## pseudocode

```c
_BOOL8 __fastcall SHFusionInitializeFromModuleID(HMODULE hModule, unsigned __int16 a2)
{
  HMODULE ModuleHandleW; // rbx
  HANDLE v4; // rax
  ACTCTXW pActCtx; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  ModuleHandleW = hModule;
  if ( g_hActCtx != (HANDLE)-1LL )
    return 1;
  memset(&pActCtx, 0, sizeof(pActCtx));
  if ( !hModule )
    ModuleHandleW = GetModuleHandleW(0);
  GetModuleFileNameW(ModuleHandleW, Filename, 0x104u);
  pActCtx.lpResourceName = (LPCWSTR)a2;
  pActCtx.cbSize = 56;
  pActCtx.lpSource = Filename;
  pActCtx.dwFlags = 136;
  pActCtx.hModule = ModuleHandleW;
  v4 = CreateActCtxW(&pActCtx);
  if ( v4 != (HANDLE)-1LL )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hActCtx, (signed __int64)v4, -1) != -1 )
      ReleaseActCtx(v4);
    DelayLoadCC();
  }
  return g_hActCtx != (HANDLE)-1LL;
}

```

## disassembly

```asm
0x18001b5c8  mov     [rsp-8+arg_10], rbx
0x18001b5cd  mov     [rsp-8+arg_18], rdi
0x18001b5d2  push    rbp
0x18001b5d3  lea     rbp, [rsp-180h]
0x18001b5db  sub     rsp, 280h
0x18001b5e2  mov     rax, cs:__security_cookie
0x18001b5e9  xor     rax, rsp
0x18001b5ec  mov     [rbp+180h+var_10], rax
0x18001b5f3  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18001b5fb  mov     rbx, rcx
0x18001b5fe  mov     edi, edx
0x18001b600  jnz     loc_18001B6A4
0x18001b606  xorps   xmm0, xmm0
0x18001b609  xor     eax, eax
0x18001b60b  mov     [rsp+280h+pActCtx.hModule], rax
0x18001b610  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x18001b615  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18001b61a  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x18001b61f  test    rcx, rcx
0x18001b622  jnz     short loc_18001B62D
0x18001b624  call    cs:__imp_GetModuleHandleW
0x18001b62a  mov     rbx, rax
0x18001b62d  mov     r8d, 104h; nSize
0x18001b633  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18001b638  mov     rcx, rbx; hModule
0x18001b63b  call    cs:__imp_GetModuleFileNameW
0x18001b641  movzx   ecx, di
0x18001b644  lea     rax, [rsp+280h+Filename]
0x18001b649  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x18001b64e  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x18001b653  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x18001b65b  mov     [rsp+280h+pActCtx.lpSource], rax
0x18001b660  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x18001b668  mov     [rsp+280h+pActCtx.hModule], rbx
0x18001b66d  call    cs:__imp_CreateActCtxW
0x18001b673  mov     rcx, rax; hActCtx
0x18001b676  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b67a  jz      short loc_18001B696
0x18001b67c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b680  lock cmpxchg cs:g_hActCtx, rcx
0x18001b689  jz      short loc_18001B691
0x18001b68b  call    cs:__imp_ReleaseActCtx
0x18001b691  call    DelayLoadCC
0x18001b696  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18001b69e  jnz     short loc_18001B6A4
0x18001b6a0  xor     eax, eax
0x18001b6a2  jmp     short loc_18001B6A9
0x18001b6a4  mov     eax, 1
0x18001b6a9  mov     rcx, [rbp+180h+var_10]
0x18001b6b0  xor     rcx, rsp; StackCookie
0x18001b6b3  call    __security_check_cookie
0x18001b6b8  lea     r11, [rsp+280h+var_s0]
0x18001b6c0  mov     rbx, [r11+20h]
0x18001b6c4  mov     rdi, [r11+28h]
0x18001b6c8  mov     rsp, r11
0x18001b6cb  pop     rbp
0x18001b6cc  retn
```
