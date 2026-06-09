# CdNonCachedXARead

- ea: `0x14000f618`
- end: `0x14000fcaa`
- name: `CdNonCachedXARead`
- size: `1682`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140017ab8`

## callees

- `0x140001114`
- `0x140002df0`
- `0x140003000`
- `0x140003300`
- `0x14000e978`
- `0x14000ea54`
- `0x14000f060`
- `0x14000f618`
- `0x140010098`
- `0x140010e90`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000f6e1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000f6e1`
- `ntoskrnl!KeFlushIoBuffers` at `0x14000fc30`
- `ntoskrnl!KeFlushIoBuffers` at `0x14000fc30`

## pseudocode

```c
__int64 __fastcall CdNonCachedXARead(__int64 a1, __int64 a2, unsigned __int64 a3, ULONG a4)
{
  __int64 v4; // rsi
  __int64 v6; // rbx
  size_t v8; // r12
  __int64 v9; // r14
  __int64 v10; // rcx
  char *v11; // r14
  __int64 v12; // r12
  __int64 v13; // r11
  __int64 v14; // r10
  __int64 v15; // rcx
  unsigned int v16; // r9d
  size_t v17; // rax
  int v18; // ecx
  int v19; // ecx
  int v20; // eax
  int v21; // r13d
  unsigned int v22; // ecx
  int v23; // r9d
  char v25; // [rsp+88h] [rbp-258h]
  int v26; // [rsp+8Ch] [rbp-254h]
  unsigned int v27; // [rsp+90h] [rbp-250h] BYREF
  int v28; // [rsp+94h] [rbp-24Ch] BYREF
  size_t v29; // [rsp+98h] [rbp-248h]
  size_t v30; // [rsp+A0h] [rbp-240h]
  __int128 v31; // [rsp+A8h] [rbp-238h]
  _BYTE v32[28]; // [rsp+B8h] [rbp-228h] BYREF
  _BYTE v33[4]; // [rsp+D4h] [rbp-20Ch] BYREF
  int v34; // [rsp+D8h] [rbp-208h]
  int v35; // [rsp+DCh] [rbp-204h]
  int v36; // [rsp+E0h] [rbp-200h]
  int v37; // [rsp+E4h] [rbp-1FCh]
  int v38; // [rsp+E8h] [rbp-1F8h]
  unsigned __int64 v39; // [rsp+F0h] [rbp-1F0h]
  char *v40; // [rsp+F8h] [rbp-1E8h]
  __int64 v41; // [rsp+100h] [rbp-1E0h]
  _BYTE v42[80]; // [rsp+108h] [rbp-1D8h] BYREF
  _BYTE v43[320]; // [rsp+158h] [rbp-188h] BYREF

  v4 = a4;
  v6 = a2;
  v41 = a1;
  v34 = 0;
  v31 = 0;
  memset(v32, 0, sizeof(v32));
  v28 = 0;
  LODWORD(v8) = 0;
  v29 = 0;
  v27 = 0;
  v25 = 0;
  v9 = *(_QWORD *)(a1 + 8);
  if ( !*(_QWORD *)(v9 + 8) )
  {
    CdCreateUserMdl(a1, a4);
    v9 = *(_QWORD *)(a1 + 8);
  }
  if ( (signed __int64)(a3 + v4) > *(_QWORD *)(v6 + 32) )
    LODWORD(v4) = *(_DWORD *)(v6 + 32) - a3;
  v10 = *(_QWORD *)(v9 + 8);
  if ( v10 )
  {
    if ( (*(_BYTE *)(v10 + 10) & 5) != 0 )
      v11 = *(char **)(v10 + 24);
    else
      v11 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v10, 0, MmCached, 0, 0, 0x40000010u);
  }
  else
  {
    v11 = *(char **)(v9 + 112);
  }
  if ( !v11 )
    CdRaiseStatusEx(a1, 3221225626LL, 0, 655360, 683);
  if ( a3 < 0x2C )
  {
    if ( (*(_DWORD *)(v6 + 172) & 0x10) != 0 )
    {
      v12 = *(_QWORD *)(v6 + 120);
      if ( (*(_DWORD *)(v12 + 48) & 0x80u) == 0 )
      {
        v31 = CdXAAudioPhileHeader;
        *(_OWORD *)v32 = xmmword_1400070D8;
        *(_OWORD *)&v32[12] = *(__int128 *)((char *)&xmmword_1400070D8 + 12);
        v18 = *(_DWORD *)(v6 + 32);
        DWORD1(v31) = v18 + _mm_cvtsi128_si32(_mm_srli_si128((__m128i)CdXAAudioPhileHeader, 4));
        *(_DWORD *)&v32[24] = v18 + _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)((char *)&xmmword_1400070D8 + 12), 12));
        v8 = (unsigned int)(44 - a3);
        v29 = v8;
        v27 = 44 - a3;
        memmove(v11, &v33[-v8], v8);
        v17 = (unsigned int)v8;
      }
      else
      {
        v13 = *(unsigned __int8 *)(v6 + 182);
        v14 = *(_QWORD *)(v12 + 520);
        v31 = CdAudioPlayHeader;
        *(_OWORD *)v32 = xmmword_140007108;
        *(_OWORD *)&v32[12] = *(__int128 *)((char *)&xmmword_140007108 + 12);
        *(_DWORD *)&v32[8] = *(_DWORD *)(*(_QWORD *)(v12 + 8) + 24LL);
        *(_WORD *)&v32[6] = *(unsigned __int8 *)(v14 + 8 * v13 + 6);
        LOBYTE(v26) = *(_BYTE *)(v14 + 8 * v13 + 11);
        BYTE1(v26) = *(_BYTE *)(v14 + 8 * v13 + 10);
        BYTE2(v26) = *(_BYTE *)(v14 + 8 * v13 + 9);
        HIBYTE(v26) = *(_BYTE *)(v14 + 8 * v13 + 8);
        v32[20] = (v26 + 150) % 0x4Bu;
        v32[21] = (v26 + 150) / 0x4Bu % 0x3C;
        LODWORD(v29) = (v26 + 150) / 0x4Bu / 0x3C;
        v32[22] = v29;
        v32[12] = *(_BYTE *)(v14 + 8 * v13 + 11);
        v32[13] = *(_BYTE *)(v14 + 8 * v13 + 10);
        v32[14] = *(_BYTE *)(v14 + 8 * v13 + 9);
        v32[15] = *(_BYTE *)(v14 + 8 * v13 + 8);
        v15 = *(_QWORD *)(v12 + 520);
        v32[16] = *(_BYTE *)(v15 + 8 * v13 + 19);
        v32[17] = *(_BYTE *)(v15 + 8 * v13 + 18);
        v32[18] = *(_BYTE *)(v15 + 8 * v13 + 17);
        v32[19] = *(_BYTE *)(v15 + 8 * v13 + 16);
        if ( *(_DWORD *)&v32[16] >= *(_DWORD *)&v32[12] )
        {
          v16 = *(_DWORD *)&v32[16] - *(_DWORD *)&v32[12];
          *(_DWORD *)&v32[16] -= *(_DWORD *)&v32[12];
        }
        else
        {
          *(_DWORD *)&v32[16] = 0;
          v16 = 0;
        }
        v32[24] = v16 % 0x4B;
        v32[25] = v16 / 0x4B % 0x3C;
        LODWORD(v30) = v16 / 0x4B / 0x3C;
        v32[26] = v30;
        LODWORD(v8) = 44 - a3;
        v29 = (unsigned int)(44 - a3);
        v27 = 44 - a3;
        memmove(v11, &v33[-(unsigned int)v8], (unsigned int)v8);
        v17 = v29;
      }
    }
    else
    {
      v31 = CdXAFileHeader;
      *(_OWORD *)v32 = xmmword_1400070A8;
      *(_OWORD *)&v32[12] = *(__int128 *)((char *)&xmmword_1400070A8 + 12);
      v19 = *(_DWORD *)(v6 + 32);
      DWORD1(v31) = v19 + _mm_cvtsi128_si32(_mm_srli_si128((__m128i)CdXAFileHeader, 4));
      *(_DWORD *)&v32[24] = v19 + _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)((char *)&xmmword_1400070A8 + 12), 12));
      *(_WORD *)&v32[8] = *(_WORD *)(v6 + 180);
      v32[12] = *(_BYTE *)(v6 + 182);
      v29 = (unsigned int)(44 - a3);
      v27 = 44 - a3;
      v30 = v29;
      memmove(v11, &v33[-v29], (unsigned int)v29);
      LODWORD(v8) = 44 - a3;
      v17 = (unsigned int)v29;
    }
    v11 += v17;
    v40 = v11;
    v37 = v8;
    a3 += v17;
    v39 = a3;
    LODWORD(v4) = v4 - v8;
    v36 = v4;
  }
  v20 = *(_DWORD *)(v6 + 172);
  if ( (v20 & 4) != 0 )
    v21 = 1;
  else
    v21 = ((unsigned __int8)v20 >> 3) & 2;
  v35 = v21;
  while ( 2 )
  {
    v22 = v29;
    while ( 1 )
    {
      if ( !(_DWORD)v4 )
      {
        LOBYTE(a2) = 1;
        KeFlushIoBuffers(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL), a2, 0);
        goto LABEL_39;
      }
      if ( !v25 )
      {
        memset(v43, 0, sizeof(v43));
        memset(v42, 0, sizeof(v42));
        CdPrepareXABuffers(
          a1,
          *(_QWORD *)(a1 + 8),
          v6,
          (_DWORD)v11,
          v8,
          a3,
          v4,
          (__int64)v43,
          (__int64)&v28,
          (__int64)&v27);
        v22 = v27;
        v29 = v27;
      }
      if ( v28 )
        break;
LABEL_37:
      LODWORD(v4) = v4 - v22;
      v36 = v4;
      a3 += v22;
      v39 = a3;
      v11 += v22;
      v40 = v11;
      LODWORD(v8) = v22 + v8;
      v37 = v8;
    }
    LODWORD(v30) = v28;
    CdMultipleXAAsync(a1, v28, (unsigned int)v43, (unsigned int)v42, v21);
    CdWaitSync(a1);
    v34 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 48LL);
    v38 = v34;
    if ( v34 >= 0 )
    {
      v28 = 0;
      if ( v25 )
      {
        *(_DWORD *)(v6 + 172) |= 8u;
        *(_DWORD *)(v6 + 172) &= ~4u;
        v25 = 0;
      }
      CdFinishBuffers(a1, (unsigned int)v43, v30, 0, 1);
      v22 = v29;
      goto LABEL_37;
    }
    if ( !v25 && (*(_DWORD *)(v6 + 172) & 4) != 0 )
    {
      v25 = 1;
      v21 = 0;
      v35 = 0;
      *(_DWORD *)(*(_QWORD *)(a1 + 48) + 16LL) = 0;
      continue;
    }
    break;
  }
LABEL_39:
  if ( v28 )
  {
    LOBYTE(v23) = 1;
    CdFinishBuffers(a1, (unsigned int)v43, v28, v23, 0);
  }
  return (unsigned int)v34;
}

```

