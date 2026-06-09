# lldpAcquireInterLock

- ea: `0x140012568`
- end: `0x1400125ea`
- name: `lldpAcquireInterLock`
- size: `130`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400041fc`
- `0x14000458c`
- `0x140006310`
- `0x1400063bc`
- `0x14000edc0`
- `0x140011cac`

## callees

- `0x140012568`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400125b4`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400125b4`

## pseudocode

```c
signed __int64 __fastcall lldpAcquireInterLock(__int64 a1, char a2)
{
  struct _KTHREAD *CurrentThread; // rdi
  signed __int64 result; // rax
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp+8h] BYREF

  CurrentThread = KeGetCurrentThread();
  Interval.QuadPart = -10000;
  while ( 1 )
  {
    result = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8), (signed __int64)CurrentThread, 0);
    if ( !result )
      break;
    if ( a2 && (struct _KTHREAD *)result == CurrentThread )
    {
      ++*(_DWORD *)a1;
      return result;
    }
    KeDelayExecutionThread(0, 0, &Interval);
    if ( Interval.QuadPart > -10000000 )
      Interval.QuadPart *= 2LL;
  }
  return result;
}

```

## disassembly

```asm
0x140012568  mov     rax, rsp
0x14001256b  mov     [rax+10h], rbx
0x14001256f  mov     [rax+18h], rsi
0x140012573  push    rdi
0x140012574  sub     rsp, 20h
0x140012578  mov     qword ptr [rax+8], 0
0x140012580  mov     sil, dl
0x140012583  mov     rdi, gs:188h
0x14001258c  mov     rbx, rcx
0x14001258f  mov     qword ptr [rax+8], 0FFFFFFFFFFFFD8F0h
0x140012597  xor     eax, eax
0x140012599  lock cmpxchg [rbx+8], rdi
0x14001259f  jz      short loc_1400125D9
0x1400125a1  test    sil, sil
0x1400125a4  jz      short loc_1400125AB
0x1400125a6  cmp     rax, rdi
0x1400125a9  jz      short loc_1400125D7
0x1400125ab  lea     r8, [rsp+28h+Interval]; Interval
0x1400125b0  xor     edx, edx; Alertable
0x1400125b2  xor     ecx, ecx; WaitMode
0x1400125b4  call    cs:__imp_KeDelayExecutionThread
0x1400125bb  nop     dword ptr [rax+rax+00h]
0x1400125c0  mov     rax, qword ptr [rsp+28h+Interval]
0x1400125c5  cmp     rax, 0FFFFFFFFFF676980h
0x1400125cb  jle     short loc_140012597
0x1400125cd  add     rax, rax
0x1400125d0  mov     qword ptr [rsp+28h+Interval], rax
0x1400125d5  jmp     short loc_140012597
0x1400125d7  inc     dword ptr [rbx]
0x1400125d9  mov     rbx, [rsp+28h+arg_8]
0x1400125de  mov     rsi, [rsp+28h+arg_10]
0x1400125e3  add     rsp, 20h
0x1400125e7  pop     rdi
0x1400125e8  retn
```
