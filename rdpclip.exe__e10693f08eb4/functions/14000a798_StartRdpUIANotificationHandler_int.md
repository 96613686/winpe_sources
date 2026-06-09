# StartRdpUIANotificationHandler(int *)

- ea: `0x14000a798`
- end: `0x14000abdd`
- name: `?StartRdpUIANotificationHandler@@YAXPEAH@Z`
- size: `1093`
- prototype: `void __fastcall(int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140004fb0`
- `0x140015c20`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x1400056c4`
- `0x140005704`
- `0x140008ce0`
- `0x14000a640`
- `0x14000a6c0`
- `0x14000a798`
- `0x14006a120`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x14000a983`
- `msvcrt!_wsplitpath_s` at `0x14000a983`
- `msvcrt!_wmakepath_s` at `0x14000a9bf`
- `msvcrt!_wmakepath_s` at `0x14000a9bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a7dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a7dc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14000a7d3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14000a7d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000a891`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000a891`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000a84d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000a84d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a804`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000aa8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ab17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a804`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000aa8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ab17`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x14000a911`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x14000a911`
- `SHELL32!ShellExecuteW` at `0x14000aa3c`
- `SHELL32!ShellExecuteW` at `0x14000aa3c`
- `WINSTA!WinStationVirtualOpenEx` at `0x14000a827`
- `WINSTA!WinStationVirtualOpenEx` at `0x14000a827`

## string_xrefs

- `0x14000a7c8`: `RdpNotifyAlreadyRunningMutex`

## pseudocode

```c
void __fastcall StartRdpUIANotificationHandler(int *a1)
{
  HANDLE MutexW; // rbx
  DWORD LastError; // eax
  int v4; // r14d
  int v5; // r12d
  void *v6; // r14
  int v7; // esi
  HANDLE CurrentProcess; // r15
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  PVOID *v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // eax
  DWORD DirCount; // [rsp+20h] [rbp-E0h]
  DWORD dwSize; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Drive[2]; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v19; // [rsp+58h] [rbp-A8h]
  wchar_t Buffer[256]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Parameters[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR ExeName[264]; // [rsp+470h] [rbp+370h] BYREF
  wchar_t Dir[264]; // [rsp+680h] [rbp+580h] BYREF

  MutexW = CreateMutexW(0, 0, L"RdpNotifyAlreadyRunningMutex");
  LastError = GetLastError();
  if ( !MutexW || LastError == 183 )
  {
    v4 = 1;
    if ( !MutexW )
      goto LABEL_6;
  }
  else
  {
    v4 = 0;
  }
  CloseHandle(MutexW);
LABEL_6:
  v5 = 0;
  if ( !v4 )
  {
    v6 = (void *)WinStationVirtualOpenEx(0, 0xFFFFFFFFLL, "Microsoft::Windows::RDS::Notify", 15);
    if ( !v6 )
      goto LABEL_46;
    memset_0(Parameters, 0, 0x208u);
    DirCount = GetCurrentProcessId();
    v7 = StringCchPrintfW(Parameters, 0x104u, L"%s%d %s%Id", L"/pid:", DirCount, L"/handle:", v6);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_f0d6bd2394e7306c08992e14a76eeedf_Traceguids,
          CurrentThreadActivityIdPrefix,
          v7);
      }
      goto LABEL_37;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !CurrentProcess )
    {
LABEL_29:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_f0d6bd2394e7306c08992e14a76eeedf_Traceguids, v11);
      }
LABEL_37:
      CloseHandle(v6);
      goto LABEL_46;
    }
    memset_0(ExeName, 0, 0x208u);
    dwSize = 260;
    memset_0(Buffer, 0, sizeof(Buffer));
    *(_DWORD *)Drive = 0;
    v19 = 0;
    memset_0(Dir, 0, 0x208u);
    if ( QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize) )
    {
      if ( !_wsplitpath_s(ExeName, Drive, 3u, Dir, 0x104u, 0, 0, 0, 0)
        && !_wmakepath_s(Buffer, 0x100u, Drive, Dir, L"rdpnotify", L"EXE") )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)Buffer, (__int64)Parameters);
        }
        if ( (__int64)ShellExecuteW(0, L"open", Buffer, Parameters, 0, 1) > 32 )
        {
          v5 = 1;
          goto LABEL_46;
        }
        goto LABEL_29;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_28;
      }
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 12;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_28;
      }
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 10;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_f0d6bd2394e7306c08992e14a76eeedf_Traceguids, v9);
LABEL_28:
    CloseHandle(v6);
    goto LABEL_29;
  }
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_f0d6bd2394e7306c08992e14a76eeedf_Traceguids,
        v14,
        (__int64)L"rdpnotify");
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_f0d6bd2394e7306c08992e14a76eeedf_Traceguids, v15, v4);
    }
  }
LABEL_46:
  if ( a1 )
    *a1 = v5;
}

```

