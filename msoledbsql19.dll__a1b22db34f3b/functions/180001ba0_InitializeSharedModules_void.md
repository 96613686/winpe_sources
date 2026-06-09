# InitializeSharedModules(void)

- ea: `0x180001ba0`
- end: `0x180001f60`
- name: `?InitializeSharedModules@@YAHXZ`
- size: `960`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004920`

## callees

- `0x180001ba0`
- `0x1800030c0`
- `0x180003d80`
- `0x180135df4`
- `0x1801523e0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180001e9b`
- `KERNEL32!FreeLibrary` at `0x180001ec9`
- `KERNEL32!FreeLibrary` at `0x180001e9b`
- `KERNEL32!FreeLibrary` at `0x180001ec9`
- `KERNEL32!LoadLibraryExW` at `0x180001d75`
- `KERNEL32!LoadLibraryExW` at `0x180001dee`
- `KERNEL32!LoadLibraryExW` at `0x180001ee5`
- `KERNEL32!LoadLibraryExW` at `0x180001d75`
- `KERNEL32!LoadLibraryExW` at `0x180001dee`
- `KERNEL32!LoadLibraryExW` at `0x180001ee5`
- `KERNEL32!GetProcAddress` at `0x180001d91`
- `KERNEL32!GetProcAddress` at `0x180001dac`
- `KERNEL32!GetProcAddress` at `0x180001e0e`
- `KERNEL32!GetProcAddress` at `0x180001e29`
- `KERNEL32!GetProcAddress` at `0x180001e44`
- `KERNEL32!GetProcAddress` at `0x180001f01`
- `KERNEL32!GetProcAddress` at `0x180001f2e`
- `KERNEL32!GetProcAddress` at `0x180001d91`
- `KERNEL32!GetProcAddress` at `0x180001dac`
- `KERNEL32!GetProcAddress` at `0x180001e0e`
- `KERNEL32!GetProcAddress` at `0x180001e29`
- `KERNEL32!GetProcAddress` at `0x180001e44`
- `KERNEL32!GetProcAddress` at `0x180001f01`
- `KERNEL32!GetProcAddress` at `0x180001f2e`
- `KERNEL32!GetModuleHandleW` at `0x180001f15`
- `KERNEL32!GetModuleHandleW` at `0x180001f15`
- `ADVAPI32!DeregisterEventSource` at `0x180001c9b`
- `ADVAPI32!DeregisterEventSource` at `0x180001c9b`
- `ADVAPI32!RegisterEventSourceW` at `0x180001c5b`
- `ADVAPI32!RegisterEventSourceW` at `0x180001c5b`
- `ADVAPI32!ReportEventW` at `0x180001c92`
- `ADVAPI32!ReportEventW` at `0x180001c92`

## string_xrefs

- `0x180001d6e`: `crypt32.dll`
- `0x180001de7`: `advapi32.dll`
- `0x180001ede`: `advapi32.dll`
- `0x180001f0e`: `ntdll.dll`
- `0x180001f24`: `NtCompareTokens`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 InitializeSharedModules(void)
{
  unsigned int v0; // ebx
  HANDLE v1; // rax
  void *v2; // rdi
  HMODULE Library; // rax
  int (*ProcAddress)(void *, unsigned int, unsigned int); // rax
  HMODULE v6; // rax
  int (*v7)(int); // rax
  HMODULE v8; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v10; // [rsp+50h] [rbp-18h] BYREF

  v10 = -1;
  if ( (bidGblFlags & 4) != 0 && off_180266288[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_180248060[0])(
      bidID,
      0,
      0,
      &v10,
      off_180266288[0],
      0);
  if ( (g_uInitializationStatus & 0x110) == 0 )
  {
    LoadResourceDLL(g_szSqlncliRllFileName, g_hinstance, &g_hinstance_language);
    if ( !g_hinstance_language )
    {
      v1 = RegisterEventSourceW(0, L"MSOLEDBSQL19.1");
      v2 = v1;
      if ( v1 )
      {
        ReportEventW(v1, 1u, 0, 0xC0000001, 0, 0, 0, 0, 0);
        DeregisterEventSource(v2);
      }
LABEL_10:
      v0 = 0;
      goto LABEL_11;
    }
    if ( (bidGblFlags & 2) != 0 && off_180262CA0[0] )
      bidTraceW(off_1802601B0[0], 334857, off_180262CA0[0], 327);
    if ( bidID != -1 )
      ((void (__fastcall *)(__int64, __int64, __int64, _QWORD, HMODULE, _QWORD))off_180248030[0])(
        bidID,
        -1,
        1073741860,
        0,
        g_hinstance_language,
        0);
    Library = LoadLibraryExW(L"crypt32.dll", 0, 0x800u);
    g_hCrypt = Library;
    if ( Library )
    {
      g_pfnCryptProtectMemory = (int (*)(void *, unsigned int, unsigned int))GetProcAddress(
                                                                               Library,
                                                                               "CryptProtectMemory");
      ProcAddress = (int (*)(void *, unsigned int, unsigned int))GetProcAddress(g_hCrypt, "CryptUnprotectMemory");
      g_pfnCryptUnprotectMemory = ProcAddress;
      if ( g_pfnCryptProtectMemory && ProcAddress )
      {
        if ( g_hCrypt )
          goto LABEL_32;
      }
      else
      {
        g_pfnCryptProtectMemory = 0;
        g_pfnCryptUnprotectMemory = 0;
        FreeLibrary(g_hCrypt);
        g_hCrypt = 0;
      }
    }
    v6 = LoadLibraryExW(L"advapi32.dll", 0, 0x800u);
    g_hCrypt = v6;
    if ( v6 )
    {
      g_pfnRtlEncryptMemory = (int (*)(void *, unsigned int, unsigned int))GetProcAddress(v6, "SystemFunction040");
      g_pfnRtlDecryptMemory = (int (*)(void *, unsigned int, unsigned int))GetProcAddress(g_hCrypt, "SystemFunction041");
      v7 = (int (*)(int))GetProcAddress(g_hCrypt, "LsaNtStatusToWinError");
      g_pfnLsaNtStatusToWinError = v7;
      if ( g_pfnRtlEncryptMemory && g_pfnRtlDecryptMemory && v7 )
      {
        g_pfnCryptProtectMemory = (int (*)(void *, unsigned int, unsigned int))CryptProtectMemoryInternal;
        g_pfnCryptUnprotectMemory = (int (*)(void *, unsigned int, unsigned int))CryptUnprotectMemoryInternal;
      }
      else
      {
        g_pfnRtlEncryptMemory = 0;
        g_pfnRtlDecryptMemory = 0;
        g_pfnLsaNtStatusToWinError = 0;
        FreeLibrary(g_hCrypt);
        g_hCrypt = 0;
      }
    }
LABEL_32:
    v8 = LoadLibraryExW(L"advapi32.dll", 0, 0x800u);
    g_hEvt = v8;
    if ( v8 )
      g_pfnEventActivityIdControl = GetProcAddress(v8, "EventActivityIdControl");
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    if ( ModuleHandleW )
    {
      g_pfnNtCompareTokens = (int (*)(void *, void *, unsigned __int8 *))GetProcAddress(
                                                                           ModuleHandleW,
                                                                           "NtCompareTokens");
      if ( g_pfnNtCompareTokens )
      {
        v0 = DllMain_Sni(g_hinstance, 1u, 0);
        goto LABEL_11;
      }
    }
    goto LABEL_10;
  }
  v0 = 1;
LABEL_11:
  if ( v10 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180248068[0])(bidID, 0, 0, &v10);
  return v0;
}

```

