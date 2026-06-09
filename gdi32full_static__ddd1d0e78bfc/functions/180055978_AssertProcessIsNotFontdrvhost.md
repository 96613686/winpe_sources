# AssertProcessIsNotFontdrvhost

- ea: `0x180055978`
- end: `0x180055ae0`
- name: `AssertProcessIsNotFontdrvhost`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18005b9f8`

## callees

- `0x180055978`
- `0x18007f800`
- `0x180080604`
- `0x1800a2b64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800559f0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180055ac2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800559f0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180055ac2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180055a9f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180055a9f`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x1800559ce`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x1800559ce`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180055a66`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180055a66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800559b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180055a46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800559b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180055a46`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180055a7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180055a7d`

## pseudocode

```c
DWORD AssertProcessIsNotFontdrvhost()
{
  HANDLE CurrentProcess; // rax
  DWORD result; // eax
  HANDLE v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  WCHAR BaseName[8]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v8; // [rsp+30h] [rbp-D0h]
  __int16 v9; // [rsp+40h] [rbp-C0h]
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[264]; // [rsp+260h] [rbp+160h] BYREF

  *(_OWORD *)BaseName = 0;
  v9 = 0;
  v8 = 0;
  CurrentProcess = GetCurrentProcess();
  result = K32GetModuleBaseNameW(CurrentProcess, 0, BaseName, 0x11u);
  if ( result )
  {
    result = _o__wcsnicmp(L"fontdrvhost.exe", BaseName, 16);
    if ( !result )
    {
      memset_0(Filename, 0, 0x208u);
      memset_0(Buffer, 0, 0x208u);
      v2 = GetCurrentProcess();
      result = K32GetModuleFileNameExW(v2, 0, Filename, 0x104u);
      if ( result )
      {
        result = GetSystemDirectoryW(Buffer, 0x104u);
        if ( result )
        {
          result = _o_wcscat_s(Buffer, 260, L"\\fontdrvhost.exe");
          if ( !result )
          {
            result = _o__wcsnicmp(Buffer, Filename, 260);
            if ( !result )
              return MicrosoftTelemetryAssertTriggeredNoArgs(v4, v3, v5, v6, *(_QWORD *)BaseName);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180055978  mov     [rsp-8+arg_0], rbx
0x18005597d  push    rbp
0x18005597e  lea     rbp, [rsp-380h]
0x180055986  sub     rsp, 480h
0x18005598d  mov     rax, cs:__security_cookie
0x180055994  xor     rax, rsp
0x180055997  mov     [rbp+380h+var_10], rax
0x18005599e  xorps   xmm0, xmm0
0x1800559a1  xor     eax, eax
0x1800559a3  movups  xmmword ptr [rsp+480h+BaseName], xmm0
0x1800559a8  mov     [rsp+480h+var_440], ax
0x1800559ad  movups  [rsp+480h+var_450], xmm0
0x1800559b2  call    cs:__imp_GetCurrentProcess
0x1800559b9  nop     dword ptr [rax+rax+00h]
0x1800559be  mov     r9d, 11h; nSize
0x1800559c4  lea     r8, [rsp+480h+BaseName]; lpBaseName
0x1800559c9  mov     rcx, rax; hProcess
0x1800559cc  xor     edx, edx; hModule
0x1800559ce  call    cs:__imp_K32GetModuleBaseNameW
0x1800559d5  nop     dword ptr [rax+rax+00h]
0x1800559da  test    eax, eax
0x1800559dc  jz      short loc_180055A00
0x1800559de  mov     r8d, 10h
0x1800559e4  lea     rdx, [rsp+480h+BaseName]
0x1800559e9  lea     rcx, aFontdrvhostExe+2; "fontdrvhost.exe"
0x1800559f0  call    cs:__imp__o__wcsnicmp
0x1800559f7  nop     dword ptr [rax+rax+00h]
0x1800559fc  test    eax, eax
0x1800559fe  jz      short loc_180055A21
0x180055a00  mov     rcx, [rbp+380h+var_10]
0x180055a07  xor     rcx, rsp; StackCookie
0x180055a0a  call    __security_check_cookie
0x180055a0f  mov     rbx, [rsp+480h+arg_0]
0x180055a17  add     rsp, 480h
0x180055a1e  pop     rbp
0x180055a1f  retn
0x180055a21  mov     ebx, 208h
0x180055a26  lea     rcx, [rbp+380h+Filename]; void *
0x180055a2d  mov     r8d, ebx; Size
0x180055a30  xor     edx, edx; Val
0x180055a32  call    memset_0
0x180055a37  mov     r8d, ebx; Size
0x180055a3a  lea     rcx, [rsp+480h+Buffer]; void *
0x180055a3f  xor     edx, edx; Val
0x180055a41  call    memset_0
0x180055a46  call    cs:__imp_GetCurrentProcess
0x180055a4d  nop     dword ptr [rax+rax+00h]
0x180055a52  mov     ebx, 104h
0x180055a57  lea     r8, [rbp+380h+Filename]; lpFilename
0x180055a5e  mov     rcx, rax; hProcess
0x180055a61  mov     r9d, ebx; nSize
0x180055a64  xor     edx, edx; hModule
0x180055a66  call    cs:__imp_K32GetModuleFileNameExW
0x180055a6d  nop     dword ptr [rax+rax+00h]
0x180055a72  test    eax, eax
0x180055a74  jz      short loc_180055A00
0x180055a76  mov     edx, ebx; uSize
0x180055a78  lea     rcx, [rsp+480h+Buffer]; lpBuffer
0x180055a7d  call    cs:__imp_GetSystemDirectoryW
0x180055a84  nop     dword ptr [rax+rax+00h]
0x180055a89  test    eax, eax
0x180055a8b  jz      loc_180055A00
0x180055a91  lea     r8, aFontdrvhostExe; "\\fontdrvhost.exe"
0x180055a98  mov     edx, ebx
0x180055a9a  lea     rcx, [rsp+480h+Buffer]
0x180055a9f  call    cs:__imp__o_wcscat_s
0x180055aa6  nop     dword ptr [rax+rax+00h]
0x180055aab  test    eax, eax
0x180055aad  jnz     loc_180055A00
0x180055ab3  mov     r8d, ebx
0x180055ab6  lea     rdx, [rbp+380h+Filename]
0x180055abd  lea     rcx, [rsp+480h+Buffer]
0x180055ac2  call    cs:__imp__o__wcsnicmp
0x180055ac9  nop     dword ptr [rax+rax+00h]
0x180055ace  test    eax, eax
0x180055ad0  jnz     loc_180055A00
0x180055ad6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180055adb  jmp     loc_180055A00
```
