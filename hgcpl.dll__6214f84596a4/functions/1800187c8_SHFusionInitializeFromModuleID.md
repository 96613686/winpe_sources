# SHFusionInitializeFromModuleID

- ea: `0x1800187c8`
- end: `0x1800188d7`
- name: `SHFusionInitializeFromModuleID`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018740`

## callees

- `0x1800187c8`
- `0x180018938`
- `0x180018a80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001882e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001882e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180018845`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180018845`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180018895`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180018895`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180018877`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180018877`

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
  ModuleHandleW = qword_18002A860;
  v1 = dword_18002A868;
  memset(&pActCtx, 0, sizeof(pActCtx));
  if ( !qword_18002A860 )
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
0x1800187c8  mov     [rsp-8+arg_0], rbx
0x1800187cd  mov     [rsp-8+arg_8], rdi
0x1800187d2  push    rbp
0x1800187d3  lea     rbp, [rsp-180h]
0x1800187db  sub     rsp, 280h
0x1800187e2  mov     rax, cs:__security_cookie
0x1800187e9  xor     rax, rsp
0x1800187ec  mov     [rbp+180h+var_10], rax
0x1800187f3  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x1800187fb  jnz     loc_1800188AE
0x180018801  mov     rbx, cs:qword_18002A860
0x180018808  xorps   xmm0, xmm0
0x18001880b  mov     edi, cs:dword_18002A868
0x180018811  xor     eax, eax
0x180018813  mov     [rsp+280h+pActCtx.hModule], rax
0x180018818  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x18001881d  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x180018822  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x180018827  test    rbx, rbx
0x18001882a  jnz     short loc_180018837
0x18001882c  xor     ecx, ecx; lpModuleName
0x18001882e  call    cs:__imp_GetModuleHandleW
0x180018834  mov     rbx, rax
0x180018837  mov     r8d, 104h; nSize
0x18001883d  lea     rdx, [rsp+280h+Filename]; lpFilename
0x180018842  mov     rcx, rbx; hModule
0x180018845  call    cs:__imp_GetModuleFileNameW
0x18001884b  movzx   ecx, di
0x18001884e  lea     rax, [rsp+280h+Filename]
0x180018853  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x180018858  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x18001885d  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x180018865  mov     [rsp+280h+pActCtx.lpSource], rax
0x18001886a  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x180018872  mov     [rsp+280h+pActCtx.hModule], rbx
0x180018877  call    cs:__imp_CreateActCtxW
0x18001887d  mov     rcx, rax; hActCtx
0x180018880  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018884  jz      short loc_1800188A0
0x180018886  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001888a  lock cmpxchg cs:g_hActCtx, rcx
0x180018893  jz      short loc_18001889B
0x180018895  call    cs:__imp_ReleaseActCtx
0x18001889b  call    DelayLoadCC
0x1800188a0  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x1800188a8  jnz     short loc_1800188AE
0x1800188aa  xor     eax, eax
0x1800188ac  jmp     short loc_1800188B3
0x1800188ae  mov     eax, 1
0x1800188b3  mov     rcx, [rbp+180h+var_10]
0x1800188ba  xor     rcx, rsp; StackCookie
0x1800188bd  call    __security_check_cookie
0x1800188c2  lea     r11, [rsp+280h+var_s0]
0x1800188ca  mov     rbx, [r11+10h]
0x1800188ce  mov     rdi, [r11+18h]
0x1800188d2  mov     rsp, r11
0x1800188d5  pop     rbp
0x1800188d6  retn
```
