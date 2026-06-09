# CoconetChunker::ComputeChunksUsingSampleByteHash(uint,uchar const *,uint,int,CoconetChunker::_CHUNK *,uint,uint *)

- ea: `0x180027b74`
- end: `0x180027f71`
- name: `?ComputeChunksUsingSampleByteHash@CoconetChunker@@QEAA_NIPEBEIHPEAU_CHUNK@1@IPEAI@Z`
- size: `1021`
- prototype: `bool __fastcall(CoconetChunker *__hidden this, unsigned int, const unsigned __int8 *, unsigned int, int, struct CoconetChunker::_CHUNK *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800272c8`

## callees

- `0x180027b74`

## pseudocode

```c
char __fastcall CoconetChunker::ComputeChunksUsingSampleByteHash(
        CoconetChunker *this,
        int a2,
        const unsigned __int8 *a3,
        int a4,
        int a5,
        struct CoconetChunker::_CHUNK *a6,
        unsigned int a7,
        unsigned int *a8)
{
  int v8; // r10d
  int v9; // esi
  int v10; // ebp
  unsigned int v13; // r11d
  int v14; // edx
  const unsigned __int8 *v15; // rdi
  int v16; // ecx
  int v17; // r8d
  int v18; // edx
  int v19; // eax
  int v20; // ecx
  int v21; // edx
  int v22; // eax
  int v23; // r9d
  int v24; // edx
  int v25; // r8d
  int v26; // ecx
  int v27; // ecx
  int v28; // r8d
  int v29; // r8d
  int v30; // r9d
  int v31; // eax
  int v32; // ecx
  int v33; // edx
  __int64 v34; // rax
  const unsigned __int8 *v35; // r10
  int v36; // ecx
  int v37; // r8d
  int v38; // edx
  int v39; // eax
  int v40; // ecx
  int v41; // edx
  int v42; // r9d
  int v43; // edx
  int v44; // ecx
  int v45; // r8d
  int v46; // eax
  int v47; // ecx
  int v48; // r8d
  int v49; // r8d
  int v50; // r9d
  int v51; // eax
  int v52; // ecx
  int v53; // edx

  v8 = a4 + 1;
  v9 = a4;
  v10 = a5 - 12;
  v13 = *a8;
  if ( a4 + 1 < a5 - 12 )
  {
    while ( 1 )
    {
      if ( *((_BYTE *)&CoconetChunker::m_sampleByteHash + a3[v8]) == 1 )
        goto LABEL_14;
      if ( *((_BYTE *)&CoconetChunker::m_sampleByteHash + a3[v8 + 1]) == 1 )
      {
        ++v8;
        goto LABEL_14;
      }
      v8 += 2;
      if ( *((_BYTE *)&CoconetChunker::m_sampleByteHash + a3[v8]) == 1 )
        goto LABEL_14;
      if ( *((_BYTE *)&CoconetChunker::m_sampleByteHash + a3[v8 + 1]) == 1 )
        break;
      v8 += 2;
      if ( *((_BYTE *)&CoconetChunker::m_sampleByteHash + a3[v8]) == 1 )
        goto LABEL_14;
      if ( *((_BYTE *)&CoconetChunker::m_sampleByteHash + a3[v8 + 1]) == 1 )
        break;
      v14 = v8 + 2;
      if ( *((_BYTE *)&CoconetChunker::m_sampleByteHash + a3[v8 + 2]) == 1 )
      {
        v8 += 2;
LABEL_14:
        if ( v13 < 0x1194 )
        {
          v15 = &a3[v9];
          if ( ((unsigned __int8)v15 & 3) != 0 )
          {
            if ( ((unsigned __int8)v15 & 1) != 0 )
            {
              v23 = ((v15[5] + ((v15[6] + (v15[7] << 8)) << 8)) << 8) - 559038725 + v15[4];
              v24 = ((v15[9] + ((v15[10] + (v15[11] << 8)) << 8)) << 8) - 559038725 + v15[8];
              v25 = __ROR4__(v24, 28);
              v22 = *v15;
              v26 = (v15[1] + ((v15[2] + (v15[3] << 8)) << 8)) << 8;
            }
            else
            {
              v22 = *(unsigned __int16 *)v15;
              v23 = (*((unsigned __int16 *)v15 + 3) << 16) - 559038725 + *((unsigned __int16 *)v15 + 2);
              v24 = (*((unsigned __int16 *)v15 + 5) << 16) - 559038725 + *((unsigned __int16 *)v15 + 4);
              v25 = __ROR4__(v24, 28);
              v26 = *((unsigned __int16 *)v15 + 1) << 16;
            }
            v27 = v22 + v26;
            v19 = v24 + v23;
            v28 = (v27 - v24 - 559038725) ^ v25;
            v20 = (v23 - v28) ^ __ROR4__(v28, 26);
            v21 = v24 + v23 + v28;
          }
          else
          {
            v16 = *((_DWORD *)v15 + 2) - 559038725;
            v17 = *((_DWORD *)v15 + 1) - 559038725;
            v18 = (*(_DWORD *)v15 - *((_DWORD *)v15 + 2)) ^ __ROR4__(v16, 28);
            v19 = v16 + v17;
            v20 = (v17 - v18) ^ __ROR4__(v18, 26);
            v21 = v19 + v18;
          }
          v29 = v21 + v20;
          v30 = (v19 - v20) ^ __ROR4__(v20, 24);
          v31 = v21 + v20;
          v32 = (v21 - v30) ^ __ROR4__(v30, 16);
          v33 = (v31 - v32) ^ __ROR4__(v32, 13);
          v34 = v13;
          *((_DWORD *)a6 + 2 * v13++) = (v30 + v29 - v33) ^ __ROR4__(v33, 28);
          *((_DWORD *)a6 + 2 * v34 + 1) = v9;
        }
        v9 = v8;
        v8 += a2;
        goto LABEL_23;
      }
      v8 += 3;
      if ( *((_BYTE *)&CoconetChunker::m_sampleByteHash + a3[v14 + 1]) == 1 )
        goto LABEL_14;
LABEL_23:
      if ( ++v8 >= v10 )
        goto LABEL_24;
    }
    ++v8;
    goto LABEL_14;
  }
LABEL_24:
  if ( v9 <= v10 && v13 < 0x1194 )
  {
    v35 = &a3[v9];
    if ( ((unsigned __int8)v35 & 3) != 0 )
    {
      if ( ((unsigned __int8)v35 & 1) != 0 )
      {
        v42 = ((v35[5] + ((v35[6] + (v35[7] << 8)) << 8)) << 8) - 559038725 + v35[4];
        v43 = ((v35[9] + ((v35[10] + (v35[11] << 8)) << 8)) << 8) - 559038725 + v35[8];
        v45 = __ROR4__(v43, 28);
        v46 = *v35;
        v44 = ((v35[1] + ((v35[2] + (v35[3] << 8)) << 8)) << 8)
            - (((v35[9] + ((v35[10] + (v35[11] << 8)) << 8)) << 8)
             + v35[8]);
      }
      else
      {
        v42 = (*((unsigned __int16 *)v35 + 3) << 16) - 559038725 + *((unsigned __int16 *)v35 + 2);
        v43 = (*((unsigned __int16 *)v35 + 5) << 16) - 559038725 + *((unsigned __int16 *)v35 + 4);
        v44 = (*((unsigned __int16 *)v35 + 1) << 16) - v43;
        v45 = __ROR4__(v43, 28);
        v46 = *(unsigned __int16 *)v35 - 559038725;
      }
      v47 = v46 + v44;
      v39 = v43 + v42;
      v48 = v47 ^ v45;
      v40 = (v42 - v48) ^ __ROR4__(v48, 26);
      v41 = v48 + v43 + v42;
    }
    else
    {
      v36 = *((_DWORD *)v35 + 2) - 559038725;
      v37 = *((_DWORD *)v35 + 1) - 559038725;
      v38 = (*(_DWORD *)v35 - *((_DWORD *)v35 + 2)) ^ __ROR4__(v36, 28);
      v39 = v36 + v37;
      v40 = (v37 - v38) ^ __ROR4__(v38, 26);
      v41 = v39 + v38;
    }
    v49 = v41 + v40;
    v50 = (v39 - v40) ^ __ROR4__(v40, 24);
    v51 = v41 + v40;
    v52 = (v41 - v50) ^ __ROR4__(v50, 16);
    v53 = (v51 - v52) ^ __ROR4__(v52, 13);
    *((_DWORD *)a6 + 2 * v13 + 1) = v9;
    *((_DWORD *)a6 + 2 * v13++) = (v50 + v49 - v53) ^ __ROR4__(v53, 28);
  }
  if ( v13 == *a8 )
    return 0;
  *a8 = v13;
  return 1;
}

```

