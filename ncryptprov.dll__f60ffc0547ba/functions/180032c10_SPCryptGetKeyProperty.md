# SPCryptGetKeyProperty

- ea: `0x180032c10`
- end: `0x180033a00`
- name: `SPCryptGetKeyProperty`
- size: `3568`
- prototype: `__int64 __fastcall(__int64, __int64, const wchar_t *, unsigned int *, unsigned int cbOutput, ULONG *pcbResult, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a0c0`
- `0x18004db44`

## callees

- `0x180004400`
- `0x180004f8c`
- `0x18000af80`
- `0x18000d3d0`
- `0x180014160`
- `0x180015ebc`
- `0x180017a80`
- `0x18001cf18`
- `0x18001ec8c`
- `0x18001edc8`
- `0x180020c70`
- `0x180032c10`
- `0x1800398b0`
- `0x18005038c`
- `0x1800622e0`
- `0x180063010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800338e4`
- `ntdll!RtlReleaseResource` at `0x1800339dd`
- `ntdll!RtlReleaseResource` at `0x1800338e4`
- `ntdll!RtlReleaseResource` at `0x1800339dd`
- `ntdll!RtlAcquireResourceShared` at `0x180032d69`
- `ntdll!RtlAcquireResourceShared` at `0x1800332ac`
- `ntdll!RtlAcquireResourceShared` at `0x180033661`
- `ntdll!RtlAcquireResourceShared` at `0x180032d69`
- `ntdll!RtlAcquireResourceShared` at `0x1800332ac`
- `ntdll!RtlAcquireResourceShared` at `0x180033661`
- `bcrypt!BCryptGetProperty` at `0x180032f0c`
- `bcrypt!BCryptGetProperty` at `0x180032f8d`
- `bcrypt!BCryptGetProperty` at `0x180032e0c`
- `bcrypt!BCryptGetProperty` at `0x180032f0c`
- `bcrypt!BCryptGetProperty` at `0x180032f8d`

## string_xrefs

- `0x180032c5f`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x180032ca1`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x180032da6`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x1800332f7`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18003376a`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x1800339af`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x180032d03`: `Security Descr`

## pseudocode

