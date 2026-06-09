# ChannelFree

- ea: `0x140019f70`
- end: `0x14001a124`
- name: `ChannelFree`
- size: `436`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003818`
- `0x140003bf4`
- `0x140004a68`
- `0x1400157dc`
- `0x140018040`
- `0x140018e9c`
- `0x140019f70`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019fc6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019fc6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a06f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a06f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a0d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a0d9`

## string_xrefs

- `0x14001a0a7`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`
- `0x14001a0c2`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`

## pseudocode

```c
void __fastcall ChannelFree(__int64 a1, int a2)
{
  _QWORD *v2; // rbx
  __int64 v3; // rdi
  _QWORD *v4; // rcx
  void **v5; // rax
  _QWORD *v6; // rcx
  _QWORD *v7; // rax
  __int64 v8; // rsi
  __int64 v9; // rdx
  char v10; // bp
  int v11; // edx
  int v12; // edx

  v2 = (_QWORD *)(a1 - 24);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      31,
      (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids,
      a1 - 24);
  v3 = v2[7];
  *(_BYTE *)(v3 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 56));
  v4 = (_QWORD *)*v2;
  if ( *(_QWORD **)(*v2 + 8LL) != v2 )
    goto LABEL_23;
  v5 = (void **)v2[1];
  if ( *v5 != v2 )
    goto LABEL_23;
  *v5 = v4;
  v4[1] = v5;
  v6 = v2 + 9;
  v2[1] = v2;
  *v2 = v2;
  v7 = (_QWORD *)v2[9];
  if ( v7 != v2 + 9 )
  {
    if ( (_QWORD *)v7[1] == v6 )
    {
      v9 = *v7;
      if ( *(_QWORD **)(*v7 + 8LL) == v7 )
      {
        *v6 = v9;
        v8 = (__int64)(v7 - 35);
        *(_QWORD *)(v9 + 8) = v6;
        v7[1] = v7;
        *v7 = v7;
        goto LABEL_10;
      }
    }
LABEL_23:
    __fastfail(3u);
  }
  v8 = 0;
LABEL_10:
  v10 = 0;
  if ( *(_QWORD *)(v3 + 80) == v3 + 80 && *(int *)(v3 + 48) < 5 )
  {
    if ( !v2 || *((_BYTE *)v2 + 186) )
      v10 = 1;
    RfcommSetState(v3, 5);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 56), *(_BYTE *)(v3 + 64));
  RfcommStartTimer(*(_QWORD *)(v3 + 72));
  if ( v10 )
    SessionDisconnectRequest(v3);
  if ( v8 )
  {
    ChannelConnect(v8, v11);
    RefObj_ReleaseEx(v8 + 24, 1313754947, 1002, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
  }
  RefObj_ReleaseEx(v3 + 24, 1312901187, 1005, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
  ExFreePoolWithTag(v2, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      3,
      32,
      (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids);
}

```

## disassembly

