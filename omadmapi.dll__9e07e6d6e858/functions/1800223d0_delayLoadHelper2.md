# __delayLoadHelper2

- ea: `0x1800223d0`
- end: `0x18002291f`
- name: `__delayLoadHelper2`
- size: `1359`
- prototype: ``
- caller_count: `15`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003ea5`
- `0x180003f54`
- `0x180004003`
- `0x18000408e`
- `0x18000414f`
- `0x1800041da`
- `0x1800042f5`
- `0x1800043a4`
- `0x180004489`
- `0x180004514`
- `0x1800045f9`
- `0x1800047fe`
- `0x1800048e3`
- `0x18000496e`
- `0x1800049f9`

## callees

- `0x180003db8`
- `0x1800222e4`
- `0x1800223d0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800225cf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800225cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800226f4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800226f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022777`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022777`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800226c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800226c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800226ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800226ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022514`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002267e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002282a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022514`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002267e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002282a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002278f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002278f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022447`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800224fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022663`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002280f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002287e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022900`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022447`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800224fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022663`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002280f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002287e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022900`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022417`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800224d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022638`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800227e4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022849`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800228d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022417`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800224d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022638`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800227e4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022849`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800228d5`

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
0x1800223d0  push    rbp
0x1800223d2  push    rbx
0x1800223d3  push    rsi
0x1800223d4  push    rdi
0x1800223d5  push    r12
0x1800223d7  push    r13
0x1800223d9  push    r15
0x1800223db  mov     rbp, rsp
0x1800223de  sub     rsp, 70h
0x1800223e2  xor     eax, eax
0x1800223e4  mov     r13, rdx
0x1800223e7  mov     rsi, rcx
0x1800223ea  mov     [rbp+var_4C], eax
0x1800223ed  xor     edx, edx; Val
0x1800223ef  lea     rcx, [rbp+var_50]; void *
0x1800223f3  lea     r8d, [rax+44h]; Size
0x1800223f7  call    memset_0
0x1800223fc  test    cs:dword_1800250F0, 1000h
0x180022406  lea     rbx, DloadSrwLock
0x18002240d  mov     edi, 1
0x180022412  jz      short loc_180022453
0x180022414  mov     rcx, rbx; SRWLock
0x180022417  call    cs:__imp_AcquireSRWLockExclusive
0x18002241e  nop     dword ptr [rax+rax+00h]
0x180022423  mov     eax, cs:DloadSectionLockCount
0x180022429  add     eax, edi
0x18002242b  mov     cs:DloadSectionLockCount, eax
0x180022431  cmp     eax, edi
0x180022433  jnz     short loc_180022444
0x180022435  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18002243c  lea     ecx, [rdi+3]; flNewProtect
0x18002243f  call    DloadProtectSection
0x180022444  mov     rcx, rbx; SRWLock
0x180022447  call    cs:__imp_ReleaseSRWLockExclusive
0x18002244e  nop     dword ptr [rax+rax+00h]
0x180022453  mov     eax, [rsi+4]
0x180022456  lea     rdx, __ImageBase
0x18002245d  mov     r15d, [rsi+8]
0x180022461  add     rax, rdx
0x180022464  mov     r12d, [rsi+14h]
0x180022468  add     r15, rdx
0x18002246b  mov     ecx, [rsi+1Ch]
0x18002246e  add     r12, rdx
0x180022471  mov     [rbp+lpLibFileName], rax
0x180022475  mov     eax, [rsi]
0x180022477  and     eax, edi
0x180022479  mov     [rbp+arg_0], ecx
0x18002247c  mov     [rbp+var_50], 48h ; 'H'
0x180022483  mov     [rbp+var_48], rsi
0x180022487  mov     [rbp+var_40], r13
0x18002248b  mov     [rbp+var_30], 0
0x180022492  mov     [rbp+lpProcName], 0
0x18002249a  mov     [rbp+var_20], 0
0x1800224a2  mov     [rbp+var_18], 0
0x1800224aa  mov     [rbp+var_10], 0
0x1800224b1  test    al, al
0x1800224b3  jnz     short loc_180022527
0x1800224b5  test    cs:dword_1800250F0, 1000h
0x1800224bf  lea     rax, [rbp+var_50]
0x1800224c3  mov     [rbp+Arguments], rax
0x1800224c7  mov     dword ptr [rbp+flOldProtect], 0
0x1800224ce  jz      short loc_180022506
0x1800224d0  mov     rcx, rbx; SRWLock
0x1800224d3  call    cs:__imp_AcquireSRWLockExclusive
0x1800224da  nop     dword ptr [rax+rax+00h]
0x1800224df  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800224e6  jnz     short loc_1800224F7
0x1800224e8  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800224ee  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800224f2  call    DloadProtectSection
0x1800224f7  mov     rcx, rbx; SRWLock
0x1800224fa  call    cs:__imp_ReleaseSRWLockExclusive
0x180022501  nop     dword ptr [rax+rax+00h]
0x180022506  lea     r9, [rbp+Arguments]; lpArguments
0x18002250a  mov     r8d, edi; nNumberOfArguments
0x18002250d  xor     edx, edx; dwExceptionFlags
0x18002250f  mov     ecx, 0C06D0057h; dwExceptionCode
0x180022514  call    cs:__imp_RaiseException
0x18002251b  nop     dword ptr [rax+rax+00h]
0x180022520  xor     eax, eax
0x180022522  jmp     loc_18002290F
0x180022527  mov     eax, [rsi+0Ch]
0x18002252a  mov     rcx, r13
0x18002252d  mov     rbx, [r15]
0x180022530  sub     rcx, rax
0x180022533  sub     rcx, rdx
0x180022536  sar     rcx, 3
0x18002253a  mov     eax, ecx
0x18002253c  mov     ecx, [rsi+10h]
0x18002253f  shl     rax, 3
0x180022543  add     rcx, rax
0x180022546  mov     [rbp+flOldProtect], rax
0x18002254a  xor     eax, eax
0x18002254c  cmp     [rcx+rdx], rax
0x180022550  setnl   al
0x180022553  mov     [rbp+var_30], eax
0x180022556  test    eax, eax
0x180022558  jz      short loc_18002256D
0x18002255a  mov     eax, [rcx+rdx]
0x18002255d  lea     rdx, word_180000002
0x180022564  add     rax, rdx
0x180022567  mov     [rbp+lpProcName], rax
0x18002256b  jmp     short loc_180022574
0x18002256d  movzx   eax, word ptr [rcx+rdx]
0x180022571  mov     dword ptr [rbp+lpProcName], eax
0x180022574  mov     rax, cs:__pfnDliNotifyHook2
0x18002257b  xor     edi, edi
0x18002257d  test    rax, rax
0x180022580  jz      short loc_1800225A0
0x180022582  lea     rdx, [rbp+var_50]
0x180022586  xor     ecx, ecx
0x180022588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002258d  mov     rdi, rax
0x180022590  test    rax, rax
0x180022593  mov     rax, cs:__pfnDliNotifyHook2
0x18002259a  jnz     loc_180022899
0x1800225a0  test    rbx, rbx
0x1800225a3  jnz     loc_18002270E
0x1800225a9  test    rax, rax
0x1800225ac  jz      short loc_1800225C6
0x1800225ae  lea     rdx, [rbp+var_50]
0x1800225b2  lea     ecx, [rbx+1]
0x1800225b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225ba  mov     rbx, rax
0x1800225bd  test    rax, rax
0x1800225c0  jnz     loc_180022693
0x1800225c6  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800225ca  xor     r8d, r8d; dwFlags
0x1800225cd  xor     edx, edx; hFile
0x1800225cf  call    cs:__imp_LoadLibraryExA
0x1800225d6  nop     dword ptr [rax+rax+00h]
0x1800225db  mov     rbx, rax
0x1800225de  test    rax, rax
0x1800225e1  jnz     loc_180022693
0x1800225e7  call    cs:__imp_GetLastError
0x1800225ee  nop     dword ptr [rax+rax+00h]
0x1800225f3  mov     [rbp+var_10], eax
0x1800225f6  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800225fd  test    rax, rax
0x180022600  jz      short loc_180022616
0x180022602  lea     rdx, [rbp+var_50]
0x180022606  lea     ecx, [rbx+3]
0x180022609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002260e  mov     rbx, rax
0x180022611  test    rax, rax
0x180022614  jnz     short loc_180022693
0x180022616  test    cs:dword_1800250F0, 1000h
0x180022620  lea     rax, [rbp+var_50]
0x180022624  mov     [rbp+Arguments], rax
0x180022628  mov     dword ptr [rbp+flOldProtect], 0
0x18002262f  jz      short loc_18002266F
0x180022631  lea     rcx, DloadSrwLock; SRWLock
0x180022638  call    cs:__imp_AcquireSRWLockExclusive
0x18002263f  nop     dword ptr [rax+rax+00h]
0x180022644  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18002264b  jnz     short loc_18002265C
0x18002264d  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180022653  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180022657  call    DloadProtectSection
0x18002265c  lea     rcx, DloadSrwLock; SRWLock
0x180022663  call    cs:__imp_ReleaseSRWLockExclusive
0x18002266a  nop     dword ptr [rax+rax+00h]
0x18002266f  xor     edx, edx; dwExceptionFlags
0x180022671  lea     r9, [rbp+Arguments]; lpArguments
0x180022675  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18002267a  lea     r8d, [rdx+1]; nNumberOfArguments
0x18002267e  call    cs:__imp_RaiseException
0x180022685  nop     dword ptr [rax+rax+00h]
0x18002268a  mov     rax, [rbp+var_18]
0x18002268e  jmp     loc_18002290F
0x180022693  xor     eax, eax
0x180022695  lock cmpxchg [r15], rbx
0x18002269a  mov     r15, rax
0x18002269d  jnz     short loc_1800226EB
0x18002269f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800226a3  jz      short loc_180022707
0x1800226a5  cmp     dword ptr [rsi+18h], 0
0x1800226a9  jz      short loc_180022707
0x1800226ab  call    cs:__imp_GetProcessHeap
0x1800226b2  nop     dword ptr [rax+rax+00h]
0x1800226b7  mov     edx, 8; dwFlags
0x1800226bc  mov     rcx, rax; hHeap
0x1800226bf  lea     r8d, [rdx+8]; dwBytes
0x1800226c3  call    cs:__imp_HeapAlloc
0x1800226ca  nop     dword ptr [rax+rax+00h]
0x1800226cf  test    rax, rax
0x1800226d2  jz      short loc_180022707
0x1800226d4  mov     [rax+8], rsi
0x1800226d8  mov     rcx, cs:__puiHead
0x1800226df  mov     [rax], rcx
0x1800226e2  mov     cs:__puiHead, rax
0x1800226e9  jmp     short loc_180022707
0x1800226eb  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800226ef  jz      short loc_180022700
0x1800226f1  mov     rcx, rbx; hLibModule
0x1800226f4  call    cs:__imp_FreeLibrary
0x1800226fb  nop     dword ptr [rax+rax+00h]
0x180022700  cmp     rbx, r15
0x180022703  cmovnz  rbx, r15
0x180022707  mov     rax, cs:__pfnDliNotifyHook2
0x18002270e  mov     [rbp+var_20], rbx
0x180022712  test    rax, rax
0x180022715  jz      short loc_18002272F
0x180022717  lea     rdx, [rbp+var_50]
0x18002271b  mov     ecx, 2
0x180022720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022725  mov     rdi, rax
0x180022728  mov     rax, cs:__pfnDliNotifyHook2
0x18002272f  test    rdi, rdi
0x180022732  jnz     loc_180022895
0x180022738  cmp     [rsi+14h], edi
0x18002273b  jz      short loc_180022770
0x18002273d  cmp     [rsi+1Ch], edi
0x180022740  jz      short loc_180022770
0x180022742  movsxd  rcx, dword ptr [rbx+3Ch]
0x180022746  cmp     dword ptr [rcx+rbx], 4550h
0x18002274d  jnz     short loc_180022770
0x18002274f  mov     edx, [rbp+arg_0]
0x180022752  cmp     [rcx+rbx+8], edx
0x180022756  jnz     short loc_180022770
0x180022758  cmp     rbx, [rcx+rbx+30h]
0x18002275d  jnz     short loc_180022770
0x18002275f  mov     rdi, [rbp+flOldProtect]
0x180022763  mov     rdi, [rdi+r12]
0x180022767  test    rdi, rdi
0x18002276a  jnz     loc_180022895
0x180022770  mov     rdx, [rbp+lpProcName]; lpProcName
0x180022774  mov     rcx, rbx; hModule
0x180022777  call    cs:__imp_GetProcAddress
0x18002277e  nop     dword ptr [rax+rax+00h]
0x180022783  mov     rdi, rax
0x180022786  test    rax, rax
0x180022789  jnz     loc_18002288E
0x18002278f  call    cs:__imp_GetLastError
0x180022796  nop     dword ptr [rax+rax+00h]
0x18002279b  mov     [rbp+var_10], eax
0x18002279e  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800227a5  test    rax, rax
0x1800227a8  jz      short loc_1800227C2
0x1800227aa  lea     rdx, [rbp+var_50]
0x1800227ae  lea     ecx, [rdi+4]
0x1800227b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227b6  mov     rdi, rax
0x1800227b9  test    rax, rax
0x1800227bc  jnz     loc_18002288E
0x1800227c2  test    cs:dword_1800250F0, 1000h
0x1800227cc  lea     rax, [rbp+var_50]
0x1800227d0  mov     [rbp+Arguments], rax
0x1800227d4  mov     dword ptr [rbp+flOldProtect], 0
0x1800227db  jz      short loc_18002281B
0x1800227dd  lea     rcx, DloadSrwLock; SRWLock
0x1800227e4  call    cs:__imp_AcquireSRWLockExclusive
0x1800227eb  nop     dword ptr [rax+rax+00h]
0x1800227f0  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800227f7  jnz     short loc_180022808
0x1800227f9  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800227ff  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180022803  call    DloadProtectSection
0x180022808  lea     rcx, DloadSrwLock; SRWLock
0x18002280f  call    cs:__imp_ReleaseSRWLockExclusive
0x180022816  nop     dword ptr [rax+rax+00h]
0x18002281b  xor     edx, edx; dwExceptionFlags
0x18002281d  lea     r9, [rbp+Arguments]; lpArguments
0x180022821  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180022826  lea     r8d, [rdx+1]; nNumberOfArguments
0x18002282a  call    cs:__imp_RaiseException
0x180022831  nop     dword ptr [rax+rax+00h]
0x180022836  test    cs:dword_1800250F0, 1000h
0x180022840  jz      short loc_18002288A
0x180022842  lea     rcx, DloadSrwLock; SRWLock
0x180022849  call    cs:__imp_AcquireSRWLockExclusive
0x180022850  nop     dword ptr [rax+rax+00h]
0x180022855  mov     eax, cs:DloadSectionLockCount
0x18002285b  inc     eax
0x18002285d  mov     cs:DloadSectionLockCount, eax
0x180022863  cmp     eax, 1
0x180022866  jnz     short loc_180022877
0x180022868  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18002286f  lea     ecx, [rax+3]; flNewProtect
0x180022872  call    DloadProtectSection
0x180022877  lea     rcx, DloadSrwLock; SRWLock
0x18002287e  call    cs:__imp_ReleaseSRWLockExclusive
0x180022885  nop     dword ptr [rax+rax+00h]
0x18002288a  mov     rdi, [rbp+var_18]
0x18002288e  mov     rax, cs:__pfnDliNotifyHook2
0x180022895  mov     [r13+0], rdi
0x180022899  test    rax, rax
0x18002289c  jz      short loc_1800228BB
0x18002289e  lea     rdx, [rbp+var_50]
0x1800228a2  mov     [rbp+var_10], 0
0x1800228a9  mov     ecx, 5
0x1800228ae  mov     [rbp+var_20], rbx
0x1800228b2  mov     [rbp+var_18], rdi
0x1800228b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228bb  test    cs:dword_1800250F0, 1000h
0x1800228c5  mov     dword ptr [rbp+flOldProtect], 0
0x1800228cc  jz      short loc_18002290C
0x1800228ce  lea     rcx, DloadSrwLock; SRWLock
0x1800228d5  call    cs:__imp_AcquireSRWLockExclusive
0x1800228dc  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
