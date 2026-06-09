# SHFusionInitializeFromModuleID

- ea: `0x14001c0c4`
- end: `0x14001c1d3`
- name: `SHFusionInitializeFromModuleID`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001bf00`

## callees

- `0x14001c0c4`
- `0x14001c234`
- `0x140025d70`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x14001c141`
- `KERNEL32!GetModuleFileNameW` at `0x14001c141`
- `KERNEL32!CreateActCtxW` at `0x14001c173`
- `KERNEL32!CreateActCtxW` at `0x14001c173`
- `KERNEL32!GetModuleHandleW` at `0x14001c12a`
- `KERNEL32!GetModuleHandleW` at `0x14001c12a`
- `KERNEL32!ReleaseActCtx` at `0x14001c191`
- `KERNEL32!ReleaseActCtx` at `0x14001c191`

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
  v1 = dword_140037458;
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
0x14001c0c4  mov     [rsp-8+arg_0], rbx
0x14001c0c9  mov     [rsp-8+arg_8], rdi
0x14001c0ce  push    rbp
0x14001c0cf  lea     rbp, [rsp-180h]
0x14001c0d7  sub     rsp, 280h
0x14001c0de  mov     rax, cs:__security_cookie
0x14001c0e5  xor     rax, rsp
0x14001c0e8  mov     [rbp+180h+var_10], rax
0x14001c0ef  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x14001c0f7  jnz     loc_14001C1AA
0x14001c0fd  mov     rbx, cs:hModule
0x14001c104  xorps   xmm0, xmm0
0x14001c107  mov     edi, cs:dword_140037458
0x14001c10d  xor     eax, eax
0x14001c10f  mov     [rsp+280h+pActCtx.hModule], rax
0x14001c114  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x14001c119  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x14001c11e  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x14001c123  test    rbx, rbx
0x14001c126  jnz     short loc_14001C133
0x14001c128  xor     ecx, ecx; lpModuleName
0x14001c12a  call    cs:__imp_GetModuleHandleW
0x14001c130  mov     rbx, rax
0x14001c133  mov     r8d, 104h; nSize
0x14001c139  lea     rdx, [rsp+280h+Filename]; lpFilename
0x14001c13e  mov     rcx, rbx; hModule
0x14001c141  call    cs:__imp_GetModuleFileNameW
0x14001c147  movzx   ecx, di
0x14001c14a  lea     rax, [rsp+280h+Filename]
0x14001c14f  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x14001c154  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x14001c159  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x14001c161  mov     [rsp+280h+pActCtx.lpSource], rax
0x14001c166  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x14001c16e  mov     [rsp+280h+pActCtx.hModule], rbx
0x14001c173  call    cs:__imp_CreateActCtxW
0x14001c179  mov     rcx, rax; hActCtx
0x14001c17c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001c180  jz      short loc_14001C19C
0x14001c182  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001c186  lock cmpxchg cs:g_hActCtx, rcx
0x14001c18f  jz      short loc_14001C197
0x14001c191  call    cs:__imp_ReleaseActCtx
0x14001c197  call    DelayLoadCC
0x14001c19c  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x14001c1a4  jnz     short loc_14001C1AA
0x14001c1a6  xor     eax, eax
0x14001c1a8  jmp     short loc_14001C1AF
0x14001c1aa  mov     eax, 1
0x14001c1af  mov     rcx, [rbp+180h+var_10]
0x14001c1b6  xor     rcx, rsp; StackCookie
0x14001c1b9  call    __security_check_cookie
0x14001c1be  lea     r11, [rsp+280h+var_s0]
0x14001c1c6  mov     rbx, [r11+10h]
0x14001c1ca  mov     rdi, [r11+18h]
0x14001c1ce  mov     rsp, r11
0x14001c1d1  pop     rbp
0x14001c1d2  retn
```
