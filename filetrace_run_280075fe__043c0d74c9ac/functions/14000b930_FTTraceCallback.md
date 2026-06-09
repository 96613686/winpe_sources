# FTTraceCallback

- ea: `0x14000b930`
- end: `0x14000bcdd`
- name: `FTTraceCallback`
- size: `941`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003900`
- `0x14000b930`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000bbea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bbea`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000bb86`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000bb86`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b9f5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b9f5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000ba57`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000ba57`
- `ntoskrnl!WmiQueryTraceInformation` at `0x14000bb33`
- `ntoskrnl!WmiQueryTraceInformation` at `0x14000bb33`
- `ntoskrnl!DbgPrintEx` at `0x14000b9b2`
- `ntoskrnl!DbgPrintEx` at `0x14000b9df`
- `ntoskrnl!DbgPrintEx` at `0x14000ba43`
- `ntoskrnl!DbgPrintEx` at `0x14000baae`
- `ntoskrnl!DbgPrintEx` at `0x14000baff`
- `ntoskrnl!DbgPrintEx` at `0x14000b9b2`
- `ntoskrnl!DbgPrintEx` at `0x14000b9df`
- `ntoskrnl!DbgPrintEx` at `0x14000ba43`
- `ntoskrnl!DbgPrintEx` at `0x14000baae`
- `ntoskrnl!DbgPrintEx` at `0x14000baff`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000bb9d`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000bbf9`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000bb9d`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000bbf9`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000bbd3`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000bbd3`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14000bb52`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14000bb52`

## pseudocode

