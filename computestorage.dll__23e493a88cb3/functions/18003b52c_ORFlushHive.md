# ORFlushHive

- ea: `0x18003b52c`
- end: `0x18003b65a`
- name: `ORFlushHive`
- size: `302`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002d9b0`
- `0x18002dcec`

## callees

- `0x18003b52c`
- `0x18003db94`
- `0x18003dc8c`
- `0x18003e854`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18003b625`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18003b625`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003b5d4`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003b5d4`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18003b5e7`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18003b5e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b58e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b58e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b55e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b55e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b5f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b5f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b635`

## pseudocode

```c
__int64 __fastcall ORFlushHive(__int64 a1)
{
  char v1; // bp
  __int64 v2; // rdi
  unsigned int LastError; // ebx
  void *v5; // rsi

  v1 = 0;
  if ( *(_WORD *)(a1 + 28) != 29806 )
  {
    v2 = 0;
LABEL_3:
    LastError = 6;
    goto LABEL_4;
  }
  v2 = *(_QWORD *)(a1 + 16);
  if ( !v2 )
    goto LABEL_3;
  if ( *(_DWORD *)v2 != -1092567328 )
    goto LABEL_3;
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 136));
  v1 = 1;
  if ( !*(_QWORD *)(v2 + 128) )
    goto LABEL_3;
  if ( !*(_DWORD *)(v2 + 180) )
    goto LABEL_11;
  LastError = ORSerializeHive(v2);
  if ( !LastError )
  {
    if ( (v5 = *(void **)(v2 + 128), SetFilePointerEx(v5, 0, 0, 0)) && SetEndOfFile(v5)
      || (LastError = GetLastError()) == 0 )
    {
      LastError = ORWriteToTempFile(v2, v5);
      if ( !LastError && (FlushFileBuffers(v5) || (LastError = GetLastError()) == 0) )
      {
        *(_DWORD *)(v2 + 180) = 0;
LABEL_11:
        LastError = 0;
      }
    }
  }
LABEL_4:
  ORFreeBinMap(v2);
  if ( v1 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 136));
  return LastError;
}

```

## disassembly

```asm
0x18003b52c  push    rbx
0x18003b52e  push    rbp
0x18003b52f  push    rsi
0x18003b530  push    rdi
0x18003b531  sub     rsp, 28h
0x18003b535  xor     bpl, bpl
0x18003b538  mov     eax, 746Eh
0x18003b53d  cmp     [rcx+1Ch], ax
0x18003b541  jz      short loc_18003B576
0x18003b543  xor     edi, edi
0x18003b545  mov     ebx, 6
0x18003b54a  mov     rcx, rdi
0x18003b54d  call    ORFreeBinMap
0x18003b552  test    bpl, bpl
0x18003b555  jz      short loc_18003B56A
0x18003b557  lea     rcx, [rdi+88h]; lpCriticalSection
0x18003b55e  call    cs:__imp_LeaveCriticalSection
0x18003b565  nop     dword ptr [rax+rax+00h]
0x18003b56a  mov     eax, ebx
0x18003b56c  add     rsp, 28h
0x18003b570  pop     rdi
0x18003b571  pop     rsi
0x18003b572  pop     rbp
0x18003b573  pop     rbx
0x18003b574  retn
0x18003b576  mov     rdi, [rcx+10h]
0x18003b57a  test    rdi, rdi
0x18003b57d  jz      short loc_18003B545
0x18003b57f  cmp     dword ptr [rdi], 0BEE0BEE0h
0x18003b585  jnz     short loc_18003B545
0x18003b587  lea     rcx, [rdi+88h]; lpCriticalSection
0x18003b58e  call    cs:__imp_EnterCriticalSection
0x18003b595  nop     dword ptr [rax+rax+00h]
0x18003b59a  cmp     qword ptr [rdi+80h], 0
0x18003b5a2  mov     bpl, 1
0x18003b5a5  jz      short loc_18003B545
0x18003b5a7  cmp     dword ptr [rdi+0B4h], 0
0x18003b5ae  jnz     short loc_18003B5B4
0x18003b5b0  xor     ebx, ebx
0x18003b5b2  jmp     short loc_18003B54A
0x18003b5b4  mov     rcx, rdi
0x18003b5b7  call    ORSerializeHive
0x18003b5bc  mov     ebx, eax
0x18003b5be  test    eax, eax
0x18003b5c0  jnz     short loc_18003B54A
0x18003b5c2  mov     rsi, [rdi+80h]
0x18003b5c9  xor     edx, edx; liDistanceToMove
0x18003b5cb  mov     rcx, rsi; hFile
0x18003b5ce  xor     r9d, r9d; dwMoveMethod
0x18003b5d1  xor     r8d, r8d; lpNewFilePointer
0x18003b5d4  call    cs:__imp_SetFilePointerEx
0x18003b5db  nop     dword ptr [rax+rax+00h]
0x18003b5e0  test    eax, eax
0x18003b5e2  jz      short loc_18003B5F7
0x18003b5e4  mov     rcx, rsi; hFile
0x18003b5e7  call    cs:__imp_SetEndOfFile
0x18003b5ee  nop     dword ptr [rax+rax+00h]
0x18003b5f3  test    eax, eax
0x18003b5f5  jnz     short loc_18003B60D
0x18003b5f7  call    cs:__imp_GetLastError
0x18003b5fe  nop     dword ptr [rax+rax+00h]
0x18003b603  mov     ebx, eax
0x18003b605  test    eax, eax
0x18003b607  jnz     loc_18003B54A
0x18003b60d  mov     rdx, rsi
0x18003b610  mov     rcx, rdi
0x18003b613  call    ORWriteToTempFile
0x18003b618  mov     ebx, eax
0x18003b61a  test    eax, eax
0x18003b61c  jnz     loc_18003B54A
0x18003b622  mov     rcx, rsi; hFile
0x18003b625  call    cs:__imp_FlushFileBuffers
0x18003b62c  nop     dword ptr [rax+rax+00h]
0x18003b631  test    eax, eax
0x18003b633  jnz     short loc_18003B64B
0x18003b635  call    cs:__imp_GetLastError
0x18003b63c  nop     dword ptr [rax+rax+00h]
0x18003b641  mov     ebx, eax
0x18003b643  test    eax, eax
0x18003b645  jnz     loc_18003B54A
0x18003b64b  mov     dword ptr [rdi+0B4h], 0
0x18003b655  jmp     loc_18003B5B0
```
