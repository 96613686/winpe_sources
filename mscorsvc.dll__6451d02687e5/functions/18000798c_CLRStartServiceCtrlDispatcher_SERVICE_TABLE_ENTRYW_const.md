# CLRStartServiceCtrlDispatcher(_SERVICE_TABLE_ENTRYW * const)

- ea: `0x18000798c`
- end: `0x180007a03`
- name: `?CLRStartServiceCtrlDispatcher@@YAHQEAU_SERVICE_TABLE_ENTRYW@@@Z`
- size: `119`
- prototype: `__int64 __fastcall(struct _SERVICE_TABLE_ENTRYW *const)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18001bcfc`

## callees

- `0x18000798c`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800079b5`
- `KERNEL32!LoadLibraryExW` at `0x1800079b5`
- `KERNEL32!GetProcAddress` at `0x1800079ca`
- `KERNEL32!GetProcAddress` at `0x1800079ca`

## string_xrefs

- `0x1800079ac`: `advapi32.dll`
- `0x1800079c0`: `StartServiceCtrlDispatcherW`

## pseudocode

```c
__int64 __fastcall CLRStartServiceCtrlDispatcher(struct _SERVICE_TABLE_ENTRYW *const a1)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FF00;
  if ( qword_18006FF00 )
    return ((__int64 (__fastcall *)(struct _SERVICE_TABLE_ENTRYW *const))ProcAddress)(a1);
  if ( !bStartServiceCtrlDispatcherProbed
    && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FF00)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "StartServiceCtrlDispatcherW"),
                  qword_18006FF00 = (__int64)ProcAddress),
        bStartServiceCtrlDispatcherProbed = 1,
        ProcAddress) )
  {
    return ((__int64 (__fastcall *)(struct _SERVICE_TABLE_ENTRYW *const))ProcAddress)(a1);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18000798c  push    rbx
0x18000798e  sub     rsp, 20h
0x180007992  mov     rax, cs:qword_18006FF00
0x180007999  mov     rbx, rcx
0x18000799c  test    rax, rax
0x18000799f  jnz     short loc_1800079F4
0x1800079a1  cmp     cs:?bStartServiceCtrlDispatcherProbed@@3_NA, al; bool bStartServiceCtrlDispatcherProbed
0x1800079a7  jnz     short loc_1800079EC
0x1800079a9  xor     r8d, r8d; dwFlags
0x1800079ac  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x1800079b3  xor     edx, edx; hFile
0x1800079b5  call    cs:__imp_LoadLibraryExW
0x1800079bb  test    rax, rax
0x1800079be  jz      short loc_1800079D9
0x1800079c0  lea     rdx, aStartservicect; "StartServiceCtrlDispatcherW"
0x1800079c7  mov     rcx, rax; hModule
0x1800079ca  call    cs:__imp_GetProcAddress
0x1800079d0  mov     cs:qword_18006FF00, rax
0x1800079d7  jmp     short loc_1800079E0
0x1800079d9  mov     rax, cs:qword_18006FF00
0x1800079e0  mov     cs:?bStartServiceCtrlDispatcherProbed@@3_NA, 1; bool bStartServiceCtrlDispatcherProbed
0x1800079e7  test    rax, rax
0x1800079ea  jnz     short loc_1800079F4
0x1800079ec  xor     eax, eax
0x1800079ee  add     rsp, 20h
0x1800079f2  pop     rbx
0x1800079f3  retn
0x1800079f4  mov     rcx, rbx
0x1800079f7  add     rsp, 20h
0x1800079fb  pop     rbx
0x1800079fc  jmp     cs:__guard_dispatch_icall_fptr
```
