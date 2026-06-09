# DereferenceTunnel

- ea: `0x14001ac30`
- end: `0x14001ae39`
- name: `DereferenceTunnel`
- size: `521`
- prototype: ``
- caller_count: `14`
- callee_count: `7`
- tags: ``

## callers

- `0x14000f008`
- `0x14000f2ec`
- `0x14000f898`
- `0x140011070`
- `0x140011518`
- `0x140013bc0`
- `0x140015050`
- `0x1400154b8`
- `0x140017010`
- `0x1400171e0`
- `0x140019940`
- `0x140019a80`
- `0x14001a640`
- `0x14001c050`

## callees

- `0x140001870`
- `0x1400031ec`
- `0x14000328c`
- `0x140018260`
- `0x14001ac30`
- `0x14001c050`
- `0x14001c400`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001aded`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001aded`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ac70`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ac70`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ac47`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ac47`

## pseudocode

```c
__int64 __fastcall DereferenceTunnel(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v3; // rdx
  bool v4; // zf
  unsigned int v5; // edi
  __int64 v6; // rdx
  __int64 v8; // rax
  _QWORD *v9; // rcx
  __int64 v10; // [rsp+40h] [rbp-38h]

  v1 = *(_QWORD *)(a1 + 24);
  *(_BYTE *)(v1 + 152) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 144));
  v4 = (*(_DWORD *)(a1 + 20))-- == 1;
  v5 = *(_DWORD *)(a1 + 20);
  if ( v4 )
  {
    if ( (*(_DWORD *)(a1 + 120) & 0x104) != 0 )
    {
      v8 = *(_QWORD *)a1;
      if ( *(_QWORD *)a1 != a1 )
      {
        if ( *(_QWORD *)(v8 + 8) != a1 || (v9 = *(_QWORD **)(a1 + 8), *v9 != a1) )
          __fastfail(3u);
        *v9 = v8;
        *(_QWORD *)(v8 + 8) = v9;
        *(_QWORD *)(a1 + 8) = a1;
        *(_QWORD *)a1 = a1;
        if ( (*(_DWORD *)(a1 + 120) & 0x10) != 0 )
        {
          LOBYTE(v3) = 1;
          ReferenceTunnel(a1, v3);
          ScheduleTunnelWork(a1, 0, (__int64)L2TPDeleteHostRoute, 0, 0, 0, 0, 1, 0);
        }
        if ( (*(_DWORD *)(a1 + 120) & 1) != 0 )
        {
          LOBYTE(v3) = 1;
          ReferenceTunnel(a1, v3);
          LOBYTE(v10) = 0;
          ScheduleTunnelWork(a1, 0, (__int64)CloseTransport, 0, 0, 0, 0, 1, v10);
        }
      }
    }
    else
    {
      LOBYTE(v3) = 1;
      ReferenceTunnel(a1, v3);
      ScheduleTunnelWork(a1, 0, (__int64)FsmCloseTunnel, 1, 0, 0, 0, 1, 0);
    }
    v5 = *(_DWORD *)(a1 + 20);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 144), *(_BYTE *)(v1 + 152));
  if ( v5 )
    return v5;
  TimerQTerminate(*(_QWORD *)(a1 + 304), v6, v1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qdd(
      WPP_GLOBAL_Control->AttachedDevice,
      36,
      WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids,
      a1,
      *(unsigned __int16 *)(a1 + 114),
      *(unsigned __int16 *)(a1 + 116));
  }
  *(_DWORD *)(a1 + 16) = 810824268;
  ExFreePoolWithTag((PVOID)(a1 - 16), 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids, a1);
  }
  DereferenceAdapter(v1);
  return 0;
}

```

## disassembly

