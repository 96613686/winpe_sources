# _CleanupProfile(ushort const *,HKEY__ *,ulong)

- ea: `0x180037bbc`
- end: `0x18003810f`
- name: `?_CleanupProfile@@YAJPEBGPEAUHKEY__@@K@Z`
- size: `1363`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003797c`

## callees

- `0x180014b4c`
- `0x180022440`
- `0x180023950`
- `0x180024cb0`
- `0x180026e5c`
- `0x18002837c`
- `0x18002eae0`
- `0x180030ad0`
- `0x180037bbc`
- `0x18003bc70`
- `0x1800401b0`
- `0x1800403f8`
- `0x180040958`
- `0x180040bcc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180037e17`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180037e7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180037e17`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180037e7d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180037ced`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180037dbb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180037e2d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180037f15`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180037ced`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180037dbb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180037e2d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180037f15`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180037d0d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180037d43`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180037d0d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180037d43`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180037c24`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180037c24`

## string_xrefs

- `0x180037c45`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`
- `0x180037d27`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`
- `0x180037d5d`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`
- `0x180037f80`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`
- `0x180037fcb`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`
- `0x18003803c`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _CleanupProfile(const unsigned __int16 *a1, HKEY a2, unsigned int a3)
{
  __int64 v3; // r15
  int BasicProfileFolderPath; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  char v9; // r12
  __int64 v10; // rbx
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  int v13; // r8d
  bool v15; // r14
  int v16; // eax
  wil::details::in1diag3 *v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  int v20; // r14d
  int v21; // eax
  int v22; // [rsp+20h] [rbp-E0h]
  FILETIME v23; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  FILETIME FileTime1; // [rsp+40h] [rbp-C0h] BYREF
  FILETIME v26; // [rsp+48h] [rbp-B8h] BYREF
  FILETIME FileTime2; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v29[3]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v30[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v31; // [rsp+88h] [rbp-78h]
  int v32; // [rsp+90h] [rbp-70h]
  int v33; // [rsp+94h] [rbp-6Ch]
  FILETIME *v34; // [rsp+98h] [rbp-68h]
  __int64 v35; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v36[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v3 = a3;
  v28 = 0;
  BasicProfileFolderPath = CProfMgrAutoLock::Lock((CProfMgrAutoLock *)&v28, a1);
  v7 = BasicProfileFolderPath;
  if ( BasicProfileFolderPath >= 0 )
  {
    BasicProfileFolderPath = GetBasicProfileFolderPath(5, a1, v36, 260);
    v7 = BasicProfileFolderPath;
    if ( BasicProfileFolderPath < 0 )
    {
      v8 = 69;
      goto LABEL_5;
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
            v22);
        v12 = RegDeleteKeyValueW(a2, a1, L"LocalProfileCleanupCheckTimeHigh");
        if ( v12 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x59,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cleanup.cpp",
            (const char *)(unsigned int)v12,
            v22);
      }
      v23 = 0;
      if ( SHRegGetDWORD(a2, a1, L"LocalProfileUnloadTimeLow", (unsigned int *)&v23) >= 0
        && SHRegGetDWORD(a2, a1, L"LocalProfileUnloadTimeHigh", &v23.dwHighDateTime) >= 0
        && CompareFileTime(&FileTime2, &v23) == -1 )
      {
        v26 = (FILETIME)(864000000000LL * v3 + *(_QWORD *)&v23);
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        if ( CompareFileTime(&v26, &SystemTimeAsFileTime) != -1 )
          goto LABEL_19;
        goto LABEL_38;
      }
    }
    FileTime1 = 0;
    GetSystemTimeAsFileTime(&FileTime1);
    SystemTimeAsFileTime = 0;
    if ( !v9
      && SHRegGetDWORD(a2, a1, L"LocalProfileCleanupCheckTimeLow", (unsigned int *)&SystemTimeAsFileTime) >= 0
      && SHRegGetDWORD(a2, a1, L"LocalProfileCleanupCheckTimeHigh", &SystemTimeAsFileTime.dwHighDateTime) >= 0 )
    {
      v23 = (FILETIME)(864000000000LL * v3 + *(_QWORD *)&SystemTimeAsFileTime);
      v26 = v23;
      v15 = CompareFileTime(&v26, &FileTime1) == -1;
      goto LABEL_37;
    }
    v16 = SHRegSetDWORD(a2, a1, L"LocalProfileCleanupCheckTimeLow", FileTime1.dwLowDateTime);
    v17 = retaddr;
    if ( v16 >= 0 )
    {
      v16 = SHRegSetDWORD(a2, a1, L"LocalProfileCleanupCheckTimeHigh", FileTime1.dwHighDateTime);
      v17 = retaddr;
      if ( v16 >= 0 )
        goto LABEL_19;
      v18 = 152;
    }
    else
    {
      v18 = 151;
    }
    wil::details::in1diag3::_Log_Hr(
      v17,
      (void *)v18,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cleanup.cpp",
      (const char *)(unsigned int)v16,
      v22);
    memset(v29, 0, sizeof(v29));
    v19 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::InitializeFormat(
            v29,
            L"%s\\%s",
            v36,
            L"ntuser.man");
    v20 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cleanup.cpp",
        (const char *)(unsigned int)v19,
        v22);
LABEL_31:
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(v29);
      v7 = v20;
      goto LABEL_20;
    }
    v15 = _CheckFileTime(v29[0], v3);
    if ( !v15 )
    {
      v30[0] = 0;
      v30[1] = 0;
      v31 = 0;
      v21 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::InitializeFormat(
              v30,
              L"%s\\%s",
              v36,
              L"ntuser.dat");
      v20 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cleanup.cpp",
          (const char *)(unsigned int)v21,
          v22);
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(v30);
        goto LABEL_31;
      }
      v15 = _CheckFileTime(v30[0], v3);
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(v30);
    }
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(v29);
LABEL_37:
    if ( !v15 )
      goto LABEL_19;
LABEL_38:
    if ( Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
    {
      v23.dwLowDateTime = v3;
      do
        ++v10;
      while ( v36[v10] );
      v31 = v36;
      v32 = 2 * v10 + 2;
      v33 = 0;
      v34 = &v23;
      v35 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)v36,
        (unsigned int)EVENT_DELETE_OLD_PROFILE,
        v13,
        3,
        (__int64)v30);
    }
    ProfileTelemetry::CleanupDeletingProfile<unsigned short (&)[260]>(v36);
    BasicProfileFolderPath = DeleteProfileP(a1, v36);
    v7 = BasicProfileFolderPath;
    if ( BasicProfileFolderPath < 0 )
    {
      v8 = 180;
      goto LABEL_5;
    }
LABEL_19:
    v7 = 0;
    goto LABEL_20;
  }
  v8 = 66;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cleanup.cpp",
    (const char *)(unsigned int)BasicProfileFolderPath,
    v22);
LABEL_20:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v28);
  return v7;
}

```

