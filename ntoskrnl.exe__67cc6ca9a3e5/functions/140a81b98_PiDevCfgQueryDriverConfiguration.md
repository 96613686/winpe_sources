# PiDevCfgQueryDriverConfiguration

- ea: `0x140a81b98`
- end: `0x140a82183`
- name: `PiDevCfgQueryDriverConfiguration`
- size: `1515`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140768e9c`
- `0x14076b388`
- `0x14076c784`
- `0x1409b055c`
- `0x140a82324`

## callees

- `0x1403f2d50`
- `0x1406d9d70`
- `0x1406f4880`
- `0x1408be7f0`
- `0x1408eeff0`
- `0x14092bbb0`
- `0x1409737d4`
- `0x140a81728`
- `0x140a81b98`
- `0x140a8218c`
- `0x140a82324`
- `0x140a826a0`
- `0x140bae8c0`

## string_xrefs

- `0x140a81cb2`: `ConfigFlags`
- `0x140a81c9a`: `Win32Services`
- `0x140a81c3d`: `Service`
- `0x140a81cdd`: `IncludedConfigs`

## pseudocode

```c
__int64 __fastcall PiDevCfgQueryDriverConfiguration(__int64 a1)
{
  int v1; // eax
  __int64 v3; // rbx
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
    v3 = *(_QWORD *)(a1 + 32);
    if ( !v3 )
      return (unsigned int)-1073740653;
  }
  else
  {
    ObjectProperties = PiDevCfgBuildDriverConfigurationId(a1, a1 + 424);
    if ( ObjectProperties < 0 )
      goto LABEL_16;
    if ( !*(_QWORD *)(a1 + 24) || (v3 = *(_QWORD *)(a1 + 32)) == 0 )
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
  RegistryValues = RtlpQueryRegistryValues(-1073741824, v3, (int)v22, 0, v16, 1);
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
0x140a81b98  push    rbp
0x140a81b9a  push    rbx
0x140a81b9b  push    rsi
0x140a81b9c  push    rdi
0x140a81b9d  push    r12
0x140a81b9f  push    r13
0x140a81ba1  push    r14
0x140a81ba3  push    r15
0x140a81ba5  lea     rbp, [rsp-1C8h]
0x140a81bad  sub     rsp, 2C8h
0x140a81bb4  mov     rax, cs:__security_cookie
0x140a81bbb  xor     rax, rsp
0x140a81bbe  mov     [rbp+200h+var_50], rax
0x140a81bc5  mov     eax, [rcx+0B8h]
0x140a81bcb  xor     r12d, r12d
0x140a81bce  mov     [rsp+300h+var_29F], r12b
0x140a81bd3  mov     rdi, rcx
0x140a81bd6  mov     [rsp+300h+var_2A0], r12b
0x140a81bdb  mov     [rsp+300h+var_29E], r12b
0x140a81be0  mov     qword ptr [rsp+300h+DestinationString.Length], r12
0x140a81be5  mov     [rsp+300h+DestinationString.Buffer], r12
0x140a81bea  mov     [rsp+300h+var_29C], 1
0x140a81bf2  mov     [rsp+300h+var_298], r12d
0x140a81bf7  test    al, 20h
0x140a81bf9  jz      loc_140A81FCD
0x140a81bff  mov     rbx, [rcx+20h]
0x140a81c03  test    rbx, rbx
0x140a81c06  jz      loc_140A82020
0x140a81c0c  xor     edx, edx; Val
0x140a81c0e  lea     rcx, [rbp+200h+var_280]; void *
0x140a81c12  mov     r8d, 230h; Size
0x140a81c18  call    memset_0
0x140a81c1d  mov     r8d, 7000000h
0x140a81c23  mov     [rbp+200h+var_260], 1000000h
0x140a81c2a  mov     r9d, 120h
0x140a81c30  mov     [rbp+200h+var_228], r8d
0x140a81c34  mov     ecx, 4000000h
0x140a81c39  mov     [rbp+200h+var_278], r9d
0x140a81c3d  lea     rax, aService_0; "Service"
0x140a81c44  mov     [rbp+200h+var_1F0], r8d
0x140a81c48  mov     [rbp+200h+var_270], rax
0x140a81c4c  lea     rsi, [rdi+130h]
0x140a81c53  lea     edx, [r9+10h]
0x140a81c57  mov     [rbp+200h+var_1B8], r8d
0x140a81c5b  lea     rax, [rdi+120h]
0x140a81c62  mov     [rbp+200h+var_240], edx
0x140a81c65  mov     [rbp+200h+var_268], rax
0x140a81c69  lea     r14, [rdi+140h]
0x140a81c70  lea     rax, aLowerfilters; "LowerFilters"
0x140a81c77  mov     dword ptr [rbp+200h+var_208], edx
0x140a81c7a  mov     [rbp+200h+var_238], rax
0x140a81c7e  lea     r15, [rdi+150h]
0x140a81c85  lea     rax, aUpperfilters_0; "UpperFilters"
0x140a81c8c  mov     [rbp+200h+var_1D0], edx
0x140a81c8f  mov     [rbp+200h+var_200], rax
0x140a81c93  lea     r12, [rdi+160h]
0x140a81c9a  lea     rax, aWin32services; "Win32Services"
0x140a81ca1  mov     [rbp+200h+var_180], ecx
0x140a81ca7  mov     [rbp+200h+var_1C8], rax
0x140a81cab  lea     r13, [rdi+170h]
0x140a81cb2  lea     rax, aConfigflags; "ConfigFlags"
0x140a81cb9  mov     [rbp+200h+var_148], r8d
0x140a81cc0  mov     [rbp+200h+var_190], rax
0x140a81cc4  lea     rax, [rdi+1A0h]
0x140a81ccb  mov     [rbp+200h+var_188], rax
0x140a81ccf  lea     rax, aIncludedinfs_0; "IncludedInfs"
0x140a81cd6  mov     [rbp+200h+var_158], rax
0x140a81cdd  lea     rax, aIncludedconfig; "IncludedConfigs"
0x140a81ce4  mov     [rbp+200h+var_120], rax
0x140a81ceb  lea     rax, aReboot; "Reboot"
0x140a81cf2  mov     [rbp+200h+var_E8], rax
0x140a81cf9  lea     rax, [rdi+1A4h]
0x140a81d00  mov     [rbp+200h+var_E0], rax
0x140a81d07  lea     rax, aShimids; "ShimIds"
0x140a81d0e  mov     [rbp+200h+var_B0], rax
0x140a81d15  lea     rax, [rdi+190h]
0x140a81d1c  mov     [rbp+200h+var_160], edx
0x140a81d22  mov     [rbp+200h+var_110], r8d
0x140a81d29  mov     [rbp+200h+var_128], edx
0x140a81d2f  mov     [rbp+200h+var_D8], ecx
0x140a81d35  mov     ecx, 0C0000000h; int
0x140a81d3a  mov     [rbp+200h+var_F0], r9d
0x140a81d41  xor     r9d, r9d; int
0x140a81d44  mov     [rbp+200h+var_A0], r8d
0x140a81d4b  lea     r8, [rbp+200h+var_280]; int
0x140a81d4f  mov     [rbp+200h+var_B8], edx
0x140a81d55  mov     rdx, rbx; int
0x140a81d58  mov     [rbp+200h+var_A8], rax
0x140a81d5f  mov     [rbp+200h+var_230], rsi
0x140a81d63  mov     [rbp+200h+var_1F8], r14
0x140a81d67  mov     [rbp+200h+var_1C0], r15
0x140a81d6b  mov     [rbp+200h+var_198], 124h
0x140a81d72  mov     [rbp+200h+var_150], r12
0x140a81d79  mov     [rbp+200h+var_118], r13
0x140a81d80  mov     [rsp+300h+var_2D8], 1; char
0x140a81d85  call    RtlpQueryRegistryValues
0x140a81d8a  mov     ebx, eax
0x140a81d8c  cmp     eax, 0C0000034h
0x140a81d91  jz      loc_140A81E29
0x140a81d97  test    eax, eax
0x140a81d99  js      loc_140A81E2E
0x140a81d9f  cmp     word ptr [rsi], 2
0x140a81da3  jbe     loc_140A8202A
0x140a81da9  cmp     word ptr [r14], 2
0x140a81dae  jbe     loc_140A82045
0x140a81db4  cmp     word ptr [r15], 2
0x140a81db9  jbe     loc_140A82060
0x140a81dbf  cmp     word ptr [r12], 2
0x140a81dc5  jbe     loc_140A8207B
0x140a81dcb  xor     r12d, r12d
0x140a81dce  cmp     word ptr [r13+0], 2
0x140a81dd4  jbe     loc_140A82096
0x140a81dda  lea     rcx, [rdi+190h]; UnicodeString
0x140a81de1  cmp     word ptr [rcx], 2
0x140a81de5  jbe     loc_140A820B0
0x140a81deb  mov     eax, [rdi+0B8h]
0x140a81df1  lea     r15, [rdi+120h]
0x140a81df8  test    al, 20h
0x140a81dfa  jnz     loc_140A820C7
0x140a81e00  mov     rcx, [rdi+128h]; SourceString
0x140a81e07  test    rcx, rcx
0x140a81e0a  jz      short loc_140A81E6E
0x140a81e0c  cmp     [r15], r12w
0x140a81e10  jz      short loc_140A81E6E
0x140a81e12  lea     r8, [rdi+1B8h]
0x140a81e19  lea     rdx, [rsp+300h+var_29F]
0x140a81e1e  call    PiDevCfgVerifyService
0x140a81e23  mov     ebx, eax
0x140a81e25  test    eax, eax
0x140a81e27  jns     short loc_140A81E63
0x140a81e29  mov     ebx, 0C0000493h
0x140a81e2e  mov     rcx, [rsp+300h+DestinationString.Buffer]; P
0x140a81e33  test    rcx, rcx
0x140a81e36  jz      short loc_140A81E3D
0x140a81e38  call    ExFreePool
0x140a81e3d  mov     eax, ebx
0x140a81e3f  mov     rcx, [rbp+200h+var_50]
0x140a81e46  xor     rcx, rsp; StackCookie
0x140a81e49  call    __security_check_cookie
0x140a81e4e  add     rsp, 2C8h
0x140a81e55  pop     r15
0x140a81e57  pop     r14
0x140a81e59  pop     r13
0x140a81e5b  pop     r12
0x140a81e5d  pop     rdi
0x140a81e5e  pop     rsi
0x140a81e5f  pop     rbx
0x140a81e60  pop     rbp
0x140a81e61  retn
0x140a81e63  cmp     [rsp+300h+var_29F], r12b
0x140a81e68  jnz     loc_140A820ED
0x140a81e6e  mov     rsi, [rdi+138h]
0x140a81e75  or      r15, 0FFFFFFFFFFFFFFFFh
0x140a81e79  test    rsi, rsi
0x140a81e7c  jnz     loc_140A820F9
0x140a81e82  mov     rsi, [rdi+148h]
0x140a81e89  test    rsi, rsi
0x140a81e8c  jnz     loc_140A82122
0x140a81e92  mov     eax, [rdi+0B8h]
0x140a81e98  test    al, 20h
0x140a81e9a  jnz     loc_140A81FC1
0x140a81ea0  xor     edx, edx; Val
0x140a81ea2  lea     rcx, [rbp+200h+var_280]; void *
0x140a81ea6  mov     r8d, 0A0h; Size
0x140a81eac  call    memset_0
0x140a81eb1  mov     r9, [rdi+10h]
0x140a81eb5  lea     rax, DEVPKEY_DriverPackage_ClassGuid
0x140a81ebc  mov     rdx, [rdi+40h]
0x140a81ec0  lea     rsi, [rdi+0F0h]
0x140a81ec7  mov     qword ptr [rbp+200h+var_280], rax
0x140a81ecb  lea     r14, [rdi+110h]
0x140a81ed2  mov     ecx, 6
0x140a81ed7  mov     dword ptr [rsp+300h+var_2D8], 4
0x140a81edf  lea     rax, DEVPKEY_DriverPackage_ProviderName
0x140a81ee6  mov     [rbp+200h+var_278], 0Dh
0x140a81eed  mov     [rbp+200h+var_258], rax
0x140a81ef1  lea     rax, DEVPKEY_DriverPackage_NeedsReconfig
0x140a81ef8  mov     [rbp+200h+var_230], rax
0x140a81efc  lea     rax, [rsp+300h+var_2A0]
0x140a81f01  mov     [rbp+200h+var_220], rax
0x140a81f05  lea     r13d, [rcx+2]
0x140a81f09  lea     rax, DEVPKEY_DriverPackage_GroupIds
0x140a81f10  mov     [rbp+200h+var_270], rsi
0x140a81f14  mov     [rbp+200h+var_208], rax
0x140a81f18  mov     r8d, r13d
0x140a81f1b  lea     rax, [rsp+300h+DestinationString]
0x140a81f20  mov     dword ptr [rbp+200h+var_268], 10h
0x140a81f27  mov     [rbp+200h+var_1F8], rax
0x140a81f2b  lea     rax, [rbp+200h+var_280]
0x140a81f2f  mov     [rsp+300h+var_2E0], rax
0x140a81f34  mov     [rbp+200h+var_250], 12h
0x140a81f3b  mov     [rbp+200h+var_248], r14
0x140a81f3f  mov     [rbp+200h+var_23C], ecx
0x140a81f42  mov     [rbp+200h+var_228], 11h
0x140a81f49  mov     [rbp+200h+var_218], 1
0x140a81f50  mov     dword ptr [rbp+200h+var_200], 2012h
0x140a81f57  mov     [rbp+200h+var_1EC], ecx
0x140a81f5a  call    PiDevCfgQueryObjectProperties
0x140a81f5f  mov     ebx, eax
0x140a81f61  test    eax, eax
0x140a81f63  js      loc_140A81E2E
0x140a81f69  cmp     [rbp+200h+var_260], r12d
0x140a81f6d  jge     loc_140A81FFF
0x140a81f73  xorps   xmm0, xmm0
0x140a81f76  movups  xmmword ptr [rsi], xmm0
0x140a81f79  cmp     dword ptr [rbp+200h+var_238], r12d
0x140a81f7d  jl      loc_140A8214B
0x140a81f83  cmp     [rbp+200h+var_210], r12d
0x140a81f87  jl      loc_140A8215A
0x140a81f8d  mov     al, [rsp+300h+var_2A0]
0x140a81f91  cmp     al, r15b
0x140a81f94  jz      loc_140A82166
0x140a81f9a  cmp     [rbp+200h+var_1E8], r12d
0x140a81f9e  jl      loc_140A82172
0x140a81fa4  cmp     [rsp+300h+DestinationString.Buffer], r12
0x140a81fa9  jnz     loc_140B70C35
0x140a81faf  mov     rcx, rdi
0x140a81fb2  call    PiDevCfgQueryIncludedDriverConfigurations
0x140a81fb7  mov     ebx, eax
0x140a81fb9  test    eax, eax
0x140a81fbb  js      loc_140A81E2E
0x140a81fc1  or      dword ptr [rdi+0B8h], 1
0x140a81fc8  jmp     loc_140A81E2E
0x140a81fcd  lea     rdx, [rcx+1A8h]
0x140a81fd4  call    PiDevCfgBuildDriverConfigurationId
0x140a81fd9  mov     ebx, eax
0x140a81fdb  test    eax, eax
0x140a81fdd  js      loc_140A81E2E
0x140a81fe3  cmp     [rdi+18h], r12
0x140a81fe7  jz      loc_140A81E29
0x140a81fed  mov     rbx, [rdi+20h]
0x140a81ff1  test    rbx, rbx
0x140a81ff4  jnz     loc_140A81C0C
0x140a81ffa  jmp     loc_140A81E29
0x140a81fff  lea     rdx, [rdi+100h]
0x140a82006  mov     r8b, 1
0x140a82009  mov     rcx, rsi
0x140a8200c  call    RtlStringFromGUIDEx
0x140a82011  mov     ebx, eax
0x140a82013  test    eax, eax
0x140a82015  js      loc_140A81E2E
0x140a8201b  jmp     loc_140A81F79
0x140a82020  mov     ebx, 0C0000493h
0x140a82025  jmp     loc_140A81E3D
0x140a8202a  cmp     qword ptr [rdi+138h], 0
0x140a82032  jz      loc_140A81DA9
0x140a82038  mov     rcx, rsi; UnicodeString
0x140a8203b  call    RtlFreeAnsiString
0x140a82040  jmp     loc_140A81DA9
0x140a82045  cmp     qword ptr [rdi+148h], 0
0x140a8204d  jz      loc_140A81DB4
0x140a82053  mov     rcx, r14; UnicodeString
0x140a82056  call    RtlFreeAnsiString
0x140a8205b  jmp     loc_140A81DB4
0x140a82060  cmp     qword ptr [rdi+158h], 0
0x140a82068  jz      loc_140A81DBF
0x140a8206e  mov     rcx, r15; UnicodeString
0x140a82071  call    RtlFreeAnsiString
0x140a82076  jmp     loc_140A81DBF
0x140a8207b  cmp     qword ptr [rdi+168h], 0
0x140a82083  jz      loc_140A81DCB
0x140a82089  mov     rcx, r12; UnicodeString
0x140a8208c  call    RtlFreeAnsiString
0x140a82091  jmp     loc_140A81DCB
0x140a82096  cmp     [rdi+178h], r12
0x140a8209d  jz      loc_140A81DDA
0x140a820a3  mov     rcx, r13; UnicodeString
0x140a820a6  call    RtlFreeAnsiString
0x140a820ab  jmp     loc_140A81DDA
0x140a820b0  cmp     [rdi+198h], r12
0x140a820b7  jz      loc_140A81DEB
0x140a820bd  call    RtlFreeAnsiString
0x140a820c2  jmp     loc_140A81DEB
0x140a820c7  mov     eax, [rdi+68h]
0x140a820ca  test    al, 4
0x140a820cc  jnz     loc_140B70BB6
0x140a820d2  cmp     [rdi+128h], r12
0x140a820d9  jz      loc_140B70BB6
0x140a820df  mov     rcx, r15; UnicodeString
0x140a820e2  call    RtlFreeAnsiString
0x140a820e7  nop
0x140a820e8  jmp     loc_140B70BB6
0x140a820ed  or      dword ptr [rdi+0B8h], 10h
0x140a820f4  jmp     loc_140A81E6E
0x140a820f9  cmp     [rsi], r12w
0x140a820fd  jz      loc_140B70C04
0x140a82103  xor     r8d, r8d
0x140a82106  xor     edx, edx
0x140a82108  mov     rcx, rsi; SourceString
0x140a8210b  call    PiDevCfgVerifyService
0x140a82110  mov     ebx, eax
0x140a82112  test    eax, eax
0x140a82114  js      loc_140A81E29
0x140a8211a  mov     rax, r15
0x140a8211d  jmp     loc_140B70BED
0x140a82122  cmp     [rsi], r12w
0x140a82126  jz      loc_140B70C28
0x140a8212c  xor     r8d, r8d
0x140a8212f  xor     edx, edx
0x140a82131  mov     rcx, rsi; SourceString
  ... truncated ...
```
