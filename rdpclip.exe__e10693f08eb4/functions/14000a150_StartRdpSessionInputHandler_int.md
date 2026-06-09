# StartRdpSessionInputHandler(int *)

- ea: `0x14000a150`
- end: `0x14000a637`
- name: `?StartRdpSessionInputHandler@@YAXPEAH@Z`
- size: `1255`
- prototype: `void __fastcall(int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140004fb0`
- `0x140015c20`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x1400056c4`
- `0x140005704`
- `0x140008ce0`
- `0x14000a150`
- `0x14000a640`
- `0x14000a6c0`
- `0x14003054c`
- `0x140030c98`
- `0x14006a120`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x14000a359`
- `msvcrt!_wsplitpath_s` at `0x14000a359`
- `msvcrt!_wmakepath_s` at `0x14000a395`
- `msvcrt!_wmakepath_s` at `0x14000a395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a1a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a1a6`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14000a19d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14000a19d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000a26f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000a26f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000a227`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000a227`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a1cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a463`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a4ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a1cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a463`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a4ed`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x14000a2ec`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x14000a2ec`
- `SHELL32!ShellExecuteW` at `0x14000a412`
- `SHELL32!ShellExecuteW` at `0x14000a412`
- `WINSTA!WinStationVirtualOpenEx` at `0x14000a201`
- `WINSTA!WinStationVirtualOpenEx` at `0x14000a201`

## string_xrefs

- `0x14000a18f`: `RdpInputAlreadyRunningMutex`

## pseudocode

```c
void __fastcall StartRdpSessionInputHandler(int *a1)
{
  int IsRdpTouchRemotingPolicyEnabled; // r15d
  int v2; // r12d
  HANDLE MutexW; // rbx
  DWORD LastError; // eax
  int v5; // r14d
  int v6; // r13d
  void *v7; // r14
  int v8; // esi
  HANDLE CurrentProcess; // r15
  unsigned int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  PVOID *v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  DWORD DirCount; // [rsp+20h] [rbp-E0h]
  DWORD dwSize; // [rsp+50h] [rbp-B0h] BYREF
  int *v21; // [rsp+58h] [rbp-A8h]
  wchar_t Drive[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v23; // [rsp+64h] [rbp-9Ch]
  wchar_t Buffer[256]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Parameters[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR ExeName[264]; // [rsp+480h] [rbp+380h] BYREF
  wchar_t Dir[264]; // [rsp+690h] [rbp+590h] BYREF

  v21 = a1;
  IsRdpTouchRemotingPolicyEnabled = Win32PointerApi::IsRdpTouchRemotingPolicyEnabled();
  v2 = IsPointerInputRedirectionAllowed();
  MutexW = CreateMutexW(0, 0, L"RdpInputAlreadyRunningMutex");
  LastError = GetLastError();
  if ( MutexW && LastError != 183 )
  {
    v5 = 0;
LABEL_5:
    CloseHandle(MutexW);
    goto LABEL_6;
  }
  v5 = 1;
  if ( MutexW )
    goto LABEL_5;
LABEL_6:
  v6 = 0;
  if ( IsRdpTouchRemotingPolicyEnabled && v2 && !v5 )
  {
    v7 = (void *)WinStationVirtualOpenEx(0, 0xFFFFFFFFLL, "Microsoft::Windows::RDS::Input", 591);
    if ( !v7 )
      goto LABEL_56;
    memset_0(Parameters, 0, 0x208u);
    DirCount = GetCurrentProcessId();
    v8 = StringCchPrintfW(Parameters, 0x104u, L"%s%d %s%Id", L"/pid:", DirCount, L"/handle:", v7);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_58429c8c29ba3f29a0818ab0de17db3e_Traceguids,
          CurrentThreadActivityIdPrefix,
          v8);
      }
      goto LABEL_39;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !CurrentProcess )
    {
LABEL_31:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_58429c8c29ba3f29a0818ab0de17db3e_Traceguids, v12);
      }
