# SHFusionInitializeFromModuleID

- ea: `0x18000c89c`
- end: `0x18000c9a1`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `_BOOL8 __fastcall(HMODULE hModule, unsigned __int16)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a9e4`
- `0x18000c82c`

## callees

- `0x18000c89c`
- `0x18000ca08`
- `0x18000cbf0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c8f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c8f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c90f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c90f`
- `KERNEL32!CreateActCtxW` at `0x18000c941`
- `KERNEL32!CreateActCtxW` at `0x18000c941`
- `KERNEL32!ReleaseActCtx` at `0x18000c95f`
- `KERNEL32!ReleaseActCtx` at `0x18000c95f`

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
0x18000c89c  mov     [rsp-8+arg_10], rbx
0x18000c8a1  mov     [rsp-8+arg_18], rdi
0x18000c8a6  push    rbp
0x18000c8a7  lea     rbp, [rsp-180h]
0x18000c8af  sub     rsp, 280h
0x18000c8b6  mov     rax, cs:__security_cookie
0x18000c8bd  xor     rax, rsp
0x18000c8c0  mov     [rbp+180h+var_10], rax
0x18000c8c7  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18000c8cf  mov     rbx, rcx
0x18000c8d2  mov     edi, edx
0x18000c8d4  jnz     loc_18000C978
0x18000c8da  xorps   xmm0, xmm0
0x18000c8dd  xor     eax, eax
0x18000c8df  mov     [rsp+280h+pActCtx.hModule], rax
0x18000c8e4  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x18000c8e9  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18000c8ee  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x18000c8f3  test    rcx, rcx
0x18000c8f6  jnz     short loc_18000C901
0x18000c8f8  call    cs:__imp_GetModuleHandleW
0x18000c8fe  mov     rbx, rax
0x18000c901  mov     r8d, 104h; nSize
0x18000c907  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18000c90c  mov     rcx, rbx; hModule
0x18000c90f  call    cs:__imp_GetModuleFileNameW
0x18000c915  movzx   ecx, di
0x18000c918  lea     rax, [rsp+280h+Filename]
0x18000c91d  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x18000c922  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x18000c927  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x18000c92f  mov     [rsp+280h+pActCtx.lpSource], rax
0x18000c934  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x18000c93c  mov     [rsp+280h+pActCtx.hModule], rbx
0x18000c941  call    cs:__imp_CreateActCtxW
0x18000c947  mov     rcx, rax; hActCtx
0x18000c94a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c94e  jz      short loc_18000C96A
0x18000c950  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c954  lock cmpxchg cs:g_hActCtx, rcx
0x18000c95d  jz      short loc_18000C965
0x18000c95f  call    cs:__imp_ReleaseActCtx
0x18000c965  call    DelayLoadCC
0x18000c96a  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18000c972  jnz     short loc_18000C978
0x18000c974  xor     eax, eax
0x18000c976  jmp     short loc_18000C97D
0x18000c978  mov     eax, 1
0x18000c97d  mov     rcx, [rbp+180h+var_10]
0x18000c984  xor     rcx, rsp; StackCookie
0x18000c987  call    __security_check_cookie
0x18000c98c  lea     r11, [rsp+280h+var_s0]
0x18000c994  mov     rbx, [r11+20h]
0x18000c998  mov     rdi, [r11+28h]
0x18000c99c  mov     rsp, r11
0x18000c99f  pop     rbp
0x18000c9a0  retn
```
