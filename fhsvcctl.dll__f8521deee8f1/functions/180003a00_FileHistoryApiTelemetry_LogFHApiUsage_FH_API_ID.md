# FileHistoryApiTelemetry::LogFHApiUsage(_FH_API_ID)

- ea: `0x180003a00`
- end: `0x180003bc7`
- name: `?LogFHApiUsage@FileHistoryApiTelemetry@@YAXW4_FH_API_ID@@@Z`
- size: `455`
- prototype: `int __fastcall(char)`
- caller_count: `12`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800029d0`
- `0x180002b50`
- `0x180002c40`
- `0x180002db0`
- `0x180002f90`
- `0x180003070`
- `0x180003150`
- `0x180003230`
- `0x180003610`
- `0x180003700`
- `0x1800037f0`
- `0x1800038e0`

## callees

- `0x180003a00`
- `0x180004c94`
- `0x180004eee`
- `0x180004f20`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003a85`
- `msvcrt!_wcsicmp` at `0x180003a9e`
- `msvcrt!_wcsicmp` at `0x180003ab7`
- `msvcrt!_wcsicmp` at `0x180003ad0`
- `msvcrt!_wcsicmp` at `0x180003ae9`
- `msvcrt!_wcsicmp` at `0x180003a85`
- `msvcrt!_wcsicmp` at `0x180003a9e`
- `msvcrt!_wcsicmp` at `0x180003ab7`
- `msvcrt!_wcsicmp` at `0x180003ad0`
- `msvcrt!_wcsicmp` at `0x180003ae9`
- `KERNEL32!GetCurrentProcess` at `0x180003a27`
- `KERNEL32!GetCurrentProcess` at `0x180003a27`
- `KERNEL32!QueryFullProcessImageNameW` at `0x180003a62`
- `KERNEL32!QueryFullProcessImageNameW` at `0x180003a62`
- `SHLWAPI!PathStripPathW` at `0x180003a74`
- `SHLWAPI!PathStripPathW` at `0x180003a74`

## string_xrefs

- `0x180003ac5`: `SystemSettingsBroker.exe`

## pseudocode

```c
int __fastcall FileHistoryApiTelemetry::LogFHApiUsage(char a1)
{
  HANDLE CurrentProcess; // rax
  void *v3; // rbx
  __int64 v4; // rax
  char v6; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwSize; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v8; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v9[32]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v10; // [rsp+60h] [rbp-A0h]
  __int64 v11; // [rsp+68h] [rbp-98h]
  WCHAR *v12; // [rsp+70h] [rbp-90h]
  int v13; // [rsp+78h] [rbp-88h]
  int v14; // [rsp+7Ch] [rbp-84h]
  char *v15; // [rsp+80h] [rbp-80h]
  __int64 v16; // [rsp+88h] [rbp-78h]
  wchar_t ExeName[264]; // [rsp+90h] [rbp-70h] BYREF

  CurrentProcess = GetCurrentProcess();
  v3 = CurrentProcess;
  if ( CurrentProcess )
  {
    memset_0(ExeName, 0, 0x208u);
    dwSize = 260;
    LODWORD(CurrentProcess) = QueryFullProcessImageNameW(v3, 0, ExeName, &dwSize);
    if ( (_DWORD)CurrentProcess )
    {
      PathStripPathW(ExeName);
      LODWORD(CurrentProcess) = _wcsicmp(ExeName, L"FileHistory.exe ");
      if ( (_DWORD)CurrentProcess )
      {
        LODWORD(CurrentProcess) = _wcsicmp(ExeName, L"Control.exe");
        if ( (_DWORD)CurrentProcess )
        {
          LODWORD(CurrentProcess) = _wcsicmp(ExeName, L"SystemSettings.exe");
          if ( (_DWORD)CurrentProcess )
          {
            LODWORD(CurrentProcess) = _wcsicmp(ExeName, L"SystemSettingsBroker.exe");
            if ( (_DWORD)CurrentProcess )
            {
              LODWORD(CurrentProcess) = _wcsicmp(ExeName, L"Explorer.exe");
              if ( (_DWORD)CurrentProcess )
              {
                LODWORD(CurrentProcess) = dword_18000A008;
                if ( (unsigned int)dword_18000A008 > 5 )
                {
                  LODWORD(CurrentProcess) = qword_18000A018;
                  if ( (qword_18000A018 & 0x400000000000LL) != 0 )
                  {
                    LODWORD(CurrentProcess) = 0;
                    if ( (qword_18000A020 & 0x400000000000LL) == qword_18000A020 )
                    {
                      v6 = a1;
                      v8 = 1;
                      v15 = &v6;
                      v4 = -1;
                      v16 = 1;
                      do
                        ++v4;
                      while ( ExeName[v4] );
                      v14 = 0;
                      v13 = 2 * v4 + 2;
                      v12 = ExeName;
                      v10 = &v8;
                      v11 = 8;
                      LODWORD(CurrentProcess) = tlgWriteAgg(
                                                  (unsigned int)&dword_18000A008,
                                                  (unsigned int)byte_180008291,
                                                  0,
                                                  5,
                                                  (__int64)v9);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (int)CurrentProcess;
}

```

## disassembly

