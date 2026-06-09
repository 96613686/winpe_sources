# ClasspIsOffloadDataTransferCommand

- ea: `0x140007680`
- end: `0x1400076a6`
- name: `ClasspIsOffloadDataTransferCommand`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400077ac`
- `0x1400084b0`

## callees

- `0x140007654`
- `0x140007680`
- `0x140007788`

## pseudocode

```c
char __fastcall ClasspIsOffloadDataTransferCommand(__int64 a1, __int64 a2)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  char result; // al

  if ( (unsigned __int8)ClasspIsTokenOperation(a1, a2, a1) )
    return 1;
  result = ClasspIsReceiveTokenInformation(v3, v2, v3);
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x140007680  sub     rsp, 28h
0x140007684  mov     r8, rcx
0x140007687  call    ClasspIsTokenOperation
0x14000768c  test    al, al
0x14000768e  jnz     short loc_1400076A2
0x140007690  mov     rcx, r8
0x140007693  call    ClasspIsReceiveTokenInformation
0x140007698  test    al, al
0x14000769a  jnz     short loc_1400076A2
0x14000769c  add     rsp, 28h
0x1400076a0  retn
0x1400076a2  mov     al, 1
0x1400076a4  jmp     short loc_14000769C
```
