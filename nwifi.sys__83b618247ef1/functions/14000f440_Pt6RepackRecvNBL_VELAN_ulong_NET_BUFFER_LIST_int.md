# Pt6RepackRecvNBL(_VELAN *,ulong,_NET_BUFFER_LIST *,int)

- ea: `0x14000f440`
- end: `0x14000f8d9`
- name: `?Pt6RepackRecvNBL@@YAPEAU_NET_BUFFER_LIST@@PEAU_VELAN@@KPEAU1@H@Z`
- size: `1177`
- prototype: `struct _NET_BUFFER_LIST *(struct _VELAN *, unsigned int, struct _NET_BUFFER_LIST *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f0c0`

## callees

- `0x14000d22c`
- `0x14000f440`
- `0x14000f8e0`
- `0x140010228`
- `0x140013730`
- `0x1400137a0`
- `0x140019314`
- `0x1400208f0`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000f5b5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000f5b5`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x14000f6ef`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x14000f734`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x14000f6ef`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x14000f734`
- `NDIS!NdisFReturnNetBufferLists` at `0x14000f88b`
- `NDIS!NdisFReturnNetBufferLists` at `0x14000f88b`
- `NDIS!NdisAllocateNetBufferList` at `0x14000f587`
- `NDIS!NdisAllocateNetBufferList` at `0x14000f587`
- `NDIS!NdisFreeNetBufferList` at `0x14000f5cf`
- `NDIS!NdisFreeNetBufferList` at `0x14000f5cf`
- `NDIS!NdisReleaseRWLock` at `0x14000f850`
- `NDIS!NdisReleaseRWLock` at `0x14000f850`
- `NDIS!NdisAcquireRWLockRead` at `0x14000f4a4`
- `NDIS!NdisAcquireRWLockRead` at `0x14000f4a4`

## pseudocode

```c
struct _NET_BUFFER_LIST *__fastcall Pt6RepackRecvNBL(struct _VELAN *a1, int a2, struct _NET_BUFFER_LIST *a3, int a4)
{
  struct _NDIS_RW_LOCK_EX *pRWLock; // rcx
  int v7; // r13d
  PNET_BUFFER_LIST NetBufferList; // r14
  struct _NET_BUFFER_LIST *Alignment; // rbx
  struct _NET_BUFFER_LIST *v10; // r15
  struct _NET_BUFFER_LIST *v11; // rsi
  unsigned int v12; // r12d
  _NET_BUFFER *FirstNetBuffer; // rax
  _MDL *CurrentMdl; // rdx
  _WORD *v15; // r8
  const unsigned __int8 *v16; // r12
  _DWORD *v17; // rax
  char *v18; // rbx
  int v19; // eax
  void *v20; // rbx
  unsigned int v21; // r12d
  _NET_BUFFER_LIST_CONTEXT *Context; // rcx
  __int64 v23; // rdx
  _QWORD *v24; // rcx
  struct _ADAPT *v25; // rcx
  unsigned int v26; // r8d
  struct _NET_BUFFER_LIST *v28; // [rsp+30h] [rbp-78h]
  unsigned __int64 v29; // [rsp+38h] [rbp-70h]
  struct _NET_BUFFER_LIST *v30; // [rsp+40h] [rbp-68h] BYREF
  struct _NET_BUFFER_LIST *v31; // [rsp+48h] [rbp-60h]
  _QWORD *p_Alignment; // [rsp+50h] [rbp-58h]
  struct _LOCK_STATE_EX LockState; // [rsp+B0h] [rbp+8h] BYREF
  size_t Size; // [rsp+B8h] [rbp+10h]
  unsigned int v35; // [rsp+C0h] [rbp+18h]
  int v36; // [rsp+C8h] [rbp+20h]

