# ATL::CComTypeInfoHolder::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x18000ec84`
- end: `0x18000ecf5`
- name: `?GetTypeInfo@CComTypeInfoHolder@ATL@@QEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `113`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *this, int, LCID, struct ITypeInfo **)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ebf0`
- `0x18000ec10`
- `0x18000ec30`
- `0x18000ec50`
- `0x18000ec70`

## callees

- `0x18000ea78`
- `0x18000ec84`
- `0x180022010`

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
0x18000ec84  mov     [rsp+arg_0], rbx
0x18000ec89  push    rdi
0x18000ec8a  sub     rsp, 20h
0x18000ec8e  mov     rdi, r9
0x18000ec91  mov     rbx, rcx
0x18000ec94  test    edx, edx
0x18000ec96  jz      short loc_18000EC9F
0x18000ec98  mov     eax, 8002000Bh
0x18000ec9d  jmp     short loc_18000ECEA
0x18000ec9f  test    rdi, rdi
0x18000eca2  jnz     short loc_18000ECAB
0x18000eca4  mov     ecx, 80004003h
0x18000eca9  jmp     short loc_18000ECE8
0x18000ecab  xor     ecx, ecx
0x18000ecad  mov     qword ptr [r9], 0
0x18000ecb4  cmp     [rbx+18h], rcx
0x18000ecb8  jnz     short loc_18000ECC7
0x18000ecba  mov     edx, r8d; lcid
0x18000ecbd  mov     rcx, rbx; this
0x18000ecc0  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000ecc5  mov     ecx, eax
0x18000ecc7  mov     rax, [rbx+18h]
0x18000eccb  mov     [rdi], rax
0x18000ecce  mov     rdx, [rbx+18h]
0x18000ecd2  test    rdx, rdx
0x18000ecd5  jz      short loc_18000ECE8
0x18000ecd7  mov     rax, [rdx]
0x18000ecda  mov     rcx, rdx
0x18000ecdd  mov     rax, [rax+8]
0x18000ece1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ece6  xor     ecx, ecx
0x18000ece8  mov     eax, ecx
0x18000ecea  mov     rbx, [rsp+28h+arg_0]
0x18000ecef  add     rsp, 20h
0x18000ecf3  pop     rdi
0x18000ecf4  retn
```
