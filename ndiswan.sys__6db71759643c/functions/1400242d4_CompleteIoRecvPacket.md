# CompleteIoRecvPacket

- ea: `0x1400242d4`
- end: `0x140024720`
- name: `CompleteIoRecvPacket`
- size: `1100`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002f620`

## callees

- `0x14000a290`
- `0x140010580`
- `0x1400161f0`
- `0x140016400`
- `0x1400242d4`
- `0x14002d570`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400244f6`
- `ntoskrnl!IofCompleteRequest` at `0x1400244f6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140024396`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140024396`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400244cc`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400246be`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400244cc`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400246be`
- `ntoskrnl!KeReleaseSpinLock` at `0x140024367`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400244e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400246d7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140024367`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400244e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400246d7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002437a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140024505`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400246e6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002437a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140024505`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400246e6`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x1400245bf`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x1400245bf`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x14002455e`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x14002455e`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140024591`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140024591`

## pseudocode

```c
__int64 __fastcall CompleteIoRecvPacket(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  int v5; // ebx
  IRP *v6; // r13
  __int64 v7; // rcx
  int v8; // edx
  struct _IRP *MasterIrp; // rbx
  int v10; // edi
  __int16 v11; // cx
  struct _NET_BUFFER_LIST *v12; // r10
  int v13; // ebx
  int v14; // ebx
  __int64 *v16; // rax
  unsigned int v17; // ebx
  __int64 v18; // [rsp+30h] [rbp-20h] BYREF
  __int64 v19; // [rsp+38h] [rbp-18h] BYREF
  int v20; // [rsp+40h] [rbp-10h]
  __int16 v21; // [rsp+44h] [rbp-Ch]

  v2 = *(_QWORD *)(a2 + 24);
  v19 = 0x5220FF5643455220LL;
  v20 = -11123899;
  v21 = -1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_52604c4400d53a16edd48a543f00e082_Traceguids);
  }
  v5 = *(_DWORD *)(a2 + 72);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 1768), *(_BYTE *)(a1 + 1776));
  byte_14001E3D8 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v2 + 736));
  if ( !*(_QWORD *)(v2 + 48)
    || *(_DWORD *)(v2 + 96)
    || !IoRecvList
    || (v6 = (IRP *)(qword_14001E308 - 168), !_InterlockedExchange64((volatile __int64 *)(qword_14001E308 - 64), 0)) )
  {
    if ( *(_DWORD *)(v2 + 20) == 2
      && ((*(_DWORD *)(*(_QWORD *)(v2 + 72) + 20LL) & 1) != 0 || *(_DWORD *)(v2 + 24) == 2)
      && *(_DWORD *)(v2 + 96) < 5u )
    {
      v16 = (__int64 *)qword_14001E340;
      if ( *(__int64 **)qword_14001E340 != &qword_14001E338 )
        goto LABEL_28;
      *(_QWORD *)(a2 + 8) = qword_14001E340;
      *(_QWORD *)a2 = &qword_14001E338;
      *v16 = a2;
      qword_14001E340 = a2;
      ++*(_DWORD *)(v2 + 96);
      if ( ++dword_14001E32C > (unsigned int)dword_14001E330 )
        dword_14001E330 = dword_14001E32C;
      v17 = 259;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_52604c4400d53a16edd48a543f00e082_Traceguids);
      }
      v17 = -1073741823;
    }
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v2 + 736));
    KeReleaseSpinLock(&SpinLock, byte_14001E3D8);
    *(_BYTE *)(a1 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 1768));
    return v17;
  }
  if ( *(__int64 **)(qword_14001E308 + 8) != &qword_14001E308
    || (v7 = *(_QWORD *)qword_14001E308, *(_QWORD *)(*(_QWORD *)qword_14001E308 + 8LL) != qword_14001E308) )
  {
LABEL_28:
    __fastfail(3u);
  }
  qword_14001E308 = *(_QWORD *)qword_14001E308;
  v8 = v5 + 14;
  *(_QWORD *)(v7 + 8) = &qword_14001E308;
  --IoRecvList;
  MasterIrp = v6->AssociatedIrp.MasterIrp;
  v10 = v6->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length - 31;
  MasterIrp->MdlAddress = *(PMDL *)(v2 + 48);
  *((_WORD *)&MasterIrp->Flags + 3) = 0;
  MasterIrp->Flags = 961456;
  if ( v8 <= v10 )
    v10 = v8;
  *((_WORD *)&MasterIrp->Flags + 2) = v10;
  v11 = *(_WORD *)(a2 + 56);
  BYTE5(v19) = *(_BYTE *)(v2 + 40);
  HIBYTE(v20) = BYTE5(v19);
  LOBYTE(v21) = HIBYTE(v11);
  HIBYTE(v21) = v11;
  MasterIrp->AssociatedIrp.MasterIrp = (struct _IRP *)v19;
  LODWORD(MasterIrp->ThreadListEntry.Flink) = v20;
  WORD2(MasterIrp->ThreadListEntry.Flink) = v21;
  memmove((char *)&MasterIrp->ThreadListEntry.Flink + 6, *(const void **)(a2 + 64), v10 - 14);
  v6->IoStatus.Status = 0;
  v6->IoStatus.Information = v10 + 31LL;
  dword_14001E324 = *(_DWORD *)&MasterIrp->Type;
  qword_14001E318 = (__int64)v6;
  dword_14001E320 = 0;
  dword_14001E328 = v6->IoStatus.Information;
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v2 + 736));
  KeReleaseSpinLock(&SpinLock, byte_14001E3D8);
  IofCompleteRequest(v6, 2);
  *(_BYTE *)(a1 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 1768));
  if ( qword_14001E2D8 || gbEnablePacketCapture && *(_BYTE *)(a1 + 2436) )
  {
    v12 = *(struct _NET_BUFFER_LIST **)(a2 + 104);
    v13 = *(_DWORD *)(a2 + 72);
    v18 = 0;
    v14 = v13 - *(_DWORD *)(v12->Link.Region + 24);
    if ( !NdisRetreatNetBufferListDataStart(v12, v14 + 14, 0, 0, 0) )
    {
      RtlCopyKernelBufferToMdl(
        &v19,
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 104) + 8LL) + 8LL),
        *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(a2 + 104) + 8LL) + 16LL),
        14,
        &v18);
      IndicatePromiscuousRecv(a1, a2, *(_QWORD *)(a2 + 104), 1);
      NdisAdvanceNetBufferListDataStart(*(PNET_BUFFER_LIST *)(a2 + 104), v14 + 14, 1u, 0);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_52604c4400d53a16edd48a543f00e082_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x1400242d4  mov     [rsp-38h+arg_10], rbx
