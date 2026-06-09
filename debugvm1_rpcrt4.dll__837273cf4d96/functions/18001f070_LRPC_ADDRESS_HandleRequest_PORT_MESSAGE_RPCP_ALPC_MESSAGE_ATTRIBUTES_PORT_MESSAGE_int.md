# LRPC_ADDRESS::HandleRequest(_PORT_MESSAGE *,RPCP_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *,int)

- ea: `0x18001f070`
- end: `0x18001f95d`
- name: `?HandleRequest@LRPC_ADDRESS@@AEAAXPEAU_PORT_MESSAGE@@PEAVRPCP_ALPC_MESSAGE_ATTRIBUTES@@0H@Z`
- size: `2285`
- prototype: `void __usercall(LRPC_ADDRESS *__hidden this@<rcx>, struct _PORT_MESSAGE *@<rdx>, struct RPCP_ALPC_MESSAGE_ATTRIBUTES *@<r8>, struct _PORT_MESSAGE *@<r9>, int)`
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001f970`

## callees

- `0x180016bfc`
- `0x180017ec0`
- `0x180018abc`
- `0x180018f60`
- `0x180018fb4`
- `0x1800190e4`
- `0x180019300`
- `0x1800193a8`
- `0x180019720`
- `0x18001a2f0`
- `0x18001a4f0`
- `0x18001b00c`
- `0x18001f070`
- `0x1800206a0`
- `0x180021e70`
- `0x180023ca0`
- `0x180025130`
- `0x180026ca0`
- `0x180080dd0`
- `0x1800951bc`
- `0x18009d7f0`
- `0x18009d84c`
- `0x1800a4e4c`
- `0x1800ca031`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18001f6df`
- `ntdll!EtwEventActivityIdControl` at `0x18001f6df`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f73b`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f76a`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f73b`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f76a`
- `ntdll!RtlEnterCriticalSection` at `0x18001f6fe`
- `ntdll!RtlEnterCriticalSection` at `0x18001f6fe`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18001f232`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18001f232`

## pseudocode

