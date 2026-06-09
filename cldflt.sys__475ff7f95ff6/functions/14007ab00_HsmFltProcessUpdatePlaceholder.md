# HsmFltProcessUpdatePlaceholder

- ea: `0x14007ab00`
- end: `0x14007b063`
- name: `HsmFltProcessUpdatePlaceholder`
- size: `1379`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, PFLT_CALLBACK_DATA CallbackData, _DWORD *, unsigned int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x14004dff0`

## callees

- `0x140001b00`
- `0x140003c50`
- `0x14000abb8`
- `0x14000ac28`
- `0x1400350c0`
- `0x140050dc0`
- `0x140052574`
- `0x14007ab00`
- `0x14007b06c`
- `0x14007b72c`

## import_xrefs

- `FLTMGR!FltGetRequestorProcess` at `0x14007ad22`
- `FLTMGR!FltGetRequestorProcess` at `0x14007ad22`

## pseudocode

```c
__int64 __fastcall HsmFltProcessUpdatePlaceholder(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        PFLT_CALLBACK_DATA CallbackData,
        _DWORD *a9,
        unsigned int a10,
        int a11)
{
  __int64 v11; // rdi
  unsigned int v14; // edx
  unsigned int v15; // r8d
  unsigned int v16; // eax
  unsigned int v17; // edx
  unsigned int SyncPolicy; // ebx
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  int v21; // r14d
  PFLT_CALLBACK_DATA v22; // r15
  unsigned int RequestorProcess; // eax
  unsigned int v24; // r12d
  __int64 v25; // r11
  _QWORD *v26; // rbx
  _DWORD *v27; // rcx
  _QWORD *v28; // r9
  _QWORD *v29; // rdx
  __int64 v30; // r10
  __int64 *v31; // r13
  int v32; // r12d
  __int64 v33; // r8
  unsigned int v34; // r11d
  __int64 v35; // rax
  int updated; // eax
  int v37; // r8d
  __int64 v38; // rax
  __int64 v40; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v41; // [rsp+C0h] [rbp+50h]
  int v42; // [rsp+C8h] [rbp+58h] BYREF
  int v43; // [rsp+CCh] [rbp+5Ch]

  v43 = HIDWORD(a4);
  v41 = a3;
  v11 = (__int64)a9;
  v40 = 0;
  v42 = 0;
  v14 = a9[17];
  if ( v14 > a10
    || (v15 = a9[18], v15 > a10 - v14)
    || (v16 = a9[15], v16 > a10)
    || (v17 = a9[16], v17 > a10 - v16)
    || v17 > 0x1000 )
  {
    SyncPolicy = -1073688821;
    HsmDbgBreakOnStatus(-1073688821);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v20 = 167;
      goto LABEL_85;
    }
    return SyncPolicy;
  }
  if ( (a9[2] & 0x80u) != 0 && v17 )
  {
    SyncPolicy = -1073688821;
    HsmDbgBreakOnStatus(-1073688821);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v20 = 168;
LABEL_85:
      WPP_SF_qqiqd(
        v19->AttachedDevice,
        v20,
        WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        CallbackData,
        a2,
        a5,
        a7,
        -1073688821);
      return SyncPolicy;
    }
    return SyncPolicy;
  }
  if ( (v15 & 0xF) == 0 )
  {
    v21 = a11;
    if ( (unsigned int)(a11 - 1) <= 6 )
    {
      SyncPolicy = -1073688821;
      HsmDbgBreakOnStatus(-1073688821);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqiDd(
          WPP_GLOBAL_Control->AttachedDevice,
          170,
          WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
          CallbackData,
          a2,
          a7,
          v21,
          -1073688821);
      }
      return SyncPolicy;
    }
    SyncPolicy = HsmpCldGetSyncPolicy(a2, 0, a3, 0, (__int64)&v42);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( (SyncPolicy & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqiqd(
          WPP_GLOBAL_Control->AttachedDevice,
          171,
          WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
          CallbackData,
          a2,
          a5,
          a7,
          SyncPolicy);
      }
      return SyncPolicy;
    }
    v22 = CallbackData;
    if ( (v42 & 0x20000000) == 0 )
    {
      LOBYTE(a10) = 0;
      if ( CallbackData )
        RequestorProcess = (unsigned int)FltGetRequestorProcess(CallbackData);
      else
        RequestorProcess = 0;
      SyncPolicy = HsmpCldCheckSyncProviderAccess(a2, a5, a3, RequestorProcess, (__int64)&a10);
      HsmDbgBreakOnStatus(SyncPolicy);
      if ( (SyncPolicy & 0x80000000) != 0 )
      {
LABEL_35:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqqd(
            WPP_GLOBAL_Control->AttachedDevice,
            172,
            WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
            a2,
            v22,
            a3,
            SyncPolicy);
        }
        return SyncPolicy;
      }
      if ( !(_BYTE)a10 )
      {
        SyncPolicy = -1073688808;
        HsmDbgBreakOnStatus(-1073688808);
        goto LABEL_35;
      }
    }
    if ( (*(_DWORD *)(v11 + 8) & 0x2000) != 0 )
      HsmpDeletePropertyStream(a2, a6);
    v24 = *(_DWORD *)(v11 + 8);
    v25 = *(_QWORD *)(v11 + 16);
    v40 = v25;
    a10 = v24;
    if ( (v24 & 0x20000) != 0 )
    {
      v30 = 0;
      v26 = 0;
      v28 = 0;
      v29 = 0;
      v27 = 0;
    }
    else
    {
      v26 = (_QWORD *)(v11 + 24);
      v27 = (_DWORD *)(v11 + 56);
      if ( (v24 & 0x10000) != 0 )
      {
        v28 = (_QWORD *)(v11 + 32);
        v29 = (_QWORD *)(v11 + 40);
        v30 = v11 + 48;
      }
      else
      {
        if ( !*v26 )
          v26 = 0;
        v28 = (_QWORD *)(v11 + 32);
        if ( !*v27 )
          v27 = 0;
        v29 = (_QWORD *)(v11 + 40);
        if ( !*v28 )
          v28 = 0;
        if ( !*v29 )
          v29 = 0;
        v30 = (v11 + 48) & -(__int64)(*(_QWORD *)(v11 + 48) != 0);
      }
    }
    if ( (*(_DWORD *)(a5 + 28) & 2) != 0 )
    {
      v37 = *(_DWORD *)(v11 + 64);
      if ( v37 )
        v38 = v11 + *(unsigned int *)(v11 + 60);
      else
        v38 = 0;
      updated = HsmiOpUpdatePlaceholderDirectory(a2, a5, a3, v24, v38, v37, v27, v28, v29, v30);
    }
    else
    {
      if ( v25 || v21 )
        v31 = &v40;
      else
        v31 = 0;
      v32 = *(_DWORD *)(v11 + 64);
      if ( v32 )
        v33 = v11 + *(unsigned int *)(v11 + 60);
      else
        v33 = 0;
      v34 = *(_DWORD *)(v11 + 72);
      if ( v34 )
        v35 = v11 + *(unsigned int *)(v11 + 68);
      else
        v35 = 0;
      updated = HsmiOpUpdatePlaceholderFile(a2, a5, v41, a10, v35, v34 >> 4, v33, v32, v26, v27, v28, v29, v30, v31);
    }
    SyncPolicy = updated;
    HsmDbgBreakOnStatus(updated);
    if ( (SyncPolicy & 0x80000000) == 0 )
    {
      if ( v21 )
        *(_QWORD *)v11 = v40;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          174,
          WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
          v22,
          a2,
          a7,
          SyncPolicy);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqiDd(
        WPP_GLOBAL_Control->AttachedDevice,
        173,
        WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        v22,
        a2,
        a7,
        v21,
        SyncPolicy);
    }
    return SyncPolicy;
  }
  SyncPolicy = -1073688821;
  HsmDbgBreakOnStatus(-1073688821);
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v20 = 169;
    goto LABEL_85;
  }
  return SyncPolicy;
}

