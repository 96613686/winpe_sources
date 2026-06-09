# XMLHttp2::Initialize(void)

- ea: `0x10102ab7`
- end: `0x10102bdd`
- name: `?Initialize@XMLHttp2@@AAGJXZ`
- size: `294`
- prototype: `HRESULT __stdcall(XMLHttp2 *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x10103c5e`

## callees

- `0x10067bc0`
- `0x10102074`
- `0x10102ab7`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10102baa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10102baa`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x10102b01`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x10102b01`

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
  if ( (byte_101857A0[0] & 2) != 0 )
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
  if ( (byte_101857A0[16 * (ApartmentType >> 31)] & 2) != 0 )
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
0x10102ab7  mov     edi, edi
0x10102ab9  push    ebp
0x10102aba  mov     ebp, esp
0x10102abc  sub     esp, 0Ch
0x10102abf  push    ebx
0x10102ac0  push    esi
0x10102ac1  push    edi
0x10102ac2  mov     esi, this
0x10102ac4  mov     [ebp+pXMLHttp], 0
0x10102acb  mov     [ebp+AptType], 0FFFFFFFFh
0x10102ad2  xor     ebx, ebx
0x10102ad4  mov     [ebp+AptQualifier], 0
0x10102adb  test    byte_101857A0, 2; __annotation("TMF:",
0x10102ae2  jz      short loc_10102AF9
0x10102ae4  push    esi; _a1
0x10102ae5  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x10102aea  mov     edx, 83h; id
0x10102aef  mov     this, 401h; LevelKeyword
0x10102af4  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10102af9  lea     eax, [ebp+AptQualifier]
0x10102afc  push    eax; pAptQualifier
0x10102afd  lea     eax, [ebp+AptType]
0x10102b00  push    eax; pAptType
0x10102b01  call    ds:__imp__CoGetApartmentType@8; CoGetApartmentType(x,x)
0x10102b07  mov     edi, eax
0x10102b09  test    edi, edi
0x10102b0b  js      short loc_10102B31
0x10102b0d  mov     eax, [ebp+AptType]
0x10102b10  sub     eax, 0
0x10102b13  jz      loc_10102BAA
0x10102b19  sub     eax, 1
0x10102b1c  jz      loc_10102BA5
0x10102b22  sub     eax, 1
0x10102b25  jz      short loc_10102B82
0x10102b27  sub     eax, 1
0x10102b2a  jz      short loc_10102BAA
0x10102b2c  mov     edi, 8001010Eh
0x10102b31  mov     this, [ebp+pXMLHttp]
0x10102b34  test    this, this
0x10102b36  jz      short loc_10102B4F
0x10102b38  mov     eax, [this]
0x10102b3a  push    this
0x10102b3b  mov     esi, [eax+8]
0x10102b3e  mov     this, esi; this
0x10102b40  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10102b46  call    esi
0x10102b48  mov     [ebp+pXMLHttp], 0
0x10102b4f  mov     this, edi; __annotation("TMF:",
0x10102b51  sar     this, 1Fh
0x10102b54  mov     eax, this
0x10102b56  shl     eax, 4
0x10102b59  test    byte_101857A0[eax], 2
0x10102b60  jz      short loc_10102B7B
0x10102b62  add     this, 2
0x10102b65  mov     edx, 84h; id
0x10102b6a  push    edi; _a1
0x10102b6b  shl     this, 9
0x10102b6e  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x10102b73  or      this, 1; LevelKeyword
0x10102b76  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10102b7b  mov     eax, edi
0x10102b7d  pop     edi
0x10102b7e  pop     esi
0x10102b7f  pop     ebx
0x10102b80  leave
0x10102b81  retn
0x10102b82  mov     eax, [ebp+AptQualifier]
0x10102b85  sub     eax, 1
0x10102b88  jz      short loc_10102BA5
0x10102b8a  sub     eax, 1
0x10102b8d  jz      short loc_10102BA5
0x10102b8f  sub     eax, 1
0x10102b92  jz      short loc_10102BB3
0x10102b94  sub     eax, 1
0x10102b97  jz      short loc_10102BA5
0x10102b99  sub     eax, 1
0x10102b9c  jz      short loc_10102BB3
0x10102b9e  sub     eax, 1
0x10102ba1  jz      short loc_10102BB3
0x10102ba3  jmp     short loc_10102B2C
0x10102ba5  xor     ebx, ebx
0x10102ba7  inc     ebx
0x10102ba8  jmp     short loc_10102BB3
0x10102baa  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10102bb0  mov     [esi+1Ch], eax
0x10102bb3  lea     eax, [ebp+pXMLHttp]
0x10102bb6  xor     edx, edx
0x10102bb8  push    eax; ppXmlHttp
0x10102bb9  push    0; fServer
0x10102bbb  inc     edx; fDisableLegacyFeatures
0x10102bbc  mov     this, ebx; fMta
0x10102bbe  call    ?CreateInstance@XMLHttp@@SGJHHHPAPAV1@@Z; XMLHttp::CreateInstance(int,int,int,XMLHttp * *)
0x10102bc3  mov     edi, eax
0x10102bc5  test    edi, edi
0x10102bc7  js      loc_10102B31
0x10102bcd  mov     eax, [ebp+pXMLHttp]
0x10102bd0  xor     this, this
0x10102bd2  mov     [esi+18h], eax
0x10102bd5  mov     [ebp+pXMLHttp], this
0x10102bd8  jmp     CleanUp_362
```
