# SvcWorker::UseProtectedProcess(ushort const *,ushort const *,ushort const *,LogicalImage *)

- ea: `0x18002f454`
- end: `0x18002fa5e`
- name: `?UseProtectedProcess@SvcWorker@@CA_NPEBG00PEAVLogicalImage@@@Z`
- size: `1546`
- prototype: `bool __fastcall(wchar_t *String1, const unsigned __int16 *, const unsigned __int16 *, struct LogicalImage *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002a784`

## callees

- `0x1800064a8`
- `0x1800083e0`
- `0x180008434`
- `0x180008488`
- `0x18000d5f0`
- `0x1800252ac`
- `0x18002e798`
- `0x18002f454`
- `0x180030b1c`
- `0x180030d84`
- `0x1800351e8`
- `0x1800354e0`
- `0x1800366a8`
- `0x180037c10`
- `0x18003b85c`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18002fa00`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18002fa00`
- `KERNEL32!FindClose` at `0x18002f879`
- `KERNEL32!FindClose` at `0x18002f879`
- `KERNEL32!CreateFileW` at `0x18002f618`
- `KERNEL32!CreateFileW` at `0x18002f7eb`
- `KERNEL32!CreateFileW` at `0x18002f618`
- `KERNEL32!CreateFileW` at `0x18002f7eb`
- `KERNEL32!GetModuleHandleW` at `0x18002f53a`
- `KERNEL32!GetModuleHandleW` at `0x18002f53a`
- `KERNEL32!FindNextFileW` at `0x18002f730`
- `KERNEL32!FindNextFileW` at `0x18002f730`
- `KERNEL32!CloseHandle` at `0x18002f801`
- `KERNEL32!CloseHandle` at `0x18002f8cf`
- `KERNEL32!CloseHandle` at `0x18002f801`
- `KERNEL32!CloseHandle` at `0x18002f8cf`
- `KERNEL32!GetLastError` at `0x18002f73a`
- `KERNEL32!GetLastError` at `0x18002f73a`
- `KERNEL32!GetProcAddress` at `0x18002f553`
- `KERNEL32!GetProcAddress` at `0x18002f553`
- `KERNEL32!HeapFree` at `0x18002f8bb`
- `KERNEL32!HeapFree` at `0x18002f8bb`
- `KERNEL32!GetProcessHeap` at `0x18002f8a6`
- `KERNEL32!GetProcessHeap` at `0x18002f8a6`
- `VCRUNTIME140_CLR0400!wcsrchr` at `0x18002f67e`
- `VCRUNTIME140_CLR0400!wcsrchr` at `0x18002f67e`
- `VCRUNTIME140_CLR0400!wcschr` at `0x18002f984`
- `VCRUNTIME140_CLR0400!wcschr` at `0x18002f9c8`
- `VCRUNTIME140_CLR0400!wcschr` at `0x18002f984`
- `VCRUNTIME140_CLR0400!wcschr` at `0x18002f9c8`
- `VCRUNTIME140_CLR0400!wcsstr` at `0x18002f999`
- `VCRUNTIME140_CLR0400!wcsstr` at `0x18002f9dd`
- `VCRUNTIME140_CLR0400!wcsstr` at `0x18002f999`
- `VCRUNTIME140_CLR0400!wcsstr` at `0x18002f9dd`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002f4f9`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002fa19`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002f4f9`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002fa19`
- `ucrtbase_clr0400!_wcsicmp` at `0x18002f7b6`
- `ucrtbase_clr0400!_wcsicmp` at `0x18002f7b6`

## string_xrefs

