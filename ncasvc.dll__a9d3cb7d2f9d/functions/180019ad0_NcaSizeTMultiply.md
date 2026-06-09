# NcaSizeTMultiply

- ea: `0x180019ad0`
- end: `0x180019afa`
- name: `NcaSizeTMultiply`
- size: `42`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, _QWORD *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180019178`
- `0x180019b04`
- `0x180019c70`
- `0x18001ac28`
- `0x18001ac78`
- `0x18001c03c`

## callees

- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall NcaSizeTMultiply(unsigned __int64 a1, unsigned __int64 a2, _QWORD *a3)
{
  *a3 = a2 * a1;
  if ( a2 && a1 > 0xFFFFFFFFFFFFFFFFuLL / a2 )
    return 2147942934LL;
  else
    return 0;
}

```

## disassembly

```asm
0x180019ad0  mov     rax, rcx
0x180019ad3  mov     r9, rdx
0x180019ad6  imul    rax, rdx
0x180019ada  mov     [r8], rax
0x180019add  test    rdx, rdx
0x180019ae0  jz      short loc_180019AF7
0x180019ae2  xor     edx, edx
0x180019ae4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019ae8  div     r9
0x180019aeb  cmp     rcx, rax
0x180019aee  jbe     short loc_180019AF7
0x180019af0  mov     eax, 80070216h
0x180019af5  retn
0x180019af7  xor     eax, eax
0x180019af9  retn
```
