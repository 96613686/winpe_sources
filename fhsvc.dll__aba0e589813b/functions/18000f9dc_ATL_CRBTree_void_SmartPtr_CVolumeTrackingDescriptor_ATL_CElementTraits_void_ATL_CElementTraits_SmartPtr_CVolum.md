# ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBDeleteFixup(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)

- ea: `0x18000f9dc`
- end: `0x18000fb53`
- name: `?RBDeleteFixup@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAXPEAVCNode@12@@Z`
- size: `375`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f6b8`
- `0x18000f7c8`
- `0x18000f8cc`

## callees

- `0x18000b48c`
- `0x18000f588`
- `0x18000f9dc`
- `0x18000fdf8`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBDeleteFixup(
        __int64 *a1,
        __int64 a2)
{
  __int64 *v2; // r10
  __int64 *v3; // r9
  __int64 v4; // r8
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r11
  __int64 result; // rax
  __int64 v9; // r11

  v2 = a1;
  if ( !a2 )
    ATL::AtlThrowImpl(-2147467259);
  if ( a2 != *a1 )
  {
    do
    {
      if ( *(_DWORD *)(a2 + 16) != 1 )
        break;
      v3 = (__int64 *)(a2 + 40);
      v4 = *(_QWORD *)(a2 + 40);
      v5 = *(_QWORD *)(v4 + 24);
      if ( a2 == v5 )
      {
        v6 = *(_QWORD *)(v4 + 32);
        if ( !*(_DWORD *)(v6 + 16) )
        {
          *(_DWORD *)(v6 + 16) = 1;
          *(_DWORD *)(*(_QWORD *)(v6 + 40) + 16LL) = 0;
          ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::LeftRotate(
            v2,
            *v3);
          v4 = *v3;
          v6 = *(_QWORD *)(*v3 + 32);
        }
        v7 = *(_QWORD *)(v6 + 24);
        if ( *(_DWORD *)(v7 + 16) != 1 || (result = *(_QWORD *)(v6 + 32), *(_DWORD *)(result + 16) != 1) )
        {
          if ( *(_DWORD *)(*(_QWORD *)(v6 + 32) + 16LL) == 1 )
          {
            *(_DWORD *)(v7 + 16) = 1;
            *(_DWORD *)(v6 + 16) = 0;
            ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RightRotate(
              v2,
              v6);
            v4 = *v3;
            v6 = *(_QWORD *)(*v3 + 32);
          }
          *(_DWORD *)(v6 + 16) = *(_DWORD *)(v4 + 16);
          *(_DWORD *)(*v3 + 16) = 1;
          *(_DWORD *)(*(_QWORD *)(v6 + 32) + 16LL) = 1;
          result = ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::LeftRotate(
                     v2,
                     *v3);
LABEL_21:
          v3 = v2;
          goto LABEL_22;
        }
        *(_DWORD *)(v6 + 16) = 0;
      }
      else
      {
        if ( !*(_DWORD *)(v5 + 16) )
        {
          *(_DWORD *)(v5 + 16) = 1;
          *(_DWORD *)(*(_QWORD *)(v5 + 40) + 16LL) = 0;
          ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RightRotate(
            v2,
            *v3);
          v4 = *v3;
          v5 = *(_QWORD *)(*v3 + 24);
        }
        v9 = *(_QWORD *)(v5 + 32);
        if ( *(_DWORD *)(v9 + 16) != 1 || (result = *(_QWORD *)(v5 + 24), *(_DWORD *)(result + 16) != 1) )
        {
          if ( *(_DWORD *)(*(_QWORD *)(v5 + 24) + 16LL) == 1 )
          {
            *(_DWORD *)(v9 + 16) = 1;
            *(_DWORD *)(v5 + 16) = 0;
            ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::LeftRotate(
              v2,
              v5);
            v4 = *v3;
            v5 = *(_QWORD *)(*v3 + 24);
          }
          *(_DWORD *)(v5 + 16) = *(_DWORD *)(v4 + 16);
          *(_DWORD *)(*v3 + 16) = 1;
          *(_DWORD *)(*(_QWORD *)(v5 + 24) + 16LL) = 1;
          result = ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RightRotate(
                     v2,
                     *v3);
          goto LABEL_21;
        }
        *(_DWORD *)(v5 + 16) = 0;
      }
LABEL_22:
      a2 = *v3;
    }
    while ( *v3 != *v2 );
  }
  *(_DWORD *)(a2 + 16) = 1;
  return result;
}

```

## disassembly

