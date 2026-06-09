# DpiPersistence::ReadDpiFromRegistry(_LUID const &,uint,int,ulong *)

- ea: `0x1403dc2c8`
- end: `0x1403dc80b`
- name: `?ReadDpiFromRegistry@DpiPersistence@@YAJAEBU_LUID@@IHPEAK@Z`
- size: `1347`
- prototype: `__int64 __fastcall(DpiPersistence *__hidden this, const struct _LUID *, unsigned int, int, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1401e1120`
- `0x1402332b0`

## callees

- `0x14000d990`
- `0x140012540`
- `0x14001b9c0`
- `0x140329ff0`
- `0x1403dbfbc`
- `0x1403dc2c8`
- `0x1403dc814`
- `0x1403dc838`
- `0x140401848`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403dc347`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403dc378`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403dc347`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403dc378`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1403dc6ef`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1403dc6ef`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403dc470`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403dc488`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403dc786`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403dc79e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403dc470`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403dc488`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403dc786`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403dc79e`
- `ntoskrnl!ZwOpenKey` at `0x1403dc4c9`
- `ntoskrnl!ZwOpenKey` at `0x1403dc4c9`
- `watchdog!WdLogSingleEntry2` at `0x1403dc362`
- `watchdog!WdLogSingleEntry2` at `0x1403dc362`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1403dc3cd`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1403dc44e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1403dc3cd`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1403dc44e`
- `watchdog!WdLogSingleEntry0` at `0x1403dc408`
- `watchdog!WdLogSingleEntry0` at `0x1403dc514`
- `watchdog!WdLogSingleEntry0` at `0x1403dc5b0`
- `watchdog!WdLogSingleEntry0` at `0x1403dc649`
- `watchdog!WdLogSingleEntry0` at `0x1403dc408`
- `watchdog!WdLogSingleEntry0` at `0x1403dc514`
- `watchdog!WdLogSingleEntry0` at `0x1403dc5b0`
- `watchdog!WdLogSingleEntry0` at `0x1403dc649`
- `watchdog!WdLogSingleEntry1` at `0x1403dc4e4`
- `watchdog!WdLogSingleEntry1` at `0x1403dc589`
- `watchdog!WdLogSingleEntry1` at `0x1403dc622`
- `watchdog!WdLogSingleEntry1` at `0x1403dc70a`
- `watchdog!WdLogSingleEntry1` at `0x1403dc4e4`
- `watchdog!WdLogSingleEntry1` at `0x1403dc589`
- `watchdog!WdLogSingleEntry1` at `0x1403dc622`
- `watchdog!WdLogSingleEntry1` at `0x1403dc70a`

## string_xrefs

