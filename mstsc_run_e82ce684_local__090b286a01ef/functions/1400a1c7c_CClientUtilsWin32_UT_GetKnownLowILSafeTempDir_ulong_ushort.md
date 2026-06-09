# CClientUtilsWin32::UT_GetKnownLowILSafeTempDir(ulong,ushort *)

- ea: `0x1400a1c7c`
- end: `0x1400a1f72`
- name: `?UT_GetKnownLowILSafeTempDir@CClientUtilsWin32@@SAJKPEAG@Z`
- size: `758`
- prototype: `static int(unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1400582a0`

## callees

- `0x140008a78`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14001e210`
- `0x1400a1c7c`
- `0x140114010`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x1400a1e70`
- `KERNEL32!CreateDirectoryW` at `0x1400a1e70`
- `KERNEL32!LoadLibraryExW` at `0x1400a1cae`
- `KERNEL32!LoadLibraryExW` at `0x1400a1cae`
- `KERNEL32!FreeLibrary` at `0x1400a1f56`
- `KERNEL32!FreeLibrary` at `0x1400a1f56`
- `KERNEL32!GetProcAddress` at `0x1400a1d40`
- `KERNEL32!GetProcAddress` at `0x1400a1d40`
- `KERNEL32!GetLastError` at `0x1400a1cdb`
- `KERNEL32!GetLastError` at `0x1400a1d18`
- `KERNEL32!GetLastError` at `0x1400a1d6a`
- `KERNEL32!GetLastError` at `0x1400a1e7e`
- `KERNEL32!GetLastError` at `0x1400a1cdb`
- `KERNEL32!GetLastError` at `0x1400a1d18`
- `KERNEL32!GetLastError` at `0x1400a1d6a`
- `KERNEL32!GetLastError` at `0x1400a1e7e`
- `ole32!CoTaskMemFree` at `0x1400a1f48`
- `ole32!CoTaskMemFree` at `0x1400a1f48`

## string_xrefs

- `0x1400a1ca5`: `shell32.dll`
- `0x1400a1ded`: `%s\Temp`
- `0x1400a1e3c`: `StringCchPrintf(KnownFolderPath\Temp) failed`
- `0x1400a1d36`: `SHGetKnownFolderPath`
- `0x1400a1ddf`: `SHGetKnownFolderPath(LocalAppDataLow) failed`

## pseudocode