LABEL_39:
      CloseHandle(v7);
      goto LABEL_56;
    }
    memset_0(ExeName, 0, 0x208u);
    dwSize = 260;
    memset_0(Buffer, 0, sizeof(Buffer));
    *(_DWORD *)Drive = 0;
    v23 = 0;
    memset_0(Dir, 0, 0x208u);
    if ( QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize) )
    {
      if ( !_wsplitpath_s(ExeName, Drive, 3u, Dir, 0x104u, 0, 0, 0, 0)
        && !_wmakepath_s(Buffer, 0x100u, Drive, Dir, L"rdpinput", L"EXE") )
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
          v6 = 1;
          goto LABEL_56;
        }
        goto LABEL_31;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_30;
      }
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 12;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_30;
      }
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 10;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_58429c8c29ba3f29a0818ab0de17db3e_Traceguids, v10);
LABEL_30:
    CloseHandle(v7);
    goto LABEL_31;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_58429c8c29ba3f29a0818ab0de17db3e_Traceguids,
        v15,
        (__int64)L"rdpinput");
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v14 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_58429c8c29ba3f29a0818ab0de17db3e_Traceguids,
          v16,
          IsRdpTouchRemotingPolicyEnabled);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v14 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 2u )
        {
          v17 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_58429c8c29ba3f29a0818ab0de17db3e_Traceguids, v17, v2);
          v14 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 2u )
        {
          v18 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_58429c8c29ba3f29a0818ab0de17db3e_Traceguids, v18, v5);
        }
      }
    }
  }
LABEL_56:
  if ( v21 )
    *v21 = v6;
}

