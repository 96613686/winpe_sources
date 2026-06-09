# CNotifyUILanguageChangeTask::RunTask(void)

- ea: `0x18002df70`
- end: `0x18002e19c`
- name: `?RunTask@CNotifyUILanguageChangeTask@@UEAAJXZ`
- size: `556`
- prototype: `__int64 __fastcall(CNotifyUILanguageChangeTask *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003470`
- `0x18000ac48`
- `0x18001aa9c`
- `0x1800230b0`
- `0x180026b68`
- `0x18002df70`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `SHLWAPI!SHDeleteValueW` at `0x18002e0f9`
- `SHLWAPI!SHDeleteValueW` at `0x18002e0f9`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x18002e0b5`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x18002e0b5`
- `ntdll!RtlNtStatusToDosError` at `0x18002e016`
- `ntdll!RtlNtStatusToDosError` at `0x18002e016`
- `ntdll!RtlpVerifyAndCommitUILanguageSettings` at `0x18002e00e`
- `ntdll!RtlpVerifyAndCommitUILanguageSettings` at `0x18002e00e`
- `ext-ms-win-kernel32-localization-l1-1-0!NotifyUILanguageChange` at `0x18002e067`
- `ext-ms-win-kernel32-localization-l1-1-0!NotifyUILanguageChange` at `0x18002e067`

## string_xrefs

- `0x18002e107`: `shell\oobe\machine\plugins\language\languagetasks.cpp`
- `0x18002dffa`: `Failed to initialize notify language done cache setting before calling NotifyUILanguageChange`
- `0x18002e0d5`: `Failed to verify and commit UI language settings [0x%08X]`
- `0x18002e033`: `Successfully verified and committed UI language settings`
- `0x18002e15a`: `Failed to set notify language done cache setting`
- `0x18002e0c6`: `Failed to clear notify UI language change task thread's preferred UI language list [0x%08X]`

## pseudocode

