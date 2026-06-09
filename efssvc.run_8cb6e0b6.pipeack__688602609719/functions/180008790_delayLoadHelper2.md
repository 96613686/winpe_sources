# __delayLoadHelper2

- ea: `0x180008790`
- end: `0x180008cdf`
- name: `__delayLoadHelper2`
- size: `1359`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002290`
- `0x18000239e`
- `0x18000284f`
- `0x1800028da`

## callees

- `0x1800086a0`
- `0x180008790`
- `0x18000d192`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008b37`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008b37`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008ab4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008ab4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000898f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000898f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b4f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800088d4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008a3e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008bea`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800088d4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008a3e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008bea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800087d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008893`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800089f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008ba4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c95`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800087d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008893`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800089f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008ba4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008807`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800088ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008a23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008bcf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008cc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008807`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800088ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008a23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008bcf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008cc0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008a83`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008a83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a6b`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  volatile signed __int64 *v4; // r15
  DWORD dwTimeStamp; // ecx
  char *v6; // r12
  int v7; // eax
  HMODULE Library; // rbx
  __int64 v10; // rcx
  PfnDliHook v11; // rax
  INT_PTR (__stdcall *ProcAddress)(); // rdi
  signed __int64 v13; // r15
  HANDLE ProcessHeap; // rax
  struct UnloadInfo *v15; // rax
  __int64 v16; // rcx
  struct DelayLoadInfo v17; // [rsp+20h] [rbp-50h] BYREF
  DWORD v18; // [rsp+B0h] [rbp+40h]
  __int64 flOldProtect; // [rsp+B8h] [rbp+48h] BYREF
  ULONG_PTR Arguments; // [rsp+C0h] [rbp+50h] BYREF

  *(&v17.cb + 1) = 0;
  memset_0(&v17, 0, 0x44u);
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( ++DloadSectionLockCount == 1 )
    DloadProtectSection(4u, &DloadSectionOldProtection);
  ReleaseSRWLockExclusive(&DloadSrwLock);
  v4 = (volatile signed __int64 *)((char *)&_ImageBase + a1->rvaHmod);
  dwTimeStamp = a1->dwTimeStamp;
  v6 = (char *)&_ImageBase + a1->rvaBoundIAT;
  v17.szDll = (char *)&_ImageBase + a1->rvaDLLName;
  v7 = a1->grAttrs & 1;
  v18 = dwTimeStamp;
  v17.cb = 72;
  v17.pidd = a1;
  v17.ppfn = a2;
  v17.dlp.fImportByName = 0;
  memset(&v17.dlp.szProcName, 0, 28);
  if ( !(_BYTE)v7 )
  {
    Arguments = (ULONG_PTR)&v17;
    LODWORD(flOldProtect) = 0;
    AcquireSRWLockExclusive(&DloadSrwLock);
    if ( !--DloadSectionLockCount )
      DloadProtectSection(DloadSectionOldProtection, (PDWORD)&flOldProtect);
    ReleaseSRWLockExclusive(&DloadSrwLock);
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v4;
  v10 = 8LL * (unsigned int)(((char *)a2 - a1->rvaIAT - (char *)&_ImageBase) >> 3) + a1->rvaINT;
  flOldProtect = 8LL * (unsigned int)(((char *)a2 - a1->rvaIAT - (char *)&_ImageBase) >> 3);
  v17.dlp.fImportByName = *(_QWORD *)((char *)&_ImageBase + v10) >= 0LL;
  if ( v17.dlp.fImportByName )
    v17.dlp.szProcName = (char *)&word_180000002 + *(unsigned int *)((char *)&_ImageBase + v10);
  else
    v17.dlp.dwOrdinal = *(unsigned __int16 *)((char *)&_ImageBase + v10);
  v11 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( !_pfnDliNotifyHook2 || (ProcAddress = _pfnDliNotifyHook2(0, &v17), v11 = _pfnDliNotifyHook2, !ProcAddress) )
  {
    if ( !Library )
    {
      if ( !v11 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v11)(1, &v17)) == 0 )
      {
        Library = LoadLibraryExA(v17.szDll, 0, 0);
        if ( !Library )
        {
          v17.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, &v17)) == 0 )
          {
            Arguments = (ULONG_PTR)&v17;
            LODWORD(flOldProtect) = 0;
            AcquireSRWLockExclusive(&DloadSrwLock);
            if ( !--DloadSectionLockCount )
              DloadProtectSection(DloadSectionOldProtection, (PDWORD)&flOldProtect);
            ReleaseSRWLockExclusive(&DloadSrwLock);
            RaiseException(0xC06D007E, 0, 1u, &Arguments);
            return v17.pfnCur;
          }
        }
      }
      v13 = _InterlockedCompareExchange64(v4, (signed __int64)Library, 0);
      if ( v13 )
      {
        if ( Library != (HMODULE)-1LL )
          FreeLibrary(Library);
        if ( Library != (HMODULE)v13 )
          Library = (HMODULE)v13;
      }
      else if ( Library != (HMODULE)-1LL )
      {
        if ( a1->rvaUnloadIAT )
        {
          ProcessHeap = GetProcessHeap();
          v15 = (struct UnloadInfo *)HeapAlloc(ProcessHeap, 8u, 0x10u);
          if ( v15 )
          {
            v15->pidd = a1;
            v15->puiNext = _puiHead;
            _puiHead = v15;
          }
        }
      }
      v11 = _pfnDliNotifyHook2;
    }
    v17.hmodCur = Library;
    if ( v11 )
    {
      ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v11)(2, &v17);
      v11 = _pfnDliNotifyHook2;
    }
    if ( !ProcAddress )
    {
      if ( !a1->rvaBoundIAT
        || !a1->dwTimeStamp
        || (v16 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v16) != 17744)
        || *(_DWORD *)((char *)Library + v16 + 8) != v18
        || Library != *(HMODULE *)((char *)Library + v16 + 48)
        || (ProcAddress = *(INT_PTR (__stdcall **)())&v6[flOldProtect]) == 0 )
      {
        ProcAddress = GetProcAddress(Library, v17.dlp.szProcName);
        if ( !ProcAddress )
        {
          v17.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2
            || (ProcAddress = (INT_PTR (__stdcall *)())_pfnDefaultDliFailureHook2(4, &v17)) == 0 )
          {
            Arguments = (ULONG_PTR)&v17;
            LODWORD(flOldProtect) = 0;
            AcquireSRWLockExclusive(&DloadSrwLock);
            if ( !--DloadSectionLockCount )
              DloadProtectSection(DloadSectionOldProtection, (PDWORD)&flOldProtect);
            ReleaseSRWLockExclusive(&DloadSrwLock);
            RaiseException(0xC06D007F, 0, 1u, &Arguments);
            AcquireSRWLockExclusive(&DloadSrwLock);
            if ( ++DloadSectionLockCount == 1 )
              DloadProtectSection(4u, &DloadSectionOldProtection);
            ReleaseSRWLockExclusive(&DloadSrwLock);
            ProcAddress = v17.pfnCur;
          }
        }
        v11 = _pfnDliNotifyHook2;
      }
    }
    *a2 = ProcAddress;
  }
  if ( v11 )
  {
    v17.dwLastError = 0;
    v17.hmodCur = Library;
    v17.pfnCur = ProcAddress;
    ((void (__fastcall *)(__int64, struct DelayLoadInfo *))v11)(5, &v17);
  }
  LODWORD(flOldProtect) = 0;
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( !--DloadSectionLockCount )
    DloadProtectSection(DloadSectionOldProtection, (PDWORD)&flOldProtect);
  ReleaseSRWLockExclusive(&DloadSrwLock);
  return ProcAddress;
}

```

