# ATL::CComObjectRootBase::_Delegate(void *,_GUID const &,void * *,unsigned __int64)

- ea: `0x1800025c0`
- end: `0x1800025dc`
- name: `?_Delegate@CComObjectRootBase@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX_K@Z`
- size: `28`
- prototype: `__int64 __fastcall(void *, const struct _GUID *, void **, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800025c0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectRootBase::_Delegate(char *a1, const struct _GUID *a2, void **a3, __int64 a4)
{
  __int64 (__fastcall ***v4)(_QWORD, const struct _GUID *, void **); // rcx

  v4 = *(__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))&a1[a4];
  if ( v4 )
    return (**v4)(v4, a2, a3);
  else
    return 2147500034LL;
}

```

## disassembly

```asm
0x1800025c0  mov     rcx, [rcx+r9]
0x1800025c4  test    rcx, rcx
0x1800025c7  jz      short loc_1800025D5
0x1800025c9  mov     rax, [rcx]
0x1800025cc  mov     rax, [rax]
0x1800025cf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800025d4  retn
0x1800025d5  mov     eax, 80004002h
0x1800025da  jmp     short locret_1800025D4
```
