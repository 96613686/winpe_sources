# URLMONRequest::_FreeTransportSettings(void)

- ea: `0x1800868bc`
- end: `0x18008695f`
- name: `?_FreeTransportSettings@URLMONRequest@@IEAAXXZ`
- size: `163`
- prototype: `void __fastcall(URLMONRequest *this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180086664`
- `0x180155620`
- `0x1801597a0`

## callees

- `0x1800868bc`
- `0x180185008`
- `0x1801850e0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086914`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086914`

## pseudocode

```c
void __fastcall URLMONRequest::_FreeTransportSettings(URLMONRequest *this)
{
  unsigned __int8 *pbSetting; // rcx
  URLMONRequest_vtbl *v3; // rax

  if ( (xmmword_1801F6C20 & 8) != 0 )
    WPP_SF_q(0x403u, 0x64u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (unsigned __int64)this);
  this->Lock(this);
  this->_SettingId = 0;
  pbSetting = this->_pbSetting;
  this->_cbSetting = 0;
  CoTaskMemFree(pbSetting);
  v3 = this->__vftable;
  this->_pbSetting = 0;
  v3->Unlock(this);
  if ( (xmmword_1801F6C20 & 8) != 0 )
    WPP_SF_d(0x403u, 0x65u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, 0);
}

```

## disassembly

```asm
0x1800868bc  push    rbx
0x1800868be  sub     rsp, 20h
0x1800868c2  mov     rbx, this
0x1800868c5  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x1800868cc  jz      short loc_1800868E7
0x1800868ce  mov     edx, 64h ; 'd'; id
0x1800868d3  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1800868da  mov     ecx, 403h; LevelKeyword
0x1800868df  mov     r9, rbx; _a1
0x1800868e2  call    WPP_SF_q
0x1800868e7  mov     rax, [rbx]
0x1800868ea  mov     this, rbx
0x1800868ed  mov     rax, [rax+0F8h]
0x1800868f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800868f9  xorps   xmm0, xmm0
0x1800868fc  movups  xmmword ptr [rbx+1F4h], xmm0
0x180086903  mov     this, [rbx+208h]; pv
0x18008690a  mov     dword ptr [rbx+204h], 0
0x180086914  call    cs:__imp_CoTaskMemFree
0x18008691a  mov     rax, [rbx]
0x18008691d  mov     this, rbx
0x180086920  mov     qword ptr [rbx+208h], 0
0x18008692b  mov     rax, [rax+100h]
0x180086932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086937  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x18008693e  jz      short loc_180086959
0x180086940  mov     edx, 65h ; 'e'; id
0x180086945  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18008694c  mov     ecx, 403h; LevelKeyword
0x180086951  xor     r9d, r9d; _a1
0x180086954  call    WPP_SF_d
0x180086959  add     rsp, 20h
0x18008695d  pop     rbx
0x18008695e  retn
```
