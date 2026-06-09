# SHFusionInitializeFromModuleID

- ea: `0x18002ea40`
- end: `0x18002eb4f`
- name: `SHFusionInitializeFromModuleID`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002e9b8`

## callees

- `0x18002ea40`
- `0x18002ebac`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002eaa6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002eaa6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002eabd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002eabd`
- `KERNEL32!CreateActCtxW` at `0x18002eaef`
- `KERNEL32!CreateActCtxW` at `0x18002eaef`
- `KERNEL32!ReleaseActCtx` at `0x18002eb0d`
- `KERNEL32!ReleaseActCtx` at `0x18002eb0d`

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
  v1 = dword_18004DA90;
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
0x18002ea40  mov     [rsp-8+arg_0], rbx
0x18002ea45  mov     [rsp-8+arg_8], rdi
0x18002ea4a  push    rbp
0x18002ea4b  lea     rbp, [rsp-180h]
0x18002ea53  sub     rsp, 280h
0x18002ea5a  mov     rax, cs:__security_cookie
0x18002ea61  xor     rax, rsp
0x18002ea64  mov     [rbp+180h+var_10], rax
0x18002ea6b  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18002ea73  jnz     loc_18002EB26
0x18002ea79  mov     rbx, cs:hModule
0x18002ea80  xorps   xmm0, xmm0
0x18002ea83  mov     edi, cs:dword_18004DA90
0x18002ea89  xor     eax, eax
0x18002ea8b  mov     [rsp+280h+pActCtx.hModule], rax
0x18002ea90  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x18002ea95  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18002ea9a  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x18002ea9f  test    rbx, rbx
0x18002eaa2  jnz     short loc_18002EAAF
0x18002eaa4  xor     ecx, ecx; lpModuleName
0x18002eaa6  call    cs:__imp_GetModuleHandleW
0x18002eaac  mov     rbx, rax
0x18002eaaf  mov     r8d, 104h; nSize
0x18002eab5  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18002eaba  mov     rcx, rbx; hModule
0x18002eabd  call    cs:__imp_GetModuleFileNameW
0x18002eac3  movzx   ecx, di
0x18002eac6  lea     rax, [rsp+280h+Filename]
0x18002eacb  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x18002ead0  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x18002ead5  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x18002eadd  mov     [rsp+280h+pActCtx.lpSource], rax
0x18002eae2  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x18002eaea  mov     [rsp+280h+pActCtx.hModule], rbx
0x18002eaef  call    cs:__imp_CreateActCtxW
0x18002eaf5  mov     rcx, rax; hActCtx
0x18002eaf8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002eafc  jz      short loc_18002EB18
0x18002eafe  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002eb02  lock cmpxchg cs:g_hActCtx, rcx
0x18002eb0b  jz      short loc_18002EB13
0x18002eb0d  call    cs:__imp_ReleaseActCtx
0x18002eb13  call    DelayLoadCC
0x18002eb18  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18002eb20  jnz     short loc_18002EB26
0x18002eb22  xor     eax, eax
0x18002eb24  jmp     short loc_18002EB2B
0x18002eb26  mov     eax, 1
0x18002eb2b  mov     rcx, [rbp+180h+var_10]
0x18002eb32  xor     rcx, rsp; StackCookie
0x18002eb35  call    __security_check_cookie
0x18002eb3a  lea     r11, [rsp+280h+var_s0]
0x18002eb42  mov     rbx, [r11+10h]
0x18002eb46  mov     rdi, [r11+18h]
0x18002eb4a  mov     rsp, r11
0x18002eb4d  pop     rbp
0x18002eb4e  retn
```
