# PxClIncomingCloseCall

- ea: `0x14000fbb0`
- end: `0x14000fca0`
- name: `PxClIncomingCloseCall`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140001bc8`
- `0x140006e08`
- `0x14000fbb0`
- `0x140015290`
- `0x1400156d8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fc47`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fc47`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fc83`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fc83`

## pseudocode

```c
void __fastcall PxClIncomingCloseCall(__int64 a1, unsigned __int64 a2)
{
  _DWORD *v3; // rbx
  __int64 v4; // r8
  PVOID Entry[3]; // [rsp+20h] [rbp-18h] BYREF

  Entry[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids, a2);
  GetVcFromCtx(a2, Entry);
  v3 = Entry[0];
  if ( Entry[0] )
  {
    *((_BYTE *)v3 + 520) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry[0] + 64);
    v3[9] |= 1u;
    PxVcCleanup((__int64)v3, 8, v4);
    if ( v3[7]-- == 1 )
      DoDerefVcWork(v3);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)v3 + 64, *((_BYTE *)v3 + 520));
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (unsigned int)(LODWORD(Entry[0]) + 38),
      WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids,
      a2);
  }
}

```

## disassembly

```asm
0x14000fbb0  mov     [rsp+arg_0], rbx
0x14000fbb5  mov     [rsp+arg_8], rsi
0x14000fbba  push    rdi
0x14000fbbb  sub     rsp, 30h
0x14000fbbf  mov     rdi, rdx
0x14000fbc2  mov     [rsp+38h+Entry], 0
0x14000fbcb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fbd2  lea     rsi, WPP_GLOBAL_Control
0x14000fbd9  cmp     rcx, rsi
0x14000fbdc  jz      short loc_14000FBFC
0x14000fbde  cmp     byte ptr [rcx+29h], 5
0x14000fbe2  jb      short loc_14000FBFC
0x14000fbe4  mov     rcx, [rcx+18h]
0x14000fbe8  lea     r8, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x14000fbef  mov     edx, 25h ; '%'
0x14000fbf4  mov     r9, rdi
0x14000fbf7  call    WPP_SF_q
0x14000fbfc  lea     rdx, [rsp+38h+Entry]
0x14000fc01  mov     rcx, rdi
0x14000fc04  call    GetVcFromCtx
0x14000fc09  mov     rbx, [rsp+38h+Entry]
0x14000fc0e  test    rbx, rbx
0x14000fc11  jnz     short loc_14000FC3D
0x14000fc13  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc1a  cmp     rcx, rsi
0x14000fc1d  jz      short loc_14000FC8F
0x14000fc1f  cmp     byte ptr [rcx+29h], 3
0x14000fc23  jb      short loc_14000FC8F
0x14000fc25  mov     rcx, [rcx+18h]
0x14000fc29  lea     edx, [rbx+26h]
0x14000fc2c  mov     r9, rdi
0x14000fc2f  lea     r8, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x14000fc36  call    WPP_SF_q
0x14000fc3b  jmp     short loc_14000FC8F
0x14000fc3d  lea     rdi, [rbx+200h]
0x14000fc44  mov     rcx, rdi; SpinLock
0x14000fc47  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fc4e  nop     dword ptr [rax+rax+00h]
0x14000fc53  mov     [rbx+208h], al
0x14000fc59  mov     edx, 8
0x14000fc5e  or      dword ptr [rbx+24h], 1
0x14000fc62  mov     rcx, rbx
0x14000fc65  call    PxVcCleanup
0x14000fc6a  add     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x14000fc6e  jnz     short loc_14000FC7A
0x14000fc70  mov     rcx, rbx; Entry
0x14000fc73  call    DoDerefVcWork
0x14000fc78  jmp     short loc_14000FC8F
0x14000fc7a  mov     dl, [rbx+208h]; NewIrql
0x14000fc80  mov     rcx, rdi; SpinLock
0x14000fc83  call    cs:__imp_KeReleaseSpinLock
0x14000fc8a  nop     dword ptr [rax+rax+00h]
0x14000fc8f  mov     rbx, [rsp+38h+arg_0]
0x14000fc94  mov     rsi, [rsp+38h+arg_8]
0x14000fc99  add     rsp, 30h
0x14000fc9d  pop     rdi
0x14000fc9e  retn
```
