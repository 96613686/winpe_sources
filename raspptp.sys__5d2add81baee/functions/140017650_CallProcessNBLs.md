# CallProcessNBLs

- ea: `0x140017650`
- end: `0x140017b47`
- name: `CallProcessNBLs`
- size: `1271`
- prototype: `NDIS_IO_WORKITEM_FUNCTION`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140001a70`
- `0x140003e08`
- `0x14000429c`
- `0x140007710`
- `0x140017650`
- `0x140017b50`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400176f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017738`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017798`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400178a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400178fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017988`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017a2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017a8b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400176f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017738`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017798`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400178a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400178fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017988`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017a2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017a8b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400176a5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001770c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017759`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017843`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017965`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017a10`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017a68`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400176a5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001770c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017759`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017843`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017965`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017a10`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017a68`
- `NDIS!NdisQueueIoWorkItem` at `0x1400178e4`
- `NDIS!NdisQueueIoWorkItem` at `0x1400178e4`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140017ae9`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140017ae9`

## pseudocode

```c
void __fastcall CallProcessNBLs(char *WorkItemContext, NDIS_HANDLE NdisIoWorkItemHandle)
{
  int v3; // r14d
  int v4; // r13d
  int v5; // r12d
  __int64 v6; // r8
  __int64 v7; // rdi
  __int64 v8; // r8
  _QWORD *i; // rsi
  KIRQL v10; // al
  unsigned int v11; // r14d
  int v12; // ecx
  KIRQL v13; // al
  int v14; // eax
  KSPIN_LOCK *v15; // rcx
  KIRQL v16; // al
  KIRQL v17; // al
  int v18; // [rsp+30h] [rbp-58h]
  int v19; // [rsp+40h] [rbp-48h]
  int v20; // [rsp+44h] [rbp-44h]
  char v21; // [rsp+90h] [rbp+8h]
  int v22; // [rsp+A0h] [rbp+18h]
  int v23; // [rsp+A0h] [rbp+18h]
  int v24; // [rsp+A8h] [rbp+20h]

  v3 = 0;
  v24 = 0;
  v19 = 0;
  v4 = 0;
  v5 = 50;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 116, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
  }
  WorkItemContext[144] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)WorkItemContext + 17);
  do
  {
    v7 = *((_QWORD *)WorkItemContext + 15);
    if ( !v7 )
      break;
    --v5;
    *((_QWORD *)WorkItemContext + 15) = *(_QWORD *)v7;
    *(_QWORD *)v7 = 0;
    v20 = 0;
    if ( !*((_QWORD *)WorkItemContext + 15) )
      *((_QWORD *)WorkItemContext + 16) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)WorkItemContext + 17, WorkItemContext[144]);
    *(_DWORD *)(v7 + 140) = 0;
    WorkItemContext[104] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)WorkItemContext + 12);
    v21 = 0;
    if ( v7 == *((_QWORD *)WorkItemContext + 60) )
    {
      ++*((_DWORD *)WorkItemContext + 114);
      v21 = 1;
      _InterlockedIncrement((volatile signed __int32 *)WorkItemContext + 170);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)WorkItemContext + 12, WorkItemContext[104]);
    for ( i = *(_QWORD **)(v7 + 8); ; i = (_QWORD *)*i )
    {
      if ( !i )
      {
        v24 = v3;
        if ( v21 )
          goto LABEL_19;
        goto LABEL_18;
      }
      ++v20;
      v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)WorkItemContext + 12);
      --*((_DWORD *)WorkItemContext + 47);
      v11 = 0;
      v12 = *((_DWORD *)WorkItemContext + 68);
      WorkItemContext[104] = v10;
      if ( *((_DWORD *)WorkItemContext + 82) != v12 )
      {
        *((_DWORD *)WorkItemContext + 82) = v12;
        v11 = 2;
        v19 = v12 - 1;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)WorkItemContext + 12, v10);
      if ( !v21 )
        break;
      if ( v11 )
        goto LABEL_15;
      v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)WorkItemContext + 12);
      ++*((_DWORD *)WorkItemContext + 114);
      WorkItemContext[104] = v13;
      WorkItemContext[464] = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)WorkItemContext + 12, v13);
      _InterlockedIncrement((volatile signed __int32 *)WorkItemContext + 171);
      DereferenceRefCount(WorkItemContext + 32);
      v3 = v24;
LABEL_16:
      ;
    }
    v4 = *((_DWORD *)WorkItemContext + 81);
    v11 |= 1u;
    *((_DWORD *)WorkItemContext + 81) = v4 + 1;
