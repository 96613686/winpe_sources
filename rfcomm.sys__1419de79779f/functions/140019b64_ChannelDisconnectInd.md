# ChannelDisconnectInd

- ea: `0x140019b64`
- end: `0x140019cc9`
- name: `ChannelDisconnectInd`
- size: `357`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001127c`
- `0x14001138c`
- `0x140012590`
- `0x14001291c`
- `0x140014210`
- `0x140017db4`

## callees

- `0x140004a68`
- `0x1400051b4`
- `0x140015688`
- `0x1400197ec`
- `0x140019b64`
- `0x14001a164`
- `0x14001bfa8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019bc1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019c28`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019bc1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019c28`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019c0e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019c4b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019c0e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019c4b`

## pseudocode

```c
__int64 __fastcall ChannelDisconnectInd(__int64 a1, int a2, unsigned int a3)
{
  __int64 v3; // rdi
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  void *DeviceExtension; // rbx
  const char *v11; // rax
  __int64 v12; // rdx
  int v14; // ecx
  int v15; // ecx

  v3 = *(_QWORD *)(a1 + 56);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3u,
      0x1Au,
      (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids,
      a1);
  *(_BYTE *)(v3 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 56));
  v7 = *(_DWORD *)(a1 + 48);
  if ( v7 > 5 )
  {
    v14 = v7 - 6;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( v15 )
      {
        if ( v15 == 2 )
          goto LABEL_12;
        goto LABEL_10;
      }
    }
    goto LABEL_9;
  }
  if ( v7 == 5 )
    goto LABEL_9;
  if ( !v7 )
    goto LABEL_12;
  v8 = v7 - 1;
  if ( !v8 )
    goto LABEL_12;
  v9 = v8 - 1;
  if ( !v9 )
    goto LABEL_12;
  if ( (unsigned int)(v9 - 1) <= 1 )
LABEL_9:
    ChannelSetState(a1, 8);
LABEL_10:
  if ( a2 == 4 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 56), *(_BYTE *)(v3 + 64));
    RfcommSendUA(v3, a1);
    *(_BYTE *)(v3 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 56));
  }
LABEL_12:
  ChannelDisconnect(a1, a3, 1);
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 56), *(_BYTE *)(v3 + 64));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    v11 = NtStatusTxt(0);
    WPP_RECORDER_SF_s(
      (__int64)DeviceExtension,
      v12,
      3u,
      0x1Bu,
      (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids,
      v11);
  }
  return 0;
}

```

## disassembly

```asm
0x140019b64  push    rbx
0x140019b66  push    rbp
0x140019b67  push    rsi
0x140019b68  push    rdi
0x140019b69  push    r12
0x140019b6b  push    r13
0x140019b6d  push    r14
0x140019b6f  sub     rsp, 30h
0x140019b73  mov     rdi, [rcx+38h]
0x140019b77  mov     r14d, r8d
0x140019b7a  mov     ebp, edx
0x140019b7c  mov     rbx, rcx
0x140019b7f  lea     r13, WPP_RECORDER_INITIALIZED
0x140019b86  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140019b8d  lea     r12, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x140019b94  jz      short loc_140019BBA
0x140019b96  mov     [rsp+68h+var_40], rcx
0x140019b9b  mov     r9d, 1Ah
0x140019ba1  mov     rcx, cs:WPP_GLOBAL_Control
0x140019ba8  mov     [rsp+68h+var_48], r12
0x140019bad  lea     r8d, [r9-17h]
0x140019bb1  mov     rcx, [rcx+40h]
0x140019bb5  call    WPP_RECORDER_SF_q
0x140019bba  lea     rsi, [rdi+38h]
0x140019bbe  mov     rcx, rsi; SpinLock
0x140019bc1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019bc8  nop     dword ptr [rax+rax+00h]
0x140019bcd  mov     [rdi+40h], al
0x140019bd0  mov     ecx, [rbx+30h]
0x140019bd3  cmp     ecx, 5
0x140019bd6  jg      loc_140019CA0
0x140019bdc  jz      short loc_140019BF6
0x140019bde  test    ecx, ecx
0x140019be0  jz      short loc_140019C37
0x140019be2  sub     ecx, 1
0x140019be5  jz      short loc_140019C37
0x140019be7  sub     ecx, 1
0x140019bea  jz      short loc_140019C37
0x140019bec  sub     ecx, 1
0x140019bef  jz      short loc_140019BF6
0x140019bf1  cmp     ecx, 1
0x140019bf4  jnz     short loc_140019C03
0x140019bf6  mov     edx, 8
0x140019bfb  mov     rcx, rbx
0x140019bfe  call    ChannelSetState
0x140019c03  cmp     ebp, 4
0x140019c06  jnz     short loc_140019C37
0x140019c08  mov     dl, [rdi+40h]; NewIrql
0x140019c0b  mov     rcx, rsi; SpinLock
0x140019c0e  call    cs:__imp_KeReleaseSpinLock
0x140019c15  nop     dword ptr [rax+rax+00h]
0x140019c1a  mov     rdx, rbx
0x140019c1d  mov     rcx, rdi
0x140019c20  call    RfcommSendUA
0x140019c25  mov     rcx, rsi; SpinLock
0x140019c28  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019c2f  nop     dword ptr [rax+rax+00h]
0x140019c34  mov     [rdi+40h], al
0x140019c37  mov     r8b, 1
0x140019c3a  mov     edx, r14d
0x140019c3d  mov     rcx, rbx
0x140019c40  call    ChannelDisconnect
0x140019c45  mov     dl, [rdi+40h]; NewIrql
0x140019c48  mov     rcx, rsi; SpinLock
0x140019c4b  call    cs:__imp_KeReleaseSpinLock
0x140019c52  nop     dword ptr [rax+rax+00h]
0x140019c57  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140019c5e  jz      short loc_140019C8E
0x140019c60  mov     rax, cs:WPP_GLOBAL_Control
0x140019c67  xor     ecx, ecx
0x140019c69  mov     rbx, [rax+40h]
0x140019c6d  call    NtStatusTxt
0x140019c72  mov     r9d, 1Bh
0x140019c78  mov     [rsp+68h+var_40], rax
0x140019c7d  mov     rcx, rbx
0x140019c80  mov     [rsp+68h+var_48], r12
0x140019c85  lea     r8d, [r9-18h]
0x140019c89  call    WPP_RECORDER_SF_s
0x140019c8e  xor     eax, eax
0x140019c90  add     rsp, 30h
0x140019c94  pop     r14
0x140019c96  pop     r13
0x140019c98  pop     r12
0x140019c9a  pop     rdi
0x140019c9b  pop     rsi
0x140019c9c  pop     rbp
0x140019c9d  pop     rbx
0x140019c9e  retn
0x140019ca0  sub     ecx, 6
0x140019ca3  jz      loc_140019BF6
0x140019ca9  sub     ecx, 1
0x140019cac  jz      loc_140019BF6
0x140019cb2  sub     ecx, 1
0x140019cb5  jz      loc_140019C03
0x140019cbb  cmp     ecx, 1
0x140019cbe  jz      loc_140019C37
0x140019cc4  jmp     loc_140019C03
```