## disassembly

```asm
0x180008790  push    rbp
0x180008792  push    rbx
0x180008793  push    rsi
0x180008794  push    rdi
0x180008795  push    r12
0x180008797  push    r13
0x180008799  push    r15
0x18000879b  mov     rbp, rsp
0x18000879e  sub     rsp, 70h
0x1800087a2  xor     eax, eax
0x1800087a4  mov     r13, rdx
0x1800087a7  mov     rsi, rcx
0x1800087aa  mov     [rbp+var_4C], eax
0x1800087ad  xor     edx, edx; Val
0x1800087af  lea     rcx, [rbp+var_50]; void *
0x1800087b3  lea     r8d, [rax+44h]; Size
0x1800087b7  call    memset_0
0x1800087bc  test    cs:dword_18000F0A0, 1000h
0x1800087c6  lea     rbx, DloadSrwLock
0x1800087cd  mov     edi, 1
0x1800087d2  jz      short loc_180008813
0x1800087d4  mov     rcx, rbx; SRWLock
0x1800087d7  call    cs:__imp_AcquireSRWLockExclusive
0x1800087de  nop     dword ptr [rax+rax+00h]
0x1800087e3  mov     eax, cs:DloadSectionLockCount
0x1800087e9  add     eax, edi
0x1800087eb  mov     cs:DloadSectionLockCount, eax
0x1800087f1  cmp     eax, edi
0x1800087f3  jnz     short loc_180008804
0x1800087f5  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x1800087fc  lea     ecx, [rdi+3]; flNewProtect
0x1800087ff  call    DloadProtectSection
0x180008804  mov     rcx, rbx; SRWLock
0x180008807  call    cs:__imp_ReleaseSRWLockExclusive
0x18000880e  nop     dword ptr [rax+rax+00h]
0x180008813  mov     eax, [rsi+4]
0x180008816  lea     rdx, __ImageBase
0x18000881d  mov     r15d, [rsi+8]
0x180008821  add     rax, rdx
0x180008824  mov     r12d, [rsi+14h]
0x180008828  add     r15, rdx
0x18000882b  mov     ecx, [rsi+1Ch]
0x18000882e  add     r12, rdx
0x180008831  mov     [rbp+lpLibFileName], rax
0x180008835  mov     eax, [rsi]
0x180008837  and     eax, edi
0x180008839  mov     [rbp+arg_0], ecx
0x18000883c  mov     [rbp+var_50], 48h ; 'H'
0x180008843  mov     [rbp+var_48], rsi
0x180008847  mov     [rbp+var_40], r13
0x18000884b  mov     [rbp+var_30], 0
0x180008852  mov     [rbp+lpProcName], 0
0x18000885a  mov     [rbp+var_20], 0
0x180008862  mov     [rbp+var_18], 0
0x18000886a  mov     [rbp+var_10], 0
0x180008871  test    al, al
0x180008873  jnz     short loc_1800088E7
0x180008875  test    cs:dword_18000F0A0, 1000h
0x18000887f  lea     rax, [rbp+var_50]
0x180008883  mov     [rbp+Arguments], rax
0x180008887  mov     dword ptr [rbp+flOldProtect], 0
0x18000888e  jz      short loc_1800088C6
0x180008890  mov     rcx, rbx; SRWLock
0x180008893  call    cs:__imp_AcquireSRWLockExclusive
0x18000889a  nop     dword ptr [rax+rax+00h]
0x18000889f  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800088a6  jnz     short loc_1800088B7
0x1800088a8  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800088ae  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800088b2  call    DloadProtectSection
0x1800088b7  mov     rcx, rbx; SRWLock
0x1800088ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1800088c1  nop     dword ptr [rax+rax+00h]
0x1800088c6  lea     r9, [rbp+Arguments]; lpArguments
0x1800088ca  mov     r8d, edi; nNumberOfArguments
0x1800088cd  xor     edx, edx; dwExceptionFlags
0x1800088cf  mov     ecx, 0C06D0057h; dwExceptionCode
0x1800088d4  call    cs:__imp_RaiseException
0x1800088db  nop     dword ptr [rax+rax+00h]
0x1800088e0  xor     eax, eax
0x1800088e2  jmp     loc_180008CCF
0x1800088e7  mov     eax, [rsi+0Ch]
0x1800088ea  mov     rcx, r13
0x1800088ed  mov     rbx, [r15]
0x1800088f0  sub     rcx, rax
0x1800088f3  sub     rcx, rdx
0x1800088f6  sar     rcx, 3
0x1800088fa  mov     eax, ecx
0x1800088fc  mov     ecx, [rsi+10h]
0x1800088ff  shl     rax, 3
0x180008903  add     rcx, rax
0x180008906  mov     [rbp+flOldProtect], rax
0x18000890a  xor     eax, eax
0x18000890c  cmp     [rcx+rdx], rax
0x180008910  setnl   al
0x180008913  mov     [rbp+var_30], eax
0x180008916  test    eax, eax
0x180008918  jz      short loc_18000892D
0x18000891a  mov     eax, [rcx+rdx]
0x18000891d  lea     rdx, word_180000002
0x180008924  add     rax, rdx
0x180008927  mov     [rbp+lpProcName], rax
0x18000892b  jmp     short loc_180008934
0x18000892d  movzx   eax, word ptr [rcx+rdx]
0x180008931  mov     dword ptr [rbp+lpProcName], eax
0x180008934  mov     rax, cs:__pfnDliNotifyHook2
0x18000893b  xor     edi, edi
0x18000893d  test    rax, rax
0x180008940  jz      short loc_180008960
0x180008942  lea     rdx, [rbp+var_50]
0x180008946  xor     ecx, ecx
0x180008948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000894d  mov     rdi, rax
0x180008950  test    rax, rax
0x180008953  mov     rax, cs:__pfnDliNotifyHook2
0x18000895a  jnz     loc_180008C59
0x180008960  test    rbx, rbx
0x180008963  jnz     loc_180008ACE
0x180008969  test    rax, rax
0x18000896c  jz      short loc_180008986
0x18000896e  lea     rdx, [rbp+var_50]
0x180008972  lea     ecx, [rbx+1]
0x180008975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000897a  mov     rbx, rax
0x18000897d  test    rax, rax
0x180008980  jnz     loc_180008A53
0x180008986  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000898a  xor     r8d, r8d; dwFlags
0x18000898d  xor     edx, edx; hFile
0x18000898f  call    cs:__imp_LoadLibraryExA
0x180008996  nop     dword ptr [rax+rax+00h]
0x18000899b  mov     rbx, rax
0x18000899e  test    rax, rax
0x1800089a1  jnz     loc_180008A53
0x1800089a7  call    cs:__imp_GetLastError
0x1800089ae  nop     dword ptr [rax+rax+00h]
0x1800089b3  mov     [rbp+var_10], eax
0x1800089b6  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800089bd  test    rax, rax
0x1800089c0  jz      short loc_1800089D6
0x1800089c2  lea     rdx, [rbp+var_50]
0x1800089c6  lea     ecx, [rbx+3]
0x1800089c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089ce  mov     rbx, rax
0x1800089d1  test    rax, rax
0x1800089d4  jnz     short loc_180008A53
0x1800089d6  test    cs:dword_18000F0A0, 1000h
0x1800089e0  lea     rax, [rbp+var_50]
0x1800089e4  mov     [rbp+Arguments], rax
0x1800089e8  mov     dword ptr [rbp+flOldProtect], 0
0x1800089ef  jz      short loc_180008A2F
0x1800089f1  lea     rcx, DloadSrwLock; SRWLock
0x1800089f8  call    cs:__imp_AcquireSRWLockExclusive
0x1800089ff  nop     dword ptr [rax+rax+00h]
0x180008a04  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180008a0b  jnz     short loc_180008A1C
0x180008a0d  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180008a13  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180008a17  call    DloadProtectSection
0x180008a1c  lea     rcx, DloadSrwLock; SRWLock
0x180008a23  call    cs:__imp_ReleaseSRWLockExclusive
0x180008a2a  nop     dword ptr [rax+rax+00h]
0x180008a2f  xor     edx, edx; dwExceptionFlags
0x180008a31  lea     r9, [rbp+Arguments]; lpArguments
0x180008a35  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180008a3a  lea     r8d, [rdx+1]; nNumberOfArguments
0x180008a3e  call    cs:__imp_RaiseException
0x180008a45  nop     dword ptr [rax+rax+00h]
0x180008a4a  mov     rax, [rbp+var_18]
0x180008a4e  jmp     loc_180008CCF
0x180008a53  xor     eax, eax
0x180008a55  lock cmpxchg [r15], rbx
0x180008a5a  mov     r15, rax
0x180008a5d  jnz     short loc_180008AAB
0x180008a5f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180008a63  jz      short loc_180008AC7
0x180008a65  cmp     dword ptr [rsi+18h], 0
0x180008a69  jz      short loc_180008AC7
0x180008a6b  call    cs:__imp_GetProcessHeap
0x180008a72  nop     dword ptr [rax+rax+00h]
0x180008a77  mov     edx, 8; dwFlags
0x180008a7c  mov     rcx, rax; hHeap
0x180008a7f  lea     r8d, [rdx+8]; dwBytes
0x180008a83  call    cs:__imp_HeapAlloc
0x180008a8a  nop     dword ptr [rax+rax+00h]
0x180008a8f  test    rax, rax
0x180008a92  jz      short loc_180008AC7
0x180008a94  mov     [rax+8], rsi
0x180008a98  mov     rcx, cs:__puiHead
0x180008a9f  mov     [rax], rcx
0x180008aa2  mov     cs:__puiHead, rax
0x180008aa9  jmp     short loc_180008AC7
0x180008aab  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180008aaf  jz      short loc_180008AC0
0x180008ab1  mov     rcx, rbx; hLibModule
0x180008ab4  call    cs:__imp_FreeLibrary
0x180008abb  nop     dword ptr [rax+rax+00h]
0x180008ac0  cmp     rbx, r15
0x180008ac3  cmovnz  rbx, r15
0x180008ac7  mov     rax, cs:__pfnDliNotifyHook2
0x180008ace  mov     [rbp+var_20], rbx
0x180008ad2  test    rax, rax
0x180008ad5  jz      short loc_180008AEF
0x180008ad7  lea     rdx, [rbp+var_50]
0x180008adb  mov     ecx, 2
0x180008ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ae5  mov     rdi, rax
0x180008ae8  mov     rax, cs:__pfnDliNotifyHook2
0x180008aef  test    rdi, rdi
0x180008af2  jnz     loc_180008C55
0x180008af8  cmp     [rsi+14h], edi
0x180008afb  jz      short loc_180008B30
0x180008afd  cmp     [rsi+1Ch], edi
0x180008b00  jz      short loc_180008B30
0x180008b02  movsxd  rcx, dword ptr [rbx+3Ch]
0x180008b06  cmp     dword ptr [rcx+rbx], 4550h
0x180008b0d  jnz     short loc_180008B30
0x180008b0f  mov     edx, [rbp+arg_0]
0x180008b12  cmp     [rcx+rbx+8], edx
0x180008b16  jnz     short loc_180008B30
0x180008b18  cmp     rbx, [rcx+rbx+30h]
0x180008b1d  jnz     short loc_180008B30
0x180008b1f  mov     rdi, [rbp+flOldProtect]
0x180008b23  mov     rdi, [rdi+r12]
0x180008b27  test    rdi, rdi
0x180008b2a  jnz     loc_180008C55
0x180008b30  mov     rdx, [rbp+lpProcName]; lpProcName
0x180008b34  mov     rcx, rbx; hModule
0x180008b37  call    cs:__imp_GetProcAddress
0x180008b3e  nop     dword ptr [rax+rax+00h]
0x180008b43  mov     rdi, rax
0x180008b46  test    rax, rax
0x180008b49  jnz     loc_180008C4E
0x180008b4f  call    cs:__imp_GetLastError
0x180008b56  nop     dword ptr [rax+rax+00h]
0x180008b5b  mov     [rbp+var_10], eax
0x180008b5e  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180008b65  test    rax, rax
0x180008b68  jz      short loc_180008B82
0x180008b6a  lea     rdx, [rbp+var_50]
0x180008b6e  lea     ecx, [rdi+4]
0x180008b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b76  mov     rdi, rax
0x180008b79  test    rax, rax
0x180008b7c  jnz     loc_180008C4E
0x180008b82  test    cs:dword_18000F0A0, 1000h
0x180008b8c  lea     rax, [rbp+var_50]
0x180008b90  mov     [rbp+Arguments], rax
0x180008b94  mov     dword ptr [rbp+flOldProtect], 0
0x180008b9b  jz      short loc_180008BDB
0x180008b9d  lea     rcx, DloadSrwLock; SRWLock
0x180008ba4  call    cs:__imp_AcquireSRWLockExclusive
0x180008bab  nop     dword ptr [rax+rax+00h]
0x180008bb0  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180008bb7  jnz     short loc_180008BC8
0x180008bb9  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180008bbf  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180008bc3  call    DloadProtectSection
0x180008bc8  lea     rcx, DloadSrwLock; SRWLock
0x180008bcf  call    cs:__imp_ReleaseSRWLockExclusive
0x180008bd6  nop     dword ptr [rax+rax+00h]
0x180008bdb  xor     edx, edx; dwExceptionFlags
0x180008bdd  lea     r9, [rbp+Arguments]; lpArguments
0x180008be1  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180008be6  lea     r8d, [rdx+1]; nNumberOfArguments
0x180008bea  call    cs:__imp_RaiseException
0x180008bf1  nop     dword ptr [rax+rax+00h]
0x180008bf6  test    cs:dword_18000F0A0, 1000h
0x180008c00  jz      short loc_180008C4A
0x180008c02  lea     rcx, DloadSrwLock; SRWLock
0x180008c09  call    cs:__imp_AcquireSRWLockExclusive
0x180008c10  nop     dword ptr [rax+rax+00h]
0x180008c15  mov     eax, cs:DloadSectionLockCount
0x180008c1b  inc     eax
0x180008c1d  mov     cs:DloadSectionLockCount, eax
0x180008c23  cmp     eax, 1
0x180008c26  jnz     short loc_180008C37
0x180008c28  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x180008c2f  lea     ecx, [rax+3]; flNewProtect
0x180008c32  call    DloadProtectSection
0x180008c37  lea     rcx, DloadSrwLock; SRWLock
0x180008c3e  call    cs:__imp_ReleaseSRWLockExclusive
0x180008c45  nop     dword ptr [rax+rax+00h]
0x180008c4a  mov     rdi, [rbp+var_18]
0x180008c4e  mov     rax, cs:__pfnDliNotifyHook2
0x180008c55  mov     [r13+0], rdi
0x180008c59  test    rax, rax
0x180008c5c  jz      short loc_180008C7B
0x180008c5e  lea     rdx, [rbp+var_50]
0x180008c62  mov     [rbp+var_10], 0
0x180008c69  mov     ecx, 5
0x180008c6e  mov     [rbp+var_20], rbx
0x180008c72  mov     [rbp+var_18], rdi
0x180008c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c7b  test    cs:dword_18000F0A0, 1000h
0x180008c85  mov     dword ptr [rbp+flOldProtect], 0
0x180008c8c  jz      short loc_180008CCC
0x180008c8e  lea     rcx, DloadSrwLock; SRWLock
0x180008c95  call    cs:__imp_AcquireSRWLockExclusive
0x180008c9c  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
