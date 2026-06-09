# SafeLoadLibrary

- ea: `0x14000929c`
- end: `0x14000939e`
- name: `SafeLoadLibrary`
- size: `258`
- prototype: `__int64 __fastcall(char *Source)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x140010d64`
- `0x140010fd4`

## callees

- `0x14000929c`
- `0x140009c70`
- `0x140009cb0`

## import_xrefs

- `msvcrt!strcpy_s` at `0x140009350`
- `msvcrt!strcpy_s` at `0x140009360`
- `msvcrt!strcpy_s` at `0x140009350`
- `msvcrt!strcpy_s` at `0x140009360`
- `KERNEL32!GetSystemDirectoryA` at `0x1400092c2`
- `KERNEL32!GetSystemDirectoryA` at `0x14000931a`
- `KERNEL32!GetSystemDirectoryA` at `0x1400092c2`
- `KERNEL32!GetSystemDirectoryA` at `0x14000931a`
- `KERNEL32!GetLastError` at `0x1400092ce`
- `KERNEL32!GetLastError` at `0x140009324`
- `KERNEL32!GetLastError` at `0x1400092ce`
- `KERNEL32!GetLastError` at `0x140009324`
- `KERNEL32!LoadLibraryExA` at `0x140009371`
- `KERNEL32!LoadLibraryExA` at `0x140009371`

## pseudocode

```c
__int64 __fastcall SafeLoadLibrary(char *Source, HMODULE *a2)
{
  UINT SystemDirectoryA; // ebx
  signed int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  unsigned int v8; // edi
  CHAR *v9; // rax
  CHAR *v10; // rsi
  UINT v11; // eax
  signed int LastError; // eax
  UINT v13; // ebx
  char *v14; // rdi
  HMODULE Library; // rax
  CHAR Buffer; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  SystemDirectoryA = GetSystemDirectoryA(&Buffer, 0);
  if ( SystemDirectoryA )
  {
    v7 = -1;
    do
      ++v7;
    while ( Source[v7] );
    v8 = v7 + SystemDirectoryA + 2;
    v9 = (CHAR *)operator new(v8);
    v10 = v9;
    if ( v9 )
    {
      v11 = GetSystemDirectoryA(v9, SystemDirectoryA + 1);
      if ( v11
        && (v13 = v8 - v11,
            v14 = &v10[v11],
            strcpy_s(v14, v13, "\\"),
            strcpy_s(v14 + 1, v13 - 1, Source),
            (Library = LoadLibraryExA(v10, 0, 0x800u)) != 0) )
      {
        *a2 = Library;
        v6 = 0;
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
      operator delete(v10);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x14000929c  mov     [rsp+arg_0], rbx
0x1400092a1  mov     [rsp+arg_10], rbp
0x1400092a6  push    rsi
0x1400092a7  push    rdi
0x1400092a8  push    r14
0x1400092aa  sub     rsp, 20h
0x1400092ae  mov     r14, rdx
0x1400092b1  mov     qword ptr [rdx], 0
0x1400092b8  mov     rbp, rcx
0x1400092bb  xor     edx, edx; uSize
0x1400092bd  lea     rcx, [rsp+38h+Buffer]; lpBuffer
0x1400092c2  call    cs:__imp_GetSystemDirectoryA
0x1400092c8  mov     ebx, eax
0x1400092ca  test    eax, eax
0x1400092cc  jnz     short loc_1400092EC
0x1400092ce  call    cs:__imp_GetLastError
0x1400092d4  mov     ebx, eax
0x1400092d6  test    eax, eax
0x1400092d8  jle     loc_140009389
0x1400092de  movzx   ebx, ax
0x1400092e1  or      ebx, 80070000h
0x1400092e7  jmp     loc_140009389
0x1400092ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400092f0  inc     rax
0x1400092f3  cmp     byte ptr [rax+rbp], 0
0x1400092f7  jnz     short loc_1400092F0
0x1400092f9  lea     edi, [rbx+2]
0x1400092fc  add     edi, eax
0x1400092fe  mov     ecx, edi; Size
0x140009300  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009305  mov     rsi, rax
0x140009308  test    rax, rax
0x14000930b  jnz     short loc_140009314
0x14000930d  mov     ebx, 8007000Eh
0x140009312  jmp     short loc_140009389
0x140009314  lea     edx, [rbx+1]; uSize
0x140009317  mov     rcx, rsi; lpBuffer
0x14000931a  call    cs:__imp_GetSystemDirectoryA
0x140009320  test    eax, eax
0x140009322  jnz     short loc_14000933B
0x140009324  call    cs:__imp_GetLastError
0x14000932a  mov     ebx, eax
0x14000932c  test    eax, eax
0x14000932e  jle     short loc_140009381
0x140009330  movzx   ebx, ax
0x140009333  or      ebx, 80070000h
0x140009339  jmp     short loc_140009381
0x14000933b  sub     edi, eax
0x14000933d  lea     r8, asc_14001A1DC; "\\"
0x140009344  mov     ebx, edi
0x140009346  mov     edi, eax
0x140009348  mov     edx, ebx; SizeInBytes
0x14000934a  add     rdi, rsi
0x14000934d  mov     rcx, rdi; Destination
0x140009350  call    cs:__imp_strcpy_s
0x140009356  lea     edx, [rbx-1]; SizeInBytes
0x140009359  mov     r8, rbp; Source
0x14000935c  lea     rcx, [rdi+1]; Destination
0x140009360  call    cs:__imp_strcpy_s
0x140009366  xor     edx, edx; hFile
0x140009368  mov     r8d, 800h; dwFlags
0x14000936e  mov     rcx, rsi; lpLibFileName
0x140009371  call    cs:__imp_LoadLibraryExA
0x140009377  test    rax, rax
0x14000937a  jz      short loc_140009324
0x14000937c  mov     [r14], rax
0x14000937f  xor     ebx, ebx
0x140009381  mov     rcx, rsi; Block
0x140009384  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140009389  mov     rbp, [rsp+38h+arg_10]
0x14000938e  mov     eax, ebx
0x140009390  mov     rbx, [rsp+38h+arg_0]
0x140009395  add     rsp, 20h
0x140009399  pop     r14
0x14000939b  pop     rdi
0x14000939c  pop     rsi
0x14000939d  retn
```
