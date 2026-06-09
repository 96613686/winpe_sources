# SetCancelRoutineSafe

- ea: `0x140019e70`
- end: `0x140019e97`
- name: `SetCancelRoutineSafe`
- size: `39`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140010988`
- `0x140010c58`
- `0x140010fd4`
- `0x140011500`

## callees

- `0x140019e70`

## pseudocode

```c
bool __fastcall SetCancelRoutineSafe(__int64 a1, __int64 a2)
{
  _InterlockedExchange64((volatile __int64 *)(a1 + 104), a2);
  if ( !*(_BYTE *)(a1 + 68) )
  {
    *(_BYTE *)(*(_QWORD *)(a1 + 184) + 3LL) |= 1u;
    return 1;
  }
  return !_InterlockedExchange64((volatile __int64 *)(a1 + 104), 0);
}

```

## disassembly

```asm
0x140019e70  xchg    rdx, [rcx+68h]
0x140019e74  cmp     byte ptr [rcx+44h], 0
0x140019e78  jnz     short loc_140019E89
0x140019e7a  mov     rax, [rcx+0B8h]
0x140019e81  or      byte ptr [rax+3], 1
0x140019e85  mov     al, 1
0x140019e87  retn
0x140019e89  xor     eax, eax
0x140019e8b  xchg    rax, [rcx+68h]
0x140019e8f  test    rax, rax
0x140019e92  jz      short loc_140019E85
0x140019e94  xor     al, al
0x140019e96  retn
```
