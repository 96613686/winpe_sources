# CLRWTSFreeMemory(void *)

- ea: `0x180007e1c`
- end: `0x180007e93`
- name: `?CLRWTSFreeMemory@@YAHPEAX@Z`
- size: `119`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007130`

## callees

- `0x180007e1c`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180007e45`
- `KERNEL32!LoadLibraryExW` at `0x180007e45`
- `KERNEL32!GetProcAddress` at `0x180007e5a`
- `KERNEL32!GetProcAddress` at `0x180007e5a`

## string_xrefs

- `0x180007e3c`: `Wtsapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=38
__int64 __fastcall CLRWTSFreeMemory(void *a1)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FF78;
  if ( qword_18006FF78 )
    return ((__int64 (__fastcall *)(void *))ProcAddress)(a1);
  if ( !bWTSFreeMemoryProbed
    && ((Library = LoadLibraryExW(L"Wtsapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FF78)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "WTSFreeMemory"), qword_18006FF78 = (__int64)ProcAddress),
        bWTSFreeMemoryProbed = 1,
        ProcAddress) )
  {
    return ((__int64 (__fastcall *)(void *))ProcAddress)(a1);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180007e1c  push    rbx
0x180007e1e  sub     rsp, 20h
0x180007e22  mov     rax, cs:qword_18006FF78
0x180007e29  mov     rbx, rcx
0x180007e2c  test    rax, rax
0x180007e2f  jnz     short loc_180007E84
0x180007e31  cmp     cs:?bWTSFreeMemoryProbed@@3_NA, al; bool bWTSFreeMemoryProbed
0x180007e37  jnz     short loc_180007E7C
0x180007e39  xor     r8d, r8d; dwFlags
0x180007e3c  lea     rcx, aWtsapi32Dll; "Wtsapi32.dll"
0x180007e43  xor     edx, edx; hFile
0x180007e45  call    cs:__imp_LoadLibraryExW
0x180007e4b  test    rax, rax
0x180007e4e  jz      short loc_180007E69
0x180007e50  lea     rdx, aWtsfreememory; "WTSFreeMemory"
0x180007e57  mov     rcx, rax; hModule
0x180007e5a  call    cs:__imp_GetProcAddress
0x180007e60  mov     cs:qword_18006FF78, rax
0x180007e67  jmp     short loc_180007E70
0x180007e69  mov     rax, cs:qword_18006FF78
0x180007e70  mov     cs:?bWTSFreeMemoryProbed@@3_NA, 1; bool bWTSFreeMemoryProbed
0x180007e77  test    rax, rax
0x180007e7a  jnz     short loc_180007E84
0x180007e7c  xor     eax, eax
0x180007e7e  add     rsp, 20h
0x180007e82  pop     rbx
0x180007e83  retn
0x180007e84  mov     rcx, rbx
0x180007e87  add     rsp, 20h
0x180007e8b  pop     rbx
0x180007e8c  jmp     cs:__guard_dispatch_icall_fptr
```
