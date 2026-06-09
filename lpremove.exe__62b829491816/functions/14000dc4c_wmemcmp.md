# wmemcmp

- ea: `0x14000dc4c`
- end: `0x14000dd6c`
- name: `wmemcmp`
- size: `288`
- prototype: `int __cdecl(const wchar_t *S1, const wchar_t *S2, size_t N)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140003260`
- `0x14000de70`
- `0x14000df20`
- `0x14000eeb8`

## callees

- `0x14000dc4c`

## pseudocode

```c
int __cdecl wmemcmp(const wchar_t *S1, const wchar_t *S2, size_t N)
{
  size_t v3; // r9
  const __m128i *v7; // r11
  unsigned __int64 v11; // rcx
  int result; // eax
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rax
  bool v17; // cf
  wchar_t v18; // ax

  v3 = 0;
  _R10 = (const __m128i *)S1;
  v7 = (const __m128i *)S2;
  if ( Avx2WmemEnabledWeakValue && N >= 0x10 )
  {
    while ( 1 )
    {
      __asm
      {
        vmovdqu ymm1, ymmword ptr [r10]
        vpcmpeqw ymm1, ymm1, ymmword ptr [r11]
        vpmovmskb eax, ymm1
      }
      if ( _EAX != -1 )
        break;
      v3 += 16LL;
      _R10 += 2;
      v7 += 2;
      if ( v3 + 16 > N )
      {
        __asm { vzeroupper }
        goto LABEL_9;
      }
    }
    _BitScanForward((unsigned int *)&v11, ~_EAX);
    result = S1[(v11 >> 1) + v3] < S2[(v11 >> 1) + v3] ? -1 : 1;
    __asm { vzeroupper }
  }
  else
  {
LABEL_9:
    while ( v3 + 8 <= N )
    {
      LOWORD(v13) = _mm_movemask_epi8(_mm_cmpeq_epi16(_mm_loadu_si128(v7), _mm_loadu_si128(_R10)));
      if ( (_WORD)v13 != 0xFFFF )
      {
        _BitScanForward((unsigned int *)&v13, ~(unsigned __int16)v13);
        v15 = (v13 >> 1) + v3;
        v16 = v15;
LABEL_14:
        v17 = S1[v15] < S2[v16];
        return v17 ? -1 : 1;
      }
      v3 += 8LL;
      ++_R10;
      ++v7;
    }
    if ( v3 + 4 > N )
      goto LABEL_19;
    if ( _R10->m128i_i64[0] != v7->m128i_i64[0] )
    {
      _BitScanForward64(&v14, _R10->m128i_i64[0] ^ v7->m128i_i64[0]);
      v15 = (v14 >> 4) + v3;
      v16 = v15;
      goto LABEL_14;
    }
    v3 += 4LL;
LABEL_19:
    while ( v3 < N )
    {
      v18 = S1[v3];
      v17 = v18 < S2[v3];
      if ( v18 != S2[v3] )
        return v17 ? -1 : 1;
      ++v3;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000dc4c  mov     [rsp+arg_8], rbx
0x14000dc51  mov     [rsp+arg_10], rdi
0x14000dc56  xor     r9d, r9d
0x14000dc59  mov     rbx, rdx
0x14000dc5c  cmp     cs:_Avx2WmemEnabledWeakValue, r9d
0x14000dc63  mov     rdi, rcx
0x14000dc66  mov     r10, rcx
0x14000dc69  mov     r11, rdx
0x14000dc6c  jz      loc_14000DCF4
0x14000dc72  cmp     r8, 10h
0x14000dc76  jb      short loc_14000DCF4
0x14000dc78  vmovdqu ymm1, ymmword ptr [r10]
0x14000dc7d  vpcmpeqw ymm1, ymm1, ymmword ptr [r11]
0x14000dc82  vpmovmskb eax, ymm1
0x14000dc86  cmp     eax, 0FFFFFFFFh
0x14000dc89  jnz     short loc_14000DCA5
0x14000dc8b  add     r9, 10h
0x14000dc8f  add     r10, 20h ; ' '
0x14000dc93  add     r11, 20h ; ' '
0x14000dc97  lea     rax, [r9+10h]
0x14000dc9b  cmp     rax, r8
0x14000dc9e  jbe     short loc_14000DC78
0x14000dca0  vzeroupper
0x14000dca3  jmp     short loc_14000DCF4
0x14000dca5  not     eax
0x14000dca7  bsf     ecx, eax
0x14000dcaa  shr     rcx, 1
0x14000dcad  lea     rax, [rcx+r9]
0x14000dcb1  lea     rdx, [rcx+r9]
0x14000dcb5  movzx   ecx, word ptr [rbx+rax*2]
0x14000dcb9  cmp     [rdi+rdx*2], cx
0x14000dcbd  sbb     eax, eax
0x14000dcbf  and     eax, 0FFFFFFFEh
0x14000dcc2  inc     eax
0x14000dcc4  vzeroupper
0x14000dcc7  jmp     loc_14000DD61
0x14000dccc  movdqu  xmm1, xmmword ptr [r11]
0x14000dcd1  mov     ecx, 0FFFFh
0x14000dcd6  movdqu  xmm0, xmmword ptr [r10]
0x14000dcdb  pcmpeqw xmm1, xmm0
0x14000dcdf  pmovmskb eax, xmm1
0x14000dce3  cmp     ax, cx
0x14000dce6  jnz     short loc_14000DD23
0x14000dce8  add     r9, 8
0x14000dcec  add     r10, 10h
0x14000dcf0  add     r11, 10h
0x14000dcf4  lea     rax, [r9+8]
0x14000dcf8  cmp     rax, r8
0x14000dcfb  jbe     short loc_14000DCCC
0x14000dcfd  lea     rax, [r9+4]
0x14000dd01  cmp     rax, r8
0x14000dd04  ja      short loc_14000DD5A
0x14000dd06  mov     rcx, [r11]
0x14000dd09  cmp     [r10], rcx
0x14000dd0c  jz      short loc_14000DD46
0x14000dd0e  xor     rcx, [r10]
0x14000dd11  bsf     rcx, rcx
0x14000dd15  shr     rcx, 4
0x14000dd19  lea     rdx, [rcx+r9]
0x14000dd1d  lea     rax, [rcx+r9]
0x14000dd21  jmp     short loc_14000DD35
0x14000dd23  movzx   eax, ax
0x14000dd26  not     eax
0x14000dd28  bsf     eax, eax
0x14000dd2b  shr     rax, 1
0x14000dd2e  lea     rdx, [rax+r9]
0x14000dd32  add     rax, r9
0x14000dd35  movzx   ecx, word ptr [rbx+rax*2]
0x14000dd39  cmp     [rdi+rdx*2], cx
0x14000dd3d  sbb     eax, eax
0x14000dd3f  and     eax, 0FFFFFFFEh
0x14000dd42  inc     eax
0x14000dd44  jmp     short loc_14000DD61
0x14000dd46  mov     r9, rax
0x14000dd49  jmp     short loc_14000DD5A
0x14000dd4b  movzx   eax, word ptr [rdi+r9*2]
0x14000dd50  cmp     ax, [rdx+r9*2]
0x14000dd55  jnz     short loc_14000DD3D
0x14000dd57  inc     r9
0x14000dd5a  cmp     r9, r8
0x14000dd5d  jb      short loc_14000DD4B
0x14000dd5f  xor     eax, eax
0x14000dd61  mov     rbx, [rsp+arg_8]
0x14000dd66  mov     rdi, [rsp+arg_10]
0x14000dd6b  retn
```
