# HsmFltProcessUpdatePlaceholder

- ea: `0x14007a9c0`
- end: `0x14007af23`
- name: `HsmFltProcessUpdatePlaceholder`
- size: `1379`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, PFLT_CALLBACK_DATA CallbackData, __int64, int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x14004ded0`

## callees

- `0x140001b00`
- `0x140003c50`
- `0x14000abb8`
- `0x14000ac28`
- `0x1400350c0`
- `0x140050ca0`
- `0x140052454`
- `0x14007a9c0`
- `0x14007af2c`
- `0x14007b5ec`

## import_xrefs

- `FLTMGR!FltGetRequestorProcess` at `0x14007abe2`
- `FLTMGR!FltGetRequestorProcess` at `0x14007abe2`

## pseudocode

```c
__int64 __fastcall HsmFltProcessUpdatePlaceholder(
        __int64 a1,
        __int64 a2,
        struct _FILE_OBJECT *a3,
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
  PDEVICE_OBJECT v22; // rcx
  PFLT_CALLBACK_DATA v23; // r9
  __int64 v24; // rdx
  PFLT_CALLBACK_DATA v25; // r15
  unsigned int RequestorProcess; // eax
  int v27; // r12d
  __int64 v28; // r11
  __int64 *v29; // rbx
  _DWORD *v30; // rcx
  _QWORD *v31; // r9
  _QWORD *v32; // rdx
  _QWORD *v33; // r10
  __int64 *v34; // r13
  int v35; // r12d
  void *v36; // r8
  unsigned int v37; // r11d
  __int128 *v38; // rax
  unsigned int updated; // eax
  int v40; // r8d
  void *v41; // rax
  __int64 v43; // [rsp+B0h] [rbp+40h] BYREF
  struct _FILE_OBJECT *v44; // [rsp+C0h] [rbp+50h]
  int v45; // [rsp+C8h] [rbp+58h] BYREF
  int v46; // [rsp+CCh] [rbp+5Ch]

  v46 = HIDWORD(a4);
  v44 = a3;
  v11 = (__int64)a9;
  v43 = 0;
  v45 = 0;
  v14 = a9[17];
  if ( v14 > a10
    || (v15 = a9[18], v15 > a10 - v14)
    || (v16 = a9[15], v16 > a10)
    || (v17 = a9[16], v17 > a10 - v16)
    || v17 > 0x1000 )
  {
    SyncPolicy = -1073688821;
    HsmDbgBreakOnStatus(3221278475LL);
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
    HsmDbgBreakOnStatus(3221278475LL);
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
      HsmDbgBreakOnStatus(3221278475LL);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return SyncPolicy;
      }
      v23 = CallbackData;
      v24 = 170;
      goto LABEL_22;
    }
    SyncPolicy = HsmpCldGetSyncPolicy(a2, 0, (_DWORD)a3, 0, (__int64)&v45);
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
    v25 = CallbackData;
    if ( (v45 & 0x20000000) == 0 )
    {
      LOBYTE(a10) = 0;
      if ( CallbackData )
        RequestorProcess = (unsigned int)FltGetRequestorProcess(CallbackData);
      else
        RequestorProcess = 0;
      SyncPolicy = HsmpCldCheckSyncProviderAccess(a2, a5, (_DWORD)a3, RequestorProcess, (__int64)&a10);
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
            v25,
            a3,
            SyncPolicy);
        }
        return SyncPolicy;
      }
      if ( !(_BYTE)a10 )
      {
        SyncPolicy = -1073688808;
        HsmDbgBreakOnStatus(3221278488LL);
        goto LABEL_35;
      }
    }
    if ( (*(_DWORD *)(v11 + 8) & 0x2000) != 0 )
      HsmpDeletePropertyStream(a2, a6);
    v27 = *(_DWORD *)(v11 + 8);
    v28 = *(_QWORD *)(v11 + 16);
    v43 = v28;
    a10 = v27;
    if ( (v27 & 0x20000) != 0 )
    {
      v33 = 0;
      v29 = 0;
      v31 = 0;
      v32 = 0;
      v30 = 0;
    }
    else
    {
      v29 = (__int64 *)(v11 + 24);
      v30 = (_DWORD *)(v11 + 56);
      if ( (v27 & 0x10000) != 0 )
      {
        v31 = (_QWORD *)(v11 + 32);
        v32 = (_QWORD *)(v11 + 40);
        v33 = (_QWORD *)(v11 + 48);
      }
      else
      {
        if ( !*v29 )
          v29 = 0;
        v31 = (_QWORD *)(v11 + 32);
        if ( !*v30 )
          v30 = 0;
        v32 = (_QWORD *)(v11 + 40);
        if ( !*v31 )
          v31 = 0;
        if ( !*v32 )
          v32 = 0;
        v33 = (_QWORD *)((v11 + 48) & -(__int64)(*(_QWORD *)(v11 + 48) != 0));
      }
    }
    if ( (*(_DWORD *)(a5 + 28) & 2) != 0 )
    {
      v40 = *(_DWORD *)(v11 + 64);
      if ( v40 )
        v41 = (void *)(v11 + *(unsigned int *)(v11 + 60));
      else
        v41 = 0;
      updated = HsmiOpUpdatePlaceholderDirectory(a2, a5, a3, v27, v41, v40, v30, v31, v32, v33);
    }
    else
    {
      if ( v28 || v21 )
        v34 = &v43;
      else
        v34 = 0;
      v35 = *(_DWORD *)(v11 + 64);
      if ( v35 )
        v36 = (void *)(v11 + *(unsigned int *)(v11 + 60));
      else
        v36 = 0;
      v37 = *(_DWORD *)(v11 + 72);
      if ( v37 )
        v38 = (__int128 *)(v11 + *(unsigned int *)(v11 + 68));
      else
        v38 = 0;
      updated = HsmiOpUpdatePlaceholderFile(a2, a5, v44, a10, v38, v37 >> 4, v36, v35, v29, v30, v31, v32, v33, v34);
    }
    SyncPolicy = updated;
    HsmDbgBreakOnStatus(updated);
    if ( (SyncPolicy & 0x80000000) == 0 )
    {
      if ( v21 )
        *(_QWORD *)v11 = v43;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          174,
          WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
          v25,
          a2,
          a7,
          SyncPolicy);
      }
      return SyncPolicy;
    }
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return SyncPolicy;
    }
    v24 = 173;
    v23 = v25;