```asm
0x14001ac30  push    rbx
0x14001ac32  push    rbp
0x14001ac33  push    rsi
0x14001ac34  push    rdi
0x14001ac35  sub     rsp, 58h
0x14001ac39  mov     rsi, [rcx+18h]
0x14001ac3d  mov     rbx, rcx
0x14001ac40  lea     rcx, [rsi+90h]; SpinLock
0x14001ac47  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001ac4e  nop     dword ptr [rax+rax+00h]
0x14001ac53  mov     [rsi+98h], al
0x14001ac59  add     dword ptr [rbx+14h], 0FFFFFFFFh
0x14001ac5d  mov     edi, [rbx+14h]
0x14001ac60  jz      short loc_14001AC90
0x14001ac62  movzx   edx, byte ptr [rsi+98h]; NewIrql
0x14001ac69  lea     rcx, [rsi+90h]; SpinLock
0x14001ac70  call    cs:__imp_KeReleaseSpinLock
0x14001ac77  nop     dword ptr [rax+rax+00h]
0x14001ac7c  test    edi, edi
0x14001ac7e  jz      loc_14001AD87
0x14001ac84  mov     eax, edi
0x14001ac86  add     rsp, 58h
0x14001ac8a  pop     rdi
0x14001ac8b  pop     rsi
0x14001ac8c  pop     rbp
0x14001ac8d  pop     rbx
0x14001ac8e  retn
0x14001ac90  test    dword ptr [rbx+78h], 104h
0x14001ac97  jnz     short loc_14001ACDA
0x14001ac99  mov     dl, 1
0x14001ac9b  mov     rcx, rbx
0x14001ac9e  call    ReferenceTunnel
0x14001aca3  mov     byte ptr [rsp+78h+var_38], 0
0x14001aca8  lea     r8, FsmCloseTunnel
0x14001acaf  xor     edi, edi
0x14001acb1  mov     [rsp+78h+var_40], 1
0x14001acb6  mov     [rsp+78h+var_48], rdi
0x14001acbb  mov     r9d, 1
0x14001acc1  mov     [rsp+78h+var_50], rdi
0x14001acc6  mov     [rsp+78h+var_58], rdi
0x14001accb  xor     edx, edx
0x14001accd  mov     rcx, rbx
0x14001acd0  call    ScheduleTunnelWork
0x14001acd5  mov     edi, [rbx+14h]
0x14001acd8  jmp     short loc_14001AC62
0x14001acda  mov     rax, [rbx]
0x14001acdd  cmp     rax, rbx
0x14001ace0  jz      short loc_14001ACD5
0x14001ace2  cmp     [rax+8], rbx
0x14001ace6  jnz     loc_14001AD80
0x14001acec  mov     rcx, [rbx+8]
0x14001acf0  cmp     [rcx], rbx
0x14001acf3  jnz     loc_14001AD80
0x14001acf9  mov     [rcx], rax
0x14001acfc  xor     edi, edi
0x14001acfe  mov     [rax+8], rcx
0x14001ad02  mov     [rbx+8], rbx
0x14001ad06  mov     [rbx], rbx
0x14001ad09  mov     eax, [rbx+78h]
0x14001ad0c  test    al, 10h
0x14001ad0e  jz      short loc_14001AD47
0x14001ad10  mov     dl, 1
0x14001ad12  mov     rcx, rbx
0x14001ad15  call    ReferenceTunnel
0x14001ad1a  mov     byte ptr [rsp+78h+var_38], dil
0x14001ad1f  lea     r8, L2TPDeleteHostRoute
0x14001ad26  mov     [rsp+78h+var_40], 1
0x14001ad2b  xor     r9d, r9d
0x14001ad2e  mov     [rsp+78h+var_48], rdi
0x14001ad33  xor     edx, edx
0x14001ad35  mov     [rsp+78h+var_50], rdi
0x14001ad3a  mov     rcx, rbx
0x14001ad3d  mov     [rsp+78h+var_58], rdi
0x14001ad42  call    ScheduleTunnelWork
0x14001ad47  mov     eax, [rbx+78h]
0x14001ad4a  test    al, 1
0x14001ad4c  jz      short loc_14001ACD5
0x14001ad4e  mov     dl, 1
0x14001ad50  mov     rcx, rbx
0x14001ad53  call    ReferenceTunnel
0x14001ad58  mov     byte ptr [rsp+78h+var_38], dil
0x14001ad5d  lea     r8, CloseTransport
0x14001ad64  mov     [rsp+78h+var_40], 1
0x14001ad69  xor     r9d, r9d
0x14001ad6c  mov     [rsp+78h+var_48], rdi
0x14001ad71  mov     [rsp+78h+var_50], rdi
0x14001ad76  mov     [rsp+78h+var_58], rdi
0x14001ad7b  jmp     loc_14001ACCB
0x14001ad80  mov     ecx, 3
0x14001ad85  int     29h; Win8: RtlFailFast(ecx)
0x14001ad87  mov     rcx, [rbx+130h]
0x14001ad8e  mov     r8, rsi
0x14001ad91  call    TimerQTerminate
0x14001ad96  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ad9d  lea     rdi, WPP_GLOBAL_Control
0x14001ada4  cmp     rcx, rdi
0x14001ada7  jz      short loc_14001ADE0
0x14001ada9  mov     eax, [rcx+2Ch]
0x14001adac  test    al, 1
0x14001adae  jz      short loc_14001ADE0
0x14001adb0  cmp     byte ptr [rcx+29h], 2
0x14001adb4  jb      short loc_14001ADE0
0x14001adb6  movzx   r8d, word ptr [rbx+72h]
0x14001adbb  mov     edx, 24h ; '$'
0x14001adc0  movzx   eax, word ptr [rbx+74h]
0x14001adc4  mov     r9, rbx
0x14001adc7  mov     rcx, [rcx+18h]
0x14001adcb  mov     dword ptr [rsp+78h+var_50], eax
0x14001adcf  mov     dword ptr [rsp+78h+var_58], r8d
0x14001add4  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x14001addb  call    WPP_SF_qdd
0x14001ade0  lea     rcx, [rbx-10h]; P
0x14001ade4  mov     dword ptr [rbx+10h], 3054324Ch
0x14001adeb  xor     edx, edx; Tag
0x14001aded  call    cs:__imp_ExFreePoolWithTag
0x14001adf4  nop     dword ptr [rax+rax+00h]
0x14001adf9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ae00  cmp     rcx, rdi
0x14001ae03  jz      short loc_14001AE2A
0x14001ae05  mov     eax, [rcx+2Ch]
0x14001ae08  test    al, 1
0x14001ae0a  jz      short loc_14001AE2A
0x14001ae0c  cmp     byte ptr [rcx+29h], 2
0x14001ae10  jb      short loc_14001AE2A
0x14001ae12  mov     rcx, [rcx+18h]
0x14001ae16  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x14001ae1d  mov     edx, 25h ; '%'
0x14001ae22  mov     r9, rbx
0x14001ae25  call    WPP_SF_q
0x14001ae2a  mov     rcx, rsi
0x14001ae2d  call    DereferenceAdapter
0x14001ae32  xor     eax, eax
0x14001ae34  jmp     loc_14001AC86
```
