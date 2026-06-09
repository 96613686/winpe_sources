# EaiDisableAggregateEvent

- ea: `0x180001460`
- end: `0x1800016ab`
- name: `EaiDisableAggregateEvent`
- size: `587`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800013a0`
- `0x180004350`
- `0x180007de0`

## callees

- `0x180001460`
- `0x180003d90`
- `0x1800062e0`
- `0x1800072e0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001586`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800015c9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001586`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800015c9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001548`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001548`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800015a0`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800015a0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001536`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000167f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001536`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000167f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000154e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001565`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000154e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001565`

## pseudocode

```c
__int64 __fastcall EaiDisableAggregateEvent(__int64 a1)
{
  unsigned int v2; // esi
  _QWORD *v3; // rax
  unsigned int v5; // [rsp+30h] [rbp-49h] BYREF
  __int64 v6; // [rsp+38h] [rbp-41h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-39h] BYREF
  EVENT_DESCRIPTOR v8; // [rsp+50h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-19h] BYREF
  __int16 *v10; // [rsp+70h] [rbp-9h]
  int v11; // [rsp+78h] [rbp-1h]
  int v12; // [rsp+7Ch] [rbp+3h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+80h] [rbp+7h]
  __int64 v14; // [rsp+88h] [rbp+Fh]
  unsigned int *v15; // [rsp+90h] [rbp+17h]
  __int64 v16; // [rsp+98h] [rbp+1Fh]

  if ( (unsigned int)dword_180012000 > 4 )
  {
    v6 = a1;
    p_EventDescriptor = (EVENT_DESCRIPTOR *)&v6;
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_180012008;
    v14 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v10 = word_18000F6B2;
    UserData.Reserved = 2;
    v11 = 43;
    v12 = 1;
    v5 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  RtlAcquireSRWLockExclusive(a1 + 80);
  *(_DWORD *)(a1 + 88) = GetCurrentThreadId();
  if ( !*(_DWORD *)(a1 + 108) )
  {
    v2 = 0;
    goto LABEL_11;
  }
  EaLibClearAndReleaseTimer(a1);
  if ( *(_QWORD *)(a1 + 112) == GetCurrentThreadId() )
  {
    v2 = -1073741637;
LABEL_11:
    *(_DWORD *)(a1 + 88) = 0;
    RtlReleaseSRWLockExclusive(a1 + 80);
    goto LABEL_12;
  }
  *(_DWORD *)(a1 + 108) = 0;
  *(_DWORD *)(a1 + 88) = 0;
  RtlReleaseSRWLockExclusive(a1 + 80);
  v3 = *(_QWORD **)(a1 + 56);
  if ( *v3 && *(_QWORD *)*v3 )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    ***(_QWORD ***)(a1 + 56) = 0;
  }
  v2 = EaiSetAggregateConditionsEnabledState(a1, 0);
LABEL_12:
  if ( (unsigned int)dword_180012000 > 4 )
  {
    *(_QWORD *)&EventDescriptor.Id = a1;
    p_EventDescriptor = &EventDescriptor;
    v14 = 8;
    v15 = &v5;
    *(_DWORD *)&v8.Level = 516;
    UserData.Ptr = (ULONGLONG)off_180012008;
    v5 = v2;
    v16 = 4;
    *(_DWORD *)&v8.Id = 184549376;
    v8.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v10 = (__int16 *)byte_18000F715;
    UserData.Reserved = 2;
    v11 = 52;
    v12 = 1;
    LODWORD(v6) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &v8, 0, 0, 4u, &UserData);
  }
  return v2;
}

