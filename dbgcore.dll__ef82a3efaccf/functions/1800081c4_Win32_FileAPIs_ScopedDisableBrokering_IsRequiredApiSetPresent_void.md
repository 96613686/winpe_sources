# Win32::FileAPIs::ScopedDisableBrokering::IsRequiredApiSetPresent(void)

- ea: `0x1800081c4`
- end: `0x180008255`
- name: `?IsRequiredApiSetPresent@ScopedDisableBrokering@FileAPIs@Win32@@SA_NXZ`
- size: `145`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800100f0`

## callees

- `0x1800081c4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1800081f2`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1800081f2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180008208`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180008208`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000823e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000823e`

## string_xrefs

- `0x1800081e9`: `ntdll.dll`
- `0x18000821a`: `ext-ms-win-winrt-storage-win32broker-l1-1-0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool Win32::FileAPIs::ScopedDisableBrokering::IsRequiredApiSetPresent(void)
{
  int v0; // eax
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+40h] [rbp+8h] BYREF

  v0 = Win32::FileAPIs::ScopedDisableBrokering::ApiSetState;
  if ( !Win32::FileAPIs::ScopedDisableBrokering::ApiSetState )
  {
    phModule = 0;
    if ( GetModuleHandleExW(0, L"ntdll.dll", &phModule)
      && (ProcAddress = GetProcAddress(phModule, "RtlIsApiSetImplemented")) != 0 )
    {
      v0 = ((((int (__fastcall *)(const char *))ProcAddress)("ext-ms-win-winrt-storage-win32broker-l1-1-0") >> 31) & 1)
         + 1;
    }
    else
    {
      v0 = 2;
    }
    Win32::FileAPIs::ScopedDisableBrokering::ApiSetState = v0;
    if ( phModule )
    {
      FreeLibrary(phModule);
      v0 = Win32::FileAPIs::ScopedDisableBrokering::ApiSetState;
    }
  }
  return v0 == 1;
}

```

## disassembly

```asm
0x1800081c4  sub     rsp, 38h
0x1800081c8  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800081d1  mov     eax, cs:?ApiSetState@ScopedDisableBrokering@FileAPIs@Win32@@0W4ApiPresence@123@A; Win32::FileAPIs::ScopedDisableBrokering::ApiPresence Win32::FileAPIs::ScopedDisableBrokering::ApiSetState
0x1800081d7  test    eax, eax
0x1800081d9  jnz     short loc_18000824A
0x1800081db  mov     [rsp+38h+phModule], 0
0x1800081e4  lea     r8, [rsp+38h+phModule]; phModule
0x1800081e9  lea     rdx, ModuleName; "ntdll.dll"
0x1800081f0  xor     ecx, ecx; dwFlags
0x1800081f2  call    cs:__imp_GetModuleHandleExW
0x1800081f8  test    eax, eax
0x1800081fa  jz      short loc_180008213
0x1800081fc  lea     rdx, aRtlisapisetimp; "RtlIsApiSetImplemented"
0x180008203  mov     rcx, [rsp+38h+phModule]; hModule
0x180008208  call    cs:__imp_GetProcAddress
0x18000820e  test    rax, rax
0x180008211  jnz     short loc_18000821A
0x180008213  mov     eax, 2
0x180008218  jmp     short loc_18000822E
0x18000821a  lea     rcx, aExtMsWinWinrtS; "ext-ms-win-winrt-storage-win32broker-l1"...
0x180008221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008226  sar     eax, 1Fh
0x180008229  and     eax, 1
0x18000822c  inc     eax
0x18000822e  mov     cs:?ApiSetState@ScopedDisableBrokering@FileAPIs@Win32@@0W4ApiPresence@123@A, eax; Win32::FileAPIs::ScopedDisableBrokering::ApiPresence Win32::FileAPIs::ScopedDisableBrokering::ApiSetState
0x180008234  mov     rcx, [rsp+38h+phModule]; hLibModule
0x180008239  test    rcx, rcx
0x18000823c  jz      short loc_18000824A
0x18000823e  call    cs:__imp_FreeLibrary
0x180008244  mov     eax, cs:?ApiSetState@ScopedDisableBrokering@FileAPIs@Win32@@0W4ApiPresence@123@A; Win32::FileAPIs::ScopedDisableBrokering::ApiPresence Win32::FileAPIs::ScopedDisableBrokering::ApiSetState
0x18000824a  cmp     eax, 1
0x18000824d  setz    al
0x180008250  add     rsp, 38h
0x180008254  retn
```
