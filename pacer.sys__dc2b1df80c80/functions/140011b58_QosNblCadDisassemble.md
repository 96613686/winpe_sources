# QosNblCadDisassemble

- ea: `0x140011b58`
- end: `0x140011e1f`
- name: `QosNblCadDisassemble`
- size: `711`
- prototype: `__int64 __usercall@<rax>(PNET_BUFFER_LIST SrcNetBufferList@<rcx>, int, __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400121c8`

## callees

- `0x140007f60`
- `0x140009b50`
- `0x140011b58`
- `0x140011f7c`
- `0x140013600`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140011df8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140011df8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140011de3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140011de3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140011d82`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140011d82`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011bdf`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011bdf`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140011d90`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140011d90`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140011cca`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140011cca`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140011ba9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140011ba9`
- `NDIS!NdisAllocateNetBufferList` at `0x140011c31`
- `NDIS!NdisAllocateNetBufferList` at `0x140011c31`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140011c4b`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140011c4b`
- `NDIS!NdisFreeNetBufferList` at `0x140011ced`
- `NDIS!NdisFreeNetBufferList` at `0x140011ced`

## pseudocode

```c
__int64 __fastcall QosNblCadDisassemble(
        PNET_BUFFER_LIST SrcNetBufferList,
        __int64 a2,
        unsigned int a3,
        int a4,
        int a5,
        __int64 *a6,
        char a7)
{
  struct _NPAGED_LOOKASIDE_LIST *v9; // rcx
  __int64 v11; // r13
  KSPIN_LOCK *v12; // rax
  KSPIN_LOCK *v13; // rdi
  unsigned int v14; // ebx
  int NetBufferCount; // eax
  int v16; // edx
  unsigned int v17; // r14d
  int v18; // eax
  unsigned int i; // r12d
  struct _NET_BUFFER_LIST *NetBufferList; // rax
  struct _NET_BUFFER_LIST *v21; // r13
  PNET_BUFFER_LIST_CONTEXT Context; // rcx
  __int64 v23; // rbx
  __int64 v24; // rdx
  struct _NET_BUFFER_LIST *v25; // rax
  __int64 v26; // rdx
  _QWORD *v27; // r8
  unsigned int v28; // eax
  _QWORD *j; // rcx
  _QWORD *v30; // rdx
  _QWORD *v31; // rax
  KSPIN_LOCK *v32; // rcx
  _QWORD *v33; // r8
  char *v34; // rdi
  char **v35; // r9
  char *v36; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-58h] BYREF

  v9 = QosgNblCadLookasideList;
  *(_OWORD *)a6 = 0;
  a6[2] = 0;
  v11 = a2;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v12 = (KSPIN_LOCK *)ExAllocateFromNPagedLookasideList(v9);
  v13 = v12;
  if ( v12 )
  {
    *(_OWORD *)v12 = 0;
    *((_OWORD *)v12 + 1) = 0;
    *((_OWORD *)v12 + 2) = 0;
    v12[6] = 0;
    KeInitializeSpinLock(v12 + 2);
    v13[5] = (KSPIN_LOCK)(v13 + 4);
    v13[4] = (KSPIN_LOCK)(v13 + 4);
    v13[3] = (KSPIN_LOCK)SrcNetBufferList;
    NetBufferCount = QosGetNetBufferCount(SrcNetBufferList, 0);
    v17 = v16 + 1;
    v18 = NetBufferCount - a3;
    if ( v18 )
    {
      v17 = a4 + 1;
      if ( a4 == -1 )
        v17 = v18 + 1;
    }
    for ( i = 0; i < v17; ++i )
    {
      NetBufferList = NdisAllocateNetBufferList(*(NDIS_HANDLE *)(v11 + 40), 0x70u, 0);
      v21 = NetBufferList;
      if ( !NetBufferList )
      {
        v14 = -1073741670;
        ExFreeToNPagedLookasideList(QosgNblCadLookasideList, v13);
        goto LABEL_11;
      }
      NdisCopySendNetBufferListInfo(NetBufferList, SrcNetBufferList);
      Context = v21->Context;
      v21->SourceHandle = *(NDIS_HANDLE *)(a2 + 32);
      v23 = (__int64)Context + Context->Offset;
      memset((void *)(v23 + 16), 0, 0x70u);
      v24 = a6[1];
      *(_QWORD *)(v23 + 48) = a2;
      *(_QWORD *)(v23 + 32) = v13;
      *(_QWORD *)(v23 + 40) = v21;
      *(_DWORD *)(v23 + 56) = 0;
      QosNblChainInsert(a6, v24, v21);
      v11 = a2;
    }
    v26 = *a6;
    v27 = 0;
    *(_QWORD *)(v26 + 8) = SrcNetBufferList->FirstNetBuffer;
    v28 = 0;
    SrcNetBufferList->Link.Region = 0;
    for ( j = *(_QWORD **)(v26 + 8); v28 < a3; j = (_QWORD *)*j )
    {
      ++v28;
      v27 = j;
    }
    *v27 = 0;
    v30 = *(_QWORD **)v26;
    if ( v30 )
    {
      if ( a4 == 1 )
      {
        v30[1] = j;
      }
      else if ( j )
      {
        do
        {
          v31 = (_QWORD *)*j;
          v30[1] = j;
          *j = 0;
          j = v31;
          v30 = (_QWORD *)*v30;
        }
        while ( v31 );
      }
    }
    else
    {
      SrcNetBufferList->Link.Region = (ULONGLONG)j;
    }
    _InterlockedAdd((volatile signed __int32 *)v13 + 12, *((_DWORD *)a6 + 4));
    v32 = v13 + 2;
    if ( a7 )
      KeAcquireInStackQueuedSpinLockAtDpcLevel(v32, &LockHandle);
    else
      KeAcquireInStackQueuedSpinLock(v32, &LockHandle);
    v33 = (_QWORD *)*a6;
    if ( *a6 )
    {
      v34 = (char *)(v13 + 4);
      do
      {
        v35 = (char **)*((_QWORD *)v34 + 1);
        if ( *v35 != v34 )
          __fastfail(3u);
        v36 = (char *)(*(unsigned __int16 *)(v33[2] + 10LL) + v33[2] + 16LL);
        *(_QWORD *)v36 = v34;
        *((_QWORD *)v36 + 1) = v35;
        *v35 = v36;
        *((_QWORD *)v34 + 1) = v36;
        v33 = (_QWORD *)*v33;
      }
      while ( v33 );
    }
    v14 = 0;
    if ( a7 )
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    else
      KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  else
  {
    v14 = -1073741670;
LABEL_11:
    while ( *a6 )
    {
      v25 = (struct _NET_BUFFER_LIST *)QosNblChainRemove(a6);
      NdisFreeNetBufferList(v25);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x140011b58  mov     r11, rsp
0x140011b5b  mov     [r11+8], rbx
0x140011b5f  mov     [r11+18h], r8d
0x140011b63  mov     [r11+10h], rdx
0x140011b67  push    rbp
0x140011b68  push    rsi
0x140011b69  push    rdi
0x140011b6a  push    r12
0x140011b6c  push    r13
0x140011b6e  push    r14
0x140011b70  push    r15
0x140011b72  sub     rsp, 40h
0x140011b76  mov     rsi, [rsp+78h+arg_28]
0x140011b7e  xor     eax, eax
0x140011b80  xorps   xmm0, xmm0
0x140011b83  xorps   xmm1, xmm1
0x140011b86  mov     rbp, rcx
0x140011b89  mov     r15d, r9d
0x140011b8c  mov     rcx, cs:QosgNblCadLookasideList; Lookaside
0x140011b93  mov     ebx, r8d
0x140011b96  movups  xmmword ptr [rsi], xmm1
0x140011b99  mov     [rsi+10h], rax
0x140011b9d  mov     r13, rdx
0x140011ba0  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x140011ba5  mov     [r11-48h], rax
0x140011ba9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140011bb0  nop     dword ptr [rax+rax+00h]
0x140011bb5  mov     rdi, rax
0x140011bb8  test    rax, rax
0x140011bbb  jnz     short loc_140011BC7
0x140011bbd  mov     ebx, 0C000009Ah
0x140011bc2  jmp     loc_140011CD6
0x140011bc7  xorps   xmm0, xmm0
0x140011bca  lea     rcx, [rdi+10h]; SpinLock
0x140011bce  movups  xmmword ptr [rdi], xmm0
0x140011bd1  xor     eax, eax
0x140011bd3  movups  xmmword ptr [rdi+10h], xmm0
0x140011bd7  movups  xmmword ptr [rdi+20h], xmm0
0x140011bdb  mov     [rdi+30h], rax
0x140011bdf  call    cs:__imp_KeInitializeSpinLock
0x140011be6  nop     dword ptr [rax+rax+00h]
0x140011beb  lea     rax, [rdi+20h]
0x140011bef  xor     edx, edx
0x140011bf1  mov     [rax+8], rax
0x140011bf5  mov     rcx, rbp
0x140011bf8  mov     [rax], rax
0x140011bfb  mov     [rdi+18h], rbp
0x140011bff  call    QosGetNetBufferCount
0x140011c04  lea     r14d, [rdx+1]
0x140011c08  sub     eax, ebx
0x140011c0a  jz      short loc_140011C1A
0x140011c0c  lea     r14d, [r15+1]
0x140011c10  cmp     r15d, 0FFFFFFFFh
0x140011c14  jnz     short loc_140011C1A
0x140011c16  lea     r14d, [rax+1]
0x140011c1a  xor     r12d, r12d
0x140011c1d  cmp     r12d, r14d
0x140011c20  jnb     loc_140011CFB
0x140011c26  mov     rcx, [r13+28h]; PoolHandle
0x140011c2a  xor     r8d, r8d; ContextBackFill
0x140011c2d  lea     edx, [r8+70h]; ContextSize
0x140011c31  call    cs:__imp_NdisAllocateNetBufferList
0x140011c38  nop     dword ptr [rax+rax+00h]
0x140011c3d  mov     r13, rax
0x140011c40  test    rax, rax
0x140011c43  jz      short loc_140011CBB
0x140011c45  mov     rdx, rbp; SrcNetBufferList
0x140011c48  mov     rcx, rax; DestNetBufferList
0x140011c4b  call    cs:__imp_NdisCopySendNetBufferListInfo
0x140011c52  nop     dword ptr [rax+rax+00h]
0x140011c57  mov     rcx, [rsp+78h+arg_8]
0x140011c5f  xor     edx, edx; Val
0x140011c61  mov     rax, [rcx+20h]
0x140011c65  lea     r8d, [rdx+70h]; Size
0x140011c69  mov     rcx, [r13+10h]
0x140011c6d  mov     [r13+78h], rax
0x140011c71  movzx   ebx, word ptr [rcx+0Ah]
0x140011c75  add     rbx, rcx
0x140011c78  lea     rcx, [rbx+10h]; void *
0x140011c7c  call    memset
0x140011c81  mov     rax, [rsp+78h+arg_8]
0x140011c89  mov     r8, r13
0x140011c8c  mov     rdx, [rsi+8]
0x140011c90  mov     rcx, rsi
0x140011c93  mov     [rbx+30h], rax
0x140011c97  mov     [rbx+20h], rdi
0x140011c9b  mov     [rbx+28h], r13
0x140011c9f  mov     dword ptr [rbx+38h], 0
0x140011ca6  call    QosNblChainInsert
0x140011cab  mov     r13, [rsp+78h+arg_8]
0x140011cb3  inc     r12d
0x140011cb6  jmp     loc_140011C1D
0x140011cbb  mov     rcx, cs:QosgNblCadLookasideList; Lookaside
0x140011cc2  mov     rdx, rdi; Entry
0x140011cc5  mov     ebx, 0C000009Ah
0x140011cca  call    cs:__imp_ExFreeToNPagedLookasideList
0x140011cd1  nop     dword ptr [rax+rax+00h]
0x140011cd6  mov     r8, [rsi]
0x140011cd9  test    r8, r8
0x140011cdc  jz      loc_140011E04
0x140011ce2  mov     rcx, rsi
0x140011ce5  call    QosNblChainRemove
0x140011cea  mov     rcx, rax; NetBufferList
0x140011ced  call    cs:__imp_NdisFreeNetBufferList
0x140011cf4  nop     dword ptr [rax+rax+00h]
0x140011cf9  jmp     short loc_140011CD6
0x140011cfb  mov     rax, [rbp+8]
0x140011cff  xor     r14d, r14d
0x140011d02  mov     rdx, [rsi]
0x140011d05  mov     r8d, r14d
0x140011d08  mov     ebx, [rsp+78h+arg_10]
0x140011d0f  mov     [rdx+8], rax
0x140011d13  mov     eax, r14d
0x140011d16  mov     [rbp+8], r14
0x140011d1a  mov     rcx, [rdx+8]
0x140011d1e  test    ebx, ebx
0x140011d20  jz      short loc_140011D2E
0x140011d22  inc     eax
0x140011d24  mov     r8, rcx
0x140011d27  mov     rcx, [rcx]
0x140011d2a  cmp     eax, ebx
0x140011d2c  jb      short loc_140011D22
0x140011d2e  mov     [r8], r14
0x140011d31  mov     rdx, [rdx]
0x140011d34  test    rdx, rdx
0x140011d37  jz      short loc_140011D61
0x140011d39  cmp     r15d, 1
0x140011d3d  jnz     short loc_140011D45
0x140011d3f  mov     [rdx+8], rcx
0x140011d43  jmp     short loc_140011D65
0x140011d45  test    rcx, rcx
0x140011d48  jz      short loc_140011D65
0x140011d4a  mov     rax, [rcx]
0x140011d4d  mov     [rdx+8], rcx
0x140011d51  mov     [rcx], r14
0x140011d54  mov     rcx, rax
0x140011d57  mov     rdx, [rdx]
0x140011d5a  test    rax, rax
0x140011d5d  jnz     short loc_140011D4A
0x140011d5f  jmp     short loc_140011D65
0x140011d61  mov     [rbp+8], rcx
0x140011d65  mov     eax, [rsi+10h]
0x140011d68  lock add [rdi+30h], eax
0x140011d6c  mov     bpl, [rsp+78h+arg_30]
0x140011d74  lea     rcx, [rdi+10h]; SpinLock
0x140011d78  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x140011d7d  test    bpl, bpl
0x140011d80  jz      short loc_140011D90
0x140011d82  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140011d89  nop     dword ptr [rax+rax+00h]
0x140011d8e  jmp     short loc_140011D9C
0x140011d90  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140011d97  nop     dword ptr [rax+rax+00h]
0x140011d9c  mov     r8, [rsi]
0x140011d9f  test    r8, r8
0x140011da2  jz      short loc_140011DD6
0x140011da4  add     rdi, 20h ; ' '
0x140011da8  mov     r9, [rdi+8]
0x140011dac  cmp     [r9], rdi
0x140011daf  jnz     short loc_140011DF1
0x140011db1  mov     rcx, [r8+10h]
0x140011db5  movzx   eax, word ptr [rcx+0Ah]
0x140011db9  lea     rdx, [rcx+10h]
0x140011dbd  add     rdx, rax
0x140011dc0  mov     [rdx], rdi
0x140011dc3  mov     [rdx+8], r9
0x140011dc7  mov     [r9], rdx
0x140011dca  mov     [rdi+8], rdx
0x140011dce  mov     r8, [r8]
0x140011dd1  test    r8, r8
0x140011dd4  jnz     short loc_140011DA8
0x140011dd6  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140011ddb  mov     ebx, r14d
0x140011dde  test    bpl, bpl
0x140011de1  jz      short loc_140011DF8
0x140011de3  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140011dea  nop     dword ptr [rax+rax+00h]
0x140011def  jmp     short loc_140011E04
0x140011df1  mov     ecx, 3
0x140011df6  int     29h; Win8: RtlFailFast(ecx)
0x140011df8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140011dff  nop     dword ptr [rax+rax+00h]
0x140011e04  mov     eax, ebx
0x140011e06  mov     rbx, [rsp+78h+arg_0]
0x140011e0e  add     rsp, 40h
0x140011e12  pop     r15
0x140011e14  pop     r14
0x140011e16  pop     r13
0x140011e18  pop     r12
0x140011e1a  pop     rdi
0x140011e1b  pop     rsi
0x140011e1c  pop     rbp
0x140011e1d  retn
```
