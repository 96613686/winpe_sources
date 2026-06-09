# DllMain

- ea: `0x180010ea4`
- end: `0x180010f19`
- name: `DllMain`
- size: `117`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001384`

## callees

- `0x180010ea4`
- `0x18001c298`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180010ed8`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180010ed8`
- `KERNEL32!ReleaseActCtx` at `0x180010ef0`
- `KERNEL32!ReleaseActCtx` at `0x180010ef0`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL result; // eax
  DWORD v5; // edx

  result = 0;
  if ( fdwReason )
  {
    v5 = fdwReason - 1;
    if ( v5 )
    {
      if ( v5 - 1 > 1 )
        return result;
    }
    else
    {
      SHFusionInitializeFromModuleID(hinstDLL);
      g_hInstDll = hinstDLL;
      DisableThreadLibraryCalls(hinstDLL);
    }
  }
  else
  {
    if ( g_hActCtx != (HANDLE)-1LL )
    {
      ReleaseActCtx(g_hActCtx);
      g_hActCtx = (HANDLE)-1LL;
    }
    if ( hModule )
      hModule = (HMODULE)-1LL;
  }
  return 1;
}

```

## disassembly

```asm
0x180010ea4  push    rbx
0x180010ea6  sub     rsp, 20h
0x180010eaa  xor     eax, eax
0x180010eac  mov     rbx, rcx
0x180010eaf  test    edx, edx
0x180010eb1  jz      short loc_180010EE0
0x180010eb3  sub     edx, 1
0x180010eb6  jz      short loc_180010EC4
0x180010eb8  sub     edx, 1
0x180010ebb  jz      short loc_180010F0E
0x180010ebd  cmp     edx, 1
0x180010ec0  jnz     short loc_180010F13
0x180010ec2  jmp     short loc_180010F0E
0x180010ec4  mov     edx, 7Bh ; '{'
0x180010ec9  call    SHFusionInitializeFromModuleID
0x180010ece  mov     rcx, rbx; hLibModule
0x180010ed1  mov     cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstDll
0x180010ed8  call    cs:__imp_DisableThreadLibraryCalls
0x180010ede  jmp     short loc_180010F0E
0x180010ee0  mov     rcx, cs:g_hActCtx; hActCtx
0x180010ee7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180010eeb  cmp     rcx, rbx
0x180010eee  jz      short loc_180010EFD
0x180010ef0  call    cs:__imp_ReleaseActCtx
0x180010ef6  mov     cs:g_hActCtx, rbx
0x180010efd  cmp     cs:hModule, 0
0x180010f05  jz      short loc_180010F0E
0x180010f07  mov     cs:hModule, rbx
0x180010f0e  mov     eax, 1
0x180010f13  add     rsp, 20h
0x180010f17  pop     rbx
0x180010f18  retn
```
