# ULongSub(ulong,ulong,ulong *)

- ea: `0x18000bcb8`
- end: `0x18000bcd5`
- name: `?ULongSub@@YAJKKPEAK@Z`
- size: `29`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002510`
- `0x1800054f0`
- `0x18000b7ec`
- `0x18000c21c`
- `0x180011714`
- `0x180014df0`

## callees

- `0x18000bcb8`

## pseudocode

```c
__int64 __fastcall ULongSub(unsigned int a1, unsigned int a2, unsigned int *a3)
{
  unsigned int v3; // r9d

  if ( a1 < a2 )
    v3 = -1;
  else
    v3 = a1 - a2;
  *a3 = v3;
  return a1 < a2 ? 0x80070216 : 0;
}

```

## disassembly

```asm
0x18000bcb8  cmp     ecx, edx
0x18000bcba  jb      short loc_18000BCC4
0x18000bcbc  mov     r9d, ecx
0x18000bcbf  sub     r9d, edx
0x18000bcc2  jmp     short loc_18000BCC8
0x18000bcc4  or      r9d, 0FFFFFFFFh
0x18000bcc8  cmp     ecx, edx
0x18000bcca  mov     [r8], r9d
0x18000bccd  sbb     eax, eax
0x18000bccf  and     eax, 80070216h
0x18000bcd4  retn
```
