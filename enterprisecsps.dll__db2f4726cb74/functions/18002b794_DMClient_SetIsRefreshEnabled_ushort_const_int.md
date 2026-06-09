# DMClient::SetIsRefreshEnabled(ushort const *,int)

- ea: `0x18002b794`
- end: `0x18002b8ed`
- name: `?SetIsRefreshEnabled@DMClient@@YAJPEBGH@Z`
- size: `345`
- prototype: `__int64 __fastcall(DMClient *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180038960`

## callees

- `0x18000d4d4`
- `0x180025ac0`
- `0x180028488`
- `0x18002b794`
- `0x18002dcc8`
- `0x1800f7338`
- `0x1800f7de0`
- `0x1800f7e88`
- `0x1800f7efc`
- `0x1800f7fa4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002b832`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002b832`
- `DMCmnUtils!DmEnableTask` at `0x18002b87d`
- `DMCmnUtils!DmEnableTask` at `0x18002b87d`
- `DMCmnUtils!DmDisableTask` at `0x18002b8b2`
- `DMCmnUtils!DmDisableTask` at `0x18002b8b2`

## string_xrefs

- `0x18002b86c`: `Schedule created by dm client to refresh settings`
- `0x18002b8a1`: `Schedule created by dm client to refresh settings`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DMClient::SetIsRefreshEnabled(DMClient *this, const unsigned __int16 *a2)
{
  int v2; // esi
  unsigned int v4; // ebx
  int v5; // r9d
  int ConfigRefreshKey; // eax
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  LSTATUS v9; // eax
  CConfigRefreshLogger *Logger; // rcx
  CConfigRefreshLogger *v11; // rax
  CConfigRefreshLogger *v12; // rax
  int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  BOOL Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v2 = (int)a2;
  hKey = 0;
  if ( !this )
  {
    v4 = -2147024809;
    goto LABEL_13;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  ConfigRefreshKey = DMClient::GetConfigRefreshKey(this, (const unsigned __int16 *)&hKey, (HKEY *)1, v5);
  v4 = ConfigRefreshKey;
  if ( ConfigRefreshKey < 0 )
  {
    v7 = (unsigned int)ConfigRefreshKey;
    v8 = 5604;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclienttools.cpp",
      (const char *)v7,
      lpData);
    goto LABEL_13;
  }
  Data = v2 != 0;
  v9 = RegSetValueExW(hKey, L"Enabled", 0, 4u, (const BYTE *)&Data, 4u);
  v4 = v9;
  if ( v9 > 0 )
    v4 = (unsigned __int16)v9 | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
  {
    v7 = v4;
    v8 = 5614;
    goto LABEL_5;
  }
  Logger = CConfigRefreshLogger::GetLogger();
  if ( v2 )
  {
    CConfigRefreshLogger::LogConfigRefreshTaskEnabledStart(Logger);
    v4 = DmEnableTask(
           L"\\Microsoft\\Windows\\EnterpriseMgmtNonCritical",
           (const unsigned __int16 *)this,
           L"Schedule created by dm client to refresh settings");
    v11 = CConfigRefreshLogger::GetLogger();
    CConfigRefreshLogger::LogConfigRefreshTaskEnabledEnd(v11, v4);
  }
  else
  {
    CConfigRefreshLogger::LogConfigRefreshTaskDisabledStart(Logger);
    v4 = DmDisableTask(
           L"\\Microsoft\\Windows\\EnterpriseMgmtNonCritical",
           (const unsigned __int16 *)this,
           L"Schedule created by dm client to refresh settings");
    v12 = CConfigRefreshLogger::GetLogger();
    CConfigRefreshLogger::LogConfigRefreshTaskDisabledEnd(v12, v4);
  }
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v4;
}

```

## disassembly

