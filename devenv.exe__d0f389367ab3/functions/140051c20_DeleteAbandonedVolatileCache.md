# DeleteAbandonedVolatileCache

- ea: `0x140051c20`
- end: `0x140051fe9`
- name: `DeleteAbandonedVolatileCache`
- size: `969`
- prototype: `__int64 __fastcall(HANDLE hToken, HKEY hKey)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x14005215c`

## callees

- `0x140001020`
- `0x140003070`
- `0x140003160`
- `0x1400094b8`
- `0x1400095f4`
- `0x14000b710`
- `0x14000fb64`
- `0x140022db0`
- `0x14002bd70`
- `0x140033ab0`
- `0x140046514`
- `0x14004a1e0`
- `0x140051c20`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140051fae`
- `ADVAPI32!RegCloseKey` at `0x140051fae`
- `ADVAPI32!RegOpenKeyExW` at `0x140051cc3`
- `ADVAPI32!RegOpenKeyExW` at `0x140051cc3`
- `ADVAPI32!RegEnumKeyExW` at `0x140051d4c`
- `ADVAPI32!RegEnumKeyExW` at `0x140051d4c`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140051c92`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140051c92`
- `ADVAPI32!RevertToSelf` at `0x140051f7c`
- `ADVAPI32!RevertToSelf` at `0x140051f7c`
- `KERNEL32!ReleaseSemaphore` at `0x140051e06`
- `KERNEL32!ReleaseSemaphore` at `0x140051e66`
- `KERNEL32!ReleaseSemaphore` at `0x140051e06`
- `KERNEL32!ReleaseSemaphore` at `0x140051e66`
- `KERNEL32!CloseHandle` at `0x140051e3c`
- `KERNEL32!CloseHandle` at `0x140051e9c`
- `KERNEL32!CloseHandle` at `0x140051e3c`
- `KERNEL32!CloseHandle` at `0x140051e9c`
- `KERNEL32!GetLastError` at `0x140051e10`
- `KERNEL32!GetLastError` at `0x140051e33`
- `KERNEL32!GetLastError` at `0x140051e70`
- `KERNEL32!GetLastError` at `0x140051e93`
- `KERNEL32!GetLastError` at `0x140051e10`
- `KERNEL32!GetLastError` at `0x140051e33`
- `KERNEL32!GetLastError` at `0x140051e70`
- `KERNEL32!GetLastError` at `0x140051e93`
- `VCRUNTIME140!wcsstr` at `0x140051d62`
- `VCRUNTIME140!wcsstr` at `0x140051d62`

## string_xrefs

- `0x140051de0`: `Could not create or find pkgdef Semaphore`
- `0x140051ce8`: `_Config_`
- `0x140051f0f`: `Removing abandoned configuration cache`
- `0x140051f39`: `Could not remove abandoned configuration cache`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
LSTATUS __fastcall DeleteAbandonedVolatileCache(HANDLE hToken, HKEY hKey, _QWORD *a3)
{
  HKEY v5; // r14
  bool v6; // di
  DWORD i; // esi
  int v8; // ebx
  const unsigned __int16 *v9; // rdx
  HANDLE v10; // rbx
  signed int v11; // eax
  unsigned int v12; // edx
  bool v13; // r15
  HANDLE v14; // rbx
  signed int LastError; // eax
  unsigned int v16; // edx
  __int64 v17; // rsi
  const unsigned __int16 *v18; // rbx
  _QWORD *v19; // rax
  int v20; // eax
  LPCWSTR v21; // rdx
  signed __int32 v22; // eax
  bool v23; // cc
  LSTATUS result; // eax
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v27; // [rsp+58h] [rbp-A8h]
  __int64 v28; // [rsp+68h] [rbp-98h]
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v30; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hSemaphore[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v32; // [rsp+90h] [rbp-70h]
  __int128 v33; // [rsp+98h] [rbp-68h] BYREF
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int128 v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+C0h] [rbp-40h]
  struct _FILETIME ftLastWriteTime; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t SubStr[16]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Name[264]; // [rsp+F0h] [rbp-10h] BYREF

  v5 = 0;
  v27 = 0u;
  v28 = 0;
  lpSubKey = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpSubKey,
    *a3);
  ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RemoveFileSpec(&lpSubKey);
  v6 = ImpersonateLoggedOnUser(hToken);
  hKeya = 0;
  if ( !RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &hKeya) )
  {
    v5 = hKeya;
    *(_QWORD *)&v27 = hKeya;
    DWORD2(v27) = 0;
    cchName = 260;
    wcscpy(SubStr, L"_Config_");
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v36 = 10;
    for ( i = 0; !RegEnumKeyExW(hKeya, i, Name, &cchName, 0, 0, 0, &ftLastWriteTime); ++i )
    {
      if ( wcsstr(Name, SubStr) )
      {
        hSemaphore[0] = &CCacheUsageTracker::`vftable';
        hSemaphore[1] = 0;
        v32 = 0;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v30,
          Name);
        v8 = CCacheUsageTracker::SetName(hSemaphore, &v30);
        v9 = v30 - 12;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v30 - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9);
        }
        if ( v8 >= 0 )
        {
          v13 = (_BYTE)v32 != 0;
          v14 = hSemaphore[1];
          if ( hSemaphore[1] )
          {
            if ( BYTE1(v32) && !ReleaseSemaphore(hSemaphore[1], 1, 0) )
            {
              LastError = GetLastError();
              v16 = (unsigned __int16)LastError | 0x80070000;
              if ( LastError <= 0 )
                v16 = LastError;
              CLogger::LogError(L"Failed to decrement PkgDef Semaphore", v16, 0);
              GetLastError();
            }
            CloseHandle(v14);
          }
          if ( v13 )
            ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
              &v33,
              Name);
        }
        else
        {
          _mm_lfence();
          CLogger::LogError(L"Could not create or find pkgdef Semaphore", v8, Name);
          v10 = hSemaphore[1];
          if ( hSemaphore[1] )
          {
            if ( BYTE1(v32) && !ReleaseSemaphore(hSemaphore[1], 1, 0) )
            {
              v11 = GetLastError();
              v12 = (unsigned __int16)v11 | 0x80070000;
              if ( v11 <= 0 )
                v12 = v11;
              CLogger::LogError(L"Failed to decrement PkgDef Semaphore", v12, 0);
              GetLastError();
            }
            CloseHandle(v10);
          }
        }
      }
      cchName = 260;
    }
    while ( v34 )
    {
      v17 = *((_QWORD *)&v33 + 1);
      if ( !*((_QWORD *)&v33 + 1) )
        ATL::AtlThrowImpl(-2147467259);
      v18 = (const unsigned __int16 *)(ATL::CSimpleStringT<unsigned short,0>::CloneData(*(_QWORD *)(*((_QWORD *)&v33 + 1)
                                                                                                  + 16LL) - 24LL)
                                     + 24);
      v30 = v18;
      v19 = *(_QWORD **)(v17 + 8);
      *((_QWORD *)&v33 + 1) = v19;
      if ( v19 )
        *v19 = 0;
      else
        *(_QWORD *)&v33 = 0;
      ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::FreeNode(
        &v33,
        v17);
      CLogger::LogInfo(L"Removing abandoned configuration cache", 0, v18);
      v20 = DeleteKeyIfExists(hKeya, hToken);
      if ( v20 < 0 )
      {
        _mm_lfence();
        CLogger::LogError(L"Could not remove abandoned configuration cache", v20, 0);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v18 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v18 - 3) + 8LL))(*((_QWORD *)v18 - 3));
      }
    }
    ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&v33);
  }
  if ( v6 )
    RevertToSelf();
  v21 = lpSubKey - 12;
  v22 = _InterlockedExchangeAdd((volatile signed __int32 *)lpSubKey - 2, 0xFFFFFFFF);
  v23 = v22 <= 1;
  result = v22 - 1;
  if ( v23 )
  {
    _mm_lfence();
    result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 8LL))(*(_QWORD *)v21);
  }
  if ( v5 )
    return RegCloseKey(v5);
  return result;
}

