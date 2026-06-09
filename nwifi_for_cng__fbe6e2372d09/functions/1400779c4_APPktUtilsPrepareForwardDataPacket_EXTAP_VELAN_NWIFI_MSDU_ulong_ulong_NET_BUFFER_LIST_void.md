# APPktUtilsPrepareForwardDataPacket(_EXTAP_VELAN *,NWIFI_MSDU *,ulong,ulong,_NET_BUFFER_LIST * *,void * *)

- ea: `0x1400779c4`
- end: `0x140077da9`
- name: `?APPktUtilsPrepareForwardDataPacket@@YAHPEAU_EXTAP_VELAN@@PEAUNWIFI_MSDU@@KKPEAPEAU_NET_BUFFER_LIST@@PEAPEAX@Z`
- size: `997`
- prototype: `__int64 __fastcall(struct _EXTAP_VELAN *, struct NWIFI_MSDU *, unsigned int, unsigned int, struct _NET_BUFFER_LIST **, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140077db0`

## callees

- `0x14000d21c`
- `0x140013acc`
- `0x140016f88`
- `0x140020dc0`
- `0x1400779c4`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140077b24`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140077c4e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140077b24`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140077c4e`
- `ntoskrnl!MmSizeOfMdl` at `0x140077b53`
- `ntoskrnl!MmSizeOfMdl` at `0x140077b53`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140077bbe`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140077bbe`
- `ntoskrnl!ExAllocatePool2` at `0x140077bd6`
- `ntoskrnl!ExAllocatePool2` at `0x140077bd6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140077cf4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140077cf4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077d05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077d05`
- `ntoskrnl!IoFreeMdl` at `0x140077d19`
- `ntoskrnl!IoFreeMdl` at `0x140077d19`
- `ntoskrnl!IoAllocateMdl` at `0x140077ad9`
- `ntoskrnl!IoAllocateMdl` at `0x140077ad9`
- `NDIS!NdisAllocateNetBuffer` at `0x140077ca3`
- `NDIS!NdisAllocateNetBuffer` at `0x140077ca3`

## pseudocode

```c
__int64 __fastcall APPktUtilsPrepareForwardDataPacket(
        struct _EXTAP_VELAN *a1,
        struct NWIFI_MSDU *a2,
        unsigned int a3,
        int a4,
        struct _NET_BUFFER_LIST **a5,
        void **a6)
{
  _VELAN *pVElan; // rcx
  __int64 v8; // rdi
  __int64 uBackFillSize; // r12
  unsigned int v10; // r14d
  unsigned int v11; // ebx
  _NET_BUFFER_LIST *pNdisPacket; // rsi
  struct _NET_BUFFER_LIST *v13; // rbp
  __int64 v14; // rcx
  _MDL *v15; // rbx
  struct _MDL *Mdl; // rax
  struct _MDL *v17; // rdi
  unsigned int v18; // r15d
  unsigned int v19; // ecx
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  struct _MDL *v22; // rsi
  char *MappedSystemVa; // r15
  PNET_BUFFER NetBuffer; // r9
  _NET_BUFFER_LIST_CONTEXT *Context; // rdx
  __int64 Offset; // rcx
  _QWORD *v27; // r8
  struct _NET_BUFFER_LIST **v28; // rax
  _NET_BUFFER_LIST *v30; // [rsp+38h] [rbp-50h]
  struct _NET_BUFFER_LIST *v32; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v33; // [rsp+A0h] [rbp+18h]
  int v34; // [rsp+A8h] [rbp+20h]

  v34 = a4;
  v33 = a3;
  pVElan = a1->pVElan;
  v8 = a3;
  v32 = 0;
  uBackFillSize = pVElan->uBackFillSize;
  v10 = uBackFillSize + a4;
  if ( (int)uBackFillSize + a4 < (unsigned int)uBackFillSize )
  {
    v11 = -1073676267;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_7d0e4632fdee3958307e1f8f9ef20022_Traceguids);
    return v11;
  }
  pNdisPacket = a2->MSDUCore.pNdisPacket;
  v30 = pNdisPacket;
  v11 = Dot11AllocateSendPacket(pVElan, &v32);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_7d0e4632fdee3958307e1f8f9ef20022_Traceguids, v11);
    v13 = v32;
    goto LABEL_37;
  }
  v13 = v32;
  *(_DOT11_QOS_SEND_INFO *)&v32->Context->ContextData[v32->Context->Offset + 20] = a2->MSDUCore.QoSSendInfo;
  v14 = v8;
  v15 = *(_MDL **)(pNdisPacket->Link.Region + 8);
  if ( v15->ByteCount <= (unsigned int)v8 )
  {
    do
    {
      v14 = (unsigned int)(v14 - v15->ByteCount);
      v15 = v15->Next;
    }
    while ( v15->ByteCount <= (unsigned int)v14 );
  }
  Mdl = IoAllocateMdl((char *)v15->MappedSystemVa + v14, v15->ByteCount - (int)v14, 0, 0, 0);
  v17 = Mdl;
  if ( !Mdl )
  {
    v11 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_7d0e4632fdee3958307e1f8f9ef20022_Traceguids);
    goto LABEL_37;
  }
  MmBuildMdlForNonPagedPool(Mdl);
  v17->Next = v15->Next;
  if ( v10 > 0x1F3B )
    goto LABEL_35;
  v18 = (MmSizeOfMdl((PVOID)0xFFF, v10) + 7) & 0xFFFFFFF8;
  v19 = v18 + v10 + 16;
  if ( v19 < 0x10 )
    goto LABEL_35;
  if ( v19 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_23:
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_25;
  }
  if ( v19 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_23;
  }
  if ( v19 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_23;
  }
  if ( v19 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_23;
  }
  p_DeviceQueue = 0;
  Pool2 = (char *)ExAllocatePool2(64, v19, 808870262);
