# DepFSDismountDependency

- ea: `0x18000aa48`
- end: `0x18000aec6`
- name: `DepFSDismountDependency`
- size: `1150`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x18000a874`
- `0x18000aecc`
- `0x18000ce60`

## callees

- `0x180001064`
- `0x1800010b8`
- `0x180001150`
- `0x180001544`
- `0x18000aa48`
- `0x18000b1d4`
- `0x18000f73c`
- `0x18000f91c`
- `0x18000f970`

## import_xrefs

- `ntoskrnl!KeBugCheck` at `0x18000abb6`
- `ntoskrnl!KeBugCheck` at `0x18000abb6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000ac42`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000adcc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000adf9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000aea7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000ac42`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000adcc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000adf9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000aea7`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000ae36`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000ae36`
- `ntoskrnl!KeInitializeEvent` at `0x18000ad24`
- `ntoskrnl!KeInitializeEvent` at `0x18000ad24`
- `ntoskrnl!IofCallDriver` at `0x18000ae0f`
- `ntoskrnl!IofCallDriver` at `0x18000ae0f`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000ac36`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000adc0`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000aded`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000ae9b`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000ac36`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000adc0`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000aded`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000ae9b`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18000ad66`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18000ad66`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000aa91`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000ac73`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000aa91`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000ac73`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000aa7c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000ac5e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000aa7c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000ac5e`

## pseudocode

```c
__int64 __fastcall DepFSDismountDependency(char *P)
{
  _QWORD *v2; // r15
  unsigned int v3; // ecx
  int v4; // ecx
  _QWORD **v5; // r14
  _QWORD *v6; // rsi
  __int64 v7; // rdi
  unsigned int v8; // ebx
  _QWORD *i; // rdi
  __int64 v10; // rsi
  int v11; // eax
  IRP *v12; // rdi
  unsigned int v14; // eax
  __int64 Status; // r9
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-19h] BYREF
  __int128 InputBuffer; // [rsp+60h] [rbp-9h] BYREF
  __int64 v18; // [rsp+70h] [rbp+7h]
  struct _KEVENT Event; // [rsp+78h] [rbp+Fh] BYREF

  IoStatusBlock = 0;
  v18 = 0;
  memset(&Event, 0, sizeof(Event));
  InputBuffer = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  v2 = P + 40;
  if ( (_QWORD *)*v2 == v2 )
    goto LABEL_57;
  v3 = *((_DWORD *)P + 23);
  if ( (v3 & 3) != 0 )
    goto LABEL_57;
  v4 = (v3 >> 5) & 1;
  if ( byte_180005194 )
    v4 |= 2u;
  v5 = (_QWORD **)(P + 24);
  v6 = (_QWORD *)*((_QWORD *)P + 3);
  *(_QWORD *)&InputBuffer = *((_QWORD *)P + 13);
  *((_QWORD *)&InputBuffer + 1) = *((_QWORD *)P + 15);
  LODWORD(v18) = v4;
  while ( v6 != v5 )
  {
    v7 = *(v6 - 3);
    v6 = (_QWORD *)*v6;
    if ( (*((_DWORD *)P + 23) & 0x20) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids, P, v7);
      }
      *(_DWORD *)(v7 + 56) |= 0x20u;
      if ( (*(_DWORD *)(v7 + 56) & 2) != 0 )
        KeBugCheck(0x22u);
    }
    else if ( (*(_DWORD *)(v7 + 56) & 2) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids, P, v7);
      }
      v8 = -1073741790;
      goto LABEL_48;
    }
  }
  if ( (*((_DWORD *)P + 23) & 0x20) == 0 )
  {
    for ( i = *v5; i != v5; i = (_QWORD *)*i )
    {
      v10 = *(i - 3);
      if ( (*(_DWORD *)(v10 + 56) & 5) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qq(
            WPP_GLOBAL_Control->AttachedDevice,
            14,
            WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids,
            P,
            *(i - 3));
        }
      }
      else
      {
        v11 = ReferenceVolumeContext((PFLT_CONTEXT)*(i - 3));
        if ( v11 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_Dqq(
              WPP_GLOBAL_Control->AttachedDevice,
              13,
              WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids,
              (unsigned int)v11,
              P,
              v10);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids, P, v10);
          }
          *(_DWORD *)(v10 + 56) |= 4u;
          ExReleaseResourceLite(&Resource);
          KeLeaveCriticalRegion();
          DepFSSendDismountRequest(v10);
          DereferenceVolumeContext(v10);
          KeEnterCriticalRegion();
          ExAcquireResourceExclusiveLite(&Resource, 1u);
        }
        i = P + 24;
      }
    }
  }
  if ( (_QWORD *)*v2 == v2 || (*((_DWORD *)P + 23) & 3) != 0 )
  {
LABEL_57:
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
  }
  else
  {
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v12 = IoBuildDeviceIoControlRequest(
            0x2D9194u,
            *((PDEVICE_OBJECT *)P + 16),
            &InputBuffer,
            0x18u,
            0,
            0,
            0,
            &Event,
            &IoStatusBlock);
    if ( !v12 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids, P);
      }
      *((_DWORD *)P + 23) |= 2u;
      v8 = -1073741670;
LABEL_48:
      ExReleaseResourceLite(&Resource);
      KeLeaveCriticalRegion();
      return v8;
    }
    *((_DWORD *)P + 23) |= 1u;
    ++*((_DWORD *)P + 14);
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    v14 = IofCallDriver(*((PDEVICE_OBJECT *)P + 16), v12);
    Status = v14;
    if ( v14 == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = (unsigned int)IoStatusBlock.Status;
    }
    if ( (int)Status < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Dq(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids, Status, P);
    }
    DereferenceDependencyContext(P);
  }
  return 0;
}

```

