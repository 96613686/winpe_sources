# NGENService::GetSystemSnapshot(SYSTEM_SNAPSHOT *,ulong)

- ea: `0x180007130`
- end: `0x180007516`
- name: `?GetSystemSnapshot@NGENService@@YAXPEAUSYSTEM_SNAPSHOT@@K@Z`
- size: `998`
- prototype: `void __fastcall(NGENService *__hidden this, struct SYSTEM_SNAPSHOT *, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x180004170`
- `0x1800050b4`
- `0x18000765c`

## callees

- `0x180002f0c`
- `0x180007050`
- `0x180007130`
- `0x180007e1c`
- `0x180007e94`
- `0x18002e1d0`
- `0x1800366a8`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800071b3`
- `KERNEL32!LoadLibraryExW` at `0x1800072a5`
- `KERNEL32!LoadLibraryExW` at `0x1800071b3`
- `KERNEL32!LoadLibraryExW` at `0x1800072a5`
- `KERNEL32!GetTickCount` at `0x180007148`
- `KERNEL32!GetTickCount` at `0x180007148`
- `KERNEL32!GetSystemPowerStatus` at `0x18000716a`
- `KERNEL32!GetSystemPowerStatus` at `0x18000716a`
- `KERNEL32!GetProcAddress` at `0x1800071c8`
- `KERNEL32!GetProcAddress` at `0x1800072ba`
- `KERNEL32!GetProcAddress` at `0x1800071c8`
- `KERNEL32!GetProcAddress` at `0x1800072ba`
- `USER32!SystemParametersInfoW` at `0x18000727f`
- `USER32!SystemParametersInfoW` at `0x18000727f`

## string_xrefs

- `0x1800071aa`: `Wtsapi32.dll`
- `0x18000729c`: `powrprof.dll`

## pseudocode

```c
void __fastcall NGENService::GetSystemSnapshot(struct _SYSTEM_POWER_STATUS *this, struct SYSTEM_SNAPSHOT *a2)
{
  DWORD TickCount; // eax
  unsigned int *v4; // r8
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  int v7; // edi
  __int64 v8; // rdx
  void *v9; // rcx
  __int64 v10; // r8
  struct _WTS_SESSION_INFOW *v11; // rax
  __int64 v12; // rdx
  FARPROC v13; // rax
  HMODULE v14; // rax
  bool v15; // dl
  NGENService *v16; // rcx
  const unsigned __int16 *v17; // rdx
  unsigned int ConfigValue; // eax
  const unsigned __int16 *v19; // rdx
  const unsigned __int16 *v20; // rdx
  const unsigned __int16 *v21; // rdi
  BYTE ACLineStatus; // al
  __int64 BatteryLifePercent; // r8
  const unsigned __int16 *v24; // rdx
  const unsigned __int16 *v25; // rdx
  const unsigned __int16 *v26; // rdx
  const unsigned __int16 *v27; // rdx
  const unsigned __int16 *v28; // rdx
  const unsigned __int16 *v29; // rdx
  const unsigned __int16 *v30; // rdx
  const unsigned __int16 *v31; // rdx
  char v32; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v33; // [rsp+68h] [rbp+10h] BYREF
  struct _WTS_SESSION_INFOW *v34; // [rsp+70h] [rbp+18h] BYREF
  void *v35; // [rsp+78h] [rbp+20h] BYREF

  v33 = (unsigned int)a2;
  this->BatteryLifeTime &= 0xFFFFFE00;
  TickCount = GetTickCount();
  *(_DWORD *)&this->ACLineStatus = TickCount;
  if ( (unsigned int)NGENService::IdleGetLastInputInfo((NGENService *)TickCount, (int)this + 8, v4) )
    this->BatteryLifeTime |= 1u;
  if ( GetSystemPowerStatus(this + 1) )
    this->BatteryLifeTime |= 8u;
  if ( NGENService::g_fRunningOnTS )
  {
    ProcAddress = (FARPROC)qword_18006FF70;
    if ( qword_18006FF70
      || !bWTSQuerySessionInformationProbed
      && ((Library = LoadLibraryExW(L"Wtsapi32.dll", 0, 0)) == 0
        ? (ProcAddress = (FARPROC)qword_18006FF70)
        : (FARPROC)(ProcAddress = GetProcAddress(Library, "WTSQuerySessionInformationW"),
                    qword_18006FF70 = (__int64)ProcAddress),
          bWTSQuerySessionInformationProbed = 1,
          ProcAddress) )
    {
      if ( ((unsigned int (__fastcall *)(_QWORD, __int64, __int64, void **, char *))ProcAddress)(
             0,
             0xFFFFFFFFLL,
             4,
             &v35,
             &v32) )
      {
        v7 = *(_DWORD *)v35;
        CLRWTSFreeMemory(v35);
        if ( (unsigned int)CLRWTSEnumerateSessions(v9, v8, v10, &v34, &v33) )
        {
          this[2].BatteryFullLifeTime = 0;
          if ( v33 )
          {
            v11 = v34;
            v12 = v33;
            do
            {
              if ( v11->State == WTSActive && v11->SessionId != v7 )
                this[2].BatteryFullLifeTime = 1;
              ++v11;
              --v12;
            }
            while ( v12 );
          }
          CLRWTSFreeMemory(v34);
        }
        this->BatteryLifeTime |= 0x80u;
      }
    }
  }
  else
  {
    this->BatteryLifeTime |= 0x80u;
    this[2].BatteryFullLifeTime = 0;
  }
  if ( SystemParametersInfoW(0x72u, 0, &this[2].BatteryLifeTime, 0) )
    this->BatteryLifeTime |= 0x40u;
  v13 = (FARPROC)qword_180070860;
  if ( qword_180070860
    || ((v14 = LoadLibraryExW(L"powrprof.dll", 0, 0)) == 0
      ? (v13 = (FARPROC)qword_180070860)
      : (FARPROC)(v13 = GetProcAddress(v14, "CallNtPowerInformation"), qword_180070860 = (__int64)v13),
        v13) )
  {
    if ( !((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD, struct _SYSTEM_POWER_STATUS *, int))v13)(
            16,
            0,
            0,
            &this[2],
            4) )
      this->BatteryLifeTime |= 0x20u;
  }
  if ( NGENService::ConfigDebugLog(v16, v15) )
  {
    if ( byte_180070844 )
    {
      ConfigValue = dword_180070840;
    }
    else
    {
      ConfigValue = CLRConfig::GetConfigValue(
                      (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_NGENServiceIdleDebugInfo,
                      (bool)v17,
                      (bool *)&v33);
      dword_180070840 = ConfigValue;
      byte_180070844 = 1;
    }
    if ( ConfigValue )
    {
      NGENService::DebugLog((NGENService *)L"System snapshot: \n", v17);
      NGENService::DebugLog(
        (NGENService *)L"\tSnapshot time: %u \n",
        (const unsigned __int16 *)*(unsigned int *)&this->ACLineStatus);
      NGENService::DebugLog(
        (NGENService *)L"\tSnapshot time: %uh %um %us\n",
        (const unsigned __int16 *)(*(_DWORD *)&this->ACLineStatus / 0x36EE80u),
        *(_DWORD *)&this->ACLineStatus / 0xEA60u % 0x3C,
        *(_DWORD *)&this->ACLineStatus / 0x3E8u % 0x3C);
      if ( (this->BatteryLifeTime & 1) != 0 )
        NGENService::DebugLog(
          (NGENService *)L"\tNo input in last %uh %um %us\n",
          (const unsigned __int16 *)(this->BatteryFullLifeTime / 0x36EE80),
          this->BatteryFullLifeTime / 0xEA60 % 0x3C,
          this->BatteryFullLifeTime / 0x3E8 % 0x3C);
      else
        NGENService::DebugLog((NGENService *)L"\tLast Input time: N/A\n", v19);
      v21 = L"NO";
      if ( (this->BatteryLifeTime & 8) != 0 )
      {
        ACLineStatus = this[1].ACLineStatus;
        if ( ACLineStatus || this[1].BatteryLifePercent == 0xFF )
          BatteryLifePercent = 0xFFFFFFFFLL;
        else
          BatteryLifePercent = this[1].BatteryLifePercent;
        v24 = L"YES";
        if ( ACLineStatus )
          v24 = L"NO";
        NGENService::DebugLog((NGENService *)L"\tRunning on battery: %s (%i%% left)\n", v24, BatteryLifePercent);
      }
      else
      {
        NGENService::DebugLog((NGENService *)L"\tRunning on battery: N/A\n", v20);
      }
      if ( (this->BatteryLifeTime & 0x40) != 0 )
      {
        v26 = L"NO";
        if ( this[2].BatteryLifeTime )
          v26 = L"YES";
        NGENService::DebugLog((NGENService *)L"\tScreen saver running: %s\n", v26);
      }
      else
      {
        NGENService::DebugLog((NGENService *)L"\tScreen saver running: N/A\n", v25);
      }
      if ( SLOBYTE(this->BatteryLifeTime) >= 0 )
      {
        NGENService::DebugLog((NGENService *)L"\tOther active Terminal Server sessions: N/A\n", v27);
      }
      else
      {
        v28 = L"NO";
        if ( this[2].BatteryFullLifeTime )
          v28 = L"YES";
        NGENService::DebugLog((NGENService *)L"\tOther active Terminal Server sessions: %s\n", v28);
      }
      if ( (this->BatteryLifeTime & 0x100) != 0 )
      {
        v30 = L"NO";
        if ( *(_DWORD *)&this[3].ACLineStatus )
          v30 = L"YES";
        NGENService::DebugLog((NGENService *)L"\tDisk is Idle: %s\n", v30);
      }
      else
      {
        NGENService::DebugLog((NGENService *)L"\tDisk is Idle: N/A\n", v29);
      }
      if ( (this->BatteryLifeTime & 0x20) != 0 )
      {
        if ( (this[2].ACLineStatus & 2) != 0 )
          v21 = L"YES";
        NGENService::DebugLog((NGENService *)L"\tES_DISPLAY_REQUIRED: %s\n", v21);
      }
      else
      {
        NGENService::DebugLog((NGENService *)L"\tES_DISPLAY_REQUIRED: N/A\n", v31);
      }
    }
  }
}

