# CreateAppContainerEnumerator

- ea: `0x180002650`
- end: `0x180002a86`
- name: `CreateAppContainerEnumerator`
- size: `1078`
- prototype: `__int64 __fastcall(void *, wil::details **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800023d8`
- `0x180002650`
- `0x180002a8c`
- `0x180003fdc`
- `0x180004990`
- `0x180004c10`
- `0x180005b60`
- `0x180005b90`
- `0x18000608c`
- `0x1800064b0`
- `0x18000a214`
- `0x18000dc34`
- `0x18000f0b8`
- `0x18000f13c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800026c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800026c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027fa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002699`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002699`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002825`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002825`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180002834`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180002834`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002681`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002681`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000286b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002950`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000286b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002950`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a7b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002783`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002783`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800027bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800028ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002925`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800027bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800028ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002925`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800028c6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800028c6`

## pseudocode

```c
__int64 __fastcall CreateAppContainerEnumerator(void *a1, wil::details **a2)
{
  HANDLE CurrentThread; // rax
  HANDLE ProcessHeap; // rax
  wil::details *v6; // rdi
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9
  int SidString; // eax
  HLOCAL v12; // rbx
  int v13; // eax
  unsigned int v14; // r14d
  unsigned int v15; // eax
  unsigned int v16; // esi
  void *v17; // rdx
  DWORD LastError; // eax
  void *v19; // rbx
  HANDLE CurrentProcess; // rax
  const char *v21; // r9
  int IsChildAppContainerSid; // eax
  const char *v23; // r9
  int v24; // eax
  unsigned int v25; // esi
  void *v26; // rdx
  void *v27; // rdx
  void *v28; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-60h]
  unsigned int phkResulta; // [rsp+20h] [rbp-60h]
  LPCWSTR lpSubKey[3]; // [rsp+30h] [rbp-50h] BYREF
  HLOCAL hMem[3]; // [rsp+48h] [rbp-38h] BYREF
  LPWSTR StringSid[4]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  int v35; // [rsp+B8h] [rbp+38h] BYREF
  void *TokenHandle; // [rsp+C0h] [rbp+40h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      if ( LastError )
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xF0,
               (unsigned int)"minio\\profapi\\appcontainer.cpp",
               (const char *)LastError,
               phkResult);
      else
        v7 = 0;
      goto LABEL_6;
    }
    v19 = TokenHandle;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v35);
      CloseHandle(v19);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v35);
    }
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      v7 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xEC,
             (unsigned int)"minio\\profapi\\appcontainer.cpp",
             v21);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      return v7;
    }
  }
  if ( a1 )
  {
    v35 = 0;
    IsChildAppContainerSid = _IsChildAppContainerSid(a1, &v35);
    v7 = IsChildAppContainerSid;
    if ( IsChildAppContainerSid < 0 )
    {
      v9 = (unsigned int)IsChildAppContainerSid;
      v8 = 247;
      goto LABEL_5;
    }
    if ( v35 )
    {
      v7 = -2147024809;
      v8 = 248;
      v9 = 2147942487LL;
      goto LABEL_5;
    }
  }
  ProcessHeap = GetProcessHeap();
  v6 = (wil::details *)HeapAlloc(ProcessHeap, 8u, 0x10u);
  if ( !v6 )
  {
    v7 = -2147024882;
    v8 = 252;
    v9 = 2147942414LL;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"minio\\profapi\\appcontainer.cpp",
      (const char *)v9,
      phkResult);
LABEL_6:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v7;
  }
  hMem[0] = 0;
  hMem[1] = (HLOCAL)-1LL;
  hMem[2] = (HLOCAL)-1LL;
  SidString = GetSidString(TokenHandle, (unsigned __int16 **)hMem);
  v7 = SidString;
  if ( SidString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"minio\\profapi\\appcontainer.cpp",
      (const char *)(unsigned int)SidString,
      phkResult);
    goto LABEL_41;
  }
  v12 = hMem[0];
  memset(lpSubKey, 0, sizeof(lpSubKey));
  v13 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
          lpSubKey,
          L"%s\\Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppContainer\\Mappings\\",
          hMem[0]);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x105,
      (unsigned int)"minio\\profapi\\appcontainer.cpp",
      (const char *)(unsigned int)v13,
      phkResult);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(hMem);
    wil::details::FreeProcessHeap(v6, v27);
    v7 = v14;
    goto LABEL_6;
  }
  if ( a1 )
  {
    StringSid[0] = 0;
    StringSid[1] = (LPWSTR)-1LL;
    StringSid[2] = (LPWSTR)-1LL;
    if ( ConvertSidToStringSidW(a1, StringSid) )
    {
      v24 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
              lpSubKey,
              L"%s\\Children\\",
              StringSid[0]);
      v25 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10B,
          (unsigned int)"minio\\profapi\\appcontainer.cpp",
          (const char *)(unsigned int)v24,
          phkResult);
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(StringSid);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(hMem);
        wil::details::FreeProcessHeap(v6, v28);
        v7 = v25;
        goto LABEL_6;
      }
      if ( StringSid[0] )
        LocalFree(StringSid[0]);
      goto LABEL_11;
    }
    v7 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x10A,
           (unsigned int)"minio\\profapi\\appcontainer.cpp",
           v23);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(StringSid);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
LABEL_41:
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(hMem);
    wil::details::FreeProcessHeap(v6, v26);
    goto LABEL_6;
  }
LABEL_11:
  v15 = RegOpenKeyExW(HKEY_USERS, lpSubKey[0], 0, 0x20019u, (PHKEY)v6);
  if ( v15 )
  {
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x10E,
            (unsigned int)"minio\\profapi\\appcontainer.cpp",
            (const char *)v15,
            phkResulta);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
    if ( v12 )
      LocalFree(v12);
    wil::details::FreeProcessHeap(v6, v17);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return v16;
  }
  else
  {
    *((_DWORD *)v6 + 2) = 0;
    *a2 = v6;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
    if ( v12 )
      LocalFree(v12);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return 0;
  }
}

```

