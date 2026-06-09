# PcpLineSignalExternalEvent

- ea: `0x140008290`
- end: `0x140008433`
- name: `PcpLineSignalExternalEvent`
- size: `419`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140003ab0`
- `0x140005c10`
- `0x140007f90`
- `0x1400085c0`
- `0x140009b80`
- `0x140009fe0`
- `0x14000cce0`

## callees

- `0x140008290`
- `0x14000a380`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x140008422`
- `NDIS!NdisReleaseRWLock` at `0x140008422`
- `NDIS!NdisAcquireRWLockWrite` at `0x140008402`
- `NDIS!NdisAcquireRWLockWrite` at `0x140008402`
- `HAL!KeQueryPerformanceCounter` at `0x140008321`
- `HAL!KeQueryPerformanceCounter` at `0x140008321`

## pseudocode

```c
void __fastcall PcpLineSignalExternalEvent(__int64 a1, unsigned int a2)
{
  __int64 v3; // rbx
  unsigned __int64 v5; // rsi
  LARGE_INTEGER v6; // rax
  union _LARGE_INTEGER v7; // r8
  LARGE_INTEGER v8; // r9
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  unsigned __int8 v11; // al
  unsigned __int8 v12; // al
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+40h] [rbp+8h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+48h] [rbp+10h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v3 = MEMORY[0xFFFFF78000000008];
  v5 = *(_QWORD *)QosgTimerTable + ((unsigned __int64)a2 << 7);
  if ( MEMORY[0xFFFFF78000000008] != *(_QWORD *)(v5 + 8) )
  {
    PerformanceFrequency.QuadPart = 0;
    v6 = KeQueryPerformanceCounter(&PerformanceFrequency);
    v7 = PerformanceFrequency;
    v8 = v6;
    v9 = *(unsigned __int8 *)(v5 + 112);
    v10 = ((1000000 * HIDWORD(v6.QuadPart) / (unsigned __int64)PerformanceFrequency.QuadPart) << 32)
        + (1000000LL * v6.LowPart
         + ((1000000 * HIDWORD(v6.QuadPart) % (unsigned __int64)PerformanceFrequency.QuadPart) << 32))
        / PerformanceFrequency.QuadPart;
    if ( (_BYTE)v9 )
      v11 = v9 - 1;
    else
      v11 = 2;
    if ( (__int64)(*(_QWORD *)(v5 + 8LL * v11 + 64) - v10) > 0 )
    {
      *(_QWORD *)(v5 + 8 * v9 + 16) = *(_QWORD *)(v5 + 8LL * v11 + 16);
      *(_QWORD *)(v5 + 8 * v9 + 40) = *(_QWORD *)(v5 + 8LL * v11 + 40);
      *(_QWORD *)(v5 + 8 * v9 + 64) = *(_QWORD *)(v5 + 8LL * v11 + 64);
      v10 = *(_QWORD *)(v5 + 8LL * v11 + 64);
    }
    else
    {
      *(LARGE_INTEGER *)(v5 + 8 * v9 + 16) = v8;
      *(union _LARGE_INTEGER *)(v5 + 8 * v9 + 40) = v7;
      *(_QWORD *)(v5 + 8 * v9 + 64) = v10;
    }
    *(_QWORD *)(v5 + 8 * v9 + 88) = v3;
    v12 = *(_BYTE *)(v5 + 112) + 1;
    *(_QWORD *)v5 = v10;
    *(_QWORD *)(v5 + 8) = v3;
    *(_BYTE *)(v5 + 112) = v12 % 3u;
  }
  if ( ((__int64)(*(_QWORD *)(a1 + 192) - *(_QWORD *)v5) <= 0 || (__int64)(*(_QWORD *)(a1 + 184) - *(_QWORD *)v5) <= 0)
    && !_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 152), 1u) )
  {
    NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 16), &LockState, 0);
    QosLineSignalExternalEvent(a1 + 24, a2);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 16), &LockState);
  }
}

```

## disassembly

