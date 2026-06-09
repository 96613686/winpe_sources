# SHFusionInitializeFromModuleID

- ea: `0x180017cd8`
- end: `0x180017de7`
- name: `SHFusionInitializeFromModuleID`
- size: `271`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017c70`

## callees

- `0x180017cd8`
- `0x180018110`
- `0x180018500`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180017d55`
- `KERNEL32!GetModuleFileNameW` at `0x180017d55`
- `KERNEL32!GetModuleHandleW` at `0x180017d3e`
- `KERNEL32!GetModuleHandleW` at `0x180017d3e`
- `KERNEL32!CreateActCtxW` at `0x180017d87`
- `KERNEL32!CreateActCtxW` at `0x180017d87`
- `KERNEL32!ReleaseActCtx` at `0x180017da5`
- `KERNEL32!ReleaseActCtx` at `0x180017da5`

## pseudocode

```c
_BOOL8 SHFusionInitializeFromModuleID()
{
  HMODULE ModuleHandleW; // rbx
  unsigned __int16 v1; // di
  HANDLE v2; // rax
  ACTCTXW pActCtx; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( g_hActCtx != -1 )
    return 1;
  ModuleHandleW = hModule;
  v1 = dword_180021C58;
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
    if ( _InterlockedCompareExchange64(&g_hActCtx, (signed __int64)v2, -1) != -1 )
      ReleaseActCtx(v2);
    DelayLoadCC();
  }
  return g_hActCtx != -1;
}

```

## disassembly

```asm
0x180017cd8  mov     [rsp-8+arg_0], rbx
0x180017cdd  mov     [rsp-8+arg_8], rdi
0x180017ce2  push    rbp
0x180017ce3  lea     rbp, [rsp-180h]
0x180017ceb  sub     rsp, 280h
0x180017cf2  mov     rax, cs:__security_cookie
0x180017cf9  xor     rax, rsp
0x180017cfc  mov     [rbp+180h+var_10], rax
0x180017d03  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180017d0b  jnz     loc_180017DBE
0x180017d11  mov     rbx, cs:hModule
0x180017d18  xorps   xmm0, xmm0
0x180017d1b  mov     edi, cs:dword_180021C58
0x180017d21  xor     eax, eax
0x180017d23  mov     [rsp+280h+pActCtx.hModule], rax
0x180017d28  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x180017d2d  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x180017d32  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x180017d37  test    rbx, rbx
0x180017d3a  jnz     short loc_180017D47
0x180017d3c  xor     ecx, ecx; lpModuleName
0x180017d3e  call    cs:__imp_GetModuleHandleW
0x180017d44  mov     rbx, rax
0x180017d47  mov     r8d, 104h; nSize
0x180017d4d  lea     rdx, [rsp+280h+Filename]; lpFilename
0x180017d52  mov     rcx, rbx; hModule
0x180017d55  call    cs:__imp_GetModuleFileNameW
0x180017d5b  movzx   ecx, di
0x180017d5e  lea     rax, [rsp+280h+Filename]
0x180017d63  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x180017d68  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x180017d6d  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x180017d75  mov     [rsp+280h+pActCtx.lpSource], rax
0x180017d7a  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x180017d82  mov     [rsp+280h+pActCtx.hModule], rbx
0x180017d87  call    cs:__imp_CreateActCtxW
0x180017d8d  mov     rcx, rax; hActCtx
0x180017d90  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017d94  jz      short loc_180017DB0
0x180017d96  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017d9a  lock cmpxchg cs:g_hActCtx, rcx
0x180017da3  jz      short loc_180017DAB
0x180017da5  call    cs:__imp_ReleaseActCtx
0x180017dab  call    DelayLoadCC
0x180017db0  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180017db8  jnz     short loc_180017DBE
0x180017dba  xor     eax, eax
0x180017dbc  jmp     short loc_180017DC3
0x180017dbe  mov     eax, 1
0x180017dc3  mov     rcx, [rbp+180h+var_10]
0x180017dca  xor     rcx, rsp; StackCookie
0x180017dcd  call    __security_check_cookie
0x180017dd2  lea     r11, [rsp+280h+var_s0]
0x180017dda  mov     rbx, [r11+10h]
0x180017dde  mov     rdi, [r11+18h]
0x180017de2  mov     rsp, r11
0x180017de5  pop     rbp
0x180017de6  retn
```
