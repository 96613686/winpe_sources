# CEulaPlugin::Update(void)

- ea: `0x180022560`
- end: `0x18002273a`
- name: `?Update@CEulaPlugin@@UEAAJXZ`
- size: `474`
- prototype: `__int64 __fastcall(CEulaPlugin *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180022560`
- `0x1800230b0`
- `0x1800b8834`
- `0x1800bf3e0`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryBOOL` at `0x180022593`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryBOOL` at `0x180022593`
- `WINBRAND!InstallEULA` at `0x1800225db`
- `WINBRAND!InstallEULA` at `0x1800225db`
- `ntdll!RtlPublishWnfStateData` at `0x1800226d7`
- `ntdll!RtlPublishWnfStateData` at `0x1800226d7`

## string_xrefs

- `0x1800225ae`: `shell\oobe\machine\plugins\eula\eulaplugin.cpp`
- `0x1800226e9`: `shell\oobe\machine\plugins\eula\eulaplugin.cpp`
- `0x1800225fb`: `Successfully installed EULA for language [%s], region [%s], channel [%s], edition [%s]`
- `0x180022658`: `Failed to install EULA for language [%s], region [%s], channel [%s], edition [%s] with hr=0x%08X`
- `0x1800226a9`: `The EULA was already installed during setup.  Skipping install of EULA [%s].`
- `0x1800226ff`: `Unknown edition for EULA.  Cannot install EULA [%s].`
- `0x180022717`: `No EULA file specified on update.`

## pseudocode

