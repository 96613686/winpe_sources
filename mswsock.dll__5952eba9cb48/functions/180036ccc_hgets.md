# hgets

- ea: `0x180036ccc`
- end: `0x180036e07`
- name: `hgets`
- size: `315`
- prototype: `__int64 __fastcall(LPVOID lpBuffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001ad4`

## callees

- `0x180036ccc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180036d26`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180036d9a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180036d26`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180036d9a`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180036d01`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180036de2`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180036d01`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180036de2`

## pseudocode

```c
char *__fastcall hgets(char *lpBuffer, __int64 a2, void *a3)
{
  DWORD v5; // r8d
  __int64 v6; // rdi
  LONGLONG v7; // rax
  __int64 v8; // r14
  bool v9; // zf
  char *v10; // rsi
  BOOL v11; // eax
  union _LARGE_INTEGER v12; // rdx
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp+38h] BYREF
  union _LARGE_INTEGER NewFilePointer; // [rsp+78h] [rbp+48h] BYREF

  NumberOfBytesRead = 0;
  NewFilePointer.QuadPart = 0;
  SetFilePointerEx(a3, 0, &NewFilePointer, 1u);
  if ( !ReadFile(a3, lpBuffer, 0x1FFu, &NumberOfBytesRead, 0) )
    return 0;
  v5 = NumberOfBytesRead;
  if ( !NumberOfBytesRead )
    return 0;
  v6 = 0;
  while ( 1 )
  {
    v7 = NewFilePointer.QuadPart + 1;
    v8 = (unsigned int)v6;
    v9 = lpBuffer[v6] == 13;
    ++NewFilePointer.QuadPart;
    if ( v9 )
    {
      lpBuffer[v6] = 10;
      v10 = &lpBuffer[(unsigned int)(v6 + 1)];
      if ( (int)v6 + 1 >= v5 )
      {
        v11 = ReadFile(a3, &lpBuffer[(unsigned int)(v6 + 1)], 1u, &NumberOfBytesRead, 0);
        v5 = NumberOfBytesRead;
        if ( v11 && NumberOfBytesRead == 1 && *v10 == 10 )
          ++NewFilePointer.QuadPart;
      }
      else if ( *v10 == 10 )
      {
        NewFilePointer.QuadPart = v7 + 1;
      }
    }
    v6 = (unsigned int)(v6 + 1);
    if ( lpBuffer[v8] == 10 )
      break;
    if ( (unsigned int)v6 >= v5 )
    {
      lpBuffer[v6] = 0;
      return lpBuffer;
    }
  }
  v12 = NewFilePointer;
  lpBuffer[v6] = 0;
  SetFilePointerEx(a3, v12, 0, 0);
  return lpBuffer;
}

```

## disassembly