```c
void __fastcall LRPC_ADDRESS::HandleRequest(
        LRPC_ADDRESS *this,
        struct _PORT_MESSAGE *a2,
        struct RPCP_ALPC_MESSAGE_ATTRIBUTES *a3,
        struct _PORT_MESSAGE *a4,
        int a5)
{
  int v7; // r8d
  int v9; // r10d
  __int64 v10; // rdx
  RPCP_ALPC_HANDLE_ATTR *v11; // rsi
  unsigned __int64 v12; // rcx
  __int64 v14; // r15
  __int64 v15; // r12
  size_t v16; // r8
  char *v17; // r13
  _QWORD *v18; // r14
  signed __int64 v19; // rbx
  int DoNotUseThisField_low; // eax
  signed __int64 v21; // rdx
  PSLIST_ENTRY v22; // rax
  PSLIST_ENTRY v23; // rax
  int v24; // r14d
  int v25; // r14d
  int v26; // r15d
  BOOL v27; // esi
  BOOL v28; // r15d
  LRPC_SASSOCIATION *v29; // rbx
  int v30; // eax
  unsigned __int64 v31; // rcx
  BCACHE *v32; // rcx
  LRPC_SCALL *v33; // rax
  CALL *v34; // rcx
  _BYTE *p_DoNotUseThisField; // r13
  int v36; // ecx
  int v37; // r13d
  struct _PORT_MESSAGE *v38; // r12
  int v39; // eax
  void *v40; // rdx
  LRPC_ADDRESS *v41; // r8
  unsigned int HeaderSize; // eax
  BCACHE *v43; // rcx
  struct _SLIST_ENTRY *v44; // rax
  struct _SLIST_ENTRY *v45; // r14
  RPC_STATUS v46; // eax
  GUID *v47; // rdx
  struct _RTL_CRITICAL_SECTION *v48; // r14
  __int64 v49; // r15
  _QWORD *v50; // rcx
  LRPC_SCALL *v51; // rax
  int v52; // [rsp+40h] [rbp-98h] BYREF
  struct _PORT_MESSAGE *v53; // [rsp+48h] [rbp-90h]
  size_t Size; // [rsp+50h] [rbp-88h]
  _QWORD *v55; // [rsp+58h] [rbp-80h]
  CALL *v56; // [rsp+60h] [rbp-78h]
  __int64 v57; // [rsp+68h] [rbp-70h] BYREF
  ULONG Length; // [rsp+70h] [rbp-68h]
  int v59; // [rsp+74h] [rbp-64h]
  SIZE_T ClientViewSize; // [rsp+78h] [rbp-60h]

  v7 = *(_DWORD *)a3;
  v9 = *((_DWORD *)a3 + 1);
  v10 = (v7 >> 31) & 0x18;
  v11 = 0;
  v12 = (v7 & 0x40000000 | 0x10000000uLL) >> 25;
  v14 = *(_QWORD *)((char *)a3 + v10 + v12);
  if ( (v9 & 0x10000000) != 0 )
    v11 = (struct RPCP_ALPC_MESSAGE_ATTRIBUTES *)((char *)a3 + v10 + (HIBYTE(v7) & 0x20) + v12);
  if ( (v9 & 0x40000000) == 0 )
  {
    v15 = 0;
    if ( a2->u1.s1.TotalLength >= 0x68u )
    {
      v16 = 0;
      Size = 0;
      goto LABEL_6;
    }
    goto LABEL_29;
  }
  HeaderSize = RpcpAlpcpGetHeaderSize(v7 & 0x80000000);
  v15 = *(_QWORD *)((char *)a3 + HeaderSize + 16);
  if ( a2->u1.s1.TotalLength < 0x70u
    || (v16 = *(_QWORD *)&a2[2].MessageId, Size = v16, *(_QWORD *)((char *)a3 + HeaderSize + 24) < v16) )
  {
LABEL_29:
    v25 = 1728;
    v26 = 1;
    goto LABEL_30;
  }
  if ( (*(_DWORD *)((_BYTE *)a3 + HeaderSize) & 0x40000) == 0 )
  {
    v44 = BCACHE::Allocate(v43, v16);
    v45 = v44;
    if ( !v44 )
    {
      v25 = 14;
      if ( (LOBYTE(a2[1].DoNotUseThisField) & 2) != 0 )
        v26 = LRPC_SASSOCIATION::CFCallDispatchFailure((LRPC_SASSOCIATION *)v14, (struct _LRPC_REQUEST_MESSAGE *)a2);
      else
        v26 = 0;
LABEL_30:
      if ( v11 )
        RPCP_ALPC_HANDLE_ATTR::Cleanup(v11);
      v27 = v26 == 0;
      v28 = v15 != 0;
      v29 = *(LRPC_SASSOCIATION **)((char *)a3
                                  + ((*(int *)a3 >> 31) & 0x18)
                                  + ((*(_DWORD *)a3 & 0x40000000 | 0x10000000uLL) >> 25));
      SetFaultPacket((struct _LRPC_FAULT_MESSAGE *)a2, v25, v27, a5);
      v30 = LRPC_ADDRESS::AlpcSend(this, a2, v28, 0, 0, 0, 0);
      if ( v30 < 0
        && (*(unsigned int (__fastcall **)(LRPC_ADDRESS *, _QWORD))(*(_QWORD *)this + 184LL))(this, (unsigned int)v30) == 14 )
      {
        SetCommonFaultFields((struct _LRPC_FAULT_MESSAGE *)a2, v25, 0, v27);
        LRPC_ADDRESS::AlpcSend(this, a2, v28, 0, 0, 0, 0);
      }
      LRPC_SASSOCIATION::MessageReceived(v29);
      v31 = *((_QWORD *)this + 37);
      if ( v31 && (unsigned __int64)a2 > v31 && (unsigned __int64)a2 < v31 + *((unsigned int *)this + 76) )
        LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(this, a2);
      else
        FreeEmergencyOrNormalMessage(a2);
      if ( a4 )
        goto LABEL_36;
      return;
    }
    memcpy_0(v44, (const void *)v15, Size);
    LRPC_ADDRESS::AlpcFreeView(this, (void *)v15);
    v9 = *((_DWORD *)a3 + 1);
    v16 = Size;
    v15 = (unsigned __int64)v45 | 1;
  }
LABEL_6:
  if ( (v9 & 0x8000000) != 0 )
    v17 = (char *)a3
        + (HIBYTE(*(_DWORD *)a3) & 0x20)
        + ((*(_DWORD *)a3 & 0x40000000 | 0x10000000uLL) >> 25)
        + ((*(int *)a3 >> 31) & 0x18)
        + ((*(_DWORD *)a3 & 0x10000000) != 0 ? 0x18 : 0);
  else
    v17 = 0;
  if ( (v9 & 0x2000000) != 0 )
  {
    v16 = Size;
    v18 = (_QWORD *)((char *)a3
                   + ((*(_DWORD *)a3 & 0x10000000) != 0 ? 0x18 : 0)
                   + ((*(_DWORD *)a3 >> 23) & 8)
                   + (HIBYTE(*(_DWORD *)a3) & 0x20)
                   + ((*(_DWORD *)a3 & 0x40000000 | 0x10000000uLL) >> 25)
                   + ((*(int *)a3 >> 31) & 0x18)
                   + ((*(_DWORD *)a3 & 0x8000000) != 0 ? 0x18 : 0));
  }
  else
  {
    v18 = 0;
  }
  v19 = 0;
  v55 = v18;
  if ( !a4 )
  {
    v53 = a2;
    v24 = 14;
    goto LABEL_51;
  }
  *(_OWORD *)&a4->u1.s1.DataLength = *(_OWORD *)&a2->u1.s1.DataLength;
  *(union _PORT_MESSAGE::$C6BC508B531A81D74C33985719C23F49 *)((char *)&a4->8 + 8) = *(union _PORT_MESSAGE::$C6BC508B531A81D74C33985719C23F49 *)((char *)&a2->8 + 8);
  a4->ClientViewSize = a2->ClientViewSize;
  DoNotUseThisField_low = LODWORD(a2[1].DoNotUseThisField);
  if ( (DoNotUseThisField_low & 0x40) == 0 )
  {
    v21 = *(_QWORD *)(v14 + 400);
    LODWORD(v53) = HIDWORD(a2[1].DoNotUseThisField);
    if ( v21 && v21 == _InterlockedCompareExchange64((volatile signed __int64 *)(v14 + 400), 0, v21) )
    {
      v19 = v21;
LABEL_17:
      *(_DWORD *)(v19 + 532) = (_DWORD)v53;
      *(_QWORD *)(v19 + 24) = 0;
      *(_QWORD *)(v19 + 40) = 0;
      *(_QWORD *)(v19 + 312) = 0;
      *(_QWORD *)(v19 + 592) = 0;
      REFERENCED_OBJECT::SingleThreadedAddReference((REFERENCED_OBJECT *)v19);
      if ( dword_1800F9624 )
      {
        v46 = UuidCreate((UUID *)(v19 + 208));
        v47 = (GUID *)(v19 + 208);
        if ( v46 )
          *v47 = g_NullActivityId;
        EtwEventActivityIdControl(2, v47);
      }
      else
      {
        *(GUID *)(v19 + 208) = g_NullActivityId;
      }
LABEL_19:
      if ( v17 )
      {
        *(_OWORD *)(v19 + 624) = *(_OWORD *)v17;
        *(_QWORD *)(v19 + 640) = *((_QWORD *)v17 + 2);
        _InterlockedOr((volatile signed __int32 *)(v19 + 232), 0x8000u);
      }
      else
      {
        _InterlockedAnd((volatile signed __int32 *)(v19 + 232), 0xFFFF7FFF);
      }
      if ( v18 )
      {
        *(_QWORD *)(v19 + 648) = *v18;
        _InterlockedOr((volatile signed __int32 *)(v19 + 232), 0x10000u);
      }
      else
      {
        _InterlockedAnd((volatile signed __int32 *)(v19 + 232), 0xFFFEFFFF);
      }
      v24 = RpcpConvertToLongRunning();
      if ( v24 )
      {
        v53 = a4;
      }
      else
      {
        if ( (*(_DWORD *)(v19 + 232) & 0x400) != 0 )
        {
          if ( !*(_DWORD *)(v14 + 200) )
          {
            *(_DWORD *)(v19 + 232) &= ~0x400u;
LABEL_27:
            LRPC_SCALL::HandleRequest((LRPC_SCALL *)v19, a2, a4, v15, Size, v11);
            return;
          }
        }
        else
        {
          v48 = (struct _RTL_CRITICAL_SECTION *)(v14 + 112);
          RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v14 + 112));
          if ( !*(_DWORD *)(v14 + 200) )
          {
            v49 = v14 + 248;
            v50 = *(_QWORD **)(v49 + 8);
            if ( *v50 != v49 )
              __fastfail(3u);
            *(_QWORD *)(v19 + 552) = v50;
            *(_QWORD *)(v19 + 544) = v49;
            *v50 = v19 + 544;
            *(_QWORD *)(v49 + 8) = v19 + 544;
            RtlLeaveCriticalSection(v48);
            goto LABEL_27;
          }
          RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v14 + 112));
        }
        v24 = 1727;
        v53 = a4;
      }
LABEL_51:
      p_DoNotUseThisField = (_BYTE *)&a2[1].DoNotUseThisField;
      if ( !v11 )
        goto LABEL_53;
      goto LABEL_52;
    }
    v22 = InterlockedPopEntrySList((PSLIST_HEADER)(v14 + 416));
    if ( v22 )
    {
      v23 = v22 - 37;
      if ( v23 )
      {
        v19 = (signed __int64)v23;
        goto LABEL_17;
      }
    }
    v52 = 0;
    if ( gfRPCVerifierEnabled )
    {
      v51 = (LRPC_SCALL *)AllocWrapper(0x290u);
      v56 = v51;
      if ( v51 )
      {
        LRPC_SCALL::LRPC_SCALL(v51, &v52, (struct LRPC_SASSOCIATION *)v14, (unsigned int)v53);
        v34 = v56;
        *(_QWORD *)v56 = &LRPC_SCALL_AVRF::`vftable';
