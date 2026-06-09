# BwcUpdateFlow

- ea: `0x140013570`
- end: `0x14001393a`
- name: `BwcUpdateFlow`
- size: `970`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140011ed4`
- `0x140013940`

## callees

- `0x140009368`
- `0x140011da8`
- `0x1400123e4`
- `0x1400127f0`
- `0x140012ddc`
- `0x140013570`
- `0x140013f48`
- `0x140013fb8`
- `0x140014010`
- `0x140014050`
- `0x1400141c0`
- `0x140014384`
- `0x140014434`
- `0x140014fb4`
- `0x1400161f0`
- `0x140016230`
- `0x140016700`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001369b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001369b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013902`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013902`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013635`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013635`
- `NDIS!NdisReleaseRWLock` at `0x140013717`
- `NDIS!NdisReleaseRWLock` at `0x1400137f0`
- `NDIS!NdisReleaseRWLock` at `0x1400138a8`
- `NDIS!NdisReleaseRWLock` at `0x140013717`
- `NDIS!NdisReleaseRWLock` at `0x1400137f0`
- `NDIS!NdisReleaseRWLock` at `0x1400138a8`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400136d9`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400137c7`
- `NDIS!NdisAcquireRWLockWrite` at `0x140013889`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400136d9`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400137c7`
- `NDIS!NdisAcquireRWLockWrite` at `0x140013889`

## pseudocode

```c
__int64 __fastcall BwcUpdateFlow(_QWORD *a1, __int64 a2)
{
  PNDIS_RW_LOCK_EX *v2; // rdi
  __int64 v5; // rcx
  KIRQL v6; // al
  bool v7; // zf
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  ULONG CurrentProcessorNumber; // eax
  __int64 v12; // r8
  __int64 v13; // rdx
  ULONG v14; // r14d
  __int64 CurrentTime; // rax
  __int64 v16; // rdx
  int v17; // r9d
  int v18; // ecx
  int v19; // edx
  unsigned int updated; // r12d
  int v21; // ebx
  int v22; // r15d
  int v23; // edx
  int v24; // r9d
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v27; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v28; // [rsp+48h] [rbp-B8h] BYREF
  int v29; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+70h] [rbp-90h] BYREF
  __int128 v35; // [rsp+78h] [rbp-88h] BYREF
  __int128 v36; // [rsp+88h] [rbp-78h]
  _OWORD v37[2]; // [rsp+98h] [rbp-68h] BYREF
  int v38; // [rsp+B8h] [rbp-48h]
  _QWORD v39[8]; // [rsp+C0h] [rbp-40h] BYREF

  v2 = (PNDIS_RW_LOCK_EX *)BwcVirtualLine;
  v38 = 0;
  v31 = 0;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v32 = 0;
  memset(v37, 0, sizeof(v37));
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v29 = 0;
  v27 = 0;
  v28 = 0;
  memset(v39, 0, sizeof(v39));
  v5 = a1[2] >> 10;
  v36 = 0;
  HIDWORD(v39[7]) = 2;
  DWORD2(v36) = 1;
  v35 = 0;
  BwcGetQoSParameters(v5, &v39[3], &v27, &v28);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 472));
  v7 = *(_DWORD *)(a2 + 464) == 0;
  *(_BYTE *)(a2 + 480) = v6;
  if ( v7 )
  {
    v8 = a1[4];
    v9 = a1[2];
    if ( !v8 )
      v8 = v9 * v27;
    v39[1] = v8 >> 3;
    v10 = a1[3];
    if ( !v10 )
      v10 = v9 * v28;
    v39[0] = v9 >> 3;
    v39[2] = v10 >> 3;
    v39[4] = 0x1FFFFFFFFLL;
  }
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  LOBYTE(v12) = 1;
  LOBYTE(v13) = 1;
  v14 = CurrentProcessorNumber;
  CurrentTime = QosTimerGetCurrentTime(CurrentProcessorNumber, v13, v12);
  if ( (unsigned __int8)QosFlowNeedQueueFeedback(a2 + 40, CurrentTime, v37) )
  {
    NdisAcquireRWLockWrite(*v2, &LockState, 1u);
    if ( (unsigned __int8)QosLineNeedSignal(v2 + 1, v14) )
      QosLineSignalExternalEvent(v2 + 1, v14);
    QosLineQueryQueueFeedback(v2 + 1, v16, v37);
    NdisReleaseRWLock(*v2, &LockState);
    QosTbcAdjustSendWindow(a2 + 40, v37);
  }
  HIDWORD(v39[7]) |= 1u;
  if ( LODWORD(v39[7]) == -1
    || ((v17 = *(_DWORD *)(a2 + 360), v18 = LODWORD(v39[7]) - v17, LODWORD(v39[7]) - v17 != LODWORD(v39[7]))
      ? (v19 = (v18 != -v17) - 1)
      : (v19 = 1),
        !v18) )
  {
    updated = QosFlowUpdateComplete(
                (int)a2 + 40,
                v14,
                (unsigned int)v39,
                0,
                (__int64)&v29,
                (__int64)&v31,
                (__int64)&v30);
    if ( updated != 259 )
      goto LABEL_19;
  }
  else
  {
    LODWORD(v35) = *(_DWORD *)(a2 + 360);
    DWORD1(v35) = v39[7];
    DWORD2(v35) = LODWORD(v39[7]) - v17;
    HIDWORD(v35) = v19;
  }
  NdisAcquireRWLockWrite(*v2, &LockState, 1u);
  v21 = QosLineUpdate(v2 + 1, 0, 0, &v35);
  NdisReleaseRWLock(*v2, &LockState);
  updated = QosFlowUpdateComplete(
              (int)a2 + 40,
              v14,
              (unsigned int)v39,
              v21,
              (__int64)&v29,
              (__int64)&v31,
              (__int64)&v30);
