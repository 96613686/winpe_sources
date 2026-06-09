# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180001b40`
- end: `0x180001bea`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `170`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800019c0`
- `0x180015164`
- `0x18001a6bc`
- `0x1800221f8`
- `0x18002239c`
- `0x1800250dc`
- `0x180026350`
- `0x180026410`

## callees

- `0x180001b40`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180001b72`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180001b72`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  LPUNKNOWN v2; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v4; // rcx
  LPUNKNOWN v5; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v2 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v4 = *((_QWORD *)this + 3);
    if ( v4 )
    {
      *((_QWORD *)this + 3) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(
      v2,
      &GUID_00000003_0000_0000_c000_000000000046,
      (char *)this + 24);
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
0x180001b40  mov     [rsp+arg_8], rbx
0x180001b45  mov     [rsp+arg_10], rbp
0x180001b4a  push    rsi
0x180001b4b  push    rdi
0x180001b4c  push    r14
0x180001b4e  sub     rsp, 20h
0x180001b52  mov     rsi, rcx
0x180001b55  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180001b5c  mov     [rcx], rax
0x180001b5f  xor     r14d, r14d
0x180001b62  mov     [rcx+18h], r14
0x180001b66  mov     [rsp+38h+ppunkMarshal], r14
0x180001b6b  lea     rdx, [rsp+38h+ppunkMarshal]; ppunkMarshal
0x180001b70  xor     ecx, ecx; punkOuter
0x180001b72  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180001b78  test    eax, eax
0x180001b7a  js      short loc_180001BB8
0x180001b7c  mov     rbx, [rsp+38h+ppunkMarshal]
0x180001b81  mov     rax, [rbx]
0x180001b84  mov     rbp, [rax]
0x180001b87  mov     rcx, [rsi+18h]
0x180001b8b  test    rcx, rcx
0x180001b8e  jz      short loc_180001BA1
0x180001b90  mov     [rsi+18h], r14
0x180001b94  mov     rdx, [rcx]
0x180001b97  mov     rax, [rdx+10h]
0x180001b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ba0  nop
0x180001ba1  lea     r8, [rsi+18h]
0x180001ba5  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180001bac  mov     rcx, rbx
0x180001baf  mov     rax, rbp
0x180001bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bb7  nop
0x180001bb8  mov     rcx, [rsp+38h+ppunkMarshal]
0x180001bbd  test    rcx, rcx
0x180001bc0  jz      short loc_180001BD4
0x180001bc2  mov     [rsp+38h+ppunkMarshal], r14
0x180001bc7  mov     rax, [rcx]
0x180001bca  mov     rax, [rax+10h]
0x180001bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bd3  nop
0x180001bd4  mov     rax, rsi
0x180001bd7  mov     rbx, [rsp+38h+arg_8]
0x180001bdc  mov     rbp, [rsp+38h+arg_10]
0x180001be1  add     rsp, 20h
0x180001be5  pop     r14
0x180001be7  pop     rdi
0x180001be8  pop     rsi
0x180001be9  retn
```
