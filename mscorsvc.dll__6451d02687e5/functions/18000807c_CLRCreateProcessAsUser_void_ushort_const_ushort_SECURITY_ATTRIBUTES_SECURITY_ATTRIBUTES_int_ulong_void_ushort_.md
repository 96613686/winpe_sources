# CLRCreateProcessAsUser(void *,ushort const *,ushort *,_SECURITY_ATTRIBUTES *,_SECURITY_ATTRIBUTES *,int,ulong,void *,ushort const *,_STARTUPINFOW *,_PROCESS_INFORMATION *)

- ea: `0x18000807c`
- end: `0x180008157`
- name: `?CLRCreateProcessAsUser@@YAHPEAXPEBGPEAGPEAU_SECURITY_ATTRIBUTES@@3HK01PEAU_STARTUPINFOW@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned __int16 *, struct _SECURITY_ATTRIBUTES *, struct _SECURITY_ATTRIBUTES *, int, unsigned int, void *, const unsigned __int16 *, struct _STARTUPINFOW *, struct _PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a784`

## callees

- `0x18000807c`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800080b5`
- `KERNEL32!LoadLibraryExW` at `0x1800080b5`
- `KERNEL32!GetProcAddress` at `0x1800080ca`
- `KERNEL32!GetProcAddress` at `0x1800080ca`

## string_xrefs

- `0x1800080ac`: `advapi32.dll`
- `0x1800080c0`: `CreateProcessAsUserW`

## pseudocode

```c
__int64 __fastcall CLRCreateProcessAsUser(
        void *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct _SECURITY_ATTRIBUTES *a4,
        struct _SECURITY_ATTRIBUTES *a5,
        int a6,
        unsigned int a7,
        void *a8,
        const unsigned __int16 *a9,
        struct _STARTUPINFOW *a10,
        struct _PROCESS_INFORMATION *a11)
{
  FARPROC ProcAddress; // r10
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FFA0;
  if ( qword_18006FFA0 )
    return ((__int64 (__fastcall *)(void *, const unsigned __int16 *, unsigned __int16 *, _QWORD, _QWORD, int, unsigned int, _QWORD, _QWORD, struct _STARTUPINFOW *, struct _PROCESS_INFORMATION *))ProcAddress)(
             a1,
             a2,
             a3,
             0,
             0,
             1,
             a7,
             0,
             0,
             a10,
             a11);
  if ( !bCreateProcessAsUserProbed
    && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FFA0)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "CreateProcessAsUserW"), qword_18006FFA0 = (__int64)ProcAddress),
        bCreateProcessAsUserProbed = 1,
        ProcAddress) )
  {
    return ((__int64 (__fastcall *)(void *, const unsigned __int16 *, unsigned __int16 *, _QWORD, _QWORD, int, unsigned int, _QWORD, _QWORD, struct _STARTUPINFOW *, struct _PROCESS_INFORMATION *))ProcAddress)(
             a1,
             a2,
             a3,
             0,
             0,
             1,
             a7,
             0,
             0,
             a10,
             a11);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18000807c  mov     [rsp+arg_0], rbx
0x180008081  mov     [rsp+arg_8], rsi
0x180008086  push    rdi
0x180008087  sub     rsp, 60h
0x18000808b  mov     r10, cs:qword_18006FFA0
0x180008092  mov     rbx, r8
0x180008095  mov     rdi, rdx
0x180008098  mov     rsi, rcx
0x18000809b  test    r10, r10
0x18000809e  jnz     short loc_1800080F3
0x1800080a0  cmp     cs:?bCreateProcessAsUserProbed@@3_NA, r10b; bool bCreateProcessAsUserProbed
0x1800080a7  jnz     short loc_1800080EF
0x1800080a9  xor     r8d, r8d; dwFlags
0x1800080ac  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x1800080b3  xor     edx, edx; hFile
0x1800080b5  call    cs:__imp_LoadLibraryExW
0x1800080bb  test    rax, rax
0x1800080be  jz      short loc_1800080DC
0x1800080c0  lea     rdx, aCreateprocessa; "CreateProcessAsUserW"
0x1800080c7  mov     rcx, rax; hModule
0x1800080ca  call    cs:__imp_GetProcAddress
0x1800080d0  mov     r10, rax
0x1800080d3  mov     cs:qword_18006FFA0, rax
0x1800080da  jmp     short loc_1800080E3
0x1800080dc  mov     r10, cs:qword_18006FFA0
0x1800080e3  mov     cs:?bCreateProcessAsUserProbed@@3_NA, 1; bool bCreateProcessAsUserProbed
0x1800080ea  test    r10, r10
0x1800080ed  jnz     short loc_1800080F3
0x1800080ef  xor     eax, eax
0x1800080f1  jmp     short loc_180008147
0x1800080f3  mov     rax, [rsp+68h+arg_50]
0x1800080fb  xor     r9d, r9d
0x1800080fe  mov     [rsp+68h+var_18], rax
0x180008103  mov     r8, rbx
0x180008106  mov     rax, [rsp+68h+arg_48]
0x18000810e  mov     rdx, rdi
0x180008111  mov     [rsp+68h+var_20], rax
0x180008116  mov     rcx, rsi
0x180008119  and     [rsp+68h+var_28], 0
0x18000811f  and     [rsp+68h+var_30], 0
0x180008125  mov     eax, [rsp+68h+arg_30]
0x18000812c  mov     [rsp+68h+var_38], eax
0x180008130  mov     rax, r10
0x180008133  mov     [rsp+68h+var_40], 1
0x18000813b  and     [rsp+68h+var_48], 0
0x180008141  call    cs:__guard_dispatch_icall_fptr
0x180008147  mov     rbx, [rsp+68h+arg_0]
0x18000814c  mov     rsi, [rsp+68h+arg_8]
0x180008151  add     rsp, 60h
0x180008155  pop     rdi
0x180008156  retn
```
