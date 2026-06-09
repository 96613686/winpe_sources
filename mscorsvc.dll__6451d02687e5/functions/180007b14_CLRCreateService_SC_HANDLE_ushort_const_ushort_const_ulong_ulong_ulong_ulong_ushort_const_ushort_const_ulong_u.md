# CLRCreateService(SC_HANDLE__ *,ushort const *,ushort const *,ulong,ulong,ulong,ulong,ushort const *,ushort const *,ulong *,ushort const *,ushort const *,ushort const *)

- ea: `0x180007b14`
- end: `0x180007bf5`
- name: `?CLRCreateService@@YAPEAUSC_HANDLE__@@PEAU1@PEBG1KKKK11PEAK111@Z`
- size: `225`
- prototype: `struct SC_HANDLE__ *__fastcall(struct SC_HANDLE__ *, const unsigned __int16 *, const unsigned __int16 *, __int64, unsigned int, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001b9d0`

## callees

- `0x180007b14`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180007b4d`
- `KERNEL32!LoadLibraryExW` at `0x180007b4d`
- `KERNEL32!GetProcAddress` at `0x180007b62`
- `KERNEL32!GetProcAddress` at `0x180007b62`

## string_xrefs

- `0x180007b44`: `advapi32.dll`
- `0x180007b58`: `CreateServiceW`

## pseudocode

```c
struct SC_HANDLE__ *__fastcall CLRCreateService(
        struct SC_HANDLE__ *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        const unsigned __int16 *a8)
{
  FARPROC ProcAddress; // r10
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FF18;
  if ( qword_18006FF18 )
    return (struct SC_HANDLE__ *)((__int64 (__fastcall *)(struct SC_HANDLE__ *, const unsigned __int16 *, const unsigned __int16 *, __int64, int, int, _DWORD, const unsigned __int16 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(
                                   a1,
                                   a2,
                                   a3,
                                   983551,
                                   16,
                                   2,
                                   0,
                                   a8,
                                   0,
                                   0,
                                   0,
                                   0,
                                   0);
  if ( !bCreateServiceProbed
    && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FF18)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "CreateServiceW"), qword_18006FF18 = (__int64)ProcAddress),
        bCreateServiceProbed = 1,
        ProcAddress) )
  {
    return (struct SC_HANDLE__ *)((__int64 (__fastcall *)(struct SC_HANDLE__ *, const unsigned __int16 *, const unsigned __int16 *, __int64, int, int, _DWORD, const unsigned __int16 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(
                                   a1,
                                   a2,
                                   a3,
                                   983551,
                                   16,
                                   2,
                                   0,
                                   a8,
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
0x180007b14  mov     [rsp+arg_0], rbx
0x180007b19  mov     [rsp+arg_8], rsi
0x180007b1e  push    rdi
0x180007b1f  sub     rsp, 70h
0x180007b23  mov     r10, cs:qword_18006FF18
0x180007b2a  mov     rbx, r8
0x180007b2d  mov     rdi, rdx
0x180007b30  mov     rsi, rcx
0x180007b33  test    r10, r10
0x180007b36  jnz     short loc_180007B8B
0x180007b38  cmp     cs:?bCreateServiceProbed@@3_NA, r10b; bool bCreateServiceProbed
0x180007b3f  jnz     short loc_180007B87
0x180007b41  xor     r8d, r8d; dwFlags
0x180007b44  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x180007b4b  xor     edx, edx; hFile
0x180007b4d  call    cs:__imp_LoadLibraryExW
0x180007b53  test    rax, rax
0x180007b56  jz      short loc_180007B74
0x180007b58  lea     rdx, aCreateservicew; "CreateServiceW"
0x180007b5f  mov     rcx, rax; hModule
0x180007b62  call    cs:__imp_GetProcAddress
0x180007b68  mov     r10, rax
0x180007b6b  mov     cs:qword_18006FF18, rax
0x180007b72  jmp     short loc_180007B7B
0x180007b74  mov     r10, cs:qword_18006FF18
0x180007b7b  mov     cs:?bCreateServiceProbed@@3_NA, 1; bool bCreateServiceProbed
0x180007b82  test    r10, r10
0x180007b85  jnz     short loc_180007B8B
0x180007b87  xor     eax, eax
0x180007b89  jmp     short loc_180007BE3
0x180007b8b  and     [rsp+78h+var_18], 0
0x180007b91  mov     r9d, 0F01FFh
0x180007b97  and     [rsp+78h+var_20], 0
0x180007b9d  mov     r8, rbx
0x180007ba0  and     [rsp+78h+var_28], 0
0x180007ba6  mov     rdx, rdi
0x180007ba9  and     [rsp+78h+var_30], 0
0x180007baf  mov     rcx, rsi
0x180007bb2  and     [rsp+78h+var_38], 0
0x180007bb8  mov     rax, [rsp+78h+arg_38]
0x180007bc0  mov     [rsp+78h+var_40], rax
0x180007bc5  mov     rax, r10
0x180007bc8  and     [rsp+78h+var_48], 0
0x180007bcd  mov     [rsp+78h+var_50], 2
0x180007bd5  mov     [rsp+78h+var_58], 10h
0x180007bdd  call    cs:__guard_dispatch_icall_fptr
0x180007be3  lea     r11, [rsp+78h+var_8]
0x180007be8  mov     rbx, [r11+10h]
0x180007bec  mov     rsi, [r11+18h]
0x180007bf0  mov     rsp, r11
0x180007bf3  pop     rdi
0x180007bf4  retn
```
