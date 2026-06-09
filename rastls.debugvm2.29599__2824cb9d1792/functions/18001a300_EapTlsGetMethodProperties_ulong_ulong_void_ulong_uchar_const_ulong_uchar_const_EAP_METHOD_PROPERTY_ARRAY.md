# EapTlsGetMethodProperties(ulong,ulong,void *,ulong,uchar const *,ulong,uchar const *,_EAP_METHOD_PROPERTY_ARRAY *)

- ea: `0x18001a300`
- end: `0x18001aa29`
- name: `?EapTlsGetMethodProperties@@YAKKKPEAXKPEBEK1PEAU_EAP_METHOD_PROPERTY_ARRAY@@@Z`
- size: `1833`
- prototype: `unsigned int(unsigned int, unsigned int, void *, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, struct _EAP_METHOD_PROPERTY_ARRAY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18001a1e0`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180007910`
- `0x18001a300`
- `0x18003623c`
- `0x180057d54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a4e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a981`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a4e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a981`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a58f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a671`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a81b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a58f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a671`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a81b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a995`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a9da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a9ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a995`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a9da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a9ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a9b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a9b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a45f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a45f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a49f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a539`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a5c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a91d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a49f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a539`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a5c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a91d`

## string_xrefs

- `0x18001a451`: `System\CurrentControlSet\Services\Rasman\PPP\EAP\13`
- `0x18001a916`: `UseSoftTokenWithMachineAuthentication`

## pseudocode

```c
__int64 __fastcall EapTlsGetMethodProperties(
        __int64 a1,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        const unsigned __int8 *a7,
        __int64 a8)
{
  struct _EAP_METHOD_PROPERTY_ARRAY *v8; // rbx
  int v9; // r12d
  struct _EAPTLS_CONN_PROPERTIES *v10; // rsi
  DWORD LastError; // r15d
  struct _EAPTLS_CONTROL_BLOCK *v12; // rax
  __int64 v13; // rdx
  unsigned int v14; // edi
  LSTATUS v15; // eax
  struct _EAPTLS_CONTROL_BLOCK *v16; // rax
  __int64 v17; // rdx
  int v18; // edi
  int v19; // r14d
  HKEY v20; // rcx
  unsigned int v21; // eax
  struct _EAPTLS_CONN_PROPERTIES *v22; // r13
  unsigned int v23; // eax
  __int64 v24; // rax
  EAP_METHOD_PROPERTY *v25; // rax
  __int64 v26; // r13
  __int64 v27; // r8
  __int64 v28; // rdx
  unsigned __int8 v29; // cf
  __int64 v30; // rcx
  struct _EAPTLS_CONN_PROPERTIES *v31; // r12
  DWORD i; // edi
  DWORD v33; // eax
  __int64 v34; // rdx
  EAP_METHOD_PROPERTY *pMethodProperty; // rcx
  EAP_METHOD_PROPERTY *v36; // r10
  int eapMethodPropertyType; // ecx
  unsigned int v38; // r13d
  struct _EAPTLS_CONN_PROPERTIES *v39; // r8
  __int64 v40; // r9
  unsigned int v41; // r8d
  BYTE *v42; // rax
  struct _EAP_METHOD_PROPERTY_ARRAY *v43; // r9
  EAP_METHOD_PROPERTY *v44; // rdx
  struct _EAPTLS_CONN_PROPERTIES *v45; // rcx
  DWORD j; // edi
  __int64 v47; // r13
  EAP_METHOD_PROPERTY *v48; // rcx
  EAP_METHOD_PROPERTY_TYPE v49; // eax
  __int64 v50; // r8
  EAP_METHOD_PROPERTY *v51; // rdx
  char v52; // cl
  int value; // eax
  DWORD k; // edi
  EAP_METHOD_PROPERTY *v55; // rax
  BYTE Data[8]; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-28h] BYREF
  struct _EAPTLS_CONN_PROPERTIES *v59; // [rsp+40h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+30h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+40h] BYREF
  int v62; // [rsp+A4h] [rbp+44h]

  v62 = HIDWORD(a3);
  v8 = (struct _EAP_METHOD_PROPERTY_ARRAY *)a8;
  hKey = 0;
  v9 = 0;
  Type = 0;
  v10 = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  v59 = 0;
  if ( !a8 )
  {
    LastError = 87;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_84;
    v13 = 818;
    goto LABEL_4;
  }
  if ( a4 && !a5 )
  {
    LastError = 87;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v13 = 819;
LABEL_4:
      WPP_SF_(*((_QWORD *)v12 + 2), v13, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      goto LABEL_84;
    }
    goto LABEL_84;
  }
  if ( !a6 || a7 )
  {
    LastError = 0;
    if ( a4 && a5 )
    {
      LastError = EapTlsReadConnectionData(a2, a5, a4, &v59);
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            821,
            &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
            LastError);
        v10 = v59;
        goto LABEL_84;
      }
      v10 = v59;
    }
    v14 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP\\13",
            0,
            0x20019u,
            &hKey);
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 828, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v14);
      LastError = v14;
      goto LABEL_84;
    }
    cbData = 4;
    v15 = RegQueryValueExW(hKey, L"Properties", 0, &Type, Data, &cbData);
    if ( v15 )
    {
      if ( v15 != 2 )
      {
        LastError = GetLastError();
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_84;
        v17 = 823;
        goto LABEL_34;
      }
      v18 = 0;
      v19 = 0;
    }
    else
    {
      if ( Type != 4 )
      {
        LastError = 1629;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_84;
        v17 = 822;
LABEL_34:
        WPP_SF_d(*((_QWORD *)v16 + 2), v17, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, LastError);
        goto LABEL_84;
      }
      v18 = *(_DWORD *)Data;
      v19 = 30;
    }
    v20 = hKey;
    *v8 = 0;
    v21 = RegQueryValueExW(v20, L"ExtendedProperties", 0, &Type, 0, &cbData);
    if ( v21 )
    {
      v59 = 0;
      if ( v21 != 2 )
      {
        LastError = v21;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 827, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v21);
        goto LABEL_84;
      }
    }
    else
    {
      if ( Type != 3 )
      {
        LastError = 1629;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_84;
        v17 = 824;
        goto LABEL_34;
      }
      v59 = (struct _EAPTLS_CONN_PROPERTIES *)LocalAlloc(0x40u, cbData);
      v22 = v59;
      if ( !v59 )
      {
LABEL_83:
        LastError = GetLastError();
        goto LABEL_84;
      }
      v23 = RegQueryValueExW(hKey, L"ExtendedProperties", 0, &Type, (LPBYTE)v59, &cbData);
      if ( v23 )
      {
        LastError = v23;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 825, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v23);
        goto LABEL_84;
      }
      LODWORD(a8) = v19;
      if ( (unsigned int)ValidateExtendedMethodProperties(&a8, v22, cbData) != 1 )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 826, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
        LastError = 13;
        goto LABEL_84;
      }
      v9 = a8;
    }
    v24 = (unsigned int)(v9 + v19);
    v8->dwNumberOfProperties = v24;
    if ( !(_DWORD)v24 )
      goto LABEL_84;
    v25 = (EAP_METHOD_PROPERTY *)LocalAlloc(0x40u, 24 * v24);
    v8->pMethodProperty = v25;
    if ( v25 )
    {
      v26 = 0;
      if ( v19 )
      {
        v27 = 0;
        do
        {
          v28 = v27;
          v29 = _bittest(&v18, v27);
          v8->pMethodProperty[v28].eapMethodPropertyType = v27;
          v27 = (unsigned int)(v27 + 1);
          v8->pMethodProperty[v28].eapMethodPropertyValueType = empvtBool;
          v8->pMethodProperty[v28].eapMethodPropertyValue.empvBool.length = 4;
          v8->pMethodProperty[v28].eapMethodPropertyValue.empvBool.value = v29;
        }
        while ( (unsigned int)v27 < v19 - 1 );
        v30 = v27;
        v8->pMethodProperty[v30].eapMethodPropertyType = emptLegacyMethodPropertyFlag;
        v8->pMethodProperty[v30].eapMethodPropertyValueType = empvtDword;
        v8->pMethodProperty[v30].eapMethodPropertyValue.empvBool.length = 4;
        v8->pMethodProperty[v30].eapMethodPropertyValue.empvBool.value = v18;
      }
      v31 = v59;
      for ( i = v19; i < v8->dwNumberOfProperties; ++i )
      {
        v33 = *(_DWORD *)((char *)v31 + v26);
        v34 = i;
        pMethodProperty = v8->pMethodProperty;
        a8 = v34 * 24;
        pMethodProperty[v34].eapMethodPropertyType = v33;
        v36 = v8->pMethodProperty;
        eapMethodPropertyType = v36[v34].eapMethodPropertyType;
        if ( eapMethodPropertyType > 255 )
          goto LABEL_84;
        v38 = v26 + 4;
        v39 = (struct _EAPTLS_CONN_PROPERTIES *)((char *)v31 + v38);
        v59 = v39;
        v40 = v38 + 4;
        v26 = v40;
        if ( eapMethodPropertyType == 255 )
        {
          v36[v34].eapMethodPropertyValueType = empvtString;
          v42 = (BYTE *)LocalAlloc(0x40u, *(unsigned int *)v39);
          v43 = (struct _EAP_METHOD_PROPERTY_ARRAY *)a8;
          *(BYTE **)((char *)&v8->pMethodProperty->eapMethodPropertyValue.empvString.value + a8) = v42;
          v44 = v8->pMethodProperty;
          if ( !*(_QWORD *)((char *)&v43[1].dwNumberOfProperties + (_QWORD)v44) )
            goto LABEL_83;
          v45 = v59;
          *(_DWORD *)((char *)&v43->pMethodProperty + (_QWORD)v44) = *(_DWORD *)v59;
          memcpy_0(
            *(void **)((char *)&v8->pMethodProperty->eapMethodPropertyValue.empvString.value + (unsigned __int64)v43),
            (char *)v31 + v26,
            *(unsigned int *)v45);
        }
        else
        {
          if ( (unsigned int)eapMethodPropertyType > 0x1C )
            goto LABEL_84;
          v36[v34].eapMethodPropertyValueType = empvtBool;
          v8->pMethodProperty[v34].eapMethodPropertyValue.empvBool.length = *(_DWORD *)v39;
          v41 = *(_DWORD *)((char *)v31 + v40);
          if ( v41 > 1 )
            goto LABEL_84;
          v26 = (unsigned int)(v40 + 4);
          v8->pMethodProperty[v34].eapMethodPropertyValue.empvBool.value = v41 != 0;
        }
      }
      if ( v10 )
      {
        for ( j = 0; j < v8->dwNumberOfProperties; ++j )
        {
          v47 = j;
          v48 = &v8->pMethodProperty[v47];
          v49 = v48->eapMethodPropertyType;
          if ( v48->eapMethodPropertyType == emptPropMutualAuth )
          {
            if ( (*((_BYTE *)v10 + 8) & 2) != 0 )
              v48->eapMethodPropertyValue.empvBool.value = 0;
          }
          else if ( v49 == emptPropMachineAuth )
          {
            if ( (*((_BYTE *)v10 + 8) & 1) == 0 )
            {
              cbData = 4;
              if ( RegQueryValueExW(hKey, L"UseSoftTokenWithMachineAuthentication", 0, &Type, Data, &cbData)
                || Type != 4
                || *(_DWORD *)Data != 1 )
              {
                v8->pMethodProperty[v47].eapMethodPropertyValue.empvBool.value = 0;
              }
            }
          }
          else if ( v49 == emptLegacyMethodPropertyFlag )
          {
            v48->eapMethodPropertyValue.empvBool.value = 0;
            v50 = 0;
            do
            {
              v51 = v8->pMethodProperty;
              v52 = v50;
              value = v51[v50].eapMethodPropertyValue.empvBool.value;
              v50 = (unsigned int)(v50 + 1);
              v51[v47].eapMethodPropertyValue.empvBool.value |= value << v52;
            }
            while ( (unsigned int)v50 < v19 - 1 );
          }
        }
      }
      goto LABEL_84;
    }
    goto LABEL_83;
  }
  LastError = 87;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v13 = 820;
    goto LABEL_4;
  }
