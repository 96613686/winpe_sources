# PcQoSPQueryTrafficClass

- ea: `0x140009350`
- end: `0x140009850`
- name: `PcQoSPQueryTrafficClass`
- size: `1280`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140009350`
- `0x140009860`
- `0x14000eb54`
- `0x14000f48c`
- `0x14000f508`
- `0x140011500`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400095a1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400095a1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009549`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009549`
- `NDIS!NdisIfGetInterfaceIndexFromNetLuid` at `0x1400093c3`
- `NDIS!NdisIfGetInterfaceIndexFromNetLuid` at `0x14000948c`
- `NDIS!NdisIfGetInterfaceIndexFromNetLuid` at `0x1400093c3`
- `NDIS!NdisIfGetInterfaceIndexFromNetLuid` at `0x14000948c`
- `NDIS!NdisAcquireRWLockRead` at `0x1400093f5`
- `NDIS!NdisAcquireRWLockRead` at `0x1400094b7`
- `NDIS!NdisAcquireRWLockRead` at `0x1400093f5`
- `NDIS!NdisAcquireRWLockRead` at `0x1400094b7`
- `NDIS!NdisReleaseRWLock` at `0x140009435`
- `NDIS!NdisReleaseRWLock` at `0x140009518`
- `NDIS!NdisReleaseRWLock` at `0x1400096e5`
- `NDIS!NdisReleaseRWLock` at `0x1400097db`
- `NDIS!NdisReleaseRWLock` at `0x140009435`
- `NDIS!NdisReleaseRWLock` at `0x140009518`
- `NDIS!NdisReleaseRWLock` at `0x1400096e5`
- `NDIS!NdisReleaseRWLock` at `0x1400097db`

## pseudocode

```c
char __fastcall PcQoSPQueryTrafficClass(__int64 *a1)
{
  __int64 v2; // rsi
  NET_LUID v3; // rbx
  __int64 v4; // r13
  unsigned __int16 v5; // r12
  __int64 *v6; // rax
  __int64 *v7; // rcx
  int v8; // r14d
  __int64 *v9; // rax
  __int64 *v10; // rcx
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  int v14; // eax
  bool v15; // zf
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+38h] [rbp-39h] BYREF
  __int128 v21; // [rsp+50h] [rbp-21h] BYREF
  __int128 v22; // [rsp+60h] [rbp-11h]
  _OWORD v23[2]; // [rsp+70h] [rbp-1h] BYREF
  unsigned __int8 v24; // [rsp+D8h] [rbp+67h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+E0h] [rbp+6Fh] BYREF
  ULONG pIfIndex; // [rsp+E8h] [rbp+77h] BYREF

  v2 = *(_QWORD *)(*a1 + 168);
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    if ( PcgEventTraceEnabled )
    {
      v17 = *(_QWORD *)(*a1 + 248) & 0x7FFFFFFFFFFFFFFFLL;
      if ( v17 )
        PcpEtwTransferFlowActivity(v17, v2, 1);
    }
  }
  v3.Value = a1[1];
  v4 = *a1;
  v5 = (*(_DWORD *)(v2 + 48) >> 14) & 1;
  v24 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  pIfIndex = 0;
  if ( NdisIfGetInterfaceIndexFromNetLuid(v3, &pIfIndex) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_i)(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_263d9268693f357b83e9029a6246d0a9_Traceguids,
        (NET_LUID)v3.Value);
    }
  }
  else
  {
    *(_WORD *)&LockState.OldIrql = 0;
    LockState.Flags = 0;
    NdisAcquireRWLockRead(PcgFilterDriverContext, &LockState, 0);
    v6 = (__int64 *)qword_140018828;
    while ( v6 != &qword_140018828 )
    {
      v7 = v6;
      v6 = (__int64 *)*v6;
      if ( *((_DWORD *)v7 + 24) == pIfIndex )
      {
        v8 = *((_DWORD *)v7 + 5);
        NdisReleaseRWLock(PcgFilterDriverContext, &LockState);
        goto LABEL_7;
      }
    }
    NdisReleaseRWLock(PcgFilterDriverContext, &LockState);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_i)(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_263d9268693f357b83e9029a6246d0a9_Traceguids,
        (NET_LUID)v3.Value);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_i)(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      WPP_3643923c9bd13e596b9957c4c416ef65_Traceguids,
      (NET_LUID)v3.Value);
  }
  v8 = 0;