  v36 = a4;
  LODWORD(Size) = a2;
  v30 = 0;
  p_Alignment = 0;
  pRWLock = a1->pRWLock;
  v7 = 0;
  v28 = 0;
  NetBufferList = 0;
  v31 = 0;
  Alignment = 0;
  v35 = 0;
  v10 = 0;
  LockState.OldIrql = 0;
  v11 = 0;
  *(_WORD *)&LockState.LockState = 0;
  v12 = 0;
  NdisAcquireRWLockRead(pRWLock, &LockState, 0);
  while ( a3 )
  {
    FirstNetBuffer = a3->FirstNetBuffer;
    Alignment = (struct _NET_BUFFER_LIST *)a3->Link.Alignment;
    v29 = a3->Link.Alignment;
    if ( !FirstNetBuffer )
      goto LABEL_38;
    CurrentMdl = FirstNetBuffer->CurrentMdl;
    if ( !CurrentMdl )
      goto LABEL_38;
    NetBufferList = 0;
    v15 = (char *)CurrentMdl->MappedSystemVa + FirstNetBuffer->CurrentMdlOffset;
    v30 = 0;
    if ( (((unsigned __int16)*v15 >> 2) & 3) != 0 )
    {
      if ( (((unsigned __int16)*v15 >> 2) & 3) == 1 )
      {
        if ( (unsigned __int8)*v15 >> 4 != 10
          && (unsigned __int8)*v15 >> 4 != 11
          && (unsigned int)((unsigned __int8)*v15 >> 4) - 14 > 1 )
        {
          goto LABEL_10;
        }
      }
      else if ( (((unsigned __int16)*v15 >> 2) & 3) != 2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_591672ea4a6b33fdc9f57e1d50f33c40_Traceguids);
        goto LABEL_10;
      }
    }
    v16 = (const unsigned __int8 *)(v15 + 5);
    if ( v15 != (_WORD *)-10LL )
    {
      NetBufferList = NdisAllocateNetBufferList(a1->hRecvNetBufferListPool, 8u, 0);
      if ( !NetBufferList )
      {
        v7 = -1073741670;
        goto LABEL_21;
      }
      NetBufferList->SourceHandle = a1->hMiniport;
      v17 = ExAllocateFromNPagedLookasideList(&Lookaside);
      if ( v17 )
      {
        v18 = (char *)(v17 + 4);
        *(_QWORD *)v17 = &Lookaside;
        v17[2] = 1634300791;
        memset(v17 + 4, 0, 0x300u);
        *((_QWORD *)v18 + 5) = v18 + 48;
        *(_QWORD *)&NetBufferList->Context->ContextData[NetBufferList->Context->Offset] = v18;
        *(_QWORD *)v18 = a1;
        Dot11AcquireMacState(
          &a1->MacStateTable,
          (const unsigned __int8 (*)[6])v16,
          (struct DOT11_MAC_STATE_ENTRY **)v18 + 1);
        v30 = NetBufferList;
        if ( !v36 )
        {
          a3->Link.Alignment = 0;
          NdisCopyReceiveNetBufferListInfo(NetBufferList, a3);
          v7 = 0;
          v20 = a3->NetBufferListInfo[6];
          NetBufferList->Link.Region = a3->Link.Region;
          goto LABEL_34;
        }
        v19 = Pt6DuplicateOneNBLAndData((__int64)a1, (__int64)a3, (__int64)NetBufferList);
        v7 = v19;
        if ( !v19 )
        {
          NdisCopyReceiveNetBufferListInfo(NetBufferList, a3);
          v20 = (void *)(*(_QWORD *)&NetBufferList->Context->ContextData[NetBufferList->Context->Offset] + 432LL);
          memmove(v20, a3->NetBufferListInfo[6], (unsigned int)Size);
          a3 = 0;
LABEL_34:
          v21 = v35;
          NetBufferList->NetBufferListInfo[6] = v20;
          v12 = v21 + 1;
          Context = NetBufferList->Context;
          v35 = v12;
          v23 = *(_QWORD *)&Context->ContextData[Context->Offset];
          v24 = *(_QWORD **)(v23 + 40);
          *(_QWORD *)(v23 + 40) = v24 + 3;
          *v24 = Pt6RecvNBLComplete;
          v24[1] = a1;
          v24[2] = a3;
          NetBufferList->Link.Alignment = 0;
          if ( v10 )
            *p_Alignment = NetBufferList;
          else
            v10 = NetBufferList;
          Alignment = (struct _NET_BUFFER_LIST *)v29;
          p_Alignment = &NetBufferList->Link.Alignment;
          goto LABEL_44;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_f7be174c5c0c3ddfd0519d9dc4150861_Traceguids, a3, v19);
        }
        Alignment = (struct _NET_BUFFER_LIST *)v29;
        v11 = v28;
      }
      else
      {
        v7 = -1073741670;
        NdisFreeNetBufferList(NetBufferList);
        NetBufferList = 0;
LABEL_21:
        v30 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_f7be174c5c0c3ddfd0519d9dc4150861_Traceguids, a3);
        }
      }
