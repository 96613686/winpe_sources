# NbtDereferenceTracker

- ea: `0x140009e1c`
- end: `0x140009ed2`
- name: `NbtDereferenceTracker`
- size: `182`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x140006e2c`
- `0x140009844`
- `0x140009ee0`
- `0x14000cca0`
- `0x14000d9a0`
- `0x14000ebe0`
- `0x140019870`
- `0x14001ba80`
- `0x14001d580`
- `0x140028580`
- `0x14002919c`
- `0x14002e420`
- `0x14005006c`

## callees

- `0x140009e1c`
- `0x14000b810`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009e49`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009e49`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009e81`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009e81`

## pseudocode

```c
void __fastcall NbtDereferenceTracker(__int64 a1, char a2, int a3, __int64 a4)
{
  KIRQL v6; // si

  v6 = -1;
  if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_qddds(
      a1,
      0x54u,
      (ULONGLONG)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
      a1,
      *(_DWORD *)(a1 + 20),
      *(_DWORD *)(a1 + 20) - 1,
      a3,
      a4);
  if ( !a2 )
    v6 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF) == 1 )
    FreeTracker(a1, 4);
  if ( !a2 )
    KeReleaseSpinLock(&SpinLock, v6);
}

```

## disassembly

```asm
0x140009e1c  mov     [rsp+arg_0], rbx
0x140009e21  mov     [rsp+arg_8], rsi
0x140009e26  push    rdi
0x140009e27  sub     rsp, 40h
0x140009e2b  mov     dil, dl
0x140009e2e  mov     rbx, rcx
0x140009e31  mov     sil, 0FFh
0x140009e34  test    byte ptr cs:xmmword_140038420+9, 40h
0x140009e3b  jnz     short loc_140009E9E
0x140009e3d  test    dil, dil
0x140009e40  jnz     short loc_140009E58
0x140009e42  lea     rcx, SpinLock; SpinLock
0x140009e49  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009e50  nop     dword ptr [rax+rax+00h]
0x140009e55  mov     sil, al
0x140009e58  or      edx, 0FFFFFFFFh
0x140009e5b  lock xadd [rbx+14h], edx
0x140009e60  cmp     edx, 1
0x140009e63  jnz     short loc_140009E72
0x140009e65  mov     edx, 4
0x140009e6a  mov     rcx, rbx
0x140009e6d  call    FreeTracker
0x140009e72  test    dil, dil
0x140009e75  jnz     short loc_140009E8D
0x140009e77  mov     dl, sil; NewIrql
0x140009e7a  lea     rcx, SpinLock; SpinLock
0x140009e81  call    cs:__imp_KeReleaseSpinLock
0x140009e88  nop     dword ptr [rax+rax+00h]
0x140009e8d  mov     rbx, [rsp+48h+arg_0]
0x140009e92  mov     rsi, [rsp+48h+arg_8]
0x140009e97  add     rsp, 40h
0x140009e9b  pop     rdi
0x140009e9c  retn
0x140009e9e  mov     r10d, [rcx+14h]
0x140009ea2  mov     edx, 54h ; 'T'
0x140009ea7  mov     [rsp+48h+var_10], r9
0x140009eac  mov     r9, rbx
0x140009eaf  mov     [rsp+48h+var_18], r8d
0x140009eb4  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x140009ebb  lea     eax, [r10-1]
0x140009ebf  mov     [rsp+48h+var_20], eax
0x140009ec3  mov     [rsp+48h+var_28], r10d
0x140009ec8  call    WPP_SF_qddds
0x140009ecd  jmp     loc_140009E3D
```
