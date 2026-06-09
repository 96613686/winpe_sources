# AslLogCreate

- ea: `0x18006a718`
- end: `0x18006a9de`
- name: `AslLogCreate`
- size: `710`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800045c0`

## callees

- `0x180005e40`
- `0x18006855c`
- `0x18006a718`
- `0x18006b1a8`
- `0x18006b25c`
- `0x18006b324`
- `0x180116010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006a857`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006a857`
- `ntdll!EtwEventRegister` at `0x18006a7e4`
- `ntdll!EtwEventRegister` at `0x18006a7e4`
- `ntdll!RtlInitializeCriticalSection` at `0x18006a782`
- `ntdll!RtlInitializeCriticalSection` at `0x18006a782`
- `ntdll!RtlAllocateHeap` at `0x18006a75b`
- `ntdll!RtlAllocateHeap` at `0x18006a75b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18006a7fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18006a7fd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006a882`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006a882`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006a824`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006a824`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a89a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a89a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a803`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006a91f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006a91f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006a8bd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006a8de`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006a8bd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006a8de`

## string_xrefs

- `0x18006a875`: `ntdll.dll`
- `0x18006a8b6`: `%OSDataDrive%\SystemData\Temp`
- `0x18006a8d7`: `%TEMP%`
- `0x18006a901`: `%s\Temp`

## pseudocode

