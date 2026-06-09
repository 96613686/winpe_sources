# NdisMAllocateNetBufferSGList

- ea: `0x1400466d0`
- end: `0x140046c27`
- name: `NdisMAllocateNetBufferSGList`
- size: `1367`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE NdisMiniportDmaHandle, PNET_BUFFER NetBuffer, PVOID Context, ULONG Flags, PVOID ScatterGatherListBuffer, ULONG ScatterGatherListBufferSize)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x14001cf60`
- `0x1400466d0`
- `0x140046d70`
- `0x140046e10`
- `0x140088cc0`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140046acb`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140046acb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f0121`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f0121`
- `ntoskrnl!ExAllocatePool2` at `0x140046a7b`
- `ntoskrnl!ExAllocatePool2` at `0x140046a7b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140046928`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140046928`
- `ntoskrnl!IoAllocateMdl` at `0x140046aae`
- `ntoskrnl!IoAllocateMdl` at `0x140046aae`
- `ntoskrnl!IoFreeMdl` at `0x1400f0101`
- `ntoskrnl!IoFreeMdl` at `0x1400f0101`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140046a00`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140046a00`

## pseudocode

```c
NDIS_STATUS __stdcall NdisMAllocateNetBufferSGList(
        NDIS_HANDLE NdisMiniportDmaHandle,
        PNET_BUFFER NetBuffer,
        PVOID Context,
        ULONG Flags,
        PVOID ScatterGatherListBuffer,
        ULONG ScatterGatherListBufferSize)
{
  __int64 v6; // rbp
  unsigned int Number; // ebx
  int v11; // eax
  __int64 v12; // r14
  int v13; // r8d
  _MDL *MdlChain; // rsi
  unsigned int DataOffset; // ecx
  ULONG i; // eax
  unsigned int DataLength; // eax
  char v18; // r13
  struct _MDL *v19; // r10
  unsigned __int16 *p_Reserved; // r12
  int v21; // r10d
  __int64 v22; // r8
  unsigned __int64 v23; // rax
  __int64 v25; // r8
  unsigned __int64 v26; // rdx
  struct _LOOKASIDE_LIST_EX *v27; // rcx
  PVOID v28; // rax
  _WORD *v29; // rax
  __int64 v30; // r8
  unsigned __int64 v31; // rdx
  unsigned __int64 v32; // rcx
  PMDL Pool2; // rax
  PMDL v34; // rcx
  PMDL v35; // r8
  PVOID v36; // rdx
  enum Ndis::ReadBindingsOptions::Flags *v37; // rdx
  int v38; // [rsp+38h] [rbp-80h]
  int v39; // [rsp+38h] [rbp-80h]
  struct _LOOKASIDE_LIST_EX *Entry; // [rsp+60h] [rbp-58h]
  PVOID Entrya; // [rsp+60h] [rbp-58h]
  PMDL Entryb; // [rsp+60h] [rbp-58h]
  PMDL Mdl; // [rsp+68h] [rbp-50h]
  PMDL Mdla; // [rsp+68h] [rbp-50h]
  int v45; // [rsp+70h] [rbp-48h]
  unsigned __int64 v46; // [rsp+C0h] [rbp+8h] BYREF
  PVOID v47; // [rsp+D0h] [rbp+18h]
  ULONG Length; // [rsp+D8h] [rbp+20h]

  v47 = Context;
  v6 = *((_QWORD *)NdisMiniportDmaHandle + 1);
  Number = -1;
  v11 = *(_DWORD *)(v6 + 48);
  if ( v11 || (v12 = 0, LOWORD(v13) = 0, *(_DWORD *)(v6 + 80)) )
  {
    v12 = *(_QWORD *)(v6 + 40);
    v13 = *(_DWORD *)(v6 + 80);
    if ( !v12 )
      v12 = *(_QWORD *)(v6 + 40);
    if ( (v11 & 0x400) != 0 )
    {
      Number = KeGetPcr()->Prcb.Number;
      ++*(_QWORD *)(ndisPcwOffsetToPerCpuData + v12 + ndisPcwPerCpuDataStride * Number + 80);
    }
  }
  v45 = v13 & 0x400;
  if ( (v13 & 0x400) != 0 )
  {
    if ( Number == -1 )
      Number = KeGetPcr()->Prcb.Number;
    *(_QWORD *)(ndisPcwOffsetToPerCpuData + v12 + ndisPcwPerCpuDataStride * Number + 384) = __rdtsc();
  }
  if ( *((_QWORD *)NdisMiniportDmaHandle + 2) )
    ndisBugCheckEx(0x28u, 3u, 0, 0);
  MdlChain = NetBuffer->MdlChain;
  if ( !MdlChain )
    return -1073741823;
  DataOffset = NetBuffer->DataOffset;
  for ( i = MdlChain->ByteCount; DataOffset >= i; i = MdlChain->ByteCount )
  {
    MdlChain = MdlChain->Next;
    DataOffset -= i;
  }
  DataLength = NetBuffer->DataLength;
  NetBuffer->Link.Region = (unsigned __int64)MdlChain;
  NetBuffer->CurrentMdlOffset = DataOffset;
  Length = DataLength + DataOffset;
  if ( DataLength + DataOffset < DataLength )
    return -1073676268;
  v18 = Flags & 1;
  v19 = (struct _MDL *)((char *)MdlChain->StartVa + MdlChain->ByteOffset);
  p_Reserved = &NetBuffer->Reserved;
  Mdl = v19;
  if ( (Flags & 1) != 0 )
    *p_Reserved |= 4u;
  if ( !ScatterGatherListBuffer )
  {
    v46 = (unsigned __int64)&NetBuffer->Reserved;
LABEL_27:
    v25 = *((_QWORD *)NdisMiniportDmaHandle + 10);
    v26 = (unsigned __int64)(KeGetPcr()->Prcb.Number + 1) << 7;
    v27 = (struct _LOOKASIDE_LIST_EX *)(v26 + v25 + 64);
    Entry = v27;
    if ( LOBYTE(v27[1].L.Depth) )
    {
      v46 = (unsigned __int64)&NetBuffer->Reserved;
    }
    else
    {
      PplpLazyInitializeLookasideList(v25, v26 + v25 + 64);
      v27 = Entry;
    }
    v28 = ExAllocateFromLookasideListEx(v27);
    Entrya = v28;
    if ( v28 )
    {
      *p_Reserved |= 1u;
      NetBuffer->NdisReserved[0] = v28;
      LOBYTE(v38) = v18;
      v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _MDL *, PMDL, ULONG, _QWORD, PVOID, int, PVOID, _DWORD))(*(_QWORD *)(*((_QWORD *)NdisMiniportDmaHandle + 5) + 8LL) + 112LL))(
              *((_QWORD *)NdisMiniportDmaHandle + 5),
              *(_QWORD *)(v6 + 3824),
              MdlChain,
              Mdl,
              Length,
              *((_QWORD *)NdisMiniportDmaHandle + 6),
              v47,
              v38,
              v28,
              *((_DWORD *)NdisMiniportDmaHandle + 18));
      if ( v21 >= 0 )
        goto LABEL_15;
      v29 = (_WORD *)v46;
      NetBuffer->NdisReserved[0] = 0;
      *p_Reserved = *v29 & 0xFFFE;
      v30 = *((_QWORD *)NdisMiniportDmaHandle + 10);
      v31 = (unsigned __int64)(KeGetPcr()->Prcb.Number + 1) << 7;
      v32 = v31 + v30 + 64;
      v46 = v32;
      if ( !*(_BYTE *)(v32 + 112) )
      {
        PplpLazyInitializeLookasideList(v30, v31 + v30 + 64);
        v32 = v46;
      }
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)v32, Entrya);
    }
    LOBYTE(v38) = v18;
    v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _MDL *, PMDL, ULONG, _QWORD, PVOID, int))(*(_QWORD *)(*((_QWORD *)NdisMiniportDmaHandle + 5) + 8LL)
                                                                                             + 88LL))(
            *((_QWORD *)NdisMiniportDmaHandle + 5),
            *(_QWORD *)(v6 + 3824),
            MdlChain,
            Mdl,
            Length,
            *((_QWORD *)NdisMiniportDmaHandle + 6),
            v47,
            v38);
    if ( v21 >= 0 )
      goto LABEL_15;
    v46 = 0;
    Pool2 = (PMDL)ExAllocatePool2(66, Length, 1735607374);
    Entryb = Pool2;
    v34 = Pool2;
    if ( !Pool2 )
    {
      v21 = -1073741670;
      Mdla = 0;
      LODWORD(v46) = -1073741670;
      goto LABEL_50;
    }
    Pool2 = IoAllocateMdl(Pool2, Length, 0, 0, 0);
    Mdla = Pool2;
    if ( !Pool2 )
    {
      v34 = Entryb;
      v21 = -1073741670;
      LODWORD(v46) = -1073741670;
      goto LABEL_50;
    }
    MmBuildMdlForNonPagedPool(Pool2);
    v35 = Mdla;
    Mdla->Next = 0;
    if ( v18 )
    {
      LODWORD(v46) = RtlCopyMdlToBuffer(MdlChain, 0, Entryb, Length, &v46);
      v21 = v46;
      if ( (v46 & 0x80000000) != 0LL )
      {
LABEL_39:
        Pool2 = Mdla;
        v34 = Entryb;
LABEL_50:
        v37 = &WPP_RECORDER_INITIALIZED;
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v37) = 4;
          WPP_RECORDER_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            (int)v37,
            3,
            49,
            (struct _GUID *)&WPP_2779bc3468263007f5ef77c40b63ca16_Traceguids,
            v21);
          v21 = v46;
          Pool2 = Mdla;
          v34 = Entryb;
        }
        if ( Pool2 )
        {
          IoFreeMdl(Pool2);
          v21 = v46;
          v34 = Entryb;
        }
        if ( v34 )
        {
          ExFreePoolWithTag(v34, 0);
          v21 = v46;
        }
        NetBuffer->NdisReserved[0] = 0;
        NetBuffer->Reserved &= ~2u;
        if ( v21 < 0 )
          NetBuffer->Reserved &= ~4u;
        goto LABEL_15;
      }
      v35 = Mdla;
    }
    *p_Reserved |= 2u;
    v36 = v47;
    NetBuffer->NdisReserved[0] = v35;
    LOBYTE(v39) = v18;
    LODWORD(v46) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, PMDL, PMDL, ULONG, _QWORD, PVOID, int))(*(_QWORD *)(*((_QWORD *)NdisMiniportDmaHandle + 5) + 8LL) + 88LL))(
                     *((_QWORD *)NdisMiniportDmaHandle + 5),
                     *(_QWORD *)(v6 + 3824),
                     v35,
                     Entryb,
                     Length,
                     *((_QWORD *)NdisMiniportDmaHandle + 6),
                     v36,
                     v39);
    v21 = v46;
    if ( (v46 & 0x80000000) == 0LL )
      goto LABEL_15;
    goto LABEL_39;
  }
  v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _MDL *, struct _MDL *, unsigned int, _QWORD, PVOID, _BYTE, PVOID, ULONG))(*(_QWORD *)(*((_QWORD *)NdisMiniportDmaHandle + 5) + 8LL) + 112LL))(
          *((_QWORD *)NdisMiniportDmaHandle + 5),
          *(_QWORD *)(v6 + 3824),
          MdlChain,
          v19,
          DataLength + DataOffset,
          *((_QWORD *)NdisMiniportDmaHandle + 6),
          Context,
          Flags & 1,
          ScatterGatherListBuffer,
          ScatterGatherListBufferSize);
  if ( v21 < 0 )
  {
    v46 = (unsigned __int64)&NetBuffer->Reserved;
    goto LABEL_27;
  }
