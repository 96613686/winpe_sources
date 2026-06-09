# DRMGetServiceLocation

- ea: `0x18001c1c0`
- end: `0x18001c2ed`
- name: `DRMGetServiceLocation`
- size: `301`
- prototype: `HRESULT __stdcall(DRMHSESSION hClient, UINT uServiceType, UINT uServiceLocation, PWSTR wszIssuanceLicense, UINT *puServiceURLLength, PWSTR wszServiceURL)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180017acc`
- `0x18005aadc`

## callees

- `0x180001284`
- `0x18000420c`
- `0x1800046c8`
- `0x18001c1c0`
- `0x180026568`

## string_xrefs

- `0x18001c21c`: `DRM_SERVICE_TYPE_ACTIVATION`
- `0x18001c213`: `DRM_SERVICE_TYPE_CERTIFICATION`
- `0x18001c20a`: `DRM_SERVICE_TYPE_PUBLISHING`
- `0x18001c201`: `DRM_SERVICE_TYPE_CLIENTLICENSOR`
- `0x18001c238`: `DRM_SERVICE_LOCATION_INTERNET`
- `0x18001c22f`: `DRM_SERVICE_LOCATION_ENTERPRISE`
- `0x18001c23f`: `[msdrm]:+DRMGetServiceLocation uServiceType = %S,uServiceLocation = %S\n`
- `0x18001c2b8`: `[msdrm]: DRMGetServiceLocation Returned : ServiceUrl = %S\n`
- `0x18001c2d4`: `[msdrm]:-DRMGetServiceLocation HR=%x\n`

## pseudocode

```c
HRESULT __stdcall DRMGetServiceLocation(
        DRMHSESSION hClient,
        UINT uServiceType,
        UINT uServiceLocation,
        PWSTR wszIssuanceLicense,
        UINT *puServiceURLLength,
        PWSTR wszServiceURL)
{
  char v6; // bl
  const wchar_t *v7; // rdx
  const wchar_t *v10; // r8
  bool v11; // di
  unsigned int v12; // ebx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // eax
  char v16; // dl
  HRESULT ServiceLocation; // ebx

  v6 = uServiceType;
  v7 = 0;
  v10 = 0;
  v11 = (v6 & 0x10) != 0;
  v12 = v6 & 0xF;
  switch ( v12 )
  {
    case 1u:
      v7 = L"DRM_SERVICE_TYPE_ACTIVATION";
      break;
    case 2u:
      v7 = L"DRM_SERVICE_TYPE_CERTIFICATION";
      break;
    case 4u:
      v7 = L"DRM_SERVICE_TYPE_PUBLISHING";
      break;
    case 8u:
      v7 = L"DRM_SERVICE_TYPE_CLIENTLICENSOR";
      break;
  }
  if ( uServiceLocation == 1 )
  {
    v10 = L"DRM_SERVICE_LOCATION_INTERNET";
  }
  else if ( uServiceLocation == 2 )
  {
    v10 = L"DRM_SERVICE_LOCATION_ENTERPRISE";
  }
  _RTLTRACE("[msdrm]:+DRMGetServiceLocation uServiceType = %S,uServiceLocation = %S\n", v7, v10);
  if ( (!wszIssuanceLicense || (unsigned __int8)DRMIsValidStringT<unsigned short>(wszIssuanceLicense, 0, v13, v14))
    && puServiceURLLength
    && v12 <= 8
    && (v15 = 278, _bittest(&v15, v12))
    && uServiceLocation - 1 <= 1 )
  {
    v16 = v12 | 0x10;
    if ( !v11 )
      v16 = v12;
    ServiceLocation = GetServiceLocation(
                        (__int64)puServiceURLLength,
                        v16,
                        uServiceLocation,
                        wszIssuanceLicense,
                        puServiceURLLength,
                        wszServiceURL);
    if ( ServiceLocation >= 0 && wszServiceURL )
      _RTLTRACE("[msdrm]: DRMGetServiceLocation Returned : ServiceUrl = %S\n", wszServiceURL);
  }
  else
  {
    ServiceLocation = -2147024809;
  }
  operator delete(0);
  _RTLTRACE("[msdrm]:-DRMGetServiceLocation HR=%x\n", ServiceLocation);
  return ServiceLocation;
}

```

## disassembly

