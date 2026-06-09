# CThisDllClassFactory::QueryInterface(_GUID const &,void * *)

- ea: `0x180011ee0`
- end: `0x180011f40`
- name: `?QueryInterface@CThisDllClassFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `96`
- prototype: `__int64 __fastcall(CThisDllClassFactory *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180011ee0`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CThisDllClassFactory::QueryInterface(CThisDllClassFactory *this, const struct _GUID *a2, void **a3)
{
  __int64 v3; // rax
  __int64 v4; // rax

  v3 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v3 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( !v3 )
    goto LABEL_8;
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IClassFactory.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IClassFactory.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IClassFactory.Data4;
  if ( v4 )
  {
    *a3 = 0;
    return 2147500034LL;
  }
  else
  {
LABEL_8:
    *a3 = this;
    (*(void (__fastcall **)(CThisDllClassFactory *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
}

```

## disassembly

```asm
0x180011ee0  sub     rsp, 28h
0x180011ee4  mov     rax, [rdx]
0x180011ee7  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180011eee  jnz     short loc_180011EFB
0x180011ef0  mov     rax, [rdx+8]
0x180011ef4  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180011efb  test    rax, rax
0x180011efe  jz      short loc_180011F2A
0x180011f00  mov     rax, [rdx]
0x180011f03  sub     rax, qword ptr cs:IID_IClassFactory.Data1
0x180011f0a  jnz     short loc_180011F17
0x180011f0c  mov     rax, [rdx+8]
0x180011f10  sub     rax, qword ptr cs:IID_IClassFactory.Data4
0x180011f17  test    rax, rax
0x180011f1a  jz      short loc_180011F2A
0x180011f1c  mov     qword ptr [r8], 0
0x180011f23  mov     eax, 80004002h
0x180011f28  jmp     short loc_180011F3B
0x180011f2a  mov     [r8], rcx
0x180011f2d  mov     rax, [rcx]
0x180011f30  mov     rax, [rax+8]
0x180011f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f39  xor     eax, eax
0x180011f3b  add     rsp, 28h
0x180011f3f  retn
```
