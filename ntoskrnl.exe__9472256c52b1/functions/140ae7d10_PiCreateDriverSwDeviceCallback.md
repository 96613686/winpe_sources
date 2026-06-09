# PiCreateDriverSwDeviceCallback

- ea: `0x140ae7d10`
- end: `0x140ae8747`
- name: `PiCreateDriverSwDeviceCallback`
- size: `2615`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, _DWORD *)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140403380`
- `0x140471688`
- `0x14048eb48`
- `0x140544600`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406f7380`
- `0x140774ed0`
- `0x14086f4e8`
- `0x1408756c0`
- `0x14087852c`
- `0x140878f34`
- `0x1408ee610`
- `0x1408efdd0`
- `0x1408f6a50`
- `0x140900d30`
- `0x14094b120`
- `0x1409b84d0`
- `0x1409bb9d0`
- `0x140a47eac`
- `0x140a4acf4`
- `0x140ae7d10`
- `0x140b04c04`
- `0x140bb1410`
- `0x140bb19d0`
- `0x140bb19f0`

## string_xrefs

- `0x140ae8389`: `Security`
- `0x140ae7e4a`: `CompatibleIds`

## pseudocode

```c
__int64 __fastcall PiCreateDriverSwDeviceCallback(__int64 a1, __int64 a2, const WCHAR *a3, _DWORD *a4)
{
  __int64 v5; // rcx
  unsigned int v6; // r12d
  _DWORD *v7; // r13
  ULONG v8; // r15d
  WCHAR *Pool2; // rdi
  void *v10; // rsi
  __int64 v11; // rax
  int RegistryValues; // ebx
  int v13; // r8d
  PCWSTR v14; // r15
  int v15; // ecx
  __int64 v17; // r13
  __int64 v18; // r14
  ULONG v19; // r15d
  const wchar_t *i; // rsi
  __int64 v21; // rax
  const WCHAR *v22; // rcx
  NTSTATUS RegistryValue; // eax
  PVOID v24; // r12
  __int64 v25; // rax
  NTSTATUS v26; // eax
  int v27; // r15d
  unsigned int v28; // r14d
  char *v29; // rsi
  int GenericStorePropertyKeys; // eax
  unsigned int v31; // eax
  unsigned int v32; // r15d
  _QWORD *v33; // r14
  unsigned int v34; // r13d
  __int64 v35; // r12
  char *v36; // rcx
  __int128 v37; // xmm0
  unsigned int v38; // eax
  void *v39; // rcx
  __int64 v40; // rax
  void *v41; // rcx
  ULONG v42; // [rsp+20h] [rbp-E0h]
  unsigned int v43; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR SourceString; // [rsp+78h] [rbp-88h]
  unsigned int v45; // [rsp+80h] [rbp-80h]
  _DWORD *v46; // [rsp+88h] [rbp-78h] BYREF
  _DWORD *v47; // [rsp+90h] [rbp-70h]
  ULONG HashValue; // [rsp+98h] [rbp-68h] BYREF
  int v49; // [rsp+9Ch] [rbp-64h] BYREF
  char *v50; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp-58h] BYREF
  int v52; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-48h]
  UNICODE_STRING UnicodeString; // [rsp+C0h] [rbp-40h] BYREF
  UNICODE_STRING v55; // [rsp+D0h] [rbp-30h] BYREF
  UNICODE_STRING GuidString; // [rsp+E0h] [rbp-20h] BYREF
  PVOID v57; // [rsp+F0h] [rbp-10h] BYREF
  UNICODE_STRING String2; // [rsp+F8h] [rbp-8h] BYREF
  UNICODE_STRING v59; // [rsp+108h] [rbp+8h] BYREF
  UNICODE_STRING v60; // [rsp+118h] [rbp+18h] BYREF
  UNICODE_STRING DestinationString; // [rsp+128h] [rbp+28h] BYREF
  PVOID P[2]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v63; // [rsp+148h] [rbp+48h]
  PCWCH String1[2]; // [rsp+150h] [rbp+50h]
  GUID Guid; // [rsp+160h] [rbp+60h] BYREF
  int v66[4]; // [rsp+170h] [rbp+70h] BYREF
  const wchar_t *v67; // [rsp+180h] [rbp+80h]
  UNICODE_STRING *p_UnicodeString; // [rsp+188h] [rbp+88h]
  int v69; // [rsp+190h] [rbp+90h]
  int v70; // [rsp+1B0h] [rbp+B0h]
  const wchar_t *v71; // [rsp+1B8h] [rbp+B8h]
  UNICODE_STRING *v72; // [rsp+1C0h] [rbp+C0h]
  int v73; // [rsp+1C8h] [rbp+C8h]
  int v74; // [rsp+1E8h] [rbp+E8h]
  const wchar_t *v75; // [rsp+1F0h] [rbp+F0h]
  UNICODE_STRING *p_GuidString; // [rsp+1F8h] [rbp+F8h]
  int v77; // [rsp+200h] [rbp+100h]
  int v78; // [rsp+220h] [rbp+120h]
  const wchar_t *v79; // [rsp+228h] [rbp+128h]
  int *v80; // [rsp+230h] [rbp+130h]
  int v81; // [rsp+238h] [rbp+138h]
  int v82; // [rsp+258h] [rbp+158h]
  const wchar_t *v83; // [rsp+260h] [rbp+160h]
  UNICODE_STRING *v84; // [rsp+268h] [rbp+168h]
  int v85; // [rsp+270h] [rbp+170h]
  int v86; // [rsp+290h] [rbp+190h]
  const wchar_t *v87; // [rsp+298h] [rbp+198h]
  UNICODE_STRING *v88; // [rsp+2A0h] [rbp+1A0h]
  int v89; // [rsp+2A8h] [rbp+1A8h]

  v63 = a1;
  v47 = a4;
  SourceString = a3;
  v5 = 0;
  v52 = 1;
  v6 = 0;
  Handle = 0;
  v49 = 0;
  v7 = a4;
  LODWORD(v50) = 0;
  HashValue = 0;
  v46 = 0;
  v8 = 0;
  v57 = 0;
  Pool2 = 0;
  v43 = 0;
  v10 = 0;
  UnicodeString = 0;
  v55 = 0;
  GuidString = 0;
  Guid = 0;
  v59 = 0;
  v60 = 0;
  String2 = 0;
  DestinationString = 0;
  *(_OWORD *)P = 0;
  if ( a1 )
  {
    v11 = *(_QWORD *)(a1 + 224);
    if ( v11 )
      v5 = *(_QWORD *)(v11 + 8);
  }
  RegistryValues = RegRtlOpenKeyTransacted(a2, a3, 0, 131097, &Handle, v5);
  if ( RegistryValues < 0 )
    goto LABEL_27;
  memset_0(v66, 0, 0x188u);
  v81 = 0x4000000;
  v66[2] = 304;
  v69 = 117440512;
  v67 = L"HardwareIds";
  v70 = 304;
  p_UnicodeString = &UnicodeString;
  v73 = 117440512;
  v71 = L"CompatibleIds";
  v74 = 288;
  v72 = &v55;
  v77 = 0x1000000;
  v75 = L"ContainerId";
  p_GuidString = &GuidString;
  v79 = L"Capabilities";
  v80 = &v49;
  v83 = L"Description";
  v84 = &v59;
  v87 = L"LocationInfo";
  v78 = 288;
  v82 = 288;
  v85 = 0x1000000;
  v86 = 288;
  v89 = 0x1000000;
  v88 = &v60;
  RegistryValues = RtlpQueryRegistryValues(3221225472LL, (const WCHAR *)Handle, v66, 0, v42, 1);
  if ( RegistryValues < 0 )
    goto LABEL_94;
  if ( UnicodeString.Buffer && UnicodeString.Length <= 2u )
    RtlFreeAnsiString(&UnicodeString);
  if ( v55.Buffer && v55.Length <= 2u )
    RtlFreeAnsiString(&v55);
  if ( !GuidString.Buffer )
    goto LABEL_17;
  if ( GuidString.Length < 2u )
    RtlFreeAnsiString(&GuidString);
  if ( !GuidString.Buffer || RtlGUIDFromString(&GuidString, &Guid) < 0 )
LABEL_17:
    Guid = 0;
  if ( v59.Buffer && v59.Length < 2u )
    RtlFreeAnsiString(&v59);
  if ( v60.Buffer && v60.Length < 2u )
    RtlFreeAnsiString(&v60);
  if ( !UnicodeString.Buffer && !v55.Buffer )
  {
    RegistryValues = -1073741637;
    goto LABEL_27;
  }
  v17 = *(_QWORD *)v7;
  String1[0] = UnicodeString.Buffer;
  v53 = 0x300000002LL;
  v18 = -1;
  String1[1] = v55.Buffer;
  v45 = 0;
  while ( (PVOID)v17 != IopRootDeviceNode )
  {
    if ( *(PDRIVER_OBJECT *)(*(_QWORD *)(v17 + 32) + 8LL) == PiSwDeviceDriverObject )
    {
      RtlInitUnicodeString(&DestinationString, L"SWD\\");
      if ( RtlPrefixUnicodeString(&DestinationString, (PCUNICODE_STRING)(v17 + 40), 1u) )
      {
        RtlInitUnicodeString(
          &String2,
          (PCWSTR)(*(_QWORD *)(v17 + 48) + 2 * ((unsigned __int64)DestinationString.Length >> 1)));
        RtlInitUnicodeString(&DestinationString, L"DRIVERENUM");
        if ( RtlPrefixUnicodeString(&DestinationString, &String2, 1u) )
        {
          if ( String2.Buffer[(unsigned __int64)DestinationString.Length >> 1] == 92 )
          {
            if ( !v8 )
            {
              RegistryValues = PnpGenerateDeviceIdsHash(UnicodeString.Buffer, v55.Buffer, &v50);
              if ( RegistryValues < 0 )
                goto LABEL_93;
              if ( (v49 & 8) != 0 )
              {
                v19 = (unsigned int)v50;
              }
              else
              {
                RtlInitUnicodeString(&String2, &PiSwGenericRawCompatibleId);
                RegistryValues = RtlHashUnicodeString(&String2, 1u, 0, &HashValue);
                if ( RegistryValues < 0 )
                  goto LABEL_93;
                v19 = HashValue + (_DWORD)v50;
              }
              RtlInitUnicodeString(&String2, &PiSwGenericCompatibleId);
              RegistryValues = RtlHashUnicodeString(&String2, 1u, 0, &HashValue);
              if ( RegistryValues < 0 )
                goto LABEL_93;
              v8 = HashValue + v19;
              LODWORD(v50) = v8;
            }
            if ( *(_DWORD *)(v17 + 684) == v8 )
            {
              if ( Pool2
                || (v45 = 2048, LODWORD(v10) = 2048, (Pool2 = (WCHAR *)ExAllocatePool2(256, 2048, 538996816)) != 0) )
              {
                do
                {
                  v43 = (unsigned int)v10;
                  if ( (int)CmGetDeviceRegProp(
                              *(__int64 *)&PiPnpRtlCtx,
                              *(_QWORD *)(v17 + 48),
                              0,
                              *((_DWORD *)&v53 + v6),
                              (__int64)&v52,
                              (__int64)Pool2,
                              (__int64)&v43,
                              0) < 0
                    || v52 != 7
                    || v43 < 2 )
                  {
                    *Pool2 = 0;
                  }
                  if ( v6 == 1 )
                  {
                    for ( i = Pool2; *i; i += v21 + 1 )
                    {
                      if ( !wcsicmp(i, &PiSwGenericRawCompatibleId) || !wcsicmp(i, &PiSwGenericCompatibleId) )
                      {
                        *i = 0;
                        break;
                      }
                      v21 = -1;
                      do
                        ++v21;
                      while ( i[v21] );
                    }
                    LODWORD(v10) = v45;
                  }
                  v22 = String1[v6];
                  if ( v22 )
                  {
                    if ( !(unsigned __int8)PnpCompareMultiSz(v22, Pool2, 1u) )
                      goto LABEL_87;
                  }
                  else if ( *Pool2 )
                  {
LABEL_87:
                    v6 = 0;
                    goto LABEL_88;
                  }
                  ++v6;
                }
                while ( v6 < 2 );
                v10 = v46;
                RegistryValues = -1073740028;
                v7 = v47;
LABEL_27:
                v14 = SourceString;
                goto LABEL_28;
              }
              RegistryValues = -1073741670;
LABEL_93:
              v10 = v46;
              goto LABEL_94;
            }
          }
        }
      }
    }
LABEL_88:
    v17 = *(_QWORD *)(v17 + 16);
  }
  RegistryValue = IopGetRegistryValue(Handle, L"Security", 0, &v46);
  v10 = v46;
  RegistryValues = RegistryValue;
  if ( RegistryValue < 0 )
  {
    if ( RegistryValue == -1073741772 )
    {
      v53 = 0;
      v45 = 0;
      goto LABEL_101;
    }
LABEL_94:
    v7 = v47;
    goto LABEL_27;
  }
  if ( v46[1] != 3 || (v45 = v46[3], v45 < 0x28) )
  {
    RegistryValues = -1073741823;
    goto LABEL_94;
  }
  v53 = (__int64)v46 + (unsigned int)v46[2];
LABEL_101:
  v7 = v47;
  if ( *(PVOID *)v47 == IopRootDeviceNode )
  {
    v14 = SourceString;
    if ( !RtlCreateUnicodeString((PUNICODE_STRING)P, SourceString) )
    {
      RegistryValues = -1073741670;
      goto LABEL_28;
    }
LABEL_110:
    v27 = v63;
    v28 = 0;
    v29 = 0;
    while ( 1 )
    {
      GenericStorePropertyKeys = PnpGetGenericStorePropertyKeys(
                                   v27,
                                   (_DWORD)Handle,
                                   0,
                                   0,
                                   (__int64)v29,
                                   v28,
                                   (__int64)&v43);
      RegistryValues = GenericStorePropertyKeys;
      if ( GenericStorePropertyKeys != -1073741789 )
        break;
      v31 = v43;
      if ( v43 <= v28 )
      {
        RegistryValues = -1073741595;
        goto LABEL_142;
      }
      if ( v29 )
      {
        ExFreePoolWithTag(v29, 0);
        v31 = v43;
      }
      v28 = v31;
      v29 = (char *)ExAllocatePool2(256, 20LL * v31, 538996816);
      if ( !v29 )
      {
        v10 = v46;
        RegistryValues = -1073741670;
        goto LABEL_27;
      }
    }
    if ( GenericStorePropertyKeys < 0 )
      goto LABEL_142;
    v32 = v43;
    if ( v43 )
    {
      v33 = (_QWORD *)ExAllocatePool2(256, 48LL * v43, 538996816);
      if ( !v33 )
      {
        RegistryValues = -1073741670;
LABEL_142:
        if ( v29 )
          ExFreePoolWithTag(v29, 0);
        goto LABEL_93;
      }
      v34 = 0;
LABEL_125:
      v35 = 6LL * v34;
      v36 = &v29[20 * v34];
      v37 = *(_OWORD *)v36;
      v50 = v36;
      *(_OWORD *)&v33[v35] = v37;
      v33[v35 + 2] = *((unsigned int *)v36 + 4);
      while ( 1 )
      {
        RegistryValues = PnpGetGenericStoreProperty(
                           v63,
                           (_DWORD)Handle,
                           0,
                           (_DWORD)v36,
                           (__int64)&v33[v35 + 4],
                           v33[v35 + 5],
                           HIDWORD(v33[v35 + 4]),
                           (__int64)&v43);
        v38 = v43;
        if ( RegistryValues != -1073741789 )
        {
          HIDWORD(v33[v35 + 4]) = v43;
          v6 = 0;
          if ( RegistryValues < 0 )
            goto LABEL_136;
          if ( ++v34 >= v32 )
          {
            v7 = v47;
            goto LABEL_135;
          }
          goto LABEL_125;
        }
        if ( v43 <= HIDWORD(v33[v35 + 4]) )
          break;
        v39 = (void *)v33[v35 + 5];
        if ( v39 )
        {
          ExFreePoolWithTag(v39, 0);
          v38 = v43;
        }
        HIDWORD(v33[v35 + 4]) = v38;
        v40 = ExAllocatePool2(256, v43, 538996816);
        v33[v35 + 5] = v40;
        if ( !v40 )
        {
          RegistryValues = -1073741670;
          goto LABEL_145;
        }
        LODWORD(v36) = (_DWORD)v50;
      }
      RegistryValues = -1073741595;
LABEL_145:
      v6 = 0;
    }
    else
    {
      v33 = 0;
LABEL_135:
      RegistryValues = PiSwStartCreate(
                         (unsigned int)L"DRIVERENUM",
                         *(_QWORD *)(*(_QWORD *)v7 + 48LL),
                         P[1],
                         UnicodeString.Buffer,
                         (__int64)v55.Buffer,
                         (unsigned __int64)&Guid & -(__int64)(GuidString.Buffer != 0),
                         v49,
                         (__int64)v59.Buffer,
                         (__int64)v60.Buffer,
                         v53,
                         v45,
                         (__int64)v33,
                         v32);
LABEL_136:
      if ( !v33 )
        goto LABEL_142;
    }
    if ( v32 )
    {
      do
      {
        v41 = (void *)v33[6 * v6 + 5];
        if ( v41 )
          ExFreePoolWithTag(v41, 0);
        ++v6;
      }
      while ( v6 < v32 );
    }
    ExFreePoolWithTag(v33, 0);
    goto LABEL_142;
  }
  RegistryValues = PipMakeGloballyUniqueId(*(_QWORD *)(*(_QWORD *)v47 + 32LL), 0, (wchar_t **)&v57);
  if ( RegistryValues < 0 )
    goto LABEL_27;
  v24 = v57;
  v25 = -1;
  do
    ++v25;
  while ( *((_WORD *)v57 + v25) );
  v14 = SourceString;
  do
    ++v18;
  while ( SourceString[v18] );
  WORD1(P[0]) = 2 * (v25 + 2 + v18);
  P[1] = (PVOID)ExAllocatePool2(256, WORD1(P[0]), 1735554131);
  if ( !P[1] )
  {
    RegistryValues = -1073741670;
    goto LABEL_28;
  }
  v26 = RtlUnicodeStringPrintf((PUNICODE_STRING)P, L"%ws&%ws", v14, v24);
  v6 = 0;
  RegistryValues = v26;
  if ( v26 >= 0 )
    goto LABEL_110;
LABEL_28:
  if ( P[1] )
    ExFreePool(P[1]);
  if ( v57 )
    ExFreePoolWithTag(v57, 0);
  if ( UnicodeString.Buffer )
  {
    ExFreePool(UnicodeString.Buffer);
    UnicodeString = 0;
  }
  if ( v55.Buffer )
  {
    ExFreePool(v55.Buffer);
    v55 = 0;
  }
  if ( GuidString.Buffer )
  {
    ExFreePool(GuidString.Buffer);
    GuidString = 0;
  }
  if ( v59.Buffer )
  {
    ExFreePool(v59.Buffer);
    v59 = 0;
  }
  if ( v60.Buffer )
  {
    ExFreePool(v60.Buffer);
    v60 = 0;
  }
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  v15 = (int)Handle;
  if ( Handle )
    ZwClose(Handle);
  if ( RegistryValues < 0 && (byte_140ED9FEC & 4) != 0 )
    McTemplateK0zzd_EtwWriteTransfer(
      v15,
      (unsigned int)KMPnPEvt_CreateDriverSwDevice_Failure,
      v13,
      *(_QWORD *)(*(_QWORD *)v7 + 48LL),
      (__int64)v14,
      RegistryValues);
  if ( (int)v7[2] >= 0 )
    v7[2] = RegistryValues;
  return 0;
}

```

