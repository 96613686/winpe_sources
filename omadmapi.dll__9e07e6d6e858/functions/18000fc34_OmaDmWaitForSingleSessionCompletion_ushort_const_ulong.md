# OmaDmWaitForSingleSessionCompletion(ushort const *,ulong)

- ea: `0x18000fc34`
- end: `0x18000ff17`
- name: `?OmaDmWaitForSingleSessionCompletion@@YAHPEBGK@Z`
- size: `739`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fb50`

## callees

- `0x1800031b0`
- `0x180003db8`
- `0x180009bf4`
- `0x18000c974`
- `0x18000fc34`
- `0x180014514`
- `0x180014570`
- `0x1800174d0`
- `0x180018480`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fcfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ff04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fcfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ff04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fd53`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fd53`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18000fd89`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18000fd89`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000fe1a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000fe1a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000fe29`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000fe29`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fcba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fcba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fce7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000feee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fce7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000feee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fc66`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fdfa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fe7e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fc66`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fdfa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fe7e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall OmaDmWaitForSingleSessionCompletion(LPCWSTR lpSubKey, DWORD a2)
{
  DWORD TickCount; // r15d
  HANDLE EventW; // rbx
  HKEY *phkResult; // rax
  BOOL v8; // edi
  __int64 v9; // r8
  DWORD v10; // edx
  DWORD v11; // eax
  HKEY hKey; // [rsp+30h] [rbp-79h] BYREF
  HKEY v13; // [rsp+38h] [rbp-71h] BYREF
  HANDLE v14; // [rsp+40h] [rbp-69h] BYREF
  _DWORD v15[5]; // [rsp+50h] [rbp-59h] BYREF
  int v16; // [rsp+64h] [rbp-45h]
  _DWORD v17[4]; // [rsp+90h] [rbp-19h] BYREF
  HANDLE *v18; // [rsp+A0h] [rbp-9h]
  __int64 v19; // [rsp+A8h] [rbp-1h]
  HKEY *v20; // [rsp+B0h] [rbp+7h]
  __int64 v21; // [rsp+B8h] [rbp+Fh]

  TickCount = GetTickCount();
  v13 = 0;
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(WP_OMADMAPI_PROVIDER_Context, WaitingForSession, lpSubKey);
  if ( !lpSubKey )
    return 1;
  hKey = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  v14 = EventW;
  if ( !EventW )
  {
LABEL_7:
    if ( hKey )
      RegCloseKey(hKey);
    return 1;
  }
  if ( (int)GetAccountRootKeyByInitiationId(lpSubKey, &v13) < 0
    || (phkResult = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey),
        RegOpenKeyExW(v13, lpSubKey, 0, 0x20119u, phkResult)) )
  {
    CloseHandle(EventW);
    goto LABEL_7;
  }
  v8 = 0;
  memset_0(v17, 0, 0x40u);
  do
  {
    if ( RegNotifyChangeKeyValue(hKey, 1, 5u, EventW, 1) )
      break;
    memset_0(v17, 0, 0x40u);
    v17[0] = 64;
    if ( (int)OmaDmGetInitiationInfo(lpSubKey) < 0 )
      break;
    v8 = (unsigned int)(HIDWORD(v18) - 5) <= 1 || !HIDWORD(v18);
    OmaDmFreeInitiationInfo(v17);
    if ( v8 )
      break;
    if ( a2 == -1 )
    {
      v10 = -1;
    }
    else
    {
      v11 = GetTickCount() - TickCount;
      v10 = v11 > a2 ? 0 : a2 - v11;
    }
    WaitForSingleObject(EventW, v10);
    ResetEvent(EventW);
    memset_0(v15, 0, 0x40u);
    v15[0] = 64;
    if ( (int)OmaDmGetInitiationInfo(lpSubKey) < 0 )
      break;
    v8 = (unsigned int)(v16 - 5) <= 1 || !v16;
    OmaDmFreeInitiationInfo(v15);
    if ( v8 )
      break;
  }
  while ( GetTickCount() - TickCount < a2 );
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 2) != 0 )
  {
    LODWORD(v13) = HIDWORD(v18);
    LODWORD(v14) = v8;
    v18 = &v14;
    v19 = 4;
    v20 = &v13;
    v21 = 4;
    McGenEventWrite_EventWriteTransfer(WP_OMADMAPI_PROVIDER_Context, WaitingForSessionDone, v9, 3, v17);
  }
  CloseHandle(EventW);
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x18000fc34  mov     [rsp-8+arg_10], rbx
0x18000fc39  mov     [rsp-8+arg_18], rsi
0x18000fc3e  push    rbp
0x18000fc3f  push    rdi
0x18000fc40  push    r13
0x18000fc42  push    r14
0x18000fc44  push    r15
0x18000fc46  lea     rbp, [rsp-37h]
0x18000fc4b  sub     rsp, 0E0h
0x18000fc52  mov     rax, cs:__security_cookie
0x18000fc59  xor     rax, rsp
0x18000fc5c  mov     [rbp+57h+var_30], rax
0x18000fc60  mov     r14d, edx
0x18000fc63  mov     rsi, rcx
0x18000fc66  call    cs:__imp_GetTickCount
0x18000fc6d  nop     dword ptr [rax+rax+00h]
0x18000fc72  mov     r15d, eax
0x18000fc75  mov     [rbp+57h+var_C8], 0
0x18000fc7d  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 2
0x18000fc84  jz      short loc_18000FC9C
0x18000fc86  mov     r8, rsi
0x18000fc89  lea     rdx, WaitingForSession
0x18000fc90  lea     rcx, WP_OMADMAPI_PROVIDER_Context
0x18000fc97  call    McTemplateU0z_EventWriteTransfer
0x18000fc9c  mov     r13d, 1
0x18000fca2  test    rsi, rsi
0x18000fca5  jz      short loc_18000FD09
0x18000fca7  mov     [rbp+57h+hKey], 0
0x18000fcaf  xor     r9d, r9d; lpName
0x18000fcb2  xor     r8d, r8d; bInitialState
0x18000fcb5  mov     edx, r13d; bManualReset
0x18000fcb8  xor     ecx, ecx; lpEventAttributes
0x18000fcba  call    cs:__imp_CreateEventW
0x18000fcc1  nop     dword ptr [rax+rax+00h]
0x18000fcc6  mov     rbx, rax
0x18000fcc9  mov     [rbp+57h+var_C0], rax
0x18000fccd  test    rax, rax
0x18000fcd0  jnz     short loc_18000FCD4
0x18000fcd2  jmp     short loc_18000FCF4
0x18000fcd4  lea     rdx, [rbp+57h+var_C8]
0x18000fcd8  mov     rcx, rsi
0x18000fcdb  call    GetAccountRootKeyByInitiationId
0x18000fce0  test    eax, eax
0x18000fce2  jns     short loc_18000FD35
0x18000fce4  mov     rcx, rbx; hObject
0x18000fce7  call    cs:__imp_CloseHandle
0x18000fcee  nop     dword ptr [rax+rax+00h]
0x18000fcf3  nop
0x18000fcf4  mov     rcx, [rbp+57h+hKey]; hKey
0x18000fcf8  test    rcx, rcx
0x18000fcfb  jz      short loc_18000FD09
0x18000fcfd  call    cs:__imp_RegCloseKey
0x18000fd04  nop     dword ptr [rax+rax+00h]
0x18000fd09  mov     eax, r13d
0x18000fd0c  mov     rcx, [rbp+57h+var_30]
0x18000fd10  xor     rcx, rsp; StackCookie
0x18000fd13  call    __security_check_cookie
0x18000fd18  lea     r11, [rsp+100h+var_20]
0x18000fd20  mov     rbx, [r11+40h]
0x18000fd24  mov     rsi, [r11+48h]
0x18000fd28  mov     rsp, r11
0x18000fd2b  pop     r15
0x18000fd2d  pop     r14
0x18000fd2f  pop     r13
0x18000fd31  pop     rdi
0x18000fd32  pop     rbp
0x18000fd33  retn
0x18000fd35  lea     rcx, [rbp+57h+hKey]
0x18000fd39  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000fd3e  mov     [rsp+100h+phkResult], rax; phkResult
0x18000fd43  mov     r9d, 20119h; samDesired
0x18000fd49  xor     r8d, r8d; ulOptions
0x18000fd4c  mov     rdx, rsi; lpSubKey
0x18000fd4f  mov     rcx, [rbp+57h+var_C8]; hKey
0x18000fd53  call    cs:__imp_RegOpenKeyExW
0x18000fd5a  nop     dword ptr [rax+rax+00h]
0x18000fd5f  test    eax, eax
0x18000fd61  jnz     short loc_18000FCE4
0x18000fd63  xor     edi, edi
0x18000fd65  xor     edx, edx; Val
0x18000fd67  lea     r8d, [rax+40h]; Size
0x18000fd6b  lea     rcx, [rbp+57h+var_70]; void *
0x18000fd6f  call    memset_0
0x18000fd74  mov     dword ptr [rsp+100h+phkResult], r13d; fAsynchronous
0x18000fd79  mov     r9, rbx; hEvent
0x18000fd7c  mov     r8d, 5; dwNotifyFilter
0x18000fd82  mov     edx, r13d; bWatchSubtree
0x18000fd85  mov     rcx, [rbp+57h+hKey]; hKey
0x18000fd89  call    cs:__imp_RegNotifyChangeKeyValue
0x18000fd90  nop     dword ptr [rax+rax+00h]
0x18000fd95  test    eax, eax
0x18000fd97  jnz     loc_18000FE96
0x18000fd9d  xor     edx, edx; Val
0x18000fd9f  lea     r8d, [rax+40h]; Size
0x18000fda3  lea     rcx, [rbp+57h+var_70]; void *
0x18000fda7  call    memset_0
0x18000fdac  mov     [rbp+57h+var_70], 40h ; '@'
0x18000fdb3  lea     rdx, [rbp+57h+var_70]
0x18000fdb7  mov     rcx, rsi; lpSubKey
0x18000fdba  call    OmaDmGetInitiationInfo
0x18000fdbf  test    eax, eax
0x18000fdc1  js      loc_18000FE96
0x18000fdc7  mov     ecx, [rbp+57h+var_5C]
0x18000fdca  lea     eax, [rcx-5]
0x18000fdcd  cmp     eax, r13d
0x18000fdd0  jbe     short loc_18000FDDA
0x18000fdd2  test    ecx, ecx
0x18000fdd4  jz      short loc_18000FDDA
0x18000fdd6  xor     edi, edi
0x18000fdd8  jmp     short loc_18000FDDD
0x18000fdda  mov     edi, r13d
0x18000fddd  lea     rcx, [rbp+57h+var_70]
0x18000fde1  call    OmaDmFreeInitiationInfo
0x18000fde6  test    edi, edi
0x18000fde8  jnz     loc_18000FE96
0x18000fdee  or      eax, 0FFFFFFFFh
0x18000fdf1  cmp     r14d, eax
0x18000fdf4  jnz     short loc_18000FDFA
0x18000fdf6  mov     edx, eax
0x18000fdf8  jmp     short loc_18000FE17
0x18000fdfa  call    cs:__imp_GetTickCount
0x18000fe01  nop     dword ptr [rax+rax+00h]
0x18000fe06  sub     eax, r15d
0x18000fe09  cmp     eax, r14d
0x18000fe0c  ja      short loc_18000FE15
0x18000fe0e  mov     edx, r14d
0x18000fe11  sub     edx, eax
0x18000fe13  jmp     short loc_18000FE17
0x18000fe15  xor     edx, edx; dwMilliseconds
0x18000fe17  mov     rcx, rbx; hHandle
0x18000fe1a  call    cs:__imp_WaitForSingleObject
0x18000fe21  nop     dword ptr [rax+rax+00h]
0x18000fe26  mov     rcx, rbx; hEvent
0x18000fe29  call    cs:__imp_ResetEvent
0x18000fe30  nop     dword ptr [rax+rax+00h]
0x18000fe35  xor     edx, edx; Val
0x18000fe37  lea     r8d, [rdx+40h]; Size
0x18000fe3b  lea     rcx, [rbp+57h+var_B0]; void *
0x18000fe3f  call    memset_0
0x18000fe44  mov     [rbp+57h+var_B0], 40h ; '@'
0x18000fe4b  lea     rdx, [rbp+57h+var_B0]
0x18000fe4f  mov     rcx, rsi; lpSubKey
0x18000fe52  call    OmaDmGetInitiationInfo
0x18000fe57  test    eax, eax
0x18000fe59  js      short loc_18000FE96
0x18000fe5b  mov     ecx, [rbp+57h+var_9C]
0x18000fe5e  lea     eax, [rcx-5]
0x18000fe61  cmp     eax, r13d
0x18000fe64  jbe     short loc_18000FE6E
0x18000fe66  test    ecx, ecx
0x18000fe68  jz      short loc_18000FE6E
0x18000fe6a  xor     edi, edi
0x18000fe6c  jmp     short loc_18000FE71
0x18000fe6e  mov     edi, r13d
0x18000fe71  lea     rcx, [rbp+57h+var_B0]
0x18000fe75  call    OmaDmFreeInitiationInfo
0x18000fe7a  test    edi, edi
0x18000fe7c  jnz     short loc_18000FE96
0x18000fe7e  call    cs:__imp_GetTickCount
0x18000fe85  nop     dword ptr [rax+rax+00h]
0x18000fe8a  sub     eax, r15d
0x18000fe8d  cmp     eax, r14d
0x18000fe90  jb      loc_18000FD74
0x18000fe96  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 2
0x18000fe9d  jz      short loc_18000FEEB
0x18000fe9f  mov     eax, [rbp+57h+var_5C]
0x18000fea2  mov     dword ptr [rbp+57h+var_C8], eax
0x18000fea5  mov     dword ptr [rbp+57h+var_C0], edi
0x18000fea8  lea     rax, [rbp+57h+var_C0]
0x18000feac  mov     [rbp-9], rax
0x18000feb0  mov     [rbp+57h+var_58], 4
0x18000feb8  lea     rax, [rbp+57h+var_C8]
0x18000febc  mov     [rbp+57h+var_50], rax
0x18000fec0  mov     [rbp+57h+var_48], 4
0x18000fec8  lea     rax, [rbp+57h+var_70]
0x18000fecc  mov     [rsp+100h+phkResult], rax
0x18000fed1  mov     r9d, 3
0x18000fed7  lea     rdx, WaitingForSessionDone
0x18000fede  lea     rcx, WP_OMADMAPI_PROVIDER_Context
0x18000fee5  call    McGenEventWrite_EventWriteTransfer
0x18000feea  nop
0x18000feeb  mov     rcx, rbx; hObject
0x18000feee  call    cs:__imp_CloseHandle
0x18000fef5  nop     dword ptr [rax+rax+00h]
0x18000fefa  nop
0x18000fefb  mov     rcx, [rbp+57h+hKey]; hKey
0x18000feff  test    rcx, rcx
0x18000ff02  jz      short loc_18000FF10
0x18000ff04  call    cs:__imp_RegCloseKey
0x18000ff0b  nop     dword ptr [rax+rax+00h]
0x18000ff10  mov     eax, edi
0x18000ff12  jmp     loc_18000FD0C
```
