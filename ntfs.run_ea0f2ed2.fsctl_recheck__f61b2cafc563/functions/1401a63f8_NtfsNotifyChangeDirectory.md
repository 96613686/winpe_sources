# NtfsNotifyChangeDirectory

- ea: `0x1401a63f8`
- end: `0x1401a687a`
- name: `NtfsNotifyChangeDirectory`
- size: `1154`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID FsContext)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1401a7710`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000ea70`
- `0x140010be0`
- `0x140020de0`
- `0x1401841d0`
- `0x1401a63f8`

## import_xrefs

- `ntoskrnl!FsRtlNotifyFilterChangeDirectoryLite` at `0x1401a658b`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectoryLite` at `0x1401a658b`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401a66be`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401a6716`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401a66be`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401a6716`
- `ntoskrnl!PsIsThreadImpersonating` at `0x1401a64eb`
- `ntoskrnl!PsIsThreadImpersonating` at `0x1401a64eb`
- `ntoskrnl!SeTokenIsAdmin` at `0x1401a6733`
- `ntoskrnl!SeTokenIsAdmin` at `0x1401a6733`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401a6773`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401a6773`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1401a6801`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1401a6801`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a6784`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad78e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a6784`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad78e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a66a2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a66fa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a66a2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a66fa`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a6470`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a6470`

## pseudocode

```c
__int64 __fastcall NtfsNotifyChangeDirectory(__int64 a1, IRP *a2, __int64 a3, __int64 a4, _DWORD *FsContext)
{
  struct _SECURITY_SUBJECT_CONTEXT *PoolWithTag; // rsi
  __int64 (__fastcall *v9)(); // r14
  int v10; // edi
  __int64 v11; // rdx
  int v12; // r12d
  PVOID v13; // rdi
  UCHAR MinorFunction; // al
  PACCESS_TOKEN ClientToken; // rcx
  char v17; // [rsp+61h] [rbp-67h]
  BOOLEAN WatchTree[4]; // [rsp+64h] [rbp-64h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+80h] [rbp-48h]
  ULONG CompletionFilter; // [rsp+D8h] [rbp+10h]

  PoolWithTag = 0;
  v9 = 0;
  v17 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  CompletionFilter = CurrentStackLocation->Parameters.Create.Options;
  v10 = CurrentStackLocation->Flags & 1;
  *(_DWORD *)WatchTree = v10;
  *(_DWORD *)(a1 + 12) |= 1u;
  NtfsPurgeFileRecordCache(a1);
  if ( !ExAcquireResourceSharedLite((PERESOURCE)(a3 + 2160), 1u) )
  {
    NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 1901753);
    JUMPOUT(0x1401A687ALL);
  }
  if ( !*(_WORD *)(*(_QWORD *)(a4 + 184) + 188LL) )
  {
LABEL_24:
    if ( NtfsStatusDebugFlags )
      goto LABEL_26;
    while ( 1 )
    {
      NtfsRaiseStatusInternal(a1, -1073741738, 0, 0, 854924);
LABEL_26:
      NtfsStatusTraceAndDebugInternal(a1, 3221225558LL, 854924);
    }
  }
  v12 = *(_DWORD *)(a4 + 512) & 4;
  if ( v12 || !v10 )
  {
    v13 = FsContext;
    goto LABEL_12;
  }
  v13 = FsContext;
  if ( (FsContext[1] & 0x80u) != 0 )
    goto LABEL_30;
  while ( 1 )
  {
    if ( byte_140095C7E )
    {
      if ( !_bittest16((const signed __int16 *)v13 + 52, 9u)
        && ((unsigned __int8)PsIsThreadImpersonating(KeGetCurrentThread(), v11, 0)
         || (unsigned __int8)NtfsEffectiveMode(a2) == 1) )
      {
        if ( !PoolWithTag )
        {
          PoolWithTag = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                              (POOL_TYPE)(PoolType | 0x10),
                                                              0x20u,
                                                              0x6446744Eu);
          SeCaptureSubjectContext(PoolWithTag);
        }
        ClientToken = PoolWithTag->ClientToken;
        if ( !PoolWithTag->ClientToken )
          ClientToken = PoolWithTag->PrimaryToken;
        if ( !SeTokenIsAdmin(ClientToken) )
          v9 = NtfsNotifyTraverseCheckEx;
      }
      if ( !v9 && PoolWithTag )
      {
        SeReleaseSubjectContext(PoolWithTag);
        ExFreePoolWithTag(PoolWithTag, 0);
        PoolWithTag = 0;
      }
    }
LABEL_12:
    if ( (*((_DWORD *)v13 + 1) & 0x800000) == 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(a3 + 4LL * (v12 != 0) + 2436));
      v17 = 1;
    }
    MinorFunction = CurrentStackLocation->MinorFunction;
    if ( !v12 )
      break;
    if ( MinorFunction != 3 || CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 1 )
    {
      FsRtlNotifyFilterChangeDirectory(
        *(PNOTIFY_SYNC *)(a3 + 1464),
        (PLIST_ENTRY)(a3 + 1448),
        v13,
        0,
        WatchTree[0],
        0,
        CompletionFilter,
        a2,
        0,
        *(PSECURITY_SUBJECT_CONTEXT *)(a4 + 184),
        0);
      goto LABEL_17;
    }
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225659LL, 855024);
    NtfsRaiseStatusInternal(a1, -1073741637, 0, 0, 855024);
LABEL_30:
    PoolWithTag = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                        (POOL_TYPE)(PoolType | 0x10),
                                                        0x20u,
                                                        0x6446744Eu);
    SeCaptureSubjectContext(PoolWithTag);
    v9 = NtfsNotifyTraverseCheck;
  }
  if ( MinorFunction == 3 && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart - 1 > 2 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225475LL, 855049);
    NtfsRaiseStatusInternal(a1, -1073741821, 0, 0, 855049);
    goto LABEL_24;
  }
  FsRtlNotifyFilterChangeDirectoryLite(
    a4 + 768,
    a4 + 752,
    v13,
    *(unsigned int *)WatchTree,
    CompletionFilter,
    a2,
    v9,
    PoolWithTag,
    TxfIsoReportChangeFilter);
LABEL_17:
  if ( v17 && (*((_DWORD *)v13 + 1) & 0x800000) == 0 )
    _InterlockedOr((volatile signed __int32 *)v13 + 1, 0x800000u);
  NtfsReleaseVcb(a1, a3);
  NtfsExtendedCompleteRequestInternal(a1, 0, 0, 0, 1);
  return 259;
}

```

