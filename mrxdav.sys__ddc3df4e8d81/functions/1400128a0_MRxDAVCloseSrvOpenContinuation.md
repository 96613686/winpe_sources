# MRxDAVCloseSrvOpenContinuation

- ea: `0x1400128a0`
- end: `0x140012ecd`
- name: `MRxDAVCloseSrvOpenContinuation`
- size: `1581`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x1400024b0`
- `0x140002ac4`
- `0x140002b60`
- `0x1400128a0`
- `0x1400252f8`
- `0x140025808`
- `0x1400287f4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140012939`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012980`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400129c7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012a14`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012ae9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012b58`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012bdc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012da3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012e92`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012939`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012980`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400129c7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012a14`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012ae9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012b58`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012bdc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012da3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012e92`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012a4b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012cd4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012a4b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012cd4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140012a66`
- `ntoskrnl!ExReleaseResourceLite` at `0x140012d0c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140012a66`
- `ntoskrnl!ExReleaseResourceLite` at `0x140012d0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d70`
- `ntoskrnl!ZwClose` at `0x140012b92`
- `ntoskrnl!ZwClose` at `0x140012b92`
- `ntoskrnl!IoGetCurrentProcess` at `0x140012b49`
- `ntoskrnl!IoGetCurrentProcess` at `0x140012b49`
- `ntoskrnl!ObfDereferenceObject` at `0x140012c22`
- `ntoskrnl!ObfDereferenceObject` at `0x140012c22`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140012905`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140012905`
- `ntoskrnl!IoRaiseInformationalHardError` at `0x140012e69`
- `ntoskrnl!IoRaiseInformationalHardError` at `0x140012e69`
- `rdbss!RxLogEventWithAnnotation` at `0x140012e4e`
- `rdbss!RxLogEventWithAnnotation` at `0x140012e4e`

## pseudocode

```c
__int64 __fastcall MRxDAVCloseSrvOpenContinuation(__int64 a1, __int64 a2)
{
  __int64 v2; // r12
  __int64 v4; // rsi
  int v5; // r15d
  __int64 v6; // r14
  __int64 v7; // rcx
  __int64 v8; // rbp
  __int64 v9; // rbx
  HANDLE v10; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax
  __int64 v13; // rbx
  HANDLE v14; // rax
  __int64 v15; // rbx
  unsigned int v16; // eax
  signed __int32 v17; // eax
  int v18; // ecx
  signed __int32 v19; // edi
  __int64 v20; // rbx
  HANDLE CurrentThreadId; // rax
  HANDLE v22; // rdi
  __int64 v23; // rsi
  PEPROCESS CurrentProcess; // rbx
  HANDLE v25; // rax
  __int64 v26; // r8
  __int64 v27; // rbx
  unsigned int v28; // eax
  __int64 v29; // r12
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rdx
  _QWORD *v33; // rax
  __int64 v34; // r8
  _QWORD *v35; // rdx
  void *v36; // rcx
  __int64 v37; // rbx
  HANDLE v38; // rax
  USHORT v39; // ax
  __int64 v40; // rbx
  HANDLE v41; // rax
  struct _UNICODE_STRING Annotation; // [rsp+40h] [rbp-58h] BYREF
  int v45; // [rsp+A8h] [rbp+10h]
  signed __int32 v46; // [rsp+B0h] [rbp+18h]
  __int64 v47; // [rsp+B8h] [rbp+20h]

  v2 = *(_QWORD *)(a2 + 72);
  v4 = a1;
  v5 = 0;
  v6 = 0;
  if ( v2 )
    v6 = *(_QWORD *)(v2 + 48);
  v7 = *(_QWORD *)(v2 + 32);
  v8 = 0;
  if ( v7 )
    v8 = *(_QWORD *)(v7 + 136);
  if ( v6 )
  {
    v47 = *(_QWORD *)(a2 + 56);
    if ( ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(v7 + 8)) != 1 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
LABEL_19:
        if ( *(_QWORD *)(v6 + 48) )
        {
          ExAcquireResourceExclusiveLite(&LockTokenEntryListLock, 1u);
          *(_DWORD *)(*(_QWORD *)(v6 + 56) + 52LL) = 0;
          ExReleaseResourceLite(&LockTokenEntryListLock);
        }
        v17 = _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 16), 0, 0);
        v18 = *(_DWORD *)(v8 + 24);
        v19 = v17;
        v46 = v17;
        if ( !v18 || (v45 = 0, v18 == 1) && *(_QWORD *)(v6 + 48) )
        {
          v45 = 1;
          v5 = UMRxSubmitAsyncEngUserModeRequest(
                 v4,
                 (_QWORD *)a2,
                 (__int64)MRxDAVFormatUserModeCloseRequest,
                 (__int64)MRxDAVPrecompleteUserModeCloseRequest);
          if ( v5 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
            {
              v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              CurrentThreadId = PsGetCurrentThreadId();
              WPP_SF_qD(v20, 128, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, CurrentThreadId, v5);
            }
          }
        }
        if ( *(_DWORD *)v8 )
          goto LABEL_40;
        if ( *(_DWORD *)(v6 + 44) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
          {
            v22 = *(HANDLE *)v6;
            v23 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            CurrentProcess = IoGetCurrentProcess();
            v25 = PsGetCurrentThreadId();
            WPP_SF_qqqqq(v23, 129, v26, v25, v22, CurrentProcess, v2, v6);
            v19 = v46;
          }
          ZwClose(*(HANDLE *)v6);
          v4 = a1;
          *(_QWORD *)v6 = 0;
          *(_QWORD *)(v6 + 8) = 0;
        }
        if ( !*(_QWORD *)(v6 + 24) )
        {
LABEL_40:
          v29 = v47;
        }
        else
        {
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) == 0 )
          {
            v29 = v47;
          }
          else
          {
            v27 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v28 = (unsigned int)PsGetCurrentThreadId();
            v29 = v47;
            WPP_SF_qZ(v27, 130, (unsigned int)WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v28, v47 + 360);
          }
          ObfDereferenceObject(*(PVOID *)(v6 + 24));
          *(_QWORD *)(v6 + 24) = 0;
        }
        v30 = v45;
        if ( v45 )
        {
          if ( *(_DWORD *)(v8 + 12) )
          {
            MRxDAVInvalidateFileInfoCache(a2);
            v31 = *(_QWORD *)(a2 + 56);
            v32 = *(_BYTE *)(a2 + 32) ? *(_QWORD *)(v31 + 120) : *(_QWORD *)(a2 + 648);
            MRxDAVCacheFileNotFoundWithName(v31 + 360, v32);
            if ( (*(_DWORD *)(v29 + 232) & 0x4010) == 0x4010 )
              MRxDAVRemoveEncryptedDirectoryKey((PUNICODE_STRING)(v8 + 40));
          }
          if ( v19 )
            MRxDAVInvalidateFileInfoCache(a2);
          v5 = *(_DWORD *)(v4 + 128);
          v30 = v45;
        }
        if ( !v5 && v30 )
          *(_DWORD *)(v8 + 60) = 0;
        if ( *(_QWORD *)(v6 + 48) )
        {
          ExAcquireResourceExclusiveLite(&LockTokenEntryListLock, 1u);
          v33 = *(_QWORD **)(v6 + 56);
          v34 = *v33;
          if ( *(_QWORD **)(*v33 + 8LL) != v33 || (v35 = (_QWORD *)v33[1], (_QWORD *)*v35 != v33) )
            __fastfail(3u);
          *v35 = v34;
          *(_QWORD *)(v34 + 8) = v35;
          ExReleaseResourceLite(&LockTokenEntryListLock);
          ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)(v6 + 56) + 24LL), 0);
          *(_QWORD *)(*(_QWORD *)(v6 + 56) + 24LL) = 0;
          ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)(v6 + 56) + 32LL), 0);
          *(_QWORD *)(*(_QWORD *)(v6 + 56) + 32LL) = 0;
          ExFreePoolWithTag(*(PVOID *)(v6 + 56), 0);
          v36 = *(void **)(v6 + 48);
          *(_QWORD *)(v6 + 56) = 0;
          ExFreePoolWithTag(v36, 0);
          *(_QWORD *)(v6 + 48) = 0;
          *(_DWORD *)(v8 + 24) = 0;
        }
        goto LABEL_58;
      }
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v10 = PsGetCurrentThreadId();
        WPP_SF_q(v9, 124, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v10);
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v12 = PsGetCurrentThreadId();
        WPP_SF_q(v11, 125, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v12);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v13 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v14 = PsGetCurrentThreadId();
          WPP_SF_qqq(v13, 126, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v14, v4, a2);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v16 = (unsigned int)PsGetCurrentThreadId();
          WPP_SF_qZ(v15, 127, (unsigned int)WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v16, v47 + 360);
        }
      }
    }
    goto LABEL_19;
  }
