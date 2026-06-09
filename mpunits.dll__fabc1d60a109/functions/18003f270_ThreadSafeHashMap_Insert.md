# ThreadSafeHashMap_Insert

- ea: `0x18003f270`
- end: `0x18003f404`
- name: `ThreadSafeHashMap_Insert`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18003da30`

## callees

- `0x18003f270`
- `0x180042ecc`
- `0x180043120`
- `0x1800431f0`
- `0x180043d40`
- `0x180044344`
- `0x1800443d4`
- `0x180044464`
- `0x18004449c`
- `0x1800444f4`
- `0x18004462c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f28d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f37e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f28d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f37e`

## pseudocode

```c
__int64 __fastcall ThreadSafeHashMap_Insert(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  unsigned int v5; // edi
  __int64 v6; // rax
  __int64 v7; // rbp
  __int64 v8; // rax
  __int64 v9; // rcx
  _QWORD *i; // r14
  __int64 v12; // rcx

  v3 = a1 + 48;
  v5 = 0;
  if ( *(_QWORD *)(a1 + 88) != GetCurrentThreadId() && (unsigned int)_Pump_BeginDeferringHelper(v3) )
    _Pump_BeginDeferring(v3);
  v6 = HashMap_Find(a1, a2);
  v7 = v6;
  if ( !v6 )
  {
    if ( !(unsigned int)TryAcquireWrite(a1 + 96) )
      QueueAcquireWrite(a1 + 96);
    for ( i = *(_QWORD **)(a1 + 64); ; i = (_QWORD *)*i )
    {
      if ( !i )
      {
        _InterlockedExchange64((volatile __int64 *)(a2 + 16), 0);
        Pump_Queue(v3, a2 + 8);
        goto LABEL_20;
      }
      if ( (*(unsigned int (__fastcall **)(_QWORD *, __int64))(a1 + 112))(i - 1, a2) )
        break;
    }
    _m_prefetchw(i + 1);
    v12 = i[1];
    if ( v12 == 3 )
    {
      _InterlockedCompareExchange64(i + 1, 0, 3);
LABEL_32:
      (*(void (__fastcall **)(__int64))(a1 + 120))(a2);
      goto LABEL_20;
    }
    if ( v12 )
    {
      if ( v12 == 2 )
      {
        _InterlockedExchange64(i + 1, 1);
        Pump_Dequeue(v3, i);
        goto LABEL_32;
      }
    }
    else
    {
      v5 = 11;
    }
LABEL_20:
    v9 = a1 + 96;
    goto LABEL_21;
  }
  _m_prefetchw((const void *)(v6 + 16));
  v8 = *(_QWORD *)(v6 + 16);
  if ( v8 != 1 )
  {
    if ( v8 != 2 )
      goto LABEL_22;
    if ( !(unsigned int)TryAcquireWrite(a1 + 96) )
      QueueAcquireWrite(a1 + 96);
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v7 + 16), 1, 2) == 2 )
    {
      Pump_Dequeue(v3, v7 + 8);
      (*(void (__fastcall **)(__int64))(a1 + 120))(a2);
    }
    v9 = a1 + 96;
LABEL_21:
    ReadWriteLock_ReleaseWrite(v9);
    goto LABEL_22;
  }
  v5 = 11;
LABEL_22:
  if ( *(_QWORD *)(v3 + 40) != GetCurrentThreadId() && (unsigned int)_Pump_EndDeferringHelper(v3) )
    _Pump_EndDeferring(v3);
  return v5;
}

