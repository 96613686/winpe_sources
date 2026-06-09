# MilWerRegisterMemoryBlock(void const *,uint)

- ea: `0x14000f954`
- end: `0x14000f99f`
- name: `?MilWerRegisterMemoryBlock@@YAXPEBXI@Z`
- size: `75`
- prototype: `void __fastcall(const void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000f724`

## callees

- `0x14000f954`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f96a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f96a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f97f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f97f`

## string_xrefs

- `0x14000f963`: `kernel32.dll`

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
0x14000f954  mov     [rsp+arg_0], rbx
0x14000f959  push    rdi
0x14000f95a  sub     rsp, 20h
0x14000f95e  mov     rdi, rcx
0x14000f961  mov     ebx, edx
0x14000f963  lea     rcx, aKernel32Dll; "kernel32.dll"
0x14000f96a  call    cs:__imp_GetModuleHandleW
0x14000f970  test    rax, rax
0x14000f973  jz      short loc_14000F994
0x14000f975  lea     rdx, aWerregistermem; "WerRegisterMemoryBlock"
0x14000f97c  mov     rcx, rax; hModule
0x14000f97f  call    cs:__imp_GetProcAddress
0x14000f985  test    rax, rax
0x14000f988  jz      short loc_14000F994
0x14000f98a  mov     edx, ebx
0x14000f98c  mov     rcx, rdi
0x14000f98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f994  mov     rbx, [rsp+28h+arg_0]
0x14000f999  add     rsp, 20h
0x14000f99d  pop     rdi
0x14000f99e  retn
```
