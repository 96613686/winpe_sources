# I_UrlCacheWriteCryptBlobArray2

- ea: `0x18000b4a4`
- end: `0x18000b71a`
- name: `I_UrlCacheWriteCryptBlobArray2`
- size: `630`
- prototype: `__int64 __fastcall(_WORD *lpBuffer, HANDLE hFile, HANDLE, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004c90`

## callees

- `0x18000b4a4`
- `0x18000e2f0`
- `0x18000ec40`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b55f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b55f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000b58d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000b5dd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000b60f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000b645`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000b669`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000b58d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000b5dd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000b60f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000b645`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000b669`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000b624`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000b6ad`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000b624`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000b6ad`

## pseudocode

```c
__int64 __fastcall I_UrlCacheWriteCryptBlobArray2(
        _WORD *lpBuffer,
        HANDLE hFile,
        HANDLE a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  unsigned int v7; // edi
  _WORD *v10; // r12
  __int64 v12; // xmm0_8
  __int64 v13; // rbx
  __int64 v14; // rax
  unsigned int v15; // ebx
  _WORD *v17; // rcx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-91h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+34h] [rbp-8Dh] BYREF
  _WORD *v20; // [rsp+38h] [rbp-89h]
  _DWORD Buffer[3]; // [rsp+40h] [rbp-81h] BYREF
  DWORD v22; // [rsp+4Ch] [rbp-75h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-71h] BYREF
  int v24; // [rsp+58h] [rbp-69h]
  int v25; // [rsp+80h] [rbp-41h]
  __int64 v26; // [rsp+84h] [rbp-3Dh]
  int v27; // [rsp+8Ch] [rbp-35h]
  int v28; // [rsp+90h] [rbp-31h]
  __int16 v29; // [rsp+94h] [rbp-2Dh]
  __int16 v30; // [rsp+96h] [rbp-2Bh]
  __int64 v31; // [rsp+98h] [rbp-29h]
  int v32; // [rsp+A0h] [rbp-21h]
  DWORD v33; // [rsp+A4h] [rbp-1Dh]
  int v34; // [rsp+A8h] [rbp-19h]

  v7 = 0;
  v20 = lpBuffer;
  v10 = lpBuffer;
  NumberOfBytesWritten = 0;
  memset_0(Buffer, 0, 0x70u);
  Buffer[0] = 112;
  Buffer[1] = 537002241;
  v24 = 40;
  if ( a5 )
  {
    v12 = *(_QWORD *)(a5 + 4);
    v25 = *(_DWORD *)a5;
    v27 = *(_DWORD *)(a5 + 12);
    v26 = v12;
  }
  else
  {
    v25 = 16;
  }
  if ( a3 )
    Buffer[2] = *(_DWORD *)a4;
  v13 = -1;
  if ( v10 )
  {
    v14 = -1;
    do
      ++v14;
    while ( v10[v14] );
  }
  else
  {
    LODWORD(v14) = 0;
  }
  v22 = 2 * v14 + 2;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v28 = 32;
  if ( a7 )
  {
    v17 = *(_WORD **)(a7 + 24);
    v29 = *(_WORD *)(a7 + 4);
    v30 = *(_WORD *)(a7 + 6);
    v31 = *(_QWORD *)(a7 + 8);
    v32 = *(_DWORD *)(a7 + 16);
    v34 = *(_DWORD *)(a7 + 32);
    if ( v17 )
    {
      if ( *v17 )
      {
        do
          ++v13;
        while ( v17[v13] );
        v33 = 2 * v13 + 2;
      }
    }
  }
  if ( !WriteFile(hFile, Buffer, 0x70u, &NumberOfBytesWritten, 0) )
    return 0;
  v15 = 1;
  if ( a3 )
  {
    while ( v7 < *(_DWORD *)a4 )
    {
      nNumberOfBytesToWrite = *(_DWORD *)(*(_QWORD *)(a4 + 8) + 16LL * v7);
      if ( !WriteFile(hFile, &nNumberOfBytesToWrite, 4u, &NumberOfBytesWritten, 0)
        || nNumberOfBytesToWrite
        && !WriteFile(
              a3,
              *(LPCVOID *)(*(_QWORD *)(a4 + 8) + 16LL * v7 + 8),
              nNumberOfBytesToWrite,
              &NumberOfBytesWritten,
              0) )
      {
        return 0;
      }
      ++v7;
    }
    SetEndOfFile(a3);
    v10 = v20;
  }
  if ( WriteFile(hFile, v10, v22, &NumberOfBytesWritten, 0)
    && (!v33 || WriteFile(hFile, *(LPCVOID *)(a7 + 24), v33, &NumberOfBytesWritten, 0)) )
  {
    SetEndOfFile(hFile);
  }
  else
  {
    return 0;
  }
  return v15;
}

```

