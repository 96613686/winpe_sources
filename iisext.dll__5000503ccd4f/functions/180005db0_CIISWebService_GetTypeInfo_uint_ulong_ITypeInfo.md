# CIISWebService::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180005db0`
- end: `0x180005dc9`
- name: `?GetTypeInfo@CIISWebService@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `25`
- prototype: `__int64 __fastcall(CIISWebService *__hidden this, unsigned int, unsigned int, struct ITypeInfo **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISWebService::GetTypeInfo(CIISWebService *this, __int64 a2, __int64 a3, struct ITypeInfo **a4)
{
  return (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, struct ITypeInfo **))(**((_QWORD **)this + 7) + 32LL))(
           *((_QWORD *)this + 7),
           a2,
           a3,
           a4);
}

```

## disassembly

```asm
0x180005db0  sub     rsp, 38h
0x180005db4  mov     rcx, [rcx+38h]
0x180005db8  mov     rax, [rcx]
0x180005dbb  mov     rax, [rax+20h]
0x180005dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dc4  add     rsp, 38h
0x180005dc8  retn
```
