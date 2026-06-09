# RdpBoundsAccumulator::IntersectsBA(IRdpBoundsAccumulator const *,uint *,float *)

- ea: `0x18001be70`
- end: `0x18001c07f`
- name: `?IntersectsBA@RdpBoundsAccumulator@@UEBAJPEBVIRdpBoundsAccumulator@@PEAIPEAM@Z`
- size: `527`
- prototype: `__int64 __fastcall(RdpBoundsAccumulator *__hidden this, const struct IRdpBoundsAccumulator *, unsigned int *, float *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x18001baa0`
- `0x18001be70`
- `0x18001cc98`
- `0x18001d098`
- `0x18001d114`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x18001bf4a`: `UpdateRectsIter failed`

## pseudocode

```c
__int64 __fastcall RdpBoundsAccumulator::IntersectsBA(
        RdpBoundsAccumulator *this,
        const struct IRdpBoundsAccumulator *a2,
        unsigned int *a3,
        float *a4)
{
  int v8; // eax
  int updated; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  int ActivityIdPrefix; // eax
  unsigned int v13; // ebp
  unsigned int i; // r13d
  unsigned int v15; // r12d
  __m128i v16; // xmm6
  __int128 v18; // [rsp+30h] [rbp-78h] BYREF
  __m128i j; // [rsp+40h] [rbp-68h] BYREF

  j = 0;
  v18 = 0;
  if ( a2 )
  {
    *a3 = 0;
    *a4 = 0.0;
    updated = RdpBoundsAccumulator::UpdateRectsIter(this);
    if ( updated >= 0 )
    {
      v13 = 0;
      for ( i = (*(__int64 (__fastcall **)(const struct IRdpBoundsAccumulator *))(*(_QWORD *)a2 + 176LL))(a2);
            v13 < *((_DWORD *)this + 20);
            *a4 = (float)((_mm_cvtsi128_si32(_mm_srli_si128(v16, 8)) - _mm_cvtsi128_si32(v16))
                        * (_mm_cvtsi128_si32(_mm_srli_si128(v16, 12)) - _mm_cvtsi128_si32(_mm_srli_si128(v16, 4))))
                + *a4 )
      {
        v15 = 0;
        v16 = *(__m128i *)(*((_QWORD *)this + 9) + 16LL * v13);
        for ( j = v16; v15 < i; *a3 += (DWORD2(v18) - v18) * (HIDWORD(v18) - DWORD1(v18)) )
        {
          (*(void (__fastcall **)(const struct IRdpBoundsAccumulator *, _QWORD, __int128 *))(*(_QWORD *)a2 + 184LL))(
            a2,
            v15,
            &v18);
          RdpRect::Intersect((RdpRect *)&v18, (const struct RdpRect *)&j);
          ++v15;
        }
        ++v13;
      }
      *a4 = (float)((float)(int)*a3 * 100.0) / *a4;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, WPP_GLOBAL_Control, v10, v11);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        (unsigned int)WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids,
        ActivityIdPrefix,
        (__int64)"UpdateRectsIter failed",
        updated);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, 0, a3, a4);
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids,
        v8,
        (__int64)"pOther");
    }
    return (unsigned int)-2147467261;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18001be70  push    rbx
