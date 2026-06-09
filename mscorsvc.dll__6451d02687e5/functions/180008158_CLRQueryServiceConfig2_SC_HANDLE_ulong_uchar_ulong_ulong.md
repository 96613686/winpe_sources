# CLRQueryServiceConfig2(SC_HANDLE__ *,ulong,uchar *,ulong,ulong *)

- ea: `0x180008158`
- end: `0x180008200`
- name: `?CLRQueryServiceConfig2@@YAHPEAUSC_HANDLE__@@KPEAEKPEAK@Z`
- size: `168`
- prototype: `__int64 __fastcall(struct SC_HANDLE__ *, __int64, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001b800`

## callees

- `0x180008158`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180008191`
- `KERNEL32!LoadLibraryExW` at `0x180008191`
- `KERNEL32!GetProcAddress` at `0x1800081a6`
- `KERNEL32!GetProcAddress` at `0x1800081a6`

## string_xrefs

- `0x180008188`: `advapi32.dll`
- `0x18000819c`: `QueryServiceConfig2W`

## pseudocode

```c
__int64 __fastcall CLRQueryServiceConfig2(
        struct SC_HANDLE__ *a1,
        __int64 a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int *a5)
{
  FARPROC ProcAddress; // r10
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FFA8;
  if ( qword_18006FFA8 )
    return ((__int64 (__fastcall *)(struct SC_HANDLE__ *, __int64, unsigned __int8 *, _QWORD, unsigned int *))ProcAddress)(
             a1,
             6,
             a3,
             a4,
             a5);
  if ( !bQueryServiceConfig2Probed
    && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FFA8)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "QueryServiceConfig2W"), qword_18006FFA8 = (__int64)ProcAddress),
        bQueryServiceConfig2Probed = 1,
        ProcAddress) )
  {
    return ((__int64 (__fastcall *)(struct SC_HANDLE__ *, __int64, unsigned __int8 *, _QWORD, unsigned int *))ProcAddress)(
             a1,
             6,
             a3,
             a4,
             a5);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180008158  mov     [rsp+arg_0], rbx
0x18000815d  mov     [rsp+arg_8], rsi
0x180008162  push    rdi
0x180008163  sub     rsp, 30h
0x180008167  mov     r10, cs:qword_18006FFA8
0x18000816e  mov     ebx, r9d
0x180008171  mov     rdi, r8
0x180008174  mov     rsi, rcx
0x180008177  test    r10, r10
0x18000817a  jnz     short loc_1800081CF
0x18000817c  cmp     cs:?bQueryServiceConfig2Probed@@3_NA, r10b; bool bQueryServiceConfig2Probed
0x180008183  jnz     short loc_1800081CB
0x180008185  xor     r8d, r8d; dwFlags
0x180008188  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x18000818f  xor     edx, edx; hFile
0x180008191  call    cs:__imp_LoadLibraryExW
0x180008197  test    rax, rax
0x18000819a  jz      short loc_1800081B8
0x18000819c  lea     rdx, aQueryserviceco; "QueryServiceConfig2W"
0x1800081a3  mov     rcx, rax; hModule
0x1800081a6  call    cs:__imp_GetProcAddress
0x1800081ac  mov     r10, rax
0x1800081af  mov     cs:qword_18006FFA8, rax
0x1800081b6  jmp     short loc_1800081BF
0x1800081b8  mov     r10, cs:qword_18006FFA8
0x1800081bf  mov     cs:?bQueryServiceConfig2Probed@@3_NA, 1; bool bQueryServiceConfig2Probed
0x1800081c6  test    r10, r10
0x1800081c9  jnz     short loc_1800081CF
0x1800081cb  xor     eax, eax
0x1800081cd  jmp     short loc_1800081F0
0x1800081cf  mov     rax, [rsp+38h+arg_20]
0x1800081d4  mov     r9d, ebx
0x1800081d7  mov     [rsp+38h+var_18], rax
0x1800081dc  mov     r8, rdi
0x1800081df  mov     rax, r10
0x1800081e2  mov     edx, 6
0x1800081e7  mov     rcx, rsi
0x1800081ea  call    cs:__guard_dispatch_icall_fptr
0x1800081f0  mov     rbx, [rsp+38h+arg_0]
0x1800081f5  mov     rsi, [rsp+38h+arg_8]
0x1800081fa  add     rsp, 30h
0x1800081fe  pop     rdi
0x1800081ff  retn
```
