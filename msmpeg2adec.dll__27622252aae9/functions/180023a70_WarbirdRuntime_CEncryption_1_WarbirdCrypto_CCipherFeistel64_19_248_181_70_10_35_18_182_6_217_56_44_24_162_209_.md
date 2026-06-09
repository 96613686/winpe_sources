# WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::Encrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar *)

- ea: `0x180023a70`
- end: `0x180023e37`
- name: `?Encrypt@?$CEncryption@$00V?$CCipherFeistel64@$0BD@$0PI@$0LF@$0EG@$09$0CD@$0BC@$0LG@$05$0NJ@$0DI@$0CM@$0BI@$0KC@$0NB@$0JF@$0BA@$0NF@$0NO@$0LH@$0BE@$0CD@$0DD@$0CI@$0BN@$0IL@$0HD@$0NF@$0M@$0OE@$0BK@$0PN@$03$0FI@$0HI@$0DF@$0BF@$0OF@$0CP@$0OD@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$0A@$0ENFLKLIPNEIOMFLN@@2@UENCRYPTED_SEGMENT_DATA_CONST_2@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@K1@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180022470`

## callees

- `0x1800017b0`
- `0x180023a70`

## pseudocode

```c
void __fastcall WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::Encrypt(
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
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // r15
  unsigned __int64 *v14; // r10
  unsigned __int64 v15; // r12
  int v16; // edx
  int v17; // r8d
  int v18; // ecx
  int v19; // edx
  int v20; // r8d
  int v21; // ecx
  unsigned int v22; // edx
  int v23; // r8d
  int v24; // ebx
  int v25; // esi
  unsigned __int64 *v26; // r8
  __int64 v27; // rcx
  char *v28; // rdx
  char v29; // al
  char *v30; // rdx
  __int64 v31; // rcx
  unsigned __int64 *v32; // r8
  unsigned __int64 *v33; // r9
  __int64 v34; // rdx
  char v35; // cl
  unsigned __int64 *v36; // r13
  unsigned __int64 v37; // rbp
  int v38; // edi
  unsigned __int64 v39; // r11
  int v40; // r9d
  unsigned int v41; // r8d
  int v42; // edx
  int v43; // r10d
  int v44; // r8d
  int v45; // r9d
  int v46; // edx
  int v47; // r10d
  int v48; // ecx
  unsigned __int64 *v49; // rdx
  unsigned __int64 v50; // rsi
  __int16 v51; // [rsp+0h] [rbp-78h]
  unsigned __int64 v52; // [rsp+8h] [rbp-70h] BYREF
  int v53; // [rsp+10h] [rbp-68h]
  unsigned __int64 *v54; // [rsp+18h] [rbp-60h]
  unsigned __int64 v55; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int64 v56; // [rsp+28h] [rbp-50h]

  if ( a3 )
  {
    v8 = a5;
    v9 = ~a5;
    *a6 = a1[a3 - 1];
    v54 = a2;
    v53 = a4;
    v10 = a3 & 7;
    if ( (a3 & 7) != 0 )
    {
      v12 = HIDWORD(a4);
      v15 = HIWORD(a4);
      v13 = a4 >> 16;
      v16 = v9 ^ (__ROR4__(a5, 11) + WORD1(a4) * __ROR4__(a5 - HIDWORD(a4), 17));
      v51 = a4;
      v17 = a5 ^ ((unsigned __int16)a4 * (v16 ^ WORD2(a4)) - __ROR4__(v16, 1));
      v18 = v16 ^ (__ROR4__(v17, 6) + HIWORD(a4) * __ROR4__(a4 + v17, 27));
      v19 = v17 ^ a4 ^ (v18 - WORD2(a4));
      v20 = v18 ^ __ROR4__(v19, 10) ^ (WORD1(a4) * __ROR4__(HIDWORD(a4) ^ v19, 21));
      v21 = v19 ^ ((unsigned __int16)a4 * __ROR4__(HIDWORD(a4) - v20, 6) - __ROR4__(v20, 29));
      v22 = v20 ^ (WORD2(a4) * (HIWORD(a4) + __ROR4__(~v21, 13)));
      v23 = v21 ^ ((v22 >> 15) + WORD2(a4) * __ROL4__((unsigned __int16)a4 ^ v22, 1));
      v24 = v22 ^ (WORD1(a4) * __ROL4__((unsigned __int16)a4 ^ v23, 5) - __ROR4__(v23, 28));
      v25 = v23 ^ __ROR4__(v24, 9) ^ ((unsigned __int16)a4 * __ROR4__(HIDWORD(a4) - v24, 27));
      v56 = 0;
      v55 = 0;
      v26 = &v55;
      v27 = v10;
      v28 = a1;
      do
      {
        v29 = *v28++;
        *(_BYTE *)v26 = v29;
        v26 = (unsigned __int64 *)((char *)v26 + 1);
        --v27;
      }
      while ( v27 );
      v8 = HIDWORD(v55) ^ v25;
      v11 = v55;
      v30 = (char *)&v52 + v10;
      v9 = v55 ^ v24;
      v52 = __PAIR64__(v8, v9);
      v31 = 8 - v10;
      if ( v10 != 8 )
      {
        do
        {
          *v30++ = 0;
          --v31;
        }
        while ( v31 );
        v8 = HIDWORD(v52);
        v9 = v52;
      }
      v14 = v54;
      v32 = &v52;
      v33 = v54;
      v34 = v10;
      do
      {
        v35 = *(_BYTE *)v32;
        v32 = (unsigned __int64 *)((char *)v32 + 1);
        *(_BYTE *)v33 = v35;
        v33 = (unsigned __int64 *)((char *)v33 + 1);
        --v34;
      }
      while ( v34 );
      LOWORD(a4) = v51;
    }
    else
    {
      v11 = 0;
      v12 = HIDWORD(a4);
      v13 = a4 >> 16;
      v14 = a2;
      v56 = 0;
      v15 = HIWORD(a4);
    }
    v36 = (unsigned __int64 *)&a1[v10];
    v37 = a3 >> 3;
    v54 = (unsigned __int64 *)((char *)v14 + v10);
    if ( v37 )
    {
      v38 = (unsigned __int16)a4;
      do
      {
        v39 = *v36++;
        v40 = v8 ^ HIDWORD(v39) ^ __ROR4__(v9 ^ v39, 9) ^ (v38 * __ROR4__(v12 - (v9 ^ v39), 27));
        v41 = v9 ^ v39 ^ ((unsigned __int16)v13 * __ROL4__(v40 ^ v38, 5) - __ROR4__(v40, 28));
        v42 = v40 ^ ((v41 >> 15) + (unsigned __int16)v12 * __ROL4__(v41 ^ v38, 1));
        v43 = v41 ^ ((unsigned __int16)v12 * (v15 + __ROR4__(~v42, 13)));
        v44 = v42 ^ (v38 * __ROR4__(v12 - v43, 6) - __ROR4__(v43, 29));
        v45 = v43 ^ __ROR4__(v44, 10) ^ ((unsigned __int16)v13 * __ROR4__(v12 ^ v44, 21));
        v46 = v53 ^ v44 ^ (v45 - (unsigned __int16)v12);
        v47 = v45 ^ (__ROR4__(v46, 6) + v15 * __ROR4__(v46 + v53, 27));
        v48 = v46 ^ (v38 * ((unsigned __int16)v12 ^ v47) - __ROR4__(v47, 1));
        v49 = v54;
        v9 = v11 ^ v47 ^ (__ROR4__(v48, 11) + (unsigned __int16)v13 * __ROR4__(v48 - v12, 17));
        LODWORD(v52) = v9;
        v50 = HIDWORD(v11);
        v11 = v39;
        v8 = v48 ^ v50;
        HIDWORD(v52) = v8;
        *v54 = v52;
        v54 = v49 + 1;
        ++v56;
      }
      while ( v56 < v37 );
    }
  }
}

```