```asm
0x18001c1c0  push    rbx
0x18001c1c2  push    rbp
0x18001c1c3  push    rsi
0x18001c1c4  push    rdi
0x18001c1c5  push    r14
0x18001c1c7  sub     rsp, 30h
0x18001c1cb  xor     al, al
0x18001c1cd  mov     ebx, edx
0x18001c1cf  xor     edx, edx
0x18001c1d1  movzx   edi, al
0x18001c1d4  mov     esi, r8d
0x18001c1d7  mov     rbp, r9
0x18001c1da  xor     r8d, r8d
0x18001c1dd  test    bl, 10h
0x18001c1e0  lea     r14d, [rdx+1]
0x18001c1e4  cmovnz  edi, r14d
0x18001c1e8  and     ebx, 0Fh
0x18001c1eb  mov     eax, ebx
0x18001c1ed  sub     eax, r14d
0x18001c1f0  jz      short loc_18001C21C
0x18001c1f2  sub     eax, r14d
0x18001c1f5  jz      short loc_18001C213
0x18001c1f7  sub     eax, 2
0x18001c1fa  jz      short loc_18001C20A
0x18001c1fc  cmp     eax, 4
0x18001c1ff  jnz     short loc_18001C223
0x18001c201  lea     rdx, aDrmServiceType_2; "DRM_SERVICE_TYPE_CLIENTLICENSOR"
0x18001c208  jmp     short loc_18001C223
0x18001c20a  lea     rdx, aDrmServiceType; "DRM_SERVICE_TYPE_PUBLISHING"
0x18001c211  jmp     short loc_18001C223
0x18001c213  lea     rdx, aDrmServiceType_1; "DRM_SERVICE_TYPE_CERTIFICATION"
0x18001c21a  jmp     short loc_18001C223
0x18001c21c  lea     rdx, aDrmServiceType_0; "DRM_SERVICE_TYPE_ACTIVATION"
0x18001c223  mov     eax, esi
0x18001c225  sub     eax, r14d
0x18001c228  jz      short loc_18001C238
0x18001c22a  cmp     eax, r14d
0x18001c22d  jnz     short loc_18001C23F
0x18001c22f  lea     r8, aDrmServiceLoca; "DRM_SERVICE_LOCATION_ENTERPRISE"
0x18001c236  jmp     short loc_18001C23F
0x18001c238  lea     r8, aDrmServiceLoca_0; "DRM_SERVICE_LOCATION_INTERNET"
0x18001c23f  lea     rcx, aMsdrmDrmgetser_0; "[msdrm]:+DRMGetServiceLocation uService"...
0x18001c246  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001c24b  test    rbp, rbp
0x18001c24e  jz      short loc_18001C25E
0x18001c250  xor     edx, edx
0x18001c252  mov     rcx, rbp
0x18001c255  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x18001c25a  test    al, al
0x18001c25c  jz      short loc_18001C2C6
0x18001c25e  mov     rcx, [rsp+58h+puServiceURLLength]; unsigned int
0x18001c266  test    rcx, rcx
0x18001c269  jz      short loc_18001C2C6
0x18001c26b  cmp     ebx, 8
0x18001c26e  ja      short loc_18001C2C6
0x18001c270  mov     eax, 116h
0x18001c275  bt      eax, ebx
0x18001c278  jnb     short loc_18001C2C6
0x18001c27a  lea     eax, [rsi-1]
0x18001c27d  cmp     eax, r14d
0x18001c280  ja      short loc_18001C2C6
0x18001c282  mov     edx, ebx
0x18001c284  mov     r9, rbp; unsigned __int16 *
0x18001c287  or      edx, 10h
0x18001c28a  mov     r8d, esi; unsigned int
0x18001c28d  test    dil, dil
0x18001c290  mov     rdi, [rsp+58h+wszServiceURL]
0x18001c298  mov     [rsp+58h+var_30], rdi; unsigned __int16 *
0x18001c29d  cmovz   edx, ebx; unsigned int
0x18001c2a0  mov     [rsp+58h+var_38], rcx; unsigned int *
0x18001c2a5  call    ?GetServiceLocation@@YAJKIIPEAGPEAI0@Z; GetServiceLocation(ulong,uint,uint,ushort *,uint *,ushort *)
0x18001c2aa  mov     ebx, eax
0x18001c2ac  test    eax, eax
0x18001c2ae  js      short loc_18001C2CB
0x18001c2b0  test    rdi, rdi
0x18001c2b3  jz      short loc_18001C2CB
0x18001c2b5  mov     rdx, rdi
0x18001c2b8  lea     rcx, aMsdrmDrmgetser_1; "[msdrm]: DRMGetServiceLocation Returned"...
0x18001c2bf  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001c2c4  jmp     short loc_18001C2CB
0x18001c2c6  mov     ebx, 80070057h
0x18001c2cb  xor     ecx, ecx; Block
0x18001c2cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c2d2  mov     edx, ebx
0x18001c2d4  lea     rcx, aMsdrmDrmgetser; "[msdrm]:-DRMGetServiceLocation HR=%x\n"
0x18001c2db  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001c2e0  mov     eax, ebx
0x18001c2e2  add     rsp, 30h
0x18001c2e6  pop     r14
0x18001c2e8  pop     rdi
0x18001c2e9  pop     rsi
0x18001c2ea  pop     rbp
0x18001c2eb  pop     rbx
0x18001c2ec  retn
```
