# CcSetupWatchForRegistryChanges

- ea: `0x1405be464`
- end: `0x1405be622`
- name: `CcSetupWatchForRegistryChanges`
- size: `446`
- prototype: `void()`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14041bec8`

## callees

- `0x1402a2f90`
- `0x1402a4aa0`
- `0x140403380`
- `0x1405be3ec`
- `0x1405be464`
- `0x1406df840`
- `0x1406f7380`
- `0x140bb1320`

## string_xrefs

- `0x1405be4db`: `\Registry\Machine\System\CurrentControlSet\Control\Session Manager\Memory Management`
- `0x1405be595`: `CcSetupWatchForRegistryChanges: Failed, status=0x%08x for "%wZ"\n`
- `0x1405be5c1`: `CcSetupWatchForRegistryChanges: Error-unexpected memory allocation!\n`
- `0x140705a97`: `CcSetupWatchForRegistryChanges: Error-unexpected memory allocation!\n`
- `0x1405be523`: `CcSetupWatchForRegistryChanges: Failed to open Key, status=0x%08x "%wZ"\n`
- `0x1405be57b`: `CcSetupWatchForRegistryChanges: Queued for "%wZ"\n`
- `0x1405be5fb`: `CcSetupWatchForRegistryChanges: Queuing worker thread, status=0x%08x for "%wZ"\n`
- `0x140705ac5`: `CcSetupWatchForRegistryChanges: Queuing worker thread, status=0x%08x for "%wZ"\n`

## pseudocode

```c
void CcSetupWatchForRegistryChanges()
{
  char *PoolWithTag; // rax
  char *v1; // rbx
  int v2; // edi
  int v3; // eax
  NTSTATUS v4; // eax
  __int128 v5; // [rsp+A8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-38h] BYREF

  IoStatusBlock = 0;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x50u, 0x52576343u);
  v1 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset_0(PoolWithTag, 0, 0x50u);
  if ( !v1 )
  {
    v2 = -1073741670;
    goto LABEL_14;
  }
  RtlInitUnicodeString(
    (PUNICODE_STRING)(v1 + 56),
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Session Manager\\Memory Management");
  *((_QWORD *)v1 + 5) = CcUpdateDynamicRegistrySettings;
  *((_QWORD *)v1 + 2) = CcRegistryChangeCallback;
  *((_QWORD *)v1 + 3) = v1;
  *(_QWORD *)v1 = 0;
  v3 = CcOpenRegistryPath(v1 + 56, v1 + 32);
  v2 = v3;
  if ( v3 < 0 )
  {
    DbgPrintEx(
      0x7Fu,
      0,
      "CcSetupWatchForRegistryChanges: Failed to open Key, status=0x%08x \"%wZ\"\n",
      (unsigned int)v3,
      v1 + 56);
    goto LABEL_14;
  }
  v4 = ZwNotifyChangeKey(*((HANDLE *)v1 + 4), 0, (PIO_APC_ROUTINE)v1, (PVOID)1, &IoStatusBlock, 5u, 1u, 0, 0, 1u);
  v2 = v4;
  if ( v4 == 259 )
  {
    DbgPrintEx(0x7Fu, 2u, "CcSetupWatchForRegistryChanges: Queued for \"%wZ\"\n", v1 + 56);
LABEL_13:
    CcRegistryWatchInitComplete = 1;
    goto LABEL_14;
  }
  if ( v4 >= 0 )
    goto LABEL_13;
  DbgPrintEx(0x7Fu, 0, "CcSetupWatchForRegistryChanges: Failed, status=0x%08x for \"%wZ\"\n", (unsigned int)v4, v1 + 56);
LABEL_14:
  if ( v1 )
  {
    if ( v2 < 0 )
    {
      v5 = *(_OWORD *)(v1 + 56);
      DbgPrintEx(
        0x7Fu,
        2u,
        "CcSetupWatchForRegistryChanges: Queuing worker thread, status=0x%08x for \"%wZ\"\n",
        (unsigned int)v2,
        &v5);
      v1[72] = 1;
      ExQueueWorkItem((PWORK_QUEUE_ITEM)v1, DelayedWorkQueue);
    }
  }
  else
  {
    DbgPrintEx(0x7Fu, 0, "CcSetupWatchForRegistryChanges: Error-unexpected memory allocation!\n");
  }
}

