# MP6SendNBLInternal(_VELAN *,_NET_BUFFER_LIST *)

- ea: `0x14000d2e0`
- end: `0x14000d49d`
- name: `?MP6SendNBLInternal@@YAXPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@@Z`
- size: `445`
- prototype: `void __fastcall(struct _VELAN *, struct _NET_BUFFER_LIST *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140037a10`

## callees

- `0x14000d2e0`
- `0x14000d77c`
- `0x14000df98`
- `0x14000e178`
- `0x140019314`
- `0x14009bbf0`

## import_xrefs

- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000d3b2`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000d3b2`
- `NDIS!NdisReleaseRWLock` at `0x14000d3dd`
- `NDIS!NdisReleaseRWLock` at `0x14000d3dd`
- `NDIS!NdisAcquireRWLockRead` at `0x14000d31f`
- `NDIS!NdisAcquireRWLockRead` at `0x14000d31f`

## pseudocode

```c
void __fastcall MP6SendNBLInternal(struct _VELAN *a1, struct _NET_BUFFER_LIST *a2)
{
  struct _NET_BUFFER_LIST *v2; // rbx
  struct _NDIS_RW_LOCK_EX *pRWLock; // rcx
  PNET_BUFFER_LIST v5; // rax
  struct _NET_BUFFER_LIST *Alignment; // rsi
  int v7; // ebx
  bool i; // zf
  DOT11_DRIVER *pDot11Driver; // rax
  struct _NET_BUFFER_LIST *v10; // rsi
  __int128 v11; // [rsp+30h] [rbp-28h] BYREF
  __int64 v12; // [rsp+40h] [rbp-18h]
  struct _LOCK_STATE_EX LockState; // [rsp+80h] [rbp+28h] BYREF
  struct _NET_BUFFER_LIST *v14; // [rsp+88h] [rbp+30h] BYREF
  PNET_BUFFER_LIST NetBufferList; // [rsp+90h] [rbp+38h] BYREF
  struct _NET_BUFFER_LIST *v16; // [rsp+98h] [rbp+40h] BYREF

  v2 = 0;
  NetBufferList = a2;
  v14 = 0;
  v16 = 0;
  pRWLock = a1->pRWLock;
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  v11 = 0;
  v12 = 0;
  NdisAcquireRWLockRead(pRWLock, &LockState, 0);
  v5 = NetBufferList;
  if ( NetBufferList )
  {
    do
    {
      Alignment = (struct _NET_BUFFER_LIST *)v5->Link.Alignment;
      v5->Link.Alignment = 0;
      v7 = MP6SendOneNBL(a1, NetBufferList, &v14, &v16);
      if ( v7 != 259 )
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
            v7);
        }
        NetBufferList->Status = v7;
        NdisFSendNetBufferListsComplete(a1->hMiniport, NetBufferList, 0);
      }
      v5 = Alignment;
      NetBufferList = Alignment;
    }
    while ( Alignment );
    v2 = v14;
  }
  NdisReleaseRWLock(a1->pRWLock, &LockState);
  for ( i = v2 == 0; ; i = v10 == 0 )
  {
    NetBufferList = v2;
    if ( i )
      break;
    pDot11Driver = a1->pDot11Driver;
    v10 = (struct _NET_BUFFER_LIST *)v2->Link.Alignment;
    v2->Link.Alignment = 0;
    if ( a1->FIPSContext.bSafeMode || !pDot11Driver->Dot11SendHandleLocal )
      pDot11Driver->Dot11SendHandle(a1->pVElanExt, &NetBufferList, 1u);
    else
      pDot11Driver->Dot11SendHandleLocal(a1->pVElanExt, &NetBufferList, 1u, &v11);
    v2 = v10;
  }
  Dot11FlushIntermediateSendQueue(a1);
  v16 = 0;
  LODWORD(v14) = 0;
  if ( (_DWORD)v11 )
  {
    LODWORD(v11) = 0;
    Dot11FlushIntermediateSendQueueWithoutLock(a1, (__int64)&v16);
  }
}

```

## disassembly

