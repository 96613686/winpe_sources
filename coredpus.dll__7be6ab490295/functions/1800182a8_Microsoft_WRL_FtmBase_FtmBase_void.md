# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x1800182a8`
- end: `0x180018335`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `141`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016ac8`

## callees

- `0x180011d6c`
- `0x1800182a8`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800182e4`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800182e4`

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
0x1800182a8  push    rbx
0x1800182aa  push    rsi
0x1800182ab  push    rdi
0x1800182ac  push    r14
0x1800182ae  sub     rsp, 28h
0x1800182b2  mov     rsi, rcx
0x1800182b5  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800182bc  mov     [rcx], rax
0x1800182bf  lea     r14, [rcx+18h]
0x1800182c3  mov     qword ptr [r14], 0
0x1800182ca  mov     [rsp+48h+ppunkMarshal], 0
0x1800182d3  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800182d8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800182dd  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800182e2  xor     ecx, ecx; punkOuter
0x1800182e4  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800182eb  nop     dword ptr [rax+rax+00h]
0x1800182f0  test    eax, eax
0x1800182f2  js      short loc_18001831D
0x1800182f4  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800182f9  mov     rax, [rbx]
0x1800182fc  mov     rdi, [rax]
0x1800182ff  mov     rcx, r14
0x180018302  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018307  mov     r8, r14
0x18001830a  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180018311  mov     rcx, rbx
0x180018314  mov     rax, rdi
0x180018317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001831c  nop
0x18001831d  lea     rcx, [rsp+48h+ppunkMarshal]
0x180018322  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018327  mov     rax, rsi
0x18001832a  add     rsp, 28h
0x18001832e  pop     r14
0x180018330  pop     rdi
0x180018331  pop     rsi
0x180018332  pop     rbx
0x180018333  retn
```
