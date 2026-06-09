# URLMONRequest::_ApplySettingToProtocol(void)

- ea: `0x10135ce8`
- end: `0x10135ea2`
- name: `?_ApplySettingToProtocol@URLMONRequest@@IAEJXZ`
- size: `442`
- prototype: `HRESULT __thiscall(URLMONRequest *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10139ef0`

## callees

- `0x100508cd`
- `0x10067bc0`
- `0x10135bca`
- `0x10135ce8`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x10135d73`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x10135d73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10135d83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10135d83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10135e64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10135e64`

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
  if ( (byte_101857A0[0] & 8) != 0 )
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
  if ( (byte_101857A0[16 * (v2 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v2 >> 31) + 2) << 9) | 3, 0x69u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x10135ce8  mov     edi, edi
0x10135cea  push    ebp
0x10135ceb  mov     ebp, esp
0x10135ced  sub     esp, 0Ch
0x10135cf0  push    ebx
0x10135cf1  xor     eax, eax
0x10135cf3  mov     ebx, this
0x10135cf5  push    esi
0x10135cf6  push    edi
0x10135cf7  mov     edi, eax
0x10135cf9  mov     [ebp+pTransportSettings], eax
0x10135cfc  mov     [ebp+cbTemp], eax
0x10135cff  mov     [ebp+pbTemp], eax
0x10135d02  test    byte_101857A0, 8; __annotation("TMF:",
0x10135d09  jz      short loc_10135D1E
0x10135d0b  push    ebx; _a1
0x10135d0c  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10135d11  push    68h ; 'h'
0x10135d13  pop     edx; id
0x10135d14  mov     this, 403h; LevelKeyword
0x10135d19  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10135d1e  mov     eax, [ebx]
0x10135d20  mov     esi, [eax+7Ch]
0x10135d23  mov     this, esi; this
0x10135d25  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10135d2b  mov     this, ebx
0x10135d2d  call    esi
0x10135d2f  xor     esi, esi
0x10135d31  cmp     [ebx+68h], esi
0x10135d34  jz      CleanUp_479
0x10135d3a  cmp     [ebx+130h], esi
0x10135d40  jz      CleanUp_479
0x10135d46  cmp     [ebx+134h], esi
0x10135d4c  jz      CleanUp_479
0x10135d52  lea     this, [ebx+120h]; rguid1
0x10135d58  mov     edx, offset _GUID_NULL; rguid2
0x10135d5d  call    ?IsEqualGUID@@YGHABU_GUID@@0@Z; IsEqualGUID(_GUID const &,_GUID const &)
0x10135d62  test    eax, eax
0x10135d64  jnz     CleanUp_479
0x10135d6a  push    1F0003h; dwDesiredAccess
0x10135d6f  push    1; dwFlags
0x10135d71  push    esi; lpName
0x10135d72  push    esi; lpEventAttributes
0x10135d73  call    ds:__imp__CreateEventExW@16; CreateEventExW(x,x,x,x)
0x10135d79  mov     [ebx+144h], eax
0x10135d7f  test    eax, eax
0x10135d81  jnz     short loc_10135DA1
0x10135d83  call    ds:__imp__GetLastError@0; GetLastError()
0x10135d89  mov     edi, eax
0x10135d8b  test    edi, edi
0x10135d8d  jle     CleanUp_479
0x10135d93  movzx   edi, di
0x10135d96  or      edi, 80070000h
0x10135d9c  jmp     CleanUp_479
0x10135da1  mov     this, [ebx+68h]
0x10135da4  mov     eax, [this]
0x10135da6  mov     esi, [eax]
0x10135da8  lea     eax, [ebp+pTransportSettings]
0x10135dab  push    eax
0x10135dac  push    offset _IID_INetworkTransportSettings
0x10135db1  push    this
0x10135db2  mov     this, esi; this
0x10135db4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10135dba  call    esi
0x10135dbc  mov     edi, eax
0x10135dbe  test    edi, edi
0x10135dc0  js      short loc_10135DF2
0x10135dc2  mov     this, [ebp+pTransportSettings]
0x10135dc5  mov     eax, [this]
0x10135dc7  mov     esi, [eax+0Ch]
0x10135dca  lea     eax, [ebp+pbTemp]
0x10135dcd  push    eax
0x10135dce  lea     eax, [ebp+cbTemp]
0x10135dd1  push    eax
0x10135dd2  push    dword ptr [ebx+134h]
0x10135dd8  lea     eax, [ebx+120h]
0x10135dde  push    dword ptr [ebx+130h]
0x10135de4  push    eax
0x10135de5  push    this
0x10135de6  mov     this, esi; this
0x10135de8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10135dee  call    esi
0x10135df0  mov     edi, eax
0x10135df2  cmp     edi, 80004002h
0x10135df8  jz      short loc_10135E02
0x10135dfa  cmp     edi, 80004001h
0x10135e00  jnz     short CleanUp_479
0x10135e02  mov     eax, [ebx]
0x10135e04  mov     esi, [eax+80h]
0x10135e0a  mov     this, esi; this
0x10135e0c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10135e12  mov     this, ebx
0x10135e14  call    esi
0x10135e16  push    edi; hr
0x10135e17  mov     this, ebx; this
0x10135e19  call    ?_AbortBadPushRequest@URLMONRequest@@IAEXJ@Z; URLMONRequest::_AbortBadPushRequest(long)
0x10135e1e  mov     eax, [ebx]
0x10135e20  mov     esi, [eax+7Ch]
0x10135e23  mov     this, esi; this
0x10135e25  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10135e2b  mov     this, ebx
0x10135e2d  call    esi
0x10135e2f  mov     eax, [ebx]
0x10135e31  mov     esi, [eax+80h]
0x10135e37  mov     this, esi; this
0x10135e39  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10135e3f  mov     this, ebx
0x10135e41  call    esi
0x10135e43  mov     this, [ebp+pTransportSettings]
0x10135e46  test    this, this
0x10135e48  jz      short loc_10135E61
0x10135e4a  mov     eax, [this]
0x10135e4c  push    this
0x10135e4d  mov     esi, [eax+8]
0x10135e50  mov     this, esi; this
0x10135e52  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10135e58  call    esi
0x10135e5a  mov     [ebp+pTransportSettings], 0
0x10135e61  push    [ebp+pbTemp]; pv
0x10135e64  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10135e6a  mov     [ebp+pbTemp], 0
0x10135e71  mov     this, edi; __annotation("TMF:",
0x10135e73  sar     this, 1Fh
0x10135e76  mov     eax, this
0x10135e78  shl     eax, 4
0x10135e7b  test    byte_101857A0[eax], 8
0x10135e82  jz      short loc_10135E9B
0x10135e84  push    edi; _a1
0x10135e85  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10135e8a  add     this, 2
0x10135e8d  shl     this, 9
0x10135e90  push    69h ; 'i'
0x10135e92  or      this, 3; LevelKeyword
0x10135e95  pop     edx; id
0x10135e96  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10135e9b  mov     eax, edi
0x10135e9d  pop     edi
0x10135e9e  pop     esi
0x10135e9f  pop     ebx
0x10135ea0  leave
0x10135ea1  retn
```
