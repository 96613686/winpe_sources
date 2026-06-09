# SHFusionInitializeFromModuleID

- ea: `0x180004604`
- end: `0x180004713`
- name: `SHFusionInitializeFromModuleID`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000459c`

## callees

- `0x180004604`
- `0x18000477c`
- `0x180004920`

## import_xrefs

- `KERNEL32!CreateActCtxW` at `0x1800046b3`
- `KERNEL32!CreateActCtxW` at `0x1800046b3`
- `KERNEL32!ReleaseActCtx` at `0x1800046d1`
- `KERNEL32!ReleaseActCtx` at `0x1800046d1`
- `KERNEL32!GetModuleHandleW` at `0x18000466a`
- `KERNEL32!GetModuleHandleW` at `0x18000466a`
- `KERNEL32!GetModuleFileNameW` at `0x180004681`
- `KERNEL32!GetModuleFileNameW` at `0x180004681`

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
  v1 = dword_180009778;
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
0x180004604  mov     [rsp-8+arg_0], rbx
0x180004609  mov     [rsp-8+arg_8], rdi
0x18000460e  push    rbp
0x18000460f  lea     rbp, [rsp-180h]
0x180004617  sub     rsp, 280h
0x18000461e  mov     rax, cs:__security_cookie
0x180004625  xor     rax, rsp
0x180004628  mov     [rbp+180h+var_10], rax
0x18000462f  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180004637  jnz     loc_1800046EA
0x18000463d  mov     rbx, cs:hModule
0x180004644  xorps   xmm0, xmm0
0x180004647  mov     edi, cs:dword_180009778
0x18000464d  xor     eax, eax
0x18000464f  mov     [rsp+280h+pActCtx.hModule], rax
0x180004654  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x180004659  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18000465e  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x180004663  test    rbx, rbx
0x180004666  jnz     short loc_180004673
0x180004668  xor     ecx, ecx; lpModuleName
0x18000466a  call    cs:__imp_GetModuleHandleW
0x180004670  mov     rbx, rax
0x180004673  mov     r8d, 104h; nSize
0x180004679  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18000467e  mov     rcx, rbx; hModule
0x180004681  call    cs:__imp_GetModuleFileNameW
0x180004687  movzx   ecx, di
0x18000468a  lea     rax, [rsp+280h+Filename]
0x18000468f  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x180004694  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x180004699  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x1800046a1  mov     [rsp+280h+pActCtx.lpSource], rax
0x1800046a6  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x1800046ae  mov     [rsp+280h+pActCtx.hModule], rbx
0x1800046b3  call    cs:__imp_CreateActCtxW
0x1800046b9  mov     rcx, rax; hActCtx
0x1800046bc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800046c0  jz      short loc_1800046DC
0x1800046c2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800046c6  lock cmpxchg cs:g_hActCtx, rcx
0x1800046cf  jz      short loc_1800046D7
0x1800046d1  call    cs:__imp_ReleaseActCtx
0x1800046d7  call    DelayLoadCC
0x1800046dc  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x1800046e4  jnz     short loc_1800046EA
0x1800046e6  xor     eax, eax
0x1800046e8  jmp     short loc_1800046EF
0x1800046ea  mov     eax, 1
0x1800046ef  mov     rcx, [rbp+180h+var_10]
0x1800046f6  xor     rcx, rsp; StackCookie
0x1800046f9  call    __security_check_cookie
0x1800046fe  lea     r11, [rsp+280h+var_s0]
0x180004706  mov     rbx, [r11+10h]
0x18000470a  mov     rdi, [r11+18h]
0x18000470e  mov     rsp, r11
0x180004711  pop     rbp
0x180004712  retn
```
