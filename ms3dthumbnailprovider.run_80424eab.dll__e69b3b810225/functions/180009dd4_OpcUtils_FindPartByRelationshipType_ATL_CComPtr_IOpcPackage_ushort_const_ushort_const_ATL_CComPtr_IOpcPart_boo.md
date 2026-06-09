# OpcUtils::FindPartByRelationshipType(ATL::CComPtr<IOpcPackage> &,ushort const *,ushort const *,ATL::CComPtr<IOpcPart> &,bool)

- ea: `0x180009dd4`
- end: `0x180009ea0`
- name: `?FindPartByRelationshipType@OpcUtils@@YAJAEAV?$CComPtr@UIOpcPackage@@@ATL@@PEBG1AEAV?$CComPtr@UIOpcPart@@@3@_N@Z`
- size: `204`
- prototype: `__int64 __fastcall(_QWORD *, __int64, int, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009c98`

## callees

- `0x180009dd4`
- `0x180009ea8`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall OpcUtils::FindPartByRelationshipType(_QWORD *a1, __int64 a2, int a3, _QWORD *a4)
{
  int PartByRelationshipType; // ebx
  int v8; // r8d
  __int64 v10; // [rsp+60h] [rbp+8h] BYREF
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF

  v10 = 0;
  v11 = 0;
  PartByRelationshipType = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 24LL))(*a1, &v11);
  if ( PartByRelationshipType >= 0 )
  {
    PartByRelationshipType = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 32LL))(*a1, &v10);
    if ( PartByRelationshipType >= 0 )
    {
      PartByRelationshipType = OpcUtils::FindPartByRelationshipType(
                                 (unsigned int)&v10,
                                 (unsigned int)&v11,
                                 v8,
                                 a3,
                                 (__int64)a4);
      if ( PartByRelationshipType >= 0 && !*a4 )
        PartByRelationshipType = -2147467259;
    }
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)PartByRelationshipType;
}

```

## disassembly

```asm
0x180009dd4  mov     r11, rsp
0x180009dd7  mov     [r11+18h], rbx
0x180009ddb  mov     [r11+10h], rdx
0x180009ddf  push    rbp
0x180009de0  push    rsi
0x180009de1  push    rdi
0x180009de2  sub     rsp, 40h
0x180009de6  mov     rdi, r9
0x180009de9  mov     rbp, r8
0x180009dec  mov     rsi, rcx
0x180009def  mov     qword ptr [r11+8], 0
0x180009df7  mov     qword ptr [r11-28h], 0
0x180009dff  mov     qword ptr [r11+10h], 0
0x180009e07  mov     rcx, [rcx]
0x180009e0a  mov     rax, [rcx]
0x180009e0d  lea     rdx, [r11+10h]
0x180009e11  mov     rax, [rax+18h]
0x180009e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e1a  mov     ebx, eax
0x180009e1c  test    eax, eax
0x180009e1e  js      short loc_180009E63
0x180009e20  mov     rcx, [rsi]
0x180009e23  mov     rax, [rcx]
0x180009e26  lea     rdx, [rsp+58h+arg_0]
0x180009e2b  mov     rax, [rax+20h]
0x180009e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e34  mov     ebx, eax
0x180009e36  test    eax, eax
0x180009e38  js      short loc_180009E63
0x180009e3a  mov     [rsp+58h+var_38], rdi
0x180009e3f  mov     r9, rbp
0x180009e42  lea     rdx, [rsp+58h+arg_8]
0x180009e47  lea     rcx, [rsp+58h+arg_0]
0x180009e4c  call    ?FindPartByRelationshipType@OpcUtils@@YAJAEAV?$CComPtr@UIOpcRelationshipSet@@@ATL@@AEAV?$CComPtr@UIOpcPartSet@@@3@PEBG2AEAV?$CComPtr@UIOpcPart@@@3@@Z; OpcUtils::FindPartByRelationshipType(ATL::CComPtr<IOpcRelationshipSet> &,ATL::CComPtr<IOpcPartSet> &,ushort const *,ushort const *,ATL::CComPtr<IOpcPart> &)
0x180009e51  mov     ebx, eax
0x180009e53  test    eax, eax
0x180009e55  js      short loc_180009E63
0x180009e57  mov     eax, 80004005h
0x180009e5c  cmp     qword ptr [rdi], 0
0x180009e60  cmovz   ebx, eax
0x180009e63  mov     rcx, [rsp+58h+arg_8]
0x180009e68  test    rcx, rcx
0x180009e6b  jz      short loc_180009E7A
0x180009e6d  mov     rax, [rcx]
0x180009e70  mov     rax, [rax+10h]
0x180009e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e79  nop
0x180009e7a  mov     rcx, [rsp+58h+arg_0]
0x180009e7f  test    rcx, rcx
0x180009e82  jz      short loc_180009E91
0x180009e84  mov     rax, [rcx]
0x180009e87  mov     rax, [rax+10h]
0x180009e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e90  nop
0x180009e91  mov     eax, ebx
0x180009e93  mov     rbx, [rsp+58h+arg_10]
0x180009e98  add     rsp, 40h
0x180009e9c  pop     rdi
0x180009e9d  pop     rsi
0x180009e9e  pop     rbp
0x180009e9f  retn
```
