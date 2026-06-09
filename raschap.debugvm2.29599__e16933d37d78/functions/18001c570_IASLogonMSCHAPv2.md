# IASLogonMSCHAPv2

- ea: `0x18001c570`
- end: `0x18001ca04`
- name: `IASLogonMSCHAPv2`
- size: `1172`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180014bd8`

## callees

- `0x180003bd0`
- `0x180006a20`
- `0x18000de00`
- `0x18000e090`
- `0x18000e0e0`
- `0x180013b20`
- `0x180014610`
- `0x18001be60`
- `0x18001c300`
- `0x18001c570`

## string_xrefs

- `0x18001c93f`: `On the client side, this is the receive key; on the server side, it is the send key.`

## pseudocode

```c
__int64 __fastcall IASLogonMSCHAPv2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        __int64 a5,
        unsigned int a6,
        _QWORD *a7,
        __int64 a8,
        __int64 a9,
        void *a10)
{
  _OWORD *v11; // rbx
  __int64 v14; // r8
  unsigned int v15; // eax
  __int64 v16; // rcx
  unsigned int v18; // eax
  unsigned int v19; // esi
  int v20; // eax
  _OWORD *v21; // rax
  __int64 v22; // rcx
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h]
  _QWORD v32[3]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v33[514]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v34[46]; // [rsp+272h] [rbp+172h] BYREF
  __int128 v35; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v36; // [rsp+2B0h] [rbp+1B0h]
  __int64 v37; // [rsp+2B8h] [rbp+1B8h] BYREF
  _BYTE v38[24]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v11 = (_OWORD *)a9;
  v31 = a1;
  phHash[1] = a10;
  phHash[0] = 0;
  memset_0(v33, 0, 0x228u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids);
  CngRsa32Compat_SHAInit(phHash);
  CngRsa32Compat_SHAUpdate(phHash, a8, 16);
  CngRsa32Compat_SHAUpdate(phHash, a5, a6);
  v14 = -1;
  do
    ++v14;
  while ( *(_BYTE *)(a3 + v14) );
  CngRsa32Compat_SHAUpdate(phHash, a3, v14);
  CngRsa32Compat_SHAFinal(phHash, &v35);
  v37 = v35;
  if ( a4 )
  {
    v15 = IASComputeResponse(a2, a4, (__int64)&v37, (__int64)v32, (__int64)v33);
    if ( v15 )
      goto LABEL_11;
    v16 = *a7 - v32[0];
    if ( *a7 == v32[0] )
    {
      v16 = a7[1] - v32[1];
      if ( !v16 )
        v16 = a7[2] - v32[2];
    }
    if ( v16 )
    {
LABEL_11:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids, v15);
      return 1326;
    }
LABEL_18:
    CngRsa32Compat_SHAInit(phHash);
    CngRsa32Compat_SHAUpdate(phHash, v34, 16);
    CngRsa32Compat_SHAUpdate(phHash, a7, 24);
    CngRsa32Compat_SHAUpdate(phHash, AuthMagic1, 39);
    CngRsa32Compat_SHAFinal(phHash, &v35);
    CngRsa32Compat_SHAInit(phHash);
    CngRsa32Compat_SHAUpdate(phHash, &v35, 20);
    CngRsa32Compat_SHAUpdate(phHash, &v37, 8);
    CngRsa32Compat_SHAUpdate(phHash, AuthMagic2, 41);
    CngRsa32Compat_SHAFinal(phHash, &v35);
    v20 = v36;
    *(_OWORD *)(a9 + 514) = v35;
    *(_DWORD *)(a9 + 530) = v20;
    CngRsa32Compat_SHAInit(phHash);
    CngRsa32Compat_SHAUpdate(phHash, v34, 16);
    CngRsa32Compat_SHAUpdate(phHash, a7, 24);
    CngRsa32Compat_SHAUpdate(phHash, KeyMagic1, 27);
    CngRsa32Compat_SHAFinal(phHash, v38);
    CngRsa32Compat_SHAInit(phHash);
    CngRsa32Compat_SHAUpdate(phHash, v38, 16);
    CngRsa32Compat_SHAUpdate(phHash, &SHSpad1, 40);
    CngRsa32Compat_SHAUpdate(phHash, &KeyMagic2, 84);
    CngRsa32Compat_SHAUpdate(phHash, &SHSpad2, 40);
    CngRsa32Compat_SHAFinal(phHash, &v35);
    *(_OWORD *)(a9 + 534) = v35;
    CngRsa32Compat_SHAInit(phHash);
    CngRsa32Compat_SHAUpdate(phHash, v38, 16);
    CngRsa32Compat_SHAUpdate(phHash, &SHSpad1, 40);
    CngRsa32Compat_SHAUpdate(phHash, KeyMagic3, 84);
    CngRsa32Compat_SHAUpdate(phHash, &SHSpad2, 40);
    CngRsa32Compat_SHAFinal(phHash, &v35);
    v21 = v33;
    v22 = 4;
    *(_OWORD *)(a9 + 550) = v35;
    do
    {
      v23 = v21[1];
      *v11 = *v21;
      v24 = v21[2];
      v11[1] = v23;
      v25 = v21[3];
      v11[2] = v24;
      v26 = v21[4];
      v11[3] = v25;
      v27 = v21[5];
      v11[4] = v26;
      v28 = v21[6];
      v11[5] = v27;
      v29 = v21[7];
      v21 += 8;
      v11[6] = v28;
      v11[7] = v29;
      v11 += 8;
      --v22;
    }
    while ( v22 );
    *(_WORD *)v11 = *(_WORD *)v21;
    return 0;
  }
  v18 = IASLogonMSCHAP(v31, a2, &v37, a7);
  v19 = v18;
  if ( !v18 )
    goto LABEL_18;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids, v18);
  return v19;
}

