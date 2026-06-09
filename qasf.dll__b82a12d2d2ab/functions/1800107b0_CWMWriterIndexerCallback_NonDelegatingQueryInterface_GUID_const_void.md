# CWMWriterIndexerCallback::NonDelegatingQueryInterface(_GUID const &,void * *)

- ea: `0x1800107b0`
- end: `0x180010808`
- name: `?NonDelegatingQueryInterface@CWMWriterIndexerCallback@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `88`
- prototype: `__int64 __fastcall(CWMWriterIndexerCallback *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006e78`
- `0x1800107b0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriterIndexerCallback::NonDelegatingQueryInterface(
        CWMWriterIndexerCallback *this,
        const struct _GUID *a2,
        void **a3)
{
  void *v3; // rcx

  if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_IWMStatusCallback.Data1
    || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_IWMStatusCallback.Data4 )
  {
    return CUnknown::NonDelegatingQueryInterface(this, a2, a3);
  }
  v3 = (void *)(((unsigned __int64)this + 24) & -(__int64)(this != 0));
  if ( !a3 )
    return 2147500035LL;
  *a3 = v3;
  (*(void (__fastcall **)(void *))(*(_QWORD *)v3 + 8LL))(v3);
  return 0;
}

```

## disassembly

```asm
0x1800107b0  sub     rsp, 28h
0x1800107b4  mov     rax, [rdx]
0x1800107b7  cmp     rax, qword ptr cs:IID_IWMStatusCallback.Data1
0x1800107be  jnz     short loc_1800107FF
0x1800107c0  mov     rax, [rdx+8]
0x1800107c4  cmp     rax, qword ptr cs:IID_IWMStatusCallback.Data4
0x1800107cb  jnz     short loc_1800107FF
0x1800107cd  lea     rax, [rcx+18h]
0x1800107d1  neg     rcx
0x1800107d4  sbb     rcx, rcx
0x1800107d7  and     rcx, rax
0x1800107da  test    r8, r8
0x1800107dd  jnz     short loc_1800107E9
0x1800107df  mov     eax, 80004003h
0x1800107e4  add     rsp, 28h
0x1800107e8  retn
0x1800107e9  mov     [r8], rcx
0x1800107ec  mov     rax, [rcx]
0x1800107ef  mov     rax, [rax+8]
0x1800107f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107f8  xor     eax, eax
0x1800107fa  add     rsp, 28h
0x1800107fe  retn
0x1800107ff  add     rsp, 28h
0x180010803  jmp     ?NonDelegatingQueryInterface@CUnknown@@UEAAJAEBU_GUID@@PEAPEAX@Z; CUnknown::NonDelegatingQueryInterface(_GUID const &,void * *)
```
