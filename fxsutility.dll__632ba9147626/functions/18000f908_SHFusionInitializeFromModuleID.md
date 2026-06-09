# SHFusionInitializeFromModuleID

- ea: `0x18000f908`
- end: `0x18000fa0d`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004a74`
- `0x18000f898`

## callees

- `0x18000f908`
- `0x18000fa74`
- `0x180015cf0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000f964`
- `KERNEL32!GetModuleHandleW` at `0x18000f964`
- `KERNEL32!GetModuleFileNameW` at `0x18000f97b`
- `KERNEL32!GetModuleFileNameW` at `0x18000f97b`
- `KERNEL32!CreateActCtxW` at `0x18000f9ad`
- `KERNEL32!CreateActCtxW` at `0x18000f9ad`
- `KERNEL32!ReleaseActCtx` at `0x18000f9cb`
- `KERNEL32!ReleaseActCtx` at `0x18000f9cb`

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
0x18000f908  mov     [rsp-8+arg_10], rbx
0x18000f90d  mov     [rsp-8+arg_18], rdi
0x18000f912  push    rbp
0x18000f913  lea     rbp, [rsp-180h]
0x18000f91b  sub     rsp, 280h
0x18000f922  mov     rax, cs:__security_cookie
0x18000f929  xor     rax, rsp
0x18000f92c  mov     [rbp+180h+var_10], rax
0x18000f933  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18000f93b  mov     rbx, rcx
0x18000f93e  mov     edi, edx
0x18000f940  jnz     loc_18000F9E4
0x18000f946  xorps   xmm0, xmm0
0x18000f949  xor     eax, eax
0x18000f94b  mov     [rsp+280h+pActCtx.hModule], rax
0x18000f950  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x18000f955  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18000f95a  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x18000f95f  test    rcx, rcx
0x18000f962  jnz     short loc_18000F96D
0x18000f964  call    cs:__imp_GetModuleHandleW
0x18000f96a  mov     rbx, rax
0x18000f96d  mov     r8d, 104h; nSize
0x18000f973  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18000f978  mov     rcx, rbx; hModule
0x18000f97b  call    cs:__imp_GetModuleFileNameW
0x18000f981  movzx   ecx, di
0x18000f984  lea     rax, [rsp+280h+Filename]
0x18000f989  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x18000f98e  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x18000f993  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x18000f99b  mov     [rsp+280h+pActCtx.lpSource], rax
0x18000f9a0  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x18000f9a8  mov     [rsp+280h+pActCtx.hModule], rbx
0x18000f9ad  call    cs:__imp_CreateActCtxW
0x18000f9b3  mov     rcx, rax; hActCtx
0x18000f9b6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f9ba  jz      short loc_18000F9D6
0x18000f9bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f9c0  lock cmpxchg cs:g_hActCtx, rcx
0x18000f9c9  jz      short loc_18000F9D1
0x18000f9cb  call    cs:__imp_ReleaseActCtx
0x18000f9d1  call    DelayLoadCC
0x18000f9d6  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18000f9de  jnz     short loc_18000F9E4
0x18000f9e0  xor     eax, eax
0x18000f9e2  jmp     short loc_18000F9E9
0x18000f9e4  mov     eax, 1
0x18000f9e9  mov     rcx, [rbp+180h+var_10]
0x18000f9f0  xor     rcx, rsp; StackCookie
0x18000f9f3  call    __security_check_cookie
0x18000f9f8  lea     r11, [rsp+280h+var_s0]
0x18000fa00  mov     rbx, [r11+20h]
0x18000fa04  mov     rdi, [r11+28h]
0x18000fa08  mov     rsp, r11
0x18000fa0b  pop     rbp
0x18000fa0c  retn
```