LABEL_38:
      if ( NetBufferList )
      {
        Dot11FreeRecvPacket(&v30);
        NetBufferList = v30;
      }
    }
LABEL_10:
    if ( !v36 )
    {
      if ( v11 )
      {
        v31->Link.Alignment = (unsigned __int64)a3;
      }
      else
      {
        v11 = a3;
        v28 = a3;
      }
      v31 = a3;
    }
    if ( v7 == -1073741670 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_f7be174c5c0c3ddfd0519d9dc4150861_Traceguids);
      }
      v12 = v35;
      break;
    }
    v12 = v35;
LABEL_44:
    v11 = v28;
    a3 = Alignment;
  }
  NdisReleaseRWLock(a1->pRWLock, &LockState);
  if ( !v36 )
  {
    if ( v11 )
    {
      v31->Link.Alignment = (unsigned __int64)Alignment;
LABEL_55:
      NdisFReturnNetBufferLists(a1->pAdapt->hBinding, v11, 0);
    }
    else if ( Alignment )
    {
      v11 = Alignment;
      goto LABEL_55;
    }
  }
  _InterlockedAdd((volatile signed __int32 *)&a1->OutstandingReceives, v12);
  _InterlockedAdd((volatile signed __int32 *)&a1->pAdapt->uOutstandingReceives, v12);
  if ( v7 == -1073741670 && v10 )
  {
    FilterReturnNetBufferLists(v25, v10, v26);
    return 0;
  }
  return v10;
}

