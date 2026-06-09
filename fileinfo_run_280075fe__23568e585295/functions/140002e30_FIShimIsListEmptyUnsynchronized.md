# FIShimIsListEmptyUnsynchronized

- ea: `0x140002e30`
- end: `0x140002e37`
- name: `FIShimIsListEmptyUnsynchronized`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140013bc0`

## pseudocode

```c
bool __fastcall FIShimIsListEmptyUnsynchronized(_QWORD *a1)
{
  return *a1 == (_QWORD)a1;
}

```

## disassembly

```asm
0x140002e30  cmp     [rcx], rcx
0x140002e33  setz    al
0x140002e36  retn
```
