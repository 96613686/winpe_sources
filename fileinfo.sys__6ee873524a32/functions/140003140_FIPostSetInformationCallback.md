# FIPostSetInformationCallback

- ea: `0x140003140`
- end: `0x1400033ea`
- name: `FIPostSetInformationCallback`
- size: `682`
- prototype: `FLT_POSTOP_CALLBACK_STATUS __stdcall(PFLT_CALLBACK_DATA Data, PCFLT_RELATED_OBJECTS FltObjects, PVOID CompletionContext, FLT_POST_OPERATION_FLAGS Flags)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140001570`
- `0x1400028c8`
- `0x140003140`
- `0x1400033f0`
- `0x140012bd8`
- `0x1400138d4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140003193`
- `ntoskrnl!KeGetCurrentIrql` at `0x140003193`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400032b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400033a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400032b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400033a7`
- `ntoskrnl!ExfReleasePushLock` at `0x1400032a4`
- `ntoskrnl!ExfReleasePushLock` at `0x14000339b`
- `ntoskrnl!ExfReleasePushLock` at `0x1400032a4`
- `ntoskrnl!ExfReleasePushLock` at `0x14000339b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140003263`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000335e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140003263`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000335e`
- `ntoskrnl!ExfAcquirePushLockExclusive` at `0x140003277`
- `ntoskrnl!ExfAcquirePushLockExclusive` at `0x140003372`
- `ntoskrnl!ExfAcquirePushLockExclusive` at `0x140003277`
- `ntoskrnl!ExfAcquirePushLockExclusive` at `0x140003372`
- `FLTMGR!FltReleaseContext` at `0x1400033c1`
- `FLTMGR!FltReleaseContext` at `0x1400033c1`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x1400031cb`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x1400031cb`

## pseudocode

```c
__int64 __fastcall FIPostSetInformationCallback(
        PFLT_CALLBACK_DATA Data,
        PCFLT_RELATED_OBJECTS FltObjects,
        PVOID CompletionContext,
        FLT_POST_OPERATION_FLAGS Flags)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  ULONG Options; // edi
  char *v10; // rdi
  _QWORD *EaBuffer; // rbx
  __int64 v12; // rdx
  _DWORD *v13; // rbx
  char v14; // bl
  _QWORD v16[4]; // [rsp+30h] [rbp-20h] BYREF
  enum _FLT_POSTOP_CALLBACK_STATUS RetPostOperationStatus; // [rsp+80h] [rbp+30h] BYREF
  PFLT_CONTEXT Context; // [rsp+88h] [rbp+38h] BYREF

  v16[0] = FltObjects->Volume;
  v16[1] = FltObjects->Instance;
  v16[2] = FltObjects->FileObject;
  Iopb = Data->Iopb;
  RetPostOperationStatus = FLT_POSTOP_FINISHED_PROCESSING;
  Context = 0;
  Options = Iopb->Parameters.Create.Options;
  if ( KeGetCurrentIrql() > 1u )
  {
    FltDoCompletionProcessingWhenSafe(
      Data,
      FltObjects,
      CompletionContext,
      Flags,
      FIPostSetInformationCallback,
      &RetPostOperationStatus);
    return (unsigned int)RetPostOperationStatus;
  }
  if ( *(_QWORD *)(qword_140009A00 + 24) )
    FIETWLogOperationEnd(Data);
  if ( (Flags & 1) == 0 && Data->IoStatus.Status >= 0 )
  {
    switch ( Options )
    {
      case 0xAu:
        goto LABEL_13;
      case 0xDu:
        goto LABEL_21;
      case 0x13u:
        EaBuffer = Data->Iopb->Parameters.Create.EaBuffer;
        if ( (int)FIStreamGet(Data, v16, &Context, 0) < 0 )
          goto LABEL_26;
        v12 = 1;
        break;
      case 0x14u:
        EaBuffer = Data->Iopb->Parameters.Create.EaBuffer;
        if ( (int)FIStreamGet(Data, v16, &Context, 0) < 0 )
          goto LABEL_26;
        v12 = 0;
        break;
      case 0x40u:
LABEL_21:
        v13 = Data->Iopb->Parameters.Create.EaBuffer;
        if ( Options == 64 )
          v14 = *v13 & 1;
        else
          v14 = *(_BYTE *)v13;
        if ( (int)FIStreamGet(Data, v16, &Context, 0) >= 0 )
        {
          KeEnterCriticalRegion();
          v10 = (char *)Context;
          ExfAcquirePushLockExclusive((char *)Context + 40);
          FIStreamVolatileBitFieldBitSet(v10, 5, v14 != 0);
          ExfReleasePushLock(v10 + 40);
          KeLeaveCriticalRegion();
          goto LABEL_27;
        }
LABEL_26:
        v10 = (char *)Context;
LABEL_27:
        if ( v10 )
          FltReleaseContext(v10);
        return (unsigned int)RetPostOperationStatus;
      case 0x41u:
LABEL_13:
        if ( dword_140009A70 != 1 )
          return (unsigned int)RetPostOperationStatus;
        if ( (int)FIStreamGet(Data, v16, &Context, 0) >= 0 )
        {
          KeEnterCriticalRegion();
          v10 = (char *)Context;
          ExfAcquirePushLockExclusive((char *)Context + 40);
          FIStreamVolatileBitFieldBitSet(v10, 0, 1);
          FIStreamVolatileBitFieldBitSet(v10, 6, 1);
          ExfReleasePushLock(v10 + 40);
          KeLeaveCriticalRegion();
          FIStreamGetInfo(Data);
          goto LABEL_27;
        }
        goto LABEL_26;
      default:
        return (unsigned int)RetPostOperationStatus;
    }
    v10 = (char *)Context;
    FITruncationLog(Context, v12, *EaBuffer);
    goto LABEL_27;
  }
  return (unsigned int)RetPostOperationStatus;
}

