# ReadCmapFormat0

- ea: `0x18000f0f4`
- end: `0x18000f190`
- name: `ReadCmapFormat0`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800143f0`

## callees

- `0x18000db8c`
- `0x18000f0f4`
- `0x18001a3bc`
- `0x18001a578`

## pseudocode

```c
__int64 __fastcall ReadCmapFormat0(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _WORD *a5)
{
  unsigned int CmapSubtable; // esi
  __int64 result; // rax
  _WORD v8[2]; // [rsp+40h] [rbp-38h] BYREF
  _DWORD v9[13]; // [rsp+44h] [rbp-34h] BYREF

  v8[0] = 0;
  v9[0] = 0;
  CmapSubtable = FindCmapSubtable();
  if ( !CmapSubtable )
    return 1006;
  result = ReadGeneric(a1, (__int64)a5, 6u, (unsigned __int8 *)&CMAP_FORMAT0_CONTROL, CmapSubtable, v8);
  if ( (_WORD)result )
    return result;
  if ( *a5 )
    return 1006;
  else
    return ReadGenericRepeat(
             a1,
             (__int64)(a5 + 3),
             (unsigned __int8 *)BYTE_CONTROL,
             CmapSubtable + v8[0],
             v9,
             0x100u,
             1u);
}

```

## disassembly

```asm
0x18000f0f4  push    rbx
0x18000f0f6  push    rbp
0x18000f0f7  push    rsi
0x18000f0f8  push    rdi
0x18000f0f9  sub     rsp, 58h
0x18000f0fd  xor     ebp, ebp
0x18000f0ff  mov     rdi, rcx
0x18000f102  mov     [rsp+78h+var_38], bp
0x18000f107  mov     [rsp+78h+var_34], ebp
0x18000f10b  call    FindCmapSubtable
0x18000f110  mov     esi, eax
0x18000f112  test    eax, eax
0x18000f114  jz      short loc_18000F182
0x18000f116  mov     rbx, [rsp+78h+arg_20]
0x18000f11e  lea     rax, [rsp+78h+var_38]
0x18000f123  mov     [rsp+78h+var_50], rax
0x18000f128  lea     r8d, [rbp+6]
0x18000f12c  mov     rdx, rbx
0x18000f12f  mov     dword ptr [rsp+78h+var_58], esi
0x18000f133  lea     r9, CMAP_FORMAT0_CONTROL
0x18000f13a  mov     rcx, rdi
0x18000f13d  call    ReadGeneric
0x18000f142  test    ax, ax
0x18000f145  jnz     short loc_18000F187
0x18000f147  cmp     [rbx], bp
0x18000f14a  jnz     short loc_18000F182
0x18000f14c  movzx   r9d, [rsp+78h+var_38]
0x18000f152  lea     rax, [rsp+78h+var_34]
0x18000f157  mov     [rsp+78h+var_48], 1
0x18000f15e  lea     rdx, [rbx+6]
0x18000f162  add     r9d, esi
0x18000f165  mov     word ptr [rsp+78h+var_50], 100h
0x18000f16c  lea     r8, BYTE_CONTROL
0x18000f173  mov     [rsp+78h+var_58], rax
0x18000f178  mov     rcx, rdi
0x18000f17b  call    ReadGenericRepeat
0x18000f180  jmp     short loc_18000F187
0x18000f182  mov     eax, 3EEh
0x18000f187  add     rsp, 58h
0x18000f18b  pop     rdi
0x18000f18c  pop     rsi
0x18000f18d  pop     rbp
0x18000f18e  pop     rbx
0x18000f18f  retn
```
