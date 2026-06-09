# ByteMatch

- ea: `0x180037f90`
- end: `0x180038183`
- name: `ByteMatch`
- size: `499`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callees

- `0x180037f90`
- `0x18003818c`
- `0x1800381ec`
- `0x180038290`
- `0x1800382f0`
- `0x1800827c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800380b0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180038162`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800380b0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180038162`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180038056`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180038056`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180038088`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180038088`

## pseudocode

```c
__int64 __fastcall ByteMatch(__int64 a1, __int64 a2, _DWORD *a3)
{
  int v5; // ebx
  void *v6; // rcx
  void *v7; // rcx
  unsigned int j; // ebx
  unsigned int i; // ebx
  DWORD NumberOfBytesRead[2]; // [rsp+30h] [rbp-40h] BYREF
  LONG lDistanceToMove; // [rsp+38h] [rbp-38h] BYREF
  __int64 v13; // [rsp+40h] [rbp-30h] BYREF
  _BYTE Buffer[32]; // [rsp+48h] [rbp-28h] BYREF

  *a3 = 0;
  if ( (unsigned int)LoadImageFile() )
  {
    v13 = 0;
    v5 = 0;
    lDistanceToMove = 0;
    *(_QWORD *)NumberOfBytesRead = 0;
    while ( !v5 )
    {
      if ( (int)ByteMatchGetSection(a1, ByteMatchSectionInstallers, &v13, NumberOfBytesRead) >= 0
        && (unsigned int)TestByteMatchEntry(v13, *(_QWORD *)NumberOfBytesRead, &ByteMatchSectionInstallers) )
      {
LABEL_16:
        *a3 = 1;
        return 0;
      }
      v5 = 1;
    }
    if ( (int)ByteMatchGetAppendedDataOffset(a1, &lDistanceToMove) >= 0 )
    {
      v6 = *(void **)(a1 + 56);
      NumberOfBytesRead[0] = 0;
      if ( SetFilePointer(v6, lDistanceToMove, 0, 0) != -1
        && ReadFile(*(HANDLE *)(a1 + 56), Buffer, 0x20u, NumberOfBytesRead, 0)
        && NumberOfBytesRead[0] == 32 )
      {
        for ( i = 0; i < 0xB; ++i )
        {
          if ( (unsigned int)TestByteMatchEntry(Buffer, 32, &ByteMatchAppendedDataInstallers[4 * i]) )
            goto LABEL_16;
        }
      }
      v7 = *(void **)(a1 + 56);
      NumberOfBytesRead[0] = 0;
      if ( SetFilePointerEx(v7, (LARGE_INTEGER)-32LL, 0, 2u)
        && ReadFile(*(HANDLE *)(a1 + 56), Buffer, 0x20u, NumberOfBytesRead, 0)
        && NumberOfBytesRead[0] == 32 )
      {
        for ( j = 0; j < 2; ++j )
        {
          if ( (unsigned int)TestByteMatchEntry(Buffer, 32, &ByteMatchEOFInstallers[4 * j]) )
            goto LABEL_16;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180037f90  mov     [rsp-18h+arg_8], rbx
0x180037f95  mov     [rsp-18h+arg_18], rsi
0x180037f9a  push    rbp
0x180037f9b  push    rdi
0x180037f9c  push    r14
0x180037f9e  mov     rbp, rsp
0x180037fa1  sub     rsp, 70h
0x180037fa5  mov     rax, cs:__security_cookie
0x180037fac  xor     rax, rsp
0x180037faf  mov     [rbp+var_8], rax
0x180037fb3  mov     r14, r8
0x180037fb6  mov     dword ptr [r8], 0
0x180037fbd  mov     rdi, rcx
0x180037fc0  call    LoadImageFile
0x180037fc5  test    eax, eax
0x180037fc7  jz      loc_1800380F8
0x180037fcd  mov     [rbp+var_30], 0
0x180037fd5  xor     ebx, ebx
0x180037fd7  mov     [rbp+lDistanceToMove], 0
0x180037fde  mov     qword ptr [rbp+NumberOfBytesRead], 0
0x180037fe6  cmp     ebx, 1
0x180037fe9  jnb     short loc_18003802E
0x180037feb  lea     rcx, ByteMatchSectionInstallers
0x180037ff2  mov     esi, ebx
0x180037ff4  shl     rsi, 5
0x180037ff8  lea     r9, [rbp+NumberOfBytesRead]
0x180037ffc  add     rsi, rcx
0x180037fff  lea     r8, [rbp+var_30]
0x180038003  mov     rcx, rdi
0x180038006  mov     rdx, [rsi]
0x180038009  call    ByteMatchGetSection
0x18003800e  test    eax, eax
0x180038010  js      short loc_18003802A
0x180038012  mov     rdx, qword ptr [rbp+NumberOfBytesRead]
0x180038016  mov     r8, rsi
0x180038019  mov     rcx, [rbp+var_30]
0x18003801d  call    TestByteMatchEntry
0x180038022  test    eax, eax
0x180038024  jnz     loc_1800380F1
0x18003802a  inc     ebx
0x18003802c  jmp     short loc_180037FE6
0x18003802e  lea     rdx, [rbp+lDistanceToMove]
0x180038032  mov     rcx, rdi
0x180038035  call    ByteMatchGetAppendedDataOffset
0x18003803a  test    eax, eax
0x18003803c  js      loc_1800380F8
0x180038042  mov     edx, [rbp+lDistanceToMove]; lDistanceToMove
0x180038045  xor     r9d, r9d; dwMoveMethod
0x180038048  mov     rcx, [rdi+38h]; hFile
0x18003804c  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003804f  mov     [rbp+NumberOfBytesRead], 0
0x180038056  call    cs:__imp_SetFilePointer
0x18003805d  nop     dword ptr [rax+rax+00h]
0x180038062  mov     esi, 20h ; ' '
0x180038067  cmp     eax, 0FFFFFFFFh
0x18003806a  jnz     loc_18003814A
0x180038070  mov     rcx, [rdi+38h]; hFile
0x180038074  xor     r8d, r8d; lpNewFilePointer
0x180038077  mov     r9d, 2; dwMoveMethod
0x18003807d  mov     [rbp+NumberOfBytesRead], 0
0x180038084  lea     rdx, [r8-20h]; liDistanceToMove
0x180038088  call    cs:__imp_SetFilePointerEx
0x18003808f  nop     dword ptr [rax+rax+00h]
0x180038094  test    eax, eax
0x180038096  jz      short loc_1800380F8
0x180038098  mov     rcx, [rdi+38h]; hFile
0x18003809c  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800380a0  mov     r8d, esi; nNumberOfBytesToRead
0x1800380a3  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x1800380ac  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800380b0  call    cs:__imp_ReadFile
0x1800380b7  nop     dword ptr [rax+rax+00h]
0x1800380bc  test    eax, eax
0x1800380be  jz      short loc_1800380F8
0x1800380c0  cmp     [rbp+NumberOfBytesRead], esi
0x1800380c3  jnz     short loc_1800380F8
0x1800380c5  xor     ebx, ebx
0x1800380c7  cmp     ebx, 2
0x1800380ca  jnb     short loc_1800380F8
0x1800380cc  lea     rax, ByteMatchEOFInstallers
0x1800380d3  mov     r8d, ebx
0x1800380d6  shl     r8, 5
0x1800380da  lea     rcx, [rbp+Buffer]
0x1800380de  add     r8, rax
0x1800380e1  mov     rdx, rsi
0x1800380e4  call    TestByteMatchEntry
0x1800380e9  test    eax, eax
0x1800380eb  jnz     short loc_1800380F1
0x1800380ed  inc     ebx
0x1800380ef  jmp     short loc_1800380C7
0x1800380f1  mov     dword ptr [r14], 1
0x1800380f8  xor     eax, eax
0x1800380fa  mov     rcx, [rbp+var_8]
0x1800380fe  xor     rcx, rsp; StackCookie
0x180038101  call    __security_check_cookie
0x180038106  lea     r11, [rsp+70h+var_s0]
0x18003810b  mov     rbx, [r11+28h]
0x18003810f  mov     rsi, [r11+38h]
0x180038113  mov     rsp, r11
0x180038116  pop     r14
0x180038118  pop     rdi
0x180038119  pop     rbp
0x18003811a  retn
0x18003811c  cmp     ebx, 0Bh
0x18003811f  jnb     loc_180038070
0x180038125  lea     rax, ByteMatchAppendedDataInstallers
0x18003812c  mov     r8d, ebx
0x18003812f  shl     r8, 5
0x180038133  lea     rcx, [rbp+Buffer]
0x180038137  add     r8, rax
0x18003813a  mov     rdx, rsi
0x18003813d  call    TestByteMatchEntry
0x180038142  test    eax, eax
0x180038144  jnz     short loc_1800380F1
0x180038146  inc     ebx
0x180038148  jmp     short loc_18003811C
0x18003814a  mov     rcx, [rdi+38h]; hFile
0x18003814e  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180038152  mov     r8d, esi; nNumberOfBytesToRead
0x180038155  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x18003815e  lea     rdx, [rbp+Buffer]; lpBuffer
0x180038162  call    cs:__imp_ReadFile
0x180038169  nop     dword ptr [rax+rax+00h]
0x18003816e  test    eax, eax
0x180038170  jz      loc_180038070
0x180038176  cmp     [rbp+NumberOfBytesRead], esi
0x180038179  jnz     loc_180038070
0x18003817f  xor     ebx, ebx
0x180038181  jmp     short loc_18003811C
```
