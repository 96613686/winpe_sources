# CMediaBufferOnIMediaSample::CServiceProviderImpl::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x180017f80`
- end: `0x180017fc8`
- name: `?QueryService@CServiceProviderImpl@CMediaBufferOnIMediaSample@@EEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `72`
- prototype: `__int64 __fastcall(CMediaBufferOnIMediaSample::CServiceProviderImpl *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180017f80`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CMediaBufferOnIMediaSample::CServiceProviderImpl::QueryService(
        CMediaBufferOnIMediaSample::CServiceProviderImpl *this,
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
    v5 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*((_QWORD *)this + 1);
    if ( v5 )
      return (**v5)(v5, a3, a4);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180017f80  mov     r10, r8
0x180017f83  test    r9, r9
0x180017f86  jnz     short loc_180017F8F
0x180017f88  mov     eax, 80004003h
0x180017f8d  jmp     short locret_180017FC7
0x180017f8f  mov     rax, [rdx]
0x180017f92  cmp     rax, qword ptr cs:IID_IMediaSample.Data1
0x180017f99  jnz     short loc_180017FC2
0x180017f9b  mov     rax, [rdx+8]
0x180017f9f  cmp     rax, qword ptr cs:IID_IMediaSample.Data4
0x180017fa6  jnz     short loc_180017FC2
0x180017fa8  mov     rcx, [rcx+8]
0x180017fac  test    rcx, rcx
0x180017faf  jz      short loc_180017FC2
0x180017fb1  mov     rax, [rcx]
0x180017fb4  mov     r8, r9
0x180017fb7  mov     rdx, r10
0x180017fba  mov     rax, [rax]
0x180017fbd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180017fc2  mov     eax, 80004005h
0x180017fc7  retn
```
