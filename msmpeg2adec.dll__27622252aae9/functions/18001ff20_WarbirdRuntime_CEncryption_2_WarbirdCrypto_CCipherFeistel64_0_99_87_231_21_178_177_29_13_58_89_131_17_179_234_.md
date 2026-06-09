# WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Decrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar,int)

- ea: `0x18001ff20`
- end: `0x18002059d`
- name: `?Decrypt@?$CEncryption@$01V?$CCipherFeistel64@$0A@$0GD@$0FH@$0OH@$0BF@$0LC@$0LB@$0BN@$0N@$0DK@$0FJ@$0ID@$0BB@$0LD@$0OK@$0FA@$0BD@$0LL@$0MF@$0MH@$02$0EA@$0JO@$01$01$0PL@$0GM@$0KE@$0P@$0LK@$0EI@$0NL@$0BC@$09$0CK@$0LM@$0BO@$0GO@$0HK@$0DC@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$00$0BKGBKNDEJDGFEBEE@@2@UENCRYPTED_SEGMENT_DATA_CONST_3@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_3@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@KEH@Z`
- size: `1661`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180022820`

## callees

- `0x1800017b0`
- `0x18001ff20`
- `0x180025230`

## pseudocode

```c
void __fastcall WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Decrypt(
        char *a1,
        _BYTE *a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        int a5,
        char a6,
        int a7)
{
  __int64 v7; // rbx
  _BYTE *v8; // rbp
  unsigned __int64 v9; // rdi
  char *v11; // r15
  volatile unsigned int v12; // r14d
  char *v13; // rsi
  unsigned int v14; // r10d
  signed int v15; // r8d
  signed int v16; // r9d
  unsigned int v17; // edx
  unsigned int v18; // ecx
  unsigned int v19; // r12d
  unsigned __int64 v20; // r11
  volatile unsigned int i; // r9d
  unsigned int v22; // r8d
  unsigned int v23; // ecx
  char *v24; // r10
  signed __int64 v25; // r8
  char v26; // r11
  int v27; // ecx
  int v28; // r13d
  unsigned __int64 v29; // r8
  unsigned __int64 v30; // r10
  _QWORD *v31; // rax
  int v32; // edi
  int v33; // r8d
  int v34; // r9d
  unsigned int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  int v38; // r8d
  int v39; // ecx
  unsigned int v40; // r10d
  __int64 *v41; // r9
  char *v42; // r8
  int v43; // r13d
  __int64 v44; // rcx
  char v45; // al
  char *v46; // r8
  __int64 v47; // rax
  __int64 v48; // r8
  char *v49; // r9
  _BYTE *v50; // r10
  char v51; // al
  __int64 *v52; // r10
  int v53; // esi
  unsigned __int64 v54; // rbp
  int v55; // r15d
  _QWORD *v56; // r12
  int v57; // r14d
  int v58; // edx
  int v59; // r8d
  __int64 v60; // rax
  int v61; // r10d
  int v62; // r11d
  unsigned int v63; // r9d
  int v64; // r10d
  int v65; // r11d
  int v66; // r9d
  int v67; // r10d
  int v68; // r11d
  unsigned int v69; // r9d
  _QWORD *v70; // r8
  char *v71; // r10
  unsigned int v72; // r8d
  unsigned int v73; // ecx
  char *v74; // r9
  signed __int64 v75; // r8
  char v76; // [rsp+20h] [rbp-C8h]
  unsigned int v77; // [rsp+24h] [rbp-C4h]
  int v78; // [rsp+24h] [rbp-C4h]
  __int64 v79; // [rsp+28h] [rbp-C0h] BYREF
  int v80; // [rsp+30h] [rbp-B8h]
  unsigned int v81; // [rsp+34h] [rbp-B4h]
  __int64 v82; // [rsp+38h] [rbp-B0h] BYREF
  volatile unsigned int v83; // [rsp+40h] [rbp-A8h]
  unsigned int v84; // [rsp+44h] [rbp-A4h]
  unsigned __int64 v85; // [rsp+48h] [rbp-A0h]
  unsigned __int64 v86; // [rsp+50h] [rbp-98h]
  _QWORD *v87; // [rsp+58h] [rbp-90h]
  unsigned __int64 v88; // [rsp+60h] [rbp-88h]
  _QWORD *v89; // [rsp+68h] [rbp-80h]
  char *v90; // [rsp+70h] [rbp-78h]
  unsigned __int64 v91; // [rsp+78h] [rbp-70h]
  _BYTE *v92; // [rsp+80h] [rbp-68h]
  char *v93; // [rsp+88h] [rbp-60h]

  v7 = 0;
  v8 = a2;
  v9 = a4;
  v11 = a1;
  v93 = a1;
  v85 = a4;
  v91 = a3;
  v92 = a2;
  if ( a7 )
  {
    v12 = WarbirdRuntime::g_PrivateRelocationsTableCount;
    v13 = (char *)&_ImageBase + WarbirdRuntime::g_PrivateRelocationsTable;
    v14 = (_DWORD)a1 - (unsigned int)&_ImageBase;
    v90 = v13;
    v83 = WarbirdRuntime::g_PrivateRelocationsTableCount;
    v15 = 0;
    v16 = WarbirdRuntime::g_PrivateRelocationsTableCount - 1;
    while ( v16 >= v15 )
    {
      v17 = (v16 + v15) / 2;
      v81 = v17;
      v18 = *(_DWORD *)&v13[4 * v17] & 0xFFFFFFF;
      if ( v14 >= v18 )
      {
        if ( v14 <= v18 )
          goto LABEL_9;
        v15 = v17 + 1;
      }
      else
      {
        v16 = v17 - 1;
      }
    }
    v17 = v15;
    v81 = v15;
LABEL_9:
    v19 = v14 + a3;
    v84 = v14 + a3;
    v20 = WarbirdRuntime::g_preferedImageBase - (_QWORD)&_ImageBase;
    for ( i = v17; i < v12; ++i )
    {
      v22 = *(_DWORD *)&v13[4 * i];
      if ( (v22 & 0xFFFFFFF) >= v19 )
        break;
      v23 = v22 >> 28;
      if ( v22 >> 28 )
      {
        v24 = (char *)&_ImageBase + (v22 & 0xFFFFFFF);
        v25 = v24 - v11;
        if ( v23 == 3 )
        {
          *(_DWORD *)&v8[v25] = v20 + *(_DWORD *)v24;
        }
        else if ( v23 == 10 )
        {
          *(_QWORD *)&v8[v25] = v20 + *(_QWORD *)v24;
        }
      }
    }
  }
  else
  {
    v19 = v82;
    v13 = 0;
    v17 = v82;
    v12 = 0;
    v84 = v82;
    v81 = v82;
    v90 = 0;
    v83 = 0;
  }
  v26 = 0;
  v76 = 0;
  if ( a3 )
  {
    v77 = a3 & 7;
    v27 = ~a5;
    v79 = 0;
    if ( (a3 & 7) != 0 )
    {
      v30 = v9;
      v31 = (_QWORD *)(v9 >> 16);
      v32 = WORD1(v9);
      v87 = v31;
      v88 = HIDWORD(v30);
      v33 = v27 ^ (a5 - (unsigned __int16)v31 - HIDWORD(v30));
      v34 = a5 ^ __ROR4__(v33, 3) ^ ((unsigned __int16)v85 * __ROR4__(v33 - HIDWORD(v30), 12));
      v86 = HIWORD(v85);
      v35 = v33 ^ (HIWORD(v85) * __ROR4__(v34 + v85, 11) - __ROR4__(v34, 3));
      v36 = v34 ^ (v35 >> 4) ^ (WORD2(v30) * (v32 ^ v35));
      v37 = v35 ^ (v32 * (HIWORD(v85) ^ v36) + __ROR4__(v36, 9));
      LODWORD(v30) = v36 ^ __ROR4__(v37, 14) ^ ((unsigned __int16)v85 * __ROR4__(HIDWORD(v30) - v37, 12));
      v38 = v37 ^ (HIWORD(v85) * __ROR4__(v85 ^ v30, 18) - __ROR4__(v30, 19));
      v39 = v30 ^ (__ROR4__(v38, 8) + WORD2(v30) * __ROR4__(v85 - v38, 28));
      v40 = v38 ^ (__ROR4__(v39, 30) + v32 * __ROR4__(v39 - v88, 23));
      v7 = a3 & 7;
      v41 = &v82;
      v42 = v11;
      v82 = 0;
      v43 = v39 ^ ((v40 >> 13) + (unsigned __int16)v85 * (v32 ^ v40));
      v44 = v77;
      do
      {
        v45 = *v42++;
        *(_BYTE *)v41 = v45;
        v41 = (__int64 *)((char *)v41 + 1);
        --v44;
      }
      while ( v44 );
      v27 = v82;
      v46 = (char *)&v79 + v77;
      a5 = HIDWORD(v82);
      LODWORD(v79) = v82 ^ v40;
      HIDWORD(v79) = HIDWORD(v82) ^ v43;
      v47 = 8LL - v77;
      do
      {
        *v46++ = 0;
        --v47;
      }
      while ( v47 );
      v28 = HIDWORD(v79);
      v78 = v79;
      v48 = v7;
      v49 = (char *)&v79;
      v50 = v8;
      do
      {
        v51 = *v49++;
        *v50++ = v51;
        --v48;
      }
      while ( v48 );
      LODWORD(v9) = v85;
      LOWORD(v29) = (_WORD)v87;
    }
    else
    {
      v28 = HIDWORD(v79);
      v88 = HIDWORD(v9);
      v29 = v9 >> 16;
      v86 = HIWORD(v9);
      v78 = 0;
    }
    v87 = &v8[v7];
    v52 = (__int64 *)&v11[v7];
    v89 = (_QWORD *)(v91 >> 3);
    if ( v91 >> 3 )
    {
      v53 = v88;
      v54 = 0;
      v55 = v78;
      v56 = v89;
      v57 = v86;
      v58 = a5;
      LODWORD(v85) = (unsigned __int16)v29;
      v59 = (unsigned __int16)v9;
      LODWORD(v82) = (unsigned __int16)v88;
      v80 = (unsigned __int16)v9;
      do
      {
        v60 = *v52;
        v89 = v52 + 1;
        v61 = v55 ^ v60 ^ ((v28 ^ HIDWORD(v60)) - v85 - v53);
        v62 = v28 ^ HIDWORD(v60) ^ __ROR4__(v61, 3) ^ (v59 * __ROR4__(v61 - v53, 12));
        v63 = v61 ^ (v57 * __ROR4__(v9 + v62, 11) - __ROR4__(v62, 3));
        v64 = v62 ^ (v63 >> 4) ^ (v82 * (v63 ^ v85));
        v65 = v63 ^ (v85 * (v64 ^ v57) + __ROR4__(v64, 9));
        v66 = v64 ^ __ROR4__(v65, 14) ^ (v80 * __ROR4__(v53 - v65, 12));
        v67 = v65 ^ (v57 * __ROR4__(v66 ^ v9, 18) - __ROR4__(v66, 19));
        v68 = v66 ^ (__ROR4__(v67, 8) + v82 * __ROR4__(v9 - v67, 28));
        v69 = v67 ^ (__ROR4__(v68, 30) + v85 * __ROR4__(v68 - v53, 23));
        v55 = v69 ^ v27;
        LODWORD(v79) = v69 ^ v27;
        v70 = v87;
        v52 = v89;
        v28 = v68 ^ v58 ^ ((v69 >> 13) + v80 * (v69 ^ v85));
        HIDWORD(v79) = v28;
        v27 = v60;
        ++v54;
        *v87 = v79;
        v58 = HIDWORD(v60);
        v87 = v70 + 1;
        v59 = v80;
      }
      while ( v54 < (unsigned __int64)v56 );
      v17 = v81;
      v13 = v90;
      v8 = v92;
      v12 = v83;
      v11 = v93;
      v19 = v84;
    }
    v26 = v8[v91 - 1];
    v76 = v26;
  }
  if ( a7 )
  {
    v71 = (char *)&_ImageBase - WarbirdRuntime::g_preferedImageBase;
    while ( v17 < v12 )
    {
      v72 = *(_DWORD *)&v13[4 * v17];
      if ( (v72 & 0xFFFFFFF) >= v19 )
        break;
      ++v17;
      v73 = v72 >> 28;
      if ( v72 >> 28 )
      {
        v74 = (char *)&_ImageBase + (v72 & 0xFFFFFFF);
        v75 = v74 - v11;
        if ( v73 == 3 )
        {
          *(_DWORD *)&v8[v75] = (_DWORD)v71 + *(_DWORD *)v74;
        }
        else if ( v73 == 10 )
        {
          *(_QWORD *)&v8[v75] = &v71[*(_QWORD *)v74];
        }
      }
    }
    v26 = v76;
  }
  if ( v26 != a6 )
    WarbirdRuntime::CTermination::TrashStack();
}

