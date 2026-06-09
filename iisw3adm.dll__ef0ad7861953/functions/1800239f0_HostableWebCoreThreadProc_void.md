# HostableWebCoreThreadProc(void *)

- ea: `0x1800239f0`
- end: `0x180023c86`
- name: `?HostableWebCoreThreadProc@@YAKPEAX@Z`
- size: `662`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001274`
- `0x1800239f0`
- `0x18006101a`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023bd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023bd0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180023c35`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180023c35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023baa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023baa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bf9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180023a87`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180023ae6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180023a87`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180023ae6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180023b7e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180023b7e`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180023b00`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180023b00`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023c40`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023c4b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023c40`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023c4b`
- `iisutil!PuDbgPrint` at `0x180023b69`
- `iisutil!PuDbgPrint` at `0x180023b69`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180023a47`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180023a6d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180023a47`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180023a6d`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180023ac2`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180023ac2`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180023af5`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180023af5`

## string_xrefs

- `0x180023b5d`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180023a78`: `%windir%\system32\inetsrv`
- `0x180023ad7`: `%windir%\system32\inetsrv`
- `0x180023b36`: `w3wphost.dll`
- `0x180023b74`: `w3wphost.dll`
- `0x180023b3d`: `Error loading process model hosting dll '%ws'. SetDllDirectory() failed.  Error = %d\n`
- `0x180023b51`: `HostableWebCoreThreadProc`
- `0x180023bba`: `Error loading process model hosting dll '%ws'.  Error = %d\n`

## pseudocode

```c
__int64 __fastcall HostableWebCoreThreadProc(PVOID Parameter)
{
  HMODULE v2; // rdi
  DWORD v3; // edx
  signed int v4; // eax
  signed int v5; // ebx
  signed int v6; // eax
  HMODULE LibraryW; // rax
  signed int v8; // eax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  DWORD v12; // [rsp+30h] [rbp-D0h]
  DWORD v13; // [rsp+30h] [rbp-D0h]
  DWORD v14; // [rsp+30h] [rbp-D0h]
  _BYTE v15[32]; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR lpDst; // [rsp+60h] [rbp-A0h]
  unsigned int v17; // [rsp+68h] [rbp-98h]
  _BYTE v18[56]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v19[256]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v20[256]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v2 = 0;
  memset_0(v19, 0, sizeof(v19));
  STRU::STRU((STRU *)v18, v19, 0x100u);
  memset_0(v20, 0, sizeof(v20));
  STRU::STRU((STRU *)v15, v20, 0x100u);
  v3 = ExpandEnvironmentStringsW(L"%windir%\\system32\\inetsrv", lpDst, v17 >> 1);
  if ( !v3 )
    goto LABEL_2;
  if ( v3 <= v17 >> 1 )
    goto LABEL_7;
  v5 = STRU::Resize((STRU *)v15, 2 * v3);
  if ( v5 < 0 )
    goto LABEL_24;
  if ( ExpandEnvironmentStringsW(L"%windir%\\system32\\inetsrv", lpDst, v17 >> 1) )
  {
LABEL_7:
    STRU::SyncWithBuffer((STRU *)v15);
    if ( SetDllDirectoryW(lpDst) )
    {
      LibraryW = LoadLibraryW(L"w3wphost.dll");
      v2 = LibraryW;
      if ( LibraryW )
      {
        ProcAddress = GetProcAddress(LibraryW, "AppHostInitialize");
        if ( ProcAddress )
        {
          v5 = ((__int64 (__fastcall *)(PVOID, _QWORD, __int64))ProcAddress)(Parameter, 0, 1);
        }
        else
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            v14 = GetLastError();
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
              3496,
              "HostableWebCoreThreadProc",
              "Could not find entry point '%s'.  Error = %d\n",
              "AppHostInitialize",
              v14);
          }
        }
      }
      else
      {
        v8 = GetLastError();
        v5 = v8;
        if ( v8 > 0 )
          v5 = (unsigned __int16)v8 | 0x80070000;
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          v13 = GetLastError();
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
            3482,
            "HostableWebCoreThreadProc",
            "Error loading process model hosting dll '%ws'.  Error = %d\n",
            L"w3wphost.dll",
            v13);
        }
      }
    }
    else
    {
      v6 = GetLastError();
      v5 = v6;
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        v12 = GetLastError();
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
          3468,
          "HostableWebCoreThreadProc",
          "Error loading process model hosting dll '%ws'. SetDllDirectory() failed.  Error = %d\n",
          L"w3wphost.dll",
          v12);
      }
    }
  }
  else
  {
LABEL_2:
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
LABEL_24:
  operator delete(Parameter);
  if ( v2 )
    FreeLibrary(v2);
  STRU::~STRU((STRU *)v15);
  STRU::~STRU((STRU *)v18);
  if ( v5 < 0 )
    return 0xFFFFFFFFLL;
  else
    return 4294967294LL;
}

```

