# ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RightRotate(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)

- ea: `0x18000fdf8`
- end: `0x18000fe50`
- name: `?RightRotate@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z`
- size: `88`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f9dc`
- `0x18000fb5c`
- `0x18000fcd4`

## callees

- `0x18000fdf8`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RightRotate(
        _QWORD *a1,
        __int64 a2)
{
  __int64 result; // rax
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rax

  if ( !a2 )
    return 0;
  v4 = *(_QWORD *)(a2 + 24);
  *(_QWORD *)(a2 + 24) = *(_QWORD *)(v4 + 32);
  v5 = *(_QWORD *)(v4 + 32);
  if ( v5 != a1[5] )
    *(_QWORD *)(v5 + 40) = a2;
  *(_QWORD *)(v4 + 40) = *(_QWORD *)(a2 + 40);
  v6 = *(_QWORD *)(a2 + 40);
  if ( v6 == a1[5] )
  {
    *a1 = v4;
  }
  else if ( a2 == *(_QWORD *)(v6 + 32) )
  {
    *(_QWORD *)(v6 + 32) = v4;
  }
  else
  {
    *(_QWORD *)(v6 + 24) = v4;
  }
  *(_QWORD *)(v4 + 32) = a2;
  result = a2;
  *(_QWORD *)(a2 + 40) = v4;
  return result;
}

```

## disassembly

```asm
0x18000fdf8  mov     r8, rcx
0x18000fdfb  test    rdx, rdx
0x18000fdfe  jnz     short loc_18000FE03
0x18000fe00  xor     eax, eax
0x18000fe02  retn
0x18000fe03  mov     rcx, [rdx+18h]
0x18000fe07  mov     rax, [rcx+20h]
0x18000fe0b  mov     [rdx+18h], rax
0x18000fe0f  mov     rax, [rcx+20h]
0x18000fe13  cmp     rax, [r8+28h]
0x18000fe17  jz      short loc_18000FE1D
0x18000fe19  mov     [rax+28h], rdx
0x18000fe1d  mov     rax, [rdx+28h]
0x18000fe21  mov     [rcx+28h], rax
0x18000fe25  mov     rax, [rdx+28h]
0x18000fe29  cmp     rax, [r8+28h]
0x18000fe2d  jnz     short loc_18000FE34
0x18000fe2f  mov     [r8], rcx
0x18000fe32  jmp     short loc_18000FE44
0x18000fe34  cmp     rdx, [rax+20h]
0x18000fe38  jnz     short loc_18000FE40
0x18000fe3a  mov     [rax+20h], rcx
0x18000fe3e  jmp     short loc_18000FE44
0x18000fe40  mov     [rax+18h], rcx
0x18000fe44  mov     [rcx+20h], rdx
0x18000fe48  mov     rax, rdx
0x18000fe4b  mov     [rdx+28h], rcx
0x18000fe4f  retn
```
