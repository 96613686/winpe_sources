# URLMONRequest::_FreeTransportSettings(void)

- ea: `0x180084fe4`
- end: `0x18008508e`
- name: `?_FreeTransportSettings@URLMONRequest@@IEAAXXZ`
- size: `170`
- prototype: `void __fastcall(URLMONRequest *this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180084d74`
- `0x180158ca0`
- `0x18015cf00`

## callees

- `0x180084fe4`
- `0x180189008`
- `0x1801890e0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008503c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008503c`

## pseudocode

```c
void __fastcall URLMONRequest::_FreeTransportSettings(URLMONRequest *this)
{
  unsigned __int8 *pbSetting; // rcx
  URLMONRequest_vtbl *v3; // rax

  if ( (xmmword_1801FAD20 & 8) != 0 )
    WPP_SF_q(0x403u, 0x64u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (unsigned __int64)this);
  this->Lock(this);
  this->_SettingId = 0;
  pbSetting = this->_pbSetting;
  this->_cbSetting = 0;
  CoTaskMemFree(pbSetting);
  v3 = this->__vftable;
  this->_pbSetting = 0;
  v3->Unlock(this);
  if ( (xmmword_1801FAD20 & 8) != 0 )
    WPP_SF_d(0x403u, 0x65u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, 0);
}

```

## disassembly

```asm
0x180084fe4  push    rbx
0x180084fe6  sub     rsp, 20h
0x180084fea  mov     rbx, this
0x180084fed  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x180084ff4  jz      short loc_18008500F
0x180084ff6  mov     edx, 64h ; 'd'; id
0x180084ffb  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180085002  mov     ecx, 403h; LevelKeyword
0x180085007  mov     r9, rbx; _a1
0x18008500a  call    WPP_SF_q
0x18008500f  mov     rax, [rbx]
0x180085012  mov     this, rbx
0x180085015  mov     rax, [rax+0F8h]
0x18008501c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085021  xorps   xmm0, xmm0
0x180085024  movups  xmmword ptr [rbx+1F4h], xmm0
0x18008502b  mov     this, [rbx+208h]; pv
0x180085032  mov     dword ptr [rbx+204h], 0
0x18008503c  call    cs:__imp_CoTaskMemFree
0x180085043  nop     dword ptr [rax+rax+00h]
0x180085048  mov     rax, [rbx]
0x18008504b  mov     this, rbx
0x18008504e  mov     qword ptr [rbx+208h], 0
0x180085059  mov     rax, [rax+100h]
0x180085060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085065  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x18008506c  jz      short loc_180085087
0x18008506e  mov     edx, 65h ; 'e'; id
0x180085073  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18008507a  mov     ecx, 403h; LevelKeyword
0x18008507f  xor     r9d, r9d; _a1
0x180085082  call    WPP_SF_d
0x180085087  add     rsp, 20h
0x18008508b  pop     rbx
0x18008508c  retn
```