```c
__int64 __fastcall CEulaPlugin::Update(CEulaPlugin *this)
{
  signed int v2; // eax
  bool v3; // sf
  int v4; // esi
  const wchar_t *v5; // r8
  __int64 v6; // rax
  const wchar_t *v7; // rcx
  const wchar_t *v8; // r9
  const wchar_t *v9; // rax
  const wchar_t *v10; // rax
  __int64 v11; // r8
  int v12; // eax
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v16; // [rsp+50h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 9) )
  {
    v2 = SetPersistedRegistryBOOL(
           L"SetupOOBE",
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
           L"SetupDisplayedEula",
           1);
    v3 = v2 < 0;
    if ( v2 > 0 )
    {
      v2 = (unsigned __int16)v2 | 0x80070000;
      v3 = v2 < 0;
    }
    if ( v3 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"shell\\oobe\\machine\\plugins\\eula\\eulaplugin.cpp",
        (const char *)(unsigned int)v2,
        v14);
    if ( *((_QWORD *)this + 8) )
    {
      v4 = InstallEULA(*((_QWORD *)this + 5), *((_QWORD *)this + 6), *((_QWORD *)this + 7));
      v5 = L"null";
      v6 = *((_QWORD *)this + 8);
      v7 = L"null";
      v8 = L"null";
      if ( v4 < 0 )
      {
        if ( v6 )
          v7 = (const wchar_t *)*((_QWORD *)this + 8);
        v10 = L"null";
        if ( *((_QWORD *)this + 7) )
          v10 = (const wchar_t *)*((_QWORD *)this + 7);
        if ( *((_QWORD *)this + 6) )
          v8 = (const wchar_t *)*((_QWORD *)this + 6);
        if ( *((_QWORD *)this + 5) )
          v5 = (const wchar_t *)*((_QWORD *)this + 5);
        UnattendLogW(
          1,
          L"Failed to install EULA for language [%s], region [%s], channel [%s], edition [%s] with hr=0x%08X",
          v5,
          v8,
          v10,
          v7,
          v4);
      }
      else
      {
        if ( v6 )
          v7 = (const wchar_t *)*((_QWORD *)this + 8);
        v9 = L"null";
        if ( *((_QWORD *)this + 7) )
          v9 = (const wchar_t *)*((_QWORD *)this + 7);
        if ( *((_QWORD *)this + 6) )
          v8 = (const wchar_t *)*((_QWORD *)this + 6);
        if ( *((_QWORD *)this + 5) )
          v5 = (const wchar_t *)*((_QWORD *)this + 5);
        UnattendLogW(
          0,
          L"Successfully installed EULA for language [%s], region [%s], channel [%s], edition [%s]",
          v5,
          v8,
          v9,
          v7);
        return (unsigned int)CBasePlugin::_SetGlobalSettingBool(this, L"EULAACCEPT", 1);
      }
    }
    else
    {
      v11 = *((_QWORD *)this + 9);
      if ( *((_BYTE *)this + 80) )
      {
        v4 = 0;
        UnattendLogW(2, L"The EULA was already installed during setup.  Skipping install of EULA [%s].", v11);
        v16 = 1;
        v12 = RtlPublishWnfStateData(WNF_OLIC_OS_LICENSE_TERMS_ACCEPTED, 0, &v16, 4) | 0x10000000;
        if ( v12 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x10C,
            (unsigned int)"shell\\oobe\\machine\\plugins\\eula\\eulaplugin.cpp",
            (const char *)(unsigned int)v12,
            0);
      }
      else
      {
        v4 = -2147418113;
        UnattendLogW(1, L"Unknown edition for EULA.  Cannot install EULA [%s].", v11);
      }
    }
  }
  else
  {
    v4 = -2147024894;
    UnattendLogW(1, L"No EULA file specified on update.");
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180022560  mov     [rsp+arg_8], rbx
0x180022565  push    rsi
0x180022566  sub     rsp, 40h
0x18002256a  cmp     qword ptr [rcx+48h], 0
0x18002256f  mov     rbx, rcx
0x180022572  jz      loc_180022717
0x180022578  mov     r9d, 1
0x18002257e  lea     r8, aSetupdisplayed_1; "SetupDisplayedEula"
0x180022585  lea     rdx, aSoftwareMicros_19; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002258c  lea     rcx, aSetupoobe; "SetupOOBE"
0x180022593  call    cs:__imp_SetPersistedRegistryBOOL
0x180022599  test    eax, eax
0x18002259b  jle     short loc_1800225A7
0x18002259d  movzx   eax, ax
0x1800225a0  or      eax, 80070000h
0x1800225a5  test    eax, eax
0x1800225a7  jns     short loc_1800225C2
0x1800225a9  mov     rcx, [rsp+48h]; this
0x1800225ae  lea     r8, aShellOobeMachi_17; "shell\\oobe\\machine\\plugins\\eula\\eu"...
0x1800225b5  mov     r9d, eax; char *
0x1800225b8  mov     edx, 0E8h; void *
0x1800225bd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800225c2  mov     r9, [rbx+40h]
0x1800225c6  test    r9, r9
0x1800225c9  jz      loc_18002269D
0x1800225cf  mov     r8, [rbx+38h]
0x1800225d3  mov     rdx, [rbx+30h]
0x1800225d7  mov     rcx, [rbx+28h]
0x1800225db  call    cs:__imp_InstallEULA
0x1800225e1  mov     esi, eax
0x1800225e3  lea     r8, aNull; "null"
0x1800225ea  mov     rax, [rbx+40h]
0x1800225ee  mov     rcx, r8
0x1800225f1  mov     r9, r8
0x1800225f4  test    esi, esi
0x1800225f6  js      short loc_180022651
0x1800225f8  test    rax, rax
0x1800225fb  lea     rdx, aSuccessfullyIn_0; "Successfully installed EULA for languag"...
0x180022602  cmovnz  rcx, rax
0x180022606  cmp     qword ptr [rbx+38h], 0
0x18002260b  mov     rax, r8
0x18002260e  mov     [rsp+48h+var_20], rcx
0x180022613  cmovnz  rax, [rbx+38h]
0x180022618  cmp     qword ptr [rbx+30h], 0
0x18002261d  mov     qword ptr [rsp+48h+var_28], rax
0x180022622  cmovnz  r9, [rbx+30h]
0x180022627  cmp     qword ptr [rbx+28h], 0
0x18002262c  cmovnz  r8, [rbx+28h]
0x180022631  xor     ecx, ecx
0x180022633  call    UnattendLogW
0x180022638  mov     r8b, 1; bool
0x18002263b  lea     rdx, aEulaaccept; "EULAACCEPT"
0x180022642  mov     rcx, rbx; this
0x180022645  call    ?_SetGlobalSettingBool@CBasePlugin@@IEAAJPEBG_N@Z; CBasePlugin::_SetGlobalSettingBool(ushort const *,bool)
0x18002264a  mov     esi, eax
0x18002264c  jmp     loc_18002272D
0x180022651  test    rax, rax
0x180022654  mov     [rsp+48h+var_18], esi
0x180022658  lea     rdx, aFailedToInstal_0; "Failed to install EULA for language [%s"...
0x18002265f  cmovnz  rcx, rax
0x180022663  cmp     qword ptr [rbx+38h], 0
0x180022668  mov     rax, r8
0x18002266b  mov     [rsp+48h+var_20], rcx
0x180022670  cmovnz  rax, [rbx+38h]
0x180022675  mov     ecx, 1
0x18002267a  cmp     qword ptr [rbx+30h], 0
0x18002267f  mov     qword ptr [rsp+48h+var_28], rax
0x180022684  cmovnz  r9, [rbx+30h]
0x180022689  cmp     qword ptr [rbx+28h], 0
0x18002268e  cmovnz  r8, [rbx+28h]
0x180022693  call    UnattendLogW
0x180022698  jmp     loc_18002272D
0x18002269d  cmp     byte ptr [rbx+50h], 0
0x1800226a1  mov     r8, [rbx+48h]
0x1800226a5  jz      short loc_1800226FF
0x1800226a7  xor     esi, esi
0x1800226a9  lea     rdx, aTheEulaWasAlre; "The EULA was already installed during s"...
0x1800226b0  lea     ecx, [rsi+2]
0x1800226b3  call    UnattendLogW
0x1800226b8  mov     rcx, cs:WNF_OLIC_OS_LICENSE_TERMS_ACCEPTED
0x1800226bf  lea     r9d, [rsi+4]
0x1800226c3  lea     r8, [rsp+48h+arg_0]
0x1800226c8  mov     [rsp+48h+arg_0], 1
0x1800226d0  xor     edx, edx
0x1800226d2  mov     qword ptr [rsp+48h+var_28], rsi; int
0x1800226d7  call    cs:__imp_RtlPublishWnfStateData
0x1800226dd  or      eax, 10000000h
0x1800226e2  jge     short loc_18002272D
0x1800226e4  mov     rcx, [rsp+48h]; this
0x1800226e9  lea     r8, aShellOobeMachi_17; "shell\\oobe\\machine\\plugins\\eula\\eu"...
0x1800226f0  mov     r9d, eax; char *
0x1800226f3  mov     edx, 10Ch; void *
0x1800226f8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800226fd  jmp     short loc_18002272D
0x1800226ff  lea     rdx, aUnknownEdition; "Unknown edition for EULA.  Cannot insta"...
0x180022706  mov     ecx, 1
0x18002270b  mov     esi, 8000FFFFh
0x180022710  call    UnattendLogW
0x180022715  jmp     short loc_18002272D
0x180022717  lea     rdx, aNoEulaFileSpec; "No EULA file specified on update."
0x18002271e  mov     ecx, 1
0x180022723  mov     esi, 80070002h
0x180022728  call    UnattendLogW
0x18002272d  mov     rbx, [rsp+48h+arg_8]
0x180022732  mov     eax, esi
0x180022734  add     rsp, 40h
0x180022738  pop     rsi
0x180022739  retn
```
