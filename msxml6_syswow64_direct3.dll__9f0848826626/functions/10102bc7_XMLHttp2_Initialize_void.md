# XMLHttp2::Initialize(void)

- ea: `0x10102bc7`
- end: `0x10102ced`
- name: `?Initialize@XMLHttp2@@AAGJXZ`
- size: `294`
- prototype: `HRESULT __stdcall(XMLHttp2 *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x10103d7e`

## callees

- `0x10067b20`
- `0x10102184`
- `0x10102bc7`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10102cba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10102cba`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x10102c11`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x10102c11`

## pseudocode

```c
HRESULT __cdecl XMLHttp2::Initialize(XMLHttp2 *this)
{
  int v1; // ecx
  int v2; // esi
  int v3; // ebx
  HRESULT ApartmentType; // edi
  XMLHttp *v5; // ecx
  _APTTYPEQUALIFIER AptQualifier; // [esp+Ch] [ebp-Ch] BYREF
  _APTTYPE AptType; // [esp+10h] [ebp-8h] BYREF
  XMLHttp *pXMLHttp; // [esp+14h] [ebp-4h] BYREF

  v2 = v1;
  pXMLHttp = 0;
  AptType = APTTYPE_CURRENT;
  v3 = 0;
  AptQualifier = APTTYPEQUALIFIER_NONE;
  if ( (byte_10185760[0] & 2) != 0 )
    WPP_SF_q(0x401u, 0x83u, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, v1);
  ApartmentType = CoGetApartmentType(&AptType, &AptQualifier);
  if ( ApartmentType < 0 )
    goto LABEL_9;
  if ( AptType == APTTYPE_STA )
  {
LABEL_22:
    *(_DWORD *)(v2 + 28) = GetCurrentThreadId();
    goto LABEL_23;
  }
  if ( AptType == APTTYPE_MTA )
    goto LABEL_21;
  if ( AptType != APTTYPE_NA )
  {
    if ( AptType != APTTYPE_MAINSTA )
    {
LABEL_8:
      ApartmentType = -2147417842;
LABEL_9:
      v5 = pXMLHttp;
      goto CleanUp_362;
    }
    goto LABEL_22;
  }
  switch ( AptQualifier )
  {
    case APTTYPEQUALIFIER_IMPLICIT_MTA:
    case APTTYPEQUALIFIER_NA_ON_MTA:
      goto LABEL_21;
    case APTTYPEQUALIFIER_NA_ON_STA:
      goto LABEL_23;
    case APTTYPEQUALIFIER_NA_ON_IMPLICIT_MTA:
LABEL_21:
      v3 = 1;
      goto LABEL_23;
  }
  if ( (unsigned int)(AptQualifier - 5) >= 2 )
    goto LABEL_8;
LABEL_23:
  ApartmentType = XMLHttp::CreateInstance(v3, 1, 0, &pXMLHttp);
  if ( ApartmentType < 0 )
    goto LABEL_9;
  v5 = 0;
  *(_DWORD *)(v2 + 24) = pXMLHttp;
  pXMLHttp = 0;
CleanUp_362:
  if ( v5 )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IDispatch *), XMLHttp *))v5->Release)(v5->Release, v5);
    pXMLHttp = 0;
  }
  if ( (byte_10185760[16 * (ApartmentType >> 31)] & 2) != 0 )
    WPP_SF_q(
      (((unsigned __int16)(ApartmentType >> 31) + 2) << 9) | 1,
      0x84u,
      WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids,
      ApartmentType);
  return ApartmentType;
}

