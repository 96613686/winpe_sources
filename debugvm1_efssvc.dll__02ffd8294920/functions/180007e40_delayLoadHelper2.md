# __delayLoadHelper2

- ea: `0x180007e40`
- end: `0x18000830a`
- name: `__delayLoadHelper2`
- size: `1226`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002260`
- `0x18000236e`
- `0x18000281f`
- `0x1800028aa`

## callees

- `0x180007d50`
- `0x180007e40`
- `0x18000c392`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008199`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008199`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000811c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000811c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180008021`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180008021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007f6c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800080b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008234`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007f6c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800080b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008234`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007e87`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007f37`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000807e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800081fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000824d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800082cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007e87`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007f37`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000807e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800081fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000824d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800082cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007eb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007f58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800080a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000821f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000827c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800082f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007eb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007f58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800080a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000821f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000827c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800082f2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800080f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800080f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800080df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800080df`

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
0x180007e40  push    rbp
0x180007e42  push    rbx
0x180007e43  push    rsi
0x180007e44  push    rdi
0x180007e45  push    r12
0x180007e47  push    r13
0x180007e49  push    r15
0x180007e4b  mov     rbp, rsp
0x180007e4e  sub     rsp, 70h
0x180007e52  xor     eax, eax
0x180007e54  mov     r13, rdx
0x180007e57  mov     rsi, rcx
0x180007e5a  mov     [rbp+var_4C], eax
0x180007e5d  xor     edx, edx; Val
0x180007e5f  lea     rcx, [rbp+var_50]; void *
0x180007e63  lea     r8d, [rax+44h]; Size
0x180007e67  call    memset_0
0x180007e6c  test    cs:dword_18000E0A0, 1000h
0x180007e76  lea     rbx, DloadSrwLock
0x180007e7d  mov     edi, 1
0x180007e82  jz      short loc_180007EB7
0x180007e84  mov     rcx, rbx; SRWLock
0x180007e87  call    cs:__imp_AcquireSRWLockExclusive
0x180007e8d  mov     eax, cs:DloadSectionLockCount
0x180007e93  add     eax, edi
0x180007e95  mov     cs:DloadSectionLockCount, eax
0x180007e9b  cmp     eax, edi
0x180007e9d  jnz     short loc_180007EAE
0x180007e9f  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x180007ea6  lea     ecx, [rdi+3]; flNewProtect
0x180007ea9  call    DloadProtectSection
0x180007eae  mov     rcx, rbx; SRWLock
0x180007eb1  call    cs:__imp_ReleaseSRWLockExclusive
0x180007eb7  mov     eax, [rsi+4]
0x180007eba  lea     rdx, __ImageBase
0x180007ec1  mov     r15d, [rsi+8]
0x180007ec5  add     rax, rdx
0x180007ec8  mov     r12d, [rsi+14h]
0x180007ecc  add     r15, rdx
0x180007ecf  mov     ecx, [rsi+1Ch]
0x180007ed2  add     r12, rdx
0x180007ed5  mov     [rbp+lpLibFileName], rax
0x180007ed9  mov     eax, [rsi]
0x180007edb  and     eax, edi
0x180007edd  mov     [rbp+arg_0], ecx
0x180007ee0  mov     [rbp+var_50], 48h ; 'H'
0x180007ee7  mov     [rbp+var_48], rsi
0x180007eeb  mov     [rbp+var_40], r13
0x180007eef  mov     [rbp+var_30], 0
0x180007ef6  mov     [rbp+lpProcName], 0
0x180007efe  mov     [rbp+var_20], 0
0x180007f06  mov     [rbp+var_18], 0
0x180007f0e  mov     [rbp+var_10], 0
0x180007f15  test    al, al
0x180007f17  jnz     short loc_180007F79
0x180007f19  test    cs:dword_18000E0A0, 1000h
0x180007f23  lea     rax, [rbp+var_50]
0x180007f27  mov     [rbp+Arguments], rax
0x180007f2b  mov     dword ptr [rbp+flOldProtect], 0
0x180007f32  jz      short loc_180007F5E
0x180007f34  mov     rcx, rbx; SRWLock
0x180007f37  call    cs:__imp_AcquireSRWLockExclusive
0x180007f3d  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180007f44  jnz     short loc_180007F55
0x180007f46  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180007f4c  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180007f50  call    DloadProtectSection
0x180007f55  mov     rcx, rbx; SRWLock
0x180007f58  call    cs:__imp_ReleaseSRWLockExclusive
0x180007f5e  lea     r9, [rbp+Arguments]; lpArguments
0x180007f62  mov     r8d, edi; nNumberOfArguments
0x180007f65  xor     edx, edx; dwExceptionFlags
0x180007f67  mov     ecx, 0C06D0057h; dwExceptionCode
0x180007f6c  call    cs:__imp_RaiseException
0x180007f72  xor     eax, eax
0x180007f74  jmp     loc_1800082FB
0x180007f79  mov     eax, [rsi+0Ch]
0x180007f7c  mov     rcx, r13
0x180007f7f  mov     rbx, [r15]
0x180007f82  sub     rcx, rax
0x180007f85  sub     rcx, rdx
0x180007f88  sar     rcx, 3
0x180007f8c  mov     eax, ecx
0x180007f8e  mov     ecx, [rsi+10h]
0x180007f91  shl     rax, 3
0x180007f95  add     rcx, rax
0x180007f98  mov     [rbp+flOldProtect], rax
0x180007f9c  xor     eax, eax
0x180007f9e  cmp     [rcx+rdx], rax
0x180007fa2  setnl   al
0x180007fa5  mov     [rbp+var_30], eax
0x180007fa8  test    eax, eax
0x180007faa  jz      short loc_180007FBF
0x180007fac  mov     eax, [rcx+rdx]
0x180007faf  lea     rdx, word_180000002
0x180007fb6  add     rax, rdx
0x180007fb9  mov     [rbp+lpProcName], rax
0x180007fbd  jmp     short loc_180007FC6
0x180007fbf  movzx   eax, word ptr [rcx+rdx]
0x180007fc3  mov     dword ptr [rbp+lpProcName], eax
0x180007fc6  mov     rax, cs:__pfnDliNotifyHook2
0x180007fcd  xor     edi, edi
0x180007fcf  test    rax, rax
0x180007fd2  jz      short loc_180007FF2
0x180007fd4  lea     rdx, [rbp+var_50]
0x180007fd8  xor     ecx, ecx
0x180007fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fdf  mov     rdi, rax
0x180007fe2  test    rax, rax
0x180007fe5  mov     rax, cs:__pfnDliNotifyHook2
0x180007fec  jnz     loc_180008291
0x180007ff2  test    rbx, rbx
0x180007ff5  jnz     loc_180008130
0x180007ffb  test    rax, rax
0x180007ffe  jz      short loc_180008018
0x180008000  lea     rdx, [rbp+var_50]
0x180008004  lea     ecx, [rbx+1]
0x180008007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000800c  mov     rbx, rax
0x18000800f  test    rax, rax
0x180008012  jnz     loc_1800080C7
0x180008018  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000801c  xor     r8d, r8d; dwFlags
0x18000801f  xor     edx, edx; hFile
0x180008021  call    cs:__imp_LoadLibraryExA
0x180008027  mov     rbx, rax
0x18000802a  test    rax, rax
0x18000802d  jnz     loc_1800080C7
0x180008033  call    cs:__imp_GetLastError
0x180008039  mov     [rbp+var_10], eax
0x18000803c  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180008043  test    rax, rax
0x180008046  jz      short loc_18000805C
0x180008048  lea     rdx, [rbp+var_50]
0x18000804c  lea     ecx, [rbx+3]
0x18000804f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008054  mov     rbx, rax
0x180008057  test    rax, rax
0x18000805a  jnz     short loc_1800080C7
0x18000805c  test    cs:dword_18000E0A0, 1000h
0x180008066  lea     rax, [rbp+var_50]
0x18000806a  mov     [rbp+Arguments], rax
0x18000806e  mov     dword ptr [rbp+flOldProtect], 0
0x180008075  jz      short loc_1800080A9
0x180008077  lea     rcx, DloadSrwLock; SRWLock
0x18000807e  call    cs:__imp_AcquireSRWLockExclusive
0x180008084  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18000808b  jnz     short loc_18000809C
0x18000808d  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180008093  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180008097  call    DloadProtectSection
0x18000809c  lea     rcx, DloadSrwLock; SRWLock
0x1800080a3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800080a9  xor     edx, edx; dwExceptionFlags
0x1800080ab  lea     r9, [rbp+Arguments]; lpArguments
0x1800080af  mov     ecx, 0C06D007Eh; dwExceptionCode
0x1800080b4  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800080b8  call    cs:__imp_RaiseException
0x1800080be  mov     rax, [rbp+var_18]
0x1800080c2  jmp     loc_1800082FB
0x1800080c7  xor     eax, eax
0x1800080c9  lock cmpxchg [r15], rbx
0x1800080ce  mov     r15, rax
0x1800080d1  jnz     short loc_180008113
0x1800080d3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800080d7  jz      short loc_180008129
0x1800080d9  cmp     dword ptr [rsi+18h], 0
0x1800080dd  jz      short loc_180008129
0x1800080df  call    cs:__imp_GetProcessHeap
0x1800080e5  mov     edx, 8; dwFlags
0x1800080ea  mov     rcx, rax; hHeap
0x1800080ed  lea     r8d, [rdx+8]; dwBytes
0x1800080f1  call    cs:__imp_HeapAlloc
0x1800080f7  test    rax, rax
0x1800080fa  jz      short loc_180008129
0x1800080fc  mov     [rax+8], rsi
0x180008100  mov     rcx, cs:__puiHead
0x180008107  mov     [rax], rcx
0x18000810a  mov     cs:__puiHead, rax
0x180008111  jmp     short loc_180008129
0x180008113  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180008117  jz      short loc_180008122
0x180008119  mov     rcx, rbx; hLibModule
0x18000811c  call    cs:__imp_FreeLibrary
0x180008122  cmp     rbx, r15
0x180008125  cmovnz  rbx, r15
0x180008129  mov     rax, cs:__pfnDliNotifyHook2
0x180008130  mov     [rbp+var_20], rbx
0x180008134  test    rax, rax
0x180008137  jz      short loc_180008151
0x180008139  lea     rdx, [rbp+var_50]
0x18000813d  mov     ecx, 2
0x180008142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008147  mov     rdi, rax
0x18000814a  mov     rax, cs:__pfnDliNotifyHook2
0x180008151  test    rdi, rdi
0x180008154  jnz     loc_18000828D
0x18000815a  cmp     [rsi+14h], edi
0x18000815d  jz      short loc_180008192
0x18000815f  cmp     [rsi+1Ch], edi
0x180008162  jz      short loc_180008192
0x180008164  movsxd  rcx, dword ptr [rbx+3Ch]
0x180008168  cmp     dword ptr [rcx+rbx], 4550h
0x18000816f  jnz     short loc_180008192
0x180008171  mov     edx, [rbp+arg_0]
0x180008174  cmp     [rcx+rbx+8], edx
0x180008178  jnz     short loc_180008192
0x18000817a  cmp     rbx, [rcx+rbx+30h]
0x18000817f  jnz     short loc_180008192
0x180008181  mov     rdi, [rbp+flOldProtect]
0x180008185  mov     rdi, [rdi+r12]
0x180008189  test    rdi, rdi
0x18000818c  jnz     loc_18000828D
0x180008192  mov     rdx, [rbp+lpProcName]; lpProcName
0x180008196  mov     rcx, rbx; hModule
0x180008199  call    cs:__imp_GetProcAddress
0x18000819f  mov     rdi, rax
0x1800081a2  test    rax, rax
0x1800081a5  jnz     loc_180008286
0x1800081ab  call    cs:__imp_GetLastError
0x1800081b1  mov     [rbp+var_10], eax
0x1800081b4  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800081bb  test    rax, rax
0x1800081be  jz      short loc_1800081D8
0x1800081c0  lea     rdx, [rbp+var_50]
0x1800081c4  lea     ecx, [rdi+4]
0x1800081c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081cc  mov     rdi, rax
0x1800081cf  test    rax, rax
0x1800081d2  jnz     loc_180008286
0x1800081d8  test    cs:dword_18000E0A0, 1000h
0x1800081e2  lea     rax, [rbp+var_50]
0x1800081e6  mov     [rbp+Arguments], rax
0x1800081ea  mov     dword ptr [rbp+flOldProtect], 0
0x1800081f1  jz      short loc_180008225
0x1800081f3  lea     rcx, DloadSrwLock; SRWLock
0x1800081fa  call    cs:__imp_AcquireSRWLockExclusive
0x180008200  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180008207  jnz     short loc_180008218
0x180008209  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18000820f  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180008213  call    DloadProtectSection
0x180008218  lea     rcx, DloadSrwLock; SRWLock
0x18000821f  call    cs:__imp_ReleaseSRWLockExclusive
0x180008225  xor     edx, edx; dwExceptionFlags
0x180008227  lea     r9, [rbp+Arguments]; lpArguments
0x18000822b  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180008230  lea     r8d, [rdx+1]; nNumberOfArguments
0x180008234  call    cs:__imp_RaiseException
0x18000823a  test    cs:dword_18000E0A0, 1000h
0x180008244  jz      short loc_180008282
0x180008246  lea     rcx, DloadSrwLock; SRWLock
0x18000824d  call    cs:__imp_AcquireSRWLockExclusive
0x180008253  mov     eax, cs:DloadSectionLockCount
0x180008259  inc     eax
0x18000825b  mov     cs:DloadSectionLockCount, eax
0x180008261  cmp     eax, 1
0x180008264  jnz     short loc_180008275
0x180008266  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18000826d  lea     ecx, [rax+3]; flNewProtect
0x180008270  call    DloadProtectSection
0x180008275  lea     rcx, DloadSrwLock; SRWLock
0x18000827c  call    cs:__imp_ReleaseSRWLockExclusive
0x180008282  mov     rdi, [rbp+var_18]
0x180008286  mov     rax, cs:__pfnDliNotifyHook2
0x18000828d  mov     [r13+0], rdi
0x180008291  test    rax, rax
0x180008294  jz      short loc_1800082B3
0x180008296  lea     rdx, [rbp+var_50]
0x18000829a  mov     [rbp+var_10], 0
0x1800082a1  mov     ecx, 5
0x1800082a6  mov     [rbp+var_20], rbx
0x1800082aa  mov     [rbp+var_18], rdi
0x1800082ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082b3  test    cs:dword_18000E0A0, 1000h
0x1800082bd  mov     dword ptr [rbp+flOldProtect], 0
0x1800082c4  jz      short loc_1800082F8
0x1800082c6  lea     rcx, DloadSrwLock; SRWLock
0x1800082cd  call    cs:__imp_AcquireSRWLockExclusive
0x1800082d3  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800082da  jnz     short loc_1800082EB
0x1800082dc  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800082e2  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800082e6  call    DloadProtectSection
0x1800082eb  lea     rcx, DloadSrwLock; SRWLock
0x1800082f2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800082f8  mov     rax, rdi
0x1800082fb  add     rsp, 70h
0x1800082ff  pop     r15
0x180008301  pop     r13
0x180008303  pop     r12
0x180008305  pop     rdi
0x180008306  pop     rsi
0x180008307  pop     rbx
0x180008308  pop     rbp
0x180008309  retn
```
