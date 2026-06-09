# TimerQScheduleItem

- ea: `0x1400181a8`
- end: `0x140018259`
- name: `TimerQScheduleItem`
- size: `177`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f698`
- `0x140015050`
- `0x140015de4`
- `0x140015ebc`
- `0x1400171e0`
- `0x1400175f0`
- `0x140019a80`

## callees

- `0x14000fa20`
- `0x1400181a8`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140018243`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018243`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400181ce`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400181ce`

## pseudocode

```c
void __fastcall TimerQScheduleItem(__int64 a1, __int64 *a2, unsigned int a3, __int64 a4, __int64 a5)
{
  KSPIN_LOCK *v5; // rsi
  __int64 v7; // rbp
  KIRQL v9; // al
  bool v10; // zf
  KIRQL v11; // dl
  __int64 *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 *i; // r8
  __int64 v16; // rax

  v5 = (KSPIN_LOCK *)(a1 + 48);
  v7 = a3;
  a2[3] = a4;
  a2[4] = a5;
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 48));
  v10 = *(_BYTE *)(a1 + 40) == 0;
  *(_BYTE *)(a1 + 56) = v9;
  if ( v10 )
  {
    v12 = (__int64 *)(a1 + 8);
    v13 = MEMORY[0xFFFFF78000000014];
    v14 = MEMORY[0xFFFFF78000000014] + 10000 * v7;
    a2[2] = v14;
    for ( i = *(__int64 **)(a1 + 16); i != v12 && i[2] >= v14; i = (__int64 *)i[1] )
      ;
    v16 = *i;
    *a2 = *i;
    a2[1] = (__int64)i;
    *(_QWORD *)(v16 + 8) = a2;
    *(_QWORD *)a2[1] = a2;
    if ( (__int64 *)*v12 == a2 )
      SetTimer(a1, v13);
    v11 = *(_BYTE *)(a1 + 56);
  }
  else
  {
    v11 = v9;
  }
  KeReleaseSpinLock(v5, v11);
}

```

## disassembly

```asm
0x1400181a8  push    rbx
0x1400181aa  push    rbp
0x1400181ab  push    rsi
0x1400181ac  push    rdi
0x1400181ad  sub     rsp, 28h
0x1400181b1  mov     rax, [rsp+48h+arg_20]
0x1400181b6  lea     rsi, [rcx+30h]
0x1400181ba  mov     rdi, rcx
0x1400181bd  mov     ebp, r8d
0x1400181c0  mov     rcx, rsi; SpinLock
0x1400181c3  mov     [rdx+18h], r9
0x1400181c7  mov     rbx, rdx
0x1400181ca  mov     [rdx+20h], rax
0x1400181ce  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400181d5  nop     dword ptr [rax+rax+00h]
0x1400181da  cmp     byte ptr [rdi+28h], 0
0x1400181de  mov     [rdi+38h], al
0x1400181e1  jz      short loc_1400181E7
0x1400181e3  mov     dl, al
0x1400181e5  jmp     short loc_140018240
0x1400181e7  imul    rax, rbp, 2710h
0x1400181ee  mov     rdx, 0FFFFF78000000014h
0x1400181f8  lea     rcx, [rdi+8]
0x1400181fc  mov     rdx, [rdx]
0x1400181ff  add     rax, rdx
0x140018202  mov     [rbx+10h], rax
0x140018206  mov     r8, [rdi+10h]
0x14001820a  jmp     short loc_140018216
0x14001820c  cmp     [r8+10h], rax
0x140018210  jl      short loc_14001821B
0x140018212  mov     r8, [r8+8]
0x140018216  cmp     r8, rcx
0x140018219  jnz     short loc_14001820C
0x14001821b  mov     rax, [r8]
0x14001821e  mov     [rbx], rax
0x140018221  mov     [rbx+8], r8
0x140018225  mov     [rax+8], rbx
0x140018229  mov     rax, [rbx+8]
0x14001822d  mov     [rax], rbx
0x140018230  cmp     [rcx], rbx
0x140018233  jnz     short loc_14001823D
0x140018235  mov     rcx, rdi
0x140018238  call    SetTimer
0x14001823d  mov     dl, [rdi+38h]; NewIrql
0x140018240  mov     rcx, rsi; SpinLock
0x140018243  call    cs:__imp_KeReleaseSpinLock
0x14001824a  nop     dword ptr [rax+rax+00h]
0x14001824f  add     rsp, 28h
0x140018253  pop     rdi
0x140018254  pop     rsi
0x140018255  pop     rbp
0x140018256  pop     rbx
0x140018257  retn
```
