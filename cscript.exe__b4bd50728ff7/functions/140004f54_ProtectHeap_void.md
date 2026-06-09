# ProtectHeap(void)

- ea: `0x140004f54`
- end: `0x140004fc9`
- name: `?ProtectHeap@@YAHXZ`
- size: `117`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003e2c`

## callees

- `0x140004f54`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140004f95`
- `KERNEL32!GetProcAddress` at `0x140004f95`
- `KERNEL32!LoadLibraryExW` at `0x140004f7d`
- `KERNEL32!LoadLibraryExW` at `0x140004f7d`
- `KERNEL32!FreeLibrary` at `0x140004fb6`
- `KERNEL32!FreeLibrary` at `0x140004fb6`

## string_xrefs

- `0x140004f70`: `kernel32.dll`

## pseudocode

```c
HMODULE ProtectHeap(void)
{
  unsigned int v0; // edi
  HMODULE result; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax

  v0 = 0;
  if ( !Global::g_fWindowsVista )
    return (HMODULE)1;
  result = LoadLibraryExW(L"kernel32.dll", 0, 0x800u);
  v2 = result;
  if ( result )
  {
    ProcAddress = GetProcAddress(result, "HeapSetInformation");
    if ( ProcAddress )
      v0 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD))ProcAddress)(0, 1, 0);
    FreeLibrary(v2);
    return (HMODULE)v0;
  }
  return result;
}

```

## disassembly

```asm
0x140004f54  mov     [rsp+arg_0], rbx
0x140004f59  push    rdi
0x140004f5a  sub     rsp, 30h
0x140004f5e  xor     edi, edi
0x140004f60  cmp     cs:?g_fWindowsVista@Global@@2_NA, dil; bool Global::g_fWindowsVista
0x140004f67  jnz     short loc_140004F6E
0x140004f69  lea     eax, [rdi+1]
0x140004f6c  jmp     short loc_140004FBE
0x140004f6e  xor     edx, edx; hFile
0x140004f70  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x140004f77  mov     r8d, 800h; dwFlags
0x140004f7d  call    cs:__imp_LoadLibraryExW
0x140004f83  mov     rbx, rax
0x140004f86  test    rax, rax
0x140004f89  jz      short loc_140004FBE
0x140004f8b  lea     rdx, aHeapsetinforma; "HeapSetInformation"
0x140004f92  mov     rcx, rbx; hModule
0x140004f95  call    cs:__imp_GetProcAddress
0x140004f9b  test    rax, rax
0x140004f9e  jz      short loc_140004FB3
0x140004fa0  xor     r9d, r9d
0x140004fa3  xor     r8d, r8d
0x140004fa6  xor     ecx, ecx
0x140004fa8  lea     edx, [r9+1]
0x140004fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004fb1  mov     edi, eax
0x140004fb3  mov     rcx, rbx; hLibModule
0x140004fb6  call    cs:__imp_FreeLibrary
0x140004fbc  mov     eax, edi
0x140004fbe  mov     rbx, [rsp+38h+arg_0]
0x140004fc3  add     rsp, 30h
0x140004fc7  pop     rdi
0x140004fc8  retn
```
