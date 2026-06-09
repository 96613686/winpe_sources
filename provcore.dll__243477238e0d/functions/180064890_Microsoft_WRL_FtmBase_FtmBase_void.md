# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180064890`
- end: `0x180064932`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `162`
- prototype: `void __fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800645c0`

## callees

- `0x180002790`
- `0x18005b4a4`
- `0x180064890`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800648db`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800648db`

## pseudocode

```c
void __fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  Microsoft::WRL::ComPtr<IMarshal> *p_marshaller; // r14
  IUnknown *ptr; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  Microsoft::WRL::ComPtr<IUnknown> unknown; // [rsp+20h] [rbp-38h] BYREF

  this->__vftable = (Microsoft::WRL::FtmBase_vtbl *)Microsoft::WRL::FtmBase::`vftable';
  p_marshaller = &this->marshaller_;
  this->marshaller_.ptr_ = 0;
  unknown.ptr_ = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&unknown);
  if ( CoCreateFreeThreadedMarshaler(0, &unknown.ptr_) >= 0 )
  {
    ptr = unknown.ptr_;
    QueryInterface = unknown.ptr_->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)p_marshaller);
    QueryInterface(ptr, &GUID_00000003_0000_0000_c000_000000000046, (void **)&p_marshaller->ptr_);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&unknown);
}

```

## disassembly

```asm
0x180064890  push    rbx
0x180064892  push    rsi
0x180064893  push    rdi
0x180064894  push    r14
0x180064896  sub     rsp, 38h
0x18006489a  mov     rax, cs:__security_cookie
0x1800648a1  xor     rax, rsp
0x1800648a4  mov     [rsp+58h+var_30], rax
0x1800648a9  mov     rsi, this
0x1800648ac  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800648b3  mov     [this], rax
0x1800648b6  lea     r14, [this+18h]
0x1800648ba  mov     qword ptr [r14], 0
0x1800648c1  mov     [rsp+58h+unknown.ptr_], 0
0x1800648ca  lea     this, [rsp+58h+unknown]; this
0x1800648cf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800648d4  lea     rdx, [rsp+58h+unknown]; ppunkMarshal
0x1800648d9  xor     ecx, ecx; punkOuter
0x1800648db  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800648e1  test    eax, eax
0x1800648e3  js      short loc_18006490E
0x1800648e5  mov     rbx, [rsp+58h+unknown.ptr_]
0x1800648ea  mov     rax, [rbx]
0x1800648ed  mov     rdi, [rax]
0x1800648f0  mov     this, r14; this
0x1800648f3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800648f8  mov     r8, r14
0x1800648fb  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180064902  mov     this, rbx
0x180064905  mov     rax, rdi
0x180064908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006490d  nop
0x18006490e  lea     this, [rsp+58h+unknown]; this
0x180064913  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180064918  mov     rax, rsi
0x18006491b  mov     this, [rsp+58h+var_30]
0x180064920  xor     this, rsp; StackCookie
0x180064923  call    __security_check_cookie
0x180064928  add     rsp, 38h
0x18006492c  pop     r14
0x18006492e  pop     rdi
0x18006492f  pop     rsi
0x180064930  pop     rbx
0x180064931  retn
```
