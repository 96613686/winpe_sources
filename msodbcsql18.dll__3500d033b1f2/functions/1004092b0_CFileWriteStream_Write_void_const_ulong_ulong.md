# CFileWriteStream::Write(void const *,ulong,ulong *)

- ea: `0x1004092b0`
- end: `0x100409331`
- name: `?Write@CFileWriteStream@@UEAAJPEBXKPEAK@Z`
- size: `129`
- prototype: `int(CFileWriteStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x100409338`

## callees

- `0x1004092b0`
- `0x100546a24`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100409315`
- `KERNEL32!GetLastError` at `0x100409315`
- `KERNEL32!WriteFile` at `0x10040930b`
- `KERNEL32!WriteFile` at `0x10040930b`

## pseudocode

```c
__int64 __fastcall CFileWriteStream::Write(CFileWriteStream *this, const void *a2, DWORD a3, unsigned int *a4)
{
  unsigned int v4; // ebx
  unsigned int *v6; // r9
  void *v7; // rcx
  signed int LastError; // eax
  char v10; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  if ( a2 )
  {
    v6 = (unsigned int *)&v10;
    if ( a4 )
      v6 = a4;
    *v6 = 0;
    v7 = (void *)*((_QWORD *)this + 2);
    if ( v7 == (void *)-1LL )
    {
      return (unsigned int)-2147221301;
    }
    else if ( !WriteFile(v7, a2, a3, v6, 0) )
    {
      LastError = GetLastError();
      v4 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        return (unsigned int)LastError;
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    return (unsigned int)bidTraceHR(0, 306185, 2147942487LL, a4);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x1004092b0  push    rbx
0x1004092b2  sub     rsp, 30h
0x1004092b6  xor     ebx, ebx
0x1004092b8  mov     rax, r9
0x1004092bb  test    rdx, rdx
0x1004092be  jnz     short loc_1004092E6
0x1004092c0  test    byte ptr cs:_bidGblFlags, 2
0x1004092c7  jz      short loc_1004092DF
0x1004092c9  mov     edx, 4AC09h
0x1004092ce  xor     ecx, ecx
0x1004092d0  mov     r8d, 80070057h
0x1004092d6  call    _bidTraceHR
0x1004092db  mov     ebx, eax
0x1004092dd  jmp     short loc_100409329
0x1004092df  mov     ebx, 80070057h
0x1004092e4  jmp     short loc_100409329
0x1004092e6  test    rax, rax
0x1004092e9  lea     r9, [rsp+38h+arg_8]
0x1004092ee  cmovnz  r9, rax; lpNumberOfBytesWritten
0x1004092f2  mov     [r9], ebx
0x1004092f5  mov     rcx, [rcx+10h]; hFile
0x1004092f9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1004092fd  jnz     short loc_100409306
0x1004092ff  mov     ebx, 800400CBh
0x100409304  jmp     short loc_100409329
0x100409306  mov     [rsp+38h+lpOverlapped], rbx; lpOverlapped
0x10040930b  call    cs:__imp_WriteFile
0x100409311  test    eax, eax
0x100409313  jnz     short loc_100409329
0x100409315  call    cs:__imp_GetLastError
0x10040931b  movzx   ebx, ax
0x10040931e  or      ebx, 80070000h
0x100409324  test    eax, eax
0x100409326  cmovle  ebx, eax
0x100409329  mov     eax, ebx
0x10040932b  add     rsp, 30h
0x10040932f  pop     rbx
0x100409330  retn
```
