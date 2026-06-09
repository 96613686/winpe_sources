# ReadGenericRepeat

- ea: `0x18001a578`
- end: `0x18001a617`
- name: `ReadGenericRepeat`
- size: `159`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180007800`
- `0x180009010`
- `0x180009544`
- `0x180009978`
- `0x18000e214`
- `0x18000e618`
- `0x18000e8f4`
- `0x18000f0f4`
- `0x1800109fc`
- `0x180017f04`
- `0x180018b84`

## callees

- `0x18001a3bc`
- `0x18001a578`

## pseudocode

```c
__int64 __fastcall ReadGenericRepeat(
        __int64 a1,
        __int64 a2,
        unsigned __int8 *a3,
        unsigned int a4,
        _DWORD *a5,
        unsigned __int16 a6,
        unsigned __int16 a7)
{
  unsigned __int16 i; // bx
  __int64 result; // rax
  _WORD v13[36]; // [rsp+30h] [rbp-48h] BYREF

  v13[0] = 0;
  for ( i = 0; i < a6; ++i )
  {
    result = ReadGeneric(a1, a2, a7, a3, a4, v13);
    if ( (_WORD)result )
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
0x18001a578  push    rbx
0x18001a57a  push    rbp
0x18001a57b  push    rsi
0x18001a57c  push    r12
0x18001a57e  push    r14
0x18001a580  push    r15
0x18001a582  sub     rsp, 48h
0x18001a586  xor     r12d, r12d
0x18001a589  mov     esi, r9d
0x18001a58c  mov     [rsp+78h+var_48], r12w
0x18001a592  mov     ebx, r12d
0x18001a595  mov     r14, r8
0x18001a598  mov     rbp, rdx
0x18001a59b  mov     r15, rcx
0x18001a59e  cmp     bx, [rsp+78h+arg_28]
0x18001a5a6  jnb     short loc_18001A5E9
0x18001a5a8  movzx   r8d, [rsp+78h+arg_30]
0x18001a5b1  lea     rax, [rsp+78h+var_48]
0x18001a5b6  mov     [rsp+78h+var_50], rax
0x18001a5bb  mov     r9, r14
0x18001a5be  mov     rdx, rbp
0x18001a5c1  mov     [rsp+78h+var_58], esi
0x18001a5c5  mov     rcx, r15
0x18001a5c8  call    ReadGeneric
0x18001a5cd  test    ax, ax
0x18001a5d0  jnz     short loc_18001A609
0x18001a5d2  movzx   eax, [rsp+78h+var_48]
0x18001a5d7  add     esi, eax
0x18001a5d9  movzx   eax, [rsp+78h+arg_30]
0x18001a5e1  add     rbp, rax
0x18001a5e4  inc     bx
0x18001a5e7  jmp     short loc_18001A59E
0x18001a5e9  movzx   eax, [rsp+78h+arg_30]
0x18001a5f1  movzx   ecx, [rsp+78h+arg_28]
0x18001a5f9  imul    ecx, eax
0x18001a5fc  mov     rax, [rsp+78h+arg_20]
0x18001a604  mov     [rax], ecx
0x18001a606  mov     eax, r12d
0x18001a609  add     rsp, 48h
0x18001a60d  pop     r15
0x18001a60f  pop     r14
0x18001a611  pop     r12
0x18001a613  pop     rsi
0x18001a614  pop     rbp
0x18001a615  pop     rbx
0x18001a616  retn
```
