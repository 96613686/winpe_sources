# SockReenableAsyncSelectEvent

- ea: `0x1800216a8`
- end: `0x1800217f6`
- name: `SockReenableAsyncSelectEvent`
- size: `334`
- prototype: ``
- caller_count: `10`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005810`
- `0x18000c2b0`
- `0x180012c10`
- `0x180013670`
- `0x180014420`
- `0x18001d990`
- `0x180025530`
- `0x1800269e0`
- `0x180027140`
- `0x1800456ac`

## callees

- `0x1800028b8`
- `0x1800052a0`
- `0x180008250`
- `0x1800216a8`
- `0x180038258`
- `0x1800382b8`
- `0x180053010`

## import_xrefs

- `ntdll!NtSetIoCompletion` at `0x18002179e`
- `ntdll!NtSetIoCompletion` at `0x18002179e`
- `ntdll!RtlFreeHeap` at `0x180021767`
- `ntdll!RtlFreeHeap` at `0x1800217c3`
- `ntdll!RtlFreeHeap` at `0x180021767`
- `ntdll!RtlFreeHeap` at `0x1800217c3`

## pseudocode

```c
__int64 __fastcall SockReenableAsyncSelectEvent(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // edi
  __int64 v5; // r8
  _DWORD *HeapRoutine; // rsi
  NTSTATUS v8; // ebp
  HANDLE v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8

  v3 = a2;
  if ( ((unsigned int)a2 & *(_DWORD *)(a1 + 124)) == 0 || *(_DWORD *)(a1 + 24) == 4 )
    return 0;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_Lqq(a1, a2, a3, (unsigned int)a2, *(_QWORD *)(a1 + 8), a1);
  v5 = *(unsigned int *)(a1 + 120);
  *(_DWORD *)(a1 + 124) &= ~v3;
  if ( (~*(_DWORD *)(a1 + 124) & (unsigned int)v5) == 0 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_qll(*(unsigned int *)(a1 + 124), 40, v5, a1, v5, *(_DWORD *)(a1 + 124));
    return 0;
  }
  HeapRoutine = (_DWORD *)SockAllocateHeapRoutine(SockPrivateHeap, 0, 64);
  if ( !HeapRoutine )
  {
    *(_DWORD *)(a1 + 124) |= v3;
    return 10055;
  }
  if ( !SockCheckAndReferenceAsyncThread() )
  {
    *(_DWORD *)(a1 + 124) |= v3;
    RtlFreeHeap(SockPrivateHeap, 0, HeapRoutine);
    return 10055;
  }
  _InterlockedIncrement((volatile signed __int32 *)a1);
  *(_QWORD *)HeapRoutine = a1;
  HeapRoutine[2] = ++*(_DWORD *)(a1 + 112);
  v8 = NtSetIoCompletion(SockAsyncQueuePort, SockProcessQueuedAsyncSelect, HeapRoutine, 0, 0);
  if ( v8 >= 0 )
    return 0;
  v9 = SockPrivateHeap;
  *(_DWORD *)(a1 + 124) |= v3;
  RtlFreeHeap(v9, 0, HeapRoutine);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0xFFFFFFFF) == 1 )
    SockDestroySocket(a1, v10, v11);
  _InterlockedDecrement(&SockAsyncThreadReferenceCount);
  return NtStatusToSocketError((unsigned int)v8);
}

