# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)

- ea: `0x140004510`
- end: `0x1400045bb`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `171`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003f18`
- `0x140004198`

## callees

- `0x140004510`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140004541`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140004541`

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
0x140004510  push    rbx
0x140004512  push    rbp
0x140004513  push    rsi
0x140004514  push    rdi
0x140004515  sub     rsp, 28h
0x140004519  mov     rsi, rcx
0x14000451c  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x140004523  mov     [rcx], rax
0x140004526  lea     rdi, [rcx+18h]
0x14000452a  mov     qword ptr [rdi], 0
0x140004531  mov     [rsp+48h+ppunkMarshal], 0
0x14000453a  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x14000453f  xor     ecx, ecx; punkOuter
0x140004541  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x140004548  nop     dword ptr [rax+rax+00h]
0x14000454d  test    eax, eax
0x14000454f  js      short loc_14000458E
0x140004551  mov     rbx, [rsp+48h+ppunkMarshal]
0x140004556  mov     rax, [rbx]
0x140004559  mov     rbp, [rax]
0x14000455c  mov     rcx, [rdi]
0x14000455f  test    rcx, rcx
0x140004562  jz      short loc_140004578
0x140004564  mov     qword ptr [rdi], 0
0x14000456b  mov     rdx, [rcx]
0x14000456e  mov     rax, [rdx+10h]
0x140004572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004577  nop
0x140004578  mov     r8, rdi
0x14000457b  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x140004582  mov     rcx, rbx
0x140004585  mov     rax, rbp
0x140004588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000458d  nop
0x14000458e  mov     rcx, [rsp+48h+ppunkMarshal]
0x140004593  test    rcx, rcx
0x140004596  jz      short loc_1400045AE
0x140004598  mov     [rsp+48h+ppunkMarshal], 0
0x1400045a1  mov     rax, [rcx]
0x1400045a4  mov     rax, [rax+10h]
0x1400045a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045ad  nop
0x1400045ae  mov     rax, rsi
0x1400045b1  add     rsp, 28h
0x1400045b5  pop     rdi
0x1400045b6  pop     rsi
0x1400045b7  pop     rbp
0x1400045b8  pop     rbx
0x1400045b9  retn
```