```asm
0x180036ccc  mov     [rsp-28h+arg_0], rbx
0x180036cd1  mov     [rsp-28h+NumberOfBytesRead], edx
0x180036cd5  push    rbp
0x180036cd6  push    rsi
0x180036cd7  push    rdi
0x180036cd8  push    r14
0x180036cda  push    r15
0x180036cdc  mov     rbp, rsp
0x180036cdf  sub     rsp, 30h
0x180036ce3  xor     edx, edx; liDistanceToMove
0x180036ce5  mov     [rbp+NumberOfBytesRead], 0
0x180036cec  mov     r15, r8
0x180036cef  mov     qword ptr [rbp+NewFilePointer], rdx
0x180036cf3  mov     rbx, rcx
0x180036cf6  lea     r8, [rbp+NewFilePointer]; lpNewFilePointer
0x180036cfa  mov     rcx, r15; hFile
0x180036cfd  lea     r9d, [rdx+1]; dwMoveMethod
0x180036d01  call    cs:__imp_SetFilePointerEx
0x180036d08  nop     dword ptr [rax+rax+00h]
0x180036d0d  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180036d11  mov     [rsp+30h+lpOverlapped], 0; lpOverlapped
0x180036d1a  mov     r8d, 1FFh; nNumberOfBytesToRead
0x180036d20  mov     rdx, rbx; lpBuffer
0x180036d23  mov     rcx, r15; hFile
0x180036d26  call    cs:__imp_ReadFile
0x180036d2d  nop     dword ptr [rax+rax+00h]
0x180036d32  test    eax, eax
0x180036d34  jz      loc_180036DF3
0x180036d3a  mov     r8d, [rbp+NumberOfBytesRead]
0x180036d3e  test    r8d, r8d
0x180036d41  jz      loc_180036DF3
0x180036d47  xor     edi, edi
0x180036d49  test    r8d, r8d
0x180036d4c  jz      short loc_180036DCB
0x180036d4e  mov     rax, qword ptr [rbp+NewFilePointer]
0x180036d52  inc     rax
0x180036d55  mov     r14d, edi
0x180036d58  cmp     byte ptr [rdi+rbx], 0Dh
0x180036d5c  mov     qword ptr [rbp+NewFilePointer], rax
0x180036d60  jnz     short loc_180036DBD
0x180036d62  lea     edx, [rdi+1]
0x180036d65  mov     byte ptr [rdi+rbx], 0Ah
0x180036d69  mov     esi, edx
0x180036d6b  add     rsi, rbx
0x180036d6e  cmp     edx, r8d
0x180036d71  jnb     short loc_180036D81
0x180036d73  cmp     byte ptr [rsi], 0Ah
0x180036d76  jnz     short loc_180036DBD
0x180036d78  inc     rax
0x180036d7b  mov     qword ptr [rbp+NewFilePointer], rax
0x180036d7f  jmp     short loc_180036DBD
0x180036d81  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180036d85  mov     [rsp+30h+lpOverlapped], 0; lpOverlapped
0x180036d8e  mov     r8d, 1; nNumberOfBytesToRead
0x180036d94  mov     rdx, rsi; lpBuffer
0x180036d97  mov     rcx, r15; hFile
0x180036d9a  call    cs:__imp_ReadFile
0x180036da1  nop     dword ptr [rax+rax+00h]
0x180036da6  mov     r8d, [rbp+NumberOfBytesRead]
0x180036daa  test    eax, eax
0x180036dac  jz      short loc_180036DBD
0x180036dae  cmp     r8d, 1
0x180036db2  jnz     short loc_180036DBD
0x180036db4  cmp     byte ptr [rsi], 0Ah
0x180036db7  jnz     short loc_180036DBD
0x180036db9  inc     qword ptr [rbp+NewFilePointer]
0x180036dbd  inc     edi
0x180036dbf  cmp     byte ptr [r14+rbx], 0Ah
0x180036dc4  jz      short loc_180036DD1
0x180036dc6  cmp     edi, r8d
0x180036dc9  jb      short loc_180036D4E
0x180036dcb  mov     byte ptr [rdi+rbx], 0
0x180036dcf  jmp     short loc_180036DEE
0x180036dd1  mov     rdx, qword ptr [rbp+NewFilePointer]; liDistanceToMove
0x180036dd5  xor     r9d, r9d; dwMoveMethod
0x180036dd8  xor     r8d, r8d; lpNewFilePointer
0x180036ddb  mov     byte ptr [rdi+rbx], 0
0x180036ddf  mov     rcx, r15; hFile
0x180036de2  call    cs:__imp_SetFilePointerEx
0x180036de9  nop     dword ptr [rax+rax+00h]
0x180036dee  mov     rax, rbx
0x180036df1  jmp     short loc_180036DF5
0x180036df3  xor     eax, eax
0x180036df5  mov     rbx, [rsp+30h+arg_0]
0x180036dfa  add     rsp, 30h
0x180036dfe  pop     r15
0x180036e00  pop     r14
0x180036e02  pop     rdi
0x180036e03  pop     rsi
0x180036e04  pop     rbp
0x180036e05  retn
```
