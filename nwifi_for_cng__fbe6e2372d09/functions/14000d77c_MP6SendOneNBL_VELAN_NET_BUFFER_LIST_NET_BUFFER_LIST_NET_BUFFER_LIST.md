# MP6SendOneNBL(_VELAN *,_NET_BUFFER_LIST *,_NET_BUFFER_LIST * *,_NET_BUFFER_LIST * *)

- ea: `0x14000d77c`
- end: `0x14000dddc`
- name: `?MP6SendOneNBL@@YAHPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@PEAPEAU2@2@Z`
- size: `1632`
- prototype: `__int64 __fastcall(struct _VELAN *, struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST **, struct _NET_BUFFER_LIST **)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000d2e0`
- `0x14000d4b0`

## callees

- `0x14000d21c`
- `0x14000d77c`
- `0x14000dde4`
- `0x14000dec8`
- `0x14000e25c`
- `0x140010510`
- `0x140019314`
- `0x140038168`
- `0x14009bbb0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000dbb0`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000dbb0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000db24`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000db24`
- `ntoskrnl!IoFreeMdl` at `0x14000dbec`
- `ntoskrnl!IoFreeMdl` at `0x14000dbec`
- `ntoskrnl!IoAllocateMdl` at `0x14000dad3`
- `ntoskrnl!IoAllocateMdl` at `0x14000dad3`
- `NDIS!NdisAllocateNetBufferList` at `0x14000d8c2`
- `NDIS!NdisAllocateNetBufferList` at `0x14000d8c2`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x14000d97b`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x14000d97b`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000dd94`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000dd94`
- `NDIS!NdisFreeNetBufferListContext` at `0x14000dd7e`
- `NDIS!NdisFreeNetBufferListContext` at `0x14000dd7e`
- `NDIS!NdisAllocateNetBuffer` at `0x14000dbd5`
- `NDIS!NdisAllocateNetBuffer` at `0x14000dbd5`
- `NETIO!WfpNblInfoClone` at `0x14000d9a7`
- `NETIO!WfpNblInfoClone` at `0x14000d9a7`

## pseudocode

