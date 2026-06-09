# DeviceSetDevConfig

- ea: `0x1800101d0`
- end: `0x1800102a0`
- name: `DeviceSetDevConfig`
- size: `208`
- prototype: `DWORD __fastcall(__int64, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000d92c`
- `0x1800101d0`
- `0x180012340`
- `0x180012f20`
- `0x180029266`

## import_xrefs

- `msvcrt!_stricmp` at `0x180010210`
- `msvcrt!_stricmp` at `0x180010210`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010239`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010239`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001022b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001022b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001025c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001028f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001025c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001028f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010252`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010285`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010252`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010285`

## string_xrefs

- `0x1800101ef`: `DeviceSetDevConfig: port 0x%x not found`

## pseudocode

```c
DWORD __fastcall DeviceSetDevConfig(__int64 a1, const void *a2, unsigned int a3)
{
  SIZE_T v3; // rsi
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  void *v12; // rcx
  HLOCAL v13; // rax
  HANDLE v14; // rcx

  v3 = a3;
  v5 = LookUpControlBlock();
  v6 = v5;
  if ( !v5 )
  {
    RasTapiTrace("DeviceSetDevConfig: port 0x%x not found");
    return 615;
  }
  if ( _stricmp((const char *)(v5 + 64), "MODEM") )
    return 0;
  GetMutex(v9, v8, v10, v11);
  v12 = *(void **)(v6 + 1064);
  if ( v12 )
    LocalFree(v12);
  v13 = LocalAlloc(0x40u, v3);
  *(_QWORD *)(v6 + 1064) = v13;
  if ( v13 )
  {
    memcpy_0(v13, a2, v3);
    v14 = RasTapiMutex;
    *(_DWORD *)(v6 + 1072) = v3;
    if ( !ReleaseMutex(v14) )
      GetLastError();
    return 0;
  }
  if ( !ReleaseMutex(RasTapiMutex) )
    GetLastError();
  return GetLastError();
}

```

## disassembly

```asm
0x1800101d0  push    rbx
0x1800101d2  push    rbp
0x1800101d3  push    rsi
0x1800101d4  push    rdi
0x1800101d5  sub     rsp, 28h
0x1800101d9  mov     esi, r8d
0x1800101dc  mov     rbp, rdx
0x1800101df  call    LookUpControlBlock
0x1800101e4  mov     rbx, rax
0x1800101e7  test    rax, rax
0x1800101ea  jnz     short loc_180010205
0x1800101ec  mov     rdx, rcx
0x1800101ef  lea     rcx, aDevicesetdevco_0; "DeviceSetDevConfig: port 0x%x not found"
0x1800101f6  call    RasTapiTrace
0x1800101fb  mov     eax, 267h
0x180010200  jmp     loc_180010297
0x180010205  lea     rcx, [rax+40h]; String1
0x180010209  lea     rdx, aModem; "MODEM"
0x180010210  call    cs:__imp__stricmp
0x180010216  test    eax, eax
0x180010218  jnz     short loc_180010295
0x18001021a  call    GetMutex
0x18001021f  mov     rcx, [rbx+428h]; hMem
0x180010226  test    rcx, rcx
0x180010229  jz      short loc_180010231
0x18001022b  call    cs:__imp_LocalFree
0x180010231  mov     rdx, rsi; uBytes
0x180010234  mov     ecx, 40h ; '@'; uFlags
0x180010239  call    cs:__imp_LocalAlloc
0x18001023f  mov     [rbx+428h], rax
0x180010246  test    rax, rax
0x180010249  jnz     short loc_18001026A
0x18001024b  mov     rcx, cs:RasTapiMutex; hMutex
0x180010252  call    cs:__imp_ReleaseMutex
0x180010258  test    eax, eax
0x18001025a  jnz     short loc_180010262
0x18001025c  call    cs:__imp_GetLastError
0x180010262  call    cs:__imp_GetLastError
0x180010268  jmp     short loc_180010297
0x18001026a  mov     r8, rsi; Size
0x18001026d  mov     rdx, rbp; Src
0x180010270  mov     rcx, rax; void *
0x180010273  call    memcpy_0
0x180010278  mov     rcx, cs:RasTapiMutex; hMutex
0x18001027f  mov     [rbx+430h], esi
0x180010285  call    cs:__imp_ReleaseMutex
0x18001028b  test    eax, eax
0x18001028d  jnz     short loc_180010295
0x18001028f  call    cs:__imp_GetLastError
0x180010295  xor     eax, eax
0x180010297  add     rsp, 28h
0x18001029b  pop     rdi
0x18001029c  pop     rsi
0x18001029d  pop     rbp
0x18001029e  pop     rbx
0x18001029f  retn
```
