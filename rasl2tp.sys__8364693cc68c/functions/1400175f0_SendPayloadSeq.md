# SendPayloadSeq

- ea: `0x1400175f0`
- end: `0x140017ae4`
- name: `SendPayloadSeq`
- size: `1268`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001990`
- `0x140003050`
- `0x140003cf8`
- `0x1400047f0`
- `0x14000f698`
- `0x1400175f0`
- `0x1400181a8`
- `0x14001b830`
- `0x14001c1b0`
- `0x14001c390`
- `0x14001c400`
- `0x14001c620`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400176d7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400176fb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400176d7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400176fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400178f0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017945`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400179b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400178f0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017945`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400179b9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017678`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400179cb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400179e6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400179fa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017678`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400179cb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400179e6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400179fa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017717`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400178a5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017717`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400178a5`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001777f`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001777f`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140017a5c`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140017a5c`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x1400177d9`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x1400177d9`

## pseudocode

```c
__int64 __fastcall SendPayloadSeq(PVOID Entry, __int64 a2, __int64 a3, __int64 **a4)
{
  PNET_BUFFER_LIST *p_NetBufferLists; // r12
  __int64 v9; // rbp
  __int64 *v10; // rbx
  __int64 *v11; // rdi
  __int64 v12; // r14
  struct _NPAGED_LOOKASIDE_LIST *v13; // rbp
  _QWORD *v14; // r15
  volatile signed __int32 *v15; // rdi
  ULONG v16; // r8d
  ULONG v17; // ebp
  __int16 v18; // cx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rdx
  volatile signed __int32 **v22; // rcx
  KIRQL v23; // al
  _QWORD *v24; // rcx
  ULONG v25; // eax
  unsigned int v26; // eax
  __int64 result; // rax
  __int16 v28; // [rsp+30h] [rbp-98h]
  ULONG v29; // [rsp+40h] [rbp-88h] BYREF
  __int16 v30; // [rsp+44h] [rbp-84h]
  __int64 v31; // [rsp+48h] [rbp-80h]
  __int64 *v32; // [rsp+50h] [rbp-78h]
  PNET_BUFFER_LIST NetBufferLists; // [rsp+58h] [rbp-70h] BYREF
  __int64 v34; // [rsp+60h] [rbp-68h] BYREF
  _BYTE v35[2]; // [rsp+68h] [rbp-60h] BYREF
  __int16 v36; // [rsp+6Ah] [rbp-5Eh]

  NetBufferLists = 0;
  p_NetBufferLists = &NetBufferLists;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids);
  }
  v9 = *(_QWORD *)(a2 + 24);
  v10 = *a4;
  v31 = v9;
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v9 + 960), Entry);
  if ( v10 )
  {
    do
    {
      v11 = (__int64 *)*v10;
      v32 = (__int64 *)*v10;
      *((_DWORD *)v10 + 35) = 0;
      *v10 = 0;
      if ( (unsigned __int8)ReferenceCall(a3) )
      {
        *((_DWORD *)v10 + 28) = 1;
        v12 = v10[1];
        while ( v12 )
        {
          v13 = (struct _NPAGED_LOOKASIDE_LIST *)(v9 + 576);
          v14 = ExAllocateFromNPagedLookasideList(v13);
          if ( !v14 )
            goto LABEL_23;
          v15 = (volatile signed __int32 *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v31 + 832));
          if ( !v15 )
          {
            ExFreeToNPagedLookasideList(v13, v14);
LABEL_23:
            v9 = v31;
LABEL_24:
            *((_DWORD *)v10 + 35) = -1073741823;
            break;
          }
          *(_BYTE *)(a3 + 48) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 40));
          v30 = *(_WORD *)(a3 + 226);
          LOWORD(v29) = v30;
          v28 = *(_WORD *)(a3 + 280);
          *(_WORD *)(a3 + 226) = v30 + 1;
          v29 = BuildL2tpHeader((unsigned int)v35, 0, 0, (int)a2 + 116, a3 + 58, (__int64)&v29, v28);
          if ( NdisRetreatNetBufferDataStart((PNET_BUFFER)v12, v29, v16, 0) )
          {
            KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 40), *(_BYTE *)(a3 + 48));
            ExFreeToNPagedLookasideList(v13, v14);
            v9 = v31;
            ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v31 + 832), (PVOID)v15);
            goto LABEL_24;
          }
          v17 = v29;
          v29 = *(_DWORD *)(v12 + 24);
          v18 = __ROR2__(v29, 8);
          *(_DWORD *)(v12 + 136) = v17;
          *(_QWORD *)(v12 + 128) = v10;
          v36 = v18;
          v19 = *(unsigned int *)(v12 + 16);
          v20 = *(_QWORD *)(v12 + 8);
          v34 = 0;
          RtlCopyKernelBufferToMdl(v35, v20, v19, v17, &v34);
          v21 = *(_QWORD *)(a3 + 272);
          if ( v21 )
          {
            RemoveTqi(*(_QWORD *)(a2 + 304), v21, 1);
            *(_QWORD *)(a3 + 272) = 0;
          }
          *((_WORD *)v15 + 18) = v30;
          *((_DWORD *)v15 + 8) = 0;
          v14[1] = v14;
          *v14 = v14;
          *((_QWORD *)v15 + 5) = v14;
          *((_QWORD *)v15 + 6) = v12;
          ReferenceTunnel(a2, 0);
          *((_QWORD *)v15 + 7) = a2;
          ReferenceVc(a3);
          *((_QWORD *)v15 + 8) = a3;
          *((_DWORD *)v15 + 18) = -1073741823;
          *((_QWORD *)v15 + 10) = MEMORY[0xFFFFF78000000014];
          *((_QWORD *)v15 + 11) = 0;
          _InterlockedAdd(v15 + 8, 1u);
          v22 = *(volatile signed __int32 ***)(a3 + 240);
          if ( *v22 != (volatile signed __int32 *)(a3 + 232) )
            goto LABEL_37;
          *(_QWORD *)v15 = a3 + 232;
          *((_QWORD *)v15 + 1) = v22;
          *v22 = v15;
          *(_QWORD *)(a3 + 240) = v15;
          _InterlockedAdd(v15 + 8, 1u);
          _InterlockedAdd(v15 + 8, 1u);
          v23 = KeAcquireSpinLockRaiseToDpc(&g_lockDebugPs);
          v24 = (_QWORD *)qword_14000A298;
          NewIrql = v23;
          if ( *(__int64 **)qword_14000A298 != &g_listDebugPs )
LABEL_37:
            __fastfail(3u);
          *((_QWORD *)v15 + 3) = qword_14000A298;
          *((_QWORD *)v15 + 2) = &g_listDebugPs;
          *v24 = v15 + 4;
          qword_14000A298 = (__int64)(v15 + 4);
          KeReleaseSpinLock(&g_lockDebugPs, NewIrql);
          TimerQScheduleItem(
            *(_QWORD *)(a2 + 304),
            *((_QWORD *)v15 + 5),
            *(_DWORD *)(a3 + 268),
            (unsigned int)SendPayloadTimerEvent,
            (__int64)v15);
          v25 = v29;
          ++*(_DWORD *)(a3 + 384);
          *(_DWORD *)(a3 + 360) += v25 - v17;
          *(_DWORD *)(a3 + 412) += *(_DWORD *)(a3 + 248);
          KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 40), *(_BYTE *)(a3 + 48));
          _InterlockedAdd((volatile signed __int32 *)v10 + 28, 1u);
          v26 = L2tpSendDatagram(a2, (_DWORD)v15, v12, 2, v12);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_Dq(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_GLOBAL_Control, v26, v12);
          }
          v12 = *(_QWORD *)v12;
          v9 = v31;
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 28, 0xFFFFFFFF) == 1 )
        {
          *p_NetBufferLists = (PNET_BUFFER_LIST)v10;
          p_NetBufferLists = (PNET_BUFFER_LIST *)v10;
          DereferenceCall(a3);
        }
        v11 = v32;
      }
      else
      {
        *((_DWORD *)v10 + 35) = -1073741823;
        *p_NetBufferLists = (PNET_BUFFER_LIST)v10;
        p_NetBufferLists = (PNET_BUFFER_LIST *)v10;
      }
      v10 = v11;
    }
    while ( v11 );
    if ( NetBufferLists )
      NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(a3 + 304), NetBufferLists, 0);
  }
  result = DereferenceCall(a3);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x1400175f0  push    rbx
0x1400175f2  push    rbp
0x1400175f3  push    rsi
0x1400175f4  push    rdi
0x1400175f5  push    r12
0x1400175f7  push    r13
0x1400175f9  push    r14
0x1400175fb  push    r15
0x1400175fd  sub     rsp, 88h
0x140017604  mov     rax, cs:__security_cookie
0x14001760b  xor     rax, rsp
0x14001760e  mov     [rsp+0C8h+var_50], rax
0x140017613  mov     rbx, r9
0x140017616  mov     [rsp+0C8h+NetBufferLists], 0
0x14001761f  mov     rsi, r8
0x140017622  lea     r12, [rsp+0C8h+NetBufferLists]
0x140017627  mov     r13, rdx
0x14001762a  mov     rdi, rcx
0x14001762d  mov     rcx, cs:WPP_GLOBAL_Control
0x140017634  lea     r14, WPP_GLOBAL_Control
0x14001763b  cmp     rcx, r14
0x14001763e  jz      short loc_140017662
0x140017640  mov     eax, [rcx+2Ch]
0x140017643  test    al, 10h
0x140017645  jz      short loc_140017662
0x140017647  cmp     byte ptr [rcx+29h], 4
0x14001764b  jb      short loc_140017662
0x14001764d  mov     rcx, [rcx+18h]
0x140017651  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x140017658  mov     edx, 14h
0x14001765d  call    WPP_SF_
0x140017662  mov     rbp, [r13+18h]
0x140017666  mov     rdx, rdi; Entry
0x140017669  mov     rbx, [rbx]
0x14001766c  mov     [rsp+0C8h+var_80], rbp
0x140017671  lea     rcx, [rbp+3C0h]; Lookaside
0x140017678  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001767f  nop     dword ptr [rax+rax+00h]
0x140017684  test    rbx, rbx
0x140017687  jz      loc_140017A6F
0x14001768d  mov     r15d, 1
0x140017693  mov     rdi, [rbx]
0x140017696  mov     rcx, rsi
0x140017699  mov     [rsp+0C8h+var_78], rdi
0x14001769e  mov     dword ptr [rbx+8Ch], 0
0x1400176a8  mov     qword ptr [rbx], 0
0x1400176af  call    ReferenceCall
0x1400176b4  test    al, al
0x1400176b6  jz      loc_140017AC7
0x1400176bc  mov     [rbx+70h], r15d
0x1400176c0  mov     r14, [rbx+8]
0x1400176c4  test    r14, r14
0x1400176c7  jz      loc_140017A1B
0x1400176cd  add     rbp, 240h
0x1400176d4  mov     rcx, rbp; Lookaside
0x1400176d7  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400176de  nop     dword ptr [rax+rax+00h]
0x1400176e3  mov     r15, rax
0x1400176e6  test    rax, rax
0x1400176e9  jz      loc_140017A06
0x1400176ef  mov     rcx, [rsp+0C8h+var_80]
0x1400176f4  add     rcx, 340h; Lookaside
0x1400176fb  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140017702  nop     dword ptr [rax+rax+00h]
0x140017707  mov     rdi, rax
0x14001770a  test    rax, rax
0x14001770d  jz      loc_1400179F4
0x140017713  lea     rcx, [rsi+28h]; SpinLock
0x140017717  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001771e  nop     dword ptr [rax+rax+00h]
0x140017723  mov     [rsi+30h], al
0x140017726  lea     r9, [r13+74h]
0x14001772a  movzx   eax, word ptr [rsi+0E2h]
0x140017731  xor     r8d, r8d
0x140017734  mov     [rsp+0C8h+var_84], ax
0x140017739  xor     edx, edx
0x14001773b  mov     word ptr [rsp+0C8h+var_88], ax
0x140017740  lea     ecx, [rax+1]
0x140017743  movzx   eax, word ptr [rsi+118h]
0x14001774a  mov     [rsp+0C8h+var_98], ax
0x14001774f  lea     rax, [rsp+0C8h+var_88]
0x140017754  mov     [rsi+0E2h], cx
0x14001775b  lea     rcx, [rsi+3Ah]
0x14001775f  mov     [rsp+0C8h+var_A0], rax
0x140017764  mov     [rsp+0C8h+var_A8], rcx
0x140017769  lea     rcx, [rsp+0C8h+var_60]
0x14001776e  call    BuildL2tpHeader
0x140017773  mov     edx, eax; DataOffsetDelta
0x140017775  mov     [rsp+0C8h+var_88], eax
0x140017779  mov     rcx, r14; NetBuffer
0x14001777c  xor     r9d, r9d; AllocateMdlHandler
0x14001777f  call    cs:__imp_NdisRetreatNetBufferDataStart
0x140017786  nop     dword ptr [rax+rax+00h]
0x14001778b  test    eax, eax
0x14001778d  jnz     loc_1400179B2
0x140017793  mov     ecx, [r14+18h]
0x140017797  lea     rax, [rsp+0C8h+var_68]
0x14001779c  mov     ebp, [rsp+0C8h+var_88]
0x1400177a0  mov     [rsp+0C8h+var_88], ecx
0x1400177a4  mov     r9d, ebp
0x1400177a7  ror     cx, 8
0x1400177ab  mov     [r14+88h], ebp
0x1400177b2  mov     [r14+80h], rbx
0x1400177b9  mov     [rsp+0C8h+var_5E], cx
0x1400177be  lea     rcx, [rsp+0C8h+var_60]
0x1400177c3  mov     r8d, [r14+10h]
0x1400177c7  mov     rdx, [r14+8]
0x1400177cb  mov     [rsp+0C8h+var_68], 0
0x1400177d4  mov     [rsp+0C8h+var_A8], rax
0x1400177d9  call    cs:__imp_RtlCopyKernelBufferToMdl
0x1400177e0  nop     dword ptr [rax+rax+00h]
0x1400177e5  mov     rdx, [rsi+110h]
0x1400177ec  test    rdx, rdx
0x1400177ef  jz      short loc_14001780E
0x1400177f1  mov     rcx, [r13+130h]
0x1400177f8  mov     r8d, 1
0x1400177fe  call    RemoveTqi
0x140017803  mov     qword ptr [rsi+110h], 0
0x14001780e  movzx   eax, [rsp+0C8h+var_84]
0x140017813  xor     edx, edx
0x140017815  mov     [rdi+24h], ax
0x140017819  mov     rcx, r13
0x14001781c  mov     dword ptr [rdi+20h], 0
0x140017823  mov     [r15+8], r15
0x140017827  mov     [r15], r15
0x14001782a  mov     [rdi+28h], r15
0x14001782e  mov     [rdi+30h], r14
0x140017832  call    ReferenceTunnel
0x140017837  mov     rcx, rsi
0x14001783a  mov     [rdi+38h], r13
0x14001783e  call    ReferenceVc
0x140017843  mov     rax, 0FFFFF78000000014h
0x14001784d  mov     [rdi+40h], rsi
0x140017851  mov     dword ptr [rdi+48h], 0C0000001h
0x140017858  mov     r15d, 1
0x14001785e  mov     rax, [rax]
0x140017861  mov     [rdi+50h], rax
0x140017865  mov     qword ptr [rdi+58h], 0
0x14001786d  lock add [rdi+20h], r15d
0x140017872  lea     rax, [rsi+0E8h]
0x140017879  mov     rcx, [rax+8]
0x14001787d  cmp     [rcx], rax
0x140017880  jnz     loc_140017ADD
0x140017886  mov     [rdi], rax
0x140017889  mov     [rdi+8], rcx
0x14001788d  mov     [rcx], rdi
0x140017890  mov     [rax+8], rdi
0x140017894  lock add [rdi+20h], r15d
0x140017899  lock add [rdi+20h], r15d
0x14001789e  lea     rcx, g_lockDebugPs; SpinLock
0x1400178a5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400178ac  nop     dword ptr [rax+rax+00h]
0x1400178b1  mov     rcx, cs:qword_14000A298
0x1400178b8  lea     rdx, g_listDebugPs
0x1400178bf  mov     cs:NewIrql, al
0x1400178c5  cmp     [rcx], rdx
0x1400178c8  jnz     loc_140017ADD
0x1400178ce  lea     rax, [rdi+10h]
0x1400178d2  mov     [rax+8], rcx
0x1400178d6  mov     [rax], rdx
0x1400178d9  mov     [rcx], rax
0x1400178dc  lea     rcx, g_lockDebugPs; SpinLock
0x1400178e3  mov     dl, cs:NewIrql; NewIrql
0x1400178e9  mov     cs:qword_14000A298, rax
0x1400178f0  call    cs:__imp_KeReleaseSpinLock
0x1400178f7  nop     dword ptr [rax+rax+00h]
0x1400178fc  mov     r8d, [rsi+10Ch]
0x140017903  lea     r9, SendPayloadTimerEvent
0x14001790a  mov     rdx, [rdi+28h]
0x14001790e  mov     rcx, [r13+130h]
0x140017915  mov     [rsp+0C8h+var_A8], rdi
0x14001791a  call    TimerQScheduleItem
0x14001791f  mov     eax, [rsp+0C8h+var_88]
0x140017923  lea     rcx, [rsi+28h]; SpinLock
0x140017927  add     [rsi+180h], r15d
0x14001792e  sub     eax, ebp
0x140017930  add     [rsi+168h], eax
0x140017936  mov     eax, [rsi+0F8h]
0x14001793c  add     [rsi+19Ch], eax
0x140017942  mov     dl, [rsi+30h]; NewIrql
0x140017945  call    cs:__imp_KeReleaseSpinLock
0x14001794c  nop     dword ptr [rax+rax+00h]
0x140017951  lock add [rbx+70h], r15d
0x140017956  lea     r9d, [r15+1]
0x14001795a  mov     [rsp+0C8h+var_A8], r14
0x14001795f  mov     r8, r14
0x140017962  mov     rdx, rdi
0x140017965  mov     rcx, r13
0x140017968  call    L2tpSendDatagram
0x14001796d  mov     r8, cs:WPP_GLOBAL_Control
0x140017974  lea     rcx, WPP_GLOBAL_Control
0x14001797b  cmp     r8, rcx
0x14001797e  jz      short loc_1400179A5
0x140017980  mov     ecx, [r8+2Ch]
0x140017984  test    cl, 10h
0x140017987  jz      short loc_1400179A5
0x140017989  cmp     byte ptr [r8+29h], 4
0x14001798e  jb      short loc_1400179A5
0x140017990  mov     rcx, [r8+18h]
0x140017994  lea     edx, [r15+14h]
0x140017998  mov     r9d, eax
0x14001799b  mov     [rsp+0C8h+var_A8], r14
0x1400179a0  call    WPP_SF_Dq
0x1400179a5  mov     r14, [r14]
0x1400179a8  mov     rbp, [rsp+0C8h+var_80]
0x1400179ad  jmp     loc_1400176C4
0x1400179b2  mov     dl, [rsi+30h]; NewIrql
0x1400179b5  lea     rcx, [rsi+28h]; SpinLock
0x1400179b9  call    cs:__imp_KeReleaseSpinLock
0x1400179c0  nop     dword ptr [rax+rax+00h]
0x1400179c5  mov     rdx, r15; Entry
0x1400179c8  mov     rcx, rbp; Lookaside
0x1400179cb  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400179d2  nop     dword ptr [rax+rax+00h]
0x1400179d7  mov     rbp, [rsp+0C8h+var_80]
0x1400179dc  mov     rdx, rdi; Entry
0x1400179df  lea     rcx, [rbp+340h]; Lookaside
0x1400179e6  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400179ed  nop     dword ptr [rax+rax+00h]
0x1400179f2  jmp     short loc_140017A0B
0x1400179f4  mov     rdx, r15; Entry
0x1400179f7  mov     rcx, rbp; Lookaside
0x1400179fa  call    cs:__imp_ExFreeToNPagedLookasideList
0x140017a01  nop     dword ptr [rax+rax+00h]
0x140017a06  mov     rbp, [rsp+0C8h+var_80]
0x140017a0b  mov     dword ptr [rbx+8Ch], 0C0000001h
0x140017a15  mov     r15d, 1
0x140017a1b  or      eax, 0FFFFFFFFh
0x140017a1e  lock xadd [rbx+70h], eax
0x140017a23  cmp     eax, 1
0x140017a26  jnz     short loc_140017A37
0x140017a28  mov     [r12], rbx
0x140017a2c  mov     rcx, rsi
0x140017a2f  mov     r12, rbx
0x140017a32  call    DereferenceCall
0x140017a37  mov     rdi, [rsp+0C8h+var_78]
0x140017a3c  mov     rbx, rdi
0x140017a3f  test    rdi, rdi
0x140017a42  jnz     loc_140017693
0x140017a48  mov     rdx, [rsp+0C8h+NetBufferLists]; NetBufferLists
0x140017a4d  test    rdx, rdx
0x140017a50  jz      short loc_140017A68
0x140017a52  mov     rcx, [rsi+130h]; NdisVcHandle
0x140017a59  xor     r8d, r8d; SendCompleteFlags
0x140017a5c  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x140017a63  nop     dword ptr [rax+rax+00h]
0x140017a68  lea     r14, WPP_GLOBAL_Control
0x140017a6f  mov     rcx, rsi
0x140017a72  call    DereferenceCall
0x140017a77  mov     rcx, cs:WPP_GLOBAL_Control
0x140017a7e  cmp     rcx, r14
0x140017a81  jz      short loc_140017AA5
0x140017a83  mov     eax, [rcx+2Ch]
0x140017a86  test    al, 10h
0x140017a88  jz      short loc_140017AA5
0x140017a8a  cmp     byte ptr [rcx+29h], 4
0x140017a8e  jb      short loc_140017AA5
0x140017a90  mov     rcx, [rcx+18h]
0x140017a94  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x140017a9b  mov     edx, 16h
0x140017aa0  call    WPP_SF_
0x140017aa5  mov     rcx, [rsp+0C8h+var_50]
0x140017aaa  xor     rcx, rsp; StackCookie
0x140017aad  call    __security_check_cookie
0x140017ab2  add     rsp, 88h
0x140017ab9  pop     r15
0x140017abb  pop     r14
0x140017abd  pop     r13
0x140017abf  pop     r12
0x140017ac1  pop     rdi
0x140017ac2  pop     rsi
0x140017ac3  pop     rbp
0x140017ac4  pop     rbx
0x140017ac5  retn
0x140017ac7  mov     dword ptr [rbx+8Ch], 0C0000001h
0x140017ad1  mov     [r12], rbx
0x140017ad5  mov     r12, rbx
0x140017ad8  jmp     loc_140017A3C
0x140017add  mov     ecx, 3
0x140017ae2  int     29h; Win8: RtlFailFast(ecx)
```
