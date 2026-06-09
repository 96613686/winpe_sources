# RemoveTqi

- ea: `0x14000f698`
- end: `0x14000f7bd`
- name: `RemoveTqi`
- size: `293`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x14000f008`
- `0x14000f2ec`
- `0x140013c74`
- `0x1400152b0`
- `0x140015de4`
- `0x140015fa8`
- `0x1400171e0`
- `0x1400175f0`
- `0x140017d90`

## callees

- `0x140004830`
- `0x14000f698`
- `0x14000fa20`
- `0x1400181a8`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000f74f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f79b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f74f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f79b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f6c3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f6c3`
- `NDIS!NdisCancelTimer` at `0x14000f6fc`
- `NDIS!NdisCancelTimer` at `0x14000f6fc`

## pseudocode

```c
char __fastcall RemoveTqi(__int64 a1, _QWORD *a2, unsigned int a3)
{
  KSPIN_LOCK *v6; // rsi
  KIRQL v7; // al
  char v8; // bp
  KIRQL v9; // dl
  _QWORD *v10; // rax
  _QWORD *v11; // rcx
  void (__fastcall *v12)(_QWORD *, _QWORD, _QWORD); // rax
  unsigned __int8 TimerCancelled; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    return 0;
  v6 = (KSPIN_LOCK *)(a1 + 48);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 48));
  *(_BYTE *)(a1 + 56) = v7;
  if ( (_QWORD *)*a2 == a2 || *(_BYTE *)(a1 + 40) )
  {
    v9 = v7;
    goto LABEL_18;
  }
  if ( a2 == *(_QWORD **)(a1 + 8) )
  {
    TimerCancelled = 0;
    v8 = 1;
    NdisCancelTimer((PNDIS_TIMER)(a1 + 64), &TimerCancelled);
    if ( !TimerCancelled )
    {
      v9 = *(_BYTE *)(a1 + 56);
LABEL_18:
      KeReleaseSpinLock(v6, v9);
      return 0;
    }
  }
  else
  {
    v8 = 0;
  }
  v10 = (_QWORD *)*a2;
  if ( *(_QWORD **)(*a2 + 8LL) != a2 || (v11 = (_QWORD *)a2[1], (_QWORD *)*v11 != a2) )
    __fastfail(3u);
  *v11 = v10;
  v10[1] = v11;
  a2[1] = a2;
  *a2 = a2;
  if ( v8 )
    SetTimer(a1, 0);
  KeReleaseSpinLock(v6, *(_BYTE *)(a1 + 56));
  v12 = (void (__fastcall *)(_QWORD *, _QWORD, _QWORD))a2[3];
  if ( a3 )
    v12(a2, a2[4], a3);
  else
    TimerQScheduleItem(a1, (_DWORD)a2, 0, (_DWORD)v12, a2[4]);
  return 1;
}

```

## disassembly

```asm
0x14000f698  mov     [rsp+arg_0], rbx
0x14000f69d  mov     [rsp+arg_10], rbp
0x14000f6a2  push    rsi
0x14000f6a3  push    rdi
0x14000f6a4  push    r14
0x14000f6a6  sub     rsp, 30h
0x14000f6aa  mov     r14d, r8d
0x14000f6ad  mov     rbx, rdx
0x14000f6b0  mov     rdi, rcx
0x14000f6b3  test    rdx, rdx
0x14000f6b6  jz      loc_14000F7A7
0x14000f6bc  lea     rsi, [rcx+30h]
0x14000f6c0  mov     rcx, rsi; SpinLock
0x14000f6c3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f6ca  nop     dword ptr [rax+rax+00h]
0x14000f6cf  mov     [rdi+38h], al
0x14000f6d2  cmp     [rbx], rbx
0x14000f6d5  jz      loc_14000F796
0x14000f6db  cmp     byte ptr [rdi+28h], 0
0x14000f6df  jnz     loc_14000F796
0x14000f6e5  cmp     rbx, [rdi+8]
0x14000f6e9  jnz     short loc_14000F717
0x14000f6eb  lea     rcx, [rdi+40h]; Timer
0x14000f6ef  mov     [rsp+48h+TimerCancelled], 0
0x14000f6f4  lea     rdx, [rsp+48h+TimerCancelled]; TimerCancelled
0x14000f6f9  mov     bpl, 1
0x14000f6fc  call    cs:__imp_NdisCancelTimer
0x14000f703  nop     dword ptr [rax+rax+00h]
0x14000f708  cmp     [rsp+48h+TimerCancelled], 0
0x14000f70d  jnz     short loc_14000F71A
0x14000f70f  mov     dl, [rdi+38h]
0x14000f712  jmp     loc_14000F798
0x14000f717  xor     bpl, bpl
0x14000f71a  mov     rax, [rbx]
0x14000f71d  cmp     [rax+8], rbx
0x14000f721  jnz     short loc_14000F78F
0x14000f723  mov     rcx, [rbx+8]
0x14000f727  cmp     [rcx], rbx
0x14000f72a  jnz     short loc_14000F78F
0x14000f72c  mov     [rcx], rax
0x14000f72f  mov     [rax+8], rcx
0x14000f733  mov     [rbx+8], rbx
0x14000f737  mov     [rbx], rbx
0x14000f73a  test    bpl, bpl
0x14000f73d  jz      short loc_14000F749
0x14000f73f  xor     edx, edx
0x14000f741  mov     rcx, rdi
0x14000f744  call    SetTimer
0x14000f749  mov     dl, [rdi+38h]; NewIrql
0x14000f74c  mov     rcx, rsi; SpinLock
0x14000f74f  call    cs:__imp_KeReleaseSpinLock
0x14000f756  nop     dword ptr [rax+rax+00h]
0x14000f75b  mov     rdx, [rbx+20h]
0x14000f75f  mov     rax, [rbx+18h]
0x14000f763  test    r14d, r14d
0x14000f766  jnz     short loc_14000F780
0x14000f768  mov     [rsp+48h+var_28], rdx
0x14000f76d  mov     r9, rax
0x14000f770  mov     rdx, rbx
0x14000f773  xor     r8d, r8d
0x14000f776  mov     rcx, rdi
0x14000f779  call    TimerQScheduleItem
0x14000f77e  jmp     short loc_14000F78B
0x14000f780  mov     r8d, r14d
0x14000f783  mov     rcx, rbx
0x14000f786  call    _guard_dispatch_icall
0x14000f78b  mov     al, 1
0x14000f78d  jmp     short loc_14000F7A9
0x14000f78f  mov     ecx, 3
0x14000f794  int     29h; Win8: RtlFailFast(ecx)
0x14000f796  mov     dl, al; NewIrql
0x14000f798  mov     rcx, rsi; SpinLock
0x14000f79b  call    cs:__imp_KeReleaseSpinLock
0x14000f7a2  nop     dword ptr [rax+rax+00h]
0x14000f7a7  xor     al, al
0x14000f7a9  mov     rbx, [rsp+48h+arg_0]
0x14000f7ae  mov     rbp, [rsp+48h+arg_10]
0x14000f7b3  add     rsp, 30h
0x14000f7b7  pop     r14
0x14000f7b9  pop     rdi
0x14000f7ba  pop     rsi
0x14000f7bb  retn
```
