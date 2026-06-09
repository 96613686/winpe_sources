# Pt6RepackRecvNBL(_VELAN *,ulong,_NET_BUFFER_LIST *,int)

- ea: `0x14000f430`
- end: `0x14000f8c9`
- name: `?Pt6RepackRecvNBL@@YAPEAU_NET_BUFFER_LIST@@PEAU_VELAN@@KPEAU1@H@Z`
- size: `1177`
- prototype: `struct _NET_BUFFER_LIST *(struct _VELAN *, unsigned int, struct _NET_BUFFER_LIST *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f0b0`

## callees

- `0x14000d21c`
- `0x14000f430`
- `0x14000f8d0`
- `0x140010218`
- `0x140013720`
- `0x140013790`
- `0x140019314`
- `0x1400208f0`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000f5a5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000f5a5`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x14000f6df`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x14000f724`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x14000f6df`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x14000f724`
- `NDIS!NdisFReturnNetBufferLists` at `0x14000f87b`
- `NDIS!NdisFReturnNetBufferLists` at `0x14000f87b`
- `NDIS!NdisAllocateNetBufferList` at `0x14000f577`
- `NDIS!NdisAllocateNetBufferList` at `0x14000f577`
- `NDIS!NdisFreeNetBufferList` at `0x14000f5bf`
- `NDIS!NdisFreeNetBufferList` at `0x14000f5bf`
- `NDIS!NdisReleaseRWLock` at `0x14000f840`
- `NDIS!NdisReleaseRWLock` at `0x14000f840`
- `NDIS!NdisAcquireRWLockRead` at `0x14000f494`
- `NDIS!NdisAcquireRWLockRead` at `0x14000f494`

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
0x14000f430  mov     r11, rsp
0x14000f433  mov     [r11+20h], r9d
0x14000f437  mov     dword ptr [rsp+Size], edx
0x14000f43b  push    rbx
0x14000f43c  push    rbp
0x14000f43d  push    rsi
0x14000f43e  push    rdi
0x14000f43f  push    r12
0x14000f441  push    r13
0x14000f443  push    r14
0x14000f445  push    r15
0x14000f447  sub     rsp, 68h
0x14000f44b  xor     eax, eax
0x14000f44d  lea     rdx, [r11+8]; LockState
0x14000f451  mov     rdi, r8
0x14000f454  mov     [r11-68h], rax
0x14000f458  mov     rbp, rcx
0x14000f45b  mov     [rsp+0A8h+var_58], rax
0x14000f460  mov     rcx, [rcx+90h]; Lock
0x14000f467  xor     r8d, r8d; Flags
0x14000f46a  mov     r13d, eax
0x14000f46d  mov     [rsp+0A8h+var_78], rax
0x14000f472  mov     r14d, eax
0x14000f475  mov     [rsp+0A8h+var_60], rax
0x14000f47a  mov     ebx, eax
0x14000f47c  mov     [rsp+0A8h+arg_10], eax
0x14000f483  mov     r15d, eax
0x14000f486  mov     [r11+8], al
0x14000f48a  mov     esi, eax
0x14000f48c  mov     [r11+9], ax
0x14000f491  mov     r12d, eax
0x14000f494  call    cs:__imp_NdisAcquireRWLockRead
0x14000f49b  nop     dword ptr [rax+rax+00h]
0x14000f4a0  lea     r9, WPP_GLOBAL_Control
0x14000f4a7  test    rdi, rdi
0x14000f4aa  jz      loc_14000F831
0x14000f4b0  mov     rax, [rdi+8]
0x14000f4b4  mov     rbx, [rdi]
0x14000f4b7  mov     [rsp+0A8h+var_70], rbx
0x14000f4bc  test    rax, rax
0x14000f4bf  jz      loc_14000F7AC
0x14000f4c5  mov     rdx, [rax+8]
0x14000f4c9  test    rdx, rdx
0x14000f4cc  jz      loc_14000F7AC
0x14000f4d2  mov     r8d, [rax+10h]
0x14000f4d6  xor     r14d, r14d
0x14000f4d9  add     r8, [rdx+18h]
0x14000f4dd  mov     [rsp+0A8h+var_68], r14
0x14000f4e2  movzx   ecx, word ptr [r8]
0x14000f4e6  mov     edx, ecx
0x14000f4e8  shr     edx, 2
0x14000f4eb  and     edx, 3
0x14000f4ee  jz      short loc_14000F55F
0x14000f4f0  sub     edx, 1
0x14000f4f3  jz      short loc_14000F545
0x14000f4f5  cmp     edx, 1
0x14000f4f8  jz      short loc_14000F55F
0x14000f4fa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f501  cmp     rcx, r9
0x14000f504  jz      short loc_14000F51A
0x14000f506  mov     rcx, [rcx+18h]
0x14000f50a  lea     edx, [r14+0Fh]
0x14000f50e  lea     r8, WPP_591672ea4a6b33fdc9f57e1d50f33c40_Traceguids
0x14000f515  call    WPP_SF_
0x14000f51a  lea     r12, WPP_GLOBAL_Control
0x14000f521  cmp     [rsp+0A8h+arg_18], 0
0x14000f529  jnz     loc_14000F7DD
0x14000f52f  test    rsi, rsi
0x14000f532  jnz     loc_14000F7D0
0x14000f538  mov     rsi, rdi
0x14000f53b  mov     [rsp+0A8h+var_78], rdi
0x14000f540  jmp     loc_14000F7D8
0x14000f545  shr     ecx, 4
0x14000f548  and     ecx, 0Fh
0x14000f54b  sub     ecx, 0Ah
0x14000f54e  jz      short loc_14000F55F
0x14000f550  sub     ecx, 1
0x14000f553  jz      short loc_14000F55F
0x14000f555  sub     ecx, 3
0x14000f558  jz      short loc_14000F55F
0x14000f55a  cmp     ecx, 1
0x14000f55d  jnz     short loc_14000F51A
0x14000f55f  mov     eax, 0Ah
0x14000f564  lea     r12, [rax+r8]
0x14000f568  test    r12, r12
0x14000f56b  jz      short loc_14000F51A
0x14000f56d  mov     rcx, [rbp+40h]; PoolHandle
0x14000f571  lea     edx, [rax-2]; ContextSize
0x14000f574  xor     r8d, r8d; ContextBackFill
0x14000f577  call    cs:__imp_NdisAllocateNetBufferList
0x14000f57e  nop     dword ptr [rax+rax+00h]
0x14000f583  mov     r14, rax
0x14000f586  test    rax, rax
0x14000f589  jnz     short loc_14000F593
0x14000f58b  mov     r13d, 0C000009Ah
0x14000f591  jmp     short loc_14000F5CE
0x14000f593  mov     rax, [rbp+20h]
0x14000f597  lea     r13, Lookaside
0x14000f59e  mov     rcx, r13; Lookaside
0x14000f5a1  mov     [r14+78h], rax
0x14000f5a5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000f5ac  nop     dword ptr [rax+rax+00h]
0x14000f5b1  test    rax, rax
0x14000f5b4  jnz     short loc_14000F61C
0x14000f5b6  mov     r13d, 0C000009Ah
0x14000f5bc  mov     rcx, r14; NetBufferList
0x14000f5bf  call    cs:__imp_NdisFreeNetBufferList
0x14000f5c6  nop     dword ptr [rax+rax+00h]
0x14000f5cb  xor     r14d, r14d
0x14000f5ce  mov     [rsp+0A8h+var_68], r14
0x14000f5d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f5da  lea     r12, WPP_GLOBAL_Control
0x14000f5e1  cmp     rcx, r12
0x14000f5e4  jz      loc_14000F7B3
0x14000f5ea  cmp     byte ptr [rcx+29h], 2
0x14000f5ee  jb      loc_14000F7B3
0x14000f5f4  mov     eax, [rcx+2Ch]
0x14000f5f7  test    al, 20h
0x14000f5f9  jz      loc_14000F7B3
0x14000f5ff  mov     rcx, [rcx+18h]
0x14000f603  lea     r8, WPP_f7be174c5c0c3ddfd0519d9dc4150861_Traceguids
0x14000f60a  mov     edx, 0Ah
0x14000f60f  mov     r9, rdi
0x14000f612  call    WPP_SF_q
0x14000f617  jmp     loc_14000F7B3
0x14000f61c  lea     rbx, [rax+10h]
0x14000f620  mov     [rax], r13
0x14000f623  mov     rcx, rbx; void *
0x14000f626  mov     dword ptr [rax+8], 61697377h
0x14000f62d  xor     edx, edx; Val
0x14000f62f  mov     r8d, 300h; Size
0x14000f635  call    memset
0x14000f63a  lea     rax, [rbx+30h]
0x14000f63e  mov     rdx, r12; unsigned __int8 (*)[6]
0x14000f641  mov     [rbx+28h], rax
0x14000f645  lea     r8, [rbx+8]; struct DOT11_MAC_STATE_ENTRY **
0x14000f649  mov     rcx, [r14+10h]
0x14000f64d  movzx   eax, word ptr [rcx+0Ah]
0x14000f651  mov     [rax+rcx+10h], rbx
0x14000f656  lea     rcx, [rbp+0A0h]; struct DOT11_MAC_STATE_MODULE *
0x14000f65d  mov     [rbx], rbp
0x14000f660  call    ?Dot11AcquireMacState@@YAHPEAUDOT11_MAC_STATE_MODULE@@PEAY05$$CBEPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11AcquireMacState(DOT11_MAC_STATE_MODULE *,uchar const (*)[6],DOT11_MAC_STATE_ENTRY * *)
0x14000f665  cmp     [rsp+0A8h+arg_18], 0
0x14000f66d  mov     rdx, rdi; SrcNetBufferList
0x14000f670  mov     [rsp+0A8h+var_68], r14
0x14000f675  jz      loc_14000F71A
0x14000f67b  mov     r8, r14
0x14000f67e  mov     rcx, rbp
0x14000f681  call    Pt6DuplicateOneNBLAndData
0x14000f686  mov     r13d, eax
0x14000f689  test    eax, eax
0x14000f68b  jz      short loc_14000F6D9
0x14000f68d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f694  lea     r12, WPP_GLOBAL_Control
0x14000f69b  cmp     rcx, r12
0x14000f69e  jz      short loc_14000F6CA
0x14000f6a0  cmp     byte ptr [rcx+29h], 2
0x14000f6a4  jb      short loc_14000F6CA
0x14000f6a6  mov     edx, [rcx+2Ch]
0x14000f6a9  test    dl, 20h
0x14000f6ac  jz      short loc_14000F6CA
0x14000f6ae  mov     rcx, [rcx+18h]
0x14000f6b2  lea     r8, WPP_f7be174c5c0c3ddfd0519d9dc4150861_Traceguids
0x14000f6b9  mov     edx, 0Bh
0x14000f6be  mov     [rsp+0A8h+var_88], eax
0x14000f6c2  mov     r9, rdi
0x14000f6c5  call    WPP_SF_qD
0x14000f6ca  mov     rbx, [rsp+0A8h+var_70]
0x14000f6cf  mov     rsi, [rsp+0A8h+var_78]
0x14000f6d4  jmp     loc_14000F7B3
0x14000f6d9  mov     rdx, rdi; SrcNetBufferList
0x14000f6dc  mov     rcx, r14; DestNetBufferList
0x14000f6df  call    cs:__imp_NdisCopyReceiveNetBufferListInfo
0x14000f6e6  nop     dword ptr [rax+rax+00h]
0x14000f6eb  mov     rcx, [r14+10h]
0x14000f6ef  mov     r8d, dword ptr [rsp+0A8h+Size]; Size
0x14000f6f7  mov     rdx, [rdi+0C0h]; Src
0x14000f6fe  movzx   eax, word ptr [rcx+0Ah]
0x14000f702  mov     rbx, [rax+rcx+10h]
0x14000f707  add     rbx, 1B0h
0x14000f70e  mov     rcx, rbx; void *
0x14000f711  call    memmove
0x14000f716  xor     edi, edi
0x14000f718  jmp     short loc_14000F742
0x14000f71a  mov     rcx, r14; DestNetBufferList
0x14000f71d  mov     qword ptr [rdi], 0
0x14000f724  call    cs:__imp_NdisCopyReceiveNetBufferListInfo
0x14000f72b  nop     dword ptr [rax+rax+00h]
0x14000f730  mov     rax, [rdi+8]
0x14000f734  xor     r13d, r13d
0x14000f737  mov     rbx, [rdi+0C0h]
0x14000f73e  mov     [r14+8], rax
0x14000f742  mov     r12d, [rsp+0A8h+arg_10]
0x14000f74a  mov     [r14+0C0h], rbx
0x14000f751  inc     r12d
0x14000f754  mov     rcx, [r14+10h]
0x14000f758  mov     [rsp+0A8h+arg_10], r12d
0x14000f760  movzx   eax, word ptr [rcx+0Ah]
0x14000f764  mov     rdx, [rax+rcx+10h]
0x14000f769  mov     rcx, [rdx+28h]
0x14000f76d  lea     rax, [rcx+18h]
0x14000f771  mov     [rdx+28h], rax
0x14000f775  lea     rax, Pt6RecvNBLComplete
0x14000f77c  mov     [rcx], rax
0x14000f77f  mov     [rcx+8], rbp
0x14000f783  mov     [rcx+10h], rdi
0x14000f787  mov     qword ptr [r14], 0
0x14000f78e  test    r15, r15
0x14000f791  jnz     short loc_14000F798
0x14000f793  mov     r15, r14
0x14000f796  jmp     short loc_14000F7A0
0x14000f798  mov     rax, [rsp+0A8h+var_58]
0x14000f79d  mov     [rax], r14
0x14000f7a0  mov     rbx, [rsp+0A8h+var_70]
0x14000f7a5  mov     [rsp+0A8h+var_58], r14
0x14000f7aa  jmp     short loc_14000F7EE
0x14000f7ac  lea     r12, WPP_GLOBAL_Control
0x14000f7b3  test    r14, r14
0x14000f7b6  jz      loc_14000F521
0x14000f7bc  lea     rcx, [rsp+0A8h+var_68]; struct _NET_BUFFER_LIST **
0x14000f7c1  call    ?Dot11FreeRecvPacket@@YAXPEAPEAU_NET_BUFFER_LIST@@@Z; Dot11FreeRecvPacket(_NET_BUFFER_LIST * *)
0x14000f7c6  mov     r14, [rsp+0A8h+var_68]
0x14000f7cb  jmp     loc_14000F521
0x14000f7d0  mov     rax, [rsp+0A8h+var_60]
0x14000f7d5  mov     [rax], rdi
0x14000f7d8  mov     [rsp+0A8h+var_60], rdi
0x14000f7dd  cmp     r13d, 0C000009Ah
0x14000f7e4  jz      short loc_14000F7FB
0x14000f7e6  mov     r12d, [rsp+0A8h+arg_10]
0x14000f7ee  mov     rsi, [rsp+0A8h+var_78]
0x14000f7f3  mov     rdi, rbx
0x14000f7f6  jmp     loc_14000F4A0
0x14000f7fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f802  cmp     rcx, r12
0x14000f805  jz      short loc_14000F829
0x14000f807  cmp     byte ptr [rcx+29h], 4
0x14000f80b  jb      short loc_14000F829
0x14000f80d  mov     eax, [rcx+2Ch]
0x14000f810  test    al, 20h
0x14000f812  jz      short loc_14000F829
0x14000f814  mov     rcx, [rcx+18h]
0x14000f818  lea     r8, WPP_f7be174c5c0c3ddfd0519d9dc4150861_Traceguids
0x14000f81f  mov     edx, 0Ch
0x14000f824  call    WPP_SF_
0x14000f829  mov     r12d, [rsp+0A8h+arg_10]
0x14000f831  mov     rcx, [rbp+90h]; Lock
0x14000f838  lea     rdx, [rsp+0A8h+LockState]; LockState
0x14000f840  call    cs:__imp_NdisReleaseRWLock
0x14000f847  nop     dword ptr [rax+rax+00h]
0x14000f84c  cmp     [rsp+0A8h+arg_18], 0
0x14000f854  jnz     short loc_14000F887
0x14000f856  test    rsi, rsi
0x14000f859  jnz     short loc_14000F865
0x14000f85b  test    rbx, rbx
0x14000f85e  jz      short loc_14000F887
0x14000f860  mov     rsi, rbx
0x14000f863  jmp     short loc_14000F86D
0x14000f865  mov     rax, [rsp+0A8h+var_60]
0x14000f86a  mov     [rax], rbx
0x14000f86d  mov     rcx, [rbp+10h]
0x14000f871  xor     r8d, r8d; ReturnFlags
0x14000f874  mov     rdx, rsi; NetBufferLists
0x14000f877  mov     rcx, [rcx+50h]; NdisFilterHandle
0x14000f87b  call    cs:__imp_NdisFReturnNetBufferLists
0x14000f882  nop     dword ptr [rax+rax+00h]
0x14000f887  lock add [rbp+135Ch], r12d
0x14000f88f  mov     rax, [rbp+10h]
0x14000f893  lock add [rax+0ECh], r12d
0x14000f89b  cmp     r13d, 0C000009Ah
0x14000f8a2  jnz     short loc_14000F8B4
0x14000f8a4  test    r15, r15
0x14000f8a7  jz      short loc_14000F8B4
0x14000f8a9  mov     rdx, r15; struct _NET_BUFFER_LIST *
0x14000f8ac  call    ?FilterReturnNetBufferLists@@YAXPEAU_ADAPT@@PEAU_NET_BUFFER_LIST@@K@Z; FilterReturnNetBufferLists(_ADAPT *,_NET_BUFFER_LIST *,ulong)
0x14000f8b1  xor     r15d, r15d
0x14000f8b4  mov     rax, r15
0x14000f8b7  add     rsp, 68h
0x14000f8bb  pop     r15
0x14000f8bd  pop     r14
0x14000f8bf  pop     r13
0x14000f8c1  pop     r12
0x14000f8c3  pop     rdi
0x14000f8c4  pop     rsi
0x14000f8c5  pop     rbp
0x14000f8c6  pop     rbx
0x14000f8c7  retn
```
