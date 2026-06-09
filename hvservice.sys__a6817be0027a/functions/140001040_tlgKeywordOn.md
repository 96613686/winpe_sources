# _tlgKeywordOn

- ea: `0x140001040`
- end: `0x140001067`
- name: `_tlgKeywordOn`
- size: `39`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140001600`
- `0x140012658`
- `0x140013510`
- `0x140013a60`
- `0x140013c34`

## callees

- `0x140001040`

## pseudocode

```c
bool __fastcall tlgKeywordOn(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  bool result; // al

  result = 1;
  if ( a2 )
  {
    v3 = *(_QWORD *)(a1 + 24);
    if ( (*(_QWORD *)(a1 + 16) & a2) == 0 || (a2 & v3) != v3 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140001040  mov     rax, rcx
0x140001043  test    rdx, rdx
0x140001046  jz      short loc_140001060
0x140001048  mov     rcx, [rcx+18h]
0x14000104c  mov     rax, [rax+10h]
0x140001050  test    rdx, rax
0x140001053  jz      short loc_140001064
0x140001055  mov     rax, rcx
0x140001058  and     rax, rdx
0x14000105b  cmp     rax, rcx
0x14000105e  jnz     short loc_140001064
0x140001060  mov     al, 1
0x140001062  retn
0x140001064  xor     al, al
0x140001066  retn
```
