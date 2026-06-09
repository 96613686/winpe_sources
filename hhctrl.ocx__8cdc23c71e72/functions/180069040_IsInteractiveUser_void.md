# IsInteractiveUser(void)

- ea: `0x180069040`
- end: `0x1800691e7`
- name: `?IsInteractiveUser@@YAHXZ`
- size: `423`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800310a0`
- `0x180038640`
- `0x1800399ec`
- `0x18003a54c`

## callees

- `0x180002a64`
- `0x180017ca0`
- `0x180065230`
- `0x180067190`
- `0x180069040`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800690b0`
- `KERNEL32!GetProcAddress` at `0x1800690cb`
- `KERNEL32!GetProcAddress` at `0x1800690b0`
- `KERNEL32!GetProcAddress` at `0x1800690cb`
- `ADVAPI32!DeregisterEventSource` at `0x1800691b6`
- `ADVAPI32!DeregisterEventSource` at `0x1800691b6`
- `ADVAPI32!ReportEventA` at `0x1800691ab`
- `ADVAPI32!ReportEventA` at `0x1800691ab`

## string_xrefs

- `0x180069075`: `advapi32.dll`
- `0x1800690a6`: `CreateWellKnownSid`
- `0x1800690bd`: `CheckTokenMembership`

## pseudocode

