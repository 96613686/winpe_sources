# CopyStreamToFile(IStream *,ushort const *,ulong)

- ea: `0x18000abf0`
- end: `0x18000ad56`
- name: `?CopyStreamToFile@@YAJPEAUIStream@@PEBGK@Z`
- size: `358`
- prototype: `__int64 __fastcall(struct IStream *, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180007cf8`
- `0x1800098ac`
- `0x180009dd8`

## callees

- `0x18000abf0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad26`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000acfa`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000acfa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ac6c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ac6c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000ac2d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000ac2d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000ad2f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000ad2f`

## pseudocode

```c
__int64 __fastcall CopyStreamToFile(struct IStream *a1, const unsigned __int16 *a2, unsigned int a3)
{
  HGLOBAL v6; // rsi
  unsigned int v7; // ebx
  HANDLE FileW; // rbp
  int v9; // edi
  DWORD v10; // ecx
  int v11; // ebx
  unsigned int v12; // r12d
  __int64 v13; // r8
  int v14; // eax
  DWORD v15; // r8d
  BOOL v16; // eax
  DWORD nNumberOfBytesToWrite; // [rsp+80h] [rbp+8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+98h] [rbp+20h] BYREF

  if ( !a1 || !a2 )
    return 2147500035LL;
  v6 = GlobalAlloc(0x40u, 0x1000u);
  if ( v6 )
  {
    FileW = CreateFileW(a2, 0x40000000u, 0, 0, 1u, 0x8000000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      v7 = -2147467259;
    }
    else
    {
      v9 = 0;
      nNumberOfBytesToWrite = 4096;
      v10 = 4096;
      v11 = 0;
      NumberOfBytesWritten = 4096;
      v12 = a3;
      do
      {
        if ( v10 != 4096 )
          break;
        v13 = 4096;
        if ( v12 < 0x1000 )
          v13 = v12;
        v14 = ((__int64 (__fastcall *)(struct IStream *, HGLOBAL, __int64, DWORD *))a1->lpVtbl->Read)(
                a1,
                v6,
                v13,
                &nNumberOfBytesToWrite);
        v12 -= nNumberOfBytesToWrite;
        v9 = v14;
        v15 = a3 - v11;
        if ( nNumberOfBytesToWrite + v11 <= a3 )
          v15 = nNumberOfBytesToWrite;
        v16 = WriteFile(FileW, v6, v15, &NumberOfBytesWritten, 0);
        v10 = NumberOfBytesWritten;
        if ( v16 )
          v11 += NumberOfBytesWritten;
      }
      while ( nNumberOfBytesToWrite == 4096 );
      if ( v9 )
        v9 = -2147467259;
      v7 = v9;
      CloseHandle(FileW);
    }
    GlobalFree(v6);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x18000abf0  mov     [rsp+arg_8], rbx
0x18000abf5  push    rbp
0x18000abf6  push    rsi
0x18000abf7  push    rdi
0x18000abf8  push    r12
0x18000abfa  push    r13
0x18000abfc  push    r14
0x18000abfe  push    r15
0x18000ac00  sub     rsp, 40h
0x18000ac04  mov     r15d, r8d
0x18000ac07  mov     rbx, rdx
0x18000ac0a  mov     r14, rcx
0x18000ac0d  test    rcx, rcx
0x18000ac10  jz      loc_18000AD39
0x18000ac16  test    rdx, rdx
0x18000ac19  jz      loc_18000AD39
0x18000ac1f  mov     r13d, 1000h
0x18000ac25  mov     ecx, 40h ; '@'; uFlags
0x18000ac2a  mov     edx, r13d; dwBytes
0x18000ac2d  call    cs:__imp_GlobalAlloc
0x18000ac33  mov     rsi, rax
0x18000ac36  test    rax, rax
0x18000ac39  jnz     short loc_18000AC45
0x18000ac3b  mov     ebx, 8007000Eh
0x18000ac40  jmp     loc_18000AD35
0x18000ac45  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18000ac4e  xor     r9d, r9d; lpSecurityAttributes
0x18000ac51  mov     [rsp+78h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18000ac59  xor     r8d, r8d; dwShareMode
0x18000ac5c  mov     edx, 40000000h; dwDesiredAccess
0x18000ac61  mov     [rsp+78h+dwCreationDisposition], 1; dwCreationDisposition
0x18000ac69  mov     rcx, rbx; lpFileName
0x18000ac6c  call    cs:__imp_CreateFileW
0x18000ac72  mov     rbp, rax
0x18000ac75  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ac79  jnz     short loc_18000AC85
0x18000ac7b  mov     ebx, 80004005h
0x18000ac80  jmp     loc_18000AD2C
0x18000ac85  xor     edi, edi
0x18000ac87  mov     [rsp+78h+nNumberOfBytesToWrite], r13d
0x18000ac8f  mov     ecx, r13d
0x18000ac92  xor     ebx, ebx
0x18000ac94  mov     [rsp+78h+NumberOfBytesWritten], ecx
0x18000ac9b  mov     r12d, r15d
0x18000ac9e  cmp     ecx, r13d
0x18000aca1  jnz     short loc_18000AD17
0x18000aca3  mov     rax, [r14]
0x18000aca6  lea     r9, [rsp+78h+nNumberOfBytesToWrite]
0x18000acae  mov     r8d, r13d
0x18000acb1  cmp     r12d, r13d
0x18000acb4  mov     rdx, rsi
0x18000acb7  mov     rcx, r14
0x18000acba  cmovb   r8d, r12d
0x18000acbe  mov     rax, [rax+18h]
0x18000acc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acc7  mov     edx, [rsp+78h+nNumberOfBytesToWrite]
0x18000acce  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000acd6  sub     r12d, edx
0x18000acd9  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOverlapped
0x18000ace2  mov     r8d, r15d
0x18000ace5  mov     edi, eax
0x18000ace7  sub     r8d, ebx
0x18000acea  lea     ecx, [rdx+rbx]
0x18000aced  cmp     ecx, r15d
0x18000acf0  mov     rcx, rbp; hFile
0x18000acf3  cmovbe  r8d, edx; nNumberOfBytesToWrite
0x18000acf7  mov     rdx, rsi; lpBuffer
0x18000acfa  call    cs:__imp_WriteFile
0x18000ad00  mov     ecx, [rsp+78h+NumberOfBytesWritten]
0x18000ad07  test    eax, eax
0x18000ad09  jz      short loc_18000AD0D
0x18000ad0b  add     ebx, ecx
0x18000ad0d  cmp     [rsp+78h+nNumberOfBytesToWrite], r13d
0x18000ad15  jz      short loc_18000AC9E
0x18000ad17  mov     ebx, 80004005h
0x18000ad1c  test    edi, edi
0x18000ad1e  cmovnz  edi, ebx
0x18000ad21  mov     ebx, edi
0x18000ad23  mov     rcx, rbp; hObject
0x18000ad26  call    cs:__imp_CloseHandle
0x18000ad2c  mov     rcx, rsi; hMem
0x18000ad2f  call    cs:__imp_GlobalFree
0x18000ad35  mov     eax, ebx
0x18000ad37  jmp     short loc_18000AD3E
0x18000ad39  mov     eax, 80004003h
0x18000ad3e  mov     rbx, [rsp+78h+arg_8]
0x18000ad46  add     rsp, 40h
0x18000ad4a  pop     r15
0x18000ad4c  pop     r14
0x18000ad4e  pop     r13
0x18000ad50  pop     r12
0x18000ad52  pop     rdi
0x18000ad53  pop     rsi
0x18000ad54  pop     rbp
0x18000ad55  retn
```
