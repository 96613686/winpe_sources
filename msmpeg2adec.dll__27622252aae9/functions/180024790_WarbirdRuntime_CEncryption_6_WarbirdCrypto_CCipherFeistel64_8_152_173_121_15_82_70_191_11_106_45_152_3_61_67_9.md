# WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::Encrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar *)

- ea: `0x180024790`
- end: `0x180024b63`
- name: `?Encrypt@?$CEncryption@$05V?$CCipherFeistel64@$07$0JI@$0KN@$0HJ@$0P@$0FC@$0EG@$0LP@$0L@$0GK@$0CN@$0JI@$02$0DN@$0ED@$08$0M@$0HL@$0DN@$0GO@$04$0KF@$0PE@$0CJ@$0BM@$0NK@$0CA@$0HN@$0A@$0O@$0EG@$0EI@$0BC@$0JE@$0PJ@$0CA@$08$0IG@$0FF@$0ED@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$01$02$0FLGHJNDFFJOLLCJB@@2@UENCRYPTED_SEGMENT_DATA_CONST_7@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@K1@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800232d0`

## callees

- `0x1800017b0`
- `0x180024790`

## pseudocode

```c
void __fastcall WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::Encrypt(
        char *a1,
        unsigned __int64 *a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        int a5,
        _BYTE *a6)
{
  int v8; // esi
  int v9; // ebx
  __int64 v10; // rdi
  _QWORD *v11; // rax
  unsigned __int64 v12; // r12
  unsigned __int64 v13; // r14
  unsigned __int16 v14; // cx
  unsigned __int64 *v15; // r11
  unsigned __int64 v16; // r15
  int v17; // edx
  unsigned int v18; // r8d
  int v19; // ecx
  int v20; // edx
  int v21; // r8d
  int v22; // ecx
  int v23; // edx
  int v24; // r8d
  unsigned int v25; // ebx
  int v26; // esi
  __int64 v27; // rcx
  _BYTE *v28; // r8
  char *v29; // rdx
  char v30; // al
  char *v31; // rdx
  __int64 v32; // rcx
  unsigned __int64 *v33; // r8
  unsigned __int64 *v34; // r10
  __int64 v35; // rdx
  char v36; // cl
  unsigned __int64 v37; // rbp
  __int64 *v38; // rdx
  int v39; // edi
  __int64 v40; // r11
  unsigned int v41; // r9d
  int v42; // r8d
  int v43; // r10d
  int v44; // r9d
  int v45; // edx
  int v46; // r8d
  unsigned int v47; // r9d
  int v48; // r10d
  int v49; // edx
  int v50; // rsi^4
  unsigned __int64 *v51; // rdx
  unsigned __int64 v52; // [rsp+8h] [rbp-60h] BYREF
  _QWORD *v53; // [rsp+10h] [rbp-58h] BYREF
  unsigned __int64 *v54; // [rsp+18h] [rbp-50h]
  unsigned __int64 v55; // [rsp+20h] [rbp-48h]

  if ( a3 )
  {
    v8 = a5;
    v9 = ~a5;
    *a6 = a1[a3 - 1];
    v54 = a2;
    v10 = a3 & 7;
    if ( (a3 & 7) != 0 )
    {
      v13 = HIDWORD(a4);
      v12 = HIWORD(a4);
      v16 = a4 >> 16;
      v17 = v9 ^ (__ROR4__(a5, 6) + WORD1(a4) * __ROL4__(a5 ^ (unsigned __int16)a4, 2));
      v18 = a5 ^ __ROR4__(v17, 2) ^ ((unsigned __int16)a4 * __ROR4__(v17 - HIDWORD(a4), 2));
      v19 = v17 ^ ((v18 >> 11) + HIWORD(a4) * (v18 ^ WORD2(a4)));
      v20 = v18 ^ v19 ^ a4 ^ HIDWORD(a4);
      v21 = v19 ^ (WORD1(a4) * (WORD2(a4) ^ v20)) ^ __ROR4__(v20, 5);
      v22 = v20 ^ (__ROR4__(v21, 18) + (unsigned __int16)a4 * __ROR4__(v21 + HIDWORD(a4), 31));
      v23 = v21 ^ (HIWORD(a4) * (WORD1(a4) ^ v22) + __ROR4__(v22, 8));
      v24 = v22 ^ __ROR4__(v23, 29) ^ (WORD2(a4) * __ROL4__((unsigned __int16)a4 ^ v23, 4));
      v25 = v23 ^ (WORD1(a4) * __ROR4__(v24 + HIDWORD(a4), 9) - __ROR4__(v24, 6));
      v26 = v24 ^ (v25 >> 2) ^ ((unsigned __int16)a4 * __ROL4__(v25 - HIWORD(a4), 6));
      v55 = 0;
      v53 = 0;
      v27 = v10;
      v28 = &v53;
      v29 = a1;
      do
      {
        v30 = *v29++;
        *v28++ = v30;
        --v27;
      }
      while ( v27 );
      v8 = HIDWORD(v53) ^ v26;
      v11 = v53;
      v31 = (char *)&v52 + v10;
      v9 = (unsigned int)v53 ^ v25;
      v52 = __PAIR64__(v8, v9);
      v32 = 8 - v10;
      if ( v10 != 8 )
      {
        do
        {
          *v31++ = 0;
          --v32;
        }
        while ( v32 );
        v8 = HIDWORD(v52);
        v9 = v52;
      }
      v15 = v54;
      v33 = &v52;
      v34 = v54;
      v35 = v10;
      do
      {
        v36 = *(_BYTE *)v33;
        v33 = (unsigned __int64 *)((char *)v33 + 1);
        *(_BYTE *)v34 = v36;
        v34 = (unsigned __int64 *)((char *)v34 + 1);
        --v35;
      }
      while ( v35 );
      v14 = a4;
    }
    else
    {
      v11 = 0;
      v12 = HIWORD(a4);
      v13 = HIDWORD(a4);
      v14 = a4;
      v55 = 0;
      v15 = a2;
      v16 = a4 >> 16;
    }
    v37 = a3 >> 3;
    v54 = (unsigned __int64 *)((char *)v15 + v10);
    v38 = (__int64 *)&a1[v10];
    if ( v37 )
    {
      v39 = a4 ^ v13;
      do
      {
        v40 = *v38;
        v53 = v38 + 1;
        v41 = v8 ^ ((v9 ^ (unsigned int)v40) >> 2) ^ HIDWORD(v40) ^ (v14 * __ROL4__((v9 ^ v40) - v12, 6));
        v42 = v9 ^ v40 ^ ((unsigned __int16)v16 * __ROR4__(v41 + v13, 9) - __ROR4__(v41, 6));
        v43 = v41 ^ __ROR4__(v42, 29) ^ ((unsigned __int16)v13 * __ROL4__(v42 ^ v14, 4));
        v44 = v42 ^ (v12 * ((unsigned __int16)v16 ^ v43) + __ROR4__(v43, 8));
        v45 = v43 ^ (__ROR4__(v44, 18) + v14 * __ROR4__(v44 + v13, 31));
        v46 = v44 ^ ((unsigned __int16)v16 * ((unsigned __int16)v13 ^ v45)) ^ __ROR4__(v45, 5);
        v47 = v39 ^ v45 ^ v46;
        v48 = v46 ^ ((v47 >> 11) + v12 * ((unsigned __int16)v13 ^ v47));
        v49 = v47 ^ __ROR4__(v48, 2) ^ (v14 * __ROR4__(v48 - v13, 2));
        v9 = (unsigned int)v11 ^ v48 ^ (__ROR4__(v49, 6) + (unsigned __int16)v16 * __ROL4__(v14 ^ v49, 2));
        LODWORD(v52) = v9;
        v50 = HIDWORD(v11);
        v11 = (_QWORD *)v40;
        v8 = v49 ^ v50;
        v51 = v54;
        HIDWORD(v52) = v8;
        *v54 = v52;
        v54 = v51 + 1;
        v38 = v53;
        ++v55;
      }
      while ( v55 < v37 );
    }
  }
}

```