## disassembly

```asm
0x180023a70  test    r8, r8
0x180023a73  jz      locret_180023E35
0x180023a79  mov     r11, rsp
0x180023a7c  push    rbp
0x180023a7d  push    r13
0x180023a7f  sub     rsp, 68h
0x180023a83  mov     rax, cs:__security_cookie
0x180023a8a  xor     rax, rsp
0x180023a8d  mov     [rsp+78h+var_48], rax
0x180023a92  mov     [r11+8], rbx
0x180023a96  mov     r13, rcx
0x180023a99  mov     rcx, [rsp+78h+arg_28]
0x180023aa1  mov     rbp, r8
0x180023aa4  mov     [r11-18h], rsi
0x180023aa8  mov     esi, [rsp+78h+arg_20]
0x180023aaf  mov     ebx, esi
0x180023ab1  movzx   eax, byte ptr [r13+r8-1]
0x180023ab7  not     ebx
0x180023ab9  mov     [r11-20h], rdi
0x180023abd  mov     rdi, r8
0x180023ac0  mov     [r11-28h], r12
0x180023ac4  mov     r12, r9
0x180023ac7  mov     [r11-30h], r14
0x180023acb  mov     r14, r9
0x180023ace  mov     [r11-38h], r15
0x180023ad2  mov     r15, r9
0x180023ad5  mov     [rcx], al
0x180023ad7  mov     [rsp+78h+var_60], rdx
0x180023adc  mov     [rsp+78h+var_68], r9d
0x180023ae1  and     edi, 7
0x180023ae4  jnz     short loc_180023B01
0x180023ae6  xor     eax, eax
0x180023ae8  shr     r14, 20h
0x180023aec  shr     r15, 10h
0x180023af0  mov     r10, rdx
0x180023af3  mov     [rsp+78h+var_50], rax
0x180023af8  shr     r12, 30h
0x180023afc  jmp     loc_180023C8A
0x180023b01  mov     eax, esi
0x180023b03  shr     r14, 20h
0x180023b07  ror     eax, 0Bh
0x180023b0a  mov     edx, esi
0x180023b0c  sub     edx, r14d
0x180023b0f  movzx   r10d, r14w
0x180023b13  ror     edx, 11h
0x180023b16  mov     r8d, r10d
0x180023b19  shr     r12, 30h
0x180023b1d  shr     r15, 10h
0x180023b21  movzx   r11d, r15w
0x180023b25  imul    edx, r11d
0x180023b29  add     edx, eax
0x180023b2b  xor     edx, ebx
0x180023b2d  movzx   ebx, r9w
0x180023b31  xor     r8d, edx
0x180023b34  mov     dword ptr [rsp+78h+var_78], ebx
0x180023b37  imul    r8d, ebx
0x180023b3b  mov     eax, edx
0x180023b3d  ror     eax, 1
0x180023b3f  sub     r8d, eax
0x180023b42  xor     r8d, esi
0x180023b45  mov     esi, r14d
0x180023b48  mov     eax, r8d
0x180023b4b  ror     eax, 6
0x180023b4e  lea     ecx, [r9+r8]
0x180023b52  ror     ecx, 1Bh
0x180023b55  imul    ecx, r12d
0x180023b59  add     ecx, eax
0x180023b5b  xor     ecx, edx
0x180023b5d  mov     edx, ecx
0x180023b5f  sub     edx, r10d
0x180023b62  xor     edx, r9d
0x180023b65  xor     edx, r8d
0x180023b68  mov     eax, edx
0x180023b6a  mov     r8d, edx
0x180023b6d  xor     r8d, r14d
0x180023b70  ror     eax, 0Ah
0x180023b73  ror     r8d, 15h
0x180023b77  imul    r8d, r11d
0x180023b7b  xor     r8d, eax
0x180023b7e  xor     r8d, ecx
0x180023b81  mov     ecx, r14d
0x180023b84  sub     ecx, r8d
0x180023b87  mov     eax, r8d
0x180023b8a  ror     eax, 1Dh
0x180023b8d  ror     ecx, 6
0x180023b90  imul    ecx, ebx
0x180023b93  sub     ecx, eax
0x180023b95  xor     ecx, edx
0x180023b97  mov     edx, ecx
0x180023b99  not     edx
0x180023b9b  ror     edx, 0Dh
0x180023b9e  add     edx, r12d
0x180023ba1  imul    edx, r10d
0x180023ba5  xor     edx, r8d
0x180023ba8  mov     eax, edx
0x180023baa  mov     r8d, edx
0x180023bad  xor     r8d, ebx
0x180023bb0  shr     eax, 0Fh
0x180023bb3  rol     r8d, 1
0x180023bb6  imul    r8d, r10d
0x180023bba  add     r8d, eax
0x180023bbd  xor     r8d, ecx
0x180023bc0  mov     eax, r8d
0x180023bc3  mov     ebx, r8d
0x180023bc6  xor     ebx, dword ptr [rsp+78h+var_78]
0x180023bc9  rol     ebx, 5
0x180023bcc  ror     eax, 1Ch
0x180023bcf  imul    ebx, r11d
0x180023bd3  sub     ebx, eax
0x180023bd5  xor     ebx, edx
0x180023bd7  sub     esi, ebx
0x180023bd9  mov     eax, ebx
0x180023bdb  ror     esi, 1Bh
0x180023bde  imul    esi, dword ptr [rsp+78h+var_78]
0x180023be2  ror     eax, 9
0x180023be5  xor     esi, eax
0x180023be7  xor     esi, r8d
0x180023bea  xor     eax, eax
0x180023bec  mov     [rsp+78h+var_50], rax
0x180023bf1  mov     [rsp+78h+var_58], rax
0x180023bf6  lea     r8, [rsp+78h+var_58]
0x180023bfb  mov     rcx, rdi
0x180023bfe  mov     rdx, r13
0x180023c01  movzx   eax, byte ptr [rdx]
0x180023c04  lea     rdx, [rdx+1]
0x180023c08  mov     [r8], al
0x180023c0b  lea     r8, [r8+1]
0x180023c0f  sub     rcx, 1
0x180023c13  jnz     short loc_180023C01
0x180023c15  xor     esi, dword ptr [rsp+78h+var_58+4]
0x180023c19  lea     rdx, [rsp+78h+var_70]
0x180023c1e  mov     rax, [rsp+78h+var_58]
0x180023c23  lea     rdx, [rdx+rdi]
0x180023c27  xor     ebx, eax
0x180023c29  mov     dword ptr [rsp+78h+var_70+4], esi
0x180023c2d  mov     ecx, 8
0x180023c32  mov     dword ptr [rsp+78h+var_70], ebx
0x180023c36  sub     rcx, rdi
0x180023c39  jz      short loc_180023C55
0x180023c3b  nop     dword ptr [rax+rax+00h]
0x180023c40  mov     byte ptr [rdx], 0
0x180023c43  lea     rdx, [rdx+1]
0x180023c47  sub     rcx, 1
0x180023c4b  jnz     short loc_180023C40
0x180023c4d  mov     esi, dword ptr [rsp+78h+var_70+4]
0x180023c51  mov     ebx, dword ptr [rsp+78h+var_70]
0x180023c55  mov     r10, [rsp+78h+var_60]
0x180023c5a  lea     r8, [rsp+78h+var_70]
0x180023c5f  mov     r9, r10
0x180023c62  mov     rdx, rdi
0x180023c65  nop     word ptr [rax+rax+00000000h]
0x180023c70  movzx   ecx, byte ptr [r8]
0x180023c74  lea     r8, [r8+1]
0x180023c78  mov     [r9], cl
0x180023c7b  lea     r9, [r9+1]
0x180023c7f  sub     rdx, 1
0x180023c83  jnz     short loc_180023C70
0x180023c85  movzx   r9d, [rsp+78h+var_78]
0x180023c8a  add     r13, rdi
0x180023c8d  shr     rbp, 3
0x180023c91  lea     rcx, [rdi+r10]
0x180023c95  mov     [rsp+78h+var_60], rcx
0x180023c9a  test    rbp, rbp
0x180023c9d  jz      loc_180023E00
0x180023ca3  movzx   ecx, r15w
0x180023ca7  mov     dword ptr [rsp+78h+var_78], ecx
0x180023caa  movzx   edi, r9w
0x180023cae  movzx   r15d, r14w
0x180023cb2  nop     dword ptr [rax+00h]
0x180023cb6  nop     word ptr [rax+rax+00000000h]
0x180023cc0  mov     r11, [r13+0]
0x180023cc4  lea     r13, [r13+8]
0x180023cc8  mov     edx, r11d
0x180023ccb  mov     r9d, r14d
0x180023cce  xor     edx, ebx
0x180023cd0  mov     r8d, edi
0x180023cd3  sub     r9d, edx
0x180023cd6  mov     ecx, edx
0x180023cd8  ror     ecx, 9
0x180023cdb  ror     r9d, 1Bh
0x180023cdf  imul    r9d, edi
0x180023ce3  xor     r9d, ecx
0x180023ce6  mov     rcx, r11
0x180023ce9  shr     rcx, 20h
0x180023ced  xor     r9d, ecx
0x180023cf0  xor     r9d, esi
0x180023cf3  mov     esi, dword ptr [rsp+78h+var_78]
0x180023cf6  xor     r8d, r9d
0x180023cf9  mov     ecx, r9d
0x180023cfc  rol     r8d, 5
0x180023d00  ror     ecx, 1Ch
0x180023d03  imul    r8d, esi
0x180023d07  sub     r8d, ecx
0x180023d0a  xor     r8d, edx
0x180023d0d  mov     edx, edi
0x180023d0f  xor     edx, r8d
0x180023d12  mov     ecx, r8d
0x180023d15  shr     ecx, 0Fh
0x180023d18  rol     edx, 1
0x180023d1a  imul    edx, r15d
0x180023d1e  add     edx, ecx
0x180023d20  xor     edx, r9d
0x180023d23  mov     r10d, edx
0x180023d26  not     r10d
0x180023d29  ror     r10d, 0Dh
0x180023d2d  add     r10d, r12d
0x180023d30  imul    r10d, r15d
0x180023d34  xor     r10d, r8d
0x180023d37  mov     r8d, r14d
0x180023d3a  sub     r8d, r10d
0x180023d3d  mov     ecx, r10d
0x180023d40  ror     ecx, 1Dh
0x180023d43  ror     r8d, 6
0x180023d47  imul    r8d, edi
0x180023d4b  sub     r8d, ecx
0x180023d4e  xor     r8d, edx
0x180023d51  mov     r9d, r8d
0x180023d54  mov     ecx, r8d
0x180023d57  ror     ecx, 0Ah
0x180023d5a  xor     r9d, r14d
0x180023d5d  ror     r9d, 15h
0x180023d61  imul    r9d, esi
0x180023d65  xor     r9d, ecx
0x180023d68  mov     ecx, [rsp+78h+var_68]
0x180023d6c  xor     r9d, r10d
0x180023d6f  mov     edx, r9d
0x180023d72  sub     edx, r15d
0x180023d75  xor     edx, r8d
0x180023d78  xor     edx, ecx
0x180023d7a  lea     r10d, [rdx+rcx]
0x180023d7e  mov     ecx, edx
0x180023d80  ror     ecx, 6
0x180023d83  ror     r10d, 1Bh
0x180023d87  imul    r10d, r12d
0x180023d8b  add     r10d, ecx
0x180023d8e  xor     r10d, r9d
0x180023d91  mov     r8d, r10d
0x180023d94  mov     ecx, r10d
0x180023d97  xor     r8d, r15d
0x180023d9a  ror     ecx, 1
0x180023d9c  imul    r8d, edi
0x180023da0  sub     r8d, ecx
0x180023da3  xor     r8d, edx
0x180023da6  mov     ebx, r8d
0x180023da9  mov     ecx, r8d
0x180023dac  sub     ebx, r14d
0x180023daf  ror     ecx, 0Bh
0x180023db2  ror     ebx, 11h
0x180023db5  imul    ebx, esi
0x180023db8  add     ebx, ecx
0x180023dba  xor     ebx, r10d
0x180023dbd  mov     rdx, [rsp+78h+var_60]
0x180023dc2  xor     ebx, eax
0x180023dc4  mov     rsi, rax
0x180023dc7  mov     dword ptr [rsp+78h+var_70], ebx
0x180023dcb  shr     rsi, 20h
0x180023dcf  mov     rax, r11
0x180023dd2  xor     esi, r8d
0x180023dd5  mov     dword ptr [rsp+78h+var_70+4], esi
0x180023dd9  mov     rcx, [rsp+78h+var_70]
0x180023dde  mov     [rdx], rcx
0x180023de1  add     rdx, 8
0x180023de5  mov     rcx, [rsp+78h+var_50]
0x180023dea  inc     rcx
0x180023ded  mov     [rsp+78h+var_60], rdx
0x180023df2  mov     [rsp+78h+var_50], rcx
0x180023df7  cmp     rcx, rbp
0x180023dfa  jb      loc_180023CC0
0x180023e00  mov     r14, [rsp+78h+var_30]
0x180023e05  mov     r12, [rsp+78h+var_28]
0x180023e0a  mov     r15, [rsp+78h+var_38]
0x180023e0f  mov     rsi, [rsp+78h+var_18]
0x180023e14  mov     rbx, [rsp+78h+arg_0]
0x180023e1c  mov     rdi, [rsp+78h+var_20]
0x180023e21  mov     rcx, [rsp+78h+var_48]
0x180023e26  xor     rcx, rsp; StackCookie
0x180023e29  call    __security_check_cookie
0x180023e2e  add     rsp, 68h
0x180023e32  pop     r13
0x180023e34  pop     rbp
0x180023e35  retn
```
