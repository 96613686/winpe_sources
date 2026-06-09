# TupleVariationInterpolator::ComputeTupleScalar(array_ref<float const>,OpenTypeShortFrac const *,OpenTypeShortFrac const *,ushort)

- ea: `0x140045540`
- end: `0x1400456b4`
- name: `?ComputeTupleScalar@TupleVariationInterpolator@@SAMV?$array_ref@$$CBM@@PEBUOpenTypeShortFrac@@1G@Z`
- size: `372`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140044e14`
- `0x140045194`

## callees

- `0x140045540`

## pseudocode

```c
__m128 __fastcall TupleVariationInterpolator::ComputeTupleScalar(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4)
{
  __int128 v4; // xmm5
  unsigned __int16 i; // r10
  float v7; // xmm2_4
  float v8; // xmm0_4
  float v9; // xmm4_4
  char v10; // al
  char v11; // cl
  float v12; // xmm1_4
  float v14; // xmm1_4

  v4 = LODWORD(FLOAT_1_0);
  for ( i = 0; i < a4; ++i )
  {
    v7 = (float)(__int16)_byteswap_ushort(*(_WORD *)(a2 + 2LL * i)) * 0.000061035156;
    if ( a3 )
    {
      v8 = (float)(__int16)_byteswap_ushort(*(_WORD *)(a3 + 2LL * i)) * 0.000061035156;
      v9 = (float)(__int16)_byteswap_ushort(*(_WORD *)(a3 + 2LL * (unsigned __int16)(a4 + i))) * 0.000061035156;
    }
    else
    {
      v9 = 0.0;
      v8 = 0.0;
    }
    v10 = v7 >= 0.0;
    if ( v8 < 0.0 )
    {
      v11 = 0;
    }
    else
    {
      v11 = v7 >= 0.0;
      if ( v8 > 0.0 )
        v11 = 1;
    }
    if ( v9 < 0.0 )
    {
      v10 = 0;
    }
    else if ( v9 > 0.0 )
    {
      v10 = 1;
    }
    if ( v7 != 0.0 && (!a3 || v11 == v10 && v7 >= v8 && v9 >= v7) )
    {
      v12 = *(float *)(*a1 + 4LL * i);
      if ( v12 == 0.0 )
        return (__m128)0LL;
      if ( a3 )
      {
        if ( v12 < v8 || v9 < v12 )
          return (__m128)0LL;
        if ( v7 > v12 )
        {
          v12 = v12 - v8;
          v7 = v7 - v8;
          goto LABEL_23;
        }
        if ( v12 > v7 )
          v14 = (float)(v9 - v12) / (float)(v9 - v7);
        else
          v14 = FLOAT_1_0;
      }
      else
      {
        if ( v12 < 0.0 && v7 > v12 || v12 > 0.0 && v12 > v7 )
          return (__m128)0LL;
LABEL_23:
        v14 = v12 / v7;
      }
      *(float *)&v4 = *(float *)&v4 * v14;
      continue;
    }
  }
  return (__m128)v4;
}

