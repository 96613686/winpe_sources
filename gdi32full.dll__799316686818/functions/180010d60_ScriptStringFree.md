# ScriptStringFree

- ea: `0x180010d60`
- end: `0x180010e4d`
- name: `ScriptStringFree`
- size: `237`
- prototype: `HRESULT __stdcall(SCRIPT_STRING_ANALYSIS *pssa)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f270`
- `0x18000f6f0`
- `0x18000f970`
- `0x180013a50`
- `0x180015dc0`
- `0x18002e380`
- `0x18002e880`
- `0x18002ec50`
- `0x18002ed40`
- `0x18002f7b0`
- `0x1800374c0`
- `0x180053610`
- `0x180055720`
- `0x18005e24c`
- `0x1800607dc`
- `0x180076c30`
- `0x18009f800`

## callees

- `0x18000db8c`
- `0x180010d60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010dff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010dff`
- `GDI32!DeleteObject` at `0x180010dad`
- `GDI32!DeleteObject` at `0x180010dad`

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
0x180010d60  mov     [rsp+arg_10], rdi
0x180010d65  push    r14
0x180010d67  sub     rsp, 20h
0x180010d6b  mov     r14, rcx
0x180010d6e  test    rcx, rcx
0x180010d71  jz      loc_180010E38
0x180010d77  mov     rdi, [rcx]
0x180010d7a  test    rdi, rdi
0x180010d7d  jz      loc_180010E38
0x180010d83  mov     [rsp+28h+arg_0], rbx
0x180010d88  mov     [rsp+28h+arg_8], rsi
0x180010d8d  mov     esi, 1
0x180010d92  mov     ebx, esi
0x180010d94  nop     dword ptr [rax+00h]
0x180010d98  nop     dword ptr [rax+rax+00000000h]
0x180010da0  mov     rcx, [rdi+rbx*8+390h]; ho
0x180010da8  test    rcx, rcx
0x180010dab  jz      short loc_180010DB3
0x180010dad  call    cs:__imp_DeleteObject
0x180010db3  inc     rbx
0x180010db6  cmp     rbx, 3Bh ; ';'
0x180010dba  jnz     short loc_180010DA0
0x180010dbc  mov     rcx, cs:?ghHeap@@3PEAXEA; hHeap
0x180010dc3  mov     rbx, [rsp+28h+arg_0]
0x180010dc8  test    rcx, rcx
0x180010dcb  jz      short loc_180010E1D
0x180010dcd  cmp     rdi, cs:?pbStaticAnalysisBuffer@@3PEAEEA; uchar * pbStaticAnalysisBuffer
0x180010dd4  jnz     short loc_180010DFA
0x180010dd6  xchg    esi, cs:?fStaticAnalysisBufferIsFree@@3JA; long fStaticAnalysisBufferIsFree
0x180010ddc  test    esi, esi
0x180010dde  jnz     short loc_180010E46
0x180010de0  xor     eax, eax
0x180010de2  mov     rsi, [rsp+28h+arg_8]
0x180010de7  mov     qword ptr [r14], 0
0x180010dee  mov     rdi, [rsp+28h+arg_10]
0x180010df3  add     rsp, 20h
0x180010df7  pop     r14
0x180010df9  retn
0x180010dfa  mov     r8, rdi; lpMem
0x180010dfd  xor     edx, edx; dwFlags
0x180010dff  call    cs:__imp_HeapFree
0x180010e05  test    eax, eax
0x180010e07  jnz     short loc_180010DE0
0x180010e09  call    cs:__imp_GetLastError
0x180010e0f  test    eax, eax
0x180010e11  jle     short loc_180010DE2
0x180010e13  movzx   eax, ax
0x180010e16  or      eax, 80070000h
0x180010e1b  jmp     short loc_180010DE2
0x180010e1d  cmp     cs:?gfMemoryInitFailed@@3HA, 0; int gfMemoryInitFailed
0x180010e24  jnz     short loc_180010E3F
0x180010e26  call    ?UspInitMemory@@YAHXZ; UspInitMemory(void)
0x180010e2b  test    eax, eax
0x180010e2d  jz      short loc_180010E3F
0x180010e2f  mov     rcx, cs:?ghHeap@@3PEAXEA; void * ghHeap
0x180010e36  jmp     short loc_180010DCD
0x180010e38  mov     eax, 80070057h
0x180010e3d  jmp     short loc_180010DEE
0x180010e3f  mov     eax, 8007000Eh
0x180010e44  jmp     short loc_180010DE2
0x180010e46  mov     eax, 80004005h
0x180010e4b  jmp     short loc_180010DE2
```