```

## disassembly

```asm
0x10102bc7  mov     edi, edi
0x10102bc9  push    ebp
0x10102bca  mov     ebp, esp
0x10102bcc  sub     esp, 0Ch
0x10102bcf  push    ebx
0x10102bd0  push    esi
0x10102bd1  push    edi
0x10102bd2  mov     esi, this
0x10102bd4  mov     [ebp+pXMLHttp], 0
0x10102bdb  mov     [ebp+AptType], 0FFFFFFFFh
0x10102be2  xor     ebx, ebx
0x10102be4  mov     [ebp+AptQualifier], 0
0x10102beb  test    byte_10185760, 2; __annotation("TMF:",
0x10102bf2  jz      short loc_10102C09
0x10102bf4  push    esi; _a1
0x10102bf5  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x10102bfa  mov     edx, 83h; id
0x10102bff  mov     this, 401h; LevelKeyword
0x10102c04  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10102c09  lea     eax, [ebp+AptQualifier]
0x10102c0c  push    eax; pAptQualifier
0x10102c0d  lea     eax, [ebp+AptType]
0x10102c10  push    eax; pAptType
0x10102c11  call    ds:__imp__CoGetApartmentType@8; CoGetApartmentType(x,x)
0x10102c17  mov     edi, eax
0x10102c19  test    edi, edi
0x10102c1b  js      short loc_10102C41
0x10102c1d  mov     eax, [ebp+AptType]
0x10102c20  sub     eax, 0
0x10102c23  jz      loc_10102CBA
0x10102c29  sub     eax, 1
0x10102c2c  jz      loc_10102CB5
0x10102c32  sub     eax, 1
0x10102c35  jz      short loc_10102C92
0x10102c37  sub     eax, 1
0x10102c3a  jz      short loc_10102CBA
0x10102c3c  mov     edi, 8001010Eh
0x10102c41  mov     this, [ebp+pXMLHttp]
0x10102c44  test    this, this
0x10102c46  jz      short loc_10102C5F
0x10102c48  mov     eax, [this]
0x10102c4a  push    this
0x10102c4b  mov     esi, [eax+8]
0x10102c4e  mov     this, esi; this
0x10102c50  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10102c56  call    esi
0x10102c58  mov     [ebp+pXMLHttp], 0
0x10102c5f  mov     this, edi; __annotation("TMF:",
0x10102c61  sar     this, 1Fh
0x10102c64  mov     eax, this
0x10102c66  shl     eax, 4
0x10102c69  test    byte_10185760[eax], 2
0x10102c70  jz      short loc_10102C8B
0x10102c72  add     this, 2
0x10102c75  mov     edx, 84h; id
0x10102c7a  push    edi; _a1
0x10102c7b  shl     this, 9
0x10102c7e  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x10102c83  or      this, 1; LevelKeyword
0x10102c86  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10102c8b  mov     eax, edi
0x10102c8d  pop     edi
0x10102c8e  pop     esi
0x10102c8f  pop     ebx
0x10102c90  leave
0x10102c91  retn
0x10102c92  mov     eax, [ebp+AptQualifier]
0x10102c95  sub     eax, 1
0x10102c98  jz      short loc_10102CB5
0x10102c9a  sub     eax, 1
0x10102c9d  jz      short loc_10102CB5
0x10102c9f  sub     eax, 1
0x10102ca2  jz      short loc_10102CC3
0x10102ca4  sub     eax, 1
0x10102ca7  jz      short loc_10102CB5
0x10102ca9  sub     eax, 1
0x10102cac  jz      short loc_10102CC3
0x10102cae  sub     eax, 1
0x10102cb1  jz      short loc_10102CC3
0x10102cb3  jmp     short loc_10102C3C
0x10102cb5  xor     ebx, ebx
0x10102cb7  inc     ebx
0x10102cb8  jmp     short loc_10102CC3
0x10102cba  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10102cc0  mov     [esi+1Ch], eax
0x10102cc3  lea     eax, [ebp+pXMLHttp]
0x10102cc6  xor     edx, edx
0x10102cc8  push    eax; ppXmlHttp
0x10102cc9  push    0; fServer
0x10102ccb  inc     edx; fDisableLegacyFeatures
0x10102ccc  mov     this, ebx; fMta
0x10102cce  call    ?CreateInstance@XMLHttp@@SGJHHHPAPAV1@@Z; XMLHttp::CreateInstance(int,int,int,XMLHttp * *)
0x10102cd3  mov     edi, eax
0x10102cd5  test    edi, edi
0x10102cd7  js      loc_10102C41
0x10102cdd  mov     eax, [ebp+pXMLHttp]
0x10102ce0  xor     this, this
0x10102ce2  mov     [esi+18h], eax
0x10102ce5  mov     [ebp+pXMLHttp], this
0x10102ce8  jmp     CleanUp_362
```
