# FIPfBlockedOpInsert

- ea: `0x140016788`
- end: `0x140016894`
- name: `FIPfBlockedOpInsert`
- size: `268`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140010350`
- `0x140015a48`
- `0x140015d3c`
- `0x14001606c`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x140003d80`
- `0x140016788`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400167b9`
- `ntoskrnl!KeInitializeEvent` at `0x1400167b9`

## pseudocode

```c
void __fastcall FIPfBlockedOpInsert(__int64 a1, _DWORD *a2, struct _KEVENT *a3)
{
  struct _KEVENT **v6; // rax
  struct _LIST_ENTRY ***v7; // rdx
  struct _LIST_ENTRY *v8; // [rsp+30h] [rbp+8h]

  memset(a3, 0, 0xD8u);
  KeInitializeEvent(a3 + 2, NotificationEvent, 0);
  HIDWORD(v8) = _InterlockedIncrement(&dword_140009640);
  LODWORD(v8) = ((MEMORY[0xFFFFF78000000004] * MEMORY[0xFFFFF78000000324]) << 8)
              + ((MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24);
  a3[1].Header.WaitListHead.Flink = v8;
  v6 = *(struct _KEVENT ***)(a1 + 8);
  if ( *v6 != (struct _KEVENT *)a1
    || (*(_QWORD *)&a3->Header.Lock = a1,
        a3->Header.WaitListHead.Flink = (struct _LIST_ENTRY *)v6,
        *v6 = a3,
        *(_QWORD *)(a1 + 8) = a3,
        ++*a2,
        FILockExclusiveAcquire((__int64)&qword_140009578),
        v7 = (struct _LIST_ENTRY ***)qword_140009588,
        *(__int64 **)qword_140009588 != &qword_140009580) )
  {
    __fastfail(3u);
  }
  a3->Header.WaitListHead.Blink = (struct _LIST_ENTRY *)&qword_140009580;
  *(_QWORD *)&a3[1].Header.Lock = v7;
  *v7 = &a3->Header.WaitListHead.Blink;
  ++dword_140009590;
  qword_140009588 = (__int64)&a3->Header.WaitListHead.Blink;
  FILockExclusiveRelease((__int64)&qword_140009578);
  _InterlockedIncrement(&dword_1400097F0);
}

```

## disassembly

```asm
0x140016788  mov     [rsp+arg_8], rbx
0x14001678d  mov     [rsp+arg_10], rsi
0x140016792  push    rdi
0x140016793  sub     rsp, 20h
0x140016797  mov     rbx, r8
0x14001679a  mov     rsi, rdx
0x14001679d  mov     rdi, rcx
0x1400167a0  xor     edx, edx; Val
0x1400167a2  mov     rcx, rbx; void *
0x1400167a5  mov     r8d, 0D8h; Size
0x1400167ab  call    memset
0x1400167b0  lea     rcx, [rbx+30h]; Event
0x1400167b4  xor     r8d, r8d; State
0x1400167b7  xor     edx, edx; Type
0x1400167b9  call    cs:__imp_KeInitializeEvent
0x1400167c0  nop     dword ptr [rax+rax+00h]
0x1400167c5  mov     eax, 1
0x1400167ca  lock xadd cs:dword_140009640, eax
0x1400167d2  inc     eax
0x1400167d4  mov     rcx, 0FFFFF78000000320h
0x1400167de  mov     dword ptr [rsp+28h+arg_0+4], eax
0x1400167e2  mov     rcx, [rcx]
0x1400167e5  mov     eax, ds:0FFFFF78000000004h
0x1400167ee  mov     edx, ecx
0x1400167f0  mov     r8d, eax
0x1400167f3  imul    r8, rdx
0x1400167f7  shr     rcx, 20h
0x1400167fb  imul    ecx, eax
0x1400167fe  shr     r8, 18h
0x140016802  shl     ecx, 8
0x140016805  add     r8d, ecx
0x140016808  mov     dword ptr [rsp+28h+arg_0], r8d
0x14001680d  mov     rax, [rsp+28h+arg_0]
0x140016812  mov     [rbx+20h], rax
0x140016816  mov     rax, [rdi+8]
0x14001681a  cmp     [rax], rdi
0x14001681d  jnz     short loc_14001688D
0x14001681f  mov     [rbx], rdi
0x140016822  lea     rcx, qword_140009578
0x140016829  mov     [rbx+8], rax
0x14001682d  mov     [rax], rbx
0x140016830  mov     [rdi+8], rbx
0x140016834  inc     dword ptr [rsi]
0x140016836  call    FILockExclusiveAcquire
0x14001683b  mov     rdx, cs:qword_140009588
0x140016842  lea     rcx, qword_140009580
0x140016849  cmp     [rdx], rcx
0x14001684c  jnz     short loc_14001688D
0x14001684e  lea     rax, [rbx+10h]
0x140016852  mov     [rax], rcx
0x140016855  lea     rcx, qword_140009578
0x14001685c  mov     [rax+8], rdx
0x140016860  mov     [rdx], rax
0x140016863  inc     cs:dword_140009590
0x140016869  mov     cs:qword_140009588, rax
0x140016870  call    FILockExclusiveRelease
0x140016875  lock inc cs:dword_1400097F0
0x14001687c  mov     rbx, [rsp+28h+arg_8]
0x140016881  mov     rsi, [rsp+28h+arg_10]
0x140016886  add     rsp, 20h
0x14001688a  pop     rdi
0x14001688b  retn
0x14001688d  mov     ecx, 3
0x140016892  int     29h; Win8: RtlFailFast(ecx)
```
