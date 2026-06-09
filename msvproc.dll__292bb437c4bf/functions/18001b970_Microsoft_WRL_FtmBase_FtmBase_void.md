# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18001b970`
- end: `0x18001ba0a`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `154`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180027b60`
- `0x180032e64`
- `0x180037d80`
- `0x1800b30d8`
- `0x1800c09ac`
- `0x1800c16e0`
- `0x1800c17dc`
- `0x1800c1a48`
- `0x1800caf1c`

## callees

- `0x18000a09c`
- `0x18001b970`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001b9ac`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001b9ac`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v1; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN v5; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  v1 = (char *)this + 24;
  ppunkMarshal = 0;
  *(_QWORD *)this = &CMFMediaBufferWrapper2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 3) = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v1);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v3, &GUID_00000003_0000_0000_c000_000000000046, v1);
  }
  v5 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v5->lpVtbl->Release)(v5);
  }
  return this;
}

```

## disassembly

```asm
0x18001b970  push    rbx
0x18001b972  push    rsi
0x18001b973  push    rdi
0x18001b974  push    r14
0x18001b976  sub     rsp, 28h
0x18001b97a  lea     r14, [rcx+18h]
0x18001b97e  mov     [rsp+48h+ppunkMarshal], 0
0x18001b987  lea     rax, ??_7CMFMediaBufferWrapper2@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CMFMediaBufferWrapper2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001b98e  mov     rsi, rcx
0x18001b991  mov     [rcx], rax
0x18001b994  lea     rcx, [rsp+48h+ppunkMarshal]
0x18001b999  mov     qword ptr [r14], 0
0x18001b9a0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001b9a5  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18001b9aa  xor     ecx, ecx; punkOuter
0x18001b9ac  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18001b9b2  test    eax, eax
0x18001b9b4  js      short loc_18001B9DE
0x18001b9b6  mov     rbx, [rsp+48h+ppunkMarshal]
0x18001b9bb  mov     rcx, r14
0x18001b9be  mov     rax, [rbx]
0x18001b9c1  mov     rdi, [rax]
0x18001b9c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001b9c9  mov     r8, r14
0x18001b9cc  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18001b9d3  mov     rcx, rbx
0x18001b9d6  mov     rax, rdi
0x18001b9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9de  mov     rcx, [rsp+48h+ppunkMarshal]
0x18001b9e3  test    rcx, rcx
0x18001b9e6  jz      short loc_18001B9FD
0x18001b9e8  mov     [rsp+48h+ppunkMarshal], 0
0x18001b9f1  mov     rax, [rcx]
0x18001b9f4  mov     rax, [rax+10h]
0x18001b9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9fd  mov     rax, rsi
0x18001ba00  add     rsp, 28h
0x18001ba04  pop     r14
0x18001ba06  pop     rdi
0x18001ba07  pop     rsi
0x18001ba08  pop     rbx
0x18001ba09  retn
```
