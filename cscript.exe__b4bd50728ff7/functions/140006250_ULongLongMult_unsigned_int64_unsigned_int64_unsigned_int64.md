# ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)

- ea: `0x140006250`
- end: `0x14000627c`
- name: `?ULongLongMult@@YAJ_K0PEA_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400028b0`
- `0x140002a70`
- `0x140003160`
- `0x140005f10`

## callees

- `0x140006250`

## pseudocode

```c
__int64 __fastcall ULongLongMult(unsigned __int64 a1, __int64 a2, unsigned __int64 *a3)
{
  __int64 v4; // rcx
  __int64 result; // rax

  v4 = 2 * a1;
  if ( is_mul_ok(a1, 2u) )
  {
    result = 0;
    *a3 = v4;
  }
  else
  {
    *a3 = -1;
    return 2147942934LL;
  }
  return result;
}

```

## disassembly

```asm
0x140006250  mov     eax, 2
0x140006255  mov     [rsp+arg_8], 0
0x14000625e  mul     rcx
0x140006261  mov     rcx, rax
0x140006264  test    rdx, rdx
0x140006267  jnz     short loc_14000626F
0x140006269  xor     eax, eax
0x14000626b  mov     [r8], rcx
0x14000626e  retn
0x14000626f  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x140006276  mov     eax, 80070216h
0x14000627b  retn
```
