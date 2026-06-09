# CCabItemList::GetCount(void)

- ea: `0x18000b884`
- end: `0x18000b8a1`
- name: `?GetCount@CCabItemList@@QEAAIXZ`
- size: `29`
- prototype: `unsigned int __fastcall(CCabItemList *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ba40`
- `0x18000bfa4`
- `0x18000cc80`
- `0x18000d130`
- `0x18000f000`
- `0x180010440`

## callees

- `0x18000b884`
- `0x18000e848`

## pseudocode

```c
__int64 __fastcall CCabItemList::GetCount(CCabItemList *this)
{
  __int64 v1; // rcx

  if ( CCabItemList::GetState(this) == 1 )
    return **(unsigned int **)(v1 + 8);
  else
    return 0;
}

```

## disassembly

```asm
0x18000b884  sub     rsp, 28h
0x18000b888  call    ?GetState@CCabItemList@@QEAAIXZ; CCabItemList::GetState(void)
0x18000b88d  cmp     eax, 1
0x18000b890  jnz     short loc_18000B89A
0x18000b892  mov     rax, [rcx+8]
0x18000b896  mov     eax, [rax]
0x18000b898  jmp     short loc_18000B89C
0x18000b89a  xor     eax, eax
0x18000b89c  add     rsp, 28h
0x18000b8a0  retn
```
