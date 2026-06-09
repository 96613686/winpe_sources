# WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::Decrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar,int)

- ea: `0x180020d30`
- end: `0x180021309`
- name: `?Decrypt@?$CEncryption@$04V?$CCipherFeistel64@$0BM@$0NJ@$0MM@$0HO@$0N@$0DA@$0NP@$0NA@$0BB@$0NG@$0MK@$0NP@$0BC@$0LO@$0KF@$0IJ@$07$0KN@$0NK@$0PM@$0L@$0DO@$0KH@$0LN@$0O@$0FN@$0CA@$0CD@$0BO@$0FL@$0JF@$0CD@$01$0OH@$0EK@$0LG@$0BI@$0ON@$0HO@$0KJ@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$00$01$0CAFEBNIPCLCBHOGE@@2@UENCRYPTED_SEGMENT_DATA_CONST_6@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@KEH@Z`
- size: `1497`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180022f00`

## callees

- `0x1800017b0`
- `0x180020d30`
- `0x180025230`

## pseudocode

```c
void __fastcall WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::Decrypt(
        char *a1,
        _BYTE *a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        int a5,
        char a6,
        int a7)
{
  unsigned __int64 v7; // rbp
  _BYTE *v8; // r14
  char *v9; // r15
  volatile unsigned int v10; // edi
  char *v11; // r13
  unsigned int v12; // r11d
  signed int v13; // r8d
  signed int v14; // r10d
  unsigned int v15; // edx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned __int64 v18; // rbx
  char v19; // si
  volatile unsigned int v20; // r10d
  unsigned int v21; // r8d
  unsigned int v22; // ecx
  char *v23; // r11
  signed __int64 v24; // r8
  bool v25; // zf
  char v26; // di
  int v27; // ecx
  int v28; // ebx
  __int64 v29; // rsi
  int v30; // edi
  unsigned int v31; // r8d
  int v32; // r10d
  int v33; // r11d
  unsigned int v34; // r8d
  int v35; // r10d
  int v36; // r11d
  int v37; // ecx
  int v38; // edi
  int v39; // ebx
  __int64 v40; // rcx
  char *v41; // r8
  _BYTE *v42; // r10
  char v43; // al
  char *v44; // r8
  __int64 v45; // rax
  __int64 v46; // r8
  char *v47; // r10
  _BYTE *v48; // r11
  char v49; // al
  __int64 *v50; // r8
  unsigned __int64 v51; // r13
  __int64 v52; // rax
  int v53; // r10d
  unsigned int v54; // ebx
  int v55; // r11d
  int v56; // r10d
  int v57; // ebx
  unsigned int v58; // r11d
  int v59; // r10d
  int v60; // ebx
  int v61; // r11d
  _QWORD *v62; // r8
  int v63; // r10d
  volatile unsigned int v64; // r11d
  char *v65; // r10
  unsigned int v66; // r8d
  unsigned int v67; // ecx
  char *v68; // r9
  signed __int64 v69; // r8
  char v70; // [rsp+20h] [rbp-A8h]
  unsigned int v71; // [rsp+24h] [rbp-A4h]
  __int64 v72; // [rsp+28h] [rbp-A0h] BYREF
  unsigned int v73; // [rsp+30h] [rbp-98h]
  __int64 *v74; // [rsp+38h] [rbp-90h]
  _QWORD *v75; // [rsp+40h] [rbp-88h] BYREF
  volatile unsigned int v76; // [rsp+48h] [rbp-80h]
  char *v77; // [rsp+50h] [rbp-78h]
  unsigned __int64 v78; // [rsp+58h] [rbp-70h]
  _BYTE *v79; // [rsp+60h] [rbp-68h]
  char *v80; // [rsp+68h] [rbp-60h]

  v7 = a3;
  v8 = a2;
  v9 = a1;
  v80 = a1;
  v78 = a3;
  v79 = a2;
  if ( a7 )
  {
    v10 = WarbirdRuntime::g_PrivateRelocationsTableCount;
    v11 = (char *)&_ImageBase + WarbirdRuntime::g_PrivateRelocationsTable;
    v12 = (_DWORD)a1 - (unsigned int)&_ImageBase;
    v77 = v11;
    v76 = WarbirdRuntime::g_PrivateRelocationsTableCount;
    v13 = 0;
    v14 = WarbirdRuntime::g_PrivateRelocationsTableCount - 1;
    while ( v14 >= v13 )
    {
      v15 = (v14 + v13) / 2;
      v73 = v15;
      v16 = *(_DWORD *)&v11[4 * v15] & 0xFFFFFFF;
      if ( v12 >= v16 )
      {
        if ( v12 <= v16 )
          goto LABEL_9;
        v13 = v15 + 1;
      }
      else
      {
        v14 = v15 - 1;
      }
    }
    v15 = v13;
    v73 = v13;
LABEL_9:
    v17 = v12 + v7;
    v71 = v12 + v7;
    v18 = WarbirdRuntime::g_preferedImageBase - (_QWORD)&_ImageBase;
    v19 = v7;
    v20 = v15;
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          if ( v20 >= v10 )
            goto LABEL_20;
          v21 = *(_DWORD *)&v11[4 * v20];
          if ( (v21 & 0xFFFFFFF) >= v17 )
            goto LABEL_20;
          ++v20;
          v22 = v21 >> 28;
          if ( v21 >> 28 )
            break;
          v17 = v71;
        }
        v23 = (char *)&_ImageBase + (v21 & 0xFFFFFFF);
        v24 = v23 - v9;
        if ( v22 != 3 )
          break;
        *(_DWORD *)&v8[v24] = v18 + *(_DWORD *)v23;
LABEL_11:
        v17 = v71;
      }
      v25 = v22 == 10;
      v17 = v71;
      if ( v25 )
      {
        *(_QWORD *)&v8[v24] = v18 + *(_QWORD *)v23;
        goto LABEL_11;
      }
    }
  }
  v11 = 0;
  v15 = (unsigned int)v74;
  v19 = a3;
  v71 = (unsigned int)v74;
  v73 = (unsigned int)v74;
  v77 = 0;
  v76 = 0;
