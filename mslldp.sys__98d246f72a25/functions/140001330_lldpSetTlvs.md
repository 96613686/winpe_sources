# lldpSetTlvs

- ea: `0x140001330`
- end: `0x140001651`
- name: `lldpSetTlvs`
- size: `801`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140001230`
- `0x14000f360`
- `0x140011914`

## callees

- `0x140001330`
- `0x140001660`
- `0x140001690`
- `0x140001a90`
- `0x1400025d8`
- `0x140003f20`
- `0x140012180`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400015aa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400015aa`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140001608`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140001608`
- `ntoskrnl!KeCancelTimer` at `0x140001571`
- `ntoskrnl!KeCancelTimer` at `0x140001571`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400015d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400015d8`
- `NDIS!NdisReleaseRWLock` at `0x1400013d2`
- `NDIS!NdisReleaseRWLock` at `0x1400014c3`
- `NDIS!NdisReleaseRWLock` at `0x140001627`
- `NDIS!NdisReleaseRWLock` at `0x1400013d2`
- `NDIS!NdisReleaseRWLock` at `0x1400014c3`
- `NDIS!NdisReleaseRWLock` at `0x140001627`
- `NDIS!NdisAcquireRWLockWrite` at `0x140001380`
- `NDIS!NdisAcquireRWLockWrite` at `0x140001380`

## pseudocode

```c
__int64 __fastcall lldpSetTlvs(char *Context, unsigned int *a2, unsigned __int8 a3)
{
  unsigned int v6; // r10d
  unsigned int v7; // r11d
  __int64 i; // r9
  int v9; // eax
  int v10; // r9d
  unsigned int v11; // r11d
  char *v12; // rbp
  char *v13; // rsi
  __int16 v14; // r14
  __int64 j; // r15
  int v16; // r14d
  unsigned int v17; // edi
  char v18; // al
  struct _NDIS_RW_LOCK_EX *v19; // rcx
  char v20; // si
  signed __int32 v21; // eax
  signed __int32 v22; // ett
  signed __int32 v23; // eax
  signed __int32 v24; // ett
  int v25; // ecx
  int v26; // ecx
  signed __int32 v27; // eax
  signed __int32 v28; // ett
  __int64 k; // rax
  _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+20h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( !(unsigned __int8)lldpValidateTlvArray(a2, a3) )
    return 3221225485LL;
  if ( !*a2 )
    return 0;
  NdisAcquireRWLockWrite(*((PNDIS_RW_LOCK_EX *)Context + 122), &LockState, 0);
  v6 = *a2;
  v7 = 2;
  for ( i = 0; (unsigned int)i < v6; i = (unsigned int)(v10 + 1) )
  {
    v9 = lldpWireSizeOfTlv(&a2[4 * i + 1 + (unsigned int)i]);
    if ( v9 + v11 < v11 )
    {
      NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)Context + 122), &LockState);
      return 3221225621LL;
    }
    v7 = v9 + v11;
  }
  v12 = &Context[*((unsigned int *)Context + 247) + 996];
  v13 = Context + 996;
