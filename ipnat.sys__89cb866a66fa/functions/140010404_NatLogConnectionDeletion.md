# NatLogConnectionDeletion

- ea: `0x140010404`
- end: `0x140010664`
- name: `NatLogConnectionDeletion`
- size: `608`
- prototype: `void __fastcall(unsigned int, __int64, __int64, unsigned __int16, char, char)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000e378`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x140010404`
- `0x140010c74`
- `0x14002c6d0`
- `0x14002cbc0`

## import_xrefs

- `ntoskrnl!IoWMIWriteEvent` at `0x140010580`
- `ntoskrnl!IoWMIWriteEvent` at `0x140010580`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010504`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010504`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400104e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400104e8`

## pseudocode

```c
void __fastcall NatLogConnectionDeletion(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        char a5,
        char a6)
{
  unsigned int v7; // r14d
  __int16 v8; // si
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  KIRQL v12; // al
  __int64 v13; // r12
  NTSTATUS v14; // eax
  _QWORD WnodeEventItem[8]; // [rsp+40h] [rbp-29h] BYREF

  v7 = a2;
  v8 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_DdDd(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1, (unsigned __int16)a3, a2, a4);
  }
  if ( HIDWORD(NatWmiEnabledEvents) )
  {
    v12 = KeAcquireSpinLockRaiseToDpc(&NatWmiLock);
    v13 = *((_QWORD *)&NatWmiLogHandles + 1);
    KeReleaseSpinLock(&NatWmiLock, v12);
    if ( v13 )
    {
      memset(WnodeEventItem, 0, sizeof(WnodeEventItem));
      LOWORD(WnodeEventItem[0]) = 64;
      WnodeEventItem[3] = ConnectionDeletionEventGuid;
      HIDWORD(WnodeEventItem[0]) = 0;
      HIDWORD(WnodeEventItem[5]) = 655872;
      WnodeEventItem[1] = v13;
      WnodeEventItem[2] = MEMORY[0xFFFFF78000000014];
      BYTE4(WnodeEventItem[7]) = a5;
      BYTE5(WnodeEventItem[7]) = a6;
      WnodeEventItem[6] = __PAIR64__(v7, a1);
      LOWORD(WnodeEventItem[7]) = v8;
      WORD1(WnodeEventItem[7]) = a4;
      v14 = IoWMIWriteEvent(WnodeEventItem);
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            29,
            WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids,
            (unsigned int)v14);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids);
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v11 = 31;
      goto LABEL_28;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v11 = 28;
LABEL_28:
      WPP_SF_(v10->AttachedDevice, v11, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x140010404  mov     [rsp-8+arg_8], rsi
0x140010409  mov     [rsp-8+arg_10], rdi
0x14001040e  push    rbp
0x14001040f  push    r12
0x140010411  push    r13
0x140010413  push    r14
0x140010415  push    r15
0x140010417  lea     rbp, [rsp-27h]
0x14001041c  sub     rsp, 90h
0x140010423  mov     rax, cs:__security_cookie
0x14001042a  xor     rax, rsp
0x14001042d  mov     [rbp+47h+var_30], rax
0x140010431  movzx   edi, r9w
0x140010435  mov     r14d, edx
0x140010438  movzx   esi, r8w
0x14001043c  mov     r15d, ecx
0x14001043f  mov     rcx, cs:WPP_GLOBAL_Control
0x140010446  lea     r12, WPP_GLOBAL_Control
0x14001044d  cmp     rcx, r12
0x140010450  jz      short loc_140010477
0x140010452  mov     eax, [rcx+2Ch]
0x140010455  test    al, 1
0x140010457  jz      short loc_140010477
0x140010459  cmp     byte ptr [rcx+29h], 6
0x14001045d  jb      short loc_140010477
0x14001045f  mov     rcx, [rcx+18h]
0x140010463  mov     r9d, r15d
0x140010466  mov     [rsp+0B0h+var_80], edi
0x14001046a  mov     [rsp+0B0h+var_88], edx
0x14001046e  mov     [rsp+0B0h+var_90], esi
0x140010472  call    WPP_SF_DdDd
0x140010477  cmp     dword ptr cs:NatWmiEnabledEvents+4, 0
0x14001047e  jnz     short loc_1400104E1
0x140010480  mov     rcx, cs:WPP_GLOBAL_Control
0x140010487  cmp     rcx, r12
0x14001048a  jz      loc_14001063A
0x140010490  mov     eax, [rcx+2Ch]
0x140010493  test    al, 1
0x140010495  jz      short loc_1400104B2
0x140010497  cmp     byte ptr [rcx+29h], 2
0x14001049b  jb      short loc_1400104B2
0x14001049d  mov     rcx, [rcx+18h]
0x1400104a1  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x1400104a8  mov     edx, 1Bh
0x1400104ad  call    WPP_SF_
0x1400104b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400104b9  cmp     rcx, r12
0x1400104bc  jz      loc_14001063A
0x1400104c2  mov     eax, [rcx+2Ch]
0x1400104c5  test    al, 1
0x1400104c7  jz      loc_14001063A
0x1400104cd  cmp     byte ptr [rcx+29h], 6
0x1400104d1  jb      loc_14001063A
0x1400104d7  mov     edx, 1Ch
0x1400104dc  jmp     loc_14001062A
0x1400104e1  lea     rcx, NatWmiLock; SpinLock
0x1400104e8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400104ef  nop     dword ptr [rax+rax+00h]
0x1400104f4  mov     r12, qword ptr cs:NatWmiLogHandles+8
0x1400104fb  lea     rcx, NatWmiLock; SpinLock
0x140010502  mov     dl, al; NewIrql
0x140010504  call    cs:__imp_KeReleaseSpinLock
0x14001050b  nop     dword ptr [rax+rax+00h]
0x140010510  test    r12, r12
0x140010513  jz      loc_1400105CE
0x140010519  mov     r13d, 40h ; '@'
0x14001051f  lea     rcx, [rbp+47h+WnodeEventItem]; void *
0x140010523  mov     r8d, r13d; Size
0x140010526  xor     edx, edx; Val
0x140010528  call    memset
0x14001052d  lea     rax, ConnectionDeletionEventGuid
0x140010534  mov     [rbp+47h+WnodeEventItem], r13w
0x140010539  mov     [rbp+47h+var_58], rax
0x14001053d  lea     rcx, [rbp+47h+WnodeEventItem]; WnodeEventItem
0x140010541  mov     [rbp+47h+var_6C], 0
0x140010548  mov     rax, 0FFFFF78000000014h
0x140010552  mov     [rbp+47h+var_44], 0A0200h
0x140010559  mov     [rbp+47h+var_68], r12
0x14001055d  mov     rax, [rax]
0x140010560  mov     [rbp+47h+var_60], rax
0x140010564  mov     al, [rbp+47h+arg_20]
0x140010567  mov     [rbp+47h+var_34], al
0x14001056a  mov     al, [rbp+47h+arg_28]
0x14001056d  mov     [rbp+47h+var_33], al
0x140010570  mov     [rbp+47h+var_40], r15d
0x140010574  mov     [rbp+47h+var_3C], r14d
0x140010578  mov     [rbp+47h+var_38], si
0x14001057c  mov     [rbp+47h+var_36], di
0x140010580  call    cs:__imp_IoWMIWriteEvent
0x140010587  nop     dword ptr [rax+rax+00h]
0x14001058c  test    eax, eax
0x14001058e  jns     short loc_140010605
0x140010590  mov     rcx, cs:WPP_GLOBAL_Control
0x140010597  lea     rdi, WPP_GLOBAL_Control
0x14001059e  cmp     rcx, rdi
0x1400105a1  jz      loc_14001063A
0x1400105a7  mov     edx, [rcx+2Ch]
0x1400105aa  test    dl, 1
0x1400105ad  jz      short loc_14001060C
0x1400105af  cmp     byte ptr [rcx+29h], 2
0x1400105b3  jb      short loc_14001060C
0x1400105b5  mov     rcx, [rcx+18h]
0x1400105b9  lea     edx, [r13-23h]
0x1400105bd  mov     r9d, eax
0x1400105c0  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x1400105c7  call    WPP_SF_d
0x1400105cc  jmp     short loc_14001060C
0x1400105ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400105d5  lea     rdi, WPP_GLOBAL_Control
0x1400105dc  cmp     rcx, rdi
0x1400105df  jz      short loc_14001063A
0x1400105e1  mov     eax, [rcx+2Ch]
0x1400105e4  test    al, 1
0x1400105e6  jz      short loc_14001060C
0x1400105e8  cmp     byte ptr [rcx+29h], 2
0x1400105ec  jb      short loc_14001060C
0x1400105ee  mov     rcx, [rcx+18h]
0x1400105f2  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x1400105f9  mov     edx, 1Eh
0x1400105fe  call    WPP_SF_
0x140010603  jmp     short loc_14001060C
0x140010605  lea     rdi, WPP_GLOBAL_Control
0x14001060c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010613  cmp     rcx, rdi
0x140010616  jz      short loc_14001063A
0x140010618  mov     eax, [rcx+2Ch]
0x14001061b  test    al, 1
0x14001061d  jz      short loc_14001063A
0x14001061f  cmp     byte ptr [rcx+29h], 6
0x140010623  jb      short loc_14001063A
0x140010625  mov     edx, 1Fh
0x14001062a  mov     rcx, [rcx+18h]
0x14001062e  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140010635  call    WPP_SF_
0x14001063a  mov     rcx, [rbp+47h+var_30]
0x14001063e  xor     rcx, rsp; StackCookie
0x140010641  call    __security_check_cookie
0x140010646  lea     r11, [rsp+0B0h+var_20]
0x14001064e  mov     rsi, [r11+38h]
0x140010652  mov     rdi, [r11+40h]
0x140010656  mov     rsp, r11
0x140010659  pop     r15
0x14001065b  pop     r14
0x14001065d  pop     r13
0x14001065f  pop     r12
0x140010661  pop     rbp
0x140010662  retn
```
