# SendNotification(PROF_NOTIFY_EVENT_FLAGS,PROF_NOTIFY_PARAM *,ulong,void *)

- ea: `0x1800128b0`
- end: `0x180012fa7`
- name: `?SendNotification@@YAJW4PROF_NOTIFY_EVENT_FLAGS@@PEAUPROF_NOTIFY_PARAM@@KPEAX@Z`
- size: `1783`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b540`
- `0x1800123cc`
- `0x1800127e4`
- `0x18002e0cc`
- `0x18002ed00`
- `0x180030624`

## callees

- `0x1800128b0`
- `0x180012fb0`
- `0x180012fec`
- `0x180013048`
- `0x180013570`
- `0x18002d2d8`
- `0x180032a04`
- `0x180034c98`
- `0x18003ab00`
- `0x18003f42c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012ab8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012dc0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012ab8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012dc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012ae2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012ba2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012ca8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012e02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012e52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012ed2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012ae2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012ba2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012ca8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012e02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012e52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012ed2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012aaa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012ad4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012b94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012c9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012db2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012df4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012e44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012ec4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012aaa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012ad4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012b94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012c9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012db2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012df4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012e44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012ec4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012c57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012c57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001291c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012a23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001291c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012a23`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800129b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012b45`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800129b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012b45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012a71`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012d00`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012a71`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012d00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012aed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012c30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012aed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012c30`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012d9b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012ddb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012d9b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012ddb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180012c45`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180012c45`

## string_xrefs

