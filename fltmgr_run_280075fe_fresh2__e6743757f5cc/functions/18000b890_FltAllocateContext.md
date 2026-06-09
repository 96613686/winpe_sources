# FltAllocateContext

- ea: `0x18000b890`
- end: `0x18000beb1`
- name: `FltAllocateContext`
- size: `1569`
- prototype: `NTSTATUS __stdcall(PFLT_FILTER Filter, FLT_CONTEXT_TYPE ContextType, SIZE_T ContextSize, POOL_TYPE PoolType, PFLT_CONTEXT *ReturnedContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18007d770`

## callees

- `0x180009f20`
- `0x18000b890`
- `0x1800170e0`
- `0x180024880`
- `0x180024c00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000bbaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bcbd`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bbaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bcbd`
- `ntoskrnl!KeInitializeEvent` at `0x18000bc4d`
- `ntoskrnl!KeInitializeEvent` at `0x18000bc4d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000baa2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000bac7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000bbff`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000baa2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000bac7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000bbff`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000bb57`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000bb57`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18000bb02`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18000bb02`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000ba74`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000bb76`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000ba74`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000bb76`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18000b95e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18000b95e`
- `ntoskrnl!ExAcquireRundownProtection` at `0x18000b9ce`
- `ntoskrnl!ExAcquireRundownProtection` at `0x18000b9ce`
- `ntoskrnl!RtlWalkFrameChain` at `0x18000bda3`
- `ntoskrnl!RtlWalkFrameChain` at `0x18000be42`
- `ntoskrnl!RtlWalkFrameChain` at `0x18000bda3`
- `ntoskrnl!RtlWalkFrameChain` at `0x18000be42`

## pseudocode

```c
NTSTATUS __stdcall FltAllocateContext(
        PFLT_FILTER Filter,
        FLT_CONTEXT_TYPE ContextType,
        SIZE_T ContextSize,
        POOL_TYPE PoolType,
        PFLT_CONTEXT *ReturnedContext)
{
  int v5; // esi
  __int64 v8; // rbx
  _ALLOCATE_CONTEXT_HEADER *v9; // rbx
  SIZE_T v10; // r14
  int AllocationType; // ecx
  SIZE_T ContextCleanupCallback_high; // rcx
  struct _KEVENT **v13; // rdi
  unsigned __int8 v14; // al
  unsigned int v15; // ebx
  NTSTATUS result; // eax
  int v17; // ecx
  struct _KEVENT **PoolWithTag; // rax
  struct _KEVENT *v19; // rax
  struct _KEVENT *v20; // rdx
  int Reserved1; // ecx
  int v22; // eax
  int v23; // ecx
  struct _KEVENT *v24; // rax
  _FLT_OBJECT_LOG *v25; // rax
  unsigned __int64 v26; // rbx
  _FLT_OBJECT_LOG *RundownLog; // rcx
  unsigned __int64 v28; // rbx

  v5 = ContextType;
  if ( ContextSize > 0xFFFF )
    return -1073741306;
  if ( ContextType != 4 )
  {
    switch ( ContextType )
    {
      case 1u:
        v8 = 0;
        goto LABEL_6;
      case 2u:
        v8 = 1;
        goto LABEL_6;
      case 8u:
        v8 = 3;
        goto LABEL_6;
      case 0x10u:
        v8 = 4;
        goto LABEL_6;
      case 0x20u:
        v8 = 5;
        goto LABEL_6;
      case 0x40u:
        v8 = 6;
LABEL_6:
        if ( (ContextType & 0x7F) != 0 )
          goto LABEL_7;
        goto LABEL_85;
      default:
LABEL_85:
        *ReturnedContext = 0;
        result = -1073741637;
        break;
    }
    return result;
  }
  v8 = 2;
LABEL_7:
  _mm_lfence();
  v9 = Filter->SupportedContexts[v8];
  v10 = ContextSize + 96;
  while ( 1 )
  {
    if ( !v9 )
    {
      *ReturnedContext = 0;
      return -1071906794;
    }
    AllocationType = v9->AllocationType;
    if ( AllocationType == 1 )
      break;
    v17 = AllocationType - 2;
    if ( !v17 )
    {
      PoolWithTag = (struct _KEVENT **)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x400), v10, (ULONG)v9[1].Filter);
      v13 = PoolWithTag;
      if ( !ExPoolZeroingNativelySupported && PoolWithTag )
        goto LABEL_88;
      goto LABEL_14;
    }
    if ( v17 == 1 )
    {
      v13 = (struct _KEVENT **)((__int64 (__fastcall *)(_QWORD, SIZE_T, _QWORD))v9[1].Filter)(
                                 (unsigned int)PoolType,
                                 v10,
                                 ContextType);
      goto LABEL_14;
    }
