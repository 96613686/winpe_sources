# CFileWriter::Seek(__int64,ulong)

- ea: `0x18012a8a0`
- end: `0x18012a9d4`
- name: `?Seek@CFileWriter@@UEAAJ_JK@Z`
- size: `308`
- prototype: `int(CFileWriter *__hidden this, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180003d80`
- `0x18012a8a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18012a8f6`
- `KERNEL32!GetLastError` at `0x18012a900`
- `KERNEL32!GetLastError` at `0x18012a950`
- `KERNEL32!GetLastError` at `0x18012a99a`
- `KERNEL32!GetLastError` at `0x18012a9a4`
- `KERNEL32!GetLastError` at `0x18012a8f6`
- `KERNEL32!GetLastError` at `0x18012a900`
- `KERNEL32!GetLastError` at `0x18012a950`
- `KERNEL32!GetLastError` at `0x18012a99a`
- `KERNEL32!GetLastError` at `0x18012a9a4`
- `KERNEL32!SetFilePointer` at `0x18012a941`
- `KERNEL32!SetFilePointer` at `0x18012a98f`
- `KERNEL32!SetFilePointer` at `0x18012a941`
- `KERNEL32!SetFilePointer` at `0x18012a98f`
- `KERNEL32!GetFileSize` at `0x18012a8e8`
- `KERNEL32!GetFileSize` at `0x18012a8e8`

## pseudocode

```c
int __fastcall CFileWriter::Seek(CFileWriter *this, __int64 a2, DWORD a3)
{
  int v3; // edi
  void *v5; // rcx
  int result; // eax
  DWORD FileSize; // eax
  void *v10; // rcx
  signed int LastError; // eax
  LONG DistanceToMoveHigh[2]; // [rsp+20h] [rbp-38h] BYREF
  LONG v13[2]; // [rsp+28h] [rbp-30h] BYREF

  v3 = 0;
  v5 = (void *)*((_QWORD *)this + 1);
  *(_QWORD *)v13 = 0;
  DistanceToMoveHigh[1] = 0;
  if ( v5 == (void *)-1LL )
    return -2147221301;
  FileSize = GetFileSize(v5, (LPDWORD)this + 5);
  *((_DWORD *)this + 4) = FileSize;
  if ( FileSize == -1 && GetLastError() )
  {
LABEL_5:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( a3 )
  {
    if ( a3 != 1 )
      return -2147024809;
    DistanceToMoveHigh[0] = SetFilePointer(*((HANDLE *)this + 1), 0, &DistanceToMoveHigh[1], 1u);
    if ( DistanceToMoveHigh[0] == -1 && GetLastError() )
      goto LABEL_5;
    if ( a2 + *(_QWORD *)DistanceToMoveHigh > *((_QWORD *)this + 2) )
      return -2147221297;
  }
  else if ( a2 > *((_QWORD *)this + 2) )
  {
    return -2147221297;
  }
  v10 = (void *)*((_QWORD *)this + 1);
  *(_QWORD *)v13 = a2;
  if ( SetFilePointer(v10, a2, &v13[1], a3) == -1 && GetLastError() )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return LastError;
  }
  return v3;
}

```

## disassembly

