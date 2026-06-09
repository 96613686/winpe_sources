# CKsOutputPin::SetMediaType(CMediaType const *)

- ea: `0x1800192a0`
- end: `0x18001933f`
- name: `?SetMediaType@CKsOutputPin@@UEAAJPEBVCMediaType@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(CKsOutputPin *this, struct CMediaType *rclsid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008690`

## callees

- `0x1800192a0`
- `0x18001b190`
- `0x18001bb40`
- `0x18003f6ac`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall CKsOutputPin::SetMediaType(CKsOutputPin *this, struct CMediaType *rclsid)
{
  void *m_PinHandle; // rcx
  __int64 result; // rax
  IUnknown *m_UnkInner; // rcx

  m_PinHandle = this->m_PinHandle;
  if ( !m_PinHandle || (result = SetMediaType(m_PinHandle, rclsid), (int)result >= 0) )
  {
    if ( this->m_DataTypeHandler )
    {
      m_UnkInner = this->m_UnkInner;
      this->m_DataTypeHandler = 0;
      if ( m_UnkInner )
      {
        this->m_UnkInner = 0;
        m_UnkInner->Release(m_UnkInner);
      }
    }
    OpenDataHandler(
      &rclsid->majortype,
      (LPUNKNOWN)((unsigned __int64)&this->IPin & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
      &this->m_DataTypeHandler,
      &this->m_UnkInner);
    return CBasePin::SetMediaType(this, rclsid);
  }
  return result;
}

```

## disassembly

```asm
0x1800192a0  mov     [rsp+arg_0], rbx
0x1800192a5  mov     [rsp+arg_8], rsi
0x1800192aa  push    rdi
0x1800192ab  sub     rsp, 20h
0x1800192af  mov     rbx, rcx
0x1800192b2  mov     rsi, rdx
0x1800192b5  mov     rcx, [rcx+208h]; hFile
0x1800192bc  test    rcx, rcx
0x1800192bf  jz      short loc_1800192CA
0x1800192c1  call    ?SetMediaType@@YAJPEAXPEBVCMediaType@@@Z; SetMediaType(void *,CMediaType const *)
0x1800192c6  test    eax, eax
0x1800192c8  js      short loc_18001932E
0x1800192ca  lea     rdi, [rbx+230h]
0x1800192d1  cmp     qword ptr [rdi], 0
0x1800192d5  jz      short loc_180019301
0x1800192d7  mov     rcx, [rbx+238h]
0x1800192de  mov     qword ptr [rdi], 0
0x1800192e5  test    rcx, rcx
0x1800192e8  jz      short loc_180019301
0x1800192ea  mov     qword ptr [rbx+238h], 0
0x1800192f5  mov     rax, [rcx]
0x1800192f8  mov     rax, [rax+10h]
0x1800192fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019301  lea     rcx, [rbx+18h]
0x180019305  mov     rax, rbx
0x180019308  neg     rax
0x18001930b  lea     r9, [rbx+238h]; struct IUnknown **
0x180019312  mov     r8, rdi; struct IKsDataTypeHandler **
0x180019315  sbb     rdx, rdx
0x180019318  and     rdx, rcx; pUnkOuter
0x18001931b  mov     rcx, rsi; rclsid
0x18001931e  call    ?OpenDataHandler@@YAXPEBVCMediaType@@PEAUIUnknown@@PEAPEAUIKsDataTypeHandler@@PEAPEAU2@@Z; OpenDataHandler(CMediaType const *,IUnknown *,IKsDataTypeHandler * *,IUnknown * *)
0x180019323  mov     rdx, rsi; struct CMediaType *
0x180019326  mov     rcx, rbx; this
0x180019329  call    ?SetMediaType@CBasePin@@UEAAJPEBVCMediaType@@@Z; CBasePin::SetMediaType(CMediaType const *)
0x18001932e  mov     rbx, [rsp+28h+arg_0]
0x180019333  mov     rsi, [rsp+28h+arg_8]
0x180019338  add     rsp, 20h
0x18001933c  pop     rdi
0x18001933d  retn
```
