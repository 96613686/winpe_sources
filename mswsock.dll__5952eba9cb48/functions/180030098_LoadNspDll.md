# LoadNspDll

- ea: `0x180030098`
- end: `0x180030573`
- name: `LoadNspDll`
- size: `1243`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002ff9c`

## callees

- `0x1800119a0`
- `0x18001757c`
- `0x180030098`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180030162`
- `ntdll!RtlFreeHeap` at `0x18003022a`
- `ntdll!RtlFreeHeap` at `0x180030278`
- `ntdll!RtlFreeHeap` at `0x180030290`
- `ntdll!RtlFreeHeap` at `0x1800302d9`
- `ntdll!RtlFreeHeap` at `0x180030308`
- `ntdll!RtlFreeHeap` at `0x1800303fc`
- `ntdll!RtlFreeHeap` at `0x180030531`
- `ntdll!RtlFreeHeap` at `0x180030549`
- `ntdll!RtlFreeHeap` at `0x180030162`
- `ntdll!RtlFreeHeap` at `0x18003022a`
- `ntdll!RtlFreeHeap` at `0x180030278`
- `ntdll!RtlFreeHeap` at `0x180030290`
- `ntdll!RtlFreeHeap` at `0x1800302d9`
- `ntdll!RtlFreeHeap` at `0x180030308`
- `ntdll!RtlFreeHeap` at `0x1800303fc`
- `ntdll!RtlFreeHeap` at `0x180030531`
- `ntdll!RtlFreeHeap` at `0x180030549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030329`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030329`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030517`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800302b1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800302b1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800302ed`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800302ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030344`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030344`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003035b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800303b0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800303e4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003035b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800303b0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800303e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030212`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030318`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030559`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030212`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030318`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030559`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800301a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003025a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800301a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003025a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030148`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030148`

## string_xrefs

- `0x1800300fa`: `System\CurrentControlSet\Services\`
- `0x18003011a`: `\ServiceProvider`
- `0x180030253`: `ProviderPath`

## pseudocode

```c
DWORD __fastcall LoadNspDll(STRSAFE_LPCWSTR pszSrc)
{
  wchar_t *v2; // rax
  wchar_t *v3; // rbx
  LSTATUS v5; // edi
  DWORD LastError; // ebx
  void *v7; // rdi
  void *v8; // r14
  LSTATUS v9; // esi
  DWORD v10; // eax
  HMODULE Library; // rsi
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v13)(int *, __int64, DWORD *); // r14
  __int64 v14; // rax
  _DWORD *v15; // rdi
  int v16; // ebx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 **v19; // r8
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rcx
  unsigned int v23; // r8d
  __int64 v24; // rcx
  int v25; // r9d
  __int64 v26; // r10
  __int64 i; // rax
  __int64 *v28; // rcx
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF
  int v32; // [rsp+80h] [rbp+40h] BYREF
  int Data; // [rsp+88h] [rbp+48h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  v32 = 0;
  v2 = (wchar_t *)((__int64 (__fastcall *)(HANDLE, _QWORD, __int64))SockAllocateHeapRoutine)(SockPrivateHeap, 0, 520);
  v3 = v2;
  if ( !v2 )
    return 8;
  StringCbCopyW(v2, 0x208u, L"System\\CurrentControlSet\\Services\\");
  StringCbCatW(v3, 0x208u, pszSrc);
  StringCbCatW(v3, 0x208u, L"\\ServiceProvider");
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  RtlFreeHeap(SockPrivateHeap, 0, v3);
  if ( v5 )
    return v5;
  cbData = 4;
  LastError = RegQueryValueExW(hKey, L"Class", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( LastError )
    goto LABEL_52;
  LastError = 8;
  if ( (Data & 8) == 0 )
  {
    LastError = 50;
LABEL_52:
    RegCloseKey(hKey);
    return LastError;
  }
  v7 = (void *)((__int64 (__fastcall *)(HANDLE, _QWORD, __int64))SockAllocateHeapRoutine)(SockPrivateHeap, 0, 520);
  if ( !v7 )
    goto LABEL_52;
  v8 = (void *)((__int64 (__fastcall *)(HANDLE, _QWORD, __int64))SockAllocateHeapRoutine)(SockPrivateHeap, 0, 520);
  if ( !v8 )
  {
    RegCloseKey(hKey);
    RtlFreeHeap(SockPrivateHeap, 0, v7);
    return LastError;
  }
  cbData = 520;
  v9 = RegQueryValueExW(hKey, L"ProviderPath", 0, &Type, (LPBYTE)v7, &cbData);
  if ( v9 )
  {
    RtlFreeHeap(SockPrivateHeap, 0, v7);
    RtlFreeHeap(SockPrivateHeap, 0, v8);
    LastError = v9;
    goto LABEL_52;
  }
  v10 = ExpandEnvironmentStringsW((LPCWSTR)v7, (LPWSTR)v8, 0x104u);
  if ( !v10 )
  {
    LastError = GetLastError();
    goto LABEL_51;
  }
  if ( v10 > 0x104 )
  {
    LastError = 122;
LABEL_51:
    RtlFreeHeap(SockPrivateHeap, 0, v7);
    RtlFreeHeap(SockPrivateHeap, 0, v8);
    goto LABEL_52;
  }
  RtlFreeHeap(SockPrivateHeap, 0, v7);
  Library = LoadLibraryExW((LPCWSTR)v8, 0, 0);
  RtlFreeHeap(SockPrivateHeap, 0, v8);
  RegCloseKey(hKey);
  if ( !Library )
    return GetLastError();
  ProcAddress = GetProcAddress(Library, "NPLoadNameSpaces");
  v13 = (__int64 (__fastcall *)(int *, __int64, DWORD *))ProcAddress;
  if ( !ProcAddress )
  {
    FreeLibrary(Library);
    return GetLastError();
  }
  v32 = 1;
  ((void (__fastcall *)(int *, _QWORD, DWORD *))ProcAddress)(&v32, 0, &cbData);
  if ( !v32 )
  {
    LastError = 50;
LABEL_22:
    FreeLibrary(Library);
    return LastError;
  }
  v14 = ((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(SockPrivateHeap, 0, cbData);
  v15 = (_DWORD *)v14;
  if ( !v14 )
    goto LABEL_22;
  v32 = 1;
  v16 = v13(&v32, v14, &cbData);
  if ( v16 )
  {
    while ( 1 )
    {
      v17 = ((__int64 (__fastcall *)(HANDLE, _QWORD, __int64))SockAllocateHeapRoutine)(SockPrivateHeap, 0, 64);
      v18 = v17;
      if ( v17 )
      {
        *(_QWORD *)(v17 + 16) = Library;
        v19 = (__int64 **)(v15 + 2);
        if ( *v15 )
          v20 = **v19;
        else
          v20 = 0;
        *(_QWORD *)(v18 + 24) = v20;
        if ( *v15 <= 1u )
          v21 = 0;
        else
          v21 = (*v19)[1];
        *(_QWORD *)(v18 + 40) = v21;
        if ( *v15 <= 2u )
          v22 = 0;
        else
          v22 = (*v19)[2];
        v23 = DefaultExclusionCount;
        *(_QWORD *)(v18 + 32) = v22;
        v24 = 0;
        *(_DWORD *)(v18 + 56) = *v15;
        *(_DWORD *)(v18 + 48) = v15[5];
        v25 = v15[4];
        *(_DWORD *)(v18 + 52) = v25;
        *(_DWORD *)(v18 + 60) = 1;
        if ( v23 )
        {
          v26 = DefaultExclusions;
          do
          {
            if ( v25 == *(_DWORD *)(v26 + 4 * v24) )
              *(_DWORD *)(v18 + 60) = 0;
            v24 = (unsigned int)(v24 + 1);
          }
          while ( (unsigned int)v24 < v23 );
        }
        for ( i = NameSpaceListHead; (__int64 *)i != &NameSpaceListHead; i = *(_QWORD *)i )
        {
          if ( *(_DWORD *)(i + 48) > *(_DWORD *)(v18 + 48) )
            break;
        }
        v28 = *(__int64 **)(i + 8);
        if ( *v28 != i )
          __fastfail(3u);
        *(_QWORD *)v18 = i;
        Library = 0;
        *(_QWORD *)(v18 + 8) = v28;
        *v28 = v18;
        *(_QWORD *)(i + 8) = v18;
      }
      if ( !--v16 )
        break;
      v15 += 6;
    }
    return 0;
  }
  else
  {
    FreeLibrary(Library);
    RtlFreeHeap(SockPrivateHeap, 0, v15);
    return -1;
  }
}

```

## disassembly

```asm
0x180030098  push    rbp
0x18003009a  push    rbx
0x18003009b  push    rsi
0x18003009c  push    rdi
0x18003009d  push    r14
0x18003009f  mov     rbp, rsp
0x1800300a2  sub     rsp, 40h
0x1800300a6  mov     rax, cs:SockAllocateHeapRoutine
0x1800300ad  mov     rdi, rcx
0x1800300b0  mov     rcx, cs:SockPrivateHeap
0x1800300b7  mov     esi, 208h
0x1800300bc  mov     r8d, esi
0x1800300bf  mov     [rbp+hKey], 0
0x1800300c7  xor     edx, edx
0x1800300c9  mov     [rbp+Type], 0
0x1800300d0  mov     [rbp+Data], 0
0x1800300d7  mov     [rbp+cbData], 0
0x1800300de  mov     [rbp+arg_10], 0
0x1800300e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300ea  mov     rbx, rax
0x1800300ed  test    rax, rax
0x1800300f0  jnz     short loc_1800300FA
0x1800300f2  lea     eax, [rbx+8]
0x1800300f5  jmp     loc_180030567
0x1800300fa  lea     r8, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\"
0x180030101  mov     rdx, rsi; cbDest
0x180030104  mov     rcx, rbx; pszDest
0x180030107  call    StringCbCopyW
0x18003010c  mov     r8, rdi; pszSrc
0x18003010f  mov     rdx, rsi; cbDest
0x180030112  mov     rcx, rbx; pszDest
0x180030115  call    StringCbCatW
0x18003011a  lea     r8, aServiceprovide; "\\ServiceProvider"
0x180030121  mov     rdx, rsi; cbDest
0x180030124  mov     rcx, rbx; pszDest
0x180030127  call    StringCbCatW
0x18003012c  lea     rax, [rbp+hKey]
0x180030130  mov     r9d, 20019h; samDesired
0x180030136  xor     r8d, r8d; ulOptions
0x180030139  mov     [rsp+40h+phkResult], rax; phkResult
0x18003013e  mov     rdx, rbx; lpSubKey
0x180030141  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180030148  call    cs:__imp_RegOpenKeyExW
0x18003014f  nop     dword ptr [rax+rax+00h]
0x180030154  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18003015b  mov     r8, rbx; P
0x18003015e  xor     edx, edx; Flags
0x180030160  mov     edi, eax
0x180030162  call    cs:__imp_RtlFreeHeap
0x180030169  nop     dword ptr [rax+rax+00h]
0x18003016e  test    edi, edi
0x180030170  jz      short loc_180030179
0x180030172  mov     eax, edi
0x180030174  jmp     loc_180030567
0x180030179  mov     rcx, [rbp+hKey]; hKey
0x18003017d  lea     rax, [rbp+cbData]
0x180030181  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180030186  lea     r9, [rbp+Type]; lpType
0x18003018a  lea     rax, [rbp+Data]
0x18003018e  mov     [rbp+cbData], 4
0x180030195  xor     r8d, r8d; lpReserved
0x180030198  mov     [rsp+40h+phkResult], rax; lpData
0x18003019d  lea     rdx, aClass; "Class"
0x1800301a4  call    cs:__imp_RegQueryValueExW
0x1800301ab  nop     dword ptr [rax+rax+00h]
0x1800301b0  mov     ebx, eax
0x1800301b2  test    eax, eax
0x1800301b4  jnz     loc_180030555
0x1800301ba  lea     ebx, [rax+8]
0x1800301bd  test    byte ptr [rbp+Data], bl
0x1800301c0  jnz     short loc_1800301CA
0x1800301c2  lea     ebx, [rax+32h]
0x1800301c5  jmp     loc_180030555
0x1800301ca  mov     rcx, cs:SockPrivateHeap
0x1800301d1  mov     r8, rsi
0x1800301d4  mov     rax, cs:SockAllocateHeapRoutine
0x1800301db  xor     edx, edx
0x1800301dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301e2  mov     rdi, rax
0x1800301e5  test    rax, rax
0x1800301e8  jz      loc_180030555
0x1800301ee  mov     rcx, cs:SockPrivateHeap
0x1800301f5  mov     r8, rsi
0x1800301f8  mov     rax, cs:SockAllocateHeapRoutine
0x1800301ff  xor     edx, edx
0x180030201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030206  mov     rcx, [rbp+hKey]; hKey
0x18003020a  mov     r14, rax
0x18003020d  test    rax, rax
0x180030210  jnz     short loc_18003023B
0x180030212  call    cs:__imp_RegCloseKey
0x180030219  nop     dword ptr [rax+rax+00h]
0x18003021e  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180030225  mov     r8, rdi; P
0x180030228  xor     edx, edx; Flags
0x18003022a  call    cs:__imp_RtlFreeHeap
0x180030231  nop     dword ptr [rax+rax+00h]
0x180030236  jmp     loc_180030565
0x18003023b  lea     rax, [rbp+cbData]
0x18003023f  mov     [rbp+cbData], esi
0x180030242  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180030247  lea     r9, [rbp+Type]; lpType
0x18003024b  xor     r8d, r8d; lpReserved
0x18003024e  mov     [rsp+40h+phkResult], rdi; lpData
0x180030253  lea     rdx, aProviderpath; "ProviderPath"
0x18003025a  call    cs:__imp_RegQueryValueExW
0x180030261  nop     dword ptr [rax+rax+00h]
0x180030266  mov     esi, eax
0x180030268  test    eax, eax
0x18003026a  jz      short loc_1800302A3
0x18003026c  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180030273  mov     r8, rdi; P
0x180030276  xor     edx, edx; Flags
0x180030278  call    cs:__imp_RtlFreeHeap
0x18003027f  nop     dword ptr [rax+rax+00h]
0x180030284  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18003028b  mov     r8, r14; P
0x18003028e  xor     edx, edx; Flags
0x180030290  call    cs:__imp_RtlFreeHeap
0x180030297  nop     dword ptr [rax+rax+00h]
0x18003029c  mov     ebx, esi
0x18003029e  jmp     loc_180030555
0x1800302a3  mov     esi, 104h
0x1800302a8  mov     rdx, r14; lpDst
0x1800302ab  mov     r8d, esi; nSize
0x1800302ae  mov     rcx, rdi; lpSrc
0x1800302b1  call    cs:__imp_ExpandEnvironmentStringsW
0x1800302b8  nop     dword ptr [rax+rax+00h]
0x1800302bd  test    eax, eax
0x1800302bf  jz      loc_180030517
0x1800302c5  cmp     eax, esi
0x1800302c7  ja      loc_180030510
0x1800302cd  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800302d4  mov     r8, rdi; P
0x1800302d7  xor     edx, edx; Flags
0x1800302d9  call    cs:__imp_RtlFreeHeap
0x1800302e0  nop     dword ptr [rax+rax+00h]
0x1800302e5  xor     r8d, r8d; dwFlags
0x1800302e8  xor     edx, edx; hFile
0x1800302ea  mov     rcx, r14; lpLibFileName
0x1800302ed  call    cs:__imp_LoadLibraryExW
0x1800302f4  nop     dword ptr [rax+rax+00h]
0x1800302f9  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180030300  mov     r8, r14; P
0x180030303  xor     edx, edx; Flags
0x180030305  mov     rsi, rax
0x180030308  call    cs:__imp_RtlFreeHeap
0x18003030f  nop     dword ptr [rax+rax+00h]
0x180030314  mov     rcx, [rbp+hKey]; hKey
0x180030318  call    cs:__imp_RegCloseKey
0x18003031f  nop     dword ptr [rax+rax+00h]
0x180030324  test    rsi, rsi
0x180030327  jnz     short loc_18003033A
0x180030329  call    cs:__imp_GetLastError
0x180030330  nop     dword ptr [rax+rax+00h]
0x180030335  jmp     loc_180030567
0x18003033a  lea     rdx, aNploadnamespac_0; "NPLoadNameSpaces"
0x180030341  mov     rcx, rsi; hModule
0x180030344  call    cs:__imp_GetProcAddress
0x18003034b  nop     dword ptr [rax+rax+00h]
0x180030350  mov     r14, rax
0x180030353  test    rax, rax
0x180030356  jnz     short loc_180030369
0x180030358  mov     rcx, rsi; hLibModule
0x18003035b  call    cs:__imp_FreeLibrary
0x180030362  nop     dword ptr [rax+rax+00h]
0x180030367  jmp     short loc_180030329
0x180030369  lea     r8, [rbp+cbData]
0x18003036d  mov     [rbp+arg_10], 1
0x180030374  xor     edx, edx
0x180030376  lea     rcx, [rbp+arg_10]
0x18003037a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003037f  cmp     [rbp+arg_10], 1
0x180030383  jnb     short loc_18003038C
0x180030385  mov     ebx, 32h ; '2'
0x18003038a  jmp     short loc_1800303AD
0x18003038c  mov     r8d, [rbp+cbData]
0x180030390  xor     edx, edx
0x180030392  mov     rcx, cs:SockPrivateHeap
0x180030399  mov     rax, cs:SockAllocateHeapRoutine
0x1800303a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303a5  mov     rdi, rax
0x1800303a8  test    rax, rax
0x1800303ab  jnz     short loc_1800303C1
0x1800303ad  mov     rcx, rsi; hLibModule
0x1800303b0  call    cs:__imp_FreeLibrary
0x1800303b7  nop     dword ptr [rax+rax+00h]
0x1800303bc  jmp     loc_180030565
0x1800303c1  lea     r8, [rbp+cbData]
0x1800303c5  mov     [rbp+arg_10], 1
0x1800303cc  mov     rdx, rdi
0x1800303cf  lea     rcx, [rbp+arg_10]
0x1800303d3  mov     rax, r14
0x1800303d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303db  mov     ebx, eax
0x1800303dd  test    eax, eax
0x1800303df  jnz     short loc_180030410
0x1800303e1  mov     rcx, rsi; hLibModule
0x1800303e4  call    cs:__imp_FreeLibrary
0x1800303eb  nop     dword ptr [rax+rax+00h]
0x1800303f0  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800303f7  mov     r8, rdi; P
0x1800303fa  xor     edx, edx; Flags
0x1800303fc  call    cs:__imp_RtlFreeHeap
0x180030403  nop     dword ptr [rax+rax+00h]
0x180030408  or      eax, 0FFFFFFFFh
0x18003040b  jmp     loc_180030567
0x180030410  lea     r14, NameSpaceListHead
0x180030417  mov     rcx, cs:SockPrivateHeap
0x18003041e  xor     edx, edx
0x180030420  mov     rax, cs:SockAllocateHeapRoutine
0x180030427  lea     r8d, [rdx+40h]
0x18003042b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030430  mov     rdx, rax
0x180030433  test    rax, rax
0x180030436  jz      loc_1800304F7
0x18003043c  mov     [rax+10h], rsi
0x180030440  lea     r8, [rdi+8]
0x180030444  cmp     dword ptr [rdi], 0
0x180030447  jbe     short loc_180030451
0x180030449  mov     rcx, [r8]
0x18003044c  mov     rax, [rcx]
0x18003044f  jmp     short loc_180030453
0x180030451  xor     eax, eax
0x180030453  mov     [rdx+18h], rax
0x180030457  cmp     dword ptr [rdi], 1
0x18003045a  jbe     short loc_180030465
0x18003045c  mov     rax, [r8]
0x18003045f  mov     rcx, [rax+8]
0x180030463  jmp     short loc_180030467
0x180030465  xor     ecx, ecx
0x180030467  mov     [rdx+28h], rcx
0x18003046b  cmp     dword ptr [rdi], 2
0x18003046e  jbe     short loc_180030479
0x180030470  mov     rax, [r8]
0x180030473  mov     rcx, [rax+10h]
0x180030477  jmp     short loc_18003047B
0x180030479  xor     ecx, ecx
0x18003047b  mov     r8d, cs:DefaultExclusionCount
0x180030482  mov     [rdx+20h], rcx
0x180030486  xor     ecx, ecx
0x180030488  mov     eax, [rdi]
0x18003048a  mov     [rdx+38h], eax
0x18003048d  mov     eax, [rdi+14h]
0x180030490  mov     [rdx+30h], eax
0x180030493  mov     r9d, [rdi+10h]
0x180030497  mov     [rdx+34h], r9d
0x18003049b  mov     dword ptr [rdx+3Ch], 1
0x1800304a2  test    r8d, r8d
0x1800304a5  jz      short loc_1800304C2
0x1800304a7  mov     r10, cs:DefaultExclusions
0x1800304ae  cmp     r9d, [r10+rcx*4]
0x1800304b2  jnz     short loc_1800304BB
0x1800304b4  mov     dword ptr [rdx+3Ch], 0
0x1800304bb  inc     ecx
0x1800304bd  cmp     ecx, r8d
0x1800304c0  jb      short loc_1800304AE
0x1800304c2  mov     rax, cs:NameSpaceListHead
0x1800304c9  cmp     rax, r14
0x1800304cc  jz      short loc_1800304DE
0x1800304ce  mov     ecx, [rdx+30h]
0x1800304d1  cmp     [rax+30h], ecx
0x1800304d4  ja      short loc_1800304DE
0x1800304d6  mov     rax, [rax]
0x1800304d9  cmp     rax, r14
0x1800304dc  jnz     short loc_1800304D1
0x1800304de  mov     rcx, [rax+8]
0x1800304e2  cmp     [rcx], rax
0x1800304e5  jnz     short loc_180030505
0x1800304e7  mov     [rdx], rax
0x1800304ea  xor     esi, esi
0x1800304ec  mov     [rdx+8], rcx
0x1800304f0  mov     [rcx], rdx
0x1800304f3  mov     [rax+8], rdx
0x1800304f7  add     ebx, 0FFFFFFFFh
0x1800304fa  jz      short loc_18003050C
0x1800304fc  add     rdi, 18h
0x180030500  jmp     loc_180030417
0x180030505  mov     ecx, 3
0x18003050a  int     29h; Win8: RtlFailFast(ecx)
0x18003050c  xor     eax, eax
0x18003050e  jmp     short loc_180030567
0x180030510  mov     ebx, 7Ah ; 'z'
0x180030515  jmp     short loc_180030525
0x180030517  call    cs:__imp_GetLastError
0x18003051e  nop     dword ptr [rax+rax+00h]
0x180030523  mov     ebx, eax
0x180030525  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18003052c  mov     r8, rdi; P
0x18003052f  xor     edx, edx; Flags
0x180030531  call    cs:__imp_RtlFreeHeap
0x180030538  nop     dword ptr [rax+rax+00h]
0x18003053d  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180030544  mov     r8, r14; P
0x180030547  xor     edx, edx; Flags
0x180030549  call    cs:__imp_RtlFreeHeap
0x180030550  nop     dword ptr [rax+rax+00h]
0x180030555  mov     rcx, [rbp+hKey]; hKey
0x180030559  call    cs:__imp_RegCloseKey
0x180030560  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
