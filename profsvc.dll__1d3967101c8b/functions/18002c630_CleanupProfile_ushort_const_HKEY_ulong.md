# _CleanupProfile(ushort const *,HKEY__ *,ulong)

- ea: `0x18002c630`
- end: `0x18002cba0`
- name: `?_CleanupProfile@@YAJPEBGPEAUHKEY__@@K@Z`
- size: `1392`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002f4fc`

## callees

- `0x1800090d8`
- `0x1800164e0`
- `0x18001fb70`
- `0x180021ca0`
- `0x1800245c0`
- `0x18002c630`
- `0x18002d2d8`
- `0x180030624`
- `0x18003a730`
- `0x18003ea9c`
- `0x18003ecc8`
- `0x18003f1f0`
- `0x18003f42c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c6a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c8ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ca47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002cb93`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c6a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c8ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ca47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002cb93`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002c882`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002c8df`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002c882`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002c8df`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002c76d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002c82b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002c892`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002c971`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002c76d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002c82b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002c892`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002c971`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002c788`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002c7b9`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002c788`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002c7b9`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18002c6c6`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18002c6c6`

## string_xrefs

- `0x18002c685`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`
- `0x18002c79c`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`
- `0x18002c7cd`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`
- `0x18002c9d7`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`
- `0x18002ca21`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`
- `0x18002caa1`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`
- `0x18002cb77`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`

## pseudocode

```c
__int64 __fastcall _CleanupProfile(const unsigned __int16 *a1, HKEY a2, unsigned int a3)
{
  __int64 v3; // r15
  int BasicProfileFolderPath; // r14d
  __int64 v7; // rdx
  char v9; // r12
  __int64 v10; // r14
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  int v13; // r8d
  bool v14; // si
  int v15; // eax
  wil::details::in1diag3 *v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  unsigned int v19; // esi
  int v20; // eax
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // [rsp+20h] [rbp-E0h]
  FILETIME v24; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  FILETIME FileTime1; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-B8h] BYREF
  FILETIME v28; // [rsp+50h] [rbp-B0h] BYREF
  FILETIME FileTime2; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v30[3]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v31[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+94h] [rbp-6Ch]
  FILETIME *v35; // [rsp+98h] [rbp-68h]
  __int64 v36; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v37[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v3 = a3;
  SRWLock = 0;
  BasicProfileFolderPath = CProfMgrAutoLock::Lock((CProfMgrAutoLock *)&SRWLock, a1);
  if ( BasicProfileFolderPath < 0 )
  {
    v7 = 66;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cleanup.cpp",
      (const char *)(unsigned int)BasicProfileFolderPath,
      v23);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return (unsigned int)BasicProfileFolderPath;
  }
  BasicProfileFolderPath = GetBasicProfileFolderPath(5, a1, v37, 260);
  if ( BasicProfileFolderPath < 0 )
  {
    v7 = 69;
    goto LABEL_3;
  }
  v9 = 0;
  FileTime2 = 0;
  v10 = -1;
  if ( SHRegGetDWORD(a2, a1, L"LocalProfileLoadTimeLow", (unsigned int *)&FileTime2) >= 0
    && SHRegGetDWORD(a2, a1, L"LocalProfileLoadTimeHigh", &FileTime2.dwHighDateTime) >= 0 )
  {
    FileTime1 = 0;
    if ( SHRegGetDWORD(a2, a1, L"LocalProfileCleanupCheckTimeLow", (unsigned int *)&FileTime1) >= 0
      && SHRegGetDWORD(a2, a1, L"LocalProfileCleanupCheckTimeHigh", &FileTime1.dwHighDateTime) >= 0
      && CompareFileTime(&FileTime1, &FileTime2) == -1 )
    {
      v9 = 1;
      v11 = RegDeleteKeyValueW(a2, a1, L"LocalProfileCleanupCheckTimeLow");
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x58,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cleanup.cpp",
          (const char *)(unsigned int)v11,
          v23);
      v12 = RegDeleteKeyValueW(a2, a1, L"LocalProfileCleanupCheckTimeHigh");
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x59,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cleanup.cpp",
          (const char *)(unsigned int)v12,
          v23);
    }
    v24 = 0;
    if ( SHRegGetDWORD(a2, a1, L"LocalProfileUnloadTimeLow", (unsigned int *)&v24) >= 0
      && SHRegGetDWORD(a2, a1, L"LocalProfileUnloadTimeHigh", &v24.dwHighDateTime) >= 0
      && CompareFileTime(&FileTime2, &v24) == -1 )
    {
      v28 = (FILETIME)(864000000000LL * v3 + *(_QWORD *)&v24);
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( CompareFileTime(&v28, &SystemTimeAsFileTime) != -1 )
      {
LABEL_21:
        if ( SRWLock )
          ReleaseSRWLockExclusive(SRWLock);
        return 0;
      }
      goto LABEL_43;
    }
  }
  FileTime1 = 0;
  GetSystemTimeAsFileTime(&FileTime1);
  SystemTimeAsFileTime = 0;
  if ( !v9
    && SHRegGetDWORD(a2, a1, L"LocalProfileCleanupCheckTimeLow", (unsigned int *)&SystemTimeAsFileTime) >= 0
    && SHRegGetDWORD(a2, a1, L"LocalProfileCleanupCheckTimeHigh", &SystemTimeAsFileTime.dwHighDateTime) >= 0 )
  {
    v24 = (FILETIME)(864000000000LL * v3 + *(_QWORD *)&SystemTimeAsFileTime);
    v28 = v24;
    v14 = CompareFileTime(&v28, &FileTime1) == -1;
    goto LABEL_42;
  }
  v15 = SHRegSetDWORD(a2, a1, L"LocalProfileCleanupCheckTimeLow", FileTime1.dwLowDateTime);
  v16 = retaddr;
  if ( v15 >= 0 )
  {
    v15 = SHRegSetDWORD(a2, a1, L"LocalProfileCleanupCheckTimeHigh", FileTime1.dwHighDateTime);
    v16 = retaddr;
    if ( v15 >= 0 )
      goto LABEL_21;
    v17 = 152;
  }
  else
  {
    v17 = 151;
  }
  wil::details::in1diag3::_Log_Hr(
    v16,
    (void *)v17,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cleanup.cpp",
    (const char *)(unsigned int)v15,
    v23);
  memset(v30, 0, sizeof(v30));
  v18 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::InitializeFormat(
          v30,
          L"%s\\%s",
          v37,
          L"ntuser.man");
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cleanup.cpp",
      (const char *)(unsigned int)v18,
      v23);
