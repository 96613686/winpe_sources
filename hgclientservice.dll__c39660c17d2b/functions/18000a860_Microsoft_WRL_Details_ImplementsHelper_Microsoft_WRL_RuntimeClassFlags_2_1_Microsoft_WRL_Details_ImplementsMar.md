# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)

- ea: `0x18000a860`
- end: `0x18000a904`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `164`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800030bc`
- `0x180003190`

## callees

- `0x18000a860`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000a891`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000a891`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(
        _QWORD *a1)
{
  __int64 *v2; // rdi
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v5; // rcx
  LPUNKNOWN v6; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *a1 = &Microsoft::WRL::FtmBase::`vftable';
  v2 = a1 + 3;
  a1[3] = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v5 = *v2;
    if ( *v2 )
    {
      *v2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64 *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  v6 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v6->lpVtbl->Release)(v6);
  }
  return a1;
}

```

## disassembly

```asm
0x18000a860  push    rbx
0x18000a862  push    rbp
0x18000a863  push    rsi
0x18000a864  push    rdi
0x18000a865  sub     rsp, 28h
0x18000a869  mov     rsi, rcx
0x18000a86c  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000a873  mov     [rcx], rax
0x18000a876  lea     rdi, [rcx+18h]
0x18000a87a  mov     qword ptr [rdi], 0
0x18000a881  mov     [rsp+48h+ppunkMarshal], 0
0x18000a88a  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18000a88f  xor     ecx, ecx; punkOuter
0x18000a891  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000a897  test    eax, eax
0x18000a899  js      short loc_18000A8D8
0x18000a89b  mov     rbx, [rsp+48h+ppunkMarshal]
0x18000a8a0  mov     rax, [rbx]
0x18000a8a3  mov     rbp, [rax]
0x18000a8a6  mov     rcx, [rdi]
0x18000a8a9  test    rcx, rcx
0x18000a8ac  jz      short loc_18000A8C2
0x18000a8ae  mov     qword ptr [rdi], 0
0x18000a8b5  mov     rdx, [rcx]
0x18000a8b8  mov     rax, [rdx+10h]
0x18000a8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8c1  nop
0x18000a8c2  mov     r8, rdi
0x18000a8c5  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000a8cc  mov     rcx, rbx
0x18000a8cf  mov     rax, rbp
0x18000a8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8d7  nop
0x18000a8d8  mov     rcx, [rsp+48h+ppunkMarshal]
0x18000a8dd  test    rcx, rcx
0x18000a8e0  jz      short loc_18000A8F8
0x18000a8e2  mov     [rsp+48h+ppunkMarshal], 0
0x18000a8eb  mov     rax, [rcx]
0x18000a8ee  mov     rax, [rax+10h]
0x18000a8f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8f7  nop
0x18000a8f8  mov     rax, rsi
0x18000a8fb  add     rsp, 28h
0x18000a8ff  pop     rdi
0x18000a900  pop     rsi
0x18000a901  pop     rbp
0x18000a902  pop     rbx
0x18000a903  retn
```
