# RdpWppGetCurrentThreadActivityIdPrefix(void)

- ea: `0x18001ef44`
- end: `0x18001efd2`
- name: `?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ`
- size: `142`
- prototype: `unsigned int(void)`
- caller_count: `23`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001e40c`
- `0x18001e550`
- `0x18001f870`
- `0x18001fa10`
- `0x18001fb94`
- `0x18001fd68`
- `0x18001fe90`
- `0x180020078`
- `0x1800205c0`
- `0x18002063c`
- `0x18002081c`
- `0x180020a90`
- `0x180020b30`
- `0x180020fe0`
- `0x180021430`
- `0x1800214c0`
- `0x18002a278`
- `0x18002a33c`
- `0x18002a608`
- `0x18002a888`
- `0x18002ab18`
- `0x18002ad68`
- `0x18002b4b8`

## callees

- `0x18001ef44`
- `0x18002b960`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ef97`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ef97`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001efb6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001efb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001ef81`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001ef81`

## string_xrefs

- `0x18001ef6c`: `Advapi32.dll`

## pseudocode

```c
__int64 RdpWppGetCurrentThreadActivityIdPrefix(void)
{
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v3; // [rsp+28h] [rbp-20h] BYREF
  __int64 v4; // [rsp+2Ch] [rbp-1Ch]
  int v5; // [rsp+34h] [rbp-14h]

  phModule = 0;
  v4 = 0;
  v5 = 0;
  v3 = -186580992;
  if ( GetModuleHandleExA(0, "Advapi32.dll", &phModule) )
  {
    ProcAddress = GetProcAddress(phModule, "EventActivityIdControl");
    if ( ProcAddress )
      ((void (__fastcall *)(__int64, unsigned int *))ProcAddress)(1, &v3);
    FreeLibrary(phModule);
  }
  return v3;
}

```

## disassembly

```asm
0x18001ef44  sub     rsp, 48h
0x18001ef48  mov     rax, cs:__security_cookie
0x18001ef4f  xor     rax, rsp
0x18001ef52  mov     [rsp+48h+var_10], rax
0x18001ef57  xor     eax, eax
0x18001ef59  mov     [rsp+48h+phModule], 0
0x18001ef62  lea     r8, [rsp+48h+phModule]; phModule
0x18001ef67  mov     [rsp+48h+var_1C], rax
0x18001ef6c  lea     rdx, aAdvapi32Dll_0; "Advapi32.dll"
0x18001ef73  mov     [rsp+48h+var_14], eax
0x18001ef77  xor     ecx, ecx; dwFlags
0x18001ef79  mov     [rsp+48h+var_20], 0F4E10000h
0x18001ef81  call    cs:__imp_GetModuleHandleExA
0x18001ef87  test    eax, eax
0x18001ef89  jz      short loc_18001EFBC
0x18001ef8b  mov     rcx, [rsp+48h+phModule]; hModule
0x18001ef90  lea     rdx, aEventactivityi; "EventActivityIdControl"
0x18001ef97  call    cs:__imp_GetProcAddress
0x18001ef9d  test    rax, rax
0x18001efa0  jz      short loc_18001EFB1
0x18001efa2  lea     rdx, [rsp+48h+var_20]
0x18001efa7  mov     ecx, 1
0x18001efac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efb1  mov     rcx, [rsp+48h+phModule]; hLibModule
0x18001efb6  call    cs:__imp_FreeLibrary
0x18001efbc  mov     eax, [rsp+48h+var_20]
0x18001efc0  mov     rcx, [rsp+48h+var_10]
0x18001efc5  xor     rcx, rsp; StackCookie
0x18001efc8  call    __security_check_cookie
0x18001efcd  add     rsp, 48h
0x18001efd1  retn
```
