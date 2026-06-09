# HsmpRpCreate

- ea: `0x14006ad44`
- end: `0x14006b30c`
- name: `HsmpRpCreate`
- size: `1480`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x140046cc0`
- `0x1400608bc`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000b62c`
- `0x14001e1c0`
- `0x14005a7dc`
- `0x14006ad44`
- `0x14006b314`
- `0x14006bcf4`
- `0x1400766ac`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006ae0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006af01`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ae0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006af01`
- `ntoskrnl!ExAllocatePool2` at `0x14006ada9`
- `ntoskrnl!ExAllocatePool2` at `0x14006ada9`
- `FLTMGR!FltTagFile` at `0x14006aeb9`
- `FLTMGR!FltTagFile` at `0x14006b23f`
- `FLTMGR!FltTagFile` at `0x14006aeb9`
- `FLTMGR!FltTagFile` at `0x14006b23f`
- `FLTMGR!FltTagFileEx` at `0x14006b1cc`
- `FLTMGR!FltTagFileEx` at `0x14006b1cc`
- `FLTMGR!FltUntagFile` at `0x14006af94`
- `FLTMGR!FltUntagFile` at `0x14006af94`

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
  NTSTATUS v24; // eax
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
    HsmDbgBreakOnStatus(v14);
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
      HsmDbgBreakOnStatus(v14);
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
    HsmDbgBreakOnStatus(v14);
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
        HsmDbgBreakOnStatus(v14);
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
          HsmDbgBreakOnStatus(v14);
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
      || (LOBYTE(v17) = 1, v14 = HsmpToggleFileSparseAttribute(a1, a2, v17), HsmDbgBreakOnStatus(v14), v14 >= 0) )
    {
      if ( v26 )
        goto LABEL_13;
      v14 = HsmpToggleFileAttributes(a1, a2, 0, 4198400);
      HsmDbgBreakOnStatus(v14);
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
  HsmDbgBreakOnStatus(-1073741670);
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
0x14006ad44  mov     [rsp-8+arg_10], rbx
0x14006ad49  push    rbp
0x14006ad4a  push    rsi
0x14006ad4b  push    rdi
0x14006ad4c  push    r12
0x14006ad4e  push    r13
0x14006ad50  push    r14
0x14006ad52  push    r15
0x14006ad54  lea     rbp, [rsp-0Fh]
0x14006ad59  sub     rsp, 0A0h
0x14006ad60  mov     rax, cs:__security_cookie
0x14006ad67  xor     rax, rsp
0x14006ad6a  mov     [rbp+3Fh+var_40], rax
0x14006ad6e  mov     rax, [rcx+20h]
0x14006ad72  mov     rsi, rdx
0x14006ad75  mov     rbx, [rbp+3Fh+arg_20]
0x14006ad79  mov     edx, 4000h
0x14006ad7e  mov     rdi, r8
0x14006ad81  mov     [rbp+3Fh+var_58], r8
0x14006ad85  mov     r14, rcx
0x14006ad88  mov     [rbp+3Fh+var_7C], dx
0x14006ad8c  xor     r12d, r12d
0x14006ad8f  mov     [rbp+3Fh+var_68], r9d
0x14006ad93  mov     ecx, 100h
0x14006ad98  mov     [rbp+3Fh+InitiatingInstance], rax
0x14006ad9c  mov     r8d, 70527348h
0x14006ada2  mov     [rbp+3Fh+var_78], r12
0x14006ada6  mov     r13d, r9d
0x14006ada9  call    cs:__imp_ExAllocatePool2
0x14006adb0  nop     dword ptr [rax+rax+00h]
0x14006adb5  mov     [rbp+3Fh+P], rax
0x14006adb9  test    rax, rax
0x14006adbc  jz      loc_14006AFE8
0x14006adc2  mov     r9d, dword ptr [rbp+3Fh+arg_28]
0x14006adc6  lea     rcx, [rbp+3Fh+var_7C]
0x14006adca  mov     qword ptr [rsp+0D0h+DataBufferLength], rcx
0x14006adcf  mov     r8, rbx
0x14006add2  mov     rcx, rdi
0x14006add5  mov     [rsp+0D0h+DataBuffer], rax
0x14006adda  mov     edx, r13d
0x14006addd  call    HsmiRpInitializeTable
0x14006ade2  mov     ecx, eax
0x14006ade4  mov     ebx, eax
0x14006ade6  call    HsmDbgBreakOnStatus
0x14006adeb  test    ebx, ebx
0x14006aded  jns     short loc_14006AE45
0x14006adef  mov     r10, cs:WPP_GLOBAL_Control
0x14006adf6  lea     rax, WPP_GLOBAL_Control
0x14006adfd  cmp     r10, rax
0x14006ae00  jnz     loc_14006B04A
0x14006ae06  mov     rcx, [rbp+3Fh+P]; P
0x14006ae0a  mov     edx, 70527348h; Tag
0x14006ae0f  call    cs:__imp_ExFreePoolWithTag
0x14006ae16  nop     dword ptr [rax+rax+00h]
0x14006ae1b  mov     eax, ebx
0x14006ae1d  mov     rcx, [rbp+3Fh+var_40]
0x14006ae21  xor     rcx, rsp; StackCookie
0x14006ae24  call    __security_check_cookie
0x14006ae29  mov     rbx, [rsp+0D0h+arg_10]
0x14006ae31  add     rsp, 0A0h
0x14006ae38  pop     r15
0x14006ae3a  pop     r14
0x14006ae3c  pop     r13
0x14006ae3e  pop     r12
0x14006ae40  pop     rdi
0x14006ae41  pop     rsi
0x14006ae42  pop     rbp
0x14006ae43  retn
0x14006ae45  mov     eax, r13d
0x14006ae48  mov     dil, 1
0x14006ae4b  and     eax, 4
0x14006ae4e  mov     [rbp+3Fh+var_64], eax
0x14006ae51  jz      loc_14006B096
0x14006ae57  mov     [rbp+3Fh+var_80], r12b
0x14006ae5b  mov     r15d, r13d
0x14006ae5e  mov     [rbp+3Fh+var_7F], r12b
0x14006ae62  and     r15d, 2
0x14006ae66  mov     eax, r13d
0x14006ae69  shl     r15d, 4
0x14006ae6d  and     eax, 0C0h
0x14006ae72  or      r15d, eax
0x14006ae75  mov     eax, r13d
0x14006ae78  add     r15d, r15d
0x14006ae7b  and     eax, 20h
0x14006ae7e  or      r15d, eax
0x14006ae81  shl     r15d, 7
0x14006ae85  or      r15d, cs:dword_140029670
0x14006ae8c  cmp     [rsi+4Bh], r12b
0x14006ae90  jnz     short loc_14006AE9A
0x14006ae92  mov     [rsi+4Bh], dil
0x14006ae96  mov     [rbp+3Fh+var_7F], dil
0x14006ae9a  movzx   eax, [rbp+3Fh+var_7C]
0x14006ae9e  xor     r9d, r9d; Guid
0x14006aea1  mov     rcx, [rbp+3Fh+InitiatingInstance]; InitiatingInstance
0x14006aea5  mov     r8d, r15d; FileTag
0x14006aea8  mov     [rsp+0D0h+DataBufferLength], ax; DataBufferLength
0x14006aead  mov     rdx, rsi; FileObject
0x14006aeb0  mov     rax, [rbp+3Fh+P]
0x14006aeb4  mov     [rsp+0D0h+DataBuffer], rax; DataBuffer
0x14006aeb9  call    cs:__imp_FltTagFile
0x14006aec0  nop     dword ptr [rax+rax+00h]
0x14006aec5  mov     ecx, eax
0x14006aec7  mov     ebx, eax
0x14006aec9  call    HsmDbgBreakOnStatus
0x14006aece  test    ebx, ebx
0x14006aed0  js      loc_14006B0EE
0x14006aed6  cmp     [rbp+3Fh+var_64], 0
0x14006aeda  jz      loc_14006B2A1
0x14006aee0  cmp     [rbp+3Fh+var_80], 0
0x14006aee4  jz      short loc_14006AF12
0x14006aee6  cmp     [rbp+3Fh+var_7F], 0
0x14006aeea  jz      short loc_14006AEF0
0x14006aeec  mov     byte ptr [rsi+4Bh], 0
0x14006aef0  test    r12, r12
0x14006aef3  jz      loc_14006AE06
0x14006aef9  mov     edx, 70527348h; Tag
0x14006aefe  mov     rcx, r12; P
0x14006af01  call    cs:__imp_ExFreePoolWithTag
0x14006af08  nop     dword ptr [rax+rax+00h]
0x14006af0d  jmp     loc_14006AE06
0x14006af12  mov     r9d, 401000h
0x14006af18  xor     r8d, r8d
0x14006af1b  mov     rdx, rsi
0x14006af1e  mov     rcx, r14
0x14006af21  call    HsmpToggleFileAttributes
0x14006af26  mov     ecx, eax
0x14006af28  mov     ebx, eax
0x14006af2a  call    HsmDbgBreakOnStatus
0x14006af2f  test    ebx, ebx
0x14006af31  jns     short loc_14006AEE6
0x14006af33  mov     rcx, cs:WPP_GLOBAL_Control
0x14006af3a  lea     rax, WPP_GLOBAL_Control
0x14006af41  cmp     rcx, rax
0x14006af44  jz      short loc_14006AEE6
0x14006af46  mov     eax, [rcx+2Ch]
0x14006af49  test    dil, al
0x14006af4c  jz      short loc_14006AEE6
0x14006af4e  cmp     byte ptr [rcx+29h], 2
0x14006af52  jb      short loc_14006AEE6
0x14006af54  mov     edx, 47h ; 'G'
0x14006af59  mov     rcx, [rcx+18h]
0x14006af5d  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x14006af64  mov     dword ptr [rsp+0D0h+DataBufferLength], ebx
0x14006af68  mov     r9, r14
0x14006af6b  mov     [rsp+0D0h+DataBuffer], rsi
0x14006af70  call    WPP_SF_qqd
0x14006af75  jmp     loc_14006AEE6
0x14006af7a  call    Feature_ReFS_OneDrive_Support__private_IsEnabledDeviceUsageNoInline
0x14006af7f  test    eax, eax
0x14006af81  jz      loc_14006B19C
0x14006af87  mov     rcx, [r14+20h]; InitiatingInstance
0x14006af8b  mov     r9, r13; Guid
0x14006af8e  mov     r8d, ebx; FileTag
0x14006af91  mov     rdx, rsi; FileObject
0x14006af94  call    cs:__imp_FltUntagFile
0x14006af9b  nop     dword ptr [rax+rax+00h]
0x14006afa0  mov     ecx, eax
0x14006afa2  mov     ebx, eax
0x14006afa4  call    HsmDbgBreakOnStatus
0x14006afa9  test    ebx, ebx
0x14006afab  jns     loc_14006B220
0x14006afb1  mov     rcx, cs:WPP_GLOBAL_Control
0x14006afb8  lea     rax, WPP_GLOBAL_Control
0x14006afbf  cmp     rcx, rax
0x14006afc2  jz      loc_14006AEE6
0x14006afc8  mov     eax, [rcx+2Ch]
0x14006afcb  test    dil, al
0x14006afce  jz      loc_14006AEE6
0x14006afd4  cmp     byte ptr [rcx+29h], 2
0x14006afd8  jb      loc_14006AEE6
0x14006afde  mov     edx, 44h ; 'D'
0x14006afe3  jmp     loc_14006AF59
0x14006afe8  mov     ebx, 0C000009Ah
0x14006afed  mov     ecx, ebx
0x14006afef  call    HsmDbgBreakOnStatus
0x14006aff4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006affb  lea     rax, WPP_GLOBAL_Control
0x14006b002  cmp     rcx, rax
0x14006b005  jz      loc_14006AE1B
0x14006b00b  mov     eax, [rcx+2Ch]
0x14006b00e  mov     dil, 1
0x14006b011  test    dil, al
0x14006b014  jz      loc_14006AE1B
0x14006b01a  cmp     byte ptr [rcx+29h], 2
0x14006b01e  jb      loc_14006AE1B
0x14006b024  mov     rcx, [rcx+18h]
0x14006b028  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x14006b02f  mov     edx, 3Fh ; '?'
0x14006b034  mov     dword ptr [rsp+0D0h+DataBufferLength], ebx
0x14006b038  mov     r9, r14
0x14006b03b  mov     [rsp+0D0h+DataBuffer], rsi
0x14006b040  call    WPP_SF_qqd
0x14006b045  jmp     loc_14006AE1B
0x14006b04a  mov     ecx, [r10+2Ch]
0x14006b04e  mov     dil, 1
0x14006b051  test    dil, cl
0x14006b054  jz      loc_14006AE06
0x14006b05a  cmp     byte ptr [r10+29h], 2
0x14006b05f  jb      loc_14006AE06
0x14006b065  mov     rcx, [r10+18h]
0x14006b069  mov     edx, 40h ; '@'
0x14006b06e  jmp     short loc_14006B079
0x14006b070  mov     rcx, [rcx+18h]
0x14006b074  mov     edx, 41h ; 'A'
0x14006b079  mov     dword ptr [rsp+0D0h+DataBufferLength], ebx
0x14006b07d  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x14006b084  mov     r9, r14
0x14006b087  mov     [rsp+0D0h+DataBuffer], rsi
0x14006b08c  call    WPP_SF_qqd
0x14006b091  jmp     loc_14006AE06
0x14006b096  xor     r9d, r9d
0x14006b099  mov     [rbp+3Fh+var_80], dil
0x14006b09d  mov     r8d, 401000h
0x14006b0a3  mov     rdx, rsi
0x14006b0a6  mov     rcx, r14
0x14006b0a9  call    HsmpToggleFileAttributes
0x14006b0ae  mov     ecx, eax
0x14006b0b0  mov     ebx, eax
0x14006b0b2  call    HsmDbgBreakOnStatus
0x14006b0b7  test    ebx, ebx
0x14006b0b9  jns     loc_14006AE5B
0x14006b0bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b0c6  lea     rax, WPP_GLOBAL_Control
0x14006b0cd  cmp     rcx, rax
0x14006b0d0  jz      loc_14006AE06
0x14006b0d6  mov     eax, [rcx+2Ch]
0x14006b0d9  test    dil, al
0x14006b0dc  jz      loc_14006AE06
0x14006b0e2  cmp     byte ptr [rcx+29h], 2
0x14006b0e6  jb      loc_14006AE06
0x14006b0ec  jmp     short loc_14006B070
0x14006b0ee  cmp     [rbp+3Fh+arg_30], r12b
0x14006b0f2  jnz     short loc_14006B12B
0x14006b0f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b0fb  lea     rax, WPP_GLOBAL_Control
0x14006b102  cmp     rcx, rax
0x14006b105  jz      loc_14006AEE6
0x14006b10b  mov     eax, [rcx+2Ch]
0x14006b10e  test    dil, al
0x14006b111  jz      loc_14006AEE6
0x14006b117  cmp     byte ptr [rcx+29h], 2
0x14006b11b  jb      loc_14006AEE6
0x14006b121  mov     edx, 42h ; 'B'
0x14006b126  jmp     loc_14006AF59
0x14006b12b  cmp     ebx, 0C0000277h
0x14006b131  jnz     loc_14006AED6
0x14006b137  mov     rcx, [rbp+3Fh+InitiatingInstance]; Instance
0x14006b13b  lea     r8, [rbp+3Fh+var_78]
0x14006b13f  xorps   xmm0, xmm0
0x14006b142  mov     rdx, rsi; FileObject
0x14006b145  movups  [rbp+3Fh+var_50], xmm0
0x14006b149  call    HsmpRpReadBuffer
0x14006b14e  mov     ecx, eax
0x14006b150  mov     ebx, eax
0x14006b152  call    HsmDbgBreakOnStatus
0x14006b157  mov     r12, [rbp+3Fh+var_78]
0x14006b15b  test    ebx, ebx
0x14006b15d  js      short loc_14006B180
0x14006b15f  mov     ebx, [r12]
0x14006b163  test    ebx, ebx
0x14006b165  js      short loc_14006B172
0x14006b167  movups  xmm0, xmmword ptr [r12+8]
0x14006b16d  movdqu  [rbp+3Fh+var_50], xmm0
0x14006b172  xor     eax, eax
0x14006b174  lea     r13, [rbp+3Fh+var_50]
0x14006b178  test    ebx, ebx
0x14006b17a  cmovs   r13, rax
0x14006b17e  jmp     short loc_14006B191
0x14006b180  cmp     ebx, 0C0000275h
0x14006b186  jnz     loc_14006B24D
0x14006b18c  xor     ebx, ebx
0x14006b18e  xor     r13d, r13d
0x14006b191  cmp     dword ptr [r14+50h], 1Ch
0x14006b196  jz      loc_14006AF7A
0x14006b19c  movzx   eax, [rbp+3Fh+var_7C]
0x14006b1a0  xor     r9d, r9d
0x14006b1a3  mov     rcx, [r14+20h]
0x14006b1a7  mov     r8d, r15d
0x14006b1aa  mov     [rsp+0D0h+var_90], 0
0x14006b1b2  mov     rdx, rsi
0x14006b1b5  mov     [rsp+0D0h+var_98], r13
0x14006b1ba  mov     [rsp+0D0h+var_A0], ebx
0x14006b1be  mov     [rsp+0D0h+DataBufferLength], ax
0x14006b1c3  mov     rax, [rbp+3Fh+P]
0x14006b1c7  mov     [rsp+0D0h+DataBuffer], rax
0x14006b1cc  call    cs:__imp_FltTagFileEx
0x14006b1d3  nop     dword ptr [rax+rax+00h]
0x14006b1d8  mov     ecx, eax
0x14006b1da  mov     ebx, eax
0x14006b1dc  call    HsmDbgBreakOnStatus
0x14006b1e1  test    ebx, ebx
0x14006b1e3  jns     loc_14006B298
0x14006b1e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b1f0  lea     rax, WPP_GLOBAL_Control
0x14006b1f7  cmp     rcx, rax
0x14006b1fa  jz      loc_14006AEE6
0x14006b200  mov     eax, [rcx+2Ch]
0x14006b203  test    dil, al
0x14006b206  jz      loc_14006AEE6
0x14006b20c  cmp     byte ptr [rcx+29h], 2
  ... truncated ...
```
