# CKsOutputPin2::SetMediaType(CMediaType const *)

- ea: `0x1001b660`
- end: `0x1001b855`
- name: `?SetMediaType@CKsOutputPin2@@UAEJPBVCMediaType@@@Z`
- size: `501`
- prototype: `int __thiscall(CKsOutputPin2 *__hidden this, const struct CMediaType *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1001a001`
- `0x1001a052`
- `0x1001a1c4`
- `0x1001b4c6`
- `0x1001b660`
- `0x1001e1f8`
- `0x1001ec14`
- `0x1001f6ea`
- `0x1001f846`
- `0x10021aad`
- `0x1002d510`
- `0x100302a7`
- `0x10031bae`
- `0x1003aba0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1001b793`
- `ole32!CoTaskMemAlloc` at `0x1001b793`
- `ole32!CoTaskMemFree` at `0x1001b780`
- `ole32!CoTaskMemFree` at `0x1001b780`

## pseudocode

```c
int __thiscall CKsOutputPin2::SetMediaType(CKsOutputPin2 *this, struct CMediaType *a2)
{
  struct CMediaType *v2; // esi
  int MediaTypeArrays; // edi
  int v5; // ecx
  int v6; // ecx
  void *v7; // esi
  struct IKsDataTypeHandler **v9; // [esp+0h] [ebp-30h]
  void **v10; // [esp+0h] [ebp-30h]
  union KSDATAFORMAT *v11; // [esp+0h] [ebp-30h]
  struct IUnknown **v12; // [esp+4h] [ebp-2Ch]
  struct CMediaType *v13; // [esp+4h] [ebp-2Ch]
  struct _AMMediaType *v14; // [esp+4h] [ebp-2Ch]
  const struct CMediaType *v15; // [esp+4h] [ebp-2Ch]
  LPVOID pv; // [esp+Ch] [ebp-24h] BYREF
  struct CMediaType *v17; // [esp+10h] [ebp-20h]
  unsigned int v18; // [esp+14h] [ebp-1Ch] BYREF
  _BYTE v19[20]; // [esp+18h] [ebp-18h] BYREF

  v2 = a2;
  MediaTypeArrays = 0;
  v17 = a2;
  pv = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_s(
      0x18u,
      &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (int)"CKsOutputPin2::SetMediaType");
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_DirectShow_KernelSupport_Context,
      SetMediaType_Enter,
      this,
      1,
      v19);
  if ( *((_DWORD *)this + 94) )
  {
    v5 = *((_DWORD *)this + 95);
    *((_DWORD *)this + 94) = 0;
    if ( v5 )
    {
      *((_DWORD *)this + 95) = 0;
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v5 + 8))(*(_DWORD *)(*(_DWORD *)v5 + 8), v5);
      v2 = v17;
    }
  }
  OpenDataHandler(
    this != 0 ? (IUnknown *)this + 3 : 0,
    (int)v2,
    (const struct CMediaType *)((char *)this + 376),
    (LPVOID *)this + 95,
    v9,
    v12);
  if ( *((_DWORD *)this + 202) || (MediaTypeArrays = CKsOutputPin2::CreateMediaTypeArrays(this), MediaTypeArrays >= 0) )
  {
    if ( *((_DWORD *)this + 192) )
    {
      MediaTypeArrays = InitializeDataFormat(
                          (const struct CMediaType *)&pv,
                          (unsigned int)&v18,
                          v10,
                          &v13->majortype.Data1);
      if ( MediaTypeArrays < 0 )
        goto LABEL_26;
      v7 = pv;
      MediaTypeArrays = CKsOutputPin2::SetPluginMediaType(this, (union KSDATAFORMAT *)pv, 0);
      if ( MediaTypeArrays < 0 )
      {
        if ( v7 )
          CoTaskMemFree(v7);
        goto LABEL_26;
      }
      if ( !*((_DWORD *)this + 89) )
        goto LABEL_25;
      if ( CoTaskMemAlloc(0x48u) )
      {
        MediaTypeArrays = ConvertKsMediaTypeToAmMediaType(v11, v14);
        if ( MediaTypeArrays >= 0 )
          MediaTypeArrays = SetMediaType(v11, v15);
      }
      else
      {
        MediaTypeArrays = -2147024882;
      }
      DeleteMediaType((struct _AMMediaType *)v11);
    }
    else
    {
      v6 = *((_DWORD *)this + 89);
      if ( v6 )
      {
        MediaTypeArrays = SetMediaType(v10, v13);
        if ( MediaTypeArrays < 0 )
          goto LABEL_29;
      }
    }
    if ( MediaTypeArrays >= 0 )
LABEL_25:
      MediaTypeArrays = CBasePin::SetMediaType((CBasePin *)this, v17);
LABEL_26:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_sd(0x19u, *((_QWORD *)WPP_GLOBAL_Control + 2), (int)"CKsOutputPin2::SetMediaType", MediaTypeArrays);
  }
LABEL_29:
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_DirectShow_KernelSupport_Context,
      SetMediaType_Exit,
      v6,
      1,
      v19);
  return MediaTypeArrays;
}

```