```

## disassembly

```asm
0x18001c570  push    rbp
0x18001c572  push    rbx
0x18001c573  push    rsi
0x18001c574  push    rdi
0x18001c575  push    r12
0x18001c577  push    r13
0x18001c579  push    r14
0x18001c57b  push    r15
0x18001c57d  lea     rbp, [rsp-1E8h]
0x18001c585  sub     rsp, 2E8h
0x18001c58c  mov     rax, cs:__security_cookie
0x18001c593  xor     rax, rsp
0x18001c596  mov     [rbp+220h+var_48], rax
0x18001c59d  mov     rax, [rbp+220h+arg_48]
0x18001c5a4  mov     rsi, r8
0x18001c5a7  mov     rbx, [rbp+220h+arg_40]
0x18001c5ae  mov     r14, rdx
0x18001c5b1  mov     r12, [rbp+220h+arg_20]
0x18001c5b8  xor     edx, edx; Val
0x18001c5ba  mov     rdi, [rbp+220h+arg_30]
0x18001c5c1  mov     r8d, 228h; Size
0x18001c5c7  mov     r13, [rbp+220h+arg_38]
0x18001c5ce  mov     r15, r9
0x18001c5d1  mov     [rsp+320h+var_2D0], rcx
0x18001c5d6  lea     rcx, [rsp+320h+var_2B0]; void *
0x18001c5db  mov     [rsp+320h+var_2D8], rax
0x18001c5e0  mov     [rsp+320h+phHash], 0
0x18001c5e9  call    memset_0
0x18001c5ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5f5  lea     rax, WPP_GLOBAL_Control
0x18001c5fc  cmp     rcx, rax
0x18001c5ff  jz      short loc_18001C616
0x18001c601  mov     rcx, [rcx+10h]
0x18001c605  lea     r8, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids
0x18001c60c  mov     edx, 20h ; ' '
0x18001c611  call    WPP_SF_
0x18001c616  lea     rcx, [rsp+320h+phHash]; phHash
0x18001c61b  call    CngRsa32Compat_SHAInit
0x18001c620  mov     r8d, 10h
0x18001c626  lea     rcx, [rsp+320h+phHash]
0x18001c62b  mov     rdx, r13
0x18001c62e  call    CngRsa32Compat_SHAUpdate
0x18001c633  mov     r8d, [rbp+220h+arg_28]
0x18001c63a  lea     rcx, [rsp+320h+phHash]
0x18001c63f  mov     rdx, r12
0x18001c642  call    CngRsa32Compat_SHAUpdate
0x18001c647  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c64b  inc     r8
0x18001c64e  cmp     byte ptr [rsi+r8], 0
0x18001c653  jnz     short loc_18001C64B
0x18001c655  mov     rdx, rsi
0x18001c658  lea     rcx, [rsp+320h+phHash]
0x18001c65d  call    CngRsa32Compat_SHAUpdate
0x18001c662  lea     rdx, [rbp+220h+var_80]
0x18001c669  lea     rcx, [rsp+320h+phHash]
0x18001c66e  call    CngRsa32Compat_SHAFinal
0x18001c673  mov     rax, qword ptr [rbp+220h+var_80]
0x18001c67a  lea     r8, [rbp+220h+var_68]
0x18001c681  mov     [rbp+220h+var_68], rax
0x18001c688  test    r15, r15
0x18001c68b  jz      short loc_18001C707
0x18001c68d  lea     rax, [rsp+320h+var_2B0]
0x18001c692  mov     rdx, r15
0x18001c695  lea     r9, [rsp+320h+var_2C8]
0x18001c69a  mov     [rsp+320h+var_300], rax
0x18001c69f  mov     rcx, r14
0x18001c6a2  call    IASComputeResponse
0x18001c6a7  test    eax, eax
0x18001c6a9  jnz     short loc_18001C6D2
0x18001c6ab  mov     rcx, [rdi]
0x18001c6ae  sub     rcx, [rsp+320h+var_2C8]
0x18001c6b3  jnz     short loc_18001C6C9
0x18001c6b5  mov     rcx, [rdi+8]
0x18001c6b9  sub     rcx, [rsp+320h+var_2C0]
0x18001c6be  jnz     short loc_18001C6C9
0x18001c6c0  mov     rcx, [rdi+10h]
0x18001c6c4  sub     rcx, [rsp+320h+var_2B8]
0x18001c6c9  test    rcx, rcx
0x18001c6cc  jz      loc_18001C763
0x18001c6d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c6d9  lea     rdx, WPP_GLOBAL_Control
0x18001c6e0  cmp     rcx, rdx
0x18001c6e3  jz      short loc_18001C6FD
0x18001c6e5  mov     rcx, [rcx+10h]
0x18001c6e9  lea     r8, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids
0x18001c6f0  mov     edx, 21h ; '!'
0x18001c6f5  mov     r9d, eax
0x18001c6f8  call    WPP_SF_d
0x18001c6fd  mov     eax, 52Eh
0x18001c702  jmp     loc_18001C9E1
0x18001c707  mov     rax, [rsp+320h+var_2D8]
0x18001c70c  mov     r9, rdi
0x18001c70f  mov     rcx, [rsp+320h+var_2D0]
0x18001c714  mov     rdx, r14
0x18001c717  mov     [rsp+320h+var_2F0], rax
0x18001c71c  lea     rax, [rsp+320h+var_2B0]
0x18001c721  mov     [rsp+320h+var_2F8], rax
0x18001c726  call    IASLogonMSCHAP
0x18001c72b  mov     esi, eax
0x18001c72d  test    eax, eax
0x18001c72f  jz      short loc_18001C763
0x18001c731  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c738  lea     rdx, WPP_GLOBAL_Control
0x18001c73f  cmp     rcx, rdx
0x18001c742  jz      short loc_18001C75C
0x18001c744  mov     rcx, [rcx+10h]
0x18001c748  lea     r8, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids
0x18001c74f  mov     edx, 22h ; '"'
0x18001c754  mov     r9d, eax
0x18001c757  call    WPP_SF_d
0x18001c75c  mov     eax, esi
0x18001c75e  jmp     loc_18001C9E1
0x18001c763  lea     rcx, [rsp+320h+phHash]; phHash
0x18001c768  call    CngRsa32Compat_SHAInit
0x18001c76d  mov     r14d, 10h
0x18001c773  lea     rdx, [rbp+220h+var_AE]
0x18001c77a  mov     r8d, r14d
0x18001c77d  lea     rcx, [rsp+320h+phHash]
0x18001c782  call    CngRsa32Compat_SHAUpdate
0x18001c787  lea     esi, [r14+8]
0x18001c78b  mov     rdx, rdi
0x18001c78e  mov     r8d, esi
0x18001c791  lea     rcx, [rsp+320h+phHash]
0x18001c796  call    CngRsa32Compat_SHAUpdate
0x18001c79b  lea     r8d, [r14+17h]
0x18001c79f  lea     rdx, AuthMagic1; "Magic server to client signing constant"
0x18001c7a6  lea     rcx, [rsp+320h+phHash]
0x18001c7ab  call    CngRsa32Compat_SHAUpdate
0x18001c7b0  lea     rdx, [rbp+220h+var_80]
0x18001c7b7  lea     rcx, [rsp+320h+phHash]
0x18001c7bc  call    CngRsa32Compat_SHAFinal
0x18001c7c1  lea     rcx, [rsp+320h+phHash]; phHash
0x18001c7c6  call    CngRsa32Compat_SHAInit
0x18001c7cb  lea     r8d, [r14+4]
0x18001c7cf  lea     rdx, [rbp+220h+var_80]
0x18001c7d6  lea     rcx, [rsp+320h+phHash]
0x18001c7db  call    CngRsa32Compat_SHAUpdate
0x18001c7e0  lea     r8d, [r14-8]
0x18001c7e4  lea     rdx, [rbp+220h+var_68]
0x18001c7eb  lea     rcx, [rsp+320h+phHash]
0x18001c7f0  call    CngRsa32Compat_SHAUpdate
0x18001c7f5  lea     r8d, [r14+19h]
0x18001c7f9  lea     rdx, AuthMagic2; "Pad to make it do more than one iterati"...
0x18001c800  lea     rcx, [rsp+320h+phHash]
0x18001c805  call    CngRsa32Compat_SHAUpdate
0x18001c80a  lea     rdx, [rbp+220h+var_80]
0x18001c811  lea     rcx, [rsp+320h+phHash]
0x18001c816  call    CngRsa32Compat_SHAFinal
0x18001c81b  movups  xmm0, [rbp+220h+var_80]
0x18001c822  mov     eax, [rbp+220h+var_70]
0x18001c828  lea     rcx, [rsp+320h+phHash]; phHash
0x18001c82d  movups  xmmword ptr [rbx+202h], xmm0
0x18001c834  mov     [rbx+212h], eax
0x18001c83a  call    CngRsa32Compat_SHAInit
0x18001c83f  mov     r8d, r14d
0x18001c842  lea     rdx, [rbp+220h+var_AE]
0x18001c849  lea     rcx, [rsp+320h+phHash]
0x18001c84e  call    CngRsa32Compat_SHAUpdate
0x18001c853  mov     r8d, esi
0x18001c856  lea     rcx, [rsp+320h+phHash]
0x18001c85b  mov     rdx, rdi
0x18001c85e  call    CngRsa32Compat_SHAUpdate
0x18001c863  lea     r8d, [r14+0Bh]
0x18001c867  lea     rdx, KeyMagic1; "This is the MPPE Master Key"
0x18001c86e  lea     rcx, [rsp+320h+phHash]
0x18001c873  call    CngRsa32Compat_SHAUpdate
0x18001c878  lea     rdx, [rbp+220h+var_60]
0x18001c87f  lea     rcx, [rsp+320h+phHash]
0x18001c884  call    CngRsa32Compat_SHAFinal
0x18001c889  lea     rcx, [rsp+320h+phHash]; phHash
0x18001c88e  call    CngRsa32Compat_SHAInit
0x18001c893  mov     r8d, r14d
0x18001c896  lea     rdx, [rbp+220h+var_60]
0x18001c89d  lea     rcx, [rsp+320h+phHash]
0x18001c8a2  call    CngRsa32Compat_SHAUpdate
0x18001c8a7  lea     esi, [r14+18h]
0x18001c8ab  mov     r8d, esi
0x18001c8ae  lea     rdx, SHSpad1
0x18001c8b5  lea     rcx, [rsp+320h+phHash]
0x18001c8ba  call    CngRsa32Compat_SHAUpdate
0x18001c8bf  lea     edi, [rsi+2Ch]
0x18001c8c2  mov     r8d, edi
0x18001c8c5  lea     rdx, KeyMagic2
0x18001c8cc  lea     rcx, [rsp+320h+phHash]
0x18001c8d1  call    CngRsa32Compat_SHAUpdate
0x18001c8d6  mov     r8d, esi
0x18001c8d9  lea     rdx, SHSpad2
0x18001c8e0  lea     rcx, [rsp+320h+phHash]
0x18001c8e5  call    CngRsa32Compat_SHAUpdate
0x18001c8ea  lea     rdx, [rbp+220h+var_80]
0x18001c8f1  lea     rcx, [rsp+320h+phHash]
0x18001c8f6  call    CngRsa32Compat_SHAFinal
0x18001c8fb  movups  xmm0, [rbp+220h+var_80]
0x18001c902  lea     rcx, [rsp+320h+phHash]; phHash
0x18001c907  movdqu  xmmword ptr [rbx+216h], xmm0
0x18001c90f  call    CngRsa32Compat_SHAInit
0x18001c914  mov     r8d, r14d
0x18001c917  lea     rdx, [rbp+220h+var_60]
0x18001c91e  lea     rcx, [rsp+320h+phHash]
0x18001c923  call    CngRsa32Compat_SHAUpdate
0x18001c928  mov     r8d, esi
0x18001c92b  lea     rdx, SHSpad1
0x18001c932  lea     rcx, [rsp+320h+phHash]
0x18001c937  call    CngRsa32Compat_SHAUpdate
0x18001c93c  mov     r8d, edi
0x18001c93f  lea     rdx, KeyMagic3; "On the client side, this is the receive"...
0x18001c946  lea     rcx, [rsp+320h+phHash]
0x18001c94b  call    CngRsa32Compat_SHAUpdate
0x18001c950  mov     r8d, esi
0x18001c953  lea     rdx, SHSpad2
0x18001c95a  lea     rcx, [rsp+320h+phHash]
0x18001c95f  call    CngRsa32Compat_SHAUpdate
0x18001c964  lea     rdx, [rbp+220h+var_80]
0x18001c96b  lea     rcx, [rsp+320h+phHash]
0x18001c970  call    CngRsa32Compat_SHAFinal
0x18001c975  movups  xmm0, [rbp+220h+var_80]
0x18001c97c  lea     rax, [rsp+320h+var_2B0]
0x18001c981  lea     ecx, [rsi-24h]
0x18001c984  movdqu  xmmword ptr [rbx+226h], xmm0
0x18001c98c  lea     edx, [rsi+58h]
0x18001c98f  movups  xmm0, xmmword ptr [rax]
0x18001c992  movups  xmm1, xmmword ptr [rax+10h]
0x18001c996  movups  xmmword ptr [rbx], xmm0
0x18001c999  movups  xmm0, xmmword ptr [rax+20h]
0x18001c99d  movups  xmmword ptr [rbx+10h], xmm1
0x18001c9a1  movups  xmm1, xmmword ptr [rax+30h]
0x18001c9a5  movups  xmmword ptr [rbx+20h], xmm0
0x18001c9a9  movups  xmm0, xmmword ptr [rax+40h]
0x18001c9ad  movups  xmmword ptr [rbx+30h], xmm1
0x18001c9b1  movups  xmm1, xmmword ptr [rax+50h]
0x18001c9b5  movups  xmmword ptr [rbx+40h], xmm0
0x18001c9b9  movups  xmm0, xmmword ptr [rax+60h]
0x18001c9bd  movups  xmmword ptr [rbx+50h], xmm1
0x18001c9c1  movups  xmm1, xmmword ptr [rax+70h]
0x18001c9c5  add     rax, rdx
0x18001c9c8  movups  xmmword ptr [rbx+60h], xmm0
0x18001c9cc  movups  xmmword ptr [rbx+70h], xmm1
0x18001c9d0  add     rbx, rdx
0x18001c9d3  sub     rcx, 1
0x18001c9d7  jnz     short loc_18001C98F
0x18001c9d9  movzx   eax, word ptr [rax]
0x18001c9dc  mov     [rbx], ax
0x18001c9df  xor     eax, eax
0x18001c9e1  mov     rcx, [rbp+220h+var_48]
0x18001c9e8  xor     rcx, rsp; StackCookie
0x18001c9eb  call    __security_check_cookie
0x18001c9f0  add     rsp, 2E8h
0x18001c9f7  pop     r15
0x18001c9f9  pop     r14
0x18001c9fb  pop     r13
0x18001c9fd  pop     r12
0x18001c9ff  pop     rdi
0x18001ca00  pop     rsi
0x18001ca01  pop     rbx
0x18001ca02  pop     rbp
0x18001ca03  retn
```