```c
__int64 __fastcall FTTraceCallback(unsigned __int8 a1, __int64 a2, unsigned int a3, _DWORD *a4, __int64 a5, _DWORD *a6)
{
  _DWORD *v6; // r14
  __int64 v9; // r14
  int v10; // ebp
  int v11; // edi
  NTSTATUS v12; // ebx
  int v13; // ebx
  __int64 v14; // rcx
  _QWORD *v15; // r9
  __int64 v16; // r15
  __int64 v17; // r12
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // rsi
  _DWORD *PoolWithTag; // r14
  bool v20; // zf
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int128 v25; // xmm0
  ULONG RequiredLength; // [rsp+60h] [rbp+8h] BYREF

  v6 = a6;
  *a6 = 0;
  if ( a1 <= 5u )
  {
    if ( a1 != 5 )
    {
      if ( a1 && a1 == 4 )
      {
        RequiredLength = 0;
        DbgPrintEx(0x8Eu, 2u, "IRP_MN_ENABLE_EVENTS: ");
        if ( a3 < 0x30 )
          return (unsigned int)-1073741811;
        v9 = *((_QWORD *)a4 + 1);
        DbgPrintEx(0x8Eu, 2u, "logger = %I64X, ", v9);
        ExAcquireFastMutex(&SessionLock);
        v10 = 0;
        v11 = 1;
        while ( (&WmiRegistrationContext.Queue.ListEntry.Flink)[2 * v10] != (struct _LIST_ENTRY *)*((_QWORD *)a4 + 3)
             || (&WmiRegistrationContext.Queue.ListEntry.Blink)[2 * v10] != (struct _LIST_ENTRY *)*((_QWORD *)a4 + 4) )
        {
          if ( ++v10 >= 4 )
            goto LABEL_10;
        }
        v13 = -1;
        if ( v10 == -1 )
        {
LABEL_10:
          DbgPrintEx(0x8Eu, 2u, "No matching guid\n");
          v12 = -1073741163;
          goto LABEL_11;
        }
        v14 = 0;
        while ( 1 )
        {
          if ( !*((_DWORD *)LogSessions + 10 * v14 + 3) && v13 < 0 )
            v13 = v14;
          if ( *((_WORD *)LogSessions + 20 * v14) == (_WORD)v9 )
            break;
          v14 = (unsigned int)(v14 + 1);
          if ( (int)v14 >= 8 )
            goto LABEL_21;
        }
        v13 = v14;
LABEL_21:
        DbgPrintEx(0x8Eu, 2u, "TargetIndex = %d, ", v13);
        if ( v13 < 0 )
        {
          v12 = -1073741670;
LABEL_11:
          ExReleaseFastMutex(&SessionLock);
          return (unsigned int)v12;
        }
        v15 = LogSessions;
        v16 = 5LL * v13;
        ++*((_DWORD *)LogSessions + 2 * v16 + 2);
        v15[v16] = v9;
        HIDWORD(v15[v16 + 1]) = 0;
        DbgPrintEx(0x8Eu, 2u, "Refcount now %d\n", LODWORD(v15[5 * v13 + 1]));
        v17 = v10 + 10LL * v13;
        v12 = WmiQueryTraceInformation(
                TraceEnableFlagsClass,
                (char *)LogSessions + 4 * v17 + 20,
                4u,
                &RequiredLength,
                a4);
        if ( v12 >= 0 && v10 == 3 )
        {
          GenericWorkItem = FltAllocateGenericWorkItem();
          if ( !GenericWorkItem )
          {
LABEL_26:
            v12 = -1073741670;
            goto LABEL_11;
          }
          PoolWithTag = ExAllocatePoolWithTag(PagedPool, 4u, 0x72744C46u);
          if ( !PoolWithTag )
          {
            FltFreeGenericWorkItem(GenericWorkItem);
            goto LABEL_26;
          }
          *PoolWithTag = *((_DWORD *)LogSessions + v17 + 5);
          v12 = FltQueueGenericWorkItem(
                  GenericWorkItem,
                  WmiRegistrationContext.SecurityDescriptor,
                  (PFLT_GENERIC_WORKITEM_ROUTINE)AttachToRequestedDrives,
                  DelayedWorkQueue,
                  PoolWithTag);
          if ( v12 < 0 )
          {
            ExFreePoolWithTag(PoolWithTag, 0x72744C46u);
            FltFreeGenericWorkItem(GenericWorkItem);
          }
        }
        v20 = SessionSerialNumber == -1;
        v21 = ++SessionSerialNumber;
        if ( v20 )
          SessionSerialNumber = 1;
        else
          v11 = v21;
        *((_DWORD *)LogSessions + 2 * v16 + 3) = v11;
        goto LABEL_11;
      }
      return (unsigned int)-1073741808;
    }
    return 0;
  }
  if ( a1 == 6 || a1 == 7 )
    return 0;
  if ( a1 != 8 )
    return (unsigned int)-1073741808;
  if ( a3 >= 0x98 )
  {
    memset(a4, 0, a3);
    v22 = 0;
    *a4 = 152;
    a4[2] = 0;
    a4[4] = 4;
    do
    {
      v23 = 8 * v22;
      v24 = 2 * v22++;
      v25 = *(__int128 *)((char *)&WmiRegistrationContext.Queue.ListEntry + 8 * v24);
      a4[v23 + 10] = 528384;
      *(_OWORD *)&a4[v23 + 6] = v25;
    }
    while ( v22 != 4 );
    *v6 = 152;
    return 0;
  }
  v12 = -1073741789;
  if ( a3 >= 4 )
  {
    *a4 = 152;
    *v6 = 4;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000b930  mov     [rsp+arg_8], rbx
0x14000b935  mov     [rsp+arg_10], rbp
0x14000b93a  push    rsi
0x14000b93b  push    rdi
0x14000b93c  push    r12
0x14000b93e  push    r14
0x14000b940  push    r15
0x14000b942  sub     rsp, 30h
0x14000b946  mov     r14, [rsp+58h+arg_28]
0x14000b94e  mov     rsi, r9
0x14000b951  movzx   edx, cl
0x14000b954  mov     edi, r8d
0x14000b957  mov     dword ptr [r14], 0
0x14000b95e  cmp     edx, 5
0x14000b961  ja      loc_14000BC37
0x14000b967  jz      loc_14000BCAB
0x14000b96d  test    cl, cl
0x14000b96f  jz      loc_14000BC46
0x14000b975  sub     edx, 1
0x14000b978  jz      loc_14000BC46
0x14000b97e  sub     edx, 1
0x14000b981  jz      loc_14000BC46
0x14000b987  sub     edx, 1
0x14000b98a  jz      loc_14000BC46
0x14000b990  cmp     edx, 1
0x14000b993  jnz     loc_14000BC46
0x14000b999  lea     r8, aIrpMnEnableEve; "IRP_MN_ENABLE_EVENTS: "
0x14000b9a0  mov     [rsp+58h+RequiredLength], 0
0x14000b9a8  mov     edx, 2; Level
0x14000b9ad  mov     ecx, 8Eh; ComponentId
0x14000b9b2  call    cs:__imp_DbgPrintEx
0x14000b9b9  nop     dword ptr [rax+rax+00h]
0x14000b9be  cmp     edi, 30h ; '0'
0x14000b9c1  jb      loc_14000BC30
0x14000b9c7  mov     r14, [rsi+8]
0x14000b9cb  lea     r8, aLoggerI64x; "logger = %I64X, "
0x14000b9d2  mov     r9, r14
0x14000b9d5  mov     edx, 2; Level
0x14000b9da  mov     ecx, 8Eh; ComponentId
0x14000b9df  call    cs:__imp_DbgPrintEx
0x14000b9e6  nop     dword ptr [rax+rax+00h]
0x14000b9eb  lea     r15, SessionLock
0x14000b9f2  mov     rcx, r15; FastMutex
0x14000b9f5  call    cs:__imp_ExAcquireFastMutex
0x14000b9fc  nop     dword ptr [rax+rax+00h]
0x14000ba01  xor     ebp, ebp
0x14000ba03  lea     r8, WmiRegistrationContext.Queue
0x14000ba0a  lea     edi, [rbp+1]
0x14000ba0d  movsxd  r12, ebp
0x14000ba10  mov     rcx, r12
0x14000ba13  add     rcx, rcx
0x14000ba16  mov     rax, [r8+rcx*8]
0x14000ba1a  cmp     rax, [rsi+18h]
0x14000ba1e  jnz     short loc_14000BA2B
0x14000ba20  mov     rax, [r8+rcx*8+8]
0x14000ba25  cmp     rax, [rsi+20h]
0x14000ba29  jz      short loc_14000BA68
0x14000ba2b  add     ebp, edi
0x14000ba2d  cmp     ebp, 4
0x14000ba30  jl      short loc_14000BA0D
0x14000ba32  lea     r8, aNoMatchingGuid; "No matching guid\n"
0x14000ba39  mov     edx, 2; Level
0x14000ba3e  mov     ecx, 8Eh; ComponentId
0x14000ba43  call    cs:__imp_DbgPrintEx
0x14000ba4a  nop     dword ptr [rax+rax+00h]
0x14000ba4f  mov     ebx, 0C0000295h
0x14000ba54  mov     rcx, r15; FastMutex
0x14000ba57  call    cs:__imp_ExReleaseFastMutex
0x14000ba5e  nop     dword ptr [rax+rax+00h]
0x14000ba63  jmp     loc_14000BCAD
0x14000ba68  or      ebx, 0FFFFFFFFh
0x14000ba6b  cmp     ebp, ebx
0x14000ba6d  jz      short loc_14000BA32
0x14000ba6f  xor     ecx, ecx
0x14000ba71  mov     rax, cs:LogSessions
0x14000ba78  lea     rdx, [rcx+rcx*4]
0x14000ba7c  cmp     dword ptr [rax+rdx*8+0Ch], 0
0x14000ba81  jnz     short loc_14000BA88
0x14000ba83  test    ebx, ebx
0x14000ba85  cmovs   ebx, ecx
0x14000ba88  cmp     [rax+rdx*8], r14w
0x14000ba8d  jz      short loc_14000BA98
0x14000ba8f  add     ecx, edi
0x14000ba91  cmp     ecx, 8
0x14000ba94  jl      short loc_14000BA71
0x14000ba96  jmp     short loc_14000BA9A
0x14000ba98  mov     ebx, ecx
0x14000ba9a  mov     r9d, ebx
0x14000ba9d  lea     r8, aTargetindexD; "TargetIndex = %d, "
0x14000baa4  mov     edx, 2; Level
0x14000baa9  mov     ecx, 8Eh; ComponentId
0x14000baae  call    cs:__imp_DbgPrintEx
0x14000bab5  nop     dword ptr [rax+rax+00h]
0x14000baba  test    ebx, ebx
0x14000babc  jns     short loc_14000BAC5
0x14000babe  mov     ebx, 0C000009Ah
0x14000bac3  jmp     short loc_14000BA54
0x14000bac5  mov     r9, cs:LogSessions
0x14000bacc  lea     r8, aRefcountNowD; "Refcount now %d\n"
0x14000bad3  movsxd  rbx, ebx
0x14000bad6  mov     ecx, 8Eh; ComponentId
0x14000badb  lea     r15, [rbx+rbx*4]
0x14000badf  add     [r9+r15*8+8], edi
0x14000bae4  mov     [r9+r15*8], r14
0x14000bae8  mov     r14d, 2
0x14000baee  mov     dword ptr [r9+r15*8+0Ch], 0
0x14000baf7  mov     edx, r14d; Level
0x14000bafa  mov     r9d, [r9+r15*8+8]
0x14000baff  call    cs:__imp_DbgPrintEx
0x14000bb06  nop     dword ptr [rax+rax+00h]
0x14000bb0b  mov     rdx, cs:LogSessions
0x14000bb12  lea     rax, [rbx+rbx*4]
0x14000bb16  add     rdx, 14h
0x14000bb1a  mov     [rsp+58h+Buffer], rsi; Buffer
0x14000bb1f  lea     r12, [r12+rax*2]
0x14000bb23  mov     ecx, r14d; TraceInformationClass
0x14000bb26  lea     r9, [rsp+58h+RequiredLength]; RequiredLength
0x14000bb2b  lea     r8d, [r14+2]; TraceInformationLength
0x14000bb2f  lea     rdx, [rdx+r12*4]; TraceInformation
0x14000bb33  call    cs:__imp_WmiQueryTraceInformation
0x14000bb3a  nop     dword ptr [rax+rax+00h]
0x14000bb3f  mov     ebx, eax
0x14000bb41  test    eax, eax
0x14000bb43  js      loc_14000BC05
0x14000bb49  cmp     ebp, 3
0x14000bb4c  jnz     loc_14000BC05
0x14000bb52  call    cs:__imp_FltAllocateGenericWorkItem
0x14000bb59  nop     dword ptr [rax+rax+00h]
0x14000bb5e  mov     rsi, rax
0x14000bb61  test    rax, rax
0x14000bb64  jnz     short loc_14000BB77
0x14000bb66  mov     ebx, 0C000009Ah
0x14000bb6b  lea     rcx, SessionLock
0x14000bb72  jmp     loc_14000BA57
0x14000bb77  mov     ebp, 72744C46h
0x14000bb7c  mov     edx, 4; NumberOfBytes
0x14000bb81  mov     r8d, ebp; Tag
0x14000bb84  mov     ecx, edi; PoolType
0x14000bb86  call    cs:__imp_ExAllocatePoolWithTag
0x14000bb8d  nop     dword ptr [rax+rax+00h]
0x14000bb92  mov     r14, rax
0x14000bb95  test    rax, rax
0x14000bb98  jnz     short loc_14000BBAB
0x14000bb9a  mov     rcx, rsi; FltWorkItem
0x14000bb9d  call    cs:__imp_FltFreeGenericWorkItem
0x14000bba4  nop     dword ptr [rax+rax+00h]
0x14000bba9  jmp     short loc_14000BB66
0x14000bbab  mov     rax, cs:LogSessions
0x14000bbb2  lea     r8, AttachToRequestedDrives; WorkerRoutine
0x14000bbb9  mov     r9d, edi; QueueType
0x14000bbbc  mov     [rsp+58h+Buffer], r14; Context
0x14000bbc1  mov     ecx, [rax+r12*4+14h]
0x14000bbc6  mov     [r14], ecx
0x14000bbc9  mov     rcx, rsi; FltWorkItem
0x14000bbcc  mov     rdx, cs:WmiRegistrationContext.SecurityDescriptor; FltObject
0x14000bbd3  call    cs:__imp_FltQueueGenericWorkItem
0x14000bbda  nop     dword ptr [rax+rax+00h]
0x14000bbdf  mov     ebx, eax
0x14000bbe1  test    eax, eax
0x14000bbe3  jns     short loc_14000BC05
0x14000bbe5  mov     edx, ebp; Tag
0x14000bbe7  mov     rcx, r14; P
0x14000bbea  call    cs:__imp_ExFreePoolWithTag
0x14000bbf1  nop     dword ptr [rax+rax+00h]
0x14000bbf6  mov     rcx, rsi; FltWorkItem
0x14000bbf9  call    cs:__imp_FltFreeGenericWorkItem
0x14000bc00  nop     dword ptr [rax+rax+00h]
0x14000bc05  mov     eax, cs:SessionSerialNumber
0x14000bc0b  add     eax, edi
0x14000bc0d  mov     cs:SessionSerialNumber, eax
0x14000bc13  jnz     short loc_14000BC1D
0x14000bc15  mov     cs:SessionSerialNumber, edi
0x14000bc1b  jmp     short loc_14000BC1F
0x14000bc1d  mov     edi, eax
0x14000bc1f  mov     rax, cs:LogSessions
0x14000bc26  mov     [rax+r15*8+0Ch], edi
0x14000bc2b  jmp     loc_14000BB6B
0x14000bc30  mov     ebx, 0C000000Dh
0x14000bc35  jmp     short loc_14000BCAD
0x14000bc37  sub     edx, 6
0x14000bc3a  jz      short loc_14000BCAB
0x14000bc3c  sub     edx, 1
0x14000bc3f  jz      short loc_14000BCAB
0x14000bc41  sub     edx, 1
0x14000bc44  jz      short loc_14000BC4D
0x14000bc46  mov     ebx, 0C0000010h
0x14000bc4b  jmp     short loc_14000BCAD
0x14000bc4d  mov     ebp, 98h
0x14000bc52  cmp     edi, ebp
0x14000bc54  jb      short loc_14000BCC7
0x14000bc56  mov     r8, rdi; Size
0x14000bc59  xor     edx, edx; Val
0x14000bc5b  mov     rcx, rsi; void *
0x14000bc5e  call    memset
0x14000bc63  xor     edx, edx
0x14000bc65  mov     [rsi], ebp
0x14000bc67  mov     dword ptr [rsi+8], 0
0x14000bc6e  lea     r8, WmiRegistrationContext.Queue
0x14000bc75  mov     dword ptr [rsi+10h], 4
0x14000bc7c  lea     edi, [rdx+1]
0x14000bc7f  mov     rax, rdx
0x14000bc82  mov     rcx, rdx
0x14000bc85  shl     rcx, 5
0x14000bc89  add     rax, rax
0x14000bc8c  add     rdx, rdi
0x14000bc8f  movups  xmm0, xmmword ptr [r8+rax*8]
0x14000bc94  mov     dword ptr [rcx+rsi+28h], 81000h
0x14000bc9c  movdqu  xmmword ptr [rcx+rsi+18h], xmm0
0x14000bca2  cmp     rdx, 4
0x14000bca6  jnz     short loc_14000BC7F
0x14000bca8  mov     [r14], ebp
0x14000bcab  xor     ebx, ebx
0x14000bcad  mov     rbp, [rsp+58h+arg_10]
0x14000bcb2  mov     eax, ebx
0x14000bcb4  mov     rbx, [rsp+58h+arg_8]
0x14000bcb9  add     rsp, 30h
0x14000bcbd  pop     r15
0x14000bcbf  pop     r14
0x14000bcc1  pop     r12
0x14000bcc3  pop     rdi
0x14000bcc4  pop     rsi
0x14000bcc5  retn
0x14000bcc7  mov     ebx, 0C0000023h
0x14000bccc  cmp     edi, 4
0x14000bccf  jb      short loc_14000BCAD
0x14000bcd1  mov     [r9], ebp
0x14000bcd4  mov     dword ptr [r14], 4
0x14000bcdb  jmp     short loc_14000BCAD
```
