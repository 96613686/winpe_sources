# OneCore::Base::Telemetry::OneSettingsQuery::Query(ushort const *,bool,ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x1800055f4`
- end: `0x18000578e`
- name: `?Query@OneSettingsQuery@Telemetry@Base@OneCore@@QEAAJPEBG_N0PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, const unsigned __int16 *, bool, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800039c8`

## callees

- `0x180003388`
- `0x18000354c`
- `0x180004a2c`
- `0x180004b04`
- `0x1800055f4`
- `0x180006664`
- `0x180006eb0`
- `0x180007504`
- `0x180007b54`
- `0x180007c90`
- `0x180007e34`
- `0x1800191f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000569b`
- `KERNEL32!GetLastError` at `0x18000569b`
- `KERNEL32!CloseHandle` at `0x18000572f`
- `KERNEL32!CloseHandle` at `0x18000572f`
- `KERNEL32!ReleaseMutex` at `0x180005726`
- `KERNEL32!ReleaseMutex` at `0x180005726`
- `KERNEL32!CreateMutexW` at `0x18000567a`
- `KERNEL32!CreateMutexW` at `0x18000567a`
- `KERNEL32!WaitForSingleObject` at `0x180005690`
- `KERNEL32!WaitForSingleObject` at `0x180005690`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::Query(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        const unsigned __int16 *a2,
        char a3,
        const unsigned __int16 *a4)
{
  _WORD *v5; // rcx
  void *v7; // rsi
  HANDLE MutexW; // rax
  int OneSettingsCommonClient; // ebx
  bool v10; // al
  const unsigned __int16 *v11; // rdx
  unsigned __int16 v12; // cx
  const unsigned __int16 *v13; // r8
  int v14; // eax
  unsigned __int16 v15; // dx
  unsigned __int16 v16; // cx
  unsigned __int16 v17; // r8
  const unsigned __int16 *v18; // rdx
  const unsigned __int16 *v19; // r8
  int SavedSettingsFromRegistry; // eax
  WCHAR Name[264]; // [rsp+40h] [rbp-238h] BYREF

  v5 = (_WORD *)((char *)this + 40);
  if ( !*v5 || !*((_WORD *)this + 280) )
    return (unsigned int)-2147024809;
  v7 = 0;
  if ( (int)StringCchPrintfW(Name, 0x104u, L"%s+%s+%s", L"Global\\OneSettingQueryMutex", v5, (char *)this + 560) >= 0 )
  {
    MutexW = CreateMutexW(0, 0, Name);
    v7 = MutexW;
    if ( !MutexW || WaitForSingleObject(MutexW, 0xEA60u) == -1 )
      GetLastError();
  }
  OneSettingsCommonClient = 1;
  v10 = OneCore::Base::Telemetry::OneSettingsQuery::SettingsFresh(this);
  if ( !a3 || v10 )
  {
LABEL_23:
    SavedSettingsFromRegistry = OneCore::Base::Telemetry::OneSettingsQuery::ReadSavedSettingsFromRegistry(this);
    if ( SavedSettingsFromRegistry < 0 )
    {
      if ( OneSettingsCommonClient >= 0 )
        OneSettingsCommonClient = SavedSettingsFromRegistry;
      goto LABEL_19;
    }
    goto LABEL_18;
  }
  OneSettingsCommonClient = OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(this);
  if ( OneSettingsCommonClient >= 0 )
  {
    v14 = OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsFromCommonClient(this, v11, v13);
LABEL_15:
    OneSettingsCommonClient = v14;
    goto LABEL_16;
  }
  if ( IsWindowsVersionOrGreaterEx(v12, (unsigned __int16)v11, (unsigned __int16)v13, 0x4F7Cu) )
    goto LABEL_19;
  if ( !IsWindowsVersionOrGreaterEx(v16, v15, v17, 0x47BBu) || OneSettingsCommonClient == -2147024770 )
  {
    v14 = OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsDirectly((void **)this, v18, v19);
    goto LABEL_15;
  }
LABEL_16:
  if ( OneSettingsCommonClient )
  {
    if ( OneSettingsCommonClient == 1 )
    {
      OneCore::Base::Telemetry::OneSettingsQuery::UpdateQueryParameters(this);
      OneCore::Base::Telemetry::OneSettingsQuery::UpdateRefreshDeadline((struct _FILETIME *)this);
    }
    goto LABEL_23;
  }
  OneCore::Base::Telemetry::OneSettingsQuery::SaveSettingsToRegistry(this);
  OneCore::Base::Telemetry::OneSettingsQuery::UpdateRefreshDeadline((struct _FILETIME *)this);
LABEL_18:
  OneSettingsCommonClient = 0;
LABEL_19:
  if ( v7 )
  {
    ReleaseMutex(v7);
    CloseHandle(v7);
  }
  return (unsigned int)OneSettingsCommonClient;
}

