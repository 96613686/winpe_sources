# sub_1801DFC5C

- ea: `0x1801dfc5c`
- end: `0x1801dfce1`
- name: `sub_1801DFC5C`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801dfb38`
- `0x1801f665c`
- `0x1801f672c`
- `0x1801f67fc`
- `0x18027364c`

## callees

- `0x180048d5c`
- `0x1801dfc5c`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1801dfc98`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1801dfc98`

## pseudocode

```c
_QWORD *__fastcall sub_1801DFC5C(_QWORD *a1)
{
  _QWORD *v1; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  v1 = a1 + 3;
  ppunkMarshal = 0;
  *a1 = off_180285F30;
  a1[3] = 0;
  sub_180048D5C(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    sub_180048D5C(v1);
    ((void (__fastcall *)(LPUNKNOWN, __int64 *, _QWORD *))QueryInterface)(v3, qword_1802BE988, v1);
  }
  sub_180048D5C(&ppunkMarshal);
  return a1;
}

```

## disassembly

```asm
0x1801dfc5c  push    rbx
0x1801dfc5e  push    rsi
0x1801dfc5f  push    rdi
0x1801dfc60  push    r14
0x1801dfc62  sub     rsp, 28h
0x1801dfc66  lea     r14, [rcx+18h]
0x1801dfc6a  mov     [rsp+48h+ppunkMarshal], 0
0x1801dfc73  lea     rax, off_180285F30
0x1801dfc7a  mov     rsi, rcx
0x1801dfc7d  mov     [rcx], rax
0x1801dfc80  lea     rcx, [rsp+48h+ppunkMarshal]
0x1801dfc85  mov     qword ptr [r14], 0
0x1801dfc8c  call    sub_180048D5C
0x1801dfc91  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1801dfc96  xor     ecx, ecx; punkOuter
0x1801dfc98  call    cs:CoCreateFreeThreadedMarshaler
0x1801dfc9e  test    eax, eax
0x1801dfca0  js      short loc_1801DFCCA
0x1801dfca2  mov     rbx, [rsp+48h+ppunkMarshal]
0x1801dfca7  mov     rcx, r14
0x1801dfcaa  mov     rax, [rbx]
0x1801dfcad  mov     rdi, [rax]
0x1801dfcb0  call    sub_180048D5C
0x1801dfcb5  mov     r8, r14
0x1801dfcb8  lea     rdx, qword_1802BE988
0x1801dfcbf  mov     rcx, rbx
0x1801dfcc2  mov     rax, rdi
0x1801dfcc5  call    j__guard_dispatch_icall
0x1801dfcca  lea     rcx, [rsp+48h+ppunkMarshal]
0x1801dfccf  call    sub_180048D5C
0x1801dfcd4  mov     rax, rsi
0x1801dfcd7  add     rsp, 28h
0x1801dfcdb  pop     r14
0x1801dfcdd  pop     rdi
0x1801dfcde  pop     rsi
0x1801dfcdf  pop     rbx
0x1801dfce0  retn
```
