# Pkcs11ConvertToKeyBlob

- ea: `0x180088308`
- end: `0x1800888a6`
- name: `Pkcs11ConvertToKeyBlob`
- size: `1438`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180021e20`
- `0x18004b7ac`
- `0x180081178`

## callees

- `0x18000e090`
- `0x180010530`
- `0x180010590`
- `0x18001155c`
- `0x180023f00`
- `0x18004979c`
- `0x180049c28`
- `0x18004b070`
- `0x18004c010`
- `0x180081b10`
- `0x180088308`
- `0x1800888ac`
- `0x180088bf0`
- `0x180089498`
- `0x1800a4260`
- `0x1800a4380`
- `0x1800a45c0`

## string_xrefs

- `0x1800883c4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18008854a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x180088584`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x1800885e9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18008863f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x1800886b1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18008880c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`

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
0x180088308  mov     [rsp-8+arg_0], rbx
0x18008830d  push    rbp
0x18008830e  push    rsi
0x18008830f  push    rdi
0x180088310  push    r12
0x180088312  push    r13
0x180088314  push    r14
0x180088316  push    r15
0x180088318  lea     rbp, [rsp-210h]
0x180088320  sub     rsp, 310h
0x180088327  mov     rax, cs:__security_cookie
0x18008832e  xor     rax, rsp
0x180088331  mov     [rbp+240h+var_40], rax
0x180088338  mov     rdi, [rbp+240h+arg_20]
0x18008833f  xor     eax, eax
0x180088341  mov     rbx, r9
0x180088344  mov     [rbp+240h+var_2A0], r8
0x180088348  mov     r15, r8
0x18008834b  mov     [rbp+240h+var_2C0], rcx
0x18008834f  mov     r14, rdx
0x180088352  mov     [rsp+340h+var_2D8], rbx
0x180088357  mov     rsi, rcx
0x18008835a  mov     dword ptr [rsp+340h+Size+4], eax
0x18008835e  xor     edx, edx; Val
0x180088360  mov     [rsp+340h+var_2C8], eax
0x180088364  mov     r8d, 250h; Size
0x18008836a  mov     dword ptr [rsp+340h+var_2E8], eax
0x18008836e  lea     rcx, [rbp+240h+var_290]; void *
0x180088372  mov     dword ptr [rsp+340h+Size], eax
0x180088376  mov     r13d, eax
0x180088379  mov     qword ptr [rsp+340h+var_2E0], rax
0x18008837e  mov     r12d, eax
0x180088381  mov     qword ptr [rsp+340h+var_2D0], rax
0x180088386  mov     [rbp+240h+var_2A4], eax
0x180088389  call    memset
0x18008838e  test    rbx, rbx
0x180088391  jz      loc_1800887FA
0x180088397  test    rsi, rsi
0x18008839a  jz      loc_1800887FA
0x1800883a0  mov     rcx, r14
0x1800883a3  call    validateMSCryptRsaKey
0x1800883a8  test    rax, rax
0x1800883ab  jnz     short loc_1800883D5
0x1800883ad  mov     ebx, 0C000000Dh
0x1800883b2  mov     r9d, 263h
0x1800883b8  mov     ecx, 0C000000Dh
0x1800883bd  lea     rdx, aStatus; "Status"
0x1800883c4  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800883cb  call    DebugTraceError
0x1800883d0  jmp     loc_180088879
0x1800883d5  mov     byte ptr [rsp+340h+var_310], r13b
0x1800883da  lea     rax, [rsp+340h+var_2C8]
0x1800883df  mov     esi, 4
0x1800883e4  mov     dword ptr [rsp+340h+var_318], r13d
0x1800883e9  mov     r9d, esi
0x1800883ec  mov     [rsp+340h+Src], rax
0x1800883f1  lea     r8, [rsp+340h+Size+4]
0x1800883f6  mov     rcx, r14
0x1800883f9  lea     rdx, aKeylength; "KeyLength"
0x180088400  call    GetRsaProperty
0x180088405  mov     ebx, eax
0x180088407  test    eax, eax
0x180088409  jns     short loc_180088415
0x18008840b  mov     r9d, 271h
0x180088411  mov     ecx, eax
0x180088413  jmp     short loc_1800883BD
0x180088415  mov     r8d, dword ptr [rsp+340h+Size+4]
0x18008841a  mov     rcx, rdi
0x18008841d  mov     edx, [rbp+240h+arg_28]
0x180088423  shr     r8d, 3
0x180088427  mov     dword ptr [rsp+340h+Size+4], r8d
0x18008842c  call    Pkcs11VerifyRsaAesWrapBlob
0x180088431  mov     ebx, eax
0x180088433  test    eax, eax
0x180088435  jns     short loc_18008843F
0x180088437  mov     r9d, 27Ch
0x18008843d  jmp     short loc_180088411
0x18008843f  mov     ecx, [rdi+4]
0x180088442  add     ecx, 10h
0x180088445  cmp     ecx, 10h
0x180088448  jnb     short loc_18008845F
0x18008844a  mov     r9d, 286h
0x180088450  mov     ebx, 0C0000095h
0x180088455  mov     ecx, 0C0000095h
0x18008845a  jmp     loc_1800883BD
0x18008845f  mov     edx, [rdi+8]
0x180088462  mov     eax, ecx
0x180088464  add     edx, ecx
0x180088466  add     rax, rdi
0x180088469  mov     [rbp+240h+var_2B8], rax
0x18008846d  cmp     edx, ecx
0x18008846f  jnb     short loc_180088479
0x180088471  mov     r9d, 28Eh
0x180088477  jmp     short loc_180088450
0x180088479  mov     ecx, [rdi+0Ch]
0x18008847c  lea     r12, [rdi+10h]
0x180088480  test    ecx, ecx
0x180088482  jnz     short loc_18008848A
0x180088484  mov     [rbp+240h+var_2B0], r13
0x180088488  jmp     short loc_180088493
0x18008848a  mov     eax, edx
0x18008848c  add     rax, rdi
0x18008848f  mov     [rbp+240h+var_2B0], rax
0x180088493  mov     r8d, dword ptr [rsp+340h+Size+4]
0x180088498  lea     rax, [rsp+340h+var_2E8]
0x18008849d  mov     [rsp+340h+var_2F8], esi
0x1800884a1  lea     r9, [rbp+240h+var_2B8]
0x1800884a5  mov     [rsp+340h+var_300], rax
0x1800884aa  mov     rdx, r12
0x1800884ad  mov     [rsp+340h+var_308], r13d
0x1800884b2  mov     qword ptr [rsp+340h+var_310], r13
0x1800884b7  mov     [rbp+240h+var_2A8], ecx
0x1800884ba  mov     rcx, r14
0x1800884bd  mov     dword ptr [rsp+340h+var_318], r13d
0x1800884c2  mov     [rsp+340h+Src], r13
0x1800884c7  call    MSCryptRsaDecrypt
0x1800884cc  mov     ebx, eax
0x1800884ce  test    eax, eax
0x1800884d0  jns     short loc_1800884DD
0x1800884d2  mov     r9d, 2A1h
0x1800884d8  jmp     loc_180088411
0x1800884dd  mov     ebx, dword ptr [rsp+340h+var_2E8]
0x1800884e1  mov     ecx, ebx
0x1800884e3  call    MSCryptAlloc
0x1800884e8  mov     rsi, rax
0x1800884eb  test    rax, rax
0x1800884ee  jnz     short loc_180088505
0x1800884f0  mov     ebx, 0C0000017h
0x1800884f5  mov     r9d, 2A8h
0x1800884fb  mov     ecx, 0C0000017h
0x180088500  jmp     loc_1800883BD
0x180088505  mov     r8d, dword ptr [rsp+340h+Size+4]
0x18008850a  lea     rax, [rsp+340h+var_2E8]
0x18008850f  mov     [rsp+340h+var_2F8], 4
0x180088517  lea     r9, [rbp+240h+var_2B8]
0x18008851b  mov     [rsp+340h+var_300], rax
0x180088520  mov     rdx, r12
0x180088523  mov     [rsp+340h+var_308], ebx
0x180088527  mov     rcx, r14
0x18008852a  mov     qword ptr [rsp+340h+var_310], rsi
0x18008852f  mov     dword ptr [rsp+340h+var_318], r13d
0x180088534  mov     [rsp+340h+Src], r13
0x180088539  call    MSCryptRsaDecrypt
0x18008853e  mov     ebx, eax
0x180088540  test    eax, eax
0x180088542  jns     short loc_180088564
0x180088544  mov     r9d, 2B8h
0x18008854a  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180088551  lea     rdx, aStatus; "Status"
0x180088558  mov     ecx, eax
0x18008855a  call    DebugTraceError
0x18008855f  jmp     loc_180088859
0x180088564  xor     r8d, r8d
0x180088567  lea     rdx, aAes; "AES"
0x18008856e  lea     rcx, [rsp+340h+var_2E0]
0x180088573  call    MSCryptOpenSymmetricProvider
0x180088578  mov     ebx, eax
0x18008857a  test    eax, eax
0x18008857c  jns     short loc_1800885A3
0x18008857e  mov     r9d, 2C3h
0x180088584  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008858b  lea     rdx, aStatus; "Status"
0x180088592  mov     ecx, eax
0x180088594  call    DebugTraceError
0x180088599  mov     r13, qword ptr [rsp+340h+var_2E0]
0x18008859e  jmp     loc_180088842
0x1800885a3  mov     eax, dword ptr [rsp+340h+var_2E8]
0x1800885a7  lea     r8, [rbp+240h+var_290]; int
0x1800885ab  mov     [rsp+340h+var_310], r13d; int
0x1800885b0  lea     rdx, [rsp+340h+var_2D0]; int
0x1800885b5  mov     r13, qword ptr [rsp+340h+var_2E0]
0x1800885ba  mov     r14d, 250h
0x1800885c0  mov     dword ptr [rsp+340h+var_318], eax; Size
0x1800885c4  mov     rcx, r13; int
0x1800885c7  mov     r9d, r14d; int
0x1800885ca  mov     [rsp+340h+Src], rsi; Src
0x1800885cf  call    MSCryptGenerateSymmetricKey
0x1800885d4  mov     ebx, eax
0x1800885d6  test    eax, eax
0x1800885d8  jns     short loc_1800885FF
0x1800885da  mov     r9d, 2D0h
0x1800885e0  mov     ecx, eax
0x1800885e2  lea     rdx, aStatus; "Status"
0x1800885e9  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800885f0  call    DebugTraceError
0x1800885f5  mov     r12, qword ptr [rsp+340h+var_2D0]
0x1800885fa  jmp     loc_180088825
0x1800885ff  mov     eax, dword ptr [rsp+340h+Size+4]
0x180088603  mov     edi, [rdi+4]
0x180088606  cmp     edi, eax
0x180088608  jb      loc_1800887E5
0x18008860e  sub     edi, eax
0x180088610  lea     r8, [rsp+340h+Size]
0x180088615  add     rax, r12
0x180088618  mov     dword ptr [rsp+340h+Src], edi
0x18008861c  mov     r12, qword ptr [rsp+340h+var_2D0]
0x180088621  mov     r9, rax
0x180088624  mov     rcx, r12
0x180088627  mov     qword ptr [rsp+340h+var_2E0], rax
0x18008862c  xor     edx, edx
0x18008862e  call    MSCryptAesKeyUnwrapPad
0x180088633  mov     ebx, eax
0x180088635  test    eax, eax
0x180088637  jns     short loc_180088659
0x180088639  mov     r9d, 2E3h
0x18008863f  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180088646  lea     rdx, aStatus; "Status"
0x18008864d  mov     ecx, eax
0x18008864f  call    DebugTraceError
0x180088654  jmp     loc_180088825
0x180088659  mov     ecx, dword ptr [rsp+340h+Size]
0x18008865d  call    MSCryptAlloc
0x180088662  mov     r14, rax
0x180088665  test    rax, rax
0x180088668  jnz     short loc_18008867F
0x18008866a  mov     ebx, 0C0000017h
0x18008866f  mov     r9d, 2EAh
0x180088675  mov     ecx, 0C0000017h
0x18008867a  jmp     loc_18008880C
0x18008867f  mov     r9, qword ptr [rsp+340h+var_2E0]
0x180088684  lea     r8, [rsp+340h+Size]
0x180088689  mov     rdx, r14
0x18008868c  mov     dword ptr [rsp+340h+Src], edi
0x180088690  mov     rcx, r12
0x180088693  call    MSCryptAesKeyUnwrapPad
0x180088698  mov     edi, dword ptr [rsp+340h+Size]
0x18008869c  mov     ebx, eax
0x18008869e  test    eax, eax
0x1800886a0  jns     short loc_1800886C2
0x1800886a2  mov     r9d, 2F5h
0x1800886a8  mov     ecx, eax
0x1800886aa  lea     rdx, aStatus; "Status"
0x1800886b1  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800886b8  call    DebugTraceError
0x1800886bd  jmp     loc_1800887C5
0x1800886c2  mov     rax, [rbp+240h+var_2C0]
0x1800886c6  mov     ecx, [rax+8]
0x1800886c9  mov     eax, ecx
0x1800886cb  and     eax, 0FFFF0000h
0x1800886d0  cmp     eax, 30000h
0x1800886d5  jnz     short loc_180088753
0x1800886d7  movzx   ecx, cx
0x1800886da  mov     dword ptr [rsp+340h+Size], 0
0x1800886e2  lea     eax, [rcx-4]
0x1800886e5  cmp     eax, 2
0x1800886e8  jbe     short loc_1800886F4
0x1800886ea  cmp     ecx, 0Bh
0x1800886ed  mov     ecx, 3
0x1800886f2  jnz     short loc_1800886F9
0x1800886f4  mov     ecx, 5
0x1800886f9  mov     r8, [rsp+340h+var_2D8]
0x1800886fe  lea     rax, [rsp+340h+Size]
0x180088703  mov     [rsp+340h+var_318], rax
0x180088708  mov     r9, r14
0x18008870b  mov     rdx, r15
0x18008870e  mov     dword ptr [rsp+340h+Src], edi
0x180088712  call    Pkcs8ConvertToKeyBlob
0x180088717  mov     ebx, eax
0x180088719  test    eax, eax
0x18008871b  jns     short loc_180088725
0x18008871d  mov     r9d, 30Bh
0x180088723  jmp     short loc_1800886A8
0x180088725  mov     eax, dword ptr [rsp+340h+Size]
0x180088729  test    eax, eax
0x18008872b  jz      loc_1800887C5
0x180088731  mov     rcx, [rbp+240h+var_2C0]
0x180088735  cmp     eax, [rcx+8]
0x180088738  jz      loc_1800887C5
0x18008873e  mov     ebx, 0C000090Bh
0x180088743  mov     r9d, 313h
0x180088749  mov     ecx, 0C000090Bh
0x18008874e  jmp     loc_1800886AA
0x180088753  mov     rax, [rbp+240h+var_2A0]
0x180088757  lea     r15d, [rdi+0Ch]
0x18008875b  test    rax, rax
0x18008875e  jz      short loc_1800887BD
0x180088760  cmp     edi, 0C80h
0x180088766  jbe     short loc_18008877D
0x180088768  mov     ebx, 0C0000157h
0x18008876d  mov     r9d, 325h
0x180088773  mov     ecx, 0C0000157h
0x180088778  jmp     loc_1800886AA
0x18008877d  mov     rcx, [rsp+340h+var_2D8]
0x180088782  cmp     [rcx], edi
0x180088784  jnb     short loc_18008879E
0x180088786  mov     [rcx], r15d
0x180088789  mov     ebx, 80090028h
0x18008878e  mov     ecx, 80090028h
0x180088793  mov     r9d, 32Ch
0x180088799  jmp     loc_1800886AA
0x18008879e  mov     r8, rdi; Size
0x1800887a1  mov     dword ptr [rax], 4D42444Bh
0x1800887a7  lea     rcx, [rax+0Ch]; void *
0x1800887ab  mov     dword ptr [rax+4], 1
0x1800887b2  mov     rdx, r14; Src
0x1800887b5  mov     [rax+8], edi
0x1800887b8  call    memmove
0x1800887bd  mov     rax, [rsp+340h+var_2D8]
0x1800887c2  mov     [rax], r15d
0x1800887c5  mov     rcx, rdi
  ... truncated ...
```
