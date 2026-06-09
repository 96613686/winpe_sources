# CDimsJobClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800025e0`
- end: `0x180002660`
- name: `?CreateInstance@CDimsJobClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `128`
- prototype: `__int64 __fastcall(CDimsJobClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x1800025e0`
- `0x180002670`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CDimsJobClassFactory::CreateInstance(
        CDimsJobClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 SingletonObject; // rdi
  unsigned int v7; // ebx
  __int64 result; // rax
  CExcept *v9; // rbx
  CExcept *v10; // [rsp+20h] [rbp-18h] BYREF

  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  try
  {
    SingletonObject = CSingleton<CDimsJobTaskHandler>::GetSingletonObject();
    v7 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))SingletonObject)(SingletonObject, a3, a4);
    if ( SingletonObject )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)SingletonObject + 16LL))(SingletonObject);
    result = v7;
  }
  catch ( CExcept *v10 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
      v9 = v10;
    }
    else
    {
      v9 = v10;
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids,
        *(unsigned int *)v10);
    }
    return *(unsigned int *)v9;
  }
  SingletonObject = CSingleton<CDimsJobTaskHandler>::GetSingletonObject();
}

```

## disassembly

```asm
0x1800025e0  mov     [rsp+arg_0], rbx
0x1800025e5  mov     [rsp+arg_10], rsi
0x1800025ea  push    rdi
0x1800025eb  sub     rsp, 30h
0x1800025ef  mov     rbx, r9
0x1800025f2  mov     rsi, r8
0x1800025f5  mov     qword ptr [r9], 0
0x1800025fc  test    rdx, rdx
0x1800025ff  jnz     short loc_180002645
0x180002601  call    ?GetSingletonObject@?$CSingleton@VCDimsJobTaskHandler@@@@SAPEAVCDimsJobTaskHandler@@XZ; CSingleton<CDimsJobTaskHandler>::GetSingletonObject(void)
0x180002606  mov     rdi, rax
0x180002609  mov     rcx, [rax]
0x18000260c  mov     rax, [rcx]
0x18000260f  mov     r8, rbx
0x180002612  mov     rdx, rsi
0x180002615  mov     rcx, rdi
0x180002618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000261d  mov     ebx, eax
0x18000261f  test    rdi, rdi
0x180002622  jz      short loc_180002633
0x180002624  mov     rcx, [rdi]
0x180002627  mov     rax, [rcx+10h]
0x18000262b  mov     rcx, rdi
0x18000262e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002633  mov     eax, ebx
0x180002635  mov     rbx, [rsp+38h+arg_0]
0x18000263a  mov     rsi, [rsp+38h+arg_10]
0x18000263f  add     rsp, 30h
0x180002643  pop     rdi
0x180002644  retn
0x180002645  mov     eax, 80040110h
0x18000264a  mov     rbx, [rsp+38h+arg_0]
0x18000264f  mov     rsi, [rsp+38h+arg_10]
0x180002654  add     rsp, 30h
0x180002658  pop     rdi
0x180002659  retn
0x18000265a  mov     eax, [rsp+38h+arg_8]
0x18000265e  jmp     short loc_180002635
```
