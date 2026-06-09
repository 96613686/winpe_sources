# GetHashStringPreRS2(ushort const *,ushort * const)

- ea: `0x1800156f0`
- end: `0x180015b91`
- name: `?GetHashStringPreRS2@@YAJPEBGQEAG@Z`
- size: `1185`
- prototype: `__int64 __fastcall(PUCHAR pbInput, unsigned __int16 *const)`
- caller_count: `7`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000b0c0`
- `0x18000f700`
- `0x180014aa0`
- `0x180014d90`
- `0x18002b6dc`
- `0x18002d71c`
- `0x18003fcdc`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x1800156f0`
- `0x180042410`
- `0x18004317c`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x180015b1e`
- `bcrypt!BCryptDestroyHash` at `0x180015b1e`
- `bcrypt!BCryptFinishHash` at `0x18001579b`
- `bcrypt!BCryptFinishHash` at `0x18001579b`
- `bcrypt!BCryptCreateHash` at `0x180015747`
- `bcrypt!BCryptCreateHash` at `0x180015747`
- `bcrypt!BCryptHashData` at `0x180015778`
- `bcrypt!BCryptHashData` at `0x180015778`

## string_xrefs

- `0x1800157b2`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180015b29`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180015b5d`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180015b44`: `BCryptCreateHash`

## pseudocode