```c
__int64 __fastcall CNotifyUILanguageChangeTask::RunTask(CNotifyUILanguageChangeTask *this, __int64 a2, __int64 a3)
{
  __int64 *v4; // rcx
  __int64 v5; // rax
  char v6; // di
  NTSTATUS v7; // eax
  signed int v8; // eax
  __int64 Error; // rbx
  LSTATUS v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  int pdwStatusRtrn; // [rsp+20h] [rbp-48h]
  DWORD v15; // [rsp+30h] [rbp-38h] BYREF
  ULONG pulNumLanguages; // [rsp+34h] [rbp-34h] BYREF
  int v17[4]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v18; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_OOBE_Machine_Plugins_Context,
      NotifyUILanguageChangeTask_Start,
      a3,
      1,
      v17);
  v4 = (__int64 *)*((_QWORD *)this + 69);
  v18 = 0;
  *(_OWORD *)v17 = 0;
  v17[2] = 0;
  v5 = *v4;
  LOWORD(v17[0]) = 19;
  if ( (*(int (__fastcall **)(__int64 *, const WCHAR *, int *))(v5 + 32))(v4, L"NOTIFYLANGUAGEDONE", v17) < 0 )
    UnattendLogW(1, L"Failed to initialize notify language done cache setting before calling NotifyUILanguageChange");
  v6 = 0;
  v7 = RtlpVerifyAndCommitUILanguageSettings(0);
  v8 = RtlNtStatusToDosError(v7);
  LODWORD(Error) = v8;
  if ( v8 > 0 )
    LODWORD(Error) = (unsigned __int16)v8 | 0x80070000;
  if ( (int)Error < 0 )
  {
    UnattendLogW(1, L"Failed to verify and commit UI language settings [0x%08X]", (unsigned int)Error);
  }
  else
  {
    UnattendLogW(0, L"Successfully verified and committed UI language settings");
    v15 = 0;
    if ( NotifyUILanguageChange(8u, 0, 0, *((_BYTE *)this + 560) != 0, &v15) )
    {
      v6 = 1;
      UnattendLogW(0, L"Successfully notified UI language change");
    }
    else
    {
      LODWORD(Error) = v15;
      if ( (int)v15 > 0 )
        LODWORD(Error) = (unsigned __int16)v15 | 0x80070000;
      UnattendLogW(1, L"Failed to notify UI language change [0x%08X]", (unsigned int)Error);
    }
    pulNumLanguages = 0;
    if ( !SetThreadPreferredUILanguages(0, 0, &pulNumLanguages) )
    {
      Error = (unsigned int)ResultFromKnownLastError();
      UnattendLogW(
        1,
        L"Failed to clear notify UI language change task thread's preferred UI language list [0x%08X]",
        Error);
    }
  }
  v10 = SHDeleteValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
          L"LanguageChoicePending");
  if ( v10 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"shell\\oobe\\machine\\plugins\\language\\languagetasks.cpp",
      (const char *)(unsigned int)v10,
      pdwStatusRtrn);
  v11 = *((_QWORD *)this + 69);
  v18 = 0;
  *(_OWORD *)v17 = 0;
  LOWORD(v17[0]) = 19;
  v17[2] = 2 - (v6 != 0);
  if ( (*(int (__fastcall **)(__int64, const WCHAR *, int *))(*(_QWORD *)v11 + 32LL))(v11, L"NOTIFYLANGUAGEDONE", v17) < 0 )
    UnattendLogW(1, L"Failed to set notify language done cache setting");
  if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
    McTemplateU0q_EventWriteTransfer(v12, NotifyUILanguageChangeTask_Stop, (unsigned int)Error);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002df70  push    rbp
0x18002df72  push    rbx
0x18002df73  push    rsi
0x18002df74  push    rdi
0x18002df75  push    r13
0x18002df77  push    r14
0x18002df79  mov     rbp, rsp
0x18002df7c  sub     rsp, 68h
0x18002df80  mov     rax, cs:__security_cookie
0x18002df87  xor     rax, rsp
0x18002df8a  mov     [rbp+var_18], rax
0x18002df8e  mov     r14d, 1
0x18002df94  mov     rsi, rcx
0x18002df97  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, r14b
0x18002df9e  jz      short loc_18002DFBF
0x18002dfa0  lea     rax, [rbp+var_30]
0x18002dfa4  mov     r9d, r14d
0x18002dfa7  lea     rdx, NotifyUILanguageChangeTask_Start
0x18002dfae  mov     qword ptr [rsp+68h+pdwStatusRtrn], rax; int
0x18002dfb3  lea     rcx, Microsoft_Windows_OOBE_Machine_Plugins_Context
0x18002dfba  call    McGenEventWrite_EventWriteTransfer
0x18002dfbf  mov     rcx, [rsi+228h]
0x18002dfc6  lea     r8, [rbp+var_30]
0x18002dfca  xor     eax, eax
0x18002dfcc  lea     rdx, aNotifylanguage; "NOTIFYLANGUAGEDONE"
0x18002dfd3  mov     [rbp+var_20], rax
0x18002dfd7  xorps   xmm0, xmm0
0x18002dfda  movups  xmmword ptr [rbp+var_30], xmm0
0x18002dfde  mov     [rbp+var_30+8], eax
0x18002dfe1  lea     r13d, [rax+13h]
0x18002dfe5  mov     rax, [rcx]
0x18002dfe8  mov     word ptr [rbp+var_30], r13w
0x18002dfed  mov     rax, [rax+20h]
0x18002dff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dff6  test    eax, eax
0x18002dff8  jns     short loc_18002E009
0x18002dffa  lea     rdx, aFailedToInitia_0; "Failed to initialize notify language do"...
0x18002e001  mov     ecx, r14d
0x18002e004  call    UnattendLogW
0x18002e009  xor     ecx, ecx
0x18002e00b  xor     dil, dil
0x18002e00e  call    cs:__imp_RtlpVerifyAndCommitUILanguageSettings
0x18002e014  mov     ecx, eax; Status
0x18002e016  call    cs:__imp_RtlNtStatusToDosError
0x18002e01c  mov     ebx, eax
0x18002e01e  test    eax, eax
0x18002e020  jle     short loc_18002E02B
0x18002e022  movzx   ebx, ax
0x18002e025  or      ebx, 80070000h
0x18002e02b  test    ebx, ebx
0x18002e02d  js      loc_18002E0D2
0x18002e033  lea     rdx, aSuccessfullyVe; "Successfully verified and committed UI "...
0x18002e03a  xor     ecx, ecx
0x18002e03c  call    UnattendLogW
0x18002e041  xor     r9d, r9d
0x18002e044  mov     [rbp+var_38], 0
0x18002e04b  cmp     [rsi+230h], dil
0x18002e052  lea     rax, [rbp+var_38]
0x18002e056  mov     qword ptr [rsp+68h+pdwStatusRtrn], rax; pdwStatusRtrn
0x18002e05b  setnz   r9b; dwReserved
0x18002e05f  xor     edx, edx; pcwstrNewLanguage
0x18002e061  xor     r8d, r8d; pcwstrPreviousLanguage
0x18002e064  lea     ecx, [rdx+8]; dwFlags
0x18002e067  call    cs:__imp_NotifyUILanguageChange
0x18002e06d  test    eax, eax
0x18002e06f  jz      short loc_18002E084
0x18002e071  lea     rdx, aSuccessfullyNo; "Successfully notified UI language chang"...
0x18002e078  xor     ecx, ecx
0x18002e07a  mov     dil, r14b
0x18002e07d  call    UnattendLogW
0x18002e082  jmp     short loc_18002E0A6
0x18002e084  mov     ebx, [rbp+var_38]
0x18002e087  test    ebx, ebx
0x18002e089  jle     short loc_18002E094
0x18002e08b  movzx   ebx, bx
0x18002e08e  or      ebx, 80070000h
0x18002e094  mov     r8d, ebx
0x18002e097  lea     rdx, aFailedToNotify; "Failed to notify UI language change [0x"...
0x18002e09e  mov     ecx, r14d
0x18002e0a1  call    UnattendLogW
0x18002e0a6  lea     r8, [rbp+pulNumLanguages]; pulNumLanguages
0x18002e0aa  mov     [rbp+pulNumLanguages], 0
0x18002e0b1  xor     edx, edx; pwszLanguagesBuffer
0x18002e0b3  xor     ecx, ecx; dwFlags
0x18002e0b5  call    cs:__imp_SetThreadPreferredUILanguages
0x18002e0bb  test    eax, eax
0x18002e0bd  jnz     short loc_18002E0E4
0x18002e0bf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002e0c4  mov     ebx, eax
0x18002e0c6  lea     rdx, aFailedToClearN; "Failed to clear notify UI language chan"...
0x18002e0cd  mov     r8d, eax
0x18002e0d0  jmp     short loc_18002E0DC
0x18002e0d2  mov     r8d, ebx
0x18002e0d5  lea     rdx, aFailedToVerify; "Failed to verify and commit UI language"...
0x18002e0dc  mov     ecx, r14d
0x18002e0df  call    UnattendLogW
0x18002e0e4  lea     r8, pszValue; "LanguageChoicePending"
0x18002e0eb  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002e0f2  lea     rdx, pszSubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002e0f9  call    cs:__imp_SHDeleteValueW
0x18002e0ff  test    eax, eax
0x18002e101  jns     short loc_18002E11B
0x18002e103  mov     rcx, [rbp+30h]; this
0x18002e107  lea     r8, aShellOobeMachi_37; "shell\\oobe\\machine\\plugins\\language"...
0x18002e10e  mov     r9d, eax; char *
0x18002e111  mov     edx, 0B9h; void *
0x18002e116  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002e11b  mov     rcx, [rsi+228h]
0x18002e122  lea     r8, [rbp+var_30]
0x18002e126  xor     eax, eax
0x18002e128  lea     rdx, aNotifylanguage; "NOTIFYLANGUAGEDONE"
0x18002e12f  mov     [rbp+var_20], rax
0x18002e133  xorps   xmm0, xmm0
0x18002e136  movups  xmmword ptr [rbp+var_30], xmm0
0x18002e13a  neg     dil
0x18002e13d  mov     word ptr [rbp+var_30], r13w
0x18002e142  sbb     eax, eax
0x18002e144  add     eax, 2
0x18002e147  mov     [rbp+var_30+8], eax
0x18002e14a  mov     rax, [rcx]
0x18002e14d  mov     rax, [rax+20h]
0x18002e151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e156  test    eax, eax
0x18002e158  jns     short loc_18002E169
0x18002e15a  lea     rdx, aFailedToSetNot; "Failed to set notify language done cach"...
0x18002e161  mov     ecx, r14d
0x18002e164  call    UnattendLogW
0x18002e169  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, r14b
0x18002e170  jz      short loc_18002E181
0x18002e172  mov     r8d, ebx
0x18002e175  lea     rdx, NotifyUILanguageChangeTask_Stop
0x18002e17c  call    McTemplateU0q_EventWriteTransfer
0x18002e181  mov     eax, ebx
0x18002e183  mov     rcx, [rbp+var_18]
0x18002e187  xor     rcx, rsp; StackCookie
0x18002e18a  call    __security_check_cookie
0x18002e18f  add     rsp, 68h
0x18002e193  pop     r14
0x18002e195  pop     r13
0x18002e197  pop     rdi
0x18002e198  pop     rsi
0x18002e199  pop     rbx
0x18002e19a  pop     rbp
0x18002e19b  retn
```
