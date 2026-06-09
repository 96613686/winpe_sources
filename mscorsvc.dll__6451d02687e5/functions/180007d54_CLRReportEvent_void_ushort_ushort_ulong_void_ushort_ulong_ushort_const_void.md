# CLRReportEvent(void *,ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *)

- ea: `0x180007d54`
- end: `0x180007e19`
- name: `?CLRReportEvent@@YAHPEAXGGK0GKPEAPEBG0@Z`
- size: `197`
- prototype: `__int64 __fastcall(void *, unsigned __int16, __int64, unsigned int, void *, unsigned __int16, unsigned int, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002dfa0`

## callees

- `0x180007d54`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180007d8d`
- `KERNEL32!LoadLibraryExW` at `0x180007d8d`
- `KERNEL32!GetProcAddress` at `0x180007da2`
- `KERNEL32!GetProcAddress` at `0x180007da2`

## string_xrefs

- `0x180007d84`: `advapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=49
__int64 __fastcall CLRReportEvent(
        void *a1,
        unsigned __int16 a2,
        __int64 a3,
        unsigned int a4,
        void *a5,
        unsigned __int16 a6,
        unsigned int a7,
        const unsigned __int16 **a8)
{
  FARPROC ProcAddress; // r10
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FF58;
  if ( qword_18006FF58 )
    return ((__int64 (__fastcall *)(void *, _QWORD, _QWORD, _QWORD, _QWORD, unsigned __int16, _DWORD, const unsigned __int16 **, _QWORD))ProcAddress)(
             a1,
             a2,
             0,
             a4,
             0,
             a6,
             0,
             a8,
             0);
  if ( !bReportEventProbed
    && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FF58)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "ReportEventW"), qword_18006FF58 = (__int64)ProcAddress),
        bReportEventProbed = 1,
        ProcAddress) )
  {
    return ((__int64 (__fastcall *)(void *, _QWORD, _QWORD, _QWORD, _QWORD, unsigned __int16, _DWORD, const unsigned __int16 **, _QWORD))ProcAddress)(
             a1,
             a2,
             0,
             a4,
             0,
             a6,
             0,
             a8,
             0);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180007d54  mov     [rsp+arg_0], rbx
0x180007d59  mov     [rsp+arg_8], rsi
0x180007d5e  push    rdi
0x180007d5f  sub     rsp, 50h
0x180007d63  mov     r10, cs:qword_18006FF58
0x180007d6a  mov     ebx, r9d
0x180007d6d  movzx   edi, dx
0x180007d70  mov     rsi, rcx
0x180007d73  test    r10, r10
0x180007d76  jnz     short loc_180007DCB
0x180007d78  cmp     cs:?bReportEventProbed@@3_NA, r10b; bool bReportEventProbed
0x180007d7f  jnz     short loc_180007DC7
0x180007d81  xor     r8d, r8d; dwFlags
0x180007d84  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x180007d8b  xor     edx, edx; hFile
0x180007d8d  call    cs:__imp_LoadLibraryExW
0x180007d93  test    rax, rax
0x180007d96  jz      short loc_180007DB4
0x180007d98  lea     rdx, aReporteventw; "ReportEventW"
0x180007d9f  mov     rcx, rax; hModule
0x180007da2  call    cs:__imp_GetProcAddress
0x180007da8  mov     r10, rax
0x180007dab  mov     cs:qword_18006FF58, rax
0x180007db2  jmp     short loc_180007DBB
0x180007db4  mov     r10, cs:qword_18006FF58
0x180007dbb  mov     cs:?bReportEventProbed@@3_NA, 1; bool bReportEventProbed
0x180007dc2  test    r10, r10
0x180007dc5  jnz     short loc_180007DCB
0x180007dc7  xor     eax, eax
0x180007dc9  jmp     short loc_180007E09
0x180007dcb  mov     rax, [rsp+58h+arg_38]
0x180007dd3  xor     r8d, r8d
0x180007dd6  and     [rsp+58h+var_18], r8
0x180007ddb  mov     r9d, ebx
0x180007dde  mov     [rsp+58h+var_20], rax
0x180007de3  movzx   edx, di
0x180007de6  and     [rsp+58h+var_28], r8d
0x180007deb  mov     rcx, rsi
0x180007dee  movzx   eax, [rsp+58h+arg_28]
0x180007df6  mov     [rsp+58h+var_30], ax
0x180007dfb  mov     rax, r10
0x180007dfe  and     [rsp+58h+var_38], r8
0x180007e03  call    cs:__guard_dispatch_icall_fptr
0x180007e09  mov     rbx, [rsp+58h+arg_0]
0x180007e0e  mov     rsi, [rsp+58h+arg_8]
0x180007e13  add     rsp, 50h
0x180007e17  pop     rdi
0x180007e18  retn
```
