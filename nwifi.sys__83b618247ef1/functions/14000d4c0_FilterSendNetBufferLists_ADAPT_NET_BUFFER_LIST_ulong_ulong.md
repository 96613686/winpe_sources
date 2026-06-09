# FilterSendNetBufferLists(_ADAPT *,_NET_BUFFER_LIST *,ulong,ulong)

- ea: `0x14000d4c0`
- end: `0x14000d785`
- name: `?FilterSendNetBufferLists@@YAXPEAU_ADAPT@@PEAU_NET_BUFFER_LIST@@KK@Z`
- size: `709`
- prototype: `void(struct _ADAPT *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14000d22c`
- `0x14000d4c0`
- `0x14000d78c`
- `0x14000dfa8`
- `0x14000e188`
- `0x140019314`
- `0x140037c8c`
- `0x14009a410`

## import_xrefs

- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000d61e`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000d762`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000d61e`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000d762`
- `NDIS!NdisReleaseRWLock` at `0x14000d649`
- `NDIS!NdisReleaseRWLock` at `0x14000d649`
- `NDIS!NdisAcquireRWLockRead` at `0x14000d589`
- `NDIS!NdisAcquireRWLockRead` at `0x14000d589`

## pseudocode

```c
void __fastcall FilterSendNetBufferLists(struct _ADAPT *a1, struct _NET_BUFFER_LIST *a2)
{
  _VELAN *pActiveVElan; // rdi
  struct _NDIS_RW_LOCK_EX *pRWLock; // rcx
  struct _NET_BUFFER_LIST *v5; // rsi
  PNET_BUFFER_LIST v6; // rax
  struct _NET_BUFFER_LIST *Alignment; // rsi
  int v8; // eax
  int v9; // r15d
  DOT11_DRIVER *pDot11Driver; // rax
  struct _NET_BUFFER_LIST *v11; // r14
  void *hMiniport; // rcx
  struct _NET_BUFFER_LIST *i; // rax
  struct _NET_BUFFER_LIST *v14; // [rsp+30h] [rbp-30h] BYREF
  PNET_BUFFER_LIST NetBufferList; // [rsp+38h] [rbp-28h] BYREF
  struct _NET_BUFFER_LIST *v16; // [rsp+40h] [rbp-20h] BYREF
  __int128 v17; // [rsp+48h] [rbp-18h] BYREF
  __int64 v18; // [rsp+58h] [rbp-8h]
  struct _LOCK_STATE_EX LockState; // [rsp+80h] [rbp+20h] BYREF

  pActiveVElan = a1->pActiveVElan;
  if ( pActiveVElan->State == MP6_RUNNING && pActiveVElan->MPDevicePowerState <= NdisDeviceStateD0 )
  {
    if ( (pActiveVElan->uNumRoamingNBL || pActiveVElan->bRoamingMode)
      && (unsigned int)MP6QueueRoamingNBL(pActiveVElan) == 259 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_c867dd3d8fa430bb45808a98b994f216_Traceguids);
      }
    }
    else
    {
      pRWLock = pActiveVElan->pRWLock;
      NetBufferList = a2;
      v5 = 0;
      *(_WORD *)&LockState.LockState = 0;
      v14 = 0;
      v16 = 0;
      LockState.OldIrql = 0;
      v17 = 0;
      v18 = 0;
      NdisAcquireRWLockRead(pRWLock, &LockState, 0);
      v6 = NetBufferList;
      if ( NetBufferList )
      {
        do
        {
          Alignment = (struct _NET_BUFFER_LIST *)v6->Link.Alignment;
          v6->Link.Alignment = 0;
          v8 = MP6SendOneNBL(pActiveVElan, NetBufferList, &v14, &v16);
          v9 = v8;
          if ( v8 != 259 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                25,
                WPP_c867dd3d8fa430bb45808a98b994f216_Traceguids,
                NetBufferList,
                v8);
            }
            NetBufferList->Status = v9;
            NdisFSendNetBufferListsComplete(pActiveVElan->hMiniport, NetBufferList, 0);
          }
          v6 = Alignment;
          NetBufferList = Alignment;
        }
        while ( Alignment );
        v5 = v14;
      }
      NdisReleaseRWLock(pActiveVElan->pRWLock, &LockState);
      NetBufferList = v5;
      if ( v5 )
      {
        do
        {
          pDot11Driver = pActiveVElan->pDot11Driver;
          v11 = (struct _NET_BUFFER_LIST *)v5->Link.Alignment;
          v5->Link.Alignment = 0;
          if ( pActiveVElan->FIPSContext.bSafeMode || !pDot11Driver->Dot11SendHandleLocal )
            pDot11Driver->Dot11SendHandle(pActiveVElan->pVElanExt, &NetBufferList, 1u);
          else
            pDot11Driver->Dot11SendHandleLocal(pActiveVElan->pVElanExt, &NetBufferList, 1u, &v17);
          NetBufferList = v11;
          v5 = v11;
        }
        while ( v11 );
      }
      Dot11FlushIntermediateSendQueue(pActiveVElan);
      v16 = 0;
      LODWORD(v14) = 0;
      if ( (_DWORD)v17 )
      {
        LODWORD(v17) = 0;
        Dot11FlushIntermediateSendQueueWithoutLock(pActiveVElan, (__int64)&v16);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_c867dd3d8fa430bb45808a98b994f216_Traceguids);
    }
    hMiniport = pActiveVElan->hMiniport;
    for ( i = a2; i; i = (struct _NET_BUFFER_LIST *)i->Link.Alignment )
      i->Status = -1071448022;
    NdisFSendNetBufferListsComplete(hMiniport, a2, 0);
  }
}

```

