# SHFusionInitializeFromModuleID

- ea: `0x1800391ac`
- end: `0x1800392bb`
- name: `SHFusionInitializeFromModuleID`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180038fdc`

## callees

- `0x1800391ac`
- `0x18003946c`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039212`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039212`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180039229`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180039229`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18003925b`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18003925b`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180039279`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180039279`

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
  v1 = dword_180063F58;
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
0x1800391ac  mov     [rsp-8+arg_0], rbx
0x1800391b1  mov     [rsp-8+arg_8], rdi
0x1800391b6  push    rbp
0x1800391b7  lea     rbp, [rsp-180h]
0x1800391bf  sub     rsp, 280h
0x1800391c6  mov     rax, cs:__security_cookie
0x1800391cd  xor     rax, rsp
0x1800391d0  mov     [rbp+180h+var_10], rax
0x1800391d7  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x1800391df  jnz     loc_180039292
0x1800391e5  mov     rbx, cs:hModule
0x1800391ec  xorps   xmm0, xmm0
0x1800391ef  mov     edi, cs:dword_180063F58
0x1800391f5  xor     eax, eax
0x1800391f7  mov     [rsp+280h+pActCtx.hModule], rax
0x1800391fc  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x180039201  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x180039206  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x18003920b  test    rbx, rbx
0x18003920e  jnz     short loc_18003921B
0x180039210  xor     ecx, ecx; lpModuleName
0x180039212  call    cs:__imp_GetModuleHandleW
0x180039218  mov     rbx, rax
0x18003921b  mov     r8d, 104h; nSize
0x180039221  lea     rdx, [rsp+280h+Filename]; lpFilename
0x180039226  mov     rcx, rbx; hModule
0x180039229  call    cs:__imp_GetModuleFileNameW
0x18003922f  movzx   ecx, di
0x180039232  lea     rax, [rsp+280h+Filename]
0x180039237  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x18003923c  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x180039241  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x180039249  mov     [rsp+280h+pActCtx.lpSource], rax
0x18003924e  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x180039256  mov     [rsp+280h+pActCtx.hModule], rbx
0x18003925b  call    cs:__imp_CreateActCtxW
0x180039261  mov     rcx, rax; hActCtx
0x180039264  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039268  jz      short loc_180039284
0x18003926a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003926e  lock cmpxchg cs:g_hActCtx, rcx
0x180039277  jz      short loc_18003927F
0x180039279  call    cs:__imp_ReleaseActCtx
0x18003927f  call    DelayLoadCC
0x180039284  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18003928c  jnz     short loc_180039292
0x18003928e  xor     eax, eax
0x180039290  jmp     short loc_180039297
0x180039292  mov     eax, 1
0x180039297  mov     rcx, [rbp+180h+var_10]
0x18003929e  xor     rcx, rsp; StackCookie
0x1800392a1  call    __security_check_cookie
0x1800392a6  lea     r11, [rsp+280h+var_s0]
0x1800392ae  mov     rbx, [r11+10h]
0x1800392b2  mov     rdi, [r11+18h]
0x1800392b6  mov     rsp, r11
0x1800392b9  pop     rbp
0x1800392ba  retn
```
