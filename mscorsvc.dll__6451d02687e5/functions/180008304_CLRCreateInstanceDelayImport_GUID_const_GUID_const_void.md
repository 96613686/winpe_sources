# CLRCreateInstanceDelayImport(_GUID const &,_GUID const &,void * *)

- ea: `0x180008304`
- end: `0x18000838a`
- name: `?CLRCreateInstanceDelayImport@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `134`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002e940`

## callees

- `0x180008304`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180008334`
- `KERNEL32!LoadLibraryExW` at `0x180008334`
- `KERNEL32!GetProcAddress` at `0x180008349`
- `KERNEL32!GetProcAddress` at `0x180008349`

## string_xrefs

- `0x18000833f`: `CLRCreateInstance`
- `0x18000832b`: `mscoree.dll`

## pseudocode

```c
__int64 __fastcall CLRCreateInstanceDelayImport(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_180070878;
  if ( qword_180070878 )
    return ((__int64 (__fastcall *)(const struct _GUID *, const struct _GUID *, void **))ProcAddress)(a1, a2, a3);
  Library = LoadLibraryExW(L"mscoree.dll", 0, 0);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "CLRCreateInstance");
    qword_180070878 = (__int64)ProcAddress;
  }
  else
  {
    ProcAddress = (FARPROC)qword_180070878;
  }
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(const struct _GUID *, const struct _GUID *, void **))ProcAddress)(a1, a2, a3);
  else
    return 1;
}

```

## disassembly

```asm
0x180008304  mov     [rsp+arg_0], rbx
0x180008309  mov     [rsp+arg_8], rsi
0x18000830e  push    rdi
0x18000830f  sub     rsp, 20h
0x180008313  mov     rax, cs:qword_180070878
0x18000831a  mov     rbx, r8
0x18000831d  mov     rdi, rdx
0x180008320  mov     rsi, rcx
0x180008323  test    rax, rax
0x180008326  jnz     short loc_18000836B
0x180008328  xor     r8d, r8d; dwFlags
0x18000832b  lea     rcx, aMscoreeDll_0; "mscoree.dll"
0x180008332  xor     edx, edx; hFile
0x180008334  call    cs:__imp_LoadLibraryExW
0x18000833a  test    rax, rax
0x18000833d  jz      short loc_180008358
0x18000833f  lea     rdx, aClrcreateinsta; "CLRCreateInstance"
0x180008346  mov     rcx, rax; hModule
0x180008349  call    cs:__imp_GetProcAddress
0x18000834f  mov     cs:qword_180070878, rax
0x180008356  jmp     short loc_18000835F
0x180008358  mov     rax, cs:qword_180070878
0x18000835f  test    rax, rax
0x180008362  jnz     short loc_18000836B
0x180008364  mov     eax, 1
0x180008369  jmp     short loc_18000837A
0x18000836b  mov     r8, rbx
0x18000836e  mov     rdx, rdi
0x180008371  mov     rcx, rsi
0x180008374  call    cs:__guard_dispatch_icall_fptr
0x18000837a  mov     rbx, [rsp+28h+arg_0]
0x18000837f  mov     rsi, [rsp+28h+arg_8]
0x180008384  add     rsp, 20h
0x180008388  pop     rdi
0x180008389  retn
```
