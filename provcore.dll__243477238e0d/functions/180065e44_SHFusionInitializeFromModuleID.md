# SHFusionInitializeFromModuleID

- ea: `0x180065e44`
- end: `0x180065f53`
- name: `SHFusionInitializeFromModuleID`
- size: `271`
- prototype: `int __fastcall(HINSTANCE__ *hMod, int id)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180065dbc`

## callees

- `0x180002790`
- `0x180065e44`
- `0x180065fb4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180065ec1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180065ec1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180065eaa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180065eaa`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180065ef3`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180065ef3`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180065f11`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180065f11`

## pseudocode

```c
_BOOL8 __fastcall SHFusionInitializeFromModuleID(HINSTANCE__ *hMod, int id)
{
  HINSTANCE__ *ModuleHandleW; // rbx
  unsigned __int16 v3; // di
  wchar_t *v4; // rax
  const wchar_t *v5; // rcx
  tagACTCTXW act; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR szPath[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( g_hActCtx != (HANDLE)-1LL )
    return 1;
  ModuleHandleW = g_hmod;
  v3 = g_id;
  memset(&act, 0, sizeof(act));
  if ( !g_hmod )
    ModuleHandleW = GetModuleHandleW(0);
  GetModuleFileNameW(ModuleHandleW, szPath, 0x104u);
  act.lpResourceName = (const wchar_t *)v3;
  act.cbSize = 56;
  act.lpSource = szPath;
  act.dwFlags = 136;
  act.hModule = ModuleHandleW;
  v4 = (wchar_t *)CreateActCtxW(&act);
  v5 = v4;
  if ( v4 != (wchar_t *)-1LL )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hActCtx, (signed __int64)v4, -1) != -1 )
      ReleaseActCtx(v4);
    DelayLoadCC(v5);
  }
  return g_hActCtx != (HANDLE)-1LL;
}

```

## disassembly

```asm
0x180065e44  mov     [rsp-8+arg_0], rbx
0x180065e49  mov     [rsp-8+arg_8], rdi
0x180065e4e  push    rbp
0x180065e4f  lea     rbp, [rsp-180h]
0x180065e57  sub     rsp, 280h
0x180065e5e  mov     rax, cs:__security_cookie
0x180065e65  xor     rax, rsp
0x180065e68  mov     [rbp+180h+var_10], rax
0x180065e6f  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180065e77  jnz     loc_180065F2A
0x180065e7d  mov     rbx, cs:g_hmod
0x180065e84  xorps   xmm0, xmm0
0x180065e87  mov     edi, cs:g_id
0x180065e8d  xor     eax, eax
0x180065e8f  mov     [rsp+280h+act.hModule], rax
0x180065e94  movups  xmmword ptr [rsp+280h+act.cbSize], xmm0
0x180065e99  movups  xmmword ptr [rsp+280h+act.wProcessorArchitecture], xmm0
0x180065e9e  movups  xmmword ptr [rsp+280h+act.lpResourceName], xmm0
0x180065ea3  test    rbx, rbx
0x180065ea6  jnz     short loc_180065EB3
0x180065ea8  xor     ecx, ecx; lpModuleName
0x180065eaa  call    cs:__imp_GetModuleHandleW
0x180065eb0  mov     rbx, rax
0x180065eb3  mov     r8d, 104h; nSize
0x180065eb9  lea     rdx, [rsp+280h+szPath]; lpFilename
0x180065ebe  mov     rcx, rbx; hModule
0x180065ec1  call    cs:__imp_GetModuleFileNameW
0x180065ec7  movzx   ecx, di
0x180065eca  lea     rax, [rsp+280h+szPath]
0x180065ecf  mov     [rsp+280h+act.lpResourceName], rcx
0x180065ed4  lea     rcx, [rsp+280h+act]; pActCtx
0x180065ed9  mov     [rsp+280h+act.cbSize], 38h ; '8'
0x180065ee1  mov     [rsp+280h+act.lpSource], rax
0x180065ee6  mov     [rsp+280h+act.dwFlags], 88h
0x180065eee  mov     [rsp+280h+act.hModule], rbx
0x180065ef3  call    cs:__imp_CreateActCtxW
0x180065ef9  mov     rcx, rax; hActCtx
0x180065efc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180065f00  jz      short loc_180065F1C
0x180065f02  or      rax, 0FFFFFFFFFFFFFFFFh
0x180065f06  lock cmpxchg cs:g_hActCtx, rcx
0x180065f0f  jz      short loc_180065F17
0x180065f11  call    cs:__imp_ReleaseActCtx
0x180065f17  call    DelayLoadCC
0x180065f1c  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180065f24  jnz     short loc_180065F2A
0x180065f26  xor     eax, eax
0x180065f28  jmp     short loc_180065F2F
0x180065f2a  mov     eax, 1
0x180065f2f  mov     rcx, [rbp+180h+var_10]
0x180065f36  xor     rcx, rsp; StackCookie
0x180065f39  call    __security_check_cookie
0x180065f3e  lea     r11, [rsp+280h+var_s0]
0x180065f46  mov     rbx, [r11+10h]
0x180065f4a  mov     rdi, [r11+18h]
0x180065f4e  mov     rsp, r11
0x180065f51  pop     rbp
0x180065f52  retn
```
