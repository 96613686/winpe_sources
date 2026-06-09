# EaiSignalAggregateCallback

- ea: `0x1800064b0`
- end: `0x1800066c5`
- name: `EaiSignalAggregateCallback`
- size: `533`
- prototype: `ULONG __fastcall(__int64, __int64 *, void (__fastcall *)(__int64, __int64, _QWORD, __int64, int), __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800069d0`

## callees

- `0x1800064b0`
- `0x1800072e0`
- `0x18000c010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800065b6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800065b6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800065dc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800065dc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000658d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006698`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000658d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006698`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065e2`

## pseudocode

```c
ULONG __fastcall EaiSignalAggregateCallback(
        __int64 a1,
        __int64 *a2,
        void (__fastcall *a3)(__int64, __int64, _QWORD, __int64, int),
        __int64 a4,
        int a5)
{
  __int64 v9; // rbx
  bool v10; // zf
  ULONG result; // eax
  __int64 v12; // [rsp+38h] [rbp-39h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-21h] BYREF
  __int16 *v15; // [rsp+60h] [rbp-11h]
  int v16; // [rsp+68h] [rbp-9h]
  int v17; // [rsp+6Ch] [rbp-5h]
  __int64 *v18; // [rsp+70h] [rbp-1h]
  __int64 v19; // [rsp+78h] [rbp+7h]

  if ( (unsigned int)dword_180012000 > 4 )
  {
    v12 = a1;
    v18 = &v12;
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_180012008;
    v19 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v15 = word_18000F23A;
    UserData.Reserved = 2;
    v16 = 35;
    v17 = 1;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  if ( a3 )
  {
    v9 = *a2;
    *(_DWORD *)(a1 + 108) = 2;
    *(_QWORD *)(a1 + 112) = GetCurrentThreadId();
    *(_DWORD *)(a1 + 88) = 0;
    RtlReleaseSRWLockExclusive(a1 + 80);
    a3(a1, v9, *(_QWORD *)(a1 + 72), a4, a5);
    RtlAcquireSRWLockExclusive(a1 + 80);
    *(_DWORD *)(a1 + 88) = GetCurrentThreadId();
    v10 = *(_DWORD *)(a1 + 108) == 2;
    *(_QWORD *)(a1 + 112) = 0;
    if ( v10 )
      *(_DWORD *)(a1 + 108) = 1;
  }
  result = dword_180012000;
  if ( (unsigned int)dword_180012000 > 4 )
  {
    v12 = a1;
    v18 = &v12;
    *(_DWORD *)&EventDescriptor.Level = 516;
    UserData.Ptr = (ULONGLONG)off_180012008;
    v19 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v15 = (__int16 *)&unk_18000F0D8;
    UserData.Reserved = 2;
    v16 = 36;
    v17 = 1;
    return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x1800064b0  mov     [rsp-8+arg_8], rbx
0x1800064b5  push    rbp
0x1800064b6  push    rsi
0x1800064b7  push    rdi
0x1800064b8  push    r12
0x1800064ba  push    r13
0x1800064bc  push    r14
0x1800064be  push    r15
0x1800064c0  lea     rbp, [rsp-1Fh]
0x1800064c5  sub     rsp, 90h
0x1800064cc  mov     rax, cs:__security_cookie
0x1800064d3  xor     rax, rsp
0x1800064d6  mov     [rbp+4Fh+var_40], rax
0x1800064da  mov     eax, cs:dword_180012000
0x1800064e0  lea     r14, _TraceLoggingMetadataEnd
0x1800064e7  xor     r13d, r13d
0x1800064ea  lea     rdi, _TraceLoggingMetadata
0x1800064f1  mov     r12, r9
0x1800064f4  mov     r15, r8
0x1800064f7  mov     rbx, rdx
0x1800064fa  mov     rsi, rcx
0x1800064fd  cmp     eax, 4
0x180006500  jbe     loc_180006593
0x180006506  mov     [rbp+4Fh+var_88], rcx
0x18000650a  lea     rax, [rbp+4Fh+var_88]
0x18000650e  mov     [rbp+4Fh+var_50], rax
0x180006512  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x180006516  movzx   eax, cs:word_18000F230
0x18000651d  xor     r9d, r9d; RelatedActivityId
0x180006520  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x180006523  xor     r8d, r8d; ActivityId
0x180006526  mov     rax, cs:off_180012008
0x18000652d  mov     [rbp+4Fh+var_70.Ptr], rax
0x180006531  mov     [rbp+4Fh+var_48], 8
0x180006539  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], 0B000000h
0x180006540  mov     [rbp+4Fh+EventDescriptor.Keyword], r13
0x180006544  movzx   eax, word ptr [rax]
0x180006547  mov     [rbp+4Fh+var_70.Size], eax
0x18000654a  lea     rax, word_18000F23A
0x180006551  mov     [rbp+4Fh+var_60], rax
0x180006555  mov     rax, r14
0x180006558  sub     eax, edi
0x18000655a  mov     dword ptr [rbp+4Fh+var_70.0Ch], 2
0x180006561  mov     [rbp+4Fh+var_58], 23h ; '#'
0x180006568  mov     [rbp+4Fh+var_54], 1
0x18000656f  mov     [rbp+4Fh+var_90], eax
0x180006572  mov     eax, [rbp+4Fh+var_90]
0x180006575  mov     rcx, cs:RegHandle; RegHandle
0x18000657c  lea     rax, [rbp+4Fh+var_70]
0x180006580  mov     [rsp+0C0h+UserData], rax; UserData
0x180006585  mov     [rsp+0C0h+UserDataCount], 3; UserDataCount
0x18000658d  call    cs:__imp_EventWriteTransfer
0x180006593  test    r15, r15
0x180006596  jz      short loc_180006603
0x180006598  mov     rbx, [rbx]
0x18000659b  mov     dword ptr [rsi+6Ch], 2
0x1800065a2  call    cs:__imp_GetCurrentThreadId
0x1800065a8  mov     eax, eax
0x1800065aa  lea     rcx, [rsi+50h]
0x1800065ae  mov     [rsi+70h], rax
0x1800065b2  mov     [rsi+58h], r13d
0x1800065b6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800065bc  mov     eax, [rbp+4Fh+arg_20]
0x1800065bf  mov     r9, r12
0x1800065c2  mov     r8, [rsi+48h]
0x1800065c6  mov     rdx, rbx
0x1800065c9  mov     [rsp+0C0h+UserDataCount], eax
0x1800065cd  mov     rcx, rsi
0x1800065d0  mov     rax, r15
0x1800065d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065d8  lea     rcx, [rsi+50h]
0x1800065dc  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800065e2  call    cs:__imp_GetCurrentThreadId
0x1800065e8  mov     [rsi+58h], eax
0x1800065eb  lea     rdi, _TraceLoggingMetadata
0x1800065f2  cmp     dword ptr [rsi+6Ch], 2
0x1800065f6  mov     [rsi+70h], r13
0x1800065fa  jnz     short loc_180006603
0x1800065fc  mov     dword ptr [rsi+6Ch], 1
0x180006603  mov     eax, cs:dword_180012000
0x180006609  cmp     eax, 4
0x18000660c  jbe     loc_18000669E
0x180006612  lea     rax, [rbp+4Fh+var_88]
0x180006616  mov     [rbp+4Fh+var_88], rsi
0x18000661a  mov     [rbp+4Fh+var_50], rax
0x18000661e  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x180006622  movzx   eax, cs:word_18000F0CE
0x180006629  sub     r14d, edi
0x18000662c  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x18000662f  xor     r9d, r9d; RelatedActivityId
0x180006632  mov     rax, cs:off_180012008
0x180006639  xor     r8d, r8d; ActivityId
0x18000663c  mov     [rbp+4Fh+var_70.Ptr], rax
0x180006640  mov     [rbp+4Fh+var_48], 8
0x180006648  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], 0B000000h
0x18000664f  mov     [rbp+4Fh+EventDescriptor.Keyword], r13
0x180006653  movzx   eax, word ptr [rax]
0x180006656  mov     [rbp+4Fh+var_70.Size], eax
0x180006659  lea     rax, unk_18000F0D8
0x180006660  mov     [rbp+4Fh+var_60], rax
0x180006664  mov     dword ptr [rbp+4Fh+var_70.0Ch], 2
0x18000666b  mov     [rbp+4Fh+var_58], 24h ; '$'
0x180006672  mov     [rbp+4Fh+var_54], 1
0x180006679  mov     [rbp+4Fh+var_90], r14d
0x18000667d  mov     eax, [rbp+4Fh+var_90]
0x180006680  mov     rcx, cs:RegHandle; RegHandle
0x180006687  lea     rax, [rbp+4Fh+var_70]
0x18000668b  mov     [rsp+0C0h+UserData], rax; UserData
0x180006690  mov     [rsp+0C0h+UserDataCount], 3; UserDataCount
0x180006698  call    cs:__imp_EventWriteTransfer
0x18000669e  mov     rcx, [rbp+4Fh+var_40]
0x1800066a2  xor     rcx, rsp; StackCookie
0x1800066a5  call    __security_check_cookie
0x1800066aa  mov     rbx, [rsp+0C0h+arg_8]
0x1800066b2  add     rsp, 90h
0x1800066b9  pop     r15
0x1800066bb  pop     r14
0x1800066bd  pop     r13
0x1800066bf  pop     r12
0x1800066c1  pop     rdi
0x1800066c2  pop     rsi
0x1800066c3  pop     rbp
0x1800066c4  retn
```
