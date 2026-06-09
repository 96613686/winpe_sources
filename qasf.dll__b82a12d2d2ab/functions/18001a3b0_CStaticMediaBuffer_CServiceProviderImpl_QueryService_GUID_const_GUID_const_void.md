# CStaticMediaBuffer::CServiceProviderImpl::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x18001a3b0`
- end: `0x18001a3f8`
- name: `?QueryService@CServiceProviderImpl@CStaticMediaBuffer@@EEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `72`
- prototype: `__int64 __fastcall(CStaticMediaBuffer::CServiceProviderImpl *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18001a3b0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CStaticMediaBuffer::CServiceProviderImpl::QueryService(
        CStaticMediaBuffer::CServiceProviderImpl *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 (__fastcall ***v5)(_QWORD, const struct _GUID *, void **); // rcx

  if ( !a4 )
    return 2147500035LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMediaSample.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IMediaSample.Data4 )
  {
    v5 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*((_QWORD *)this - 1);
    if ( v5 )
      return (**v5)(v5, a3, a4);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18001a3b0  mov     r10, r8
0x18001a3b3  test    r9, r9
0x18001a3b6  jnz     short loc_18001A3BF
0x18001a3b8  mov     eax, 80004003h
0x18001a3bd  jmp     short locret_18001A3F7
0x18001a3bf  mov     rax, [rdx]
0x18001a3c2  cmp     rax, qword ptr cs:IID_IMediaSample.Data1
0x18001a3c9  jnz     short loc_18001A3F2
0x18001a3cb  mov     rax, [rdx+8]
0x18001a3cf  cmp     rax, qword ptr cs:IID_IMediaSample.Data4
0x18001a3d6  jnz     short loc_18001A3F2
0x18001a3d8  mov     rcx, [rcx-8]
0x18001a3dc  test    rcx, rcx
0x18001a3df  jz      short loc_18001A3F2
0x18001a3e1  mov     rax, [rcx]
0x18001a3e4  mov     r8, r9
0x18001a3e7  mov     rdx, r10
0x18001a3ea  mov     rax, [rax]
0x18001a3ed  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3f2  mov     eax, 80004005h
0x18001a3f7  retn
```
