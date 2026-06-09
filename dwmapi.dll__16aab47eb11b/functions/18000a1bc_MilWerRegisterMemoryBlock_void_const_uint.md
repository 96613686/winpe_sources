# MilWerRegisterMemoryBlock(void const *,uint)

- ea: `0x18000a1bc`
- end: `0x18000a207`
- name: `?MilWerRegisterMemoryBlock@@YAXPEBXI@Z`
- size: `75`
- prototype: `void __fastcall(const void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800034c0`

## callees

- `0x18000a1bc`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a1d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a1d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1e7`

## string_xrefs

- `0x18000a1cb`: `kernel32.dll`

## pseudocode

```c
void __fastcall MilWerRegisterMemoryBlock(const void *a1, unsigned int a2)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "WerRegisterMemoryBlock");
    if ( ProcAddress )
      ((void (__fastcall *)(const void *, _QWORD))ProcAddress)(a1, a2);
  }
}

```

## disassembly

```asm
0x18000a1bc  mov     [rsp+arg_0], rbx
0x18000a1c1  push    rdi
0x18000a1c2  sub     rsp, 20h
0x18000a1c6  mov     rdi, rcx
0x18000a1c9  mov     ebx, edx
0x18000a1cb  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18000a1d2  call    cs:__imp_GetModuleHandleW
0x18000a1d8  test    rax, rax
0x18000a1db  jz      short loc_18000A1FC
0x18000a1dd  lea     rdx, aWerregistermem; "WerRegisterMemoryBlock"
0x18000a1e4  mov     rcx, rax; hModule
0x18000a1e7  call    cs:__imp_GetProcAddress
0x18000a1ed  test    rax, rax
0x18000a1f0  jz      short loc_18000A1FC
0x18000a1f2  mov     edx, ebx
0x18000a1f4  mov     rcx, rdi
0x18000a1f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1fc  mov     rbx, [rsp+28h+arg_0]
0x18000a201  add     rsp, 20h
0x18000a205  pop     rdi
0x18000a206  retn
```
