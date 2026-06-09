# IppEnsureContiguousHeaders

- ea: `0x14006a2d0`
- end: `0x14006a6e1`
- name: `IppEnsureContiguousHeaders`
- size: `1041`
- prototype: `__int64 __fastcall(int, int, int, int, int, ULONG DataOffsetDelta, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400693f0`

## callees

- `0x140034190`
- `0x140054138`
- `0x14005b3ac`
- `0x1400632f0`
- `0x14006a2d0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a541`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a570`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a5ba`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a5e6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a681`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a541`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a570`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a5ba`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a5e6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a681`
- `NETIO!NetioAllocateMdl` at `0x14006a3e2`
- `NETIO!NetioDereferenceNetBufferList` at `0x14006a482`
- `NETIO!NetioDereferenceNetBufferList` at `0x14006a482`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14006a648`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14006a648`
- `NETIO!NetioAllocateAndReferenceCloneNetBufferList` at `0x14006a435`
- `NETIO!NetioAllocateAndReferenceCloneNetBufferList` at `0x14006a435`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14006a515`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14006a515`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006a3ec`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006a3ec`

## pseudocode

```c
__int64 __fastcall IppEnsureContiguousHeaders(
        __int64 *a1,
        __int64 a2,
        PNET_BUFFER *a3,
        unsigned int a4,
        unsigned int a5,
        ULONG DataOffsetDelta,
        char **a7,
        char **a8)
{
  unsigned int v8; // ebp
  int v9; // r12d
  __int64 v10; // r13
  ULONG v14; // ebx
  struct _NET_BUFFER *v15; // rcx
  ULONG v16; // edx
  ULONG CurrentMdlOffset; // eax
  NDIS_STATUS v18; // r15d
  PNET_BUFFER v19; // r10
  PMDL CurrentMdl; // r11
  __int64 v21; // rdx
  char *MappedSystemVa; // rax
  ULONG v23; // ecx
  PNET_BUFFER v24; // rbx
  PMDL v25; // rcx
  char *v26; // rax
  char *v27; // rcx
  char **v28; // rax
  __int64 v30; // r8
  __int64 v31; // rax
  __int64 v32; // r8
  __int64 v33; // r10
  struct _NET_BUFFER *v34; // rax
  struct _NET_BUFFER *Alignment; // r14
  PNET_BUFFER v36; // rbx
  PMDL v37; // rcx
  char *v38; // rax
  char *v39; // rcx
  __int64 v40; // rbx
  __int64 v41; // rcx
  char *v42; // rax
  unsigned int v43; // ebx
  PNET_BUFFER v44; // rbp
  PMDL v45; // rcx
  char *v46; // rax
  __int64 DataOffset; // rdx
  char *v48; // r8
  PMDL MdlChain; // rcx
  ULONG *p_CurrentMdlOffset; // [rsp+78h] [rbp+10h] BYREF
  __int64 v51; // [rsp+80h] [rbp+18h]

  v8 = a5;
  v9 = 0;
  v10 = *(_QWORD *)(a2 + 8);
  if ( a5 && a1 == &Ipv6Global )
    v9 = *(unsigned __int16 *)(a2 + 48) + *(unsigned __int16 *)(a2 + 50) + *(unsigned __int16 *)(a2 + 52);
  v14 = DataOffsetDelta;
  v15 = *a3;
  v16 = a4 + DataOffsetDelta;
  CurrentMdlOffset = (*a3)->CurrentMdlOffset;
  if ( CurrentMdlOffset < a4 + DataOffsetDelta )
  {
    v18 = NdisRetreatNetBufferDataStart(v15, v16, 0, NetioAllocateMdl);
    if ( v18 < 0 )
      goto LABEL_17;
  }
  else
  {
    v15->DataOffset -= v16;
    v15->DataLength += v16;
    v15->CurrentMdlOffset = CurrentMdlOffset - v16;
    v18 = 0;
  }
  v19 = *a3;
  DataOffsetDelta = v8 + v9 + a4;
  CurrentMdl = v19->CurrentMdl;
  v21 = DataOffsetDelta + v14;
  a5 = v21;
  p_CurrentMdlOffset = &v19->CurrentMdlOffset;
  if ( CurrentMdl->ByteCount - v19->CurrentMdlOffset >= (unsigned int)v21 )
  {
    if ( (CurrentMdl->MdlFlags & 5) != 0 )
    {
      MappedSystemVa = (char *)CurrentMdl->MappedSystemVa;
    }
    else
    {
      MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(CurrentMdl, 0, MmCached, 0, 0, 0x40000000u);
      v21 = a5;
    }
    v19 = *a3;
    if ( &MappedSystemVa[*p_CurrentMdlOffset] )
    {
      if ( v14 )
      {
        v23 = v14 + v19->CurrentMdlOffset;
        if ( v23 >= *(_DWORD *)(v19->Link.Region + 40) )
        {
          NdisAdvanceNetBufferDataStart(*a3, v14, 0, 0);
        }
        else
        {
          v19->DataOffset += v14;
          v19->DataLength -= v14;
          v19->CurrentMdlOffset = v23;
        }
      }
      v24 = *a3;
      v25 = (*a3)->CurrentMdl;
      if ( (v25->MdlFlags & 5) != 0 )
        v26 = (char *)v25->MappedSystemVa;
      else
        v26 = (char *)MmMapLockedPagesSpecifyCache(v25, 0, MmCached, 0, 0, 0x40000000u);
      v27 = &v26[v24->CurrentMdlOffset];
      v28 = a7;
LABEL_14:
      *v28 = v27;
      return (unsigned int)v18;
    }
  }
  NetioAdvanceNetBuffer(v19, v21);
  v31 = NetioAllocateAndReferenceCloneNetBufferList(v10, 0);
  v51 = v31;
  if ( v31 )
  {
    IppCopyNetBufferListInfo(v31, v10);
    *(_QWORD *)(a2 + 8) = v33;
    v34 = *(struct _NET_BUFFER **)(v33 + 8);
    Alignment = *(struct _NET_BUFFER **)(v10 + 8);
    while ( Alignment )
    {
      if ( *a3 == Alignment )
      {
        *a3 = v34;
        break;
      }
      Alignment = (struct _NET_BUFFER *)Alignment->Link.Alignment;
      v34 = (struct _NET_BUFFER *)v34->Link.Alignment;
    }
    NetioDereferenceNetBufferList(v10, 0);
    v18 = NetioRetreatNetBuffer(*a3, DataOffsetDelta, v14);
    if ( v18 >= 0 )
    {
      if ( v8 )
      {
        NetioAdvanceNetBuffer(*a3, a4);
        v43 = v9 + v8;
        NetioRetreatNetBuffer(Alignment, v9 + v8, 0);
        v44 = *a3;
        v45 = (*a3)->CurrentMdl;
        if ( (v45->MdlFlags & 5) != 0 )
          v46 = (char *)v45->MappedSystemVa;
        else
          v46 = (char *)MmMapLockedPagesSpecifyCache(v45, 0, MmCached, 0, 0, 0x40000000u);
        DataOffset = Alignment->DataOffset;
        v48 = &v46[v44->CurrentMdlOffset];
        MdlChain = Alignment->MdlChain;
        p_CurrentMdlOffset = 0;
        RtlCopyMdlToKernelBuffer(MdlChain, DataOffset, v48, v43, &p_CurrentMdlOffset);
        NetioRetreatNetBuffer(*a3, a4, 0);
      }
      v36 = *a3;
      v37 = (*a3)->CurrentMdl;
      if ( (v37->MdlFlags & 5) != 0 )
        v38 = (char *)v37->MappedSystemVa;
      else
        v38 = (char *)MmMapLockedPagesSpecifyCache(v37, 0, MmCached, 0, 0, 0x40000000u);
      v39 = &v38[v36->CurrentMdlOffset];
      v40 = *(_QWORD *)(v51 + 8);
      *a7 = v39;
      v41 = *(_QWORD *)(v40 + 8);
      if ( (*(_BYTE *)(v41 + 10) & 5) != 0 )
        v42 = *(char **)(v41 + 24);
      else
        v42 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v41, 0, MmCached, 0, 0, 0x40000000u);
      v27 = &v42[*(unsigned int *)(v40 + 16)];
      v28 = a8;
      goto LABEL_14;
    }
LABEL_17:
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v30,
        L"retreat contiguous header (IPNG)");
    return (unsigned int)v18;
  }
  if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
    McTemplateK0z_EtwWriteTransfer(
      &MICROSOFT_TCPIP_PROVIDER_Context,
      TCPIP_MEMORY_FAILURES,
      v32,
      L"clone for contiguous header (IPNG)");
  return 3221225626LL;
}

