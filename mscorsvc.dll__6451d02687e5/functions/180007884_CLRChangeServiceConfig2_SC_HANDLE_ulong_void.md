# CLRChangeServiceConfig2(SC_HANDLE__ *,ulong,void *)

- ea: `0x180007884`
- end: `0x180007914`
- name: `?CLRChangeServiceConfig2@@YAHPEAUSC_HANDLE__@@KPEAX@Z`
- size: `144`
- prototype: `__int64 __fastcall(struct SC_HANDLE__ *, unsigned int, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001b57c`
- `0x18001b9d0`

## callees

- `0x180007884`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800078bb`
- `KERNEL32!LoadLibraryExW` at `0x1800078bb`
- `KERNEL32!GetProcAddress` at `0x1800078d0`
- `KERNEL32!GetProcAddress` at `0x1800078d0`

## string_xrefs

- `0x1800078b2`: `advapi32.dll`
- `0x1800078c6`: `ChangeServiceConfig2W`

## pseudocode

```c
__int64 __fastcall CLRChangeServiceConfig2(struct SC_HANDLE__ *a1, unsigned int a2, void *a3)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FEE8;
  if ( qword_18006FEE8 )
    return ((__int64 (__fastcall *)(struct SC_HANDLE__ *, _QWORD, void *))ProcAddress)(a1, a2, a3);
  if ( !bChangeServiceConfig2Probed
    && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FEE8)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "ChangeServiceConfig2W"), qword_18006FEE8 = (__int64)ProcAddress),
        bChangeServiceConfig2Probed = 1,
        ProcAddress) )
  {
    return ((__int64 (__fastcall *)(struct SC_HANDLE__ *, _QWORD, void *))ProcAddress)(a1, a2, a3);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180007884  mov     [rsp+arg_0], rbx
0x180007889  mov     [rsp+arg_8], rsi
0x18000788e  push    rdi
0x18000788f  sub     rsp, 20h
0x180007893  mov     rax, cs:qword_18006FEE8
0x18000789a  mov     rbx, r8
0x18000789d  mov     edi, edx
0x18000789f  mov     rsi, rcx
0x1800078a2  test    rax, rax
0x1800078a5  jnz     short loc_1800078F6
0x1800078a7  cmp     cs:?bChangeServiceConfig2Probed@@3_NA, al; bool bChangeServiceConfig2Probed
0x1800078ad  jnz     short loc_1800078F2
0x1800078af  xor     r8d, r8d; dwFlags
0x1800078b2  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x1800078b9  xor     edx, edx; hFile
0x1800078bb  call    cs:__imp_LoadLibraryExW
0x1800078c1  test    rax, rax
0x1800078c4  jz      short loc_1800078DF
0x1800078c6  lea     rdx, aChangeservicec; "ChangeServiceConfig2W"
0x1800078cd  mov     rcx, rax; hModule
0x1800078d0  call    cs:__imp_GetProcAddress
0x1800078d6  mov     cs:qword_18006FEE8, rax
0x1800078dd  jmp     short loc_1800078E6
0x1800078df  mov     rax, cs:qword_18006FEE8
0x1800078e6  mov     cs:?bChangeServiceConfig2Probed@@3_NA, 1; bool bChangeServiceConfig2Probed
0x1800078ed  test    rax, rax
0x1800078f0  jnz     short loc_1800078F6
0x1800078f2  xor     eax, eax
0x1800078f4  jmp     short loc_180007904
0x1800078f6  mov     r8, rbx
0x1800078f9  mov     edx, edi
0x1800078fb  mov     rcx, rsi
0x1800078fe  call    cs:__guard_dispatch_icall_fptr
0x180007904  mov     rbx, [rsp+28h+arg_0]
0x180007909  mov     rsi, [rsp+28h+arg_8]
0x18000790e  add     rsp, 20h
0x180007912  pop     rdi
0x180007913  retn
```