## disassembly

```asm
0x14000d4c0  mov     [rsp-18h+arg_8], rsi
0x14000d4c5  mov     [rsp-18h+arg_10], rdi
0x14000d4ca  push    rbp
0x14000d4cb  push    r14
0x14000d4cd  push    r15
0x14000d4cf  mov     rbp, rsp
0x14000d4d2  sub     rsp, 60h
0x14000d4d6  mov     rdi, [rcx+80h]
0x14000d4dd  mov     rsi, rdx
0x14000d4e0  cmp     dword ptr [rdi+18h], 3
0x14000d4e4  jnz     loc_14000D709
0x14000d4ea  cmp     dword ptr [rdi+13F4h], 1
0x14000d4f1  jg      loc_14000D709
0x14000d4f7  cmp     dword ptr [rdi+60h], 0
0x14000d4fb  jnz     short loc_14000D503
0x14000d4fd  cmp     dword ptr [rdi+50h], 0
0x14000d501  jz      short loc_14000D558
0x14000d503  mov     rcx, rdi; struct _VELAN *
0x14000d506  call    MP6QueueRoamingNBL
0x14000d50b  cmp     eax, 103h
0x14000d510  jnz     short loc_14000D558
0x14000d512  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d519  lea     r14, WPP_GLOBAL_Control
0x14000d520  cmp     rcx, r14
0x14000d523  jz      loc_14000D76E
0x14000d529  cmp     byte ptr [rcx+29h], 4
0x14000d52d  jb      loc_14000D76E
0x14000d533  mov     eax, [rcx+2Ch]
0x14000d536  test    al, 40h
0x14000d538  jz      loc_14000D76E
0x14000d53e  mov     rcx, [rcx+18h]
0x14000d542  lea     r8, WPP_c867dd3d8fa430bb45808a98b994f216_Traceguids
0x14000d549  mov     edx, 1Bh
0x14000d54e  call    WPP_SF_
0x14000d553  jmp     loc_14000D76E
0x14000d558  mov     rcx, [rdi+90h]; Lock
0x14000d55f  lea     rdx, [rbp+LockState]; LockState
0x14000d563  xor     eax, eax
0x14000d565  mov     [rbp+NetBufferList], rsi
0x14000d569  xor     esi, esi
0x14000d56b  mov     word ptr [rbp+LockState.LockState], ax
0x14000d56f  xorps   xmm0, xmm0
0x14000d572  mov     [rbp+var_30], rsi
0x14000d576  xor     r8d, r8d; Flags
0x14000d579  mov     [rbp+var_20], rsi
0x14000d57d  mov     [rbp+LockState.OldIrql], sil
0x14000d581  movups  [rbp+var_18], xmm0
0x14000d585  mov     [rbp+var_8], rax
0x14000d589  call    cs:__imp_NdisAcquireRWLockRead
0x14000d590  nop     dword ptr [rax+rax+00h]
0x14000d595  mov     rax, [rbp+NetBufferList]
0x14000d599  test    rax, rax
0x14000d59c  jz      loc_14000D63E
0x14000d5a2  lea     r14, WPP_GLOBAL_Control
0x14000d5a9  mov     rsi, [rax]
0x14000d5ac  lea     r9, [rbp+var_20]; struct _NET_BUFFER_LIST **
0x14000d5b0  mov     qword ptr [rax], 0
0x14000d5b7  lea     r8, [rbp+var_30]; struct _NET_BUFFER_LIST **
0x14000d5bb  mov     rdx, [rbp+NetBufferList]; struct _NET_BUFFER_LIST *
0x14000d5bf  mov     rcx, rdi; struct _VELAN *
0x14000d5c2  call    ?MP6SendOneNBL@@YAHPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@PEAPEAU2@2@Z; MP6SendOneNBL(_VELAN *,_NET_BUFFER_LIST *,_NET_BUFFER_LIST * *,_NET_BUFFER_LIST * *)
0x14000d5c7  mov     r15d, eax
0x14000d5ca  cmp     eax, 103h
0x14000d5cf  jz      short loc_14000D62A
0x14000d5d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d5d8  cmp     rcx, r14
0x14000d5db  jz      short loc_14000D608
0x14000d5dd  cmp     byte ptr [rcx+29h], 4
0x14000d5e1  jb      short loc_14000D608
0x14000d5e3  mov     edx, [rcx+2Ch]
0x14000d5e6  test    dl, 40h
0x14000d5e9  jz      short loc_14000D608
0x14000d5eb  mov     r9, [rbp+NetBufferList]
0x14000d5ef  lea     r8, WPP_c867dd3d8fa430bb45808a98b994f216_Traceguids
0x14000d5f6  mov     rcx, [rcx+18h]
0x14000d5fa  mov     edx, 19h
0x14000d5ff  mov     dword ptr [rsp+60h+var_40], eax
0x14000d603  call    WPP_SF_qD
0x14000d608  mov     rax, [rbp+NetBufferList]
0x14000d60c  xor     r8d, r8d; SendCompleteFlags
0x14000d60f  mov     [rax+8Ch], r15d
0x14000d616  mov     rdx, [rbp+NetBufferList]; NetBufferList
0x14000d61a  mov     rcx, [rdi+20h]; NdisFilterHandle
0x14000d61e  call    cs:__imp_NdisFSendNetBufferListsComplete
0x14000d625  nop     dword ptr [rax+rax+00h]
0x14000d62a  mov     rax, rsi
0x14000d62d  mov     [rbp+NetBufferList], rax
0x14000d631  test    rsi, rsi
0x14000d634  jnz     loc_14000D5A9
0x14000d63a  mov     rsi, [rbp+var_30]
0x14000d63e  mov     rcx, [rdi+90h]; Lock
0x14000d645  lea     rdx, [rbp+LockState]; LockState
0x14000d649  call    cs:__imp_NdisReleaseRWLock
0x14000d650  nop     dword ptr [rax+rax+00h]
0x14000d655  mov     [rbp+NetBufferList], rsi
0x14000d659  test    rsi, rsi
0x14000d65c  jz      short loc_14000D6C5
0x14000d65e  mov     rax, [rdi+98h]
0x14000d665  mov     r14, [rsi]
0x14000d668  mov     qword ptr [rsi], 0
0x14000d66f  cmp     dword ptr [rdi+15F8h], 0
0x14000d676  jnz     short loc_14000D6A0
0x14000d678  mov     r10, [rax+8]
0x14000d67c  test    r10, r10
0x14000d67f  jz      short loc_14000D6A0
0x14000d681  mov     rcx, [rdi+1F68h]
0x14000d688  lea     r9, [rbp+var_18]
0x14000d68c  mov     r8d, 1
0x14000d692  lea     rdx, [rbp+NetBufferList]
0x14000d696  mov     rax, r10
0x14000d699  call    _guard_dispatch_icall
0x14000d69e  jmp     short loc_14000D6B9
0x14000d6a0  mov     rax, [rax]
0x14000d6a3  lea     rdx, [rbp+NetBufferList]
0x14000d6a7  mov     rcx, [rdi+1F68h]
0x14000d6ae  mov     r8d, 1
0x14000d6b4  call    _guard_dispatch_icall
0x14000d6b9  mov     [rbp+NetBufferList], r14
0x14000d6bd  mov     rsi, r14
0x14000d6c0  test    r14, r14
0x14000d6c3  jnz     short loc_14000D65E
0x14000d6c5  mov     rcx, rdi; struct _VELAN *
0x14000d6c8  call    ?Dot11FlushIntermediateSendQueue@@YAXPEAU_VELAN@@@Z; Dot11FlushIntermediateSendQueue(_VELAN *)
0x14000d6cd  mov     edx, dword ptr [rbp+var_18]
0x14000d6d0  mov     [rbp+var_20], 0
0x14000d6d8  mov     dword ptr [rbp+var_30], 0
0x14000d6df  test    edx, edx
0x14000d6e1  jz      loc_14000D76E
0x14000d6e7  mov     r8, qword ptr [rbp+var_18+8]
0x14000d6eb  lea     rax, [rbp+var_20]
0x14000d6ef  lea     r9, [rbp+var_30]
0x14000d6f3  mov     [rsp+60h+var_40], rax; __int64
0x14000d6f8  mov     rcx, rdi; struct _VELAN *
0x14000d6fb  mov     dword ptr [rbp+var_18], 0
0x14000d702  call    Dot11FlushIntermediateSendQueueWithoutLock
0x14000d707  jmp     short loc_14000D76E
0x14000d709  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d710  lea     r14, WPP_GLOBAL_Control
0x14000d717  cmp     rcx, r14
0x14000d71a  jz      short loc_14000D73E
0x14000d71c  cmp     byte ptr [rcx+29h], 4
0x14000d720  jb      short loc_14000D73E
0x14000d722  mov     eax, [rcx+2Ch]
0x14000d725  test    al, 40h
0x14000d727  jz      short loc_14000D73E
0x14000d729  mov     rcx, [rcx+18h]
0x14000d72d  lea     r8, WPP_c867dd3d8fa430bb45808a98b994f216_Traceguids
0x14000d734  mov     edx, 1Ah
0x14000d739  call    WPP_SF_
0x14000d73e  mov     rcx, [rdi+20h]; NdisFilterHandle
0x14000d742  mov     rax, rsi
0x14000d745  test    rsi, rsi
0x14000d748  jz      short loc_14000D75C
0x14000d74a  mov     dword ptr [rax+8Ch], 0C023002Ah
0x14000d754  mov     rax, [rax]
0x14000d757  test    rax, rax
0x14000d75a  jnz     short loc_14000D74A
0x14000d75c  xor     r8d, r8d; SendCompleteFlags
0x14000d75f  mov     rdx, rsi; NetBufferList
0x14000d762  call    cs:__imp_NdisFSendNetBufferListsComplete
0x14000d769  nop     dword ptr [rax+rax+00h]
0x14000d76e  lea     r11, [rsp+60h+var_s0]
0x14000d773  mov     rsi, [r11+28h]
0x14000d777  mov     rdi, [r11+30h]
0x14000d77b  mov     rsp, r11
0x14000d77e  pop     r15
0x14000d780  pop     r14
0x14000d782  pop     rbp
0x14000d783  retn
```
