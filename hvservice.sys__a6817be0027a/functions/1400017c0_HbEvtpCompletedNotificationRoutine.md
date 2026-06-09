# HbEvtpCompletedNotificationRoutine

- ea: `0x1400017c0`
- end: `0x1400018f1`
- name: `HbEvtpCompletedNotificationRoutine`
- size: `305`
- prototype: `void __fastcall(int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001600`
- `0x1400017c0`

## import_xrefs

- `ntoskrnl!KeInsertQueueDpc` at `0x1400018a2`
- `ntoskrnl!KeInsertQueueDpc` at `0x1400018a2`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140001884`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140001884`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140001820`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140001820`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400018d3`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400018d3`

## string_xrefs

- `0x1400017d6`: `HbEvtpCompletedNotificationRoutine`

## pseudocode

```c
void __fastcall HbEvtpCompletedNotificationRoutine(int a1, unsigned int a2)
{
  unsigned __int64 v2; // rsi
  void *v3; // rbx
  __int64 v4; // r14
  struct _EX_RUNDOWN_REF *v5; // r12
  unsigned int v6; // eax
  __int64 v7; // rdi
  void *v8; // rbp
  __int64 v9; // rsi

  v2 = a2;
  v3 = (void *)a1;
  HbpTraceEvent(
    3,
    "HbEvtpCompletedNotificationRoutine",
    4455,
    "Received notification for eventlogtype %d, buffer %d",
    a1,
    a2);
  if ( (_DWORD)v3 != 2 )
  {
    v4 = 18LL * (_QWORD)v3;
    v5 = (struct _EX_RUNDOWN_REF *)&HbEvtpEventLog[18 * (_QWORD)v3];
    if ( ExAcquireRundownProtection(v5 + 3) )
    {
      v6 = HbEvtpEventLog[v4 + 1];
      if ( (unsigned int)v2 < v6 && (v7 = HbEvtpEventLog[v4 + 4]) != 0 && v6 )
      {
        v8 = (void *)v2;
        v9 = 112 * v2;
        if ( (_DWORD)v3 != 1
          || !ExpInterlockedPushEntrySList((PSLIST_HEADER)&qword_1400092F0[v4 + 10], (PSLIST_ENTRY)(v7 + v9 + 96)) )
        {
          KeInsertQueueDpc((PRKDPC)(v7 + v9 + 16), v3, v8);
        }
      }
      else
      {
        HbpTraceEvent(1, "HbEvtpCompletedNotificationRoutine", 4488, "Eventlogtype %d has no buffers", (_DWORD)v3);
      }
      ExReleaseRundownProtection(v5 + 3);
    }
    else
    {
      HbpTraceEvent(
        1,
        "HbEvtpCompletedNotificationRoutine",
        4475,
        "Couldn't acquire rundown for event log type %d",
        (_DWORD)v3);
    }
  }
}

```

## disassembly

```asm
0x1400017c0  push    rbx
0x1400017c2  push    rbp
0x1400017c3  push    rsi
0x1400017c4  push    rdi
0x1400017c5  push    r12
0x1400017c7  push    r13
0x1400017c9  push    r14
0x1400017cb  push    r15
0x1400017cd  sub     rsp, 38h
0x1400017d1  mov     esi, edx
0x1400017d3  movsxd  rbx, ecx
0x1400017d6  lea     rbp, aHbevtpcomplete; "HbEvtpCompletedNotificationRoutine"
0x1400017dd  mov     [rsp+78h+var_50], esi
0x1400017e1  mov     rdx, rbp
0x1400017e4  mov     [rsp+78h+var_58], ebx
0x1400017e8  lea     r9, aReceivedNotifi; "Received notification for eventlogtype "...
0x1400017ef  mov     r8d, 1167h
0x1400017f5  mov     ecx, 3
0x1400017fa  call    HbpTraceEvent
0x1400017ff  cmp     ebx, 2
0x140001802  jz      loc_1400018DF
0x140001808  lea     r14, [rbx+rbx*8]
0x14000180c  shl     r14, 4
0x140001810  lea     r13, HbEvtpEventLog
0x140001817  lea     r12, [r14+r13]
0x14000181b  lea     rcx, [r12+18h]; RunRef
0x140001820  call    cs:__imp_ExAcquireRundownProtection
0x140001827  nop     dword ptr [rax+rax+00h]
0x14000182c  test    al, al
0x14000182e  jnz     short loc_140001853
0x140001830  lea     r9, aCouldnTAcquire; "Couldn't acquire rundown for event log "...
0x140001837  mov     [rsp+78h+var_58], ebx
0x14000183b  mov     r8d, 117Bh
0x140001841  mov     rdx, rbp
0x140001844  mov     ecx, 1
0x140001849  call    HbpTraceEvent
0x14000184e  jmp     loc_1400018DF
0x140001853  mov     eax, [r14+r13+8]
0x140001858  cmp     esi, eax
0x14000185a  jnb     short loc_1400018B0
0x14000185c  mov     rdi, [r14+r13+20h]
0x140001861  test    rdi, rdi
0x140001864  jz      short loc_1400018B0
0x140001866  test    eax, eax
0x140001868  jz      short loc_1400018B0
0x14000186a  mov     rbp, rsi
0x14000186d  imul    rsi, 70h ; 'p'
0x140001871  cmp     ebx, 1
0x140001874  jnz     short loc_140001895
0x140001876  lea     rdx, [rsi+60h]
0x14000187a  lea     rcx, [r13+70h]
0x14000187e  add     rdx, rdi; ListEntry
0x140001881  add     rcx, r14; ListHead
0x140001884  call    cs:__imp_ExpInterlockedPushEntrySList
0x14000188b  nop     dword ptr [rax+rax+00h]
0x140001890  test    rax, rax
0x140001893  jnz     short loc_1400018CE
0x140001895  lea     rcx, [rsi+10h]
0x140001899  mov     r8, rbp; SystemArgument2
0x14000189c  add     rcx, rdi; Dpc
0x14000189f  mov     rdx, rbx; SystemArgument1
0x1400018a2  call    cs:__imp_KeInsertQueueDpc
0x1400018a9  nop     dword ptr [rax+rax+00h]
0x1400018ae  jmp     short loc_1400018CE
0x1400018b0  lea     r9, aEventlogtypeDH; "Eventlogtype %d has no buffers"
0x1400018b7  mov     [rsp+78h+var_58], ebx
0x1400018bb  mov     r8d, 1188h
0x1400018c1  mov     rdx, rbp
0x1400018c4  mov     ecx, 1
0x1400018c9  call    HbpTraceEvent
0x1400018ce  lea     rcx, [r12+18h]; RunRef
0x1400018d3  call    cs:__imp_ExReleaseRundownProtection
0x1400018da  nop     dword ptr [rax+rax+00h]
0x1400018df  add     rsp, 38h
0x1400018e3  pop     r15
0x1400018e5  pop     r14
0x1400018e7  pop     r13
0x1400018e9  pop     r12
0x1400018eb  pop     rdi
0x1400018ec  pop     rsi
0x1400018ed  pop     rbp
0x1400018ee  pop     rbx
0x1400018ef  retn
```