LABEL_40:
        v24 = v52;
        if ( v52 )
        {
          (*(void (__fastcall **)(CALL *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 1);
        }
        else
        {
          v19 = (signed __int64)v34;
          CALL::CreateAndSetActivityId(v34);
        }
        goto LABEL_42;
      }
    }
    else
    {
      v33 = (LRPC_SCALL *)AllocWrapper(0x290u);
      if ( v33 )
      {
        v34 = LRPC_SCALL::LRPC_SCALL(v33, &v52, (struct LRPC_SASSOCIATION *)v14, (unsigned int)v53);
        if ( v34 )
          goto LABEL_40;
      }
    }
    v24 = 14;
LABEL_42:
    if ( v24 )
    {
      v53 = a4;
      goto LABEL_51;
    }
    v18 = v55;
    goto LABEL_19;
  }
  if ( (DoNotUseThisField_low & 2) != 0 )
  {
    v24 = 1728;
    v53 = a4;
    goto LABEL_51;
  }
  if ( !v11 )
  {
    LRPC_SASSOCIATION::HandlePipeChunk((LRPC_SASSOCIATION *)v14, a2, a4, (void *)v15, v16, a5);
    return;
  }
  v24 = 1728;
  v53 = a4;
  p_DoNotUseThisField = (_BYTE *)&a2[1].DoNotUseThisField;
