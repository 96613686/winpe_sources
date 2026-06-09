# CtlDisconnectCall

- ea: `0x140012798`
- end: `0x140012ab6`
- name: `CtlDisconnectCall`
- size: `798`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x140002e78`
- `0x140005bf0`

## callees

- `0x140003d58`
- `0x140003e08`
- `0x140004374`
- `0x1400076d0`
- `0x140007710`
- `0x140007ac0`
- `0x14000f0d8`
- `0x140011b90`
- `0x140011c00`
- `0x140012798`
- `0x140013164`
- `0x1400131e4`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x1400128e1`
- `ntoskrnl!KeResetEvent` at `0x140012a0d`
- `ntoskrnl!KeResetEvent` at `0x1400128e1`
- `ntoskrnl!KeResetEvent` at `0x140012a0d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012866`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012878`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012922`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012952`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012a3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012a71`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012a83`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012866`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012878`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012922`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012952`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012a3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012a71`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012a83`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012811`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012828`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012896`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001293b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400129f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012811`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012828`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012896`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001293b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400129f7`
- `NDIS!NdisSetTimerObject` at `0x1400128fd`
- `NDIS!NdisSetTimerObject` at `0x140012a29`
- `NDIS!NdisSetTimerObject` at `0x1400128fd`
- `NDIS!NdisSetTimerObject` at `0x140012a29`

## pseudocode

```c
__int64 __fastcall CtlDisconnectCall(__int64 a1)
{
  __int64 v1; // r14
  KIRQL v3; // al
  __int64 v4; // rbx
  __int64 v5; // rsi
  char v6; // r12
  unsigned int v7; // r15d
  __int64 v8; // rax
  __int64 v9; // rbp
  struct _DEVICE_OBJECT *AttachedDevice; // rdi
  __int64 StringFromSockAddr; // rax
  _BYTE v13[80]; // [rsp+30h] [rbp-A8h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  memset(v13, 0, 0x41u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x5Bu,
      (__int64)WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids);
  }
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  v4 = *(_QWORD *)(a1 + 56);
  *(_BYTE *)(a1 + 104) = v3;
  *(_BYTE *)(v4 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 8));
  v5 = *(_QWORD *)(a1 + 80);
  if ( v5 && *(_DWORD *)(v5 + 32) == 1414550608 )
  {
    v6 = 0;
    v7 = 0;
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 16));
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 56) + 8LL), *(_BYTE *)(*(_QWORD *)(a1 + 56) + 16LL));
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
    CallDisconnectFromCtl(a1, v5);
    *(_BYTE *)(v1 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 8));
    if ( *(_QWORD *)(v5 + 56) == v5 + 56 )
    {
      if ( *(_DWORD *)(v5 + 48) == 5 )
      {
        if ( *(_BYTE *)(v5 + 72) )
        {
          KeResetEvent((PRKEVENT)(v5 + 632));
          NdisSetTimerObject(*(NDIS_HANDLE *)(v5 + 600), (LARGE_INTEGER)-300000000LL, 0, 0);
        }
        else
        {
          CtlSetState(v5, 6);
          v6 = 1;
        }
      }
      else
      {
        CtlSetState(v5, 7);
        KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 8), *(_BYTE *)(v1 + 16));
        CtlCleanup(v5, 0);
        *(_BYTE *)(v1 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 8));
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 8), *(_BYTE *)(v1 + 16));
    if ( v6 )
    {
      v8 = CtlAllocPacket(v5, 3);
      v9 = v8;
      if ( v8 )
      {
        *(_BYTE *)(v8 + 12) = 1;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
          StringFromSockAddr = GetStringFromSockAddr(v5 + 368, v13);
          WPP_SF_s(AttachedDevice, 92, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids, StringFromSockAddr);
        }
        CtlSend(v5, v9);
        *(_BYTE *)(v5 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 96));
        KeResetEvent((PRKEVENT)(v5 + 632));
        NdisSetTimerObject(*(NDIS_HANDLE *)(v5 + 600), (LARGE_INTEGER)-300000000LL, 0, 0);
        KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 96), *(_BYTE *)(v5 + 104));
      }
      else
      {
        v7 = -1073741670;
        CtlSetState(v5, 7);
        CtlCleanup(v5, 0);
      }
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 16), 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(__int64))(v5 + 24))(v5);
    return v7;
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 56) + 8LL), *(_BYTE *)(*(_QWORD *)(a1 + 56) + 16LL));
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
    return 0;
  }
}

```

## disassembly

