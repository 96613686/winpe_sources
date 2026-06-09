# CMQVariant::_setCACLSID(tagCACLSID const &)

- ea: `0x180003ecc`
- end: `0x180003f2d`
- name: `?_setCACLSID@CMQVariant@@AEAAXAEBUtagCACLSID@@@Z`
- size: `97`
- prototype: `void __fastcall(CMQVariant *__hidden this, const struct tagCACLSID *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003f34`
- `0x180016d80`
- `0x180017120`

## callees

- `0x18001722c`
- `0x18002f0a2`

## pseudocode

```c
void __fastcall CMQVariant::_setCACLSID(CMQVariant *this, const struct tagCACLSID *a2)
{
  ULONG cElems; // edi
  void *v5; // rax

  cElems = a2->cElems;
  v5 = MmAllocate(saturated_mul(a2->cElems, 0x10u));
  *((_QWORD *)this + 2) = v5;
  memcpy_0(v5, a2->pElems, 16LL * cElems);
  *((_DWORD *)this + 2) = cElems;
  *(_WORD *)this = 4168;
}

```

## disassembly

```asm
0x180003ecc  mov     [rsp+arg_0], rbx
0x180003ed1  mov     [rsp+arg_8], rsi
0x180003ed6  push    rdi
0x180003ed7  sub     rsp, 20h
0x180003edb  mov     edi, [rdx]
0x180003edd  mov     rsi, rcx
0x180003ee0  mov     rbx, rdx
0x180003ee3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003eea  mov     eax, 10h
0x180003eef  mul     rdi
0x180003ef2  cmovb   rax, rcx
0x180003ef6  mov     rcx, rax; unsigned __int64
0x180003ef9  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180003efe  mov     [rsi+10h], rax
0x180003f02  mov     r8d, edi
0x180003f05  mov     rdx, [rbx+8]; Src
0x180003f09  mov     rcx, rax; void *
0x180003f0c  shl     r8, 4; Size
0x180003f10  call    memcpy_0
0x180003f15  mov     rbx, [rsp+28h+arg_0]
0x180003f1a  mov     [rsi+8], edi
0x180003f1d  mov     word ptr [rsi], 1048h
0x180003f22  mov     rsi, [rsp+28h+arg_8]
0x180003f27  add     rsp, 20h
0x180003f2b  pop     rdi
0x180003f2c  retn
```