```c
__int64 __fastcall MP6SendOneNBL(
        struct _VELAN *a1,
        struct _NET_BUFFER_LIST *a2,
        struct _NET_BUFFER_LIST **a3,
        struct _NET_BUFFER_LIST **a4)
{
  void *v4; // r14
  unsigned int MacOptions; // edx
  int v9; // edi
  signed __int32 Value; // eax
  volatile signed __int32 *v11; // r12
  struct _MDL *v12; // r13
  _NET_BUFFER *FirstNetBuffer; // rax
  PNET_BUFFER_LIST NetBufferList; // rax
  PNET_BUFFER_LIST v15; // rsi
  _NET_BUFFER_LIST_CONTEXT *Context; // rdx
  _NET_BUFFER_LIST_CONTEXT *v17; // rdx
  __int64 Offset; // rcx
  _NET_BUFFER_LIST_CONTEXT *v19; // rdx
  __int64 v20; // rcx
  _QWORD *v21; // r8
  _NET_BUFFER_LIST_CONTEXT *v22; // rdi
  __int64 v23; // r12
  struct _ADAPT *v24; // rcx
  __int64 v25; // r8
  int v26; // eax
  _NET_BUFFER **p_Next; // rax
  struct _MDL *CurrentMdl; // r8
  struct _MDL *v29; // r12
  unsigned int CurrentMdlOffset; // edi
  struct _MDL *i; // rcx
  unsigned int ByteCount; // edx
  struct _MDL *Mdl; // rax
  struct _MDL *v34; // rdi
  unsigned int v35; // edx
  char *MappedSystemVa; // rax
  unsigned __int8 *v37; // rcx
  unsigned int v38; // r8d
  unsigned int v39; // r9d
  PNET_BUFFER NetBuffer; // rax
  _NET_BUFFER_LIST_CONTEXT *v41; // rdx
  __int64 v42; // rcx
  _QWORD *v43; // r8
  _NET_BUFFER_LIST_CONTEXT *v44; // rcx
  __int64 v45; // rax
  unsigned __int8 *v46; // rdx
  int Status; // r8d
  int Irp; // [rsp+20h] [rbp-89h]
  unsigned int v49; // [rsp+40h] [rbp-69h] BYREF
  struct _MDL *v50; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v51; // [rsp+50h] [rbp-59h] BYREF
  int v52; // [rsp+54h] [rbp-55h]
  unsigned int DataLength; // [rsp+58h] [rbp-51h]
  unsigned int v54; // [rsp+5Ch] [rbp-4Dh]
  _NET_BUFFER *v55; // [rsp+60h] [rbp-49h]
  struct _NET_BUFFER_LIST *v56; // [rsp+68h] [rbp-41h]
  _QWORD *p_Alignment; // [rsp+70h] [rbp-39h]
  struct _MDL *v58; // [rsp+78h] [rbp-31h]
  struct DOT11_MP60_SEND_CTX *v59; // [rsp+80h] [rbp-29h]
  struct _NET_BUFFER_LIST **v60; // [rsp+88h] [rbp-21h]
  __int128 v61; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int8 v62[8]; // [rsp+A0h] [rbp-9h] BYREF
  int v63; // [rsp+A8h] [rbp-1h]
  __int16 v64; // [rsp+ACh] [rbp+3h]

  v4 = a2->NetBufferListInfo[4];
  *(_QWORD *)&v61 = a4;
  v60 = a3;
  v52 = 0;
  if ( v4 )
  {
    MacOptions = a1->MacOptions;
    if ( (unsigned __int16)v4 >> 4 && (MacOptions & 0x200) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_c867dd3d8fa430bb45808a98b994f216_Traceguids);
      return 65539;
    }
    BYTE1(v49) = (unsigned int)v4 >> 4;
    if ( (MacOptions & 0x40) != 0 )
      LOBYTE(v49) = ((unsigned int)v4 >> 12) & 0xF | (32 * (_BYTE)v4);
    else
      LOBYTE(v49) = ((unsigned int)v4 >> 12) & 0xF;
    v52 = (unsigned __int16)v49;
    LOBYTE(v4) = BYTE2(v4) & 0xF;
  }
  v9 = 0;
  v56 = *a3;
  p_Alignment = *a4;
  do
  {
    Value = a1->Reference.Value;
    if ( (Value & 1) != 0 )
      return 3221291020LL;
  }
  while ( Value != _InterlockedCompareExchange((volatile signed __int32 *)&a1->Reference, Value + 2, Value) );
  v59 = AllocateAndInitializeOriginalNblContext(a2);
  v11 = (volatile signed __int32 *)v59;
  if ( v59 )
  {
    v12 = 0;
    _InterlockedIncrement((volatile signed __int32 *)&a1->OutstandingSends);
    FirstNetBuffer = a2->FirstNetBuffer;
    while ( 1 )
    {
      v55 = FirstNetBuffer;
      if ( !FirstNetBuffer )
        goto LABEL_62;
      NetBufferList = NdisAllocateNetBufferList(a1->hSendNetBufferListPool, 0x300u, a1->ContextSize - 768);
      v15 = NetBufferList;
      if ( !NetBufferList )
        break;
      Context = NetBufferList->Context;
      NetBufferList->SourceHandle = a1->hMiniport;
      memset(&Context->ContextData[Context->Offset], 0, 0x300u);
      v17 = v15->Context;
      Offset = v17->Offset;
      *(_QWORD *)&v17->ContextData[Offset + 40] = &v17->ContextData[Offset + 48];
      v15->NetBufferListInfo[6] = &v17->ContextData[Offset + 432];
      *(_QWORD *)&v17->ContextData[Offset] = a1;
      v19 = v15->Context;
      v20 = v19->Offset;
      v21 = *(_QWORD **)&v19->ContextData[v20 + 40];
      *(_QWORD *)&v19->ContextData[v20 + 40] = v21 + 3;
      *v21 = &Dot11SendNBComplete;
      v21[1] = a1;
      v21[2] = a2;
      _InterlockedIncrement(v11);
      v22 = v15->Context;
      v23 = v22->Offset;
      *(_QWORD *)&v22->ContextData[v23 + 24] = a2->NetBufferListInfo[6];
      v50 = (struct _MDL *)v15->NetBufferListInfo[6];
      NdisCopySendNetBufferListInfo(v15, a2);
      if ( v12 )
      {
        if ( v15 != (PNET_BUFFER_LIST)v12 )
        {
          LOBYTE(Irp) = 1;
          LOBYTE(v25) = 1;
          WfpNblInfoClone(v12, v15, v25, 0, Irp);
        }
      }
      else
      {
        v12 = (struct _MDL *)v15;
      }
      v15->NetBufferListInfo[6] = v50;
      if ( (_BYTE)v4 )
      {
        v22->ContextData[v23 + 20] |= 2u;
        v22->ContextData[v23 + 21] = (unsigned __int8)v4;
      }
      DataLength = v55->DataLength;
      if ( DataLength <= 0xE )
      {
        v9 = -1073676267;
        goto LABEL_60;
      }
      CurrentMdl = v55->CurrentMdl;
      v58 = CurrentMdl;
      v29 = CurrentMdl;
      v50 = CurrentMdl;
      v51 = 0;
      v49 = 0;
      if ( !CurrentMdl )
        goto LABEL_36;
      CurrentMdlOffset = v55->CurrentMdlOffset;
      for ( i = CurrentMdl; ; CurrentMdl = i )
      {
        ByteCount = CurrentMdl->ByteCount;
        if ( CurrentMdlOffset < ByteCount )
          break;
        i = v29->Next;
        v50 = i;
        v29 = i;
        if ( !i )
          goto LABEL_36;
        CurrentMdlOffset -= ByteCount;
      }
      v35 = ByteCount - CurrentMdlOffset;
      v54 = v35;
      if ( v35 < 0xE )
      {
        v9 = Dot11CopyMdlToBuffer(&v50, CurrentMdlOffset, v62, 0xEu, &v51, &v49);
        if ( v9 )
          goto LABEL_37;
        if ( v49 != 14 )
        {
LABEL_36:
          v9 = -1073741789;
          goto LABEL_37;
        }
        v29 = v50;
        v37 = v62;
        v38 = v51;
      }
      else
      {
        if ( (i->MdlFlags & 5) != 0 )
        {
          MappedSystemVa = (char *)i->MappedSystemVa;
        }
        else
        {
          MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(i, 0, MmCached, 0, 0, 0x40000000u);
          v35 = v54;
        }
        if ( !MappedSystemVa )
        {
          v9 = -1073741670;
LABEL_37:
          v24 = 0;
LABEL_60:
          Dot11SendNwifiNblCompletion(v24, v15, v9);
          goto LABEL_62;
        }
        v37 = (unsigned __int8 *)&MappedSystemVa[CurrentMdlOffset];
        if ( v35 <= 0xE )
        {
          v29 = v29->Next;
          v38 = 0;
        }
        else
        {
          v38 = CurrentMdlOffset + 14;
        }
      }
      v50 = v12;
      if ( v37 != v62 )
      {
        *(_QWORD *)v62 = *(_QWORD *)v37;
        v63 = *((_DWORD *)v37 + 2);
        v64 = *((_WORD *)v37 + 6);
      }
      Mdl = IoAllocateMdl((char *)v29->MappedSystemVa + v38, v29->ByteCount - v38, 0, 0, 0);
      v34 = Mdl;
      if ( !Mdl )
      {
        v9 = -1073741823;
        goto LABEL_60;
      }
      MmBuildMdlForNonPagedPool(Mdl);
      v39 = DataLength;
      v34->Next = v29->Next;
      NetBuffer = NdisAllocateNetBuffer(a1->hSendNetBufferPool, v34, 0, v39 - 14);
      if ( !NetBuffer )
      {
        IoFreeMdl(v34);
        v9 = -1073741670;
        goto LABEL_60;
      }
      NetBuffer->Link.Alignment = 0;
      v41 = v15->Context;
      v42 = v41->Offset;
      v43 = *(_QWORD **)&v41->ContextData[v42 + 40];
      *(_QWORD *)&v41->ContextData[v42 + 40] = v43 + 3;
      *v43 = Dot11PrepareEthernetPayloadPacketComplete;
      v43[1] = a1;
      v43[2] = 0;
      v15->Link.Region = (unsigned __int64)NetBuffer;
      v26 = Dot11PacketConverterSendPacket(a1, v15, v62, v52);
      v9 = v26;
      if ( v26 )
      {
        v15->Status = v26;
        goto LABEL_60;
      }
      p_Next = &v55->Next;
      v11 = (volatile signed __int32 *)v59;
      *((_DWORD *)v59 + 1) += v55->DataLength;
      if ( v56 )
        *p_Alignment = v15;
      else
        v56 = v15;
      FirstNetBuffer = *p_Next;
      p_Alignment = &v15->Link.Alignment;
    }
    v9 = -1073741670;
LABEL_62:
    *v60 = v56;
    *(_QWORD *)v61 = p_Alignment;
    v44 = a2->Context;
    v45 = v44->Offset;
    v46 = &v44->ContextData[v45];
    if ( *(_DWORD *)v46 )
    {
      if ( v9 )
        a2->Status = v9;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v46, 0xFFFFFFFF) == 1 )
      {
        Status = a2->Status;
        if ( Status )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              23,
              WPP_c867dd3d8fa430bb45808a98b994f216_Traceguids,
              a2,
              Status);
          }
          ++a1->TransmitFailuresOther;
        }
        else if ( v46[8] )
        {
          ++a1->GoodUcastTransmits;
          a1->GoodUcastTransmitBytes += *((unsigned int *)v46 + 1);
        }
        else if ( v46[9] )
        {
          ++a1->GoodBcastTransmits;
          a1->GoodBcastTransmitBytes += *((unsigned int *)v46 + 1);
        }
        else
        {
          ++a1->GoodMcastTransmits;
          a1->GoodMcastTransmitBytes += *((unsigned int *)v46 + 1);
        }
        NdisFreeNetBufferListContext(a2, 0x10u);
        NdisFSendNetBufferListsComplete(a1->hMiniport, a2, 0);
        _InterlockedDecrement((volatile signed __int32 *)&a1->OutstandingSends);
        _InterlockedAdd((volatile signed __int32 *)&a1->Reference, 0xFFFFFFFE);
      }
    }
    else
    {
      v61 = 0;
      if ( (byte_1400B2804 & 0x20) != 0 )
        McTemplateK0pppq_EtwWriteTransfer(
          (_DWORD)v44,
          (_DWORD)v46,
          (unsigned int)&v61,
          0,
          (char)a2,
          v45 + (_BYTE)v44 + 16,
          v9);
    }
    return 259;
  }
  else
  {
    _InterlockedAdd((volatile signed __int32 *)&a1->Reference, 0xFFFFFFFE);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14000d77c  push    rbp
0x14000d77e  push    rbx
0x14000d77f  push    rsi
0x14000d780  push    rdi
0x14000d781  push    r12
0x14000d783  push    r13
0x14000d785  push    r14
0x14000d787  push    r15
0x14000d789  lea     rbp, [rsp-1Fh]
0x14000d78e  sub     rsp, 0C8h
0x14000d795  mov     rax, cs:__security_cookie
0x14000d79c  xor     rax, rsp
0x14000d79f  mov     [rbp+57h+var_50], rax
0x14000d7a3  mov     r14, [rdx+0B0h]
0x14000d7aa  mov     r15, rdx
0x14000d7ad  mov     qword ptr [rbp+57h+var_70], r9
0x14000d7b1  mov     rbx, rcx
0x14000d7b4  mov     [rbp+57h+var_78], r8
0x14000d7b8  mov     [rbp+57h+var_AC], 0
0x14000d7bf  test    r14, r14
0x14000d7c2  jz      short loc_14000D83F
0x14000d7c4  mov     edx, [rcx+80h]
0x14000d7ca  mov     eax, r14d
0x14000d7cd  shr     eax, 4
0x14000d7d0  test    eax, 0FFFh
0x14000d7d5  jz      short loc_14000D80F
0x14000d7d7  bt      edx, 9
0x14000d7db  jb      short loc_14000D80F
0x14000d7dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d7e4  lea     rax, WPP_GLOBAL_Control
0x14000d7eb  cmp     rcx, rax
0x14000d7ee  jz      short loc_14000D805
0x14000d7f0  mov     rcx, [rcx+18h]
0x14000d7f4  lea     r8, WPP_c867dd3d8fa430bb45808a98b994f216_Traceguids
0x14000d7fb  mov     edx, 18h
0x14000d800  call    WPP_SF_
0x14000d805  mov     eax, 10003h
0x14000d80a  jmp     loc_14000DDBB
0x14000d80f  mov     ecx, r14d
0x14000d812  mov     byte ptr [rbp+57h+var_C0+1], al
0x14000d815  shr     ecx, 0Ch
0x14000d818  and     cl, 0Fh
0x14000d81b  test    dl, 40h
0x14000d81e  jz      short loc_14000D82D
0x14000d820  mov     al, r14b
0x14000d823  shl     al, 5
0x14000d826  or      al, cl
0x14000d828  mov     byte ptr [rbp+57h+var_C0], al
0x14000d82b  jmp     short loc_14000D830
0x14000d82d  mov     byte ptr [rbp+57h+var_C0], cl
0x14000d830  movzx   eax, word ptr [rbp+57h+var_C0]
0x14000d834  shr     r14d, 10h
0x14000d838  mov     [rbp+57h+var_AC], eax
0x14000d83b  and     r14b, 0Fh
0x14000d83f  mov     rax, [r8]
0x14000d842  xor     edi, edi
0x14000d844  mov     [rbp+57h+var_98], rax
0x14000d848  mov     rax, [r9]
0x14000d84b  mov     [rbp+57h+var_90], rax
0x14000d84f  mov     eax, [rbx+1530h]
0x14000d855  test    al, 1
0x14000d857  jnz     loc_14000DDB6
0x14000d85d  lea     ecx, [rax+2]
0x14000d860  lock cmpxchg [rbx+1530h], ecx
0x14000d868  jnz     short loc_14000D84F
0x14000d86a  mov     rcx, r15; struct _NET_BUFFER_LIST *
0x14000d86d  call    ?AllocateAndInitializeOriginalNblContext@@YAPEAUDOT11_MP60_SEND_CTX@@PEAU_NET_BUFFER_LIST@@@Z; AllocateAndInitializeOriginalNblContext(_NET_BUFFER_LIST *)
0x14000d872  mov     [rbp+57h+var_80], rax
0x14000d876  mov     r12, rax
0x14000d879  test    rax, rax
0x14000d87c  jnz     short loc_14000D890
0x14000d87e  lock add dword ptr [rbx+1530h], 0FFFFFFFEh
0x14000d886  mov     eax, 0C000009Ah
0x14000d88b  jmp     loc_14000DDBB
0x14000d890  xor     r13d, r13d
0x14000d893  lock inc dword ptr [rbx+1358h]
0x14000d89a  mov     rax, [r15+8]
0x14000d89e  mov     [rbp+57h+var_A0], rax
0x14000d8a2  mov     ecx, 300h
0x14000d8a7  test    rax, rax
0x14000d8aa  jz      loc_14000DC6A
0x14000d8b0  movzx   r8d, word ptr [rbx+1F9Ch]
0x14000d8b8  mov     edx, ecx; ContextSize
0x14000d8ba  sub     r8w, cx; ContextBackFill
0x14000d8be  mov     rcx, [rbx+30h]; PoolHandle
0x14000d8c2  call    cs:__imp_NdisAllocateNetBufferList
0x14000d8c9  nop     dword ptr [rax+rax+00h]
0x14000d8ce  mov     rsi, rax
0x14000d8d1  test    rax, rax
0x14000d8d4  jz      loc_14000DC65
0x14000d8da  mov     rdx, [rax+10h]
0x14000d8de  mov     r8d, 300h; Size
0x14000d8e4  mov     rcx, [rbx+20h]
0x14000d8e8  mov     [rax+78h], rcx
0x14000d8ec  movzx   ecx, word ptr [rdx+0Ah]
0x14000d8f0  add     rcx, 10h
0x14000d8f4  add     rcx, rdx; void *
0x14000d8f7  xor     edx, edx; Val
0x14000d8f9  call    memset
0x14000d8fe  mov     rdx, [rsi+10h]
0x14000d902  movzx   ecx, word ptr [rdx+0Ah]
0x14000d906  lea     rax, [rdx+40h]
0x14000d90a  add     rax, rcx
0x14000d90d  mov     [rcx+rdx+38h], rax
0x14000d912  lea     rax, [rdx+1C0h]
0x14000d919  add     rax, rcx
0x14000d91c  mov     [rsi+0C0h], rax
0x14000d923  mov     [rcx+rdx+10h], rbx
0x14000d928  mov     rdx, [rsi+10h]
0x14000d92c  movzx   ecx, word ptr [rdx+0Ah]
0x14000d930  mov     r8, [rcx+rdx+38h]
0x14000d935  lea     rax, [r8+18h]
0x14000d939  mov     [rcx+rdx+38h], rax
0x14000d93e  lea     rax, Dot11SendNBComplete
0x14000d945  mov     [r8], rax
0x14000d948  mov     [r8+8], rbx
0x14000d94c  mov     [r8+10h], r15
0x14000d950  lock inc dword ptr [r12]
0x14000d955  mov     rdi, [rsi+10h]
0x14000d959  mov     rdx, r15; SrcNetBufferList
0x14000d95c  mov     rax, [r15+0C0h]
0x14000d963  mov     rcx, rsi; DestNetBufferList
0x14000d966  movzx   r12d, word ptr [rdi+0Ah]
0x14000d96b  mov     [r12+rdi+28h], rax
0x14000d970  mov     rax, [rsi+0C0h]
0x14000d977  mov     [rbp+57h+var_B8], rax
0x14000d97b  call    cs:__imp_NdisCopySendNetBufferListInfo
0x14000d982  nop     dword ptr [rax+rax+00h]
0x14000d987  test    r13, r13
0x14000d98a  jnz     short loc_14000D991
0x14000d98c  mov     r13, rsi
0x14000d98f  jmp     short loc_14000D9B3
0x14000d991  cmp     rsi, r13
0x14000d994  jz      short loc_14000D9B3
0x14000d996  xor     r9d, r9d
0x14000d999  mov     byte ptr [rsp+100h+Irp], 1
0x14000d99e  mov     r8b, 1
0x14000d9a1  mov     rdx, rsi
0x14000d9a4  mov     rcx, r13
0x14000d9a7  call    cs:__imp_WfpNblInfoClone
0x14000d9ae  nop     dword ptr [rax+rax+00h]
0x14000d9b3  mov     rax, [rbp+57h+var_B8]
0x14000d9b7  mov     [rsi+0C0h], rax
0x14000d9be  test    r14b, r14b
0x14000d9c1  jz      short loc_14000D9CE
0x14000d9c3  or      byte ptr [r12+rdi+24h], 2
0x14000d9c9  mov     [r12+rdi+25h], r14b
0x14000d9ce  mov     rdi, [rbp+57h+var_A0]
0x14000d9d2  mov     eax, [rdi+18h]
0x14000d9d5  mov     [rbp+57h+var_A8], eax
0x14000d9d8  cmp     eax, 0Eh
0x14000d9db  ja      short loc_14000DA2F
0x14000d9dd  mov     edi, 0C0010015h
0x14000d9e2  test    edi, edi
0x14000d9e4  jnz     loc_14000DC58
0x14000d9ea  movzx   r9d, word ptr [rbp+57h+var_AC]; unsigned __int16
0x14000d9ef  lea     r8, [rbp+57h+var_60]; unsigned __int8 *
0x14000d9f3  mov     rdx, rsi; struct _NET_BUFFER_LIST *
0x14000d9f6  mov     rcx, rbx; struct _VELAN *
0x14000d9f9  call    ?Dot11PacketConverterSendPacket@@YAHPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@PEAEG@Z; Dot11PacketConverterSendPacket(_VELAN *,_NET_BUFFER_LIST *,uchar *,ushort)
0x14000d9fe  mov     edi, eax
0x14000da00  test    eax, eax
0x14000da02  jnz     loc_14000DC52
0x14000da08  mov     rax, [rbp+57h+var_A0]
0x14000da0c  mov     r12, [rbp+57h+var_80]
0x14000da10  mov     ecx, [rax+18h]
0x14000da13  add     [r12+4], ecx
0x14000da18  cmp     [rbp+57h+var_98], 0
0x14000da1d  jz      loc_14000DC42
0x14000da23  mov     rcx, [rbp+57h+var_90]
0x14000da27  mov     [rcx], rsi
0x14000da2a  jmp     loc_14000DC46
0x14000da2f  mov     r8, [rdi+8]
0x14000da33  mov     [rbp+57h+var_88], r8
0x14000da37  mov     r12, r8
0x14000da3a  mov     [rbp+57h+var_B8], r8
0x14000da3e  mov     [rbp+57h+var_B0], 0
0x14000da45  mov     [rbp+57h+var_C0], 0
0x14000da4c  test    r8, r8
0x14000da4f  jz      short loc_14000DA7A
0x14000da51  mov     edi, [rdi+10h]
0x14000da54  mov     rcx, r8; MemoryDescriptorList
0x14000da57  mov     edx, [r8+28h]
0x14000da5b  cmp     edi, edx
0x14000da5d  jb      loc_14000DAF5
0x14000da63  mov     rcx, [r12]
0x14000da67  mov     [rbp+57h+var_B8], rcx
0x14000da6b  mov     r12, rcx
0x14000da6e  test    rcx, rcx
0x14000da71  jz      short loc_14000DA7A
0x14000da73  sub     edi, edx
0x14000da75  mov     r8, rcx
0x14000da78  jmp     short loc_14000DA57
0x14000da7a  mov     edi, 0C0000023h
0x14000da7f  mov     r12, [rbp+57h+var_88]
0x14000da83  xor     r8d, r8d
0x14000da86  xor     ecx, ecx
0x14000da88  test    edi, edi
0x14000da8a  jnz     loc_14000DC58
0x14000da90  lea     rax, [rbp+57h+var_60]
0x14000da94  mov     [rbp+57h+var_B8], r13
0x14000da98  cmp     rcx, rax
0x14000da9b  jz      short loc_14000DAB4
0x14000da9d  movsd   xmm0, qword ptr [rcx]
0x14000daa1  movsd   qword ptr [rbp+57h+var_60], xmm0
0x14000daa6  mov     eax, [rcx+8]
0x14000daa9  mov     [rbp+57h+var_58], eax
0x14000daac  movzx   eax, word ptr [rcx+0Ch]
0x14000dab0  mov     [rbp+57h+var_54], ax
0x14000dab4  mov     edx, [r12+28h]
0x14000dab9  xor     r9d, r9d; ChargeQuota
0x14000dabc  mov     ecx, r8d
0x14000dabf  sub     edx, r8d; Length
0x14000dac2  add     rcx, [r12+18h]; VirtualAddress
0x14000dac7  xor     r8d, r8d; SecondaryBuffer
0x14000daca  mov     [rsp+100h+Irp], 0; Irp
0x14000dad3  call    cs:__imp_IoAllocateMdl
0x14000dada  nop     dword ptr [rax+rax+00h]
0x14000dadf  mov     rdi, rax
0x14000dae2  test    rax, rax
0x14000dae5  jnz     loc_14000DBAD
0x14000daeb  mov     edi, 0C0000001h
0x14000daf0  jmp     loc_14000D9E2
0x14000daf5  sub     edx, edi
0x14000daf7  mov     [rbp+57h+var_A4], edx
0x14000dafa  cmp     edx, 0Eh
0x14000dafd  jb      short loc_14000DB61
0x14000daff  test    byte ptr [rcx+0Ah], 5
0x14000db03  jz      short loc_14000DB0B
0x14000db05  mov     rax, [rcx+18h]
0x14000db09  jmp     short loc_14000DB33
0x14000db0b  xor     r9d, r9d; RequestedAddress
0x14000db0e  mov     [rsp+100h+Priority], 40000000h; Priority
0x14000db16  xor     edx, edx; AccessMode
0x14000db18  mov     dword ptr [rsp+100h+Irp], 0; BugCheckOnFailure
0x14000db20  lea     r8d, [r9+1]; CacheType
0x14000db24  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000db2b  nop     dword ptr [rax+rax+00h]
0x14000db30  mov     edx, [rbp+57h+var_A4]
0x14000db33  test    rax, rax
0x14000db36  jnz     short loc_14000DB42
0x14000db38  mov     edi, 0C000009Ah
0x14000db3d  jmp     loc_14000DA7F
0x14000db42  mov     ecx, edi
0x14000db44  add     rcx, rax
0x14000db47  cmp     edx, 0Eh
0x14000db4a  jbe     short loc_14000DB55
0x14000db4c  lea     r8d, [rdi+0Eh]
0x14000db50  jmp     loc_14000DA90
0x14000db55  mov     r12, [r12]
0x14000db59  xor     r8d, r8d
0x14000db5c  jmp     loc_14000DA90
0x14000db61  lea     rax, [rbp+57h+var_C0]
0x14000db65  mov     r9d, 0Eh; unsigned int
0x14000db6b  mov     qword ptr [rsp+100h+Priority], rax; unsigned int *
0x14000db70  lea     r8, [rbp+57h+var_60]; void *
0x14000db74  lea     rax, [rbp+57h+var_B0]
0x14000db78  mov     edx, edi; unsigned int
0x14000db7a  lea     rcx, [rbp+57h+var_B8]; struct _MDL **
0x14000db7e  mov     [rsp+100h+Irp], rax; unsigned int *
0x14000db83  call    ?Dot11CopyMdlToBuffer@@YAHPEAPEAU_MDL@@KPEAXKPEAK2@Z; Dot11CopyMdlToBuffer(_MDL * *,ulong,void *,ulong,ulong *,ulong *)
0x14000db88  mov     edi, eax
0x14000db8a  test    eax, eax
0x14000db8c  jnz     loc_14000DA7F
0x14000db92  cmp     [rbp+57h+var_C0], 0Eh
0x14000db96  jnz     loc_14000DA7A
0x14000db9c  mov     r12, [rbp+57h+var_B8]
0x14000dba0  lea     rcx, [rbp+57h+var_60]
0x14000dba4  mov     r8d, [rbp+57h+var_B0]
0x14000dba8  jmp     loc_14000DA90
0x14000dbad  mov     rcx, rdi; MemoryDescriptorList
0x14000dbb0  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14000dbb7  nop     dword ptr [rax+rax+00h]
0x14000dbbc  mov     rax, [r12]
0x14000dbc0  xor     r8d, r8d; DataOffset
0x14000dbc3  mov     r9d, [rbp+57h+var_A8]
0x14000dbc7  mov     rdx, rdi; MdlChain
0x14000dbca  mov     [rdi], rax
0x14000dbcd  add     r9d, 0FFFFFFF2h; DataLength
0x14000dbd1  mov     rcx, [rbx+38h]; PoolHandle
0x14000dbd5  call    cs:__imp_NdisAllocateNetBuffer
0x14000dbdc  nop     dword ptr [rax+rax+00h]
0x14000dbe1  mov     r9, rax
0x14000dbe4  test    rax, rax
0x14000dbe7  jnz     short loc_14000DC06
0x14000dbe9  mov     rcx, rdi; Mdl
0x14000dbec  call    cs:__imp_IoFreeMdl
0x14000dbf3  nop     dword ptr [rax+rax+00h]
0x14000dbf8  mov     r13, [rbp+57h+var_B8]
0x14000dbfc  mov     edi, 0C000009Ah
0x14000dc01  jmp     loc_14000D9E2
0x14000dc06  mov     qword ptr [rax], 0
0x14000dc0d  mov     rdx, [rsi+10h]
0x14000dc11  movzx   ecx, word ptr [rdx+0Ah]
0x14000dc15  mov     r8, [rcx+rdx+38h]
0x14000dc1a  lea     rax, [r8+18h]
0x14000dc1e  mov     [rcx+rdx+38h], rax
0x14000dc23  lea     rax, Dot11PrepareEthernetPayloadPacketComplete
0x14000dc2a  mov     [r8], rax
0x14000dc2d  mov     [r8+8], rbx
  ... truncated ...
```
