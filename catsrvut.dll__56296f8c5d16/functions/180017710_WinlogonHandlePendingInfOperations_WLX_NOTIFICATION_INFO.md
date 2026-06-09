# WinlogonHandlePendingInfOperations(_WLX_NOTIFICATION_INFO *)

- ea: `0x180017710`
- end: `0x180017abf`
- name: `?WinlogonHandlePendingInfOperations@@YAXPEAU_WLX_NOTIFICATION_INFO@@@Z`
- size: `943`
- prototype: `void __fastcall(struct _WLX_NOTIFICATION_INFO *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000e3b8`
- `0x180014ec8`
- `0x180014f58`
- `0x180016ffc`
- `0x180017688`
- `0x180017710`
- `0x18005583a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017a90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017a9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017aa4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017a90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017a9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017aa4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800177ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017837`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800178e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800177ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017837`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800178e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a46`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001777b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800177c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180017858`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001777b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800177c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180017858`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017a76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017a86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017a76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017a86`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180017a3c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180017a3c`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x1800178ac`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x180017998`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x1800178ac`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x180017998`

## string_xrefs

- `0x180017802`: `rundll32.exe`
- `0x180017889`: `setup\comsetup.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
void __fastcall WinlogonHandlePendingInfOperations(struct _WLX_NOTIFICATION_INFO *a1)
{
  WCHAR *v1; // rsi
  WCHAR *v2; // rdi
  UINT SystemDirectoryW; // eax
  UINT v4; // r15d
  __int64 v5; // rax
  __int64 v6; // r13
  unsigned __int64 v7; // r12
  WCHAR *v8; // rax
  WCHAR *v9; // r14
  UINT v10; // eax
  WCHAR *v11; // rax
  UINT v12; // eax
  DWORD ShortPathNameW; // eax
  DWORD v14; // r15d
  __int64 v15; // rdx
  unsigned __int64 v16; // r12
  DWORD v17; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-C0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-A8h] BYREF
  LPWSTR lpszShortPath; // [rsp+128h] [rbp+10h] BYREF
  unsigned __int64 cchBuffer; // [rsp+130h] [rbp+18h] BYREF
  WCHAR *v22; // [rsp+138h] [rbp+20h]

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v1 = 0;
  v22 = 0;
  v2 = 0;
  lpszShortPath = 0;
  if ( !(unsigned int)IsUpgradingPDC() )
  {
    if ( (unsigned int)WaitForNetworkAvailability() )
    {
      SystemDirectoryW = GetSystemDirectoryW(0, 0);
      v4 = SystemDirectoryW;
      if ( SystemDirectoryW )
      {
        v5 = SystemDirectoryW + 1;
        v6 = (unsigned int)v5;
        v7 = v5 + 13;
        v8 = (WCHAR *)CoTaskMemAlloc(saturated_mul(v5 + 13, 2u));
        v9 = v8;
        if ( v8 )
        {
          v10 = GetSystemDirectoryW(v8, v4);
          if ( v10 && v10 <= v4 )
          {
            if ( v9[v10 - 1] != 92 )
            {
              v9[v10] = 92;
              v9[v10 + 1] = 0;
            }
            if ( StringCchCatW(v9, v7, L"rundll32.exe") >= 0 )
            {
              v11 = (WCHAR *)CoTaskMemAlloc(saturated_mul(v6 + 19, 2u));
              v1 = v11;
              v22 = v11;
              if ( v11 )
              {
                v12 = GetSystemDirectoryW(v11, v4);
                if ( v12 )
                {
                  if ( v12 <= v4 )
                  {
                    if ( v1[v12 - 1] != 92 )
                    {
                      v1[v12] = 92;
                      v1[v12 + 1] = 0;
                    }
                    if ( StringCchCatW(v1, v6 + 19, L"setup\\comsetup.dll") >= 0 )
                    {
                      ShortPathNameW = GetShortPathNameW(v1, 0, 0);
                      v14 = ShortPathNameW;
                      if ( ShortPathNameW )
                      {
                        v15 = -1;
                        do
                          ++v15;
                        while ( v9[v15] );
                        v16 = v15 + ShortPathNameW + 29LL;
                        cchBuffer = v16;
                        v2 = (WCHAR *)CoTaskMemAlloc(saturated_mul(v16, 2u));
                        lpszShortPath = v2;
                        if ( v2 )
                        {
                          if ( (int)StringCchCopyExW(v2, v16, v9, &lpszShortPath, &cchBuffer, 0) >= 0 )
                          {
                            if ( (int)StringCchCatExW(lpszShortPath, cchBuffer, L" ", &lpszShortPath, &cchBuffer, 0) >= 0 )
                            {
                              v2 = lpszShortPath;
                              v17 = GetShortPathNameW(v1, lpszShortPath, cchBuffer);
                              if ( v17 )
                              {
                                if ( v17 <= v14 && StringCchCatW(v2, cchBuffer, L",HandlePendingInfOperations") >= 0 )
                                {
                                  StartupInfo.cb = 104;
                                  memset(&StartupInfo.lpReserved, 0, 24);
                                  StartupInfo.dwFlags = 129;
                                  *(_DWORD *)&StartupInfo.wShowWindow = 6;
                                  StartupInfo.lpReserved2 = 0;
                                  if ( !CreateProcessW(v9, v2, 0, 0, 0, 8u, 0, 0, &StartupInfo, &ProcessInformation) )
                                    GetLastError();
                                }
                              }
                            }
                            else
                            {
                              v2 = lpszShortPath;
                            }
                          }
                          else
                          {
                            v2 = lpszShortPath;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          if ( ProcessInformation.hProcess )
            CloseHandle(ProcessInformation.hProcess);
          if ( ProcessInformation.hThread )
            CloseHandle(ProcessInformation.hThread);
          CoTaskMemFree(v1);
          CoTaskMemFree(v9);
          CoTaskMemFree(v2);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180017710  push    rbx
0x180017712  push    rsi
0x180017713  push    rdi
0x180017714  push    r12
0x180017716  push    r13
0x180017718  push    r14
0x18001771a  push    r15
0x18001771c  sub     rsp, 0E0h
0x180017723  xor     edx, edx; Val
0x180017725  lea     r8d, [rdx+68h]; Size
0x180017729  lea     rcx, [rsp+118h+StartupInfo]; void *
0x18001772e  call    memset_0
0x180017733  xorps   xmm0, xmm0
0x180017736  xor     eax, eax
0x180017738  movups  xmmword ptr [rsp+118h+ProcessInformation.hProcess], xmm0
0x18001773d  mov     qword ptr [rsp+118h+ProcessInformation.dwProcessId], rax
0x180017742  xor     ebx, ebx
0x180017744  mov     esi, ebx
0x180017746  mov     [rsp+118h+arg_18], rbx
0x18001774e  mov     [rsp+118h+var_C8], rbx
0x180017753  mov     edi, ebx
0x180017755  mov     [rsp+118h+lpszShortPath], rbx
0x18001775d  call    ?IsUpgradingPDC@@YAHXZ; IsUpgradingPDC(void)
0x180017762  test    eax, eax
0x180017764  jnz     loc_180017AAB
0x18001776a  call    ?WaitForNetworkAvailability@@YAHXZ; WaitForNetworkAvailability(void)
0x18001776f  test    eax, eax
0x180017771  jz      loc_180017AAB
0x180017777  xor     edx, edx; uSize
0x180017779  xor     ecx, ecx; lpBuffer
0x18001777b  call    cs:__imp_GetSystemDirectoryW
0x180017781  mov     r15d, eax
0x180017784  test    eax, eax
0x180017786  jz      loc_180017AAB
0x18001778c  inc     eax
0x18001778e  mov     r13d, eax
0x180017791  lea     r12, [rax+0Dh]
0x180017795  mov     eax, 2
0x18001779a  mul     r12
0x18001779d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800177a4  cmovb   rax, rcx
0x1800177a8  mov     rcx, rax; cb
0x1800177ab  call    cs:__imp_CoTaskMemAlloc
0x1800177b1  mov     r14, rax
0x1800177b4  mov     [rsp+118h+var_C8], rax
0x1800177b9  test    rax, rax
0x1800177bc  jz      loc_180017AAB
0x1800177c2  mov     edx, r15d; uSize
0x1800177c5  mov     rcx, r14; lpBuffer
0x1800177c8  call    cs:__imp_GetSystemDirectoryW
0x1800177ce  mov     r9d, eax
0x1800177d1  cmp     r9d, 1
0x1800177d5  jb      loc_180017A55
0x1800177db  cmp     r9d, r15d
0x1800177de  ja      loc_180017A55
0x1800177e4  lea     r8d, [r9-1]
0x1800177e8  mov     ecx, 5Ch ; '\'
0x1800177ed  cmp     [r14+r8*2], cx
0x1800177f2  jz      short loc_180017802
0x1800177f4  mov     [r14+r9*2], cx
0x1800177f9  lea     eax, [r9+1]
0x1800177fd  mov     [r14+rax*2], bx
0x180017802  lea     r8, aRundll32Exe_0; "rundll32.exe"
0x180017809  mov     rdx, r12; unsigned __int64
0x18001780c  mov     rcx, r14; unsigned __int16 *
0x18001780f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017814  test    eax, eax
0x180017816  jns     short loc_18001781D
0x180017818  jmp     loc_180017A6C
0x18001781d  lea     r12, [r13+13h]
0x180017821  mov     eax, 2
0x180017826  mul     r12
0x180017829  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180017830  cmovb   rax, r13
0x180017834  mov     rcx, rax; cb
0x180017837  call    cs:__imp_CoTaskMemAlloc
0x18001783d  mov     rsi, rax
0x180017840  mov     [rsp+118h+arg_18], rax
0x180017848  test    rax, rax
0x18001784b  jnz     short loc_180017852
0x18001784d  jmp     loc_180017A6C
0x180017852  mov     edx, r15d; uSize
0x180017855  mov     rcx, rsi; lpBuffer
0x180017858  call    cs:__imp_GetSystemDirectoryW
0x18001785e  test    eax, eax
0x180017860  jz      loc_180017A53
0x180017866  cmp     eax, r15d
0x180017869  ja      loc_180017A53
0x18001786f  lea     ecx, [rax-1]
0x180017872  mov     edx, 5Ch ; '\'
0x180017877  cmp     [rsi+rcx*2], dx
0x18001787b  jz      short loc_180017889
0x18001787d  mov     ecx, eax
0x18001787f  mov     [rsi+rcx*2], dx
0x180017883  inc     eax
0x180017885  mov     [rsi+rax*2], bx
0x180017889  lea     r8, aSetupComsetupD; "setup\\comsetup.dll"
0x180017890  mov     rdx, r12; unsigned __int64
0x180017893  mov     rcx, rsi; unsigned __int16 *
0x180017896  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001789b  test    eax, eax
0x18001789d  jns     short loc_1800178A4
0x18001789f  jmp     loc_180017A6C
0x1800178a4  xor     r8d, r8d; cchBuffer
0x1800178a7  xor     edx, edx; lpszShortPath
0x1800178a9  mov     rcx, rsi; lpszLongPath
0x1800178ac  call    cs:__imp_GetShortPathNameW
0x1800178b2  mov     r15d, eax
0x1800178b5  test    eax, eax
0x1800178b7  jnz     short loc_1800178BE
0x1800178b9  jmp     loc_180017A6C
0x1800178be  mov     rdx, r13
0x1800178c1  inc     rdx
0x1800178c4  cmp     [r14+rdx*2], bx
0x1800178c9  jnz     short loc_1800178C1
0x1800178cb  lea     r12, [r15+1Dh]
0x1800178cf  add     r12, rdx
0x1800178d2  mov     [rsp+118h+cchBuffer], r12
0x1800178da  mov     eax, 2
0x1800178df  mul     r12
0x1800178e2  cmovb   rax, r13
0x1800178e6  mov     rcx, rax; cb
0x1800178e9  call    cs:__imp_CoTaskMemAlloc
0x1800178ef  mov     rdi, rax
0x1800178f2  mov     [rsp+118h+lpszShortPath], rax
0x1800178fa  test    rax, rax
0x1800178fd  jnz     short loc_180017904
0x1800178ff  jmp     loc_180017A6C
0x180017904  mov     [rsp+118h+dwCreationFlags], ebx; unsigned int
0x180017908  lea     rax, [rsp+118h+cchBuffer]
0x180017910  mov     qword ptr [rsp+118h+bInheritHandles], rax; unsigned __int64 *
0x180017915  lea     r9, [rsp+118h+lpszShortPath]; unsigned __int16 **
0x18001791d  mov     r8, r14; unsigned __int16 *
0x180017920  mov     rdx, r12; unsigned __int64
0x180017923  mov     rcx, rdi; pszDest
0x180017926  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18001792b  test    eax, eax
0x18001792d  jns     short loc_18001793C
0x18001792f  mov     rdi, [rsp+118h+lpszShortPath]
0x180017937  jmp     loc_180017A6C
0x18001793c  mov     [rsp+118h+dwCreationFlags], ebx; unsigned int
0x180017940  lea     rax, [rsp+118h+cchBuffer]
0x180017948  mov     qword ptr [rsp+118h+bInheritHandles], rax; unsigned __int64 *
0x18001794d  lea     r9, [rsp+118h+lpszShortPath]; unsigned __int16 **
0x180017955  lea     r8, asc_180062608; " "
0x18001795c  mov     rdx, [rsp+118h+cchBuffer]; unsigned __int64
0x180017964  mov     rcx, [rsp+118h+lpszShortPath]; psz
0x18001796c  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180017971  test    eax, eax
0x180017973  jns     short loc_180017982
0x180017975  mov     rdi, [rsp+118h+lpszShortPath]
0x18001797d  jmp     loc_180017A6C
0x180017982  mov     r8d, dword ptr [rsp+118h+cchBuffer]; cchBuffer
0x18001798a  mov     rdi, [rsp+118h+lpszShortPath]
0x180017992  mov     rdx, rdi; lpszShortPath
0x180017995  mov     rcx, rsi; lpszLongPath
0x180017998  call    cs:__imp_GetShortPathNameW
0x18001799e  test    eax, eax
0x1800179a0  jz      loc_180017A51
0x1800179a6  cmp     eax, r15d
0x1800179a9  ja      loc_180017A51
0x1800179af  lea     r8, aHandlependingi; ",HandlePendingInfOperations"
0x1800179b6  mov     rdx, [rsp+118h+cchBuffer]; unsigned __int64
0x1800179be  mov     rcx, rdi; unsigned __int16 *
0x1800179c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800179c6  test    eax, eax
0x1800179c8  jns     short loc_1800179CF
0x1800179ca  jmp     loc_180017A6C
0x1800179cf  mov     [rsp+118h+StartupInfo.cb], 68h ; 'h'
0x1800179d7  mov     [rsp+118h+StartupInfo.lpReserved], rbx
0x1800179dc  xorps   xmm0, xmm0
0x1800179df  movdqa  xmmword ptr [rsp+118h+StartupInfo.lpDesktop], xmm0
0x1800179e8  mov     [rsp+118h+StartupInfo.dwFlags], 81h
0x1800179f3  mov     dword ptr [rsp+118h+StartupInfo.wShowWindow], 6
0x1800179fe  mov     [rsp+118h+StartupInfo.lpReserved2], rbx
0x180017a06  lea     rax, [rsp+118h+ProcessInformation]
0x180017a0b  mov     [rsp+118h+lpProcessInformation], rax; lpProcessInformation
0x180017a10  lea     rax, [rsp+118h+StartupInfo]
0x180017a15  mov     [rsp+118h+lpStartupInfo], rax; lpStartupInfo
0x180017a1a  mov     [rsp+118h+lpCurrentDirectory], rbx; lpCurrentDirectory
0x180017a1f  mov     [rsp+118h+lpEnvironment], rbx; lpEnvironment
0x180017a24  mov     [rsp+118h+dwCreationFlags], 8; dwCreationFlags
0x180017a2c  mov     [rsp+118h+bInheritHandles], ebx; bInheritHandles
0x180017a30  xor     r9d, r9d; lpThreadAttributes
0x180017a33  xor     r8d, r8d; lpProcessAttributes
0x180017a36  mov     rdx, rdi; lpCommandLine
0x180017a39  mov     rcx, r14; lpApplicationName
0x180017a3c  call    cs:__imp_CreateProcessW
0x180017a42  test    eax, eax
0x180017a44  jnz     short loc_180017A4F
0x180017a46  call    cs:__imp_GetLastError
0x180017a4c  nop
0x180017a4d  jmp     short loc_180017A6C
0x180017a4f  jmp     short loc_180017A6C
0x180017a51  jmp     short loc_180017A6C
0x180017a53  jmp     short loc_180017A6C
0x180017a55  jmp     short loc_180017A6C
0x180017a57  mov     rsi, [rsp+118h+arg_18]
0x180017a5f  mov     r14, [rsp+118h+var_C8]
0x180017a64  mov     rdi, [rsp+118h+lpszShortPath]
0x180017a6c  mov     rcx, [rsp+118h+ProcessInformation.hProcess]; hObject
0x180017a71  test    rcx, rcx
0x180017a74  jz      short loc_180017A7C
0x180017a76  call    cs:__imp_CloseHandle
0x180017a7c  mov     rcx, [rsp+118h+ProcessInformation.hThread]; hObject
0x180017a81  test    rcx, rcx
0x180017a84  jz      short loc_180017A8D
0x180017a86  call    cs:__imp_CloseHandle
0x180017a8c  nop
0x180017a8d  mov     rcx, rsi; pv
0x180017a90  call    cs:__imp_CoTaskMemFree
0x180017a96  nop
0x180017a97  mov     rcx, r14; pv
0x180017a9a  call    cs:__imp_CoTaskMemFree
0x180017aa0  nop
0x180017aa1  mov     rcx, rdi; pv
0x180017aa4  call    cs:__imp_CoTaskMemFree
0x180017aaa  nop
0x180017aab  add     rsp, 0E0h
0x180017ab2  pop     r15
0x180017ab4  pop     r14
0x180017ab6  pop     r13
0x180017ab8  pop     r12
0x180017aba  pop     rdi
0x180017abb  pop     rsi
0x180017abc  pop     rbx
0x180017abd  retn
```
