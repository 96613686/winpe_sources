# TxfPublishCommittedChangesToDefaultReaderSection

- ea: `0x14029ac70`
- end: `0x14029af16`
- name: `TxfPublishCommittedChangesToDefaultReaderSection`
- size: `678`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400415b4`
- `0x14019dc78`

## callees

- `0x140150bc0`
- `0x140163f78`
- `0x140276550`
- `0x14029ac70`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14029aede`
- `ntoskrnl!ObfDereferenceObject` at `0x1402be595`
- `ntoskrnl!ObfDereferenceObject` at `0x14029aede`
- `ntoskrnl!ObfDereferenceObject` at `0x1402be595`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14029aeca`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1402be582`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14029aeca`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1402be582`
- `ntoskrnl!CcPurgeCacheSection` at `0x14029ad93`
- `ntoskrnl!CcPurgeCacheSection` at `0x14029ad93`
- `ntoskrnl!MmForceSectionClosed` at `0x14029ae07`
- `ntoskrnl!MmForceSectionClosed` at `0x14029ae07`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029ae62`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029ae79`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402be4fe`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402be51d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029ae62`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029ae79`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402be4fe`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402be51d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029accc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029ae31`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402be4cc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029accc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029ae31`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402be4cc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029ad37`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029aea5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029aefd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402be55e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029ad37`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029aea5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029aefd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402be55e`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14029aca9`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14029aca9`

## pseudocode

```c
void __fastcall TxfPublishCommittedChangesToDefaultReaderSection(int a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // r14
  __int64 *v6; // rsi
  __int64 v7; // rsi
  int v8; // r9d
  int v9; // ecx
  _QWORD v10[7]; // [rsp+30h] [rbp-38h] BYREF
  PFILE_OBJECT FileObject; // [rsp+80h] [rbp+18h] BYREF
  __int64 v12; // [rsp+88h] [rbp+20h]

  FileObject = 0;
  v4 = *(_QWORD *)(a2 + 528);
  v5 = a2 + 184;
  if ( !ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v4 + 64) + 136LL)) )
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v5 + 328LL) + 136LL), 1u);
  v6 = *(__int64 **)(v4 + 112);
  if ( !v6 )
    *(_DWORD *)(v4 + 24) &= ~0x1000u;
  if ( (*(_DWORD *)(*(_QWORD *)(a2 + 528) + 24LL) & 0x1000) == 0 || (*(_DWORD *)(v4 + 24) & 0x2000) != 0 )
  {
    ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v5 + 328LL) + 136LL));
  }
  else
  {
    v12 = v4;
    v7 = *v6;
    v10[1] = v7;
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 64));
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 212));
    *(_DWORD *)(v4 + 24) |= 0x2000u;
    ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v5 + 328LL) + 136LL));
    LOBYTE(v8) = 4;
    NtfsCreateInternalAttributeStream(a1, a2, 0, v8, 0, (__int64)&FileObject);
    NtfsSetCcFileSizes(FileObject, a2, a2 + 24);
    if ( !CcPurgeCacheSection(FileObject->SectionObjectPointer, 0, 0, 0) )
    {
      if ( !*(_QWORD *)(a2 + 280) )
        NtfsCreateInternalAttributeStream(a1, a2, 0, 0, 0, 0);
      v10[0] = 0;
      TxfCopyDataRange(v9, (_DWORD)FileObject, *(_QWORD *)(a2 + 280), (unsigned int)v10, *(_DWORD *)(a2 + 32));
      MmForceSectionClosed(FileObject->SectionObjectPointer, 1u);
      *(_DWORD *)(*(_QWORD *)(a2 + 528) + 24LL) |= 0x40u;
    }
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v5 + 328LL) + 136LL), 1u);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 64), 0xFFFFFFFF) == 1 )
    {
      if ( (*(_DWORD *)(v7 + 68) & 1) != 0 )
        *(_WORD *)v7 = 0;
      else
        ExFreeToLookasideListEx(&NtfsScbNonpagedLookasideList, (PVOID)v7);
      ExFreeToLookasideListEx(&TxfDefaultReaderSectionLookasideList, *(PVOID *)(v4 + 112));
      *(_QWORD *)(v4 + 112) = 0;
    }
    *(_DWORD *)(v4 + 24) &= 0xFFFFCFFF;
    ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)v5 + 328LL) + 136LL));
    _InterlockedDecrement((volatile signed __int32 *)(a2 + 212));
    if ( FileObject )
    {
      CcUninitializeCacheMap(FileObject, 0, 0);
      ObfDereferenceObject(FileObject);
    }
  }
}