LABEL_25:
  if ( !Pool2 )
  {
LABEL_35:
    v11 = -1073741670;
    IoFreeMdl(v17);
    goto LABEL_37;
  }
  *((_DWORD *)Pool2 + 2) = 808870262;
  v22 = (struct _MDL *)(Pool2 + 16);
  *(_QWORD *)Pool2 = p_DeviceQueue;
  if ( Pool2 != (char *)-16LL )
  {
    v22->Next = 0;
    *((_DWORD *)Pool2 + 14) = v10;
    *((_QWORD *)Pool2 + 6) = ((unsigned __int64)v22 + v18) & 0xFFFFFFFFFFFFF000uLL;
    *((_WORD *)Pool2 + 13) = 0;
    *((_WORD *)Pool2 + 12) = 8 * ((((((_DWORD)Pool2 + 16 + v18) & 0xFFFLL) + (unsigned __int64)v10 + 4095) >> 12) + 6);
    *((_DWORD *)Pool2 + 15) = ((_DWORD)Pool2 + 16 + v18) & 0xFFF;
    MmBuildMdlForNonPagedPool(v22);
  }
  MappedSystemVa = (char *)v22->MappedSystemVa;
  v11 = 0;
  v22->Next = v17;
  memset(MappedSystemVa, 0, v10);
  NetBuffer = NdisAllocateNetBuffer(
                a1->pVElan->hSendNetBufferPool,
                v22,
                uBackFillSize,
                v34 + a2->uOffset + a2->uPktLength - v33);
  if ( !NetBuffer )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_7d0e4632fdee3958307e1f8f9ef20022_Traceguids);
    if ( v22 )
    {
      if ( v22[-1].StartVa )
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v22[-1].StartVa, &v22[-1].StartVa);
      else
        ExFreePoolWithTag(&v22[-1].StartVa, v22[-1].ByteCount);
    }
    goto LABEL_35;
  }
  Context = v13->Context;
  Offset = Context->Offset;
  v27 = *(_QWORD **)&Context->ContextData[Offset + 40];
  *(_QWORD *)&Context->ContextData[Offset + 40] = v27 + 3;
  *v27 = APPktUtilsPrepareForwardDataPacketComplete;
  v27[2] = v30;
  v28 = a5;
  v27[1] = a1;
  NetBuffer->Link.Alignment = 0;
  v13->Link.Region = (unsigned __int64)NetBuffer;
  *v28 = v13;
  v13 = 0;
  v32 = 0;
  *a6 = &MappedSystemVa[uBackFillSize];
LABEL_37:
  if ( v13 )
    Dot11FreeSendPacket(&v32);
  return v11;
}

