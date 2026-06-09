# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180007a40`
- end: `0x180007ae1`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `161`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007a1c`
- `0x18001c914`
- `0x180043d18`

## callees

- `0x180007a40`
- `0x180007ae8`
- `0x180045010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x180007a7c`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x180007a7c`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  Microsoft::WRL::ComPtr<IMarshal> *p_marshaller; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  LPUNKNOWN v5; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  p_marshaller = &this->marshaller_;
  ppunkMarshal = 0;
  this->__vftable = (Microsoft::WRL::FtmBase_vtbl *)&Microsoft::WRL::FtmBase::`vftable';
  this->marshaller_.ptr_ = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(p_marshaller);
    QueryInterface(v3, &GUID_00000003_0000_0000_c000_000000000046, (void **)&p_marshaller->ptr_);
  }
  v5 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    v5->Release(v5);
  }
  return this;
}

```

## disassembly

```asm
0x180007a40  push    rbx
0x180007a42  push    rsi
0x180007a43  push    rdi
0x180007a44  push    r14
0x180007a46  sub     rsp, 28h
0x180007a4a  lea     r14, [rcx+18h]
0x180007a4e  mov     [rsp+48h+ppunkMarshal], 0
0x180007a57  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180007a5e  mov     rsi, rcx
0x180007a61  mov     [rcx], rax
0x180007a64  lea     rcx, [rsp+48h+ppunkMarshal]
0x180007a69  mov     qword ptr [r14], 0
0x180007a70  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007a75  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180007a7a  xor     ecx, ecx; punkOuter
0x180007a7c  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180007a83  nop     dword ptr [rax+rax+00h]
0x180007a88  test    eax, eax
0x180007a8a  js      short loc_180007AB4
0x180007a8c  mov     rbx, [rsp+48h+ppunkMarshal]
0x180007a91  mov     rcx, r14
0x180007a94  mov     rax, [rbx]
0x180007a97  mov     rdi, [rax]
0x180007a9a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007a9f  mov     r8, r14
0x180007aa2  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180007aa9  mov     rcx, rbx
0x180007aac  mov     rax, rdi
0x180007aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ab4  mov     rcx, [rsp+48h+ppunkMarshal]
0x180007ab9  test    rcx, rcx
0x180007abc  jz      short loc_180007AD3
0x180007abe  mov     [rsp+48h+ppunkMarshal], 0
0x180007ac7  mov     rax, [rcx]
0x180007aca  mov     rax, [rax+10h]
0x180007ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ad3  mov     rax, rsi
0x180007ad6  add     rsp, 28h
0x180007ada  pop     r14
0x180007adc  pop     rdi
0x180007add  pop     rsi
0x180007ade  pop     rbx
0x180007adf  retn
```
