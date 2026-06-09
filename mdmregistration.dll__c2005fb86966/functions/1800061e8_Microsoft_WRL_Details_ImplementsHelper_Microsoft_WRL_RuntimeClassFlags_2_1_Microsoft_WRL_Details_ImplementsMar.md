# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)

- ea: `0x1800061e8`
- end: `0x180006293`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `171`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800058cc`
- `0x180005b20`
- `0x18001aadc`
- `0x180021ef0`
- `0x180044f4c`

## callees

- `0x1800061e8`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180006219`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180006219`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800061e8  push    rbx
0x1800061ea  push    rbp
0x1800061eb  push    rsi
0x1800061ec  push    rdi
0x1800061ed  sub     rsp, 28h
0x1800061f1  mov     rsi, rcx
0x1800061f4  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800061fb  mov     [rcx], rax
0x1800061fe  lea     rdi, [rcx+18h]
0x180006202  mov     qword ptr [rdi], 0
0x180006209  mov     [rsp+48h+ppunkMarshal], 0
0x180006212  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180006217  xor     ecx, ecx; punkOuter
0x180006219  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180006220  nop     dword ptr [rax+rax+00h]
0x180006225  test    eax, eax
0x180006227  js      short loc_180006266
0x180006229  mov     rbx, [rsp+48h+ppunkMarshal]
0x18000622e  mov     rax, [rbx]
0x180006231  mov     rbp, [rax]
0x180006234  mov     rcx, [rdi]
0x180006237  test    rcx, rcx
0x18000623a  jz      short loc_180006250
0x18000623c  mov     qword ptr [rdi], 0
0x180006243  mov     rdx, [rcx]
0x180006246  mov     rax, [rdx+10h]
0x18000624a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000624f  nop
0x180006250  mov     r8, rdi
0x180006253  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000625a  mov     rcx, rbx
0x18000625d  mov     rax, rbp
0x180006260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006265  nop
0x180006266  mov     rcx, [rsp+48h+ppunkMarshal]
0x18000626b  test    rcx, rcx
0x18000626e  jz      short loc_180006286
0x180006270  mov     [rsp+48h+ppunkMarshal], 0
0x180006279  mov     rax, [rcx]
0x18000627c  mov     rax, [rax+10h]
0x180006280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006285  nop
0x180006286  mov     rax, rsi
0x180006289  add     rsp, 28h
0x18000628d  pop     rdi
0x18000628e  pop     rsi
0x18000628f  pop     rbp
0x180006290  pop     rbx
0x180006291  retn
```