0x1400242d9  push    rbp
0x1400242da  push    rsi
0x1400242db  push    rdi
0x1400242dc  push    r12
0x1400242de  push    r13
0x1400242e0  push    r14
0x1400242e2  push    r15
0x1400242e4  mov     rbp, rsp
0x1400242e7  sub     rsp, 50h
0x1400242eb  mov     rax, cs:__security_cookie
0x1400242f2  xor     rax, rsp
0x1400242f5  mov     [rbp+var_8], rax
0x1400242f9  mov     r14, [rdx+18h]
0x1400242fd  mov     rsi, rdx
0x140024300  mov     r15, rcx
0x140024303  mov     dword ptr [rbp+var_18], 43455220h
0x14002430a  mov     dword ptr [rbp+var_18+4], 5220FF56h
0x140024311  mov     [rbp+var_10], 0FF564345h
0x140024318  mov     [rbp+var_C], 0FFFFh
0x14002431e  mov     rcx, cs:WPP_GLOBAL_Control
0x140024325  lea     r13, WPP_GLOBAL_Control
0x14002432c  cmp     rcx, r13
0x14002432f  jz      short loc_140024353
0x140024331  mov     eax, [rcx+2Ch]
0x140024334  test    al, 10h
0x140024336  jz      short loc_140024353
0x140024338  cmp     byte ptr [rcx+29h], 5
0x14002433c  jb      short loc_140024353
0x14002433e  mov     rcx, [rcx+18h]
0x140024342  lea     r8, WPP_52604c4400d53a16edd48a543f00e082_Traceguids
0x140024349  mov     edx, 52h ; 'R'
0x14002434e  call    WPP_SF_
0x140024353  mov     dl, [r15+6F0h]; NewIrql
0x14002435a  lea     r12, [r15+6E8h]
0x140024361  mov     ebx, [rsi+48h]
0x140024364  mov     rcx, r12; SpinLock
0x140024367  call    cs:__imp_KeReleaseSpinLock
0x14002436e  nop     dword ptr [rax+rax+00h]
0x140024373  lea     rcx, SpinLock; SpinLock
0x14002437a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140024381  nop     dword ptr [rax+rax+00h]
0x140024386  lea     rdi, [r14+2E0h]
0x14002438d  mov     cs:byte_14001E3D8, al
0x140024393  mov     rcx, rdi; SpinLock
0x140024396  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14002439d  nop     dword ptr [rax+rax+00h]
0x1400243a2  xor     r8d, r8d
0x1400243a5  cmp     [r14+30h], r8
0x1400243a9  jz      loc_14002460E
0x1400243af  cmp     [r14+60h], r8d
0x1400243b3  ja      loc_14002460E
0x1400243b9  cmp     cs:IoRecvList, r8d
0x1400243c0  jz      loc_14002460E
0x1400243c6  mov     r13, cs:qword_14001E308
0x1400243cd  mov     eax, r8d
0x1400243d0  xchg    rax, [r13-40h]
0x1400243d4  add     r13, 0FFFFFFFFFFFFFF58h
0x1400243db  test    rax, rax
0x1400243de  jz      loc_140024607
0x1400243e4  mov     rax, cs:qword_14001E308
0x1400243eb  lea     r9, qword_14001E308
0x1400243f2  cmp     [rax+8], r9
0x1400243f6  jnz     loc_140024644
0x1400243fc  mov     rcx, [rax]
0x1400243ff  cmp     [rcx+8], rax
0x140024403  jnz     loc_140024644
0x140024409  mov     cs:qword_14001E308, rcx
0x140024410  lea     edx, [rbx+0Eh]
0x140024413  mov     [rcx+8], r9
0x140024417  dec     cs:IoRecvList
0x14002441d  mov     rax, [r13+0B8h]
0x140024424  mov     rbx, [r13+18h]
0x140024428  mov     edi, [rax+8]
0x14002442b  mov     rax, [r14+30h]
0x14002442f  add     edi, 0FFFFFFE1h
0x140024432  mov     [rbx+8], rax
0x140024436  cmp     edx, edi
0x140024438  mov     [rbx+16h], r8w
0x14002443d  mov     dword ptr [rbx+10h], 0EABB0h
0x140024444  cmovle  edi, edx
0x140024447  mov     [rbx+14h], di
0x14002444b  mov     al, [r14+28h]
0x14002444f  movzx   ecx, word ptr [rsi+38h]
0x140024453  mov     byte ptr [rbp+var_18+5], al
0x140024456  movsd   xmm0, [rbp+var_18]
0x14002445b  mov     byte ptr [rbp+var_10+3], al
0x14002445e  movzx   eax, cx
0x140024461  mov     byte ptr [rbp+var_C+1], cl
0x140024464  lea     rcx, [rbx+26h]; void *
0x140024468  shr     ax, 8
0x14002446c  mov     byte ptr [rbp+var_C], al
0x14002446f  movsd   qword ptr [rbx+18h], xmm0
0x140024474  mov     eax, [rbp+var_10]
0x140024477  mov     [rbx+20h], eax
0x14002447a  movzx   eax, [rbp+var_C]
0x14002447e  mov     [rbx+24h], ax
0x140024482  lea     eax, [rdi-0Eh]
0x140024485  mov     rdx, [rsi+40h]; Src
0x140024489  movsxd  r8, eax; Size
0x14002448c  call    memmove
0x140024491  mov     dword ptr [r13+30h], 0
0x140024499  lea     rcx, [r14+2E0h]; SpinLock
0x1400244a0  movsxd  rax, edi
0x1400244a3  xor     edi, edi
0x1400244a5  add     rax, 1Fh
0x1400244a9  mov     [r13+38h], rax
0x1400244ad  mov     eax, [rbx]
0x1400244af  mov     cs:dword_14001E324, eax
0x1400244b5  mov     cs:qword_14001E318, r13
0x1400244bc  mov     cs:dword_14001E320, edi
0x1400244c2  mov     eax, [r13+38h]
0x1400244c6  mov     cs:dword_14001E328, eax
0x1400244cc  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400244d3  nop     dword ptr [rax+rax+00h]
0x1400244d8  mov     dl, cs:byte_14001E3D8; NewIrql
0x1400244de  lea     rcx, SpinLock; SpinLock
0x1400244e5  call    cs:__imp_KeReleaseSpinLock
0x1400244ec  nop     dword ptr [rax+rax+00h]
0x1400244f1  mov     dl, 2; PriorityBoost
0x1400244f3  mov     rcx, r13; Irp
0x1400244f6  call    cs:__imp_IofCompleteRequest
0x1400244fd  nop     dword ptr [rax+rax+00h]
0x140024502  mov     rcx, r12; SpinLock
0x140024505  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002450c  nop     dword ptr [rax+rax+00h]
0x140024511  mov     [r15+6F0h], al
0x140024518  cmp     cs:qword_14001E2D8, rdi
0x14002451f  jnz     short loc_14002453B
0x140024521  cmp     cs:gbEnablePacketCapture, dil
0x140024528  jz      loc_1400245CB
0x14002452e  cmp     [r15+984h], dil
0x140024535  jz      loc_1400245CB
0x14002453b  mov     r10, [rsi+68h]
0x14002453f  xor     r9d, r9d; AllocateMdlHandler
0x140024542  mov     ebx, [rsi+48h]
0x140024545  xor     r8d, r8d; DataBackFill
0x140024548  mov     [rbp+var_20], rdi
0x14002454c  mov     rcx, r10; NetBufferList
0x14002454f  mov     [rsp+50h+FreeMdlHandler], rdi; FreeMdlHandler
0x140024554  mov     rax, [r10+8]
0x140024558  sub     ebx, [rax+18h]
0x14002455b  lea     edx, [rbx+0Eh]; DataOffsetDelta
0x14002455e  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x140024565  nop     dword ptr [rax+rax+00h]
0x14002456a  test    eax, eax
0x14002456c  jnz     short loc_1400245CB
0x14002456e  mov     rax, [rsi+68h]
0x140024572  lea     rcx, [rbp+var_18]
0x140024576  mov     r9d, 0Eh
0x14002457c  mov     rdx, [rax+8]
0x140024580  lea     rax, [rbp+var_20]
0x140024584  mov     [rsp+50h+FreeMdlHandler], rax
0x140024589  mov     r8d, [rdx+10h]
0x14002458d  mov     rdx, [rdx+8]
0x140024591  call    cs:__imp_RtlCopyKernelBufferToMdl
0x140024598  nop     dword ptr [rax+rax+00h]
0x14002459d  mov     r8, [rsi+68h]
0x1400245a1  mov     r9d, 1
0x1400245a7  mov     rdx, rsi
0x1400245aa  mov     rcx, r15
0x1400245ad  call    IndicatePromiscuousRecv
0x1400245b2  mov     rcx, [rsi+68h]; NetBufferList
0x1400245b6  lea     edx, [rbx+0Eh]; DataOffsetDelta
0x1400245b9  xor     r9d, r9d; FreeMdlMdlHandler
0x1400245bc  mov     r8b, 1; FreeMdl
0x1400245bf  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x1400245c6  nop     dword ptr [rax+rax+00h]
0x1400245cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400245d2  lea     rax, WPP_GLOBAL_Control
0x1400245d9  cmp     rcx, rax
0x1400245dc  jz      short loc_140024600
0x1400245de  mov     eax, [rcx+2Ch]
0x1400245e1  test    al, 10h
0x1400245e3  jz      short loc_140024600
0x1400245e5  cmp     byte ptr [rcx+29h], 5
0x1400245e9  jb      short loc_140024600
0x1400245eb  mov     rcx, [rcx+18h]
0x1400245ef  lea     r8, WPP_52604c4400d53a16edd48a543f00e082_Traceguids
0x1400245f6  mov     edx, 54h ; 'T'
0x1400245fb  call    WPP_SF_
0x140024600  xor     eax, eax
0x140024602  jmp     loc_1400246FB
0x140024607  lea     r13, WPP_GLOBAL_Control
0x14002460e  mov     r9d, [r14+14h]
0x140024612  cmp     r9d, 2
0x140024616  jnz     short loc_140024683
0x140024618  mov     rax, [r14+48h]
0x14002461c  mov     ecx, [rax+14h]
0x14002461f  test    cl, 1
0x140024622  jnz     short loc_14002462A
0x140024624  cmp     [r14+18h], r9d
0x140024628  jnz     short loc_140024683
0x14002462a  cmp     dword ptr [r14+60h], 5
0x14002462f  jnb     short loc_140024683
0x140024631  mov     rax, cs:qword_14001E340
0x140024638  lea     rcx, qword_14001E338
0x14002463f  cmp     [rax], rcx
0x140024642  jz      short loc_14002464B
0x140024644  mov     ecx, 3
0x140024649  int     29h; Win8: RtlFailFast(ecx)
0x14002464b  mov     [rsi+8], rax
0x14002464f  mov     [rsi], rcx
0x140024652  mov     [rax], rsi
0x140024655  mov     cs:qword_14001E340, rsi
0x14002465c  inc     dword ptr [r14+60h]
0x140024660  mov     eax, cs:dword_14001E32C
0x140024666  inc     eax
0x140024668  cmp     eax, cs:dword_14001E330
0x14002466e  mov     cs:dword_14001E32C, eax
0x140024674  jbe     short loc_14002467C
0x140024676  mov     cs:dword_14001E330, eax
0x14002467c  mov     ebx, 103h
0x140024681  jmp     short loc_1400246BB
0x140024683  mov     rcx, cs:WPP_GLOBAL_Control
0x14002468a  cmp     rcx, r13
0x14002468d  jz      short loc_1400246B6
0x14002468f  mov     eax, [rcx+2Ch]
0x140024692  test    al, 10h
0x140024694  jz      short loc_1400246B6
0x140024696  cmp     byte ptr [rcx+29h], 5
0x14002469a  jb      short loc_1400246B6
0x14002469c  mov     rcx, [rcx+18h]
0x1400246a0  lea     r8, WPP_52604c4400d53a16edd48a543f00e082_Traceguids
0x1400246a7  mov     edx, 53h ; 'S'
0x1400246ac  mov     [rsp+50h+FreeMdlHandler], r14
0x1400246b1  call    WPP_SF_dq
0x1400246b6  mov     ebx, 0C0000001h
0x1400246bb  mov     rcx, rdi; SpinLock
0x1400246be  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400246c5  nop     dword ptr [rax+rax+00h]
0x1400246ca  mov     dl, cs:byte_14001E3D8; NewIrql
0x1400246d0  lea     rcx, SpinLock; SpinLock
0x1400246d7  call    cs:__imp_KeReleaseSpinLock
0x1400246de  nop     dword ptr [rax+rax+00h]
0x1400246e3  mov     rcx, r12; SpinLock
0x1400246e6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400246ed  nop     dword ptr [rax+rax+00h]
0x1400246f2  mov     [r15+6F0h], al
0x1400246f9  mov     eax, ebx
0x1400246fb  mov     rcx, [rbp+var_8]
0x1400246ff  xor     rcx, rsp; StackCookie
0x140024702  call    __security_check_cookie
0x140024707  mov     rbx, [rsp+50h+arg_10]
0x14002470f  add     rsp, 50h
0x140024713  pop     r15
0x140024715  pop     r14
0x140024717  pop     r13
0x140024719  pop     r12
0x14002471b  pop     rdi
0x14002471c  pop     rsi
0x14002471d  pop     rbp
0x14002471e  retn
```