```asm
0x180003a00  push    rbp
0x180003a02  push    rbx
0x180003a03  push    rsi
0x180003a04  push    rdi
0x180003a05  lea     rbp, [rsp-1B8h]
0x180003a0d  sub     rsp, 2B8h
0x180003a14  mov     rax, cs:__security_cookie
0x180003a1b  xor     rax, rsp
0x180003a1e  mov     [rbp+1D0h+var_30], rax
0x180003a25  mov     edi, ecx
0x180003a27  call    cs:__imp_GetCurrentProcess
0x180003a2d  xor     esi, esi
0x180003a2f  mov     rbx, rax
0x180003a32  test    rax, rax
0x180003a35  jz      loc_180003BAC
0x180003a3b  xor     edx, edx; Val
0x180003a3d  lea     rcx, [rbp+1D0h+ExeName]; void *
0x180003a41  mov     r8d, 208h; Size
0x180003a47  call    memset_0
0x180003a4c  lea     r9, [rsp+2D0h+dwSize]; lpdwSize
0x180003a51  mov     [rsp+2D0h+dwSize], 104h
0x180003a59  lea     r8, [rbp+1D0h+ExeName]; lpExeName
0x180003a5d  xor     edx, edx; dwFlags
0x180003a5f  mov     rcx, rbx; hProcess
0x180003a62  call    cs:__imp_QueryFullProcessImageNameW
0x180003a68  test    eax, eax
0x180003a6a  jz      loc_180003BAC
0x180003a70  lea     rcx, [rbp+1D0h+ExeName]; pszPath
0x180003a74  call    cs:__imp_PathStripPathW
0x180003a7a  lea     rdx, aFilehistoryExe; "FileHistory.exe "
0x180003a81  lea     rcx, [rbp+1D0h+ExeName]; String1
0x180003a85  call    cs:__imp__wcsicmp
0x180003a8b  test    eax, eax
0x180003a8d  jz      loc_180003BAC
0x180003a93  lea     rdx, aControlExe; "Control.exe"
0x180003a9a  lea     rcx, [rbp+1D0h+ExeName]; String1
0x180003a9e  call    cs:__imp__wcsicmp
0x180003aa4  test    eax, eax
0x180003aa6  jz      loc_180003BAC
0x180003aac  lea     rdx, aSystemsettings_0; "SystemSettings.exe"
0x180003ab3  lea     rcx, [rbp+1D0h+ExeName]; String1
0x180003ab7  call    cs:__imp__wcsicmp
0x180003abd  test    eax, eax
0x180003abf  jz      loc_180003BAC
0x180003ac5  lea     rdx, aSystemsettings; "SystemSettingsBroker.exe"
0x180003acc  lea     rcx, [rbp+1D0h+ExeName]; String1
0x180003ad0  call    cs:__imp__wcsicmp
0x180003ad6  test    eax, eax
0x180003ad8  jz      loc_180003BAC
0x180003ade  lea     rdx, aExplorerExe; "Explorer.exe"
0x180003ae5  lea     rcx, [rbp+1D0h+ExeName]; String1
0x180003ae9  call    cs:__imp__wcsicmp
0x180003aef  test    eax, eax
0x180003af1  jz      loc_180003BAC
0x180003af7  mov     eax, cs:dword_18000A008
0x180003afd  lea     r9d, [rsi+5]
0x180003b01  cmp     eax, r9d
0x180003b04  jbe     loc_180003BAC
0x180003b0a  mov     rcx, cs:qword_18000A020
0x180003b11  mov     rdx, 400000000000h
0x180003b1b  mov     rax, cs:qword_18000A018
0x180003b22  test    rdx, rax
0x180003b25  jz      loc_180003BAC
0x180003b2b  mov     rax, rcx
0x180003b2e  and     rax, rdx
0x180003b31  cmp     rax, rcx
0x180003b34  jnz     short loc_180003BAC
0x180003b36  lea     ecx, [rsi+1]
0x180003b39  mov     [rsp+2D0h+var_2A0], dil
0x180003b3e  lea     rax, [rsp+2D0h+var_2A0]
0x180003b43  mov     [rsp+2D0h+var_298], rcx
0x180003b48  mov     [rbp+1D0h+var_250], rax
0x180003b4c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003b50  mov     [rbp+1D0h+var_248], rcx
0x180003b54  lea     rcx, [rbp+1D0h+ExeName]
0x180003b58  inc     rax
0x180003b5b  cmp     [rcx+rax*2], si
0x180003b5f  jnz     short loc_180003B58
0x180003b61  lea     eax, ds:2[rax*2]
0x180003b68  mov     [rsp+2D0h+var_254], esi
0x180003b6c  mov     [rsp+2D0h+var_258], eax
0x180003b70  lea     rcx, [rbp+1D0h+ExeName]
0x180003b74  lea     rax, [rsp+2D0h+var_298]
0x180003b79  mov     [rsp+2D0h+var_260], rcx
0x180003b7e  mov     [rsp+2D0h+var_270], rax
0x180003b83  lea     rdx, byte_180008291
0x180003b8a  lea     rax, [rsp+2D0h+var_290]
0x180003b8f  mov     [rsp+2D0h+var_268], 8
0x180003b98  xor     r8d, r8d
0x180003b9b  mov     [rsp+2D0h+var_2B0], rax
0x180003ba0  lea     rcx, dword_18000A008
0x180003ba7  call    _tlgWriteAgg
0x180003bac  mov     rcx, [rbp+1D0h+var_30]
0x180003bb3  xor     rcx, rsp; StackCookie
0x180003bb6  call    __security_check_cookie
0x180003bbb  add     rsp, 2B8h
0x180003bc2  pop     rdi
0x180003bc3  pop     rsi
0x180003bc4  pop     rbx
0x180003bc5  pop     rbp
0x180003bc6  retn
```
