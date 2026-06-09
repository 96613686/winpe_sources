# URLMONRequest::_ApplySettingToProtocol(void)

- ea: `0x10135df8`
- end: `0x10135fb2`
- name: `?_ApplySettingToProtocol@URLMONRequest@@IAEJXZ`
- size: `442`
- prototype: `HRESULT __thiscall(URLMONRequest *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1013a000`

## callees

- `0x1005083d`
- `0x10067b20`
- `0x10135cda`
- `0x10135df8`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x10135e83`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x10135e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10135e93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10135e93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10135f74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10135f74`

## pseudocode

```c
HRESULT __thiscall URLMONRequest::_ApplySettingToProtocol(URLMONRequest *this)
{
  HRESULT v2; // edi
  HANDLE Event; // eax
  signed int LastError; // eax
  unsigned int cbTemp; // [esp+Ch] [ebp-Ch] BYREF
  unsigned __int8 *pbTemp; // [esp+10h] [ebp-8h] BYREF
  INetworkTransportSettings *pTransportSettings; // [esp+14h] [ebp-4h] BYREF

  v2 = 0;
  pTransportSettings = 0;
  cbTemp = 0;
  pbTemp = 0;
  if ( (byte_10185760[0] & 8) != 0 )
    WPP_SF_q(0x403u, 0x68u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (int)this);
  this->Lock(this);
  if ( this->_pIInternetProtocol
    && this->_cbSetting
    && this->_pbSetting
    && !IsEqualGUID(&this->_SettingId.Guid, &GUID_NULL) )
  {
    Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
    this->_hStartComplete = Event;
    if ( Event )
    {
      v2 = ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IInternetProtocol *, GUID *, INetworkTransportSettings **))this->_pIInternetProtocol->QueryInterface)(
             this->_pIInternetProtocol->QueryInterface,
             this->_pIInternetProtocol,
             &IID_INetworkTransportSettings,
             &pTransportSettings);
      if ( v2 >= 0 )
        v2 = ((int (__thiscall *)(HRESULT (__stdcall *)(INetworkTransportSettings *, const TRANSPORT_SETTING_ID *, unsigned int, const unsigned __int8 *, unsigned int *, unsigned __int8 **), INetworkTransportSettings *, TRANSPORT_SETTING_ID *, unsigned int, unsigned __int8 *, unsigned int *, unsigned __int8 **))pTransportSettings->ApplySetting)(
               pTransportSettings->ApplySetting,
               pTransportSettings,
               &this->_SettingId,
               this->_cbSetting,
               this->_pbSetting,
               &cbTemp,
               &pbTemp);
      if ( v2 == -2147467262 || v2 == -2147467263 )
      {
        this->Unlock(this);
        URLMONRequest::_AbortBadPushRequest(this, v2);
        this->Lock(this);
      }
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  this->Unlock(this);
  if ( pTransportSettings )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), INetworkTransportSettings *))pTransportSettings->Release)(
      pTransportSettings->Release,
      pTransportSettings);
    pTransportSettings = 0;
  }
  CoTaskMemFree(pbTemp);
  pbTemp = 0;
  if ( (byte_10185760[16 * (v2 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v2 >> 31) + 2) << 9) | 3, 0x69u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x10135df8  mov     edi, edi
0x10135dfa  push    ebp
0x10135dfb  mov     ebp, esp
0x10135dfd  sub     esp, 0Ch
0x10135e00  push    ebx
0x10135e01  xor     eax, eax
0x10135e03  mov     ebx, this
0x10135e05  push    esi
0x10135e06  push    edi
0x10135e07  mov     edi, eax
0x10135e09  mov     [ebp+pTransportSettings], eax
0x10135e0c  mov     [ebp+cbTemp], eax
0x10135e0f  mov     [ebp+pbTemp], eax
0x10135e12  test    byte_10185760, 8; __annotation("TMF:",
0x10135e19  jz      short loc_10135E2E
0x10135e1b  push    ebx; _a1
0x10135e1c  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10135e21  push    68h ; 'h'
0x10135e23  pop     edx; id
0x10135e24  mov     this, 403h; LevelKeyword
0x10135e29  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10135e2e  mov     eax, [ebx]
0x10135e30  mov     esi, [eax+7Ch]
0x10135e33  mov     this, esi; this
0x10135e35  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10135e3b  mov     this, ebx
0x10135e3d  call    esi
0x10135e3f  xor     esi, esi
0x10135e41  cmp     [ebx+68h], esi
0x10135e44  jz      CleanUp_479
0x10135e4a  cmp     [ebx+130h], esi
0x10135e50  jz      CleanUp_479
0x10135e56  cmp     [ebx+134h], esi
0x10135e5c  jz      CleanUp_479
0x10135e62  lea     this, [ebx+120h]; rguid1
0x10135e68  mov     edx, offset _GUID_NULL; rguid2
0x10135e6d  call    ?IsEqualGUID@@YGHABU_GUID@@0@Z; IsEqualGUID(_GUID const &,_GUID const &)
0x10135e72  test    eax, eax
0x10135e74  jnz     CleanUp_479
0x10135e7a  push    1F0003h; dwDesiredAccess
0x10135e7f  push    1; dwFlags
0x10135e81  push    esi; lpName
0x10135e82  push    esi; lpEventAttributes
0x10135e83  call    ds:__imp__CreateEventExW@16; CreateEventExW(x,x,x,x)
0x10135e89  mov     [ebx+144h], eax
0x10135e8f  test    eax, eax
0x10135e91  jnz     short loc_10135EB1
0x10135e93  call    ds:__imp__GetLastError@0; GetLastError()
0x10135e99  mov     edi, eax
0x10135e9b  test    edi, edi
0x10135e9d  jle     CleanUp_479
0x10135ea3  movzx   edi, di
0x10135ea6  or      edi, 80070000h
0x10135eac  jmp     CleanUp_479
0x10135eb1  mov     this, [ebx+68h]
0x10135eb4  mov     eax, [this]
0x10135eb6  mov     esi, [eax]
0x10135eb8  lea     eax, [ebp+pTransportSettings]
0x10135ebb  push    eax
0x10135ebc  push    offset _IID_INetworkTransportSettings
0x10135ec1  push    this
0x10135ec2  mov     this, esi; this
0x10135ec4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10135eca  call    esi
0x10135ecc  mov     edi, eax
0x10135ece  test    edi, edi
0x10135ed0  js      short loc_10135F02
0x10135ed2  mov     this, [ebp+pTransportSettings]
0x10135ed5  mov     eax, [this]
0x10135ed7  mov     esi, [eax+0Ch]
0x10135eda  lea     eax, [ebp+pbTemp]
0x10135edd  push    eax
0x10135ede  lea     eax, [ebp+cbTemp]
0x10135ee1  push    eax
0x10135ee2  push    dword ptr [ebx+134h]
0x10135ee8  lea     eax, [ebx+120h]
0x10135eee  push    dword ptr [ebx+130h]
0x10135ef4  push    eax
0x10135ef5  push    this
0x10135ef6  mov     this, esi; this
0x10135ef8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10135efe  call    esi
0x10135f00  mov     edi, eax
0x10135f02  cmp     edi, 80004002h
0x10135f08  jz      short loc_10135F12
0x10135f0a  cmp     edi, 80004001h
0x10135f10  jnz     short CleanUp_479
0x10135f12  mov     eax, [ebx]
0x10135f14  mov     esi, [eax+80h]
0x10135f1a  mov     this, esi; this
0x10135f1c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10135f22  mov     this, ebx
0x10135f24  call    esi
0x10135f26  push    edi; hr
0x10135f27  mov     this, ebx; this
0x10135f29  call    ?_AbortBadPushRequest@URLMONRequest@@IAEXJ@Z; URLMONRequest::_AbortBadPushRequest(long)
0x10135f2e  mov     eax, [ebx]
0x10135f30  mov     esi, [eax+7Ch]
0x10135f33  mov     this, esi; this
0x10135f35  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10135f3b  mov     this, ebx
0x10135f3d  call    esi
0x10135f3f  mov     eax, [ebx]
0x10135f41  mov     esi, [eax+80h]
0x10135f47  mov     this, esi; this
0x10135f49  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10135f4f  mov     this, ebx
0x10135f51  call    esi
0x10135f53  mov     this, [ebp+pTransportSettings]
0x10135f56  test    this, this
0x10135f58  jz      short loc_10135F71
0x10135f5a  mov     eax, [this]
0x10135f5c  push    this
0x10135f5d  mov     esi, [eax+8]
0x10135f60  mov     this, esi; this
0x10135f62  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10135f68  call    esi
0x10135f6a  mov     [ebp+pTransportSettings], 0
0x10135f71  push    [ebp+pbTemp]; pv
0x10135f74  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10135f7a  mov     [ebp+pbTemp], 0
0x10135f81  mov     this, edi; __annotation("TMF:",
0x10135f83  sar     this, 1Fh
0x10135f86  mov     eax, this
0x10135f88  shl     eax, 4
0x10135f8b  test    byte_10185760[eax], 8
0x10135f92  jz      short loc_10135FAB
0x10135f94  push    edi; _a1
0x10135f95  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10135f9a  add     this, 2
0x10135f9d  shl     this, 9
0x10135fa0  push    69h ; 'i'
0x10135fa2  or      this, 3; LevelKeyword
0x10135fa5  pop     edx; id
0x10135fa6  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10135fab  mov     eax, edi
0x10135fad  pop     edi
0x10135fae  pop     esi
0x10135faf  pop     ebx
0x10135fb0  leave
0x10135fb1  retn
```
