# LvDataOrig::ReadPage(DataPage &,ulong,Err &)

- ea: `0x1003b1d0`
- end: `0x1003b253`
- name: `?ReadPage@LvDataOrig@@QAEXAAVDataPage@@KAAVErr@@@Z`
- size: `131`
- prototype: `void __thiscall(LvDataOrig *__hidden this, struct DataPage *, unsigned int, struct Err *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1003b970`
- `0x1003d300`

## callees

- `0x10023690`
- `0x10025ee0`
- `0x1003b1d0`
- `0x1003ff40`

## pseudocode

```c
void __thiscall LvDataOrig::ReadPage(LvDataOrig *this, struct DataPage *a2, unsigned int a3, void **a4)
{
  __int16 v4; // ax
  Database **v5; // [esp-4h] [ebp-10h]

  v5 = *(Database ***)(*(_DWORD *)(*((_DWORD *)this + 517) + 8) + 40);
  Database::ReadPage(v5[2], a2, a3 >> 8, 1, a4, (struct Transaction *)v5);
  if ( (*(_BYTE *)a4 & 8) == 0 )
  {
    v4 = **((_WORD **)a2 + 1);
    if ( v4 == 257 )
    {
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_jet_3xlv>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_jet_3xlv>::GetImpl'::`2'::impl);
    }
    else if ( v4 == 265 )
    {
      Err::SetError(a4, -1611, 265);
    }
    else
    {
      Err::SetError(a4, -1206, 265);
    }
  }
}

```

## disassembly

```asm
0x1003b1d0  mov     edi, edi
0x1003b1d2  push    ebp
0x1003b1d3  mov     ebp, esp
0x1003b1d5  push    ecx
0x1003b1d6  mov     eax, [ecx+814h]
0x1003b1dc  push    esi
0x1003b1dd  mov     esi, [ebp+arg_8]
0x1003b1e0  push    edi
0x1003b1e1  mov     eax, [eax+8]
0x1003b1e4  mov     edi, [ebp+arg_0]
0x1003b1e7  mov     ecx, [eax+28h]
0x1003b1ea  mov     eax, [ebp+arg_4]
0x1003b1ed  push    ecx; struct Transaction *
0x1003b1ee  push    esi; struct Err *
0x1003b1ef  mov     ecx, [ecx+8]; this
0x1003b1f2  push    1; char
0x1003b1f4  shr     eax, 8
0x1003b1f7  push    eax; unsigned int
0x1003b1f8  push    edi; struct PageRef *
0x1003b1f9  call    ?ReadPage@Database@@QAEXAAVPageRef@@KIAAVErr@@PAVTransaction@@@Z; Database::ReadPage(PageRef &,ulong,uint,Err &,Transaction *)
0x1003b1fe  test    byte ptr [esi], 8
0x1003b201  jnz     short loc_1003B24C
0x1003b203  mov     eax, [edi+4]
0x1003b206  mov     ecx, 101h
0x1003b20b  movzx   eax, word ptr [eax]
0x1003b20e  cmp     ax, cx
0x1003b211  jz      short loc_1003B242
0x1003b213  mov     ecx, 109h
0x1003b218  push    ecx
0x1003b219  cmp     ax, cx
0x1003b21c  mov     ecx, esi
0x1003b21e  jz      short loc_1003B231
0x1003b220  push    0FFFFFB4Ah
0x1003b225  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1003b22a  pop     edi
0x1003b22b  pop     esi
0x1003b22c  pop     ecx
0x1003b22d  pop     ebp
0x1003b22e  retn    0Ch
0x1003b231  push    0FFFFF9B5h
0x1003b236  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1003b23b  pop     edi
0x1003b23c  pop     esi
0x1003b23d  pop     ecx
0x1003b23e  pop     ebp
0x1003b23f  retn    0Ch
0x1003b242  mov     ecx, offset ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_jet_3xlv@@@wil@@CGAAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_jet_3xlv@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_jet_3xlv> `wil::Feature<__WilFeatureTraits_Feature_Servicing_jet_3xlv>::GetImpl(void)'::`2'::impl
0x1003b247  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_jet_3xlv@@@details@wil@@QAE_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_jet_3xlv>::__private_IsEnabled(void)
0x1003b24c  pop     edi
0x1003b24d  pop     esi
0x1003b24e  pop     ecx
0x1003b24f  pop     ebp
0x1003b250  retn    0Ch
```