## disassembly

```asm
0x18000b4a4  push    rbp
0x18000b4a6  push    rbx
0x18000b4a7  push    rsi
0x18000b4a8  push    rdi
0x18000b4a9  push    r12
0x18000b4ab  push    r13
0x18000b4ad  push    r14
0x18000b4af  push    r15
0x18000b4b1  lea     rbp, [rsp-7]
0x18000b4b6  sub     rsp, 0C8h
0x18000b4bd  mov     rax, cs:__security_cookie
0x18000b4c4  xor     rax, rsp
0x18000b4c7  mov     [rbp+3Fh+var_50], rax
0x18000b4cb  mov     rbx, [rbp+3Fh+arg_20]
0x18000b4cf  xor     edi, edi
0x18000b4d1  mov     rsi, [rbp+3Fh+arg_30]
0x18000b4d5  mov     r15, r8
0x18000b4d8  mov     r14, rdx
0x18000b4db  mov     [rsp+100h+var_C8], rcx
0x18000b4e0  mov     r12, rcx
0x18000b4e3  mov     [rsp+100h+NumberOfBytesWritten], edi
0x18000b4e7  lea     r8d, [rdi+70h]; Size
0x18000b4eb  xor     edx, edx; Val
0x18000b4ed  lea     rcx, [rsp+100h+Buffer]; void *
0x18000b4f2  mov     r13, r9
0x18000b4f5  call    memset_0
0x18000b4fa  mov     [rsp+100h+Buffer], 70h ; 'p'
0x18000b502  mov     [rbp+3Fh+var_BC], 20020101h
0x18000b509  mov     [rbp+3Fh+var_A8], 28h ; '('
0x18000b510  test    rbx, rbx
0x18000b513  jz      loc_18000B697
0x18000b519  mov     eax, [rbx]
0x18000b51b  movsd   xmm0, qword ptr [rbx+4]
0x18000b520  mov     [rbp+3Fh+var_80], eax
0x18000b523  mov     eax, [rbx+0Ch]
0x18000b526  mov     [rbp+3Fh+var_74], eax
0x18000b529  movsd   [rbp+3Fh+var_7C], xmm0
0x18000b52e  test    r15, r15
0x18000b531  jnz     loc_18000B70E
0x18000b537  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000b53b  test    r12, r12
0x18000b53e  jz      loc_18000B6A3
0x18000b544  mov     rax, rbx
0x18000b547  inc     rax
0x18000b54a  cmp     [r12+rax*2], di
0x18000b54f  jnz     short loc_18000B547
0x18000b551  lea     eax, ds:2[rax*2]
0x18000b558  lea     rcx, [rbp+3Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000b55c  mov     [rbp+3Fh+var_B4], eax
0x18000b55f  call    cs:__imp_GetSystemTimeAsFileTime
0x18000b565  mov     [rbp+3Fh+var_70], 20h ; ' '
0x18000b56c  test    rsi, rsi
0x18000b56f  jnz     loc_18000B6BC
0x18000b575  lea     r9, [rsp+100h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000b57a  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x18000b57f  mov     r8d, 70h ; 'p'; nNumberOfBytesToWrite
0x18000b585  lea     rdx, [rsp+100h+Buffer]; lpBuffer
0x18000b58a  mov     rcx, r14; hFile
0x18000b58d  call    cs:__imp_WriteFile
0x18000b593  test    eax, eax
0x18000b595  jz      loc_18000B673
0x18000b59b  mov     ebx, 1
0x18000b5a0  test    r15, r15
0x18000b5a3  jz      loc_18000B631
0x18000b5a9  cmp     edi, [r13+0]
0x18000b5ad  jnb     short loc_18000B621
0x18000b5af  mov     rax, [r13+8]
0x18000b5b3  lea     r9, [rsp+100h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000b5b8  mov     r12d, edi
0x18000b5bb  lea     rdx, [rsp+100h+nNumberOfBytesToWrite]; lpBuffer
0x18000b5c0  add     r12, r12
0x18000b5c3  mov     [rsp+100h+lpOverlapped], 0; lpOverlapped
0x18000b5cc  mov     r8d, 4; nNumberOfBytesToWrite
0x18000b5d2  mov     ecx, [rax+r12*8]
0x18000b5d6  mov     [rsp+100h+nNumberOfBytesToWrite], ecx
0x18000b5da  mov     rcx, r14; hFile
0x18000b5dd  call    cs:__imp_WriteFile
0x18000b5e3  test    eax, eax
0x18000b5e5  jz      short loc_18000B61D
0x18000b5e7  mov     r8d, [rsp+100h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18000b5ec  test    r8d, r8d
0x18000b5ef  jz      loc_18000B6B5
0x18000b5f5  mov     rdx, [r13+8]
0x18000b5f9  lea     r9, [rsp+100h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000b5fe  mov     rcx, r15; hFile
0x18000b601  mov     [rsp+100h+lpOverlapped], 0; lpOverlapped
0x18000b60a  mov     rdx, [rdx+r12*8+8]; lpBuffer
0x18000b60f  call    cs:__imp_WriteFile
0x18000b615  test    eax, eax
0x18000b617  jnz     loc_18000B6B5
0x18000b61d  xor     edi, edi
0x18000b61f  jmp     short loc_18000B673
0x18000b621  mov     rcx, r15; hFile
0x18000b624  call    cs:__imp_SetEndOfFile
0x18000b62a  mov     r12, [rsp+100h+var_C8]
0x18000b62f  xor     edi, edi
0x18000b631  mov     r8d, [rbp+3Fh+var_B4]; nNumberOfBytesToWrite
0x18000b635  lea     r9, [rsp+100h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000b63a  mov     rdx, r12; lpBuffer
0x18000b63d  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x18000b642  mov     rcx, r14; hFile
0x18000b645  call    cs:__imp_WriteFile
0x18000b64b  test    eax, eax
0x18000b64d  jz      short loc_18000B673
0x18000b64f  mov     r8d, [rbp+3Fh+var_5C]; nNumberOfBytesToWrite
0x18000b653  test    r8d, r8d
0x18000b656  jz      short loc_18000B6AA
0x18000b658  mov     rdx, [rsi+18h]; lpBuffer
0x18000b65c  lea     r9, [rsp+100h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000b661  mov     rcx, r14; hFile
0x18000b664  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x18000b669  call    cs:__imp_WriteFile
0x18000b66f  test    eax, eax
0x18000b671  jnz     short loc_18000B6AA
0x18000b673  mov     ebx, edi
0x18000b675  mov     eax, ebx
0x18000b677  mov     rcx, [rbp+3Fh+var_50]
0x18000b67b  xor     rcx, rsp; StackCookie
0x18000b67e  call    __security_check_cookie
0x18000b683  add     rsp, 0C8h
0x18000b68a  pop     r15
0x18000b68c  pop     r14
0x18000b68e  pop     r13
0x18000b690  pop     r12
0x18000b692  pop     rdi
0x18000b693  pop     rsi
0x18000b694  pop     rbx
0x18000b695  pop     rbp
0x18000b696  retn
0x18000b697  mov     [rbp+3Fh+var_80], 10h
0x18000b69e  jmp     loc_18000B52E
0x18000b6a3  mov     eax, edi
0x18000b6a5  jmp     loc_18000B551
0x18000b6aa  mov     rcx, r14; hFile
0x18000b6ad  call    cs:__imp_SetEndOfFile
0x18000b6b3  jmp     short loc_18000B675
0x18000b6b5  add     edi, ebx
0x18000b6b7  jmp     loc_18000B5A9
0x18000b6bc  movzx   eax, word ptr [rsi+4]
0x18000b6c0  mov     rcx, [rsi+18h]
0x18000b6c4  mov     [rbp+3Fh+var_6C], ax
0x18000b6c8  movzx   eax, word ptr [rsi+6]
0x18000b6cc  mov     [rbp+3Fh+var_6A], ax
0x18000b6d0  mov     rax, [rsi+8]
0x18000b6d4  mov     [rbp+3Fh+var_68], rax
0x18000b6d8  mov     eax, [rsi+10h]
0x18000b6db  mov     [rbp+3Fh+var_60], eax
0x18000b6de  mov     eax, [rsi+20h]
0x18000b6e1  mov     [rbp+3Fh+var_58], eax
0x18000b6e4  test    rcx, rcx
0x18000b6e7  jz      loc_18000B575
0x18000b6ed  cmp     di, [rcx]
0x18000b6f0  jz      loc_18000B575
0x18000b6f6  inc     rbx
0x18000b6f9  cmp     [rcx+rbx*2], di
0x18000b6fd  jnz     short loc_18000B6F6
0x18000b6ff  lea     eax, ds:2[rbx*2]
0x18000b706  mov     [rbp+3Fh+var_5C], eax
0x18000b709  jmp     loc_18000B575
0x18000b70e  mov     eax, [r13+0]
0x18000b712  mov     [rbp+3Fh+var_B8], eax
0x18000b715  jmp     loc_18000B537
```
