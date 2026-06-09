# MP6SendOneNBL(_VELAN *,_NET_BUFFER_LIST *,_NET_BUFFER_LIST * *,_NET_BUFFER_LIST * *)

- ea: `0x14000d78c`
- end: `0x14000ddec`
- name: `?MP6SendOneNBL@@YAHPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@PEAPEAU2@2@Z`
- size: `1632`
- prototype: `__int64 __fastcall(struct _VELAN *, struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST **, struct _NET_BUFFER_LIST **)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000d2f0`
- `0x14000d4c0`

## callees

- `0x14000d22c`
- `0x14000d78c`
- `0x14000ddf4`
- `0x14000ded8`
- `0x14000e26c`
- `0x140010520`
- `0x140019314`
- `0x140037f48`
- `0x14009a3d0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000dbc0`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000dbc0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000db34`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000db34`
- `ntoskrnl!IoFreeMdl` at `0x14000dbfc`
- `ntoskrnl!IoFreeMdl` at `0x14000dbfc`
- `ntoskrnl!IoAllocateMdl` at `0x14000dae3`
- `ntoskrnl!IoAllocateMdl` at `0x14000dae3`
- `NDIS!NdisAllocateNetBufferList` at `0x14000d8d2`
- `NDIS!NdisAllocateNetBufferList` at `0x14000d8d2`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x14000d98b`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x14000d98b`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000dda4`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000dda4`
- `NDIS!NdisFreeNetBufferListContext` at `0x14000dd8e`
- `NDIS!NdisFreeNetBufferListContext` at `0x14000dd8e`
- `NDIS!NdisAllocateNetBuffer` at `0x14000dbe5`
- `NDIS!NdisAllocateNetBuffer` at `0x14000dbe5`
- `NETIO!WfpNblInfoClone` at `0x14000d9b7`
- `NETIO!WfpNblInfoClone` at `0x14000d9b7`

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
      if ( (byte_1400AF804 & 0x20) != 0 )
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
0x14000d78c  push    rbp
0x14000d78e  push    rbx
0x14000d78f  push    rsi
0x14000d790  push    rdi
0x14000d791  push    r12
0x14000d793  push    r13
0x14000d795  push    r14
0x14000d797  push    r15
0x14000d799  lea     rbp, [rsp-1Fh]
0x14000d79e  sub     rsp, 0C8h
0x14000d7a5  mov     rax, cs:__security_cookie
0x14000d7ac  xor     rax, rsp
0x14000d7af  mov     [rbp+57h+var_50], rax
0x14000d7b3  mov     r14, [rdx+0B0h]
0x14000d7ba  mov     r15, rdx
0x14000d7bd  mov     qword ptr [rbp+57h+var_70], r9
0x14000d7c1  mov     rbx, rcx
0x14000d7c4  mov     [rbp+57h+var_78], r8
0x14000d7c8  mov     [rbp+57h+var_AC], 0
0x14000d7cf  test    r14, r14
0x14000d7d2  jz      short loc_14000D84F
0x14000d7d4  mov     edx, [rcx+80h]
0x14000d7da  mov     eax, r14d
0x14000d7dd  shr     eax, 4
0x14000d7e0  test    eax, 0FFFh
0x14000d7e5  jz      short loc_14000D81F
0x14000d7e7  bt      edx, 9
0x14000d7eb  jb      short loc_14000D81F
0x14000d7ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d7f4  lea     rax, WPP_GLOBAL_Control
0x14000d7fb  cmp     rcx, rax
0x14000d7fe  jz      short loc_14000D815
0x14000d800  mov     rcx, [rcx+18h]
0x14000d804  lea     r8, WPP_c867dd3d8fa430bb45808a98b994f216_Traceguids
0x14000d80b  mov     edx, 18h
0x14000d810  call    WPP_SF_
0x14000d815  mov     eax, 10003h
0x14000d81a  jmp     loc_14000DDCB
0x14000d81f  mov     ecx, r14d
0x14000d822  mov     byte ptr [rbp+57h+var_C0+1], al
0x14000d825  shr     ecx, 0Ch
0x14000d828  and     cl, 0Fh
0x14000d82b  test    dl, 40h
0x14000d82e  jz      short loc_14000D83D
0x14000d830  mov     al, r14b
0x14000d833  shl     al, 5
0x14000d836  or      al, cl
0x14000d838  mov     byte ptr [rbp+57h+var_C0], al
0x14000d83b  jmp     short loc_14000D840
0x14000d83d  mov     byte ptr [rbp+57h+var_C0], cl
0x14000d840  movzx   eax, word ptr [rbp+57h+var_C0]
0x14000d844  shr     r14d, 10h
0x14000d848  mov     [rbp+57h+var_AC], eax
0x14000d84b  and     r14b, 0Fh
0x14000d84f  mov     rax, [r8]
0x14000d852  xor     edi, edi
0x14000d854  mov     [rbp+57h+var_98], rax
0x14000d858  mov     rax, [r9]
0x14000d85b  mov     [rbp+57h+var_90], rax
0x14000d85f  mov     eax, [rbx+1530h]
0x14000d865  test    al, 1
0x14000d867  jnz     loc_14000DDC6
0x14000d86d  lea     ecx, [rax+2]
0x14000d870  lock cmpxchg [rbx+1530h], ecx
0x14000d878  jnz     short loc_14000D85F
0x14000d87a  mov     rcx, r15; struct _NET_BUFFER_LIST *
0x14000d87d  call    ?AllocateAndInitializeOriginalNblContext@@YAPEAUDOT11_MP60_SEND_CTX@@PEAU_NET_BUFFER_LIST@@@Z; AllocateAndInitializeOriginalNblContext(_NET_BUFFER_LIST *)
0x14000d882  mov     [rbp+57h+var_80], rax
0x14000d886  mov     r12, rax
0x14000d889  test    rax, rax
0x14000d88c  jnz     short loc_14000D8A0
0x14000d88e  lock add dword ptr [rbx+1530h], 0FFFFFFFEh
0x14000d896  mov     eax, 0C000009Ah
0x14000d89b  jmp     loc_14000DDCB
0x14000d8a0  xor     r13d, r13d
0x14000d8a3  lock inc dword ptr [rbx+1358h]
0x14000d8aa  mov     rax, [r15+8]
0x14000d8ae  mov     [rbp+57h+var_A0], rax
0x14000d8b2  mov     ecx, 300h
0x14000d8b7  test    rax, rax
0x14000d8ba  jz      loc_14000DC7A
0x14000d8c0  movzx   r8d, word ptr [rbx+1F9Ch]
0x14000d8c8  mov     edx, ecx; ContextSize
0x14000d8ca  sub     r8w, cx; ContextBackFill
0x14000d8ce  mov     rcx, [rbx+30h]; PoolHandle
0x14000d8d2  call    cs:__imp_NdisAllocateNetBufferList
0x14000d8d9  nop     dword ptr [rax+rax+00h]
0x14000d8de  mov     rsi, rax
0x14000d8e1  test    rax, rax
0x14000d8e4  jz      loc_14000DC75
0x14000d8ea  mov     rdx, [rax+10h]
0x14000d8ee  mov     r8d, 300h; Size
0x14000d8f4  mov     rcx, [rbx+20h]
0x14000d8f8  mov     [rax+78h], rcx
0x14000d8fc  movzx   ecx, word ptr [rdx+0Ah]
0x14000d900  add     rcx, 10h
0x14000d904  add     rcx, rdx; void *
0x14000d907  xor     edx, edx; Val
0x14000d909  call    memset
0x14000d90e  mov     rdx, [rsi+10h]
0x14000d912  movzx   ecx, word ptr [rdx+0Ah]
0x14000d916  lea     rax, [rdx+40h]
0x14000d91a  add     rax, rcx
0x14000d91d  mov     [rcx+rdx+38h], rax
0x14000d922  lea     rax, [rdx+1C0h]
0x14000d929  add     rax, rcx
0x14000d92c  mov     [rsi+0C0h], rax
0x14000d933  mov     [rcx+rdx+10h], rbx
0x14000d938  mov     rdx, [rsi+10h]
0x14000d93c  movzx   ecx, word ptr [rdx+0Ah]
0x14000d940  mov     r8, [rcx+rdx+38h]
0x14000d945  lea     rax, [r8+18h]
0x14000d949  mov     [rcx+rdx+38h], rax
0x14000d94e  lea     rax, Dot11SendNBComplete
0x14000d955  mov     [r8], rax
0x14000d958  mov     [r8+8], rbx
0x14000d95c  mov     [r8+10h], r15
0x14000d960  lock inc dword ptr [r12]
0x14000d965  mov     rdi, [rsi+10h]
0x14000d969  mov     rdx, r15; SrcNetBufferList
0x14000d96c  mov     rax, [r15+0C0h]
0x14000d973  mov     rcx, rsi; DestNetBufferList
0x14000d976  movzx   r12d, word ptr [rdi+0Ah]
0x14000d97b  mov     [r12+rdi+28h], rax
0x14000d980  mov     rax, [rsi+0C0h]
0x14000d987  mov     [rbp+57h+var_B8], rax
0x14000d98b  call    cs:__imp_NdisCopySendNetBufferListInfo
0x14000d992  nop     dword ptr [rax+rax+00h]
0x14000d997  test    r13, r13
0x14000d99a  jnz     short loc_14000D9A1
0x14000d99c  mov     r13, rsi
0x14000d99f  jmp     short loc_14000D9C3
0x14000d9a1  cmp     rsi, r13
0x14000d9a4  jz      short loc_14000D9C3
0x14000d9a6  xor     r9d, r9d
0x14000d9a9  mov     byte ptr [rsp+100h+Irp], 1
0x14000d9ae  mov     r8b, 1
0x14000d9b1  mov     rdx, rsi
0x14000d9b4  mov     rcx, r13
0x14000d9b7  call    cs:__imp_WfpNblInfoClone
0x14000d9be  nop     dword ptr [rax+rax+00h]
0x14000d9c3  mov     rax, [rbp+57h+var_B8]
0x14000d9c7  mov     [rsi+0C0h], rax
0x14000d9ce  test    r14b, r14b
0x14000d9d1  jz      short loc_14000D9DE
0x14000d9d3  or      byte ptr [r12+rdi+24h], 2
0x14000d9d9  mov     [r12+rdi+25h], r14b
0x14000d9de  mov     rdi, [rbp+57h+var_A0]
0x14000d9e2  mov     eax, [rdi+18h]
0x14000d9e5  mov     [rbp+57h+var_A8], eax
0x14000d9e8  cmp     eax, 0Eh
0x14000d9eb  ja      short loc_14000DA3F
0x14000d9ed  mov     edi, 0C0010015h
0x14000d9f2  test    edi, edi
0x14000d9f4  jnz     loc_14000DC68
0x14000d9fa  movzx   r9d, word ptr [rbp+57h+var_AC]; unsigned __int16
0x14000d9ff  lea     r8, [rbp+57h+var_60]; unsigned __int8 *
0x14000da03  mov     rdx, rsi; struct _NET_BUFFER_LIST *
0x14000da06  mov     rcx, rbx; struct _VELAN *
0x14000da09  call    ?Dot11PacketConverterSendPacket@@YAHPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@PEAEG@Z; Dot11PacketConverterSendPacket(_VELAN *,_NET_BUFFER_LIST *,uchar *,ushort)
0x14000da0e  mov     edi, eax
0x14000da10  test    eax, eax
0x14000da12  jnz     loc_14000DC62
0x14000da18  mov     rax, [rbp+57h+var_A0]
0x14000da1c  mov     r12, [rbp+57h+var_80]
0x14000da20  mov     ecx, [rax+18h]
0x14000da23  add     [r12+4], ecx
0x14000da28  cmp     [rbp+57h+var_98], 0
0x14000da2d  jz      loc_14000DC52
0x14000da33  mov     rcx, [rbp+57h+var_90]
0x14000da37  mov     [rcx], rsi
0x14000da3a  jmp     loc_14000DC56
0x14000da3f  mov     r8, [rdi+8]
0x14000da43  mov     [rbp+57h+var_88], r8
0x14000da47  mov     r12, r8
0x14000da4a  mov     [rbp+57h+var_B8], r8
0x14000da4e  mov     [rbp+57h+var_B0], 0
0x14000da55  mov     [rbp+57h+var_C0], 0
0x14000da5c  test    r8, r8
0x14000da5f  jz      short loc_14000DA8A
0x14000da61  mov     edi, [rdi+10h]
0x14000da64  mov     rcx, r8; MemoryDescriptorList
0x14000da67  mov     edx, [r8+28h]
0x14000da6b  cmp     edi, edx
0x14000da6d  jb      loc_14000DB05
0x14000da73  mov     rcx, [r12]
0x14000da77  mov     [rbp+57h+var_B8], rcx
0x14000da7b  mov     r12, rcx
0x14000da7e  test    rcx, rcx
0x14000da81  jz      short loc_14000DA8A
0x14000da83  sub     edi, edx
0x14000da85  mov     r8, rcx
0x14000da88  jmp     short loc_14000DA67
0x14000da8a  mov     edi, 0C0000023h
0x14000da8f  mov     r12, [rbp+57h+var_88]
0x14000da93  xor     r8d, r8d
0x14000da96  xor     ecx, ecx
0x14000da98  test    edi, edi
0x14000da9a  jnz     loc_14000DC68
0x14000daa0  lea     rax, [rbp+57h+var_60]
0x14000daa4  mov     [rbp+57h+var_B8], r13
0x14000daa8  cmp     rcx, rax
0x14000daab  jz      short loc_14000DAC4
0x14000daad  movsd   xmm0, qword ptr [rcx]
0x14000dab1  movsd   qword ptr [rbp+57h+var_60], xmm0
0x14000dab6  mov     eax, [rcx+8]
0x14000dab9  mov     [rbp+57h+var_58], eax
0x14000dabc  movzx   eax, word ptr [rcx+0Ch]
0x14000dac0  mov     [rbp+57h+var_54], ax
0x14000dac4  mov     edx, [r12+28h]
0x14000dac9  xor     r9d, r9d; ChargeQuota
0x14000dacc  mov     ecx, r8d
0x14000dacf  sub     edx, r8d; Length
0x14000dad2  add     rcx, [r12+18h]; VirtualAddress
0x14000dad7  xor     r8d, r8d; SecondaryBuffer
0x14000dada  mov     [rsp+100h+Irp], 0; Irp
0x14000dae3  call    cs:__imp_IoAllocateMdl
0x14000daea  nop     dword ptr [rax+rax+00h]
0x14000daef  mov     rdi, rax
0x14000daf2  test    rax, rax
0x14000daf5  jnz     loc_14000DBBD
0x14000dafb  mov     edi, 0C0000001h
0x14000db00  jmp     loc_14000D9F2
0x14000db05  sub     edx, edi
0x14000db07  mov     [rbp+57h+var_A4], edx
0x14000db0a  cmp     edx, 0Eh
0x14000db0d  jb      short loc_14000DB71
0x14000db0f  test    byte ptr [rcx+0Ah], 5
0x14000db13  jz      short loc_14000DB1B
0x14000db15  mov     rax, [rcx+18h]
0x14000db19  jmp     short loc_14000DB43
0x14000db1b  xor     r9d, r9d; RequestedAddress
0x14000db1e  mov     [rsp+100h+Priority], 40000000h; Priority
0x14000db26  xor     edx, edx; AccessMode
0x14000db28  mov     dword ptr [rsp+100h+Irp], 0; BugCheckOnFailure
0x14000db30  lea     r8d, [r9+1]; CacheType
0x14000db34  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000db3b  nop     dword ptr [rax+rax+00h]
0x14000db40  mov     edx, [rbp+57h+var_A4]
0x14000db43  test    rax, rax
0x14000db46  jnz     short loc_14000DB52
0x14000db48  mov     edi, 0C000009Ah
0x14000db4d  jmp     loc_14000DA8F
0x14000db52  mov     ecx, edi
0x14000db54  add     rcx, rax
0x14000db57  cmp     edx, 0Eh
0x14000db5a  jbe     short loc_14000DB65
0x14000db5c  lea     r8d, [rdi+0Eh]
0x14000db60  jmp     loc_14000DAA0
0x14000db65  mov     r12, [r12]
0x14000db69  xor     r8d, r8d
0x14000db6c  jmp     loc_14000DAA0
0x14000db71  lea     rax, [rbp+57h+var_C0]
0x14000db75  mov     r9d, 0Eh; unsigned int
0x14000db7b  mov     qword ptr [rsp+100h+Priority], rax; unsigned int *
0x14000db80  lea     r8, [rbp+57h+var_60]; void *
0x14000db84  lea     rax, [rbp+57h+var_B0]
0x14000db88  mov     edx, edi; unsigned int
0x14000db8a  lea     rcx, [rbp+57h+var_B8]; struct _MDL **
0x14000db8e  mov     [rsp+100h+Irp], rax; unsigned int *
0x14000db93  call    ?Dot11CopyMdlToBuffer@@YAHPEAPEAU_MDL@@KPEAXKPEAK2@Z; Dot11CopyMdlToBuffer(_MDL * *,ulong,void *,ulong,ulong *,ulong *)
0x14000db98  mov     edi, eax
0x14000db9a  test    eax, eax
0x14000db9c  jnz     loc_14000DA8F
0x14000dba2  cmp     [rbp+57h+var_C0], 0Eh
0x14000dba6  jnz     loc_14000DA8A
0x14000dbac  mov     r12, [rbp+57h+var_B8]
0x14000dbb0  lea     rcx, [rbp+57h+var_60]
0x14000dbb4  mov     r8d, [rbp+57h+var_B0]
0x14000dbb8  jmp     loc_14000DAA0
0x14000dbbd  mov     rcx, rdi; MemoryDescriptorList
0x14000dbc0  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14000dbc7  nop     dword ptr [rax+rax+00h]
0x14000dbcc  mov     rax, [r12]
0x14000dbd0  xor     r8d, r8d; DataOffset
0x14000dbd3  mov     r9d, [rbp+57h+var_A8]
0x14000dbd7  mov     rdx, rdi; MdlChain
0x14000dbda  mov     [rdi], rax
0x14000dbdd  add     r9d, 0FFFFFFF2h; DataLength
0x14000dbe1  mov     rcx, [rbx+38h]; PoolHandle
0x14000dbe5  call    cs:__imp_NdisAllocateNetBuffer
0x14000dbec  nop     dword ptr [rax+rax+00h]
0x14000dbf1  mov     r9, rax
0x14000dbf4  test    rax, rax
0x14000dbf7  jnz     short loc_14000DC16
0x14000dbf9  mov     rcx, rdi; Mdl
0x14000dbfc  call    cs:__imp_IoFreeMdl
0x14000dc03  nop     dword ptr [rax+rax+00h]
0x14000dc08  mov     r13, [rbp+57h+var_B8]
0x14000dc0c  mov     edi, 0C000009Ah
0x14000dc11  jmp     loc_14000D9F2
0x14000dc16  mov     qword ptr [rax], 0
0x14000dc1d  mov     rdx, [rsi+10h]
0x14000dc21  movzx   ecx, word ptr [rdx+0Ah]
0x14000dc25  mov     r8, [rcx+rdx+38h]
0x14000dc2a  lea     rax, [r8+18h]
0x14000dc2e  mov     [rcx+rdx+38h], rax
0x14000dc33  lea     rax, Dot11PrepareEthernetPayloadPacketComplete
0x14000dc3a  mov     [r8], rax
0x14000dc3d  mov     [r8+8], rbx
  ... truncated ...
```
