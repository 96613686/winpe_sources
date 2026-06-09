# CFile::_InvokeFileMethod__CFile::Read_::_2_::_lambda_1___

- ea: `0x1800a6d78`
- end: `0x1800a6e50`
- name: `CFile::_InvokeFileMethod__CFile::Read_::_2_::_lambda_1___`
- size: `216`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800c1444`
- `0x1800effa8`

## callees

- `0x1800a6d78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6dcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6df8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6dcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6df8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a6dc2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a6dee`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a6dc2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a6dee`

## pseudocode

```c
__int64 __fastcall CFile::_InvokeFileMethod__CFile::Read_::_2_::_lambda_1___(_QWORD *a1, __int64 a2)
{
  unsigned int v3; // ebx
  struct _OVERLAPPED *lpOverlapped; // r10
  DWORD *v5; // r9
  DWORD v6; // r8d
  void *v7; // rcx
  void *v8; // rdx
  signed int LastError; // eax
  signed int v10; // eax
  unsigned int v11; // ecx

  if ( *a1 == -1 || (v3 = 0, !*a1) )
  {
    v3 = -2147024890;
  }
  else
  {
    lpOverlapped = *(struct _OVERLAPPED **)(a2 + 32);
    v5 = *(DWORD **)(a2 + 24);
    v6 = *(_DWORD *)(a2 + 16);
    v7 = **(void ***)a2;
    v8 = *(void **)(a2 + 8);
    if ( lpOverlapped )
    {
      if ( !ReadFile(v7, v8, v6, v5, lpOverlapped) )
      {
        LastError = GetLastError();
        if ( LastError != 997 )
        {
          v3 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v3 = LastError;
        }
      }
    }
    else if ( !ReadFile(v7, v8, v6, v5, 0) )
    {
      v10 = GetLastError();
      if ( v10 )
      {
        v11 = (unsigned __int16)v10 | 0x80070000;
        if ( v10 <= 0 )
          v11 = v10;
      }
      else
      {
        v11 = -2147467259;
      }
      v3 = v11;
    }
  }
  if ( v3 == -2147024890 )
    *a1 = -1;
  return v3;
}

```

## disassembly

```asm
0x1800a6d78  mov     [rsp+arg_8], rbx
0x1800a6d7d  mov     [rsp+arg_0], rcx
0x1800a6d82  push    rdi
0x1800a6d83  sub     rsp, 40h
0x1800a6d87  mov     rdi, rcx
0x1800a6d8a  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1800a6d8e  jz      loc_1800A6E2F
0x1800a6d94  xor     ebx, ebx
0x1800a6d96  cmp     [rcx], rbx
0x1800a6d99  jz      loc_1800A6E2F
0x1800a6d9f  mov     r10, [rdx+20h]
0x1800a6da3  mov     r9, [rdx+18h]; lpNumberOfBytesRead
0x1800a6da7  mov     r8d, [rdx+10h]; nNumberOfBytesToRead
0x1800a6dab  mov     r11, [rdx+8]
0x1800a6daf  mov     rax, [rdx]
0x1800a6db2  mov     rcx, [rax]; hFile
0x1800a6db5  mov     rdx, r11; lpBuffer
0x1800a6db8  test    r10, r10
0x1800a6dbb  jz      short loc_1800A6DE9
0x1800a6dbd  mov     [rsp+48h+lpOverlapped], r10; lpOverlapped
0x1800a6dc2  call    cs:__imp_ReadFile
0x1800a6dc8  test    eax, eax
0x1800a6dca  jnz     short loc_1800A6E19
0x1800a6dcc  call    cs:__imp_GetLastError
0x1800a6dd2  cmp     eax, 3E5h
0x1800a6dd7  jz      short loc_1800A6E19
0x1800a6dd9  movzx   ebx, ax
0x1800a6ddc  or      ebx, 80070000h
0x1800a6de2  test    eax, eax
0x1800a6de4  cmovle  ebx, eax
0x1800a6de7  jmp     short loc_1800A6E19
0x1800a6de9  mov     [rsp+48h+lpOverlapped], rbx; lpOverlapped
0x1800a6dee  call    cs:__imp_ReadFile
0x1800a6df4  test    eax, eax
0x1800a6df6  jnz     short loc_1800A6E19
0x1800a6df8  call    cs:__imp_GetLastError
0x1800a6dfe  test    eax, eax
0x1800a6e00  jz      short loc_1800A6E12
0x1800a6e02  movzx   ecx, ax
0x1800a6e05  or      ecx, 80070000h
0x1800a6e0b  test    eax, eax
0x1800a6e0d  cmovle  ecx, eax
0x1800a6e10  jmp     short loc_1800A6E17
0x1800a6e12  mov     ecx, 80004005h
0x1800a6e17  mov     ebx, ecx
0x1800a6e19  mov     [rsp+48h+var_18], ebx
0x1800a6e1d  jmp     short loc_1800A6E34
0x1800a6e1f  mov     ebx, 80070006h
0x1800a6e24  mov     [rsp+48h+var_18], ebx
0x1800a6e28  mov     rdi, [rsp+48h+arg_0]
0x1800a6e2d  jmp     short loc_1800A6E34
0x1800a6e2f  mov     ebx, 80070006h
0x1800a6e34  cmp     ebx, 80070006h
0x1800a6e3a  jnz     short loc_1800A6E43
0x1800a6e3c  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800a6e43  mov     eax, ebx
0x1800a6e45  mov     rbx, [rsp+48h+arg_8]
0x1800a6e4a  add     rsp, 40h
0x1800a6e4e  pop     rdi
0x1800a6e4f  retn
0x180113600  push    rbp
0x180113602  sub     rsp, 30h
0x180113606  mov     rbp, rdx
0x180113609  mov     rax, [rcx]
0x18011360c  xor     ecx, ecx
0x18011360e  cmp     dword ptr [rax], 0C0000008h
0x180113614  setz    cl
0x180113617  mov     eax, ecx
0x180113619  add     rsp, 30h
0x18011361d  pop     rbp
0x18011361e  retn
```
