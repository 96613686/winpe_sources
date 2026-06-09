# NatDeleteDirector

- ea: `0x140001480`
- end: `0x140001637`
- name: `NatDeleteDirector`
- size: `439`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001640`

## callees

- `0x140001030`
- `0x140001480`
- `0x14000218c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140001580`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001580`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001545`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001545`

## pseudocode

```c
__int64 __fastcall NatDeleteDirector(PVOID **P)
{
  KIRQL v3; // al
  PVOID *v4; // r8
  PVOID *v5; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
  }
  if ( P )
  {
    _InterlockedDecrement((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1);
    v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredRoutine);
    v4 = *P;
    if ( (*P)[1] != P || (v5 = P[1], *v5 != P) )
      __fastfail(3u);
    *v5 = v4;
    v4[1] = v5;
    *((_DWORD *)P + 12) |= 0x80000000;
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredRoutine, v3);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 5, 0xFFFFFFFF) <= 1 )
    {
      NatCleanupDirector(P);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
      }
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
        }
      }
      return 259;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
      }
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x140001480  mov     [rsp+arg_0], rbx
0x140001485  mov     [rsp+arg_8], rbp
0x14000148a  push    rsi
0x14000148b  sub     rsp, 20h
0x14000148f  mov     rbx, rcx
0x140001492  mov     rcx, cs:WPP_GLOBAL_Control
0x140001499  lea     rsi, WPP_GLOBAL_Control
0x1400014a0  lea     rbp, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids
0x1400014a7  cmp     rcx, rsi
0x1400014aa  jz      short loc_1400014CA
0x1400014ac  mov     eax, [rcx+2Ch]
0x1400014af  test    al, 1
0x1400014b1  jz      short loc_1400014CA
0x1400014b3  cmp     byte ptr [rcx+29h], 6
0x1400014b7  jb      short loc_1400014CA
0x1400014b9  mov     rcx, [rcx+18h]
0x1400014bd  mov     edx, 14h
0x1400014c2  mov     r8, rbp
0x1400014c5  call    WPP_SF_
0x1400014ca  test    rbx, rbx
0x1400014cd  jnz     short loc_140001537
0x1400014cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400014d6  cmp     rcx, rsi
0x1400014d9  jz      short loc_140001521
0x1400014db  mov     eax, [rcx+2Ch]
0x1400014de  test    al, 1
0x1400014e0  jz      short loc_1400014F7
0x1400014e2  cmp     byte ptr [rcx+29h], 2
0x1400014e6  jb      short loc_1400014F7
0x1400014e8  mov     rcx, [rcx+18h]
0x1400014ec  lea     edx, [rbx+15h]
0x1400014ef  mov     r8, rbp
0x1400014f2  call    WPP_SF_
0x1400014f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400014fe  cmp     rcx, rsi
0x140001501  jz      short loc_140001521
0x140001503  mov     eax, [rcx+2Ch]
0x140001506  test    al, 1
0x140001508  jz      short loc_140001521
0x14000150a  cmp     byte ptr [rcx+29h], 6
0x14000150e  jb      short loc_140001521
0x140001510  mov     rcx, [rcx+18h]
0x140001514  mov     edx, 16h
0x140001519  mov     r8, rbp
0x14000151c  call    WPP_SF_
0x140001521  mov     eax, 0C000000Dh
0x140001526  mov     rbx, [rsp+28h+arg_0]
0x14000152b  mov     rbp, [rsp+28h+arg_8]
0x140001530  add     rsp, 20h
0x140001534  pop     rsi
0x140001535  retn
0x140001537  lock dec dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h+4
0x14000153e  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; SpinLock
0x140001545  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000154c  nop     dword ptr [rax+rax+00h]
0x140001551  mov     r8, [rbx]
0x140001554  cmp     [r8+8], rbx
0x140001558  jnz     loc_140001630
0x14000155e  mov     rdx, [rbx+8]
0x140001562  cmp     [rdx], rbx
0x140001565  jnz     loc_140001630
0x14000156b  mov     [rdx], r8
0x14000156e  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; SpinLock
0x140001575  mov     [r8+8], rdx
0x140001579  mov     dl, al; NewIrql
0x14000157b  bts     dword ptr [rbx+30h], 1Fh
0x140001580  call    cs:__imp_KeReleaseSpinLock
0x140001587  nop     dword ptr [rax+rax+00h]
0x14000158c  or      eax, 0FFFFFFFFh
0x14000158f  lock xadd [rbx+14h], eax
0x140001594  sub     eax, 1
0x140001597  jle     short loc_1400015F7
0x140001599  mov     rcx, cs:WPP_GLOBAL_Control
0x1400015a0  cmp     rcx, rsi
0x1400015a3  jz      short loc_1400015ED
0x1400015a5  mov     eax, [rcx+2Ch]
0x1400015a8  test    al, 1
0x1400015aa  jz      short loc_1400015C3
0x1400015ac  cmp     byte ptr [rcx+29h], 5
0x1400015b0  jb      short loc_1400015C3
0x1400015b2  mov     rcx, [rcx+18h]
0x1400015b6  mov     edx, 17h
0x1400015bb  mov     r8, rbp
0x1400015be  call    WPP_SF_
0x1400015c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400015ca  cmp     rcx, rsi
0x1400015cd  jz      short loc_1400015ED
0x1400015cf  mov     eax, [rcx+2Ch]
0x1400015d2  test    al, 1
0x1400015d4  jz      short loc_1400015ED
0x1400015d6  cmp     byte ptr [rcx+29h], 6
0x1400015da  jb      short loc_1400015ED
0x1400015dc  mov     rcx, [rcx+18h]
0x1400015e0  mov     edx, 18h
0x1400015e5  mov     r8, rbp
0x1400015e8  call    WPP_SF_
0x1400015ed  mov     eax, 103h
0x1400015f2  jmp     loc_140001526
0x1400015f7  mov     rcx, rbx; P
0x1400015fa  call    NatCleanupDirector
0x1400015ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140001606  cmp     rcx, rsi
0x140001609  jz      short loc_140001629
0x14000160b  mov     eax, [rcx+2Ch]
0x14000160e  test    al, 1
0x140001610  jz      short loc_140001629
0x140001612  cmp     byte ptr [rcx+29h], 6
0x140001616  jb      short loc_140001629
0x140001618  mov     rcx, [rcx+18h]
0x14000161c  mov     edx, 19h
0x140001621  mov     r8, rbp
0x140001624  call    WPP_SF_
0x140001629  xor     eax, eax
0x14000162b  jmp     loc_140001526
0x140001630  mov     ecx, 3
0x140001635  int     29h; Win8: RtlFailFast(ecx)
```