```c
__int64 __fastcall SPCryptGetKeyProperty(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        unsigned int *a4,
        unsigned int cbOutput,
        ULONG *pcbResult,
        unsigned int a7)
{
  unsigned int v10; // ebx
  __int64 v11; // rdi
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r15
  unsigned __int64 v15; // rax
  unsigned int v16; // ebx
  __int64 v17; // r9
  __int64 v18; // rcx
  size_t v19; // rax
  __int64 v20; // r12
  __int64 v21; // r13
  NTSTATUS (__stdcall *v22)(BCRYPT_HANDLE, LPCWSTR, PUCHAR, ULONG, ULONG *, ULONG); // rax
  int v23; // eax
  __int64 v24; // r8
  __int64 v25; // rcx
  _WORD *v26; // r12
  unsigned int v27; // eax
  unsigned int v28; // ecx
  NTSTATUS Property; // eax
  __int64 v30; // rcx
  const void *v31; // r9
  int v32; // r15d
  __int64 v33; // rax
  __int64 v34; // rcx
  unsigned int SecurityOnKeyFile; // eax
  const void *v36; // rsi
  const void *v37; // r13
  __int64 v38; // rcx
  __int64 v39; // rax
  unsigned int v40; // edx
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int PasswordHashAlg; // eax
  __int64 v47; // r9
  __int64 v48; // rcx
  const void *v49; // rdx
  unsigned int KeyLengthsFromBCrypt; // eax
  unsigned int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  unsigned int v54; // eax
  unsigned int v55; // eax
  unsigned int v56; // eax
  unsigned int v57; // eax
  unsigned int v58; // eax
  unsigned int v59; // eax
  unsigned int v60; // eax
  unsigned int v61; // eax
  unsigned int v62; // eax
  size_t v63; // r8
  int v64; // eax
  size_t Size; // [rsp+48h] [rbp-49h] BYREF
  const void *v67; // [rsp+50h] [rbp-41h]
  const void *v68; // [rsp+58h] [rbp-39h]
  size_t v69; // [rsp+60h] [rbp-31h] BYREF
  const void *v70; // [rsp+68h] [rbp-29h] BYREF
  void *Src; // [rsp+70h] [rbp-21h] BYREF
  int v72; // [rsp+78h] [rbp-19h] BYREF
  __int64 v73; // [rsp+80h] [rbp-11h]

  LODWORD(Size) = 0;
  Src = 0;
  v67 = 0;
  v70 = 0;
  LODWORD(v69) = 0;
  v73 = KspValidateAndLockProvider(a1, 0);
  if ( v73 )
  {
    v11 = KspValidateKeyHandle(a2);
    if ( !v11 )
    {
      v10 = -2146893786;
      v12 = 980;
      v13 = 2148073510LL;
LABEL_5:
      DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", v12);
LABEL_256:
      RtlReleaseResource((PRTL_RESOURCE)(v73 + 64));
      return v10;
    }
    if ( !a3 )
    {
      v12 = 987;
LABEL_8:
      v10 = -2146893785;
      v13 = 2148073511LL;
      goto LABEL_5;
    }
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( a3[v15] );
    if ( v15 > 0x40 )
    {
      v12 = 993;
      goto LABEL_8;
    }
    if ( !pcbResult )
    {
      v12 = 1000;
      goto LABEL_8;
    }
    v16 = a7;
    v72 = wcscmp_0(a3, L"Security Descr");
    if ( v72 )
    {
      if ( (a7 & 0xBFFFFFBF) != 0 )
      {
        v12 = 1035;
        goto LABEL_18;
      }
    }
    else
    {
      v16 = a7 & 0xFFFFFFBF;
      if ( (a7 & 0xFFFFFFBF) == 0 )
      {
        v12 = 1012;
LABEL_18:
        v10 = -2146893815;
        v13 = 2148073481LL;
        goto LABEL_5;
      }
      if ( (a7 & 0xFFFFFFA0) != 0 )
      {
        v12 = 1025;
        goto LABEL_18;
      }
    }
    if ( (v16 & 0x40000000) != 0 )
    {
      RtlAcquireResourceShared((PRTL_RESOURCE)(v11 + 304), 1u);
      if ( !(unsigned int)LookupKeyProperty(v11, a3, &Src, &Size) )
      {
        v19 = (unsigned int)Size;
        *pcbResult = Size;
        if ( a4 )
        {
          if ( cbOutput < (unsigned int)v19 )
          {
            v10 = -2146893784;
            goto LABEL_242;
          }
          memcpy_0(a4, Src, v19);
        }
        v10 = 0;
LABEL_242:
        v36 = v67;
        goto LABEL_243;
      }
      v10 = -2146893807;
      v17 = 1057;
      v18 = 2148073489LL;
LABEL_26:
      DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", v17);
      goto LABEL_242;
    }
    v20 = *(_QWORD *)(v11 + 112);
    v68 = 0;
    if ( v20 )
    {
      v21 = v20;
      v22 = *(NTSTATUS (__stdcall **)(BCRYPT_HANDLE, LPCWSTR, PUCHAR, ULONG, ULONG *, ULONG))(*(_QWORD *)(v11 + 168)
                                                                                            + 16LL);
    }
    else
    {
      v21 = *(_QWORD *)(v11 + 104);
      v22 = BCryptGetProperty;
    }
    Size = (size_t)v22;
    v23 = wcscmp_0(a3, L"Algorithm Name");
    v25 = *(_QWORD *)(v11 + 64);
    if ( !v23 )
    {
      v26 = *(_WORD **)v25;
      v27 = 1;
      v10 = 0;
      do
        ++v14;
      while ( v26[v14] );
LABEL_38:
      v28 = 2 * v14 + 2;
LABEL_39:
      LODWORD(Size) = v28;
LABEL_163:
      v31 = 0;
LABEL_164:
      v32 = 0;
      goto LABEL_165;
    }
    if ( *(_DWORD *)(v25 + 8) == 1 )
    {
      if ( !wcscmp_0(a3, L"Chaining Mode") )
      {
        if ( v20 || (Property = KspCheckStrongKeyAndUnprotect(v11, v16), v10 = Property, Property >= 0) )
        {
          Property = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned int *, _QWORD, ULONG *, _DWORD))(*(_QWORD *)(v11 + 168) + 16LL))(
                       *(_QWORD *)(v11 + 112),
                       L"ChainingMode",
                       a4,
                       cbOutput,
                       pcbResult,
                       0);
          v10 = Property;
          if ( Property >= 0 )
            goto LABEL_256;
          v12 = 1144;
        }
        else
        {
          v12 = 1129;
        }
        goto LABEL_45;
      }
      v26 = 0;
      if ( !wcscmp_0(a3, L"AuthTagLength") )
      {
        Property = BCryptGetProperty(*(BCRYPT_HANDLE *)(v11 + 88), L"AuthTagLength", (PUCHAR)a4, cbOutput, pcbResult, 0);
        v10 = Property;
        if ( Property >= 0 )
          goto LABEL_256;
        v12 = 1161;
        goto LABEL_45;
      }
    }
    else
    {
      v26 = 0;
    }
    if ( !wcscmp_0(a3, L"Block Length") )
    {
      v30 = *(_QWORD *)(v11 + 64);
      if ( *(_DWORD *)(v30 + 32) == 196609 )
      {
        v27 = 2;
        v31 = 0;
        v28 = 4;
        v32 = 0;
LABEL_55:
        LODWORD(Size) = v28;
        v10 = 0;
LABEL_165:
        v37 = v67;
        goto LABEL_166;
      }
      if ( *(_DWORD *)(v30 + 8) == 1 )
      {
        Property = BCryptGetProperty(*(BCRYPT_HANDLE *)(v11 + 88), L"BlockLength", (PUCHAR)a4, cbOutput, pcbResult, 0);
        v10 = Property;
        if ( Property >= 0 )
          goto LABEL_256;
        v12 = 1184;
        goto LABEL_45;
      }
      v12 = 1191;
LABEL_60:
      v10 = -2146893783;
      v13 = 2148073513LL;
      goto LABEL_5;
    }
    if ( !wcscmp_0(a3, L"Virtual Iso") )
    {
      v27 = 29;
LABEL_63:
      v28 = 4;
LABEL_64:
      v31 = v68;
      v32 = (int)v68;
      goto LABEL_55;
    }
    if ( !wcscmp_0(a3, L"Per Boot Key") )
    {
      v27 = 30;
      goto LABEL_63;
    }
    if ( !wcscmp_0(a3, L"Export Policy") )
    {
      v27 = 3;
      goto LABEL_63;
    }
    if ( !wcscmp_0(a3, L"Key Usage") )
    {
      v27 = 5;
      goto LABEL_63;
    }
    if ( !wcscmp_0(a3, L"Key Type") )
    {
      v27 = 22;
      goto LABEL_63;
    }
    if ( !wcscmp_0(a3, L"HWND Handle") )
    {
      v28 = *(_DWORD *)(v11 + 408);
      v10 = 0;
      LODWORD(Size) = v28;
      if ( v28 )
      {
        v27 = 17;
        goto LABEL_163;
      }
      v12 = 1227;
LABEL_76:
      v10 = -2146893807;
      v13 = 2148073489LL;
      goto LABEL_5;
    }
    if ( !wcscmp_0(a3, L"UI Policy") )
    {
      v28 = *(_DWORD *)(v11 + 424);
      v10 = 0;
      LODWORD(Size) = v28;
      if ( v28 )
      {
        v27 = 12;
        goto LABEL_163;
      }
      v12 = 1238;
      goto LABEL_76;
    }
    if ( !wcscmp_0(a3, L"Use Context") )
    {
      v33 = *(_QWORD *)(v11 + 504);
      v10 = 0;
      if ( v33 )
      {
        do
          ++v14;
        while ( *(_WORD *)(v33 + 2 * v14) );
        v28 = 2 * v14 + 2;
        LODWORD(Size) = v28;
        if ( 2 * (_DWORD)v14 != -2 )
        {
          v27 = 21;
          goto LABEL_163;
        }
      }
      v12 = 1257;
      goto LABEL_76;
    }
    if ( !wcscmp_0(a3, L"MSSP/UI Password Hash Alg") )
    {
      v27 = 23;
      goto LABEL_63;
    }
    if ( !wcscmp_0(a3, L"MSSP/UI Internal Flags") )
    {
      v27 = 18;
      goto LABEL_63;
    }
    if ( !wcscmp_0(a3, L"Modified") )
    {
      v27 = 6;
      v28 = 8;
      goto LABEL_64;
    }
    if ( !wcscmp_0(a3, L"Length") )
    {
      v10 = 0;
      if ( *(_DWORD *)(*(_QWORD *)(v11 + 64) + 96LL) )
      {
        v27 = 7;
        v28 = 4;
        goto LABEL_39;
      }
      v12 = 1283;
      goto LABEL_60;
    }
    if ( !wcscmp_0(a3, L"Lengths") )
    {
      v10 = 0;
      if ( *(_DWORD *)(*(_QWORD *)(v11 + 64) + 96LL) )
      {
        v27 = 8;
        v28 = 16;
        goto LABEL_39;
      }
      v12 = 1296;
      goto LABEL_60;
    }
    if ( !wcscmp_0(a3, L"Name") )
    {
      v34 = *(_QWORD *)(v11 + 8);
      v10 = 0;
      if ( v34 )
      {
        v27 = 9;
        do
          ++v14;
        while ( *(_WORD *)(v34 + 2 * v14) );
        goto LABEL_38;
      }
      v12 = 1310;
      goto LABEL_60;
    }
    if ( !wcscmp_0(a3, L"Ephemeral Name") )
    {
      v10 = 0;
      if ( !*(_QWORD *)(v11 + 8) )
      {
        if ( !*(_DWORD *)(v11 + 568) )
        {
          v10 = -2146893779;
          v12 = 1325;
          v13 = 2148073517LL;
          goto LABEL_5;
        }
        Property = CreateEphemeralKeyName(v11);
        v10 = Property;
        if ( Property )
        {
          v12 = 1332;
          goto LABEL_45;
        }
        v10 = 0;
      }
      v27 = 33;
      do
        ++v14;
      while ( *(_WORD *)(*(_QWORD *)(v11 + 8) + 2 * v14) );
      v31 = v68;
      v28 = 2 * v14 + 2;
      LODWORD(Size) = v28;
      v32 = (int)v68;
      goto LABEL_165;
    }
    if ( !v72 )
    {
      RtlAcquireResourceShared((PRTL_RESOURCE)(v11 + 304), 1u);
      if ( !*(_QWORD *)(v11 + 224) )
      {
        v10 = -2146893813;
        v17 = 1350;
        v18 = 2148073483LL;
        goto LABEL_26;
      }
      SecurityOnKeyFile = GetSecurityOnKeyFile(v11, v16, &v70, &v69);
      v10 = SecurityOnKeyFile;
      if ( SecurityOnKeyFile )
      {
        DebugTraceError(
          SecurityOnKeyFile,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
          1362);
        v36 = v70;
LABEL_243:
        RtlReleaseResource((PRTL_RESOURCE)(v11 + 304));
        goto LABEL_254;
      }
      v37 = v70;
      v27 = 11;
      v28 = v69;
      v10 = 0;
      v31 = v68;
      LODWORD(Size) = v69;
      v32 = 1;
      v67 = v70;
LABEL_166:
      *pcbResult = v28;
      if ( !a4 )
        goto LABEL_241;
      if ( cbOutput < v28 )
      {
        v10 = -2146893784;
        goto LABEL_241;
      }
      if ( v27 > 0x11 )
      {
        if ( v27 <= 0x19 )
        {
          if ( v27 == 25 )
          {
            v49 = *(const void **)(v11 + 544);
          }
          else
          {
            v55 = v27 - 18;
            if ( !v55 )
            {
              PasswordHashAlg = *(_DWORD *)(v11 + 428);
              goto LABEL_190;
            }
            v56 = v55 - 3;
            if ( v56 )
            {
              v57 = v56 - 1;
              if ( !v57 )
              {
                *a4 = *(_DWORD *)(v11 + 32) != 0 ? 0x20 : 0;
                goto LABEL_240;
              }
              v58 = v57 - 1;
              if ( !v58 )
              {
                PasswordHashAlg = MyCryptProtectGetPasswordHashAlg(v11, pcbResult, v24, v31);
                goto LABEL_190;
              }
              if ( v58 != 1 )
                goto LABEL_230;
              v49 = *(const void **)(v11 + 512);
            }
            else
            {
              v49 = *(const void **)(v11 + 504);
            }
          }
          goto LABEL_238;
        }
        v59 = v27 - 26;
        if ( !v59 )
        {
          v49 = *(const void **)(v11 + 552);
          goto LABEL_238;
        }
        v60 = v59 - 3;
        if ( !v60 )
        {
          PasswordHashAlg = *(_DWORD *)(v11 + 144);
          goto LABEL_190;
        }
        v61 = v60 - 1;
        if ( !v61 )
        {
          PasswordHashAlg = *(_DWORD *)(v11 + 148);
          goto LABEL_190;
        }
        v62 = v61 - 2;
        if ( !v62 )
        {
          v70 = 0;
          LODWORD(v69) = 0;
          KeyLengthsFromBCrypt = LookupKeyPropertyByNumber(
                                   v11,
                                   32,
                                   (unsigned int)&Src,
                                   (unsigned int)&v70,
                                   (__int64)&v69);
          v10 = KeyLengthsFromBCrypt;
          if ( !KeyLengthsFromBCrypt )
          {
            v63 = (unsigned int)v69;
            v49 = v70;
LABEL_239:
            memcpy_0(a4, v49, v63);
            goto LABEL_240;
          }
          v47 = 1749;
          goto LABEL_194;
        }
        if ( v62 != 1 )
          goto LABEL_230;
      }
      else
      {
        if ( v27 == 17 )
        {
          v49 = (const void *)(v11 + 400);
LABEL_238:
          v63 = v28;
          goto LABEL_239;
        }
        if ( v27 <= 8 )
        {
          if ( v27 != 8 )
          {
            v41 = v27 - 1;
            if ( v41 )
            {
              v42 = v41 - 1;
              if ( !v42 )
              {
                PasswordHashAlg = (unsigned int)(*(_DWORD *)(v11 + 28) + 7) >> 3;
                goto LABEL_190;
              }
              v43 = v42 - 1;
              if ( !v43 )
              {
                PasswordHashAlg = *(_DWORD *)(v11 + 36);
                goto LABEL_190;
              }
              v44 = v43 - 2;
              if ( !v44 )
              {
                PasswordHashAlg = *(_DWORD *)(v11 + 40);
                goto LABEL_190;
              }
              v45 = v44 - 1;
              if ( v45 )
              {
                if ( v45 == 1 )
                {
                  PasswordHashAlg = *(_DWORD *)(v11 + 28);
LABEL_190:
                  *a4 = PasswordHashAlg;
                  goto LABEL_240;
                }
LABEL_230:
                v10 = -2146893779;
                goto LABEL_241;
              }
              if ( !v32 )
              {
                RtlAcquireResourceShared((PRTL_RESOURCE)(v11 + 304), 1u);
                v32 = 1;
              }
              if ( (unsigned int)LookupKeyProperty(v11, a3, &Src, &Size) )
              {
                v10 = -2146893807;
                v47 = 1682;
                v48 = 2148073489LL;
              }
              else
              {
                if ( (_DWORD)Size == 8 )
                {
                  *(_QWORD *)a4 = *(_QWORD *)Src;
LABEL_240:
                  v10 = 0;
LABEL_241:
                  if ( v32 )
                    goto LABEL_242;
LABEL_253:
                  v36 = v67;
LABEL_254:
                  if ( v36 )
                    MSCryptFree(v36);
                  goto LABEL_256;
                }
                v10 = -2146893779;
                v47 = 1689;
                v48 = 2148073517LL;
              }
LABEL_204:
              DebugTraceError(v48, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", v47);
              goto LABEL_241;
            }
            v49 = v26;
            goto LABEL_238;
          }
          KeyLengthsFromBCrypt = GetKeyLengthsFromBCrypt(v11, a4, cbOutput, v31);
          v10 = KeyLengthsFromBCrypt;
          if ( !KeyLengthsFromBCrypt )
            goto LABEL_240;
          v47 = 1706;
LABEL_194:
          v48 = KeyLengthsFromBCrypt;
          goto LABEL_204;
        }
        v51 = v27 - 9;
        if ( v51 )
        {
          v52 = v51 - 2;
          if ( v52 )
          {
            v53 = v52 - 1;
            if ( !v53 )
            {
              memcpy_0(a4, *(const void **)(v11 + 416), v28);
              if ( cbOutput >= 0x14 )
              {
                if ( (*(_BYTE *)(v11 + 428) & 1) != 0 )
                  a4[1] = 2;
                if ( (*(_BYTE *)(v11 + 428) & 0x20) != 0 && (*(_BYTE *)(*(_QWORD *)(v11 + 416) + 4LL) & 7) == 0 )
                  a4[1] = 9;
                goto LABEL_240;
              }
              v10 = -2146893784;
              v47 = 1640;
              v48 = 2148073512LL;
              goto LABEL_204;
            }
            v54 = v53 - 3;
            if ( v54 )
            {
              if ( v54 != 1 )
                goto LABEL_230;
              v49 = v31;
            }
            else
            {
              v49 = *(const void **)(v11 + 16);
            }
          }
          else
          {
            v49 = v37;
          }
          goto LABEL_238;
        }
      }
      v49 = *(const void **)(v11 + 8);
      goto LABEL_238;
    }
    v10 = 0;
    if ( !wcscmp_0(a3, L"Unique Name") )
    {
      v38 = *(_QWORD *)(v11 + 16);
      if ( v38 )
      {
        v27 = 15;
        do
          ++v14;
        while ( *(_WORD *)(v38 + 2 * v14) );
        goto LABEL_38;
      }
      v12 = 1376;
      goto LABEL_60;
    }
    if ( !wcscmp_0(a3, L"Algorithm Group") )
    {
      v27 = 16;
      v31 = *(const void **)(*(_QWORD *)(v11 + 64) + 88LL);
      do
        ++v14;
      while ( *((_WORD *)v31 + v14) );
      v28 = 2 * v14 + 2;
      LODWORD(Size) = v28;
      goto LABEL_164;
    }
    if ( !wcscmp_0(a3, L"SmartCardKeyCertificate") )
    {
      v28 = *(_DWORD *)(v11 + 520);
      LODWORD(Size) = v28;
      if ( v28 )
      {
        v27 = 24;
        goto LABEL_163;
      }
      v12 = 1396;
      goto LABEL_76;
    }
    if ( !wcscmp_0(a3, L"SignatureLength") )
    {
      Property = ((__int64 (__fastcall *)(__int64, const wchar_t *, unsigned int *, _QWORD, ULONG *, _DWORD))Size)(
                   v21,
                   L"SignatureLength",
                   a4,
                   cbOutput,
                   pcbResult,
                   0);
      v10 = Property;
      if ( Property >= 0 )
        goto LABEL_256;
      v12 = 1412;
    }
    else if ( !wcscmp_0(a3, L"PublicKeyLength") )
    {
      Property = ((__int64 (__fastcall *)(__int64, const wchar_t *, unsigned int *, _QWORD, ULONG *, _DWORD))Size)(
                   v21,
                   L"PublicKeyLength",
                   a4,
                   cbOutput,
                   pcbResult,
                   0);
      v10 = Property;
      if ( Property >= 0 )
        goto LABEL_256;
      v12 = 1428;
    }
    else if ( !wcscmp_0(a3, L"ECCParameters") )
    {
      if ( *(_QWORD *)(v11 + 552) )
      {
        v28 = *(_DWORD *)(v11 + 560);
        LODWORD(Size) = v28;
        if ( v28 )
        {
          v27 = 26;
          goto LABEL_163;
        }
        v12 = 1447;
        goto LABEL_76;
      }
      Property = ((__int64 (__fastcall *)(__int64, const wchar_t *, unsigned int *, _QWORD, ULONG *, _DWORD))Size)(
                   v21,
                   L"ECCParameters",
                   a4,
                   cbOutput,
                   pcbResult,
                   0);
      v10 = Property;
      if ( Property >= 0 )
        goto LABEL_256;
      v12 = 1463;
    }
    else if ( !wcscmp_0(a3, L"ECCCurveNameList") )
    {
      Property = SerializeCurveNameList(*(BCRYPT_HANDLE *)(v11 + 88));
      v10 = Property;
      if ( Property >= 0 )
        goto LABEL_256;
      v12 = 1475;
    }
    else
    {
      if ( !wcscmp_0(a3, L"ECCCurveName") )
      {
        v39 = *(_QWORD *)(v11 + 544);
        if ( v39 )
        {
          do
            ++v14;
          while ( *(_WORD *)(v39 + 2 * v14) );
          v28 = 2 * v14 + 2;
          LODWORD(Size) = v28;
          if ( 2 * (_DWORD)v14 != -2 )
          {
            v27 = 25;
            goto LABEL_163;
          }
        }
        v12 = 1496;
        goto LABEL_76;
      }
      if ( !wcscmp_0(a3, L"CreatorProcessName") )
      {
        LODWORD(v69) = 0;
        if ( !(unsigned int)LookupKeyPropertyByNumber(v11, 32, (unsigned int)&v72, (unsigned int)&v70, (__int64)&v69) )
        {
          v28 = v69;
          v27 = v40;
          LODWORD(Size) = v69;
          if ( (_DWORD)v69 )
            goto LABEL_163;
        }
        v12 = 1518;
        goto LABEL_76;
      }
      if ( wcscmp_0(a3, L"ParameterSetName") )
      {
        if ( !wcscmp_0(a3, L"KEMSharedSecretLength") || !wcscmp_0(a3, L"KEMCiphertextLength") )
        {
          v64 = ((__int64 (__fastcall *)(__int64, const wchar_t *, unsigned int *, _QWORD, ULONG *, _DWORD))Size)(
                  v21,
                  a3,
                  a4,
                  cbOutput,
                  pcbResult,
                  0);
          v10 = v64;
          if ( v64 >= 0 )
            goto LABEL_256;
          DebugTraceError(
            (unsigned int)v64,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
            1551);
          goto LABEL_253;
        }
        v12 = 1558;
        goto LABEL_60;
      }
      Property = ((__int64 (__fastcall *)(__int64, const wchar_t *, unsigned int *, _QWORD, ULONG *, _DWORD))Size)(
                   v21,
                   L"ParameterSetName",
                   a4,
                   cbOutput,
                   pcbResult,
                   0);
      v10 = Property;
      if ( Property >= 0 )
        goto LABEL_256;
      v12 = 1534;
    }
LABEL_45:
    v13 = (unsigned int)Property;
    goto LABEL_5;
  }
  v10 = -2146893786;
  DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", 971);
  return v10;
}

```

