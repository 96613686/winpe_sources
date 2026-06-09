# URLMONRequest::_FreeTransportSettings(void)

- ea: `0x1013749b`
- end: `0x10137529`
- name: `?_FreeTransportSettings@URLMONRequest@@IAEXXZ`
- size: `142`
- prototype: `void __thiscall(URLMONRequest *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10133218`
- `0x10133580`
- `0x10139a70`

## callees

- `0x10067bc0`
- `0x1013749b`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101374e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101374e9`

## pseudocode

```c
void __thiscall URLMONRequest::_FreeTransportSettings(URLMONRequest *this)
{
  URLMONRequest_vtbl *v2; // eax
  unsigned __int8 *pbSetting; // [esp-4h] [ebp-10h]

  if ( (byte_101857A0[0] & 8) != 0 )
    WPP_SF_q(0x403u, 0x64u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (int)this);
  this->Lock(this);
  this->_SettingId.Guid.Data1 = 0;
  *(_DWORD *)&this->_SettingId.Guid.Data2 = 0;
  *(_DWORD *)this->_SettingId.Guid.Data4 = 0;
  *(_DWORD *)&this->_SettingId.Guid.Data4[4] = 0;
  pbSetting = this->_pbSetting;
  this->_cbSetting = 0;
  CoTaskMemFree(pbSetting);
  v2 = this->__vftable;
  this->_pbSetting = 0;
  v2->Unlock(this);
  if ( (byte_101857A0[0] & 8) != 0 )
    WPP_SF_q(0x403u, 0x65u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, 0);
}

```

## disassembly

```asm
0x1013749b  mov     edi, edi
0x1013749d  push    ebx
0x1013749e  push    esi
0x1013749f  push    edi
0x101374a0  mov     ebx, this
0x101374a2  test    byte_101857A0, 8; __annotation("TMF:",
0x101374a9  jz      short loc_101374BE
0x101374ab  push    ebx; _a1
0x101374ac  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101374b1  push    64h ; 'd'
0x101374b3  pop     edx; id
0x101374b4  mov     this, 403h; LevelKeyword
0x101374b9  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101374be  mov     eax, [ebx]
0x101374c0  mov     esi, [eax+7Ch]
0x101374c3  mov     this, esi; this
0x101374c5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101374cb  mov     this, ebx
0x101374cd  call    esi
0x101374cf  xor     eax, eax
0x101374d1  lea     edi, [ebx+120h]
0x101374d7  stosd
0x101374d8  stosd
0x101374d9  stosd
0x101374da  stosd
0x101374db  push    dword ptr [ebx+134h]; pv
0x101374e1  xor     edi, edi
0x101374e3  mov     [ebx+130h], edi
0x101374e9  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x101374ef  mov     eax, [ebx]
0x101374f1  mov     [ebx+134h], edi
0x101374f7  mov     esi, [eax+80h]
0x101374fd  mov     this, esi; this
0x101374ff  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10137505  mov     this, ebx
0x10137507  call    esi
0x10137509  test    byte_101857A0, 8; __annotation("TMF:",
0x10137510  jz      short loc_10137525
0x10137512  push    edi; _a1
0x10137513  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10137518  push    65h ; 'e'
0x1013751a  pop     edx; id
0x1013751b  mov     this, 403h; LevelKeyword
0x10137520  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10137525  pop     edi
0x10137526  pop     esi
0x10137527  pop     ebx
0x10137528  retn
```
