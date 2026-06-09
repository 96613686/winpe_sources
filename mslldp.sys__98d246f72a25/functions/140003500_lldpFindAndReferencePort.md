# lldpFindAndReferencePort

- ea: `0x140003500`
- end: `0x14000357c`
- name: `lldpFindAndReferencePort`
- size: `124`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ec14`
- `0x14000ec80`
- `0x14000ece8`
- `0x14000efd0`
- `0x14000fdd0`
- `0x140010150`

## callees

- `0x140003500`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003514`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003514`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003561`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003561`

## pseudocode

```c
struct _LIST_ENTRY *__fastcall lldpFindAndReferencePort(__int64 a1)
{
  KIRQL v2; // al
  struct _LIST_ENTRY *Flink; // rbx

  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.AlignmentRequirement);
  Flink = WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink;
  LOBYTE(WPP_MAIN_CB.DeviceQueue.Type) = v2;
  while ( Flink )
  {
    if ( Flink[7].Blink == *(struct _LIST_ENTRY **)a1 && HIDWORD(Flink[8].Flink) == *(_DWORD *)(a1 + 8) )
    {
      _InterlockedIncrement((volatile signed __int32 *)&Flink[3]);
      break;
    }
    Flink = Flink[2].Flink;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.AlignmentRequirement, WPP_MAIN_CB.DeviceQueue.Type);
  return Flink;
}

```

## disassembly

```asm
0x140003500  mov     [rsp+arg_0], rbx
0x140003505  push    rdi
0x140003506  sub     rsp, 20h
0x14000350a  mov     rdi, rcx
0x14000350d  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; SpinLock
0x140003514  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000351b  nop     dword ptr [rax+rax+00h]
0x140003520  mov     rbx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x140003527  mov     byte ptr cs:WPP_MAIN_CB.DeviceQueue.Type, al
0x14000352d  nop     dword ptr [rax]
0x140003530  test    rbx, rbx
0x140003533  jz      short loc_140003553
0x140003535  mov     rax, [rdi]
0x140003538  cmp     [rbx+78h], rax
0x14000353c  jz      short loc_140003544
0x14000353e  mov     rbx, [rbx+20h]
0x140003542  jmp     short loc_140003530
0x140003544  mov     eax, [rdi+8]
0x140003547  cmp     [rbx+84h], eax
0x14000354d  jnz     short loc_14000353E
0x14000354f  lock inc dword ptr [rbx+30h]
0x140003553  movzx   edx, byte ptr cs:WPP_MAIN_CB.DeviceQueue.Type; NewIrql
0x14000355a  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; SpinLock
0x140003561  call    cs:__imp_KeReleaseSpinLock
0x140003568  nop     dword ptr [rax+rax+00h]
0x14000356d  mov     rax, rbx
0x140003570  mov     rbx, [rsp+28h+arg_0]
0x140003575  add     rsp, 20h
0x140003579  pop     rdi
0x14000357a  retn
```