```asm
0x18012a8a0  mov     [rsp+arg_18], rbx
0x18012a8a5  push    rbp
0x18012a8a6  push    rsi
0x18012a8a7  push    rdi
0x18012a8a8  sub     rsp, 40h
0x18012a8ac  mov     rax, cs:__security_cookie
0x18012a8b3  xor     rax, rsp
0x18012a8b6  mov     [rsp+58h+var_28], rax
0x18012a8bb  xor     edi, edi
0x18012a8bd  mov     rbx, rcx
0x18012a8c0  mov     rcx, [rcx+8]; hFile
0x18012a8c4  mov     ebp, r8d
0x18012a8c7  mov     qword ptr [rsp+58h+var_30], rdi
0x18012a8cc  mov     rsi, rdx
0x18012a8cf  mov     qword ptr [rsp+58h+DistanceToMoveHigh], rdi
0x18012a8d4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18012a8d8  jnz     short loc_18012A8E4
0x18012a8da  mov     eax, 800400CBh
0x18012a8df  jmp     loc_18012A9BA
0x18012a8e4  lea     rdx, [rbx+14h]; lpFileSizeHigh
0x18012a8e8  call    cs:__imp_GetFileSize
0x18012a8ee  mov     [rbx+10h], eax
0x18012a8f1  cmp     eax, 0FFFFFFFFh
0x18012a8f4  jnz     short loc_18012A91B
0x18012a8f6  call    cs:__imp_GetLastError
0x18012a8fc  test    eax, eax
0x18012a8fe  jz      short loc_18012A91B
0x18012a900  call    cs:__imp_GetLastError
0x18012a906  test    eax, eax
0x18012a908  jle     loc_18012A9BA
0x18012a90e  movzx   eax, ax
0x18012a911  or      eax, 80070000h
0x18012a916  jmp     loc_18012A9BA
0x18012a91b  mov     eax, ebp
0x18012a91d  test    ebp, ebp
0x18012a91f  jz      short loc_18012A96F
0x18012a921  cmp     eax, 1
0x18012a924  jz      short loc_18012A930
0x18012a926  mov     eax, 80070057h
0x18012a92b  jmp     loc_18012A9BA
0x18012a930  mov     rcx, [rbx+8]; hFile
0x18012a934  lea     r8, [rsp+58h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18012a939  mov     r9d, 1; dwMoveMethod
0x18012a93f  xor     edx, edx; lDistanceToMove
0x18012a941  call    cs:__imp_SetFilePointer
0x18012a947  mov     [rsp+58h+DistanceToMoveHigh], eax
0x18012a94b  cmp     eax, 0FFFFFFFFh
0x18012a94e  jnz     short loc_18012A95A
0x18012a950  call    cs:__imp_GetLastError
0x18012a956  test    eax, eax
0x18012a958  jnz     short loc_18012A900
0x18012a95a  mov     rcx, qword ptr [rsp+58h+DistanceToMoveHigh]
0x18012a95f  add     rcx, rsi
0x18012a962  cmp     rcx, [rbx+10h]
0x18012a966  jle     short loc_18012A97C
0x18012a968  mov     eax, 800400CFh
0x18012a96d  jmp     short loc_18012A9BA
0x18012a96f  cmp     rsi, [rbx+10h]
0x18012a973  jle     short loc_18012A97C
0x18012a975  mov     eax, 800400CFh
0x18012a97a  jmp     short loc_18012A9BA
0x18012a97c  mov     rcx, [rbx+8]; hFile
0x18012a980  lea     r8, [rsp+58h+var_30+4]; lpDistanceToMoveHigh
0x18012a985  mov     r9d, ebp; dwMoveMethod
0x18012a988  mov     qword ptr [rsp+58h+var_30], rsi
0x18012a98d  mov     edx, esi; lDistanceToMove
0x18012a98f  call    cs:__imp_SetFilePointer
0x18012a995  cmp     eax, 0FFFFFFFFh
0x18012a998  jnz     short loc_18012A9B8
0x18012a99a  call    cs:__imp_GetLastError
0x18012a9a0  test    eax, eax
0x18012a9a2  jz      short loc_18012A9B8
0x18012a9a4  call    cs:__imp_GetLastError
0x18012a9aa  test    eax, eax
0x18012a9ac  jle     short loc_18012A9B6
0x18012a9ae  movzx   eax, ax
0x18012a9b1  or      eax, 80070000h
0x18012a9b6  mov     edi, eax
0x18012a9b8  mov     eax, edi
0x18012a9ba  mov     rcx, [rsp+58h+var_28]
0x18012a9bf  xor     rcx, rsp; StackCookie
0x18012a9c2  call    __security_check_cookie
0x18012a9c7  mov     rbx, [rsp+58h+arg_18]
0x18012a9cc  add     rsp, 40h
0x18012a9d0  pop     rdi
0x18012a9d1  pop     rsi
0x18012a9d2  pop     rbp
0x18012a9d3  retn
```