```

## disassembly

```asm
0x1405be464  push    rbx
0x1405be466  push    rsi
0x1405be467  push    rdi
0x1405be468  push    r14
0x1405be46a  sub     rsp, 88h
0x1405be471  mov     [rsp+0A8h+var_58], 0C0000001h
0x1405be479  xorps   xmm0, xmm0
0x1405be47c  movups  xmmword ptr [rsp+0A8h+var_38], xmm0
0x1405be481  mov     [rsp+0A8h+var_50], 0
0x1405be48a  mov     edi, 50h ; 'P'
0x1405be48f  mov     r8d, 52576343h; Tag
0x1405be495  mov     edx, edi; NumberOfBytes
0x1405be497  mov     ecx, 600h; PoolType
0x1405be49c  call    ExAllocatePoolWithTag
0x1405be4a1  mov     rbx, rax
0x1405be4a4  cmp     cs:ExPoolZeroingNativelySupported, 0
0x1405be4ab  jnz     short loc_1405BE4BF
0x1405be4ad  test    rax, rax
0x1405be4b0  jz      short loc_1405BE4BF
0x1405be4b2  mov     r8d, edi; Size
0x1405be4b5  xor     edx, edx; Val
0x1405be4b7  mov     rcx, rax; void *
0x1405be4ba  call    memset_0
0x1405be4bf  mov     [rsp+0A8h+var_50], rbx
0x1405be4c4  test    rbx, rbx
0x1405be4c7  jnz     short loc_1405BE4D7
0x1405be4c9  mov     edi, 0C000009Ah
0x1405be4ce  mov     [rsp+0A8h+var_58], edi
0x1405be4d2  jmp     loc_1405BE5BC
0x1405be4d7  lea     rsi, [rbx+38h]
0x1405be4db  lea     rdx, aRegistryMachin_74; "\\Registry\\Machine\\System\\CurrentCon"...
0x1405be4e2  mov     rcx, rsi; DestinationString
0x1405be4e5  call    RtlInitUnicodeString
0x1405be4ea  lea     rax, CcUpdateDynamicRegistrySettings
0x1405be4f1  mov     [rbx+28h], rax
0x1405be4f5  lea     rax, CcRegistryChangeCallback
0x1405be4fc  mov     [rbx+10h], rax
0x1405be500  mov     [rbx+18h], rbx
0x1405be504  mov     qword ptr [rbx], 0
0x1405be50b  lea     rdx, [rbx+20h]
0x1405be50f  mov     rcx, rsi
0x1405be512  call    CcOpenRegistryPath
0x1405be517  mov     edi, eax
0x1405be519  mov     [rsp+0A8h+var_58], eax
0x1405be51d  xor     edx, edx; Event
0x1405be51f  test    eax, eax
0x1405be521  jns     short loc_1405BE52C
0x1405be523  lea     r8, aCcsetupwatchfo_3; "CcSetupWatchForRegistryChanges: Failed "...
0x1405be52a  jmp     short loc_1405BE59E
0x1405be52c  mov     [rsp+0A8h+Asynchronous], 1; Asynchronous
0x1405be531  mov     [rsp+0A8h+BufferSize], 0; BufferSize
0x1405be539  mov     [rsp+0A8h+Buffer], 0; Buffer
0x1405be542  mov     [rsp+0A8h+WatchTree], 1; WatchTree
0x1405be547  mov     [rsp+0A8h+CompletionFilter], 5; CompletionFilter
0x1405be54f  lea     rax, [rsp+0A8h+var_38]
0x1405be554  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x1405be559  mov     r9d, 1; ApcContext
0x1405be55f  mov     r8, rbx; ApcRoutine
0x1405be562  mov     rcx, [rbx+20h]; KeyHandle
0x1405be566  call    ZwNotifyChangeKey
0x1405be56b  mov     edi, eax
0x1405be56d  mov     [rsp+0A8h+var_58], eax
0x1405be571  cmp     eax, 103h
0x1405be576  jnz     short loc_1405BE591
0x1405be578  mov     r9, rsi
0x1405be57b  lea     r8, aCcsetupwatchfo_1; "CcSetupWatchForRegistryChanges: Queued "...
0x1405be582  mov     edx, 2; Level
0x1405be587  lea     ecx, [rdx+7Dh]; ComponentId
0x1405be58a  call    DbgPrintEx
0x1405be58f  jmp     short loc_1405BE5B2
0x1405be591  test    eax, eax
0x1405be593  jns     short loc_1405BE5B2
0x1405be595  lea     r8, aCcsetupwatchfo_0; "CcSetupWatchForRegistryChanges: Failed,"...
0x1405be59c  xor     edx, edx; Level
0x1405be59e  mov     r9d, eax
0x1405be5a1  mov     [rsp+0A8h+IoStatusBlock], rsi
0x1405be5a6  mov     ecx, 7Fh; ComponentId
0x1405be5ab  call    DbgPrintEx
0x1405be5b0  jmp     short loc_1405BE5BC
0x1405be5b2  mov     cs:CcRegistryWatchInitComplete, 1
0x1405be5bc  test    rbx, rbx
0x1405be5bf  jnz     short loc_1405BE5E0
0x1405be5c1  lea     r8, aCcsetupwatchfo_2; "CcSetupWatchForRegistryChanges: Error-u"...
0x1405be5c8  xor     edx, edx; Level
0x1405be5ca  lea     ecx, [rbx+7Fh]; ComponentId
0x1405be5cd  call    DbgPrintEx
0x1405be5d2  add     rsp, 88h
0x1405be5d9  pop     r14
0x1405be5db  pop     rdi
0x1405be5dc  pop     rsi
0x1405be5dd  pop     rbx
0x1405be5de  retn
0x1405be5e0  test    edi, edi
0x1405be5e2  jns     short loc_1405BE5D2
0x1405be5e4  movups  xmm0, xmmword ptr [rbx+38h]
0x1405be5e8  movdqu  [rsp+0A8h+var_48], xmm0
0x1405be5ee  lea     rax, [rsp+0A8h+var_48]
0x1405be5f3  mov     [rsp+0A8h+IoStatusBlock], rax
0x1405be5f8  mov     r9d, edi
0x1405be5fb  lea     r8, aCcsetupwatchfo; "CcSetupWatchForRegistryChanges: Queuing"...
0x1405be602  mov     edx, 2; Level
0x1405be607  lea     ecx, [rdx+7Dh]; ComponentId
0x1405be60a  call    DbgPrintEx
0x1405be60f  mov     byte ptr [rbx+48h], 1
0x1405be613  mov     edx, 1; QueueType
0x1405be618  mov     rcx, rbx; WorkItem
0x1405be61b  call    ExQueueWorkItem
0x1405be620  jmp     short loc_1405BE5D2
0x140705a84  push    rbx
0x140705a86  push    rbp
0x140705a87  sub     rsp, 58h
0x140705a8b  mov     rbp, rdx
0x140705a8e  mov     rbx, [rbp+58h]
0x140705a92  test    rbx, rbx
0x140705a95  jnz     short loc_140705AAA
0x140705a97  lea     r8, aCcsetupwatchfo_2; "CcSetupWatchForRegistryChanges: Error-u"...
0x140705a9e  xor     edx, edx; Level
0x140705aa0  lea     ecx, [rbx+7Fh]; ComponentId
0x140705aa3  call    DbgPrintEx
0x140705aa8  jmp     short loc_140705AEB
0x140705aaa  mov     r9d, [rbp+50h]
0x140705aae  test    r9d, r9d
0x140705ab1  jns     short loc_140705AEB
0x140705ab3  movups  xmm0, xmmword ptr [rbx+38h]
0x140705ab7  movdqu  xmmword ptr [rbp+60h], xmm0
0x140705abc  lea     rax, [rbp+60h]
0x140705ac0  mov     qword ptr [rsp+68h+var_48], rax
0x140705ac5  lea     r8, aCcsetupwatchfo; "CcSetupWatchForRegistryChanges: Queuing"...
0x140705acc  mov     edx, 2; Level
0x140705ad1  lea     ecx, [rdx+7Dh]; ComponentId
0x140705ad4  call    DbgPrintEx
0x140705ad9  mov     byte ptr [rbx+48h], 1
0x140705add  mov     edx, 1; QueueType
0x140705ae2  mov     rcx, rbx; WorkItem
0x140705ae5  call    ExQueueWorkItem
0x140705aea  nop
0x140705aeb  add     rsp, 58h
0x140705aef  pop     rbp
0x140705af0  pop     rbx
0x140705af1  retn
```
