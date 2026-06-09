# ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::LeftRotate(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)

- ea: `0x18000f588`
- end: `0x18000f5e0`
- name: `?LeftRotate@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z`
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

- `0x18000f588`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::LeftRotate(
        _QWORD *a1,
        __int64 a2)
{
  __int64 result; // rax
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rax

  if ( !a2 )
    return 0;
  v4 = *(_QWORD *)(a2 + 32);
  *(_QWORD *)(a2 + 32) = *(_QWORD *)(v4 + 24);
  v5 = *(_QWORD *)(v4 + 24);
  if ( v5 != a1[5] )
    *(_QWORD *)(v5 + 40) = a2;
  *(_QWORD *)(v4 + 40) = *(_QWORD *)(a2 + 40);
  v6 = *(_QWORD *)(a2 + 40);
  if ( v6 == a1[5] )
  {
    *a1 = v4;
  }
  else if ( a2 == *(_QWORD *)(v6 + 24) )
  {
    *(_QWORD *)(v6 + 24) = v4;
  }
  else
  {
    *(_QWORD *)(v6 + 32) = v4;
  }
  *(_QWORD *)(v4 + 24) = a2;
  result = a2;
  *(_QWORD *)(a2 + 40) = v4;
  return result;
}

```

## disassembly

```asm
0x18000f588  mov     r8, rcx
0x18000f58b  test    rdx, rdx
0x18000f58e  jnz     short loc_18000F593
0x18000f590  xor     eax, eax
0x18000f592  retn
0x18000f593  mov     rcx, [rdx+20h]
0x18000f597  mov     rax, [rcx+18h]
0x18000f59b  mov     [rdx+20h], rax
0x18000f59f  mov     rax, [rcx+18h]
0x18000f5a3  cmp     rax, [r8+28h]
0x18000f5a7  jz      short loc_18000F5AD
0x18000f5a9  mov     [rax+28h], rdx
0x18000f5ad  mov     rax, [rdx+28h]
0x18000f5b1  mov     [rcx+28h], rax
0x18000f5b5  mov     rax, [rdx+28h]
0x18000f5b9  cmp     rax, [r8+28h]
0x18000f5bd  jnz     short loc_18000F5C4
0x18000f5bf  mov     [r8], rcx
0x18000f5c2  jmp     short loc_18000F5D4
0x18000f5c4  cmp     rdx, [rax+18h]
0x18000f5c8  jnz     short loc_18000F5D0
0x18000f5ca  mov     [rax+18h], rcx
0x18000f5ce  jmp     short loc_18000F5D4
0x18000f5d0  mov     [rax+20h], rcx
0x18000f5d4  mov     [rcx+18h], rdx
0x18000f5d8  mov     rax, rdx
0x18000f5db  mov     [rdx+28h], rcx
0x18000f5df  retn
```
