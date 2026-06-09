# EaiEnableAggregateEvent

- ea: `0x180005940`
- end: `0x180005cb2`
- name: `EaiEnableAggregateEvent`
- size: `882`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002ae0`
- `0x1800044c0`
- `0x180007f00`

## callees

- `0x180005940`
- `0x1800062e0`
- `0x1800072e0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005b47`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005b82`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005b47`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005b82`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180005988`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180005988`
- `ntdll!RtlFreeHeap` at `0x180005b9f`
- `ntdll!RtlFreeHeap` at `0x180005b9f`
- `ntdll!RtlAllocateHeap` at `0x180005a6c`
- `ntdll!RtlAllocateHeap` at `0x180005a6c`
- `ntdll!NtQueryWnfStateData` at `0x180005add`
- `ntdll!NtQueryWnfStateData` at `0x180005add`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180005b19`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180005b19`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180005b61`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180005b61`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005a44`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005c8a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005a44`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005c8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000598e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000598e`

## pseudocode

```c
__int64 __fastcall EaiEnableAggregateEvent(__int64 a1)
{
  PVOID Heap; // rsi
  int v3; // edi
  __int64 v4; // rdx
  __int64 *v5; // rax
  __int64 v6; // rax
  _QWORD *v7; // rax
  unsigned int v9; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v10; // [rsp+44h] [rbp-BCh] BYREF
  int v11; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v12; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v13; // [rsp+50h] [rbp-B0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v15; // [rsp+68h] [rbp-98h] BYREF
  EVENT_DESCRIPTOR v16; // [rsp+70h] [rbp-90h] BYREF
  __int64 v17; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-70h] BYREF
  int *v19; // [rsp+A0h] [rbp-60h]
  int v20; // [rsp+A8h] [rbp-58h]
  int v21; // [rsp+ACh] [rbp-54h]
  __int64 *v22; // [rsp+B0h] [rbp-50h]
  __int64 v23; // [rsp+B8h] [rbp-48h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+C0h] [rbp-40h]
  __int64 v25; // [rsp+C8h] [rbp-38h]
  unsigned int *v26; // [rsp+D0h] [rbp-30h]
  __int64 v27; // [rsp+D8h] [rbp-28h]
  int *v28; // [rsp+E0h] [rbp-20h]
  __int64 v29; // [rsp+E8h] [rbp-18h]

  v11 = 4096;
  v9 = 0;
  v17 = 0;
  Heap = 0;
  v3 = 0;
  RtlAcquireSRWLockExclusive(a1 + 80);
  *(_DWORD *)(a1 + 88) = GetCurrentThreadId();
  if ( (unsigned int)dword_180012000 > 4 )
  {
    v13 = a1;
    v22 = &v13;
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_180012008;
    v23 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v19 = (int *)&unk_18000F3F8;
    UserData.Reserved = 2;
    v20 = 42;
    v21 = 1;
    v10 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  if ( *(_DWORD *)(a1 + 108) )
  {
LABEL_18:
    *(_DWORD *)(a1 + 88) = 0;
    RtlReleaseSRWLockExclusive(a1 + 80);
    if ( !Heap )
      goto LABEL_20;
    goto LABEL_19;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x1000u);
  if ( !Heap )
  {
    v3 = -1073741801;
    goto LABEL_18;
  }
  v5 = *(__int64 **)(a1 + 56);
  *(_QWORD *)(a1 + 112) = 0;
  if ( !*v5
    || (LODWORD(v17) = *(_DWORD *)(*v5 + 8),
        v6 = *v5,
        v4 = *(unsigned int *)(v6 + 12),
        HIDWORD(v17) = *(_DWORD *)(v6 + 12),
        !(_DWORD)v17)
    && !(_DWORD)v4
    || ((*(_BYTE *)(a1 + 140) & 2) == 0 || (v11 = 4096, v3 = NtQueryWnfStateData(&v17, 0, 0, &v9, Heap, &v11), v3 >= 0))
    && (v3 = RtlSubscribeWnfStateChangeNotification(
               **(_QWORD **)(a1 + 56),
               v17,
               v9,
               AggregateEventWnfCallback,
               a1,
               0,
               *(_DWORD *)(a1 + 144),
               0),
        v3 >= 0) )
  {
    if ( !*(_QWORD *)(*(_QWORD *)(a1 + 56) + 8LL)
      || (LOBYTE(v4) = 1, v3 = EaiSetAggregateConditionsEnabledState(a1, v4), v3 >= 0) )
    {
      *(_DWORD *)(a1 + 108) = 1;
      goto LABEL_18;
    }
  }
  *(_DWORD *)(a1 + 88) = 0;
  RtlReleaseSRWLockExclusive(a1 + 80);
  v7 = *(_QWORD **)(a1 + 56);
  if ( *v7 && *(_QWORD *)*v7 )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    ***(_QWORD ***)(a1 + 56) = 0;
  }
