# HeapSetInformation_HeapEnableTerminationOnCorruption_Downlevel(void)

- ea: `0x1400062a4`
- end: `0x1400062fa`
- name: `?HeapSetInformation_HeapEnableTerminationOnCorruption_Downlevel@@YAXXZ`
- size: `86`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400011e4`

## callees

- `0x1400062a4`
- `0x14000a010`

## import_xrefs

- `KERNEL32!GetVersion` at `0x1400062a8`
- `KERNEL32!GetVersion` at `0x1400062a8`
- `KERNEL32!GetProcAddress` at `0x1400062d9`
- `KERNEL32!GetProcAddress` at `0x1400062d9`
- `KERNEL32!GetModuleHandleW` at `0x1400062c4`
- `KERNEL32!GetModuleHandleW` at `0x1400062c4`

## string_xrefs

- `0x1400062bd`: `Kernel32.dll`

## pseudocode

```c
void HeapSetInformation_HeapEnableTerminationOnCorruption_Downlevel(void)
{
  signed int Version; // eax
  unsigned int v1; // ecx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  Version = GetVersion();
  v1 = 0;
  if ( Version >= 0 )
    v1 = (unsigned __int8)Version;
  if ( v1 >= 6 )
  {
    ModuleHandleW = GetModuleHandleW(L"Kernel32.dll");
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "HeapSetInformation");
      if ( ProcAddress )
        ((void (__fastcall *)(_QWORD, __int64, _QWORD))ProcAddress)(0, 1, 0);
    }
  }
}

```

## disassembly

```asm
0x1400062a4  sub     rsp, 38h
0x1400062a8  call    cs:__imp_GetVersion
0x1400062ae  xor     ecx, ecx
0x1400062b0  movzx   edx, al
0x1400062b3  test    eax, eax
0x1400062b5  cmovns  ecx, edx
0x1400062b8  cmp     ecx, 6
0x1400062bb  jb      short loc_1400062F5
0x1400062bd  lea     rcx, aKernel32Dll_1; "Kernel32.dll"
0x1400062c4  call    cs:__imp_GetModuleHandleW
0x1400062ca  test    rax, rax
0x1400062cd  jz      short loc_1400062F5
0x1400062cf  lea     rdx, aHeapsetinforma; "HeapSetInformation"
0x1400062d6  mov     rcx, rax; hModule
0x1400062d9  call    cs:__imp_GetProcAddress
0x1400062df  test    rax, rax
0x1400062e2  jz      short loc_1400062F5
0x1400062e4  xor     r9d, r9d
0x1400062e7  xor     r8d, r8d
0x1400062ea  xor     ecx, ecx
0x1400062ec  lea     edx, [r9+1]
0x1400062f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062f5  add     rsp, 38h
0x1400062f9  retn
```