LABEL_34:
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(v30);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return v19;
  }
  v14 = _CheckFileTime(v30[0], v3);
  if ( !v14 )
  {
    v31[0] = 0;
    v31[1] = 0;
    v32 = 0;
    v20 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::InitializeFormat(
            v31,
            L"%s\\%s",
            v37,
            L"ntuser.dat");
    v19 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAA,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cleanup.cpp",
        (const char *)(unsigned int)v20,
        v23);
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(v31);
      goto LABEL_34;
    }
    v14 = _CheckFileTime(v31[0], v3);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(v31);
  }
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(v30);
LABEL_42:
  if ( !v14 )
    goto LABEL_21;
LABEL_43:
  if ( Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
  {
    v24.dwLowDateTime = v3;
    do
      ++v10;
    while ( v37[v10] );
    v32 = v37;
    v33 = 2 * v10 + 2;
    v34 = 0;
    v35 = &v24;
    v36 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)v37,
      (unsigned int)EVENT_DELETE_OLD_PROFILE,
      v13,
      3,
      (__int64)v31);
  }
  ProfileTelemetry::CleanupDeletingProfile<unsigned short (&)[260]>(v37);
  v21 = DeleteProfileP(a1, v37);
  v22 = v21;
  if ( v21 >= 0 )
    goto LABEL_21;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB4,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cleanup.cpp",
    (const char *)(unsigned int)v21,
    v23);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return v22;
}

