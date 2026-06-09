# PxCmCloseCall

- ea: `0x140010240`
- end: `0x1400103b8`
- name: `PxCmCloseCall`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140001bc8`
- `0x140006e08`
- `0x140007940`
- `0x140010240`
- `0x1400156d8`
- `0x140016450`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400102dc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010323`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010371`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400102dc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010323`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010371`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400102ff`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010361`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010396`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400102ff`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010361`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010396`
- `NDIS!NdisCmCloseCallComplete` at `0x140010314`
- `NDIS!NdisCmCloseCallComplete` at `0x140010314`

## pseudocode

```c
__int64 __fastcall PxCmCloseCall(unsigned __int64 a1)
{
  _DWORD *v2; // rbx
  KIRQL v4; // al
  __int64 v5; // rdi
  bool v6; // zf
  KIRQL v7; // al
  PVOID Entry[3]; // [rsp+20h] [rbp-18h] BYREF

  Entry[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids, a1);
  GetVcFromCtx(a1, Entry);
  v2 = Entry[0];
  if ( Entry[0] )
  {
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry[0] + 64);
    *((_BYTE *)v2 + 520) = v4;
    v2[6] = 0;
    v2[9] |= 0x80u;
    KeReleaseSpinLock((PKSPIN_LOCK)v2 + 64, v4);
    NdisCmCloseCallComplete(0, *((NDIS_HANDLE *)v2 + 8), 0);
    *((_BYTE *)v2 + 520) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v2 + 64);
    if ( (v2[8] & 8) != 0 )
      PxCloseCallWithCm(v2);
    v5 = *((_QWORD *)v2 + 10);
    v6 = v2[7] == 2;
    v2[7] -= 2;
    if ( v6 )
      DoDerefVcWork(v2);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)v2 + 64, *((_BYTE *)v2 + 520));
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 88));
    v6 = (*(_DWORD *)(v5 + 20))-- == 1;
    *(_BYTE *)(v5 + 96) = v7;
    if ( v6 )
      DoDerefCmAfWork((PVOID)v5);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 88), v7);
    return 259;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        (unsigned int)(LODWORD(Entry[0]) + 22),
        WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids,
        a1);
    return 0;
  }
}

```

## disassembly

```asm
0x140010240  mov     [rsp+arg_0], rbx
0x140010245  mov     [rsp+arg_8], rsi
0x14001024a  push    rdi
0x14001024b  sub     rsp, 30h
0x14001024f  mov     rdi, rcx
0x140010252  mov     [rsp+38h+Entry], 0
0x14001025b  mov     rcx, cs:WPP_GLOBAL_Control
0x140010262  lea     rsi, WPP_GLOBAL_Control
0x140010269  cmp     rcx, rsi
0x14001026c  jz      short loc_14001028C
0x14001026e  cmp     byte ptr [rcx+29h], 5
0x140010272  jb      short loc_14001028C
0x140010274  mov     rcx, [rcx+18h]
0x140010278  lea     r8, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids
0x14001027f  mov     edx, 15h
0x140010284  mov     r9, rdi
0x140010287  call    WPP_SF_q
0x14001028c  lea     rdx, [rsp+38h+Entry]
0x140010291  mov     rcx, rdi
0x140010294  call    GetVcFromCtx
0x140010299  mov     rbx, [rsp+38h+Entry]
0x14001029e  test    rbx, rbx
0x1400102a1  jnz     short loc_1400102D2
0x1400102a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400102aa  cmp     rcx, rsi
0x1400102ad  jz      short loc_1400102CB
0x1400102af  cmp     byte ptr [rcx+29h], 3
0x1400102b3  jb      short loc_1400102CB
0x1400102b5  mov     rcx, [rcx+18h]
0x1400102b9  lea     edx, [rbx+16h]
0x1400102bc  mov     r9, rdi
0x1400102bf  lea     r8, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids
0x1400102c6  call    WPP_SF_q
0x1400102cb  xor     eax, eax
0x1400102cd  jmp     loc_1400103A7
0x1400102d2  lea     rsi, [rbx+200h]
0x1400102d9  mov     rcx, rsi; SpinLock
0x1400102dc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400102e3  nop     dword ptr [rax+rax+00h]
0x1400102e8  mov     [rbx+208h], al
0x1400102ee  mov     dl, al; NewIrql
0x1400102f0  mov     dword ptr [rbx+18h], 0
0x1400102f7  mov     rcx, rsi; SpinLock
0x1400102fa  bts     dword ptr [rbx+24h], 7
0x1400102ff  call    cs:__imp_KeReleaseSpinLock
0x140010306  nop     dword ptr [rax+rax+00h]
0x14001030b  mov     rdx, [rbx+40h]; NdisVcHandle
0x14001030f  xor     r8d, r8d; NdisPartyHandle
0x140010312  xor     ecx, ecx; Status
0x140010314  call    cs:__imp_NdisCmCloseCallComplete
0x14001031b  nop     dword ptr [rax+rax+00h]
0x140010320  mov     rcx, rsi; SpinLock
0x140010323  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001032a  nop     dword ptr [rax+rax+00h]
0x14001032f  mov     [rbx+208h], al
0x140010335  mov     eax, [rbx+20h]
0x140010338  test    al, 8
0x14001033a  jz      short loc_140010344
0x14001033c  mov     rcx, rbx
0x14001033f  call    PxCloseCallWithCm
0x140010344  mov     rdi, [rbx+50h]
0x140010348  add     dword ptr [rbx+1Ch], 0FFFFFFFEh
0x14001034c  jnz     short loc_140010358
0x14001034e  mov     rcx, rbx; Entry
0x140010351  call    DoDerefVcWork
0x140010356  jmp     short loc_14001036D
0x140010358  mov     dl, [rbx+208h]; NewIrql
0x14001035e  mov     rcx, rsi; SpinLock
0x140010361  call    cs:__imp_KeReleaseSpinLock
0x140010368  nop     dword ptr [rax+rax+00h]
0x14001036d  lea     rcx, [rdi+58h]; SpinLock
0x140010371  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010378  nop     dword ptr [rax+rax+00h]
0x14001037d  add     dword ptr [rdi+14h], 0FFFFFFFFh
0x140010381  mov     [rdi+60h], al
0x140010384  jnz     short loc_140010390
0x140010386  mov     rcx, rdi; P
0x140010389  call    DoDerefCmAfWork
0x14001038e  jmp     short loc_1400103A2
0x140010390  mov     dl, al; NewIrql
0x140010392  lea     rcx, [rdi+58h]; SpinLock
0x140010396  call    cs:__imp_KeReleaseSpinLock
0x14001039d  nop     dword ptr [rax+rax+00h]
0x1400103a2  mov     eax, 103h
0x1400103a7  mov     rbx, [rsp+38h+arg_0]
0x1400103ac  mov     rsi, [rsp+38h+arg_8]
0x1400103b1  add     rsp, 30h
0x1400103b5  pop     rdi
0x1400103b6  retn
```