```

## disassembly

```asm
0x14000a150  push    rbp
0x14000a152  push    rbx
0x14000a153  push    rsi
0x14000a154  push    rdi
0x14000a155  push    r12
0x14000a157  push    r13
0x14000a159  push    r14
0x14000a15b  push    r15
0x14000a15d  lea     rbp, [rsp-7B8h]
0x14000a165  sub     rsp, 8B8h
0x14000a16c  mov     rax, cs:__security_cookie
0x14000a173  xor     rax, rsp
0x14000a176  mov     [rbp+7F0h+var_50], rax
0x14000a17d  mov     [rsp+8F0h+var_898], rcx
0x14000a182  call    ?IsRdpTouchRemotingPolicyEnabled@Win32PointerApi@@SAHXZ; Win32PointerApi::IsRdpTouchRemotingPolicyEnabled(void)
0x14000a187  mov     r15d, eax
0x14000a18a  call    ?IsPointerInputRedirectionAllowed@@YAHXZ; IsPointerInputRedirectionAllowed(void)
0x14000a18f  lea     r8, Name; "RdpInputAlreadyRunningMutex"
0x14000a196  xor     edx, edx; bInitialOwner
0x14000a198  xor     ecx, ecx; lpMutexAttributes
0x14000a19a  mov     r12d, eax
0x14000a19d  call    cs:__imp_CreateMutexW
0x14000a1a3  mov     rbx, rax
0x14000a1a6  call    cs:__imp_GetLastError
0x14000a1ac  test    rbx, rbx
0x14000a1af  jz      short loc_14000A1BD
0x14000a1b1  cmp     eax, 0B7h
0x14000a1b6  jz      short loc_14000A1BD
0x14000a1b8  xor     r14d, r14d
0x14000a1bb  jmp     short loc_14000A1C8
0x14000a1bd  mov     r14d, 1
0x14000a1c3  test    rbx, rbx
0x14000a1c6  jz      short loc_14000A1D1
0x14000a1c8  mov     rcx, rbx; hObject
0x14000a1cb  call    cs:__imp_CloseHandle
0x14000a1d1  xor     r13d, r13d
0x14000a1d4  test    r15d, r15d
0x14000a1d7  jz      loc_14000A4F8
0x14000a1dd  test    r12d, r12d
0x14000a1e0  jz      loc_14000A4F8
0x14000a1e6  test    r14d, r14d
0x14000a1e9  jnz     loc_14000A4F8
0x14000a1ef  mov     r9d, 24Fh
0x14000a1f5  lea     r8, aMicrosoftWindo_2; "Microsoft::Windows::RDS::Input"
0x14000a1fc  or      edx, 0FFFFFFFFh
0x14000a1ff  xor     ecx, ecx
0x14000a201  call    cs:__imp_WinStationVirtualOpenEx
0x14000a207  mov     r14, rax
0x14000a20a  test    rax, rax
0x14000a20d  jz      loc_14000A607
0x14000a213  xor     edx, edx; Val
0x14000a215  lea     rcx, [rbp+7F0h+Parameters]; void *
0x14000a21c  mov     r8d, 208h; Size
0x14000a222  call    memset_0
0x14000a227  call    cs:__imp_GetCurrentProcessId
0x14000a22d  lea     rcx, aHandle_0; "/handle:"
0x14000a234  mov     [rsp+8F0h+FilenameCount], r14
0x14000a239  mov     [rsp+8F0h+Filename], rcx
0x14000a23e  lea     r9, aPid; "/pid:"
0x14000a245  mov     r12d, 104h
0x14000a24b  mov     dword ptr [rsp+8F0h+DirCount], eax
0x14000a24f  lea     rcx, [rbp+7F0h+Parameters]; unsigned __int16 *
0x14000a256  mov     edx, r12d; unsigned __int64
0x14000a259  lea     r8, aSDSId; "%s%d %s%Id"
0x14000a260  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a265  mov     esi, eax
0x14000a267  test    eax, eax
0x14000a269  js      loc_14000A4A2
0x14000a26f  call    cs:__imp_GetCurrentProcess
0x14000a275  lea     rdi, WPP_GLOBAL_Control
0x14000a27c  mov     bl, 2
0x14000a27e  lea     rsi, WPP_58429c8c29ba3f29a0818ab0de17db3e_Traceguids
0x14000a285  mov     r15, rax
0x14000a288  test    rax, rax
0x14000a28b  jz      loc_14000A469
0x14000a291  xor     edx, edx; Val
0x14000a293  lea     rcx, [rbp+7F0h+ExeName]; void *
0x14000a29a  mov     r8d, 208h; Size
0x14000a2a0  call    memset_0
0x14000a2a5  xor     edx, edx; Val
0x14000a2a7  mov     [rsp+8F0h+dwSize], r12d
0x14000a2ac  mov     r8d, 200h; Size
0x14000a2b2  lea     rcx, [rsp+8F0h+Buffer]; void *
0x14000a2b7  call    memset_0
0x14000a2bc  xor     eax, eax
0x14000a2be  lea     rcx, [rbp+7F0h+Dir]; void *
0x14000a2c5  xor     edx, edx; Val
0x14000a2c7  mov     dword ptr [rsp+8F0h+Drive], eax
0x14000a2cb  mov     r8d, 208h; Size
0x14000a2d1  mov     [rsp+8F0h+var_88C], ax
0x14000a2d6  call    memset_0
0x14000a2db  lea     r9, [rsp+8F0h+dwSize]; lpdwSize
0x14000a2e0  xor     edx, edx; dwFlags
0x14000a2e2  lea     r8, [rbp+7F0h+ExeName]; lpExeName
0x14000a2e9  mov     rcx, r15; hProcess
0x14000a2ec  call    cs:__imp_QueryFullProcessImageNameW
0x14000a2f2  test    eax, eax
0x14000a2f4  jnz     short loc_14000A327
0x14000a2f6  mov     rax, cs:WPP_GLOBAL_Control
0x14000a2fd  cmp     rax, rdi
0x14000a300  jz      loc_14000A460
0x14000a306  test    byte ptr [rax+1Ch], 1
0x14000a30a  jz      loc_14000A460
0x14000a310  cmp     [rax+19h], bl
0x14000a313  jb      loc_14000A460
0x14000a319  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000a31e  lea     edx, [r13+0Ah]
0x14000a322  jmp     loc_14000A44A
0x14000a327  mov     [rsp+8F0h+ExtCount], r13; ExtCount
0x14000a32c  lea     r9, [rbp+7F0h+Dir]; Dir
0x14000a333  mov     [rsp+8F0h+Ext], r13; Ext
0x14000a338  lea     rdx, [rsp+8F0h+Drive]; Drive
0x14000a33d  mov     [rsp+8F0h+FilenameCount], r13; FilenameCount
0x14000a342  lea     rcx, [rbp+7F0h+ExeName]; FullPath
0x14000a349  mov     [rsp+8F0h+Filename], r13; Filename
0x14000a34e  mov     r8d, 3; DriveCount
0x14000a354  mov     [rsp+8F0h+DirCount], r12; DirCount
0x14000a359  call    cs:__imp__wsplitpath_s
0x14000a35f  test    eax, eax
0x14000a361  jnz     loc_14000A429
0x14000a367  lea     rax, aExe; "EXE"
0x14000a36e  mov     edx, 100h; BufferCount
0x14000a373  lea     rcx, aRdpinput; "rdpinput"
0x14000a37a  mov     [rsp+8F0h+Filename], rax; Ext
0x14000a37f  mov     [rsp+8F0h+DirCount], rcx; Filename
0x14000a384  lea     r9, [rbp+7F0h+Dir]; Dir
0x14000a38b  lea     rcx, [rsp+8F0h+Buffer]; Buffer
0x14000a390  lea     r8, [rsp+8F0h+Drive]; Drive
0x14000a395  call    cs:__imp__wmakepath_s
0x14000a39b  test    eax, eax
0x14000a39d  jnz     loc_14000A429
0x14000a3a3  mov     rax, cs:WPP_GLOBAL_Control
0x14000a3aa  cmp     rax, rdi
0x14000a3ad  jz      short loc_14000A3F0
0x14000a3af  test    byte ptr [rax+1Ch], 1
0x14000a3b3  jz      short loc_14000A3F0
0x14000a3b5  cmp     [rax+19h], bl
0x14000a3b8  jb      short loc_14000A3F0
0x14000a3ba  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000a3bf  lea     rcx, [rbp+7F0h+Parameters]
0x14000a3c6  mov     edx, 0Bh
0x14000a3cb  mov     [rsp+8F0h+Filename], rcx; __int64
0x14000a3d0  mov     r9d, eax
0x14000a3d3  lea     rcx, [rsp+8F0h+Buffer]
0x14000a3d8  mov     r8, rsi
0x14000a3db  mov     [rsp+8F0h+DirCount], rcx; __int64
0x14000a3e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a3e7  mov     rcx, [rcx+10h]; LoggerHandle
0x14000a3eb  call    WPP_SF_DSS
0x14000a3f0  mov     dword ptr [rsp+8F0h+Filename], 1; nShowCmd
0x14000a3f8  lea     r9, [rbp+7F0h+Parameters]; lpParameters
0x14000a3ff  lea     r8, [rsp+8F0h+Buffer]; lpFile
0x14000a404  mov     [rsp+8F0h+DirCount], r13; lpDirectory
0x14000a409  lea     rdx, Operation; "open"
0x14000a410  xor     ecx, ecx; hwnd
0x14000a412  call    cs:__imp_ShellExecuteW
0x14000a418  cmp     rax, 20h ; ' '
0x14000a41c  jle     short loc_14000A469
0x14000a41e  mov     r13d, 1
0x14000a424  jmp     loc_14000A607
0x14000a429  mov     rax, cs:WPP_GLOBAL_Control
0x14000a430  cmp     rax, rdi
0x14000a433  jz      short loc_14000A460
0x14000a435  test    byte ptr [rax+1Ch], 1
0x14000a439  jz      short loc_14000A460
0x14000a43b  cmp     [rax+19h], bl
0x14000a43e  jb      short loc_14000A460
0x14000a440  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000a445  mov     edx, 0Ch
0x14000a44a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a451  mov     r9d, eax
0x14000a454  mov     r8, rsi
0x14000a457  mov     rcx, [rcx+10h]
0x14000a45b  call    WPP_SF_d
0x14000a460  mov     rcx, r14; hObject
0x14000a463  call    cs:__imp_CloseHandle
0x14000a469  mov     rax, cs:WPP_GLOBAL_Control
0x14000a470  cmp     rax, rdi
0x14000a473  jz      short loc_14000A4EA
0x14000a475  test    byte ptr [rax+1Ch], 1
0x14000a479  jz      short loc_14000A4EA
0x14000a47b  cmp     [rax+19h], bl
0x14000a47e  jb      short loc_14000A4EA
0x14000a480  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000a485  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a48c  mov     edx, 0Dh
0x14000a491  mov     r9d, eax
0x14000a494  mov     r8, rsi
0x14000a497  mov     rcx, [rcx+10h]
0x14000a49b  call    WPP_SF_d
0x14000a4a0  jmp     short loc_14000A4EA
0x14000a4a2  mov     rax, cs:WPP_GLOBAL_Control
0x14000a4a9  lea     rdi, WPP_GLOBAL_Control
0x14000a4b0  cmp     rax, rdi
0x14000a4b3  jz      short loc_14000A4EA
0x14000a4b5  test    byte ptr [rax+1Ch], 1
0x14000a4b9  jz      short loc_14000A4EA
0x14000a4bb  mov     bl, 2
0x14000a4bd  cmp     [rax+19h], bl
0x14000a4c0  jb      short loc_14000A4EA
0x14000a4c2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000a4c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a4ce  lea     r8, WPP_58429c8c29ba3f29a0818ab0de17db3e_Traceguids
0x14000a4d5  mov     edx, 0Eh
0x14000a4da  mov     dword ptr [rsp+8F0h+DirCount], esi
0x14000a4de  mov     r9d, eax
0x14000a4e1  mov     rcx, [rcx+10h]
0x14000a4e5  call    WPP_SF_Dd
0x14000a4ea  mov     rcx, r14; hObject
0x14000a4ed  call    cs:__imp_CloseHandle
0x14000a4f3  jmp     loc_14000A607
0x14000a4f8  mov     rax, cs:WPP_GLOBAL_Control
0x14000a4ff  lea     rdi, WPP_GLOBAL_Control
0x14000a506  cmp     rax, rdi
0x14000a509  jz      loc_14000A607
0x14000a50f  test    byte ptr [rax+1Ch], 1
0x14000a513  lea     rsi, WPP_58429c8c29ba3f29a0818ab0de17db3e_Traceguids
0x14000a51a  mov     bl, 2
0x14000a51c  jz      short loc_14000A556
0x14000a51e  cmp     [rax+19h], bl
0x14000a521  jb      short loc_14000A556
0x14000a523  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000a528  lea     rcx, aRdpinput; "rdpinput"
0x14000a52f  mov     edx, 0Fh
0x14000a534  mov     [rsp+8F0h+DirCount], rcx
0x14000a539  mov     r9d, eax
0x14000a53c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a543  mov     r8, rsi
0x14000a546  mov     rcx, [rcx+10h]
0x14000a54a  call    WPP_SF_DS
0x14000a54f  mov     rax, cs:WPP_GLOBAL_Control
0x14000a556  cmp     rax, rdi
0x14000a559  jz      loc_14000A607
0x14000a55f  test    byte ptr [rax+1Ch], 1
0x14000a563  jz      short loc_14000A596
0x14000a565  cmp     [rax+19h], bl
0x14000a568  jb      short loc_14000A596
0x14000a56a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000a56f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a576  mov     edx, 10h
0x14000a57b  mov     r9d, eax
0x14000a57e  mov     dword ptr [rsp+8F0h+DirCount], r15d
0x14000a583  mov     r8, rsi
0x14000a586  mov     rcx, [rcx+10h]
0x14000a58a  call    WPP_SF_Dd
0x14000a58f  mov     rax, cs:WPP_GLOBAL_Control
0x14000a596  cmp     rax, rdi
0x14000a599  jz      short loc_14000A607
0x14000a59b  test    byte ptr [rax+1Ch], 1
0x14000a59f  jz      short loc_14000A5D2
0x14000a5a1  cmp     [rax+19h], bl
0x14000a5a4  jb      short loc_14000A5D2
0x14000a5a6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000a5ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a5b2  mov     edx, 11h
0x14000a5b7  mov     r9d, eax
0x14000a5ba  mov     dword ptr [rsp+8F0h+DirCount], r12d
0x14000a5bf  mov     r8, rsi
0x14000a5c2  mov     rcx, [rcx+10h]
0x14000a5c6  call    WPP_SF_Dd
0x14000a5cb  mov     rax, cs:WPP_GLOBAL_Control
0x14000a5d2  cmp     rax, rdi
0x14000a5d5  jz      short loc_14000A607
0x14000a5d7  test    byte ptr [rax+1Ch], 1
0x14000a5db  jz      short loc_14000A607
0x14000a5dd  cmp     [rax+19h], bl
0x14000a5e0  jb      short loc_14000A607
0x14000a5e2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000a5e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a5ee  mov     edx, 12h
0x14000a5f3  mov     r9d, eax
0x14000a5f6  mov     dword ptr [rsp+8F0h+DirCount], r14d
0x14000a5fb  mov     r8, rsi
0x14000a5fe  mov     rcx, [rcx+10h]
0x14000a602  call    WPP_SF_Dd
0x14000a607  mov     rax, [rsp+8F0h+var_898]
0x14000a60c  test    rax, rax
0x14000a60f  jz      short loc_14000A614
0x14000a611  mov     [rax], r13d
0x14000a614  mov     rcx, [rbp+7F0h+var_50]
0x14000a61b  xor     rcx, rsp; StackCookie
0x14000a61e  call    __security_check_cookie
0x14000a623  add     rsp, 8B8h
0x14000a62a  pop     r15
0x14000a62c  pop     r14
0x14000a62e  pop     r13
0x14000a630  pop     r12
0x14000a632  pop     rdi
0x14000a633  pop     rsi
0x14000a634  pop     rbx
0x14000a635  pop     rbp
0x14000a636  retn
```