```

## disassembly

```asm
0x1400779c4  mov     rax, rsp
0x1400779c7  mov     [rax+20h], r9d
0x1400779cb  mov     [rax+18h], r8d
0x1400779cf  mov     [rax+8], rcx
0x1400779d3  push    rbx
0x1400779d4  push    rbp
0x1400779d5  push    rsi
0x1400779d6  push    rdi
0x1400779d7  push    r12
0x1400779d9  push    r13
0x1400779db  push    r14
0x1400779dd  push    r15
0x1400779df  sub     rsp, 48h
0x1400779e3  mov     rcx, [rcx]; struct _VELAN *
0x1400779e6  mov     r13, rdx
0x1400779e9  mov     edi, r8d
0x1400779ec  mov     qword ptr [rax+10h], 0
0x1400779f4  mov     r12d, [rcx+84h]
0x1400779fb  lea     r14d, [r12+r9]
0x1400779ff  cmp     r14d, r12d
0x140077a02  jnb     short loc_140077A3A
0x140077a04  mov     ebx, 0C0010015h
0x140077a09  mov     rcx, cs:WPP_GLOBAL_Control
0x140077a10  lea     rax, WPP_GLOBAL_Control
0x140077a17  cmp     rcx, rax
0x140077a1a  jz      loc_140077D95
0x140077a20  mov     rcx, [rcx+18h]
0x140077a24  lea     r8, WPP_7d0e4632fdee3958307e1f8f9ef20022_Traceguids
0x140077a2b  mov     edx, 11h
0x140077a30  call    WPP_SF_
0x140077a35  jmp     loc_140077D95
0x140077a3a  mov     rsi, [rdx+20h]
0x140077a3e  lea     rdx, [rsp+88h+arg_8]; struct _NET_BUFFER_LIST **
0x140077a46  mov     [rsp+88h+var_50], rsi
0x140077a4b  call    ?Dot11AllocateSendPacket@@YAHPEAU_VELAN@@PEAPEAU_NET_BUFFER_LIST@@@Z; Dot11AllocateSendPacket(_VELAN *,_NET_BUFFER_LIST * *)
0x140077a50  mov     ebx, eax
0x140077a52  test    eax, eax
0x140077a54  jz      short loc_140077A8E
0x140077a56  mov     rcx, cs:WPP_GLOBAL_Control
0x140077a5d  lea     rax, WPP_GLOBAL_Control
0x140077a64  cmp     rcx, rax
0x140077a67  jz      short loc_140077A81
0x140077a69  mov     rcx, [rcx+18h]
0x140077a6d  lea     r8, WPP_7d0e4632fdee3958307e1f8f9ef20022_Traceguids
0x140077a74  mov     edx, 12h
0x140077a79  mov     r9d, ebx
0x140077a7c  call    WPP_SF_d
0x140077a81  mov     rbp, [rsp+88h+arg_8]
0x140077a89  jmp     loc_140077D83
0x140077a8e  mov     eax, [r13+8]
0x140077a92  mov     rbp, [rsp+88h+arg_8]
0x140077a9a  mov     rdx, [rbp+10h]
0x140077a9e  movzx   ecx, word ptr [rdx+0Ah]
0x140077aa2  mov     [rcx+rdx+24h], eax
0x140077aa6  mov     rcx, rdi
0x140077aa9  mov     rax, [rsi+8]
0x140077aad  mov     rbx, [rax+8]
0x140077ab1  cmp     [rbx+28h], edi
0x140077ab4  ja      short loc_140077AC1
0x140077ab6  sub     ecx, [rbx+28h]
0x140077ab9  mov     rbx, [rbx]
0x140077abc  cmp     [rbx+28h], ecx
0x140077abf  jbe     short loc_140077AB6
0x140077ac1  mov     edx, [rbx+28h]
0x140077ac4  xor     r9d, r9d; ChargeQuota
0x140077ac7  sub     edx, ecx; Length
0x140077ac9  mov     [rsp+88h+Irp], 0; Irp
0x140077ad2  add     rcx, [rbx+18h]; VirtualAddress
0x140077ad6  xor     r8d, r8d; SecondaryBuffer
0x140077ad9  call    cs:__imp_IoAllocateMdl
0x140077ae0  nop     dword ptr [rax+rax+00h]
0x140077ae5  mov     rdi, rax
0x140077ae8  test    rax, rax
0x140077aeb  jnz     short loc_140077B21
0x140077aed  mov     ebx, 0C000009Ah
0x140077af2  mov     rcx, cs:WPP_GLOBAL_Control
0x140077af9  lea     rax, WPP_GLOBAL_Control
0x140077b00  cmp     rcx, rax
0x140077b03  jz      loc_140077D83
0x140077b09  mov     rcx, [rcx+18h]
0x140077b0d  lea     edx, [rdi+13h]
0x140077b10  lea     r8, WPP_7d0e4632fdee3958307e1f8f9ef20022_Traceguids
0x140077b17  call    WPP_SF_
0x140077b1c  jmp     loc_140077D83
0x140077b21  mov     rcx, rdi; MemoryDescriptorList
0x140077b24  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140077b2b  nop     dword ptr [rax+rax+00h]
0x140077b30  mov     rax, [rbx]
0x140077b33  mov     [rdi], rax
0x140077b36  cmp     r14d, 1F3Bh
0x140077b3d  ja      loc_140077D11
0x140077b43  mov     eax, r14d
0x140077b46  mov     ecx, 0FFFh; Base
0x140077b4b  mov     edx, r14d; Length
0x140077b4e  mov     [rsp+88h+Size], rax
0x140077b53  call    cs:__imp_MmSizeOfMdl
0x140077b5a  nop     dword ptr [rax+rax+00h]
0x140077b5f  lea     ecx, [r14+10h]
0x140077b63  lea     r15d, [rax+7]
0x140077b67  and     r15d, 0FFFFFFF8h
0x140077b6b  add     ecx, r15d
0x140077b6e  cmp     ecx, 10h
0x140077b71  jb      loc_140077D11
0x140077b77  mov     esi, 30366176h
0x140077b7c  cmp     ecx, 40h ; '@'
0x140077b7f  ja      short loc_140077B8A
0x140077b81  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140077b88  jmp     short loc_140077BBB
0x140077b8a  cmp     ecx, 100h
0x140077b90  ja      short loc_140077B9B
0x140077b92  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140077b99  jmp     short loc_140077BBB
0x140077b9b  cmp     ecx, 400h
0x140077ba1  ja      short loc_140077BAC
0x140077ba3  lea     rbx, Lookaside
0x140077baa  jmp     short loc_140077BBB
0x140077bac  cmp     ecx, 800h
0x140077bb2  ja      short loc_140077BCC
0x140077bb4  lea     rbx, stru_1400B31C0
0x140077bbb  mov     rcx, rbx; Lookaside
0x140077bbe  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140077bc5  nop     dword ptr [rax+rax+00h]
0x140077bca  jmp     short loc_140077BE2
0x140077bcc  xor     ebx, ebx
0x140077bce  mov     edx, ecx
0x140077bd0  mov     r8d, esi
0x140077bd3  lea     ecx, [rbx+40h]
0x140077bd6  call    cs:__imp_ExAllocatePool2
0x140077bdd  nop     dword ptr [rax+rax+00h]
0x140077be2  test    rax, rax
0x140077be5  jz      loc_140077D11
0x140077beb  mov     [rax+8], esi
0x140077bee  lea     rsi, [rax+10h]
0x140077bf2  mov     [rax], rbx
0x140077bf5  test    rsi, rsi
0x140077bf8  jz      short loc_140077C5A
0x140077bfa  mov     r9d, 0FFFh
0x140077c00  mov     edx, r15d
0x140077c03  add     rdx, rsi
0x140077c06  mov     ecx, r14d
0x140077c09  add     rcx, r9
0x140077c0c  mov     qword ptr [rsi], 0
0x140077c13  mov     r8d, edx
0x140077c16  mov     [rsi+28h], r14d
0x140077c1a  mov     eax, r8d
0x140077c1d  and     rdx, 0FFFFFFFFFFFFF000h
0x140077c24  and     rax, r9
0x140077c27  mov     [rsi+20h], rdx
0x140077c2b  add     rcx, rax
0x140077c2e  and     r8d, r9d
0x140077c31  shr     rcx, 0Ch
0x140077c35  xor     eax, eax
0x140077c37  add     cx, 6
0x140077c3b  mov     [rsi+0Ah], ax
0x140077c3f  shl     cx, 3
0x140077c43  mov     [rsi+8], cx
0x140077c47  mov     rcx, rsi; MemoryDescriptorList
0x140077c4a  mov     [rsi+2Ch], r8d
0x140077c4e  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140077c55  nop     dword ptr [rax+rax+00h]
0x140077c5a  mov     r15, [rsi+18h]
0x140077c5e  xor     edx, edx; Val
0x140077c60  mov     r8, [rsp+88h+Size]; Size
0x140077c65  mov     rcx, r15; void *
0x140077c68  xor     ebx, ebx
0x140077c6a  mov     [rsi], rdi
0x140077c6d  mov     r14, rsi
0x140077c70  call    memset
0x140077c75  mov     r9d, [r13+3Ch]
0x140077c79  mov     r8d, r12d; DataOffset
0x140077c7c  add     r9d, [r13+38h]
0x140077c80  mov     rdx, rsi; MdlChain
0x140077c83  sub     r9d, [rsp+88h+arg_10]
0x140077c8b  mov     r13, [rsp+88h+arg_0]
0x140077c93  add     r9d, [rsp+88h+arg_18]; DataLength
0x140077c9b  mov     rcx, [r13+0]
0x140077c9f  mov     rcx, [rcx+38h]; PoolHandle
0x140077ca3  call    cs:__imp_NdisAllocateNetBuffer
0x140077caa  nop     dword ptr [rax+rax+00h]
0x140077caf  mov     r9, rax
0x140077cb2  test    rax, rax
0x140077cb5  jnz     short loc_140077D27
0x140077cb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140077cbe  lea     rax, WPP_GLOBAL_Control
0x140077cc5  cmp     rcx, rax
0x140077cc8  jz      short loc_140077CDD
0x140077cca  mov     rcx, [rcx+18h]
0x140077cce  lea     edx, [rbx+14h]
0x140077cd1  lea     r8, WPP_7d0e4632fdee3958307e1f8f9ef20022_Traceguids
0x140077cd8  call    WPP_SF_
0x140077cdd  test    r14, r14
0x140077ce0  jz      short loc_140077D11
0x140077ce2  lea     rcx, [r14-10h]; P
0x140077ce6  mov     rax, [rcx]
0x140077ce9  test    rax, rax
0x140077cec  jz      short loc_140077D02
0x140077cee  mov     rdx, rcx; Entry
0x140077cf1  mov     rcx, rax; Lookaside
0x140077cf4  call    cs:__imp_ExFreeToNPagedLookasideList
0x140077cfb  nop     dword ptr [rax+rax+00h]
0x140077d00  jmp     short loc_140077D11
0x140077d02  mov     edx, [rcx+8]; Tag
0x140077d05  call    cs:__imp_ExFreePoolWithTag
0x140077d0c  nop     dword ptr [rax+rax+00h]
0x140077d11  mov     rcx, rdi; Mdl
0x140077d14  mov     ebx, 0C000009Ah
0x140077d19  call    cs:__imp_IoFreeMdl
0x140077d20  nop     dword ptr [rax+rax+00h]
0x140077d25  jmp     short loc_140077D83
0x140077d27  mov     rdx, [rbp+10h]
0x140077d2b  movzx   ecx, word ptr [rdx+0Ah]
0x140077d2f  mov     r8, [rcx+rdx+38h]
0x140077d34  lea     rax, [r8+18h]
0x140077d38  mov     [rcx+rdx+38h], rax
0x140077d3d  lea     rax, ?APPktUtilsPrepareForwardDataPacketComplete@@YAXPEAU_NET_BUFFER_LIST@@HPEAU_EXTAP_VELAN@@0@Z; APPktUtilsPrepareForwardDataPacketComplete(_NET_BUFFER_LIST *,int,_EXTAP_VELAN *,_NET_BUFFER_LIST *)
0x140077d44  mov     [r8], rax
0x140077d47  lea     rcx, [r15+r12]
0x140077d4b  mov     rax, [rsp+88h+var_50]
0x140077d50  mov     [r8+10h], rax
0x140077d54  mov     rax, [rsp+88h+arg_20]
0x140077d5c  mov     [r8+8], r13
0x140077d60  mov     qword ptr [r9], 0
0x140077d67  mov     [rbp+8], r9
0x140077d6b  mov     [rax], rbp
0x140077d6e  xor     ebp, ebp
0x140077d70  mov     rax, [rsp+88h+arg_28]
0x140077d78  mov     [rsp+88h+arg_8], rbp
0x140077d80  mov     [rax], rcx
0x140077d83  test    rbp, rbp
0x140077d86  jz      short loc_140077D95
0x140077d88  lea     rcx, [rsp+88h+arg_8]; struct _NET_BUFFER_LIST **
0x140077d90  call    ?Dot11FreeSendPacket@@YAXPEAPEAU_NET_BUFFER_LIST@@@Z; Dot11FreeSendPacket(_NET_BUFFER_LIST * *)
0x140077d95  mov     eax, ebx
0x140077d97  add     rsp, 48h
0x140077d9b  pop     r15
0x140077d9d  pop     r14
0x140077d9f  pop     r13
0x140077da1  pop     r12
0x140077da3  pop     rdi
0x140077da4  pop     rsi
0x140077da5  pop     rbp
0x140077da6  pop     rbx
0x140077da7  retn
```
