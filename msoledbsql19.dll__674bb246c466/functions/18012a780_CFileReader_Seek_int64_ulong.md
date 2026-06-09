# CFileReader::Seek(__int64,ulong)

- ea: `0x18012a780`
- end: `0x18012a88d`
- name: `?Seek@CFileReader@@UEAAJ_JK@Z`
- size: `269`
- prototype: `int(CFileReader *__hidden this, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180003d80`
- `0x18012a780`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18012a7f5`
- `KERNEL32!GetLastError` at `0x18012a7ff`
- `KERNEL32!GetLastError` at `0x18012a853`
- `KERNEL32!GetLastError` at `0x18012a85d`
- `KERNEL32!GetLastError` at `0x18012a7f5`
- `KERNEL32!GetLastError` at `0x18012a7ff`
- `KERNEL32!GetLastError` at `0x18012a853`
- `KERNEL32!GetLastError` at `0x18012a85d`
- `KERNEL32!SetFilePointer` at `0x18012a7e6`
- `KERNEL32!SetFilePointer` at `0x18012a848`
- `KERNEL32!SetFilePointer` at `0x18012a7e6`
- `KERNEL32!SetFilePointer` at `0x18012a848`

## pseudocode

```c
int __fastcall CFileReader::Seek(CFileReader *this, __int64 a2, DWORD a3)
{
  int v3; // ebx
  void *v5; // rcx
  int result; // eax
  void *v9; // rcx
  signed int LastError; // eax
  LONG DistanceToMoveHigh[2]; // [rsp+20h] [rbp-38h] BYREF
  LONG v12[2]; // [rsp+28h] [rbp-30h] BYREF

  v3 = 0;
  v5 = (void *)*((_QWORD *)this + 1);
  *(_QWORD *)v12 = 0;
  DistanceToMoveHigh[1] = 0;
  if ( v5 == (void *)-1LL )
    return -2147221301;
  if ( a3 )
  {
    if ( a3 != 1 )
      return -2147024809;
    DistanceToMoveHigh[0] = SetFilePointer(v5, 0, &DistanceToMoveHigh[1], 1u);
    if ( DistanceToMoveHigh[0] == -1 && GetLastError() )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    if ( a2 + *(_QWORD *)DistanceToMoveHigh > *((_QWORD *)this + 2) )
      return -2147221300;
  }
  else if ( a2 > *((_QWORD *)this + 2) )
  {
    return -2147221300;
  }
  v9 = (void *)*((_QWORD *)this + 1);
  *(_QWORD *)v12 = a2;
  if ( SetFilePointer(v9, a2, &v12[1], a3) == -1 && GetLastError() )
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
0x18012a780  mov     [rsp+arg_18], rbx
0x18012a785  push    rbp
0x18012a786  push    rsi
0x18012a787  push    rdi
0x18012a788  sub     rsp, 40h
0x18012a78c  mov     rax, cs:__security_cookie
0x18012a793  xor     rax, rsp
0x18012a796  mov     [rsp+58h+var_28], rax
0x18012a79b  xor     ebx, ebx
0x18012a79d  mov     rsi, rcx
0x18012a7a0  mov     rcx, [rcx+8]; hFile
0x18012a7a4  mov     ebp, r8d
0x18012a7a7  mov     qword ptr [rsp+58h+var_30], rbx
0x18012a7ac  mov     rdi, rdx
0x18012a7af  mov     qword ptr [rsp+58h+DistanceToMoveHigh], rbx
0x18012a7b4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18012a7b8  jnz     short loc_18012A7C4
0x18012a7ba  mov     eax, 800400CBh
0x18012a7bf  jmp     loc_18012A873
0x18012a7c4  mov     eax, ebp
0x18012a7c6  test    ebp, ebp
0x18012a7c8  jz      short loc_18012A828
0x18012a7ca  cmp     eax, 1
0x18012a7cd  jz      short loc_18012A7D9
0x18012a7cf  mov     eax, 80070057h
0x18012a7d4  jmp     loc_18012A873
0x18012a7d9  mov     r9d, 1; dwMoveMethod
0x18012a7df  lea     r8, [rsp+58h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18012a7e4  xor     edx, edx; lDistanceToMove
0x18012a7e6  call    cs:__imp_SetFilePointer
0x18012a7ec  mov     [rsp+58h+DistanceToMoveHigh], eax
0x18012a7f0  cmp     eax, 0FFFFFFFFh
0x18012a7f3  jnz     short loc_18012A813
0x18012a7f5  call    cs:__imp_GetLastError
0x18012a7fb  test    eax, eax
0x18012a7fd  jz      short loc_18012A813
0x18012a7ff  call    cs:__imp_GetLastError
0x18012a805  test    eax, eax
0x18012a807  jle     short loc_18012A873
0x18012a809  movzx   eax, ax
0x18012a80c  or      eax, 80070000h
0x18012a811  jmp     short loc_18012A873
0x18012a813  mov     rcx, qword ptr [rsp+58h+DistanceToMoveHigh]
0x18012a818  add     rcx, rdi
0x18012a81b  cmp     rcx, [rsi+10h]
0x18012a81f  jle     short loc_18012A835
0x18012a821  mov     eax, 800400CCh
0x18012a826  jmp     short loc_18012A873
0x18012a828  cmp     rdi, [rsi+10h]
0x18012a82c  jle     short loc_18012A835
0x18012a82e  mov     eax, 800400CCh
0x18012a833  jmp     short loc_18012A873
0x18012a835  mov     rcx, [rsi+8]; hFile
0x18012a839  lea     r8, [rsp+58h+var_30+4]; lpDistanceToMoveHigh
0x18012a83e  mov     r9d, ebp; dwMoveMethod
0x18012a841  mov     qword ptr [rsp+58h+var_30], rdi
0x18012a846  mov     edx, edi; lDistanceToMove
0x18012a848  call    cs:__imp_SetFilePointer
0x18012a84e  cmp     eax, 0FFFFFFFFh
0x18012a851  jnz     short loc_18012A871
0x18012a853  call    cs:__imp_GetLastError
0x18012a859  test    eax, eax
0x18012a85b  jz      short loc_18012A871
0x18012a85d  call    cs:__imp_GetLastError
0x18012a863  test    eax, eax
0x18012a865  jle     short loc_18012A86F
0x18012a867  movzx   eax, ax
0x18012a86a  or      eax, 80070000h
0x18012a86f  mov     ebx, eax
0x18012a871  mov     eax, ebx
0x18012a873  mov     rcx, [rsp+58h+var_28]
0x18012a878  xor     rcx, rsp; StackCookie
0x18012a87b  call    __security_check_cookie
0x18012a880  mov     rbx, [rsp+58h+arg_18]
0x18012a885  add     rsp, 40h
0x18012a889  pop     rdi
0x18012a88a  pop     rsi
0x18012a88b  pop     rbp
0x18012a88c  retn
```
