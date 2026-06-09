# InternalColorCplGetProfileProperties

- ea: `0x180009e34`
- end: `0x18000a303`
- name: `InternalColorCplGetProfileProperties`
- size: `1231`
- prototype: `__int64 __fastcall(unsigned __int16 *, char, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003f554`
- `0x180046350`

## callees

- `0x180009e34`
- `0x18000a30c`
- `0x18000a740`
- `0x18000bce0`
- `0x180020944`
- `0x1800230bc`
- `0x180029e64`
- `0x18002e5f0`
- `0x18002e614`
- `0x180057204`
- `0x1800576a8`
- `0x1800577f0`
- `0x1800579a8`
- `0x1800586ac`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f4a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009f3b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009f3b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180009f75`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180009f75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a2c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a2c9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a08d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a08d`
- `OLEAUT32!__imp_VariantInit` at `0x180009e9e`
- `OLEAUT32!__imp_VariantInit` at `0x180009e9e`
- `OLEAUT32!__imp_VariantClear` at `0x18000a268`
- `OLEAUT32!__imp_VariantClear` at `0x18000a268`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a05f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a05f`

## pseudocode

```c
__int64 __fastcall InternalColorCplGetProfileProperties(unsigned __int16 *a1, char a2, __int64 a3)
{
  struct IXMLDOMElement *v4; // r14
  void (__fastcall ***v5)(_QWORD, __int64); // r12
  __int64 v8; // r15
  unsigned int *v9; // r8
  __int64 v10; // rax
  int PreferredPropertiesLanguages; // eax
  int IsIccProfile; // ebx
  int ProfilePathName; // eax
  void *v14; // rsi
  HANDLE FileW; // rax
  signed int LastError; // eax
  bool *v17; // r9
  void *LowPart; // rdx
  __int64 v19; // rax
  HPROFILE v20; // rax
  int IccProfileProperties; // eax
  __int64 v22; // rax
  int v23; // eax
  int CompatibilityMarkupProcessor; // eax
  bool *v25; // r9
  bool *v26; // r9
  bool *v27; // r9
  unsigned __int64 v28; // rdx
  struct COLOR_PROFILE_PROPERTIES *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  struct COLOR_PROFILE_PROPERTIES *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  struct COLOR_PROFILE_PROPERTIES *hTemplateFile; // [rsp+30h] [rbp-D0h]
  unsigned __int16 v34[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v35[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v36[12]; // [rsp+54h] [rbp-ACh] BYREF
  struct IXMLDOMDocument2 *v37; // [rsp+60h] [rbp-A0h] BYREF
  struct IXMLDOMElement *v38; // [rsp+68h] [rbp-98h] BYREF
  _LARGE_INTEGER FileSize; // [rsp+70h] [rbp-90h] BYREF
  void (__fastcall ***v40)(_QWORD, __int64); // [rsp+78h] [rbp-88h]
  PROFILE pCDMPProfile; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-60h] BYREF
  OLECHAR FileName[264]; // [rsp+C0h] [rbp-40h] BYREF

  v38 = 0;
  *(_QWORD *)&v36[4] = 0;
  v37 = 0;
  v4 = 0;
  v40 = 0;
  v5 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v8 = -1;
  VariantInit(&pvarg);
  if ( !a1 )
    goto LABEL_47;
  v10 = -1;
  do
    ++v10;
  while ( a1[v10] );
  if ( !v10 || !a3 || *(_DWORD *)a3 != 1 )
  {
LABEL_47:
    IsIccProfile = -2147024809;
LABEL_48:
    v14 = 0;
    goto LABEL_49;
  }
  *(_DWORD *)(a3 + 8) = 0;
  *(_DWORD *)v36 = 0;
  if ( !*(_DWORD *)(a3 + 12) )
  {
    PreferredPropertiesLanguages = ProfileProperties::GetPreferredPropertiesLanguages(
                                     (ProfileProperties *)&v38,
                                     (unsigned __int16 **)v36,
                                     v9);
    v4 = v38;
    IsIccProfile = PreferredPropertiesLanguages;
    if ( PreferredPropertiesLanguages < 0 )
      goto LABEL_48;
  }
  ProfilePathName = ColorCplSupportUtil::GetProfilePathName(a1, FileName, (unsigned int)v9);
  v14 = 0;
  IsIccProfile = ProfilePathName;
  if ( ProfilePathName < 0 )
    goto LABEL_49;
  FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x10000080u, 0);
  v8 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL || (FileSize.QuadPart = 0, !GetFileSizeEx(FileW, &FileSize)) )
  {
LABEL_11:
    LastError = GetLastError();
    IsIccProfile = LastError;
    if ( LastError > 0 )
      IsIccProfile = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_49;
  }
  if ( FileSize.HighPart )
    goto LABEL_45;
  LowPart = (void *)FileSize.LowPart;
  if ( (*(_BYTE *)(a3 + 4) & 1) != 0 )
  {
    *(_DWORD *)(a3 + 8) |= 1u;
    *(_DWORD *)(a3 + 16) = (_DWORD)LowPart;
  }
  LOBYTE(v34[0]) = 0;
  IsIccProfile = ProfileProperties::IsIccProfile((HANDLE)v8, LowPart, (unsigned int)v34, v17);
  if ( IsIccProfile < 0 )
    goto LABEL_49;
  if ( LOBYTE(v34[0]) )
  {
    *(_QWORD *)&pCDMPProfile.dwType = 1;
    pCDMPProfile.pProfileData = FileName;
    v19 = -1;
    *(&pCDMPProfile.cbDataSize + 1) = 0;
    do
      ++v19;
    while ( FileName[v19] );
    pCDMPProfile.cbDataSize = 2 * v19 + 2;
    v20 = WcsOpenColorProfileW(&pCDMPProfile, 0, 0, 1u, 1u, 3u, 1u);
    v14 = v20;
    if ( v20 )
    {
      IccProfileProperties = ProfileProperties::GetIccProfileProperties(
                               v20,
                               v4,
                               (const unsigned __int16 *)*(unsigned int *)v36,
                               a3,
                               dwCreationDisposition);
LABEL_23:
      IsIccProfile = IccProfileProperties;
      goto LABEL_49;
    }
    goto LABEL_11;
  }
  if ( a2 )
  {
LABEL_45:
    IsIccProfile = -2147022885;
    goto LABEL_49;
  }
  IsIccProfile = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, (LPVOID *)&v36[4]);
  if ( IsIccProfile < 0 )
    goto LABEL_49;
  if ( !*(_QWORD *)&v36[4] )
  {
    IsIccProfile = -2147467259;
    goto LABEL_49;
  }
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(FileName);
  if ( !pvarg.llVal )
  {
    IsIccProfile = -2147024882;
    goto LABEL_49;
  }
  v35[0] = 0;
  v22 = **(_QWORD **)&v36[4];
  pCDMPProfile = (PROFILE)pvarg;
  v23 = (*(__int64 (__fastcall **)(_QWORD, PROFILE *, __int16 *))(v22 + 464))(*(_QWORD *)&v36[4], &pCDMPProfile, v35);
  IsIccProfile = v23;
  if ( v23 >= 0 )
  {
    if ( v23 == 1 || !v35[0] )
    {
      IsIccProfile = -2147221497;
      goto LABEL_49;
    }
    CompatibilityMarkupProcessor = CreateCompatibilityMarkupProcessor(5, &gc_apwszWcsNamespaces);
    v5 = v40;
    IsIccProfile = CompatibilityMarkupProcessor;
    if ( CompatibilityMarkupProcessor >= 0 )
    {
      IsIccProfile = ((__int64 (__fastcall *)(_QWORD, _QWORD))(*v40)[1])(v40, *(_QWORD *)&v36[4]);
      if ( IsIccProfile >= 0 )
      {
        IsIccProfile = (*(__int64 (__fastcall **)(_QWORD, struct IXMLDOMDocument2 **))(**(_QWORD **)&v36[4] + 360LL))(
                         *(_QWORD *)&v36[4],
                         &v37);
        if ( IsIccProfile >= 0 )
        {
          LOBYTE(v34[0]) = 0;
          IsIccProfile = ProfileProperties::IsElementInNamespace(
                           (ProfileProperties *)v37,
                           (struct IXMLDOMElement *)&stru_1800882C0,
                           v34,
                           v25);
          if ( IsIccProfile >= 0 )
          {
            if ( LOBYTE(v34[0]) )
            {
              IccProfileProperties = ProfileProperties::GetDmpProfileProperties(
                                       *(enum COLORPROFILETYPE *)&v36[4],
                                       v37,
                                       (enum COLORPROFILETYPE)v4,
                                       (const unsigned __int16 *)*(unsigned int *)v36,
                                       a3,
                                       dwFlagsAndAttributes);
              goto LABEL_23;
            }
            LOBYTE(v34[0]) = 0;
            IsIccProfile = ProfileProperties::IsElementInNamespace(
                             (ProfileProperties *)v37,
                             (struct IXMLDOMElement *)&stru_18008DEB0,
                             v34,
                             v26);
            if ( IsIccProfile >= 0 )
            {
              if ( LOBYTE(v34[0]) )
              {
                LODWORD(dwCreationDispositiona) = *(_DWORD *)v36;
                IccProfileProperties = ProfileProperties::GetCampProfileProperties(
                                         (ProfileProperties *)v8,
                                         *(void **)&v36[4],
                                         v37,
                                         v4,
                                         dwCreationDispositiona,
                                         a3,
                                         hTemplateFile);
                goto LABEL_23;
              }
              LOBYTE(v34[0]) = 0;
              IsIccProfile = ProfileProperties::IsElementInNamespace(
                               (ProfileProperties *)v37,
                               (struct IXMLDOMElement *)&stru_18008E320,
                               v34,
                               v27);
              if ( IsIccProfile >= 0 )
              {
                if ( LOBYTE(v34[0]) )
                {
                  LODWORD(dwCreationDispositiona) = *(_DWORD *)v36;
                  IccProfileProperties = ProfileProperties::GetGmmpProfileProperties(
                                           (ProfileProperties *)v8,
                                           *(void **)&v36[4],
                                           v37,
                                           v4,
                                           dwCreationDispositiona,
                                           a3,
                                           hTemplateFile);
                  goto LABEL_23;
                }
                goto LABEL_45;
              }
            }
          }
        }
      }
    }
  }
