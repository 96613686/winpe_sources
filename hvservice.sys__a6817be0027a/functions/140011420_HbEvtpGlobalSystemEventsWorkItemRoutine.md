# HbEvtpGlobalSystemEventsWorkItemRoutine

- ea: `0x140011420`
- end: `0x140011599`
- name: `HbEvtpGlobalSystemEventsWorkItemRoutine`
- size: `377`
- prototype: `void __fastcall(_QWORD *IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001230`
- `0x140001600`
- `0x140011420`
- `0x140012524`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001157b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001157b`
- `ntoskrnl!IoFreeWorkItem` at `0x14001154a`
- `ntoskrnl!IoFreeWorkItem` at `0x14001154a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001144b`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001144b`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140011562`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140011562`
- `winhvr!WinHvReleaseEventLogBuffer` at `0x140011534`
- `winhvr!WinHvReleaseEventLogBuffer` at `0x140011534`

## string_xrefs

- `0x140011494`: `Failed to get config`

## pseudocode

```c
void __fastcall HbEvtpGlobalSystemEventsWorkItemRoutine(_QWORD *IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)
{
  struct _IO_REMOVE_LOCK *v3; // rbp
  unsigned int v5; // edi
  char v6; // r14
  __int64 *v7; // r13
  unsigned int *v8; // rbx
  unsigned int v9; // r15d
  unsigned int *i; // rsi
  __int64 v11; // rax
  unsigned int v12; // ebx
  __int64 *v13; // [rsp+70h] [rbp+8h] BYREF

  v3 = (struct _IO_REMOVE_LOCK *)IoObject[8];
  v13 = 0;
  v5 = (unsigned int)Context;
  if ( ExAcquireRundownProtection(&stru_1400092E8) )
  {
    v6 = 1;
    if ( (int)HbEvtpGetLogConfiguration(0, &v13) >= 0 )
    {
      if ( HvBootDriverControlGuid_Context )
      {
        if ( v5 != -1 )
        {
          v7 = v13;
          do
          {
            v8 = *(unsigned int **)(112LL * v5 + v7[4]);
            if ( !v8 )
              break;
            v9 = 0;
            for ( i = v8 + 18; v9 < v8[12]; i = (unsigned int *)((char *)i + v11) )
            {
              if ( i >= (unsigned int *)((char *)v8 + *v8) )
                break;
              HbEvtpLogGlobalSystemEvent(i);
              v11 = *((unsigned __int16 *)i + 2);
              v9 += v11;
            }
            v12 = v8[14];
            WinHvReleaseEventLogBuffer(0, v5);
            v5 = v12;
          }
          while ( v12 != -1 );
        }
      }
      else
      {
        HbpTraceEvent(
          1,
          "HbEvtpGlobalSystemEventsWorkItemRoutine",
          3533,
          "Microsoft_Windows_Hyper_V_HypervisorHandle == 0");
      }
    }
    else
    {
      HbpTraceEvent(1, "HbEvtpGlobalSystemEventsWorkItemRoutine", 3525, "Failed to get config");
    }
  }
  else
  {
    v6 = 0;
    HbpTraceEvent(1, "HbEvtpGlobalSystemEventsWorkItemRoutine", 3517, "Rundown not available");
  }
  IoFreeWorkItem(IoWorkItem);
  if ( v6 )
    ExReleaseRundownProtection(&stru_1400092E8);
  IoReleaseRemoveLockEx(v3 + 2, v3, 0x20u);
}

```

## disassembly

