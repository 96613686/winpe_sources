# URLMONRequest::GetSerializedClientCertContext(uchar * *,ulong *)

- ea: `0x10134c90`
- end: `0x10134dd9`
- name: `?GetSerializedClientCertContext@URLMONRequest@@MAGJPAPAEPAK@Z`
- size: `329`
- prototype: `HRESULT __stdcall(URLMONRequest *this, unsigned __int8 **ppbClientCert, unsigned int *pcbClientCert)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x10067b20`
- `0x10134c90`
- `0x10137807`
- `0x101712a4`
- `0x10180006`
- `0x10180652`
- `0x101806b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10134d15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10134d15`

## pseudocode

```c
HRESULT __stdcall URLMONRequest::GetSerializedClientCertContext(
        URLMONRequest *this,
        unsigned __int8 **ppbClientCert,
        unsigned int *pcbClientCert)
{
  int v3; // edi
  unsigned __int8 *v4; // eax
  unsigned __int8 *v6; // [esp+Ch] [ebp-4h]

  if ( (byte_10185760[0] & 8) != 0 )
    WPP_SF_qdq(0x403u, 0xB1u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, this, ppbClientCert, pcbClientCert);
  this->Lock(this);
  v3 = URLMONRequest::_OnClientCert(this);
  if ( v3 < 0 )
    goto LABEL_14;
  if ( !ppbClientCert || (*ppbClientCert = 0, !pcbClientCert) )
  {
    v3 = -2147467261;
LABEL_14:
    this->Unlock(this);
    goto LABEL_15;
  }
  *pcbClientCert = 0;
  if ( !this->_cbClientCert || !this->_pbClientCert )
  {
    v3 = -2147467259;
    goto LABEL_14;
  }
  v4 = (unsigned __int8 *)CoTaskMemAlloc(this->_cbClientCert);
  v6 = v4;
  if ( !v4 )
  {
    v3 = -2147024882;
    goto LABEL_14;
  }
  memcpy(v4, this->_pbClientCert, this->_cbClientCert);
  *ppbClientCert = v6;
  *pcbClientCert = this->_cbClientCert;
  this->Unlock(this);
  if ( (byte_10185760[0] & 8) != 0 )
    WPP_SF_qd(0x403u, 0xB2u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, *ppbClientCert, *pcbClientCert);
LABEL_15:
  if ( (byte_10185760[16 * (v3 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v3 >> 31) + 2) << 9) | 3, 0xB3u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x10134c90  mov     edi, edi
0x10134c92  push    ebp
0x10134c93  mov     ebp, esp
0x10134c95  push    ecx
0x10134c96  push    ebx
0x10134c97  push    esi
0x10134c98  push    edi
0x10134c99  test    byte_10185760, 8; __annotation("TMF:",
0x10134ca0  mov     ebx, [ebp+this]
0x10134ca3  jz      short loc_10134CC2
0x10134ca5  mov     ecx, [ebp+pcbClientCert]
0x10134ca8  mov     edx, 0B1h; id
0x10134cad  mov     eax, [ebp+ppbClientCert]
0x10134cb0  push    ecx; _a3
0x10134cb1  push    eax; _a2
0x10134cb2  push    ebx; _a1
0x10134cb3  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10134cb8  mov     ecx, 403h; LevelKeyword
0x10134cbd  call    _WPP_SF_qdq@24; WPP_SF_qdq(x,x,x,x,x,x)
0x10134cc2  mov     eax, [ebx]
0x10134cc4  mov     esi, [eax+7Ch]
0x10134cc7  mov     ecx, esi; this
0x10134cc9  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10134ccf  mov     ecx, ebx
0x10134cd1  call    esi
0x10134cd3  mov     ecx, ebx; this
0x10134cd5  call    ?_OnClientCert@URLMONRequest@@IAEJXZ; URLMONRequest::_OnClientCert(void)
0x10134cda  mov     edi, eax
0x10134cdc  test    edi, edi
0x10134cde  js      loc_10134D90
0x10134ce4  mov     esi, [ebp+ppbClientCert]
0x10134ce7  test    esi, esi
0x10134ce9  jnz     short loc_10134CF5
0x10134ceb  mov     edi, 80004003h
0x10134cf0  jmp     loc_10134D90
0x10134cf5  mov     eax, [ebp+pcbClientCert]
0x10134cf8  xor     ecx, ecx
0x10134cfa  mov     [esi], ecx
0x10134cfc  test    eax, eax
0x10134cfe  jz      short loc_10134CEB
0x10134d00  mov     [eax], ecx
0x10134d02  mov     eax, [ebx+10Ch]
0x10134d08  test    eax, eax
0x10134d0a  jz      short loc_10134D8B
0x10134d0c  cmp     [ebx+110h], ecx
0x10134d12  jz      short loc_10134D8B
0x10134d14  push    eax; cb
0x10134d15  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10134d1b  mov     [ebp+var_4], eax
0x10134d1e  test    eax, eax
0x10134d20  jnz     short loc_10134D29
0x10134d22  mov     edi, 8007000Eh
0x10134d27  jmp     short loc_10134D90
0x10134d29  push    dword ptr [ebx+10Ch]; Size
0x10134d2f  push    dword ptr [ebx+110h]; Src
0x10134d35  push    eax; void *
0x10134d36  call    _memcpy
0x10134d3b  mov     ecx, [ebp+pcbClientCert]
0x10134d3e  add     esp, 0Ch
0x10134d41  mov     eax, [ebp+var_4]
0x10134d44  mov     [esi], eax
0x10134d46  mov     eax, [ebx+10Ch]
0x10134d4c  mov     [ecx], eax
0x10134d4e  mov     eax, [ebx]
0x10134d50  mov     esi, [eax+80h]
0x10134d56  mov     ecx, esi; this
0x10134d58  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10134d5e  mov     ecx, ebx
0x10134d60  call    esi
0x10134d62  test    byte_10185760, 8; __annotation("TMF:",
0x10134d69  jz      short loc_10134DA4
0x10134d6b  mov     eax, [ebp+pcbClientCert]
0x10134d6e  mov     edx, 0B2h; id
0x10134d73  mov     ecx, 403h; LevelKeyword
0x10134d78  push    dword ptr [eax]; _a2
0x10134d7a  mov     eax, [ebp+ppbClientCert]
0x10134d7d  push    dword ptr [eax]; _a1
0x10134d7f  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10134d84  call    _WPP_SF_qd@20; WPP_SF_qd(x,x,x,x,x)
0x10134d89  jmp     short loc_10134DA4
0x10134d8b  mov     edi, 80004005h
0x10134d90  mov     eax, [ebx]
0x10134d92  mov     esi, [eax+80h]
0x10134d98  mov     ecx, esi; this
0x10134d9a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10134da0  mov     ecx, ebx
0x10134da2  call    esi
0x10134da4  mov     ecx, edi; __annotation("TMF:",
0x10134da6  sar     ecx, 1Fh
0x10134da9  mov     eax, ecx
0x10134dab  shl     eax, 4
0x10134dae  test    byte_10185760[eax], 8
0x10134db5  jz      short loc_10134DD0
0x10134db7  add     ecx, 2
0x10134dba  mov     edx, 0B3h; id
0x10134dbf  push    edi; _a1
0x10134dc0  shl     ecx, 9
0x10134dc3  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10134dc8  or      ecx, 3; LevelKeyword
0x10134dcb  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10134dd0  mov     eax, edi
0x10134dd2  pop     edi
0x10134dd3  pop     esi
0x10134dd4  pop     ebx
0x10134dd5  leave
0x10134dd6  retn    0Ch
```