```

## disassembly

```asm
0x14006a2d0  push    rbx
0x14006a2d2  push    rbp
0x14006a2d3  push    rsi
0x14006a2d4  push    rdi
0x14006a2d5  push    r12
0x14006a2d7  push    r13
0x14006a2d9  push    r14
0x14006a2db  sub     rsp, 30h
0x14006a2df  mov     ebp, [rsp+68h+arg_20]
0x14006a2e6  xor     r12d, r12d
0x14006a2e9  mov     r13, [rdx+8]
0x14006a2ed  mov     esi, r9d
0x14006a2f0  mov     rdi, r8
0x14006a2f3  mov     r14, rdx
0x14006a2f6  test    ebp, ebp
0x14006a2f8  jnz     loc_14006A68F
0x14006a2fe  mov     ebx, [rsp+68h+DataOffsetDelta]
0x14006a305  mov     rcx, [r8]; NetBuffer
0x14006a308  mov     [rsp+68h+arg_0], r15
0x14006a30d  lea     edx, [r9+rbx]; DataOffsetDelta
0x14006a311  mov     eax, [rcx+10h]
0x14006a314  cmp     eax, edx
0x14006a316  jb      loc_14006A3E2
0x14006a31c  sub     [rcx+28h], edx
0x14006a31f  sub     eax, edx
0x14006a321  add     [rcx+18h], edx
0x14006a324  mov     [rcx+10h], eax
0x14006a327  xor     r15d, r15d
0x14006a32a  mov     r10, [rdi]
0x14006a32d  lea     eax, [r12+rsi]
0x14006a331  add     eax, ebp
0x14006a333  mov     [rsp+68h+DataOffsetDelta], eax
0x14006a33a  mov     r11, [r10+8]
0x14006a33e  lea     edx, [rax+rbx]
0x14006a341  lea     rax, [r10+10h]
0x14006a345  mov     [rsp+68h+arg_20], edx
0x14006a34c  mov     [rsp+68h+arg_8], rax
0x14006a351  mov     ecx, [r11+28h]
0x14006a355  sub     ecx, [rax]
0x14006a357  cmp     ecx, edx
0x14006a359  jb      loc_14006A428
0x14006a35f  test    byte ptr [r11+0Ah], 5
0x14006a364  jz      loc_14006A552
0x14006a36a  mov     rax, [r11+18h]
0x14006a36e  mov     rcx, [rsp+68h+arg_8]
0x14006a373  mov     r10, [rdi]
0x14006a376  mov     ecx, [rcx]
0x14006a378  add     rcx, rax
0x14006a37b  jz      loc_14006A428
0x14006a381  test    ebx, ebx
0x14006a383  jz      short loc_14006A3A4
0x14006a385  mov     rax, [r10+8]
0x14006a389  mov     ecx, [r10+10h]
0x14006a38d  add     ecx, ebx
0x14006a38f  cmp     ecx, [rax+28h]
0x14006a392  jnb     loc_14006A50A
0x14006a398  add     [r10+28h], ebx
0x14006a39c  sub     [r10+18h], ebx
0x14006a3a0  mov     [r10+10h], ecx
0x14006a3a4  mov     rbx, [rdi]
0x14006a3a7  mov     rcx, [rbx+8]; MemoryDescriptorList
0x14006a3ab  test    byte ptr [rcx+0Ah], 5
0x14006a3af  jz      loc_14006A526
0x14006a3b5  mov     rax, [rcx+18h]
0x14006a3b9  mov     ecx, [rbx+10h]
0x14006a3bc  add     rcx, rax
0x14006a3bf  mov     rax, [rsp+68h+arg_30]
0x14006a3c7  mov     [rax], rcx
0x14006a3ca  mov     eax, r15d
0x14006a3cd  mov     r15, [rsp+68h+arg_0]
0x14006a3d2  add     rsp, 30h
0x14006a3d6  pop     r14
0x14006a3d8  pop     r13
0x14006a3da  pop     r12
0x14006a3dc  pop     rdi
0x14006a3dd  pop     rsi
0x14006a3de  pop     rbp
0x14006a3df  pop     rbx
0x14006a3e0  retn
0x14006a3e2  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x14006a3e9  xor     r8d, r8d; DataBackFill
0x14006a3ec  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14006a3f3  nop     dword ptr [rax+rax+00h]
0x14006a3f8  mov     r15d, eax
0x14006a3fb  test    eax, eax
0x14006a3fd  jns     loc_14006A32A
0x14006a403  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, 0
0x14006a40a  jge     short loc_14006A3CA
0x14006a40c  lea     r9, aRetreatContigu; "retreat contiguous header (IPNG)"
0x14006a413  lea     rdx, TCPIP_MEMORY_FAILURES
0x14006a41a  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14006a421  call    McTemplateK0z_EtwWriteTransfer
0x14006a426  jmp     short loc_14006A3CA
0x14006a428  mov     rcx, r10
0x14006a42b  call    NetioAdvanceNetBuffer
0x14006a430  xor     edx, edx
0x14006a432  mov     rcx, r13
0x14006a435  call    cs:__imp_NetioAllocateAndReferenceCloneNetBufferList
0x14006a43c  nop     dword ptr [rax+rax+00h]
0x14006a441  mov     [rsp+68h+arg_10], rax
0x14006a449  mov     r10, rax
0x14006a44c  test    rax, rax
0x14006a44f  jz      loc_14006A588
0x14006a455  mov     rdx, r13
0x14006a458  mov     rcx, rax
0x14006a45b  call    IppCopyNetBufferListInfo
0x14006a460  mov     [r14+8], r10
0x14006a464  mov     rax, [r10+8]
0x14006a468  mov     r14, [r13+8]
0x14006a46c  test    r14, r14
0x14006a46f  jz      short loc_14006A47D
0x14006a471  cmp     [rdi], r14
0x14006a474  jnz     loc_14006A6D6
0x14006a47a  mov     [rdi], rax
0x14006a47d  xor     edx, edx
0x14006a47f  mov     rcx, r13
0x14006a482  call    cs:__imp_NetioDereferenceNetBufferList
0x14006a489  nop     dword ptr [rax+rax+00h]
0x14006a48e  mov     edx, [rsp+68h+DataOffsetDelta]
0x14006a495  mov     r8d, ebx
0x14006a498  mov     rcx, [rdi]
0x14006a49b  call    NetioRetreatNetBuffer
0x14006a4a0  mov     r15d, eax
0x14006a4a3  test    eax, eax
0x14006a4a5  js      loc_14006A403
0x14006a4ab  test    ebp, ebp
0x14006a4ad  jnz     loc_14006A5F7
0x14006a4b3  mov     rbx, [rdi]
0x14006a4b6  mov     rcx, [rbx+8]; MemoryDescriptorList
0x14006a4ba  test    byte ptr [rcx+0Ah], 5
0x14006a4be  jz      loc_14006A59F
0x14006a4c4  mov     rax, [rcx+18h]
0x14006a4c8  mov     ecx, [rbx+10h]
0x14006a4cb  mov     rbx, [rsp+68h+arg_10]
0x14006a4d3  add     rcx, rax
0x14006a4d6  mov     rax, [rsp+68h+arg_30]
0x14006a4de  mov     rbx, [rbx+8]
0x14006a4e2  mov     [rax], rcx
0x14006a4e5  mov     rcx, [rbx+8]; MemoryDescriptorList
0x14006a4e9  test    byte ptr [rcx+0Ah], 5
0x14006a4ed  jz      loc_14006A5CB
0x14006a4f3  mov     rax, [rcx+18h]
0x14006a4f7  mov     ecx, [rbx+10h]
0x14006a4fa  add     rcx, rax
0x14006a4fd  mov     rax, [rsp+68h+arg_38]
0x14006a505  jmp     loc_14006A3C7
0x14006a50a  xor     r9d, r9d; FreeMdlHandler
0x14006a50d  xor     r8d, r8d; FreeMdl
0x14006a510  mov     edx, ebx; DataOffsetDelta
0x14006a512  mov     rcx, r10; NetBuffer
0x14006a515  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14006a51c  nop     dword ptr [rax+rax+00h]
0x14006a521  jmp     loc_14006A3A4
0x14006a526  mov     [rsp+68h+Priority], 40000000h; Priority
0x14006a52e  xor     r9d, r9d; RequestedAddress
0x14006a531  xor     edx, edx; AccessMode
0x14006a533  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14006a53b  mov     r8d, 1; CacheType
0x14006a541  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006a548  nop     dword ptr [rax+rax+00h]
0x14006a54d  jmp     loc_14006A3B9
0x14006a552  mov     [rsp+68h+Priority], 40000000h; Priority
0x14006a55a  xor     r9d, r9d; RequestedAddress
0x14006a55d  xor     edx, edx; AccessMode
0x14006a55f  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14006a567  mov     r8d, 1; CacheType
0x14006a56d  mov     rcx, r11; MemoryDescriptorList
0x14006a570  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006a577  nop     dword ptr [rax+rax+00h]
0x14006a57c  mov     edx, [rsp+68h+arg_20]
0x14006a583  jmp     loc_14006A36E
0x14006a588  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, 0
0x14006a58f  jl      loc_14006A6B7
0x14006a595  mov     eax, 0C000009Ah
0x14006a59a  jmp     loc_14006A3CD
0x14006a59f  mov     [rsp+68h+Priority], 40000000h; Priority
0x14006a5a7  xor     r9d, r9d; RequestedAddress
0x14006a5aa  xor     edx, edx; AccessMode
0x14006a5ac  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14006a5b4  mov     r8d, 1; CacheType
0x14006a5ba  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006a5c1  nop     dword ptr [rax+rax+00h]
0x14006a5c6  jmp     loc_14006A4C8
0x14006a5cb  mov     [rsp+68h+Priority], 40000000h; Priority
0x14006a5d3  xor     r9d, r9d; RequestedAddress
0x14006a5d6  xor     edx, edx; AccessMode
0x14006a5d8  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14006a5e0  mov     r8d, 1; CacheType
0x14006a5e6  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006a5ed  nop     dword ptr [rax+rax+00h]
0x14006a5f2  jmp     loc_14006A4F7
0x14006a5f7  mov     rcx, [rdi]
0x14006a5fa  mov     edx, esi
0x14006a5fc  call    NetioAdvanceNetBuffer
0x14006a601  lea     ebx, [r12+rbp]
0x14006a605  xor     r8d, r8d
0x14006a608  mov     edx, ebx
0x14006a60a  mov     rcx, r14
0x14006a60d  call    NetioRetreatNetBuffer
0x14006a612  mov     rbp, [rdi]
0x14006a615  mov     rcx, [rbp+8]; MemoryDescriptorList
0x14006a619  test    byte ptr [rcx+0Ah], 5
0x14006a61d  jz      short loc_14006A666
0x14006a61f  mov     rax, [rcx+18h]
0x14006a623  mov     r8d, [rbp+10h]
0x14006a627  mov     edx, [r14+28h]
0x14006a62b  add     r8, rax
0x14006a62e  mov     rcx, [r14+20h]
0x14006a632  lea     rax, [rsp+68h+arg_8]
0x14006a637  mov     r9d, ebx
0x14006a63a  mov     qword ptr [rsp+68h+BugCheckOnFailure], rax
0x14006a63f  mov     [rsp+68h+arg_8], 0
0x14006a648  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x14006a64f  nop     dword ptr [rax+rax+00h]
0x14006a654  mov     rcx, [rdi]
0x14006a657  xor     r8d, r8d
0x14006a65a  mov     edx, esi
0x14006a65c  call    NetioRetreatNetBuffer
0x14006a661  jmp     loc_14006A4B3
0x14006a666  mov     [rsp+68h+Priority], 40000000h; Priority
0x14006a66e  xor     r9d, r9d; RequestedAddress
0x14006a671  xor     edx, edx; AccessMode
0x14006a673  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14006a67b  mov     r8d, 1; CacheType
0x14006a681  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006a688  nop     dword ptr [rax+rax+00h]
0x14006a68d  jmp     short loc_14006A623
0x14006a68f  lea     rax, Ipv6Global
0x14006a696  cmp     rcx, rax
0x14006a699  jnz     loc_14006A2FE
0x14006a69f  movzx   eax, word ptr [rdx+32h]
0x14006a6a3  movzx   r12d, word ptr [rdx+34h]
0x14006a6a8  add     r12d, eax
0x14006a6ab  movzx   eax, word ptr [rdx+30h]
0x14006a6af  add     r12d, eax
0x14006a6b2  jmp     loc_14006A2FE
0x14006a6b7  lea     r9, aCloneForContig; "clone for contiguous header (IPNG)"
0x14006a6be  lea     rdx, TCPIP_MEMORY_FAILURES
0x14006a6c5  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14006a6cc  call    McTemplateK0z_EtwWriteTransfer
0x14006a6d1  jmp     loc_14006A595
0x14006a6d6  mov     r14, [r14]
0x14006a6d9  mov     rax, [rax]
0x14006a6dc  jmp     loc_14006A46C
```
