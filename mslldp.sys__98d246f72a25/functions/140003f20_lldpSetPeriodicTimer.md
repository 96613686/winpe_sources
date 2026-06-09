# lldpSetPeriodicTimer

- ea: `0x140003f20`
- end: `0x140003ff9`
- name: `lldpSetPeriodicTimer`
- size: `217`
- prototype: `__int64 __fastcall(PKTIMER Timer)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140001330`
- `0x140002180`
- `0x140002500`

## callees

- `0x140003f20`
- `0x140004000`
- `0x140004b00`
- `0x140006460`

## import_xrefs

- `ntoskrnl!KeSetCoalescableTimer` at `0x140003fe3`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140003fe3`

## pseudocode

```c
BOOLEAN __fastcall lldpSetPeriodicTimer(PKTIMER Timer, unsigned int a2, char a3)
{
  __int64 v3; // rbx
  __int64 v6; // rdx
  __int64 v7; // r9
  ULONG ToleranceForTime; // esi

  v3 = a2;
  if ( a2 - 1 > 0xFFFD
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xBu,
      (__int64)WPP_3fbb6981ec7538c7b4b2c49461eb0c03_Traceguids,
      a2);
  }
  v6 = MEMORY[0xFFFFF78000000014];
  if ( a3 )
    v7 = MEMORY[0xFFFFF78000000014];
  else
    v7 = MEMORY[0xFFFFF78000000014] + 10000000 * v3;
  *(_QWORD *)&Timer[2].Header.Lock = v7;
  ToleranceForTime = lldpGetToleranceForTime((unsigned int)v3, v6);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_iidd(WPP_GLOBAL_Control->AttachedDevice);
  return KeSetCoalescableTimer(
           Timer,
           *(LARGE_INTEGER *)&Timer[2].Header.Lock,
           1000 * v3,
           ToleranceForTime,
           (PKDPC)&Timer[1]);
}

```

## disassembly

```asm
0x140003f20  push    rbx
0x140003f22  push    rbp
0x140003f23  push    rsi
0x140003f24  push    rdi
0x140003f25  sub     rsp, 48h
0x140003f29  mov     ebx, edx
0x140003f2b  lea     rbp, WPP_GLOBAL_Control
0x140003f32  movzx   esi, r8b
0x140003f36  mov     rdi, rcx
0x140003f39  lea     eax, [rbx-1]
0x140003f3c  cmp     eax, 0FFFDh
0x140003f41  jbe     short loc_140003F6D
0x140003f43  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f4a  cmp     rcx, rbp
0x140003f4d  jz      short loc_140003F6D
0x140003f4f  cmp     byte ptr [rcx+29h], 3
0x140003f53  jb      short loc_140003F6D
0x140003f55  mov     rcx, [rcx+18h]
0x140003f59  lea     r8, WPP_3fbb6981ec7538c7b4b2c49461eb0c03_Traceguids
0x140003f60  mov     edx, 0Bh
0x140003f65  mov     r9d, ebx
0x140003f68  call    WPP_SF_d
0x140003f6d  mov     rdx, 0FFFFF78000000014h
0x140003f77  mov     rdx, [rdx]
0x140003f7a  test    sil, sil
0x140003f7d  jz      short loc_140003F84
0x140003f7f  mov     r9, rdx
0x140003f82  jmp     short loc_140003F8E
0x140003f84  imul    r9, rbx, 989680h
0x140003f8b  add     r9, rdx
0x140003f8e  mov     ecx, ebx
0x140003f90  mov     [rdi+80h], r9
0x140003f97  call    lldpGetToleranceForTime
0x140003f9c  mov     esi, eax
0x140003f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003fa5  cmp     rcx, rbp
0x140003fa8  jz      short loc_140003FC6
0x140003faa  cmp     byte ptr [rcx+29h], 4
0x140003fae  jb      short loc_140003FC6
0x140003fb0  mov     rcx, [rcx+18h]
0x140003fb4  mov     [rsp+68h+var_38], eax
0x140003fb8  mov     [rsp+68h+var_40], ebx
0x140003fbc  mov     [rsp+68h+Dpc], rdx
0x140003fc1  call    WPP_SF_iidd
0x140003fc6  mov     rdx, [rdi+80h]; DueTime
0x140003fcd  lea     rax, [rdi+40h]
0x140003fd1  imul    r8d, ebx, 3E8h; Period
0x140003fd8  mov     r9d, esi; TolerableDelay
0x140003fdb  mov     rcx, rdi; Timer
0x140003fde  mov     [rsp+68h+Dpc], rax; Dpc
0x140003fe3  call    cs:__imp_KeSetCoalescableTimer
0x140003fea  nop     dword ptr [rax+rax+00h]
0x140003fef  add     rsp, 48h
0x140003ff3  pop     rdi
0x140003ff4  pop     rsi
0x140003ff5  pop     rbp
0x140003ff6  pop     rbx
0x140003ff7  retn
```
