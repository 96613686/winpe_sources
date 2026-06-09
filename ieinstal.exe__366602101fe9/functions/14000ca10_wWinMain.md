# wWinMain

- ea: `0x14000ca10`
- end: `0x14000cf6e`
- name: `wWinMain`
- size: `1374`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400012b0`

## callees

- `0x140004108`
- `0x1400042c4`
- `0x140008c74`
- `0x14000c498`
- `0x14000c964`
- `0x14000ca10`
- `0x14000d998`
- `0x140010986`
- `0x1400109c0`
- `0x140011010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000ccde`
- `ADVAPI32!RegCloseKey` at `0x14000cd49`
- `ADVAPI32!RegCloseKey` at `0x14000ccde`
- `ADVAPI32!RegCloseKey` at `0x14000cd49`
- `ADVAPI32!RegOpenKeyExW` at `0x14000cc93`
- `ADVAPI32!RegOpenKeyExW` at `0x14000cd04`
- `ADVAPI32!RegOpenKeyExW` at `0x14000cc93`
- `ADVAPI32!RegOpenKeyExW` at `0x14000cd04`
- `ADVAPI32!RegDeleteKeyW` at `0x14000cccb`
- `ADVAPI32!RegDeleteKeyW` at `0x14000cd36`
- `ADVAPI32!RegDeleteKeyW` at `0x14000cccb`
- `ADVAPI32!RegDeleteKeyW` at `0x14000cd36`
- `KERNEL32!CloseHandle` at `0x14000cf1b`
- `KERNEL32!CloseHandle` at `0x14000cf1b`
- `KERNEL32!GetProcAddress` at `0x14000ce92`
- `KERNEL32!GetProcAddress` at `0x14000ce92`
- `KERNEL32!FreeLibrary` at `0x14000ceab`
- `KERNEL32!FreeLibrary` at `0x14000ceab`
- `KERNEL32!LoadLibraryExW` at `0x14000ce74`
- `KERNEL32!LoadLibraryExW` at `0x14000ce74`
- `KERNEL32!CreateEventW` at `0x14000cdd6`
- `KERNEL32!CreateEventW` at `0x14000cdd6`
- `KERNEL32!HeapSetInformation` at `0x14000ca86`
- `KERNEL32!HeapSetInformation` at `0x14000ca86`
- `KERNEL32!GetLastError` at `0x14000cf29`
- `KERNEL32!GetLastError` at `0x14000cf29`
- `KERNEL32!WaitForSingleObject` at `0x14000cec8`
- `KERNEL32!WaitForSingleObject` at `0x14000cec8`
- `KERNEL32!ReleaseActCtx` at `0x14000cee5`
- `KERNEL32!ReleaseActCtx` at `0x14000cee5`
- `msvcrt!_wcsnicmp` at `0x14000cac5`
- `msvcrt!_wcsnicmp` at `0x14000caee`
- `msvcrt!_wcsnicmp` at `0x14000cb12`
- `msvcrt!_wcsnicmp` at `0x14000cb36`
- `msvcrt!_wcsnicmp` at `0x14000cb5a`
- `msvcrt!_wcsnicmp` at `0x14000cb7a`
- `msvcrt!_wcsnicmp` at `0x14000cbb3`
- `msvcrt!_wcsnicmp` at `0x14000cac5`
- `msvcrt!_wcsnicmp` at `0x14000caee`
- `msvcrt!_wcsnicmp` at `0x14000cb12`
- `msvcrt!_wcsnicmp` at `0x14000cb36`
- `msvcrt!_wcsnicmp` at `0x14000cb5a`
- `msvcrt!_wcsnicmp` at `0x14000cb7a`
- `msvcrt!_wcsnicmp` at `0x14000cbb3`
- `msvcrt!wcstok_s` at `0x14000ca9d`
- `msvcrt!wcstok_s` at `0x14000cbf5`
- `msvcrt!wcstok_s` at `0x14000ca9d`
- `msvcrt!wcstok_s` at `0x14000cbf5`
- `msvcrt!_wtoi` at `0x14000cbc7`
- `msvcrt!_wtoi` at `0x14000cbc7`
- `ole32!CoUninitialize` at `0x14000cf08`
- `ole32!CoUninitialize` at `0x14000cf08`
- `ole32!StringFromGUID2` at `0x14000ccb6`
- `ole32!StringFromGUID2` at `0x14000cd21`
- `ole32!StringFromGUID2` at `0x14000ccb6`
- `ole32!StringFromGUID2` at `0x14000cd21`
- `ole32!CoInitializeSecurity` at `0x14000ce4b`
- `ole32!CoInitializeSecurity` at `0x14000ce4b`
- `ole32!CLSIDFromString` at `0x14000cb95`
- `ole32!CLSIDFromString` at `0x14000cb95`
- `ole32!CoInitializeEx` at `0x14000cdf6`
- `ole32!CoInitializeEx` at `0x14000cdf6`

## string_xrefs

- `0x14000cc7f`: `CLSID`
- `0x14000cb70`: `-CLSID:`
- `0x14000ce6b`: `user32.dll`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  int v4; // esi
  LSTATUS v7; // edi
  int v8; // r15d
  int v9; // r12d
  int v10; // r14d
  wchar_t *v11; // rbx
  LSTATUS v12; // ebx
  const unsigned __int16 *v13; // rcx
  HMODULE Library; // rax
  HMODULE v15; // rbx
  void (*ProcAddress)(void); // rax
  signed int LastError; // eax
  HKEY hKey; // [rsp+50h] [rbp-89h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-81h] BYREF
  wchar_t *Context[2]; // [rsp+60h] [rbp-79h] BYREF
  GUID rguid; // [rsp+70h] [rbp-69h] BYREF
  GUID v23; // [rsp+80h] [rbp-59h] BYREF
  wchar_t Delimiter[8]; // [rsp+90h] [rbp-49h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-39h] BYREF

  v4 = 0;
  wcscpy(Delimiter, L" ,\t\n");
  Context[0] = 0;
  g_clsid = GUID_NULL;
  v7 = -2147024809;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  v11 = wcstok_s(lpCmdLine, Delimiter, Context);
  if ( v11 )
  {
    do
    {
      if ( _wcsnicmp(v11, L"-Embedding", 0xBu) )
      {
        if ( _wcsnicmp(v11, L"/REGSERVER", 0xBu) && _wcsnicmp(v11, L"-REGSERVER", 0xBu) )
        {
          if ( _wcsnicmp(v11, L"/UNREGSERVER", 0xDu) && _wcsnicmp(v11, L"-UNREGSERVER", 0xDu) )
          {
            if ( _wcsnicmp(v11, L"-CLSID:", 7u) )
            {
              if ( !_wcsnicmp(v11, L"-PID:", 5u) )
                g_dwIntegrity = _wtoi(v11 + 5);
            }
            else
            {
              CLSIDFromString(v11 + 7, &g_clsid);
            }
          }
          else
          {
            v9 = 1;
          }
        }
        else
        {
          v8 = 1;
        }
      }
      else
      {
        v10 = 1;
      }
      ++v4;
      v11 = wcstok_s(0, Delimiter, Context);
    }
    while ( v11 );
    if ( v4 == 1 || v4 == 2 && memcmp_0(&g_clsid, &GUID_NULL, 0x10u) )
    {
      if ( v9 )
      {
        hKey = 0;
        phkResult = 0;
        v23 = (GUID)xmmword_140012D50;
        rguid = CLSID_CIeAxiInstaller;
        v7 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0xF003Fu, &hKey);
        if ( !v7 )
        {
          StringFromGUID2(&rguid, sz, 39);
          v7 = RegDeleteKeyW(hKey, sz);
          RegCloseKey(hKey);
        }
        v12 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"AppID", 0, 0xF003Fu, &phkResult);
        if ( !v12 )
        {
          StringFromGUID2(&v23, sz, 39);
          v12 = RegDeleteKeyW(phkResult, sz);
          RegCloseKey(phkResult);
        }
        if ( v12 )
        {
          if ( v12 <= 0 )
            return v12;
          v7 = (unsigned __int16)v12;
        }
        else
        {
          if ( !v7 )
            return 0;
          if ( v7 <= 0 )
            return v7;
          v7 = (unsigned __int16)v7;
        }
        return v7 | 0x80070000;
      }
      if ( v8 )
      {
        v23 = (GUID)xmmword_140012D50;
        rguid = CLSID_CIeAxiInstaller;
        v7 = RegisterLocalServer(&rguid, &v23);
        if ( v7 >= 0 )
          return RegisterProxyDll(v13);
      }
      else
      {
        if ( !v10 )
          return v7;
        g_hQuitEvent = CreateEventW(0, 1, 0, 0);
        if ( !g_hQuitEvent )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError <= 0 )
            return v7;
          v7 = (unsigned __int16)LastError;
          return v7 | 0x80070000;
        }
        v7 = CoInitializeEx(0, 0);
        if ( v7 >= 0 )
        {
          if ( (unsigned int)SHFusionInitializeFromModuleID(hInstance) )
          {
            v7 = CoInitializeSecurity(0, -1, 0, 0, 2u, 3u, 0, 0, 0);
            if ( v7 >= 0 )
            {
              v7 = RegisterClassFactory();
              if ( v7 >= 0 )
              {
                Library = LoadLibraryExW(L"user32.dll", 0, 0);
                v15 = Library;
                if ( Library )
                {
                  ProcAddress = (void (*)(void))GetProcAddress(Library, "SetProcessDPIAware");
                  if ( ProcAddress )
                    ProcAddress();
                  FreeLibrary(v15);
                }
                v7 = CleanupTempDirs();
                WaitForSingleObject(g_hQuitEvent, 0xFFFFFFFF);
                RevokeClassFactory();
              }
            }
            if ( g_hActCtx != (HANDLE)-1LL )
            {
              ReleaseActCtx(g_hActCtx);
              g_hActCtx = (HANDLE)-1LL;
            }
            if ( hModule )
              hModule = (HMODULE)-1LL;
          }
          CoUninitialize();
        }
        CloseHandle(g_hQuitEvent);
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14000ca10  mov     [rsp-8+arg_8], rbx
0x14000ca15  push    rbp
0x14000ca16  push    rsi
0x14000ca17  push    rdi
0x14000ca18  push    r12
0x14000ca1a  push    r13
0x14000ca1c  push    r14
0x14000ca1e  push    r15
0x14000ca20  lea     rbp, [rsp-27h]
0x14000ca25  sub     rsp, 100h
0x14000ca2c  mov     rax, cs:__security_cookie
0x14000ca33  xor     rax, rsp
0x14000ca36  mov     [rbp+57h+var_40], rax
0x14000ca3a  movsd   xmm0, qword ptr cs:asc_1400134D8; " ,\t\n"
0x14000ca42  xor     esi, esi
0x14000ca44  movzx   eax, word ptr cs:asc_1400134D8+8; ""
0x14000ca4b  mov     rbx, r8
0x14000ca4e  movsd   qword ptr [rbp+57h+Delimiter], xmm0
0x14000ca53  mov     r13, rcx
0x14000ca56  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14000ca5d  xor     r9d, r9d; HeapInformationLength
0x14000ca60  mov     [rbp+57h+Context], rsi
0x14000ca64  xor     r8d, r8d; HeapInformation
0x14000ca67  mov     [rbp+57h+var_98], ax
0x14000ca6b  lea     edx, [rsi+1]; HeapInformationClass
0x14000ca6e  xor     ecx, ecx; HeapHandle
0x14000ca70  movdqu  xmmword ptr cs:?g_clsid@@3U_GUID@@A.Data1, xmm0; _GUID g_clsid ...
0x14000ca78  mov     edi, 80070057h
0x14000ca7d  xor     r15d, r15d
0x14000ca80  xor     r12d, r12d
0x14000ca83  xor     r14d, r14d
0x14000ca86  call    cs:__imp_HeapSetInformation
0x14000ca8d  nop     dword ptr [rax+rax+00h]
0x14000ca92  lea     r8, [rbp+57h+Context]; Context
0x14000ca96  mov     rcx, rbx; String
0x14000ca99  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x14000ca9d  call    cs:__imp_wcstok_s
0x14000caa4  nop     dword ptr [rax+rax+00h]
0x14000caa9  mov     rbx, rax
0x14000caac  test    rax, rax
0x14000caaf  jz      loc_14000CF44
0x14000cab5  mov     r8d, 0Bh; MaxCount
0x14000cabb  lea     rdx, aEmbedding; "-Embedding"
0x14000cac2  mov     rcx, rbx; String1
0x14000cac5  call    cs:__imp__wcsnicmp
0x14000cacc  nop     dword ptr [rax+rax+00h]
0x14000cad1  test    eax, eax
0x14000cad3  jnz     short loc_14000CADE
0x14000cad5  lea     r14d, [rax+1]
0x14000cad9  jmp     loc_14000CBE9
0x14000cade  mov     r8d, 0Bh; MaxCount
0x14000cae4  lea     rdx, aRegserver_1; "/REGSERVER"
0x14000caeb  mov     rcx, rbx; String1
0x14000caee  call    cs:__imp__wcsnicmp
0x14000caf5  nop     dword ptr [rax+rax+00h]
0x14000cafa  test    eax, eax
0x14000cafc  jz      loc_14000CBE3
0x14000cb02  mov     r8d, 0Bh; MaxCount
0x14000cb08  lea     rdx, aRegserver; "-REGSERVER"
0x14000cb0f  mov     rcx, rbx; String1
0x14000cb12  call    cs:__imp__wcsnicmp
0x14000cb19  nop     dword ptr [rax+rax+00h]
0x14000cb1e  test    eax, eax
0x14000cb20  jz      loc_14000CBE3
0x14000cb26  mov     r8d, 0Dh; MaxCount
0x14000cb2c  lea     rdx, aUnregserver; "/UNREGSERVER"
0x14000cb33  mov     rcx, rbx; String1
0x14000cb36  call    cs:__imp__wcsnicmp
0x14000cb3d  nop     dword ptr [rax+rax+00h]
0x14000cb42  test    eax, eax
0x14000cb44  jz      loc_14000CBDB
0x14000cb4a  mov     r8d, 0Dh; MaxCount
0x14000cb50  lea     rdx, aUnregserver_0; "-UNREGSERVER"
0x14000cb57  mov     rcx, rbx; String1
0x14000cb5a  call    cs:__imp__wcsnicmp
0x14000cb61  nop     dword ptr [rax+rax+00h]
0x14000cb66  test    eax, eax
0x14000cb68  jz      short loc_14000CBDB
0x14000cb6a  mov     r8d, 7; MaxCount
0x14000cb70  lea     rdx, aClsid; "-CLSID:"
0x14000cb77  mov     rcx, rbx; String1
0x14000cb7a  call    cs:__imp__wcsnicmp
0x14000cb81  nop     dword ptr [rax+rax+00h]
0x14000cb86  test    eax, eax
0x14000cb88  jnz     short loc_14000CBA3
0x14000cb8a  lea     rcx, [rbx+0Eh]; lpsz
0x14000cb8e  lea     rdx, ?g_clsid@@3U_GUID@@A; pclsid
0x14000cb95  call    cs:__imp_CLSIDFromString
0x14000cb9c  nop     dword ptr [rax+rax+00h]
0x14000cba1  jmp     short loc_14000CBE9
0x14000cba3  mov     r8d, 5; MaxCount
0x14000cba9  lea     rdx, aPid; "-PID:"
0x14000cbb0  mov     rcx, rbx; String1
0x14000cbb3  call    cs:__imp__wcsnicmp
0x14000cbba  nop     dword ptr [rax+rax+00h]
0x14000cbbf  test    eax, eax
0x14000cbc1  jnz     short loc_14000CBE9
0x14000cbc3  lea     rcx, [rbx+0Ah]; String
0x14000cbc7  call    cs:__imp__wtoi
0x14000cbce  nop     dword ptr [rax+rax+00h]
0x14000cbd3  mov     cs:?g_dwIntegrity@@3KA, eax; ulong g_dwIntegrity
0x14000cbd9  jmp     short loc_14000CBE9
0x14000cbdb  mov     r12d, 1
0x14000cbe1  jmp     short loc_14000CBE9
0x14000cbe3  mov     r15d, 1
0x14000cbe9  lea     r8, [rbp+57h+Context]; Context
0x14000cbed  xor     ecx, ecx; String
0x14000cbef  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x14000cbf3  inc     esi
0x14000cbf5  call    cs:__imp_wcstok_s
0x14000cbfc  nop     dword ptr [rax+rax+00h]
0x14000cc01  mov     rbx, rax
0x14000cc04  test    rax, rax
0x14000cc07  jnz     loc_14000CAB5
0x14000cc0d  lea     ebx, [rax+1]
0x14000cc10  cmp     esi, ebx
0x14000cc12  jz      short loc_14000CC40
0x14000cc14  cmp     esi, 2
0x14000cc17  jnz     loc_14000CF44
0x14000cc1d  lea     r8d, [rax+10h]; Size
0x14000cc21  lea     rdx, GUID_NULL; Buf2
0x14000cc28  lea     rcx, ?g_clsid@@3U_GUID@@A; Buf1
0x14000cc2f  call    memcmp_0
0x14000cc34  xor     esi, esi
0x14000cc36  test    eax, eax
0x14000cc38  jz      loc_14000CF44
0x14000cc3e  jmp     short loc_14000CC42
0x14000cc40  xor     esi, esi
0x14000cc42  test    r12d, r12d
0x14000cc45  jz      loc_14000CD83
0x14000cc4b  movups  xmm0, cs:xmmword_140012D50
0x14000cc52  lea     rax, [rsp+130h+hKey]
0x14000cc57  mov     ebx, 0F003Fh
0x14000cc5c  movups  xmm1, xmmword ptr cs:CLSID_CIeAxiInstaller.Data1
0x14000cc63  mov     r15, 0FFFFFFFF80000000h
0x14000cc6a  mov     [rsp+130h+hKey], rsi
0x14000cc6f  mov     r9d, ebx; samDesired
0x14000cc72  mov     [rsp+130h+var_D8], rsi
0x14000cc77  xor     r8d, r8d; ulOptions
0x14000cc7a  mov     [rsp+130h+phkResult], rax; phkResult
0x14000cc7f  lea     rdx, aClsid_0; "CLSID"
0x14000cc86  mov     rcx, r15; hKey
0x14000cc89  movdqu  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x14000cc8e  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm1
0x14000cc93  call    cs:__imp_RegOpenKeyExW
0x14000cc9a  nop     dword ptr [rax+rax+00h]
0x14000cc9f  mov     edi, eax
0x14000cca1  mov     r14d, 27h ; '''
0x14000cca7  test    eax, eax
0x14000cca9  jnz     short loc_14000CCEA
0x14000ccab  mov     r8d, r14d; cchMax
0x14000ccae  lea     rdx, [rbp+57h+sz]; lpsz
0x14000ccb2  lea     rcx, [rbp+57h+rguid]; rguid
0x14000ccb6  call    cs:__imp_StringFromGUID2
0x14000ccbd  nop     dword ptr [rax+rax+00h]
0x14000ccc2  mov     rcx, [rsp+130h+hKey]; hKey
0x14000ccc7  lea     rdx, [rbp+57h+sz]; lpSubKey
0x14000cccb  call    cs:__imp_RegDeleteKeyW
0x14000ccd2  nop     dword ptr [rax+rax+00h]
0x14000ccd7  mov     rcx, [rsp+130h+hKey]; hKey
0x14000ccdc  mov     edi, eax
0x14000ccde  call    cs:__imp_RegCloseKey
0x14000cce5  nop     dword ptr [rax+rax+00h]
0x14000ccea  lea     rax, [rsp+130h+var_D8]
0x14000ccef  mov     r9d, ebx; samDesired
0x14000ccf2  xor     r8d, r8d; ulOptions
0x14000ccf5  mov     [rsp+130h+phkResult], rax; phkResult
0x14000ccfa  lea     rdx, aAppid; "AppID"
0x14000cd01  mov     rcx, r15; hKey
0x14000cd04  call    cs:__imp_RegOpenKeyExW
0x14000cd0b  nop     dword ptr [rax+rax+00h]
0x14000cd10  mov     ebx, eax
0x14000cd12  test    eax, eax
0x14000cd14  jnz     short loc_14000CD55
0x14000cd16  mov     r8d, r14d; cchMax
0x14000cd19  lea     rdx, [rbp+57h+sz]; lpsz
0x14000cd1d  lea     rcx, [rbp+57h+var_B0]; rguid
0x14000cd21  call    cs:__imp_StringFromGUID2
0x14000cd28  nop     dword ptr [rax+rax+00h]
0x14000cd2d  mov     rcx, [rsp+130h+var_D8]; hKey
0x14000cd32  lea     rdx, [rbp+57h+sz]; lpSubKey
0x14000cd36  call    cs:__imp_RegDeleteKeyW
0x14000cd3d  nop     dword ptr [rax+rax+00h]
0x14000cd42  mov     rcx, [rsp+130h+var_D8]; hKey
0x14000cd47  mov     ebx, eax
0x14000cd49  call    cs:__imp_RegCloseKey
0x14000cd50  nop     dword ptr [rax+rax+00h]
0x14000cd55  test    ebx, ebx
0x14000cd57  jnz     short loc_14000CD72
0x14000cd59  test    edi, edi
0x14000cd5b  jnz     short loc_14000CD64
0x14000cd5d  mov     edi, esi
0x14000cd5f  jmp     loc_14000CF44
0x14000cd64  jle     loc_14000CF44
0x14000cd6a  movzx   edi, di
0x14000cd6d  jmp     loc_14000CF3E
0x14000cd72  jg      short loc_14000CD7B
0x14000cd74  mov     edi, ebx
0x14000cd76  jmp     loc_14000CF44
0x14000cd7b  movzx   edi, bx
0x14000cd7e  jmp     loc_14000CF3E
0x14000cd83  test    r15d, r15d
0x14000cd86  jz      short loc_14000CDC3
0x14000cd88  movups  xmm0, cs:xmmword_140012D50
0x14000cd8f  lea     rdx, [rbp+57h+var_B0]; GUID *
0x14000cd93  movups  xmm1, xmmword ptr cs:CLSID_CIeAxiInstaller.Data1
0x14000cd9a  lea     rcx, [rbp+57h+rguid]; rguid
0x14000cd9e  movdqu  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x14000cda3  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm1
0x14000cda8  call    ?RegisterLocalServer@@YAJU_GUID@@U1@@Z; RegisterLocalServer(_GUID,_GUID)
0x14000cdad  mov     edi, eax
0x14000cdaf  test    eax, eax
0x14000cdb1  js      loc_14000CF44
0x14000cdb7  call    ?RegisterProxyDll@@YAJPEBG@Z; RegisterProxyDll(ushort const *)
0x14000cdbc  mov     edi, eax
0x14000cdbe  jmp     loc_14000CF44
0x14000cdc3  test    r14d, r14d
0x14000cdc6  jz      loc_14000CF44
0x14000cdcc  xor     r9d, r9d; lpName
0x14000cdcf  xor     r8d, r8d; bInitialState
0x14000cdd2  mov     edx, ebx; bManualReset
0x14000cdd4  xor     ecx, ecx; lpEventAttributes
0x14000cdd6  call    cs:__imp_CreateEventW
0x14000cddd  nop     dword ptr [rax+rax+00h]
0x14000cde2  mov     cs:?g_hQuitEvent@@3PEAXEA, rax; void * g_hQuitEvent
0x14000cde9  test    rax, rax
0x14000cdec  jz      loc_14000CF29
0x14000cdf2  xor     edx, edx; dwCoInit
0x14000cdf4  xor     ecx, ecx; pvReserved
0x14000cdf6  call    cs:__imp_CoInitializeEx
0x14000cdfd  nop     dword ptr [rax+rax+00h]
0x14000ce02  mov     edi, eax
0x14000ce04  test    eax, eax
0x14000ce06  js      loc_14000CF14
0x14000ce0c  mov     edx, ebx
0x14000ce0e  mov     rcx, r13; hModule
0x14000ce11  call    SHFusionInitializeFromModuleID
0x14000ce16  test    eax, eax
0x14000ce18  jz      loc_14000CF08
0x14000ce1e  mov     [rsp+130h+pReserved3], rsi; pReserved3
0x14000ce23  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000ce27  mov     [rsp+130h+dwCapabilities], esi; dwCapabilities
0x14000ce2b  xor     r9d, r9d; pReserved1
0x14000ce2e  mov     [rsp+130h+pAuthList], rsi; pAuthList
0x14000ce33  xor     r8d, r8d; asAuthSvc
0x14000ce36  mov     [rsp+130h+dwImpLevel], 3; dwImpLevel
0x14000ce3e  mov     edx, r14d; cAuthSvc
0x14000ce41  xor     ecx, ecx; pSecDesc
0x14000ce43  mov     dword ptr [rsp+130h+phkResult], 2; dwAuthnLevel
0x14000ce4b  call    cs:__imp_CoInitializeSecurity
0x14000ce52  nop     dword ptr [rax+rax+00h]
0x14000ce57  mov     edi, eax
0x14000ce59  test    eax, eax
0x14000ce5b  js      short loc_14000CED9
0x14000ce5d  call    ?RegisterClassFactory@@YAJXZ; RegisterClassFactory(void)
0x14000ce62  mov     edi, eax
0x14000ce64  test    eax, eax
0x14000ce66  js      short loc_14000CED9
0x14000ce68  xor     r8d, r8d; dwFlags
0x14000ce6b  lea     rcx, aUser32Dll_0; "user32.dll"
0x14000ce72  xor     edx, edx; hFile
0x14000ce74  call    cs:__imp_LoadLibraryExW
0x14000ce7b  nop     dword ptr [rax+rax+00h]
0x14000ce80  mov     rbx, rax
0x14000ce83  test    rax, rax
0x14000ce86  jz      short loc_14000CEB7
0x14000ce88  lea     rdx, aSetprocessdpia; "SetProcessDPIAware"
0x14000ce8f  mov     rcx, rax; hModule
0x14000ce92  call    cs:__imp_GetProcAddress
0x14000ce99  nop     dword ptr [rax+rax+00h]
0x14000ce9e  test    rax, rax
0x14000cea1  jz      short loc_14000CEA8
0x14000cea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cea8  mov     rcx, rbx; hLibModule
0x14000ceab  call    cs:__imp_FreeLibrary
0x14000ceb2  nop     dword ptr [rax+rax+00h]
0x14000ceb7  call    ?CleanupTempDirs@@YAJXZ; CleanupTempDirs(void)
0x14000cebc  mov     rcx, cs:?g_hQuitEvent@@3PEAXEA; hHandle
0x14000cec3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000cec6  mov     edi, eax
0x14000cec8  call    cs:__imp_WaitForSingleObject
0x14000cecf  nop     dword ptr [rax+rax+00h]
0x14000ced4  call    ?RevokeClassFactory@@YAJXZ; RevokeClassFactory(void)
0x14000ced9  mov     rcx, cs:g_hActCtx; hActCtx
0x14000cee0  cmp     rcx, r14
0x14000cee3  jz      short loc_14000CEF8
0x14000cee5  call    cs:__imp_ReleaseActCtx
0x14000ceec  nop     dword ptr [rax+rax+00h]
0x14000cef1  mov     cs:g_hActCtx, r14
0x14000cef8  cmp     cs:hModule, rsi
0x14000ceff  jz      short loc_14000CF08
0x14000cf01  mov     cs:hModule, r14
0x14000cf08  call    cs:__imp_CoUninitialize
0x14000cf0f  nop     dword ptr [rax+rax+00h]
0x14000cf14  mov     rcx, cs:?g_hQuitEvent@@3PEAXEA; hObject
0x14000cf1b  call    cs:__imp_CloseHandle
0x14000cf22  nop     dword ptr [rax+rax+00h]
0x14000cf27  jmp     short loc_14000CF44
0x14000cf29  call    cs:__imp_GetLastError
0x14000cf30  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