LABEL_20:
  v26 = 0;
  v70 = 0;
  if ( v7 )
  {
    v72 = 0;
    v27 = ~a5;
    LODWORD(v74) = v19 & 7;
    if ( (v19 & 7) != 0 )
    {
      v75 = 0;
      v31 = v27 ^ (WORD2(a4) * (WORD1(a4) + __ROR4__(v27, 13)));
      v32 = v31 ^ ((a5 ^ (v31 >> 15) ^ ((unsigned __int16)a4 * (WORD1(a4) ^ v31))) - HIWORD(a4) - a4);
      v33 = a5
          ^ (v31 >> 15)
          ^ ((unsigned __int16)a4 * (WORD1(a4) ^ v31))
          ^ (__ROR4__(v32, 5) + WORD2(a4) * __ROR4__(a4 ^ v32, 2));
      v34 = v32 ^ __ROR4__(v33, 4) ^ (WORD1(a4) * __ROL4__(v33 ^ (unsigned __int16)a4, 7));
      v35 = v33 ^ (v34 >> 13) ^ ((unsigned __int16)a4 * __ROL4__(v34 - HIWORD(a4), 2));
      v36 = v34 ^ __ROR4__(v35, 14) ^ (HIWORD(a4) * __ROR4__(v35 - a4, 11));
      v37 = v35 ^ (WORD2(a4) * __ROR4__(a4 ^ v36, 17) - __ROR4__(v36, 7));
      v29 = (unsigned int)v74;
      v38 = v36 ^ (__ROR4__(v37, 23) + WORD1(a4) * __ROR4__(HIDWORD(a4) - v37, 7));
      v39 = v37 ^ v38 ^ HIDWORD(a4) ^ a4;
      v40 = (unsigned int)v74;
      v41 = v9;
      v42 = &v75;
      do
      {
        v43 = *v41++;
        *v42++ = v43;
        --v40;
      }
      while ( v40 );
      v27 = (int)v75;
      v44 = (char *)&v72 + v29;
      a5 = HIDWORD(v75);
      HIDWORD(v72) = HIDWORD(v75) ^ v39;
      LODWORD(v72) = (unsigned int)v75 ^ v38;
      v45 = 8 - v29;
      do
      {
        *v44++ = 0;
        --v45;
      }
      while ( v45 );
      v28 = HIDWORD(v72);
      v30 = v72;
      v46 = v29;
      v47 = (char *)&v72;
      v48 = v8;
      do
      {
        v49 = *v47++;
        *v48++ = v49;
        --v46;
      }
      while ( v46 );
      v7 = v78;
    }
    else
    {
      v28 = HIDWORD(v72);
      v29 = 0;
      v30 = 0;
    }
    v75 = &v8[v29];
    v50 = (__int64 *)&v9[v29];
    if ( v7 >> 3 )
    {
      v51 = 0;
      do
      {
        v52 = *v50;
        v74 = v50 + 1;
        v53 = v28 ^ HIDWORD(v52);
        v54 = v30 ^ v52 ^ (WORD2(a4) * (WORD1(a4) + __ROR4__(~(v28 ^ HIDWORD(v52)), 13)));
        v55 = v53 ^ (v54 >> 15) ^ ((unsigned __int16)a4 * (WORD1(a4) ^ v54));
        v56 = v54 ^ (v55 - HIWORD(a4) - a4);
        v57 = v55 ^ (__ROR4__(v56, 5) + WORD2(a4) * __ROR4__(a4 ^ v56, 2));
        v58 = v56 ^ __ROR4__(v57, 4) ^ (WORD1(a4) * __ROL4__((unsigned __int16)a4 ^ v57, 7));
        v59 = v57 ^ (v58 >> 13) ^ ((unsigned __int16)a4 * __ROL4__(v58 - HIWORD(a4), 2));
        v60 = v58 ^ __ROR4__(v59, 14) ^ (HIWORD(a4) * __ROR4__(v59 - a4, 11));
        v61 = v59 ^ (WORD2(a4) * __ROR4__(a4 ^ v60, 17) - __ROR4__(v60, 7));
        v62 = v75;
        v63 = v60 ^ (__ROR4__(v61, 23) + WORD1(a4) * __ROR4__(HIDWORD(a4) - v61, 7));
        v30 = v63 ^ v27;
        v27 = v52;
        LODWORD(v72) = v30;
        v28 = v61 ^ v63 ^ a5 ^ HIDWORD(a4) ^ a4;
        a5 = HIDWORD(v52);
        HIDWORD(v72) = v28;
        ++v51;
        *v75 = v72;
        v75 = v62 + 1;
        v50 = v74;
      }
      while ( v51 < v7 >> 3 );
      v15 = v73;
      v11 = v77;
      v8 = v79;
      v9 = v80;
      v7 = v78;
    }
    v26 = v8[v7 - 1];
    v70 = v26;
  }
  if ( a7 )
  {
    v64 = v76;
    v65 = (char *)&_ImageBase - WarbirdRuntime::g_preferedImageBase;
    while ( v15 < v64 )
    {
      v66 = *(_DWORD *)&v11[4 * v15];
      if ( (v66 & 0xFFFFFFF) >= v71 )
        break;
      ++v15;
      v67 = v66 >> 28;
      if ( v66 >> 28 )
      {
        v68 = (char *)&_ImageBase + (v66 & 0xFFFFFFF);
        v69 = v68 - v9;
        if ( v67 == 3 )
        {
          *(_DWORD *)&v8[v69] = (_DWORD)v65 + *(_DWORD *)v68;
        }
        else if ( v67 == 10 )
        {
          *(_QWORD *)&v8[v69] = &v65[*(_QWORD *)v68];
        }
      }
    }
    v26 = v70;
  }
  if ( v26 != a6 )
    WarbirdRuntime::CTermination::TrashStack();
}

