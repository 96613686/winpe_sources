# QuicWorkerMoveConnection

- ea: `0x140022528`
- end: `0x14002263e`
- name: `QuicWorkerMoveConnection`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000edc0`

## callees

- `0x14000c6f0`
- `0x140010820`
- `0x140022528`
- `0x14002e7a4`
- `0x14003fd84`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140022554`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140022554`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022609`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022609`
- `HAL!KeQueryPerformanceCounter` at `0x140022573`
- `HAL!KeQueryPerformanceCounter` at `0x140022573`

## pseudocode

```c
void __fastcall QuicWorkerMoveConnection(__int64 a1, __int64 a2, char a3)
{
  KSPIN_LOCK *v3; // rbp
  char IsIdle; // r14
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 *v9; // rdx
  __int64 v10; // rcx
  __int64 **v11; // rax
  __int64 **v12; // rax

  v3 = (KSPIN_LOCK *)(a1 + 160);
  *(_BYTE *)(a1 + 168) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 160));
  IsIdle = QuicWorkerIsIdle(a1);
  PerformanceCounter = KeQueryPerformanceCounter(0);
  *(_DWORD *)(a2 + 3672) = ((__int64 (__fastcall *)(_QWORD))QuicTimePlatToUs64)((LARGE_INTEGER)PerformanceCounter.QuadPart);
  v9 = (__int64 *)(a2 + 32);
  if ( a3 )
  {
    v10 = **(_QWORD **)(a1 + 192);
    v11 = *(__int64 ***)(v10 + 8);
    *v9 = v10;
    *(_QWORD *)(a2 + 40) = v11;
    *v11 = v9;
    *(_QWORD *)(v10 + 8) = v9;
    *(_QWORD *)(a1 + 192) = v9;
    *(_BYTE *)(a2 + 277) |= 4u;
  }
  else
  {
    v10 = a1 + 176;
    v12 = *(__int64 ***)(a1 + 184);
    *v9 = a1 + 176;
    *(_QWORD *)(a2 + 40) = v12;
    *v12 = v9;
    *(_QWORD *)(a1 + 184) = v9;
  }
  if ( byte_14005C489 < 0 )
    McTemplateU0pq_EtwWriteTransfer(v10, (const EVENT_DESCRIPTOR *)QuicConnScheduleState, a2, 1);
  _InterlockedIncrement((volatile signed __int32 *)(a2 + 240));
  KeReleaseSpinLock(v3, *(_BYTE *)(a1 + 168));
  if ( IsIdle )
    QuicWorkerThreadWake(a1);
}

```

## disassembly

```asm
0x140022528  mov     rax, rsp
0x14002252b  mov     [rax+8], rbx
0x14002252f  mov     [rax+10h], rbp
0x140022533  mov     [rax+18h], rsi
0x140022537  mov     [rax+20h], rdi
0x14002253b  push    r14
0x14002253d  sub     rsp, 20h
0x140022541  lea     rbp, [rcx+0A0h]
0x140022548  mov     rdi, rcx
0x14002254b  mov     rcx, rbp; SpinLock
0x14002254e  mov     bl, r8b
0x140022551  mov     rsi, rdx
0x140022554  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002255b  nop     dword ptr [rax+rax+00h]
0x140022560  mov     rcx, rdi
0x140022563  mov     [rdi+0A8h], al
0x140022569  call    QuicWorkerIsIdle
0x14002256e  xor     ecx, ecx; PerformanceFrequency
0x140022570  mov     r14b, al
0x140022573  call    cs:__imp_KeQueryPerformanceCounter
0x14002257a  nop     dword ptr [rax+rax+00h]
0x14002257f  mov     rcx, rax
0x140022582  call    QuicTimePlatToUs64
0x140022587  mov     [rsi+0E58h], eax
0x14002258d  lea     rdx, [rsi+20h]
0x140022591  test    bl, bl
0x140022593  jz      short loc_1400225C1
0x140022595  mov     rax, [rdi+0C0h]
0x14002259c  mov     rcx, [rax]
0x14002259f  mov     rax, [rcx+8]
0x1400225a3  mov     [rdx], rcx
0x1400225a6  mov     [rdx+8], rax
0x1400225aa  mov     [rax], rdx
0x1400225ad  mov     [rcx+8], rdx
0x1400225b1  mov     [rdi+0C0h], rdx
0x1400225b8  or      byte ptr [rsi+115h], 4
0x1400225bf  jmp     short loc_1400225DA
0x1400225c1  lea     rcx, [rdi+0B0h]
0x1400225c8  mov     rax, [rcx+8]
0x1400225cc  mov     [rdx], rcx
0x1400225cf  mov     [rdx+8], rax
0x1400225d3  mov     [rax], rdx
0x1400225d6  mov     [rcx+8], rdx
0x1400225da  mov     al, cs:byte_14005C489
0x1400225e0  test    al, al
0x1400225e2  jns     short loc_1400225F9
0x1400225e4  mov     r9d, 1
0x1400225ea  lea     rdx, QuicConnScheduleState
0x1400225f1  mov     r8, rsi
0x1400225f4  call    McTemplateU0pq_EtwWriteTransfer
0x1400225f9  lock inc dword ptr [rsi+0F0h]
0x140022600  mov     dl, [rdi+0A8h]; NewIrql
0x140022606  mov     rcx, rbp; SpinLock
0x140022609  call    cs:__imp_KeReleaseSpinLock
0x140022610  nop     dword ptr [rax+rax+00h]
0x140022615  test    r14b, r14b
0x140022618  jz      short loc_140022622
0x14002261a  mov     rcx, rdi
0x14002261d  call    QuicWorkerThreadWake
0x140022622  mov     rbx, [rsp+28h+arg_0]
0x140022627  mov     rbp, [rsp+28h+arg_8]
0x14002262c  mov     rsi, [rsp+28h+arg_10]
0x140022631  mov     rdi, [rsp+28h+arg_18]
0x140022636  add     rsp, 20h
0x14002263a  pop     r14
0x14002263c  retn
```