```

## disassembly

```asm
0x140045540  push    rbx
0x140045542  push    rsi
0x140045543  push    rdi
0x140045544  movss   xmm5, cs:__real@3f800000
0x14004554c  xor     r10d, r10d
0x14004554f  mov     r11, r8
0x140045552  mov     rbx, rdx
0x140045555  mov     rdi, rcx
0x140045558  xorps   xmm3, xmm3
0x14004555b  lea     esi, [r10+1]
0x14004555f  cmp     r10w, r9w
0x140045563  jnb     loc_140045632
0x140045569  movzx   r8d, r10w
0x14004556d  movzx   eax, byte ptr [rbx+r8*2]
0x140045572  movzx   ecx, byte ptr [rbx+r8*2+1]
0x140045578  shl     ax, 8
0x14004557c  or      ax, cx
0x14004557f  cwde
0x140045580  movd    xmm2, eax
0x140045584  cvtdq2ps xmm2, xmm2
0x140045587  mulss   xmm2, cs:__real@38800000
0x14004558f  test    r11, r11
0x140045592  jz      loc_140045662
0x140045598  movzx   ecx, byte ptr [r11+r8*2]
0x14004559d  movzx   eax, byte ptr [r11+r8*2+1]
0x1400455a3  shl     cx, 8
0x1400455a7  or      ax, cx
0x1400455aa  cwde
0x1400455ab  movd    xmm0, eax
0x1400455af  lea     eax, [r9+r10]
0x1400455b3  movzx   ecx, ax
0x1400455b6  cvtdq2ps xmm0, xmm0
0x1400455b9  movzx   eax, byte ptr [r11+rcx*2]
0x1400455be  movzx   edx, byte ptr [r11+rcx*2+1]
0x1400455c4  shl     ax, 8
0x1400455c8  mulss   xmm0, cs:__real@38800000
0x1400455d0  or      ax, dx
0x1400455d3  cwde
0x1400455d4  movd    xmm4, eax
0x1400455d8  cvtdq2ps xmm4, xmm4
0x1400455db  mulss   xmm4, cs:__real@38800000
0x1400455e3  comiss  xmm2, xmm3
0x1400455e6  setnb   al
0x1400455e9  comiss  xmm3, xmm0
0x1400455ec  ja      short loc_14004565E
0x1400455ee  comiss  xmm0, xmm3
0x1400455f1  movzx   ecx, al
0x1400455f4  cmova   ecx, esi
0x1400455f7  comiss  xmm3, xmm4
0x1400455fa  ja      short loc_14004566D
0x1400455fc  comiss  xmm4, xmm3
0x1400455ff  movzx   eax, al
0x140045602  cmova   eax, esi
0x140045605  ucomiss xmm2, xmm3
0x140045608  jp      short loc_14004560C
0x14004560a  jz      short loc_140045655
0x14004560c  test    r11, r11
0x14004560f  jz      short loc_14004561F
0x140045611  cmp     cl, al
0x140045613  jnz     short loc_140045655
0x140045615  comiss  xmm2, xmm0
0x140045618  jb      short loc_140045655
0x14004561a  comiss  xmm4, xmm2
0x14004561d  jb      short loc_140045655
0x14004561f  mov     rax, [rdi]
0x140045622  movss   xmm1, dword ptr [rax+r8*4]
0x140045628  ucomiss xmm1, xmm3
0x14004562b  jp      short loc_140045639
0x14004562d  jnz     short loc_140045639
0x14004562f  movaps  xmm5, xmm3
0x140045632  movaps  xmm0, xmm5
0x140045635  pop     rdi
0x140045636  pop     rsi
0x140045637  pop     rbx
0x140045638  retn
0x140045639  test    r11, r11
0x14004563c  jnz     short loc_140045678
0x14004563e  comiss  xmm3, xmm1
0x140045641  ja      short loc_140045671
0x140045643  comiss  xmm1, xmm3
0x140045646  jbe     short loc_14004564D
0x140045648  comiss  xmm1, xmm2
0x14004564b  ja      short loc_14004562F
0x14004564d  divss   xmm1, xmm2
0x140045651  mulss   xmm5, xmm1
0x140045655  add     r10w, si
0x140045659  jmp     loc_14004555F
0x14004565e  xor     cl, cl
0x140045660  jmp     short loc_1400455F7
0x140045662  movaps  xmm4, xmm3
0x140045665  movaps  xmm0, xmm3
0x140045668  jmp     loc_1400455E3
0x14004566d  xor     al, al
0x14004566f  jmp     short loc_140045605
0x140045671  comiss  xmm2, xmm1
0x140045674  ja      short loc_14004562F
0x140045676  jmp     short loc_140045643
0x140045678  comiss  xmm1, xmm0
0x14004567b  jb      short loc_14004562F
0x14004567d  comiss  xmm4, xmm1
0x140045680  jb      short loc_14004562F
0x140045682  comiss  xmm2, xmm1
0x140045685  ja      short loc_140045696
0x140045687  comiss  xmm1, xmm2
0x14004568a  ja      short loc_1400456A0
0x14004568c  movss   xmm1, cs:__real@3f800000
0x140045694  jmp     short loc_140045651
0x140045696  subss   xmm1, xmm0
0x14004569a  subss   xmm2, xmm0
0x14004569e  jmp     short loc_14004564D
0x1400456a0  movaps  xmm0, xmm4
0x1400456a3  subss   xmm4, xmm2
0x1400456a7  subss   xmm0, xmm1
0x1400456ab  movaps  xmm1, xmm0
0x1400456ae  divss   xmm1, xmm4
0x1400456b2  jmp     short loc_140045651
```
