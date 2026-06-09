# ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::FreeNode(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)

- ea: `0x18000b65c`
- end: `0x18000b6a0`
- name: `?FreeNode@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAXPEAVCNode@12@@Z`
- size: `68`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b614`
- `0x18000f6b8`

## callees

- `0x18000b48c`
- `0x18000b65c`
- `0x18000be90`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::FreeNode(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  if ( !a2 )
    ATL::AtlThrowImpl(-2147467259);
  SmartPtr<CVolumeTrackingDescriptor>::~SmartPtr<CVolumeTrackingDescriptor>((_QWORD *)(a2 + 8));
  result = *(_QWORD *)(a1 + 16);
  *(_QWORD *)(a2 + 24) = result;
  *(_QWORD *)(a1 + 16) = a2;
  --*(_QWORD *)(a1 + 8);
  return result;
}

```

## disassembly

```asm
0x18000b65c  mov     [rsp+arg_0], rbx
0x18000b661  push    rdi
0x18000b662  sub     rsp, 20h
0x18000b666  mov     rbx, rdx
0x18000b669  mov     rdi, rcx
0x18000b66c  test    rdx, rdx
0x18000b66f  jnz     short loc_18000B67C
0x18000b671  mov     ecx, 80004005h; int
0x18000b676  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b67c  lea     rcx, [rdx+8]
0x18000b680  call    ??1?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAA@XZ; SmartPtr<CVolumeTrackingDescriptor>::~SmartPtr<CVolumeTrackingDescriptor>(void)
0x18000b685  mov     rax, [rdi+10h]
0x18000b689  mov     [rbx+18h], rax
0x18000b68d  mov     [rdi+10h], rbx
0x18000b691  dec     qword ptr [rdi+8]
0x18000b695  mov     rbx, [rsp+28h+arg_0]
0x18000b69a  add     rsp, 20h
0x18000b69e  pop     rdi
0x18000b69f  retn
```