```

## disassembly

```asm
0x14007ab00  mov     rax, rsp
0x14007ab03  mov     [rax+10h], rbx
0x14007ab07  mov     [rax+20h], r9
0x14007ab0b  mov     [rax+18h], r8
0x14007ab0f  mov     [rax+8], rcx
0x14007ab13  push    rbp
0x14007ab14  push    rsi
0x14007ab15  push    rdi
0x14007ab16  push    r12
0x14007ab18  push    r13
0x14007ab1a  push    r14
0x14007ab1c  push    r15
0x14007ab1e  mov     rbp, rsp
0x14007ab21  sub     rsp, 70h
0x14007ab25  mov     rdi, [rbp+arg_40]
0x14007ab2c  xor     r12d, r12d
0x14007ab2f  mov     ecx, [rbp+arg_48]
0x14007ab35  mov     rsi, rdx
0x14007ab38  mov     r13, r8
0x14007ab3b  mov     [rbp+arg_0], r12
0x14007ab3f  mov     [rbp+arg_18], r12d
0x14007ab43  mov     edx, [rdi+44h]
0x14007ab46  cmp     edx, ecx
0x14007ab48  ja      loc_14007AFE6
0x14007ab4e  mov     r8d, [rdi+48h]
0x14007ab52  mov     eax, ecx
0x14007ab54  sub     eax, edx
0x14007ab56  cmp     r8d, eax
0x14007ab59  ja      loc_14007AFE6
0x14007ab5f  mov     eax, [rdi+3Ch]
0x14007ab62  cmp     eax, ecx
0x14007ab64  ja      loc_14007AFE6
0x14007ab6a  mov     edx, [rdi+40h]
0x14007ab6d  sub     ecx, eax
0x14007ab6f  cmp     edx, ecx
0x14007ab71  ja      loc_14007AFE6
0x14007ab77  cmp     edx, 1000h
0x14007ab7d  ja      loc_14007AFE6
0x14007ab83  mov     eax, [rdi+8]
0x14007ab86  test    al, al
0x14007ab88  jns     short loc_14007ABD2
0x14007ab8a  test    edx, edx
0x14007ab8c  jz      short loc_14007ABD2
0x14007ab8e  mov     edi, 0C000CF0Bh
0x14007ab93  mov     ecx, edi
0x14007ab95  mov     ebx, edi
0x14007ab97  call    HsmDbgBreakOnStatus
0x14007ab9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007aba3  lea     rax, WPP_GLOBAL_Control
0x14007abaa  cmp     rcx, rax
0x14007abad  jz      loc_14007B048
0x14007abb3  mov     eax, [rcx+2Ch]
0x14007abb6  test    al, 1
0x14007abb8  jz      loc_14007B048
0x14007abbe  cmp     byte ptr [rcx+29h], 2
0x14007abc2  jb      loc_14007B048
0x14007abc8  mov     edx, 0A8h
0x14007abcd  jmp     loc_14007B019
0x14007abd2  test    r8b, 0Fh
0x14007abd6  jz      short loc_14007AC1C
0x14007abd8  mov     edi, 0C000CF0Bh
0x14007abdd  mov     ecx, edi
0x14007abdf  mov     ebx, edi
0x14007abe1  call    HsmDbgBreakOnStatus
0x14007abe6  mov     rcx, cs:WPP_GLOBAL_Control
0x14007abed  lea     rax, WPP_GLOBAL_Control
0x14007abf4  cmp     rcx, rax
0x14007abf7  jz      loc_14007B048
0x14007abfd  mov     eax, [rcx+2Ch]
0x14007ac00  test    al, 1
0x14007ac02  jz      loc_14007B048
0x14007ac08  cmp     byte ptr [rcx+29h], 2
0x14007ac0c  jb      loc_14007B048
0x14007ac12  mov     edx, 0A9h
0x14007ac17  jmp     loc_14007B019
0x14007ac1c  mov     r14d, [rbp+arg_50]
0x14007ac23  lea     eax, [r14-1]
0x14007ac27  cmp     eax, 6
0x14007ac2a  ja      short loc_14007AC9B
0x14007ac2c  mov     edi, 0C000CF0Bh
0x14007ac31  mov     ecx, edi
0x14007ac33  mov     ebx, edi
0x14007ac35  call    HsmDbgBreakOnStatus
0x14007ac3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ac41  lea     rax, WPP_GLOBAL_Control
0x14007ac48  cmp     rcx, rax
0x14007ac4b  jz      loc_14007B048
0x14007ac51  mov     eax, [rcx+2Ch]
0x14007ac54  test    al, 1
0x14007ac56  jz      loc_14007B048
0x14007ac5c  cmp     byte ptr [rcx+29h], 2
0x14007ac60  jb      loc_14007B048
0x14007ac66  mov     r9, [rbp+CallbackData]
0x14007ac6a  mov     edx, 0AAh
0x14007ac6f  mov     dword ptr [rsp+70h+var_38], edi
0x14007ac73  mov     rax, [rbp+arg_30]
0x14007ac77  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x14007ac7e  mov     rcx, [rcx+18h]
0x14007ac82  mov     dword ptr [rsp+70h+var_40], r14d
0x14007ac87  mov     [rsp+70h+var_48], rax
0x14007ac8c  mov     [rsp+70h+var_50], rsi
0x14007ac91  call    WPP_SF_qqiDd
0x14007ac96  jmp     loc_14007B048
0x14007ac9b  lea     rax, [rbp+arg_18]
0x14007ac9f  xor     r9d, r9d
0x14007aca2  mov     r8, r13
0x14007aca5  mov     [rsp+70h+var_50], rax
0x14007acaa  xor     edx, edx
0x14007acac  mov     rcx, rsi
0x14007acaf  call    HsmpCldGetSyncPolicy
0x14007acb4  mov     ecx, eax
0x14007acb6  mov     ebx, eax
0x14007acb8  call    HsmDbgBreakOnStatus
0x14007acbd  test    ebx, ebx
0x14007acbf  jns     short loc_14007AD02
0x14007acc1  mov     r10, cs:WPP_GLOBAL_Control
0x14007acc8  lea     rax, WPP_GLOBAL_Control
0x14007accf  cmp     r10, rax
0x14007acd2  jz      loc_14007B048
0x14007acd8  mov     ecx, [r10+2Ch]
0x14007acdc  test    cl, 1
0x14007acdf  jz      loc_14007B048
0x14007ace5  cmp     byte ptr [r10+29h], 2
0x14007acea  jb      loc_14007B048
0x14007acf0  mov     rcx, [r10+18h]
0x14007acf4  mov     edx, 0ABh
0x14007acf9  mov     dword ptr [rsp+70h+var_38], ebx
0x14007acfd  jmp     loc_14007B021
0x14007ad02  test    [rbp+arg_18], 20000000h
0x14007ad09  mov     r15, [rbp+CallbackData]
0x14007ad0d  jnz     loc_14007ADCA
0x14007ad13  mov     byte ptr [rbp+arg_48], r12b
0x14007ad1a  test    r15, r15
0x14007ad1d  jz      short loc_14007AD30
0x14007ad1f  mov     rcx, r15; CallbackData
0x14007ad22  call    cs:__imp_FltGetRequestorProcess
0x14007ad29  nop     dword ptr [rax+rax+00h]
0x14007ad2e  jmp     short loc_14007AD33
0x14007ad30  mov     rax, r12
0x14007ad33  mov     rdx, [rbp+arg_20]
0x14007ad37  lea     rcx, [rbp+arg_48]
0x14007ad3e  mov     [rsp+70h+var_50], rcx
0x14007ad43  mov     r9, rax
0x14007ad46  mov     rcx, rsi
0x14007ad49  mov     r8, r13
0x14007ad4c  call    HsmpCldCheckSyncProviderAccess
0x14007ad51  mov     ecx, eax
0x14007ad53  mov     ebx, eax
0x14007ad55  call    HsmDbgBreakOnStatus
0x14007ad5a  test    ebx, ebx
0x14007ad5c  js      short loc_14007AD73
0x14007ad5e  cmp     byte ptr [rbp+arg_48], r12b
0x14007ad65  jnz     short loc_14007ADCA
0x14007ad67  mov     ebx, 0C000CF18h
0x14007ad6c  mov     ecx, ebx
0x14007ad6e  call    HsmDbgBreakOnStatus
0x14007ad73  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ad7a  lea     rax, WPP_GLOBAL_Control
0x14007ad81  cmp     rcx, rax
0x14007ad84  jz      loc_14007B048
0x14007ad8a  mov     eax, [rcx+2Ch]
0x14007ad8d  test    al, 1
0x14007ad8f  jz      loc_14007B048
0x14007ad95  cmp     byte ptr [rcx+29h], 2
0x14007ad99  jb      loc_14007B048
0x14007ad9f  mov     rcx, [rcx+18h]
0x14007ada3  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x14007adaa  mov     dword ptr [rsp+70h+var_40], ebx
0x14007adae  mov     edx, 0ACh
0x14007adb3  mov     [rsp+70h+var_48], r13
0x14007adb8  mov     r9, rsi
0x14007adbb  mov     [rsp+70h+var_50], r15
0x14007adc0  call    WPP_SF_qqqd
0x14007adc5  jmp     loc_14007B048
0x14007adca  test    dword ptr [rdi+8], 2000h
0x14007add1  jz      short loc_14007ADDF
0x14007add3  mov     rdx, [rbp+arg_28]
0x14007add7  mov     rcx, rsi
0x14007adda  call    HsmpDeletePropertyStream
0x14007addf  mov     r12d, [rdi+8]
0x14007ade3  mov     r11, [rdi+10h]
0x14007ade7  mov     [rbp+arg_0], r11
0x14007adeb  mov     [rbp+arg_48], r12d
0x14007adf2  bt      r12d, 11h
0x14007adf7  jb      short loc_14007AE50
0x14007adf9  lea     rbx, [rdi+18h]
0x14007adfd  lea     rcx, [rdi+38h]
0x14007ae01  bt      r12d, 10h
0x14007ae06  jb      short loc_14007AE42
0x14007ae08  xor     eax, eax
0x14007ae0a  cmp     [rbx], rax
0x14007ae0d  jnz     short loc_14007AE11
0x14007ae0f  mov     ebx, eax
0x14007ae11  lea     r9, [rdi+20h]
0x14007ae15  cmp     [rcx], eax
0x14007ae17  jnz     short loc_14007AE1C
0x14007ae19  mov     rcx, rax
0x14007ae1c  lea     rdx, [rdi+28h]
0x14007ae20  cmp     [r9], rax
0x14007ae23  jnz     short loc_14007AE28
0x14007ae25  mov     r9, rax
0x14007ae28  lea     r8, [rdi+30h]
0x14007ae2c  cmp     [rdx], rax
0x14007ae2f  jnz     short loc_14007AE34
0x14007ae31  mov     rdx, rax
0x14007ae34  mov     rax, [r8]
0x14007ae37  neg     rax
0x14007ae3a  sbb     r10, r10
0x14007ae3d  and     r10, r8
0x14007ae40  jmp     short loc_14007AE5C
0x14007ae42  lea     r9, [rdi+20h]
0x14007ae46  lea     rdx, [rdi+28h]
0x14007ae4a  lea     r10, [rdi+30h]
0x14007ae4e  jmp     short loc_14007AE5C
0x14007ae50  xor     r10d, r10d
0x14007ae53  xor     ebx, ebx
0x14007ae55  xor     r9d, r9d
0x14007ae58  xor     edx, edx
0x14007ae5a  xor     ecx, ecx
0x14007ae5c  mov     rax, [rbp+arg_20]
0x14007ae60  mov     eax, [rax+1Ch]
0x14007ae63  test    al, 2
0x14007ae65  jnz     loc_14007AEF5
0x14007ae6b  test    r11, r11
0x14007ae6e  jnz     short loc_14007AE7A
0x14007ae70  test    r14d, r14d
0x14007ae73  jnz     short loc_14007AE7A
0x14007ae75  xor     r13d, r13d
0x14007ae78  jmp     short loc_14007AE7E
0x14007ae7a  lea     r13, [rbp+arg_0]
0x14007ae7e  mov     r12d, [rdi+40h]
0x14007ae82  test    r12d, r12d
0x14007ae85  jz      short loc_14007AE90
0x14007ae87  mov     r8d, [rdi+3Ch]
0x14007ae8b  add     r8, rdi
0x14007ae8e  jmp     short loc_14007AE93
0x14007ae90  xor     r8d, r8d
0x14007ae93  mov     r11d, [rdi+48h]
0x14007ae97  test    r11d, r11d
0x14007ae9a  jz      short loc_14007AEA4
0x14007ae9c  mov     eax, [rdi+44h]
0x14007ae9f  add     rax, rdi
0x14007aea2  jmp     short loc_14007AEA6
0x14007aea4  xor     eax, eax
0x14007aea6  mov     [rsp+70h+var_8], r13
0x14007aeab  mov     [rsp+70h+var_10], r10
0x14007aeb0  mov     [rsp+70h+var_18], rdx
0x14007aeb5  mov     rdx, [rbp+arg_20]
0x14007aeb9  mov     [rsp+70h+var_20], r9
0x14007aebe  mov     r9d, [rbp+arg_48]
0x14007aec5  mov     [rsp+70h+var_28], rcx
0x14007aeca  mov     rcx, rsi
0x14007aecd  mov     [rsp+70h+var_30], rbx
0x14007aed2  mov     dword ptr [rsp+70h+var_38], r12d
0x14007aed7  mov     [rsp+70h+var_40], r8
0x14007aedc  mov     r8, [rbp+arg_10]
0x14007aee0  shr     r11d, 4
0x14007aee4  mov     dword ptr [rsp+70h+var_48], r11d
0x14007aee9  mov     [rsp+70h+var_50], rax
0x14007aeee  call    HsmiOpUpdatePlaceholderFile
0x14007aef3  jmp     short loc_14007AF38
0x14007aef5  mov     r8d, [rdi+40h]
0x14007aef9  test    r8d, r8d
0x14007aefc  jz      short loc_14007AF06
0x14007aefe  mov     eax, [rdi+3Ch]
0x14007af01  add     rax, rdi
0x14007af04  jmp     short loc_14007AF08
0x14007af06  xor     eax, eax
0x14007af08  mov     [rsp+70h+var_28], r10
0x14007af0d  mov     [rsp+70h+var_30], rdx
0x14007af12  mov     rdx, [rbp+arg_20]
0x14007af16  mov     [rsp+70h+var_38], r9
0x14007af1b  mov     r9d, r12d
0x14007af1e  mov     [rsp+70h+var_40], rcx
0x14007af23  mov     rcx, rsi
0x14007af26  mov     dword ptr [rsp+70h+var_48], r8d
0x14007af2b  mov     r8, r13
0x14007af2e  mov     [rsp+70h+var_50], rax
0x14007af33  call    HsmiOpUpdatePlaceholderDirectory
0x14007af38  mov     ecx, eax
0x14007af3a  mov     ebx, eax
0x14007af3c  call    HsmDbgBreakOnStatus
0x14007af41  test    ebx, ebx
0x14007af43  jns     short loc_14007AF82
0x14007af45  mov     rcx, cs:WPP_GLOBAL_Control
0x14007af4c  lea     rax, WPP_GLOBAL_Control
0x14007af53  cmp     rcx, rax
0x14007af56  jz      loc_14007B048
0x14007af5c  mov     eax, [rcx+2Ch]
0x14007af5f  test    al, 1
0x14007af61  jz      loc_14007B048
0x14007af67  cmp     byte ptr [rcx+29h], 2
0x14007af6b  jb      loc_14007B048
0x14007af71  mov     edx, 0ADh
0x14007af76  mov     dword ptr [rsp+70h+var_38], ebx
0x14007af7a  mov     r9, r15
0x14007af7d  jmp     loc_14007AC73
0x14007af82  test    r14d, r14d
0x14007af85  jz      short loc_14007AF8E
0x14007af87  mov     rax, [rbp+arg_0]
  ... truncated ...
```
