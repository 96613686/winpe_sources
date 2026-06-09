# DsSamExtAddWellKnownSecurityPrincipals

- ea: `0x1803a9770`
- end: `0x1803a9d2d`
- name: `DsSamExtAddWellKnownSecurityPrincipals`
- size: `1469`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1803a9d40`

## callees

- `0x180006360`
- `0x18000bb80`
- `0x18001e090`
- `0x18001ea60`
- `0x180032114`
- `0x180042184`
- `0x18007f99c`
- `0x18008dfe0`
- `0x18015456c`
- `0x180166ee0`
- `0x180166f10`
- `0x1803a9770`
- `0x1803aff80`
- `0x1803b0070`
- `0x1803de418`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1803a9af5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1803a9af5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803a9c3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803a9cb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803a9c3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803a9cb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803a9c01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803a9cf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803a9cfd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803a9c01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803a9cf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803a9cfd`
- `ntdll!RtlInitUnicodeString` at `0x1803a9c4f`
- `ntdll!RtlInitUnicodeString` at `0x1803a9c4f`
- `ntdll!RtlNtStatusToDosError` at `0x1803a9998`
- `ntdll!RtlNtStatusToDosError` at `0x1803a9c30`
- `ntdll!RtlNtStatusToDosError` at `0x1803a9998`
- `ntdll!RtlNtStatusToDosError` at `0x1803a9c30`
- `ADVAPI32!ConvertStringSDToSDDomainW` at `0x1803a98af`
- `ADVAPI32!ConvertStringSDToSDDomainW` at `0x1803a98af`
- `SAMSRV!SampWriteEventLog` at `0x1803a9c77`
- `SAMSRV!SampWriteEventLog` at `0x1803a9cdc`
- `SAMSRV!SampWriteEventLog` at `0x1803a9c77`
- `SAMSRV!SampWriteEventLog` at `0x1803a9cdc`

## string_xrefs

- `0x1803a9921`: `WellKnown Security Principals`

## pseudocode

