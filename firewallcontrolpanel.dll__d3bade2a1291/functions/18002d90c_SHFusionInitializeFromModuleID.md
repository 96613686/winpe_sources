# SHFusionInitializeFromModuleID

- ea: `0x18002d90c`
- end: `0x18002da11`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b768`
- `0x18002d7c8`

## callees

- `0x18002d90c`
- `0x18002dacc`
- `0x180030ea0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d968`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d968`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002d97f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002d97f`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18002d9cf`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18002d9cf`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18002d9b1`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18002d9b1`

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
0x18002d90c  mov     [rsp-8+arg_10], rbx
0x18002d911  mov     [rsp-8+arg_18], rdi
0x18002d916  push    rbp
0x18002d917  lea     rbp, [rsp-180h]
0x18002d91f  sub     rsp, 280h
0x18002d926  mov     rax, cs:__security_cookie
0x18002d92d  xor     rax, rsp
0x18002d930  mov     [rbp+180h+var_10], rax
0x18002d937  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18002d93f  mov     rbx, rcx
0x18002d942  mov     edi, edx
0x18002d944  jnz     loc_18002D9E8
0x18002d94a  xorps   xmm0, xmm0
0x18002d94d  xor     eax, eax
0x18002d94f  mov     [rsp+280h+pActCtx.hModule], rax
0x18002d954  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x18002d959  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18002d95e  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x18002d963  test    rcx, rcx
0x18002d966  jnz     short loc_18002D971
0x18002d968  call    cs:__imp_GetModuleHandleW
0x18002d96e  mov     rbx, rax
0x18002d971  mov     r8d, 104h; nSize
0x18002d977  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18002d97c  mov     rcx, rbx; hModule
0x18002d97f  call    cs:__imp_GetModuleFileNameW
0x18002d985  movzx   ecx, di
0x18002d988  lea     rax, [rsp+280h+Filename]
0x18002d98d  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x18002d992  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x18002d997  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x18002d99f  mov     [rsp+280h+pActCtx.lpSource], rax
0x18002d9a4  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x18002d9ac  mov     [rsp+280h+pActCtx.hModule], rbx
0x18002d9b1  call    cs:__imp_CreateActCtxW
0x18002d9b7  mov     rcx, rax; hActCtx
0x18002d9ba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d9be  jz      short loc_18002D9DA
0x18002d9c0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d9c4  lock cmpxchg cs:g_hActCtx, rcx
0x18002d9cd  jz      short loc_18002D9D5
0x18002d9cf  call    cs:__imp_ReleaseActCtx
0x18002d9d5  call    DelayLoadCC
0x18002d9da  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18002d9e2  jnz     short loc_18002D9E8
0x18002d9e4  xor     eax, eax
0x18002d9e6  jmp     short loc_18002D9ED
0x18002d9e8  mov     eax, 1
0x18002d9ed  mov     rcx, [rbp+180h+var_10]
0x18002d9f4  xor     rcx, rsp; StackCookie
0x18002d9f7  call    __security_check_cookie
0x18002d9fc  lea     r11, [rsp+280h+var_s0]
0x18002da04  mov     rbx, [r11+20h]
0x18002da08  mov     rdi, [r11+28h]
0x18002da0c  mov     rsp, r11
0x18002da0f  pop     rbp
0x18002da10  retn
```
