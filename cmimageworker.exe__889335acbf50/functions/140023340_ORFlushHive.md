# ORFlushHive

- ea: `0x140023340`
- end: `0x14002346e`
- name: `ORFlushHive`
- size: `302`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x140023340`
- `0x140027f2c`
- `0x140028024`
- `0x140028ce8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400233a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400233a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140023372`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140023372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002340b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002340b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023449`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1400233e8`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1400233e8`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1400233fb`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1400233fb`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x140023439`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x140023439`

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
0x140023340  push    rbx
0x140023342  push    rbp
0x140023343  push    rsi
0x140023344  push    rdi
0x140023345  sub     rsp, 28h
0x140023349  xor     bpl, bpl
0x14002334c  mov     eax, 746Eh
0x140023351  cmp     [rcx+1Ch], ax
0x140023355  jz      short loc_14002338A
0x140023357  xor     edi, edi
0x140023359  mov     ebx, 6
0x14002335e  mov     rcx, rdi
0x140023361  call    ORFreeBinMap
0x140023366  test    bpl, bpl
0x140023369  jz      short loc_14002337E
0x14002336b  lea     rcx, [rdi+88h]; lpCriticalSection
0x140023372  call    cs:__imp_LeaveCriticalSection
0x140023379  nop     dword ptr [rax+rax+00h]
0x14002337e  mov     eax, ebx
0x140023380  add     rsp, 28h
0x140023384  pop     rdi
0x140023385  pop     rsi
0x140023386  pop     rbp
0x140023387  pop     rbx
0x140023388  retn
0x14002338a  mov     rdi, [rcx+10h]
0x14002338e  test    rdi, rdi
0x140023391  jz      short loc_140023359
0x140023393  cmp     dword ptr [rdi], 0BEE0BEE0h
0x140023399  jnz     short loc_140023359
0x14002339b  lea     rcx, [rdi+88h]; lpCriticalSection
0x1400233a2  call    cs:__imp_EnterCriticalSection
0x1400233a9  nop     dword ptr [rax+rax+00h]
0x1400233ae  cmp     qword ptr [rdi+80h], 0
0x1400233b6  mov     bpl, 1
0x1400233b9  jz      short loc_140023359
0x1400233bb  cmp     dword ptr [rdi+0B4h], 0
0x1400233c2  jnz     short loc_1400233C8
0x1400233c4  xor     ebx, ebx
0x1400233c6  jmp     short loc_14002335E
0x1400233c8  mov     rcx, rdi
0x1400233cb  call    ORSerializeHive
0x1400233d0  mov     ebx, eax
0x1400233d2  test    eax, eax
0x1400233d4  jnz     short loc_14002335E
0x1400233d6  mov     rsi, [rdi+80h]
0x1400233dd  xor     edx, edx; liDistanceToMove
0x1400233df  mov     rcx, rsi; hFile
0x1400233e2  xor     r9d, r9d; dwMoveMethod
0x1400233e5  xor     r8d, r8d; lpNewFilePointer
0x1400233e8  call    cs:__imp_SetFilePointerEx
0x1400233ef  nop     dword ptr [rax+rax+00h]
0x1400233f4  test    eax, eax
0x1400233f6  jz      short loc_14002340B
0x1400233f8  mov     rcx, rsi; hFile
0x1400233fb  call    cs:__imp_SetEndOfFile
0x140023402  nop     dword ptr [rax+rax+00h]
0x140023407  test    eax, eax
0x140023409  jnz     short loc_140023421
0x14002340b  call    cs:__imp_GetLastError
0x140023412  nop     dword ptr [rax+rax+00h]
0x140023417  mov     ebx, eax
0x140023419  test    eax, eax
0x14002341b  jnz     loc_14002335E
0x140023421  mov     rdx, rsi
0x140023424  mov     rcx, rdi
0x140023427  call    ORWriteToTempFile
0x14002342c  mov     ebx, eax
0x14002342e  test    eax, eax
0x140023430  jnz     loc_14002335E
0x140023436  mov     rcx, rsi; hFile
0x140023439  call    cs:__imp_FlushFileBuffers
0x140023440  nop     dword ptr [rax+rax+00h]
0x140023445  test    eax, eax
0x140023447  jnz     short loc_14002345F
0x140023449  call    cs:__imp_GetLastError
0x140023450  nop     dword ptr [rax+rax+00h]
0x140023455  mov     ebx, eax
0x140023457  test    eax, eax
0x140023459  jnz     loc_14002335E
0x14002345f  mov     dword ptr [rdi+0B4h], 0
0x140023469  jmp     loc_1400233C4
```