LABEL_11:
  if ( v13 + 2 < v12 && (v14 = *(_WORD *)v13, (*(_WORD *)v13 & 0xFE) != 0) )
  {
    for ( j = 0; (unsigned int)j < v6; j = (unsigned int)(j + 1) )
    {
      if ( (unsigned __int8)lldpTlvTypeMatch(v13, &a2[4 * j + 1 + (unsigned int)j]) )
      {
        v16 = v14 & 1;
LABEL_20:
        v13 += 256 * v16 + (unsigned int)(unsigned __int8)v13[1] + 2;
        goto LABEL_11;
      }
    }
    v16 = v14 & 1;
    if ( (unsigned __int8)v13[1] + v7 + (v16 << 8) + 2 >= v7 )
    {
      v7 += (unsigned __int8)v13[1] + (v16 << 8) + 2;
      goto LABEL_20;
    }
    v17 = -1073741675;
  }
  else
  {
    if ( v7 <= *((_DWORD *)Context + 35) )
    {
      v18 = lldpMergeTlvsWithMib(Context + 984, a2);
      v19 = (struct _NDIS_RW_LOCK_EX *)*((_QWORD *)Context + 122);
      v20 = v18;
      Context[151] = v18;
      NdisReleaseRWLock(v19, &LockState);
      _m_prefetchw(Context + 52);
      v21 = *((_DWORD *)Context + 13);
      do
      {
        v22 = v21;
        v21 = _InterlockedCompareExchange((volatile signed __int32 *)Context + 13, v21, v21);
      }
      while ( v22 != v21 );
      if ( (unsigned int)(v21 - 4) > 1 )
        goto LABEL_35;
      _m_prefetchw(Context + 304);
      v23 = *((_DWORD *)Context + 76);
      do
      {
        v24 = v23;
        v23 = _InterlockedCompareExchange((volatile signed __int32 *)Context + 76, v23, v23);
      }
      while ( v24 != v23 );
      if ( v23 || (v25 = *((_DWORD *)Context + 62)) == 0 || (v26 = v25 - 1) != 0 && v26 != 2 )
      {
LABEL_35:
        KeCancelTimer((PKTIMER)(Context + 584));
        if ( _InterlockedExchange((volatile __int32 *)Context + 215, 0) )
          lldpTxSendShutdownPacket(Context);
      }
      else
      {
        _m_prefetchw(Context + 876);
        v27 = *((_DWORD *)Context + 219);
        do
        {
          v28 = v27;
          v27 = _InterlockedCompareExchange((volatile signed __int32 *)Context + 219, v27, v27);
        }
        while ( v28 != v27 );
        _InterlockedExchange((volatile __int32 *)Context + 215, 1);
        lldpSetPeriodicTimer((PKTIMER)(Context + 584));
      }
      v17 = 0;
      if ( v20 && *((_QWORD *)Context + 11) )
      {
        Context[80] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 9);
        for ( k = *((_QWORD *)Context + 11); k; k = *(_QWORD *)(k + 8) )
          _InterlockedOr((volatile signed __int32 *)(k + 32), 1u);
        KeReleaseSpinLock((PKSPIN_LOCK)Context + 9, Context[80]);
        if ( !_InterlockedExchange((volatile __int32 *)Context + 24, 1) )
        {
          _InterlockedIncrement((volatile signed __int32 *)Context + 12);
          IoQueueWorkItemEx(*((PIO_WORKITEM *)Context + 13), lldpDeliverChangeNotifications, DelayedWorkQueue, Context);
        }
      }
      return v17;
    }
    v17 = -1073741298;
  }
  NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)Context + 122), &LockState);
  return v17;
}