```c
__int64 AslLogCreate()
{
  char *Heap; // rax
  char *v1; // rbx
  int v2; // edi
  PVOID ProcessHeap; // rcx
  HMODULE v4; // rbp
  wchar_t *v6; // rax
  WCHAR *v7; // rsi
  HMODULE Library; // rax
  unsigned __int8 (*ProcAddress)(void); // rax
  __int64 NtSystemRoot; // rax
  const char *v11; // rsi
  int DefaultFlags; // eax
  __int64 v13; // rdx
  __int64 v14; // rax
  _BYTE *v15; // rcx
  _BYTE *v16; // rax
  unsigned int v17; // ecx
  WCHAR *v18; // [rsp+28h] [rbp-470h]
  DWORD CurrentProcessId; // [rsp+30h] [rbp-468h]
  WCHAR Dst[264]; // [rsp+40h] [rbp-458h] BYREF
  WCHAR Filename[264]; // [rsp+250h] [rbp-248h] BYREF

  g_Logger = 0;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x2D8u);
  v1 = Heap;
  if ( !Heap )
    return (unsigned int)-1073741801;
  *((_QWORD *)Heap + 90) = 0;
  RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 104));
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  *((_OWORD *)v1 + 9) = 0;
  *((_OWORD *)v1 + 10) = 0;
  *((_OWORD *)v1 + 11) = 0;
  if ( !ProcessHeap )
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
  *((_QWORD *)v1 + 18) = ProcessHeap;
  *((_QWORD *)v1 + 21) = 4096;
  EtwEventRegister(AE_LOG, 0, 0, v1 + 712);
  GetModuleFileNameW(0, Filename, 0x104u);
  if ( GetLastError() )
  {
    v4 = 0;
LABEL_7:
    v2 = -1073741823;
LABEL_8:
    AslLogDelete(v1);
    goto LABEL_9;
  }
  v6 = wcsrchr(Filename, 0x5Cu);
  if ( v6 )
    v7 = v6 + 1;
  else
    v7 = Filename;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v4 = Library;
  if ( Library
    && (ProcAddress = (unsigned __int8 (*)(void))GetProcAddress(Library, "RtlIsStateSeparationEnabled")) != 0
    && ProcAddress() )
  {
    if ( (!ExpandEnvironmentStringsW(L"%OSDataDrive%\\SystemData\\Temp", Dst, 0x104u) || Dst[0] == 37)
      && (!ExpandEnvironmentStringsW(L"%TEMP%", Dst, 0x104u) || Dst[0] == 37) )
    {
      goto LABEL_7;
    }
  }
  else
  {
    NtSystemRoot = AslPathGetNtSystemRoot();
    v2 = RtlStringCchPrintfW(Dst, 260, L"%s\\Temp", NtSystemRoot);
    if ( v2 < 0 )
      goto LABEL_8;
  }
  CurrentProcessId = GetCurrentProcessId();
  v18 = v7;
  v11 = "devinv";
  v2 = RtlStringCchPrintfW(v1 + 192, 260, L"%s\\AslLog_%S_%s_%d.txt", Dst, "devinv", v18, CurrentProcessId);
  if ( v2 < 0 )
    goto LABEL_8;
  *(_QWORD *)v1 = v1 + 8;
  DefaultFlags = AslLogGetDefaultFlags();
  v13 = 64;
  *(_DWORD *)(*(_QWORD *)v1 + 80LL) = DefaultFlags;
  v14 = 2147483646;
  v15 = *(_BYTE **)v1;
  do
  {
    if ( !v14 )
      break;
    if ( !*v11 )
      break;
    *v15++ = *v11++;
    --v14;
    --v13;
  }
  while ( v13 );
  v16 = v15 - 1;
  if ( v13 )
    v16 = v15;
  *v16 = 0;
  v17 = *((_DWORD *)v1 + 40);
  if ( v17 <= 0x1000 )
  {
    v17 = 4096;
LABEL_35:
    *(_DWORD *)(*(_QWORD *)v1 + 76LL) = v17;
    goto LABEL_36;
  }
  if ( v17 == (v17 & -v17) )
    goto LABEL_35;
LABEL_36:
  v2 = 0;
  g_Logger = v1;
LABEL_9:
  if ( v4 )
    FreeLibrary(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18006a718  push    rbx
0x18006a71a  push    rbp
0x18006a71b  push    rsi
0x18006a71c  push    rdi
0x18006a71d  push    r15
0x18006a71f  sub     rsp, 470h
0x18006a726  mov     rax, cs:__security_cookie
0x18006a72d  xor     rax, rsp
0x18006a730  mov     [rsp+498h+var_38], rax
0x18006a738  mov     cs:?g_Logger@@3VAslLogGlobalLogger@@A, 0; AslLogGlobalLogger g_Logger
0x18006a743  mov     edx, 8; Flags
0x18006a748  mov     rcx, gs:60h
0x18006a751  mov     r8d, 2D8h; Size
0x18006a757  mov     rcx, [rcx+30h]; HeapHandle
0x18006a75b  call    cs:__imp_RtlAllocateHeap
0x18006a761  mov     rbx, rax
0x18006a764  test    rax, rax
0x18006a767  jnz     short loc_18006A773
0x18006a769  mov     edi, 0C0000017h
0x18006a76e  jmp     loc_18006A82A
0x18006a773  lea     rcx, [rax+68h]; CriticalSection
0x18006a777  mov     qword ptr [rax+2D0h], 0
0x18006a782  call    cs:__imp_RtlInitializeCriticalSection
0x18006a788  mov     rax, gs:60h
0x18006a791  xorps   xmm0, xmm0
0x18006a794  mov     rcx, [rax+30h]
0x18006a798  movups  xmmword ptr [rbx+90h], xmm0
0x18006a79f  movups  xmmword ptr [rbx+0A0h], xmm0
0x18006a7a6  movups  xmmword ptr [rbx+0B0h], xmm0
0x18006a7ad  test    rcx, rcx
0x18006a7b0  jnz     short loc_18006A7BF
0x18006a7b2  mov     rax, gs:60h
0x18006a7bb  mov     rcx, [rax+30h]
0x18006a7bf  mov     [rbx+90h], rcx
0x18006a7c6  mov     qword ptr [rbx+0A8h], 1000h
0x18006a7d1  lea     r9, [rbx+2C8h]
0x18006a7d8  xor     r8d, r8d
0x18006a7db  xor     edx, edx
0x18006a7dd  lea     rcx, AE_LOG
0x18006a7e4  call    cs:__imp_EtwEventRegister
0x18006a7ea  mov     r15d, 104h
0x18006a7f0  lea     rdx, [rsp+498h+Filename]; lpFilename
0x18006a7f8  mov     r8d, r15d; nSize
0x18006a7fb  xor     ecx, ecx; hModule
0x18006a7fd  call    cs:__imp_GetModuleFileNameW
0x18006a803  call    cs:__imp_GetLastError
0x18006a809  test    eax, eax
0x18006a80b  jz      short loc_18006A84A
0x18006a80d  xor     ebp, ebp
0x18006a80f  mov     edi, 0C0000001h
0x18006a814  mov     rcx, rbx; P
0x18006a817  call    AslLogDelete
0x18006a81c  test    rbp, rbp
0x18006a81f  jz      short loc_18006A82A
0x18006a821  mov     rcx, rbp; hLibModule
0x18006a824  call    cs:__imp_FreeLibrary
0x18006a82a  mov     eax, edi
0x18006a82c  mov     rcx, [rsp+498h+var_38]
0x18006a834  xor     rcx, rsp; StackCookie
0x18006a837  call    __security_check_cookie
0x18006a83c  add     rsp, 470h
0x18006a843  pop     r15
0x18006a845  pop     rdi
0x18006a846  pop     rsi
0x18006a847  pop     rbp
0x18006a848  pop     rbx
0x18006a849  retn
0x18006a84a  mov     edx, 5Ch ; '\'; Ch
0x18006a84f  lea     rcx, [rsp+498h+Filename]; Str
0x18006a857  call    cs:__imp_wcsrchr
0x18006a85d  mov     rsi, rax
0x18006a860  test    rax, rax
0x18006a863  jnz     short loc_18006A86F
0x18006a865  lea     rsi, [rsp+498h+Filename]
0x18006a86d  jmp     short loc_18006A873
0x18006a86f  add     rsi, 2
0x18006a873  xor     edx, edx; hFile
0x18006a875  lea     rcx, LibFileName; "ntdll.dll"
0x18006a87c  mov     r8d, 800h; dwFlags
0x18006a882  call    cs:__imp_LoadLibraryExW
0x18006a888  mov     rbp, rax
0x18006a88b  test    rax, rax
0x18006a88e  jz      short loc_18006A8F9
0x18006a890  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x18006a897  mov     rcx, rax; hModule
0x18006a89a  call    cs:__imp_GetProcAddress
0x18006a8a0  test    rax, rax
0x18006a8a3  jz      short loc_18006A8F9
0x18006a8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a8aa  test    al, al
0x18006a8ac  jz      short loc_18006A8F9
0x18006a8ae  mov     r8d, r15d; nSize
0x18006a8b1  lea     rdx, [rsp+498h+Dst]; lpDst
0x18006a8b6  lea     rcx, aOsdatadriveSys; "%OSDataDrive%\\SystemData\\Temp"
0x18006a8bd  call    cs:__imp_ExpandEnvironmentStringsW
0x18006a8c3  test    eax, eax
0x18006a8c5  jz      short loc_18006A8CF
0x18006a8c7  cmp     [rsp+498h+Dst], 25h ; '%'
0x18006a8cd  jnz     short loc_18006A91F
0x18006a8cf  mov     r8d, r15d; nSize
0x18006a8d2  lea     rdx, [rsp+498h+Dst]; lpDst
0x18006a8d7  lea     rcx, aTemp; "%TEMP%"
0x18006a8de  call    cs:__imp_ExpandEnvironmentStringsW
0x18006a8e4  test    eax, eax
0x18006a8e6  jz      loc_18006A80F
0x18006a8ec  cmp     [rsp+498h+Dst], 25h ; '%'
0x18006a8f2  jnz     short loc_18006A91F
0x18006a8f4  jmp     loc_18006A80F
0x18006a8f9  call    AslPathGetNtSystemRoot
0x18006a8fe  mov     r9, rax
0x18006a901  lea     r8, aSTemp; "%s\\Temp"
0x18006a908  mov     rdx, r15
0x18006a90b  lea     rcx, [rsp+498h+Dst]
0x18006a910  call    RtlStringCchPrintfW
0x18006a915  mov     edi, eax
0x18006a917  test    eax, eax
0x18006a919  js      loc_18006A814
0x18006a91f  call    cs:__imp_GetCurrentProcessId
0x18006a925  mov     [rsp+498h+var_468], eax
0x18006a929  lea     rcx, [rbx+0C0h]
0x18006a930  mov     [rsp+498h+var_470], rsi
0x18006a935  mov     rdx, r15
0x18006a938  lea     rsi, aDevinv; "devinv"
0x18006a93f  lea     r9, [rsp+498h+Dst]
0x18006a944  mov     [rsp+498h+var_478], rsi
0x18006a949  lea     r8, aSAsllogSSDTxt; "%s\\AslLog_%S_%s_%d.txt"
0x18006a950  call    RtlStringCchPrintfW
0x18006a955  mov     edi, eax
0x18006a957  test    eax, eax
0x18006a959  js      loc_18006A814
0x18006a95f  lea     rax, [rbx+8]
0x18006a963  mov     [rbx], rax
0x18006a966  call    AslLogGetDefaultFlags
0x18006a96b  mov     rcx, [rbx]
0x18006a96e  mov     edx, 40h ; '@'
0x18006a973  mov     [rcx+50h], eax
0x18006a976  mov     eax, 7FFFFFFEh
0x18006a97b  mov     rcx, [rbx]
0x18006a97e  test    rax, rax
0x18006a981  jz      short loc_18006A99D
0x18006a983  mov     r8b, [rsi]
0x18006a986  test    r8b, r8b
0x18006a989  jz      short loc_18006A99D
0x18006a98b  mov     [rcx], r8b
0x18006a98e  inc     rsi
0x18006a991  inc     rcx
0x18006a994  dec     rax
0x18006a997  sub     rdx, 1
0x18006a99b  jnz     short loc_18006A97E
0x18006a99d  test    rdx, rdx
0x18006a9a0  lea     rax, [rcx-1]
0x18006a9a4  cmovnz  rax, rcx
0x18006a9a8  mov     byte ptr [rax], 0
0x18006a9ab  mov     ecx, [rbx+0A0h]
0x18006a9b1  cmp     ecx, 1000h
0x18006a9b7  jbe     short loc_18006A9C5
0x18006a9b9  mov     eax, ecx
0x18006a9bb  neg     eax
0x18006a9bd  and     eax, ecx
0x18006a9bf  cmp     ecx, eax
0x18006a9c1  jnz     short loc_18006A9D0
0x18006a9c3  jmp     short loc_18006A9CA
0x18006a9c5  mov     ecx, 1000h
0x18006a9ca  mov     rax, [rbx]
0x18006a9cd  mov     [rax+4Ch], ecx
0x18006a9d0  xor     edi, edi
0x18006a9d2  mov     cs:?g_Logger@@3VAslLogGlobalLogger@@A, rbx; AslLogGlobalLogger g_Logger
0x18006a9d9  jmp     loc_18006A81C
```
