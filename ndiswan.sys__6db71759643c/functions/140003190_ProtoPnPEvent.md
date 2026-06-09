# ProtoPnPEvent

- ea: `0x140003190`
- end: `0x14000353d`
- name: `ProtoPnPEvent`
- size: `941`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140003190`
- `0x1400035f0`
- `0x14000a290`
- `0x14000ed9c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140003481`
- `ntoskrnl!IofCompleteRequest` at `0x140003481`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003292`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003341`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400033e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003461`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003292`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003341`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400033e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003461`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400031e3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003262`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400032fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400033bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003411`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003494`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400031e3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003262`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400032fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400033bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003411`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003494`
- `NDIS!NdisResetEvent` at `0x1400031ff`
- `NDIS!NdisResetEvent` at `0x1400031ff`
- `NDIS!NdisWaitEvent` at `0x1400033fe`
- `NDIS!NdisWaitEvent` at `0x1400033fe`

## pseudocode

```c
__int64 __fastcall ProtoPnPEvent(__int64 a1, __int64 a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // eax
  KIRQL v7; // al
  KIRQL v8; // dl
  KSPIN_LOCK *v9; // rcx
  int v10; // esi
  KIRQL v11; // al
  PIRP v12; // rdi
  int v14; // esi
  KIRQL v15; // al
  KIRQL v16; // al
  KIRQL v17; // al

  if ( !a1 )
    return 0;
  v3 = *(_DWORD *)(a2 + 8);
  v4 = 0;
  if ( !v3 )
  {
    v10 = **(_DWORD **)(a2 + 16);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qsd(
        WPP_GLOBAL_Control->AttachedDevice,
        35,
        (unsigned int)WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids,
        a1,
        (__int64)"SetPower",
        v10);
    }
    if ( v10 != 4 && (unsigned int)(v10 - 2) > 1 )
      goto LABEL_14;
    if ( *(_DWORD *)(a1 + 120) != 12 || *(_DWORD *)(a1 + 124) != 3 || *(int *)(a1 + 200) < 0 )
      v4 = -1073741637;
    v11 = KeAcquireSpinLockRaiseToDpc(&NdisWanCB);
    v12 = Irp;
    byte_14001E288 = v11;
    if ( !Irp || !_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
      goto LABEL_12;
    goto LABEL_31;
  }
  v5 = v3 - 1;
  if ( !v5 )
  {
    v14 = **(_DWORD **)(a2 + 16);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qsd(
        WPP_GLOBAL_Control->AttachedDevice,
        36,
        (unsigned int)WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids,
        a1,
        (__int64)"QueryPower",
        v14);
    }
    if ( v14 != 4 && (unsigned int)(v14 - 2) > 1 )
      goto LABEL_14;
    v15 = KeAcquireSpinLockRaiseToDpc(&NdisWanCB);
    v12 = Irp;
    byte_14001E288 = v15;
    if ( !Irp || !_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
      goto LABEL_12;
LABEL_31:
    Irp = 0;
    KeReleaseSpinLock(&NdisWanCB, byte_14001E288);
    v12->IoStatus.Status = 0;
    v12->IoStatus.Information = 0;
    IofCompleteRequest(v12, 2);
    byte_14001E288 = KeAcquireSpinLockRaiseToDpc(&NdisWanCB);
LABEL_12:
    v8 = byte_14001E288;
    v9 = &NdisWanCB;
    goto LABEL_13;
  }
  v6 = v5 - 7;
  if ( v6 )
  {
    if ( v6 != 1 )
      goto LABEL_14;
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 504));
    *(_DWORD *)(a1 + 24) = 0;
    *(_BYTE *)(a1 + 512) = v7;
    NdisResetEvent((PNDIS_EVENT)(a1 + 528));
    *(_DWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 40) = DoBindingPauseCompleteWork;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 32));
    v8 = *(_BYTE *)(a1 + 512);
    v9 = (KSPIN_LOCK *)(a1 + 504);
  }
  else
  {
    v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 504));
    *(_DWORD *)(a1 + 24) = 1;
    *(_BYTE *)(a1 + 512) = v16;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 504), v16);
    DereferenceRefCount(a1 + 32);
    NdisWaitEvent((PNDIS_EVENT)(a1 + 528), 0);
    v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 504));
    *(_DWORD *)(a1 + 24) = 2;
    v9 = (KSPIN_LOCK *)(a1 + 504);
    *(_BYTE *)(a1 + 512) = v17;
    v8 = v17;
  }
LABEL_13:
  KeReleaseSpinLock(v9, v8);
LABEL_14:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
  }
  return v4;
}

