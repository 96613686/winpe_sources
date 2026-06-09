# _VerifyTokenBinding

- ea: `0x180023a78`
- end: `0x18002402b`
- name: `_VerifyTokenBinding`
- size: `1459`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1800237b0`

## callees

- `0x1800029b0`
- `0x1800040e0`
- `0x180004840`
- `0x180007bd8`
- `0x1800100c8`
- `0x180010114`
- `0x18001017c`
- `0x180010198`
- `0x1800108a0`
- `0x180010a00`
- `0x18001f008`
- `0x18001f058`
- `0x180023a78`
- `0x180024034`

## pseudocode

```c
__int64 __fastcall VerifyTokenBinding(
        __int64 a1,
        unsigned int *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        _DWORD *a7,
        _BYTE *a8)
{
  __int64 v11; // rcx
  unsigned int v12; // esi
  __int64 v13; // rax
  unsigned int v14; // ebx
  __int64 v15; // rax
  unsigned __int16 v16; // di
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned int v19; // r14d
  unsigned int v20; // r8d
  int v21; // r9d
  unsigned __int64 v22; // r10
  __int64 v23; // rcx
  const wchar_t **v24; // r11
  _BYTE *v25; // r8
  unsigned int v26; // r13d
  unsigned int v27; // eax
  PUCHAR pbInput; // rdi
  NTSTATUS v29; // edi
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  unsigned __int16 v32; // r13
  __int64 v33; // rdx
  size_t v34; // rdi
  unsigned int v35; // ecx
  PUCHAR v36; // rsi
  NTSTATUS v37; // r14d
  __int64 v38; // rcx
  unsigned __int16 v39; // di
  __int64 v40; // rdx
  UCHAR *v41; // rsi
  NTSTATUS v42; // eax
  __int64 v43; // rcx
  unsigned __int16 v44; // bx
  unsigned int v45; // edx
  char v47; // [rsp+40h] [rbp-A9h]
  ULONG dwFlags; // [rsp+44h] [rbp-A5h]
  unsigned int v49; // [rsp+48h] [rbp-A1h]
  unsigned int v50; // [rsp+48h] [rbp-A1h]
  ULONG v51; // [rsp+4Ch] [rbp-9Dh]
  unsigned int v52; // [rsp+50h] [rbp-99h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-91h] BYREF
  ULONG cbInput; // [rsp+60h] [rbp-89h]
  _BYTE *v55; // [rsp+68h] [rbp-81h]
  void *pPaddingInfo; // [rsp+70h] [rbp-79h]
  PUCHAR v57; // [rsp+78h] [rbp-71h] BYREF
  PUCHAR v58; // [rsp+80h] [rbp-69h] BYREF
  unsigned __int64 v59; // [rsp+88h] [rbp-61h]
  const wchar_t *v60; // [rsp+90h] [rbp-59h] BYREF
  __int64 v61; // [rsp+98h] [rbp-51h]
  _DWORD *v62; // [rsp+A0h] [rbp-49h]
  __int64 v63; // [rsp+A8h] [rbp-41h]
  _QWORD v64[2]; // [rsp+B0h] [rbp-39h] BYREF
  UCHAR pbHash[16]; // [rsp+C0h] [rbp-29h] BYREF
  __int128 v66; // [rsp+D0h] [rbp-19h]

  v63 = a5;
  v62 = a7;
  v60 = L"SHA256";
  v64[0] = L"SHA256";
  *a8 = 0;
  v11 = *a2;
  v55 = a8;
  v52 = a3;
  v57 = 0;
  v58 = 0;
  phKey = 0;
  v64[1] = 32;
  v59 = (unsigned int)a3;
  v61 = v11;
  *(_OWORD *)pbHash = 0;
  v66 = 0;
  if ( v11 + 4 > (unsigned __int64)(unsigned int)a3 )
    goto LABEL_63;
  v12 = *(unsigned __int8 *)(v11 + a1);
  v13 = (unsigned int)(v11 + 1);
  *a2 = v13;
  v14 = *(unsigned __int8 *)(v13 + a1);
  v15 = (unsigned int)(v11 + 2);
  *a2 = v15;
  v16 = (*(_WORD *)(v15 + a1) << 8) | *(unsigned __int8 *)(v15 + a1 + 1);
  v47 = v12;
  *a2 = v11 + 4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
  {
    WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 3), 12, a3, v12, v14, v16);
    a3 = v52;
  }
  v19 = TBValidateBindingType(v12, a2, a3);
  if ( !v19 )
  {
    v19 = TBValidateKeyType(v14, v17, v18, v14);
    if ( !v19 )
    {
      v23 = *a2;
      if ( v16 + (unsigned int)v23 > v20 )
        goto LABEL_63;
      if ( !(_BYTE)v12 && v14 != a4 )
        goto LABEL_10;
      if ( (_BYTE)v14 )
      {
        if ( (_BYTE)v14 != 1 )
        {
          pPaddingInfo = 0;
          dwFlags = 0;
          goto LABEL_17;
        }
        dwFlags = 8;
        v24 = (const wchar_t **)v64;
      }
      else
      {
        dwFlags = 2;
        v24 = &v60;
      }
      pPaddingInfo = v24;
LABEL_17:
      if ( !(_BYTE)v14 || v21 == 1 )
      {
        if ( v23 + 2 <= v22 )
        {
          v32 = (*(_WORD *)(v23 + a1) << 8) | *(unsigned __int8 *)(v23 + a1 + 1);
          v50 = v23 + 2;
          *a2 = v23 + 2;
          if ( v32 )
          {
            v33 = (unsigned int)v23 + v32 + 2;
            if ( (unsigned int)v33 <= v20 )
            {
              *a2 = v33;
              if ( v33 + 1 <= v22 )
              {
                v34 = *(unsigned __int8 *)(v33 + a1);
                v51 = v33 + 1;
                *a2 = v33 + 1;
                if ( (_BYTE)v34 )
                {
                  v35 = v33 + v34 + 1;
                  if ( v35 <= v20 )
                  {
                    *a2 = v35;
                    cbInput = v32 + 24 + v34;
                    if ( (unsigned int)TBAllocateBuffer(&v57, cbInput) )
                    {
                      v36 = v57;
                      *(_DWORD *)v57 = 826364754;
                      *((_QWORD *)v36 + 2) = 0;
                      *((_DWORD *)v36 + 1) = 8 * v32;
                      *((_DWORD *)v36 + 3) = v32;
                      *((_DWORD *)v36 + 2) = v34;
                      memmove(v36 + 24, (const void *)(a1 + v51), v34);
                      memmove(&v36[v34 + 24], (const void *)(a1 + v50), v32);
                      v29 = BCryptImportKeyPair((BCRYPT_ALG_HANDLE)0xE1, 0, L"RSAPUBLICBLOB", &phKey, v36, cbInput, 0);
                      if ( v29 < 0 )
                      {
                        v30 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
                        {
                          goto LABEL_46;
                        }
                        v31 = 13;
                        goto LABEL_45;
                      }
LABEL_48:
                      v25 = v55;
                      goto LABEL_49;
                    }
LABEL_40:
                    v19 = -2146893056;
                    goto LABEL_64;
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        if ( v21 != 2 )
        {
          if ( (_BYTE)v12 != 1 )
          {
LABEL_10:
            v19 = -2146893816;
            goto LABEL_64;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 15);
          v25 = v55;
          *a2 += v16;
          *v25 = 1;
LABEL_49:
          *v62 = *a2 - v61 - 1;
          v38 = *a2;
          if ( v38 + 2 <= v59 )
          {
            v39 = (*(_WORD *)(v38 + a1) << 8) | *(unsigned __int8 *)(v38 + a1 + 1);
            *a2 = v38 + 2;
            if ( v39 )
            {
              v40 = (unsigned int)v38 + v39 + 2;
              if ( (unsigned int)v40 <= v52 )
              {
                v41 = (UCHAR *)(a1 + (unsigned int)(v38 + 2));
                *a2 = v40;
                if ( !*v25 )
                {
                  LOBYTE(v40) = v14;
                  LOBYTE(v38) = v47;
                  v19 = TBPopulateTokenBindingHash(v38, v40, v63, a6, pbHash);
                  if ( v19 )
                    goto LABEL_64;
                  v42 = BCryptVerifySignature(phKey, pPaddingInfo, pbHash, 0x20u, v41, v39, dwFlags);
                  if ( v42 < 0 )
                  {
                    v37 = v42;
                    goto LABEL_47;
                  }
                }
                v43 = *a2;
                if ( v43 + 2 <= (unsigned __int64)v52 )
                {
                  v44 = (*(_WORD *)(v43 + a1) << 8) | *(unsigned __int8 *)(v43 + a1 + 1);
                  *a2 = v43 + 2;
                  if ( !v44 )
                    goto LABEL_64;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
                  {
                    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 19);
                  }
                  v45 = *a2 + v44;
                  if ( v45 <= v52 )
                  {
                    *a2 = v45;
                    goto LABEL_64;
                  }
                }
              }
            }
          }
          goto LABEL_63;
        }
        if ( v23 + 1 <= v22 )
        {
          v26 = *(unsigned __int8 *)(a1 + v23);
          v49 = v23 + 1;
          *a2 = v23 + 1;
          if ( (_BYTE)v26 )
          {
            v27 = v26 + v23 + 1;
            if ( v27 <= v20 )
            {
              *a2 = v27;
              if ( (unsigned int)TBAllocateBuffer(&v58, v26 + 8) )
              {
                pbInput = v58;
                *(_DWORD *)v58 = 827540293;
                *((_DWORD *)pbInput + 1) = v26 >> 1;
                memmove(pbInput + 8, (const void *)(a1 + v49), v26);
                v29 = BCryptImportKeyPair((BCRYPT_ALG_HANDLE)0x2E1, 0, L"ECCPUBLICBLOB", &phKey, pbInput, v26 + 8, 0);
                if ( v29 < 0 )
                {
                  v30 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
                  {
                    goto LABEL_46;
                  }
                  v31 = 14;
LABEL_45:
                  WPP_SF_D(v30[3], v31, WPP_0c97cf3ebcf83aea482108bb01090baf_Traceguids, (unsigned int)v29);
LABEL_46:
                  v37 = v29;
LABEL_47:
                  v19 = v37 | 0x10000000;
                  goto LABEL_64;
                }
                goto LABEL_48;
              }
              goto LABEL_40;
            }
          }
        }
      }
LABEL_63:
      v19 = -2146893819;
    }
  }
LABEL_64:
  TBFreeBuffer(&v57);
  TBFreeBuffer(&v58);
  if ( phKey )
    BCryptDestroyKey(phKey);
  return v19;
}

```

## disassembly

```asm
0x180023a78  mov     [rsp-8+arg_10], rbx
0x180023a7d  push    rbp
0x180023a7e  push    rsi
0x180023a7f  push    rdi
0x180023a80  push    r12
0x180023a82  push    r13
0x180023a84  push    r14
0x180023a86  push    r15
0x180023a88  lea     rbp, [rsp-7]
0x180023a8d  sub     rsp, 0F0h
0x180023a94  mov     rax, cs:__security_cookie
0x180023a9b  xor     rax, rsp
0x180023a9e  mov     [rbp+37h+var_40], rax
0x180023aa2  mov     rax, [rbp+37h+arg_20]
0x180023aa6  mov     r12, rcx
0x180023aa9  mov     [rbp+37h+var_78], rax
0x180023aad  lea     rcx, aSha256; "SHA256"
0x180023ab4  mov     rax, [rbp+37h+arg_30]
0x180023ab8  xorps   xmm0, xmm0
0x180023abb  mov     [rbp+37h+var_80], rax
0x180023abf  mov     r13d, r9d
0x180023ac2  mov     rax, [rbp+37h+arg_38]
0x180023ac6  mov     r15, rdx
0x180023ac9  mov     r10d, r8d
0x180023acc  mov     [rbp+37h+var_90], rcx
0x180023ad0  mov     [rbp+37h+var_70], rcx
0x180023ad4  mov     byte ptr [rax], 0
0x180023ad7  mov     ecx, [rdx]
0x180023ad9  mov     [rsp+120h+var_B8], rax
0x180023ade  mov     [rsp+120h+var_D0], r8d
0x180023ae3  mov     [rbp+37h+var_A8], 0
0x180023aeb  lea     rax, [rcx+4]
0x180023aef  mov     [rbp+37h+var_A0], 0
0x180023af7  mov     [rsp+120h+phKey], 0
0x180023b00  mov     [rbp+37h+var_68], 20h ; ' '
0x180023b08  mov     [rbp+37h+var_98], r10
0x180023b0c  mov     [rbp+37h+var_88], rcx
0x180023b10  movups  xmmword ptr [rbp+37h+pbHash], xmm0
0x180023b14  movups  [rbp+37h+var_50], xmm0
0x180023b18  cmp     rax, r10
0x180023b1b  ja      loc_180023FD9
0x180023b21  movzx   esi, byte ptr [rcx+r12]
0x180023b26  lea     eax, [rcx+1]
0x180023b29  mov     [rdx], eax
0x180023b2b  movzx   ebx, byte ptr [rax+r12]
0x180023b30  lea     eax, [rcx+2]
0x180023b33  mov     [rdx], eax
0x180023b35  movzx   edi, byte ptr [rax+r12+1]
0x180023b3b  movzx   eax, word ptr [rax+r12]
0x180023b40  shl     ax, 8
0x180023b44  or      di, ax
0x180023b47  mov     [rsp+120h+var_E0], sil
0x180023b4c  lea     eax, [rcx+4]
0x180023b4f  mov     [rdx], eax
0x180023b51  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b58  lea     rax, WPP_GLOBAL_Control
0x180023b5f  cmp     rcx, rax
0x180023b62  jz      short loc_180023B90
0x180023b64  mov     eax, [rcx+2Ch]
0x180023b67  test    al, 4
0x180023b69  jz      short loc_180023B90
0x180023b6b  mov     rcx, [rcx+18h]
0x180023b6f  mov     r9d, esi
0x180023b72  movzx   eax, di
0x180023b75  mov     edx, 0Ch
0x180023b7a  mov     [rsp+120h+cbInput], eax
0x180023b7e  mov     dword ptr [rsp+120h+pbInput], ebx
0x180023b82  call    WPP_SF_ddd
0x180023b87  mov     r8d, [rsp+120h+var_D0]
0x180023b8c  mov     r10, [rbp+37h+var_98]
0x180023b90  mov     ecx, esi
0x180023b92  call    TBValidateBindingType
0x180023b97  mov     r14d, eax
0x180023b9a  test    eax, eax
0x180023b9c  jnz     loc_180023FDF
0x180023ba2  mov     ecx, ebx
0x180023ba4  mov     r9d, ebx
0x180023ba7  call    TBValidateKeyType
0x180023bac  mov     r14d, eax
0x180023baf  test    eax, eax
0x180023bb1  jnz     loc_180023FDF
0x180023bb7  mov     ecx, [r15]
0x180023bba  movzx   edi, di
0x180023bbd  lea     eax, [rdi+rcx]
0x180023bc0  cmp     eax, r8d
0x180023bc3  ja      loc_180023FD9
0x180023bc9  test    sil, sil
0x180023bcc  jnz     short loc_180023BDE
0x180023bce  cmp     ebx, r13d
0x180023bd1  jz      short loc_180023BDE
0x180023bd3  mov     r14d, 80090008h
0x180023bd9  jmp     loc_180023FDF
0x180023bde  test    bl, bl
0x180023be0  jnz     short loc_180023BF4
0x180023be2  mov     [rsp+120h+var_DC], 2
0x180023bea  lea     r11, [rbp+37h+var_90]
0x180023bee  mov     [rbp+37h+pPaddingInfo], r11
0x180023bf2  jmp     short loc_180023C17
0x180023bf4  cmp     bl, 1
0x180023bf7  jnz     short loc_180023C07
0x180023bf9  mov     [rsp+120h+var_DC], 8
0x180023c01  lea     r11, [rbp+37h+var_70]
0x180023c05  jmp     short loc_180023BEE
0x180023c07  mov     [rbp+37h+pPaddingInfo], 0
0x180023c0f  mov     [rsp+120h+var_DC], 0
0x180023c17  mov     edx, r9d
0x180023c1a  test    bl, bl
0x180023c1c  jz      loc_180023D4B
0x180023c22  sub     edx, 1
0x180023c25  jz      loc_180023D4B
0x180023c2b  cmp     edx, 1
0x180023c2e  jz      short loc_180023C70
0x180023c30  cmp     sil, 1
0x180023c34  jnz     short loc_180023BD3
0x180023c36  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c3d  lea     rax, WPP_GLOBAL_Control
0x180023c44  cmp     rcx, rax
0x180023c47  jz      short loc_180023C5F
0x180023c49  mov     eax, [rcx+2Ch]
0x180023c4c  test    sil, al
0x180023c4f  jz      short loc_180023C5F
0x180023c51  mov     rcx, [rcx+18h]
0x180023c55  mov     edx, 0Fh
0x180023c5a  call    WPP_SF_d
0x180023c5f  mov     r8, [rsp+120h+var_B8]
0x180023c64  add     [r15], edi
0x180023c67  mov     byte ptr [r8], 1
0x180023c6b  jmp     loc_180023EB7
0x180023c70  lea     rax, [rcx+1]
0x180023c74  cmp     rax, r10
0x180023c77  ja      loc_180023FD9
0x180023c7d  movzx   r13d, byte ptr [r12+rcx]
0x180023c82  lea     eax, [rcx+1]
0x180023c85  mov     [rsp+120h+var_D8], eax
0x180023c89  mov     [r15], eax
0x180023c8c  test    r13b, r13b
0x180023c8f  jz      loc_180023FD9
0x180023c95  lea     eax, [rcx+1]
0x180023c98  mov     esi, r13d
0x180023c9b  add     eax, r13d
0x180023c9e  cmp     eax, r8d
0x180023ca1  ja      loc_180023FD9
0x180023ca7  mov     [r15], eax
0x180023caa  lea     rcx, [rbp+37h+var_A0]
0x180023cae  lea     eax, [r13+8]
0x180023cb2  mov     edx, eax
0x180023cb4  mov     [rsp+120h+var_D4], eax
0x180023cb8  call    TBAllocateBuffer
0x180023cbd  test    eax, eax
0x180023cbf  jz      loc_180023DE4
0x180023cc5  mov     rdi, [rbp+37h+var_A0]
0x180023cc9  mov     r8d, r13d; Size
0x180023ccc  mov     edx, [rsp+120h+var_D8]
0x180023cd0  shr     esi, 1
0x180023cd2  add     rdx, r12; Src
0x180023cd5  mov     dword ptr [rdi], 31534345h
0x180023cdb  lea     rcx, [rdi+8]; void *
0x180023cdf  mov     [rdi+4], esi
0x180023ce2  call    memmove
0x180023ce7  mov     eax, [rsp+120h+var_D4]
0x180023ceb  lea     r9, [rsp+120h+phKey]; phKey
0x180023cf0  mov     [rsp+120h+dwFlags], 0; dwFlags
0x180023cf8  lea     r8, pszBlobType; "ECCPUBLICBLOB"
0x180023cff  mov     [rsp+120h+cbInput], eax; cbInput
0x180023d03  xor     edx, edx; hImportKey
0x180023d05  mov     ecx, 2E1h; hAlgorithm
0x180023d0a  mov     [rsp+120h+pbInput], rdi; pbInput
0x180023d0f  call    BCryptImportKeyPair
0x180023d14  mov     edi, eax
0x180023d16  test    eax, eax
0x180023d18  jns     loc_180023EB2
0x180023d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d25  lea     rax, WPP_GLOBAL_Control
0x180023d2c  cmp     rcx, rax
0x180023d2f  jz      loc_180023EA5
0x180023d35  mov     edx, [rcx+2Ch]
0x180023d38  test    dl, 1
0x180023d3b  jz      loc_180023EA5
0x180023d41  mov     edx, 0Eh
0x180023d46  jmp     loc_180023E92
0x180023d4b  lea     rax, [rcx+2]
0x180023d4f  cmp     rax, r10
0x180023d52  ja      loc_180023FD9
0x180023d58  movzx   eax, word ptr [rcx+r12]
0x180023d5d  movzx   r13d, byte ptr [rcx+r12+1]
0x180023d63  shl     ax, 8
0x180023d67  or      r13w, ax
0x180023d6b  lea     eax, [rcx+2]
0x180023d6e  mov     [rsp+120h+var_D8], eax
0x180023d72  mov     [r15], eax
0x180023d75  jz      loc_180023FD9
0x180023d7b  movzx   edx, r13w
0x180023d7f  add     edx, 2
0x180023d82  add     edx, ecx
0x180023d84  cmp     edx, r8d
0x180023d87  ja      loc_180023FD9
0x180023d8d  lea     rax, [rdx+1]
0x180023d91  mov     [r15], edx
0x180023d94  cmp     rax, r10
0x180023d97  ja      loc_180023FD9
0x180023d9d  movzx   edi, byte ptr [rdx+r12]
0x180023da2  lea     eax, [rdx+1]
0x180023da5  mov     [rsp+120h+var_D4], eax
0x180023da9  mov     [r15], eax
0x180023dac  test    dil, dil
0x180023daf  jz      loc_180023FD9
0x180023db5  lea     ecx, [rdi+1]
0x180023db8  mov     eax, edi
0x180023dba  add     ecx, edx
0x180023dbc  cmp     ecx, r8d
0x180023dbf  ja      loc_180023FD9
0x180023dc5  movzx   edx, r13w
0x180023dc9  add     edx, 18h
0x180023dcc  mov     [r15], ecx
0x180023dcf  add     eax, edx
0x180023dd1  lea     rcx, [rbp+37h+var_A8]
0x180023dd5  mov     edx, eax
0x180023dd7  mov     [rsp+120h+var_C0], eax
0x180023ddb  call    TBAllocateBuffer
0x180023de0  test    eax, eax
0x180023de2  jnz     short loc_180023DEF
0x180023de4  mov     r14d, 80090300h
0x180023dea  jmp     loc_180023FDF
0x180023def  mov     rsi, [rbp+37h+var_A8]
0x180023df3  mov     r8, rdi; Size
0x180023df6  mov     edx, [rsp+120h+var_D4]
0x180023dfa  movzx   ecx, r13w
0x180023dfe  add     rdx, r12; Src
0x180023e01  mov     dword ptr [rsi], 31415352h
0x180023e07  mov     qword ptr [rsi+10h], 0
0x180023e0f  lea     eax, ds:0[rcx*8]
0x180023e16  mov     [rsi+4], eax
0x180023e19  mov     [rsi+0Ch], ecx
0x180023e1c  lea     rcx, [rsi+18h]; void *
0x180023e20  mov     [rsi+8], edi
0x180023e23  call    memmove
0x180023e28  mov     edx, [rsp+120h+var_D8]
0x180023e2c  lea     rcx, [rsi+18h]
0x180023e30  add     rdx, r12; Src
0x180023e33  movzx   r8d, r13w; Size
0x180023e37  add     rcx, rdi; void *
0x180023e3a  call    memmove
0x180023e3f  mov     eax, [rsp+120h+var_C0]
0x180023e43  lea     r9, [rsp+120h+phKey]; phKey
0x180023e48  mov     [rsp+120h+dwFlags], 0; dwFlags
0x180023e50  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x180023e57  mov     [rsp+120h+cbInput], eax; cbInput
0x180023e5b  xor     edx, edx; hImportKey
0x180023e5d  mov     ecx, 0E1h; hAlgorithm
0x180023e62  mov     [rsp+120h+pbInput], rsi; pbInput
0x180023e67  call    BCryptImportKeyPair
0x180023e6c  mov     edi, eax
0x180023e6e  test    eax, eax
0x180023e70  jns     short loc_180023EB2
0x180023e72  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e79  lea     rax, WPP_GLOBAL_Control
0x180023e80  cmp     rcx, rax
0x180023e83  jz      short loc_180023EA5
0x180023e85  mov     edx, [rcx+2Ch]
0x180023e88  test    dl, 1
0x180023e8b  jz      short loc_180023EA5
0x180023e8d  mov     edx, 0Dh
0x180023e92  mov     rcx, [rcx+18h]
0x180023e96  lea     r8, WPP_0c97cf3ebcf83aea482108bb01090baf_Traceguids
0x180023e9d  mov     r9d, edi
0x180023ea0  call    WPP_SF_D
0x180023ea5  mov     r14d, edi
0x180023ea8  bts     r14d, 1Ch
0x180023ead  jmp     loc_180023FDF
0x180023eb2  mov     r8, [rsp+120h+var_B8]
0x180023eb7  mov     eax, [r15]
0x180023eba  sub     eax, dword ptr [rbp+37h+var_88]
0x180023ebd  mov     rcx, [rbp+37h+var_80]
0x180023ec1  dec     eax
0x180023ec3  mov     [rcx], eax
0x180023ec5  mov     ecx, [r15]
0x180023ec8  lea     rax, [rcx+2]
0x180023ecc  cmp     rax, [rbp+37h+var_98]
0x180023ed0  ja      loc_180023FD9
0x180023ed6  movzx   eax, word ptr [rcx+r12]
0x180023edb  lea     r9d, [rcx+2]
0x180023edf  movzx   edi, byte ptr [rcx+r12+1]
0x180023ee5  shl     ax, 8
0x180023ee9  or      di, ax
0x180023eec  mov     [r15], r9d
0x180023eef  jz      loc_180023FD9
0x180023ef5  mov     r13d, [rsp+120h+var_D0]
0x180023efa  movzx   edx, di
0x180023efd  add     edx, 2
0x180023f00  add     edx, ecx
0x180023f02  cmp     edx, r13d
0x180023f05  ja      loc_180023FD9
0x180023f0b  mov     esi, r9d
0x180023f0e  add     rsi, r12
0x180023f11  mov     [r15], edx
0x180023f14  cmp     byte ptr [r8], 0
0x180023f18  jnz     short loc_180023F77
0x180023f1a  mov     r9d, [rbp+37h+arg_28]
0x180023f1e  lea     rax, [rbp+37h+pbHash]
0x180023f22  mov     r8, [rbp+37h+var_78]
  ... truncated ...
```
