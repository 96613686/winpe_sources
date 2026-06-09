# CCOMComponentRegistrar::ImportComponent(ushort const *,ushort const *,__MIDL___MIDL_itf_registrar_0000_0000_0001)

- ea: `0x18002e660`
- end: `0x18002f041`
- name: `?ImportComponent@CCOMComponentRegistrar@@UEAAJPEBG0W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z`
- size: `2529`
- prototype: `HRESULT __fastcall(__int64, const unsigned __int16 *, const OLECHAR *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180001e60`
- `0x180014ec8`
- `0x18002b3a4`
- `0x18002e660`
- `0x18002f750`
- `0x180055822`
- `0x18005583a`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e8ad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e8ad`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002e765`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002e765`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002e7f1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002e7f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e85f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e85f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e86e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e86e`
- `CLBCatQ!CLSIDFromStringByBitness` at `0x18002ea18`
- `CLBCatQ!CLSIDFromStringByBitness` at `0x18002ea18`
- `CLBCatQ!ServerGetApplicationType` at `0x18002e9ee`
- `CLBCatQ!ServerGetApplicationType` at `0x18002e9ee`

## string_xrefs

- `0x18002e797`: `Software\Classes\CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall CCOMComponentRegistrar::ImportComponent(
        __int64 a1,
        const unsigned __int16 *a2,
        const OLECHAR *a3,
        unsigned int a4)
{
  HRESULT result; // eax
  bool v9; // zf
  HRESULT ApplicationType; // ebx
  int v11; // r8d
  __int64 v12; // rax
  __int64 v13; // r9
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+58h] [rbp-A8h] BYREF
  int v16; // [rsp+5Ch] [rbp-A4h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  int v18; // [rsp+68h] [rbp-98h] BYREF
  int v19; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  int v21; // [rsp+78h] [rbp-88h] BYREF
  int v22; // [rsp+7Ch] [rbp-84h] BYREF
  _QWORD *v23; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+88h] [rbp-78h] BYREF
  __int64 v25; // [rsp+90h] [rbp-70h] BYREF
  __int64 v26; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v27[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v28; // [rsp+B0h] [rbp-50h]
  int v29; // [rsp+B4h] [rbp-4Ch]
  struct _GUID v30; // [rsp+B8h] [rbp-48h] BYREF
  GUID pclsid; // [rsp+C8h] [rbp-38h] BYREF
  struct _GUID Buf1; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v33[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v34; // [rsp+100h] [rbp+0h]
  int v35; // [rsp+104h] [rbp+4h]
  int *v36; // [rsp+108h] [rbp+8h]
  int v37; // [rsp+110h] [rbp+10h]
  int v38; // [rsp+114h] [rbp+14h]
  int v39; // [rsp+118h] [rbp+18h]
  int v40; // [rsp+11Ch] [rbp+1Ch]
  __int64 v41; // [rsp+120h] [rbp+20h]
  int v42; // [rsp+128h] [rbp+28h]
  int v43; // [rsp+12Ch] [rbp+2Ch]
  __int64 v44; // [rsp+130h] [rbp+30h]
  OLECHAR sz[40]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR SubKey[24]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v47[480]; // [rsp+1C0h] [rbp+C0h] BYREF

  v21 = 3;
  ppv = 0;
  v14 = 0;
  v16 = 0;
  v15 = 0;
  v22 = 1;
  v25 = 0;
  v26 = 0;
  v23 = 0;
  v24 = 0;
  v18 = 0;
  v19 = 0;
  pclsid = 0;
  v30 = 0;
  Buf1 = 0;
  if ( !a2 || !a3 )
    return -2147024809;
  v33[0] = 0;
  v34 = 72;
  v28 = 72;
  v33[1] = 0;
  v35 = 16;
  v36 = 0;
  v37 = 0;
  v38 = 8;
  v39 = 19;
  v40 = 4;
  v41 = 0;
  v42 = 1;
  v43 = 1;
  v44 = 130;
  v27[0] = &v30;
  v27[1] = 0;
  v29 = 16;
  result = CLSIDFromString(a3, &pclsid);
  if ( result < 0 )
    return result;
  if ( a4 == 4096 )
    goto LABEL_13;
  if ( a4 )
  {
    if ( a4 == 3 )
      goto LABEL_20;
  }
  else
  {
    memset_0(sz, 0, 0x4Eu);
    wcscpy(SubKey, L"Software\\Classes\\CLSID\\");
    memset_0(v47, 0, 0x1D8u);
    v9 = *a3 == 123;
    hKey = 0;
    if ( v9 )
      result = StringCchCopyW(sz, 0x27u, a3);
    else
      result = StringFromGUID2(&pclsid, sz, 39);
    if ( result < 0 )
      return result;
    result = StringCchCatW(SubKey, 0x104u, sz);
    if ( result < 0 )
      return result;
    result = StringCchCatW(SubKey, 0x104u, L"\\InprocServer32");
    if ( result < 0 )
      return result;
    a4 = 1;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20119u, &hKey) )
    {
      RegCloseKey(hKey);
LABEL_13:
      a4 = 2;
    }
  }
  *(_DWORD *)(a1 + 168) = (a4 != 1) + 1;
  v18 = (a4 != 1) + 1;
  ApplicationType = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, &ppv);
  if ( ApplicationType < 0 )
    goto LABEL_78;
  ApplicationType = ResolveAppIdFromName((struct ISimpleTableDispenser *)ppv, a2, &v30, &Buf1);
  if ( ApplicationType < 0 )
    goto LABEL_78;
  if ( memcmp_0(&Buf1, &GUID_DefaultAppPartition, 0x10u) )
  {
    ApplicationType = -2146368432;
    goto LABEL_78;
  }
  ApplicationType = (*(__int64 (__fastcall **)(LPVOID, __int128 *, const struct _GUID *, _QWORD *, __int64, int, _DWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(
                      ppv,
                      &didCOMSERVICES,
                      &TID_APPLICATION,
                      v27,
                      1,
                      1,
                      0,
                      &v14);
  if ( ApplicationType < 0 )
    goto LABEL_78;
  ApplicationType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
  if ( ApplicationType < 0 )
    goto LABEL_78;
  ApplicationType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 32LL))(v14);
  if ( ApplicationType < 0 )
    goto LABEL_78;
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14) == -2146367487 )
  {
LABEL_20:
    ApplicationType = -2147024809;
    goto LABEL_78;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  ApplicationType = ServerGetApplicationType(ppv, &v30, &v19);
  if ( ApplicationType < 0 )
    goto LABEL_78;
  if ( (a4 & v19) != 0 )
  {
    if ( (int)CLSIDFromStringByBitness(a3, &pclsid, a4) >= 0 )
    {
      v33[0] = &pclsid;
      v11 = 10485760;
      v36 = &v18;
      if ( a4 != 1 )
        v11 = 12582912;
      ApplicationType = (*(__int64 (__fastcall **)(LPVOID, __int128 *, const struct _GUID *, _QWORD *, __int64, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                          ppv,
                          &didCOMSERVICES,
                          &tidCOMSERVICES_CLASSES,
                          v33,
                          3,
                          1,
                          v11,
                          &v14);
      if ( ApplicationType < 0 )
        goto LABEL_78;
      ApplicationType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
      if ( ApplicationType < 0 )
        goto LABEL_78;
      ApplicationType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 32LL))(v14);
      if ( ApplicationType < 0 )
        goto LABEL_78;
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14) == -2146367487 )
      {
        ApplicationType = -2146368495;
      }
      else
      {
        ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, _QWORD **))(*(_QWORD *)v14 + 64LL))(
                            v14,
                            9,
                            &v16,
                            &v15,
                            &v23);
        if ( ApplicationType >= 0 )
        {
          if ( !v23 )
            goto LABEL_45;
          v12 = *v23 - *(_QWORD *)&v30.Data1;
          if ( *v23 == *(_QWORD *)&v30.Data1 )
            v12 = v23[1] - *(_QWORD *)v30.Data4;
          if ( !v12 )
          {
LABEL_45:
            v13 = *(unsigned int *)(a1 + 168);
            LODWORD(hKey) = 0;
            ApplicationType = CCOMComponentRegistrar::IsClassLegacyConfigured(v23, ppv, &pclsid, v13, &hKey);
            if ( ApplicationType < 0 )
              goto LABEL_78;
            if ( !(_DWORD)hKey )
            {
              ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, __int64 *))(*(_QWORD *)v14 + 64LL))(
                                  v14,
                                  1,
                                  &v16,
                                  &v15,
                                  &v24);
              if ( ApplicationType >= 0 )
              {
                if ( v24 )
                {
                  ApplicationType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 128LL))(v14);
                  if ( ApplicationType >= 0 )
                  {
                    ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct _GUID *))(*(_QWORD *)v14 + 160LL))(
                                        v14,
                                        9,
                                        0,
                                        &v30);
                    if ( ApplicationType >= 0 )
                    {
                      ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, __int64 *))(*(_QWORD *)v14 + 64LL))(
                                          v14,
                                          3,
                                          &v16,
                                          &v15,
                                          &v25);
                      if ( ApplicationType >= 0 )
                      {
                        if ( !v25
                          || (ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 160LL))(
                                                  v14,
                                                  33),
                              ApplicationType >= 0) )
                        {
                          v21 = 3;
                          v22 = 1;
                          ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v14 + 160LL))(
                                              v14,
                                              20,
                                              0,
                                              &ulFalse);
                          if ( ApplicationType >= 0 )
                          {
                            ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                v14,
                                                18,
                                                0,
                                                &v21);
                            if ( ApplicationType >= 0 )
                            {
                              ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                  v14,
                                                  17,
                                                  0,
                                                  &v22);
                              if ( ApplicationType >= 0 )
                              {
                                ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v14 + 160LL))(
                                                    v14,
                                                    21,
                                                    0,
                                                    &ulFalse);
                                if ( ApplicationType >= 0 )
                                {
                                  ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v14 + 160LL))(
                                                      v14,
                                                      22,
                                                      0,
                                                      &ulTrue);
                                  if ( ApplicationType >= 0 )
                                  {
                                    ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v14 + 160LL))(
                                                        v14,
                                                        23,
                                                        0,
                                                        &ulFalse);
                                    if ( ApplicationType >= 0 )
                                    {
                                      ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v14 + 160LL))(
                                                          v14,
                                                          62,
                                                          0,
                                                          &ulTrue);
                                      if ( ApplicationType >= 0 )
                                      {
                                        ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v14 + 160LL))(
                                                            v14,
                                                            43,
                                                            0,
                                                            &ulFalse);
                                        if ( ApplicationType >= 0 )
                                        {
                                          ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v14 + 160LL))(
                                                              v14,
                                                              46,
                                                              0,
                                                              &ulTrue);
                                          if ( ApplicationType >= 0 )
                                          {
                                            ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v14 + 160LL))(
                                                                v14,
                                                                47,
                                                                0,
                                                                &ulFalse);
                                            if ( ApplicationType >= 0 )
                                            {
                                              ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v14 + 160LL))(
                                                                  v14,
                                                                  50,
                                                                  0,
                                                                  &ulFalse);
                                              if ( ApplicationType >= 0 )
                                              {
                                                ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v14 + 160LL))(
                                                                    v14,
                                                                    51,
                                                                    0,
                                                                    &ulFalse);
                                                if ( ApplicationType >= 0 )
                                                {
                                                  ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v14 + 160LL))(
                                                                      v14,
                                                                      52,
                                                                      0,
                                                                      &ulTrue);
                                                  if ( ApplicationType >= 0 )
                                                  {
                                                    ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v14 + 160LL))(
                                                                        v14,
                                                                        53,
                                                                        0,
                                                                        &ulIsoLevelSerializable);
                                                    if ( ApplicationType >= 0 )
                                                    {
                                                      ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v14 + 160LL))(
                                                                          v14,
                                                                          54,
                                                                          0,
                                                                          &ulFalse);
                                                      if ( ApplicationType >= 0 )
                                                      {
                                                        ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct _GUID *))(*(_QWORD *)v14 + 160LL))(
                                                                            v14,
                                                                            6,
                                                                            0,
                                                                            &Buf1);
                                                        if ( ApplicationType >= 0 )
                                                        {
                                                          ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, GUID *))(*(_QWORD *)v14 + 160LL))(
                                                                              v14,
                                                                              7,
                                                                              0,
                                                                              &GUID_NULL);
                                                          if ( ApplicationType >= 0 )
                                                          {
                                                            ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL))(
                                                                                v14,
                                                                                8,
                                                                                0,
                                                                                &v18);
                                                            if ( ApplicationType >= 0 )
                                                            {
                                                              ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, __int64 *))(*(_QWORD *)v14 + 64LL))(
                                                                                  v14,
                                                                                  2,
                                                                                  &v16,
                                                                                  &v15,
                                                                                  &v26);
                                                              if ( ApplicationType >= 0 )
                                                              {
                                                                if ( !v26
                                                                  || (ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 160LL))(
                                                                                          v14,
                                                                                          48),
                                                                      ApplicationType >= 0) )
                                                                {
                                                                  ApplicationType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 144LL))(v14);
                                                                  if ( ApplicationType >= 0 )
                                                                    ApplicationType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 96LL))(v14);
                                                                }
                                                              }
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
                else
                {
                  ApplicationType = -2146368510;
                }
              }
              goto LABEL_78;
            }
          }
          ApplicationType = -2146368508;
        }
      }
    }
    else
    {
      ApplicationType = -2146368450;
    }
  }
  else
  {
    ApplicationType = -2146368382;
  }
LABEL_78:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return ApplicationType;
}

```

