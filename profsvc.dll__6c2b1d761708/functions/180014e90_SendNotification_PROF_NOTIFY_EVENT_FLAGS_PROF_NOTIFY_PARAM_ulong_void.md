# SendNotification(PROF_NOTIFY_EVENT_FLAGS,PROF_NOTIFY_PARAM *,ulong,void *)

- ea: `0x180014e90`
- end: `0x180015645`
- name: `?SendNotification@@YAJW4PROF_NOTIFY_EVENT_FLAGS@@PEAUPROF_NOTIFY_PARAM@@KPEAX@Z`
- size: `1973`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006dbc`
- `0x180008fa0`
- `0x180014dc4`
- `0x18002eae0`
- `0x18002fa8c`
- `0x180030050`

## callees

- `0x18000e1a0`
- `0x180014e90`
- `0x18001564c`
- `0x180015690`
- `0x1800156ec`
- `0x180015c20`
- `0x180030ad0`
- `0x180033650`
- `0x180035464`
- `0x18003c040`
- `0x180040bcc`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800150b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015412`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800150b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015412`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800150e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800151be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800152e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015466`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800154c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001556a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800150e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800151be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800152e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015466`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800154c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001556a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001509c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800150d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800151aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800152cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800153fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015452`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800154ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015556`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001509c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800150d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800151aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800152cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800153fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015452`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800154ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015556`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015284`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015284`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014efc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015009`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014efc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015009`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014f90`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015155`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014f90`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015155`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001505d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015340`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001505d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015340`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800150f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015251`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800150f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015251`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800153e1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180015433`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800153e1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180015433`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001526c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001526c`

## string_xrefs

