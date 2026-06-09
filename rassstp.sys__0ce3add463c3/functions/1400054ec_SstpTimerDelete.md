# SstpTimerDelete

- ea: `0x1400054ec`
- end: `0x1400055f2`
- name: `SstpTimerDelete`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140016cf0`

## callees

- `0x1400054ec`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000551a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000551a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400055cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400055cd`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005533`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005543`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005533`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005543`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400055a3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400055b2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400055a3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400055b2`
- `NETIO!RtlReturnTimerWheelEntry` at `0x140005562`
- `NETIO!RtlReturnTimerWheelEntry` at `0x140005562`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x14000557a`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x14000557a`

## pseudocode

```c
void __fastcall SstpTimerDelete(KSPIN_LOCK *a1, char a2)
{
  KSPIN_LOCK v2; // rdi
  KIRQL v3; // bp
  KSPIN_LOCK v6; // rdx
  KSPIN_LOCK **v7; // rax
  char v8; // [rsp+78h] [rbp+10h] BYREF

  v2 = a1[2];
  v3 = 0;
  v8 = 0;
  if ( !a2 )
    v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 976));
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v2 + 128));
  KeAcquireSpinLockAtDpcLevel(a1 + 6);
  if ( a2 )
    RtlReturnTimerWheelEntry(v2 + 152, a1 + 7);
  RtlCleanupTimerWheelEntry(v2 + 152, a1 + 7, &v8);
  v6 = *a1;
  if ( *(KSPIN_LOCK **)(*a1 + 8) != a1 || (v7 = (KSPIN_LOCK **)a1[1], *v7 != a1) )
    __fastfail(3u);
  *v7 = (KSPIN_LOCK *)v6;
  *(_QWORD *)(v6 + 8) = v7;
  KeReleaseSpinLockFromDpcLevel(a1 + 6);
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v2 + 128));
  if ( !a2 )
    KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 976), v3);
}

```

## disassembly

```asm
0x1400054ec  push    rbx
0x1400054ee  push    rbp
0x1400054ef  push    rsi
0x1400054f0  push    rdi
0x1400054f1  push    r12
0x1400054f3  push    r13
0x1400054f5  push    r14
0x1400054f7  push    r15
0x1400054f9  sub     rsp, 28h
0x1400054fd  mov     rdi, [rcx+10h]
0x140005501  xor     bpl, bpl
0x140005504  mov     [rsp+68h+arg_8], bpl
0x140005509  mov     sil, dl
0x14000550c  mov     rbx, rcx
0x14000550f  test    dl, dl
0x140005511  jnz     short loc_140005529
0x140005513  lea     rcx, [rdi+3D0h]; SpinLock
0x14000551a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005521  nop     dword ptr [rax+rax+00h]
0x140005526  mov     bpl, al
0x140005529  lea     r12, [rdi+80h]
0x140005530  mov     rcx, r12; SpinLock
0x140005533  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000553a  nop     dword ptr [rax+rax+00h]
0x14000553f  lea     rcx, [rbx+30h]; SpinLock
0x140005543  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000554a  nop     dword ptr [rax+rax+00h]
0x14000554f  lea     r15, [rdi+98h]
0x140005556  test    sil, sil
0x140005559  jz      short loc_14000556E
0x14000555b  lea     rdx, [rbx+38h]
0x14000555f  mov     rcx, r15
0x140005562  call    cs:__imp_RtlReturnTimerWheelEntry
0x140005569  nop     dword ptr [rax+rax+00h]
0x14000556e  lea     r8, [rsp+68h+arg_8]
0x140005573  mov     rcx, r15
0x140005576  lea     rdx, [rbx+38h]
0x14000557a  call    cs:__imp_RtlCleanupTimerWheelEntry
0x140005581  nop     dword ptr [rax+rax+00h]
0x140005586  mov     rdx, [rbx]
0x140005589  cmp     [rdx+8], rbx
0x14000558d  jnz     short loc_1400055EB
0x14000558f  mov     rax, [rbx+8]
0x140005593  cmp     [rax], rbx
0x140005596  jnz     short loc_1400055EB
0x140005598  mov     [rax], rdx
0x14000559b  lea     rcx, [rbx+30h]; SpinLock
0x14000559f  mov     [rdx+8], rax
0x1400055a3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400055aa  nop     dword ptr [rax+rax+00h]
0x1400055af  mov     rcx, r12; SpinLock
0x1400055b2  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400055b9  nop     dword ptr [rax+rax+00h]
0x1400055be  test    sil, sil
0x1400055c1  jnz     short loc_1400055D9
0x1400055c3  lea     rcx, [rdi+3D0h]; SpinLock
0x1400055ca  mov     dl, bpl; NewIrql
0x1400055cd  call    cs:__imp_KeReleaseSpinLock
0x1400055d4  nop     dword ptr [rax+rax+00h]
0x1400055d9  add     rsp, 28h
0x1400055dd  pop     r15
0x1400055df  pop     r14
0x1400055e1  pop     r13
0x1400055e3  pop     r12
0x1400055e5  pop     rdi
0x1400055e6  pop     rsi
0x1400055e7  pop     rbp
0x1400055e8  pop     rbx
0x1400055e9  retn
0x1400055eb  mov     ecx, 3
0x1400055f0  int     29h; Win8: RtlFailFast(ecx)
```
