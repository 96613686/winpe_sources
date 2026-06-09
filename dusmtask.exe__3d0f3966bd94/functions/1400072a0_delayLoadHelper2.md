# __delayLoadHelper2

- ea: `0x1400072a0`
- end: `0x14000776a`
- name: `__delayLoadHelper2`
- size: `1226`
- prototype: `FARPROC __fastcall(const ImgDelayDescr *, FARPROC *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001fca`

## callees

- `0x140001f0e`
- `0x1400071bc`
- `0x1400072a0`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400075f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400075f9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000757c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000757c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x140007481`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x140007481`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400072e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007397`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400074de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000765a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400076ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000772d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400072e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007397`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400074de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000765a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400076ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000772d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007311`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400073b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007503`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000767f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400076dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007752`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007311`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400073b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007503`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000767f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400076dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007752`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000753f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000753f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007551`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000760b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000760b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400073cc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140007518`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140007694`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400073cc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140007518`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140007694`

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
    v17.dlp.szProcName = (char *)&word_140000002 + *(unsigned int *)((char *)&_ImageBase + v10);
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
0x1400072a0  push    rbp
0x1400072a2  push    rbx
0x1400072a3  push    rsi
0x1400072a4  push    rdi
0x1400072a5  push    r12
0x1400072a7  push    r13
0x1400072a9  push    r15
0x1400072ab  mov     rbp, rsp
0x1400072ae  sub     rsp, 70h
0x1400072b2  xor     eax, eax
0x1400072b4  mov     r13, rdx
0x1400072b7  mov     rsi, rcx
0x1400072ba  mov     [rbp+var_4C], eax
0x1400072bd  xor     edx, edx; Val
0x1400072bf  lea     rcx, [rbp+var_50]; void *
0x1400072c3  lea     r8d, [rax+44h]; Size
0x1400072c7  call    memset_0
0x1400072cc  test    cs:dword_140009130, 1000h
0x1400072d6  lea     rbx, DloadSrwLock
0x1400072dd  mov     edi, 1
0x1400072e2  jz      short loc_140007317
0x1400072e4  mov     rcx, rbx; SRWLock
0x1400072e7  call    cs:__imp_AcquireSRWLockExclusive
0x1400072ed  mov     eax, cs:DloadSectionLockCount
0x1400072f3  add     eax, edi
0x1400072f5  mov     cs:DloadSectionLockCount, eax
0x1400072fb  cmp     eax, edi
0x1400072fd  jnz     short loc_14000730E
0x1400072ff  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x140007306  lea     ecx, [rdi+3]; flNewProtect
0x140007309  call    DloadProtectSection
0x14000730e  mov     rcx, rbx; SRWLock
0x140007311  call    cs:__imp_ReleaseSRWLockExclusive
0x140007317  mov     eax, [rsi+4]
0x14000731a  lea     rdx, __ImageBase
0x140007321  mov     r15d, [rsi+8]
0x140007325  add     rax, rdx
0x140007328  mov     r12d, [rsi+14h]
0x14000732c  add     r15, rdx
0x14000732f  mov     ecx, [rsi+1Ch]
0x140007332  add     r12, rdx
0x140007335  mov     [rbp+lpLibFileName], rax
0x140007339  mov     eax, [rsi]
0x14000733b  and     eax, edi
0x14000733d  mov     [rbp+arg_0], ecx
0x140007340  mov     [rbp+var_50], 48h ; 'H'
0x140007347  mov     [rbp+var_48], rsi
0x14000734b  mov     [rbp+var_40], r13
0x14000734f  mov     [rbp+var_30], 0
0x140007356  mov     [rbp+lpProcName], 0
0x14000735e  mov     [rbp+var_20], 0
0x140007366  mov     [rbp+var_18], 0
0x14000736e  mov     [rbp+var_10], 0
0x140007375  test    al, al
0x140007377  jnz     short loc_1400073D9
0x140007379  test    cs:dword_140009130, 1000h
0x140007383  lea     rax, [rbp+var_50]
0x140007387  mov     [rbp+Arguments], rax
0x14000738b  mov     dword ptr [rbp+flOldProtect], 0
0x140007392  jz      short loc_1400073BE
0x140007394  mov     rcx, rbx; SRWLock
0x140007397  call    cs:__imp_AcquireSRWLockExclusive
0x14000739d  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1400073a4  jnz     short loc_1400073B5
0x1400073a6  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1400073ac  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1400073b0  call    DloadProtectSection
0x1400073b5  mov     rcx, rbx; SRWLock
0x1400073b8  call    cs:__imp_ReleaseSRWLockExclusive
0x1400073be  lea     r9, [rbp+Arguments]; lpArguments
0x1400073c2  mov     r8d, edi; nNumberOfArguments
0x1400073c5  xor     edx, edx; dwExceptionFlags
0x1400073c7  mov     ecx, 0C06D0057h; dwExceptionCode
0x1400073cc  call    cs:__imp_RaiseException
0x1400073d2  xor     eax, eax
0x1400073d4  jmp     loc_14000775B
0x1400073d9  mov     eax, [rsi+0Ch]
0x1400073dc  mov     rcx, r13
0x1400073df  mov     rbx, [r15]
0x1400073e2  sub     rcx, rax
0x1400073e5  sub     rcx, rdx
0x1400073e8  sar     rcx, 3
0x1400073ec  mov     eax, ecx
0x1400073ee  mov     ecx, [rsi+10h]
0x1400073f1  shl     rax, 3
0x1400073f5  add     rcx, rax
0x1400073f8  mov     [rbp+flOldProtect], rax
0x1400073fc  xor     eax, eax
0x1400073fe  cmp     [rcx+rdx], rax
0x140007402  setnl   al
0x140007405  mov     [rbp+var_30], eax
0x140007408  test    eax, eax
0x14000740a  jz      short loc_14000741F
0x14000740c  mov     eax, [rcx+rdx]
0x14000740f  lea     rdx, word_140000002
0x140007416  add     rax, rdx
0x140007419  mov     [rbp+lpProcName], rax
0x14000741d  jmp     short loc_140007426
0x14000741f  movzx   eax, word ptr [rcx+rdx]
0x140007423  mov     dword ptr [rbp+lpProcName], eax
0x140007426  mov     rax, cs:__pfnDliNotifyHook2
0x14000742d  xor     edi, edi
0x14000742f  test    rax, rax
0x140007432  jz      short loc_140007452
0x140007434  lea     rdx, [rbp+var_50]
0x140007438  xor     ecx, ecx
0x14000743a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000743f  mov     rdi, rax
0x140007442  test    rax, rax
0x140007445  mov     rax, cs:__pfnDliNotifyHook2
0x14000744c  jnz     loc_1400076F1
0x140007452  test    rbx, rbx
0x140007455  jnz     loc_140007590
0x14000745b  test    rax, rax
0x14000745e  jz      short loc_140007478
0x140007460  lea     rdx, [rbp+var_50]
0x140007464  lea     ecx, [rbx+1]
0x140007467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000746c  mov     rbx, rax
0x14000746f  test    rax, rax
0x140007472  jnz     loc_140007527
0x140007478  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x14000747c  xor     r8d, r8d; dwFlags
0x14000747f  xor     edx, edx; hFile
0x140007481  call    cs:__imp_LoadLibraryExA
0x140007487  mov     rbx, rax
0x14000748a  test    rax, rax
0x14000748d  jnz     loc_140007527
0x140007493  call    cs:__imp_GetLastError
0x140007499  mov     [rbp+var_10], eax
0x14000749c  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1400074a3  test    rax, rax
0x1400074a6  jz      short loc_1400074BC
0x1400074a8  lea     rdx, [rbp+var_50]
0x1400074ac  lea     ecx, [rbx+3]
0x1400074af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074b4  mov     rbx, rax
0x1400074b7  test    rax, rax
0x1400074ba  jnz     short loc_140007527
0x1400074bc  test    cs:dword_140009130, 1000h
0x1400074c6  lea     rax, [rbp+var_50]
0x1400074ca  mov     [rbp+Arguments], rax
0x1400074ce  mov     dword ptr [rbp+flOldProtect], 0
0x1400074d5  jz      short loc_140007509
0x1400074d7  lea     rcx, DloadSrwLock; SRWLock
0x1400074de  call    cs:__imp_AcquireSRWLockExclusive
0x1400074e4  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1400074eb  jnz     short loc_1400074FC
0x1400074ed  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1400074f3  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1400074f7  call    DloadProtectSection
0x1400074fc  lea     rcx, DloadSrwLock; SRWLock
0x140007503  call    cs:__imp_ReleaseSRWLockExclusive
0x140007509  xor     edx, edx; dwExceptionFlags
0x14000750b  lea     r9, [rbp+Arguments]; lpArguments
0x14000750f  mov     ecx, 0C06D007Eh; dwExceptionCode
0x140007514  lea     r8d, [rdx+1]; nNumberOfArguments
0x140007518  call    cs:__imp_RaiseException
0x14000751e  mov     rax, [rbp+var_18]
0x140007522  jmp     loc_14000775B
0x140007527  xor     eax, eax
0x140007529  lock cmpxchg [r15], rbx
0x14000752e  mov     r15, rax
0x140007531  jnz     short loc_140007573
0x140007533  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140007537  jz      short loc_140007589
0x140007539  cmp     dword ptr [rsi+18h], 0
0x14000753d  jz      short loc_140007589
0x14000753f  call    cs:__imp_GetProcessHeap
0x140007545  mov     edx, 8; dwFlags
0x14000754a  mov     rcx, rax; hHeap
0x14000754d  lea     r8d, [rdx+8]; dwBytes
0x140007551  call    cs:__imp_HeapAlloc
0x140007557  test    rax, rax
0x14000755a  jz      short loc_140007589
0x14000755c  mov     [rax+8], rsi
0x140007560  mov     rcx, cs:__puiHead
0x140007567  mov     [rax], rcx
0x14000756a  mov     cs:__puiHead, rax
0x140007571  jmp     short loc_140007589
0x140007573  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140007577  jz      short loc_140007582
0x140007579  mov     rcx, rbx; hLibModule
0x14000757c  call    cs:__imp_FreeLibrary
0x140007582  cmp     rbx, r15
0x140007585  cmovnz  rbx, r15
0x140007589  mov     rax, cs:__pfnDliNotifyHook2
0x140007590  mov     [rbp+var_20], rbx
0x140007594  test    rax, rax
0x140007597  jz      short loc_1400075B1
0x140007599  lea     rdx, [rbp+var_50]
0x14000759d  mov     ecx, 2
0x1400075a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400075a7  mov     rdi, rax
0x1400075aa  mov     rax, cs:__pfnDliNotifyHook2
0x1400075b1  test    rdi, rdi
0x1400075b4  jnz     loc_1400076ED
0x1400075ba  cmp     [rsi+14h], edi
0x1400075bd  jz      short loc_1400075F2
0x1400075bf  cmp     [rsi+1Ch], edi
0x1400075c2  jz      short loc_1400075F2
0x1400075c4  movsxd  rcx, dword ptr [rbx+3Ch]
0x1400075c8  cmp     dword ptr [rcx+rbx], 4550h
0x1400075cf  jnz     short loc_1400075F2
0x1400075d1  mov     edx, [rbp+arg_0]
0x1400075d4  cmp     [rcx+rbx+8], edx
0x1400075d8  jnz     short loc_1400075F2
0x1400075da  cmp     rbx, [rcx+rbx+30h]
0x1400075df  jnz     short loc_1400075F2
0x1400075e1  mov     rdi, [rbp+flOldProtect]
0x1400075e5  mov     rdi, [rdi+r12]
0x1400075e9  test    rdi, rdi
0x1400075ec  jnz     loc_1400076ED
0x1400075f2  mov     rdx, [rbp+lpProcName]; lpProcName
0x1400075f6  mov     rcx, rbx; hModule
0x1400075f9  call    cs:__imp_GetProcAddress
0x1400075ff  mov     rdi, rax
0x140007602  test    rax, rax
0x140007605  jnz     loc_1400076E6
0x14000760b  call    cs:__imp_GetLastError
0x140007611  mov     [rbp+var_10], eax
0x140007614  mov     rax, cs:__pfnDefaultDliFailureHook2
0x14000761b  test    rax, rax
0x14000761e  jz      short loc_140007638
0x140007620  lea     rdx, [rbp+var_50]
0x140007624  lea     ecx, [rdi+4]
0x140007627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000762c  mov     rdi, rax
0x14000762f  test    rax, rax
0x140007632  jnz     loc_1400076E6
0x140007638  test    cs:dword_140009130, 1000h
0x140007642  lea     rax, [rbp+var_50]
0x140007646  mov     [rbp+Arguments], rax
0x14000764a  mov     dword ptr [rbp+flOldProtect], 0
0x140007651  jz      short loc_140007685
0x140007653  lea     rcx, DloadSrwLock; SRWLock
0x14000765a  call    cs:__imp_AcquireSRWLockExclusive
0x140007660  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x140007667  jnz     short loc_140007678
0x140007669  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x14000766f  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x140007673  call    DloadProtectSection
0x140007678  lea     rcx, DloadSrwLock; SRWLock
0x14000767f  call    cs:__imp_ReleaseSRWLockExclusive
0x140007685  xor     edx, edx; dwExceptionFlags
0x140007687  lea     r9, [rbp+Arguments]; lpArguments
0x14000768b  mov     ecx, 0C06D007Fh; dwExceptionCode
0x140007690  lea     r8d, [rdx+1]; nNumberOfArguments
0x140007694  call    cs:__imp_RaiseException
0x14000769a  test    cs:dword_140009130, 1000h
0x1400076a4  jz      short loc_1400076E2
0x1400076a6  lea     rcx, DloadSrwLock; SRWLock
0x1400076ad  call    cs:__imp_AcquireSRWLockExclusive
0x1400076b3  mov     eax, cs:DloadSectionLockCount
0x1400076b9  inc     eax
0x1400076bb  mov     cs:DloadSectionLockCount, eax
0x1400076c1  cmp     eax, 1
0x1400076c4  jnz     short loc_1400076D5
0x1400076c6  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x1400076cd  lea     ecx, [rax+3]; flNewProtect
0x1400076d0  call    DloadProtectSection
0x1400076d5  lea     rcx, DloadSrwLock; SRWLock
0x1400076dc  call    cs:__imp_ReleaseSRWLockExclusive
0x1400076e2  mov     rdi, [rbp+var_18]
0x1400076e6  mov     rax, cs:__pfnDliNotifyHook2
0x1400076ed  mov     [r13+0], rdi
0x1400076f1  test    rax, rax
0x1400076f4  jz      short loc_140007713
0x1400076f6  lea     rdx, [rbp+var_50]
0x1400076fa  mov     [rbp+var_10], 0
0x140007701  mov     ecx, 5
0x140007706  mov     [rbp+var_20], rbx
0x14000770a  mov     [rbp+var_18], rdi
0x14000770e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007713  test    cs:dword_140009130, 1000h
0x14000771d  mov     dword ptr [rbp+flOldProtect], 0
0x140007724  jz      short loc_140007758
0x140007726  lea     rcx, DloadSrwLock; SRWLock
0x14000772d  call    cs:__imp_AcquireSRWLockExclusive
0x140007733  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x14000773a  jnz     short loc_14000774B
0x14000773c  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x140007742  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x140007746  call    DloadProtectSection
0x14000774b  lea     rcx, DloadSrwLock; SRWLock
0x140007752  call    cs:__imp_ReleaseSRWLockExclusive
0x140007758  mov     rax, rdi
0x14000775b  add     rsp, 70h
0x14000775f  pop     r15
0x140007761  pop     r13
0x140007763  pop     r12
0x140007765  pop     rdi
0x140007766  pop     rsi
0x140007767  pop     rbx
0x140007768  pop     rbp
0x140007769  retn
```
