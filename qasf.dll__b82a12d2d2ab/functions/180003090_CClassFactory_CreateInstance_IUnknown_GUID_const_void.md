# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003090`
- end: `0x180003185`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `245`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003090`
- `0x18001f010`

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
0x180003090  mov     [rsp+arg_0], rbx
0x180003095  mov     [rsp+arg_8], rsi
0x18000309a  push    rdi
0x18000309b  sub     rsp, 20h
0x18000309f  mov     rsi, r8
0x1800030a2  mov     r8, rdx
0x1800030a5  mov     rbx, r9
0x1800030a8  test    r9, r9
0x1800030ab  jnz     short loc_1800030B7
0x1800030ad  mov     eax, 80004003h
0x1800030b2  jmp     loc_180003175
0x1800030b7  mov     qword ptr [r9], 0
0x1800030be  test    r8, r8
0x1800030c1  jz      short loc_1800030E6
0x1800030c3  mov     rax, [rsi]
0x1800030c6  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800030cd  jnz     short loc_1800030DC
0x1800030cf  mov     rax, [rsi+8]
0x1800030d3  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800030da  jz      short loc_1800030E6
0x1800030dc  mov     eax, 80004002h
0x1800030e1  jmp     loc_180003175
0x1800030e6  mov     rax, [rcx+8]
0x1800030ea  lea     rdx, [rsp+28h+arg_18]
0x1800030ef  mov     [rsp+28h+arg_18], 0
0x1800030f7  mov     rcx, r8
0x1800030fa  mov     rax, [rax+10h]
0x1800030fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003103  mov     rdi, rax
0x180003106  test    rax, rax
0x180003109  jnz     short loc_18000311D
0x18000310b  mov     [rbx], rax
0x18000310e  mov     eax, [rsp+28h+arg_18]
0x180003112  test    eax, eax
0x180003114  js      short loc_180003175
0x180003116  mov     eax, 8007000Eh
0x18000311b  jmp     short loc_180003175
0x18000311d  cmp     [rsp+28h+arg_18], 0
0x180003122  mov     rcx, rdi
0x180003125  mov     rax, [rax]
0x180003128  jge     short loc_180003141
0x18000312a  mov     rax, [rax+18h]
0x18000312e  mov     edx, 1
0x180003133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003138  mov     qword ptr [rbx], 0
0x18000313f  jmp     short loc_180003171
0x180003141  mov     rax, [rax+8]
0x180003145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000314a  mov     rax, [rdi]
0x18000314d  mov     r8, rbx
0x180003150  mov     rdx, rsi
0x180003153  mov     rcx, rdi
0x180003156  mov     rax, [rax]
0x180003159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000315e  mov     [rsp+28h+arg_18], eax
0x180003162  mov     rcx, rdi
0x180003165  mov     rax, [rdi]
0x180003168  mov     rax, [rax+10h]
0x18000316c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003171  mov     eax, [rsp+28h+arg_18]
0x180003175  mov     rbx, [rsp+28h+arg_0]
0x18000317a  mov     rsi, [rsp+28h+arg_8]
0x18000317f  add     rsp, 20h
0x180003183  pop     rdi
0x180003184  retn
```
