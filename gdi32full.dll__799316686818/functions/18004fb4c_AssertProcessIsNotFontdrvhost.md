# AssertProcessIsNotFontdrvhost

- ea: `0x18004fb4c`
- end: `0x18004fc7f`
- name: `AssertProcessIsNotFontdrvhost`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180057424`

## callees

- `0x18004fb4c`
- `0x18007ac50`
- `0x18007ba24`
- `0x18009fbe8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004fbb8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004fc67`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004fbb8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004fc67`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004fc4a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004fc4a`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x18004fb9c`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x18004fb9c`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18004fc21`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18004fc21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004fb86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004fc07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004fb86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004fc07`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004fc32`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004fc32`

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
0x18004fb4c  mov     [rsp-8+arg_0], rbx
0x18004fb51  push    rbp
0x18004fb52  lea     rbp, [rsp-380h]
0x18004fb5a  sub     rsp, 480h
0x18004fb61  mov     rax, cs:__security_cookie
0x18004fb68  xor     rax, rsp
0x18004fb6b  mov     [rbp+380h+var_10], rax
0x18004fb72  xorps   xmm0, xmm0
0x18004fb75  xor     eax, eax
0x18004fb77  movups  xmmword ptr [rsp+480h+BaseName], xmm0
0x18004fb7c  mov     [rsp+480h+var_440], ax
0x18004fb81  movups  [rsp+480h+var_450], xmm0
0x18004fb86  call    cs:__imp_GetCurrentProcess
0x18004fb8c  mov     r9d, 11h; nSize
0x18004fb92  lea     r8, [rsp+480h+BaseName]; lpBaseName
0x18004fb97  mov     rcx, rax; hProcess
0x18004fb9a  xor     edx, edx; hModule
0x18004fb9c  call    cs:__imp_K32GetModuleBaseNameW
0x18004fba2  test    eax, eax
0x18004fba4  jz      short loc_18004FBC2
0x18004fba6  mov     r8d, 10h
0x18004fbac  lea     rdx, [rsp+480h+BaseName]
0x18004fbb1  lea     rcx, aFontdrvhostExe+2; "fontdrvhost.exe"
0x18004fbb8  call    cs:__imp__o__wcsnicmp
0x18004fbbe  test    eax, eax
0x18004fbc0  jz      short loc_18004FBE2
0x18004fbc2  mov     rcx, [rbp+380h+var_10]
0x18004fbc9  xor     rcx, rsp; StackCookie
0x18004fbcc  call    __security_check_cookie
0x18004fbd1  mov     rbx, [rsp+480h+arg_0]
0x18004fbd9  add     rsp, 480h
0x18004fbe0  pop     rbp
0x18004fbe1  retn
0x18004fbe2  mov     ebx, 208h
0x18004fbe7  lea     rcx, [rbp+380h+Filename]; void *
0x18004fbee  mov     r8d, ebx; Size
0x18004fbf1  xor     edx, edx; Val
0x18004fbf3  call    memset_0
0x18004fbf8  mov     r8d, ebx; Size
0x18004fbfb  lea     rcx, [rsp+480h+Buffer]; void *
0x18004fc00  xor     edx, edx; Val
0x18004fc02  call    memset_0
0x18004fc07  call    cs:__imp_GetCurrentProcess
0x18004fc0d  mov     ebx, 104h
0x18004fc12  lea     r8, [rbp+380h+Filename]; lpFilename
0x18004fc19  mov     rcx, rax; hProcess
0x18004fc1c  mov     r9d, ebx; nSize
0x18004fc1f  xor     edx, edx; hModule
0x18004fc21  call    cs:__imp_K32GetModuleFileNameExW
0x18004fc27  test    eax, eax
0x18004fc29  jz      short loc_18004FBC2
0x18004fc2b  mov     edx, ebx; uSize
0x18004fc2d  lea     rcx, [rsp+480h+Buffer]; lpBuffer
0x18004fc32  call    cs:__imp_GetSystemDirectoryW
0x18004fc38  test    eax, eax
0x18004fc3a  jz      short loc_18004FBC2
0x18004fc3c  lea     r8, aFontdrvhostExe; "\\fontdrvhost.exe"
0x18004fc43  mov     edx, ebx
0x18004fc45  lea     rcx, [rsp+480h+Buffer]
0x18004fc4a  call    cs:__imp__o_wcscat_s
0x18004fc50  test    eax, eax
0x18004fc52  jnz     loc_18004FBC2
0x18004fc58  mov     r8d, ebx
0x18004fc5b  lea     rdx, [rbp+380h+Filename]
0x18004fc62  lea     rcx, [rsp+480h+Buffer]
0x18004fc67  call    cs:__imp__o__wcsnicmp
0x18004fc6d  test    eax, eax
0x18004fc6f  jnz     loc_18004FBC2
0x18004fc75  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004fc7a  jmp     loc_18004FBC2
```
