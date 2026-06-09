# COfflineFilesSetting::DeletePreferenceInternal(ulong)

- ea: `0x18005bd80`
- end: `0x18005bf57`
- name: `?DeletePreferenceInternal@COfflineFilesSetting@@UEAAJK@Z`
- size: `471`
- prototype: `int(COfflineFilesSetting *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180023520`
- `0x180029ce4`
- `0x18002f10c`
- `0x180039610`
- `0x18003c5ec`
- `0x18005bd80`
- `0x18005caf4`
- `0x180080d34`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18005be31`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005be31`
- `ntdll!RtlReleaseResource` at `0x18005beb4`
- `ntdll!RtlReleaseResource` at `0x18005beb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005bf34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005bf34`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005be8d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005be8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bea7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bea7`
- `ADVAPI32!SetThreadToken` at `0x18005bf20`
- `ADVAPI32!SetThreadToken` at `0x18005bf20`

## pseudocode

```c
__int64 __fastcall COfflineFilesSetting::DeletePreferenceInternal(COfflineFilesSetting *this, unsigned int a2)
{
  const struct SETTING_DESCRIPTOR *v3; // rcx
  int PreferenceInfoFromDescriptor; // ebx
  COfflineFilesSetting *v5; // rcx
  HKEY v6; // rdi
  LSTATUS v7; // eax
  const wchar_t *v8; // r9
  int v10; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v13; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE Token; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpValueName; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v16[264]; // [rsp+70h] [rbp-90h] BYREF

  v13 = 0;
  v3 = (const struct SETTING_DESCRIPTOR *)*((_QWORD *)this + 3);
  lpValueName = 0;
  v12 = 0;
  LODWORD(hKey) = 0;
  PreferenceInfoFromDescriptor = CscSettingp_GetPreferenceInfoFromDescriptor(
                                   v3,
                                   &v13,
                                   &v12,
                                   v16,
                                   v10,
                                   &lpValueName,
                                   (int *)&hKey,
                                   a2);
  if ( PreferenceInfoFromDescriptor >= 0 )
  {
    Token = 0;
    if ( !v12
      || (PreferenceInfoFromDescriptor = CComTemporaryRevertToSelf::RevertToSelf((CComTemporaryRevertToSelf *)&Token),
          PreferenceInfoFromDescriptor >= 0) )
    {
      RtlAcquireResourceExclusive(&g_swmrSettingsLock, 1u);
      v6 = v13;
      if ( (_DWORD)hKey )
      {
        PreferenceInfoFromDescriptor = COfflineFilesSetting::_DeletePreferenceKey(v5, v13, v16);
      }
      else
      {
        hKey = 0;
        PreferenceInfoFromDescriptor = CscSetting_OpenRegKey(v13, v16, 0x20006u, 0, &hKey);
        if ( PreferenceInfoFromDescriptor >= 0 )
        {
          v7 = RegDeleteValueW(hKey, lpValueName);
          PreferenceInfoFromDescriptor = v7;
          if ( v7 > 0 )
            PreferenceInfoFromDescriptor = (unsigned __int16)v7 | 0x80070000;
          RegCloseKey(hKey);
        }
      }
      RtlReleaseResource(&g_swmrSettingsLock);
      if ( PreferenceInfoFromDescriptor >= 0
        && WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
      {
        v8 = L"Machine";
        if ( v6 != HKEY_LOCAL_MACHINE )
          v8 = L"User";
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_8efcffa2381534b4e0c94c54ca70b20c_Traceguids,
          (_DWORD)v8,
          **((_QWORD **)this + 3));
      }
    }
    if ( Token )
    {
      if ( !SetThreadToken(0, Token) )
        ResultFromLastError();
      CloseHandle(Token);
    }
  }
  return (unsigned int)PreferenceInfoFromDescriptor;
}

