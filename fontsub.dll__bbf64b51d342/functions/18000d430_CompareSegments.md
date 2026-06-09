# CompareSegments

- ea: `0x18000d430`
- end: `0x18000d455`
- name: `CompareSegments`
- size: `37`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d430`

## pseudocode

```c
__int64 __fastcall CompareSegments(_WORD *a1, _WORD *a2)
{
  if ( *a1 > *a2 || a1[1] < a2[1] )
    return a1[1] < a2[1] ? -1 : 1;
  else
    return 0;
}

```

## disassembly

```asm
0x18000d430  movzx   eax, word ptr [rdx]
0x18000d433  cmp     [rcx], ax
0x18000d436  ja      short loc_18000D445
0x18000d438  movzx   eax, word ptr [rdx+2]
0x18000d43c  cmp     [rcx+2], ax
0x18000d440  jb      short loc_18000D445
0x18000d442  xor     eax, eax
0x18000d444  retn
0x18000d445  movzx   eax, word ptr [rdx+2]
0x18000d449  cmp     [rcx+2], ax
0x18000d44d  sbb     eax, eax
0x18000d44f  and     eax, 0FFFFFFFEh
0x18000d452  inc     eax
0x18000d454  retn
```