LABEL_15:
    LOBYTE(v18) = v21;
    v24 = CallTransmitNB(WorkItemContext, v7, i, v11, v4, v19, v18);
    v3 = v24;
    if ( v24 == 259 )
      goto LABEL_16;
    v14 = *(_DWORD *)(v7 + 96);
    v22 = v14;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_qdd(WPP_GLOBAL_Control->AttachedDevice, 117, v8, WorkItemContext, *((_DWORD *)WorkItemContext + 50), v24);
      v14 = v22;
    }
    v15 = (KSPIN_LOCK *)(WorkItemContext + 96);
    if ( v21 )
    {
      v16 = KeAcquireSpinLockRaiseToDpc(v15);
      WorkItemContext[464] = 0;
      WorkItemContext[104] = v16;
      KeReleaseSpinLock((PKSPIN_LOCK)WorkItemContext + 12, v16);
      _InterlockedIncrement((volatile signed __int32 *)WorkItemContext + 171);
      goto LABEL_44;
    }
    v23 = v14 - v20;
    *(_DWORD *)(v7 + 140) = -1073741823;
    _InterlockedAdd((volatile signed __int32 *)WorkItemContext + 167, v14 - v20);
    _InterlockedAdd(&dword_14000B3FC, v14 - v20);
    v17 = KeAcquireSpinLockRaiseToDpc(v15);
    *((_DWORD *)WorkItemContext + 47) -= v23;
    WorkItemContext[104] = v17;
    KeReleaseSpinLock((PKSPIN_LOCK)WorkItemContext + 12, v17);
LABEL_18:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 112), 0xFFFFFFFF) != 1 )
      goto LABEL_19;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qdd(WPP_GLOBAL_Control->AttachedDevice, 118, v8, WorkItemContext, *((_DWORD *)WorkItemContext + 50), v3);
    }
    NdisMCoSendNetBufferListsComplete(*((NDIS_HANDLE *)WorkItemContext + 28), (PNET_BUFFER_LIST)v7, 0);
    DereferenceRefCount(*((_QWORD *)WorkItemContext + 7) + 192LL);
LABEL_44:
    DereferenceRefCount(WorkItemContext + 32);
LABEL_19:
    v3 = v24;
    WorkItemContext[144] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)WorkItemContext + 17);
  }
  while ( v5 );
  if ( *((_QWORD *)WorkItemContext + 15) )
  {
    NdisQueueIoWorkItem(*((NDIS_HANDLE *)WorkItemContext + 75), CallProcessNBLs, WorkItemContext);
    KeReleaseSpinLock((PKSPIN_LOCK)WorkItemContext + 17, WorkItemContext[144]);
  }
  else
  {
    WorkItemContext[195] = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qdd(
        WPP_GLOBAL_Control->AttachedDevice,
        119,
        v6,
        WorkItemContext,
        *((_DWORD *)WorkItemContext + 50),
        *((_DWORD *)WorkItemContext + 47));
    }
    KeReleaseSpinLock((PKSPIN_LOCK)WorkItemContext + 17, WorkItemContext[144]);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)WorkItemContext, 0xFFFFFFFF) == 1 )
      (*((void (__fastcall **)(char *))WorkItemContext + 1))(WorkItemContext);
  }
}