```

## disassembly

```asm
0x140051c20  mov     [rsp-8+arg_18], rbx
0x140051c25  push    rbp
0x140051c26  push    rsi
0x140051c27  push    rdi
0x140051c28  push    r12
0x140051c2a  push    r13
0x140051c2c  push    r14
0x140051c2e  push    r15
0x140051c30  lea     rbp, [rsp-210h]
0x140051c38  sub     rsp, 310h
0x140051c3f  mov     rax, cs:__security_cookie
0x140051c46  xor     rax, rsp
0x140051c49  mov     [rbp+240h+var_40], rax
0x140051c50  mov     rbx, rdx
0x140051c53  mov     r12, rcx
0x140051c56  xor     r13d, r13d
0x140051c59  xorps   xmm0, xmm0
0x140051c5c  movups  [rsp+340h+var_2E8], xmm0
0x140051c61  mov     r14d, r13d
0x140051c64  mov     qword ptr [rsp+340h+var_2E8], r13
0x140051c69  mov     dword ptr [rsp+340h+var_2E8+8], r13d
0x140051c6e  mov     [rsp+340h+var_2D8], r13
0x140051c73  mov     [rsp+340h+lpSubKey], r13
0x140051c78  mov     rdx, [r8]
0x140051c7b  lea     rcx, [rsp+340h+lpSubKey]
0x140051c80  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140051c85  lea     rcx, [rsp+340h+lpSubKey]
0x140051c8a  call    ?RemoveFileSpec@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::RemoveFileSpec(void)
0x140051c8f  mov     rcx, r12; hToken
0x140051c92  call    cs:__imp_ImpersonateLoggedOnUser
0x140051c98  test    eax, eax
0x140051c9a  setnz   dil
0x140051c9e  mov     [rsp+340h+var_300], dil
0x140051ca3  mov     [rsp+340h+hKey], r13
0x140051ca8  lea     rax, [rsp+340h+hKey]
0x140051cad  mov     [rsp+340h+phkResult], rax; phkResult
0x140051cb2  mov     r9d, 20019h; samDesired
0x140051cb8  xor     r8d, r8d; ulOptions
0x140051cbb  mov     rdx, [rsp+340h+lpSubKey]; lpSubKey
0x140051cc0  mov     rcx, rbx; hKey
0x140051cc3  call    cs:__imp_RegOpenKeyExW
0x140051cc9  test    eax, eax
0x140051ccb  jnz     loc_140051F77
0x140051cd1  mov     r14, [rsp+340h+hKey]
0x140051cd6  mov     qword ptr [rsp+340h+var_2E8], r14
0x140051cdb  mov     dword ptr [rsp+340h+var_2E8+8], r13d
0x140051ce0  mov     [rsp+340h+cchName], 104h
0x140051ce8  movups  xmm0, xmmword ptr cs:aConfig_1; "_Config_"
0x140051cef  movups  xmmword ptr [rbp+240h+SubStr], xmm0
0x140051cf3  movzx   eax, word ptr cs:aConfig_1+10h; ""
0x140051cfa  mov     [rbp+240h+var_260], ax
0x140051cfe  xorps   xmm0, xmm0
0x140051d01  movups  [rbp+240h+var_298], xmm0
0x140051d05  movups  [rbp+240h+var_288], xmm0
0x140051d09  movdqu  [rbp+240h+var_2A8], xmm0
0x140051d0e  mov     qword ptr [rbp+240h+var_298], r13
0x140051d12  xorps   xmm1, xmm1
0x140051d15  movdqu  [rbp+240h+var_298+8], xmm1
0x140051d1a  mov     dword ptr [rbp+240h+var_288+8], 0Ah
0x140051d21  mov     esi, r13d
0x140051d24  lea     rax, [rbp+240h+ftLastWriteTime]
0x140051d28  mov     [rsp+340h+lpftLastWriteTime], rax; lpftLastWriteTime
0x140051d2d  mov     [rsp+340h+lpcchClass], r13; lpcchClass
0x140051d32  mov     [rsp+340h+lpClass], r13; lpClass
0x140051d37  mov     [rsp+340h+phkResult], r13; lpReserved
0x140051d3c  lea     r9, [rsp+340h+cchName]; lpcchName
0x140051d41  lea     r8, [rbp+240h+Name]; lpName
0x140051d45  mov     edx, esi; dwIndex
0x140051d47  mov     rcx, [rsp+340h+hKey]; hKey
0x140051d4c  call    cs:__imp_RegEnumKeyExW
0x140051d52  test    eax, eax
0x140051d54  jnz     loc_140051F63
0x140051d5a  lea     rdx, [rbp+240h+SubStr]; SubStr
0x140051d5e  lea     rcx, [rbp+240h+Name]; Str
0x140051d62  call    cs:__imp_wcsstr
0x140051d68  test    rax, rax
0x140051d6b  jz      loc_140051EB5
0x140051d71  xorps   xmm0, xmm0
0x140051d74  xor     eax, eax
0x140051d76  movups  xmmword ptr [rbp+240h+hSemaphore], xmm0
0x140051d7a  mov     [rbp+240h+var_2B0], rax
0x140051d7e  lea     rax, ??_7CCacheUsageTracker@@6B@; const CCacheUsageTracker::`vftable'
0x140051d85  mov     [rbp+240h+hSemaphore], rax
0x140051d89  mov     [rbp+240h+hSemaphore+8], r13
0x140051d8d  mov     word ptr [rbp+240h+var_2B0], r13w
0x140051d92  lea     rdx, [rbp+240h+Name]
0x140051d96  lea     rcx, [rsp+340h+var_2C8]
0x140051d9b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140051da0  lea     rdx, [rsp+340h+var_2C8]
0x140051da5  lea     rcx, [rbp+240h+hSemaphore]
0x140051da9  call    ?SetName@CCacheUsageTracker@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CCacheUsageTracker::SetName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140051dae  mov     ebx, eax
0x140051db0  mov     rdx, [rsp+340h+var_2C8]
0x140051db5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140051db9  or      ecx, 0FFFFFFFFh
0x140051dbc  lock xadd [rdx+10h], ecx
0x140051dc1  sub     ecx, 1
0x140051dc4  jg      short loc_140051DD3
0x140051dc6  lfence
0x140051dc9  mov     rcx, [rdx]
0x140051dcc  mov     r8, [rcx]
0x140051dcf  call    qword ptr [r8+8]
0x140051dd3  test    ebx, ebx
0x140051dd5  jns     short loc_140051E45
0x140051dd7  lfence
0x140051dda  lea     r8, [rbp+240h+Name]; unsigned __int16 *
0x140051dde  mov     edx, ebx; int
0x140051de0  lea     rcx, aCouldNotCreate; "Could not create or find pkgdef Semapho"...
0x140051de7  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x140051dec  nop
0x140051ded  mov     rbx, [rbp+240h+hSemaphore+8]
0x140051df1  test    rbx, rbx
0x140051df4  jz      short loc_140051E43
0x140051df6  cmp     byte ptr [rbp+240h+var_2B0+1], r13b
0x140051dfa  jz      short loc_140051E39
0x140051dfc  xor     r8d, r8d; lpPreviousCount
0x140051dff  lea     edx, [r8+1]; lReleaseCount
0x140051e03  mov     rcx, rbx; hSemaphore
0x140051e06  call    cs:__imp_ReleaseSemaphore
0x140051e0c  test    eax, eax
0x140051e0e  jnz     short loc_140051E39
0x140051e10  call    cs:__imp_GetLastError
0x140051e16  movzx   edx, ax
0x140051e19  or      edx, 80070000h
0x140051e1f  test    eax, eax
0x140051e21  cmovle  edx, eax; int
0x140051e24  xor     r8d, r8d; unsigned __int16 *
0x140051e27  lea     rcx, aFailedToDecrem; "Failed to decrement PkgDef Semaphore"
0x140051e2e  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x140051e33  call    cs:__imp_GetLastError
0x140051e39  mov     rcx, rbx; hObject
0x140051e3c  call    cs:__imp_CloseHandle
0x140051e42  nop
0x140051e43  jmp     short loc_140051EB5
0x140051e45  cmp     byte ptr [rbp+240h+var_2B0], r13b
0x140051e49  setnz   r15b
0x140051e4d  mov     rbx, [rbp+240h+hSemaphore+8]
0x140051e51  test    rbx, rbx
0x140051e54  jz      short loc_140051EA3
0x140051e56  cmp     byte ptr [rbp+240h+var_2B0+1], r13b
0x140051e5a  jz      short loc_140051E99
0x140051e5c  xor     r8d, r8d; lpPreviousCount
0x140051e5f  lea     edx, [r8+1]; lReleaseCount
0x140051e63  mov     rcx, rbx; hSemaphore
0x140051e66  call    cs:__imp_ReleaseSemaphore
0x140051e6c  test    eax, eax
0x140051e6e  jnz     short loc_140051E99
0x140051e70  call    cs:__imp_GetLastError
0x140051e76  movzx   edx, ax
0x140051e79  or      edx, 80070000h
0x140051e7f  test    eax, eax
0x140051e81  cmovle  edx, eax; int
0x140051e84  xor     r8d, r8d; unsigned __int16 *
0x140051e87  lea     rcx, aFailedToDecrem; "Failed to decrement PkgDef Semaphore"
0x140051e8e  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x140051e93  call    cs:__imp_GetLastError
0x140051e99  mov     rcx, rbx; hObject
0x140051e9c  call    cs:__imp_CloseHandle
0x140051ea2  nop
0x140051ea3  test    r15b, r15b
0x140051ea6  jz      short loc_140051EB5
0x140051ea8  lea     rdx, [rbp+240h+Name]
0x140051eac  lea     rcx, [rbp+240h+var_2A8]
0x140051eb0  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x140051eb5  inc     esi
0x140051eb7  mov     [rsp+340h+cchName], 104h
0x140051ebf  jmp     loc_140051D24
0x140051ec4  mov     rsi, qword ptr [rbp+240h+var_2A8+8]
0x140051ec8  test    rsi, rsi
0x140051ecb  jz      loc_140051FDE
0x140051ed1  mov     rcx, [rsi+10h]
0x140051ed5  sub     rcx, 18h
0x140051ed9  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140051ede  lea     rbx, [rax+18h]
0x140051ee2  mov     [rsp+340h+var_2C8], rbx
0x140051ee7  mov     rax, [rsi+8]
0x140051eeb  mov     qword ptr [rbp+240h+var_2A8+8], rax
0x140051eef  test    rax, rax
0x140051ef2  jz      short loc_140051EF9
0x140051ef4  mov     [rax], r13
0x140051ef7  jmp     short loc_140051EFD
0x140051ef9  mov     qword ptr [rbp+240h+var_2A8], r13
0x140051efd  mov     rdx, rsi
0x140051f00  lea     rcx, [rbp+240h+var_2A8]
0x140051f04  call    ?FreeNode@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::FreeNode(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CNode *)
0x140051f09  nop
0x140051f0a  mov     r8, rbx; unsigned __int16 *
0x140051f0d  xor     edx, edx; int
0x140051f0f  lea     rcx, aRemovingAbando; "Removing abandoned configuration cache"
0x140051f16  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x140051f1b  lea     r8, [rsp+340h+var_2C8]
0x140051f20  mov     rdx, r12; hToken
0x140051f23  mov     rcx, [rsp+340h+hKey]; hkey
0x140051f28  call    ?DeleteKeyIfExists@@YAJPEAUHKEY__@@PEAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; DeleteKeyIfExists(HKEY__ *,void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140051f2d  test    eax, eax
0x140051f2f  jns     short loc_140051F46
0x140051f31  lfence
0x140051f34  xor     r8d, r8d; unsigned __int16 *
0x140051f37  mov     edx, eax; int
0x140051f39  lea     rcx, aCouldNotRemove; "Could not remove abandoned configuratio"...
0x140051f40  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x140051f45  nop
0x140051f46  lea     rdx, [rbx-18h]
0x140051f4a  or      eax, 0FFFFFFFFh
0x140051f4d  lock xadd [rdx+10h], eax
0x140051f52  sub     eax, 1
0x140051f55  jg      short loc_140051F63
0x140051f57  lfence
0x140051f5a  mov     rcx, [rdx]
0x140051f5d  mov     rax, [rcx]
0x140051f60  call    qword ptr [rax+8]
0x140051f63  cmp     qword ptr [rbp+240h+var_298], r13
0x140051f67  jnz     loc_140051EC4
0x140051f6d  lea     rcx, [rbp+240h+var_2A8]
0x140051f71  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x140051f76  nop
0x140051f77  test    dil, dil
0x140051f7a  jz      short loc_140051F83
0x140051f7c  call    cs:__imp_RevertToSelf
0x140051f82  nop
0x140051f83  mov     rdx, [rsp+340h+lpSubKey]
0x140051f88  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140051f8c  or      eax, 0FFFFFFFFh
0x140051f8f  lock xadd [rdx+10h], eax
0x140051f94  sub     eax, 1
0x140051f97  jg      short loc_140051FA6
0x140051f99  lfence
0x140051f9c  mov     rcx, [rdx]
0x140051f9f  mov     rax, [rcx]
0x140051fa2  call    qword ptr [rax+8]
0x140051fa5  nop
0x140051fa6  test    r14, r14
0x140051fa9  jz      short loc_140051FB4
0x140051fab  mov     rcx, r14; hKey
0x140051fae  call    cs:__imp_RegCloseKey
0x140051fb4  mov     rcx, [rbp+240h+var_40]
0x140051fbb  xor     rcx, rsp; StackCookie
0x140051fbe  call    __security_check_cookie
0x140051fc3  mov     rbx, [rsp+340h+arg_18]
0x140051fcb  add     rsp, 310h
0x140051fd2  pop     r15
0x140051fd4  pop     r14
0x140051fd6  pop     r13
0x140051fd8  pop     r12
0x140051fda  pop     rdi
0x140051fdb  pop     rsi
0x140051fdc  pop     rbp
0x140051fdd  retn
0x140051fde  mov     ecx, 80004005h; int
0x140051fe3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
