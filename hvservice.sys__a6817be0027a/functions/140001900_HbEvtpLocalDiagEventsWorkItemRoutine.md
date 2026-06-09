# HbEvtpLocalDiagEventsWorkItemRoutine

- ea: `0x140001900`
- end: `0x140001ae6`
- name: `HbEvtpLocalDiagEventsWorkItemRoutine`
- size: `486`
- prototype: `void __fastcall(__int64, __int64 *, struct _IO_WORKITEM *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001230`
- `0x140001600`
- `0x140001900`
- `0x140011e18`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001acc`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001acc`
- `ntoskrnl!IoFreeWorkItem` at `0x140001ab3`
- `ntoskrnl!IoFreeWorkItem` at `0x140001ab3`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x140001991`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x140001991`
- `ntoskrnl!ExReleaseFastMutex` at `0x140001aa4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140001aa4`
- `ntoskrnl!KeSetEvent` at `0x140001a60`
- `ntoskrnl!KeSetEvent` at `0x140001a60`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000193e`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000193e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000192b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000192b`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001a95`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001a95`

## pseudocode

```c
void __fastcall HbEvtpLocalDiagEventsWorkItemRoutine(__int64 a1, __int64 *a2, struct _IO_WORKITEM *a3)
{
  __int64 v3; // rbp
  int LogConfiguration; // eax
  union _SLIST_HEADER *v6; // rdi
  PSLIST_ENTRY v7; // rax
  _QWORD *v8; // rsi
  _QWORD *p_Next; // rdx
  _QWORD *v10; // rbx
  _QWORD *Alignment; // rsi
  _QWORD *v12; // rbx
  LONG v13; // eax
  union _SLIST_HEADER *v14; // [rsp+78h] [rbp+10h] BYREF

  v14 = (union _SLIST_HEADER *)a2;
  v3 = *(_QWORD *)(a1 + 64);
  v14 = 0;
  ExAcquireFastMutex((PFAST_MUTEX)(v3 + 272));
  if ( ExAcquireRundownProtection(&RunRef) )
  {
    LogConfiguration = HbEvtpGetLogConfiguration(1, (__int64 **)&v14);
    v6 = v14;
    if ( LogConfiguration >= 0 )
    {
      v7 = ExpInterlockedFlushSList(v14 + 7);
      v8 = 0;
      while ( v7 )
      {
        p_Next = &v7->Next;
        v7 = v7->Next;
        *p_Next = v8;
        v8 = p_Next;
      }
      while ( v8 )
      {
        v10 = v8;
        v8 = (_QWORD *)*v8;
        HbpTraceEvent(
          3,
          "HbEvtpLocalDiagEventsWorkItemRoutine",
          4239,
          "Processing buffer list with head at index %d",
          *((_DWORD *)v10 - 3));
        HbEvtpLocalDiagWriteBufferList(v3, v6, *((unsigned int *)v10 - 3));
      }
      Alignment = (_QWORD *)v6[8].Alignment;
      v6[8].Alignment = 0;
      while ( Alignment )
      {
        v12 = Alignment;
        Alignment = (_QWORD *)*Alignment;
        HbpTraceEvent(
          3,
          "HbEvtpLocalDiagEventsWorkItemRoutine",
          4265,
          "Trying to process out-of-order buffer %d",
          *((_DWORD *)v12 - 3));
        HbEvtpLocalDiagWriteBufferList(v3, v6, *((unsigned int *)v12 - 3));
      }
    }
    if ( v6 && LODWORD(v6[3].Alignment) == 1 )
    {
      v13 = KeSetEvent(&HbEvtpCompleteBufferAsyncEvent, 0, 0);
      HbpTraceEvent(3, "HbEvtpLocalDiagEventsWorkItemRoutine", 4284, "Set async event (previous state: %d)", v13);
    }
    ExReleaseRundownProtection(&RunRef);
  }
  else
  {
    HbpTraceEvent(1, "HbEvtpLocalDiagEventsWorkItemRoutine", 4199, "Rundown not available");
  }
  ExReleaseFastMutex((PFAST_MUTEX)(v3 + 272));
  IoFreeWorkItem(a3);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v3 + 64), (PVOID)v3, 0x20u);
}

```

## disassembly