```

## disassembly

```asm
0x18002c630  push    rbp
0x18002c632  push    rbx
0x18002c633  push    rsi
0x18002c634  push    r12
0x18002c636  push    r13
0x18002c638  push    r14
0x18002c63a  push    r15
0x18002c63c  lea     rbp, [rsp-1D0h]
0x18002c644  sub     rsp, 2D0h
0x18002c64b  mov     rax, cs:__security_cookie
0x18002c652  xor     rax, rsp
0x18002c655  mov     [rbp+200h+var_40], rax
0x18002c65c  mov     r15d, r8d
0x18002c65f  mov     rsi, rdx
0x18002c662  mov     rbx, rcx
0x18002c665  xor     r13d, r13d
0x18002c668  mov     [rsp+300h+SRWLock], r13
0x18002c66d  mov     rdx, rcx; unsigned __int16 *
0x18002c670  lea     rcx, [rsp+300h+SRWLock]; this
0x18002c675  call    ?Lock@CProfMgrAutoLock@@QEAAJPEBG@Z; CProfMgrAutoLock::Lock(ushort const *)
0x18002c67a  mov     r14d, eax
0x18002c67d  test    eax, eax
0x18002c67f  jns     short loc_18002C6B4
0x18002c681  lea     edx, [r13+42h]; void *
0x18002c685  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002c68c  mov     r9d, r14d; char *
0x18002c68f  mov     rcx, [rbp+208h]; this
0x18002c696  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c69b  nop
0x18002c69c  mov     rcx, [rsp+300h+SRWLock]; SRWLock
0x18002c6a1  test    rcx, rcx
0x18002c6a4  jz      short loc_18002C6AC
0x18002c6a6  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c6ac  mov     eax, r14d
0x18002c6af  jmp     loc_18002C8B3
0x18002c6b4  mov     r9d, 104h
0x18002c6ba  lea     r8, [rbp+200h+var_250]
0x18002c6be  mov     rdx, rbx
0x18002c6c1  mov     ecx, 5
0x18002c6c6  call    cs:__imp_GetBasicProfileFolderPath
0x18002c6cc  mov     r14d, eax
0x18002c6cf  test    eax, eax
0x18002c6d1  jns     short loc_18002C6DA
0x18002c6d3  mov     edx, 45h ; 'E'
0x18002c6d8  jmp     short loc_18002C685
0x18002c6da  mov     r12b, r13b
0x18002c6dd  mov     qword ptr [rsp+300h+FileTime2.dwLowDateTime], r13
0x18002c6e2  lea     r9, [rsp+300h+FileTime2]; unsigned int *
0x18002c6e7  lea     r8, aLocalprofilelo; "LocalProfileLoadTimeLow"
0x18002c6ee  mov     rdx, rbx; unsigned __int16 *
0x18002c6f1  mov     rcx, rsi; HKEY
0x18002c6f4  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002c6f9  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002c6fd  test    eax, eax
0x18002c6ff  js      loc_18002C8D5
0x18002c705  lea     r9, [rsp+300h+FileTime2.dwHighDateTime]; unsigned int *
0x18002c70a  lea     r8, aLocalprofilelo_0; "LocalProfileLoadTimeHigh"
0x18002c711  mov     rdx, rbx; unsigned __int16 *
0x18002c714  mov     rcx, rsi; HKEY
0x18002c717  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002c71c  test    eax, eax
0x18002c71e  js      loc_18002C8D5
0x18002c724  mov     qword ptr [rsp+300h+FileTime1.dwLowDateTime], r13
0x18002c729  lea     r9, [rsp+300h+FileTime1]; unsigned int *
0x18002c72e  lea     r8, aLocalprofilecl; "LocalProfileCleanupCheckTimeLow"
0x18002c735  mov     rdx, rbx; unsigned __int16 *
0x18002c738  mov     rcx, rsi; HKEY
0x18002c73b  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002c740  test    eax, eax
0x18002c742  js      loc_18002C7DE
0x18002c748  lea     r9, [rsp+300h+FileTime1.dwHighDateTime]; unsigned int *
0x18002c74d  lea     r8, aLocalprofilecl_0; "LocalProfileCleanupCheckTimeHigh"
0x18002c754  mov     rdx, rbx; unsigned __int16 *
0x18002c757  mov     rcx, rsi; HKEY
0x18002c75a  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002c75f  test    eax, eax
0x18002c761  js      short loc_18002C7DE
0x18002c763  lea     rdx, [rsp+300h+FileTime2]; lpFileTime2
0x18002c768  lea     rcx, [rsp+300h+FileTime1]; lpFileTime1
0x18002c76d  call    cs:__imp_CompareFileTime
0x18002c773  cmp     eax, r14d
0x18002c776  jnz     short loc_18002C7DE
0x18002c778  mov     r12b, 1
0x18002c77b  lea     r8, aLocalprofilecl; "LocalProfileCleanupCheckTimeLow"
0x18002c782  mov     rdx, rbx; lpSubKey
0x18002c785  mov     rcx, rsi; hKey
0x18002c788  call    cs:__imp_RegDeleteKeyValueW
0x18002c78e  mov     rcx, [rbp+208h]; this
0x18002c795  test    eax, eax
0x18002c797  jns     short loc_18002C7AC
0x18002c799  mov     r9d, eax; char *
0x18002c79c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002c7a3  lea     edx, [r14+59h]; void *
0x18002c7a7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c7ac  lea     r8, aLocalprofilecl_0; "LocalProfileCleanupCheckTimeHigh"
0x18002c7b3  mov     rdx, rbx; lpSubKey
0x18002c7b6  mov     rcx, rsi; hKey
0x18002c7b9  call    cs:__imp_RegDeleteKeyValueW
0x18002c7bf  mov     rcx, [rbp+208h]; this
0x18002c7c6  test    eax, eax
0x18002c7c8  jns     short loc_18002C7DE
0x18002c7ca  mov     r9d, eax; char *
0x18002c7cd  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002c7d4  mov     edx, 59h ; 'Y'; void *
0x18002c7d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c7de  mov     qword ptr [rsp+300h+var_2D0.dwLowDateTime], r13
0x18002c7e3  lea     r9, [rsp+300h+var_2D0]; unsigned int *
0x18002c7e8  lea     r8, aLocalprofileun; "LocalProfileUnloadTimeLow"
0x18002c7ef  mov     rdx, rbx; unsigned __int16 *
0x18002c7f2  mov     rcx, rsi; HKEY
0x18002c7f5  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002c7fa  test    eax, eax
0x18002c7fc  js      loc_18002C8D5
0x18002c802  lea     r9, [rsp+300h+var_2D0.dwHighDateTime]; unsigned int *
0x18002c807  lea     r8, aLocalprofileun_0; "LocalProfileUnloadTimeHigh"
0x18002c80e  mov     rdx, rbx; unsigned __int16 *
0x18002c811  mov     rcx, rsi; HKEY
0x18002c814  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002c819  test    eax, eax
0x18002c81b  js      loc_18002C8D5
0x18002c821  lea     rdx, [rsp+300h+var_2D0]; lpFileTime2
0x18002c826  lea     rcx, [rsp+300h+FileTime2]; lpFileTime1
0x18002c82b  call    cs:__imp_CompareFileTime
0x18002c831  cmp     eax, r14d
0x18002c834  jnz     loc_18002C8D5
0x18002c83a  mov     eax, [rsp+300h+var_2D0.dwHighDateTime]
0x18002c83e  mov     [rsp+300h+SystemTimeAsFileTime.dwHighDateTime], eax
0x18002c842  mov     eax, [rsp+300h+var_2D0.dwLowDateTime]
0x18002c846  mov     [rsp+300h+SystemTimeAsFileTime.dwLowDateTime], eax
0x18002c84a  mov     rcx, r15
0x18002c84d  mov     rax, 0C92A69C000h
0x18002c857  imul    rcx, rax
0x18002c85b  mov     rax, qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime]
0x18002c860  add     rax, rcx
0x18002c863  mov     qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002c868  mov     ecx, [rsp+300h+SystemTimeAsFileTime.dwLowDateTime]
0x18002c86c  mov     [rsp+300h+var_2B0.dwLowDateTime], ecx
0x18002c870  shr     rax, 20h
0x18002c874  mov     [rsp+300h+var_2B0.dwHighDateTime], eax
0x18002c878  mov     qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime], r13
0x18002c87d  lea     rcx, [rsp+300h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002c882  call    cs:__imp_GetSystemTimeAsFileTime
0x18002c888  lea     rdx, [rsp+300h+SystemTimeAsFileTime]; lpFileTime2
0x18002c88d  lea     rcx, [rsp+300h+var_2B0]; lpFileTime1
0x18002c892  call    cs:__imp_CompareFileTime
0x18002c898  cmp     eax, r14d
0x18002c89b  jz      loc_18002CAEE
0x18002c8a1  mov     rcx, [rsp+300h+SRWLock]; SRWLock
0x18002c8a6  test    rcx, rcx
0x18002c8a9  jz      short loc_18002C8B1
0x18002c8ab  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c8b1  xor     eax, eax
0x18002c8b3  mov     rcx, [rbp+200h+var_40]
0x18002c8ba  xor     rcx, rsp; StackCookie
0x18002c8bd  call    __security_check_cookie
0x18002c8c2  add     rsp, 2D0h
0x18002c8c9  pop     r15
0x18002c8cb  pop     r14
0x18002c8cd  pop     r13
0x18002c8cf  pop     r12
0x18002c8d1  pop     rsi
0x18002c8d2  pop     rbx
0x18002c8d3  pop     rbp
0x18002c8d4  retn
0x18002c8d5  mov     qword ptr [rsp+300h+FileTime1.dwLowDateTime], r13
0x18002c8da  lea     rcx, [rsp+300h+FileTime1]; lpSystemTimeAsFileTime
0x18002c8df  call    cs:__imp_GetSystemTimeAsFileTime
0x18002c8e5  mov     qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime], r13
0x18002c8ea  test    r12b, r12b
0x18002c8ed  jnz     loc_18002C983
0x18002c8f3  lea     r9, [rsp+300h+SystemTimeAsFileTime]; unsigned int *
0x18002c8f8  lea     r8, aLocalprofilecl; "LocalProfileCleanupCheckTimeLow"
0x18002c8ff  mov     rdx, rbx; unsigned __int16 *
0x18002c902  mov     rcx, rsi; HKEY
0x18002c905  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002c90a  test    eax, eax
0x18002c90c  js      short loc_18002C983
0x18002c90e  lea     r9, [rsp+300h+SystemTimeAsFileTime.dwHighDateTime]; unsigned int *
0x18002c913  lea     r8, aLocalprofilecl_0; "LocalProfileCleanupCheckTimeHigh"
0x18002c91a  mov     rdx, rbx; unsigned __int16 *
0x18002c91d  mov     rcx, rsi; HKEY
0x18002c920  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002c925  test    eax, eax
0x18002c927  js      short loc_18002C983
0x18002c929  mov     eax, [rsp+300h+SystemTimeAsFileTime.dwHighDateTime]
0x18002c92d  mov     [rsp+300h+var_2D0.dwHighDateTime], eax
0x18002c931  mov     eax, [rsp+300h+SystemTimeAsFileTime.dwLowDateTime]
0x18002c935  mov     [rsp+300h+var_2D0.dwLowDateTime], eax
0x18002c939  mov     rcx, r15
0x18002c93c  mov     rax, 0C92A69C000h
0x18002c946  imul    rcx, rax
0x18002c94a  mov     rax, qword ptr [rsp+300h+var_2D0.dwLowDateTime]
0x18002c94f  add     rax, rcx
0x18002c952  mov     qword ptr [rsp+300h+var_2D0.dwLowDateTime], rax
0x18002c957  mov     ecx, [rsp+300h+var_2D0.dwLowDateTime]
0x18002c95b  mov     [rsp+300h+var_2B0.dwLowDateTime], ecx
0x18002c95f  shr     rax, 20h
0x18002c963  mov     [rsp+300h+var_2B0.dwHighDateTime], eax
0x18002c967  lea     rdx, [rsp+300h+FileTime1]; lpFileTime2
0x18002c96c  lea     rcx, [rsp+300h+var_2B0]; lpFileTime1
0x18002c971  call    cs:__imp_CompareFileTime
0x18002c977  cmp     eax, r14d
0x18002c97a  setz    sil
0x18002c97e  jmp     loc_18002CAE5
0x18002c983  mov     r9d, [rsp+300h+FileTime1.dwLowDateTime]; unsigned int
0x18002c988  lea     r8, aLocalprofilecl; "LocalProfileCleanupCheckTimeLow"
0x18002c98f  mov     rdx, rbx; unsigned __int16 *
0x18002c992  mov     rcx, rsi; HKEY
0x18002c995  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002c99a  mov     rcx, [rbp+208h]
0x18002c9a1  test    eax, eax
0x18002c9a3  jns     short loc_18002C9AC
0x18002c9a5  mov     edx, 97h
0x18002c9aa  jmp     short loc_18002C9D7
0x18002c9ac  mov     r9d, [rsp+300h+FileTime1.dwHighDateTime]; unsigned int
0x18002c9b1  lea     r8, aLocalprofilecl_0; "LocalProfileCleanupCheckTimeHigh"
0x18002c9b8  mov     rdx, rbx; unsigned __int16 *
0x18002c9bb  mov     rcx, rsi; HKEY
0x18002c9be  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002c9c3  mov     rcx, [rbp+208h]; this
0x18002c9ca  test    eax, eax
0x18002c9cc  jns     loc_18002C8A1
0x18002c9d2  mov     edx, 98h; void *
0x18002c9d7  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002c9de  mov     r9d, eax; char *
0x18002c9e1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c9e6  mov     [rsp+300h+var_2A0], r13
0x18002c9eb  mov     [rsp+300h+var_298], r13
0x18002c9f0  mov     [rsp+300h+var_290], r13
0x18002c9f5  lea     r9, ?c_szNTUserMan@@3QBGB; "ntuser.man"
0x18002c9fc  lea     r8, [rbp+200h+var_250]
0x18002ca00  lea     rdx, aSS_0; "%s\\%s"
0x18002ca07  lea     rcx, [rsp+300h+var_2A0]
0x18002ca0c  call    ?InitializeFormat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002ca11  mov     esi, eax
0x18002ca13  test    eax, eax
0x18002ca15  jns     short loc_18002CA54
0x18002ca17  mov     rcx, [rbp+208h]; this
0x18002ca1e  mov     r9d, eax; char *
0x18002ca21  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002ca28  mov     edx, 0A4h; void *
0x18002ca2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ca32  lea     rcx, [rsp+300h+var_2A0]
0x18002ca37  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18002ca3c  nop
0x18002ca3d  mov     rcx, [rsp+300h+SRWLock]; SRWLock
0x18002ca42  test    rcx, rcx
0x18002ca45  jz      short loc_18002CA4D
0x18002ca47  call    cs:__imp_ReleaseSRWLockExclusive
0x18002ca4d  mov     eax, esi
0x18002ca4f  jmp     loc_18002C8B3
0x18002ca54  mov     edx, r15d; unsigned int
0x18002ca57  mov     rcx, [rsp+300h+var_2A0]; unsigned __int16 *
0x18002ca5c  call    ?_CheckFileTime@@YA_NPEBGK@Z; _CheckFileTime(ushort const *,ulong)
0x18002ca61  mov     sil, al
0x18002ca64  test    al, al
0x18002ca66  jnz     short loc_18002CADB
0x18002ca68  mov     [rsp+300h+var_288], r13
0x18002ca6d  mov     [rbp+200h+var_280], r13
0x18002ca71  mov     [rbp+200h+var_278], r13
0x18002ca75  lea     r9, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x18002ca7c  lea     r8, [rbp+200h+var_250]
0x18002ca80  lea     rdx, aSS_0; "%s\\%s"
0x18002ca87  lea     rcx, [rsp+300h+var_288]
0x18002ca8c  call    ?InitializeFormat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002ca91  mov     esi, eax
0x18002ca93  test    eax, eax
0x18002ca95  jns     short loc_18002CAC1
0x18002ca97  mov     rcx, [rbp+208h]; this
0x18002ca9e  mov     r9d, eax; char *
0x18002caa1  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002caa8  mov     edx, 0AAh; void *
0x18002caad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cab2  lea     rcx, [rsp+300h+var_288]
0x18002cab7  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18002cabc  jmp     loc_18002CA32
0x18002cac1  mov     edx, r15d; unsigned int
0x18002cac4  mov     rcx, [rsp+300h+var_288]; unsigned __int16 *
0x18002cac9  call    ?_CheckFileTime@@YA_NPEBGK@Z; _CheckFileTime(ushort const *,ulong)
0x18002cace  mov     sil, al
0x18002cad1  lea     rcx, [rsp+300h+var_288]
0x18002cad6  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18002cadb  lea     rcx, [rsp+300h+var_2A0]
0x18002cae0  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18002cae5  test    sil, sil
0x18002cae8  jz      loc_18002C8A1
0x18002caee  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r13b
0x18002caf5  jge     short loc_18002CB4E
0x18002caf7  mov     [rsp+300h+var_2D0.dwLowDateTime], r15d
0x18002cafc  lea     rax, [rbp+200h+var_250]
0x18002cb00  inc     r14
0x18002cb03  cmp     [rax+r14*2], r13w
0x18002cb08  jnz     short loc_18002CB00
0x18002cb0a  lea     eax, ds:2[r14*2]
0x18002cb12  lea     rcx, [rbp+200h+var_250]
0x18002cb16  mov     [rbp+200h+var_278], rcx
0x18002cb1a  mov     [rbp+200h+var_270], eax
0x18002cb1d  mov     [rbp+200h+var_26C], r13d
0x18002cb21  lea     rax, [rsp+300h+var_2D0]
0x18002cb26  mov     [rbp+200h+var_268], rax
  ... truncated ...
```
