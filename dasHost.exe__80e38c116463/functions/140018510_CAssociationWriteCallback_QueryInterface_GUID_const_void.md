# CAssociationWriteCallback::QueryInterface(_GUID const &,void * *)

- ea: `0x140018510`
- end: `0x140018590`
- name: `?QueryInterface@CAssociationWriteCallback@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `128`
- prototype: `__int64 __fastcall(CAssociationWriteCallback *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140018510`
- `0x14001c010`

## pseudocode

```c
__int64 __fastcall CAssociationWriteCallback::QueryInterface(
        CAssociationWriteCallback *this,
        const struct _GUID *a2,
        void **a3)
{
  unsigned int v5; // ebx

  if ( a3 )
  {
    v5 = 0;
    *a3 = 0;
    if ( *(_OWORD *)&GUID_00000000_0000_0000_c000_000000000046 == *(_OWORD *)a2
      || *(_QWORD *)&GUID_f3a6ff08_0290_4748_8c31_3c937eb2058e.Data1 == *(_QWORD *)&a2->Data1
      && *(_QWORD *)GUID_f3a6ff08_0290_4748_8c31_3c937eb2058e.Data4 == *(_QWORD *)a2->Data4 )
    {
      (*(void (__fastcall **)(CAssociationWriteCallback *))(*(_QWORD *)this + 8LL))(this);
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
0x140018510  mov     [rsp+arg_0], rbx
0x140018515  mov     [rsp+arg_8], rsi
0x14001851a  push    rdi
0x14001851b  sub     rsp, 20h
0x14001851f  mov     rsi, r8
0x140018522  mov     rdi, rcx
0x140018525  test    r8, r8
0x140018528  jz      short loc_140018579
0x14001852a  xor     ebx, ebx
0x14001852c  mov     [r8], rbx
0x14001852f  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x140018536  cmp     rax, [rdx]
0x140018539  jnz     short loc_140018548
0x14001853b  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x140018542  cmp     rax, [rdx+8]
0x140018546  jz      short loc_140018561
0x140018548  mov     rax, qword ptr cs:_GUID_f3a6ff08_0290_4748_8c31_3c937eb2058e.Data1
0x14001854f  cmp     rax, [rdx]
0x140018552  jnz     short loc_140018572
0x140018554  mov     rax, qword ptr cs:_GUID_f3a6ff08_0290_4748_8c31_3c937eb2058e.Data4
0x14001855b  cmp     rax, [rdx+8]
0x14001855f  jnz     short loc_140018572
0x140018561  mov     rax, [rcx]
0x140018564  mov     rax, [rax+8]
0x140018568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001856d  mov     [rsi], rdi
0x140018570  jmp     short loc_14001857E
0x140018572  mov     ebx, 80004002h
0x140018577  jmp     short loc_14001857E
0x140018579  mov     ebx, 80070057h
0x14001857e  mov     rsi, [rsp+28h+arg_8]
0x140018583  mov     eax, ebx
0x140018585  mov     rbx, [rsp+28h+arg_0]
0x14001858a  add     rsp, 20h
0x14001858e  pop     rdi
0x14001858f  retn
```
