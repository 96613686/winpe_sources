# FLoadXoleHlp(void)

- ea: `0x100546db0`
- end: `0x100546deb`
- name: `?FLoadXoleHlp@@YAHXZ`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100546df4`

## callees

- `0x100546db0`

## import_xrefs

- `KERNEL32!LoadLibraryA` at `0x100546dbb`
- `KERNEL32!LoadLibraryA` at `0x100546dbb`
- `KERNEL32!FreeLibrary` at `0x100546dd1`
- `KERNEL32!FreeLibrary` at `0x100546dd1`

## string_xrefs

- `0x100546db4`: `XOLEHLP.DLL`

## pseudocode

```c
_BOOL8 FLoadXoleHlp(void)
{
  HMODULE LibraryA; // rcx

  LibraryA = LoadLibraryA("XOLEHLP.DLL");
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hXoleHlpDll, (signed __int64)LibraryA, 0) )
    FreeLibrary(LibraryA);
  return g_hXoleHlpDll != 0;
}

```

## disassembly

```asm
0x100546db0  sub     rsp, 28h
0x100546db4  lea     rcx, aXolehlpDll; "XOLEHLP.DLL"
0x100546dbb  call    cs:__imp_LoadLibraryA
0x100546dc1  mov     rcx, rax; hLibModule
0x100546dc4  xor     eax, eax
0x100546dc6  lock cmpxchg cs:?g_hXoleHlpDll@@3REAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hXoleHlpDll
0x100546dcf  jz      short loc_100546DD7
0x100546dd1  call    cs:__imp_FreeLibrary
0x100546dd7  mov     rcx, cs:?g_hXoleHlpDll@@3REAUHINSTANCE__@@EA; HINSTANCE__ * g_hXoleHlpDll
0x100546dde  xor     eax, eax
0x100546de0  test    rcx, rcx
0x100546de3  setnz   al
0x100546de6  add     rsp, 28h
0x100546dea  retn
```