```

## disassembly

```asm
0x180020d30  mov     r11, rsp
0x180020d33  sub     rsp, 0C8h
0x180020d3a  mov     rax, cs:__security_cookie
0x180020d41  xor     rax, rsp
0x180020d44  mov     [rsp+0C8h+var_58], rax
0x180020d49  mov     [r11-8], rbx
0x180020d4d  mov     [r11-10h], rbp
0x180020d51  mov     rbp, r8
0x180020d54  mov     [r11-18h], rsi
0x180020d58  mov     [r11-20h], rdi
0x180020d5c  mov     [r11-28h], r12
0x180020d60  xor     r12d, r12d
0x180020d63  mov     [r11-30h], r13
0x180020d67  mov     [r11-38h], r14
0x180020d6b  mov     r14, rdx
0x180020d6e  mov     [r11-40h], r15
0x180020d72  mov     r15, rcx
0x180020d75  mov     [rsp+0C8h+var_60], rcx
0x180020d7a  lea     rcx, __ImageBase
0x180020d81  mov     [rsp+0C8h+var_70], r8
0x180020d86  mov     [rsp+0C8h+var_68], rdx
0x180020d8b  cmp     [rsp+0C8h+arg_30], r12d
0x180020d93  jz      loc_180020E8C
0x180020d99  mov     r13d, cs:?g_PrivateRelocationsTable@WarbirdRuntime@@3KC; ulong volatile WarbirdRuntime::g_PrivateRelocationsTable
0x180020da0  mov     r11d, r15d
0x180020da3  mov     edi, cs:?g_PrivateRelocationsTableCount@WarbirdRuntime@@3KC; ulong volatile WarbirdRuntime::g_PrivateRelocationsTableCount
0x180020da9  add     r13, rcx
0x180020dac  sub     r11d, ecx
0x180020daf  mov     [rsp+0C8h+var_78], r13
0x180020db4  mov     [rsp+0C8h+var_80], edi
0x180020db8  mov     r8d, r12d
0x180020dbb  lea     r10d, [rdi-1]
0x180020dbf  test    r10d, r10d
0x180020dc2  js      short loc_180020DF8
0x180020dc4  lea     edx, [r10+r8]
0x180020dc8  test    edx, edx
0x180020dca  jns     short loc_180020DCE
0x180020dcc  inc     edx
0x180020dce  sar     edx, 1
0x180020dd0  movsxd  rax, edx
0x180020dd3  mov     [rsp+0C8h+var_98], edx
0x180020dd7  mov     ecx, [r13+rax*4+0]
0x180020ddc  and     ecx, 0FFFFFFFh
0x180020de2  cmp     r11d, ecx
0x180020de5  jnb     short loc_180020DED
0x180020de7  lea     r10d, [rdx-1]
0x180020deb  jmp     short loc_180020DF3
0x180020ded  jbe     short loc_180020DFF
0x180020def  lea     r8d, [rdx+1]
0x180020df3  cmp     r10d, r8d
0x180020df6  jge     short loc_180020DC4
0x180020df8  mov     edx, r8d
0x180020dfb  mov     [rsp+0C8h+var_98], edx
0x180020dff  mov     rbx, cs:?g_preferedImageBase@WarbirdRuntime@@3_KC; unsigned __int64 volatile WarbirdRuntime::g_preferedImageBase
0x180020e06  lea     ecx, [r11+rbp]
0x180020e0a  lea     r11, __ImageBase
0x180020e11  mov     [rsp+0C8h+var_A4], ecx
0x180020e15  sub     rbx, r11
0x180020e18  mov     esi, ebp
0x180020e1a  mov     r10d, edx
0x180020e1d  jmp     short loc_180020E31
0x180020e20  mov     ecx, [rsp+0C8h+var_A4]
0x180020e24  jmp     short loc_180020E31
0x180020e26  mov     ecx, [rsp+0C8h+var_A4]
0x180020e2a  lea     r11, __ImageBase
0x180020e31  cmp     r10d, edi
0x180020e34  jnb     short loc_180020EAB
0x180020e36  mov     eax, r10d
0x180020e39  mov     r8d, [r13+rax*4+0]
0x180020e3e  mov     eax, r8d
0x180020e41  and     eax, 0FFFFFFFh
0x180020e46  cmp     eax, ecx
0x180020e48  jnb     short loc_180020EAB
0x180020e4a  mov     ecx, r8d
0x180020e4d  inc     r10d
0x180020e50  shr     ecx, 1Ch
0x180020e53  test    ecx, ecx
0x180020e55  jz      short loc_180020E20
0x180020e57  and     r8d, 0FFFFFFFh
0x180020e5e  add     r11, r8
0x180020e61  mov     r8, r11
0x180020e64  sub     r8, r15
0x180020e67  cmp     ecx, 3
0x180020e6a  jz      short loc_180020E81
0x180020e6c  cmp     ecx, 0Ah
0x180020e6f  mov     ecx, [rsp+0C8h+var_A4]
0x180020e73  jnz     short loc_180020E2A
0x180020e75  mov     rcx, [r11]
0x180020e78  add     rcx, rbx
0x180020e7b  mov     [r8+r14], rcx
0x180020e7f  jmp     short loc_180020E26
0x180020e81  mov     ecx, [r11]
0x180020e84  add     ecx, ebx
0x180020e86  mov     [r8+r14], ecx
0x180020e8a  jmp     short loc_180020E26
0x180020e8c  mov     eax, dword ptr [rsp+0C8h+var_90]
0x180020e90  mov     r13, r12
0x180020e93  mov     edx, dword ptr [rsp+0C8h+var_90]
0x180020e97  mov     esi, ebp
0x180020e99  mov     [rsp+0C8h+var_A4], eax
0x180020e9d  mov     [rsp+0C8h+var_98], edx
0x180020ea1  mov     [rsp+0C8h+var_78], r12
0x180020ea6  mov     [rsp+0C8h+var_80], r12d
0x180020eab  xor     dil, dil
0x180020eae  mov     [rsp+0C8h+var_A8], dil
0x180020eb3  test    rbp, rbp
0x180020eb6  jz      loc_180021221
0x180020ebc  mov     r10d, [rsp+0C8h+arg_20]
0x180020ec4  and     esi, 7
0x180020ec7  mov     ecx, r10d
0x180020eca  mov     [rsp+0C8h+var_A0], r12
0x180020ecf  not     ecx
0x180020ed1  mov     dword ptr [rsp+0C8h+var_90], esi
0x180020ed5  jnz     short loc_180020EE6
0x180020ed7  mov     ebx, dword ptr [rsp+0C8h+var_A0+4]
0x180020edb  mov     rsi, r12
0x180020ede  mov     edi, r12d
0x180020ee1  jmp     loc_18002107B
0x180020ee6  mov     r8d, ecx
0x180020ee9  mov     [rsp+0C8h+var_88], r12
0x180020eee  ror     r8d, 0Dh
0x180020ef2  mov     rax, r9
0x180020ef5  shr     rax, 10h
0x180020ef9  mov     rbp, r9
0x180020efc  movzx   esi, ax
0x180020eff  mov     rbx, r9
0x180020f02  add     r8d, esi
0x180020f05  shr     rbx, 30h
0x180020f09  shr     rbp, 20h
0x180020f0d  movzx   edi, bp
0x180020f10  imul    r8d, edi
0x180020f14  movzx   eax, r9w
0x180020f18  xor     r8d, ecx
0x180020f1b  mov     ecx, r8d
0x180020f1e  xor     ecx, esi
0x180020f20  imul    ecx, eax
0x180020f23  mov     eax, r8d
0x180020f26  shr     eax, 0Fh
0x180020f29  xor     ecx, eax
0x180020f2b  xor     ecx, r10d
0x180020f2e  mov     r10d, ecx
0x180020f31  sub     r10d, ebx
0x180020f34  sub     r10d, r9d
0x180020f37  xor     r10d, r8d
0x180020f3a  mov     r11d, r10d
0x180020f3d  mov     eax, r10d
0x180020f40  ror     eax, 5
0x180020f43  xor     r11d, r9d
0x180020f46  ror     r11d, 2
0x180020f4a  imul    r11d, edi
0x180020f4e  add     r11d, eax
0x180020f51  xor     r11d, ecx
0x180020f54  movzx   ecx, r9w
0x180020f58  mov     r8d, ecx
0x180020f5b  mov     eax, r11d
0x180020f5e  xor     r8d, r11d
0x180020f61  ror     eax, 4
0x180020f64  rol     r8d, 7
0x180020f68  imul    r8d, esi
0x180020f6c  xor     r8d, eax
0x180020f6f  xor     r8d, r10d
0x180020f72  mov     r10d, r8d
0x180020f75  mov     eax, r8d
0x180020f78  sub     r10d, ebx
0x180020f7b  shr     eax, 0Dh
0x180020f7e  rol     r10d, 2
0x180020f82  imul    r10d, ecx
0x180020f86  xor     r10d, eax
0x180020f89  xor     r10d, r11d
0x180020f8c  mov     r11d, r10d
0x180020f8f  mov     eax, r10d
0x180020f92  ror     eax, 0Eh
0x180020f95  sub     r11d, r9d
0x180020f98  ror     r11d, 0Bh
0x180020f9c  imul    r11d, ebx
0x180020fa0  mov     ebx, r9d
0x180020fa3  xor     ebx, ebp
0x180020fa5  xor     r11d, eax
0x180020fa8  xor     r11d, r8d
0x180020fab  mov     ecx, r11d
0x180020fae  mov     eax, r11d
0x180020fb1  xor     ecx, r9d
0x180020fb4  ror     eax, 7
0x180020fb7  ror     ecx, 11h
0x180020fba  imul    ecx, edi
0x180020fbd  mov     edi, ebp
0x180020fbf  sub     ecx, eax
0x180020fc1  xor     ecx, r10d
0x180020fc4  sub     edi, ecx
0x180020fc6  mov     eax, ecx
0x180020fc8  ror     edi, 7
0x180020fcb  imul    edi, esi
0x180020fce  mov     esi, dword ptr [rsp+0C8h+var_90]
0x180020fd2  ror     eax, 17h
0x180020fd5  add     edi, eax
0x180020fd7  xor     edi, r11d
0x180020fda  xor     ebx, edi
0x180020fdc  xor     ebx, ecx
0x180020fde  mov     ecx, esi
0x180020fe0  mov     r8, r15
0x180020fe3  lea     r10, [rsp+0C8h+var_88]
0x180020fe8  nop     dword ptr [rax+rax+00000000h]
0x180020ff0  movzx   eax, byte ptr [r8]
0x180020ff4  lea     r8, [r8+1]
0x180020ff8  mov     [r10], al
0x180020ffb  lea     r10, [r10+1]
0x180020fff  sub     rcx, 1
0x180021003  jnz     short loc_180020FF0
0x180021005  mov     eax, dword ptr [rsp+0C8h+var_88+4]
0x180021009  lea     r8, [rsp+0C8h+var_A0]
0x18002100e  mov     rcx, [rsp+0C8h+var_88]
0x180021013  lea     r8, [r8+rsi]
0x180021017  xor     ebx, eax
0x180021019  mov     [rsp+0C8h+arg_20], eax
0x180021020  xor     edi, ecx
0x180021022  mov     dword ptr [rsp+0C8h+var_A0+4], ebx
0x180021026  mov     eax, 8
0x18002102b  mov     dword ptr [rsp+0C8h+var_A0], edi
0x18002102f  sub     rax, rsi
0x180021032  jz      short loc_180021056
0x180021034  nop     dword ptr [rax+00h]
0x180021038  nop     dword ptr [rax+rax+00000000h]
0x180021040  mov     byte ptr [r8], 0
0x180021044  lea     r8, [r8+1]
0x180021048  sub     rax, 1
0x18002104c  jnz     short loc_180021040
0x18002104e  mov     ebx, dword ptr [rsp+0C8h+var_A0+4]
0x180021052  mov     edi, dword ptr [rsp+0C8h+var_A0]
0x180021056  mov     r8, rsi
0x180021059  lea     r10, [rsp+0C8h+var_A0]
0x18002105e  mov     r11, r14
0x180021061  movzx   eax, byte ptr [r10]
0x180021065  lea     r10, [r10+1]
0x180021069  mov     [r11], al
0x18002106c  lea     r11, [r11+1]
0x180021070  sub     r8, 1
0x180021074  jnz     short loc_180021061
0x180021076  mov     rbp, [rsp+0C8h+var_70]
0x18002107b  lea     rax, [rsi+r14]
0x18002107f  mov     [rsp+0C8h+var_88], rax
0x180021084  lea     r8, [rsi+r15]
0x180021088  mov     rax, rbp
0x18002108b  shr     rax, 3
0x18002108f  test    rax, rax
0x180021092  jz      loc_180021216
0x180021098  xor     r13d, r13d
0x18002109b  mov     rdx, rax
0x18002109e  xchg    ax, ax
0x1800210a0  mov     rax, [r8]
0x1800210a3  mov     r15, r9
0x1800210a6  add     r8, 8
0x1800210aa  shr     r15, 20h
0x1800210ae  mov     [rsp+0C8h+var_90], r8
0x1800210b3  mov     r12, rax
0x1800210b6  movzx   ebp, r15w
0x1800210ba  mov     r8, r9
0x1800210bd  shr     r8, 10h
0x1800210c1  mov     rsi, r9
0x1800210c4  movzx   r14d, r8w
0x1800210c8  shr     rsi, 30h
0x1800210cc  shr     r12, 20h
0x1800210d0  mov     r10d, r12d
0x1800210d3  xor     r10d, ebx
0x1800210d6  mov     ebx, r10d
0x1800210d9  not     ebx
0x1800210db  ror     ebx, 0Dh
0x1800210de  add     ebx, r14d
0x1800210e1  imul    ebx, ebp
0x1800210e4  xor     ebx, eax
0x1800210e6  xor     ebx, edi
0x1800210e8  movzx   edi, r9w
0x1800210ec  mov     r11d, ebx
0x1800210ef  mov     r8d, ebx
0x1800210f2  xor     r11d, r14d
0x1800210f5  shr     r8d, 0Fh
0x1800210f9  imul    r11d, edi
0x1800210fd  xor     r11d, r8d
0x180021100  xor     r11d, r10d
0x180021103  mov     r10d, r11d
0x180021106  sub     r10d, esi
0x180021109  sub     r10d, r9d
0x18002110c  xor     r10d, ebx
0x18002110f  mov     ebx, r10d
0x180021112  mov     r8d, r10d
0x180021115  ror     r8d, 5
0x180021119  xor     ebx, r9d
0x18002111c  ror     ebx, 2
0x18002111f  imul    ebx, ebp
0x180021122  add     ebx, r8d
0x180021125  xor     ebx, r11d
0x180021128  mov     r11d, ebx
0x18002112b  mov     r8d, ebx
0x18002112e  xor     r11d, edi
0x180021131  ror     r8d, 4
0x180021135  rol     r11d, 7
0x180021139  imul    r11d, r14d
0x18002113d  xor     r11d, r8d
0x180021140  xor     r11d, r10d
0x180021143  mov     r10d, r11d
0x180021146  mov     r8d, r11d
  ... truncated ...
```