## disassembly

```asm
0x1401a63f8  mov     rax, rsp
0x1401a63fb  mov     [rax+18h], r8
0x1401a63ff  mov     [rax+8], rcx
0x1401a6403  push    rbx
0x1401a6404  push    rsi
0x1401a6405  push    rdi
0x1401a6406  push    r12
0x1401a6408  push    r13
0x1401a640a  push    r14
0x1401a640c  push    r15
0x1401a640e  sub     rsp, 90h
0x1401a6415  mov     r13, r9
0x1401a6418  mov     r15, r8
0x1401a641b  mov     [rax-58h], rdx
0x1401a641f  mov     rbx, rcx
0x1401a6422  xor     ecx, ecx
0x1401a6424  mov     esi, ecx
0x1401a6426  mov     [rax-60h], rcx
0x1401a642a  mov     r14d, ecx
0x1401a642d  mov     [rax-66h], cl
0x1401a6430  mov     [rax-68h], cl
0x1401a6433  mov     [rax-67h], cl
0x1401a6436  mov     rax, [rdx+0B8h]
0x1401a643d  mov     [rsp+0C8h+var_48], rax
0x1401a6445  mov     ecx, [rax+10h]
0x1401a6448  mov     [rsp+0C8h+arg_8], ecx
0x1401a644f  mov     al, [rax+2]
0x1401a6452  and     al, 1
0x1401a6454  movzx   edi, al
0x1401a6457  mov     dword ptr [rsp+0C8h+var_64], edi
0x1401a645b  or      dword ptr [rbx+0Ch], 1
0x1401a645f  mov     rcx, rbx
0x1401a6462  call    NtfsPurgeFileRecordCache
0x1401a6467  lea     rcx, [r15+870h]; Resource
0x1401a646e  mov     dl, 1; Wait
0x1401a6470  call    cs:__imp_ExAcquireResourceSharedLite
0x1401a6477  nop     dword ptr [rax+rax+00h]
0x1401a647c  xor     r8d, r8d
0x1401a647f  test    al, al
0x1401a6481  jz      loc_1401A685A
0x1401a6487  mov     rax, [r13+0B8h]
0x1401a648e  cmp     [rax+0BCh], r8w
0x1401a6496  jz      loc_1401A661A
0x1401a649c  mov     r12d, [r13+200h]
0x1401a64a3  and     r12d, 4
0x1401a64a7  setnz   [rsp+0C8h+var_66]
0x1401a64ac  test    r12d, r12d
0x1401a64af  jnz     short loc_1401A6519
0x1401a64b1  test    edi, edi
0x1401a64b3  jz      short loc_1401A6519
0x1401a64b5  mov     rdi, [rsp+0C8h+FsContext]
0x1401a64bd  mov     eax, [rdi+4]
0x1401a64c0  test    al, al
0x1401a64c2  js      loc_1401A668E
0x1401a64c8  mov     [rsp+0C8h+var_68], r8b
0x1401a64cd  cmp     cs:byte_140095C7E, 0
0x1401a64d4  jz      short loc_1401A6521
0x1401a64d6  bt      word ptr [rdi+68h], 9
0x1401a64dc  jb      loc_1401A6754
0x1401a64e2  mov     rcx, gs:188h
0x1401a64eb  call    cs:__imp_PsIsThreadImpersonating
0x1401a64f2  nop     dword ptr [rax+rax+00h]
0x1401a64f7  test    al, al
0x1401a64f9  jnz     loc_1401A66E3
0x1401a64ff  mov     rcx, [rsp+0C8h+var_58]
0x1401a6504  call    NtfsEffectiveMode
0x1401a6509  cmp     al, 1
0x1401a650b  jz      loc_1401A66E3
0x1401a6511  xor     r8d, r8d
0x1401a6514  jmp     loc_1401A6754
0x1401a6519  mov     rdi, [rsp+0C8h+FsContext]
0x1401a6521  test    dword ptr [rdi+4], 800000h
0x1401a6528  jz      loc_1401A65BB
0x1401a652e  mov     rcx, [rsp+0C8h+var_48]
0x1401a6536  mov     al, [rcx+1]
0x1401a6539  test    r12d, r12d
0x1401a653c  jnz     loc_1401A67A5
0x1401a6542  cmp     al, 3
0x1401a6544  jz      loc_1401A65D3
0x1401a654a  lea     rdx, [r13+2F0h]
0x1401a6551  lea     rcx, [r13+300h]
0x1401a6558  lea     rax, TxfIsoReportChangeFilter
0x1401a655f  mov     [rsp+0C8h+TraverseCallback], rax
0x1401a6564  mov     [rsp+0C8h+NotifyIrp], rsi
0x1401a6569  mov     qword ptr [rsp+0C8h+CompletionFilter], r14
0x1401a656e  mov     rax, [rsp+0C8h+var_58]
0x1401a6573  mov     qword ptr [rsp+0C8h+IgnoreBuffer], rax
0x1401a6578  mov     eax, [rsp+0C8h+arg_8]
0x1401a657f  mov     dword ptr [rsp+0C8h+WatchTree], eax
0x1401a6583  mov     r9d, dword ptr [rsp+0C8h+var_64]
0x1401a6588  mov     r8, rdi
0x1401a658b  call    cs:__imp_FsRtlNotifyFilterChangeDirectoryLite
0x1401a6592  nop     dword ptr [rax+rax+00h]
0x1401a6597  cmp     [rsp+0C8h+var_67], 0
0x1401a659c  jz      loc_1401A6812
0x1401a65a2  mov     eax, [rdi+4]
0x1401a65a5  mov     ecx, 800000h
0x1401a65aa  test    ecx, eax
0x1401a65ac  jnz     loc_1401A6812
0x1401a65b2  lock or [rdi+4], ecx
0x1401a65b6  jmp     loc_1401A6812
0x1401a65bb  movzx   eax, [rsp+0C8h+var_66]
0x1401a65c0  lock inc dword ptr [r15+rax*4+984h]
0x1401a65c9  mov     [rsp+0C8h+var_67], 1
0x1401a65ce  jmp     loc_1401A652E
0x1401a65d3  mov     eax, [rcx+18h]
0x1401a65d6  dec     eax
0x1401a65d8  cmp     eax, 2
0x1401a65db  jbe     loc_1401A654A
0x1401a65e1  mov     al, cs:NtfsStatusDebugFlags
0x1401a65e7  test    al, al
0x1401a65e9  jz      short loc_1401A65FE
0x1401a65eb  mov     edx, 0C0000003h
0x1401a65f0  mov     r8d, 0D0C09h
0x1401a65f6  mov     rcx, rbx
0x1401a65f9  call    NtfsStatusTraceAndDebugInternal
0x1401a65fe  mov     qword ptr [rsp+0C8h+WatchTree], 0D0C09h
0x1401a6607  xor     r9d, r9d
0x1401a660a  xor     r8d, r8d
0x1401a660d  mov     edx, 0C0000003h
0x1401a6612  mov     rcx, rbx
0x1401a6615  call    NtfsRaiseStatusInternal
0x1401a661a  mov     al, cs:NtfsStatusDebugFlags
0x1401a6620  test    al, al
0x1401a6622  jnz     short loc_1401A6640
0x1401a6624  mov     qword ptr [rsp+0C8h+WatchTree], 0D0B8Ch
0x1401a662d  xor     r9d, r9d
0x1401a6630  xor     r8d, r8d
0x1401a6633  mov     edx, 0C0000056h
0x1401a6638  mov     rcx, rbx
0x1401a663b  call    NtfsRaiseStatusInternal
0x1401a6640  mov     edx, 0C0000056h
0x1401a6645  mov     r8d, 0D0B8Ch
0x1401a664b  mov     rcx, rbx
0x1401a664e  call    NtfsStatusTraceAndDebugInternal
0x1401a6653  jmp     short loc_1401A6624
0x1401a6655  mov     al, cs:NtfsStatusDebugFlags
0x1401a665b  test    al, al
0x1401a665d  jz      short loc_1401A6672
0x1401a665f  mov     edx, 0C00000BBh
0x1401a6664  mov     r8d, 0D0BF0h
0x1401a666a  mov     rcx, rbx
0x1401a666d  call    NtfsStatusTraceAndDebugInternal
0x1401a6672  mov     qword ptr [rsp+0C8h+WatchTree], 0D0BF0h
0x1401a667b  xor     r9d, r9d
0x1401a667e  xor     r8d, r8d
0x1401a6681  mov     edx, 0C00000BBh
0x1401a6686  mov     rcx, rbx
0x1401a6689  call    NtfsRaiseStatusInternal
0x1401a668e  mov     ecx, cs:PoolType
0x1401a6694  or      ecx, 10h; PoolType
0x1401a6697  mov     edx, 20h ; ' '; NumberOfBytes
0x1401a669c  mov     r8d, 6446744Eh; Tag
0x1401a66a2  call    cs:__imp_ExAllocatePoolWithTag
0x1401a66a9  nop     dword ptr [rax+rax+00h]
0x1401a66ae  mov     rsi, rax
0x1401a66b1  mov     [rsp+0C8h+var_60], rax
0x1401a66b6  mov     [rsp+0C8h+var_68], 1
0x1401a66bb  mov     rcx, rax; SubjectContext
0x1401a66be  call    cs:__imp_SeCaptureSubjectContext
0x1401a66c5  nop     dword ptr [rax+rax+00h]
0x1401a66ca  xor     r8d, r8d
0x1401a66cd  mov     [rsp+0C8h+var_68], r8b
0x1401a66d2  lea     r14, NtfsNotifyTraverseCheck
0x1401a66d9  mov     [rsp+0C8h+var_50], r14
0x1401a66de  jmp     loc_1401A64C8
0x1401a66e3  test    rsi, rsi
0x1401a66e6  jnz     short loc_1401A6727
0x1401a66e8  mov     ecx, cs:PoolType
0x1401a66ee  or      ecx, 10h; PoolType
0x1401a66f1  lea     edx, [rsi+20h]; NumberOfBytes
0x1401a66f4  mov     r8d, 6446744Eh; Tag
0x1401a66fa  call    cs:__imp_ExAllocatePoolWithTag
0x1401a6701  nop     dword ptr [rax+rax+00h]
0x1401a6706  mov     rsi, rax
0x1401a6709  mov     [rsp+0C8h+var_60], rax
0x1401a670e  mov     [rsp+0C8h+var_68], 1
0x1401a6713  mov     rcx, rax; SubjectContext
0x1401a6716  call    cs:__imp_SeCaptureSubjectContext
0x1401a671d  nop     dword ptr [rax+rax+00h]
0x1401a6722  mov     [rsp+0C8h+var_68], 0
0x1401a6727  mov     rcx, [rsi]
0x1401a672a  test    rcx, rcx
0x1401a672d  jnz     short loc_1401A6733
0x1401a672f  mov     rcx, [rsi+10h]; Token
0x1401a6733  call    cs:__imp_SeTokenIsAdmin
0x1401a673a  nop     dword ptr [rax+rax+00h]
0x1401a673f  lea     rcx, NtfsNotifyTraverseCheckEx
0x1401a6746  xor     r8d, r8d
0x1401a6749  test    al, al
0x1401a674b  cmovz   r14, rcx
0x1401a674f  mov     [rsp+0C8h+var_50], r14
0x1401a6754  mov     [rsp+0C8h+var_68], r8b
0x1401a6759  test    r14, r14
0x1401a675c  jnz     loc_1401A6521
0x1401a6762  mov     [rsp+0C8h+var_68], r8b
0x1401a6767  test    rsi, rsi
0x1401a676a  jz      loc_1401A6521
0x1401a6770  mov     rcx, rsi; SubjectContext
0x1401a6773  call    cs:__imp_SeReleaseSubjectContext
0x1401a677a  nop     dword ptr [rax+rax+00h]
0x1401a677f  xor     edx, edx; Tag
0x1401a6781  mov     rcx, rsi; P
0x1401a6784  call    cs:__imp_ExFreePoolWithTag
0x1401a678b  nop     dword ptr [rax+rax+00h]
0x1401a6790  xor     r8d, r8d
0x1401a6793  mov     esi, r8d
0x1401a6796  mov     [rsp+0C8h+var_60], r8
0x1401a679b  mov     [rsp+0C8h+var_68], r8b
0x1401a67a0  jmp     loc_1401A6521
0x1401a67a5  cmp     al, 3
0x1401a67a7  jnz     short loc_1401A67B3
0x1401a67a9  cmp     dword ptr [rcx+18h], 1
0x1401a67ad  jnz     loc_1401A6655
0x1401a67b3  lea     rdx, [r15+5A8h]; NotifyList
0x1401a67ba  mov     [rsp+0C8h+FilterCallback], r8; FilterCallback
0x1401a67bf  mov     rax, [r13+0B8h]
0x1401a67c6  mov     [rsp+0C8h+SubjectContext], rax; SubjectContext
0x1401a67cb  mov     [rsp+0C8h+TraverseCallback], r8; TraverseCallback
0x1401a67d0  mov     rax, [rsp+0C8h+var_58]
0x1401a67d5  mov     [rsp+0C8h+NotifyIrp], rax; NotifyIrp
0x1401a67da  mov     eax, [rsp+0C8h+arg_8]
0x1401a67e1  mov     [rsp+0C8h+CompletionFilter], eax; CompletionFilter
0x1401a67e5  mov     [rsp+0C8h+IgnoreBuffer], r8b; IgnoreBuffer
0x1401a67ea  mov     r9d, dword ptr [rsp+0C8h+var_64]
0x1401a67ef  mov     [rsp+0C8h+WatchTree], r9b; WatchTree
0x1401a67f4  xor     r9d, r9d; FullDirectoryName
0x1401a67f7  mov     r8, rdi; FsContext
0x1401a67fa  mov     rcx, [r15+5B8h]; NotifySync
0x1401a6801  call    cs:__imp_FsRtlNotifyFilterChangeDirectory
0x1401a6808  nop     dword ptr [rax+rax+00h]
0x1401a680d  jmp     loc_1401A6597
0x1401a6812  mov     al, cs:NtfsStatusDebugFlags
0x1401a6818  mov     rdx, r15
0x1401a681b  mov     rcx, rbx
0x1401a681e  call    NtfsReleaseVcb
0x1401a6823  mov     al, cs:NtfsStatusDebugFlags
0x1401a6829  mov     dword ptr [rsp+0C8h+WatchTree], 1
0x1401a6831  xor     r9d, r9d
0x1401a6834  xor     r8d, r8d
0x1401a6837  xor     edx, edx
0x1401a6839  mov     rcx, rbx
0x1401a683c  call    NtfsExtendedCompleteRequestInternal
0x1401a6841  mov     eax, 103h
0x1401a6846  add     rsp, 90h
0x1401a684d  pop     r15
0x1401a684f  pop     r14
0x1401a6851  pop     r13
0x1401a6853  pop     r12
0x1401a6855  pop     rdi
0x1401a6856  pop     rsi
0x1401a6857  pop     rbx
0x1401a6858  retn
0x1401a685a  mov     al, cs:NtfsStatusDebugFlags
0x1401a6860  mov     qword ptr [rsp+0C8h+WatchTree], 1D04B9h
0x1401a6869  xor     r9d, r9d
0x1401a686c  mov     edx, 0C00000D8h
0x1401a6871  mov     rcx, rbx
0x1401a6874  call    NtfsRaiseStatusInternal
0x1401a6879  nop
0x1402ad71c  push    rbx
0x1402ad71e  push    rbp
0x1402ad71f  push    rdi
0x1402ad720  sub     rsp, 60h
0x1402ad724  mov     rbp, rdx
0x1402ad727  movzx   edi, cl
0x1402ad72a  test    cl, cl
0x1402ad72c  jz      short loc_1402AD734
0x1402ad72e  mov     al, cs:NtfsStatusDebugFlags
0x1402ad734  mov     rbx, [rbp+0E0h]
0x1402ad73b  mov     rdx, rbx
0x1402ad73e  mov     rcx, [rbp+0D0h]
0x1402ad745  call    NtfsReleaseVcb
0x1402ad74a  mov     eax, edi
0x1402ad74c  test    dil, dil
0x1402ad74f  jz      short loc_1402AD79B
0x1402ad751  cmp     byte ptr [rbp+61h], 0
0x1402ad755  jz      short loc_1402AD782
0x1402ad757  mov     rcx, [rbp+0F0h]
0x1402ad75e  add     rcx, 4
0x1402ad762  mov     edx, 800000h
0x1402ad767  call    ClearFlagInterlocked
0x1402ad76c  cmp     byte ptr [rbp+62h], 0
0x1402ad770  jz      short loc_1402AD77B
0x1402ad772  lock dec dword ptr [rbx+988h]
0x1402ad779  jmp     short loc_1402AD782
0x1402ad77b  lock dec dword ptr [rbx+984h]
0x1402ad782  cmp     byte ptr [rbp+60h], 0
0x1402ad786  jz      short loc_1402AD79B
0x1402ad788  xor     edx, edx; Tag
0x1402ad78a  mov     rcx, [rbp+68h]; P
0x1402ad78e  call    cs:__imp_ExFreePoolWithTag
0x1402ad795  nop     dword ptr [rax+rax+00h]
0x1402ad79a  nop
0x1402ad79b  add     rsp, 60h
0x1402ad79f  pop     rdi
0x1402ad7a0  pop     rbp
0x1402ad7a1  pop     rbx
0x1402ad7a2  retn
```
