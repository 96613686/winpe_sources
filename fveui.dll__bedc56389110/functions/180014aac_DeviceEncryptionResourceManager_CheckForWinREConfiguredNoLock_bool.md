# DeviceEncryptionResourceManager::CheckForWinREConfiguredNoLock(bool *)

- ea: `0x180014aac`
- end: `0x180014da9`
- name: `?CheckForWinREConfiguredNoLock@DeviceEncryptionResourceManager@@IEAAJPEA_N@Z`
- size: `765`
- prototype: `__int64 __fastcall(DeviceEncryptionResourceManager *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180014564`

## callees

- `0x180001bb0`
- `0x1800037a0`
- `0x18000e354`
- `0x1800102b0`
- `0x180010414`
- `0x1800105f8`
- `0x1800113f4`
- `0x1800116f4`
- `0x180014aac`
- `0x1800297d4`
- `0x18002bb5c`
- `0x18002bc10`

## string_xrefs

- `0x180014ba0`: `ReportDEWinREConfigured`

## pseudocode

```c
__int64 __fastcall DeviceEncryptionResourceManager::CheckForWinREConfiguredNoLock(
        DeviceEncryptionResourceManager *this,
        bool *a2)
{
  int v4; // ebx
  _DWORD *v5; // rdi
  unsigned int DeviceType; // eax
  PVOID *v7; // rcx
  bool *v8; // rdi
  unsigned int v9; // r8d
  unsigned int WinReConfiguration; // eax
  unsigned int v11; // r8d
  PVOID *v12; // rcx
  __int64 v13; // rdx
  unsigned int FveVolumePath; // eax
  unsigned int v15; // eax
  bool v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  _QWORD v19[2]; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v20[2]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v21[3]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v22[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v23[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v24[304]; // [rsp+280h] [rbp+180h] BYREF

  v22[0] = &CFvePolicy::`vftable';
  v22[1] = 0;
  v17 = 0;
  v18 = 0;
  v4 = 0;
  if ( *((_BYTE *)this + 117) )
  {
    v8 = (bool *)this + 116;
LABEL_51:
    *((_BYTE *)this + 117) = 1;
    *a2 = *v8;
    if ( !*v8 )
    {
      v19[0] = 0;
      memset(v21, 0, sizeof(v21));
      v20[1] = v20;
      v20[0] = v20;
      v19[1] = FVE_DE_WINRE_INVALID_CONFIGURATION;
      FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)v21, (struct _FVEAPI_EVENT_DATA_COLLECTION *)v19);
      FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)v21);
    }
    goto LABEL_53;
  }
  v5 = (_DWORD *)((char *)this + 112);
  if ( *((_DWORD *)this + 28)
    || (DeviceType = NgscbGetDeviceType((DeviceEncryptionResourceManager *)((char *)this + 112)), (v4 = DeviceType) == 0) )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, DeviceType);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 < 0 )
      goto LABEL_53;
  }
  if ( *v5 != 1 )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
      WPP_SF_(v7[2], 66, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids);
    v8 = (bool *)this + 116;
LABEL_47:
    *v8 = 1;
    goto LABEL_48;
  }
  v8 = (bool *)this + 116;
  if ( NgscbGet_TEST_BooleanOverride(L"ReportDEWinREConfigured", (bool *)this + 116) )
    goto LABEL_48;
  WinReConfiguration = NgscbGetWinReConfiguration(&v17, v24, v9);
  v4 = WinReConfiguration;
  if ( WinReConfiguration )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids,
        WinReConfiguration);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 < 0 )
      goto LABEL_53;
  }
  else
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v17 )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
    {
      v13 = 68;
LABEL_27:
      WPP_SF_(v12[2], v13, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  FveVolumePath = CFveDriveType::GetFveVolumePath(v24, v23, v11);
  v4 = FveVolumePath;
  if ( !FveVolumePath )
    goto LABEL_33;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, FveVolumePath);
  if ( v4 >= 0 )
  {
LABEL_33:
    v15 = CFveDriveType::CheckIsOSDrive(v23, &v18);
    v4 = v15;
    if ( !v15 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_40;
    }
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v15);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 >= 0 )
    {
LABEL_40:
      if ( !v18 )
      {
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
          WPP_SF_(v12[2], 72, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids);
        goto LABEL_47;
      }
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
      {
        v13 = 71;
        goto LABEL_27;
      }
LABEL_48:
      if ( v4 < 0 )
        goto LABEL_53;
      goto LABEL_51;
    }
  }