LABEL_7:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_d142f05ff1783a702b1695b6c61349f7_Traceguids);
  }
  memset(v23, 0, 28);
  v21 = 0;
  v22 = 0;
  if ( v8 == 9 )
  {
    pIfIndex = 0;
    v5 |= 2u;
    if ( NdisIfGetInterfaceIndexFromNetLuid(v3, &pIfIndex) )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      {
        v18 = 10;
LABEL_53:
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_i)(
          v16->AttachedDevice,
          v18,
          WPP_263d9268693f357b83e9029a6246d0a9_Traceguids,
          (NET_LUID)v3.Value);
      }
    }
    else
    {
      *(_WORD *)&LockState.OldIrql = 0;
      LockState.Flags = 0;
      NdisAcquireRWLockRead(PcgFilterDriverContext, &LockState, 0);
      v9 = (__int64 *)qword_140018828;
      while ( v9 != &qword_140018828 )
      {
        v10 = v9;
        v9 = (__int64 *)*v9;
        if ( *((_DWORD *)v10 + 24) == pIfIndex )
        {
          v11 = *(_OWORD *)((char *)v10 + 230);
          v21 = *(_OWORD *)((char *)v10 + 214);
          v12 = *(_OWORD *)((char *)v10 + 246);
          v22 = v11;
          v13 = *(_OWORD *)((char *)v10 + 258);
          v23[0] = v12;
          *(_OWORD *)((char *)v23 + 12) = v13;
          NdisReleaseRWLock(PcgFilterDriverContext, &LockState);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              11,
              WPP_3643923c9bd13e596b9957c4c416ef65_Traceguids,
              (unsigned __int8)v21);
          }
          goto LABEL_16;
        }
      }
      NdisReleaseRWLock(PcgFilterDriverContext, &LockState);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      {
        v18 = 11;
        goto LABEL_53;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_3643923c9bd13e596b9957c4c416ef65_Traceguids);
    }
  }
LABEL_16:
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v2 + 96), &LockHandle);
  while ( *(_DWORD *)(v2 + 104) )
    ;
  QosMrkComputeMarking(v2 + 136, (unsigned int)&v21, v4, v5, (__int64)&v24, (__int64)a1 + 17);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  LOBYTE(v14) = v24 >> 2;
  v15 = PcgAllowAppDSCPMarking == 0;
  *((_BYTE *)a1 + 16) = v24 >> 2;
  if ( v15 )
  {
    v14 = *(_DWORD *)(v2 + 48);
    if ( (((unsigned __int8)v14 - 2) & 0xFFFFFFFD) != 0 )
      *((_BYTE *)a1 + 16) = 0;
  }
  return v14;
}