- `0x180012a67`: `CLSID`
- `0x180012cf6`: `CLSID`
- `0x180012e2a`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x180012e63`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x180012e9a`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x180012f51`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SendNotification(int a1, _QWORD *a2, int a3, void *a4)
{
  void *v4; // r12
  int v5; // r14d
  unsigned int v6; // eax
  unsigned int v7; // r8d
  const char *v8; // r9
  char *v9; // rbx
  const WCHAR *v10; // rdi
  const WCHAR *v11; // rax
  const WCHAR *v12; // r15
  HKEY v13; // r13
  LSTATUS ValueW; // eax
  signed int v15; // ebx
  LSTATUS v16; // eax
  HKEY v17; // rsi
  BYTE *v18; // r14
  LSTATUS v19; // eax
  DWORD v20; // ebx
  HANDLE ProcessHeap; // rax
  void *v22; // rsi
  HANDLE v23; // rax
  int v24; // eax
  HANDLE v25; // rax
  char *v26; // rdi
  unsigned __int64 v27; // rdx
  char *v28; // rcx
  int v29; // ebx
  _QWORD **v30; // rcx
  _QWORD *v31; // rax
  void *v32; // rbx
  HANDLE v33; // rax
  __int64 result; // rax
  LSTATUS v35; // eax
  __int64 v36; // rsi
  __int64 v37; // rax
  DWORD v38; // r12d
  HANDLE v39; // rax
  WCHAR *v40; // rax
  WCHAR *v41; // rbx
  DWORD v42; // eax
  DWORD v43; // esi
  HANDLE v44; // rax
  unsigned __int64 v45; // r9
  __int64 v46; // rdx
  HANDLE v47; // rax
  HANDLE v48; // rax
  const char *v49; // r9
  int phkResult; // [rsp+20h] [rbp-118h]
  unsigned int phkResulta; // [rsp+20h] [rbp-118h]
  int phkResultb; // [rsp+20h] [rbp-118h]
  int phkResultc; // [rsp+20h] [rbp-118h]
  char v54; // [rsp+40h] [rbp-F8h]
  DWORD Type; // [rsp+44h] [rbp-F4h] BYREF
  unsigned int pvData; // [rsp+48h] [rbp-F0h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-ECh] BYREF
  unsigned int v58; // [rsp+50h] [rbp-E8h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-E0h]
  __int64 v60; // [rsp+60h] [rbp-D8h]
  __int64 v61; // [rsp+68h] [rbp-D0h]
  HKEY hkey; // [rsp+70h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-C0h] BYREF
  void *v64[2]; // [rsp+80h] [rbp-B8h] BYREF
  __int64 v65; // [rsp+90h] [rbp-A8h]
  const WCHAR *v66; // [rsp+98h] [rbp-A0h]
  const wil::ResultException *v67; // [rsp+A0h] [rbp-98h] BYREF
  char v68[16]; // [rsp+B0h] [rbp-88h] BYREF
  LPVOID v69; // [rsp+C0h] [rbp-78h]
  char v70; // [rsp+C8h] [rbp-70h]
  _QWORD v71[3]; // [rsp+D0h] [rbp-68h] BYREF
  int v72; // [rsp+E8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v4 = a4;
  v5 = a1;
  ProfileTelemetry::WatchCurrentThread(v68);
  try
  {
    wil::CoInitializeEx();
    hkey = 0;
    v6 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\\\CurrentVersion\\ProfileNotification\\",
           0,
           0x20019u,
           &hkey);
    if ( v6 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x11E, v7, (const char *)v6, phkResulta);
    GetSubkeyNames(v64, hkey);
    v9 = (char *)v64[0];
    v10 = (const WCHAR *)v64[0];
    v11 = (const WCHAR *)v64[1];
    v66 = (const WCHAR *)v64[1];
    while ( v10 != v11 )
    {
      if ( *((_QWORD *)v10 + 3) <= 7u )
        v12 = v10;
      else
        v12 = *(const WCHAR **)v10;
      v13 = hkey;
      pvData = 0;
      Type = 4;
      ValueW = RegGetValueW(hkey, v12, L"Events", 0x10u, 0, &pvData, &Type);
      v15 = ValueW;
      if ( ValueW > 0 )
        v15 = (unsigned __int16)ValueW | 0x80070000;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE7,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
          (const char *)(unsigned int)v15,
          phkResultb);
        goto LABEL_73;
      }
      if ( (v5 & pvData) == 0 )
        goto LABEL_11;
      lpMem = 0;
      v60 = 0;
      v61 = 0;
      hKey = 0;
      v16 = RegOpenKeyExW(v13, v12, 0, 0x20019u, &hKey);
      v15 = v16;
      if ( v16 > 0 )
        v15 = (unsigned __int16)v16 | 0x80070000;
      if ( v15 < 0 )
      {
        v22 = lpMem;
        goto LABEL_26;
      }
      v17 = hKey;
      v18 = 0;
      Type = 0;
      cbData = 0;
      v19 = RegQueryValueExW(hKey, L"CLSID", 0, &Type, 0, &cbData);
      v15 = v19;
      if ( v19 > 0 )
        v15 = (unsigned __int16)v19 | 0x80070000;
      if ( v15 < 0 )
        goto LABEL_24;
      if ( Type - 1 > 1 || !cbData || (cbData & 1) != 0 )
        goto LABEL_69;
      v20 = cbData;
      ProcessHeap = GetProcessHeap();
      v18 = (BYTE *)HeapAlloc(ProcessHeap, 0, v20);
      if ( v18 )
      {
        v35 = RegQueryValueExW(v17, L"CLSID", 0, &Type, v18, &cbData);
        v15 = v35;
        if ( v35 > 0 )
          v15 = (unsigned __int16)v35 | 0x80070000;
        if ( v15 < 0 )
          goto LABEL_24;
        v36 = (cbData >> 1) - 1;
        if ( Type != 2 )
          goto LABEL_58;
        v38 = ExpandEnvironmentStringsW((LPCWSTR)v18, 0, 0);
        if ( !v38 )
          goto LABEL_58;
        v39 = GetProcessHeap();
        v40 = (WCHAR *)HeapAlloc(v39, 0, 2LL * v38);
        v41 = v40;
        if ( v40 )
        {
          v42 = ExpandEnvironmentStringsW((LPCWSTR)v18, v40, v38);
          v43 = v42;
          if ( !v42 || v42 > v38 )
          {
            v48 = GetProcessHeap();
            HeapFree(v48, 0, v41);
            v15 = -2147024774;
            goto LABEL_24;
          }
          v44 = GetProcessHeap();
          HeapFree(v44, 0, v18);
          v18 = (BYTE *)v41;
          v36 = v43 - 1;
          v15 = 0;
LABEL_58:
          if ( !*(_WORD *)&v18[2 * v36] )
          {
            v60 = 0;
            v61 = 0;
            if ( !v18 || (v37 = (unsigned int)(v36 + 1), (_DWORD)v36 == -1) )
            {
              v22 = lpMem;
            }
            else
            {
              v22 = v18;
              lpMem = v18;
              v61 = (unsigned int)v37;
              v60 = v37 - 1;
              *(_WORD *)&v18[2 * (unsigned int)v37 - 2] = 0;
            }
            v18 = 0;
            goto LABEL_25;
          }
LABEL_69:
          v15 = -2147024883;
          goto LABEL_24;
        }
      }
      v15 = -2147024882;
LABEL_24:
      v22 = lpMem;
LABEL_25:
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v18);
      RegCloseKey(hKey);
      v5 = a1;
      v4 = a4;
LABEL_26:
      if ( v15 < 0 )
      {
        v45 = (unsigned int)v15;
        v46 = 236;
LABEL_71:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v46,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
          (const char *)v45,
          phkResultc);
        if ( v22 )
        {
          v47 = GetProcessHeap();
          HeapFree(v47, 0, v22);
        }
LABEL_73:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x124,
          (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
          (const char *)(unsigned int)v15);
        v10 += 16;
        v9 = (char *)v64[0];
        v11 = v66;
      }
      else
      {
        v58 = 0;
        Type = 4;
        RegGetValueW(v13, v12, L"Flags", 0x10u, 0, &v58, &Type);
        v8 = (const char *)v58;
        if ( (a3 != -1 || (v58 & 4) == 0) && (v4 || (v58 & 2) == 0) )
        {
          v24 = NotifyComponent((const OLECHAR *)v22, v5, a2, v58, v4);
          v15 = v24;
          if ( v24 < 0 )
          {
            v45 = (unsigned int)v24;
            v46 = 245;
            goto LABEL_71;
          }
        }
        if ( v22 )
        {
          v25 = GetProcessHeap();
          HeapFree(v25, 0, v22);
        }
LABEL_11:
        v10 += 16;
        v9 = (char *)v64[0];
        v11 = v66;
      }
    }
    if ( v9 )
    {
      v26 = (char *)v64[1];
      if ( v9 != v64[1] )
      {
        do
        {
          v27 = *((_QWORD *)v9 + 3);
          if ( v27 > 7 )
            std::_Deallocate<16>(*(_QWORD **)v9, 2 * v27 + 2);
          *((_QWORD *)v9 + 2) = 0;
          *((_QWORD *)v9 + 3) = 7;
          *(_WORD *)v9 = 0;
          v9 += 32;
        }
        while ( v9 != v26 );
        v9 = (char *)v64[0];
      }
      if ( ((v65 - (_QWORD)v9) & 0xFFFFFFFFFFFFFFE0uLL) >= 0x1000 )
      {
        v28 = (char *)*((_QWORD *)v9 - 1);
        if ( (unsigned __int64)(v9 - v28 - 8) > 0x1F )
          __fastfail(5u);
      }
      else
      {
        v28 = v9;
      }
      operator delete(v28);
      *(_OWORD *)v64 = 0;
      v65 = 0;
    }
    if ( hkey )
      RegCloseKey(hkey);
    if ( v54 )
      CoUninitialize();
    v29 = v72;
    if ( v72 )
    {
      if ( v29 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
      v72 = 0;
      v30 = (_QWORD **)v71[0];
      while ( 1 )
      {
        v31 = *v30;
        if ( !*v30 )
          break;
        if ( v31 == v71 )
        {
          *v30 = (_QWORD *)v71[2];
          break;
        }
        v30 = (_QWORD **)(v31 + 2);
        v71[0] = v31 + 2;
      }
      v71[0] = 0;
    }
    if ( v70 )
    {
      v32 = v69;
      v33 = GetProcessHeap();
      HeapFree(v33, 0, v32);
    }
    result = 0;
  }
  catch ( const wil::ResultException *v67 )
  {
    v49 = (const char *)*((unsigned int *)v67 + 8);
    pvData = (unsigned int)v49;
    if ( (int)v49 < 0 )
    {
      if ( (_DWORD)v49 == -2147467263 )
        return 2147500033LL;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12D,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
        v49,
        phkResult);
      return pvData;
    }
    return pvData;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x132,
                           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x1800128b0  mov     qword ptr [rsp+arg_18], r9
0x1800128b5  mov     [rsp+arg_10], r8d
0x1800128ba  mov     [rsp+arg_8], rdx
0x1800128bf  mov     [rsp+arg_0], ecx
0x1800128c3  push    rbx
0x1800128c4  push    rsi
0x1800128c5  push    rdi
0x1800128c6  push    r12
0x1800128c8  push    r13
0x1800128ca  push    r14
0x1800128cc  push    r15
0x1800128ce  sub     rsp, 100h
0x1800128d5  mov     r12, r9
0x1800128d8  mov     r14d, ecx
0x1800128db  xor     esi, esi
0x1800128dd  lea     rcx, [rsp+138h+var_88]
0x1800128e5  call    ?WatchCurrentThread@ProfileTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; ProfileTelemetry::WatchCurrentThread(char const *)
0x1800128ea  nop
0x1800128eb  lea     rcx, [rsp+138h+var_F8]
0x1800128f0  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x1800128f5  nop
0x1800128f6  mov     [rsp+138h+hkey], rsi
0x1800128fb  lea     rax, [rsp+138h+hkey]
0x180012900  mov     [rsp+138h+phkResult], rax; unsigned int
0x180012905  mov     r9d, 20019h; samDesired
0x18001290b  xor     r8d, r8d; ulOptions
0x18001290e  lea     rdx, aSoftwareMicros_33; "Software\\Microsoft\\Windows NT\\\\Curr"...
0x180012915  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001291c  call    cs:__imp_RegOpenKeyExW
0x180012922  test    eax, eax
0x180012924  jnz     loc_180012D7D
0x18001292a  mov     rdx, [rsp+138h+hkey]
0x18001292f  lea     rcx, [rsp+138h+var_B8]
0x180012937  call    ?GetSubkeyNames@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@@Z; GetSubkeyNames(HKEY__ *)
0x18001293c  nop
0x18001293d  mov     rbx, [rsp+138h+var_B8]
0x180012945  mov     rdi, rbx
0x180012948  mov     rax, [rsp+138h+var_B8+8]
0x180012950  mov     [rsp+138h+var_A0], rax
0x180012958  nop     dword ptr [rax+rax+00000000h]
0x180012960  cmp     rdi, rax
0x180012963  jz      loc_180012BAD
0x180012969  cmp     qword ptr [rdi+18h], 7
0x18001296e  jbe     short loc_1800129E6
0x180012970  mov     r15, [rdi]
0x180012973  mov     r13, [rsp+138h+hkey]
0x180012978  mov     [rsp+138h+var_F0], esi
0x18001297c  mov     [rsp+138h+Type], 4
0x180012984  lea     rax, [rsp+138h+Type]
0x180012989  mov     [rsp+138h+pcbData], rax; pcbData
0x18001298e  lea     rax, [rsp+138h+var_F0]
0x180012993  mov     [rsp+138h+pvData], rax; pvData
0x180012998  mov     [rsp+138h+phkResult], rsi; int
0x18001299d  mov     r9d, 10h; dwFlags
0x1800129a3  lea     r8, aEvents; "Events"
0x1800129aa  mov     rdx, r15; lpSubKey
0x1800129ad  mov     rcx, r13; hkey
0x1800129b0  call    cs:__imp_RegGetValueW
0x1800129b6  mov     ebx, eax
0x1800129b8  test    eax, eax
0x1800129ba  jg      short loc_1800129EB
0x1800129bc  test    ebx, ebx
0x1800129be  js      loc_180012E8F
0x1800129c4  test    [rsp+138h+var_F0], r14d
0x1800129c9  jnz     short loc_1800129F6
0x1800129cb  add     rdi, 20h ; ' '
0x1800129cf  mov     rbx, [rsp+138h+var_B8]
0x1800129d7  mov     rax, [rsp+138h+var_A0]
0x1800129df  xor     esi, esi
0x1800129e1  jmp     loc_180012960
0x1800129e6  mov     r15, rdi
0x1800129e9  jmp     short loc_180012973
0x1800129eb  movzx   ebx, ax
0x1800129ee  or      ebx, 80070000h
0x1800129f4  jmp     short loc_1800129BC
0x1800129f6  mov     [rsp+138h+lpMem], rsi
0x1800129fb  mov     [rsp+138h+var_D8], rsi
0x180012a00  mov     [rsp+138h+var_D0], rsi
0x180012a05  mov     [rsp+138h+hKey], rsi
0x180012a0a  lea     rax, [rsp+138h+hKey]
0x180012a0f  mov     [rsp+138h+phkResult], rax; phkResult
0x180012a14  mov     r9d, 20019h; samDesired
0x180012a1a  xor     r8d, r8d; ulOptions
0x180012a1d  mov     rdx, r15; lpSubKey
0x180012a20  mov     rcx, r13; hKey
0x180012a23  call    cs:__imp_RegOpenKeyExW
0x180012a29  mov     ebx, eax
0x180012a2b  test    eax, eax
0x180012a2d  jg      loc_180012CC3
0x180012a33  test    ebx, ebx
0x180012a35  js      loc_180012EBA
0x180012a3b  mov     rsi, [rsp+138h+hKey]
0x180012a40  xor     r12d, r12d
0x180012a43  mov     r14d, r12d
0x180012a46  mov     [rsp+138h+Type], r12d
0x180012a4b  mov     [rsp+138h+cbData], r12d
0x180012a50  lea     rax, [rsp+138h+cbData]
0x180012a55  mov     [rsp+138h+pvData], rax; lpcbData
0x180012a5a  mov     [rsp+138h+phkResult], r12; lpData
0x180012a5f  lea     r9, [rsp+138h+Type]; lpType
0x180012a64  xor     r8d, r8d; lpReserved
0x180012a67  lea     rdx, aClsid; "CLSID"
0x180012a6e  mov     rcx, rsi; hKey
0x180012a71  call    cs:__imp_RegQueryValueExW
0x180012a77  mov     ebx, eax
0x180012a79  test    eax, eax
0x180012a7b  jg      loc_180012CD1
0x180012a81  test    ebx, ebx
0x180012a83  js      short loc_180012ACF
0x180012a85  mov     eax, [rsp+138h+Type]
0x180012a89  dec     eax
0x180012a8b  cmp     eax, 1
0x180012a8e  ja      loc_180012E18
0x180012a94  mov     eax, [rsp+138h+cbData]
0x180012a98  test    eax, eax
0x180012a9a  jz      loc_180012E18
0x180012aa0  test    al, 1
0x180012aa2  jnz     loc_180012E18
0x180012aa8  mov     ebx, eax
0x180012aaa  call    cs:__imp_GetProcessHeap
0x180012ab0  mov     rcx, rax; hHeap
0x180012ab3  mov     r8d, ebx; dwBytes
0x180012ab6  xor     edx, edx; dwFlags
0x180012ab8  call    cs:__imp_HeapAlloc
0x180012abe  mov     r14, rax
0x180012ac1  test    rax, rax
0x180012ac4  jnz     loc_180012CDF
0x180012aca  mov     ebx, 8007000Eh
0x180012acf  mov     rsi, [rsp+138h+lpMem]
0x180012ad4  call    cs:__imp_GetProcessHeap
0x180012ada  mov     rcx, rax; hHeap
0x180012add  mov     r8, r14; lpMem
0x180012ae0  xor     edx, edx; dwFlags
0x180012ae2  call    cs:__imp_HeapFree
0x180012ae8  mov     rcx, [rsp+138h+hKey]; hKey
0x180012aed  call    cs:__imp_RegCloseKey
0x180012af3  mov     r14d, [rsp+138h+arg_0]
0x180012afb  mov     r12, qword ptr [rsp+138h+arg_18]
0x180012b03  test    ebx, ebx
0x180012b05  js      loc_180012EAD
0x180012b0b  xor     ecx, ecx
0x180012b0d  mov     [rsp+138h+var_E8], ecx
0x180012b11  mov     [rsp+138h+Type], 4
0x180012b19  lea     rax, [rsp+138h+Type]
0x180012b1e  mov     [rsp+138h+pcbData], rax; pcbData
0x180012b23  lea     rax, [rsp+138h+var_E8]
0x180012b28  mov     [rsp+138h+pvData], rax; pvData
0x180012b2d  mov     [rsp+138h+phkResult], rcx; pdwType
0x180012b32  mov     r9d, 10h; dwFlags
0x180012b38  lea     r8, aFlags; "Flags"
0x180012b3f  mov     rdx, r15; lpSubKey
0x180012b42  mov     rcx, r13; hkey
0x180012b45  call    cs:__imp_RegGetValueW
0x180012b4b  mov     r9d, [rsp+138h+var_E8]
0x180012b50  cmp     [rsp+138h+arg_10], 0FFFFFFFFh
0x180012b58  jnz     short loc_180012B60
0x180012b5a  test    r9b, 4
0x180012b5e  jnz     short loc_180012B8B
0x180012b60  test    r12, r12
0x180012b63  jz      loc_180012EF4
0x180012b69  mov     [rsp+138h+phkResult], r12; int
0x180012b6e  mov     r8, [rsp+138h+arg_8]
0x180012b76  mov     edx, r14d
0x180012b79  mov     rcx, rsi
0x180012b7c  call    ?NotifyComponent@@YAJPEBGW4PROF_NOTIFY_EVENT_FLAGS@@PEAUPROF_NOTIFY_PARAM@@W4PROF_NOTIFY_FLAGS@@PEAX@Z; NotifyComponent(ushort const *,PROF_NOTIFY_EVENT_FLAGS,PROF_NOTIFY_PARAM *,PROF_NOTIFY_FLAGS,void *)
0x180012b81  mov     ebx, eax
0x180012b83  test    eax, eax
0x180012b85  js      loc_180012E22
0x180012b8b  test    rsi, rsi
0x180012b8e  jz      loc_1800129CB
0x180012b94  call    cs:__imp_GetProcessHeap
0x180012b9a  mov     rcx, rax; hHeap
0x180012b9d  mov     r8, rsi; lpMem
0x180012ba0  xor     edx, edx; dwFlags
0x180012ba2  call    cs:__imp_HeapFree
0x180012ba8  jmp     loc_1800129CB
0x180012bad  test    rbx, rbx
0x180012bb0  jz      short loc_180012C26
0x180012bb2  mov     rdi, [rsp+138h+var_B8+8]
0x180012bba  cmp     rbx, rdi
0x180012bbd  jz      short loc_180012BEE
0x180012bbf  nop
0x180012bc0  mov     rdx, [rbx+18h]
0x180012bc4  cmp     rdx, 7
0x180012bc8  ja      loc_180012F03
0x180012bce  mov     [rbx+10h], rsi
0x180012bd2  mov     qword ptr [rbx+18h], 7
0x180012bda  mov     [rbx], si
0x180012bdd  add     rbx, 20h ; ' '
0x180012be1  cmp     rbx, rdi
0x180012be4  jnz     short loc_180012BC0
0x180012be6  mov     rbx, [rsp+138h+var_B8]
0x180012bee  mov     rdx, [rsp+138h+var_A8]
0x180012bf6  sub     rdx, rbx
0x180012bf9  and     rdx, 0FFFFFFFFFFFFFFE0h; unsigned __int64
0x180012bfd  cmp     rdx, 1000h
0x180012c04  jnb     loc_180012F18
0x180012c0a  mov     rcx, rbx; void *
0x180012c0d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012c12  xorps   xmm0, xmm0
0x180012c15  movdqu  xmmword ptr [rsp+138h+var_B8], xmm0
0x180012c1e  mov     [rsp+138h+var_A8], rsi
0x180012c26  mov     rcx, [rsp+138h+hkey]; hKey
0x180012c2b  test    rcx, rcx
0x180012c2e  jz      short loc_180012C37
0x180012c30  call    cs:__imp_RegCloseKey
0x180012c36  nop
0x180012c37  movzx   eax, [rsp+138h+var_F8]
0x180012c3c  mov     [rsp+138h+var_F8], 0
0x180012c41  test    al, al
0x180012c43  jz      short loc_180012C4C
0x180012c45  call    cs:__imp_CoUninitialize
0x180012c4b  nop
0x180012c4c  mov     ebx, [rsp+138h+var_50]
0x180012c53  test    ebx, ebx
0x180012c55  jz      short loc_180012C88
0x180012c57  call    cs:__imp_GetCurrentThreadId
0x180012c5d  cmp     ebx, eax
0x180012c5f  jnz     loc_180012F39
0x180012c65  mov     [rsp+138h+var_50], esi
0x180012c6c  mov     rcx, [rsp+138h+var_68]
0x180012c74  mov     rax, [rcx]
0x180012c77  test    rax, rax
0x180012c7a  jnz     loc_180012F62
0x180012c80  mov     [rsp+138h+var_68], rsi
0x180012c88  cmp     [rsp+138h+var_70], 0
0x180012c90  jz      short loc_180012CAE
0x180012c92  mov     rbx, [rsp+138h+var_78]
0x180012c9a  call    cs:__imp_GetProcessHeap
0x180012ca0  mov     r8, rbx; lpMem
0x180012ca3  xor     edx, edx; dwFlags
0x180012ca5  mov     rcx, rax; hHeap
0x180012ca8  call    cs:__imp_HeapFree
0x180012cae  xor     eax, eax
0x180012cb0  add     rsp, 100h
0x180012cb7  pop     r15
0x180012cb9  pop     r14
0x180012cbb  pop     r13
0x180012cbd  pop     r12
0x180012cbf  pop     rdi
0x180012cc0  pop     rsi
0x180012cc1  pop     rbx
0x180012cc2  retn
0x180012cc3  movzx   ebx, ax
0x180012cc6  or      ebx, 80070000h
0x180012ccc  jmp     loc_180012A33
0x180012cd1  movzx   ebx, ax
0x180012cd4  or      ebx, 80070000h
0x180012cda  jmp     loc_180012A81
0x180012cdf  lea     rax, [rsp+138h+cbData]
0x180012ce4  mov     [rsp+138h+pvData], rax; lpcbData
0x180012ce9  mov     [rsp+138h+phkResult], r14; lpData
0x180012cee  lea     r9, [rsp+138h+Type]; lpType
0x180012cf3  xor     r8d, r8d; lpReserved
0x180012cf6  lea     rdx, aClsid; "CLSID"
0x180012cfd  mov     rcx, rsi; hKey
0x180012d00  call    cs:__imp_RegQueryValueExW
0x180012d06  mov     ebx, eax
0x180012d08  test    eax, eax
0x180012d0a  jg      short loc_180012D72
0x180012d0c  test    ebx, ebx
0x180012d0e  js      loc_180012ACF
0x180012d14  mov     esi, [rsp+138h+cbData]
0x180012d18  shr     esi, 1
0x180012d1a  dec     esi
0x180012d1c  cmp     [rsp+138h+Type], 2
0x180012d21  jz      short loc_180012D93
0x180012d23  cmp     word ptr [r14+rsi*2], 0
0x180012d29  jnz     loc_180012E18
0x180012d2f  mov     [rsp+138h+var_D8], r12
0x180012d34  mov     [rsp+138h+var_D0], r12
0x180012d39  test    r14, r14
0x180012d3c  jz      loc_180012EEA
0x180012d42  lea     eax, [rsi+1]
0x180012d45  mov     ecx, eax
0x180012d47  test    eax, eax
0x180012d49  jz      loc_180012EEA
0x180012d4f  mov     rsi, r14
0x180012d52  mov     [rsp+138h+lpMem], r14
0x180012d57  mov     [rsp+138h+var_D0], rcx
0x180012d5c  dec     rax
0x180012d5f  mov     [rsp+138h+var_D8], rax
0x180012d64  mov     [r14+rcx*2-2], r12w
0x180012d6a  mov     r14, r12
0x180012d6d  jmp     loc_180012AD4
0x180012d72  movzx   ebx, ax
0x180012d75  or      ebx, 80070000h
0x180012d7b  jmp     short loc_180012D0C
0x180012d7d  mov     rcx, [rsp+138h]; this
0x180012d85  mov     r9d, eax; char *
0x180012d88  mov     edx, 11Eh; void *
0x180012d8d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180012d93  xor     r8d, r8d; nSize
0x180012d96  xor     edx, edx; lpDst
0x180012d98  mov     rcx, r14; lpSrc
0x180012d9b  call    cs:__imp_ExpandEnvironmentStringsW
0x180012da1  mov     r12d, eax
0x180012da4  test    eax, eax
0x180012da6  jz      loc_180012EE2
0x180012dac  mov     ebx, r12d
  ... truncated ...
```
