# WriteNewCredentialHistoryRecord

- ea: `0x1800296c8`
- end: `0x18002980f`
- name: `WriteNewCredentialHistoryRecord`
- size: `327`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003b98`
- `0x1800284ac`

## callees

- `0x180007f10`
- `0x1800296c8`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002977f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002977f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800297f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800297f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800296ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800296ff`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002976e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002976e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800297b1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800297b1`

## string_xrefs

- `0x180029725`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`

## pseudocode

```c
__int64 __fastcall WriteNewCredentialHistoryRecord(HANDLE hFile, __int64 a2, unsigned int a3, __int64 a4)
{
  unsigned int v4; // eax
  __int64 v5; // rbp
  __int64 v8; // rbx
  char *v10; // rax
  char *v11; // rdi
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  DWORD LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+18h] BYREF

  NumberOfBytesWritten = 0;
  v4 = 24;
  v5 = a3;
  if ( a3 )
    v4 = a3;
  v8 = v4;
  v10 = (char *)LocalAlloc(0x40u, v4);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
      memcpy_0(v10, (const void *)(a2 + 24), v5 - 24);
    *(_OWORD *)&v11[v8 - 24] = *(_OWORD *)a4;
    *(_QWORD *)&v11[v8 - 8] = *(_QWORD *)(a4 + 16);
    if ( SetFilePointer(hFile, 0, 0, 2u) == -1 )
    {
      LastError = GetLastError();
      v13 = 1491;
    }
    else
    {
      if ( WriteFile(hFile, v11, v8, &NumberOfBytesWritten, 0) )
      {
        if ( NumberOfBytesWritten == (_DWORD)v8 )
        {
          v12 = 0;
          goto LABEL_17;
        }
        v12 = 665;
        v13 = 1510;
        goto LABEL_5;
      }
      LastError = GetLastError();
      v13 = 1503;
    }
    v12 = LastError;
    v14 = LastError;
    goto LABEL_6;
  }
  v12 = 14;
  v13 = 1460;
LABEL_5:
  v14 = v12;
LABEL_6:
  DebugTraceError(v14, "dwResult", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", v13);
LABEL_17:
  LocalFree(v11);
  return v12;
}

```

## disassembly

```asm
0x1800296c8  mov     rax, rsp
0x1800296cb  push    rbx
0x1800296cc  push    rbp
0x1800296cd  push    rsi
0x1800296ce  push    rdi
0x1800296cf  push    r14
0x1800296d1  push    r15
0x1800296d3  sub     rsp, 38h
0x1800296d7  mov     dword ptr [rax+18h], 0
0x1800296de  test    r8d, r8d
0x1800296e1  mov     eax, 18h
0x1800296e6  mov     ebp, r8d
0x1800296e9  cmovnz  eax, r8d
0x1800296ed  mov     rsi, rdx
0x1800296f0  mov     r14, rcx
0x1800296f3  mov     edx, eax; uBytes
0x1800296f5  mov     ecx, 40h ; '@'; uFlags
0x1800296fa  mov     ebx, eax
0x1800296fc  mov     r15, r9
0x1800296ff  call    cs:__imp_LocalAlloc
0x180029706  nop     dword ptr [rax+rax+00h]
0x18002970b  mov     rdi, rax
0x18002970e  test    rax, rax
0x180029711  jnz     short loc_180029736
0x180029713  lea     ebx, [rax+0Eh]
0x180029716  mov     r9d, 5B4h
0x18002971c  mov     ecx, ebx
0x18002971e  lea     rdx, aDwresult; "dwResult"
0x180029725  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002972c  call    DebugTraceError
0x180029731  jmp     loc_1800297F0
0x180029736  test    rsi, rsi
0x180029739  jz      short loc_18002974B
0x18002973b  lea     r8, [rbp-18h]; Size
0x18002973f  mov     rcx, rdi; void *
0x180029742  lea     rdx, [rsi+18h]; Src
0x180029746  call    memcpy_0
0x18002974b  movups  xmm0, xmmword ptr [r15]
0x18002974f  mov     r9d, 2; dwMoveMethod
0x180029755  xor     r8d, r8d; lpDistanceToMoveHigh
0x180029758  xor     edx, edx; lDistanceToMove
0x18002975a  mov     rcx, r14; hFile
0x18002975d  movups  xmmword ptr [rbx+rdi-18h], xmm0
0x180029762  movsd   xmm1, qword ptr [r15+10h]
0x180029768  movsd   qword ptr [rbx+rdi-8], xmm1
0x18002976e  call    cs:__imp_SetFilePointer
0x180029775  nop     dword ptr [rax+rax+00h]
0x18002977a  cmp     eax, 0FFFFFFFFh
0x18002977d  jnz     short loc_180029797
0x18002977f  call    cs:__imp_GetLastError
0x180029786  nop     dword ptr [rax+rax+00h]
0x18002978b  mov     r9d, 5D3h
0x180029791  mov     ebx, eax
0x180029793  mov     ecx, eax
0x180029795  jmp     short loc_18002971E
0x180029797  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002979f  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800297a8  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800297ab  mov     rdx, rdi; lpBuffer
0x1800297ae  mov     rcx, r14; hFile
0x1800297b1  call    cs:__imp_WriteFile
0x1800297b8  nop     dword ptr [rax+rax+00h]
0x1800297bd  test    eax, eax
0x1800297bf  jnz     short loc_1800297D5
0x1800297c1  call    cs:__imp_GetLastError
0x1800297c8  nop     dword ptr [rax+rax+00h]
0x1800297cd  mov     r9d, 5DFh
0x1800297d3  jmp     short loc_180029791
0x1800297d5  cmp     [rsp+68h+NumberOfBytesWritten], ebx
0x1800297dc  jz      short loc_1800297EE
0x1800297de  mov     ebx, 299h
0x1800297e3  mov     r9d, 5E6h
0x1800297e9  jmp     loc_18002971C
0x1800297ee  xor     ebx, ebx
0x1800297f0  mov     rcx, rdi; hMem
0x1800297f3  call    cs:__imp_LocalFree
0x1800297fa  nop     dword ptr [rax+rax+00h]
0x1800297ff  mov     eax, ebx
0x180029801  add     rsp, 38h
0x180029805  pop     r15
0x180029807  pop     r14
0x180029809  pop     rdi
0x18002980a  pop     rsi
0x18002980b  pop     rbp
0x18002980c  pop     rbx
0x18002980d  retn
```
