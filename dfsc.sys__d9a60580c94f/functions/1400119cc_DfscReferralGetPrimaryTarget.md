# DfscReferralGetPrimaryTarget

- ea: `0x1400119cc`
- end: `0x1400119f0`
- name: `DfscReferralGetPrimaryTarget`
- size: `36`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140003020`
- `0x1400110d8`
- `0x140011c80`
- `0x140021688`
- `0x140022840`

## callees

- `0x1400119cc`

## pseudocode

```c
__int64 __fastcall DfscReferralGetPrimaryTarget(__int64 a1)
{
  __int64 v1; // rdx
  __int64 result; // rax
  __int64 v3; // rcx

  v1 = *(_QWORD *)(a1 + 16);
  result = 0;
  v3 = *(unsigned __int16 *)(v1 + 26);
  if ( (_WORD)v3 != 0xFFFF )
    return v1 + 112 * v3 + 160;
  return result;
}

```

## disassembly

```asm
0x1400119cc  mov     rdx, [rcx+10h]
0x1400119d0  xor     eax, eax
0x1400119d2  mov     r8d, 0FFFFh
0x1400119d8  movzx   ecx, word ptr [rdx+1Ah]
0x1400119dc  cmp     cx, r8w
0x1400119e0  jz      short locret_1400119EF
0x1400119e2  imul    rax, rcx, 70h ; 'p'
0x1400119e6  add     rax, 0A0h
0x1400119ec  add     rax, rdx
0x1400119ef  retn
```
