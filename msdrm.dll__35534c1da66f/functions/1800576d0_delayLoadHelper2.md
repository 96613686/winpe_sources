# __delayLoadHelper2

- ea: `0x1800576d0`
- end: `0x180057b9a`
- name: `__delayLoadHelper2`
- size: `1226`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800037ff`
- `0x1800038d2`
- `0x1800039ff`
- `0x180003b3e`
- `0x180003ca1`
- `0x180003d3e`
- `0x180003ddb`
- `0x180004070`

## callees

- `0x1800575e8`
- `0x1800576d0`
- `0x18005bd72`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057717`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800577c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005790e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057a8a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057add`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057b5d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057717`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800577c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005790e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057a8a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057add`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057b5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057741`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800577e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057933`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057aaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057b0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057b82`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057741`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800577e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057933`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057aaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057b0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057b82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800578c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800578c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800577fc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180057948`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180057ac4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800577fc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180057948`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180057ac4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180057a29`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180057a29`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1800578b1`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1800578b1`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800579ac`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800579ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057981`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057981`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005796f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005796f`

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
0x1800576d0  push    rbp
0x1800576d2  push    rbx
0x1800576d3  push    rsi
0x1800576d4  push    rdi
0x1800576d5  push    r12
0x1800576d7  push    r13
0x1800576d9  push    r15
0x1800576db  mov     rbp, rsp
0x1800576de  sub     rsp, 70h
0x1800576e2  xor     eax, eax
0x1800576e4  mov     r13, rdx
0x1800576e7  mov     rsi, rcx
0x1800576ea  mov     [rbp+var_4C], eax
0x1800576ed  xor     edx, edx; Val
0x1800576ef  lea     rcx, [rbp+var_50]; void *
0x1800576f3  lea     r8d, [rax+44h]; Size
0x1800576f7  call    memset_0
0x1800576fc  test    cs:dword_180060160, 1000h
0x180057706  lea     rbx, DloadSrwLock
0x18005770d  mov     edi, 1
0x180057712  jz      short loc_180057747
0x180057714  mov     rcx, rbx; SRWLock
0x180057717  call    cs:__imp_AcquireSRWLockExclusive
0x18005771d  mov     eax, cs:DloadSectionLockCount
0x180057723  add     eax, edi
0x180057725  mov     cs:DloadSectionLockCount, eax
0x18005772b  cmp     eax, edi
0x18005772d  jnz     short loc_18005773E
0x18005772f  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x180057736  lea     ecx, [rdi+3]; flNewProtect
0x180057739  call    DloadProtectSection
0x18005773e  mov     rcx, rbx; SRWLock
0x180057741  call    cs:__imp_ReleaseSRWLockExclusive
0x180057747  mov     eax, [rsi+4]
0x18005774a  lea     rdx, __ImageBase
0x180057751  mov     r15d, [rsi+8]
0x180057755  add     rax, rdx
0x180057758  mov     r12d, [rsi+14h]
0x18005775c  add     r15, rdx
0x18005775f  mov     ecx, [rsi+1Ch]
0x180057762  add     r12, rdx
0x180057765  mov     [rbp+lpLibFileName], rax
0x180057769  mov     eax, [rsi]
0x18005776b  and     eax, edi
0x18005776d  mov     [rbp+arg_0], ecx
0x180057770  mov     [rbp+var_50], 48h ; 'H'
0x180057777  mov     [rbp+var_48], rsi
0x18005777b  mov     [rbp+var_40], r13
0x18005777f  mov     [rbp+var_30], 0
0x180057786  mov     [rbp+lpProcName], 0
0x18005778e  mov     [rbp+var_20], 0
0x180057796  mov     [rbp+var_18], 0
0x18005779e  mov     [rbp+var_10], 0
0x1800577a5  test    al, al
0x1800577a7  jnz     short loc_180057809
0x1800577a9  test    cs:dword_180060160, 1000h
0x1800577b3  lea     rax, [rbp+var_50]
0x1800577b7  mov     [rbp+Arguments], rax
0x1800577bb  mov     dword ptr [rbp+flOldProtect], 0
0x1800577c2  jz      short loc_1800577EE
0x1800577c4  mov     rcx, rbx; SRWLock
0x1800577c7  call    cs:__imp_AcquireSRWLockExclusive
0x1800577cd  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800577d4  jnz     short loc_1800577E5
0x1800577d6  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800577dc  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800577e0  call    DloadProtectSection
0x1800577e5  mov     rcx, rbx; SRWLock
0x1800577e8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800577ee  lea     r9, [rbp+Arguments]; lpArguments
0x1800577f2  mov     r8d, edi; nNumberOfArguments
0x1800577f5  xor     edx, edx; dwExceptionFlags
0x1800577f7  mov     ecx, 0C06D0057h; dwExceptionCode
0x1800577fc  call    cs:__imp_RaiseException
0x180057802  xor     eax, eax
0x180057804  jmp     loc_180057B8B
0x180057809  mov     eax, [rsi+0Ch]
0x18005780c  mov     rcx, r13
0x18005780f  mov     rbx, [r15]
0x180057812  sub     rcx, rax
0x180057815  sub     rcx, rdx
0x180057818  sar     rcx, 3
0x18005781c  mov     eax, ecx
0x18005781e  mov     ecx, [rsi+10h]
0x180057821  shl     rax, 3
0x180057825  add     rcx, rax
0x180057828  mov     [rbp+flOldProtect], rax
0x18005782c  xor     eax, eax
0x18005782e  cmp     [rcx+rdx], rax
0x180057832  setnl   al
0x180057835  mov     [rbp+var_30], eax
0x180057838  test    eax, eax
0x18005783a  jz      short loc_18005784F
0x18005783c  mov     eax, [rcx+rdx]
0x18005783f  lea     rdx, word_180000002
0x180057846  add     rax, rdx
0x180057849  mov     [rbp+lpProcName], rax
0x18005784d  jmp     short loc_180057856
0x18005784f  movzx   eax, word ptr [rcx+rdx]
0x180057853  mov     dword ptr [rbp+lpProcName], eax
0x180057856  mov     rax, cs:__pfnDliNotifyHook2
0x18005785d  xor     edi, edi
0x18005785f  test    rax, rax
0x180057862  jz      short loc_180057882
0x180057864  lea     rdx, [rbp+var_50]
0x180057868  xor     ecx, ecx
0x18005786a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005786f  mov     rdi, rax
0x180057872  test    rax, rax
0x180057875  mov     rax, cs:__pfnDliNotifyHook2
0x18005787c  jnz     loc_180057B21
0x180057882  test    rbx, rbx
0x180057885  jnz     loc_1800579C0
0x18005788b  test    rax, rax
0x18005788e  jz      short loc_1800578A8
0x180057890  lea     rdx, [rbp+var_50]
0x180057894  lea     ecx, [rbx+1]
0x180057897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005789c  mov     rbx, rax
0x18005789f  test    rax, rax
0x1800578a2  jnz     loc_180057957
0x1800578a8  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800578ac  xor     r8d, r8d; dwFlags
0x1800578af  xor     edx, edx; hFile
0x1800578b1  call    cs:__imp_LoadLibraryExA
0x1800578b7  mov     rbx, rax
0x1800578ba  test    rax, rax
0x1800578bd  jnz     loc_180057957
0x1800578c3  call    cs:__imp_GetLastError
0x1800578c9  mov     [rbp+var_10], eax
0x1800578cc  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800578d3  test    rax, rax
0x1800578d6  jz      short loc_1800578EC
0x1800578d8  lea     rdx, [rbp+var_50]
0x1800578dc  lea     ecx, [rbx+3]
0x1800578df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800578e4  mov     rbx, rax
0x1800578e7  test    rax, rax
0x1800578ea  jnz     short loc_180057957
0x1800578ec  test    cs:dword_180060160, 1000h
0x1800578f6  lea     rax, [rbp+var_50]
0x1800578fa  mov     [rbp+Arguments], rax
0x1800578fe  mov     dword ptr [rbp+flOldProtect], 0
0x180057905  jz      short loc_180057939
0x180057907  lea     rcx, DloadSrwLock; SRWLock
0x18005790e  call    cs:__imp_AcquireSRWLockExclusive
0x180057914  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18005791b  jnz     short loc_18005792C
0x18005791d  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180057923  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180057927  call    DloadProtectSection
0x18005792c  lea     rcx, DloadSrwLock; SRWLock
0x180057933  call    cs:__imp_ReleaseSRWLockExclusive
0x180057939  xor     edx, edx; dwExceptionFlags
0x18005793b  lea     r9, [rbp+Arguments]; lpArguments
0x18005793f  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180057944  lea     r8d, [rdx+1]; nNumberOfArguments
0x180057948  call    cs:__imp_RaiseException
0x18005794e  mov     rax, [rbp+var_18]
0x180057952  jmp     loc_180057B8B
0x180057957  xor     eax, eax
0x180057959  lock cmpxchg [r15], rbx
0x18005795e  mov     r15, rax
0x180057961  jnz     short loc_1800579A3
0x180057963  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180057967  jz      short loc_1800579B9
0x180057969  cmp     dword ptr [rsi+18h], 0
0x18005796d  jz      short loc_1800579B9
0x18005796f  call    cs:__imp_GetProcessHeap
0x180057975  mov     edx, 8; dwFlags
0x18005797a  mov     rcx, rax; hHeap
0x18005797d  lea     r8d, [rdx+8]; dwBytes
0x180057981  call    cs:__imp_HeapAlloc
0x180057987  test    rax, rax
0x18005798a  jz      short loc_1800579B9
0x18005798c  mov     [rax+8], rsi
0x180057990  mov     rcx, cs:__puiHead
0x180057997  mov     [rax], rcx
0x18005799a  mov     cs:__puiHead, rax
0x1800579a1  jmp     short loc_1800579B9
0x1800579a3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800579a7  jz      short loc_1800579B2
0x1800579a9  mov     rcx, rbx; hLibModule
0x1800579ac  call    cs:__imp_FreeLibrary
0x1800579b2  cmp     rbx, r15
0x1800579b5  cmovnz  rbx, r15
0x1800579b9  mov     rax, cs:__pfnDliNotifyHook2
0x1800579c0  mov     [rbp+var_20], rbx
0x1800579c4  test    rax, rax
0x1800579c7  jz      short loc_1800579E1
0x1800579c9  lea     rdx, [rbp+var_50]
0x1800579cd  mov     ecx, 2
0x1800579d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800579d7  mov     rdi, rax
0x1800579da  mov     rax, cs:__pfnDliNotifyHook2
0x1800579e1  test    rdi, rdi
0x1800579e4  jnz     loc_180057B1D
0x1800579ea  cmp     [rsi+14h], edi
0x1800579ed  jz      short loc_180057A22
0x1800579ef  cmp     [rsi+1Ch], edi
0x1800579f2  jz      short loc_180057A22
0x1800579f4  movsxd  rcx, dword ptr [rbx+3Ch]
0x1800579f8  cmp     dword ptr [rcx+rbx], 4550h
0x1800579ff  jnz     short loc_180057A22
0x180057a01  mov     edx, [rbp+arg_0]
0x180057a04  cmp     [rcx+rbx+8], edx
0x180057a08  jnz     short loc_180057A22
0x180057a0a  cmp     rbx, [rcx+rbx+30h]
0x180057a0f  jnz     short loc_180057A22
0x180057a11  mov     rdi, [rbp+flOldProtect]
0x180057a15  mov     rdi, [rdi+r12]
0x180057a19  test    rdi, rdi
0x180057a1c  jnz     loc_180057B1D
0x180057a22  mov     rdx, [rbp+lpProcName]; lpProcName
0x180057a26  mov     rcx, rbx; hModule
0x180057a29  call    cs:__imp_GetProcAddress
0x180057a2f  mov     rdi, rax
0x180057a32  test    rax, rax
0x180057a35  jnz     loc_180057B16
0x180057a3b  call    cs:__imp_GetLastError
0x180057a41  mov     [rbp+var_10], eax
0x180057a44  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180057a4b  test    rax, rax
0x180057a4e  jz      short loc_180057A68
0x180057a50  lea     rdx, [rbp+var_50]
0x180057a54  lea     ecx, [rdi+4]
0x180057a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a5c  mov     rdi, rax
0x180057a5f  test    rax, rax
0x180057a62  jnz     loc_180057B16
0x180057a68  test    cs:dword_180060160, 1000h
0x180057a72  lea     rax, [rbp+var_50]
0x180057a76  mov     [rbp+Arguments], rax
0x180057a7a  mov     dword ptr [rbp+flOldProtect], 0
0x180057a81  jz      short loc_180057AB5
0x180057a83  lea     rcx, DloadSrwLock; SRWLock
0x180057a8a  call    cs:__imp_AcquireSRWLockExclusive
0x180057a90  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180057a97  jnz     short loc_180057AA8
0x180057a99  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180057a9f  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180057aa3  call    DloadProtectSection
0x180057aa8  lea     rcx, DloadSrwLock; SRWLock
0x180057aaf  call    cs:__imp_ReleaseSRWLockExclusive
0x180057ab5  xor     edx, edx; dwExceptionFlags
0x180057ab7  lea     r9, [rbp+Arguments]; lpArguments
0x180057abb  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180057ac0  lea     r8d, [rdx+1]; nNumberOfArguments
0x180057ac4  call    cs:__imp_RaiseException
0x180057aca  test    cs:dword_180060160, 1000h
0x180057ad4  jz      short loc_180057B12
0x180057ad6  lea     rcx, DloadSrwLock; SRWLock
0x180057add  call    cs:__imp_AcquireSRWLockExclusive
0x180057ae3  mov     eax, cs:DloadSectionLockCount
0x180057ae9  inc     eax
0x180057aeb  mov     cs:DloadSectionLockCount, eax
0x180057af1  cmp     eax, 1
0x180057af4  jnz     short loc_180057B05
0x180057af6  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x180057afd  lea     ecx, [rax+3]; flNewProtect
0x180057b00  call    DloadProtectSection
0x180057b05  lea     rcx, DloadSrwLock; SRWLock
0x180057b0c  call    cs:__imp_ReleaseSRWLockExclusive
0x180057b12  mov     rdi, [rbp+var_18]
0x180057b16  mov     rax, cs:__pfnDliNotifyHook2
0x180057b1d  mov     [r13+0], rdi
0x180057b21  test    rax, rax
0x180057b24  jz      short loc_180057B43
0x180057b26  lea     rdx, [rbp+var_50]
0x180057b2a  mov     [rbp+var_10], 0
0x180057b31  mov     ecx, 5
0x180057b36  mov     [rbp+var_20], rbx
0x180057b3a  mov     [rbp+var_18], rdi
0x180057b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057b43  test    cs:dword_180060160, 1000h
0x180057b4d  mov     dword ptr [rbp+flOldProtect], 0
0x180057b54  jz      short loc_180057B88
0x180057b56  lea     rcx, DloadSrwLock; SRWLock
0x180057b5d  call    cs:__imp_AcquireSRWLockExclusive
0x180057b63  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180057b6a  jnz     short loc_180057B7B
0x180057b6c  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180057b72  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180057b76  call    DloadProtectSection
0x180057b7b  lea     rcx, DloadSrwLock; SRWLock
0x180057b82  call    cs:__imp_ReleaseSRWLockExclusive
0x180057b88  mov     rax, rdi
0x180057b8b  add     rsp, 70h
0x180057b8f  pop     r15
0x180057b91  pop     r13
0x180057b93  pop     r12
0x180057b95  pop     rdi
0x180057b96  pop     rsi
0x180057b97  pop     rbx
0x180057b98  pop     rbp
0x180057b99  retn
```