```

## disassembly

```asm
0x18003f270  push    rbx
0x18003f272  push    rbp
0x18003f273  push    rsi
0x18003f274  push    rdi
0x18003f275  push    r12
0x18003f277  push    r13
0x18003f279  push    r14
0x18003f27b  push    r15
0x18003f27d  sub     rsp, 28h
0x18003f281  mov     r15, rdx
0x18003f284  lea     rbx, [rcx+30h]
0x18003f288  mov     rsi, rcx
0x18003f28b  xor     edi, edi
0x18003f28d  call    cs:__imp_GetCurrentThreadId
0x18003f293  mov     eax, eax
0x18003f295  cmp     [rbx+28h], rax
0x18003f299  jz      short loc_18003F2AF
0x18003f29b  mov     rcx, rbx
0x18003f29e  call    __Pump_BeginDeferringHelper
0x18003f2a3  test    eax, eax
0x18003f2a5  jz      short loc_18003F2AF
0x18003f2a7  mov     rcx, rbx
0x18003f2aa  call    __Pump_BeginDeferring
0x18003f2af  mov     rdx, r15
0x18003f2b2  mov     rcx, rsi
0x18003f2b5  call    HashMap_Find
0x18003f2ba  mov     rbp, rax
0x18003f2bd  test    rax, rax
0x18003f2c0  jz      short loc_18003F32A
0x18003f2c2  prefetchw byte ptr [rax+10h]
0x18003f2c6  mov     rax, [rax+10h]
0x18003f2ca  mov     r13d, 1
0x18003f2d0  cmp     rax, r13
0x18003f2d3  jnz     short loc_18003F2DE
0x18003f2d5  lea     edi, [r13+0Ah]
0x18003f2d9  jmp     loc_18003F37E
0x18003f2de  cmp     rax, 2
0x18003f2e2  jnz     loc_18003F37E
0x18003f2e8  lea     r14, [rsi+60h]
0x18003f2ec  mov     rcx, r14
0x18003f2ef  call    TryAcquireWrite
0x18003f2f4  test    eax, eax
0x18003f2f6  jnz     short loc_18003F300
0x18003f2f8  mov     rcx, r14
0x18003f2fb  call    QueueAcquireWrite
0x18003f300  mov     eax, 2
0x18003f305  lock cmpxchg [rbp+10h], r13
0x18003f30b  jnz     short loc_18003F325
0x18003f30d  lea     rdx, [rbp+8]
0x18003f311  mov     rcx, rbx
0x18003f314  call    Pump_Dequeue
0x18003f319  mov     rax, [rsi+78h]
0x18003f31d  mov     rcx, r15
0x18003f320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f325  mov     rcx, r14
0x18003f328  jmp     short loc_18003F379
0x18003f32a  lea     r12, [rsi+60h]
0x18003f32e  mov     rcx, r12
0x18003f331  call    TryAcquireWrite
0x18003f336  test    eax, eax
0x18003f338  jnz     short loc_18003F342
0x18003f33a  mov     rcx, r12
0x18003f33d  call    QueueAcquireWrite
0x18003f342  mov     r14, [rsi+40h]
0x18003f346  jmp     short loc_18003F35F
0x18003f348  mov     rax, [rsi+70h]
0x18003f34c  lea     rcx, [r14-8]
0x18003f350  mov     rdx, r15
0x18003f353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f358  test    eax, eax
0x18003f35a  jnz     short loc_18003F3B3
0x18003f35c  mov     r14, [r14]
0x18003f35f  test    r14, r14
0x18003f362  jnz     short loc_18003F348
0x18003f364  xor     eax, eax
0x18003f366  lea     rdx, [r15+8]
0x18003f36a  xchg    rax, [r15+10h]
0x18003f36e  mov     rcx, rbx
0x18003f371  call    Pump_Queue
0x18003f376  mov     rcx, r12
0x18003f379  call    ReadWriteLock_ReleaseWrite
0x18003f37e  call    cs:__imp_GetCurrentThreadId
0x18003f384  mov     edx, eax
0x18003f386  cmp     [rbx+28h], rdx
0x18003f38a  jz      short loc_18003F3A0
0x18003f38c  mov     rcx, rbx
0x18003f38f  call    __Pump_EndDeferringHelper
0x18003f394  test    eax, eax
0x18003f396  jz      short loc_18003F3A0
0x18003f398  mov     rcx, rbx
0x18003f39b  call    __Pump_EndDeferring
0x18003f3a0  mov     eax, edi
0x18003f3a2  add     rsp, 28h
0x18003f3a6  pop     r15
0x18003f3a8  pop     r14
0x18003f3aa  pop     r13
0x18003f3ac  pop     r12
0x18003f3ae  pop     rdi
0x18003f3af  pop     rsi
0x18003f3b0  pop     rbp
0x18003f3b1  pop     rbx
0x18003f3b2  retn
0x18003f3b3  prefetchw byte ptr [r14+8]
0x18003f3b8  mov     rcx, [r14+8]
0x18003f3bc  mov     eax, 3
0x18003f3c1  cmp     rcx, rax
0x18003f3c4  jnz     short loc_18003F3D0
0x18003f3c6  xor     ecx, ecx
0x18003f3c8  lock cmpxchg [r14+8], rcx
0x18003f3ce  jmp     short loc_18003F3F3
0x18003f3d0  test    rcx, rcx
0x18003f3d3  jnz     short loc_18003F3DA
0x18003f3d5  lea     edi, [rcx+0Bh]
0x18003f3d8  jmp     short loc_18003F376
0x18003f3da  cmp     rcx, 2
0x18003f3de  jnz     short loc_18003F376
0x18003f3e0  lea     r13d, [rcx-1]
0x18003f3e4  mov     rdx, r14
0x18003f3e7  xchg    r13, [r14+8]
0x18003f3eb  mov     rcx, rbx
0x18003f3ee  call    Pump_Dequeue
0x18003f3f3  mov     rax, [rsi+78h]
0x18003f3f7  mov     rcx, r15
0x18003f3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3ff  jmp     loc_18003F376
```
