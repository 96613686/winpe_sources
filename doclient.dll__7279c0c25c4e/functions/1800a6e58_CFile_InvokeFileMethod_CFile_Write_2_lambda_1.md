# CFile::_InvokeFileMethod__CFile::Write_::_2_::_lambda_1___

- ea: `0x1800a6e58`
- end: `0x1800a6f30`
- name: `CFile::_InvokeFileMethod__CFile::Write_::_2_::_lambda_1___`
- size: `216`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800bb3c0`
- `0x1800c170c`
- `0x1800f029c`

## callees

- `0x1800a6e58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6eac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6ed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6eac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6ed8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a6ea2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a6ece`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a6ea2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a6ece`

## pseudocode

```c
__int64 __fastcall CFile::_InvokeFileMethod__CFile::Write_::_2_::_lambda_1___(_QWORD *a1, __int64 a2)
{
  unsigned int v3; // ebx
  struct _OVERLAPPED *lpOverlapped; // r10
  DWORD *v5; // r9
  DWORD v6; // r8d
  void *v7; // rcx
  const void *v8; // rdx
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
    v8 = *(const void **)(a2 + 8);
    if ( lpOverlapped )
    {
      if ( !WriteFile(v7, v8, v6, v5, lpOverlapped) )
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
    else if ( !WriteFile(v7, v8, v6, v5, 0) )
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
0x1800a6e58  mov     [rsp+arg_8], rbx
0x1800a6e5d  mov     [rsp+arg_0], rcx
0x1800a6e62  push    rdi
0x1800a6e63  sub     rsp, 40h
0x1800a6e67  mov     rdi, rcx
0x1800a6e6a  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1800a6e6e  jz      loc_1800A6F0F
0x1800a6e74  xor     ebx, ebx
0x1800a6e76  cmp     [rcx], rbx
0x1800a6e79  jz      loc_1800A6F0F
0x1800a6e7f  mov     r10, [rdx+20h]
0x1800a6e83  mov     r9, [rdx+18h]; lpNumberOfBytesWritten
0x1800a6e87  mov     r8d, [rdx+10h]; nNumberOfBytesToWrite
0x1800a6e8b  mov     r11, [rdx+8]
0x1800a6e8f  mov     rax, [rdx]
0x1800a6e92  mov     rcx, [rax]; hFile
0x1800a6e95  mov     rdx, r11; lpBuffer
0x1800a6e98  test    r10, r10
0x1800a6e9b  jz      short loc_1800A6EC9
0x1800a6e9d  mov     [rsp+48h+lpOverlapped], r10; lpOverlapped
0x1800a6ea2  call    cs:__imp_WriteFile
0x1800a6ea8  test    eax, eax
0x1800a6eaa  jnz     short loc_1800A6EF9
0x1800a6eac  call    cs:__imp_GetLastError
0x1800a6eb2  cmp     eax, 3E5h
0x1800a6eb7  jz      short loc_1800A6EF9
0x1800a6eb9  movzx   ebx, ax
0x1800a6ebc  or      ebx, 80070000h
0x1800a6ec2  test    eax, eax
0x1800a6ec4  cmovle  ebx, eax
0x1800a6ec7  jmp     short loc_1800A6EF9
0x1800a6ec9  mov     [rsp+48h+lpOverlapped], rbx; lpOverlapped
0x1800a6ece  call    cs:__imp_WriteFile
0x1800a6ed4  test    eax, eax
0x1800a6ed6  jnz     short loc_1800A6EF9
0x1800a6ed8  call    cs:__imp_GetLastError
0x1800a6ede  test    eax, eax
0x1800a6ee0  jz      short loc_1800A6EF2
0x1800a6ee2  movzx   ecx, ax
0x1800a6ee5  or      ecx, 80070000h
0x1800a6eeb  test    eax, eax
0x1800a6eed  cmovle  ecx, eax
0x1800a6ef0  jmp     short loc_1800A6EF7
0x1800a6ef2  mov     ecx, 80004005h
0x1800a6ef7  mov     ebx, ecx
0x1800a6ef9  mov     [rsp+48h+var_18], ebx
0x1800a6efd  jmp     short loc_1800A6F14
0x1800a6eff  mov     ebx, 80070006h
0x1800a6f04  mov     [rsp+48h+var_18], ebx
0x1800a6f08  mov     rdi, [rsp+48h+arg_0]
0x1800a6f0d  jmp     short loc_1800A6F14
0x1800a6f0f  mov     ebx, 80070006h
0x1800a6f14  cmp     ebx, 80070006h
0x1800a6f1a  jnz     short loc_1800A6F23
0x1800a6f1c  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800a6f23  mov     eax, ebx
0x1800a6f25  mov     rbx, [rsp+48h+arg_8]
0x1800a6f2a  add     rsp, 40h
0x1800a6f2e  pop     rdi
0x1800a6f2f  retn
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