LABEL_19:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
LABEL_20:
  if ( (unsigned int)dword_180012000 > 4 )
  {
    v15 = a1;
    v22 = &v15;
    *(_QWORD *)&EventDescriptor.Id = v17;
    v23 = 8;
    p_EventDescriptor = &EventDescriptor;
    v25 = 8;
    v26 = &v10;
    v12 = v9;
    v28 = (int *)&v12;
    *(_DWORD *)&v16.Level = 516;
    UserData.Ptr = (ULONGLONG)off_180012008;
    v10 = v3;
    v27 = 4;
    v29 = 4;
    *(_DWORD *)&v16.Id = 184549376;
    v16.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v19 = &dword_18000F454;
    UserData.Reserved = 2;
    v20 = 73;
    v21 = 1;
    LODWORD(v13) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &v16, 0, 0, 6u, &UserData);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180005940  push    rbp
0x180005942  push    rbx
0x180005943  push    rsi
0x180005944  push    rdi
0x180005945  push    r12
0x180005947  push    r13
0x180005949  push    r14
0x18000594b  push    r15
0x18000594d  lea     rbp, [rsp-8]
0x180005952  sub     rsp, 108h
0x180005959  mov     rax, cs:__security_cookie
0x180005960  xor     rax, rsp
0x180005963  mov     [rbp+40h+var_50], rax
0x180005967  xor     r12d, r12d
0x18000596a  mov     [rsp+140h+var_F8], 1000h
0x180005972  mov     rbx, rcx
0x180005975  mov     [rsp+140h+var_100], r12d
0x18000597a  add     rcx, 50h ; 'P'
0x18000597e  mov     [rbp+40h+var_C0], r12
0x180005982  mov     esi, r12d
0x180005985  mov     edi, r12d
0x180005988  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000598e  call    cs:__imp_GetCurrentThreadId
0x180005994  mov     [rbx+58h], eax
0x180005997  lea     r15, _TraceLoggingMetadataEnd
0x18000599e  mov     eax, cs:dword_180012000
0x1800059a4  lea     r13, _TraceLoggingMetadata
0x1800059ab  cmp     eax, 4
0x1800059ae  jbe     loc_180005A4A
0x1800059b4  lea     rax, [rsp+140h+var_F0]
0x1800059b9  mov     [rsp+140h+var_F0], rbx
0x1800059be  mov     [rbp+40h+var_90], rax
0x1800059c2  lea     rdx, [rsp+140h+EventDescriptor]; EventDescriptor
0x1800059c7  movzx   eax, cs:word_18000F3EE
0x1800059ce  xor     r9d, r9d; RelatedActivityId
0x1800059d1  mov     dword ptr [rsp+140h+EventDescriptor.Level], eax
0x1800059d5  xor     r8d, r8d; ActivityId
0x1800059d8  mov     rax, cs:off_180012008
0x1800059df  mov     [rbp+40h+var_B0.Ptr], rax
0x1800059e3  mov     [rbp+40h+var_88], 8
0x1800059eb  mov     dword ptr [rsp+140h+EventDescriptor.Id], 0B000000h
0x1800059f3  mov     [rsp+140h+EventDescriptor.Keyword], r12
0x1800059f8  movzx   eax, word ptr [rax]
0x1800059fb  mov     [rbp+40h+var_B0.Size], eax
0x1800059fe  lea     rax, unk_18000F3F8
0x180005a05  mov     [rbp+40h+var_A0], rax
0x180005a09  mov     rax, r15
0x180005a0c  sub     eax, r13d
0x180005a0f  mov     dword ptr [rbp+40h+var_B0.0Ch], 2
0x180005a16  mov     [rbp+40h+var_98], 2Ah ; '*'
0x180005a1d  mov     [rbp+40h+var_94], 1
0x180005a24  mov     [rsp+140h+var_FC], eax
0x180005a28  mov     eax, [rsp+140h+var_FC]
0x180005a2c  mov     rcx, cs:RegHandle; RegHandle
0x180005a33  lea     rax, [rbp+40h+var_B0]
0x180005a37  mov     [rsp+140h+UserData], rax; UserData
0x180005a3c  mov     [rsp+140h+UserDataCount], 3; UserDataCount
0x180005a44  call    cs:__imp_EventWriteTransfer
0x180005a4a  cmp     [rbx+6Ch], r12d
0x180005a4e  jnz     loc_180005B7A
0x180005a54  mov     rcx, gs:60h
0x180005a5d  mov     edx, 8; Flags
0x180005a62  mov     r8d, 1000h; Size
0x180005a68  mov     rcx, [rcx+30h]; HeapHandle
0x180005a6c  call    cs:__imp_RtlAllocateHeap
0x180005a72  mov     rsi, rax
0x180005a75  test    rax, rax
0x180005a78  jnz     short loc_180005A84
0x180005a7a  mov     edi, 0C0000017h
0x180005a7f  jmp     loc_180005B7A
0x180005a84  mov     rax, [rbx+38h]
0x180005a88  mov     [rbx+70h], r12
0x180005a8c  mov     rcx, [rax]
0x180005a8f  test    rcx, rcx
0x180005a92  jz      loc_180005B25
0x180005a98  mov     ecx, [rcx+8]
0x180005a9b  mov     dword ptr [rbp+40h+var_C0], ecx
0x180005a9e  mov     rax, [rax]
0x180005aa1  mov     edx, [rax+0Ch]
0x180005aa4  mov     dword ptr [rbp+40h+var_C0+4], edx
0x180005aa7  test    ecx, ecx
0x180005aa9  jnz     short loc_180005AAF
0x180005aab  test    edx, edx
0x180005aad  jz      short loc_180005B25
0x180005aaf  test    byte ptr [rbx+8Ch], 2
0x180005ab6  jz      short loc_180005AE9
0x180005ab8  lea     rax, [rsp+140h+var_F8]
0x180005abd  mov     [rsp+140h+var_F8], 1000h
0x180005ac5  mov     [rsp+140h+UserData], rax
0x180005aca  lea     r9, [rsp+140h+var_100]
0x180005acf  xor     r8d, r8d
0x180005ad2  mov     qword ptr [rsp+140h+UserDataCount], rsi
0x180005ad7  xor     edx, edx
0x180005ad9  lea     rcx, [rbp+40h+var_C0]
0x180005add  call    cs:__imp_NtQueryWnfStateData
0x180005ae3  mov     edi, eax
0x180005ae5  test    eax, eax
0x180005ae7  js      short loc_180005B3F
0x180005ae9  mov     rcx, [rbx+38h]
0x180005aed  lea     r9, AggregateEventWnfCallback
0x180005af4  mov     eax, [rbx+90h]
0x180005afa  mov     r8d, [rsp+140h+var_100]
0x180005aff  mov     rdx, [rbp+40h+var_C0]
0x180005b03  mov     rcx, [rcx]
0x180005b06  mov     [rsp+140h+var_108], r12d
0x180005b0b  mov     [rsp+140h+var_110], eax
0x180005b0f  mov     [rsp+140h+UserData], r12
0x180005b14  mov     qword ptr [rsp+140h+UserDataCount], rbx
0x180005b19  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180005b1f  mov     edi, eax
0x180005b21  test    eax, eax
0x180005b23  js      short loc_180005B3F
0x180005b25  mov     rax, [rbx+38h]
0x180005b29  cmp     [rax+8], r12
0x180005b2d  jz      short loc_180005B73
0x180005b2f  mov     dl, 1
0x180005b31  mov     rcx, rbx
0x180005b34  call    EaiSetAggregateConditionsEnabledState
0x180005b39  mov     edi, eax
0x180005b3b  test    eax, eax
0x180005b3d  jns     short loc_180005B73
0x180005b3f  lea     rcx, [rbx+50h]
0x180005b43  mov     [rbx+58h], r12d
0x180005b47  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180005b4d  mov     rax, [rbx+38h]
0x180005b51  mov     rcx, [rax]
0x180005b54  test    rcx, rcx
0x180005b57  jz      short loc_180005B8D
0x180005b59  mov     rcx, [rcx]
0x180005b5c  test    rcx, rcx
0x180005b5f  jz      short loc_180005B8D
0x180005b61  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180005b67  mov     rax, [rbx+38h]
0x180005b6b  mov     rcx, [rax]
0x180005b6e  mov     [rcx], r12
0x180005b71  jmp     short loc_180005B8D
0x180005b73  mov     dword ptr [rbx+6Ch], 1
0x180005b7a  lea     rcx, [rbx+50h]
0x180005b7e  mov     [rbx+58h], r12d
0x180005b82  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180005b88  test    rsi, rsi
0x180005b8b  jz      short loc_180005BA5
0x180005b8d  mov     rcx, gs:60h
0x180005b96  mov     r8, rsi; P
0x180005b99  xor     edx, edx; Flags
0x180005b9b  mov     rcx, [rcx+30h]; HeapHandle
0x180005b9f  call    cs:__imp_RtlFreeHeap
0x180005ba5  mov     eax, cs:dword_180012000
0x180005bab  cmp     eax, 4
0x180005bae  jbe     loc_180005C90
0x180005bb4  mov     [rsp+140h+var_D8], rbx
0x180005bb9  lea     rax, [rsp+140h+var_D8]
0x180005bbe  mov     [rbp+40h+var_90], rax
0x180005bc2  lea     rdx, [rsp+140h+var_D0]; EventDescriptor
0x180005bc7  mov     rax, [rbp+40h+var_C0]
0x180005bcb  sub     r15d, r13d
0x180005bce  mov     qword ptr [rsp+140h+EventDescriptor.Id], rax
0x180005bd3  xor     r9d, r9d; RelatedActivityId
0x180005bd6  mov     [rbp+40h+var_88], 8
0x180005bde  lea     rax, [rsp+140h+EventDescriptor]
0x180005be3  mov     [rbp+40h+var_80], rax
0x180005be7  xor     r8d, r8d; ActivityId
0x180005bea  lea     rax, [rsp+140h+var_FC]
0x180005bef  mov     [rbp+40h+var_78], 8
0x180005bf7  mov     [rbp+40h+var_70], rax
0x180005bfb  mov     eax, [rsp+140h+var_100]
0x180005bff  mov     [rsp+140h+var_F4], eax
0x180005c03  lea     rax, [rsp+140h+var_F4]
0x180005c08  mov     [rbp+40h+var_60], rax
0x180005c0c  movzx   eax, cs:word_18000F44A
0x180005c13  mov     dword ptr [rsp+140h+var_D0.Level], eax
0x180005c17  mov     rax, cs:off_180012008
0x180005c1e  mov     [rbp+40h+var_B0.Ptr], rax
0x180005c22  mov     [rsp+140h+var_FC], edi
0x180005c26  mov     [rbp+40h+var_68], 4
0x180005c2e  mov     [rbp+40h+var_58], 4
0x180005c36  mov     dword ptr [rsp+140h+var_D0.Id], 0B000000h
0x180005c3e  mov     [rsp+140h+var_D0.Keyword], r12
0x180005c43  movzx   eax, word ptr [rax]
0x180005c46  mov     [rbp+40h+var_B0.Size], eax
0x180005c49  lea     rax, dword_18000F454
0x180005c50  mov     [rbp+40h+var_A0], rax
0x180005c54  mov     dword ptr [rbp+40h+var_B0.0Ch], 2
0x180005c5b  mov     [rbp+40h+var_98], 49h ; 'I'
0x180005c62  mov     [rbp+40h+var_94], 1
0x180005c69  mov     dword ptr [rsp+140h+var_F0], r15d
0x180005c6e  mov     eax, dword ptr [rsp+140h+var_F0]
0x180005c72  mov     rcx, cs:RegHandle; RegHandle
0x180005c79  lea     rax, [rbp+40h+var_B0]
0x180005c7d  mov     [rsp+140h+UserData], rax; UserData
0x180005c82  mov     [rsp+140h+UserDataCount], 6; UserDataCount
0x180005c8a  call    cs:__imp_EventWriteTransfer
0x180005c90  mov     eax, edi
0x180005c92  mov     rcx, [rbp+40h+var_50]
0x180005c96  xor     rcx, rsp; StackCookie
0x180005c99  call    __security_check_cookie
0x180005c9e  add     rsp, 108h
0x180005ca5  pop     r15
0x180005ca7  pop     r14
0x180005ca9  pop     r13
0x180005cab  pop     r12
0x180005cad  pop     rdi
0x180005cae  pop     rsi
0x180005caf  pop     rbx
0x180005cb0  pop     rbp
0x180005cb1  retn
```
