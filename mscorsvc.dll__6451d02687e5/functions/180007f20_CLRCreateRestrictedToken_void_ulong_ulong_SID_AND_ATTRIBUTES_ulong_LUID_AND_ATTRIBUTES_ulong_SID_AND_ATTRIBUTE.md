# CLRCreateRestrictedToken(void *,ulong,ulong,_SID_AND_ATTRIBUTES *,ulong,_LUID_AND_ATTRIBUTES *,ulong,_SID_AND_ATTRIBUTES *,void * *)

- ea: `0x180007f20`
- end: `0x180007fd2`
- name: `?CLRCreateRestrictedToken@@YAHPEAXKKPEAU_SID_AND_ATTRIBUTES@@KPEAU_LUID_AND_ATTRIBUTES@@K1PEAPEAX@Z`
- size: `178`
- prototype: `__int64 __fastcall(void *, __int64, __int64, struct _SID_AND_ATTRIBUTES *, unsigned int, struct _LUID_AND_ATTRIBUTES *, unsigned int, struct _SID_AND_ATTRIBUTES *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800280bc`

## callees

- `0x180007f20`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180007f4a`
- `KERNEL32!LoadLibraryExW` at `0x180007f4a`
- `KERNEL32!GetProcAddress` at `0x180007f5f`
- `KERNEL32!GetProcAddress` at `0x180007f5f`

## string_xrefs

- `0x180007f41`: `advapi32.dll`
- `0x180007f55`: `CreateRestrictedToken`

## pseudocode

```c
__int64 __fastcall CLRCreateRestrictedToken(
        void *a1,
        __int64 a2,
        __int64 a3,
        struct _SID_AND_ATTRIBUTES *a4,
        unsigned int a5,
        struct _LUID_AND_ATTRIBUTES *a6,
        unsigned int a7,
        struct _SID_AND_ATTRIBUTES *a8,
        void **a9)
{
  FARPROC ProcAddress; // r10
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FF90;
  if ( qword_18006FF90 )
    return ((__int64 (__fastcall *)(void *, _QWORD, _QWORD, _QWORD, unsigned int, struct _LUID_AND_ATTRIBUTES *, _DWORD, _QWORD, void **))ProcAddress)(
             a1,
             0,
             0,
             0,
             a5,
             a6,
             0,
             0,
             a9);
  if ( !bCreateRestrictedTokenProbed
    && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FF90)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "CreateRestrictedToken"), qword_18006FF90 = (__int64)ProcAddress),
        bCreateRestrictedTokenProbed = 1,
        ProcAddress) )
  {
    return ((__int64 (__fastcall *)(void *, _QWORD, _QWORD, _QWORD, unsigned int, struct _LUID_AND_ATTRIBUTES *, _DWORD, _QWORD, void **))ProcAddress)(
             a1,
             0,
             0,
             0,
             a5,
             a6,
             0,
             0,
             a9);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180007f20  push    rbx
0x180007f22  sub     rsp, 50h
0x180007f26  mov     r10, cs:qword_18006FF90
0x180007f2d  mov     rbx, rcx
0x180007f30  test    r10, r10
0x180007f33  jnz     short loc_180007F88
0x180007f35  cmp     cs:?bCreateRestrictedTokenProbed@@3_NA, r10b; bool bCreateRestrictedTokenProbed
0x180007f3c  jnz     short loc_180007F84
0x180007f3e  xor     r8d, r8d; dwFlags
0x180007f41  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x180007f48  xor     edx, edx; hFile
0x180007f4a  call    cs:__imp_LoadLibraryExW
0x180007f50  test    rax, rax
0x180007f53  jz      short loc_180007F71
0x180007f55  lea     rdx, aCreaterestrict; "CreateRestrictedToken"
0x180007f5c  mov     rcx, rax; hModule
0x180007f5f  call    cs:__imp_GetProcAddress
0x180007f65  mov     r10, rax
0x180007f68  mov     cs:qword_18006FF90, rax
0x180007f6f  jmp     short loc_180007F78
0x180007f71  mov     r10, cs:qword_18006FF90
0x180007f78  mov     cs:?bCreateRestrictedTokenProbed@@3_NA, 1; bool bCreateRestrictedTokenProbed
0x180007f7f  test    r10, r10
0x180007f82  jnz     short loc_180007F88
0x180007f84  xor     eax, eax
0x180007f86  jmp     short loc_180007FCC
0x180007f88  mov     rax, [rsp+58h+arg_40]
0x180007f90  xor     r9d, r9d
0x180007f93  mov     [rsp+58h+var_18], rax
0x180007f98  xor     r8d, r8d
0x180007f9b  and     [rsp+58h+var_20], 0
0x180007fa1  xor     edx, edx
0x180007fa3  mov     rax, [rsp+58h+arg_28]
0x180007fab  mov     rcx, rbx
0x180007fae  and     [rsp+58h+var_28], 0
0x180007fb3  mov     [rsp+58h+var_30], rax
0x180007fb8  mov     eax, [rsp+58h+arg_20]
0x180007fbf  mov     [rsp+58h+var_38], eax
0x180007fc3  mov     rax, r10
0x180007fc6  call    cs:__guard_dispatch_icall_fptr
0x180007fcc  add     rsp, 50h
0x180007fd0  pop     rbx
0x180007fd1  retn
```