```asm
0x14000d2e0  push    rbp
0x14000d2e2  push    rbx
0x14000d2e3  push    rsi
0x14000d2e4  push    rdi
0x14000d2e5  mov     rbp, rsp
0x14000d2e8  sub     rsp, 58h
0x14000d2ec  xor     ebx, ebx
0x14000d2ee  mov     [rbp+NetBufferList], rdx
0x14000d2f2  xor     eax, eax
0x14000d2f4  mov     [rbp+arg_8], rbx
0x14000d2f8  mov     rdi, rcx
0x14000d2fb  mov     [rbp+arg_18], rbx
0x14000d2ff  mov     rcx, [rcx+90h]; Lock
0x14000d306  lea     rdx, [rbp+LockState]; LockState
0x14000d30a  xorps   xmm0, xmm0
0x14000d30d  mov     [rbp+LockState.OldIrql], bl
0x14000d310  xor     r8d, r8d; Flags
0x14000d313  mov     word ptr [rbp+LockState.LockState], ax
0x14000d317  movups  [rbp+var_28], xmm0
0x14000d31b  mov     [rbp+var_18], rax
0x14000d31f  call    cs:__imp_NdisAcquireRWLockRead
0x14000d326  nop     dword ptr [rax+rax+00h]
0x14000d32b  mov     rax, [rbp+NetBufferList]
0x14000d32f  test    rax, rax
0x14000d332  jz      loc_14000D3D2
0x14000d338  mov     rsi, [rax]
0x14000d33b  lea     r9, [rbp+arg_18]; struct _NET_BUFFER_LIST **
0x14000d33f  mov     qword ptr [rax], 0
0x14000d346  lea     r8, [rbp+arg_8]; struct _NET_BUFFER_LIST **
0x14000d34a  mov     rdx, [rbp+NetBufferList]; struct _NET_BUFFER_LIST *
0x14000d34e  mov     rcx, rdi; struct _VELAN *
0x14000d351  call    ?MP6SendOneNBL@@YAHPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@PEAPEAU2@2@Z; MP6SendOneNBL(_VELAN *,_NET_BUFFER_LIST *,_NET_BUFFER_LIST * *,_NET_BUFFER_LIST * *)
0x14000d356  mov     ebx, eax
0x14000d358  cmp     eax, 103h
0x14000d35d  jz      short loc_14000D3BE
0x14000d35f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d366  lea     rax, WPP_GLOBAL_Control
0x14000d36d  cmp     rcx, rax
0x14000d370  jz      short loc_14000D39D
0x14000d372  cmp     byte ptr [rcx+29h], 4
0x14000d376  jb      short loc_14000D39D
0x14000d378  mov     edx, [rcx+2Ch]
0x14000d37b  test    dl, 40h
0x14000d37e  jz      short loc_14000D39D
0x14000d380  mov     r9, [rbp+NetBufferList]
0x14000d384  lea     r8, WPP_c867dd3d8fa430bb45808a98b994f216_Traceguids
0x14000d38b  mov     rcx, [rcx+18h]
0x14000d38f  mov     edx, 19h
0x14000d394  mov     dword ptr [rsp+58h+var_38], ebx
0x14000d398  call    WPP_SF_qD
0x14000d39d  mov     rax, [rbp+NetBufferList]
0x14000d3a1  xor     r8d, r8d; SendCompleteFlags
0x14000d3a4  mov     [rax+8Ch], ebx
0x14000d3aa  mov     rdx, [rbp+NetBufferList]; NetBufferList
0x14000d3ae  mov     rcx, [rdi+20h]; NdisFilterHandle
0x14000d3b2  call    cs:__imp_NdisFSendNetBufferListsComplete
0x14000d3b9  nop     dword ptr [rax+rax+00h]
0x14000d3be  mov     rax, rsi
0x14000d3c1  mov     [rbp+NetBufferList], rax
0x14000d3c5  test    rsi, rsi
0x14000d3c8  jnz     loc_14000D338
0x14000d3ce  mov     rbx, [rbp+arg_8]
0x14000d3d2  mov     rcx, [rdi+90h]; Lock
0x14000d3d9  lea     rdx, [rbp+LockState]; LockState
0x14000d3dd  call    cs:__imp_NdisReleaseRWLock
0x14000d3e4  nop     dword ptr [rax+rax+00h]
0x14000d3e9  test    rbx, rbx
0x14000d3ec  jmp     short loc_14000D44F
0x14000d3ee  mov     rax, [rdi+98h]
0x14000d3f5  mov     rsi, [rbx]
0x14000d3f8  mov     qword ptr [rbx], 0
0x14000d3ff  cmp     dword ptr [rdi+15F8h], 0
0x14000d406  jnz     short loc_14000D430
0x14000d408  mov     r10, [rax+8]
0x14000d40c  test    r10, r10
0x14000d40f  jz      short loc_14000D430
0x14000d411  mov     rcx, [rdi+1F68h]
0x14000d418  lea     r9, [rbp+var_28]
0x14000d41c  mov     r8d, 1
0x14000d422  lea     rdx, [rbp+NetBufferList]
0x14000d426  mov     rax, r10
0x14000d429  call    _guard_dispatch_icall
0x14000d42e  jmp     short loc_14000D449
0x14000d430  mov     rax, [rax]
0x14000d433  lea     rdx, [rbp+NetBufferList]
0x14000d437  mov     rcx, [rdi+1F68h]
0x14000d43e  mov     r8d, 1
0x14000d444  call    _guard_dispatch_icall
0x14000d449  mov     rbx, rsi
0x14000d44c  test    rsi, rsi
0x14000d44f  mov     [rbp+NetBufferList], rbx
0x14000d453  jnz     short loc_14000D3EE
0x14000d455  mov     rcx, rdi; struct _VELAN *
0x14000d458  call    ?Dot11FlushIntermediateSendQueue@@YAXPEAU_VELAN@@@Z; Dot11FlushIntermediateSendQueue(_VELAN *)
0x14000d45d  mov     edx, dword ptr [rbp+var_28]
0x14000d460  mov     [rbp+arg_18], 0
0x14000d468  mov     dword ptr [rbp+arg_8], 0
0x14000d46f  test    edx, edx
0x14000d471  jz      short loc_14000D493
0x14000d473  mov     r8, qword ptr [rbp+var_28+8]
0x14000d477  lea     rax, [rbp+arg_18]
0x14000d47b  lea     r9, [rbp+arg_8]
0x14000d47f  mov     [rsp+58h+var_38], rax; __int64
0x14000d484  mov     rcx, rdi; struct _VELAN *
0x14000d487  mov     dword ptr [rbp+var_28], 0
0x14000d48e  call    Dot11FlushIntermediateSendQueueWithoutLock
0x14000d493  add     rsp, 58h
0x14000d497  pop     rdi
0x14000d498  pop     rsi
0x14000d499  pop     rbx
0x14000d49a  pop     rbp
0x14000d49b  retn
```
