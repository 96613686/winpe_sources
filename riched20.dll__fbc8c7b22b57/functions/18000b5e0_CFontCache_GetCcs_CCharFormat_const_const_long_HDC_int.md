# CFontCache::GetCcs(CCharFormat const * const,long,HDC__ *,int)

- ea: `0x18000b5e0`
- end: `0x18000bab2`
- name: `?GetCcs@CFontCache@@QEAAPEAVCCcs@@QEBVCCharFormat@@JPEAUHDC__@@H@Z`
- size: `1234`
- prototype: `struct CCcs *__usercall@<rax>(CFontCache *__hidden this@<rcx>, const struct CCharFormat *const@<rdx>, int@<r8d>, HDC@<r9>, int)`
- caller_count: `13`
- callee_count: `6`
- tags: ``

## callers

- `0x180009108`
- `0x180009804`
- `0x1800099c0`
- `0x18000a1d0`
- `0x18000b240`
- `0x18000b540`
- `0x18000c840`
- `0x18000dad0`
- `0x1800112c0`
- `0x18001a434`
- `0x180058184`
- `0x18005b090`
- `0x18005d0bc`

## callees

- `0x18000b5e0`
- `0x18001aa0c`
- `0x18002cc48`
- `0x180042f94`
- `0x180048e30`
- `0x180060e44`

## pseudocode

