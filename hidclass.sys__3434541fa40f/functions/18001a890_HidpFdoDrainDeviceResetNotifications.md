# HidpFdoDrainDeviceResetNotifications

- ea: `0x18001a890`
- end: `0x18001acb0`
- name: `HidpFdoDrainDeviceResetNotifications`
- size: `1056`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003b444`
- `0x18003f2b4`

## callees

- `0x18000a15c`
- `0x18000ff44`
- `0x180018978`
- `0x18001a890`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x18001ac69`
- `ntoskrnl!IoFreeIrp` at `0x18001ac69`
- `ntoskrnl!IofCompleteRequest` at `0x18001ab87`
- `ntoskrnl!IofCompleteRequest` at `0x18001ab87`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001ac7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001ac7a`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001aaa8`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001ac55`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001aaa8`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001ac55`
- `ntoskrnl!IoCancelIrp` at `0x18001ac2b`
- `ntoskrnl!IoCancelIrp` at `0x18001ac2b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001a8c2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001ac3a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001a8c2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001ac3a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18001ac94`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18001ac94`

## pseudocode

```c
void __fastcall HidpFdoDrainDeviceResetNotifications(__int64 a1)
{
  KSPIN_LOCK *v2; // r15
  IRP *v3; // r14
  __int64 **v4; // rdx
  int v5; // r8d
  KIRQL v6; // r12
  IRP **v7; // rsi
  __int64 ****v8; // rbx
  __int64 ***v9; // rcx
  __int64 **v10; // rax
  _QWORD *v11; // rax
  int v12; // edx
  int v13; // r8d
  __int64 *v14; // rax
  __int64 *v15; // rcx
  __int64 **v16; // rdx
  IRP *v17; // rbx
  KIRQL v18; // al
  int v19; // ebx
  __int64 *v20; // [rsp+60h] [rbp-10h] BYREF
  __int64 **v21; // [rsp+68h] [rbp-8h]

  v21 = &v20;
  v2 = (KSPIN_LOCK *)(a1 + 1896);
  v20 = (__int64 *)&v20;
  v3 = 0;
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 1896));
  if ( *(_BYTE *)(a1 + 1904) )
  {
    v7 = 0;
  }
  else
  {
    *(_BYTE *)(a1 + 1904) = 1;
    LOBYTE(v4) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v4,
        v5,
        *(_QWORD *)(a1 + 672),
        4,
        10,
        15,
        (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
        *(_QWORD *)a1);
    }
    v7 = *(IRP ***)(a1 + 1936);
    if ( v7 && !*((_DWORD *)v7 + 2) )
    {
      v3 = *v7;
      *((_DWORD *)v7 + 2) = 2;
      *(_QWORD *)(a1 + 1936) = 0;
    }
    v21 = &v20;
    v8 = (__int64 ****)(a1 + 1912);
    v20 = (__int64 *)&v20;
    while ( 1 )
    {
      v9 = *v8;
      if ( *v8 == (__int64 ***)v8 )
        break;
      if ( v9[1] != (__int64 **)v8 || (v10 = *v9, (*v9)[1] != (__int64 *)v9) )
LABEL_42:
        __fastfail(3u);
      *v8 = (__int64 ***)v10;
      v10[1] = (__int64 *)v8;
      if ( _InterlockedExchange64((volatile __int64 *)v9 - 8, 0) )
      {
        v11 = v21;
        if ( *v21 != (__int64 *)&v20 )
          goto LABEL_42;
        v9[1] = v21;
        v4 = &v20;
        *v9 = &v20;
        *v11 = v9;
        v21 = (__int64 **)v9;
      }
      else
      {
        v9[1] = (__int64 **)v9;
        *v9 = (__int64 **)v9;
        LOBYTE(v4) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_qq(
            WPP_GLOBAL_Control->AttachedDevice,
            (_DWORD)v4,
            v5,
            *(_QWORD *)(a1 + 672),
            4,
            10,
            11,
            (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
            *(_QWORD *)a1,
            (_BYTE)v9 + 88);
        }
      }
    }
  }
  KeReleaseSpinLock(v2, v6);
  while ( 1 )
  {
    v14 = v20;
    if ( v20 == (__int64 *)&v20 )
      break;
    if ( (__int64 **)v20[1] != &v20 )
      goto LABEL_42;
    v15 = (__int64 *)*v20;
    if ( *(__int64 **)(*v20 + 8) != v20 )
      goto LABEL_42;
    v20 = (__int64 *)*v20;
    v16 = &v20;
    v17 = (IRP *)(v14 - 21);
    v15[1] = (__int64)&v20;
    *((_DWORD *)v14 - 30) = -1073741536;
    LOBYTE(v16) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v16,
        v13,
        *(_QWORD *)(a1 + 672),
        4,
        10,
        12,
        (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
        *(_QWORD *)a1,
        (_BYTE)v14 + 88,
        32);
    }
    IofCompleteRequest(v17, 0);
  }
  if ( v3 )
  {
    LOBYTE(v12) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        v12,
        v13,
        *(_QWORD *)(a1 + 672),
        4,
        10,
        16,
        (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
        *(_QWORD *)a1,
        (char)v3);
    }
    IoCancelIrp(v3);
    v18 = KeAcquireSpinLockRaiseToDpc(v2);
    v19 = *((_DWORD *)v7 + 2);
    *((_DWORD *)v7 + 2) = 3;
    KeReleaseSpinLock(v2, v18);
    if ( v19 == 1 )
    {
      IoFreeIrp(v3);
      ExFreePoolWithTag(v7, 0);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 640), v3, 0x20u);
    }
  }
}

```

