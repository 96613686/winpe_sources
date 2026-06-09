# EtwDemux_MatchFlow

- ea: `0x180019ee0`
- end: `0x180019fa5`
- name: `EtwDemux_MatchFlow`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180019500`

## callees

- `0x180019ee0`
- `0x180044464`
- `0x18004449c`
- `0x1800444f4`
- `0x18004462c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019efb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019f78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019efb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019f78`

## pseudocode

```c
__int64 __fastcall EtwDemux_MatchFlow(
        __int64 a1,
        _QWORD *a2,
        unsigned __int8 a3,
        __int64 a4,
        void (__fastcall *a5)(__int64, __int64),
        __int64 a6)
{
  __int64 v7; // rdi
  _QWORD *i; // rcx
  __int64 j; // rbx
  __int64 result; // rax

  v7 = a1 + 8;
  if ( *(_QWORD *)(a1 + 48) != GetCurrentThreadId() && (unsigned int)_Pump_BeginDeferringHelper(v7) )
    _Pump_BeginDeferring(v7);
  for ( i = *(_QWORD **)a1; i; i = (_QWORD *)*i )
  {
    if ( *a2 == i[2] && a2[1] == i[3] )
    {
      for ( j = i[1]; j; j = *(_QWORD *)(j + 8) )
      {
        if ( a3 <= *(_BYTE *)(j + 16) && (!a4 || !*(_QWORD *)(j + 24) || (a4 & *(_QWORD *)(j + 24)) != 0) )
          a5(j, a6);
      }
      break;
    }
  }
  result = GetCurrentThreadId();
  if ( *(_QWORD *)(v7 + 40) != (unsigned int)result )
  {
    result = _Pump_EndDeferringHelper(v7);
    if ( (_DWORD)result )
      return _Pump_EndDeferring(v7);
  }
  return result;
}

```

## disassembly

```asm
0x180019ee0  push    rbx
0x180019ee2  push    rbp
0x180019ee3  push    rsi
0x180019ee4  push    rdi
0x180019ee5  push    r14
0x180019ee7  sub     rsp, 20h
0x180019eeb  mov     rbp, r9
0x180019eee  lea     rdi, [rcx+8]
0x180019ef2  mov     r14b, r8b
0x180019ef5  mov     rsi, rdx
0x180019ef8  mov     rbx, rcx
0x180019efb  call    cs:__imp_GetCurrentThreadId
0x180019f01  mov     eax, eax
0x180019f03  cmp     [rdi+28h], rax
0x180019f07  jz      short loc_180019F1D
0x180019f09  mov     rcx, rdi
0x180019f0c  call    __Pump_BeginDeferringHelper
0x180019f11  test    eax, eax
0x180019f13  jz      short loc_180019F1D
0x180019f15  mov     rcx, rdi
0x180019f18  call    __Pump_BeginDeferring
0x180019f1d  mov     rcx, [rbx]
0x180019f20  jmp     short loc_180019F38
0x180019f22  mov     rax, [rsi]
0x180019f25  cmp     rax, [rcx+10h]
0x180019f29  jnz     short loc_180019F35
0x180019f2b  mov     rax, [rsi+8]
0x180019f2f  cmp     rax, [rcx+18h]
0x180019f33  jz      short loc_180019F3F
0x180019f35  mov     rcx, [rcx]
0x180019f38  test    rcx, rcx
0x180019f3b  jnz     short loc_180019F22
0x180019f3d  jmp     short loc_180019F78
0x180019f3f  mov     rbx, [rcx+8]
0x180019f43  jmp     short loc_180019F73
0x180019f45  cmp     r14b, [rbx+10h]
0x180019f49  ja      short loc_180019F6F
0x180019f4b  test    rbp, rbp
0x180019f4e  jz      short loc_180019F5D
0x180019f50  cmp     qword ptr [rbx+18h], 0
0x180019f55  jz      short loc_180019F5D
0x180019f57  test    [rbx+18h], rbp
0x180019f5b  jz      short loc_180019F6F
0x180019f5d  mov     rdx, [rsp+48h+arg_28]
0x180019f62  mov     rcx, rbx
0x180019f65  mov     rax, [rsp+48h+arg_20]
0x180019f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f6f  mov     rbx, [rbx+8]
0x180019f73  test    rbx, rbx
0x180019f76  jnz     short loc_180019F45
0x180019f78  call    cs:__imp_GetCurrentThreadId
0x180019f7e  mov     eax, eax
0x180019f80  cmp     [rdi+28h], rax
0x180019f84  jz      short loc_180019F9A
0x180019f86  mov     rcx, rdi
0x180019f89  call    __Pump_EndDeferringHelper
0x180019f8e  test    eax, eax
0x180019f90  jz      short loc_180019F9A
0x180019f92  mov     rcx, rdi
0x180019f95  call    __Pump_EndDeferring
0x180019f9a  add     rsp, 20h
0x180019f9e  pop     r14
0x180019fa0  pop     rdi
0x180019fa1  pop     rsi
0x180019fa2  pop     rbp
0x180019fa3  pop     rbx
0x180019fa4  retn
```
