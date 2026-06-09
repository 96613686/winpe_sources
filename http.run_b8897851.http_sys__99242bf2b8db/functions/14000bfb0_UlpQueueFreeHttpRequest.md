# UlpQueueFreeHttpRequest

- ea: `0x14000bfb0`
- end: `0x14000c382`
- name: `UlpQueueFreeHttpRequest`
- size: `978`
- prototype: ``
- caller_count: `41`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14000a520`
- `0x140019b50`
- `0x14001a900`
- `0x14001aba0`
- `0x14001d270`
- `0x14002cce0`
- `0x1400311f0`
- `0x140037440`
- `0x140038110`
- `0x14003a870`
- `0x14003f1b0`
- `0x14003fa90`
- `0x140051db0`
- `0x14005e0f0`
- `0x14005f3c0`
- `0x14006ce40`
- `0x1400704c4`
- `0x1400710bc`
- `0x1400a1828`
- `0x1400a1c08`
- `0x1400a24c0`
- `0x1400a9694`
- `0x1400aa118`
- `0x1400aee90`
- `0x1400b0e94`
- `0x1400c5c20`
- `0x1400c6584`
- `0x1400cbd30`
- `0x1400cca5c`
- `0x1400cdc2c`
- `0x1400e3c44`
- `0x1400eafb0`
- `0x1400eb700`
- `0x1400ef550`
- `0x1400f03c0`
- `0x1400f1ad8`
- `0x1400f2c7c`
- `0x1400f3fdc`
- `0x14011d648`
- `0x14011e2e8`
- `0x14011ea2c`

## callees

- `0x14000a350`
- `0x14000bfb0`
- `0x14000c390`
- `0x140022610`
- `0x14013dc78`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9e44`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000c06b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000c06b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000c1bc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000c1bc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000c10f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000c10f`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14000c16b`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14000c16b`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14000c32e`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14000c32e`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000c097`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000c097`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000c0d3`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000c0d3`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000c234`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000c234`
- `ntoskrnl!KeSetEvent` at `0x14000c1da`
- `ntoskrnl!KeSetEvent` at `0x14000c1da`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14000c138`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14000c138`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000c217`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000c217`

## pseudocode

```c
void __fastcall UlpQueueFreeHttpRequest(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rdi
  ULONG_PTR v6; // rdx
  void *CurrentServerSilo; // rbx
  char v8; // si
  __int64 v9; // rax
  __int64 v10; // rbp
  ULONG v11; // esi
  ULONG_PTR v12; // rdx
  int v13; // eax
  __int64 v14; // rsi
  __int64 v15; // rax
  __int64 v16; // [rsp+50h] [rbp+8h] BYREF

  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( a1 )
      v15 = *(_QWORD *)(a1 + 64);
    else
      v15 = 0;
    WPP_SF_qq(1032, 40, WPP_682cf469470432b235cb9a4961616e40_Traceguids, a1, v15);
  }
  if ( (*(_DWORD *)(a1 + 2264) & 1) != 0 || *(_QWORD *)(a1 + 2288) || *(_QWORD *)(a1 + 2312) )
  {
    v6 = a1 + 1248;
    if ( *(_QWORD *)(a1 + 1248) || *(_QWORD *)(a1 + 1264) || *(_QWORD *)(a1 + 1280) )
      UlBugCheckEx(1u, v6, (ULONG_PTR)"minio\\http\\sys\\httpconn.c", 0x645u);
    LOBYTE(a4) = 1;
    UlThreadPoolEnqueueWorkItem(0, v6, UlpFreeHttpRequest, a4, *(_QWORD *)(*(_QWORD *)(a1 + 24) + 1088LL), -1);
  }
  else
  {
    v5 = a1 + 1248;
    if ( *(_QWORD *)(a1 + 1248) || *(_QWORD *)(a1 + 1264) || *(_QWORD *)(a1 + 1280) )
      UlBugCheckEx(1u, a1 + 1248, (ULONG_PTR)"minio\\http\\sys\\httpconn.c", 0x64Du);
    CurrentServerSilo = *(void **)(*(_QWORD *)(a1 + 24) + 1088LL);
    if ( !KeGetCurrentIrql() )
    {
      v8 = 0;
      if ( CurrentServerSilo == (void *)-1LL )
      {
        v10 = 0;
      }
      else
      {
        v9 = PsAttachSiloToCurrentThread(CurrentServerSilo);
        v10 = v9;
        v8 = 1;
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
        {
          WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v9, CurrentServerSilo);
          UlpFreeHttpRequest(v5);
LABEL_17:
          if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
            WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v10);
          PsDetachSiloFromCurrentThread(v10);
          goto LABEL_20;
        }
      }
      UlpFreeHttpRequest(v5);
      if ( !v8 )
        goto LABEL_20;
      goto LABEL_17;
    }
    v11 = 0;
    if ( (unsigned int)dword_1401A3F48 > 1 )
    {
      v11 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
      if ( byte_1401A3F60 )
        v11 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
    }
    if ( CurrentServerSilo == (void *)-1LL )
      CurrentServerSilo = (void *)PsGetCurrentServerSilo();
    *(_QWORD *)(v5 + 32) = CurrentServerSilo;
    v16 = 0;
    if ( CurrentServerSilo )
      ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
    PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v16);
    v12 = v16 + 24;
    v13 = _InterlockedIncrement((volatile signed __int32 *)(v16 + 24));
    if ( UxDebugCheckRefcount && v13 <= -1 )
      UlBugCheckEx(3u, v12, 0xDu, v13);
    *(_BYTE *)(v5 + 24) = 1;
    v14 = *(_QWORD *)(qword_1401A3F50 + 8LL * v11);
    *(_QWORD *)(v5 + 16) = UlpFreeHttpRequest;
    if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v14 + 16), (PSLIST_ENTRY)v5) )
    {
      KeSetEvent((PRKEVENT)(v14 + 32), 0, 0);
      if ( *(_BYTE *)(*(_QWORD *)v14 + 33LL) )
      {
        if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v14 + 68), 1, 0) )
        {
          if ( (BYTE11(xmmword_1401A2CA0) & 1) != 0 )
            WPP_SF_Dd(
              1304,
              18,
              WPP_c88c5541e4f33e794c7dde5eb878f2f0_Traceguids,
              *(unsigned int *)(v14 + 8),
              **(_DWORD **)v14);
          _InterlockedIncrement((volatile signed __int32 *)(v14 + 64));
          ExAcquireRundownProtection(&UlThreadPoolIoWorkItemsRundown);
          IoQueueWorkItemEx(*(PIO_WORKITEM *)(v14 + 56), UlpThreadPoolStarter, DelayedWorkQueue, (PVOID)v14);
        }
      }
    }
  }
