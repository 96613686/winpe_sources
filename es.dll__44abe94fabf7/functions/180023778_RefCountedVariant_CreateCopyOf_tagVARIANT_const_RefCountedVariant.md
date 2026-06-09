# RefCountedVariant::CreateCopyOf(tagVARIANT const &,RefCountedVariant * &)

- ea: `0x180023778`
- end: `0x1800237fb`
- name: `?CreateCopyOf@RefCountedVariant@@SAJAEBUtagVARIANT@@AEAPEAU1@@Z`
- size: `131`
- prototype: `__int64 __fastcall(VARIANTARG *pvargSrc, VARIANTARG **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180040490`

## callees

- `0x18000d66c`
- `0x180023778`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800237aa`
- `OLEAUT32!__imp_VariantInit` at `0x1800237aa`
- `OLEAUT32!__imp_VariantCopy` at `0x1800237b9`
- `OLEAUT32!__imp_VariantCopy` at `0x1800237b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023792`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023792`

## pseudocode

```c
__int64 __fastcall RefCountedVariant::CreateCopyOf(VARIANTARG *pvargSrc, VARIANTARG **a2)
{
  struct RefCountedVariant *v4; // rax
  struct RefCountedVariant *v5; // rdi
  HRESULT v6; // edi

  v4 = (struct RefCountedVariant *)CoTaskMemAlloc(0x20u);
  v5 = v4;
  if ( v4 )
  {
    *((_DWORD *)v4 + 6) = 1;
    VariantInit((VARIANTARG *)v4);
    *a2 = (VARIANTARG *)v5;
    v6 = VariantCopy((VARIANTARG *)v5, pvargSrc);
    if ( v6 < 0 )
    {
      if ( *a2 )
        RefCountedVariant::`scalar deleting destructor'(*a2);
      *a2 = 0;
    }
    return (unsigned int)v6;
  }
  else
  {
    *a2 = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180023778  mov     [rsp+arg_0], rbx
0x18002377d  mov     [rsp+arg_8], rsi
0x180023782  push    rdi
0x180023783  sub     rsp, 20h
0x180023787  mov     rsi, rcx
0x18002378a  mov     rbx, rdx
0x18002378d  mov     ecx, 20h ; ' '; cb
0x180023792  call    cs:__imp_CoTaskMemAlloc
0x180023798  mov     rdi, rax
0x18002379b  test    rax, rax
0x18002379e  jz      short loc_1800237D7
0x1800237a0  mov     rcx, rax; pvarg
0x1800237a3  mov     dword ptr [rax+18h], 1
0x1800237aa  call    cs:__imp_VariantInit
0x1800237b0  mov     rdx, rsi; pvargSrc
0x1800237b3  mov     [rbx], rdi
0x1800237b6  mov     rcx, rdi; pvargDest
0x1800237b9  call    cs:__imp_VariantCopy
0x1800237bf  mov     edi, eax
0x1800237c1  test    eax, eax
0x1800237c3  js      short loc_1800237E5
0x1800237c5  mov     eax, edi
0x1800237c7  mov     rbx, [rsp+28h+arg_0]
0x1800237cc  mov     rsi, [rsp+28h+arg_8]
0x1800237d1  add     rsp, 20h
0x1800237d5  pop     rdi
0x1800237d6  retn
0x1800237d7  mov     qword ptr [rbx], 0
0x1800237de  mov     eax, 8007000Eh
0x1800237e3  jmp     short loc_1800237C7
0x1800237e5  mov     rcx, [rbx]; this
0x1800237e8  test    rcx, rcx
0x1800237eb  jz      short loc_1800237F2
0x1800237ed  call    ??_GRefCountedVariant@@AEAAPEAXI@Z; RefCountedVariant::`scalar deleting destructor'(uint)
0x1800237f2  mov     qword ptr [rbx], 0
0x1800237f9  jmp     short loc_1800237C5
```
