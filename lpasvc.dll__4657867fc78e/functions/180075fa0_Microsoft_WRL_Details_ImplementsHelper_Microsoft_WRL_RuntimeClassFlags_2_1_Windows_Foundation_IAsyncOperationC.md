# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Microsoft::WRL::FtmBase>(void)

- ea: `0x180075fa0`
- end: `0x180076031`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180075f38`

## callees

- `0x18005aa2c`
- `0x180075fa0`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180075fe7`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180075fe7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Microsoft::WRL::FtmBase>(
        _QWORD *a1)
{
  _QWORD *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *a1 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>::`vftable';
  a1[1] = &Microsoft::WRL::FtmBase::`vftable';
  v2 = a1 + 4;
  a1[4] = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, _QWORD *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  return a1;
}

```

## disassembly

```asm
0x180075fa0  push    rbx
0x180075fa2  push    rsi
0x180075fa3  push    rdi
0x180075fa4  push    r14
0x180075fa6  sub     rsp, 28h
0x180075faa  mov     rsi, rcx
0x180075fad  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>::`vftable'
0x180075fb4  mov     [rcx], rax
0x180075fb7  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180075fbe  mov     [rcx+8], rax
0x180075fc2  lea     r14, [rcx+20h]
0x180075fc6  mov     qword ptr [r14], 0
0x180075fcd  mov     [rsp+48h+ppunkMarshal], 0
0x180075fd6  lea     rcx, [rsp+48h+ppunkMarshal]
0x180075fdb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180075fe0  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180075fe5  xor     ecx, ecx; punkOuter
0x180075fe7  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180075fed  test    eax, eax
0x180075fef  js      short loc_18007601A
0x180075ff1  mov     rbx, [rsp+48h+ppunkMarshal]
0x180075ff6  mov     rax, [rbx]
0x180075ff9  mov     rdi, [rax]
0x180075ffc  mov     rcx, r14
0x180075fff  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180076004  mov     r8, r14
0x180076007  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18007600e  mov     rcx, rbx
0x180076011  mov     rax, rdi
0x180076014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076019  nop
0x18007601a  lea     rcx, [rsp+48h+ppunkMarshal]
0x18007601f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180076024  mov     rax, rsi
0x180076027  add     rsp, 28h
0x18007602b  pop     r14
0x18007602d  pop     rdi
0x18007602e  pop     rsi
0x18007602f  pop     rbx
0x180076030  retn
```
