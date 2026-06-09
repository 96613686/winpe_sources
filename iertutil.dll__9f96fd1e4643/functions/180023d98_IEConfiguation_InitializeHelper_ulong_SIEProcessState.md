# _IEConfiguation_InitializeHelper(ulong,SIEProcessState *)

- ea: `0x180023d98`
- end: `0x18002446e`
- name: `?_IEConfiguation_InitializeHelper@@YAJKPEAUSIEProcessState@@@Z`
- size: `1750`
- prototype: `__int64 __fastcall(unsigned int, struct SIEProcessState *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018d20`

## callees

- `0x18001b510`
- `0x18001d0f0`
- `0x180022fd0`
- `0x180023d98`
- `0x180024480`
- `0x180024530`
- `0x1800245b0`
- `0x180024640`
- `0x1800246e8`
- `0x180024788`
- `0x180024850`
- `0x1800248f8`
- `0x180024bb4`
- `0x180024d04`
- `0x180024eb0`
- `0x180025024`
- `0x1800250ac`
- `0x180025440`
- `0x180083c10`

## import_xrefs

- `msvcrt!wcstol` at `0x1800243d1`
- `msvcrt!wcstol` at `0x1800243d1`
- `msvcrt!_wcsnicmp` at `0x1800240b9`
- `msvcrt!_wcsnicmp` at `0x1800240d7`
- `msvcrt!_wcsnicmp` at `0x1800240f5`
- `msvcrt!_wcsnicmp` at `0x180024137`
- `msvcrt!_wcsnicmp` at `0x18002437d`
- `msvcrt!_wcsnicmp` at `0x180024399`
- `msvcrt!_wcsnicmp` at `0x1800243b5`
- `msvcrt!_wcsnicmp` at `0x1800240b9`
- `msvcrt!_wcsnicmp` at `0x1800240d7`
- `msvcrt!_wcsnicmp` at `0x1800240f5`
- `msvcrt!_wcsnicmp` at `0x180024137`
- `msvcrt!_wcsnicmp` at `0x18002437d`
- `msvcrt!_wcsnicmp` at `0x180024399`
- `msvcrt!_wcsnicmp` at `0x1800243b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800242d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800242d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024237`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024237`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002428a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002428a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180023e20`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180023e67`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180023e20`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180023e67`

## pseudocode

```c
__int64 __fastcall _IEConfiguation_InitializeHelper(int a1, struct SIEProcessState *a2)
{
  int v4; // r14d
  int IsAppContainerHR; // eax
  char v6; // cl
  bool v7; // al
  BOOL v8; // edi
  int Value_Internal; // eax
  BOOL v10; // ecx
  int v11; // eax
  char v12; // cl
  char v13; // al
  DWORD CurrentProcessId; // eax
  __int64 v16; // rcx
  HANDLE CurrentProcess; // rax
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  int v21[4]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t String2[128]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = 0;
  if ( !*((_BYTE *)a2 + 1) )
    v4 = IEConfiguration_SetBrowserAppProfileDefault();
  if ( byte_180299FFC )
  {
    v6 = byte_18029A129;
  }
  else
  {
    IsAppContainerHR = ProcessIsAppContainerHR(0);
    byte_180299FFC = 1;
    v6 = IsAppContainerHR == 0;
    byte_18029A129 = IsAppContainerHR == 0;
  }
  *((_BYTE *)a2 + 6) = v6;
  InitOnceExecuteOnce(&stru_180298EF0, InitOnceIsCurrentProcessEdgeContentHost, 0, 0);
  *((_BYTE *)a2 + 28) = byte_180298EE9;
  *((_BYTE *)a2 + 52) = 0;
  *((_BYTE *)a2 + 30) = 0;
  *((_BYTE *)a2 + 48) = 0;
  *((_BYTE *)a2 + 50) = 0;
  *((_BYTE *)a2 + 54) = 0;
  *((_BYTE *)a2 + 60) = 0;
  *((_BYTE *)a2 + 56) = 0;
  *((_BYTE *)a2 + 58) = 0;
  *((_DWORD *)a2 + 8) = 0;
  InitOnceExecuteOnce(&stru_180299FB8, InitOnceDeviceFamily, 0, 0);
  if ( !byte_180298C9C || (unsigned int)IEConfiguration_GetDWORD(268435501) == 2 )
    GetCurrentProcessIntegrityLevel((bool *)a2 + 12, (bool *)a2 + 10, (bool *)a2 + 8);
  if ( v4 >= 0 )
  {
    if ( !*((_BYTE *)a2 + 8) )
    {
      if ( !*((_BYTE *)a2 + 10) && (unsigned int)IsUserAdmin() )
        *((_BYTE *)a2 + 14) = 1;
      hObject = 0;
      CurrentProcessId = GetCurrentProcessId();
      if ( (int)GetProcessToken(v16, CurrentProcessId, &hObject) >= 0 )
      {
        v18 = 0;
        v21[0] = 0;
        if ( (int)LUAGetSplitToken(hObject, &v18, v21) >= 0 )
        {
          if ( v21[0] )
          {
            *((_BYTE *)a2 + 16) = 1;
            if ( v18 )
              *((_BYTE *)a2 + 18) = 1;
          }
        }
        CloseHandle(hObject);
      }
      if ( IsTokenBuiltInAdministrator() )
        *((_BYTE *)a2 + 20) = 1;
    }
    if ( IEIsWebPlatformProcess() )
      *((_BYTE *)a2 + 26) = 1;
    byte_18029919A = IEConfiguration_IsLowMemSystem();
    byte_1802991A2 = IEConfiguration_IsLowDiskSpaceSystem();
    v18 = 0;
    if ( (int)GetValue_Internal((__int64 *)SettingStore::IEVALUE_LCIE_FTW[0], 0, 1, &v18, 4, 0, 0) < 0
      || (byte_180298F56 = 0, v18) )
    {
      byte_180298F56 = 1;
    }
    v18 = 0;
    if ( (int)GetValue_Internal((__int64 *)SettingStore::IEVALUE_LCIE_MFP[0], 0, 1, &v18, 4, 0, 0) < 0 )
    {
      v7 = 1;
    }
    else
    {
      v7 = v18 != 0;
      if ( !v18 )
      {
        byte_180298F50 = 0;
        goto LABEL_17;
      }
    }
    byte_180298F50 = 1;
LABEL_17:
    if ( v7 )
    {
      v18 = 0;
      if ( (int)GetValue_Internal((__int64 *)SettingStore::IEVALUE_LCIE_NTI[0], 0, 1, &v18, 4, 0, 0) < 0
        || (byte_180298F52 = 0, v18) )
      {
        byte_180298F52 = 1;
      }
    }
    v18 = 0;
    if ( (int)GetValue_Internal((__int64 *)SettingStore::IEVALUE_LCIE_AET[0], 0, 1, &v18, 4, 0, 0) < 0
      || (v8 = v18 != 0, !(unsigned int)IsElevatedProcess())
      || (a1 & 0x8000000) != 0 )
    {
      v8 = 1;
    }
    else if ( !v8 )
    {
      byte_180298F54 = 0;
      goto LABEL_28;
    }
    byte_180298F54 = 1;
LABEL_28:
    v18 = 0;
    Value_Internal = GetValue_Internal(
                       (__int64 *)SettingStore::IEVALUE_Security_RunBinaryControlHostProcessInSeparateAppContainer[0],
                       0,
                       1,
                       &v18,
                       4,
                       0,
                       0);
    if ( Value_Internal >= 0 )
    {
      if ( !v18 )
        goto LABEL_34;
      v8 = 1;
    }
    byte_180299C68 = 1;
    v10 = 0;
    if ( Value_Internal >= 0 )
      v10 = v8;
    if ( v10 )
    {
LABEL_35:
      v19 = -1;
      if ( (a1 & 0x8000000) != 0 )
      {
        v11 = 1;
        v19 = 1;
        goto LABEL_95;
      }
      if ( (int)GetValue_Internal((__int64 *)SettingStore::IEVALUE_LCIE_TPGstr[0], 2, 1, String2, 256, 0, 0) < 0 )
      {
LABEL_44:
        v11 = v19;
        if ( v19 == -1 )
        {
          if ( (int)GetValue_Internal((__int64 *)SettingStore::IEVALUE_LCIE_TPGint, 1, 1, &v19, 4, 0, 0) >= 0 )
          {
            v11 = v19;
          }
          else
          {
            v11 = -1;
            v19 = -1;
          }
        }
        if ( v11 < 0 )
        {
          v12 = byte_180298F4C;
          goto LABEL_49;
        }
        if ( !v11 )
        {
          v12 = 0;
          byte_180298F4C = 0;
LABEL_49:
          if ( !v12 )
          {
            if ( (a1 & 0x800000) != 0
              || (CurrentProcess = GetCurrentProcess(), (unsigned int)IEIsImmersiveProcess(CurrentProcess))
              && (unsigned int)IsBrowserProcess() )
            {
              v11 = -1;
              v19 = -1;
            }
            else
            {
              v11 = v19;
            }
          }
          goto LABEL_50;
        }
        if ( v11 > 255 )
        {
          v11 = 255;
          v19 = 255;
        }
LABEL_95:
        byte_180298F4C = 1;
        dword_180298F3C = v11;
LABEL_50:
        if ( v11 == -1 )
        {
          byte_180298F4C = 1;
          byte_180298F4E = 1;
        }
        if ( !(unsigned int)IsElevatedProcess() || byte_180298F54 )
        {
          v13 = byte_180298F4C;
        }
        else
        {
          v13 = 0;
          byte_180298F4C = 0;
        }
        if ( !v13 )
        {
          dword_180298F44 = 0;
          dword_180298F3C = 0;
          byte_180298F4E = 0;
          byte_180298F52 = 0;
          byte_180298F54 = 0;
        }
        if ( (unsigned int)IsProtectedModeEnabled() )
          byte_180298F5C = 1;
        if ( !(unsigned int)IsProtectedModeProcess() )
          *((_BYTE *)a2 + 24) = 1;
        return (unsigned int)v4;
      }
      v19 = -2;
      if ( _wcsnicmp(L"small", String2, 6u) && _wcsnicmp(L"low", String2, 4u) )
      {
        if ( _wcsnicmp(L"medium", String2, 7u) )
        {
          if ( _wcsnicmp(L"large", String2, 6u) && _wcsnicmp(L"high", String2, 5u) && _wcsnicmp(L"flat", String2, 5u) )
          {
            hObject = 0;
            v19 = wcstol(String2, (wchar_t **)&hObject, 0);
            if ( *(_WORD *)hObject )
              v19 = -1;
            goto LABEL_42;
          }
          dword_180298F3C = 16;
          dword_180298F44 = 2;
        }
        else
        {
          dword_180298F3C = 7;
          dword_180298F44 = 7;
        }
      }
      else
      {
        dword_180298F3C = 3;
        dword_180298F44 = 11;
      }
      byte_180298F4C = 1;
      byte_180298F4E = 1;
LABEL_42:
      if ( !_wcsnicmp(L"flat", String2, 5u) )
        byte_18029919C = 1;
      goto LABEL_44;
    }
LABEL_34:
    byte_180299C68 = 0;
    goto LABEL_35;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180023d98  mov     [rsp-8+arg_0], rbx
0x180023d9d  mov     [rsp-8+arg_10], rsi
0x180023da2  push    rbp
0x180023da3  push    rdi
0x180023da4  push    r12
0x180023da6  push    r14
0x180023da8  push    r15
0x180023daa  lea     rbp, [rsp-70h]
0x180023daf  sub     rsp, 170h
0x180023db6  mov     rax, cs:__security_cookie
0x180023dbd  xor     rax, rsp
0x180023dc0  mov     [rbp+90h+var_30], rax
0x180023dc4  xor     r15d, r15d
0x180023dc7  mov     rbx, rdx
0x180023dca  mov     esi, ecx
0x180023dcc  mov     r14d, r15d
0x180023dcf  cmp     [rdx+1], r15b
0x180023dd3  jnz     short loc_180023DDD
0x180023dd5  call    ?IEConfiguration_SetBrowserAppProfileDefault@@YAJXZ; IEConfiguration_SetBrowserAppProfileDefault(void)
0x180023dda  mov     r14d, eax
0x180023ddd  cmp     cs:byte_180299FFC, r15b
0x180023de4  mov     r12d, 1
0x180023dea  jnz     loc_180024354
0x180023df0  xor     ecx, ecx; unsigned int
0x180023df2  call    ?ProcessIsAppContainerHR@@YAJK@Z; ProcessIsAppContainerHR(ulong)
0x180023df7  test    eax, eax
0x180023df9  mov     cs:byte_180299FFC, r12b
0x180023e00  setz    cl
0x180023e03  mov     cs:byte_18029A129, cl
0x180023e09  mov     [rbx+6], cl
0x180023e0c  lea     rdx, InitOnceIsCurrentProcessEdgeContentHost; InitFn
0x180023e13  lea     rcx, stru_180298EF0; InitOnce
0x180023e1a  xor     r9d, r9d; Context
0x180023e1d  xor     r8d, r8d; Parameter
0x180023e20  call    cs:__imp_InitOnceExecuteOnce
0x180023e26  mov     al, cs:byte_180298EE9
0x180023e2c  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180023e33  xor     r9d, r9d; Context
0x180023e36  mov     [rbx+1Ch], al
0x180023e39  xor     r8d, r8d; Parameter
0x180023e3c  mov     [rbx+34h], r15b
0x180023e40  lea     rcx, stru_180299FB8; InitOnce
0x180023e47  mov     [rbx+1Eh], r15b
0x180023e4b  mov     [rbx+30h], r15b
0x180023e4f  mov     [rbx+32h], r15b
0x180023e53  mov     [rbx+36h], r15b
0x180023e57  mov     [rbx+3Ch], r15b
0x180023e5b  mov     [rbx+38h], r15b
0x180023e5f  mov     [rbx+3Ah], r15b
0x180023e63  mov     [rbx+20h], r15d
0x180023e67  call    cs:__imp_InitOnceExecuteOnce
0x180023e6d  cmp     cs:byte_180298C9C, r15b
0x180023e74  jz      loc_180024212
0x180023e7a  mov     ecx, 1000002Dh
0x180023e7f  call    ?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180023e84  cmp     eax, 2
0x180023e87  jz      loc_180024212
0x180023e8d  test    r14d, r14d
0x180023e90  js      loc_1800241E7
0x180023e96  cmp     [rbx+8], r15b
0x180023e9a  jz      loc_180024228
0x180023ea0  call    ?IEIsWebPlatformProcess@@YA_NXZ; IEIsWebPlatformProcess(void)
0x180023ea5  test    al, al
0x180023ea7  jnz     loc_18002434B
0x180023ead  call    IEConfiguration_IsLowMemSystem
0x180023eb2  mov     cs:byte_18029919A, al
0x180023eb8  call    IEConfiguration_IsLowDiskSpaceSystem
0x180023ebd  mov     rcx, cs:?IEVALUE_LCIE_FTW@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_LCIE_FTW
0x180023ec4  lea     r9, [rsp+190h+var_150]
0x180023ec9  mov     [rsp+190h+var_160], r15
0x180023ece  mov     edi, 4
0x180023ed3  mov     [rsp+190h+var_168], r15
0x180023ed8  mov     r8d, r12d
0x180023edb  xor     edx, edx
0x180023edd  mov     [rsp+190h+var_170], edi
0x180023ee1  mov     cs:byte_1802991A2, al
0x180023ee7  mov     [rsp+190h+var_150], r15d
0x180023eec  call    GetValue_Internal
0x180023ef1  test    eax, eax
0x180023ef3  js      short loc_180023F0B
0x180023ef5  cmp     [rsp+190h+var_150], r15d
0x180023efa  mov     eax, r15d
0x180023efd  mov     cs:byte_180298F56, r15b
0x180023f04  setnz   al
0x180023f07  test    eax, eax
0x180023f09  jz      short loc_180023F12
0x180023f0b  mov     cs:byte_180298F56, r12b
0x180023f12  mov     rcx, cs:?IEVALUE_LCIE_MFP@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_LCIE_MFP
0x180023f19  lea     r9, [rsp+190h+var_150]
0x180023f1e  mov     [rsp+190h+var_160], r15
0x180023f23  mov     r8d, r12d
0x180023f26  mov     [rsp+190h+var_168], r15
0x180023f2b  xor     edx, edx
0x180023f2d  mov     [rsp+190h+var_170], edi
0x180023f31  mov     [rsp+190h+var_150], r15d
0x180023f36  call    GetValue_Internal
0x180023f3b  test    eax, eax
0x180023f3d  js      loc_1800242B2
0x180023f43  cmp     [rsp+190h+var_150], r15d
0x180023f48  mov     eax, r15d
0x180023f4b  setnz   al
0x180023f4e  test    eax, eax
0x180023f50  jz      loc_1800242A6
0x180023f56  mov     cs:byte_180298F50, r12b
0x180023f5d  test    al, al
0x180023f5f  jz      short loc_180023FAB
0x180023f61  mov     rcx, cs:?IEVALUE_LCIE_NTI@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_LCIE_NTI
0x180023f68  lea     r9, [rsp+190h+var_150]
0x180023f6d  mov     [rsp+190h+var_160], r15
0x180023f72  mov     r8d, r12d
0x180023f75  mov     [rsp+190h+var_168], r15
0x180023f7a  xor     edx, edx
0x180023f7c  mov     [rsp+190h+var_170], edi
0x180023f80  mov     [rsp+190h+var_150], r15d
0x180023f85  call    GetValue_Internal
0x180023f8a  test    eax, eax
0x180023f8c  js      short loc_180023FA4
0x180023f8e  cmp     [rsp+190h+var_150], r15d
0x180023f93  mov     eax, r15d
0x180023f96  mov     cs:byte_180298F52, r15b
0x180023f9d  setnz   al
0x180023fa0  test    eax, eax
0x180023fa2  jz      short loc_180023FAB
0x180023fa4  mov     cs:byte_180298F52, r12b
0x180023fab  mov     rcx, cs:?IEVALUE_LCIE_AET@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_LCIE_AET
0x180023fb2  lea     r9, [rsp+190h+var_150]
0x180023fb7  mov     [rsp+190h+var_160], r15
0x180023fbc  mov     r8d, r12d
0x180023fbf  mov     [rsp+190h+var_168], r15
0x180023fc4  xor     edx, edx
0x180023fc6  mov     [rsp+190h+var_170], edi
0x180023fca  mov     [rsp+190h+var_150], r15d
0x180023fcf  call    GetValue_Internal
0x180023fd4  test    eax, eax
0x180023fd6  js      short loc_180024000
0x180023fd8  cmp     [rsp+190h+var_150], r15d
0x180023fdd  mov     edi, r15d
0x180023fe0  setnz   dil
0x180023fe4  call    ?IsElevatedProcess@@YAHXZ; IsElevatedProcess(void)
0x180023fe9  test    eax, eax
0x180023feb  jz      short loc_180024000
0x180023fed  bt      esi, 1Bh
0x180023ff1  jb      short loc_180024000
0x180023ff3  test    edi, edi
0x180023ff5  jnz     short loc_180024003
0x180023ff7  mov     cs:byte_180298F54, r15b
0x180023ffe  jmp     short loc_18002400A
0x180024000  mov     edi, r12d
0x180024003  mov     cs:byte_180298F54, r12b
0x18002400a  mov     rcx, cs:?IEVALUE_Security_RunBinaryControlHostProcessInSeparateAppContainer@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_Security_RunBinaryControlHostProcessInSeparateAppContainer
0x180024011  lea     r9, [rsp+190h+var_150]
0x180024016  mov     [rsp+190h+var_160], r15
0x18002401b  mov     r8d, r12d
0x18002401e  mov     [rsp+190h+var_168], r15
0x180024023  xor     edx, edx
0x180024025  mov     [rsp+190h+var_170], 4
0x18002402d  mov     [rsp+190h+var_150], r15d
0x180024032  call    GetValue_Internal
0x180024037  test    eax, eax
0x180024039  js      short loc_180024045
0x18002403b  cmp     [rsp+190h+var_150], r15d
0x180024040  jz      short loc_180024058
0x180024042  mov     edi, r12d
0x180024045  test    eax, eax
0x180024047  mov     cs:byte_180299C68, r12b
0x18002404e  mov     ecx, r15d
0x180024051  cmovns  ecx, edi
0x180024054  test    ecx, ecx
0x180024056  jnz     short loc_18002405F
0x180024058  mov     cs:byte_180299C68, r15b
0x18002405f  or      edi, 0FFFFFFFFh
0x180024062  mov     [rsp+190h+var_14C], edi
0x180024066  bt      esi, 1Bh
0x18002406a  jb      loc_18002435F
0x180024070  mov     rcx, cs:?IEVALUE_LCIE_TPGstr@SettingStore@@3U?$VALUEID@PEAG@1@B; SettingStore::VALUEID<ushort *> const SettingStore::IEVALUE_LCIE_TPGstr
0x180024077  lea     r9, [rsp+190h+String2]
0x18002407c  mov     [rsp+190h+var_160], r15
0x180024081  lea     edx, [rdi+3]
0x180024084  mov     [rsp+190h+var_168], r15
0x180024089  mov     r8d, r12d
0x18002408c  mov     [rsp+190h+var_170], 100h
0x180024094  call    GetValue_Internal
0x180024099  test    eax, eax
0x18002409b  js      loc_180024148
0x1800240a1  lea     r8d, [rdi+7]; MaxCount
0x1800240a5  mov     [rsp+190h+var_14C], 0FFFFFFFEh
0x1800240ad  lea     rdx, [rsp+190h+String2]; String2
0x1800240b2  lea     rcx, aSmall_0; "small"
0x1800240b9  call    cs:__imp__wcsnicmp
0x1800240bf  test    eax, eax
0x1800240c1  jz      loc_1800242BA
0x1800240c7  lea     r8d, [rdi+5]; MaxCount
0x1800240cb  lea     rdx, [rsp+190h+String2]; String2
0x1800240d0  lea     rcx, aLow_2; "low"
0x1800240d7  call    cs:__imp__wcsnicmp
0x1800240dd  test    eax, eax
0x1800240df  jz      loc_1800242BA
0x1800240e5  lea     r8d, [rdi+8]; MaxCount
0x1800240e9  lea     rdx, [rsp+190h+String2]; String2
0x1800240ee  lea     rcx, aMedium_0; "medium"
0x1800240f5  call    cs:__imp__wcsnicmp
0x1800240fb  test    eax, eax
0x1800240fd  jnz     loc_18002436B
0x180024103  mov     cs:dword_180298F3C, 7
0x18002410d  mov     cs:dword_180298F44, 7
0x180024117  mov     cs:byte_180298F4C, r12b
0x18002411e  mov     cs:byte_180298F4E, r12b
0x180024125  mov     r8d, 5; MaxCount
0x18002412b  lea     rdx, [rsp+190h+String2]; String2
0x180024130  lea     rcx, aFlat; "flat"
0x180024137  call    cs:__imp__wcsnicmp
0x18002413d  test    eax, eax
0x18002413f  jnz     short loc_180024148
0x180024141  mov     cs:byte_18029919C, r12b
0x180024148  mov     eax, [rsp+190h+var_14C]
0x18002414c  cmp     eax, edi
0x18002414e  jnz     short loc_180024187
0x180024150  mov     rcx, cs:?IEVALUE_LCIE_TPGint@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_LCIE_TPGint
0x180024157  lea     r9, [rsp+190h+var_14C]
0x18002415c  mov     [rsp+190h+var_160], r15
0x180024161  mov     r8d, r12d
0x180024164  mov     [rsp+190h+var_168], r15
0x180024169  mov     edx, r12d
0x18002416c  mov     [rsp+190h+var_170], 4
0x180024174  call    GetValue_Internal
0x180024179  test    eax, eax
0x18002417b  jns     loc_18002430F
0x180024181  mov     eax, edi
0x180024183  mov     [rsp+190h+var_14C], eax
0x180024187  test    eax, eax
0x180024189  jns     loc_18002440C
0x18002418f  mov     cl, cs:byte_180298F4C
0x180024195  test    cl, cl
0x180024197  jz      loc_1800242D3
0x18002419d  cmp     eax, edi
0x18002419f  jnz     short loc_1800241AF
0x1800241a1  mov     cs:byte_180298F4C, r12b
0x1800241a8  mov     cs:byte_180298F4E, r12b
0x1800241af  call    ?IsElevatedProcess@@YAHXZ; IsElevatedProcess(void)
0x1800241b4  test    eax, eax
0x1800241b6  jnz     loc_1800242F4
0x1800241bc  mov     al, cs:byte_180298F4C
0x1800241c2  test    al, al
0x1800241c4  jz      loc_18002443D
0x1800241ca  call    ?IsProtectedModeEnabled@@YAHXZ; IsProtectedModeEnabled(void)
0x1800241cf  test    eax, eax
0x1800241d1  jz      short loc_1800241DA
0x1800241d3  mov     cs:byte_180298F5C, r12b
0x1800241da  call    ?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1800241df  test    eax, eax
0x1800241e1  jz      loc_180024465
0x1800241e7  mov     eax, r14d
0x1800241ea  mov     rcx, [rbp+90h+var_30]
0x1800241ee  xor     rcx, rsp; StackCookie
0x1800241f1  call    __security_check_cookie
0x1800241f6  lea     r11, [rsp+190h+var_20]
0x1800241fe  mov     rbx, [r11+30h]
0x180024202  mov     rsi, [r11+40h]
0x180024206  mov     rsp, r11
0x180024209  pop     r15
0x18002420b  pop     r14
0x18002420d  pop     r12
0x18002420f  pop     rdi
0x180024210  pop     rbp
0x180024211  retn
0x180024212  lea     r8, [rbx+8]; bool *
0x180024216  lea     rdx, [rbx+0Ah]; bool *
0x18002421a  lea     rcx, [rbx+0Ch]; bool *
0x18002421e  call    ?GetCurrentProcessIntegrityLevel@@YAXPEA_N00@Z; GetCurrentProcessIntegrityLevel(bool *,bool *,bool *)
0x180024223  jmp     loc_180023E8D
0x180024228  cmp     [rbx+0Ah], r15b
0x18002422c  jz      loc_180024318
0x180024232  mov     [rsp+190h+hObject], r15
0x180024237  call    cs:__imp_GetCurrentProcessId
0x18002423d  mov     edx, eax; unsigned int
0x18002423f  lea     r8, [rsp+190h+hObject]; void **
0x180024244  call    ?GetProcessToken@@YAJKKPEAPEAX@Z; GetProcessToken(ulong,ulong,void * *)
0x180024249  test    eax, eax
0x18002424b  js      short loc_180024290
0x18002424d  mov     rcx, [rsp+190h+hObject]; TokenHandle
0x180024252  lea     r8, [rsp+190h+var_140]; int *
0x180024257  lea     rdx, [rsp+190h+var_150]; int *
0x18002425c  mov     [rsp+190h+var_150], r15d
0x180024261  mov     [rsp+190h+var_140], r15d
0x180024266  call    ?LUAGetSplitToken@@YAJPEAXPEAH1@Z; LUAGetSplitToken(void *,int *,int *)
0x18002426b  test    eax, eax
0x18002426d  js      short loc_180024285
0x18002426f  cmp     [rsp+190h+var_140], r15d
0x180024274  jz      short loc_180024285
0x180024276  mov     [rbx+10h], r12b
0x18002427a  cmp     [rsp+190h+var_150], r15d
0x18002427f  jnz     loc_180024342
0x180024285  mov     rcx, [rsp+190h+hObject]; hObject
0x18002428a  call    cs:__imp_CloseHandle
0x180024290  call    ?IsTokenBuiltInAdministrator@@YAHXZ; IsTokenBuiltInAdministrator(void)
0x180024295  test    eax, eax
0x180024297  jz      loc_180023EA0
0x18002429d  mov     [rbx+14h], r12b
0x1800242a1  jmp     loc_180023EA0
0x1800242a6  mov     cs:byte_180298F50, r15b
  ... truncated ...
```
