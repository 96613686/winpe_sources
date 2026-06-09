# TimerQScheduleItem

- ea: `0x140015f08`
- end: `0x14001600e`
- name: `TimerQScheduleItem`
- size: `262`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140016310`
- `0x140016534`
- `0x140017740`
- `0x140017a00`

## callees

- `0x14000113c`
- `0x140015e58`
- `0x140015f08`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140015ff1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015ff1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015f6e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015f6e`

## pseudocode

```c
void __fastcall TimerQScheduleItem(__int64 a1, __int64 *a2, unsigned int a3, __int64 a4, __int64 a5)
{
  __int64 v6; // rdi
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 *i; // r8
  __int64 v11; // rax

  v6 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xBu,
      (__int64)WPP_9a0567af5d373ab1ea780e14cbd413d9_Traceguids,
      a3);
  }
  a2[4] = a5;
  a2[3] = a4;
  byte_14000A258 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v8 = MEMORY[0xFFFFF78000000014];
  v9 = MEMORY[0xFFFFF78000000014] + 10000 * v6;
  a2[2] = v9;
  for ( i = (__int64 *)qword_14000A230; i != &qword_14000A228 && i[2] >= v9; i = (__int64 *)i[1] )
    ;
  v11 = *i;
  *a2 = *i;
  a2[1] = (__int64)i;
  *(_QWORD *)(v11 + 8) = a2;
  *(_QWORD *)a2[1] = a2;
  if ( (__int64 *)qword_14000A228 == a2 )
    SetTimer(&gl_TimerQ, v8);
  KeReleaseSpinLock(&SpinLock, byte_14000A258);
}

```

## disassembly

```asm
0x140015f08  mov     [rsp+arg_0], rbx
0x140015f0d  mov     [rsp+arg_8], rsi
0x140015f12  push    rdi
0x140015f13  sub     rsp, 20h
0x140015f17  mov     rsi, r9
0x140015f1a  mov     edi, r8d
0x140015f1d  mov     rbx, rdx
0x140015f20  mov     rcx, cs:WPP_GLOBAL_Control
0x140015f27  lea     rax, WPP_GLOBAL_Control
0x140015f2e  cmp     rcx, rax
0x140015f31  jz      short loc_140015F5A
0x140015f33  test    dword ptr [rcx+2Ch], 400h
0x140015f3a  jz      short loc_140015F5A
0x140015f3c  cmp     byte ptr [rcx+29h], 3
0x140015f40  jb      short loc_140015F5A
0x140015f42  mov     rcx, [rcx+18h]
0x140015f46  lea     r8, WPP_9a0567af5d373ab1ea780e14cbd413d9_Traceguids
0x140015f4d  mov     edx, 0Bh
0x140015f52  mov     r9d, edi
0x140015f55  call    WPP_SF_d
0x140015f5a  mov     rax, [rsp+28h+arg_20]
0x140015f5f  lea     rcx, SpinLock; SpinLock
0x140015f66  mov     [rbx+20h], rax
0x140015f6a  mov     [rbx+18h], rsi
0x140015f6e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015f75  nop     dword ptr [rax+rax+00h]
0x140015f7a  mov     cs:byte_14000A258, al
0x140015f80  mov     rdx, 0FFFFF78000000014h
0x140015f8a  lea     rcx, qword_14000A228
0x140015f91  imul    rax, rdi, 2710h
0x140015f98  mov     rdx, [rdx]
0x140015f9b  add     rax, rdx
0x140015f9e  mov     [rbx+10h], rax
0x140015fa2  mov     r8, cs:qword_14000A230
0x140015fa9  jmp     short loc_140015FB5
0x140015fab  cmp     [r8+10h], rax
0x140015faf  jl      short loc_140015FBA
0x140015fb1  mov     r8, [r8+8]
0x140015fb5  cmp     r8, rcx
0x140015fb8  jnz     short loc_140015FAB
0x140015fba  mov     rax, [r8]
0x140015fbd  mov     [rbx], rax
0x140015fc0  mov     [rbx+8], r8
0x140015fc4  mov     [rax+8], rbx
0x140015fc8  mov     rax, [rbx+8]
0x140015fcc  mov     [rax], rbx
0x140015fcf  cmp     cs:qword_14000A228, rbx
0x140015fd6  jnz     short loc_140015FE4
0x140015fd8  lea     rcx, gl_TimerQ
0x140015fdf  call    SetTimer
0x140015fe4  mov     dl, cs:byte_14000A258; NewIrql
0x140015fea  lea     rcx, SpinLock; SpinLock
0x140015ff1  call    cs:__imp_KeReleaseSpinLock
0x140015ff8  nop     dword ptr [rax+rax+00h]
0x140015ffd  mov     rbx, [rsp+28h+arg_0]
0x140016002  mov     rsi, [rsp+28h+arg_8]
0x140016007  add     rsp, 20h
0x14001600b  pop     rdi
0x14001600c  retn
```