## disassembly

```asm
0x180002650  mov     [rsp-28h+arg_0], rbx
0x180002655  mov     [rsp-28h+arg_18], rsi
0x18000265a  push    rbp
0x18000265b  push    rdi
0x18000265c  push    r13
0x18000265e  push    r14
0x180002660  push    r15
0x180002662  mov     rbp, rsp
0x180002665  sub     rsp, 80h
0x18000266c  mov     r15, rdx
0x18000266f  mov     qword ptr [rdx], 0
0x180002676  mov     rsi, rcx
0x180002679  mov     [rbp+TokenHandle], 0
0x180002681  call    cs:__imp_GetCurrentThread
0x180002687  mov     edi, 8
0x18000268c  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180002690  mov     edx, edi; DesiredAccess
0x180002692  mov     rcx, rax; ThreadHandle
0x180002695  lea     r8d, [rdi-7]; OpenAsSelf
0x180002699  call    cs:__imp_OpenThreadToken
0x18000269f  test    eax, eax
0x1800026a1  jz      loc_1800027FA
0x1800026a7  test    rsi, rsi
0x1800026aa  jnz     loc_180002876
0x1800026b0  call    cs:__imp_GetProcessHeap
0x1800026b6  mov     r8d, 10h; dwBytes
0x1800026bc  mov     edx, edi; dwFlags
0x1800026be  mov     rcx, rax; hHeap
0x1800026c1  call    cs:__imp_HeapAlloc
0x1800026c7  mov     rdi, rax
0x1800026ca  test    rax, rax
0x1800026cd  jnz     short loc_1800026FC
0x1800026cf  mov     ebx, 8007000Eh
0x1800026d4  mov     edx, 0FCh; void *
0x1800026d9  mov     r9d, ebx; char *
0x1800026dc  mov     rcx, [rbp+28h]; this
0x1800026e0  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x1800026e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800026ec  lea     rcx, [rbp+TokenHandle]
0x1800026f0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800026f5  mov     eax, ebx
0x1800026f7  jmp     loc_1800027DE
0x1800026fc  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180002700  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x180002704  or      r13, 0FFFFFFFFFFFFFFFFh
0x180002708  mov     [rbp+hMem], 0
0x180002710  mov     [rbp+var_30], r13
0x180002714  mov     [rbp+var_28], r13
0x180002718  call    ?GetSidString@@YAJPEAXPEAPEAG@Z; GetSidString(void *,ushort * *)
0x18000271d  mov     ebx, eax
0x18000271f  test    eax, eax
0x180002721  js      loc_18000299B
0x180002727  mov     rbx, [rbp+hMem]
0x18000272b  lea     rdx, aSSoftwareClass; "%s\\Software\\Classes\\Local Settings\\"...
0x180002732  mov     r8, rbx
0x180002735  mov     [rbp+lpSubKey], 0
0x18000273d  lea     rcx, [rbp+lpSubKey]
0x180002741  mov     [rbp+var_48], 0
0x180002749  mov     [rbp+var_40], 0
0x180002751  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180002756  mov     r14d, eax
0x180002759  test    eax, eax
0x18000275b  js      loc_1800029F4
0x180002761  test    rsi, rsi
0x180002764  jnz     loc_1800028AF
0x18000276a  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18000276e  mov     r9d, 20019h; samDesired
0x180002774  xor     r8d, r8d; ulOptions
0x180002777  mov     qword ptr [rsp+80h+phkResult], rdi; unsigned int
0x18000277c  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180002783  call    cs:__imp_RegOpenKeyExW
0x180002789  test    eax, eax
0x18000278b  jz      loc_18000290A
0x180002791  mov     rcx, [rbp+28h]; this
0x180002795  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x18000279c  mov     r9d, eax; char *
0x18000279f  mov     edx, 10Eh; void *
0x1800027a4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800027a9  lea     rcx, [rbp+lpSubKey]
0x1800027ad  mov     esi, eax
0x1800027af  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800027b4  test    rbx, rbx
0x1800027b7  jz      short loc_1800027C2
0x1800027b9  mov     rcx, rbx; hMem
0x1800027bc  call    cs:__imp_LocalFree
0x1800027c2  mov     rcx, rdi; this
0x1800027c5  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800027ca  mov     rcx, [rbp+TokenHandle]; hObject
0x1800027ce  lea     rdx, [rcx-1]
0x1800027d2  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800027d6  jbe     loc_180002A70
0x1800027dc  mov     eax, esi
0x1800027de  lea     r11, [rsp+80h+var_s0]
0x1800027e6  mov     rbx, [r11+30h]
0x1800027ea  mov     rsi, [r11+48h]
0x1800027ee  mov     rsp, r11
0x1800027f1  pop     r15
0x1800027f3  pop     r14
0x1800027f5  pop     r13
0x1800027f7  pop     rdi
0x1800027f8  pop     rbp
0x1800027f9  retn
0x1800027fa  call    cs:__imp_GetLastError
0x180002800  cmp     eax, 3F0h
0x180002805  jnz     loc_180002964
0x18000280b  mov     rbx, [rbp+TokenHandle]
0x18000280f  lea     rax, [rbx-1]
0x180002813  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002817  jbe     loc_180002944
0x18000281d  mov     [rbp+TokenHandle], 0
0x180002825  call    cs:__imp_GetCurrentProcess
0x18000282b  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000282f  mov     edx, edi; DesiredAccess
0x180002831  mov     rcx, rax; ProcessHandle
0x180002834  call    cs:__imp_OpenProcessToken
0x18000283a  test    eax, eax
0x18000283c  jnz     loc_1800026A7
0x180002842  mov     rcx, [rbp+28h]; this
0x180002846  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x18000284d  mov     edx, 0ECh; void *
0x180002852  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180002857  mov     rcx, [rbp+TokenHandle]; hObject
0x18000285b  mov     ebx, eax
0x18000285d  lea     rdx, [rcx-1]
0x180002861  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180002865  ja      loc_1800026F5
0x18000286b  call    cs:__imp_CloseHandle
0x180002871  jmp     loc_1800026F5
0x180002876  lea     rdx, [rbp+arg_8]; int *
0x18000287a  mov     [rbp+arg_8], 0
0x180002881  mov     rcx, rsi; void *
0x180002884  call    ?_IsChildAppContainerSid@@YAJQEAXPEAH@Z; _IsChildAppContainerSid(void * const,int *)
0x180002889  mov     ebx, eax
0x18000288b  test    eax, eax
0x18000288d  js      loc_18000298E
0x180002893  cmp     [rbp+arg_8], 0
0x180002897  jz      loc_1800026B0
0x18000289d  mov     ebx, 80070057h
0x1800028a2  mov     edx, 0F8h
0x1800028a7  mov     r9d, ebx
0x1800028aa  jmp     loc_1800026DC
0x1800028af  lea     rdx, [rbp+StringSid]; StringSid
0x1800028b3  mov     [rbp+StringSid], 0
0x1800028bb  mov     rcx, rsi; Sid
0x1800028be  mov     [rbp+var_18], r13
0x1800028c2  mov     [rbp+var_10], r13
0x1800028c6  call    cs:__imp_ConvertSidToStringSidW
0x1800028cc  test    eax, eax
0x1800028ce  jz      loc_1800029B5
0x1800028d4  mov     r8, [rbp+StringSid]
0x1800028d8  lea     rdx, aSChildren; "%s\\Children\\"
0x1800028df  lea     rcx, [rbp+lpSubKey]
0x1800028e3  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x1800028e8  mov     esi, eax
0x1800028ea  test    eax, eax
0x1800028ec  js      loc_180002A2E
0x1800028f2  mov     rcx, [rbp+StringSid]; hMem
0x1800028f6  test    rcx, rcx
0x1800028f9  jz      loc_18000276A
0x1800028ff  call    cs:__imp_LocalFree
0x180002905  jmp     loc_18000276A
0x18000290a  mov     dword ptr [rdi+8], 0
0x180002911  lea     rcx, [rbp+lpSubKey]
0x180002915  mov     [r15], rdi
0x180002918  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000291d  test    rbx, rbx
0x180002920  jz      short loc_18000292B
0x180002922  mov     rcx, rbx; hMem
0x180002925  call    cs:__imp_LocalFree
0x18000292b  mov     rcx, [rbp+TokenHandle]; hObject
0x18000292f  lea     rax, [rcx-1]
0x180002933  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002937  jbe     loc_180002A7B
0x18000293d  xor     eax, eax
0x18000293f  jmp     loc_1800027DE
0x180002944  lea     rcx, [rbp+arg_8]; this
0x180002948  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000294d  mov     rcx, rbx; hObject
0x180002950  call    cs:__imp_CloseHandle
0x180002956  lea     rcx, [rbp+arg_8]; this
0x18000295a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000295f  jmp     loc_18000281D
0x180002964  test    eax, eax
0x180002966  jz      short loc_180002987
0x180002968  mov     rcx, [rbp+28h]; this
0x18000296c  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180002973  mov     r9d, eax; char *
0x180002976  mov     edx, 0F0h; void *
0x18000297b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002980  mov     ebx, eax
0x180002982  jmp     loc_1800026EC
0x180002987  xor     ebx, ebx
0x180002989  jmp     loc_1800026EC
0x18000298e  mov     r9d, eax
0x180002991  mov     edx, 0F7h
0x180002996  jmp     loc_1800026DC
0x18000299b  mov     rcx, [rbp+28h]; this
0x18000299f  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x1800029a6  mov     r9d, eax; char *
0x1800029a9  mov     edx, 100h; void *
0x1800029ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800029b3  jmp     short loc_1800029DE
0x1800029b5  mov     rcx, [rbp+28h]; this
0x1800029b9  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x1800029c0  mov     edx, 10Ah; void *
0x1800029c5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800029ca  lea     rcx, [rbp+StringSid]
0x1800029ce  mov     ebx, eax
0x1800029d0  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1800029d5  lea     rcx, [rbp+lpSubKey]
0x1800029d9  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800029de  lea     rcx, [rbp+hMem]
0x1800029e2  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1800029e7  mov     rcx, rdi; this
0x1800029ea  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800029ef  jmp     loc_1800026EC
0x1800029f4  mov     rcx, [rbp+28h]; this
0x1800029f8  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x1800029ff  mov     r9d, r14d; char *
0x180002a02  mov     edx, 105h; void *
0x180002a07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002a0c  lea     rcx, [rbp+lpSubKey]
0x180002a10  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180002a15  lea     rcx, [rbp+hMem]
0x180002a19  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180002a1e  mov     rcx, rdi; this
0x180002a21  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180002a26  mov     ebx, r14d
0x180002a29  jmp     loc_1800026EC
0x180002a2e  mov     rcx, [rbp+28h]; this
0x180002a32  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180002a39  mov     r9d, esi; char *
0x180002a3c  mov     edx, 10Bh; void *
0x180002a41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002a46  lea     rcx, [rbp+StringSid]
0x180002a4a  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180002a4f  lea     rcx, [rbp+lpSubKey]
0x180002a53  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180002a58  lea     rcx, [rbp+hMem]
0x180002a5c  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180002a61  mov     rcx, rdi; this
0x180002a64  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180002a69  mov     ebx, esi
0x180002a6b  jmp     loc_1800026EC
0x180002a70  call    cs:__imp_CloseHandle
0x180002a76  jmp     loc_1800027DC
0x180002a7b  call    cs:__imp_CloseHandle
0x180002a81  jmp     loc_18000293D
```
