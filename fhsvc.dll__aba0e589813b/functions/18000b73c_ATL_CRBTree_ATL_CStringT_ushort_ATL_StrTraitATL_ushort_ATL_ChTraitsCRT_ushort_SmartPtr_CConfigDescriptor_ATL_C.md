# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RemoveAll(void)

- ea: `0x18000b73c`
- end: `0x18000b79b`
- name: `?RemoveAll@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@QEAAXXZ`
- size: `95`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007cb0`

## callees

- `0x18000b73c`
- `0x18000b7a4`

## import_xrefs

- `msvcrt!free` at `0x18000b76b`
- `msvcrt!free` at `0x18000b76b`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RemoveAll(
        _QWORD *a1)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rbx
  __int64 result; // rax

  if ( *a1 != a1[5] )
    ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RemovePostOrder(a1);
  v2 = (_QWORD *)a1[3];
  a1[1] = 0;
  if ( v2 )
  {
    do
    {
      v3 = (_QWORD *)*v2;
      free(v2);
      v2 = v3;
    }
    while ( v3 );
  }
  result = a1[5];
  *a1 = result;
  a1[3] = 0;
  a1[2] = 0;
  return result;
}

```

## disassembly

```asm
0x18000b73c  mov     [rsp+arg_0], rbx
0x18000b741  push    rdi
0x18000b742  sub     rsp, 20h
0x18000b746  mov     rdx, [rcx]
0x18000b749  mov     rdi, rcx
0x18000b74c  cmp     rdx, [rcx+28h]
0x18000b750  jz      short loc_18000B757
0x18000b752  call    ?RemovePostOrder@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RemovePostOrder(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x18000b757  mov     rcx, [rdi+18h]; Block
0x18000b75b  mov     qword ptr [rdi+8], 0
0x18000b763  test    rcx, rcx
0x18000b766  jz      short loc_18000B779
0x18000b768  mov     rbx, [rcx]
0x18000b76b  call    cs:__imp_free
0x18000b771  mov     rcx, rbx
0x18000b774  test    rbx, rbx
0x18000b777  jnz     short loc_18000B768
0x18000b779  mov     rax, [rdi+28h]
0x18000b77d  mov     rbx, [rsp+28h+arg_0]
0x18000b782  mov     [rdi], rax
0x18000b785  mov     qword ptr [rdi+18h], 0
0x18000b78d  mov     qword ptr [rdi+10h], 0
0x18000b795  add     rsp, 20h
0x18000b799  pop     rdi
0x18000b79a  retn
```