```

## disassembly

```asm
0x140001330  push    rbx
0x140001332  push    rdi
0x140001333  sub     rsp, 28h
0x140001337  mov     rdi, rdx
0x14000133a  xor     eax, eax
0x14000133c  mov     rbx, rcx
0x14000133f  mov     word ptr [rsp+38h+LockState.OldIrql], ax
0x140001344  mov     rcx, rdi
0x140001347  mov     [rsp+38h+LockState.Flags], al
0x14000134b  movzx   edx, r8b
0x14000134f  call    lldpValidateTlvArray
0x140001354  test    al, al
0x140001356  jnz     short loc_140001365
0x140001358  mov     eax, 0C000000Dh
0x14000135d  add     rsp, 28h
0x140001361  pop     rdi
0x140001362  pop     rbx
0x140001363  retn
0x140001365  cmp     dword ptr [rdi], 0
0x140001368  jnz     short loc_140001371
0x14000136a  xor     eax, eax
0x14000136c  jmp     loc_140001649
0x140001371  mov     rcx, [rbx+3D0h]; Lock
0x140001378  lea     rdx, [rsp+38h+LockState]; LockState
0x14000137d  xor     r8d, r8d; Flags
0x140001380  call    cs:__imp_NdisAcquireRWLockWrite
0x140001387  nop     dword ptr [rax+rax+00h]
0x14000138c  mov     r10d, [rdi]
0x14000138f  mov     r11d, 2
0x140001395  xor     r9d, r9d
0x140001398  cmp     r9d, r10d
0x14000139b  jnb     short loc_1400013E8
0x14000139d  mov     ecx, r9d
0x1400013a0  inc     rcx
0x1400013a3  lea     rcx, [rcx+r9*4]
0x1400013a7  lea     rcx, [rdi+rcx*4]
0x1400013ab  call    lldpWireSizeOfTlv
0x1400013b0  lea     ecx, [rax+r11]
0x1400013b4  cmp     ecx, r11d
0x1400013b7  jb      short loc_1400013C1
0x1400013b9  mov     r11d, ecx
0x1400013bc  inc     r9d
0x1400013bf  jmp     short loc_140001398
0x1400013c1  mov     rcx, [rbx+3D0h]; Lock
0x1400013c8  lea     rdx, [rsp+38h+LockState]; LockState
0x1400013cd  mov     edi, 0C0000095h
0x1400013d2  call    cs:__imp_NdisReleaseRWLock
0x1400013d9  nop     dword ptr [rax+rax+00h]
0x1400013de  mov     eax, edi
0x1400013e0  add     rsp, 28h
0x1400013e4  pop     rdi
0x1400013e5  pop     rbx
0x1400013e6  retn
0x1400013e8  mov     eax, [rbx+3DCh]
0x1400013ee  mov     [rsp+38h+arg_0], rbp
0x1400013f3  lea     rbp, [rbx+3E4h]
0x1400013fa  mov     [rsp+38h+arg_8], rsi
0x1400013ff  add     rbp, rax
0x140001402  mov     [rsp+38h+var_18], r15
0x140001407  lea     rsi, [rbx+3E4h]
0x14000140e  mov     [rsp+38h+arg_10], r14
0x140001413  lea     rax, [rsi+2]
0x140001417  cmp     rax, rbp
0x14000141a  jnb     short loc_140001492
0x14000141c  movzx   r14d, word ptr [rsi]
0x140001420  test    r14b, 0FEh
0x140001424  jz      short loc_140001492
0x140001426  xor     r15d, r15d
0x140001429  cmp     r15d, r10d
0x14000142c  jnb     short loc_140001453
0x14000142e  mov     ecx, r15d
0x140001431  inc     rcx
0x140001434  lea     rcx, [rcx+r15*4]
0x140001438  lea     rdx, [rdi+rcx*4]
0x14000143c  mov     rcx, rsi
0x14000143f  call    lldpTlvTypeMatch
0x140001444  test    al, al
0x140001446  jnz     short loc_14000144D
0x140001448  inc     r15d
0x14000144b  jmp     short loc_140001429
0x14000144d  and     r14d, 1
0x140001451  jmp     short loc_140001471
0x140001453  movzx   ecx, byte ptr [rsi+1]
0x140001457  and     r14d, 1
0x14000145b  mov     edx, r14d
0x14000145e  shl     edx, 8
0x140001461  add     edx, 2
0x140001464  add     edx, r11d
0x140001467  add     edx, ecx
0x140001469  cmp     edx, r11d
0x14000146c  jb      short loc_140001488
0x14000146e  mov     r11d, edx
0x140001471  movzx   eax, byte ptr [rsi+1]
0x140001475  add     rsi, 2
0x140001479  shl     r14d, 8
0x14000147d  add     r14d, eax
0x140001480  mov     eax, r14d
0x140001483  add     rsi, rax
0x140001486  jmp     short loc_140001413
0x140001488  mov     edi, 0C0000095h
0x14000148d  jmp     loc_14000161B
0x140001492  cmp     r11d, [rbx+8Ch]
0x140001499  ja      loc_140001616
0x14000149f  mov     rdx, rdi
0x1400014a2  lea     rcx, [rbx+3D8h]
0x1400014a9  call    lldpMergeTlvsWithMib
0x1400014ae  mov     rcx, [rbx+3D0h]; Lock
0x1400014b5  lea     rdx, [rsp+38h+LockState]; LockState
0x1400014ba  movzx   esi, al
0x1400014bd  mov     [rbx+97h], al
0x1400014c3  call    cs:__imp_NdisReleaseRWLock
0x1400014ca  nop     dword ptr [rax+rax+00h]
0x1400014cf  prefetchw byte ptr [rbx+34h]
0x1400014d3  mov     eax, [rbx+34h]
0x1400014d6  mov     ecx, eax
0x1400014d8  lock cmpxchg [rbx+34h], ecx
0x1400014dd  jnz     short loc_1400014D6
0x1400014df  sub     eax, 4
0x1400014e2  jz      short loc_1400014ED
0x1400014e4  cmp     eax, 1
0x1400014e7  jnz     loc_14000156A
0x1400014ed  prefetchw byte ptr [rbx+130h]
0x1400014f4  mov     eax, [rbx+130h]
0x1400014fa  mov     ecx, eax
0x1400014fc  lock cmpxchg [rbx+130h], ecx
0x140001504  jnz     short loc_1400014FA
0x140001506  test    eax, eax
0x140001508  jnz     short loc_14000156A
0x14000150a  mov     ecx, [rbx+0F8h]
0x140001510  test    ecx, ecx
0x140001512  jz      short loc_14000156A
0x140001514  sub     ecx, 1
0x140001517  jz      short loc_140001523
0x140001519  sub     ecx, 1
0x14000151c  jz      short loc_14000156A
0x14000151e  cmp     ecx, 1
0x140001521  jnz     short loc_14000156A
0x140001523  prefetchw byte ptr [rbx+36Ch]
0x14000152a  mov     eax, [rbx+36Ch]
0x140001530  mov     ecx, eax
0x140001532  lock cmpxchg [rbx+36Ch], ecx
0x14000153a  jnz     short loc_140001530
0x14000153c  test    eax, eax
0x14000153e  mov     edx, 10Ch
0x140001543  mov     eax, 1
0x140001548  mov     ecx, 100h
0x14000154d  cmovnz  ecx, edx
0x140001550  mov     r8b, 1
0x140001553  mov     edx, [rbx+rcx]
0x140001556  lea     rcx, [rbx+248h]; Timer
0x14000155d  xchg    eax, [rbx+35Ch]
0x140001563  call    lldpSetPeriodicTimer
0x140001568  jmp     short loc_140001591
0x14000156a  lea     rcx, [rbx+248h]; PKTIMER
0x140001571  call    cs:__imp_KeCancelTimer
0x140001578  nop     dword ptr [rax+rax+00h]
0x14000157d  xor     eax, eax
0x14000157f  xchg    eax, [rbx+35Ch]
0x140001585  test    eax, eax
0x140001587  jz      short loc_140001591
0x140001589  mov     rcx, rbx
0x14000158c  call    lldpTxSendShutdownPacket
0x140001591  xor     edi, edi
0x140001593  test    sil, sil
0x140001596  jz      loc_140001633
0x14000159c  cmp     [rbx+58h], rdi
0x1400015a0  jz      loc_140001633
0x1400015a6  lea     rcx, [rbx+48h]; SpinLock
0x1400015aa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400015b1  nop     dword ptr [rax+rax+00h]
0x1400015b6  mov     [rbx+50h], al
0x1400015b9  mov     rax, [rbx+58h]
0x1400015bd  test    rax, rax
0x1400015c0  jz      short loc_1400015D0
0x1400015c2  lock or dword ptr [rax+20h], 1
0x1400015c7  mov     rax, [rax+8]
0x1400015cb  test    rax, rax
0x1400015ce  jnz     short loc_1400015C2
0x1400015d0  movzx   edx, byte ptr [rbx+50h]; NewIrql
0x1400015d4  lea     rcx, [rbx+48h]; SpinLock
0x1400015d8  call    cs:__imp_KeReleaseSpinLock
0x1400015df  nop     dword ptr [rax+rax+00h]
0x1400015e4  mov     eax, 1
0x1400015e9  xchg    eax, [rbx+60h]
0x1400015ec  test    eax, eax
0x1400015ee  jnz     short loc_140001633
0x1400015f0  lock inc dword ptr [rbx+30h]
0x1400015f4  mov     rcx, [rbx+68h]; IoWorkItem
0x1400015f8  lea     rdx, lldpDeliverChangeNotifications; WorkerRoutine
0x1400015ff  mov     r9, rbx; Context
0x140001602  mov     r8d, 1; QueueType
0x140001608  call    cs:__imp_IoQueueWorkItemEx
0x14000160f  nop     dword ptr [rax+rax+00h]
0x140001614  jmp     short loc_140001633
0x140001616  mov     edi, 0C000020Eh
0x14000161b  mov     rcx, [rbx+3D0h]; Lock
0x140001622  lea     rdx, [rsp+38h+LockState]; LockState
0x140001627  call    cs:__imp_NdisReleaseRWLock
0x14000162e  nop     dword ptr [rax+rax+00h]
0x140001633  mov     r14, [rsp+38h+arg_10]
0x140001638  mov     eax, edi
0x14000163a  mov     rsi, [rsp+38h+arg_8]
0x14000163f  mov     rbp, [rsp+38h+arg_0]
0x140001644  mov     r15, [rsp+38h+var_18]
0x140001649  add     rsp, 28h
0x14000164d  pop     rdi
0x14000164e  pop     rbx
0x14000164f  retn
```
