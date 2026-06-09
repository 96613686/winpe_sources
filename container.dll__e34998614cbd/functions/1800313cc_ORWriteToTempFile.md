# ORWriteToTempFile

- ea: `0x1800313cc`
- end: `0x1800314ad`
- name: `ORWriteToTempFile`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x18002e494`

## callees

- `0x18002fc08`
- `0x1800313cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031458`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180031448`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180031448`

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
0x1800313cc  mov     [rsp+arg_8], rbx
0x1800313d1  mov     [rsp+arg_10], rbp
0x1800313d6  push    rsi
0x1800313d7  push    rdi
0x1800313d8  push    r12
0x1800313da  push    r14
0x1800313dc  push    r15
0x1800313de  sub     rsp, 30h
0x1800313e2  mov     [rsp+58h+NumberOfBytesWritten], 0
0x1800313ea  mov     r12, rdx
0x1800313ed  mov     rbx, rcx
0x1800313f0  test    rcx, rcx
0x1800313f3  jnz     short loc_1800313FD
0x1800313f5  lea     edi, [rcx+57h]
0x1800313f8  jmp     loc_180031493
0x1800313fd  cmp     qword ptr [rcx+10h], 0
0x180031402  jz      short loc_180031409
0x180031404  call    ORUpdateBaseBlock
0x180031409  mov     rcx, [rbx+10h]
0x18003140d  mov     edx, 1000h
0x180031412  mov     eax, [rcx+28h]
0x180031415  add     eax, edx
0x180031417  jz      short loc_180031491
0x180031419  xor     r15d, r15d
0x18003141c  xor     bpl, bpl
0x18003141f  xor     esi, esi
0x180031421  test    bpl, bpl
0x180031424  jnz     short loc_18003142B
0x180031426  mov     r14d, edx
0x180031429  jmp     short loc_180031433
0x18003142b  mov     r14d, [rsi+24h]
0x18003142f  mov     rcx, [rsi+28h]
0x180031433  mov     rdx, rcx; lpBuffer
0x180031436  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003143b  xor     edi, edi
0x18003143d  mov     rcx, r12; hFile
0x180031440  mov     r8d, r14d; nNumberOfBytesToWrite
0x180031443  mov     [rsp+58h+lpOverlapped], rdi; lpOverlapped
0x180031448  call    cs:__imp_WriteFile
0x18003144f  nop     dword ptr [rax+rax+00h]
0x180031454  test    eax, eax
0x180031456  jnz     short loc_180031466
0x180031458  call    cs:__imp_GetLastError
0x18003145f  nop     dword ptr [rax+rax+00h]
0x180031464  mov     edi, eax
0x180031466  test    edi, edi
0x180031468  jnz     short loc_180031493
0x18003146a  test    bpl, bpl
0x18003146d  jz      short loc_180031474
0x18003146f  mov     rsi, [rsi]
0x180031472  jmp     short loc_18003147B
0x180031474  mov     rsi, [rbx+50h]
0x180031478  mov     bpl, 1
0x18003147b  mov     rcx, [rbx+10h]
0x18003147f  mov     edx, 1000h
0x180031484  add     r15d, r14d
0x180031487  mov     eax, [rcx+28h]
0x18003148a  add     eax, edx
0x18003148c  cmp     r15d, eax
0x18003148f  jb      short loc_180031421
0x180031491  xor     edi, edi
0x180031493  mov     rbx, [rsp+58h+arg_8]
0x180031498  mov     eax, edi
0x18003149a  mov     rbp, [rsp+58h+arg_10]
0x18003149f  add     rsp, 30h
0x1800314a3  pop     r15
0x1800314a5  pop     r14
0x1800314a7  pop     r12
0x1800314a9  pop     rdi
0x1800314aa  pop     rsi
0x1800314ab  retn
```
