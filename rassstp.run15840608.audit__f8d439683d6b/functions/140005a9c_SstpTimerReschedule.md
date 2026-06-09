# SstpTimerReschedule

- ea: `0x140005a9c`
- end: `0x140005bab`
- name: `SstpTimerReschedule`
- size: `271`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140016414`
- `0x1400165a0`
- `0x140016734`
- `0x1400169a4`
- `0x140016e84`
- `0x140016f4c`
- `0x14001707c`
- `0x140017204`

## callees

- `0x1400054c4`
- `0x140005a9c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005acd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005acd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005b8d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005b8d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005ae0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005ae0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005b7b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005b7b`
- `NETIO!RtlIndicateTimerWheelEntryTimerStart` at `0x140005b6b`
- `NETIO!RtlIndicateTimerWheelEntryTimerStart` at `0x140005b6b`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x140005b34`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x140005b34`

## pseudocode

```c
void __fastcall SstpTimerReschedule(__int64 a1, __int64 a2, __int64 a3, char a4, int a5, char a6)
{
  __int64 v6; // rbx
  KIRQL v11; // r13
  int v12; // r8d
  bool v13; // zf
  char v14; // [rsp+88h] [rbp+20h] BYREF

  v6 = *(_QWORD *)(a1 + 16);
  v14 = 0;
  v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 128));
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 48));
  v12 = 1000 * a5;
  v13 = a6 == 0;
  *(_QWORD *)(a1 + 32) = a2;
  *(_BYTE *)(a1 + 24) = a4;
  *(_QWORD *)(a1 + 40) = a3;
  *(_DWORD *)(a1 + 28) = v12;
  *(_BYTE *)(a1 + 25) = 1;
  if ( v13 )
  {
    *(_DWORD *)(a1 + 76) = 0;
    RtlCleanupTimerWheelEntry(v6 + 152, a1 + 56, &v14);
  }
  if ( (unsigned __int8)RtlStartTimerWheelEntryTimer(
                          a1 + 56,
                          *(_DWORD *)(a1 + 28) % Period,
                          *(_DWORD *)(v6 + 156) + *(_DWORD *)(a1 + 28) / Period) )
    RtlIndicateTimerWheelEntryTimerStart(v6 + 152, a1 + 56);
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 48));
  KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 128), v11);
}

```

## disassembly

```asm
0x140005a9c  mov     rax, rsp
0x140005a9f  push    rbx
0x140005aa0  push    rbp
0x140005aa1  push    rsi
0x140005aa2  push    rdi
0x140005aa3  push    r12
0x140005aa5  push    r13
0x140005aa7  push    r14
0x140005aa9  push    r15
0x140005aab  sub     rsp, 28h
0x140005aaf  mov     rbx, [rcx+10h]
0x140005ab3  mov     r14, rcx
0x140005ab6  mov     sil, r9b
0x140005ab9  mov     byte ptr [rax+20h], 0
0x140005abd  mov     rbp, r8
0x140005ac0  mov     rdi, rdx
0x140005ac3  lea     r15, [rbx+80h]
0x140005aca  mov     rcx, r15; SpinLock
0x140005acd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005ad4  nop     dword ptr [rax+rax+00h]
0x140005ad9  lea     rcx, [r14+30h]; SpinLock
0x140005add  mov     r13b, al
0x140005ae0  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140005ae7  nop     dword ptr [rax+rax+00h]
0x140005aec  imul    r8d, [rsp+68h+arg_20], 3E8h
0x140005af8  cmp     [rsp+68h+arg_28], 0
0x140005b00  mov     [r14+20h], rdi
0x140005b04  lea     rdi, [r14+38h]
0x140005b08  mov     [r14+18h], sil
0x140005b0c  mov     [r14+28h], rbp
0x140005b10  mov     [r14+1Ch], r8d
0x140005b14  mov     byte ptr [r14+19h], 1
0x140005b19  jnz     short loc_140005B40
0x140005b1b  lea     r8, [rsp+68h+arg_18]
0x140005b23  mov     dword ptr [rdi+14h], 0
0x140005b2a  mov     rdx, rdi
0x140005b2d  lea     rcx, [rbx+98h]
0x140005b34  call    cs:__imp_RtlCleanupTimerWheelEntry
0x140005b3b  nop     dword ptr [rax+rax+00h]
0x140005b40  mov     eax, [r14+1Ch]
0x140005b44  xor     edx, edx
0x140005b46  div     dword ptr cs:Period
0x140005b4c  mov     rcx, rdi
0x140005b4f  add     eax, [rbx+9Ch]
0x140005b55  mov     r8d, eax
0x140005b58  call    RtlStartTimerWheelEntryTimer
0x140005b5d  test    al, al
0x140005b5f  jz      short loc_140005B77
0x140005b61  mov     rdx, rdi
0x140005b64  lea     rcx, [rbx+98h]
0x140005b6b  call    cs:__imp_RtlIndicateTimerWheelEntryTimerStart
0x140005b72  nop     dword ptr [rax+rax+00h]
0x140005b77  lea     rcx, [r14+30h]; SpinLock
0x140005b7b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140005b82  nop     dword ptr [rax+rax+00h]
0x140005b87  mov     dl, r13b; NewIrql
0x140005b8a  mov     rcx, r15; SpinLock
0x140005b8d  call    cs:__imp_KeReleaseSpinLock
0x140005b94  nop     dword ptr [rax+rax+00h]
0x140005b99  add     rsp, 28h
0x140005b9d  pop     r15
0x140005b9f  pop     r14
0x140005ba1  pop     r13
0x140005ba3  pop     r12
0x140005ba5  pop     rdi
0x140005ba6  pop     rsi
0x140005ba7  pop     rbp
0x140005ba8  pop     rbx
0x140005ba9  retn
```