```

## disassembly

```asm
0x1800055f4  mov     [rsp+arg_8], rbx
0x1800055f9  mov     [rsp+arg_10], rbp
0x1800055fe  push    rsi
0x1800055ff  push    rdi
0x180005600  push    r14
0x180005602  sub     rsp, 260h
0x180005609  mov     rax, cs:__security_cookie
0x180005610  xor     rax, rsp
0x180005613  mov     [rsp+278h+var_28], rax
0x18000561b  mov     rdi, rcx
0x18000561e  xor     r14d, r14d
0x180005621  add     rcx, 28h ; '('
0x180005625  mov     bpl, r8b
0x180005628  cmp     [rcx], r14w
0x18000562c  jz      loc_18000575F
0x180005632  lea     rax, [rdi+230h]
0x180005639  cmp     [rax], r14w
0x18000563d  jz      loc_18000575F
0x180005643  mov     [rsp+278h+var_250], rax
0x180005648  lea     r9, aGlobalOnesetti; "Global\\OneSettingQueryMutex"
0x18000564f  mov     [rsp+278h+var_258], rcx
0x180005654  lea     r8, aSSS; "%s+%s+%s"
0x18000565b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180005660  mov     edx, 104h; unsigned __int64
0x180005665  mov     esi, r14d
0x180005668  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000566d  test    eax, eax
0x18000566f  js      short loc_1800056A1
0x180005671  lea     r8, [rsp+278h+Name]; lpName
0x180005676  xor     edx, edx; bInitialOwner
0x180005678  xor     ecx, ecx; lpMutexAttributes
0x18000567a  call    cs:__imp_CreateMutexW
0x180005680  mov     rsi, rax
0x180005683  test    rax, rax
0x180005686  jz      short loc_18000569B
0x180005688  mov     edx, 0EA60h; dwMilliseconds
0x18000568d  mov     rcx, rax; hHandle
0x180005690  call    cs:__imp_WaitForSingleObject
0x180005696  cmp     eax, 0FFFFFFFFh
0x180005699  jnz     short loc_1800056A1
0x18000569b  call    cs:__imp_GetLastError
0x1800056a1  mov     rcx, rdi; this
0x1800056a4  mov     ebx, 1
0x1800056a9  call    ?SettingsFresh@OneSettingsQuery@Telemetry@Base@OneCore@@QEAA_NXZ; OneCore::Base::Telemetry::OneSettingsQuery::SettingsFresh(void)
0x1800056ae  test    bpl, bpl
0x1800056b1  jz      loc_18000574C
0x1800056b7  test    al, al
0x1800056b9  jnz     loc_18000574C
0x1800056bf  mov     rcx, rdi; this
0x1800056c2  call    ?LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)
0x1800056c7  mov     ebx, eax
0x1800056c9  test    eax, eax
0x1800056cb  js      short loc_1800056D7
0x1800056cd  mov     rcx, rdi; this
0x1800056d0  call    ?DownloadSettingsFromCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG0@Z; OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsFromCommonClient(ushort const *,ushort const *)
0x1800056d5  jmp     short loc_180005705
0x1800056d7  mov     r9d, 4F7Ch; unsigned __int16
0x1800056dd  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x1800056e2  test    al, al
0x1800056e4  jnz     short loc_18000571E
0x1800056e6  mov     r9d, 47BBh; unsigned __int16
0x1800056ec  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x1800056f1  test    al, al
0x1800056f3  jz      short loc_1800056FD
0x1800056f5  cmp     ebx, 8007007Eh
0x1800056fb  jnz     short loc_180005707
0x1800056fd  mov     rcx, rdi; this
0x180005700  call    ?DownloadSettingsDirectly@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG0@Z; OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsDirectly(ushort const *,ushort const *)
0x180005705  mov     ebx, eax
0x180005707  test    ebx, ebx
0x180005709  jnz     short loc_180005737
0x18000570b  mov     rcx, rdi; this
0x18000570e  call    ?SaveSettingsToRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::SaveSettingsToRegistry(void)
0x180005713  mov     rcx, rdi; this
0x180005716  call    ?UpdateRefreshDeadline@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::UpdateRefreshDeadline(void)
0x18000571b  mov     ebx, r14d
0x18000571e  test    rsi, rsi
0x180005721  jz      short loc_180005764
0x180005723  mov     rcx, rsi; hMutex
0x180005726  call    cs:__imp_ReleaseMutex
0x18000572c  mov     rcx, rsi; hObject
0x18000572f  call    cs:__imp_CloseHandle
0x180005735  jmp     short loc_180005764
0x180005737  cmp     ebx, 1
0x18000573a  jnz     short loc_18000574C
0x18000573c  mov     rcx, rdi; this
0x18000573f  call    ?UpdateQueryParameters@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::UpdateQueryParameters(void)
0x180005744  mov     rcx, rdi; this
0x180005747  call    ?UpdateRefreshDeadline@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::UpdateRefreshDeadline(void)
0x18000574c  mov     rcx, rdi; this
0x18000574f  call    ?ReadSavedSettingsFromRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ; OneCore::Base::Telemetry::OneSettingsQuery::ReadSavedSettingsFromRegistry(void)
0x180005754  test    eax, eax
0x180005756  jns     short loc_18000571B
0x180005758  test    ebx, ebx
0x18000575a  cmovns  ebx, eax
0x18000575d  jmp     short loc_18000571E
0x18000575f  mov     ebx, 80070057h
0x180005764  mov     eax, ebx
0x180005766  mov     rcx, [rsp+278h+var_28]
0x18000576e  xor     rcx, rsp; StackCookie
0x180005771  call    __security_check_cookie
0x180005776  lea     r11, [rsp+278h+var_18]
0x18000577e  mov     rbx, [r11+28h]
0x180005782  mov     rbp, [r11+30h]
0x180005786  mov     rsp, r11
0x180005789  pop     r14
0x18000578b  pop     rdi
0x18000578c  pop     rsi
0x18000578d  retn
```
