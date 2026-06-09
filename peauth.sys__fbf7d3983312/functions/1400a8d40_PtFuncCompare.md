# PtFuncCompare

- ea: `0x1400a8d40`
- end: `0x1400a8d5e`
- name: `PtFuncCompare`
- size: `30`
- prototype: `int __cdecl(void *, const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140026060`

## pseudocode

```c
__int64 __fastcall PtFuncCompare(void *a1, const void *a2, const void *a3)
{
  return sub_140026060(a2, a3, a1);
}

```

## disassembly

```asm
0x1400a8d40  sub     rsp, 28h
0x1400a8d44  mov     rax, r8
0x1400a8d47  mov     r9, rdx
0x1400a8d4a  mov     r8, rcx
0x1400a8d4d  mov     rdx, rax
0x1400a8d50  mov     rcx, r9
0x1400a8d53  call    sub_140026060
0x1400a8d58  add     rsp, 28h
0x1400a8d5c  retn
```
