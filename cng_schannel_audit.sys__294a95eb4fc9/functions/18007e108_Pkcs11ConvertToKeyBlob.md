# Pkcs11ConvertToKeyBlob

- ea: `0x18007e108`
- end: `0x18007e6a6`
- name: `Pkcs11ConvertToKeyBlob`
- size: `1438`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180017cf0`
- `0x1800417cc`
- `0x180076fd8`

## callees

- `0x180003f70`
- `0x180006410`
- `0x180006470`
- `0x18000743c`
- `0x180019dd0`
- `0x18003f7dc`
- `0x18003fc68`
- `0x180041090`
- `0x180042030`
- `0x180077970`
- `0x18007e108`
- `0x18007e6ac`
- `0x18007e9f0`
- `0x18007f298`
- `0x18009d820`
- `0x18009da40`
- `0x18009dd40`

## string_xrefs

- `0x18007e1c4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18007e34a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18007e384`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18007e3e9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18007e43f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18007e4b1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18007e60c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`

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
  int v20; // ebx
  _BYTE *Src; // rsi
  int v22; // eax
  int v23; // eax
  __int64 v24; // r14
  int SymmetricKey; // eax
  __int64 v26; // r9
  __int64 v27; // rcx
  unsigned int v28; // edi
  unsigned int v29; // edi
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rax
  void *v33; // r14
  __int64 v34; // r9
  __int64 v35; // rcx
  int v36; // eax
  __int64 v37; // rdi
  __int64 v38; // r9
  __int64 v39; // rcx
  int v40; // ecx
  bool v41; // zf
  int v42; // ecx
  _DWORD *v43; // rax
  int v44; // r15d
  size_t v45; // r8
  __int64 v46; // rcx
  _BYTE *v47; // rax
  int *v48; // rax
  __int64 v49; // rax
  _BYTE *v50; // rcx
  size_t v52; // [rsp+28h] [rbp-D8h]
  size_t Size; // [rsp+50h] [rbp-B0h] BYREF
  size_t v54; // [rsp+58h] [rbp-A8h] BYREF
  int v55[2]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v56; // [rsp+68h] [rbp-98h]
  int v57[2]; // [rsp+70h] [rbp-90h] BYREF
  int v58; // [rsp+78h] [rbp-88h] BYREF
  __int64 v59; // [rsp+80h] [rbp-80h]
  char *v60; // [rsp+88h] [rbp-78h] BYREF
  char *v61; // [rsp+90h] [rbp-70h]
  int v62; // [rsp+98h] [rbp-68h]
  int v63; // [rsp+9Ch] [rbp-64h]
  _DWORD *v64; // [rsp+A0h] [rbp-60h]
  int v65[148]; // [rsp+B0h] [rbp-50h] BYREF

  v64 = a3;
  v7 = (int)a3;
  v59 = a1;
  v56 = a4;
  v58 = 0;
  LODWORD(v54) = 0;
  Size = 0;
  v10 = 0;
  *(_QWORD *)v55 = 0;
  v11 = 0;
  *(_QWORD *)v57 = 0;
  v63 = 0;
  memset(v65, 0, sizeof(v65));
  if ( !a4 || !a1 )
  {
    Src = 0;
    v12 = -1073741811;
    v34 = 603;
    v35 = 3221225485LL;
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
  RsaProperty = GetRsaProperty(a2, L"KeyLength", (char *)&Size + 4, 4, &v58, 0, 0);
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
  v60 = (char *)a5 + v16;
  if ( v17 < v16 )
  {
    v13 = 654;
    goto LABEL_13;
  }
  v18 = a5[3];
  if ( v18 )
    v61 = (char *)a5 + v17;
  else
    v61 = 0;
  v62 = v18;
  RsaProperty = MSCryptRsaDecrypt(a2, (int)a5 + 16, HIDWORD(Size), (unsigned int)&v60, 0, 0, 0, 0, (__int64)&v54, 4);
  v12 = RsaProperty;
  if ( RsaProperty < 0 )
  {
    v13 = 673;
    goto LABEL_8;
  }
  v20 = v54;
  Src = (_BYTE *)MSCryptAlloc((unsigned int)v54, v19);
  if ( !Src )
  {
    v12 = -1073741801;
    v13 = 680;
    v14 = 3221225495LL;
    goto LABEL_5;
  }
  v22 = MSCryptRsaDecrypt(
          a2,
          (int)a5 + 16,
          HIDWORD(Size),
          (unsigned int)&v60,
          0,
          0,
          (__int64)Src,
          v20,
          (__int64)&v54,
          4);
  v12 = v22;
  if ( v22 < 0 )
  {
    DebugTraceError(
      (unsigned int)v22,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c",
      696);
LABEL_68:
    v49 = (unsigned int)v54;
    v50 = Src;
    if ( (_DWORD)v54 )
    {
      do
      {
        *v50++ = 0;
        --v49;
      }
      while ( v49 );
    }
    MSCryptFree(Src);
    return v12;
  }
  v23 = MSCryptOpenSymmetricProvider(v55, L"AES", 0);
  v12 = v23;
  if ( v23 < 0 )
  {
    DebugTraceError(
      (unsigned int)v23,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c",
      707);
    v10 = *(_QWORD *)v55;
    goto LABEL_65;
  }
  v10 = *(_QWORD *)v55;
  v24 = 592;
  LODWORD(v52) = v54;
  SymmetricKey = MSCryptGenerateSymmetricKey(v55[0], (int)v57, (int)v65, 592, Src, v52, 0);
  v12 = SymmetricKey;
  if ( SymmetricKey < 0 )
  {
    v26 = 720;
    v27 = (unsigned int)SymmetricKey;
LABEL_29:
    DebugTraceError(v27, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c", v26);
    v11 = *(_QWORD *)v57;
    goto LABEL_62;
  }
  v28 = a5[1];
  if ( v28 < HIDWORD(Size) )
  {
    v12 = -1073741675;
    v26 = 727;
    v27 = 3221225621LL;
    goto LABEL_29;
  }
  v29 = v28 - HIDWORD(Size);
  v11 = *(_QWORD *)v57;
  *(_QWORD *)v55 = (char *)a5 + HIDWORD(Size) + 16;
  v30 = MSCryptAesKeyUnwrapPad(v57[0], 0, (unsigned int)&Size, v55[0], v29);
  v12 = v30;
  if ( v30 < 0 )
  {
    DebugTraceError(
      (unsigned int)v30,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c",
      739);
    goto LABEL_62;
  }
  v32 = MSCryptAlloc((unsigned int)Size, v31);
  v33 = (void *)v32;
  if ( v32 )
  {
    v36 = MSCryptAesKeyUnwrapPad(v11, v32, (unsigned int)&Size, v55[0], v29);
    v37 = (unsigned int)Size;
    v12 = v36;
    if ( v36 >= 0 )
    {
      v40 = *(_DWORD *)(v59 + 8);
      if ( (v40 & 0xFFFF0000) != 0x30000 )
      {
        v43 = v64;
        v44 = Size + 12;
        if ( v64 )
        {
          if ( (unsigned int)Size > 0xC80 )
          {
            v12 = -1073741481;
            v38 = 805;
            v39 = 3221225815LL;
            goto LABEL_38;
          }
          if ( *v56 < (unsigned int)Size )
          {
            *v56 = v44;
            v12 = -2146893784;
            v39 = 2148073512LL;
            v38 = 812;
            goto LABEL_38;
          }
          v45 = (unsigned int)Size;
          *v64 = 1296188491;
          v43[1] = 1;
          v43[2] = v37;
          memmove(v43 + 3, v33, v45);
        }
        *v56 = v44;
        goto LABEL_55;
      }
      LODWORD(Size) = 0;
      if ( (unsigned int)(unsigned __int16)v40 - 4 <= 2 || (v41 = (unsigned __int16)v40 == 11, v42 = 3, v41) )
        v42 = 5;
      v36 = Pkcs8ConvertToKeyBlob(v42, v7, (_DWORD)v56, (_DWORD)v33, v37, (__int64)&Size);
      v12 = v36;
      if ( v36 >= 0 )
      {
        if ( !(_DWORD)Size || (_DWORD)Size == *(_DWORD *)(v59 + 8) )
          goto LABEL_55;
        v12 = -1073739509;
        v38 = 787;
        v39 = 3221227787LL;
        goto LABEL_38;
      }
      v38 = 779;
    }
    else
    {
      v38 = 757;
    }
    v39 = (unsigned int)v36;
LABEL_38:
    DebugTraceError(v39, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c", v38);
LABEL_55:
    v46 = v37;
    v47 = v33;
    if ( (_DWORD)v37 )
    {
      do
      {
        *v47++ = 0;
        --v46;
      }
      while ( v46 );
    }
    MSCryptFree(v33);
    goto LABEL_61;
  }
  v12 = -1073741801;
  v34 = 746;
  v35 = 3221225495LL;
LABEL_60:
  DebugTraceError(v35, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c", v34);
LABEL_61:
  v24 = 592;
LABEL_62:
  if ( v11 )
  {
    MSCryptDestroyKey(v11);
    v48 = v65;
    do
    {
      *(_BYTE *)v48 = 0;
      v48 = (int *)((char *)v48 + 1);
      --v24;
    }
    while ( v24 );
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
0x18007e108  mov     [rsp-8+arg_0], rbx
0x18007e10d  push    rbp
0x18007e10e  push    rsi
0x18007e10f  push    rdi
0x18007e110  push    r12
0x18007e112  push    r13
0x18007e114  push    r14
0x18007e116  push    r15
0x18007e118  lea     rbp, [rsp-210h]
0x18007e120  sub     rsp, 310h
0x18007e127  mov     rax, cs:__security_cookie
0x18007e12e  xor     rax, rsp
0x18007e131  mov     [rbp+240h+var_40], rax
0x18007e138  mov     rdi, [rbp+240h+arg_20]
0x18007e13f  xor     eax, eax
0x18007e141  mov     rbx, r9
0x18007e144  mov     [rbp+240h+var_2A0], r8
0x18007e148  mov     r15, r8
0x18007e14b  mov     [rbp+240h+var_2C0], rcx
0x18007e14f  mov     r14, rdx
0x18007e152  mov     [rsp+340h+var_2D8], rbx
0x18007e157  mov     rsi, rcx
0x18007e15a  mov     dword ptr [rsp+340h+Size+4], eax
0x18007e15e  xor     edx, edx; Val
0x18007e160  mov     [rsp+340h+var_2C8], eax
0x18007e164  mov     r8d, 250h; Size
0x18007e16a  mov     dword ptr [rsp+340h+var_2E8], eax
0x18007e16e  lea     rcx, [rbp+240h+var_290]; void *
0x18007e172  mov     dword ptr [rsp+340h+Size], eax
0x18007e176  mov     r13d, eax
0x18007e179  mov     qword ptr [rsp+340h+var_2E0], rax
0x18007e17e  mov     r12d, eax
0x18007e181  mov     qword ptr [rsp+340h+var_2D0], rax
0x18007e186  mov     [rbp+240h+var_2A4], eax
0x18007e189  call    memset
0x18007e18e  test    rbx, rbx
0x18007e191  jz      loc_18007E5FA
0x18007e197  test    rsi, rsi
0x18007e19a  jz      loc_18007E5FA
0x18007e1a0  mov     rcx, r14
0x18007e1a3  call    validateMSCryptRsaKey
0x18007e1a8  test    rax, rax
0x18007e1ab  jnz     short loc_18007E1D5
0x18007e1ad  mov     ebx, 0C000000Dh
0x18007e1b2  mov     r9d, 263h
0x18007e1b8  mov     ecx, 0C000000Dh
0x18007e1bd  lea     rdx, aStatus; "Status"
0x18007e1c4  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e1cb  call    DebugTraceError
0x18007e1d0  jmp     loc_18007E679
0x18007e1d5  mov     byte ptr [rsp+340h+var_310], r13b
0x18007e1da  lea     rax, [rsp+340h+var_2C8]
0x18007e1df  mov     esi, 4
0x18007e1e4  mov     dword ptr [rsp+340h+var_318], r13d
0x18007e1e9  mov     r9d, esi
0x18007e1ec  mov     [rsp+340h+Src], rax
0x18007e1f1  lea     r8, [rsp+340h+Size+4]
0x18007e1f6  mov     rcx, r14
0x18007e1f9  lea     rdx, aKeylength; "KeyLength"
0x18007e200  call    GetRsaProperty
0x18007e205  mov     ebx, eax
0x18007e207  test    eax, eax
0x18007e209  jns     short loc_18007E215
0x18007e20b  mov     r9d, 271h
0x18007e211  mov     ecx, eax
0x18007e213  jmp     short loc_18007E1BD
0x18007e215  mov     r8d, dword ptr [rsp+340h+Size+4]
0x18007e21a  mov     rcx, rdi
0x18007e21d  mov     edx, [rbp+240h+arg_28]
0x18007e223  shr     r8d, 3
0x18007e227  mov     dword ptr [rsp+340h+Size+4], r8d
0x18007e22c  call    Pkcs11VerifyRsaAesWrapBlob
0x18007e231  mov     ebx, eax
0x18007e233  test    eax, eax
0x18007e235  jns     short loc_18007E23F
0x18007e237  mov     r9d, 27Ch
0x18007e23d  jmp     short loc_18007E211
0x18007e23f  mov     ecx, [rdi+4]
0x18007e242  add     ecx, 10h
0x18007e245  cmp     ecx, 10h
0x18007e248  jnb     short loc_18007E25F
0x18007e24a  mov     r9d, 286h
0x18007e250  mov     ebx, 0C0000095h
0x18007e255  mov     ecx, 0C0000095h
0x18007e25a  jmp     loc_18007E1BD
0x18007e25f  mov     edx, [rdi+8]
0x18007e262  mov     eax, ecx
0x18007e264  add     edx, ecx
0x18007e266  add     rax, rdi
0x18007e269  mov     [rbp+240h+var_2B8], rax
0x18007e26d  cmp     edx, ecx
0x18007e26f  jnb     short loc_18007E279
0x18007e271  mov     r9d, 28Eh
0x18007e277  jmp     short loc_18007E250
0x18007e279  mov     ecx, [rdi+0Ch]
0x18007e27c  lea     r12, [rdi+10h]
0x18007e280  test    ecx, ecx
0x18007e282  jnz     short loc_18007E28A
0x18007e284  mov     [rbp+240h+var_2B0], r13
0x18007e288  jmp     short loc_18007E293
0x18007e28a  mov     eax, edx
0x18007e28c  add     rax, rdi
0x18007e28f  mov     [rbp+240h+var_2B0], rax
0x18007e293  mov     r8d, dword ptr [rsp+340h+Size+4]
0x18007e298  lea     rax, [rsp+340h+var_2E8]
0x18007e29d  mov     [rsp+340h+var_2F8], esi
0x18007e2a1  lea     r9, [rbp+240h+var_2B8]
0x18007e2a5  mov     [rsp+340h+var_300], rax
0x18007e2aa  mov     rdx, r12
0x18007e2ad  mov     [rsp+340h+var_308], r13d
0x18007e2b2  mov     qword ptr [rsp+340h+var_310], r13
0x18007e2b7  mov     [rbp+240h+var_2A8], ecx
0x18007e2ba  mov     rcx, r14
0x18007e2bd  mov     dword ptr [rsp+340h+var_318], r13d
0x18007e2c2  mov     [rsp+340h+Src], r13
0x18007e2c7  call    MSCryptRsaDecrypt
0x18007e2cc  mov     ebx, eax
0x18007e2ce  test    eax, eax
0x18007e2d0  jns     short loc_18007E2DD
0x18007e2d2  mov     r9d, 2A1h
0x18007e2d8  jmp     loc_18007E211
0x18007e2dd  mov     ebx, dword ptr [rsp+340h+var_2E8]
0x18007e2e1  mov     ecx, ebx
0x18007e2e3  call    MSCryptAlloc
0x18007e2e8  mov     rsi, rax
0x18007e2eb  test    rax, rax
0x18007e2ee  jnz     short loc_18007E305
0x18007e2f0  mov     ebx, 0C0000017h
0x18007e2f5  mov     r9d, 2A8h
0x18007e2fb  mov     ecx, 0C0000017h
0x18007e300  jmp     loc_18007E1BD
0x18007e305  mov     r8d, dword ptr [rsp+340h+Size+4]
0x18007e30a  lea     rax, [rsp+340h+var_2E8]
0x18007e30f  mov     [rsp+340h+var_2F8], 4
0x18007e317  lea     r9, [rbp+240h+var_2B8]
0x18007e31b  mov     [rsp+340h+var_300], rax
0x18007e320  mov     rdx, r12
0x18007e323  mov     [rsp+340h+var_308], ebx
0x18007e327  mov     rcx, r14
0x18007e32a  mov     qword ptr [rsp+340h+var_310], rsi
0x18007e32f  mov     dword ptr [rsp+340h+var_318], r13d
0x18007e334  mov     [rsp+340h+Src], r13
0x18007e339  call    MSCryptRsaDecrypt
0x18007e33e  mov     ebx, eax
0x18007e340  test    eax, eax
0x18007e342  jns     short loc_18007E364
0x18007e344  mov     r9d, 2B8h
0x18007e34a  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e351  lea     rdx, aStatus; "Status"
0x18007e358  mov     ecx, eax
0x18007e35a  call    DebugTraceError
0x18007e35f  jmp     loc_18007E659
0x18007e364  xor     r8d, r8d
0x18007e367  lea     rdx, aAes; "AES"
0x18007e36e  lea     rcx, [rsp+340h+var_2E0]
0x18007e373  call    MSCryptOpenSymmetricProvider
0x18007e378  mov     ebx, eax
0x18007e37a  test    eax, eax
0x18007e37c  jns     short loc_18007E3A3
0x18007e37e  mov     r9d, 2C3h
0x18007e384  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e38b  lea     rdx, aStatus; "Status"
0x18007e392  mov     ecx, eax
0x18007e394  call    DebugTraceError
0x18007e399  mov     r13, qword ptr [rsp+340h+var_2E0]
0x18007e39e  jmp     loc_18007E642
0x18007e3a3  mov     eax, dword ptr [rsp+340h+var_2E8]
0x18007e3a7  lea     r8, [rbp+240h+var_290]; int
0x18007e3ab  mov     [rsp+340h+var_310], r13d; int
0x18007e3b0  lea     rdx, [rsp+340h+var_2D0]; int
0x18007e3b5  mov     r13, qword ptr [rsp+340h+var_2E0]
0x18007e3ba  mov     r14d, 250h
0x18007e3c0  mov     dword ptr [rsp+340h+var_318], eax; Size
0x18007e3c4  mov     rcx, r13; int
0x18007e3c7  mov     r9d, r14d; int
0x18007e3ca  mov     [rsp+340h+Src], rsi; Src
0x18007e3cf  call    MSCryptGenerateSymmetricKey
0x18007e3d4  mov     ebx, eax
0x18007e3d6  test    eax, eax
0x18007e3d8  jns     short loc_18007E3FF
0x18007e3da  mov     r9d, 2D0h
0x18007e3e0  mov     ecx, eax
0x18007e3e2  lea     rdx, aStatus; "Status"
0x18007e3e9  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e3f0  call    DebugTraceError
0x18007e3f5  mov     r12, qword ptr [rsp+340h+var_2D0]
0x18007e3fa  jmp     loc_18007E625
0x18007e3ff  mov     eax, dword ptr [rsp+340h+Size+4]
0x18007e403  mov     edi, [rdi+4]
0x18007e406  cmp     edi, eax
0x18007e408  jb      loc_18007E5E5
0x18007e40e  sub     edi, eax
0x18007e410  lea     r8, [rsp+340h+Size]
0x18007e415  add     rax, r12
0x18007e418  mov     dword ptr [rsp+340h+Src], edi
0x18007e41c  mov     r12, qword ptr [rsp+340h+var_2D0]
0x18007e421  mov     r9, rax
0x18007e424  mov     rcx, r12
0x18007e427  mov     qword ptr [rsp+340h+var_2E0], rax
0x18007e42c  xor     edx, edx
0x18007e42e  call    MSCryptAesKeyUnwrapPad
0x18007e433  mov     ebx, eax
0x18007e435  test    eax, eax
0x18007e437  jns     short loc_18007E459
0x18007e439  mov     r9d, 2E3h
0x18007e43f  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e446  lea     rdx, aStatus; "Status"
0x18007e44d  mov     ecx, eax
0x18007e44f  call    DebugTraceError
0x18007e454  jmp     loc_18007E625
0x18007e459  mov     ecx, dword ptr [rsp+340h+Size]
0x18007e45d  call    MSCryptAlloc
0x18007e462  mov     r14, rax
0x18007e465  test    rax, rax
0x18007e468  jnz     short loc_18007E47F
0x18007e46a  mov     ebx, 0C0000017h
0x18007e46f  mov     r9d, 2EAh
0x18007e475  mov     ecx, 0C0000017h
0x18007e47a  jmp     loc_18007E60C
0x18007e47f  mov     r9, qword ptr [rsp+340h+var_2E0]
0x18007e484  lea     r8, [rsp+340h+Size]
0x18007e489  mov     rdx, r14
0x18007e48c  mov     dword ptr [rsp+340h+Src], edi
0x18007e490  mov     rcx, r12
0x18007e493  call    MSCryptAesKeyUnwrapPad
0x18007e498  mov     edi, dword ptr [rsp+340h+Size]
0x18007e49c  mov     ebx, eax
0x18007e49e  test    eax, eax
0x18007e4a0  jns     short loc_18007E4C2
0x18007e4a2  mov     r9d, 2F5h
0x18007e4a8  mov     ecx, eax
0x18007e4aa  lea     rdx, aStatus; "Status"
0x18007e4b1  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e4b8  call    DebugTraceError
0x18007e4bd  jmp     loc_18007E5C5
0x18007e4c2  mov     rax, [rbp+240h+var_2C0]
0x18007e4c6  mov     ecx, [rax+8]
0x18007e4c9  mov     eax, ecx
0x18007e4cb  and     eax, 0FFFF0000h
0x18007e4d0  cmp     eax, 30000h
0x18007e4d5  jnz     short loc_18007E553
0x18007e4d7  movzx   ecx, cx
0x18007e4da  mov     dword ptr [rsp+340h+Size], 0
0x18007e4e2  lea     eax, [rcx-4]
0x18007e4e5  cmp     eax, 2
0x18007e4e8  jbe     short loc_18007E4F4
0x18007e4ea  cmp     ecx, 0Bh
0x18007e4ed  mov     ecx, 3
0x18007e4f2  jnz     short loc_18007E4F9
0x18007e4f4  mov     ecx, 5
0x18007e4f9  mov     r8, [rsp+340h+var_2D8]
0x18007e4fe  lea     rax, [rsp+340h+Size]
0x18007e503  mov     [rsp+340h+var_318], rax
0x18007e508  mov     r9, r14
0x18007e50b  mov     rdx, r15
0x18007e50e  mov     dword ptr [rsp+340h+Src], edi
0x18007e512  call    Pkcs8ConvertToKeyBlob
0x18007e517  mov     ebx, eax
0x18007e519  test    eax, eax
0x18007e51b  jns     short loc_18007E525
0x18007e51d  mov     r9d, 30Bh
0x18007e523  jmp     short loc_18007E4A8
0x18007e525  mov     eax, dword ptr [rsp+340h+Size]
0x18007e529  test    eax, eax
0x18007e52b  jz      loc_18007E5C5
0x18007e531  mov     rcx, [rbp+240h+var_2C0]
0x18007e535  cmp     eax, [rcx+8]
0x18007e538  jz      loc_18007E5C5
0x18007e53e  mov     ebx, 0C000090Bh
0x18007e543  mov     r9d, 313h
0x18007e549  mov     ecx, 0C000090Bh
0x18007e54e  jmp     loc_18007E4AA
0x18007e553  mov     rax, [rbp+240h+var_2A0]
0x18007e557  lea     r15d, [rdi+0Ch]
0x18007e55b  test    rax, rax
0x18007e55e  jz      short loc_18007E5BD
0x18007e560  cmp     edi, 0C80h
0x18007e566  jbe     short loc_18007E57D
0x18007e568  mov     ebx, 0C0000157h
0x18007e56d  mov     r9d, 325h
0x18007e573  mov     ecx, 0C0000157h
0x18007e578  jmp     loc_18007E4AA
0x18007e57d  mov     rcx, [rsp+340h+var_2D8]
0x18007e582  cmp     [rcx], edi
0x18007e584  jnb     short loc_18007E59E
0x18007e586  mov     [rcx], r15d
0x18007e589  mov     ebx, 80090028h
0x18007e58e  mov     ecx, 80090028h
0x18007e593  mov     r9d, 32Ch
0x18007e599  jmp     loc_18007E4AA
0x18007e59e  mov     r8, rdi; Size
0x18007e5a1  mov     dword ptr [rax], 4D42444Bh
0x18007e5a7  lea     rcx, [rax+0Ch]; void *
0x18007e5ab  mov     dword ptr [rax+4], 1
0x18007e5b2  mov     rdx, r14; Src
0x18007e5b5  mov     [rax+8], edi
0x18007e5b8  call    memmove
0x18007e5bd  mov     rax, [rsp+340h+var_2D8]
0x18007e5c2  mov     [rax], r15d
0x18007e5c5  mov     rcx, rdi
  ... truncated ...
```
