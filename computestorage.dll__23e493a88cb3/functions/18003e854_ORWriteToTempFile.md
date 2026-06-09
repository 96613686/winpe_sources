# ORWriteToTempFile

- ea: `0x18003e854`
- end: `0x18003e935`
- name: `ORWriteToTempFile`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x18003b52c`

## callees

- `0x1800390d0`
- `0x18003e854`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003e8d0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003e8d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e8e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e8e0`

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
0x18003e854  mov     [rsp+arg_8], rbx
0x18003e859  mov     [rsp+arg_10], rbp
0x18003e85e  push    rsi
0x18003e85f  push    rdi
0x18003e860  push    r12
0x18003e862  push    r14
0x18003e864  push    r15
0x18003e866  sub     rsp, 30h
0x18003e86a  mov     [rsp+58h+NumberOfBytesWritten], 0
0x18003e872  mov     r12, rdx
0x18003e875  mov     rbx, rcx
0x18003e878  test    rcx, rcx
0x18003e87b  jnz     short loc_18003E885
0x18003e87d  lea     edi, [rcx+57h]
0x18003e880  jmp     loc_18003E91B
0x18003e885  cmp     qword ptr [rcx+10h], 0
0x18003e88a  jz      short loc_18003E891
0x18003e88c  call    ORUpdateBaseBlock
0x18003e891  mov     rcx, [rbx+10h]
0x18003e895  mov     edx, 1000h
0x18003e89a  mov     eax, [rcx+28h]
0x18003e89d  add     eax, edx
0x18003e89f  jz      short loc_18003E919
0x18003e8a1  xor     r15d, r15d
0x18003e8a4  xor     bpl, bpl
0x18003e8a7  xor     esi, esi
0x18003e8a9  test    bpl, bpl
0x18003e8ac  jnz     short loc_18003E8B3
0x18003e8ae  mov     r14d, edx
0x18003e8b1  jmp     short loc_18003E8BB
0x18003e8b3  mov     r14d, [rsi+24h]
0x18003e8b7  mov     rcx, [rsi+28h]
0x18003e8bb  mov     rdx, rcx; lpBuffer
0x18003e8be  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003e8c3  xor     edi, edi
0x18003e8c5  mov     rcx, r12; hFile
0x18003e8c8  mov     r8d, r14d; nNumberOfBytesToWrite
0x18003e8cb  mov     [rsp+58h+lpOverlapped], rdi; lpOverlapped
0x18003e8d0  call    cs:__imp_WriteFile
0x18003e8d7  nop     dword ptr [rax+rax+00h]
0x18003e8dc  test    eax, eax
0x18003e8de  jnz     short loc_18003E8EE
0x18003e8e0  call    cs:__imp_GetLastError
0x18003e8e7  nop     dword ptr [rax+rax+00h]
0x18003e8ec  mov     edi, eax
0x18003e8ee  test    edi, edi
0x18003e8f0  jnz     short loc_18003E91B
0x18003e8f2  test    bpl, bpl
0x18003e8f5  jz      short loc_18003E8FC
0x18003e8f7  mov     rsi, [rsi]
0x18003e8fa  jmp     short loc_18003E903
0x18003e8fc  mov     rsi, [rbx+50h]
0x18003e900  mov     bpl, 1
0x18003e903  mov     rcx, [rbx+10h]
0x18003e907  mov     edx, 1000h
0x18003e90c  add     r15d, r14d
0x18003e90f  mov     eax, [rcx+28h]
0x18003e912  add     eax, edx
0x18003e914  cmp     r15d, eax
0x18003e917  jb      short loc_18003E8A9
0x18003e919  xor     edi, edi
0x18003e91b  mov     rbx, [rsp+58h+arg_8]
0x18003e920  mov     eax, edi
0x18003e922  mov     rbp, [rsp+58h+arg_10]
0x18003e927  add     rsp, 30h
0x18003e92b  pop     r15
0x18003e92d  pop     r14
0x18003e92f  pop     r12
0x18003e931  pop     rdi
0x18003e932  pop     rsi
0x18003e933  retn
```