```c
struct CCcs *__fastcall CFontCache::GetCcs(CFontCache *this, __m128i *a2, int a3, HDC a4, int a5)
{
  __m128i v6; // xmm2
  __int64 v9; // xmm0_8
  __m128i v11; // xmm6
  char v12; // r15
  __int16 FontNameIndex; // bp
  unsigned __int32 v14; // ebx
  int v15; // edx
  int v16; // r8d
  unsigned int v17; // r12d
  __int64 v18; // r10
  struct CCcs *result; // rax
  __int16 v20; // r11
  int v21; // edx
  CFontCache *v22; // r9
  __int64 v23; // r14
  unsigned int v24; // ecx
  CFontCache *v25; // rax
  CFontCache *v26; // rbx
  __int64 v27; // r14
  __int64 v28; // rcx
  __int64 FontSignatureFromFace; // rax
  __int64 v30; // rcx
  _BYTE *v31; // rax
  __int64 v32; // rbx
  __int8 v33; // eax^2
  __m128i v34; // [rsp+20h] [rbp-68h] BYREF
  __m128i v35; // [rsp+30h] [rbp-58h]
  __int64 v36; // [rsp+40h] [rbp-48h]

  v6 = *a2;
  v9 = a2[2].m128i_i64[0];
  v11 = a2[1];
  v12 = _mm_cvtsi128_si32(_mm_srli_si128(*a2, 4));
  v34 = *a2;
  v35 = v11;
  v36 = v9;
  if ( a5 )
  {
    if ( CW32System::_dwPlatformId != 1 )
    {
      v28 = a2->m128i_i16[3];
      if ( (int)v28 < 0 || (int)v28 > dword_1800A72B4 )
        goto LABEL_54;
      v31 = lpMem;
      v32 = 2 * v28;
      if ( (*((_BYTE *)lpMem + 16 * v28 + 14) & 1) == 0 )
      {
        GetFontSignatureFromFace(v28, 0);
        v31 = lpMem;
      }
      if ( (v31[8 * v32 + 14] & 4) == 0 )
      {
LABEL_54:
        FontNameIndex = v34.m128i_i16[3];
        v14 = v34.m128i_i32[0] | 0x100000;
        v34.m128i_i32[0] |= 0x100000u;
        goto LABEL_4;
      }
      goto LABEL_2;
    }
    if ( CW32System::_ACP == 1258 || CW32System::_ACP == 874 )
    {
      FontSignatureFromFace = GetFontSignatureFromFace(v6.m128i_i16[3], 0);
      if ( v12 == -34 )
      {
        if ( (FontSignatureFromFace & 0x10000) == 0 )
          goto LABEL_67;
      }
      else if ( v12 == -93 && (FontSignatureFromFace & 0x100) == 0 )
      {
        goto LABEL_67;
      }
      if ( (*(_BYTE *)CFontCache::GetInfoFlags(v30, &a5, (unsigned int)a2->m128i_i16[3]) & 4) == 0 )
      {
LABEL_67:
        FontNameIndex = GetFontNameIndex(L"Tahoma");
        v34.m128i_i16[3] = FontNameIndex;
        goto LABEL_3;
      }
    }
  }
LABEL_2:
  FontNameIndex = v34.m128i_i16[3];
LABEL_3:
  v14 = v34.m128i_i32[0];
LABEL_4:
  if ( !a4 )
  {
    a4 = CW32System::_hdcScreen;
    if ( !CW32System::_hdcScreen )
    {
      result = (struct CCcs *)CW32System::CreateIC(L"DISPLAY", 0, 0, 0);
      CW32System::_hdcScreen = (HDC)result;
      a4 = (HDC)result;
      if ( !result )
        return result;
    }
  }
  if ( (v14 & 0x30000) != 0 )
    v15 = 2 * v34.m128i_i16[4] / 3;
  else
    LOWORD(v15) = v34.m128i_i16[4];
  v16 = (a3 * (__int16)v15 + 720) / 1440;
  v34.m128i_i16[4] = v16;
  if ( !(_WORD)v16 )
  {
    LOWORD(v16) = 1;
    v34.m128i_i16[4] = 1;
  }
  v17 = ((v14 & 3) << 14) | FontNameIndex | ((__int16)v16 << 16);
  v18 = v17 % 0x1F;
  if ( v17 == *((_DWORD *)this + 4 * v18 + 770) )
  {
    result = (struct CCcs *)*((_QWORD *)this + 2 * v18 + 386);
    if ( result
      && (*((_BYTE *)result + 123) & 1) != 0
      && *((_WORD *)result + 4) == FontNameIndex
      && *((_WORD *)result + 44) == (_WORD)v16
      && (*((_BYTE *)result + 118) == v12 || *((_BYTE *)result + 119) == v12) )
    {
      v20 = _mm_cvtsi128_si32(v11);
      if ( *((_WORD *)result + 57) == v20
        && (((*((_BYTE *)result + 123) >> 4) ^ (unsigned __int8)(v14 >> 20)) & 1) == 0
        && (((*((_BYTE *)result + 123) >> 2) ^ (unsigned __int8)(v14 >> 1)) & 1) == 0
        && *((HDC *)result + 8) == a4
        && *((_BYTE *)result + 122) == v34.m128i_i8[5]
        && ((v14 & 0x40000) == 0 || *((_BYTE *)result + 121) == 2) )
      {
        goto LABEL_21;
      }
      goto LABEL_29;
    }
  }
  else
  {
    *((_DWORD *)this + 4 * (v17 % 0x1F) + 770) = v17;
  }
  v20 = v35.m128i_i16[0];
LABEL_29:
  v22 = (CFontCache *)((char *)this + 2944);
  for ( result = this; ; result = (struct CCcs *)((char *)result + 128) )
  {
    if ( result > v22 )
    {
      v23 = v18 + 193;
      v24 = -1;
      v25 = 0;
      v26 = this;
      if ( this <= v22 )
      {
        while ( (*((_BYTE *)v26 + 123) & 1) != 0 )
        {
          if ( !*((_WORD *)v26 + 5) && *((_DWORD *)v26 + 1) < v24 )
          {
            v24 = *((_DWORD *)v26 + 1);
            v25 = v26;
          }
          v26 = (CFontCache *)((char *)v26 + 128);
          if ( v26 > v22 )
          {
            if ( !v25 )
              goto LABEL_34;
            v26 = v25;
            break;
          }
        }
        *((_QWORD *)v26 + 8) = a4;
        v27 = 2 * v23;
        if ( (unsigned int)CCcs::Init(v26, (const struct CCharFormat *const)&v34) )
        {
          ++*((_WORD *)v26 + 5);
          *((_QWORD *)this + v27) = v26;
          if ( v26 )
          {
            v33 = v34.m128i_i8[2];
            *((_BYTE *)v26 + 123) &= ~0x10u;
            *(_DWORD *)v26 = v17;
            *((_BYTE *)v26 + 123) |= v33 & 0x10;
          }
          return v26;
        }
      }
      else
      {
LABEL_34:
        v27 = 2 * v23;
      }
      *((_QWORD *)this + v27) = 0;
      return 0;
    }
    if ( *(_DWORD *)result == v17
      && (*((_BYTE *)result + 123) & 1) != 0
      && *((_WORD *)result + 4) == FontNameIndex
      && *((_WORD *)result + 44) == (_WORD)v16
      && (*((_BYTE *)result + 118) == v12 || *((_BYTE *)result + 119) == v12)
      && *((_WORD *)result + 57) == v20
      && (((*((_BYTE *)result + 123) >> 4) ^ (unsigned __int8)(v14 >> 20)) & 1) == 0
      && (((*((_BYTE *)result + 123) >> 2) ^ (unsigned __int8)(v14 >> 1)) & 1) == 0
      && *((HDC *)result + 8) == a4
      && *((_BYTE *)result + 122) == v34.m128i_i8[5]
      && ((v14 & 0x40000) == 0 || *((_BYTE *)result + 121) == 2) )
    {
      break;
    }
  }
  *((_QWORD *)this + 2 * v18 + 386) = result;
LABEL_21:
  v21 = *((_DWORD *)this + 768);
  if ( *((_DWORD *)result + 1) != v21 - 1 )
  {
    *((_DWORD *)this + 768) = v21 + 1;
    *((_DWORD *)result + 1) = v21;
  }
  ++*((_WORD *)result + 5);
  return result;
}

```