## disassembly

```asm
0x180032c10  push    rbp
0x180032c12  push    rbx
0x180032c13  push    rsi
0x180032c14  push    rdi
0x180032c15  push    r12
0x180032c17  push    r13
0x180032c19  push    r14
0x180032c1b  push    r15
0x180032c1d  lea     rbp, [rsp-7]
0x180032c22  sub     rsp, 98h
0x180032c29  xor     r12d, r12d
0x180032c2c  mov     rbx, rdx
0x180032c2f  xor     edx, edx
0x180032c31  mov     dword ptr [rbp+3Fh+Size], r12d
0x180032c35  mov     [rbp+3Fh+Src], r12
0x180032c39  mov     rsi, r9
0x180032c3c  mov     [rbp+3Fh+var_80], r12
0x180032c40  mov     r14, r8
0x180032c43  mov     [rbp+3Fh+var_68], r12
0x180032c47  mov     dword ptr [rbp+3Fh+var_70], r12d
0x180032c4b  call    KspValidateAndLockProvider
0x180032c50  mov     [rbp+3Fh+var_50], rax
0x180032c54  test    rax, rax
0x180032c57  jnz     short loc_180032C81
0x180032c59  mov     r9d, 3CBh
0x180032c5f  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180032c66  lea     rdx, aStatus; "Status"
0x180032c6d  mov     ecx, 80090026h
0x180032c72  mov     ebx, 80090026h
0x180032c77  call    DebugTraceError
0x180032c7c  jmp     loc_1800339E9
0x180032c81  mov     rcx, rbx
0x180032c84  call    KspValidateKeyHandle
0x180032c89  mov     rdi, rax
0x180032c8c  test    rax, rax
0x180032c8f  jnz     short loc_180032CB9
0x180032c91  mov     ebx, 80090026h
0x180032c96  mov     r9d, 3D4h
0x180032c9c  mov     ecx, 80090026h
0x180032ca1  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180032ca8  lea     rdx, aStatus; "Status"
0x180032caf  call    DebugTraceError
0x180032cb4  jmp     loc_1800339D5
0x180032cb9  test    r14, r14
0x180032cbc  jnz     short loc_180032CD0
0x180032cbe  mov     r9d, 3DBh
0x180032cc4  mov     ebx, 80090027h
0x180032cc9  mov     ecx, 80090027h
0x180032cce  jmp     short loc_180032CA1
0x180032cd0  or      r15, 0FFFFFFFFFFFFFFFFh
0x180032cd4  mov     rax, r15
0x180032cd7  inc     rax
0x180032cda  cmp     [r14+rax*2], r12w
0x180032cdf  jnz     short loc_180032CD7
0x180032ce1  cmp     rax, 40h ; '@'
0x180032ce5  jbe     short loc_180032CEF
0x180032ce7  mov     r9d, 3E1h
0x180032ced  jmp     short loc_180032CC4
0x180032cef  mov     r12, [rbp+3Fh+arg_28]
0x180032cf3  xor     r13d, r13d
0x180032cf6  test    r12, r12
0x180032cf9  jnz     short loc_180032D03
0x180032cfb  mov     r9d, 3E8h
0x180032d01  jmp     short loc_180032CC4
0x180032d03  lea     rdx, aSecurityDescr; "Security Descr"
0x180032d0a  mov     rcx, r14; String1
0x180032d0d  call    wcscmp_0
0x180032d12  mov     ebx, [rbp+3Fh+arg_30]
0x180032d15  mov     [rbp+3Fh+var_58], eax
0x180032d18  test    eax, eax
0x180032d1a  jnz     short loc_180032D46
0x180032d1c  and     ebx, 0FFFFFFBFh
0x180032d1f  jnz     short loc_180032D36
0x180032d21  mov     r9d, 3F4h
0x180032d27  mov     ebx, 80090009h
0x180032d2c  mov     ecx, 80090009h
0x180032d31  jmp     loc_180032CA1
0x180032d36  test    ebx, 0FFFFFFE0h
0x180032d3c  jz      short loc_180032D56
0x180032d3e  mov     r9d, 401h
0x180032d44  jmp     short loc_180032D27
0x180032d46  test    ebx, 0BFFFFFBFh
0x180032d4c  jz      short loc_180032D56
0x180032d4e  mov     r9d, 40Bh
0x180032d54  jmp     short loc_180032D27
0x180032d56  bt      ebx, 1Eh
0x180032d5a  jnb     loc_180032DEB
0x180032d60  lea     rcx, [rdi+130h]; Resource
0x180032d67  mov     dl, 1; Wait
0x180032d69  call    cs:__imp_RtlAcquireResourceShared
0x180032d70  nop     dword ptr [rax+rax+00h]
0x180032d75  lea     r9, [rbp+3Fh+Size]
0x180032d79  mov     rdx, r14
0x180032d7c  lea     r8, [rbp+3Fh+Src]
0x180032d80  mov     rcx, rdi
0x180032d83  call    LookupKeyProperty
0x180032d88  xor     r15d, r15d
0x180032d8b  test    eax, eax
0x180032d8d  jz      short loc_180032DB7
0x180032d8f  mov     ebx, 80090011h
0x180032d94  mov     r9d, 421h
0x180032d9a  mov     ecx, 80090011h
0x180032d9f  lea     rdx, aStatus; "Status"
0x180032da6  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180032dad  call    DebugTraceError
0x180032db2  jmp     loc_1800338D9
0x180032db7  mov     eax, dword ptr [rbp+3Fh+Size]
0x180032dba  mov     [r12], eax
0x180032dbe  test    rsi, rsi
0x180032dc1  jnz     short loc_180032DCB
0x180032dc3  mov     ebx, r15d
0x180032dc6  jmp     loc_1800338D9
0x180032dcb  cmp     [rbp+3Fh+cbOutput], eax
0x180032dce  jnb     short loc_180032DDA
0x180032dd0  mov     ebx, 80090028h
0x180032dd5  jmp     loc_1800338D9
0x180032dda  mov     rdx, [rbp+3Fh+Src]; Src
0x180032dde  mov     r8, rax; Size
0x180032de1  mov     rcx, rsi; void *
0x180032de4  call    memcpy_0
0x180032de9  jmp     short loc_180032DC3
0x180032deb  mov     r12, [rdi+70h]
0x180032def  mov     [rbp+3Fh+var_78], r13
0x180032df3  test    r12, r12
0x180032df6  jz      short loc_180032E08
0x180032df8  mov     rax, [rdi+0A8h]
0x180032dff  mov     r13, r12
0x180032e02  mov     rax, [rax+10h]
0x180032e06  jmp     short loc_180032E13
0x180032e08  mov     r13, [rdi+68h]
0x180032e0c  mov     rax, cs:__imp_BCryptGetProperty
0x180032e13  lea     rdx, aAlgorithmName; "Algorithm Name"
0x180032e1a  mov     [rbp+3Fh+Size], rax
0x180032e1e  mov     rcx, r14; String1
0x180032e21  call    wcscmp_0
0x180032e26  mov     rcx, [rdi+40h]
0x180032e2a  test    eax, eax
0x180032e2c  jnz     short loc_180032E52
0x180032e2e  mov     r12, [rcx]
0x180032e31  mov     eax, 1
0x180032e36  xor     ebx, ebx
0x180032e38  inc     r15
0x180032e3b  cmp     [r12+r15*2], bx
0x180032e40  jnz     short loc_180032E38
0x180032e42  lea     ecx, ds:2[r15*2]
0x180032e4a  mov     dword ptr [rbp+3Fh+Size], ecx
0x180032e4d  jmp     loc_1800335D1
0x180032e52  cmp     dword ptr [rcx+8], 1
0x180032e56  jnz     loc_180032F2D
0x180032e5c  lea     rdx, aChainingMode; "Chaining Mode"
0x180032e63  mov     rcx, r14; String1
0x180032e66  call    wcscmp_0
0x180032e6b  test    eax, eax
0x180032e6d  jnz     short loc_180032ED6
0x180032e6f  xor     r14d, r14d
0x180032e72  test    r12, r12
0x180032e75  jnz     short loc_180032E94
0x180032e77  mov     edx, ebx
0x180032e79  mov     rcx, rdi
0x180032e7c  call    KspCheckStrongKeyAndUnprotect
0x180032e81  mov     ebx, eax
0x180032e83  test    eax, eax
0x180032e85  jns     short loc_180032E94
0x180032e87  mov     r9d, 469h
0x180032e8d  mov     ecx, eax
0x180032e8f  jmp     loc_180032CA1
0x180032e94  mov     rax, [rdi+0A8h]
0x180032e9b  mov     r8, rsi
0x180032e9e  mov     rdx, [rbp+3Fh+arg_28]
0x180032ea2  mov     r9d, [rbp+3Fh+cbOutput]
0x180032ea6  mov     rcx, [rdi+70h]
0x180032eaa  mov     rax, [rax+10h]
0x180032eae  mov     [rsp+0D0h+dwFlags], r14d
0x180032eb3  mov     [rsp+0D0h+pcbResult], rdx
0x180032eb8  lea     rdx, aChainingmode; "ChainingMode"
0x180032ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ec4  mov     ebx, eax
0x180032ec6  test    eax, eax
0x180032ec8  jns     loc_1800339D5
0x180032ece  mov     r9d, 478h
0x180032ed4  jmp     short loc_180032E8D
0x180032ed6  lea     rdx, aAuthtaglength; "AuthTagLength"
0x180032edd  mov     rcx, r14; String1
0x180032ee0  call    wcscmp_0
0x180032ee5  xor     r12d, r12d
0x180032ee8  test    eax, eax
0x180032eea  jnz     short loc_180032F30
0x180032eec  mov     rdx, [rbp+3Fh+arg_28]
0x180032ef0  mov     r8, rsi; pbOutput
0x180032ef3  mov     r9d, [rbp+3Fh+cbOutput]; cbOutput
0x180032ef7  mov     rcx, [rdi+58h]; hObject
0x180032efb  mov     [rsp+0D0h+dwFlags], r12d; dwFlags
0x180032f00  mov     [rsp+0D0h+pcbResult], rdx; pcbResult
0x180032f05  lea     rdx, aAuthtaglength; "AuthTagLength"
0x180032f0c  call    cs:__imp_BCryptGetProperty
0x180032f13  nop     dword ptr [rax+rax+00h]
0x180032f18  mov     ebx, eax
0x180032f1a  test    eax, eax
0x180032f1c  jns     loc_1800339D5
0x180032f22  mov     r9d, 489h
0x180032f28  jmp     loc_180032E8D
0x180032f2d  xor     r12d, r12d
0x180032f30  lea     rdx, aBlockLength; "Block Length"
0x180032f37  mov     rcx, r14; String1
0x180032f3a  call    wcscmp_0
0x180032f3f  xor     edx, edx
0x180032f41  test    eax, eax
0x180032f43  jnz     short loc_180032FC3
0x180032f45  mov     rcx, [rdi+40h]
0x180032f49  cmp     dword ptr [rcx+20h], 30001h
0x180032f50  jnz     short loc_180032F68
0x180032f52  lea     eax, [rdx+2]
0x180032f55  mov     r9d, edx
0x180032f58  lea     ecx, [rdx+4]
0x180032f5b  mov     r15d, edx
0x180032f5e  mov     dword ptr [rbp+3Fh+Size], ecx
0x180032f61  xor     ebx, ebx
0x180032f63  jmp     loc_1800335D7
0x180032f68  cmp     dword ptr [rcx+8], 1
0x180032f6c  jnz     short loc_180032FAE
0x180032f6e  mov     r9d, [rbp+3Fh+cbOutput]; cbOutput
0x180032f72  mov     r8, rsi; pbOutput
0x180032f75  mov     rcx, [rdi+58h]; hObject
0x180032f79  mov     [rsp+0D0h+dwFlags], edx; dwFlags
0x180032f7d  mov     rdx, [rbp+3Fh+arg_28]
0x180032f81  mov     [rsp+0D0h+pcbResult], rdx; pcbResult
0x180032f86  lea     rdx, aBlocklength; "BlockLength"
0x180032f8d  call    cs:__imp_BCryptGetProperty
0x180032f94  nop     dword ptr [rax+rax+00h]
0x180032f99  mov     ebx, eax
0x180032f9b  test    eax, eax
0x180032f9d  jns     loc_1800339D5
0x180032fa3  mov     r9d, 4A0h
0x180032fa9  jmp     loc_180032E8D
0x180032fae  mov     r9d, 4A7h
0x180032fb4  mov     ebx, 80090029h
0x180032fb9  mov     ecx, 80090029h
0x180032fbe  jmp     loc_180032CA1
0x180032fc3  lea     rdx, aVirtualIso; "Virtual Iso"
0x180032fca  mov     rcx, r14; String1
0x180032fcd  call    wcscmp_0
0x180032fd2  test    eax, eax
0x180032fd4  jnz     short loc_180032FEC
0x180032fd6  mov     eax, 1Dh
0x180032fdb  mov     ecx, 4
0x180032fe0  mov     r9, [rbp+3Fh+var_78]
0x180032fe4  mov     r15d, r9d
0x180032fe7  jmp     loc_180032F5E
0x180032fec  lea     rdx, aPerBootKey; "Per Boot Key"
0x180032ff3  mov     rcx, r14; String1
0x180032ff6  call    wcscmp_0
0x180032ffb  test    eax, eax
0x180032ffd  jnz     short loc_180033006
0x180032fff  mov     eax, 1Eh
0x180033004  jmp     short loc_180032FDB
0x180033006  lea     rdx, aExportPolicy; "Export Policy"
0x18003300d  mov     rcx, r14; String1
0x180033010  call    wcscmp_0
0x180033015  test    eax, eax
0x180033017  jnz     short loc_180033020
0x180033019  mov     eax, 3
0x18003301e  jmp     short loc_180032FDB
0x180033020  lea     rdx, aKeyUsage; "Key Usage"
0x180033027  mov     rcx, r14; String1
0x18003302a  call    wcscmp_0
0x18003302f  test    eax, eax
0x180033031  jnz     short loc_18003303A
0x180033033  mov     eax, 5
0x180033038  jmp     short loc_180032FDB
0x18003303a  lea     rdx, aKeyType; "Key Type"
0x180033041  mov     rcx, r14; String1
0x180033044  call    wcscmp_0
0x180033049  test    eax, eax
0x18003304b  jnz     short loc_180033054
0x18003304d  mov     eax, 16h
0x180033052  jmp     short loc_180032FDB
0x180033054  lea     rdx, aHwndHandle; "HWND Handle"
0x18003305b  mov     rcx, r14; String1
0x18003305e  call    wcscmp_0
0x180033063  test    eax, eax
0x180033065  jnz     short loc_180033095
0x180033067  mov     ecx, [rdi+198h]
0x18003306d  xor     ebx, ebx
0x18003306f  mov     dword ptr [rbp+3Fh+Size], ecx
0x180033072  test    ecx, ecx
0x180033074  jnz     short loc_18003308B
0x180033076  mov     r9d, 4CBh
0x18003307c  mov     ebx, 80090011h
0x180033081  mov     ecx, 80090011h
0x180033086  jmp     loc_180032CA1
0x18003308b  mov     eax, 11h
0x180033090  jmp     loc_1800335D1
0x180033095  lea     rdx, aUiPolicy; "UI Policy"
0x18003309c  mov     rcx, r14; String1
0x18003309f  call    wcscmp_0
0x1800330a4  test    eax, eax
0x1800330a6  jnz     short loc_1800330C9
0x1800330a8  mov     ecx, [rdi+1A8h]
0x1800330ae  xor     ebx, ebx
0x1800330b0  mov     dword ptr [rbp+3Fh+Size], ecx
  ... truncated ...
```