```

## disassembly

```asm
0x180001460  push    rbp
0x180001462  push    rbx
0x180001463  push    r12
0x180001465  push    r14
0x180001467  push    r15
0x180001469  lea     rbp, [rsp-37h]
0x18000146e  sub     rsp, 0B0h
0x180001475  mov     rax, cs:__security_cookie
0x18000147c  xor     rax, rsp
0x18000147f  mov     [rbp+57h+var_30], rax
0x180001483  mov     eax, cs:dword_180012000
0x180001489  lea     r14, _TraceLoggingMetadataEnd
0x180001490  xor     r15d, r15d
0x180001493  mov     [rsp+0D0h+arg_10], rdi
0x18000149b  lea     r12, _TraceLoggingMetadata
0x1800014a2  mov     rbx, rcx
0x1800014a5  cmp     eax, 4
0x1800014a8  jbe     loc_18000153C
0x1800014ae  mov     [rbp+57h+var_98], rcx
0x1800014b2  lea     rax, [rbp+57h+var_98]
0x1800014b6  mov     [rbp+57h+var_50], rax
0x1800014ba  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1800014be  movzx   eax, cs:word_18000F6A8
0x1800014c5  xor     r9d, r9d; RelatedActivityId
0x1800014c8  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800014cb  xor     r8d, r8d; ActivityId
0x1800014ce  mov     rax, cs:off_180012008
0x1800014d5  mov     [rbp+57h+var_70.Ptr], rax
0x1800014d9  mov     [rbp+57h+var_48], 8
0x1800014e1  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1800014e8  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x1800014ec  movzx   eax, word ptr [rax]
0x1800014ef  mov     [rbp+57h+var_70.Size], eax
0x1800014f2  lea     rax, word_18000F6B2
0x1800014f9  mov     [rbp+57h+var_60], rax
0x1800014fd  mov     rax, r14
0x180001500  sub     eax, r12d
0x180001503  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x18000150a  mov     [rbp+57h+var_58], 2Bh ; '+'
0x180001511  mov     [rbp+57h+var_54], 1
0x180001518  mov     [rbp+57h+var_A0], eax
0x18000151b  mov     eax, [rbp+57h+var_A0]
0x18000151e  mov     rcx, cs:RegHandle; RegHandle
0x180001525  lea     rax, [rbp+57h+var_70]
0x180001529  mov     [rsp+0D0h+UserData], rax; UserData
0x18000152e  mov     [rsp+0D0h+UserDataCount], 3; UserDataCount
0x180001536  call    cs:__imp_EventWriteTransfer
0x18000153c  lea     rcx, [rbx+50h]
0x180001540  mov     [rsp+0D0h+arg_8], rsi
0x180001548  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000154e  call    cs:__imp_GetCurrentThreadId
0x180001554  mov     [rbx+58h], eax
0x180001557  cmp     [rbx+6Ch], r15d
0x18000155b  jz      short loc_1800015BE
0x18000155d  mov     rcx, rbx
0x180001560  call    EaLibClearAndReleaseTimer
0x180001565  call    cs:__imp_GetCurrentThreadId
0x18000156b  mov     eax, eax
0x18000156d  cmp     [rbx+70h], rax
0x180001571  jnz     short loc_18000157A
0x180001573  mov     esi, 0C00000BBh
0x180001578  jmp     short loc_1800015C1
0x18000157a  lea     rcx, [rbx+50h]
0x18000157e  mov     [rbx+6Ch], r15d
0x180001582  mov     [rbx+58h], r15d
0x180001586  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000158c  mov     rax, [rbx+38h]
0x180001590  mov     rcx, [rax]
0x180001593  test    rcx, rcx
0x180001596  jz      short loc_1800015B0
0x180001598  mov     rcx, [rcx]
0x18000159b  test    rcx, rcx
0x18000159e  jz      short loc_1800015B0
0x1800015a0  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800015a6  mov     rax, [rbx+38h]
0x1800015aa  mov     rcx, [rax]
0x1800015ad  mov     [rcx], r15
0x1800015b0  xor     edx, edx
0x1800015b2  mov     rcx, rbx
0x1800015b5  call    EaiSetAggregateConditionsEnabledState
0x1800015ba  mov     esi, eax
0x1800015bc  jmp     short loc_1800015CF
0x1800015be  mov     esi, r15d
0x1800015c1  lea     rcx, [rbx+50h]
0x1800015c5  mov     [rbx+58h], r15d
0x1800015c9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800015cf  mov     eax, cs:dword_180012000
0x1800015d5  mov     rdi, [rsp+0D0h+arg_10]
0x1800015dd  cmp     eax, 4
0x1800015e0  jbe     loc_180001685
0x1800015e6  mov     qword ptr [rbp+57h+EventDescriptor.Id], rbx
0x1800015ea  lea     rax, [rbp+57h+EventDescriptor]
0x1800015ee  mov     [rbp+57h+var_50], rax
0x1800015f2  lea     rdx, [rbp+57h+var_80]; EventDescriptor
0x1800015f6  lea     rax, [rbp+57h+var_A0]
0x1800015fa  mov     [rbp+57h+var_48], 8
0x180001602  mov     [rbp+57h+var_40], rax
0x180001606  sub     r14d, r12d
0x180001609  movzx   eax, cs:word_18000F70B
0x180001610  xor     r9d, r9d; RelatedActivityId
0x180001613  mov     dword ptr [rbp+57h+var_80.Level], eax
0x180001616  xor     r8d, r8d; ActivityId
0x180001619  mov     rax, cs:off_180012008
0x180001620  mov     [rbp+57h+var_70.Ptr], rax
0x180001624  mov     [rbp+57h+var_A0], esi
0x180001627  mov     [rbp+57h+var_38], 4
0x18000162f  mov     dword ptr [rbp+57h+var_80.Id], 0B000000h
0x180001636  mov     [rbp+57h+var_80.Keyword], r15
0x18000163a  movzx   eax, word ptr [rax]
0x18000163d  mov     [rbp+57h+var_70.Size], eax
0x180001640  lea     rax, byte_18000F715
0x180001647  mov     [rbp+57h+var_60], rax
0x18000164b  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x180001652  mov     [rbp+57h+var_58], 34h ; '4'
0x180001659  mov     [rbp+57h+var_54], 1
0x180001660  mov     dword ptr [rbp+57h+var_98], r14d
0x180001664  mov     eax, dword ptr [rbp+57h+var_98]
0x180001667  mov     rcx, cs:RegHandle; RegHandle
0x18000166e  lea     rax, [rbp+57h+var_70]
0x180001672  mov     [rsp+0D0h+UserData], rax; UserData
0x180001677  mov     [rsp+0D0h+UserDataCount], 4; UserDataCount
0x18000167f  call    cs:__imp_EventWriteTransfer
0x180001685  mov     eax, esi
0x180001687  mov     rsi, [rsp+0D0h+arg_8]
0x18000168f  mov     rcx, [rbp+57h+var_30]
0x180001693  xor     rcx, rsp; StackCookie
0x180001696  call    __security_check_cookie
0x18000169b  add     rsp, 0B0h
0x1800016a2  pop     r15
0x1800016a4  pop     r14
0x1800016a6  pop     r12
0x1800016a8  pop     rbx
0x1800016a9  pop     rbp
0x1800016aa  retn
```