```asm
0x140001900  mov     [rsp+arg_8], rdx
0x140001905  push    rbx
0x140001906  push    rbp
0x140001907  push    rsi
0x140001908  push    rdi
0x140001909  push    r14
0x14000190b  push    r15
0x14000190d  sub     rsp, 38h
0x140001911  mov     rbp, [rcx+40h]
0x140001915  mov     r15, r8
0x140001918  mov     [rsp+68h+arg_8], 0
0x140001921  lea     r14, [rbp+110h]
0x140001928  mov     rcx, r14; FastMutex
0x14000192b  call    cs:__imp_ExAcquireFastMutex
0x140001932  nop     dword ptr [rax+rax+00h]
0x140001937  lea     rcx, RunRef; RunRef
0x14000193e  call    cs:__imp_ExAcquireRundownProtection
0x140001945  nop     dword ptr [rax+rax+00h]
0x14000194a  test    al, al
0x14000194c  jnz     short loc_140001971
0x14000194e  lea     r9, aRundownNotAvai; "Rundown not available"
0x140001955  mov     r8d, 1067h
0x14000195b  lea     rdx, aHbevtplocaldia_3; "HbEvtpLocalDiagEventsWorkItemRoutine"
0x140001962  mov     ecx, 1
0x140001967  call    HbpTraceEvent
0x14000196c  jmp     loc_140001AA1
0x140001971  lea     rdx, [rsp+68h+arg_8]
0x140001976  mov     ecx, 1
0x14000197b  call    HbEvtpGetLogConfiguration
0x140001980  mov     rdi, [rsp+68h+arg_8]
0x140001985  test    eax, eax
0x140001987  js      loc_140001A49
0x14000198d  lea     rcx, [rdi+70h]; ListHead
0x140001991  call    cs:__imp_ExpInterlockedFlushSList
0x140001998  nop     dword ptr [rax+rax+00h]
0x14000199d  xor     esi, esi
0x14000199f  jmp     short loc_1400019B0
0x1400019a1  mov     rdx, rax
0x1400019a4  mov     rcx, rax
0x1400019a7  mov     rax, [rax]
0x1400019aa  mov     [rdx], rsi
0x1400019ad  mov     rsi, rdx
0x1400019b0  test    rax, rax
0x1400019b3  jnz     short loc_1400019A1
0x1400019b5  jmp     short loc_1400019F1
0x1400019b7  lea     rbx, [rsi]
0x1400019ba  mov     rsi, [rsi]
0x1400019bd  mov     eax, [rbx-0Ch]
0x1400019c0  lea     r9, aProcessingBuff; "Processing buffer list with head at ind"...
0x1400019c7  mov     r8d, 108Fh
0x1400019cd  mov     [rsp+68h+var_48], eax
0x1400019d1  lea     rdx, aHbevtplocaldia_3; "HbEvtpLocalDiagEventsWorkItemRoutine"
0x1400019d8  mov     ecx, 3
0x1400019dd  call    HbpTraceEvent
0x1400019e2  mov     r8d, [rbx-0Ch]
0x1400019e6  mov     rdx, rdi
0x1400019e9  mov     rcx, rbp
0x1400019ec  call    HbEvtpLocalDiagWriteBufferList
0x1400019f1  test    rsi, rsi
0x1400019f4  jnz     short loc_1400019B7
0x1400019f6  mov     rsi, [rdi+80h]
0x1400019fd  mov     qword ptr [rdi+80h], 0
0x140001a08  jmp     short loc_140001A44
0x140001a0a  lea     rbx, [rsi]
0x140001a0d  mov     rsi, [rsi]
0x140001a10  mov     eax, [rbx-0Ch]
0x140001a13  lea     r9, aTryingToProces; "Trying to process out-of-order buffer %"...
0x140001a1a  mov     r8d, 10A9h
0x140001a20  mov     [rsp+68h+var_48], eax
0x140001a24  lea     rdx, aHbevtplocaldia_3; "HbEvtpLocalDiagEventsWorkItemRoutine"
0x140001a2b  mov     ecx, 3
0x140001a30  call    HbpTraceEvent
0x140001a35  mov     r8d, [rbx-0Ch]
0x140001a39  mov     rdx, rdi
0x140001a3c  mov     rcx, rbp
0x140001a3f  call    HbEvtpLocalDiagWriteBufferList
0x140001a44  test    rsi, rsi
0x140001a47  jnz     short loc_140001A0A
0x140001a49  test    rdi, rdi
0x140001a4c  jz      short loc_140001A8E
0x140001a4e  cmp     dword ptr [rdi+30h], 1
0x140001a52  jnz     short loc_140001A8E
0x140001a54  xor     r8d, r8d; Wait
0x140001a57  lea     rcx, HbEvtpCompleteBufferAsyncEvent; Event
0x140001a5e  xor     edx, edx; Increment
0x140001a60  call    cs:__imp_KeSetEvent
0x140001a67  nop     dword ptr [rax+rax+00h]
0x140001a6c  lea     r9, aSetAsyncEventP; "Set async event (previous state: %d)"
0x140001a73  mov     [rsp+68h+var_48], eax
0x140001a77  mov     r8d, 10BCh
0x140001a7d  lea     rdx, aHbevtplocaldia_3; "HbEvtpLocalDiagEventsWorkItemRoutine"
0x140001a84  mov     ecx, 3
0x140001a89  call    HbpTraceEvent
0x140001a8e  lea     rcx, RunRef; RunRef
0x140001a95  call    cs:__imp_ExReleaseRundownProtection
0x140001a9c  nop     dword ptr [rax+rax+00h]
0x140001aa1  mov     rcx, r14; FastMutex
0x140001aa4  call    cs:__imp_ExReleaseFastMutex
0x140001aab  nop     dword ptr [rax+rax+00h]
0x140001ab0  mov     rcx, r15; IoWorkItem
0x140001ab3  call    cs:__imp_IoFreeWorkItem
0x140001aba  nop     dword ptr [rax+rax+00h]
0x140001abf  lea     rcx, [rbp+40h]; RemoveLock
0x140001ac3  mov     r8d, 20h ; ' '; RemlockSize
0x140001ac9  mov     rdx, rbp; Tag
0x140001acc  call    cs:__imp_IoReleaseRemoveLockEx
0x140001ad3  nop     dword ptr [rax+rax+00h]
0x140001ad8  add     rsp, 38h
0x140001adc  pop     r15
0x140001ade  pop     r14
0x140001ae0  pop     rdi
0x140001ae1  pop     rsi
0x140001ae2  pop     rbp
0x140001ae3  pop     rbx
0x140001ae4  retn
```
