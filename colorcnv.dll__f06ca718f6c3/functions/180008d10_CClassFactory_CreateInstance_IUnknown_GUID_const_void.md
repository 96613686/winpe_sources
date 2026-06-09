# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180008d10`
- end: `0x180008e0c`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `252`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f070`

## callees

- `0x180008d10`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  _QWORD *v9; // rcx
  __int64 v10; // rax
  __int64 result; // rax
  __int64 v12; // rax
  int v13; // [rsp+48h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
  {
    v12 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v12 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( v12 )
      return 2147500034LL;
  }
  v6 = *((_QWORD *)this + 1);
  v13 = 0;
  v7 = (_QWORD *)(*(__int64 (__fastcall **)(struct IUnknown *, int *))(v6 + 8))(a2, &v13);
  v8 = v7;
  if ( v7 )
  {
    v9 = v7;
    v10 = *v7;
    if ( v13 < 0 )
    {
      (*(void (__fastcall **)(_QWORD *, __int64))(v10 + 24))(v9, 1);
    }
    else
    {
      (*(void (__fastcall **)(_QWORD *))(v10 + 8))(v9);
      v13 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v8)(v8, a3, a4);
      (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
    }
    return (unsigned int)v13;
  }
  else
  {
    result = (unsigned int)v13;
    if ( v13 >= 0 )
      return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180008d10  mov     [rsp+arg_0], rbx
0x180008d15  mov     [rsp+arg_8], rsi
0x180008d1a  push    rdi
0x180008d1b  sub     rsp, 20h
0x180008d1f  mov     rsi, r8
0x180008d22  mov     r8, rdx
0x180008d25  mov     rdi, r9
0x180008d28  test    r9, r9
0x180008d2b  jz      loc_180008DBF
0x180008d31  mov     qword ptr [r9], 0
0x180008d38  test    rdx, rdx
0x180008d3b  jnz     loc_180008DC6
0x180008d41  mov     rax, [rcx+8]
0x180008d45  lea     rdx, [rsp+28h+arg_18]
0x180008d4a  mov     [rsp+28h+arg_18], 0
0x180008d52  mov     rcx, r8
0x180008d55  mov     rax, [rax+8]
0x180008d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d5e  mov     rbx, rax
0x180008d61  test    rax, rax
0x180008d64  jz      loc_180008DED
0x180008d6a  cmp     [rsp+28h+arg_18], 0
0x180008d6f  mov     rcx, rbx
0x180008d72  mov     rax, [rax]
0x180008d75  jl      loc_180008DFC
0x180008d7b  mov     rax, [rax+8]
0x180008d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d84  mov     rax, [rbx]
0x180008d87  mov     r8, rdi
0x180008d8a  mov     rdx, rsi
0x180008d8d  mov     rcx, rbx
0x180008d90  mov     rax, [rax]
0x180008d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d98  mov     [rsp+28h+arg_18], eax
0x180008d9c  mov     rcx, rbx
0x180008d9f  mov     rax, [rbx]
0x180008da2  mov     rax, [rax+10h]
0x180008da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dab  mov     eax, [rsp+28h+arg_18]
0x180008daf  mov     rbx, [rsp+28h+arg_0]
0x180008db4  mov     rsi, [rsp+28h+arg_8]
0x180008db9  add     rsp, 20h
0x180008dbd  pop     rdi
0x180008dbe  retn
0x180008dbf  mov     eax, 80004003h
0x180008dc4  jmp     short loc_180008DAF
0x180008dc6  mov     rax, [rsi]
0x180008dc9  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180008dd0  jnz     short loc_180008DDD
0x180008dd2  mov     rax, [rsi+8]
0x180008dd6  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180008ddd  test    rax, rax
0x180008de0  jz      loc_180008D41
0x180008de6  mov     eax, 80004002h
0x180008deb  jmp     short loc_180008DAF
0x180008ded  mov     eax, [rsp+28h+arg_18]
0x180008df1  test    eax, eax
0x180008df3  js      short loc_180008DAF
0x180008df5  mov     eax, 8007000Eh
0x180008dfa  jmp     short loc_180008DAF
0x180008dfc  mov     rax, [rax+18h]
0x180008e00  mov     edx, 1
0x180008e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e0a  jmp     short loc_180008DAB
```
