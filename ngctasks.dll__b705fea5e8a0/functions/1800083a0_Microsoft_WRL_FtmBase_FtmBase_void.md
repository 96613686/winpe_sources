# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x1800083a0`
- end: `0x180008432`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `146`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800082fc`

## callees

- `0x1800083a0`
- `0x18000b33c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800083e3`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800083e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+48h] [rbp+10h] BYREF

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
0x1800083a0  mov     r11, rsp
0x1800083a3  mov     [r11+18h], rbx
0x1800083a7  mov     [r11+8], rcx
0x1800083ab  push    rsi
0x1800083ac  push    rdi
0x1800083ad  push    r14
0x1800083af  sub     rsp, 20h
0x1800083b3  mov     rsi, rcx
0x1800083b6  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800083bd  mov     [rcx], rax
0x1800083c0  lea     r14, [rcx+18h]
0x1800083c4  mov     qword ptr [r14], 0
0x1800083cb  mov     qword ptr [r11+10h], 0
0x1800083d3  lea     rcx, [r11+10h]
0x1800083d7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800083dc  lea     rdx, [rsp+38h+ppunkMarshal]; ppunkMarshal
0x1800083e1  xor     ecx, ecx; punkOuter
0x1800083e3  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800083e9  test    eax, eax
0x1800083eb  js      short loc_180008416
0x1800083ed  mov     rbx, [rsp+38h+ppunkMarshal]
0x1800083f2  mov     rax, [rbx]
0x1800083f5  mov     rdi, [rax]
0x1800083f8  mov     rcx, r14
0x1800083fb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180008400  mov     r8, r14
0x180008403  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000840a  mov     rcx, rbx
0x18000840d  mov     rax, rdi
0x180008410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008415  nop
0x180008416  lea     rcx, [rsp+38h+ppunkMarshal]
0x18000841b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180008420  nop
0x180008421  mov     rax, rsi
0x180008424  mov     rbx, [rsp+38h+arg_10]
0x180008429  add     rsp, 20h
0x18000842d  pop     r14
0x18000842f  pop     rdi
0x180008430  pop     rsi
0x180008431  retn
```