## disassembly

```asm
0x14000a798  push    rbp
0x14000a79a  push    rbx
0x14000a79b  push    rsi
0x14000a79c  push    rdi
0x14000a79d  push    r12
0x14000a79f  push    r13
0x14000a7a1  push    r14
0x14000a7a3  push    r15
0x14000a7a5  lea     rbp, [rsp-7A8h]
0x14000a7ad  sub     rsp, 8A8h
0x14000a7b4  mov     rax, cs:__security_cookie
0x14000a7bb  xor     rax, rsp
0x14000a7be  mov     [rbp+7E0h+var_50], rax
0x14000a7c5  mov     r13, rcx
0x14000a7c8  lea     r8, aRdpnotifyalrea; "RdpNotifyAlreadyRunningMutex"
0x14000a7cf  xor     ecx, ecx; lpMutexAttributes
0x14000a7d1  xor     edx, edx; bInitialOwner
0x14000a7d3  call    cs:__imp_CreateMutexW
0x14000a7d9  mov     rbx, rax
0x14000a7dc  call    cs:__imp_GetLastError
0x14000a7e2  mov     r15d, 1
0x14000a7e8  test    rbx, rbx
0x14000a7eb  jz      short loc_14000A7F9
0x14000a7ed  cmp     eax, 0B7h
0x14000a7f2  jz      short loc_14000A7F9
0x14000a7f4  xor     r14d, r14d
0x14000a7f7  jmp     short loc_14000A801
0x14000a7f9  mov     r14d, r15d
0x14000a7fc  test    rbx, rbx
0x14000a7ff  jz      short loc_14000A80A
0x14000a801  mov     rcx, rbx; hObject
0x14000a804  call    cs:__imp_CloseHandle
0x14000a80a  xor     r12d, r12d
0x14000a80d  test    r14d, r14d
0x14000a810  jnz     loc_14000AB22
0x14000a816  lea     r9d, [r12+0Fh]
0x14000a81b  or      edx, 0FFFFFFFFh
0x14000a81e  lea     r8, aMicrosoftWindo_5; "Microsoft::Windows::RDS::Notify"
0x14000a825  xor     ecx, ecx
0x14000a827  call    cs:__imp_WinStationVirtualOpenEx
0x14000a82d  mov     r14, rax
0x14000a830  test    rax, rax
0x14000a833  jz      loc_14000ABB1
0x14000a839  xor     edx, edx; Val
0x14000a83b  lea     rcx, [rbp+7E0h+Parameters]; void *
0x14000a842  mov     r8d, 208h; Size
0x14000a848  call    memset_0
0x14000a84d  call    cs:__imp_GetCurrentProcessId
0x14000a853  lea     rcx, aHandle_0; "/handle:"
0x14000a85a  mov     [rsp+8E0h+FilenameCount], r14
0x14000a85f  mov     [rsp+8E0h+Filename], rcx
0x14000a864  lea     r9, aPid; "/pid:"
0x14000a86b  lea     rcx, [rbp+7E0h+Parameters]; unsigned __int16 *
0x14000a872  mov     dword ptr [rsp+8E0h+DirCount], eax
0x14000a876  lea     r8, aSDSId; "%s%d %s%Id"
0x14000a87d  mov     edx, 104h; unsigned __int64
0x14000a882  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a887  mov     esi, eax
0x14000a889  test    eax, eax
0x14000a88b  js      loc_14000AACC
0x14000a891  call    cs:__imp_GetCurrentProcess
0x14000a897  lea     rdi, WPP_GLOBAL_Control
0x14000a89e  mov     bl, 2
0x14000a8a0  lea     rsi, WPP_f0d6bd2394e7306c08992e14a76eeedf_Traceguids
0x14000a8a7  mov     r15, rax
0x14000a8aa  test    rax, rax
0x14000a8ad  jz      loc_14000AA93
0x14000a8b3  xor     edx, edx; Val
0x14000a8b5  lea     rcx, [rbp+7E0h+ExeName]; void *
0x14000a8bc  mov     r8d, 208h; Size
0x14000a8c2  call    memset_0
0x14000a8c7  xor     edx, edx; Val
0x14000a8c9  mov     [rsp+8E0h+dwSize], 104h
0x14000a8d1  mov     r8d, 200h; Size
0x14000a8d7  lea     rcx, [rsp+8E0h+Buffer]; void *
0x14000a8dc  call    memset_0
0x14000a8e1  xor     eax, eax
0x14000a8e3  lea     rcx, [rbp+7E0h+Dir]; void *
0x14000a8ea  xor     edx, edx; Val
0x14000a8ec  mov     dword ptr [rsp+8E0h+Drive], eax
0x14000a8f0  mov     r8d, 208h; Size
0x14000a8f6  mov     [rsp+8E0h+var_888], ax
0x14000a8fb  call    memset_0
0x14000a900  lea     r9, [rsp+8E0h+dwSize]; lpdwSize
0x14000a905  xor     edx, edx; dwFlags
0x14000a907  lea     r8, [rbp+7E0h+ExeName]; lpExeName
0x14000a90e  mov     rcx, r15; hProcess
0x14000a911  call    cs:__imp_QueryFullProcessImageNameW
0x14000a917  test    eax, eax
0x14000a919  jnz     short loc_14000A94D
0x14000a91b  mov     rax, cs:WPP_GLOBAL_Control
0x14000a922  cmp     rax, rdi
0x14000a925  jz      loc_14000AA8A
0x14000a92b  test    byte ptr [rax+1Ch], 1
0x14000a92f  jz      loc_14000AA8A
0x14000a935  cmp     [rax+19h], bl
0x14000a938  jb      loc_14000AA8A
0x14000a93e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000a943  lea     edx, [r12+0Ah]
0x14000a948  jmp     loc_14000AA74
0x14000a94d  mov     [rsp+8E0h+ExtCount], r12; ExtCount
0x14000a952  lea     r9, [rbp+7E0h+Dir]; Dir
0x14000a959  mov     [rsp+8E0h+Ext], r12; Ext
0x14000a95e  lea     rdx, [rsp+8E0h+Drive]; Drive
0x14000a963  mov     [rsp+8E0h+FilenameCount], r12; FilenameCount
0x14000a968  lea     rcx, [rbp+7E0h+ExeName]; FullPath
0x14000a96f  mov     [rsp+8E0h+Filename], r12; Filename
0x14000a974  mov     r8d, 3; DriveCount
0x14000a97a  mov     [rsp+8E0h+DirCount], 104h; DirCount
0x14000a983  call    cs:__imp__wsplitpath_s
0x14000a989  test    eax, eax
0x14000a98b  jnz     loc_14000AA53
0x14000a991  lea     rax, aExe; "EXE"
0x14000a998  mov     edx, 100h; BufferCount
0x14000a99d  lea     rcx, aRdpnotify; "rdpnotify"
0x14000a9a4  mov     [rsp+8E0h+Filename], rax; Ext
0x14000a9a9  mov     [rsp+8E0h+DirCount], rcx; Filename
0x14000a9ae  lea     r9, [rbp+7E0h+Dir]; Dir
0x14000a9b5  lea     rcx, [rsp+8E0h+Buffer]; Buffer
0x14000a9ba  lea     r8, [rsp+8E0h+Drive]; Drive
0x14000a9bf  call    cs:__imp__wmakepath_s
0x14000a9c5  test    eax, eax
0x14000a9c7  jnz     loc_14000AA53
0x14000a9cd  mov     rax, cs:WPP_GLOBAL_Control
0x14000a9d4  cmp     rax, rdi
0x14000a9d7  jz      short loc_14000AA1A
0x14000a9d9  test    byte ptr [rax+1Ch], 1
0x14000a9dd  jz      short loc_14000AA1A
0x14000a9df  cmp     [rax+19h], bl
0x14000a9e2  jb      short loc_14000AA1A
0x14000a9e4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000a9e9  lea     rcx, [rbp+7E0h+Parameters]
0x14000a9f0  mov     edx, 0Bh
0x14000a9f5  mov     [rsp+8E0h+Filename], rcx; __int64
0x14000a9fa  mov     r9d, eax
0x14000a9fd  lea     rcx, [rsp+8E0h+Buffer]
0x14000aa02  mov     r8, rsi
0x14000aa05  mov     [rsp+8E0h+DirCount], rcx; __int64
0x14000aa0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aa11  mov     rcx, [rcx+10h]; LoggerHandle
0x14000aa15  call    WPP_SF_DSS
0x14000aa1a  mov     dword ptr [rsp+8E0h+Filename], 1; nShowCmd
0x14000aa22  lea     r9, [rbp+7E0h+Parameters]; lpParameters
0x14000aa29  lea     r8, [rsp+8E0h+Buffer]; lpFile
0x14000aa2e  mov     [rsp+8E0h+DirCount], r12; lpDirectory
0x14000aa33  lea     rdx, Operation; "open"
0x14000aa3a  xor     ecx, ecx; hwnd
0x14000aa3c  call    cs:__imp_ShellExecuteW
0x14000aa42  cmp     rax, 20h ; ' '
0x14000aa46  jle     short loc_14000AA93
0x14000aa48  mov     r12d, 1
0x14000aa4e  jmp     loc_14000ABB1
0x14000aa53  mov     rax, cs:WPP_GLOBAL_Control
0x14000aa5a  cmp     rax, rdi
0x14000aa5d  jz      short loc_14000AA8A
0x14000aa5f  test    byte ptr [rax+1Ch], 1
0x14000aa63  jz      short loc_14000AA8A
0x14000aa65  cmp     [rax+19h], bl
0x14000aa68  jb      short loc_14000AA8A
0x14000aa6a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000aa6f  mov     edx, 0Ch
0x14000aa74  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aa7b  mov     r9d, eax
0x14000aa7e  mov     r8, rsi
0x14000aa81  mov     rcx, [rcx+10h]
0x14000aa85  call    WPP_SF_d
0x14000aa8a  mov     rcx, r14; hObject
0x14000aa8d  call    cs:__imp_CloseHandle
0x14000aa93  mov     rax, cs:WPP_GLOBAL_Control
0x14000aa9a  cmp     rax, rdi
0x14000aa9d  jz      short loc_14000AB14
0x14000aa9f  test    byte ptr [rax+1Ch], 1
0x14000aaa3  jz      short loc_14000AB14
0x14000aaa5  cmp     [rax+19h], bl
0x14000aaa8  jb      short loc_14000AB14
0x14000aaaa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000aaaf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aab6  mov     edx, 0Dh
0x14000aabb  mov     r9d, eax
0x14000aabe  mov     r8, rsi
0x14000aac1  mov     rcx, [rcx+10h]
0x14000aac5  call    WPP_SF_d
0x14000aaca  jmp     short loc_14000AB14
0x14000aacc  mov     rax, cs:WPP_GLOBAL_Control
0x14000aad3  lea     rdi, WPP_GLOBAL_Control
0x14000aada  cmp     rax, rdi
0x14000aadd  jz      short loc_14000AB14
0x14000aadf  test    [rax+1Ch], r15b
0x14000aae3  jz      short loc_14000AB14
0x14000aae5  mov     bl, 2
0x14000aae7  cmp     [rax+19h], bl
0x14000aaea  jb      short loc_14000AB14
0x14000aaec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000aaf1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aaf8  lea     r8, WPP_f0d6bd2394e7306c08992e14a76eeedf_Traceguids
0x14000aaff  mov     edx, 0Eh
0x14000ab04  mov     dword ptr [rsp+8E0h+DirCount], esi
0x14000ab08  mov     r9d, eax
0x14000ab0b  mov     rcx, [rcx+10h]
0x14000ab0f  call    WPP_SF_Dd
0x14000ab14  mov     rcx, r14; hObject
0x14000ab17  call    cs:__imp_CloseHandle
0x14000ab1d  jmp     loc_14000ABB1
0x14000ab22  mov     rax, cs:WPP_GLOBAL_Control
0x14000ab29  lea     rdi, WPP_GLOBAL_Control
0x14000ab30  cmp     rax, rdi
0x14000ab33  jz      short loc_14000ABB1
0x14000ab35  lea     rsi, WPP_f0d6bd2394e7306c08992e14a76eeedf_Traceguids
0x14000ab3c  mov     bl, 2
0x14000ab3e  test    [rax+1Ch], r15b
0x14000ab42  jz      short loc_14000AB7C
0x14000ab44  cmp     [rax+19h], bl
0x14000ab47  jb      short loc_14000AB7C
0x14000ab49  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000ab4e  lea     rcx, aRdpnotify; "rdpnotify"
0x14000ab55  mov     edx, 0Fh
0x14000ab5a  mov     [rsp+8E0h+DirCount], rcx
0x14000ab5f  mov     r9d, eax
0x14000ab62  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ab69  mov     r8, rsi
0x14000ab6c  mov     rcx, [rcx+10h]
0x14000ab70  call    WPP_SF_DS
0x14000ab75  mov     rax, cs:WPP_GLOBAL_Control
0x14000ab7c  cmp     rax, rdi
0x14000ab7f  jz      short loc_14000ABB1
0x14000ab81  test    [rax+1Ch], r15b
0x14000ab85  jz      short loc_14000ABB1
0x14000ab87  cmp     [rax+19h], bl
0x14000ab8a  jb      short loc_14000ABB1
0x14000ab8c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000ab91  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ab98  mov     edx, 10h
0x14000ab9d  mov     r9d, eax
0x14000aba0  mov     dword ptr [rsp+8E0h+DirCount], r14d
0x14000aba5  mov     r8, rsi
0x14000aba8  mov     rcx, [rcx+10h]
0x14000abac  call    WPP_SF_Dd
0x14000abb1  test    r13, r13
0x14000abb4  jz      short loc_14000ABBA
0x14000abb6  mov     [r13+0], r12d
0x14000abba  mov     rcx, [rbp+7E0h+var_50]
0x14000abc1  xor     rcx, rsp; StackCookie
0x14000abc4  call    __security_check_cookie
0x14000abc9  add     rsp, 8A8h
0x14000abd0  pop     r15
0x14000abd2  pop     r14
0x14000abd4  pop     r13
0x14000abd6  pop     r12
0x14000abd8  pop     rdi
0x14000abd9  pop     rsi
0x14000abda  pop     rbx
0x14000abdb  pop     rbp
0x14000abdc  retn
```
