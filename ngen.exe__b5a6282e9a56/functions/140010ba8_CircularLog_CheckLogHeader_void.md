# CircularLog::CheckLogHeader(void)

- ea: `0x140010ba8`
- end: `0x140010c68`
- name: `?CheckLogHeader@CircularLog@@IEAAHXZ`
- size: `192`
- prototype: `__int64 __fastcall(CircularLog *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14001070c`
- `0x140010c68`

## callees

- `0x14000b010`
- `0x140010ba8`

## import_xrefs

- `KERNEL32!ReadFile` at `0x140010c25`
- `KERNEL32!ReadFile` at `0x140010c25`
- `KERNEL32!CreateFileW` at `0x140010bec`
- `KERNEL32!CreateFileW` at `0x140010bec`
- `KERNEL32!CloseHandle` at `0x140010c57`
- `KERNEL32!CloseHandle` at `0x140010c57`

## pseudocode

```c
__int64 __fastcall CircularLog::CheckLogHeader(CircularLog *this)
{
  unsigned int v1; // edi
  char *v2; // rbx
  const WCHAR *v3; // rcx
  HANDLE FileW; // rax
  void *v5; // rbx
  BOOL v6; // eax
  __int16 Buffer; // [rsp+68h] [rbp+10h] BYREF
  char v9; // [rsp+6Ah] [rbp+12h]
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+18h] BYREF

  v1 = 0;
  v2 = (char *)this + 8;
  if ( this == (CircularLog *)-8LL )
  {
    v3 = 0;
  }
  else
  {
    SString::ConvertToUnicode((CircularLog *)((char *)this + 8));
    v3 = (const WCHAR *)*((_QWORD *)v2 + 2);
  }
  FileW = CreateFileW(v3, 1u, 3u, 0, 3u, 0x80u, 0);
  v5 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    NumberOfBytesRead = 3;
    v6 = ReadFile(FileW, &Buffer, 3u, &NumberOfBytesRead, 0);
    LOBYTE(v1) = !v6;
    if ( v6 && (NumberOfBytesRead != 3 || Buffer != -17425 || v9 != -65) )
      v1 = 1;
    CloseHandle(v5);
  }
  return v1;
}

```

## disassembly

```asm
0x140010ba8  push    rbx
0x140010baa  push    rdi
0x140010bab  push    r14
0x140010bad  sub     rsp, 40h
0x140010bb1  xor     edi, edi
0x140010bb3  lea     rbx, [rcx+8]
0x140010bb7  test    rbx, rbx
0x140010bba  jnz     short loc_140010BC0
0x140010bbc  xor     ecx, ecx
0x140010bbe  jmp     short loc_140010BCC
0x140010bc0  mov     rcx, rbx; this
0x140010bc3  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140010bc8  mov     rcx, [rbx+10h]; lpFileName
0x140010bcc  and     [rsp+58h+var_28], rdi
0x140010bd1  xor     r9d, r9d; lpSecurityAttributes
0x140010bd4  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140010bdc  mov     [rsp+58h+dwCreationDisposition], 3; lpOverlapped
0x140010be4  lea     edx, [r9+1]; dwDesiredAccess
0x140010be8  lea     r8d, [r9+3]; dwShareMode
0x140010bec  call    cs:__imp_CreateFileW
0x140010bf2  mov     rbx, rax
0x140010bf5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140010bf9  jz      short loc_140010C5D
0x140010bfb  and     qword ptr [rsp+58h+dwCreationDisposition], rdi
0x140010c00  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140010c05  mov     r8d, 3; nNumberOfBytesToRead
0x140010c0b  mov     [rsp+58h+arg_0], 0BBEFh
0x140010c12  lea     rdx, [rsp+58h+Buffer]; lpBuffer
0x140010c17  mov     [rsp+58h+NumberOfBytesRead], 3
0x140010c1f  mov     rcx, rax; hFile
0x140010c22  mov     r14b, 0BFh
0x140010c25  call    cs:__imp_ReadFile
0x140010c2b  test    eax, eax
0x140010c2d  setz    dil
0x140010c31  test    eax, eax
0x140010c33  jz      short loc_140010C54
0x140010c35  cmp     [rsp+58h+NumberOfBytesRead], 3
0x140010c3a  jnz     short loc_140010C4F
0x140010c3c  movzx   eax, [rsp+58h+arg_0]
0x140010c41  cmp     ax, [rsp+58h+Buffer]
0x140010c46  jnz     short loc_140010C4F
0x140010c48  cmp     r14b, [rsp+58h+arg_A]
0x140010c4d  jz      short loc_140010C54
0x140010c4f  mov     edi, 1
0x140010c54  mov     rcx, rbx; hObject
0x140010c57  call    cs:__imp_CloseHandle
0x140010c5d  mov     eax, edi
0x140010c5f  add     rsp, 40h
0x140010c63  pop     r14
0x140010c65  pop     rdi
0x140010c66  pop     rbx
0x140010c67  retn
```