```c
__int64 __fastcall CClientUtilsWin32::UT_GetKnownLowILSafeTempDir(__int64 a1, unsigned __int16 *a2)
{
  void *v2; // rcx
  HMODULE Library; // rax
  HMODULE v5; // r14
  signed int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  __int64 v9; // rdx
  signed int v10; // eax
  signed int v11; // ebx
  FARPROC ProcAddress; // rax
  signed int v13; // eax
  unsigned int v14; // eax
  int v15; // edx
  const char *v16; // rcx
  signed int LastError; // eax
  signed int v18; // ebp
  PVOID *v19; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v21; // eax
  void *v23; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  v23 = 0;
  if ( a2 )
  {
    Library = LoadLibraryExW(L"shell32.dll", 0, 0);
    v5 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "SHGetKnownFolderPath");
      if ( ProcAddress )
      {
        v11 = ((__int64 (__fastcall *)(const GUID *, _QWORD, _QWORD, void **))ProcAddress)(
                &FOLDERID_LocalAppDataLow,
                0,
                0,
                &v23);
        if ( v11 >= 0 )
        {
          v11 = StringCchPrintfW(a2, 0x104u, L"%s\\Temp", v23);
          if ( v11 >= 0 )
          {
            if ( CreateDirectoryW(a2, 0) )
              goto LABEL_45;
            LastError = GetLastError();
            v18 = LastError;
            if ( LastError == 183 )
              goto LABEL_45;
            if ( LastError > 0 )
              v11 = (unsigned __int16)LastError | 0x80070000;
            else
              v11 = LastError;
            v19 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  52,
                  &WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids,
                  CurrentThreadActivityIdPrefix,
                  v18);
                v19 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 3u )
              {
                v21 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  53,
                  (unsigned int)&WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids,
                  v21,
                  (__int64)a2);
              }
            }
LABEL_43:
            if ( v11 >= 0 )
            {
LABEL_45:
              v2 = v23;
              goto LABEL_47;
            }
LABEL_44:
            *a2 = 0;
            goto LABEL_45;
          }
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_44;
          }
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          v15 = 51;
          v16 = "StringCchPrintf(KnownFolderPath\\Temp) failed";
        }
        else
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_44;
          }
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          v15 = 50;
          v16 = "SHGetKnownFolderPath(LocalAppDataLow) failed";
        }
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v15,
          (unsigned int)&WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids,
          v14,
          (__int64)v16,
          v11);
        goto LABEL_44;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = GetLastError();
        v7 = v13;
        if ( v13 > 0 )
          v7 = (unsigned __int16)v13 | 0x80070000;
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 49;
        goto LABEL_9;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = GetLastError();
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 48;
LABEL_9:
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids, v8, v7);
    }
    v10 = GetLastError();
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    goto LABEL_43;
  }
  v5 = 0;
  v11 = -2147024809;
LABEL_47:
  if ( v2 )
    CoTaskMemFree(v2);
  if ( v5 )
    FreeLibrary(v5);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400a1c7c  mov     [rsp+arg_0], rbx
0x1400a1c81  mov     [rsp+arg_10], rbp
0x1400a1c86  push    rdi
0x1400a1c87  push    r14
0x1400a1c89  push    r15
0x1400a1c8b  sub     rsp, 30h
0x1400a1c8f  xor     ecx, ecx; pv
0x1400a1c91  mov     r15, rdx
0x1400a1c94  mov     [rsp+48h+arg_8], rcx
0x1400a1c99  test    rdx, rdx
0x1400a1c9c  jz      loc_1400A1F3B
0x1400a1ca2  xor     r8d, r8d; dwFlags
0x1400a1ca5  lea     rcx, aShell32Dll_0; "shell32.dll"
0x1400a1cac  xor     edx, edx; hFile
0x1400a1cae  call    cs:__imp_LoadLibraryExW
0x1400a1cb4  mov     r14, rax
0x1400a1cb7  test    rax, rax
0x1400a1cba  jnz     short loc_1400A1D36
0x1400a1cbc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1cc3  lea     rdi, WPP_GLOBAL_Control
0x1400a1cca  cmp     rcx, rdi
0x1400a1ccd  jz      short loc_1400A1D18
0x1400a1ccf  test    byte ptr [rcx+1Ch], 8
0x1400a1cd3  jz      short loc_1400A1D18
0x1400a1cd5  cmp     byte ptr [rcx+19h], 2
0x1400a1cd9  jb      short loc_1400A1D18
0x1400a1cdb  call    cs:__imp_GetLastError
0x1400a1ce1  mov     ebx, eax
0x1400a1ce3  test    eax, eax
0x1400a1ce5  jle     short loc_1400A1CF0
0x1400a1ce7  movzx   ebx, ax
0x1400a1cea  or      ebx, 80070000h
0x1400a1cf0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1cf5  mov     edx, 30h ; '0'
0x1400a1cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1d01  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1400a1d08  mov     r9d, eax
0x1400a1d0b  mov     dword ptr [rsp+48h+var_28], ebx
0x1400a1d0f  mov     rcx, [rcx+10h]
0x1400a1d13  call    WPP_SF_Dd
0x1400a1d18  call    cs:__imp_GetLastError
0x1400a1d1e  mov     ebx, eax
0x1400a1d20  test    eax, eax
0x1400a1d22  jle     loc_1400A1F2A
0x1400a1d28  movzx   ebx, ax
0x1400a1d2b  or      ebx, 80070000h
0x1400a1d31  jmp     loc_1400A1F2A
0x1400a1d36  lea     rdx, aShgetknownfold_0; "SHGetKnownFolderPath"
0x1400a1d3d  mov     rcx, rax; hModule
0x1400a1d40  call    cs:__imp_GetProcAddress
0x1400a1d46  test    rax, rax
0x1400a1d49  jnz     short loc_1400A1D8E
0x1400a1d4b  mov     rax, cs:WPP_GLOBAL_Control
0x1400a1d52  lea     rdi, WPP_GLOBAL_Control
0x1400a1d59  cmp     rax, rdi
0x1400a1d5c  jz      short loc_1400A1D18
0x1400a1d5e  test    byte ptr [rax+1Ch], 8
0x1400a1d62  jz      short loc_1400A1D18
0x1400a1d64  cmp     byte ptr [rax+19h], 2
0x1400a1d68  jb      short loc_1400A1D18
0x1400a1d6a  call    cs:__imp_GetLastError
0x1400a1d70  mov     ebx, eax
0x1400a1d72  test    eax, eax
0x1400a1d74  jle     short loc_1400A1D7F
0x1400a1d76  movzx   ebx, ax
0x1400a1d79  or      ebx, 80070000h
0x1400a1d7f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1d84  mov     edx, 31h ; '1'
0x1400a1d89  jmp     loc_1400A1CFA
0x1400a1d8e  lea     r9, [rsp+48h+arg_8]
0x1400a1d93  xor     r8d, r8d
0x1400a1d96  xor     edx, edx
0x1400a1d98  lea     rcx, FOLDERID_LocalAppDataLow
0x1400a1d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a1da4  mov     ebx, eax
0x1400a1da6  test    eax, eax
0x1400a1da8  jns     short loc_1400A1DE8
0x1400a1daa  mov     rax, cs:WPP_GLOBAL_Control
0x1400a1db1  lea     rdi, WPP_GLOBAL_Control
0x1400a1db8  cmp     rax, rdi
0x1400a1dbb  jz      loc_1400A1F2E
0x1400a1dc1  test    byte ptr [rax+1Ch], 8
0x1400a1dc5  jz      loc_1400A1F2E
0x1400a1dcb  cmp     byte ptr [rax+19h], 2
0x1400a1dcf  jb      loc_1400A1F2E
0x1400a1dd5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1dda  mov     edx, 32h ; '2'
0x1400a1ddf  lea     rcx, aShgetknownfold_2; "SHGetKnownFolderPath(LocalAppDataLow) f"...
0x1400a1de6  jmp     short loc_1400A1E43
0x1400a1de8  mov     r9, [rsp+48h+arg_8]
0x1400a1ded  lea     r8, aSTemp; "%s\\Temp"
0x1400a1df4  mov     edx, 104h; unsigned __int64
0x1400a1df9  mov     rcx, r15; unsigned __int16 *
0x1400a1dfc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400a1e01  mov     ebx, eax
0x1400a1e03  test    eax, eax
0x1400a1e05  jns     short loc_1400A1E6B
0x1400a1e07  mov     rax, cs:WPP_GLOBAL_Control
0x1400a1e0e  lea     rdi, WPP_GLOBAL_Control
0x1400a1e15  cmp     rax, rdi
0x1400a1e18  jz      loc_1400A1F2E
0x1400a1e1e  test    byte ptr [rax+1Ch], 8
0x1400a1e22  jz      loc_1400A1F2E
0x1400a1e28  cmp     byte ptr [rax+19h], 2
0x1400a1e2c  jb      loc_1400A1F2E
0x1400a1e32  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1e37  mov     edx, 33h ; '3'
0x1400a1e3c  lea     rcx, aStringcchprint_3; "StringCchPrintf(KnownFolderPath\\Temp) "...
0x1400a1e43  mov     [rsp+48h+var_20], ebx
0x1400a1e47  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1400a1e4e  mov     [rsp+48h+var_28], rcx
0x1400a1e53  mov     r9d, eax
0x1400a1e56  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1e5d  mov     rcx, [rcx+10h]
0x1400a1e61  call    WPP_SF_DsD
0x1400a1e66  jmp     loc_1400A1F2E
0x1400a1e6b  xor     edx, edx; lpSecurityAttributes
0x1400a1e6d  mov     rcx, r15; lpPathName
0x1400a1e70  call    cs:__imp_CreateDirectoryW
0x1400a1e76  test    eax, eax
0x1400a1e78  jnz     loc_1400A1F34
0x1400a1e7e  call    cs:__imp_GetLastError
0x1400a1e84  mov     ebp, eax
0x1400a1e86  cmp     eax, 0B7h
0x1400a1e8b  jz      loc_1400A1F34
0x1400a1e91  test    eax, eax
0x1400a1e93  jg      short loc_1400A1E99
0x1400a1e95  mov     ebx, eax
0x1400a1e97  jmp     short loc_1400A1EA2
0x1400a1e99  movzx   ebx, bp
0x1400a1e9c  or      ebx, 80070000h
0x1400a1ea2  mov     rax, cs:WPP_GLOBAL_Control
0x1400a1ea9  lea     rdi, WPP_GLOBAL_Control
0x1400a1eb0  cmp     rax, rdi
0x1400a1eb3  jz      short loc_1400A1F2A
0x1400a1eb5  test    byte ptr [rax+1Ch], 1
0x1400a1eb9  jz      short loc_1400A1EF0
0x1400a1ebb  cmp     byte ptr [rax+19h], 2
0x1400a1ebf  jb      short loc_1400A1EF0
0x1400a1ec1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1ec6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1ecd  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1400a1ed4  mov     edx, 34h ; '4'
0x1400a1ed9  mov     dword ptr [rsp+48h+var_28], ebp
0x1400a1edd  mov     r9d, eax
0x1400a1ee0  mov     rcx, [rcx+10h]
0x1400a1ee4  call    WPP_SF_Dd
0x1400a1ee9  mov     rax, cs:WPP_GLOBAL_Control
0x1400a1ef0  cmp     rax, rdi
0x1400a1ef3  jz      short loc_1400A1F2A
0x1400a1ef5  test    byte ptr [rax+1Ch], 1
0x1400a1ef9  jz      short loc_1400A1F2A
0x1400a1efb  cmp     byte ptr [rax+19h], 3
0x1400a1eff  jb      short loc_1400A1F2A
0x1400a1f01  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1f06  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1f0d  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1400a1f14  mov     edx, 35h ; '5'
0x1400a1f19  mov     [rsp+48h+var_28], r15
0x1400a1f1e  mov     r9d, eax
0x1400a1f21  mov     rcx, [rcx+10h]
0x1400a1f25  call    WPP_SF_DS
0x1400a1f2a  test    ebx, ebx
0x1400a1f2c  jns     short loc_1400A1F34
0x1400a1f2e  xor     eax, eax
0x1400a1f30  mov     [r15], ax
0x1400a1f34  mov     rcx, [rsp+48h+arg_8]
0x1400a1f39  jmp     short loc_1400A1F43
0x1400a1f3b  xor     r14d, r14d
0x1400a1f3e  mov     ebx, 80070057h
0x1400a1f43  test    rcx, rcx
0x1400a1f46  jz      short loc_1400A1F4E
0x1400a1f48  call    cs:__imp_CoTaskMemFree
0x1400a1f4e  test    r14, r14
0x1400a1f51  jz      short loc_1400A1F5C
0x1400a1f53  mov     rcx, r14; hLibModule
0x1400a1f56  call    cs:__imp_FreeLibrary
0x1400a1f5c  mov     rbp, [rsp+48h+arg_10]
0x1400a1f61  mov     eax, ebx
0x1400a1f63  mov     rbx, [rsp+48h+arg_0]
0x1400a1f68  add     rsp, 30h
0x1400a1f6c  pop     r15
0x1400a1f6e  pop     r14
0x1400a1f70  pop     rdi
0x1400a1f71  retn
```