```c
__int64 __fastcall GetHashStringPreRS2(PUCHAR pbInput, unsigned __int16 *const a2)
{
  unsigned int v4; // edi
  __int64 v5; // r8
  const UCHAR *v6; // r9
  char v7; // al
  const UCHAR *v8; // rdx
  bool v9; // zf
  unsigned int i; // r10d
  __int64 v12; // r9
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // r8
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // r8
  unsigned __int64 v21; // r8
  unsigned __int64 v22; // r8
  unsigned __int64 v23; // r8
  unsigned __int64 v24; // r8
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // r8
  unsigned __int64 v27; // r8
  unsigned int v28; // ecx
  unsigned __int64 v29; // r8
  const char *v30; // r9
  const char *v31; // r9
  PUCHAR pbSecret; // [rsp+20h] [rbp-68h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-48h] BYREF
  UCHAR pbOutput[32]; // [rsp+48h] [rbp-40h] BYREF

  phHash = 0;
  memset_0(a2, 0, 0x82u);
  v4 = BCryptCreateHash(g_hSHA256, &phHash, 0, 0, 0, 0, 0);
  if ( v4 )
  {
    v30 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    LODWORD(pbSecret) = 979;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v4, v30, pbSecret, "BCryptCreateHash", &Class);
  }
  else
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)&pbInput[2 * v5] );
    v4 = BCryptHashData(phHash, pbInput, 2 * v5, 0);
    if ( v4 )
    {
      v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      LODWORD(pbSecret) = 988;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v4, v31, pbSecret, "BCryptHashData", &Class);
    }
    else
    {
      v4 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
      if ( v4 )
      {
        v6 = "";
        while ( 1 )
        {
          v7 = *(v6 - 1);
          v8 = v6--;
          v9 = v7 == 92;
          if ( v7 == 92 )
            break;
          if ( v6 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
          {
            v9 = v7 == 92;
            break;
          }
        }
        if ( v9 )
          v6 = v8;
        LODWORD(pbSecret) = 997;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v4, v6, pbSecret, "BCryptFinishHash", &Class);
      }
      else
      {
        for ( i = 0; i < 0x20; i += 16 )
        {
          v12 = 2 * i;
          v13 = (unsigned __int64)pbOutput[i] >> 4;
          a2[v12] = a0123456789abcd[pbOutput[i] & 0xF];
          a2[(unsigned int)(v12 + 1)] = a0123456789abcd[v13];
          v14 = (unsigned __int64)pbOutput[i + 1] >> 4;
          a2[(unsigned int)(v12 + 2)] = a0123456789abcd[pbOutput[i + 1] & 0xF];
          a2[(unsigned int)(v12 + 3)] = a0123456789abcd[v14];
          v15 = (unsigned __int64)pbOutput[i + 2] >> 4;
          a2[2 * i + 4] = a0123456789abcd[pbOutput[i + 2] & 0xF];
          a2[(unsigned int)(v12 + 5)] = a0123456789abcd[v15];
          v16 = (unsigned __int64)pbOutput[i + 3] >> 4;
          a2[2 * i + 6] = a0123456789abcd[pbOutput[i + 3] & 0xF];
          a2[(unsigned int)(v12 + 7)] = a0123456789abcd[v16];
          v17 = (unsigned __int64)pbOutput[i + 4] >> 4;
          a2[2 * i + 8] = a0123456789abcd[pbOutput[i + 4] & 0xF];
          a2[(unsigned int)(v12 + 9)] = a0123456789abcd[v17];
          v18 = (unsigned __int64)pbOutput[i + 5] >> 4;
          a2[2 * i + 10] = a0123456789abcd[pbOutput[i + 5] & 0xF];
          a2[(unsigned int)(v12 + 11)] = a0123456789abcd[v18];
          v19 = (unsigned __int64)pbOutput[i + 6] >> 4;
          a2[2 * i + 12] = a0123456789abcd[pbOutput[i + 6] & 0xF];
          a2[(unsigned int)(v12 + 13)] = a0123456789abcd[v19];
          v20 = (unsigned __int64)pbOutput[i + 7] >> 4;
          a2[2 * i + 14] = a0123456789abcd[pbOutput[i + 7] & 0xF];
          a2[(unsigned int)(v12 + 15)] = a0123456789abcd[v20];
          v21 = (unsigned __int64)pbOutput[i + 8] >> 4;
          a2[2 * i + 16] = a0123456789abcd[pbOutput[i + 8] & 0xF];
          a2[(unsigned int)(v12 + 17)] = a0123456789abcd[v21];
          v22 = (unsigned __int64)pbOutput[i + 9] >> 4;
          a2[2 * i + 18] = a0123456789abcd[pbOutput[i + 9] & 0xF];
          a2[(unsigned int)(v12 + 19)] = a0123456789abcd[v22];
          v23 = (unsigned __int64)pbOutput[i + 10] >> 4;
          a2[2 * i + 20] = a0123456789abcd[pbOutput[i + 10] & 0xF];
          a2[(unsigned int)(v12 + 21)] = a0123456789abcd[v23];
          v24 = (unsigned __int64)pbOutput[i + 11] >> 4;
          a2[2 * i + 22] = a0123456789abcd[pbOutput[i + 11] & 0xF];
          a2[(unsigned int)(v12 + 23)] = a0123456789abcd[v24];
          v25 = (unsigned __int64)pbOutput[i + 12] >> 4;
          a2[2 * i + 24] = a0123456789abcd[pbOutput[i + 12] & 0xF];
          a2[(unsigned int)(v12 + 25)] = a0123456789abcd[v25];
          v26 = (unsigned __int64)pbOutput[i + 13] >> 4;
          a2[2 * i + 26] = a0123456789abcd[pbOutput[i + 13] & 0xF];
          a2[(unsigned int)(v12 + 27)] = a0123456789abcd[v26];
          v27 = (unsigned __int64)pbOutput[i + 14] >> 4;
          a2[2 * i + 28] = a0123456789abcd[pbOutput[i + 14] & 0xF];
          a2[(unsigned int)(v12 + 29)] = a0123456789abcd[v27];
          v28 = i + 15;
          v29 = pbOutput[i + 15];
          a2[2 * v28] = a0123456789abcd[v29 & 0xF];
          a2[(unsigned int)(v12 + 31)] = a0123456789abcd[v29 >> 4];
        }
        a2[64] = 0;
        v4 = 0;
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  return v4;
}

```

## disassembly

