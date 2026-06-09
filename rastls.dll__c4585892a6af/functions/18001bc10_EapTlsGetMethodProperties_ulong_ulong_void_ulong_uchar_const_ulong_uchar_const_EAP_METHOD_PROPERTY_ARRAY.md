# EapTlsGetMethodProperties(ulong,ulong,void *,ulong,uchar const *,ulong,uchar const *,_EAP_METHOD_PROPERTY_ARRAY *)

- ea: `0x18001bc10`
- end: `0x18001c391`
- name: `?EapTlsGetMethodProperties@@YAKKKPEAXKPEBEK1PEAU_EAP_METHOD_PROPERTY_ARRAY@@@Z`
- size: `1921`
- prototype: `unsigned int(unsigned int, unsigned int, void *, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, struct _EAP_METHOD_PROPERTY_ARRAY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18001baf0`

## callees

- `0x180005010`
- `0x180007d00`
- `0x1800080a0`
- `0x18001bc10`
- `0x180038e4c`
- `0x18005af5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001beb7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bfa5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c159`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001beb7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bfa5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c159`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c2e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c336`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c34c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c2e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c336`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c34c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c307`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c307`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bd6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bd6f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bdb5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001be5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bef3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c261`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bdb5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001be5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bef3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c261`

## string_xrefs

- `0x18001bd61`: `System\CurrentControlSet\Services\Rasman\PPP\EAP\13`
- `0x18001c25a`: `UseSoftTokenWithMachineAuthentication`

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
      WPP_SF_(*((_QWORD *)v12 + 2), v13, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
            &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 828, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v14);
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
        WPP_SF_d(*((_QWORD *)v16 + 2), v17, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, LastError);
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
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 827, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v21);
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
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 825, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v23);
        goto LABEL_84;
      }
      LODWORD(a8) = v19;
      if ( (unsigned int)ValidateExtendedMethodProperties(&a8, v22, cbData) != 1 )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 826, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
0x18001bc10  mov     rax, rsp
0x18001bc13  mov     [rax+18h], r8
0x18001bc17  mov     [rax+8], ecx
0x18001bc1a  push    rbp
0x18001bc1b  push    rbx
0x18001bc1c  push    rdi
0x18001bc1d  push    r13
0x18001bc1f  push    r15
0x18001bc21  mov     rbp, rsp
0x18001bc24  sub     rsp, 60h
0x18001bc28  mov     rbx, [rbp+arg_38]
0x18001bc2c  xor     r13d, r13d
0x18001bc2f  mov     [rax+10h], rsi
0x18001bc33  mov     r10d, edx
0x18001bc36  mov     [rax-30h], r12
0x18001bc3a  mov     eax, r9d
0x18001bc3d  mov     [rbp+hKey], r13
0x18001bc41  mov     r12d, r13d
0x18001bc44  mov     [rbp+Type], r13d
0x18001bc48  mov     esi, r13d
0x18001bc4b  mov     dword ptr [rbp+Data], r13d
0x18001bc4f  mov     [rbp+cbData], r13d
0x18001bc53  mov     [rbp+var_20], r13
0x18001bc57  test    rbx, rbx
0x18001bc5a  jnz     short loc_18001BC93
0x18001bc5c  mov     r15d, 57h ; 'W'
0x18001bc62  mov     rax, cs:WPP_GLOBAL_Control
0x18001bc69  lea     rcx, WPP_GLOBAL_Control
0x18001bc70  cmp     rax, rcx
0x18001bc73  jz      loc_18001C2E2
0x18001bc79  mov     edx, 332h
0x18001bc7e  mov     rcx, [rax+10h]
0x18001bc82  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18001bc89  call    WPP_SF_
0x18001bc8e  jmp     loc_18001C2E2
0x18001bc93  test    eax, eax
0x18001bc95  jz      short loc_18001BCC1
0x18001bc97  cmp     [rbp+arg_20], rsi
0x18001bc9b  jnz     short loc_18001BCC1
0x18001bc9d  mov     r15d, 57h ; 'W'
0x18001bca3  mov     rax, cs:WPP_GLOBAL_Control
0x18001bcaa  lea     rcx, WPP_GLOBAL_Control
0x18001bcb1  cmp     rax, rcx
0x18001bcb4  jz      loc_18001C2E2
0x18001bcba  mov     edx, 333h
0x18001bcbf  jmp     short loc_18001BC7E
0x18001bcc1  cmp     [rbp+arg_28], esi
0x18001bcc4  jz      short loc_18001BCF0
0x18001bcc6  cmp     [rbp+arg_30], rsi
0x18001bcca  jnz     short loc_18001BCF0
0x18001bccc  mov     r15d, 57h ; 'W'
0x18001bcd2  mov     rax, cs:WPP_GLOBAL_Control
0x18001bcd9  lea     rcx, WPP_GLOBAL_Control
0x18001bce0  cmp     rax, rcx
0x18001bce3  jz      loc_18001C2E2
0x18001bce9  mov     edx, 334h
0x18001bcee  jmp     short loc_18001BC7E
0x18001bcf0  mov     r15d, r13d
0x18001bcf3  test    eax, eax
0x18001bcf5  jz      short loc_18001BD4F
0x18001bcf7  cmp     [rbp+arg_20], rsi
0x18001bcfb  jz      short loc_18001BD4F
0x18001bcfd  mov     rdx, [rbp+arg_20]; unsigned __int8 *
0x18001bd01  lea     r9, [rbp+var_20]; struct _EAPTLS_CONN_PROPERTIES **
0x18001bd05  mov     r8d, eax; unsigned int
0x18001bd08  mov     ecx, r10d; unsigned int
0x18001bd0b  call    ?EapTlsReadConnectionData@@YAKKPEAEKPEAPEAU_EAPTLS_CONN_PROPERTIES@@@Z; EapTlsReadConnectionData(ulong,uchar *,ulong,_EAPTLS_CONN_PROPERTIES * *)
0x18001bd10  mov     r15d, eax
0x18001bd13  test    eax, eax
0x18001bd15  jz      short loc_18001BD4B
0x18001bd17  mov     rax, cs:WPP_GLOBAL_Control
0x18001bd1e  lea     rcx, WPP_GLOBAL_Control
0x18001bd25  cmp     rax, rcx
0x18001bd28  jz      short loc_18001BD42
0x18001bd2a  mov     rcx, [rax+10h]
0x18001bd2e  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18001bd35  mov     edx, 335h
0x18001bd3a  mov     r9d, r15d
0x18001bd3d  call    WPP_SF_d
0x18001bd42  mov     rsi, [rbp+var_20]
0x18001bd46  jmp     loc_18001C2E2
0x18001bd4b  mov     rsi, [rbp+var_20]
0x18001bd4f  lea     rax, [rbp+hKey]
0x18001bd53  mov     r9d, 20019h; samDesired
0x18001bd59  xor     r8d, r8d; ulOptions
0x18001bd5c  mov     [rsp+60h+phkResult], rax; phkResult
0x18001bd61  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ra"...
0x18001bd68  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001bd6f  call    cs:__imp_RegOpenKeyExW
0x18001bd76  nop     dword ptr [rax+rax+00h]
0x18001bd7b  mov     edi, eax
0x18001bd7d  test    eax, eax
0x18001bd7f  jnz     loc_18001C29B
0x18001bd85  mov     rcx, [rbp+hKey]; hKey
0x18001bd89  lea     rax, [rbp+cbData]
0x18001bd8d  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18001bd92  lea     r9, [rbp+Type]; lpType
0x18001bd96  lea     rax, [rbp+Data]
0x18001bd9a  mov     [rsp+60h+var_10], r14
0x18001bd9f  xor     r8d, r8d; lpReserved
0x18001bda2  mov     [rsp+60h+phkResult], rax; lpData
0x18001bda7  lea     rdx, ValueName; "Properties"
0x18001bdae  mov     [rbp+cbData], 4
0x18001bdb5  call    cs:__imp_RegQueryValueExW
0x18001bdbc  nop     dword ptr [rax+rax+00h]
0x18001bdc1  test    eax, eax
0x18001bdc3  jnz     short loc_18001BDFD
0x18001bdc5  cmp     [rbp+Type], 4
0x18001bdc9  jz      short loc_18001BDF2
0x18001bdcb  mov     r15d, 65Dh
0x18001bdd1  mov     rax, cs:WPP_GLOBAL_Control
0x18001bdd8  lea     rcx, WPP_GLOBAL_Control
0x18001bddf  cmp     rax, rcx
0x18001bde2  jz      loc_18001C2DD
0x18001bde8  mov     edx, 336h
0x18001bded  jmp     loc_18001BE97
0x18001bdf2  mov     edi, dword ptr [rbp+Data]
0x18001bdf5  mov     r14d, 1Eh
0x18001bdfb  jmp     short loc_18001BE35
0x18001bdfd  cmp     eax, 2
0x18001be00  jz      short loc_18001BE2F
0x18001be02  call    cs:__imp_GetLastError
0x18001be09  nop     dword ptr [rax+rax+00h]
0x18001be0e  mov     r15d, eax
0x18001be11  mov     rax, cs:WPP_GLOBAL_Control
0x18001be18  lea     rcx, WPP_GLOBAL_Control
0x18001be1f  cmp     rax, rcx
0x18001be22  jz      loc_18001C2DD
0x18001be28  mov     edx, 337h
0x18001be2d  jmp     short loc_18001BE97
0x18001be2f  mov     edi, r13d
0x18001be32  mov     r14d, r13d
0x18001be35  mov     rcx, [rbp+hKey]; hKey
0x18001be39  lea     rax, [rbp+cbData]
0x18001be3d  xorps   xmm0, xmm0
0x18001be40  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18001be45  lea     r9, [rbp+Type]; lpType
0x18001be49  mov     [rsp+60h+phkResult], r13; lpData
0x18001be4e  xor     r8d, r8d; lpReserved
0x18001be51  lea     rdx, aExtendedproper; "ExtendedProperties"
0x18001be58  movups  xmmword ptr [rbx], xmm0
0x18001be5b  call    cs:__imp_RegQueryValueExW
0x18001be62  nop     dword ptr [rax+rax+00h]
0x18001be67  test    eax, eax
0x18001be69  jnz     loc_18001C0CC
0x18001be6f  cmp     [rbp+Type], 3
0x18001be73  jz      short loc_18001BEAF
0x18001be75  mov     r15d, 65Dh
0x18001be7b  mov     rax, cs:WPP_GLOBAL_Control
0x18001be82  lea     rcx, WPP_GLOBAL_Control
0x18001be89  cmp     rax, rcx
0x18001be8c  jz      loc_18001C2DD
0x18001be92  mov     edx, 338h
0x18001be97  mov     rcx, [rax+10h]
0x18001be9b  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18001bea2  mov     r9d, r15d
0x18001bea5  call    WPP_SF_d
0x18001beaa  jmp     loc_18001C2DD
0x18001beaf  mov     edx, [rbp+cbData]; uBytes
0x18001beb2  mov     ecx, 40h ; '@'; uFlags
0x18001beb7  call    cs:__imp_LocalAlloc
0x18001bebe  nop     dword ptr [rax+rax+00h]
0x18001bec3  mov     [rbp+var_20], rax
0x18001bec7  mov     r13, rax
0x18001beca  test    rax, rax
0x18001becd  jz      loc_18001C2CB
0x18001bed3  mov     rcx, [rbp+hKey]; hKey
0x18001bed7  lea     rax, [rbp+cbData]
0x18001bedb  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18001bee0  lea     r9, [rbp+Type]; lpType
0x18001bee4  xor     r8d, r8d; lpReserved
0x18001bee7  mov     [rsp+60h+phkResult], r13; lpData
0x18001beec  lea     rdx, aExtendedproper; "ExtendedProperties"
0x18001bef3  call    cs:__imp_RegQueryValueExW
0x18001befa  nop     dword ptr [rax+rax+00h]
0x18001beff  test    eax, eax
0x18001bf01  jz      short loc_18001BF3A
0x18001bf03  mov     r15d, eax
0x18001bf06  mov     r10, cs:WPP_GLOBAL_Control
0x18001bf0d  lea     rcx, WPP_GLOBAL_Control
0x18001bf14  cmp     r10, rcx
0x18001bf17  jz      loc_18001C2DA
0x18001bf1d  mov     rcx, [r10+10h]
0x18001bf21  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18001bf28  mov     edx, 339h
0x18001bf2d  mov     r9d, eax
0x18001bf30  call    WPP_SF_d
0x18001bf35  jmp     loc_18001C2DA
0x18001bf3a  mov     r8d, [rbp+cbData]
0x18001bf3e  lea     rcx, [rbp+arg_38]
0x18001bf42  mov     rdx, r13
0x18001bf45  mov     dword ptr [rbp+arg_38], r14d
0x18001bf49  call    ValidateExtendedMethodProperties
0x18001bf4e  cmp     eax, 1
0x18001bf51  jz      short loc_18001BF86
0x18001bf53  mov     rax, cs:WPP_GLOBAL_Control
0x18001bf5a  lea     rcx, WPP_GLOBAL_Control
0x18001bf61  cmp     rax, rcx
0x18001bf64  jz      short loc_18001BF7B
0x18001bf66  mov     rcx, [rax+10h]
0x18001bf6a  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18001bf71  mov     edx, 33Ah
0x18001bf76  call    WPP_SF_
0x18001bf7b  mov     r15d, 0Dh
0x18001bf81  jmp     loc_18001C2DA
0x18001bf86  mov     r12d, dword ptr [rbp+arg_38]
0x18001bf8a  lea     eax, [r12+r14]
0x18001bf8e  mov     [rbx], eax
0x18001bf90  test    eax, eax
0x18001bf92  jz      loc_18001C2DA
0x18001bf98  lea     rdx, [rax+rax*2]
0x18001bf9c  mov     ecx, 40h ; '@'; uFlags
0x18001bfa1  shl     rdx, 3; uBytes
0x18001bfa5  call    cs:__imp_LocalAlloc
0x18001bfac  nop     dword ptr [rax+rax+00h]
0x18001bfb1  mov     [rbx+8], rax
0x18001bfb5  test    rax, rax
0x18001bfb8  jz      loc_18001C2CB
0x18001bfbe  xor     r13d, r13d
0x18001bfc1  test    r14d, r14d
0x18001bfc4  jz      short loc_18001C03E
0x18001bfc6  xor     r8d, r8d
0x18001bfc9  lea     r9d, [r14-1]
0x18001bfcd  mov     rax, [rbx+8]
0x18001bfd1  lea     rcx, [r8+r8*2]
0x18001bfd5  lea     rdx, ds:0[rcx*8]
0x18001bfdd  xor     ecx, ecx
0x18001bfdf  bt      edi, r8d
0x18001bfe3  mov     [rdx+rax], r8d
0x18001bfe7  setb    cl
0x18001bfea  mov     rax, [rbx+8]
0x18001bfee  inc     r8d
0x18001bff1  mov     [rax+rdx+4], r13d
0x18001bff6  mov     rax, [rbx+8]
0x18001bffa  mov     dword ptr [rax+rdx+8], 4
0x18001c002  mov     rax, [rbx+8]
0x18001c006  mov     [rax+rdx+0Ch], ecx
0x18001c00a  cmp     r8d, r9d
0x18001c00d  jb      short loc_18001BFCD
0x18001c00f  mov     rax, [rbx+8]
0x18001c013  lea     rcx, [r8+r8*2]
0x18001c017  mov     dword ptr [rax+rcx*8], 1Fh
0x18001c01e  mov     rax, [rbx+8]
0x18001c022  mov     dword ptr [rax+rcx*8+4], 1
0x18001c02a  mov     rax, [rbx+8]
0x18001c02e  mov     dword ptr [rax+rcx*8+8], 4
0x18001c036  mov     rax, [rbx+8]
0x18001c03a  mov     [rax+rcx*8+0Ch], edi
0x18001c03e  mov     r12, [rbp+var_20]
0x18001c042  lea     r11, __ImageBase
0x18001c049  mov     edi, r14d
0x18001c04c  mov     eax, [rbx]
0x18001c04e  cmp     edi, eax
0x18001c050  jnb     loc_18001C1B0
0x18001c056  mov     eax, edi
0x18001c058  lea     rcx, [rax+rax*2]
0x18001c05c  mov     eax, [r13+r12+0]
0x18001c061  lea     rdx, ds:0[rcx*8]
0x18001c069  mov     rcx, [rbx+8]
0x18001c06d  mov     [rbp+arg_38], rdx
0x18001c071  mov     [rdx+rcx], eax
0x18001c074  mov     r10, [rbx+8]
0x18001c078  movsxd  rcx, dword ptr [r10+rdx]
0x18001c07c  cmp     ecx, 0FFh
0x18001c082  jg      loc_18001C2DA
0x18001c088  add     r13d, 4
0x18001c08c  mov     r8d, r13d
0x18001c08f  add     r8, r12
0x18001c092  mov     [rbp+var_20], r8
0x18001c096  lea     r9d, [r13+4]
0x18001c09a  mov     r13d, r9d
0x18001c09d  cmp     ecx, 0FFh
0x18001c0a3  jz      loc_18001C148
0x18001c0a9  cmp     ecx, 1Ch
0x18001c0ac  ja      loc_18001C2DA
0x18001c0b2  movzx   eax, ds:rva byte_18001C374[r11+rcx]
0x18001c0bb  mov     ecx, ds:(jpt_18001C0C6 - 180000000h)[r11+rax*4]; switch 1 cases
0x18001c0c3  add     rcx, r11
0x18001c0c6  jmp     rcx; switch jump
0x18001c0cc  mov     [rbp+var_20], r13
0x18001c0d0  cmp     eax, 2
0x18001c0d3  jz      loc_18001BF8A
0x18001c0d9  mov     r15d, eax
0x18001c0dc  mov     r10, cs:WPP_GLOBAL_Control
0x18001c0e3  lea     rcx, WPP_GLOBAL_Control
0x18001c0ea  cmp     r10, rcx
0x18001c0ed  jz      loc_18001C2DD
0x18001c0f3  mov     rcx, [r10+10h]
0x18001c0f7  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18001c0fe  mov     edx, 33Bh
0x18001c103  mov     r9d, eax
0x18001c106  call    WPP_SF_d
0x18001c10b  jmp     loc_18001C2DD
0x18001c110  mov     dword ptr [r10+rdx+4], 0; jumptable 000000018001C0C6 case 0
0x18001c119  mov     eax, [r8]
0x18001c11c  mov     rcx, [rbx+8]
0x18001c120  mov     [rcx+rdx+8], eax
0x18001c124  mov     r8d, [r9+r12]
0x18001c128  cmp     r8d, 1
0x18001c12c  ja      loc_18001C2DA
  ... truncated ...
```
