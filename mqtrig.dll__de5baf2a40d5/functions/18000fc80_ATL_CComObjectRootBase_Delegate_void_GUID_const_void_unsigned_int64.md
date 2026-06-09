# ATL::CComObjectRootBase::_Delegate(void *,_GUID const &,void * *,unsigned __int64)

- ea: `0x18000fc80`
- end: `0x18000fca2`
- name: `?_Delegate@CComObjectRootBase@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX_K@Z`
- size: `34`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, void **, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000fc80`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectRootBase::_Delegate(char *a1, const struct _GUID *a2, void **a3, __int64 a4)
{
  __int64 (__fastcall ***v4)(_QWORD, const struct _GUID *, void **); // rcx
  __int64 result; // rax

  v4 = *(__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))&a1[a4];
  result = 2147500034LL;
  if ( v4 )
    return (**v4)(v4, a2, a3);
  return result;
}

```

## disassembly

```asm
0x18000fc80  sub     rsp, 28h
0x18000fc84  mov     rcx, [rcx+r9]
0x18000fc88  mov     eax, 80004002h
0x18000fc8d  test    rcx, rcx
0x18000fc90  jz      short loc_18000FC9D
0x18000fc92  mov     rax, [rcx]
0x18000fc95  mov     rax, [rax]
0x18000fc98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc9d  add     rsp, 28h
0x18000fca1  retn
```
