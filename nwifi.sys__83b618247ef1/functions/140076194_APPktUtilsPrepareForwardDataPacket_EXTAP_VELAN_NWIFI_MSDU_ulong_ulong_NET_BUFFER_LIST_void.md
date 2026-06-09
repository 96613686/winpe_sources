# APPktUtilsPrepareForwardDataPacket(_EXTAP_VELAN *,NWIFI_MSDU *,ulong,ulong,_NET_BUFFER_LIST * *,void * *)

- ea: `0x140076194`
- end: `0x140076579`
- name: `?APPktUtilsPrepareForwardDataPacket@@YAHPEAU_EXTAP_VELAN@@PEAUNWIFI_MSDU@@KKPEAPEAU_NET_BUFFER_LIST@@PEAPEAX@Z`
- size: `997`
- prototype: `__int64 __fastcall(struct _EXTAP_VELAN *, struct NWIFI_MSDU *, unsigned int, unsigned int, struct _NET_BUFFER_LIST **, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140076580`

## callees

- `0x14000d22c`
- `0x140013adc`
- `0x140016f88`
- `0x140020dc0`
- `0x140076194`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400762f4`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14007641e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400762f4`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14007641e`
- `ntoskrnl!MmSizeOfMdl` at `0x140076323`
- `ntoskrnl!MmSizeOfMdl` at `0x140076323`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007638e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007638e`
- `ntoskrnl!ExAllocatePool2` at `0x1400763a6`
- `ntoskrnl!ExAllocatePool2` at `0x1400763a6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400764c4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400764c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400764d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400764d5`
- `ntoskrnl!IoFreeMdl` at `0x1400764e9`
- `ntoskrnl!IoFreeMdl` at `0x1400764e9`
- `ntoskrnl!IoAllocateMdl` at `0x1400762a9`
- `ntoskrnl!IoAllocateMdl` at `0x1400762a9`
- `NDIS!NdisAllocateNetBuffer` at `0x140076473`
- `NDIS!NdisAllocateNetBuffer` at `0x140076473`

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
  __int64 v18; // r9
  unsigned int v19; // r15d
  unsigned int v20; // ecx
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  struct _MDL *v23; // rsi
  char *MappedSystemVa; // r15
  PNET_BUFFER NetBuffer; // r9
  _NET_BUFFER_LIST_CONTEXT *Context; // rdx
  __int64 Offset; // rcx
  _QWORD *v28; // r8
  struct _NET_BUFFER_LIST **v29; // rax
  _NET_BUFFER_LIST *v31; // [rsp+38h] [rbp-50h]
  struct _NET_BUFFER_LIST *v33; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v34; // [rsp+A0h] [rbp+18h]
  int v35; // [rsp+A8h] [rbp+20h]

  v35 = a4;
  v34 = a3;
  pVElan = a1->pVElan;
  v8 = a3;
  v33 = 0;
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
  v31 = pNdisPacket;
  v11 = Dot11AllocateSendPacket(pVElan, &v33);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_7d0e4632fdee3958307e1f8f9ef20022_Traceguids, v11);
    v13 = v33;
    goto LABEL_37;
  }
  v13 = v33;
  *(_DOT11_QOS_SEND_INFO *)&v33->Context->ContextData[v33->Context->Offset + 20] = a2->MSDUCore.QoSSendInfo;
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
  v19 = (MmSizeOfMdl((PVOID)0xFFF, v10) + 7) & 0xFFFFFFF8;
  v20 = v19 + v10 + 16;
  if ( v20 < 0x10 )
    goto LABEL_35;
  if ( v20 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_23:
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_25;
  }
  if ( v20 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_23;
  }
  if ( v20 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_23;
  }
  if ( v20 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_23;
  }
  p_DeviceQueue = 0;
  Pool2 = (char *)ExAllocatePool2(64, v20, 808870262, v18);
