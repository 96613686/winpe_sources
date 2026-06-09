# EaSignalAggregatedEvent

- ea: `0x1800054c0`
- end: `0x18000592e`
- name: `EaSignalAggregatedEvent`
- size: `1134`
- prototype: `__int64 __fastcall(__int64, _DWORD *, unsigned __int8, unsigned __int8, __int128 *, __int64, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180001730`
- `0x1800054c0`
- `0x180005cc0`
- `0x180006c14`
- `0x1800072e0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockShared` at `0x180005618`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000565e`
- `ntdll!RtlAcquireSRWLockShared` at `0x180005618`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000565e`
- `ntdll!RtlReleaseSRWLockShared` at `0x180005654`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000568a`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800056a9`
- `ntdll!RtlReleaseSRWLockShared` at `0x180005919`
- `ntdll!RtlReleaseSRWLockShared` at `0x180005654`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000568a`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800056a9`
- `ntdll!RtlReleaseSRWLockShared` at `0x180005919`
- `ntdll!RtlFreeHeap` at `0x180005907`
- `ntdll!RtlFreeHeap` at `0x180005907`
- `ntdll!RtlAllocateHeap` at `0x180005750`
- `ntdll!RtlAllocateHeap` at `0x180005750`
- `ntdll!RtlLookupEntryHashTable` at `0x180005634`
- `ntdll!RtlLookupEntryHashTable` at `0x180005634`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800055cc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005854`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800055cc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005854`

## pseudocode

