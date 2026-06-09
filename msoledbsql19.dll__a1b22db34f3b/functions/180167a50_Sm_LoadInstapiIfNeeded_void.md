# Sm::LoadInstapiIfNeeded(void)

- ea: `0x180167a50`
- end: `0x180167f27`
- name: `?LoadInstapiIfNeeded@Sm@@SAKXZ`
- size: `1239`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801684e0`

## callees

- `0x1800013e0`
- `0x180001f70`
- `0x1800030c0`
- `0x180003824`
- `0x180003d80`
- `0x18000451c`
- `0x18015a6f0`
- `0x18015a880`
- `0x180167a50`
- `0x180168720`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180167dfb`
- `KERNEL32!FreeLibrary` at `0x180167dfb`
- `KERNEL32!GetLastError` at `0x180167cef`
- `KERNEL32!GetLastError` at `0x180167d4d`
- `KERNEL32!GetLastError` at `0x180167da8`
- `KERNEL32!GetLastError` at `0x180167cef`
- `KERNEL32!GetLastError` at `0x180167d4d`
- `KERNEL32!GetLastError` at `0x180167da8`
- `KERNEL32!GetProcAddress` at `0x180167d3e`
- `KERNEL32!GetProcAddress` at `0x180167d99`
- `KERNEL32!GetProcAddress` at `0x180167d3e`
- `KERNEL32!GetProcAddress` at `0x180167d99`
- `KERNEL32!LoadLibraryA` at `0x180167ce1`
- `KERNEL32!LoadLibraryA` at `0x180167ce1`
- `ADVAPI32!RegQueryValueExA` at `0x180167c00`
- `ADVAPI32!RegQueryValueExA` at `0x180167c00`
- `ADVAPI32!RegOpenKeyExA` at `0x180167b84`
- `ADVAPI32!RegOpenKeyExA` at `0x180167b84`
- `ADVAPI32!RegCloseKey` at `0x180167c0d`
- `ADVAPI32!RegCloseKey` at `0x180167c0d`

## string_xrefs

- `0x180167c7a`: `instapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 Sm::LoadInstapiIfNeeded(void)
{
  DWORD LastError; // ebx
  _QWORD *v1; // rax
  signed __int64 v2; // rdi
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  struct __crt_locale_pointers *v7; // rax
  HMODULE LibraryA; // rax
  FARPROC ProcAddress; // rax
  FARPROC v10; // rax
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v15; // [rsp+50h] [rbp-B0h] BYREF
  char v16[16]; // [rsp+58h] [rbp-A8h] BYREF
  CHAR SubKey[56]; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[272]; // [rsp+A0h] [rbp-60h] BYREF
  CHAR LibFileName[288]; // [rsp+1B0h] [rbp+B0h] BYREF

  LastError = 0;
  v15 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266A60[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_180248060[0])(
      bidID,
      0,
      0,
      &v15,
      off_180266A60[0],
      0);
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&qword_1802539E0, 0, 0) )
    goto LABEL_41;
  v1 = (_QWORD *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 24);
  v2 = (signed __int64)v1;
  if ( !v1 )
  {
    LastError = 14;
LABEL_37:
    if ( (bidGblFlags & 2) != 0 && off_1802648E8[0] )
    {
      SniErrorIdFromStringId(0xC3D8u);
      bidTraceW(off_1802615A0[0], 317440, off_1802648E8[0], 3);
    }
    SNISetLastError(3, LastError, 50136);
LABEL_41:
    if ( (bidGblFlags & 0x20002) == 0x20002 )
    {
      if ( off_1802648F0[0] )
        bidTraceW(off_1802615A8[0], 320512, off_1802648F0[0], LastError);
    }
    _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v15);
    return LastError;
  }
  *v1 = 0;
  strcpy(SubKey, "Software\\Microsoft\\Microsoft SQL Server\\90");
  hKey = 0;
  v3 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
  LastError = v3;
  if ( v3 )
  {
    if ( (bidGblFlags & 2) != 0 && off_1802648B8[0] )
      bidTraceW(off_180261570[0], 205824, off_1802648B8[0], v3);
    goto LABEL_34;
  }
  cbData = 260;
  Type = 0;
  LastError = RegQueryValueExA(hKey, "SharedCode", 0, &Type, Data, &cbData);
  RegCloseKey(hKey);
  if ( LastError )
  {
    if ( (bidGblFlags & 2) != 0 && off_1802648C0[0] )
      bidTraceW(off_180261578[0], 224256, off_1802648C0[0], LastError);
    goto LABEL_34;
  }
  if ( Type != 1 )
  {
    LastError = 13;
    goto LABEL_34;
  }
  if ( cbData >= 0x105uLL )
    _report_rangecheckfailure(v5, v4, v6);
  Data[cbData] = 0;
  strcpy(v16, "instapi.dll");
  v7 = (struct __crt_locale_pointers *)ImplBidTouch();
  if ( (int)StringCchPrintf_lA(LibFileName, 0x111u, "%s%s", v7, Data, v16) < 0 )
  {
    LastError = 87;
    goto LABEL_34;
  }
  LibFileName[272] = 0;
  LibraryA = LoadLibraryA(LibFileName);
  *(_QWORD *)v2 = LibraryA;
  if ( !LibraryA )
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_1802648C8[0] )
      bidTraceW(off_180261580[0], 258048, off_1802648C8[0], LastError);
    goto LABEL_34;
  }
  ProcAddress = GetProcAddress(LibraryA, "GetSvcInstanceIDFromName");
  *(_QWORD *)(v2 + 8) = ProcAddress;
  if ( !ProcAddress )
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_1802648D0[0] )
      bidTraceW(off_180261588[0], 271360, off_1802648D0[0], LastError);
    goto LABEL_34;
  }
  v10 = GetProcAddress(*(HMODULE *)v2, "GetSQLInstanceRegStringByID");
  *(_QWORD *)(v2 + 16) = v10;
  if ( !v10 )
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_1802648D8[0] )
      bidTraceW(off_180261590[0], 285696, off_1802648D8[0], LastError);
LABEL_34:
    if ( *(_QWORD *)v2 )
      FreeLibrary(*(HMODULE *)v2);
    operator delete((void *)v2, 0x18u);
    if ( !LastError )
      goto LABEL_41;
    goto LABEL_37;
  }
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&qword_1802539E0, v2, 0) )
    goto LABEL_34;
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802648E0[0] )
    bidTraceW(off_180261598[0], 300032, off_1802648E0[0], 0);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v15);
  return 0;
}

```

