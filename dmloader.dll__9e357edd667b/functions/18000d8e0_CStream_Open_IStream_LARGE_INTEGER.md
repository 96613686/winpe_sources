# CStream::Open(IStream *,_LARGE_INTEGER)

- ea: `0x18000d8e0`
- end: `0x18000d94f`
- name: `?Open@CStream@@QEAAJPEAUIStream@@T_LARGE_INTEGER@@@Z`
- size: `111`
- prototype: `__int64 __fastcall(CStream *__hidden this, struct IStream *, union _LARGE_INTEGER)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ae74`
- `0x18000b81c`

## callees

- `0x18000d8e0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CStream::Open(CStream *this, struct IStream *a2, union _LARGE_INTEGER a3)
{
  __int64 v5; // rcx

  v5 = *((_QWORD *)this + 3);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  *((_QWORD *)this + 3) = a2;
  if ( a2 )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))a2->lpVtbl->Seek)(a2, (union _LARGE_INTEGER)a3.QuadPart, 0, 0);
    ((void (__fastcall *)(struct IStream *))a2->lpVtbl->AddRef)(a2);
  }
  return 0;
}

```

## disassembly

```asm
0x18000d8e0  mov     [rsp+arg_0], rbx
0x18000d8e5  mov     [rsp+arg_8], rsi
0x18000d8ea  push    rdi
0x18000d8eb  sub     rsp, 30h
0x18000d8ef  mov     rsi, rcx
0x18000d8f2  mov     rbx, r8
0x18000d8f5  mov     rcx, [rcx+18h]
0x18000d8f9  mov     rdi, rdx
0x18000d8fc  test    rcx, rcx
0x18000d8ff  jz      short loc_18000D90D
0x18000d901  mov     rax, [rcx]
0x18000d904  mov     rax, [rax+10h]
0x18000d908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d90d  mov     [rsi+18h], rdi
0x18000d911  test    rdi, rdi
0x18000d914  jz      short loc_18000D93D
0x18000d916  mov     rax, [rdi]
0x18000d919  xor     r9d, r9d
0x18000d91c  xor     r8d, r8d
0x18000d91f  mov     rdx, rbx
0x18000d922  mov     rcx, rdi
0x18000d925  mov     rax, [rax+28h]
0x18000d929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d92e  mov     rax, [rdi]
0x18000d931  mov     rcx, rdi
0x18000d934  mov     rax, [rax+8]
0x18000d938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d93d  mov     rbx, [rsp+38h+arg_0]
0x18000d942  xor     eax, eax
0x18000d944  mov     rsi, [rsp+38h+arg_8]
0x18000d949  add     rsp, 30h
0x18000d94d  pop     rdi
0x18000d94e  retn
```
