# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)

- ea: `0x140004474`
- end: `0x140004518`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `164`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003e98`
- `0x140004110`

## callees

- `0x140004474`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1400044a5`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1400044a5`

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
0x140004474  push    rbx
0x140004476  push    rbp
0x140004477  push    rsi
0x140004478  push    rdi
0x140004479  sub     rsp, 28h
0x14000447d  mov     rsi, rcx
0x140004480  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x140004487  mov     [rcx], rax
0x14000448a  lea     rdi, [rcx+18h]
0x14000448e  mov     qword ptr [rdi], 0
0x140004495  mov     [rsp+48h+ppunkMarshal], 0
0x14000449e  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1400044a3  xor     ecx, ecx; punkOuter
0x1400044a5  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1400044ab  test    eax, eax
0x1400044ad  js      short loc_1400044EC
0x1400044af  mov     rbx, [rsp+48h+ppunkMarshal]
0x1400044b4  mov     rax, [rbx]
0x1400044b7  mov     rbp, [rax]
0x1400044ba  mov     rcx, [rdi]
0x1400044bd  test    rcx, rcx
0x1400044c0  jz      short loc_1400044D6
0x1400044c2  mov     qword ptr [rdi], 0
0x1400044c9  mov     rdx, [rcx]
0x1400044cc  mov     rax, [rdx+10h]
0x1400044d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044d5  nop
0x1400044d6  mov     r8, rdi
0x1400044d9  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1400044e0  mov     rcx, rbx
0x1400044e3  mov     rax, rbp
0x1400044e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044eb  nop
0x1400044ec  mov     rcx, [rsp+48h+ppunkMarshal]
0x1400044f1  test    rcx, rcx
0x1400044f4  jz      short loc_14000450C
0x1400044f6  mov     [rsp+48h+ppunkMarshal], 0
0x1400044ff  mov     rax, [rcx]
0x140004502  mov     rax, [rax+10h]
0x140004506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000450b  nop
0x14000450c  mov     rax, rsi
0x14000450f  add     rsp, 28h
0x140004513  pop     rdi
0x140004514  pop     rsi
0x140004515  pop     rbp
0x140004516  pop     rbx
0x140004517  retn
```
