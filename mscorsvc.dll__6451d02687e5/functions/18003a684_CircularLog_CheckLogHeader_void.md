# CircularLog::CheckLogHeader(void)

- ea: `0x18003a684`
- end: `0x18003a73e`
- name: `?CheckLogHeader@CircularLog@@IEAAHXZ`
- size: `186`
- prototype: `__int64 __fastcall(CircularLog *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18003a1e8`
- `0x18003a740`

## callees

- `0x180030d84`
- `0x18003a684`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18003a6fc`
- `KERNEL32!ReadFile` at `0x18003a6fc`
- `KERNEL32!CreateFileW` at `0x18003a6c5`
- `KERNEL32!CreateFileW` at `0x18003a6c5`
- `KERNEL32!CloseHandle` at `0x18003a72d`
- `KERNEL32!CloseHandle` at `0x18003a72d`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CircularLog::CheckLogHeader(CircularLog *this)
{
  unsigned int v1; // ebx
  HANDLE FileW; // rax
  void *v3; // rdi
  BOOL v4; // eax
  __int16 Buffer; // [rsp+68h] [rbp+10h] BYREF
  char v7; // [rsp+6Ah] [rbp+12h]
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+18h] BYREF

  v1 = 0;
  SString::ConvertToUnicode((SString *)&qword_18006F258);
  FileW = CreateFileW(lpFileName, 1u, 3u, 0, 3u, 0x80u, 0);
  v3 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    NumberOfBytesRead = 3;
    v4 = ReadFile(FileW, &Buffer, 3u, &NumberOfBytesRead, 0);
    LOBYTE(v1) = !v4;
    if ( v4 && (NumberOfBytesRead != 3 || Buffer != -17425 || v7 != -65) )
      v1 = 1;
    CloseHandle(v3);
  }
  return v1;
}

```

## disassembly

```asm
0x18003a684  mov     [rsp+arg_0], rcx
0x18003a689  push    rbx
0x18003a68a  push    rdi
0x18003a68b  push    r14
0x18003a68d  sub     rsp, 40h
0x18003a691  lea     rcx, qword_18006F258; this
0x18003a698  xor     ebx, ebx
0x18003a69a  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003a69f  and     [rsp+58h+var_28], rbx
0x18003a6a4  lea     edx, [rbx+1]; dwDesiredAccess
0x18003a6a7  mov     rcx, cs:lpFileName; lpFileName
0x18003a6ae  lea     r8d, [rbx+3]; dwShareMode
0x18003a6b2  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003a6ba  xor     r9d, r9d; lpSecurityAttributes
0x18003a6bd  mov     [rsp+58h+dwCreationDisposition], 3; lpOverlapped
0x18003a6c5  call    cs:__imp_CreateFileW
0x18003a6cb  mov     rdi, rax
0x18003a6ce  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003a6d2  jz      short loc_18003A733
0x18003a6d4  and     qword ptr [rsp+58h+dwCreationDisposition], rbx
0x18003a6d9  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003a6de  lea     r8d, [rbx+3]; nNumberOfBytesToRead
0x18003a6e2  mov     word ptr [rsp+58h+arg_0], 0BBEFh
0x18003a6e9  lea     rdx, [rsp+58h+Buffer]; lpBuffer
0x18003a6ee  mov     [rsp+58h+NumberOfBytesRead], 3
0x18003a6f6  mov     rcx, rax; hFile
0x18003a6f9  mov     r14b, 0BFh
0x18003a6fc  call    cs:__imp_ReadFile
0x18003a702  test    eax, eax
0x18003a704  setz    bl
0x18003a707  test    eax, eax
0x18003a709  jz      short loc_18003A72A
0x18003a70b  cmp     [rsp+58h+NumberOfBytesRead], 3
0x18003a710  jnz     short loc_18003A725
0x18003a712  movzx   eax, word ptr [rsp+58h+arg_0]
0x18003a717  cmp     ax, [rsp+58h+Buffer]
0x18003a71c  jnz     short loc_18003A725
0x18003a71e  cmp     r14b, [rsp+58h+arg_A]
0x18003a723  jz      short loc_18003A72A
0x18003a725  mov     ebx, 1
0x18003a72a  mov     rcx, rdi; hObject
0x18003a72d  call    cs:__imp_CloseHandle
0x18003a733  mov     eax, ebx
0x18003a735  add     rsp, 40h
0x18003a739  pop     r14
0x18003a73b  pop     rdi
0x18003a73c  pop     rbx
0x18003a73d  retn
```
