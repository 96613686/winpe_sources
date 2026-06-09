# FilterSendNetBufferLists(_ADAPT *,_NET_BUFFER_LIST *,ulong,ulong)

- ea: `0x14000d4b0`
- end: `0x14000d775`
- name: `?FilterSendNetBufferLists@@YAXPEAU_ADAPT@@PEAU_NET_BUFFER_LIST@@KK@Z`
- size: `709`
- prototype: `void(struct _ADAPT *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14000d21c`
- `0x14000d4b0`
- `0x14000d77c`
- `0x14000df98`
- `0x14000e178`
- `0x140019314`
- `0x140037eac`
- `0x14009bbf0`

## import_xrefs

- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000d60e`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000d752`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000d60e`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000d752`
- `NDIS!NdisReleaseRWLock` at `0x14000d639`
- `NDIS!NdisReleaseRWLock` at `0x14000d639`
- `NDIS!NdisAcquireRWLockRead` at `0x14000d579`
- `NDIS!NdisAcquireRWLockRead` at `0x14000d579`

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
0x14000d4b0  mov     [rsp-18h+arg_8], rsi
0x14000d4b5  mov     [rsp-18h+arg_10], rdi
0x14000d4ba  push    rbp
0x14000d4bb  push    r14
0x14000d4bd  push    r15
0x14000d4bf  mov     rbp, rsp
0x14000d4c2  sub     rsp, 60h
0x14000d4c6  mov     rdi, [rcx+80h]
0x14000d4cd  mov     rsi, rdx
0x14000d4d0  cmp     dword ptr [rdi+18h], 3
0x14000d4d4  jnz     loc_14000D6F9
0x14000d4da  cmp     dword ptr [rdi+13F4h], 1
0x14000d4e1  jg      loc_14000D6F9
0x14000d4e7  cmp     dword ptr [rdi+60h], 0
0x14000d4eb  jnz     short loc_14000D4F3
0x14000d4ed  cmp     dword ptr [rdi+50h], 0
0x14000d4f1  jz      short loc_14000D548
0x14000d4f3  mov     rcx, rdi; struct _VELAN *
0x14000d4f6  call    MP6QueueRoamingNBL
0x14000d4fb  cmp     eax, 103h
0x14000d500  jnz     short loc_14000D548
0x14000d502  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d509  lea     r14, WPP_GLOBAL_Control
0x14000d510  cmp     rcx, r14
0x14000d513  jz      loc_14000D75E
0x14000d519  cmp     byte ptr [rcx+29h], 4
0x14000d51d  jb      loc_14000D75E
0x14000d523  mov     eax, [rcx+2Ch]
0x14000d526  test    al, 40h
0x14000d528  jz      loc_14000D75E
0x14000d52e  mov     rcx, [rcx+18h]
0x14000d532  lea     r8, WPP_c867dd3d8fa430bb45808a98b994f216_Traceguids
0x14000d539  mov     edx, 1Bh
0x14000d53e  call    WPP_SF_
0x14000d543  jmp     loc_14000D75E
0x14000d548  mov     rcx, [rdi+90h]; Lock
0x14000d54f  lea     rdx, [rbp+LockState]; LockState
0x14000d553  xor     eax, eax
0x14000d555  mov     [rbp+NetBufferList], rsi
0x14000d559  xor     esi, esi
0x14000d55b  mov     word ptr [rbp+LockState.LockState], ax
0x14000d55f  xorps   xmm0, xmm0
0x14000d562  mov     [rbp+var_30], rsi
0x14000d566  xor     r8d, r8d; Flags
0x14000d569  mov     [rbp+var_20], rsi
0x14000d56d  mov     [rbp+LockState.OldIrql], sil
0x14000d571  movups  [rbp+var_18], xmm0
0x14000d575  mov     [rbp+var_8], rax
0x14000d579  call    cs:__imp_NdisAcquireRWLockRead
0x14000d580  nop     dword ptr [rax+rax+00h]
0x14000d585  mov     rax, [rbp+NetBufferList]
0x14000d589  test    rax, rax
0x14000d58c  jz      loc_14000D62E
0x14000d592  lea     r14, WPP_GLOBAL_Control
0x14000d599  mov     rsi, [rax]
0x14000d59c  lea     r9, [rbp+var_20]; struct _NET_BUFFER_LIST **
0x14000d5a0  mov     qword ptr [rax], 0
0x14000d5a7  lea     r8, [rbp+var_30]; struct _NET_BUFFER_LIST **
0x14000d5ab  mov     rdx, [rbp+NetBufferList]; struct _NET_BUFFER_LIST *
0x14000d5af  mov     rcx, rdi; struct _VELAN *
0x14000d5b2  call    ?MP6SendOneNBL@@YAHPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@PEAPEAU2@2@Z; MP6SendOneNBL(_VELAN *,_NET_BUFFER_LIST *,_NET_BUFFER_LIST * *,_NET_BUFFER_LIST * *)
0x14000d5b7  mov     r15d, eax
0x14000d5ba  cmp     eax, 103h
0x14000d5bf  jz      short loc_14000D61A
0x14000d5c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d5c8  cmp     rcx, r14
0x14000d5cb  jz      short loc_14000D5F8
0x14000d5cd  cmp     byte ptr [rcx+29h], 4
0x14000d5d1  jb      short loc_14000D5F8
0x14000d5d3  mov     edx, [rcx+2Ch]
0x14000d5d6  test    dl, 40h
0x14000d5d9  jz      short loc_14000D5F8
0x14000d5db  mov     r9, [rbp+NetBufferList]
0x14000d5df  lea     r8, WPP_c867dd3d8fa430bb45808a98b994f216_Traceguids
0x14000d5e6  mov     rcx, [rcx+18h]
0x14000d5ea  mov     edx, 19h
0x14000d5ef  mov     dword ptr [rsp+60h+var_40], eax
0x14000d5f3  call    WPP_SF_qD
0x14000d5f8  mov     rax, [rbp+NetBufferList]
0x14000d5fc  xor     r8d, r8d; SendCompleteFlags
0x14000d5ff  mov     [rax+8Ch], r15d
0x14000d606  mov     rdx, [rbp+NetBufferList]; NetBufferList
0x14000d60a  mov     rcx, [rdi+20h]; NdisFilterHandle
0x14000d60e  call    cs:__imp_NdisFSendNetBufferListsComplete
0x14000d615  nop     dword ptr [rax+rax+00h]
0x14000d61a  mov     rax, rsi
0x14000d61d  mov     [rbp+NetBufferList], rax
0x14000d621  test    rsi, rsi
0x14000d624  jnz     loc_14000D599
0x14000d62a  mov     rsi, [rbp+var_30]
0x14000d62e  mov     rcx, [rdi+90h]; Lock
0x14000d635  lea     rdx, [rbp+LockState]; LockState
0x14000d639  call    cs:__imp_NdisReleaseRWLock
0x14000d640  nop     dword ptr [rax+rax+00h]
0x14000d645  mov     [rbp+NetBufferList], rsi
0x14000d649  test    rsi, rsi
0x14000d64c  jz      short loc_14000D6B5
0x14000d64e  mov     rax, [rdi+98h]
0x14000d655  mov     r14, [rsi]
0x14000d658  mov     qword ptr [rsi], 0
0x14000d65f  cmp     dword ptr [rdi+15F8h], 0
0x14000d666  jnz     short loc_14000D690
0x14000d668  mov     r10, [rax+8]
0x14000d66c  test    r10, r10
0x14000d66f  jz      short loc_14000D690
0x14000d671  mov     rcx, [rdi+1F68h]
0x14000d678  lea     r9, [rbp+var_18]
0x14000d67c  mov     r8d, 1
0x14000d682  lea     rdx, [rbp+NetBufferList]
0x14000d686  mov     rax, r10
0x14000d689  call    _guard_dispatch_icall
0x14000d68e  jmp     short loc_14000D6A9
0x14000d690  mov     rax, [rax]
0x14000d693  lea     rdx, [rbp+NetBufferList]
0x14000d697  mov     rcx, [rdi+1F68h]
0x14000d69e  mov     r8d, 1
0x14000d6a4  call    _guard_dispatch_icall
0x14000d6a9  mov     [rbp+NetBufferList], r14
0x14000d6ad  mov     rsi, r14
0x14000d6b0  test    r14, r14
0x14000d6b3  jnz     short loc_14000D64E
0x14000d6b5  mov     rcx, rdi; struct _VELAN *
0x14000d6b8  call    ?Dot11FlushIntermediateSendQueue@@YAXPEAU_VELAN@@@Z; Dot11FlushIntermediateSendQueue(_VELAN *)
0x14000d6bd  mov     edx, dword ptr [rbp+var_18]
0x14000d6c0  mov     [rbp+var_20], 0
0x14000d6c8  mov     dword ptr [rbp+var_30], 0
0x14000d6cf  test    edx, edx
0x14000d6d1  jz      loc_14000D75E
0x14000d6d7  mov     r8, qword ptr [rbp+var_18+8]
0x14000d6db  lea     rax, [rbp+var_20]
0x14000d6df  lea     r9, [rbp+var_30]
0x14000d6e3  mov     [rsp+60h+var_40], rax; __int64
0x14000d6e8  mov     rcx, rdi; struct _VELAN *
0x14000d6eb  mov     dword ptr [rbp+var_18], 0
0x14000d6f2  call    Dot11FlushIntermediateSendQueueWithoutLock
0x14000d6f7  jmp     short loc_14000D75E
0x14000d6f9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d700  lea     r14, WPP_GLOBAL_Control
0x14000d707  cmp     rcx, r14
0x14000d70a  jz      short loc_14000D72E
0x14000d70c  cmp     byte ptr [rcx+29h], 4
0x14000d710  jb      short loc_14000D72E
0x14000d712  mov     eax, [rcx+2Ch]
0x14000d715  test    al, 40h
0x14000d717  jz      short loc_14000D72E
0x14000d719  mov     rcx, [rcx+18h]
0x14000d71d  lea     r8, WPP_c867dd3d8fa430bb45808a98b994f216_Traceguids
0x14000d724  mov     edx, 1Ah
0x14000d729  call    WPP_SF_
0x14000d72e  mov     rcx, [rdi+20h]; NdisFilterHandle
0x14000d732  mov     rax, rsi
0x14000d735  test    rsi, rsi
0x14000d738  jz      short loc_14000D74C
0x14000d73a  mov     dword ptr [rax+8Ch], 0C023002Ah
0x14000d744  mov     rax, [rax]
0x14000d747  test    rax, rax
0x14000d74a  jnz     short loc_14000D73A
0x14000d74c  xor     r8d, r8d; SendCompleteFlags
0x14000d74f  mov     rdx, rsi; NetBufferList
0x14000d752  call    cs:__imp_NdisFSendNetBufferListsComplete
0x14000d759  nop     dword ptr [rax+rax+00h]
0x14000d75e  lea     r11, [rsp+60h+var_s0]
0x14000d763  mov     rsi, [r11+28h]
0x14000d767  mov     rdi, [r11+30h]
0x14000d76b  mov     rsp, r11
0x14000d76e  pop     r15
0x14000d770  pop     r14
0x14000d772  pop     rbp
0x14000d773  retn
```
