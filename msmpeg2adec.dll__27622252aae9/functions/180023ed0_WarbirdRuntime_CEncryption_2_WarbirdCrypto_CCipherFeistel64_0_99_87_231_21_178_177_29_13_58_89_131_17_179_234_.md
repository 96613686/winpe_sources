# WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Encrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar *)

- ea: `0x180023ed0`
- end: `0x180024286`
- name: `?Encrypt@?$CEncryption@$01V?$CCipherFeistel64@$0A@$0GD@$0FH@$0OH@$0BF@$0LC@$0LB@$0BN@$0N@$0DK@$0FJ@$0ID@$0BB@$0LD@$0OK@$0FA@$0BD@$0LL@$0MF@$0MH@$02$0EA@$0JO@$01$01$0PL@$0GM@$0KE@$0P@$0LK@$0EI@$0NL@$0BC@$09$0CK@$0LM@$0BO@$0GO@$0HK@$0DC@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$00$0BKGBKNDEJDGFEBEE@@2@UENCRYPTED_SEGMENT_DATA_CONST_3@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_3@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@K1@Z`
- size: `950`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180022820`

## callees

- `0x1800017b0`
- `0x180023ed0`

## pseudocode

```c
void __fastcall WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Encrypt(
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
  unsigned __int64 v11; // r11
  unsigned __int64 v12; // r15
  unsigned __int64 v13; // r14
  __int64 v14; // rax
  unsigned __int64 v15; // r12
  unsigned __int64 *v16; // r10
  int v17; // edx
  int v18; // r8d
  unsigned int v19; // ecx
  int v20; // edx
  int v21; // r8d
  int v22; // r9d
  int v23; // edx
  int v24; // ecx
  unsigned int v25; // ebx
  int v26; // esi
  __int64 *v27; // r8
  __int64 v28; // rcx
  char *v29; // rdx
  char v30; // al
  char *v31; // rdx
  __int64 v32; // rcx
  unsigned __int64 *v33; // r8
  unsigned __int64 *v34; // r9
  __int64 v35; // rdx
  char v36; // cl
  __int64 *v37; // r13
  unsigned __int64 v38; // rbp
  int v39; // edi
  int v40; // r15d
  __int64 v41; // r10
  int v42; // r9d
  int v43; // r8d
  int v44; // edx
  int v45; // r9d
  int v46; // r8d
  unsigned int v47; // edx
  int v48; // r9d
  int v49; // r8d
  int v50; // edx
  unsigned __int64 *v51; // rdx
  int v52; // [rsp+0h] [rbp-68h]
  unsigned __int64 v53; // [rsp+8h] [rbp-60h] BYREF
  int v54; // [rsp+10h] [rbp-58h]
  unsigned __int64 *v55; // [rsp+18h] [rbp-50h]
  __int64 v56; // [rsp+20h] [rbp-48h] BYREF

  if ( a3 )
  {
    v8 = a5;
    v9 = ~a5;
    *a6 = a1[a3 - 1];
    v55 = a2;
    v10 = a3 & 7;
    if ( (a3 & 7) != 0 )
    {
      v52 = (unsigned __int16)a4;
      v13 = HIDWORD(a4);
      v15 = HIWORD(a4);
      v12 = a4 >> 16;
      v17 = v9 ^ (a5 - WORD1(a4) - HIDWORD(a4));
      v54 = a4;
      v18 = a5 ^ __ROR4__(v17, 3) ^ ((unsigned __int16)a4 * __ROR4__(v17 - HIDWORD(a4), 12));
      v19 = v17 ^ (HIWORD(a4) * __ROR4__(a4 + v18, 11) - __ROR4__(v18, 3));
      v20 = v18 ^ (v19 >> 4) ^ (WORD2(a4) * (WORD1(a4) ^ v19));
      v21 = v19 ^ (WORD1(a4) * (HIWORD(a4) ^ v20) + __ROR4__(v20, 9));
      v22 = v20 ^ __ROR4__(v21, 14) ^ ((unsigned __int16)a4 * __ROR4__(HIDWORD(a4) - v21, 12));
      v23 = v21 ^ (v15 * __ROR4__(v54 ^ v22, 18) - __ROR4__(v22, 19));
      v24 = v22 ^ (__ROR4__(v23, 8) + (unsigned __int16)v13 * __ROR4__(v54 - v23, 28));
      v25 = v23 ^ (__ROR4__(v24, 30) + (unsigned __int16)v12 * __ROR4__(v24 - v13, 23));
      v26 = v24 ^ ((v25 >> 13) + v52 * ((unsigned __int16)v12 ^ v25));
      v11 = 0;
      v27 = &v56;
      v56 = 0;
      v28 = v10;
      v29 = a1;
      do
      {
        v30 = *v29++;
        *(_BYTE *)v27 = v30;
        v27 = (__int64 *)((char *)v27 + 1);
        --v28;
      }
      while ( v28 );
      v8 = HIDWORD(v56) ^ v26;
      v14 = v56;
      v31 = (char *)&v53 + v10;
      v9 = v56 ^ v25;
      v53 = __PAIR64__(v8, v9);
      v32 = 8 - v10;
      if ( v10 != 8 )
      {
        do
        {
          *v31++ = 0;
          --v32;
        }
        while ( v32 );
        v8 = HIDWORD(v53);
        v9 = v53;
      }
      v16 = v55;
      v33 = &v53;
      v34 = v55;
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
      LOWORD(a4) = v52;
    }
    else
    {
      v11 = 0;
      v12 = a4 >> 16;
      v13 = HIDWORD(a4);
      v14 = 0;
      v15 = HIWORD(a4);
      v16 = a2;
      v54 = a4;
    }
    v37 = (__int64 *)&a1[v10];
    v38 = a3 >> 3;
    v55 = (unsigned __int64 *)((char *)v16 + v10);
    if ( v38 )
    {
      v39 = (unsigned __int16)v12;
      v40 = (unsigned __int16)a4;
      do
      {
        v41 = *v37++;
        v42 = v8 ^ HIDWORD(v41) ^ (((v9 ^ (unsigned int)v41) >> 13) + v40 * (v39 ^ v9 ^ v41));
        v43 = v9 ^ v41 ^ (__ROR4__(v42, 30) + v39 * __ROR4__(v42 - v13, 23));
        v44 = v42 ^ (__ROR4__(v43, 8) + (unsigned __int16)v13 * __ROR4__(v54 - v43, 28));
        v45 = v43 ^ (v15 * __ROR4__(v54 ^ v44, 18) - __ROR4__(v44, 19));
        v46 = v44 ^ __ROR4__(v45, 14) ^ (v40 * __ROR4__(v13 - v45, 12));
        v47 = v45 ^ (v39 * (v15 ^ v46) + __ROR4__(v46, 9));
        v48 = v46 ^ (v47 >> 4) ^ ((unsigned __int16)v13 * (v39 ^ v47));
        v49 = v47 ^ (v15 * __ROR4__(v48 + v54, 11) - __ROR4__(v48, 3));
        v50 = v48 ^ __ROR4__(v49, 3) ^ (v40 * __ROR4__(v49 - v13, 12));
        v9 = v14 ^ v49 ^ (v50 - v13 - v39);
        LODWORD(v53) = v9;
        ++v11;
        v8 = v50 ^ HIDWORD(v14);
        v14 = v41;
        v51 = v55;
        HIDWORD(v53) = v8;
        *v55 = v53;
        v55 = v51 + 1;
      }
      while ( v11 < v38 );
    }
  }
}