```asm
0x140019f70  push    rbx
0x140019f72  push    rbp
0x140019f73  push    rsi
0x140019f74  push    rdi
0x140019f75  push    r12
0x140019f77  push    r13
0x140019f79  push    r14
0x140019f7b  sub     rsp, 30h
0x140019f7f  lea     rbx, [rcx-18h]
0x140019f83  lea     r13, WPP_RECORDER_INITIALIZED
0x140019f8a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140019f91  lea     r12, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x140019f98  jz      short loc_140019FBE
0x140019f9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140019fa1  mov     r9d, 1Fh
0x140019fa7  mov     [rsp+68h+var_40], rbx
0x140019fac  mov     [rsp+68h+var_48], r12
0x140019fb1  mov     rcx, [rcx+40h]
0x140019fb5  lea     r8d, [r9-1Ch]
0x140019fb9  call    WPP_RECORDER_SF_q
0x140019fbe  mov     rdi, [rbx+38h]
0x140019fc2  lea     rcx, [rdi+38h]; SpinLock
0x140019fc6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019fcd  nop     dword ptr [rax+rax+00h]
0x140019fd2  mov     [rdi+40h], al
0x140019fd5  mov     rcx, [rbx]
0x140019fd8  cmp     [rcx+8], rbx
0x140019fdc  jnz     loc_14001A11D
0x140019fe2  mov     rax, [rbx+8]
0x140019fe6  cmp     [rax], rbx
0x140019fe9  jnz     loc_14001A11D
0x140019fef  mov     [rax], rcx
0x140019ff2  mov     [rcx+8], rax
0x140019ff6  lea     rcx, [rbx+48h]
0x140019ffa  mov     [rbx+8], rbx
0x140019ffe  mov     [rbx], rbx
0x14001a001  mov     rax, [rcx]
0x14001a004  cmp     rax, rcx
0x14001a007  jnz     short loc_14001A00D
0x14001a009  xor     esi, esi
0x14001a00b  jmp     short loc_14001A039
0x14001a00d  cmp     [rax+8], rcx
0x14001a011  jnz     loc_14001A11D
0x14001a017  mov     rdx, [rax]
0x14001a01a  cmp     [rdx+8], rax
0x14001a01e  jnz     loc_14001A11D
0x14001a024  mov     [rcx], rdx
0x14001a027  lea     rsi, [rax-118h]
0x14001a02e  mov     [rdx+8], rcx
0x14001a032  mov     [rax+8], rax
0x14001a036  mov     [rax], rax
0x14001a039  xor     bpl, bpl
0x14001a03c  lea     rax, [rdi+50h]
0x14001a040  cmp     [rax], rax
0x14001a043  jnz     short loc_14001A068
0x14001a045  mov     edx, 5
0x14001a04a  cmp     [rdi+30h], edx
0x14001a04d  jge     short loc_14001A068
0x14001a04f  test    rbx, rbx
0x14001a052  jz      short loc_14001A05D
0x14001a054  cmp     [rbx+0BAh], bpl
0x14001a05b  jz      short loc_14001A060
0x14001a05d  mov     bpl, 1
0x14001a060  mov     rcx, rdi
0x14001a063  call    RfcommSetState
0x14001a068  mov     dl, [rdi+40h]; NewIrql
0x14001a06b  lea     rcx, [rdi+38h]; SpinLock
0x14001a06f  call    cs:__imp_KeReleaseSpinLock
0x14001a076  nop     dword ptr [rax+rax+00h]
0x14001a07b  mov     rcx, [rdi+48h]
0x14001a07f  call    RfcommStartTimer
0x14001a084  test    bpl, bpl
0x14001a087  jz      short loc_14001A091
0x14001a089  mov     rcx, rdi
0x14001a08c  call    SessionDisconnectRequest
0x14001a091  test    rsi, rsi
0x14001a094  jz      short loc_14001A0B9
0x14001a096  mov     rcx, rsi
0x14001a099  call    ChannelConnect
0x14001a09e  lea     rcx, [rsi+18h]
0x14001a0a2  mov     edx, 4E4E4F43h
0x14001a0a7  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001a0ae  mov     r8d, 3EAh
0x14001a0b4  call    RefObj_ReleaseEx
0x14001a0b9  lea     rcx, [rdi+18h]
0x14001a0bd  mov     edx, 4E414843h
0x14001a0c2  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001a0c9  mov     r8d, 3EDh
0x14001a0cf  call    RefObj_ReleaseEx
0x14001a0d4  xor     edx, edx; Tag
0x14001a0d6  mov     rcx, rbx; P
0x14001a0d9  call    cs:__imp_ExFreePoolWithTag
0x14001a0e0  nop     dword ptr [rax+rax+00h]
0x14001a0e5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001a0ec  jz      short loc_14001A10D
0x14001a0ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a0f5  mov     r9d, 20h ; ' '
0x14001a0fb  mov     [rsp+68h+var_48], r12
0x14001a100  mov     rcx, [rcx+40h]
0x14001a104  lea     r8d, [r9-1Dh]
0x14001a108  call    WPP_RECORDER_SF_
0x14001a10d  add     rsp, 30h
0x14001a111  pop     r14
0x14001a113  pop     r13
0x14001a115  pop     r12
0x14001a117  pop     rdi
0x14001a118  pop     rsi
0x14001a119  pop     rbp
0x14001a11a  pop     rbx
0x14001a11b  retn
0x14001a11d  mov     ecx, 3
0x14001a122  int     29h; Win8: RtlFailFast(ecx)
```