- `0x1403dc4f0`: `Unable to open HKey root handle (Status = 0x%I64x)`
- `0x1403dc45a`: `\Registry\Machine\System`
- `0x1403dc77a`: `\Registry\Machine\System`
- `0x1403dc419`: `pDxgSessionData->GetUserRegistryPath()->Length == 0`
- `0x1403dc716`: `Unable to read registry values. (Status = 0x%I64x, SubKeyHandle2 = 0x%I64x, QueryTable = 0x%I64x)`

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
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int CurrentProcessSessionId; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // eax
  const WCHAR *v16; // rdx
  NTSTATUS v17; // eax
  const wchar_t *v18; // r9
  void *v19; // r8
  int v20; // eax
  void *v21; // r8
  int v22; // eax
  void *v23; // rdx
  int v24; // eax
  const struct _UNICODE_STRING *v25; // r9
  unsigned int *v27; // [rsp+20h] [rbp-E0h]
  unsigned int v28; // [rsp+28h] [rbp-D8h]
  void *v29; // [rsp+50h] [rbp-B0h] BYREF
  void *v30; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING v31; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v33; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  __int64 v35; // [rsp+C0h] [rbp-40h] BYREF
  int v36; // [rsp+C8h] [rbp-38h]
  const WCHAR *v37; // [rsp+D0h] [rbp-30h]
  struct _UNICODE_STRING *v38; // [rsp+D8h] [rbp-28h]
  int v39; // [rsp+E0h] [rbp-20h]
  int *v40; // [rsp+E8h] [rbp-18h]
  int v41; // [rsp+F0h] [rbp-10h]
  __int64 v42; // [rsp+F8h] [rbp-8h]
  int v43; // [rsp+100h] [rbp+0h]
  __int64 v44; // [rsp+108h] [rbp+8h]
  __int128 v45; // [rsp+110h] [rbp+10h]
  __int128 v46; // [rsp+120h] [rbp+20h]
  int v47; // [rsp+180h] [rbp+80h] BYREF
  void *KeyHandle; // [rsp+188h] [rbp+88h] BYREF

  v47 = 0;
  *(_DWORD *)&a4->Length = 0;
  KeyHandle = 0;
  v33 = 0;
  v29 = 0;
  v5 = 0;
  v30 = 0;
  DestinationString = 0;
  v31 = 0;
  LODWORD(v7) = DpiPersistence::AllocateMonitorSetIdFromAdapterSource(this, a2, (unsigned int)&v33, a4);
  if ( (int)v7 >= 0 )
  {
    Global = DXGGLOBAL::GetGlobal();
    SessionData = DXGGLOBAL::GetSessionData(Global);
    v5 = (struct _UNICODE_STRING *)SessionData;
    if ( !SessionData )
    {
      CurrentProcessSessionId = PsGetCurrentProcessSessionId(v11, v10);
      LODWORD(v7) = -1073741811;
      WdLogSingleEntry2(2, CurrentProcessSessionId, -1073741811);
      WdLogGlobalForLineNumber = 828;
      v15 = PsGetCurrentProcessSessionId(v14, v13);
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Current session does not have session data in session 0x%I64x, returning 0x%I64x.",
        v15,
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
      v16 = L"Control Panel\\Desktop\\PerMonitorSettings\\";
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
      v16 = L"CurrentControlSet\\Control\\GraphicsDrivers\\ScaleFactors";
    }
    RtlInitUnicodeString(&v31, v16);
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    ObjectAttributes.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v17 = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
    v7 = v17;
    if ( v17 >= 0 )
    {
      v19 = KeyHandle;
      if ( !KeyHandle )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 880;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"HKeyRootHandle", 880, 0, 0, 0, 0);
        v19 = KeyHandle;
      }
      v20 = OpenRegistrySubkey(&v29, 0xF003Fu, v19, &v31, 0);
      LODWORD(v7) = v20;
      if ( v20 < 0 )
      {
        WdLogSingleEntry1(4, v20);
        WdLogGlobalForLineNumber = 892;
        goto LABEL_24;
      }
      v21 = v29;
      if ( !v29 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 896;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"PerMonSettingsKeyHandle", 896, 0, 0, 0, 0);
        v21 = v29;
      }
      v22 = OpenRegistrySubkey(&v30, 0xF003Fu, v21, &v33, 0);
      LODWORD(v7) = v22;
      if ( v22 < 0 )
      {
        WdLogSingleEntry1(4, v22);
        WdLogGlobalForLineNumber = 909;
        goto LABEL_24;
      }
      v23 = v30;
      if ( !v30 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 912;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"MonitorIdKeyHandle", 912, 0, 0, 0, 0);
        v23 = v30;
      }
      v35 = 0;
      v36 = 288;
      v37 = L"DpiValue";
      v38 = a4;
      v40 = &v47;
      v39 = 67108868;
      v41 = 4;
      v42 = 0;
      v43 = 0;
      v44 = 0;
      v45 = 0;
      v46 = 0;
      v24 = RtlQueryRegistryValuesEx(0x40000000, v23, &v35, 0, 0);
      v7 = v24;
      if ( v24 >= 0 )
        goto LABEL_24;
      WdLogSingleEntry1(2, v24);
      v18 = L"Unable to read registry values. (Status = 0x%I64x, SubKeyHandle2 = 0x%I64x, QueryTable = 0x%I64x)";
      WdLogGlobalForLineNumber = 934;
    }
    else
    {
      WdLogSingleEntry1(2, v17);
      v18 = L"Unable to open HKey root handle (Status = 0x%I64x)";
      WdLogGlobalForLineNumber = 877;
    }
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v18, v7, 0, 0, 0, 0);
  }