- `0x180015053`: `CLSID`
- `0x180015336`: `CLSID`
- `0x180015497`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x1800154d9`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x180015510`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x18001552e`: `onecore\ds\security\gina\profile\profsvc\ntfyhlp.cpp`
- `0x1800155ef`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
  unsigned __int64 v28; // rdx
  char *v29; // rcx
  int v30; // ebx
  _QWORD **v31; // rcx
  _QWORD *v32; // rax
  void *v33; // rbx
  HANDLE v34; // rax
  __int64 result; // rax
  LSTATUS v36; // eax
  __int64 v37; // rsi
  __int64 v38; // rax
  DWORD v39; // r12d
  HANDLE v40; // rax
  WCHAR *v41; // rax
  BYTE *v42; // rbx
  DWORD v43; // eax
  DWORD v44; // esi
  HANDLE v45; // rax
  HANDLE v46; // rax
  HANDLE v47; // rax
  const char *v48; // r9
  int phkResult; // [rsp+20h] [rbp-118h]
  unsigned int phkResulta; // [rsp+20h] [rbp-118h]
  int phkResultb; // [rsp+20h] [rbp-118h]
  int phkResultc; // [rsp+20h] [rbp-118h]
  int phkResultd; // [rsp+20h] [rbp-118h]
  int phkResulte; // [rsp+20h] [rbp-118h]
  char v55; // [rsp+40h] [rbp-F8h]
  DWORD Type; // [rsp+44h] [rbp-F4h] BYREF
  unsigned int pvData; // [rsp+48h] [rbp-F0h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-ECh] BYREF
  unsigned int v59; // [rsp+50h] [rbp-E8h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-E0h] BYREF
  __int64 v61; // [rsp+60h] [rbp-D8h]
  __int64 v62; // [rsp+68h] [rbp-D0h]
  HKEY hkey; // [rsp+70h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-C0h] BYREF
  void *v65[2]; // [rsp+80h] [rbp-B8h] BYREF
  __int64 v66; // [rsp+90h] [rbp-A8h]
  const WCHAR *v67; // [rsp+98h] [rbp-A0h]
  const wil::ResultException *v68; // [rsp+A0h] [rbp-98h] BYREF
  char v69[16]; // [rsp+B0h] [rbp-88h] BYREF
  LPVOID v70; // [rsp+C0h] [rbp-78h]
  char v71; // [rsp+C8h] [rbp-70h]
  _QWORD v72[3]; // [rsp+D0h] [rbp-68h] BYREF
  int v73; // [rsp+E8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v4 = a4;
  v5 = a1;
  ProfileTelemetry::WatchCurrentThread(v69);
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
    GetSubkeyNames(v65, hkey);
    v9 = (char *)v65[0];
    v10 = (const WCHAR *)v65[0];
    v11 = (const WCHAR *)v65[1];
    v67 = (const WCHAR *)v65[1];
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
        goto LABEL_72;
      }
      if ( (v5 & pvData) == 0 )
        goto LABEL_11;
      lpMem = 0;
      v61 = 0;
      v62 = 0;
      hKey = 0;
      v16 = RegOpenKeyExW(v13, v12, 0, 0x20019u, &hKey);
      v15 = v16;
      if ( v16 > 0 )
        v15 = (unsigned __int16)v16 | 0x80070000;
      if ( v15 >= 0 )
      {
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
        if ( Type - 1 <= 1 && cbData && (cbData & 1) == 0 )
        {
          v20 = cbData;
          ProcessHeap = GetProcessHeap();
          v18 = (BYTE *)HeapAlloc(ProcessHeap, 0, v20);
          if ( !v18 )
            goto LABEL_23;
          v36 = RegQueryValueExW(v17, L"CLSID", 0, &Type, v18, &cbData);
          v15 = v36;
          if ( v36 > 0 )
            v15 = (unsigned __int16)v36 | 0x80070000;
          if ( v15 < 0 )
            goto LABEL_24;
          v37 = (cbData >> 1) - 1;
          if ( Type == 2 )
          {
            v39 = ExpandEnvironmentStringsW((LPCWSTR)v18, 0, 0);
            if ( v39 )
            {
              v40 = GetProcessHeap();
              v41 = (WCHAR *)HeapAlloc(v40, 0, 2LL * v39);
              v42 = (BYTE *)v41;
              if ( v41 )
              {
                v43 = ExpandEnvironmentStringsW((LPCWSTR)v18, v41, v39);
                v44 = v43;
                if ( v43 && v43 <= v39 )
                {
                  v45 = GetProcessHeap();
                  HeapFree(v45, 0, v18);
                  v18 = v42;
                  v37 = v44 - 1;
                  v15 = 0;
                  goto LABEL_58;
                }
                v47 = GetProcessHeap();
                HeapFree(v47, 0, v42);
                v15 = -2147024774;
              }
              else
              {
LABEL_23:
                v15 = -2147024882;
              }
LABEL_24:
              v22 = lpMem;
LABEL_25:
              v23 = GetProcessHeap();
              HeapFree(v23, 0, v18);
              RegCloseKey(hKey);
              v5 = a1;
              v4 = a4;
              goto LABEL_26;
            }
          }
LABEL_58:
          if ( !*(_WORD *)&v18[2 * v37] )
          {
            v61 = 0;
            v62 = 0;
            if ( !v18 || (v38 = (unsigned int)(v37 + 1), (_DWORD)v37 == -1) )
            {
              v22 = lpMem;
            }
            else
            {
              v22 = v18;
              lpMem = v18;
              v62 = (unsigned int)v38;
              v61 = v38 - 1;
              *(_WORD *)&v18[2 * (unsigned int)v38 - 2] = 0;
            }
            v18 = 0;
            goto LABEL_25;
          }
        }
        v15 = -2147024883;
        goto LABEL_24;
      }
      v22 = lpMem;
LABEL_26:
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEC,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
          (const char *)(unsigned int)v15,
          phkResultc);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpMem);
        goto LABEL_72;
      }
      v59 = 0;
      Type = 4;
      RegGetValueW(v13, v12, L"Flags", 0x10u, 0, &v59, &Type);
      v8 = (const char *)v59;
      if ( a3 == -1 && (v59 & 4) != 0
        || !v4 && (v59 & 2) != 0
        || (v24 = NotifyComponent((const OLECHAR *)v22, v5, a2, v59, v4), v15 = v24, v24 >= 0) )
      {
        if ( v22 )
        {
          v25 = GetProcessHeap();
          HeapFree(v25, 0, v22);
        }
LABEL_11:
        v10 += 16;
        v9 = (char *)v65[0];
        v11 = v67;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF5,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
          (const char *)(unsigned int)v24,
          phkResultd);
        if ( v22 )
        {
          v46 = GetProcessHeap();
          HeapFree(v46, 0, v22);
        }
LABEL_72:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x124,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
          (const char *)(unsigned int)v15,
          phkResulte);
        v10 += 16;
        v9 = (char *)v65[0];
        v11 = v67;
      }
    }
    if ( v9 )
    {
      v26 = (char *)v65[1];
      if ( v9 != v65[1] )
      {
        do
        {
          v27 = *((_QWORD *)v9 + 3);
          if ( v27 > 7 )
            std::_Deallocate<16>(*(_QWORD *)v9, 2 * v27 + 2);
          *((_QWORD *)v9 + 2) = 0;
          *((_QWORD *)v9 + 3) = 7;
          *(_WORD *)v9 = 0;
          v9 += 32;
        }
        while ( v9 != v26 );
        v9 = (char *)v65[0];
      }
      v28 = (v66 - (_QWORD)v9) & 0xFFFFFFFFFFFFFFE0uLL;
      if ( v28 >= 0x1000 )
      {
        v29 = (char *)*((_QWORD *)v9 - 1);
        if ( (unsigned __int64)(v9 - v29 - 8) > 0x1F )
          __fastfail(5u);
        v28 += 39LL;
      }
      else
      {
        v29 = v9;
      }
      operator delete(v29, v28);
      *(_OWORD *)v65 = 0;
      v66 = 0;
    }
    if ( hkey )
      RegCloseKey(hkey);
    if ( v55 )
      CoUninitialize();
    v30 = v73;
    if ( v73 )
    {
      if ( v30 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
      v73 = 0;
      v31 = (_QWORD **)v72[0];
      while ( 1 )
      {
        v32 = *v31;
        if ( !*v31 )
          break;
        if ( v32 == v72 )
        {
          *v31 = (_QWORD *)v72[2];
          break;
        }
        v31 = (_QWORD **)(v32 + 2);
        v72[0] = v32 + 2;
      }
      v72[0] = 0;
    }
    if ( v71 )
    {
      v33 = v70;
      v34 = GetProcessHeap();
      HeapFree(v34, 0, v33);
    }
    result = 0;
  }
  catch ( const wil::ResultException *v68 )
  {
    v48 = (const char *)*((unsigned int *)v68 + 8);
    pvData = (unsigned int)v48;
    if ( (int)v48 < 0 )
    {
      if ( (_DWORD)v48 == -2147467263 )
        return 2147500033LL;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12D,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\ntfyhlp.cpp",
        v48,
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
0x180014e90  mov     qword ptr [rsp+arg_18], r9
0x180014e95  mov     [rsp+arg_10], r8d
0x180014e9a  mov     [rsp+arg_8], rdx
0x180014e9f  mov     [rsp+arg_0], ecx
0x180014ea3  push    rbx
0x180014ea4  push    rsi
0x180014ea5  push    rdi
0x180014ea6  push    r12
0x180014ea8  push    r13
0x180014eaa  push    r14
0x180014eac  push    r15
0x180014eae  sub     rsp, 100h
0x180014eb5  mov     r12, r9
0x180014eb8  mov     r14d, ecx
0x180014ebb  xor     esi, esi
0x180014ebd  lea     rcx, [rsp+138h+var_88]
0x180014ec5  call    ?WatchCurrentThread@ProfileTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; ProfileTelemetry::WatchCurrentThread(char const *)
0x180014eca  nop
0x180014ecb  lea     rcx, [rsp+138h+var_F8]
0x180014ed0  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x180014ed5  nop
0x180014ed6  mov     [rsp+138h+hkey], rsi
0x180014edb  lea     rax, [rsp+138h+hkey]
0x180014ee0  mov     [rsp+138h+phkResult], rax; unsigned int
0x180014ee5  mov     r9d, 20019h; samDesired
0x180014eeb  xor     r8d, r8d; ulOptions
0x180014eee  lea     rdx, aSoftwareMicros_33; "Software\\Microsoft\\Windows NT\\\\Curr"...
0x180014ef5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014efc  call    cs:__imp_RegOpenKeyExW
0x180014f03  nop     dword ptr [rax+rax+00h]
0x180014f08  test    eax, eax
0x180014f0a  jnz     loc_1800153C3
0x180014f10  mov     rdx, [rsp+138h+hkey]
0x180014f15  lea     rcx, [rsp+138h+var_B8]
0x180014f1d  call    ?GetSubkeyNames@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@@Z; GetSubkeyNames(HKEY__ *)
0x180014f22  nop
0x180014f23  mov     rbx, [rsp+138h+var_B8]
0x180014f2b  mov     rdi, rbx
0x180014f2e  mov     rax, [rsp+138h+var_B8+8]
0x180014f36  mov     [rsp+138h+var_A0], rax
0x180014f3e  xchg    ax, ax
0x180014f40  cmp     rdi, rax
0x180014f43  jz      loc_1800151CF
0x180014f49  cmp     qword ptr [rdi+18h], 7
0x180014f4e  jbe     short loc_180014FCC
0x180014f50  mov     r15, [rdi]
0x180014f53  mov     r13, [rsp+138h+hkey]
0x180014f58  mov     [rsp+138h+var_F0], esi
0x180014f5c  mov     [rsp+138h+Type], 4
0x180014f64  lea     rax, [rsp+138h+Type]
0x180014f69  mov     [rsp+138h+pcbData], rax; pcbData
0x180014f6e  lea     rax, [rsp+138h+var_F0]
0x180014f73  mov     [rsp+138h+pvData], rax; pvData
0x180014f78  mov     [rsp+138h+phkResult], rsi; int
0x180014f7d  mov     r9d, 10h; dwFlags
0x180014f83  lea     r8, aEvents; "Events"
0x180014f8a  mov     rdx, r15; lpSubKey
0x180014f8d  mov     rcx, r13; hkey
0x180014f90  call    cs:__imp_RegGetValueW
0x180014f97  nop     dword ptr [rax+rax+00h]
0x180014f9c  mov     ebx, eax
0x180014f9e  test    eax, eax
0x180014fa0  jg      short loc_180014FD1
0x180014fa2  test    ebx, ebx
0x180014fa4  js      loc_180015505
0x180014faa  test    [rsp+138h+var_F0], r14d
0x180014faf  jnz     short loc_180014FDC
0x180014fb1  add     rdi, 20h ; ' '
0x180014fb5  mov     rbx, [rsp+138h+var_B8]
0x180014fbd  mov     rax, [rsp+138h+var_A0]
0x180014fc5  xor     esi, esi
0x180014fc7  jmp     loc_180014F40
0x180014fcc  mov     r15, rdi
0x180014fcf  jmp     short loc_180014F53
0x180014fd1  movzx   ebx, ax
0x180014fd4  or      ebx, 80070000h
0x180014fda  jmp     short loc_180014FA2
0x180014fdc  mov     [rsp+138h+lpMem], rsi
0x180014fe1  mov     [rsp+138h+var_D8], rsi
0x180014fe6  mov     [rsp+138h+var_D0], rsi
0x180014feb  mov     [rsp+138h+hKey], rsi
0x180014ff0  lea     rax, [rsp+138h+hKey]
0x180014ff5  mov     [rsp+138h+phkResult], rax; phkResult
0x180014ffa  mov     r9d, 20019h; samDesired
0x180015000  xor     r8d, r8d; ulOptions
0x180015003  mov     rdx, r15; lpSubKey
0x180015006  mov     rcx, r13; hKey
0x180015009  call    cs:__imp_RegOpenKeyExW
0x180015010  nop     dword ptr [rax+rax+00h]
0x180015015  mov     ebx, eax
0x180015017  test    eax, eax
0x180015019  jg      loc_180015303
0x18001501f  test    ebx, ebx
0x180015021  js      loc_18001554C
0x180015027  mov     rsi, [rsp+138h+hKey]
0x18001502c  xor     r12d, r12d
0x18001502f  mov     r14d, r12d
0x180015032  mov     [rsp+138h+Type], r12d
0x180015037  mov     [rsp+138h+cbData], r12d
0x18001503c  lea     rax, [rsp+138h+cbData]
0x180015041  mov     [rsp+138h+pvData], rax; lpcbData
0x180015046  mov     [rsp+138h+phkResult], r12; int
0x18001504b  lea     r9, [rsp+138h+Type]; lpType
0x180015050  xor     r8d, r8d; lpReserved
0x180015053  lea     rdx, aClsid; "CLSID"
0x18001505a  mov     rcx, rsi; hKey
0x18001505d  call    cs:__imp_RegQueryValueExW
0x180015064  nop     dword ptr [rax+rax+00h]
0x180015069  mov     ebx, eax
0x18001506b  test    eax, eax
0x18001506d  jg      loc_180015311
0x180015073  test    ebx, ebx
0x180015075  js      short loc_1800150CD
0x180015077  mov     eax, [rsp+138h+Type]
0x18001507b  dec     eax
0x18001507d  cmp     eax, 1
0x180015080  ja      loc_180015482
0x180015086  mov     eax, [rsp+138h+cbData]
0x18001508a  test    eax, eax
0x18001508c  jz      loc_180015482
0x180015092  test    al, 1
0x180015094  jnz     loc_180015482
0x18001509a  mov     ebx, eax
0x18001509c  call    cs:__imp_GetProcessHeap
0x1800150a3  nop     dword ptr [rax+rax+00h]
0x1800150a8  mov     rcx, rax; hHeap
0x1800150ab  mov     r8d, ebx; dwBytes
0x1800150ae  xor     edx, edx; dwFlags
0x1800150b0  call    cs:__imp_HeapAlloc
0x1800150b7  nop     dword ptr [rax+rax+00h]
0x1800150bc  mov     r14, rax
0x1800150bf  test    rax, rax
0x1800150c2  jnz     loc_18001531F
0x1800150c8  mov     ebx, 8007000Eh
0x1800150cd  mov     rsi, [rsp+138h+lpMem]
0x1800150d2  call    cs:__imp_GetProcessHeap
0x1800150d9  nop     dword ptr [rax+rax+00h]
0x1800150de  mov     rcx, rax; hHeap
0x1800150e1  mov     r8, r14; lpMem
0x1800150e4  xor     edx, edx; dwFlags
0x1800150e6  call    cs:__imp_HeapFree
0x1800150ed  nop     dword ptr [rax+rax+00h]
0x1800150f2  mov     rcx, [rsp+138h+hKey]; hKey
0x1800150f7  call    cs:__imp_RegCloseKey
0x1800150fe  nop     dword ptr [rax+rax+00h]
0x180015103  mov     r14d, [rsp+138h+arg_0]
0x18001510b  mov     r12, qword ptr [rsp+138h+arg_18]
0x180015113  test    ebx, ebx
0x180015115  js      loc_180015523
0x18001511b  xor     ecx, ecx
0x18001511d  mov     [rsp+138h+var_E8], ecx
0x180015121  mov     [rsp+138h+Type], 4
0x180015129  lea     rax, [rsp+138h+Type]
0x18001512e  mov     [rsp+138h+pcbData], rax; pcbData
0x180015133  lea     rax, [rsp+138h+var_E8]
0x180015138  mov     [rsp+138h+pvData], rax; pvData
0x18001513d  mov     [rsp+138h+phkResult], rcx; pdwType
0x180015142  mov     r9d, 10h; dwFlags
0x180015148  lea     r8, Value; "Flags"
0x18001514f  mov     rdx, r15; lpSubKey
0x180015152  mov     rcx, r13; hkey
0x180015155  call    cs:__imp_RegGetValueW
0x18001515c  nop     dword ptr [rax+rax+00h]
0x180015161  mov     r9d, [rsp+138h+var_E8]
0x180015166  cmp     [rsp+138h+arg_10], 0FFFFFFFFh
0x18001516e  jnz     short loc_180015176
0x180015170  test    r9b, 4
0x180015174  jnz     short loc_1800151A1
0x180015176  test    r12, r12
0x180015179  jz      loc_180015592
0x18001517f  mov     [rsp+138h+phkResult], r12; int
0x180015184  mov     r8, [rsp+138h+arg_8]
0x18001518c  mov     edx, r14d
0x18001518f  mov     rcx, rsi
0x180015192  call    ?NotifyComponent@@YAJPEBGW4PROF_NOTIFY_EVENT_FLAGS@@PEAUPROF_NOTIFY_PARAM@@W4PROF_NOTIFY_FLAGS@@PEAX@Z; NotifyComponent(ushort const *,PROF_NOTIFY_EVENT_FLAGS,PROF_NOTIFY_PARAM *,PROF_NOTIFY_FLAGS,void *)
0x180015197  mov     ebx, eax
0x180015199  test    eax, eax
0x18001519b  js      loc_18001548C
0x1800151a1  test    rsi, rsi
0x1800151a4  jz      loc_180014FB1
0x1800151aa  call    cs:__imp_GetProcessHeap
0x1800151b1  nop     dword ptr [rax+rax+00h]
0x1800151b6  mov     rcx, rax; hHeap
0x1800151b9  mov     r8, rsi; lpMem
0x1800151bc  xor     edx, edx; dwFlags
0x1800151be  call    cs:__imp_HeapFree
0x1800151c5  nop     dword ptr [rax+rax+00h]
0x1800151ca  jmp     loc_180014FB1
0x1800151cf  test    rbx, rbx
0x1800151d2  jz      short loc_180015247
0x1800151d4  mov     rdi, [rsp+138h+var_B8+8]
0x1800151dc  cmp     rbx, rdi
0x1800151df  jz      short loc_18001520F
0x1800151e1  mov     rdx, [rbx+18h]
0x1800151e5  cmp     rdx, 7
0x1800151e9  ja      loc_1800155A1
0x1800151ef  mov     [rbx+10h], rsi
0x1800151f3  mov     qword ptr [rbx+18h], 7
0x1800151fb  mov     [rbx], si
0x1800151fe  add     rbx, 20h ; ' '
0x180015202  cmp     rbx, rdi
0x180015205  jnz     short loc_1800151E1
0x180015207  mov     rbx, [rsp+138h+var_B8]
0x18001520f  mov     rdx, [rsp+138h+var_A8]
0x180015217  sub     rdx, rbx
0x18001521a  and     rdx, 0FFFFFFFFFFFFFFE0h; unsigned __int64
0x18001521e  cmp     rdx, 1000h
0x180015225  jnb     loc_1800155B6
0x18001522b  mov     rcx, rbx; void *
0x18001522e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015233  xorps   xmm0, xmm0
0x180015236  movdqu  xmmword ptr [rsp+138h+var_B8], xmm0
0x18001523f  mov     [rsp+138h+var_A8], rsi
0x180015247  mov     rcx, [rsp+138h+hkey]; hKey
0x18001524c  test    rcx, rcx
0x18001524f  jz      short loc_18001525E
0x180015251  call    cs:__imp_RegCloseKey
0x180015258  nop     dword ptr [rax+rax+00h]
0x18001525d  nop
0x18001525e  movzx   eax, [rsp+138h+var_F8]
0x180015263  mov     [rsp+138h+var_F8], 0
0x180015268  test    al, al
0x18001526a  jz      short loc_180015279
0x18001526c  call    cs:__imp_CoUninitialize
0x180015273  nop     dword ptr [rax+rax+00h]
0x180015278  nop
0x180015279  mov     ebx, [rsp+138h+var_50]
0x180015280  test    ebx, ebx
0x180015282  jz      short loc_1800152BB
0x180015284  call    cs:__imp_GetCurrentThreadId
0x18001528b  nop     dword ptr [rax+rax+00h]
0x180015290  cmp     ebx, eax
0x180015292  jnz     loc_1800155D7
0x180015298  mov     [rsp+138h+var_50], esi
0x18001529f  mov     rcx, [rsp+138h+var_68]
0x1800152a7  mov     rax, [rcx]
0x1800152aa  test    rax, rax
0x1800152ad  jnz     loc_180015600
0x1800152b3  mov     [rsp+138h+var_68], rsi
0x1800152bb  cmp     [rsp+138h+var_70], 0
0x1800152c3  jz      short loc_1800152ED
0x1800152c5  mov     rbx, [rsp+138h+var_78]
0x1800152cd  call    cs:__imp_GetProcessHeap
0x1800152d4  nop     dword ptr [rax+rax+00h]
0x1800152d9  mov     r8, rbx; lpMem
0x1800152dc  xor     edx, edx; dwFlags
0x1800152de  mov     rcx, rax; hHeap
0x1800152e1  call    cs:__imp_HeapFree
0x1800152e8  nop     dword ptr [rax+rax+00h]
0x1800152ed  xor     eax, eax
0x1800152ef  add     rsp, 100h
0x1800152f6  pop     r15
0x1800152f8  pop     r14
0x1800152fa  pop     r13
0x1800152fc  pop     r12
0x1800152fe  pop     rdi
0x1800152ff  pop     rsi
0x180015300  pop     rbx
0x180015301  retn
0x180015303  movzx   ebx, ax
0x180015306  or      ebx, 80070000h
0x18001530c  jmp     loc_18001501F
0x180015311  movzx   ebx, ax
0x180015314  or      ebx, 80070000h
0x18001531a  jmp     loc_180015073
0x18001531f  lea     rax, [rsp+138h+cbData]
0x180015324  mov     [rsp+138h+pvData], rax; lpcbData
0x180015329  mov     [rsp+138h+phkResult], r14; lpData
0x18001532e  lea     r9, [rsp+138h+Type]; lpType
0x180015333  xor     r8d, r8d; lpReserved
0x180015336  lea     rdx, aClsid; "CLSID"
0x18001533d  mov     rcx, rsi; hKey
0x180015340  call    cs:__imp_RegQueryValueExW
0x180015347  nop     dword ptr [rax+rax+00h]
0x18001534c  mov     ebx, eax
0x18001534e  test    eax, eax
0x180015350  jg      short loc_1800153B8
0x180015352  test    ebx, ebx
0x180015354  js      loc_1800150CD
0x18001535a  mov     esi, [rsp+138h+cbData]
0x18001535e  shr     esi, 1
0x180015360  dec     esi
0x180015362  cmp     [rsp+138h+Type], 2
0x180015367  jz      short loc_1800153D9
0x180015369  cmp     word ptr [r14+rsi*2], 0
0x18001536f  jnz     loc_180015482
0x180015375  mov     [rsp+138h+var_D8], r12
0x18001537a  mov     [rsp+138h+var_D0], r12
0x18001537f  test    r14, r14
0x180015382  jz      loc_180015588
0x180015388  lea     eax, [rsi+1]
0x18001538b  mov     ecx, eax
0x18001538d  test    eax, eax
0x18001538f  jz      loc_180015588
0x180015395  mov     rsi, r14
0x180015398  mov     [rsp+138h+lpMem], r14
0x18001539d  mov     [rsp+138h+var_D0], rcx
0x1800153a2  dec     rax
0x1800153a5  mov     [rsp+138h+var_D8], rax
0x1800153aa  mov     [r14+rcx*2-2], r12w
  ... truncated ...
```
