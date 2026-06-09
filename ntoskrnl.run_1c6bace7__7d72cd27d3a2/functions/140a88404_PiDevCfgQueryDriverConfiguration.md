# PiDevCfgQueryDriverConfiguration

- ea: `0x140a88404`
- end: `0x140a889ef`
- name: `PiDevCfgQueryDriverConfiguration`
- size: `1515`
- prototype: ``
- caller_count: `5`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x14076d30c`
- `0x14076f7f8`
- `0x140770bf4`
- `0x1409b85fc`
- `0x140a88b90`

## callees

- `0x140403380`
- `0x1406dc8c0`
- `0x1406f7380`
- `0x140878f34`
- `0x1408f3700`
- `0x140923cd0`
- `0x14094b120`
- `0x140a87f94`
- `0x140a88404`
- `0x140a889f8`
- `0x140a88b90`
- `0x140a88f0c`
- `0x140bb19d0`

## string_xrefs

- `0x140a8851e`: `ConfigFlags`
- `0x140a88549`: `IncludedConfigs`
- `0x140a884a9`: `Service`
- `0x140a88506`: `Win32Services`

## pseudocode

```c
__int64 __fastcall PiDevCfgQueryDriverConfiguration(__int64 a1)
{
  int v1; // eax
  const WCHAR *v3; // rbx
  int RegistryValues; // eax
  int ObjectProperties; // ebx
  const WCHAR *v6; // rcx
  const WCHAR *v8; // rsi
  const WCHAR *v9; // rsi
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // r8
  char v13; // al
  __int64 v14; // rax
  __int64 v15; // rax
  ULONG v16; // [rsp+20h] [rbp-E0h]
  _BYTE v17[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[2]; // [rsp+62h] [rbp-9Eh] BYREF
  int v19; // [rsp+64h] [rbp-9Ch] BYREF
  int v20; // [rsp+68h] [rbp-98h] BYREF
  UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  int v22[2]; // [rsp+80h] [rbp-80h] BYREF
  int v23; // [rsp+88h] [rbp-78h]
  const wchar_t *v24; // [rsp+90h] [rbp-70h]
  __int64 v25; // [rsp+98h] [rbp-68h]
  int v26; // [rsp+A0h] [rbp-60h]
  const int *v27; // [rsp+A8h] [rbp-58h]
  int v28; // [rsp+B0h] [rbp-50h]
  __int64 v29; // [rsp+B8h] [rbp-48h]
  int v30; // [rsp+C0h] [rbp-40h]
  int v31; // [rsp+C4h] [rbp-3Ch]
  const wchar_t *v32; // [rsp+C8h] [rbp-38h]
  __int64 *v33; // [rsp+D0h] [rbp-30h]
  int v34; // [rsp+D8h] [rbp-28h]
  _BYTE *v35; // [rsp+E0h] [rbp-20h]
  int v36; // [rsp+E8h] [rbp-18h]
  int v37; // [rsp+F0h] [rbp-10h]
  __int64 *v38; // [rsp+F8h] [rbp-8h]
  const wchar_t *v39; // [rsp+100h] [rbp+0h]
  UNICODE_STRING *p_DestinationString; // [rsp+108h] [rbp+8h]
  int v41; // [rsp+110h] [rbp+10h]
  int v42; // [rsp+114h] [rbp+14h]
  int v43; // [rsp+118h] [rbp+18h]
  int v44; // [rsp+130h] [rbp+30h]
  const wchar_t *v45; // [rsp+138h] [rbp+38h]
  __int64 v46; // [rsp+140h] [rbp+40h]
  int v47; // [rsp+148h] [rbp+48h]
  int v48; // [rsp+168h] [rbp+68h]
  const wchar_t *v49; // [rsp+170h] [rbp+70h]
  __int64 v50; // [rsp+178h] [rbp+78h]
  int v51; // [rsp+180h] [rbp+80h]
  int v52; // [rsp+1A0h] [rbp+A0h]
  const wchar_t *v53; // [rsp+1A8h] [rbp+A8h]
  __int64 v54; // [rsp+1B0h] [rbp+B0h]
  int v55; // [rsp+1B8h] [rbp+B8h]
  int v56; // [rsp+1D8h] [rbp+D8h]
  const wchar_t *v57; // [rsp+1E0h] [rbp+E0h]
  __int64 v58; // [rsp+1E8h] [rbp+E8h]
  int v59; // [rsp+1F0h] [rbp+F0h]
  int v60; // [rsp+210h] [rbp+110h]
  const wchar_t *v61; // [rsp+218h] [rbp+118h]
  __int64 v62; // [rsp+220h] [rbp+120h]
  int v63; // [rsp+228h] [rbp+128h]
  int v64; // [rsp+248h] [rbp+148h]
  const wchar_t *v65; // [rsp+250h] [rbp+150h]
  __int64 v66; // [rsp+258h] [rbp+158h]
  int v67; // [rsp+260h] [rbp+160h]

  v1 = *(_DWORD *)(a1 + 184);
  v17[1] = 0;
  v17[0] = 0;
  v18[0] = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  v19 = 1;
  v20 = 0;
  if ( (v1 & 0x20) != 0 )
  {
    v3 = *(const WCHAR **)(a1 + 32);
    if ( !v3 )
      return (unsigned int)-1073740653;
  }
  else
  {
    ObjectProperties = PiDevCfgBuildDriverConfigurationId(a1, a1 + 424);
    if ( ObjectProperties < 0 )
      goto LABEL_16;
    if ( !*(_QWORD *)(a1 + 24) || (v3 = *(const WCHAR **)(a1 + 32)) == 0 )
    {
LABEL_15:
      ObjectProperties = -1073740653;
      goto LABEL_16;
    }
  }
  memset_0(v22, 0, 0x230u);
  v26 = 0x1000000;
  v34 = 117440512;
  v23 = 288;
  v41 = 117440512;
  v24 = L"Service";
  v47 = 117440512;
  v30 = 304;
  v25 = a1 + 288;
  LODWORD(v38) = 304;
  v32 = L"LowerFilters";
  v44 = 304;
  v39 = L"UpperFilters";
  v51 = 0x4000000;
  v45 = L"Win32Services";
  v55 = 117440512;
  v49 = L"ConfigFlags";
  v50 = a1 + 416;
  v53 = L"IncludedInfs";
  v57 = L"IncludedConfigs";
  v61 = L"Reboot";
  v62 = a1 + 420;
  v65 = L"ShimIds";
  v52 = 304;
  v59 = 117440512;
  v56 = 304;
  v63 = 0x4000000;
  v60 = 288;
  v67 = 117440512;
  v64 = 304;
  v66 = a1 + 400;
  v33 = (__int64 *)(a1 + 304);
  p_DestinationString = (UNICODE_STRING *)(a1 + 320);
  v46 = a1 + 336;
  v48 = 292;
  v54 = a1 + 352;
  v58 = a1 + 368;
  RegistryValues = RtlpQueryRegistryValues(3221225472LL, v3, v22, 0, v16, 1);
  ObjectProperties = RegistryValues;
  if ( RegistryValues == -1073741772 )
    goto LABEL_15;
  if ( RegistryValues < 0 )
    goto LABEL_16;
  if ( *(_WORD *)(a1 + 304) <= 2u && *(_QWORD *)(a1 + 312) )
    RtlFreeAnsiString((PUNICODE_STRING)(a1 + 304));
  if ( *(_WORD *)(a1 + 320) <= 2u && *(_QWORD *)(a1 + 328) )
    RtlFreeAnsiString((PUNICODE_STRING)(a1 + 320));
  if ( *(_WORD *)(a1 + 336) <= 2u && *(_QWORD *)(a1 + 344) )
    RtlFreeAnsiString((PUNICODE_STRING)(a1 + 336));
  if ( *(_WORD *)(a1 + 352) <= 2u && *(_QWORD *)(a1 + 360) )
    RtlFreeAnsiString((PUNICODE_STRING)(a1 + 352));
  if ( *(_WORD *)(a1 + 368) <= 2u && *(_QWORD *)(a1 + 376) )
    RtlFreeAnsiString((PUNICODE_STRING)(a1 + 368));
  if ( *(_WORD *)(a1 + 400) <= 2u && *(_QWORD *)(a1 + 408) )
    RtlFreeAnsiString((PUNICODE_STRING)(a1 + 400));
  if ( (*(_DWORD *)(a1 + 184) & 0x20) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 104) & 4) == 0 && *(_QWORD *)(a1 + 296) )
      RtlFreeAnsiString((PUNICODE_STRING)(a1 + 288));
    if ( (*(_DWORD *)(a1 + 104) & 2) == 0 )
    {
      if ( *(_QWORD *)(a1 + 312) )
        RtlFreeAnsiString((PUNICODE_STRING)(a1 + 304));
      if ( *(_QWORD *)(a1 + 328) )
        RtlFreeAnsiString((PUNICODE_STRING)(a1 + 320));
    }
  }
  v6 = *(const WCHAR **)(a1 + 296);
  if ( v6 )
  {
    if ( *(_WORD *)(a1 + 288) )
    {
      ObjectProperties = PiDevCfgVerifyService(v6);
      if ( ObjectProperties < 0 )
        goto LABEL_15;
    }
  }
  v8 = *(const WCHAR **)(a1 + 312);
  if ( v8 )
  {
    while ( *v8 )
    {
      ObjectProperties = PiDevCfgVerifyService(v8);
      if ( ObjectProperties < 0 )
        goto LABEL_15;
      v14 = -1;
      do
        ++v14;
      while ( v8[v14] );
      v8 += v14 + 1;
    }
    if ( ObjectProperties < 0 )
      goto LABEL_16;
  }
  v9 = *(const WCHAR **)(a1 + 328);
  if ( v9 )
  {
    while ( *v9 )
    {
      ObjectProperties = PiDevCfgVerifyService(v9);
      if ( ObjectProperties < 0 )
        goto LABEL_15;
      v15 = -1;
      do
        ++v15;
      while ( v9[v15] );
      v9 += v15 + 1;
    }
    if ( ObjectProperties < 0 )
      goto LABEL_16;
  }
  if ( (*(_DWORD *)(a1 + 184) & 0x20) != 0 )
    goto LABEL_35;
  memset_0(v22, 0, 0xA0u);
  v10 = *(_QWORD *)(a1 + 16);
  v11 = *(_QWORD *)(a1 + 64);
  *(_QWORD *)v22 = DEVPKEY_DriverPackage_ClassGuid;
  v23 = 13;
  v27 = &DEVPKEY_DriverPackage_ProviderName;
  v33 = DEVPKEY_DriverPackage_NeedsReconfig;
  v35 = v17;
  v24 = (const wchar_t *)(a1 + 240);
  v38 = DEVPKEY_DriverPackage_GroupIds;
  LODWORD(v25) = 16;
  p_DestinationString = &DestinationString;
  v28 = 18;
  v29 = a1 + 272;
  v31 = 6;
  v34 = 17;
  v36 = 1;
  LODWORD(v39) = 8210;
  v42 = 6;
  ObjectProperties = PiDevCfgQueryObjectProperties(6, v11, 8, v10, (__int64)v22, 4);
  if ( ObjectProperties < 0 )
    goto LABEL_16;
  if ( v26 < 0 )
  {
    *(_OWORD *)(a1 + 240) = 0;
    goto LABEL_25;
  }
  LOBYTE(v12) = 1;
  ObjectProperties = RtlStringFromGUIDEx(a1 + 240, a1 + 256, v12);
  if ( ObjectProperties >= 0 )
  {
LABEL_25:
    if ( (int)v32 < 0 )
      RtlInitUnicodeString((PUNICODE_STRING)(a1 + 272), 0);
    if ( v37 < 0 )
    {
      v13 = 0;
      v17[0] = 0;
    }
    else
    {
      v13 = v17[0];
    }
    if ( v13 == -1 )
      *(_DWORD *)(a1 + 184) |= 0x40u;
    if ( v43 < 0 )
      RtlInitUnicodeString(&DestinationString, 0);
    if ( DestinationString.Buffer )
    {
      if ( DestinationString.Length > 2u )
      {
        *(_DWORD *)(a1 + 184) |= 0x80u;
        if ( (int)PnpGetObjectProperty(
                    PiPnpRtlCtx,
                    *(_QWORD *)(a1 + 64),
                    8,
                    *(_QWORD *)(a1 + 16),
                    0,
                    (__int64)DEVPKEY_DriverPackage_NoGroupUpdate,
                    (__int64)&v19,
                    (__int64)v18,
                    1,
                    (__int64)&v20,
                    0) < 0
          || v19 != 17
          || v20 != 1
          || !v18[0] )
        {
          *(_DWORD *)(a1 + 184) |= 0x100u;
        }
      }
    }
    ObjectProperties = PiDevCfgQueryIncludedDriverConfigurations(a1);
    if ( ObjectProperties < 0 )
      goto LABEL_16;
LABEL_35:
    *(_DWORD *)(a1 + 184) |= 1u;
  }
