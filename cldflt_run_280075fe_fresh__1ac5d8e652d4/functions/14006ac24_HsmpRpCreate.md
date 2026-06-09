# HsmpRpCreate

- ea: `0x14006ac24`
- end: `0x14006b1ec`
- name: `HsmpRpCreate`
- size: `1480`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x140046bd0`
- `0x14006079c`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000b62c`
- `0x14001e140`
- `0x14005a6bc`
- `0x14006ac24`
- `0x14006b1f4`
- `0x14006bbd4`
- `0x14007658c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006acef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ade1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006acef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ade1`
- `ntoskrnl!ExAllocatePool2` at `0x14006ac89`
- `ntoskrnl!ExAllocatePool2` at `0x14006ac89`
- `FLTMGR!FltTagFile` at `0x14006ad99`
- `FLTMGR!FltTagFile` at `0x14006b11f`
- `FLTMGR!FltTagFile` at `0x14006ad99`
- `FLTMGR!FltTagFile` at `0x14006b11f`
- `FLTMGR!FltTagFileEx` at `0x14006b0ac`
- `FLTMGR!FltTagFileEx` at `0x14006b0ac`
- `FLTMGR!FltUntagFile` at `0x14006ae74`
- `FLTMGR!FltUntagFile` at `0x14006ae74`

## pseudocode

