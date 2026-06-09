# NcsiConfigData::MonitorRegistry(void *)

- ea: `0x180052660`
- end: `0x180052917`
- name: `?MonitorRegistry@NcsiConfigData@@CAIPEAX@Z`
- size: `695`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180010200`
- `0x180011a58`
- `0x180021e7c`
- `0x18002d6a0`
- `0x180047240`
- `0x180052660`
- `0x1800529ac`
- `0x1800532d0`
- `0x180053448`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052721`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052721`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800527af`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800527af`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800527d6`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800527d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NcsiConfigData::MonitorRegistry(void *a1)
{
  __int64 v1; // rcx
  LPCWSTR *v2; // rbx
  const WCHAR *v3; // rdx
  LSTATUS v4; // eax
  int v5; // edx
  int v6; // r8d
  char v7; // bl
  unsigned int v8; // eax
  __int64 v9; // r8
  bool v10; // dl
  NcsiConfigData *v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v16; // rdx
  HANDLE Handles[2]; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-18h] BYREF

  v1 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
    v1 = WPP_GLOBAL_Control;
  }
  if ( (char *)g_registryMonitorEvent - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( (_UNKNOWN *)v1 == &WPP_GLOBAL_Control || (*(_BYTE *)(v1 + 28) & 0x10) == 0 || *(_BYTE *)(v1 + 25) < 2u )
      return 0xFFFFFFFFLL;
    v16 = 19;
LABEL_53:
    WPP_SF_(*(_QWORD *)(v1 + 16), v16, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
    return 0xFFFFFFFFLL;
  }
  if ( (char *)g_registryNotificationEvent - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( (_UNKNOWN *)v1 == &WPP_GLOBAL_Control || (*(_BYTE *)(v1 + 28) & 0x10) == 0 || *(_BYTE *)(v1 + 25) < 2u )
      return 0xFFFFFFFFLL;
    v16 = 20;
    goto LABEL_53;
  }
  hKey = 0;
  v2 = &g_ncsiRegistry;
  v3 = (const WCHAR *)&g_ncsiRegistry;
  if ( (unsigned __int64)qword_18009AA78 > 7 )
    v3 = g_ncsiRegistry;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  if ( v4 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      if ( (unsigned __int64)qword_18009AA78 > 7 )
        LODWORD(v2) = (_DWORD)g_ncsiRegistry;
      WPP_SF_Sl(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v5, v6, (_DWORD)v2, v4);
    }
  }
  else
  {
    Handles[0] = g_registryMonitorEvent;
    Handles[1] = g_registryNotificationEvent;
LABEL_17:
    v7 = 1;
    while ( 1 )
    {
      if ( v7 )
      {
        v8 = RegNotifyChangeKeyValue(hKey, 1, 5u, g_registryMonitorEvent, 1);
        if ( v8 )
          break;
      }
      if ( !CheckIfClientPresent() )
      {
        v13 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
        {
          v14 = 23;
LABEL_43:
          WPP_SF_(*(_QWORD *)(v13 + 16), v14, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
        }
LABEL_44:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 4294967294LL;
      }
      WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( !CheckIfClientPresent() )
      {
        v13 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
        {
          v14 = 24;
          goto LABEL_43;
        }
        goto LABEL_44;
      }
      if ( !(_DWORD)v12 )
      {
        NcsiConfigData::QueryRegParamRegistry(v11, v10);
        goto LABEL_17;
      }
      if ( (_DWORD)v12 != 1 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
        {
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids, v12);
        }
        v7 = 0;
      }
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, v9, v8);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180052660  mov     [rsp+arg_0], rbx
0x180052665  mov     [rsp+arg_8], rbp
0x18005266a  push    rsi
0x18005266b  sub     rsp, 50h
0x18005266f  mov     rax, cs:__security_cookie
0x180052676  xor     rax, rsp
0x180052679  mov     [rsp+58h+var_10], rax
0x18005267e  lea     rsi, WPP_GLOBAL_Control
0x180052685  lea     rbp, WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids
0x18005268c  mov     rcx, cs:WPP_GLOBAL_Control
0x180052693  cmp     rcx, rsi
0x180052696  jz      short loc_1800526BC
0x180052698  test    byte ptr [rcx+1Ch], 10h
0x18005269c  jz      short loc_1800526BC
0x18005269e  cmp     byte ptr [rcx+19h], 5
0x1800526a2  jb      short loc_1800526BC
0x1800526a4  mov     edx, 12h
0x1800526a9  mov     r8, rbp
0x1800526ac  mov     rcx, [rcx+10h]
0x1800526b0  call    WPP_SF_
0x1800526b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800526bc  mov     rax, cs:?g_registryMonitorEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryMonitorEvent
0x1800526c3  dec     rax
0x1800526c6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800526ca  ja      loc_1800528D5
0x1800526d0  mov     rax, cs:?g_registryNotificationEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryNotificationEvent
0x1800526d7  dec     rax
0x1800526da  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800526de  ja      loc_1800528BD
0x1800526e4  mov     [rsp+58h+hKey], 0
0x1800526ed  lea     rbx, ?g_ncsiRegistry@@3VNcsiRegistry@@A; NcsiRegistry g_ncsiRegistry
0x1800526f4  mov     rdx, rbx
0x1800526f7  cmp     cs:qword_18009AA78, 7
0x1800526ff  cmova   rdx, cs:?g_ncsiRegistry@@3VNcsiRegistry@@A; lpSubKey
0x180052707  lea     rax, [rsp+58h+hKey]
0x18005270c  mov     [rsp+58h+phkResult], rax; phkResult
0x180052711  mov     r9d, 20019h; samDesired
0x180052717  xor     r8d, r8d; ulOptions
0x18005271a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180052721  call    cs:__imp_RegOpenKeyExW
0x180052727  test    eax, eax
0x180052729  jz      short loc_180052774
0x18005272b  mov     rcx, cs:WPP_GLOBAL_Control
0x180052732  cmp     rcx, rsi
0x180052735  jz      loc_180052854
0x18005273b  test    byte ptr [rcx+1Ch], 10h
0x18005273f  jz      loc_180052854
0x180052745  cmp     byte ptr [rcx+19h], 2
0x180052749  jb      loc_180052854
0x18005274f  cmp     cs:qword_18009AA78, 7
0x180052757  cmova   rbx, cs:?g_ncsiRegistry@@3VNcsiRegistry@@A; NcsiRegistry g_ncsiRegistry
0x18005275f  mov     dword ptr [rsp+58h+phkResult], eax
0x180052763  mov     r9, rbx
0x180052766  mov     rcx, [rcx+10h]
0x18005276a  call    WPP_SF_Sl
0x18005276f  jmp     loc_180052854
0x180052774  mov     rax, cs:?g_registryMonitorEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryMonitorEvent
0x18005277b  mov     [rsp+58h+Handles], rax
0x180052780  mov     rax, cs:?g_registryNotificationEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_registryNotificationEvent
0x180052787  mov     [rsp+58h+var_20], rax
0x18005278c  mov     bl, 1
0x18005278e  test    bl, bl
0x180052790  jz      short loc_1800527B9
0x180052792  mov     dword ptr [rsp+58h+phkResult], 1; fAsynchronous
0x18005279a  mov     r9, cs:?g_registryMonitorEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; hEvent
0x1800527a1  mov     edx, 1; bWatchSubtree
0x1800527a6  lea     r8d, [rdx+4]; dwNotifyFilter
0x1800527aa  mov     rcx, [rsp+58h+hKey]; hKey
0x1800527af  call    cs:__imp_RegNotifyChangeKeyValue
0x1800527b5  test    eax, eax
0x1800527b7  jnz     short loc_18005282A
0x1800527b9  call    ?CheckIfClientPresent@@YA_NXZ; CheckIfClientPresent(void)
0x1800527be  test    al, al
0x1800527c0  jz      loc_180052882
0x1800527c6  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800527ca  xor     r8d, r8d; bWaitAll
0x1800527cd  lea     rdx, [rsp+58h+Handles]; lpHandles
0x1800527d2  lea     ecx, [r8+2]; nCount
0x1800527d6  call    cs:__imp_WaitForMultipleObjects
0x1800527dc  mov     r9d, eax
0x1800527df  call    ?CheckIfClientPresent@@YA_NXZ; CheckIfClientPresent(void)
0x1800527e4  test    al, al
0x1800527e6  jz      short loc_180052863
0x1800527e8  test    r9d, r9d
0x1800527eb  jnz     short loc_1800527F4
0x1800527ed  call    ?QueryRegParamRegistry@NcsiConfigData@@QEAAX_N@Z; NcsiConfigData::QueryRegParamRegistry(bool)
0x1800527f2  jmp     short loc_18005278C
0x1800527f4  cmp     r9d, 1
0x1800527f8  jz      short loc_18005278E
0x1800527fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180052801  cmp     rcx, rsi
0x180052804  jz      short loc_180052823
0x180052806  test    byte ptr [rcx+1Ch], 10h
0x18005280a  jz      short loc_180052823
0x18005280c  cmp     byte ptr [rcx+19h], 3
0x180052810  jb      short loc_180052823
0x180052812  mov     edx, 19h
0x180052817  mov     r8, rbp
0x18005281a  mov     rcx, [rcx+10h]
0x18005281e  call    WPP_SF_d
0x180052823  xor     bl, bl
0x180052825  jmp     loc_18005278E
0x18005282a  mov     rcx, cs:WPP_GLOBAL_Control
0x180052831  cmp     rcx, rsi
0x180052834  jz      short loc_180052854
0x180052836  test    byte ptr [rcx+1Ch], 10h
0x18005283a  jz      short loc_180052854
0x18005283c  cmp     byte ptr [rcx+19h], 2
0x180052840  jb      short loc_180052854
0x180052842  mov     edx, 16h
0x180052847  mov     r9d, eax
0x18005284a  mov     rcx, [rcx+10h]
0x18005284e  call    WPP_SF_l
0x180052853  nop
0x180052854  lea     rcx, [rsp+58h+hKey]
0x180052859  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005285e  jmp     loc_1800528F7
0x180052863  mov     rcx, cs:WPP_GLOBAL_Control
0x18005286a  cmp     rcx, rsi
0x18005286d  jz      short loc_1800528AC
0x18005286f  test    byte ptr [rcx+1Ch], 10h
0x180052873  jz      short loc_1800528AC
0x180052875  cmp     byte ptr [rcx+19h], 5
0x180052879  jb      short loc_1800528AC
0x18005287b  mov     edx, 18h
0x180052880  jmp     short loc_18005289F
0x180052882  mov     rcx, cs:WPP_GLOBAL_Control
0x180052889  cmp     rcx, rsi
0x18005288c  jz      short loc_1800528AC
0x18005288e  test    byte ptr [rcx+1Ch], 10h
0x180052892  jz      short loc_1800528AC
0x180052894  cmp     byte ptr [rcx+19h], 5
0x180052898  jb      short loc_1800528AC
0x18005289a  mov     edx, 17h
0x18005289f  mov     r8, rbp
0x1800528a2  mov     rcx, [rcx+10h]
0x1800528a6  call    WPP_SF_
0x1800528ab  nop
0x1800528ac  lea     rcx, [rsp+58h+hKey]
0x1800528b1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800528b6  mov     eax, 0FFFFFFFEh
0x1800528bb  jmp     short loc_1800528FA
0x1800528bd  cmp     rcx, rsi
0x1800528c0  jz      short loc_1800528F7
0x1800528c2  test    byte ptr [rcx+1Ch], 10h
0x1800528c6  jz      short loc_1800528F7
0x1800528c8  cmp     byte ptr [rcx+19h], 2
0x1800528cc  jb      short loc_1800528F7
0x1800528ce  mov     edx, 14h
0x1800528d3  jmp     short loc_1800528EB
0x1800528d5  cmp     rcx, rsi
0x1800528d8  jz      short loc_1800528F7
0x1800528da  test    byte ptr [rcx+1Ch], 10h
0x1800528de  jz      short loc_1800528F7
0x1800528e0  cmp     byte ptr [rcx+19h], 2
0x1800528e4  jb      short loc_1800528F7
0x1800528e6  mov     edx, 13h
0x1800528eb  mov     r8, rbp
0x1800528ee  mov     rcx, [rcx+10h]
0x1800528f2  call    WPP_SF_
0x1800528f7  or      eax, 0FFFFFFFFh
0x1800528fa  mov     rcx, [rsp+58h+var_10]
0x1800528ff  xor     rcx, rsp; StackCookie
0x180052902  call    __security_check_cookie
0x180052907  mov     rbx, [rsp+58h+arg_0]
0x18005290c  mov     rbp, [rsp+58h+arg_8]
0x180052911  add     rsp, 50h
0x180052915  pop     rsi
0x180052916  retn
```
