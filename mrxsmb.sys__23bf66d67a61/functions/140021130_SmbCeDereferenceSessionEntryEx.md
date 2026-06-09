# SmbCeDereferenceSessionEntryEx

- ea: `0x140021130`
- end: `0x1400213a5`
- name: `SmbCeDereferenceSessionEntryEx`
- size: `629`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `16`
- callee_count: `5`
- tags: ``

## callers

- `0x1400017f0`
- `0x1400093a0`
- `0x140022950`
- `0x140024330`
- `0x140027dc0`
- `0x14002dab0`
- `0x14002dff0`
- `0x14002e770`
- `0x1400302f0`
- `0x140030a20`
- `0x140045c60`
- `0x140046170`
- `0x1400461fc`
- `0x14004ad90`
- `0x14004b33c`
- `0x14004b4cc`

## callees

- `0x140003480`
- `0x140005540`
- `0x140005f10`
- `0x140021130`
- `0x140037fa4`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140021372`
- `ntoskrnl!KeBugCheckEx` at `0x140021398`
- `ntoskrnl!KeBugCheckEx` at `0x140021372`
- `ntoskrnl!KeBugCheckEx` at `0x140021398`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140021348`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140021348`
- `rdbss!RxPostToWorkerThread` at `0x14002126b`
- `rdbss!RxPostToWorkerThread` at `0x14002126b`

## pseudocode

```c
int __fastcall SmbCeDereferenceSessionEntryEx(unsigned __int16 *BugCheckParameter2, char a2)
{
  signed __int32 v4; // ebx
  PDEVICE_OBJECT *v5; // rax
  __int64 v6; // rbx
  KIRQL v7; // bp
  int v8; // r8d
  __int64 v9; // rdx
  unsigned __int16 **v10; // rax
  signed __int32 v11; // ecx
  char v12; // cc
  signed __int32 v13; // ecx
  signed __int32 v14; // eax
  signed __int32 v15; // eax
  __int64 v16; // rax
  __int64 *v17; // rdx
  int v18; // ecx
  __int64 v19; // rax
  __int64 v20; // rax

  v4 = _InterlockedDecrement((volatile signed __int32 *)BugCheckParameter2 + 2);
  v5 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)v5 & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      LODWORD(v5) = WPP_SF_qDD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      22,
                      WPP_84a53c2c5f823219b45553a65390e18c_Traceguids,
                      BugCheckParameter2,
                      v4 + 1,
                      v4);
  }
  if ( !v4 )
  {
    v6 = *((_QWORD *)BugCheckParameter2 + 3);
    v7 = 0;
    if ( !a2 )
      v7 = SmbCeAcquireSpinLock(v6);
    v8 = BugCheckParameter2[6];
    if ( (_WORD)v8 == 10 )
      goto LABEL_10;
    if ( *BugCheckParameter2 == 57858 )
    {
      if ( (byte_1400712C1 & 4) == 0 )
        goto LABEL_10;
      v16 = *((_QWORD *)BugCheckParameter2 + 48);
      v17 = SessionStateTransition;
      v18 = *(unsigned __int16 *)(v16 + 80);
      v19 = *(_QWORD *)(v16 + 88);
    }
    else
    {
      if ( *BugCheckParameter2 != 57860 || (byte_1400712C1 & 4) == 0 )
        goto LABEL_10;
      v20 = *((_QWORD *)BugCheckParameter2 + 53);
      v17 = VNetRootStateTransition;
      v18 = *(unsigned __int16 *)(v20 + 96);
      v19 = *(_QWORD *)(v20 + 104);
    }
    LOWORD(v18) = (unsigned __int16)v18 >> 1;
    McTemplateK0phhqhzr4_EtwWriteTransfer(v18, (_DWORD)v17, v8, (_DWORD)BugCheckParameter2, v8, 10, 12, v18, v19);
LABEL_10:
    *((_DWORD *)BugCheckParameter2 + 3) = 10;
    SmbCeUpperDisconnectAllBindingObjectsLite(BugCheckParameter2, 3221225996LL);
    v9 = *((_QWORD *)BugCheckParameter2 + 49);
    if ( *(unsigned __int16 **)(v9 + 8) != BugCheckParameter2 + 196
      || (v10 = (unsigned __int16 **)*((_QWORD *)BugCheckParameter2 + 50), *v10 != BugCheckParameter2 + 196) )
    {
      __fastfail(3u);
    }
    *v10 = (unsigned __int16 *)v9;
    *(_QWORD *)(v9 + 8) = v10;
    if ( !a2 )
    {
      *(_DWORD *)(v6 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v6 + 1920), v7);
    }
    *((_QWORD *)BugCheckParameter2 + 26) = BugCheckParameter2 + 100;
    *((_QWORD *)BugCheckParameter2 + 25) = BugCheckParameter2 + 100;
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 2668));
    v11 = _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 2640), 1u);
    v12 = (v11 + 1 < 0) ^ __OFADD__(1, v11) | (v11 == -1);
    v13 = v11 + 1;
    if ( v12 )
      KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)BugCheckParameter2, v13, 2u);
    v14 = _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 2664), 1u);
    v12 = (v14 + 1 < 0) ^ __OFADD__(1, v14) | (v14 == -1);
    v15 = v14 + 1;
    if ( v12 )
      KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)BugCheckParameter2, v15, 8u);
    LODWORD(v5) = RxPostToWorkerThread(
                    (PRDBSS_DEVICE_OBJECT)v6,
                    NormalWorkQueue,
                    (PRX_WORK_QUEUE_ITEM)BugCheckParameter2 + 5,
                    SmbCepTearDownSessionEntry,
                    BugCheckParameter2);
  }
  return (int)v5;
}