LABEL_58:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v37 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v38 = PsGetCurrentThreadId();
    WPP_SF_qD(v37, 131, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v38, v5);
  }
  if ( *(_BYTE *)(a2 + 32) == 2 )
  {
    if ( v5 < 0 && _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 16), 0, 0) )
    {
      v39 = 190;
      if ( *(_WORD *)(v8 + 40) <= 0xBEu )
      {
        v39 = *(_WORD *)(v8 + 40);
        Annotation.Length = v39;
      }
      else
      {
        Annotation.Length = 190;
      }
      Annotation.MaximumLength = v39;
      Annotation.Buffer = *(PWSTR *)(v8 + 48);
      RxLogEventWithAnnotation(g_MRxDAVDeviceObject, 0x800039D0, -1073741278, 0, 0, &Annotation, 1u);
      if ( !IoRaiseInformationalHardError(-1073741278, (PUNICODE_STRING)(v8 + 40), KeGetCurrentThread())
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v40 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v41 = PsGetCurrentThreadId();
        WPP_SF_q(v40, 132, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v41);
      }
    }
    return 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400128a0  mov     [rsp+arg_0], rcx
0x1400128a5  push    rbx
0x1400128a6  push    rbp
0x1400128a7  push    rsi
0x1400128a8  push    rdi
0x1400128a9  push    r12
0x1400128ab  push    r13
0x1400128ad  push    r14
0x1400128af  push    r15
0x1400128b1  sub     rsp, 58h
0x1400128b5  mov     r12, [rdx+48h]
0x1400128b9  xor     edi, edi
0x1400128bb  mov     r13, rdx
0x1400128be  mov     rsi, rcx
0x1400128c1  mov     r15d, edi
0x1400128c4  mov     r14d, edi
0x1400128c7  test    r12, r12
0x1400128ca  jz      short loc_1400128D1
0x1400128cc  mov     r14, [r12+30h]
0x1400128d1  mov     rcx, [r12+20h]
0x1400128d6  mov     rbp, rdi
0x1400128d9  test    rcx, rcx
0x1400128dc  jz      short loc_1400128E5
0x1400128de  mov     rbp, [rcx+88h]
0x1400128e5  test    r14, r14
0x1400128e8  jz      loc_140012D83
0x1400128ee  mov     rax, [rdx+38h]
0x1400128f2  mov     rcx, [rcx+8]; Resource
0x1400128f6  mov     [rsp+98h+arg_18], rax
0x1400128fe  lea     rdi, [rax+168h]
0x140012905  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14001290c  nop     dword ptr [rax+rax+00h]
0x140012911  cmp     al, 1
0x140012913  jz      short loc_14001295C
0x140012915  mov     rbx, cs:WPP_GLOBAL_Control
0x14001291c  lea     rax, WPP_GLOBAL_Control
0x140012923  cmp     rbx, rax
0x140012926  jz      loc_140012A3C
0x14001292c  test    dword ptr [rbx+2Ch], 2000h
0x140012933  jz      short loc_14001295C
0x140012935  mov     rbx, [rbx+18h]
0x140012939  call    cs:__imp_PsGetCurrentThreadId
0x140012940  nop     dword ptr [rax+rax+00h]
0x140012945  mov     edx, 7Ch ; '|'
0x14001294a  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140012951  mov     r9, rax
0x140012954  mov     rcx, rbx
0x140012957  call    WPP_SF_q
0x14001295c  mov     rbx, cs:WPP_GLOBAL_Control
0x140012963  lea     rax, WPP_GLOBAL_Control
0x14001296a  cmp     rbx, rax
0x14001296d  jz      loc_140012A3C
0x140012973  test    dword ptr [rbx+2Ch], 4000h
0x14001297a  jz      short loc_1400129A3
0x14001297c  mov     rbx, [rbx+18h]
0x140012980  call    cs:__imp_PsGetCurrentThreadId
0x140012987  nop     dword ptr [rax+rax+00h]
0x14001298c  mov     edx, 7Dh ; '}'
0x140012991  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140012998  mov     r9, rax
0x14001299b  mov     rcx, rbx
0x14001299e  call    WPP_SF_q
0x1400129a3  mov     rbx, cs:WPP_GLOBAL_Control
0x1400129aa  lea     rax, WPP_GLOBAL_Control
0x1400129b1  cmp     rbx, rax
0x1400129b4  jz      loc_140012A3C
0x1400129ba  test    dword ptr [rbx+2Ch], 2000h
0x1400129c1  jz      short loc_1400129F4
0x1400129c3  mov     rbx, [rbx+18h]
0x1400129c7  call    cs:__imp_PsGetCurrentThreadId
0x1400129ce  nop     dword ptr [rax+rax+00h]
0x1400129d3  mov     edx, 7Eh ; '~'
0x1400129d8  mov     [rsp+98h+Annotation], r13
0x1400129dd  mov     r9, rax
0x1400129e0  mov     qword ptr [rsp+98h+DataBufferLength], rsi
0x1400129e5  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x1400129ec  mov     rcx, rbx
0x1400129ef  call    WPP_SF_qqq
0x1400129f4  mov     rbx, cs:WPP_GLOBAL_Control
0x1400129fb  lea     rax, WPP_GLOBAL_Control
0x140012a02  cmp     rbx, rax
0x140012a05  jz      short loc_140012A3C
0x140012a07  test    dword ptr [rbx+2Ch], 4000h
0x140012a0e  jz      short loc_140012A3C
0x140012a10  mov     rbx, [rbx+18h]
0x140012a14  call    cs:__imp_PsGetCurrentThreadId
0x140012a1b  nop     dword ptr [rax+rax+00h]
0x140012a20  mov     edx, 7Fh
0x140012a25  mov     qword ptr [rsp+98h+DataBufferLength], rdi
0x140012a2a  mov     r9, rax
0x140012a2d  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140012a34  mov     rcx, rbx
0x140012a37  call    WPP_SF_qZ
0x140012a3c  cmp     [r14+30h], r15
0x140012a40  jz      short loc_140012A72
0x140012a42  mov     dl, 1; Wait
0x140012a44  lea     rcx, LockTokenEntryListLock; Resource
0x140012a4b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140012a52  nop     dword ptr [rax+rax+00h]
0x140012a57  mov     rax, [r14+38h]
0x140012a5b  lea     rcx, LockTokenEntryListLock; Resource
0x140012a62  mov     [rax+34h], r15d
0x140012a66  call    cs:__imp_ExReleaseResourceLite
0x140012a6d  nop     dword ptr [rax+rax+00h]
0x140012a72  xor     ecx, ecx
0x140012a74  xor     eax, eax
0x140012a76  lock cmpxchg [rbp+10h], ecx
0x140012a7b  mov     ecx, [rbp+18h]
0x140012a7e  mov     edi, eax
0x140012a80  mov     [rsp+98h+arg_10], eax
0x140012a87  test    ecx, ecx
0x140012a89  jz      short loc_140012A9E
0x140012a8b  mov     [rsp+98h+arg_8], r15d
0x140012a93  cmp     ecx, 1
0x140012a96  jnz     short loc_140012B11
0x140012a98  cmp     [r14+30h], r15
0x140012a9c  jz      short loc_140012B11
0x140012a9e  lea     r9, MRxDAVPrecompleteUserModeCloseRequest
0x140012aa5  mov     [rsp+98h+arg_8], 1
0x140012ab0  lea     r8, MRxDAVFormatUserModeCloseRequest
0x140012ab7  mov     rdx, r13
0x140012aba  mov     rcx, rsi
0x140012abd  call    UMRxSubmitAsyncEngUserModeRequest
0x140012ac2  mov     r15d, eax
0x140012ac5  test    eax, eax
0x140012ac7  jz      short loc_140012B11
0x140012ac9  mov     rbx, cs:WPP_GLOBAL_Control
0x140012ad0  lea     rax, WPP_GLOBAL_Control
0x140012ad7  cmp     rbx, rax
0x140012ada  jz      short loc_140012B18
0x140012adc  test    dword ptr [rbx+2Ch], 2000h
0x140012ae3  jz      short loc_140012B18
0x140012ae5  mov     rbx, [rbx+18h]
0x140012ae9  call    cs:__imp_PsGetCurrentThreadId
0x140012af0  nop     dword ptr [rax+rax+00h]
0x140012af5  mov     edx, 80h
0x140012afa  mov     dword ptr [rsp+98h+DataBufferLength], r15d
0x140012aff  mov     r9, rax
0x140012b02  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140012b09  mov     rcx, rbx
0x140012b0c  call    WPP_SF_qD
0x140012b11  lea     rax, WPP_GLOBAL_Control
0x140012b18  cmp     dword ptr [rbp+0], 0
0x140012b1c  jnz     loc_140012C38
0x140012b22  cmp     dword ptr [r14+2Ch], 0
0x140012b27  jz      loc_140012BB5
0x140012b2d  mov     rsi, cs:WPP_GLOBAL_Control
0x140012b34  cmp     rsi, rax
0x140012b37  jz      short loc_140012B8F
0x140012b39  test    dword ptr [rsi+2Ch], 4000h
0x140012b40  jz      short loc_140012B8F
0x140012b42  mov     rdi, [r14]
0x140012b45  mov     rsi, [rsi+18h]
0x140012b49  call    cs:__imp_IoGetCurrentProcess
0x140012b50  nop     dword ptr [rax+rax+00h]
0x140012b55  mov     rbx, rax
0x140012b58  call    cs:__imp_PsGetCurrentThreadId
0x140012b5f  nop     dword ptr [rax+rax+00h]
0x140012b64  mov     [rsp+98h+var_60], r14
0x140012b69  mov     edx, 81h
0x140012b6e  mov     qword ptr [rsp+98h+AnnotationCount], r12
0x140012b73  mov     r9, rax
0x140012b76  mov     [rsp+98h+Annotation], rbx
0x140012b7b  mov     rcx, rsi
0x140012b7e  mov     qword ptr [rsp+98h+DataBufferLength], rdi
0x140012b83  call    WPP_SF_qqqqq
0x140012b88  mov     edi, [rsp+98h+arg_10]
0x140012b8f  mov     rcx, [r14]; Handle
0x140012b92  call    cs:__imp_ZwClose
0x140012b99  nop     dword ptr [rax+rax+00h]
0x140012b9e  mov     rsi, [rsp+98h+arg_0]
0x140012ba6  mov     qword ptr [r14], 0
0x140012bad  mov     qword ptr [r14+8], 0
0x140012bb5  cmp     qword ptr [r14+18h], 0
0x140012bba  jz      short loc_140012C38
0x140012bbc  mov     rbx, cs:WPP_GLOBAL_Control
0x140012bc3  lea     rax, WPP_GLOBAL_Control
0x140012bca  cmp     rbx, rax
0x140012bcd  jz      short loc_140012C16
0x140012bcf  test    dword ptr [rbx+2Ch], 4000h
0x140012bd6  jz      short loc_140012C16
0x140012bd8  mov     rbx, [rbx+18h]
0x140012bdc  call    cs:__imp_PsGetCurrentThreadId
0x140012be3  nop     dword ptr [rax+rax+00h]
0x140012be8  mov     r12, [rsp+98h+arg_18]
0x140012bf0  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140012bf7  mov     r9, rax
0x140012bfa  mov     edx, 82h
0x140012bff  mov     rcx, rbx
0x140012c02  lea     rax, [r12+168h]
0x140012c0a  mov     qword ptr [rsp+98h+DataBufferLength], rax
0x140012c0f  call    WPP_SF_qZ
0x140012c14  jmp     short loc_140012C1E
0x140012c16  mov     r12, [rsp+98h+arg_18]
0x140012c1e  mov     rcx, [r14+18h]; Object
0x140012c22  call    cs:__imp_ObfDereferenceObject
0x140012c29  nop     dword ptr [rax+rax+00h]
0x140012c2e  mov     qword ptr [r14+18h], 0
0x140012c36  jmp     short loc_140012C40
0x140012c38  mov     r12, [rsp+98h+arg_18]
0x140012c40  mov     eax, [rsp+98h+arg_8]
0x140012c47  test    eax, eax
0x140012c49  jz      short loc_140012CB3
0x140012c4b  cmp     dword ptr [rbp+0Ch], 0
0x140012c4f  jz      short loc_140012C99
0x140012c51  mov     rcx, r13
0x140012c54  call    MRxDAVInvalidateFileInfoCache
0x140012c59  cmp     byte ptr [r13+20h], 0
0x140012c5e  mov     rcx, [r13+38h]
0x140012c62  jnz     short loc_140012C6D
0x140012c64  mov     rdx, [r13+288h]
0x140012c6b  jmp     short loc_140012C71
0x140012c6d  mov     rdx, [rcx+78h]
0x140012c71  add     rcx, 168h
0x140012c78  call    MRxDAVCacheFileNotFoundWithName
0x140012c7d  mov     eax, [r12+0E8h]
0x140012c85  mov     ecx, 4010h
0x140012c8a  and     eax, ecx
0x140012c8c  cmp     eax, ecx
0x140012c8e  jnz     short loc_140012C99
0x140012c90  lea     rcx, [rbp+28h]; ValueName
0x140012c94  call    MRxDAVRemoveEncryptedDirectoryKey
0x140012c99  test    edi, edi
0x140012c9b  jz      short loc_140012CA5
0x140012c9d  mov     rcx, r13
0x140012ca0  call    MRxDAVInvalidateFileInfoCache
0x140012ca5  mov     r15d, [rsi+80h]
0x140012cac  mov     eax, [rsp+98h+arg_8]
0x140012cb3  xor     edi, edi
0x140012cb5  test    r15d, r15d
0x140012cb8  jnz     short loc_140012CC1
0x140012cba  test    eax, eax
0x140012cbc  jz      short loc_140012CC1
0x140012cbe  mov     [rbp+3Ch], edi
0x140012cc1  cmp     [r14+30h], rdi
0x140012cc5  jz      loc_140012D83
0x140012ccb  mov     dl, 1; Wait
0x140012ccd  lea     rcx, LockTokenEntryListLock; Resource
0x140012cd4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140012cdb  nop     dword ptr [rax+rax+00h]
0x140012ce0  mov     rax, [r14+38h]
0x140012ce4  mov     r8, [rax]
0x140012ce7  cmp     [r8+8], rax
0x140012ceb  jnz     loc_140012E03
0x140012cf1  mov     rdx, [rax+8]
0x140012cf5  cmp     [rdx], rax
0x140012cf8  jnz     loc_140012E03
0x140012cfe  mov     [rdx], r8
0x140012d01  lea     rcx, LockTokenEntryListLock; Resource
0x140012d08  mov     [r8+8], rdx
0x140012d0c  call    cs:__imp_ExReleaseResourceLite
0x140012d13  nop     dword ptr [rax+rax+00h]
0x140012d18  mov     rcx, [r14+38h]
0x140012d1c  xor     edx, edx; Tag
0x140012d1e  mov     rcx, [rcx+18h]; P
0x140012d22  call    cs:__imp_ExFreePoolWithTag
0x140012d29  nop     dword ptr [rax+rax+00h]
0x140012d2e  mov     rax, [r14+38h]
0x140012d32  xor     edx, edx; Tag
0x140012d34  mov     [rax+18h], rdi
0x140012d38  mov     rcx, [r14+38h]
0x140012d3c  mov     rcx, [rcx+20h]; P
0x140012d40  call    cs:__imp_ExFreePoolWithTag
0x140012d47  nop     dword ptr [rax+rax+00h]
0x140012d4c  mov     rax, [r14+38h]
0x140012d50  xor     edx, edx; Tag
0x140012d52  mov     [rax+20h], rdi
0x140012d56  mov     rcx, [r14+38h]; P
0x140012d5a  call    cs:__imp_ExFreePoolWithTag
0x140012d61  nop     dword ptr [rax+rax+00h]
0x140012d66  mov     rcx, [r14+30h]; P
0x140012d6a  xor     edx, edx; Tag
0x140012d6c  mov     [r14+38h], rdi
0x140012d70  call    cs:__imp_ExFreePoolWithTag
0x140012d77  nop     dword ptr [rax+rax+00h]
0x140012d7c  mov     [r14+30h], rdi
0x140012d80  mov     [rbp+18h], edi
0x140012d83  mov     rbx, cs:WPP_GLOBAL_Control
0x140012d8a  lea     rsi, WPP_GLOBAL_Control
0x140012d91  cmp     rbx, rsi
0x140012d94  jz      short loc_140012DCB
0x140012d96  test    dword ptr [rbx+2Ch], 4000h
0x140012d9d  jz      short loc_140012DCB
0x140012d9f  mov     rbx, [rbx+18h]
0x140012da3  call    cs:__imp_PsGetCurrentThreadId
0x140012daa  nop     dword ptr [rax+rax+00h]
0x140012daf  mov     edx, 83h
0x140012db4  mov     dword ptr [rsp+98h+DataBufferLength], r15d
0x140012db9  mov     r9, rax
0x140012dbc  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140012dc3  mov     rcx, rbx
0x140012dc6  call    WPP_SF_qD
0x140012dcb  cmp     byte ptr [r13+20h], 2
0x140012dd0  jnz     loc_140012EB8
0x140012dd6  test    r15d, r15d
0x140012dd9  jns     loc_140012EB5
0x140012ddf  mov     ecx, edi
0x140012de1  xor     eax, eax
0x140012de3  lock cmpxchg [rbp+10h], ecx
0x140012de8  jz      loc_140012EB5
  ... truncated ...
```