LABEL_52:
  RPCP_ALPC_HANDLE_ATTR::Cleanup(v11);
LABEL_53:
  if ( (*p_DoNotUseThisField & 2) != 0 )
  {
    Length = a2[2].u1.Length;
    ClientViewSize = a2[1].ClientViewSize;
    v59 = 256;
    v57 = 1;
    LRPC_SASSOCIATION::ProcessCausalFlowGapBatch((LRPC_SASSOCIATION *)v14, (struct _LRPC_BROKEN_FLOWS_MESSAGE *)&v57);
    v36 = (unsigned __int8)v59;
  }
  else
  {
    v36 = 1;
  }
  v52 = v36;
  if ( v15 )
  {
    if ( (v15 & 1) != 0 )
    {
      v37 = 0;
      LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(*(LRPC_ADDRESS **)(v14 + 56), (void *)(v15 ^ 1));
      v36 = v52;
    }
    else
    {
      v37 = 1;
    }
  }
  else
  {
    v37 = 0;
  }
  v38 = v53;
  Size = *(_QWORD *)(v14 + 56);
  v52 = v36 == 0;
  SetFaultPacket((struct _LRPC_FAULT_MESSAGE *)v53, v24, v52, a5);
  v39 = LRPC_ADDRESS::AlpcSend((LRPC_ADDRESS *)Size, v38, v37, 0, 0, 0, 0);
  if ( v39 < 0
    && (*(unsigned int (__fastcall **)(size_t, _QWORD))(*(_QWORD *)Size + 184LL))(Size, (unsigned int)v39) == 14 )
  {
    SetCommonFaultFields((struct _LRPC_FAULT_MESSAGE *)v38, v24, 0, v52);
    LRPC_ADDRESS::AlpcSend((LRPC_ADDRESS *)Size, v38, v37, 0, 0, 0, 0);
  }
  if ( (unsigned int)LRPC_ADDRESS::IsBufferInCompletionList(*(LRPC_ADDRESS **)(v14 + 56), a2) )
    LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(v41, v40);
  else
    FreeEmergencyOrNormalMessage(a2);
  LRPC_SASSOCIATION::MessageReceived((LRPC_SASSOCIATION *)v14);
  if ( v19 )
    (*(void (__fastcall **)(signed __int64, __int64))(*(_QWORD *)v19 + 8LL))(v19, 1);
  if ( a4 )
LABEL_36:
    BCACHE::Free(v32, a4);
}

