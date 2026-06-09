# EtwStream_EndCallback

- ea: `0x180019420`
- end: `0x1800194ab`
- name: `EtwStream_EndCallback`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18001936c`
- `0x180019420`
- `0x180044464`
- `0x18004449c`
- `0x1800444f4`
- `0x18004462c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019433`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019480`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019433`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019480`

## pseudocode

```c
__int64 __fastcall EtwStream_EndCallback(__int64 a1)
{
  __int64 v2; // rdi
  _QWORD *i; // rbx
  __int64 j; // rsi
  __int64 result; // rax

  v2 = a1 + 224;
  if ( *(_QWORD *)(a1 + 264) != GetCurrentThreadId() && (unsigned int)_Pump_BeginDeferringHelper(v2) )
    _Pump_BeginDeferring(v2);
  for ( i = *(_QWORD **)(a1 + 216); i; i = (_QWORD *)*i )
  {
    for ( j = i[1]; j; j = *(_QWORD *)(j + 8) )
      EtwStream_DemuxEndCallback(j, a1);
  }
  result = GetCurrentThreadId();
  if ( *(_QWORD *)(v2 + 40) != (unsigned int)result )
  {
    result = _Pump_EndDeferringHelper(v2);
    if ( (_DWORD)result )
      return _Pump_EndDeferring(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180019420  push    rbx
0x180019422  push    rbp
0x180019423  push    rsi
0x180019424  push    rdi
0x180019425  sub     rsp, 28h
0x180019429  mov     rbp, rcx
0x18001942c  lea     rdi, [rcx+0E0h]
0x180019433  call    cs:__imp_GetCurrentThreadId
0x180019439  mov     eax, eax
0x18001943b  cmp     [rdi+28h], rax
0x18001943f  jz      short loc_180019455
0x180019441  mov     rcx, rdi
0x180019444  call    __Pump_BeginDeferringHelper
0x180019449  test    eax, eax
0x18001944b  jz      short loc_180019455
0x18001944d  mov     rcx, rdi
0x180019450  call    __Pump_BeginDeferring
0x180019455  mov     rbx, [rbp+0D8h]
0x18001945c  jmp     short loc_18001947B
0x18001945e  mov     rsi, [rbx+8]
0x180019462  jmp     short loc_180019473
0x180019464  mov     rdx, rbp
0x180019467  mov     rcx, rsi
0x18001946a  call    EtwStream_DemuxEndCallback
0x18001946f  mov     rsi, [rsi+8]
0x180019473  test    rsi, rsi
0x180019476  jnz     short loc_180019464
0x180019478  mov     rbx, [rbx]
0x18001947b  test    rbx, rbx
0x18001947e  jnz     short loc_18001945E
0x180019480  call    cs:__imp_GetCurrentThreadId
0x180019486  mov     eax, eax
0x180019488  cmp     [rdi+28h], rax
0x18001948c  jz      short loc_1800194A2
0x18001948e  mov     rcx, rdi
0x180019491  call    __Pump_EndDeferringHelper
0x180019496  test    eax, eax
0x180019498  jz      short loc_1800194A2
0x18001949a  mov     rcx, rdi
0x18001949d  call    __Pump_EndDeferring
0x1800194a2  add     rsp, 28h
0x1800194a6  pop     rdi
0x1800194a7  pop     rsi
0x1800194a8  pop     rbp
0x1800194a9  pop     rbx
0x1800194aa  retn
```
