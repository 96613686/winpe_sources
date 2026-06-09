# __delayLoadHelper2

- ea: `0x180003480`
- end: `0x18000394a`
- name: `__delayLoadHelper2`
- size: `1226`
- prototype: `FARPROC __fastcall(const ImgDelayDescr *, FARPROC *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001940`

## callees

- `0x180003394`
- `0x180003480`
- `0x180003a86`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003731`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003731`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000371f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000371f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800034c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003577`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800036be`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000383a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000388d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000390d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800034c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003577`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800036be`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000383a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000388d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000390d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800034f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003598`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800036e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000385f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800038bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003932`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800034f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003598`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800036e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000385f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800038bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003932`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000375c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000375c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800037d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800037d9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180003661`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180003661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037eb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800035ac`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800036f8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003874`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800035ac`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800036f8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003874`

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
    v17.dlp.dwOrdinal = *(WCHAR *)((char *)&_ImageBase + v10);
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
0x180003480  push    rbp
0x180003482  push    rbx
0x180003483  push    rsi
0x180003484  push    rdi
0x180003485  push    r12
0x180003487  push    r13
0x180003489  push    r15
0x18000348b  mov     rbp, rsp
0x18000348e  sub     rsp, 70h
0x180003492  xor     eax, eax
0x180003494  mov     r13, rdx
0x180003497  mov     rsi, rcx
0x18000349a  mov     [rbp+var_4C], eax
0x18000349d  xor     edx, edx; Val
0x18000349f  lea     rcx, [rbp+var_50]; void *
0x1800034a3  lea     r8d, [rax+44h]; Size
0x1800034a7  call    memset_0
0x1800034ac  test    cs:dword_1800050D0, 1000h
0x1800034b6  lea     rbx, DloadSrwLock
0x1800034bd  mov     edi, 1
0x1800034c2  jz      short loc_1800034F7
0x1800034c4  mov     rcx, rbx; SRWLock
0x1800034c7  call    cs:__imp_AcquireSRWLockExclusive
0x1800034cd  mov     eax, cs:DloadSectionLockCount
0x1800034d3  add     eax, edi
0x1800034d5  mov     cs:DloadSectionLockCount, eax
0x1800034db  cmp     eax, edi
0x1800034dd  jnz     short loc_1800034EE
0x1800034df  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x1800034e6  lea     ecx, [rdi+3]; flNewProtect
0x1800034e9  call    DloadProtectSection
0x1800034ee  mov     rcx, rbx; SRWLock
0x1800034f1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800034f7  mov     eax, [rsi+4]
0x1800034fa  lea     rdx, __ImageBase
0x180003501  mov     r15d, [rsi+8]
0x180003505  add     rax, rdx
0x180003508  mov     r12d, [rsi+14h]
0x18000350c  add     r15, rdx
0x18000350f  mov     ecx, [rsi+1Ch]
0x180003512  add     r12, rdx
0x180003515  mov     [rbp+lpLibFileName], rax
0x180003519  mov     eax, [rsi]
0x18000351b  and     eax, edi
0x18000351d  mov     [rbp+arg_0], ecx
0x180003520  mov     [rbp+var_50], 48h ; 'H'
0x180003527  mov     [rbp+var_48], rsi
0x18000352b  mov     [rbp+var_40], r13
0x18000352f  mov     [rbp+var_30], 0
0x180003536  mov     [rbp+lpProcName], 0
0x18000353e  mov     [rbp+var_20], 0
0x180003546  mov     [rbp+var_18], 0
0x18000354e  mov     [rbp+var_10], 0
0x180003555  test    al, al
0x180003557  jnz     short loc_1800035B9
0x180003559  test    cs:dword_1800050D0, 1000h
0x180003563  lea     rax, [rbp+var_50]
0x180003567  mov     [rbp+Arguments], rax
0x18000356b  mov     dword ptr [rbp+flOldProtect], 0
0x180003572  jz      short loc_18000359E
0x180003574  mov     rcx, rbx; SRWLock
0x180003577  call    cs:__imp_AcquireSRWLockExclusive
0x18000357d  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180003584  jnz     short loc_180003595
0x180003586  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18000358c  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180003590  call    DloadProtectSection
0x180003595  mov     rcx, rbx; SRWLock
0x180003598  call    cs:__imp_ReleaseSRWLockExclusive
0x18000359e  lea     r9, [rbp+Arguments]; lpArguments
0x1800035a2  mov     r8d, edi; nNumberOfArguments
0x1800035a5  xor     edx, edx; dwExceptionFlags
0x1800035a7  mov     ecx, 0C06D0057h; dwExceptionCode
0x1800035ac  call    cs:__imp_RaiseException
0x1800035b2  xor     eax, eax
0x1800035b4  jmp     loc_18000393B
0x1800035b9  mov     eax, [rsi+0Ch]
0x1800035bc  mov     rcx, r13
0x1800035bf  mov     rbx, [r15]
0x1800035c2  sub     rcx, rax
0x1800035c5  sub     rcx, rdx
0x1800035c8  sar     rcx, 3
0x1800035cc  mov     eax, ecx
0x1800035ce  mov     ecx, [rsi+10h]
0x1800035d1  shl     rax, 3
0x1800035d5  add     rcx, rax
0x1800035d8  mov     [rbp+flOldProtect], rax
0x1800035dc  xor     eax, eax
0x1800035de  cmp     [rcx+rdx], rax
0x1800035e2  setnl   al
0x1800035e5  mov     [rbp+var_30], eax
0x1800035e8  test    eax, eax
0x1800035ea  jz      short loc_1800035FF
0x1800035ec  mov     eax, [rcx+rdx]
0x1800035ef  lea     rdx, word_180000002
0x1800035f6  add     rax, rdx
0x1800035f9  mov     [rbp+lpProcName], rax
0x1800035fd  jmp     short loc_180003606
0x1800035ff  movzx   eax, word ptr [rcx+rdx]
0x180003603  mov     dword ptr [rbp+lpProcName], eax
0x180003606  mov     rax, cs:__pfnDliNotifyHook2
0x18000360d  xor     edi, edi
0x18000360f  test    rax, rax
0x180003612  jz      short loc_180003632
0x180003614  lea     rdx, [rbp+var_50]
0x180003618  xor     ecx, ecx
0x18000361a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000361f  mov     rdi, rax
0x180003622  test    rax, rax
0x180003625  mov     rax, cs:__pfnDliNotifyHook2
0x18000362c  jnz     loc_1800038D1
0x180003632  test    rbx, rbx
0x180003635  jnz     loc_180003770
0x18000363b  test    rax, rax
0x18000363e  jz      short loc_180003658
0x180003640  lea     rdx, [rbp+var_50]
0x180003644  lea     ecx, [rbx+1]
0x180003647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000364c  mov     rbx, rax
0x18000364f  test    rax, rax
0x180003652  jnz     loc_180003707
0x180003658  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000365c  xor     r8d, r8d; dwFlags
0x18000365f  xor     edx, edx; hFile
0x180003661  call    cs:__imp_LoadLibraryExA
0x180003667  mov     rbx, rax
0x18000366a  test    rax, rax
0x18000366d  jnz     loc_180003707
0x180003673  call    cs:__imp_GetLastError
0x180003679  mov     [rbp+var_10], eax
0x18000367c  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180003683  test    rax, rax
0x180003686  jz      short loc_18000369C
0x180003688  lea     rdx, [rbp+var_50]
0x18000368c  lea     ecx, [rbx+3]
0x18000368f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003694  mov     rbx, rax
0x180003697  test    rax, rax
0x18000369a  jnz     short loc_180003707
0x18000369c  test    cs:dword_1800050D0, 1000h
0x1800036a6  lea     rax, [rbp+var_50]
0x1800036aa  mov     [rbp+Arguments], rax
0x1800036ae  mov     dword ptr [rbp+flOldProtect], 0
0x1800036b5  jz      short loc_1800036E9
0x1800036b7  lea     rcx, DloadSrwLock; SRWLock
0x1800036be  call    cs:__imp_AcquireSRWLockExclusive
0x1800036c4  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800036cb  jnz     short loc_1800036DC
0x1800036cd  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800036d3  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800036d7  call    DloadProtectSection
0x1800036dc  lea     rcx, DloadSrwLock; SRWLock
0x1800036e3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800036e9  xor     edx, edx; dwExceptionFlags
0x1800036eb  lea     r9, [rbp+Arguments]; lpArguments
0x1800036ef  mov     ecx, 0C06D007Eh; dwExceptionCode
0x1800036f4  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800036f8  call    cs:__imp_RaiseException
0x1800036fe  mov     rax, [rbp+var_18]
0x180003702  jmp     loc_18000393B
0x180003707  xor     eax, eax
0x180003709  lock cmpxchg [r15], rbx
0x18000370e  mov     r15, rax
0x180003711  jnz     short loc_180003753
0x180003713  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180003717  jz      short loc_180003769
0x180003719  cmp     dword ptr [rsi+18h], 0
0x18000371d  jz      short loc_180003769
0x18000371f  call    cs:__imp_GetProcessHeap
0x180003725  mov     edx, 8; dwFlags
0x18000372a  mov     rcx, rax; hHeap
0x18000372d  lea     r8d, [rdx+8]; dwBytes
0x180003731  call    cs:__imp_HeapAlloc
0x180003737  test    rax, rax
0x18000373a  jz      short loc_180003769
0x18000373c  mov     [rax+8], rsi
0x180003740  mov     rcx, cs:__puiHead
0x180003747  mov     [rax], rcx
0x18000374a  mov     cs:__puiHead, rax
0x180003751  jmp     short loc_180003769
0x180003753  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180003757  jz      short loc_180003762
0x180003759  mov     rcx, rbx; hLibModule
0x18000375c  call    cs:__imp_FreeLibrary
0x180003762  cmp     rbx, r15
0x180003765  cmovnz  rbx, r15
0x180003769  mov     rax, cs:__pfnDliNotifyHook2
0x180003770  mov     [rbp+var_20], rbx
0x180003774  test    rax, rax
0x180003777  jz      short loc_180003791
0x180003779  lea     rdx, [rbp+var_50]
0x18000377d  mov     ecx, 2
0x180003782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003787  mov     rdi, rax
0x18000378a  mov     rax, cs:__pfnDliNotifyHook2
0x180003791  test    rdi, rdi
0x180003794  jnz     loc_1800038CD
0x18000379a  cmp     [rsi+14h], edi
0x18000379d  jz      short loc_1800037D2
0x18000379f  cmp     [rsi+1Ch], edi
0x1800037a2  jz      short loc_1800037D2
0x1800037a4  movsxd  rcx, dword ptr [rbx+3Ch]
0x1800037a8  cmp     dword ptr [rcx+rbx], 4550h
0x1800037af  jnz     short loc_1800037D2
0x1800037b1  mov     edx, [rbp+arg_0]
0x1800037b4  cmp     [rcx+rbx+8], edx
0x1800037b8  jnz     short loc_1800037D2
0x1800037ba  cmp     rbx, [rcx+rbx+30h]
0x1800037bf  jnz     short loc_1800037D2
0x1800037c1  mov     rdi, [rbp+flOldProtect]
0x1800037c5  mov     rdi, [rdi+r12]
0x1800037c9  test    rdi, rdi
0x1800037cc  jnz     loc_1800038CD
0x1800037d2  mov     rdx, [rbp+lpProcName]; lpProcName
0x1800037d6  mov     rcx, rbx; hModule
0x1800037d9  call    cs:__imp_GetProcAddress
0x1800037df  mov     rdi, rax
0x1800037e2  test    rax, rax
0x1800037e5  jnz     loc_1800038C6
0x1800037eb  call    cs:__imp_GetLastError
0x1800037f1  mov     [rbp+var_10], eax
0x1800037f4  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800037fb  test    rax, rax
0x1800037fe  jz      short loc_180003818
0x180003800  lea     rdx, [rbp+var_50]
0x180003804  lea     ecx, [rdi+4]
0x180003807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000380c  mov     rdi, rax
0x18000380f  test    rax, rax
0x180003812  jnz     loc_1800038C6
0x180003818  test    cs:dword_1800050D0, 1000h
0x180003822  lea     rax, [rbp+var_50]
0x180003826  mov     [rbp+Arguments], rax
0x18000382a  mov     dword ptr [rbp+flOldProtect], 0
0x180003831  jz      short loc_180003865
0x180003833  lea     rcx, DloadSrwLock; SRWLock
0x18000383a  call    cs:__imp_AcquireSRWLockExclusive
0x180003840  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180003847  jnz     short loc_180003858
0x180003849  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18000384f  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180003853  call    DloadProtectSection
0x180003858  lea     rcx, DloadSrwLock; SRWLock
0x18000385f  call    cs:__imp_ReleaseSRWLockExclusive
0x180003865  xor     edx, edx; dwExceptionFlags
0x180003867  lea     r9, [rbp+Arguments]; lpArguments
0x18000386b  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180003870  lea     r8d, [rdx+1]; nNumberOfArguments
0x180003874  call    cs:__imp_RaiseException
0x18000387a  test    cs:dword_1800050D0, 1000h
0x180003884  jz      short loc_1800038C2
0x180003886  lea     rcx, DloadSrwLock; SRWLock
0x18000388d  call    cs:__imp_AcquireSRWLockExclusive
0x180003893  mov     eax, cs:DloadSectionLockCount
0x180003899  inc     eax
0x18000389b  mov     cs:DloadSectionLockCount, eax
0x1800038a1  cmp     eax, 1
0x1800038a4  jnz     short loc_1800038B5
0x1800038a6  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x1800038ad  lea     ecx, [rax+3]; flNewProtect
0x1800038b0  call    DloadProtectSection
0x1800038b5  lea     rcx, DloadSrwLock; SRWLock
0x1800038bc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800038c2  mov     rdi, [rbp+var_18]
0x1800038c6  mov     rax, cs:__pfnDliNotifyHook2
0x1800038cd  mov     [r13+0], rdi
0x1800038d1  test    rax, rax
0x1800038d4  jz      short loc_1800038F3
0x1800038d6  lea     rdx, [rbp+var_50]
0x1800038da  mov     [rbp+var_10], 0
0x1800038e1  mov     ecx, 5
0x1800038e6  mov     [rbp+var_20], rbx
0x1800038ea  mov     [rbp+var_18], rdi
0x1800038ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038f3  test    cs:dword_1800050D0, 1000h
0x1800038fd  mov     dword ptr [rbp+flOldProtect], 0
0x180003904  jz      short loc_180003938
0x180003906  lea     rcx, DloadSrwLock; SRWLock
0x18000390d  call    cs:__imp_AcquireSRWLockExclusive
0x180003913  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18000391a  jnz     short loc_18000392B
0x18000391c  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180003922  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180003926  call    DloadProtectSection
0x18000392b  lea     rcx, DloadSrwLock; SRWLock
0x180003932  call    cs:__imp_ReleaseSRWLockExclusive
0x180003938  mov     rax, rdi
0x18000393b  add     rsp, 70h
0x18000393f  pop     r15
0x180003941  pop     r13
0x180003943  pop     r12
0x180003945  pop     rdi
0x180003946  pop     rsi
0x180003947  pop     rbx
0x180003948  pop     rbp
0x180003949  retn
```
