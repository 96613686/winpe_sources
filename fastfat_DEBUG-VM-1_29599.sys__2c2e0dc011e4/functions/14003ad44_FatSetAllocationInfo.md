# FatSetAllocationInfo

- ea: `0x14003ad44`
- end: `0x14003b003`
- name: `FatSetAllocationInfo`
- size: `703`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140039e94`

## callees

- `0x140001858`
- `0x140001d4c`
- `0x140020458`
- `0x1400226b8`
- `0x140023ad4`
- `0x140033270`
- `0x14003ad44`
- `0x140044bac`

## import_xrefs

- `ntoskrnl!CcUninitializeCacheMap` at `0x14003afd8`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14005e4e2`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14003afd8`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14005e4e2`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x14003afb9`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x14003afb9`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14003aeb3`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14003aeb3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003aef1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003aef1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003afef`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e500`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003afef`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e500`
- `ntoskrnl!CcSetFileSizes` at `0x14003af40`
- `ntoskrnl!CcSetFileSizes` at `0x14003af40`

## pseudocode

```c
__int64 __fastcall FatSetAllocationInfo(__int64 a1, __int64 a2, __int64 a3, struct _FILE_OBJECT *a4)
{
  int v9; // r8d
  unsigned int *v10; // r10
  unsigned int v11; // r12d
  char v12; // dl
  unsigned int v13; // r15d
  _DWORD *v14; // rsi
  int v15; // ecx
  _QWORD *p_DataSectionObject; // rax
  unsigned int v17; // esi
  char v18; // [rsp+50h] [rbp-58h]
  char v19; // [rsp+51h] [rbp-57h]
  int v20; // [rsp+54h] [rbp-54h]
  union _LARGE_INTEGER *NewFileSize; // [rsp+68h] [rbp-40h]
  char v22; // [rsp+B8h] [rbp+10h]

  if ( *(_WORD *)a3 == 1283 )
    return 3221225488LL;
  NewFileSize = *(union _LARGE_INTEGER **)(a2 + 24);
  if ( !(unsigned __int8)FatIsIoRangeValid(a1, NewFileSize->QuadPart, 0, *(unsigned int *)(a3 + 132)) )
    return 3221225599LL;
  v11 = 0;
  v20 = v9;
  v18 = v9;
  v12 = 0;
  v22 = 0;
  v19 = 0;
  v13 = *v10;
  v14 = (_DWORD *)(a3 + 192);
  if ( (*(_DWORD *)(*(_QWORD *)(a3 + 184) + 200LL) & 0x400000) != 0 && (*v14 & 0x8000) != 0 )
    v20 = *(_DWORD *)(a3 + 132);
  v15 = a3 + 24;
  if ( *(_QWORD *)(a3 + 24) == -1 )
  {
    FatLookupFileAllocationSize(a1, a3);
    v15 = a3 + 24;
    v12 = 0;
  }
  p_DataSectionObject = &a4->SectionObjectPointer->DataSectionObject;
  if ( *p_DataSectionObject && !p_DataSectionObject[1] && (*(_DWORD *)(a2 + 16) & 2) == 0 )
  {
    FatInitializeCacheMap((int)a4, v15, 0, (int)&qword_140017D90, (PVOID)a3);
    v12 = 1;
    v22 = 1;
  }
  *v14 |= 2u;
  a4->Flags |= 0x1000u;
  v17 = v13 + v20;
  if ( v13 + v20 > *(_DWORD *)(a3 + 24) )
  {
    FatAddFileAllocation(a1);
LABEL_29:
    v12 = v22;
    goto LABEL_30;
  }
  if ( *(_DWORD *)(a3 + 32) <= v17 )
  {
LABEL_25:
    FatTruncateFileAllocation(a1, a3, v17);
    if ( v18 )
    {
      CcSetFileSizes(a4, (PCC_FILE_SIZES)(a3 + 24));
      FatSetFileSizeInDirent(a1, a3);
      if ( !*(_QWORD *)(a3 + 536) )
        FatSetFullFileNameInFcb(a1);
      FsRtlNotifyFullReportChange(
        *(PNOTIFY_SYNC *)(*(_QWORD *)(a3 + 184) + 816LL),
        (PLIST_ENTRY)(*(_QWORD *)(a3 + 184) + 800LL),
        (PSTRING)(a3 + 528),
        *(_WORD *)(a3 + 528) - *(_WORD *)(a3 + 544),
        0,
        0,
        8u,
        3u,
        0);
    }
    goto LABEL_29;
  }
  if ( !*(_DWORD *)(a3 + 240) )
  {
    if ( !MmCanFileBeTruncated(a4->SectionObjectPointer, NewFileSize) )
    {
      v11 = -1073741245;
      goto LABEL_29;
    }
    v18 = 1;
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a3 + 16), 1u);
    v19 = 1;
    *(_DWORD *)(a3 + 32) = v13;
    if ( *(_DWORD *)(a3 + 40) > v13 )
      *(_DWORD *)(a3 + 40) = v13;
    if ( *(_DWORD *)(a3 + 280) > v13 )
      *(_DWORD *)(a3 + 280) = v13;
    goto LABEL_25;
  }
  v11 = -1073740747;
