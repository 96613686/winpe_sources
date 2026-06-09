# CdDevCtrlCompletionRoutine

- ea: `0x140001ad0`
- end: `0x140001ae4`
- name: `CdDevCtrlCompletionRoutine`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001ad0`

## pseudocode

```c
__int64 __fastcall CdDevCtrlCompletionRoutine(__int64 a1, __int64 a2)
{
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  return 0;
}

```

## disassembly

```asm
0x140001ad0  cmp     byte ptr [rdx+41h], 0
0x140001ad4  jz      short loc_140001AE1
0x140001ad6  mov     rax, [rdx+0B8h]
0x140001add  or      byte ptr [rax+3], 1
0x140001ae1  xor     eax, eax
0x140001ae3  retn
```
