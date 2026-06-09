# CHost::InitWldp(void *)

- ea: `0x14000187c`
- end: `0x14000194a`
- name: `?InitWldp@CHost@@IEAAJPEAX@Z`
- size: `206`
- prototype: `__int64 __fastcall(CHost *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400014b0`

## callees

- `0x14000187c`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400018b2`
- `KERNEL32!GetProcAddress` at `0x1400018d2`
- `KERNEL32!GetProcAddress` at `0x1400018b2`
- `KERNEL32!GetProcAddress` at `0x1400018d2`
- `KERNEL32!LoadLibraryExW` at `0x14000189a`
- `KERNEL32!LoadLibraryExW` at `0x14000189a`
- `KERNEL32!GetLastError` at `0x1400018dd`
- `KERNEL32!GetLastError` at `0x1400018dd`
- `KERNEL32!FreeLibrary` at `0x1400018fe`
- `KERNEL32!FreeLibrary` at `0x1400018fe`

## string_xrefs

- `0x14000188d`: `WLDP.DLL`

## pseudocode

```c
__int64 __fastcall CHost::InitWldp(CHost *this, void *a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rdi
  FARPROC ProcAddress; // rbp
  FARPROC v7; // rax
  signed int LastError; // eax
  signed int v9; // ebx
  bool v11; // zf
  int v12; // [rsp+70h] [rbp+18h] BYREF

  Library = LoadLibraryExW(L"WLDP.DLL", 0, 0x800u);
  v5 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WldpIsClassInApprovedList");
    if ( ProcAddress )
    {
      v12 = 0;
      v7 = GetProcAddress(v5, "WldpCanExecuteFile");
      if ( v7 )
      {
        v9 = ((__int64 (__fastcall *)(__int64 *, _QWORD, void *, _QWORD, int *))v7)(
               WLDP_HOST_WINDOWS_SCRIPT_HOST,
               0,
               a2,
               0,
               &v12);
        if ( v9 >= 0 )
        {
          *((_QWORD *)this + 2) = v5;
          v11 = v12 == 1;
          *((_QWORD *)this + 3) = ProcAddress;
          *((_DWORD *)this + 2) = !v11;
          return (unsigned int)v9;
        }
        goto LABEL_8;
      }
    }
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( v9 < 0 && v5 )
LABEL_8:
    FreeLibrary(v5);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000187c  push    rbx
0x14000187e  push    rbp
0x14000187f  push    rsi
0x140001880  push    rdi
0x140001881  sub     rsp, 38h
0x140001885  mov     rbx, rdx
0x140001888  mov     rsi, rcx
0x14000188b  xor     edx, edx; hFile
0x14000188d  lea     rcx, LibFileName; "WLDP.DLL"
0x140001894  mov     r8d, 800h; dwFlags
0x14000189a  call    cs:__imp_LoadLibraryExW
0x1400018a0  mov     rdi, rax
0x1400018a3  test    rax, rax
0x1400018a6  jz      short loc_1400018DD
0x1400018a8  lea     rdx, ProcName; "WldpIsClassInApprovedList"
0x1400018af  mov     rcx, rax; hModule
0x1400018b2  call    cs:__imp_GetProcAddress
0x1400018b8  mov     rbp, rax
0x1400018bb  test    rax, rax
0x1400018be  jz      short loc_1400018DD
0x1400018c0  lea     rdx, aWldpcanexecute; "WldpCanExecuteFile"
0x1400018c7  mov     [rsp+58h+arg_10], 0
0x1400018cf  mov     rcx, rdi; hModule
0x1400018d2  call    cs:__imp_GetProcAddress
0x1400018d8  test    rax, rax
0x1400018db  jnz     short loc_14000190F
0x1400018dd  call    cs:__imp_GetLastError
0x1400018e3  mov     ebx, eax
0x1400018e5  test    eax, eax
0x1400018e7  jle     short loc_1400018F2
0x1400018e9  movzx   ebx, ax
0x1400018ec  or      ebx, 80070000h
0x1400018f2  test    ebx, ebx
0x1400018f4  jns     short loc_140001904
0x1400018f6  test    rdi, rdi
0x1400018f9  jz      short loc_140001904
0x1400018fb  mov     rcx, rdi; hLibModule
0x1400018fe  call    cs:__imp_FreeLibrary
0x140001904  mov     eax, ebx
0x140001906  add     rsp, 38h
0x14000190a  pop     rdi
0x14000190b  pop     rsi
0x14000190c  pop     rbp
0x14000190d  pop     rbx
0x14000190e  retn
0x14000190f  lea     rcx, [rsp+58h+arg_10]
0x140001914  xor     r9d, r9d
0x140001917  mov     [rsp+58h+var_38], rcx
0x14000191c  mov     r8, rbx
0x14000191f  lea     rcx, WLDP_HOST_WINDOWS_SCRIPT_HOST
0x140001926  xor     edx, edx
0x140001928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000192d  mov     ebx, eax
0x14000192f  test    eax, eax
0x140001931  js      short loc_1400018FB
0x140001933  xor     ecx, ecx
0x140001935  mov     [rsi+10h], rdi
0x140001939  cmp     [rsp+58h+arg_10], 1
0x14000193e  mov     [rsi+18h], rbp
0x140001942  setnz   cl
0x140001945  mov     [rsi+8], ecx
0x140001948  jmp     short loc_140001904
```
