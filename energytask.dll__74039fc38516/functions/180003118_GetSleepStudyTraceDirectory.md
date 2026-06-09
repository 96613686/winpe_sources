# GetSleepStudyTraceDirectory

- ea: `0x180003118`
- end: `0x1800032ce`
- name: `GetSleepStudyTraceDirectory`
- size: `438`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800029bc`

## callees

- `0x1800019e4`
- `0x180002c00`
- `0x180003118`
- `0x180003950`
- `0x180003ac0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800032aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800032aa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000317f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000317f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003199`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003199`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180003227`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180003272`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180003227`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180003272`

## string_xrefs

- `0x18000314f`: `SleepStudyTraceDirectory`
- `0x1800031bd`: `%windir%\system32\SleepStudy`

## pseudocode

```c
__int64 __fastcall GetSleepStudyTraceDirectory(unsigned __int16 *a1)
{
  __int64 v2; // rdi
  HRESULT v3; // ebx
  __int64 v4; // rax
  const wchar_t *v5; // rcx
  unsigned __int16 *v6; // rcx
  HRESULT v7; // eax
  PWSTR ppszPath; // [rsp+40h] [rbp-258h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-250h] BYREF
  WCHAR Src[264]; // [rsp+50h] [rbp-248h] BYREF

  pcbData = 520;
  ppszPath = 0;
  Src[0] = 0;
  v2 = 260;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\Session Manager\\Power",
          L"SleepStudyTraceDirectory",
          2u,
          0,
          Src,
          &pcbData)
    && ExpandEnvironmentStringsW(Src, a1, 0x104u) - 1 <= 0x103 )
  {
    v3 = 0;
    goto LABEL_21;
  }
  if ( !(unsigned __int8)IsSHGetKnownFolderPathPresent() )
  {
    v4 = 2147483646;
    v5 = L"%windir%\\system32\\SleepStudy";
    do
    {
      if ( !v4 )
        break;
      if ( !*v5 )
        break;
      *a1++ = *v5++;
      --v4;
      --v2;
    }
    while ( v2 );
    v6 = a1 - 1;
    if ( v2 )
      v6 = a1;
    v3 = v2 == 0 ? 0x8007007A : 0;
    *v6 = 0;
    if ( !v2 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    goto LABEL_21;
  }
  v7 = SHGetKnownFolderPath(&FOLDERID_SystemData, 0, 0, &ppszPath);
  if ( v7 >= 0 )
  {
    v3 = StringCchPrintfW(a1, 0x104u, L"%s\\ETW\\SleepStudy", ppszPath);
    if ( v3 >= 0 )
      goto LABEL_21;
    goto LABEL_20;
  }
  if ( v7 != -2147024894 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v3 = SHGetKnownFolderPath(&FOLDERID_System, 0, 0, &ppszPath);
  if ( v3 >= 0 )
  {
    v3 = StringCchPrintfW(a1, 0x104u, L"%s\\SleepStudy", ppszPath);
    if ( v3 < 0 )
LABEL_20:
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
LABEL_21:
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003118  push    rbx
0x18000311a  push    rbp
0x18000311b  push    rsi
0x18000311c  push    rdi
0x18000311d  sub     rsp, 278h
0x180003124  mov     rax, cs:__security_cookie
0x18000312b  xor     rax, rsp
0x18000312e  mov     [rsp+298h+var_38], rax
0x180003136  xor     ebp, ebp
0x180003138  mov     [rsp+298h+var_250], 208h
0x180003140  lea     rax, [rsp+298h+var_250]
0x180003145  mov     [rsp+298h+ppszPath], rbp
0x18000314a  mov     [rsp+298h+pcbData], rax; pcbData
0x18000314f  lea     r8, aSleepstudytrac; "SleepStudyTraceDirectory"
0x180003156  lea     rax, [rsp+298h+Src]
0x18000315b  mov     [rsp+298h+Src], bp
0x180003160  mov     rsi, rcx
0x180003163  mov     [rsp+298h+pvData], rax; pvData
0x180003168  lea     r9d, [rbp+2]; dwFlags
0x18000316c  mov     [rsp+298h+pdwType], rbp; pdwType
0x180003171  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Ses"...
0x180003178  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000317f  call    cs:__imp_RegGetValueW
0x180003185  mov     edi, 104h
0x18000318a  test    eax, eax
0x18000318c  jnz     short loc_1800031AF
0x18000318e  mov     r8d, edi; nSize
0x180003191  lea     rcx, [rsp+298h+Src]; lpSrc
0x180003196  mov     rdx, rsi; lpDst
0x180003199  call    cs:__imp_ExpandEnvironmentStringsW
0x18000319f  dec     eax
0x1800031a1  cmp     eax, 103h
0x1800031a6  ja      short loc_1800031AF
0x1800031a8  mov     ebx, ebp
0x1800031aa  jmp     loc_1800032A0
0x1800031af  call    IsSHGetKnownFolderPathPresent
0x1800031b4  test    al, al
0x1800031b6  jnz     short loc_180003216
0x1800031b8  mov     eax, 7FFFFFFEh
0x1800031bd  lea     rcx, aWindirSystem32; "%windir%\\system32\\SleepStudy"
0x1800031c4  test    rax, rax
0x1800031c7  jz      short loc_1800031E5
0x1800031c9  movzx   edx, word ptr [rcx]
0x1800031cc  test    dx, dx
0x1800031cf  jz      short loc_1800031E5
0x1800031d1  mov     [rsi], dx
0x1800031d4  add     rcx, 2
0x1800031d8  add     rsi, 2
0x1800031dc  dec     rax
0x1800031df  sub     rdi, 1
0x1800031e3  jnz     short loc_1800031C4
0x1800031e5  test    rdi, rdi
0x1800031e8  lea     rcx, [rsi-2]
0x1800031ec  mov     rax, rdi
0x1800031ef  cmovnz  rcx, rsi
0x1800031f3  neg     rax
0x1800031f6  sbb     ebx, ebx
0x1800031f8  not     ebx
0x1800031fa  and     ebx, 8007007Ah
0x180003200  mov     [rcx], bp
0x180003203  test    rdi, rdi
0x180003206  jnz     loc_1800032A0
0x18000320c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180003211  jmp     loc_1800032A0
0x180003216  lea     r9, [rsp+298h+ppszPath]; ppszPath
0x18000321b  xor     r8d, r8d; hToken
0x18000321e  xor     edx, edx; dwFlags
0x180003220  lea     rcx, ?FOLDERID_SystemData@@3U_GUID@@B; rfid
0x180003227  call    cs:__imp_SHGetKnownFolderPath
0x18000322d  test    eax, eax
0x18000322f  js      short loc_180003255
0x180003231  mov     r9, [rsp+298h+ppszPath]
0x180003236  lea     r8, aSEtwSleepstudy; "%s\\ETW\\SleepStudy"
0x18000323d  mov     rdx, rdi; unsigned __int64
0x180003240  mov     rcx, rsi; unsigned __int16 *
0x180003243  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003248  mov     ebx, eax
0x18000324a  test    eax, eax
0x18000324c  jns     short loc_1800032A0
0x18000324e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180003253  jmp     short loc_1800032A0
0x180003255  cmp     eax, 80070002h
0x18000325a  jz      short loc_180003261
0x18000325c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180003261  lea     r9, [rsp+298h+ppszPath]; ppszPath
0x180003266  xor     r8d, r8d; hToken
0x180003269  xor     edx, edx; dwFlags
0x18000326b  lea     rcx, FOLDERID_System; rfid
0x180003272  call    cs:__imp_SHGetKnownFolderPath
0x180003278  mov     ebx, eax
0x18000327a  test    eax, eax
0x18000327c  js      short loc_1800032A0
0x18000327e  mov     r9, [rsp+298h+ppszPath]
0x180003283  lea     r8, aSSleepstudy; "%s\\SleepStudy"
0x18000328a  mov     rdx, rdi; unsigned __int64
0x18000328d  mov     rcx, rsi; unsigned __int16 *
0x180003290  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003295  mov     ebx, eax
0x180003297  test    eax, eax
0x180003299  jns     short loc_1800032A0
0x18000329b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800032a0  mov     rcx, [rsp+298h+ppszPath]; pv
0x1800032a5  test    rcx, rcx
0x1800032a8  jz      short loc_1800032B0
0x1800032aa  call    cs:__imp_CoTaskMemFree
0x1800032b0  mov     eax, ebx
0x1800032b2  mov     rcx, [rsp+298h+var_38]
0x1800032ba  xor     rcx, rsp; StackCookie
0x1800032bd  call    __security_check_cookie
0x1800032c2  add     rsp, 278h
0x1800032c9  pop     rdi
0x1800032ca  pop     rsi
0x1800032cb  pop     rbp
0x1800032cc  pop     rbx
0x1800032cd  retn
```