LABEL_30:
  if ( v12 )
    CcUninitializeCacheMap(a4, 0, 0);
  if ( v19 )
    ExReleaseResourceLite(*(PERESOURCE *)(a3 + 16));
  return v11;
}

```

## disassembly

```asm
0x14003ad44  mov     [rsp+arg_18], r9
0x14003ad49  mov     [rsp+arg_10], r8
0x14003ad4e  push    rbx
0x14003ad4f  push    rsi
0x14003ad50  push    rdi
0x14003ad51  push    r12
0x14003ad53  push    r13
0x14003ad55  push    r14
0x14003ad57  push    r15
0x14003ad59  sub     rsp, 70h
0x14003ad5d  mov     rdi, r9
0x14003ad60  mov     rbx, r8
0x14003ad63  mov     r13, rdx
0x14003ad66  mov     r14, rcx
0x14003ad69  mov     eax, 503h
0x14003ad6e  cmp     [r8], ax
0x14003ad72  jnz     short loc_14003AD8A
0x14003ad74  mov     eax, 0C0000010h
0x14003ad79  add     rsp, 70h
0x14003ad7d  pop     r15
0x14003ad7f  pop     r14
0x14003ad81  pop     r13
0x14003ad83  pop     r12
0x14003ad85  pop     rdi
0x14003ad86  pop     rsi
0x14003ad87  pop     rbx
0x14003ad88  retn
0x14003ad8a  mov     r10, [rdx+18h]
0x14003ad8e  mov     [rsp+0A8h+NewFileSize], r10
0x14003ad93  mov     r9d, [r8+84h]
0x14003ad9a  xor     r8d, r8d
0x14003ad9d  mov     rdx, [r10]
0x14003ada0  call    FatIsIoRangeValid
0x14003ada5  test    al, al
0x14003ada7  jnz     short loc_14003ADB0
0x14003ada9  mov     eax, 0C000007Fh
0x14003adae  jmp     short loc_14003AD79
0x14003adb0  xor     r12d, r12d
0x14003adb3  mov     [rsp+0A8h+var_54], r8d
0x14003adb8  mov     [rsp+0A8h+var_58], r8b
0x14003adbd  xor     dl, dl
0x14003adbf  mov     [rsp+0A8h+arg_8], dl
0x14003adc6  mov     [rsp+0A8h+var_57], dl
0x14003adca  mov     [rsp+0A8h+var_50], r8d
0x14003adcf  mov     [rsp+0A8h+var_4C], r8d
0x14003add4  mov     [rsp+0A8h+var_48], r8d
0x14003add9  mov     r15d, [r10]
0x14003addc  mov     rax, [rbx+0B8h]
0x14003ade3  mov     ecx, [rax+0C8h]
0x14003ade9  lea     rsi, [rbx+0C0h]
0x14003adf0  bt      ecx, 16h
0x14003adf4  jnb     short loc_14003AE08
0x14003adf6  test    dword ptr [rsi], 8000h
0x14003adfc  jz      short loc_14003AE08
0x14003adfe  mov     eax, [rbx+84h]
0x14003ae04  mov     [rsp+0A8h+var_54], eax
0x14003ae08  lea     rcx, [rbx+18h]
0x14003ae0c  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x14003ae10  jnz     short loc_14003AE24
0x14003ae12  mov     rdx, rbx
0x14003ae15  mov     rcx, r14
0x14003ae18  call    FatLookupFileAllocationSize
0x14003ae1d  lea     rcx, [rbx+18h]
0x14003ae21  mov     dl, r12b
0x14003ae24  mov     rax, [rdi+28h]
0x14003ae28  cmp     [rax], r12
0x14003ae2b  jz      short loc_14003AE5E
0x14003ae2d  cmp     [rax+8], r12
0x14003ae31  jnz     short loc_14003AE5E
0x14003ae33  mov     eax, [r13+10h]
0x14003ae37  test    al, 2
0x14003ae39  jnz     short loc_14003AE5E
0x14003ae3b  mov     [rsp+0A8h+StreamName], rbx; PVOID
0x14003ae40  lea     r9, qword_140017D90; int
0x14003ae47  xor     r8d, r8d; int
0x14003ae4a  mov     rdx, rcx; int
0x14003ae4d  mov     rcx, rdi; int
0x14003ae50  call    FatInitializeCacheMap
0x14003ae55  mov     dl, 1
0x14003ae57  mov     [rsp+0A8h+arg_8], dl
0x14003ae5e  or      dword ptr [rsi], 2
0x14003ae61  mov     eax, [rdi+50h]
0x14003ae64  bts     eax, 0Ch
0x14003ae68  mov     [rdi+50h], eax
0x14003ae6b  mov     esi, [rsp+0A8h+var_54]
0x14003ae6f  add     esi, r15d
0x14003ae72  cmp     esi, [rbx+18h]
0x14003ae75  jbe     short loc_14003AE8D
0x14003ae77  mov     r9d, esi
0x14003ae7a  mov     r8, rdi
0x14003ae7d  mov     rdx, rbx
0x14003ae80  mov     rcx, r14
0x14003ae83  call    FatAddFileAllocation
0x14003ae88  jmp     loc_14003AFC5
0x14003ae8d  cmp     [rbx+20h], esi
0x14003ae90  jbe     loc_14003AF20
0x14003ae96  cmp     dword ptr [rbx+0F0h], 0
0x14003ae9d  jz      short loc_14003AEAA
0x14003ae9f  mov     r12d, 0C0000435h
0x14003aea5  jmp     loc_14003AFCC
0x14003aeaa  mov     rdx, [rsp+0A8h+NewFileSize]; NewFileSize
0x14003aeaf  mov     rcx, [rdi+28h]; SectionPointer
0x14003aeb3  call    cs:__imp_MmCanFileBeTruncated
0x14003aeba  nop     dword ptr [rax+rax+00h]
0x14003aebf  test    al, al
0x14003aec1  jnz     short loc_14003AECE
0x14003aec3  mov     r12d, 0C0000243h
0x14003aec9  jmp     loc_14003AFC5
0x14003aece  mov     [rsp+0A8h+var_58], 1
0x14003aed3  mov     eax, [rbx+20h]
0x14003aed6  mov     [rsp+0A8h+var_50], eax
0x14003aeda  mov     eax, [rbx+28h]
0x14003aedd  mov     [rsp+0A8h+var_4C], eax
0x14003aee1  mov     eax, [rbx+118h]
0x14003aee7  mov     [rsp+0A8h+var_48], eax
0x14003aeeb  mov     dl, 1; Wait
0x14003aeed  mov     rcx, [rbx+10h]; Resource
0x14003aef1  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14003aef8  nop     dword ptr [rax+rax+00h]
0x14003aefd  mov     [rsp+0A8h+var_57], 1
0x14003af02  mov     [rbx+20h], r15d
0x14003af06  cmp     [rbx+28h], r15d
0x14003af0a  jbe     short loc_14003AF10
0x14003af0c  mov     [rbx+28h], r15d
0x14003af10  cmp     [rbx+118h], r15d
0x14003af17  jbe     short loc_14003AF20
0x14003af19  mov     [rbx+118h], r15d
0x14003af20  mov     r8d, esi
0x14003af23  mov     rdx, rbx
0x14003af26  mov     rcx, r14
0x14003af29  call    FatTruncateFileAllocation
0x14003af2e  cmp     [rsp+0A8h+var_58], 0
0x14003af33  jz      loc_14003AFC5
0x14003af39  lea     rdx, [rbx+18h]; FileSizes
0x14003af3d  mov     rcx, rdi; FileObject
0x14003af40  call    cs:__imp_CcSetFileSizes
0x14003af47  nop     dword ptr [rax+rax+00h]
0x14003af4c  xor     esi, esi
0x14003af4e  mov     [rsp+0A8h+var_58], sil
0x14003af53  mov     rdx, rbx
0x14003af56  mov     rcx, r14
0x14003af59  call    FatSetFileSizeInDirent
0x14003af5e  cmp     [rbx+218h], rsi
0x14003af65  jnz     short loc_14003AF72
0x14003af67  mov     rdx, rbx
0x14003af6a  mov     rcx, r14; int
0x14003af6d  call    FatSetFullFileNameInFcb
0x14003af72  lea     r8, [rbx+210h]; FullTargetName
0x14003af79  mov     rcx, [rbx+0B8h]
0x14003af80  movzx   r9d, word ptr [r8]
0x14003af84  sub     r9w, [rbx+220h]; TargetNameOffset
0x14003af8c  lea     rdx, [rcx+320h]; NotifyList
0x14003af93  mov     [rsp+0A8h+TargetContext], rsi; TargetContext
0x14003af98  mov     [rsp+0A8h+Action], 3; Action
0x14003afa0  mov     [rsp+0A8h+FilterMatch], 8; FilterMatch
0x14003afa8  mov     [rsp+0A8h+NormalizedParentName], rsi; NormalizedParentName
0x14003afad  mov     [rsp+0A8h+StreamName], rsi; StreamName
0x14003afb2  mov     rcx, [rcx+330h]; NotifySync
0x14003afb9  call    cs:__imp_FsRtlNotifyFullReportChange
0x14003afc0  nop     dword ptr [rax+rax+00h]
0x14003afc5  mov     dl, [rsp+0A8h+arg_8]
0x14003afcc  test    dl, dl
0x14003afce  jz      short loc_14003AFE4
0x14003afd0  xor     r8d, r8d; UninitializeEvent
0x14003afd3  xor     edx, edx; TruncateSize
0x14003afd5  mov     rcx, rdi; FileObject
0x14003afd8  call    cs:__imp_CcUninitializeCacheMap
0x14003afdf  nop     dword ptr [rax+rax+00h]
0x14003afe4  cmp     [rsp+0A8h+var_57], 0
0x14003afe9  jz      short loc_14003AFFB
0x14003afeb  mov     rcx, [rbx+10h]; Resource
0x14003afef  call    cs:__imp_ExReleaseResourceLite
0x14003aff6  nop     dword ptr [rax+rax+00h]
0x14003affb  mov     eax, r12d
0x14003affe  jmp     loc_14003AD79
0x14005e47d  push    rbp
0x14005e47f  sub     rsp, 50h
0x14005e483  mov     rbp, rdx
0x14005e486  movzx   eax, cl
0x14005e489  test    cl, cl
0x14005e48b  jz      short loc_14005E4CD
0x14005e48d  cmp     byte ptr [rbp+50h], 0
0x14005e491  jz      short loc_14005E4CD
0x14005e493  mov     eax, [rbp+58h]
0x14005e496  mov     rdx, [rbp+0C0h]
0x14005e49d  mov     [rdx+20h], eax
0x14005e4a0  mov     eax, [rbp+5Ch]
0x14005e4a3  mov     [rdx+28h], eax
0x14005e4a6  mov     eax, [rbp+60h]
0x14005e4a9  mov     [rdx+118h], eax
0x14005e4af  mov     rcx, [rbp+0C8h]
0x14005e4b6  mov     rax, [rcx+28h]
0x14005e4ba  cmp     qword ptr [rax+8], 0
0x14005e4bf  jz      short loc_14005E4CD
0x14005e4c1  mov     rcx, [rax+8]
0x14005e4c5  mov     rax, [rdx+20h]
0x14005e4c9  mov     [rcx+8], rax
0x14005e4cd  cmp     byte ptr [rbp+0B8h], 0
0x14005e4d4  jz      short loc_14005E4EF
0x14005e4d6  xor     r8d, r8d; UninitializeEvent
0x14005e4d9  xor     edx, edx; TruncateSize
0x14005e4db  mov     rcx, [rbp+0C8h]; FileObject
0x14005e4e2  call    cs:__imp_CcUninitializeCacheMap
0x14005e4e9  nop     dword ptr [rax+rax+00h]
0x14005e4ee  nop
0x14005e4ef  cmp     byte ptr [rbp+51h], 0
0x14005e4f3  jz      short loc_14005E50D
0x14005e4f5  mov     rcx, [rbp+0C0h]
0x14005e4fc  mov     rcx, [rcx+10h]; Resource
0x14005e500  call    cs:__imp_ExReleaseResourceLite
0x14005e507  nop     dword ptr [rax+rax+00h]
0x14005e50c  nop
0x14005e50d  add     rsp, 50h
0x14005e511  pop     rbp
0x14005e512  retn
```
