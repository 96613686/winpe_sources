# SessionReconfig

- ea: `0x1400185c8`
- end: `0x1400186ac`
- name: `SessionReconfig`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140018e9c`

## callees

- `0x140003cb4`
- `0x140004a68`
- `0x14000ecd0`
- `0x140017db4`
- `0x1400185c8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018615`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018615`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018630`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018630`

## pseudocode

```c
__int64 __fastcall SessionReconfig(__int64 a1, int a2)
{
  KIRQL v3; // al
  int v4; // ebx
  signed int v5; // eax
  int v6; // edx
  unsigned int v7; // ebx
  __int64 v9; // [rsp+28h] [rbp-30h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      21,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids,
      a1);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  v4 = *(_DWORD *)(a1 + 288);
  *(_BYTE *)(a1 + 64) = v3;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v3);
  v5 = BrbpReconfig(a1, 0, *(_QWORD *)(a1 + 264), v4, *(_QWORD *)(a1 + 280));
  v7 = v5;
  if ( v5 < 0 )
    SessionDisconnectInd(a1, 1, v5, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v9) = v7;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      3,
      22,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids,
      v9);
  }
  return v7;
}

```

## disassembly

```asm
0x1400185c8  push    rbx
0x1400185ca  push    rbp
0x1400185cb  push    rsi
0x1400185cc  push    rdi
0x1400185cd  push    r15
0x1400185cf  sub     rsp, 30h
0x1400185d3  mov     rsi, rcx
0x1400185d6  lea     rbp, WPP_RECORDER_INITIALIZED
0x1400185dd  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400185e4  lea     r15, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x1400185eb  jz      short loc_140018611
0x1400185ed  mov     [rsp+58h+var_30], rcx
0x1400185f2  mov     r9d, 15h
0x1400185f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400185ff  mov     [rsp+58h+var_38], r15
0x140018604  lea     r8d, [r9-12h]
0x140018608  mov     rcx, [rcx+40h]
0x14001860c  call    WPP_RECORDER_SF_q
0x140018611  lea     rcx, [rsi+38h]; SpinLock
0x140018615  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001861c  nop     dword ptr [rax+rax+00h]
0x140018621  mov     ebx, [rsi+120h]
0x140018627  lea     rcx, [rsi+38h]; SpinLock
0x14001862b  mov     dl, al; NewIrql
0x14001862d  mov     [rsi+40h], al
0x140018630  call    cs:__imp_KeReleaseSpinLock
0x140018637  nop     dword ptr [rax+rax+00h]
0x14001863c  mov     rax, [rsi+118h]
0x140018643  mov     r9d, ebx
0x140018646  mov     r8, [rsi+108h]
0x14001864d  xor     edx, edx
0x14001864f  mov     rcx, rsi
0x140018652  mov     [rsp+58h+var_38], rax
0x140018657  call    BrbpReconfig
0x14001865c  mov     ebx, eax
0x14001865e  test    eax, eax
0x140018660  jns     short loc_140018672
0x140018662  xor     r9d, r9d
0x140018665  mov     r8d, eax
0x140018668  mov     dl, 1
0x14001866a  mov     rcx, rsi
0x14001866d  call    SessionDisconnectInd
0x140018672  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140018679  jz      short loc_14001869E
0x14001867b  mov     rcx, cs:WPP_GLOBAL_Control
0x140018682  mov     r9d, 16h
0x140018688  mov     dword ptr [rsp+58h+var_30], ebx
0x14001868c  mov     [rsp+58h+var_38], r15
0x140018691  mov     rcx, [rcx+40h]
0x140018695  lea     r8d, [r9-13h]
0x140018699  call    WPP_RECORDER_SF_d
0x14001869e  mov     eax, ebx
0x1400186a0  add     rsp, 30h
0x1400186a4  pop     r15
0x1400186a6  pop     rdi
0x1400186a7  pop     rsi
0x1400186a8  pop     rbp
0x1400186a9  pop     rbx
0x1400186aa  retn
```