## disassembly

```asm
0x14000f618  push    rbx
0x14000f61a  push    rsi
0x14000f61b  push    rdi
0x14000f61c  push    r12
0x14000f61e  push    r13
0x14000f620  push    r14
0x14000f622  push    r15
0x14000f624  sub     rsp, 270h
0x14000f62b  mov     rax, cs:__security_cookie
0x14000f632  xor     rax, rsp
0x14000f635  mov     [rsp+2A8h+var_48], rax
0x14000f63d  mov     esi, r9d
0x14000f640  mov     r15, r8
0x14000f643  mov     rbx, rdx
0x14000f646  mov     rdi, rcx
0x14000f649  mov     [rsp+2A8h+var_1E0], rcx
0x14000f651  xor     eax, eax
0x14000f653  mov     [rsp+2A8h+var_208], eax
0x14000f65a  xorps   xmm0, xmm0
0x14000f65d  movups  [rsp+2A8h+var_238], xmm0
0x14000f662  movups  [rsp+2A8h+var_228], xmm0
0x14000f66a  movups  [rsp+2A8h+var_228+0Ch], xmm0
0x14000f672  mov     [rsp+2A8h+var_24C], eax
0x14000f676  xor     r12d, r12d
0x14000f679  mov     [rsp+2A8h+var_248], rax
0x14000f67e  mov     [rsp+2A8h+var_250], eax
0x14000f682  mov     [rsp+2A8h+var_254], eax
0x14000f686  mov     [rsp+2A8h+var_258], al
0x14000f68a  mov     r14, [rcx+8]
0x14000f68e  cmp     [r14+8], rax
0x14000f692  jnz     short loc_14000F69F
0x14000f694  mov     edx, esi
0x14000f696  call    CdCreateUserMdl
0x14000f69b  mov     r14, [rdi+8]
0x14000f69f  lea     rax, [r15+rsi]
0x14000f6a3  cmp     rax, [rbx+20h]
0x14000f6a7  jle     short loc_14000F6AF
0x14000f6a9  mov     esi, [rbx+20h]
0x14000f6ac  sub     esi, r15d
0x14000f6af  mov     rcx, [r14+8]; MemoryDescriptorList
0x14000f6b3  test    rcx, rcx
0x14000f6b6  jnz     short loc_14000F6BE
0x14000f6b8  mov     r14, [r14+70h]
0x14000f6bc  jmp     short loc_14000F6F0
0x14000f6be  mov     al, [rcx+0Ah]
0x14000f6c1  test    al, 5
0x14000f6c3  jz      short loc_14000F6CB
0x14000f6c5  mov     r14, [rcx+18h]
0x14000f6c9  jmp     short loc_14000F6F0
0x14000f6cb  mov     [rsp+2A8h+Priority], 40000010h; Priority
0x14000f6d3  mov     [rsp+2A8h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14000f6d8  xor     r9d, r9d; RequestedAddress
0x14000f6db  xor     edx, edx; AccessMode
0x14000f6dd  lea     r8d, [r9+1]; CacheType
0x14000f6e1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000f6e8  nop     dword ptr [rax+rax+00h]
0x14000f6ed  mov     r14, rax
0x14000f6f0  test    r14, r14
0x14000f6f3  jz      loc_14000FC8B
0x14000f6f9  mov     r13d, 2Ch ; ','
0x14000f6ff  cmp     r15, r13
0x14000f702  jnb     loc_14000FA6A
0x14000f708  mov     eax, [rbx+0ACh]
0x14000f70e  test    al, 10h
0x14000f710  jz      loc_14000F9AA
0x14000f716  mov     r12, [rbx+78h]
0x14000f71a  mov     eax, [r12+30h]
0x14000f71f  test    al, al
0x14000f721  jns     loc_14000F92C
0x14000f727  movzx   r11d, byte ptr [rbx+0B6h]
0x14000f72f  mov     r10, [r12+208h]
0x14000f737  movups  xmm0, cs:CdAudioPlayHeader
0x14000f73e  movups  [rsp+2A8h+var_238], xmm0
0x14000f743  movups  xmm1, cs:xmmword_140007108
0x14000f74a  movups  [rsp+2A8h+var_228], xmm1
0x14000f752  movups  xmm0, cs:xmmword_140007108+0Ch
0x14000f759  movups  [rsp+2A8h+var_228+0Ch], xmm0
0x14000f761  mov     rax, [r12+8]
0x14000f766  mov     ecx, [rax+18h]
0x14000f769  mov     dword ptr [rsp+2A8h+var_228+8], ecx
0x14000f770  movzx   eax, byte ptr [r10+r11*8+6]
0x14000f776  mov     word ptr [rsp+2A8h+var_228+6], ax
0x14000f77e  mov     al, [r10+r11*8+0Bh]
0x14000f783  mov     byte ptr [rsp+2A8h+var_254], al
0x14000f787  mov     al, [r10+r11*8+0Ah]
0x14000f78c  mov     byte ptr [rsp+2A8h+var_254+1], al
0x14000f790  mov     al, [r10+r11*8+9]
0x14000f795  mov     byte ptr [rsp+2A8h+var_254+2], al
0x14000f799  mov     al, [r10+r11*8+8]
0x14000f79e  mov     byte ptr [rsp+2A8h+var_254+3], al
0x14000f7a2  mov     eax, [rsp+2A8h+var_254]
0x14000f7a6  mov     dword ptr [rsp+2A8h+var_248], eax
0x14000f7aa  lea     r8d, [rax+96h]
0x14000f7b1  mov     dword ptr [rsp+2A8h+var_248], r8d
0x14000f7b6  mov     eax, 1B4E81B5h
0x14000f7bb  mul     r8d
0x14000f7be  mov     r9d, edx
0x14000f7c1  shr     r9d, 3
0x14000f7c5  movzx   eax, r9b
0x14000f7c9  imul    ecx, eax, 4Bh ; 'K'
0x14000f7cc  sub     r8b, cl
0x14000f7cf  mov     [rsp+2A8h+var_214], r8b
0x14000f7d7  mov     dword ptr [rsp+2A8h+var_248], r9d
0x14000f7dc  mov     eax, 88888889h
0x14000f7e1  mul     r9d
0x14000f7e4  shr     edx, 5
0x14000f7e7  movzx   eax, dl
0x14000f7ea  imul    ecx, eax, 3Ch ; '<'
0x14000f7ed  sub     r9b, cl
0x14000f7f0  mov     [rsp+2A8h+var_213], r9b
0x14000f7f8  mov     dword ptr [rsp+2A8h+var_248], edx
0x14000f7fc  mov     [rsp+2A8h+var_212], dl
0x14000f803  mov     al, [r10+r11*8+0Bh]
0x14000f808  mov     byte ptr [rsp+2A8h+var_228+0Ch], al
0x14000f80f  mov     al, [r10+r11*8+0Ah]
0x14000f814  mov     byte ptr [rsp+2A8h+var_228+0Dh], al
0x14000f81b  mov     al, [r10+r11*8+9]
0x14000f820  mov     byte ptr [rsp+2A8h+var_228+0Eh], al
0x14000f827  mov     al, [r10+r11*8+8]
0x14000f82c  mov     byte ptr [rsp+2A8h+var_228+0Fh], al
0x14000f833  mov     rcx, [r12+208h]
0x14000f83b  mov     al, [rcx+r11*8+13h]
0x14000f840  mov     byte ptr [rsp+2A8h+var_218], al
0x14000f847  mov     al, [rcx+r11*8+12h]
0x14000f84c  mov     byte ptr [rsp+2A8h+var_218+1], al
0x14000f853  mov     al, [rcx+r11*8+11h]
0x14000f858  mov     byte ptr [rsp+2A8h+var_218+2], al
0x14000f85f  mov     al, [rcx+r11*8+10h]
0x14000f864  mov     byte ptr [rsp+2A8h+var_218+3], al
0x14000f86b  mov     r9d, [rsp+2A8h+var_218]
0x14000f873  cmp     r9d, dword ptr [rsp+2A8h+var_228+0Ch]
0x14000f87b  jnb     short loc_14000F88D
0x14000f87d  mov     [rsp+2A8h+var_218], 0
0x14000f888  xor     r9d, r9d
0x14000f88b  jmp     short loc_14000F89D
0x14000f88d  sub     r9d, dword ptr [rsp+2A8h+var_228+0Ch]
0x14000f895  mov     [rsp+2A8h+var_218], r9d
0x14000f89d  lea     eax, [r9-96h]
0x14000f8a4  mov     [rsp+2A8h+var_254], eax
0x14000f8a8  mov     dword ptr [rsp+2A8h+var_240], eax
0x14000f8ac  mov     dword ptr [rsp+2A8h+var_240], r9d
0x14000f8b1  mov     eax, 1B4E81B5h
0x14000f8b6  mul     r9d
0x14000f8b9  mov     r8d, edx
0x14000f8bc  shr     r8d, 3
0x14000f8c0  movzx   eax, r8b
0x14000f8c4  imul    ecx, eax, 4Bh ; 'K'
0x14000f8c7  sub     r9b, cl
0x14000f8ca  mov     byte ptr [rsp+2A8h+var_210], r9b
0x14000f8d2  mov     dword ptr [rsp+2A8h+var_240], r8d
0x14000f8d7  mov     eax, 88888889h
0x14000f8dc  mul     r8d
0x14000f8df  shr     edx, 5
0x14000f8e2  movzx   eax, dl
0x14000f8e5  imul    ecx, eax, 3Ch ; '<'
0x14000f8e8  sub     r8b, cl
0x14000f8eb  mov     byte ptr [rsp+2A8h+var_210+1], r8b
0x14000f8f3  mov     dword ptr [rsp+2A8h+var_240], edx
0x14000f8f7  mov     byte ptr [rsp+2A8h+var_210+2], dl
0x14000f8fe  sub     r13d, r15d
0x14000f901  mov     r12d, r13d
0x14000f904  mov     [rsp+2A8h+var_248], r13
0x14000f909  mov     [rsp+2A8h+var_250], r13d
0x14000f90e  lea     rdx, [rsp+2A8h+var_20C]
0x14000f916  sub     rdx, r12; Src
0x14000f919  mov     r8d, r13d; Size
0x14000f91c  mov     rcx, r14; void *
0x14000f91f  call    memmove
0x14000f924  mov     eax, r13d
0x14000f927  jmp     loc_14000FA42
0x14000f92c  movups  xmm2, cs:CdXAAudioPhileHeader
0x14000f933  movups  [rsp+2A8h+var_238], xmm2
0x14000f938  movups  xmm0, cs:xmmword_1400070D8
0x14000f93f  movups  [rsp+2A8h+var_228], xmm0
0x14000f947  movups  xmm1, cs:xmmword_1400070D8+0Ch
0x14000f94e  movups  [rsp+2A8h+var_228+0Ch], xmm1
0x14000f956  mov     ecx, [rbx+20h]
0x14000f959  psrldq  xmm2, 4
0x14000f95e  movd    eax, xmm2
0x14000f962  add     eax, ecx
0x14000f964  mov     dword ptr [rsp+2A8h+var_238+4], eax
0x14000f968  psrldq  xmm1, 0Ch
0x14000f96d  movd    eax, xmm1
0x14000f971  add     eax, ecx
0x14000f973  mov     [rsp+2A8h+var_210], eax
0x14000f97a  sub     r13d, r15d
0x14000f97d  mov     r12d, r13d
0x14000f980  mov     eax, r13d
0x14000f983  mov     [rsp+2A8h+var_248], rax
0x14000f988  mov     [rsp+2A8h+var_250], eax
0x14000f98c  lea     rdx, [rsp+2A8h+var_20C]
0x14000f994  sub     rdx, r12; Src
0x14000f997  mov     r8d, r13d; Size
0x14000f99a  mov     rcx, r14; void *
0x14000f99d  call    memmove
0x14000f9a2  mov     eax, r12d
0x14000f9a5  jmp     loc_14000FA42
0x14000f9aa  movups  xmm2, cs:CdXAFileHeader
0x14000f9b1  movups  [rsp+2A8h+var_238], xmm2
0x14000f9b6  movups  xmm0, cs:xmmword_1400070A8
0x14000f9bd  movups  [rsp+2A8h+var_228], xmm0
0x14000f9c5  movups  xmm1, cs:xmmword_1400070A8+0Ch
0x14000f9cc  movups  [rsp+2A8h+var_228+0Ch], xmm1
0x14000f9d4  mov     ecx, [rbx+20h]
0x14000f9d7  psrldq  xmm2, 4
0x14000f9dc  movd    eax, xmm2
0x14000f9e0  add     eax, ecx
0x14000f9e2  mov     dword ptr [rsp+2A8h+var_238+4], eax
0x14000f9e6  psrldq  xmm1, 0Ch
0x14000f9eb  movd    eax, xmm1
0x14000f9ef  add     eax, ecx
0x14000f9f1  mov     [rsp+2A8h+var_210], eax
0x14000f9f8  movzx   eax, word ptr [rbx+0B4h]
0x14000f9ff  mov     word ptr [rsp+2A8h+var_228+8], ax
0x14000fa07  mov     al, [rbx+0B6h]
0x14000fa0d  mov     byte ptr [rsp+2A8h+var_228+0Ch], al
0x14000fa14  sub     r13d, r15d
0x14000fa17  mov     [rsp+2A8h+var_248], r13
0x14000fa1c  mov     [rsp+2A8h+var_250], r13d
0x14000fa21  mov     [rsp+2A8h+var_240], r13
0x14000fa26  lea     rdx, [rsp+2A8h+var_20C]
0x14000fa2e  sub     rdx, r13; Src
0x14000fa31  mov     r8d, r13d; Size
0x14000fa34  mov     rcx, r14; void *
0x14000fa37  call    memmove
0x14000fa3c  mov     r12d, r13d
0x14000fa3f  mov     eax, r13d
0x14000fa42  add     r14, rax
0x14000fa45  mov     [rsp+2A8h+var_1E8], r14
0x14000fa4d  mov     [rsp+2A8h+var_1FC], r12d
0x14000fa55  add     r15, rax
0x14000fa58  mov     [rsp+2A8h+var_1F0], r15
0x14000fa60  sub     esi, r12d
0x14000fa63  mov     [rsp+2A8h+var_200], esi
0x14000fa6a  mov     eax, [rbx+0ACh]
0x14000fa70  test    al, 4
0x14000fa72  jz      short loc_14000FA7C
0x14000fa74  mov     r13d, 1
0x14000fa7a  jmp     short loc_14000FA88
0x14000fa7c  movzx   r13d, al
0x14000fa80  shr     r13d, 3
0x14000fa84  and     r13d, 2
0x14000fa88  mov     [rsp+2A8h+var_204], r13d
0x14000fa90  mov     rcx, [rsp+2A8h+var_248]
0x14000fa95  test    esi, esi
0x14000fa97  jz      loc_14000FC23
0x14000fa9d  cmp     [rsp+2A8h+var_258], 0
0x14000faa2  jnz     short loc_14000FB16
0x14000faa4  xor     edx, edx; Val
0x14000faa6  mov     r8d, 140h; Size
0x14000faac  lea     rcx, [rsp+2A8h+var_188]; void *
0x14000fab4  call    memset
0x14000fab9  xor     edx, edx; Val
0x14000fabb  lea     r8d, [rdx+50h]; Size
0x14000fabf  lea     rcx, [rsp+2A8h+var_1D8]; void *
0x14000fac7  call    memset
0x14000facc  lea     rax, [rsp+2A8h+var_250]
0x14000fad1  mov     [rsp+2A8h+var_260], rax
0x14000fad6  lea     rax, [rsp+2A8h+var_24C]
0x14000fadb  mov     [rsp+2A8h+var_268], rax
0x14000fae0  lea     rax, [rsp+2A8h+var_188]
0x14000fae8  mov     [rsp+2A8h+var_270], rax
0x14000faed  mov     [rsp+2A8h+var_278], esi
0x14000faf1  mov     qword ptr [rsp+2A8h+Priority], r15
0x14000faf6  mov     [rsp+2A8h+BugCheckOnFailure], r12d
0x14000fafb  mov     r9, r14
0x14000fafe  mov     r8, rbx
0x14000fb01  mov     rdx, [rdi+8]
0x14000fb05  mov     rcx, rdi
0x14000fb08  call    CdPrepareXABuffers
0x14000fb0d  mov     ecx, [rsp+2A8h+var_250]
0x14000fb11  mov     [rsp+2A8h+var_248], rcx
0x14000fb16  mov     eax, [rsp+2A8h+var_24C]
0x14000fb1a  test    eax, eax
0x14000fb1c  jz      loc_14000FBF2
0x14000fb22  mov     dword ptr [rsp+2A8h+var_240], eax
0x14000fb26  mov     [rsp+2A8h+BugCheckOnFailure], r13d
0x14000fb2b  lea     r9, [rsp+2A8h+var_1D8]
0x14000fb33  lea     r8, [rsp+2A8h+var_188]
0x14000fb3b  mov     edx, eax
0x14000fb3d  mov     rcx, rdi
0x14000fb40  call    CdMultipleXAAsync
0x14000fb45  mov     rcx, rdi
0x14000fb48  call    CdWaitSync
0x14000fb4d  mov     rax, [rdi+8]
0x14000fb51  mov     eax, [rax+30h]
0x14000fb54  mov     [rsp+2A8h+var_208], eax
0x14000fb5b  mov     [rsp+2A8h+var_1F8], eax
0x14000fb62  test    eax, eax
0x14000fb64  jns     short loc_14000FBA1
0x14000fb66  cmp     [rsp+2A8h+var_258], 0
0x14000fb6b  jnz     loc_14000FC3D
0x14000fb71  mov     eax, [rbx+0ACh]
0x14000fb77  test    al, 4
0x14000fb79  jz      loc_14000FC3D
0x14000fb7f  mov     al, 1
0x14000fb81  mov     [rsp+2A8h+var_258], al
0x14000fb85  mov     [rsp+2A8h+var_257], al
0x14000fb89  xor     r13d, r13d
0x14000fb8c  mov     [rsp+2A8h+var_204], r13d
  ... truncated ...
```
