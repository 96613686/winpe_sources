# GetSleepStudyTraceDirectory

- ea: `0x180041c5c`
- end: `0x180041d5e`
- name: `GetSleepStudyTraceDirectory`
- size: `258`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003053c`
- `0x180077808`

## callees

- `0x180008740`
- `0x180030bec`
- `0x180041c5c`
- `0x180041d64`
- `0x180045d70`
- `0x18004dd2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041d4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041d4b`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180041cc4`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180041d11`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180041cc4`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180041d11`

## string_xrefs

- `0x180041c90`: `%windir%\system32\SleepStudy`

## pseudocode

```c
__int64 __fastcall GetSleepStudyTraceDirectory(unsigned __int16 *a1)
{
  HRESULT v2; // ebx
  unsigned __int64 v3; // rdx
  HRESULT v4; // eax
  PWSTR ppszPath; // [rsp+38h] [rbp+10h] BYREF

  ppszPath = 0;
  if ( GetSleepStudyTraceDirectoryOverride(a1) )
  {
    v2 = 0;
    goto LABEL_14;
  }
  if ( !(unsigned __int8)IsSHGetKnownFolderPathPresent() )
  {
    v2 = StringCchCopyW(a1, v3, L"%windir%\\system32\\SleepStudy");
    if ( v2 >= 0 )
      goto LABEL_14;
    goto LABEL_13;
  }
  v4 = SHGetKnownFolderPath(&FOLDERID_SystemData, 0, 0, &ppszPath);
  if ( v4 >= 0 )
  {
    v2 = StringCchPrintfW(a1, 0x104u, L"%s\\ETW\\SleepStudy", ppszPath);
    if ( v2 >= 0 )
      goto LABEL_14;
    goto LABEL_13;
  }
  if ( v4 != -2147024894 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v2 = SHGetKnownFolderPath(&FOLDERID_System, 0, 0, &ppszPath);
  if ( v2 >= 0 )
  {
    v2 = StringCchPrintfW(a1, 0x104u, L"%s\\SleepStudy", ppszPath);
    if ( v2 < 0 )
LABEL_13:
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
LABEL_14:
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180041c5c  mov     [rsp+arg_0], rbx
0x180041c61  mov     [rsp+ppszPath], rdx
0x180041c66  push    rdi
0x180041c67  sub     rsp, 20h
0x180041c6b  mov     rdi, rcx
0x180041c6e  mov     [rsp+28h+ppszPath], 0
0x180041c77  call    ?GetSleepStudyTraceDirectoryOverride@@YAHPEAG_K@Z; GetSleepStudyTraceDirectoryOverride(ushort *,unsigned __int64)
0x180041c7c  test    eax, eax
0x180041c7e  jz      short loc_180041C87
0x180041c80  xor     ebx, ebx
0x180041c82  jmp     loc_180041D41
0x180041c87  call    IsSHGetKnownFolderPathPresent
0x180041c8c  test    al, al
0x180041c8e  jnz     short loc_180041CB3
0x180041c90  lea     r8, aWindirSystem32; "%windir%\\system32\\SleepStudy"
0x180041c97  mov     rcx, rdi; unsigned __int16 *
0x180041c9a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041c9f  mov     ebx, eax
0x180041ca1  test    eax, eax
0x180041ca3  jns     loc_180041D41
0x180041ca9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180041cae  jmp     loc_180041D41
0x180041cb3  lea     r9, [rsp+28h+ppszPath]; ppszPath
0x180041cb8  xor     r8d, r8d; hToken
0x180041cbb  xor     edx, edx; dwFlags
0x180041cbd  lea     rcx, ?FOLDERID_SystemData@@3U_GUID@@B; rfid
0x180041cc4  call    cs:__imp_SHGetKnownFolderPath
0x180041cca  test    eax, eax
0x180041ccc  js      short loc_180041CF4
0x180041cce  mov     r9, [rsp+28h+ppszPath]
0x180041cd3  lea     r8, aSEtwSleepstudy; "%s\\ETW\\SleepStudy"
0x180041cda  mov     edx, 104h; unsigned __int64
0x180041cdf  mov     rcx, rdi; unsigned __int16 *
0x180041ce2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041ce7  mov     ebx, eax
0x180041ce9  test    eax, eax
0x180041ceb  jns     short loc_180041D41
0x180041ced  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180041cf2  jmp     short loc_180041D41
0x180041cf4  cmp     eax, 80070002h
0x180041cf9  jz      short loc_180041D00
0x180041cfb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180041d00  lea     r9, [rsp+28h+ppszPath]; ppszPath
0x180041d05  xor     r8d, r8d; hToken
0x180041d08  xor     edx, edx; dwFlags
0x180041d0a  lea     rcx, FOLDERID_System; rfid
0x180041d11  call    cs:__imp_SHGetKnownFolderPath
0x180041d17  mov     ebx, eax
0x180041d19  test    eax, eax
0x180041d1b  js      short loc_180041D41
0x180041d1d  mov     r9, [rsp+28h+ppszPath]
0x180041d22  lea     r8, aSSleepstudy; "%s\\SleepStudy"
0x180041d29  mov     edx, 104h; unsigned __int64
0x180041d2e  mov     rcx, rdi; unsigned __int16 *
0x180041d31  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041d36  mov     ebx, eax
0x180041d38  test    eax, eax
0x180041d3a  jns     short loc_180041D41
0x180041d3c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180041d41  mov     rcx, [rsp+28h+ppszPath]; pv
0x180041d46  test    rcx, rcx
0x180041d49  jz      short loc_180041D51
0x180041d4b  call    cs:__imp_CoTaskMemFree
0x180041d51  mov     eax, ebx
0x180041d53  mov     rbx, [rsp+28h+arg_0]
0x180041d58  add     rsp, 20h
0x180041d5c  pop     rdi
0x180041d5d  retn
```
