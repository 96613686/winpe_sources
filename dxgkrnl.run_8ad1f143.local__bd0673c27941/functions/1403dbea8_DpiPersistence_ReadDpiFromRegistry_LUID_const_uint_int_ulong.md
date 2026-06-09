# DpiPersistence::ReadDpiFromRegistry(_LUID const &,uint,int,ulong *)

- ea: `0x1403dbea8`
- end: `0x1403dc3eb`
- name: `?ReadDpiFromRegistry@DpiPersistence@@YAJAEBU_LUID@@IHPEAK@Z`
- size: `1347`
- prototype: `__int64 __fastcall(DpiPersistence *__hidden this, const struct _LUID *, unsigned int, int, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1401dedb0`
- `0x1402307a0`

## callees

- `0x14000d7d0`
- `0x140012380`
- `0x14001b890`
- `0x140323280`
- `0x1403dbb9c`
- `0x1403dbea8`
- `0x1403dc3f4`
- `0x1403dc418`
- `0x140403b40`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403dbf27`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403dbf58`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403dbf27`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403dbf58`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1403dc2cf`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1403dc2cf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403dc050`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403dc068`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403dc366`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403dc37e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403dc050`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403dc068`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403dc366`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403dc37e`
- `ntoskrnl!ZwOpenKey` at `0x1403dc0a9`
- `ntoskrnl!ZwOpenKey` at `0x1403dc0a9`
- `watchdog!WdLogSingleEntry2` at `0x1403dbf42`
- `watchdog!WdLogSingleEntry2` at `0x1403dbf42`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1403dbfad`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1403dc02e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1403dbfad`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1403dc02e`
- `watchdog!WdLogSingleEntry0` at `0x1403dbfe8`
- `watchdog!WdLogSingleEntry0` at `0x1403dc0f4`
- `watchdog!WdLogSingleEntry0` at `0x1403dc190`
- `watchdog!WdLogSingleEntry0` at `0x1403dc229`
- `watchdog!WdLogSingleEntry0` at `0x1403dbfe8`
- `watchdog!WdLogSingleEntry0` at `0x1403dc0f4`
- `watchdog!WdLogSingleEntry0` at `0x1403dc190`
- `watchdog!WdLogSingleEntry0` at `0x1403dc229`
- `watchdog!WdLogSingleEntry1` at `0x1403dc0c4`
- `watchdog!WdLogSingleEntry1` at `0x1403dc169`
- `watchdog!WdLogSingleEntry1` at `0x1403dc202`
- `watchdog!WdLogSingleEntry1` at `0x1403dc2ea`
- `watchdog!WdLogSingleEntry1` at `0x1403dc0c4`
- `watchdog!WdLogSingleEntry1` at `0x1403dc169`
- `watchdog!WdLogSingleEntry1` at `0x1403dc202`
- `watchdog!WdLogSingleEntry1` at `0x1403dc2ea`

## string_xrefs

- `0x1403dc0d0`: `Unable to open HKey root handle (Status = 0x%I64x)`
- `0x1403dc03a`: `\Registry\Machine\System`
- `0x1403dc35a`: `\Registry\Machine\System`
- `0x1403dbff9`: `pDxgSessionData->GetUserRegistryPath()->Length == 0`
- `0x1403dc2f6`: `Unable to read registry values. (Status = 0x%I64x, SubKeyHandle2 = 0x%I64x, QueryTable = 0x%I64x)`

## pseudocode

```c
__int64 __fastcall DpiPersistence::ReadDpiFromRegistry(
        struct _LUID *this,
        const struct _LUID *a2,
        int a3,
        struct _UNICODE_STRING *a4)
{
  struct _UNICODE_STRING *v5; // rsi
  __int64 v7; // rdi
  DXGGLOBAL *Global; // rax
  struct DXGSESSIONDATA *SessionData; // rax
  unsigned int CurrentProcessSessionId; // eax
  unsigned int v11; // eax
  const WCHAR *v12; // rdx
  NTSTATUS v13; // eax
  const wchar_t *v14; // r9
  void *v15; // r8
  void *v16; // r8
  void *v17; // rdx
  int v18; // eax
  const struct _UNICODE_STRING *v19; // r9
  unsigned int *v21; // [rsp+20h] [rbp-E0h]
  unsigned int v22; // [rsp+28h] [rbp-D8h]
  void *v23; // [rsp+50h] [rbp-B0h] BYREF
  void *v24; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING v25; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v27; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  __int64 v29; // [rsp+C0h] [rbp-40h] BYREF
  int v30; // [rsp+C8h] [rbp-38h]
  const WCHAR *v31; // [rsp+D0h] [rbp-30h]
  struct _UNICODE_STRING *v32; // [rsp+D8h] [rbp-28h]
  int v33; // [rsp+E0h] [rbp-20h]
  int *v34; // [rsp+E8h] [rbp-18h]
  int v35; // [rsp+F0h] [rbp-10h]
  __int64 v36; // [rsp+F8h] [rbp-8h]
  int v37; // [rsp+100h] [rbp+0h]
  __int64 v38; // [rsp+108h] [rbp+8h]
  __int128 v39; // [rsp+110h] [rbp+10h]
  __int128 v40; // [rsp+120h] [rbp+20h]
  int v41; // [rsp+180h] [rbp+80h] BYREF
  void *KeyHandle; // [rsp+188h] [rbp+88h] BYREF

