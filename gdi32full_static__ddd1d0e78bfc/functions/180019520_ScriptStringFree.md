# ScriptStringFree

- ea: `0x180019520`
- end: `0x180019620`
- name: `ScriptStringFree`
- size: `256`
- prototype: `HRESULT __stdcall(SCRIPT_STRING_ANALYSIS *pssa)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x1800156c0`
- `0x180016820`
- `0x180016b20`
- `0x180017df0`
- `0x180018070`
- `0x180019cd0`
- `0x18001acb0`
- `0x18001fc00`
- `0x180021f80`
- `0x180022e60`
- `0x180043050`
- `0x180058680`
- `0x18005a0d0`
- `0x1800620ac`
- `0x18006507c`
- `0x18007b6b0`
- `0x1800a26f0`

## callees

- `0x180006f3c`
- `0x180019520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800195c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800195c6`
- `GDI32!DeleteObject` at `0x18001956d`
- `GDI32!DeleteObject` at `0x18001956d`

## pseudocode

```c
HRESULT __stdcall ScriptStringFree(SCRIPT_STRING_ANALYSIS *pssa)
{
  _QWORD *v2; // rdi
  __int64 i; // rbx
  void *v4; // rcx
  HANDLE v5; // rcx
  HRESULT result; // eax

  if ( pssa )
  {
    v2 = *pssa;
    if ( *pssa )
    {
      for ( i = 1; i != 59; ++i )
      {
        v4 = (void *)v2[i + 114];
        if ( v4 )
          DeleteObject(v4);
      }
      v5 = ghHeap;
      if ( !ghHeap )
      {
        if ( gfMemoryInitFailed || !(unsigned int)UspInitMemory() )
        {
          result = -2147024882;
          goto LABEL_11;
        }
        v5 = ghHeap;
      }
      if ( v2 == pbStaticAnalysisBuffer )
      {
        if ( _InterlockedExchange(&fStaticAnalysisBufferIsFree, 1) )
        {
          result = -2147467259;
          goto LABEL_11;
        }
      }
      else if ( !HeapFree(v5, 0, v2) )
      {
        result = GetLastError();
        if ( result > 0 )
          result = (unsigned __int16)result | 0x80070000;
        goto LABEL_11;
      }
      result = 0;
LABEL_11:
      *pssa = 0;
      return result;
    }
  }
  return -2147024809;
}

```

## disassembly

```asm
0x180019520  mov     [rsp+arg_10], rdi
0x180019525  push    r14
0x180019527  sub     rsp, 20h
0x18001952b  mov     r14, rcx
0x18001952e  test    rcx, rcx
0x180019531  jz      loc_18001960B
0x180019537  mov     rdi, [rcx]
0x18001953a  test    rdi, rdi
0x18001953d  jz      loc_18001960B
0x180019543  mov     [rsp+28h+arg_0], rbx
0x180019548  mov     [rsp+28h+arg_8], rsi
0x18001954d  mov     esi, 1
0x180019552  mov     ebx, esi
0x180019554  nop     dword ptr [rax+00h]
0x180019558  nop     dword ptr [rax+rax+00000000h]
0x180019560  mov     rcx, [rdi+rbx*8+390h]; ho
0x180019568  test    rcx, rcx
0x18001956b  jz      short loc_180019579
0x18001956d  call    cs:__imp_DeleteObject
0x180019574  nop     dword ptr [rax+rax+00h]
0x180019579  inc     rbx
0x18001957c  cmp     rbx, 3Bh ; ';'
0x180019580  jnz     short loc_180019560
0x180019582  mov     rcx, cs:?ghHeap@@3PEAXEA; hHeap
0x180019589  mov     rbx, [rsp+28h+arg_0]
0x18001958e  test    rcx, rcx
0x180019591  jz      short loc_1800195F0
0x180019593  cmp     rdi, cs:?pbStaticAnalysisBuffer@@3PEAEEA; uchar * pbStaticAnalysisBuffer
0x18001959a  jnz     short loc_1800195C1
0x18001959c  xchg    esi, cs:?fStaticAnalysisBufferIsFree@@3JA; long fStaticAnalysisBufferIsFree
0x1800195a2  test    esi, esi
0x1800195a4  jnz     short loc_180019619
0x1800195a6  xor     eax, eax
0x1800195a8  mov     rsi, [rsp+28h+arg_8]
0x1800195ad  mov     qword ptr [r14], 0
0x1800195b4  mov     rdi, [rsp+28h+arg_10]
0x1800195b9  add     rsp, 20h
0x1800195bd  pop     r14
0x1800195bf  retn
0x1800195c1  mov     r8, rdi; lpMem
0x1800195c4  xor     edx, edx; dwFlags
0x1800195c6  call    cs:__imp_HeapFree
0x1800195cd  nop     dword ptr [rax+rax+00h]
0x1800195d2  test    eax, eax
0x1800195d4  jnz     short loc_1800195A6
0x1800195d6  call    cs:__imp_GetLastError
0x1800195dd  nop     dword ptr [rax+rax+00h]
0x1800195e2  test    eax, eax
0x1800195e4  jle     short loc_1800195A8
0x1800195e6  movzx   eax, ax
0x1800195e9  or      eax, 80070000h
0x1800195ee  jmp     short loc_1800195A8
0x1800195f0  cmp     cs:?gfMemoryInitFailed@@3HA, 0; int gfMemoryInitFailed
0x1800195f7  jnz     short loc_180019612
0x1800195f9  call    ?UspInitMemory@@YAHXZ; UspInitMemory(void)
0x1800195fe  test    eax, eax
0x180019600  jz      short loc_180019612
0x180019602  mov     rcx, cs:?ghHeap@@3PEAXEA; void * ghHeap
0x180019609  jmp     short loc_180019593
0x18001960b  mov     eax, 80070057h
0x180019610  jmp     short loc_1800195B4
0x180019612  mov     eax, 8007000Eh
0x180019617  jmp     short loc_1800195A8
0x180019619  mov     eax, 80004005h
0x18001961e  jmp     short loc_1800195A8
```