```c
__int64 __fastcall EaSignalAggregatedEvent(
        __int64 a1,
        _DWORD *a2,
        unsigned __int8 a3,
        unsigned __int8 a4,
        __int128 *a5,
        __int64 a6,
        __int64 a7,
        int a8,
        __int64 a9)
{
  __int64 v9; // r12
  __int64 v11; // rcx
  const struct _TraceLoggingMetadata_t *v14; // rdx
  int v15; // ebx
  __int64 v16; // rax
  __int64 v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // rdx
  void *v20; // r14
  __int128 v21; // xmm0
  int v22; // esi
  __int128 v23; // xmm0
  unsigned __int8 v24; // r12
  PVOID Heap; // rax
  __int64 v27; // rax
  unsigned int Size; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int8 Size_4; // [rsp+4Ch] [rbp-BCh]
  __int64 v30; // [rsp+50h] [rbp-B8h]
  __int64 v31; // [rsp+58h] [rbp-B0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+70h] [rbp-98h]
  _QWORD v34[3]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v35; // [rsp+90h] [rbp-78h] BYREF
  _BYTE UserData[24]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v37; // [rsp+C0h] [rbp-48h]
  __int64 *v38; // [rsp+C8h] [rbp-40h]
  __int64 v39; // [rsp+D0h] [rbp-38h]
  unsigned int *p_Size; // [rsp+D8h] [rbp-30h]
  __int64 v41; // [rsp+E0h] [rbp-28h]

  v9 = 0;
  v11 = a7;
  v34[0] = a6;
  v31 = a9;
  Size_4 = a4;
  v14 = &TraceLoggingMetadata;
  v33 = a7;
  v30 = 0;
  *(_OWORD *)&v34[1] = 0;
  v35 = 0;
  if ( (unsigned int)dword_180012000 > 4 )
  {
    *(_DWORD *)&EventDescriptor.Level = 260;
    *(_QWORD *)UserData = off_180012008;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    *(_QWORD *)&UserData[8] = *(unsigned __int16 *)off_180012008 | 0x200000000LL;
    *(_QWORD *)&UserData[16] = qword_18000EE28;
    v37 = 0x100000015LL;
    Size = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, (PEVENT_DATA_DESCRIPTOR)UserData);
    v11 = v33;
  }
  if ( !*a2 && !a2[1] )
  {
    v15 = -1073741811;
    goto LABEL_24;
  }
  if ( a8 && !v11 )
  {
    v9 = v30;
    v15 = -1073741811;
    goto LABEL_24;
  }
  RtlAcquireSRWLockShared(AggregateEventListLock, v14);
  if ( qword_180012148 )
  {
    v16 = RtlLookupEntryHashTable(qword_180012148, a1, 0);
    v17 = v16;
    if ( v16 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v16 + 136));
      RtlReleaseSRWLockShared(AggregateEventListLock);
      RtlAcquireSRWLockShared(v17 + 80, v18);
      if ( a3 )
      {
        v19 = **(_QWORD **)(v17 + 56);
        if ( v19 )
        {
          if ( *a2 != *(_DWORD *)(v19 + 8) || a2[1] != *(_DWORD *)(v19 + 12) )
          {
            RtlReleaseSRWLockShared(v17 + 80);
            v15 = -1073741637;
            EaiReleaseAggregateEvent(v17);
LABEL_23:
            v9 = v17;
            goto LABEL_24;
          }
        }
      }
      v20 = 0;
      RtlReleaseSRWLockShared(v17 + 80);
      memset(UserData, 0, sizeof(UserData));
      HIDWORD(v38) = 0;
      if ( a5 )
      {
        v21 = *a5;
        *(_QWORD *)UserData = &v34[1];
        *(_OWORD *)&v34[1] = v21;
      }
      v22 = a5 != 0 ? 2 : 0;
      if ( v34[0] )
      {
        v23 = *(_OWORD *)v34[0];
        v22 |= 1u;
        *(_QWORD *)&UserData[8] = &v35;
        v35 = v23;
      }
      LODWORD(v38) = a8;
      v24 = Size_4;
      Size = 0;
      v37 = v33;
      v15 = EapSignalContentPrepareEventForPublishing(a3, Size_4, (int)UserData, (int)&Size, 0);
      if ( v15 != -1073741789 )
        goto LABEL_33;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Size);
      v20 = Heap;
      if ( !Heap )
      {
        v15 = -1073741801;
        EaiReleaseAggregateEvent(v17);
        goto LABEL_23;
      }
      v15 = EapSignalContentPrepareEventForPublishing(a3, v24, (int)UserData, (int)&Size, Heap);
      if ( v15 >= 0
        && (Size == 8 ? (v27 = 0) : (v27 = (__int64)v20 + 8),
            v15 = EaiProcessNotification(v17, (_DWORD)a2, a3, v24, v27, Size - 8, v22, v31),
            v15 >= 0) )
      {
        v15 = 0;
        EaiReleaseAggregateEvent(v17);
      }
      else
      {
LABEL_33:
        EaiReleaseAggregateEvent(v17);
        if ( !v20 )
          goto LABEL_23;
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
      goto LABEL_23;
    }
  }
  RtlReleaseSRWLockShared(AggregateEventListLock);
  v9 = v30;
  v15 = -1073741816;
LABEL_24:
  if ( (unsigned int)dword_180012000 > 4 )
  {
    v31 = v9;
    EventDescriptor.Keyword = 0;
    v38 = &v31;
    v39 = 8;
    p_Size = &Size;
    *(_DWORD *)&EventDescriptor.Level = 516;
    *(_QWORD *)UserData = off_180012008;
    Size = v15;
    v41 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_QWORD *)&UserData[8] = *(unsigned __int16 *)off_180012008 | 0x200000000LL;
    *(_QWORD *)&UserData[16] = byte_18000F3C1;
    v37 = 0x10000002BLL;
    LODWORD(v30) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, (PEVENT_DATA_DESCRIPTOR)UserData);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800054c0  mov     r11, rsp
0x1800054c3  push    rbp
0x1800054c4  push    rbx
0x1800054c5  push    r12
0x1800054c7  push    r14
0x1800054c9  lea     rbp, [r11-38h]
0x1800054cd  sub     rsp, 118h
0x1800054d4  mov     rax, cs:__security_cookie
0x1800054db  xor     rax, rsp
0x1800054de  mov     [rbp+30h+var_50], rax
0x1800054e2  mov     rax, [rbp+30h+arg_28]
0x1800054e6  lea     r14, _TraceLoggingMetadataEnd
0x1800054ed  mov     [r11-28h], rsi
0x1800054f1  xor     r12d, r12d
0x1800054f4  mov     rsi, [rbp+30h+arg_20]
0x1800054f8  mov     rbx, rcx
0x1800054fb  mov     rcx, [rbp+30h+arg_30]
0x1800054ff  xorps   xmm0, xmm0
0x180005502  mov     qword ptr [rsp+130h+var_C0], rax
0x180005507  xorps   xmm1, xmm1
0x18000550a  mov     rax, [rbp+30h+arg_40]
0x180005511  mov     [r11-38h], r13
0x180005515  movzx   r13d, r8b
0x180005519  mov     qword ptr [rsp+130h+var_E0], rax
0x18000551e  mov     eax, cs:dword_180012000
0x180005524  mov     [r11-40h], r15
0x180005528  mov     r15, rdx
0x18000552b  mov     byte ptr [rsp+130h+Size+4], r9b
0x180005530  lea     rdx, _TraceLoggingMetadata
0x180005537  mov     [rsp+130h+var_C8], rcx
0x18000553c  mov     [rsp+130h+var_E8], r12
0x180005541  movups  xmmword ptr [rsp+130h+var_C0+8], xmm0
0x180005546  movups  [rbp+30h+var_A8], xmm1
0x18000554a  cmp     eax, 4
0x18000554d  jbe     loc_1800055D7
0x180005553  movzx   eax, cs:word_18000EE1E
0x18000555a  xor     r9d, r9d; RelatedActivityId
0x18000555d  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x180005561  xor     r8d, r8d; ActivityId
0x180005564  mov     rax, cs:off_180012008
0x18000556b  mov     qword ptr [rbp+30h+var_90], rax
0x18000556f  mov     dword ptr [rsp+130h+EventDescriptor.Id], 0B000000h
0x180005577  mov     [rsp+130h+EventDescriptor.Keyword], r12
0x18000557c  movzx   eax, word ptr [rax]
0x18000557f  mov     dword ptr [rbp+30h+var_90+8], eax
0x180005582  lea     rax, qword_18000EE28
0x180005589  mov     qword ptr [rbp+30h+var_90+10h], rax
0x18000558d  mov     rax, r14
0x180005590  sub     eax, edx
0x180005592  mov     dword ptr [rbp+30h+var_90+0Ch], 2
0x180005599  mov     dword ptr [rbp+30h+var_78], 15h
0x1800055a0  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x1800055a5  mov     dword ptr [rbp+30h+var_78+4], 1
0x1800055ac  mov     dword ptr [rsp+130h+Size], eax
0x1800055b0  mov     eax, dword ptr [rsp+130h+Size]
0x1800055b4  mov     rcx, cs:RegHandle; RegHandle
0x1800055bb  lea     rax, [rbp+30h+var_90]
0x1800055bf  mov     [rsp+130h+UserData], rax; UserData
0x1800055c4  mov     [rsp+130h+UserDataCount], 2; UserDataCount
0x1800055cc  call    cs:__imp_EventWriteTransfer
0x1800055d2  mov     rcx, [rsp+130h+var_C8]
0x1800055d7  cmp     [r15], r12d
0x1800055da  jnz     short loc_1800055EC
0x1800055dc  cmp     [r15+4], r12d
0x1800055e0  jnz     short loc_1800055EC
0x1800055e2  mov     ebx, 0C000000Dh
0x1800055e7  jmp     loc_180005781
0x1800055ec  mov     r12d, [rbp+30h+arg_38]
0x1800055f0  test    r12d, r12d
0x1800055f3  jz      short loc_180005609
0x1800055f5  test    rcx, rcx
0x1800055f8  jnz     short loc_180005609
0x1800055fa  mov     r12, [rsp+130h+var_E8]
0x1800055ff  mov     ebx, 0C000000Dh
0x180005604  jmp     loc_180005781
0x180005609  lea     rcx, AggregateEventListLock
0x180005610  mov     [rsp+130h+var_28], rdi
0x180005618  call    cs:__imp_RtlAcquireSRWLockShared
0x18000561e  mov     rcx, cs:qword_180012148
0x180005625  test    rcx, rcx
0x180005628  jz      loc_180005912
0x18000562e  xor     r8d, r8d
0x180005631  mov     rdx, rbx
0x180005634  call    cs:__imp_RtlLookupEntryHashTable
0x18000563a  mov     rdi, rax
0x18000563d  test    rax, rax
0x180005640  jz      loc_180005912
0x180005646  lock inc dword ptr [rax+88h]
0x18000564d  lea     rcx, AggregateEventListLock
0x180005654  call    cs:__imp_RtlReleaseSRWLockShared
0x18000565a  lea     rcx, [rdi+50h]
0x18000565e  call    cs:__imp_RtlAcquireSRWLockShared
0x180005664  test    r13b, r13b
0x180005667  jz      short loc_1800056A2
0x180005669  mov     rax, [rdi+38h]
0x18000566d  mov     rdx, [rax]
0x180005670  test    rdx, rdx
0x180005673  jz      short loc_1800056A2
0x180005675  mov     eax, [rdx+8]
0x180005678  cmp     [r15], eax
0x18000567b  jnz     short loc_180005686
0x18000567d  mov     eax, [rdx+0Ch]
0x180005680  cmp     [r15+4], eax
0x180005684  jz      short loc_1800056A2
0x180005686  lea     rcx, [rdi+50h]
0x18000568a  call    cs:__imp_RtlReleaseSRWLockShared
0x180005690  mov     rcx, rdi
0x180005693  mov     ebx, 0C00000BBh
0x180005698  call    EaiReleaseAggregateEvent
0x18000569d  jmp     loc_180005776
0x1800056a2  lea     rcx, [rdi+50h]
0x1800056a6  xor     r14d, r14d
0x1800056a9  call    cs:__imp_RtlReleaseSRWLockShared
0x1800056af  xor     ecx, ecx
0x1800056b1  xorps   xmm0, xmm0
0x1800056b4  mov     qword ptr [rbp+30h+var_90], rcx
0x1800056b8  mov     dword ptr [rbp+30h+var_70+4], ecx
0x1800056bb  movdqu  xmmword ptr [rbp+30h+var_90+8], xmm0
0x1800056c0  test    rsi, rsi
0x1800056c3  jz      short loc_1800056D6
0x1800056c5  movups  xmm0, xmmword ptr [rsi]
0x1800056c8  lea     rax, [rsp+130h+var_C0+8]
0x1800056cd  mov     qword ptr [rbp+30h+var_90], rax
0x1800056d1  movups  xmmword ptr [rsp+130h+var_C0+8], xmm0
0x1800056d6  mov     rax, qword ptr [rsp+130h+var_C0]
0x1800056db  neg     rsi
0x1800056de  sbb     esi, esi
0x1800056e0  and     esi, 2
0x1800056e3  test    rax, rax
0x1800056e6  jz      short loc_1800056FA
0x1800056e8  movups  xmm0, xmmword ptr [rax]
0x1800056eb  lea     rax, [rbp+30h+var_A8]
0x1800056ef  or      esi, 1
0x1800056f2  mov     qword ptr [rbp+30h+var_90+8], rax
0x1800056f6  movups  [rbp+30h+var_A8], xmm0
0x1800056fa  mov     rax, [rsp+130h+var_C8]
0x1800056ff  lea     r9, [rsp+130h+Size]; int
0x180005704  mov     dword ptr [rbp+30h+var_70], r12d
0x180005708  lea     r8, [rbp+30h+var_90]; int
0x18000570c  movzx   r12d, byte ptr [rsp+130h+Size+4]
0x180005712  mov     dword ptr [rsp+130h+Size], ecx
0x180005716  movzx   edx, r12b; int
0x18000571a  mov     qword ptr [rsp+130h+UserDataCount], rcx; void *
0x18000571f  movzx   ecx, r13b; int
0x180005723  mov     [rbp+30h+var_78], rax
0x180005727  call    EapSignalContentPrepareEventForPublishing
0x18000572c  mov     ebx, eax
0x18000572e  cmp     eax, 0C0000023h
0x180005733  jnz     loc_1800058E4
0x180005739  mov     rcx, gs:60h
0x180005742  mov     edx, 8; Flags
0x180005747  mov     r8d, dword ptr [rsp+130h+Size]; Size
0x18000574c  mov     rcx, [rcx+30h]; HeapHandle
0x180005750  call    cs:__imp_RtlAllocateHeap
0x180005756  mov     r14, rax
0x180005759  test    rax, rax
0x18000575c  jnz     loc_180005876
0x180005762  mov     rcx, rdi
0x180005765  mov     ebx, 0C0000017h
0x18000576a  call    EaiReleaseAggregateEvent
0x18000576f  lea     r14, _TraceLoggingMetadataEnd
0x180005776  mov     r12, rdi
0x180005779  mov     rdi, [rsp+130h+var_28]
0x180005781  mov     eax, cs:dword_180012000
0x180005787  mov     r15, [rsp+130h+var_38]
0x18000578f  mov     r13, [rsp+130h+var_30]
0x180005797  mov     rsi, [rsp+110h]
0x18000579f  cmp     eax, 4
0x1800057a2  jbe     loc_18000585A
0x1800057a8  xor     ecx, ecx
0x1800057aa  mov     qword ptr [rsp+130h+var_E0], r12
0x1800057af  mov     [rsp+130h+EventDescriptor.Keyword], rcx
0x1800057b4  lea     rax, [rsp+130h+var_E0]
0x1800057b9  mov     [rbp+30h+var_70], rax
0x1800057bd  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x1800057c2  lea     rax, [rsp+130h+Size]
0x1800057c7  mov     [rbp+30h+var_68], 8
0x1800057cf  mov     [rbp+30h+var_60], rax
0x1800057d3  xor     r9d, r9d; RelatedActivityId
0x1800057d6  movzx   eax, cs:word_18000F3B7
0x1800057dd  xor     r8d, r8d; ActivityId
0x1800057e0  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x1800057e4  mov     rax, cs:off_180012008
0x1800057eb  mov     qword ptr [rbp+30h+var_90], rax
0x1800057ef  mov     dword ptr [rsp+130h+Size], ebx
0x1800057f3  mov     [rbp+30h+var_58], 4
0x1800057fb  mov     dword ptr [rsp+130h+EventDescriptor.Id], 0B000000h
0x180005803  movzx   eax, word ptr [rax]
0x180005806  mov     dword ptr [rbp+30h+var_90+8], eax
0x180005809  lea     rax, byte_18000F3C1
0x180005810  mov     qword ptr [rbp+30h+var_90+10h], rax
0x180005814  lea     rax, _TraceLoggingMetadata
0x18000581b  sub     r14d, eax
0x18000581e  mov     dword ptr [rbp+30h+var_90+0Ch], 2
0x180005825  mov     dword ptr [rbp+30h+var_78], 2Bh ; '+'
0x18000582c  mov     dword ptr [rbp+30h+var_78+4], 1
0x180005833  mov     dword ptr [rsp+130h+var_E8], r14d
0x180005838  mov     eax, dword ptr [rsp+130h+var_E8]
0x18000583c  mov     rcx, cs:RegHandle; RegHandle
0x180005843  lea     rax, [rbp+30h+var_90]
0x180005847  mov     [rsp+130h+UserData], rax; UserData
0x18000584c  mov     [rsp+130h+UserDataCount], 4; UserDataCount
0x180005854  call    cs:__imp_EventWriteTransfer
0x18000585a  mov     eax, ebx
0x18000585c  mov     rcx, [rbp+30h+var_50]
0x180005860  xor     rcx, rsp; StackCookie
0x180005863  call    __security_check_cookie
0x180005868  add     rsp, 118h
0x18000586f  pop     r14
0x180005871  pop     r12
0x180005873  pop     rbx
0x180005874  pop     rbp
0x180005875  retn
0x180005876  lea     r9, [rsp+130h+Size]; int
0x18000587b  mov     qword ptr [rsp+130h+UserDataCount], r14; void *
0x180005880  lea     r8, [rbp+30h+var_90]; int
0x180005884  movzx   edx, r12b; int
0x180005888  movzx   ecx, r13b; int
0x18000588c  call    EapSignalContentPrepareEventForPublishing
0x180005891  mov     ebx, eax
0x180005893  test    eax, eax
0x180005895  js      short loc_1800058E4
0x180005897  mov     ecx, dword ptr [rsp+130h+Size]
0x18000589b  add     ecx, 0FFFFFFF8h
0x18000589e  jz      short loc_1800058A6
0x1800058a0  lea     rax, [r14+8]
0x1800058a4  jmp     short loc_1800058A8
0x1800058a6  xor     eax, eax
0x1800058a8  mov     rdx, qword ptr [rsp+130h+var_E0]
0x1800058ad  movzx   r9d, r12b
0x1800058b1  mov     qword ptr [rsp+130h+var_F8], rdx
0x1800058b6  movzx   r8d, r13b
0x1800058ba  mov     dword ptr [rsp+130h+var_100], esi
0x1800058be  mov     rdx, r15
0x1800058c1  mov     dword ptr [rsp+130h+UserData], ecx
0x1800058c5  mov     rcx, rdi
0x1800058c8  mov     qword ptr [rsp+130h+UserDataCount], rax
0x1800058cd  call    EaiProcessNotification
0x1800058d2  mov     ebx, eax
0x1800058d4  test    eax, eax
0x1800058d6  js      short loc_1800058E4
0x1800058d8  xor     ebx, ebx
0x1800058da  mov     rcx, rdi
0x1800058dd  call    EaiReleaseAggregateEvent
0x1800058e2  jmp     short loc_1800058F5
0x1800058e4  mov     rcx, rdi
0x1800058e7  call    EaiReleaseAggregateEvent
0x1800058ec  test    r14, r14
0x1800058ef  jz      loc_18000576F
0x1800058f5  mov     rcx, gs:60h
0x1800058fe  mov     r8, r14; P
0x180005901  xor     edx, edx; Flags
0x180005903  mov     rcx, [rcx+30h]; HeapHandle
0x180005907  call    cs:__imp_RtlFreeHeap
0x18000590d  jmp     loc_18000576F
0x180005912  lea     rcx, AggregateEventListLock
0x180005919  call    cs:__imp_RtlReleaseSRWLockShared
0x18000591f  mov     r12, [rsp+130h+var_E8]
0x180005924  mov     ebx, 0C0000008h
0x180005929  jmp     loc_180005779
```
