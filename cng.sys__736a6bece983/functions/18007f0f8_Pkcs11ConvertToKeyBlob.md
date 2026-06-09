# Pkcs11ConvertToKeyBlob

- ea: `0x18007f0f8`
- end: `0x18007f696`
- name: `Pkcs11ConvertToKeyBlob`
- size: `1438`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180014da0`
- `0x18004235c`
- `0x1800779e8`

## callees

- `0x180003f70`
- `0x180006410`
- `0x180006470`
- `0x18000743c`
- `0x180016e80`
- `0x18004036c`
- `0x1800407f8`
- `0x180041c20`
- `0x180042ac0`
- `0x180078380`
- `0x18007f0f8`
- `0x18007f69c`
- `0x18007f9e0`
- `0x180080288`
- `0x18009f650`
- `0x18009f780`
- `0x18009fa80`

## string_xrefs

- `0x18007f1b4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18007f33a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18007f374`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18007f3d9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18007f42f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18007f4a1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18007f5fc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`

## pseudocode

```c
__int64 __fastcall Pkcs11ConvertToKeyBlob(__int64 a1, __int64 a2, _DWORD *a3, _DWORD *a4, _DWORD *a5, unsigned int a6)
{
  int v7; // r15d
  __int64 v10; // r13
  __int64 v11; // r12
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  int RsaProperty; // eax
  unsigned int v16; // ecx
  unsigned int v17; // edx
  int v18; // ecx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // ebx
  _BYTE *Src; // rsi
  int v24; // eax
  int v25; // eax
  __int64 v26; // r14
  int SymmetricKey; // eax
  __int64 v28; // r9
  __int64 v29; // rcx
  unsigned int v30; // edi
  unsigned int v31; // edi
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rax
  void *v37; // r14
  __int64 v38; // r9
  __int64 v39; // rcx
  int v40; // eax
  __int64 v41; // rdi
  __int64 v42; // r9
  __int64 v43; // rcx
  int v44; // ecx
  bool v45; // zf
  int v46; // ecx
  _DWORD *v47; // rax
  int v48; // r15d
  size_t v49; // r8
  __int64 v50; // rcx
  _BYTE *v51; // rax
  int *v52; // rax
  __int64 v53; // rax
  _BYTE *v54; // rcx
  size_t v56; // [rsp+28h] [rbp-D8h]
  size_t Size; // [rsp+50h] [rbp-B0h] BYREF
  size_t v58; // [rsp+58h] [rbp-A8h] BYREF
  int v59[2]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v60; // [rsp+68h] [rbp-98h]
  int v61[2]; // [rsp+70h] [rbp-90h] BYREF
  int v62; // [rsp+78h] [rbp-88h] BYREF
  __int64 v63; // [rsp+80h] [rbp-80h]
  char *v64; // [rsp+88h] [rbp-78h] BYREF
  char *v65; // [rsp+90h] [rbp-70h]
  int v66; // [rsp+98h] [rbp-68h]
  int v67; // [rsp+9Ch] [rbp-64h]
  _DWORD *v68; // [rsp+A0h] [rbp-60h]
  int v69[148]; // [rsp+B0h] [rbp-50h] BYREF

  v68 = a3;
  v7 = (int)a3;
  v63 = a1;
  v60 = a4;
  v62 = 0;
  LODWORD(v58) = 0;
  Size = 0;
  v10 = 0;
  *(_QWORD *)v59 = 0;
  v11 = 0;
  *(_QWORD *)v61 = 0;
  v67 = 0;
  memset(v69, 0, sizeof(v69));
  if ( !a4 || !a1 )
  {
    Src = 0;
    v12 = -1073741811;
    v38 = 603;
    v39 = 3221225485LL;
    goto LABEL_60;
  }
  if ( !validateMSCryptRsaKey(a2) )
  {
    v12 = -1073741811;
    v13 = 611;
    v14 = 3221225485LL;
LABEL_5:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c", v13);
    return v12;
  }
  RsaProperty = GetRsaProperty(a2, L"KeyLength", (char *)&Size + 4, 4, &v62, 0, 0);
  v12 = RsaProperty;
  if ( RsaProperty < 0 )
  {
    v13 = 625;
LABEL_8:
    v14 = (unsigned int)RsaProperty;
    goto LABEL_5;
  }
  HIDWORD(Size) >>= 3;
  RsaProperty = Pkcs11VerifyRsaAesWrapBlob(a5, a6);
  v12 = RsaProperty;
  if ( RsaProperty < 0 )
  {
    v13 = 636;
    goto LABEL_8;
  }
  v16 = a5[1] + 16;
  if ( a5[1] >= 0xFFFFFFF0 )
  {
    v13 = 646;
LABEL_13:
    v12 = -1073741675;
    v14 = 3221225621LL;
    goto LABEL_5;
  }
  v17 = v16 + a5[2];
  v64 = (char *)a5 + v16;
  if ( v17 < v16 )
  {
    v13 = 654;
    goto LABEL_13;
  }
  v18 = a5[3];
  if ( v18 )
    v65 = (char *)a5 + v17;
  else
    v65 = 0;
  v66 = v18;
  RsaProperty = MSCryptRsaDecrypt(a2, (int)a5 + 16, HIDWORD(Size), (unsigned int)&v64, 0, 0, 0, 0, (__int64)&v58, 4);
  v12 = RsaProperty;
  if ( RsaProperty < 0 )
  {
    v13 = 673;
    goto LABEL_8;
  }
  v22 = v58;
  Src = (_BYTE *)MSCryptAlloc((unsigned int)v58, v19, v20, v21);
  if ( !Src )
  {
    v12 = -1073741801;
    v13 = 680;
    v14 = 3221225495LL;
    goto LABEL_5;
  }
  v24 = MSCryptRsaDecrypt(
          a2,
          (int)a5 + 16,
          HIDWORD(Size),
          (unsigned int)&v64,
          0,
          0,
          (__int64)Src,
          v22,
          (__int64)&v58,
          4);
  v12 = v24;
  if ( v24 < 0 )
  {
    DebugTraceError(
      (unsigned int)v24,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c",
      696);
LABEL_68:
    v53 = (unsigned int)v58;
    v54 = Src;
    if ( (_DWORD)v58 )
    {
      do
      {
        *v54++ = 0;
        --v53;
      }
      while ( v53 );
    }
    MSCryptFree(Src);
    return v12;
  }
  v25 = MSCryptOpenSymmetricProvider(v59, L"AES", 0);
  v12 = v25;
  if ( v25 < 0 )
  {
    DebugTraceError(
      (unsigned int)v25,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c",
      707);
    v10 = *(_QWORD *)v59;
    goto LABEL_65;
  }
  v10 = *(_QWORD *)v59;
  v26 = 592;
  LODWORD(v56) = v58;
  SymmetricKey = MSCryptGenerateSymmetricKey(v59[0], (int)v61, (int)v69, 592, Src, v56, 0);
  v12 = SymmetricKey;
  if ( SymmetricKey < 0 )
  {
    v28 = 720;
    v29 = (unsigned int)SymmetricKey;
LABEL_29:
    DebugTraceError(v29, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c", v28);
    v11 = *(_QWORD *)v61;
    goto LABEL_62;
  }
  v30 = a5[1];
  if ( v30 < HIDWORD(Size) )
  {
    v12 = -1073741675;
    v28 = 727;
    v29 = 3221225621LL;
    goto LABEL_29;
  }
  v31 = v30 - HIDWORD(Size);
  v11 = *(_QWORD *)v61;
  *(_QWORD *)v59 = (char *)a5 + HIDWORD(Size) + 16;
  v32 = MSCryptAesKeyUnwrapPad(v61[0], 0, (unsigned int)&Size, v59[0], v31);
  v12 = v32;
  if ( v32 < 0 )
  {
    DebugTraceError(
      (unsigned int)v32,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c",
      739);
    goto LABEL_62;
  }
  v36 = MSCryptAlloc((unsigned int)Size, v33, v34, v35);
  v37 = (void *)v36;
  if ( v36 )
  {
    v40 = MSCryptAesKeyUnwrapPad(v11, v36, (unsigned int)&Size, v59[0], v31);
    v41 = (unsigned int)Size;
    v12 = v40;
    if ( v40 >= 0 )
    {
      v44 = *(_DWORD *)(v63 + 8);
      if ( (v44 & 0xFFFF0000) != 0x30000 )
      {
        v47 = v68;
        v48 = Size + 12;
        if ( v68 )
        {
          if ( (unsigned int)Size > 0xC80 )
          {
            v12 = -1073741481;
            v42 = 805;
            v43 = 3221225815LL;
            goto LABEL_38;
          }
          if ( *v60 < (unsigned int)Size )
          {
            *v60 = v48;
            v12 = -2146893784;
            v43 = 2148073512LL;
            v42 = 812;
            goto LABEL_38;
          }
          v49 = (unsigned int)Size;
          *v68 = 1296188491;
          v47[1] = 1;
          v47[2] = v41;
          memmove(v47 + 3, v37, v49);
        }
        *v60 = v48;
        goto LABEL_55;
      }
      LODWORD(Size) = 0;
      if ( (unsigned int)(unsigned __int16)v44 - 4 <= 2 || (v45 = (unsigned __int16)v44 == 11, v46 = 3, v45) )
        v46 = 5;
      v40 = Pkcs8ConvertToKeyBlob(v46, v7, (_DWORD)v60, (_DWORD)v37, v41, (__int64)&Size);
      v12 = v40;
      if ( v40 >= 0 )
      {
        if ( !(_DWORD)Size || (_DWORD)Size == *(_DWORD *)(v63 + 8) )
          goto LABEL_55;
        v12 = -1073739509;
        v42 = 787;
        v43 = 3221227787LL;
        goto LABEL_38;
      }
      v42 = 779;
    }
    else
    {
      v42 = 757;
    }
    v43 = (unsigned int)v40;
LABEL_38:
    DebugTraceError(v43, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c", v42);
LABEL_55:
    v50 = v41;
    v51 = v37;
    if ( (_DWORD)v41 )
    {
      do
      {
        *v51++ = 0;
        --v50;
      }
      while ( v50 );
    }
    MSCryptFree(v37);
    goto LABEL_61;
  }
  v12 = -1073741801;
  v38 = 746;
  v39 = 3221225495LL;
LABEL_60:
  DebugTraceError(v39, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c", v38);
LABEL_61:
  v26 = 592;
LABEL_62:
  if ( v11 )
  {
    MSCryptDestroyKey(v11);
    v52 = v69;
    do
    {
      *(_BYTE *)v52 = 0;
      v52 = (int *)((char *)v52 + 1);
      --v26;
    }
    while ( v26 );
  }
LABEL_65:
  if ( v10 )
    MSCryptCloseSymmetricProvider(v10, 0);
  if ( Src )
    goto LABEL_68;
  return v12;
}

```

