# QosNblCadDisassemble

- ea: `0x1400148a0`
- end: `0x140014b67`
- name: `QosNblCadDisassemble`
- size: `711`
- prototype: `__int64 __usercall@<rax>(PNET_BUFFER_LIST SrcNetBufferList@<rcx>, int, __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140014d6c`

## callees

- `0x1400097c8`
- `0x14000a168`
- `0x1400148a0`
- `0x140014cc4`
- `0x140016700`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140014927`
- `ntoskrnl!KeInitializeSpinLock` at `0x140014927`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140014aca`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140014aca`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140014b2b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140014b2b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140014b40`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140014b40`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140014ad8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140014ad8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140014a12`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140014a12`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400148f1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400148f1`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140014993`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140014993`
- `NDIS!NdisFreeNetBufferList` at `0x140014a35`
- `NDIS!NdisFreeNetBufferList` at `0x140014a35`
- `NDIS!NdisAllocateNetBufferList` at `0x140014979`
- `NDIS!NdisAllocateNetBufferList` at `0x140014979`

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
0x1400148a0  mov     r11, rsp
0x1400148a3  mov     [r11+8], rbx
0x1400148a7  mov     [r11+18h], r8d
0x1400148ab  mov     [r11+10h], rdx
0x1400148af  push    rbp
0x1400148b0  push    rsi
0x1400148b1  push    rdi
0x1400148b2  push    r12
0x1400148b4  push    r13
0x1400148b6  push    r14
0x1400148b8  push    r15
0x1400148ba  sub     rsp, 40h
0x1400148be  mov     rsi, [rsp+78h+arg_28]
0x1400148c6  xor     eax, eax
0x1400148c8  xorps   xmm0, xmm0
0x1400148cb  xorps   xmm1, xmm1
0x1400148ce  mov     rbp, rcx
0x1400148d1  mov     r15d, r9d
0x1400148d4  mov     rcx, cs:QosgNblCadLookasideList; Lookaside
0x1400148db  mov     ebx, r8d
0x1400148de  movups  xmmword ptr [rsi], xmm1
0x1400148e1  mov     [rsi+10h], rax
0x1400148e5  mov     r13, rdx
0x1400148e8  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x1400148ed  mov     [r11-48h], rax
0x1400148f1  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400148f8  nop     dword ptr [rax+rax+00h]
0x1400148fd  mov     rdi, rax
0x140014900  test    rax, rax
0x140014903  jnz     short loc_14001490F
0x140014905  mov     ebx, 0C000009Ah
0x14001490a  jmp     loc_140014A1E
0x14001490f  xorps   xmm0, xmm0
0x140014912  lea     rcx, [rdi+10h]; SpinLock
0x140014916  movups  xmmword ptr [rdi], xmm0
0x140014919  xor     eax, eax
0x14001491b  movups  xmmword ptr [rdi+10h], xmm0
0x14001491f  movups  xmmword ptr [rdi+20h], xmm0
0x140014923  mov     [rdi+30h], rax
0x140014927  call    cs:__imp_KeInitializeSpinLock
0x14001492e  nop     dword ptr [rax+rax+00h]
0x140014933  lea     rax, [rdi+20h]
0x140014937  xor     edx, edx
0x140014939  mov     [rax+8], rax
0x14001493d  mov     rcx, rbp
0x140014940  mov     [rax], rax
0x140014943  mov     [rdi+18h], rbp
0x140014947  call    QosGetNetBufferCount
0x14001494c  lea     r14d, [rdx+1]
0x140014950  sub     eax, ebx
0x140014952  jz      short loc_140014962
0x140014954  lea     r14d, [r15+1]
0x140014958  cmp     r15d, 0FFFFFFFFh
0x14001495c  jnz     short loc_140014962
0x14001495e  lea     r14d, [rax+1]
0x140014962  xor     r12d, r12d
0x140014965  cmp     r12d, r14d
0x140014968  jnb     loc_140014A43
0x14001496e  mov     rcx, [r13+28h]; PoolHandle
0x140014972  xor     r8d, r8d; ContextBackFill
0x140014975  lea     edx, [r8+70h]; ContextSize
0x140014979  call    cs:__imp_NdisAllocateNetBufferList
0x140014980  nop     dword ptr [rax+rax+00h]
0x140014985  mov     r13, rax
0x140014988  test    rax, rax
0x14001498b  jz      short loc_140014A03
0x14001498d  mov     rdx, rbp; SrcNetBufferList
0x140014990  mov     rcx, rax; DestNetBufferList
0x140014993  call    cs:__imp_NdisCopySendNetBufferListInfo
0x14001499a  nop     dword ptr [rax+rax+00h]
0x14001499f  mov     rcx, [rsp+78h+arg_8]
0x1400149a7  xor     edx, edx; Val
0x1400149a9  mov     rax, [rcx+20h]
0x1400149ad  lea     r8d, [rdx+70h]; Size
0x1400149b1  mov     rcx, [r13+10h]
0x1400149b5  mov     [r13+78h], rax
0x1400149b9  movzx   ebx, word ptr [rcx+0Ah]
0x1400149bd  add     rbx, rcx
0x1400149c0  lea     rcx, [rbx+10h]; void *
0x1400149c4  call    memset
0x1400149c9  mov     rax, [rsp+78h+arg_8]
0x1400149d1  mov     r8, r13
0x1400149d4  mov     rdx, [rsi+8]
0x1400149d8  mov     rcx, rsi
0x1400149db  mov     [rbx+30h], rax
0x1400149df  mov     [rbx+20h], rdi
0x1400149e3  mov     [rbx+28h], r13
0x1400149e7  mov     dword ptr [rbx+38h], 0
0x1400149ee  call    QosNblChainInsert
0x1400149f3  mov     r13, [rsp+78h+arg_8]
0x1400149fb  inc     r12d
0x1400149fe  jmp     loc_140014965
0x140014a03  mov     rcx, cs:QosgNblCadLookasideList; Lookaside
0x140014a0a  mov     rdx, rdi; Entry
0x140014a0d  mov     ebx, 0C000009Ah
0x140014a12  call    cs:__imp_ExFreeToNPagedLookasideList
0x140014a19  nop     dword ptr [rax+rax+00h]
0x140014a1e  mov     r8, [rsi]
0x140014a21  test    r8, r8
0x140014a24  jz      loc_140014B4C
0x140014a2a  mov     rcx, rsi
0x140014a2d  call    QosNblChainRemove
0x140014a32  mov     rcx, rax; NetBufferList
0x140014a35  call    cs:__imp_NdisFreeNetBufferList
0x140014a3c  nop     dword ptr [rax+rax+00h]
0x140014a41  jmp     short loc_140014A1E
0x140014a43  mov     rax, [rbp+8]
0x140014a47  xor     r14d, r14d
0x140014a4a  mov     rdx, [rsi]
0x140014a4d  mov     r8d, r14d
0x140014a50  mov     ebx, [rsp+78h+arg_10]
0x140014a57  mov     [rdx+8], rax
0x140014a5b  mov     eax, r14d
0x140014a5e  mov     [rbp+8], r14
0x140014a62  mov     rcx, [rdx+8]
0x140014a66  test    ebx, ebx
0x140014a68  jz      short loc_140014A76
0x140014a6a  inc     eax
0x140014a6c  mov     r8, rcx
0x140014a6f  mov     rcx, [rcx]
0x140014a72  cmp     eax, ebx
0x140014a74  jb      short loc_140014A6A
0x140014a76  mov     [r8], r14
0x140014a79  mov     rdx, [rdx]
0x140014a7c  test    rdx, rdx
0x140014a7f  jz      short loc_140014AA9
0x140014a81  cmp     r15d, 1
0x140014a85  jnz     short loc_140014A8D
0x140014a87  mov     [rdx+8], rcx
0x140014a8b  jmp     short loc_140014AAD
0x140014a8d  test    rcx, rcx
0x140014a90  jz      short loc_140014AAD
0x140014a92  mov     rax, [rcx]
0x140014a95  mov     [rdx+8], rcx
0x140014a99  mov     [rcx], r14
0x140014a9c  mov     rcx, rax
0x140014a9f  mov     rdx, [rdx]
0x140014aa2  test    rax, rax
0x140014aa5  jnz     short loc_140014A92
0x140014aa7  jmp     short loc_140014AAD
0x140014aa9  mov     [rbp+8], rcx
0x140014aad  mov     eax, [rsi+10h]
0x140014ab0  lock add [rdi+30h], eax
0x140014ab4  mov     bpl, [rsp+78h+arg_30]
0x140014abc  lea     rcx, [rdi+10h]; SpinLock
0x140014ac0  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x140014ac5  test    bpl, bpl
0x140014ac8  jz      short loc_140014AD8
0x140014aca  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140014ad1  nop     dword ptr [rax+rax+00h]
0x140014ad6  jmp     short loc_140014AE4
0x140014ad8  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140014adf  nop     dword ptr [rax+rax+00h]
0x140014ae4  mov     r8, [rsi]
0x140014ae7  test    r8, r8
0x140014aea  jz      short loc_140014B1E
0x140014aec  add     rdi, 20h ; ' '
0x140014af0  mov     r9, [rdi+8]
0x140014af4  cmp     [r9], rdi
0x140014af7  jnz     short loc_140014B39
0x140014af9  mov     rcx, [r8+10h]
0x140014afd  movzx   eax, word ptr [rcx+0Ah]
0x140014b01  lea     rdx, [rcx+10h]
0x140014b05  add     rdx, rax
0x140014b08  mov     [rdx], rdi
0x140014b0b  mov     [rdx+8], r9
0x140014b0f  mov     [r9], rdx
0x140014b12  mov     [rdi+8], rdx
0x140014b16  mov     r8, [r8]
0x140014b19  test    r8, r8
0x140014b1c  jnz     short loc_140014AF0
0x140014b1e  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140014b23  mov     ebx, r14d
0x140014b26  test    bpl, bpl
0x140014b29  jz      short loc_140014B40
0x140014b2b  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140014b32  nop     dword ptr [rax+rax+00h]
0x140014b37  jmp     short loc_140014B4C
0x140014b39  mov     ecx, 3
0x140014b3e  int     29h; Win8: RtlFailFast(ecx)
0x140014b40  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140014b47  nop     dword ptr [rax+rax+00h]
0x140014b4c  mov     eax, ebx
0x140014b4e  mov     rbx, [rsp+78h+arg_0]
0x140014b56  add     rsp, 40h
0x140014b5a  pop     r15
0x140014b5c  pop     r14
0x140014b5e  pop     r13
0x140014b60  pop     r12
0x140014b62  pop     rdi
0x140014b63  pop     rsi
0x140014b64  pop     rbp
0x140014b65  retn
```
