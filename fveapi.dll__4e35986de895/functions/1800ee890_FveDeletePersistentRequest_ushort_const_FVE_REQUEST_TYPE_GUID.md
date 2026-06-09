# FveDeletePersistentRequest(ushort const *,_FVE_REQUEST_TYPE,_GUID)

- ea: `0x1800ee890`
- end: `0x1800eebbb`
- name: `?FveDeletePersistentRequest@@YAJPEBGW4_FVE_REQUEST_TYPE@@U_GUID@@@Z`
- size: `811`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct _GUID *)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1800ee66c`
- `0x1800f2b50`
- `0x1800f3328`

## callees

- `0x180004798`
- `0x180008d70`
- `0x1800090c0`
- `0x180045ff0`
- `0x1800485f0`
- `0x18004ad74`
- `0x1800edec4`
- `0x1800ee890`
- `0x1800ef0d0`
- `0x1800f0a00`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eea75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eea75`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800eea5e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800eea5e`

## string_xrefs

- `0x1800ee9cb`: `MakeSystemVolumeInformationPath`
- `0x1800eea6e`: `DeleteFileW`
- `0x1800eea17`: `BuildPersistentRequestFilePath`

## pseudocode

```c
__int64 __fastcall FveDeletePersistentRequest(const unsigned __int16 *a1, unsigned int a2, struct _GUID *a3)
{
  PVOID *v6; // rcx
  signed int v7; // ebx
  __int64 v8; // rdx
  unsigned int FolderName; // eax
  unsigned int v10; // r9d
  unsigned int SystemVolumeInformationPath; // eax
  unsigned int v12; // r9d
  unsigned int v13; // eax
  signed int LastError; // eax
  __int64 v15; // rcx
  struct _GUID v17; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[32]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v19[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v20[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR FileName[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(FileName, 0, 0x208u);
  memset_0(v20, 0, 0x208u);
  memset_0(v19, 0, 0x208u);
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    FolderName = FvePersistentRequest::GetFolderName(a2, v20);
    v7 = FolderName;
    if ( !FolderName )
      goto LABEL_27;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, FolderName);
    if ( v7 >= 0 )
    {
LABEL_27:
      SystemVolumeInformationPath = MakeSystemVolumeInformationPath(a1, v20, v19, v10);
      v7 = SystemVolumeInformationPath;
      if ( !SystemVolumeInformationPath )
        goto LABEL_40;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          157,
          &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
          SystemVolumeInformationPath);
      if ( v7 >= 0 )
      {
LABEL_40:
        v17 = *a3;
        v13 = FvePersistentRequest::BuildPersistentRequestFilePath(v19, &v17, FileName, v12);
        v7 = v13;
        if ( !v13 )
          goto LABEL_41;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v13);
        if ( v7 >= 0 )
        {
LABEL_41:
          if ( !DeleteFileW(FileName) )
          {
            LastError = GetLastError();
            v7 = LastError;
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
            v6 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              v8 = 159;
              goto LABEL_29;
            }
          }
        }
      }
    }
  }
  else
  {
    v7 = -2147024809;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 )
    {
      v8 = 155;
LABEL_29:
      WPP_SF_d(v6[2], v8, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, (unsigned int)v7);
    }
  }
  TelemetryProviderRegistrar::TelemetryProviderRegistrar(
    (TelemetryProviderRegistrar *)v18,
    &g_hBitLockerKeyRollProvider,
    &g_bitLockerKeyRollProviderInitLock,
    &g_bitLockerKeyRollProviderRefCount);
  if ( v7 < 0 && (unsigned int)dword_180172588 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180172588, 0x400000000000LL) )
  {
    *(_QWORD *)&v17.Data1 = v19;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v15,
      word_1801603AA);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      160,
      &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
      (unsigned int)v7);
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar((TelemetryProviderRegistrar *)v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800ee890  push    rbp
0x1800ee892  push    rbx
0x1800ee893  push    rsi
0x1800ee894  push    r12
0x1800ee896  push    r13
0x1800ee898  push    r14
0x1800ee89a  push    r15
0x1800ee89c  lea     rbp, [rsp-5E0h]
0x1800ee8a4  sub     rsp, 6E0h
0x1800ee8ab  mov     rax, cs:__security_cookie
0x1800ee8b2  xor     rax, rsp
0x1800ee8b5  mov     [rbp+610h+var_40], rax
0x1800ee8bc  mov     r15, r8
0x1800ee8bf  mov     r12d, edx
0x1800ee8c2  mov     r14, rcx
0x1800ee8c5  mov     ebx, 208h
0x1800ee8ca  mov     r8d, ebx; Size
0x1800ee8cd  lea     rcx, [rbp+610h+FileName]; void *
0x1800ee8d4  xor     edx, edx; Val
0x1800ee8d6  call    memset_0
0x1800ee8db  mov     r8d, ebx; Size
0x1800ee8de  lea     rcx, [rbp+610h+var_460]; void *
0x1800ee8e5  xor     edx, edx; Val
0x1800ee8e7  call    memset_0
0x1800ee8ec  mov     r8d, ebx; Size
0x1800ee8ef  lea     rcx, [rbp+610h+var_670]; void *
0x1800ee8f3  xor     edx, edx; Val
0x1800ee8f5  call    memset_0
0x1800ee8fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee901  lea     r13, WPP_GLOBAL_Control
0x1800ee908  cmp     rcx, r13
0x1800ee90b  jz      short loc_1800EE92F
0x1800ee90d  test    byte ptr [rcx+1Ch], 20h
0x1800ee911  jz      short loc_1800EE92F
0x1800ee913  mov     rcx, [rcx+10h]
0x1800ee917  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ee91e  mov     edx, 9Ah
0x1800ee923  call    WPP_SF_
0x1800ee928  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee92f  test    r14, r14
0x1800ee932  jnz     short loc_1800EE95D
0x1800ee934  lea     rsi, aInvalidarg; "INVALIDARG"
0x1800ee93b  mov     ebx, 80070057h
0x1800ee940  cmp     rcx, r13
0x1800ee943  jz      loc_1800EEABA
0x1800ee949  test    byte ptr [rcx+1Ch], 40h
0x1800ee94d  jz      loc_1800EEABA
0x1800ee953  mov     edx, 9Bh
0x1800ee958  jmp     loc_1800EEAA7
0x1800ee95d  lea     rdx, [rbp+610h+var_460]
0x1800ee964  mov     ecx, r12d
0x1800ee967  call    ?GetFolderName@FvePersistentRequest@@SAJW4_FVE_REQUEST_TYPE@@PEAGK@Z; FvePersistentRequest::GetFolderName(_FVE_REQUEST_TYPE,ushort *,ulong)
0x1800ee96c  mov     ebx, eax
0x1800ee96e  test    eax, eax
0x1800ee970  jz      short loc_1800EE9AB
0x1800ee972  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee979  lea     rsi, aGetfoldername; "GetFolderName"
0x1800ee980  cmp     rcx, r13
0x1800ee983  jz      short loc_1800EE9A3
0x1800ee985  test    byte ptr [rcx+1Ch], 40h
0x1800ee989  jz      short loc_1800EE9A3
0x1800ee98b  mov     rcx, [rcx+10h]
0x1800ee98f  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ee996  mov     edx, 9Ch
0x1800ee99b  mov     r9d, eax
0x1800ee99e  call    WPP_SF_d
0x1800ee9a3  test    ebx, ebx
0x1800ee9a5  js      loc_1800EEABA
0x1800ee9ab  lea     r8, [rbp+610h+var_670]; unsigned __int16 *
0x1800ee9af  mov     rcx, r14; unsigned __int16 *
0x1800ee9b2  lea     rdx, [rbp+610h+var_460]; unsigned __int16 *
0x1800ee9b9  call    ?MakeSystemVolumeInformationPath@@YAJPEBG0PEAGK@Z; MakeSystemVolumeInformationPath(ushort const *,ushort const *,ushort *,ulong)
0x1800ee9be  mov     ebx, eax
0x1800ee9c0  test    eax, eax
0x1800ee9c2  jz      short loc_1800EE9FD
0x1800ee9c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee9cb  lea     rsi, aMakesystemvolu; "MakeSystemVolumeInformationPath"
0x1800ee9d2  cmp     rcx, r13
0x1800ee9d5  jz      short loc_1800EE9F5
0x1800ee9d7  test    byte ptr [rcx+1Ch], 40h
0x1800ee9db  jz      short loc_1800EE9F5
0x1800ee9dd  mov     rcx, [rcx+10h]
0x1800ee9e1  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ee9e8  mov     edx, 9Dh
0x1800ee9ed  mov     r9d, eax
0x1800ee9f0  call    WPP_SF_d
0x1800ee9f5  test    ebx, ebx
0x1800ee9f7  js      loc_1800EEABA
0x1800ee9fd  movups  xmm0, xmmword ptr [r15]
0x1800eea01  lea     r8, [rbp+610h+FileName]; unsigned __int16 *
0x1800eea08  lea     rdx, [rsp+710h+var_6A0]; struct _GUID
0x1800eea0d  lea     rcx, [rbp+610h+var_670]; unsigned __int16 *
0x1800eea11  movdqu  xmmword ptr [rsp+710h+var_6A0.Data1], xmm0
0x1800eea17  lea     rsi, aBuildpersisten; "BuildPersistentRequestFilePath"
0x1800eea1e  call    ?BuildPersistentRequestFilePath@FvePersistentRequest@@SAJPEBGU_GUID@@PEAGK@Z; FvePersistentRequest::BuildPersistentRequestFilePath(ushort const *,_GUID,ushort *,ulong)
0x1800eea23  mov     ebx, eax
0x1800eea25  test    eax, eax
0x1800eea27  jz      short loc_1800EEA57
0x1800eea29  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eea30  cmp     rcx, r13
0x1800eea33  jz      short loc_1800EEA53
0x1800eea35  test    byte ptr [rcx+1Ch], 40h
0x1800eea39  jz      short loc_1800EEA53
0x1800eea3b  mov     rcx, [rcx+10h]
0x1800eea3f  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800eea46  mov     edx, 9Eh
0x1800eea4b  mov     r9d, eax
0x1800eea4e  call    WPP_SF_d
0x1800eea53  test    ebx, ebx
0x1800eea55  js      short loc_1800EEABA
0x1800eea57  lea     rcx, [rbp+610h+FileName]; lpFileName
0x1800eea5e  call    cs:__imp_DeleteFileW
0x1800eea65  nop     dword ptr [rax+rax+00h]
0x1800eea6a  test    eax, eax
0x1800eea6c  jnz     short loc_1800EEABA
0x1800eea6e  lea     rsi, aDeletefilew; "DeleteFileW"
0x1800eea75  call    cs:__imp_GetLastError
0x1800eea7c  nop     dword ptr [rax+rax+00h]
0x1800eea81  mov     ebx, eax
0x1800eea83  test    eax, eax
0x1800eea85  jle     short loc_1800EEA90
0x1800eea87  movzx   ebx, ax
0x1800eea8a  or      ebx, 80070000h
0x1800eea90  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eea97  cmp     rcx, r13
0x1800eea9a  jz      short loc_1800EEABA
0x1800eea9c  test    byte ptr [rcx+1Ch], 40h
0x1800eeaa0  jz      short loc_1800EEABA
0x1800eeaa2  mov     edx, 9Fh
0x1800eeaa7  mov     rcx, [rcx+10h]
0x1800eeaab  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800eeab2  mov     r9d, ebx
0x1800eeab5  call    WPP_SF_d
0x1800eeaba  lea     r9, ?g_bitLockerKeyRollProviderRefCount@@3JC; volatile int *
0x1800eeac1  lea     r8, ?g_bitLockerKeyRollProviderInitLock@@3U_RTL_SRWLOCK@@A; struct _RTL_SRWLOCK *
0x1800eeac8  lea     rdx, g_hBitLockerKeyRollProvider; struct _tlgProvider_t **
0x1800eeacf  lea     rcx, [rbp+610h+var_690]; this
0x1800eead3  call    ??0TelemetryProviderRegistrar@@QEAA@PEBQEBU_tlgProvider_t@@PEAU_RTL_SRWLOCK@@PECJ@Z; TelemetryProviderRegistrar::TelemetryProviderRegistrar(_tlgProvider_t const * const *,_RTL_SRWLOCK *,long volatile *)
0x1800eead8  test    ebx, ebx
0x1800eeada  jns     loc_1800EEB63
0x1800eeae0  mov     eax, cs:dword_180172588
0x1800eeae6  cmp     eax, 5
0x1800eeae9  jbe     short loc_1800EEB63
0x1800eeaeb  mov     rdx, 400000000000h
0x1800eeaf5  lea     rcx, dword_180172588
0x1800eeafc  call    _tlgKeywordOn
0x1800eeb01  test    al, al
0x1800eeb03  jz      short loc_1800EEB63
0x1800eeb05  lea     rax, [rbp+610h+var_670]
0x1800eeb09  mov     [rsp+710h+var_6B8], 1000000h
0x1800eeb12  mov     qword ptr [rsp+710h+var_6A0.Data1], rax
0x1800eeb17  lea     rdx, word_1801603AA
0x1800eeb1e  lea     rax, [rsp+710h+var_6B8]
0x1800eeb23  mov     [rsp+710h+var_6B0], rsi
0x1800eeb28  mov     [rsp+710h+var_6D0], rax
0x1800eeb2d  lea     rax, [rsp+710h+var_6B0]
0x1800eeb32  mov     [rsp+710h+var_6D8], rax
0x1800eeb37  lea     rax, [rsp+710h+var_6C0]
0x1800eeb3c  mov     [rsp+710h+var_6E0], rax
0x1800eeb41  lea     rax, [rsp+710h+var_6A0]
0x1800eeb46  mov     [rsp+710h+var_6E8], rax
0x1800eeb4b  lea     rax, [rsp+710h+var_6BC]
0x1800eeb50  mov     [rsp+710h+var_6F0], rax
0x1800eeb55  mov     [rsp+710h+var_6C0], r12d
0x1800eeb5a  mov     [rsp+710h+var_6BC], ebx
0x1800eeb5e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@34AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800eeb63  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eeb6a  cmp     rcx, r13
0x1800eeb6d  jz      short loc_1800EEB8D
0x1800eeb6f  test    byte ptr [rcx+1Ch], 20h
0x1800eeb73  jz      short loc_1800EEB8D
0x1800eeb75  mov     rcx, [rcx+10h]
0x1800eeb79  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800eeb80  mov     edx, 0A0h
0x1800eeb85  mov     r9d, ebx
0x1800eeb88  call    WPP_SF_d
0x1800eeb8d  lea     rcx, [rbp+610h+var_690]; this
0x1800eeb91  call    ??1TelemetryProviderRegistrar@@QEAA@XZ; TelemetryProviderRegistrar::~TelemetryProviderRegistrar(void)
0x1800eeb96  mov     eax, ebx
0x1800eeb98  mov     rcx, [rbp+610h+var_40]
0x1800eeb9f  xor     rcx, rsp; StackCookie
0x1800eeba2  call    __security_check_cookie
0x1800eeba7  add     rsp, 6E0h
0x1800eebae  pop     r15
0x1800eebb0  pop     r14
0x1800eebb2  pop     r13
0x1800eebb4  pop     r12
0x1800eebb6  pop     rsi
0x1800eebb7  pop     rbx
0x1800eebb8  pop     rbp
0x1800eebb9  retn
```
