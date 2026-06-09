# PxTapiOpen

- ea: `0x1400146c0`
- end: `0x1400148db`
- name: `PxTapiOpen`
- size: `539`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001b54`
- `0x140001b84`
- `0x140006c1c`
- `0x1400081c0`
- `0x140011194`
- `0x1400146c0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014789`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400147db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014789`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400147db`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400147b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014847`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014869`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001487f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014892`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400147b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014847`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014869`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001487f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014892`
- `NDIS!NdisMSleep` at `0x1400147ca`
- `NDIS!NdisMSleep` at `0x1400147ca`

## pseudocode

```c
__int64 __fastcall PxTapiOpen(__int64 a1)
{
  _BYTE *v3; // rsi
  KSPIN_LOCK *v4; // rbp
  KIRQL v5; // al
  KIRQL v6; // dl
  int v7; // ebx
  KIRQL v8; // al
  __int64 v9; // rbx
  bool v10; // zf
  KIRQL v11; // dl
  KIRQL v12; // dl
  PVOID P; // [rsp+40h] [rbp+8h] BYREF

  P = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
  if ( IsTapiDeviceValid(*(_DWORD *)(a1 + 52), (struct _SINGLE_LIST_ENTRY **)&P) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        110,
        WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids,
        *(unsigned int *)(a1 + 52));
    v3 = P;
    v4 = (KSPIN_LOCK *)((char *)P + 120);
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 15);
    v3[128] = v5;
    v6 = v5;
    if ( (*(_DWORD *)(*((_QWORD *)v3 + 10) + 56LL) & 4) != 0 )
    {
LABEL_16:
      *((_QWORD *)v3 + 5) = *(_QWORD *)(a1 + 56);
      ++*(_DWORD *)(*((_QWORD *)v3 + 10) + 12LL);
      *(_QWORD *)(a1 + 64) = *((unsigned int *)v3 + 12);
      v9 = *(_QWORD *)(*((_QWORD *)v3 + 3) + 24LL);
      memmove((void *)(a1 + 72), (const void *)(v9 + 152), 0x10u);
      *(_DWORD *)(a1 + 88) = *(_DWORD *)(v9 + 172);
      v10 = (*((_DWORD *)v3 + 4))-- == 1;
      v11 = v3[128];
      if ( v10 )
      {
        KeReleaseSpinLock(v4, v11);
        FreeTapiLine(v3);
      }
      else
      {
        KeReleaseSpinLock(v4, v11);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
      return 0;
    }
    else
    {
      v7 = 10;
      while ( v7 )
      {
        KeReleaseSpinLock(v4, v6);
        NdisMSleep(0x7A120u);
        --v7;
        v8 = KeAcquireSpinLockRaiseToDpc(v4);
        v3[128] = v8;
        v6 = v8;
        if ( (*(_DWORD *)(*((_QWORD *)v3 + 10) + 56LL) & 4) != 0 )
          goto LABEL_16;
      }
      v10 = (*((_DWORD *)v3 + 4))-- == 1;
      v12 = v3[128];
      if ( v10 )
      {
        KeReleaseSpinLock(v4, v12);
        FreeTapiLine(v3);
      }
      else
      {
        KeReleaseSpinLock(v4, v12);
      }
      return 4099;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        109,
        WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids,
        *(unsigned int *)(a1 + 52));
    return 4098;
  }
}

