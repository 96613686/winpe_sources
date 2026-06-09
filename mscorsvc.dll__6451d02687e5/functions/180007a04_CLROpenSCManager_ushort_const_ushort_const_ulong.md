# CLROpenSCManager(ushort const *,ushort const *,ulong)

- ea: `0x180007a04`
- end: `0x180007a7f`
- name: `?CLROpenSCManager@@YAPEAUSC_HANDLE__@@PEBG0K@Z`
- size: `123`
- prototype: `struct SC_HANDLE__ *__fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a690`
- `0x18001b128`
- `0x18001b9d0`

## callees

- `0x180007a04`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180007a2d`
- `KERNEL32!LoadLibraryExW` at `0x180007a2d`
- `KERNEL32!GetProcAddress` at `0x180007a42`
- `KERNEL32!GetProcAddress` at `0x180007a42`

## string_xrefs

- `0x180007a24`: `advapi32.dll`
- `0x180007a38`: `OpenSCManagerW`

## pseudocode

```c
struct SC_HANDLE__ *__fastcall CLROpenSCManager(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FF08;
  if ( qword_18006FF08 )
    return (struct SC_HANDLE__ *)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))ProcAddress)(0, 0, a3);
  if ( !bOpenSCManagerProbed
    && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FF08)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "OpenSCManagerW"), qword_18006FF08 = (__int64)ProcAddress),
        bOpenSCManagerProbed = 1,
        ProcAddress) )
  {
    return (struct SC_HANDLE__ *)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))ProcAddress)(0, 0, a3);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180007a04  push    rbx
0x180007a06  sub     rsp, 20h
0x180007a0a  mov     rax, cs:qword_18006FF08
0x180007a11  mov     ebx, r8d
0x180007a14  test    rax, rax
0x180007a17  jnz     short loc_180007A6C
0x180007a19  cmp     cs:?bOpenSCManagerProbed@@3_NA, al; bool bOpenSCManagerProbed
0x180007a1f  jnz     short loc_180007A64
0x180007a21  xor     r8d, r8d; dwFlags
0x180007a24  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x180007a2b  xor     edx, edx; hFile
0x180007a2d  call    cs:__imp_LoadLibraryExW
0x180007a33  test    rax, rax
0x180007a36  jz      short loc_180007A51
0x180007a38  lea     rdx, aOpenscmanagerw; "OpenSCManagerW"
0x180007a3f  mov     rcx, rax; hModule
0x180007a42  call    cs:__imp_GetProcAddress
0x180007a48  mov     cs:qword_18006FF08, rax
0x180007a4f  jmp     short loc_180007A58
0x180007a51  mov     rax, cs:qword_18006FF08
0x180007a58  mov     cs:?bOpenSCManagerProbed@@3_NA, 1; bool bOpenSCManagerProbed
0x180007a5f  test    rax, rax
0x180007a62  jnz     short loc_180007A6C
0x180007a64  xor     eax, eax
0x180007a66  add     rsp, 20h
0x180007a6a  pop     rbx
0x180007a6b  retn
0x180007a6c  mov     r8d, ebx
0x180007a6f  xor     edx, edx
0x180007a71  xor     ecx, ecx
0x180007a73  add     rsp, 20h
0x180007a77  pop     rbx
0x180007a78  jmp     cs:__guard_dispatch_icall_fptr
```