LABEL_84:
  LocalFree(v10);
  if ( hKey )
    RegCloseKey(hKey);
  if ( LastError )
  {
    for ( k = 0; k < v8->dwNumberOfProperties; ++k )
    {
      v55 = v8->pMethodProperty;
      if ( v55[k].eapMethodPropertyValueType == empvtString )
        LocalFree(v55[k].eapMethodPropertyValue.empvString.value);
    }
    LocalFree(v8->pMethodProperty);
    *v8 = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18001a300  mov     rax, rsp
0x18001a303  mov     [rax+18h], r8
0x18001a307  mov     [rax+8], ecx
0x18001a30a  push    rbp
0x18001a30b  push    rbx
0x18001a30c  push    rdi
0x18001a30d  push    r13
0x18001a30f  push    r15
0x18001a311  mov     rbp, rsp
0x18001a314  sub     rsp, 60h
0x18001a318  mov     rbx, [rbp+arg_38]
0x18001a31c  xor     r13d, r13d
0x18001a31f  mov     [rax+10h], rsi
0x18001a323  mov     r10d, edx
0x18001a326  mov     [rax-30h], r12
0x18001a32a  mov     eax, r9d
0x18001a32d  mov     [rbp+hKey], r13
0x18001a331  mov     r12d, r13d
0x18001a334  mov     [rbp+Type], r13d
0x18001a338  mov     esi, r13d
0x18001a33b  mov     dword ptr [rbp+Data], r13d
0x18001a33f  mov     [rbp+cbData], r13d
0x18001a343  mov     [rbp+var_20], r13
0x18001a347  test    rbx, rbx
0x18001a34a  jnz     short loc_18001A383
0x18001a34c  mov     r15d, 57h ; 'W'
0x18001a352  mov     rax, cs:WPP_GLOBAL_Control
0x18001a359  lea     rcx, WPP_GLOBAL_Control
0x18001a360  cmp     rax, rcx
0x18001a363  jz      loc_18001A992
0x18001a369  mov     edx, 332h
0x18001a36e  mov     rcx, [rax+10h]
0x18001a372  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18001a379  call    WPP_SF_
0x18001a37e  jmp     loc_18001A992
0x18001a383  test    eax, eax
0x18001a385  jz      short loc_18001A3B1
0x18001a387  cmp     [rbp+arg_20], rsi
0x18001a38b  jnz     short loc_18001A3B1
0x18001a38d  mov     r15d, 57h ; 'W'
0x18001a393  mov     rax, cs:WPP_GLOBAL_Control
0x18001a39a  lea     rcx, WPP_GLOBAL_Control
0x18001a3a1  cmp     rax, rcx
0x18001a3a4  jz      loc_18001A992
0x18001a3aa  mov     edx, 333h
0x18001a3af  jmp     short loc_18001A36E
0x18001a3b1  cmp     [rbp+arg_28], esi
0x18001a3b4  jz      short loc_18001A3E0
0x18001a3b6  cmp     [rbp+arg_30], rsi
0x18001a3ba  jnz     short loc_18001A3E0
0x18001a3bc  mov     r15d, 57h ; 'W'
0x18001a3c2  mov     rax, cs:WPP_GLOBAL_Control
0x18001a3c9  lea     rcx, WPP_GLOBAL_Control
0x18001a3d0  cmp     rax, rcx
0x18001a3d3  jz      loc_18001A992
0x18001a3d9  mov     edx, 334h
0x18001a3de  jmp     short loc_18001A36E
0x18001a3e0  mov     r15d, r13d
0x18001a3e3  test    eax, eax
0x18001a3e5  jz      short loc_18001A43F
0x18001a3e7  cmp     [rbp+arg_20], rsi
0x18001a3eb  jz      short loc_18001A43F
0x18001a3ed  mov     rdx, [rbp+arg_20]; unsigned __int8 *
0x18001a3f1  lea     r9, [rbp+var_20]; struct _EAPTLS_CONN_PROPERTIES **
0x18001a3f5  mov     r8d, eax; unsigned int
0x18001a3f8  mov     ecx, r10d; unsigned int
0x18001a3fb  call    ?EapTlsReadConnectionData@@YAKKPEAEKPEAPEAU_EAPTLS_CONN_PROPERTIES@@@Z; EapTlsReadConnectionData(ulong,uchar *,ulong,_EAPTLS_CONN_PROPERTIES * *)
0x18001a400  mov     r15d, eax
0x18001a403  test    eax, eax
0x18001a405  jz      short loc_18001A43B
0x18001a407  mov     rax, cs:WPP_GLOBAL_Control
0x18001a40e  lea     rcx, WPP_GLOBAL_Control
0x18001a415  cmp     rax, rcx
0x18001a418  jz      short loc_18001A432
0x18001a41a  mov     rcx, [rax+10h]
0x18001a41e  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18001a425  mov     edx, 335h
0x18001a42a  mov     r9d, r15d
0x18001a42d  call    WPP_SF_d
0x18001a432  mov     rsi, [rbp+var_20]
0x18001a436  jmp     loc_18001A992
0x18001a43b  mov     rsi, [rbp+var_20]
0x18001a43f  lea     rax, [rbp+hKey]
0x18001a443  mov     r9d, 20019h; samDesired
0x18001a449  xor     r8d, r8d; ulOptions
0x18001a44c  mov     [rsp+60h+phkResult], rax; phkResult
0x18001a451  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ra"...
0x18001a458  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a45f  call    cs:__imp_RegOpenKeyExW
0x18001a465  mov     edi, eax
0x18001a467  test    eax, eax
0x18001a469  jnz     loc_18001A951
0x18001a46f  mov     rcx, [rbp+hKey]; hKey
0x18001a473  lea     rax, [rbp+cbData]
0x18001a477  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18001a47c  lea     r9, [rbp+Type]; lpType
0x18001a480  lea     rax, [rbp+Data]
0x18001a484  mov     [rsp+60h+var_10], r14
0x18001a489  xor     r8d, r8d; lpReserved
0x18001a48c  mov     [rsp+60h+phkResult], rax; lpData
0x18001a491  lea     rdx, ValueName; "Properties"
0x18001a498  mov     [rbp+cbData], 4
0x18001a49f  call    cs:__imp_RegQueryValueExW
0x18001a4a5  test    eax, eax
0x18001a4a7  jnz     short loc_18001A4E1
0x18001a4a9  cmp     [rbp+Type], 4
0x18001a4ad  jz      short loc_18001A4D6
0x18001a4af  mov     r15d, 65Dh
0x18001a4b5  mov     rax, cs:WPP_GLOBAL_Control
0x18001a4bc  lea     rcx, WPP_GLOBAL_Control
0x18001a4c3  cmp     rax, rcx
0x18001a4c6  jz      loc_18001A98D
0x18001a4cc  mov     edx, 336h
0x18001a4d1  jmp     loc_18001A56F
0x18001a4d6  mov     edi, dword ptr [rbp+Data]
0x18001a4d9  mov     r14d, 1Eh
0x18001a4df  jmp     short loc_18001A513
0x18001a4e1  cmp     eax, 2
0x18001a4e4  jz      short loc_18001A50D
0x18001a4e6  call    cs:__imp_GetLastError
0x18001a4ec  mov     r15d, eax
0x18001a4ef  mov     rax, cs:WPP_GLOBAL_Control
0x18001a4f6  lea     rcx, WPP_GLOBAL_Control
0x18001a4fd  cmp     rax, rcx
0x18001a500  jz      loc_18001A98D
0x18001a506  mov     edx, 337h
0x18001a50b  jmp     short loc_18001A56F
0x18001a50d  mov     edi, r13d
0x18001a510  mov     r14d, r13d
0x18001a513  mov     rcx, [rbp+hKey]; hKey
0x18001a517  lea     rax, [rbp+cbData]
0x18001a51b  xorps   xmm0, xmm0
0x18001a51e  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18001a523  lea     r9, [rbp+Type]; lpType
0x18001a527  mov     [rsp+60h+phkResult], r13; lpData
0x18001a52c  xor     r8d, r8d; lpReserved
0x18001a52f  lea     rdx, aExtendedproper; "ExtendedProperties"
0x18001a536  movups  xmmword ptr [rbx], xmm0
0x18001a539  call    cs:__imp_RegQueryValueExW
0x18001a53f  test    eax, eax
0x18001a541  jnz     loc_18001A78E
0x18001a547  cmp     [rbp+Type], 3
0x18001a54b  jz      short loc_18001A587
0x18001a54d  mov     r15d, 65Dh
0x18001a553  mov     rax, cs:WPP_GLOBAL_Control
0x18001a55a  lea     rcx, WPP_GLOBAL_Control
0x18001a561  cmp     rax, rcx
0x18001a564  jz      loc_18001A98D
0x18001a56a  mov     edx, 338h
0x18001a56f  mov     rcx, [rax+10h]
0x18001a573  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18001a57a  mov     r9d, r15d
0x18001a57d  call    WPP_SF_d
0x18001a582  jmp     loc_18001A98D
0x18001a587  mov     edx, [rbp+cbData]; uBytes
0x18001a58a  mov     ecx, 40h ; '@'; uFlags
0x18001a58f  call    cs:__imp_LocalAlloc
0x18001a595  mov     [rbp+var_20], rax
0x18001a599  mov     r13, rax
0x18001a59c  test    rax, rax
0x18001a59f  jz      loc_18001A981
0x18001a5a5  mov     rcx, [rbp+hKey]; hKey
0x18001a5a9  lea     rax, [rbp+cbData]
0x18001a5ad  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18001a5b2  lea     r9, [rbp+Type]; lpType
0x18001a5b6  xor     r8d, r8d; lpReserved
0x18001a5b9  mov     [rsp+60h+phkResult], r13; lpData
0x18001a5be  lea     rdx, aExtendedproper; "ExtendedProperties"
0x18001a5c5  call    cs:__imp_RegQueryValueExW
0x18001a5cb  test    eax, eax
0x18001a5cd  jz      short loc_18001A606
0x18001a5cf  mov     r15d, eax
0x18001a5d2  mov     r10, cs:WPP_GLOBAL_Control
0x18001a5d9  lea     rcx, WPP_GLOBAL_Control
0x18001a5e0  cmp     r10, rcx
0x18001a5e3  jz      loc_18001A98A
0x18001a5e9  mov     rcx, [r10+10h]
0x18001a5ed  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18001a5f4  mov     edx, 339h
0x18001a5f9  mov     r9d, eax
0x18001a5fc  call    WPP_SF_d
0x18001a601  jmp     loc_18001A98A
0x18001a606  mov     r8d, [rbp+cbData]
0x18001a60a  lea     rcx, [rbp+arg_38]
0x18001a60e  mov     rdx, r13
0x18001a611  mov     dword ptr [rbp+arg_38], r14d
0x18001a615  call    ValidateExtendedMethodProperties
0x18001a61a  cmp     eax, 1
0x18001a61d  jz      short loc_18001A652
0x18001a61f  mov     rax, cs:WPP_GLOBAL_Control
0x18001a626  lea     rcx, WPP_GLOBAL_Control
0x18001a62d  cmp     rax, rcx
0x18001a630  jz      short loc_18001A647
0x18001a632  mov     rcx, [rax+10h]
0x18001a636  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18001a63d  mov     edx, 33Ah
0x18001a642  call    WPP_SF_
0x18001a647  mov     r15d, 0Dh
0x18001a64d  jmp     loc_18001A98A
0x18001a652  mov     r12d, dword ptr [rbp+arg_38]
0x18001a656  lea     eax, [r12+r14]
0x18001a65a  mov     [rbx], eax
0x18001a65c  test    eax, eax
0x18001a65e  jz      loc_18001A98A
0x18001a664  lea     rdx, [rax+rax*2]
0x18001a668  mov     ecx, 40h ; '@'; uFlags
0x18001a66d  shl     rdx, 3; uBytes
0x18001a671  call    cs:__imp_LocalAlloc
0x18001a677  mov     [rbx+8], rax
0x18001a67b  test    rax, rax
0x18001a67e  jz      loc_18001A981
0x18001a684  xor     r13d, r13d
0x18001a687  test    r14d, r14d
0x18001a68a  jz      short loc_18001A704
0x18001a68c  xor     r8d, r8d
0x18001a68f  lea     r9d, [r14-1]
0x18001a693  mov     rax, [rbx+8]
0x18001a697  lea     rcx, [r8+r8*2]
0x18001a69b  lea     rdx, ds:0[rcx*8]
0x18001a6a3  xor     ecx, ecx
0x18001a6a5  bt      edi, r8d
0x18001a6a9  mov     [rdx+rax], r8d
0x18001a6ad  setb    cl
0x18001a6b0  mov     rax, [rbx+8]
0x18001a6b4  inc     r8d
0x18001a6b7  mov     [rax+rdx+4], r13d
0x18001a6bc  mov     rax, [rbx+8]
0x18001a6c0  mov     dword ptr [rax+rdx+8], 4
0x18001a6c8  mov     rax, [rbx+8]
0x18001a6cc  mov     [rax+rdx+0Ch], ecx
0x18001a6d0  cmp     r8d, r9d
0x18001a6d3  jb      short loc_18001A693
0x18001a6d5  mov     rax, [rbx+8]
0x18001a6d9  lea     rcx, [r8+r8*2]
0x18001a6dd  mov     dword ptr [rax+rcx*8], 1Fh
0x18001a6e4  mov     rax, [rbx+8]
0x18001a6e8  mov     dword ptr [rax+rcx*8+4], 1
0x18001a6f0  mov     rax, [rbx+8]
0x18001a6f4  mov     dword ptr [rax+rcx*8+8], 4
0x18001a6fc  mov     rax, [rbx+8]
0x18001a700  mov     [rax+rcx*8+0Ch], edi
0x18001a704  mov     r12, [rbp+var_20]
0x18001a708  lea     r11, __ImageBase
0x18001a70f  mov     edi, r14d
0x18001a712  mov     eax, [rbx]
0x18001a714  cmp     edi, eax
0x18001a716  jnb     loc_18001A86C
0x18001a71c  mov     eax, edi
0x18001a71e  lea     rcx, [rax+rax*2]
0x18001a722  mov     eax, [r13+r12+0]
0x18001a727  lea     rdx, ds:0[rcx*8]
0x18001a72f  mov     rcx, [rbx+8]
0x18001a733  mov     [rbp+arg_38], rdx
0x18001a737  mov     [rdx+rcx], eax
0x18001a73a  mov     r10, [rbx+8]
0x18001a73e  movsxd  rcx, dword ptr [r10+rdx]
0x18001a742  cmp     ecx, 0FFh
0x18001a748  jg      loc_18001A98A
0x18001a74e  add     r13d, 4
0x18001a752  mov     r8d, r13d
0x18001a755  add     r8, r12
0x18001a758  mov     [rbp+var_20], r8
0x18001a75c  lea     r9d, [r13+4]
0x18001a760  mov     r13d, r9d
0x18001a763  cmp     ecx, 0FFh
0x18001a769  jz      loc_18001A80A
0x18001a76f  cmp     ecx, 1Ch
0x18001a772  ja      loc_18001A98A
0x18001a778  movzx   eax, ds:rva byte_18001AA0C[r11+rcx]
0x18001a781  mov     ecx, ds:(jpt_18001A78C - 180000000h)[r11+rax*4]; switch 1 cases
0x18001a789  add     rcx, r11
0x18001a78c  jmp     rcx; switch jump
0x18001a78e  mov     [rbp+var_20], r13
0x18001a792  cmp     eax, 2
0x18001a795  jz      loc_18001A656
0x18001a79b  mov     r15d, eax
0x18001a79e  mov     r10, cs:WPP_GLOBAL_Control
0x18001a7a5  lea     rcx, WPP_GLOBAL_Control
0x18001a7ac  cmp     r10, rcx
0x18001a7af  jz      loc_18001A98D
0x18001a7b5  mov     rcx, [r10+10h]
0x18001a7b9  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18001a7c0  mov     edx, 33Bh
0x18001a7c5  mov     r9d, eax
0x18001a7c8  call    WPP_SF_d
0x18001a7cd  jmp     loc_18001A98D
0x18001a7d2  mov     dword ptr [r10+rdx+4], 0; jumptable 000000018001A78C case 0
0x18001a7db  mov     eax, [r8]
0x18001a7de  mov     rcx, [rbx+8]
0x18001a7e2  mov     [rcx+rdx+8], eax
0x18001a7e6  mov     r8d, [r9+r12]
0x18001a7ea  cmp     r8d, 1
0x18001a7ee  ja      loc_18001A98A
0x18001a7f4  mov     rax, [rbx+8]
0x18001a7f8  xor     ecx, ecx
0x18001a7fa  add     r13d, 4
0x18001a7fe  test    r8d, r8d
0x18001a801  setnz   cl
0x18001a804  mov     [rax+rdx+0Ch], ecx
0x18001a808  jmp     short loc_18001A865
  ... truncated ...
```