```

## disassembly

```asm
0x140021130  push    rbx
0x140021132  push    rsi
0x140021133  push    rdi
0x140021134  sub     rsp, 50h
0x140021138  movzx   esi, dl
0x14002113b  mov     rdi, rcx
0x14002113e  mov     ebx, 0FFFFFFFFh
0x140021143  lock xadd [rcx+8], ebx
0x140021148  dec     ebx
0x14002114a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140021151  lea     rax, WPP_GLOBAL_Control
0x140021158  cmp     rcx, rax
0x14002115b  jz      short loc_140021168
0x14002115d  mov     eax, [rcx+2Ch]
0x140021160  test    al, 40h
0x140021162  jnz     loc_1400212F1
0x140021168  test    ebx, ebx
0x14002116a  jz      short loc_140021175
0x14002116c  add     rsp, 50h
0x140021170  pop     rdi
0x140021171  pop     rsi
0x140021172  pop     rbx
0x140021173  retn
0x140021175  mov     rbx, [rdi+18h]
0x140021179  mov     [rsp+68h+arg_8], rbp
0x14002117e  xor     bpl, bpl
0x140021181  mov     [rsp+68h+arg_10], r14
0x140021189  test    sil, sil
0x14002118c  jz      loc_140021323
0x140021192  movzx   r8d, word ptr [rdi+0Ch]
0x140021197  mov     r14d, 0Ah
0x14002119d  cmp     r8w, r14w
0x1400211a1  jz      short loc_1400211C4
0x1400211a3  movzx   edx, word ptr [rdi]
0x1400211a6  sub     edx, 0E202h
0x1400211ac  jz      loc_140021288
0x1400211b2  cmp     edx, 2
0x1400211b5  jnz     short loc_1400211C4
0x1400211b7  test    cs:byte_1400712C1, 4
0x1400211be  jnz     loc_1400212AD
0x1400211c4  mov     dword ptr [rsp+68h+arg_0], 0C000020Ch
0x1400211cc  mov     rcx, rdi
0x1400211cf  mov     dword ptr [rsp+68h+arg_0+4], 0
0x1400211d7  mov     rdx, [rsp+68h+arg_0]
0x1400211dc  mov     [rdi+0Ch], r14d
0x1400211e0  call    SmbCeUpperDisconnectAllBindingObjectsLite
0x1400211e5  mov     r14, [rsp+68h+arg_10]
0x1400211ed  lea     rcx, [rdi+188h]
0x1400211f4  mov     rdx, [rcx]
0x1400211f7  cmp     [rdx+8], rcx
0x1400211fb  jnz     loc_140021281
0x140021201  mov     rax, [rcx+8]
0x140021205  cmp     [rax], rcx
0x140021208  jnz     short loc_140021281
0x14002120a  mov     [rax], rdx
0x14002120d  mov     [rdx+8], rax
0x140021211  test    sil, sil
0x140021214  jz      loc_140021333
0x14002121a  lea     r8, [rdi+0C8h]; pWorkQueueItem
0x140021221  mov     [r8+8], r8
0x140021225  mov     [r8], r8
0x140021228  lock inc dword ptr [rbx+0A6Ch]
0x14002122f  mov     eax, 1
0x140021234  mov     ecx, eax
0x140021236  lock xadd [rbx+0A50h], ecx
0x14002123e  add     ecx, eax
0x140021240  jle     loc_140021359
0x140021246  lock xadd [rbx+0A68h], eax
0x14002124e  add     eax, 1
0x140021251  jle     loc_14002137F
0x140021257  lea     r9, SmbCepTearDownSessionEntry; Routine
0x14002125e  mov     [rsp+68h+pContext], rdi; pContext
0x140021263  mov     edx, 3; WorkQueueType
0x140021268  mov     rcx, rbx; pMRxDeviceObject
0x14002126b  call    cs:__imp_RxPostToWorkerThread
0x140021272  nop     dword ptr [rax+rax+00h]
0x140021277  mov     rbp, [rsp+68h+arg_8]
0x14002127c  jmp     loc_14002116C
0x140021281  mov     ecx, 3
0x140021286  int     29h; Win8: RtlFailFast(ecx)
0x140021288  test    cs:byte_1400712C1, 4
0x14002128f  jz      loc_1400211C4
0x140021295  mov     rax, [rdi+180h]
0x14002129c  lea     rdx, SessionStateTransition
0x1400212a3  movzx   ecx, word ptr [rax+50h]
0x1400212a7  mov     rax, [rax+58h]
0x1400212ab  jmp     short loc_1400212C3
0x1400212ad  mov     rax, [rdi+1A8h]
0x1400212b4  lea     rdx, VNetRootStateTransition
0x1400212bb  movzx   ecx, word ptr [rax+60h]
0x1400212bf  mov     rax, [rax+68h]
0x1400212c3  mov     [rsp+68h+var_28], rax
0x1400212c8  mov     r9, rdi
0x1400212cb  shr     cx, 1
0x1400212ce  mov     [rsp+68h+var_30], cx
0x1400212d3  mov     [rsp+68h+var_38], 0C000020Ch
0x1400212db  mov     word ptr [rsp+68h+var_40], r14w
0x1400212e1  mov     word ptr [rsp+68h+pContext], r8w
0x1400212e7  call    McTemplateK0phhqhzr4_EtwWriteTransfer
0x1400212ec  jmp     loc_1400211C4
0x1400212f1  cmp     byte ptr [rcx+29h], 4
0x1400212f5  jb      loc_140021168
0x1400212fb  mov     rcx, [rcx+18h]
0x1400212ff  lea     eax, [rbx+1]
0x140021302  mov     edx, 16h
0x140021307  mov     [rsp+68h+var_40], ebx
0x14002130b  mov     r9, rdi
0x14002130e  mov     dword ptr [rsp+68h+pContext], eax
0x140021312  lea     r8, WPP_84a53c2c5f823219b45553a65390e18c_Traceguids
0x140021319  call    WPP_SF_qDD
0x14002131e  jmp     loc_140021168
0x140021323  mov     rcx, rbx
0x140021326  call    SmbCeAcquireSpinLock
0x14002132b  movzx   ebp, al
0x14002132e  jmp     loc_140021192
0x140021333  lea     rcx, [rbx+780h]; SpinLock
0x14002133a  mov     dword ptr [rbx+930h], 0FFFFFFFFh
0x140021344  movzx   edx, bpl; OldIrql
0x140021348  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002134f  nop     dword ptr [rax+rax+00h]
0x140021354  jmp     loc_14002121A
0x140021359  movsxd  r9, ecx; BugCheckParameter3
0x14002135c  mov     r8, rdi; BugCheckParameter2
0x14002135f  mov     ecx, 27h ; '''; BugCheckCode
0x140021364  mov     [rsp+68h+pContext], 2; BugCheckParameter4
0x14002136d  mov     edx, 0A0001h; BugCheckParameter1
0x140021372  call    cs:__imp_KeBugCheckEx
0x14002137f  movsxd  r9, eax; BugCheckParameter3
0x140021382  mov     r8, rdi; BugCheckParameter2
0x140021385  mov     edx, 0A0001h; BugCheckParameter1
0x14002138a  mov     [rsp+68h+pContext], 8; BugCheckParameter4
0x140021393  mov     ecx, 27h ; '''; BugCheckCode
0x140021398  call    cs:__imp_KeBugCheckEx
```
