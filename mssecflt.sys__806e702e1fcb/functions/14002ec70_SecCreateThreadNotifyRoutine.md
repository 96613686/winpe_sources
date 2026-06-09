# SecCreateThreadNotifyRoutine

- ea: `0x14002ec70`
- end: `0x14002f0f9`
- name: `SecCreateThreadNotifyRoutine`
- size: `1161`
- prototype: `EXPAND_STACK_CALLOUT`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140006754`
- `0x140006b6c`
- `0x140006d3c`
- `0x14000885c`
- `0x14000888c`
- `0x140009b80`
- `0x14000ab48`
- `0x14000ac04`
- `0x140010080`
- `0x140011610`
- `0x140011650`
- `0x14002c6b0`
- `0x14002e97c`
- `0x14002ec70`
- `0x140040f3c`
- `0x1400425bc`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14002ed39`
- `ntoskrnl!ObfReferenceObject` at `0x14002ed39`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002f019`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002f019`
- `ntoskrnl!PsGetThreadProcess` at `0x14002ed23`
- `ntoskrnl!PsGetThreadProcess` at `0x14002ed23`
- `ntoskrnl!PsLookupThreadByThreadId` at `0x14002ece0`
- `ntoskrnl!PsLookupThreadByThreadId` at `0x14002ece0`
- `ntoskrnl!PsIsSystemThread` at `0x14002ecfe`
- `ntoskrnl!PsIsSystemThread` at `0x14002ecfe`
- `ntoskrnl!ZwQueryVirtualMemory` at `0x14002ef36`
- `ntoskrnl!ZwQueryVirtualMemory` at `0x14002efaa`
- `ntoskrnl!ZwQueryVirtualMemory` at `0x14002ef36`
- `ntoskrnl!ZwQueryVirtualMemory` at `0x14002efaa`
- `ntoskrnl!PsInitialSystemProcess` at `0x14002ed45`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14002efe4`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14002efe4`
- `ntoskrnl!KeStackAttachProcess` at `0x14002ef0d`
- `ntoskrnl!KeStackAttachProcess` at `0x14002ef0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ee46`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ee46`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002ef77`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002ef77`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002ed55`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002ed55`
- `ntoskrnl!ObfDereferenceObject` at `0x14002edf9`
- `ntoskrnl!ObfDereferenceObject` at `0x14002ee0d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002edf9`
- `ntoskrnl!ObfDereferenceObject` at `0x14002ee0d`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002ed64`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002ed64`

## pseudocode

```c
void __fastcall SecCreateThreadNotifyRoutine(_QWORD *Parameter)
{
  void *v2; // rcx
  PEPROCESS v3; // rbx
  void *v4; // rdi
  HANDLE CurrentProcessId; // r14
  __int64 v6; // r8
  PVOID PoolWithTag; // rax
  void *v8; // rdi
  unsigned int CurrentThreadId; // eax
  volatile signed __int64 *v10; // rbx
  struct _SLIST_ENTRY *Next; // rdi
  wchar_t *Str; // r14
  __int64 v13; // r15
  struct _SLIST_ENTRY *v14; // rsi
  __int64 v15; // r13
  void *v16; // r12
  char ProcessSessionId_0; // al
  int v18; // ecx
  unsigned int v19; // eax
  PEPROCESS ThreadProcess; // [rsp+88h] [rbp-80h]
  NTSTATUS ThreadStartAddressFromCid; // [rsp+90h] [rbp-78h]
  __int64 v22; // [rsp+98h] [rbp-70h]
  char v23[4]; // [rsp+A0h] [rbp-68h]
  char v24[4]; // [rsp+A4h] [rbp-64h]
  int v25; // [rsp+A8h] [rbp-60h]
  PEPROCESS CurrentProcess; // [rsp+B0h] [rbp-58h]
  int v27; // [rsp+B8h] [rbp-50h]
  PSLIST_ENTRY v28; // [rsp+C0h] [rbp-48h] BYREF
  PSLIST_ENTRY ListEntry; // [rsp+C8h] [rbp-40h] BYREF
  PVOID BaseAddress; // [rsp+D0h] [rbp-38h] BYREF
  PETHREAD Thread; // [rsp+D8h] [rbp-30h] BYREF
  PVOID P; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v33[8]; // [rsp+E8h] [rbp-20h] BYREF
  __int128 MemoryInformation; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v35; // [rsp+100h] [rbp-8h]
  __int128 v36; // [rsp+110h] [rbp+8h]
  struct _KAPC_STATE ApcState; // [rsp+120h] [rbp+18h] BYREF

  ListEntry = 0;
  v28 = 0;
  v2 = (void *)Parameter[1];
  v3 = 0;
  Thread = 0;
  v4 = 0;
  P = 0;
  v33[0] = 0;
  BaseAddress = 0;
  MemoryInformation = 0;
  v22 = 0;
  v35 = 0;
  v36 = 0;
  if ( PsLookupThreadByThreadId(v2, &Thread) < 0 )
    goto LABEL_40;
  if ( PsIsSystemThread(Thread) )
  {
    SecDetAssert28(Parameter[1], *Parameter);
    goto LABEL_11;
  }
  ThreadProcess = PsGetThreadProcess(Thread);
  v3 = ThreadProcess;
  ObfReferenceObject(ThreadProcess);
  if ( PsInitialSystemProcess != ThreadProcess )
  {
    CurrentProcessId = PsGetCurrentProcessId();
    CurrentProcess = IoGetCurrentProcess();
    if ( (int)SecGetProcessContextByObject(CurrentProcess, &ListEntry) < 0 )
    {
      _mm_lfence();
      if ( (int)SecCreateProcessContext(CurrentProcessId, CurrentProcess, 0, &ListEntry) < 0 )
        goto LABEL_40;
    }
    if ( (int)SecGetProcessContextByObject(ThreadProcess, &v28) < 0 )
    {
      _mm_lfence();
      if ( (int)SecCreateProcessContext(*Parameter, ThreadProcess, 0, &v28) < 0 )
        goto LABEL_40;
    }
    if ( (HIDWORD(v28[38].Next) & 1) != 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)&v28[38].Next + 1, 0xFFFFFFFE);
      goto LABEL_11;
    }
    if ( CurrentProcessId != (HANDLE)*Parameter && (xmmword_14001B740 & 0x100000) != 0 )
    {
      if ( (int)SecGetEffectiveTokenUser(KeGetCurrentThread(), (__int64)ListEntry, &P, v33, 0) >= 0 )
      {
        _mm_lfence();
        ThreadStartAddressFromCid = SecGetThreadStartAddressFromCid(Parameter[1], *Parameter, &BaseAddress);
        if ( ThreadStartAddressFromCid >= 0 )
        {
          _mm_lfence();
          memset(&ApcState, 0, sizeof(ApcState));
          KeStackAttachProcess(ThreadProcess, &ApcState);
          ThreadStartAddressFromCid = ZwQueryVirtualMemory(
                                        (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                        BaseAddress,
                                        MemoryBasicInformation,
                                        &MemoryInformation,
                                        0x30u,
                                        0);
          if ( ThreadStartAddressFromCid < 0 )
          {
            MemoryInformation = 0;
            v35 = 0;
            v36 = 0;
          }
          else
          {
            if ( qword_140020008 )
              PoolWithTag = (PVOID)qword_140020008(256, 512, 1833788243);
            else
              PoolWithTag = ExAllocatePoolWithTag(PagedPool, 0x200u, 0x6D4D6353u);
            v22 = (__int64)PoolWithTag;
            v8 = PoolWithTag;
            if ( PoolWithTag )
            {
              ThreadStartAddressFromCid = ZwQueryVirtualMemory(
                                            (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                            BaseAddress,
                                            MemorySectionName,
                                            PoolWithTag,
                                            0x200u,
                                            0);
              if ( ThreadStartAddressFromCid < 0 )
              {
                _mm_lfence();
                SecFreePool(v8, 0x6D4D6353u);
                v22 = 0;
              }
            }
          }
          KeUnstackDetachProcess(&ApcState);
        }
        else
        {
          BaseAddress = 0;
        }
        LOBYTE(v6) = 1;
        SecDetPerformImmediateAssertions(CurrentProcess, ListEntry, v6);
        SecDetPerformProcessAssertionsWithContext(ThreadProcess, v28, 0);
        *(_DWORD *)v23 = *((_DWORD *)Parameter + 2);
        *(_DWORD *)v24 = *(_DWORD *)Parameter;
        CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
        v10 = (volatile signed __int64 *)SecData;
        v27 = CurrentThreadId;
        Next = v28[3].Next;
        Str = (wchar_t *)v28[10].Next;
        v13 = *((_QWORD *)&v28[2].Next + 1);
        v14 = ListEntry[3].Next;
        v15 = *((_QWORD *)&ListEntry[2].Next + 1);
        v16 = *(void **)P;
        v25 = (int)ListEntry[2].Next;
        ProcessSessionId_0 = PsGetProcessSessionId_0(CurrentProcess);
        v18 = _InterlockedExchangeAdd64(v10 + 42, 1u) + 1;
        v19 = EventWriteRemoteThread(
                v18,
                v25,
                v15,
                v27,
                v16,
                ProcessSessionId_0,
                v24[0],
                v13,
                Str,
                v23[0],
                (char)BaseAddress,
                (__int64)&MemoryInformation,
                ThreadStartAddressFromCid,
                (char)v14,
                (char)Next,
                v22);
        SecIncrementEtwCounters(v19);
        v3 = ThreadProcess;
        v4 = (void *)v22;
        goto LABEL_11;
      }
LABEL_40:
      SecIncrementInternalErrorCounter();
    }
  }
LABEL_11:
  if ( Thread )
    ObfDereferenceObject(Thread);
  if ( v3 )
    ObfDereferenceObject(v3);
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( v28 )
    SecReleaseProcessContext(v28);
  if ( P && v33[0] )
    ExFreePoolWithTag(P, 0);
  if ( v4 )
    SecFreePool(v4, 0x6D4D6353u);
}