```

## disassembly

```asm
0x18001ff20  mov     r11, rsp
0x18001ff23  sub     rsp, 0E8h
0x18001ff2a  mov     rax, cs:__security_cookie
0x18001ff31  xor     rax, rsp
0x18001ff34  mov     [rsp+0E8h+var_58], rax
0x18001ff3c  mov     [r11-8], rbx
0x18001ff40  xor     ebx, ebx
0x18001ff42  mov     [r11-10h], rbp
0x18001ff46  mov     rbp, rdx
0x18001ff49  mov     [r11-18h], rsi
0x18001ff4d  mov     [r11-20h], rdi
0x18001ff51  mov     rdi, r9
0x18001ff54  mov     [r11-28h], r12
0x18001ff58  mov     [r11-30h], r13
0x18001ff5c  mov     r13, r8
0x18001ff5f  mov     [r11-38h], r14
0x18001ff63  mov     [r11-40h], r15
0x18001ff67  mov     r15, rcx
0x18001ff6a  mov     [rsp+0E8h+var_60], rcx
0x18001ff72  lea     rcx, __ImageBase
0x18001ff79  mov     [rsp+0E8h+var_A0], r9
0x18001ff7e  mov     [rsp+0E8h+var_70], r8
0x18001ff83  mov     [rsp+0E8h+var_68], rdx
0x18001ff8b  cmp     [rsp+0E8h+arg_30], ebx
0x18001ff92  jz      loc_18002007F
0x18001ff98  mov     esi, cs:?g_PrivateRelocationsTable@WarbirdRuntime@@3KC; ulong volatile WarbirdRuntime::g_PrivateRelocationsTable
0x18001ff9e  mov     r10d, r15d
0x18001ffa1  mov     r14d, cs:?g_PrivateRelocationsTableCount@WarbirdRuntime@@3KC; ulong volatile WarbirdRuntime::g_PrivateRelocationsTableCount
0x18001ffa8  add     rsi, rcx
0x18001ffab  sub     r10d, ecx
0x18001ffae  mov     [rsp+0E8h+var_78], rsi
0x18001ffb3  mov     [rsp+0E8h+var_A8], r14d
0x18001ffb8  mov     r8d, ebx
0x18001ffbb  lea     r9d, [r14-1]
0x18001ffbf  test    r9d, r9d
0x18001ffc2  js      short loc_18001FFF6
0x18001ffc4  lea     edx, [r9+r8]
0x18001ffc8  test    edx, edx
0x18001ffca  jns     short loc_18001FFCE
0x18001ffcc  inc     edx
0x18001ffce  sar     edx, 1
0x18001ffd0  movsxd  rax, edx
0x18001ffd3  mov     [rsp+0E8h+var_B4], edx
0x18001ffd7  mov     ecx, [rsi+rax*4]
0x18001ffda  and     ecx, 0FFFFFFFh
0x18001ffe0  cmp     r10d, ecx
0x18001ffe3  jnb     short loc_18001FFEB
0x18001ffe5  lea     r9d, [rdx-1]
0x18001ffe9  jmp     short loc_18001FFF1
0x18001ffeb  jbe     short loc_18001FFFD
0x18001ffed  lea     r8d, [rdx+1]
0x18001fff1  cmp     r9d, r8d
0x18001fff4  jge     short loc_18001FFC4
0x18001fff6  mov     edx, r8d
0x18001fff9  mov     [rsp+0E8h+var_B4], edx
0x18001fffd  mov     r11, cs:?g_preferedImageBase@WarbirdRuntime@@3_KC; unsigned __int64 volatile WarbirdRuntime::g_preferedImageBase
0x180020004  lea     r12d, [r10+r13]
0x180020008  lea     r10, __ImageBase
0x18002000f  mov     [rsp+0E8h+var_A4], r12d
0x180020014  sub     r11, r10
0x180020017  mov     r9d, edx
0x18002001a  jmp     short loc_180020027
0x180020020  lea     r10, __ImageBase
0x180020027  cmp     r9d, r14d
0x18002002a  jnb     short loc_1800200A0
0x18002002c  mov     eax, r9d
0x18002002f  mov     r8d, [rsi+rax*4]
0x180020033  mov     eax, r8d
0x180020036  and     eax, 0FFFFFFFh
0x18002003b  cmp     eax, r12d
0x18002003e  jnb     short loc_1800200A0
0x180020040  mov     ecx, r8d
0x180020043  inc     r9d
0x180020046  shr     ecx, 1Ch
0x180020049  test    ecx, ecx
0x18002004b  jz      short loc_180020027
0x18002004d  and     r8d, 0FFFFFFFh
0x180020054  add     r10, r8
0x180020057  mov     r8, r10
0x18002005a  sub     r8, r15
0x18002005d  cmp     ecx, 3
0x180020060  jz      short loc_180020073
0x180020062  cmp     ecx, 0Ah
0x180020065  jnz     short loc_180020020
0x180020067  mov     rcx, [r10]
0x18002006a  add     rcx, r11
0x18002006d  mov     [r8+rbp], rcx
0x180020071  jmp     short loc_180020020
0x180020073  mov     ecx, [r10]
0x180020076  add     ecx, r11d
0x180020079  mov     [r8+rbp], ecx
0x18002007d  jmp     short loc_180020020
0x18002007f  mov     r12d, dword ptr [rsp+0E8h+var_B0]
0x180020084  mov     rsi, rbx
0x180020087  mov     edx, dword ptr [rsp+0E8h+var_B0]
0x18002008b  mov     r14d, ebx
0x18002008e  mov     [rsp+0E8h+var_A4], r12d
0x180020093  mov     [rsp+0E8h+var_B4], edx
0x180020097  mov     [rsp+0E8h+var_78], rbx
0x18002009c  mov     [rsp+0E8h+var_A8], ebx
0x1800200a0  xor     r11b, r11b
0x1800200a3  mov     eax, r13d
0x1800200a6  mov     [rsp+0E8h+var_C8], r11b
0x1800200ab  test    r13, r13
0x1800200ae  jz      loc_1800204BA
0x1800200b4  mov     r11d, [rsp+0E8h+arg_20]
0x1800200bc  and     eax, 7
0x1800200bf  mov     ecx, r11d
0x1800200c2  mov     [rsp+0E8h+var_C4], eax
0x1800200c6  not     ecx
0x1800200c8  mov     [rsp+0E8h+var_C0], rbx
0x1800200cd  mov     rax, rdi
0x1800200d0  jnz     short loc_1800200FF
0x1800200d2  mov     r13d, dword ptr [rsp+0E8h+var_C0+4]
0x1800200d7  mov     r8, rdi
0x1800200da  shr     rax, 20h
0x1800200de  mov     r10d, ebx
0x1800200e1  mov     [rsp+0E8h+var_88], rax
0x1800200e6  mov     rax, rdi
0x1800200e9  shr     r8, 10h
0x1800200ed  shr     rax, 30h
0x1800200f1  mov     [rsp+0E8h+var_98], rax
0x1800200f6  mov     [rsp+0E8h+var_C4], ebx
0x1800200fa  jmp     loc_1800202CF
0x1800200ff  mov     r13, [rsp+0E8h+var_A0]
0x180020104  mov     r10, rdi
0x180020107  shr     rax, 10h
0x18002010b  mov     r8d, r11d
0x18002010e  movzx   edi, ax
0x180020111  mov     [rsp+0E8h+var_90], rax
0x180020116  sub     r8d, edi
0x180020119  shr     r10, 20h
0x18002011d  sub     r8d, r10d
0x180020120  mov     [rsp+0E8h+var_88], r10
0x180020125  xor     r8d, ecx
0x180020128  movzx   ebx, r13w
0x18002012c  mov     eax, r8d
0x18002012f  mov     r9d, r8d
0x180020132  ror     eax, 3
0x180020135  sub     r9d, r10d
0x180020138  ror     r9d, 0Ch
0x18002013c  imul    r9d, ebx
0x180020140  xor     r9d, eax
0x180020143  mov     rax, r13
0x180020146  shr     rax, 30h
0x18002014a  xor     r9d, r11d
0x18002014d  mov     [rsp+0E8h+var_98], rax
0x180020152  movzx   r11d, r10w
0x180020156  lea     ecx, [r9+r13]
0x18002015a  ror     ecx, 0Bh
0x18002015d  imul    ecx, eax
0x180020160  mov     eax, r9d
0x180020163  ror     eax, 3
0x180020166  sub     ecx, eax
0x180020168  xor     ecx, r8d
0x18002016b  mov     eax, ecx
0x18002016d  mov     r8d, ecx
0x180020170  shr     eax, 4
0x180020173  xor     r8d, edi
0x180020176  imul    r8d, r11d
0x18002017a  xor     r8d, eax
0x18002017d  xor     r8d, r9d
0x180020180  mov     eax, r8d
0x180020183  mov     r9d, r8d
0x180020186  xor     eax, dword ptr [rsp+0E8h+var_98]
0x18002018a  imul    eax, edi
0x18002018d  ror     r9d, 9
0x180020191  add     r9d, eax
0x180020194  xor     r9d, ecx
0x180020197  mov     ecx, r13d
0x18002019a  sub     r10d, r9d
0x18002019d  mov     eax, r9d
0x1800201a0  ror     r10d, 0Ch
0x1800201a4  ror     eax, 0Eh
0x1800201a7  imul    r10d, ebx
0x1800201ab  xor     r10d, eax
0x1800201ae  xor     r10d, r8d
0x1800201b1  mov     eax, r10d
0x1800201b4  mov     r8d, r10d
0x1800201b7  ror     eax, 13h
0x1800201ba  xor     r8d, r13d
0x1800201bd  ror     r8d, 12h
0x1800201c1  imul    r8d, dword ptr [rsp+0E8h+var_98]
0x1800201c7  sub     r8d, eax
0x1800201ca  xor     r8d, r9d
0x1800201cd  sub     ecx, r8d
0x1800201d0  mov     eax, r8d
0x1800201d3  ror     eax, 8
0x1800201d6  ror     ecx, 1Ch
0x1800201d9  imul    ecx, r11d
0x1800201dd  add     ecx, eax
0x1800201df  mov     rax, [rsp+0E8h+var_88]
0x1800201e4  xor     ecx, r10d
0x1800201e7  mov     r10d, ecx
0x1800201ea  sub     r10d, eax
0x1800201ed  mov     eax, ecx
0x1800201ef  ror     r10d, 17h
0x1800201f3  imul    r10d, edi
0x1800201f7  ror     eax, 1Eh
0x1800201fa  add     r10d, eax
0x1800201fd  xor     r10d, r8d
0x180020200  mov     r13d, r10d
0x180020203  mov     eax, r10d
0x180020206  xor     r13d, edi
0x180020209  imul    r13d, ebx
0x18002020d  mov     ebx, [rsp+0E8h+var_C4]
0x180020211  lea     r9, [rsp+0E8h+var_B0]
0x180020216  shr     eax, 0Dh
0x180020219  mov     r8, r15
0x18002021c  add     r13d, eax
0x18002021f  mov     [rsp+0E8h+var_B0], 0
0x180020228  xor     r13d, ecx
0x18002022b  mov     ecx, ebx
0x18002022d  nop     dword ptr [rax]
0x180020230  movzx   eax, byte ptr [r8]
0x180020234  lea     r8, [r8+1]
0x180020238  mov     [r9], al
0x18002023b  lea     r9, [r9+1]
0x18002023f  sub     rcx, 1
0x180020243  jnz     short loc_180020230
0x180020245  mov     r11d, dword ptr [rsp+0E8h+var_B0+4]
0x18002024a  lea     r8, [rsp+0E8h+var_C0]
0x18002024f  mov     rcx, [rsp+0E8h+var_B0]
0x180020254  lea     r8, [r8+rbx]
0x180020258  xor     r10d, ecx
0x18002025b  mov     [rsp+0E8h+arg_20], r11d
0x180020263  xor     r13d, r11d
0x180020266  mov     [rsp+0E8h+var_C4], r10d
0x18002026b  mov     eax, 8
0x180020270  mov     dword ptr [rsp+0E8h+var_C0], r10d
0x180020275  mov     dword ptr [rsp+0E8h+var_C0+4], r13d
0x18002027a  sub     rax, rbx
0x18002027d  jz      short loc_18002029D
0x18002027f  nop
0x180020280  mov     byte ptr [r8], 0
0x180020284  lea     r8, [r8+1]
0x180020288  sub     rax, 1
0x18002028c  jnz     short loc_180020280
0x18002028e  mov     r10d, dword ptr [rsp+0E8h+var_C0]
0x180020293  mov     r13d, dword ptr [rsp+0E8h+var_C0+4]
0x180020298  mov     [rsp+0E8h+var_C4], r10d
0x18002029d  mov     r8, rbx
0x1800202a0  lea     r9, [rsp+0E8h+var_C0]
0x1800202a5  mov     r10, rbp
0x1800202a8  nop     dword ptr [rax+rax+00000000h]
0x1800202b0  movzx   eax, byte ptr [r9]
0x1800202b4  lea     r9, [r9+1]
0x1800202b8  mov     [r10], al
0x1800202bb  lea     r10, [r10+1]
0x1800202bf  sub     r8, 1
0x1800202c3  jnz     short loc_1800202B0
0x1800202c5  mov     rdi, [rsp+0E8h+var_A0]
0x1800202ca  mov     r8, [rsp+0E8h+var_90]
0x1800202cf  lea     rax, [rbx+rbp]
0x1800202d3  mov     r9, rdi
0x1800202d6  mov     [rsp+0E8h+var_90], rax
0x1800202db  lea     r10, [rbx+r15]
0x1800202df  mov     rax, [rsp+0E8h+var_70]
0x1800202e4  shr     rax, 3
0x1800202e8  mov     [rsp+0E8h+var_80], rax
0x1800202ed  test    rax, rax
0x1800202f0  jz      loc_1800204AA
0x1800202f6  mov     rsi, [rsp+0E8h+var_88]
0x1800202fb  xor     ebp, ebp
0x1800202fd  mov     r15d, [rsp+0E8h+var_C4]
0x180020302  mov     r12, [rsp+0E8h+var_80]
0x180020307  mov     r14, [rsp+0E8h+var_98]
0x18002030c  mov     edx, [rsp+0E8h+arg_20]
0x180020313  movzx   eax, r8w
0x180020317  mov     dword ptr [rsp+0E8h+var_A0], eax
0x18002031b  movzx   eax, si
0x18002031e  movzx   r8d, r9w
0x180020322  mov     dword ptr [rsp+0E8h+var_B0], eax
0x180020326  mov     [rsp+0E8h+var_B8], r8d
0x18002032b  nop     dword ptr [rax+rax+00h]
0x180020330  mov     rax, [r10]
0x180020333  add     r10, 8
0x180020337  mov     [rsp+0E8h+var_80], r10
0x18002033c  mov     rbx, rax
0x18002033f  shr     rbx, 20h
0x180020343  mov     r9d, ebx
0x180020346  xor     r9d, r13d
0x180020349  mov     r13d, dword ptr [rsp+0E8h+var_A0]
0x18002034e  mov     r10d, r9d
0x180020351  sub     r10d, r13d
0x180020354  sub     r10d, esi
0x180020357  xor     r10d, eax
0x18002035a  xor     r10d, r15d
0x18002035d  mov     r15d, ecx
0x180020360  mov     r11d, r10d
0x180020363  sub     r11d, esi
0x180020366  ror     r11d, 0Ch
0x18002036a  imul    r11d, r8d
0x18002036e  mov     r8d, r10d
0x180020371  ror     r8d, 3
0x180020375  xor     r11d, r8d
0x180020378  xor     r11d, r9d
0x18002037b  mov     r8d, r11d
0x18002037e  ror     r8d, 3
0x180020382  lea     r9d, [rdi+r11]
  ... truncated ...
```
