# ___crtCorExitProcess

- ea: `0x10033a3b`
- end: `0x10033a6f`
- name: `___crtCorExitProcess`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x10033a6f`

## callees

- `0x10033a3b`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x10033a4a`
- `KERNEL32!GetModuleHandleExW` at `0x10033a4a`
- `KERNEL32!GetProcAddress` at `0x10033a5c`
- `KERNEL32!GetProcAddress` at `0x10033a5c`

## string_xrefs

- `0x10033a43`: `mscoree.dll`

## pseudocode

```c
FARPROC __cdecl __crtCorExitProcess(int a1)
{
  HMODULE v1; // ecx
  FARPROC result; // eax
  HMODULE phModule; // [esp+0h] [ebp-4h] BYREF

  phModule = v1;
  result = (FARPROC)GetModuleHandleExW(0, L"mscoree.dll", &phModule);
  if ( result )
  {
    result = GetProcAddress(phModule, "CorExitProcess");
    if ( result )
      return (FARPROC)((int (__stdcall *)(int))result)(a1);
  }
  return result;
}

```

## disassembly

```asm
0x10033a3b  push    ebp
0x10033a3c  mov     ebp, esp
0x10033a3e  push    ecx
0x10033a3f  lea     eax, [ebp+phModule]
0x10033a42  push    eax; phModule
0x10033a43  push    offset aMscoreeDll
0x10033a48  push    0; dwFlags
0x10033a4a  call    ds:__imp__GetModuleHandleExW@12
0x10033a50  test    eax, eax
0x10033a52  jz      short loc_10033A6B
0x10033a54  push    offset aCorexitprocess
0x10033a59  push    [ebp+phModule]; hModule
0x10033a5c  call    ds:__imp__GetProcAddress@8
0x10033a62  test    eax, eax
0x10033a64  jz      short loc_10033A6B
0x10033a66  push    [ebp+arg_0]
0x10033a69  call    eax
0x10033a6b  mov     esp, ebp
0x10033a6d  pop     ebp
0x10033a6e  retn
```