## disassembly

```asm
0x180027b74  push    rbx
0x180027b76  push    rbp
0x180027b77  push    rsi
0x180027b78  push    rdi
0x180027b79  push    r12
0x180027b7b  push    r14
0x180027b7d  push    r15
0x180027b7f  mov     r15, [rsp+38h+arg_38]
0x180027b84  lea     r10d, [r9+1]
0x180027b88  mov     ebp, [rsp+38h+arg_20]
0x180027b8c  mov     esi, r9d
0x180027b8f  mov     r14, [rsp+38h+arg_28]
0x180027b94  sub     ebp, 0Ch
0x180027b97  mov     rbx, r8
0x180027b9a  mov     r12d, edx
0x180027b9d  mov     r11d, [r15]
0x180027ba0  cmp     r10d, ebp
0x180027ba3  jge     loc_180027DCC
0x180027ba9  lea     r8, ?m_sampleByteHash@CoconetChunker@@0QBEB; uchar const near * const CoconetChunker::m_sampleByteHash
0x180027bb0  movsxd  rax, r10d
0x180027bb3  movzx   ecx, byte ptr [rax+rbx]
0x180027bb7  cmp     byte ptr [rcx+r8], 1
0x180027bbc  jz      loc_180027C4B
0x180027bc2  movsxd  rax, r10d
0x180027bc5  movzx   ecx, byte ptr [rax+rbx+1]
0x180027bca  cmp     byte ptr [rcx+r8], 1
0x180027bcf  jz      short loc_180027C48
0x180027bd1  add     r10d, 2
0x180027bd5  movsxd  rax, r10d
0x180027bd8  movzx   ecx, byte ptr [rax+rbx]
0x180027bdc  cmp     byte ptr [rcx+r8], 1
0x180027be1  jz      short loc_180027C4B
0x180027be3  movsxd  rax, r10d
0x180027be6  movzx   ecx, byte ptr [rax+rbx+1]
0x180027beb  cmp     byte ptr [rcx+r8], 1
0x180027bf0  jz      short loc_180027C43
0x180027bf2  add     r10d, 2
0x180027bf6  movsxd  rax, r10d
0x180027bf9  movzx   ecx, byte ptr [rax+rbx]
0x180027bfd  cmp     byte ptr [rcx+r8], 1
0x180027c02  jz      short loc_180027C4B
0x180027c04  movsxd  rax, r10d
0x180027c07  movzx   ecx, byte ptr [rax+rbx+1]
0x180027c0c  cmp     byte ptr [rcx+r8], 1
0x180027c11  jz      short loc_180027C43
0x180027c13  lea     edx, [r10+2]
0x180027c17  movsxd  rax, edx
0x180027c1a  movzx   ecx, byte ptr [rax+rbx]
0x180027c1e  cmp     byte ptr [rcx+r8], 1
0x180027c23  jz      short loc_180027C3E
0x180027c25  movsxd  rax, edx
0x180027c28  lea     r10d, [rdx+1]
0x180027c2c  movzx   ecx, byte ptr [rax+rbx+1]
0x180027c31  cmp     byte ptr [rcx+r8], 1
0x180027c36  jnz     loc_180027DC0
0x180027c3c  jmp     short loc_180027C4B
0x180027c3e  mov     r10d, edx
0x180027c41  jmp     short loc_180027C4B
0x180027c43  inc     r10d
0x180027c46  jmp     short loc_180027C4B
0x180027c48  inc     r10d
0x180027c4b  cmp     r11d, 1194h
0x180027c52  jnb     loc_180027DBA
0x180027c58  movsxd  rdi, esi
0x180027c5b  add     rdi, rbx
0x180027c5e  test    dil, 3
0x180027c62  jnz     short loc_180027C9E
0x180027c64  mov     ecx, [rdi+8]
0x180027c67  mov     r8d, [rdi+4]
0x180027c6b  add     ecx, 0DEADBEFBh
0x180027c71  mov     eax, [rdi]
0x180027c73  mov     edx, ecx
0x180027c75  sub     eax, ecx
0x180027c77  ror     edx, 1Ch
0x180027c7a  add     r8d, 0DEADBEFBh
0x180027c81  sub     eax, 21524105h
0x180027c86  xor     edx, eax
0x180027c88  lea     eax, [rcx+r8]
0x180027c8c  mov     ecx, edx
0x180027c8e  ror     ecx, 1Ah
0x180027c91  sub     r8d, edx
0x180027c94  xor     ecx, r8d
0x180027c97  add     edx, eax
0x180027c99  jmp     loc_180027D6F
0x180027c9e  test    dil, 1
0x180027ca2  jnz     short loc_180027CDF
0x180027ca4  movzx   ecx, word ptr [rdi+6]
0x180027ca8  movzx   r9d, word ptr [rdi+4]
0x180027cad  movzx   edx, word ptr [rdi+8]
0x180027cb1  movzx   eax, word ptr [rdi]
0x180027cb4  shl     ecx, 10h
0x180027cb7  add     ecx, 0DEADBEFBh
0x180027cbd  add     r9d, ecx
0x180027cc0  movzx   ecx, word ptr [rdi+0Ah]
0x180027cc4  shl     ecx, 10h
0x180027cc7  add     ecx, 0DEADBEFBh
0x180027ccd  add     edx, ecx
0x180027ccf  movzx   ecx, word ptr [rdi+2]
0x180027cd3  mov     r8d, edx
0x180027cd6  ror     r8d, 1Ch
0x180027cda  shl     ecx, 10h
0x180027cdd  jmp     short loc_180027D4E
0x180027cdf  movzx   eax, byte ptr [rdi+6]
0x180027ce3  movzx   ecx, byte ptr [rdi+7]
0x180027ce7  movzx   r9d, byte ptr [rdi+4]
0x180027cec  movzx   edx, byte ptr [rdi+8]
0x180027cf0  shl     ecx, 8
0x180027cf3  add     ecx, eax
0x180027cf5  movzx   eax, byte ptr [rdi+5]
0x180027cf9  shl     ecx, 8
0x180027cfc  add     ecx, eax
0x180027cfe  movzx   eax, byte ptr [rdi+0Ah]
0x180027d02  shl     ecx, 8
0x180027d05  add     ecx, 0DEADBEFBh
0x180027d0b  add     r9d, ecx
0x180027d0e  movzx   ecx, byte ptr [rdi+0Bh]
0x180027d12  shl     ecx, 8
0x180027d15  add     ecx, eax
0x180027d17  movzx   eax, byte ptr [rdi+9]
0x180027d1b  shl     ecx, 8
0x180027d1e  add     ecx, eax
0x180027d20  movzx   eax, byte ptr [rdi+2]
0x180027d24  shl     ecx, 8
0x180027d27  add     ecx, 0DEADBEFBh
0x180027d2d  add     edx, ecx
0x180027d2f  movzx   ecx, byte ptr [rdi+3]
0x180027d33  shl     ecx, 8
0x180027d36  mov     r8d, edx
0x180027d39  add     ecx, eax
0x180027d3b  ror     r8d, 1Ch
0x180027d3f  movzx   eax, byte ptr [rdi+1]
0x180027d43  shl     ecx, 8
0x180027d46  add     ecx, eax
0x180027d48  movzx   eax, byte ptr [rdi]
0x180027d4b  shl     ecx, 8
0x180027d4e  add     ecx, eax
0x180027d50  lea     eax, [rdx+r9]
0x180027d54  sub     ecx, edx
0x180027d56  sub     ecx, 21524105h
0x180027d5c  xor     r8d, ecx
0x180027d5f  mov     ecx, r8d
0x180027d62  sub     r9d, r8d
0x180027d65  ror     ecx, 1Ah
0x180027d68  xor     ecx, r9d
0x180027d6b  lea     edx, [rax+r8]
0x180027d6f  lea     r8d, [rdx+rcx]
0x180027d73  sub     eax, ecx
0x180027d75  mov     r9d, ecx
0x180027d78  ror     r9d, 18h
0x180027d7c  xor     r9d, eax
0x180027d7f  mov     eax, r8d
0x180027d82  sub     edx, r9d
0x180027d85  mov     ecx, r9d
0x180027d88  ror     ecx, 10h
0x180027d8b  xor     ecx, edx
0x180027d8d  sub     eax, ecx
0x180027d8f  mov     edx, ecx
0x180027d91  ror     edx, 0Dh
0x180027d94  xor     edx, eax
0x180027d96  mov     eax, r11d
0x180027d99  sub     r8d, edx
0x180027d9c  mov     ecx, edx
0x180027d9e  add     r8d, r9d
0x180027da1  ror     ecx, 1Ch
0x180027da4  xor     ecx, r8d
0x180027da7  lea     r8, ?m_sampleByteHash@CoconetChunker@@0QBEB; uchar const near * const CoconetChunker::m_sampleByteHash
0x180027dae  mov     [r14+rax*8], ecx
0x180027db2  inc     r11d
0x180027db5  mov     [r14+rax*8+4], esi
0x180027dba  mov     esi, r10d
0x180027dbd  add     r10d, r12d
0x180027dc0  inc     r10d
0x180027dc3  cmp     r10d, ebp
0x180027dc6  jl      loc_180027BB0
0x180027dcc  cmp     esi, ebp
0x180027dce  jg      loc_180027F58
0x180027dd4  cmp     r11d, 1194h
0x180027ddb  jnb     loc_180027F58
0x180027de1  movsxd  r10, esi
0x180027de4  add     r10, rbx
0x180027de7  test    r10b, 3
0x180027deb  jnz     short loc_180027E29
0x180027ded  mov     ecx, [r10+8]
0x180027df1  mov     r8d, [r10+4]
0x180027df5  add     ecx, 0DEADBEFBh
0x180027dfb  mov     eax, [r10]
0x180027dfe  mov     edx, ecx
0x180027e00  sub     eax, ecx
0x180027e02  ror     edx, 1Ch
0x180027e05  add     r8d, 0DEADBEFBh
0x180027e0c  sub     eax, 21524105h
0x180027e11  xor     edx, eax
0x180027e13  lea     eax, [rcx+r8]
0x180027e17  mov     ecx, edx
0x180027e19  ror     ecx, 1Ah
0x180027e1c  sub     r8d, edx
0x180027e1f  xor     ecx, r8d
0x180027e22  add     edx, eax
0x180027e24  jmp     loc_180027F14
0x180027e29  test    r10b, 1
0x180027e2d  jnz     short loc_180027E79
0x180027e2f  movzx   ecx, word ptr [r10+6]
0x180027e34  movzx   r9d, word ptr [r10+4]
0x180027e39  movzx   edx, word ptr [r10+8]
0x180027e3e  movzx   eax, word ptr [r10]
0x180027e42  shl     ecx, 10h
0x180027e45  add     ecx, 0DEADBEFBh
0x180027e4b  add     r9d, ecx
0x180027e4e  movzx   ecx, word ptr [r10+0Ah]
0x180027e53  shl     ecx, 10h
0x180027e56  add     ecx, 0DEADBEFBh
0x180027e5c  add     edx, ecx
0x180027e5e  movzx   ecx, word ptr [r10+2]
0x180027e63  shl     ecx, 10h
0x180027e66  mov     r8d, edx
0x180027e69  sub     ecx, edx
0x180027e6b  ror     r8d, 1Ch
0x180027e6f  add     eax, 0DEADBEFBh
0x180027e74  jmp     loc_180027EFB
0x180027e79  movzx   eax, byte ptr [r10+6]
0x180027e7e  movzx   ecx, byte ptr [r10+7]
0x180027e83  movzx   r9d, byte ptr [r10+4]
0x180027e88  movzx   edx, byte ptr [r10+8]
0x180027e8d  shl     ecx, 8
0x180027e90  add     ecx, eax
0x180027e92  movzx   eax, byte ptr [r10+5]
0x180027e97  shl     ecx, 8
0x180027e9a  add     ecx, eax
0x180027e9c  movzx   eax, byte ptr [r10+0Ah]
0x180027ea1  shl     ecx, 8
0x180027ea4  add     ecx, 0DEADBEFBh
0x180027eaa  add     r9d, ecx
0x180027ead  movzx   ecx, byte ptr [r10+0Bh]
0x180027eb2  shl     ecx, 8
0x180027eb5  add     ecx, eax
0x180027eb7  movzx   eax, byte ptr [r10+9]
0x180027ebc  shl     ecx, 8
0x180027ebf  add     ecx, eax
0x180027ec1  movzx   eax, byte ptr [r10+2]
0x180027ec6  shl     ecx, 8
0x180027ec9  add     ecx, 0DEADBEFBh
0x180027ecf  add     edx, ecx
0x180027ed1  movzx   ecx, byte ptr [r10+3]
0x180027ed6  shl     ecx, 8
0x180027ed9  mov     r8d, edx
0x180027edc  add     ecx, eax
0x180027ede  ror     r8d, 1Ch
0x180027ee2  movzx   eax, byte ptr [r10+1]
0x180027ee7  shl     ecx, 8
0x180027eea  add     ecx, eax
0x180027eec  movzx   eax, byte ptr [r10]
0x180027ef0  shl     ecx, 8
0x180027ef3  sub     ecx, edx
0x180027ef5  add     ecx, 0DEADBEFBh
0x180027efb  add     ecx, eax
0x180027efd  lea     eax, [rdx+r9]
0x180027f01  xor     r8d, ecx
0x180027f04  mov     ecx, r8d
0x180027f07  sub     r9d, r8d
0x180027f0a  ror     ecx, 1Ah
0x180027f0d  xor     ecx, r9d
0x180027f10  lea     edx, [r8+rax]
0x180027f14  sub     eax, ecx
0x180027f16  lea     r8d, [rdx+rcx]
0x180027f1a  mov     r9d, ecx
0x180027f1d  ror     r9d, 18h
0x180027f21  xor     r9d, eax
0x180027f24  mov     eax, r8d
0x180027f27  sub     edx, r9d
0x180027f2a  mov     ecx, r9d
0x180027f2d  ror     ecx, 10h
0x180027f30  xor     ecx, edx
0x180027f32  sub     eax, ecx
0x180027f34  mov     edx, ecx
0x180027f36  mov     ecx, r11d
0x180027f39  ror     edx, 0Dh
0x180027f3c  xor     edx, eax
0x180027f3e  sub     r8d, edx
0x180027f41  mov     eax, edx
0x180027f43  add     r8d, r9d
0x180027f46  ror     eax, 1Ch
0x180027f49  xor     eax, r8d
0x180027f4c  mov     [r14+rcx*8+4], esi
0x180027f51  mov     [r14+rcx*8], eax
0x180027f55  inc     r11d
0x180027f58  cmp     r11d, [r15]
0x180027f5b  jz      short loc_180027F64
0x180027f5d  mov     [r15], r11d
0x180027f60  mov     al, 1
0x180027f62  jmp     short loc_180027F66
0x180027f64  xor     al, al
0x180027f66  pop     r15
0x180027f68  pop     r14
0x180027f6a  pop     r12
0x180027f6c  pop     rdi
0x180027f6d  pop     rsi
0x180027f6e  pop     rbp
0x180027f6f  pop     rbx
0x180027f70  retn
```