```

## disassembly

```asm
0x180023ed0  test    r8, r8
0x180023ed3  jz      locret_180024284
0x180023ed9  push    rbp
0x180023eda  push    r13
0x180023edc  sub     rsp, 58h
0x180023ee0  mov     rax, cs:__security_cookie
0x180023ee7  xor     rax, rsp
0x180023eea  mov     [rsp+68h+var_40], rax
0x180023eef  mov     [rsp+68h+arg_0], rbx
0x180023ef4  mov     r13, rcx
0x180023ef7  mov     rcx, [rsp+68h+arg_28]
0x180023eff  mov     rbp, r8
0x180023f02  mov     [rsp+68h+var_18], rsi
0x180023f07  mov     esi, [rsp+68h+arg_20]
0x180023f0e  mov     ebx, esi
0x180023f10  movzx   eax, byte ptr [r13+r8-1]
0x180023f16  not     ebx
0x180023f18  mov     [rsp+68h+var_20], rdi
0x180023f1d  mov     rdi, r8
0x180023f20  mov     [rsp+68h+var_28], r12
0x180023f25  mov     r12, r9
0x180023f28  mov     [rsp+68h+var_30], r14
0x180023f2d  mov     r14, r9
0x180023f30  mov     [rsp+68h+var_38], r15
0x180023f35  mov     r15, r9
0x180023f38  mov     [rcx], al
0x180023f3a  mov     [rsp+68h+var_50], rdx
0x180023f3f  and     edi, 7
0x180023f42  jnz     short loc_180023F63
0x180023f44  xor     r11d, r11d
0x180023f47  shr     r15, 10h
0x180023f4b  shr     r14, 20h
0x180023f4f  mov     eax, r11d
0x180023f52  shr     r12, 30h
0x180023f56  mov     r10, rdx
0x180023f59  mov     [rsp+68h+var_58], r9d
0x180023f5e  jmp     loc_1800240FA
0x180023f63  movzx   eax, r9w
0x180023f67  mov     edx, esi
0x180023f69  mov     [rsp+68h+var_68], eax
0x180023f6c  shr     r14, 20h
0x180023f70  shr     r12, 30h
0x180023f74  shr     r15, 10h
0x180023f78  movzx   r11d, r15w
0x180023f7c  sub     edx, r11d
0x180023f7f  movzx   r10d, r14w
0x180023f83  sub     edx, r14d
0x180023f86  xor     edx, ebx
0x180023f88  mov     ebx, r9d
0x180023f8b  mov     r8d, edx
0x180023f8e  mov     [rsp+68h+var_58], ebx
0x180023f92  sub     r8d, r14d
0x180023f95  ror     r8d, 0Ch
0x180023f99  imul    r8d, eax
0x180023f9d  mov     eax, edx
0x180023f9f  ror     eax, 3
0x180023fa2  xor     r8d, eax
0x180023fa5  xor     r8d, esi
0x180023fa8  mov     eax, r8d
0x180023fab  ror     eax, 3
0x180023fae  lea     ecx, [r9+r8]
0x180023fb2  mov     r9d, r14d
0x180023fb5  ror     ecx, 0Bh
0x180023fb8  imul    ecx, r12d
0x180023fbc  sub     ecx, eax
0x180023fbe  xor     ecx, edx
0x180023fc0  mov     edx, ecx
0x180023fc2  mov     eax, ecx
0x180023fc4  shr     eax, 4
0x180023fc7  xor     edx, r11d
0x180023fca  imul    edx, r10d
0x180023fce  xor     edx, eax
0x180023fd0  xor     edx, r8d
0x180023fd3  mov     eax, edx
0x180023fd5  mov     r8d, edx
0x180023fd8  xor     eax, r12d
0x180023fdb  ror     r8d, 9
0x180023fdf  imul    eax, r11d
0x180023fe3  add     r8d, eax
0x180023fe6  xor     r8d, ecx
0x180023fe9  mov     ecx, ebx
0x180023feb  sub     r9d, r8d
0x180023fee  mov     eax, r8d
0x180023ff1  ror     eax, 0Eh
0x180023ff4  ror     r9d, 0Ch
0x180023ff8  imul    r9d, [rsp+68h+var_68]
0x180023ffd  xor     r9d, eax
0x180024000  xor     r9d, edx
0x180024003  mov     edx, r9d
0x180024006  mov     eax, r9d
0x180024009  xor     edx, ebx
0x18002400b  ror     eax, 13h
0x18002400e  ror     edx, 12h
0x180024011  imul    edx, r12d
0x180024015  sub     edx, eax
0x180024017  xor     edx, r8d
0x18002401a  sub     ecx, edx
0x18002401c  mov     eax, edx
0x18002401e  ror     eax, 8
0x180024021  ror     ecx, 1Ch
0x180024024  imul    ecx, r10d
0x180024028  add     ecx, eax
0x18002402a  xor     ecx, r9d
0x18002402d  mov     ebx, ecx
0x18002402f  mov     eax, ecx
0x180024031  sub     ebx, r14d
0x180024034  ror     eax, 1Eh
0x180024037  ror     ebx, 17h
0x18002403a  imul    ebx, r11d
0x18002403e  add     ebx, eax
0x180024040  xor     ebx, edx
0x180024042  mov     esi, ebx
0x180024044  mov     eax, ebx
0x180024046  xor     esi, r11d
0x180024049  shr     eax, 0Dh
0x18002404c  imul    esi, [rsp+68h+var_68]
0x180024050  add     esi, eax
0x180024052  xor     esi, ecx
0x180024054  xor     r11d, r11d
0x180024057  lea     r8, [rsp+68h+var_48]
0x18002405c  mov     [rsp+68h+var_48], r11
0x180024061  mov     rcx, rdi
0x180024064  mov     rdx, r13
0x180024067  nop     word ptr [rax+rax+00000000h]
0x180024070  movzx   eax, byte ptr [rdx]
0x180024073  lea     rdx, [rdx+1]
0x180024077  mov     [r8], al
0x18002407a  lea     r8, [r8+1]
0x18002407e  sub     rcx, 1
0x180024082  jnz     short loc_180024070
0x180024084  xor     esi, dword ptr [rsp+68h+var_48+4]
0x180024088  lea     rdx, [rsp+68h+var_60]
0x18002408d  mov     rax, [rsp+68h+var_48]
0x180024092  lea     rdx, [rdx+rdi]
0x180024096  xor     ebx, eax
0x180024098  mov     dword ptr [rsp+68h+var_60+4], esi
0x18002409c  mov     ecx, 8
0x1800240a1  mov     dword ptr [rsp+68h+var_60], ebx
0x1800240a5  sub     rcx, rdi
0x1800240a8  jz      short loc_1800240C5
0x1800240aa  nop     word ptr [rax+rax+00h]
0x1800240b0  mov     [rdx], r11b
0x1800240b3  lea     rdx, [rdx+1]
0x1800240b7  sub     rcx, 1
0x1800240bb  jnz     short loc_1800240B0
0x1800240bd  mov     esi, dword ptr [rsp+68h+var_60+4]
0x1800240c1  mov     ebx, dword ptr [rsp+68h+var_60]
0x1800240c5  mov     r10, [rsp+68h+var_50]
0x1800240ca  lea     r8, [rsp+68h+var_60]
0x1800240cf  mov     r9, r10
0x1800240d2  mov     rdx, rdi
0x1800240d5  nop     word ptr [rax+rax+00000000h]
0x1800240e0  movzx   ecx, byte ptr [r8]
0x1800240e4  lea     r8, [r8+1]
0x1800240e8  mov     [r9], cl
0x1800240eb  lea     r9, [r9+1]
0x1800240ef  sub     rdx, 1
0x1800240f3  jnz     short loc_1800240E0
0x1800240f5  movzx   r9d, word ptr [rsp+68h+var_68]
0x1800240fa  add     r13, rdi
0x1800240fd  shr     rbp, 3
0x180024101  lea     rcx, [rdi+r10]
0x180024105  mov     [rsp+68h+var_50], rcx
0x18002410a  test    rbp, rbp
0x18002410d  jz      loc_180024252
0x180024113  movzx   ecx, r14w
0x180024117  movzx   edi, r15w
0x18002411b  mov     [rsp+68h+var_68], ecx
0x18002411e  movzx   r15d, r9w
0x180024122  mov     r10, [r13+0]
0x180024126  lea     r13, [r13+8]
0x18002412a  mov     edx, r10d
0x18002412d  xor     edx, ebx
0x18002412f  mov     ebx, [rsp+68h+var_58]
0x180024133  mov     ecx, edx
0x180024135  mov     r9d, edx
0x180024138  shr     ecx, 0Dh
0x18002413b  xor     r9d, edi
0x18002413e  imul    r9d, r15d
0x180024142  add     r9d, ecx
0x180024145  mov     rcx, r10
0x180024148  shr     rcx, 20h
0x18002414c  xor     r9d, ecx
0x18002414f  xor     r9d, esi
0x180024152  mov     r8d, r9d
0x180024155  mov     ecx, r9d
0x180024158  ror     ecx, 1Eh
0x18002415b  sub     r8d, r14d
0x18002415e  ror     r8d, 17h
0x180024162  imul    r8d, edi
0x180024166  add     r8d, ecx
0x180024169  xor     r8d, edx
0x18002416c  mov     edx, ebx
0x18002416e  sub     edx, r8d
0x180024171  mov     ecx, r8d
0x180024174  ror     ecx, 8
0x180024177  ror     edx, 1Ch
0x18002417a  imul    edx, [rsp+68h+var_68]
0x18002417e  add     edx, ecx
0x180024180  xor     edx, r9d
0x180024183  mov     r9d, edx
0x180024186  mov     ecx, edx
0x180024188  xor     r9d, ebx
0x18002418b  ror     ecx, 13h
0x18002418e  ror     r9d, 12h
0x180024192  imul    r9d, r12d
0x180024196  sub     r9d, ecx
0x180024199  xor     r9d, r8d
0x18002419c  mov     r8d, r14d
0x18002419f  sub     r8d, r9d
0x1800241a2  mov     ecx, r9d
0x1800241a5  ror     ecx, 0Eh
0x1800241a8  ror     r8d, 0Ch
0x1800241ac  imul    r8d, r15d
0x1800241b0  xor     r8d, ecx
0x1800241b3  xor     r8d, edx
0x1800241b6  mov     ecx, r8d
0x1800241b9  mov     edx, r8d
0x1800241bc  ror     edx, 9
0x1800241bf  xor     ecx, r12d
0x1800241c2  imul    ecx, edi
0x1800241c5  add     edx, ecx
0x1800241c7  xor     edx, r9d
0x1800241ca  mov     r9d, edx
0x1800241cd  mov     ecx, edx
0x1800241cf  shr     ecx, 4
0x1800241d2  xor     r9d, edi
0x1800241d5  imul    r9d, [rsp+68h+var_68]
0x1800241da  xor     r9d, ecx
0x1800241dd  xor     r9d, r8d
0x1800241e0  mov     ecx, r9d
0x1800241e3  ror     ecx, 3
0x1800241e6  lea     r8d, [r9+rbx]
0x1800241ea  ror     r8d, 0Bh
0x1800241ee  imul    r8d, r12d
0x1800241f2  sub     r8d, ecx
0x1800241f5  xor     r8d, edx
0x1800241f8  mov     edx, r8d
0x1800241fb  mov     ecx, r8d
0x1800241fe  sub     edx, r14d
0x180024201  ror     ecx, 3
0x180024204  ror     edx, 0Ch
0x180024207  imul    edx, r15d
0x18002420b  xor     edx, ecx
0x18002420d  xor     edx, r9d
0x180024210  mov     ebx, edx
0x180024212  sub     ebx, r14d
0x180024215  sub     ebx, edi
0x180024217  xor     ebx, r8d
0x18002421a  xor     ebx, eax
0x18002421c  mov     rsi, rax
0x18002421f  mov     dword ptr [rsp+68h+var_60], ebx
0x180024223  shr     rsi, 20h
0x180024227  inc     r11
0x18002422a  xor     esi, edx
0x18002422c  mov     rax, r10
0x18002422f  mov     rdx, [rsp+68h+var_50]
0x180024234  mov     dword ptr [rsp+68h+var_60+4], esi
0x180024238  mov     rcx, [rsp+68h+var_60]
0x18002423d  mov     [rdx], rcx
0x180024240  add     rdx, 8
0x180024244  mov     [rsp+68h+var_50], rdx
0x180024249  cmp     r11, rbp
0x18002424c  jb      loc_180024122
0x180024252  mov     r14, [rsp+68h+var_30]
0x180024257  mov     r12, [rsp+68h+var_28]
0x18002425c  mov     r15, [rsp+68h+var_38]
0x180024261  mov     rsi, [rsp+68h+var_18]
0x180024266  mov     rbx, [rsp+68h+arg_0]
0x18002426b  mov     rdi, [rsp+68h+var_20]
0x180024270  mov     rcx, [rsp+68h+var_40]
0x180024275  xor     rcx, rsp; StackCookie
0x180024278  call    __security_check_cookie
0x18002427d  add     rsp, 58h
0x180024281  pop     r13
0x180024283  pop     rbp
0x180024284  retn
```
