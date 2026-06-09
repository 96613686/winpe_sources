# CAppRecorderPlugin::EnableAppRecorder(wchar_t const *,void *)

- ea: `0x18002ecac`
- end: `0x18002f04f`
- name: `?EnableAppRecorder@CAppRecorderPlugin@@AEAAJPEB_WPEAX@Z`
- size: `931`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *this, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002f330`

## callees

- `0x180009ed8`
- `0x180009f00`
- `0x18000a004`
- `0x18002ecac`
- `0x18002f798`
- `0x1800302b8`
- `0x180036e08`
- `0x180036ec4`
- `0x180037098`
- `0x1800375ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002ee2e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002ee2e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002eff9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002eff9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ef59`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ef59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ed20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f02a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ed20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f02a`

## string_xrefs

- `0x18002ed53`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins`
- `0x18002eeca`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\AppRecorder`
- `0x18002ef4f`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\AppRecorder`

## pseudocode

```c
__int64 __fastcall CAppRecorderPlugin::EnableAppRecorder(CAppRecorderPlugin *this, const wchar_t *a2, wchar_t *a3)
{
  int v7; // edi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // edi
  __int64 v14; // rsi
  HKEY *phkResult; // rax
  enum _ACCESS_MODE v16; // edx
  int v17; // eax
  BYTE Data[8]; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  int v20; // [rsp+98h] [rbp+38h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+48h] BYREF

  v20 = 0;
  hKey = 0;
  dwDisposition = 0;
  *(_DWORD *)Data = 1;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids);
    return 2147942487LL;
  }
  if ( *((_DWORD *)this + 14) == 1 || *((_DWORD *)this + 15) == 1 )
    return 0;
  v7 = CheckPluginLastPromptedTime(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins",
         a3,
         2u,
         &v20);
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 24;
LABEL_12:
      WPP_SF_(v8[2], v9, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids);
    }
    goto LABEL_49;
  }
  if ( v20 )
  {
    v10 = WerPluginParseSettings(
            (CAppRecorderPlugin *)((char *)this + 80),
            2u,
            (struct KEY_DATA_TYPE *)&off_180062430,
            2,
            a2);
    v7 = v10;
    if ( v10 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 25;
LABEL_18:
        WPP_SF_d(v11[2], v12, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids, (unsigned int)v10);
      }
      goto LABEL_49;
    }
    v13 = 0;
    while ( 1 )
    {
      v14 = 568LL * v13;
      if ( !(unsigned int)_o__wcsicmp((char *)this + v14 + 84, L"AppRecorderVersion")
        && *(_DWORD *)((char *)this + v14 + 640) > 1u )
      {
        break;
      }
      if ( ++v13 >= 2 )
      {
        if ( !(unsigned int)CAppRecorderPlugin::PromptForEnableAppRecorder(this, a3) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids);
          v7 = 1;
          goto LABEL_49;
        }
        v10 = CAppRecorderPlugin::WriteAppCompatLayer(this);
        v7 = v10;
        if ( v10 >= 0 )
        {
          v10 = WerPluginWriteSettings(
                  (CAppRecorderPlugin *)((char *)this + 80),
                  2u,
                  HKEY_CURRENT_USER,
                  L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\AppRecorder");
          v7 = v10;
          if ( v10 >= 0 )
          {
            phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
            if ( RegCreateKeyExW(
                   HKEY_CURRENT_USER,
                   L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\AppRecorder",
                   0,
                   0,
                   0,
                   0x60002u,
                   0,
                   phkResult,
                   &dwDisposition) )
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v9 = 29;
                goto LABEL_12;
              }
            }
            else
            {
              v17 = WerPluginAdjustAppContainerAccessToKey(hKey, v16, 0x80010002);
              v7 = v17;
              if ( v17 < 0
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  30,
                  WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids,
                  (unsigned int)v17);
              }
              if ( !RegSetValueExW(hKey, L"AppRecorderEnabled", 0, 4u, Data, 4u) )
                break;
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v9 = 31;
                goto LABEL_12;
              }
            }
          }
          else
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v12 = 28;
              goto LABEL_18;
            }
          }
        }
        else
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v12 = 27;
            goto LABEL_18;
          }
        }
        goto LABEL_49;
      }
    }
  }
  v7 = 0;
