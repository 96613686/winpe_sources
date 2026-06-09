# PcpCreateTimerUnits

- ea: `0x14000c800`
- end: `0x14000c8c0`
- name: `PcpCreateTimerUnits`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000cba0`

## callees

- `0x14000c800`
- `0x14000c8fc`
- `0x14000d248`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8a8`
- `ntoskrnl!ExAllocatePool2` at `0x14000c82f`
- `ntoskrnl!ExAllocatePool2` at `0x14000c82f`

## pseudocode

```c
__int64 PcpCreateTimerUnits()
{
  int v0; // edi
  char *Pool2; // rsi
  __int64 i; // rbx
  __int64 j; // rbp

  v0 = 0;
  if ( !PcgTimerUnits )
  {
    Pool2 = (char *)ExAllocatePool2(64, 192LL * (unsigned int)PcgNumberOfProcessors, 1635017552);
    if ( Pool2 )
    {
      for ( i = 0; (unsigned int)i < PcgNumberOfProcessors; i = (unsigned int)(i + 1) )
      {
        v0 = PcpInitializeTimerUnit(&Pool2[192 * i], i);
        if ( v0 < 0 )
          goto LABEL_9;
      }
      if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&PcgTimerUnits, (signed __int64)Pool2, 0) )
        return (unsigned int)v0;
LABEL_9:
      for ( j = 0; (unsigned int)j < (unsigned int)i; j = (unsigned int)(j + 1) )
        PcpUninitializeTimerUnit(&Pool2[192 * j]);
      ExFreePoolWithTag(Pool2, 0x61746350u);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14000c800  push    rbx
0x14000c802  push    rbp
0x14000c803  push    rsi
0x14000c804  push    rdi
0x14000c805  sub     rsp, 28h
0x14000c809  xor     edi, edi
0x14000c80b  cmp     cs:PcgTimerUnits, rdi
0x14000c812  jnz     loc_14000C8B4
0x14000c818  mov     eax, cs:PcgNumberOfProcessors
0x14000c81e  lea     ecx, [rdi+40h]
0x14000c821  mov     r8d, 61746350h
0x14000c827  lea     rdx, [rax+rax*2]
0x14000c82b  shl     rdx, 6
0x14000c82f  call    cs:__imp_ExAllocatePool2
0x14000c836  nop     dword ptr [rax+rax+00h]
0x14000c83b  mov     rsi, rax
0x14000c83e  test    rax, rax
0x14000c841  jnz     short loc_14000C84A
0x14000c843  mov     edi, 0C000009Ah
0x14000c848  jmp     short loc_14000C8B4
0x14000c84a  xor     ebx, ebx
0x14000c84c  cmp     ebx, cs:PcgNumberOfProcessors
0x14000c852  jnb     short loc_14000C870
0x14000c854  lea     rcx, [rbx+rbx*2]
0x14000c858  mov     edx, ebx; ProcIndex
0x14000c85a  shl     rcx, 6
0x14000c85e  add     rcx, rsi; void *
0x14000c861  call    PcpInitializeTimerUnit
0x14000c866  mov     edi, eax
0x14000c868  test    eax, eax
0x14000c86a  js      short loc_14000C87D
0x14000c86c  inc     ebx
0x14000c86e  jmp     short loc_14000C84C
0x14000c870  xor     eax, eax
0x14000c872  lock cmpxchg cs:PcgTimerUnits, rsi
0x14000c87b  jz      short loc_14000C8B4
0x14000c87d  xor     ebp, ebp
0x14000c87f  test    ebx, ebx
0x14000c881  jz      short loc_14000C8A0
0x14000c883  lea     rcx, ds:0[rbp*2]
0x14000c88b  add     rcx, rbp
0x14000c88e  shl     rcx, 6
0x14000c892  add     rcx, rsi
0x14000c895  call    PcpUninitializeTimerUnit
0x14000c89a  inc     ebp
0x14000c89c  cmp     ebp, ebx
0x14000c89e  jb      short loc_14000C883
0x14000c8a0  mov     edx, 61746350h; Tag
0x14000c8a5  mov     rcx, rsi; P
0x14000c8a8  call    cs:__imp_ExFreePoolWithTag
0x14000c8af  nop     dword ptr [rax+rax+00h]
0x14000c8b4  mov     eax, edi
0x14000c8b6  add     rsp, 28h
0x14000c8ba  pop     rdi
0x14000c8bb  pop     rsi
0x14000c8bc  pop     rbp
0x14000c8bd  pop     rbx
0x14000c8be  retn
```
