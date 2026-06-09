# CClassFactory::QueryInterface(_GUID const &,void * *)

- ea: `0x180001fc0`
- end: `0x180002018`
- name: `?QueryInterface@CClassFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `88`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001fc0`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall CClassFactory::QueryInterface(CClassFactory *this, const struct _GUID *a2, void **a3)
{
  if ( *(_QWORD *)&IID_IUnknown.Data1 == *(_QWORD *)&a2->Data1 && *(_QWORD *)IID_IUnknown.Data4 == *(_QWORD *)a2->Data4
    || *(_QWORD *)&IID_IClassFactory.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_IClassFactory.Data4 == *(_QWORD *)a2->Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x180001fc0  sub     rsp, 28h
0x180001fc4  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x180001fcb  cmp     rax, [rdx]
0x180001fce  jnz     short loc_180001FDD
0x180001fd0  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x180001fd7  cmp     rax, [rdx+8]
0x180001fdb  jz      short loc_180001FF6
0x180001fdd  mov     rax, qword ptr cs:IID_IClassFactory.Data1
0x180001fe4  cmp     rax, [rdx]
0x180001fe7  jnz     short loc_180002009
0x180001fe9  mov     rax, qword ptr cs:IID_IClassFactory.Data4
0x180001ff0  cmp     rax, [rdx+8]
0x180001ff4  jnz     short loc_180002009
0x180001ff6  mov     [r8], rcx
0x180001ff9  mov     rax, [rcx]
0x180001ffc  mov     rax, [rax+8]
0x180002000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002005  xor     eax, eax
0x180002007  jmp     short loc_180002013
0x180002009  xor     eax, eax
0x18000200b  mov     [r8], rax
0x18000200e  mov     eax, 80004002h
0x180002013  add     rsp, 28h
0x180002017  retn
```
