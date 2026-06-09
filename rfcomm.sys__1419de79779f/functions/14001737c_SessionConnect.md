# SessionConnect

- ea: `0x14001737c`
- end: `0x1400174a2`
- name: `SessionConnect`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140018e9c`

## callees

- `0x140003cb4`
- `0x140004a68`
- `0x14000e4e0`
- `0x14001737c`
- `0x140017ab8`
- `0x140017db4`
- `0x14001e74c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400173e6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400173e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017401`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017401`

## string_xrefs

- `0x1400173c7`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\session.c`
- `0x140017433`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\session.c`

## pseudocode

```c
__int64 __fastcall SessionConnect(__int64 a1, int a2)
{
  KIRQL v3; // al
  int v4; // edi
  int v5; // edx
  int v6; // ebx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      14,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids,
      a1);
  RefObj_AddRefEx(a1 + 24, 1413697091, 164, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\session.c");
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  v4 = *(_DWORD *)(a1 + 288);
  *(_BYTE *)(a1 + 64) = v3;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v3);
  v6 = BrbpConnect(a1, 0, *(_QWORD *)(a1 + 264), v4, 0, 0);
  if ( v6 < 0 )
  {
    RefObj_ReleaseEx(a1 + 24, 1413697091, 175, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\session.c");
    SessionDisconnectInd(a1, 0, (unsigned int)v6);
    SessionDisconnect(a1);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      3,
      15,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids,
      v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001737c  push    rbx
0x14001737e  push    rbp
0x14001737f  push    rsi
0x140017380  push    rdi
0x140017381  push    r12
0x140017383  push    r14
0x140017385  sub     rsp, 38h
0x140017389  mov     rsi, rcx
0x14001738c  lea     r14, WPP_RECORDER_INITIALIZED
0x140017393  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001739a  lea     r12, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x1400173a1  jz      short loc_1400173C7
0x1400173a3  mov     [rsp+68h+var_40], rcx
0x1400173a8  mov     r9d, 0Eh
0x1400173ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400173b5  mov     [rsp+68h+var_48], r12
0x1400173ba  lea     r8d, [r9-0Bh]
0x1400173be  mov     rcx, [rcx+40h]
0x1400173c2  call    WPP_RECORDER_SF_q
0x1400173c7  lea     r9, aOnecoreDrivers; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400173ce  mov     edx, 54434E43h
0x1400173d3  mov     r8d, 0A4h
0x1400173d9  lea     rcx, [rsi+18h]
0x1400173dd  call    RefObj_AddRefEx
0x1400173e2  lea     rcx, [rsi+38h]; SpinLock
0x1400173e6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400173ed  nop     dword ptr [rax+rax+00h]
0x1400173f2  mov     edi, [rsi+120h]
0x1400173f8  lea     rcx, [rsi+38h]; SpinLock
0x1400173fc  mov     dl, al; NewIrql
0x1400173fe  mov     [rsi+40h], al
0x140017401  call    cs:__imp_KeReleaseSpinLock
0x140017408  nop     dword ptr [rax+rax+00h]
0x14001740d  mov     r8, [rsi+108h]
0x140017414  xor     eax, eax
0x140017416  mov     word ptr [rsp+68h+var_40], ax
0x14001741b  mov     r9d, edi
0x14001741e  xor     edx, edx
0x140017420  mov     [rsp+68h+var_48], rax
0x140017425  mov     rcx, rsi
0x140017428  call    BrbpConnect
0x14001742d  mov     ebx, eax
0x14001742f  test    eax, eax
0x140017431  jns     short loc_140017466
0x140017433  lea     r9, aOnecoreDrivers; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001743a  mov     edx, 54434E43h
0x14001743f  mov     r8d, 0AFh
0x140017445  lea     rcx, [rsi+18h]
0x140017449  call    RefObj_ReleaseEx
0x14001744e  xor     r9d, r9d
0x140017451  mov     r8d, ebx
0x140017454  xor     edx, edx
0x140017456  mov     rcx, rsi
0x140017459  call    SessionDisconnectInd
0x14001745e  mov     rcx, rsi
0x140017461  call    SessionDisconnect
0x140017466  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001746d  jz      short loc_140017492
0x14001746f  mov     rcx, cs:WPP_GLOBAL_Control
0x140017476  mov     r9d, 0Fh
0x14001747c  mov     dword ptr [rsp+68h+var_40], ebx
0x140017480  mov     [rsp+68h+var_48], r12
0x140017485  mov     rcx, [rcx+40h]
0x140017489  lea     r8d, [r9-0Ch]
0x14001748d  call    WPP_RECORDER_SF_d
0x140017492  mov     eax, ebx
0x140017494  add     rsp, 38h
0x140017498  pop     r14
0x14001749a  pop     r12
0x14001749c  pop     rdi
0x14001749d  pop     rsi
0x14001749e  pop     rbp
0x14001749f  pop     rbx
0x1400174a0  retn
```
