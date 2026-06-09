# Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream>::Attach(CMarshaledInterface::CMarshalStream *)

- ea: `0x1800073e0`
- end: `0x180007412`
- name: `?Attach@?$ComPtr@VCMarshalStream@CMarshaledInterface@@@WRL@Microsoft@@QEAAXPEAVCMarshalStream@CMarshaledInterface@@@Z`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006c5c`
- `0x18000a640`

## callees

- `0x1800073e0`
- `0x18001a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream>::Attach(__int64 *a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 result; // rax

  v4 = *a1;
  if ( v4 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *a1 = a2;
  return result;
}

```

## disassembly

```asm
0x1800073e0  mov     [rsp+arg_0], rbx
0x1800073e5  push    rdi
0x1800073e6  sub     rsp, 20h
0x1800073ea  mov     rbx, rcx
0x1800073ed  mov     rdi, rdx
0x1800073f0  mov     rcx, [rcx]
0x1800073f3  test    rcx, rcx
0x1800073f6  jz      short loc_180007404
0x1800073f8  mov     rax, [rcx]
0x1800073fb  mov     rax, [rax+10h]
0x1800073ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007404  mov     [rbx], rdi
0x180007407  mov     rbx, [rsp+28h+arg_0]
0x18000740c  add     rsp, 20h
0x180007410  pop     rdi
0x180007411  retn
```
