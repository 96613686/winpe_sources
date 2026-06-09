# SHFusionInitializeFromModuleID

- ea: `0x14000d998`
- end: `0x14000dab6`
- name: `SHFusionInitializeFromModuleID`
- size: `286`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000ca10`
- `0x14000d920`

## callees

- `0x14000d998`
- `0x14000db28`
- `0x1400109c0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000d9f4`
- `KERNEL32!GetModuleHandleW` at `0x14000d9f4`
- `KERNEL32!CreateActCtxW` at `0x14000da49`
- `KERNEL32!CreateActCtxW` at `0x14000da49`
- `KERNEL32!GetModuleFileNameW` at `0x14000da11`
- `KERNEL32!GetModuleFileNameW` at `0x14000da11`
- `KERNEL32!ReleaseActCtx` at `0x14000da6d`
- `KERNEL32!ReleaseActCtx` at `0x14000da6d`

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
0x14000d998  mov     [rsp-8+arg_10], rbx
0x14000d99d  mov     [rsp-8+arg_18], rdi
0x14000d9a2  push    rbp
0x14000d9a3  lea     rbp, [rsp-180h]
0x14000d9ab  sub     rsp, 280h
0x14000d9b2  mov     rax, cs:__security_cookie
0x14000d9b9  xor     rax, rsp
0x14000d9bc  mov     [rbp+180h+var_10], rax
0x14000d9c3  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x14000d9cb  mov     rbx, rcx
0x14000d9ce  mov     edi, edx
0x14000d9d0  jnz     loc_14000DA8C
0x14000d9d6  xorps   xmm0, xmm0
0x14000d9d9  xor     eax, eax
0x14000d9db  mov     [rsp+280h+pActCtx.hModule], rax
0x14000d9e0  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x14000d9e5  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x14000d9ea  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x14000d9ef  test    rcx, rcx
0x14000d9f2  jnz     short loc_14000DA03
0x14000d9f4  call    cs:__imp_GetModuleHandleW
0x14000d9fb  nop     dword ptr [rax+rax+00h]
0x14000da00  mov     rbx, rax
0x14000da03  mov     r8d, 104h; nSize
0x14000da09  lea     rdx, [rsp+280h+Filename]; lpFilename
0x14000da0e  mov     rcx, rbx; hModule
0x14000da11  call    cs:__imp_GetModuleFileNameW
0x14000da18  nop     dword ptr [rax+rax+00h]
0x14000da1d  movzx   ecx, di
0x14000da20  lea     rax, [rsp+280h+Filename]
0x14000da25  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x14000da2a  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x14000da2f  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x14000da37  mov     [rsp+280h+pActCtx.lpSource], rax
0x14000da3c  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x14000da44  mov     [rsp+280h+pActCtx.hModule], rbx
0x14000da49  call    cs:__imp_CreateActCtxW
0x14000da50  nop     dword ptr [rax+rax+00h]
0x14000da55  mov     rcx, rax; hActCtx
0x14000da58  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000da5c  jz      short loc_14000DA7E
0x14000da5e  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000da62  lock cmpxchg cs:g_hActCtx, rcx
0x14000da6b  jz      short loc_14000DA79
0x14000da6d  call    cs:__imp_ReleaseActCtx
0x14000da74  nop     dword ptr [rax+rax+00h]
0x14000da79  call    DelayLoadCC
0x14000da7e  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x14000da86  jnz     short loc_14000DA8C
0x14000da88  xor     eax, eax
0x14000da8a  jmp     short loc_14000DA91
0x14000da8c  mov     eax, 1
0x14000da91  mov     rcx, [rbp+180h+var_10]
0x14000da98  xor     rcx, rsp; StackCookie
0x14000da9b  call    __security_check_cookie
0x14000daa0  lea     r11, [rsp+280h+var_s0]
0x14000daa8  mov     rbx, [r11+20h]
0x14000daac  mov     rdi, [r11+28h]
0x14000dab0  mov     rsp, r11
0x14000dab3  pop     rbp
0x14000dab4  retn
```