```c
__int64 __fastcall IsInteractiveUser(HHUrlSecurityManager::InternalSecurityManager *a1)
{
  __int64 v1; // rdx
  HMODULE LibraryA; // rax
  FARPROC ProcAddress; // rax
  unsigned int v5; // [rsp+50h] [rbp-1D8h] BYREF
  int v6; // [rsp+54h] [rbp-1D4h] BYREF
  LPCSTR Strings; // [rsp+58h] [rbp-1D0h] BYREF
  HANDLE hEventLog[10]; // [rsp+60h] [rbp-1C8h] BYREF
  CHAR v9[80]; // [rsp+B0h] [rbp-178h] BYREF
  CHAR LibFileName[272]; // [rsp+100h] [rbp-128h] BYREF

  HHUrlSecurityManager::InternalSecurityManager::Init(a1);
  if ( *(_DWORD *)&dword_18008C2DC != 1 )
  {
    if ( !qword_18008C890
      && GetPathToSystemBinary(LibFileName, v1, "advapi32.dll")
      && (LibraryA = IsolationAwareLoadLibraryA(LibFileName), (qword_18008C890 = LibraryA) != 0) )
    {
      qword_18008C888 = (__int64)GetProcAddress(LibraryA, "CreateWellKnownSid");
      ProcAddress = GetProcAddress(qword_18008C890, "CheckTokenMembership");
      qword_18008C880 = (__int64)ProcAddress;
    }
    else
    {
      ProcAddress = (FARPROC)qword_18008C880;
    }
    if ( qword_18008C888 && ProcAddress )
    {
      v6 = 68;
      v5 = 0;
      if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, CHAR *, int *))qword_18008C888)(11, 0, v9, &v6)
        || (unsigned int)((__int64 (__fastcall *)(_QWORD, CHAR *, unsigned int *))qword_18008C880)(0, v9, &v5) )
      {
        if ( v5 )
          return v5;
      }
      else
      {
        v5 = 0;
      }
      HHEventManager::HHEventManager((HHEventManager *)hEventLog);
      Strings = (LPCSTR)hEventLog[4];
      if ( hEventLog[0] )
      {
        ReportEventA(hEventLog[0], 4u, 0, 0x76Fu, 0, 1u, 0, &Strings, 0);
        DeregisterEventSource(hEventLog[0]);
      }
      return v5;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180069040  sub     rsp, 228h
0x180069047  mov     rax, cs:__security_cookie
0x18006904e  xor     rax, rsp
0x180069051  mov     [rsp+228h+var_18], rax
0x180069059  call    ?Init@InternalSecurityManager@HHUrlSecurityManager@@QEAAXXZ; HHUrlSecurityManager::InternalSecurityManager::Init(void)
0x18006905e  cmp     cs:dword_18008C2DC, 1
0x180069065  jz      loc_1800691CA
0x18006906b  cmp     cs:qword_18008C890, 0
0x180069073  jnz     short loc_1800690DA
0x180069075  lea     r8, aAdvapi32Dll_0; "advapi32.dll"
0x18006907c  lea     rcx, [rsp+228h+LibFileName]; char *
0x180069084  call    ?GetPathToSystemBinary@@YA_NPEADKPEBD@Z; GetPathToSystemBinary(char *,ulong,char const *)
0x180069089  test    al, al
0x18006908b  jz      short loc_1800690DA
0x18006908d  lea     rcx, [rsp+228h+LibFileName]; lpLibFileName
0x180069095  call    IsolationAwareLoadLibraryA
0x18006909a  mov     cs:qword_18008C890, rax
0x1800690a1  test    rax, rax
0x1800690a4  jz      short loc_1800690DA
0x1800690a6  lea     rdx, aCreatewellknow; "CreateWellKnownSid"
0x1800690ad  mov     rcx, rax; hModule
0x1800690b0  call    cs:__imp_GetProcAddress
0x1800690b6  mov     rcx, cs:qword_18008C890; hModule
0x1800690bd  lea     rdx, aChecktokenmemb; "CheckTokenMembership"
0x1800690c4  mov     cs:qword_18008C888, rax
0x1800690cb  call    cs:__imp_GetProcAddress
0x1800690d1  mov     cs:qword_18008C880, rax
0x1800690d8  jmp     short loc_1800690E1
0x1800690da  mov     rax, cs:qword_18008C880
0x1800690e1  mov     r10, cs:qword_18008C888
0x1800690e8  test    r10, r10
0x1800690eb  jz      loc_1800691CA
0x1800690f1  test    rax, rax
0x1800690f4  jz      loc_1800691CA
0x1800690fa  mov     [rsp+228h+var_8], rdi
0x180069102  lea     r9, [rsp+228h+var_1D4]
0x180069107  xor     edi, edi
0x180069109  mov     [rsp+228h+var_1D4], 44h ; 'D'
0x180069111  lea     r8, [rsp+228h+var_178]
0x180069119  mov     [rsp+228h+var_1D8], edi
0x18006911d  xor     edx, edx
0x18006911f  mov     ecx, 0Bh
0x180069124  mov     rax, r10
0x180069127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006912c  test    eax, eax
0x18006912e  jz      short loc_180069155
0x180069130  mov     rax, cs:qword_18008C880
0x180069137  lea     r8, [rsp+228h+var_1D8]
0x18006913c  lea     rdx, [rsp+228h+var_178]
0x180069144  xor     ecx, ecx
0x180069146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006914b  test    eax, eax
0x18006914d  jnz     short loc_180069155
0x18006914f  mov     [rsp+228h+var_1D8], edi
0x180069153  jmp     short loc_18006915B
0x180069155  cmp     [rsp+228h+var_1D8], edi
0x180069159  jnz     short loc_1800691BC
0x18006915b  lea     rcx, [rsp+228h+hEventLog]; this
0x180069160  call    ??0HHEventManager@@QEAA@XZ; HHEventManager::HHEventManager(void)
0x180069165  mov     rax, [rsp+228h+var_1A8]
0x18006916d  mov     [rsp+228h+Strings], rax
0x180069172  cmp     [rsp+228h+hEventLog], rdi
0x180069177  jz      short loc_1800691BC
0x180069179  mov     [rsp+228h+lpRawData], rdi; lpRawData
0x18006917e  lea     rcx, [rsp+228h+Strings]
0x180069183  mov     [rsp+228h+lpStrings], rcx; lpStrings
0x180069188  xor     r8d, r8d; wCategory
0x18006918b  mov     rcx, [rsp+228h+hEventLog]; hEventLog
0x180069190  mov     edx, 4; wType
0x180069195  mov     [rsp+228h+dwDataSize], edi; dwDataSize
0x180069199  mov     r9d, 76Fh; dwEventID
0x18006919f  mov     [rsp+228h+wNumStrings], 1; wNumStrings
0x1800691a6  mov     [rsp+228h+lpUserSid], rdi; lpUserSid
0x1800691ab  call    cs:__imp_ReportEventA
0x1800691b1  mov     rcx, [rsp+228h+hEventLog]; hEventLog
0x1800691b6  call    cs:__imp_DeregisterEventSource
0x1800691bc  mov     eax, [rsp+228h+var_1D8]
0x1800691c0  mov     rdi, [rsp+228h+var_8]
0x1800691c8  jmp     short loc_1800691CF
0x1800691ca  mov     eax, 1
0x1800691cf  mov     rcx, [rsp+228h+var_18]
0x1800691d7  xor     rcx, rsp; StackCookie
0x1800691da  call    __security_check_cookie
0x1800691df  add     rsp, 228h
0x1800691e6  retn
```
