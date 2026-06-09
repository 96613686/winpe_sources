# CLROpenService(SC_HANDLE__ *,ushort const *,ulong)

- ea: `0x180007a80`
- end: `0x180007b12`
- name: `?CLROpenService@@YAPEAUSC_HANDLE__@@PEAU1@PEBGK@Z`
- size: `146`
- prototype: `struct SC_HANDLE__ *__fastcall(struct SC_HANDLE__ *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001a690`
- `0x18001b128`

## callees

- `0x180007a80`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180007ab8`
- `KERNEL32!LoadLibraryExW` at `0x180007ab8`
- `KERNEL32!GetProcAddress` at `0x180007acd`
- `KERNEL32!GetProcAddress` at `0x180007acd`

## string_xrefs

- `0x180007aaf`: `advapi32.dll`
- `0x180007ac3`: `OpenServiceW`

## pseudocode

```c
struct SC_HANDLE__ *__fastcall CLROpenService(struct SC_HANDLE__ *a1, const unsigned __int16 *a2, unsigned int a3)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FF10;
  if ( qword_18006FF10 )
    return (struct SC_HANDLE__ *)((__int64 (__fastcall *)(struct SC_HANDLE__ *, const unsigned __int16 *, _QWORD))ProcAddress)(
                                   a1,
                                   a2,
                                   a3);
  if ( !bOpenServiceProbed
    && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FF10)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "OpenServiceW"), qword_18006FF10 = (__int64)ProcAddress),
        bOpenServiceProbed = 1,
        ProcAddress) )
  {
    return (struct SC_HANDLE__ *)((__int64 (__fastcall *)(struct SC_HANDLE__ *, const unsigned __int16 *, _QWORD))ProcAddress)(
                                   a1,
                                   a2,
                                   a3);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180007a80  mov     [rsp+arg_0], rbx
0x180007a85  mov     [rsp+arg_8], rsi
0x180007a8a  push    rdi
0x180007a8b  sub     rsp, 20h
0x180007a8f  mov     rax, cs:qword_18006FF10
0x180007a96  mov     ebx, r8d
0x180007a99  mov     rdi, rdx
0x180007a9c  mov     rsi, rcx
0x180007a9f  test    rax, rax
0x180007aa2  jnz     short loc_180007AF3
0x180007aa4  cmp     cs:?bOpenServiceProbed@@3_NA, al; bool bOpenServiceProbed
0x180007aaa  jnz     short loc_180007AEF
0x180007aac  xor     r8d, r8d; dwFlags
0x180007aaf  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x180007ab6  xor     edx, edx; hFile
0x180007ab8  call    cs:__imp_LoadLibraryExW
0x180007abe  test    rax, rax
0x180007ac1  jz      short loc_180007ADC
0x180007ac3  lea     rdx, aOpenservicew; "OpenServiceW"
0x180007aca  mov     rcx, rax; hModule
0x180007acd  call    cs:__imp_GetProcAddress
0x180007ad3  mov     cs:qword_18006FF10, rax
0x180007ada  jmp     short loc_180007AE3
0x180007adc  mov     rax, cs:qword_18006FF10
0x180007ae3  mov     cs:?bOpenServiceProbed@@3_NA, 1; bool bOpenServiceProbed
0x180007aea  test    rax, rax
0x180007aed  jnz     short loc_180007AF3
0x180007aef  xor     eax, eax
0x180007af1  jmp     short loc_180007B02
0x180007af3  mov     r8d, ebx
0x180007af6  mov     rdx, rdi
0x180007af9  mov     rcx, rsi
0x180007afc  call    cs:__guard_dispatch_icall_fptr
0x180007b02  mov     rbx, [rsp+28h+arg_0]
0x180007b07  mov     rsi, [rsp+28h+arg_8]
0x180007b0c  add     rsp, 20h
0x180007b10  pop     rdi
0x180007b11  retn
```