LABEL_49:
  VariantClear(&pvarg);
  if ( v37 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v37->lpVtbl->Release)(v37);
  if ( v5 )
    (**v5)(v5, 1);
  if ( *(_QWORD *)&v36[4] )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v36[4] + 16LL))(*(_QWORD *)&v36[4]);
  if ( v14 )
    CloseColorProfile(v14);
  if ( v8 != -1 )
    CloseHandle((HANDLE)v8);
  operator delete(v4, v28);
  return (unsigned int)IsIccProfile;
}

```

## disassembly

```asm
0x180009e34  mov     [rsp-8+arg_8], rbx
0x180009e39  push    rbp
0x180009e3a  push    rsi
0x180009e3b  push    rdi
0x180009e3c  push    r12
0x180009e3e  push    r13
0x180009e40  push    r14
0x180009e42  push    r15
0x180009e44  lea     rbp, [rsp-1E0h]
0x180009e4c  sub     rsp, 2E0h
0x180009e53  mov     rax, cs:__security_cookie
0x180009e5a  xor     rax, rsp
0x180009e5d  mov     [rbp+210h+var_40], rax
0x180009e64  xor     ebx, ebx
0x180009e66  mov     rsi, rcx
0x180009e69  xorps   xmm0, xmm0
0x180009e6c  mov     [rsp+310h+var_2A8], rbx
0x180009e71  xor     eax, eax
0x180009e73  mov     qword ptr [rsp+310h+var_2BC+4], rbx
0x180009e78  lea     rcx, [rbp+210h+pvarg]; pvarg
0x180009e7c  mov     [rsp+310h+var_2B0], rbx
0x180009e81  mov     r14d, ebx
0x180009e84  mov     [rsp+310h+var_298], rbx
0x180009e89  mov     r12d, ebx
0x180009e8c  mov     qword ptr [rbp+210h+pvarg+10h], rax
0x180009e90  movups  xmmword ptr [rbp+210h+pvarg], xmm0
0x180009e94  mov     rdi, r8
0x180009e97  mov     r13b, dl
0x180009e9a  or      r15, 0FFFFFFFFFFFFFFFFh
0x180009e9e  call    cs:__imp_VariantInit
0x180009ea4  test    rsi, rsi
0x180009ea7  jz      loc_18000A25C
0x180009ead  or      rax, r15
0x180009eb0  inc     rax
0x180009eb3  cmp     [rsi+rax*2], bx
0x180009eb7  jnz     short loc_180009EB0
0x180009eb9  test    rax, rax
0x180009ebc  jz      loc_18000A25C
0x180009ec2  test    rdi, rdi
0x180009ec5  jz      loc_18000A25C
0x180009ecb  cmp     dword ptr [rdi], 1
0x180009ece  jnz     loc_18000A25C
0x180009ed4  mov     [rdi+8], ebx
0x180009ed7  mov     dword ptr [rsp+310h+var_2BC], ebx
0x180009edb  cmp     [rdi+0Ch], ebx
0x180009ede  jnz     short loc_180009EFE
0x180009ee0  lea     rdx, [rsp+310h+var_2BC]; unsigned __int16 **
0x180009ee5  lea     rcx, [rsp+310h+var_2A8]; this
0x180009eea  call    ?GetPreferredPropertiesLanguages@ProfileProperties@@YAJPEAPEAGPEAK@Z; ProfileProperties::GetPreferredPropertiesLanguages(ushort * *,ulong *)
0x180009eef  mov     r14, [rsp+310h+var_2A8]
0x180009ef4  mov     ebx, eax
0x180009ef6  test    eax, eax
0x180009ef8  js      loc_18000A261
0x180009efe  lea     rdx, [rbp+210h+FileName]; unsigned __int16 *
0x180009f02  mov     rcx, rsi; unsigned __int16 *
0x180009f05  call    ?GetProfilePathName@ColorCplSupportUtil@@SAJPEBGPEAGK@Z; ColorCplSupportUtil::GetProfilePathName(ushort const *,ushort *,ulong)
0x180009f0a  xor     esi, esi
0x180009f0c  mov     ebx, eax
0x180009f0e  test    eax, eax
0x180009f10  js      loc_18000A264
0x180009f16  mov     [rsp+310h+hTemplateFile], rsi; struct COLOR_PROFILE_PROPERTIES *
0x180009f1b  lea     r8d, [rsi+1]; dwShareMode
0x180009f1f  mov     [rsp+310h+dwFlagsAndAttributes], 10000080h; struct COLOR_PROFILE_PROPERTIES *
0x180009f27  lea     rcx, [rbp+210h+FileName]; lpFileName
0x180009f2b  xor     r9d, r9d; lpSecurityAttributes
0x180009f2e  mov     [rsp+310h+dwCreationDisposition], 3; dwCreationDisposition
0x180009f36  mov     edx, 80000000h; dwDesiredAccess
0x180009f3b  call    cs:__imp_CreateFileW
0x180009f41  mov     r15, rax
0x180009f44  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009f48  jnz     short loc_180009F68
0x180009f4a  call    cs:__imp_GetLastError
0x180009f50  mov     ebx, eax
0x180009f52  test    eax, eax
0x180009f54  jle     loc_18000A264
0x180009f5a  movzx   ebx, ax
0x180009f5d  or      ebx, 80070000h
0x180009f63  jmp     loc_18000A264
0x180009f68  lea     rdx, [rsp+310h+FileSize]; lpFileSize
0x180009f6d  mov     qword ptr [rsp+310h+FileSize], rsi
0x180009f72  mov     rcx, r15; hFile
0x180009f75  call    cs:__imp_GetFileSizeEx
0x180009f7b  test    eax, eax
0x180009f7d  jz      short loc_180009F4A
0x180009f7f  cmp     dword ptr [rsp+310h+FileSize+4], esi
0x180009f83  jnz     loc_18000A24E
0x180009f89  test    byte ptr [rdi+4], 1
0x180009f8d  mov     rdx, qword ptr [rsp+310h+FileSize]; void *
0x180009f92  jz      short loc_180009F9B
0x180009f94  or      dword ptr [rdi+8], 1
0x180009f98  mov     [rdi+10h], edx
0x180009f9b  lea     r8, [rsp+310h+var_2D0]; unsigned int
0x180009fa0  mov     byte ptr [rsp+310h+var_2D0], sil
0x180009fa5  mov     rcx, r15; hFile
0x180009fa8  call    ?IsIccProfile@ProfileProperties@@YAJPEAXKPEA_N@Z; ProfileProperties::IsIccProfile(void *,ulong,bool *)
0x180009fad  mov     ebx, eax
0x180009faf  test    eax, eax
0x180009fb1  js      loc_18000A264
0x180009fb7  cmp     byte ptr [rsp+310h+var_2D0], sil
0x180009fbc  jz      short loc_18000A038
0x180009fbe  lea     rax, [rbp+210h+FileName]
0x180009fc2  mov     qword ptr [rbp+210h+pCDMPProfile.dwType], 1
0x180009fca  mov     [rbp+210h+pCDMPProfile.pProfileData], rax
0x180009fce  lea     rdx, [rbp+210h+FileName]
0x180009fd2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009fd6  mov     dword ptr [rbp+210h+pCDMPProfile+14h], esi
0x180009fd9  mov     ecx, 1
0x180009fde  inc     rax
0x180009fe1  cmp     [rdx+rax*2], si
0x180009fe5  jnz     short loc_180009FDE
0x180009fe7  mov     dword ptr [rsp+310h+hTemplateFile], ecx; dwFlags
0x180009feb  lea     eax, ds:2[rax*2]
0x180009ff2  mov     r9d, ecx; dwDesireAccess
0x180009ff5  mov     [rsp+310h+dwFlagsAndAttributes], 3; dwCreationMode
0x180009ffd  mov     [rsp+310h+dwCreationDisposition], ecx; struct COLOR_PROFILE_PROPERTIES *
0x18000a001  xor     r8d, r8d; pGMMPProfile
0x18000a004  lea     rcx, [rbp+210h+pCDMPProfile]; pCDMPProfile
0x18000a008  mov     [rbp+210h+pCDMPProfile.cbDataSize], eax
0x18000a00b  xor     edx, edx; pCAMPProfile
0x18000a00d  call    WcsOpenColorProfileW
0x18000a012  mov     rsi, rax
0x18000a015  test    rax, rax
0x18000a018  jz      loc_180009F4A
0x18000a01e  mov     r8d, dword ptr [rsp+310h+var_2BC]; unsigned __int16 *
0x18000a023  mov     r9, rdi; unsigned int
0x18000a026  mov     rdx, r14; void *
0x18000a029  mov     rcx, rax; hProfile
0x18000a02c  call    ?GetIccProfileProperties@ProfileProperties@@YAJPEAXPEBGKPEAUCOLOR_PROFILE_PROPERTIES@@@Z; ProfileProperties::GetIccProfileProperties(void *,ushort const *,ulong,COLOR_PROFILE_PROPERTIES *)
0x18000a031  mov     ebx, eax
0x18000a033  jmp     loc_18000A264
0x18000a038  test    r13b, r13b
0x18000a03b  jnz     loc_18000A24E
0x18000a041  xor     edx, edx; pUnkOuter
0x18000a043  lea     rax, [rsp+310h+var_2BC+4]
0x18000a048  lea     r9, IID_IXMLDOMDocument2; riid
0x18000a04f  mov     qword ptr [rsp+310h+dwCreationDisposition], rax; ppv
0x18000a054  lea     rcx, CLSID_DOMDocument60; rclsid
0x18000a05b  lea     r8d, [rdx+1]; dwClsContext
0x18000a05f  call    cs:__imp_CoCreateInstance
0x18000a065  mov     ebx, eax
0x18000a067  test    eax, eax
0x18000a069  js      loc_18000A264
0x18000a06f  cmp     qword ptr [rsp+310h+var_2BC+4], rsi
0x18000a074  jnz     short loc_18000A080
0x18000a076  mov     ebx, 80004005h
0x18000a07b  jmp     loc_18000A264
0x18000a080  mov     eax, 8
0x18000a085  lea     rcx, [rbp+210h+FileName]; psz
0x18000a089  mov     word ptr [rbp+210h+pvarg], ax
0x18000a08d  call    cs:__imp_SysAllocString
0x18000a093  mov     qword ptr [rbp+210h+pvarg+8], rax
0x18000a097  test    rax, rax
0x18000a09a  jnz     short loc_18000A0A6
0x18000a09c  mov     ebx, 8007000Eh
0x18000a0a1  jmp     loc_18000A264
0x18000a0a6  mov     rcx, qword ptr [rsp+310h+var_2BC+4]
0x18000a0ab  lea     r8, [rsp+310h+var_2C0]
0x18000a0b0  movups  xmm0, xmmword ptr [rbp+210h+pvarg]
0x18000a0b4  lea     rdx, [rbp+210h+pCDMPProfile]
0x18000a0b8  mov     [rsp+310h+var_2C0], si
0x18000a0bd  movsd   xmm1, qword ptr [rbp+210h+pvarg+10h]
0x18000a0c2  mov     rax, [rcx]
0x18000a0c5  movaps  xmmword ptr [rbp+210h+pCDMPProfile.dwType], xmm0
0x18000a0c9  movsd   qword ptr [rbp+210h+pCDMPProfile.cbDataSize], xmm1
0x18000a0ce  mov     rax, [rax+1D0h]
0x18000a0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0da  mov     ebx, eax
0x18000a0dc  test    eax, eax
0x18000a0de  js      loc_18000A264
0x18000a0e4  cmp     eax, 1
0x18000a0e7  jz      loc_18000A255
0x18000a0ed  cmp     si, [rsp+310h+var_2C0]
0x18000a0f2  jz      loc_18000A255
0x18000a0f8  lea     r8, [rsp+310h+var_298]
0x18000a0fd  mov     ecx, 5; int
0x18000a102  lea     rdx, ?gc_apwszWcsNamespaces@@3QBQEBGB; unsigned __int16 **
0x18000a109  call    CreateCompatibilityMarkupProcessor
0x18000a10e  mov     r12, [rsp+310h+var_298]
0x18000a113  mov     ebx, eax
0x18000a115  test    eax, eax
0x18000a117  js      loc_18000A264
0x18000a11d  mov     rax, [r12]
0x18000a121  mov     rcx, r12
0x18000a124  mov     rdx, qword ptr [rsp+310h+var_2BC+4]
0x18000a129  mov     rax, [rax+8]
0x18000a12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a132  mov     ebx, eax
0x18000a134  test    eax, eax
0x18000a136  js      loc_18000A264
0x18000a13c  mov     rcx, qword ptr [rsp+310h+var_2BC+4]
0x18000a141  lea     rdx, [rsp+310h+var_2B0]
0x18000a146  mov     rax, [rcx]
0x18000a149  mov     rax, [rax+168h]
0x18000a150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a155  mov     ebx, eax
0x18000a157  test    eax, eax
0x18000a159  js      loc_18000A264
0x18000a15f  mov     rcx, [rsp+310h+var_2B0]; this
0x18000a164  lea     r8, [rsp+310h+var_2D0]; unsigned __int16 *
0x18000a169  lea     rdx, stru_1800882C0; struct IXMLDOMElement *
0x18000a170  mov     byte ptr [rsp+310h+var_2D0], sil
0x18000a175  call    ?IsElementInNamespace@ProfileProperties@@YAJPEAUIXMLDOMElement@@PEBGPEA_N@Z; ProfileProperties::IsElementInNamespace(IXMLDOMElement *,ushort const *,bool *)
0x18000a17a  mov     ebx, eax
0x18000a17c  test    eax, eax
0x18000a17e  js      loc_18000A264
0x18000a184  cmp     byte ptr [rsp+310h+var_2D0], sil
0x18000a189  jz      short loc_18000A1AC
0x18000a18b  mov     r9d, dword ptr [rsp+310h+var_2BC]; unsigned __int16 *
0x18000a190  mov     r8, r14; enum COLORPROFILETYPE
0x18000a193  mov     rdx, [rsp+310h+var_2B0]; struct IXMLDOMDocument2 *
0x18000a198  mov     rcx, qword ptr [rsp+310h+var_2BC+4]; this
0x18000a19d  mov     qword ptr [rsp+310h+dwCreationDisposition], rdi; unsigned int
0x18000a1a2  call    ?GetDmpProfileProperties@ProfileProperties@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBGKPEAUCOLOR_PROFILE_PROPERTIES@@@Z; ProfileProperties::GetDmpProfileProperties(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ulong,COLOR_PROFILE_PROPERTIES *)
0x18000a1a7  jmp     loc_18000A031
0x18000a1ac  mov     rcx, [rsp+310h+var_2B0]; this
0x18000a1b1  lea     r8, [rsp+310h+var_2D0]; unsigned __int16 *
0x18000a1b6  lea     rdx, stru_18008DEB0; struct IXMLDOMElement *
0x18000a1bd  mov     byte ptr [rsp+310h+var_2D0], sil
0x18000a1c2  call    ?IsElementInNamespace@ProfileProperties@@YAJPEAUIXMLDOMElement@@PEBGPEA_N@Z; ProfileProperties::IsElementInNamespace(IXMLDOMElement *,ushort const *,bool *)
0x18000a1c7  mov     ebx, eax
0x18000a1c9  test    eax, eax
0x18000a1cb  js      loc_18000A264
0x18000a1d1  cmp     byte ptr [rsp+310h+var_2D0], sil
0x18000a1d6  jz      short loc_18000A1FF
0x18000a1d8  mov     eax, dword ptr [rsp+310h+var_2BC]
0x18000a1dc  mov     r9, r14; struct IXMLDOMElement *
0x18000a1df  mov     r8, [rsp+310h+var_2B0]; struct IXMLDOMDocument2 *
0x18000a1e4  mov     rcx, r15; this
0x18000a1e7  mov     rdx, qword ptr [rsp+310h+var_2BC+4]; void *
0x18000a1ec  mov     qword ptr [rsp+310h+dwFlagsAndAttributes], rdi; unsigned int
0x18000a1f1  mov     [rsp+310h+dwCreationDisposition], eax; unsigned __int16 *
0x18000a1f5  call    ?GetCampProfileProperties@ProfileProperties@@YAJPEAXPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBGKPEAUCOLOR_PROFILE_PROPERTIES@@@Z; ProfileProperties::GetCampProfileProperties(void *,IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ulong,COLOR_PROFILE_PROPERTIES *)
0x18000a1fa  jmp     loc_18000A031
0x18000a1ff  mov     rcx, [rsp+310h+var_2B0]; this
0x18000a204  lea     r8, [rsp+310h+var_2D0]; unsigned __int16 *
0x18000a209  lea     rdx, stru_18008E320; struct IXMLDOMElement *
0x18000a210  mov     byte ptr [rsp+310h+var_2D0], sil
0x18000a215  call    ?IsElementInNamespace@ProfileProperties@@YAJPEAUIXMLDOMElement@@PEBGPEA_N@Z; ProfileProperties::IsElementInNamespace(IXMLDOMElement *,ushort const *,bool *)
0x18000a21a  mov     ebx, eax
0x18000a21c  test    eax, eax
0x18000a21e  js      short loc_18000A264
0x18000a220  cmp     byte ptr [rsp+310h+var_2D0], sil
0x18000a225  jz      short loc_18000A24E
0x18000a227  mov     eax, dword ptr [rsp+310h+var_2BC]
0x18000a22b  mov     r9, r14; struct IXMLDOMElement *
0x18000a22e  mov     r8, [rsp+310h+var_2B0]; struct IXMLDOMDocument2 *
0x18000a233  mov     rcx, r15; this
0x18000a236  mov     rdx, qword ptr [rsp+310h+var_2BC+4]; void *
0x18000a23b  mov     qword ptr [rsp+310h+dwFlagsAndAttributes], rdi; unsigned int
0x18000a240  mov     [rsp+310h+dwCreationDisposition], eax; unsigned __int16 *
0x18000a244  call    ?GetGmmpProfileProperties@ProfileProperties@@YAJPEAXPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBGKPEAUCOLOR_PROFILE_PROPERTIES@@@Z; ProfileProperties::GetGmmpProfileProperties(void *,IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ulong,COLOR_PROFILE_PROPERTIES *)
0x18000a249  jmp     loc_18000A031
0x18000a24e  mov     ebx, 800707DBh
0x18000a253  jmp     short loc_18000A264
0x18000a255  mov     ebx, 80040007h
0x18000a25a  jmp     short loc_18000A264
0x18000a25c  mov     ebx, 80070057h
0x18000a261  mov     rsi, r12
0x18000a264  lea     rcx, [rbp+210h+pvarg]; pvarg
0x18000a268  call    cs:__imp_VariantClear
0x18000a26e  mov     rcx, [rsp+310h+var_2B0]
0x18000a273  test    rcx, rcx
0x18000a276  jz      short loc_18000A284
0x18000a278  mov     rax, [rcx]
0x18000a27b  mov     rax, [rax+10h]
0x18000a27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a284  test    r12, r12
0x18000a287  jz      short loc_18000A29D
0x18000a289  mov     rax, [r12]
0x18000a28d  mov     edx, 1
0x18000a292  mov     rcx, r12
0x18000a295  mov     rax, [rax]
0x18000a298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a29d  mov     rcx, qword ptr [rsp+310h+var_2BC+4]
0x18000a2a2  test    rcx, rcx
0x18000a2a5  jz      short loc_18000A2B3
0x18000a2a7  mov     rax, [rcx]
0x18000a2aa  mov     rax, [rax+10h]
0x18000a2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2b3  test    rsi, rsi
0x18000a2b6  jz      short loc_18000A2C0
0x18000a2b8  mov     rcx, rsi; hProfile
0x18000a2bb  call    CloseColorProfile
0x18000a2c0  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000a2c4  jz      short loc_18000A2CF
0x18000a2c6  mov     rcx, r15; hObject
0x18000a2c9  call    cs:__imp_CloseHandle
0x18000a2cf  mov     rcx, r14; void *
0x18000a2d2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a2d7  mov     eax, ebx
0x18000a2d9  mov     rcx, [rbp+210h+var_40]
0x18000a2e0  xor     rcx, rsp; StackCookie
0x18000a2e3  call    __security_check_cookie
0x18000a2e8  mov     rbx, [rsp+310h+arg_8]
0x18000a2f0  add     rsp, 2E0h
0x18000a2f7  pop     r15
0x18000a2f9  pop     r14
0x18000a2fb  pop     r13
0x18000a2fd  pop     r12
0x18000a2ff  pop     rdi
  ... truncated ...
```