```

## disassembly

```asm
0x140003190  push    rdi
0x140003192  sub     rsp, 30h
0x140003196  mov     rdi, rcx
0x140003199  test    rcx, rcx
0x14000319c  jz      loc_1400034AB
0x1400031a2  mov     eax, [rdx+8]
0x1400031a5  mov     [rsp+38h+arg_0], rbx
0x1400031aa  xor     ebx, ebx
0x1400031ac  mov     [rsp+38h+arg_8], rbp
0x1400031b1  lea     rbp, WPP_GLOBAL_Control
0x1400031b8  mov     [rsp+38h+arg_10], rsi
0x1400031bd  test    eax, eax
0x1400031bf  jz      short loc_14000322D
0x1400031c1  sub     eax, 1
0x1400031c4  jz      loc_1400032CE
0x1400031ca  sub     eax, 7
0x1400031cd  jz      loc_1400033B6
0x1400031d3  cmp     eax, 1
0x1400031d6  jnz     loc_14000329E
0x1400031dc  add     rcx, 1F8h; SpinLock
0x1400031e3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400031ea  nop     dword ptr [rax+rax+00h]
0x1400031ef  lea     rcx, [rdi+210h]; Event
0x1400031f6  mov     [rdi+18h], ebx
0x1400031f9  mov     [rdi+200h], al
0x1400031ff  call    cs:__imp_NdisResetEvent
0x140003206  nop     dword ptr [rax+rax+00h]
0x14000320b  lea     rax, DoBindingPauseCompleteWork
0x140003212  mov     [rdi+20h], ebx
0x140003215  mov     [rdi+28h], rax
0x140003219  lock inc dword ptr [rdi+20h]
0x14000321d  movzx   edx, byte ptr [rdi+200h]
0x140003224  lea     rcx, [rdi+1F8h]
0x14000322b  jmp     short loc_140003292
0x14000322d  mov     rax, [rdx+10h]
0x140003231  mov     esi, [rax]
0x140003233  mov     rcx, cs:WPP_GLOBAL_Control
0x14000323a  cmp     rcx, rbp
0x14000323d  jnz     loc_140003359
0x140003243  cmp     esi, 4
0x140003246  jnz     loc_140003502
0x14000324c  cmp     dword ptr [rdi+78h], 0Ch
0x140003250  jz      loc_14000339B
0x140003256  mov     ebx, 0C00000BBh
0x14000325b  lea     rcx, NdisWanCB; SpinLock
0x140003262  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003269  nop     dword ptr [rax+rax+00h]
0x14000326e  mov     rdi, cs:Irp
0x140003275  mov     cs:byte_14001E288, al
0x14000327b  test    rdi, rdi
0x14000327e  jnz     loc_140003439
0x140003284  movzx   edx, cs:byte_14001E288; NewIrql
0x14000328b  lea     rcx, NdisWanCB; SpinLock
0x140003292  call    cs:__imp_KeReleaseSpinLock
0x140003299  nop     dword ptr [rax+rax+00h]
0x14000329e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400032a5  mov     rsi, [rsp+38h+arg_10]
0x1400032aa  cmp     rcx, rbp
0x1400032ad  mov     rbp, [rsp+38h+arg_8]
0x1400032b2  jz      short loc_1400032C0
0x1400032b4  mov     edx, [rcx+2Ch]
0x1400032b7  test    dl, 4
0x1400032ba  jnz     loc_140003519
0x1400032c0  mov     eax, ebx
0x1400032c2  mov     rbx, [rsp+38h+arg_0]
0x1400032c7  add     rsp, 30h
0x1400032cb  pop     rdi
0x1400032cc  retn
0x1400032ce  mov     rax, [rdx+10h]
0x1400032d2  mov     esi, [rax]
0x1400032d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400032db  cmp     rcx, rbp
0x1400032de  jz      short loc_1400032EB
0x1400032e0  mov     eax, [rcx+2Ch]
0x1400032e3  test    al, 4
0x1400032e5  jnz     loc_1400034CB
0x1400032eb  cmp     esi, 4
0x1400032ee  jnz     loc_1400034B4
0x1400032f4  lea     rcx, NdisWanCB; SpinLock
0x1400032fb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003302  nop     dword ptr [rax+rax+00h]
0x140003307  mov     rdi, cs:Irp
0x14000330e  mov     cs:byte_14001E288, al
0x140003314  test    rdi, rdi
0x140003317  jz      loc_140003284
0x14000331d  xor     eax, eax
0x14000331f  xchg    rax, [rdi+68h]
0x140003323  test    rax, rax
0x140003326  jz      loc_140003284
0x14000332c  movzx   edx, cs:byte_14001E288; NewIrql
0x140003333  lea     rcx, NdisWanCB; SpinLock
0x14000333a  mov     cs:Irp, rbx
0x140003341  call    cs:__imp_KeReleaseSpinLock
0x140003348  nop     dword ptr [rax+rax+00h]
0x14000334d  mov     [rdi+30h], ebx
0x140003350  mov     [rdi+38h], rbx
0x140003354  jmp     loc_14000347C
0x140003359  mov     eax, [rcx+2Ch]
0x14000335c  test    al, 4
0x14000335e  jz      loc_140003243
0x140003364  cmp     byte ptr [rcx+29h], 5
0x140003368  jb      loc_140003243
0x14000336e  mov     rcx, [rcx+18h]
0x140003372  lea     rax, aSetpower; "SetPower"
0x140003379  mov     edx, 23h ; '#'
0x14000337e  mov     [rsp+38h+var_10], esi
0x140003382  mov     r9, rdi
0x140003385  mov     [rsp+38h+var_18], rax
0x14000338a  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140003391  call    WPP_SF_qsd
0x140003396  jmp     loc_140003243
0x14000339b  cmp     dword ptr [rdi+7Ch], 3
0x14000339f  jnz     loc_140003256
0x1400033a5  cmp     [rdi+0C8h], ebx
0x1400033ab  jge     loc_14000325B
0x1400033b1  jmp     loc_140003256
0x1400033b6  add     rcx, 1F8h; SpinLock
0x1400033bd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400033c4  nop     dword ptr [rax+rax+00h]
0x1400033c9  lea     rcx, [rdi+1F8h]; SpinLock
0x1400033d0  mov     dword ptr [rdi+18h], 1
0x1400033d7  movzx   edx, al; NewIrql
0x1400033da  mov     [rdi+200h], al
0x1400033e0  call    cs:__imp_KeReleaseSpinLock
0x1400033e7  nop     dword ptr [rax+rax+00h]
0x1400033ec  lea     rcx, [rdi+20h]
0x1400033f0  call    DereferenceRefCount
0x1400033f5  lea     rcx, [rdi+210h]; Event
0x1400033fc  xor     edx, edx; MsToWait
0x1400033fe  call    cs:__imp_NdisWaitEvent
0x140003405  nop     dword ptr [rax+rax+00h]
0x14000340a  lea     rcx, [rdi+1F8h]; SpinLock
0x140003411  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003418  nop     dword ptr [rax+rax+00h]
0x14000341d  mov     dword ptr [rdi+18h], 2
0x140003424  lea     rcx, [rdi+1F8h]
0x14000342b  mov     [rdi+200h], al
0x140003431  movzx   edx, al
0x140003434  jmp     loc_140003292
0x140003439  xor     eax, eax
0x14000343b  xchg    rax, [rdi+68h]
0x14000343f  test    rax, rax
0x140003442  jz      loc_140003284
0x140003448  movzx   edx, cs:byte_14001E288; NewIrql
0x14000344f  lea     rcx, NdisWanCB; SpinLock
0x140003456  mov     cs:Irp, 0
0x140003461  call    cs:__imp_KeReleaseSpinLock
0x140003468  nop     dword ptr [rax+rax+00h]
0x14000346d  mov     dword ptr [rdi+30h], 0
0x140003474  mov     qword ptr [rdi+38h], 0
0x14000347c  mov     dl, 2; PriorityBoost
0x14000347e  mov     rcx, rdi; Irp
0x140003481  call    cs:__imp_IofCompleteRequest
0x140003488  nop     dword ptr [rax+rax+00h]
0x14000348d  lea     rcx, NdisWanCB; SpinLock
0x140003494  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000349b  nop     dword ptr [rax+rax+00h]
0x1400034a0  mov     cs:byte_14001E288, al
0x1400034a6  jmp     loc_140003284
0x1400034ab  xor     eax, eax
0x1400034ad  add     rsp, 30h
0x1400034b1  pop     rdi
0x1400034b2  retn
0x1400034b4  sub     esi, 2
0x1400034b7  jz      loc_1400032F4
0x1400034bd  cmp     esi, 1
0x1400034c0  jnz     loc_14000329E
0x1400034c6  jmp     loc_1400032F4
0x1400034cb  cmp     byte ptr [rcx+29h], 5
0x1400034cf  jb      loc_1400032EB
0x1400034d5  mov     rcx, [rcx+18h]
0x1400034d9  lea     rax, aQuerypower; "QueryPower"
0x1400034e0  mov     edx, 24h ; '$'
0x1400034e5  mov     [rsp+38h+var_10], esi
0x1400034e9  mov     r9, rdi
0x1400034ec  mov     [rsp+38h+var_18], rax
0x1400034f1  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x1400034f8  call    WPP_SF_qsd
0x1400034fd  jmp     loc_1400032EB
0x140003502  sub     esi, 2
0x140003505  jz      loc_14000324C
0x14000350b  cmp     esi, 1
0x14000350e  jnz     loc_14000329E
0x140003514  jmp     loc_14000324C
0x140003519  cmp     byte ptr [rcx+29h], 5
0x14000351d  jb      loc_1400032C0
0x140003523  mov     rcx, [rcx+18h]
0x140003527  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x14000352e  mov     edx, 25h ; '%'
0x140003533  call    WPP_SF_
0x140003538  jmp     loc_1400032C0
```