## disassembly

```asm
0x180001ba0  mov     [rsp+arg_0], rbx
0x180001ba5  mov     [rsp+arg_8], rsi
0x180001baa  push    rdi
0x180001bab  sub     rsp, 60h
0x180001baf  mov     rax, cs:__security_cookie
0x180001bb6  xor     rax, rsp
0x180001bb9  mov     [rsp+68h+var_10], rax
0x180001bbe  mov     [rsp+68h+var_18], 0FFFFFFFFFFFFFFFFh
0x180001bc7  xor     esi, esi
0x180001bc9  test    byte ptr cs:_bidGblFlags, 4
0x180001bd0  jz      short loc_180001C17
0x180001bd2  mov     rax, cs:off_180266288; "<InitializeSharedModules|SNAC> "
0x180001bd9  test    rax, rax
0x180001bdc  jz      short loc_180001C17
0x180001bde  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180001be6  jz      short loc_180001C17
0x180001be8  mov     rax, cs:off_180248060
0x180001bef  mov     qword ptr [rsp+68h+wNumStrings], rsi
0x180001bf4  mov     rcx, cs:off_180266288; "<InitializeSharedModules|SNAC> "
0x180001bfb  mov     [rsp+68h+lpUserSid], rcx
0x180001c00  lea     r9, [rsp+68h+var_18]
0x180001c05  xor     r8d, r8d
0x180001c08  xor     edx, edx
0x180001c0a  mov     rcx, cs:_bidID
0x180001c11  call    cs:__guard_dispatch_icall_fptr
0x180001c17  mov     eax, cs:?g_uInitializationStatus@@3KC; ulong volatile g_uInitializationStatus
0x180001c1d  test    eax, 110h
0x180001c22  jz      short loc_180001C2B
0x180001c24  mov     ebx, 1
0x180001c29  jmp     short loc_180001CA3
0x180001c2b  lea     r8, ?g_hinstance_language@@3PEAUHINSTANCE__@@EA; HINSTANCE *
0x180001c32  mov     rdx, cs:?g_hinstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180001c39  mov     rcx, cs:?g_szSqlncliRllFileName@@3PEB_WEB; wchar_t *
0x180001c40  call    ?LoadResourceDLL@@YAJPEB_WPEAUHINSTANCE__@@PEAPEAU1@@Z; LoadResourceDLL(wchar_t const *,HINSTANCE__ *,HINSTANCE__ * *)
0x180001c45  cmp     cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * g_hinstance_language
0x180001c4c  jnz     loc_180001CF8
0x180001c52  lea     rdx, SourceName; "MSOLEDBSQL19.1"
0x180001c59  xor     ecx, ecx; lpUNCServerName
0x180001c5b  call    cs:__imp_RegisterEventSourceW
0x180001c61  mov     rdi, rax
0x180001c64  test    rax, rax
0x180001c67  jz      short loc_180001CA1
0x180001c69  xor     r8d, r8d; wCategory
0x180001c6c  mov     edx, 1; wType
0x180001c71  mov     [rsp+68h+lpRawData], rsi; lpRawData
0x180001c76  mov     [rsp+68h+lpStrings], rsi; lpStrings
0x180001c7b  mov     [rsp+68h+dwDataSize], esi; dwDataSize
0x180001c7f  mov     [rsp+68h+wNumStrings], si; wNumStrings
0x180001c84  mov     [rsp+68h+lpUserSid], rsi; lpUserSid
0x180001c89  mov     r9d, 0C0000001h; dwEventID
0x180001c8f  mov     rcx, rax; hEventLog
0x180001c92  call    cs:__imp_ReportEventW
0x180001c98  mov     rcx, rdi; hEventLog
0x180001c9b  call    cs:__imp_DeregisterEventSource
0x180001ca1  mov     ebx, esi
0x180001ca3  cmp     [rsp+68h+var_18], 0FFFFFFFFFFFFFFFFh
0x180001ca9  jz      short loc_180001CD9
0x180001cab  test    byte ptr cs:_bidGblFlags, 4
0x180001cb2  jz      short loc_180001CD9
0x180001cb4  mov     rcx, cs:_bidID
0x180001cbb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180001cbf  jz      short loc_180001CD9
0x180001cc1  lea     r9, [rsp+68h+var_18]
0x180001cc6  xor     r8d, r8d
0x180001cc9  xor     edx, edx
0x180001ccb  mov     rax, cs:off_180248068
0x180001cd2  call    cs:__guard_dispatch_icall_fptr
0x180001cd8  nop
0x180001cd9  mov     eax, ebx
0x180001cdb  mov     rcx, [rsp+68h+var_10]
0x180001ce0  xor     rcx, rsp; StackCookie
0x180001ce3  call    __security_check_cookie
0x180001ce8  mov     rbx, [rsp+68h+arg_0]
0x180001ced  mov     rsi, [rsp+68h+arg_8]
0x180001cf2  add     rsp, 60h
0x180001cf6  pop     rdi
0x180001cf7  retn
0x180001cf8  test    byte ptr cs:_bidGblFlags, 2
0x180001cff  jz      short loc_180001D2B
0x180001d01  mov     rcx, cs:off_1802601B0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\dl"...
0x180001d08  mov     rax, cs:off_180262CA0; "<Trace|MARK> line %d\n"
0x180001d0f  test    rax, rax
0x180001d12  jz      short loc_180001D2B
0x180001d14  mov     r9d, 147h
0x180001d1a  mov     r8, cs:off_180262CA0; "<Trace|MARK> line %d\n"
0x180001d21  mov     edx, 51C09h
0x180001d26  call    _bidTraceW
0x180001d2b  mov     rcx, cs:_bidID
0x180001d32  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180001d36  jz      short loc_180001D66
0x180001d38  mov     qword ptr [rsp+68h+wNumStrings], rsi
0x180001d3d  mov     r8, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinstance_language
0x180001d44  mov     [rsp+68h+lpUserSid], r8
0x180001d49  xor     r9d, r9d
0x180001d4c  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180001d53  mov     r8d, 40000024h
0x180001d59  mov     rax, cs:off_180248030
0x180001d60  call    cs:__guard_dispatch_icall_fptr
0x180001d66  xor     edx, edx; hFile
0x180001d68  mov     r8d, 800h; dwFlags
0x180001d6e  lea     rcx, LibFileName; "crypt32.dll"
0x180001d75  call    cs:__imp_LoadLibraryExW
0x180001d7b  mov     cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hCrypt
0x180001d82  test    rax, rax
0x180001d85  jz      short loc_180001DDF
0x180001d87  lea     rdx, aCryptprotectme; "CryptProtectMemory"
0x180001d8e  mov     rcx, rax; hModule
0x180001d91  call    cs:__imp_GetProcAddress
0x180001d97  mov     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, rax; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x180001d9e  lea     rdx, aCryptunprotect; "CryptUnprotectMemory"
0x180001da5  mov     rcx, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; hModule
0x180001dac  call    cs:__imp_GetProcAddress
0x180001db2  mov     cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA, rax; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x180001db9  cmp     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, rsi; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x180001dc0  jz      loc_180001E86
0x180001dc6  test    rax, rax
0x180001dc9  jz      loc_180001E86
0x180001dcf  mov     rax, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hCrypt
0x180001dd6  test    rax, rax
0x180001dd9  jnz     loc_180001ED6
0x180001ddf  xor     edx, edx; hFile
0x180001de1  mov     r8d, 800h; dwFlags
0x180001de7  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x180001dee  call    cs:__imp_LoadLibraryExW
0x180001df4  mov     cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hCrypt
0x180001dfb  test    rax, rax
0x180001dfe  jz      loc_180001ED6
0x180001e04  lea     rdx, aSystemfunction_0; "SystemFunction040"
0x180001e0b  mov     rcx, rax; hModule
0x180001e0e  call    cs:__imp_GetProcAddress
0x180001e14  mov     cs:?g_pfnRtlEncryptMemory@@3P6AJPEAXKK@ZEA, rax; long (*g_pfnRtlEncryptMemory)(void *,ulong,ulong)
0x180001e1b  lea     rdx, aSystemfunction; "SystemFunction041"
0x180001e22  mov     rcx, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; hModule
0x180001e29  call    cs:__imp_GetProcAddress
0x180001e2f  mov     cs:?g_pfnRtlDecryptMemory@@3P6AJPEAXKK@ZEA, rax; long (*g_pfnRtlDecryptMemory)(void *,ulong,ulong)
0x180001e36  lea     rdx, aLsantstatustow; "LsaNtStatusToWinError"
0x180001e3d  mov     rcx, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; hModule
0x180001e44  call    cs:__imp_GetProcAddress
0x180001e4a  mov     cs:?g_pfnLsaNtStatusToWinError@@3P6AJJ@ZEA, rax; long (*g_pfnLsaNtStatusToWinError)(long)
0x180001e51  cmp     cs:?g_pfnRtlEncryptMemory@@3P6AJPEAXKK@ZEA, rsi; long (*g_pfnRtlEncryptMemory)(void *,ulong,ulong)
0x180001e58  jz      short loc_180001EAD
0x180001e5a  cmp     cs:?g_pfnRtlDecryptMemory@@3P6AJPEAXKK@ZEA, rsi; long (*g_pfnRtlDecryptMemory)(void *,ulong,ulong)
0x180001e61  jz      short loc_180001EAD
0x180001e63  test    rax, rax
0x180001e66  jz      short loc_180001EAD
0x180001e68  lea     rax, ?CryptProtectMemoryInternal@@YAHPEAXKK@Z; CryptProtectMemoryInternal(void *,ulong,ulong)
0x180001e6f  mov     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, rax; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x180001e76  lea     rax, ?CryptUnprotectMemoryInternal@@YAHPEAXKK@Z; CryptUnprotectMemoryInternal(void *,ulong,ulong)
0x180001e7d  mov     cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA, rax; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x180001e84  jmp     short loc_180001ED6
0x180001e86  mov     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, rsi; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x180001e8d  mov     cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA, rsi; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x180001e94  mov     rcx, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; hLibModule
0x180001e9b  call    cs:__imp_FreeLibrary
0x180001ea1  mov     cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * g_hCrypt
0x180001ea8  jmp     loc_180001DDF
0x180001ead  mov     cs:?g_pfnRtlEncryptMemory@@3P6AJPEAXKK@ZEA, rsi; long (*g_pfnRtlEncryptMemory)(void *,ulong,ulong)
0x180001eb4  mov     cs:?g_pfnRtlDecryptMemory@@3P6AJPEAXKK@ZEA, rsi; long (*g_pfnRtlDecryptMemory)(void *,ulong,ulong)
0x180001ebb  mov     cs:?g_pfnLsaNtStatusToWinError@@3P6AJJ@ZEA, rsi; long (*g_pfnLsaNtStatusToWinError)(long)
0x180001ec2  mov     rcx, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; hLibModule
0x180001ec9  call    cs:__imp_FreeLibrary
0x180001ecf  mov     cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * g_hCrypt
0x180001ed6  xor     edx, edx; hFile
0x180001ed8  mov     r8d, 800h; dwFlags
0x180001ede  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x180001ee5  call    cs:__imp_LoadLibraryExW
0x180001eeb  mov     cs:?g_hEvt@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hEvt
0x180001ef2  test    rax, rax
0x180001ef5  jz      short loc_180001F0E
0x180001ef7  lea     rdx, aEventactivityi; "EventActivityIdControl"
0x180001efe  mov     rcx, rax; hModule
0x180001f01  call    cs:__imp_GetProcAddress
0x180001f07  mov     cs:?g_pfnEventActivityIdControl@@3P6A_JXZEA, rax; __int64 (*g_pfnEventActivityIdControl)(void)
0x180001f0e  lea     rcx, ModuleName; "ntdll.dll"
0x180001f15  call    cs:__imp_GetModuleHandleW
0x180001f1b  test    rax, rax
0x180001f1e  jz      loc_180001CA1
0x180001f24  lea     rdx, aNtcomparetoken; "NtCompareTokens"
0x180001f2b  mov     rcx, rax; hModule
0x180001f2e  call    cs:__imp_GetProcAddress
0x180001f34  mov     cs:?g_pfnNtCompareTokens@@3P6AJPEAX0PEAE@ZEA, rax; long (*g_pfnNtCompareTokens)(void *,void *,uchar *)
0x180001f3b  test    rax, rax
0x180001f3e  jz      loc_180001CA1
0x180001f44  xor     r8d, r8d; void *
0x180001f47  mov     edx, 1; unsigned int
0x180001f4c  mov     rcx, cs:?g_hinstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180001f53  call    ?DllMain_Sni@@YAHPEAUHINSTANCE__@@KPEAX@Z; DllMain_Sni(HINSTANCE__ *,ulong,void *)
0x180001f58  mov     ebx, eax
0x180001f5a  jmp     loc_180001CA3
```