LABEL_53:
  CFvePolicy::~CFvePolicy((CFvePolicy *)v22);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014aac  mov     [rsp-8+arg_10], rbx
0x180014ab1  push    rbp
0x180014ab2  push    rsi
0x180014ab3  push    rdi
0x180014ab4  push    r12
0x180014ab6  push    r13
0x180014ab8  push    r14
0x180014aba  push    r15
0x180014abc  lea     rbp, [rsp-3F0h]
0x180014ac4  sub     rsp, 4F0h
0x180014acb  mov     rax, cs:__security_cookie
0x180014ad2  xor     rax, rsp
0x180014ad5  mov     [rbp+420h+var_40], rax
0x180014adc  mov     r14, rdx
0x180014adf  mov     rsi, rcx
0x180014ae2  lea     rax, ??_7CFvePolicy@@6B@; const CFvePolicy::`vftable'
0x180014ae9  mov     [rsp+520h+var_4C0], rax
0x180014aee  xor     r15d, r15d
0x180014af1  mov     [rsp+520h+var_4B8], r15
0x180014af6  mov     [rsp+520h+var_500], r15b
0x180014afb  mov     [rsp+520h+var_4FC], r15d
0x180014b00  mov     ebx, r15d
0x180014b03  cmp     [rcx+75h], r15b
0x180014b07  jnz     loc_180014D12
0x180014b0d  lea     rdi, [rcx+70h]
0x180014b11  lea     r12, WPP_GLOBAL_Control
0x180014b18  lea     r13, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x180014b1f  cmp     [rdi], r15d
0x180014b22  jnz     short loc_180014B68
0x180014b24  mov     rcx, rdi; enum NgscbDeviceType *
0x180014b27  call    ?NgscbGetDeviceType@@YAJPEAW4NgscbDeviceType@@@Z; NgscbGetDeviceType(NgscbDeviceType *)
0x180014b2c  mov     ebx, eax
0x180014b2e  test    eax, eax
0x180014b30  jz      short loc_180014B68
0x180014b32  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b39  cmp     rcx, r12
0x180014b3c  jz      short loc_180014B5E
0x180014b3e  test    byte ptr [rcx+1Ch], 40h
0x180014b42  jz      short loc_180014B5E
0x180014b44  lea     edx, [r15+41h]
0x180014b48  mov     r9d, eax
0x180014b4b  mov     r8, r13
0x180014b4e  mov     rcx, [rcx+10h]
0x180014b52  call    WPP_SF_d
0x180014b57  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b5e  test    ebx, ebx
0x180014b60  js      loc_180014D73
0x180014b66  jmp     short loc_180014B6F
0x180014b68  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b6f  cmp     dword ptr [rdi], 1
0x180014b72  jz      short loc_180014B99
0x180014b74  cmp     rcx, r12
0x180014b77  jz      short loc_180014B90
0x180014b79  test    byte ptr [rcx+1Ch], 8
0x180014b7d  jz      short loc_180014B90
0x180014b7f  mov     edx, 42h ; 'B'
0x180014b84  mov     r8, r13
0x180014b87  mov     rcx, [rcx+10h]
0x180014b8b  call    WPP_SF_
0x180014b90  lea     rdi, [rsi+74h]
0x180014b94  jmp     loc_180014D09
0x180014b99  lea     rdi, [rsi+74h]
0x180014b9d  mov     rdx, rdi; bool *
0x180014ba0  lea     rcx, aReportdewinrec; "ReportDEWinREConfigured"
0x180014ba7  call    ?NgscbGet_TEST_BooleanOverride@@YA_NPEBGPEA_N@Z; NgscbGet_TEST_BooleanOverride(ushort const *,bool *)
0x180014bac  test    al, al
0x180014bae  jnz     loc_180014D0C
0x180014bb4  lea     rdx, [rbp+420h+var_2A0]; unsigned __int16 *
0x180014bbb  lea     rcx, [rsp+520h+var_500]; bool *
0x180014bc0  call    ?NgscbGetWinReConfiguration@@YAJPEA_NPEAGK@Z; NgscbGetWinReConfiguration(bool *,ushort *,ulong)
0x180014bc5  mov     ebx, eax
0x180014bc7  test    eax, eax
0x180014bc9  jz      short loc_180014C02
0x180014bcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bd2  cmp     rcx, r12
0x180014bd5  jz      short loc_180014BF8
0x180014bd7  test    byte ptr [rcx+1Ch], 40h
0x180014bdb  jz      short loc_180014BF8
0x180014bdd  mov     edx, 43h ; 'C'
0x180014be2  mov     r9d, eax
0x180014be5  mov     r8, r13
0x180014be8  mov     rcx, [rcx+10h]
0x180014bec  call    WPP_SF_d
0x180014bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bf8  test    ebx, ebx
0x180014bfa  js      loc_180014D73
0x180014c00  jmp     short loc_180014C09
0x180014c02  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c09  cmp     [rsp+520h+var_500], r15b
0x180014c0e  jnz     short loc_180014C39
0x180014c10  cmp     rcx, r12
0x180014c13  jz      loc_180014D0C
0x180014c19  test    byte ptr [rcx+1Ch], 2
0x180014c1d  jz      loc_180014D0C
0x180014c23  mov     edx, 44h ; 'D'
0x180014c28  mov     r8, r13
0x180014c2b  mov     rcx, [rcx+10h]
0x180014c2f  call    WPP_SF_
0x180014c34  jmp     loc_180014D0C
0x180014c39  lea     rdx, [rsp+520h+var_4B0]; unsigned __int16 *
0x180014c3e  lea     rcx, [rbp+420h+var_2A0]; unsigned __int16 *
0x180014c45  call    ?GetFveVolumePath@CFveDriveType@@SAJPEBGPEAGK@Z; CFveDriveType::GetFveVolumePath(ushort const *,ushort *,ulong)
0x180014c4a  mov     ebx, eax
0x180014c4c  test    eax, eax
0x180014c4e  jz      short loc_180014C7E
0x180014c50  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c57  cmp     rcx, r12
0x180014c5a  jz      short loc_180014C76
0x180014c5c  test    byte ptr [rcx+1Ch], 40h
0x180014c60  jz      short loc_180014C76
0x180014c62  mov     edx, 45h ; 'E'
0x180014c67  mov     r9d, eax
0x180014c6a  mov     r8, r13
0x180014c6d  mov     rcx, [rcx+10h]
0x180014c71  call    WPP_SF_d
0x180014c76  test    ebx, ebx
0x180014c78  js      loc_180014D73
0x180014c7e  lea     rdx, [rsp+520h+var_4FC]; int *
0x180014c83  lea     rcx, [rsp+520h+var_4B0]; unsigned __int16 *
0x180014c88  call    ?CheckIsOSDrive@CFveDriveType@@SAJPEBGPEAH@Z; CFveDriveType::CheckIsOSDrive(ushort const *,int *)
0x180014c8d  mov     ebx, eax
0x180014c8f  test    eax, eax
0x180014c91  jz      short loc_180014CCA
0x180014c93  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c9a  cmp     rcx, r12
0x180014c9d  jz      short loc_180014CC0
0x180014c9f  test    byte ptr [rcx+1Ch], 40h
0x180014ca3  jz      short loc_180014CC0
0x180014ca5  mov     edx, 46h ; 'F'
0x180014caa  mov     r9d, eax
0x180014cad  mov     r8, r13
0x180014cb0  mov     rcx, [rcx+10h]
0x180014cb4  call    WPP_SF_d
0x180014cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180014cc0  test    ebx, ebx
0x180014cc2  js      loc_180014D73
0x180014cc8  jmp     short loc_180014CD1
0x180014cca  mov     rcx, cs:WPP_GLOBAL_Control
0x180014cd1  cmp     [rsp+520h+var_4FC], r15d
0x180014cd6  jz      short loc_180014CED
0x180014cd8  cmp     rcx, r12
0x180014cdb  jz      short loc_180014D0C
0x180014cdd  test    byte ptr [rcx+1Ch], 2
0x180014ce1  jz      short loc_180014D0C
0x180014ce3  mov     edx, 47h ; 'G'
0x180014ce8  jmp     loc_180014C28
0x180014ced  cmp     rcx, r12
0x180014cf0  jz      short loc_180014D09
0x180014cf2  test    byte ptr [rcx+1Ch], 8
0x180014cf6  jz      short loc_180014D09
0x180014cf8  mov     edx, 48h ; 'H'
0x180014cfd  mov     r8, r13
0x180014d00  mov     rcx, [rcx+10h]
0x180014d04  call    WPP_SF_
0x180014d09  mov     byte ptr [rdi], 1
0x180014d0c  test    ebx, ebx
0x180014d0e  js      short loc_180014D73
0x180014d10  jmp     short loc_180014D16
0x180014d12  lea     rdi, [rcx+74h]
0x180014d16  mov     byte ptr [rsi+75h], 1
0x180014d1a  mov     al, [rdi]
0x180014d1c  mov     [r14], al
0x180014d1f  cmp     [rdi], r15b
0x180014d22  jnz     short loc_180014D73
0x180014d24  mov     [rsp+520h+var_4F8], r15
0x180014d29  mov     [rsp+520h+var_4D8], r15
0x180014d2e  mov     [rsp+520h+var_4D0], r15
0x180014d33  mov     [rsp+520h+var_4C8], r15
0x180014d38  lea     rax, [rsp+520h+var_4E8]
0x180014d3d  mov     [rsp+520h+var_4E0], rax
0x180014d42  lea     rax, [rsp+520h+var_4E8]
0x180014d47  mov     [rsp+520h+var_4E8], rax
0x180014d4c  lea     rax, FVE_DE_WINRE_INVALID_CONFIGURATION
0x180014d53  mov     [rsp+520h+var_4F0], rax
0x180014d58  lea     rdx, [rsp+520h+var_4F8]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x180014d5d  lea     rcx, [rsp+520h+var_4D8]; this
0x180014d62  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x180014d67  nop
0x180014d68  lea     rcx, [rsp+520h+var_4D8]; this
0x180014d6d  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x180014d72  nop
0x180014d73  lea     rcx, [rsp+520h+var_4C0]; this
0x180014d78  call    ??1CFvePolicy@@QEAA@XZ; CFvePolicy::~CFvePolicy(void)
0x180014d7d  mov     eax, ebx
0x180014d7f  mov     rcx, [rbp+420h+var_40]
0x180014d86  xor     rcx, rsp; StackCookie
0x180014d89  call    __security_check_cookie
0x180014d8e  mov     rbx, [rsp+520h+arg_10]
0x180014d96  add     rsp, 4F0h
0x180014d9d  pop     r15
0x180014d9f  pop     r14
0x180014da1  pop     r13
0x180014da3  pop     r12
0x180014da5  pop     rdi
0x180014da6  pop     rsi
0x180014da7  pop     rbp
0x180014da8  retn
```
