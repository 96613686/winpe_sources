# CIISWebService::PrivateGetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180006140`
- end: `0x18000616d`
- name: `?PrivateGetIDsOfNames@CIISWebService@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `45`
- prototype: `__int64 __fastcall(CIISWebService *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, unsigned int, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISWebService::PrivateGetIDsOfNames(
        CIISWebService *this,
        const struct _GUID *a2,
        unsigned __int16 **a3)
{
  return (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *, unsigned __int16 **))(**((_QWORD **)this + 8) + 16LL))(
           *((_QWORD *)this + 8),
           a2,
           a3);
}

```

## disassembly

```asm
0x180006140  sub     rsp, 48h
0x180006144  mov     r10, [rsp+48h+arg_28]
0x180006149  mov     rcx, [rcx+40h]
0x18000614d  mov     [rsp+48h+var_20], r10
0x180006152  mov     r10d, [rsp+48h+arg_20]
0x180006157  mov     [rsp+48h+var_28], r10d
0x18000615c  mov     rax, [rcx]
0x18000615f  mov     rax, [rax+10h]
0x180006163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006168  add     rsp, 48h
0x18000616c  retn
```
