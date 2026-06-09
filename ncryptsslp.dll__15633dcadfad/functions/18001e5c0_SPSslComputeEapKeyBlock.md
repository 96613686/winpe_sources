# SPSslComputeEapKeyBlock

- ea: `0x18001e5c0`
- end: `0x18001e8b4`
- name: `SPSslComputeEapKeyBlock`
- size: `756`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800068e0`
- `0x180007960`
- `0x180008810`
- `0x18000b654`
- `0x18001e5c0`
- `0x180024ef0`
- `0x180025660`

## string_xrefs

- `0x18001e633`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18001e79a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslComputeEapKeyBlock(
        __int64 a1,
        __int64 a2,
        _OWORD *a3,
        int a4,
        _OWORD *a5,
        unsigned int a6,
        _DWORD *a7,
        int a8)
{
  __int64 v12; // r9
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // r14
  __int64 v16; // rsi
  int v17; // r8d
  char *v18; // r13
  int v19; // r12d
  _OWORD *v20; // rax
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  int v24; // eax
  __int64 v25; // r9
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  _BYTE *v37; // rax
  int v39; // [rsp+60h] [rbp-A0h]
  int v40; // [rsp+64h] [rbp-9Ch]
  _OWORD v41[12]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v42[4]; // [rsp+130h] [rbp+30h] BYREF

  memset(v41, 0, sizeof(v41));
  if ( !SslpValidateProvHandle(a1) )
  {
    v12 = 358;
LABEL_3:
    v13 = -2146893786;
    v14 = 2148073510LL;
LABEL_4:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v12);
    return v13;
  }
  v15 = SslpValidateMasterKeyHandle(a2);
  if ( !v15 )
  {
    v12 = 367;
    goto LABEL_3;
  }
  if ( (a8 & 0xFFFFFF00) != 0 )
  {
    v12 = 374;
LABEL_9:
    v13 = -2146893815;
    v14 = 2148073481LL;
    goto LABEL_4;
  }
  if ( (unsigned __int8)a8 >= 4u )
  {
    v12 = 383;
    goto LABEL_9;
  }
  v16 = 64;
  if ( a4 != 64 )
  {
    v12 = 390;
LABEL_14:
    v13 = -2146893785;
    v14 = 2148073511LL;
    goto LABEL_4;
  }
  if ( *(_DWORD *)(v15 + 8) < 0x301u )
  {
    v12 = 400;
    goto LABEL_14;
  }
  *a7 = 192;
  if ( !a5 )
    return 0;
  if ( a6 < 0xC0 )
    return (unsigned int)-2146893784;
  v17 = (int)(&rgEapPrfInfo)[3 * (unsigned __int8)a8 + 1];
  v18 = (&rgEapPrfInfo)[3 * (unsigned __int8)a8];
  v19 = (int)(&rgEapPrfInfo)[3 * (unsigned __int8)a8 + 2];
  v40 = v17;
  v39 = *((_DWORD *)&rgEapPrfInfo + 6 * (unsigned __int8)a8 + 3);
  if ( v19 )
  {
    v20 = v42;
    v21 = a3[3];
    v42[0] = a3[2];
    v22 = *a3;
    v42[1] = v21;
    v23 = a3[1];
    v42[2] = v22;
    v42[3] = v23;
  }
  else
  {
    v20 = a3;
  }
  v24 = Tls1Prf(
          *(_DWORD *)(v15 + 8),
          *(const WCHAR **)(*(_QWORD *)(v15 + 16) + 104LL),
          *(_QWORD *)(*(_QWORD *)(v15 + 16) + 136LL),
          (UCHAR *)(v15 + 28),
          0x30u,
          (__int64)v18,
          v17,
          (__int64)v20,
          64,
          (__int64)v41,
          0x80u);
  v13 = v24;
  if ( v24 < 0 )
  {
    v25 = 462;
LABEL_26:
    DebugTraceError((unsigned int)v24, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v25);
    goto LABEL_31;
  }
  if ( v39 )
  {
    v24 = Tls1Prf(
            *(_DWORD *)(v15 + 8),
            *(const WCHAR **)(*(_QWORD *)(v15 + 16) + 104LL),
            *(_QWORD *)(*(_QWORD *)(v15 + 16) + 136LL),
            0,
            0,
            (__int64)v18,
            v40,
            (__int64)a3,
            64,
            (__int64)&v41[8],
            0x40u);
    v13 = v24;
    if ( v24 < 0 )
    {
      v25 = 488;
      goto LABEL_26;
    }
  }
  v13 = 0;
  v26 = v41[1];
  *a5 = v41[0];
  v27 = v41[2];
  a5[1] = v26;
  v28 = v41[3];
  a5[2] = v27;
  v29 = v41[4];
  a5[3] = v28;
  v30 = v41[5];
  a5[4] = v29;
  v31 = v41[6];
  a5[5] = v30;
  v32 = v41[7];
  a5[6] = v31;
  v33 = v41[8];
  a5[7] = v32;
  v34 = v41[9];
  a5[8] = v33;
  v35 = v41[10];
  a5[9] = v34;
  v36 = v41[11];
  a5[10] = v35;
  a5[11] = v36;
LABEL_31:
  if ( v19 )
  {
    v37 = v42;
    do
    {
      *v37++ = 0;
      --v16;
    }
    while ( v16 );
  }
  return v13;
}

```

