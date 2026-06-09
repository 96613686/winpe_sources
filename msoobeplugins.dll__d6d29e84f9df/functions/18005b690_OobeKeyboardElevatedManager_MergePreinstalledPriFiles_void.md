# OobeKeyboardElevatedManager::MergePreinstalledPriFiles(void)

- ea: `0x18005b690`
- end: `0x18005b7dc`
- name: `?MergePreinstalledPriFiles@OobeKeyboardElevatedManager@@AEAAXXZ`
- size: `332`
- prototype: `void __fastcall(OobeKeyboardElevatedManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005b3b0`

## callees

- `0x180003470`
- `0x180003ffc`
- `0x180008b98`
- `0x18005b690`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18005b7a4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18005b7a4`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18005b6d8`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18005b6d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b7b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b7be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b7b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b7be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005b6ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005b6ef`

## string_xrefs

- `0x18005b71d`: `%s\lpremove.exe /g %s`

## pseudocode

```c
void __fastcall OobeKeyboardElevatedManager::MergePreinstalledPriFiles(OobeKeyboardElevatedManager *this)
{
  UINT SystemDirectoryW; // eax
  ULONG pcchLanguagesBuffer; // [rsp+50h] [rbp-B0h] BYREF
  ULONG pulNumLanguages; // [rsp+54h] [rbp-ACh] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR pwszLanguagesBuffer[264]; // [rsp+2F0h] [rbp+1F0h] BYREF
  WCHAR CommandLine[264]; // [rsp+500h] [rbp+400h] BYREF

  pulNumLanguages = 0;
  pcchLanguagesBuffer = 260;
  if ( GetThreadPreferredUILanguages(0x38u, &pulNumLanguages, pwszLanguagesBuffer, &pcchLanguagesBuffer) )
  {
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
    if ( SystemDirectoryW )
    {
      if ( SystemDirectoryW < 0x104
        && StringCchPrintfW(CommandLine, 0x104u, L"%s\\lpremove.exe /g %s", Buffer, pwszLanguagesBuffer) >= 0 )
      {
        memset_0(&StartupInfo.cb + 1, 0, 0x64u);
        StartupInfo.cb = 104;
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        if ( CreateProcessW(0, CommandLine, 0, 0, 0, 0xC000008u, 0, Buffer, &StartupInfo, &ProcessInformation) )
        {
          CloseHandle(ProcessInformation.hProcess);
          CloseHandle(ProcessInformation.hThread);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18005b690  push    rbp
0x18005b692  lea     rbp, [rsp-620h]
0x18005b69a  sub     rsp, 720h
0x18005b6a1  mov     rax, cs:__security_cookie
0x18005b6a8  xor     rax, rsp
0x18005b6ab  mov     [rbp+620h+var_10], rax
0x18005b6b2  lea     r9, [rsp+720h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18005b6b7  mov     [rsp+720h+pulNumLanguages], 0
0x18005b6bf  lea     r8, [rbp+620h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x18005b6c6  mov     [rsp+720h+pcchLanguagesBuffer], 104h
0x18005b6ce  lea     rdx, [rsp+720h+pulNumLanguages]; pulNumLanguages
0x18005b6d3  mov     ecx, 38h ; '8'; dwFlags
0x18005b6d8  call    cs:__imp_GetThreadPreferredUILanguages
0x18005b6de  test    eax, eax
0x18005b6e0  jz      loc_18005B7C4
0x18005b6e6  mov     edx, 104h; uSize
0x18005b6eb  lea     rcx, [rbp+620h+Buffer]; lpBuffer
0x18005b6ef  call    cs:__imp_GetSystemDirectoryW
0x18005b6f5  test    eax, eax
0x18005b6f7  jz      loc_18005B7C4
0x18005b6fd  cmp     eax, 104h
0x18005b702  jnb     loc_18005B7C4
0x18005b708  lea     rax, [rbp+620h+pwszLanguagesBuffer]
0x18005b70f  mov     edx, 104h; unsigned __int64
0x18005b714  lea     r9, [rbp+620h+Buffer]
0x18005b718  mov     qword ptr [rsp+720h+bInheritHandles], rax
0x18005b71d  lea     r8, aSLpremoveExeGS; "%s\\lpremove.exe /g %s"
0x18005b724  lea     rcx, [rbp+620h+CommandLine]; unsigned __int16 *
0x18005b72b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005b730  test    eax, eax
0x18005b732  js      loc_18005B7C4
0x18005b738  xor     edx, edx; Val
0x18005b73a  lea     rcx, [rsp+720h+StartupInfo+4]; void *
0x18005b73f  lea     r8d, [rdx+64h]; Size
0x18005b743  call    memset_0
0x18005b748  xor     eax, eax
0x18005b74a  mov     [rsp+720h+StartupInfo.cb], 68h ; 'h'
0x18005b752  mov     qword ptr [rsp+720h+ProcessInformation.dwProcessId], rax
0x18005b757  lea     rdx, [rbp+620h+CommandLine]; lpCommandLine
0x18005b75e  lea     rax, [rsp+720h+ProcessInformation]
0x18005b763  xorps   xmm0, xmm0
0x18005b766  mov     [rsp+720h+lpProcessInformation], rax; lpProcessInformation
0x18005b76b  xor     r9d, r9d; lpThreadAttributes
0x18005b76e  lea     rax, [rsp+720h+StartupInfo]
0x18005b773  xor     r8d, r8d; lpProcessAttributes
0x18005b776  mov     [rsp+720h+lpStartupInfo], rax; lpStartupInfo
0x18005b77b  xor     ecx, ecx; lpApplicationName
0x18005b77d  lea     rax, [rbp+620h+Buffer]
0x18005b781  mov     [rsp+720h+lpCurrentDirectory], rax; lpCurrentDirectory
0x18005b786  mov     [rsp+720h+lpEnvironment], 0; lpEnvironment
0x18005b78f  mov     [rsp+720h+dwCreationFlags], 0C000008h; dwCreationFlags
0x18005b797  mov     [rsp+720h+bInheritHandles], 0; bInheritHandles
0x18005b79f  movups  xmmword ptr [rsp+720h+ProcessInformation.hProcess], xmm0
0x18005b7a4  call    cs:__imp_CreateProcessW
0x18005b7aa  test    eax, eax
0x18005b7ac  jz      short loc_18005B7C4
0x18005b7ae  mov     rcx, [rsp+720h+ProcessInformation.hProcess]; hObject
0x18005b7b3  call    cs:__imp_CloseHandle
0x18005b7b9  mov     rcx, [rsp+720h+ProcessInformation.hThread]; hObject
0x18005b7be  call    cs:__imp_CloseHandle
0x18005b7c4  mov     rcx, [rbp+620h+var_10]
0x18005b7cb  xor     rcx, rsp; StackCookie
0x18005b7ce  call    __security_check_cookie
0x18005b7d3  add     rsp, 720h
0x18005b7da  pop     rbp
0x18005b7db  retn
```