0x18001be72  push    rbp
0x18001be73  push    rsi
0x18001be74  push    rdi
0x18001be75  push    r12
0x18001be77  push    r13
0x18001be79  push    r14
0x18001be7b  push    r15
0x18001be7d  sub     rsp, 68h
0x18001be81  movaps  [rsp+0A8h+var_58], xmm6
0x18001be86  xorps   xmm0, xmm0
0x18001be89  xorps   xmm1, xmm1
0x18001be8c  mov     rdi, r9
0x18001be8f  mov     r14, r8
0x18001be92  mov     r15, rdx
0x18001be95  mov     rsi, rcx
0x18001be98  movdqu  [rsp+0A8h+var_68], xmm0
0x18001be9e  movdqu  [rsp+0A8h+var_78], xmm1
0x18001bea4  test    rdx, rdx
0x18001bea7  jnz     short loc_18001BF01
0x18001bea9  mov     rax, cs:WPP_GLOBAL_Control
0x18001beb0  lea     rcx, WPP_GLOBAL_Control
0x18001beb7  cmp     rax, rcx
0x18001beba  jz      short loc_18001BEF7
0x18001bebc  test    byte ptr [rax+1Ch], 8
0x18001bec0  jz      short loc_18001BEF7
0x18001bec2  cmp     byte ptr [rax+19h], 2
0x18001bec6  jb      short loc_18001BEF7
0x18001bec8  call    RdpX_GetActivityIdPrefix
0x18001becd  lea     rcx, aPother; "pOther"
0x18001bed4  mov     r9d, eax
0x18001bed7  mov     [rsp+0A8h+var_88], rcx
0x18001bedc  lea     edx, [r15+2Ah]
0x18001bee0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bee7  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001beee  mov     rcx, [rcx+10h]
0x18001bef2  call    WPP_SF_Ds
0x18001bef7  mov     ebx, 80004003h
0x18001befc  jmp     loc_18001C067
0x18001bf01  mov     dword ptr [r8], 0
0x18001bf08  mov     dword ptr [r9], 0
0x18001bf0f  call    ?UpdateRectsIter@RdpBoundsAccumulator@@AEBAJXZ; RdpBoundsAccumulator::UpdateRectsIter(void)
0x18001bf14  mov     ebx, eax
0x18001bf16  test    eax, eax
0x18001bf18  jns     short loc_18001BF7E
0x18001bf1a  mov     rdx, cs:WPP_GLOBAL_Control
0x18001bf21  lea     rcx, WPP_GLOBAL_Control
0x18001bf28  cmp     rdx, rcx
0x18001bf2b  jz      loc_18001C067
0x18001bf31  test    byte ptr [rdx+1Ch], 8
0x18001bf35  jz      loc_18001C067
0x18001bf3b  cmp     byte ptr [rdx+19h], 2
0x18001bf3f  jb      loc_18001C067
0x18001bf45  call    RdpX_GetActivityIdPrefix
0x18001bf4a  lea     rcx, aUpdaterectsite; "UpdateRectsIter failed"
0x18001bf51  mov     [rsp+0A8h+var_80], ebx
0x18001bf55  mov     [rsp+0A8h+var_88], rcx
0x18001bf5a  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001bf61  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf68  mov     edx, 2Bh ; '+'
0x18001bf6d  mov     r9d, eax
0x18001bf70  mov     rcx, [rcx+10h]
0x18001bf74  call    WPP_SF_DsD
0x18001bf79  jmp     loc_18001C067
0x18001bf7e  mov     rax, [r15]
0x18001bf81  mov     rcx, r15
0x18001bf84  mov     rax, [rax+0B0h]
0x18001bf8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf90  xor     ebp, ebp
0x18001bf92  mov     r13d, eax
0x18001bf95  cmp     [rsi+50h], ebp
0x18001bf98  jbe     loc_18001C04C
0x18001bf9e  mov     rax, [rsi+48h]
0x18001bfa2  xor     r12d, r12d
0x18001bfa5  mov     ecx, ebp
0x18001bfa7  add     rcx, rcx
0x18001bfaa  movups  xmm6, xmmword ptr [rax+rcx*8]
0x18001bfae  movdqu  [rsp+0A8h+var_68], xmm6
0x18001bfb4  test    r13d, r13d
0x18001bfb7  jz      short loc_18001C000
0x18001bfb9  mov     rax, [r15]
0x18001bfbc  lea     r8, [rsp+0A8h+var_78]
0x18001bfc1  mov     edx, r12d
0x18001bfc4  mov     rcx, r15
0x18001bfc7  mov     rax, [rax+0B8h]
0x18001bfce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfd3  lea     rdx, [rsp+0A8h+var_68]; struct RdpRect *
0x18001bfd8  lea     rcx, [rsp+0A8h+var_78]; this
0x18001bfdd  call    ?Intersect@RdpRect@@QEAA_NAEBU1@@Z; RdpRect::Intersect(RdpRect const &)
0x18001bfe2  mov     eax, dword ptr [rsp+0A8h+var_78+8]
0x18001bfe6  inc     r12d
0x18001bfe9  sub     eax, dword ptr [rsp+0A8h+var_78]
0x18001bfed  mov     ecx, dword ptr [rsp+0A8h+var_78+0Ch]
0x18001bff1  sub     ecx, dword ptr [rsp+0A8h+var_78+4]
0x18001bff5  imul    ecx, eax
0x18001bff8  add     [r14], ecx
0x18001bffb  cmp     r12d, r13d
0x18001bffe  jb      short loc_18001BFB9
0x18001c000  movdqa  xmm0, xmm6
0x18001c004  movdqa  xmm1, xmm6
0x18001c008  psrldq  xmm0, 0Ch
0x18001c00d  inc     ebp
0x18001c00f  movd    edx, xmm0
0x18001c013  movdqa  xmm0, xmm6
0x18001c017  psrldq  xmm0, 8
0x18001c01c  movd    ecx, xmm0
0x18001c020  psrldq  xmm1, 4
0x18001c025  movd    eax, xmm1
0x18001c029  sub     edx, eax
0x18001c02b  movd    eax, xmm6
0x18001c02f  sub     ecx, eax
0x18001c031  imul    edx, ecx
0x18001c034  movd    xmm0, edx
0x18001c038  cvtdq2ps xmm0, xmm0
0x18001c03b  addss   xmm0, dword ptr [rdi]
0x18001c03f  movss   dword ptr [rdi], xmm0
0x18001c043  cmp     ebp, [rsi+50h]
0x18001c046  jb      loc_18001BF9E
0x18001c04c  mov     eax, [r14]
0x18001c04f  xorps   xmm0, xmm0
0x18001c052  cvtsi2ss xmm0, rax
0x18001c057  mulss   xmm0, cs:__real@42c80000
0x18001c05f  divss   xmm0, dword ptr [rdi]
0x18001c063  movss   dword ptr [rdi], xmm0
0x18001c067  movaps  xmm6, [rsp+0A8h+var_58]
0x18001c06c  mov     eax, ebx
0x18001c06e  add     rsp, 68h
0x18001c072  pop     r15
0x18001c074  pop     r14
0x18001c076  pop     r13
0x18001c078  pop     r12
0x18001c07a  pop     rdi
0x18001c07b  pop     rsi
0x18001c07c  pop     rbp
0x18001c07d  pop     rbx
0x18001c07e  retn
```