## disassembly

```asm
0x1001b660  mov     edi, edi
0x1001b662  push    ebp
0x1001b663  mov     ebp, esp
0x1001b665  and     esp, 0FFFFFFF8h
0x1001b668  sub     esp, 24h
0x1001b66b  mov     eax, ___security_cookie
0x1001b670  xor     eax, esp
0x1001b672  mov     [esp+24h+var_4], eax
0x1001b676  push    ebx
0x1001b677  push    esi; struct CMediaType *
0x1001b678  mov     esi, [ebp+arg_0]
0x1001b67b  mov     ebx, ecx
0x1001b67d  push    edi; void *
0x1001b67e  xor     edi, edi
0x1001b680  mov     [esp+30h+var_20], esi
0x1001b684  mov     [esp+30h+pv], edi
0x1001b688  mov     eax, _WPP_GLOBAL_Control
0x1001b68d  cmp     eax, offset _WPP_GLOBAL_Control
0x1001b692  jz      short loc_1001B6B2
0x1001b694  cmp     byte ptr [eax+19h], 2
0x1001b698  jb      short loc_1001B6B2
0x1001b69a  push    offset aCksoutputpin2S; "CKsOutputPin2::SetMediaType"
0x1001b69f  push    dword ptr [eax+14h]
0x1001b6a2  mov     edx, offset _WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids; MessageGuid
0x1001b6a7  push    dword ptr [eax+10h]; LoggerHandle
0x1001b6aa  push    18h
0x1001b6ac  pop     ecx; MessageNumber
0x1001b6ad  call    _WPP_SF_s@20; WPP_SF_s(x,x,x,x,x)
0x1001b6b2  test    _Microsoft_Windows_DirectShow_KernelSupportEnableBits, 1
0x1001b6b9  jz      short loc_1001B6D2
0x1001b6bb  lea     eax, [esp+30h+var_18]
0x1001b6bf  mov     edx, offset _SetMediaType_Enter
0x1001b6c4  push    eax
0x1001b6c5  push    1
0x1001b6c7  push    ecx
0x1001b6c8  mov     ecx, offset _Microsoft_Windows_DirectShow_KernelSupport_Context
0x1001b6cd  call    _McGenEventWrite_EventWriteTransfer@20; McGenEventWrite_EventWriteTransfer(x,x,x,x,x)
0x1001b6d2  lea     eax, [ebx+178h]
0x1001b6d8  xor     edx, edx
0x1001b6da  cmp     [eax], edx
0x1001b6dc  jz      short loc_1001B704
0x1001b6de  mov     ecx, [ebx+17Ch]
0x1001b6e4  mov     [eax], edx
0x1001b6e6  test    ecx, ecx
0x1001b6e8  jz      short loc_1001B704
0x1001b6ea  mov     [ebx+17Ch], edx
0x1001b6f0  mov     eax, [ecx]
0x1001b6f2  push    ecx
0x1001b6f3  mov     esi, [eax+8]
0x1001b6f6  mov     ecx, esi; this
0x1001b6f8  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001b6fe  call    esi
0x1001b700  mov     esi, [esp+30h+var_20]
0x1001b704  lea     eax, [ebx+17Ch]
0x1001b70a  mov     edx, ebx
0x1001b70c  push    eax; ppv
0x1001b70d  neg     edx
0x1001b70f  lea     eax, [ebx+178h]
0x1001b715  push    eax; struct CMediaType *
0x1001b716  lea     eax, [ebx+0Ch]
0x1001b719  sbb     edx, edx
0x1001b71b  and     edx, eax
0x1001b71d  mov     ecx, esi
0x1001b71f  call    ?OpenDataHandler@@YGXPBVCMediaType@@PAUIUnknown@@PAPAUIKsDataTypeHandler@@PAPAU2@@Z; OpenDataHandler(CMediaType const *,IUnknown *,IKsDataTypeHandler * *,IUnknown * *)
0x1001b724  cmp     [ebx+328h], edi
0x1001b72a  jnz     short loc_1001B73D
0x1001b72c  mov     ecx, ebx; this
0x1001b72e  call    ?CreateMediaTypeArrays@CKsOutputPin2@@QAEJXZ; CKsOutputPin2::CreateMediaTypeArrays(void)
0x1001b733  mov     edi, eax
0x1001b735  test    edi, edi
0x1001b737  js      loc_1001B81F
0x1001b73d  cmp     dword ptr [ebx+300h], 0
0x1001b744  jz      loc_1001B7D1
0x1001b74a  lea     eax, [esp+30h+var_1C]
0x1001b74e  xor     edx, edx
0x1001b750  push    eax; unsigned int
0x1001b751  lea     eax, [esp+34h+pv]
0x1001b755  mov     ecx, esi
0x1001b757  push    eax; struct CMediaType *
0x1001b758  call    ?InitializeDataFormat@@YGJPBVCMediaType@@KPAPAXPAK@Z; InitializeDataFormat(CMediaType const *,ulong,void * *,ulong *)
0x1001b75d  mov     edi, eax
0x1001b75f  test    edi, edi
0x1001b761  js      loc_1001B7F9
0x1001b767  mov     esi, [esp+30h+pv]
0x1001b76b  mov     ecx, ebx; this
0x1001b76d  push    0; int
0x1001b76f  push    esi; union KSDATAFORMAT *
0x1001b770  call    ?SetPluginMediaType@CKsOutputPin2@@QAEJPATKSDATAFORMAT@@H@Z; CKsOutputPin2::SetPluginMediaType(KSDATAFORMAT *,int)
0x1001b775  mov     edi, eax
0x1001b777  test    edi, edi
0x1001b779  jns     short loc_1001B788
0x1001b77b  test    esi, esi
0x1001b77d  jz      short loc_1001B7F9
0x1001b77f  push    esi; pv
0x1001b780  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001b786  jmp     short loc_1001B7F9
0x1001b788  cmp     dword ptr [ebx+164h], 0
0x1001b78f  jz      short loc_1001B7EC
0x1001b791  push    48h ; 'H'; cb
0x1001b793  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1001b799  mov     esi, eax
0x1001b79b  test    esi, esi
0x1001b79d  jnz     short loc_1001B7A6
0x1001b79f  mov     edi, 8007000Eh
0x1001b7a4  jmp     short loc_1001B7C8
0x1001b7a6  mov     ecx, [ebx+330h]
0x1001b7ac  mov     edx, esi
0x1001b7ae  call    ?ConvertKsMediaTypeToAmMediaType@@YGJPATKSDATAFORMAT@@PAU_AMMediaType@@@Z; ConvertKsMediaTypeToAmMediaType(KSDATAFORMAT *,_AMMediaType *)
0x1001b7b3  mov     edi, eax
0x1001b7b5  test    edi, edi
0x1001b7b7  js      short loc_1001B7C8
0x1001b7b9  mov     ecx, [ebx+164h]
0x1001b7bf  mov     edx, esi
0x1001b7c1  call    ?SetMediaType@@YGJPAXPBVCMediaType@@@Z; SetMediaType(void *,CMediaType const *)
0x1001b7c6  mov     edi, eax
0x1001b7c8  mov     ecx, esi
0x1001b7ca  call    ?DeleteMediaType@@YGXPAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x1001b7cf  jmp     short loc_1001B7E8
0x1001b7d1  mov     ecx, [ebx+164h]
0x1001b7d7  test    ecx, ecx
0x1001b7d9  jz      short loc_1001B7E8
0x1001b7db  mov     edx, esi
0x1001b7dd  call    ?SetMediaType@@YGJPAXPBVCMediaType@@@Z; SetMediaType(void *,CMediaType const *)
0x1001b7e2  mov     edi, eax
0x1001b7e4  test    edi, edi
0x1001b7e6  js      short loc_1001B81F
0x1001b7e8  test    edi, edi
0x1001b7ea  js      short loc_1001B7F9
0x1001b7ec  push    [esp+30h+var_20]; struct CMediaType *
0x1001b7f0  mov     ecx, ebx; this
0x1001b7f2  call    ?SetMediaType@CBasePin@@UAEJPBVCMediaType@@@Z; CBasePin::SetMediaType(CMediaType const *)
0x1001b7f7  mov     edi, eax
0x1001b7f9  mov     eax, _WPP_GLOBAL_Control
0x1001b7fe  cmp     eax, offset _WPP_GLOBAL_Control
0x1001b803  jz      short loc_1001B81F
0x1001b805  cmp     byte ptr [eax+19h], 2
0x1001b809  jb      short loc_1001B81F
0x1001b80b  push    edi; char
0x1001b80c  push    offset aCksoutputpin2S; "CKsOutputPin2::SetMediaType"
0x1001b811  push    dword ptr [eax+14h]
0x1001b814  push    dword ptr [eax+10h]; LoggerHandle
0x1001b817  push    19h
0x1001b819  pop     ecx; MessageNumber
0x1001b81a  call    _WPP_SF_sd@24; WPP_SF_sd(x,x,x,x,x,x)
0x1001b81f  test    _Microsoft_Windows_DirectShow_KernelSupportEnableBits, 1
0x1001b826  jz      short loc_1001B83F
0x1001b828  lea     eax, [esp+30h+var_18]
0x1001b82c  mov     edx, offset _SetMediaType_Exit
0x1001b831  push    eax
0x1001b832  push    1
0x1001b834  push    ecx
0x1001b835  mov     ecx, offset _Microsoft_Windows_DirectShow_KernelSupport_Context
0x1001b83a  call    _McGenEventWrite_EventWriteTransfer@20; McGenEventWrite_EventWriteTransfer(x,x,x,x,x)
0x1001b83f  mov     ecx, [esp+30h+var_4]
0x1001b843  mov     eax, edi
0x1001b845  pop     edi
0x1001b846  pop     esi
0x1001b847  pop     ebx
0x1001b848  xor     ecx, esp; StackCookie
0x1001b84a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001b84f  mov     esp, ebp
0x1001b851  pop     ebp
0x1001b852  retn    4
```