## disassembly

```asm
0x180167a50  mov     [rsp-8+arg_0], rbx
0x180167a55  mov     [rsp-8+arg_8], rsi
0x180167a5a  mov     [rsp-8+arg_10], rdi
0x180167a5f  push    rbp
0x180167a60  lea     rbp, [rsp-1E0h]
0x180167a68  sub     rsp, 2E0h
0x180167a6f  mov     rax, cs:__security_cookie
0x180167a76  xor     rax, rsp
0x180167a79  mov     [rbp+1E0h+var_10], rax
0x180167a80  xor     esi, esi
0x180167a82  mov     ebx, esi
0x180167a84  mov     [rsp+2E0h+var_290], 0FFFFFFFFFFFFFFFFh
0x180167a8d  mov     eax, cs:_bidGblFlags
0x180167a93  and     eax, 20004h
0x180167a98  cmp     eax, 20004h
0x180167a9d  jnz     short loc_180167AE7
0x180167a9f  mov     rax, cs:off_180266A60; "<Sm::LoadInstapiIfNeeded|API|SNI> \n"
0x180167aa6  test    rax, rax
0x180167aa9  jz      short loc_180167AE7
0x180167aab  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180167ab3  jz      short loc_180167AE7
0x180167ab5  mov     r10, cs:off_180248060
0x180167abc  mov     [rsp+2E0h+lpcbData], rsi
0x180167ac1  mov     rax, cs:off_180266A60; "<Sm::LoadInstapiIfNeeded|API|SNI> \n"
0x180167ac8  mov     [rsp+2E0h+phkResult], rax
0x180167acd  lea     r9, [rsp+2E0h+var_290]
0x180167ad2  xor     r8d, r8d
0x180167ad5  xor     edx, edx
0x180167ad7  mov     rcx, cs:_bidID
0x180167ade  mov     rax, r10
0x180167ae1  call    cs:__guard_dispatch_icall_fptr
0x180167ae7  xor     eax, eax
0x180167ae9  lock cmpxchg cs:qword_1802539E0, rsi
0x180167af2  jnz     loc_180167E69
0x180167af8  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x180167aff  mov     rax, [rcx]
0x180167b02  mov     edx, 18h
0x180167b07  mov     rax, [rax+58h]
0x180167b0b  call    cs:__guard_dispatch_icall_fptr
0x180167b11  mov     rdi, rax
0x180167b14  test    rax, rax
0x180167b17  jnz     short loc_180167B23
0x180167b19  mov     ebx, 0Eh
0x180167b1e  jmp     loc_180167E12
0x180167b23  mov     [rax], rsi
0x180167b26  movups  xmm0, xmmword ptr cs:aSoftwareMicros_5; "Software\\Microsoft\\Microsoft SQL Serv"...
0x180167b2d  movups  xmmword ptr [rsp+2E0h+SubKey], xmm0
0x180167b32  movups  xmm1, xmmword ptr cs:aSoftwareMicros_5+10h; "ft\\Microsoft SQL Server\\90"
0x180167b39  movups  [rsp+2E0h+var_268], xmm1
0x180167b3e  movsd   xmm0, qword ptr cs:aSoftwareMicros_5+20h; " Server\\90"
0x180167b46  movsd   [rbp+1E0h+var_258], xmm0
0x180167b4b  movzx   eax, word ptr cs:aSoftwareMicros_5+28h; "90"
0x180167b52  mov     [rbp+1E0h+var_250], ax
0x180167b56  movzx   eax, byte ptr cs:aSoftwareMicros_5+2Ah; ""
0x180167b5d  mov     [rbp+1E0h+var_24E], al
0x180167b60  mov     [rsp+2E0h+hKey], rsi
0x180167b65  lea     rax, [rsp+2E0h+hKey]
0x180167b6a  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180167b6f  mov     r9d, 1; samDesired
0x180167b75  xor     r8d, r8d; ulOptions
0x180167b78  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x180167b7d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180167b84  call    cs:__imp_RegOpenKeyExA
0x180167b8a  mov     ebx, eax
0x180167b8c  test    eax, eax
0x180167b8e  jz      short loc_180167BCD
0x180167b90  test    byte ptr cs:_bidGblFlags, 2
0x180167b97  jz      loc_180167DF3
0x180167b9d  mov     rcx, cs:off_1802648B8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Canno"...
0x180167ba4  test    rcx, rcx
0x180167ba7  jz      loc_180167DF3
0x180167bad  mov     r9d, eax
0x180167bb0  mov     r8, cs:off_1802648B8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Canno"...
0x180167bb7  mov     edx, 32400h
0x180167bbc  mov     rcx, cs:off_180261570; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180167bc3  call    _bidTraceW
0x180167bc8  jmp     loc_180167DF3
0x180167bcd  mov     [rsp+2E0h+cbData], 104h
0x180167bd5  mov     [rsp+2E0h+Type], esi
0x180167bd9  lea     rax, [rsp+2E0h+cbData]
0x180167bde  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x180167be3  lea     rax, [rbp+1E0h+Data]
0x180167be7  mov     [rsp+2E0h+phkResult], rax; lpData
0x180167bec  lea     r9, [rsp+2E0h+Type]; lpType
0x180167bf1  xor     r8d, r8d; lpReserved
0x180167bf4  lea     rdx, aSharedcode; "SharedCode"
0x180167bfb  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180167c00  call    cs:__imp_RegQueryValueExA
0x180167c06  mov     ebx, eax
0x180167c08  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180167c0d  call    cs:__imp_RegCloseKey
0x180167c13  test    ebx, ebx
0x180167c15  jz      short loc_180167C54
0x180167c17  test    byte ptr cs:_bidGblFlags, 2
0x180167c1e  jz      loc_180167DF3
0x180167c24  mov     rax, cs:off_1802648C0; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Canno"...
0x180167c2b  test    rax, rax
0x180167c2e  jz      loc_180167DF3
0x180167c34  mov     r9d, ebx
0x180167c37  mov     r8, cs:off_1802648C0; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Canno"...
0x180167c3e  mov     edx, 36C00h
0x180167c43  mov     rcx, cs:off_180261578; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180167c4a  call    _bidTraceW
0x180167c4f  jmp     loc_180167DF3
0x180167c54  cmp     [rsp+2E0h+Type], 1
0x180167c59  jz      short loc_180167C65
0x180167c5b  mov     ebx, 0Dh
0x180167c60  jmp     loc_180167DF3
0x180167c65  mov     eax, [rsp+2E0h+cbData]
0x180167c69  cmp     rax, 105h
0x180167c6f  jnb     loc_180167F21
0x180167c75  mov     [rbp+rax+1E0h+Data], 0
0x180167c7a  movsd   xmm0, qword ptr cs:aInstapiDll; "instapi.dll"
0x180167c82  movsd   qword ptr [rsp+2E0h+var_288], xmm0
0x180167c88  mov     eax, dword ptr cs:aInstapiDll+8; "dll"
0x180167c8e  mov     dword ptr [rsp+2E0h+var_288+8], eax
0x180167c92  call    ImplBidTouch
0x180167c97  mov     r9, rax; struct __crt_locale_pointers *
0x180167c9a  lea     rax, [rsp+2E0h+var_288]
0x180167c9f  mov     [rsp+2E0h+lpcbData], rax
0x180167ca4  lea     rax, [rbp+1E0h+Data]
0x180167ca8  mov     [rsp+2E0h+phkResult], rax
0x180167cad  lea     r8, aSS_2; "%s%s"
0x180167cb4  mov     edx, 111h; unsigned __int64
0x180167cb9  lea     rcx, [rbp+1E0h+LibFileName]; Buffer
0x180167cc0  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x180167cc5  test    eax, eax
0x180167cc7  jns     short loc_180167CD3
0x180167cc9  mov     ebx, 57h ; 'W'
0x180167cce  jmp     loc_180167DF3
0x180167cd3  mov     [rbp+1E0h+var_20], 0
0x180167cda  lea     rcx, [rbp+1E0h+LibFileName]; lpLibFileName
0x180167ce1  call    cs:__imp_LoadLibraryA
0x180167ce7  mov     [rdi], rax
0x180167cea  test    rax, rax
0x180167ced  jnz     short loc_180167D34
0x180167cef  call    cs:__imp_GetLastError
0x180167cf5  mov     ebx, eax
0x180167cf7  test    byte ptr cs:_bidGblFlags, 2
0x180167cfe  jz      loc_180167DF3
0x180167d04  mov     rax, cs:off_1802648C8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x180167d0b  test    rax, rax
0x180167d0e  jz      loc_180167DF3
0x180167d14  mov     r9d, ebx
0x180167d17  mov     r8, cs:off_1802648C8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x180167d1e  mov     edx, 3F000h
0x180167d23  mov     rcx, cs:off_180261580; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180167d2a  call    _bidTraceW
0x180167d2f  jmp     loc_180167DF3
0x180167d34  lea     rdx, aGetsvcinstance; "GetSvcInstanceIDFromName"
0x180167d3b  mov     rcx, rax; hModule
0x180167d3e  call    cs:__imp_GetProcAddress
0x180167d44  mov     [rdi+8], rax
0x180167d48  test    rax, rax
0x180167d4b  jnz     short loc_180167D8F
0x180167d4d  call    cs:__imp_GetLastError
0x180167d53  mov     ebx, eax
0x180167d55  test    byte ptr cs:_bidGblFlags, 2
0x180167d5c  jz      loc_180167DF3
0x180167d62  mov     rax, cs:off_1802648D0; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x180167d69  test    rax, rax
0x180167d6c  jz      loc_180167DF3
0x180167d72  mov     r9d, ebx
0x180167d75  mov     r8, cs:off_1802648D0; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x180167d7c  mov     edx, 42400h
0x180167d81  mov     rcx, cs:off_180261588; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180167d88  call    _bidTraceW
0x180167d8d  jmp     short loc_180167DF3
0x180167d8f  lea     rdx, aGetsqlinstance; "GetSQLInstanceRegStringByID"
0x180167d96  mov     rcx, [rdi]; hModule
0x180167d99  call    cs:__imp_GetProcAddress
0x180167d9f  mov     [rdi+10h], rax
0x180167da3  test    rax, rax
0x180167da6  jnz     short loc_180167DE2
0x180167da8  call    cs:__imp_GetLastError
0x180167dae  mov     ebx, eax
0x180167db0  test    byte ptr cs:_bidGblFlags, 2
0x180167db7  jz      short loc_180167DF3
0x180167db9  mov     rax, cs:off_1802648D8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x180167dc0  test    rax, rax
0x180167dc3  jz      short loc_180167DF3
0x180167dc5  mov     r9d, ebx
0x180167dc8  mov     r8, cs:off_1802648D8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x180167dcf  mov     edx, 45C00h
0x180167dd4  mov     rcx, cs:off_180261590; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180167ddb  call    _bidTraceW
0x180167de0  jmp     short loc_180167DF3
0x180167de2  xor     eax, eax
0x180167de4  lock cmpxchg cs:qword_1802539E0, rdi
0x180167ded  jz      loc_180167ED8
0x180167df3  mov     rcx, [rdi]; hLibModule
0x180167df6  test    rcx, rcx
0x180167df9  jz      short loc_180167E01
0x180167dfb  call    cs:__imp_FreeLibrary
0x180167e01  mov     edx, 18h; unsigned __int64
0x180167e06  mov     rcx, rdi; void *
0x180167e09  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180167e0e  test    ebx, ebx
0x180167e10  jz      short loc_180167E69
0x180167e12  test    byte ptr cs:_bidGblFlags, 2
0x180167e19  jz      short loc_180167E57
0x180167e1b  mov     rax, cs:off_1802648E8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Provi"...
0x180167e22  test    rax, rax
0x180167e25  jz      short loc_180167E57
0x180167e27  mov     ecx, 0C3D8h; unsigned int
0x180167e2c  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x180167e31  mov     dword ptr [rsp+2E0h+lpcbData], ebx
0x180167e35  mov     dword ptr [rsp+2E0h+phkResult], eax
0x180167e39  mov     r9d, 3
0x180167e3f  mov     r8, cs:off_1802648E8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Provi"...
0x180167e46  mov     edx, 4D800h
0x180167e4b  mov     rcx, cs:off_1802615A0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180167e52  call    _bidTraceW
0x180167e57  mov     r8d, 0C3D8h
0x180167e5d  mov     edx, ebx
0x180167e5f  mov     ecx, 3
0x180167e64  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x180167e69  mov     eax, cs:_bidGblFlags
0x180167e6f  and     eax, 20002h
0x180167e74  cmp     eax, 20002h
0x180167e79  jnz     short loc_180167EA3
0x180167e7b  mov     rax, cs:off_1802648F0; "<Sm::LoadInstapiIfNeeded|RET|SNI> %d{WI"...
0x180167e82  test    rax, rax
0x180167e85  jz      short loc_180167EA3
0x180167e87  mov     r9d, ebx
0x180167e8a  mov     r8, cs:off_1802648F0; "<Sm::LoadInstapiIfNeeded|RET|SNI> %d{WI"...
0x180167e91  mov     edx, 4E400h
0x180167e96  mov     rcx, cs:off_1802615A8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180167e9d  call    _bidTraceW
0x180167ea2  nop
0x180167ea3  lea     rcx, [rsp+2E0h+var_290]; this
0x180167ea8  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x180167ead  nop
0x180167eae  mov     eax, ebx
0x180167eb0  mov     rcx, [rbp+1E0h+var_10]
0x180167eb7  xor     rcx, rsp; StackCookie
0x180167eba  call    __security_check_cookie
0x180167ebf  lea     r11, [rsp+2E0h+var_s0]
0x180167ec7  mov     rbx, [r11+10h]
0x180167ecb  mov     rsi, [r11+18h]
0x180167ecf  mov     rdi, [r11+20h]
0x180167ed3  mov     rsp, r11
0x180167ed6  pop     rbp
0x180167ed7  retn
0x180167ed8  mov     eax, cs:_bidGblFlags
0x180167ede  and     eax, 20002h
0x180167ee3  cmp     eax, 20002h
0x180167ee8  jnz     short loc_180167F12
0x180167eea  mov     rax, cs:off_1802648E0; "<Sm::LoadInstapiIfNeeded|RET|SNI> Loade"...
0x180167ef1  test    rax, rax
0x180167ef4  jz      short loc_180167F12
0x180167ef6  xor     r9d, r9d
0x180167ef9  mov     r8, cs:off_1802648E0; "<Sm::LoadInstapiIfNeeded|RET|SNI> Loade"...
0x180167f00  mov     edx, 49400h
0x180167f05  mov     rcx, cs:off_180261598; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180167f0c  call    _bidTraceW
0x180167f11  nop
0x180167f12  lea     rcx, [rsp+2E0h+var_290]; this
0x180167f17  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x180167f1c  nop
0x180167f1d  xor     eax, eax
0x180167f1f  jmp     short loc_180167EB0
0x180167f21  call    __report_rangecheckfailure
```
