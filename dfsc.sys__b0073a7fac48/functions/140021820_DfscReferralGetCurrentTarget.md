# DfscReferralGetCurrentTarget

- ea: `0x140021820`
- end: `0x140021844`
- name: `DfscReferralGetCurrentTarget`
- size: `36`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1400110d8`
- `0x140011c80`
- `0x140016070`
- `0x140018d44`
- `0x1400191d0`
- `0x140021410`
- `0x140021688`
- `0x14002184c`
- `0x1400281ac`

## callees

- `0x140021820`

## pseudocode

```c
__int64 __fastcall DfscReferralGetCurrentTarget(__int64 a1)
{
  __int64 v1; // rax

  v1 = *(unsigned __int16 *)(a1 + 32);
  if ( (_WORD)v1 == 0xFFFF )
    return 0;
  else
    return 112 * v1 + *(_QWORD *)(a1 + 16) + 160LL;
}

```

## disassembly

```asm
0x140021820  movzx   eax, word ptr [rcx+20h]
0x140021824  mov     edx, 0FFFFh
0x140021829  cmp     ax, dx
0x14002182c  jz      short loc_140021841
0x14002182e  imul    r8, rax, 70h ; 'p'
0x140021832  mov     rax, [rcx+10h]
0x140021836  add     rax, 0A0h
0x14002183c  add     rax, r8
0x14002183f  retn
0x140021841  xor     eax, eax
0x140021843  retn
```
