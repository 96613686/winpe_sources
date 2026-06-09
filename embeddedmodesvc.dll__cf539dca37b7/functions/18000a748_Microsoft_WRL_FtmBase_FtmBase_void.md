# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000a748`
- end: `0x18000a7ce`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009b28`
- `0x18000ff60`

## callees

- `0x180005590`
- `0x18000a748`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000a784`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000a784`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  v2 = (char *)this + 24;
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v3, &GUID_00000003_0000_0000_c000_000000000046, v2);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  return this;
}

```

## disassembly

```asm
0x18000a748  push    rbx
0x18000a74a  push    rsi
0x18000a74b  push    rdi
0x18000a74c  push    r14
0x18000a74e  sub     rsp, 28h
0x18000a752  mov     rsi, rcx
0x18000a755  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000a75c  mov     [rcx], rax
0x18000a75f  lea     r14, [rcx+18h]
0x18000a763  mov     qword ptr [r14], 0
0x18000a76a  mov     [rsp+48h+ppunkMarshal], 0
0x18000a773  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000a778  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a77d  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18000a782  xor     ecx, ecx; punkOuter
0x18000a784  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000a78a  test    eax, eax
0x18000a78c  js      short loc_18000A7B7
0x18000a78e  mov     rbx, [rsp+48h+ppunkMarshal]
0x18000a793  mov     rax, [rbx]
0x18000a796  mov     rdi, [rax]
0x18000a799  mov     rcx, r14
0x18000a79c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a7a1  mov     r8, r14
0x18000a7a4  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000a7ab  mov     rcx, rbx
0x18000a7ae  mov     rax, rdi
0x18000a7b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7b6  nop
0x18000a7b7  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000a7bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a7c1  mov     rax, rsi
0x18000a7c4  add     rsp, 28h
0x18000a7c8  pop     r14
0x18000a7ca  pop     rdi
0x18000a7cb  pop     rsi
0x18000a7cc  pop     rbx
0x18000a7cd  retn
```
