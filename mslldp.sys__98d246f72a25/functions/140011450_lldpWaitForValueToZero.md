# lldpWaitForValueToZero

- ea: `0x140011450`
- end: `0x1400114bf`
- name: `lldpWaitForValueToZero`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140011390`

## callees

- `0x140011450`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140011489`
- `ntoskrnl!KeDelayExecutionThread` at `0x140011489`

## pseudocode

```c
__int64 __fastcall lldpWaitForValueToZero(_DWORD *a1)
{
  __int64 result; // rax
  int v3; // ett
  int v4; // ett
  union _LARGE_INTEGER Interval; // [rsp+38h] [rbp+10h] BYREF

  Interval.QuadPart = -10000;
  _m_prefetchw(a1);
  LODWORD(result) = *a1;
  do
  {
    v3 = result;
    result = (unsigned int)_InterlockedCompareExchange(a1, result, result);
  }
  while ( v3 != (_DWORD)result );
  while ( (_DWORD)result )
  {
    KeDelayExecutionThread(0, 0, &Interval);
    if ( Interval.QuadPart > -10000000 )
      Interval.QuadPart *= 2LL;
    _m_prefetchw(a1);
    LODWORD(result) = *a1;
    do
    {
      v4 = result;
      result = (unsigned int)_InterlockedCompareExchange(a1, result, result);
    }
    while ( v4 != (_DWORD)result );
  }
  return result;
}

```

## disassembly

```asm
0x140011450  push    rbx
0x140011452  sub     rsp, 20h
0x140011456  mov     rbx, rcx
0x140011459  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFFFD8F0h
0x140011462  prefetchw byte ptr [rcx]
0x140011465  mov     eax, [rcx]
0x140011467  mov     ecx, eax
0x140011469  lock cmpxchg [rbx], ecx
0x14001146d  jnz     short loc_140011467
0x14001146f  test    eax, eax
0x140011471  jnz     short loc_140011480
0x140011473  add     rsp, 20h
0x140011477  pop     rbx
0x140011478  retn
0x140011480  lea     r8, [rsp+28h+Interval]; Interval
0x140011485  xor     edx, edx; Alertable
0x140011487  xor     ecx, ecx; WaitMode
0x140011489  call    cs:__imp_KeDelayExecutionThread
0x140011490  nop     dword ptr [rax+rax+00h]
0x140011495  mov     rax, qword ptr [rsp+28h+Interval]
0x14001149a  cmp     rax, 0FFFFFFFFFF676980h
0x1400114a0  jg      short loc_1400114B5
0x1400114a2  prefetchw byte ptr [rbx]
0x1400114a5  mov     eax, [rbx]
0x1400114a7  mov     ecx, eax
0x1400114a9  lock cmpxchg [rbx], ecx
0x1400114ad  jnz     short loc_1400114A7
0x1400114af  test    eax, eax
0x1400114b1  jz      short loc_140011473
0x1400114b3  jmp     short loc_140011480
0x1400114b5  add     rax, rax
0x1400114b8  mov     qword ptr [rsp+28h+Interval], rax
0x1400114bd  jmp     short loc_1400114A2
```