  v41 = 0;
  *(_DWORD *)&a4->Length = 0;
  KeyHandle = 0;
  v27 = 0;
  v23 = 0;
  v5 = 0;
  v24 = 0;
  DestinationString = 0;
  v25 = 0;
  LODWORD(v7) = DpiPersistence::AllocateMonitorSetIdFromAdapterSource(this, a2, (unsigned int)&v27, a4);
  if ( (int)v7 >= 0 )
  {
    Global = DXGGLOBAL::GetGlobal();
    SessionData = DXGGLOBAL::GetSessionData(Global);
    v5 = (struct _UNICODE_STRING *)SessionData;
    if ( !SessionData )
    {
      CurrentProcessSessionId = PsGetCurrentProcessSessionId();
      LODWORD(v7) = -1073741811;
      WdLogSingleEntry2(2, CurrentProcessSessionId);
      WdLogGlobalForLineNumber = 828;
      v11 = PsGetCurrentProcessSessionId();
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Current session does not have session data in session 0x%I64x, returning 0x%I64x.",
        v11,
        -1073741811,
        0,
        0,
        0);
      goto LABEL_26;
    }
    if ( *((_QWORD *)SessionData + 2343) )
    {
      WdLogNewEntry5_WdTrace();
      WdLogGlobalForLineNumber = 860;
      v12 = L"Control Panel\\Desktop\\PerMonitorSettings\\";
      DestinationString = v5[1171];
    }
    else
    {
      if ( *((_WORD *)SessionData + 9368) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 851;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"pDxgSessionData->GetUserRegistryPath()->Length == 0",
          851,
          0,
          0,
          0,
          0);
      }
      WdLogNewEntry5_WdTrace();
      WdLogGlobalForLineNumber = 852;
      RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System");
      v12 = L"CurrentControlSet\\Control\\GraphicsDrivers\\ScaleFactors";
    }
    RtlInitUnicodeString(&v25, v12);
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    ObjectAttributes.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v13 = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
    v7 = v13;
    if ( v13 >= 0 )
    {
      v15 = KeyHandle;
      if ( !KeyHandle )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 880;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"HKeyRootHandle", 880, 0, 0, 0, 0);
        v15 = KeyHandle;
      }
      LODWORD(v7) = OpenRegistrySubkey(&v23, 0xF003Fu, v15, &v25, 0);
      if ( (int)v7 < 0 )
      {
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 892;
        goto LABEL_24;
      }
      v16 = v23;
      if ( !v23 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 896;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"PerMonSettingsKeyHandle", 896, 0, 0, 0, 0);
        v16 = v23;
      }
      LODWORD(v7) = OpenRegistrySubkey(&v24, 0xF003Fu, v16, &v27, 0);
      if ( (int)v7 < 0 )
      {
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 909;
        goto LABEL_24;
      }
      v17 = v24;
      if ( !v24 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 912;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"MonitorIdKeyHandle", 912, 0, 0, 0, 0);
        v17 = v24;
      }
      v29 = 0;
      v30 = 288;
      v31 = L"DpiValue";
      v32 = a4;
      v34 = &v41;
      v33 = 67108868;
      v35 = 4;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      v39 = 0;
      v40 = 0;
      v18 = RtlQueryRegistryValuesEx(0x40000000, v17, &v29, 0, 0);
      v7 = v18;
      if ( v18 >= 0 )
        goto LABEL_24;
      WdLogSingleEntry1(2);
      v14 = L"Unable to read registry values. (Status = 0x%I64x, SubKeyHandle2 = 0x%I64x, QueryTable = 0x%I64x)";
      WdLogGlobalForLineNumber = 934;
    }
    else
    {
      WdLogSingleEntry1(2);
      v14 = L"Unable to open HKey root handle (Status = 0x%I64x)";
      WdLogGlobalForLineNumber = 877;
    }
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v14, v7, 0, 0, 0, 0);
  }
