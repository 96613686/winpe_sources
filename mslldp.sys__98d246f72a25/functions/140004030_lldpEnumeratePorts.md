# lldpEnumeratePorts

- ea: `0x140004030`
- end: `0x1400040fc`
- name: `lldpEnumeratePorts`
- size: `204`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000ef10`
- `0x14000fdd0`

## callees

- `0x140004030`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004054`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004054`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400040d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400040d5`

## pseudocode

```c
__int64 __fastcall lldpEnumeratePorts(__int64 a1, unsigned __int64 a2, _QWORD *a3)
{
  unsigned int v4; // ebx
  KIRQL v7; // al
  struct _LIST_ENTRY *Flink; // r9
  signed __int32 Flink_high; // eax
  signed __int32 v10; // ett
  signed __int32 v11; // eax
  signed __int32 v12; // eax
  __int64 v13; // rdx

  *a3 = 0;
  v4 = 0;
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.AlignmentRequirement);
  Flink = WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink;
  for ( LOBYTE(WPP_MAIN_CB.DeviceQueue.Type) = v7; Flink; Flink = Flink[2].Flink )
  {
    _m_prefetchw((char *)&Flink[3].Flink + 4);
    Flink_high = HIDWORD(Flink[3].Flink);
    do
    {
      v10 = Flink_high;
      Flink_high = _InterlockedCompareExchange((volatile signed __int32 *)&Flink[3].Flink + 1, Flink_high, Flink_high);
    }
    while ( v10 != Flink_high );
    if ( Flink_high == 5 || (v11 = Flink_high - 3) == 0 || (v12 = v11 - 1) == 0 || v12 == 2 )
    {
      if ( v4 < a2 )
      {
        v13 = 2LL * v4;
        *(_QWORD *)(a1 + 8 * v13) = Flink[7].Blink;
        *(_QWORD *)(a1 + 8 * v13 + 8) = HIDWORD(Flink[8].Flink);
      }
      ++v4;
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.AlignmentRequirement, WPP_MAIN_CB.DeviceQueue.Type);
  *a3 = v4;
  return a2 < v4 ? 0xC0000023 : 0;
}

```

## disassembly

```asm
0x140004030  push    rbx
0x140004032  push    rbp
0x140004033  push    rsi
0x140004034  push    rdi
0x140004035  push    r14
0x140004037  sub     rsp, 20h
0x14000403b  mov     rbp, rcx
0x14000403e  xor     r14d, r14d
0x140004041  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; SpinLock
0x140004048  mov     [r8], r14
0x14000404b  mov     ebx, r14d
0x14000404e  mov     rsi, r8
0x140004051  mov     rdi, rdx
0x140004054  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000405b  nop     dword ptr [rax+rax+00h]
0x140004060  mov     r9, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x140004067  mov     byte ptr cs:WPP_MAIN_CB.DeviceQueue.Type, al
0x14000406d  test    r9, r9
0x140004070  jz      short loc_1400040C7
0x140004072  prefetchw byte ptr [r9+34h]
0x140004077  mov     eax, [r9+34h]
0x14000407b  mov     ecx, eax
0x14000407d  lock cmpxchg [r9+34h], ecx
0x140004083  jnz     short loc_14000407B
0x140004085  cmp     eax, 5
0x140004088  jz      short loc_140004099
0x14000408a  sub     eax, 3
0x14000408d  jz      short loc_140004099
0x14000408f  sub     eax, 1
0x140004092  jz      short loc_140004099
0x140004094  cmp     eax, 2
0x140004097  jnz     short loc_1400040BE
0x140004099  mov     edx, ebx
0x14000409b  cmp     rdx, rdi
0x14000409e  jnb     short loc_1400040BC
0x1400040a0  mov     rax, [r9+78h]
0x1400040a4  add     rdx, rdx
0x1400040a7  mov     [rbp+rdx*8+0], rax
0x1400040ac  mov     eax, [r9+84h]
0x1400040b3  mov     [rbp+rdx*8+8], eax
0x1400040b7  mov     [rbp+rdx*8+0Ch], r14d
0x1400040bc  inc     ebx
0x1400040be  mov     r9, [r9+20h]
0x1400040c2  test    r9, r9
0x1400040c5  jnz     short loc_140004072
0x1400040c7  movzx   edx, byte ptr cs:WPP_MAIN_CB.DeviceQueue.Type; NewIrql
0x1400040ce  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; SpinLock
0x1400040d5  call    cs:__imp_KeReleaseSpinLock
0x1400040dc  nop     dword ptr [rax+rax+00h]
0x1400040e1  mov     eax, ebx
0x1400040e3  cmp     rdi, rax
0x1400040e6  mov     [rsi], rax
0x1400040e9  sbb     eax, eax
0x1400040eb  and     eax, 0C0000023h
0x1400040f0  add     rsp, 20h
0x1400040f4  pop     r14
0x1400040f6  pop     rdi
0x1400040f7  pop     rsi
0x1400040f8  pop     rbp
0x1400040f9  pop     rbx
0x1400040fa  retn
```