## disassembly

```asm
0x18000aa48  push    rbp
0x18000aa4a  push    rbx
0x18000aa4b  push    rsi
0x18000aa4c  push    rdi
0x18000aa4d  push    r14
0x18000aa4f  push    r15
0x18000aa51  lea     rbp, [rsp-2Fh]
0x18000aa56  sub     rsp, 98h
0x18000aa5d  xorps   xmm0, xmm0
0x18000aa60  xor     eax, eax
0x18000aa62  xorps   xmm1, xmm1
0x18000aa65  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x18000aa69  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18000aa6d  mov     [rbp+57h+var_50], rax
0x18000aa71  mov     rbx, rcx
0x18000aa74  movups  xmmword ptr [rbp+57h+Event.Header], xmm1
0x18000aa78  movups  [rbp+57h+InputBuffer], xmm0
0x18000aa7c  call    cs:__imp_KeEnterCriticalRegion
0x18000aa83  nop     dword ptr [rax+rax+00h]
0x18000aa88  mov     dl, 1; Wait
0x18000aa8a  lea     rcx, Resource; Resource
0x18000aa91  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000aa98  nop     dword ptr [rax+rax+00h]
0x18000aa9d  lea     r15, [rbx+28h]
0x18000aaa1  cmp     [r15], r15
0x18000aaa4  jz      loc_18000AE94
0x18000aaaa  mov     ecx, [rbx+5Ch]
0x18000aaad  test    cl, 3
0x18000aab0  jnz     loc_18000AE94
0x18000aab6  shr     ecx, 5
0x18000aab9  and     ecx, 1
0x18000aabc  cmp     cs:byte_180005194, 0
0x18000aac3  jz      short loc_18000AAC8
0x18000aac5  or      ecx, 2
0x18000aac8  mov     rax, [rbx+68h]
0x18000aacc  lea     r14, [rbx+18h]
0x18000aad0  mov     rsi, [r14]
0x18000aad3  lea     rdx, WPP_GLOBAL_Control
0x18000aada  mov     qword ptr [rbp+57h+InputBuffer], rax
0x18000aade  mov     rax, [rbx+78h]
0x18000aae2  mov     qword ptr [rbp+57h+InputBuffer+8], rax
0x18000aae6  mov     dword ptr [rbp+57h+var_50], ecx
0x18000aae9  jmp     loc_18000AB8F
0x18000aaee  mov     eax, [rbx+5Ch]
0x18000aaf1  mov     rdi, [rsi-18h]
0x18000aaf5  mov     rsi, [rsi]
0x18000aaf8  test    al, 20h
0x18000aafa  jnz     short loc_18000AB47
0x18000aafc  mov     eax, [rdi+38h]
0x18000aaff  test    al, 2
0x18000ab01  jz      loc_18000AB8F
0x18000ab07  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab0e  cmp     rcx, rdx
0x18000ab11  jz      short loc_18000AB3D
0x18000ab13  mov     eax, [rcx+2Ch]
0x18000ab16  test    al, 20h
0x18000ab18  jz      short loc_18000AB3D
0x18000ab1a  cmp     byte ptr [rcx+29h], 4
0x18000ab1e  jb      short loc_18000AB3D
0x18000ab20  mov     rcx, [rcx+18h]
0x18000ab24  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000ab2b  mov     edx, 0Ah
0x18000ab30  mov     [rsp+0C0h+OutputBuffer], rdi
0x18000ab35  mov     r9, rbx
0x18000ab38  call    WPP_SF_qq
0x18000ab3d  mov     ebx, 0C0000022h
0x18000ab42  jmp     loc_18000ADB9
0x18000ab47  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab4e  cmp     rcx, rdx
0x18000ab51  jz      short loc_18000AB84
0x18000ab53  mov     eax, [rcx+2Ch]
0x18000ab56  test    al, 20h
0x18000ab58  jz      short loc_18000AB84
0x18000ab5a  cmp     byte ptr [rcx+29h], 4
0x18000ab5e  jb      short loc_18000AB84
0x18000ab60  mov     rcx, [rcx+18h]
0x18000ab64  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000ab6b  mov     edx, 0Bh
0x18000ab70  mov     [rsp+0C0h+OutputBuffer], rdi
0x18000ab75  mov     r9, rbx
0x18000ab78  call    WPP_SF_qq
0x18000ab7d  lea     rdx, WPP_GLOBAL_Control
0x18000ab84  or      dword ptr [rdi+38h], 20h
0x18000ab88  mov     eax, [rdi+38h]
0x18000ab8b  test    al, 2
0x18000ab8d  jnz     short loc_18000ABB1
0x18000ab8f  cmp     rsi, r14
0x18000ab92  jnz     loc_18000AAEE
0x18000ab98  mov     eax, [rbx+5Ch]
0x18000ab9b  test    al, 20h
0x18000ab9d  jnz     loc_18000AD07
0x18000aba3  mov     rdi, [r14]
0x18000aba6  cmp     rdi, r14
0x18000aba9  jz      loc_18000AD07
0x18000abaf  jmp     short loc_18000ABCA
0x18000abb1  mov     ecx, 22h ; '"'; BugCheckCode
0x18000abb6  call    cs:__imp_KeBugCheck
0x18000abc3  lea     rdx, WPP_GLOBAL_Control
0x18000abca  mov     rsi, [rdi-18h]
0x18000abce  mov     eax, [rsi+38h]
0x18000abd1  test    al, 5
0x18000abd3  jnz     loc_18000ACC5
0x18000abd9  xor     edx, edx
0x18000abdb  mov     rcx, rsi; Context
0x18000abde  call    ReferenceVolumeContext
0x18000abe3  mov     r9d, eax
0x18000abe6  test    eax, eax
0x18000abe8  js      loc_18000AC81
0x18000abee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abf5  lea     rax, WPP_GLOBAL_Control
0x18000abfc  cmp     rcx, rax
0x18000abff  jz      short loc_18000AC2B
0x18000ac01  mov     eax, [rcx+2Ch]
0x18000ac04  test    al, 20h
0x18000ac06  jz      short loc_18000AC2B
0x18000ac08  cmp     byte ptr [rcx+29h], 4
0x18000ac0c  jb      short loc_18000AC2B
0x18000ac0e  mov     rcx, [rcx+18h]
0x18000ac12  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000ac19  mov     edx, 0Ch
0x18000ac1e  mov     [rsp+0C0h+OutputBuffer], rsi
0x18000ac23  mov     r9, rbx
0x18000ac26  call    WPP_SF_qq
0x18000ac2b  or      dword ptr [rsi+38h], 4
0x18000ac2f  lea     rcx, Resource; Resource
0x18000ac36  call    cs:__imp_ExReleaseResourceLite
0x18000ac3d  nop     dword ptr [rax+rax+00h]
0x18000ac42  call    cs:__imp_KeLeaveCriticalRegion
0x18000ac49  nop     dword ptr [rax+rax+00h]
0x18000ac4e  mov     rcx, rsi
0x18000ac51  call    DepFSSendDismountRequest
0x18000ac56  mov     rcx, rsi
0x18000ac59  call    DereferenceVolumeContext
0x18000ac5e  call    cs:__imp_KeEnterCriticalRegion
0x18000ac65  nop     dword ptr [rax+rax+00h]
0x18000ac6a  mov     dl, 1; Wait
0x18000ac6c  lea     rcx, Resource; Resource
0x18000ac73  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000ac7a  nop     dword ptr [rax+rax+00h]
0x18000ac7f  jmp     short loc_18000ACC0
0x18000ac81  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac88  lea     rax, WPP_GLOBAL_Control
0x18000ac8f  cmp     rcx, rax
0x18000ac92  jz      short loc_18000ACC0
0x18000ac94  mov     eax, [rcx+2Ch]
0x18000ac97  test    al, 20h
0x18000ac99  jz      short loc_18000ACC0
0x18000ac9b  cmp     byte ptr [rcx+29h], 4
0x18000ac9f  jb      short loc_18000ACC0
0x18000aca1  mov     rcx, [rcx+18h]
0x18000aca5  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000acac  mov     edx, 0Dh
0x18000acb1  mov     qword ptr [rsp+0C0h+OutputBufferLength], rsi
0x18000acb6  mov     [rsp+0C0h+OutputBuffer], rbx
0x18000acbb  call    WPP_SF_Dqq
0x18000acc0  mov     rdi, r14
0x18000acc3  jmp     short loc_18000ACFB
0x18000acc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000accc  cmp     rcx, rdx
0x18000accf  jz      short loc_18000ACFB
0x18000acd1  mov     eax, [rcx+2Ch]
0x18000acd4  test    al, 20h
0x18000acd6  jz      short loc_18000ACFB
0x18000acd8  cmp     byte ptr [rcx+29h], 4
0x18000acdc  jb      short loc_18000ACFB
0x18000acde  mov     rcx, [rcx+18h]
0x18000ace2  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000ace9  mov     edx, 0Eh
0x18000acee  mov     [rsp+0C0h+OutputBuffer], rsi
0x18000acf3  mov     r9, rbx
0x18000acf6  call    WPP_SF_qq
0x18000acfb  mov     rdi, [rdi]
0x18000acfe  cmp     rdi, r14
0x18000ad01  jnz     loc_18000ABC3
0x18000ad07  cmp     [r15], r15
0x18000ad0a  jz      loc_18000AE94
0x18000ad10  mov     eax, [rbx+5Ch]
0x18000ad13  test    al, 3
0x18000ad15  jnz     loc_18000AE94
0x18000ad1b  xor     r8d, r8d; State
0x18000ad1e  lea     rcx, [rbp+57h+Event]; Event
0x18000ad22  xor     edx, edx; Type
0x18000ad24  call    cs:__imp_KeInitializeEvent
0x18000ad2b  nop     dword ptr [rax+rax+00h]
0x18000ad30  mov     rdx, [rbx+80h]; DeviceObject
0x18000ad37  lea     rax, [rbp+57h+var_70]
0x18000ad3b  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x18000ad40  lea     r8, [rbp+57h+InputBuffer]; InputBuffer
0x18000ad44  xor     esi, esi
0x18000ad46  lea     rax, [rbp+57h+Event]
0x18000ad4a  mov     [rsp+0C0h+var_88], rax; Event
0x18000ad4f  mov     ecx, 2D9194h; IoControlCode
0x18000ad54  mov     [rsp+0C0h+InternalDeviceIoControl], sil; InternalDeviceIoControl
0x18000ad59  mov     [rsp+0C0h+OutputBufferLength], esi; OutputBufferLength
0x18000ad5d  lea     r9d, [rsi+18h]; InputBufferLength
0x18000ad61  mov     [rsp+0C0h+OutputBuffer], rsi; OutputBuffer
0x18000ad66  call    cs:__imp_IoBuildDeviceIoControlRequest
0x18000ad6d  nop     dword ptr [rax+rax+00h]
0x18000ad72  mov     rdi, rax
0x18000ad75  test    rax, rax
0x18000ad78  jnz     short loc_18000ADDF
0x18000ad7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad81  lea     rax, WPP_GLOBAL_Control
0x18000ad88  cmp     rcx, rax
0x18000ad8b  jz      short loc_18000ADB0
0x18000ad8d  mov     eax, [rcx+2Ch]
0x18000ad90  test    al, 1
0x18000ad92  jz      short loc_18000ADB0
0x18000ad94  cmp     byte ptr [rcx+29h], 2
0x18000ad98  jb      short loc_18000ADB0
0x18000ad9a  mov     rcx, [rcx+18h]
0x18000ad9e  lea     edx, [rsi+0Fh]
0x18000ada1  mov     r9, rbx
0x18000ada4  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000adab  call    WPP_SF_q
0x18000adb0  or      dword ptr [rbx+5Ch], 2
0x18000adb4  mov     ebx, 0C000009Ah
0x18000adb9  lea     rcx, Resource; Resource
0x18000adc0  call    cs:__imp_ExReleaseResourceLite
0x18000adc7  nop     dword ptr [rax+rax+00h]
0x18000adcc  call    cs:__imp_KeLeaveCriticalRegion
0x18000add3  nop     dword ptr [rax+rax+00h]
0x18000add8  mov     eax, ebx
0x18000adda  jmp     loc_18000AEB5
0x18000addf  or      dword ptr [rbx+5Ch], 1
0x18000ade3  lea     rcx, Resource; Resource
0x18000adea  inc     dword ptr [rbx+38h]
0x18000aded  call    cs:__imp_ExReleaseResourceLite
0x18000adf4  nop     dword ptr [rax+rax+00h]
0x18000adf9  call    cs:__imp_KeLeaveCriticalRegion
0x18000ae00  nop     dword ptr [rax+rax+00h]
0x18000ae05  mov     rcx, [rbx+80h]; DeviceObject
0x18000ae0c  mov     rdx, rdi; Irp
0x18000ae0f  call    cs:__imp_IofCallDriver
0x18000ae16  nop     dword ptr [rax+rax+00h]
0x18000ae1b  mov     r9d, eax
0x18000ae1e  cmp     eax, 103h
0x18000ae23  jnz     short loc_18000AE46
0x18000ae25  xor     r9d, r9d; Alertable
0x18000ae28  mov     [rsp+0C0h+OutputBuffer], rsi; Timeout
0x18000ae2d  xor     r8d, r8d; WaitMode
0x18000ae30  lea     rcx, [rbp+57h+Event]; Object
0x18000ae34  xor     edx, edx; WaitReason
0x18000ae36  call    cs:__imp_KeWaitForSingleObject
0x18000ae3d  nop     dword ptr [rax+rax+00h]
0x18000ae42  mov     r9d, dword ptr [rbp+57h+var_70]
0x18000ae46  test    r9d, r9d
0x18000ae49  jns     short loc_18000AE85
0x18000ae4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae52  lea     rax, WPP_GLOBAL_Control
0x18000ae59  cmp     rcx, rax
0x18000ae5c  jz      short loc_18000AE85
0x18000ae5e  mov     eax, [rcx+2Ch]
0x18000ae61  test    al, 1
0x18000ae63  jz      short loc_18000AE85
0x18000ae65  cmp     byte ptr [rcx+29h], 2
0x18000ae69  jb      short loc_18000AE85
0x18000ae6b  mov     rcx, [rcx+18h]
0x18000ae6f  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000ae76  mov     edx, 10h
0x18000ae7b  mov     [rsp+0C0h+OutputBuffer], rbx
0x18000ae80  call    WPP_SF_Dq
0x18000ae85  xor     r8d, r8d
0x18000ae88  xor     edx, edx
0x18000ae8a  mov     rcx, rbx; P
0x18000ae8d  call    DereferenceDependencyContext
0x18000ae92  jmp     short loc_18000AEB3
0x18000ae94  lea     rcx, Resource; Resource
0x18000ae9b  call    cs:__imp_ExReleaseResourceLite
0x18000aea2  nop     dword ptr [rax+rax+00h]
0x18000aea7  call    cs:__imp_KeLeaveCriticalRegion
0x18000aeae  nop     dword ptr [rax+rax+00h]
0x18000aeb3  xor     eax, eax
0x18000aeb5  add     rsp, 98h
0x18000aebc  pop     r15
0x18000aebe  pop     r14
0x18000aec0  pop     rdi
0x18000aec1  pop     rsi
0x18000aec2  pop     rbx
0x18000aec3  pop     rbp
0x18000aec4  retn
```