```asm
0x140012798  push    rbx
0x14001279a  push    rbp
0x14001279b  push    rsi
0x14001279c  push    rdi
0x14001279d  push    r12
0x14001279f  push    r13
0x1400127a1  push    r14
0x1400127a3  push    r15
0x1400127a5  sub     rsp, 98h
0x1400127ac  mov     rax, cs:__security_cookie
0x1400127b3  xor     rax, rsp
0x1400127b6  mov     [rsp+0D8h+var_58], rax
0x1400127be  mov     r14, [rcx+38h]
0x1400127c2  xor     edx, edx; Val
0x1400127c4  mov     rdi, rcx
0x1400127c7  lea     rcx, [rsp+0D8h+var_A8]; void *
0x1400127cc  lea     r8d, [rdx+41h]; Size
0x1400127d0  call    memset
0x1400127d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400127dc  lea     r13, WPP_GLOBAL_Control
0x1400127e3  cmp     rcx, r13
0x1400127e6  jz      short loc_14001280A
0x1400127e8  mov     eax, [rcx+2Ch]
0x1400127eb  test    al, 8
0x1400127ed  jz      short loc_14001280A
0x1400127ef  cmp     byte ptr [rcx+29h], 2
0x1400127f3  jb      short loc_14001280A
0x1400127f5  mov     rcx, [rcx+18h]
0x1400127f9  lea     r8, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x140012800  mov     edx, 5Bh ; '['
0x140012805  call    WPP_SF_
0x14001280a  lea     rbp, [rdi+60h]
0x14001280e  mov     rcx, rbp; SpinLock
0x140012811  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012818  nop     dword ptr [rax+rax+00h]
0x14001281d  mov     rbx, [rdi+38h]
0x140012821  mov     [rdi+68h], al
0x140012824  lea     rcx, [rbx+8]; SpinLock
0x140012828  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001282f  nop     dword ptr [rax+rax+00h]
0x140012834  mov     [rbx+10h], al
0x140012837  mov     rsi, [rdi+50h]
0x14001283b  test    rsi, rsi
0x14001283e  jz      loc_140012A66
0x140012844  cmp     dword ptr [rsi+20h], 54505450h
0x14001284b  jnz     loc_140012A66
0x140012851  xor     r12b, r12b
0x140012854  xor     r15d, r15d
0x140012857  lock inc dword ptr [rsi+10h]
0x14001285b  mov     rdx, [rdi+38h]
0x14001285f  lea     rcx, [rdx+8]; SpinLock
0x140012863  mov     dl, [rdx+10h]; NewIrql
0x140012866  call    cs:__imp_KeReleaseSpinLock
0x14001286d  nop     dword ptr [rax+rax+00h]
0x140012872  mov     dl, [rdi+68h]; NewIrql
0x140012875  mov     rcx, rbp; SpinLock
0x140012878  call    cs:__imp_KeReleaseSpinLock
0x14001287f  nop     dword ptr [rax+rax+00h]
0x140012884  mov     rdx, rsi
0x140012887  mov     rcx, rdi
0x14001288a  call    CallDisconnectFromCtl
0x14001288f  lea     rdi, [r14+8]
0x140012893  mov     rcx, rdi; SpinLock
0x140012896  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001289d  nop     dword ptr [rax+rax+00h]
0x1400128a2  mov     [r14+10h], al
0x1400128a6  mov     rbx, 0FFFFFFFFEE1E5D00h
0x1400128ad  lea     rax, [rsi+38h]
0x1400128b1  cmp     [rax], rax
0x1400128b4  jnz     loc_14001294B
0x1400128ba  cmp     dword ptr [rsi+30h], 5
0x1400128be  jnz     short loc_14001290B
0x1400128c0  cmp     [rsi+48h], r12b
0x1400128c4  jnz     short loc_1400128DA
0x1400128c6  mov     r9b, 1
0x1400128c9  lea     edx, [r15+6]
0x1400128cd  mov     rcx, rsi
0x1400128d0  call    CtlSetState
0x1400128d5  mov     r12b, 1
0x1400128d8  jmp     short loc_14001294B
0x1400128da  lea     rcx, [rsi+278h]; Event
0x1400128e1  call    cs:__imp_KeResetEvent
0x1400128e8  nop     dword ptr [rax+rax+00h]
0x1400128ed  mov     rcx, [rsi+258h]; TimerObject
0x1400128f4  xor     r9d, r9d; FunctionContext
0x1400128f7  xor     r8d, r8d; MillisecondsPeriod
0x1400128fa  mov     rdx, rbx; DueTime
0x1400128fd  call    cs:__imp_NdisSetTimerObject
0x140012904  nop     dword ptr [rax+rax+00h]
0x140012909  jmp     short loc_14001294B
0x14001290b  mov     r9b, 1
0x14001290e  mov     edx, 7
0x140012913  mov     rcx, rsi
0x140012916  call    CtlSetState
0x14001291b  mov     dl, [r14+10h]; NewIrql
0x14001291f  mov     rcx, rdi; SpinLock
0x140012922  call    cs:__imp_KeReleaseSpinLock
0x140012929  nop     dword ptr [rax+rax+00h]
0x14001292e  xor     edx, edx
0x140012930  mov     rcx, rsi
0x140012933  call    CtlCleanup
0x140012938  mov     rcx, rdi; SpinLock
0x14001293b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012942  nop     dword ptr [rax+rax+00h]
0x140012947  mov     [r14+10h], al
0x14001294b  mov     dl, [r14+10h]; NewIrql
0x14001294f  mov     rcx, rdi; SpinLock
0x140012952  call    cs:__imp_KeReleaseSpinLock
0x140012959  nop     dword ptr [rax+rax+00h]
0x14001295e  test    r12b, r12b
0x140012961  jz      loc_140012A48
0x140012967  mov     edx, 3
0x14001296c  mov     rcx, rsi
0x14001296f  call    CtlAllocPacket
0x140012974  mov     rbp, rax
0x140012977  test    rax, rax
0x14001297a  jnz     short loc_14001299F
0x14001297c  xor     r9d, r9d
0x14001297f  lea     edx, [rax+7]
0x140012982  mov     rcx, rsi
0x140012985  mov     r15d, 0C000009Ah
0x14001298b  call    CtlSetState
0x140012990  xor     edx, edx
0x140012992  mov     rcx, rsi
0x140012995  call    CtlCleanup
0x14001299a  jmp     loc_140012A48
0x14001299f  mov     byte ptr [rax+0Ch], 1
0x1400129a3  mov     rdi, cs:WPP_GLOBAL_Control
0x1400129aa  cmp     rdi, r13
0x1400129ad  jz      short loc_1400129E8
0x1400129af  mov     eax, [rdi+2Ch]
0x1400129b2  test    al, 8
0x1400129b4  jz      short loc_1400129E8
0x1400129b6  cmp     byte ptr [rdi+29h], 2
0x1400129ba  jb      short loc_1400129E8
0x1400129bc  mov     rdi, [rdi+18h]
0x1400129c0  lea     rcx, [rsi+170h]
0x1400129c7  lea     rdx, [rsp+0D8h+var_A8]
0x1400129cc  call    GetStringFromSockAddr
0x1400129d1  mov     r9, rax
0x1400129d4  lea     r8, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x1400129db  mov     edx, 5Ch ; '\'
0x1400129e0  mov     rcx, rdi
0x1400129e3  call    WPP_SF_s
0x1400129e8  mov     rdx, rbp
0x1400129eb  mov     rcx, rsi
0x1400129ee  call    CtlSend
0x1400129f3  lea     rcx, [rsi+60h]; SpinLock
0x1400129f7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400129fe  nop     dword ptr [rax+rax+00h]
0x140012a03  lea     rcx, [rsi+278h]; Event
0x140012a0a  mov     [rsi+68h], al
0x140012a0d  call    cs:__imp_KeResetEvent
0x140012a14  nop     dword ptr [rax+rax+00h]
0x140012a19  mov     rcx, [rsi+258h]; TimerObject
0x140012a20  xor     r9d, r9d; FunctionContext
0x140012a23  xor     r8d, r8d; MillisecondsPeriod
0x140012a26  mov     rdx, rbx; DueTime
0x140012a29  call    cs:__imp_NdisSetTimerObject
0x140012a30  nop     dword ptr [rax+rax+00h]
0x140012a35  mov     dl, [rsi+68h]; NewIrql
0x140012a38  lea     rcx, [rsi+60h]; SpinLock
0x140012a3c  call    cs:__imp_KeReleaseSpinLock
0x140012a43  nop     dword ptr [rax+rax+00h]
0x140012a48  or      edx, 0FFFFFFFFh
0x140012a4b  lock xadd [rsi+10h], edx
0x140012a50  cmp     edx, 1
0x140012a53  jnz     short loc_140012A61
0x140012a55  mov     rax, [rsi+18h]
0x140012a59  mov     rcx, rsi
0x140012a5c  call    _guard_dispatch_icall
0x140012a61  mov     eax, r15d
0x140012a64  jmp     short loc_140012A91
0x140012a66  mov     rdx, [rdi+38h]
0x140012a6a  lea     rcx, [rdx+8]; SpinLock
0x140012a6e  mov     dl, [rdx+10h]; NewIrql
0x140012a71  call    cs:__imp_KeReleaseSpinLock
0x140012a78  nop     dword ptr [rax+rax+00h]
0x140012a7d  mov     dl, [rdi+68h]; NewIrql
0x140012a80  mov     rcx, rbp; SpinLock
0x140012a83  call    cs:__imp_KeReleaseSpinLock
0x140012a8a  nop     dword ptr [rax+rax+00h]
0x140012a8f  xor     eax, eax
0x140012a91  mov     rcx, [rsp+0D8h+var_58]
0x140012a99  xor     rcx, rsp; StackCookie
0x140012a9c  call    __security_check_cookie
0x140012aa1  add     rsp, 98h
0x140012aa8  pop     r15
0x140012aaa  pop     r14
0x140012aac  pop     r13
0x140012aae  pop     r12
0x140012ab0  pop     rdi
0x140012ab1  pop     rsi
0x140012ab2  pop     rbp
0x140012ab3  pop     rbx
0x140012ab4  retn
```
