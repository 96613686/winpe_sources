# MP6SendNBLInternal(_VELAN *,_NET_BUFFER_LIST *)

- ea: `0x14000d2f0`
- end: `0x14000d4ad`
- name: `?MP6SendNBLInternal@@YAXPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@@Z`
- size: `445`
- prototype: `void __fastcall(struct _VELAN *, struct _NET_BUFFER_LIST *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400377f0`

## callees

- `0x14000d2f0`
- `0x14000d78c`
- `0x14000dfa8`
- `0x14000e188`
- `0x140019314`
- `0x14009a410`

## import_xrefs

- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000d3c2`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x14000d3c2`
- `NDIS!NdisReleaseRWLock` at `0x14000d3ed`
- `NDIS!NdisReleaseRWLock` at `0x14000d3ed`
- `NDIS!NdisAcquireRWLockRead` at `0x14000d32f`
- `NDIS!NdisAcquireRWLockRead` at `0x14000d32f`

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
0x14000d2f0  push    rbp
0x14000d2f2  push    rbx
0x14000d2f3  push    rsi
0x14000d2f4  push    rdi
0x14000d2f5  mov     rbp, rsp
0x14000d2f8  sub     rsp, 58h
0x14000d2fc  xor     ebx, ebx
0x14000d2fe  mov     [rbp+NetBufferList], rdx
0x14000d302  xor     eax, eax
0x14000d304  mov     [rbp+arg_8], rbx
0x14000d308  mov     rdi, rcx
0x14000d30b  mov     [rbp+arg_18], rbx
0x14000d30f  mov     rcx, [rcx+90h]; Lock
0x14000d316  lea     rdx, [rbp+LockState]; LockState
0x14000d31a  xorps   xmm0, xmm0
0x14000d31d  mov     [rbp+LockState.OldIrql], bl
0x14000d320  xor     r8d, r8d; Flags
0x14000d323  mov     word ptr [rbp+LockState.LockState], ax
0x14000d327  movups  [rbp+var_28], xmm0
0x14000d32b  mov     [rbp+var_18], rax
0x14000d32f  call    cs:__imp_NdisAcquireRWLockRead
0x14000d336  nop     dword ptr [rax+rax+00h]
0x14000d33b  mov     rax, [rbp+NetBufferList]
0x14000d33f  test    rax, rax
0x14000d342  jz      loc_14000D3E2
0x14000d348  mov     rsi, [rax]
0x14000d34b  lea     r9, [rbp+arg_18]; struct _NET_BUFFER_LIST **
0x14000d34f  mov     qword ptr [rax], 0
0x14000d356  lea     r8, [rbp+arg_8]; struct _NET_BUFFER_LIST **
0x14000d35a  mov     rdx, [rbp+NetBufferList]; struct _NET_BUFFER_LIST *
0x14000d35e  mov     rcx, rdi; struct _VELAN *
0x14000d361  call    ?MP6SendOneNBL@@YAHPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@PEAPEAU2@2@Z; MP6SendOneNBL(_VELAN *,_NET_BUFFER_LIST *,_NET_BUFFER_LIST * *,_NET_BUFFER_LIST * *)
0x14000d366  mov     ebx, eax
0x14000d368  cmp     eax, 103h
0x14000d36d  jz      short loc_14000D3CE
0x14000d36f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d376  lea     rax, WPP_GLOBAL_Control
0x14000d37d  cmp     rcx, rax
0x14000d380  jz      short loc_14000D3AD
0x14000d382  cmp     byte ptr [rcx+29h], 4
0x14000d386  jb      short loc_14000D3AD
0x14000d388  mov     edx, [rcx+2Ch]
0x14000d38b  test    dl, 40h
0x14000d38e  jz      short loc_14000D3AD
0x14000d390  mov     r9, [rbp+NetBufferList]
0x14000d394  lea     r8, WPP_c867dd3d8fa430bb45808a98b994f216_Traceguids
0x14000d39b  mov     rcx, [rcx+18h]
0x14000d39f  mov     edx, 19h
0x14000d3a4  mov     dword ptr [rsp+58h+var_38], ebx
0x14000d3a8  call    WPP_SF_qD
0x14000d3ad  mov     rax, [rbp+NetBufferList]
0x14000d3b1  xor     r8d, r8d; SendCompleteFlags
0x14000d3b4  mov     [rax+8Ch], ebx
0x14000d3ba  mov     rdx, [rbp+NetBufferList]; NetBufferList
0x14000d3be  mov     rcx, [rdi+20h]; NdisFilterHandle
0x14000d3c2  call    cs:__imp_NdisFSendNetBufferListsComplete
0x14000d3c9  nop     dword ptr [rax+rax+00h]
0x14000d3ce  mov     rax, rsi
0x14000d3d1  mov     [rbp+NetBufferList], rax
0x14000d3d5  test    rsi, rsi
0x14000d3d8  jnz     loc_14000D348
0x14000d3de  mov     rbx, [rbp+arg_8]
0x14000d3e2  mov     rcx, [rdi+90h]; Lock
0x14000d3e9  lea     rdx, [rbp+LockState]; LockState
0x14000d3ed  call    cs:__imp_NdisReleaseRWLock
0x14000d3f4  nop     dword ptr [rax+rax+00h]
0x14000d3f9  test    rbx, rbx
0x14000d3fc  jmp     short loc_14000D45F
0x14000d3fe  mov     rax, [rdi+98h]
0x14000d405  mov     rsi, [rbx]
0x14000d408  mov     qword ptr [rbx], 0
0x14000d40f  cmp     dword ptr [rdi+15F8h], 0
0x14000d416  jnz     short loc_14000D440
0x14000d418  mov     r10, [rax+8]
0x14000d41c  test    r10, r10
0x14000d41f  jz      short loc_14000D440
0x14000d421  mov     rcx, [rdi+1F68h]
0x14000d428  lea     r9, [rbp+var_28]
0x14000d42c  mov     r8d, 1
0x14000d432  lea     rdx, [rbp+NetBufferList]
0x14000d436  mov     rax, r10
0x14000d439  call    _guard_dispatch_icall
0x14000d43e  jmp     short loc_14000D459
0x14000d440  mov     rax, [rax]
0x14000d443  lea     rdx, [rbp+NetBufferList]
0x14000d447  mov     rcx, [rdi+1F68h]
0x14000d44e  mov     r8d, 1
0x14000d454  call    _guard_dispatch_icall
0x14000d459  mov     rbx, rsi
0x14000d45c  test    rsi, rsi
0x14000d45f  mov     [rbp+NetBufferList], rbx
0x14000d463  jnz     short loc_14000D3FE
0x14000d465  mov     rcx, rdi; struct _VELAN *
0x14000d468  call    ?Dot11FlushIntermediateSendQueue@@YAXPEAU_VELAN@@@Z; Dot11FlushIntermediateSendQueue(_VELAN *)
0x14000d46d  mov     edx, dword ptr [rbp+var_28]
0x14000d470  mov     [rbp+arg_18], 0
0x14000d478  mov     dword ptr [rbp+arg_8], 0
0x14000d47f  test    edx, edx
0x14000d481  jz      short loc_14000D4A3
0x14000d483  mov     r8, qword ptr [rbp+var_28+8]
0x14000d487  lea     rax, [rbp+arg_18]
0x14000d48b  lea     r9, [rbp+arg_8]
0x14000d48f  mov     [rsp+58h+var_38], rax; __int64
0x14000d494  mov     rcx, rdi; struct _VELAN *
0x14000d497  mov     dword ptr [rbp+var_28], 0
0x14000d49e  call    Dot11FlushIntermediateSendQueueWithoutLock
0x14000d4a3  add     rsp, 58h
0x14000d4a7  pop     rdi
0x14000d4a8  pop     rsi
0x14000d4a9  pop     rbx
0x14000d4aa  pop     rbp
0x14000d4ab  retn
```
