# Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>(void)

- ea: `0x180002a8c`
- end: `0x180002b5f`
- name: `??0?$ClassFactory@UIClassFactory@@VFtmBase@WRL@Microsoft@@VNil@Details@34@$0A@@WRL@Microsoft@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003620`

## callees

- `0x180002a8c`
- `0x18000b010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x180002abe`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x180002abe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>(
        __int64 a1)
{
  __int64 *v2; // rsi
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v5; // rcx
  LPUNKNOWN v6; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)(a1 + 16) = &Microsoft::WRL::FtmBase::`vftable';
  v2 = (__int64 *)(a1 + 40);
  *(_QWORD *)(a1 + 40) = 0;
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
  *(_DWORD *)(a1 + 52) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::`vftable';
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::`vftable'{for `IClassFactory'};
  *(_QWORD *)(a1 + 16) = &Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<6>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  *(_DWORD *)(a1 + 60) = 4;
  return a1;
}

```

## disassembly

```asm
0x180002a8c  push    rbx
0x180002a8e  push    rbp
0x180002a8f  push    rsi
0x180002a90  push    rdi
0x180002a91  sub     rsp, 28h
0x180002a95  mov     rdi, rcx
0x180002a98  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180002a9f  mov     [rcx+10h], rax
0x180002aa3  lea     rsi, [rcx+28h]
0x180002aa7  mov     qword ptr [rsi], 0
0x180002aae  mov     [rsp+48h+ppunkMarshal], 0
0x180002ab7  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180002abc  xor     ecx, ecx; punkOuter
0x180002abe  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180002ac4  test    eax, eax
0x180002ac6  js      short loc_180002B05
0x180002ac8  mov     rbx, [rsp+48h+ppunkMarshal]
0x180002acd  mov     rax, [rbx]
0x180002ad0  mov     rbp, [rax]
0x180002ad3  mov     rcx, [rsi]
0x180002ad6  test    rcx, rcx
0x180002ad9  jz      short loc_180002AEF
0x180002adb  mov     qword ptr [rsi], 0
0x180002ae2  mov     rdx, [rcx]
0x180002ae5  mov     rax, [rdx+10h]
0x180002ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aee  nop
0x180002aef  mov     r8, rsi
0x180002af2  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180002af9  mov     rcx, rbx
0x180002afc  mov     rax, rbp
0x180002aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b04  nop
0x180002b05  mov     rcx, [rsp+48h+ppunkMarshal]
0x180002b0a  test    rcx, rcx
0x180002b0d  jz      short loc_180002B25
0x180002b0f  mov     [rsp+48h+ppunkMarshal], 0
0x180002b18  mov     rax, [rcx]
0x180002b1b  mov     rax, [rax+10h]
0x180002b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b24  nop
0x180002b25  mov     dword ptr [rdi+34h], 1
0x180002b2c  lea     rax, ??_7?$ClassFactory@UIClassFactory@@VFtmBase@WRL@Microsoft@@VNil@Details@34@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::`vftable'
0x180002b33  mov     [rdi], rax
0x180002b36  lea     rax, ??_7?$ClassFactory@UIClassFactory@@VFtmBase@WRL@Microsoft@@VNil@Details@34@$0A@@WRL@Microsoft@@6BIClassFactory@@@; const Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::`vftable'{for `IClassFactory'}
0x180002b3d  mov     [rdi+8], rax
0x180002b41  lea     rax, ??_7?$ClassFactory@UIClassFactory@@VFtmBase@WRL@Microsoft@@VNil@Details@34@$0A@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$05@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@VNil@523@V6523@@Details@12@@; const Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<6>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180002b48  mov     [rdi+10h], rax
0x180002b4c  mov     dword ptr [rdi+3Ch], 4
0x180002b53  mov     rax, rdi
0x180002b56  add     rsp, 28h
0x180002b5a  pop     rdi
0x180002b5b  pop     rsi
0x180002b5c  pop     rbp
0x180002b5d  pop     rbx
0x180002b5e  retn
```
