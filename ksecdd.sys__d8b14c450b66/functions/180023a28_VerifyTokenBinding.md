# _VerifyTokenBinding

- ea: `0x180023a28`
- end: `0x180023fdb`
- name: `_VerifyTokenBinding`
- size: `1459`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180023760`

## callees

- `0x1800029b0`
- `0x1800040e0`
- `0x180004840`
- `0x180007bd8`
- `0x180010068`
- `0x1800100b4`
- `0x18001011c`
- `0x180010138`
- `0x180010840`
- `0x180010980`
- `0x18001f008`
- `0x18001f058`
- `0x180023a28`
- `0x180023fe4`

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
0x180023a28  mov     [rsp-8+arg_10], rbx
0x180023a2d  push    rbp
0x180023a2e  push    rsi
0x180023a2f  push    rdi
0x180023a30  push    r12
0x180023a32  push    r13
0x180023a34  push    r14
0x180023a36  push    r15
0x180023a38  lea     rbp, [rsp-7]
0x180023a3d  sub     rsp, 0F0h
0x180023a44  mov     rax, cs:__security_cookie
0x180023a4b  xor     rax, rsp
0x180023a4e  mov     [rbp+37h+var_40], rax
0x180023a52  mov     rax, [rbp+37h+arg_20]
0x180023a56  mov     r12, rcx
0x180023a59  mov     [rbp+37h+var_78], rax
0x180023a5d  lea     rcx, aSha256; "SHA256"
0x180023a64  mov     rax, [rbp+37h+arg_30]
0x180023a68  xorps   xmm0, xmm0
0x180023a6b  mov     [rbp+37h+var_80], rax
0x180023a6f  mov     r13d, r9d
0x180023a72  mov     rax, [rbp+37h+arg_38]
0x180023a76  mov     r15, rdx
0x180023a79  mov     r10d, r8d
0x180023a7c  mov     [rbp+37h+var_90], rcx
0x180023a80  mov     [rbp+37h+var_70], rcx
0x180023a84  mov     byte ptr [rax], 0
0x180023a87  mov     ecx, [rdx]
0x180023a89  mov     [rsp+120h+var_B8], rax
0x180023a8e  mov     [rsp+120h+var_D0], r8d
0x180023a93  mov     [rbp+37h+var_A8], 0
0x180023a9b  lea     rax, [rcx+4]
0x180023a9f  mov     [rbp+37h+var_A0], 0
0x180023aa7  mov     [rsp+120h+phKey], 0
0x180023ab0  mov     [rbp+37h+var_68], 20h ; ' '
0x180023ab8  mov     [rbp+37h+var_98], r10
0x180023abc  mov     [rbp+37h+var_88], rcx
0x180023ac0  movups  xmmword ptr [rbp+37h+pbHash], xmm0
0x180023ac4  movups  [rbp+37h+var_50], xmm0
0x180023ac8  cmp     rax, r10
0x180023acb  ja      loc_180023F89
0x180023ad1  movzx   esi, byte ptr [rcx+r12]
0x180023ad6  lea     eax, [rcx+1]
0x180023ad9  mov     [rdx], eax
0x180023adb  movzx   ebx, byte ptr [rax+r12]
0x180023ae0  lea     eax, [rcx+2]
0x180023ae3  mov     [rdx], eax
0x180023ae5  movzx   edi, byte ptr [rax+r12+1]
0x180023aeb  movzx   eax, word ptr [rax+r12]
0x180023af0  shl     ax, 8
0x180023af4  or      di, ax
0x180023af7  mov     [rsp+120h+var_E0], sil
0x180023afc  lea     eax, [rcx+4]
0x180023aff  mov     [rdx], eax
0x180023b01  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b08  lea     rax, WPP_GLOBAL_Control
0x180023b0f  cmp     rcx, rax
0x180023b12  jz      short loc_180023B40
0x180023b14  mov     eax, [rcx+2Ch]
0x180023b17  test    al, 4
0x180023b19  jz      short loc_180023B40
0x180023b1b  mov     rcx, [rcx+18h]
0x180023b1f  mov     r9d, esi
0x180023b22  movzx   eax, di
0x180023b25  mov     edx, 0Ch
0x180023b2a  mov     [rsp+120h+cbInput], eax
0x180023b2e  mov     dword ptr [rsp+120h+pbInput], ebx
0x180023b32  call    WPP_SF_ddd
0x180023b37  mov     r8d, [rsp+120h+var_D0]
0x180023b3c  mov     r10, [rbp+37h+var_98]
0x180023b40  mov     ecx, esi
0x180023b42  call    TBValidateBindingType
0x180023b47  mov     r14d, eax
0x180023b4a  test    eax, eax
0x180023b4c  jnz     loc_180023F8F
0x180023b52  mov     ecx, ebx
0x180023b54  mov     r9d, ebx
0x180023b57  call    TBValidateKeyType
0x180023b5c  mov     r14d, eax
0x180023b5f  test    eax, eax
0x180023b61  jnz     loc_180023F8F
0x180023b67  mov     ecx, [r15]
0x180023b6a  movzx   edi, di
0x180023b6d  lea     eax, [rdi+rcx]
0x180023b70  cmp     eax, r8d
0x180023b73  ja      loc_180023F89
0x180023b79  test    sil, sil
0x180023b7c  jnz     short loc_180023B8E
0x180023b7e  cmp     ebx, r13d
0x180023b81  jz      short loc_180023B8E
0x180023b83  mov     r14d, 80090008h
0x180023b89  jmp     loc_180023F8F
0x180023b8e  test    bl, bl
0x180023b90  jnz     short loc_180023BA4
0x180023b92  mov     [rsp+120h+var_DC], 2
0x180023b9a  lea     r11, [rbp+37h+var_90]
0x180023b9e  mov     [rbp+37h+pPaddingInfo], r11
0x180023ba2  jmp     short loc_180023BC7
0x180023ba4  cmp     bl, 1
0x180023ba7  jnz     short loc_180023BB7
0x180023ba9  mov     [rsp+120h+var_DC], 8
0x180023bb1  lea     r11, [rbp+37h+var_70]
0x180023bb5  jmp     short loc_180023B9E
0x180023bb7  mov     [rbp+37h+pPaddingInfo], 0
0x180023bbf  mov     [rsp+120h+var_DC], 0
0x180023bc7  mov     edx, r9d
0x180023bca  test    bl, bl
0x180023bcc  jz      loc_180023CFB
0x180023bd2  sub     edx, 1
0x180023bd5  jz      loc_180023CFB
0x180023bdb  cmp     edx, 1
0x180023bde  jz      short loc_180023C20
0x180023be0  cmp     sil, 1
0x180023be4  jnz     short loc_180023B83
0x180023be6  mov     rcx, cs:WPP_GLOBAL_Control
0x180023bed  lea     rax, WPP_GLOBAL_Control
0x180023bf4  cmp     rcx, rax
0x180023bf7  jz      short loc_180023C0F
0x180023bf9  mov     eax, [rcx+2Ch]
0x180023bfc  test    sil, al
0x180023bff  jz      short loc_180023C0F
0x180023c01  mov     rcx, [rcx+18h]
0x180023c05  mov     edx, 0Fh
0x180023c0a  call    WPP_SF_d
0x180023c0f  mov     r8, [rsp+120h+var_B8]
0x180023c14  add     [r15], edi
0x180023c17  mov     byte ptr [r8], 1
0x180023c1b  jmp     loc_180023E67
0x180023c20  lea     rax, [rcx+1]
0x180023c24  cmp     rax, r10
0x180023c27  ja      loc_180023F89
0x180023c2d  movzx   r13d, byte ptr [r12+rcx]
0x180023c32  lea     eax, [rcx+1]
0x180023c35  mov     [rsp+120h+var_D8], eax
0x180023c39  mov     [r15], eax
0x180023c3c  test    r13b, r13b
0x180023c3f  jz      loc_180023F89
0x180023c45  lea     eax, [rcx+1]
0x180023c48  mov     esi, r13d
0x180023c4b  add     eax, r13d
0x180023c4e  cmp     eax, r8d
0x180023c51  ja      loc_180023F89
0x180023c57  mov     [r15], eax
0x180023c5a  lea     rcx, [rbp+37h+var_A0]
0x180023c5e  lea     eax, [r13+8]
0x180023c62  mov     edx, eax
0x180023c64  mov     [rsp+120h+var_D4], eax
0x180023c68  call    TBAllocateBuffer
0x180023c6d  test    eax, eax
0x180023c6f  jz      loc_180023D94
0x180023c75  mov     rdi, [rbp+37h+var_A0]
0x180023c79  mov     r8d, r13d; Size
0x180023c7c  mov     edx, [rsp+120h+var_D8]
0x180023c80  shr     esi, 1
0x180023c82  add     rdx, r12; Src
0x180023c85  mov     dword ptr [rdi], 31534345h
0x180023c8b  lea     rcx, [rdi+8]; void *
0x180023c8f  mov     [rdi+4], esi
0x180023c92  call    memmove
0x180023c97  mov     eax, [rsp+120h+var_D4]
0x180023c9b  lea     r9, [rsp+120h+phKey]; phKey
0x180023ca0  mov     [rsp+120h+dwFlags], 0; dwFlags
0x180023ca8  lea     r8, pszBlobType; "ECCPUBLICBLOB"
0x180023caf  mov     [rsp+120h+cbInput], eax; cbInput
0x180023cb3  xor     edx, edx; hImportKey
0x180023cb5  mov     ecx, 2E1h; hAlgorithm
0x180023cba  mov     [rsp+120h+pbInput], rdi; pbInput
0x180023cbf  call    BCryptImportKeyPair
0x180023cc4  mov     edi, eax
0x180023cc6  test    eax, eax
0x180023cc8  jns     loc_180023E62
0x180023cce  mov     rcx, cs:WPP_GLOBAL_Control
0x180023cd5  lea     rax, WPP_GLOBAL_Control
0x180023cdc  cmp     rcx, rax
0x180023cdf  jz      loc_180023E55
0x180023ce5  mov     edx, [rcx+2Ch]
0x180023ce8  test    dl, 1
0x180023ceb  jz      loc_180023E55
0x180023cf1  mov     edx, 0Eh
0x180023cf6  jmp     loc_180023E42
0x180023cfb  lea     rax, [rcx+2]
0x180023cff  cmp     rax, r10
0x180023d02  ja      loc_180023F89
0x180023d08  movzx   eax, word ptr [rcx+r12]
0x180023d0d  movzx   r13d, byte ptr [rcx+r12+1]
0x180023d13  shl     ax, 8
0x180023d17  or      r13w, ax
0x180023d1b  lea     eax, [rcx+2]
0x180023d1e  mov     [rsp+120h+var_D8], eax
0x180023d22  mov     [r15], eax
0x180023d25  jz      loc_180023F89
0x180023d2b  movzx   edx, r13w
0x180023d2f  add     edx, 2
0x180023d32  add     edx, ecx
0x180023d34  cmp     edx, r8d
0x180023d37  ja      loc_180023F89
0x180023d3d  lea     rax, [rdx+1]
0x180023d41  mov     [r15], edx
0x180023d44  cmp     rax, r10
0x180023d47  ja      loc_180023F89
0x180023d4d  movzx   edi, byte ptr [rdx+r12]
0x180023d52  lea     eax, [rdx+1]
0x180023d55  mov     [rsp+120h+var_D4], eax
0x180023d59  mov     [r15], eax
0x180023d5c  test    dil, dil
0x180023d5f  jz      loc_180023F89
0x180023d65  lea     ecx, [rdi+1]
0x180023d68  mov     eax, edi
0x180023d6a  add     ecx, edx
0x180023d6c  cmp     ecx, r8d
0x180023d6f  ja      loc_180023F89
0x180023d75  movzx   edx, r13w
0x180023d79  add     edx, 18h
0x180023d7c  mov     [r15], ecx
0x180023d7f  add     eax, edx
0x180023d81  lea     rcx, [rbp+37h+var_A8]
0x180023d85  mov     edx, eax
0x180023d87  mov     [rsp+120h+var_C0], eax
0x180023d8b  call    TBAllocateBuffer
0x180023d90  test    eax, eax
0x180023d92  jnz     short loc_180023D9F
0x180023d94  mov     r14d, 80090300h
0x180023d9a  jmp     loc_180023F8F
0x180023d9f  mov     rsi, [rbp+37h+var_A8]
0x180023da3  mov     r8, rdi; Size
0x180023da6  mov     edx, [rsp+120h+var_D4]
0x180023daa  movzx   ecx, r13w
0x180023dae  add     rdx, r12; Src
0x180023db1  mov     dword ptr [rsi], 31415352h
0x180023db7  mov     qword ptr [rsi+10h], 0
0x180023dbf  lea     eax, ds:0[rcx*8]
0x180023dc6  mov     [rsi+4], eax
0x180023dc9  mov     [rsi+0Ch], ecx
0x180023dcc  lea     rcx, [rsi+18h]; void *
0x180023dd0  mov     [rsi+8], edi
0x180023dd3  call    memmove
0x180023dd8  mov     edx, [rsp+120h+var_D8]
0x180023ddc  lea     rcx, [rsi+18h]
0x180023de0  add     rdx, r12; Src
0x180023de3  movzx   r8d, r13w; Size
0x180023de7  add     rcx, rdi; void *
0x180023dea  call    memmove
0x180023def  mov     eax, [rsp+120h+var_C0]
0x180023df3  lea     r9, [rsp+120h+phKey]; phKey
0x180023df8  mov     [rsp+120h+dwFlags], 0; dwFlags
0x180023e00  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x180023e07  mov     [rsp+120h+cbInput], eax; cbInput
0x180023e0b  xor     edx, edx; hImportKey
0x180023e0d  mov     ecx, 0E1h; hAlgorithm
0x180023e12  mov     [rsp+120h+pbInput], rsi; pbInput
0x180023e17  call    BCryptImportKeyPair
0x180023e1c  mov     edi, eax
0x180023e1e  test    eax, eax
0x180023e20  jns     short loc_180023E62
0x180023e22  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e29  lea     rax, WPP_GLOBAL_Control
0x180023e30  cmp     rcx, rax
0x180023e33  jz      short loc_180023E55
0x180023e35  mov     edx, [rcx+2Ch]
0x180023e38  test    dl, 1
0x180023e3b  jz      short loc_180023E55
0x180023e3d  mov     edx, 0Dh
0x180023e42  mov     rcx, [rcx+18h]
0x180023e46  lea     r8, WPP_0c97cf3ebcf83aea482108bb01090baf_Traceguids
0x180023e4d  mov     r9d, edi
0x180023e50  call    WPP_SF_D
0x180023e55  mov     r14d, edi
0x180023e58  bts     r14d, 1Ch
0x180023e5d  jmp     loc_180023F8F
0x180023e62  mov     r8, [rsp+120h+var_B8]
0x180023e67  mov     eax, [r15]
0x180023e6a  sub     eax, dword ptr [rbp+37h+var_88]
0x180023e6d  mov     rcx, [rbp+37h+var_80]
0x180023e71  dec     eax
0x180023e73  mov     [rcx], eax
0x180023e75  mov     ecx, [r15]
0x180023e78  lea     rax, [rcx+2]
0x180023e7c  cmp     rax, [rbp+37h+var_98]
0x180023e80  ja      loc_180023F89
0x180023e86  movzx   eax, word ptr [rcx+r12]
0x180023e8b  lea     r9d, [rcx+2]
0x180023e8f  movzx   edi, byte ptr [rcx+r12+1]
0x180023e95  shl     ax, 8
0x180023e99  or      di, ax
0x180023e9c  mov     [r15], r9d
0x180023e9f  jz      loc_180023F89
0x180023ea5  mov     r13d, [rsp+120h+var_D0]
0x180023eaa  movzx   edx, di
0x180023ead  add     edx, 2
0x180023eb0  add     edx, ecx
0x180023eb2  cmp     edx, r13d
0x180023eb5  ja      loc_180023F89
0x180023ebb  mov     esi, r9d
0x180023ebe  add     rsi, r12
0x180023ec1  mov     [r15], edx
0x180023ec4  cmp     byte ptr [r8], 0
0x180023ec8  jnz     short loc_180023F27
0x180023eca  mov     r9d, [rbp+37h+arg_28]
0x180023ece  lea     rax, [rbp+37h+pbHash]
0x180023ed2  mov     r8, [rbp+37h+var_78]
  ... truncated ...
```