```

## disassembly

```asm
0x140003140  mov     [rsp-28h+arg_10], rbx
0x140003145  mov     [rsp-28h+arg_18], rsi
0x14000314a  push    rbp
0x14000314b  push    rdi
0x14000314c  push    r13
0x14000314e  push    r14
0x140003150  push    r15
0x140003152  mov     rbp, rsp
0x140003155  sub     rsp, 50h
0x140003159  mov     rax, [rdx+10h]
0x14000315d  mov     ebx, r9d
0x140003160  mov     [rbp+var_20], rax
0x140003164  mov     r15, r8
0x140003167  mov     rax, [rdx+18h]
0x14000316b  mov     r14, rdx
0x14000316e  mov     [rbp+var_18], rax
0x140003172  mov     rsi, rcx
0x140003175  mov     rax, [rdx+20h]
0x140003179  mov     [rbp+var_10], rax
0x14000317d  mov     rax, [rcx+10h]
0x140003181  mov     [rbp+arg_0], 0
0x140003188  mov     [rbp+Context], 0
0x140003190  mov     edi, [rax+20h]
0x140003193  call    cs:__imp_KeGetCurrentIrql
0x14000319a  nop     dword ptr [rax+rax+00h]
0x14000319f  mov     r13d, 1
0x1400031a5  cmp     al, r13b
0x1400031a8  jbe     short loc_1400031DC
0x1400031aa  lea     rax, [rbp+arg_0]
0x1400031ae  mov     r9d, ebx; Flags
0x1400031b1  mov     [rsp+50h+RetPostOperationStatus], rax; RetPostOperationStatus
0x1400031b6  mov     r8, r15; CompletionContext
0x1400031b9  lea     rax, FIPostSetInformationCallback
0x1400031c0  mov     rdx, r14; FltObjects
0x1400031c3  mov     rcx, rsi; Data
0x1400031c6  mov     [rsp+50h+SafePostCallback], rax; SafePostCallback
0x1400031cb  call    cs:__imp_FltDoCompletionProcessingWhenSafe
0x1400031d2  nop     dword ptr [rax+rax+00h]
0x1400031d7  jmp     loc_1400033CD
0x1400031dc  mov     rax, cs:qword_140009A00
0x1400031e3  mov     rcx, [rax+18h]
0x1400031e7  test    rcx, rcx
0x1400031ea  jz      short loc_1400031F4
0x1400031ec  mov     rcx, rsi
0x1400031ef  call    FIETWLogOperationEnd
0x1400031f4  test    r13b, bl
0x1400031f7  jnz     loc_1400033CD
0x1400031fd  cmp     dword ptr [rsi+18h], 0
0x140003201  jl      loc_1400033CD
0x140003207  mov     ecx, edi
0x140003209  sub     ecx, 0Ah
0x14000320c  jz      short loc_14000323B
0x14000320e  sub     ecx, 3
0x140003211  jz      loc_140003331
0x140003217  sub     ecx, 6
0x14000321a  jz      loc_1400032F7
0x140003220  sub     ecx, r13d
0x140003223  jz      loc_1400032D0
0x140003229  sub     ecx, 2Ch ; ','
0x14000322c  jz      loc_140003331
0x140003232  cmp     ecx, r13d
0x140003235  jnz     loc_1400033CD
0x14000323b  cmp     cs:dword_140009A70, r13d
0x140003242  jnz     loc_1400033CD
0x140003248  xor     r9d, r9d
0x14000324b  lea     r8, [rbp+Context]
0x14000324f  lea     rdx, [rbp+var_20]
0x140003253  mov     rcx, rsi
0x140003256  call    FIStreamGet
0x14000325b  test    eax, eax
0x14000325d  js      loc_1400033B5
0x140003263  call    cs:__imp_KeEnterCriticalRegion
0x14000326a  nop     dword ptr [rax+rax+00h]
0x14000326f  mov     rdi, [rbp+Context]
0x140003273  lea     rcx, [rdi+28h]
0x140003277  call    cs:__imp_ExfAcquirePushLockExclusive
0x14000327e  nop     dword ptr [rax+rax+00h]
0x140003283  mov     r8d, r13d
0x140003286  xor     edx, edx
0x140003288  mov     rcx, rdi
0x14000328b  call    FIStreamVolatileBitFieldBitSet
0x140003290  mov     r8d, r13d
0x140003293  mov     edx, 6
0x140003298  mov     rcx, rdi
0x14000329b  call    FIStreamVolatileBitFieldBitSet
0x1400032a0  lea     rcx, [rdi+28h]
0x1400032a4  call    cs:__imp_ExfReleasePushLock
0x1400032ab  nop     dword ptr [rax+rax+00h]
0x1400032b0  call    cs:__imp_KeLeaveCriticalRegion
0x1400032b7  nop     dword ptr [rax+rax+00h]
0x1400032bc  mov     r8, rdi
0x1400032bf  lea     rdx, [rbp+var_20]
0x1400032c3  mov     rcx, rsi; CallbackData
0x1400032c6  call    FIStreamGetInfo
0x1400032cb  jmp     loc_1400033B9
0x1400032d0  mov     rax, [rsi+10h]
0x1400032d4  lea     r8, [rbp+Context]
0x1400032d8  xor     r9d, r9d
0x1400032db  lea     rdx, [rbp+var_20]
0x1400032df  mov     rcx, rsi
0x1400032e2  mov     rbx, [rax+38h]
0x1400032e6  call    FIStreamGet
0x1400032eb  test    eax, eax
0x1400032ed  js      loc_1400033B5
0x1400032f3  xor     edx, edx
0x1400032f5  jmp     short loc_14000331D
0x1400032f7  mov     rax, [rsi+10h]
0x1400032fb  lea     r8, [rbp+Context]
0x1400032ff  xor     r9d, r9d
0x140003302  lea     rdx, [rbp+var_20]
0x140003306  mov     rcx, rsi
0x140003309  mov     rbx, [rax+38h]
0x14000330d  call    FIStreamGet
0x140003312  test    eax, eax
0x140003314  js      loc_1400033B5
0x14000331a  mov     edx, r13d
0x14000331d  mov     rdi, [rbp+Context]
0x140003321  mov     r8, [rbx]
0x140003324  mov     rcx, rdi
0x140003327  call    FITruncationLog
0x14000332c  jmp     loc_1400033B9
0x140003331  mov     rax, [rsi+10h]
0x140003335  mov     rbx, [rax+38h]
0x140003339  cmp     edi, 40h ; '@'
0x14000333c  jnz     short loc_140003345
0x14000333e  mov     ebx, [rbx]
0x140003340  and     bl, r13b
0x140003343  jmp     short loc_140003347
0x140003345  mov     bl, [rbx]
0x140003347  xor     r9d, r9d
0x14000334a  lea     r8, [rbp+Context]
0x14000334e  lea     rdx, [rbp+var_20]
0x140003352  mov     rcx, rsi
0x140003355  call    FIStreamGet
0x14000335a  test    eax, eax
0x14000335c  js      short loc_1400033B5
0x14000335e  call    cs:__imp_KeEnterCriticalRegion
0x140003365  nop     dword ptr [rax+rax+00h]
0x14000336a  mov     rdi, [rbp+Context]
0x14000336e  lea     rcx, [rdi+28h]
0x140003372  call    cs:__imp_ExfAcquirePushLockExclusive
0x140003379  nop     dword ptr [rax+rax+00h]
0x14000337e  mov     edx, 5
0x140003383  mov     rcx, rdi
0x140003386  test    bl, bl
0x140003388  jz      short loc_14000338F
0x14000338a  mov     r8d, r13d
0x14000338d  jmp     short loc_140003392
0x14000338f  xor     r8d, r8d
0x140003392  call    FIStreamVolatileBitFieldBitSet
0x140003397  lea     rcx, [rdi+28h]
0x14000339b  call    cs:__imp_ExfReleasePushLock
0x1400033a2  nop     dword ptr [rax+rax+00h]
0x1400033a7  call    cs:__imp_KeLeaveCriticalRegion
0x1400033ae  nop     dword ptr [rax+rax+00h]
0x1400033b3  jmp     short loc_1400033B9
0x1400033b5  mov     rdi, [rbp+Context]
0x1400033b9  test    rdi, rdi
0x1400033bc  jz      short loc_1400033CD
0x1400033be  mov     rcx, rdi; Context
0x1400033c1  call    cs:__imp_FltReleaseContext
0x1400033c8  nop     dword ptr [rax+rax+00h]
0x1400033cd  mov     eax, [rbp+arg_0]
0x1400033d0  lea     r11, [rsp+50h+var_s0]
0x1400033d5  mov     rbx, [r11+40h]
0x1400033d9  mov     rsi, [r11+48h]
0x1400033dd  mov     rsp, r11
0x1400033e0  pop     r15
0x1400033e2  pop     r14
0x1400033e4  pop     r13
0x1400033e6  pop     rdi
0x1400033e7  pop     rbp
0x1400033e8  retn
```
