# SetFileTimeAndAttr

- ea: `0x140008d20`
- end: `0x140008e5e`
- name: `SetFileTimeAndAttr`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000873c`

## callees

- `0x140008620`
- `0x140008d20`

## import_xrefs

- `KERNEL32!DosDateTimeToFileTime` at `0x140008dc0`
- `KERNEL32!DosDateTimeToFileTime` at `0x140008dc0`
- `KERNEL32!SetFileAttributesA` at `0x140008e1d`
- `KERNEL32!SetFileAttributesA` at `0x140008e1d`
- `KERNEL32!LocalFileTimeToFileTime` at `0x140008dd5`
- `KERNEL32!LocalFileTimeToFileTime` at `0x140008dd5`
- `KERNEL32!SetFileTime` at `0x140008def`
- `KERNEL32!SetFileTime` at `0x140008def`
- `KERNEL32!CloseHandle` at `0x140008dfc`
- `KERNEL32!CloseHandle` at `0x140008dfc`
- `KERNEL32!CreateFileA` at `0x140008d6a`
- `KERNEL32!CreateFileA` at `0x140008d9f`
- `KERNEL32!CreateFileA` at `0x140008d6a`
- `KERNEL32!CreateFileA` at `0x140008d9f`
- `KERNEL32!Sleep` at `0x140008d7c`
- `KERNEL32!Sleep` at `0x140008d7c`

## pseudocode

```c
__int64 __fastcall SetFileTimeAndAttr(__int64 a1, WORD *a2, __int64 a3)
{
  HANDLE FileA; // rsi
  BOOL v6; // ebx
  int v7; // edi
  int v8; // ebx
  WORD v9; // dx
  DWORD v10; // edx
  struct _FILETIME FileTime; // [rsp+70h] [rbp+8h] BYREF
  FILETIME LastWriteTime; // [rsp+88h] [rbp+20h] BYREF

  FileTime = 0;
  LastWriteTime = 0;
  FileA = CreateFileA(CurrentChar, 0x40000000u, 0, 0, 3u, 0, 0);
  if ( FileA == (HANDLE)-1LL )
  {
    Sleep(0x64u);
    FileA = CreateFileA(CurrentChar, 0x40000000u, 0, 0, 3u, 0, 0);
    if ( FileA == (HANDLE)-1LL )
      return 1;
  }
  v6 = DosDateTimeToFileTime(*a2, a2[1], &FileTime);
  v7 = v6 | LocalFileTimeToFileTime(&FileTime, &LastWriteTime);
  v8 = v7 | SetFileTime(FileA, 0, 0, &LastWriteTime);
  CloseHandle(FileA);
  v9 = a2[2];
  v10 = v9 ? v9 & 0x27 : 128;
  if ( v8 | SetFileAttributesA(CurrentChar, v10) )
    return 1;
  ErrSet(a3, "Cannot set date/time/attributes for file: %1", "%s", CurrentChar);
  return 0;
}

```

## disassembly

```asm
0x140008d20  mov     rax, rsp
0x140008d23  mov     [rax+10h], rbx
0x140008d27  mov     [rax+8], rcx
0x140008d2b  push    rbp
0x140008d2c  push    rsi
0x140008d2d  push    rdi
0x140008d2e  push    r14
0x140008d30  push    r15
0x140008d32  sub     rsp, 40h
0x140008d36  xor     r15d, r15d
0x140008d39  lea     rcx, CurrentChar; lpFileName
0x140008d40  mov     [rax-38h], r15
0x140008d44  mov     rbp, r8
0x140008d47  mov     r14, rdx
0x140008d4a  mov     [rax-40h], r15d
0x140008d4e  mov     edi, 40000000h
0x140008d53  mov     [rax+8], r15
0x140008d57  lea     ebx, [r15+3]
0x140008d5b  mov     [rax+20h], r15
0x140008d5f  xor     r9d, r9d; lpSecurityAttributes
0x140008d62  mov     [rax-48h], ebx
0x140008d65  xor     r8d, r8d; dwShareMode
0x140008d68  mov     edx, edi; dwDesiredAccess
0x140008d6a  call    cs:__imp_CreateFileA
0x140008d70  mov     rsi, rax
0x140008d73  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140008d77  jnz     short loc_140008DB2
0x140008d79  lea     ecx, [rbx+61h]; dwMilliseconds
0x140008d7c  call    cs:__imp_Sleep
0x140008d82  mov     [rsp+68h+hTemplateFile], r15; hTemplateFile
0x140008d87  lea     rcx, CurrentChar; lpFileName
0x140008d8e  mov     [rsp+68h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x140008d93  xor     r9d, r9d; lpSecurityAttributes
0x140008d96  xor     r8d, r8d; dwShareMode
0x140008d99  mov     [rsp+68h+dwCreationDisposition], ebx; dwCreationDisposition
0x140008d9d  mov     edx, edi; dwDesiredAccess
0x140008d9f  call    cs:__imp_CreateFileA
0x140008da5  mov     rsi, rax
0x140008da8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140008dac  jz      loc_140008E48
0x140008db2  movzx   edx, word ptr [r14+2]; wFatTime
0x140008db7  lea     r8, [rsp+68h+FileTime]; lpFileTime
0x140008dbc  movzx   ecx, word ptr [r14]; wFatDate
0x140008dc0  call    cs:__imp_DosDateTimeToFileTime
0x140008dc6  lea     rdx, [rsp+68h+LastWriteTime]; lpFileTime
0x140008dce  mov     ebx, eax
0x140008dd0  lea     rcx, [rsp+68h+FileTime]; lpLocalFileTime
0x140008dd5  call    cs:__imp_LocalFileTimeToFileTime
0x140008ddb  lea     r9, [rsp+68h+LastWriteTime]; lpLastWriteTime
0x140008de3  xor     r8d, r8d; lpLastAccessTime
0x140008de6  mov     edi, eax
0x140008de8  xor     edx, edx; lpCreationTime
0x140008dea  mov     rcx, rsi; hFile
0x140008ded  or      edi, ebx
0x140008def  call    cs:__imp_SetFileTime
0x140008df5  mov     ebx, eax
0x140008df7  mov     rcx, rsi; hObject
0x140008dfa  or      ebx, edi
0x140008dfc  call    cs:__imp_CloseHandle
0x140008e02  movzx   edx, word ptr [r14+4]
0x140008e07  test    dx, dx
0x140008e0a  jnz     short loc_140008E13
0x140008e0c  mov     edx, 80h
0x140008e11  jmp     short loc_140008E16
0x140008e13  and     edx, 27h; dwFileAttributes
0x140008e16  lea     rcx, CurrentChar; lpFileName
0x140008e1d  call    cs:__imp_SetFileAttributesA
0x140008e23  or      eax, ebx
0x140008e25  jnz     short loc_140008E48
0x140008e27  lea     r9, CurrentChar
0x140008e2e  mov     rcx, rbp
0x140008e31  lea     r8, aS_4; "%s"
0x140008e38  lea     rdx, aCannotSetDateT; "Cannot set date/time/attributes for fil"...
0x140008e3f  call    ErrSet
0x140008e44  xor     eax, eax
0x140008e46  jmp     short loc_140008E4D
0x140008e48  mov     eax, 1
0x140008e4d  mov     rbx, [rsp+68h+arg_8]
0x140008e52  add     rsp, 40h
0x140008e56  pop     r15
0x140008e58  pop     r14
0x140008e5a  pop     rdi
0x140008e5b  pop     rsi
0x140008e5c  pop     rbp
0x140008e5d  retn
```