## disassembly

```asm
0x18007f0f8  mov     [rsp-8+arg_0], rbx
0x18007f0fd  push    rbp
0x18007f0fe  push    rsi
0x18007f0ff  push    rdi
0x18007f100  push    r12
0x18007f102  push    r13
0x18007f104  push    r14
0x18007f106  push    r15
0x18007f108  lea     rbp, [rsp-210h]
0x18007f110  sub     rsp, 310h
0x18007f117  mov     rax, cs:__security_cookie
0x18007f11e  xor     rax, rsp
0x18007f121  mov     [rbp+240h+var_40], rax
0x18007f128  mov     rdi, [rbp+240h+arg_20]
0x18007f12f  xor     eax, eax
0x18007f131  mov     rbx, r9
0x18007f134  mov     [rbp+240h+var_2A0], r8
0x18007f138  mov     r15, r8
0x18007f13b  mov     [rbp+240h+var_2C0], rcx
0x18007f13f  mov     r14, rdx
0x18007f142  mov     [rsp+340h+var_2D8], rbx
0x18007f147  mov     rsi, rcx
0x18007f14a  mov     dword ptr [rsp+340h+Size+4], eax
0x18007f14e  xor     edx, edx; Val
0x18007f150  mov     [rsp+340h+var_2C8], eax
0x18007f154  mov     r8d, 250h; Size
0x18007f15a  mov     dword ptr [rsp+340h+var_2E8], eax
0x18007f15e  lea     rcx, [rbp+240h+var_290]; void *
0x18007f162  mov     dword ptr [rsp+340h+Size], eax
0x18007f166  mov     r13d, eax
0x18007f169  mov     qword ptr [rsp+340h+var_2E0], rax
0x18007f16e  mov     r12d, eax
0x18007f171  mov     qword ptr [rsp+340h+var_2D0], rax
0x18007f176  mov     [rbp+240h+var_2A4], eax
0x18007f179  call    memset
0x18007f17e  test    rbx, rbx
0x18007f181  jz      loc_18007F5EA
0x18007f187  test    rsi, rsi
0x18007f18a  jz      loc_18007F5EA
0x18007f190  mov     rcx, r14
0x18007f193  call    validateMSCryptRsaKey
0x18007f198  test    rax, rax
0x18007f19b  jnz     short loc_18007F1C5
0x18007f19d  mov     ebx, 0C000000Dh
0x18007f1a2  mov     r9d, 263h
0x18007f1a8  mov     ecx, 0C000000Dh
0x18007f1ad  lea     rdx, aStatus; "Status"
0x18007f1b4  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007f1bb  call    DebugTraceError
0x18007f1c0  jmp     loc_18007F669
0x18007f1c5  mov     byte ptr [rsp+340h+var_310], r13b
0x18007f1ca  lea     rax, [rsp+340h+var_2C8]
0x18007f1cf  mov     esi, 4
0x18007f1d4  mov     dword ptr [rsp+340h+var_318], r13d
0x18007f1d9  mov     r9d, esi
0x18007f1dc  mov     [rsp+340h+Src], rax
0x18007f1e1  lea     r8, [rsp+340h+Size+4]
0x18007f1e6  mov     rcx, r14
0x18007f1e9  lea     rdx, aKeylength; "KeyLength"
0x18007f1f0  call    GetRsaProperty
0x18007f1f5  mov     ebx, eax
0x18007f1f7  test    eax, eax
0x18007f1f9  jns     short loc_18007F205
0x18007f1fb  mov     r9d, 271h
0x18007f201  mov     ecx, eax
0x18007f203  jmp     short loc_18007F1AD
0x18007f205  mov     r8d, dword ptr [rsp+340h+Size+4]
0x18007f20a  mov     rcx, rdi
0x18007f20d  mov     edx, [rbp+240h+arg_28]
0x18007f213  shr     r8d, 3
0x18007f217  mov     dword ptr [rsp+340h+Size+4], r8d
0x18007f21c  call    Pkcs11VerifyRsaAesWrapBlob
0x18007f221  mov     ebx, eax
0x18007f223  test    eax, eax
0x18007f225  jns     short loc_18007F22F
0x18007f227  mov     r9d, 27Ch
0x18007f22d  jmp     short loc_18007F201
0x18007f22f  mov     ecx, [rdi+4]
0x18007f232  add     ecx, 10h
0x18007f235  cmp     ecx, 10h
0x18007f238  jnb     short loc_18007F24F
0x18007f23a  mov     r9d, 286h
0x18007f240  mov     ebx, 0C0000095h
0x18007f245  mov     ecx, 0C0000095h
0x18007f24a  jmp     loc_18007F1AD
0x18007f24f  mov     edx, [rdi+8]
0x18007f252  mov     eax, ecx
0x18007f254  add     edx, ecx
0x18007f256  add     rax, rdi
0x18007f259  mov     [rbp+240h+var_2B8], rax
0x18007f25d  cmp     edx, ecx
0x18007f25f  jnb     short loc_18007F269
0x18007f261  mov     r9d, 28Eh
0x18007f267  jmp     short loc_18007F240
0x18007f269  mov     ecx, [rdi+0Ch]
0x18007f26c  lea     r12, [rdi+10h]
0x18007f270  test    ecx, ecx
0x18007f272  jnz     short loc_18007F27A
0x18007f274  mov     [rbp+240h+var_2B0], r13
0x18007f278  jmp     short loc_18007F283
0x18007f27a  mov     eax, edx
0x18007f27c  add     rax, rdi
0x18007f27f  mov     [rbp+240h+var_2B0], rax
0x18007f283  mov     r8d, dword ptr [rsp+340h+Size+4]
0x18007f288  lea     rax, [rsp+340h+var_2E8]
0x18007f28d  mov     [rsp+340h+var_2F8], esi
0x18007f291  lea     r9, [rbp+240h+var_2B8]
0x18007f295  mov     [rsp+340h+var_300], rax
0x18007f29a  mov     rdx, r12
0x18007f29d  mov     [rsp+340h+var_308], r13d
0x18007f2a2  mov     qword ptr [rsp+340h+var_310], r13
0x18007f2a7  mov     [rbp+240h+var_2A8], ecx
0x18007f2aa  mov     rcx, r14
0x18007f2ad  mov     dword ptr [rsp+340h+var_318], r13d
0x18007f2b2  mov     [rsp+340h+Src], r13
0x18007f2b7  call    MSCryptRsaDecrypt
0x18007f2bc  mov     ebx, eax
0x18007f2be  test    eax, eax
0x18007f2c0  jns     short loc_18007F2CD
0x18007f2c2  mov     r9d, 2A1h
0x18007f2c8  jmp     loc_18007F201
0x18007f2cd  mov     ebx, dword ptr [rsp+340h+var_2E8]
0x18007f2d1  mov     ecx, ebx
0x18007f2d3  call    MSCryptAlloc
0x18007f2d8  mov     rsi, rax
0x18007f2db  test    rax, rax
0x18007f2de  jnz     short loc_18007F2F5
0x18007f2e0  mov     ebx, 0C0000017h
0x18007f2e5  mov     r9d, 2A8h
0x18007f2eb  mov     ecx, 0C0000017h
0x18007f2f0  jmp     loc_18007F1AD
0x18007f2f5  mov     r8d, dword ptr [rsp+340h+Size+4]
0x18007f2fa  lea     rax, [rsp+340h+var_2E8]
0x18007f2ff  mov     [rsp+340h+var_2F8], 4
0x18007f307  lea     r9, [rbp+240h+var_2B8]
0x18007f30b  mov     [rsp+340h+var_300], rax
0x18007f310  mov     rdx, r12
0x18007f313  mov     [rsp+340h+var_308], ebx
0x18007f317  mov     rcx, r14
0x18007f31a  mov     qword ptr [rsp+340h+var_310], rsi
0x18007f31f  mov     dword ptr [rsp+340h+var_318], r13d
0x18007f324  mov     [rsp+340h+Src], r13
0x18007f329  call    MSCryptRsaDecrypt
0x18007f32e  mov     ebx, eax
0x18007f330  test    eax, eax
0x18007f332  jns     short loc_18007F354
0x18007f334  mov     r9d, 2B8h
0x18007f33a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007f341  lea     rdx, aStatus; "Status"
0x18007f348  mov     ecx, eax
0x18007f34a  call    DebugTraceError
0x18007f34f  jmp     loc_18007F649
0x18007f354  xor     r8d, r8d
0x18007f357  lea     rdx, aAes; "AES"
0x18007f35e  lea     rcx, [rsp+340h+var_2E0]
0x18007f363  call    MSCryptOpenSymmetricProvider
0x18007f368  mov     ebx, eax
0x18007f36a  test    eax, eax
0x18007f36c  jns     short loc_18007F393
0x18007f36e  mov     r9d, 2C3h
0x18007f374  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007f37b  lea     rdx, aStatus; "Status"
0x18007f382  mov     ecx, eax
0x18007f384  call    DebugTraceError
0x18007f389  mov     r13, qword ptr [rsp+340h+var_2E0]
0x18007f38e  jmp     loc_18007F632
0x18007f393  mov     eax, dword ptr [rsp+340h+var_2E8]
0x18007f397  lea     r8, [rbp+240h+var_290]; int
0x18007f39b  mov     [rsp+340h+var_310], r13d; int
0x18007f3a0  lea     rdx, [rsp+340h+var_2D0]; int
0x18007f3a5  mov     r13, qword ptr [rsp+340h+var_2E0]
0x18007f3aa  mov     r14d, 250h
0x18007f3b0  mov     dword ptr [rsp+340h+var_318], eax; Size
0x18007f3b4  mov     rcx, r13; int
0x18007f3b7  mov     r9d, r14d; int
0x18007f3ba  mov     [rsp+340h+Src], rsi; Src
0x18007f3bf  call    MSCryptGenerateSymmetricKey
0x18007f3c4  mov     ebx, eax
0x18007f3c6  test    eax, eax
0x18007f3c8  jns     short loc_18007F3EF
0x18007f3ca  mov     r9d, 2D0h
0x18007f3d0  mov     ecx, eax
0x18007f3d2  lea     rdx, aStatus; "Status"
0x18007f3d9  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007f3e0  call    DebugTraceError
0x18007f3e5  mov     r12, qword ptr [rsp+340h+var_2D0]
0x18007f3ea  jmp     loc_18007F615
0x18007f3ef  mov     eax, dword ptr [rsp+340h+Size+4]
0x18007f3f3  mov     edi, [rdi+4]
0x18007f3f6  cmp     edi, eax
0x18007f3f8  jb      loc_18007F5D5
0x18007f3fe  sub     edi, eax
0x18007f400  lea     r8, [rsp+340h+Size]
0x18007f405  add     rax, r12
0x18007f408  mov     dword ptr [rsp+340h+Src], edi
0x18007f40c  mov     r12, qword ptr [rsp+340h+var_2D0]
0x18007f411  mov     r9, rax
0x18007f414  mov     rcx, r12
0x18007f417  mov     qword ptr [rsp+340h+var_2E0], rax
0x18007f41c  xor     edx, edx
0x18007f41e  call    MSCryptAesKeyUnwrapPad
0x18007f423  mov     ebx, eax
0x18007f425  test    eax, eax
0x18007f427  jns     short loc_18007F449
0x18007f429  mov     r9d, 2E3h
0x18007f42f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007f436  lea     rdx, aStatus; "Status"
0x18007f43d  mov     ecx, eax
0x18007f43f  call    DebugTraceError
0x18007f444  jmp     loc_18007F615
0x18007f449  mov     ecx, dword ptr [rsp+340h+Size]
0x18007f44d  call    MSCryptAlloc
0x18007f452  mov     r14, rax
0x18007f455  test    rax, rax
0x18007f458  jnz     short loc_18007F46F
0x18007f45a  mov     ebx, 0C0000017h
0x18007f45f  mov     r9d, 2EAh
0x18007f465  mov     ecx, 0C0000017h
0x18007f46a  jmp     loc_18007F5FC
0x18007f46f  mov     r9, qword ptr [rsp+340h+var_2E0]
0x18007f474  lea     r8, [rsp+340h+Size]
0x18007f479  mov     rdx, r14
0x18007f47c  mov     dword ptr [rsp+340h+Src], edi
0x18007f480  mov     rcx, r12
0x18007f483  call    MSCryptAesKeyUnwrapPad
0x18007f488  mov     edi, dword ptr [rsp+340h+Size]
0x18007f48c  mov     ebx, eax
0x18007f48e  test    eax, eax
0x18007f490  jns     short loc_18007F4B2
0x18007f492  mov     r9d, 2F5h
0x18007f498  mov     ecx, eax
0x18007f49a  lea     rdx, aStatus; "Status"
0x18007f4a1  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007f4a8  call    DebugTraceError
0x18007f4ad  jmp     loc_18007F5B5
0x18007f4b2  mov     rax, [rbp+240h+var_2C0]
0x18007f4b6  mov     ecx, [rax+8]
0x18007f4b9  mov     eax, ecx
0x18007f4bb  and     eax, 0FFFF0000h
0x18007f4c0  cmp     eax, 30000h
0x18007f4c5  jnz     short loc_18007F543
0x18007f4c7  movzx   ecx, cx
0x18007f4ca  mov     dword ptr [rsp+340h+Size], 0
0x18007f4d2  lea     eax, [rcx-4]
0x18007f4d5  cmp     eax, 2
0x18007f4d8  jbe     short loc_18007F4E4
0x18007f4da  cmp     ecx, 0Bh
0x18007f4dd  mov     ecx, 3
0x18007f4e2  jnz     short loc_18007F4E9
0x18007f4e4  mov     ecx, 5
0x18007f4e9  mov     r8, [rsp+340h+var_2D8]
0x18007f4ee  lea     rax, [rsp+340h+Size]
0x18007f4f3  mov     [rsp+340h+var_318], rax
0x18007f4f8  mov     r9, r14
0x18007f4fb  mov     rdx, r15
0x18007f4fe  mov     dword ptr [rsp+340h+Src], edi
0x18007f502  call    Pkcs8ConvertToKeyBlob
0x18007f507  mov     ebx, eax
0x18007f509  test    eax, eax
0x18007f50b  jns     short loc_18007F515
0x18007f50d  mov     r9d, 30Bh
0x18007f513  jmp     short loc_18007F498
0x18007f515  mov     eax, dword ptr [rsp+340h+Size]
0x18007f519  test    eax, eax
0x18007f51b  jz      loc_18007F5B5
0x18007f521  mov     rcx, [rbp+240h+var_2C0]
0x18007f525  cmp     eax, [rcx+8]
0x18007f528  jz      loc_18007F5B5
0x18007f52e  mov     ebx, 0C000090Bh
0x18007f533  mov     r9d, 313h
0x18007f539  mov     ecx, 0C000090Bh
0x18007f53e  jmp     loc_18007F49A
0x18007f543  mov     rax, [rbp+240h+var_2A0]
0x18007f547  lea     r15d, [rdi+0Ch]
0x18007f54b  test    rax, rax
0x18007f54e  jz      short loc_18007F5AD
0x18007f550  cmp     edi, 0C80h
0x18007f556  jbe     short loc_18007F56D
0x18007f558  mov     ebx, 0C0000157h
0x18007f55d  mov     r9d, 325h
0x18007f563  mov     ecx, 0C0000157h
0x18007f568  jmp     loc_18007F49A
0x18007f56d  mov     rcx, [rsp+340h+var_2D8]
0x18007f572  cmp     [rcx], edi
0x18007f574  jnb     short loc_18007F58E
0x18007f576  mov     [rcx], r15d
0x18007f579  mov     ebx, 80090028h
0x18007f57e  mov     ecx, 80090028h
0x18007f583  mov     r9d, 32Ch
0x18007f589  jmp     loc_18007F49A
0x18007f58e  mov     r8, rdi; Size
0x18007f591  mov     dword ptr [rax], 4D42444Bh
0x18007f597  lea     rcx, [rax+0Ch]; void *
0x18007f59b  mov     dword ptr [rax+4], 1
0x18007f5a2  mov     rdx, r14; Src
0x18007f5a5  mov     [rax+8], edi
0x18007f5a8  call    memmove
0x18007f5ad  mov     rax, [rsp+340h+var_2D8]
0x18007f5b2  mov     [rax], r15d
0x18007f5b5  mov     rcx, rdi
  ... truncated ...
```
