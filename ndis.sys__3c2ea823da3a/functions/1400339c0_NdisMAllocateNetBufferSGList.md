# NdisMAllocateNetBufferSGList

- ea: `0x1400339c0`
- end: `0x140033f17`
- name: `NdisMAllocateNetBufferSGList`
- size: `1367`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE NdisMiniportDmaHandle, PNET_BUFFER NetBuffer, PVOID Context, ULONG Flags, PVOID ScatterGatherListBuffer, ULONG ScatterGatherListBufferSize)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x140028e00`
- `0x1400339c0`
- `0x140034060`
- `0x140034100`
- `0x140083a40`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140033dbb`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140033dbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e9947`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e9947`
- `ntoskrnl!ExAllocatePool2` at `0x140033d6b`
- `ntoskrnl!ExAllocatePool2` at `0x140033d6b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140033c18`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140033c18`
- `ntoskrnl!IoAllocateMdl` at `0x140033d9e`
- `ntoskrnl!IoAllocateMdl` at `0x140033d9e`
- `ntoskrnl!IoFreeMdl` at `0x1400e9927`
- `ntoskrnl!IoFreeMdl` at `0x1400e9927`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140033cf0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140033cf0`

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
0x1400339c0  mov     [rsp+arg_10], r8
0x1400339c5  push    rbx
0x1400339c6  push    rbp
0x1400339c7  push    rdi
0x1400339c8  push    r13
0x1400339ca  push    r14
0x1400339cc  push    r15
0x1400339ce  sub     rsp, 88h
0x1400339d5  mov     rbp, [rcx+8]
0x1400339d9  mov     r13d, r9d
0x1400339dc  mov     r11, r8
0x1400339df  mov     rdi, rdx
0x1400339e2  mov     r15, rcx
0x1400339e5  mov     ebx, 0FFFFFFFFh
0x1400339ea  mov     eax, [rbp+30h]
0x1400339ed  test    eax, eax
0x1400339ef  jnz     loc_140033B9A
0x1400339f5  xor     r14d, r14d
0x1400339f8  xor     r8d, r8d
0x1400339fb  cmp     [rbp+50h], r8d
0x1400339ff  jnz     loc_140033B9A
0x140033a05  and     r8d, 400h
0x140033a0c  mov     [rsp+0B8h+var_48], r8d
0x140033a11  jz      short loc_140033A44
0x140033a13  cmp     ebx, 0FFFFFFFFh
0x140033a16  jnz     short loc_140033A20
0x140033a18  mov     ebx, gs:1A4h
0x140033a20  rdtsc
0x140033a22  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x140033a29  mov     ecx, ebx
0x140033a2b  imul    ecx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x140033a32  shl     rdx, 20h
0x140033a36  or      rax, rdx
0x140033a39  add     rcx, r14
0x140033a3c  mov     [r8+rcx+180h], rax
0x140033a44  cmp     qword ptr [r15+10h], 0
0x140033a49  jnz     loc_140033ED8
0x140033a4f  mov     [rsp+0B8h+arg_8], rsi
0x140033a57  mov     rsi, [rdi+20h]
0x140033a5b  test    rsi, rsi
0x140033a5e  jz      loc_140033B93
0x140033a64  mov     ecx, [rdi+28h]
0x140033a67  mov     eax, [rsi+28h]
0x140033a6a  cmp     ecx, eax
0x140033a6c  jnb     loc_140033EEE
0x140033a72  mov     eax, [rdi+18h]
0x140033a75  mov     [rdi+8], rsi
0x140033a79  mov     [rdi+10h], ecx
0x140033a7c  lea     r8d, [rax+rcx]
0x140033a80  mov     [rsp+0B8h+Length], r8d
0x140033a88  cmp     r8d, eax
0x140033a8b  jb      loc_140033B8C
0x140033a91  mov     r10d, [rsi+2Ch]
0x140033a95  and     r13d, 1
0x140033a99  add     r10, [rsi+20h]
0x140033a9d  mov     [rsp+0B8h+var_38], r12
0x140033aa5  lea     r12, [rdi+32h]
0x140033aa9  mov     [rsp+0B8h+Mdl], r10
0x140033aae  test    r13b, r13b
0x140033ab1  jz      short loc_140033AB9
0x140033ab3  or      word ptr [r12], 4
0x140033ab9  mov     r9, [rsp+0B8h+ScatterGatherListBuffer]
0x140033ac1  test    r9, r9
0x140033ac4  jz      loc_140033E32
0x140033aca  mov     rcx, [r15+28h]
0x140033ace  mov     edx, [rsp+0B8h+ScatterGatherListBufferSize]
0x140033ad5  mov     [rsp+0B8h+var_70], edx
0x140033ad9  mov     rdx, [r15+30h]
0x140033add  mov     rax, [rcx+8]
0x140033ae1  mov     [rsp+0B8h+var_78], r9
0x140033ae6  mov     r9, r10
0x140033ae9  mov     [rsp+0B8h+var_80], r13b
0x140033aee  mov     [rsp+0B8h+var_88], r11
0x140033af3  mov     rax, [rax+70h]
0x140033af7  mov     qword ptr [rsp+0B8h+var_90], rdx
0x140033afc  mov     rdx, [rbp+0EF0h]
0x140033b03  mov     dword ptr [rsp+0B8h+Irp], r8d
0x140033b08  mov     r8, rsi
0x140033b0b  call    _guard_dispatch_icall
0x140033b10  mov     r10d, eax
0x140033b13  test    eax, eax
0x140033b15  js      loc_140033BD9
0x140033b1b  cmp     [rsp+0B8h+var_48], 0
0x140033b20  mov     r12, [rsp+0B8h+var_38]
0x140033b28  jz      short loc_140033B6F
0x140033b2a  cmp     ebx, 0FFFFFFFFh
0x140033b2d  jnz     short loc_140033B37
0x140033b2f  mov     ebx, gs:1A4h
0x140033b37  imul    ebx, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x140033b3e  mov     r8d, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x140033b45  mov     eax, ebx
0x140033b47  add     rax, r14
0x140033b4a  add     r8, rax
0x140033b4d  rdtsc
0x140033b4f  shl     rdx, 20h
0x140033b53  or      rax, rdx
0x140033b56  sub     rax, [r8+180h]
0x140033b5d  add     [r8+0B8h], rax
0x140033b64  mov     qword ptr [r8+180h], 0
0x140033b6f  mov     eax, r10d
0x140033b72  mov     rsi, [rsp+0B8h+arg_8]
0x140033b7a  add     rsp, 88h
0x140033b81  pop     r15
0x140033b83  pop     r14
0x140033b85  pop     r13
0x140033b87  pop     rdi
0x140033b88  pop     rbp
0x140033b89  pop     rbx
0x140033b8a  retn
0x140033b8c  mov     eax, 0C0010014h
0x140033b91  jmp     short loc_140033B72
0x140033b93  mov     eax, 0C0000001h
0x140033b98  jmp     short loc_140033B72
0x140033b9a  mov     r14, [rbp+28h]
0x140033b9e  mov     r8d, [rbp+50h]
0x140033ba2  test    r14, r14
0x140033ba5  jnz     short loc_140033BAB
0x140033ba7  mov     r14, [rbp+28h]
0x140033bab  bt      eax, 0Ah
0x140033baf  jnb     loc_140033A05
0x140033bb5  mov     ebx, gs:1A4h
0x140033bbd  mov     eax, ebx
0x140033bbf  imul    eax, cs:?ndisPcwPerCpuDataStride@@3KA; ulong ndisPcwPerCpuDataStride
0x140033bc6  mov     edx, cs:?ndisPcwOffsetToPerCpuData@@3KA; ulong ndisPcwOffsetToPerCpuData
0x140033bcc  add     rax, r14
0x140033bcf  inc     qword ptr [rdx+rax+50h]
0x140033bd4  jmp     loc_140033A05
0x140033bd9  lea     r9, [rdi+32h]
0x140033bdd  mov     [rsp+0B8h+arg_0], r9
0x140033be5  mov     eax, gs:1A4h
0x140033bed  mov     r8, [r15+50h]
0x140033bf1  lea     edx, [rax+1]
0x140033bf4  shl     rdx, 7
0x140033bf8  lea     rcx, [r8+40h]
0x140033bfc  add     rcx, rdx; Lookaside
0x140033bff  mov     [rsp+0B8h+Entry], rcx
0x140033c04  movzx   eax, byte ptr [rcx+70h]
0x140033c08  test    al, al
0x140033c0a  jz      loc_140033E1D
0x140033c10  mov     [rsp+0B8h+arg_0], r12
0x140033c18  call    cs:__imp_ExAllocateFromLookasideListEx
0x140033c1f  nop     dword ptr [rax+rax+00h]
0x140033c24  mov     [rsp+0B8h+Entry], rax
0x140033c29  mov     r8, rax
0x140033c2c  test    rax, rax
0x140033c2f  jz      loc_140033CFC
0x140033c35  or      word ptr [r12], 1
0x140033c3b  mov     r9, [rsp+0B8h+Mdl]
0x140033c40  mov     [rdi+40h], rax
0x140033c44  mov     rcx, [r15+28h]
0x140033c48  mov     rdx, [rcx+8]
0x140033c4c  mov     rax, [rdx+70h]
0x140033c50  mov     edx, [r15+48h]
0x140033c54  mov     [rsp+0B8h+var_70], edx
0x140033c58  mov     rdx, [rsp+0B8h+arg_10]
0x140033c60  mov     [rsp+0B8h+var_78], r8
0x140033c65  mov     r8, rsi
0x140033c68  mov     [rsp+0B8h+var_80], r13b
0x140033c6d  mov     [rsp+0B8h+var_88], rdx
0x140033c72  mov     rdx, [r15+30h]
0x140033c76  mov     qword ptr [rsp+0B8h+var_90], rdx
0x140033c7b  mov     edx, [rsp+0B8h+Length]
0x140033c82  mov     dword ptr [rsp+0B8h+Irp], edx
0x140033c86  mov     rdx, [rbp+0EF0h]
0x140033c8d  call    _guard_dispatch_icall
0x140033c92  mov     r10d, eax
0x140033c95  test    eax, eax
0x140033c97  jns     loc_140033B1B
0x140033c9d  mov     rax, [rsp+0B8h+arg_0]
0x140033ca5  mov     ecx, 0FFFEh
0x140033caa  mov     qword ptr [rdi+40h], 0
0x140033cb2  movzx   eax, word ptr [rax]
0x140033cb5  and     ax, cx
0x140033cb8  mov     [r12], ax
0x140033cbd  mov     eax, gs:1A4h
0x140033cc5  mov     r8, [r15+50h]
0x140033cc9  lea     edx, [rax+1]
0x140033ccc  shl     rdx, 7
0x140033cd0  lea     rcx, [r8+40h]
0x140033cd4  add     rcx, rdx; Lookaside
0x140033cd7  mov     [rsp+0B8h+arg_0], rcx
0x140033cdf  movzx   eax, byte ptr [rcx+70h]
0x140033ce3  test    al, al
0x140033ce5  jz      loc_140033E3F
0x140033ceb  mov     rdx, [rsp+0B8h+Entry]; Entry
0x140033cf0  call    cs:__imp_ExFreeToLookasideListEx
0x140033cf7  nop     dword ptr [rax+rax+00h]
0x140033cfc  mov     rcx, [r15+28h]
0x140033d00  mov     r8, rsi
0x140033d03  mov     rdx, [rsp+0B8h+arg_10]
0x140033d0b  mov     r9, [rsp+0B8h+Mdl]
0x140033d10  mov     [rsp+0B8h+var_80], r13b
0x140033d15  mov     rax, [rcx+8]
0x140033d19  mov     [rsp+0B8h+var_88], rdx
0x140033d1e  mov     rdx, [r15+30h]
0x140033d22  mov     qword ptr [rsp+0B8h+var_90], rdx
0x140033d27  mov     edx, [rsp+0B8h+Length]
0x140033d2e  mov     rax, [rax+58h]
0x140033d32  mov     dword ptr [rsp+0B8h+Irp], edx
0x140033d36  mov     rdx, [rbp+0EF0h]
0x140033d3d  call    _guard_dispatch_icall
0x140033d42  mov     r10d, eax
0x140033d45  test    eax, eax
0x140033d47  jns     loc_140033B1B
0x140033d4d  mov     edx, [rsp+0B8h+Length]
0x140033d54  mov     ecx, 42h ; 'B'
0x140033d59  mov     r8d, 6773444Eh
0x140033d5f  mov     [rsp+0B8h+arg_0], 0
0x140033d6b  call    cs:__imp_ExAllocatePool2
0x140033d72  nop     dword ptr [rax+rax+00h]
0x140033d77  mov     [rsp+0B8h+Entry], rax
0x140033d7c  mov     rcx, rax; VirtualAddress
0x140033d7f  test    rax, rax
0x140033d82  jz      loc_140033EFF
0x140033d88  mov     edx, [rsp+0B8h+Length]; Length
0x140033d8f  xor     r9d, r9d; ChargeQuota
0x140033d92  xor     r8d, r8d; SecondaryBuffer
0x140033d95  mov     [rsp+0B8h+Irp], 0; Irp
0x140033d9e  call    cs:__imp_IoAllocateMdl
0x140033da5  nop     dword ptr [rax+rax+00h]
0x140033daa  mov     [rsp+0B8h+Mdl], rax
0x140033daf  test    rax, rax
0x140033db2  jz      loc_140033EC0
0x140033db8  mov     rcx, rax; MemoryDescriptorList
0x140033dbb  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140033dc2  nop     dword ptr [rax+rax+00h]
0x140033dc7  mov     r8, [rsp+0B8h+Mdl]
0x140033dcc  mov     qword ptr [r8], 0
0x140033dd3  test    r13b, r13b
0x140033dd6  jz      loc_140033E5C
0x140033ddc  mov     r9d, [rsp+0B8h+Length]; unsigned __int64
0x140033de4  lea     rax, [rsp+0B8h+arg_0]
0x140033dec  mov     r8, [rsp+0B8h+Entry]; void *
0x140033df1  xor     edx, edx; unsigned __int64
0x140033df3  mov     rcx, rsi; MemoryDescriptorList
0x140033df6  mov     [rsp+0B8h+Irp], rax; unsigned __int64 *
0x140033dfb  call    ?RtlCopyMdlToBuffer@@YAJPEAU_MDL@@_KPEAX1PEA_K@Z; RtlCopyMdlToBuffer(_MDL *,unsigned __int64,void *,unsigned __int64,unsigned __int64 *)
0x140033e00  mov     dword ptr [rsp+0B8h+arg_0], eax
0x140033e07  mov     r10d, eax
0x140033e0a  test    eax, eax
0x140033e0c  jns     short loc_140033E57
0x140033e0e  mov     rax, [rsp+0B8h+Mdl]
0x140033e13  mov     rcx, [rsp+0B8h+Entry]
0x140033e18  jmp     loc_1400E98CE
0x140033e1d  mov     rdx, rcx
0x140033e20  mov     rcx, r8
0x140033e23  call    PplpLazyInitializeLookasideList
0x140033e28  mov     rcx, [rsp+0B8h+Entry]
0x140033e2d  jmp     loc_140033C18
0x140033e32  mov     [rsp+0B8h+arg_0], r12
0x140033e3a  jmp     loc_140033BE5
0x140033e3f  mov     rdx, rcx
0x140033e42  mov     rcx, r8
0x140033e45  call    PplpLazyInitializeLookasideList
0x140033e4a  mov     rcx, [rsp+0B8h+arg_0]
0x140033e52  jmp     loc_140033CEB
0x140033e57  mov     r8, [rsp+0B8h+Mdl]
0x140033e5c  or      word ptr [r12], 2
0x140033e62  mov     rdx, [rsp+0B8h+arg_10]
0x140033e6a  mov     r9, [rsp+0B8h+Entry]
0x140033e6f  mov     [rdi+40h], r8
0x140033e73  mov     rcx, [r15+28h]
0x140033e77  mov     [rsp+0B8h+var_80], r13b
0x140033e7c  mov     [rsp+0B8h+var_88], rdx
0x140033e81  mov     rdx, [r15+30h]
0x140033e85  mov     rax, [rcx+8]
0x140033e89  mov     qword ptr [rsp+0B8h+var_90], rdx
0x140033e8e  mov     edx, [rsp+0B8h+Length]
0x140033e95  mov     dword ptr [rsp+0B8h+Irp], edx
0x140033e99  mov     rax, [rax+58h]
0x140033e9d  mov     rdx, [rbp+0EF0h]
0x140033ea4  call    _guard_dispatch_icall
0x140033ea9  mov     dword ptr [rsp+0B8h+arg_0], eax
0x140033eb0  mov     r10d, eax
0x140033eb3  test    eax, eax
0x140033eb5  jns     loc_140033B1B
0x140033ebb  jmp     loc_140033E0E
0x140033ec0  mov     rcx, [rsp+0B8h+Entry]
0x140033ec5  mov     r10d, 0C000009Ah
0x140033ecb  mov     dword ptr [rsp+0B8h+arg_0], r10d
0x140033ed3  jmp     loc_1400E98CE
0x140033ed8  xor     r9d, r9d; BugCheckParameter4
0x140033edb  xor     r8d, r8d; BugCheckParameter3
0x140033ede  mov     edx, 3; BugCheckParameter2
0x140033ee3  mov     ecx, 28h ; '('; BugCheckParameter1
0x140033ee8  call    ?ndisBugCheckEx@@YAX_K000@Z; ndisBugCheckEx(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x140033eee  mov     rsi, [rsi]
0x140033ef1  sub     ecx, eax
0x140033ef3  mov     eax, [rsi+28h]
0x140033ef6  cmp     ecx, eax
0x140033ef8  jnb     short loc_140033EEE
0x140033efa  jmp     loc_140033A72
0x140033eff  mov     r10d, 0C000009Ah
0x140033f05  mov     [rsp+0B8h+Mdl], rax
0x140033f0a  mov     dword ptr [rsp+0B8h+arg_0], r10d
0x140033f12  jmp     loc_1400E98CE
0x1400e98ce  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400e98d5  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400e98dc  jz      short loc_1400E991F
0x1400e98de  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
