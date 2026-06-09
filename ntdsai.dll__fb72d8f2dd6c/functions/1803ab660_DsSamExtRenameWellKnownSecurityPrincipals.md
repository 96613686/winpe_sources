# DsSamExtRenameWellKnownSecurityPrincipals

- ea: `0x1803ab660`
- end: `0x1803abd31`
- name: `DsSamExtRenameWellKnownSecurityPrincipals`
- size: `1745`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006360`
- `0x18000bb80`
- `0x18001e090`
- `0x18001ea60`
- `0x1800220c0`
- `0x180032114`
- `0x18004aa20`
- `0x1800528dc`
- `0x18007f99c`
- `0x18008dfe0`
- `0x18015456c`
- `0x180166f10`
- `0x1803ab660`
- `0x1803aff80`
- `0x1803b0070`
- `0x1803de418`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1803ab9e4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1803ab9e4`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1803ab92f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1803ab92f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803abc33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803abc33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803abd08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803abd08`
- `ntdll!RtlInitUnicodeString` at `0x1803abc46`
- `ntdll!RtlInitUnicodeString` at `0x1803abc46`
- `ntdll!RtlNtStatusToDosError` at `0x1803aba22`
- `ntdll!RtlNtStatusToDosError` at `0x1803abcc1`
- `ntdll!RtlNtStatusToDosError` at `0x1803aba22`
- `ntdll!RtlNtStatusToDosError` at `0x1803abcc1`
- `SAMSRV!SampWriteEventLog` at `0x1803abc6e`
- `SAMSRV!SampWriteEventLog` at `0x1803abcf2`
- `SAMSRV!SampWriteEventLog` at `0x1803abc6e`
- `SAMSRV!SampWriteEventLog` at `0x1803abcf2`

## string_xrefs

- `0x1803ab7ad`: `WellKnown Security Principals`

## pseudocode

```c
HLOCAL __fastcall DsSamExtRenameWellKnownSecurityPrincipals(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // r13
  __int64 v4; // r12
  HLOCAL v6; // rsi
  int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // r15
  NTSTATUS ConfigurationName; // edi
  unsigned int v11; // ebx
  unsigned int v12; // r15d
  __int64 v13; // r14
  ULONG v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rsi
  NTSTATUS v17; // ebx
  __int64 v18; // rcx
  __int64 v19; // r12
  int v20; // r14d
  __int64 v21; // rdx
  int v22; // ecx
  DWORD LastError; // eax
  char v24; // si
  ULONG v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rax
  ULONG v30; // eax
  __int64 v31; // rcx
  ULONG v32; // eax
  __int64 v33; // rcx
  int v34; // esi
  const WCHAR *v35; // rdx
  ULONG *v37; // [rsp+20h] [rbp-E0h]
  unsigned int v38; // [rsp+30h] [rbp-D0h] BYREF
  ULONG v39; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v40; // [rsp+38h] [rbp-C8h]
  int v41; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v42; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbSid; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  int v45; // [rsp+60h] [rbp-A0h] BYREF
  int v46; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v47; // [rsp+68h] [rbp-98h] BYREF
  __int64 v48; // [rsp+70h] [rbp-90h] BYREF
  __int64 v49; // [rsp+78h] [rbp-88h]
  _QWORD v50[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v51[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v52; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v53[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v54; // [rsp+C0h] [rbp-40h] BYREF
  __int128 *v55; // [rsp+D0h] [rbp-30h]
  __int128 v56; // [rsp+D8h] [rbp-28h] BYREF
  __int16 v57; // [rsp+E8h] [rbp-18h]
  int v58; // [rsp+EAh] [rbp-16h]
  __int16 v59; // [rsp+EEh] [rbp-12h]
  _QWORD *v60; // [rsp+F0h] [rbp-10h]
  __int64 v61; // [rsp+F8h] [rbp-8h]
  __int64 v62; // [rsp+100h] [rbp+0h]
  struct _UNICODE_STRING DestinationString; // [rsp+108h] [rbp+8h] BYREF
  __int64 v64; // [rsp+120h] [rbp+20h] BYREF
  __int16 v65; // [rsp+128h] [rbp+28h]
  __int64 v66; // [rsp+130h] [rbp+30h]
  __int16 v67; // [rsp+138h] [rbp+38h]
  int v68; // [rsp+140h] [rbp+40h]
  int v69; // [rsp+148h] [rbp+48h]
  _QWORD *v70; // [rsp+150h] [rbp+50h]
  _BYTE v71[216]; // [rsp+1A8h] [rbp+A8h] BYREF
  HLOCAL v72; // [rsp+280h] [rbp+180h] BYREF
  char v73; // [rsp+288h] [rbp+188h]
  unsigned int v74; // [rsp+294h] [rbp+194h]
  __int64 *v75; // [rsp+298h] [rbp+198h]
  __int128 *v76; // [rsp+2A0h] [rbp+1A0h]
  char v77[208]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _QWORD v78[4]; // [rsp+380h] [rbp+280h] BYREF
  char v79[224]; // [rsp+3A0h] [rbp+2A0h] BYREF
  __int64 v80; // [rsp+480h] [rbp+380h] BYREF
  char v81[128]; // [rsp+488h] [rbp+388h] BYREF
  __int16 v82; // [rsp+508h] [rbp+408h]
  __int64 **v83; // [rsp+510h] [rbp+410h]
  __int64 *v84; // [rsp+530h] [rbp+430h] BYREF
  char v85; // [rsp+538h] [rbp+438h]
  char v86; // [rsp+540h] [rbp+440h]
  int v87; // [rsp+548h] [rbp+448h]
  DWORD v88; // [rsp+550h] [rbp+450h]
  _BYTE *v89; // [rsp+558h] [rbp+458h]
  __int64 v90; // [rsp+5E0h] [rbp+4E0h] BYREF
  char v91; // [rsp+5E8h] [rbp+4E8h]
  char v92; // [rsp+5F0h] [rbp+4F0h]
  int v93; // [rsp+5F8h] [rbp+4F8h]
  int v94; // [rsp+600h] [rbp+500h]
  int *v95; // [rsp+608h] [rbp+508h]
  _BYTE pSid[80]; // [rsp+690h] [rbp+590h] BYREF
  _BYTE v97[512]; // [rsp+6E0h] [rbp+5E0h] BYREF

  v3 = 0;
  v40 = a3;
  v4 = a3;
  hMem = 0;
  v38 = 0;
  v39 = 0;
  v46 = 655436;
  v55 = 0;
  v6 = 0;
  v52 = 0;
  v54 = 0;
  memset_0(v78, 0, 0x100u);
  v48 = 0;
  v7 = 0;
  memset_0(&v72, 0, 0x100u);
  v47 = 0;
  v80 = 0;
  memset_0(v81, 0, 0x208u);
  v45 = 590199;
  v50[0] = &v45;
  v50[1] = 1;
  v58 = 0;
  v59 = 0;
  v57 = 22092;
  v60 = v50;
  v56 = 0;
  v61 = 0;
  v62 = 0;
  GetConfigurationName(4, &v38, 0);
  v8 = DSAllocAux(v38, 521732850);
  v9 = v8;
  if ( !v8 )
  {
    ConfigurationName = -1073741801;
    goto LABEL_52;
  }
  ConfigurationName = GetConfigurationName(4, &v38, v8);
  if ( ConfigurationName < 0 )
    goto LABEL_52;
  ConfigurationName = SampAppendCommonName(v9, L"WellKnown Security Principals", &hMem);
  if ( ConfigurationName < 0
    || (DSFreeAux(v9, 521732880),
        v49 = 0,
        v9 = 0,
        ConfigurationName = SampMaybeBeginDsTransaction(1),
        ConfigurationName < 0) )
  {
    v6 = hMem;
LABEL_52:
    v39 = RtlNtStatusToDosError(ConfigurationName);
    if ( v7 )
      SampMaybeEndDsTransaction(2);
    SampWriteEventLog(SAMMSG_FAILED_TO_RENAME_ALL_SECURITY_PRINCIPALS, L"b", 4, &v39);
    goto LABEL_55;
  }
  v6 = hMem;
  v81[0] = 65;
  v82 = 2;
  v85 = 73;
  v83 = &v84;
  v84 = &v90;
  v95 = &v46;
  v75 = &v80;
  v76 = &v56;
  v86 = 0;
  v87 = 589970;
  v74 = v74 & 0xFFFFFFDE | 1;
  v91 = 73;
  v92 = 0;
  v93 = 0;
  v94 = 4;
  v90 = 0;
  v72 = hMem;
  v73 = 1;
  BuildStdCommArg(v77);
  LODWORD(v54) = 3;
  v55 = &v52;
  DWORD2(v54) = 1;
  v78[2] = &v54;
  BuildStdCommArg(v79);
  v11 = 0;
  v38 = 0;
  if ( !a2 )
    goto LABEL_49;
  v12 = a2;
  do
  {
    v41 = 0;
    cbSid = 68;
    LODWORD(v42) = 256;
    v13 = 3 * v3;
    DestinationString = 0;
    if ( !CreateWellKnownSid(*(WELL_KNOWN_SID_TYPE *)(v4 + 24 * v3), 0, pSid, &cbSid) )
    {
      LastError = GetLastError();
      goto LABEL_45;
    }
    v89 = pSid;
    v88 = cbSid;
    v14 = DirSearchNative(&v72, &v47);
    v16 = v47;
    v39 = v14;
    if ( !v47 )
    {
      v17 = -1073741801;
      THClearErrors(v15);
      goto LABEL_22;
    }
    v17 = SampMapDsErrorToNTStatus(v14, v47 + 72);
    THClearErrors(v18);
    if ( v17 < 0 )
      goto LABEL_22;
    if ( *(_DWORD *)(v16 + 16) != 1 )
    {
      v17 = -1073740795;
LABEL_22:
      LastError = RtlNtStatusToDosError(v17);
      v11 = v38;
LABEL_45:
      v35 = *(const WCHAR **)(v4 + 8 * v13 + 8);
      v39 = LastError;
      RtlInitUnicodeString(&DestinationString, v35);
      v37 = &v39;
      SampWriteEventLog(SAMMSG_FAILED_TO_RENAME_SECURITY_PRINCIPAL, L"ub", &DestinationString, 4);
      goto LABEL_47;
    }
    v19 = *(_QWORD *)(v16 + 32);
    if ( (unsigned int)GetRDNInfoExternal(v19, v97, &v42, &v41, v37) )
    {
      v17 = -1073741595;
LABEL_21:
      v4 = v40;
      goto LABEL_22;
    }
    if ( !(unsigned int)_o__wcsnicmp(v97, *(_QWORD *)(v40 + 24 * v3 + 8), (unsigned int)v42) )
    {
      v20 = 0;
      if ( *(_DWORD *)(v16 + 48) == 1 )
      {
        v21 = *(_QWORD *)(v16 + 56);
        v22 = *(_DWORD *)(v21 + 8);
        if ( v22 )
        {
          if ( v22 != 1 )
          {
            v17 = -1073741595;
LABEL_20:
            v13 = 3 * v3;
            goto LABEL_21;
          }
          v20 = **(_DWORD **)(*(_QWORD *)(v21 + 16) + 8LL);
        }
      }
      v24 = 0;
      if ( (v20 & 0x40000000) == 0 )
      {
        memset_0(&v64, 0, 0x160u);
        v42 = 0;
        v51[0] = 4;
        v41 = v20 | 0x40000000;
        v64 = v19;
        v51[1] = &v41;
        v67 = 67;
        v66 = 0;
        v68 = 590199;
        v24 = 1;
        v69 = 1;
        v70 = v51;
        v65 = 1;
        BuildStdCommArg(v71);
        v25 = DirModifyEntryNative(&v64, &v42);
        v39 = v25;
        if ( !v42 )
        {
          v17 = -1073741801;
          THClearErrors(v26);
          goto LABEL_20;
        }
        v17 = SampMapDsErrorToNTStatus(v25, v42);
        THClearErrors(v27);
        if ( v17 < 0 )
          goto LABEL_20;
      }
      v28 = *(_QWORD *)(v40 + 24 * v3 + 16);
      v29 = -1;
      *((_QWORD *)&v52 + 1) = v28;
      do
        ++v29;
      while ( *(_WORD *)(v28 + 2 * v29) );
      v78[0] = v19;
      LODWORD(v52) = 2 * v29;
      v30 = DirModifyDN(v78, &v48);
      v39 = v30;
      if ( v48 )
        v17 = SampMapDsErrorToNTStatus(v30, v48);
      else
        v17 = -1073741801;
      THClearErrors(v31);
      if ( v24 )
      {
        memset_0(&v64, 0, 0x160u);
        v41 = v20;
        v53[1] = &v41;
        v42 = 0;
        v53[0] = 4;
        v64 = v19;
        v66 = 0;
        v67 = 67;
        v69 = 1;
        v65 = 1;
        v68 = 590199;
        v70 = v53;
        BuildStdCommArg(v71);
        v32 = DirModifyEntryNative(&v64, &v42);
        v39 = v32;
        if ( v42 )
          v34 = SampMapDsErrorToNTStatus(v32, v42);
        else
          v34 = -1073741801;
        THClearErrors(v33);
        if ( v17 < 0 )
          goto LABEL_20;
        v4 = v40;
        if ( v34 >= 0 )
          goto LABEL_42;
        v17 = v34;
      }
      else
      {
        v4 = v40;
        if ( v17 >= 0 )
        {
LABEL_42:
          v11 = v38;
          goto LABEL_47;
        }
      }
      v13 = 3 * v3;
      goto LABEL_22;
    }
    v11 = v38;
    v4 = v40;
LABEL_47:
    ++v11;
    ++v3;
    v38 = v11;
  }
  while ( v11 < v12 );
  v9 = v49;
  v6 = hMem;
LABEL_49:
  ConfigurationName = SampMaybeEndDsTransaction(3);
  if ( ConfigurationName < 0 )
  {
    v7 = 1;
    goto LABEL_52;
  }
LABEL_55:
  DSFreeAux(v9, 521733193);
  return LocalFree(v6);
}

```

## disassembly

```asm
0x1803ab660  push    rbp
0x1803ab662  push    rbx
0x1803ab663  push    rsi
0x1803ab664  push    rdi
0x1803ab665  push    r12
0x1803ab667  push    r13
0x1803ab669  push    r14
0x1803ab66b  push    r15
0x1803ab66d  lea     rbp, [rsp-7F8h]
0x1803ab675  sub     rsp, 8F8h
0x1803ab67c  mov     rax, cs:__security_cookie
0x1803ab683  xor     rax, rsp
0x1803ab686  mov     [rbp+830h+var_50], rax
0x1803ab68d  xor     r13d, r13d
0x1803ab690  mov     [rsp+930h+var_8F8], r8
0x1803ab695  mov     r12, r8
0x1803ab698  mov     [rsp+930h+hMem], r13
0x1803ab69d  mov     r14d, edx
0x1803ab6a0  mov     [rsp+930h+var_900], r13d
0x1803ab6a5  xorps   xmm0, xmm0
0x1803ab6a8  mov     [rsp+930h+var_8FC], r13d
0x1803ab6ad  xorps   xmm1, xmm1
0x1803ab6b0  mov     [rsp+930h+var_8CC], 0A004Ch
0x1803ab6b8  xor     eax, eax
0x1803ab6ba  lea     rcx, [rbp+830h+var_5B0]; void *
0x1803ab6c1  mov     edi, 100h
0x1803ab6c6  mov     [rbp+830h+var_860], rax
0x1803ab6ca  mov     r8d, edi; Size
0x1803ab6cd  xor     edx, edx; Val
0x1803ab6cf  mov     esi, r13d
0x1803ab6d2  movups  [rbp+830h+var_890], xmm0
0x1803ab6d6  movups  [rbp+830h+var_870], xmm1
0x1803ab6da  call    memset_0
0x1803ab6df  mov     r8d, edi; Size
0x1803ab6e2  mov     [rsp+930h+var_8C0], r13
0x1803ab6e7  xor     edx, edx; Val
0x1803ab6e9  lea     rcx, [rbp+830h+var_6B0]; void *
0x1803ab6f0  mov     ebx, r13d
0x1803ab6f3  call    memset_0
0x1803ab6f8  xor     edx, edx; Val
0x1803ab6fa  mov     [rsp+930h+var_8C8], r13
0x1803ab6ff  mov     r8d, 208h; Size
0x1803ab705  mov     [rbp+830h+var_4B0], r13
0x1803ab70c  lea     rcx, [rbp+830h+var_4A8]; void *
0x1803ab713  call    memset_0
0x1803ab718  lea     rax, [rsp+930h+var_8D0]
0x1803ab71d  mov     [rsp+930h+var_8D0], 90177h
0x1803ab725  mov     [rbp+830h+var_8B0], rax
0x1803ab729  lea     rdx, [rsp+930h+var_900]
0x1803ab72e  xor     eax, eax
0x1803ab730  mov     [rbp+830h+var_8A8], 1
0x1803ab738  mov     [rbp+830h+var_846], eax
0x1803ab73b  xorps   xmm0, xmm0
0x1803ab73e  mov     [rbp+830h+var_842], ax
0x1803ab742  xor     r8d, r8d
0x1803ab745  lea     rax, [rbp+830h+var_8B0]
0x1803ab749  mov     [rbp+830h+var_848], 564Ch
0x1803ab74f  mov     [rbp+830h+var_840], rax
0x1803ab753  xor     eax, eax
0x1803ab755  movups  [rbp+830h+var_858], xmm0
0x1803ab759  mov     [rbp+830h+var_838], r13
0x1803ab75d  mov     [rbp+830h+var_830], rax
0x1803ab761  lea     ecx, [rax+4]
0x1803ab764  call    GetConfigurationName
0x1803ab769  mov     ecx, [rsp+930h+var_900]
0x1803ab76d  mov     edx, 1F1902F2h
0x1803ab772  call    DSAllocAux
0x1803ab777  mov     r15, rax
0x1803ab77a  test    rax, rax
0x1803ab77d  jnz     short loc_1803AB789
0x1803ab77f  mov     edi, 0C0000017h
0x1803ab784  jmp     loc_1803ABCBF
0x1803ab789  mov     r8, r15
0x1803ab78c  lea     rdx, [rsp+930h+var_900]
0x1803ab791  mov     ecx, 4
0x1803ab796  call    GetConfigurationName
0x1803ab79b  mov     edi, eax
0x1803ab79d  test    eax, eax
0x1803ab79f  js      loc_1803ABCBF
0x1803ab7a5  lea     r8, [rsp+930h+hMem]
0x1803ab7aa  mov     rcx, r15
0x1803ab7ad  lea     rdx, aWellknownSecur; "WellKnown Security Principals"
0x1803ab7b4  call    SampAppendCommonName
0x1803ab7b9  mov     edi, eax
0x1803ab7bb  test    eax, eax
0x1803ab7bd  js      loc_1803ABCBA
0x1803ab7c3  mov     edx, 1F190310h
0x1803ab7c8  mov     rcx, r15
0x1803ab7cb  call    DSFreeAux
0x1803ab7d0  mov     ecx, 1
0x1803ab7d5  mov     [rsp+930h+var_8B8], r13
0x1803ab7da  mov     r15, r13
0x1803ab7dd  call    SampMaybeBeginDsTransaction
0x1803ab7e2  mov     edi, eax
0x1803ab7e4  test    eax, eax
0x1803ab7e6  js      loc_1803ABCBA
0x1803ab7ec  mov     rsi, [rsp+930h+hMem]
0x1803ab7f1  lea     rcx, [rbp+830h+var_680]
0x1803ab7f8  mov     eax, 2
0x1803ab7fd  mov     [rbp+830h+var_4A8], 41h ; 'A'
0x1803ab804  mov     [rbp+830h+var_428], ax
0x1803ab80b  mov     ebx, 1
0x1803ab810  lea     rax, [rbp+830h+var_400]
0x1803ab817  mov     [rbp+830h+var_3F8], 49h ; 'I'
0x1803ab81e  mov     [rbp+830h+var_420], rax
0x1803ab825  lea     rax, [rbp+830h+var_350]
0x1803ab82c  mov     [rbp+830h+var_400], rax
0x1803ab833  lea     rax, [rsp+930h+var_8CC]
0x1803ab838  mov     [rbp+830h+var_328], rax
0x1803ab83f  lea     rax, [rbp+830h+var_4B0]
0x1803ab846  mov     [rbp+830h+var_698], rax
0x1803ab84d  lea     rax, [rbp+830h+var_858]
0x1803ab851  mov     [rbp+830h+var_690], rax
0x1803ab858  mov     eax, [rbp+830h+var_69C]
0x1803ab85e  and     eax, 0FFFFFFDFh
0x1803ab861  mov     [rbp+830h+var_3F0], r13b
0x1803ab868  or      eax, ebx
0x1803ab86a  mov     [rbp+830h+var_3E8], 90092h
0x1803ab874  mov     [rbp+830h+var_69C], eax
0x1803ab87a  mov     [rbp+830h+var_348], 49h ; 'I'
0x1803ab881  mov     [rbp+830h+var_340], r13b
0x1803ab888  mov     [rbp+830h+var_338], r13d
0x1803ab88f  mov     [rbp+830h+var_330], 4
0x1803ab899  mov     [rbp+830h+var_350], r13
0x1803ab8a0  mov     [rbp+830h+var_6B0], rsi
0x1803ab8a7  mov     [rbp+830h+var_6A8], bl
0x1803ab8ad  call    BuildStdCommArg
0x1803ab8b2  lea     rax, [rbp+830h+var_890]
0x1803ab8b6  mov     dword ptr [rbp+830h+var_870], 3
0x1803ab8bd  mov     [rbp+830h+var_860], rax
0x1803ab8c1  lea     rcx, [rbp+830h+var_590]
0x1803ab8c8  lea     rax, [rbp+830h+var_870]
0x1803ab8cc  mov     dword ptr [rbp+830h+var_870+8], ebx
0x1803ab8cf  mov     [rbp+830h+var_5A0], rax
0x1803ab8d6  call    BuildStdCommArg
0x1803ab8db  mov     ebx, r13d
0x1803ab8de  mov     [rsp+930h+var_900], ebx
0x1803ab8e2  test    r14d, r14d
0x1803ab8e5  jz      loc_1803ABCA3
0x1803ab8eb  mov     r15d, r14d
0x1803ab8ee  mov     edi, 0C0000017h
0x1803ab8f3  xor     r14d, r14d
0x1803ab8f6  mov     [rsp+930h+var_8F0], r14d
0x1803ab8fb  lea     r9, [rsp+930h+cbSid]; cbSid
0x1803ab900  xorps   xmm0, xmm0
0x1803ab903  mov     [rsp+930h+cbSid], 44h ; 'D'
0x1803ab90b  lea     r14, ds:0[r13*2]
0x1803ab913  mov     dword ptr [rsp+930h+var_8E8], 100h
0x1803ab91b  add     r14, r13
0x1803ab91e  lea     r8, [rbp+830h+pSid]; pSid
0x1803ab925  xor     edx, edx; DomainSid
0x1803ab927  movups  xmmword ptr [rbp+830h+DestinationString.Length], xmm0
0x1803ab92b  mov     ecx, [r12+r14*8]; WellKnownSidType
0x1803ab92f  call    cs:__imp_CreateWellKnownSid
0x1803ab935  test    eax, eax
0x1803ab937  jz      loc_1803ABC33
0x1803ab93d  lea     rax, [rbp+830h+pSid]
0x1803ab944  mov     [rbp+830h+var_3D8], rax
0x1803ab94b  lea     rdx, [rsp+930h+var_8C8]
0x1803ab950  mov     eax, [rsp+930h+cbSid]
0x1803ab954  lea     rcx, [rbp+830h+var_6B0]
0x1803ab95b  mov     [rbp+830h+var_3E0], eax
0x1803ab961  call    DirSearchNative
0x1803ab966  mov     rsi, [rsp+930h+var_8C8]
0x1803ab96b  mov     [rsp+930h+var_8FC], eax
0x1803ab96f  test    rsi, rsi
0x1803ab972  jnz     short loc_1803AB980
0x1803ab974  mov     ebx, edi
0x1803ab976  call    THClearErrors
0x1803ab97b  jmp     loc_1803ABA20
0x1803ab980  lea     rdx, [rsi+48h]
0x1803ab984  mov     ecx, eax
0x1803ab986  call    SampMapDsErrorToNTStatus
0x1803ab98b  mov     ebx, eax
0x1803ab98d  call    THClearErrors
0x1803ab992  test    ebx, ebx
0x1803ab994  js      loc_1803ABA20
0x1803ab99a  cmp     dword ptr [rsi+10h], 1
0x1803ab99e  jnz     loc_1803ABC29
0x1803ab9a4  mov     r12, [rsi+20h]
0x1803ab9a8  lea     r9, [rsp+930h+var_8F0]
0x1803ab9ad  mov     rcx, r12
0x1803ab9b0  lea     r8, [rsp+930h+var_8E8]
0x1803ab9b5  lea     rdx, [rbp+830h+var_250]
0x1803ab9bc  call    GetRDNInfoExternal
0x1803ab9c1  xor     ebx, ebx
0x1803ab9c3  test    eax, eax
0x1803ab9c5  jz      short loc_1803AB9CE
0x1803ab9c7  mov     ebx, 0C00000E5h
0x1803ab9cc  jmp     short loc_1803ABA1B
0x1803ab9ce  mov     rdx, [rsp+930h+var_8F8]
0x1803ab9d3  lea     rcx, [rbp+830h+var_250]
0x1803ab9da  mov     r8d, dword ptr [rsp+930h+var_8E8]
0x1803ab9df  mov     rdx, [rdx+r14*8+8]
0x1803ab9e4  call    cs:__imp__o__wcsnicmp
0x1803ab9ea  test    eax, eax
0x1803ab9ec  jnz     loc_1803ABC76
0x1803ab9f2  cmp     dword ptr [rsi+30h], 1
0x1803ab9f6  mov     r14d, ebx
0x1803ab9f9  jnz     short loc_1803ABA3C
0x1803ab9fb  mov     rdx, [rsi+38h]
0x1803ab9ff  mov     ecx, [rdx+8]
0x1803aba02  test    ecx, ecx
0x1803aba04  jz      short loc_1803ABA3C
0x1803aba06  cmp     ecx, 1
0x1803aba09  jz      short loc_1803ABA31
0x1803aba0b  mov     ebx, 0C00000E5h
0x1803aba10  lea     r14, ds:0[r13*2]
0x1803aba18  add     r14, r13
0x1803aba1b  mov     r12, [rsp+930h+var_8F8]
0x1803aba20  mov     ecx, ebx; Status
0x1803aba22  call    cs:__imp_RtlNtStatusToDosError
0x1803aba28  mov     ebx, [rsp+930h+var_900]
0x1803aba2c  jmp     loc_1803ABC39
0x1803aba31  mov     rax, [rdx+10h]
0x1803aba35  mov     rcx, [rax+8]
0x1803aba39  mov     r14d, [rcx]
0x1803aba3c  mov     sil, bl
0x1803aba3f  bt      r14d, 1Eh
0x1803aba44  jb      loc_1803ABAF2
0x1803aba4a  xor     edx, edx; Val
0x1803aba4c  lea     rcx, [rbp+830h+var_810]; void *
0x1803aba50  mov     r8d, 160h; Size
0x1803aba56  call    memset_0
0x1803aba5b  mov     eax, r14d
0x1803aba5e  mov     [rsp+930h+var_8E8], rbx
0x1803aba63  bts     eax, 1Eh
0x1803aba67  mov     [rbp+830h+var_8A0], 4
0x1803aba6f  mov     [rsp+930h+var_8F0], eax
0x1803aba73  lea     rcx, [rbp+830h+var_788]
0x1803aba7a  lea     rax, [rsp+930h+var_8F0]
0x1803aba7f  mov     [rbp+830h+var_810], r12
0x1803aba83  mov     [rbp+830h+var_898], rax
0x1803aba87  mov     eax, 43h ; 'C'
0x1803aba8c  mov     [rbp+830h+var_7F8], ax
0x1803aba90  mov     [rbp+830h+var_800], rbx
0x1803aba94  mov     [rbp+830h+var_7F0], 90177h
0x1803aba9b  lea     esi, [rax-42h]
0x1803aba9e  lea     rax, [rbp+830h+var_8A0]
0x1803abaa2  mov     [rbp+830h+var_7E8], esi
0x1803abaa5  mov     [rbp+830h+var_7E0], rax
0x1803abaa9  mov     [rbp+830h+var_808], si
0x1803abaad  call    BuildStdCommArg
0x1803abab2  lea     rdx, [rsp+930h+var_8E8]
0x1803abab7  lea     rcx, [rbp+830h+var_810]
0x1803ababb  call    DirModifyEntryNative
0x1803abac0  mov     rdx, [rsp+930h+var_8E8]
0x1803abac5  mov     [rsp+930h+var_8FC], eax
0x1803abac9  test    rdx, rdx
0x1803abacc  jnz     short loc_1803ABADA
0x1803abace  mov     ebx, edi
0x1803abad0  call    THClearErrors
0x1803abad5  jmp     loc_1803ABA10
0x1803abada  mov     ecx, eax
0x1803abadc  call    SampMapDsErrorToNTStatus
0x1803abae1  mov     ebx, eax
0x1803abae3  call    THClearErrors
0x1803abae8  test    ebx, ebx
0x1803abaea  js      loc_1803ABA10
0x1803abaf0  xor     ebx, ebx
0x1803abaf2  mov     rax, [rsp+930h+var_8F8]
0x1803abaf7  lea     rcx, ds:0[r13*2]
0x1803abaff  add     rcx, r13
0x1803abb02  mov     rcx, [rax+rcx*8+10h]
0x1803abb07  or      rax, 0FFFFFFFFFFFFFFFFh
0x1803abb0b  mov     qword ptr [rbp+830h+var_890+8], rcx
0x1803abb0f  inc     rax
0x1803abb12  cmp     [rcx+rax*2], bx
0x1803abb16  jnz     short loc_1803ABB0F
0x1803abb18  add     eax, eax
0x1803abb1a  mov     [rbp+830h+var_5B0], r12
0x1803abb21  lea     rdx, [rsp+930h+var_8C0]
0x1803abb26  mov     dword ptr [rbp+830h+var_890], eax
0x1803abb29  lea     rcx, [rbp+830h+var_5B0]
0x1803abb30  call    DirModifyDN
0x1803abb35  mov     rdx, [rsp+930h+var_8C0]
0x1803abb3a  mov     [rsp+930h+var_8FC], eax
0x1803abb3e  test    rdx, rdx
0x1803abb41  jnz     short loc_1803ABB47
0x1803abb43  mov     ebx, edi
0x1803abb45  jmp     short loc_1803ABB50
0x1803abb47  mov     ecx, eax
0x1803abb49  call    SampMapDsErrorToNTStatus
0x1803abb4e  mov     ebx, eax
0x1803abb50  call    THClearErrors
0x1803abb55  test    sil, sil
0x1803abb58  jz      loc_1803ABC17
0x1803abb5e  xor     edx, edx; Val
0x1803abb60  lea     rcx, [rbp+830h+var_810]; void *
0x1803abb64  mov     r8d, 160h; Size
0x1803abb6a  call    memset_0
0x1803abb6f  lea     rax, [rsp+930h+var_8F0]
0x1803abb74  mov     [rsp+930h+var_8F0], r14d
0x1803abb79  mov     [rbp+830h+var_878], rax
0x1803abb7d  xor     r14d, r14d
0x1803abb80  mov     [rsp+930h+var_8E8], 0
0x1803abb89  mov     [rbp+830h+var_880], 4
0x1803abb91  mov     [rbp+830h+var_810], r12
0x1803abb95  lea     eax, [r14+43h]
0x1803abb99  mov     [rbp+830h+var_800], r14
  ... truncated ...
```
