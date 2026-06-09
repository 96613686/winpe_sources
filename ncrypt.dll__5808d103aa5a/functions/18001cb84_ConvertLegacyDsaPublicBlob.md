# ConvertLegacyDsaPublicBlob

- ea: `0x18001cb84`
- end: `0x18001ce80`
- name: `ConvertLegacyDsaPublicBlob`
- size: `764`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017990`

## callees

- `0x18000e120`
- `0x1800146b0`
- `0x18001cb84`
- `0x18001f175`

## string_xrefs

- `0x18001ce57`: `onecore\ds\security\cryptoapi\ncrypt\common\translate.c`

## pseudocode

```c
__int64 __fastcall ConvertLegacyDsaPublicBlob(
        __int64 *a1,
        unsigned int a2,
        _DWORD *a3,
        unsigned int a4,
        unsigned int *a5)
{
  size_t v5; // r15
  __int64 v7; // rcx
  __int64 v8; // r9
  unsigned int v9; // ebx
  __int64 v10; // r9
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rax
  unsigned int v13; // edi
  __int128 *v14; // rbp
  int v15; // r14d
  __int64 v16; // rax
  __int64 v17; // xmm1_8
  __int128 v18; // xmm0
  __int64 v19; // xmm1_8
  unsigned __int64 v20; // xmm0_8
  unsigned int v21; // edi
  unsigned int v22; // eax
  __int64 *v23; // rbx
  __int64 v24; // r10
  __int64 v25; // r11
  __int64 v26; // r10
  __int64 v27; // r11
  __int64 v29; // [rsp+20h] [rbp-78h]
  __int128 v30; // [rsp+28h] [rbp-70h] BYREF
  __int64 v31; // [rsp+38h] [rbp-60h]
  __m128i v32; // [rsp+40h] [rbp-58h]
  __int128 v33; // [rsp+50h] [rbp-48h] BYREF
  __int64 v34; // [rsp+60h] [rbp-38h]

  v5 = a4;
  v31 = 0;
  v30 = 0;
  if ( !a1 || a2 < 8 )
  {
    v9 = -2146893785;
    v8 = 404;
    goto LABEL_31;
  }
  v29 = *a1;
  if ( (unsigned __int8)*a1 != 6 )
  {
    v7 = 2148073475LL;
    v8 = 418;
    v9 = -2146893821;
LABEL_32:
    DebugTraceError(v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\translate.c", v8);
    return v9;
  }
  if ( (unsigned __int8)(BYTE1(v29) - 2) > 1u || HIDWORD(v29) != 8704 )
  {
    v7 = 2148073475LL;
    v8 = 426;
    v9 = -2146893821;
    goto LABEL_32;
  }
  if ( BYTE1(v29) == 2 )
  {
    v10 = 2;
    if ( a2 < 0x10
      || (v11 = a1[1], (_DWORD)v11 != 827544388)
      || (v12 = HIDWORD(v11), (unsigned int)(v12 - 512) > 0xA00)
      || (v12 & 0x3F) != 0
      || a2 < (unsigned __int64)(3 * ((unsigned int)v12 >> 3)) + 60 )
    {
      v7 = 2148073475LL;
      v8 = 438;
      v9 = -2146893821;
      goto LABEL_32;
    }
    v13 = HIDWORD(a1[1]);
    v14 = &v30;
    v15 = 0;
    v16 = 3 * (v13 >> 3);
    v17 = *(__int64 *)((char *)a1 + v16 + 52);
    v30 = *(_OWORD *)((char *)a1 + v16 + 36);
    v31 = v17;
  }
  else
  {
    v10 = 6;
    if ( a2 < 0x30
      || (v18 = *(_OWORD *)(a1 + 3),
          v19 = a1[5],
          v32 = *(__m128i *)(a1 + 1),
          v34 = v19,
          v33 = v18,
          _mm_cvtsi128_si32(v32) != 861098820)
      || (unsigned int)(v32.m128i_i32[1] - 512) > 0xA00
      || (v32.m128i_i8[4] & 0x3F) != 0
      || _mm_cvtsi128_si32(_mm_srli_si128(v32, 8)) != 160
      || (v20 = _mm_srli_si128(v32, 8).m128i_u64[0], HIDWORD(v20) > 0xC00)
      || a2 < ((unsigned __int64)(unsigned int)(HIDWORD(v20) + 7) >> 3)
            + 3 * ((unsigned __int32)v32.m128i_i32[1] >> 3)
            + 68LL )
    {
      v7 = 2148073475LL;
      v8 = 467;
      v9 = -2146893821;
      goto LABEL_32;
    }
    v14 = &v33;
    v13 = _mm_cvtsi128_si32(_mm_srli_si128(v32, 4));
    v15 = _mm_cvtsi128_si32(_mm_srli_si128(v32, 12));
  }
  v21 = v13 >> 3;
  v22 = v21 + 2 * (v21 + 26);
  *a5 = v22;
  if ( a3 )
  {
    if ( (unsigned int)v5 >= v22 )
    {
      v23 = &a1[v10];
      memset_0(a3, 0, v5);
      *a3 = 1112560452;
      a3[1] = v21;
      ReverseMemCopy(a3 + 2, v14, 4);
      ReverseMemCopy(a3 + 3, (char *)v14 + 4, 20);
      ReverseMemCopy(a3 + 13, v23, (unsigned int)a3[1]);
      ReverseMemCopy(a3 + 8, (char *)v23 + (unsigned int)a3[1], 20);
      ReverseMemCopy(v25, v24 + 20, (unsigned int)a3[1]);
      ReverseMemCopy(v27 + (unsigned int)a3[1], v26 + a3[1] + ((unsigned int)(v15 + 7) >> 3), (unsigned int)a3[1]);
      return 0;
    }
    v9 = -2146893784;
    v8 = 493;
LABEL_31:
    v7 = v9;
    goto LABEL_32;
  }
  return 0;
}

```

## disassembly

```asm
0x18001cb84  mov     [rsp+arg_8], rbx
0x18001cb89  push    rbp
0x18001cb8a  push    rsi
0x18001cb8b  push    rdi
0x18001cb8c  push    r14
0x18001cb8e  push    r15
0x18001cb90  sub     rsp, 70h
0x18001cb94  mov     rbx, [rsp+98h+arg_20]
0x18001cb9c  xor     eax, eax
0x18001cb9e  mov     r15d, r9d
0x18001cba1  xorps   xmm0, xmm0
0x18001cba4  mov     r11d, edx
0x18001cba7  mov     rsi, r8
0x18001cbaa  mov     [rsp+98h+var_60], rax
0x18001cbaf  mov     r10, rcx
0x18001cbb2  movups  [rsp+98h+var_70], xmm0
0x18001cbb7  test    rcx, rcx
0x18001cbba  jz      loc_18001CE4A
0x18001cbc0  cmp     r11d, 8
0x18001cbc4  jb      loc_18001CE4A
0x18001cbca  mov     rax, [rcx]
0x18001cbcd  mov     [rsp+98h+var_78], rax
0x18001cbd2  cmp     al, 6
0x18001cbd4  jz      short loc_18001CBE8
0x18001cbd6  mov     ecx, 80090003h
0x18001cbdb  mov     r9d, 1A2h
0x18001cbe1  mov     ebx, ecx
0x18001cbe3  jmp     loc_18001CE57
0x18001cbe8  mov     al, byte ptr [rsp+98h+var_78+1]
0x18001cbec  sub     al, 2
0x18001cbee  cmp     al, 1
0x18001cbf0  ja      loc_18001CE3B
0x18001cbf6  cmp     dword ptr [rsp+98h+var_78+4], 2200h
0x18001cbfe  jnz     loc_18001CE3B
0x18001cc04  cmp     byte ptr [rsp+98h+var_78+1], 2
0x18001cc09  jnz     loc_18001CC92
0x18001cc0f  mov     r9d, 10h
0x18001cc15  cmp     r11d, r9d
0x18001cc18  jb      short loc_18001CC80
0x18001cc1a  mov     rax, [rcx+8]
0x18001cc1e  mov     [rsp+98h+var_78], rax
0x18001cc23  cmp     eax, 31535344h
0x18001cc28  jnz     short loc_18001CC80
0x18001cc2a  shr     rax, 20h
0x18001cc2e  lea     ecx, [rax-200h]
0x18001cc34  cmp     ecx, 0A00h
0x18001cc3a  ja      short loc_18001CC80
0x18001cc3c  test    al, 3Fh
0x18001cc3e  jnz     short loc_18001CC80
0x18001cc40  shr     eax, 3
0x18001cc43  lea     edx, [rax+rax*2]
0x18001cc46  add     rdx, 3Ch ; '<'
0x18001cc4a  cmp     r11, rdx
0x18001cc4d  jb      short loc_18001CC80
0x18001cc4f  mov     edi, dword ptr [rsp+98h+var_78+4]
0x18001cc53  lea     rbp, [rsp+98h+var_70]
0x18001cc58  mov     eax, edi
0x18001cc5a  xor     r14d, r14d
0x18001cc5d  shr     eax, 3
0x18001cc60  lea     eax, [rax+rax*2]
0x18001cc63  movups  xmm0, xmmword ptr [rax+r10+24h]
0x18001cc69  movsd   xmm1, qword ptr [rax+r10+34h]
0x18001cc70  movups  [rsp+98h+var_70], xmm0
0x18001cc75  movsd   [rsp+98h+var_60], xmm1
0x18001cc7b  jmp     loc_18001CD61
0x18001cc80  mov     ecx, 80090003h
0x18001cc85  mov     r9d, 1B6h
0x18001cc8b  mov     ebx, ecx
0x18001cc8d  jmp     loc_18001CE57
0x18001cc92  mov     r9d, 30h ; '0'
0x18001cc98  cmp     r11d, r9d
0x18001cc9b  jb      loc_18001CE2C
0x18001cca1  movups  xmm2, xmmword ptr [rcx+8]
0x18001cca5  movups  xmm0, xmmword ptr [rcx+18h]
0x18001cca9  movsd   xmm1, qword ptr [rcx+28h]
0x18001ccae  movd    eax, xmm2
0x18001ccb2  movups  [rsp+98h+var_58], xmm2
0x18001ccb7  movsd   [rsp+98h+var_38], xmm1
0x18001ccbd  movups  [rsp+98h+var_48], xmm0
0x18001ccc2  cmp     eax, 33535344h
0x18001ccc7  jnz     loc_18001CE2C
0x18001cccd  movq    rcx, xmm2
0x18001ccd2  shr     rcx, 20h
0x18001ccd6  lea     eax, [rcx-200h]
0x18001ccdc  cmp     eax, 0A00h
0x18001cce1  ja      loc_18001CE2C
0x18001cce7  test    cl, 3Fh
0x18001ccea  jnz     loc_18001CE2C
0x18001ccf0  movdqa  xmm0, xmm2
0x18001ccf4  psrldq  xmm0, 8
0x18001ccf9  movd    eax, xmm0
0x18001ccfd  cmp     eax, 0A0h
0x18001cd02  jnz     loc_18001CE2C
0x18001cd08  movdqa  xmm0, xmm2
0x18001cd0c  psrldq  xmm0, 8
0x18001cd11  movq    r8, xmm0
0x18001cd16  shr     r8, 20h
0x18001cd1a  cmp     r8d, 0C00h
0x18001cd21  ja      loc_18001CE2C
0x18001cd27  shr     ecx, 3
0x18001cd2a  lea     edx, [rcx+rcx*2]
0x18001cd2d  add     rdx, 44h ; 'D'
0x18001cd31  lea     ecx, [r8+7]
0x18001cd35  shr     rcx, 3
0x18001cd39  add     rdx, rcx
0x18001cd3c  cmp     r11, rdx
0x18001cd3f  jb      loc_18001CE2C
0x18001cd45  movdqa  xmm0, xmm2
0x18001cd49  lea     rbp, [rsp+98h+var_48]
0x18001cd4e  psrldq  xmm0, 4
0x18001cd53  psrldq  xmm2, 0Ch
0x18001cd58  movd    edi, xmm0
0x18001cd5c  movd    r14d, xmm2
0x18001cd61  shr     edi, 3
0x18001cd64  lea     eax, [rdi+1Ah]
0x18001cd67  lea     eax, [rdi+rax*2]
0x18001cd6a  mov     [rbx], eax
0x18001cd6c  test    rsi, rsi
0x18001cd6f  jnz     short loc_18001CD78
0x18001cd71  xor     ebx, ebx
0x18001cd73  jmp     loc_18001CE6A
0x18001cd78  cmp     r15d, eax
0x18001cd7b  jnb     short loc_18001CD8D
0x18001cd7d  mov     ebx, 80090028h
0x18001cd82  mov     r9d, 1EDh
0x18001cd88  jmp     loc_18001CE55
0x18001cd8d  mov     r8, r15; Size
0x18001cd90  lea     rbx, [r9+r10]
0x18001cd94  xor     edx, edx; Val
0x18001cd96  mov     rcx, rsi; void *
0x18001cd99  call    memset_0
0x18001cd9e  lea     rcx, [rsi+8]
0x18001cda2  mov     dword ptr [rsi], 42505344h
0x18001cda8  mov     r8d, 4
0x18001cdae  mov     [rsi+4], edi
0x18001cdb1  mov     rdx, rbp
0x18001cdb4  call    ReverseMemCopy
0x18001cdb9  mov     edi, 14h
0x18001cdbe  lea     rdx, [rbp+4]
0x18001cdc2  mov     r8d, edi
0x18001cdc5  lea     rcx, [rsi+0Ch]
0x18001cdc9  call    ReverseMemCopy
0x18001cdce  mov     r8d, [rsi+4]
0x18001cdd2  lea     r9, [rsi+34h]
0x18001cdd6  mov     rcx, r9
0x18001cdd9  mov     rdx, rbx
0x18001cddc  call    ReverseMemCopy
0x18001cde1  mov     ecx, [rsi+4]
0x18001cde4  mov     r8d, edi
0x18001cde7  lea     r10, [rcx+rbx]
0x18001cdeb  lea     r11, [rcx+r9]
0x18001cdef  mov     rdx, r10
0x18001cdf2  lea     rcx, [rsi+20h]
0x18001cdf6  call    ReverseMemCopy
0x18001cdfb  mov     r8d, [rsi+4]
0x18001cdff  add     r10, rdi
0x18001ce02  mov     rdx, r10
0x18001ce05  mov     rcx, r11
0x18001ce08  call    ReverseMemCopy
0x18001ce0d  mov     r8d, [rsi+4]
0x18001ce11  lea     edx, [r14+7]
0x18001ce15  shr     edx, 3
0x18001ce18  add     edx, r8d
0x18001ce1b  add     rdx, r10
0x18001ce1e  lea     rcx, [r11+r8]
0x18001ce22  call    ReverseMemCopy
0x18001ce27  jmp     loc_18001CD71
0x18001ce2c  mov     ecx, 80090003h
0x18001ce31  mov     r9d, 1D3h
0x18001ce37  mov     ebx, ecx
0x18001ce39  jmp     short loc_18001CE57
0x18001ce3b  mov     ecx, 80090003h
0x18001ce40  mov     r9d, 1AAh
0x18001ce46  mov     ebx, ecx
0x18001ce48  jmp     short loc_18001CE57
0x18001ce4a  mov     ebx, 80090027h
0x18001ce4f  mov     r9d, 194h
0x18001ce55  mov     ecx, ebx
0x18001ce57  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ce5e  lea     rdx, aStatus; "Status"
0x18001ce65  call    DebugTraceError
0x18001ce6a  mov     eax, ebx
0x18001ce6c  mov     rbx, [rsp+98h+arg_8]
0x18001ce74  add     rsp, 70h
0x18001ce78  pop     r15
0x18001ce7a  pop     r14
0x18001ce7c  pop     rdi
0x18001ce7d  pop     rsi
0x18001ce7e  pop     rbp
0x18001ce7f  retn
```