LABEL_43:
    v9 = v9->Next;
  }
  ContextCleanupCallback_high = HIDWORD(v9[3].ContextCleanupCallback);
  if ( v10 != ContextCleanupCallback_high && ((v9->Flags & 2) == 0 || v10 >= ContextCleanupCallback_high) )
    goto LABEL_43;
  if ( PoolType == NonPagedPoolNx )
  {
    v13 = (struct _KEVENT **)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&v9[2]);
  }
  else
  {
    if ( PoolType == PagedPool )
    {
      v13 = (struct _KEVENT **)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)&v9[6]);
      goto LABEL_14;
    }
    PoolWithTag = (struct _KEVENT **)ExAllocatePoolWithTag(
                                       (POOL_TYPE)(PoolType | 0x400),
                                       v10,
                                       (ULONG)v9[7].ContextCleanupCallback);
    v13 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
LABEL_88:
      memset(PoolWithTag, 0, v10);
  }
LABEL_14:
  if ( !v13 )
    goto LABEL_39;
  memset(v13, 0, 0x60u);
  *((_DWORD *)v13 + 20) = 1;
  v13[1] = (struct _KEVENT *)v9;
  if ( v5 != 32 )
  {
    if ( v5 != 64 )
      goto LABEL_17;
    v24 = (struct _KEVENT *)ExAllocateFromNPagedLookasideList(&stru_18003F240);
    *v13 = v24;
    if ( v24 )
    {
      *(_QWORD *)&v24[3].Header.Lock = 0;
      v24[3].Header.WaitListHead.Flink = 0;
      v24[2].Header.WaitListHead.Flink = 0;
      (*v13)[2].Header.LockNV = 0;
      *(_QWORD *)&(*v13)->Header.Lock = 0;
      (*v13)->Header.WaitListHead.Flink = 0;
      LODWORD((*v13)->Header.WaitListHead.Blink) = 0;
      KeInitializeEvent(*v13 + 1, NotificationEvent, 0);
      goto LABEL_17;
    }
    DoFreeContextMemory(v13);
LABEL_39:
    *ReturnedContext = 0;
    return -1073741670;
  }
  v19 = (struct _KEVENT *)ExAllocateFromNPagedLookasideList(&stru_18003F040);
  *v13 = v19;
  if ( !v19 )
  {
    v20 = v13[1];
    Reserved1 = v20[1].Header.Reserved1;
    if ( Reserved1 == 1 )
    {
      v22 = *((_DWORD *)v13 + 18);
      if ( (v22 & 1) != 0 )
      {
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)&v20[8], v13);
      }
      else if ( (v22 & 8) != 0 )
      {
        ExFreePoolWithTag(v13, (ULONG)v20[9].Header.WaitListHead.Blink);
      }
      else
      {
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&v20[2].Header.WaitListHead.Blink, v13);
      }
    }
    else
    {
      v23 = Reserved1 - 2;
      if ( v23 )
      {
        if ( v23 == 1 )
          ((void (__fastcall *)(struct _KEVENT **, _QWORD))v20[1].Header.WaitListHead.Blink)(
            v13,
            LOWORD(v20[1].Header.Lock));
      }
      else
      {
        ExFreePoolWithTag(v13, (ULONG)v20[1].Header.WaitListHead.Flink);
      }
    }
    goto LABEL_39;
  }
  memset(v19, 0, 0x48u);
  *(_QWORD *)&(*v13)->Header.Lock = 0;
  (*v13)->Header.WaitListHead.Flink = (struct _LIST_ENTRY *)-1LL;
  (*v13)[2].Header.WaitListHead.Blink = 0;
