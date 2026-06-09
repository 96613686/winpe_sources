# CADMCOMW::CImpIConnectionPointContainer::FindConnectionPoint(_GUID const &,IConnectionPoint * *)

- ea: `0x18000c440`
- end: `0x18000c48f`
- name: `?FindConnectionPoint@CImpIConnectionPointContainer@CADMCOMW@@UEAAJAEBU_GUID@@PEAPEAUIConnectionPoint@@@Z`
- size: `79`
- prototype: `__int64 __fastcall(CADMCOMW::CImpIConnectionPointContainer *__hidden this, const struct _GUID *, struct IConnectionPoint **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000c440`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::CImpIConnectionPointContainer::FindConnectionPoint(
        CADMCOMW::CImpIConnectionPointContainer *this,
        const struct _GUID *a2,
        struct IConnectionPoint **a3)
{
  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  if ( *(_OWORD *)&IID_IMSAdminBaseSink_W == *(_OWORD *)a2 )
    return (**(__int64 (__fastcall ***)(__int64, GUID *))(*((_QWORD *)this + 1) + 840LL))(
             *((_QWORD *)this + 1) + 840LL,
             &IID_IConnectionPoint);
  else
    return 2147746304LL;
}

```

## disassembly

```asm
0x18000c440  test    r8, r8
0x18000c443  jnz     short loc_18000C44C
0x18000c445  mov     eax, 80070057h
0x18000c44a  jmp     short locret_18000C48E
0x18000c44c  mov     qword ptr [r8], 0
0x18000c453  mov     rax, qword ptr cs:IID_IMSAdminBaseSink_W.Data1
0x18000c45a  cmp     rax, [rdx]
0x18000c45d  jnz     short loc_18000C489
0x18000c45f  mov     rax, qword ptr cs:IID_IMSAdminBaseSink_W.Data4
0x18000c466  cmp     rax, [rdx+8]
0x18000c46a  jnz     short loc_18000C489
0x18000c46c  mov     rcx, [rcx+8]
0x18000c470  lea     rdx, IID_IConnectionPoint
0x18000c477  add     rcx, 348h
0x18000c47e  mov     rax, [rcx]
0x18000c481  mov     rax, [rax]
0x18000c484  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000c489  mov     eax, 80040200h
0x18000c48e  retn
```
