# SockAsyncSelectHelper

- ea: `0x18000203c`
- end: `0x18000222e`
- name: `SockAsyncSelectHelper`
- size: `498`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e6c0`
- `0x180027140`

## callees

- `0x180001e60`
- `0x18000203c`
- `0x1800028b8`
- `0x1800052a0`
- `0x18000fe60`
- `0x1800214f8`
- `0x1800382b8`
- `0x180053010`

## import_xrefs

- `ntdll!NtSetIoCompletion` at `0x18000211b`
- `ntdll!NtSetIoCompletion` at `0x18000211b`
- `ntdll!RtlFreeHeap` at `0x180002163`
- `ntdll!RtlFreeHeap` at `0x18000221b`
- `ntdll!RtlFreeHeap` at `0x180002163`
- `ntdll!RtlFreeHeap` at `0x18000221b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800020e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000214b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800020e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000214b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002086`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002086`

## pseudocode

```c
__int64 __fastcall SockAsyncSelectHelper(__int64 a1, __int64 a2, int a3, int a4)
{
  _DWORD *HeapRoutine; // r14
  int v9; // eax
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  NTSTATUS v11; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  unsigned int v15; // edi
  char v16[72]; // [rsp+30h] [rbp-48h] BYREF

  HeapRoutine = (_DWORD *)SockAllocateHeapRoutine(SockPrivateHeap, 0, 64);
  if ( !HeapRoutine )
    return 10055;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 224));
  if ( (*(_BYTE *)(a1 + 68) & 0x40) != 0 )
  {
    if ( *(_DWORD *)(a1 + 216) )
    {
      v15 = SockEventSelectHelper(a1, 0, 0);
      if ( v15 )
        goto LABEL_18;
    }
LABEL_4:
    *(_QWORD *)(a1 + 104) = a2;
    *(_DWORD *)(a1 + 116) = a3;
    *(_DWORD *)(a1 + 120) = a4;
    *(_DWORD *)(a1 + 124) = 0;
    if ( !SockIsSocketConnected(a1) && (*(_BYTE *)(a1 + 80) & 1) == 0 )
      *(_DWORD *)(a1 + 124) |= 2u;
    v9 = *(_DWORD *)(a1 + 124);
    v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 224);
    ++*(_DWORD *)(a1 + 112);
    if ( (~v9 & *(_DWORD *)(a1 + 120)) != 0 )
    {
      *(_QWORD *)HeapRoutine = a1;
      HeapRoutine[2] = *(_DWORD *)(a1 + 112);
      LeaveCriticalSection(v10);
      if ( !SockCheckAndReferenceAsyncThread() )
      {
        v15 = 10055;
        goto LABEL_21;
      }
      v11 = NtSetIoCompletion(SockAsyncQueuePort, SockProcessQueuedAsyncSelect, HeapRoutine, 0, 0);
      if ( v11 < 0 )
      {
        _InterlockedDecrement(&SockAsyncThreadReferenceCount);
        v15 = NtStatusToSocketError((unsigned int)v11);
        goto LABEL_21;
      }
      _InterlockedIncrement((volatile signed __int32 *)a1);
    }
    else
    {
      LeaveCriticalSection(v10);
      RtlFreeHeap(SockPrivateHeap, 0, HeapRoutine);
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_qll(v13, 20, v14, a1, *(_DWORD *)(a1 + 120), *(_DWORD *)(a1 + 124));
    }
    return 0;
  }
  v16[0] = 1;
  v15 = SockSetInformation(a1, 2, v16, 0);
  if ( !v15 )
  {
    *(_BYTE *)(a1 + 68) |= 0x40u;
    goto LABEL_4;
  }
LABEL_18:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 224));
LABEL_21:
  RtlFreeHeap(SockPrivateHeap, 0, HeapRoutine);
  return v15;
}

```

## disassembly

