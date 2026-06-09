# BwcCreateTimerUnits

- ea: `0x1400120ac`
- end: `0x14001216c`
- name: `BwcCreateTimerUnits`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140012f34`

## callees

- `0x14000721c`
- `0x1400120ac`
- `0x14001351c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140012154`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012154`
- `ntoskrnl!ExAllocatePool2` at `0x1400120db`
- `ntoskrnl!ExAllocatePool2` at `0x1400120db`

## pseudocode

```c
__int64 BwcCreateTimerUnits()
{
  int v0; // edi
  char *Pool2; // rsi
  __int64 i; // rbx
  __int64 j; // rbp

  v0 = 0;
  if ( !BwcTimerUnits )
  {
    Pool2 = (char *)ExAllocatePool2(64, 192LL * (unsigned int)BwcNumberOfProcessors, 1635022658);
    if ( Pool2 )
    {
      for ( i = 0; (unsigned int)i < BwcNumberOfProcessors; i = (unsigned int)(i + 1) )
      {
        v0 = BwcInitializeTimerUnit(&Pool2[192 * i], i);
        if ( v0 < 0 )
          goto LABEL_9;
      }
      if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&BwcTimerUnits, (signed __int64)Pool2, 0) )
        return (unsigned int)v0;
LABEL_9:
      for ( j = 0; (unsigned int)j < (unsigned int)i; j = (unsigned int)(j + 1) )
        BwcUninitializeTimerUnit(&Pool2[192 * j]);
      ExFreePoolWithTag(Pool2, 0x61747742u);
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
0x1400120ac  push    rbx
0x1400120ae  push    rbp
0x1400120af  push    rsi
0x1400120b0  push    rdi
0x1400120b1  sub     rsp, 28h
0x1400120b5  xor     edi, edi
0x1400120b7  cmp     cs:BwcTimerUnits, rdi
0x1400120be  jnz     loc_140012160
0x1400120c4  mov     eax, cs:BwcNumberOfProcessors
0x1400120ca  lea     ecx, [rdi+40h]
0x1400120cd  mov     r8d, 61747742h
0x1400120d3  lea     rdx, [rax+rax*2]
0x1400120d7  shl     rdx, 6
0x1400120db  call    cs:__imp_ExAllocatePool2
0x1400120e2  nop     dword ptr [rax+rax+00h]
0x1400120e7  mov     rsi, rax
0x1400120ea  test    rax, rax
0x1400120ed  jnz     short loc_1400120F6
0x1400120ef  mov     edi, 0C000009Ah
0x1400120f4  jmp     short loc_140012160
0x1400120f6  xor     ebx, ebx
0x1400120f8  cmp     ebx, cs:BwcNumberOfProcessors
0x1400120fe  jnb     short loc_14001211C
0x140012100  lea     rcx, [rbx+rbx*2]
0x140012104  mov     edx, ebx; ProcIndex
0x140012106  shl     rcx, 6
0x14001210a  add     rcx, rsi; void *
0x14001210d  call    BwcInitializeTimerUnit
0x140012112  mov     edi, eax
0x140012114  test    eax, eax
0x140012116  js      short loc_140012129
0x140012118  inc     ebx
0x14001211a  jmp     short loc_1400120F8
0x14001211c  xor     eax, eax
0x14001211e  lock cmpxchg cs:BwcTimerUnits, rsi
0x140012127  jz      short loc_140012160
0x140012129  xor     ebp, ebp
0x14001212b  test    ebx, ebx
0x14001212d  jz      short loc_14001214C
0x14001212f  lea     rcx, ds:0[rbp*2]
0x140012137  add     rcx, rbp
0x14001213a  shl     rcx, 6
0x14001213e  add     rcx, rsi
0x140012141  call    BwcUninitializeTimerUnit
0x140012146  inc     ebp
0x140012148  cmp     ebp, ebx
0x14001214a  jb      short loc_14001212F
0x14001214c  mov     edx, 61747742h; Tag
0x140012151  mov     rcx, rsi; P
0x140012154  call    cs:__imp_ExFreePoolWithTag
0x14001215b  nop     dword ptr [rax+rax+00h]
0x140012160  mov     eax, edi
0x140012162  add     rsp, 28h
0x140012166  pop     rdi
0x140012167  pop     rsi
0x140012168  pop     rbp
0x140012169  pop     rbx
0x14001216a  retn
```
