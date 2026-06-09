# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180013214`
- end: `0x1800132a1`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `141`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013080`
- `0x180014164`
- `0x180014298`

## callees

- `0x180004dcc`
- `0x180013214`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180013250`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180013250`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180013214  push    rbx
0x180013216  push    rsi
0x180013217  push    rdi
0x180013218  push    r14
0x18001321a  sub     rsp, 28h
0x18001321e  mov     rsi, rcx
0x180013221  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180013228  mov     [rcx], rax
0x18001322b  lea     r14, [rcx+18h]
0x18001322f  mov     qword ptr [r14], 0
0x180013236  mov     [rsp+48h+ppunkMarshal], 0
0x18001323f  lea     rcx, [rsp+48h+ppunkMarshal]
0x180013244  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013249  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18001324e  xor     ecx, ecx; punkOuter
0x180013250  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180013257  nop     dword ptr [rax+rax+00h]
0x18001325c  test    eax, eax
0x18001325e  js      short loc_180013289
0x180013260  mov     rbx, [rsp+48h+ppunkMarshal]
0x180013265  mov     rax, [rbx]
0x180013268  mov     rdi, [rax]
0x18001326b  mov     rcx, r14
0x18001326e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013273  mov     r8, r14
0x180013276  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18001327d  mov     rcx, rbx
0x180013280  mov     rax, rdi
0x180013283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013288  nop
0x180013289  lea     rcx, [rsp+48h+ppunkMarshal]
0x18001328e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013293  mov     rax, rsi
0x180013296  add     rsp, 28h
0x18001329a  pop     r14
0x18001329c  pop     rdi
0x18001329d  pop     rsi
0x18001329e  pop     rbx
0x18001329f  retn
```