LABEL_20:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 41, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
}

```

## disassembly

```asm
0x14000bfb0  push    rbx
0x14000bfb2  sub     rsp, 40h
0x14000bfb6  mov     rbx, rcx
0x14000bfb9  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000bfc0  jnz     loc_14000C29A
0x14000bfc6  mov     eax, [rbx+8D8h]
0x14000bfcc  mov     [rsp+48h+arg_8], rbp
0x14000bfd1  mov     [rsp+48h+arg_10], rsi
0x14000bfd6  mov     [rsp+48h+arg_18], rdi
0x14000bfdb  test    al, 1
0x14000bfdd  jnz     short loc_14000C029
0x14000bfdf  cmp     qword ptr [rbx+8F0h], 0
0x14000bfe7  jnz     short loc_14000C029
0x14000bfe9  cmp     qword ptr [rbx+908h], 0
0x14000bff1  jnz     short loc_14000C029
0x14000bff3  lea     rdi, [rbx+4E0h]
0x14000bffa  cmp     qword ptr [rdi], 0
0x14000bffe  jnz     short loc_14000C00E
0x14000c000  cmp     qword ptr [rdi+10h], 0
0x14000c005  jnz     short loc_14000C00E
0x14000c007  cmp     qword ptr [rdi+20h], 0
0x14000c00c  jz      short loc_14000C060
0x14000c00e  mov     r9d, 64Dh; BugCheckParameter4
0x14000c014  lea     r8, aMinioHttpSysHt; "minio\\http\\sys\\httpconn.c"
0x14000c01b  mov     rdx, rdi; BugCheckParameter2
0x14000c01e  mov     ecx, 1; BugCheckParameter1
0x14000c023  call    UlBugCheckEx
0x14000c029  lea     rdx, [rbx+4E0h]; BugCheckParameter2
0x14000c030  cmp     qword ptr [rdx], 0
0x14000c034  jnz     short loc_14000C048
0x14000c036  cmp     qword ptr [rdx+10h], 0
0x14000c03b  jnz     short loc_14000C048
0x14000c03d  cmp     qword ptr [rdx+20h], 0
0x14000c042  jz      loc_14000C26C
0x14000c048  mov     r9d, 645h; BugCheckParameter4
0x14000c04e  lea     r8, aMinioHttpSysHt; "minio\\http\\sys\\httpconn.c"
0x14000c055  mov     ecx, 1; BugCheckParameter1
0x14000c05a  call    UlBugCheckEx
0x14000c060  mov     rax, [rbx+18h]
0x14000c064  mov     rbx, [rax+440h]
0x14000c06b  call    cs:__imp_KeGetCurrentIrql
0x14000c072  nop     dword ptr [rax+rax+00h]
0x14000c077  test    al, al
0x14000c079  jnz     loc_14000C102
0x14000c07f  xor     sil, sil
0x14000c082  xorps   xmm0, xmm0
0x14000c085  movups  [rsp+48h+var_18], xmm0
0x14000c08a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000c08e  jz      loc_14000C262
0x14000c094  mov     rcx, rbx
0x14000c097  call    cs:__imp_PsAttachSiloToCurrentThread
0x14000c09e  nop     dword ptr [rax+rax+00h]
0x14000c0a3  mov     rbp, rax
0x14000c0a6  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14000c0ad  mov     sil, 1
0x14000c0b0  jnz     loc_14000C2CA
0x14000c0b6  mov     rcx, rdi
0x14000c0b9  call    UlpFreeHttpRequest
0x14000c0be  test    sil, sil
0x14000c0c1  jz      short loc_14000C0DF
0x14000c0c3  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14000c0ca  jnz     loc_14000C2F5
0x14000c0d0  mov     rcx, rbp
0x14000c0d3  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14000c0da  nop     dword ptr [rax+rax+00h]
0x14000c0df  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000c0e6  jnz     loc_14000C367
0x14000c0ec  mov     rdi, [rsp+48h+arg_18]
0x14000c0f1  mov     rsi, [rsp+48h+arg_10]
0x14000c0f6  mov     rbp, [rsp+48h+arg_8]
0x14000c0fb  add     rsp, 40h
0x14000c0ff  pop     rbx
0x14000c100  retn
0x14000c102  xor     esi, esi
0x14000c104  cmp     cs:dword_1401A3F48, 1
0x14000c10b  jbe     short loc_14000C132
0x14000c10d  xor     ecx, ecx; ProcNumber
0x14000c10f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000c116  nop     dword ptr [rax+rax+00h]
0x14000c11b  xor     edx, edx
0x14000c11d  div     cs:UxNumberOfProcessors
0x14000c123  cmp     cs:byte_1401A3F60, 0
0x14000c12a  mov     esi, edx
0x14000c12c  jnz     loc_14000C313
0x14000c132  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000c136  jnz     short loc_14000C147
0x14000c138  call    cs:__imp_PsGetCurrentServerSilo
0x14000c13f  nop     dword ptr [rax+rax+00h]
0x14000c144  mov     rbx, rax
0x14000c147  mov     [rdi+20h], rbx
0x14000c14b  mov     [rsp+48h+arg_0], 0
0x14000c154  test    rbx, rbx
0x14000c157  jnz     loc_14000C326
0x14000c15d  mov     edx, cs:UxPodMonitorSlot
0x14000c163  lea     r8, [rsp+48h+arg_0]
0x14000c168  mov     rcx, rbx
0x14000c16b  call    cs:__imp_PsGetPermanentSiloContext
0x14000c172  nop     dword ptr [rax+rax+00h]
0x14000c177  mov     rdx, [rsp+48h+arg_0]
0x14000c17c  mov     ebx, 1
0x14000c181  add     rdx, 18h; BugCheckParameter2
0x14000c185  mov     eax, ebx
0x14000c187  lock xadd [rdx], eax
0x14000c18b  inc     eax
0x14000c18d  cmp     cs:UxDebugCheckRefcount, 0
0x14000c194  jnz     loc_14000C245
0x14000c19a  mov     [rdi+18h], bl
0x14000c19d  lea     r8, UlpFreeHttpRequest
0x14000c1a4  mov     rax, cs:qword_1401A3F50
0x14000c1ab  mov     rdx, rdi; ListEntry
0x14000c1ae  mov     ecx, esi
0x14000c1b0  mov     rsi, [rax+rcx*8]
0x14000c1b4  mov     [rdi+10h], r8
0x14000c1b8  lea     rcx, [rsi+10h]; ListHead
0x14000c1bc  call    cs:__imp_ExpInterlockedPushEntrySList
0x14000c1c3  nop     dword ptr [rax+rax+00h]
0x14000c1c8  test    rax, rax
0x14000c1cb  jnz     loc_14000C0DF
0x14000c1d1  lea     rcx, [rsi+20h]; Event
0x14000c1d5  xor     r8d, r8d; Wait
0x14000c1d8  xor     edx, edx; Increment
0x14000c1da  call    cs:__imp_KeSetEvent
0x14000c1e1  nop     dword ptr [rax+rax+00h]
0x14000c1e6  mov     rax, [rsi]
0x14000c1e9  cmp     byte ptr [rax+21h], 0
0x14000c1ed  jz      loc_14000C0DF
0x14000c1f3  xor     eax, eax
0x14000c1f5  lock cmpxchg [rsi+44h], ebx
0x14000c1fa  jnz     loc_14000C0DF
0x14000c200  test    byte ptr cs:xmmword_1401A2CA0+0Bh, bl
0x14000c206  jnz     loc_14000C33F
0x14000c20c  lock inc dword ptr [rsi+40h]
0x14000c210  lea     rcx, UlThreadPoolIoWorkItemsRundown; RunRef
0x14000c217  call    cs:__imp_ExAcquireRundownProtection
0x14000c21e  nop     dword ptr [rax+rax+00h]
0x14000c223  mov     rcx, [rsi+38h]; IoWorkItem
0x14000c227  lea     rdx, UlpThreadPoolStarter; WorkerRoutine
0x14000c22e  mov     r9, rsi; Context
0x14000c231  mov     r8d, ebx; QueueType
0x14000c234  call    cs:__imp_IoQueueWorkItemEx
0x14000c23b  nop     dword ptr [rax+rax+00h]
0x14000c240  jmp     loc_14000C0DF
0x14000c245  cmp     eax, 0FFFFFFFFh
0x14000c248  jg      loc_14000C19A
0x14000c24e  movsxd  r9, eax; BugCheckParameter4
0x14000c251  mov     ecx, 3; BugCheckParameter1
0x14000c256  mov     r8d, 0Dh; BugCheckParameter3
0x14000c25c  call    UlBugCheckEx
0x14000c262  mov     rbp, qword ptr [rsp+48h+var_18+8]
0x14000c267  jmp     loc_14000C0B6
0x14000c26c  mov     rax, [rbx+18h]
0x14000c270  lea     r8, UlpFreeHttpRequest
0x14000c277  mov     [rsp+48h+var_20], 0FFFFFFFFh
0x14000c27f  mov     r9b, 1
0x14000c282  xor     ecx, ecx
0x14000c284  mov     rax, [rax+440h]
0x14000c28b  mov     [rsp+48h+var_28], rax
0x14000c290  call    UlThreadPoolEnqueueWorkItem
0x14000c295  jmp     loc_14000C0DF
0x14000c29a  test    rbx, rbx
0x14000c29d  jz      short loc_14000C2C6
0x14000c29f  mov     rax, [rcx+40h]
0x14000c2a3  mov     edx, 28h ; '('
0x14000c2a8  mov     [rsp+48h+var_28], rax
0x14000c2ad  mov     ecx, 408h
0x14000c2b2  lea     r8, WPP_682cf469470432b235cb9a4961616e40_Traceguids
0x14000c2b9  mov     r9, rbx
0x14000c2bc  call    WPP_SF_qq
0x14000c2c1  jmp     loc_14000BFC6
0x14000c2c6  xor     eax, eax
0x14000c2c8  jmp     short loc_14000C2A3
0x14000c2ca  mov     edx, 19h
0x14000c2cf  mov     [rsp+48h+var_28], rbx
0x14000c2d4  mov     ecx, 51Ch
0x14000c2d9  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x14000c2e0  mov     r9, rax
0x14000c2e3  call    WPP_SF_qq
0x14000c2e8  mov     rcx, rdi
0x14000c2eb  call    UlpFreeHttpRequest
0x14000c2f0  jmp     loc_14000C0C3
0x14000c2f5  mov     edx, 1Ah
0x14000c2fa  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x14000c301  mov     ecx, 51Ch
0x14000c306  mov     r9, rbp
0x14000c309  call    WPP_SF_q
0x14000c30e  jmp     loc_14000C0D0
0x14000c313  lea     rcx, UlThreadPoolArena
0x14000c31a  call    UlpAssignThreadPoolWork
0x14000c31f  mov     esi, eax
0x14000c321  jmp     loc_14000C132
0x14000c326  mov     edx, 49576C55h; Tag
0x14000c32b  mov     rcx, rbx; Object
0x14000c32e  call    cs:__imp_ObfReferenceObjectWithTag
0x14000c335  nop     dword ptr [rax+rax+00h]
0x14000c33a  jmp     loc_14000C15D
0x14000c33f  mov     rax, [rsi]
0x14000c342  lea     r8, WPP_c88c5541e4f33e794c7dde5eb878f2f0_Traceguids
0x14000c349  mov     r9d, [rsi+8]
0x14000c34d  mov     edx, 12h
0x14000c352  mov     ecx, 518h
0x14000c357  mov     eax, [rax]
0x14000c359  mov     dword ptr [rsp+48h+var_28], eax
0x14000c35d  call    WPP_SF_Dd
0x14000c362  jmp     loc_14000C20C
0x14000c367  mov     edx, 29h ; ')'
0x14000c36c  lea     r8, WPP_682cf469470432b235cb9a4961616e40_Traceguids
0x14000c373  mov     ecx, 408h
0x14000c378  call    WPP_SF_
0x14000c37d  jmp     loc_14000C0EC
```