## disassembly

```asm
0x180037bbc  push    rbp
0x180037bbe  push    rbx
0x180037bbf  push    rdi
0x180037bc0  push    r12
0x180037bc2  push    r13
0x180037bc4  push    r14
0x180037bc6  push    r15
0x180037bc8  lea     rbp, [rsp-1D0h]
0x180037bd0  sub     rsp, 2D0h
0x180037bd7  mov     rax, cs:__security_cookie
0x180037bde  xor     rax, rsp
0x180037be1  mov     [rbp+200h+var_40], rax
0x180037be8  mov     r15d, r8d
0x180037beb  mov     r14, rdx
0x180037bee  mov     rdi, rcx
0x180037bf1  xor     r13d, r13d
0x180037bf4  mov     [rsp+300h+var_2A8], r13
0x180037bf9  mov     rdx, rcx; unsigned __int16 *
0x180037bfc  lea     rcx, [rsp+300h+var_2A8]; this
0x180037c01  call    ?Lock@CProfMgrAutoLock@@QEAAJPEBG@Z; CProfMgrAutoLock::Lock(ushort const *)
0x180037c06  mov     ebx, eax
0x180037c08  test    eax, eax
0x180037c0a  jns     short loc_180037C12
0x180037c0c  lea     edx, [r13+42h]
0x180037c10  jmp     short loc_180037C3B
0x180037c12  mov     r9d, 104h
0x180037c18  lea     r8, [rbp+200h+var_250]
0x180037c1c  mov     rdx, rdi
0x180037c1f  mov     ecx, 5
0x180037c24  call    cs:__imp_GetBasicProfileFolderPath
0x180037c2b  nop     dword ptr [rax+rax+00h]
0x180037c30  mov     ebx, eax
0x180037c32  test    eax, eax
0x180037c34  jns     short loc_180037C56
0x180037c36  mov     edx, 45h ; 'E'; void *
0x180037c3b  mov     rcx, [rbp+208h]; this
0x180037c42  mov     r9d, eax; char *
0x180037c45  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037c4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037c51  jmp     loc_180037E44
0x180037c56  mov     r12b, r13b
0x180037c59  mov     qword ptr [rsp+300h+FileTime2.dwLowDateTime], r13
0x180037c5e  lea     r9, [rsp+300h+FileTime2]; unsigned int *
0x180037c63  lea     r8, aLocalprofilelo; "LocalProfileLoadTimeLow"
0x180037c6a  mov     rdx, rdi; unsigned __int16 *
0x180037c6d  mov     rcx, r14; HKEY
0x180037c70  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180037c75  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180037c79  test    eax, eax
0x180037c7b  js      loc_180037E73
0x180037c81  lea     r9, [rsp+300h+FileTime2.dwHighDateTime]; unsigned int *
0x180037c86  lea     r8, aLocalprofilelo_0; "LocalProfileLoadTimeHigh"
0x180037c8d  mov     rdx, rdi; unsigned __int16 *
0x180037c90  mov     rcx, r14; HKEY
0x180037c93  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180037c98  test    eax, eax
0x180037c9a  js      loc_180037E73
0x180037ca0  mov     qword ptr [rsp+300h+FileTime1.dwLowDateTime], r13
0x180037ca5  lea     r9, [rsp+300h+FileTime1]; unsigned int *
0x180037caa  lea     r8, aLocalprofilecl; "LocalProfileCleanupCheckTimeLow"
0x180037cb1  mov     rdx, rdi; unsigned __int16 *
0x180037cb4  mov     rcx, r14; HKEY
0x180037cb7  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180037cbc  test    eax, eax
0x180037cbe  js      loc_180037D6E
0x180037cc4  lea     r9, [rsp+300h+FileTime1.dwHighDateTime]; unsigned int *
0x180037cc9  lea     r8, aLocalprofilecl_0; "LocalProfileCleanupCheckTimeHigh"
0x180037cd0  mov     rdx, rdi; unsigned __int16 *
0x180037cd3  mov     rcx, r14; HKEY
0x180037cd6  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180037cdb  test    eax, eax
0x180037cdd  js      loc_180037D6E
0x180037ce3  lea     rdx, [rsp+300h+FileTime2]; lpFileTime2
0x180037ce8  lea     rcx, [rsp+300h+FileTime1]; lpFileTime1
0x180037ced  call    cs:__imp_CompareFileTime
0x180037cf4  nop     dword ptr [rax+rax+00h]
0x180037cf9  cmp     eax, ebx
0x180037cfb  jnz     short loc_180037D6E
0x180037cfd  mov     r12b, 1
0x180037d00  lea     r8, aLocalprofilecl; "LocalProfileCleanupCheckTimeLow"
0x180037d07  mov     rdx, rdi; lpSubKey
0x180037d0a  mov     rcx, r14; hKey
0x180037d0d  call    cs:__imp_RegDeleteKeyValueW
0x180037d14  nop     dword ptr [rax+rax+00h]
0x180037d19  mov     rcx, [rbp+208h]; this
0x180037d20  test    eax, eax
0x180037d22  jns     short loc_180037D36
0x180037d24  mov     r9d, eax; char *
0x180037d27  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037d2e  lea     edx, [rbx+59h]; void *
0x180037d31  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037d36  lea     r8, aLocalprofilecl_0; "LocalProfileCleanupCheckTimeHigh"
0x180037d3d  mov     rdx, rdi; lpSubKey
0x180037d40  mov     rcx, r14; hKey
0x180037d43  call    cs:__imp_RegDeleteKeyValueW
0x180037d4a  nop     dword ptr [rax+rax+00h]
0x180037d4f  mov     rcx, [rbp+208h]; this
0x180037d56  test    eax, eax
0x180037d58  jns     short loc_180037D6E
0x180037d5a  mov     r9d, eax; char *
0x180037d5d  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037d64  mov     edx, 59h ; 'Y'; void *
0x180037d69  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037d6e  mov     qword ptr [rsp+300h+var_2D0.dwLowDateTime], r13
0x180037d73  lea     r9, [rsp+300h+var_2D0]; unsigned int *
0x180037d78  lea     r8, aLocalprofileun; "LocalProfileUnloadTimeLow"
0x180037d7f  mov     rdx, rdi; unsigned __int16 *
0x180037d82  mov     rcx, r14; HKEY
0x180037d85  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180037d8a  test    eax, eax
0x180037d8c  js      loc_180037E73
0x180037d92  lea     r9, [rsp+300h+var_2D0.dwHighDateTime]; unsigned int *
0x180037d97  lea     r8, aLocalprofileun_0; "LocalProfileUnloadTimeHigh"
0x180037d9e  mov     rdx, rdi; unsigned __int16 *
0x180037da1  mov     rcx, r14; HKEY
0x180037da4  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180037da9  test    eax, eax
0x180037dab  js      loc_180037E73
0x180037db1  lea     rdx, [rsp+300h+var_2D0]; lpFileTime2
0x180037db6  lea     rcx, [rsp+300h+FileTime2]; lpFileTime1
0x180037dbb  call    cs:__imp_CompareFileTime
0x180037dc2  nop     dword ptr [rax+rax+00h]
0x180037dc7  cmp     eax, ebx
0x180037dc9  jnz     loc_180037E73
0x180037dcf  mov     eax, [rsp+300h+var_2D0.dwHighDateTime]
0x180037dd3  mov     [rsp+300h+SystemTimeAsFileTime.dwHighDateTime], eax
0x180037dd7  mov     eax, [rsp+300h+var_2D0.dwLowDateTime]
0x180037ddb  mov     [rsp+300h+SystemTimeAsFileTime.dwLowDateTime], eax
0x180037ddf  mov     rcx, r15
0x180037de2  mov     rax, 0C92A69C000h
0x180037dec  imul    rcx, rax
0x180037df0  mov     rax, qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime]
0x180037df5  add     rax, rcx
0x180037df8  mov     qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180037dfd  mov     ecx, [rsp+300h+SystemTimeAsFileTime.dwLowDateTime]
0x180037e01  mov     [rsp+300h+var_2B8.dwLowDateTime], ecx
0x180037e05  shr     rax, 20h
0x180037e09  mov     [rsp+300h+var_2B8.dwHighDateTime], eax
0x180037e0d  mov     qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime], r13
0x180037e12  lea     rcx, [rsp+300h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180037e17  call    cs:__imp_GetSystemTimeAsFileTime
0x180037e1e  nop     dword ptr [rax+rax+00h]
0x180037e23  lea     rdx, [rsp+300h+SystemTimeAsFileTime]; lpFileTime2
0x180037e28  lea     rcx, [rsp+300h+var_2B8]; lpFileTime1
0x180037e2d  call    cs:__imp_CompareFileTime
0x180037e34  nop     dword ptr [rax+rax+00h]
0x180037e39  cmp     eax, ebx
0x180037e3b  jz      loc_180038086
0x180037e41  mov     ebx, r13d
0x180037e44  lea     rcx, [rsp+300h+var_2A8]
0x180037e49  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180037e4e  mov     eax, ebx
0x180037e50  mov     rcx, [rbp+200h+var_40]
0x180037e57  xor     rcx, rsp; StackCookie
0x180037e5a  call    __security_check_cookie
0x180037e5f  add     rsp, 2D0h
0x180037e66  pop     r15
0x180037e68  pop     r14
0x180037e6a  pop     r13
0x180037e6c  pop     r12
0x180037e6e  pop     rdi
0x180037e6f  pop     rbx
0x180037e70  pop     rbp
0x180037e71  retn
0x180037e73  mov     qword ptr [rsp+300h+FileTime1.dwLowDateTime], r13
0x180037e78  lea     rcx, [rsp+300h+FileTime1]; lpSystemTimeAsFileTime
0x180037e7d  call    cs:__imp_GetSystemTimeAsFileTime
0x180037e84  nop     dword ptr [rax+rax+00h]
0x180037e89  mov     qword ptr [rsp+300h+SystemTimeAsFileTime.dwLowDateTime], r13
0x180037e8e  test    r12b, r12b
0x180037e91  jnz     loc_180037F2C
0x180037e97  lea     r9, [rsp+300h+SystemTimeAsFileTime]; unsigned int *
0x180037e9c  lea     r8, aLocalprofilecl; "LocalProfileCleanupCheckTimeLow"
0x180037ea3  mov     rdx, rdi; unsigned __int16 *
0x180037ea6  mov     rcx, r14; HKEY
0x180037ea9  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180037eae  test    eax, eax
0x180037eb0  js      short loc_180037F2C
0x180037eb2  lea     r9, [rsp+300h+SystemTimeAsFileTime.dwHighDateTime]; unsigned int *
0x180037eb7  lea     r8, aLocalprofilecl_0; "LocalProfileCleanupCheckTimeHigh"
0x180037ebe  mov     rdx, rdi; unsigned __int16 *
0x180037ec1  mov     rcx, r14; HKEY
0x180037ec4  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180037ec9  test    eax, eax
0x180037ecb  js      short loc_180037F2C
0x180037ecd  mov     eax, [rsp+300h+SystemTimeAsFileTime.dwHighDateTime]
0x180037ed1  mov     [rsp+300h+var_2D0.dwHighDateTime], eax
0x180037ed5  mov     eax, [rsp+300h+SystemTimeAsFileTime.dwLowDateTime]
0x180037ed9  mov     [rsp+300h+var_2D0.dwLowDateTime], eax
0x180037edd  mov     rcx, r15
0x180037ee0  mov     rax, 0C92A69C000h
0x180037eea  imul    rcx, rax
0x180037eee  mov     rax, qword ptr [rsp+300h+var_2D0.dwLowDateTime]
0x180037ef3  add     rax, rcx
0x180037ef6  mov     qword ptr [rsp+300h+var_2D0.dwLowDateTime], rax
0x180037efb  mov     ecx, [rsp+300h+var_2D0.dwLowDateTime]
0x180037eff  mov     [rsp+300h+var_2B8.dwLowDateTime], ecx
0x180037f03  shr     rax, 20h
0x180037f07  mov     [rsp+300h+var_2B8.dwHighDateTime], eax
0x180037f0b  lea     rdx, [rsp+300h+FileTime1]; lpFileTime2
0x180037f10  lea     rcx, [rsp+300h+var_2B8]; lpFileTime1
0x180037f15  call    cs:__imp_CompareFileTime
0x180037f1c  nop     dword ptr [rax+rax+00h]
0x180037f21  cmp     eax, ebx
0x180037f23  setz    r14b
0x180037f27  jmp     loc_18003807D
0x180037f2c  mov     r9d, [rsp+300h+FileTime1.dwLowDateTime]; unsigned int
0x180037f31  lea     r8, aLocalprofilecl; "LocalProfileCleanupCheckTimeLow"
0x180037f38  mov     rdx, rdi; unsigned __int16 *
0x180037f3b  mov     rcx, r14; HKEY
0x180037f3e  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180037f43  mov     rcx, [rbp+208h]
0x180037f4a  test    eax, eax
0x180037f4c  jns     short loc_180037F55
0x180037f4e  mov     edx, 97h
0x180037f53  jmp     short loc_180037F80
0x180037f55  mov     r9d, [rsp+300h+FileTime1.dwHighDateTime]; unsigned int
0x180037f5a  lea     r8, aLocalprofilecl_0; "LocalProfileCleanupCheckTimeHigh"
0x180037f61  mov     rdx, rdi; unsigned __int16 *
0x180037f64  mov     rcx, r14; HKEY
0x180037f67  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180037f6c  mov     rcx, [rbp+208h]; this
0x180037f73  test    eax, eax
0x180037f75  jns     loc_180037E41
0x180037f7b  mov     edx, 98h; void *
0x180037f80  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037f87  mov     r9d, eax; char *
0x180037f8a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037f8f  mov     [rsp+300h+var_2A0], r13
0x180037f94  mov     [rsp+300h+var_298], r13
0x180037f99  mov     [rsp+300h+var_290], r13
0x180037f9e  lea     r9, ?c_szNTUserMan@@3QBGB; "ntuser.man"
0x180037fa5  lea     r8, [rbp+200h+var_250]
0x180037fa9  lea     rdx, aSS_0; "%s\\%s"
0x180037fb0  lea     rcx, [rsp+300h+var_2A0]
0x180037fb5  call    ?InitializeFormat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180037fba  mov     r14d, eax
0x180037fbd  test    eax, eax
0x180037fbf  jns     short loc_180037FEE
0x180037fc1  mov     rcx, [rbp+208h]; this
0x180037fc8  mov     r9d, eax; char *
0x180037fcb  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037fd2  mov     edx, 0A4h; void *
0x180037fd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037fdc  lea     rcx, [rsp+300h+var_2A0]
0x180037fe1  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180037fe6  mov     ebx, r14d
0x180037fe9  jmp     loc_180037E44
0x180037fee  mov     edx, r15d; unsigned int
0x180037ff1  mov     rcx, [rsp+300h+var_2A0]; unsigned __int16 *
0x180037ff6  call    ?_CheckFileTime@@YA_NPEBGK@Z; _CheckFileTime(ushort const *,ulong)
0x180037ffb  mov     r14b, al
0x180037ffe  test    al, al
0x180038000  jnz     short loc_180038073
0x180038002  mov     [rsp+300h+var_288], r13
0x180038007  mov     [rbp+200h+var_280], r13
0x18003800b  mov     [rbp+200h+var_278], r13
0x18003800f  lea     r9, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x180038016  lea     r8, [rbp+200h+var_250]
0x18003801a  lea     rdx, aSS_0; "%s\\%s"
0x180038021  lea     rcx, [rsp+300h+var_288]
0x180038026  call    ?InitializeFormat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18003802b  mov     r14d, eax
0x18003802e  test    eax, eax
0x180038030  jns     short loc_180038059
0x180038032  mov     rcx, [rbp+208h]; this
0x180038039  mov     r9d, eax; char *
0x18003803c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x180038043  mov     edx, 0AAh; void *
0x180038048  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003804d  lea     rcx, [rsp+300h+var_288]
0x180038052  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180038057  jmp     short loc_180037FDC
0x180038059  mov     edx, r15d; unsigned int
0x18003805c  mov     rcx, [rsp+300h+var_288]; unsigned __int16 *
0x180038061  call    ?_CheckFileTime@@YA_NPEBGK@Z; _CheckFileTime(ushort const *,ulong)
0x180038066  mov     r14b, al
0x180038069  lea     rcx, [rsp+300h+var_288]
0x18003806e  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180038073  lea     rcx, [rsp+300h+var_2A0]
0x180038078  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18003807d  test    r14b, r14b
0x180038080  jz      loc_180037E41
0x180038086  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r13b
0x18003808d  jge     short loc_1800380E5
0x18003808f  mov     [rsp+300h+var_2D0.dwLowDateTime], r15d
0x180038094  lea     rax, [rbp+200h+var_250]
0x180038098  inc     rbx
0x18003809b  cmp     [rax+rbx*2], r13w
0x1800380a0  jnz     short loc_180038098
0x1800380a2  lea     eax, ds:2[rbx*2]
0x1800380a9  lea     rcx, [rbp+200h+var_250]
0x1800380ad  mov     [rbp+200h+var_278], rcx
0x1800380b1  mov     [rbp+200h+var_270], eax
0x1800380b4  mov     [rbp+200h+var_26C], r13d
0x1800380b8  lea     rax, [rsp+300h+var_2D0]
0x1800380bd  mov     [rbp+200h+var_268], rax
0x1800380c1  mov     [rbp+200h+var_260], 4
0x1800380c9  lea     rax, [rsp+300h+var_288]
0x1800380ce  mov     qword ptr [rsp+300h+var_2E0], rax
  ... truncated ...
```