```asm
0x140011420  push    rbx
0x140011422  push    rbp
0x140011423  push    rsi
0x140011424  push    rdi
0x140011425  push    r12
0x140011427  push    r13
0x140011429  push    r14
0x14001142b  push    r15
0x14001142d  sub     rsp, 28h
0x140011431  mov     rbp, [rcx+40h]
0x140011435  mov     r12, r8
0x140011438  lea     rcx, stru_1400092E8; RunRef
0x14001143f  mov     [rsp+68h+arg_0], 0
0x140011448  mov     rdi, rdx
0x14001144b  call    cs:__imp_ExAcquireRundownProtection
0x140011452  nop     dword ptr [rax+rax+00h]
0x140011457  test    al, al
0x140011459  jnz     short loc_140011481
0x14001145b  xor     r14b, r14b
0x14001145e  lea     r9, aRundownNotAvai; "Rundown not available"
0x140011465  mov     r8d, 0DBDh
0x14001146b  lea     rdx, aHbevtpglobalsy; "HbEvtpGlobalSystemEventsWorkItemRoutine"
0x140011472  mov     ecx, 1
0x140011477  call    HbpTraceEvent
0x14001147c  jmp     loc_140011547
0x140011481  lea     rdx, [rsp+68h+arg_0]
0x140011486  xor     ecx, ecx
0x140011488  mov     r14b, 1
0x14001148b  call    HbEvtpGetLogConfiguration
0x140011490  test    eax, eax
0x140011492  jns     short loc_1400114B7
0x140011494  lea     r9, aFailedToGetCon; "Failed to get config"
0x14001149b  mov     r8d, 0DC5h
0x1400114a1  lea     rdx, aHbevtpglobalsy; "HbEvtpGlobalSystemEventsWorkItemRoutine"
0x1400114a8  mov     ecx, 1
0x1400114ad  call    HbpTraceEvent
0x1400114b2  jmp     loc_140011547
0x1400114b7  cmp     cs:HvBootDriverControlGuid_Context, 0
0x1400114bf  jnz     short loc_1400114E1
0x1400114c1  lea     r9, aMicrosoftWindo; "Microsoft_Windows_Hyper_V_HypervisorHan"...
0x1400114c8  mov     r8d, 0DCDh
0x1400114ce  lea     rdx, aHbevtpglobalsy; "HbEvtpGlobalSystemEventsWorkItemRoutine"
0x1400114d5  mov     ecx, 1
0x1400114da  call    HbpTraceEvent
0x1400114df  jmp     short loc_140011547
0x1400114e1  cmp     edi, 0FFFFFFFFh
0x1400114e4  jz      short loc_140011547
0x1400114e6  mov     r13, [rsp+68h+arg_0]
0x1400114eb  mov     eax, edi
0x1400114ed  imul    rcx, rax, 70h ; 'p'
0x1400114f1  mov     rax, [r13+20h]
0x1400114f5  mov     rbx, [rcx+rax]
0x1400114f9  test    rbx, rbx
0x1400114fc  jz      short loc_140011547
0x1400114fe  xor     r15d, r15d
0x140011501  lea     rsi, [rbx+48h]
0x140011505  cmp     [rbx+30h], r15d
0x140011509  jbe     short loc_14001152D
0x14001150b  mov     eax, [rbx]
0x14001150d  add     rax, rbx
0x140011510  cmp     rsi, rax
0x140011513  jnb     short loc_14001152D
0x140011515  mov     rcx, rsi
0x140011518  call    HbEvtpLogGlobalSystemEvent
0x14001151d  movzx   eax, word ptr [rsi+4]
0x140011521  add     r15d, eax
0x140011524  add     rsi, rax
0x140011527  cmp     r15d, [rbx+30h]
0x14001152b  jb      short loc_14001150B
0x14001152d  mov     ebx, [rbx+38h]
0x140011530  mov     edx, edi
0x140011532  xor     ecx, ecx
0x140011534  call    cs:__imp_WinHvReleaseEventLogBuffer
0x14001153b  nop     dword ptr [rax+rax+00h]
0x140011540  mov     edi, ebx
0x140011542  cmp     ebx, 0FFFFFFFFh
0x140011545  jnz     short loc_1400114EB
0x140011547  mov     rcx, r12; IoWorkItem
0x14001154a  call    cs:__imp_IoFreeWorkItem
0x140011551  nop     dword ptr [rax+rax+00h]
0x140011556  test    r14b, r14b
0x140011559  jz      short loc_14001156E
0x14001155b  lea     rcx, stru_1400092E8; RunRef
0x140011562  call    cs:__imp_ExReleaseRundownProtection
0x140011569  nop     dword ptr [rax+rax+00h]
0x14001156e  lea     rcx, [rbp+40h]; RemoveLock
0x140011572  mov     r8d, 20h ; ' '; RemlockSize
0x140011578  mov     rdx, rbp; Tag
0x14001157b  call    cs:__imp_IoReleaseRemoveLockEx
0x140011582  nop     dword ptr [rax+rax+00h]
0x140011587  add     rsp, 28h
0x14001158b  pop     r15
0x14001158d  pop     r14
0x14001158f  pop     r13
0x140011591  pop     r12
0x140011593  pop     rdi
0x140011594  pop     rsi
0x140011595  pop     rbp
0x140011596  pop     rbx
0x140011597  retn
```
