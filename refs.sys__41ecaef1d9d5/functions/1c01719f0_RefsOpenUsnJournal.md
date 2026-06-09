# RefsOpenUsnJournal

- ea: `0x1c01719f0`
- end: `0x1c0171cc2`
- name: `RefsOpenUsnJournal`
- size: `722`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1c016fc10`
- `0x1c01a629c`
- `0x1c01ceb00`

## callees

- `0x1c0003eb4`
- `0x1c0003fb0`
- `0x1c00046d4`
- `0x1c0005818`
- `0x1c003b27c`
- `0x1c00b33a4`
- `0x1c01719f0`
- `0x1c0171cc8`
- `0x1c01d1838`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0171ac4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0171ac4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0171c99`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c018070b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0171c99`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c018070b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0171c81`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01806f3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0171c81`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01806f3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0171a5a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0171a5a`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c0171a76`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c0171c72`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c01806e0`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c0171a76`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c0171c72`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c01806e0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1c0171ae7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1c0171ae7`

## pseudocode

```c
void __fastcall RefsOpenUsnJournal(
        __int64 a1,
        __int64 a2,
        unsigned __int8 a3,
        char a4,
        char a5,
        __int128 *a6,
        _QWORD *a7)
{
  int v7; // r15d
  char v10; // r12
  char v11; // si
  struct _ERESOURCE *v12; // r13
  char v13; // dl
  __int64 v14; // r8
  __int64 v15; // r14
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rax
  __int64 v19; // r14
  _BYTE v20[5]; // [rsp+53h] [rbp-75h] BYREF
  __int64 v21; // [rsp+58h] [rbp-70h]
  __int64 v22; // [rsp+60h] [rbp-68h]
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-60h] BYREF
  __int128 v24; // [rsp+78h] [rbp-50h]
  char v25; // [rsp+E8h] [rbp+20h] BYREF

  v25 = a4;
  v7 = a3;
  v22 = 0;
  v21 = 0;
  DestinationString = 0;
  v10 = 0;
  v11 = 0;
  v24 = *(_OWORD *)(a2 + 896);
  v12 = (struct _ERESOURCE *)(a2 + 1176);
  ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1176), 1u);
  RtlCaptureStackBackTrace(0, 9u, (PVOID *)(a2 + 1280), 0);
  *(_DWORD *)(a1 + 4) |= 0x2000u;
  *(_DWORD *)(a1 + 12) |= 0x100u;
  if ( (unsigned __int8)RefsIsMinstoreTransactionActive(a1) )
    MsSetDrainStarveExclusive(*(_QWORD *)(a1 + 24));
  v15 = *(_QWORD *)(a2 + 40);
  if ( v15 )
  {
    v19 = *(_QWORD *)(v15 + 120);
    v22 = v19;
    LOBYTE(v14) = v13;
    RefsAcquireExclusivePagingIoSpecifyWait(a1, v19, v14);
    RefsAcquireExclusiveScbWithFlags(a1, *(_QWORD *)(a2 + 40), 0);
    v18 = v21;
  }
  else
  {
    DestinationString.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)17, 0x1Cu, 0x6F4D6552u);
    DestinationString.MaximumLength = 28;
    RtlCopyUnicodeString(&DestinationString, &REFS_CHANGE_JOURNAL_FILE_NAME);
    RefsAcquireExclusiveScbWithFlags(a1, *(_QWORD *)(a2 + 80), 0);
    v10 = 1;
    ConditionallyCreateOrOpenFileSystemFile(
      a1,
      a2,
      v16,
      (unsigned int)&DestinationString,
      *(_QWORD *)(a2 + 80),
      (_BYTE)v7 != 0);
    v18 = v21;
    if ( v21 )
      v19 = *(_QWORD *)(v21 + 120);
    else
      v19 = 0;
    v22 = v19;
    if ( v21 )
      v11 = 1;
  }
  if ( v19 )
  {
    *(_OWORD *)(a2 + 896) = *(_OWORD *)(v19 + 8);
    if ( a5 )
    {
      if ( !(_BYTE)v7 )
        *(_DWORD *)(a2 + 4) |= 0x200000u;
      RefsSetupUsnJournal(a1, a2, v19, v7, 0, a6);
    }
    else
    {
      if ( !v11 )
        goto LABEL_18;
      v20[0] = 0;
      LOBYTE(v17) = 1;
      RefsDecrementCloseCounts(a1, v18, 0, v17, 0, 1, (__int64)v20);
    }
    v11 = 0;
    v18 = v21;
LABEL_18:
    if ( a7 )
      *a7 = v18;
  }
  if ( v10 )
    RefsReleaseFcb(a1, *(_QWORD *)(*(_QWORD *)(a2 + 80) + 120LL));
  *(_DWORD *)(a1 + 4) &= 0xFFFFCFFF;
  RtlCaptureStackBackTrace(0, 9u, (PVOID *)(a2 + 1352), 0);
  ExReleaseResourceLite(v12);
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  if ( v11 )
  {
    v25 = 0;
    *(_DWORD *)(v19 + 4) &= ~0x100u;
    RefsDecrementCloseCounts(a1, v21, 0, 1, 0, 0, (__int64)&v25);
  }
}

```