## disassembly

```asm
0x18002e660  push    rbp
0x18002e662  push    rbx
0x18002e663  push    rsi
0x18002e664  push    rdi
0x18002e665  push    r12
0x18002e667  push    r13
0x18002e669  push    r14
0x18002e66b  push    r15
0x18002e66d  lea     rbp, [rsp-2B8h]
0x18002e675  sub     rsp, 3B8h
0x18002e67c  mov     rax, cs:__security_cookie
0x18002e683  xor     rax, rsp
0x18002e686  mov     [rbp+2F0h+var_50], rax
0x18002e68d  xor     r12d, r12d
0x18002e690  mov     [rsp+3F0h+var_378], 3
0x18002e698  mov     [rsp+3F0h+ppv], r12
0x18002e69d  xorps   xmm0, xmm0
0x18002e6a0  mov     [rsp+3F0h+var_3A0], r12
0x18002e6a5  xorps   xmm1, xmm1
0x18002e6a8  mov     [rsp+3F0h+var_394], r12d
0x18002e6ad  mov     edi, r9d
0x18002e6b0  mov     [rsp+3F0h+var_398], r12d
0x18002e6b5  lea     r13d, [r12+1]
0x18002e6ba  mov     [rsp+3F0h+var_374], r13d
0x18002e6bf  mov     rsi, r8
0x18002e6c2  mov     [rbp+2F0h+var_360], r12
0x18002e6c6  mov     r14, rdx
0x18002e6c9  mov     [rbp+2F0h+var_358], r12
0x18002e6cd  mov     r15, rcx
0x18002e6d0  mov     [rbp+2F0h+var_370], r12
0x18002e6d4  mov     [rbp+2F0h+var_368], r12
0x18002e6d8  mov     [rsp+3F0h+var_388], r12d
0x18002e6dd  mov     [rsp+3F0h+var_384], r12d
0x18002e6e2  movups  xmmword ptr [rbp+2F0h+pclsid.Data1], xmm0
0x18002e6e6  movups  xmmword ptr [rbp+2F0h+var_338.Data1], xmm1
0x18002e6ea  movups  xmmword ptr [rbp+2F0h+Buf1.Data1], xmm0
0x18002e6ee  test    rdx, rdx
0x18002e6f1  jz      loc_18002F019
0x18002e6f7  test    r8, r8
0x18002e6fa  jz      loc_18002F019
0x18002e700  lea     ecx, [r12+48h]
0x18002e705  mov     [rbp+2F0h+var_300], r12
0x18002e709  mov     [rbp+2F0h+var_2F0], ecx
0x18002e70c  lea     rax, [rbp+2F0h+var_338]
0x18002e710  mov     [rbp+2F0h+var_340], ecx
0x18002e713  lea     rdx, [rbp+2F0h+pclsid]; pclsid
0x18002e717  mov     rcx, r8; lpsz
0x18002e71a  mov     [rbp+2F0h+var_2F8], r12
0x18002e71e  mov     [rbp+2F0h+var_2EC], 10h
0x18002e725  mov     [rbp+2F0h+var_2E8], r12
0x18002e729  mov     [rbp+2F0h+var_2E0], r12d
0x18002e72d  mov     [rbp+2F0h+var_2DC], 8
0x18002e734  mov     [rbp+2F0h+var_2D8], 13h
0x18002e73b  mov     [rbp+2F0h+var_2D4], 4
0x18002e742  mov     [rbp+2F0h+var_2D0], r12
0x18002e746  mov     [rbp+2F0h+var_2C8], r13d
0x18002e74a  mov     [rbp+2F0h+var_2C4], r13d
0x18002e74e  mov     [rbp+2F0h+var_2C0], 82h
0x18002e756  mov     [rbp+2F0h+var_350], rax
0x18002e75a  mov     [rbp+2F0h+var_348], r12
0x18002e75e  mov     [rbp+2F0h+var_33C], 10h
0x18002e765  call    cs:__imp_CLSIDFromString
0x18002e76b  test    eax, eax
0x18002e76d  js      loc_18002F01E
0x18002e773  cmp     edi, 1000h
0x18002e779  jz      loc_18002E874
0x18002e77f  test    edi, edi
0x18002e781  jnz     loc_18002E916
0x18002e787  xor     edx, edx; Val
0x18002e789  lea     r8d, [r12+4Eh]; Size
0x18002e78e  lea     rcx, [rbp+2F0h+sz]; void *
0x18002e792  call    memset_0
0x18002e797  movups  xmm0, xmmword ptr cs:aSoftwareClasse_1; "Software\\Classes\\CLSID\\"
0x18002e79e  xor     edx, edx; Val
0x18002e7a0  mov     r8d, 1D8h; Size
0x18002e7a6  movups  xmm1, xmmword ptr cs:aSoftwareClasse_1+10h; "\\Classes\\CLSID\\"
0x18002e7ad  lea     rcx, [rbp+2F0h+var_230]; void *
0x18002e7b4  movaps  xmmword ptr [rbp+2F0h+SubKey], xmm0
0x18002e7bb  movups  xmm0, xmmword ptr cs:aSoftwareClasse_1+20h; "\\CLSID\\"
0x18002e7c2  movaps  [rbp+2F0h+var_250], xmm1
0x18002e7c9  movaps  [rbp+2F0h+var_240], xmm0
0x18002e7d0  call    memset_0
0x18002e7d5  cmp     word ptr [rsi], 7Bh ; '{'
0x18002e7d9  mov     [rsp+3F0h+hKey], r12
0x18002e7de  jz      loc_18002E900
0x18002e7e4  lea     r8d, [r12+27h]; cchMax
0x18002e7e9  lea     rdx, [rbp+2F0h+sz]; lpsz
0x18002e7ed  lea     rcx, [rbp+2F0h+pclsid]; rguid
0x18002e7f1  call    cs:__imp_StringFromGUID2
0x18002e7f7  test    eax, eax
0x18002e7f9  js      loc_18002F01E
0x18002e7ff  mov     ebx, 104h
0x18002e804  lea     r8, [rbp+2F0h+sz]; unsigned __int16 *
0x18002e808  mov     edx, ebx; unsigned __int64
0x18002e80a  lea     rcx, [rbp+2F0h+SubKey]; unsigned __int16 *
0x18002e811  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e816  test    eax, eax
0x18002e818  js      loc_18002F01E
0x18002e81e  lea     r8, aInprocserver32_2; "\\InprocServer32"
0x18002e825  mov     edx, ebx; unsigned __int64
0x18002e827  lea     rcx, [rbp+2F0h+SubKey]; unsigned __int16 *
0x18002e82e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e833  test    eax, eax
0x18002e835  js      loc_18002F01E
0x18002e83b  lea     rax, [rsp+3F0h+hKey]
0x18002e840  mov     r9d, 20119h; samDesired
0x18002e846  xor     r8d, r8d; ulOptions
0x18002e849  mov     [rsp+3F0h+phkResult], rax; phkResult
0x18002e84e  lea     rdx, [rbp+2F0h+SubKey]; lpSubKey
0x18002e855  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e85c  mov     edi, r13d
0x18002e85f  call    cs:__imp_RegOpenKeyExW
0x18002e865  test    eax, eax
0x18002e867  jnz     short loc_18002E879
0x18002e869  mov     rcx, [rsp+3F0h+hKey]; hKey
0x18002e86e  call    cs:__imp_RegCloseKey
0x18002e874  mov     edi, 2
0x18002e879  mov     eax, r12d
0x18002e87c  lea     r9, IID_ISimpleTableDispenser; riid
0x18002e883  cmp     edi, r13d
0x18002e886  lea     rcx, CLSID_STDispenser; rclsid
0x18002e88d  mov     r8d, r13d; dwClsContext
0x18002e890  setnz   al
0x18002e893  xor     edx, edx; pUnkOuter
0x18002e895  add     eax, r13d
0x18002e898  mov     [r15+0A8h], eax
0x18002e89f  mov     [rsp+3F0h+var_388], eax
0x18002e8a3  lea     rax, [rsp+3F0h+ppv]
0x18002e8a8  mov     [rsp+3F0h+phkResult], rax; ppv
0x18002e8ad  call    cs:__imp_CoCreateInstance
0x18002e8b3  mov     ebx, eax
0x18002e8b5  test    eax, eax
0x18002e8b7  js      loc_18002EFE4
0x18002e8bd  mov     rcx, [rsp+3F0h+ppv]; struct ISimpleTableDispenser *
0x18002e8c2  lea     r9, [rbp+2F0h+Buf1]; struct _GUID *
0x18002e8c6  lea     r8, [rbp+2F0h+var_338]; struct _GUID *
0x18002e8ca  mov     rdx, r14; unsigned __int16 *
0x18002e8cd  call    ?ResolveAppIdFromName@@YAJPEAUISimpleTableDispenser@@PEBGPEAU_GUID@@2@Z; ResolveAppIdFromName(ISimpleTableDispenser *,ushort const *,_GUID *,_GUID *)
0x18002e8d2  mov     ebx, eax
0x18002e8d4  test    eax, eax
0x18002e8d6  js      loc_18002EFE4
0x18002e8dc  mov     r8d, 10h; Size
0x18002e8e2  lea     rdx, GUID_DefaultAppPartition; Buf2
0x18002e8e9  lea     rcx, [rbp+2F0h+Buf1]; Buf1
0x18002e8ed  call    memcmp_0
0x18002e8f2  test    eax, eax
0x18002e8f4  jz      short loc_18002E929
0x18002e8f6  mov     ebx, 80110450h
0x18002e8fb  jmp     loc_18002EFE4
0x18002e900  mov     r8, rsi; unsigned __int16 *
0x18002e903  lea     rcx, [rbp+2F0h+sz]; unsigned __int16 *
0x18002e907  mov     edx, 27h ; '''; unsigned __int64
0x18002e90c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e911  jmp     loc_18002E7F7
0x18002e916  cmp     edi, 3
0x18002e919  jnz     loc_18002E879
0x18002e91f  mov     ebx, 80070057h
0x18002e924  jmp     loc_18002EFE4
0x18002e929  mov     rcx, [rsp+3F0h+ppv]
0x18002e92e  lea     rdx, [rsp+3F0h+var_3A0]
0x18002e933  mov     [rsp+3F0h+var_3B8], rdx
0x18002e938  lea     r9, [rbp+2F0h+var_350]
0x18002e93c  mov     [rsp+3F0h+var_3C0], r12d
0x18002e941  lea     r8, TID_APPLICATION
0x18002e948  mov     [rsp+3F0h+var_3C8], r13d
0x18002e94d  lea     rdx, didCOMSERVICES
0x18002e954  mov     rax, [rcx]
0x18002e957  mov     [rsp+3F0h+phkResult], r13
0x18002e95c  mov     rax, [rax+18h]
0x18002e960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e965  mov     ebx, eax
0x18002e967  test    eax, eax
0x18002e969  js      loc_18002EFE4
0x18002e96f  mov     rcx, [rsp+3F0h+var_3A0]
0x18002e974  mov     rax, [rcx]
0x18002e977  mov     rax, [rax+18h]
0x18002e97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e980  mov     ebx, eax
0x18002e982  test    eax, eax
0x18002e984  js      loc_18002EFE4
0x18002e98a  mov     rcx, [rsp+3F0h+var_3A0]
0x18002e98f  mov     rax, [rcx]
0x18002e992  mov     rax, [rax+20h]
0x18002e996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e99b  mov     ebx, eax
0x18002e99d  test    eax, eax
0x18002e99f  js      loc_18002EFE4
0x18002e9a5  mov     rcx, [rsp+3F0h+var_3A0]
0x18002e9aa  mov     rax, [rcx]
0x18002e9ad  mov     rax, [rax+28h]
0x18002e9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9b6  mov     r14d, 80110801h
0x18002e9bc  cmp     eax, r14d
0x18002e9bf  jz      loc_18002E91F
0x18002e9c5  mov     rcx, [rsp+3F0h+var_3A0]
0x18002e9ca  test    rcx, rcx
0x18002e9cd  jz      short loc_18002E9E0
0x18002e9cf  mov     rax, [rcx]
0x18002e9d2  mov     rax, [rax+10h]
0x18002e9d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9db  mov     [rsp+3F0h+var_3A0], r12
0x18002e9e0  mov     rcx, [rsp+3F0h+ppv]
0x18002e9e5  lea     r8, [rsp+3F0h+var_384]
0x18002e9ea  lea     rdx, [rbp+2F0h+var_338]
0x18002e9ee  call    cs:__imp_ServerGetApplicationType
0x18002e9f4  mov     ebx, eax
0x18002e9f6  test    eax, eax
0x18002e9f8  js      loc_18002EFE4
0x18002e9fe  test    [rsp+3F0h+var_384], edi
0x18002ea02  jnz     short loc_18002EA0E
0x18002ea04  mov     ebx, 80110482h
0x18002ea09  jmp     loc_18002EFE4
0x18002ea0e  mov     r8d, edi
0x18002ea11  lea     rdx, [rbp+2F0h+pclsid]
0x18002ea15  mov     rcx, rsi
0x18002ea18  call    cs:__imp_CLSIDFromStringByBitness
0x18002ea1e  test    eax, eax
0x18002ea20  jns     short loc_18002EA2C
0x18002ea22  mov     ebx, 8011043Eh
0x18002ea27  jmp     loc_18002EFE4
0x18002ea2c  mov     rcx, [rsp+3F0h+ppv]
0x18002ea31  lea     rax, [rbp+2F0h+pclsid]
0x18002ea35  mov     [rbp+2F0h+var_300], rax
0x18002ea39  lea     rdx, didCOMSERVICES
0x18002ea40  lea     rax, [rsp+3F0h+var_388]
0x18002ea45  mov     r8d, 0A00000h
0x18002ea4b  mov     [rbp+2F0h+var_2E8], rax
0x18002ea4f  mov     r9d, 0C00000h
0x18002ea55  mov     rax, [rcx]
0x18002ea58  cmp     edi, r13d
0x18002ea5b  mov     esi, 3
0x18002ea60  cmovnz  r8d, r9d
0x18002ea64  lea     r9, [rsp+3F0h+var_3A0]
0x18002ea69  mov     [rsp+3F0h+var_3B8], r9
0x18002ea6e  lea     r9, [rbp+2F0h+var_300]
0x18002ea72  mov     rax, [rax+18h]
0x18002ea76  mov     [rsp+3F0h+var_3C0], r8d
0x18002ea7b  lea     r8, tidCOMSERVICES_CLASSES
0x18002ea82  mov     [rsp+3F0h+var_3C8], r13d
0x18002ea87  mov     [rsp+3F0h+phkResult], rsi
0x18002ea8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea91  mov     ebx, eax
0x18002ea93  test    eax, eax
0x18002ea95  js      loc_18002EFE4
0x18002ea9b  mov     rcx, [rsp+3F0h+var_3A0]
0x18002eaa0  mov     rax, [rcx]
0x18002eaa3  mov     rax, [rax+18h]
0x18002eaa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eaac  mov     ebx, eax
0x18002eaae  test    eax, eax
0x18002eab0  js      loc_18002EFE4
0x18002eab6  mov     rcx, [rsp+3F0h+var_3A0]
0x18002eabb  mov     rax, [rcx]
0x18002eabe  mov     rax, [rax+20h]
0x18002eac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eac7  mov     ebx, eax
0x18002eac9  test    eax, eax
0x18002eacb  js      loc_18002EFE4
0x18002ead1  mov     rcx, [rsp+3F0h+var_3A0]
0x18002ead6  mov     rax, [rcx]
0x18002ead9  mov     rax, [rax+28h]
0x18002eadd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eae2  cmp     eax, r14d
0x18002eae5  jnz     short loc_18002EAF1
0x18002eae7  mov     ebx, 80110411h
0x18002eaec  jmp     loc_18002EFE4
0x18002eaf1  mov     rcx, [rsp+3F0h+var_3A0]
0x18002eaf6  lea     rdx, [rbp+2F0h+var_370]
0x18002eafa  mov     [rsp+3F0h+phkResult], rdx
0x18002eaff  lea     r9, [rsp+3F0h+var_398]
0x18002eb04  mov     edi, 9
0x18002eb09  lea     r8, [rsp+3F0h+var_394]
0x18002eb0e  mov     edx, edi
0x18002eb10  mov     rax, [rcx]
0x18002eb13  mov     rax, [rax+40h]
0x18002eb17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb1c  mov     ebx, eax
0x18002eb1e  test    eax, eax
0x18002eb20  js      loc_18002EFE4
0x18002eb26  mov     rcx, [rbp+2F0h+var_370]
0x18002eb2a  test    rcx, rcx
0x18002eb2d  jz      short loc_18002EB4F
0x18002eb2f  mov     rax, [rcx]
0x18002eb32  sub     rax, qword ptr [rbp+2F0h+var_338.Data1]
0x18002eb36  jnz     short loc_18002EB40
0x18002eb38  mov     rax, [rcx+8]
0x18002eb3c  sub     rax, qword ptr [rbp+2F0h+var_338.Data4]
0x18002eb40  test    rax, rax
0x18002eb43  jz      short loc_18002EB4F
0x18002eb45  mov     ebx, 80110404h
0x18002eb4a  jmp     loc_18002EFE4
0x18002eb4f  mov     r9d, [r15+0A8h]
0x18002eb56  lea     rax, [rsp+3F0h+hKey]
0x18002eb5b  mov     rdx, [rsp+3F0h+ppv]
0x18002eb60  lea     r8, [rbp+2F0h+pclsid]
0x18002eb64  mov     [rsp+3F0h+phkResult], rax
0x18002eb69  mov     dword ptr [rsp+3F0h+hKey], r12d
0x18002eb6e  call    ?IsClassLegacyConfigured@CCOMComponentRegistrar@@AEAAJPEAUISimpleTableDispenser@@PEAU_GUID@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@PEAH@Z; CCOMComponentRegistrar::IsClassLegacyConfigured(ISimpleTableDispenser *,_GUID *,__MIDL___MIDL_itf_registrar_0000_0000_0001,int *)
0x18002eb73  mov     ebx, eax
0x18002eb75  test    eax, eax
  ... truncated ...
```