```

## disassembly

```asm
0x14000f440  mov     r11, rsp
0x14000f443  mov     [r11+20h], r9d
0x14000f447  mov     dword ptr [rsp+Size], edx
0x14000f44b  push    rbx
0x14000f44c  push    rbp
0x14000f44d  push    rsi
0x14000f44e  push    rdi
0x14000f44f  push    r12
0x14000f451  push    r13
0x14000f453  push    r14
0x14000f455  push    r15
0x14000f457  sub     rsp, 68h
0x14000f45b  xor     eax, eax
0x14000f45d  lea     rdx, [r11+8]; LockState
0x14000f461  mov     rdi, r8
0x14000f464  mov     [r11-68h], rax
0x14000f468  mov     rbp, rcx
0x14000f46b  mov     [rsp+0A8h+var_58], rax
0x14000f470  mov     rcx, [rcx+90h]; Lock
0x14000f477  xor     r8d, r8d; Flags
0x14000f47a  mov     r13d, eax
0x14000f47d  mov     [rsp+0A8h+var_78], rax
0x14000f482  mov     r14d, eax
0x14000f485  mov     [rsp+0A8h+var_60], rax
0x14000f48a  mov     ebx, eax
0x14000f48c  mov     [rsp+0A8h+arg_10], eax
0x14000f493  mov     r15d, eax
0x14000f496  mov     [r11+8], al
0x14000f49a  mov     esi, eax
0x14000f49c  mov     [r11+9], ax
0x14000f4a1  mov     r12d, eax
0x14000f4a4  call    cs:__imp_NdisAcquireRWLockRead
0x14000f4ab  nop     dword ptr [rax+rax+00h]
0x14000f4b0  lea     r9, WPP_GLOBAL_Control
0x14000f4b7  test    rdi, rdi
0x14000f4ba  jz      loc_14000F841
0x14000f4c0  mov     rax, [rdi+8]
0x14000f4c4  mov     rbx, [rdi]
0x14000f4c7  mov     [rsp+0A8h+var_70], rbx
0x14000f4cc  test    rax, rax
0x14000f4cf  jz      loc_14000F7BC
0x14000f4d5  mov     rdx, [rax+8]
0x14000f4d9  test    rdx, rdx
0x14000f4dc  jz      loc_14000F7BC
0x14000f4e2  mov     r8d, [rax+10h]
0x14000f4e6  xor     r14d, r14d
0x14000f4e9  add     r8, [rdx+18h]
0x14000f4ed  mov     [rsp+0A8h+var_68], r14
0x14000f4f2  movzx   ecx, word ptr [r8]
0x14000f4f6  mov     edx, ecx
0x14000f4f8  shr     edx, 2
0x14000f4fb  and     edx, 3
0x14000f4fe  jz      short loc_14000F56F
0x14000f500  sub     edx, 1
0x14000f503  jz      short loc_14000F555
0x14000f505  cmp     edx, 1
0x14000f508  jz      short loc_14000F56F
0x14000f50a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f511  cmp     rcx, r9
0x14000f514  jz      short loc_14000F52A
0x14000f516  mov     rcx, [rcx+18h]
0x14000f51a  lea     edx, [r14+0Fh]
0x14000f51e  lea     r8, WPP_591672ea4a6b33fdc9f57e1d50f33c40_Traceguids
0x14000f525  call    WPP_SF_
0x14000f52a  lea     r12, WPP_GLOBAL_Control
0x14000f531  cmp     [rsp+0A8h+arg_18], 0
0x14000f539  jnz     loc_14000F7ED
0x14000f53f  test    rsi, rsi
0x14000f542  jnz     loc_14000F7E0
0x14000f548  mov     rsi, rdi
0x14000f54b  mov     [rsp+0A8h+var_78], rdi
0x14000f550  jmp     loc_14000F7E8
0x14000f555  shr     ecx, 4
0x14000f558  and     ecx, 0Fh
0x14000f55b  sub     ecx, 0Ah
0x14000f55e  jz      short loc_14000F56F
0x14000f560  sub     ecx, 1
0x14000f563  jz      short loc_14000F56F
0x14000f565  sub     ecx, 3
0x14000f568  jz      short loc_14000F56F
0x14000f56a  cmp     ecx, 1
0x14000f56d  jnz     short loc_14000F52A
0x14000f56f  mov     eax, 0Ah
0x14000f574  lea     r12, [rax+r8]
0x14000f578  test    r12, r12
0x14000f57b  jz      short loc_14000F52A
0x14000f57d  mov     rcx, [rbp+40h]; PoolHandle
0x14000f581  lea     edx, [rax-2]; ContextSize
0x14000f584  xor     r8d, r8d; ContextBackFill
0x14000f587  call    cs:__imp_NdisAllocateNetBufferList
0x14000f58e  nop     dword ptr [rax+rax+00h]
0x14000f593  mov     r14, rax
0x14000f596  test    rax, rax
0x14000f599  jnz     short loc_14000F5A3
0x14000f59b  mov     r13d, 0C000009Ah
0x14000f5a1  jmp     short loc_14000F5DE
0x14000f5a3  mov     rax, [rbp+20h]
0x14000f5a7  lea     r13, Lookaside
0x14000f5ae  mov     rcx, r13; Lookaside
0x14000f5b1  mov     [r14+78h], rax
0x14000f5b5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000f5bc  nop     dword ptr [rax+rax+00h]
0x14000f5c1  test    rax, rax
0x14000f5c4  jnz     short loc_14000F62C
0x14000f5c6  mov     r13d, 0C000009Ah
0x14000f5cc  mov     rcx, r14; NetBufferList
0x14000f5cf  call    cs:__imp_NdisFreeNetBufferList
0x14000f5d6  nop     dword ptr [rax+rax+00h]
0x14000f5db  xor     r14d, r14d
0x14000f5de  mov     [rsp+0A8h+var_68], r14
0x14000f5e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f5ea  lea     r12, WPP_GLOBAL_Control
0x14000f5f1  cmp     rcx, r12
0x14000f5f4  jz      loc_14000F7C3
0x14000f5fa  cmp     byte ptr [rcx+29h], 2
0x14000f5fe  jb      loc_14000F7C3
0x14000f604  mov     eax, [rcx+2Ch]
0x14000f607  test    al, 20h
0x14000f609  jz      loc_14000F7C3
0x14000f60f  mov     rcx, [rcx+18h]
0x14000f613  lea     r8, WPP_f7be174c5c0c3ddfd0519d9dc4150861_Traceguids
0x14000f61a  mov     edx, 0Ah
0x14000f61f  mov     r9, rdi
0x14000f622  call    WPP_SF_q
0x14000f627  jmp     loc_14000F7C3
0x14000f62c  lea     rbx, [rax+10h]
0x14000f630  mov     [rax], r13
0x14000f633  mov     rcx, rbx; void *
0x14000f636  mov     dword ptr [rax+8], 61697377h
0x14000f63d  xor     edx, edx; Val
0x14000f63f  mov     r8d, 300h; Size
0x14000f645  call    memset
0x14000f64a  lea     rax, [rbx+30h]
0x14000f64e  mov     rdx, r12; unsigned __int8 (*)[6]
0x14000f651  mov     [rbx+28h], rax
0x14000f655  lea     r8, [rbx+8]; struct DOT11_MAC_STATE_ENTRY **
0x14000f659  mov     rcx, [r14+10h]
0x14000f65d  movzx   eax, word ptr [rcx+0Ah]
0x14000f661  mov     [rax+rcx+10h], rbx
0x14000f666  lea     rcx, [rbp+0A0h]; struct DOT11_MAC_STATE_MODULE *
0x14000f66d  mov     [rbx], rbp
0x14000f670  call    ?Dot11AcquireMacState@@YAHPEAUDOT11_MAC_STATE_MODULE@@PEAY05$$CBEPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11AcquireMacState(DOT11_MAC_STATE_MODULE *,uchar const (*)[6],DOT11_MAC_STATE_ENTRY * *)
0x14000f675  cmp     [rsp+0A8h+arg_18], 0
0x14000f67d  mov     rdx, rdi; SrcNetBufferList
0x14000f680  mov     [rsp+0A8h+var_68], r14
0x14000f685  jz      loc_14000F72A
0x14000f68b  mov     r8, r14
0x14000f68e  mov     rcx, rbp
0x14000f691  call    Pt6DuplicateOneNBLAndData
0x14000f696  mov     r13d, eax
0x14000f699  test    eax, eax
0x14000f69b  jz      short loc_14000F6E9
0x14000f69d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f6a4  lea     r12, WPP_GLOBAL_Control
0x14000f6ab  cmp     rcx, r12
0x14000f6ae  jz      short loc_14000F6DA
0x14000f6b0  cmp     byte ptr [rcx+29h], 2
0x14000f6b4  jb      short loc_14000F6DA
0x14000f6b6  mov     edx, [rcx+2Ch]
0x14000f6b9  test    dl, 20h
0x14000f6bc  jz      short loc_14000F6DA
0x14000f6be  mov     rcx, [rcx+18h]
0x14000f6c2  lea     r8, WPP_f7be174c5c0c3ddfd0519d9dc4150861_Traceguids
0x14000f6c9  mov     edx, 0Bh
0x14000f6ce  mov     [rsp+0A8h+var_88], eax
0x14000f6d2  mov     r9, rdi
0x14000f6d5  call    WPP_SF_qD
0x14000f6da  mov     rbx, [rsp+0A8h+var_70]
0x14000f6df  mov     rsi, [rsp+0A8h+var_78]
0x14000f6e4  jmp     loc_14000F7C3
0x14000f6e9  mov     rdx, rdi; SrcNetBufferList
0x14000f6ec  mov     rcx, r14; DestNetBufferList
0x14000f6ef  call    cs:__imp_NdisCopyReceiveNetBufferListInfo
0x14000f6f6  nop     dword ptr [rax+rax+00h]
0x14000f6fb  mov     rcx, [r14+10h]
0x14000f6ff  mov     r8d, dword ptr [rsp+0A8h+Size]; Size
0x14000f707  mov     rdx, [rdi+0C0h]; Src
0x14000f70e  movzx   eax, word ptr [rcx+0Ah]
0x14000f712  mov     rbx, [rax+rcx+10h]
0x14000f717  add     rbx, 1B0h
0x14000f71e  mov     rcx, rbx; void *
0x14000f721  call    memmove
0x14000f726  xor     edi, edi
0x14000f728  jmp     short loc_14000F752
0x14000f72a  mov     rcx, r14; DestNetBufferList
0x14000f72d  mov     qword ptr [rdi], 0
0x14000f734  call    cs:__imp_NdisCopyReceiveNetBufferListInfo
0x14000f73b  nop     dword ptr [rax+rax+00h]
0x14000f740  mov     rax, [rdi+8]
0x14000f744  xor     r13d, r13d
0x14000f747  mov     rbx, [rdi+0C0h]
0x14000f74e  mov     [r14+8], rax
0x14000f752  mov     r12d, [rsp+0A8h+arg_10]
0x14000f75a  mov     [r14+0C0h], rbx
0x14000f761  inc     r12d
0x14000f764  mov     rcx, [r14+10h]
0x14000f768  mov     [rsp+0A8h+arg_10], r12d
0x14000f770  movzx   eax, word ptr [rcx+0Ah]
0x14000f774  mov     rdx, [rax+rcx+10h]
0x14000f779  mov     rcx, [rdx+28h]
0x14000f77d  lea     rax, [rcx+18h]
0x14000f781  mov     [rdx+28h], rax
0x14000f785  lea     rax, Pt6RecvNBLComplete
0x14000f78c  mov     [rcx], rax
0x14000f78f  mov     [rcx+8], rbp
0x14000f793  mov     [rcx+10h], rdi
0x14000f797  mov     qword ptr [r14], 0
0x14000f79e  test    r15, r15
0x14000f7a1  jnz     short loc_14000F7A8
0x14000f7a3  mov     r15, r14
0x14000f7a6  jmp     short loc_14000F7B0
0x14000f7a8  mov     rax, [rsp+0A8h+var_58]
0x14000f7ad  mov     [rax], r14
0x14000f7b0  mov     rbx, [rsp+0A8h+var_70]
0x14000f7b5  mov     [rsp+0A8h+var_58], r14
0x14000f7ba  jmp     short loc_14000F7FE
0x14000f7bc  lea     r12, WPP_GLOBAL_Control
0x14000f7c3  test    r14, r14
0x14000f7c6  jz      loc_14000F531
0x14000f7cc  lea     rcx, [rsp+0A8h+var_68]; struct _NET_BUFFER_LIST **
0x14000f7d1  call    ?Dot11FreeRecvPacket@@YAXPEAPEAU_NET_BUFFER_LIST@@@Z; Dot11FreeRecvPacket(_NET_BUFFER_LIST * *)
0x14000f7d6  mov     r14, [rsp+0A8h+var_68]
0x14000f7db  jmp     loc_14000F531
0x14000f7e0  mov     rax, [rsp+0A8h+var_60]
0x14000f7e5  mov     [rax], rdi
0x14000f7e8  mov     [rsp+0A8h+var_60], rdi
0x14000f7ed  cmp     r13d, 0C000009Ah
0x14000f7f4  jz      short loc_14000F80B
0x14000f7f6  mov     r12d, [rsp+0A8h+arg_10]
0x14000f7fe  mov     rsi, [rsp+0A8h+var_78]
0x14000f803  mov     rdi, rbx
0x14000f806  jmp     loc_14000F4B0
0x14000f80b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f812  cmp     rcx, r12
0x14000f815  jz      short loc_14000F839
0x14000f817  cmp     byte ptr [rcx+29h], 4
0x14000f81b  jb      short loc_14000F839
0x14000f81d  mov     eax, [rcx+2Ch]
0x14000f820  test    al, 20h
0x14000f822  jz      short loc_14000F839
0x14000f824  mov     rcx, [rcx+18h]
0x14000f828  lea     r8, WPP_f7be174c5c0c3ddfd0519d9dc4150861_Traceguids
0x14000f82f  mov     edx, 0Ch
0x14000f834  call    WPP_SF_
0x14000f839  mov     r12d, [rsp+0A8h+arg_10]
0x14000f841  mov     rcx, [rbp+90h]; Lock
0x14000f848  lea     rdx, [rsp+0A8h+LockState]; LockState
0x14000f850  call    cs:__imp_NdisReleaseRWLock
0x14000f857  nop     dword ptr [rax+rax+00h]
0x14000f85c  cmp     [rsp+0A8h+arg_18], 0
0x14000f864  jnz     short loc_14000F897
0x14000f866  test    rsi, rsi
0x14000f869  jnz     short loc_14000F875
0x14000f86b  test    rbx, rbx
0x14000f86e  jz      short loc_14000F897
0x14000f870  mov     rsi, rbx
0x14000f873  jmp     short loc_14000F87D
0x14000f875  mov     rax, [rsp+0A8h+var_60]
0x14000f87a  mov     [rax], rbx
0x14000f87d  mov     rcx, [rbp+10h]
0x14000f881  xor     r8d, r8d; ReturnFlags
0x14000f884  mov     rdx, rsi; NetBufferLists
0x14000f887  mov     rcx, [rcx+50h]; NdisFilterHandle
0x14000f88b  call    cs:__imp_NdisFReturnNetBufferLists
0x14000f892  nop     dword ptr [rax+rax+00h]
0x14000f897  lock add [rbp+135Ch], r12d
0x14000f89f  mov     rax, [rbp+10h]
0x14000f8a3  lock add [rax+0ECh], r12d
0x14000f8ab  cmp     r13d, 0C000009Ah
0x14000f8b2  jnz     short loc_14000F8C4
0x14000f8b4  test    r15, r15
0x14000f8b7  jz      short loc_14000F8C4
0x14000f8b9  mov     rdx, r15; struct _NET_BUFFER_LIST *
0x14000f8bc  call    ?FilterReturnNetBufferLists@@YAXPEAU_ADAPT@@PEAU_NET_BUFFER_LIST@@K@Z; FilterReturnNetBufferLists(_ADAPT *,_NET_BUFFER_LIST *,ulong)
0x14000f8c1  xor     r15d, r15d
0x14000f8c4  mov     rax, r15
0x14000f8c7  add     rsp, 68h
0x14000f8cb  pop     r15
0x14000f8cd  pop     r14
0x14000f8cf  pop     r13
0x14000f8d1  pop     r12
0x14000f8d3  pop     rdi
0x14000f8d4  pop     rsi
0x14000f8d5  pop     rbp
0x14000f8d6  pop     rbx
0x14000f8d7  retn
```
