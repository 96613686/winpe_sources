# WriteGenericRepeat

- ea: `0x18001a9c0`
- end: `0x18001aa5f`
- name: `WriteGenericRepeat`
- size: `159`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800079b8`
- `0x180009010`
- `0x180009978`
- `0x18000acf4`
- `0x180010fd4`
- `0x180013364`
- `0x180013c38`
- `0x180013ee0`

## callees

- `0x18001a808`
- `0x18001a9c0`

## pseudocode

```c
__int16 __fastcall WriteGenericRepeat(
        __int64 a1,
        __int64 a2,
        unsigned __int8 *a3,
        unsigned int a4,
        _DWORD *a5,
        unsigned __int16 a6,
        unsigned __int16 a7)
{
  unsigned __int16 i; // bx
  __int16 result; // ax
  _WORD v13[36]; // [rsp+30h] [rbp-48h] BYREF

  v13[0] = 0;
  for ( i = 0; i < a6; ++i )
  {
    result = WriteGeneric(a1, a2, a7, a3, a4, v13);
    if ( result )
      return result;
    a4 += v13[0];
    a2 += a7;
  }
  *a5 = a7 * a6;
  return 0;
}

```

## disassembly

```asm
0x18001a9c0  push    rbx
0x18001a9c2  push    rbp
0x18001a9c3  push    rsi
0x18001a9c4  push    r12
0x18001a9c6  push    r14
0x18001a9c8  push    r15
0x18001a9ca  sub     rsp, 48h
0x18001a9ce  xor     r12d, r12d
0x18001a9d1  mov     esi, r9d
0x18001a9d4  mov     [rsp+78h+var_48], r12w
0x18001a9da  mov     ebx, r12d
0x18001a9dd  mov     r14, r8
0x18001a9e0  mov     rbp, rdx
0x18001a9e3  mov     r15, rcx
0x18001a9e6  cmp     bx, [rsp+78h+arg_28]
0x18001a9ee  jnb     short loc_18001AA31
0x18001a9f0  movzx   r8d, [rsp+78h+arg_30]
0x18001a9f9  lea     rax, [rsp+78h+var_48]
0x18001a9fe  mov     [rsp+78h+var_50], rax
0x18001aa03  mov     r9, r14
0x18001aa06  mov     rdx, rbp
0x18001aa09  mov     [rsp+78h+var_58], esi
0x18001aa0d  mov     rcx, r15
0x18001aa10  call    WriteGeneric
0x18001aa15  test    ax, ax
0x18001aa18  jnz     short loc_18001AA51
0x18001aa1a  movzx   eax, [rsp+78h+var_48]
0x18001aa1f  add     esi, eax
0x18001aa21  movzx   eax, [rsp+78h+arg_30]
0x18001aa29  add     rbp, rax
0x18001aa2c  inc     bx
0x18001aa2f  jmp     short loc_18001A9E6
0x18001aa31  movzx   eax, [rsp+78h+arg_30]
0x18001aa39  movzx   ecx, [rsp+78h+arg_28]
0x18001aa41  imul    ecx, eax
0x18001aa44  mov     rax, [rsp+78h+arg_20]
0x18001aa4c  mov     [rax], ecx
0x18001aa4e  mov     eax, r12d
0x18001aa51  add     rsp, 48h
0x18001aa55  pop     r15
0x18001aa57  pop     r14
0x18001aa59  pop     r12
0x18001aa5b  pop     rsi
0x18001aa5c  pop     rbp
0x18001aa5d  pop     rbx
0x18001aa5e  retn
```