```

## disassembly

```asm
0x14029ac70  mov     rax, rsp
0x14029ac73  mov     [rax+10h], rdx
0x14029ac77  push    rbx
0x14029ac78  push    rsi
0x14029ac79  push    rdi
0x14029ac7a  push    r14
0x14029ac7c  push    r15
0x14029ac7e  sub     rsp, 40h
0x14029ac82  mov     rdi, rdx
0x14029ac85  mov     r15, rcx
0x14029ac88  mov     qword ptr [rax+18h], 0
0x14029ac90  mov     rbx, [rdx+210h]
0x14029ac97  lea     r14, [rdx+0B8h]
0x14029ac9e  mov     rcx, [rbx+40h]
0x14029aca2  mov     rcx, [rcx+88h]; Resource
0x14029aca9  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14029acb0  nop     dword ptr [rax+rax+00h]
0x14029acb5  test    al, al
0x14029acb7  jnz     short loc_14029ACD8
0x14029acb9  mov     rax, [r14]
0x14029acbc  mov     rcx, [rax+148h]
0x14029acc3  mov     dl, 1; Wait
0x14029acc5  mov     rcx, [rcx+88h]; Resource
0x14029accc  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14029acd3  nop     dword ptr [rax+rax+00h]
0x14029acd8  mov     rsi, [rbx+70h]
0x14029acdc  test    rsi, rsi
0x14029acdf  jnz     short loc_14029ACE6
0x14029ace1  btr     dword ptr [rbx+18h], 0Ch
0x14029ace6  mov     rax, [rdi+210h]
0x14029aced  test    dword ptr [rax+18h], 1000h
0x14029acf4  jz      loc_14029AEEC
0x14029acfa  mov     ecx, 2000h
0x14029acff  test    [rbx+18h], ecx
0x14029ad02  jnz     loc_14029AEEC
0x14029ad08  mov     [rsp+68h+arg_18], rbx
0x14029ad10  mov     rsi, [rsi]
0x14029ad13  mov     [rsp+68h+var_30], rsi
0x14029ad18  lock inc dword ptr [rsi+40h]
0x14029ad1c  lock inc dword ptr [rdi+0D4h]
0x14029ad23  or      [rbx+18h], ecx
0x14029ad26  mov     rax, [r14]
0x14029ad29  mov     rcx, [rax+148h]
0x14029ad30  mov     rcx, [rcx+88h]; Resource
0x14029ad37  call    cs:__imp_ExReleaseResourceLite
0x14029ad3e  nop     dword ptr [rax+rax+00h]
0x14029ad43  nop
0x14029ad44  lea     rax, [rsp+68h+FileObject]
0x14029ad4c  mov     [rsp+68h+var_40], rax
0x14029ad51  mov     [rsp+68h+var_48], 0
0x14029ad5a  mov     r9b, 4
0x14029ad5d  xor     r8d, r8d
0x14029ad60  mov     rdx, rdi
0x14029ad63  mov     rcx, r15
0x14029ad66  call    NtfsCreateInternalAttributeStream
0x14029ad6b  lea     r8, [rdi+18h]
0x14029ad6f  mov     rdx, rdi
0x14029ad72  mov     rcx, [rsp+68h+FileObject]
0x14029ad7a  call    NtfsSetCcFileSizes
0x14029ad7f  xor     r9d, r9d; Flags
0x14029ad82  xor     r8d, r8d; Length
0x14029ad85  xor     edx, edx; FileOffset
0x14029ad87  mov     rcx, [rsp+68h+FileObject]
0x14029ad8f  mov     rcx, [rcx+28h]; SectionObjectPointer
0x14029ad93  call    cs:__imp_CcPurgeCacheSection
0x14029ad9a  nop     dword ptr [rax+rax+00h]
0x14029ad9f  test    al, al
0x14029ada1  jnz     short loc_14029AE1E
0x14029ada3  cmp     qword ptr [rdi+118h], 0
0x14029adab  jnz     short loc_14029ADD0
0x14029adad  mov     [rsp+68h+var_40], 0
0x14029adb6  mov     [rsp+68h+var_48], 0
0x14029adbf  xor     r9d, r9d
0x14029adc2  xor     r8d, r8d
0x14029adc5  mov     rdx, rdi
0x14029adc8  mov     rcx, r15
0x14029adcb  call    NtfsCreateInternalAttributeStream
0x14029add0  mov     [rsp+68h+var_38], 0
0x14029add9  mov     eax, [rdi+20h]
0x14029addc  mov     dword ptr [rsp+68h+var_48], eax
0x14029ade0  lea     r9, [rsp+68h+var_38]
0x14029ade5  mov     r8, [rdi+118h]
0x14029adec  mov     rdx, [rsp+68h+FileObject]
0x14029adf4  call    TxfCopyDataRange
0x14029adf9  mov     dl, 1; DelayClose
0x14029adfb  mov     rcx, [rsp+68h+FileObject]
0x14029ae03  mov     rcx, [rcx+28h]; SectionObjectPointer
0x14029ae07  call    cs:__imp_MmForceSectionClosed
0x14029ae0e  nop     dword ptr [rax+rax+00h]
0x14029ae13  mov     rax, [rdi+210h]
0x14029ae1a  or      dword ptr [rax+18h], 40h
0x14029ae1e  mov     rax, [r14]
0x14029ae21  mov     rcx, [rax+148h]
0x14029ae28  mov     dl, 1; Wait
0x14029ae2a  mov     rcx, [rcx+88h]; Resource
0x14029ae31  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14029ae38  nop     dword ptr [rax+rax+00h]
0x14029ae3d  or      eax, 0FFFFFFFFh
0x14029ae40  lock xadd [rsi+40h], eax
0x14029ae45  cmp     eax, 1
0x14029ae48  jnz     short loc_14029AE8D
0x14029ae4a  mov     eax, [rsi+44h]
0x14029ae4d  test    al, 1
0x14029ae4f  jz      short loc_14029AE58
0x14029ae51  xor     eax, eax
0x14029ae53  mov     [rsi], ax
0x14029ae56  jmp     short loc_14029AE6E
0x14029ae58  mov     rdx, rsi; Entry
0x14029ae5b  lea     rcx, NtfsScbNonpagedLookasideList; Lookaside
0x14029ae62  call    cs:__imp_ExFreeToLookasideListEx
0x14029ae69  nop     dword ptr [rax+rax+00h]
0x14029ae6e  mov     rdx, [rbx+70h]; Entry
0x14029ae72  lea     rcx, TxfDefaultReaderSectionLookasideList; Lookaside
0x14029ae79  call    cs:__imp_ExFreeToLookasideListEx
0x14029ae80  nop     dword ptr [rax+rax+00h]
0x14029ae85  mov     qword ptr [rbx+70h], 0
0x14029ae8d  and     dword ptr [rbx+18h], 0FFFFCFFFh
0x14029ae94  mov     rax, [r14]
0x14029ae97  mov     rcx, [rax+148h]
0x14029ae9e  mov     rcx, [rcx+88h]; Resource
0x14029aea5  call    cs:__imp_ExReleaseResourceLite
0x14029aeac  nop     dword ptr [rax+rax+00h]
0x14029aeb1  lock dec dword ptr [rdi+0D4h]
0x14029aeb8  mov     rcx, [rsp+68h+FileObject]; FileObject
0x14029aec0  test    rcx, rcx
0x14029aec3  jz      short loc_14029AF09
0x14029aec5  xor     r8d, r8d; UninitializeEvent
0x14029aec8  xor     edx, edx; TruncateSize
0x14029aeca  call    cs:__imp_CcUninitializeCacheMap
0x14029aed1  nop     dword ptr [rax+rax+00h]
0x14029aed6  mov     rcx, [rsp+68h+FileObject]; Object
0x14029aede  call    cs:__imp_ObfDereferenceObject
0x14029aee5  nop     dword ptr [rax+rax+00h]
0x14029aeea  jmp     short loc_14029AF09
0x14029aeec  mov     rax, [r14]
0x14029aeef  mov     rcx, [rax+148h]
0x14029aef6  mov     rcx, [rcx+88h]; Resource
0x14029aefd  call    cs:__imp_ExReleaseResourceLite
0x14029af04  nop     dword ptr [rax+rax+00h]
0x14029af09  add     rsp, 40h
0x14029af0d  pop     r15
0x14029af0f  pop     r14
0x14029af11  pop     rdi
0x14029af12  pop     rsi
0x14029af13  pop     rbx
0x14029af14  retn
0x1402be498  push    rbx
0x1402be49a  push    rbp
0x1402be49b  push    rsi
0x1402be49c  push    rdi
0x1402be49d  sub     rsp, 38h
0x1402be4a1  mov     rbp, rdx
0x1402be4a4  mov     sil, cl
0x1402be4a7  test    cl, cl
0x1402be4a9  jz      short loc_1402BE4B1
0x1402be4ab  mov     al, cs:NtfsStatusDebugFlags
0x1402be4b1  mov     rdi, [rbp+78h]
0x1402be4b5  mov     rax, [rdi+0B8h]
0x1402be4bc  mov     rcx, [rax+148h]
0x1402be4c3  mov     dl, 1; Wait
0x1402be4c5  mov     rcx, [rcx+88h]; Resource
0x1402be4cc  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1402be4d3  nop     dword ptr [rax+rax+00h]
0x1402be4d8  mov     rdx, [rbp+38h]; Entry
0x1402be4dc  or      eax, 0FFFFFFFFh
0x1402be4df  lock xadd [rdx+40h], eax
0x1402be4e4  cmp     eax, 1
0x1402be4e7  jnz     short loc_1402BE533
0x1402be4e9  mov     eax, [rdx+44h]
0x1402be4ec  test    al, 1
0x1402be4ee  jz      short loc_1402BE4F7
0x1402be4f0  xor     eax, eax
0x1402be4f2  mov     [rdx], ax
0x1402be4f5  jmp     short loc_1402BE50B
0x1402be4f7  lea     rcx, NtfsScbNonpagedLookasideList; Lookaside
0x1402be4fe  call    cs:__imp_ExFreeToLookasideListEx
0x1402be505  nop     dword ptr [rax+rax+00h]
0x1402be50a  nop
0x1402be50b  mov     rbx, [rbp+88h]
0x1402be512  mov     rdx, [rbx+70h]; Entry
0x1402be516  lea     rcx, TxfDefaultReaderSectionLookasideList; Lookaside
0x1402be51d  call    cs:__imp_ExFreeToLookasideListEx
0x1402be524  nop     dword ptr [rax+rax+00h]
0x1402be529  mov     qword ptr [rbx+70h], 0
0x1402be531  jmp     short loc_1402BE53A
0x1402be533  mov     rbx, [rbp+88h]
0x1402be53a  test    sil, sil
0x1402be53d  jnz     short loc_1402BE544
0x1402be53f  btr     dword ptr [rbx+18h], 0Ch
0x1402be544  btr     dword ptr [rbx+18h], 0Dh
0x1402be549  mov     rax, [rdi+0B8h]
0x1402be550  mov     rcx, [rax+148h]
0x1402be557  mov     rcx, [rcx+88h]; Resource
0x1402be55e  call    cs:__imp_ExReleaseResourceLite
0x1402be565  nop     dword ptr [rax+rax+00h]
0x1402be56a  lock dec dword ptr [rdi+0D4h]
0x1402be571  mov     rcx, [rbp+80h]; FileObject
0x1402be578  test    rcx, rcx
0x1402be57b  jz      short loc_1402BE5A2
0x1402be57d  xor     r8d, r8d; UninitializeEvent
0x1402be580  xor     edx, edx; TruncateSize
0x1402be582  call    cs:__imp_CcUninitializeCacheMap
0x1402be589  nop     dword ptr [rax+rax+00h]
0x1402be58e  mov     rcx, [rbp+80h]; Object
0x1402be595  call    cs:__imp_ObfDereferenceObject
0x1402be59c  nop     dword ptr [rax+rax+00h]
0x1402be5a1  nop
0x1402be5a2  add     rsp, 38h
0x1402be5a6  pop     rdi
0x1402be5a7  pop     rsi
0x1402be5a8  pop     rbp
0x1402be5a9  pop     rbx
0x1402be5aa  retn
```