LABEL_49:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002ecac  mov     [rsp-28h+arg_0], rbx
0x18002ecb1  mov     [rsp-28h+arg_10], rsi
0x18002ecb6  push    rbp
0x18002ecb7  push    rdi
0x18002ecb8  push    r13
0x18002ecba  push    r14
0x18002ecbc  push    r15
0x18002ecbe  mov     rbp, rsp
0x18002ecc1  sub     rsp, 60h
0x18002ecc5  mov     r15, r8
0x18002ecc8  mov     rsi, rdx
0x18002eccb  mov     rbx, rcx
0x18002ecce  mov     [rbp+arg_8], 0
0x18002ecd5  xor     ecx, ecx
0x18002ecd7  mov     [rbp+hKey], rcx
0x18002ecdb  mov     [rbp+dwDisposition], ecx
0x18002ecde  lea     r13d, [rcx+1]
0x18002ece2  mov     dword ptr [rbp+Data], r13d
0x18002ece6  test    rdx, rdx
0x18002ece9  jnz     short loc_18002ED30
0x18002eceb  lea     rbx, WPP_GLOBAL_Control
0x18002ecf2  mov     rax, cs:WPP_GLOBAL_Control
0x18002ecf9  cmp     rax, rbx
0x18002ecfc  jz      short loc_18002ED1B
0x18002ecfe  test    [rax+1Ch], r13b
0x18002ed02  jz      short loc_18002ED1B
0x18002ed04  lea     edx, [rsi+17h]
0x18002ed07  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x18002ed0e  mov     rcx, [rax+10h]
0x18002ed12  call    WPP_SF_
0x18002ed17  mov     rcx, [rbp+hKey]; hKey
0x18002ed1b  test    rcx, rcx
0x18002ed1e  jz      short loc_18002ED26
0x18002ed20  call    cs:__imp_RegCloseKey
0x18002ed26  mov     eax, 80070057h
0x18002ed2b  jmp     loc_18002F036
0x18002ed30  cmp     [rbx+38h], r13d
0x18002ed34  jz      loc_18002F034
0x18002ed3a  cmp     [rbx+3Ch], r13d
0x18002ed3e  jz      loc_18002F034
0x18002ed44  lea     rax, [rbp+arg_8]
0x18002ed48  mov     qword ptr [rsp+60h+dwOptions], rax; int *
0x18002ed4d  mov     r9d, 2; unsigned int
0x18002ed53  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\Windows E"...
0x18002ed5a  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18002ed61  call    ?CheckPluginLastPromptedTime@@YAJPEAUHKEY__@@PEB_W1KPEAH@Z; CheckPluginLastPromptedTime(HKEY__ *,wchar_t const *,wchar_t const *,ulong,int *)
0x18002ed66  mov     edi, eax
0x18002ed68  test    eax, eax
0x18002ed6a  jns     short loc_18002EDA7
0x18002ed6c  lea     rbx, WPP_GLOBAL_Control
0x18002ed73  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed7a  cmp     rcx, rbx
0x18002ed7d  jz      loc_18002F021
0x18002ed83  test    [rcx+1Ch], r13b
0x18002ed87  jz      loc_18002F021
0x18002ed8d  mov     edx, 18h
0x18002ed92  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x18002ed99  mov     rcx, [rcx+10h]
0x18002ed9d  call    WPP_SF_
0x18002eda2  jmp     loc_18002F021
0x18002eda7  cmp     [rbp+arg_8], 0
0x18002edab  jz      loc_18002F01F
0x18002edb1  lea     r14, [rbx+50h]
0x18002edb5  mov     qword ptr [rsp+60h+dwOptions], rsi; wchar_t *
0x18002edba  mov     edx, 2; unsigned int
0x18002edbf  mov     r9d, edx; unsigned int
0x18002edc2  lea     r8, off_180062430; struct KEY_DATA_TYPE *
0x18002edc9  mov     rcx, r14; struct _AUTOVERIFIER_IPT_SETTINGS *
0x18002edcc  call    ?WerPluginParseSettings@@YAJPEAU_AUTOVERIFIER_IPT_SETTINGS@@KPEAUKEY_DATA_TYPE@@KPEB_W@Z; WerPluginParseSettings(_AUTOVERIFIER_IPT_SETTINGS *,ulong,KEY_DATA_TYPE *,ulong,wchar_t const *)
0x18002edd1  mov     edi, eax
0x18002edd3  test    eax, eax
0x18002edd5  jns     short loc_18002EE15
0x18002edd7  lea     rbx, WPP_GLOBAL_Control
0x18002edde  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ede5  cmp     rcx, rbx
0x18002ede8  jz      loc_18002F021
0x18002edee  test    [rcx+1Ch], r13b
0x18002edf2  jz      loc_18002F021
0x18002edf8  mov     edx, 19h
0x18002edfd  mov     r9d, eax
0x18002ee00  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x18002ee07  mov     rcx, [rcx+10h]
0x18002ee0b  call    WPP_SF_d
0x18002ee10  jmp     loc_18002F021
0x18002ee15  xor     edi, edi
0x18002ee17  mov     eax, edi
0x18002ee19  imul    rsi, rax, 238h
0x18002ee20  lea     rcx, [rbx+54h]
0x18002ee24  add     rcx, rsi
0x18002ee27  lea     rdx, aApprecorderver; "AppRecorderVersion"
0x18002ee2e  call    cs:__imp__o__wcsicmp
0x18002ee34  test    eax, eax
0x18002ee36  jnz     short loc_18002EE46
0x18002ee38  cmp     [rsi+rbx+280h], r13d
0x18002ee40  ja      loc_18002F01F
0x18002ee46  add     edi, r13d
0x18002ee49  cmp     edi, 2
0x18002ee4c  jb      short loc_18002EE17
0x18002ee4e  mov     rdx, r15; void *
0x18002ee51  mov     rcx, rbx; this
0x18002ee54  call    ?PromptForEnableAppRecorder@CAppRecorderPlugin@@AEAAHPEAX@Z; CAppRecorderPlugin::PromptForEnableAppRecorder(void *)
0x18002ee59  test    eax, eax
0x18002ee5b  jnz     short loc_18002EE91
0x18002ee5d  lea     rbx, WPP_GLOBAL_Control
0x18002ee64  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee6b  cmp     rcx, rbx
0x18002ee6e  jz      short loc_18002EE89
0x18002ee70  test    byte ptr [rcx+1Ch], 4
0x18002ee74  jz      short loc_18002EE89
0x18002ee76  lea     edx, [rax+1Ah]
0x18002ee79  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x18002ee80  mov     rcx, [rcx+10h]
0x18002ee84  call    WPP_SF_
0x18002ee89  mov     edi, r13d
0x18002ee8c  jmp     loc_18002F021
0x18002ee91  mov     rcx, rbx; this
0x18002ee94  call    ?WriteAppCompatLayer@CAppRecorderPlugin@@AEAAJXZ; CAppRecorderPlugin::WriteAppCompatLayer(void)
0x18002ee99  mov     edi, eax
0x18002ee9b  test    eax, eax
0x18002ee9d  jns     short loc_18002EECA
0x18002ee9f  lea     rbx, WPP_GLOBAL_Control
0x18002eea6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eead  cmp     rcx, rbx
0x18002eeb0  jz      loc_18002F021
0x18002eeb6  test    [rcx+1Ch], r13b
0x18002eeba  jz      loc_18002F021
0x18002eec0  mov     edx, 1Bh
0x18002eec5  jmp     loc_18002EDFD
0x18002eeca  lea     r9, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\Windows E"...
0x18002eed1  mov     rbx, 0FFFFFFFF80000001h
0x18002eed8  mov     r8, rbx; HKEY
0x18002eedb  mov     edx, 2; unsigned int
0x18002eee0  mov     rcx, r14; struct _AUTOVERIFIER_IPT_SETTINGS *
0x18002eee3  call    ?WerPluginWriteSettings@@YAJPEAU_AUTOVERIFIER_IPT_SETTINGS@@KPEAUHKEY__@@PEB_W@Z; WerPluginWriteSettings(_AUTOVERIFIER_IPT_SETTINGS *,ulong,HKEY__ *,wchar_t const *)
0x18002eee8  mov     edi, eax
0x18002eeea  test    eax, eax
0x18002eeec  jns     short loc_18002EF19
0x18002eeee  lea     rbx, WPP_GLOBAL_Control
0x18002eef5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eefc  cmp     rcx, rbx
0x18002eeff  jz      loc_18002F021
0x18002ef05  test    [rcx+1Ch], r13b
0x18002ef09  jz      loc_18002F021
0x18002ef0f  mov     edx, 1Ch
0x18002ef14  jmp     loc_18002EDFD
0x18002ef19  lea     rcx, [rbp+hKey]
0x18002ef1d  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18002ef22  lea     r8, [rbp+dwDisposition]
0x18002ef26  mov     [rsp+60h+lpdwDisposition], r8; lpdwDisposition
0x18002ef2b  mov     [rsp+60h+phkResult], rax; phkResult
0x18002ef30  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002ef39  mov     [rsp+60h+samDesired], 60002h; samDesired
0x18002ef41  mov     [rsp+60h+dwOptions], 0; dwOptions
0x18002ef49  xor     r9d, r9d; lpClass
0x18002ef4c  xor     r8d, r8d; Reserved
0x18002ef4f  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\Windows E"...
0x18002ef56  mov     rcx, rbx; hKey
0x18002ef59  call    cs:__imp_RegCreateKeyExW
0x18002ef5f  test    eax, eax
0x18002ef61  jz      short loc_18002EF8E
0x18002ef63  lea     rbx, WPP_GLOBAL_Control
0x18002ef6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef71  cmp     rcx, rbx
0x18002ef74  jz      loc_18002F021
0x18002ef7a  test    [rcx+1Ch], r13b
0x18002ef7e  jz      loc_18002F021
0x18002ef84  mov     edx, 1Dh
0x18002ef89  jmp     loc_18002ED92
0x18002ef8e  mov     r8d, 80010002h; unsigned int
0x18002ef94  mov     rcx, [rbp+hKey]; hKey
0x18002ef98  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x18002ef9d  mov     edi, eax
0x18002ef9f  lea     rbx, WPP_GLOBAL_Control
0x18002efa6  test    eax, eax
0x18002efa8  jns     short loc_18002EFD4
0x18002efaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002efb1  cmp     rcx, rbx
0x18002efb4  jz      short loc_18002EFD4
0x18002efb6  test    byte ptr [rcx+1Ch], 2
0x18002efba  jz      short loc_18002EFD4
0x18002efbc  mov     edx, 1Eh
0x18002efc1  mov     r9d, eax
0x18002efc4  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x18002efcb  mov     rcx, [rcx+10h]
0x18002efcf  call    WPP_SF_d
0x18002efd4  mov     [rsp+60h+samDesired], 4; cbData
0x18002efdc  lea     rax, [rbp+Data]
0x18002efe0  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18002efe5  mov     r9d, 4; dwType
0x18002efeb  xor     r8d, r8d; Reserved
0x18002efee  lea     rdx, aApprecorderena; "AppRecorderEnabled"
0x18002eff5  mov     rcx, [rbp+hKey]; hKey
0x18002eff9  call    cs:__imp_RegSetValueExW
0x18002efff  test    eax, eax
0x18002f001  jz      short loc_18002F01F
0x18002f003  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f00a  cmp     rcx, rbx
0x18002f00d  jz      short loc_18002F021
0x18002f00f  test    [rcx+1Ch], r13b
0x18002f013  jz      short loc_18002F021
0x18002f015  mov     edx, 1Fh
0x18002f01a  jmp     loc_18002ED92
0x18002f01f  xor     edi, edi
0x18002f021  mov     rcx, [rbp+hKey]; hKey
0x18002f025  test    rcx, rcx
0x18002f028  jz      short loc_18002F030
0x18002f02a  call    cs:__imp_RegCloseKey
0x18002f030  mov     eax, edi
0x18002f032  jmp     short loc_18002F036
0x18002f034  xor     eax, eax
0x18002f036  lea     r11, [rsp+60h+var_s0]
0x18002f03b  mov     rbx, [r11+30h]
0x18002f03f  mov     rsi, [r11+40h]
0x18002f043  mov     rsp, r11
0x18002f046  pop     r15
0x18002f048  pop     r14
0x18002f04a  pop     r13
0x18002f04c  pop     rdi
0x18002f04d  pop     rbp
0x18002f04e  retn
```