LABEL_17:
  if ( PoolType == PagedPool )
    *((_DWORD *)v13 + 18) |= 1u;
  v14 = v9->AllocationType;
  if ( v14 == 2 || PoolType != PagedPool && PoolType != NonPagedPoolNx && v14 == 1 )
    *((_DWORD *)v13 + 18) |= 8u;
  if ( ExAcquireRundownProtection(&Filter->Base.RundownRef) )
  {
    if ( (FltGlobals[0] & 0x2000) != 0 && (Filter->Base.Flags & 0x2000000) != 0
      || (FltGlobals[0] & 0x4000) != 0 && (Filter->Base.Flags & 0x4000000) != 0
      || (FltGlobals[0] & 0x8000) != 0 && (Filter->Base.Flags & 0x1000000) != 0 )
    {
      RundownLog = Filter->Base.RundownLog;
      if ( RundownLog )
      {
        v28 = (unsigned __int64)(((unsigned __int16)_InterlockedExchangeAdd(&RundownLog->Index, 1u) + 1) & 0x3FF) << 7;
        *(_FLT_OBJECT_LOG_ENTRY_ACTION *)((char *)&Filter->Base.RundownLog->Log[0].Action + v28) = ORT_Reference;
        *(unsigned __int64 *)((char *)&Filter->Base.RundownLog->Log[0].RundownRef + v28) = Filter->Base.RundownRef.Count;
        memset((char *)Filter->Base.RundownLog->Log[0].Stack + v28, 0, 0x70u);
        RtlWalkFrameChain((PVOID *)((char *)Filter->Base.RundownLog->Log[0].Stack + v28), 0xEu, 0);
      }
    }
    v15 = 0;
  }
  else
  {
    if ( (FltGlobals[0] & 0x2000) != 0 && (Filter->Base.Flags & 0x2000000) != 0
      || (FltGlobals[0] & 0x4000) != 0 && (Filter->Base.Flags & 0x4000000) != 0
      || (FltGlobals[0] & 0x8000) != 0 && (Filter->Base.Flags & 0x1000000) != 0 )
    {
      v25 = Filter->Base.RundownLog;
      if ( v25 )
      {
        v26 = (unsigned __int64)(((unsigned __int16)_InterlockedExchangeAdd(&v25->Index, 1u) + 1) & 0x3FF) << 7;
        *(_FLT_OBJECT_LOG_ENTRY_ACTION *)((char *)&Filter->Base.RundownLog->Log[0].Action + v26) = ORT_FailedRef;
        *(unsigned __int64 *)((char *)&Filter->Base.RundownLog->Log[0].RundownRef + v26) = Filter->Base.RundownRef.Count;
        memset((char *)Filter->Base.RundownLog->Log[0].Stack + v26, 0, 0x70u);
        RtlWalkFrameChain((PVOID *)((char *)Filter->Base.RundownLog->Log[0].Stack + v26), 0xEu, 0);
      }
    }
    v15 = -1071906805;
  }
  if ( (int)FltpDbgStatus(v15, "minkernel\\fs\\filtermgr\\filter\\contextsup.c", 1577, 3223060491LL) < 0 )
  {
    DoFreeContextMemory(v13);
    result = v15;
    *ReturnedContext = 0;
  }
  else
  {
    *ReturnedContext = v13 + 12;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000b890  push    rsi
0x18000b892  push    r12
0x18000b894  push    r15
0x18000b896  sub     rsp, 30h
0x18000b89a  movzx   esi, dx
0x18000b89d  mov     r12d, r9d
0x18000b8a0  mov     r15, rcx
0x18000b8a3  cmp     r8, 0FFFFh
0x18000b8aa  ja      loc_18000BC5E
0x18000b8b0  mov     [rsp+48h+arg_0], rbx
0x18000b8b5  mov     [rsp+48h+arg_10], r13
0x18000b8ba  mov     r13d, 1
0x18000b8c0  cmp     esi, 4
0x18000b8c3  jnz     short loc_18000B8CC
0x18000b8c5  mov     ebx, 2
0x18000b8ca  jmp     short loc_18000B906
0x18000b8cc  lea     eax, [rsi-1]; switch 64 cases
0x18000b8cf  cmp     eax, 3Fh
0x18000b8d2  ja      def_18000B8F1; jumptable 000000018000B8F1 default case, cases 3-7,9-15,17-31,33-63
0x18000b8d8  lea     rdx, cs:180000000h
0x18000b8df  movzx   eax, ds:(byte_180031888 - 180000000h)[rdx+rax]
0x18000b8e7  mov     ecx, ds:(jpt_18000B8F1 - 180000000h)[rdx+rax*4]
0x18000b8ee  add     rcx, rdx
0x18000b8f1  jmp     rcx; switch jump
0x18000b8f7  mov     ebx, 4; jumptable 000000018000B8F1 case 16
0x18000b8fc  test    sil, 7Fh
0x18000b900  jz      def_18000B8F1; jumptable 000000018000B8F1 default case, cases 3-7,9-15,17-31,33-63
0x18000b906  mov     [rsp+48h+arg_18], r14
0x18000b90b  lfence
0x18000b90e  mov     rbx, [r15+rbx*8+138h]
0x18000b916  lea     r14, [r8+60h]
0x18000b91a  mov     [rsp+48h+arg_8], rdi
0x18000b91f  test    rbx, rbx
0x18000b922  jz      loc_18000BBD8
0x18000b928  movzx   ecx, byte ptr [rbx+1Bh]
0x18000b92c  cmp     ecx, r13d
0x18000b92f  jnz     loc_18000BA5D
0x18000b935  mov     ecx, [rbx+6Ch]
0x18000b938  cmp     r14, rcx
0x18000b93b  jnz     loc_18000BBC0
0x18000b941  cmp     r12d, 200h
0x18000b948  jz      loc_18000BA9E
0x18000b94e  cmp     r12d, r13d
0x18000b951  jnz     loc_18000BB65
0x18000b957  lea     rcx, [rbx+0C0h]; Lookaside
0x18000b95e  call    cs:__imp_ExAllocateFromPagedLookasideList
0x18000b965  nop     dword ptr [rax+rax+00h]
0x18000b96a  mov     rdi, rax
0x18000b96d  test    rdi, rdi
0x18000b970  jz      loc_18000BB0E
0x18000b976  xor     edx, edx; Val
0x18000b978  mov     r8d, 60h ; '`'; Size
0x18000b97e  mov     rcx, rdi; void *
0x18000b981  call    memset
0x18000b986  mov     [rdi+50h], r13d
0x18000b98a  mov     [rdi+8], rbx
0x18000b98e  cmp     esi, 20h ; ' '
0x18000b991  jz      loc_18000BAC0
0x18000b997  cmp     esi, 40h ; '@'
0x18000b99a  jz      loc_18000BBF8
0x18000b9a0  xor     r14d, r14d
0x18000b9a3  cmp     r12d, r13d
0x18000b9a6  jnz     short loc_18000B9AC
0x18000b9a8  or      [rdi+48h], r13d
0x18000b9ac  movzx   eax, byte ptr [rbx+1Bh]
0x18000b9b0  cmp     al, 2
0x18000b9b2  jz      loc_18000BB2D
0x18000b9b8  cmp     r12d, r13d
0x18000b9bb  jz      short loc_18000B9CA
0x18000b9bd  cmp     r12d, 200h
0x18000b9c4  jnz     loc_18000BB24
0x18000b9ca  lea     rcx, [r15+8]; RunRef
0x18000b9ce  call    cs:__imp_ExAcquireRundownProtection
0x18000b9d5  nop     dword ptr [rax+rax+00h]
0x18000b9da  mov     ecx, cs:FltGlobals
0x18000b9e0  test    al, al
0x18000b9e2  jz      loc_18000BC6E
0x18000b9e8  bt      ecx, 0Dh
0x18000b9ec  jb      loc_18000BDD4
0x18000b9f2  bt      ecx, 0Eh
0x18000b9f6  jb      loc_18000BE53
0x18000b9fc  bt      ecx, 0Fh
0x18000ba00  jb      loc_18000BE65
0x18000ba06  mov     ebx, r14d
0x18000ba09  mov     r8d, 629h
0x18000ba0f  mov     [rsp+48h+var_28], r14
0x18000ba14  mov     r9d, 0C01C000Bh
0x18000ba1a  lea     rdx, aMinkernelFsFil_9; "minkernel\\fs\\filtermgr\\filter\\conte"...
0x18000ba21  mov     ecx, ebx
0x18000ba23  call    FltpDbgStatus
0x18000ba28  test    eax, eax
0x18000ba2a  js      loc_18000BE9A
0x18000ba30  mov     rax, [rsp+48h+ReturnedContext]
0x18000ba35  lea     rcx, [rdi+60h]
0x18000ba39  mov     [rax], rcx
0x18000ba3c  xor     eax, eax
0x18000ba3e  mov     rdi, [rsp+48h+arg_8]
0x18000ba43  mov     r14, [rsp+48h+arg_18]
0x18000ba48  mov     rbx, [rsp+48h+arg_0]
0x18000ba4d  mov     r13, [rsp+48h+arg_10]
0x18000ba52  add     rsp, 30h
0x18000ba56  pop     r15
0x18000ba58  pop     r12
0x18000ba5a  pop     rsi
0x18000ba5b  retn
0x18000ba5d  sub     ecx, 2
0x18000ba60  jnz     loc_18000BB36
0x18000ba66  mov     r8d, [rbx+20h]; Tag
0x18000ba6a  mov     ecx, r12d
0x18000ba6d  bts     ecx, 0Ah; PoolType
0x18000ba71  mov     rdx, r14; NumberOfBytes
0x18000ba74  call    cs:__imp_ExAllocatePoolWithTag
0x18000ba7b  nop     dword ptr [rax+rax+00h]
0x18000ba80  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18000ba87  mov     rdi, rax
0x18000ba8a  jnz     loc_18000B96D
0x18000ba90  test    rax, rax
0x18000ba93  jz      loc_18000B96D
0x18000ba99  jmp     loc_1800258B2
0x18000ba9e  lea     rcx, [rbx+40h]; Lookaside
0x18000baa2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x18000baa9  nop     dword ptr [rax+rax+00h]
0x18000baae  mov     rdi, rax
0x18000bab1  jmp     loc_18000B96D
0x18000bab6  mov     ebx, 3; jumptable 000000018000B8F1 case 8
0x18000babb  jmp     loc_18000B8FC
0x18000bac0  lea     rcx, stru_18003F040; Lookaside
0x18000bac7  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x18000bace  nop     dword ptr [rax+rax+00h]
0x18000bad3  mov     [rdi], rax
0x18000bad6  test    rax, rax
0x18000bad9  jnz     loc_18000BCDD
0x18000badf  mov     rdx, [rdi+8]
0x18000bae3  movzx   ecx, byte ptr [rdx+1Bh]
0x18000bae7  cmp     ecx, r13d
0x18000baea  jnz     loc_18000BBA0
0x18000baf0  mov     eax, [rdi+48h]
0x18000baf3  test    r13b, al
0x18000baf6  jz      short loc_18000BB48
0x18000baf8  lea     rcx, [rdx+0C0h]; Lookaside
0x18000baff  mov     rdx, rdi; Entry
0x18000bb02  call    cs:__imp_ExFreeToPagedLookasideList
0x18000bb09  nop     dword ptr [rax+rax+00h]
0x18000bb0e  mov     rax, [rsp+48h+ReturnedContext]
0x18000bb13  mov     qword ptr [rax], 0
0x18000bb1a  mov     eax, 0C000009Ah
0x18000bb1f  jmp     loc_18000BA3E
0x18000bb24  cmp     al, r13b
0x18000bb27  jnz     loc_18000B9CA
0x18000bb2d  or      dword ptr [rdi+48h], 8
0x18000bb31  jmp     loc_18000B9CA
0x18000bb36  cmp     ecx, r13d
0x18000bb39  jz      loc_18000BD17
0x18000bb3f  mov     rbx, [rbx+10h]
0x18000bb43  jmp     loc_18000B91F
0x18000bb48  test    al, 8
0x18000bb4a  jnz     loc_18000BCB4
0x18000bb50  lea     rcx, [rdx+40h]; Lookaside
0x18000bb54  mov     rdx, rdi; Entry
0x18000bb57  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000bb5e  nop     dword ptr [rax+rax+00h]
0x18000bb63  jmp     short loc_18000BB0E
0x18000bb65  mov     r8d, [rbx+0E8h]; Tag
0x18000bb6c  mov     ecx, r12d
0x18000bb6f  bts     ecx, 0Ah; PoolType
0x18000bb73  mov     rdx, r14; NumberOfBytes
0x18000bb76  call    cs:__imp_ExAllocatePoolWithTag
0x18000bb7d  nop     dword ptr [rax+rax+00h]
0x18000bb82  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18000bb89  mov     rdi, rax
0x18000bb8c  jnz     loc_18000B96D
0x18000bb92  test    rax, rax
0x18000bb95  jz      loc_18000B96D
0x18000bb9b  jmp     loc_1800258B2
0x18000bba0  sub     ecx, 2
0x18000bba3  jnz     loc_18000BC96
0x18000bba9  mov     edx, [rdx+20h]; Tag
0x18000bbac  mov     rcx, rdi; P
0x18000bbaf  call    cs:__imp_ExFreePoolWithTag
0x18000bbb6  nop     dword ptr [rax+rax+00h]
0x18000bbbb  jmp     loc_18000BB0E
0x18000bbc0  test    byte ptr [rbx+1Ah], 2
0x18000bbc4  jz      loc_18000BB3F
0x18000bbca  cmp     r14, rcx
0x18000bbcd  jb      loc_18000B941
0x18000bbd3  jmp     loc_18000BB3F
0x18000bbd8  mov     rax, [rsp+48h+ReturnedContext]
0x18000bbdd  mov     qword ptr [rax], 0
0x18000bbe4  mov     eax, 0C01C0016h
0x18000bbe9  jmp     loc_18000BA3E
0x18000bbee  mov     ebx, 6; jumptable 000000018000B8F1 case 64
0x18000bbf3  jmp     loc_18000B8FC
0x18000bbf8  lea     rcx, stru_18003F240; Lookaside
0x18000bbff  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x18000bc06  nop     dword ptr [rax+rax+00h]
0x18000bc0b  mov     [rdi], rax
0x18000bc0e  test    rax, rax
0x18000bc11  jz      loc_18000BE8D
0x18000bc17  xor     r14d, r14d
0x18000bc1a  xor     r8d, r8d; State
0x18000bc1d  mov     [rax+48h], r14
0x18000bc21  xor     edx, edx; Type
0x18000bc23  mov     [rax+50h], r14
0x18000bc27  mov     [rax+38h], r14
0x18000bc2b  mov     rax, [rdi]
0x18000bc2e  mov     [rax+30h], r14d
0x18000bc32  mov     rax, [rdi]
0x18000bc35  mov     [rax], r14
0x18000bc38  mov     rax, [rdi]
0x18000bc3b  mov     [rax+8], r14
0x18000bc3f  mov     rax, [rdi]
0x18000bc42  mov     [rax+10h], r14d
0x18000bc46  mov     rcx, [rdi]
0x18000bc49  add     rcx, 18h; Event
0x18000bc4d  call    cs:__imp_KeInitializeEvent
0x18000bc54  nop     dword ptr [rax+rax+00h]
0x18000bc59  jmp     loc_18000B9A3
0x18000bc5e  mov     eax, 0C0000206h
0x18000bc63  add     rsp, 30h
0x18000bc67  pop     r15
0x18000bc69  pop     r12
0x18000bc6b  pop     rsi
0x18000bc6c  retn
0x18000bc6e  bt      ecx, 0Dh
0x18000bc72  jb      loc_18000BD32
0x18000bc78  bt      ecx, 0Eh
0x18000bc7c  jb      loc_18000BDB4
0x18000bc82  bt      ecx, 0Fh
0x18000bc86  jb      loc_18000BDC2
0x18000bc8c  mov     ebx, 0C01C000Bh
0x18000bc91  jmp     loc_18000BA09
0x18000bc96  cmp     ecx, r13d
0x18000bc99  jnz     loc_18000BB0E
0x18000bc9f  mov     rax, [rdx+28h]
0x18000bca3  mov     rcx, rdi
0x18000bca6  movzx   edx, word ptr [rdx+18h]
0x18000bcaa  call    _guard_dispatch_icall
0x18000bcaf  jmp     loc_18000BB0E
0x18000bcb4  mov     edx, [rdx+0E8h]; Tag
0x18000bcba  mov     rcx, rdi; P
0x18000bcbd  call    cs:__imp_ExFreePoolWithTag
0x18000bcc4  nop     dword ptr [rax+rax+00h]
0x18000bcc9  jmp     loc_18000BB0E
0x18000bcce  xor     ebx, ebx; jumptable 000000018000B8F1 case 1
0x18000bcd0  jmp     loc_18000B8FC
0x18000bcd5  mov     rbx, r13; jumptable 000000018000B8F1 case 2
0x18000bcd8  jmp     loc_18000B8FC
0x18000bcdd  xor     edx, edx; Val
0x18000bcdf  mov     r8d, 48h ; 'H'; Size
0x18000bce5  mov     rcx, rax; void *
0x18000bce8  call    memset
0x18000bced  mov     rax, [rdi]
0x18000bcf0  xor     r14d, r14d
0x18000bcf3  mov     [rax], r14
0x18000bcf6  mov     rax, [rdi]
0x18000bcf9  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x18000bd01  mov     rax, [rdi]
0x18000bd04  mov     [rax+40h], r14
0x18000bd08  jmp     loc_18000B9A3
0x18000bd0d  mov     ebx, 5; jumptable 000000018000B8F1 case 32
0x18000bd12  jmp     loc_18000B8FC
0x18000bd17  mov     rax, [rbx+20h]
0x18000bd1b  movzx   r8d, si
0x18000bd1f  mov     rdx, r14
0x18000bd22  mov     ecx, r12d
0x18000bd25  call    _guard_dispatch_icall
0x18000bd2a  mov     rdi, rax
0x18000bd2d  jmp     loc_18000B96D
0x18000bd32  test    dword ptr [r15], 2000000h
0x18000bd39  jz      loc_18000BC78
0x18000bd3f  mov     rax, [r15+20h]
0x18000bd43  test    rax, rax
0x18000bd46  jz      loc_18000BC8C
0x18000bd4c  lock xadd [rax], r13d
0x18000bd51  mov     rax, [r15+20h]
0x18000bd55  lea     ebx, [r13+1]
0x18000bd59  and     ebx, 3FFh
0x18000bd5f  xor     edx, edx; Val
0x18000bd61  shl     rbx, 7
0x18000bd65  mov     r8d, 70h ; 'p'; Size
0x18000bd6b  mov     dword ptr [rbx+rax+8], 5
0x18000bd73  mov     rcx, [r15+20h]
0x18000bd77  mov     rax, [r15+8]
0x18000bd7b  mov     [rbx+rcx+10h], rax
0x18000bd80  mov     rcx, [r15+20h]
0x18000bd84  add     rcx, 18h
0x18000bd88  add     rcx, rbx; void *
0x18000bd8b  call    memset
0x18000bd90  mov     rcx, [r15+20h]
0x18000bd94  xor     r8d, r8d; Flags
0x18000bd97  add     rcx, 18h
0x18000bd9b  mov     edx, 0Eh; Count
0x18000bda0  add     rcx, rbx; Callers
0x18000bda3  call    cs:__imp_RtlWalkFrameChain
0x18000bdaa  nop     dword ptr [rax+rax+00h]
0x18000bdaf  jmp     loc_18000BC8C
0x18000bdb4  test    dword ptr [r15], 4000000h
0x18000bdbb  jnz     short loc_18000BD3F
0x18000bdbd  jmp     loc_18000BC82
0x18000bdc2  test    dword ptr [r15], 1000000h
  ... truncated ...
```
