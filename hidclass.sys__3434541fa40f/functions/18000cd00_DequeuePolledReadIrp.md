# DequeuePolledReadIrp

- ea: `0x18000cd00`
- end: `0x18000cda3`
- name: `DequeuePolledReadIrp`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000adc0`
- `0x180023924`

## callees

- `0x18000cd00`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x18000cd71`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000cd71`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000cd1e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000cd1e`

## pseudocode

```c
_QWORD *__fastcall DequeuePolledReadIrp(__int64 a1)
{
  KSPIN_LOCK *v1; // rsi
  _QWORD *v3; // rbx
  KIRQL v4; // cl
  _QWORD **v5; // r8
  _QWORD *v6; // rdx
  _QWORD *v7; // rax

  v1 = (KSPIN_LOCK *)(a1 + 232);
  v3 = 0;
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 232));
  v5 = (_QWORD **)(a1 + 216);
  while ( 1 )
  {
    v6 = *v5;
    if ( *v5 == v5 )
      break;
    if ( (_QWORD **)v6[1] != v5 || (v7 = (_QWORD *)*v6, *(_QWORD **)(*v6 + 8LL) != v6) )
      __fastfail(3u);
    *v5 = v7;
    v3 = v6 - 21;
    v7[1] = v5;
    if ( _InterlockedExchange64(v6 - 8, 0) )
    {
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 16));
      if ( v6 != (_QWORD *)168 )
        break;
    }
    else
    {
      v6[1] = v6;
      v3 = 0;
      *v6 = v6;
    }
  }
  KeReleaseSpinLock(v1, v4);
  return v3;
}

```

## disassembly

```asm
0x18000cd00  mov     [rsp+arg_0], rbx
0x18000cd05  mov     [rsp+arg_8], rsi
0x18000cd0a  push    rdi
0x18000cd0b  sub     rsp, 20h
0x18000cd0f  lea     rsi, [rcx+0E8h]
0x18000cd16  mov     rdi, rcx
0x18000cd19  mov     rcx, rsi; SpinLock
0x18000cd1c  xor     ebx, ebx
0x18000cd1e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18000cd25  nop     dword ptr [rax+rax+00h]
0x18000cd2a  mov     cl, al
0x18000cd2c  lea     r8, [rdi+0D8h]
0x18000cd33  mov     rdx, [r8]
0x18000cd36  cmp     rdx, r8
0x18000cd39  jz      short loc_18000CD6C
0x18000cd3b  cmp     [rdx+8], r8
0x18000cd3f  jnz     short loc_18000CD9C
0x18000cd41  mov     rax, [rdx]
0x18000cd44  cmp     [rax+8], rdx
0x18000cd48  jnz     short loc_18000CD9C
0x18000cd4a  mov     [r8], rax
0x18000cd4d  lea     rbx, [rdx-0A8h]
0x18000cd54  mov     [rax+8], r8
0x18000cd58  xor     eax, eax
0x18000cd5a  xchg    rax, [rbx+68h]
0x18000cd5e  test    rax, rax
0x18000cd61  jz      short loc_18000CD91
0x18000cd63  lock dec dword ptr [rdi+10h]
0x18000cd67  test    rbx, rbx
0x18000cd6a  jz      short loc_18000CD33
0x18000cd6c  mov     dl, cl; NewIrql
0x18000cd6e  mov     rcx, rsi; SpinLock
0x18000cd71  call    cs:__imp_KeReleaseSpinLock
0x18000cd78  nop     dword ptr [rax+rax+00h]
0x18000cd7d  mov     rsi, [rsp+28h+arg_8]
0x18000cd82  mov     rax, rbx
0x18000cd85  mov     rbx, [rsp+28h+arg_0]
0x18000cd8a  add     rsp, 20h
0x18000cd8e  pop     rdi
0x18000cd8f  retn
0x18000cd91  mov     [rdx+8], rdx
0x18000cd95  xor     ebx, ebx
0x18000cd97  mov     [rdx], rdx
0x18000cd9a  jmp     short loc_18000CD33
0x18000cd9c  mov     ecx, 3
0x18000cda1  int     29h; Win8: RtlFailFast(ecx)
```