```

## disassembly

```asm
0x140009350  mov     rax, rsp
0x140009353  push    rbp
0x140009354  push    rsi
0x140009355  push    rdi
0x140009356  lea     rbp, [rax-5Fh]
0x14000935a  sub     rsp, 0B0h
0x140009361  mov     [rax+20h], rbx
0x140009365  mov     rdi, rcx
0x140009368  mov     [rax-20h], r12
0x14000936c  mov     [rax-28h], r13
0x140009370  mov     [rax-30h], r14
0x140009374  mov     rax, [rcx]
0x140009377  mov     rsi, [rax+0A8h]
0x14000937e  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140009384  test    eax, eax
0x140009386  jnz     loc_140009690
0x14000938c  mov     r12d, [rsi+30h]
0x140009390  lea     rdx, [rbp+57h+pIfIndex]; pIfIndex
0x140009394  mov     rbx, [rdi+8]
0x140009398  xor     eax, eax
0x14000939a  mov     r13, [rdi]
0x14000939d  xorps   xmm0, xmm0
0x1400093a0  shr     r12d, 0Eh
0x1400093a4  mov     rcx, rbx; NetLuid
0x1400093a7  and     r12w, 1
0x1400093ac  mov     [rsp+0C0h+var_30], r15
0x1400093b4  mov     [rbp+57h+arg_0], 0
0x1400093b8  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x1400093bc  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x1400093c0  mov     [rbp+57h+pIfIndex], eax
0x1400093c3  call    cs:__imp_NdisIfGetInterfaceIndexFromNetLuid
0x1400093ca  nop     dword ptr [rax+rax+00h]
0x1400093cf  lea     r14, WPP_GLOBAL_Control
0x1400093d6  test    eax, eax
0x1400093d8  jnz     loc_140009638
0x1400093de  mov     rcx, cs:PcgFilterDriverContext; Lock
0x1400093e5  lea     rdx, [rbp+57h+LockState]; LockState
0x1400093e9  xor     eax, eax
0x1400093eb  xor     r8d, r8d; Flags
0x1400093ee  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x1400093f2  mov     [rbp+57h+LockState.Flags], al
0x1400093f5  call    cs:__imp_NdisAcquireRWLockRead
0x1400093fc  nop     dword ptr [rax+rax+00h]
0x140009401  mov     rax, cs:qword_140018828
0x140009408  lea     r15, qword_140018828
0x14000940f  mov     edx, [rbp+57h+pIfIndex]
0x140009412  cmp     rax, r15
0x140009415  jz      loc_1400096DA
0x14000941b  mov     rcx, rax
0x14000941e  mov     rax, [rax]
0x140009421  cmp     [rcx+60h], edx
0x140009424  jnz     short loc_140009412
0x140009426  mov     r14d, [rcx+14h]
0x14000942a  lea     rdx, [rbp+57h+LockState]; LockState
0x14000942e  mov     rcx, cs:PcgFilterDriverContext; Lock
0x140009435  call    cs:__imp_NdisReleaseRWLock
0x14000943c  nop     dword ptr [rax+rax+00h]
0x140009441  mov     rcx, cs:WPP_GLOBAL_Control
0x140009448  lea     rax, WPP_GLOBAL_Control
0x14000944f  cmp     rcx, rax
0x140009452  jz      short loc_14000945E
0x140009454  cmp     byte ptr [rcx+29h], 4
0x140009458  jnb     loc_14000975F
0x14000945e  xorps   xmm0, xmm0
0x140009461  xor     eax, eax
0x140009463  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x140009467  movups  xmmword ptr [rbp+57h+var_58+0Ch], xmm0
0x14000946b  movups  [rbp+57h+var_78], xmm0
0x14000946f  movups  [rbp+57h+var_68], xmm0
0x140009473  cmp     r14d, 9
0x140009477  jnz     loc_140009541
0x14000947d  lea     rdx, [rbp+57h+pIfIndex]; pIfIndex
0x140009481  mov     [rbp+57h+pIfIndex], eax
0x140009484  mov     rcx, rbx; NetLuid
0x140009487  or      r12w, 2
0x14000948c  call    cs:__imp_NdisIfGetInterfaceIndexFromNetLuid
0x140009493  nop     dword ptr [rax+rax+00h]
0x140009498  test    eax, eax
0x14000949a  jnz     loc_1400095E0
0x1400094a0  mov     rcx, cs:PcgFilterDriverContext; Lock
0x1400094a7  lea     rdx, [rbp+57h+LockState]; LockState
0x1400094ab  xor     eax, eax
0x1400094ad  xor     r8d, r8d; Flags
0x1400094b0  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x1400094b4  mov     [rbp+57h+LockState.Flags], al
0x1400094b7  call    cs:__imp_NdisAcquireRWLockRead
0x1400094be  nop     dword ptr [rax+rax+00h]
0x1400094c3  mov     rax, cs:qword_140018828
0x1400094ca  mov     edx, [rbp+57h+pIfIndex]
0x1400094cd  cmp     rax, r15
0x1400094d0  jz      loc_1400097D0
0x1400094d6  mov     rcx, rax
0x1400094d9  mov     rax, [rax]
0x1400094dc  cmp     [rcx+60h], edx
0x1400094df  jnz     short loc_1400094CD
0x1400094e1  movups  xmm0, xmmword ptr [rcx+0D6h]
0x1400094e8  lea     rdx, [rbp+57h+LockState]; LockState
0x1400094ec  movups  xmm1, xmmword ptr [rcx+0E6h]
0x1400094f3  movups  [rbp+57h+var_78], xmm0
0x1400094f7  movups  xmm0, xmmword ptr [rcx+0F6h]
0x1400094fe  movups  [rbp+57h+var_68], xmm1
0x140009502  movups  xmm1, xmmword ptr [rcx+102h]
0x140009509  mov     rcx, cs:PcgFilterDriverContext; Lock
0x140009510  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x140009514  movups  xmmword ptr [rbp+57h+var_58+0Ch], xmm1
0x140009518  call    cs:__imp_NdisReleaseRWLock
0x14000951f  nop     dword ptr [rax+rax+00h]
0x140009524  mov     rcx, cs:WPP_GLOBAL_Control
0x14000952b  lea     rax, WPP_GLOBAL_Control
0x140009532  cmp     rcx, rax
0x140009535  jz      short loc_140009541
0x140009537  cmp     byte ptr [rcx+29h], 5
0x14000953b  jnb     loc_1400097A4
0x140009541  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x140009545  lea     rcx, [rsi+60h]; SpinLock
0x140009549  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140009550  nop     dword ptr [rax+rax+00h]
0x140009555  mov     r15, [rsp+0C0h+var_30]
0x14000955d  mov     r14, [rsp+0C0h+var_28]
0x140009565  mov     eax, [rsi+68h]
0x140009568  test    eax, eax
0x14000956a  jnz     short loc_140009565
0x14000956c  mov     rbx, [rsp+0C0h+arg_18]
0x140009574  lea     rax, [rdi+11h]
0x140009578  mov     [rsp+28h], rax
0x14000957d  lea     rcx, [rsi+88h]
0x140009584  lea     rax, [rbp+57h+arg_0]
0x140009588  movzx   r9d, r12w
0x14000958c  mov     r8, r13
0x14000958f  mov     [rsp+0C0h+var_A0], rax
0x140009594  lea     rdx, [rbp+57h+var_78]
0x140009598  call    QosMrkComputeMarking
0x14000959d  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x1400095a1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400095a8  nop     dword ptr [rax+rax+00h]
0x1400095ad  movzx   eax, [rbp+57h+arg_0]
0x1400095b1  mov     r13, [rsp+0C0h+var_20]
0x1400095b9  mov     r12, [rsp+0A8h]
0x1400095c1  shr     al, 2
0x1400095c4  cmp     cs:PcgAllowAppDSCPMarking, 0
0x1400095cb  mov     [rdi+10h], al
0x1400095ce  jz      loc_140009832
0x1400095d4  add     rsp, 0B0h
0x1400095db  pop     rdi
0x1400095dc  pop     rsi
0x1400095dd  pop     rbp
0x1400095de  retn
0x1400095e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400095e7  lea     r14, WPP_GLOBAL_Control
0x1400095ee  cmp     rcx, r14
0x1400095f1  jnz     loc_140009786
0x1400095f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400095fe  cmp     rcx, r14
0x140009601  jz      loc_140009541
0x140009607  cmp     byte ptr [rcx+29h], 2
0x14000960b  jb      loc_140009541
0x140009611  test    dword ptr [rcx+2Ch], 800h
0x140009618  jz      loc_140009541
0x14000961e  mov     rcx, [rcx+18h]
0x140009622  lea     r8, WPP_3643923c9bd13e596b9957c4c416ef65_Traceguids
0x140009629  mov     edx, 0Ch
0x14000962e  call    WPP_SF_
0x140009633  jmp     loc_140009541
0x140009638  mov     rcx, cs:WPP_GLOBAL_Control
0x14000963f  cmp     rcx, r14
0x140009642  jnz     loc_1400096CE
0x140009648  lea     r15, qword_140018828
0x14000964f  mov     rcx, cs:WPP_GLOBAL_Control
0x140009656  cmp     rcx, r14
0x140009659  jz      short loc_140009665
0x14000965b  cmp     byte ptr [rcx+29h], 2
0x14000965f  jnb     loc_140009735
0x140009665  xor     r14d, r14d
0x140009668  jmp     loc_140009441
0x14000966d  test    dword ptr [rcx+2Ch], 800h
0x140009674  jz      short loc_140009648
0x140009676  mov     rcx, [rcx+18h]
0x14000967a  lea     r8, WPP_263d9268693f357b83e9029a6246d0a9_Traceguids
0x140009681  mov     edx, 0Ch
0x140009686  mov     r9, rbx
0x140009689  call    WPP_SF_i
0x14000968e  jmp     short loc_140009648
0x140009690  mov     eax, cs:PcgEventTraceEnabled
0x140009696  test    eax, eax
0x140009698  jz      loc_14000938C
0x14000969e  mov     rax, [rcx]
0x1400096a1  mov     rdx, 7FFFFFFFFFFFFFFFh
0x1400096ab  mov     rcx, [rax+0F8h]
0x1400096b2  and     rcx, rdx
0x1400096b5  jz      loc_14000938C
0x1400096bb  mov     r8d, 1
0x1400096c1  mov     rdx, rsi
0x1400096c4  call    PcpEtwTransferFlowActivity
0x1400096c9  jmp     loc_14000938C
0x1400096ce  cmp     byte ptr [rcx+29h], 2
0x1400096d2  jb      loc_140009648
0x1400096d8  jmp     short loc_14000966D
0x1400096da  mov     rcx, cs:PcgFilterDriverContext; Lock
0x1400096e1  lea     rdx, [rbp+57h+LockState]; LockState
0x1400096e5  call    cs:__imp_NdisReleaseRWLock
0x1400096ec  nop     dword ptr [rax+rax+00h]
0x1400096f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400096f8  cmp     rcx, r14
0x1400096fb  jz      loc_14000964F
0x140009701  cmp     byte ptr [rcx+29h], 2
0x140009705  jb      loc_14000964F
0x14000970b  test    dword ptr [rcx+2Ch], 800h
0x140009712  jz      loc_14000964F
0x140009718  mov     rcx, [rcx+18h]
0x14000971c  lea     r8, WPP_263d9268693f357b83e9029a6246d0a9_Traceguids
0x140009723  mov     edx, 0Dh
0x140009728  mov     r9, rbx
0x14000972b  call    WPP_SF_i
0x140009730  jmp     loc_14000964F
0x140009735  test    dword ptr [rcx+2Ch], 800h
0x14000973c  jz      loc_140009665
0x140009742  mov     rcx, [rcx+18h]
0x140009746  lea     r8, WPP_3643923c9bd13e596b9957c4c416ef65_Traceguids
0x14000974d  mov     edx, 0Ah
0x140009752  mov     r9, rbx
0x140009755  call    WPP_SF_i
0x14000975a  jmp     loc_140009665
0x14000975f  test    dword ptr [rcx+2Ch], 800h
0x140009766  jz      loc_14000945E
0x14000976c  mov     rcx, [rcx+18h]
0x140009770  lea     r8, WPP_d142f05ff1783a702b1695b6c61349f7_Traceguids
0x140009777  mov     edx, 0Ah
0x14000977c  call    WPP_SF_
0x140009781  jmp     loc_14000945E
0x140009786  cmp     byte ptr [rcx+29h], 2
0x14000978a  jb      loc_1400095F7
0x140009790  test    dword ptr [rcx+2Ch], 800h
0x140009797  jz      loc_1400095F7
0x14000979d  mov     edx, 0Ah
0x1400097a2  jmp     short loc_14000981A
0x1400097a4  test    dword ptr [rcx+2Ch], 800h
0x1400097ab  jz      loc_140009541
0x1400097b1  movzx   r9d, byte ptr [rbp+57h+var_78]
0x1400097b6  lea     r8, WPP_3643923c9bd13e596b9957c4c416ef65_Traceguids
0x1400097bd  mov     rcx, [rcx+18h]
0x1400097c1  mov     edx, 0Bh
0x1400097c6  call    WPP_SF_D
0x1400097cb  jmp     loc_140009541
0x1400097d0  mov     rcx, cs:PcgFilterDriverContext; Lock
0x1400097d7  lea     rdx, [rbp+57h+LockState]; LockState
0x1400097db  call    cs:__imp_NdisReleaseRWLock
0x1400097e2  nop     dword ptr [rax+rax+00h]
0x1400097e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400097ee  lea     r14, WPP_GLOBAL_Control
0x1400097f5  cmp     rcx, r14
0x1400097f8  jz      loc_1400095F7
0x1400097fe  cmp     byte ptr [rcx+29h], 2
0x140009802  jb      loc_1400095F7
0x140009808  test    dword ptr [rcx+2Ch], 800h
0x14000980f  jz      loc_1400095F7
0x140009815  mov     edx, 0Bh
0x14000981a  mov     rcx, [rcx+18h]
0x14000981e  lea     r8, WPP_263d9268693f357b83e9029a6246d0a9_Traceguids
0x140009825  mov     r9, rbx
0x140009828  call    WPP_SF_i
0x14000982d  jmp     loc_1400095F7
0x140009832  mov     eax, [rsi+30h]
0x140009835  movzx   ecx, al
0x140009838  sub     ecx, 2
0x14000983b  test    ecx, 0FFFFFFFDh
0x140009841  jz      loc_1400095D4
0x140009847  mov     byte ptr [rdi+10h], 0
0x14000984b  jmp     loc_1400095D4
```
