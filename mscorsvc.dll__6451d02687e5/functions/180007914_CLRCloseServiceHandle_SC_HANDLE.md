# CLRCloseServiceHandle(SC_HANDLE__ *)

- ea: `0x180007914`
- end: `0x18000798b`
- name: `?CLRCloseServiceHandle@@YAHPEAUSC_HANDLE__@@@Z`
- size: `119`
- prototype: `__int64 __fastcall(struct SC_HANDLE__ *)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001a690`
- `0x18001ac30`
- `0x18001aca8`
- `0x18001ada4`
- `0x18001b128`
- `0x18001b57c`
- `0x18001b800`
- `0x18001b9d0`
- `0x18001bc48`
- `0x18001bf08`

## callees

- `0x180007914`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000793d`
- `KERNEL32!LoadLibraryExW` at `0x18000793d`
- `KERNEL32!GetProcAddress` at `0x180007952`
- `KERNEL32!GetProcAddress` at `0x180007952`

## string_xrefs

- `0x180007934`: `advapi32.dll`
- `0x180007948`: `CloseServiceHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CLRCloseServiceHandle(struct SC_HANDLE__ *a1)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FEF0;
  if ( qword_18006FEF0 )
    return ((__int64 (__fastcall *)(struct SC_HANDLE__ *))ProcAddress)(a1);
  if ( !bCloseServiceHandleProbed
    && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FEF0)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "CloseServiceHandle"), qword_18006FEF0 = (__int64)ProcAddress),
        bCloseServiceHandleProbed = 1,
        ProcAddress) )
  {
    return ((__int64 (__fastcall *)(struct SC_HANDLE__ *))ProcAddress)(a1);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180007914  push    rbx
0x180007916  sub     rsp, 20h
0x18000791a  mov     rax, cs:qword_18006FEF0
0x180007921  mov     rbx, rcx
0x180007924  test    rax, rax
0x180007927  jnz     short loc_18000797C
0x180007929  cmp     cs:?bCloseServiceHandleProbed@@3_NA, al; bool bCloseServiceHandleProbed
0x18000792f  jnz     short loc_180007974
0x180007931  xor     r8d, r8d; dwFlags
0x180007934  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x18000793b  xor     edx, edx; hFile
0x18000793d  call    cs:__imp_LoadLibraryExW
0x180007943  test    rax, rax
0x180007946  jz      short loc_180007961
0x180007948  lea     rdx, aCloseserviceha; "CloseServiceHandle"
0x18000794f  mov     rcx, rax; hModule
0x180007952  call    cs:__imp_GetProcAddress
0x180007958  mov     cs:qword_18006FEF0, rax
0x18000795f  jmp     short loc_180007968
0x180007961  mov     rax, cs:qword_18006FEF0
0x180007968  mov     cs:?bCloseServiceHandleProbed@@3_NA, 1; bool bCloseServiceHandleProbed
0x18000796f  test    rax, rax
0x180007972  jnz     short loc_18000797C
0x180007974  xor     eax, eax
0x180007976  add     rsp, 20h
0x18000797a  pop     rbx
0x18000797b  retn
0x18000797c  mov     rcx, rbx
0x18000797f  add     rsp, 20h
0x180007983  pop     rbx
0x180007984  jmp     cs:__guard_dispatch_icall_fptr
```