LABEL_22:
    WPP_SF_qqiDd(v22->AttachedDevice, v24, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids, v23, a2, a7);
    return SyncPolicy;
  }
  SyncPolicy = -1073688821;
  HsmDbgBreakOnStatus(3221278475LL);
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
0x14007a9c0  mov     rax, rsp
0x14007a9c3  mov     [rax+10h], rbx
0x14007a9c7  mov     [rax+20h], r9
0x14007a9cb  mov     [rax+18h], r8
0x14007a9cf  mov     [rax+8], rcx
0x14007a9d3  push    rbp
0x14007a9d4  push    rsi
0x14007a9d5  push    rdi
0x14007a9d6  push    r12
0x14007a9d8  push    r13
0x14007a9da  push    r14
0x14007a9dc  push    r15
0x14007a9de  mov     rbp, rsp
0x14007a9e1  sub     rsp, 70h
0x14007a9e5  mov     rdi, [rbp+arg_40]
0x14007a9ec  xor     r12d, r12d
0x14007a9ef  mov     ecx, [rbp+arg_48]
0x14007a9f5  mov     rsi, rdx
0x14007a9f8  mov     r13, r8
0x14007a9fb  mov     [rbp+arg_0], r12
0x14007a9ff  mov     [rbp+arg_18], r12d
0x14007aa03  mov     edx, [rdi+44h]
0x14007aa06  cmp     edx, ecx
0x14007aa08  ja      loc_14007AEA6
0x14007aa0e  mov     r8d, [rdi+48h]
0x14007aa12  mov     eax, ecx
0x14007aa14  sub     eax, edx
0x14007aa16  cmp     r8d, eax
0x14007aa19  ja      loc_14007AEA6
0x14007aa1f  mov     eax, [rdi+3Ch]
0x14007aa22  cmp     eax, ecx
0x14007aa24  ja      loc_14007AEA6
0x14007aa2a  mov     edx, [rdi+40h]
0x14007aa2d  sub     ecx, eax
0x14007aa2f  cmp     edx, ecx
0x14007aa31  ja      loc_14007AEA6
0x14007aa37  cmp     edx, 1000h
0x14007aa3d  ja      loc_14007AEA6
0x14007aa43  mov     eax, [rdi+8]
0x14007aa46  test    al, al
0x14007aa48  jns     short loc_14007AA92
0x14007aa4a  test    edx, edx
0x14007aa4c  jz      short loc_14007AA92
0x14007aa4e  mov     edi, 0C000CF0Bh
0x14007aa53  mov     ecx, edi
0x14007aa55  mov     ebx, edi
0x14007aa57  call    HsmDbgBreakOnStatus
0x14007aa5c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007aa63  lea     rax, WPP_GLOBAL_Control
0x14007aa6a  cmp     rcx, rax
0x14007aa6d  jz      loc_14007AF08
0x14007aa73  mov     eax, [rcx+2Ch]
0x14007aa76  test    al, 1
0x14007aa78  jz      loc_14007AF08
0x14007aa7e  cmp     byte ptr [rcx+29h], 2
0x14007aa82  jb      loc_14007AF08
0x14007aa88  mov     edx, 0A8h
0x14007aa8d  jmp     loc_14007AED9
0x14007aa92  test    r8b, 0Fh
0x14007aa96  jz      short loc_14007AADC
0x14007aa98  mov     edi, 0C000CF0Bh
0x14007aa9d  mov     ecx, edi
0x14007aa9f  mov     ebx, edi
0x14007aaa1  call    HsmDbgBreakOnStatus
0x14007aaa6  mov     rcx, cs:WPP_GLOBAL_Control
0x14007aaad  lea     rax, WPP_GLOBAL_Control
0x14007aab4  cmp     rcx, rax
0x14007aab7  jz      loc_14007AF08
0x14007aabd  mov     eax, [rcx+2Ch]
0x14007aac0  test    al, 1
0x14007aac2  jz      loc_14007AF08
0x14007aac8  cmp     byte ptr [rcx+29h], 2
0x14007aacc  jb      loc_14007AF08
0x14007aad2  mov     edx, 0A9h
0x14007aad7  jmp     loc_14007AED9
0x14007aadc  mov     r14d, [rbp+arg_50]
0x14007aae3  lea     eax, [r14-1]
0x14007aae7  cmp     eax, 6
0x14007aaea  ja      short loc_14007AB5B
0x14007aaec  mov     edi, 0C000CF0Bh
0x14007aaf1  mov     ecx, edi
0x14007aaf3  mov     ebx, edi
0x14007aaf5  call    HsmDbgBreakOnStatus
0x14007aafa  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ab01  lea     rax, WPP_GLOBAL_Control
0x14007ab08  cmp     rcx, rax
0x14007ab0b  jz      loc_14007AF08
0x14007ab11  mov     eax, [rcx+2Ch]
0x14007ab14  test    al, 1
0x14007ab16  jz      loc_14007AF08
0x14007ab1c  cmp     byte ptr [rcx+29h], 2
0x14007ab20  jb      loc_14007AF08
0x14007ab26  mov     r9, [rbp+CallbackData]
0x14007ab2a  mov     edx, 0AAh
0x14007ab2f  mov     dword ptr [rsp+70h+var_38], edi
0x14007ab33  mov     rax, [rbp+arg_30]
0x14007ab37  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x14007ab3e  mov     rcx, [rcx+18h]
0x14007ab42  mov     dword ptr [rsp+70h+var_40], r14d
0x14007ab47  mov     [rsp+70h+var_48], rax
0x14007ab4c  mov     [rsp+70h+var_50], rsi
0x14007ab51  call    WPP_SF_qqiDd
0x14007ab56  jmp     loc_14007AF08
0x14007ab5b  lea     rax, [rbp+arg_18]
0x14007ab5f  xor     r9d, r9d
0x14007ab62  mov     r8, r13
0x14007ab65  mov     [rsp+70h+var_50], rax
0x14007ab6a  xor     edx, edx
0x14007ab6c  mov     rcx, rsi
0x14007ab6f  call    HsmpCldGetSyncPolicy
0x14007ab74  mov     ecx, eax
0x14007ab76  mov     ebx, eax
0x14007ab78  call    HsmDbgBreakOnStatus
0x14007ab7d  test    ebx, ebx
0x14007ab7f  jns     short loc_14007ABC2
0x14007ab81  mov     r10, cs:WPP_GLOBAL_Control
0x14007ab88  lea     rax, WPP_GLOBAL_Control
0x14007ab8f  cmp     r10, rax
0x14007ab92  jz      loc_14007AF08
0x14007ab98  mov     ecx, [r10+2Ch]
0x14007ab9c  test    cl, 1
0x14007ab9f  jz      loc_14007AF08
0x14007aba5  cmp     byte ptr [r10+29h], 2
0x14007abaa  jb      loc_14007AF08
0x14007abb0  mov     rcx, [r10+18h]
0x14007abb4  mov     edx, 0ABh
0x14007abb9  mov     dword ptr [rsp+70h+var_38], ebx
0x14007abbd  jmp     loc_14007AEE1
0x14007abc2  test    [rbp+arg_18], 20000000h
0x14007abc9  mov     r15, [rbp+CallbackData]
0x14007abcd  jnz     loc_14007AC8A
0x14007abd3  mov     byte ptr [rbp+arg_48], r12b
0x14007abda  test    r15, r15
0x14007abdd  jz      short loc_14007ABF0
0x14007abdf  mov     rcx, r15; CallbackData
0x14007abe2  call    cs:__imp_FltGetRequestorProcess
0x14007abe9  nop     dword ptr [rax+rax+00h]
0x14007abee  jmp     short loc_14007ABF3
0x14007abf0  mov     rax, r12
0x14007abf3  mov     rdx, [rbp+arg_20]
0x14007abf7  lea     rcx, [rbp+arg_48]
0x14007abfe  mov     [rsp+70h+var_50], rcx
0x14007ac03  mov     r9, rax
0x14007ac06  mov     rcx, rsi
0x14007ac09  mov     r8, r13
0x14007ac0c  call    HsmpCldCheckSyncProviderAccess
0x14007ac11  mov     ecx, eax
0x14007ac13  mov     ebx, eax
0x14007ac15  call    HsmDbgBreakOnStatus
0x14007ac1a  test    ebx, ebx
0x14007ac1c  js      short loc_14007AC33
0x14007ac1e  cmp     byte ptr [rbp+arg_48], r12b
0x14007ac25  jnz     short loc_14007AC8A
0x14007ac27  mov     ebx, 0C000CF18h
0x14007ac2c  mov     ecx, ebx
0x14007ac2e  call    HsmDbgBreakOnStatus
0x14007ac33  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ac3a  lea     rax, WPP_GLOBAL_Control
0x14007ac41  cmp     rcx, rax
0x14007ac44  jz      loc_14007AF08
0x14007ac4a  mov     eax, [rcx+2Ch]
0x14007ac4d  test    al, 1
0x14007ac4f  jz      loc_14007AF08
0x14007ac55  cmp     byte ptr [rcx+29h], 2
0x14007ac59  jb      loc_14007AF08
0x14007ac5f  mov     rcx, [rcx+18h]
0x14007ac63  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x14007ac6a  mov     dword ptr [rsp+70h+var_40], ebx
0x14007ac6e  mov     edx, 0ACh
0x14007ac73  mov     [rsp+70h+var_48], r13
0x14007ac78  mov     r9, rsi
0x14007ac7b  mov     [rsp+70h+var_50], r15
0x14007ac80  call    WPP_SF_qqqd
0x14007ac85  jmp     loc_14007AF08
0x14007ac8a  test    dword ptr [rdi+8], 2000h
0x14007ac91  jz      short loc_14007AC9F
0x14007ac93  mov     rdx, [rbp+arg_28]
0x14007ac97  mov     rcx, rsi
0x14007ac9a  call    HsmpDeletePropertyStream
0x14007ac9f  mov     r12d, [rdi+8]
0x14007aca3  mov     r11, [rdi+10h]
0x14007aca7  mov     [rbp+arg_0], r11
0x14007acab  mov     [rbp+arg_48], r12d
0x14007acb2  bt      r12d, 11h
0x14007acb7  jb      short loc_14007AD10
0x14007acb9  lea     rbx, [rdi+18h]
0x14007acbd  lea     rcx, [rdi+38h]
0x14007acc1  bt      r12d, 10h
0x14007acc6  jb      short loc_14007AD02
0x14007acc8  xor     eax, eax
0x14007acca  cmp     [rbx], rax
0x14007accd  jnz     short loc_14007ACD1
0x14007accf  mov     ebx, eax
0x14007acd1  lea     r9, [rdi+20h]
0x14007acd5  cmp     [rcx], eax
0x14007acd7  jnz     short loc_14007ACDC
0x14007acd9  mov     rcx, rax
0x14007acdc  lea     rdx, [rdi+28h]
0x14007ace0  cmp     [r9], rax
0x14007ace3  jnz     short loc_14007ACE8
0x14007ace5  mov     r9, rax
0x14007ace8  lea     r8, [rdi+30h]
0x14007acec  cmp     [rdx], rax
0x14007acef  jnz     short loc_14007ACF4
0x14007acf1  mov     rdx, rax
0x14007acf4  mov     rax, [r8]
0x14007acf7  neg     rax
0x14007acfa  sbb     r10, r10
0x14007acfd  and     r10, r8
0x14007ad00  jmp     short loc_14007AD1C
0x14007ad02  lea     r9, [rdi+20h]
0x14007ad06  lea     rdx, [rdi+28h]
0x14007ad0a  lea     r10, [rdi+30h]
0x14007ad0e  jmp     short loc_14007AD1C
0x14007ad10  xor     r10d, r10d
0x14007ad13  xor     ebx, ebx
0x14007ad15  xor     r9d, r9d
0x14007ad18  xor     edx, edx
0x14007ad1a  xor     ecx, ecx
0x14007ad1c  mov     rax, [rbp+arg_20]
0x14007ad20  mov     eax, [rax+1Ch]
0x14007ad23  test    al, 2
0x14007ad25  jnz     loc_14007ADB5
0x14007ad2b  test    r11, r11
0x14007ad2e  jnz     short loc_14007AD3A
0x14007ad30  test    r14d, r14d
0x14007ad33  jnz     short loc_14007AD3A
0x14007ad35  xor     r13d, r13d
0x14007ad38  jmp     short loc_14007AD3E
0x14007ad3a  lea     r13, [rbp+arg_0]
0x14007ad3e  mov     r12d, [rdi+40h]
0x14007ad42  test    r12d, r12d
0x14007ad45  jz      short loc_14007AD50
0x14007ad47  mov     r8d, [rdi+3Ch]
0x14007ad4b  add     r8, rdi
0x14007ad4e  jmp     short loc_14007AD53
0x14007ad50  xor     r8d, r8d
0x14007ad53  mov     r11d, [rdi+48h]
0x14007ad57  test    r11d, r11d
0x14007ad5a  jz      short loc_14007AD64
0x14007ad5c  mov     eax, [rdi+44h]
0x14007ad5f  add     rax, rdi
0x14007ad62  jmp     short loc_14007AD66
0x14007ad64  xor     eax, eax
0x14007ad66  mov     [rsp+70h+var_8], r13
0x14007ad6b  mov     [rsp+70h+var_10], r10
0x14007ad70  mov     [rsp+70h+var_18], rdx
0x14007ad75  mov     rdx, [rbp+arg_20]
0x14007ad79  mov     [rsp+70h+var_20], r9
0x14007ad7e  mov     r9d, [rbp+arg_48]
0x14007ad85  mov     [rsp+70h+var_28], rcx
0x14007ad8a  mov     rcx, rsi
0x14007ad8d  mov     [rsp+70h+var_30], rbx
0x14007ad92  mov     dword ptr [rsp+70h+var_38], r12d
0x14007ad97  mov     [rsp+70h+var_40], r8
0x14007ad9c  mov     r8, [rbp+arg_10]
0x14007ada0  shr     r11d, 4
0x14007ada4  mov     dword ptr [rsp+70h+var_48], r11d
0x14007ada9  mov     [rsp+70h+var_50], rax
0x14007adae  call    HsmiOpUpdatePlaceholderFile
0x14007adb3  jmp     short loc_14007ADF8
0x14007adb5  mov     r8d, [rdi+40h]
0x14007adb9  test    r8d, r8d
0x14007adbc  jz      short loc_14007ADC6
0x14007adbe  mov     eax, [rdi+3Ch]
0x14007adc1  add     rax, rdi
0x14007adc4  jmp     short loc_14007ADC8
0x14007adc6  xor     eax, eax
0x14007adc8  mov     [rsp+70h+var_28], r10
0x14007adcd  mov     [rsp+70h+var_30], rdx
0x14007add2  mov     rdx, [rbp+arg_20]
0x14007add6  mov     [rsp+70h+var_38], r9
0x14007addb  mov     r9d, r12d
0x14007adde  mov     [rsp+70h+var_40], rcx
0x14007ade3  mov     rcx, rsi
0x14007ade6  mov     dword ptr [rsp+70h+var_48], r8d
0x14007adeb  mov     r8, r13
0x14007adee  mov     [rsp+70h+var_50], rax
0x14007adf3  call    HsmiOpUpdatePlaceholderDirectory
0x14007adf8  mov     ecx, eax
0x14007adfa  mov     ebx, eax
0x14007adfc  call    HsmDbgBreakOnStatus
0x14007ae01  test    ebx, ebx
0x14007ae03  jns     short loc_14007AE42
0x14007ae05  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ae0c  lea     rax, WPP_GLOBAL_Control
0x14007ae13  cmp     rcx, rax
0x14007ae16  jz      loc_14007AF08
0x14007ae1c  mov     eax, [rcx+2Ch]
0x14007ae1f  test    al, 1
0x14007ae21  jz      loc_14007AF08
0x14007ae27  cmp     byte ptr [rcx+29h], 2
0x14007ae2b  jb      loc_14007AF08
0x14007ae31  mov     edx, 0ADh
0x14007ae36  mov     dword ptr [rsp+70h+var_38], ebx
0x14007ae3a  mov     r9, r15
0x14007ae3d  jmp     loc_14007AB33
0x14007ae42  test    r14d, r14d
0x14007ae45  jz      short loc_14007AE4E
0x14007ae47  mov     rax, [rbp+arg_0]
  ... truncated ...
```
