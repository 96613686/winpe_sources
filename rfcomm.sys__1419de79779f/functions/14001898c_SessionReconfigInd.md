# SessionReconfigInd

- ea: `0x14001898c`
- end: `0x140018a66`
- name: `SessionReconfigInd`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14000e840`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x14000ecd0`
- `0x140017db4`
- `0x14001898c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400189d8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400189d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400189ed`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400189ed`

## pseudocode

```c
__int64 __fastcall SessionReconfigInd(__int64 a1, __int64 a2)
{
  KIRQL v4; // al
  signed int v5; // eax
  int v6; // edx
  unsigned int v7; // ebx
  unsigned int v9; // [rsp+28h] [rbp-30h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      23,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  *(_BYTE *)(a1 + 64) = v4;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v4);
  v5 = BrbpReconfig(a1, 1, *(_QWORD *)(a1 + 264), 3, a2);
  v7 = v5;
  if ( v5 < 0 )
    SessionDisconnectInd(a1, 1, v5, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v9 = v7;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      3,
      24,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids,
      v9);
  }
  return v7;
}

```

## disassembly

```asm
0x14001898c  push    rbx
0x14001898e  push    rsi
0x14001898f  push    rdi
0x140018990  push    r14
0x140018992  push    r15
0x140018994  sub     rsp, 30h
0x140018998  mov     rsi, rdx
0x14001899b  mov     rdi, rcx
0x14001899e  lea     r14, WPP_RECORDER_INITIALIZED
0x1400189a5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400189ac  lea     r15, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x1400189b3  jz      short loc_1400189D4
0x1400189b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400189bc  mov     r9d, 17h
0x1400189c2  mov     [rsp+58h+var_38], r15
0x1400189c7  mov     rcx, [rcx+40h]
0x1400189cb  lea     r8d, [r9-14h]
0x1400189cf  call    WPP_RECORDER_SF_
0x1400189d4  lea     rcx, [rdi+38h]; SpinLock
0x1400189d8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400189df  nop     dword ptr [rax+rax+00h]
0x1400189e4  mov     dl, al; NewIrql
0x1400189e6  mov     [rdi+40h], al
0x1400189e9  lea     rcx, [rdi+38h]; SpinLock
0x1400189ed  call    cs:__imp_KeReleaseSpinLock
0x1400189f4  nop     dword ptr [rax+rax+00h]
0x1400189f9  mov     r8, [rdi+108h]
0x140018a00  mov     r9d, 3
0x140018a06  mov     dl, 1
0x140018a08  mov     [rsp+58h+var_38], rsi
0x140018a0d  mov     rcx, rdi
0x140018a10  call    BrbpReconfig
0x140018a15  mov     ebx, eax
0x140018a17  test    eax, eax
0x140018a19  jns     short loc_140018A2B
0x140018a1b  xor     r9d, r9d
0x140018a1e  mov     r8d, eax
0x140018a21  mov     dl, 1
0x140018a23  mov     rcx, rdi
0x140018a26  call    SessionDisconnectInd
0x140018a2b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140018a32  jz      short loc_140018A57
0x140018a34  mov     rcx, cs:WPP_GLOBAL_Control
0x140018a3b  mov     r9d, 18h
0x140018a41  mov     [rsp+58h+var_30], ebx
0x140018a45  mov     [rsp+58h+var_38], r15
0x140018a4a  mov     rcx, [rcx+40h]
0x140018a4e  lea     r8d, [r9-15h]
0x140018a52  call    WPP_RECORDER_SF_d
0x140018a57  mov     eax, ebx
0x140018a59  add     rsp, 30h
0x140018a5d  pop     r15
0x140018a5f  pop     r14
0x140018a61  pop     rdi
0x140018a62  pop     rsi
0x140018a63  pop     rbx
0x140018a64  retn
```
