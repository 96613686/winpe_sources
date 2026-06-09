# ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)

- ea: `0x180007010`
- end: `0x180007038`
- name: `?ULongLongMult@@YAJ_K0PEA_K@Z`
- size: `40`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, unsigned __int64 *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800033c0`
- `0x180007770`
- `0x180008660`
- `0x180009e80`
- `0x18000a208`
- `0x18000aa1c`
- `0x18000ad40`
- `0x18000b0e0`

## callees

- `0x180007010`

## pseudocode

```c
__int64 __fastcall ULongLongMult(unsigned __int64 a1, unsigned __int64 a2, unsigned __int64 *a3)
{
  unsigned __int64 v4; // rcx
  __int64 result; // rax

  v4 = a1 * a2;
  if ( is_mul_ok(a1, a2) )
  {
    result = 0;
  }
  else
  {
    result = 2147942934LL;
    v4 = -1;
  }
  *a3 = v4;
  return result;
}

```

## disassembly

```asm
0x180007010  mov     rax, rdx
0x180007013  mov     [rsp+arg_18], 0
0x18000701c  mul     rcx
0x18000701f  mov     rcx, rax
0x180007022  test    rdx, rdx
0x180007025  jnz     short loc_18000702B
0x180007027  xor     eax, eax
0x180007029  jmp     short loc_180007034
0x18000702b  mov     eax, 80070216h
0x180007030  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180007034  mov     [r8], rcx
0x180007037  retn
```