```

## disassembly

```asm
0x18001f070  push    rbx
0x18001f072  push    rbp
0x18001f073  push    rsi
0x18001f074  push    rdi
0x18001f075  push    r13
0x18001f077  push    r15
0x18001f079  sub     rsp, 0A8h
0x18001f080  mov     rax, cs:__security_cookie
0x18001f087  xor     rax, rsp
0x18001f08a  mov     [rsp+0D8h+var_58], rax
0x18001f092  mov     r13, rcx
0x18001f095  mov     rbx, r8
0x18001f098  mov     r8d, [r8]
0x18001f09b  mov     rdi, rdx
0x18001f09e  mov     ecx, r8d
0x18001f0a1  movsxd  rdx, r8d
0x18001f0a4  sar     rdx, 3Fh
0x18001f0a8  and     ecx, 40000000h
0x18001f0ae  mov     r10d, [rbx+4]
0x18001f0b2  and     edx, 18h
0x18001f0b5  bts     rcx, 1Ch
0x18001f0ba  xor     esi, esi
0x18001f0bc  shr     rcx, 19h
0x18001f0c0  mov     rbp, r9
0x18001f0c3  lea     rax, [rdx+rbx]
0x18001f0c7  mov     r15, [rax+rcx]
0x18001f0cb  bt      r10d, 1Ch
0x18001f0d0  jnb     short loc_18001F0E5
0x18001f0d2  mov     esi, r8d
0x18001f0d5  shr     rsi, 18h
0x18001f0d9  and     esi, 20h
0x18001f0dc  add     rsi, rdx
0x18001f0df  add     rsi, rbx
0x18001f0e2  add     rsi, rcx
0x18001f0e5  mov     [rsp+0D8h+var_38], r12
0x18001f0ed  mov     [rsp+0D8h+var_40], r14
0x18001f0f5  bt      r10d, 1Eh
0x18001f0fa  jb      loc_18001F633
0x18001f100  xor     r12d, r12d
0x18001f103  cmp     word ptr [rdi+2], 68h ; 'h'
0x18001f108  jb      loc_18001F37B
0x18001f10e  xor     r8d, r8d
0x18001f111  mov     [rsp+0D8h+Size], r8
0x18001f116  bt      r10d, 1Bh
0x18001f11b  jnb     loc_18001F816
0x18001f121  mov     ecx, [rbx]
0x18001f123  mov     eax, ecx
0x18001f125  and     eax, 40000000h
0x18001f12a  movsxd  rdx, ecx
0x18001f12d  bts     rax, 1Ch
0x18001f132  sar     rdx, 3Fh
0x18001f136  shr     rax, 19h
0x18001f13a  and     edx, 18h
0x18001f13d  add     rdx, rax
0x18001f140  mov     eax, ecx
0x18001f142  shr     rax, 18h
0x18001f146  and     ecx, 10000000h
0x18001f14c  and     eax, 20h
0x18001f14f  add     rax, rbx
0x18001f152  neg     ecx
0x18001f154  sbb     r13, r13
0x18001f157  add     rax, rdx
0x18001f15a  and     r13d, 18h
0x18001f15e  add     r13, rax
0x18001f161  bt      r10d, 19h
0x18001f166  jnb     loc_18001F6BB
0x18001f16c  mov     edx, [rbx]
0x18001f16e  mov     eax, edx
0x18001f170  and     eax, 40000000h
0x18001f175  movsxd  r8, edx
0x18001f178  bts     rax, 1Ch
0x18001f17d  sar     r8, 3Fh
0x18001f181  shr     rax, 19h
0x18001f185  and     r8d, 18h
0x18001f189  add     r8, rax
0x18001f18c  mov     eax, edx
0x18001f18e  shr     rax, 18h
0x18001f192  and     eax, 20h
0x18001f195  add     r8, rax
0x18001f198  mov     eax, edx
0x18001f19a  shr     rax, 17h
0x18001f19e  and     eax, 8
0x18001f1a1  add     r8, rax
0x18001f1a4  mov     eax, edx
0x18001f1a6  and     eax, 10000000h
0x18001f1ab  neg     eax
0x18001f1ad  sbb     rcx, rcx
0x18001f1b0  and     edx, 8000000h
0x18001f1b6  and     ecx, 18h
0x18001f1b9  add     rcx, rbx
0x18001f1bc  neg     edx
0x18001f1be  sbb     r14, r14
0x18001f1c1  add     rcx, r8
0x18001f1c4  mov     r8, [rsp+0D8h+Size]
0x18001f1c9  and     r14d, 18h
0x18001f1cd  add     r14, rcx
0x18001f1d0  xor     ebx, ebx
0x18001f1d2  mov     [rsp+0D8h+var_80], r14
0x18001f1d7  test    rbp, rbp
0x18001f1da  jz      loc_18001F50F
0x18001f1e0  movups  xmm0, xmmword ptr [rdi]
0x18001f1e3  movups  xmmword ptr [rbp+0], xmm0
0x18001f1e7  movups  xmm1, xmmword ptr [rdi+10h]
0x18001f1eb  movups  xmmword ptr [rbp+10h], xmm1
0x18001f1ef  movsd   xmm0, qword ptr [rdi+20h]
0x18001f1f4  movsd   qword ptr [rbp+20h], xmm0
0x18001f1f9  mov     eax, [rdi+30h]
0x18001f1fc  test    al, 40h
0x18001f1fe  jnz     loc_18001F4AC
0x18001f204  mov     rdx, [r15+190h]
0x18001f20b  mov     eax, [rdi+34h]
0x18001f20e  mov     dword ptr [rsp+0D8h+var_90], eax
0x18001f212  test    rdx, rdx
0x18001f215  jz      short loc_18001F22B
0x18001f217  xor     ecx, ecx
0x18001f219  mov     rax, rdx
0x18001f21c  lock cmpxchg [r15+190h], rcx
0x18001f225  jz      loc_18001F8B6
0x18001f22b  lea     rcx, [r15+1A0h]; ListHead
0x18001f232  call    cs:__imp_InterlockedPopEntrySList
0x18001f238  test    rax, rax
0x18001f23b  jz      loc_18001F43F
0x18001f241  add     rax, 0FFFFFFFFFFFFFDB0h
0x18001f247  jz      loc_18001F43F
0x18001f24d  mov     rbx, rax
0x18001f250  mov     r9d, dword ptr [rsp+0D8h+var_90]
0x18001f255  mov     rcx, rbx; this
0x18001f258  mov     [rbx+214h], r9d
0x18001f25f  mov     qword ptr [rbx+18h], 0
0x18001f267  mov     qword ptr [rbx+28h], 0
0x18001f26f  mov     qword ptr [rbx+138h], 0
0x18001f27a  mov     qword ptr [rbx+250h], 0
0x18001f285  nop
0x18001f286  call    ?SingleThreadedAddReference@REFERENCED_OBJECT@@QEAAXXZ; REFERENCED_OBJECT::SingleThreadedAddReference(void)
0x18001f28b  cmp     cs:dword_1800F9624, 0
0x18001f292  jnz     loc_18001F6C3
0x18001f298  movups  xmm0, xmmword ptr cs:?g_NullActivityId@@3U_GUID@@B.Data1; _GUID const g_NullActivityId ...
0x18001f29f  movups  xmmword ptr [rbx+0D0h], xmm0
0x18001f2a6  test    r13, r13
0x18001f2a9  jz      loc_18001F7D8
0x18001f2af  movups  xmm0, xmmword ptr [r13+0]
0x18001f2b4  movups  xmmword ptr [rbx+270h], xmm0
0x18001f2bb  movsd   xmm1, qword ptr [r13+10h]
0x18001f2c1  movsd   qword ptr [rbx+280h], xmm1
0x18001f2c9  lock or dword ptr [rbx+0E8h], 8000h
0x18001f2d4  test    r14, r14
0x18001f2d7  jz      loc_18001F623
0x18001f2dd  mov     rax, [r14]
0x18001f2e0  mov     [rbx+288h], rax
0x18001f2e7  lock or dword ptr [rbx+0E8h], 10000h
0x18001f2f2  call    ?RpcpConvertToLongRunning@@YAJXZ; RpcpConvertToLongRunning(void)
0x18001f2f7  mov     r14d, eax
0x18001f2fa  test    eax, eax
0x18001f2fc  jnz     loc_18001F80C
0x18001f302  mov     eax, [rbx+0E8h]
0x18001f308  bt      eax, 0Ah
0x18001f30c  jnb     loc_18001F6F7
0x18001f312  mov     eax, [r15+0C8h]
0x18001f319  test    eax, eax
0x18001f31b  jnz     loc_18001F770
0x18001f321  and     dword ptr [rbx+0E8h], 0FFFFFBFFh
0x18001f32b  mov     rax, [rsp+0D8h+Size]
0x18001f330  mov     r9, r12; void *
0x18001f333  mov     [rsp+0D8h+var_B0], rsi; struct RPCP_ALPC_HANDLE_ATTR *
0x18001f338  mov     r8, rbp; struct _PORT_MESSAGE *
0x18001f33b  mov     rdx, rdi; struct _PORT_MESSAGE *
0x18001f33e  mov     [rsp+0D8h+var_B8], rax; unsigned __int64
0x18001f343  mov     rcx, rbx; this
0x18001f346  call    ?HandleRequest@LRPC_SCALL@@QEAAXPEAU_PORT_MESSAGE@@0PEAX_KPEAVRPCP_ALPC_HANDLE_ATTR@@@Z; LRPC_SCALL::HandleRequest(_PORT_MESSAGE *,_PORT_MESSAGE *,void *,unsigned __int64,RPCP_ALPC_HANDLE_ATTR *)
0x18001f34b  mov     r14, [rsp+0D8h+var_40]
0x18001f353  mov     r12, [rsp+0D8h+var_38]
0x18001f35b  mov     rcx, [rsp+0D8h+var_58]
0x18001f363  xor     rcx, rsp; StackCookie
0x18001f366  call    __security_check_cookie
0x18001f36b  add     rsp, 0A8h
0x18001f372  pop     r15
0x18001f374  pop     r13
0x18001f376  pop     rdi
0x18001f377  pop     rsi
0x18001f378  pop     rbp
0x18001f379  pop     rbx
0x18001f37a  retn
0x18001f37b  mov     r14d, 6C0h
0x18001f381  mov     r15d, 1
0x18001f387  test    rsi, rsi
0x18001f38a  jnz     loc_18001F857
0x18001f390  movsxd  rcx, dword ptr [rbx]
0x18001f393  xor     esi, esi
0x18001f395  mov     r9d, [rsp+0D8h+arg_20]; int
0x18001f39d  mov     rax, rcx
0x18001f3a0  test    r15d, r15d
0x18001f3a3  mov     edx, r14d; int
0x18001f3a6  setz    sil
0x18001f3aa  xor     r15d, r15d
0x18001f3ad  test    r12, r12
0x18001f3b0  mov     r8d, esi; int
0x18001f3b3  setnz   r15b
0x18001f3b7  and     ecx, 40000000h
0x18001f3bd  sar     rax, 3Fh
0x18001f3c1  bts     rcx, 1Ch
0x18001f3c6  shr     rcx, 19h
0x18001f3ca  and     eax, 18h
0x18001f3cd  add     rax, rbx
0x18001f3d0  mov     rbx, [rcx+rax]
0x18001f3d4  mov     rcx, rdi; struct _LRPC_FAULT_MESSAGE *
0x18001f3d7  call    ?SetFaultPacket@@YAXPEAU_LRPC_FAULT_MESSAGE@@JHH@Z; SetFaultPacket(_LRPC_FAULT_MESSAGE *,long,int,int)
0x18001f3dc  xor     r12d, r12d
0x18001f3df  xor     r9d, r9d; void *
0x18001f3e2  mov     [rsp+0D8h+var_A8], r12; struct LRPC_SYSTEM_HANDLE_DATA *
0x18001f3e7  mov     r8d, r15d; int
0x18001f3ea  mov     [rsp+0D8h+var_B0], r12; unsigned __int64
0x18001f3ef  mov     rdx, rdi; struct _PORT_MESSAGE *
0x18001f3f2  mov     rcx, r13; this
0x18001f3f5  mov     [rsp+0D8h+var_B8], r12; void *
0x18001f3fa  call    ?AlpcSend@LRPC_ADDRESS@@QEAAJPEAU_PORT_MESSAGE@@HPEAX1_KPEAVLRPC_SYSTEM_HANDLE_DATA@@@Z; LRPC_ADDRESS::AlpcSend(_PORT_MESSAGE *,int,void *,void *,unsigned __int64,LRPC_SYSTEM_HANDLE_DATA *)
0x18001f3ff  mov     edx, eax
0x18001f401  test    eax, eax
0x18001f403  js      loc_18001F864
0x18001f409  mov     rcx, rbx; this
0x18001f40c  call    ?MessageReceived@LRPC_SASSOCIATION@@QEAAXXZ; LRPC_SASSOCIATION::MessageReceived(void)
0x18001f411  mov     rcx, [r13+128h]
0x18001f418  test    rcx, rcx
0x18001f41b  jnz     loc_18001F4E3
0x18001f421  mov     rcx, rdi; void *
0x18001f424  call    ?FreeEmergencyOrNormalMessage@@YAXPEAX@Z; FreeEmergencyOrNormalMessage(void *)
0x18001f429  test    rbp, rbp
0x18001f42c  jz      loc_18001F34B
0x18001f432  mov     rdx, rbp; void *
0x18001f435  call    ?Free@BCACHE@@QEAAXPEAX@Z; BCACHE::Free(void *)
0x18001f43a  jmp     loc_18001F34B
0x18001f43f  cmp     cs:?gfRPCVerifierEnabled@@3HA, ebx; int gfRPCVerifierEnabled
0x18001f445  mov     ecx, 290h; dwBytes
0x18001f44a  mov     [rsp+0D8h+var_98], ebx
0x18001f44e  jnz     loc_18001F78A
0x18001f454  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18001f459  test    rax, rax
0x18001f45c  jz      loc_18001F746
0x18001f462  mov     r9d, dword ptr [rsp+0D8h+var_90]; unsigned int
0x18001f467  lea     rdx, [rsp+0D8h+var_98]; int *
0x18001f46c  mov     r8, r15; struct LRPC_SASSOCIATION *
0x18001f46f  mov     rcx, rax; this
0x18001f472  call    ??0LRPC_SCALL@@QEAA@PEAJPEAVLRPC_SASSOCIATION@@K@Z; LRPC_SCALL::LRPC_SCALL(long *,LRPC_SASSOCIATION *,ulong)
0x18001f477  mov     rcx, rax; this
0x18001f47a  test    rax, rax
0x18001f47d  jz      loc_18001F746
0x18001f483  mov     r14d, [rsp+0D8h+var_98]
0x18001f488  test    r14d, r14d
0x18001f48b  jnz     loc_18001F7C2
0x18001f491  mov     rbx, rcx
0x18001f494  call    ?CreateAndSetActivityId@CALL@@QEAAXXZ; CALL::CreateAndSetActivityId(void)
0x18001f499  test    r14d, r14d
0x18001f49c  jnz     loc_18001F780
0x18001f4a2  mov     r14, [rsp+0D8h+var_80]
0x18001f4a7  jmp     loc_18001F2A6
0x18001f4ac  test    al, 2
0x18001f4ae  jnz     loc_18001F7E8
0x18001f4b4  test    rsi, rsi
0x18001f4b7  jnz     loc_18001F7F8
0x18001f4bd  mov     eax, [rsp+0D8h+arg_20]
0x18001f4c4  mov     r9, r12; void *
0x18001f4c7  mov     dword ptr [rsp+0D8h+var_B0], eax; int
0x18001f4cb  mov     rdx, rdi; struct _PORT_MESSAGE *
0x18001f4ce  mov     [rsp+0D8h+var_B8], r8; unsigned __int64
0x18001f4d3  mov     rcx, r15; this
0x18001f4d6  mov     r8, rbp; struct _PORT_MESSAGE *
0x18001f4d9  call    ?HandlePipeChunk@LRPC_SASSOCIATION@@AEAAXPEAU_LRPC_REQUEST_MESSAGE@@PEAU_PORT_MESSAGE@@PEAX_KH@Z; LRPC_SASSOCIATION::HandlePipeChunk(_LRPC_REQUEST_MESSAGE *,_PORT_MESSAGE *,void *,unsigned __int64,int)
0x18001f4de  jmp     loc_18001F34B
0x18001f4e3  cmp     rdi, rcx
0x18001f4e6  jbe     loc_18001F421
0x18001f4ec  mov     eax, [r13+130h]
0x18001f4f3  add     rax, rcx
0x18001f4f6  cmp     rdi, rax
0x18001f4f9  jnb     loc_18001F421
0x18001f4ff  mov     rdx, rdi; void *
0x18001f502  mov     rcx, r13; this
0x18001f505  call    ?RpcFreeLrpcAddressBuffer@LRPC_ADDRESS@@QEAAXPEAX@Z; LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(void *)
0x18001f50a  jmp     loc_18001F429
0x18001f50f  mov     [rsp+0D8h+var_90], rdi
0x18001f514  mov     r14d, 0Eh
0x18001f51a  lea     r13, [rdi+30h]
0x18001f51e  test    rsi, rsi
0x18001f521  jz      short loc_18001F52B
0x18001f523  mov     rcx, rsi; this
0x18001f526  call    ?Cleanup@RPCP_ALPC_HANDLE_ATTR@@QEAAXXZ; RPCP_ALPC_HANDLE_ATTR::Cleanup(void)
0x18001f52b  test    byte ptr [r13+0], 2
0x18001f530  mov     esi, 1
0x18001f535  jz      loc_18001F760
0x18001f53b  mov     eax, [rdi+50h]
0x18001f53e  lea     rdx, [rsp+0D8h+var_70]; struct _LRPC_BROKEN_FLOWS_MESSAGE *
0x18001f543  mov     [rsp+0D8h+var_68], eax
0x18001f547  mov     rcx, r15; this
0x18001f54a  mov     rax, [rdi+48h]
0x18001f54e  mov     [rsp+0D8h+var_60], rax
0x18001f553  mov     [rsp+0D8h+var_64], 100h
0x18001f55b  mov     [rsp+0D8h+var_70], 1
0x18001f564  call    ?ProcessCausalFlowGapBatch@LRPC_SASSOCIATION@@QEAAXPEAU_LRPC_BROKEN_FLOWS_MESSAGE@@@Z; LRPC_SASSOCIATION::ProcessCausalFlowGapBatch(_LRPC_BROKEN_FLOWS_MESSAGE *)
0x18001f569  movzx   ecx, byte ptr [rsp+0D8h+var_64]
0x18001f56e  mov     [rsp+0D8h+var_98], ecx
0x18001f572  test    r12, r12
0x18001f575  jnz     loc_18001F81E
  ... truncated ...
```
