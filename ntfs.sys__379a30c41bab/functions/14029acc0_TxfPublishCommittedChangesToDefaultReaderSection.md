# TxfPublishCommittedChangesToDefaultReaderSection

- ea: `0x14029acc0`
- end: `0x14029af66`
- name: `TxfPublishCommittedChangesToDefaultReaderSection`
- size: `678`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400415b4`
- `0x14019dcc8`

## callees

- `0x140150c10`
- `0x140163fc8`
- `0x1402765a0`
- `0x14029acc0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14029af2e`
- `ntoskrnl!ObfDereferenceObject` at `0x1402be5e5`
- `ntoskrnl!ObfDereferenceObject` at `0x14029af2e`
- `ntoskrnl!ObfDereferenceObject` at `0x1402be5e5`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14029af1a`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1402be5d2`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14029af1a`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1402be5d2`
- `ntoskrnl!CcPurgeCacheSection` at `0x14029ade3`
- `ntoskrnl!CcPurgeCacheSection` at `0x14029ade3`
- `ntoskrnl!MmForceSectionClosed` at `0x14029ae57`
- `ntoskrnl!MmForceSectionClosed` at `0x14029ae57`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029aeb2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029aec9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402be54e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402be56d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029aeb2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029aec9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402be54e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402be56d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029ad1c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029ae81`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402be51c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029ad1c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029ae81`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402be51c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029ad87`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029aef5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029af4d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402be5ae`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029ad87`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029aef5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029af4d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402be5ae`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14029acf9`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14029acf9`

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
0x14029acc0  mov     rax, rsp
0x14029acc3  mov     [rax+10h], rdx
0x14029acc7  push    rbx
0x14029acc8  push    rsi
0x14029acc9  push    rdi
0x14029acca  push    r14
0x14029accc  push    r15
0x14029acce  sub     rsp, 40h
0x14029acd2  mov     rdi, rdx
0x14029acd5  mov     r15, rcx
0x14029acd8  mov     qword ptr [rax+18h], 0
0x14029ace0  mov     rbx, [rdx+210h]
0x14029ace7  lea     r14, [rdx+0B8h]
0x14029acee  mov     rcx, [rbx+40h]
0x14029acf2  mov     rcx, [rcx+88h]; Resource
0x14029acf9  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14029ad00  nop     dword ptr [rax+rax+00h]
0x14029ad05  test    al, al
0x14029ad07  jnz     short loc_14029AD28
0x14029ad09  mov     rax, [r14]
0x14029ad0c  mov     rcx, [rax+148h]
0x14029ad13  mov     dl, 1; Wait
0x14029ad15  mov     rcx, [rcx+88h]; Resource
0x14029ad1c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14029ad23  nop     dword ptr [rax+rax+00h]
0x14029ad28  mov     rsi, [rbx+70h]
0x14029ad2c  test    rsi, rsi
0x14029ad2f  jnz     short loc_14029AD36
0x14029ad31  btr     dword ptr [rbx+18h], 0Ch
0x14029ad36  mov     rax, [rdi+210h]
0x14029ad3d  test    dword ptr [rax+18h], 1000h
0x14029ad44  jz      loc_14029AF3C
0x14029ad4a  mov     ecx, 2000h
0x14029ad4f  test    [rbx+18h], ecx
0x14029ad52  jnz     loc_14029AF3C
0x14029ad58  mov     [rsp+68h+arg_18], rbx
0x14029ad60  mov     rsi, [rsi]
0x14029ad63  mov     [rsp+68h+var_30], rsi
0x14029ad68  lock inc dword ptr [rsi+40h]
0x14029ad6c  lock inc dword ptr [rdi+0D4h]
0x14029ad73  or      [rbx+18h], ecx
0x14029ad76  mov     rax, [r14]
0x14029ad79  mov     rcx, [rax+148h]
0x14029ad80  mov     rcx, [rcx+88h]; Resource
0x14029ad87  call    cs:__imp_ExReleaseResourceLite
0x14029ad8e  nop     dword ptr [rax+rax+00h]
0x14029ad93  nop
0x14029ad94  lea     rax, [rsp+68h+FileObject]
0x14029ad9c  mov     [rsp+68h+var_40], rax
0x14029ada1  mov     [rsp+68h+var_48], 0
0x14029adaa  mov     r9b, 4
0x14029adad  xor     r8d, r8d
0x14029adb0  mov     rdx, rdi
0x14029adb3  mov     rcx, r15
0x14029adb6  call    NtfsCreateInternalAttributeStream
0x14029adbb  lea     r8, [rdi+18h]
0x14029adbf  mov     rdx, rdi
0x14029adc2  mov     rcx, [rsp+68h+FileObject]
0x14029adca  call    NtfsSetCcFileSizes
0x14029adcf  xor     r9d, r9d; Flags
0x14029add2  xor     r8d, r8d; Length
0x14029add5  xor     edx, edx; FileOffset
0x14029add7  mov     rcx, [rsp+68h+FileObject]
0x14029addf  mov     rcx, [rcx+28h]; SectionObjectPointer
0x14029ade3  call    cs:__imp_CcPurgeCacheSection
0x14029adea  nop     dword ptr [rax+rax+00h]
0x14029adef  test    al, al
0x14029adf1  jnz     short loc_14029AE6E
0x14029adf3  cmp     qword ptr [rdi+118h], 0
0x14029adfb  jnz     short loc_14029AE20
0x14029adfd  mov     [rsp+68h+var_40], 0
0x14029ae06  mov     [rsp+68h+var_48], 0
0x14029ae0f  xor     r9d, r9d
0x14029ae12  xor     r8d, r8d
0x14029ae15  mov     rdx, rdi
0x14029ae18  mov     rcx, r15
0x14029ae1b  call    NtfsCreateInternalAttributeStream
0x14029ae20  mov     [rsp+68h+var_38], 0
0x14029ae29  mov     eax, [rdi+20h]
0x14029ae2c  mov     dword ptr [rsp+68h+var_48], eax
0x14029ae30  lea     r9, [rsp+68h+var_38]
0x14029ae35  mov     r8, [rdi+118h]
0x14029ae3c  mov     rdx, [rsp+68h+FileObject]
0x14029ae44  call    TxfCopyDataRange
0x14029ae49  mov     dl, 1; DelayClose
0x14029ae4b  mov     rcx, [rsp+68h+FileObject]
0x14029ae53  mov     rcx, [rcx+28h]; SectionObjectPointer
0x14029ae57  call    cs:__imp_MmForceSectionClosed
0x14029ae5e  nop     dword ptr [rax+rax+00h]
0x14029ae63  mov     rax, [rdi+210h]
0x14029ae6a  or      dword ptr [rax+18h], 40h
0x14029ae6e  mov     rax, [r14]
0x14029ae71  mov     rcx, [rax+148h]
0x14029ae78  mov     dl, 1; Wait
0x14029ae7a  mov     rcx, [rcx+88h]; Resource
0x14029ae81  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14029ae88  nop     dword ptr [rax+rax+00h]
0x14029ae8d  or      eax, 0FFFFFFFFh
0x14029ae90  lock xadd [rsi+40h], eax
0x14029ae95  cmp     eax, 1
0x14029ae98  jnz     short loc_14029AEDD
0x14029ae9a  mov     eax, [rsi+44h]
0x14029ae9d  test    al, 1
0x14029ae9f  jz      short loc_14029AEA8
0x14029aea1  xor     eax, eax
0x14029aea3  mov     [rsi], ax
0x14029aea6  jmp     short loc_14029AEBE
0x14029aea8  mov     rdx, rsi; Entry
0x14029aeab  lea     rcx, NtfsScbNonpagedLookasideList; Lookaside
0x14029aeb2  call    cs:__imp_ExFreeToLookasideListEx
0x14029aeb9  nop     dword ptr [rax+rax+00h]
0x14029aebe  mov     rdx, [rbx+70h]; Entry
0x14029aec2  lea     rcx, TxfDefaultReaderSectionLookasideList; Lookaside
0x14029aec9  call    cs:__imp_ExFreeToLookasideListEx
0x14029aed0  nop     dword ptr [rax+rax+00h]
0x14029aed5  mov     qword ptr [rbx+70h], 0
0x14029aedd  and     dword ptr [rbx+18h], 0FFFFCFFFh
0x14029aee4  mov     rax, [r14]
0x14029aee7  mov     rcx, [rax+148h]
0x14029aeee  mov     rcx, [rcx+88h]; Resource
0x14029aef5  call    cs:__imp_ExReleaseResourceLite
0x14029aefc  nop     dword ptr [rax+rax+00h]
0x14029af01  lock dec dword ptr [rdi+0D4h]
0x14029af08  mov     rcx, [rsp+68h+FileObject]; FileObject
0x14029af10  test    rcx, rcx
0x14029af13  jz      short loc_14029AF59
0x14029af15  xor     r8d, r8d; UninitializeEvent
0x14029af18  xor     edx, edx; TruncateSize
0x14029af1a  call    cs:__imp_CcUninitializeCacheMap
0x14029af21  nop     dword ptr [rax+rax+00h]
0x14029af26  mov     rcx, [rsp+68h+FileObject]; Object
0x14029af2e  call    cs:__imp_ObfDereferenceObject
0x14029af35  nop     dword ptr [rax+rax+00h]
0x14029af3a  jmp     short loc_14029AF59
0x14029af3c  mov     rax, [r14]
0x14029af3f  mov     rcx, [rax+148h]
0x14029af46  mov     rcx, [rcx+88h]; Resource
0x14029af4d  call    cs:__imp_ExReleaseResourceLite
0x14029af54  nop     dword ptr [rax+rax+00h]
0x14029af59  add     rsp, 40h
0x14029af5d  pop     r15
0x14029af5f  pop     r14
0x14029af61  pop     rdi
0x14029af62  pop     rsi
0x14029af63  pop     rbx
0x14029af64  retn
0x1402be4e8  push    rbx
0x1402be4ea  push    rbp
0x1402be4eb  push    rsi
0x1402be4ec  push    rdi
0x1402be4ed  sub     rsp, 38h
0x1402be4f1  mov     rbp, rdx
0x1402be4f4  mov     sil, cl
0x1402be4f7  test    cl, cl
0x1402be4f9  jz      short loc_1402BE501
0x1402be4fb  mov     al, cs:NtfsStatusDebugFlags
0x1402be501  mov     rdi, [rbp+78h]
0x1402be505  mov     rax, [rdi+0B8h]
0x1402be50c  mov     rcx, [rax+148h]
0x1402be513  mov     dl, 1; Wait
0x1402be515  mov     rcx, [rcx+88h]; Resource
0x1402be51c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1402be523  nop     dword ptr [rax+rax+00h]
0x1402be528  mov     rdx, [rbp+38h]; Entry
0x1402be52c  or      eax, 0FFFFFFFFh
0x1402be52f  lock xadd [rdx+40h], eax
0x1402be534  cmp     eax, 1
0x1402be537  jnz     short loc_1402BE583
0x1402be539  mov     eax, [rdx+44h]
0x1402be53c  test    al, 1
0x1402be53e  jz      short loc_1402BE547
0x1402be540  xor     eax, eax
0x1402be542  mov     [rdx], ax
0x1402be545  jmp     short loc_1402BE55B
0x1402be547  lea     rcx, NtfsScbNonpagedLookasideList; Lookaside
0x1402be54e  call    cs:__imp_ExFreeToLookasideListEx
0x1402be555  nop     dword ptr [rax+rax+00h]
0x1402be55a  nop
0x1402be55b  mov     rbx, [rbp+88h]
0x1402be562  mov     rdx, [rbx+70h]; Entry
0x1402be566  lea     rcx, TxfDefaultReaderSectionLookasideList; Lookaside
0x1402be56d  call    cs:__imp_ExFreeToLookasideListEx
0x1402be574  nop     dword ptr [rax+rax+00h]
0x1402be579  mov     qword ptr [rbx+70h], 0
0x1402be581  jmp     short loc_1402BE58A
0x1402be583  mov     rbx, [rbp+88h]
0x1402be58a  test    sil, sil
0x1402be58d  jnz     short loc_1402BE594
0x1402be58f  btr     dword ptr [rbx+18h], 0Ch
0x1402be594  btr     dword ptr [rbx+18h], 0Dh
0x1402be599  mov     rax, [rdi+0B8h]
0x1402be5a0  mov     rcx, [rax+148h]
0x1402be5a7  mov     rcx, [rcx+88h]; Resource
0x1402be5ae  call    cs:__imp_ExReleaseResourceLite
0x1402be5b5  nop     dword ptr [rax+rax+00h]
0x1402be5ba  lock dec dword ptr [rdi+0D4h]
0x1402be5c1  mov     rcx, [rbp+80h]; FileObject
0x1402be5c8  test    rcx, rcx
0x1402be5cb  jz      short loc_1402BE5F2
0x1402be5cd  xor     r8d, r8d; UninitializeEvent
0x1402be5d0  xor     edx, edx; TruncateSize
0x1402be5d2  call    cs:__imp_CcUninitializeCacheMap
0x1402be5d9  nop     dword ptr [rax+rax+00h]
0x1402be5de  mov     rcx, [rbp+80h]; Object
0x1402be5e5  call    cs:__imp_ObfDereferenceObject
0x1402be5ec  nop     dword ptr [rax+rax+00h]
0x1402be5f1  nop
0x1402be5f2  add     rsp, 38h
0x1402be5f6  pop     rdi
0x1402be5f7  pop     rsi
0x1402be5f8  pop     rbp
0x1402be5f9  pop     rbx
0x1402be5fa  retn
```
