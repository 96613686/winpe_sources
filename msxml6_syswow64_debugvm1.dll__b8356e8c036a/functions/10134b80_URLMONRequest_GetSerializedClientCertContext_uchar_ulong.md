# URLMONRequest::GetSerializedClientCertContext(uchar * *,ulong *)

- ea: `0x10134b80`
- end: `0x10134cc9`
- name: `?GetSerializedClientCertContext@URLMONRequest@@MAGJPAPAEPAK@Z`
- size: `329`
- prototype: `HRESULT __stdcall(URLMONRequest *this, unsigned __int8 **ppbClientCert, unsigned int *pcbClientCert)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x10067bc0`
- `0x10134b80`
- `0x101376f7`
- `0x101711b4`
- `0x10180006`
- `0x10180652`
- `0x101806b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10134c05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10134c05`

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

  if ( (byte_101857A0[0] & 8) != 0 )
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
  if ( (byte_101857A0[0] & 8) != 0 )
    WPP_SF_qd(0x403u, 0xB2u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, *ppbClientCert, *pcbClientCert);
LABEL_15:
  if ( (byte_101857A0[16 * (v3 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v3 >> 31) + 2) << 9) | 3, 0xB3u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x10134b80  mov     edi, edi
0x10134b82  push    ebp
0x10134b83  mov     ebp, esp
0x10134b85  push    ecx
0x10134b86  push    ebx
0x10134b87  push    esi
0x10134b88  push    edi
0x10134b89  test    byte_101857A0, 8; __annotation("TMF:",
0x10134b90  mov     ebx, [ebp+this]
0x10134b93  jz      short loc_10134BB2
0x10134b95  mov     ecx, [ebp+pcbClientCert]
0x10134b98  mov     edx, 0B1h; id
0x10134b9d  mov     eax, [ebp+ppbClientCert]
0x10134ba0  push    ecx; _a3
0x10134ba1  push    eax; _a2
0x10134ba2  push    ebx; _a1
0x10134ba3  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10134ba8  mov     ecx, 403h; LevelKeyword
0x10134bad  call    _WPP_SF_qdq@24; WPP_SF_qdq(x,x,x,x,x,x)
0x10134bb2  mov     eax, [ebx]
0x10134bb4  mov     esi, [eax+7Ch]
0x10134bb7  mov     ecx, esi; this
0x10134bb9  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10134bbf  mov     ecx, ebx
0x10134bc1  call    esi
0x10134bc3  mov     ecx, ebx; this
0x10134bc5  call    ?_OnClientCert@URLMONRequest@@IAEJXZ; URLMONRequest::_OnClientCert(void)
0x10134bca  mov     edi, eax
0x10134bcc  test    edi, edi
0x10134bce  js      loc_10134C80
0x10134bd4  mov     esi, [ebp+ppbClientCert]
0x10134bd7  test    esi, esi
0x10134bd9  jnz     short loc_10134BE5
0x10134bdb  mov     edi, 80004003h
0x10134be0  jmp     loc_10134C80
0x10134be5  mov     eax, [ebp+pcbClientCert]
0x10134be8  xor     ecx, ecx
0x10134bea  mov     [esi], ecx
0x10134bec  test    eax, eax
0x10134bee  jz      short loc_10134BDB
0x10134bf0  mov     [eax], ecx
0x10134bf2  mov     eax, [ebx+10Ch]
0x10134bf8  test    eax, eax
0x10134bfa  jz      short loc_10134C7B
0x10134bfc  cmp     [ebx+110h], ecx
0x10134c02  jz      short loc_10134C7B
0x10134c04  push    eax; cb
0x10134c05  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10134c0b  mov     [ebp+var_4], eax
0x10134c0e  test    eax, eax
0x10134c10  jnz     short loc_10134C19
0x10134c12  mov     edi, 8007000Eh
0x10134c17  jmp     short loc_10134C80
0x10134c19  push    dword ptr [ebx+10Ch]; Size
0x10134c1f  push    dword ptr [ebx+110h]; Src
0x10134c25  push    eax; void *
0x10134c26  call    _memcpy
0x10134c2b  mov     ecx, [ebp+pcbClientCert]
0x10134c2e  add     esp, 0Ch
0x10134c31  mov     eax, [ebp+var_4]
0x10134c34  mov     [esi], eax
0x10134c36  mov     eax, [ebx+10Ch]
0x10134c3c  mov     [ecx], eax
0x10134c3e  mov     eax, [ebx]
0x10134c40  mov     esi, [eax+80h]
0x10134c46  mov     ecx, esi; this
0x10134c48  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10134c4e  mov     ecx, ebx
0x10134c50  call    esi
0x10134c52  test    byte_101857A0, 8; __annotation("TMF:",
0x10134c59  jz      short loc_10134C94
0x10134c5b  mov     eax, [ebp+pcbClientCert]
0x10134c5e  mov     edx, 0B2h; id
0x10134c63  mov     ecx, 403h; LevelKeyword
0x10134c68  push    dword ptr [eax]; _a2
0x10134c6a  mov     eax, [ebp+ppbClientCert]
0x10134c6d  push    dword ptr [eax]; _a1
0x10134c6f  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10134c74  call    _WPP_SF_qd@20; WPP_SF_qd(x,x,x,x,x)
0x10134c79  jmp     short loc_10134C94
0x10134c7b  mov     edi, 80004005h
0x10134c80  mov     eax, [ebx]
0x10134c82  mov     esi, [eax+80h]
0x10134c88  mov     ecx, esi; this
0x10134c8a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10134c90  mov     ecx, ebx
0x10134c92  call    esi
0x10134c94  mov     ecx, edi; __annotation("TMF:",
0x10134c96  sar     ecx, 1Fh
0x10134c99  mov     eax, ecx
0x10134c9b  shl     eax, 4
0x10134c9e  test    byte_101857A0[eax], 8
0x10134ca5  jz      short loc_10134CC0
0x10134ca7  add     ecx, 2
0x10134caa  mov     edx, 0B3h; id
0x10134caf  push    edi; _a1
0x10134cb0  shl     ecx, 9
0x10134cb3  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10134cb8  or      ecx, 3; LevelKeyword
0x10134cbb  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10134cc0  mov     eax, edi
0x10134cc2  pop     edi
0x10134cc3  pop     esi
0x10134cc4  pop     ebx
0x10134cc5  leave
0x10134cc6  retn    0Ch
```
