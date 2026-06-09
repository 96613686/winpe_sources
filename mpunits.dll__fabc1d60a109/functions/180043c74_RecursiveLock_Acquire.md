# RecursiveLock_Acquire

- ea: `0x180043c74`
- end: `0x180043cd1`
- name: `RecursiveLock_Acquire`
- size: `93`
- prototype: ``
- caller_count: `31`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a794`
- `0x18001a890`
- `0x18001a960`
- `0x18001aae0`
- `0x18001ac00`
- `0x18001b5e0`
- `0x18001c370`
- `0x18001c760`
- `0x18001c840`
- `0x18001c8a0`
- `0x18002cdf4`
- `0x18002ced8`
- `0x18002d028`
- `0x18002d3c8`
- `0x18002f430`
- `0x18002f6c0`
- `0x18002f7b0`
- `0x18002f81c`
- `0x18002f9dc`
- `0x18002fb20`
- `0x1800356b0`
- `0x180035830`
- `0x1800358f0`
- `0x180035d00`
- `0x180036360`
- `0x180036450`
- `0x180037620`
- `0x1800376b0`
- `0x180037e38`
- `0x18003d4d0`
- `0x18003d534`

## callees

- `0x180042ecc`
- `0x1800431f0`
- `0x180043c74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043c86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043c86`

## pseudocode

```c
__int64 __fastcall RecursiveLock_Acquire(unsigned __int64 a1)
{
  DWORD CurrentThreadId; // ebx
  __int64 v3; // rax
  __int64 result; // rax

  CurrentThreadId = GetCurrentThreadId();
  v3 = *(_QWORD *)(a1 + 8);
  if ( v3 > 0 && CurrentThreadId == *(_DWORD *)(a1 + 16) )
  {
    result = v3 + 1;
  }
  else
  {
    if ( !(unsigned int)TryAcquireWrite(a1) )
      QueueAcquireWrite(a1);
    *(_DWORD *)(a1 + 16) = CurrentThreadId;
    result = 1;
  }
  *(_QWORD *)(a1 + 8) = result;
  return result;
}

```

## disassembly

```asm
0x180043c74  mov     [rsp+arg_0], rbx
0x180043c79  mov     [rsp+arg_8], rsi
0x180043c7e  push    rdi
0x180043c7f  sub     rsp, 20h
0x180043c83  mov     rdi, rcx
0x180043c86  call    cs:__imp_GetCurrentThreadId
0x180043c8c  mov     ebx, eax
0x180043c8e  mov     rax, [rdi+8]
0x180043c92  test    rax, rax
0x180043c95  jle     short loc_180043CA1
0x180043c97  cmp     ebx, [rdi+10h]
0x180043c9a  jnz     short loc_180043CA1
0x180043c9c  inc     rax
0x180043c9f  jmp     short loc_180043CBD
0x180043ca1  mov     rcx, rdi
0x180043ca4  call    TryAcquireWrite
0x180043ca9  test    eax, eax
0x180043cab  jnz     short loc_180043CB5
0x180043cad  mov     rcx, rdi
0x180043cb0  call    QueueAcquireWrite
0x180043cb5  mov     [rdi+10h], ebx
0x180043cb8  mov     eax, 1
0x180043cbd  mov     [rdi+8], rax
0x180043cc1  mov     rbx, [rsp+28h+arg_0]
0x180043cc6  mov     rsi, [rsp+28h+arg_8]
0x180043ccb  add     rsp, 20h
0x180043ccf  pop     rdi
0x180043cd0  retn
```
