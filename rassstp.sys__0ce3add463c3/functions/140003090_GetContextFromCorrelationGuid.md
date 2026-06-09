# GetContextFromCorrelationGuid

- ea: `0x140003090`
- end: `0x14000317c`
- name: `GetContextFromCorrelationGuid`
- size: `236`
- prototype: `__int64 __fastcall(void *Source1)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400133f0`

## callees

- `0x140003090`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400030ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400030ac`
- `ntoskrnl!RtlCompareMemory` at `0x140003118`
- `ntoskrnl!RtlCompareMemory` at `0x140003118`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003161`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003161`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400030e9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400030e9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000312d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003144`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000312d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003144`

## pseudocode

```c
volatile signed __int32 *__fastcall GetContextFromCorrelationGuid(void *Source1)
{
  KIRQL v2; // bp
  _QWORD *i; // rdi
  volatile signed __int32 *v4; // rbx

  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 59);
  for ( i = (_QWORD *)*((_QWORD *)SstpGlobals + 60); ; i = (_QWORD *)*i )
  {
    v4 = 0;
    if ( i == (_QWORD *)((char *)SstpGlobals + 480) )
      break;
    v4 = (volatile signed __int32 *)(i - 2);
    KeAcquireSpinLockAtDpcLevel(i + 2);
    if ( i[2638] && *((_BYTE *)v4 + 21132) && RtlCompareMemory(Source1, (const void *)(v4 + 121), 0x10u) == 16 )
    {
      _InterlockedIncrement(v4);
      KeReleaseSpinLockFromDpcLevel(i + 2);
      break;
    }
    KeReleaseSpinLockFromDpcLevel(i + 2);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 59, v2);
  return v4;
}

```

## disassembly

```asm
0x140003090  push    rbx
0x140003092  push    rbp
0x140003093  push    rsi
0x140003094  push    rdi
0x140003095  push    r14
0x140003097  sub     rsp, 20h
0x14000309b  mov     r14, rcx
0x14000309e  mov     rcx, cs:SstpGlobals
0x1400030a5  add     rcx, 1D8h; SpinLock
0x1400030ac  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400030b3  nop     dword ptr [rax+rax+00h]
0x1400030b8  mov     rdx, cs:SstpGlobals
0x1400030bf  mov     bpl, al
0x1400030c2  mov     rdi, [rdx+1E0h]
0x1400030c9  mov     rdx, cs:SstpGlobals
0x1400030d0  xor     ebx, ebx
0x1400030d2  add     rdx, 1E0h
0x1400030d9  cmp     rdi, rdx
0x1400030dc  jz      short loc_140003150
0x1400030de  lea     rbx, [rdi-10h]
0x1400030e2  lea     rsi, [rbx+20h]
0x1400030e6  mov     rcx, rsi; SpinLock
0x1400030e9  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400030f0  nop     dword ptr [rax+rax+00h]
0x1400030f5  cmp     qword ptr [rbx+5280h], 0
0x1400030fd  jz      short loc_14000312A
0x1400030ff  cmp     byte ptr [rbx+528Ch], 0
0x140003106  jz      short loc_14000312A
0x140003108  lea     rdx, [rbx+1E4h]; Source2
0x14000310f  mov     r8d, 10h; Length
0x140003115  mov     rcx, r14; Source1
0x140003118  call    cs:__imp_RtlCompareMemory
0x14000311f  nop     dword ptr [rax+rax+00h]
0x140003124  cmp     rax, 10h
0x140003128  jz      short loc_14000313E
0x14000312a  mov     rcx, rsi; SpinLock
0x14000312d  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140003134  nop     dword ptr [rax+rax+00h]
0x140003139  mov     rdi, [rdi]
0x14000313c  jmp     short loc_1400030C9
0x14000313e  lock inc dword ptr [rbx]
0x140003141  mov     rcx, rsi; SpinLock
0x140003144  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000314b  nop     dword ptr [rax+rax+00h]
0x140003150  mov     rcx, cs:SstpGlobals
0x140003157  mov     dl, bpl; NewIrql
0x14000315a  add     rcx, 1D8h; SpinLock
0x140003161  call    cs:__imp_KeReleaseSpinLock
0x140003168  nop     dword ptr [rax+rax+00h]
0x14000316d  mov     rax, rbx
0x140003170  add     rsp, 20h
0x140003174  pop     r14
0x140003176  pop     rdi
0x140003177  pop     rsi
0x140003178  pop     rbp
0x140003179  pop     rbx
0x14000317a  retn
```
