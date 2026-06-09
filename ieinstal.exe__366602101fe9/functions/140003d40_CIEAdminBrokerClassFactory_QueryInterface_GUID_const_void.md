# CIEAdminBrokerClassFactory::QueryInterface(_GUID const &,void * *)

- ea: `0x140003d40`
- end: `0x140003d9e`
- name: `?QueryInterface@CIEAdminBrokerClassFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `94`
- prototype: `__int64 __fastcall(CIEAdminBrokerClassFactory *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003d40`
- `0x140011010`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerClassFactory::QueryInterface(
        CIEAdminBrokerClassFactory *this,
        const struct _GUID *a2,
        void **a3)
{
  unsigned int v3; // ebx

  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IClassFactory.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IClassFactory.Data4 )
  {
    *a3 = this;
    v3 = 0;
    (*(void (__fastcall **)(CIEAdminBrokerClassFactory *))(*(_QWORD *)this + 8LL))(this);
  }
  else
  {
    *a3 = 0;
    return (unsigned int)-2147467262;
  }
  return v3;
}

```

## disassembly

```asm
0x140003d40  push    rbx
0x140003d42  sub     rsp, 20h
0x140003d46  mov     rax, [rdx]
0x140003d49  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x140003d50  jnz     short loc_140003D5F
0x140003d52  mov     rax, [rdx+8]
0x140003d56  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x140003d5d  jz      short loc_140003D78
0x140003d5f  mov     rax, [rdx]
0x140003d62  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x140003d69  jnz     short loc_140003D8B
0x140003d6b  mov     rax, [rdx+8]
0x140003d6f  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x140003d76  jnz     short loc_140003D8B
0x140003d78  mov     [r8], rcx
0x140003d7b  xor     ebx, ebx
0x140003d7d  mov     rax, [rcx]
0x140003d80  mov     rax, [rax+8]
0x140003d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d89  jmp     short loc_140003D95
0x140003d8b  xor     ebx, ebx
0x140003d8d  mov     [r8], rbx
0x140003d90  mov     ebx, 80004002h
0x140003d95  mov     eax, ebx
0x140003d97  add     rsp, 20h
0x140003d9b  pop     rbx
0x140003d9c  retn
```