LABEL_25:
  if ( !Pool2 )
  {
LABEL_35:
    v11 = -1073741670;
    IoFreeMdl(v17);
    goto LABEL_37;
  }
  *((_DWORD *)Pool2 + 2) = 808870262;
  v23 = (struct _MDL *)(Pool2 + 16);
  *(_QWORD *)Pool2 = p_DeviceQueue;
  if ( Pool2 != (char *)-16LL )
  {
    v23->Next = 0;
    *((_DWORD *)Pool2 + 14) = v10;
    *((_QWORD *)Pool2 + 6) = ((unsigned __int64)v23 + v19) & 0xFFFFFFFFFFFFF000uLL;
    *((_WORD *)Pool2 + 13) = 0;
    *((_WORD *)Pool2 + 12) = 8 * ((((((_DWORD)Pool2 + 16 + v19) & 0xFFFLL) + (unsigned __int64)v10 + 4095) >> 12) + 6);
    *((_DWORD *)Pool2 + 15) = ((_DWORD)Pool2 + 16 + v19) & 0xFFF;
    MmBuildMdlForNonPagedPool(v23);
  }
  MappedSystemVa = (char *)v23->MappedSystemVa;
  v11 = 0;
  v23->Next = v17;
  memset(MappedSystemVa, 0, v10);
  NetBuffer = NdisAllocateNetBuffer(
                a1->pVElan->hSendNetBufferPool,
                v23,
                uBackFillSize,
                v35 + a2->uOffset + a2->uPktLength - v34);
  if ( !NetBuffer )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_7d0e4632fdee3958307e1f8f9ef20022_Traceguids);
    if ( v23 )
    {
      if ( v23[-1].StartVa )
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v23[-1].StartVa, &v23[-1].StartVa);
      else
        ExFreePoolWithTag(&v23[-1].StartVa, v23[-1].ByteCount);
    }
    goto LABEL_35;
  }
  Context = v13->Context;
  Offset = Context->Offset;
  v28 = *(_QWORD **)&Context->ContextData[Offset + 40];
  *(_QWORD *)&Context->ContextData[Offset + 40] = v28 + 3;
  *v28 = APPktUtilsPrepareForwardDataPacketComplete;
  v28[2] = v31;
  v29 = a5;
  v28[1] = a1;
  NetBuffer->Link.Alignment = 0;
  v13->Link.Region = (unsigned __int64)NetBuffer;
  *v29 = v13;
  v13 = 0;
  v33 = 0;
  *a6 = &MappedSystemVa[uBackFillSize];
LABEL_37:
  if ( v13 )
    Dot11FreeSendPacket(&v33);
  return v11;
}

