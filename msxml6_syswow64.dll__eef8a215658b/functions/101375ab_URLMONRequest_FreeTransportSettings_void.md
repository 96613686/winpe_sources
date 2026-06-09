# URLMONRequest::_FreeTransportSettings(void)

- ea: `0x101375ab`
- end: `0x10137639`
- name: `?_FreeTransportSettings@URLMONRequest@@IAEXXZ`
- size: `142`
- prototype: `void __thiscall(URLMONRequest *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10133328`
- `0x10133690`
- `0x10139b80`

## callees

- `0x10067b20`
- `0x101375ab`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101375f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101375f9`

## pseudocode

```c
void __thiscall URLMONRequest::_FreeTransportSettings(URLMONRequest *this)
{
  URLMONRequest_vtbl *v2; // eax
  unsigned __int8 *pbSetting; // [esp-4h] [ebp-10h]

  if ( (byte_10185760[0] & 8) != 0 )
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
  if ( (byte_10185760[0] & 8) != 0 )
    WPP_SF_q(0x403u, 0x65u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, 0);
}

```

## disassembly

```asm
0x101375ab  mov     edi, edi
0x101375ad  push    ebx
0x101375ae  push    esi
0x101375af  push    edi
0x101375b0  mov     ebx, this
0x101375b2  test    byte_10185760, 8; __annotation("TMF:",
0x101375b9  jz      short loc_101375CE
0x101375bb  push    ebx; _a1
0x101375bc  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101375c1  push    64h ; 'd'
0x101375c3  pop     edx; id
0x101375c4  mov     this, 403h; LevelKeyword
0x101375c9  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101375ce  mov     eax, [ebx]
0x101375d0  mov     esi, [eax+7Ch]
0x101375d3  mov     this, esi; this
0x101375d5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101375db  mov     this, ebx
0x101375dd  call    esi
0x101375df  xor     eax, eax
0x101375e1  lea     edi, [ebx+120h]
0x101375e7  stosd
0x101375e8  stosd
0x101375e9  stosd
0x101375ea  stosd
0x101375eb  push    dword ptr [ebx+134h]; pv
0x101375f1  xor     edi, edi
0x101375f3  mov     [ebx+130h], edi
0x101375f9  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x101375ff  mov     eax, [ebx]
0x10137601  mov     [ebx+134h], edi
0x10137607  mov     esi, [eax+80h]
0x1013760d  mov     this, esi; this
0x1013760f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10137615  mov     this, ebx
0x10137617  call    esi
0x10137619  test    byte_10185760, 8; __annotation("TMF:",
0x10137620  jz      short loc_10137635
0x10137622  push    edi; _a1
0x10137623  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10137628  push    65h ; 'e'
0x1013762a  pop     edx; id
0x1013762b  mov     this, 403h; LevelKeyword
0x10137630  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10137635  pop     edi
0x10137636  pop     esi
0x10137637  pop     ebx
0x10137638  retn
```
