# CGenericClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004670`
- end: `0x1800046f4`
- name: `?CreateInstance@CGenericClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `132`
- prototype: `__int64 __fastcall(CGenericClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004670`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CGenericClassFactory::CreateInstance(
        CGenericClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v6; // ebx
  __int64 (__fastcall *v7)(__int64 *); // rax
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    return (unsigned int)-2147221232;
  }
  else
  {
    v7 = (__int64 (__fastcall *)(__int64 *))*((_QWORD *)this + 2);
    v9 = 0;
    v6 = v7(&v9);
    if ( v6 >= 0 )
    {
      v6 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v9)(v9, a3, a4);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180004670  mov     [rsp+arg_0], rbx
0x180004675  mov     [rsp+arg_10], rsi
0x18000467a  push    rdi
0x18000467b  sub     rsp, 20h
0x18000467f  mov     qword ptr [r9], 0
0x180004686  mov     rdi, r9
0x180004689  mov     rsi, r8
0x18000468c  mov     rax, rcx
0x18000468f  test    rdx, rdx
0x180004692  jz      short loc_18000469B
0x180004694  mov     ebx, 80040110h
0x180004699  jmp     short loc_1800046E1
0x18000469b  mov     rax, [rax+10h]
0x18000469f  lea     rcx, [rsp+28h+arg_8]
0x1800046a4  mov     [rsp+28h+arg_8], 0
0x1800046ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046b2  mov     ebx, eax
0x1800046b4  test    eax, eax
0x1800046b6  js      short loc_1800046E1
0x1800046b8  mov     rcx, [rsp+28h+arg_8]
0x1800046bd  mov     r8, rdi
0x1800046c0  mov     rdx, rsi
0x1800046c3  mov     rax, [rcx]
0x1800046c6  mov     rax, [rax]
0x1800046c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ce  mov     rcx, [rsp+28h+arg_8]
0x1800046d3  mov     ebx, eax
0x1800046d5  mov     rax, [rcx]
0x1800046d8  mov     rax, [rax+10h]
0x1800046dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046e1  mov     rsi, [rsp+28h+arg_10]
0x1800046e6  mov     eax, ebx
0x1800046e8  mov     rbx, [rsp+28h+arg_0]
0x1800046ed  add     rsp, 20h
0x1800046f1  pop     rdi
0x1800046f2  retn
```
