# SHFusionInitializeFromModuleID

- ea: `0x1800059f0`
- end: `0x180005b61`
- name: `SHFusionInitializeFromModuleID`
- size: `369`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800088dc`
- `0x180008c24`

## callees

- `0x1800059f0`
- `0x1800088dc`
- `0x18004c670`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005a40`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005a40`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005aea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005b20`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005aea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005b20`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180005a57`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180005a57`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180005a89`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180005a89`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180005ab0`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180005ab0`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180005aff`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180005aff`

## string_xrefs

- `0x180005add`: `comctl32.dll`
- `0x180005b13`: `comctl32.dll`

## pseudocode

```c
_BOOL8 __fastcall SHFusionInitializeFromModuleID(HMODULE hModule, unsigned __int16 a2)
{
  HMODULE ModuleHandleW; // rbx
  HANDLE v4; // rax
  HMODULE Library; // rbx
  ULONG_PTR ulCookie; // [rsp+20h] [rbp-268h] BYREF
  ACTCTXW pActCtx; // [rsp+28h] [rbp-260h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-228h] BYREF

  ModuleHandleW = hModule;
  if ( g_hActCtx != (HANDLE)-1LL )
    return 1;
  memset(&pActCtx, 0, sizeof(pActCtx));
  if ( !hModule )
    ModuleHandleW = GetModuleHandleW(0);
  GetModuleFileNameW(ModuleHandleW, Filename, 0x104u);
  pActCtx.cbSize = 56;
  pActCtx.lpSource = Filename;
  pActCtx.lpResourceName = (LPCWSTR)a2;
  pActCtx.dwFlags = 136;
  pActCtx.hModule = ModuleHandleW;
  v4 = CreateActCtxW(&pActCtx);
  if ( v4 != (HANDLE)-1LL )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hActCtx, (signed __int64)v4, -1) != -1 )
      ReleaseActCtx(v4);
    if ( !g_hinstCC )
    {
      ulCookie = 0;
      if ( !(unsigned int)SHActivateContext(&ulCookie) )
      {
        g_hinstCC = 0;
LABEL_13:
        g_hinstCC = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
        return g_hActCtx != (HANDLE)-1LL;
      }
      Library = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
      if ( ulCookie )
        DeactivateActCtx(0, ulCookie);
      g_hinstCC = Library;
      if ( !Library )
        goto LABEL_13;
    }
  }
  return g_hActCtx != (HANDLE)-1LL;
}

```

## disassembly

```asm
0x1800059f0  mov     [rsp+arg_10], rbx
0x1800059f5  push    rdi
0x1800059f6  sub     rsp, 280h
0x1800059fd  mov     rax, cs:__security_cookie
0x180005a04  xor     rax, rsp
0x180005a07  mov     [rsp+288h+var_18], rax
0x180005a0f  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180005a17  mov     rbx, rcx
0x180005a1a  mov     edi, edx
0x180005a1c  jnz     loc_180005B3B
0x180005a22  xorps   xmm0, xmm0
0x180005a25  xor     eax, eax
0x180005a27  mov     [rsp+288h+pActCtx.hModule], rax
0x180005a2c  movups  xmmword ptr [rsp+288h+pActCtx.cbSize], xmm0
0x180005a31  movups  xmmword ptr [rsp+288h+pActCtx.wProcessorArchitecture], xmm0
0x180005a36  movups  xmmword ptr [rsp+288h+pActCtx.lpResourceName], xmm0
0x180005a3b  test    rcx, rcx
0x180005a3e  jnz     short loc_180005A49
0x180005a40  call    cs:__imp_GetModuleHandleW
0x180005a46  mov     rbx, rax
0x180005a49  mov     r8d, 104h; nSize
0x180005a4f  lea     rdx, [rsp+288h+Filename]; lpFilename
0x180005a54  mov     rcx, rbx; hModule
0x180005a57  call    cs:__imp_GetModuleFileNameW
0x180005a5d  lea     rax, [rsp+288h+Filename]
0x180005a62  mov     [rsp+288h+pActCtx.cbSize], 38h ; '8'
0x180005a6a  mov     [rsp+288h+pActCtx.lpSource], rax
0x180005a6f  lea     rcx, [rsp+288h+pActCtx]; pActCtx
0x180005a74  movzx   eax, di
0x180005a77  mov     [rsp+288h+pActCtx.lpResourceName], rax
0x180005a7c  mov     [rsp+288h+pActCtx.dwFlags], 88h
0x180005a84  mov     [rsp+288h+pActCtx.hModule], rbx
0x180005a89  call    cs:__imp_CreateActCtxW
0x180005a8f  xor     edi, edi
0x180005a91  mov     rcx, rax; hActCtx
0x180005a94  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005a98  jz      loc_180005B2D
0x180005a9e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005aa5  lock cmpxchg cs:g_hActCtx, rcx
0x180005aae  jz      short loc_180005AB6
0x180005ab0  call    cs:__imp_ReleaseActCtx
0x180005ab6  cmp     cs:g_hinstCC, rdi
0x180005abd  jnz     short loc_180005B2D
0x180005abf  lea     rcx, [rsp+288h+ulCookie]
0x180005ac4  mov     [rsp+288h+ulCookie], rdi
0x180005ac9  call    SHActivateContext
0x180005ace  test    eax, eax
0x180005ad0  jnz     short loc_180005ADB
0x180005ad2  mov     cs:g_hinstCC, rdi
0x180005ad9  jmp     short loc_180005B11
0x180005adb  xor     edx, edx; hFile
0x180005add  lea     rcx, LibFileName; "comctl32.dll"
0x180005ae4  mov     r8d, 4000h; dwFlags
0x180005aea  call    cs:__imp_LoadLibraryExW
0x180005af0  mov     rdx, [rsp+288h+ulCookie]; ulCookie
0x180005af5  mov     rbx, rax
0x180005af8  test    rdx, rdx
0x180005afb  jz      short loc_180005B05
0x180005afd  xor     ecx, ecx; dwFlags
0x180005aff  call    cs:__imp_DeactivateActCtx
0x180005b05  mov     cs:g_hinstCC, rbx
0x180005b0c  test    rbx, rbx
0x180005b0f  jnz     short loc_180005B2D
0x180005b11  xor     edx, edx; hFile
0x180005b13  lea     rcx, LibFileName; "comctl32.dll"
0x180005b1a  mov     r8d, 4000h; dwFlags
0x180005b20  call    cs:__imp_LoadLibraryExW
0x180005b26  mov     cs:g_hinstCC, rax
0x180005b2d  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180005b35  jnz     short loc_180005B3B
0x180005b37  mov     eax, edi
0x180005b39  jmp     short loc_180005B40
0x180005b3b  mov     eax, 1
0x180005b40  mov     rcx, [rsp+288h+var_18]
0x180005b48  xor     rcx, rsp; StackCookie
0x180005b4b  call    __security_check_cookie
0x180005b50  mov     rbx, [rsp+288h+arg_10]
0x180005b58  add     rsp, 280h
0x180005b5f  pop     rdi
0x180005b60  retn
```
