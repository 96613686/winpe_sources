# CPackage::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a1e0`
- end: `0x18000a23c`
- name: `?QueryInterface@CPackage@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `92`
- prototype: `HRESULT __fastcall(CPackage *this, const struct _GUID *, void **)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a250`
- `0x18000a260`
- `0x18000a270`
- `0x18000a280`
- `0x18000a290`
- `0x18000a2a0`
- `0x18000a2b0`
- `0x18000a2c0`
- `0x18000a2d0`
- `0x18000a2e0`

## callees

- `0x18000a1e0`
- `0x18000e010`

## import_xrefs

- `SHLWAPI!__imp_QISearch` at `0x18000a205`
- `SHLWAPI!__imp_QISearch` at `0x18000a205`

## pseudocode

```c
HRESULT __fastcall CPackage::QueryInterface(CPackage *this, const struct _GUID *a2, void **a3)
{
  HRESULT result; // eax
  __int64 (__fastcall ***v7)(_QWORD, const struct _GUID *, void **); // rcx

  result = QISearch(this, &pqit, a2, a3);
  if ( result < 0 )
  {
    v7 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*((_QWORD *)this + 33);
    if ( v7 )
      return (**v7)(v7, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x18000a1e0  mov     [rsp+arg_0], rbx
0x18000a1e5  mov     [rsp+arg_8], rsi
0x18000a1ea  push    rdi
0x18000a1eb  sub     rsp, 20h
0x18000a1ef  mov     rdi, r8
0x18000a1f2  mov     r9, r8; ppv
0x18000a1f5  mov     r8, rdx; riid
0x18000a1f8  mov     rsi, rdx
0x18000a1fb  lea     rdx, pqit; pqit
0x18000a202  mov     rbx, rcx
0x18000a205  call    cs:__imp_QISearch
0x18000a20b  test    eax, eax
0x18000a20d  jns     short loc_18000A22C
0x18000a20f  mov     rcx, [rbx+108h]
0x18000a216  test    rcx, rcx
0x18000a219  jz      short loc_18000A22C
0x18000a21b  mov     rax, [rcx]
0x18000a21e  mov     r8, rdi
0x18000a221  mov     rdx, rsi
0x18000a224  mov     rax, [rax]
0x18000a227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a22c  mov     rbx, [rsp+28h+arg_0]
0x18000a231  mov     rsi, [rsp+28h+arg_8]
0x18000a236  add     rsp, 20h
0x18000a23a  pop     rdi
0x18000a23b  retn
```