```c
HLOCAL __fastcall DsSamExtAddWellKnownSecurityPrincipals(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r13
  __int64 v5; // r14
  HLOCAL v7; // r15
  int v9; // ebx
  __int64 v10; // rax
  __int64 v11; // rsi
  NTSTATUS ConfigurationName; // edi
  _DWORD *v13; // rax
  unsigned int v14; // ebx
  DWORD v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r14
  int v18; // ebx
  __int64 v19; // rcx
  unsigned int v20; // r11d
  _QWORD *v21; // r10
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rbx
  unsigned int i; // edx
  NTSTATUS appended; // ebx
  HLOCAL v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rcx
  DWORD v30; // eax
  const WCHAR *v31; // rdx
  unsigned int v33; // [rsp+30h] [rbp-D0h] BYREF
  DWORD LastError; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbSid; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  int v37; // [rsp+48h] [rbp-B8h] BYREF
  int v38; // [rsp+4Ch] [rbp-B4h] BYREF
  int v39; // [rsp+50h] [rbp-B0h]
  unsigned int v40; // [rsp+54h] [rbp-ACh] BYREF
  int v41; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A0h]
  HLOCAL v43; // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+70h] [rbp-90h] BYREF
  __int64 v45; // [rsp+78h] [rbp-88h]
  __int128 v46; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+90h] [rbp-70h]
  _QWORD v48[2]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v49[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v50; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v51[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v52; // [rsp+D8h] [rbp-28h] BYREF
  __int16 v53; // [rsp+E8h] [rbp-18h]
  int v54; // [rsp+EAh] [rbp-16h]
  __int16 v55; // [rsp+EEh] [rbp-12h]
  _QWORD *v56; // [rsp+F0h] [rbp-10h]
  __int64 v57; // [rsp+F8h] [rbp-8h]
  __int64 v58; // [rsp+100h] [rbp+0h]
  struct _UNICODE_STRING DestinationString; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v60[24]; // [rsp+120h] [rbp+20h] BYREF
  int v61; // [rsp+138h] [rbp+38h]
  unsigned __int64 v62; // [rsp+140h] [rbp+40h]
  _BYTE *v63; // [rsp+148h] [rbp+48h]
  HLOCAL v64; // [rsp+1D0h] [rbp+D0h] BYREF
  int v65; // [rsp+1D8h] [rbp+D8h]
  _DWORD *v66; // [rsp+1E0h] [rbp+E0h]
  char v67[208]; // [rsp+210h] [rbp+110h] BYREF
  HLOCAL v68; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v69; // [rsp+2E8h] [rbp+1E8h]
  unsigned int v70; // [rsp+2F4h] [rbp+1F4h]
  _BYTE *v71; // [rsp+2F8h] [rbp+1F8h]
  __int128 *v72; // [rsp+300h] [rbp+200h]
  char v73[208]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE pSid[72]; // [rsp+3E0h] [rbp+2E0h] BYREF

  v4 = 0;
  v42 = a3;
  hMem = 0;
  v5 = a3;
  v33 = 0;
  LastError = 0;
  v38 = 655436;
  v49[1] = &v38;
  v49[0] = 4;
  v7 = 0;
  v46 = 0;
  v50 = 0;
  memset_0(&v64, 0, 0x110u);
  v45 = 0;
  v43 = 0;
  v37 = 0;
  memset_0(&v68, 0, 0x100u);
  v44 = 0;
  memset_0(v60, 0, 0xB0u);
  v40 = 0x80000000;
  v48[1] = 1;
  v51[1] = &v40;
  v51[0] = 4;
  v48[0] = &v41;
  v41 = 0;
  v54 = 0;
  v55 = 0;
  v53 = 22092;
  v56 = v48;
  v57 = 0;
  v58 = 0;
  v52 = 0;
  if ( !(unsigned int)ConvertStringSDToSDDomainW(
                        a4,
                        a4,
                        L"O:EAG:EAD:(A;;RPLCLORC;;;WD)(A;;RPWPCRLCLOCCRCWDWOSW;;;EA)(A;;RPWPCRLCLOCCDCRCWDWOSDDTSW;;;SY)",
                        1,
                        &v43,
                        &v37) )
  {
    LastError = GetLastError();
    v11 = 0;
LABEL_40:
    SampWriteEventLog(SAMMSG_FAILED_TO_ADD_ALL_SECURITY_PRINCIPALS, L"b", 4, &LastError);
    goto LABEL_41;
  }
  LODWORD(v50) = v37;
  *((_QWORD *)&v50 + 1) = v43;
  v9 = 0;
  GetConfigurationName(4, &v33, 0);
  v10 = DSAllocAux(v33, 521732442);
  v11 = v10;
  if ( !v10 )
  {
    ConfigurationName = -1073741801;
    goto LABEL_10;
  }
  ConfigurationName = GetConfigurationName(4, &v33, v10);
  if ( ConfigurationName < 0 )
  {
LABEL_10:
    LastError = RtlNtStatusToDosError(ConfigurationName);
    if ( v9 )
      SampMaybeEndDsTransaction(2);
    goto LABEL_40;
  }
  ConfigurationName = SampAppendCommonName(v11, L"WellKnown Security Principals", &hMem);
  if ( ConfigurationName < 0
    || (DSFreeAux(v11, 521732472),
        v47 = 0,
        v11 = 0,
        ConfigurationName = SampMaybeBeginDsTransaction(1),
        ConfigurationName < 0) )
  {
LABEL_9:
    v7 = hMem;
    goto LABEL_10;
  }
  v9 = 1;
  v39 = 1;
  BuildStdCommArg(v67);
  v65 = 4;
  v13 = (_DWORD *)THAlloc(384);
  v66 = v13;
  if ( !v13 )
  {
    ConfigurationName = -1073741801;
    goto LABEL_9;
  }
  *v13 = 0;
  v7 = hMem;
  v66[2] = 1;
  *((_QWORD *)v66 + 2) = v49;
  v66[24] = 589970;
  v66[26] = 1;
  *((_QWORD *)v66 + 14) = &v46;
  v66[48] = 131353;
  v66[50] = 1;
  *((_QWORD *)v66 + 26) = &v50;
  v66[72] = 590199;
  v66[74] = 1;
  *((_QWORD *)v66 + 38) = v51;
  v71 = v60;
  v60[8] = 73;
  v72 = &v52;
  v60[16] = 0;
  v61 = 589970;
  v70 = v70 & 0xFFFFFFDE | 1;
  v68 = v7;
  v69 = 1;
  BuildStdCommArg(v73);
  v14 = 0;
  v33 = 0;
  if ( !a2 )
    goto LABEL_37;
  do
  {
    cbSid = 68;
    hMem = 0;
    DestinationString = 0;
    if ( !CreateWellKnownSid(*(WELL_KNOWN_SID_TYPE *)(v5 + 16 * v4), 0, pSid, &cbSid) )
    {
      v30 = GetLastError();
      goto LABEL_32;
    }
    *((_QWORD *)&v46 + 1) = pSid;
    LODWORD(v46) = cbSid;
    v62 = __PAIR64__(DWORD1(v46), cbSid);
    v63 = pSid;
    v15 = DirSearchNative(&v68, &v44);
    v17 = v44;
    LastError = v15;
    if ( v44 )
    {
      v18 = SampMapDsErrorToNTStatus(v15, v44 + 72);
      THClearErrors(v19);
      if ( v18 >= 0 )
      {
        v20 = *(_DWORD *)(v17 + 16);
        v21 = (_QWORD *)(v17 + 24);
        v22 = 0;
        v23 = 0;
        if ( v20 )
        {
          while ( !v22 )
          {
            v24 = v21[4];
            for ( i = 0; i < *(_DWORD *)(v24 + 8); ++i )
            {
              if ( **(_DWORD **)(*(_QWORD *)(v24 + 16) + 16LL * i + 8) == v38 )
              {
                v22 = 1;
                break;
              }
            }
            v21 = (_QWORD *)*v21;
            if ( ++v23 >= v20 )
            {
              if ( !v22 )
                goto LABEL_26;
              break;
            }
          }
          v5 = v42;
          goto LABEL_34;
        }
      }
    }
    else
    {
      THClearErrors(v16);
    }
LABEL_26:
    v5 = v42;
    appended = SampAppendCommonName(v7, *(_QWORD *)(v42 + 16 * v4 + 8), &hMem);
    if ( appended < 0 )
      goto LABEL_30;
    v27 = hMem;
    v64 = hMem;
    LastError = DirAddEntryNative((struct _ADDARG_V2 *)&v64);
    LocalFree(v27);
    if ( !v45 )
    {
      appended = -1073741801;
      THClearErrors(v28);
LABEL_30:
      v30 = RtlNtStatusToDosError(appended);
      v14 = v33;
LABEL_32:
      v31 = *(const WCHAR **)(v5 + 16 * v4 + 8);
      LastError = v30;
      RtlInitUnicodeString(&DestinationString, v31);
      SampWriteEventLog(SAMMSG_FAILED_TO_ADD_SECURITY_PRINCIPAL, L"ub", &DestinationString, 4);
      goto LABEL_35;
    }
    appended = SampMapDsErrorToNTStatus(LastError, v45);
    THClearErrors(v29);
    if ( appended < 0 )
      goto LABEL_30;
LABEL_34:
    v14 = v33;
LABEL_35:
    ++v14;
    ++v4;
    v33 = v14;
  }
  while ( v14 < a2 );
  v11 = v47;
LABEL_37:
  ConfigurationName = SampMaybeEndDsTransaction(3);
  if ( ConfigurationName < 0 )
  {
    v9 = v39;
    goto LABEL_10;
  }
LABEL_41:
  DSFreeAux(v11, 521732714);
  LocalFree(v7);
  return LocalFree(v43);
}

```

