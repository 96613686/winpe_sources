# OpenTSObject

- ea: `0x180003730`
- end: `0x180003777`
- name: `OpenTSObject`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003730`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180003757`
- `KERNEL32!HeapAlloc` at `0x180003757`

## pseudocode

```c
__int64 OpenTSObject()
{
  ++dword_180012ABC;
  if ( pProcessBuffer )
    return 0;
  pProcessBuffer = HeapAlloc(hLibHeap, 8u, dwBytes);
  return pProcessBuffer == 0 ? 0xE : 0;
}

```

## disassembly

```asm
0x180003730  sub     rsp, 28h
0x180003734  inc     cs:dword_180012ABC
0x18000373a  cmp     cs:pProcessBuffer, 0
0x180003742  jnz     short loc_180003770
0x180003744  mov     r8d, cs:dwBytes; dwBytes
0x18000374b  mov     edx, 8; dwFlags
0x180003750  mov     rcx, cs:hLibHeap; hHeap
0x180003757  call    cs:__imp_HeapAlloc
0x18000375d  mov     cs:pProcessBuffer, rax
0x180003764  neg     rax
0x180003767  sbb     eax, eax
0x180003769  not     eax
0x18000376b  and     eax, 0Eh
0x18000376e  jmp     short loc_180003772
0x180003770  xor     eax, eax
0x180003772  add     rsp, 28h
0x180003776  retn
```
