# SHFusionInitializeFromModuleID

- ea: `0x1800309a8`
- end: `0x180030ab7`
- name: `SHFusionInitializeFromModuleID`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180030920`

## callees

- `0x1800309a8`
- `0x180030c38`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030a0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030a0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180030a25`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180030a25`
- `KERNEL32!ReleaseActCtx` at `0x180030a75`
- `KERNEL32!ReleaseActCtx` at `0x180030a75`
- `KERNEL32!CreateActCtxW` at `0x180030a57`
- `KERNEL32!CreateActCtxW` at `0x180030a57`

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
  v1 = dword_180047B48;
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
0x1800309a8  mov     [rsp-8+arg_0], rbx
0x1800309ad  mov     [rsp-8+arg_8], rdi
0x1800309b2  push    rbp
0x1800309b3  lea     rbp, [rsp-180h]
0x1800309bb  sub     rsp, 280h
0x1800309c2  mov     rax, cs:__security_cookie
0x1800309c9  xor     rax, rsp
0x1800309cc  mov     [rbp+180h+var_10], rax
0x1800309d3  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x1800309db  jnz     loc_180030A8E
0x1800309e1  mov     rbx, cs:hModule
0x1800309e8  xorps   xmm0, xmm0
0x1800309eb  mov     edi, cs:dword_180047B48
0x1800309f1  xor     eax, eax
0x1800309f3  mov     [rsp+280h+pActCtx.hModule], rax
0x1800309f8  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x1800309fd  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x180030a02  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x180030a07  test    rbx, rbx
0x180030a0a  jnz     short loc_180030A17
0x180030a0c  xor     ecx, ecx; lpModuleName
0x180030a0e  call    cs:__imp_GetModuleHandleW
0x180030a14  mov     rbx, rax
0x180030a17  mov     r8d, 104h; nSize
0x180030a1d  lea     rdx, [rsp+280h+Filename]; lpFilename
0x180030a22  mov     rcx, rbx; hModule
0x180030a25  call    cs:__imp_GetModuleFileNameW
0x180030a2b  movzx   ecx, di
0x180030a2e  lea     rax, [rsp+280h+Filename]
0x180030a33  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x180030a38  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x180030a3d  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x180030a45  mov     [rsp+280h+pActCtx.lpSource], rax
0x180030a4a  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x180030a52  mov     [rsp+280h+pActCtx.hModule], rbx
0x180030a57  call    cs:__imp_CreateActCtxW
0x180030a5d  mov     rcx, rax; hActCtx
0x180030a60  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030a64  jz      short loc_180030A80
0x180030a66  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030a6a  lock cmpxchg cs:g_hActCtx, rcx
0x180030a73  jz      short loc_180030A7B
0x180030a75  call    cs:__imp_ReleaseActCtx
0x180030a7b  call    DelayLoadCC
0x180030a80  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180030a88  jnz     short loc_180030A8E
0x180030a8a  xor     eax, eax
0x180030a8c  jmp     short loc_180030A93
0x180030a8e  mov     eax, 1
0x180030a93  mov     rcx, [rbp+180h+var_10]
0x180030a9a  xor     rcx, rsp; StackCookie
0x180030a9d  call    __security_check_cookie
0x180030aa2  lea     r11, [rsp+280h+var_s0]
0x180030aaa  mov     rbx, [r11+10h]
0x180030aae  mov     rdi, [r11+18h]
0x180030ab2  mov     rsp, r11
0x180030ab5  pop     rbp
0x180030ab6  retn
```