## disassembly

```asm
0x18000b5e0  mov     [rsp+arg_10], rbx
0x18000b5e5  push    rbp
0x18000b5e6  push    rsi
0x18000b5e7  push    rdi
0x18000b5e8  push    r14
0x18000b5ea  push    r15
0x18000b5ec  sub     rsp, 60h
0x18000b5f0  cmp     [rsp+88h+arg_20], 0
0x18000b5f8  mov     rdi, r9
0x18000b5fb  movups  xmm2, xmmword ptr [rdx]
0x18000b5fe  mov     r14d, r8d
0x18000b601  mov     rbx, rdx
0x18000b604  movsd   xmm0, qword ptr [rdx+20h]
0x18000b609  mov     rsi, rcx
0x18000b60c  movaps  [rsp+88h+var_38], xmm6
0x18000b611  movdqa  xmm1, xmm2
0x18000b615  movups  xmm6, xmmword ptr [rdx+10h]
0x18000b619  psrldq  xmm1, 4
0x18000b61e  movd    r15d, xmm1
0x18000b623  movups  [rsp+88h+var_68], xmm2
0x18000b628  movups  [rsp+88h+var_58], xmm6
0x18000b62d  movsd   [rsp+88h+var_48], xmm0
0x18000b633  jnz     loc_18000B90B
0x18000b639  movzx   ebp, word ptr [rsp+88h+var_68+6]
0x18000b63e  mov     ebx, dword ptr [rsp+88h+var_68]
0x18000b642  test    rdi, rdi
0x18000b645  jz      loc_18000B7D4
0x18000b64b  mov     [rsp+88h+arg_0], r12
0x18000b653  test    ebx, 30000h
0x18000b659  jnz     loc_18000BA03
0x18000b65f  movzx   edx, word ptr [rsp+88h+var_68+8]
0x18000b664  movsx   ecx, dx
0x18000b667  mov     eax, 0B60B60B7h
0x18000b66c  imul    ecx, r14d
0x18000b670  add     ecx, 2D0h
0x18000b676  imul    ecx
0x18000b678  lea     r8d, [rcx+rdx]
0x18000b67c  sar     r8d, 0Ah
0x18000b680  mov     eax, r8d
0x18000b683  shr     eax, 1Fh
0x18000b686  add     r8d, eax
0x18000b689  mov     word ptr [rsp+88h+var_68+8], r8w
0x18000b68f  test    r8w, r8w
0x18000b693  jz      loc_18000BA1D
0x18000b699  movsx   eax, bp
0x18000b69c  movsx   r12d, r8w
0x18000b6a0  shl     r12d, 10h
0x18000b6a4  or      r12d, eax
0x18000b6a7  mov     [rsp+88h+arg_8], r13
0x18000b6af  mov     eax, ebx
0x18000b6b1  and     eax, 3
0x18000b6b4  shl     eax, 0Eh
0x18000b6b7  or      r12d, eax
0x18000b6ba  mov     eax, 8421085h
0x18000b6bf  mul     r12d
0x18000b6c2  mov     ecx, r12d
0x18000b6c5  mov     eax, r12d
0x18000b6c8  sub     eax, edx
0x18000b6ca  shr     eax, 1
0x18000b6cc  add     eax, edx
0x18000b6ce  shr     eax, 4
0x18000b6d1  imul    eax, 1Fh
0x18000b6d4  sub     ecx, eax
0x18000b6d6  movsxd  r10, ecx
0x18000b6d9  mov     rcx, r10
0x18000b6dc  add     rcx, rcx
0x18000b6df  cmp     r12d, [rsi+rcx*8+0C08h]
0x18000b6e7  jnz     loc_18000B80D
0x18000b6ed  lea     rax, [r10+0C1h]
0x18000b6f4  add     rax, rax
0x18000b6f7  mov     rax, [rsi+rax*8]
0x18000b6fb  test    rax, rax
0x18000b6fe  jz      loc_18000B815
0x18000b704  movzx   ecx, byte ptr [rax+7Bh]
0x18000b708  test    cl, 1
0x18000b70b  jz      loc_18000B815
0x18000b711  cmp     [rax+8], bp
0x18000b715  jnz     loc_18000B815
0x18000b71b  cmp     [rax+58h], r8w
0x18000b720  jnz     loc_18000B815
0x18000b726  cmp     [rax+76h], r15b
0x18000b72a  jnz     loc_18000B879
0x18000b730  movd    r11d, xmm6
0x18000b735  cmp     [rax+72h], r11w
0x18000b73a  jnz     loc_18000B81B
0x18000b740  mov     edx, ebx
0x18000b742  mov     r9d, ecx
0x18000b745  shr     edx, 14h
0x18000b748  shr     ecx, 4
0x18000b74b  xor     edx, ecx
0x18000b74d  test    dl, 1
0x18000b750  jnz     loc_18000B81B
0x18000b756  shr     r9d, 2
0x18000b75a  mov     ecx, ebx
0x18000b75c  shr     ecx, 1
0x18000b75e  xor     ecx, r9d
0x18000b761  test    cl, 1
0x18000b764  jnz     loc_18000B81B
0x18000b76a  cmp     [rax+40h], rdi
0x18000b76e  jnz     loc_18000B81B
0x18000b774  movzx   ecx, byte ptr [rsp+88h+var_68+5]
0x18000b779  cmp     [rax+7Ah], cl
0x18000b77c  jnz     loc_18000B81B
0x18000b782  bt      ebx, 12h
0x18000b786  jb      loc_18000BA2E
0x18000b78c  mov     edx, [rsi+0C00h]
0x18000b792  lea     ecx, [rdx-1]
0x18000b795  cmp     [rax+4], ecx
0x18000b798  jz      short loc_18000B7A6
0x18000b79a  lea     ecx, [rdx+1]
0x18000b79d  mov     [rsi+0C00h], ecx
0x18000b7a3  mov     [rax+4], edx
0x18000b7a6  inc     word ptr [rax+0Ah]
0x18000b7aa  mov     r13, [rsp+88h+arg_8]
0x18000b7b2  mov     r12, [rsp+88h+arg_0]
0x18000b7ba  mov     rbx, [rsp+88h+arg_10]
0x18000b7c2  movaps  xmm6, [rsp+88h+var_38]
0x18000b7c7  add     rsp, 60h
0x18000b7cb  pop     r15
0x18000b7cd  pop     r14
0x18000b7cf  pop     rdi
0x18000b7d0  pop     rsi
0x18000b7d1  pop     rbp
0x18000b7d2  retn
0x18000b7d4  mov     rdi, cs:?_hdcScreen@CW32System@@0PEAUHDC__@@EA; HDC__ * CW32System::_hdcScreen
0x18000b7db  test    rdi, rdi
0x18000b7de  jnz     loc_18000B64B
0x18000b7e4  xor     r9d, r9d; struct _devicemodeW *
0x18000b7e7  lea     rcx, aDisplay; "DISPLAY"
0x18000b7ee  xor     r8d, r8d; unsigned __int16 *
0x18000b7f1  xor     edx, edx; unsigned __int16 *
0x18000b7f3  call    ?CreateIC@CW32System@@SAPEAUHDC__@@PEBG00PEBU_devicemodeW@@@Z; CW32System::CreateIC(ushort const *,ushort const *,ushort const *,_devicemodeW const *)
0x18000b7f8  mov     cs:?_hdcScreen@CW32System@@0PEAUHDC__@@EA, rax; HDC__ * CW32System::_hdcScreen
0x18000b7ff  mov     rdi, rax
0x18000b802  test    rax, rax
0x18000b805  jnz     loc_18000B64B
0x18000b80b  jmp     short loc_18000B7BA
0x18000b80d  mov     [rsi+rcx*8+0C08h], r12d
0x18000b815  movzx   r11d, word ptr [rsp+88h+var_58]
0x18000b81b  mov     r13d, 0C1h
0x18000b821  lea     r9, [rsi+0B80h]
0x18000b828  mov     rax, rsi
0x18000b82b  cmp     rax, r9
0x18000b82e  ja      short loc_18000B83B
0x18000b830  cmp     [rax], r12d
0x18000b833  jz      short loc_18000B885
0x18000b835  sub     rax, 0FFFFFFFFFFFFFF80h
0x18000b839  jmp     short loc_18000B82B
0x18000b83b  xor     ebp, ebp
0x18000b83d  lea     r14, [r10+r13]
0x18000b841  mov     ecx, 0FFFFFFFFh
0x18000b846  mov     eax, ebp
0x18000b848  mov     rbx, rsi
0x18000b84b  cmp     rsi, r9
0x18000b84e  jbe     loc_18000BA4C
0x18000b854  add     r14, r14
0x18000b857  mov     [rsi+r14*8], rbp
0x18000b85b  mov     rbx, rbp
0x18000b85e  jmp     short loc_18000B871
0x18000b860  inc     word ptr [rbx+0Ah]
0x18000b864  mov     [rsi+r14*8], rbx
0x18000b868  test    rbx, rbx
0x18000b86b  jnz     loc_18000BA9A
0x18000b871  mov     rax, rbx
0x18000b874  jmp     loc_18000B7AA
0x18000b879  cmp     [rax+77h], r15b
0x18000b87d  jz      loc_18000B730
0x18000b883  jmp     short loc_18000B815
0x18000b885  movzx   ecx, byte ptr [rax+7Bh]
0x18000b889  test    cl, 1
0x18000b88c  jz      short loc_18000B835
0x18000b88e  cmp     [rax+8], bp
0x18000b892  jnz     short loc_18000B835
0x18000b894  cmp     [rax+58h], r8w
0x18000b899  jnz     short loc_18000B835
0x18000b89b  cmp     [rax+76h], r15b
0x18000b89f  jnz     loc_18000B937
0x18000b8a5  cmp     [rax+72h], r11w
0x18000b8aa  jnz     short loc_18000B835
0x18000b8ac  mov     edx, ebx
0x18000b8ae  mov     r14d, ecx
0x18000b8b1  shr     edx, 14h
0x18000b8b4  shr     ecx, 4
0x18000b8b7  xor     edx, ecx
0x18000b8b9  test    dl, 1
0x18000b8bc  jnz     loc_18000B835
0x18000b8c2  shr     r14d, 2
0x18000b8c6  mov     ecx, ebx
0x18000b8c8  shr     ecx, 1
0x18000b8ca  xor     ecx, r14d
0x18000b8cd  test    cl, 1
0x18000b8d0  jnz     loc_18000B835
0x18000b8d6  cmp     [rax+40h], rdi
0x18000b8da  jnz     loc_18000B835
0x18000b8e0  movzx   ecx, byte ptr [rsp+88h+var_68+5]
0x18000b8e5  cmp     [rax+7Ah], cl
0x18000b8e8  jnz     loc_18000B835
0x18000b8ee  bt      ebx, 12h
0x18000b8f2  jb      loc_18000BA3D
0x18000b8f8  lea     rcx, [r10+0C1h]
0x18000b8ff  add     rcx, rcx
0x18000b902  mov     [rsi+rcx*8], rax
0x18000b906  jmp     loc_18000B78C
0x18000b90b  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18000b912  jz      short loc_18000B953
0x18000b914  movsx   rcx, word ptr [rdx+6]; int
0x18000b919  test    ecx, ecx
0x18000b91b  jns     loc_18000B9CC
0x18000b921  mov     ebx, dword ptr [rsp+88h+var_68]
0x18000b925  movzx   ebp, word ptr [rsp+88h+var_68+6]
0x18000b92a  bts     ebx, 14h
0x18000b92e  mov     dword ptr [rsp+88h+var_68], ebx
0x18000b932  jmp     loc_18000B642
0x18000b937  cmp     [rax+77h], r15b
0x18000b93b  jz      loc_18000B8A5
0x18000b941  jmp     loc_18000B835
0x18000b946  test    byte ptr [rax+rbx*8+0Eh], 4
0x18000b94b  jnz     loc_18000B639
0x18000b951  jmp     short loc_18000B921
0x18000b953  mov     eax, cs:?_ACP@CW32System@@0IA; uint CW32System::_ACP
0x18000b959  cmp     eax, 4EAh
0x18000b95e  jz      short loc_18000B96B
0x18000b960  cmp     eax, 36Ah
0x18000b965  jnz     loc_18000B639
0x18000b96b  movq    rax, xmm2
0x18000b970  xor     edx, edx; unsigned int *
0x18000b972  shr     rax, 30h
0x18000b976  movsx   ecx, ax; int
0x18000b979  call    ?GetFontSignatureFromFace@@YAKHPEAK@Z; GetFontSignatureFromFace(int,ulong *)
0x18000b97e  cmp     r15b, 0DEh
0x18000b982  jnz     short loc_18000B98C
0x18000b984  bt      eax, 10h
0x18000b988  jb      short loc_18000B998
0x18000b98a  jmp     short loc_18000B9B3
0x18000b98c  cmp     r15b, 0A3h
0x18000b990  jnz     short loc_18000B998
0x18000b992  bt      eax, 8
0x18000b996  jnb     short loc_18000B9B3
0x18000b998  movsx   r8d, word ptr [rbx+6]
0x18000b99d  lea     rdx, [rsp+88h+arg_20]
0x18000b9a5  call    ?GetInfoFlags@CFontCache@@QEAA?ATFONTINFO_FLAGS@@H@Z; CFontCache::GetInfoFlags(int)
0x18000b9aa  test    byte ptr [rax], 4
0x18000b9ad  jnz     loc_18000B639
0x18000b9b3  lea     rcx, Src; "Tahoma"
0x18000b9ba  call    ?GetFontNameIndex@@YAFPEBG@Z; GetFontNameIndex(ushort const *)
0x18000b9bf  movzx   ebp, ax
0x18000b9c2  mov     word ptr [rsp+88h+var_68+6], ax
0x18000b9c7  jmp     loc_18000B63E
0x18000b9cc  cmp     ecx, cs:dword_1800A72B4
0x18000b9d2  jg      loc_18000B921
0x18000b9d8  mov     rax, cs:lpMem
0x18000b9df  mov     rbx, rcx
0x18000b9e2  add     rbx, rbx
0x18000b9e5  test    byte ptr [rax+rbx*8+0Eh], 1
0x18000b9ea  jnz     loc_18000B946
0x18000b9f0  xor     edx, edx; unsigned int *
0x18000b9f2  call    ?GetFontSignatureFromFace@@YAKHPEAK@Z; GetFontSignatureFromFace(int,ulong *)
0x18000b9f7  mov     rax, cs:lpMem
0x18000b9fe  jmp     loc_18000B946
0x18000ba03  movsx   ecx, word ptr [rsp+88h+var_68+8]
0x18000ba08  mov     eax, 55555556h
0x18000ba0d  add     ecx, ecx
0x18000ba0f  imul    ecx
0x18000ba11  mov     eax, edx
0x18000ba13  shr     eax, 1Fh
0x18000ba16  add     edx, eax
0x18000ba18  jmp     loc_18000B664
0x18000ba1d  mov     r8d, 1
0x18000ba23  mov     word ptr [rsp+88h+var_68+8], r8w
0x18000ba29  jmp     loc_18000B699
0x18000ba2e  cmp     byte ptr [rax+79h], 2
0x18000ba32  jz      loc_18000B78C
0x18000ba38  jmp     loc_18000B81B
0x18000ba3d  cmp     byte ptr [rax+79h], 2
0x18000ba41  jz      loc_18000B8F8
0x18000ba47  jmp     loc_18000B835
0x18000ba4c  test    byte ptr [rbx+7Bh], 1
0x18000ba50  jz      short loc_18000BA79
0x18000ba52  cmp     [rbx+0Ah], bp
0x18000ba56  jnz     short loc_18000BA64
0x18000ba58  mov     edx, [rbx+4]
0x18000ba5b  cmp     edx, ecx
0x18000ba5d  jnb     short loc_18000BA64
0x18000ba5f  mov     ecx, edx
0x18000ba61  mov     rax, rbx
0x18000ba64  sub     rbx, 0FFFFFFFFFFFFFF80h
0x18000ba68  cmp     rbx, r9
0x18000ba6b  jbe     short loc_18000BA4C
0x18000ba6d  test    rax, rax
0x18000ba70  jz      loc_18000B854
0x18000ba76  mov     rbx, rax
0x18000ba79  lea     rdx, [rsp+88h+var_68]; struct CCharFormat *
0x18000ba7e  mov     [rbx+40h], rdi
0x18000ba82  mov     rcx, rbx; this
0x18000ba85  call    ?Init@CCcs@@QEAAHQEBVCCharFormat@@@Z; CCcs::Init(CCharFormat const * const)
0x18000ba8a  add     r14, r14
0x18000ba8d  test    eax, eax
0x18000ba8f  jz      loc_18000B857
0x18000ba95  jmp     loc_18000B860
0x18000ba9a  mov     eax, dword ptr [rsp+88h+var_68]
  ... truncated ...
```