```

## disassembly

```asm
0x14002ec70  mov     rax, rsp
0x14002ec73  mov     [rax+10h], rbx
0x14002ec77  mov     [rax+18h], rsi
0x14002ec7b  mov     [rax+20h], rdi
0x14002ec7f  push    rbp
0x14002ec80  push    r12
0x14002ec82  push    r13
0x14002ec84  push    r14
0x14002ec86  push    r15
0x14002ec88  lea     rbp, [rax-78h]
0x14002ec8c  sub     rsp, 150h
0x14002ec93  mov     rax, cs:__security_cookie
0x14002ec9a  xor     rax, rsp
0x14002ec9d  mov     [rbp+70h+var_28], rax
0x14002eca1  xor     r12d, r12d
0x14002eca4  lea     rdx, [rbp+70h+Thread]; Thread
0x14002eca8  xorps   xmm0, xmm0
0x14002ecab  mov     [rbp+70h+ListEntry], r12
0x14002ecaf  mov     rsi, rcx
0x14002ecb2  mov     [rbp+70h+var_B8], r12
0x14002ecb6  mov     rcx, [rcx+8]; ThreadId
0x14002ecba  mov     ebx, r12d
0x14002ecbd  mov     [rbp+70h+Thread], r12
0x14002ecc1  mov     edi, r12d
0x14002ecc4  mov     [rbp+70h+P], r12
0x14002ecc8  mov     [rbp+70h+var_90], r12b
0x14002eccc  mov     [rbp+70h+BaseAddress], r12
0x14002ecd0  movups  [rbp+70h+MemoryInformation], xmm0
0x14002ecd4  mov     [rbp+70h+var_E0], r12
0x14002ecd8  movups  [rbp+70h+var_78], xmm0
0x14002ecdc  movups  [rbp+70h+var_68], xmm0
0x14002ece0  call    cs:__imp_PsLookupThreadByThreadId
0x14002ece7  nop     dword ptr [rax+rax+00h]
0x14002ecec  mov     r13d, 6D4D6353h
0x14002ecf2  test    eax, eax
0x14002ecf4  js      loc_14002F0EF
0x14002ecfa  mov     rcx, [rbp+70h+Thread]; Thread
0x14002ecfe  call    cs:__imp_PsIsSystemThread
0x14002ed05  nop     dword ptr [rax+rax+00h]
0x14002ed0a  test    al, al
0x14002ed0c  jz      short loc_14002ED1F
0x14002ed0e  mov     rdx, [rsi]
0x14002ed11  mov     rcx, [rsi+8]
0x14002ed15  call    SecDetAssert28
0x14002ed1a  jmp     loc_14002EDF0
0x14002ed1f  mov     rcx, [rbp+70h+Thread]; Thread
0x14002ed23  call    cs:__imp_PsGetThreadProcess
0x14002ed2a  nop     dword ptr [rax+rax+00h]
0x14002ed2f  mov     rcx, rax; Object
0x14002ed32  mov     [rbp+70h+var_F0], rax
0x14002ed36  mov     rbx, rax
0x14002ed39  call    cs:__imp_ObfReferenceObject
0x14002ed40  nop     dword ptr [rax+rax+00h]
0x14002ed45  mov     rcx, cs:__imp_PsInitialSystemProcess
0x14002ed4c  cmp     [rcx], rbx
0x14002ed4f  jz      loc_14002EDF0
0x14002ed55  call    cs:__imp_PsGetCurrentProcessId
0x14002ed5c  nop     dword ptr [rax+rax+00h]
0x14002ed61  mov     r14, rax
0x14002ed64  call    cs:__imp_IoGetCurrentProcess
0x14002ed6b  nop     dword ptr [rax+rax+00h]
0x14002ed70  mov     rcx, rax
0x14002ed73  mov     [rbp+70h+var_C8], rax
0x14002ed77  lea     rdx, [rbp+70h+ListEntry]
0x14002ed7b  mov     r15, rax
0x14002ed7e  call    SecGetProcessContextByObject
0x14002ed83  test    eax, eax
0x14002ed85  jns     short loc_14002EDA4
0x14002ed87  lfence
0x14002ed8a  lea     r9, [rbp+70h+ListEntry]
0x14002ed8e  xor     r8d, r8d
0x14002ed91  mov     rdx, r15
0x14002ed94  mov     rcx, r14
0x14002ed97  call    SecCreateProcessContext
0x14002ed9c  test    eax, eax
0x14002ed9e  js      loc_14002F0EF
0x14002eda4  lea     rdx, [rbp+70h+var_B8]
0x14002eda8  mov     rcx, rbx
0x14002edab  call    SecGetProcessContextByObject
0x14002edb0  test    eax, eax
0x14002edb2  jns     short loc_14002EDD1
0x14002edb4  lfence
0x14002edb7  mov     rcx, [rsi]
0x14002edba  lea     r9, [rbp+70h+var_B8]
0x14002edbe  xor     r8d, r8d
0x14002edc1  mov     rdx, rbx
0x14002edc4  call    SecCreateProcessContext
0x14002edc9  test    eax, eax
0x14002edcb  js      loc_14002F0EF
0x14002edd1  mov     rax, [rbp+70h+var_B8]
0x14002edd5  mov     ecx, [rax+264h]
0x14002eddb  test    cl, 1
0x14002edde  jz      loc_14002EE90
0x14002ede4  mov     rax, [rbp+70h+var_B8]
0x14002ede8  lock and dword ptr [rax+264h], 0FFFFFFFEh
0x14002edf0  mov     rcx, [rbp+70h+Thread]; Object
0x14002edf4  test    rcx, rcx
0x14002edf7  jz      short loc_14002EE05
0x14002edf9  call    cs:__imp_ObfDereferenceObject
0x14002ee00  nop     dword ptr [rax+rax+00h]
0x14002ee05  test    rbx, rbx
0x14002ee08  jz      short loc_14002EE19
0x14002ee0a  mov     rcx, rbx; Object
0x14002ee0d  call    cs:__imp_ObfDereferenceObject
0x14002ee14  nop     dword ptr [rax+rax+00h]
0x14002ee19  mov     rcx, [rbp+70h+ListEntry]; ListEntry
0x14002ee1d  test    rcx, rcx
0x14002ee20  jz      short loc_14002EE27
0x14002ee22  call    SecReleaseProcessContext
0x14002ee27  mov     rcx, [rbp+70h+var_B8]; ListEntry
0x14002ee2b  test    rcx, rcx
0x14002ee2e  jz      short loc_14002EE35
0x14002ee30  call    SecReleaseProcessContext
0x14002ee35  mov     rcx, [rbp+70h+P]; P
0x14002ee39  test    rcx, rcx
0x14002ee3c  jz      short loc_14002EE52
0x14002ee3e  cmp     [rbp+70h+var_90], r12b
0x14002ee42  jz      short loc_14002EE52
0x14002ee44  xor     edx, edx; Tag
0x14002ee46  call    cs:__imp_ExFreePoolWithTag
0x14002ee4d  nop     dword ptr [rax+rax+00h]
0x14002ee52  test    rdi, rdi
0x14002ee55  jz      short loc_14002EE62
0x14002ee57  mov     edx, r13d; Tag
0x14002ee5a  mov     rcx, rdi; P
0x14002ee5d  call    SecFreePool
0x14002ee62  mov     rcx, [rbp+70h+var_28]
0x14002ee66  xor     rcx, rsp; StackCookie
0x14002ee69  call    __security_check_cookie
0x14002ee6e  lea     r11, [rsp+170h+var_20]
0x14002ee76  mov     rbx, [r11+38h]
0x14002ee7a  mov     rsi, [r11+40h]
0x14002ee7e  mov     rdi, [r11+48h]
0x14002ee82  mov     rsp, r11
0x14002ee85  pop     r15
0x14002ee87  pop     r14
0x14002ee89  pop     r13
0x14002ee8b  pop     r12
0x14002ee8d  pop     rbp
0x14002ee8e  retn
0x14002ee90  cmp     r14, [rsi]
0x14002ee93  jz      loc_14002EDF0
0x14002ee99  test    qword ptr cs:xmmword_14001B740, 100000h
0x14002eea4  jz      loc_14002EDF0
0x14002eeaa  mov     rcx, gs:188h; Thread
0x14002eeb3  lea     r9, [rbp+70h+var_90]
0x14002eeb7  mov     rdx, [rbp+70h+ListEntry]
0x14002eebb  lea     r8, [rbp+70h+P]
0x14002eebf  mov     [rsp+170h+MemoryInformationLength], r12; __int64
0x14002eec4  call    SecGetEffectiveTokenUser
0x14002eec9  test    eax, eax
0x14002eecb  js      loc_14002F0EF
0x14002eed1  lfence
0x14002eed4  mov     rdx, [rsi]
0x14002eed7  lea     r8, [rbp+70h+BaseAddress]
0x14002eedb  mov     rcx, [rsi+8]
0x14002eedf  call    SecGetThreadStartAddressFromCid
0x14002eee4  mov     dword ptr [rbp+70h+var_E8], eax
0x14002eee7  test    eax, eax
0x14002eee9  jns     short loc_14002EEF4
0x14002eeeb  mov     [rbp+70h+BaseAddress], r12
0x14002eeef  jmp     loc_14002EFF0
0x14002eef4  lfence
0x14002eef7  xorps   xmm0, xmm0
0x14002eefa  lea     rdx, [rbp+70h+ApcState]; ApcState
0x14002eefe  mov     rcx, rbx; PROCESS
0x14002ef01  movups  xmmword ptr [rbp+70h+ApcState.ApcListHead.Flink], xmm0
0x14002ef05  movups  xmmword ptr [rbp+70h+ApcState.ApcListHead.Flink+10h], xmm0
0x14002ef09  movups  xmmword ptr [rbp+70h+ApcState.Process], xmm0
0x14002ef0d  call    cs:__imp_KeStackAttachProcess
0x14002ef14  nop     dword ptr [rax+rax+00h]
0x14002ef19  mov     rdx, [rbp+70h+BaseAddress]; BaseAddress
0x14002ef1d  lea     r9, [rbp+70h+MemoryInformation]; MemoryInformation
0x14002ef21  xor     r8d, r8d; MemoryInformationClass
0x14002ef24  mov     [rsp+170h+ReturnLength], r12; ReturnLength
0x14002ef29  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14002ef2d  mov     [rsp+170h+MemoryInformationLength], 30h ; '0'; MemoryInformationLength
0x14002ef36  call    cs:__imp_ZwQueryVirtualMemory
0x14002ef3d  nop     dword ptr [rax+rax+00h]
0x14002ef42  mov     dword ptr [rbp+70h+var_E8], eax
0x14002ef45  test    eax, eax
0x14002ef47  js      loc_14002EFD1
0x14002ef4d  mov     rax, cs:qword_140020008
0x14002ef54  mov     r14d, 200h
0x14002ef5a  mov     r8d, r13d; Tag
0x14002ef5d  mov     edx, r14d; NumberOfBytes
0x14002ef60  test    rax, rax
0x14002ef63  jz      short loc_14002EF72
0x14002ef65  mov     ecx, 100h
0x14002ef6a  call    cs:__guard_dispatch_icall_fptr
0x14002ef70  jmp     short loc_14002EF83
0x14002ef72  mov     ecx, 1; PoolType
0x14002ef77  call    cs:__imp_ExAllocatePoolWithTag
0x14002ef7e  nop     dword ptr [rax+rax+00h]
0x14002ef83  mov     [rbp+70h+var_E0], rax
0x14002ef87  mov     rdi, rax
0x14002ef8a  test    rax, rax
0x14002ef8d  jz      short loc_14002EFE0
0x14002ef8f  mov     rdx, [rbp+70h+BaseAddress]; BaseAddress
0x14002ef93  mov     r9, rax; MemoryInformation
0x14002ef96  mov     [rsp+170h+ReturnLength], r12; ReturnLength
0x14002ef9b  mov     r8d, 2; MemoryInformationClass
0x14002efa1  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14002efa5  mov     [rsp+170h+MemoryInformationLength], r14; MemoryInformationLength
0x14002efaa  call    cs:__imp_ZwQueryVirtualMemory
0x14002efb1  nop     dword ptr [rax+rax+00h]
0x14002efb6  mov     dword ptr [rbp+70h+var_E8], eax
0x14002efb9  test    eax, eax
0x14002efbb  jns     short loc_14002EFE0
0x14002efbd  lfence
0x14002efc0  mov     edx, r13d; Tag
0x14002efc3  mov     rcx, rdi; P
0x14002efc6  call    SecFreePool
0x14002efcb  mov     [rbp+70h+var_E0], r12
0x14002efcf  jmp     short loc_14002EFE0
0x14002efd1  xorps   xmm0, xmm0
0x14002efd4  movups  [rbp+70h+MemoryInformation], xmm0
0x14002efd8  movups  [rbp+70h+var_78], xmm0
0x14002efdc  movups  [rbp+70h+var_68], xmm0
0x14002efe0  lea     rcx, [rbp+70h+ApcState]; ApcState
0x14002efe4  call    cs:__imp_KeUnstackDetachProcess
0x14002efeb  nop     dword ptr [rax+rax+00h]
0x14002eff0  mov     rdx, [rbp+70h+ListEntry]
0x14002eff4  mov     r8b, 1
0x14002eff7  mov     rcx, r15
0x14002effa  call    SecDetPerformImmediateAssertions
0x14002efff  mov     rdx, [rbp+70h+var_B8]
0x14002f003  xor     r8d, r8d
0x14002f006  mov     rcx, rbx
0x14002f009  call    SecDetPerformProcessAssertionsWithContext
0x14002f00e  mov     eax, [rsi+8]
0x14002f011  mov     dword ptr [rbp+70h+var_D8], eax
0x14002f014  mov     eax, [rsi]
0x14002f016  mov     dword ptr [rbp+70h+var_D4], eax
0x14002f019  call    cs:__imp_PsGetCurrentThreadId
0x14002f020  nop     dword ptr [rax+rax+00h]
0x14002f025  mov     rcx, [rbp+70h+var_B8]
0x14002f029  mov     rdx, [rbp+70h+ListEntry]
0x14002f02d  mov     rbx, cs:SecData
0x14002f034  mov     qword ptr [rbp+70h+var_C0], rax
0x14002f038  mov     rdi, [rcx+30h]
0x14002f03c  mov     r14, [rcx+0A0h]
0x14002f043  mov     r15, [rcx+28h]
0x14002f047  mov     rcx, [rbp+70h+P]
0x14002f04b  mov     eax, [rdx+20h]
0x14002f04e  mov     rsi, [rdx+30h]
0x14002f052  mov     r13, [rdx+28h]
0x14002f056  mov     r12, [rcx]
0x14002f059  mov     rcx, [rbp+70h+var_C8]
0x14002f05d  mov     [rbp+70h+var_D0], eax
0x14002f060  call    PsGetProcessSessionId_0
0x14002f065  mov     ecx, 1
0x14002f06a  lock xadd [rbx+150h], rcx
0x14002f073  mov     rdx, [rbp+70h+var_E0]
0x14002f077  inc     rcx; int
0x14002f07a  mov     r9d, [rbp+70h+var_C0]; int
0x14002f07e  mov     r8, r13; int
0x14002f081  mov     [rsp+170h+var_F8], rdx; __int64
0x14002f086  mov     edx, dword ptr [rbp+70h+var_E8]
0x14002f089  mov     qword ptr [rsp+170h+var_100], rdi; char
0x14002f08e  mov     qword ptr [rsp+170h+var_108], rsi; char
0x14002f093  mov     dword ptr [rsp+170h+var_110], edx; char
0x14002f097  lea     rdx, [rbp+70h+MemoryInformation]
0x14002f09b  mov     [rsp+170h+var_118], rdx; __int64
0x14002f0a0  mov     rdx, [rbp+70h+BaseAddress]
0x14002f0a4  mov     qword ptr [rsp+170h+var_120], rdx; char
0x14002f0a9  mov     edx, dword ptr [rbp+70h+var_D8]
0x14002f0ac  mov     dword ptr [rsp+170h+var_128], edx; char
0x14002f0b0  mov     edx, dword ptr [rbp+70h+var_D4]
0x14002f0b3  mov     [rsp+170h+Str], r14; Str
0x14002f0b8  mov     qword ptr [rsp+170h+var_138], r15; char
0x14002f0bd  mov     dword ptr [rsp+170h+var_140], edx; char
0x14002f0c1  mov     edx, [rbp+70h+var_D0]; int
0x14002f0c4  mov     dword ptr [rsp+170h+ReturnLength], eax; char
0x14002f0c8  mov     [rsp+170h+MemoryInformationLength], r12; Sid
0x14002f0cd  call    EventWriteRemoteThread
0x14002f0d2  mov     ecx, eax
0x14002f0d4  call    SecIncrementEtwCounters
0x14002f0d9  mov     rbx, [rbp+70h+var_F0]
0x14002f0dd  xor     r12d, r12d
0x14002f0e0  mov     rdi, [rbp+70h+var_E0]
0x14002f0e4  mov     r13d, 6D4D6353h
0x14002f0ea  jmp     loc_14002EDF0
0x14002f0ef  call    SecIncrementInternalErrorCounter
0x14002f0f4  jmp     loc_14002EDF0
```
