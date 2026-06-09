# CAssociationReadCallback::QueryInterface(_GUID const &,void * *)

- ea: `0x140018370`
- end: `0x1400183f0`
- name: `?QueryInterface@CAssociationReadCallback@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `128`
- prototype: `__int64 __fastcall(CAssociationReadCallback *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140018370`
- `0x14001c010`

## pseudocode

```c
__int64 __fastcall CAssociationReadCallback::QueryInterface(
        CAssociationReadCallback *this,
        const struct _GUID *a2,
        void **a3)
{
  unsigned int v5; // ebx

  if ( a3 )
  {
    v5 = 0;
    *a3 = 0;
    if ( *(_OWORD *)&GUID_00000000_0000_0000_c000_000000000046 == *(_OWORD *)a2
      || *(_QWORD *)&GUID_191eda9f_79d1_4f36_9cbf_16dfd24ae70c.Data1 == *(_QWORD *)&a2->Data1
      && *(_QWORD *)GUID_191eda9f_79d1_4f36_9cbf_16dfd24ae70c.Data4 == *(_QWORD *)a2->Data4 )
    {
      (*(void (__fastcall **)(CAssociationReadCallback *))(*(_QWORD *)this + 8LL))(this);
      *a3 = this;
    }
    else
    {
      return (unsigned int)-2147467262;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x140018370  mov     [rsp+arg_0], rbx
0x140018375  mov     [rsp+arg_8], rsi
0x14001837a  push    rdi
0x14001837b  sub     rsp, 20h
0x14001837f  mov     rsi, r8
0x140018382  mov     rdi, rcx
0x140018385  test    r8, r8
0x140018388  jz      short loc_1400183D9
0x14001838a  xor     ebx, ebx
0x14001838c  mov     [r8], rbx
0x14001838f  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x140018396  cmp     rax, [rdx]
0x140018399  jnz     short loc_1400183A8
0x14001839b  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1400183a2  cmp     rax, [rdx+8]
0x1400183a6  jz      short loc_1400183C1
0x1400183a8  mov     rax, qword ptr cs:_GUID_191eda9f_79d1_4f36_9cbf_16dfd24ae70c.Data1
0x1400183af  cmp     rax, [rdx]
0x1400183b2  jnz     short loc_1400183D2
0x1400183b4  mov     rax, qword ptr cs:_GUID_191eda9f_79d1_4f36_9cbf_16dfd24ae70c.Data4
0x1400183bb  cmp     rax, [rdx+8]
0x1400183bf  jnz     short loc_1400183D2
0x1400183c1  mov     rax, [rcx]
0x1400183c4  mov     rax, [rax+8]
0x1400183c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400183cd  mov     [rsi], rdi
0x1400183d0  jmp     short loc_1400183DE
0x1400183d2  mov     ebx, 80004002h
0x1400183d7  jmp     short loc_1400183DE
0x1400183d9  mov     ebx, 80070057h
0x1400183de  mov     rsi, [rsp+28h+arg_8]
0x1400183e3  mov     eax, ebx
0x1400183e5  mov     rbx, [rsp+28h+arg_0]
0x1400183ea  add     rsp, 20h
0x1400183ee  pop     rdi
0x1400183ef  retn
```