- `0x18002f549`: `GetCachedSigningLevel`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
char __fastcall SvcWorker::UseProtectedProcess(
        wchar_t *String1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct LogicalImage *a4)
{
  unsigned int ConfigValue; // eax
  char v9; // bl
  int v10; // eax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // r13
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(const unsigned __int16 *, int *); // rax
  int v15; // eax
  char v17; // di
  HANDLE FileW; // rax
  void *v19; // r15
  BOOL v20; // r12d
  wchar_t *v21; // rcx
  char *v22; // r14
  const unsigned __int16 *v23; // r8
  char v24; // al
  HANDLE v25; // r14
  void *v26; // rsi
  HANDLE ProcessHeap; // rax
  SString *v28; // rdi
  const unsigned __int16 *v29; // rdi
  UINT SystemWindowsDirectoryW; // eax
  __int64 v31; // rdi
  int v32; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v33; // [rsp+44h] [rbp-BCh] BYREF
  bool v34; // [rsp+48h] [rbp-B8h] BYREF
  int v35; // [rsp+4Ch] [rbp-B4h] BYREF
  char *p_hFindFile; // [rsp+50h] [rbp-B0h]
  unsigned int v37; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v38; // [rsp+60h] [rbp-A0h]
  int v39; // [rsp+68h] [rbp-98h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hFindFile; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v42; // [rsp+2C8h] [rbp+1C8h]
  int v43; // [rsp+2D0h] [rbp+1D0h]
  int v44; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int64 v45; // [rsp+2E4h] [rbp+1E4h]
  LPVOID lpMem; // [rsp+2F0h] [rbp+1F0h]
  __int16 v47; // [rsp+2F8h] [rbp+1F8h] BYREF
  wchar_t String2[264]; // [rsp+500h] [rbp+400h] BYREF

  ConfigValue = CLRConfig::GetConfigValue(
                  (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::INTERNAL_NGenProtectedProcess_FeatureEnabled,
                  (bool)a2,
                  &v34);
  v9 = 0;
  if ( !ConfigValue || ConfigValue == -1 && (unsigned int)Helpers::IsUsingPrivateStore() || !a4 && !a3 )
    return 0;
  v10 = gRunningOnStatus;
  if ( !gRunningOnStatus )
  {
    InitRunningOnVersionStatus();
    v10 = gRunningOnStatus;
  }
  if ( v10 < 6 || !_wcsnicmp(String1, L"v2.", 3u) || IsNgenOffline() )
    return 0;
  if ( !a2 )
  {
    if ( IsCLRWldpGetLockdownPolicyAvailable() )
    {
      v32 = 0;
      while ( !qword_18006FFF8 )
      {
        if ( bWldpGetLockdownPolicyProbed || !IsCLRWldpGetLockdownPolicyAvailable() )
          goto LABEL_80;
      }
      if ( (int)qword_18006FFF8(0, &v32, 0) < 0 )
        goto LABEL_83;
LABEL_80:
      if ( (v32 & 0x80000004) != 0x80000000 && (v32 & 0x80000005) != 0x80000005 )
        return 1;
    }
LABEL_83:
    if ( a4 )
    {
      v28 = (SString *)*((_QWORD *)a4 + 13);
      if ( v28 || (v28 = (SString *)*((_QWORD *)a4 + 11)) != 0 )
      {
        SString::ConvertToUnicode(v28);
        v29 = (const unsigned __int16 *)*((_QWORD *)v28 + 2);
      }
      else
      {
        v29 = 0;
      }
      if ( !IsFrameworkAssemblyName(v29) && (wcschr(v29, 0x5Cu) || !wcsstr(v29, L"ContentType=WindowsRuntime")) )
        return v9;
    }
    else if ( !IsFrameworkAssemblyName(a3) && (wcschr(a3, 0x5Cu) || !wcsstr(a3, L"ContentType=WindowsRuntime")) )
    {
      if ( !(unsigned int)IsWinMD(a3) )
        return v9;
      SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(String2, 0x104u);
      if ( !SystemWindowsDirectoryW )
        return v9;
      v31 = SystemWindowsDirectoryW;
      if ( _wcsnicmp(a3, String2, SystemWindowsDirectoryW) || a3[v31] != 92 )
        return v9;
    }
    return 1;
  }
  v35 = 0;
  if ( IsCLRGetStagedPackageOriginAvailable() )
  {
    while ( 1 )
    {
      v14 = (__int64 (__fastcall *)(const unsigned __int16 *, int *))qword_18006FFE8;
      if ( qword_18006FFE8 )
        break;
      if ( bGetStagedPackageOriginProbed || !IsCLRGetStagedPackageOriginAvailable() )
      {
        v15 = 0;
        goto LABEL_28;
      }
    }
  }
  else
  {
    if ( !IsCLRGetStagedPackageOrigin_0Available() )
      goto LABEL_14;
    while ( 1 )
    {
      v14 = (__int64 (__fastcall *)(const unsigned __int16 *, int *))qword_18006FFF0;
      if ( qword_18006FFF0 )
        break;
      if ( bGetStagedPackageOrigin_0Probed || !IsCLRGetStagedPackageOrigin_0Available() )
        return (unsigned int)(v35 - 2) <= 1;
    }
  }
  v15 = v14(a2, &v35);
LABEL_28:
  if ( !v15 )
    return (unsigned int)(v35 - 2) <= 1;
LABEL_14:
  ModuleHandleW = GetModuleHandleW(L"kernel32");
  if ( !ModuleHandleW )
    return 0;
  ProcAddress = GetProcAddress(ModuleHandleW, "GetCachedSigningLevel");
  if ( !ProcAddress )
    return 0;
  if ( a4 )
  {
    v13 = *((_QWORD *)a4 + 11);
    if ( v13 )
    {
      SString::ConvertToUnicode(*((SString **)a4 + 11));
      a3 = *(const unsigned __int16 **)(v13 + 16);
    }
    else
    {
      a3 = 0;
    }
  }
  v17 = 1;
  FileW = CreateFileW(a3, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v19 = FileW;
  v38 = FileW;
  v20 = FileW != (HANDLE)-1LL;
  v39 = v20;
  if ( FileW != (HANDLE)-1LL )
  {
    v32 = 0;
    v33 = 0;
    if ( ((unsigned int (__fastcall *)(HANDLE, int *, unsigned int *, _QWORD, _QWORD, _QWORD))ProcAddress)(
           FileW,
           &v32,
           &v33,
           0,
           0,
           0)
      && v33 >= 6 )
    {
      goto LABEL_69;
    }
    v21 = wcsrchr(a3, 0x5Cu);
    if ( v21 )
    {
      v45 = 512;
      lpMem = &v47;
      v44 = 2;
      v47 = 0;
      SString::Set((SString *)&v44, a3, v21 - a3);
      SString::ConvertToUnicode((SString *)&v44);
      v22 = (char *)lpMem;
      p_hFindFile = (char *)lpMem;
      ClrDirectoryEnumerator::ClrDirectoryEnumerator(&FindFileData, (const unsigned __int16 *)lpMem, v23);
      while ( 1 )
      {
        if ( hFindFile != (HANDLE)-1LL )
        {
          while ( 1 )
          {
            if ( v43 )
            {
              if ( !FindNextFileW(hFindFile, &FindFileData) )
              {
                if ( GetLastError() != 18 )
                  ThrowLastError();
                break;
              }
            }
            else
            {
              v43 = 1;
            }
            if ( FindFileData.cFileName[0] != 46
              || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
            {
              v24 = 1;
              goto LABEL_49;
            }
          }
        }
        v24 = 0;
LABEL_49:
        if ( !v24 )
          break;
        if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
        {
          v37 = 260;
          if ( (int)clr::fs::Path::Combine(v22, FindFileData.cFileName, &v37, String2) >= 0 )
          {
            if ( _wcsicmp(a3, String2) )
            {
              v25 = CreateFileW(String2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
              if ( v20 )
              {
                if ( v19 )
                  CloseHandle(v19);
                v20 = 0;
                v39 = 0;
              }
              v19 = v25;
              v38 = v25;
              if ( v25 != (HANDLE)-1LL )
              {
                v20 = 1;
                v39 = 1;
                if ( ((unsigned int (__fastcall *)(HANDLE, int *, unsigned int *, _QWORD, _QWORD, _QWORD))ProcAddress)(
                       v25,
                       &v32,
                       &v33,
                       0,
                       0,
                       0) )
                {
                  if ( v33 >= 6 )
                    goto LABEL_62;
                }
              }
              v22 = p_hFindFile;
            }
          }
        }
      }
      v17 = 0;
LABEL_62:
      p_hFindFile = (char *)&hFindFile;
      if ( v42 )
      {
        FindClose(hFindFile);
        v42 = 0;
      }
      if ( (v45 & 0x800000000LL) != 0 )
      {
        v26 = lpMem;
        if ( lpMem )
        {
          ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            ProcessHeap = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
          }
          HeapFree(ProcessHeap, 0, v26);
        }
      }
      goto LABEL_69;
    }
  }
  v17 = 0;
LABEL_69:
  if ( v20 )
  {
    if ( v19 )
      CloseHandle(v19);
    v39 = 0;
  }
  return v17;
}

```

## disassembly

```asm
0x18002f454  push    rbp
0x18002f456  push    rbx
0x18002f457  push    rsi
0x18002f458  push    rdi
0x18002f459  push    r12
0x18002f45b  push    r13
0x18002f45d  push    r14
0x18002f45f  push    r15
0x18002f461  lea     rbp, [rsp-628h]
0x18002f469  sub     rsp, 728h
0x18002f470  mov     rax, cs:__security_cookie
0x18002f477  xor     rax, rsp
0x18002f47a  mov     [rbp+660h+var_50], rax
0x18002f481  mov     r14, r9
0x18002f484  mov     rsi, r8
0x18002f487  mov     rdi, rdx
0x18002f48a  mov     r15, rcx
0x18002f48d  lea     r8, [rsp+760h+var_718]; bool *
0x18002f492  lea     rcx, ?INTERNAL_NGenProtectedProcess_FeatureEnabled@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x18002f499  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x18002f49e  xor     ebx, ebx
0x18002f4a0  test    eax, eax
0x18002f4a2  jz      loc_18002FA33
0x18002f4a8  cmp     eax, 0FFFFFFFFh
0x18002f4ab  jnz     short loc_18002F4BA
0x18002f4ad  call    ?IsUsingPrivateStore@Helpers@@SAHXZ; Helpers::IsUsingPrivateStore(void)
0x18002f4b2  test    eax, eax
0x18002f4b4  jnz     loc_18002FA33
0x18002f4ba  test    r14, r14
0x18002f4bd  jnz     short loc_18002F4C8
0x18002f4bf  test    rsi, rsi
0x18002f4c2  jz      loc_18002FA33
0x18002f4c8  mov     eax, cs:?gRunningOnStatus@@3W4RunningOnStatusEnum@@A; RunningOnStatusEnum gRunningOnStatus
0x18002f4ce  test    eax, eax
0x18002f4d0  jnz     short loc_18002F4DD
0x18002f4d2  call    ?InitRunningOnVersionStatus@@YAXXZ; InitRunningOnVersionStatus(void)
0x18002f4d7  mov     eax, cs:?gRunningOnStatus@@3W4RunningOnStatusEnum@@A; RunningOnStatusEnum gRunningOnStatus
0x18002f4dd  cmp     eax, 6
0x18002f4e0  jl      loc_18002FA33
0x18002f4e6  mov     r12d, 3
0x18002f4ec  mov     r8d, r12d; MaxCount
0x18002f4ef  lea     rdx, aV2; "v2."
0x18002f4f6  mov     rcx, r15; String1
0x18002f4f9  call    cs:__imp__wcsnicmp
0x18002f4ff  test    eax, eax
0x18002f501  jz      loc_18002FA33
0x18002f507  call    ?IsNgenOffline@@YA_NXZ; IsNgenOffline(void)
0x18002f50c  test    al, al
0x18002f50e  jnz     loc_18002FA33
0x18002f514  test    rdi, rdi
0x18002f517  jz      loc_18002F8E1
0x18002f51d  mov     [rsp+760h+var_714], ebx
0x18002f521  call    ?IsCLRGetStagedPackageOriginAvailable@@YA_NXZ; IsCLRGetStagedPackageOriginAvailable(void)
0x18002f526  test    al, al
0x18002f528  jnz     short loc_18002F58D
0x18002f52a  call    ?IsCLRGetStagedPackageOrigin_0Available@@YA_NXZ; IsCLRGetStagedPackageOrigin_0Available(void)
0x18002f52f  test    al, al
0x18002f531  jnz     short loc_18002F5B0
0x18002f533  lea     rcx, aKernel32; "kernel32"
0x18002f53a  call    cs:__imp_GetModuleHandleW
0x18002f540  test    rax, rax
0x18002f543  jz      loc_18002FA33
0x18002f549  lea     rdx, aGetcachedsigni; "GetCachedSigningLevel"
0x18002f550  mov     rcx, rax; hModule
0x18002f553  call    cs:__imp_GetProcAddress
0x18002f559  mov     r13, rax
0x18002f55c  test    rax, rax
0x18002f55f  jz      loc_18002FA33
0x18002f565  test    r14, r14
0x18002f568  jz      loc_18002F5F4
0x18002f56e  mov     rsi, [r14+58h]
0x18002f572  test    rsi, rsi
0x18002f575  jnz     short loc_18002F5E8
0x18002f577  mov     rsi, rbx
0x18002f57a  jmp     short loc_18002F5F4
0x18002f57c  cmp     cs:?bGetStagedPackageOriginProbed@@3_NA, bl; bool bGetStagedPackageOriginProbed
0x18002f582  jnz     short loc_18002F59B
0x18002f584  call    ?IsCLRGetStagedPackageOriginAvailable@@YA_NXZ; IsCLRGetStagedPackageOriginAvailable(void)
0x18002f589  test    al, al
0x18002f58b  jz      short loc_18002F59B
0x18002f58d  mov     rax, cs:qword_18006FFE8
0x18002f594  test    rax, rax
0x18002f597  jz      short loc_18002F57C
0x18002f599  jmp     short loc_18002F5BC
0x18002f59b  mov     eax, ebx
0x18002f59d  jmp     short loc_18002F5CA
0x18002f59f  cmp     cs:?bGetStagedPackageOrigin_0Probed@@3_NA, bl; bool bGetStagedPackageOrigin_0Probed
0x18002f5a5  jnz     short loc_18002F5D2
0x18002f5a7  call    ?IsCLRGetStagedPackageOrigin_0Available@@YA_NXZ; IsCLRGetStagedPackageOrigin_0Available(void)
0x18002f5ac  test    al, al
0x18002f5ae  jz      short loc_18002F5D2
0x18002f5b0  mov     rax, cs:qword_18006FFF0
0x18002f5b7  test    rax, rax
0x18002f5ba  jz      short loc_18002F59F
0x18002f5bc  lea     rdx, [rsp+760h+var_714]
0x18002f5c1  mov     rcx, rdi
0x18002f5c4  call    cs:__guard_dispatch_icall_fptr
0x18002f5ca  test    eax, eax
0x18002f5cc  jnz     loc_18002F533
0x18002f5d2  mov     eax, [rsp+760h+var_714]
0x18002f5d6  add     eax, 0FFFFFFFEh
0x18002f5d9  mov     edi, 1
0x18002f5de  cmp     eax, edi
0x18002f5e0  setbe   al
0x18002f5e3  jmp     loc_18002FA35
0x18002f5e8  mov     rcx, rsi; this
0x18002f5eb  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002f5f0  mov     rsi, [rsi+10h]
0x18002f5f4  mov     [rsp+760h+hTemplateFile], rbx; hTemplateFile
0x18002f5f9  mov     [rsp+760h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002f601  mov     [rsp+760h+dwCreationDisposition], r12d; dwCreationDisposition
0x18002f606  xor     r9d, r9d; lpSecurityAttributes
0x18002f609  lea     edi, [r9+1]
0x18002f60d  mov     r8d, edi; dwShareMode
0x18002f610  mov     edx, 80000000h; dwDesiredAccess
0x18002f615  mov     rcx, rsi; lpFileName
0x18002f618  call    cs:__imp_CreateFileW
0x18002f61e  mov     r15, rax
0x18002f621  mov     [rsp+760h+var_700], rax
0x18002f626  mov     [rsp+760h+var_6F8], ebx
0x18002f62a  mov     r12d, ebx
0x18002f62d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002f631  cmovnz  r12d, edi
0x18002f635  mov     [rsp+760h+var_6F8], r12d
0x18002f63a  jz      short loc_18002F68C
0x18002f63c  mov     [rsp+760h+var_720], ebx
0x18002f640  mov     [rsp+760h+var_71C], ebx
0x18002f644  mov     qword ptr [rsp+760h+dwFlagsAndAttributes], rbx
0x18002f649  mov     qword ptr [rsp+760h+dwCreationDisposition], rbx
0x18002f64e  xor     r9d, r9d
0x18002f651  lea     r8, [rsp+760h+var_71C]
0x18002f656  lea     rdx, [rsp+760h+var_720]
0x18002f65b  mov     rcx, rax
0x18002f65e  mov     rax, r13
0x18002f661  call    cs:__guard_dispatch_icall_fptr
0x18002f667  test    eax, eax
0x18002f669  jz      short loc_18002F676
0x18002f66b  cmp     [rsp+760h+var_71C], 6
0x18002f670  jnb     loc_18002F8C2
0x18002f676  mov     edx, 5Ch ; '\'; Ch
0x18002f67b  mov     rcx, rsi; Str
0x18002f67e  call    cs:__imp_wcsrchr
0x18002f684  mov     rcx, rax
0x18002f687  test    rax, rax
0x18002f68a  jnz     short loc_18002F694
0x18002f68c  mov     dil, bl
0x18002f68f  jmp     loc_18002F8C2
0x18002f694  mov     [rbp+660h+var_480], rbx
0x18002f69b  mov     [rbp+660h+var_480+4], 200h
0x18002f6a6  mov     [rbp+660h+lpMem], rbx
0x18002f6ad  lea     rax, [rbp+660h+var_468]
0x18002f6b4  mov     [rbp+660h+lpMem], rax
0x18002f6bb  mov     dword ptr [rbp+660h+var_480], 2
0x18002f6c5  mov     rax, [rbp+660h+lpMem]
0x18002f6cc  mov     [rax], bx
0x18002f6cf  sub     rcx, rsi
0x18002f6d2  sar     rcx, 1
0x18002f6d5  mov     r8d, ecx; unsigned int
0x18002f6d8  mov     rdx, rsi; unsigned __int16 *
0x18002f6db  lea     rcx, [rbp+660h+var_480]; this
0x18002f6e2  call    ?Set@SString@@QEAAXPEBGI@Z; SString::Set(ushort const *,uint)
0x18002f6e7  nop
0x18002f6e8  lea     rcx, [rbp+660h+var_480]; this
0x18002f6ef  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002f6f4  mov     r14, [rbp+660h+lpMem]
0x18002f6fb  mov     [rsp+760h+var_710], r14
0x18002f700  mov     rdx, r14; unsigned __int16 *
0x18002f703  lea     rcx, [rsp+760h+FindFileData]; lpFindFileData
0x18002f708  call    ??0ClrDirectoryEnumerator@@QEAA@PEBG0@Z; ClrDirectoryEnumerator::ClrDirectoryEnumerator(ushort const *,ushort const *)
0x18002f70d  nop
0x18002f70e  cmp     [rbp+660h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18002f716  jnz     short loc_18002F71C
0x18002f718  mov     al, bl
0x18002f71a  jmp     short loc_18002F775
0x18002f71c  cmp     [rbp+660h+var_490], ebx
0x18002f722  jz      short loc_18002F74B
0x18002f724  lea     rdx, [rsp+760h+FindFileData]; lpFindFileData
0x18002f729  mov     rcx, [rbp+660h+hFindFile]; hFindFile
0x18002f730  call    cs:__imp_FindNextFileW
0x18002f736  test    eax, eax
0x18002f738  jnz     short loc_18002F751
0x18002f73a  call    cs:__imp_GetLastError
0x18002f740  cmp     eax, 12h
0x18002f743  jnz     loc_18002FA58
0x18002f749  jmp     short loc_18002F718
0x18002f74b  mov     [rbp+660h+var_490], edi
0x18002f751  cmp     [rbp+660h+FindFileData.cFileName], 2Eh ; '.'
0x18002f756  jnz     short loc_18002F772
0x18002f758  cmp     [rbp+660h+FindFileData.cFileName+2], bx
0x18002f75c  jz      short loc_18002F71C
0x18002f75e  cmp     [rbp+660h+FindFileData.cFileName], 2Eh ; '.'
0x18002f763  jnz     short loc_18002F772
0x18002f765  cmp     [rbp+660h+FindFileData.cFileName+2], 2Eh ; '.'
0x18002f76a  jnz     short loc_18002F772
0x18002f76c  cmp     [rbp+660h+FindFileData.cFileName+4], bx
0x18002f770  jz      short loc_18002F71C
0x18002f772  mov     al, dil
0x18002f775  test    al, al
0x18002f777  jz      loc_18002F85B
0x18002f77d  test    byte ptr [rsp+760h+FindFileData.dwFileAttributes], 10h
0x18002f782  jnz     short loc_18002F70E
0x18002f784  mov     [rsp+760h+var_708], 104h
0x18002f78c  lea     r9, [rbp+660h+String2]; unsigned __int16 *
0x18002f793  lea     r8, [rsp+760h+var_708]; unsigned int *
0x18002f798  lea     rdx, [rbp+660h+FindFileData.cFileName]; unsigned __int16 *
0x18002f79c  mov     rcx, r14; unsigned __int16 *
0x18002f79f  call    ?Combine@Path@fs@clr@@SAJPEBG0PEAKPEAG@Z; clr::fs::Path::Combine(ushort const *,ushort const *,ulong *,ushort *)
0x18002f7a4  test    eax, eax
0x18002f7a6  js      loc_18002F70E
0x18002f7ac  lea     rdx, [rbp+660h+String2]; String2
0x18002f7b3  mov     rcx, rsi; String1
0x18002f7b6  call    cs:__imp__wcsicmp
0x18002f7bc  test    eax, eax
0x18002f7be  jz      loc_18002F70E
0x18002f7c4  mov     [rsp+760h+hTemplateFile], rbx; hTemplateFile
0x18002f7c9  mov     [rsp+760h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002f7d1  mov     [rsp+760h+dwCreationDisposition], 3; dwCreationDisposition
0x18002f7d9  xor     r9d, r9d; lpSecurityAttributes
0x18002f7dc  mov     r8d, edi; dwShareMode
0x18002f7df  mov     edx, 80000000h; dwDesiredAccess
0x18002f7e4  lea     rcx, [rbp+660h+String2]; lpFileName
0x18002f7eb  call    cs:__imp_CreateFileW
0x18002f7f1  mov     r14, rax
0x18002f7f4  test    r12d, r12d
0x18002f7f7  jz      short loc_18002F80E
0x18002f7f9  test    r15, r15
0x18002f7fc  jz      short loc_18002F807
0x18002f7fe  mov     rcx, r15; hObject
0x18002f801  call    cs:__imp_CloseHandle
0x18002f807  mov     r12d, ebx
0x18002f80a  mov     [rsp+760h+var_6F8], ebx
0x18002f80e  mov     r15, r14
0x18002f811  mov     [rsp+760h+var_700], r14
0x18002f816  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18002f81a  jz      short loc_18002F851
0x18002f81c  mov     r12d, edi
0x18002f81f  mov     [rsp+760h+var_6F8], edi
0x18002f823  mov     qword ptr [rsp+760h+dwFlagsAndAttributes], rbx
0x18002f828  mov     qword ptr [rsp+760h+dwCreationDisposition], rbx
0x18002f82d  xor     r9d, r9d
0x18002f830  lea     r8, [rsp+760h+var_71C]
0x18002f835  lea     rdx, [rsp+760h+var_720]
0x18002f83a  mov     rcx, r14
0x18002f83d  mov     rax, r13
0x18002f840  call    cs:__guard_dispatch_icall_fptr
0x18002f846  test    eax, eax
0x18002f848  jz      short loc_18002F851
0x18002f84a  cmp     [rsp+760h+var_71C], 6
0x18002f84f  jnb     short loc_18002F85E
0x18002f851  mov     r14, [rsp+760h+var_710]
0x18002f856  jmp     loc_18002F70E
0x18002f85b  mov     dil, bl
0x18002f85e  lea     rax, [rbp+660h+hFindFile]
0x18002f865  mov     [rsp+760h+var_710], rax
0x18002f86a  cmp     [rbp+660h+var_498], ebx
0x18002f870  jz      short loc_18002F885
0x18002f872  mov     rcx, [rbp+660h+hFindFile]; hFindFile
0x18002f879  call    cs:__imp_FindClose
0x18002f87f  mov     [rbp+660h+var_498], ebx
0x18002f885  test    [rbp+660h+var_478], 8
0x18002f88c  jz      short loc_18002F8C2
0x18002f88e  mov     rsi, [rbp+660h+lpMem]
0x18002f895  test    rsi, rsi
0x18002f898  jz      short loc_18002F8C2
0x18002f89a  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18002f8a1  test    rax, rax
0x18002f8a4  jnz     short loc_18002F8B3
0x18002f8a6  call    cs:__imp_GetProcessHeap
0x18002f8ac  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18002f8b3  mov     r8, rsi; lpMem
0x18002f8b6  xor     edx, edx; dwFlags
0x18002f8b8  mov     rcx, rax; hHeap
0x18002f8bb  call    cs:__imp_HeapFree
0x18002f8c1  nop
0x18002f8c2  test    r12d, r12d
0x18002f8c5  jz      short loc_18002F8D9
0x18002f8c7  test    r15, r15
0x18002f8ca  jz      short loc_18002F8D5
0x18002f8cc  mov     rcx, r15; hObject
0x18002f8cf  call    cs:__imp_CloseHandle
0x18002f8d5  mov     [rsp+760h+var_6F8], ebx
0x18002f8d9  mov     al, dil
0x18002f8dc  jmp     loc_18002FA35
0x18002f8e1  call    ?IsCLRWldpGetLockdownPolicyAvailable@@YA_NXZ; IsCLRWldpGetLockdownPolicyAvailable(void)
0x18002f8e6  test    al, al
0x18002f8e8  jz      short loc_18002F948
0x18002f8ea  mov     [rsp+760h+var_720], ebx
0x18002f8ee  jmp     short loc_18002F901
0x18002f8f0  cmp     cs:?bWldpGetLockdownPolicyProbed@@3_NA, bl; bool bWldpGetLockdownPolicyProbed
0x18002f8f6  jnz     short loc_18002F921
0x18002f8f8  call    ?IsCLRWldpGetLockdownPolicyAvailable@@YA_NXZ; IsCLRWldpGetLockdownPolicyAvailable(void)
0x18002f8fd  test    al, al
0x18002f8ff  jz      short loc_18002F921
0x18002f901  mov     rax, cs:qword_18006FFF8
0x18002f908  test    rax, rax
0x18002f90b  jz      short loc_18002F8F0
0x18002f90d  xor     r8d, r8d
0x18002f910  lea     rdx, [rsp+760h+var_720]
0x18002f915  xor     ecx, ecx
0x18002f917  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