```

## disassembly

```asm
0x1800216a8  push    rbx
0x1800216aa  push    rbp
0x1800216ab  push    rsi
0x1800216ac  push    rdi
0x1800216ad  sub     rsp, 38h
0x1800216b1  mov     edi, edx
0x1800216b3  mov     rbx, rcx
0x1800216b6  test    [rcx+7Ch], edx
0x1800216b9  jz      short loc_180021718
0x1800216bb  mov     eax, [rcx+18h]
0x1800216be  cmp     eax, 4
0x1800216c1  jz      short loc_180021718
0x1800216c3  test    byte ptr cs:xmmword_180063D60, 2
0x1800216ca  jz      short loc_1800216E2
0x1800216cc  mov     rax, [rcx+8]
0x1800216d0  mov     r9d, edx
0x1800216d3  mov     [rsp+58h+var_30], rcx
0x1800216d8  mov     qword ptr [rsp+58h+CompletionInformation], rax
0x1800216dd  call    WPP_SF_Lqq
0x1800216e2  mov     r8d, [rbx+78h]
0x1800216e6  mov     eax, edi
0x1800216e8  not     eax
0x1800216ea  and     [rbx+7Ch], eax
0x1800216ed  mov     ecx, [rbx+7Ch]
0x1800216f0  mov     eax, ecx
0x1800216f2  not     eax
0x1800216f4  test    r8d, eax
0x1800216f7  jnz     short loc_180021724
0x1800216f9  test    byte ptr cs:xmmword_180063D60, 2
0x180021700  jz      short loc_180021718
0x180021702  mov     dword ptr [rsp+58h+var_30], ecx
0x180021706  mov     edx, 28h ; '('
0x18002170b  mov     r9, rbx
0x18002170e  mov     [rsp+58h+CompletionInformation], r8d
0x180021713  call    WPP_SF_qll
0x180021718  xor     eax, eax
0x18002171a  add     rsp, 38h
0x18002171e  pop     rdi
0x18002171f  pop     rsi
0x180021720  pop     rbp
0x180021721  pop     rbx
0x180021722  retn
0x180021724  mov     rcx, cs:SockPrivateHeap
0x18002172b  xor     edx, edx
0x18002172d  mov     rax, cs:SockAllocateHeapRoutine
0x180021734  lea     r8d, [rdx+40h]
0x180021738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002173d  mov     rsi, rax
0x180021740  test    rax, rax
0x180021743  jnz     short loc_18002174F
0x180021745  or      [rbx+7Ch], edi
0x180021748  mov     eax, 2747h
0x18002174d  jmp     short loc_18002171A
0x18002174f  call    SockCheckAndReferenceAsyncThread
0x180021754  mov     r8, rsi; CompletionContext
0x180021757  test    al, al
0x180021759  jnz     short loc_180021775
0x18002175b  or      [rbx+7Ch], edi
0x18002175e  xor     edx, edx; Flags
0x180021760  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180021767  call    cs:__imp_RtlFreeHeap
0x18002176e  nop     dword ptr [rax+rax+00h]
0x180021773  jmp     short loc_180021748
0x180021775  lock inc dword ptr [rbx]
0x180021778  mov     [rsi], rbx
0x18002177b  lea     rdx, SockProcessQueuedAsyncSelect; CompletionKey
0x180021782  inc     dword ptr [rbx+70h]
0x180021785  xor     r9d, r9d; CompletionStatus
0x180021788  mov     eax, [rbx+70h]
0x18002178b  mov     [rsi+8], eax
0x18002178e  mov     rcx, cs:SockAsyncQueuePort; IoCompletionPortHandle
0x180021795  mov     qword ptr [rsp+58h+CompletionInformation], 0; CompletionInformation
0x18002179e  call    cs:__imp_NtSetIoCompletion
0x1800217a5  nop     dword ptr [rax+rax+00h]
0x1800217aa  mov     ebp, eax
0x1800217ac  test    eax, eax
0x1800217ae  jns     loc_180021718
0x1800217b4  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800217bb  mov     r8, rsi; P
0x1800217be  or      [rbx+7Ch], edi
0x1800217c1  xor     edx, edx; Flags
0x1800217c3  call    cs:__imp_RtlFreeHeap
0x1800217ca  nop     dword ptr [rax+rax+00h]
0x1800217cf  or      ecx, 0FFFFFFFFh
0x1800217d2  lock xadd [rbx], ecx
0x1800217d6  cmp     ecx, 1
0x1800217d9  jnz     short loc_1800217E3
0x1800217db  mov     rcx, rbx
0x1800217de  call    SockDestroySocket
0x1800217e3  lock dec cs:SockAsyncThreadReferenceCount
0x1800217ea  mov     ecx, ebp
0x1800217ec  call    NtStatusToSocketError
0x1800217f1  jmp     loc_18002171A
```
