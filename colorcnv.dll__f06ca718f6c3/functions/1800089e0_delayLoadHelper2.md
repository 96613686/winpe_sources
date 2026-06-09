# __delayLoadHelper2

- ea: `0x1800089e0`
- end: `0x180008cea`
- name: `__delayLoadHelper2`
- size: `778`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b4c2`
- `0x18000ba7c`
- `0x18000bb07`
- `0x18000bba4`
- `0x18000bc53`

## callees

- `0x1800089e0`
- `0x18000a25c`
- `0x18000a308`
- `0x18000b468`
- `0x180029c9c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008bcd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008bcd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008c42`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008c42`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180008b40`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180008b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c50`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008a8f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008b93`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008c95`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008a8f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008b93`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008c95`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  __int64 v4; // r8
  __int16 *v5; // rdx
  volatile signed __int64 *v6; // r14
  __int64 dwTimeStamp; // rcx
  char *v8; // r15
  DWORD grAttrs; // eax
  HMODULE Library; // rbx
  __int64 v12; // r13
  __int64 v13; // rcx
  PfnDliHook v14; // rax
  INT_PTR (__stdcall *ProcAddress)(); // rdi
  signed __int64 v16; // r14
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  struct DelayLoadInfo v20; // [rsp+20h] [rbp-58h] BYREF
  ULONG_PTR Arguments; // [rsp+C0h] [rbp+48h] BYREF

  *(&v20.cb + 1) = 0;
  memset_0(&v20, 0, 0x44u);
  ((void (*)(void))DloadAcquireSectionWriteAccess)();
  v5 = &_ImageBase;
  v6 = (volatile signed __int64 *)((char *)&_ImageBase + a1->rvaHmod);
  dwTimeStamp = a1->dwTimeStamp;
  v8 = (char *)&_ImageBase + a1->rvaBoundIAT;
  v20.szDll = (char *)&_ImageBase + a1->rvaDLLName;
  grAttrs = a1->grAttrs;
  LODWORD(Arguments) = dwTimeStamp;
  v20.cb = 72;
  v20.pidd = a1;
  v20.ppfn = a2;
  v20.dlp.fImportByName = 0;
  memset(&v20.dlp.szProcName, 0, 28);
  if ( (grAttrs & 1) == 0 )
  {
    Arguments = (ULONG_PTR)&v20;
    DloadReleaseSectionWriteAccess(dwTimeStamp, &_ImageBase, v4);
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v6;
  v12 = 8LL * (unsigned int)(((char *)a2 - a1->rvaIAT - (char *)&_ImageBase) >> 3);
  v13 = v12 + a1->rvaINT;
  v20.dlp.fImportByName = *(_QWORD *)((char *)&_ImageBase + v13) >= 0LL;
  if ( v20.dlp.fImportByName )
  {
    v5 = &word_180000002;
    v20.dlp.szProcName = (char *)&word_180000002 + *(unsigned int *)((char *)&_ImageBase + v13);
  }
  else
  {
    v20.dlp.dwOrdinal = *(unsigned __int16 *)((char *)&_ImageBase + v13);
  }
  v14 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( !_pfnDliNotifyHook2 || (ProcAddress = _pfnDliNotifyHook2(0, &v20), v14 = _pfnDliNotifyHook2, !ProcAddress) )
  {
    if ( !Library )
    {
      if ( !v14 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(1, &v20)) == 0 )
      {
        Library = LoadLibraryExA(v20.szDll, 0, 0);
        if ( !Library )
        {
          v20.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, &v20)) == 0 )
          {
            Arguments = (ULONG_PTR)&v20;
            DloadReleaseSectionWriteAccess(v13, v5, v4);
            RaiseException(0xC06D007E, 0, 1u, &Arguments);
            return v20.pfnCur;
          }
        }
      }
      v16 = _InterlockedCompareExchange64(v6, (signed __int64)Library, 0);
      if ( v16 )
      {
        if ( Library != (HMODULE)-1LL )
          FreeLibrary(Library);
        if ( Library != (HMODULE)v16 )
          Library = (HMODULE)v16;
      }
      else if ( Library != (HMODULE)-1LL && a1->rvaUnloadIAT )
      {
        NewUnloadInfo(a1);
      }
      v14 = _pfnDliNotifyHook2;
    }
    v20.hmodCur = Library;
    if ( v14 )
    {
      ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(2, &v20);
      v14 = _pfnDliNotifyHook2;
    }
    if ( !ProcAddress )
    {
      if ( !a1->rvaBoundIAT
        || !a1->dwTimeStamp
        || (v13 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v13) != 17744)
        || (v5 = (__int16 *)(unsigned int)Arguments, *(_DWORD *)((char *)Library + v13 + 8) != (_DWORD)Arguments)
        || Library != *(HMODULE *)((char *)Library + v13 + 48)
        || (ProcAddress = *(INT_PTR (__stdcall **)())&v8[v12]) == 0 )
      {
        ProcAddress = GetProcAddress(Library, v20.dlp.szProcName);
        if ( !ProcAddress )
        {
          v20.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2
            || (ProcAddress = (INT_PTR (__stdcall *)())_pfnDefaultDliFailureHook2(4, &v20)) == 0 )
          {
            Arguments = (ULONG_PTR)&v20;
            DloadReleaseSectionWriteAccess(v13, v5, v4);
            RaiseException(0xC06D007F, 0, 1u, &Arguments);
            DloadAcquireSectionWriteAccess(v18, v17, v19);
            ProcAddress = v20.pfnCur;
          }
        }
        v14 = _pfnDliNotifyHook2;
      }
    }
    *a2 = ProcAddress;
  }
  if ( v14 )
  {
    v20.dwLastError = 0;
    v20.hmodCur = Library;
    v20.pfnCur = ProcAddress;
    ((void (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(5, &v20);
  }
  DloadReleaseSectionWriteAccess(v13, v5, v4);
  return ProcAddress;
}

```

## disassembly

```asm
0x1800089e0  push    rbp
0x1800089e2  push    rbx
0x1800089e3  push    rsi
0x1800089e4  push    rdi
0x1800089e5  push    r12
0x1800089e7  push    r13
0x1800089e9  push    r14
0x1800089eb  push    r15
0x1800089ed  mov     rbp, rsp
0x1800089f0  sub     rsp, 78h
0x1800089f4  xor     eax, eax
0x1800089f6  mov     r12, rdx
0x1800089f9  mov     rsi, rcx
0x1800089fc  mov     [rbp+var_54], eax
0x1800089ff  xor     edx, edx; Val
0x180008a01  lea     rcx, [rbp+var_58]; void *
0x180008a05  lea     r8d, [rax+44h]; Size
0x180008a09  call    memset_0
0x180008a0e  call    DloadAcquireSectionWriteAccess
0x180008a13  mov     eax, [rsi+4]
0x180008a16  lea     rdx, __ImageBase
0x180008a1d  mov     r14d, [rsi+8]
0x180008a21  add     rax, rdx
0x180008a24  mov     r15d, [rsi+14h]
0x180008a28  add     r14, rdx
0x180008a2b  mov     ecx, [rsi+1Ch]
0x180008a2e  add     r15, rdx
0x180008a31  mov     [rbp+lpLibFileName], rax
0x180008a35  mov     eax, [rsi]
0x180008a37  mov     dword ptr [rbp+Arguments], ecx
0x180008a3a  mov     [rbp+var_58], 48h ; 'H'
0x180008a41  mov     [rbp+var_50], rsi
0x180008a45  mov     [rbp+var_48], r12
0x180008a49  mov     [rbp+var_38], 0
0x180008a50  mov     [rbp+lpProcName], 0
0x180008a58  mov     [rbp+var_28], 0
0x180008a60  mov     [rbp+var_20], 0
0x180008a68  mov     [rbp+var_18], 0
0x180008a6f  test    al, 1
0x180008a71  jnz     short loc_180008A9C
0x180008a73  lea     rax, [rbp+var_58]
0x180008a77  mov     [rbp+Arguments], rax
0x180008a7b  call    DloadReleaseSectionWriteAccess
0x180008a80  xor     edx, edx; dwExceptionFlags
0x180008a82  lea     r9, [rbp+Arguments]; lpArguments
0x180008a86  mov     ecx, 0C06D0057h; dwExceptionCode
0x180008a8b  lea     r8d, [rdx+1]; nNumberOfArguments
0x180008a8f  call    cs:__imp_RaiseException
0x180008a95  xor     eax, eax
0x180008a97  jmp     loc_180008CD9
0x180008a9c  mov     eax, [rsi+0Ch]
0x180008a9f  mov     rcx, r12
0x180008aa2  mov     rbx, [r14]
0x180008aa5  sub     rcx, rax
0x180008aa8  sub     rcx, rdx
0x180008aab  sar     rcx, 3
0x180008aaf  mov     eax, ecx
0x180008ab1  mov     ecx, [rsi+10h]
0x180008ab4  lea     r13, ds:0[rax*8]
0x180008abc  xor     eax, eax
0x180008abe  add     rcx, r13
0x180008ac1  cmp     [rcx+rdx], rax
0x180008ac5  setnl   al
0x180008ac8  mov     [rbp+var_38], eax
0x180008acb  test    eax, eax
0x180008acd  jz      short loc_180008AE2
0x180008acf  mov     eax, [rcx+rdx]
0x180008ad2  lea     rdx, word_180000002
0x180008ad9  add     rax, rdx
0x180008adc  mov     [rbp+lpProcName], rax
0x180008ae0  jmp     short loc_180008AE9
0x180008ae2  movzx   eax, word ptr [rcx+rdx]
0x180008ae6  mov     dword ptr [rbp+lpProcName], eax
0x180008ae9  mov     rax, cs:__pfnDliNotifyHook2
0x180008af0  xor     edi, edi
0x180008af2  test    rax, rax
0x180008af5  jz      short loc_180008B15
0x180008af7  lea     rdx, [rbp+var_58]
0x180008afb  xor     ecx, ecx
0x180008afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b02  mov     rdi, rax
0x180008b05  test    rax, rax
0x180008b08  mov     rax, cs:__pfnDliNotifyHook2
0x180008b0f  jnz     loc_180008CAF
0x180008b15  test    rbx, rbx
0x180008b18  jnz     loc_180008BE1
0x180008b1e  test    rax, rax
0x180008b21  jz      short loc_180008B37
0x180008b23  lea     rdx, [rbp+var_58]
0x180008b27  lea     ecx, [rbx+1]
0x180008b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b2f  mov     rbx, rax
0x180008b32  test    rax, rax
0x180008b35  jnz     short loc_180008BA2
0x180008b37  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180008b3b  xor     r8d, r8d; dwFlags
0x180008b3e  xor     edx, edx; hFile
0x180008b40  call    cs:__imp_LoadLibraryExA
0x180008b46  mov     rbx, rax
0x180008b49  test    rax, rax
0x180008b4c  jnz     short loc_180008BA2
0x180008b4e  call    cs:__imp_GetLastError
0x180008b54  mov     [rbp+var_18], eax
0x180008b57  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180008b5e  test    rax, rax
0x180008b61  jz      short loc_180008B77
0x180008b63  lea     rdx, [rbp+var_58]
0x180008b67  lea     ecx, [rbx+3]
0x180008b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b6f  mov     rbx, rax
0x180008b72  test    rax, rax
0x180008b75  jnz     short loc_180008BA2
0x180008b77  lea     rax, [rbp+var_58]
0x180008b7b  mov     [rbp+Arguments], rax
0x180008b7f  call    DloadReleaseSectionWriteAccess
0x180008b84  xor     edx, edx; dwExceptionFlags
0x180008b86  lea     r9, [rbp+Arguments]; lpArguments
0x180008b8a  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180008b8f  lea     r8d, [rdx+1]; nNumberOfArguments
0x180008b93  call    cs:__imp_RaiseException
0x180008b99  mov     rax, [rbp+var_20]
0x180008b9d  jmp     loc_180008CD9
0x180008ba2  xor     eax, eax
0x180008ba4  lock cmpxchg [r14], rbx
0x180008ba9  mov     r14, rax
0x180008bac  jnz     short loc_180008BC4
0x180008bae  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180008bb2  jz      short loc_180008BDA
0x180008bb4  cmp     dword ptr [rsi+18h], 0
0x180008bb8  jz      short loc_180008BDA
0x180008bba  mov     rcx, rsi
0x180008bbd  call    NewUnloadInfo
0x180008bc2  jmp     short loc_180008BDA
0x180008bc4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180008bc8  jz      short loc_180008BD3
0x180008bca  mov     rcx, rbx; hLibModule
0x180008bcd  call    cs:__imp_FreeLibrary
0x180008bd3  cmp     rbx, r14
0x180008bd6  cmovnz  rbx, r14
0x180008bda  mov     rax, cs:__pfnDliNotifyHook2
0x180008be1  mov     [rbp+var_28], rbx
0x180008be5  test    rax, rax
0x180008be8  jz      short loc_180008C02
0x180008bea  lea     rdx, [rbp+var_58]
0x180008bee  mov     ecx, 2
0x180008bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bf8  mov     rdi, rax
0x180008bfb  mov     rax, cs:__pfnDliNotifyHook2
0x180008c02  test    rdi, rdi
0x180008c05  jnz     loc_180008CAB
0x180008c0b  cmp     [rsi+14h], edi
0x180008c0e  jz      short loc_180008C3B
0x180008c10  cmp     [rsi+1Ch], edi
0x180008c13  jz      short loc_180008C3B
0x180008c15  movsxd  rcx, dword ptr [rbx+3Ch]
0x180008c19  cmp     dword ptr [rcx+rbx], 4550h
0x180008c20  jnz     short loc_180008C3B
0x180008c22  mov     edx, dword ptr [rbp+Arguments]
0x180008c25  cmp     [rcx+rbx+8], edx
0x180008c29  jnz     short loc_180008C3B
0x180008c2b  cmp     rbx, [rcx+rbx+30h]
0x180008c30  jnz     short loc_180008C3B
0x180008c32  mov     rdi, [r15+r13]
0x180008c36  test    rdi, rdi
0x180008c39  jnz     short loc_180008CAB
0x180008c3b  mov     rdx, [rbp+lpProcName]; lpProcName
0x180008c3f  mov     rcx, rbx; hModule
0x180008c42  call    cs:__imp_GetProcAddress
0x180008c48  mov     rdi, rax
0x180008c4b  test    rax, rax
0x180008c4e  jnz     short loc_180008CA4
0x180008c50  call    cs:__imp_GetLastError
0x180008c56  mov     [rbp+var_18], eax
0x180008c59  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180008c60  test    rax, rax
0x180008c63  jz      short loc_180008C79
0x180008c65  lea     rdx, [rbp+var_58]
0x180008c69  lea     ecx, [rdi+4]
0x180008c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c71  mov     rdi, rax
0x180008c74  test    rax, rax
0x180008c77  jnz     short loc_180008CA4
0x180008c79  lea     rax, [rbp+var_58]
0x180008c7d  mov     [rbp+Arguments], rax
0x180008c81  call    DloadReleaseSectionWriteAccess
0x180008c86  xor     edx, edx; dwExceptionFlags
0x180008c88  lea     r9, [rbp+Arguments]; lpArguments
0x180008c8c  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180008c91  lea     r8d, [rdx+1]; nNumberOfArguments
0x180008c95  call    cs:__imp_RaiseException
0x180008c9b  call    DloadAcquireSectionWriteAccess
0x180008ca0  mov     rdi, [rbp+var_20]
0x180008ca4  mov     rax, cs:__pfnDliNotifyHook2
0x180008cab  mov     [r12], rdi
0x180008caf  test    rax, rax
0x180008cb2  jz      short loc_180008CD1
0x180008cb4  lea     rdx, [rbp+var_58]
0x180008cb8  mov     [rbp+var_18], 0
0x180008cbf  mov     ecx, 5
0x180008cc4  mov     [rbp+var_28], rbx
0x180008cc8  mov     [rbp+var_20], rdi
0x180008ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cd1  call    DloadReleaseSectionWriteAccess
0x180008cd6  mov     rax, rdi
0x180008cd9  add     rsp, 78h
0x180008cdd  pop     r15
0x180008cdf  pop     r14
0x180008ce1  pop     r13
0x180008ce3  pop     r12
0x180008ce5  pop     rdi
0x180008ce6  pop     rsi
0x180008ce7  pop     rbx
0x180008ce8  pop     rbp
0x180008ce9  retn
```