## disassembly

```asm
0x18001a890  push    rbp
0x18001a892  push    rbx
0x18001a893  push    rsi
0x18001a894  push    rdi
0x18001a895  push    r12
0x18001a897  push    r14
0x18001a899  push    r15
0x18001a89b  mov     rbp, rsp
0x18001a89e  sub     rsp, 70h
0x18001a8a2  lea     rax, [rbp+var_10]
0x18001a8a6  mov     rdi, rcx
0x18001a8a9  mov     [rbp+var_8], rax
0x18001a8ad  lea     r15, [rcx+768h]
0x18001a8b4  lea     rax, [rbp+var_10]
0x18001a8b8  mov     rcx, r15; SpinLock
0x18001a8bb  mov     [rbp+var_10], rax
0x18001a8bf  xor     r14d, r14d
0x18001a8c2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18001a8c9  nop     dword ptr [rax+rax+00h]
0x18001a8ce  lea     r10, WPP_GLOBAL_Control
0x18001a8d5  mov     r12b, al
0x18001a8d8  lea     r11, WPP_RECORDER_INITIALIZED
0x18001a8df  lea     rbx, WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids
0x18001a8e6  cmp     [rdi+770h], r14b
0x18001a8ed  jnz     loc_18001AAA0
0x18001a8f3  mov     byte ptr [rdi+770h], 1
0x18001a8fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a901  cmp     rcx, r10
0x18001a904  jz      short loc_18001A919
0x18001a906  test    dword ptr [rcx+2Ch], 200h
0x18001a90d  jz      short loc_18001A919
0x18001a90f  cmp     byte ptr [rcx+29h], 4
0x18001a913  jb      short loc_18001A919
0x18001a915  mov     dl, 1
0x18001a917  jmp     short loc_18001A91B
0x18001a919  xor     dl, dl
0x18001a91b  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x18001a922  setnz   r8b
0x18001a926  test    dl, dl
0x18001a928  jnz     short loc_18001A92F
0x18001a92a  test    r8b, r8b
0x18001a92d  jz      short loc_18001A96E
0x18001a92f  mov     rax, [rdi]
0x18001a932  mov     r9, [rdi+2A0h]
0x18001a939  mov     rcx, [rcx+18h]
0x18001a93d  mov     [rsp+70h+var_30], rax
0x18001a942  mov     [rsp+70h+var_38], rbx
0x18001a947  mov     [rsp+70h+var_40], 0Fh
0x18001a94e  mov     [rsp+70h+var_48], 0Ah
0x18001a956  mov     [rsp+70h+var_50], 4
0x18001a95b  call    WPP_RECORDER_AND_TRACE_SF_q
0x18001a960  lea     r10, WPP_GLOBAL_Control
0x18001a967  lea     r11, WPP_RECORDER_INITIALIZED
0x18001a96e  mov     rsi, [rdi+790h]
0x18001a975  test    rsi, rsi
0x18001a978  jz      short loc_18001A995
0x18001a97a  cmp     [rsi+8], r14d
0x18001a97e  jnz     short loc_18001A995
0x18001a980  mov     r14, [rsi]
0x18001a983  mov     dword ptr [rsi+8], 2
0x18001a98a  mov     qword ptr [rdi+790h], 0
0x18001a995  lea     rax, [rbp+var_10]
0x18001a999  mov     [rbp+var_8], rax
0x18001a99d  lea     rbx, [rdi+778h]
0x18001a9a4  lea     rax, [rbp+var_10]
0x18001a9a8  mov     [rbp+var_10], rax
0x18001a9ac  mov     rcx, [rbx]
0x18001a9af  cmp     rcx, rbx
0x18001a9b2  jz      loc_18001AAA2
0x18001a9b8  cmp     [rcx+8], rbx
0x18001a9bc  jnz     loc_18001AB98
0x18001a9c2  mov     rax, [rcx]
0x18001a9c5  cmp     [rax+8], rcx
0x18001a9c9  jnz     loc_18001AB98
0x18001a9cf  mov     [rbx], rax
0x18001a9d2  lea     r9, [rcx-0A8h]
0x18001a9d9  mov     [rax+8], rbx
0x18001a9dd  xor     eax, eax
0x18001a9df  xchg    rax, [r9+68h]
0x18001a9e3  test    rax, rax
0x18001a9e6  jnz     loc_18001AA78
0x18001a9ec  mov     [rcx+8], rcx
0x18001a9f0  mov     [rcx], rcx
0x18001a9f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9fa  cmp     rcx, r10
0x18001a9fd  jz      short loc_18001AA12
0x18001a9ff  test    dword ptr [rcx+2Ch], 200h
0x18001aa06  jz      short loc_18001AA12
0x18001aa08  cmp     byte ptr [rcx+29h], 4
0x18001aa0c  jb      short loc_18001AA12
0x18001aa0e  mov     dl, 1
0x18001aa10  jmp     short loc_18001AA14
0x18001aa12  xor     dl, dl
0x18001aa14  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x18001aa1b  setnz   r8b
0x18001aa1f  test    dl, dl
0x18001aa21  jnz     short loc_18001AA28
0x18001aa23  test    r8b, r8b
0x18001aa26  jz      short loc_18001A9AC
0x18001aa28  mov     rax, [rdi]
0x18001aa2b  mov     rcx, [rcx+18h]
0x18001aa2f  mov     [rsp+70h+var_28], r9
0x18001aa34  mov     r9, [rdi+2A0h]
0x18001aa3b  mov     [rsp+70h+var_30], rax
0x18001aa40  lea     rax, WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids
0x18001aa47  mov     [rsp+70h+var_38], rax
0x18001aa4c  mov     [rsp+70h+var_40], 0Bh
0x18001aa53  mov     [rsp+70h+var_48], 0Ah
0x18001aa5b  mov     [rsp+70h+var_50], 4
0x18001aa60  call    WPP_RECORDER_AND_TRACE_SF_qq
0x18001aa65  lea     r10, WPP_GLOBAL_Control
0x18001aa6c  lea     r11, WPP_RECORDER_INITIALIZED
0x18001aa73  jmp     loc_18001A9AC
0x18001aa78  mov     rax, [rbp+var_8]
0x18001aa7c  lea     rdx, [rbp+var_10]
0x18001aa80  cmp     [rax], rdx
0x18001aa83  jnz     loc_18001AB98
0x18001aa89  mov     [rcx+8], rax
0x18001aa8d  lea     rdx, [rbp+var_10]
0x18001aa91  mov     [rcx], rdx
0x18001aa94  mov     [rax], rcx
0x18001aa97  mov     [rbp+var_8], rcx
0x18001aa9b  jmp     loc_18001A9AC
0x18001aaa0  xor     esi, esi
0x18001aaa2  mov     dl, r12b; NewIrql
0x18001aaa5  mov     rcx, r15; SpinLock
0x18001aaa8  call    cs:__imp_KeReleaseSpinLock
0x18001aaaf  nop     dword ptr [rax+rax+00h]
0x18001aab4  mov     r12d, 0C0000120h
0x18001aaba  mov     rax, [rbp+var_10]
0x18001aabe  lea     rcx, [rbp+var_10]
0x18001aac2  cmp     rax, rcx
0x18001aac5  jz      loc_18001AB9F
0x18001aacb  lea     rcx, [rbp+var_10]
0x18001aacf  cmp     [rax+8], rcx
0x18001aad3  jnz     loc_18001AB98
0x18001aad9  mov     rcx, [rax]
0x18001aadc  cmp     [rcx+8], rax
0x18001aae0  jnz     loc_18001AB98
0x18001aae6  mov     [rbp+var_10], rcx
0x18001aaea  lea     rdx, [rbp+var_10]
0x18001aaee  lea     rbx, [rax-0A8h]
0x18001aaf5  mov     [rcx+8], rdx
0x18001aaf9  mov     [rbx+30h], r12d
0x18001aafd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab04  lea     rax, WPP_GLOBAL_Control
0x18001ab0b  cmp     rcx, rax
0x18001ab0e  jz      short loc_18001AB23
0x18001ab10  test    dword ptr [rcx+2Ch], 200h
0x18001ab17  jz      short loc_18001AB23
0x18001ab19  cmp     byte ptr [rcx+29h], 4
0x18001ab1d  jb      short loc_18001AB23
0x18001ab1f  mov     dl, 1
0x18001ab21  jmp     short loc_18001AB25
0x18001ab23  xor     dl, dl
0x18001ab25  lea     rax, WPP_RECORDER_INITIALIZED
0x18001ab2c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001ab33  setnz   r8b
0x18001ab37  test    dl, dl
0x18001ab39  jnz     short loc_18001AB40
0x18001ab3b  test    r8b, r8b
0x18001ab3e  jz      short loc_18001AB82
0x18001ab40  mov     rax, [rdi]
0x18001ab43  mov     r9, [rdi+2A0h]
0x18001ab4a  mov     rcx, [rcx+18h]
0x18001ab4e  mov     [rsp+70h+var_20], r12d
0x18001ab53  mov     [rsp+70h+var_28], rbx
0x18001ab58  mov     [rsp+70h+var_30], rax
0x18001ab5d  lea     rax, WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids
0x18001ab64  mov     [rsp+70h+var_38], rax
0x18001ab69  mov     [rsp+70h+var_40], 0Ch
0x18001ab70  mov     [rsp+70h+var_48], 0Ah
0x18001ab78  mov     [rsp+70h+var_50], 4
0x18001ab7d  call    WPP_RECORDER_AND_TRACE_SF_qqd
0x18001ab82  xor     edx, edx; PriorityBoost
0x18001ab84  mov     rcx, rbx; Irp
0x18001ab87  call    cs:__imp_IofCompleteRequest
0x18001ab8e  nop     dword ptr [rax+rax+00h]
0x18001ab93  jmp     loc_18001AABA
0x18001ab98  mov     ecx, 3
0x18001ab9d  int     29h; Win8: RtlFailFast(ecx)
0x18001ab9f  test    r14, r14
0x18001aba2  jz      loc_18001ACA0
0x18001aba8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abaf  lea     rax, WPP_GLOBAL_Control
0x18001abb6  cmp     rcx, rax
0x18001abb9  jz      short loc_18001ABCE
0x18001abbb  test    dword ptr [rcx+2Ch], 200h
0x18001abc2  jz      short loc_18001ABCE
0x18001abc4  cmp     byte ptr [rcx+29h], 4
0x18001abc8  jb      short loc_18001ABCE
0x18001abca  mov     dl, 1
0x18001abcc  jmp     short loc_18001ABD0
0x18001abce  xor     dl, dl
0x18001abd0  lea     rax, WPP_RECORDER_INITIALIZED
0x18001abd7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001abde  setnz   r8b
0x18001abe2  test    dl, dl
0x18001abe4  jnz     short loc_18001ABEB
0x18001abe6  test    r8b, r8b
0x18001abe9  jz      short loc_18001AC28
0x18001abeb  mov     rax, [rdi]
0x18001abee  mov     r9, [rdi+2A0h]
0x18001abf5  mov     rcx, [rcx+18h]
0x18001abf9  mov     [rsp+70h+var_28], r14
0x18001abfe  mov     [rsp+70h+var_30], rax
0x18001ac03  lea     rax, WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids
0x18001ac0a  mov     [rsp+70h+var_38], rax
0x18001ac0f  mov     [rsp+70h+var_40], 10h
0x18001ac16  mov     [rsp+70h+var_48], 0Ah
0x18001ac1e  mov     [rsp+70h+var_50], 4
0x18001ac23  call    WPP_RECORDER_AND_TRACE_SF_qq
0x18001ac28  mov     rcx, r14; Irp
0x18001ac2b  call    cs:__imp_IoCancelIrp
0x18001ac32  nop     dword ptr [rax+rax+00h]
0x18001ac37  mov     rcx, r15; SpinLock
0x18001ac3a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18001ac41  nop     dword ptr [rax+rax+00h]
0x18001ac46  mov     ebx, [rsi+8]
0x18001ac49  mov     rcx, r15; SpinLock
0x18001ac4c  mov     dl, al; NewIrql
0x18001ac4e  mov     dword ptr [rsi+8], 3
0x18001ac55  call    cs:__imp_KeReleaseSpinLock
0x18001ac5c  nop     dword ptr [rax+rax+00h]
0x18001ac61  cmp     ebx, 1
0x18001ac64  jnz     short loc_18001ACA0
0x18001ac66  mov     rcx, r14; Irp
0x18001ac69  call    cs:__imp_IoFreeIrp
0x18001ac70  nop     dword ptr [rax+rax+00h]
0x18001ac75  xor     edx, edx; Tag
0x18001ac77  mov     rcx, rsi; P
0x18001ac7a  call    cs:__imp_ExFreePoolWithTag
0x18001ac81  nop     dword ptr [rax+rax+00h]
0x18001ac86  lea     rcx, [rdi+280h]; RemoveLock
0x18001ac8d  mov     rdx, r14; Tag
0x18001ac90  lea     r8d, [rbx+1Fh]; RemlockSize
0x18001ac94  call    cs:__imp_IoReleaseRemoveLockEx
0x18001ac9b  nop     dword ptr [rax+rax+00h]
0x18001aca0  add     rsp, 70h
0x18001aca4  pop     r15
0x18001aca6  pop     r14
0x18001aca8  pop     r12
0x18001acaa  pop     rdi
0x18001acab  pop     rsi
0x18001acac  pop     rbx
0x18001acad  pop     rbp
0x18001acae  retn
```