LABEL_15:
  if ( v45 )
  {
    if ( Number == -1 )
      Number = KeGetPcr()->Prcb.Number;
    v22 = v12 + ndisPcwPerCpuDataStride * Number + ndisPcwOffsetToPerCpuData;
    v23 = __rdtsc();
    *(_QWORD *)(v22 + 184) += (((unsigned __int64)HIDWORD(v23) << 32) | (unsigned int)v23) - *(_QWORD *)(v22 + 384);
    *(_QWORD *)(v22 + 384) = 0;
  }
  return v21;
}

```

## disassembly

```asm
0x1400466d0  mov     [rsp+arg_10], r8
0x1400466d5  push    rbx
0x1400466d6  push    rbp
0x1400466d7  push    rdi
0x1400466d8  push    r13
0x1400466da  push    r14
0x1400466dc  push    r15
0x1400466de  sub     rsp, 88h
0x1400466e5  mov     rbp, [rcx+8]
0x1400466e9  mov     r13d, r9d
0x1400466ec  mov     r11, r8
0x1400466ef  mov     rdi, rdx
0x1400466f2  mov     r15, rcx
0x1400466f5  mov     ebx, 0FFFFFFFFh
0x1400466fa  mov     eax, [rbp+30h]
0x1400466fd  test    eax, eax
0x1400466ff  jnz     loc_1400468AA
0x140046705  xor     r14d, r14d
0x140046708  xor     r8d, r8d
0x14004670b  cmp     [rbp+50h], r8d
0x14004670f  jnz     loc_1400468AA
0x140046715  and     r8d, 400h
0x14004671c  mov     [rsp+0B8h+var_48], r8d
0x140046721  jz      short loc_140046754
0x140046723  cmp     ebx, 0FFFFFFFFh
0x140046726  jnz     short loc_140046730
0x140046728  mov     ebx, gs:1A4h
0x140046730  rdtsc
0x140046732  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x140046739  mov     ecx, ebx
0x14004673b  imul    ecx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x140046742  shl     rdx, 20h
0x140046746  or      rax, rdx
0x140046749  add     rcx, r14
0x14004674c  mov     [r8+rcx+180h], rax
0x140046754  cmp     qword ptr [r15+10h], 0
0x140046759  jnz     loc_140046BE8
0x14004675f  mov     [rsp+0B8h+arg_8], rsi
0x140046767  mov     rsi, [rdi+20h]
0x14004676b  test    rsi, rsi
0x14004676e  jz      loc_1400468A3
0x140046774  mov     ecx, [rdi+28h]
0x140046777  mov     eax, [rsi+28h]
0x14004677a  cmp     ecx, eax
0x14004677c  jnb     loc_140046BFE
0x140046782  mov     eax, [rdi+18h]
0x140046785  mov     [rdi+8], rsi
0x140046789  mov     [rdi+10h], ecx
0x14004678c  lea     r8d, [rax+rcx]
0x140046790  mov     [rsp+0B8h+Length], r8d
0x140046798  cmp     r8d, eax
0x14004679b  jb      loc_14004689C
0x1400467a1  mov     r10d, [rsi+2Ch]
0x1400467a5  and     r13d, 1
0x1400467a9  add     r10, [rsi+20h]
0x1400467ad  mov     [rsp+0B8h+var_38], r12
0x1400467b5  lea     r12, [rdi+32h]
0x1400467b9  mov     [rsp+0B8h+Mdl], r10
0x1400467be  test    r13b, r13b
0x1400467c1  jz      short loc_1400467C9
0x1400467c3  or      word ptr [r12], 4
0x1400467c9  mov     r9, [rsp+0B8h+ScatterGatherListBuffer]
0x1400467d1  test    r9, r9
0x1400467d4  jz      loc_140046B42
0x1400467da  mov     rcx, [r15+28h]
0x1400467de  mov     edx, [rsp+0B8h+ScatterGatherListBufferSize]
0x1400467e5  mov     [rsp+0B8h+var_70], edx
0x1400467e9  mov     rdx, [r15+30h]
0x1400467ed  mov     rax, [rcx+8]
0x1400467f1  mov     [rsp+0B8h+var_78], r9
0x1400467f6  mov     r9, r10
0x1400467f9  mov     [rsp+0B8h+var_80], r13b
0x1400467fe  mov     [rsp+0B8h+var_88], r11
0x140046803  mov     rax, [rax+70h]
0x140046807  mov     qword ptr [rsp+0B8h+var_90], rdx
0x14004680c  mov     rdx, [rbp+0EF0h]
0x140046813  mov     dword ptr [rsp+0B8h+Irp], r8d
0x140046818  mov     r8, rsi
0x14004681b  call    _guard_dispatch_icall
0x140046820  mov     r10d, eax
0x140046823  test    eax, eax
0x140046825  js      loc_1400468E9
0x14004682b  cmp     [rsp+0B8h+var_48], 0
0x140046830  mov     r12, [rsp+0B8h+var_38]
0x140046838  jz      short loc_14004687F
0x14004683a  cmp     ebx, 0FFFFFFFFh
0x14004683d  jnz     short loc_140046847
0x14004683f  mov     ebx, gs:1A4h
0x140046847  imul    ebx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x14004684e  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x140046855  mov     eax, ebx
0x140046857  add     rax, r14
0x14004685a  add     r8, rax
0x14004685d  rdtsc
0x14004685f  shl     rdx, 20h
0x140046863  or      rax, rdx
0x140046866  sub     rax, [r8+180h]
0x14004686d  add     [r8+0B8h], rax
0x140046874  mov     qword ptr [r8+180h], 0
0x14004687f  mov     eax, r10d
0x140046882  mov     rsi, [rsp+0B8h+arg_8]
0x14004688a  add     rsp, 88h
0x140046891  pop     r15
0x140046893  pop     r14
0x140046895  pop     r13
0x140046897  pop     rdi
0x140046898  pop     rbp
0x140046899  pop     rbx
0x14004689a  retn
0x14004689c  mov     eax, 0C0010014h
0x1400468a1  jmp     short loc_140046882
0x1400468a3  mov     eax, 0C0000001h
0x1400468a8  jmp     short loc_140046882
0x1400468aa  mov     r14, [rbp+28h]
0x1400468ae  mov     r8d, [rbp+50h]
0x1400468b2  test    r14, r14
0x1400468b5  jnz     short loc_1400468BB
0x1400468b7  mov     r14, [rbp+28h]
0x1400468bb  bt      eax, 0Ah
0x1400468bf  jnb     loc_140046715
0x1400468c5  mov     ebx, gs:1A4h
0x1400468cd  mov     eax, ebx
0x1400468cf  imul    eax, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x1400468d6  mov     edx, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x1400468dc  add     rax, r14
0x1400468df  inc     qword ptr [rdx+rax+50h]
0x1400468e4  jmp     loc_140046715
0x1400468e9  lea     r9, [rdi+32h]
0x1400468ed  mov     [rsp+0B8h+arg_0], r9
0x1400468f5  mov     eax, gs:1A4h
0x1400468fd  mov     r8, [r15+50h]
0x140046901  lea     edx, [rax+1]
0x140046904  shl     rdx, 7
0x140046908  lea     rcx, [r8+40h]
0x14004690c  add     rcx, rdx; Lookaside
0x14004690f  mov     [rsp+0B8h+Entry], rcx
0x140046914  movzx   eax, byte ptr [rcx+70h]
0x140046918  test    al, al
0x14004691a  jz      loc_140046B2D
0x140046920  mov     [rsp+0B8h+arg_0], r12
0x140046928  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004692f  nop     dword ptr [rax+rax+00h]
0x140046934  mov     [rsp+0B8h+Entry], rax
0x140046939  mov     r8, rax
0x14004693c  test    rax, rax
0x14004693f  jz      loc_140046A0C
0x140046945  or      word ptr [r12], 1
0x14004694b  mov     r9, [rsp+0B8h+Mdl]
0x140046950  mov     [rdi+40h], rax
0x140046954  mov     rcx, [r15+28h]
0x140046958  mov     rdx, [rcx+8]
0x14004695c  mov     rax, [rdx+70h]
0x140046960  mov     edx, [r15+48h]
0x140046964  mov     [rsp+0B8h+var_70], edx
0x140046968  mov     rdx, [rsp+0B8h+arg_10]
0x140046970  mov     [rsp+0B8h+var_78], r8
0x140046975  mov     r8, rsi
0x140046978  mov     [rsp+0B8h+var_80], r13b
0x14004697d  mov     [rsp+0B8h+var_88], rdx
0x140046982  mov     rdx, [r15+30h]
0x140046986  mov     qword ptr [rsp+0B8h+var_90], rdx
0x14004698b  mov     edx, [rsp+0B8h+Length]
0x140046992  mov     dword ptr [rsp+0B8h+Irp], edx
0x140046996  mov     rdx, [rbp+0EF0h]
0x14004699d  call    _guard_dispatch_icall
0x1400469a2  mov     r10d, eax
0x1400469a5  test    eax, eax
0x1400469a7  jns     loc_14004682B
0x1400469ad  mov     rax, [rsp+0B8h+arg_0]
0x1400469b5  mov     ecx, 0FFFEh
0x1400469ba  mov     qword ptr [rdi+40h], 0
0x1400469c2  movzx   eax, word ptr [rax]
0x1400469c5  and     ax, cx
0x1400469c8  mov     [r12], ax
0x1400469cd  mov     eax, gs:1A4h
0x1400469d5  mov     r8, [r15+50h]
0x1400469d9  lea     edx, [rax+1]
0x1400469dc  shl     rdx, 7
0x1400469e0  lea     rcx, [r8+40h]
0x1400469e4  add     rcx, rdx; Lookaside
0x1400469e7  mov     [rsp+0B8h+arg_0], rcx
0x1400469ef  movzx   eax, byte ptr [rcx+70h]
0x1400469f3  test    al, al
0x1400469f5  jz      loc_140046B4F
0x1400469fb  mov     rdx, [rsp+0B8h+Entry]; Entry
0x140046a00  call    cs:__imp_ExFreeToLookasideListEx
0x140046a07  nop     dword ptr [rax+rax+00h]
0x140046a0c  mov     rcx, [r15+28h]
0x140046a10  mov     r8, rsi
0x140046a13  mov     rdx, [rsp+0B8h+arg_10]
0x140046a1b  mov     r9, [rsp+0B8h+Mdl]
0x140046a20  mov     [rsp+0B8h+var_80], r13b
0x140046a25  mov     rax, [rcx+8]
0x140046a29  mov     [rsp+0B8h+var_88], rdx
0x140046a2e  mov     rdx, [r15+30h]
0x140046a32  mov     qword ptr [rsp+0B8h+var_90], rdx
0x140046a37  mov     edx, [rsp+0B8h+Length]
0x140046a3e  mov     rax, [rax+58h]
0x140046a42  mov     dword ptr [rsp+0B8h+Irp], edx
0x140046a46  mov     rdx, [rbp+0EF0h]
0x140046a4d  call    _guard_dispatch_icall
0x140046a52  mov     r10d, eax
0x140046a55  test    eax, eax
0x140046a57  jns     loc_14004682B
0x140046a5d  mov     edx, [rsp+0B8h+Length]
0x140046a64  mov     ecx, 42h ; 'B'
0x140046a69  mov     r8d, 6773444Eh
0x140046a6f  mov     [rsp+0B8h+arg_0], 0
0x140046a7b  call    cs:__imp_ExAllocatePool2
0x140046a82  nop     dword ptr [rax+rax+00h]
0x140046a87  mov     [rsp+0B8h+Entry], rax
0x140046a8c  mov     rcx, rax; VirtualAddress
0x140046a8f  test    rax, rax
0x140046a92  jz      loc_140046C0F
0x140046a98  mov     edx, [rsp+0B8h+Length]; Length
0x140046a9f  xor     r9d, r9d; ChargeQuota
0x140046aa2  xor     r8d, r8d; SecondaryBuffer
0x140046aa5  mov     [rsp+0B8h+Irp], 0; Irp
0x140046aae  call    cs:__imp_IoAllocateMdl
0x140046ab5  nop     dword ptr [rax+rax+00h]
0x140046aba  mov     [rsp+0B8h+Mdl], rax
0x140046abf  test    rax, rax
0x140046ac2  jz      loc_140046BD0
0x140046ac8  mov     rcx, rax; MemoryDescriptorList
0x140046acb  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140046ad2  nop     dword ptr [rax+rax+00h]
0x140046ad7  mov     r8, [rsp+0B8h+Mdl]
0x140046adc  mov     qword ptr [r8], 0
0x140046ae3  test    r13b, r13b
0x140046ae6  jz      loc_140046B6C
0x140046aec  mov     r9d, [rsp+0B8h+Length]; unsigned __int64
0x140046af4  lea     rax, [rsp+0B8h+arg_0]
0x140046afc  mov     r8, [rsp+0B8h+Entry]; void *
0x140046b01  xor     edx, edx; unsigned __int64
0x140046b03  mov     rcx, rsi; MemoryDescriptorList
0x140046b06  mov     [rsp+0B8h+Irp], rax; unsigned __int64 *
0x140046b0b  call    ?RtlCopyMdlToBuffer@@YAJPEAU_MDL@@_KPEAX1PEA_K@Z; RtlCopyMdlToBuffer(_MDL *,unsigned __int64,void *,unsigned __int64,unsigned __int64 *)
0x140046b10  mov     dword ptr [rsp+0B8h+arg_0], eax
0x140046b17  mov     r10d, eax
0x140046b1a  test    eax, eax
0x140046b1c  jns     short loc_140046B67
0x140046b1e  mov     rax, [rsp+0B8h+Mdl]
0x140046b23  mov     rcx, [rsp+0B8h+Entry]
0x140046b28  jmp     loc_1400F00A8
0x140046b2d  mov     rdx, rcx
0x140046b30  mov     rcx, r8
0x140046b33  call    PplpLazyInitializeLookasideList
0x140046b38  mov     rcx, [rsp+0B8h+Entry]
0x140046b3d  jmp     loc_140046928
0x140046b42  mov     [rsp+0B8h+arg_0], r12
0x140046b4a  jmp     loc_1400468F5
0x140046b4f  mov     rdx, rcx
0x140046b52  mov     rcx, r8
0x140046b55  call    PplpLazyInitializeLookasideList
0x140046b5a  mov     rcx, [rsp+0B8h+arg_0]
0x140046b62  jmp     loc_1400469FB
0x140046b67  mov     r8, [rsp+0B8h+Mdl]
0x140046b6c  or      word ptr [r12], 2
0x140046b72  mov     rdx, [rsp+0B8h+arg_10]
0x140046b7a  mov     r9, [rsp+0B8h+Entry]
0x140046b7f  mov     [rdi+40h], r8
0x140046b83  mov     rcx, [r15+28h]
0x140046b87  mov     [rsp+0B8h+var_80], r13b
0x140046b8c  mov     [rsp+0B8h+var_88], rdx
0x140046b91  mov     rdx, [r15+30h]
0x140046b95  mov     rax, [rcx+8]
0x140046b99  mov     qword ptr [rsp+0B8h+var_90], rdx
0x140046b9e  mov     edx, [rsp+0B8h+Length]
0x140046ba5  mov     dword ptr [rsp+0B8h+Irp], edx
0x140046ba9  mov     rax, [rax+58h]
0x140046bad  mov     rdx, [rbp+0EF0h]
0x140046bb4  call    _guard_dispatch_icall
0x140046bb9  mov     dword ptr [rsp+0B8h+arg_0], eax
0x140046bc0  mov     r10d, eax
0x140046bc3  test    eax, eax
0x140046bc5  jns     loc_14004682B
0x140046bcb  jmp     loc_140046B1E
0x140046bd0  mov     rcx, [rsp+0B8h+Entry]
0x140046bd5  mov     r10d, 0C000009Ah
0x140046bdb  mov     dword ptr [rsp+0B8h+arg_0], r10d
0x140046be3  jmp     loc_1400F00A8
0x140046be8  xor     r9d, r9d; BugCheckParameter4
0x140046beb  xor     r8d, r8d; BugCheckParameter3
0x140046bee  mov     edx, 3; BugCheckParameter2
0x140046bf3  mov     ecx, 28h ; '('; BugCheckParameter1
0x140046bf8  call    ?ndisBugCheckEx@@YAX_K000@Z; ndisBugCheckEx(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x140046bfe  mov     rsi, [rsi]
0x140046c01  sub     ecx, eax
0x140046c03  mov     eax, [rsi+28h]
0x140046c06  cmp     ecx, eax
0x140046c08  jnb     short loc_140046BFE
0x140046c0a  jmp     loc_140046782
0x140046c0f  mov     r10d, 0C000009Ah
0x140046c15  mov     [rsp+0B8h+Mdl], rax
0x140046c1a  mov     dword ptr [rsp+0B8h+arg_0], r10d
0x140046c22  jmp     loc_1400F00A8
0x1400f00a8  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400f00af  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400f00b6  jz      short loc_1400F00F9
0x1400f00b8  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
