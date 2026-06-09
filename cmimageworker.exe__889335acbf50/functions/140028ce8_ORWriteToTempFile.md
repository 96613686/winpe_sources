# ORWriteToTempFile

- ea: `0x140028ce8`
- end: `0x140028dc9`
- name: `ORWriteToTempFile`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x140023340`
- `0x140023884`

## callees

- `0x14002727c`
- `0x140028ce8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028d74`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140028d64`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140028d64`

## pseudocode

```c
__int64 __fastcall ORWriteToTempFile(__int64 a1, void *a2)
{
  DWORD LastError; // edi
  _DWORD *v5; // rcx
  unsigned int v6; // r15d
  char v7; // bp
  __int64 *v8; // rsi
  DWORD v9; // r14d
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  if ( a1 )
  {
    if ( *(_QWORD *)(a1 + 16) )
      ORUpdateBaseBlock();
    v5 = *(_DWORD **)(a1 + 16);
    if ( v5[10] == -4096 )
    {
      return 0;
    }
    else
    {
      v6 = 0;
      v7 = 0;
      v8 = 0;
      while ( 1 )
      {
        if ( v7 )
        {
          v9 = *((_DWORD *)v8 + 9);
          v5 = (_DWORD *)v8[5];
        }
        else
        {
          v9 = 4096;
        }
        LastError = 0;
        if ( !WriteFile(a2, v5, v9, &NumberOfBytesWritten, 0) )
          LastError = GetLastError();
        if ( LastError )
          break;
        if ( v7 )
        {
          v8 = (__int64 *)*v8;
        }
        else
        {
          v8 = *(__int64 **)(a1 + 80);
          v7 = 1;
        }
        v5 = *(_DWORD **)(a1 + 16);
        v6 += v9;
        if ( v6 >= v5[10] + 4096 )
          return 0;
      }
    }
  }
  else
  {
    return 87;
  }
  return LastError;
}

```

## disassembly

```asm
0x140028ce8  mov     [rsp+arg_8], rbx
0x140028ced  mov     [rsp+arg_10], rbp
0x140028cf2  push    rsi
0x140028cf3  push    rdi
0x140028cf4  push    r12
0x140028cf6  push    r14
0x140028cf8  push    r15
0x140028cfa  sub     rsp, 30h
0x140028cfe  mov     [rsp+58h+NumberOfBytesWritten], 0
0x140028d06  mov     r12, rdx
0x140028d09  mov     rbx, rcx
0x140028d0c  test    rcx, rcx
0x140028d0f  jnz     short loc_140028D19
0x140028d11  lea     edi, [rcx+57h]
0x140028d14  jmp     loc_140028DAF
0x140028d19  cmp     qword ptr [rcx+10h], 0
0x140028d1e  jz      short loc_140028D25
0x140028d20  call    ORUpdateBaseBlock
0x140028d25  mov     rcx, [rbx+10h]
0x140028d29  mov     edx, 1000h
0x140028d2e  mov     eax, [rcx+28h]
0x140028d31  add     eax, edx
0x140028d33  jz      short loc_140028DAD
0x140028d35  xor     r15d, r15d
0x140028d38  xor     bpl, bpl
0x140028d3b  xor     esi, esi
0x140028d3d  test    bpl, bpl
0x140028d40  jnz     short loc_140028D47
0x140028d42  mov     r14d, edx
0x140028d45  jmp     short loc_140028D4F
0x140028d47  mov     r14d, [rsi+24h]
0x140028d4b  mov     rcx, [rsi+28h]
0x140028d4f  mov     rdx, rcx; lpBuffer
0x140028d52  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140028d57  xor     edi, edi
0x140028d59  mov     rcx, r12; hFile
0x140028d5c  mov     r8d, r14d; nNumberOfBytesToWrite
0x140028d5f  mov     [rsp+58h+lpOverlapped], rdi; lpOverlapped
0x140028d64  call    cs:__imp_WriteFile
0x140028d6b  nop     dword ptr [rax+rax+00h]
0x140028d70  test    eax, eax
0x140028d72  jnz     short loc_140028D82
0x140028d74  call    cs:__imp_GetLastError
0x140028d7b  nop     dword ptr [rax+rax+00h]
0x140028d80  mov     edi, eax
0x140028d82  test    edi, edi
0x140028d84  jnz     short loc_140028DAF
0x140028d86  test    bpl, bpl
0x140028d89  jz      short loc_140028D90
0x140028d8b  mov     rsi, [rsi]
0x140028d8e  jmp     short loc_140028D97
0x140028d90  mov     rsi, [rbx+50h]
0x140028d94  mov     bpl, 1
0x140028d97  mov     rcx, [rbx+10h]
0x140028d9b  mov     edx, 1000h
0x140028da0  add     r15d, r14d
0x140028da3  mov     eax, [rcx+28h]
0x140028da6  add     eax, edx
0x140028da8  cmp     r15d, eax
0x140028dab  jb      short loc_140028D3D
0x140028dad  xor     edi, edi
0x140028daf  mov     rbx, [rsp+58h+arg_8]
0x140028db4  mov     eax, edi
0x140028db6  mov     rbp, [rsp+58h+arg_10]
0x140028dbb  add     rsp, 30h
0x140028dbf  pop     r15
0x140028dc1  pop     r14
0x140028dc3  pop     r12
0x140028dc5  pop     rdi
0x140028dc6  pop     rsi
0x140028dc7  retn
```