```asm
0x18000f9dc  push    rbx
0x18000f9de  sub     rsp, 20h
0x18000f9e2  mov     r10, rcx
0x18000f9e5  test    rdx, rdx
0x18000f9e8  jz      loc_18000FB48
0x18000f9ee  mov     ebx, 1
0x18000f9f3  cmp     rdx, [rcx]
0x18000f9f6  jz      loc_18000FB3F
0x18000f9fc  cmp     [rdx+10h], ebx
0x18000f9ff  jnz     loc_18000FB3F
0x18000fa05  lea     r9, [rdx+28h]
0x18000fa09  mov     r8, [r9]
0x18000fa0c  mov     rcx, [r8+18h]
0x18000fa10  cmp     rdx, rcx
0x18000fa13  jnz     loc_18000FAA9
0x18000fa19  mov     rdx, [r8+20h]
0x18000fa1d  cmp     dword ptr [rdx+10h], 0
0x18000fa21  jnz     short loc_18000FA43
0x18000fa23  mov     [rdx+10h], ebx
0x18000fa26  mov     rax, [rdx+28h]
0x18000fa2a  mov     dword ptr [rax+10h], 0
0x18000fa31  mov     rdx, [r9]
0x18000fa34  mov     rcx, r10
0x18000fa37  call    ?LeftRotate@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::LeftRotate(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000fa3c  mov     r8, [r9]
0x18000fa3f  mov     rdx, [r8+20h]
0x18000fa43  mov     r11, [rdx+18h]
0x18000fa47  cmp     [r11+10h], ebx
0x18000fa4b  jnz     short loc_18000FA62
0x18000fa4d  mov     rax, [rdx+20h]
0x18000fa51  cmp     [rax+10h], ebx
0x18000fa54  jnz     short loc_18000FA62
0x18000fa56  mov     dword ptr [rdx+10h], 0
0x18000fa5d  jmp     loc_18000FB33
0x18000fa62  mov     rax, [rdx+20h]
0x18000fa66  cmp     [rax+10h], ebx
0x18000fa69  jnz     short loc_18000FA85
0x18000fa6b  mov     [r11+10h], ebx
0x18000fa6f  mov     dword ptr [rdx+10h], 0
0x18000fa76  mov     rcx, r10
0x18000fa79  call    ?RightRotate@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RightRotate(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000fa7e  mov     r8, [r9]
0x18000fa81  mov     rdx, [r8+20h]
0x18000fa85  mov     eax, [r8+10h]
0x18000fa89  mov     [rdx+10h], eax
0x18000fa8c  mov     rax, [r9]
0x18000fa8f  mov     [rax+10h], ebx
0x18000fa92  mov     rax, [rdx+20h]
0x18000fa96  mov     [rax+10h], ebx
0x18000fa99  mov     rdx, [r9]
0x18000fa9c  mov     rcx, r10
0x18000fa9f  call    ?LeftRotate@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::LeftRotate(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000faa4  jmp     loc_18000FB30
0x18000faa9  cmp     dword ptr [rcx+10h], 0
0x18000faad  jnz     short loc_18000FACF
0x18000faaf  mov     [rcx+10h], ebx
0x18000fab2  mov     rax, [rcx+28h]
0x18000fab6  mov     dword ptr [rax+10h], 0
0x18000fabd  mov     rdx, [r9]
0x18000fac0  mov     rcx, r10
0x18000fac3  call    ?RightRotate@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RightRotate(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000fac8  mov     r8, [r9]
0x18000facb  mov     rcx, [r8+18h]
0x18000facf  mov     r11, [rcx+20h]
0x18000fad3  cmp     [r11+10h], ebx
0x18000fad7  jnz     short loc_18000FAEB
0x18000fad9  mov     rax, [rcx+18h]
0x18000fadd  cmp     [rax+10h], ebx
0x18000fae0  jnz     short loc_18000FAEB
0x18000fae2  mov     dword ptr [rcx+10h], 0
0x18000fae9  jmp     short loc_18000FB33
0x18000faeb  mov     rax, [rcx+18h]
0x18000faef  cmp     [rax+10h], ebx
0x18000faf2  jnz     short loc_18000FB11
0x18000faf4  mov     [r11+10h], ebx
0x18000faf8  mov     dword ptr [rcx+10h], 0
0x18000faff  mov     rdx, rcx
0x18000fb02  mov     rcx, r10
0x18000fb05  call    ?LeftRotate@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::LeftRotate(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000fb0a  mov     r8, [r9]
0x18000fb0d  mov     rcx, [r8+18h]
0x18000fb11  mov     eax, [r8+10h]
0x18000fb15  mov     [rcx+10h], eax
0x18000fb18  mov     rax, [r9]
0x18000fb1b  mov     [rax+10h], ebx
0x18000fb1e  mov     rax, [rcx+18h]
0x18000fb22  mov     [rax+10h], ebx
0x18000fb25  mov     rdx, [r9]
0x18000fb28  mov     rcx, r10
0x18000fb2b  call    ?RightRotate@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RightRotate(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000fb30  mov     r9, r10
0x18000fb33  mov     rdx, [r9]
0x18000fb36  cmp     rdx, [r10]
0x18000fb39  jnz     loc_18000F9FC
0x18000fb3f  mov     [rdx+10h], ebx
0x18000fb42  add     rsp, 20h
0x18000fb46  pop     rbx
0x18000fb47  retn
0x18000fb48  mov     ecx, 80004005h; int
0x18000fb4d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
