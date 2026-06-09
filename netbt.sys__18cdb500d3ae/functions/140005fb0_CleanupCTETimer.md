# CleanupCTETimer

- ea: `0x140005fb0`
- end: `0x140006076`
- name: `CleanupCTETimer`
- size: `198`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `10`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140003d04`
- `0x140005e60`
- `0x14000a7b0`
- `0x14000e408`
- `0x140015818`
- `0x14001a2b8`
- `0x14001c134`
- `0x14001f6dc`
- `0x140020900`
- `0x1400247f8`

## callees

- `0x140005fb0`
- `0x140006900`
- `0x140030f80`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006021`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006021`
- `ntoskrnl!KeSetEvent` at `0x140006068`
- `ntoskrnl!KeSetEvent` at `0x140006068`

## pseudocode

```c
__int64 __fastcall CleanupCTETimer(_QWORD *Entry)
{
  void (__fastcall *v1)(__int64, __int64, _QWORD); // rdi
  __int64 v3; // rsi
  __int64 v4; // rbp
  __int64 v5; // rcx
  _QWORD *v6; // rax
  PVOID *v7; // rcx

  v1 = (void (__fastcall *)(__int64, __int64, _QWORD))Entry[5];
  v3 = Entry[6];
  v4 = Entry[7];
  Entry[5] = 0;
  *((_BYTE *)Entry + 23) = 0;
  v5 = Entry[4];
  if ( v5 )
  {
    NBT_DEREFERENCE_DEVICE(v5, 2);
    Entry[4] = 0;
  }
  if ( v1 )
    v1(v3, v4, 0);
  v6 = (_QWORD *)*Entry;
  if ( *(_QWORD **)(*Entry + 8LL) != Entry || (v7 = (PVOID *)Entry[1], *v7 != Entry) )
    __fastfail(3u);
  *v7 = v6;
  v6[1] = v7;
  *((_DWORD *)Entry + 4) = 846031188;
  ExFreeToNPagedLookasideList(&Lookaside, Entry);
  if ( !--dword_1400396A0 )
    KeSetEvent(&Event, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x140005fb0  push    rbx
0x140005fb2  push    rbp
0x140005fb3  push    rsi
0x140005fb4  push    rdi
0x140005fb5  sub     rsp, 28h
0x140005fb9  mov     rdi, [rcx+28h]
0x140005fbd  mov     rbx, rcx
0x140005fc0  mov     rsi, [rcx+30h]
0x140005fc4  mov     rbp, [rcx+38h]
0x140005fc8  mov     qword ptr [rcx+28h], 0
0x140005fd0  mov     byte ptr [rcx+17h], 0
0x140005fd4  mov     rcx, [rcx+20h]
0x140005fd8  test    rcx, rcx
0x140005fdb  jz      short loc_140005FF2
0x140005fdd  mov     r8b, 1
0x140005fe0  mov     edx, 2
0x140005fe5  call    NBT_DEREFERENCE_DEVICE
0x140005fea  mov     qword ptr [rbx+20h], 0
0x140005ff2  test    rdi, rdi
0x140005ff5  jnz     short loc_140006042
0x140005ff7  mov     rax, [rbx]
0x140005ffa  cmp     [rax+8], rbx
0x140005ffe  jnz     short loc_140006055
0x140006000  mov     rcx, [rbx+8]
0x140006004  cmp     [rcx], rbx
0x140006007  jnz     short loc_140006055
0x140006009  mov     [rcx], rax
0x14000600c  mov     rdx, rbx; Entry
0x14000600f  mov     [rax+8], rcx
0x140006013  lea     rcx, Lookaside; Lookaside
0x14000601a  mov     dword ptr [rbx+10h], 326D6954h
0x140006021  call    cs:__imp_ExFreeToNPagedLookasideList
0x140006028  nop     dword ptr [rax+rax+00h]
0x14000602d  sub     cs:dword_1400396A0, 1
0x140006034  jz      short loc_14000605C
0x140006036  xor     eax, eax
0x140006038  add     rsp, 28h
0x14000603c  pop     rdi
0x14000603d  pop     rsi
0x14000603e  pop     rbp
0x14000603f  pop     rbx
0x140006040  retn
0x140006042  xor     r8d, r8d
0x140006045  mov     rdx, rbp
0x140006048  mov     rcx, rsi
0x14000604b  mov     rax, rdi
0x14000604e  call    _guard_dispatch_icall
0x140006053  jmp     short loc_140005FF7
0x140006055  mov     ecx, 3
0x14000605a  int     29h; Win8: RtlFailFast(ecx)
0x14000605c  xor     r8d, r8d; Wait
0x14000605f  lea     rcx, Event; Event
0x140006066  xor     edx, edx; Increment
0x140006068  call    cs:__imp_KeSetEvent
0x14000606f  nop     dword ptr [rax+rax+00h]
0x140006074  jmp     short loc_140006036
```
