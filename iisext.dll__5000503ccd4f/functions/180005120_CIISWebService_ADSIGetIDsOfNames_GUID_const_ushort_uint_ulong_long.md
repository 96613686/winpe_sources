# CIISWebService::ADSIGetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180005120`
- end: `0x18000514d`
- name: `?ADSIGetIDsOfNames@CIISWebService@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `45`
- prototype: `__int64 __fastcall(CIISWebService *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, unsigned int, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISWebService::ADSIGetIDsOfNames(
        CIISWebService *this,
        const struct _GUID *a2,
        unsigned __int16 **a3)
{
  return (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *, unsigned __int16 **))(**((_QWORD **)this + 9) + 16LL))(
           *((_QWORD *)this + 9),
           a2,
           a3);
}

```

## disassembly

```asm
0x180005120  sub     rsp, 48h
0x180005124  mov     r10, [rsp+48h+arg_28]
0x180005129  mov     rcx, [rcx+48h]
0x18000512d  mov     [rsp+48h+var_20], r10
0x180005132  mov     r10d, [rsp+48h+arg_20]
0x180005137  mov     [rsp+48h+var_28], r10d
0x18000513c  mov     rax, [rcx]
0x18000513f  mov     rax, [rax+10h]
0x180005143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005148  add     rsp, 48h
0x18000514c  retn
```