```asm
0x18002b794  mov     [rsp+arg_8], rbx
0x18002b799  mov     [rsp+arg_18], rsi
0x18002b79e  push    rdi
0x18002b79f  sub     rsp, 30h
0x18002b7a3  mov     esi, edx
0x18002b7a5  mov     rdi, rcx
0x18002b7a8  mov     [rsp+38h+hKey], 0
0x18002b7b1  test    rcx, rcx
0x18002b7b4  jnz     short loc_18002B7C0
0x18002b7b6  mov     ebx, 80070057h
0x18002b7bb  jmp     loc_18002B8D0
0x18002b7c0  xor     edx, edx
0x18002b7c2  lea     rcx, [rsp+38h+hKey]
0x18002b7c7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002b7cc  mov     r8d, 1; HKEY *
0x18002b7d2  lea     rdx, [rsp+38h+hKey]; unsigned __int16 *
0x18002b7d7  mov     rcx, rdi; this
0x18002b7da  call    ?GetConfigRefreshKey@DMClient@@YAJPEBGPEAPEAUHKEY__@@H@Z; DMClient::GetConfigRefreshKey(ushort const *,HKEY__ * *,int)
0x18002b7df  mov     ebx, eax
0x18002b7e1  test    eax, eax
0x18002b7e3  jns     short loc_18002B803
0x18002b7e5  mov     r9d, eax; char *
0x18002b7e8  mov     edx, 15E4h; void *
0x18002b7ed  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18002b7f4  mov     rcx, [rsp+38h]; this
0x18002b7f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b7fe  jmp     loc_18002B8D0
0x18002b803  xor     eax, eax
0x18002b805  test    esi, esi
0x18002b807  setnz   al
0x18002b80a  mov     [rsp+38h+Data], eax
0x18002b80e  mov     r9d, 4; dwType
0x18002b814  mov     [rsp+38h+cbData], r9d; cbData
0x18002b819  lea     rax, [rsp+38h+Data]
0x18002b81e  mov     [rsp+38h+lpData], rax; lpData
0x18002b823  xor     r8d, r8d; Reserved
0x18002b826  lea     rdx, aEnabled; "Enabled"
0x18002b82d  mov     rcx, [rsp+38h+hKey]; hKey
0x18002b832  call    cs:__imp_RegSetValueExW
0x18002b839  nop     dword ptr [rax+rax+00h]
0x18002b83e  mov     ebx, eax
0x18002b840  test    eax, eax
0x18002b842  jle     short loc_18002B84D
0x18002b844  movzx   ebx, ax
0x18002b847  or      ebx, 80070000h
0x18002b84d  test    ebx, ebx
0x18002b84f  jns     short loc_18002B85B
0x18002b851  mov     r9d, ebx
0x18002b854  mov     edx, 15EEh
0x18002b859  jmp     short loc_18002B7ED
0x18002b85b  call    ?GetLogger@CConfigRefreshLogger@@SAPEAV1@XZ; CConfigRefreshLogger::GetLogger(void)
0x18002b860  mov     rcx, rax; this
0x18002b863  test    esi, esi
0x18002b865  jz      short loc_18002B89C
0x18002b867  call    ?LogConfigRefreshTaskEnabledStart@CConfigRefreshLogger@@QEAAXXZ; CConfigRefreshLogger::LogConfigRefreshTaskEnabledStart(void)
0x18002b86c  lea     r8, aScheduleCreate; "Schedule created by dm client to refres"...
0x18002b873  mov     rdx, rdi
0x18002b876  lea     rcx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmtNon"...
0x18002b87d  call    cs:__imp_?DmEnableTask@@YAJPEBG00@Z; DmEnableTask(ushort const *,ushort const *,ushort const *)
0x18002b884  nop     dword ptr [rax+rax+00h]
0x18002b889  mov     ebx, eax
0x18002b88b  call    ?GetLogger@CConfigRefreshLogger@@SAPEAV1@XZ; CConfigRefreshLogger::GetLogger(void)
0x18002b890  mov     edx, ebx; int
0x18002b892  mov     rcx, rax; this
0x18002b895  call    ?LogConfigRefreshTaskEnabledEnd@CConfigRefreshLogger@@QEAAXJ@Z; CConfigRefreshLogger::LogConfigRefreshTaskEnabledEnd(long)
0x18002b89a  jmp     short loc_18002B8D0
0x18002b89c  call    ?LogConfigRefreshTaskDisabledStart@CConfigRefreshLogger@@QEAAXXZ; CConfigRefreshLogger::LogConfigRefreshTaskDisabledStart(void)
0x18002b8a1  lea     r8, aScheduleCreate; "Schedule created by dm client to refres"...
0x18002b8a8  mov     rdx, rdi
0x18002b8ab  lea     rcx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmtNon"...
0x18002b8b2  call    cs:__imp_?DmDisableTask@@YAJPEBG00@Z; DmDisableTask(ushort const *,ushort const *,ushort const *)
0x18002b8b9  nop     dword ptr [rax+rax+00h]
0x18002b8be  mov     ebx, eax
0x18002b8c0  call    ?GetLogger@CConfigRefreshLogger@@SAPEAV1@XZ; CConfigRefreshLogger::GetLogger(void)
0x18002b8c5  mov     edx, ebx; int
0x18002b8c7  mov     rcx, rax; this
0x18002b8ca  call    ?LogConfigRefreshTaskDisabledEnd@CConfigRefreshLogger@@QEAAXJ@Z; CConfigRefreshLogger::LogConfigRefreshTaskDisabledEnd(long)
0x18002b8cf  nop
0x18002b8d0  lea     rcx, [rsp+38h+hKey]
0x18002b8d5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002b8da  mov     eax, ebx
0x18002b8dc  mov     rbx, [rsp+38h+arg_8]
0x18002b8e1  mov     rsi, [rsp+38h+arg_18]
0x18002b8e6  add     rsp, 30h
0x18002b8ea  pop     rdi
0x18002b8eb  retn
```