```

## disassembly

```asm
0x1400146c0  mov     [rsp+arg_8], rbx
0x1400146c5  mov     [rsp+arg_10], rbp
0x1400146ca  push    rsi
0x1400146cb  push    rdi
0x1400146cc  push    r14
0x1400146ce  sub     rsp, 20h
0x1400146d2  mov     rdi, rcx
0x1400146d5  mov     [rsp+38h+P], 0
0x1400146de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400146e5  lea     r14, WPP_GLOBAL_Control
0x1400146ec  cmp     rcx, r14
0x1400146ef  jz      short loc_14001470C
0x1400146f1  cmp     byte ptr [rcx+29h], 5
0x1400146f5  jb      short loc_14001470C
0x1400146f7  mov     rcx, [rcx+18h]
0x1400146fb  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140014702  mov     edx, 6Ch ; 'l'
0x140014707  call    WPP_SF_
0x14001470c  mov     ecx, [rdi+34h]
0x14001470f  lea     rdx, [rsp+38h+P]
0x140014714  call    IsTapiDeviceValid
0x140014719  test    al, al
0x14001471b  jnz     short loc_140014752
0x14001471d  mov     rcx, cs:WPP_GLOBAL_Control
0x140014724  cmp     rcx, r14
0x140014727  jz      short loc_140014748
0x140014729  cmp     byte ptr [rcx+29h], 5
0x14001472d  jb      short loc_140014748
0x14001472f  mov     r9d, [rdi+34h]
0x140014733  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x14001473a  mov     rcx, [rcx+18h]
0x14001473e  mov     edx, 6Dh ; 'm'
0x140014743  call    WPP_SF_d
0x140014748  mov     eax, 1002h
0x14001474d  jmp     loc_1400148C7
0x140014752  mov     rcx, cs:WPP_GLOBAL_Control
0x140014759  cmp     rcx, r14
0x14001475c  jz      short loc_14001477D
0x14001475e  cmp     byte ptr [rcx+29h], 4
0x140014762  jb      short loc_14001477D
0x140014764  mov     r9d, [rdi+34h]
0x140014768  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x14001476f  mov     rcx, [rcx+18h]
0x140014773  mov     edx, 6Eh ; 'n'
0x140014778  call    WPP_SF_d
0x14001477d  mov     rsi, [rsp+38h+P]
0x140014782  lea     rbp, [rsi+78h]
0x140014786  mov     rcx, rbp; SpinLock
0x140014789  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014790  nop     dword ptr [rax+rax+00h]
0x140014795  mov     [rsi+80h], al
0x14001479b  mov     dl, al; NewIrql
0x14001479d  mov     rax, [rsi+50h]
0x1400147a1  mov     ecx, [rax+38h]
0x1400147a4  test    cl, 4
0x1400147a7  jnz     short loc_1400147FB
0x1400147a9  mov     ebx, 0Ah
0x1400147ae  mov     rcx, rbp; SpinLock
0x1400147b1  test    ebx, ebx
0x1400147b3  jz      loc_14001485D
0x1400147b9  call    cs:__imp_KeReleaseSpinLock
0x1400147c0  nop     dword ptr [rax+rax+00h]
0x1400147c5  mov     ecx, 7A120h; MicrosecondsToSleep
0x1400147ca  call    cs:__imp_NdisMSleep
0x1400147d1  nop     dword ptr [rax+rax+00h]
0x1400147d6  mov     rcx, rbp; SpinLock
0x1400147d9  dec     ebx
0x1400147db  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400147e2  nop     dword ptr [rax+rax+00h]
0x1400147e7  mov     [rsi+80h], al
0x1400147ed  mov     dl, al
0x1400147ef  mov     rax, [rsi+50h]
0x1400147f3  mov     ecx, [rax+38h]
0x1400147f6  test    cl, 4
0x1400147f9  jz      short loc_1400147AE
0x1400147fb  mov     rax, [rdi+38h]
0x1400147ff  lea     rcx, [rdi+48h]; void *
0x140014803  mov     [rsi+28h], rax
0x140014807  mov     r8d, 10h; Size
0x14001480d  mov     rax, [rsi+50h]
0x140014811  inc     dword ptr [rax+0Ch]
0x140014814  mov     eax, [rsi+30h]
0x140014817  mov     [rdi+40h], rax
0x14001481b  mov     rax, [rsi+18h]
0x14001481f  mov     rbx, [rax+18h]
0x140014823  lea     rdx, [rbx+98h]; Src
0x14001482a  call    memmove
0x14001482f  mov     eax, [rbx+0ACh]
0x140014835  mov     rcx, rbp; SpinLock
0x140014838  mov     [rdi+58h], eax
0x14001483b  add     dword ptr [rsi+10h], 0FFFFFFFFh
0x14001483f  mov     dl, [rsi+80h]; NewIrql
0x140014845  jnz     short loc_140014892
0x140014847  call    cs:__imp_KeReleaseSpinLock
0x14001484e  nop     dword ptr [rax+rax+00h]
0x140014853  mov     rcx, rsi; P
0x140014856  call    FreeTapiLine
0x14001485b  jmp     short loc_14001489E
0x14001485d  add     dword ptr [rsi+10h], 0FFFFFFFFh
0x140014861  mov     dl, [rsi+80h]; NewIrql
0x140014867  jnz     short loc_14001487F
0x140014869  call    cs:__imp_KeReleaseSpinLock
0x140014870  nop     dword ptr [rax+rax+00h]
0x140014875  mov     rcx, rsi; P
0x140014878  call    FreeTapiLine
0x14001487d  jmp     short loc_14001488B
0x14001487f  call    cs:__imp_KeReleaseSpinLock
0x140014886  nop     dword ptr [rax+rax+00h]
0x14001488b  mov     eax, 1003h
0x140014890  jmp     short loc_1400148C7
0x140014892  call    cs:__imp_KeReleaseSpinLock
0x140014899  nop     dword ptr [rax+rax+00h]
0x14001489e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400148a5  cmp     rcx, r14
0x1400148a8  jz      short loc_1400148C5
0x1400148aa  cmp     byte ptr [rcx+29h], 5
0x1400148ae  jb      short loc_1400148C5
0x1400148b0  mov     rcx, [rcx+18h]
0x1400148b4  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x1400148bb  mov     edx, 6Fh ; 'o'
0x1400148c0  call    WPP_SF_
0x1400148c5  xor     eax, eax
0x1400148c7  mov     rbx, [rsp+38h+arg_8]
0x1400148cc  mov     rbp, [rsp+38h+arg_10]
0x1400148d1  add     rsp, 20h
0x1400148d5  pop     r14
0x1400148d7  pop     rdi
0x1400148d8  pop     rsi
0x1400148d9  retn
```