```

## disassembly

```asm
0x140076194  mov     rax, rsp
0x140076197  mov     [rax+20h], r9d
0x14007619b  mov     [rax+18h], r8d
0x14007619f  mov     [rax+8], rcx
0x1400761a3  push    rbx
0x1400761a4  push    rbp
0x1400761a5  push    rsi
0x1400761a6  push    rdi
0x1400761a7  push    r12
0x1400761a9  push    r13
0x1400761ab  push    r14
0x1400761ad  push    r15
0x1400761af  sub     rsp, 48h
0x1400761b3  mov     rcx, [rcx]; struct _VELAN *
0x1400761b6  mov     r13, rdx
0x1400761b9  mov     edi, r8d
0x1400761bc  mov     qword ptr [rax+10h], 0
0x1400761c4  mov     r12d, [rcx+84h]
0x1400761cb  lea     r14d, [r12+r9]
0x1400761cf  cmp     r14d, r12d
0x1400761d2  jnb     short loc_14007620A
0x1400761d4  mov     ebx, 0C0010015h
0x1400761d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400761e0  lea     rax, WPP_GLOBAL_Control
0x1400761e7  cmp     rcx, rax
0x1400761ea  jz      loc_140076565
0x1400761f0  mov     rcx, [rcx+18h]
0x1400761f4  lea     r8, WPP_7d0e4632fdee3958307e1f8f9ef20022_Traceguids
0x1400761fb  mov     edx, 11h
0x140076200  call    WPP_SF_
0x140076205  jmp     loc_140076565
0x14007620a  mov     rsi, [rdx+20h]
0x14007620e  lea     rdx, [rsp+88h+arg_8]; struct _NET_BUFFER_LIST **
0x140076216  mov     [rsp+88h+var_50], rsi
0x14007621b  call    ?Dot11AllocateSendPacket@@YAHPEAU_VELAN@@PEAPEAU_NET_BUFFER_LIST@@@Z; Dot11AllocateSendPacket(_VELAN *,_NET_BUFFER_LIST * *)
0x140076220  mov     ebx, eax
0x140076222  test    eax, eax
0x140076224  jz      short loc_14007625E
0x140076226  mov     rcx, cs:WPP_GLOBAL_Control
0x14007622d  lea     rax, WPP_GLOBAL_Control
0x140076234  cmp     rcx, rax
0x140076237  jz      short loc_140076251
0x140076239  mov     rcx, [rcx+18h]
0x14007623d  lea     r8, WPP_7d0e4632fdee3958307e1f8f9ef20022_Traceguids
0x140076244  mov     edx, 12h
0x140076249  mov     r9d, ebx
0x14007624c  call    WPP_SF_d
0x140076251  mov     rbp, [rsp+88h+arg_8]
0x140076259  jmp     loc_140076553
0x14007625e  mov     eax, [r13+8]
0x140076262  mov     rbp, [rsp+88h+arg_8]
0x14007626a  mov     rdx, [rbp+10h]
0x14007626e  movzx   ecx, word ptr [rdx+0Ah]
0x140076272  mov     [rcx+rdx+24h], eax
0x140076276  mov     rcx, rdi
0x140076279  mov     rax, [rsi+8]
0x14007627d  mov     rbx, [rax+8]
0x140076281  cmp     [rbx+28h], edi
0x140076284  ja      short loc_140076291
0x140076286  sub     ecx, [rbx+28h]
0x140076289  mov     rbx, [rbx]
0x14007628c  cmp     [rbx+28h], ecx
0x14007628f  jbe     short loc_140076286
0x140076291  mov     edx, [rbx+28h]
0x140076294  xor     r9d, r9d; ChargeQuota
0x140076297  sub     edx, ecx; Length
0x140076299  mov     [rsp+88h+Irp], 0; Irp
0x1400762a2  add     rcx, [rbx+18h]; VirtualAddress
0x1400762a6  xor     r8d, r8d; SecondaryBuffer
0x1400762a9  call    cs:__imp_IoAllocateMdl
0x1400762b0  nop     dword ptr [rax+rax+00h]
0x1400762b5  mov     rdi, rax
0x1400762b8  test    rax, rax
0x1400762bb  jnz     short loc_1400762F1
0x1400762bd  mov     ebx, 0C000009Ah
0x1400762c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400762c9  lea     rax, WPP_GLOBAL_Control
0x1400762d0  cmp     rcx, rax
0x1400762d3  jz      loc_140076553
0x1400762d9  mov     rcx, [rcx+18h]
0x1400762dd  lea     edx, [rdi+13h]
0x1400762e0  lea     r8, WPP_7d0e4632fdee3958307e1f8f9ef20022_Traceguids
0x1400762e7  call    WPP_SF_
0x1400762ec  jmp     loc_140076553
0x1400762f1  mov     rcx, rdi; MemoryDescriptorList
0x1400762f4  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400762fb  nop     dword ptr [rax+rax+00h]
0x140076300  mov     rax, [rbx]
0x140076303  mov     [rdi], rax
0x140076306  cmp     r14d, 1F3Bh
0x14007630d  ja      loc_1400764E1
0x140076313  mov     eax, r14d
0x140076316  mov     ecx, 0FFFh; Base
0x14007631b  mov     edx, r14d; Length
0x14007631e  mov     [rsp+88h+Size], rax
0x140076323  call    cs:__imp_MmSizeOfMdl
0x14007632a  nop     dword ptr [rax+rax+00h]
0x14007632f  lea     ecx, [r14+10h]
0x140076333  lea     r15d, [rax+7]
0x140076337  and     r15d, 0FFFFFFF8h
0x14007633b  add     ecx, r15d
0x14007633e  cmp     ecx, 10h
0x140076341  jb      loc_1400764E1
0x140076347  mov     esi, 30366176h
0x14007634c  cmp     ecx, 40h ; '@'
0x14007634f  ja      short loc_14007635A
0x140076351  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140076358  jmp     short loc_14007638B
0x14007635a  cmp     ecx, 100h
0x140076360  ja      short loc_14007636B
0x140076362  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140076369  jmp     short loc_14007638B
0x14007636b  cmp     ecx, 400h
0x140076371  ja      short loc_14007637C
0x140076373  lea     rbx, Lookaside
0x14007637a  jmp     short loc_14007638B
0x14007637c  cmp     ecx, 800h
0x140076382  ja      short loc_14007639C
0x140076384  lea     rbx, stru_1400B0180
0x14007638b  mov     rcx, rbx; Lookaside
0x14007638e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140076395  nop     dword ptr [rax+rax+00h]
0x14007639a  jmp     short loc_1400763B2
0x14007639c  xor     ebx, ebx
0x14007639e  mov     edx, ecx
0x1400763a0  mov     r8d, esi
0x1400763a3  lea     ecx, [rbx+40h]
0x1400763a6  call    cs:__imp_ExAllocatePool2
0x1400763ad  nop     dword ptr [rax+rax+00h]
0x1400763b2  test    rax, rax
0x1400763b5  jz      loc_1400764E1
0x1400763bb  mov     [rax+8], esi
0x1400763be  lea     rsi, [rax+10h]
0x1400763c2  mov     [rax], rbx
0x1400763c5  test    rsi, rsi
0x1400763c8  jz      short loc_14007642A
0x1400763ca  mov     r9d, 0FFFh
0x1400763d0  mov     edx, r15d
0x1400763d3  add     rdx, rsi
0x1400763d6  mov     ecx, r14d
0x1400763d9  add     rcx, r9
0x1400763dc  mov     qword ptr [rsi], 0
0x1400763e3  mov     r8d, edx
0x1400763e6  mov     [rsi+28h], r14d
0x1400763ea  mov     eax, r8d
0x1400763ed  and     rdx, 0FFFFFFFFFFFFF000h
0x1400763f4  and     rax, r9
0x1400763f7  mov     [rsi+20h], rdx
0x1400763fb  add     rcx, rax
0x1400763fe  and     r8d, r9d
0x140076401  shr     rcx, 0Ch
0x140076405  xor     eax, eax
0x140076407  add     cx, 6
0x14007640b  mov     [rsi+0Ah], ax
0x14007640f  shl     cx, 3
0x140076413  mov     [rsi+8], cx
0x140076417  mov     rcx, rsi; MemoryDescriptorList
0x14007641a  mov     [rsi+2Ch], r8d
0x14007641e  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140076425  nop     dword ptr [rax+rax+00h]
0x14007642a  mov     r15, [rsi+18h]
0x14007642e  xor     edx, edx; Val
0x140076430  mov     r8, [rsp+88h+Size]; Size
0x140076435  mov     rcx, r15; void *
0x140076438  xor     ebx, ebx
0x14007643a  mov     [rsi], rdi
0x14007643d  mov     r14, rsi
0x140076440  call    memset
0x140076445  mov     r9d, [r13+3Ch]
0x140076449  mov     r8d, r12d; DataOffset
0x14007644c  add     r9d, [r13+38h]
0x140076450  mov     rdx, rsi; MdlChain
0x140076453  sub     r9d, [rsp+88h+arg_10]
0x14007645b  mov     r13, [rsp+88h+arg_0]
0x140076463  add     r9d, [rsp+88h+arg_18]; DataLength
0x14007646b  mov     rcx, [r13+0]
0x14007646f  mov     rcx, [rcx+38h]; PoolHandle
0x140076473  call    cs:__imp_NdisAllocateNetBuffer
0x14007647a  nop     dword ptr [rax+rax+00h]
0x14007647f  mov     r9, rax
0x140076482  test    rax, rax
0x140076485  jnz     short loc_1400764F7
0x140076487  mov     rcx, cs:WPP_GLOBAL_Control
0x14007648e  lea     rax, WPP_GLOBAL_Control
0x140076495  cmp     rcx, rax
0x140076498  jz      short loc_1400764AD
0x14007649a  mov     rcx, [rcx+18h]
0x14007649e  lea     edx, [rbx+14h]
0x1400764a1  lea     r8, WPP_7d0e4632fdee3958307e1f8f9ef20022_Traceguids
0x1400764a8  call    WPP_SF_
0x1400764ad  test    r14, r14
0x1400764b0  jz      short loc_1400764E1
0x1400764b2  lea     rcx, [r14-10h]; P
0x1400764b6  mov     rax, [rcx]
0x1400764b9  test    rax, rax
0x1400764bc  jz      short loc_1400764D2
0x1400764be  mov     rdx, rcx; Entry
0x1400764c1  mov     rcx, rax; Lookaside
0x1400764c4  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400764cb  nop     dword ptr [rax+rax+00h]
0x1400764d0  jmp     short loc_1400764E1
0x1400764d2  mov     edx, [rcx+8]; Tag
0x1400764d5  call    cs:__imp_ExFreePoolWithTag
0x1400764dc  nop     dword ptr [rax+rax+00h]
0x1400764e1  mov     rcx, rdi; Mdl
0x1400764e4  mov     ebx, 0C000009Ah
0x1400764e9  call    cs:__imp_IoFreeMdl
0x1400764f0  nop     dword ptr [rax+rax+00h]
0x1400764f5  jmp     short loc_140076553
0x1400764f7  mov     rdx, [rbp+10h]
0x1400764fb  movzx   ecx, word ptr [rdx+0Ah]
0x1400764ff  mov     r8, [rcx+rdx+38h]
0x140076504  lea     rax, [r8+18h]
0x140076508  mov     [rcx+rdx+38h], rax
0x14007650d  lea     rax, ?APPktUtilsPrepareForwardDataPacketComplete@@YAXPEAU_NET_BUFFER_LIST@@HPEAU_EXTAP_VELAN@@0@Z; APPktUtilsPrepareForwardDataPacketComplete(_NET_BUFFER_LIST *,int,_EXTAP_VELAN *,_NET_BUFFER_LIST *)
0x140076514  mov     [r8], rax
0x140076517  lea     rcx, [r15+r12]
0x14007651b  mov     rax, [rsp+88h+var_50]
0x140076520  mov     [r8+10h], rax
0x140076524  mov     rax, [rsp+88h+arg_20]
0x14007652c  mov     [r8+8], r13
0x140076530  mov     qword ptr [r9], 0
0x140076537  mov     [rbp+8], r9
0x14007653b  mov     [rax], rbp
0x14007653e  xor     ebp, ebp
0x140076540  mov     rax, [rsp+88h+arg_28]
0x140076548  mov     [rsp+88h+arg_8], rbp
0x140076550  mov     [rax], rcx
0x140076553  test    rbp, rbp
0x140076556  jz      short loc_140076565
0x140076558  lea     rcx, [rsp+88h+arg_8]; struct _NET_BUFFER_LIST **
0x140076560  call    ?Dot11FreeSendPacket@@YAXPEAPEAU_NET_BUFFER_LIST@@@Z; Dot11FreeSendPacket(_NET_BUFFER_LIST * *)
0x140076565  mov     eax, ebx
0x140076567  add     rsp, 48h
0x14007656b  pop     r15
0x14007656d  pop     r14
0x14007656f  pop     r13
0x140076571  pop     r12
0x140076573  pop     rdi
0x140076574  pop     rsi
0x140076575  pop     rbp
0x140076576  pop     rbx
0x140076577  retn
```
