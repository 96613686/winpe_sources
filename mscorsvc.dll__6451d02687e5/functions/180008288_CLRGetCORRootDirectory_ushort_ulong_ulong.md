# CLRGetCORRootDirectory(ushort *,ulong,ulong *)

- ea: `0x180008288`
- end: `0x180008303`
- name: `?CLRGetCORRootDirectory@@YAJPEAGKPEAK@Z`
- size: `123`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005fc4`

## callees

- `0x180008288`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800082b0`
- `KERNEL32!LoadLibraryExW` at `0x1800082b0`
- `KERNEL32!GetProcAddress` at `0x1800082c5`
- `KERNEL32!GetProcAddress` at `0x1800082c5`

## string_xrefs

- `0x1800082bb`: `GetCORRootDirectory`
- `0x1800082a7`: `mscoree.dll`

## pseudocode

```c
__int64 __fastcall CLRGetCORRootDirectory(unsigned __int16 *a1, __int64 a2, unsigned int *a3)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_180070868;
  if ( qword_180070868 )
    return ((__int64 (__fastcall *)(unsigned __int16 *, __int64, unsigned int *))ProcAddress)(a1, 260, a3);
  Library = LoadLibraryExW(L"mscoree.dll", 0, 0);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetCORRootDirectory");
    qword_180070868 = (__int64)ProcAddress;
  }
  else
  {
    ProcAddress = (FARPROC)qword_180070868;
  }
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(unsigned __int16 *, __int64, unsigned int *))ProcAddress)(a1, 260, a3);
  else
    return 1;
}

```

## disassembly

```asm
0x180008288  mov     [rsp+arg_0], rbx
0x18000828d  push    rdi
0x18000828e  sub     rsp, 20h
0x180008292  mov     rax, cs:qword_180070868
0x180008299  mov     rbx, r8
0x18000829c  mov     rdi, rcx
0x18000829f  test    rax, rax
0x1800082a2  jnz     short loc_1800082E7
0x1800082a4  xor     r8d, r8d; dwFlags
0x1800082a7  lea     rcx, aMscoreeDll_0; "mscoree.dll"
0x1800082ae  xor     edx, edx; hFile
0x1800082b0  call    cs:__imp_LoadLibraryExW
0x1800082b6  test    rax, rax
0x1800082b9  jz      short loc_1800082D4
0x1800082bb  lea     rdx, aGetcorrootdire; "GetCORRootDirectory"
0x1800082c2  mov     rcx, rax; hModule
0x1800082c5  call    cs:__imp_GetProcAddress
0x1800082cb  mov     cs:qword_180070868, rax
0x1800082d2  jmp     short loc_1800082DB
0x1800082d4  mov     rax, cs:qword_180070868
0x1800082db  test    rax, rax
0x1800082de  jnz     short loc_1800082E7
0x1800082e0  mov     eax, 1
0x1800082e5  jmp     short loc_1800082F8
0x1800082e7  mov     r8, rbx
0x1800082ea  mov     edx, 104h
0x1800082ef  mov     rcx, rdi
0x1800082f2  call    cs:__guard_dispatch_icall_fptr
0x1800082f8  mov     rbx, [rsp+28h+arg_0]
0x1800082fd  add     rsp, 20h
0x180008301  pop     rdi
0x180008302  retn
```