## disassembly

```asm
0x180024790  test    r8, r8
0x180024793  jz      locret_180024B61
0x180024799  push    rbp
0x18002479a  push    r13
0x18002479c  sub     rsp, 58h
0x1800247a0  mov     rax, cs:__security_cookie
0x1800247a7  xor     rax, rsp
0x1800247aa  mov     [rsp+68h+var_40], rax
0x1800247af  mov     [rsp+68h+arg_0], rbx
0x1800247b4  mov     r13, rcx
0x1800247b7  mov     rcx, [rsp+68h+arg_28]
0x1800247bf  mov     rbp, r8
0x1800247c2  mov     [rsp+68h+var_18], rsi
0x1800247c7  mov     esi, [rsp+68h+arg_20]
0x1800247ce  mov     ebx, esi
0x1800247d0  movzx   eax, byte ptr [r13+r8-1]
0x1800247d6  not     ebx
0x1800247d8  mov     [rsp+68h+var_20], rdi
0x1800247dd  mov     rdi, r8
0x1800247e0  mov     [rsp+68h+var_28], r12
0x1800247e5  mov     r12, r9
0x1800247e8  mov     [rsp+68h+var_30], r14
0x1800247ed  mov     r14, r9
0x1800247f0  mov     [rsp+68h+var_38], r15
0x1800247f5  mov     r15, r9
0x1800247f8  mov     [rcx], al
0x1800247fa  mov     [rsp+68h+var_50], rdx
0x1800247ff  and     edi, 7
0x180024802  jnz     short loc_180024823
0x180024804  xor     eax, eax
0x180024806  shr     r12, 30h
0x18002480a  shr     r14, 20h
0x18002480e  movzx   ecx, r9w
0x180024812  mov     [rsp+68h+var_48], rax
0x180024817  mov     r11, rdx
0x18002481a  shr     r15, 10h
0x18002481e  jmp     loc_1800249B8
0x180024823  mov     eax, esi
0x180024825  shr     r14, 20h
0x180024829  ror     eax, 6
0x18002482c  movzx   ecx, r9w
0x180024830  mov     [rsp+68h+var_68], ecx
0x180024833  mov     edx, ecx
0x180024835  xor     edx, esi
0x180024837  shr     r12, 30h
0x18002483b  rol     edx, 2
0x18002483e  movzx   r10d, r14w
0x180024842  shr     r15, 10h
0x180024846  movzx   r11d, r15w
0x18002484a  imul    edx, r11d
0x18002484e  add     edx, eax
0x180024850  xor     edx, ebx
0x180024852  mov     eax, edx
0x180024854  mov     r8d, edx
0x180024857  ror     eax, 2
0x18002485a  sub     r8d, r14d
0x18002485d  ror     r8d, 2
0x180024861  imul    r8d, ecx
0x180024865  mov     ecx, r10d
0x180024868  xor     r8d, eax
0x18002486b  xor     r8d, esi
0x18002486e  xor     ecx, r8d
0x180024871  mov     eax, r8d
0x180024874  shr     eax, 0Bh
0x180024877  imul    ecx, r12d
0x18002487b  add     ecx, eax
0x18002487d  xor     ecx, edx
0x18002487f  mov     edx, r14d
0x180024882  xor     edx, r9d
0x180024885  xor     edx, ecx
0x180024887  xor     edx, r8d
0x18002488a  mov     eax, edx
0x18002488c  mov     r8d, edx
0x18002488f  xor     eax, r10d
0x180024892  ror     r8d, 5
0x180024896  imul    eax, r11d
0x18002489a  xor     r8d, eax
0x18002489d  xor     r8d, ecx
0x1800248a0  mov     eax, r8d
0x1800248a3  ror     eax, 12h
0x1800248a6  lea     ecx, [r8+r14]
0x1800248aa  ror     ecx, 1Fh
0x1800248ad  imul    ecx, [rsp+68h+var_68]
0x1800248b1  add     ecx, eax
0x1800248b3  xor     ecx, edx
0x1800248b5  mov     eax, ecx
0x1800248b7  mov     edx, ecx
0x1800248b9  xor     eax, r11d
0x1800248bc  ror     edx, 8
0x1800248bf  imul    eax, r12d
0x1800248c3  add     edx, eax
0x1800248c5  xor     edx, r8d
0x1800248c8  mov     eax, edx
0x1800248ca  mov     r8d, edx
0x1800248cd  xor     r8d, [rsp+68h+var_68]
0x1800248d1  ror     eax, 1Dh
0x1800248d4  rol     r8d, 4
0x1800248d8  imul    r8d, r10d
0x1800248dc  xor     r8d, eax
0x1800248df  xor     r8d, ecx
0x1800248e2  mov     eax, r8d
0x1800248e5  ror     eax, 6
0x1800248e8  lea     ebx, [r8+r14]
0x1800248ec  ror     ebx, 9
0x1800248ef  imul    ebx, r11d
0x1800248f3  sub     ebx, eax
0x1800248f5  xor     ebx, edx
0x1800248f7  mov     eax, ebx
0x1800248f9  mov     esi, ebx
0x1800248fb  sub     esi, r12d
0x1800248fe  shr     eax, 2
0x180024901  rol     esi, 6
0x180024904  imul    esi, [rsp+68h+var_68]
0x180024908  xor     esi, eax
0x18002490a  xor     esi, r8d
0x18002490d  xor     eax, eax
0x18002490f  mov     [rsp+68h+var_48], rax
0x180024914  mov     [rsp+68h+var_58], rax
0x180024919  mov     rcx, rdi
0x18002491c  lea     r8, [rsp+68h+var_58]
0x180024921  mov     rdx, r13
0x180024924  nop     dword ptr [rax+00h]
0x180024928  nop     dword ptr [rax+rax+00000000h]
0x180024930  movzx   eax, byte ptr [rdx]
0x180024933  lea     rdx, [rdx+1]
0x180024937  mov     [r8], al
0x18002493a  lea     r8, [r8+1]
0x18002493e  sub     rcx, 1
0x180024942  jnz     short loc_180024930
0x180024944  xor     esi, dword ptr [rsp+68h+var_58+4]
0x180024948  lea     rdx, [rsp+68h+var_60]
0x18002494d  mov     rax, [rsp+68h+var_58]
0x180024952  lea     rdx, [rdx+rdi]
0x180024956  xor     ebx, eax
0x180024958  mov     dword ptr [rsp+68h+var_60+4], esi
0x18002495c  mov     ecx, 8
0x180024961  mov     dword ptr [rsp+68h+var_60], ebx
0x180024965  sub     rcx, rdi
0x180024968  jz      short loc_180024985
0x18002496a  nop     word ptr [rax+rax+00h]
0x180024970  mov     byte ptr [rdx], 0
0x180024973  lea     rdx, [rdx+1]
0x180024977  sub     rcx, 1
0x18002497b  jnz     short loc_180024970
0x18002497d  mov     esi, dword ptr [rsp+68h+var_60+4]
0x180024981  mov     ebx, dword ptr [rsp+68h+var_60]
0x180024985  mov     r11, [rsp+68h+var_50]
0x18002498a  lea     r8, [rsp+68h+var_60]
0x18002498f  mov     r10, r11
0x180024992  mov     rdx, rdi
0x180024995  nop     word ptr [rax+rax+00000000h]
0x1800249a0  movzx   ecx, byte ptr [r8]
0x1800249a4  lea     r8, [r8+1]
0x1800249a8  mov     [r10], cl
0x1800249ab  lea     r10, [r10+1]
0x1800249af  sub     rdx, 1
0x1800249b3  jnz     short loc_1800249A0
0x1800249b5  mov     ecx, [rsp+68h+var_68]
0x1800249b8  shr     rbp, 3
0x1800249bc  lea     r8, [rdi+r11]
0x1800249c0  mov     [rsp+68h+var_50], r8
0x1800249c5  lea     rdx, [rdi+r13]
0x1800249c9  test    rbp, rbp
0x1800249cc  jz      loc_180024B2F
0x1800249d2  movzx   r13d, cx
0x1800249d6  mov     edi, r14d
0x1800249d9  movzx   ecx, r14w
0x1800249dd  xor     edi, r9d
0x1800249e0  mov     [rsp+68h+var_68], ecx
0x1800249e3  movzx   r15d, r15w
0x1800249e7  nop     word ptr [rax+rax+00000000h]
0x1800249f0  mov     r11, [rdx]
0x1800249f3  mov     r10d, r13d
0x1800249f6  add     rdx, 8
0x1800249fa  mov     rcx, r11
0x1800249fd  shr     rcx, 20h
0x180024a01  mov     [rsp+68h+var_58], rdx
0x180024a06  mov     edx, r11d
0x180024a09  xor     edx, ebx
0x180024a0b  mov     ebx, [rsp+68h+var_68]
0x180024a0e  mov     r9d, edx
0x180024a11  sub     r9d, r12d
0x180024a14  rol     r9d, 6
0x180024a18  imul    r9d, r13d
0x180024a1c  xor     r9d, ecx
0x180024a1f  mov     ecx, edx
0x180024a21  shr     ecx, 2
0x180024a24  xor     r9d, ecx
0x180024a27  xor     r9d, esi
0x180024a2a  mov     ecx, r9d
0x180024a2d  ror     ecx, 6
0x180024a30  lea     r8d, [r9+r14]
0x180024a34  ror     r8d, 9
0x180024a38  imul    r8d, r15d
0x180024a3c  sub     r8d, ecx
0x180024a3f  xor     r8d, edx
0x180024a42  xor     r10d, r8d
0x180024a45  mov     ecx, r8d
0x180024a48  ror     ecx, 1Dh
0x180024a4b  rol     r10d, 4
0x180024a4f  imul    r10d, ebx
0x180024a53  xor     r10d, ecx
0x180024a56  xor     r10d, r9d
0x180024a59  mov     ecx, r10d
0x180024a5c  mov     r9d, r10d
0x180024a5f  xor     ecx, r15d
0x180024a62  ror     r9d, 8
0x180024a66  imul    ecx, r12d
0x180024a6a  add     r9d, ecx
0x180024a6d  xor     r9d, r8d
0x180024a70  mov     ecx, r9d
0x180024a73  ror     ecx, 12h
0x180024a76  lea     edx, [r9+r14]
0x180024a7a  ror     edx, 1Fh
0x180024a7d  imul    edx, r13d
0x180024a81  add     edx, ecx
0x180024a83  xor     edx, r10d
0x180024a86  mov     ecx, edx
0x180024a88  mov     r8d, edx
0x180024a8b  xor     ecx, ebx
0x180024a8d  ror     r8d, 5
0x180024a91  imul    ecx, r15d
0x180024a95  xor     r8d, ecx
0x180024a98  xor     r8d, r9d
0x180024a9b  mov     r9d, r8d
0x180024a9e  xor     r9d, edx
0x180024aa1  xor     r9d, edi
0x180024aa4  mov     r10d, r9d
0x180024aa7  mov     ecx, r9d
0x180024aaa  xor     r10d, ebx
0x180024aad  shr     ecx, 0Bh
0x180024ab0  imul    r10d, r12d
0x180024ab4  add     r10d, ecx
0x180024ab7  xor     r10d, r8d
0x180024aba  mov     edx, r10d
0x180024abd  mov     ecx, r10d
0x180024ac0  sub     edx, r14d
0x180024ac3  ror     ecx, 2
0x180024ac6  ror     edx, 2
0x180024ac9  imul    edx, r13d
0x180024acd  xor     edx, ecx
0x180024acf  xor     edx, r9d
0x180024ad2  mov     ebx, edx
0x180024ad4  mov     ecx, edx
0x180024ad6  xor     ebx, r13d
0x180024ad9  ror     ecx, 6
0x180024adc  rol     ebx, 2
0x180024adf  imul    ebx, r15d
0x180024ae3  add     ebx, ecx
0x180024ae5  xor     ebx, r10d
0x180024ae8  xor     ebx, eax
0x180024aea  mov     dword ptr [rsp+68h+var_60], ebx
0x180024aee  mov     rsi, rax
0x180024af1  mov     rax, r11
0x180024af4  shr     rsi, 20h
0x180024af8  xor     esi, edx
0x180024afa  mov     rdx, [rsp+68h+var_50]
0x180024aff  mov     dword ptr [rsp+68h+var_60+4], esi
0x180024b03  mov     rcx, [rsp+68h+var_60]
0x180024b08  mov     [rdx], rcx
0x180024b0b  add     rdx, 8
0x180024b0f  mov     rcx, [rsp+68h+var_48]
0x180024b14  inc     rcx
0x180024b17  mov     [rsp+68h+var_50], rdx
0x180024b1c  mov     rdx, [rsp+68h+var_58]
0x180024b21  mov     [rsp+68h+var_48], rcx
0x180024b26  cmp     rcx, rbp
0x180024b29  jb      loc_1800249F0
0x180024b2f  mov     r14, [rsp+68h+var_30]
0x180024b34  mov     r12, [rsp+68h+var_28]
0x180024b39  mov     r15, [rsp+68h+var_38]
0x180024b3e  mov     rsi, [rsp+68h+var_18]
0x180024b43  mov     rbx, [rsp+68h+arg_0]
0x180024b48  mov     rdi, [rsp+68h+var_20]
0x180024b4d  mov     rcx, [rsp+68h+var_40]
0x180024b52  xor     rcx, rsp; StackCookie
0x180024b55  call    __security_check_cookie
0x180024b5a  add     rsp, 58h
0x180024b5e  pop     r13
0x180024b60  pop     rbp
0x180024b61  retn
```
