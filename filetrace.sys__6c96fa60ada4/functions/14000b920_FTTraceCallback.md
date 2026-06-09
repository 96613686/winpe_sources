# FTTraceCallback

- ea: `0x14000b920`
- end: `0x14000bcd0`
- name: `FTTraceCallback`
- size: `944`
- prototype: `__int64 __fastcall(unsigned __int8, __int64, unsigned int, _DWORD *, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003900`
- `0x14000b920`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000bbdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bbdd`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b9e5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b9e5`
- `ntoskrnl!ExAllocatePool2` at `0x14000bb79`
- `ntoskrnl!ExAllocatePool2` at `0x14000bb79`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000ba47`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000ba47`
- `ntoskrnl!WmiQueryTraceInformation` at `0x14000bb23`
- `ntoskrnl!WmiQueryTraceInformation` at `0x14000bb23`
- `ntoskrnl!DbgPrintEx` at `0x14000b9a2`
- `ntoskrnl!DbgPrintEx` at `0x14000b9cf`
- `ntoskrnl!DbgPrintEx` at `0x14000ba33`
- `ntoskrnl!DbgPrintEx` at `0x14000ba9e`
- `ntoskrnl!DbgPrintEx` at `0x14000baef`
- `ntoskrnl!DbgPrintEx` at `0x14000b9a2`
- `ntoskrnl!DbgPrintEx` at `0x14000b9cf`
- `ntoskrnl!DbgPrintEx` at `0x14000ba33`
- `ntoskrnl!DbgPrintEx` at `0x14000ba9e`
- `ntoskrnl!DbgPrintEx` at `0x14000baef`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000bb90`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000bbec`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000bb90`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000bbec`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000bbc6`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000bbc6`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14000bb42`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14000bb42`

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
  _DWORD *Pool2; // r14
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
          Pool2 = (_DWORD *)ExAllocatePool2(258, 4, 1920224326);
          if ( !Pool2 )
          {
            FltFreeGenericWorkItem(GenericWorkItem);
            goto LABEL_26;
          }
          *Pool2 = *((_DWORD *)LogSessions + v17 + 5);
          v12 = FltQueueGenericWorkItem(
                  GenericWorkItem,
                  WmiRegistrationContext.SecurityDescriptor,
                  AttachToRequestedDrives,
                  DelayedWorkQueue,
                  Pool2);
          if ( v12 < 0 )
          {
            ExFreePoolWithTag(Pool2, 0x72744C46u);
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
0x14000b920  mov     [rsp+arg_8], rbx
0x14000b925  mov     [rsp+arg_10], rbp
0x14000b92a  push    rsi
0x14000b92b  push    rdi
0x14000b92c  push    r12
0x14000b92e  push    r14
0x14000b930  push    r15
0x14000b932  sub     rsp, 30h
0x14000b936  mov     r14, [rsp+58h+arg_28]
0x14000b93e  mov     rsi, r9
0x14000b941  movzx   edx, cl
0x14000b944  mov     edi, r8d
0x14000b947  mov     dword ptr [r14], 0
0x14000b94e  cmp     edx, 5
0x14000b951  ja      loc_14000BC2A
0x14000b957  jz      loc_14000BC9E
0x14000b95d  test    cl, cl
0x14000b95f  jz      loc_14000BC39
0x14000b965  sub     edx, 1
0x14000b968  jz      loc_14000BC39
0x14000b96e  sub     edx, 1
0x14000b971  jz      loc_14000BC39
0x14000b977  sub     edx, 1
0x14000b97a  jz      loc_14000BC39
0x14000b980  cmp     edx, 1
0x14000b983  jnz     loc_14000BC39
0x14000b989  lea     r8, aIrpMnEnableEve; "IRP_MN_ENABLE_EVENTS: "
0x14000b990  mov     [rsp+58h+RequiredLength], 0
0x14000b998  mov     edx, 2; Level
0x14000b99d  mov     ecx, 8Eh; ComponentId
0x14000b9a2  call    cs:__imp_DbgPrintEx
0x14000b9a9  nop     dword ptr [rax+rax+00h]
0x14000b9ae  cmp     edi, 30h ; '0'
0x14000b9b1  jb      loc_14000BC23
0x14000b9b7  mov     r14, [rsi+8]
0x14000b9bb  lea     r8, aLoggerI64x; "logger = %I64X, "
0x14000b9c2  mov     r9, r14
0x14000b9c5  mov     edx, 2; Level
0x14000b9ca  mov     ecx, 8Eh; ComponentId
0x14000b9cf  call    cs:__imp_DbgPrintEx
0x14000b9d6  nop     dword ptr [rax+rax+00h]
0x14000b9db  lea     r15, SessionLock
0x14000b9e2  mov     rcx, r15; FastMutex
0x14000b9e5  call    cs:__imp_ExAcquireFastMutex
0x14000b9ec  nop     dword ptr [rax+rax+00h]
0x14000b9f1  xor     ebp, ebp
0x14000b9f3  lea     r8, WmiRegistrationContext.Queue
0x14000b9fa  lea     edi, [rbp+1]
0x14000b9fd  movsxd  r12, ebp
0x14000ba00  mov     rcx, r12
0x14000ba03  add     rcx, rcx
0x14000ba06  mov     rax, [r8+rcx*8]
0x14000ba0a  cmp     rax, [rsi+18h]
0x14000ba0e  jnz     short loc_14000BA1B
0x14000ba10  mov     rax, [r8+rcx*8+8]
0x14000ba15  cmp     rax, [rsi+20h]
0x14000ba19  jz      short loc_14000BA58
0x14000ba1b  add     ebp, edi
0x14000ba1d  cmp     ebp, 4
0x14000ba20  jl      short loc_14000B9FD
0x14000ba22  lea     r8, aNoMatchingGuid; "No matching guid\n"
0x14000ba29  mov     edx, 2; Level
0x14000ba2e  mov     ecx, 8Eh; ComponentId
0x14000ba33  call    cs:__imp_DbgPrintEx
0x14000ba3a  nop     dword ptr [rax+rax+00h]
0x14000ba3f  mov     ebx, 0C0000295h
0x14000ba44  mov     rcx, r15; FastMutex
0x14000ba47  call    cs:__imp_ExReleaseFastMutex
0x14000ba4e  nop     dword ptr [rax+rax+00h]
0x14000ba53  jmp     loc_14000BCA0
0x14000ba58  or      ebx, 0FFFFFFFFh
0x14000ba5b  cmp     ebp, ebx
0x14000ba5d  jz      short loc_14000BA22
0x14000ba5f  xor     ecx, ecx
0x14000ba61  mov     rax, cs:LogSessions
0x14000ba68  lea     rdx, [rcx+rcx*4]
0x14000ba6c  cmp     dword ptr [rax+rdx*8+0Ch], 0
0x14000ba71  jnz     short loc_14000BA78
0x14000ba73  test    ebx, ebx
0x14000ba75  cmovs   ebx, ecx
0x14000ba78  cmp     [rax+rdx*8], r14w
0x14000ba7d  jz      short loc_14000BA88
0x14000ba7f  add     ecx, edi
0x14000ba81  cmp     ecx, 8
0x14000ba84  jl      short loc_14000BA61
0x14000ba86  jmp     short loc_14000BA8A
0x14000ba88  mov     ebx, ecx
0x14000ba8a  mov     r9d, ebx
0x14000ba8d  lea     r8, aTargetindexD; "TargetIndex = %d, "
0x14000ba94  mov     edx, 2; Level
0x14000ba99  mov     ecx, 8Eh; ComponentId
0x14000ba9e  call    cs:__imp_DbgPrintEx
0x14000baa5  nop     dword ptr [rax+rax+00h]
0x14000baaa  test    ebx, ebx
0x14000baac  jns     short loc_14000BAB5
0x14000baae  mov     ebx, 0C000009Ah
0x14000bab3  jmp     short loc_14000BA44
0x14000bab5  mov     r9, cs:LogSessions
0x14000babc  lea     r8, aRefcountNowD; "Refcount now %d\n"
0x14000bac3  movsxd  rbx, ebx
0x14000bac6  mov     ecx, 8Eh; ComponentId
0x14000bacb  lea     r15, [rbx+rbx*4]
0x14000bacf  add     [r9+r15*8+8], edi
0x14000bad4  mov     [r9+r15*8], r14
0x14000bad8  mov     r14d, 2
0x14000bade  mov     dword ptr [r9+r15*8+0Ch], 0
0x14000bae7  mov     edx, r14d; Level
0x14000baea  mov     r9d, [r9+r15*8+8]
0x14000baef  call    cs:__imp_DbgPrintEx
0x14000baf6  nop     dword ptr [rax+rax+00h]
0x14000bafb  mov     rdx, cs:LogSessions
0x14000bb02  lea     rax, [rbx+rbx*4]
0x14000bb06  add     rdx, 14h
0x14000bb0a  mov     [rsp+58h+Buffer], rsi; Buffer
0x14000bb0f  lea     r12, [r12+rax*2]
0x14000bb13  mov     ecx, r14d; TraceInformationClass
0x14000bb16  lea     r9, [rsp+58h+RequiredLength]; RequiredLength
0x14000bb1b  lea     r8d, [r14+2]; TraceInformationLength
0x14000bb1f  lea     rdx, [rdx+r12*4]; TraceInformation
0x14000bb23  call    cs:__imp_WmiQueryTraceInformation
0x14000bb2a  nop     dword ptr [rax+rax+00h]
0x14000bb2f  mov     ebx, eax
0x14000bb31  test    eax, eax
0x14000bb33  js      loc_14000BBF8
0x14000bb39  cmp     ebp, 3
0x14000bb3c  jnz     loc_14000BBF8
0x14000bb42  call    cs:__imp_FltAllocateGenericWorkItem
0x14000bb49  nop     dword ptr [rax+rax+00h]
0x14000bb4e  mov     rsi, rax
0x14000bb51  test    rax, rax
0x14000bb54  jnz     short loc_14000BB67
0x14000bb56  mov     ebx, 0C000009Ah
0x14000bb5b  lea     rcx, SessionLock
0x14000bb62  jmp     loc_14000BA47
0x14000bb67  mov     ebp, 72744C46h
0x14000bb6c  mov     edx, 4
0x14000bb71  mov     r8d, ebp
0x14000bb74  mov     ecx, 102h
0x14000bb79  call    cs:__imp_ExAllocatePool2
0x14000bb80  nop     dword ptr [rax+rax+00h]
0x14000bb85  mov     r14, rax
0x14000bb88  test    rax, rax
0x14000bb8b  jnz     short loc_14000BB9E
0x14000bb8d  mov     rcx, rsi; FltWorkItem
0x14000bb90  call    cs:__imp_FltFreeGenericWorkItem
0x14000bb97  nop     dword ptr [rax+rax+00h]
0x14000bb9c  jmp     short loc_14000BB56
0x14000bb9e  mov     rax, cs:LogSessions
0x14000bba5  lea     r8, AttachToRequestedDrives; WorkerRoutine
0x14000bbac  mov     r9d, edi; QueueType
0x14000bbaf  mov     [rsp+58h+Buffer], r14; Context
0x14000bbb4  mov     ecx, [rax+r12*4+14h]
0x14000bbb9  mov     [r14], ecx
0x14000bbbc  mov     rcx, rsi; FltWorkItem
0x14000bbbf  mov     rdx, cs:WmiRegistrationContext.SecurityDescriptor; FltObject
0x14000bbc6  call    cs:__imp_FltQueueGenericWorkItem
0x14000bbcd  nop     dword ptr [rax+rax+00h]
0x14000bbd2  mov     ebx, eax
0x14000bbd4  test    eax, eax
0x14000bbd6  jns     short loc_14000BBF8
0x14000bbd8  mov     edx, ebp; Tag
0x14000bbda  mov     rcx, r14; P
0x14000bbdd  call    cs:__imp_ExFreePoolWithTag
0x14000bbe4  nop     dword ptr [rax+rax+00h]
0x14000bbe9  mov     rcx, rsi; FltWorkItem
0x14000bbec  call    cs:__imp_FltFreeGenericWorkItem
0x14000bbf3  nop     dword ptr [rax+rax+00h]
0x14000bbf8  mov     eax, cs:SessionSerialNumber
0x14000bbfe  add     eax, edi
0x14000bc00  mov     cs:SessionSerialNumber, eax
0x14000bc06  jnz     short loc_14000BC10
0x14000bc08  mov     cs:SessionSerialNumber, edi
0x14000bc0e  jmp     short loc_14000BC12
0x14000bc10  mov     edi, eax
0x14000bc12  mov     rax, cs:LogSessions
0x14000bc19  mov     [rax+r15*8+0Ch], edi
0x14000bc1e  jmp     loc_14000BB5B
0x14000bc23  mov     ebx, 0C000000Dh
0x14000bc28  jmp     short loc_14000BCA0
0x14000bc2a  sub     edx, 6
0x14000bc2d  jz      short loc_14000BC9E
0x14000bc2f  sub     edx, 1
0x14000bc32  jz      short loc_14000BC9E
0x14000bc34  sub     edx, 1
0x14000bc37  jz      short loc_14000BC40
0x14000bc39  mov     ebx, 0C0000010h
0x14000bc3e  jmp     short loc_14000BCA0
0x14000bc40  mov     ebp, 98h
0x14000bc45  cmp     edi, ebp
0x14000bc47  jb      short loc_14000BCBA
0x14000bc49  mov     r8, rdi; Size
0x14000bc4c  xor     edx, edx; Val
0x14000bc4e  mov     rcx, rsi; void *
0x14000bc51  call    memset
0x14000bc56  xor     edx, edx
0x14000bc58  mov     [rsi], ebp
0x14000bc5a  mov     dword ptr [rsi+8], 0
0x14000bc61  lea     r8, WmiRegistrationContext.Queue
0x14000bc68  mov     dword ptr [rsi+10h], 4
0x14000bc6f  lea     edi, [rdx+1]
0x14000bc72  mov     rax, rdx
0x14000bc75  mov     rcx, rdx
0x14000bc78  shl     rcx, 5
0x14000bc7c  add     rax, rax
0x14000bc7f  add     rdx, rdi
0x14000bc82  movups  xmm0, xmmword ptr [r8+rax*8]
0x14000bc87  mov     dword ptr [rcx+rsi+28h], 81000h
0x14000bc8f  movdqu  xmmword ptr [rcx+rsi+18h], xmm0
0x14000bc95  cmp     rdx, 4
0x14000bc99  jnz     short loc_14000BC72
0x14000bc9b  mov     [r14], ebp
0x14000bc9e  xor     ebx, ebx
0x14000bca0  mov     rbp, [rsp+58h+arg_10]
0x14000bca5  mov     eax, ebx
0x14000bca7  mov     rbx, [rsp+58h+arg_8]
0x14000bcac  add     rsp, 30h
0x14000bcb0  pop     r15
0x14000bcb2  pop     r14
0x14000bcb4  pop     r12
0x14000bcb6  pop     rdi
0x14000bcb7  pop     rsi
0x14000bcb8  retn
0x14000bcba  mov     ebx, 0C0000023h
0x14000bcbf  cmp     edi, 4
0x14000bcc2  jb      short loc_14000BCA0
0x14000bcc4  mov     [r9], ebp
0x14000bcc7  mov     dword ptr [r14], 4
0x14000bcce  jmp     short loc_14000BCA0
```
