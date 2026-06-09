# CLRChangeServiceConfig(SC_HANDLE__ *,ulong,ulong,ulong,ushort const *,ushort const *,ulong *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800077d0`
- end: `0x180007882`
- name: `?CLRChangeServiceConfig@@YAHPEAUSC_HANDLE__@@KKKPEBG1PEAK1111@Z`
- size: `178`
- prototype: `__int64 __fastcall(struct SC_HANDLE__ *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001ac30`

## callees

- `0x1800077d0`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180007800`
- `KERNEL32!LoadLibraryExW` at `0x180007800`
- `KERNEL32!GetProcAddress` at `0x180007815`
- `KERNEL32!GetProcAddress` at `0x180007815`

## string_xrefs

- `0x1800077f7`: `advapi32.dll`
- `0x18000780b`: `ChangeServiceConfigW`

## pseudocode

```c
__int64 __fastcall CLRChangeServiceConfig(struct SC_HANDLE__ *a1, __int64 a2, unsigned int a3)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FEE0;
  if ( qword_18006FEE0 )
    return ((__int64 (__fastcall *)(struct SC_HANDLE__ *, __int64, _QWORD, __int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(
             a1,
             0xFFFFFFFFLL,
             a3,
             0xFFFFFFFFLL,
             0,
             0,
             0,
             0,
             0,
             0,
             0);
  if ( !bChangeServiceConfigProbed
    && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FEE0)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "ChangeServiceConfigW"), qword_18006FEE0 = (__int64)ProcAddress),
        bChangeServiceConfigProbed = 1,
        ProcAddress) )
  {
    return ((__int64 (__fastcall *)(struct SC_HANDLE__ *, __int64, _QWORD, __int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(
             a1,
             0xFFFFFFFFLL,
             a3,
             0xFFFFFFFFLL,
             0,
             0,
             0,
             0,
             0,
             0,
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
0x1800077d0  mov     [rsp+arg_0], rbx
0x1800077d5  push    rdi
0x1800077d6  sub     rsp, 60h
0x1800077da  mov     rax, cs:qword_18006FEE0
0x1800077e1  mov     ebx, r8d
0x1800077e4  mov     rdi, rcx
0x1800077e7  test    rax, rax
0x1800077ea  jnz     short loc_18000783B
0x1800077ec  cmp     cs:?bChangeServiceConfigProbed@@3_NA, al; bool bChangeServiceConfigProbed
0x1800077f2  jnz     short loc_180007837
0x1800077f4  xor     r8d, r8d; dwFlags
0x1800077f7  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x1800077fe  xor     edx, edx; hFile
0x180007800  call    cs:__imp_LoadLibraryExW
0x180007806  test    rax, rax
0x180007809  jz      short loc_180007824
0x18000780b  lea     rdx, aChangeservicec_0; "ChangeServiceConfigW"
0x180007812  mov     rcx, rax; hModule
0x180007815  call    cs:__imp_GetProcAddress
0x18000781b  mov     cs:qword_18006FEE0, rax
0x180007822  jmp     short loc_18000782B
0x180007824  mov     rax, cs:qword_18006FEE0
0x18000782b  mov     cs:?bChangeServiceConfigProbed@@3_NA, 1; bool bChangeServiceConfigProbed
0x180007832  test    rax, rax
0x180007835  jnz     short loc_18000783B
0x180007837  xor     eax, eax
0x180007839  jmp     short loc_180007877
0x18000783b  and     [rsp+68h+var_18], 0
0x180007841  or      edx, 0FFFFFFFFh
0x180007844  and     [rsp+68h+var_20], 0
0x18000784a  mov     r9d, edx
0x18000784d  and     [rsp+68h+var_28], 0
0x180007853  mov     r8d, ebx
0x180007856  and     [rsp+68h+var_30], 0
0x18000785c  mov     rcx, rdi
0x18000785f  and     [rsp+68h+var_38], 0
0x180007865  and     [rsp+68h+var_40], 0
0x18000786b  and     [rsp+68h+var_48], 0
0x180007871  call    cs:__guard_dispatch_icall_fptr
0x180007877  mov     rbx, [rsp+68h+arg_0]
0x18000787c  add     rsp, 60h
0x180007880  pop     rdi
0x180007881  retn
```