LABEL_24:
  if ( (_DWORD)v7 == -1073741772 )
  {
    LODWORD(v7) = 0;
    *(_DWORD *)&a4->Length = v41;
  }
LABEL_26:
  if ( a3 && (int)v7 >= 0 && v5 && v5[1171].Buffer )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System");
    RtlInitUnicodeString(&v25, L"CurrentControlSet\\Control\\GraphicsDrivers\\ScaleFactors");
    LODWORD(v21) = *(_DWORD *)&a4->Length;
    DpiPersistence::WriteDwordToParticularRegValue(
      (DpiPersistence *)&DestinationString,
      &v25,
      &v27,
      v19,
      (const unsigned __int16 *const)v21,
      v22);
  }
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v27.Buffer);
  CloseRegistrySubkey(KeyHandle);
  CloseRegistrySubkey(v23);
  CloseRegistrySubkey(v24);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1403dbea8  mov     [rsp-8+arg_0], rbx
0x1403dbead  push    rbp
0x1403dbeae  push    rsi
0x1403dbeaf  push    rdi
0x1403dbeb0  push    r12
0x1403dbeb2  push    r13
0x1403dbeb4  push    r14
0x1403dbeb6  push    r15
0x1403dbeb8  lea     rbp, [rsp-30h]
0x1403dbebd  sub     rsp, 130h
0x1403dbec4  xor     r13d, r13d
0x1403dbec7  xorps   xmm0, xmm0
0x1403dbeca  mov     r12d, r8d
0x1403dbecd  mov     [rbp+60h+arg_10], r13d
0x1403dbed4  xorps   xmm1, xmm1
0x1403dbed7  mov     [r9], r13d
0x1403dbeda  lea     r8, [rbp+60h+var_E0]; unsigned int
0x1403dbede  mov     [rbp+60h+KeyHandle], r13
0x1403dbee5  movups  xmmword ptr [rbp+60h+var_E0.Length], xmm0
0x1403dbee9  mov     [rsp+160h+var_110], r13
0x1403dbeee  mov     esi, r13d
0x1403dbef1  mov     [rsp+160h+var_108], r13
0x1403dbef6  mov     r15, r9
0x1403dbef9  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x1403dbefe  movups  xmmword ptr [rsp+160h+var_100.Length], xmm1
0x1403dbf03  call    ?AllocateMonitorSetIdFromAdapterSource@DpiPersistence@@YAJAEBU_LUID@@IPEAU_UNICODE_STRING@@@Z; DpiPersistence::AllocateMonitorSetIdFromAdapterSource(_LUID const &,uint,_UNICODE_STRING *)
0x1403dbf08  mov     edi, eax
0x1403dbf0a  test    eax, eax
0x1403dbf0c  js      loc_1403DC32F
0x1403dbf12  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1403dbf17  mov     rcx, rax; this
0x1403dbf1a  call    ?GetSessionData@DXGGLOBAL@@QEAAPEAVDXGSESSIONDATA@@XZ; DXGGLOBAL::GetSessionData(void)
0x1403dbf1f  mov     rsi, rax
0x1403dbf22  test    rax, rax
0x1403dbf25  jnz     short loc_1403DBF9B
0x1403dbf27  call    cs:__imp_PsGetCurrentProcessSessionId
0x1403dbf2e  nop     dword ptr [rax+rax+00h]
0x1403dbf33  mov     rdi, 0FFFFFFFFC000000Dh
0x1403dbf3a  mov     edx, eax
0x1403dbf3c  mov     r8, rdi
0x1403dbf3f  lea     ecx, [rsi+2]
0x1403dbf42  call    cs:__imp_WdLogSingleEntry2
0x1403dbf49  nop     dword ptr [rax+rax+00h]
0x1403dbf4e  mov     cs:WdLogGlobalForLineNumber, 33Ch
0x1403dbf58  call    cs:__imp_PsGetCurrentProcessSessionId
0x1403dbf5f  nop     dword ptr [rax+rax+00h]
0x1403dbf64  mov     [rsp+160h+var_120], r13
0x1403dbf69  lea     r9, aCurrentSession_0; "Current session does not have session d"...
0x1403dbf70  mov     [rsp+160h+var_128], r13
0x1403dbf75  or      r8d, 0FFFFFFFFh
0x1403dbf79  mov     ecx, eax
0x1403dbf7b  mov     edx, 40000h
0x1403dbf80  mov     [rsp+160h+var_130], r13
0x1403dbf85  mov     qword ptr [rsp+160h+var_138], rdi
0x1403dbf8a  mov     [rsp+160h+var_140], rcx
0x1403dbf8f  xor     ecx, ecx
0x1403dbf91  call    DxgkLogInternalTriageEvent
0x1403dbf96  jmp     loc_1403DC343
0x1403dbf9b  or      r14d, 0FFFFFFFFh
0x1403dbf9f  mov     ebx, 1
0x1403dbfa4  cmp     [rax+4938h], r13
0x1403dbfab  jz      short loc_1403DBFDC
0x1403dbfad  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1403dbfb4  nop     dword ptr [rax+rax+00h]
0x1403dbfb9  mov     cs:WdLogGlobalForLineNumber, 35Ch
0x1403dbfc3  lea     rdx, aControlPanelDe; "Control Panel\\Desktop\\PerMonitorSetti"...
0x1403dbfca  movups  xmm0, xmmword ptr [rsi+4930h]
0x1403dbfd1  movdqu  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x1403dbfd7  jmp     loc_1403DC063
0x1403dbfdc  cmp     [rax+4930h], r13w
0x1403dbfe4  jz      short loc_1403DC02E
0x1403dbfe6  mov     ecx, ebx
0x1403dbfe8  call    cs:__imp_WdLogSingleEntry0
0x1403dbfef  nop     dword ptr [rax+rax+00h]
0x1403dbff4  mov     [rsp+160h+var_120], r13
0x1403dbff9  lea     r9, aPdxgsessiondat; "pDxgSessionData->GetUserRegistryPath()-"...
0x1403dc000  mov     [rsp+160h+var_128], r13
0x1403dc005  mov     eax, 353h
0x1403dc00a  mov     [rsp+160h+var_130], r13
0x1403dc00f  mov     r8d, r14d
0x1403dc012  mov     qword ptr [rsp+160h+var_138], r13
0x1403dc017  mov     edx, 40002h
0x1403dc01c  xor     ecx, ecx
0x1403dc01e  mov     [rsp+160h+var_140], rax
0x1403dc023  mov     cs:WdLogGlobalForLineNumber, eax
0x1403dc029  call    DxgkLogInternalTriageEvent
0x1403dc02e  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1403dc035  nop     dword ptr [rax+rax+00h]
0x1403dc03a  lea     rdx, aRegistryMachin_25; "\\Registry\\Machine\\System"
0x1403dc041  mov     cs:WdLogGlobalForLineNumber, 354h
0x1403dc04b  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x1403dc050  call    cs:__imp_RtlInitUnicodeString
0x1403dc057  nop     dword ptr [rax+rax+00h]
0x1403dc05c  lea     rdx, aCurrentcontrol; "CurrentControlSet\\Control\\GraphicsDri"...
0x1403dc063  lea     rcx, [rsp+160h+var_100]; DestinationString
0x1403dc068  call    cs:__imp_RtlInitUnicodeString
0x1403dc06f  nop     dword ptr [rax+rax+00h]
0x1403dc074  lea     rax, [rsp+160h+DestinationString]
0x1403dc079  mov     qword ptr [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x1403dc081  xorps   xmm0, xmm0
0x1403dc084  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x1403dc088  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x1403dc08c  mov     qword ptr [rbp+60h+ObjectAttributes.Attributes], 240h
0x1403dc094  mov     edx, 0F003Fh; DesiredAccess
0x1403dc099  mov     [rbp+60h+ObjectAttributes.RootDirectory], r13
0x1403dc09d  lea     rcx, [rbp+60h+KeyHandle]; KeyHandle
0x1403dc0a4  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1403dc0a9  call    cs:__imp_ZwOpenKey
0x1403dc0b0  nop     dword ptr [rax+rax+00h]
0x1403dc0b5  movsxd  rdi, eax
0x1403dc0b8  test    eax, eax
0x1403dc0ba  jns     short loc_1403DC0E6
0x1403dc0bc  mov     rdx, rdi
0x1403dc0bf  mov     ecx, 2
0x1403dc0c4  call    cs:__imp_WdLogSingleEntry1
0x1403dc0cb  nop     dword ptr [rax+rax+00h]
0x1403dc0d0  lea     r9, aUnableToOpenHk; "Unable to open HKey root handle (Status"...
0x1403dc0d7  mov     cs:WdLogGlobalForLineNumber, 36Dh
0x1403dc0e1  jmp     loc_1403DC307
0x1403dc0e6  mov     r8, [rbp+60h+KeyHandle]
0x1403dc0ed  test    r8, r8
0x1403dc0f0  jnz     short loc_1403DC141
0x1403dc0f2  mov     ecx, ebx
0x1403dc0f4  call    cs:__imp_WdLogSingleEntry0
0x1403dc0fb  nop     dword ptr [rax+rax+00h]
0x1403dc100  mov     [rsp+160h+var_120], r13
0x1403dc105  lea     r9, aHkeyroothandle; "HKeyRootHandle"
0x1403dc10c  mov     [rsp+160h+var_128], r13
0x1403dc111  mov     eax, 370h
0x1403dc116  mov     [rsp+160h+var_130], r13
0x1403dc11b  mov     r8d, r14d
0x1403dc11e  mov     qword ptr [rsp+160h+var_138], r13
0x1403dc123  mov     edx, 40002h
0x1403dc128  xor     ecx, ecx
0x1403dc12a  mov     [rsp+160h+var_140], rax
0x1403dc12f  mov     cs:WdLogGlobalForLineNumber, eax
0x1403dc135  call    DxgkLogInternalTriageEvent
0x1403dc13a  mov     r8, [rbp+60h+KeyHandle]; void *
0x1403dc141  lea     r9, [rsp+160h+var_100]; struct _UNICODE_STRING *
0x1403dc146  mov     [rsp+160h+var_140], r13; unsigned int *
0x1403dc14b  mov     edx, 0F003Fh; DesiredAccess
0x1403dc150  lea     rcx, [rsp+160h+var_110]; KeyHandle
0x1403dc155  call    ?OpenRegistrySubkey@@YAJPEAPEAXKPEAXAEBU_UNICODE_STRING@@PEAK@Z; OpenRegistrySubkey(void * *,ulong,void *,_UNICODE_STRING const &,ulong *)
0x1403dc15a  movsxd  rdi, eax
0x1403dc15d  test    eax, eax
0x1403dc15f  jns     short loc_1403DC184
0x1403dc161  mov     rdx, rdi
0x1403dc164  mov     ecx, 4
0x1403dc169  call    cs:__imp_WdLogSingleEntry1
0x1403dc170  nop     dword ptr [rax+rax+00h]
0x1403dc175  mov     cs:WdLogGlobalForLineNumber, 37Ch
0x1403dc17f  jmp     loc_1403DC32F
0x1403dc184  mov     r8, [rsp+160h+var_110]
0x1403dc189  test    r8, r8
0x1403dc18c  jnz     short loc_1403DC1DB
0x1403dc18e  mov     ecx, ebx
0x1403dc190  call    cs:__imp_WdLogSingleEntry0
0x1403dc197  nop     dword ptr [rax+rax+00h]
0x1403dc19c  mov     [rsp+160h+var_120], r13
0x1403dc1a1  lea     r9, aPermonsettings; "PerMonSettingsKeyHandle"
0x1403dc1a8  mov     [rsp+160h+var_128], r13
0x1403dc1ad  mov     eax, 380h
0x1403dc1b2  mov     [rsp+160h+var_130], r13
0x1403dc1b7  mov     r8d, r14d
0x1403dc1ba  mov     qword ptr [rsp+160h+var_138], r13
0x1403dc1bf  mov     edx, 40002h
0x1403dc1c4  xor     ecx, ecx
0x1403dc1c6  mov     [rsp+160h+var_140], rax
0x1403dc1cb  mov     cs:WdLogGlobalForLineNumber, eax
0x1403dc1d1  call    DxgkLogInternalTriageEvent
0x1403dc1d6  mov     r8, [rsp+160h+var_110]; void *
0x1403dc1db  lea     r9, [rbp+60h+var_E0]; struct _UNICODE_STRING *
0x1403dc1df  mov     [rsp+160h+var_140], r13; unsigned int *
0x1403dc1e4  mov     edx, 0F003Fh; DesiredAccess
0x1403dc1e9  lea     rcx, [rsp+160h+var_108]; KeyHandle
0x1403dc1ee  call    ?OpenRegistrySubkey@@YAJPEAPEAXKPEAXAEBU_UNICODE_STRING@@PEAK@Z; OpenRegistrySubkey(void * *,ulong,void *,_UNICODE_STRING const &,ulong *)
0x1403dc1f3  movsxd  rdi, eax
0x1403dc1f6  test    eax, eax
0x1403dc1f8  jns     short loc_1403DC21D
0x1403dc1fa  mov     rdx, rdi
0x1403dc1fd  mov     ecx, 4
0x1403dc202  call    cs:__imp_WdLogSingleEntry1
0x1403dc209  nop     dword ptr [rax+rax+00h]
0x1403dc20e  mov     cs:WdLogGlobalForLineNumber, 38Dh
0x1403dc218  jmp     loc_1403DC32F
0x1403dc21d  mov     rdx, [rsp+160h+var_108]
0x1403dc222  test    rdx, rdx
0x1403dc225  jnz     short loc_1403DC274
0x1403dc227  mov     ecx, ebx
0x1403dc229  call    cs:__imp_WdLogSingleEntry0
0x1403dc230  nop     dword ptr [rax+rax+00h]
0x1403dc235  mov     [rsp+160h+var_120], r13
0x1403dc23a  lea     r9, aMonitoridkeyha; "MonitorIdKeyHandle"
0x1403dc241  mov     [rsp+160h+var_128], r13
0x1403dc246  mov     eax, 390h
0x1403dc24b  mov     [rsp+160h+var_130], r13
0x1403dc250  mov     r8d, r14d
0x1403dc253  mov     qword ptr [rsp+160h+var_138], r13
0x1403dc258  mov     edx, 40002h
0x1403dc25d  xor     ecx, ecx
0x1403dc25f  mov     [rsp+160h+var_140], rax
0x1403dc264  mov     cs:WdLogGlobalForLineNumber, eax
0x1403dc26a  call    DxgkLogInternalTriageEvent
0x1403dc26f  mov     rdx, [rsp+160h+var_108]
0x1403dc274  xorps   xmm0, xmm0
0x1403dc277  mov     [rbp+60h+var_A0], r13
0x1403dc27b  lea     rax, aDpivalue; "DpiValue"
0x1403dc282  mov     [rbp+60h+var_98], 120h
0x1403dc289  mov     [rbp+60h+var_90], rax
0x1403dc28d  lea     r8, [rbp+60h+var_A0]
0x1403dc291  lea     rax, [rbp+60h+arg_10]
0x1403dc298  mov     [rbp+60h+var_88], r15
0x1403dc29c  xor     r9d, r9d
0x1403dc29f  mov     [rbp+60h+var_78], rax
0x1403dc2a3  mov     ecx, 40000000h
0x1403dc2a8  mov     [rbp+60h+var_80], 4000004h
0x1403dc2af  mov     [rbp+60h+var_70], 4
0x1403dc2b6  mov     [rbp+60h+var_68], r13
0x1403dc2ba  mov     [rbp+60h+var_60], r13d
0x1403dc2be  mov     [rbp+60h+var_58], r13
0x1403dc2c2  movups  [rbp+60h+var_50], xmm0
0x1403dc2c6  mov     [rsp+160h+var_140], r13
0x1403dc2cb  movups  [rbp+60h+var_40], xmm0
0x1403dc2cf  call    cs:__imp_RtlQueryRegistryValuesEx
0x1403dc2d6  nop     dword ptr [rax+rax+00h]
0x1403dc2db  movsxd  rdi, eax
0x1403dc2de  test    eax, eax
0x1403dc2e0  jns     short loc_1403DC32F
0x1403dc2e2  mov     rdx, rdi
0x1403dc2e5  mov     ecx, 2
0x1403dc2ea  call    cs:__imp_WdLogSingleEntry1
0x1403dc2f1  nop     dword ptr [rax+rax+00h]
0x1403dc2f6  lea     r9, aUnableToReadRe; "Unable to read registry values. (Status"...
0x1403dc2fd  mov     cs:WdLogGlobalForLineNumber, 3A6h
0x1403dc307  mov     [rsp+160h+var_120], r13
0x1403dc30c  mov     r8d, r14d
0x1403dc30f  mov     [rsp+160h+var_128], r13
0x1403dc314  mov     edx, 40000h
0x1403dc319  mov     [rsp+160h+var_130], r13
0x1403dc31e  xor     ecx, ecx
0x1403dc320  mov     qword ptr [rsp+160h+var_138], r13; unsigned int
0x1403dc325  mov     [rsp+160h+var_140], rdi
0x1403dc32a  call    DxgkLogInternalTriageEvent
0x1403dc32f  cmp     edi, 0C0000034h
0x1403dc335  jnz     short loc_1403DC343
0x1403dc337  mov     eax, [rbp+60h+arg_10]
0x1403dc33d  mov     edi, r13d
0x1403dc340  mov     [r15], eax
0x1403dc343  test    r12d, r12d
0x1403dc346  jz      short loc_1403DC3A4
0x1403dc348  test    edi, edi
0x1403dc34a  js      short loc_1403DC3A4
0x1403dc34c  test    rsi, rsi
0x1403dc34f  jz      short loc_1403DC3A4
0x1403dc351  cmp     [rsi+4938h], r13
0x1403dc358  jz      short loc_1403DC3A4
0x1403dc35a  lea     rdx, aRegistryMachin_25; "\\Registry\\Machine\\System"
0x1403dc361  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x1403dc366  call    cs:__imp_RtlInitUnicodeString
0x1403dc36d  nop     dword ptr [rax+rax+00h]
0x1403dc372  lea     rdx, aCurrentcontrol; "CurrentControlSet\\Control\\GraphicsDri"...
0x1403dc379  lea     rcx, [rsp+160h+var_100]; DestinationString
0x1403dc37e  call    cs:__imp_RtlInitUnicodeString
0x1403dc385  nop     dword ptr [rax+rax+00h]
0x1403dc38a  mov     eax, [r15]
0x1403dc38d  lea     r8, [rbp+60h+var_E0]; struct _UNICODE_STRING *
0x1403dc391  lea     rdx, [rsp+160h+var_100]; struct _UNICODE_STRING *
0x1403dc396  mov     dword ptr [rsp+160h+var_140], eax; unsigned __int16 *
0x1403dc39a  lea     rcx, [rsp+160h+DestinationString]; this
0x1403dc39f  call    ?WriteDwordToParticularRegValue@DpiPersistence@@YAJAEBU_UNICODE_STRING@@00QEBGK@Z; DpiPersistence::WriteDwordToParticularRegValue(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,ushort const * const,ulong)
0x1403dc3a4  mov     rcx, [rbp+60h+var_E0.Buffer]; void *
0x1403dc3a8  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1403dc3ad  mov     rcx, [rbp+60h+KeyHandle]; void *
0x1403dc3b4  call    ?CloseRegistrySubkey@@YAXPEAX@Z; CloseRegistrySubkey(void *)
0x1403dc3b9  mov     rcx, [rsp+160h+var_110]; void *
0x1403dc3be  call    ?CloseRegistrySubkey@@YAXPEAX@Z; CloseRegistrySubkey(void *)
0x1403dc3c3  mov     rcx, [rsp+160h+var_108]; void *
0x1403dc3c8  call    ?CloseRegistrySubkey@@YAXPEAX@Z; CloseRegistrySubkey(void *)
0x1403dc3cd  mov     rbx, [rsp+160h+arg_0]
0x1403dc3d5  mov     eax, edi
0x1403dc3d7  add     rsp, 130h
0x1403dc3de  pop     r15
0x1403dc3e0  pop     r14
0x1403dc3e2  pop     r13
0x1403dc3e4  pop     r12
0x1403dc3e6  pop     rdi
0x1403dc3e7  pop     rsi
0x1403dc3e8  pop     rbp
0x1403dc3e9  retn
```
