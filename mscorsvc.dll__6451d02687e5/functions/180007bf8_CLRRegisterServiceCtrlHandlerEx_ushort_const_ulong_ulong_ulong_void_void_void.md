# CLRRegisterServiceCtrlHandlerEx(ushort const *,ulong (*)(ulong,ulong,void *,void *),void *)

- ea: `0x180007bf8`
- end: `0x180007c79`
- name: `?CLRRegisterServiceCtrlHandlerEx@@YAPEAUSERVICE_STATUS_HANDLE__@@PEBGP6AKKKPEAX1@Z1@Z`
- size: `129`
- prototype: `struct SERVICE_STATUS_HANDLE__ *__fastcall(const unsigned __int16 *, unsigned int (*)(unsigned int, unsigned int, void *, void *), void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001b340`

## callees

- `0x180007bf8`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180007c21`
- `KERNEL32!LoadLibraryExW` at `0x180007c21`
- `KERNEL32!GetProcAddress` at `0x180007c36`
- `KERNEL32!GetProcAddress` at `0x180007c36`

## string_xrefs

- `0x180007c18`: `advapi32.dll`
- `0x180007c2c`: `RegisterServiceCtrlHandlerExW`

## pseudocode

```c
struct SERVICE_STATUS_HANDLE__ *__fastcall CLRRegisterServiceCtrlHandlerEx(
        const unsigned __int16 *a1,
        unsigned int (*a2)(unsigned int, unsigned int, void *, void *),
        void *a3)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FF20;
  if ( qword_18006FF20 )
    return (struct SERVICE_STATUS_HANDLE__ *)((__int64 (__fastcall *)(const unsigned __int16 *, unsigned int (__fastcall *)(NGENService *__hidden, unsigned int, unsigned int, void *, void *), _QWORD))ProcAddress)(
                                               a1,
                                               NGENService::CorServiceControlHandlerEx,
                                               0);
  if ( !bRegisterServiceCtrlHandlerExProbed
    && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FF20)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "RegisterServiceCtrlHandlerExW"),
                  qword_18006FF20 = (__int64)ProcAddress),
        bRegisterServiceCtrlHandlerExProbed = 1,
        ProcAddress) )
  {
    return (struct SERVICE_STATUS_HANDLE__ *)((__int64 (__fastcall *)(const unsigned __int16 *, unsigned int (__fastcall *)(NGENService *__hidden, unsigned int, unsigned int, void *, void *), _QWORD))ProcAddress)(
                                               a1,
                                               NGENService::CorServiceControlHandlerEx,
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
0x180007bf8  push    rbx
0x180007bfa  sub     rsp, 20h
0x180007bfe  mov     rax, cs:qword_18006FF20
0x180007c05  mov     rbx, rcx
0x180007c08  test    rax, rax
0x180007c0b  jnz     short loc_180007C60
0x180007c0d  cmp     cs:?bRegisterServiceCtrlHandlerExProbed@@3_NA, al; bool bRegisterServiceCtrlHandlerExProbed
0x180007c13  jnz     short loc_180007C58
0x180007c15  xor     r8d, r8d; dwFlags
0x180007c18  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x180007c1f  xor     edx, edx; hFile
0x180007c21  call    cs:__imp_LoadLibraryExW
0x180007c27  test    rax, rax
0x180007c2a  jz      short loc_180007C45
0x180007c2c  lea     rdx, aRegisterservic; "RegisterServiceCtrlHandlerExW"
0x180007c33  mov     rcx, rax; hModule
0x180007c36  call    cs:__imp_GetProcAddress
0x180007c3c  mov     cs:qword_18006FF20, rax
0x180007c43  jmp     short loc_180007C4C
0x180007c45  mov     rax, cs:qword_18006FF20
0x180007c4c  mov     cs:?bRegisterServiceCtrlHandlerExProbed@@3_NA, 1; bool bRegisterServiceCtrlHandlerExProbed
0x180007c53  test    rax, rax
0x180007c56  jnz     short loc_180007C60
0x180007c58  xor     eax, eax
0x180007c5a  add     rsp, 20h
0x180007c5e  pop     rbx
0x180007c5f  retn
0x180007c60  xor     r8d, r8d
0x180007c63  lea     rdx, ?CorServiceControlHandlerEx@NGENService@@YAKKKPEAX0@Z; NGENService::CorServiceControlHandlerEx(ulong,ulong,void *,void *)
0x180007c6a  mov     rcx, rbx
0x180007c6d  add     rsp, 20h
0x180007c71  pop     rbx
0x180007c72  jmp     cs:__guard_dispatch_icall_fptr
```
