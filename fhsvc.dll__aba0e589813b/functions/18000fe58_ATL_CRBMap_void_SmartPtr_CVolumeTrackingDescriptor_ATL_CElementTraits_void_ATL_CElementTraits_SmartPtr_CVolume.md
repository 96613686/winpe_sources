# ATL::CRBMap<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetAt(void *,SmartPtr<CVolumeTrackingDescriptor> const &)

- ea: `0x18000fe58`
- end: `0x18000feac`
- name: `?SetAt@?$CRBMap@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@QEAAPEAU__POSITION@@PEAXAEBV?$SmartPtr@VCVolumeTrackingDescriptor@@@@@Z`
- size: `84`
- prototype: `__int64 __fastcall(unsigned __int64 **, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a360`

## callees

- `0x18000b5b4`
- `0x18000f448`
- `0x18000fb5c`
- `0x18000fe58`

## pseudocode

```c
__int64 __fastcall ATL::CRBMap<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::SetAt(
        unsigned __int64 **a1,
        unsigned __int64 a2)
{
  unsigned __int64 *v4; // rax
  __int64 *v5; // r11
  unsigned __int64 *v6; // rbx

  v4 = ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Find(
         a1,
         a2);
  v6 = v4;
  if ( !v4 )
    return ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBInsert(
             a1,
             a2,
             v5);
  SmartPtr<CVolumeTrackingDescriptor>::operator=((__int64 *)v4 + 1, v5);
  return (__int64)v6;
}

```

## disassembly

```asm
0x18000fe58  mov     [rsp+arg_0], rbx
0x18000fe5d  mov     [rsp+arg_8], rsi
0x18000fe62  push    rdi
0x18000fe63  sub     rsp, 20h
0x18000fe67  mov     r11, r8
0x18000fe6a  mov     rdi, rdx
0x18000fe6d  mov     rsi, rcx
0x18000fe70  call    ?Find@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@IEBAPEAVCNode@12@PEAX@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Find(void *)
0x18000fe75  mov     rbx, rax
0x18000fe78  test    rax, rax
0x18000fe7b  jnz     short loc_18000FE8D
0x18000fe7d  mov     r8, r11
0x18000fe80  mov     rdx, rdi
0x18000fe83  mov     rcx, rsi
0x18000fe86  call    ?RBInsert@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@IEAAPEAVCNode@12@PEAXAEBV?$SmartPtr@VCVolumeTrackingDescriptor@@@@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBInsert(void *,SmartPtr<CVolumeTrackingDescriptor> const &)
0x18000fe8b  jmp     short loc_18000FE9C
0x18000fe8d  lea     rcx, [rax+8]
0x18000fe91  mov     rdx, r11
0x18000fe94  call    ??4?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<CVolumeTrackingDescriptor>::operator=(SmartPtr<CVolumeTrackingDescriptor> const &)
0x18000fe99  mov     rax, rbx
0x18000fe9c  mov     rbx, [rsp+28h+arg_0]
0x18000fea1  mov     rsi, [rsp+28h+arg_8]
0x18000fea6  add     rsp, 20h
0x18000feaa  pop     rdi
0x18000feab  retn
```
