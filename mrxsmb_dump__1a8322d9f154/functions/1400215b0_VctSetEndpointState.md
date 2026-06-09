# VctSetEndpointState

- ea: `0x1400215b0`
- end: `0x1400216c5`
- name: `VctSetEndpointState`
- size: `277`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b4b0`
- `0x140011910`
- `0x140012650`
- `0x14001cf70`
- `0x140035f90`
- `0x140038158`
- `0x140042814`
- `0x140042b60`
- `0x140050fe0`
- `0x140051650`
- `0x140051b60`
- `0x1400539e0`
- `0x1400552f0`
- `0x1400585e0`
- `0x14008d030`
- `0x140091b60`

## callees

- `0x140004b90`
- `0x1400215b0`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x1400216b0`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400216b0`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140021657`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140021657`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002162b`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002162b`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400215e0`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400215e0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400215f0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400215f0`

## pseudocode

```c
__int64 __fastcall VctSetEndpointState(__int64 a1, __int32 a2, char a3)
{
  KIRQL v3; // r15
  __int64 *v4; // rsi
  __int64 v8; // rbx
  unsigned __int32 v9; // ebx
  __int64 v10; // rcx
  __int64 v12; // rsi

  v3 = 0;
  v4 = (__int64 *)(a1 + 24);
  if ( !a3 )
  {
    v8 = *v4;
    v3 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(*v4 + 1920));
    *(_DWORD *)(v8 + 2352) = (unsigned int)PsGetCurrentThreadId();
  }
  v9 = _InterlockedExchange((volatile __int32 *)(a1 + 12), a2);
  if ( a2 == 1 && v9 != 1 && ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 496)) )
  {
    v12 = *(_QWORD *)(a1 + 504);
    if ( v12 && _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 632), 0xFFFFFFFF) == 1 )
    {
      SmbCeDisconnectObjectLite(v12, 3221225996LL);
      *(_BYTE *)(v12 + 736) &= ~0x20u;
    }
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)(a1 + 496));
    v4 = (__int64 *)(a1 + 24);
  }
  if ( !a3 )
  {
    v10 = *v4;
    *(_DWORD *)(v10 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v10 + 1920), v3);
  }
  return v9;
}

```

## disassembly

```asm
0x1400215b0  mov     [rsp+arg_8], rbx
0x1400215b5  push    rbp
0x1400215b6  push    rsi
0x1400215b7  push    rdi
0x1400215b8  push    r14
0x1400215ba  push    r15
0x1400215bc  sub     rsp, 20h
0x1400215c0  xor     r15b, r15b
0x1400215c3  lea     rsi, [rcx+18h]
0x1400215c7  movzx   ebp, r8b
0x1400215cb  mov     r14d, edx
0x1400215ce  mov     rdi, rcx
0x1400215d1  test    r8b, r8b
0x1400215d4  jnz     short loc_140021602
0x1400215d6  mov     rbx, [rsi]
0x1400215d9  lea     rcx, [rbx+780h]; SpinLock
0x1400215e0  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400215e7  nop     dword ptr [rax+rax+00h]
0x1400215ec  movzx   r15d, al
0x1400215f0  call    cs:__imp_PsGetCurrentThreadId
0x1400215f7  nop     dword ptr [rax+rax+00h]
0x1400215fc  mov     [rbx+930h], eax
0x140021602  mov     ebx, r14d
0x140021605  xchg    ebx, [rdi+0Ch]
0x140021608  cmp     r14d, 1
0x14002160c  jz      short loc_14002164B
0x14002160e  test    bpl, bpl
0x140021611  jnz     short loc_140021637
0x140021613  mov     rcx, [rsi]
0x140021616  movzx   edx, r15b; OldIrql
0x14002161a  mov     dword ptr [rcx+930h], 0FFFFFFFFh
0x140021624  add     rcx, 780h; SpinLock
0x14002162b  call    cs:__imp_ExReleaseSpinLockExclusive
0x140021632  nop     dword ptr [rax+rax+00h]
0x140021637  mov     eax, ebx
0x140021639  mov     rbx, [rsp+48h+arg_8]
0x14002163e  add     rsp, 20h
0x140021642  pop     r15
0x140021644  pop     r14
0x140021646  pop     rdi
0x140021647  pop     rsi
0x140021648  pop     rbp
0x140021649  retn
0x14002164b  cmp     ebx, 1
0x14002164e  jz      short loc_14002160E
0x140021650  lea     rcx, [rdi+1F0h]; RunRef
0x140021657  call    cs:__imp_ExAcquireRundownProtection
0x14002165e  nop     dword ptr [rax+rax+00h]
0x140021663  test    al, al
0x140021665  jz      short loc_14002160E
0x140021667  mov     rsi, [rdi+1F8h]
0x14002166e  test    rsi, rsi
0x140021671  jz      short loc_1400216A9
0x140021673  mov     eax, 0FFFFFFFFh
0x140021678  lock xadd [rsi+278h], eax
0x140021680  cmp     eax, 1
0x140021683  jnz     short loc_1400216A9
0x140021685  mov     dword ptr [rsp+48h+arg_0], 0C000020Ch
0x14002168d  mov     rcx, rsi
0x140021690  mov     dword ptr [rsp+48h+arg_0+4], 0
0x140021698  mov     rdx, [rsp+48h+arg_0]
0x14002169d  call    SmbCeDisconnectObjectLite
0x1400216a2  and     byte ptr [rsi+2E0h], 0DFh
0x1400216a9  lea     rcx, [rdi+1F0h]; RunRef
0x1400216b0  call    cs:__imp_ExReleaseRundownProtection
0x1400216b7  nop     dword ptr [rax+rax+00h]
0x1400216bc  lea     rsi, [rdi+18h]
0x1400216c0  jmp     loc_14002160E
```