LABEL_24:
  if ( (_DWORD)v7 == -1073741772 )
  {
    LODWORD(v7) = 0;
    *(_DWORD *)&a4->Length = v47;
  }
LABEL_26:
  if ( a3 && (int)v7 >= 0 && v5 && v5[1171].Buffer )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System");
    RtlInitUnicodeString(&v31, L"CurrentControlSet\\Control\\GraphicsDrivers\\ScaleFactors");
    LODWORD(v27) = *(_DWORD *)&a4->Length;
    DpiPersistence::WriteDwordToParticularRegValue(
      (DpiPersistence *)&DestinationString,
      &v31,
      &v33,
      v25,
      (const unsigned __int16 *const)v27,
      v28);
  }
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v33.Buffer);
  CloseRegistrySubkey(KeyHandle);
  CloseRegistrySubkey(v29);
  CloseRegistrySubkey(v30);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1403dc2c8  mov     [rsp-8+arg_0], rbx
0x1403dc2cd  push    rbp
0x1403dc2ce  push    rsi
0x1403dc2cf  push    rdi
0x1403dc2d0  push    r12
0x1403dc2d2  push    r13
0x1403dc2d4  push    r14
0x1403dc2d6  push    r15
0x1403dc2d8  lea     rbp, [rsp-30h]
0x1403dc2dd  sub     rsp, 130h
0x1403dc2e4  xor     r13d, r13d
0x1403dc2e7  xorps   xmm0, xmm0
0x1403dc2ea  mov     r12d, r8d
0x1403dc2ed  mov     [rbp+60h+arg_10], r13d
0x1403dc2f4  xorps   xmm1, xmm1
0x1403dc2f7  mov     [r9], r13d
0x1403dc2fa  lea     r8, [rbp+60h+var_E0]; unsigned int
0x1403dc2fe  mov     [rbp+60h+KeyHandle], r13
0x1403dc305  movups  xmmword ptr [rbp+60h+var_E0.Length], xmm0
0x1403dc309  mov     [rsp+160h+var_110], r13
0x1403dc30e  mov     esi, r13d
0x1403dc311  mov     [rsp+160h+var_108], r13
0x1403dc316  mov     r15, r9
0x1403dc319  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x1403dc31e  movups  xmmword ptr [rsp+160h+var_100.Length], xmm1
0x1403dc323  call    ?AllocateMonitorSetIdFromAdapterSource@DpiPersistence@@YAJAEBU_LUID@@IPEAU_UNICODE_STRING@@@Z; DpiPersistence::AllocateMonitorSetIdFromAdapterSource(_LUID const &,uint,_UNICODE_STRING *)
0x1403dc328  mov     edi, eax
0x1403dc32a  test    eax, eax
0x1403dc32c  js      loc_1403DC74F
0x1403dc332  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1403dc337  mov     rcx, rax; this
0x1403dc33a  call    ?GetSessionData@DXGGLOBAL@@QEAAPEAVDXGSESSIONDATA@@XZ; DXGGLOBAL::GetSessionData(void)
0x1403dc33f  mov     rsi, rax
0x1403dc342  test    rax, rax
0x1403dc345  jnz     short loc_1403DC3BB
0x1403dc347  call    cs:__imp_PsGetCurrentProcessSessionId
0x1403dc34e  nop     dword ptr [rax+rax+00h]
0x1403dc353  mov     rdi, 0FFFFFFFFC000000Dh
0x1403dc35a  mov     edx, eax
0x1403dc35c  mov     r8, rdi
0x1403dc35f  lea     ecx, [rsi+2]
0x1403dc362  call    cs:__imp_WdLogSingleEntry2
0x1403dc369  nop     dword ptr [rax+rax+00h]
0x1403dc36e  mov     cs:WdLogGlobalForLineNumber, 33Ch
0x1403dc378  call    cs:__imp_PsGetCurrentProcessSessionId
0x1403dc37f  nop     dword ptr [rax+rax+00h]
0x1403dc384  mov     [rsp+160h+var_120], r13
0x1403dc389  lea     r9, aCurrentSession_0; "Current session does not have session d"...
0x1403dc390  mov     [rsp+160h+var_128], r13
0x1403dc395  or      r8d, 0FFFFFFFFh
0x1403dc399  mov     ecx, eax
0x1403dc39b  mov     edx, 40000h
0x1403dc3a0  mov     [rsp+160h+var_130], r13
0x1403dc3a5  mov     qword ptr [rsp+160h+var_138], rdi
0x1403dc3aa  mov     [rsp+160h+var_140], rcx
0x1403dc3af  xor     ecx, ecx
0x1403dc3b1  call    DxgkLogInternalTriageEvent
0x1403dc3b6  jmp     loc_1403DC763
0x1403dc3bb  or      r14d, 0FFFFFFFFh
0x1403dc3bf  mov     ebx, 1
0x1403dc3c4  cmp     [rax+4938h], r13
0x1403dc3cb  jz      short loc_1403DC3FC
0x1403dc3cd  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1403dc3d4  nop     dword ptr [rax+rax+00h]
0x1403dc3d9  mov     cs:WdLogGlobalForLineNumber, 35Ch
0x1403dc3e3  lea     rdx, aControlPanelDe; "Control Panel\\Desktop\\PerMonitorSetti"...
0x1403dc3ea  movups  xmm0, xmmword ptr [rsi+4930h]
0x1403dc3f1  movdqu  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x1403dc3f7  jmp     loc_1403DC483
0x1403dc3fc  cmp     [rax+4930h], r13w
0x1403dc404  jz      short loc_1403DC44E
0x1403dc406  mov     ecx, ebx
0x1403dc408  call    cs:__imp_WdLogSingleEntry0
0x1403dc40f  nop     dword ptr [rax+rax+00h]
0x1403dc414  mov     [rsp+160h+var_120], r13
0x1403dc419  lea     r9, aPdxgsessiondat; "pDxgSessionData->GetUserRegistryPath()-"...
0x1403dc420  mov     [rsp+160h+var_128], r13
0x1403dc425  mov     eax, 353h
0x1403dc42a  mov     [rsp+160h+var_130], r13
0x1403dc42f  mov     r8d, r14d
0x1403dc432  mov     qword ptr [rsp+160h+var_138], r13
0x1403dc437  mov     edx, 40002h
0x1403dc43c  xor     ecx, ecx
0x1403dc43e  mov     [rsp+160h+var_140], rax
0x1403dc443  mov     cs:WdLogGlobalForLineNumber, eax
0x1403dc449  call    DxgkLogInternalTriageEvent
0x1403dc44e  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1403dc455  nop     dword ptr [rax+rax+00h]
0x1403dc45a  lea     rdx, aRegistryMachin_25; "\\Registry\\Machine\\System"
0x1403dc461  mov     cs:WdLogGlobalForLineNumber, 354h
0x1403dc46b  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x1403dc470  call    cs:__imp_RtlInitUnicodeString
0x1403dc477  nop     dword ptr [rax+rax+00h]
0x1403dc47c  lea     rdx, aCurrentcontrol; "CurrentControlSet\\Control\\GraphicsDri"...
0x1403dc483  lea     rcx, [rsp+160h+var_100]; DestinationString
0x1403dc488  call    cs:__imp_RtlInitUnicodeString
0x1403dc48f  nop     dword ptr [rax+rax+00h]
0x1403dc494  lea     rax, [rsp+160h+DestinationString]
0x1403dc499  mov     qword ptr [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x1403dc4a1  xorps   xmm0, xmm0
0x1403dc4a4  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x1403dc4a8  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x1403dc4ac  mov     qword ptr [rbp+60h+ObjectAttributes.Attributes], 240h
0x1403dc4b4  mov     edx, 0F003Fh; DesiredAccess
0x1403dc4b9  mov     [rbp+60h+ObjectAttributes.RootDirectory], r13
0x1403dc4bd  lea     rcx, [rbp+60h+KeyHandle]; KeyHandle
0x1403dc4c4  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1403dc4c9  call    cs:__imp_ZwOpenKey
0x1403dc4d0  nop     dword ptr [rax+rax+00h]
0x1403dc4d5  movsxd  rdi, eax
0x1403dc4d8  test    eax, eax
0x1403dc4da  jns     short loc_1403DC506
0x1403dc4dc  mov     rdx, rdi
0x1403dc4df  mov     ecx, 2
0x1403dc4e4  call    cs:__imp_WdLogSingleEntry1
0x1403dc4eb  nop     dword ptr [rax+rax+00h]
0x1403dc4f0  lea     r9, aUnableToOpenHk; "Unable to open HKey root handle (Status"...
0x1403dc4f7  mov     cs:WdLogGlobalForLineNumber, 36Dh
0x1403dc501  jmp     loc_1403DC727
0x1403dc506  mov     r8, [rbp+60h+KeyHandle]
0x1403dc50d  test    r8, r8
0x1403dc510  jnz     short loc_1403DC561
0x1403dc512  mov     ecx, ebx
0x1403dc514  call    cs:__imp_WdLogSingleEntry0
0x1403dc51b  nop     dword ptr [rax+rax+00h]
0x1403dc520  mov     [rsp+160h+var_120], r13
0x1403dc525  lea     r9, aHkeyroothandle; "HKeyRootHandle"
0x1403dc52c  mov     [rsp+160h+var_128], r13
0x1403dc531  mov     eax, 370h
0x1403dc536  mov     [rsp+160h+var_130], r13
0x1403dc53b  mov     r8d, r14d
0x1403dc53e  mov     qword ptr [rsp+160h+var_138], r13
0x1403dc543  mov     edx, 40002h
0x1403dc548  xor     ecx, ecx
0x1403dc54a  mov     [rsp+160h+var_140], rax
0x1403dc54f  mov     cs:WdLogGlobalForLineNumber, eax
0x1403dc555  call    DxgkLogInternalTriageEvent
0x1403dc55a  mov     r8, [rbp+60h+KeyHandle]; void *
0x1403dc561  lea     r9, [rsp+160h+var_100]; struct _UNICODE_STRING *
0x1403dc566  mov     [rsp+160h+var_140], r13; unsigned int *
0x1403dc56b  mov     edx, 0F003Fh; DesiredAccess
0x1403dc570  lea     rcx, [rsp+160h+var_110]; KeyHandle
0x1403dc575  call    ?OpenRegistrySubkey@@YAJPEAPEAXKPEAXAEBU_UNICODE_STRING@@PEAK@Z; OpenRegistrySubkey(void * *,ulong,void *,_UNICODE_STRING const &,ulong *)
0x1403dc57a  movsxd  rdi, eax
0x1403dc57d  test    eax, eax
0x1403dc57f  jns     short loc_1403DC5A4
0x1403dc581  mov     rdx, rdi
0x1403dc584  mov     ecx, 4
0x1403dc589  call    cs:__imp_WdLogSingleEntry1
0x1403dc590  nop     dword ptr [rax+rax+00h]
0x1403dc595  mov     cs:WdLogGlobalForLineNumber, 37Ch
0x1403dc59f  jmp     loc_1403DC74F
0x1403dc5a4  mov     r8, [rsp+160h+var_110]
0x1403dc5a9  test    r8, r8
0x1403dc5ac  jnz     short loc_1403DC5FB
0x1403dc5ae  mov     ecx, ebx
0x1403dc5b0  call    cs:__imp_WdLogSingleEntry0
0x1403dc5b7  nop     dword ptr [rax+rax+00h]
0x1403dc5bc  mov     [rsp+160h+var_120], r13
0x1403dc5c1  lea     r9, aPermonsettings; "PerMonSettingsKeyHandle"
0x1403dc5c8  mov     [rsp+160h+var_128], r13
0x1403dc5cd  mov     eax, 380h
0x1403dc5d2  mov     [rsp+160h+var_130], r13
0x1403dc5d7  mov     r8d, r14d
0x1403dc5da  mov     qword ptr [rsp+160h+var_138], r13
0x1403dc5df  mov     edx, 40002h
0x1403dc5e4  xor     ecx, ecx
0x1403dc5e6  mov     [rsp+160h+var_140], rax
0x1403dc5eb  mov     cs:WdLogGlobalForLineNumber, eax
0x1403dc5f1  call    DxgkLogInternalTriageEvent
0x1403dc5f6  mov     r8, [rsp+160h+var_110]; void *
0x1403dc5fb  lea     r9, [rbp+60h+var_E0]; struct _UNICODE_STRING *
0x1403dc5ff  mov     [rsp+160h+var_140], r13; unsigned int *
0x1403dc604  mov     edx, 0F003Fh; DesiredAccess
0x1403dc609  lea     rcx, [rsp+160h+var_108]; KeyHandle
0x1403dc60e  call    ?OpenRegistrySubkey@@YAJPEAPEAXKPEAXAEBU_UNICODE_STRING@@PEAK@Z; OpenRegistrySubkey(void * *,ulong,void *,_UNICODE_STRING const &,ulong *)
0x1403dc613  movsxd  rdi, eax
0x1403dc616  test    eax, eax
0x1403dc618  jns     short loc_1403DC63D
0x1403dc61a  mov     rdx, rdi
0x1403dc61d  mov     ecx, 4
0x1403dc622  call    cs:__imp_WdLogSingleEntry1
0x1403dc629  nop     dword ptr [rax+rax+00h]
0x1403dc62e  mov     cs:WdLogGlobalForLineNumber, 38Dh
0x1403dc638  jmp     loc_1403DC74F
0x1403dc63d  mov     rdx, [rsp+160h+var_108]
0x1403dc642  test    rdx, rdx
0x1403dc645  jnz     short loc_1403DC694
0x1403dc647  mov     ecx, ebx
0x1403dc649  call    cs:__imp_WdLogSingleEntry0
0x1403dc650  nop     dword ptr [rax+rax+00h]
0x1403dc655  mov     [rsp+160h+var_120], r13
0x1403dc65a  lea     r9, aMonitoridkeyha; "MonitorIdKeyHandle"
0x1403dc661  mov     [rsp+160h+var_128], r13
0x1403dc666  mov     eax, 390h
0x1403dc66b  mov     [rsp+160h+var_130], r13
0x1403dc670  mov     r8d, r14d
0x1403dc673  mov     qword ptr [rsp+160h+var_138], r13
0x1403dc678  mov     edx, 40002h
0x1403dc67d  xor     ecx, ecx
0x1403dc67f  mov     [rsp+160h+var_140], rax
0x1403dc684  mov     cs:WdLogGlobalForLineNumber, eax
0x1403dc68a  call    DxgkLogInternalTriageEvent
0x1403dc68f  mov     rdx, [rsp+160h+var_108]
0x1403dc694  xorps   xmm0, xmm0
0x1403dc697  mov     [rbp+60h+var_A0], r13
0x1403dc69b  lea     rax, aDpivalue; "DpiValue"
0x1403dc6a2  mov     [rbp+60h+var_98], 120h
0x1403dc6a9  mov     [rbp+60h+var_90], rax
0x1403dc6ad  lea     r8, [rbp+60h+var_A0]
0x1403dc6b1  lea     rax, [rbp+60h+arg_10]
0x1403dc6b8  mov     [rbp+60h+var_88], r15
0x1403dc6bc  xor     r9d, r9d
0x1403dc6bf  mov     [rbp+60h+var_78], rax
0x1403dc6c3  mov     ecx, 40000000h
0x1403dc6c8  mov     [rbp+60h+var_80], 4000004h
0x1403dc6cf  mov     [rbp+60h+var_70], 4
0x1403dc6d6  mov     [rbp+60h+var_68], r13
0x1403dc6da  mov     [rbp+60h+var_60], r13d
0x1403dc6de  mov     [rbp+60h+var_58], r13
0x1403dc6e2  movups  [rbp+60h+var_50], xmm0
0x1403dc6e6  mov     [rsp+160h+var_140], r13
0x1403dc6eb  movups  [rbp+60h+var_40], xmm0
0x1403dc6ef  call    cs:__imp_RtlQueryRegistryValuesEx
0x1403dc6f6  nop     dword ptr [rax+rax+00h]
0x1403dc6fb  movsxd  rdi, eax
0x1403dc6fe  test    eax, eax
0x1403dc700  jns     short loc_1403DC74F
0x1403dc702  mov     rdx, rdi
0x1403dc705  mov     ecx, 2
0x1403dc70a  call    cs:__imp_WdLogSingleEntry1
0x1403dc711  nop     dword ptr [rax+rax+00h]
0x1403dc716  lea     r9, aUnableToReadRe; "Unable to read registry values. (Status"...
0x1403dc71d  mov     cs:WdLogGlobalForLineNumber, 3A6h
0x1403dc727  mov     [rsp+160h+var_120], r13
0x1403dc72c  mov     r8d, r14d
0x1403dc72f  mov     [rsp+160h+var_128], r13
0x1403dc734  mov     edx, 40000h
0x1403dc739  mov     [rsp+160h+var_130], r13
0x1403dc73e  xor     ecx, ecx
0x1403dc740  mov     qword ptr [rsp+160h+var_138], r13; unsigned int
0x1403dc745  mov     [rsp+160h+var_140], rdi
0x1403dc74a  call    DxgkLogInternalTriageEvent
0x1403dc74f  cmp     edi, 0C0000034h
0x1403dc755  jnz     short loc_1403DC763
0x1403dc757  mov     eax, [rbp+60h+arg_10]
0x1403dc75d  mov     edi, r13d
0x1403dc760  mov     [r15], eax
0x1403dc763  test    r12d, r12d
0x1403dc766  jz      short loc_1403DC7C4
0x1403dc768  test    edi, edi
0x1403dc76a  js      short loc_1403DC7C4
0x1403dc76c  test    rsi, rsi
0x1403dc76f  jz      short loc_1403DC7C4
0x1403dc771  cmp     [rsi+4938h], r13
0x1403dc778  jz      short loc_1403DC7C4
0x1403dc77a  lea     rdx, aRegistryMachin_25; "\\Registry\\Machine\\System"
0x1403dc781  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x1403dc786  call    cs:__imp_RtlInitUnicodeString
0x1403dc78d  nop     dword ptr [rax+rax+00h]
0x1403dc792  lea     rdx, aCurrentcontrol; "CurrentControlSet\\Control\\GraphicsDri"...
0x1403dc799  lea     rcx, [rsp+160h+var_100]; DestinationString
0x1403dc79e  call    cs:__imp_RtlInitUnicodeString
0x1403dc7a5  nop     dword ptr [rax+rax+00h]
0x1403dc7aa  mov     eax, [r15]
0x1403dc7ad  lea     r8, [rbp+60h+var_E0]; struct _UNICODE_STRING *
0x1403dc7b1  lea     rdx, [rsp+160h+var_100]; struct _UNICODE_STRING *
0x1403dc7b6  mov     dword ptr [rsp+160h+var_140], eax; unsigned __int16 *
0x1403dc7ba  lea     rcx, [rsp+160h+DestinationString]; this
0x1403dc7bf  call    ?WriteDwordToParticularRegValue@DpiPersistence@@YAJAEBU_UNICODE_STRING@@00QEBGK@Z; DpiPersistence::WriteDwordToParticularRegValue(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,ushort const * const,ulong)
0x1403dc7c4  mov     rcx, [rbp+60h+var_E0.Buffer]; void *
0x1403dc7c8  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1403dc7cd  mov     rcx, [rbp+60h+KeyHandle]; void *
0x1403dc7d4  call    ?CloseRegistrySubkey@@YAXPEAX@Z; CloseRegistrySubkey(void *)
0x1403dc7d9  mov     rcx, [rsp+160h+var_110]; void *
0x1403dc7de  call    ?CloseRegistrySubkey@@YAXPEAX@Z; CloseRegistrySubkey(void *)
0x1403dc7e3  mov     rcx, [rsp+160h+var_108]; void *
0x1403dc7e8  call    ?CloseRegistrySubkey@@YAXPEAX@Z; CloseRegistrySubkey(void *)
0x1403dc7ed  mov     rbx, [rsp+160h+arg_0]
0x1403dc7f5  mov     eax, edi
0x1403dc7f7  add     rsp, 130h
0x1403dc7fe  pop     r15
0x1403dc800  pop     r14
0x1403dc802  pop     r13
0x1403dc804  pop     r12
0x1403dc806  pop     rdi
0x1403dc807  pop     rsi
0x1403dc808  pop     rbp
0x1403dc809  retn
```