## disassembly

```asm
0x1800239f0  mov     [rsp-8+arg_8], rbx
0x1800239f5  mov     [rsp-8+arg_10], rsi
0x1800239fa  push    rbp
0x1800239fb  push    rdi
0x1800239fc  push    r14
0x1800239fe  lea     rbp, [rsp-3C0h]
0x180023a06  sub     rsp, 4C0h
0x180023a0d  mov     rax, cs:__security_cookie
0x180023a14  xor     rax, rsp
0x180023a17  mov     [rbp+3D0h+var_20], rax
0x180023a1e  mov     r14, rcx
0x180023a21  mov     esi, 200h
0x180023a26  mov     r8d, esi; Size
0x180023a29  lea     rcx, [rbp+3D0h+var_420]; void *
0x180023a2d  xor     edx, edx; Val
0x180023a2f  xor     edi, edi
0x180023a31  call    memset_0
0x180023a36  mov     ebx, 100h
0x180023a3b  lea     rdx, [rbp+3D0h+var_420]
0x180023a3f  mov     r8d, ebx
0x180023a42  lea     rcx, [rsp+4D0h+var_458]
0x180023a47  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180023a4d  mov     r8d, esi; Size
0x180023a50  lea     rcx, [rbp+3D0h+var_220]; void *
0x180023a57  xor     edx, edx; Val
0x180023a59  call    memset_0
0x180023a5e  mov     r8d, ebx
0x180023a61  lea     rdx, [rbp+3D0h+var_220]
0x180023a68  lea     rcx, [rsp+4D0h+var_490]
0x180023a6d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180023a73  mov     r8d, [rsp+4D0h+var_468]
0x180023a78  lea     rcx, Src; "%windir%\\system32\\inetsrv"
0x180023a7f  mov     rdx, [rsp+4D0h+lpDst]; lpDst
0x180023a84  shr     r8d, 1; nSize
0x180023a87  call    cs:__imp_ExpandEnvironmentStringsW
0x180023a8d  mov     edx, eax
0x180023a8f  test    eax, eax
0x180023a91  jnz     short loc_180023AB1
0x180023a93  call    cs:__imp_GetLastError
0x180023a99  mov     ebx, eax
0x180023a9b  test    eax, eax
0x180023a9d  jle     loc_180023C25
0x180023aa3  movzx   ebx, ax
0x180023aa6  or      ebx, 80070000h
0x180023aac  jmp     loc_180023C25
0x180023ab1  mov     eax, [rsp+4D0h+var_468]
0x180023ab5  shr     eax, 1
0x180023ab7  cmp     edx, eax
0x180023ab9  jbe     short loc_180023AF0
0x180023abb  add     edx, edx
0x180023abd  lea     rcx, [rsp+4D0h+var_490]
0x180023ac2  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180023ac8  mov     ebx, eax
0x180023aca  test    eax, eax
0x180023acc  js      loc_180023C25
0x180023ad2  mov     r8d, [rsp+4D0h+var_468]
0x180023ad7  lea     rcx, Src; "%windir%\\system32\\inetsrv"
0x180023ade  mov     rdx, [rsp+4D0h+lpDst]; lpDst
0x180023ae3  shr     r8d, 1; nSize
0x180023ae6  call    cs:__imp_ExpandEnvironmentStringsW
0x180023aec  test    eax, eax
0x180023aee  jz      short loc_180023A93
0x180023af0  lea     rcx, [rsp+4D0h+var_490]
0x180023af5  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180023afb  mov     rcx, [rsp+4D0h+lpDst]; lpPathName
0x180023b00  call    cs:__imp_SetDllDirectoryW
0x180023b06  test    eax, eax
0x180023b08  jnz     short loc_180023B74
0x180023b0a  call    cs:__imp_GetLastError
0x180023b10  mov     ebx, eax
0x180023b12  test    eax, eax
0x180023b14  jle     short loc_180023B1F
0x180023b16  movzx   ebx, ax
0x180023b19  or      ebx, 80070000h
0x180023b1f  test    byte ptr cs:g_dwDebugFlags, 3
0x180023b26  jz      loc_180023C25
0x180023b2c  call    cs:__imp_GetLastError
0x180023b32  mov     [rsp+4D0h+var_4A0], eax
0x180023b36  lea     rsi, LibFileName; "w3wphost.dll"
0x180023b3d  lea     rax, aErrorLoadingPr; "Error loading process model hosting dll"...
0x180023b44  mov     r8d, 0D8Ch
0x180023b4a  mov     rcx, cs:g_pDebug
0x180023b51  lea     r9, aHostablewebcor; "HostableWebCoreThreadProc"
0x180023b58  mov     [rsp+4D0h+var_4A8], rsi
0x180023b5d  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180023b64  mov     [rsp+4D0h+var_4B0], rax
0x180023b69  call    cs:__imp_PuDbgPrint
0x180023b6f  jmp     loc_180023C25
0x180023b74  lea     rsi, LibFileName; "w3wphost.dll"
0x180023b7b  mov     rcx, rsi; lpLibFileName
0x180023b7e  call    cs:__imp_LoadLibraryW
0x180023b84  mov     rdi, rax
0x180023b87  test    rax, rax
0x180023b8a  jnz     short loc_180023BC3
0x180023b8c  call    cs:__imp_GetLastError
0x180023b92  mov     ebx, eax
0x180023b94  test    eax, eax
0x180023b96  jle     short loc_180023BA1
0x180023b98  movzx   ebx, ax
0x180023b9b  or      ebx, 80070000h
0x180023ba1  test    byte ptr cs:g_dwDebugFlags, 3
0x180023ba8  jz      short loc_180023C25
0x180023baa  call    cs:__imp_GetLastError
0x180023bb0  mov     [rsp+4D0h+var_4A0], eax
0x180023bb4  mov     r8d, 0D9Ah
0x180023bba  lea     rax, aErrorLoadingPr_0; "Error loading process model hosting dll"...
0x180023bc1  jmp     short loc_180023B4A
0x180023bc3  lea     rsi, ProcName; "AppHostInitialize"
0x180023bca  mov     rcx, rax; hModule
0x180023bcd  mov     rdx, rsi; lpProcName
0x180023bd0  call    cs:__imp_GetProcAddress
0x180023bd6  test    rax, rax
0x180023bd9  jnz     short loc_180023C15
0x180023bdb  call    cs:__imp_GetLastError
0x180023be1  mov     ebx, eax
0x180023be3  test    eax, eax
0x180023be5  jle     short loc_180023BF0
0x180023be7  movzx   ebx, ax
0x180023bea  or      ebx, 80070000h
0x180023bf0  test    byte ptr cs:g_dwDebugFlags, 3
0x180023bf7  jz      short loc_180023C25
0x180023bf9  call    cs:__imp_GetLastError
0x180023bff  mov     [rsp+4D0h+var_4A0], eax
0x180023c03  mov     r8d, 0DA8h
0x180023c09  lea     rax, aCouldNotFindEn; "Could not find entry point '%s'.  Error"...
0x180023c10  jmp     loc_180023B4A
0x180023c15  xor     edx, edx
0x180023c17  mov     rcx, r14
0x180023c1a  lea     r8d, [rdx+1]
0x180023c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c23  mov     ebx, eax
0x180023c25  mov     rcx, r14; Block
0x180023c28  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023c2d  test    rdi, rdi
0x180023c30  jz      short loc_180023C3B
0x180023c32  mov     rcx, rdi; hLibModule
0x180023c35  call    cs:__imp_FreeLibrary
0x180023c3b  lea     rcx, [rsp+4D0h+var_490]
0x180023c40  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180023c46  lea     rcx, [rsp+4D0h+var_458]
0x180023c4b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180023c51  test    ebx, ebx
0x180023c53  js      short loc_180023C5C
0x180023c55  mov     eax, 0FFFFFFFEh
0x180023c5a  jmp     short loc_180023C5F
0x180023c5c  or      eax, 0FFFFFFFFh
0x180023c5f  mov     rcx, [rbp+3D0h+var_20]
0x180023c66  xor     rcx, rsp; StackCookie
0x180023c69  call    __security_check_cookie
0x180023c6e  lea     r11, [rsp+4D0h+var_10]
0x180023c76  mov     rbx, [r11+28h]
0x180023c7a  mov     rsi, [r11+30h]
0x180023c7e  mov     rsp, r11
0x180023c81  pop     r14
0x180023c83  pop     rdi
0x180023c84  pop     rbp
0x180023c85  retn
```