## disassembly

```asm
0x140ae7d10  push    rbp
0x140ae7d12  push    rbx
0x140ae7d13  push    rsi
0x140ae7d14  push    rdi
0x140ae7d15  push    r12
0x140ae7d17  push    r13
0x140ae7d19  push    r14
0x140ae7d1b  push    r15
0x140ae7d1d  lea     rbp, [rsp-218h]
0x140ae7d25  sub     rsp, 318h
0x140ae7d2c  mov     rax, cs:__security_cookie
0x140ae7d33  xor     rax, rsp
0x140ae7d36  mov     [rbp+250h+var_50], rax
0x140ae7d3d  xorps   xmm0, xmm0
0x140ae7d40  mov     [rbp+250h+var_208], rcx
0x140ae7d44  xorps   xmm1, xmm1
0x140ae7d47  mov     [rbp+250h+var_2C0], r9
0x140ae7d4b  mov     rax, rcx
0x140ae7d4e  mov     [rsp+350h+SourceString], r8
0x140ae7d53  xor     ecx, ecx
0x140ae7d55  mov     [rbp+250h+var_2A0], 1
0x140ae7d5c  xor     r12d, r12d
0x140ae7d5f  mov     [rbp+250h+Handle], rcx
0x140ae7d63  mov     [rbp+250h+var_2B4], ecx
0x140ae7d66  mov     r13, r9
0x140ae7d69  mov     dword ptr [rbp+250h+var_2B0], ecx
0x140ae7d6c  mov     r11, r8
0x140ae7d6f  mov     [rbp+250h+HashValue], ecx
0x140ae7d72  mov     r10, rdx
0x140ae7d75  mov     [rbp+250h+var_2C8], rcx
0x140ae7d79  mov     r15d, ecx
0x140ae7d7c  mov     [rbp+250h+var_260], rcx
0x140ae7d80  mov     edi, ecx
0x140ae7d82  mov     [rsp+350h+var_2E0], r12d
0x140ae7d87  mov     esi, ecx
0x140ae7d89  movups  xmmword ptr [rbp+250h+UnicodeString.Length], xmm0
0x140ae7d8d  movups  xmmword ptr [rbp+250h+var_280.Length], xmm1
0x140ae7d91  movups  xmmword ptr [rbp+250h+GuidString.Length], xmm0
0x140ae7d95  movups  xmmword ptr [rbp+250h+Guid.Data1], xmm1
0x140ae7d99  movups  xmmword ptr [rbp+250h+var_248.Length], xmm0
0x140ae7d9d  movups  xmmword ptr [rbp+250h+var_238.Length], xmm1
0x140ae7da1  movups  xmmword ptr [rbp+250h+String2.Length], xmm0
0x140ae7da5  movups  xmmword ptr [rbp+250h+DestinationString.Length], xmm1
0x140ae7da9  movups  xmmword ptr [rbp+250h+P], xmm0
0x140ae7dad  test    rax, rax
0x140ae7db0  jz      short loc_140AE7DC2
0x140ae7db2  mov     rax, [rax+0E0h]
0x140ae7db9  test    rax, rax
0x140ae7dbc  jz      short loc_140AE7DC2
0x140ae7dbe  mov     rcx, [rax+8]
0x140ae7dc2  mov     qword ptr [rsp+350h+var_328], rcx
0x140ae7dc7  lea     rax, [rbp+250h+Handle]
0x140ae7dcb  mov     rcx, r10
0x140ae7dce  mov     qword ptr [rsp+350h+var_330], rax; ULONG
0x140ae7dd3  mov     r9d, 20019h
0x140ae7dd9  xor     r8d, r8d
0x140ae7ddc  mov     rdx, r11
0x140ae7ddf  call    _RegRtlOpenKeyTransacted
0x140ae7de4  mov     ebx, eax
0x140ae7de6  test    eax, eax
0x140ae7de8  js      loc_140AE7FC1
0x140ae7dee  xor     edx, edx; Val
0x140ae7df0  lea     rcx, [rbp+250h+var_1E0]; void *
0x140ae7df4  mov     r8d, 188h; Size
0x140ae7dfa  call    memset_0
0x140ae7dff  mov     edx, 130h
0x140ae7e04  mov     [rbp+250h+var_118], 4000000h
0x140ae7e0e  mov     ecx, 7000000h
0x140ae7e13  mov     [rbp+250h+var_1D8], edx
0x140ae7e16  mov     [rbp+250h+var_1C0], ecx
0x140ae7e1c  lea     rax, aHardwareids; "HardwareIds"
0x140ae7e23  mov     [rbp+250h+var_1D0], rax
0x140ae7e2a  lea     r8, [rbp+250h+var_1E0]; int
0x140ae7e2e  mov     [rbp+250h+var_1A0], edx
0x140ae7e34  lea     rax, [rbp+250h+UnicodeString]
0x140ae7e38  mov     [rbp+250h+var_1C8], rax
0x140ae7e3f  mov     edx, 120h
0x140ae7e44  mov     [rbp+250h+var_188], ecx
0x140ae7e4a  lea     rax, aCompatibleids_0; "CompatibleIds"
0x140ae7e51  mov     [rbp+250h+var_198], rax
0x140ae7e58  mov     ecx, 1000000h
0x140ae7e5d  lea     rax, [rbp+250h+var_280]
0x140ae7e61  mov     [rbp+250h+var_168], edx
0x140ae7e67  mov     [rbp+250h+var_190], rax
0x140ae7e6e  xor     r9d, r9d; int
0x140ae7e71  lea     rax, aContainerid_1; "ContainerId"
0x140ae7e78  mov     [rbp+250h+var_150], ecx
0x140ae7e7e  mov     [rbp+250h+var_160], rax
0x140ae7e85  lea     rax, [rbp+250h+GuidString]
0x140ae7e89  mov     [rbp+250h+var_158], rax
0x140ae7e90  lea     rax, aCapabilities_1; "Capabilities"
0x140ae7e97  mov     [rbp+250h+var_128], rax
0x140ae7e9e  lea     rax, [rbp+250h+var_2B4]
0x140ae7ea2  mov     [rbp+250h+var_120], rax
0x140ae7ea9  lea     rax, aDescription_0; "Description"
0x140ae7eb0  mov     [rbp+250h+var_F0], rax
0x140ae7eb7  lea     rax, [rbp+250h+var_248]
0x140ae7ebb  mov     [rbp+250h+var_E8], rax
0x140ae7ec2  lea     rax, aLocationinfo; "LocationInfo"
0x140ae7ec9  mov     [rbp+250h+var_B8], rax
0x140ae7ed0  lea     rax, [rbp+250h+var_238]
0x140ae7ed4  mov     [rbp+250h+var_130], edx
0x140ae7eda  mov     [rbp+250h+var_F8], edx
0x140ae7ee0  mov     [rbp+250h+var_E0], ecx
0x140ae7ee6  mov     [rbp+250h+var_C0], edx
0x140ae7eec  mov     rdx, [rbp+250h+Handle]; int
0x140ae7ef0  mov     [rbp+250h+var_A8], ecx
0x140ae7ef6  mov     ecx, 0C0000000h; int
0x140ae7efb  mov     [rbp+250h+var_B0], rax
0x140ae7f02  mov     [rsp+350h+var_328], 1; char
0x140ae7f07  call    RtlpQueryRegistryValues
0x140ae7f0c  mov     ebx, eax
0x140ae7f0e  test    eax, eax
0x140ae7f10  js      loc_140AE8371
0x140ae7f16  mov     r14d, 2
0x140ae7f1c  cmp     [rbp+250h+UnicodeString.Buffer], r12
0x140ae7f20  jz      short loc_140AE7F32
0x140ae7f22  cmp     [rbp+250h+UnicodeString.Length], r14w
0x140ae7f27  ja      short loc_140AE7F32
0x140ae7f29  lea     rcx, [rbp+250h+UnicodeString]; UnicodeString
0x140ae7f2d  call    RtlFreeAnsiString
0x140ae7f32  cmp     [rbp+250h+var_280.Buffer], r12
0x140ae7f36  jz      short loc_140AE7F48
0x140ae7f38  cmp     [rbp+250h+var_280.Length], r14w
0x140ae7f3d  ja      short loc_140AE7F48
0x140ae7f3f  lea     rcx, [rbp+250h+var_280]; UnicodeString
0x140ae7f43  call    RtlFreeAnsiString
0x140ae7f48  cmp     [rbp+250h+GuidString.Buffer], r12
0x140ae7f4c  jz      short loc_140AE7F75
0x140ae7f4e  cmp     [rbp+250h+GuidString.Length], r14w
0x140ae7f53  jnb     short loc_140AE7F5E
0x140ae7f55  lea     rcx, [rbp+250h+GuidString]; UnicodeString
0x140ae7f59  call    RtlFreeAnsiString
0x140ae7f5e  cmp     [rbp+250h+GuidString.Buffer], r12
0x140ae7f62  jz      short loc_140AE7F75
0x140ae7f64  lea     rdx, [rbp+250h+Guid]; Guid
0x140ae7f68  lea     rcx, [rbp+250h+GuidString]; GuidString
0x140ae7f6c  call    RtlGUIDFromString
0x140ae7f71  test    eax, eax
0x140ae7f73  jns     short loc_140AE7F7C
0x140ae7f75  xorps   xmm0, xmm0
0x140ae7f78  movups  xmmword ptr [rbp+250h+Guid.Data1], xmm0
0x140ae7f7c  cmp     [rbp+250h+var_248.Buffer], r12
0x140ae7f80  jz      short loc_140AE7F92
0x140ae7f82  cmp     [rbp+250h+var_248.Length], r14w
0x140ae7f87  jnb     short loc_140AE7F92
0x140ae7f89  lea     rcx, [rbp+250h+var_248]; UnicodeString
0x140ae7f8d  call    RtlFreeAnsiString
0x140ae7f92  cmp     [rbp+250h+var_238.Buffer], r12
0x140ae7f96  jz      short loc_140AE7FA8
0x140ae7f98  cmp     [rbp+250h+var_238.Length], r14w
0x140ae7f9d  jnb     short loc_140AE7FA8
0x140ae7f9f  lea     rcx, [rbp+250h+var_238]; UnicodeString
0x140ae7fa3  call    RtlFreeAnsiString
0x140ae7fa8  cmp     [rbp+250h+UnicodeString.Buffer], r12
0x140ae7fac  jnz     loc_140AE80D3
0x140ae7fb2  cmp     [rbp+250h+var_280.Buffer], r12
0x140ae7fb6  jnz     loc_140AE80D3
0x140ae7fbc  mov     ebx, 0C00000BBh
0x140ae7fc1  mov     r15, [rsp+350h+SourceString]
0x140ae7fc6  mov     rcx, [rbp+250h+P+8]; P
0x140ae7fca  test    rcx, rcx
0x140ae7fcd  jz      short loc_140AE7FD4
0x140ae7fcf  call    ExFreePool
0x140ae7fd4  mov     rcx, [rbp+250h+var_260]; P
0x140ae7fd8  test    rcx, rcx
0x140ae7fdb  jz      short loc_140AE7FE4
0x140ae7fdd  xor     edx, edx; Tag
0x140ae7fdf  call    ExFreePoolWithTag
0x140ae7fe4  mov     rcx, [rbp+250h+UnicodeString.Buffer]; P
0x140ae7fe8  test    rcx, rcx
0x140ae7feb  jz      short loc_140AE7FF9
0x140ae7fed  call    ExFreePool
0x140ae7ff2  xorps   xmm0, xmm0
0x140ae7ff5  movups  xmmword ptr [rbp+250h+UnicodeString.Length], xmm0
0x140ae7ff9  mov     rcx, [rbp+250h+var_280.Buffer]; P
0x140ae7ffd  test    rcx, rcx
0x140ae8000  jz      short loc_140AE800E
0x140ae8002  call    ExFreePool
0x140ae8007  xorps   xmm0, xmm0
0x140ae800a  movups  xmmword ptr [rbp+250h+var_280.Length], xmm0
0x140ae800e  mov     rcx, [rbp+250h+GuidString.Buffer]; P
0x140ae8012  test    rcx, rcx
0x140ae8015  jz      short loc_140AE8023
0x140ae8017  call    ExFreePool
0x140ae801c  xorps   xmm0, xmm0
0x140ae801f  movups  xmmword ptr [rbp+250h+GuidString.Length], xmm0
0x140ae8023  mov     rcx, [rbp+250h+var_248.Buffer]; P
0x140ae8027  test    rcx, rcx
0x140ae802a  jz      short loc_140AE8038
0x140ae802c  call    ExFreePool
0x140ae8031  xorps   xmm0, xmm0
0x140ae8034  movups  xmmword ptr [rbp+250h+var_248.Length], xmm0
0x140ae8038  mov     rcx, [rbp+250h+var_238.Buffer]; P
0x140ae803c  test    rcx, rcx
0x140ae803f  jz      short loc_140AE804D
0x140ae8041  call    ExFreePool
0x140ae8046  xorps   xmm0, xmm0
0x140ae8049  movups  xmmword ptr [rbp+250h+var_238.Length], xmm0
0x140ae804d  test    rsi, rsi
0x140ae8050  jz      short loc_140AE805C
0x140ae8052  xor     edx, edx; Tag
0x140ae8054  mov     rcx, rsi; P
0x140ae8057  call    ExFreePoolWithTag
0x140ae805c  test    rdi, rdi
0x140ae805f  jz      short loc_140AE806B
0x140ae8061  xor     edx, edx; Tag
0x140ae8063  mov     rcx, rdi; P
0x140ae8066  call    ExFreePoolWithTag
0x140ae806b  mov     rcx, [rbp+250h+Handle]; Handle
0x140ae806f  test    rcx, rcx
0x140ae8072  jz      short loc_140AE8079
0x140ae8074  call    ZwClose
0x140ae8079  test    ebx, ebx
0x140ae807b  jns     short loc_140AE80A3
0x140ae807d  test    cs:byte_140ED9FEC, 4
0x140ae8084  jz      short loc_140AE80A3
0x140ae8086  mov     r9, [r13+0]
0x140ae808a  lea     rdx, KMPnPEvt_CreateDriverSwDevice_Failure
0x140ae8091  mov     dword ptr [rsp+350h+var_328], ebx
0x140ae8095  mov     qword ptr [rsp+350h+var_330], r15
0x140ae809a  mov     r9, [r9+30h]
0x140ae809e  call    McTemplateK0zzd_EtwWriteTransfer
0x140ae80a3  cmp     [r13+8], r12d
0x140ae80a7  jl      short loc_140AE80AD
0x140ae80a9  mov     [r13+8], ebx
0x140ae80ad  xor     eax, eax
0x140ae80af  mov     rcx, [rbp+250h+var_50]
0x140ae80b6  xor     rcx, rsp; StackCookie
0x140ae80b9  call    __security_check_cookie
0x140ae80be  add     rsp, 318h
0x140ae80c5  pop     r15
0x140ae80c7  pop     r14
0x140ae80c9  pop     r13
0x140ae80cb  pop     r12
0x140ae80cd  pop     rdi
0x140ae80ce  pop     rsi
0x140ae80cf  pop     rbx
0x140ae80d0  pop     rbp
0x140ae80d1  retn
0x140ae80d3  mov     rax, [rbp+250h+UnicodeString.Buffer]
0x140ae80d7  mov     r13, [r13+0]
0x140ae80db  mov     [rbp+250h+String1], rax
0x140ae80df  mov     rax, [rbp+250h+var_280.Buffer]
0x140ae80e3  mov     dword ptr [rbp+250h+var_298], r14d
0x140ae80e7  or      r14, 0FFFFFFFFFFFFFFFFh
0x140ae80eb  mov     [rbp+250h+var_1F8], rax
0x140ae80ef  mov     [rbp+250h+var_2D0], r12d
0x140ae80f3  mov     dword ptr [rbp+250h+var_298+4], 3
0x140ae80fa  cmp     r13, cs:IopRootDeviceNode
0x140ae8101  jz      loc_140AE837A
0x140ae8107  mov     rcx, [r13+20h]
0x140ae810b  mov     rax, cs:PiSwDeviceDriverObject
0x140ae8112  cmp     [rcx+8], rax
0x140ae8116  jnz     loc_140AE8338
0x140ae811c  lea     rdx, PiSwBusName; "SWD\\"
0x140ae8123  lea     rcx, [rbp+250h+DestinationString]; DestinationString
0x140ae8127  call    RtlInitUnicodeString
0x140ae812c  lea     rdx, [r13+28h]; String2
0x140ae8130  mov     r8b, 1; CaseInSensitive
0x140ae8133  lea     rcx, [rbp+250h+DestinationString]; String1
0x140ae8137  call    RtlPrefixUnicodeString
0x140ae813c  test    al, al
0x140ae813e  jz      loc_140AE8338
0x140ae8144  mov     rax, [r13+30h]
0x140ae8148  movzx   ecx, [rbp+250h+DestinationString.Length]
0x140ae814c  shr     rcx, 1
0x140ae814f  lea     rdx, [rax+rcx*2]; SourceString
0x140ae8153  lea     rcx, [rbp+250h+String2]; DestinationString
0x140ae8157  call    RtlInitUnicodeString
0x140ae815c  lea     rdx, aDriverenum; "DRIVERENUM"
0x140ae8163  lea     rcx, [rbp+250h+DestinationString]; DestinationString
0x140ae8167  call    RtlInitUnicodeString
0x140ae816c  mov     r8b, 1; CaseInSensitive
0x140ae816f  lea     rdx, [rbp+250h+String2]; String2
0x140ae8173  lea     rcx, [rbp+250h+DestinationString]; String1
0x140ae8177  call    RtlPrefixUnicodeString
0x140ae817c  test    al, al
0x140ae817e  jz      loc_140AE8338
0x140ae8184  movzx   ecx, [rbp+250h+DestinationString.Length]
0x140ae8188  mov     rax, [rbp+250h+String2.Buffer]
0x140ae818c  shr     rcx, 1
0x140ae818f  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x140ae8194  jnz     loc_140AE8338
0x140ae819a  test    r15d, r15d
0x140ae819d  jnz     loc_140AE8232
0x140ae81a3  mov     rdx, [rbp+250h+var_280.Buffer]
0x140ae81a7  lea     r8, [rbp+250h+var_2B0]
0x140ae81ab  mov     rcx, [rbp+250h+UnicodeString.Buffer]
0x140ae81af  call    PnpGenerateDeviceIdsHash
0x140ae81b4  mov     ebx, eax
0x140ae81b6  test    eax, eax
0x140ae81b8  js      loc_140AE836D
0x140ae81be  test    byte ptr [rbp+250h+var_2B4], 8
0x140ae81c2  jnz     short loc_140AE81FA
0x140ae81c4  lea     rdx, PiSwGenericRawCompatibleId; SourceString
0x140ae81cb  lea     rcx, [rbp+250h+String2]; DestinationString
0x140ae81cf  call    RtlInitUnicodeString
0x140ae81d4  lea     r9, [rbp+250h+HashValue]; HashValue
0x140ae81d8  xor     r8d, r8d; HashAlgorithm
  ... truncated ...
```