```

## disassembly

```asm
0x140017650  mov     [rsp+arg_8], rbx
0x140017655  push    rbp
0x140017656  push    rsi
0x140017657  push    rdi
0x140017658  push    r12
0x14001765a  push    r13
0x14001765c  push    r14
0x14001765e  push    r15
0x140017660  sub     rsp, 50h
0x140017664  xor     esi, esi
0x140017666  mov     rbx, rcx
0x140017669  mov     r14d, esi
0x14001766c  mov     [rsp+88h+arg_18], esi
0x140017673  mov     [rsp+88h+var_48], esi
0x140017677  mov     r13d, esi
0x14001767a  mov     r12d, 32h ; '2'
0x140017680  mov     rcx, cs:WPP_GLOBAL_Control
0x140017687  lea     rax, WPP_GLOBAL_Control
0x14001768e  cmp     rcx, rax
0x140017691  jz      short loc_14001769E
0x140017693  mov     eax, [rcx+2Ch]
0x140017696  test    al, 20h
0x140017698  jnz     loc_14001791A
0x14001769e  lea     rcx, [rbx+88h]; SpinLock
0x1400176a5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400176ac  nop     dword ptr [rax+rax+00h]
0x1400176b1  mov     [rbx+90h], al
0x1400176b7  mov     ebp, 0FFFFFFFFh
0x1400176bc  mov     rdi, [rbx+78h]
0x1400176c0  test    rdi, rdi
0x1400176c3  jz      loc_14001786B
0x1400176c9  mov     rax, [rdi]
0x1400176cc  dec     r12d
0x1400176cf  mov     [rbx+78h], rax
0x1400176d3  mov     [rdi], rsi
0x1400176d6  cmp     qword ptr [rbx+78h], 0
0x1400176db  mov     [rsp+88h+var_44], esi
0x1400176df  jnz     short loc_1400176E8
0x1400176e1  mov     [rbx+80h], rsi
0x1400176e8  movzx   edx, byte ptr [rbx+90h]; NewIrql
0x1400176ef  lea     rcx, [rbx+88h]; SpinLock
0x1400176f6  call    cs:__imp_KeReleaseSpinLock
0x1400176fd  nop     dword ptr [rax+rax+00h]
0x140017702  lea     rcx, [rbx+60h]; SpinLock
0x140017706  mov     [rdi+8Ch], esi
0x14001770c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017713  nop     dword ptr [rax+rax+00h]
0x140017718  mov     [rbx+68h], al
0x14001771b  mov     [rsp+88h+arg_0], 0
0x140017723  cmp     rdi, [rbx+1E0h]
0x14001772a  jz      loc_14001793E
0x140017730  movzx   edx, byte ptr [rbx+68h]; NewIrql
0x140017734  lea     rcx, [rbx+60h]; SpinLock
0x140017738  call    cs:__imp_KeReleaseSpinLock
0x14001773f  nop     dword ptr [rax+rax+00h]
0x140017744  mov     rsi, [rdi+8]
0x140017748  test    rsi, rsi
0x14001774b  jz      loc_140017808
0x140017751  inc     [rsp+88h+var_44]
0x140017755  lea     rcx, [rbx+60h]; SpinLock
0x140017759  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017760  nop     dword ptr [rax+rax+00h]
0x140017765  dec     dword ptr [rbx+0BCh]
0x14001776b  xor     r14d, r14d
0x14001776e  mov     ecx, [rbx+110h]
0x140017774  mov     [rbx+68h], al
0x140017777  cmp     [rbx+148h], ecx
0x14001777d  jz      short loc_140017791
0x14001777f  mov     [rbx+148h], ecx
0x140017785  mov     r14d, 2
0x14001778b  dec     ecx
0x14001778d  mov     [rsp+88h+var_48], ecx
0x140017791  movzx   edx, al; NewIrql
0x140017794  lea     rcx, [rbx+60h]; SpinLock
0x140017798  call    cs:__imp_KeReleaseSpinLock
0x14001779f  nop     dword ptr [rax+rax+00h]
0x1400177a4  movzx   ecx, [rsp+88h+arg_0]
0x1400177ac  test    cl, cl
0x1400177ae  jnz     loc_140017958
0x1400177b4  mov     r13d, [rbx+144h]
0x1400177bb  or      r14d, 1
0x1400177bf  lea     eax, [r13+1]
0x1400177c3  mov     [rbx+144h], eax
0x1400177c9  mov     eax, [rsp+88h+var_48]
0x1400177cd  mov     r9d, r14d
0x1400177d0  mov     byte ptr [rsp+88h+var_58], cl
0x1400177d4  mov     r8, rsi
0x1400177d7  mov     [rsp+88h+var_60], eax
0x1400177db  mov     rcx, rbx
0x1400177de  mov     rdx, rdi
0x1400177e1  mov     [rsp+88h+var_68], r13d
0x1400177e6  call    CallTransmitNB
0x1400177eb  mov     [rsp+88h+arg_18], eax
0x1400177f2  mov     r14d, eax
0x1400177f5  cmp     eax, 103h
0x1400177fa  jnz     loc_1400179B1
0x140017800  mov     rsi, [rsi]
0x140017803  jmp     loc_140017748
0x140017808  cmp     [rsp+88h+arg_0], 0
0x140017810  mov     [rsp+88h+arg_18], r14d
0x140017818  mov     r14d, [rsp+88h+var_48]
0x14001781d  mov     [rsp+88h+var_48], r14d
0x140017822  jnz     short loc_14001783C
0x140017824  mov     r14d, [rsp+88h+arg_18]
0x14001782c  mov     eax, ebp
0x14001782e  lock xadd [rdi+70h], eax
0x140017833  cmp     eax, 1
0x140017836  jz      loc_140017A9C
0x14001783c  lea     rcx, [rbx+88h]; SpinLock
0x140017843  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001784a  nop     dword ptr [rax+rax+00h]
0x14001784f  mov     r14d, [rsp+88h+arg_18]
0x140017857  mov     esi, 0
0x14001785c  mov     [rbx+90h], al
0x140017862  test    r12d, r12d
0x140017865  jnz     loc_1400176BC
0x14001786b  cmp     qword ptr [rbx+78h], 0
0x140017870  jnz     short loc_1400178D3
0x140017872  mov     byte ptr [rbx+0C3h], 0
0x140017879  mov     rcx, cs:WPP_GLOBAL_Control
0x140017880  lea     rax, WPP_GLOBAL_Control
0x140017887  cmp     rcx, rax
0x14001788a  jz      short loc_140017897
0x14001788c  mov     eax, [rcx+2Ch]
0x14001788f  test    al, 10h
0x140017891  jnz     loc_140017B13
0x140017897  movzx   edx, byte ptr [rbx+90h]; NewIrql
0x14001789e  lea     rcx, [rbx+88h]; SpinLock
0x1400178a5  call    cs:__imp_KeReleaseSpinLock
0x1400178ac  nop     dword ptr [rax+rax+00h]
0x1400178b1  lock xadd [rbx], ebp
0x1400178b5  cmp     ebp, 1
0x1400178b8  jz      short loc_14001790C
0x1400178ba  mov     rbx, [rsp+88h+arg_8]
0x1400178c2  add     rsp, 50h
0x1400178c6  pop     r15
0x1400178c8  pop     r14
0x1400178ca  pop     r13
0x1400178cc  pop     r12
0x1400178ce  pop     rdi
0x1400178cf  pop     rsi
0x1400178d0  pop     rbp
0x1400178d1  retn
0x1400178d3  mov     rcx, [rbx+258h]; NdisIoWorkItemHandle
0x1400178da  lea     rdx, CallProcessNBLs; Routine
0x1400178e1  mov     r8, rbx; WorkItemContext
0x1400178e4  call    cs:__imp_NdisQueueIoWorkItem
0x1400178eb  nop     dword ptr [rax+rax+00h]
0x1400178f0  movzx   edx, byte ptr [rbx+90h]; NewIrql
0x1400178f7  lea     rcx, [rbx+88h]; SpinLock
0x1400178fe  call    cs:__imp_KeReleaseSpinLock
0x140017905  nop     dword ptr [rax+rax+00h]
0x14001790a  jmp     short loc_1400178BA
0x14001790c  mov     rax, [rbx+8]
0x140017910  mov     rcx, rbx
0x140017913  call    _guard_dispatch_icall
0x140017918  jmp     short loc_1400178BA
0x14001791a  cmp     byte ptr [rcx+29h], 2
0x14001791e  jb      loc_14001769E
0x140017924  mov     rcx, [rcx+18h]
0x140017928  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x14001792f  mov     edx, 74h ; 't'
0x140017934  call    WPP_SF_
0x140017939  jmp     loc_14001769E
0x14001793e  inc     dword ptr [rbx+1C8h]
0x140017944  mov     [rsp+88h+arg_0], 1
0x14001794c  lock inc dword ptr [rbx+2A8h]
0x140017953  jmp     loc_140017730
0x140017958  test    r14d, r14d
0x14001795b  jnz     loc_1400177C9
0x140017961  lea     rcx, [rbx+60h]; SpinLock
0x140017965  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001796c  nop     dword ptr [rax+rax+00h]
0x140017971  inc     dword ptr [rbx+1C8h]
0x140017977  lea     rcx, [rbx+60h]; SpinLock
0x14001797b  movzx   edx, al; NewIrql
0x14001797e  mov     [rbx+68h], al
0x140017981  mov     [rbx+1D0h], r14b
0x140017988  call    cs:__imp_KeReleaseSpinLock
0x14001798f  nop     dword ptr [rax+rax+00h]
0x140017994  lock inc dword ptr [rbx+2ACh]
0x14001799b  lea     rcx, [rbx+20h]
0x14001799f  call    DereferenceRefCount
0x1400179a4  mov     r14d, [rsp+88h+arg_18]
0x1400179ac  jmp     loc_140017800
0x1400179b1  mov     eax, [rdi+60h]
0x1400179b4  mov     [rsp+88h+arg_10], eax
0x1400179bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400179c2  lea     rdx, WPP_GLOBAL_Control
0x1400179c9  cmp     rcx, rdx
0x1400179cc  jz      short loc_140017A02
0x1400179ce  mov     eax, [rcx+2Ch]
0x1400179d1  test    al, 10h
0x1400179d3  jz      short loc_1400179FB
0x1400179d5  cmp     byte ptr [rcx+29h], 2
0x1400179d9  jb      short loc_1400179FB
0x1400179db  mov     eax, [rbx+0C8h]
0x1400179e1  mov     edx, 75h ; 'u'
0x1400179e6  mov     rcx, [rcx+18h]
0x1400179ea  mov     r9, rbx
0x1400179ed  mov     [rsp+88h+var_60], r14d
0x1400179f2  mov     [rsp+88h+var_68], eax
0x1400179f6  call    WPP_SF_qdd
0x1400179fb  mov     eax, [rsp+88h+arg_10]
0x140017a02  cmp     [rsp+88h+arg_0], 0
0x140017a0a  lea     rcx, [rbx+60h]; SpinLock
0x140017a0e  jz      short loc_140017A45
0x140017a10  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017a17  nop     dword ptr [rax+rax+00h]
0x140017a1c  lea     rcx, [rbx+60h]; SpinLock
0x140017a20  mov     byte ptr [rbx+1D0h], 0
0x140017a27  movzx   edx, al; NewIrql
0x140017a2a  mov     [rbx+68h], al
0x140017a2d  call    cs:__imp_KeReleaseSpinLock
0x140017a34  nop     dword ptr [rax+rax+00h]
0x140017a39  lock inc dword ptr [rbx+2ACh]
0x140017a40  jmp     loc_140017B05
0x140017a45  sub     eax, [rsp+88h+var_44]
0x140017a49  mov     [rsp+88h+arg_10], eax
0x140017a50  mov     dword ptr [rdi+8Ch], 0C0000001h
0x140017a5a  lock add [rbx+29Ch], eax
0x140017a61  lock add cs:dword_14000B3FC, eax
0x140017a68  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017a6f  nop     dword ptr [rax+rax+00h]
0x140017a74  mov     ecx, [rsp+88h+arg_10]
0x140017a7b  movzx   edx, al; NewIrql
0x140017a7e  sub     [rbx+0BCh], ecx
0x140017a84  lea     rcx, [rbx+60h]; SpinLock
0x140017a88  mov     [rbx+68h], al
0x140017a8b  call    cs:__imp_KeReleaseSpinLock
0x140017a92  nop     dword ptr [rax+rax+00h]
0x140017a97  jmp     loc_14001782C
0x140017a9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140017aa3  lea     rax, WPP_GLOBAL_Control
0x140017aaa  cmp     rcx, rax
0x140017aad  jz      short loc_140017ADC
0x140017aaf  mov     eax, [rcx+2Ch]
0x140017ab2  test    al, 10h
0x140017ab4  jz      short loc_140017ADC
0x140017ab6  cmp     byte ptr [rcx+29h], 2
0x140017aba  jb      short loc_140017ADC
0x140017abc  mov     eax, [rbx+0C8h]
0x140017ac2  mov     edx, 76h ; 'v'
0x140017ac7  mov     rcx, [rcx+18h]
0x140017acb  mov     r9, rbx
0x140017ace  mov     [rsp+88h+var_60], r14d
0x140017ad3  mov     [rsp+88h+var_68], eax
0x140017ad7  call    WPP_SF_qdd
0x140017adc  mov     rcx, [rbx+0E0h]; NdisVcHandle
0x140017ae3  xor     r8d, r8d; SendCompleteFlags
0x140017ae6  mov     rdx, rdi; NetBufferLists
0x140017ae9  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x140017af0  nop     dword ptr [rax+rax+00h]
0x140017af5  mov     rcx, [rbx+38h]
0x140017af9  add     rcx, 0C0h
0x140017b00  call    DereferenceRefCount
0x140017b05  lea     rcx, [rbx+20h]
0x140017b09  call    DereferenceRefCount
0x140017b0e  jmp     loc_14001783C
0x140017b13  cmp     byte ptr [rcx+29h], 2
0x140017b17  jb      loc_140017897
0x140017b1d  mov     eax, [rbx+0BCh]
0x140017b23  mov     edx, 77h ; 'w'
0x140017b28  mov     rcx, [rcx+18h]
0x140017b2c  mov     r9, rbx
0x140017b2f  mov     [rsp+88h+var_60], eax
0x140017b33  mov     eax, [rbx+0C8h]
0x140017b39  mov     [rsp+88h+var_68], eax
0x140017b3d  call    WPP_SF_qdd
0x140017b42  jmp     loc_140017897
```