LABEL_16:
  if ( DestinationString.Buffer )
    ExFreePool(DestinationString.Buffer);
  return (unsigned int)ObjectProperties;
}

```

## disassembly

```asm
0x140a88404  push    rbp
0x140a88406  push    rbx
0x140a88407  push    rsi
0x140a88408  push    rdi
0x140a88409  push    r12
0x140a8840b  push    r13
0x140a8840d  push    r14
0x140a8840f  push    r15
0x140a88411  lea     rbp, [rsp-1C8h]
0x140a88419  sub     rsp, 2C8h
0x140a88420  mov     rax, cs:__security_cookie
0x140a88427  xor     rax, rsp
0x140a8842a  mov     [rbp+200h+var_50], rax
0x140a88431  mov     eax, [rcx+0B8h]
0x140a88437  xor     r12d, r12d
0x140a8843a  mov     [rsp+300h+var_29F], r12b
0x140a8843f  mov     rdi, rcx
0x140a88442  mov     [rsp+300h+var_2A0], r12b
0x140a88447  mov     [rsp+300h+var_29E], r12b
0x140a8844c  mov     qword ptr [rsp+300h+DestinationString.Length], r12
0x140a88451  mov     [rsp+300h+DestinationString.Buffer], r12
0x140a88456  mov     [rsp+300h+var_29C], 1
0x140a8845e  mov     [rsp+300h+var_298], r12d
0x140a88463  test    al, 20h
0x140a88465  jz      loc_140A88839
0x140a8846b  mov     rbx, [rcx+20h]
0x140a8846f  test    rbx, rbx
0x140a88472  jz      loc_140A8888C
0x140a88478  xor     edx, edx; Val
0x140a8847a  lea     rcx, [rbp+200h+var_280]; void *
0x140a8847e  mov     r8d, 230h; Size
0x140a88484  call    memset_0
0x140a88489  mov     r8d, 7000000h
0x140a8848f  mov     [rbp+200h+var_260], 1000000h
0x140a88496  mov     r9d, 120h
0x140a8849c  mov     [rbp+200h+var_228], r8d
0x140a884a0  mov     ecx, 4000000h
0x140a884a5  mov     [rbp+200h+var_278], r9d
0x140a884a9  lea     rax, aService_0; "Service"
0x140a884b0  mov     [rbp+200h+var_1F0], r8d
0x140a884b4  mov     [rbp+200h+var_270], rax
0x140a884b8  lea     rsi, [rdi+130h]
0x140a884bf  lea     edx, [r9+10h]
0x140a884c3  mov     [rbp+200h+var_1B8], r8d
0x140a884c7  lea     rax, [rdi+120h]
0x140a884ce  mov     [rbp+200h+var_240], edx
0x140a884d1  mov     [rbp+200h+var_268], rax
0x140a884d5  lea     r14, [rdi+140h]
0x140a884dc  lea     rax, aLowerfilters; "LowerFilters"
0x140a884e3  mov     dword ptr [rbp+200h+var_208], edx
0x140a884e6  mov     [rbp+200h+var_238], rax
0x140a884ea  lea     r15, [rdi+150h]
0x140a884f1  lea     rax, aUpperfilters_0; "UpperFilters"
0x140a884f8  mov     [rbp+200h+var_1D0], edx
0x140a884fb  mov     [rbp+200h+var_200], rax
0x140a884ff  lea     r12, [rdi+160h]
0x140a88506  lea     rax, aWin32services; "Win32Services"
0x140a8850d  mov     [rbp+200h+var_180], ecx
0x140a88513  mov     [rbp+200h+var_1C8], rax
0x140a88517  lea     r13, [rdi+170h]
0x140a8851e  lea     rax, aConfigflags; "ConfigFlags"
0x140a88525  mov     [rbp+200h+var_148], r8d
0x140a8852c  mov     [rbp+200h+var_190], rax
0x140a88530  lea     rax, [rdi+1A0h]
0x140a88537  mov     [rbp+200h+var_188], rax
0x140a8853b  lea     rax, aIncludedinfs_0; "IncludedInfs"
0x140a88542  mov     [rbp+200h+var_158], rax
0x140a88549  lea     rax, aIncludedconfig; "IncludedConfigs"
0x140a88550  mov     [rbp+200h+var_120], rax
0x140a88557  lea     rax, aReboot; "Reboot"
0x140a8855e  mov     [rbp+200h+var_E8], rax
0x140a88565  lea     rax, [rdi+1A4h]
0x140a8856c  mov     [rbp+200h+var_E0], rax
0x140a88573  lea     rax, aShimids; "ShimIds"
0x140a8857a  mov     [rbp+200h+var_B0], rax
0x140a88581  lea     rax, [rdi+190h]
0x140a88588  mov     [rbp+200h+var_160], edx
0x140a8858e  mov     [rbp+200h+var_110], r8d
0x140a88595  mov     [rbp+200h+var_128], edx
0x140a8859b  mov     [rbp+200h+var_D8], ecx
0x140a885a1  mov     ecx, 0C0000000h; int
0x140a885a6  mov     [rbp+200h+var_F0], r9d
0x140a885ad  xor     r9d, r9d; int
0x140a885b0  mov     [rbp+200h+var_A0], r8d
0x140a885b7  lea     r8, [rbp+200h+var_280]; int
0x140a885bb  mov     [rbp+200h+var_B8], edx
0x140a885c1  mov     rdx, rbx; int
0x140a885c4  mov     [rbp+200h+var_A8], rax
0x140a885cb  mov     [rbp+200h+var_230], rsi
0x140a885cf  mov     [rbp+200h+var_1F8], r14
0x140a885d3  mov     [rbp+200h+var_1C0], r15
0x140a885d7  mov     [rbp+200h+var_198], 124h
0x140a885de  mov     [rbp+200h+var_150], r12
0x140a885e5  mov     [rbp+200h+var_118], r13
0x140a885ec  mov     [rsp+300h+var_2D8], 1; char
0x140a885f1  call    RtlpQueryRegistryValues
0x140a885f6  mov     ebx, eax
0x140a885f8  cmp     eax, 0C0000034h
0x140a885fd  jz      loc_140A88695
0x140a88603  test    eax, eax
0x140a88605  js      loc_140A8869A
0x140a8860b  cmp     word ptr [rsi], 2
0x140a8860f  jbe     loc_140A88896
0x140a88615  cmp     word ptr [r14], 2
0x140a8861a  jbe     loc_140A888B1
0x140a88620  cmp     word ptr [r15], 2
0x140a88625  jbe     loc_140A888CC
0x140a8862b  cmp     word ptr [r12], 2
0x140a88631  jbe     loc_140A888E7
0x140a88637  xor     r12d, r12d
0x140a8863a  cmp     word ptr [r13+0], 2
0x140a88640  jbe     loc_140A88902
0x140a88646  lea     rcx, [rdi+190h]; UnicodeString
0x140a8864d  cmp     word ptr [rcx], 2
0x140a88651  jbe     loc_140A8891C
0x140a88657  mov     eax, [rdi+0B8h]
0x140a8865d  lea     r15, [rdi+120h]
0x140a88664  test    al, 20h
0x140a88666  jnz     loc_140A88933
0x140a8866c  mov     rcx, [rdi+128h]; SourceString
0x140a88673  test    rcx, rcx
0x140a88676  jz      short loc_140A886DA
0x140a88678  cmp     [r15], r12w
0x140a8867c  jz      short loc_140A886DA
0x140a8867e  lea     r8, [rdi+1B8h]
0x140a88685  lea     rdx, [rsp+300h+var_29F]
0x140a8868a  call    PiDevCfgVerifyService
0x140a8868f  mov     ebx, eax
0x140a88691  test    eax, eax
0x140a88693  jns     short loc_140A886CF
0x140a88695  mov     ebx, 0C0000493h
0x140a8869a  mov     rcx, [rsp+300h+DestinationString.Buffer]; P
0x140a8869f  test    rcx, rcx
0x140a886a2  jz      short loc_140A886A9
0x140a886a4  call    ExFreePool
0x140a886a9  mov     eax, ebx
0x140a886ab  mov     rcx, [rbp+200h+var_50]
0x140a886b2  xor     rcx, rsp; StackCookie
0x140a886b5  call    __security_check_cookie
0x140a886ba  add     rsp, 2C8h
0x140a886c1  pop     r15
0x140a886c3  pop     r14
0x140a886c5  pop     r13
0x140a886c7  pop     r12
0x140a886c9  pop     rdi
0x140a886ca  pop     rsi
0x140a886cb  pop     rbx
0x140a886cc  pop     rbp
0x140a886cd  retn
0x140a886cf  cmp     [rsp+300h+var_29F], r12b
0x140a886d4  jnz     loc_140A88959
0x140a886da  mov     rsi, [rdi+138h]
0x140a886e1  or      r15, 0FFFFFFFFFFFFFFFFh
0x140a886e5  test    rsi, rsi
0x140a886e8  jnz     loc_140A88965
0x140a886ee  mov     rsi, [rdi+148h]
0x140a886f5  test    rsi, rsi
0x140a886f8  jnz     loc_140A8898E
0x140a886fe  mov     eax, [rdi+0B8h]
0x140a88704  test    al, 20h
0x140a88706  jnz     loc_140A8882D
0x140a8870c  xor     edx, edx; Val
0x140a8870e  lea     rcx, [rbp+200h+var_280]; void *
0x140a88712  mov     r8d, 0A0h; Size
0x140a88718  call    memset_0
0x140a8871d  mov     r9, [rdi+10h]
0x140a88721  lea     rax, DEVPKEY_DriverPackage_ClassGuid
0x140a88728  mov     rdx, [rdi+40h]
0x140a8872c  lea     rsi, [rdi+0F0h]
0x140a88733  mov     qword ptr [rbp+200h+var_280], rax
0x140a88737  lea     r14, [rdi+110h]
0x140a8873e  mov     ecx, 6
0x140a88743  mov     dword ptr [rsp+300h+var_2D8], 4
0x140a8874b  lea     rax, DEVPKEY_DriverPackage_ProviderName
0x140a88752  mov     [rbp+200h+var_278], 0Dh
0x140a88759  mov     [rbp+200h+var_258], rax
0x140a8875d  lea     rax, DEVPKEY_DriverPackage_NeedsReconfig
0x140a88764  mov     [rbp+200h+var_230], rax
0x140a88768  lea     rax, [rsp+300h+var_2A0]
0x140a8876d  mov     [rbp+200h+var_220], rax
0x140a88771  lea     r13d, [rcx+2]
0x140a88775  lea     rax, DEVPKEY_DriverPackage_GroupIds
0x140a8877c  mov     [rbp+200h+var_270], rsi
0x140a88780  mov     [rbp+200h+var_208], rax
0x140a88784  mov     r8d, r13d
0x140a88787  lea     rax, [rsp+300h+DestinationString]
0x140a8878c  mov     dword ptr [rbp+200h+var_268], 10h
0x140a88793  mov     [rbp+200h+var_1F8], rax
0x140a88797  lea     rax, [rbp+200h+var_280]
0x140a8879b  mov     [rsp+300h+var_2E0], rax
0x140a887a0  mov     [rbp+200h+var_250], 12h
0x140a887a7  mov     [rbp+200h+var_248], r14
0x140a887ab  mov     [rbp+200h+var_23C], ecx
0x140a887ae  mov     [rbp+200h+var_228], 11h
0x140a887b5  mov     [rbp+200h+var_218], 1
0x140a887bc  mov     dword ptr [rbp+200h+var_200], 2012h
0x140a887c3  mov     [rbp+200h+var_1EC], ecx
0x140a887c6  call    PiDevCfgQueryObjectProperties
0x140a887cb  mov     ebx, eax
0x140a887cd  test    eax, eax
0x140a887cf  js      loc_140A8869A
0x140a887d5  cmp     [rbp+200h+var_260], r12d
0x140a887d9  jge     loc_140A8886B
0x140a887df  xorps   xmm0, xmm0
0x140a887e2  movups  xmmword ptr [rsi], xmm0
0x140a887e5  cmp     dword ptr [rbp+200h+var_238], r12d
0x140a887e9  jl      loc_140A889B7
0x140a887ef  cmp     [rbp+200h+var_210], r12d
0x140a887f3  jl      loc_140A889C6
0x140a887f9  mov     al, [rsp+300h+var_2A0]
0x140a887fd  cmp     al, r15b
0x140a88800  jz      loc_140A889D2
0x140a88806  cmp     [rbp+200h+var_1E8], r12d
0x140a8880a  jl      loc_140A889DE
0x140a88810  cmp     [rsp+300h+DestinationString.Buffer], r12
0x140a88815  jnz     loc_140B72EC7
0x140a8881b  mov     rcx, rdi
0x140a8881e  call    PiDevCfgQueryIncludedDriverConfigurations
0x140a88823  mov     ebx, eax
0x140a88825  test    eax, eax
0x140a88827  js      loc_140A8869A
0x140a8882d  or      dword ptr [rdi+0B8h], 1
0x140a88834  jmp     loc_140A8869A
0x140a88839  lea     rdx, [rcx+1A8h]
0x140a88840  call    PiDevCfgBuildDriverConfigurationId
0x140a88845  mov     ebx, eax
0x140a88847  test    eax, eax
0x140a88849  js      loc_140A8869A
0x140a8884f  cmp     [rdi+18h], r12
0x140a88853  jz      loc_140A88695
0x140a88859  mov     rbx, [rdi+20h]
0x140a8885d  test    rbx, rbx
0x140a88860  jnz     loc_140A88478
0x140a88866  jmp     loc_140A88695
0x140a8886b  lea     rdx, [rdi+100h]
0x140a88872  mov     r8b, 1
0x140a88875  mov     rcx, rsi
0x140a88878  call    RtlStringFromGUIDEx
0x140a8887d  mov     ebx, eax
0x140a8887f  test    eax, eax
0x140a88881  js      loc_140A8869A
0x140a88887  jmp     loc_140A887E5
0x140a8888c  mov     ebx, 0C0000493h
0x140a88891  jmp     loc_140A886A9
0x140a88896  cmp     qword ptr [rdi+138h], 0
0x140a8889e  jz      loc_140A88615
0x140a888a4  mov     rcx, rsi; UnicodeString
0x140a888a7  call    RtlFreeAnsiString
0x140a888ac  jmp     loc_140A88615
0x140a888b1  cmp     qword ptr [rdi+148h], 0
0x140a888b9  jz      loc_140A88620
0x140a888bf  mov     rcx, r14; UnicodeString
0x140a888c2  call    RtlFreeAnsiString
0x140a888c7  jmp     loc_140A88620
0x140a888cc  cmp     qword ptr [rdi+158h], 0
0x140a888d4  jz      loc_140A8862B
0x140a888da  mov     rcx, r15; UnicodeString
0x140a888dd  call    RtlFreeAnsiString
0x140a888e2  jmp     loc_140A8862B
0x140a888e7  cmp     qword ptr [rdi+168h], 0
0x140a888ef  jz      loc_140A88637
0x140a888f5  mov     rcx, r12; UnicodeString
0x140a888f8  call    RtlFreeAnsiString
0x140a888fd  jmp     loc_140A88637
0x140a88902  cmp     [rdi+178h], r12
0x140a88909  jz      loc_140A88646
0x140a8890f  mov     rcx, r13; UnicodeString
0x140a88912  call    RtlFreeAnsiString
0x140a88917  jmp     loc_140A88646
0x140a8891c  cmp     [rdi+198h], r12
0x140a88923  jz      loc_140A88657
0x140a88929  call    RtlFreeAnsiString
0x140a8892e  jmp     loc_140A88657
0x140a88933  mov     eax, [rdi+68h]
0x140a88936  test    al, 4
0x140a88938  jnz     loc_140B72E48
0x140a8893e  cmp     [rdi+128h], r12
0x140a88945  jz      loc_140B72E48
0x140a8894b  mov     rcx, r15; UnicodeString
0x140a8894e  call    RtlFreeAnsiString
0x140a88953  nop
0x140a88954  jmp     loc_140B72E48
0x140a88959  or      dword ptr [rdi+0B8h], 10h
0x140a88960  jmp     loc_140A886DA
0x140a88965  cmp     [rsi], r12w
0x140a88969  jz      loc_140B72E96
0x140a8896f  xor     r8d, r8d
0x140a88972  xor     edx, edx
0x140a88974  mov     rcx, rsi; SourceString
0x140a88977  call    PiDevCfgVerifyService
0x140a8897c  mov     ebx, eax
0x140a8897e  test    eax, eax
0x140a88980  js      loc_140A88695
0x140a88986  mov     rax, r15
0x140a88989  jmp     loc_140B72E7F
0x140a8898e  cmp     [rsi], r12w
0x140a88992  jz      loc_140B72EBA
0x140a88998  xor     r8d, r8d
0x140a8899b  xor     edx, edx
0x140a8899d  mov     rcx, rsi; SourceString
  ... truncated ...
```