```

## disassembly

```asm
0x18005bd80  push    rbp
0x18005bd82  push    rbx
0x18005bd83  push    rsi
0x18005bd84  push    rdi
0x18005bd85  lea     rbp, [rsp-198h]
0x18005bd8d  sub     rsp, 298h
0x18005bd94  mov     rax, cs:__security_cookie
0x18005bd9b  xor     rax, rsp
0x18005bd9e  mov     [rbp+1B0h+var_30], rax
0x18005bda5  mov     [rsp+2B0h+var_278], edx; unsigned int
0x18005bda9  lea     rax, [rsp+2B0h+hKey]
0x18005bdae  mov     [rsp+2B0h+var_280], rax; int *
0x18005bdb3  lea     r9, [rsp+2B0h+var_240]; unsigned __int16 *
0x18005bdb8  lea     rax, [rsp+2B0h+lpValueName]
0x18005bdbd  mov     [rsp+2B0h+var_260], 0
0x18005bdc6  mov     rsi, rcx
0x18005bdc9  mov     [rsp+2B0h+var_288], rax; unsigned __int16 **
0x18005bdce  mov     rcx, [rcx+18h]; struct SETTING_DESCRIPTOR *
0x18005bdd2  lea     r8, [rsp+2B0h+var_268]; int *
0x18005bdd7  lea     rdx, [rsp+2B0h+var_260]; HKEY *
0x18005bddc  mov     [rsp+2B0h+lpValueName], 0
0x18005bde5  mov     [rsp+2B0h+var_268], 0
0x18005bded  mov     dword ptr [rsp+2B0h+hKey], 0
0x18005bdf5  call    ?CscSettingp_GetPreferenceInfoFromDescriptor@@YAJPEBUSETTING_DESCRIPTOR@@PEAPEAUHKEY__@@PEAHPEAGHPEAPEBG2K@Z; CscSettingp_GetPreferenceInfoFromDescriptor(SETTING_DESCRIPTOR const *,HKEY__ * *,int *,ushort *,int,ushort const * *,int *,ulong)
0x18005bdfa  mov     ebx, eax
0x18005bdfc  test    eax, eax
0x18005bdfe  js      loc_18005BF3A
0x18005be04  cmp     [rsp+2B0h+var_268], 0
0x18005be09  mov     [rsp+2B0h+Token], 0
0x18005be12  jz      short loc_18005BE28
0x18005be14  lea     rcx, [rsp+2B0h+Token]; this
0x18005be19  call    ?RevertToSelf@CComTemporaryRevertToSelf@@QEAAJXZ; CComTemporaryRevertToSelf::RevertToSelf(void)
0x18005be1e  mov     ebx, eax
0x18005be20  test    eax, eax
0x18005be22  js      loc_18005BF14
0x18005be28  mov     dl, 1; Wait
0x18005be2a  lea     rcx, ?g_swmrSettingsLock@@3VCSingleWriterMultiReaderLock@@A; Resource
0x18005be31  call    cs:__imp_RtlAcquireResourceExclusive
0x18005be37  cmp     dword ptr [rsp+2B0h+hKey], 0
0x18005be3c  mov     rdi, [rsp+2B0h+var_260]
0x18005be41  jz      short loc_18005BE54
0x18005be43  lea     r8, [rsp+2B0h+var_240]; unsigned __int16 *
0x18005be48  mov     rdx, rdi; HKEY
0x18005be4b  call    ?_DeletePreferenceKey@COfflineFilesSetting@@AEAAJPEAUHKEY__@@PEBG@Z; COfflineFilesSetting::_DeletePreferenceKey(HKEY__ *,ushort const *)
0x18005be50  mov     ebx, eax
0x18005be52  jmp     short loc_18005BEAD
0x18005be54  lea     rax, [rsp+2B0h+hKey]
0x18005be59  mov     [rsp+2B0h+hKey], 0
0x18005be62  xor     r9d, r9d; int
0x18005be65  mov     [rsp+2B0h+var_290], rax; HKEY *
0x18005be6a  mov     r8d, 20006h; unsigned int
0x18005be70  lea     rdx, [rsp+2B0h+var_240]; unsigned __int16 *
0x18005be75  mov     rcx, rdi; HKEY
0x18005be78  call    ?CscSetting_OpenRegKey@@YAJPEAUHKEY__@@PEBGKHPEAPEAU1@@Z; CscSetting_OpenRegKey(HKEY__ *,ushort const *,ulong,int,HKEY__ * *)
0x18005be7d  mov     ebx, eax
0x18005be7f  test    eax, eax
0x18005be81  js      short loc_18005BEAD
0x18005be83  mov     rdx, [rsp+2B0h+lpValueName]; lpValueName
0x18005be88  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18005be8d  call    cs:__imp_RegDeleteValueW
0x18005be93  mov     ebx, eax
0x18005be95  test    eax, eax
0x18005be97  jle     short loc_18005BEA2
0x18005be99  movzx   ebx, ax
0x18005be9c  or      ebx, 80070000h
0x18005bea2  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18005bea7  call    cs:__imp_RegCloseKey
0x18005bead  lea     rcx, ?g_swmrSettingsLock@@3VCSingleWriterMultiReaderLock@@A; Resource
0x18005beb4  call    cs:__imp_RtlReleaseResource
0x18005beba  test    ebx, ebx
0x18005bebc  js      short loc_18005BF14
0x18005bebe  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bec5  lea     rax, WPP_GLOBAL_Control
0x18005becc  cmp     rcx, rax
0x18005becf  jz      short loc_18005BF14
0x18005bed1  test    dword ptr [rcx+1Ch], 10000h
0x18005bed8  jz      short loc_18005BF14
0x18005beda  mov     rax, [rsi+18h]
0x18005bede  lea     r9, aMachine; "Machine"
0x18005bee5  mov     rcx, [rcx+10h]
0x18005bee9  cmp     rdi, 0FFFFFFFF80000002h
0x18005bef0  mov     edx, 14h
0x18005bef5  mov     r8, [rax]
0x18005bef8  lea     rax, aUser_1; "User"
0x18005beff  mov     [rsp+2B0h+var_290], r8
0x18005bf04  cmovnz  r9, rax
0x18005bf08  lea     r8, WPP_8efcffa2381534b4e0c94c54ca70b20c_Traceguids
0x18005bf0f  call    WPP_SF_SS
0x18005bf14  mov     rdx, [rsp+2B0h+Token]; Token
0x18005bf19  test    rdx, rdx
0x18005bf1c  jz      short loc_18005BF3A
0x18005bf1e  xor     ecx, ecx; Thread
0x18005bf20  call    cs:__imp_SetThreadToken
0x18005bf26  test    eax, eax
0x18005bf28  jnz     short loc_18005BF2F
0x18005bf2a  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18005bf2f  mov     rcx, [rsp+2B0h+Token]; hObject
0x18005bf34  call    cs:__imp_CloseHandle
0x18005bf3a  mov     eax, ebx
0x18005bf3c  mov     rcx, [rbp+1B0h+var_30]
0x18005bf43  xor     rcx, rsp; StackCookie
0x18005bf46  call    __security_check_cookie
0x18005bf4b  add     rsp, 298h
0x18005bf52  pop     rdi
0x18005bf53  pop     rsi
0x18005bf54  pop     rbx
0x18005bf55  pop     rbp
0x18005bf56  retn
```
