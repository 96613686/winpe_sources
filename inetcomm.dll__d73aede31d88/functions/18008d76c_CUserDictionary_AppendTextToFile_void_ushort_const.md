# CUserDictionary::AppendTextToFile(void *,ushort const *)

- ea: `0x18008d76c`
- end: `0x18008d89f`
- name: `?AppendTextToFile@CUserDictionary@@AEAAJPEAXPEBG@Z`
- size: `307`
- prototype: `int(CUserDictionary *__hidden this, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18008d588`

## callees

- `0x18000910c`
- `0x180036c80`
- `0x18008d76c`
- `0x1800cca00`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x18008d7bd`
- `KERNEL32!SetFilePointer` at `0x18008d862`
- `KERNEL32!SetFilePointer` at `0x18008d7bd`
- `KERNEL32!SetFilePointer` at `0x18008d862`
- `KERNEL32!WriteFile` at `0x18008d83e`
- `KERNEL32!WriteFile` at `0x18008d83e`
- `KERNEL32!SetEndOfFile` at `0x18008d86b`
- `KERNEL32!SetEndOfFile` at `0x18008d86b`

## pseudocode

```c
__int64 __fastcall CUserDictionary::AppendTextToFile(CUserDictionary *this, void *a2, const unsigned __int16 *a3)
{
  int v5; // ebx
  LONG v6; // esi
  int v7; // ebx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-D0h] BYREF
  LONG DistanceToMoveHigh; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int64 v11; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 Buffer[1032]; // [rsp+40h] [rbp-C0h] BYREF

  DistanceToMoveHigh = 0;
  v5 = -2147467259;
  v6 = SetFilePointer(a2, 0, &DistanceToMoveHigh, 2u);
  if ( v6 != -1 )
  {
    v5 = StringCchPrintfW(Buffer, 0x405u, L"%s\r\n", a3);
    if ( v5 >= 0 )
    {
      v11 = 0;
      v5 = StringCchLengthW(Buffer, 0x405u, &v11);
      if ( v5 >= 0 )
      {
        NumberOfBytesWritten = 0;
        v7 = 2 * v11;
        if ( WriteFile(a2, Buffer, 2 * v11, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == v7 )
        {
          return 0;
        }
        else
        {
          SetFilePointer(a2, v6, &DistanceToMoveHigh, 2u);
          SetEndOfFile(a2);
          return (unsigned int)-2147467259;
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18008d76c  mov     [rsp-8+arg_0], rbx
0x18008d771  mov     [rsp-8+arg_18], rsi
0x18008d776  push    rbp
0x18008d777  push    rdi
0x18008d778  push    r14
0x18008d77a  lea     rbp, [rsp-760h]
0x18008d782  sub     rsp, 860h
0x18008d789  mov     rax, cs:__security_cookie
0x18008d790  xor     rax, rsp
0x18008d793  mov     [rbp+770h+var_20], rax
0x18008d79a  mov     rdi, rdx
0x18008d79d  mov     [rsp+870h+DistanceToMoveHigh], 0
0x18008d7a5  mov     r14, r8
0x18008d7a8  mov     rcx, rdi; hFile
0x18008d7ab  mov     r9d, 2; dwMoveMethod
0x18008d7b1  lea     r8, [rsp+870h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18008d7b6  xor     edx, edx; lDistanceToMove
0x18008d7b8  mov     ebx, 80004005h
0x18008d7bd  call    cs:__imp_SetFilePointer
0x18008d7c3  mov     esi, eax
0x18008d7c5  cmp     eax, 0FFFFFFFFh
0x18008d7c8  jz      loc_18008D876
0x18008d7ce  mov     r9, r14
0x18008d7d1  lea     r8, aS; "%s\r\n"
0x18008d7d8  mov     r14d, 405h
0x18008d7de  lea     rcx, [rsp+870h+Buffer]; unsigned __int16 *
0x18008d7e3  mov     edx, r14d; unsigned __int64
0x18008d7e6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008d7eb  mov     ebx, eax
0x18008d7ed  test    eax, eax
0x18008d7ef  js      loc_18008D876
0x18008d7f5  lea     r8, [rsp+870h+var_838]; unsigned __int64 *
0x18008d7fa  mov     [rsp+870h+var_838], 0
0x18008d803  mov     edx, r14d; unsigned __int64
0x18008d806  lea     rcx, [rsp+870h+Buffer]; unsigned __int16 *
0x18008d80b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18008d810  mov     ebx, eax
0x18008d812  test    eax, eax
0x18008d814  js      short loc_18008D876
0x18008d816  mov     eax, dword ptr [rsp+870h+var_838]
0x18008d81a  lea     r9, [rsp+870h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008d81f  lea     rdx, [rsp+870h+Buffer]; lpBuffer
0x18008d824  mov     [rsp+870h+NumberOfBytesWritten], 0
0x18008d82c  mov     rcx, rdi; hFile
0x18008d82f  mov     [rsp+870h+lpOverlapped], 0; lpOverlapped
0x18008d838  lea     ebx, [rax+rax]
0x18008d83b  mov     r8d, ebx; nNumberOfBytesToWrite
0x18008d83e  call    cs:__imp_WriteFile
0x18008d844  test    eax, eax
0x18008d846  jz      short loc_18008D852
0x18008d848  cmp     [rsp+870h+NumberOfBytesWritten], ebx
0x18008d84c  jnz     short loc_18008D852
0x18008d84e  xor     ebx, ebx
0x18008d850  jmp     short loc_18008D876
0x18008d852  mov     r9d, 2; dwMoveMethod
0x18008d858  lea     r8, [rsp+870h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18008d85d  mov     edx, esi; lDistanceToMove
0x18008d85f  mov     rcx, rdi; hFile
0x18008d862  call    cs:__imp_SetFilePointer
0x18008d868  mov     rcx, rdi; hFile
0x18008d86b  call    cs:__imp_SetEndOfFile
0x18008d871  mov     ebx, 80004005h
0x18008d876  mov     eax, ebx
0x18008d878  mov     rcx, [rbp+770h+var_20]
0x18008d87f  xor     rcx, rsp; StackCookie
0x18008d882  call    __security_check_cookie
0x18008d887  lea     r11, [rsp+870h+var_10]
0x18008d88f  mov     rbx, [r11+20h]
0x18008d893  mov     rsi, [r11+38h]
0x18008d897  mov     rsp, r11
0x18008d89a  pop     r14
0x18008d89c  pop     rdi
0x18008d89d  pop     rbp
0x18008d89e  retn
```