## disassembly

```asm
0x1803a9770  mov     [rsp-8+arg_0], rbx
0x1803a9775  push    rbp
0x1803a9776  push    rsi
0x1803a9777  push    rdi
0x1803a9778  push    r12
0x1803a977a  push    r13
0x1803a977c  push    r14
0x1803a977e  push    r15
0x1803a9780  lea     rbp, [rsp-330h]
0x1803a9788  sub     rsp, 430h
0x1803a978f  mov     rax, cs:__security_cookie
0x1803a9796  xor     rax, rsp
0x1803a9799  mov     [rbp+360h+var_38], rax
0x1803a97a0  xor     r13d, r13d
0x1803a97a3  mov     [rsp+460h+var_400], r8
0x1803a97a8  xorps   xmm0, xmm0
0x1803a97ab  mov     [rsp+460h+hMem], r13
0x1803a97b0  mov     r14, r8
0x1803a97b3  mov     [rsp+460h+var_430], r13d
0x1803a97b8  mov     r12d, edx
0x1803a97bb  mov     [rsp+460h+var_42C], r13d
0x1803a97c0  lea     rax, [rsp+460h+var_414]
0x1803a97c5  mov     [rsp+460h+var_414], 0A004Ch
0x1803a97cd  xor     edx, edx; Val
0x1803a97cf  mov     [rbp+360h+var_3B0], rax
0x1803a97d3  mov     r8d, 110h; Size
0x1803a97d9  mov     [rbp+360h+var_3B8], 4
0x1803a97e1  lea     rcx, [rbp+360h+var_290]; void *
0x1803a97e8  mov     r15d, r13d
0x1803a97eb  movups  [rbp+360h+var_3E0], xmm0
0x1803a97ef  mov     rbx, r9
0x1803a97f2  movups  [rbp+360h+var_3A8], xmm0
0x1803a97f6  call    memset_0
0x1803a97fb  xor     edx, edx; Val
0x1803a97fd  mov     [rsp+460h+var_3E8], r13
0x1803a9802  mov     r8d, 100h; Size
0x1803a9808  mov     [rsp+460h+var_3F8], r13
0x1803a980d  lea     rcx, [rbp+360h+var_180]; void *
0x1803a9814  mov     [rsp+460h+var_418], r13d
0x1803a9819  call    memset_0
0x1803a981e  xor     edx, edx; Val
0x1803a9820  mov     [rsp+460h+var_3F0], r13
0x1803a9825  mov     r8d, 0B0h; Size
0x1803a982b  lea     rcx, [rbp+360h+var_340]; void *
0x1803a982f  call    memset_0
0x1803a9834  lea     ecx, [r13+1]
0x1803a9838  mov     [rsp+460h+var_40C], 80000000h
0x1803a9840  lea     rax, [rsp+460h+var_40C]
0x1803a9845  mov     [rbp+360h+var_3C0], rcx
0x1803a9849  mov     [rbp+360h+var_390], rax
0x1803a984d  lea     r8, aOEagEadARplclo; "O:EAG:EAD:(A;;RPLCLORC;;;WD)(A;;RPWPCRL"...
0x1803a9854  lea     rax, [rsp+460h+var_408]
0x1803a9859  mov     [rbp+360h+var_398], 4
0x1803a9861  mov     [rbp+360h+var_3C8], rax
0x1803a9865  xorps   xmm0, xmm0
0x1803a9868  xor     eax, eax
0x1803a986a  mov     [rsp+460h+var_408], r13d
0x1803a986f  mov     [rbp+360h+var_376], eax
0x1803a9872  mov     r9d, ecx
0x1803a9875  mov     [rbp+360h+var_372], ax
0x1803a9879  mov     rdx, rbx
0x1803a987c  lea     rax, [rbp+360h+var_3C8]
0x1803a9880  mov     [rbp+360h+var_378], 564Ch
0x1803a9886  mov     [rbp+360h+var_370], rax
0x1803a988a  mov     rcx, rbx
0x1803a988d  xor     eax, eax
0x1803a988f  mov     [rbp+360h+var_368], r13
0x1803a9893  mov     [rbp+360h+var_360], rax
0x1803a9897  lea     rax, [rsp+460h+var_418]
0x1803a989c  mov     [rsp+460h+var_438], rax
0x1803a98a1  lea     rax, [rsp+460h+var_3F8]
0x1803a98a6  mov     [rsp+460h+var_440], rax
0x1803a98ab  movups  [rbp+360h+var_388], xmm0
0x1803a98af  call    cs:__imp_ConvertStringSDToSDDomainW
0x1803a98b5  test    eax, eax
0x1803a98b7  jz      loc_1803A9CB6
0x1803a98bd  mov     eax, [rsp+460h+var_418]
0x1803a98c1  lea     rdx, [rsp+460h+var_430]
0x1803a98c6  mov     dword ptr [rbp+360h+var_3A8], eax
0x1803a98c9  lea     ecx, [r13+4]
0x1803a98cd  mov     rax, [rsp+460h+var_3F8]
0x1803a98d2  xor     r8d, r8d
0x1803a98d5  mov     qword ptr [rbp+360h+var_3A8+8], rax
0x1803a98d9  mov     ebx, r13d
0x1803a98dc  call    GetConfigurationName
0x1803a98e1  mov     ecx, [rsp+460h+var_430]
0x1803a98e5  mov     edx, 1F19015Ah
0x1803a98ea  call    DSAllocAux
0x1803a98ef  mov     rsi, rax
0x1803a98f2  test    rax, rax
0x1803a98f5  jnz     short loc_1803A9901
0x1803a98f7  mov     edi, 0C0000017h
0x1803a98fc  jmp     loc_1803A9996
0x1803a9901  mov     r8, rsi
0x1803a9904  lea     rdx, [rsp+460h+var_430]
0x1803a9909  mov     ecx, 4
0x1803a990e  call    GetConfigurationName
0x1803a9913  mov     edi, eax
0x1803a9915  test    eax, eax
0x1803a9917  js      short loc_1803A9996
0x1803a9919  lea     r8, [rsp+460h+hMem]
0x1803a991e  mov     rcx, rsi
0x1803a9921  lea     rdx, aWellknownSecur; "WellKnown Security Principals"
0x1803a9928  call    SampAppendCommonName
0x1803a992d  mov     edi, eax
0x1803a992f  test    eax, eax
0x1803a9931  js      short loc_1803A9991
0x1803a9933  mov     edx, 1F190178h
0x1803a9938  mov     rcx, rsi
0x1803a993b  call    DSFreeAux
0x1803a9940  mov     ecx, 1
0x1803a9945  mov     [rbp+360h+var_3D0], r13
0x1803a9949  mov     rsi, r13
0x1803a994c  call    SampMaybeBeginDsTransaction
0x1803a9951  mov     edi, eax
0x1803a9953  test    eax, eax
0x1803a9955  js      short loc_1803A9991
0x1803a9957  mov     ebx, 1
0x1803a995c  lea     rcx, [rbp+360h+var_250]
0x1803a9963  mov     [rsp+460h+var_410], ebx
0x1803a9967  call    BuildStdCommArg
0x1803a996c  mov     ecx, 180h
0x1803a9971  mov     [rbp+360h+var_288], 4
0x1803a997b  call    THAlloc
0x1803a9980  mov     [rbp+360h+var_280], rax
0x1803a9987  test    rax, rax
0x1803a998a  jnz     short loc_1803A99B9
0x1803a998c  mov     edi, 0C0000017h
0x1803a9991  mov     r15, [rsp+460h+hMem]
0x1803a9996  mov     ecx, edi; Status
0x1803a9998  call    cs:__imp_RtlNtStatusToDosError
0x1803a999e  mov     [rsp+460h+var_42C], eax
0x1803a99a2  test    ebx, ebx
0x1803a99a4  jz      loc_1803A9CC3
0x1803a99aa  mov     ecx, 2
0x1803a99af  call    SampMaybeEndDsTransaction
0x1803a99b4  jmp     loc_1803A9CC3
0x1803a99b9  mov     [rax], r13d
0x1803a99bc  lea     rcx, [rbp+360h+var_3B8]
0x1803a99c0  mov     rax, [rbp+360h+var_280]
0x1803a99c7  mov     edx, 90092h
0x1803a99cc  mov     r15, [rsp+460h+hMem]
0x1803a99d1  mov     [rax+8], ebx
0x1803a99d4  mov     rax, [rbp+360h+var_280]
0x1803a99db  mov     [rax+10h], rcx
0x1803a99df  lea     rcx, [rbp+360h+var_3E0]
0x1803a99e3  mov     rax, [rbp+360h+var_280]
0x1803a99ea  mov     [rax+60h], edx
0x1803a99ed  mov     rax, [rbp+360h+var_280]
0x1803a99f4  mov     [rax+68h], ebx
0x1803a99f7  mov     rax, [rbp+360h+var_280]
0x1803a99fe  mov     [rax+70h], rcx
0x1803a9a02  lea     rcx, [rbp+360h+var_3A8]
0x1803a9a06  mov     rax, [rbp+360h+var_280]
0x1803a9a0d  mov     dword ptr [rax+0C0h], 20119h
0x1803a9a17  mov     rax, [rbp+360h+var_280]
0x1803a9a1e  mov     [rax+0C8h], ebx
0x1803a9a24  mov     rax, [rbp+360h+var_280]
0x1803a9a2b  mov     [rax+0D0h], rcx
0x1803a9a32  lea     rcx, [rbp+360h+var_398]
0x1803a9a36  mov     rax, [rbp+360h+var_280]
0x1803a9a3d  mov     dword ptr [rax+120h], 90177h
0x1803a9a47  mov     rax, [rbp+360h+var_280]
0x1803a9a4e  mov     [rax+128h], ebx
0x1803a9a54  mov     rax, [rbp+360h+var_280]
0x1803a9a5b  mov     [rax+130h], rcx
0x1803a9a62  lea     rax, [rbp+360h+var_340]
0x1803a9a66  mov     [rbp+360h+var_168], rax
0x1803a9a6d  lea     rcx, [rbp+360h+var_150]
0x1803a9a74  lea     rax, [rbp+360h+var_388]
0x1803a9a78  mov     [rbp+360h+var_338], 49h ; 'I'
0x1803a9a7c  mov     [rbp+360h+var_160], rax
0x1803a9a83  mov     eax, [rbp+360h+var_16C]
0x1803a9a89  and     eax, 0FFFFFFDFh
0x1803a9a8c  mov     [rbp+360h+var_330], r13b
0x1803a9a90  or      eax, ebx
0x1803a9a92  mov     [rbp+360h+var_328], edx
0x1803a9a95  mov     [rbp+360h+var_16C], eax
0x1803a9a9b  mov     [rbp+360h+var_180], r15
0x1803a9aa2  mov     [rbp+360h+var_178], bl
0x1803a9aa8  call    BuildStdCommArg
0x1803a9aad  mov     ebx, r13d
0x1803a9ab0  mov     [rsp+460h+var_430], ebx
0x1803a9ab4  test    r12d, r12d
0x1803a9ab7  jz      loc_1803A9C9D
0x1803a9abd  mov     edi, 0C0000017h
0x1803a9ac2  mov     esi, r12d
0x1803a9ac5  xorps   xmm0, xmm0
0x1803a9ac8  mov     [rsp+460h+cbSid], 44h ; 'D'
0x1803a9ad0  mov     r12, r13
0x1803a9ad3  mov     [rsp+460h+hMem], 0
0x1803a9adc  add     r12, r12
0x1803a9adf  lea     r9, [rsp+460h+cbSid]; cbSid
0x1803a9ae4  lea     r8, [rbp+360h+pSid]; pSid
0x1803a9aeb  xor     edx, edx; DomainSid
0x1803a9aed  movups  xmmword ptr [rbp+360h+DestinationString.Length], xmm0
0x1803a9af1  mov     ecx, [r14+r12*8]; WellKnownSidType
0x1803a9af5  call    cs:__imp_CreateWellKnownSid
0x1803a9afb  test    eax, eax
0x1803a9afd  jz      loc_1803A9C3C
0x1803a9b03  lea     rax, [rbp+360h+pSid]
0x1803a9b0a  mov     qword ptr [rbp+360h+var_3E0+8], rax
0x1803a9b0e  lea     rdx, [rsp+460h+var_3F0]
0x1803a9b13  mov     eax, [rsp+460h+cbSid]
0x1803a9b17  lea     rcx, [rbp+360h+var_180]
0x1803a9b1e  mov     dword ptr [rbp+360h+var_3E0], eax
0x1803a9b21  mov     dword ptr [rbp+360h+var_320], eax
0x1803a9b24  mov     eax, dword ptr [rbp+360h+var_3E0+4]
0x1803a9b27  mov     dword ptr [rbp+360h+var_320+4], eax
0x1803a9b2a  lea     rax, [rbp+360h+pSid]
0x1803a9b31  mov     [rbp+360h+var_318], rax
0x1803a9b35  call    DirSearchNative
0x1803a9b3a  mov     r14, [rsp+460h+var_3F0]
0x1803a9b3f  mov     [rsp+460h+var_42C], eax
0x1803a9b43  test    r14, r14
0x1803a9b46  jnz     short loc_1803A9B4F
0x1803a9b48  call    THClearErrors
0x1803a9b4d  jmp     short loc_1803A9BC0
0x1803a9b4f  lea     rdx, [r14+48h]
0x1803a9b53  mov     ecx, eax
0x1803a9b55  call    SampMapDsErrorToNTStatus
0x1803a9b5a  mov     ebx, eax
0x1803a9b5c  call    THClearErrors
0x1803a9b61  test    ebx, ebx
0x1803a9b63  js      short loc_1803A9BC0
0x1803a9b65  mov     r11d, [r14+10h]
0x1803a9b69  lea     r10, [r14+18h]
0x1803a9b6d  xor     r8d, r8d
0x1803a9b70  xor     r9d, r9d
0x1803a9b73  test    r11d, r11d
0x1803a9b76  jz      short loc_1803A9BC0
0x1803a9b78  test    r8d, r8d
0x1803a9b7b  jnz     loc_1803A9C7F
0x1803a9b81  mov     rbx, [r10+20h]
0x1803a9b85  xor     edx, edx
0x1803a9b87  cmp     edx, [rbx+8]
0x1803a9b8a  jnb     short loc_1803A9BAC
0x1803a9b8c  mov     rax, [rbx+10h]
0x1803a9b90  mov     ecx, edx
0x1803a9b92  add     rcx, rcx
0x1803a9b95  mov     rcx, [rax+rcx*8+8]
0x1803a9b9a  mov     eax, [rcx]
0x1803a9b9c  cmp     eax, [rsp+460h+var_414]
0x1803a9ba0  jz      short loc_1803A9BA6
0x1803a9ba2  inc     edx
0x1803a9ba4  jmp     short loc_1803A9B87
0x1803a9ba6  mov     r8d, 1
0x1803a9bac  mov     r10, [r10]
0x1803a9baf  inc     r9d
0x1803a9bb2  cmp     r9d, r11d
0x1803a9bb5  jb      short loc_1803A9B78
0x1803a9bb7  test    r8d, r8d
0x1803a9bba  jnz     loc_1803A9C7F
0x1803a9bc0  mov     r14, [rsp+460h+var_400]
0x1803a9bc5  lea     r8, [rsp+460h+hMem]
0x1803a9bca  mov     rcx, r15
0x1803a9bcd  mov     rdx, [r14+r12*8+8]
0x1803a9bd2  call    SampAppendCommonName
0x1803a9bd7  mov     ebx, eax
0x1803a9bd9  test    eax, eax
0x1803a9bdb  js      short loc_1803A9C2E
0x1803a9bdd  mov     rbx, [rsp+460h+hMem]
0x1803a9be2  lea     rdx, [rsp+460h+var_3E8]
0x1803a9be7  lea     rcx, [rbp+360h+var_290]
0x1803a9bee  mov     [rbp+360h+var_290], rbx
0x1803a9bf5  call    DirAddEntryNative
0x1803a9bfa  mov     rcx, rbx; hMem
0x1803a9bfd  mov     [rsp+460h+var_42C], eax
0x1803a9c01  call    cs:__imp_LocalFree
0x1803a9c07  mov     rdx, [rsp+460h+var_3E8]
0x1803a9c0c  test    rdx, rdx
0x1803a9c0f  jnz     short loc_1803A9C1A
0x1803a9c11  mov     ebx, edi
0x1803a9c13  call    THClearErrors
0x1803a9c18  jmp     short loc_1803A9C2E
0x1803a9c1a  mov     ecx, [rsp+460h+var_42C]
0x1803a9c1e  call    SampMapDsErrorToNTStatus
0x1803a9c23  mov     ebx, eax
0x1803a9c25  call    THClearErrors
0x1803a9c2a  test    ebx, ebx
0x1803a9c2c  jns     short loc_1803A9C84
0x1803a9c2e  mov     ecx, ebx; Status
0x1803a9c30  call    cs:__imp_RtlNtStatusToDosError
0x1803a9c36  mov     ebx, [rsp+460h+var_430]
0x1803a9c3a  jmp     short loc_1803A9C42
0x1803a9c3c  call    cs:__imp_GetLastError
0x1803a9c42  mov     rdx, [r14+r12*8+8]; SourceString
0x1803a9c47  lea     rcx, [rbp+360h+DestinationString]; DestinationString
0x1803a9c4b  mov     [rsp+460h+var_42C], eax
0x1803a9c4f  call    cs:__imp_RtlInitUnicodeString
0x1803a9c55  lea     rax, [rsp+460h+var_42C]
0x1803a9c5a  mov     r9d, 4
0x1803a9c60  lea     r8, [rbp+360h+DestinationString]
0x1803a9c64  mov     [rsp+460h+var_440], rax
0x1803a9c69  lea     rdx, aUb; "ub"
0x1803a9c70  lea     rcx, SAMMSG_FAILED_TO_ADD_SECURITY_PRINCIPAL
0x1803a9c77  call    cs:__imp_SampWriteEventLog
0x1803a9c7d  jmp     short loc_1803A9C88
0x1803a9c7f  mov     r14, [rsp+460h+var_400]
0x1803a9c84  mov     ebx, [rsp+460h+var_430]
  ... truncated ...
```