## disassembly

```asm
0x1c01719f0  mov     rax, rsp
0x1c01719f3  mov     [rax+20h], r9b
0x1c01719f7  mov     [rax+10h], rdx
0x1c01719fb  mov     [rax+8], rcx
0x1c01719ff  push    rbx
0x1c0171a00  push    rsi
0x1c0171a01  push    rdi
0x1c0171a02  push    r12
0x1c0171a04  push    r13
0x1c0171a06  push    r14
0x1c0171a08  push    r15
0x1c0171a0a  sub     rsp, 90h
0x1c0171a11  movzx   r15d, r8b
0x1c0171a15  mov     rdi, rdx
0x1c0171a18  mov     rbx, rcx
0x1c0171a1b  xor     r14d, r14d
0x1c0171a1e  mov     [rax-68h], r14
0x1c0171a22  mov     [rax-70h], r14
0x1c0171a26  xorps   xmm0, xmm0
0x1c0171a29  movups  xmmword ptr [rax-60h], xmm0
0x1c0171a2d  mov     r12b, r14b
0x1c0171a30  mov     [rax-77h], r14b
0x1c0171a34  movzx   esi, r14b
0x1c0171a38  mov     [rax-78h], sil
0x1c0171a3c  mov     [rax-76h], r14b
0x1c0171a40  movups  xmm0, xmmword ptr [rdx+380h]
0x1c0171a47  movdqu  xmmword ptr [rax-50h], xmm0
0x1c0171a4c  lea     r13, [rdx+498h]
0x1c0171a53  lea     edx, [r14+1]; Wait
0x1c0171a57  mov     rcx, r13; Resource
0x1c0171a5a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1c0171a61  nop     dword ptr [rax+rax+00h]
0x1c0171a66  lea     r8, [rdi+500h]; BackTrace
0x1c0171a6d  xor     r9d, r9d; BackTraceHash
0x1c0171a70  lea     edx, [r14+9]; FramesToCapture
0x1c0171a74  xor     ecx, ecx; FramesToSkip
0x1c0171a76  call    cs:__imp_RtlCaptureStackBackTrace
0x1c0171a7d  nop     dword ptr [rax+rax+00h]
0x1c0171a82  bts     dword ptr [rbx+4], 0Dh
0x1c0171a87  lea     edx, [r14+1]
0x1c0171a8b  mov     [rsp+0C8h+var_76], dl
0x1c0171a8f  bts     dword ptr [rbx+0Ch], 8
0x1c0171a94  mov     rcx, rbx
0x1c0171a97  call    RefsIsMinstoreTransactionActive
0x1c0171a9c  test    al, al
0x1c0171a9e  jnz     loc_1C0171BAF
0x1c0171aa4  mov     r14, [rdi+28h]
0x1c0171aa8  test    r14, r14
0x1c0171aab  jnz     loc_1C0171BBD
0x1c0171ab1  mov     r8d, 6F4D6552h; Tag
0x1c0171ab7  mov     r14d, 1Ch
0x1c0171abd  mov     edx, r14d; NumberOfBytes
0x1c0171ac0  lea     ecx, [r14-0Bh]; PoolType
0x1c0171ac4  call    cs:__imp_ExAllocatePoolWithTag
0x1c0171acb  nop     dword ptr [rax+rax+00h]
0x1c0171ad0  mov     [rsp+0C8h+DestinationString.Buffer], rax
0x1c0171ad5  mov     [rsp+0C8h+DestinationString.MaximumLength], r14w
0x1c0171adb  lea     rdx, REFS_CHANGE_JOURNAL_FILE_NAME; SourceString
0x1c0171ae2  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x1c0171ae7  call    cs:__imp_RtlCopyUnicodeString
0x1c0171aee  nop     dword ptr [rax+rax+00h]
0x1c0171af3  xor     r8d, r8d
0x1c0171af6  mov     rdx, [rdi+50h]
0x1c0171afa  mov     rcx, rbx
0x1c0171afd  call    RefsAcquireExclusiveScbWithFlags
0x1c0171b02  lea     eax, [r14-1Bh]
0x1c0171b06  mov     r12b, al
0x1c0171b09  mov     [rsp+0C8h+var_77], al
0x1c0171b0d  test    r15b, r15b
0x1c0171b10  setnz   al
0x1c0171b13  lea     rcx, [rsp+0C8h+var_70]
0x1c0171b18  mov     [rsp+0C8h+var_80], rcx
0x1c0171b1d  mov     byte ptr [rsp+0C8h+var_A0], al
0x1c0171b21  mov     rax, [rdi+50h]
0x1c0171b25  mov     [rsp+0C8h+var_A8], rax
0x1c0171b2a  lea     r9, [rsp+0C8h+DestinationString]
0x1c0171b2f  mov     rdx, rdi
0x1c0171b32  mov     rcx, rbx
0x1c0171b35  call    ConditionallyCreateOrOpenFileSystemFile
0x1c0171b3a  mov     rax, [rsp+0C8h+var_70]
0x1c0171b3f  test    rax, rax
0x1c0171b42  jnz     loc_1C0171BF2
0x1c0171b48  xor     r14d, r14d
0x1c0171b4b  mov     [rsp+0C8h+var_68], r14
0x1c0171b50  test    rax, rax
0x1c0171b53  mov     edx, 1
0x1c0171b58  cmovnz  esi, edx
0x1c0171b5b  mov     [rsp+0C8h+var_78], sil
0x1c0171b60  test    r14, r14
0x1c0171b63  jz      loc_1C0171C46
0x1c0171b69  movups  xmm0, xmmword ptr [r14+8]
0x1c0171b6e  movdqu  xmmword ptr [rdi+380h], xmm0
0x1c0171b76  cmp     [rsp+0C8h+arg_20], 0
0x1c0171b7e  jz      short loc_1C0171BFB
0x1c0171b80  test    r15b, r15b
0x1c0171b83  jnz     short loc_1C0171B8A
0x1c0171b85  bts     dword ptr [rdi+4], 15h
0x1c0171b8a  mov     r9d, r15d
0x1c0171b8d  mov     rax, [rsp+0C8h+arg_28]
0x1c0171b95  mov     [rsp+0C8h+var_A0], rax
0x1c0171b9a  and     dword ptr [rsp+0C8h+var_A8], 0
0x1c0171b9f  mov     r8, r14
0x1c0171ba2  mov     rdx, rdi
0x1c0171ba5  mov     rcx, rbx
0x1c0171ba8  call    RefsSetupUsnJournal
0x1c0171bad  jmp     short loc_1C0171C29
0x1c0171baf  mov     rcx, [rbx+18h]
0x1c0171bb3  call    MsSetDrainStarveExclusive
0x1c0171bb8  jmp     loc_1C0171AA4
0x1c0171bbd  mov     r14, [r14+78h]
0x1c0171bc1  mov     [rsp+0C8h+var_68], r14
0x1c0171bc6  mov     r8b, dl
0x1c0171bc9  mov     rdx, r14
0x1c0171bcc  mov     rcx, rbx
0x1c0171bcf  call    RefsAcquireExclusivePagingIoSpecifyWait
0x1c0171bd4  xor     r8d, r8d
0x1c0171bd7  mov     rdx, [rdi+28h]
0x1c0171bdb  mov     rcx, rbx
0x1c0171bde  call    RefsAcquireExclusiveScbWithFlags
0x1c0171be3  mov     rax, [rsp+0C8h+var_70]
0x1c0171be8  mov     edx, 1
0x1c0171bed  jmp     loc_1C0171B60
0x1c0171bf2  mov     r14, [rax+78h]
0x1c0171bf6  jmp     loc_1C0171B4B
0x1c0171bfb  test    sil, sil
0x1c0171bfe  jz      short loc_1C0171C36
0x1c0171c00  mov     [rsp+0C8h+var_75], 0
0x1c0171c05  lea     rcx, [rsp+0C8h+var_75]
0x1c0171c0a  mov     [rsp+0C8h+var_98], rcx
0x1c0171c0f  mov     byte ptr [rsp+0C8h+var_A0], dl
0x1c0171c13  mov     byte ptr [rsp+0C8h+var_A8], 0
0x1c0171c18  mov     r9b, dl
0x1c0171c1b  xor     r8d, r8d
0x1c0171c1e  mov     rdx, rax
0x1c0171c21  mov     rcx, rbx
0x1c0171c24  call    RefsDecrementCloseCounts
0x1c0171c29  xor     sil, sil
0x1c0171c2c  mov     [rsp+0C8h+var_78], sil
0x1c0171c31  mov     rax, [rsp+0C8h+var_70]
0x1c0171c36  mov     rcx, [rsp+0C8h+arg_30]
0x1c0171c3e  test    rcx, rcx
0x1c0171c41  jz      short loc_1C0171C46
0x1c0171c43  mov     [rcx], rax
0x1c0171c46  test    r12b, r12b
0x1c0171c49  jz      short loc_1C0171C5B
0x1c0171c4b  mov     rdx, [rdi+50h]
0x1c0171c4f  mov     rdx, [rdx+78h]
0x1c0171c53  mov     rcx, rbx
0x1c0171c56  call    RefsReleaseFcb
0x1c0171c5b  and     dword ptr [rbx+4], 0FFFFCFFFh
0x1c0171c62  lea     r8, [rdi+548h]; BackTrace
0x1c0171c69  xor     r9d, r9d; BackTraceHash
0x1c0171c6c  lea     edx, [r9+9]; FramesToCapture
0x1c0171c70  xor     ecx, ecx; FramesToSkip
0x1c0171c72  call    cs:__imp_RtlCaptureStackBackTrace
0x1c0171c79  nop     dword ptr [rax+rax+00h]
0x1c0171c7e  mov     rcx, r13; Resource
0x1c0171c81  call    cs:__imp_ExReleaseResourceLite
0x1c0171c88  nop     dword ptr [rax+rax+00h]
0x1c0171c8d  mov     rcx, [rsp+0C8h+DestinationString.Buffer]; P
0x1c0171c92  test    rcx, rcx
0x1c0171c95  jz      short loc_1C0171CA5
0x1c0171c97  xor     edx, edx; Tag
0x1c0171c99  call    cs:__imp_ExFreePoolWithTag
0x1c0171ca0  nop     dword ptr [rax+rax+00h]
0x1c0171ca5  test    sil, sil
0x1c0171ca8  jnz     loc_1C018861C
0x1c0171cae  add     rsp, 90h
0x1c0171cb5  pop     r15
0x1c0171cb7  pop     r14
0x1c0171cb9  pop     r13
0x1c0171cbb  pop     r12
0x1c0171cbd  pop     rdi
0x1c0171cbe  pop     rsi
0x1c0171cbf  pop     rbx
0x1c0171cc0  retn
0x1c0180685  push    rbx
0x1c0180687  push    rbp
0x1c0180688  push    rdi
0x1c0180689  sub     rsp, 50h
0x1c018068d  mov     rbp, rdx
0x1c0180690  mov     dil, cl
0x1c0180693  cmp     byte ptr [rbp+51h], 0
0x1c0180697  jz      short loc_1C01806B5
0x1c0180699  mov     rax, [rbp+0D8h]
0x1c01806a0  mov     rdx, [rax+50h]
0x1c01806a4  mov     rdx, [rdx+78h]
0x1c01806a8  mov     rcx, [rbp+0D0h]
0x1c01806af  call    RefsReleaseFcb
0x1c01806b4  nop
0x1c01806b5  cmp     byte ptr [rbp+52h], 0
0x1c01806b9  jz      short loc_1C0180700
0x1c01806bb  mov     rax, [rbp+0D0h]
0x1c01806c2  and     dword ptr [rax+4], 0FFFFCFFFh
0x1c01806c9  mov     rbx, [rbp+0D8h]
0x1c01806d0  lea     r8, [rbx+548h]; BackTrace
0x1c01806d7  xor     r9d, r9d; BackTraceHash
0x1c01806da  lea     edx, [r9+9]; FramesToCapture
0x1c01806de  xor     ecx, ecx; FramesToSkip
0x1c01806e0  call    cs:__imp_RtlCaptureStackBackTrace
0x1c01806e7  nop     dword ptr [rax+rax+00h]
0x1c01806ec  lea     rcx, [rbx+498h]; Resource
0x1c01806f3  call    cs:__imp_ExReleaseResourceLite
0x1c01806fa  nop     dword ptr [rax+rax+00h]
0x1c01806ff  nop
0x1c0180700  mov     rcx, [rbp+70h]; P
0x1c0180704  test    rcx, rcx
0x1c0180707  jz      short loc_1C0180718
0x1c0180709  xor     edx, edx; Tag
0x1c018070b  call    cs:__imp_ExFreePoolWithTag
0x1c0180712  nop     dword ptr [rax+rax+00h]
0x1c0180717  nop
0x1c0180718  test    dil, dil
0x1c018071b  jz      short loc_1C0180730
0x1c018071d  movups  xmm0, xmmword ptr [rbp+78h]
0x1c0180721  mov     rax, [rbp+0D8h]
0x1c0180728  movdqu  xmmword ptr [rax+380h], xmm0
0x1c0180730  cmp     byte ptr [rbp+50h], 0
0x1c0180734  jz      short loc_1C0180773
0x1c0180736  mov     byte ptr [rbp+0E8h], 0
0x1c018073d  mov     rax, [rbp+60h]
0x1c0180741  btr     dword ptr [rax+4], 8
0x1c0180746  lea     rax, [rbp+0E8h]
0x1c018074d  mov     [rsp+68h+var_38], rax
0x1c0180752  mov     [rsp+68h+var_40], 0
0x1c0180757  mov     [rsp+68h+var_48], 0
0x1c018075c  mov     r9b, 1
0x1c018075f  xor     r8d, r8d
0x1c0180762  mov     rdx, [rbp+58h]
0x1c0180766  mov     rcx, [rbp+0D0h]
0x1c018076d  call    RefsDecrementCloseCounts
0x1c0180772  nop
0x1c0180773  add     rsp, 50h
0x1c0180777  pop     rdi
0x1c0180778  pop     rbp
0x1c0180779  pop     rbx
0x1c018077a  retn
0x1c018861c  mov     [rsp+0C8h+arg_18], 0
0x1c0188624  btr     dword ptr [r14+4], 8
0x1c018862a  lea     rax, [rsp+0C8h+arg_18]
0x1c0188632  mov     [rsp+0C8h+var_98], rax
0x1c0188637  mov     byte ptr [rsp+0C8h+var_A0], 0
0x1c018863c  mov     byte ptr [rsp+0C8h+var_A8], 0
0x1c0188641  mov     r9d, 1
0x1c0188647  xor     r8d, r8d
0x1c018864a  mov     rdx, [rsp+0C8h+var_70]
0x1c018864f  mov     rcx, rbx
0x1c0188652  call    RefsDecrementCloseCounts
0x1c0188657  nop
0x1c0188658  jmp     loc_1C0171CAE
```