```c
__int64 __fastcall HsmpRpCreate(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        __int64 a3,
        int a4,
        const void *a5,
        unsigned __int16 a6,
        char a7)
{
  struct _FLT_INSTANCE *v7; // rax
  UCHAR *v11; // r12
  int v12; // r13d
  void *Pool2; // rax
  int v14; // ebx
  ULONG v16; // r15d
  __int64 v17; // r8
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v21; // rdx
  signed int v22; // ebx
  GUID *v23; // r13
  unsigned int v24; // eax
  int DataBufferLength; // [rsp+28h] [rbp-69h]
  char v26; // [rsp+50h] [rbp-41h]
  char v27; // [rsp+51h] [rbp-40h]
  USHORT v28; // [rsp+54h] [rbp-3Dh] BYREF
  UCHAR *v29; // [rsp+58h] [rbp-39h] BYREF
  PVOID P; // [rsp+60h] [rbp-31h]
  int v31; // [rsp+68h] [rbp-29h]
  int v32; // [rsp+6Ch] [rbp-25h]
  PFLT_INSTANCE InitiatingInstance; // [rsp+70h] [rbp-21h]
  __int64 v34; // [rsp+78h] [rbp-19h]
  __int128 v35; // [rsp+80h] [rbp-11h] BYREF

  v7 = *(struct _FLT_INSTANCE **)(a1 + 32);
  v34 = a3;
  v28 = 0x4000;
  v11 = 0;
  v31 = a4;
  InitiatingInstance = v7;
  v29 = 0;
  v12 = a4;
  Pool2 = (void *)ExAllocatePool2(256, 0x4000, 1884451656);
  P = Pool2;
  if ( Pool2 )
  {
    v14 = HsmiRpInitializeTable(a3, v12, a5, a6, (__int64)Pool2, &v28);
    HsmDbgBreakOnStatus((unsigned int)v14);
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_4;
      }
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      v21 = 64;
LABEL_36:
      WPP_SF_qqd(AttachedDevice, v21, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids, a1, a2, v14);
LABEL_4:
      ExFreePoolWithTag(P, 0x70527348u);
      return (unsigned int)v14;
    }
    v32 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v26 = 0;
    }
    else
    {
      v26 = 1;
      v14 = HsmpToggleFileAttributes(a1, a2, 4198400, 0);
      HsmDbgBreakOnStatus((unsigned int)v14);
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_4;
        }
        AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
        v21 = 65;
        goto LABEL_36;
      }
    }
    v27 = 0;
    v16 = dword_140029670 | ((v12 & 0x20 | (2 * (v12 & 0xC0 | (16 * (v12 & 2))))) << 7);
    if ( !a2->WriteAccess )
    {
      a2->WriteAccess = 1;
      v27 = 1;
    }
    v14 = FltTagFile(InitiatingInstance, a2, v16, 0, P, v28);
    HsmDbgBreakOnStatus((unsigned int)v14);
    if ( v14 < 0 )
    {
      if ( !a7 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_13;
        }
        v19 = 66;
        goto LABEL_22;
      }
      if ( v14 == -1073741193 )
      {
        v35 = 0;
        v14 = HsmpRpReadBuffer(InitiatingInstance, a2, &v29);
        HsmDbgBreakOnStatus((unsigned int)v14);
        v11 = v29;
        if ( v14 < 0 )
        {
          if ( v14 != -1073741195 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qqd(
                WPP_GLOBAL_Control->AttachedDevice,
                67,
                WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids,
                a1,
                a2,
                v14);
            }
            v11 = v29;
            goto LABEL_13;
          }
          v22 = 0;
          v23 = 0;
        }
        else
        {
          v22 = *(_DWORD *)v29;
          if ( *(int *)v29 >= 0 )
            v35 = *(_OWORD *)(v29 + 8);
          v23 = (GUID *)&v35;
          if ( v22 < 0 )
            v23 = 0;
        }
        if ( *(_DWORD *)(a1 + 80) == 28
          && (unsigned int)Feature_ReFS_OneDrive_Support__private_IsEnabledDeviceUsageNoInline() )
        {
          v14 = FltUntagFile(*(PFLT_INSTANCE *)(a1 + 32), a2, v22, v23);
          HsmDbgBreakOnStatus((unsigned int)v14);
          if ( v14 < 0 )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_13;
            }
            v19 = 68;
            goto LABEL_22;
          }
          v24 = FltTagFile(*(PFLT_INSTANCE *)(a1 + 32), a2, v16, 0, P, v28);
        }
        else
        {
          LOWORD(DataBufferLength) = v28;
          v24 = FltTagFileEx(*(_QWORD *)(a1 + 32), a2, v16, 0, P, DataBufferLength, v22, v23, 0);
        }
        v14 = v24;
        HsmDbgBreakOnStatus(v24);
        if ( v14 < 0 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_13;
          }
          v19 = 69;
          goto LABEL_22;
        }
        LOBYTE(v12) = v31;
      }
    }
    if ( v32
      || (v12 & 0x10) != 0
      || !v34
      || (LOBYTE(v17) = 1,
          v14 = HsmpToggleFileSparseAttribute(a1, a2, v17),
          HsmDbgBreakOnStatus((unsigned int)v14),
          v14 >= 0) )
    {
      if ( v26 )
        goto LABEL_13;
      v14 = HsmpToggleFileAttributes(a1, a2, 0, 4198400);
      HsmDbgBreakOnStatus((unsigned int)v14);
      if ( v14 >= 0 )
        goto LABEL_13;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_13;
      }
      v19 = 71;
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_13;
      }
      v19 = 70;
    }
LABEL_22:
    WPP_SF_qqd(v18->AttachedDevice, v19, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids, a1, a2, v14);
LABEL_13:
    if ( v27 )
      a2->WriteAccess = 0;
    if ( v11 )
      ExFreePoolWithTag(v11, 0x70527348u);
    goto LABEL_4;
  }
  v14 = -1073741670;
  HsmDbgBreakOnStatus(3221225626LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqd(
      WPP_GLOBAL_Control->AttachedDevice,
      63,
      WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids,
      a1,
      a2,
      -1073741670);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14006ac24  mov     [rsp-8+arg_10], rbx
0x14006ac29  push    rbp
0x14006ac2a  push    rsi
0x14006ac2b  push    rdi
0x14006ac2c  push    r12
0x14006ac2e  push    r13
0x14006ac30  push    r14
0x14006ac32  push    r15
0x14006ac34  lea     rbp, [rsp-0Fh]
0x14006ac39  sub     rsp, 0A0h
0x14006ac40  mov     rax, cs:__security_cookie
0x14006ac47  xor     rax, rsp
0x14006ac4a  mov     [rbp+3Fh+var_40], rax
0x14006ac4e  mov     rax, [rcx+20h]
0x14006ac52  mov     rsi, rdx
0x14006ac55  mov     rbx, [rbp+3Fh+arg_20]
0x14006ac59  mov     edx, 4000h
0x14006ac5e  mov     rdi, r8
0x14006ac61  mov     [rbp+3Fh+var_58], r8
0x14006ac65  mov     r14, rcx
0x14006ac68  mov     [rbp+3Fh+var_7C], dx
0x14006ac6c  xor     r12d, r12d
0x14006ac6f  mov     [rbp+3Fh+var_68], r9d
0x14006ac73  mov     ecx, 100h
0x14006ac78  mov     [rbp+3Fh+InitiatingInstance], rax
0x14006ac7c  mov     r8d, 70527348h
0x14006ac82  mov     [rbp+3Fh+var_78], r12
0x14006ac86  mov     r13d, r9d
0x14006ac89  call    cs:__imp_ExAllocatePool2
0x14006ac90  nop     dword ptr [rax+rax+00h]
0x14006ac95  mov     [rbp+3Fh+P], rax
0x14006ac99  test    rax, rax
0x14006ac9c  jz      loc_14006AEC8
0x14006aca2  mov     r9d, dword ptr [rbp+3Fh+arg_28]
0x14006aca6  lea     rcx, [rbp+3Fh+var_7C]
0x14006acaa  mov     qword ptr [rsp+0D0h+DataBufferLength], rcx
0x14006acaf  mov     r8, rbx
0x14006acb2  mov     rcx, rdi
0x14006acb5  mov     [rsp+0D0h+DataBuffer], rax
0x14006acba  mov     edx, r13d
0x14006acbd  call    HsmiRpInitializeTable
0x14006acc2  mov     ecx, eax
0x14006acc4  mov     ebx, eax
0x14006acc6  call    HsmDbgBreakOnStatus
0x14006accb  test    ebx, ebx
0x14006accd  jns     short loc_14006AD25
0x14006accf  mov     r10, cs:WPP_GLOBAL_Control
0x14006acd6  lea     rax, WPP_GLOBAL_Control
0x14006acdd  cmp     r10, rax
0x14006ace0  jnz     loc_14006AF2A
0x14006ace6  mov     rcx, [rbp+3Fh+P]; P
0x14006acea  mov     edx, 70527348h; Tag
0x14006acef  call    cs:__imp_ExFreePoolWithTag
0x14006acf6  nop     dword ptr [rax+rax+00h]
0x14006acfb  mov     eax, ebx
0x14006acfd  mov     rcx, [rbp+3Fh+var_40]
0x14006ad01  xor     rcx, rsp; StackCookie
0x14006ad04  call    __security_check_cookie
0x14006ad09  mov     rbx, [rsp+0D0h+arg_10]
0x14006ad11  add     rsp, 0A0h
0x14006ad18  pop     r15
0x14006ad1a  pop     r14
0x14006ad1c  pop     r13
0x14006ad1e  pop     r12
0x14006ad20  pop     rdi
0x14006ad21  pop     rsi
0x14006ad22  pop     rbp
0x14006ad23  retn
0x14006ad25  mov     eax, r13d
0x14006ad28  mov     dil, 1
0x14006ad2b  and     eax, 4
0x14006ad2e  mov     [rbp+3Fh+var_64], eax
0x14006ad31  jz      loc_14006AF76
0x14006ad37  mov     [rbp+3Fh+var_80], r12b
0x14006ad3b  mov     r15d, r13d
0x14006ad3e  mov     [rbp+3Fh+var_7F], r12b
0x14006ad42  and     r15d, 2
0x14006ad46  mov     eax, r13d
0x14006ad49  shl     r15d, 4
0x14006ad4d  and     eax, 0C0h
0x14006ad52  or      r15d, eax
0x14006ad55  mov     eax, r13d
0x14006ad58  add     r15d, r15d
0x14006ad5b  and     eax, 20h
0x14006ad5e  or      r15d, eax
0x14006ad61  shl     r15d, 7
0x14006ad65  or      r15d, cs:dword_140029670
0x14006ad6c  cmp     [rsi+4Bh], r12b
0x14006ad70  jnz     short loc_14006AD7A
0x14006ad72  mov     [rsi+4Bh], dil
0x14006ad76  mov     [rbp+3Fh+var_7F], dil
0x14006ad7a  movzx   eax, [rbp+3Fh+var_7C]
0x14006ad7e  xor     r9d, r9d; Guid
0x14006ad81  mov     rcx, [rbp+3Fh+InitiatingInstance]; InitiatingInstance
0x14006ad85  mov     r8d, r15d; FileTag
0x14006ad88  mov     [rsp+0D0h+DataBufferLength], ax; DataBufferLength
0x14006ad8d  mov     rdx, rsi; FileObject
0x14006ad90  mov     rax, [rbp+3Fh+P]
0x14006ad94  mov     [rsp+0D0h+DataBuffer], rax; DataBuffer
0x14006ad99  call    cs:__imp_FltTagFile
0x14006ada0  nop     dword ptr [rax+rax+00h]
0x14006ada5  mov     ecx, eax
0x14006ada7  mov     ebx, eax
0x14006ada9  call    HsmDbgBreakOnStatus
0x14006adae  test    ebx, ebx
0x14006adb0  js      loc_14006AFCE
0x14006adb6  cmp     [rbp+3Fh+var_64], 0
0x14006adba  jz      loc_14006B181
0x14006adc0  cmp     [rbp+3Fh+var_80], 0
0x14006adc4  jz      short loc_14006ADF2
0x14006adc6  cmp     [rbp+3Fh+var_7F], 0
0x14006adca  jz      short loc_14006ADD0
0x14006adcc  mov     byte ptr [rsi+4Bh], 0
0x14006add0  test    r12, r12
0x14006add3  jz      loc_14006ACE6
0x14006add9  mov     edx, 70527348h; Tag
0x14006adde  mov     rcx, r12; P
0x14006ade1  call    cs:__imp_ExFreePoolWithTag
0x14006ade8  nop     dword ptr [rax+rax+00h]
0x14006aded  jmp     loc_14006ACE6
0x14006adf2  mov     r9d, 401000h
0x14006adf8  xor     r8d, r8d
0x14006adfb  mov     rdx, rsi
0x14006adfe  mov     rcx, r14
0x14006ae01  call    HsmpToggleFileAttributes
0x14006ae06  mov     ecx, eax
0x14006ae08  mov     ebx, eax
0x14006ae0a  call    HsmDbgBreakOnStatus
0x14006ae0f  test    ebx, ebx
0x14006ae11  jns     short loc_14006ADC6
0x14006ae13  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ae1a  lea     rax, WPP_GLOBAL_Control
0x14006ae21  cmp     rcx, rax
0x14006ae24  jz      short loc_14006ADC6
0x14006ae26  mov     eax, [rcx+2Ch]
0x14006ae29  test    dil, al
0x14006ae2c  jz      short loc_14006ADC6
0x14006ae2e  cmp     byte ptr [rcx+29h], 2
0x14006ae32  jb      short loc_14006ADC6
0x14006ae34  mov     edx, 47h ; 'G'
0x14006ae39  mov     rcx, [rcx+18h]
0x14006ae3d  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x14006ae44  mov     dword ptr [rsp+0D0h+DataBufferLength], ebx
0x14006ae48  mov     r9, r14
0x14006ae4b  mov     [rsp+0D0h+DataBuffer], rsi
0x14006ae50  call    WPP_SF_qqd
0x14006ae55  jmp     loc_14006ADC6
0x14006ae5a  call    Feature_ReFS_OneDrive_Support__private_IsEnabledDeviceUsageNoInline
0x14006ae5f  test    eax, eax
0x14006ae61  jz      loc_14006B07C
0x14006ae67  mov     rcx, [r14+20h]; InitiatingInstance
0x14006ae6b  mov     r9, r13; Guid
0x14006ae6e  mov     r8d, ebx; FileTag
0x14006ae71  mov     rdx, rsi; FileObject
0x14006ae74  call    cs:__imp_FltUntagFile
0x14006ae7b  nop     dword ptr [rax+rax+00h]
0x14006ae80  mov     ecx, eax
0x14006ae82  mov     ebx, eax
0x14006ae84  call    HsmDbgBreakOnStatus
0x14006ae89  test    ebx, ebx
0x14006ae8b  jns     loc_14006B100
0x14006ae91  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ae98  lea     rax, WPP_GLOBAL_Control
0x14006ae9f  cmp     rcx, rax
0x14006aea2  jz      loc_14006ADC6
0x14006aea8  mov     eax, [rcx+2Ch]
0x14006aeab  test    dil, al
0x14006aeae  jz      loc_14006ADC6
0x14006aeb4  cmp     byte ptr [rcx+29h], 2
0x14006aeb8  jb      loc_14006ADC6
0x14006aebe  mov     edx, 44h ; 'D'
0x14006aec3  jmp     loc_14006AE39
0x14006aec8  mov     ebx, 0C000009Ah
0x14006aecd  mov     ecx, ebx
0x14006aecf  call    HsmDbgBreakOnStatus
0x14006aed4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006aedb  lea     rax, WPP_GLOBAL_Control
0x14006aee2  cmp     rcx, rax
0x14006aee5  jz      loc_14006ACFB
0x14006aeeb  mov     eax, [rcx+2Ch]
0x14006aeee  mov     dil, 1
0x14006aef1  test    dil, al
0x14006aef4  jz      loc_14006ACFB
0x14006aefa  cmp     byte ptr [rcx+29h], 2
0x14006aefe  jb      loc_14006ACFB
0x14006af04  mov     rcx, [rcx+18h]
0x14006af08  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x14006af0f  mov     edx, 3Fh ; '?'
0x14006af14  mov     dword ptr [rsp+0D0h+DataBufferLength], ebx
0x14006af18  mov     r9, r14
0x14006af1b  mov     [rsp+0D0h+DataBuffer], rsi
0x14006af20  call    WPP_SF_qqd
0x14006af25  jmp     loc_14006ACFB
0x14006af2a  mov     ecx, [r10+2Ch]
0x14006af2e  mov     dil, 1
0x14006af31  test    dil, cl
0x14006af34  jz      loc_14006ACE6
0x14006af3a  cmp     byte ptr [r10+29h], 2
0x14006af3f  jb      loc_14006ACE6
0x14006af45  mov     rcx, [r10+18h]
0x14006af49  mov     edx, 40h ; '@'
0x14006af4e  jmp     short loc_14006AF59
0x14006af50  mov     rcx, [rcx+18h]
0x14006af54  mov     edx, 41h ; 'A'
0x14006af59  mov     dword ptr [rsp+0D0h+DataBufferLength], ebx
0x14006af5d  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x14006af64  mov     r9, r14
0x14006af67  mov     [rsp+0D0h+DataBuffer], rsi
0x14006af6c  call    WPP_SF_qqd
0x14006af71  jmp     loc_14006ACE6
0x14006af76  xor     r9d, r9d
0x14006af79  mov     [rbp+3Fh+var_80], dil
0x14006af7d  mov     r8d, 401000h
0x14006af83  mov     rdx, rsi
0x14006af86  mov     rcx, r14
0x14006af89  call    HsmpToggleFileAttributes
0x14006af8e  mov     ecx, eax
0x14006af90  mov     ebx, eax
0x14006af92  call    HsmDbgBreakOnStatus
0x14006af97  test    ebx, ebx
0x14006af99  jns     loc_14006AD3B
0x14006af9f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006afa6  lea     rax, WPP_GLOBAL_Control
0x14006afad  cmp     rcx, rax
0x14006afb0  jz      loc_14006ACE6
0x14006afb6  mov     eax, [rcx+2Ch]
0x14006afb9  test    dil, al
0x14006afbc  jz      loc_14006ACE6
0x14006afc2  cmp     byte ptr [rcx+29h], 2
0x14006afc6  jb      loc_14006ACE6
0x14006afcc  jmp     short loc_14006AF50
0x14006afce  cmp     [rbp+3Fh+arg_30], r12b
0x14006afd2  jnz     short loc_14006B00B
0x14006afd4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006afdb  lea     rax, WPP_GLOBAL_Control
0x14006afe2  cmp     rcx, rax
0x14006afe5  jz      loc_14006ADC6
0x14006afeb  mov     eax, [rcx+2Ch]
0x14006afee  test    dil, al
0x14006aff1  jz      loc_14006ADC6
0x14006aff7  cmp     byte ptr [rcx+29h], 2
0x14006affb  jb      loc_14006ADC6
0x14006b001  mov     edx, 42h ; 'B'
0x14006b006  jmp     loc_14006AE39
0x14006b00b  cmp     ebx, 0C0000277h
0x14006b011  jnz     loc_14006ADB6
0x14006b017  mov     rcx, [rbp+3Fh+InitiatingInstance]; Instance
0x14006b01b  lea     r8, [rbp+3Fh+var_78]
0x14006b01f  xorps   xmm0, xmm0
0x14006b022  mov     rdx, rsi; FileObject
0x14006b025  movups  [rbp+3Fh+var_50], xmm0
0x14006b029  call    HsmpRpReadBuffer
0x14006b02e  mov     ecx, eax
0x14006b030  mov     ebx, eax
0x14006b032  call    HsmDbgBreakOnStatus
0x14006b037  mov     r12, [rbp+3Fh+var_78]
0x14006b03b  test    ebx, ebx
0x14006b03d  js      short loc_14006B060
0x14006b03f  mov     ebx, [r12]
0x14006b043  test    ebx, ebx
0x14006b045  js      short loc_14006B052
0x14006b047  movups  xmm0, xmmword ptr [r12+8]
0x14006b04d  movdqu  [rbp+3Fh+var_50], xmm0
0x14006b052  xor     eax, eax
0x14006b054  lea     r13, [rbp+3Fh+var_50]
0x14006b058  test    ebx, ebx
0x14006b05a  cmovs   r13, rax
0x14006b05e  jmp     short loc_14006B071
0x14006b060  cmp     ebx, 0C0000275h
0x14006b066  jnz     loc_14006B12D
0x14006b06c  xor     ebx, ebx
0x14006b06e  xor     r13d, r13d
0x14006b071  cmp     dword ptr [r14+50h], 1Ch
0x14006b076  jz      loc_14006AE5A
0x14006b07c  movzx   eax, [rbp+3Fh+var_7C]
0x14006b080  xor     r9d, r9d
0x14006b083  mov     rcx, [r14+20h]
0x14006b087  mov     r8d, r15d
0x14006b08a  mov     [rsp+0D0h+var_90], 0
0x14006b092  mov     rdx, rsi
0x14006b095  mov     [rsp+0D0h+var_98], r13
0x14006b09a  mov     [rsp+0D0h+var_A0], ebx
0x14006b09e  mov     [rsp+0D0h+DataBufferLength], ax
0x14006b0a3  mov     rax, [rbp+3Fh+P]
0x14006b0a7  mov     [rsp+0D0h+DataBuffer], rax
0x14006b0ac  call    cs:__imp_FltTagFileEx
0x14006b0b3  nop     dword ptr [rax+rax+00h]
0x14006b0b8  mov     ecx, eax
0x14006b0ba  mov     ebx, eax
0x14006b0bc  call    HsmDbgBreakOnStatus
0x14006b0c1  test    ebx, ebx
0x14006b0c3  jns     loc_14006B178
0x14006b0c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b0d0  lea     rax, WPP_GLOBAL_Control
0x14006b0d7  cmp     rcx, rax
0x14006b0da  jz      loc_14006ADC6
0x14006b0e0  mov     eax, [rcx+2Ch]
0x14006b0e3  test    dil, al
0x14006b0e6  jz      loc_14006ADC6
0x14006b0ec  cmp     byte ptr [rcx+29h], 2
  ... truncated ...
```