```asm
0x18000203c  push    rbx
0x18000203e  push    rbp
0x18000203f  push    rsi
0x180002040  push    rdi
0x180002041  push    r12
0x180002043  push    r14
0x180002045  push    r15
0x180002047  sub     rsp, 40h
0x18000204b  mov     rax, cs:SockAllocateHeapRoutine
0x180002052  mov     r12, rdx
0x180002055  xor     edx, edx
0x180002057  mov     r15d, r8d
0x18000205a  mov     rbx, rcx
0x18000205d  mov     ebp, r9d
0x180002060  mov     rcx, cs:SockPrivateHeap
0x180002067  lea     r8d, [rdx+40h]
0x18000206b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002070  mov     r14, rax
0x180002073  test    rax, rax
0x180002076  jz      loc_180002144
0x18000207c  lea     rsi, [rbx+0E0h]
0x180002083  mov     rcx, rsi; lpCriticalSection
0x180002086  call    cs:__imp_EnterCriticalSection
0x18000208d  nop     dword ptr [rax+rax+00h]
0x180002092  test    byte ptr [rbx+44h], 40h
0x180002096  jz      loc_1800021A8
0x18000209c  cmp     dword ptr [rbx+0D8h], 0
0x1800020a3  jnz     loc_1800021D0
0x1800020a9  mov     rcx, rbx
0x1800020ac  mov     [rbx+68h], r12
0x1800020b0  mov     [rbx+74h], r15d
0x1800020b4  mov     [rbx+78h], ebp
0x1800020b7  mov     dword ptr [rbx+7Ch], 0
0x1800020be  call    SockIsSocketConnected
0x1800020c3  test    al, al
0x1800020c5  jz      loc_180002195
0x1800020cb  mov     eax, [rbx+7Ch]
0x1800020ce  mov     rcx, rsi; lpCriticalSection
0x1800020d1  inc     dword ptr [rbx+70h]
0x1800020d4  not     eax
0x1800020d6  test    [rbx+78h], eax
0x1800020d9  jz      short loc_18000214B
0x1800020db  mov     [r14], rbx
0x1800020de  mov     eax, [rbx+70h]
0x1800020e1  mov     [r14+8], eax
0x1800020e5  call    cs:__imp_LeaveCriticalSection
0x1800020ec  nop     dword ptr [rax+rax+00h]
0x1800020f1  call    SockCheckAndReferenceAsyncThread
0x1800020f6  test    al, al
0x1800020f8  jz      loc_1800021F8
0x1800020fe  mov     rcx, cs:SockAsyncQueuePort; IoCompletionPortHandle
0x180002105  lea     rdx, SockProcessQueuedAsyncSelect; CompletionKey
0x18000210c  xor     r9d, r9d; CompletionStatus
0x18000210f  mov     qword ptr [rsp+78h+CompletionInformation], 0; CompletionInformation
0x180002118  mov     r8, r14; CompletionContext
0x18000211b  call    cs:__imp_NtSetIoCompletion
0x180002122  nop     dword ptr [rax+rax+00h]
0x180002127  test    eax, eax
0x180002129  js      loc_1800021FF
0x18000212f  lock inc dword ptr [rbx]
0x180002132  xor     eax, eax
0x180002134  add     rsp, 40h
0x180002138  pop     r15
0x18000213a  pop     r14
0x18000213c  pop     r12
0x18000213e  pop     rdi
0x18000213f  pop     rsi
0x180002140  pop     rbp
0x180002141  pop     rbx
0x180002142  retn
0x180002144  mov     eax, 2747h
0x180002149  jmp     short loc_180002134
0x18000214b  call    cs:__imp_LeaveCriticalSection
0x180002152  nop     dword ptr [rax+rax+00h]
0x180002157  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18000215e  mov     r8, r14; P
0x180002161  xor     edx, edx; Flags
0x180002163  call    cs:__imp_RtlFreeHeap
0x18000216a  nop     dword ptr [rax+rax+00h]
0x18000216f  test    byte ptr cs:xmmword_180063D60, 2
0x180002176  jz      short loc_180002132
0x180002178  mov     eax, [rbx+7Ch]
0x18000217b  mov     edx, 14h
0x180002180  mov     [rsp+78h+var_50], eax
0x180002184  mov     r9, rbx
0x180002187  mov     eax, [rbx+78h]
0x18000218a  mov     [rsp+78h+CompletionInformation], eax
0x18000218e  call    WPP_SF_qll
0x180002193  jmp     short loc_180002132
0x180002195  test    byte ptr [rbx+50h], 1
0x180002199  jnz     loc_1800020CB
0x18000219f  or      dword ptr [rbx+7Ch], 2
0x1800021a3  jmp     loc_1800020CB
0x1800021a8  xor     r9d, r9d
0x1800021ab  mov     [rsp+78h+var_48], 1
0x1800021b0  lea     r8, [rsp+78h+var_48]
0x1800021b5  mov     rcx, rbx
0x1800021b8  lea     edx, [r9+2]
0x1800021bc  call    SockSetInformation
0x1800021c1  mov     edi, eax
0x1800021c3  test    eax, eax
0x1800021c5  jnz     short loc_1800021E7
0x1800021c7  or      byte ptr [rbx+44h], 40h
0x1800021cb  jmp     loc_1800020A9
0x1800021d0  xor     r8d, r8d
0x1800021d3  xor     edx, edx
0x1800021d5  mov     rcx, rbx
0x1800021d8  call    SockEventSelectHelper
0x1800021dd  mov     edi, eax
0x1800021df  test    eax, eax
0x1800021e1  jz      loc_1800020A9
0x1800021e7  mov     rcx, rsi; lpCriticalSection
0x1800021ea  call    cs:__imp_LeaveCriticalSection
0x1800021f1  nop     dword ptr [rax+rax+00h]
0x1800021f6  jmp     short loc_18000220F
0x1800021f8  mov     edi, 2747h
0x1800021fd  jmp     short loc_18000220F
0x1800021ff  lock dec cs:SockAsyncThreadReferenceCount
0x180002206  mov     ecx, eax
0x180002208  call    NtStatusToSocketError
0x18000220d  mov     edi, eax
0x18000220f  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180002216  mov     r8, r14; P
0x180002219  xor     edx, edx; Flags
0x18000221b  call    cs:__imp_RtlFreeHeap
0x180002222  nop     dword ptr [rax+rax+00h]
0x180002227  mov     eax, edi
0x180002229  jmp     loc_180002134
```