LABEL_19:
  if ( v30 )
  {
    BwcDropNbls(a2, v2, v30, &v32);
    ((void (__fastcall *)(__int64, __int64))DropQueuedNonConformantNbls)(a2, v32);
  }
  v22 = v31;
  if ( v31 )
  {
    if ( (unsigned __int8)QosLineNeedSignal(v2 + 1, v14) )
    {
      NdisAcquireRWLockWrite(*v2, &LockState, 1u);
      QosLineSignalExternalEvent(v2 + 1, v14);
      NdisReleaseRWLock(*v2, &LockState);
    }
    QosLineSendNetBufferLists((_DWORD)v2 + 8, v23, v22, v24, (__int64)&v33, (__int64)&v30);
    BwcCompleteNbls(a2, v2, v33, &v34);
    BwcSendProcessedNbls(a2, v34);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 472), *(_BYTE *)(a2 + 480));
  return updated;
}

```

## disassembly

```asm
0x140013570  mov     [rsp-8+arg_10], rbx
0x140013575  mov     [rsp-8+arg_18], rsi
0x14001357a  push    rbp
0x14001357b  push    rdi
0x14001357c  push    r12
0x14001357e  push    r14
0x140013580  push    r15
0x140013582  lea     rbp, [rsp-10h]
0x140013587  sub     rsp, 110h
0x14001358e  mov     rax, cs:__security_cookie
0x140013595  xor     rax, rsp
0x140013598  mov     [rbp+30h+var_30], rax
0x14001359c  mov     rdi, cs:BwcVirtualLine
0x1400135a3  xor     eax, eax
0x1400135a5  xorps   xmm0, xmm0
0x1400135a8  mov     [rbp+30h+var_78], eax
0x1400135ab  mov     rsi, rdx
0x1400135ae  mov     [rsp+130h+var_D8], rax
0x1400135b3  mov     rbx, rcx
0x1400135b6  mov     [rsp+130h+var_E0], rax
0x1400135bb  lea     r8d, [rax+40h]; Size
0x1400135bf  mov     [rsp+130h+var_C8], rax
0x1400135c4  xor     edx, edx; Val
0x1400135c6  mov     [rsp+130h+var_C0], rax
0x1400135cb  lea     rcx, [rbp+30h+var_70]; void *
0x1400135cf  mov     [rsp+130h+var_D0], rax
0x1400135d4  movups  [rbp+30h+var_98], xmm0
0x1400135d8  mov     word ptr [rsp+130h+LockState.OldIrql], ax
0x1400135dd  movups  [rbp+30h+var_88], xmm0
0x1400135e1  mov     [rsp+130h+LockState.Flags], al
0x1400135e5  mov     [rsp+130h+var_E4], eax
0x1400135e9  mov     [rsp+130h+var_EC], eax
0x1400135ed  mov     [rsp+130h+var_E8], eax
0x1400135f1  call    memset
0x1400135f6  mov     rcx, [rbx+10h]
0x1400135fa  lea     r9, [rsp+130h+var_E8]
0x1400135ff  xorps   xmm0, xmm0
0x140013602  shr     rcx, 0Ah
0x140013606  movups  [rbp+30h+var_A8], xmm0
0x14001360a  mov     r12d, 1
0x140013610  mov     [rbp+30h+var_34], 2
0x140013617  lea     r8, [rsp+130h+var_EC]
0x14001361c  mov     dword ptr [rbp+30h+var_A8+8], r12d
0x140013620  lea     rdx, [rbp+30h+var_58]
0x140013624  movups  [rsp+130h+var_B8], xmm0
0x140013629  call    BwcGetQoSParameters
0x14001362e  lea     rcx, [rsi+1D8h]; SpinLock
0x140013635  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001363c  nop     dword ptr [rax+rax+00h]
0x140013641  cmp     dword ptr [rsi+1D0h], 0
0x140013648  mov     [rsi+1E0h], al
0x14001364e  jnz     short loc_140013699
0x140013650  mov     rax, [rbx+20h]
0x140013654  mov     rcx, [rbx+10h]
0x140013658  test    rax, rax
0x14001365b  jnz     short loc_140013665
0x14001365d  mov     eax, [rsp+130h+var_EC]
0x140013661  imul    rax, rcx
0x140013665  shr     rax, 3
0x140013669  mov     [rbp+30h+var_68], rax
0x14001366d  mov     rax, [rbx+18h]
0x140013671  test    rax, rax
0x140013674  jnz     short loc_14001367E
0x140013676  mov     eax, [rsp+130h+var_E8]
0x14001367a  imul    rax, rcx
0x14001367e  shr     rax, 3
0x140013682  shr     rcx, 3
0x140013686  mov     [rbp+30h+var_70], rcx
0x14001368a  mov     [rbp+30h+var_60], rax
0x14001368e  mov     [rbp+30h+var_50], 0FFFFFFFFh
0x140013695  mov     [rbp+30h+var_4C], r12d
0x140013699  xor     ecx, ecx; ProcNumber
0x14001369b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400136a2  nop     dword ptr [rax+rax+00h]
0x1400136a7  mov     r8b, r12b
0x1400136aa  mov     dl, r12b
0x1400136ad  mov     ecx, eax
0x1400136af  mov     r14d, eax
0x1400136b2  call    QosTimerGetCurrentTime
0x1400136b7  lea     r15, [rsi+28h]
0x1400136bb  mov     rdx, rax
0x1400136be  mov     rcx, r15
0x1400136c1  lea     r8, [rbp+30h+var_98]
0x1400136c5  call    QosFlowNeedQueueFeedback
0x1400136ca  test    al, al
0x1400136cc  jz      short loc_14001372F
0x1400136ce  mov     rcx, [rdi]; Lock
0x1400136d1  lea     rdx, [rsp+130h+LockState]; LockState
0x1400136d6  mov     r8b, r12b; Flags
0x1400136d9  call    cs:__imp_NdisAcquireRWLockWrite
0x1400136e0  nop     dword ptr [rax+rax+00h]
0x1400136e5  lea     rbx, [rdi+8]
0x1400136e9  mov     edx, r14d
0x1400136ec  mov     rcx, rbx
0x1400136ef  call    QosLineNeedSignal
0x1400136f4  test    al, al
0x1400136f6  jz      short loc_140013703
0x1400136f8  mov     edx, r14d
0x1400136fb  mov     rcx, rbx
0x1400136fe  call    QosLineSignalExternalEvent
0x140013703  lea     r8, [rbp+30h+var_98]
0x140013707  mov     rcx, rbx
0x14001370a  call    QosLineQueryQueueFeedback
0x14001370f  mov     rcx, [rdi]; Lock
0x140013712  lea     rdx, [rsp+130h+LockState]; LockState
0x140013717  call    cs:__imp_NdisReleaseRWLock
0x14001371e  nop     dword ptr [rax+rax+00h]
0x140013723  lea     rdx, [rbp+30h+var_98]
0x140013727  mov     rcx, r15
0x14001372a  call    QosTbcAdjustSendWindow
0x14001372f  or      [rbp+30h+var_34], r12d
0x140013733  xor     r10d, r10d
0x140013736  mov     r8d, [rbp+30h+var_38]
0x14001373a  cmp     r8d, 0FFFFFFFFh
0x14001373e  jz      short loc_14001377C
0x140013740  mov     r9d, [r15+140h]
0x140013747  mov     ecx, r8d
0x14001374a  sub     ecx, r9d
0x14001374d  cmp     ecx, r8d
0x140013750  jnz     short loc_140013757
0x140013752  mov     edx, r12d
0x140013755  jmp     short loc_140013766
0x140013757  xor     edx, edx
0x140013759  mov     eax, r9d
0x14001375c  neg     eax
0x14001375e  cmp     ecx, eax
0x140013760  setnz   dl
0x140013763  sub     edx, r12d
0x140013766  test    ecx, ecx
0x140013768  jz      short loc_14001377C
0x14001376a  mov     dword ptr [rsp+130h+var_B8], r9d
0x14001376f  mov     dword ptr [rsp+130h+var_B8+4], r8d
0x140013774  mov     dword ptr [rbp+30h+var_B8+8], ecx
0x140013777  mov     dword ptr [rbp+30h+var_B8+0Ch], edx
0x14001377a  jmp     short loc_1400137BC
0x14001377c  lea     rax, [rsp+130h+var_E0]
0x140013781  mov     r9d, r10d
0x140013784  mov     [rsp+130h+var_100], rax
0x140013789  lea     r8, [rbp+30h+var_70]
0x14001378d  lea     rax, [rsp+130h+var_D8]
0x140013792  mov     edx, r14d
0x140013795  mov     [rsp+130h+var_108], rax
0x14001379a  mov     rcx, r15
0x14001379d  lea     rax, [rsp+130h+var_E4]
0x1400137a2  mov     [rsp+130h+var_110], rax
0x1400137a7  call    QosFlowUpdateComplete
0x1400137ac  mov     r12d, eax
0x1400137af  cmp     eax, 103h
0x1400137b4  jnz     short loc_14001382F
0x1400137b6  mov     r12d, 1
0x1400137bc  mov     rcx, [rdi]; Lock
0x1400137bf  lea     rdx, [rsp+130h+LockState]; LockState
0x1400137c4  mov     r8b, r12b; Flags
0x1400137c7  call    cs:__imp_NdisAcquireRWLockWrite
0x1400137ce  nop     dword ptr [rax+rax+00h]
0x1400137d3  lea     rcx, [rdi+8]
0x1400137d7  xor     r8d, r8d
0x1400137da  lea     r9, [rsp+130h+var_B8]
0x1400137df  xor     edx, edx
0x1400137e1  call    QosLineUpdate
0x1400137e6  mov     rcx, [rdi]; Lock
0x1400137e9  lea     rdx, [rsp+130h+LockState]; LockState
0x1400137ee  mov     ebx, eax
0x1400137f0  call    cs:__imp_NdisReleaseRWLock
0x1400137f7  nop     dword ptr [rax+rax+00h]
0x1400137fc  lea     rax, [rsp+130h+var_E0]
0x140013801  mov     r9d, ebx
0x140013804  mov     [rsp+130h+var_100], rax
0x140013809  lea     r8, [rbp+30h+var_70]
0x14001380d  lea     rax, [rsp+130h+var_D8]
0x140013812  mov     edx, r14d
0x140013815  mov     [rsp+130h+var_108], rax
0x14001381a  mov     rcx, r15
0x14001381d  lea     rax, [rsp+130h+var_E4]
0x140013822  mov     [rsp+130h+var_110], rax
0x140013827  call    QosFlowUpdateComplete
0x14001382c  mov     r12d, eax
0x14001382f  mov     r8, [rsp+130h+var_E0]
0x140013834  test    r8, r8
0x140013837  jz      short loc_14001385D
0x140013839  lea     r9, [rsp+130h+var_D0]
0x14001383e  mov     rdx, rdi
0x140013841  mov     rcx, rsi
0x140013844  call    BwcDropNbls
0x140013849  mov     rax, cs:DropQueuedNonConformantNbls
0x140013850  mov     rcx, rsi
0x140013853  mov     rdx, [rsp+130h+var_D0]
0x140013858  call    _guard_dispatch_icall
0x14001385d  mov     r15, [rsp+130h+var_D8]
0x140013862  test    r15, r15
0x140013865  jz      loc_1400138F5
0x14001386b  lea     rbx, [rdi+8]
0x14001386f  mov     edx, r14d
0x140013872  mov     rcx, rbx
0x140013875  call    QosLineNeedSignal
0x14001387a  test    al, al
0x14001387c  jz      short loc_1400138B4
0x14001387e  mov     rcx, [rdi]; Lock
0x140013881  lea     rdx, [rsp+130h+LockState]; LockState
0x140013886  mov     r8b, 1; Flags
0x140013889  call    cs:__imp_NdisAcquireRWLockWrite
0x140013890  nop     dword ptr [rax+rax+00h]
0x140013895  mov     edx, r14d
0x140013898  mov     rcx, rbx
0x14001389b  call    QosLineSignalExternalEvent
0x1400138a0  mov     rcx, [rdi]; Lock
0x1400138a3  lea     rdx, [rsp+130h+LockState]; LockState
0x1400138a8  call    cs:__imp_NdisReleaseRWLock
0x1400138af  nop     dword ptr [rax+rax+00h]
0x1400138b4  lea     rax, [rsp+130h+var_E0]
0x1400138b9  mov     r8, r15
0x1400138bc  mov     [rsp+130h+var_108], rax
0x1400138c1  mov     rcx, rbx
0x1400138c4  lea     rax, [rsp+130h+var_C8]
0x1400138c9  mov     [rsp+130h+var_110], rax
0x1400138ce  call    QosLineSendNetBufferLists
0x1400138d3  mov     r8, [rsp+130h+var_C8]
0x1400138d8  lea     r9, [rsp+130h+var_C0]
0x1400138dd  mov     rdx, rdi
0x1400138e0  mov     rcx, rsi
0x1400138e3  call    BwcCompleteNbls
0x1400138e8  mov     rdx, [rsp+130h+var_C0]
0x1400138ed  mov     rcx, rsi
0x1400138f0  call    BwcSendProcessedNbls
0x1400138f5  mov     dl, [rsi+1E0h]; NewIrql
0x1400138fb  lea     rcx, [rsi+1D8h]; SpinLock
0x140013902  call    cs:__imp_KeReleaseSpinLock
0x140013909  nop     dword ptr [rax+rax+00h]
0x14001390e  mov     eax, r12d
0x140013911  mov     rcx, [rbp+30h+var_30]
0x140013915  xor     rcx, rsp; StackCookie
0x140013918  call    __security_check_cookie
0x14001391d  lea     r11, [rsp+130h+var_20]
0x140013925  mov     rbx, [r11+40h]
0x140013929  mov     rsi, [r11+48h]
0x14001392d  mov     rsp, r11
0x140013930  pop     r15
0x140013932  pop     r14
0x140013934  pop     r12
0x140013936  pop     rdi
0x140013937  pop     rbp
0x140013938  retn
```