## disassembly

```asm
0x18001e5c0  push    rbp
0x18001e5c2  push    rbx
0x18001e5c3  push    rsi
0x18001e5c4  push    rdi
0x18001e5c5  push    r12
0x18001e5c7  push    r13
0x18001e5c9  push    r14
0x18001e5cb  push    r15
0x18001e5cd  lea     rbp, [rsp-88h]
0x18001e5d5  sub     rsp, 188h
0x18001e5dc  mov     rax, cs:__security_cookie
0x18001e5e3  xor     rax, rsp
0x18001e5e6  mov     [rbp+0C0h+var_50], rax
0x18001e5ea  mov     rdi, [rbp+0C0h+arg_20]
0x18001e5f1  mov     r15, r8
0x18001e5f4  mov     r13, [rbp+0C0h+arg_30]
0x18001e5fb  mov     rsi, rdx
0x18001e5fe  mov     rbx, rcx
0x18001e601  xor     edx, edx; Val
0x18001e603  mov     r8d, 0C0h; Size
0x18001e609  lea     rcx, [rsp+1C0h+var_150]; void *
0x18001e60e  mov     r12d, r9d
0x18001e611  call    memset
0x18001e616  mov     rcx, rbx
0x18001e619  call    SslpValidateProvHandle
0x18001e61e  test    rax, rax
0x18001e621  jnz     short loc_18001E64B
0x18001e623  mov     r9d, 166h
0x18001e629  mov     ebx, 80090026h
0x18001e62e  mov     ecx, 80090026h
0x18001e633  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001e63a  lea     rdx, aStatus; "Status"
0x18001e641  call    DebugTraceError
0x18001e646  jmp     loc_18001E892
0x18001e64b  mov     rcx, rsi
0x18001e64e  call    SslpValidateMasterKeyHandle
0x18001e653  mov     r14, rax
0x18001e656  test    rax, rax
0x18001e659  jnz     short loc_18001E663
0x18001e65b  mov     r9d, 16Fh
0x18001e661  jmp     short loc_18001E629
0x18001e663  test    [rbp+0C0h+arg_38], 0FFFFFF00h
0x18001e66d  jz      short loc_18001E681
0x18001e66f  mov     r9d, 176h
0x18001e675  mov     ebx, 80090009h
0x18001e67a  mov     ecx, 80090009h
0x18001e67f  jmp     short loc_18001E633
0x18001e681  movzx   eax, byte ptr [rbp+0C0h+arg_38]
0x18001e688  cmp     eax, 4
0x18001e68b  jb      short loc_18001E695
0x18001e68d  mov     r9d, 17Fh
0x18001e693  jmp     short loc_18001E675
0x18001e695  mov     esi, 40h ; '@'
0x18001e69a  cmp     r12d, esi
0x18001e69d  jz      short loc_18001E6B1
0x18001e69f  mov     r9d, 186h
0x18001e6a5  mov     ebx, 80090027h
0x18001e6aa  mov     ecx, 80090027h
0x18001e6af  jmp     short loc_18001E633
0x18001e6b1  cmp     dword ptr [r14+8], 301h
0x18001e6b9  jnb     short loc_18001E6C3
0x18001e6bb  mov     r9d, 190h
0x18001e6c1  jmp     short loc_18001E6A5
0x18001e6c3  mov     dword ptr [r13+0], 0C0h
0x18001e6cb  test    rdi, rdi
0x18001e6ce  jnz     short loc_18001E6D7
0x18001e6d0  xor     ebx, ebx
0x18001e6d2  jmp     loc_18001E892
0x18001e6d7  cmp     [rbp+0C0h+arg_28], 0C0h
0x18001e6e1  jnb     short loc_18001E6ED
0x18001e6e3  mov     ebx, 80090028h
0x18001e6e8  jmp     loc_18001E892
0x18001e6ed  lea     rcx, [rax+rax*2]
0x18001e6f1  lea     r12, rgEapPrfInfo
0x18001e6f8  mov     r8d, [r12+rcx*8+8]
0x18001e6fd  mov     eax, [r12+rcx*8+0Ch]
0x18001e702  mov     r13, [r12+rcx*8]
0x18001e706  mov     r12d, [r12+rcx*8+10h]
0x18001e70b  mov     [rsp+1C0h+var_15C], r8d
0x18001e710  mov     [rsp+1C0h+var_160], eax
0x18001e714  test    r12d, r12d
0x18001e717  jz      short loc_18001E742
0x18001e719  movups  xmm0, xmmword ptr [r15+20h]
0x18001e71e  lea     rax, [rbp+0C0h+var_90]
0x18001e722  movups  xmm1, xmmword ptr [r15+30h]
0x18001e727  movaps  [rbp+0C0h+var_90], xmm0
0x18001e72b  movups  xmm0, xmmword ptr [r15]
0x18001e72f  movaps  [rbp+0C0h+var_80], xmm1
0x18001e733  movups  xmm1, xmmword ptr [r15+10h]
0x18001e738  movaps  [rbp+0C0h+var_70], xmm0
0x18001e73c  movaps  [rbp+0C0h+var_60], xmm1
0x18001e740  jmp     short loc_18001E745
0x18001e742  mov     rax, r15
0x18001e745  mov     rdx, [r14+10h]
0x18001e749  lea     rcx, [rsp+1C0h+var_150]
0x18001e74e  mov     [rsp+1C0h+var_170], 80h
0x18001e756  lea     r9, [r14+1Ch]
0x18001e75a  mov     [rsp+1C0h+var_178], rcx
0x18001e75f  mov     ecx, [r14+8]
0x18001e763  mov     [rsp+1C0h+var_180], esi
0x18001e767  mov     [rsp+1C0h+var_188], rax
0x18001e76c  mov     [rsp+1C0h+var_190], r8d
0x18001e771  mov     r8, [rdx+88h]
0x18001e778  mov     rdx, [rdx+68h]
0x18001e77c  mov     [rsp+1C0h+var_198], r13
0x18001e781  mov     [rsp+1C0h+var_1A0], 30h ; '0'
0x18001e789  call    Tls1Prf
0x18001e78e  mov     ebx, eax
0x18001e790  test    eax, eax
0x18001e792  jns     short loc_18001E7B4
0x18001e794  mov     r9d, 1CEh
0x18001e79a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001e7a1  mov     ecx, eax
0x18001e7a3  lea     rdx, aStatus; "Status"
0x18001e7aa  call    DebugTraceError
0x18001e7af  jmp     loc_18001E87D
0x18001e7b4  cmp     [rsp+1C0h+var_160], 0
0x18001e7b9  jz      short loc_18001E80F
0x18001e7bb  mov     rdx, [r14+10h]
0x18001e7bf  lea     rax, [rbp+0C0h+var_D0]
0x18001e7c3  mov     ecx, [r14+8]
0x18001e7c7  xor     r9d, r9d
0x18001e7ca  mov     [rsp+1C0h+var_170], esi
0x18001e7ce  mov     [rsp+1C0h+var_178], rax
0x18001e7d3  mov     eax, [rsp+1C0h+var_15C]
0x18001e7d7  mov     r8, [rdx+88h]
0x18001e7de  mov     rdx, [rdx+68h]
0x18001e7e2  mov     [rsp+1C0h+var_180], esi
0x18001e7e6  mov     [rsp+1C0h+var_188], r15
0x18001e7eb  mov     [rsp+1C0h+var_190], eax
0x18001e7ef  mov     [rsp+1C0h+var_198], r13
0x18001e7f4  mov     [rsp+1C0h+var_1A0], 0
0x18001e7fc  call    Tls1Prf
0x18001e801  mov     ebx, eax
0x18001e803  test    eax, eax
0x18001e805  jns     short loc_18001E80F
0x18001e807  mov     r9d, 1E8h
0x18001e80d  jmp     short loc_18001E79A
0x18001e80f  movaps  xmm0, [rsp+1C0h+var_150]
0x18001e814  xor     ebx, ebx
0x18001e816  movaps  xmm1, [rbp+0C0h+var_140]
0x18001e81a  movups  xmmword ptr [rdi], xmm0
0x18001e81d  movaps  xmm0, [rbp+0C0h+var_130]
0x18001e821  movups  xmmword ptr [rdi+10h], xmm1
0x18001e825  movaps  xmm1, [rbp+0C0h+var_120]
0x18001e829  movups  xmmword ptr [rdi+20h], xmm0
0x18001e82d  movaps  xmm0, [rbp+0C0h+var_110]
0x18001e831  movups  xmmword ptr [rdi+30h], xmm1
0x18001e835  movaps  xmm1, [rbp+0C0h+var_100]
0x18001e839  movups  xmmword ptr [rdi+40h], xmm0
0x18001e83d  movaps  xmm0, [rbp+0C0h+var_F0]
0x18001e841  movups  xmmword ptr [rdi+50h], xmm1
0x18001e845  movaps  xmm1, [rbp+0C0h+var_E0]
0x18001e849  movups  xmmword ptr [rdi+60h], xmm0
0x18001e84d  movaps  xmm0, [rbp+0C0h+var_D0]
0x18001e851  movups  xmmword ptr [rdi+70h], xmm1
0x18001e855  movaps  xmm1, [rbp+0C0h+var_C0]
0x18001e859  movups  xmmword ptr [rdi+80h], xmm0
0x18001e860  movaps  xmm0, [rbp+0C0h+var_B0]
0x18001e864  movups  xmmword ptr [rdi+90h], xmm1
0x18001e86b  movaps  xmm1, [rbp+0C0h+var_A0]
0x18001e86f  movups  xmmword ptr [rdi+0A0h], xmm0
0x18001e876  movups  xmmword ptr [rdi+0B0h], xmm1
0x18001e87d  test    r12d, r12d
0x18001e880  jz      short loc_18001E892
0x18001e882  lea     rax, [rbp+0C0h+var_90]
0x18001e886  mov     byte ptr [rax], 0
0x18001e889  inc     rax
0x18001e88c  sub     rsi, 1
0x18001e890  jnz     short loc_18001E886
0x18001e892  mov     eax, ebx
0x18001e894  mov     rcx, [rbp+0C0h+var_50]
0x18001e898  xor     rcx, rsp; StackCookie
0x18001e89b  call    __security_check_cookie
0x18001e8a0  add     rsp, 188h
0x18001e8a7  pop     r15
0x18001e8a9  pop     r14
0x18001e8ab  pop     r13
0x18001e8ad  pop     r12
0x18001e8af  pop     rdi
0x18001e8b0  pop     rsi
0x18001e8b1  pop     rbx
0x18001e8b2  pop     rbp
0x18001e8b3  retn
```
