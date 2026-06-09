# ReadProtocolDataFromProvider

- ea: `0x180034ff0`
- end: `0x18003543a`
- name: `ReadProtocolDataFromProvider`
- size: `1098`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800328c0`

## callees

- `0x180022bd2`
- `0x1800327a8`
- `0x1800327f0`
- `0x180034ff0`
- `0x1800355e4`
- `0x1800356f8`
- `0x18003a8b0`
- `0x180053010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800350c7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800350c7`
- `ntdll!RtlFreeHeap` at `0x180035342`
- `ntdll!RtlFreeHeap` at `0x18003536f`
- `ntdll!RtlFreeHeap` at `0x1800353db`
- `ntdll!RtlFreeHeap` at `0x1800353fa`
- `ntdll!RtlFreeHeap` at `0x180035342`
- `ntdll!RtlFreeHeap` at `0x18003536f`
- `ntdll!RtlFreeHeap` at `0x1800353db`
- `ntdll!RtlFreeHeap` at `0x1800353fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003519a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003519a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180035139`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180035139`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800351bb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800351bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800351e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800351e9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003540e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003540e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800353a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800353bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800353a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800353bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035063`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800350a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035063`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800350a4`

## string_xrefs

- `0x1800350f8`: `HelperDllName`
- `0x1800351df`: `WSHEnumProtocols`
- `0x180035073`: `Failed to open service key; continuing on`
- `0x1800350b4`: `Failed to open service parameters key; continuing on`
- `0x1800350ea`: `Failed to read supported protocols; continuing on`
- `0x180035113`: `Failed to read helper DLL path; continuing on`
- `0x180035153`: `Expanded length exceeds max path length`
- `0x1800351d4`: `Could not load helper DLL`
- `0x180035202`: `Could not enumerate any protocols from helper DLL`
- `0x180035237`: `Caught exception while enumerating protocols`
- `0x180035281`: `No protocols to enumerate`
- `0x1800352bc`: `Failed to allocate memory for protocolInfo11`
- `0x180035351`: `Failed to enumerate protocols`

## pseudocode

```c
__int64 __fastcall ReadProtocolDataFromProvider(
        HKEY a1,
        const WCHAR *a2,
        WCHAR *a3,
        _QWORD *a4,
        _DWORD *a5,
        _DWORD *a6)
{
  HMODULE v9; // r15
  unsigned int String; // eax
  const wchar_t *v11; // rdx
  DWORD LastError; // edi
  const wchar_t *v13; // rdx
  __int64 v14; // rcx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v17)(PVOID, const WCHAR *, void *, size_t *); // rsi
  void *v18; // rax
  void *v19; // r14
  int v20; // esi
  size_t Size; // [rsp+30h] [rbp-78h] BYREF
  int v23; // [rsp+38h] [rbp-70h]
  LPCWSTR lpSrc; // [rsp+40h] [rbp-68h]
  unsigned int v25; // [rsp+48h] [rbp-60h]
  HKEY phkResult; // [rsp+50h] [rbp-58h] BYREF
  PVOID P; // [rsp+58h] [rbp-50h] BYREF
  HKEY hKey[4]; // [rsp+60h] [rbp-48h] BYREF

  Size = 0;
  hKey[0] = 0;
  phkResult = 0;
  P = 0;
  lpSrc = 0;
  v9 = 0;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  String = RegOpenKeyExW(a1, a2, 0, 0x20019u, hKey);
  if ( String )
  {
    v11 = L"Failed to open service key; continuing on";
LABEL_3:
    LogError(String, v11);
    LastError = 0;
    goto LABEL_35;
  }
  String = RegOpenKeyExW(hKey[0], L"Parameters\\WinSock", 0, 0x20019u, &phkResult);
  if ( String )
  {
    v11 = L"Failed to open service parameters key; continuing on";
    goto LABEL_3;
  }
  if ( (unsigned int)_o__wcsicmp(a2, L"NetBIOS") )
  {
    String = ReadProviderSupportedProtocolsFromRegistry(phkResult, &P);
    if ( String )
    {
      v11 = L"Failed to read supported protocols; continuing on";
      goto LABEL_3;
    }
  }
  String = ReadString(phkResult, L"HelperDllName");
  LastError = String;
  v25 = String;
  if ( String )
  {
    v11 = L"Failed to read helper DLL path; continuing on";
    goto LABEL_3;
  }
  if ( DefaultTranslator )
  {
    if ( (int)DefaultTranslator(1, lpSrc, 260, a3, (char *)&Size + 4) < 0 )
    {
      v13 = L"Translator failed";
      goto LABEL_17;
    }
  }
  else
  {
    HIDWORD(Size) = ExpandEnvironmentStringsW(lpSrc, a3, 0x104u);
  }
  if ( HIDWORD(Size) > 0x104 )
  {
    v13 = L"Expanded length exceeds max path length";
LABEL_17:
    v14 = 8;
    LastError = 8;
LABEL_18:
    LogError(v14, v13);
    goto LABEL_35;
  }
  if ( !HIDWORD(Size) )
  {
    LastError = GetLastError();
    v13 = L"Expanded length is zero";
    v14 = LastError;
    goto LABEL_18;
  }
  Library = LoadLibraryExW(a3, 0, 0);
  v9 = Library;
  hKey[1] = (HKEY)Library;
  if ( !Library )
  {
    v13 = L"Could not load helper DLL";
LABEL_23:
    v14 = 0;
    goto LABEL_18;
  }
  ProcAddress = GetProcAddress(Library, "WSHEnumProtocols");
  v17 = (__int64 (__fastcall *)(PVOID, const WCHAR *, void *, size_t *))ProcAddress;
  hKey[2] = (HKEY)ProcAddress;
  if ( !ProcAddress )
  {
    v13 = L"Could not enumerate any protocols from helper DLL";
    goto LABEL_23;
  }
  LODWORD(Size) = 0;
  v23 = ((__int64 (__fastcall *)(PVOID, const WCHAR *, _QWORD, size_t *))ProcAddress)(P, a2, 0, &Size);
  if ( !v23 )
    goto LABEL_27;
  v18 = (void *)((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(
                  SockPrivateHeap,
                  0,
                  (unsigned int)Size);
  v19 = v18;
  if ( !v18 )
  {
    v13 = L"Failed to allocate memory for protocolInfo11";
    goto LABEL_17;
  }
  memset_0(v18, 0, (unsigned int)Size);
  v20 = v17(P, a2, v19, &Size);
  v23 = v20;
  if ( v20 == -1 )
  {
    RtlFreeHeap(SockPrivateHeap, 0, v19);
    LastError = 31;
    v13 = L"Failed to enumerate protocols";
    v14 = 31;
    goto LABEL_18;
  }
  if ( !v20 )
  {
    RtlFreeHeap(SockPrivateHeap, 0, v19);
LABEL_27:
    LogMsg(L"No protocols to enumerate");
    goto LABEL_35;
  }
  *a4 = v19;
  *a5 = Size;
  *a6 = v20;
LABEL_35:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( P )
    RtlFreeHeap(SockPrivateHeap, 0, P);
  if ( lpSrc )
    RtlFreeHeap(SockPrivateHeap, 0, (PVOID)lpSrc);
  if ( v9 )
    FreeLibrary(v9);
  return LastError;
}

```

## disassembly

```asm
0x180034ff0  mov     rax, rsp
0x180034ff3  mov     [rax+8], rbx
0x180034ff7  mov     [rax+18h], rsi
0x180034ffb  mov     [rax+20h], r9
0x180034fff  mov     [rax+10h], rdx
0x180035003  push    rdi
0x180035004  push    r12
0x180035006  push    r13
0x180035008  push    r14
0x18003500a  push    r15
0x18003500c  sub     rsp, 80h
0x180035013  mov     r13, r9
0x180035016  mov     rsi, r8
0x180035019  mov     r12, rdx
0x18003501c  xor     ebx, ebx
0x18003501e  mov     [rax-74h], ebx
0x180035021  mov     [rax-78h], ebx
0x180035024  mov     [rax-48h], rbx
0x180035028  mov     [rax-58h], rbx
0x18003502c  mov     [rax-50h], rbx
0x180035030  mov     [rax-68h], rbx
0x180035034  mov     r15d, ebx
0x180035037  mov     [r9], rbx
0x18003503a  mov     rax, [rsp+0A8h+arg_20]
0x180035042  mov     [rax], ebx
0x180035044  mov     rax, [rsp+0A8h+arg_28]
0x18003504c  mov     [rax], ebx
0x18003504e  lea     rax, [rsp+0A8h+hKey]
0x180035053  mov     [rsp+0A8h+phkResult], rax; phkResult
0x180035058  mov     edi, 20019h
0x18003505d  mov     r9d, edi; samDesired
0x180035060  xor     r8d, r8d; ulOptions
0x180035063  call    cs:__imp_RegOpenKeyExW
0x18003506a  nop     dword ptr [rax+rax+00h]
0x18003506f  test    eax, eax
0x180035071  jz      short loc_180035088
0x180035073  lea     rdx, aFailedToOpenSe; "Failed to open service key; continuing "...
0x18003507a  mov     ecx, eax
0x18003507c  call    LogError
0x180035081  mov     edi, ebx
0x180035083  jmp     loc_18003539C
0x180035088  lea     rax, [rsp+0A8h+var_58]
0x18003508d  mov     [rsp+0A8h+phkResult], rax; phkResult
0x180035092  mov     r9d, edi; samDesired
0x180035095  xor     r8d, r8d; ulOptions
0x180035098  lea     rdx, aParametersWins_0; "Parameters\\WinSock"
0x18003509f  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1800350a4  call    cs:__imp_RegOpenKeyExW
0x1800350ab  nop     dword ptr [rax+rax+00h]
0x1800350b0  test    eax, eax
0x1800350b2  jz      short loc_1800350BD
0x1800350b4  lea     rdx, aFailedToOpenSe_0; "Failed to open service parameters key; "...
0x1800350bb  jmp     short loc_18003507A
0x1800350bd  lea     rdx, aNetbios; "NetBIOS"
0x1800350c4  mov     rcx, r12
0x1800350c7  call    cs:__imp__o__wcsicmp
0x1800350ce  nop     dword ptr [rax+rax+00h]
0x1800350d3  test    eax, eax
0x1800350d5  jz      short loc_1800350F3
0x1800350d7  lea     rdx, [rsp+0A8h+P]
0x1800350dc  mov     rcx, [rsp+0A8h+var_58]
0x1800350e1  call    ReadProviderSupportedProtocolsFromRegistry
0x1800350e6  test    eax, eax
0x1800350e8  jz      short loc_1800350F3
0x1800350ea  lea     rdx, aFailedToReadSu; "Failed to read supported protocols; con"...
0x1800350f1  jmp     short loc_18003507A
0x1800350f3  lea     r8, [rsp+0A8h+lpSrc]
0x1800350f8  lea     rdx, aHelperdllname; "HelperDllName"
0x1800350ff  mov     rcx, [rsp+0A8h+var_58]; hKey
0x180035104  call    ReadString
0x180035109  mov     edi, eax
0x18003510b  mov     [rsp+0A8h+var_60], eax
0x18003510f  test    eax, eax
0x180035111  jz      short loc_18003511F
0x180035113  lea     rdx, aFailedToReadHe; "Failed to read helper DLL path; continu"...
0x18003511a  jmp     loc_18003507A
0x18003511f  mov     rax, cs:DefaultTranslator
0x180035126  mov     r8d, 104h; nSize
0x18003512c  test    rax, rax
0x18003512f  jnz     short loc_18003515C
0x180035131  mov     rdx, rsi; lpDst
0x180035134  mov     rcx, [rsp+0A8h+lpSrc]; lpSrc
0x180035139  call    cs:__imp_ExpandEnvironmentStringsW
0x180035140  nop     dword ptr [rax+rax+00h]
0x180035145  mov     dword ptr [rsp+0A8h+Size+4], eax
0x180035149  cmp     dword ptr [rsp+0A8h+Size+4], 104h
0x180035151  jbe     short loc_180035194
0x180035153  lea     rdx, aExpandedLength_0; "Expanded length exceeds max path length"
0x18003515a  jmp     short loc_180035183
0x18003515c  lea     rcx, [rsp+0A8h+Size+4]
0x180035161  mov     [rsp+0A8h+phkResult], rcx
0x180035166  mov     r9, rsi
0x180035169  mov     rdx, [rsp+0A8h+lpSrc]
0x18003516e  mov     ecx, 1
0x180035173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035178  test    eax, eax
0x18003517a  jns     short loc_180035149
0x18003517c  lea     rdx, aTranslatorFail; "Translator failed"
0x180035183  mov     ecx, 8
0x180035188  mov     edi, ecx
0x18003518a  call    LogError
0x18003518f  jmp     loc_18003539C
0x180035194  cmp     dword ptr [rsp+0A8h+Size+4], ebx
0x180035198  jnz     short loc_1800351B3
0x18003519a  call    cs:__imp_GetLastError
0x1800351a1  nop     dword ptr [rax+rax+00h]
0x1800351a6  mov     edi, eax
0x1800351a8  lea     rdx, aExpandedLength; "Expanded length is zero"
0x1800351af  mov     ecx, eax
0x1800351b1  jmp     short loc_18003518A
0x1800351b3  xor     r8d, r8d; dwFlags
0x1800351b6  xor     edx, edx; hFile
0x1800351b8  mov     rcx, rsi; lpLibFileName
0x1800351bb  call    cs:__imp_LoadLibraryExW
0x1800351c2  nop     dword ptr [rax+rax+00h]
0x1800351c7  mov     r15, rax
0x1800351ca  mov     [rsp+0A8h+var_40], rax
0x1800351cf  test    rax, rax
0x1800351d2  jnz     short loc_1800351DF
0x1800351d4  lea     rdx, aCouldNotLoadHe; "Could not load helper DLL"
0x1800351db  xor     ecx, ecx
0x1800351dd  jmp     short loc_18003518A
0x1800351df  lea     rdx, aWshenumprotoco; "WSHEnumProtocols"
0x1800351e6  mov     rcx, rax; hModule
0x1800351e9  call    cs:__imp_GetProcAddress
0x1800351f0  nop     dword ptr [rax+rax+00h]
0x1800351f5  mov     rsi, rax
0x1800351f8  mov     [rsp+0A8h+var_38], rax
0x1800351fd  test    rax, rax
0x180035200  jnz     short loc_18003520B
0x180035202  lea     rdx, aCouldNotEnumer; "Could not enumerate any protocols from "...
0x180035209  jmp     short loc_1800351DB
0x18003520b  mov     dword ptr [rsp+0A8h+Size], ebx
0x18003520f  lea     r9, [rsp+0A8h+Size]
0x180035214  xor     r8d, r8d
0x180035217  mov     rdx, r12
0x18003521a  mov     rcx, [rsp+0A8h+P]
0x18003521f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035224  mov     r14d, eax
0x180035227  mov     [rsp+0A8h+var_70], eax
0x18003522b  jmp     short loc_18003527C
0x18003522d  mov     ebx, eax
0x18003522f  xor     r14d, r14d
0x180035232  mov     [rsp+0A8h+var_70], r14d
0x180035237  lea     rcx, aCaughtExceptio_0; "Caught exception while enumerating prot"...
0x18003523e  call    LogMsg
0x180035243  test    byte ptr cs:xmmword_180063D60, 2
0x18003524a  jz      short loc_18003525E
0x18003524c  lea     edx, [r14+24h]
0x180035250  mov     dword ptr [rsp+0A8h+phkResult], ebx
0x180035254  mov     r9, [rsp+0A8h+lpSrc]
0x180035259  call    WPP_SF_SL
0x18003525e  mov     r13, [rsp+0A8h+arg_18]
0x180035266  mov     r12, [rsp+0A8h+arg_8]
0x18003526e  mov     edi, [rsp+0A8h+var_60]
0x180035272  mov     r15, [rsp+0A8h+var_40]
0x180035277  mov     rsi, [rsp+0A8h+var_38]
0x18003527c  test    r14d, r14d
0x18003527f  jnz     short loc_180035292
0x180035281  lea     rcx, aNoProtocolsToE; "No protocols to enumerate"
0x180035288  call    LogMsg
0x18003528d  jmp     loc_18003539C
0x180035292  mov     r8d, dword ptr [rsp+0A8h+Size]
0x180035297  xor     edx, edx
0x180035299  mov     rcx, cs:SockPrivateHeap
0x1800352a0  mov     rax, cs:SockAllocateHeapRoutine
0x1800352a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800352ac  mov     r14, rax
0x1800352af  mov     [rsp+0A8h+arg_8], rax
0x1800352b7  test    rax, rax
0x1800352ba  jnz     short loc_1800352C8
0x1800352bc  lea     rdx, aFailedToAlloca_5; "Failed to allocate memory for protocolI"...
0x1800352c3  jmp     loc_180035183
0x1800352c8  mov     r8d, dword ptr [rsp+0A8h+Size]; Size
0x1800352cd  xor     edx, edx; Val
0x1800352cf  mov     rcx, r14; void *
0x1800352d2  call    memset_0
0x1800352d7  nop
0x1800352d8  lea     r9, [rsp+0A8h+Size]
0x1800352dd  mov     r8, r14
0x1800352e0  mov     rdx, r12
0x1800352e3  mov     rcx, [rsp+0A8h+P]
0x1800352e8  mov     rax, rsi
0x1800352eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800352f0  mov     esi, eax
0x1800352f2  mov     [rsp+0A8h+var_70], eax
0x1800352f6  jmp     short loc_180035331
0x1800352f8  xor     esi, esi
0x1800352fa  mov     [rsp+0A8h+var_70], esi
0x1800352fe  test    byte ptr cs:xmmword_180063D60, 2
0x180035305  jz      short loc_180035318
0x180035307  lea     edx, [rsi+25h]
0x18003530a  mov     dword ptr [rsp+0A8h+phkResult], eax
0x18003530e  mov     r9, [rsp+0A8h+lpSrc]
0x180035313  call    WPP_SF_SL
0x180035318  mov     r13, [rsp+0A8h+arg_18]
0x180035320  mov     edi, [rsp+0A8h+var_60]
0x180035324  mov     r15, [rsp+0A8h+var_40]
0x180035329  mov     r14, [rsp+0A8h+arg_8]
0x180035331  cmp     esi, 0FFFFFFFFh
0x180035334  jnz     short loc_18003535F
0x180035336  mov     r8, r14; P
0x180035339  xor     edx, edx; Flags
0x18003533b  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180035342  call    cs:__imp_RtlFreeHeap
0x180035349  nop     dword ptr [rax+rax+00h]
0x18003534e  lea     edi, [rsi+20h]
0x180035351  lea     rdx, aFailedToEnumer; "Failed to enumerate protocols"
0x180035358  mov     ecx, edi
0x18003535a  jmp     loc_18003518A
0x18003535f  test    esi, esi
0x180035361  jnz     short loc_180035380
0x180035363  mov     r8, r14; P
0x180035366  xor     edx, edx; Flags
0x180035368  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18003536f  call    cs:__imp_RtlFreeHeap
0x180035376  nop     dword ptr [rax+rax+00h]
0x18003537b  jmp     loc_180035281
0x180035380  mov     [r13+0], r14
0x180035384  mov     ecx, dword ptr [rsp+0A8h+Size]
0x180035388  mov     rax, [rsp+0A8h+arg_20]
0x180035390  mov     [rax], ecx
0x180035392  mov     rax, [rsp+0A8h+arg_28]
0x18003539a  mov     [rax], esi
0x18003539c  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1800353a1  test    rcx, rcx
0x1800353a4  jz      short loc_1800353B2
0x1800353a6  call    cs:__imp_RegCloseKey
0x1800353ad  nop     dword ptr [rax+rax+00h]
0x1800353b2  mov     rcx, [rsp+0A8h+var_58]; hKey
0x1800353b7  test    rcx, rcx
0x1800353ba  jz      short loc_1800353C8
0x1800353bc  call    cs:__imp_RegCloseKey
0x1800353c3  nop     dword ptr [rax+rax+00h]
0x1800353c8  mov     r8, [rsp+0A8h+P]; P
0x1800353cd  test    r8, r8
0x1800353d0  jz      short loc_1800353E7
0x1800353d2  xor     edx, edx; Flags
0x1800353d4  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800353db  call    cs:__imp_RtlFreeHeap
0x1800353e2  nop     dword ptr [rax+rax+00h]
0x1800353e7  mov     r8, [rsp+0A8h+lpSrc]; P
0x1800353ec  test    r8, r8
0x1800353ef  jz      short loc_180035406
0x1800353f1  xor     edx, edx; Flags
0x1800353f3  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800353fa  call    cs:__imp_RtlFreeHeap
0x180035401  nop     dword ptr [rax+rax+00h]
0x180035406  test    r15, r15
0x180035409  jz      short loc_18003541A
0x18003540b  mov     rcx, r15; hLibModule
0x18003540e  call    cs:__imp_FreeLibrary
0x180035415  nop     dword ptr [rax+rax+00h]
0x18003541a  mov     eax, edi
0x18003541c  lea     r11, [rsp+0A8h+var_28]
0x180035424  mov     rbx, [r11+30h]
0x180035428  mov     rsi, [r11+40h]
0x18003542c  mov     rsp, r11
0x18003542f  pop     r15
0x180035431  pop     r14
0x180035433  pop     r13
0x180035435  pop     r12
0x180035437  pop     rdi
0x180035438  retn
```