```asm
0x1800156f0  mov     [rsp+arg_10], rbx
0x1800156f5  push    rbp
0x1800156f6  push    rsi
0x1800156f7  push    rdi
0x1800156f8  sub     rsp, 70h
0x1800156fc  mov     rax, cs:__security_cookie
0x180015703  xor     rax, rsp
0x180015706  mov     [rsp+88h+var_20], rax
0x18001570b  mov     rbx, rdx
0x18001570e  mov     rsi, rcx
0x180015711  xor     ebp, ebp
0x180015713  mov     rcx, rbx; void *
0x180015716  xor     edx, edx; Val
0x180015718  mov     [rsp+88h+phHash], rbp
0x18001571d  mov     r8d, 82h; Size
0x180015723  call    memset_0
0x180015728  mov     rcx, cs:?g_hSHA256@@3PEAXEA; hAlgorithm
0x18001572f  lea     rdx, [rsp+88h+phHash]; phHash
0x180015734  mov     [rsp+88h+dwFlags], ebp; dwFlags
0x180015738  xor     r9d, r9d; cbHashObject
0x18001573b  mov     [rsp+88h+cbSecret], ebp; cbSecret
0x18001573f  xor     r8d, r8d; pbHashObject
0x180015742  mov     [rsp+88h+pbSecret], rbp; pbSecret
0x180015747  call    cs:__imp_BCryptCreateHash
0x18001574d  mov     edi, eax
0x18001574f  test    eax, eax
0x180015751  jnz     loc_180015B29
0x180015757  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001575e  xchg    ax, ax
0x180015760  inc     r8
0x180015763  cmp     [rsi+r8*2], bp
0x180015768  jnz     short loc_180015760
0x18001576a  mov     rcx, [rsp+88h+phHash]; hHash
0x18001576f  add     r8d, r8d; cbInput
0x180015772  xor     r9d, r9d; dwFlags
0x180015775  mov     rdx, rsi; pbInput
0x180015778  call    cs:__imp_BCryptHashData
0x18001577e  mov     edi, eax
0x180015780  test    eax, eax
0x180015782  jnz     loc_180015B5D
0x180015788  mov     rcx, [rsp+88h+phHash]; hHash
0x18001578d  lea     rdx, [rsp+88h+pbOutput]; pbOutput
0x180015792  xor     r9d, r9d; dwFlags
0x180015795  mov     r8d, 20h ; ' '; cbOutput
0x18001579b  call    cs:__imp_BCryptFinishHash
0x1800157a1  mov     edi, eax
0x1800157a3  test    eax, eax
0x1800157a5  jz      loc_180015831
0x1800157ab  lea     r9, pbInput+24h; ""
0x1800157b2  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x1800157b9  movzx   eax, byte ptr [r9-1]
0x1800157be  mov     rdx, r9
0x1800157c1  dec     r9
0x1800157c4  cmp     al, 5Ch ; '\'
0x1800157c6  jz      short loc_1800157CF
0x1800157c8  cmp     r9, rcx
0x1800157cb  ja      short loc_1800157B9
0x1800157cd  cmp     al, 5Ch ; '\'
0x1800157cf  lea     rax, Class
0x1800157d6  cmovz   r9, rdx
0x1800157da  mov     qword ptr [rsp+88h+dwFlags], rax
0x1800157df  lea     rax, aBcryptfinishha; "BCryptFinishHash"
0x1800157e6  mov     qword ptr [rsp+88h+cbSecret], rax
0x1800157eb  mov     dword ptr [rsp+88h+pbSecret], 3E5h
0x1800157f3  mov     r8d, edi
0x1800157f6  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800157fd  xor     ecx, ecx
0x1800157ff  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180015804  mov     rcx, [rsp+88h+phHash]; hHash
0x180015809  test    rcx, rcx
0x18001580c  jnz     loc_180015B1E
0x180015812  mov     eax, edi
0x180015814  mov     rcx, [rsp+88h+var_20]
0x180015819  xor     rcx, rsp; StackCookie
0x18001581c  call    __security_check_cookie
0x180015821  mov     rbx, [rsp+88h+arg_10]
0x180015829  add     rsp, 70h
0x18001582d  pop     rdi
0x18001582e  pop     rsi
0x18001582f  pop     rbp
0x180015830  retn
0x180015831  mov     r10d, ebp
0x180015834  lea     r11, a0123456789abcd; "0123456789abcdef"
0x18001583b  nop     dword ptr [rax+rax+00h]
0x180015840  lea     r9d, [r10+r10]
0x180015844  mov     eax, r10d
0x180015847  lea     ecx, [r9+1]
0x18001584b  movzx   edx, [rsp+rax+88h+pbOutput]
0x180015850  mov     eax, edx
0x180015852  shr     rdx, 4
0x180015856  and     eax, 0Fh
0x180015859  movzx   eax, word ptr [r11+rax*2]
0x18001585e  mov     [rbx+r9*2], ax
0x180015863  movzx   eax, word ptr [r11+rdx*2]
0x180015868  mov     [rbx+rcx*2], ax
0x18001586c  lea     ecx, [r9+2]
0x180015870  lea     eax, [r10+1]
0x180015874  movzx   r8d, [rsp+rax+88h+pbOutput]
0x18001587a  mov     edx, r8d
0x18001587d  shr     r8, 4
0x180015881  and     edx, 0Fh
0x180015884  movzx   eax, word ptr [r11+rdx*2]
0x180015889  mov     [rbx+rcx*2], ax
0x18001588d  lea     ecx, [r9+3]
0x180015891  movzx   eax, word ptr [r11+r8*2]
0x180015896  mov     [rbx+rcx*2], ax
0x18001589a  lea     ecx, [r10+2]
0x18001589e  movzx   r8d, [rsp+rcx+88h+pbOutput]
0x1800158a4  add     ecx, ecx
0x1800158a6  mov     edx, r8d
0x1800158a9  shr     r8, 4
0x1800158ad  and     edx, 0Fh
0x1800158b0  movzx   eax, word ptr [r11+rdx*2]
0x1800158b5  mov     [rbx+rcx*2], ax
0x1800158b9  lea     ecx, [r9+5]
0x1800158bd  movzx   eax, word ptr [r11+r8*2]
0x1800158c2  mov     [rbx+rcx*2], ax
0x1800158c6  lea     ecx, [r10+3]
0x1800158ca  movzx   r8d, [rsp+rcx+88h+pbOutput]
0x1800158d0  add     ecx, ecx
0x1800158d2  mov     edx, r8d
0x1800158d5  shr     r8, 4
0x1800158d9  and     edx, 0Fh
0x1800158dc  movzx   eax, word ptr [r11+rdx*2]
0x1800158e1  mov     [rbx+rcx*2], ax
0x1800158e5  lea     ecx, [r9+7]
0x1800158e9  movzx   eax, word ptr [r11+r8*2]
0x1800158ee  mov     [rbx+rcx*2], ax
0x1800158f2  lea     ecx, [r10+4]
0x1800158f6  movzx   r8d, [rsp+rcx+88h+pbOutput]
0x1800158fc  add     ecx, ecx
0x1800158fe  mov     edx, r8d
0x180015901  shr     r8, 4
0x180015905  and     edx, 0Fh
0x180015908  movzx   eax, word ptr [r11+rdx*2]
0x18001590d  mov     [rbx+rcx*2], ax
0x180015911  lea     ecx, [r9+9]
0x180015915  movzx   eax, word ptr [r11+r8*2]
0x18001591a  mov     [rbx+rcx*2], ax
0x18001591e  lea     ecx, [r10+5]
0x180015922  movzx   r8d, [rsp+rcx+88h+pbOutput]
0x180015928  add     ecx, ecx
0x18001592a  mov     edx, r8d
0x18001592d  shr     r8, 4
0x180015931  and     edx, 0Fh
0x180015934  movzx   eax, word ptr [r11+rdx*2]
0x180015939  mov     [rbx+rcx*2], ax
0x18001593d  lea     ecx, [r9+0Bh]
0x180015941  movzx   eax, word ptr [r11+r8*2]
0x180015946  mov     [rbx+rcx*2], ax
0x18001594a  lea     ecx, [r10+6]
0x18001594e  movzx   r8d, [rsp+rcx+88h+pbOutput]
0x180015954  add     ecx, ecx
0x180015956  mov     edx, r8d
0x180015959  shr     r8, 4
0x18001595d  and     edx, 0Fh
0x180015960  movzx   eax, word ptr [r11+rdx*2]
0x180015965  mov     [rbx+rcx*2], ax
0x180015969  lea     ecx, [r9+0Dh]
0x18001596d  movzx   eax, word ptr [r11+r8*2]
0x180015972  mov     [rbx+rcx*2], ax
0x180015976  lea     ecx, [r10+7]
0x18001597a  movzx   r8d, [rsp+rcx+88h+pbOutput]
0x180015980  mov     edx, r8d
0x180015983  and     edx, 0Fh
0x180015986  movzx   eax, word ptr [r11+rdx*2]
0x18001598b  add     ecx, ecx
0x18001598d  shr     r8, 4
0x180015991  mov     [rbx+rcx*2], ax
0x180015995  lea     ecx, [r9+0Fh]
0x180015999  movzx   eax, word ptr [r11+r8*2]
0x18001599e  mov     [rbx+rcx*2], ax
0x1800159a2  lea     ecx, [r10+8]
0x1800159a6  movzx   r8d, [rsp+rcx+88h+pbOutput]
0x1800159ac  add     ecx, ecx
0x1800159ae  mov     edx, r8d
0x1800159b1  shr     r8, 4
0x1800159b5  and     edx, 0Fh
0x1800159b8  movzx   eax, word ptr [r11+rdx*2]
0x1800159bd  mov     [rbx+rcx*2], ax
0x1800159c1  lea     ecx, [r9+11h]
0x1800159c5  movzx   eax, word ptr [r11+r8*2]
0x1800159ca  mov     [rbx+rcx*2], ax
0x1800159ce  lea     ecx, [r10+9]
0x1800159d2  movzx   r8d, [rsp+rcx+88h+pbOutput]
0x1800159d8  add     ecx, ecx
0x1800159da  mov     edx, r8d
0x1800159dd  shr     r8, 4
0x1800159e1  and     edx, 0Fh
0x1800159e4  movzx   eax, word ptr [r11+rdx*2]
0x1800159e9  mov     [rbx+rcx*2], ax
0x1800159ed  lea     ecx, [r9+13h]
0x1800159f1  movzx   eax, word ptr [r11+r8*2]
0x1800159f6  mov     [rbx+rcx*2], ax
0x1800159fa  lea     ecx, [r10+0Ah]
0x1800159fe  movzx   r8d, [rsp+rcx+88h+pbOutput]
0x180015a04  add     ecx, ecx
0x180015a06  mov     edx, r8d
0x180015a09  shr     r8, 4
0x180015a0d  and     edx, 0Fh
0x180015a10  movzx   eax, word ptr [r11+rdx*2]
0x180015a15  mov     [rbx+rcx*2], ax
0x180015a19  lea     ecx, [r9+15h]
0x180015a1d  movzx   eax, word ptr [r11+r8*2]
0x180015a22  mov     [rbx+rcx*2], ax
0x180015a26  lea     ecx, [r10+0Bh]
0x180015a2a  movzx   r8d, [rsp+rcx+88h+pbOutput]
0x180015a30  add     ecx, ecx
0x180015a32  mov     edx, r8d
0x180015a35  shr     r8, 4
0x180015a39  and     edx, 0Fh
0x180015a3c  movzx   eax, word ptr [r11+rdx*2]
0x180015a41  mov     [rbx+rcx*2], ax
0x180015a45  lea     ecx, [r9+17h]
0x180015a49  movzx   eax, word ptr [r11+r8*2]
0x180015a4e  mov     [rbx+rcx*2], ax
0x180015a52  lea     ecx, [r10+0Ch]
0x180015a56  movzx   r8d, [rsp+rcx+88h+pbOutput]
0x180015a5c  add     ecx, ecx
0x180015a5e  mov     edx, r8d
0x180015a61  shr     r8, 4
0x180015a65  and     edx, 0Fh
0x180015a68  movzx   eax, word ptr [r11+rdx*2]
0x180015a6d  mov     [rbx+rcx*2], ax
0x180015a71  lea     ecx, [r9+19h]
0x180015a75  movzx   eax, word ptr [r11+r8*2]
0x180015a7a  mov     [rbx+rcx*2], ax
0x180015a7e  lea     ecx, [r10+0Dh]
0x180015a82  movzx   r8d, [rsp+rcx+88h+pbOutput]
0x180015a88  add     ecx, ecx
0x180015a8a  mov     edx, r8d
0x180015a8d  shr     r8, 4
0x180015a91  and     edx, 0Fh
0x180015a94  movzx   eax, word ptr [r11+rdx*2]
0x180015a99  mov     [rbx+rcx*2], ax
0x180015a9d  lea     ecx, [r9+1Bh]
0x180015aa1  movzx   eax, word ptr [r11+r8*2]
0x180015aa6  mov     [rbx+rcx*2], ax
0x180015aaa  lea     ecx, [r10+0Eh]
0x180015aae  movzx   r8d, [rsp+rcx+88h+pbOutput]
0x180015ab4  add     ecx, ecx
0x180015ab6  mov     edx, r8d
0x180015ab9  and     edx, 0Fh
0x180015abc  shr     r8, 4
0x180015ac0  movzx   eax, word ptr [r11+rdx*2]
0x180015ac5  mov     [rbx+rcx*2], ax
0x180015ac9  movzx   eax, word ptr [r11+r8*2]
0x180015ace  lea     ecx, [r9+1Dh]
0x180015ad2  mov     [rbx+rcx*2], ax
0x180015ad6  lea     ecx, [r10+0Fh]
0x180015ada  movzx   r8d, [rsp+rcx+88h+pbOutput]
0x180015ae0  add     r10d, 10h
0x180015ae4  add     ecx, ecx
0x180015ae6  mov     edx, r8d
0x180015ae9  and     edx, 0Fh
0x180015aec  shr     r8, 4
0x180015af0  movzx   eax, word ptr [r11+rdx*2]
0x180015af5  mov     [rbx+rcx*2], ax
0x180015af9  lea     ecx, [r9+1Fh]
0x180015afd  movzx   eax, word ptr [r11+r8*2]
0x180015b02  mov     [rbx+rcx*2], ax
0x180015b06  cmp     r10d, 20h ; ' '
0x180015b0a  jb      loc_180015840
0x180015b10  mov     [rbx+80h], bp
0x180015b17  mov     edi, ebp
0x180015b19  jmp     loc_180015804
0x180015b1e  call    cs:__imp_BCryptDestroyHash
0x180015b24  jmp     loc_180015812
0x180015b29  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180015b30  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180015b35  mov     r9, rax
0x180015b38  lea     rax, Class
0x180015b3f  mov     qword ptr [rsp+88h+dwFlags], rax
0x180015b44  lea     rax, aBcryptcreateha; "BCryptCreateHash"
0x180015b4b  mov     qword ptr [rsp+88h+cbSecret], rax
0x180015b50  mov     dword ptr [rsp+88h+pbSecret], 3D3h
0x180015b58  jmp     loc_1800157F3
0x180015b5d  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180015b64  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180015b69  mov     r9, rax
0x180015b6c  lea     rax, Class
0x180015b73  mov     qword ptr [rsp+88h+dwFlags], rax
0x180015b78  lea     rax, aBcrypthashdata; "BCryptHashData"
0x180015b7f  mov     qword ptr [rsp+88h+cbSecret], rax
0x180015b84  mov     dword ptr [rsp+88h+pbSecret], 3DCh
0x180015b8c  jmp     loc_1800157F3
```