```

## disassembly

```asm
0x180007130  mov     [rsp+arg_8], edx
0x180007134  push    rbx
0x180007135  push    rbp
0x180007136  push    rsi
0x180007137  push    rdi
0x180007138  push    r14
0x18000713a  sub     rsp, 30h
0x18000713e  and     dword ptr [rcx+4], 0FFFFFE00h
0x180007145  mov     rbx, rcx
0x180007148  call    cs:__imp_GetTickCount
0x18000714e  lea     rbp, [rbx+8]
0x180007152  mov     [rbx], eax
0x180007154  mov     rdx, rbp; unsigned int
0x180007157  mov     ecx, eax; this
0x180007159  call    ?IdleGetLastInputInfo@NGENService@@YAHKPEAK@Z; NGENService::IdleGetLastInputInfo(ulong,ulong *)
0x18000715e  test    eax, eax
0x180007160  jz      short loc_180007166
0x180007162  or      dword ptr [rbx+4], 1
0x180007166  lea     rcx, [rbx+0Ch]; lpSystemPowerStatus
0x18000716a  call    cs:__imp_GetSystemPowerStatus
0x180007170  test    eax, eax
0x180007172  jz      short loc_180007178
0x180007174  or      dword ptr [rbx+4], 8
0x180007178  cmp     cs:?g_fRunningOnTS@NGENService@@3HA, 0; int NGENService::g_fRunningOnTS
0x18000717f  jnz     short loc_18000718F
0x180007181  bts     dword ptr [rbx+4], 7
0x180007186  and     dword ptr [rbx+20h], 0
0x18000718a  jmp     loc_180007273
0x18000718f  mov     rax, cs:qword_18006FF70
0x180007196  test    rax, rax
0x180007199  jnz     short loc_1800071EE
0x18000719b  cmp     cs:?bWTSQuerySessionInformationProbed@@3_NA, al; bool bWTSQuerySessionInformationProbed
0x1800071a1  jnz     loc_180007273
0x1800071a7  xor     r8d, r8d; dwFlags
0x1800071aa  lea     rcx, aWtsapi32Dll; "Wtsapi32.dll"
0x1800071b1  xor     edx, edx; hFile
0x1800071b3  call    cs:__imp_LoadLibraryExW
0x1800071b9  test    rax, rax
0x1800071bc  jz      short loc_1800071D7
0x1800071be  lea     rdx, aWtsquerysessio; "WTSQuerySessionInformationW"
0x1800071c5  mov     rcx, rax; hModule
0x1800071c8  call    cs:__imp_GetProcAddress
0x1800071ce  mov     cs:qword_18006FF70, rax
0x1800071d5  jmp     short loc_1800071DE
0x1800071d7  mov     rax, cs:qword_18006FF70
0x1800071de  mov     cs:?bWTSQuerySessionInformationProbed@@3_NA, 1; bool bWTSQuerySessionInformationProbed
0x1800071e5  test    rax, rax
0x1800071e8  jz      loc_180007273
0x1800071ee  lea     rcx, [rsp+58h+arg_0]
0x1800071f3  mov     r8d, 4
0x1800071f9  mov     [rsp+58h+var_38], rcx
0x1800071fe  lea     r9, [rsp+58h+arg_18]
0x180007203  xor     ecx, ecx
0x180007205  or      edx, 0FFFFFFFFh
0x180007208  call    cs:__guard_dispatch_icall_fptr
0x18000720e  test    eax, eax
0x180007210  jz      short loc_180007273
0x180007212  mov     rcx, [rsp+58h+arg_18]; void *
0x180007217  mov     edi, [rcx]
0x180007219  call    ?CLRWTSFreeMemory@@YAHPEAX@Z; CLRWTSFreeMemory(void *)
0x18000721e  lea     rax, [rsp+58h+arg_8]
0x180007223  lea     r9, [rsp+58h+arg_10]; struct _WTS_SESSION_INFOW **
0x180007228  mov     [rsp+58h+var_38], rax; unsigned int *
0x18000722d  call    ?CLRWTSEnumerateSessions@@YAHPEAXKKPEAPEAU_WTS_SESSION_INFOW@@PEAK@Z; CLRWTSEnumerateSessions(void *,ulong,ulong,_WTS_SESSION_INFOW * *,ulong *)
0x180007232  test    eax, eax
0x180007234  jz      short loc_18000726E
0x180007236  and     dword ptr [rbx+20h], 0
0x18000723a  mov     ecx, [rsp+58h+arg_8]
0x18000723e  test    ecx, ecx
0x180007240  jz      short loc_180007264
0x180007242  mov     rax, [rsp+58h+arg_10]
0x180007247  mov     edx, ecx
0x180007249  cmp     dword ptr [rax+10h], 0
0x18000724d  jnz     short loc_18000725A
0x18000724f  cmp     [rax], edi
0x180007251  jz      short loc_18000725A
0x180007253  mov     dword ptr [rbx+20h], 1
0x18000725a  add     rax, 18h
0x18000725e  sub     rdx, 1
0x180007262  jnz     short loc_180007249
0x180007264  mov     rcx, [rsp+58h+arg_10]; void *
0x180007269  call    ?CLRWTSFreeMemory@@YAHPEAX@Z; CLRWTSFreeMemory(void *)
0x18000726e  bts     dword ptr [rbx+4], 7
0x180007273  xor     edx, edx; uiParam
0x180007275  lea     r8, [rbx+1Ch]; pvParam
0x180007279  xor     r9d, r9d; fWinIni
0x18000727c  lea     ecx, [rdx+72h]; uiAction
0x18000727f  call    cs:__imp_SystemParametersInfoW
0x180007285  test    eax, eax
0x180007287  jz      short loc_18000728D
0x180007289  or      dword ptr [rbx+4], 40h
0x18000728d  mov     rax, cs:qword_180070860
0x180007294  test    rax, rax
0x180007297  jnz     short loc_1800072D5
0x180007299  xor     r8d, r8d; dwFlags
0x18000729c  lea     rcx, aPowrprofDll; "powrprof.dll"
0x1800072a3  xor     edx, edx; hFile
0x1800072a5  call    cs:__imp_LoadLibraryExW
0x1800072ab  test    rax, rax
0x1800072ae  jz      short loc_1800072C9
0x1800072b0  lea     rdx, aCallntpowerinf; "CallNtPowerInformation"
0x1800072b7  mov     rcx, rax; hModule
0x1800072ba  call    cs:__imp_GetProcAddress
0x1800072c0  mov     cs:qword_180070860, rax
0x1800072c7  jmp     short loc_1800072D0
0x1800072c9  mov     rax, cs:qword_180070860
0x1800072d0  test    rax, rax
0x1800072d3  jz      short loc_1800072F7
0x1800072d5  xor     edx, edx
0x1800072d7  mov     dword ptr [rsp+58h+var_38], 4
0x1800072df  lea     r9, [rbx+18h]
0x1800072e3  xor     r8d, r8d
0x1800072e6  lea     ecx, [rdx+10h]
0x1800072e9  call    cs:__guard_dispatch_icall_fptr
0x1800072ef  test    eax, eax
0x1800072f1  jnz     short loc_1800072F7
0x1800072f3  or      dword ptr [rbx+4], 20h
0x1800072f7  call    ?ConfigDebugLog@NGENService@@YAKXZ; NGENService::ConfigDebugLog(void)
0x1800072fc  test    eax, eax
0x1800072fe  jz      loc_18000750B
0x180007304  cmp     cs:byte_180070844, 0
0x18000730b  jnz     short loc_18000732D
0x18000730d  lea     r8, [rsp+58h+arg_8]; bool *
0x180007312  lea     rcx, ?UNSUPPORTED_NGENServiceIdleDebugInfo@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x180007319  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x18000731e  mov     cs:dword_180070840, eax
0x180007324  mov     cs:byte_180070844, 1
0x18000732b  jmp     short loc_180007333
0x18000732d  mov     eax, cs:dword_180070840
0x180007333  test    eax, eax
0x180007335  jz      loc_18000750B
0x18000733b  lea     rcx, aSystemSnapshot; "System snapshot: \n"
0x180007342  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180007347  mov     edx, [rbx]; unsigned __int16 *
0x180007349  lea     rcx, aSnapshotTimeU; "\tSnapshot time: %u \n"
0x180007350  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180007355  mov     eax, 10624DD3h
0x18000735a  lea     rcx, aSnapshotTimeUh; "\tSnapshot time: %uh %um %us\n"
0x180007361  mul     dword ptr [rbx]
0x180007363  mov     edi, 88888889h
0x180007368  mov     r9d, edx
0x18000736b  mov     eax, edi
0x18000736d  shr     r9d, 6
0x180007371  mul     r9d
0x180007374  shr     edx, 5
0x180007377  imul    eax, edx, 3Ch ; '<'
0x18000737a  sub     r9d, eax
0x18000737d  mov     eax, 45E7B273h
0x180007382  mul     dword ptr [rbx]
0x180007384  mov     eax, edi
0x180007386  mov     r8d, edx
0x180007389  shr     r8d, 0Eh
0x18000738d  mul     r8d
0x180007390  shr     edx, 5
0x180007393  imul    eax, edx, 3Ch ; '<'
0x180007396  sub     r8d, eax
0x180007399  mov     eax, 95217CB1h
0x18000739e  mul     dword ptr [rbx]
0x1800073a0  shr     edx, 15h; unsigned __int16 *
0x1800073a3  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800073a8  test    byte ptr [rbx+4], 1
0x1800073ac  jz      short loc_180007401
0x1800073ae  mov     eax, 10624DD3h
0x1800073b3  mul     dword ptr [rbp+0]
0x1800073b6  mov     eax, edi
0x1800073b8  mov     r9d, edx
0x1800073bb  shr     r9d, 6
0x1800073bf  mul     r9d
0x1800073c2  mov     eax, 45E7B273h
0x1800073c7  shr     edx, 5
0x1800073ca  imul    ecx, edx, 3Ch ; '<'
0x1800073cd  mul     dword ptr [rbp+0]
0x1800073d0  sub     r9d, ecx
0x1800073d3  mov     eax, edi
0x1800073d5  mov     r8d, edx
0x1800073d8  shr     r8d, 0Eh
0x1800073dc  mul     r8d
0x1800073df  mov     eax, 95217CB1h
0x1800073e4  shr     edx, 5
0x1800073e7  imul    ecx, edx, 3Ch ; '<'
0x1800073ea  mul     dword ptr [rbp+0]
0x1800073ed  sub     r8d, ecx
0x1800073f0  lea     rcx, aNoInputInLastU; "\tNo input in last %uh %um %us\n"
0x1800073f7  shr     edx, 15h; unsigned __int16 *
0x1800073fa  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800073ff  jmp     short loc_18000740D
0x180007401  lea     rcx, aLastInputTimeN; "\tLast Input time: N/A\n"
0x180007408  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18000740d  test    byte ptr [rbx+4], 8
0x180007411  lea     rdi, aNo; "NO"
0x180007418  lea     rbp, aYes; "YES"
0x18000741f  jz      short loc_180007450
0x180007421  mov     al, [rbx+0Ch]
0x180007424  test    al, al
0x180007426  jnz     short loc_180007435
0x180007428  cmp     byte ptr [rbx+0Eh], 0FFh
0x18000742c  jz      short loc_180007435
0x18000742e  movzx   r8d, byte ptr [rbx+0Eh]
0x180007433  jmp     short loc_180007439
0x180007435  or      r8d, 0FFFFFFFFh
0x180007439  test    al, al
0x18000743b  lea     rcx, aRunningOnBatte; "\tRunning on battery: %s (%i%% left)\n"
0x180007442  mov     rdx, rbp
0x180007445  cmovnz  rdx, rdi; unsigned __int16 *
0x180007449  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18000744e  jmp     short loc_18000745C
0x180007450  lea     rcx, aRunningOnBatte_0; "\tRunning on battery: N/A\n"
0x180007457  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18000745c  test    byte ptr [rbx+4], 40h
0x180007460  jz      short loc_18000747B
0x180007462  cmp     dword ptr [rbx+1Ch], 0
0x180007466  lea     rcx, aScreenSaverRun_0; "\tScreen saver running: %s\n"
0x18000746d  mov     rdx, rdi
0x180007470  cmovnz  rdx, rbp; unsigned __int16 *
0x180007474  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180007479  jmp     short loc_180007487
0x18000747b  lea     rcx, aScreenSaverRun; "\tScreen saver running: N/A\n"
0x180007482  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180007487  test    byte ptr [rbx+4], 80h
0x18000748b  jz      short loc_1800074A6
0x18000748d  cmp     dword ptr [rbx+20h], 0
0x180007491  lea     rcx, aOtherActiveTer_0; "\tOther active Terminal Server sessions"...
0x180007498  mov     rdx, rdi
0x18000749b  cmovnz  rdx, rbp; unsigned __int16 *
0x18000749f  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800074a4  jmp     short loc_1800074B2
0x1800074a6  lea     rcx, aOtherActiveTer; "\tOther active Terminal Server sessions"...
0x1800074ad  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800074b2  test    dword ptr [rbx+4], 100h
0x1800074b9  jz      short loc_1800074D4
0x1800074bb  cmp     dword ptr [rbx+24h], 0
0x1800074bf  lea     rcx, aDiskIsIdleS; "\tDisk is Idle: %s\n"
0x1800074c6  mov     rdx, rdi
0x1800074c9  cmovnz  rdx, rbp; unsigned __int16 *
0x1800074cd  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800074d2  jmp     short loc_1800074E0
0x1800074d4  lea     rcx, aDiskIsIdleNA; "\tDisk is Idle: N/A\n"
0x1800074db  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800074e0  test    byte ptr [rbx+4], 20h
0x1800074e4  jz      short loc_1800074FF
0x1800074e6  test    byte ptr [rbx+18h], 2
0x1800074ea  lea     rcx, aEsDisplayRequi_0; "\tES_DISPLAY_REQUIRED: %s\n"
0x1800074f1  cmovnz  rdi, rbp
0x1800074f5  mov     rdx, rdi; unsigned __int16 *
0x1800074f8  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800074fd  jmp     short loc_18000750B
0x1800074ff  lea     rcx, aEsDisplayRequi; "\tES_DISPLAY_REQUIRED: N/A\n"
0x180007506  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18000750b  add     rsp, 30h
0x18000750f  pop     r14
0x180007511  pop     rdi
0x180007512  pop     rsi
0x180007513  pop     rbp
0x180007514  pop     rbx
0x180007515  retn
```
