# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800079c0`
- end: `0x180007ab5`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `245`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800079c0`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 result; // rax
  __int64 v7; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  _QWORD *v10; // rcx
  __int64 v11; // rax
  int v12; // [rsp+48h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2
    && (*(_QWORD *)&a3->Data1 != *(_QWORD *)&IID_IUnknown.Data1 || *(_QWORD *)a3->Data4 != *(_QWORD *)IID_IUnknown.Data4) )
  {
    return 2147500034LL;
  }
  v7 = *((_QWORD *)this + 1);
  v12 = 0;
  v8 = (_QWORD *)(*(__int64 (__fastcall **)(struct IUnknown *, int *))(v7 + 16))(a2, &v12);
  v9 = v8;
  if ( v8 )
  {
    v10 = v8;
    v11 = *v8;
    if ( v12 >= 0 )
    {
      (*(void (__fastcall **)(_QWORD *))(v11 + 8))(v10);
      v12 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v9)(v9, a3, a4);
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    }
    else
    {
      (*(void (__fastcall **)(_QWORD *, __int64))(v11 + 24))(v10, 1);
      *a4 = 0;
    }
    return (unsigned int)v12;
  }
  else
  {
    *a4 = 0;
    result = (unsigned int)v12;
    if ( v12 >= 0 )
      return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800079c0  mov     [rsp+arg_0], rbx
0x1800079c5  mov     [rsp+arg_8], rsi
0x1800079ca  push    rdi
0x1800079cb  sub     rsp, 20h
0x1800079cf  mov     rsi, r8
0x1800079d2  mov     r8, rdx
0x1800079d5  mov     rbx, r9
0x1800079d8  test    r9, r9
0x1800079db  jnz     short loc_1800079E7
0x1800079dd  mov     eax, 80004003h
0x1800079e2  jmp     loc_180007AA5
0x1800079e7  mov     qword ptr [r9], 0
0x1800079ee  test    r8, r8
0x1800079f1  jz      short loc_180007A16
0x1800079f3  mov     rax, [rsi]
0x1800079f6  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800079fd  jnz     short loc_180007A0C
0x1800079ff  mov     rax, [rsi+8]
0x180007a03  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180007a0a  jz      short loc_180007A16
0x180007a0c  mov     eax, 80004002h
0x180007a11  jmp     loc_180007AA5
0x180007a16  mov     rax, [rcx+8]
0x180007a1a  lea     rdx, [rsp+28h+arg_18]
0x180007a1f  mov     [rsp+28h+arg_18], 0
0x180007a27  mov     rcx, r8
0x180007a2a  mov     rax, [rax+10h]
0x180007a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a33  mov     rdi, rax
0x180007a36  test    rax, rax
0x180007a39  jnz     short loc_180007A4D
0x180007a3b  mov     [rbx], rax
0x180007a3e  mov     eax, [rsp+28h+arg_18]
0x180007a42  test    eax, eax
0x180007a44  js      short loc_180007AA5
0x180007a46  mov     eax, 8007000Eh
0x180007a4b  jmp     short loc_180007AA5
0x180007a4d  cmp     [rsp+28h+arg_18], 0
0x180007a52  mov     rcx, rdi
0x180007a55  mov     rax, [rax]
0x180007a58  jge     short loc_180007A71
0x180007a5a  mov     rax, [rax+18h]
0x180007a5e  mov     edx, 1
0x180007a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a68  mov     qword ptr [rbx], 0
0x180007a6f  jmp     short loc_180007AA1
0x180007a71  mov     rax, [rax+8]
0x180007a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a7a  mov     rax, [rdi]
0x180007a7d  mov     r8, rbx
0x180007a80  mov     rdx, rsi
0x180007a83  mov     rcx, rdi
0x180007a86  mov     rax, [rax]
0x180007a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a8e  mov     [rsp+28h+arg_18], eax
0x180007a92  mov     rcx, rdi
0x180007a95  mov     rax, [rdi]
0x180007a98  mov     rax, [rax+10h]
0x180007a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aa1  mov     eax, [rsp+28h+arg_18]
0x180007aa5  mov     rbx, [rsp+28h+arg_0]
0x180007aaa  mov     rsi, [rsp+28h+arg_8]
0x180007aaf  add     rsp, 20h
0x180007ab3  pop     rdi
0x180007ab4  retn
```
