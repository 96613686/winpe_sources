# HelloTimerEvent

- ea: `0x140015050`
- end: `0x140015182`
- name: `HelloTimerEvent`
- size: `306`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x14000fd0c`
- `0x140015050`
- `0x1400181a8`
- `0x14001ac30`
- `0x14001c400`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140015148`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015148`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015162`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015162`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015072`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015072`

## pseudocode

```c
__int64 __fastcall HelloTimerEvent(_QWORD *Entry, __int64 a2, int a3)
{
  __int64 v3; // rbp
  KIRQL v6; // al
  bool v7; // zf
  char v8; // bl
  unsigned int v9; // edx
  int v10; // ebx
  unsigned int v11; // ecx
  _WORD *v13; // [rsp+28h] [rbp-40h]

  v3 = *(_QWORD *)(a2 + 24);
  if ( a3 )
    goto LABEL_15;
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
  v7 = *(_DWORD *)(a2 + 276) == 0;
  *(_BYTE *)(a2 + 40) = v6;
  if ( v7 )
  {
    if ( !*(_DWORD *)(a2 + 272) )
    {
      v8 = 0;
      if ( *(_DWORD *)(a2 + 124) && Entry == *(_QWORD **)(a2 + 264) )
        SendControl(a2, 0, 6u, 0, 0, v13, 0);
      *(_QWORD *)(a2 + 264) = 0;
      goto LABEL_14;
    }
  }
  else
  {
    *(_QWORD *)(a2 + 272) = *(unsigned int *)(v3 + 20);
  }
  v9 = *(_DWORD *)(a2 + 272);
  v10 = v9;
  if ( v9 >= 0x2710 )
    v10 = 10000;
  v11 = v9 - 10000;
  if ( v9 < 0x2710 )
    v11 = 0;
  *(_DWORD *)(a2 + 272) = v11;
  ReferenceTunnel(a2, 0);
  Entry[1] = Entry;
  *Entry = Entry;
  TimerQScheduleItem(*(_QWORD *)(a2 + 304), (_DWORD)Entry, v10, (unsigned int)HelloTimerEvent, a2);
  v8 = 1;
LABEL_14:
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 32), *(_BYTE *)(a2 + 40));
  if ( !v8 )
LABEL_15:
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 576), Entry);
  return DereferenceTunnel(a2);
}

```

## disassembly

```asm
0x140015050  push    rbx
0x140015052  push    rbp
0x140015053  push    rsi
0x140015054  push    rdi
0x140015055  push    r14
0x140015057  sub     rsp, 40h
0x14001505b  mov     rbp, [rdx+18h]
0x14001505f  mov     rdi, rdx
0x140015062  mov     rsi, rcx
0x140015065  test    r8d, r8d
0x140015068  jnz     loc_140015158
0x14001506e  lea     rcx, [rdx+20h]; SpinLock
0x140015072  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015079  nop     dword ptr [rax+rax+00h]
0x14001507e  cmp     dword ptr [rdi+114h], 0
0x140015085  mov     [rdi+28h], al
0x140015088  jnz     short loc_1400150D4
0x14001508a  cmp     dword ptr [rdi+110h], 0
0x140015091  jnz     short loc_1400150E7
0x140015093  xor     bl, bl
0x140015095  cmp     dword ptr [rdi+7Ch], 0
0x140015099  jz      short loc_1400150C7
0x14001509b  cmp     rsi, [rdi+108h]
0x1400150a2  jnz     short loc_1400150C7
0x1400150a4  mov     r8d, 6
0x1400150aa  mov     [rsp+68h+var_38], 0
0x1400150b2  xor     r9d, r9d
0x1400150b5  mov     dword ptr [rsp+68h+var_48], 0
0x1400150bd  xor     edx, edx
0x1400150bf  mov     rcx, rdi
0x1400150c2  call    SendControl
0x1400150c7  mov     qword ptr [rdi+108h], 0
0x1400150d2  jmp     short loc_140015141
0x1400150d4  mov     eax, [rbp+14h]
0x1400150d7  mov     [rdi+110h], eax
0x1400150dd  mov     dword ptr [rdi+114h], 0
0x1400150e7  mov     edx, [rdi+110h]
0x1400150ed  mov     r8d, 2710h
0x1400150f3  cmp     edx, r8d
0x1400150f6  mov     ebx, edx
0x1400150f8  cmovnb  ebx, r8d
0x1400150fc  xor     eax, eax
0x1400150fe  lea     ecx, [rdx-2710h]
0x140015104  cmp     edx, r8d
0x140015107  cmovb   ecx, eax
0x14001510a  xor     edx, edx
0x14001510c  mov     [rdi+110h], ecx
0x140015112  mov     rcx, rdi
0x140015115  call    ReferenceTunnel
0x14001511a  mov     [rsi+8], rsi
0x14001511e  lea     r9, HelloTimerEvent
0x140015125  mov     [rsi], rsi
0x140015128  mov     r8d, ebx
0x14001512b  mov     rcx, [rdi+130h]
0x140015132  mov     rdx, rsi
0x140015135  mov     [rsp+68h+var_48], rdi
0x14001513a  call    TimerQScheduleItem
0x14001513f  mov     bl, 1
0x140015141  mov     dl, [rdi+28h]; NewIrql
0x140015144  lea     rcx, [rdi+20h]; SpinLock
0x140015148  call    cs:__imp_KeReleaseSpinLock
0x14001514f  nop     dword ptr [rax+rax+00h]
0x140015154  test    bl, bl
0x140015156  jnz     short loc_14001516E
0x140015158  lea     rcx, [rbp+240h]; Lookaside
0x14001515f  mov     rdx, rsi; Entry
0x140015162  call    cs:__imp_ExFreeToNPagedLookasideList
0x140015169  nop     dword ptr [rax+rax+00h]
0x14001516e  mov     rcx, rdi
0x140015171  call    DereferenceTunnel
0x140015176  add     rsp, 40h
0x14001517a  pop     r14
0x14001517c  pop     rdi
0x14001517d  pop     rsi
0x14001517e  pop     rbp
0x14001517f  pop     rbx
0x140015180  retn
```
