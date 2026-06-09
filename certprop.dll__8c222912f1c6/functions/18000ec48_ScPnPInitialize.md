# ScPnPInitialize

- ea: `0x18000ec48`
- end: `0x18000f21d`
- name: `ScPnPInitialize`
- size: `1493`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x180017d90`

## callees

- `0x1800013d0`
- `0x180002560`
- `0x180004600`
- `0x18000e4ac`
- `0x18000ec48`
- `0x180014ca0`
- `0x180015554`
- `0x180016090`
- `0x180016a66`
- `0x180018b58`
- `0x180018bb4`
- `0x180019fa4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000ef7e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000ef7e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000eeeb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000eeeb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000effd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000effd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000f053`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000f06b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000f053`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000f06b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ecde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ecde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f016`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000ecd4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000ecd4`
- `USER32!RegisterDeviceNotificationW` at `0x18000ed80`
- `USER32!RegisterDeviceNotificationW` at `0x18000ee42`
- `USER32!RegisterDeviceNotificationW` at `0x18000ed80`
- `USER32!RegisterDeviceNotificationW` at `0x18000ee42`

## string_xrefs

- `0x18000eccb`: `certprop.dll`

## pseudocode

```c
__int64 __fastcall ScPnPInitialize(__int64 a1)
{
  DWORD LastError; // ebx
  HMODULE v2; // rsi
  STRSAFE_LPSTR v3; // rcx
  STRSAFE_LPSTR v4; // rcx
  __int64 v5; // rcx
  int v6; // edx
  STRSAFE_LPSTR v7; // rcx
  DWORD v8; // eax
  STRSAFE_LPSTR v9; // rcx
  DWORD v10; // eax
  HMODULE v11; // rax
  __int64 v12; // rcx
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  __int64 v14; // rcx
  DWORD v15; // eax
  int v16; // edx
  HANDLE EventW; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  HMODULE phModule[2]; // [rsp+30h] [rbp-88h] BYREF
  int NotificationFilter; // [rsp+40h] [rbp-78h] BYREF
  __int64 v25; // [rsp+44h] [rbp-74h]
  GUID v26; // [rsp+4Ch] [rbp-6Ch]
  int v27; // [rsp+5Ch] [rbp-5Ch]
  int v28; // [rsp+60h] [rbp-58h] BYREF
  __int64 v29; // [rsp+64h] [rbp-54h]
  GUID v30; // [rsp+6Ch] [rbp-4Ch]
  int v31; // [rsp+7Ch] [rbp-3Ch]

  LastError = 0;
  v2 = 0;
  phModule[0] = 0;
  WppTraceIndent(a1, 0);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids, WPP_pszIndent);
  }
  I_ScPnPReadConfiguration((__int64)v3);
  if ( !g_fEnableScPnP )
    goto LABEL_67;
  if ( !GetModuleHandleExW(0, L"certprop.dll", phModule) )
  {
    LastError = GetLastError();
    goto LABEL_67;
  }
  LastError = I_ScPnPLoadResourceString(phModule[0]);
  if ( LastError )
  {
    WppTraceIndent(v5, 2);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      v6 = 91;
LABEL_13:
      WPP_SF_sD(
        *((_QWORD *)v4 + 2),
        v6,
        (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
        WPP_pszIndent,
        LastError);
    }
  }
  else
  {
    v25 = 5;
    v27 = 0;
    LastError = 0;
    NotificationFilter = 32;
    v26 = GUID_DEVINTERFACE_SMARTCARD;
    g_hSmartCardDeviceNotify = RegisterDeviceNotificationW(g_hCertPropStatus, &NotificationFilter, 1u);
    if ( !g_hSmartCardDeviceNotify )
    {
      WppTraceIndent(v7, 2);
      v8 = GetLastError();
      LastError = v8;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          80,
          (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
          WPP_pszIndent,
          v8);
      }
    }
    if ( LastError )
    {
      WppTraceIndent(v7, 2);
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        v6 = 92;
        goto LABEL_13;
      }
    }
    else
    {
      v29 = 5;
      v31 = 0;
      LastError = 0;
      v28 = 32;
      v30 = GUID_DEVINTERFACE_SCFILTER;
      g_hScFilterNotify = RegisterDeviceNotificationW(g_hCertPropStatus, &v28, 1u);
      if ( !g_hScFilterNotify )
      {
        WppTraceIndent(v9, 2);
        v10 = GetLastError();
        LastError = v10;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            80,
            (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
            WPP_pszIndent,
            v10);
        }
      }
      if ( !LastError )
      {
        LastError = 8;
        v11 = (HMODULE)HeapAlloc(g_hHeap, 8u, 0x260u);
        v2 = v11;
        phModule[1] = v11;
        if ( !v11 )
        {
          WppTraceIndent(v12, 2);
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[28] & 1) != 0
            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              94,
              &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
              WPP_pszIndent);
          }
          goto LABEL_67;
        }
        memset_0(v11, 0, 0x260u);
        *((_DWORD *)v2 + 100) = 3;
        *((_DWORD *)v2 + 115) = 1;
        *((_DWORD *)v2 + 116) = 72;
        *((_DWORD *)v2 + 118) = 1;
        ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
        *((_QWORD *)v2 + 60) = ThreadpoolCleanupGroup;
        if ( ThreadpoolCleanupGroup )
        {
          *((_QWORD *)v2 + 52) = ThreadpoolCleanupGroup;
          *((_QWORD *)v2 + 53) = 0;
          *((_QWORD *)v2 + 54) = g_hInst;
          EventW = CreateEventW(0, 1, 0, 0);
          *((_QWORD *)v2 + 61) = EventW;
          if ( EventW )
          {
            InitializeCriticalSection((LPCRITICAL_SECTION)(v2 + 124));
            *((_DWORD *)v2 + 134) = 1;
            InitializeCriticalSection((LPCRITICAL_SECTION)(v2 + 136));
            *((_DWORD *)v2 + 146) = 1;
            *(_QWORD *)(v2 + 1) = 0;
            *((_QWORD *)v2 + 2) = 0;
            *((_DWORD *)v2 + 3) = 0;
            *((_DWORD *)v2 + 6) = 2;
            *((_DWORD *)v2 + 7) = 1;
            *(_DWORD *)v2 = 0;
            *((_QWORD *)v2 + 4) = g_hHeap;
            *((_DWORD *)v2 + 10) = 2;
            LastError = ReaderMonitorInitialize((__int64)v2);
            if ( LastError )
            {
              WppTraceIndent(v20, 2);
              v4 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control[28] & 1) != 0
                && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
              {
                v6 = 97;
                goto LABEL_13;
              }
            }
            else
            {
              LastError = I_ScPnPCreateThreadpoolWait(v20, v19, *((_QWORD *)v2 + 11), v2 + 100, v2 + 98);
              if ( LastError )
              {
                WppTraceIndent(v21, 2);
                v4 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
                  && (WPP_GLOBAL_Control[28] & 1) != 0
                  && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
                {
                  v6 = 98;
                  goto LABEL_13;
                }
              }
              else
              {
                LastError = ReaderMonitorStartThread(v2);
                if ( !LastError )
                {
                  g_pScPnPState = v2;
                  v2 = 0;
                  goto LABEL_67;
                }
                WppTraceIndent(v4, 2);
                v4 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
                  && (WPP_GLOBAL_Control[28] & 1) != 0
                  && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
                {
                  v6 = 99;
                  goto LABEL_13;
                }
              }
            }
            goto LABEL_67;
          }
          WppTraceIndent(v18, 2);
          v15 = GetLastError();
          LastError = v15;
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control[28] & 1) == 0
            || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
          {
            goto LABEL_67;
          }
          v16 = 96;
        }
        else
        {
          WppTraceIndent(v14, 2);
          v15 = GetLastError();
          LastError = v15;
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control[28] & 1) == 0
            || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
          {
            goto LABEL_67;
          }
          v16 = 95;
        }
        WPP_SF_sD(
          *((_QWORD *)v4 + 2),
          v16,
          (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
          WPP_pszIndent,
          v15);
        goto LABEL_67;
      }
      WppTraceIndent(v9, 2);
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        v6 = 93;
        goto LABEL_13;
      }
    }
  }
LABEL_67:
  if ( v2 )
    I_ScPnPFreeState(v2);
  WppTraceIndent(v4, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      100,
      (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000ec48  push    rbx
0x18000ec4a  push    rsi
0x18000ec4b  push    rdi
0x18000ec4c  push    r12
0x18000ec4e  push    r13
0x18000ec50  sub     rsp, 90h
0x18000ec57  mov     rax, cs:__security_cookie
0x18000ec5e  xor     rax, rsp
0x18000ec61  mov     [rsp+0B8h+var_38], rax
0x18000ec69  xor     ebx, ebx
0x18000ec6b  xor     esi, esi
0x18000ec6d  mov     [rsp+0B8h+phModule], rbx
0x18000ec72  xor     edx, edx
0x18000ec74  call    WppTraceIndent
0x18000ec79  lea     r12, WPP_GLOBAL_Control
0x18000ec80  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec87  lea     edi, [rbx+2]
0x18000ec8a  cmp     rcx, r12
0x18000ec8d  jz      short loc_18000ECB5
0x18000ec8f  test    [rcx+1Ch], dil
0x18000ec93  jz      short loc_18000ECB5
0x18000ec95  cmp     byte ptr [rcx+19h], 5
0x18000ec99  jb      short loc_18000ECB5
0x18000ec9b  lea     edx, [rbx+5Ah]
0x18000ec9e  mov     r9, cs:WPP_pszIndent
0x18000eca5  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18000ecac  mov     rcx, [rcx+10h]
0x18000ecb0  call    WPP_SF_s
0x18000ecb5  call    I_ScPnPReadConfiguration
0x18000ecba  cmp     cs:g_fEnableScPnP, ebx
0x18000ecc0  jz      loc_18000F1AB
0x18000ecc6  lea     r8, [rsp+0B8h+phModule]; phModule
0x18000eccb  lea     rdx, ModuleName; "certprop.dll"
0x18000ecd2  xor     ecx, ecx; dwFlags
0x18000ecd4  call    cs:__imp_GetModuleHandleExW
0x18000ecda  test    eax, eax
0x18000ecdc  jnz     short loc_18000ECEB
0x18000ecde  call    cs:__imp_GetLastError
0x18000ece4  mov     ebx, eax
0x18000ece6  jmp     loc_18000F1AB
0x18000eceb  mov     rcx, [rsp+0B8h+phModule]
0x18000ecf0  call    I_ScPnPLoadResourceString
0x18000ecf5  mov     ebx, eax
0x18000ecf7  test    eax, eax
0x18000ecf9  jz      short loc_18000ED4B
0x18000ecfb  mov     edx, edi
0x18000ecfd  call    WppTraceIndent
0x18000ed02  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed09  cmp     rcx, r12
0x18000ed0c  jz      loc_18000F1AB
0x18000ed12  test    byte ptr [rcx+1Ch], 1
0x18000ed16  jz      loc_18000F1AB
0x18000ed1c  cmp     [rcx+19h], dil
0x18000ed20  jb      loc_18000F1AB
0x18000ed26  mov     edx, 5Bh ; '['
0x18000ed2b  mov     dword ptr [rsp+0B8h+var_98], ebx
0x18000ed2f  mov     r9, cs:WPP_pszIndent
0x18000ed36  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18000ed3d  mov     rcx, [rcx+10h]
0x18000ed41  call    WPP_SF_sD
0x18000ed46  jmp     loc_18000F1AB
0x18000ed4b  mov     [rsp+0B8h+var_74], 5
0x18000ed54  mov     [rsp+0B8h+var_5C], esi
0x18000ed58  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_SMARTCARD.Data1
0x18000ed5f  xor     ebx, ebx
0x18000ed61  lea     r13d, [rbx+20h]
0x18000ed65  mov     [rsp+0B8h+NotificationFilter], r13d
0x18000ed6a  movdqu  [rsp+0B8h+var_6C], xmm0
0x18000ed70  lea     r8d, [rbx+1]; Flags
0x18000ed74  lea     rdx, [rsp+0B8h+NotificationFilter]; NotificationFilter
0x18000ed79  mov     rcx, cs:g_hCertPropStatus; hRecipient
0x18000ed80  call    cs:__imp_RegisterDeviceNotificationW
0x18000ed86  mov     cs:g_hSmartCardDeviceNotify, rax
0x18000ed8d  test    rax, rax
0x18000ed90  jnz     short loc_18000EDD8
0x18000ed92  mov     edx, edi
0x18000ed94  call    WppTraceIndent
0x18000ed99  call    cs:__imp_GetLastError
0x18000ed9f  mov     ebx, eax
0x18000eda1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eda8  cmp     rcx, r12
0x18000edab  jz      short loc_18000EDD8
0x18000edad  test    byte ptr [rcx+1Ch], 1
0x18000edb1  jz      short loc_18000EDD8
0x18000edb3  cmp     [rcx+19h], dil
0x18000edb7  jb      short loc_18000EDD8
0x18000edb9  lea     edx, [r13+30h]
0x18000edbd  mov     dword ptr [rsp+0B8h+var_98], eax
0x18000edc1  mov     r9, cs:WPP_pszIndent
0x18000edc8  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18000edcf  mov     rcx, [rcx+10h]
0x18000edd3  call    WPP_SF_sD
0x18000edd8  test    ebx, ebx
0x18000edda  jz      short loc_18000EE11
0x18000eddc  mov     edx, edi
0x18000edde  call    WppTraceIndent
0x18000ede3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000edea  cmp     rcx, r12
0x18000eded  jz      loc_18000F1AB
0x18000edf3  test    byte ptr [rcx+1Ch], 1
0x18000edf7  jz      loc_18000F1AB
0x18000edfd  cmp     [rcx+19h], dil
0x18000ee01  jb      loc_18000F1AB
0x18000ee07  mov     edx, 5Ch ; '\'
0x18000ee0c  jmp     loc_18000ED2B
0x18000ee11  mov     [rsp+0B8h+var_54], 5
0x18000ee1a  mov     [rsp+0B8h+var_3C], esi
0x18000ee1e  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_SCFILTER.Data1
0x18000ee25  xor     ebx, ebx
0x18000ee27  mov     [rsp+0B8h+var_58], r13d
0x18000ee2c  movdqu  [rsp+0B8h+var_4C], xmm0
0x18000ee32  lea     r8d, [rbx+1]; Flags
0x18000ee36  lea     rdx, [rsp+0B8h+var_58]; NotificationFilter
0x18000ee3b  mov     rcx, cs:g_hCertPropStatus; hRecipient
0x18000ee42  call    cs:__imp_RegisterDeviceNotificationW
0x18000ee48  mov     cs:g_hScFilterNotify, rax
0x18000ee4f  test    rax, rax
0x18000ee52  jnz     short loc_18000EE9B
0x18000ee54  mov     edx, edi
0x18000ee56  call    WppTraceIndent
0x18000ee5b  call    cs:__imp_GetLastError
0x18000ee61  mov     ebx, eax
0x18000ee63  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee6a  cmp     rcx, r12
0x18000ee6d  jz      short loc_18000EE9B
0x18000ee6f  test    byte ptr [rcx+1Ch], 1
0x18000ee73  jz      short loc_18000EE9B
0x18000ee75  cmp     [rcx+19h], dil
0x18000ee79  jb      short loc_18000EE9B
0x18000ee7b  mov     edx, 50h ; 'P'
0x18000ee80  mov     dword ptr [rsp+0B8h+var_98], eax
0x18000ee84  mov     r9, cs:WPP_pszIndent
0x18000ee8b  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18000ee92  mov     rcx, [rcx+10h]
0x18000ee96  call    WPP_SF_sD
0x18000ee9b  test    ebx, ebx
0x18000ee9d  jz      short loc_18000EED4
0x18000ee9f  mov     edx, edi
0x18000eea1  call    WppTraceIndent
0x18000eea6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eead  cmp     rcx, r12
0x18000eeb0  jz      loc_18000F1AB
0x18000eeb6  test    byte ptr [rcx+1Ch], 1
0x18000eeba  jz      loc_18000F1AB
0x18000eec0  cmp     [rcx+19h], dil
0x18000eec4  jb      loc_18000F1AB
0x18000eeca  mov     edx, 5Dh ; ']'
0x18000eecf  jmp     loc_18000ED2B
0x18000eed4  mov     r13d, 260h
0x18000eeda  mov     r8d, r13d; dwBytes
0x18000eedd  mov     ebx, 8
0x18000eee2  mov     edx, ebx; dwFlags
0x18000eee4  mov     rcx, cs:g_hHeap; hHeap
0x18000eeeb  call    cs:__imp_HeapAlloc
0x18000eef1  mov     rsi, rax
0x18000eef4  mov     [rsp+0B8h+var_80], rax
0x18000eef9  test    rax, rax
0x18000eefc  jnz     short loc_18000EF48
0x18000eefe  mov     edx, edi
0x18000ef00  call    WppTraceIndent
0x18000ef05  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef0c  cmp     rcx, r12
0x18000ef0f  jz      loc_18000F1AB
0x18000ef15  test    byte ptr [rcx+1Ch], 1
0x18000ef19  jz      loc_18000F1AB
0x18000ef1f  cmp     [rcx+19h], dil
0x18000ef23  jb      loc_18000F1AB
0x18000ef29  lea     edx, [rbx+56h]
0x18000ef2c  mov     r9, cs:WPP_pszIndent
0x18000ef33  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18000ef3a  mov     rcx, [rcx+10h]
0x18000ef3e  call    WPP_SF_s
0x18000ef43  jmp     loc_18000F1AB
0x18000ef48  mov     r8, r13; Size
0x18000ef4b  xor     edx, edx; Val
0x18000ef4d  mov     rcx, rsi; void *
0x18000ef50  call    memset_0
0x18000ef55  lea     r13, [rsi+190h]
0x18000ef5c  mov     dword ptr [r13+0], 3
0x18000ef64  mov     dword ptr [r13+3Ch], 1
0x18000ef6c  mov     dword ptr [r13+40h], 48h ; 'H'
0x18000ef74  mov     dword ptr [rsi+1D8h], 1
0x18000ef7e  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18000ef84  mov     [rsi+1E0h], rax
0x18000ef8b  test    rax, rax
0x18000ef8e  jnz     short loc_18000EFD1
0x18000ef90  mov     edx, edi
0x18000ef92  call    WppTraceIndent
0x18000ef97  call    cs:__imp_GetLastError
0x18000ef9d  mov     ebx, eax
0x18000ef9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efa6  cmp     rcx, r12
0x18000efa9  jz      loc_18000F1AB
0x18000efaf  test    byte ptr [rcx+1Ch], 1
0x18000efb3  jz      loc_18000F1AB
0x18000efb9  cmp     [rcx+19h], dil
0x18000efbd  jb      loc_18000F1AB
0x18000efc3  mov     edx, 5Fh ; '_'
0x18000efc8  mov     dword ptr [rsp+0B8h+var_98], eax
0x18000efcc  jmp     loc_18000ED2F
0x18000efd1  mov     [rsi+1A0h], rax
0x18000efd8  mov     qword ptr [rsi+1A8h], 0
0x18000efe3  mov     rax, cs:g_hInst
0x18000efea  mov     [rsi+1B0h], rax
0x18000eff1  xor     r9d, r9d; lpName
0x18000eff4  xor     r8d, r8d; bInitialState
0x18000eff7  lea     edx, [r9+1]; bManualReset
0x18000effb  xor     ecx, ecx; lpEventAttributes
0x18000effd  call    cs:__imp_CreateEventW
0x18000f003  mov     [rsi+1E8h], rax
0x18000f00a  test    rax, rax
0x18000f00d  jnz     short loc_18000F04C
0x18000f00f  mov     edx, edi
0x18000f011  call    WppTraceIndent
0x18000f016  call    cs:__imp_GetLastError
0x18000f01c  mov     ebx, eax
0x18000f01e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f025  cmp     rcx, r12
0x18000f028  jz      loc_18000F1AB
0x18000f02e  test    byte ptr [rcx+1Ch], 1
0x18000f032  jz      loc_18000F1AB
0x18000f038  cmp     [rcx+19h], dil
0x18000f03c  jb      loc_18000F1AB
0x18000f042  mov     edx, 60h ; '`'
0x18000f047  jmp     loc_18000EFC8
0x18000f04c  lea     rcx, [rsi+1F0h]; lpCriticalSection
0x18000f053  call    cs:__imp_InitializeCriticalSection
0x18000f059  nop
0x18000f05a  mov     dword ptr [rsi+218h], 1
0x18000f064  lea     rcx, [rsi+220h]; lpCriticalSection
0x18000f06b  call    cs:__imp_InitializeCriticalSection
0x18000f071  nop
0x18000f072  mov     dword ptr [rsi+248h], 1
0x18000f07c  mov     qword ptr [rsi+4], 0
0x18000f084  mov     qword ptr [rsi+10h], 0
0x18000f08c  mov     dword ptr [rsi+0Ch], 0
0x18000f093  mov     [rsi+18h], edi
0x18000f096  mov     dword ptr [rsi+1Ch], 1
0x18000f09d  mov     dword ptr [rsi], 0
0x18000f0a3  mov     rax, cs:g_hHeap
0x18000f0aa  mov     [rsi+20h], rax
0x18000f0ae  mov     [rsi+28h], edi
0x18000f0b1  mov     rcx, rsi
0x18000f0b4  call    ReaderMonitorInitialize
0x18000f0b9  mov     ebx, eax
0x18000f0bb  test    eax, eax
0x18000f0bd  jz      short loc_18000F0F4
0x18000f0bf  mov     edx, edi
0x18000f0c1  call    WppTraceIndent
0x18000f0c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0cd  cmp     rcx, r12
0x18000f0d0  jz      loc_18000F1AB
0x18000f0d6  test    byte ptr [rcx+1Ch], 1
0x18000f0da  jz      loc_18000F1AB
0x18000f0e0  cmp     [rcx+19h], dil
0x18000f0e4  jb      loc_18000F1AB
0x18000f0ea  mov     edx, 61h ; 'a'
0x18000f0ef  jmp     loc_18000ED2B
0x18000f0f4  lea     rax, [rsi+188h]
0x18000f0fb  mov     [rsp+0B8h+var_98], rax
0x18000f100  mov     r9, r13
0x18000f103  mov     r8, [rsi+58h]
0x18000f107  call    I_ScPnPCreateThreadpoolWait
0x18000f10c  mov     ebx, eax
0x18000f10e  test    eax, eax
0x18000f110  jz      short loc_18000F13F
0x18000f112  mov     edx, edi
0x18000f114  call    WppTraceIndent
0x18000f119  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f120  cmp     rcx, r12
0x18000f123  jz      loc_18000F1AB
0x18000f129  test    byte ptr [rcx+1Ch], 1
0x18000f12d  jz      short loc_18000F1AB
0x18000f12f  cmp     [rcx+19h], dil
0x18000f133  jb      short loc_18000F1AB
0x18000f135  mov     edx, 62h ; 'b'
0x18000f13a  jmp     loc_18000ED2B
0x18000f13f  mov     rcx, rsi; lpParameter
0x18000f142  call    ReaderMonitorStartThread
0x18000f147  mov     ebx, eax
0x18000f149  test    eax, eax
0x18000f14b  jz      short loc_18000F176
0x18000f14d  mov     edx, edi
0x18000f14f  call    WppTraceIndent
0x18000f154  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f15b  cmp     rcx, r12
0x18000f15e  jz      short loc_18000F1AB
0x18000f160  test    byte ptr [rcx+1Ch], 1
0x18000f164  jz      short loc_18000F1AB
0x18000f166  cmp     [rcx+19h], dil
0x18000f16a  jb      short loc_18000F1AB
0x18000f16c  mov     edx, 63h ; 'c'
0x18000f171  jmp     loc_18000ED2B
0x18000f176  mov     cs:g_pScPnPState, rsi
0x18000f17d  xor     esi, esi
0x18000f17f  jmp     short loc_18000F1AB
0x18000f181  mov     ebx, 8
0x18000f186  lea     r12, WPP_GLOBAL_Control
0x18000f18d  lea     edi, [rbx-6]
0x18000f190  mov     rsi, [rsp+0B8h+var_80]
  ... truncated ...
```