```asm
0x140008290  mov     [rsp+arg_10], rbx
0x140008295  push    rbp
0x140008296  push    rsi
0x140008297  push    rdi
0x140008298  sub     rsp, 20h
0x14000829c  xor     eax, eax
0x14000829e  mov     esi, edx
0x1400082a0  mov     word ptr [rsp+38h+LockState.OldIrql], ax
0x1400082a5  mov     rbx, 0FFFFF78000000008h
0x1400082af  mov     [rsp+38h+LockState.Flags], al
0x1400082b3  mov     rdi, rcx
0x1400082b6  mov     rax, cs:QosgTimerTable
0x1400082bd  shl     rsi, 7
0x1400082c1  mov     rbx, [rbx]
0x1400082c4  mov     ebp, edx
0x1400082c6  add     rsi, [rax]
0x1400082c9  cmp     rbx, [rsi+8]
0x1400082cd  jnz     short loc_140008313
0x1400082cf  mov     rcx, [rsi]
0x1400082d2  mov     rax, [rdi+0C0h]
0x1400082d9  sub     rax, rcx
0x1400082dc  test    rax, rax
0x1400082df  jle     short loc_1400082F0
0x1400082e1  mov     rax, [rdi+0B8h]
0x1400082e8  sub     rax, rcx
0x1400082eb  test    rax, rax
0x1400082ee  jg      short loc_140008305
0x1400082f0  mov     eax, 1
0x1400082f5  lock xadd [rdi+98h], eax
0x1400082fd  test    eax, eax
0x1400082ff  jz      loc_1400083F6
0x140008305  mov     rbx, [rsp+38h+arg_10]
0x14000830a  add     rsp, 20h
0x14000830e  pop     rdi
0x14000830f  pop     rsi
0x140008310  pop     rbp
0x140008311  retn
0x140008313  lea     rcx, [rsp+38h+PerformanceFrequency]; PerformanceFrequency
0x140008318  mov     qword ptr [rsp+38h+PerformanceFrequency], 0
0x140008321  call    cs:__imp_KeQueryPerformanceCounter
0x140008328  nop     dword ptr [rax+rax+00h]
0x14000832d  mov     r8, qword ptr [rsp+38h+PerformanceFrequency]
0x140008332  xor     edx, edx
0x140008334  mov     r9, rax
0x140008337  shr     rax, 20h
0x14000833b  imul    r10, rax, 0F4240h
0x140008342  mov     ecx, r9d
0x140008345  mov     rax, r10
0x140008348  div     r8
0x14000834b  mov     rax, rdx
0x14000834e  shl     rax, 20h
0x140008352  imul    rdx, rcx, 0F4240h
0x140008359  add     rax, rdx
0x14000835c  xor     edx, edx
0x14000835e  div     r8
0x140008361  xor     edx, edx
0x140008363  mov     rcx, rax
0x140008366  mov     rax, r10
0x140008369  div     r8
0x14000836c  movzx   edx, byte ptr [rsi+70h]
0x140008370  shl     rax, 20h
0x140008374  add     rcx, rax
0x140008377  test    dl, dl
0x140008379  jz      short loc_1400083CD
0x14000837b  lea     eax, [rdx-1]
0x14000837e  movzx   r10d, al
0x140008382  mov     rax, [rsi+r10*8+40h]
0x140008387  sub     rax, rcx
0x14000838a  test    rax, rax
0x14000838d  jg      short loc_1400083D1
0x14000838f  mov     [rsi+rdx*8+10h], r9
0x140008394  mov     [rsi+rdx*8+28h], r8
0x140008399  mov     [rsi+rdx*8+40h], rcx
0x14000839e  mov     [rsi+rdx*8+58h], rbx
0x1400083a3  movzx   eax, byte ptr [rsi+70h]
0x1400083a7  inc     al
0x1400083a9  mov     [rsi], rcx
0x1400083ac  movzx   r8d, al
0x1400083b0  mov     eax, 0AAAAAAABh
0x1400083b5  mul     r8d
0x1400083b8  mov     [rsi+8], rbx
0x1400083bc  shr     edx, 1
0x1400083be  lea     eax, [rdx+rdx*2]
0x1400083c1  sub     r8d, eax
0x1400083c4  mov     [rsi+70h], r8b
0x1400083c8  jmp     loc_1400082CF
0x1400083cd  mov     al, 2
0x1400083cf  jmp     short loc_14000837E
0x1400083d1  mov     rax, [rsi+r10*8+10h]
0x1400083d6  mov     [rsi+rdx*8+10h], rax
0x1400083db  mov     rax, [rsi+r10*8+28h]
0x1400083e0  mov     [rsi+rdx*8+28h], rax
0x1400083e5  mov     rax, [rsi+r10*8+40h]
0x1400083ea  mov     [rsi+rdx*8+40h], rax
0x1400083ef  mov     rcx, [rsi+r10*8+40h]
0x1400083f4  jmp     short loc_14000839E
0x1400083f6  mov     rcx, [rdi+10h]; Lock
0x1400083fa  lea     rdx, [rsp+38h+LockState]; LockState
0x1400083ff  xor     r8d, r8d; Flags
0x140008402  call    cs:__imp_NdisAcquireRWLockWrite
0x140008409  nop     dword ptr [rax+rax+00h]
0x14000840e  lea     rcx, [rdi+18h]
0x140008412  mov     edx, ebp
0x140008414  call    QosLineSignalExternalEvent
0x140008419  mov     rcx, [rdi+10h]; Lock
0x14000841d  lea     rdx, [rsp+38h+LockState]; LockState
0x140008422  call    cs:__imp_NdisReleaseRWLock
0x140008429  nop     dword ptr [rax+rax+00h]
0x14000842e  jmp     loc_140008305
```
