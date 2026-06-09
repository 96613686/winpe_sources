# CDpSearchProtocol::CreateAccessor(ushort const *,_AUTHENTICATION_INFO *,_INCREMENTAL_ACCESS_INFO *,_ITEM_INFO *,IUrlAccessor * *)

- ea: `0x180003fe0`
- end: `0x180004012`
- name: `?CreateAccessor@CDpSearchProtocol@@UEAAJPEBGPEAU_AUTHENTICATION_INFO@@PEAU_INCREMENTAL_ACCESS_INFO@@PEAU_ITEM_INFO@@PEAPEAUIUrlAccessor@@@Z`
- size: `50`
- prototype: `__int64 __fastcall(CDpSearchProtocol *__hidden this, const unsigned __int16 *, struct _AUTHENTICATION_INFO *, struct _INCREMENTAL_ACCESS_INFO *, struct _ITEM_INFO *, struct IUrlAccessor **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CDpSearchProtocol::CreateAccessor(
        CDpSearchProtocol *this,
        const unsigned __int16 *a2,
        struct _AUTHENTICATION_INFO *a3,
        struct _INCREMENTAL_ACCESS_INFO *a4,
        struct _ITEM_INFO *a5,
        struct IUrlAccessor **a6)
{
  return (*(__int64 (__fastcall **)(CDpSearchProtocol *, const unsigned __int16 *, struct _AUTHENTICATION_INFO *, struct _INCREMENTAL_ACCESS_INFO *, struct _ITEM_INFO *, _QWORD, struct IUrlAccessor **))(*(_QWORD *)this + 56LL))(
           this,
           a2,
           a3,
           a4,
           a5,
           0,
           a6);
}

```

## disassembly

```asm
0x180003fe0  sub     rsp, 48h
0x180003fe4  mov     rax, [rcx]
0x180003fe7  mov     r10, [rsp+48h+arg_28]
0x180003fec  mov     [rsp+48h+var_18], r10
0x180003ff1  mov     r10, [rsp+48h+arg_20]
0x180003ff6  mov     rax, [rax+38h]
0x180003ffa  mov     [rsp+48h+var_20], 0
0x180004003  mov     [rsp+48h+var_28], r10
0x180004008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000400d  add     rsp, 48h
0x180004011  retn
```
