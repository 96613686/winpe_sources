# HidpAsynchronousCallCompletion

- ea: `0x180012090`
- end: `0x180012156`
- name: `HidpAsynchronousCallCompletion`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003f40`
- `0x180010814`
- `0x180012090`
- `0x18001cabc`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1800120e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800120e5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800120b5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800120b5`

## pseudocode

```c
__int64 __fastcall HidpAsynchronousCallCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  KSPIN_LOCK *v3; // rbp
  char v6; // si
  KIRQL v7; // r14
  bool v8; // zf

  v3 = (KSPIN_LOCK *)(a3 + 384);
  v6 = 0;
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 384));
  if ( *(int *)(a3 + 1860) <= 0 )
    HidpDbgBreak("Invalid InFlightIoCount");
  v8 = (*(_DWORD *)(a3 + 1860))-- == 1;
  if ( v8 && *(_BYTE *)(a3 + 1724) )
  {
    *(_BYTE *)(a3 + 1724) = 0;
    v6 = 1;
  }
  KeReleaseSpinLock(v3, v7);
  if ( v6 )
    HIDSM_AddHidsmEvent(a3, 2022);
  HidpFdoReleasePoFxPowerReferenceWithTag(a3, 8);
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  return 0;
}

```

## disassembly

```asm
0x180012090  mov     [rsp+arg_0], rbx
0x180012095  mov     [rsp+arg_10], rbp
0x18001209a  push    rsi
0x18001209b  push    rdi
0x18001209c  push    r14
0x18001209e  sub     rsp, 20h
0x1800120a2  lea     rbp, [r8+180h]
0x1800120a9  mov     rbx, r8
0x1800120ac  mov     rcx, rbp; SpinLock
0x1800120af  mov     rdi, rdx
0x1800120b2  xor     sil, sil
0x1800120b5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1800120bc  nop     dword ptr [rax+rax+00h]
0x1800120c1  cmp     dword ptr [rbx+744h], 0
0x1800120c8  mov     r14b, al
0x1800120cb  jle     short loc_18001212D
0x1800120cd  sub     dword ptr [rbx+744h], 1
0x1800120d4  jnz     short loc_1800120DF
0x1800120d6  cmp     [rbx+6BCh], sil
0x1800120dd  jnz     short loc_18001213B
0x1800120df  mov     dl, r14b; NewIrql
0x1800120e2  mov     rcx, rbp; SpinLock
0x1800120e5  call    cs:__imp_KeReleaseSpinLock
0x1800120ec  nop     dword ptr [rax+rax+00h]
0x1800120f1  test    sil, sil
0x1800120f4  jnz     short loc_180012147
0x1800120f6  mov     r8, rdi
0x1800120f9  mov     edx, 8
0x1800120fe  mov     rcx, rbx
0x180012101  call    HidpFdoReleasePoFxPowerReferenceWithTag
0x180012106  cmp     byte ptr [rdi+41h], 0
0x18001210a  jz      short loc_180012117
0x18001210c  mov     rax, [rdi+0B8h]
0x180012113  or      byte ptr [rax+3], 1
0x180012117  mov     rbx, [rsp+38h+arg_0]
0x18001211c  xor     eax, eax
0x18001211e  mov     rbp, [rsp+38h+arg_10]
0x180012123  add     rsp, 20h
0x180012127  pop     r14
0x180012129  pop     rdi
0x18001212a  pop     rsi
0x18001212b  retn
0x18001212d  lea     rcx, aInvalidInfligh; "Invalid InFlightIoCount"
0x180012134  call    HidpDbgBreak
0x180012139  jmp     short loc_1800120CD
0x18001213b  mov     [rbx+6BCh], sil
0x180012142  mov     sil, 1
0x180012145  jmp     short loc_1800120DF
0x180012147  mov     edx, 7E6h
0x18001214c  mov     rcx, rbx
0x18001214f  call    HIDSM_AddHidsmEvent
0x180012154  jmp     short loc_1800120F6
```
