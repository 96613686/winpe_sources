# ATL::CComTypeInfoHolder::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x18000efb4`
- end: `0x18000f025`
- name: `?GetTypeInfo@CComTypeInfoHolder@ATL@@QEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `113`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, unsigned int, unsigned int, struct ITypeInfo **)`
- caller_count: `18`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e8c0`
- `0x18000edc0`
- `0x18000ede0`
- `0x18000ee00`
- `0x18000ee20`
- `0x18000ee40`
- `0x18000ee60`
- `0x18000ee80`
- `0x18000eea0`
- `0x18000eec0`
- `0x18000eee0`
- `0x18000ef00`
- `0x18000ef20`
- `0x18000ef40`
- `0x18000ef60`
- `0x18000ef80`
- `0x18000efa0`
- `0x180025e90`

## callees

- `0x18000ec10`
- `0x18000efb4`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTypeInfo(
        ATL::CComTypeInfoHolder *this,
        int a2,
        LCID a3,
        struct ITypeInfo **a4)
{
  unsigned int TI; // ecx
  __int64 v8; // rdx

  if ( a2 )
    return 2147614731LL;
  if ( a4 )
  {
    TI = 0;
    *a4 = 0;
    if ( !*((_QWORD *)this + 3) )
      TI = ATL::CComTypeInfoHolder::GetTI(this, a3);
    *a4 = (struct ITypeInfo *)*((_QWORD *)this + 3);
    v8 = *((_QWORD *)this + 3);
    if ( v8 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8 + 8LL))(*((_QWORD *)this + 3));
      return 0;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return TI;
}

```

## disassembly

```asm
0x18000efb4  mov     [rsp+arg_0], rbx
0x18000efb9  push    rdi
0x18000efba  sub     rsp, 20h
0x18000efbe  mov     rdi, r9
0x18000efc1  mov     rbx, rcx
0x18000efc4  test    edx, edx
0x18000efc6  jz      short loc_18000EFCF
0x18000efc8  mov     eax, 8002000Bh
0x18000efcd  jmp     short loc_18000F01A
0x18000efcf  test    rdi, rdi
0x18000efd2  jnz     short loc_18000EFDB
0x18000efd4  mov     ecx, 80004003h
0x18000efd9  jmp     short loc_18000F018
0x18000efdb  xor     ecx, ecx
0x18000efdd  mov     qword ptr [r9], 0
0x18000efe4  cmp     [rbx+18h], rcx
0x18000efe8  jnz     short loc_18000EFF7
0x18000efea  mov     edx, r8d; lcid
0x18000efed  mov     rcx, rbx; this
0x18000eff0  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000eff5  mov     ecx, eax
0x18000eff7  mov     rax, [rbx+18h]
0x18000effb  mov     [rdi], rax
0x18000effe  mov     rdx, [rbx+18h]
0x18000f002  test    rdx, rdx
0x18000f005  jz      short loc_18000F018
0x18000f007  mov     rax, [rdx]
0x18000f00a  mov     rcx, rdx
0x18000f00d  mov     rax, [rax+8]
0x18000f011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f016  xor     ecx, ecx
0x18000f018  mov     eax, ecx
0x18000f01a  mov     rbx, [rsp+28h+arg_0]
0x18000f01f  add     rsp, 20h
0x18000f023  pop     rdi
0x18000f024  retn
```
