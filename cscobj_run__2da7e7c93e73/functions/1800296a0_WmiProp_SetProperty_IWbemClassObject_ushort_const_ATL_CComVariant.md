# WmiProp_SetProperty(IWbemClassObject *,ushort const *,ATL::CComVariant)

- ea: `0x1800296a0`
- end: `0x180029716`
- name: `?WmiProp_SetProperty@@YAJPEAUIWbemClassObject@@PEBGVCComVariant@ATL@@@Z`
- size: `118`
- prototype: `int __high(struct IWbemClassObject *, const unsigned __int16 *, struct ATL::CComVariant)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001c644`
- `0x18001c700`
- `0x18001ec30`
- `0x18001ee5c`
- `0x18001ef70`
- `0x18001f22c`
- `0x180021b60`
- `0x180022030`
- `0x18002938c`

## callees

- `0x180028094`
- `0x1800296a0`
- `0x18002c010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180029703`
- `OLEAUT32!__imp_VariantClear` at `0x180029703`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WmiProp_SetProperty(__int64 a1, __int64 a2, VARIANTARG *a3)
{
  unsigned int Lo; // edi
  int v5; // r8d
  __int64 v6; // r10
  __int64 v7; // r11

  if ( a3->vt == 10 )
  {
    Lo = a3->cyVal.Lo;
  }
  else
  {
    Lo = -2147024809;
    v5 = CIMTypeFromVariantType(a3->vt);
    if ( v5 != 4095 )
      Lo = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, VARIANTARG *, int))(*(_QWORD *)v6 + 40LL))(
             v6,
             v7,
             0,
             a3,
             v5);
  }
  VariantClear(a3);
  return Lo;
}

```

## disassembly

```asm
0x1800296a0  mov     [rsp+arg_0], rbx
0x1800296a5  mov     [rsp+arg_10], r8
0x1800296aa  push    rdi
0x1800296ab  sub     rsp, 30h
0x1800296af  mov     rbx, r8
0x1800296b2  mov     r11, rdx
0x1800296b5  mov     r10, rcx
0x1800296b8  mov     eax, 0Ah
0x1800296bd  cmp     ax, [r8]
0x1800296c1  jnz     short loc_1800296C9
0x1800296c3  mov     edi, [r8+8]
0x1800296c7  jmp     short loc_180029700
0x1800296c9  mov     edi, 80070057h
0x1800296ce  movzx   ecx, word ptr [r8]; unsigned __int16
0x1800296d2  call    ?CIMTypeFromVariantType@@YAJG@Z; CIMTypeFromVariantType(ushort)
0x1800296d7  mov     r8d, eax
0x1800296da  cmp     eax, 0FFFh
0x1800296df  jz      short loc_180029700
0x1800296e1  mov     rax, [r10]
0x1800296e4  mov     [rsp+38h+var_18], r8d
0x1800296e9  mov     r9, rbx
0x1800296ec  xor     r8d, r8d
0x1800296ef  mov     rdx, r11
0x1800296f2  mov     rcx, r10
0x1800296f5  mov     rax, [rax+28h]
0x1800296f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296fe  mov     edi, eax
0x180029700  mov     rcx, rbx; pvarg
0x180029703  call    cs:__imp_VariantClear
0x180029709  mov     eax, edi
0x18002970b  mov     rbx, [rsp+38h+arg_0]
0x180029710  add     rsp, 30h
0x180029714  pop     rdi
0x180029715  retn
```
