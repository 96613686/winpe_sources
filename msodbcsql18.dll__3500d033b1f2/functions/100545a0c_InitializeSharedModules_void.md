# InitializeSharedModules(void)

- ea: `0x100545a0c`
- end: `0x100545d6b`
- name: `?InitializeSharedModules@@YAHXZ`
- size: `863`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1004e7330`

## callees

- `0x100412c0c`
- `0x10043a5f4`
- `0x100544448`
- `0x100545a0c`
- `0x100546800`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x100545ba7`
- `KERNEL32!GetModuleHandleW` at `0x100545c2a`
- `KERNEL32!GetModuleHandleW` at `0x100545ce5`
- `KERNEL32!GetModuleHandleW` at `0x100545d15`
- `KERNEL32!GetModuleHandleW` at `0x100545ba7`
- `KERNEL32!GetModuleHandleW` at `0x100545c2a`
- `KERNEL32!GetModuleHandleW` at `0x100545ce5`
- `KERNEL32!GetModuleHandleW` at `0x100545d15`
- `KERNEL32!GetProcAddress` at `0x100545bc3`
- `KERNEL32!GetProcAddress` at `0x100545bde`
- `KERNEL32!GetProcAddress` at `0x100545c4a`
- `KERNEL32!GetProcAddress` at `0x100545c65`
- `KERNEL32!GetProcAddress` at `0x100545c80`
- `KERNEL32!GetProcAddress` at `0x100545d01`
- `KERNEL32!GetProcAddress` at `0x100545d2e`
- `KERNEL32!GetProcAddress` at `0x100545bc3`
- `KERNEL32!GetProcAddress` at `0x100545bde`
- `KERNEL32!GetProcAddress` at `0x100545c4a`
- `KERNEL32!GetProcAddress` at `0x100545c65`
- `KERNEL32!GetProcAddress` at `0x100545c80`
- `KERNEL32!GetProcAddress` at `0x100545d01`
- `KERNEL32!GetProcAddress` at `0x100545d2e`
- `ADVAPI32!ReportEventW` at `0x100545afb`
- `ADVAPI32!ReportEventW` at `0x100545afb`
- `ADVAPI32!RegisterEventSourceW` at `0x100545ac5`
- `ADVAPI32!RegisterEventSourceW` at `0x100545ac5`
- `ADVAPI32!DeregisterEventSource` at `0x100545b04`
- `ADVAPI32!DeregisterEventSource` at `0x100545b04`

## string_xrefs

- `0x100545d0e`: `ntdll.dll`
- `0x100545ba0`: `crypt32.dll`
- `0x100545c23`: `advapi32.dll`
- `0x100545cde`: `advapi32.dll`
- `0x100545d24`: `NtCompareTokens`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 InitializeSharedModules(void)
{
  unsigned int v0; // ebx
  HANDLE v1; // rax
  void *v2; // rdi
  HMODULE ModuleHandleW; // rax
  int (*v5)(void *, unsigned int, unsigned int); // rax
  HMODULE v6; // rax
  HMODULE v7; // rax
  int (*ProcAddress)(int); // rax
  HMODULE v9; // rax
  HMODULE v10; // rax
  __int64 v11; // [rsp+70h] [rbp+8h] BYREF

  v11 = -1;
  if ( (bidGblFlags & 4) != 0 && off_1005E8338 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_1005D39F0)(
      bidID,
      0,
      0,
      &v11,
      off_1005E8338,
      0);
  if ( (g_uInitializationStatus & 0x100) != 0 )
  {
    v0 = 1;
  }
  else
  {
    LoadResourceDLL(lpLibFileName, (HINSTANCE)g_hinstance, &g_hinstance_language);
    if ( g_hinstance_language )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E76B8[0] )
        bidTraceW(0, 318473, off_1005E76B8[0], 311);
      bidCtlProc(-1, 1073741860, 0, (_DWORD)g_hinstance_language, 0);
      ModuleHandleW = GetModuleHandleW(L"crypt32.dll");
      g_hCrypt = ModuleHandleW;
      if ( !ModuleHandleW
        || ((g_pfnCryptProtectMemory = (int (*)(void *, unsigned int, unsigned int))GetProcAddress(
                                                                                      ModuleHandleW,
                                                                                      "CryptProtectMemory"),
             v5 = (int (*)(void *, unsigned int, unsigned int))GetProcAddress(g_hCrypt, "CryptUnprotectMemory"),
             g_pfnCryptUnprotectMemory = v5,
             !g_pfnCryptProtectMemory)
         || !v5
          ? (g_pfnCryptProtectMemory = 0, g_pfnCryptUnprotectMemory = 0, v6 = 0, g_hCrypt = 0)
          : (v6 = g_hCrypt),
            !v6) )
      {
        v7 = GetModuleHandleW(L"advapi32.dll");
        g_hCrypt = v7;
        if ( v7 )
        {
          g_pfnRtlEncryptMemory = (int (*)(void *, unsigned int, unsigned int))GetProcAddress(v7, "SystemFunction040");
          g_pfnRtlDecryptMemory = (int (*)(void *, unsigned int, unsigned int))GetProcAddress(
                                                                                 g_hCrypt,
                                                                                 "SystemFunction041");
          ProcAddress = (int (*)(int))GetProcAddress(g_hCrypt, "LsaNtStatusToWinError");
          g_pfnLsaNtStatusToWinError = ProcAddress;
          if ( g_pfnRtlEncryptMemory && g_pfnRtlDecryptMemory && ProcAddress )
          {
            g_pfnCryptProtectMemory = (int (*)(void *, unsigned int, unsigned int))CryptProtectMemoryInternal;
            g_pfnCryptUnprotectMemory = (int (*)(void *, unsigned int, unsigned int))CryptUnprotectMemoryInternal;
          }
          else
          {
            g_pfnRtlEncryptMemory = 0;
            g_pfnRtlDecryptMemory = 0;
            g_pfnLsaNtStatusToWinError = 0;
            g_hCrypt = 0;
          }
        }
      }
      v9 = GetModuleHandleW(L"advapi32.dll");
      g_hEvt = v9;
      if ( v9 )
        g_pfnEventActivityIdControl = GetProcAddress(v9, "EventActivityIdControl");
      v10 = GetModuleHandleW(L"ntdll.dll");
      if ( v10 )
      {
        g_pfnNtCompareTokens = (int (*)(void *, void *, unsigned __int8 *))GetProcAddress(v10, "NtCompareTokens");
        if ( g_pfnNtCompareTokens )
        {
          SNIErrorInitResourceDll(g_hinstance_language);
          v0 = DllMain_Sni((HINSTANCE)g_hinstance, 1u, 0);
          goto LABEL_12;
        }
      }
    }
    else if ( !g_fIsEmbeddedSNAC )
    {
      v1 = RegisterEventSourceW(0, L"msodbcsql18");
      v2 = v1;
      if ( v1 )
      {
        ReportEventW(v1, 1u, 0, 0xC0000001, 0, 0, 0, 0, 0);
        DeregisterEventSource(v2);
      }
    }
    v0 = 0;
  }
LABEL_12:
  if ( v11 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1005D39F8[0])(bidID, 0, 0, &v11);
  return v0;
}

```

## disassembly

```asm
0x100545a0c  mov     r11, rsp
0x100545a0f  push    rdi
0x100545a10  sub     rsp, 60h
0x100545a14  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x100545a1c  mov     [r11+10h], rbx
0x100545a20  mov     [r11+18h], rsi
0x100545a24  or      qword ptr [r11+8], 0FFFFFFFFFFFFFFFFh
0x100545a29  xor     esi, esi
0x100545a2b  test    byte ptr cs:_bidGblFlags, 4
0x100545a32  jz      short loc_100545A76
0x100545a34  mov     rax, cs:off_1005E8338; "<InitializeSharedModules|SNAC> "
0x100545a3b  test    rax, rax
0x100545a3e  jz      short loc_100545A76
0x100545a40  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100545a48  jz      short loc_100545A76
0x100545a4a  mov     rax, cs:off_1005D39F0
0x100545a51  mov     [r11-40h], rsi
0x100545a55  mov     rcx, cs:off_1005E8338; "<InitializeSharedModules|SNAC> "
0x100545a5c  mov     [r11-48h], rcx
0x100545a60  lea     r9, [r11+8]
0x100545a64  xor     r8d, r8d
0x100545a67  xor     edx, edx
0x100545a69  mov     rcx, cs:_bidID
0x100545a70  call    cs:__guard_dispatch_icall_fptr
0x100545a76  mov     eax, cs:?g_uInitializationStatus@@3KC; ulong volatile g_uInitializationStatus
0x100545a7c  bt      eax, 8
0x100545a80  jnb     short loc_100545A8C
0x100545a82  mov     ebx, 1
0x100545a87  jmp     loc_100545B0C
0x100545a8c  lea     r8, ?g_hinstance_language@@3PEAUHINSTANCE__@@EA; HINSTANCE *
0x100545a93  mov     rdx, cs:?g_hinstance@@3PEAUHINSTANCE__@@EA; hModule
0x100545a9a  mov     rcx, cs:lpLibFileName; lpLibFileName
0x100545aa1  call    ?LoadResourceDLL@@YAJPEBGPEAUHINSTANCE__@@PEAPEAU1@@Z; LoadResourceDLL(ushort const *,HINSTANCE__ *,HINSTANCE__ * *)
0x100545aa6  cmp     cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * g_hinstance_language
0x100545aad  jnz     loc_100545B55
0x100545ab3  cmp     cs:?g_fIsEmbeddedSNAC@@3_NA, sil; bool g_fIsEmbeddedSNAC
0x100545aba  jnz     short loc_100545B0A
0x100545abc  lea     rdx, SourceName; "msodbcsql18"
0x100545ac3  xor     ecx, ecx; lpUNCServerName
0x100545ac5  call    cs:__imp_RegisterEventSourceW
0x100545acb  mov     rdi, rax
0x100545ace  test    rax, rax
0x100545ad1  jz      short loc_100545B0A
0x100545ad3  xor     r8d, r8d; wCategory
0x100545ad6  lea     edx, [r8+1]; wType
0x100545ada  mov     [rsp+68h+lpRawData], rsi; lpRawData
0x100545adf  mov     [rsp+68h+lpStrings], rsi; lpStrings
0x100545ae4  mov     [rsp+68h+dwDataSize], esi; dwDataSize
0x100545ae8  mov     [rsp+68h+wNumStrings], si; wNumStrings
0x100545aed  mov     [rsp+68h+lpUserSid], rsi; lpUserSid
0x100545af2  mov     r9d, 0C0000001h; dwEventID
0x100545af8  mov     rcx, rax; hEventLog
0x100545afb  call    cs:__imp_ReportEventW
0x100545b01  mov     rcx, rdi; hEventLog
0x100545b04  call    cs:__imp_DeregisterEventSource
0x100545b0a  mov     ebx, esi
0x100545b0c  cmp     [rsp+68h+arg_0], 0FFFFFFFFFFFFFFFFh
0x100545b12  jz      short loc_100545B41
0x100545b14  test    byte ptr cs:_bidGblFlags, 4
0x100545b1b  jz      short loc_100545B41
0x100545b1d  mov     rcx, cs:_bidID
0x100545b24  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x100545b28  jz      short loc_100545B41
0x100545b2a  lea     r9, [rsp+68h+arg_0]
0x100545b2f  xor     r8d, r8d
0x100545b32  xor     edx, edx
0x100545b34  mov     rax, cs:off_1005D39F8
0x100545b3b  call    cs:__guard_dispatch_icall_fptr
0x100545b41  mov     eax, ebx
0x100545b43  lea     r11, [rsp+68h+var_8]
0x100545b48  mov     rbx, [r11+18h]
0x100545b4c  mov     rsi, [r11+20h]
0x100545b50  mov     rsp, r11
0x100545b53  pop     rdi
0x100545b54  retn
0x100545b55  test    byte ptr cs:_bidGblFlags, 2
0x100545b5c  jz      short loc_100545B83
0x100545b5e  mov     rax, cs:off_1005E76B8; "<Trace|MARK> line %d\n"
0x100545b65  test    rax, rax
0x100545b68  jz      short loc_100545B83
0x100545b6a  mov     r9d, 137h
0x100545b70  mov     r8, cs:off_1005E76B8; "<Trace|MARK> line %d\n"
0x100545b77  mov     edx, 4DC09h
0x100545b7c  xor     ecx, ecx
0x100545b7e  call    _bidTraceW
0x100545b83  mov     [rsp+68h+lpUserSid], rsi
0x100545b88  mov     r9, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinstance_language
0x100545b8f  xor     r8d, r8d
0x100545b92  mov     edx, 40000024h
0x100545b97  or      rcx, 0FFFFFFFFFFFFFFFFh
0x100545b9b  call    _bidCtlProc
0x100545ba0  lea     rcx, aCrypt32Dll_0; "crypt32.dll"
0x100545ba7  call    cs:__imp_GetModuleHandleW
0x100545bad  mov     cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hCrypt
0x100545bb4  test    rax, rax
0x100545bb7  jz      short loc_100545C23
0x100545bb9  lea     rdx, aCryptprotectme; "CryptProtectMemory"
0x100545bc0  mov     rcx, rax; hModule
0x100545bc3  call    cs:__imp_GetProcAddress
0x100545bc9  mov     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, rax; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x100545bd0  lea     rdx, aCryptunprotect; "CryptUnprotectMemory"
0x100545bd7  mov     rcx, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; hModule
0x100545bde  call    cs:__imp_GetProcAddress
0x100545be4  mov     cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA, rax; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x100545beb  cmp     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, rsi; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x100545bf2  jz      short loc_100545C02
0x100545bf4  test    rax, rax
0x100545bf7  jz      short loc_100545C02
0x100545bf9  mov     rax, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hCrypt
0x100545c00  jmp     short loc_100545C1A
0x100545c02  mov     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, rsi; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x100545c09  mov     cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA, rsi; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x100545c10  mov     rax, rsi
0x100545c13  mov     cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hCrypt
0x100545c1a  test    rax, rax
0x100545c1d  jnz     loc_100545CDE
0x100545c23  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x100545c2a  call    cs:__imp_GetModuleHandleW
0x100545c30  mov     cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hCrypt
0x100545c37  test    rax, rax
0x100545c3a  jz      loc_100545CDE
0x100545c40  lea     rdx, aSystemfunction_0; "SystemFunction040"
0x100545c47  mov     rcx, rax; hModule
0x100545c4a  call    cs:__imp_GetProcAddress
0x100545c50  mov     cs:?g_pfnRtlEncryptMemory@@3P6AJPEAXKK@ZEA, rax; long (*g_pfnRtlEncryptMemory)(void *,ulong,ulong)
0x100545c57  lea     rdx, aSystemfunction; "SystemFunction041"
0x100545c5e  mov     rcx, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; hModule
0x100545c65  call    cs:__imp_GetProcAddress
0x100545c6b  mov     cs:?g_pfnRtlDecryptMemory@@3P6AJPEAXKK@ZEA, rax; long (*g_pfnRtlDecryptMemory)(void *,ulong,ulong)
0x100545c72  lea     rdx, aLsantstatustow; "LsaNtStatusToWinError"
0x100545c79  mov     rcx, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; hModule
0x100545c80  call    cs:__imp_GetProcAddress
0x100545c86  mov     cs:?g_pfnLsaNtStatusToWinError@@3P6AJJ@ZEA, rax; long (*g_pfnLsaNtStatusToWinError)(long)
0x100545c8d  cmp     cs:?g_pfnRtlEncryptMemory@@3P6AJPEAXKK@ZEA, rsi; long (*g_pfnRtlEncryptMemory)(void *,ulong,ulong)
0x100545c94  jz      short loc_100545CC2
0x100545c96  cmp     cs:?g_pfnRtlDecryptMemory@@3P6AJPEAXKK@ZEA, rsi; long (*g_pfnRtlDecryptMemory)(void *,ulong,ulong)
0x100545c9d  jz      short loc_100545CC2
0x100545c9f  test    rax, rax
0x100545ca2  jz      short loc_100545CC2
0x100545ca4  lea     rax, ?CryptProtectMemoryInternal@@YAHPEAXKK@Z; CryptProtectMemoryInternal(void *,ulong,ulong)
0x100545cab  mov     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, rax; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x100545cb2  lea     rax, ?CryptUnprotectMemoryInternal@@YAHPEAXKK@Z; CryptUnprotectMemoryInternal(void *,ulong,ulong)
0x100545cb9  mov     cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA, rax; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x100545cc0  jmp     short loc_100545CDE
0x100545cc2  mov     cs:?g_pfnRtlEncryptMemory@@3P6AJPEAXKK@ZEA, rsi; long (*g_pfnRtlEncryptMemory)(void *,ulong,ulong)
0x100545cc9  mov     cs:?g_pfnRtlDecryptMemory@@3P6AJPEAXKK@ZEA, rsi; long (*g_pfnRtlDecryptMemory)(void *,ulong,ulong)
0x100545cd0  mov     cs:?g_pfnLsaNtStatusToWinError@@3P6AJJ@ZEA, rsi; long (*g_pfnLsaNtStatusToWinError)(long)
0x100545cd7  mov     cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * g_hCrypt
0x100545cde  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x100545ce5  call    cs:__imp_GetModuleHandleW
0x100545ceb  mov     cs:?g_hEvt@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hEvt
0x100545cf2  test    rax, rax
0x100545cf5  jz      short loc_100545D0E
0x100545cf7  lea     rdx, aEventactivityi; "EventActivityIdControl"
0x100545cfe  mov     rcx, rax; hModule
0x100545d01  call    cs:__imp_GetProcAddress
0x100545d07  mov     cs:?g_pfnEventActivityIdControl@@3P6A_JXZEA, rax; __int64 (*g_pfnEventActivityIdControl)(void)
0x100545d0e  lea     rcx, ModuleName; "ntdll.dll"
0x100545d15  call    cs:__imp_GetModuleHandleW
0x100545d1b  test    rax, rax
0x100545d1e  jz      loc_100545B0A
0x100545d24  lea     rdx, aNtcomparetoken; "NtCompareTokens"
0x100545d2b  mov     rcx, rax; hModule
0x100545d2e  call    cs:__imp_GetProcAddress
0x100545d34  mov     cs:?g_pfnNtCompareTokens@@3P6AJPEAX0PEAE@ZEA, rax; long (*g_pfnNtCompareTokens)(void *,void *,uchar *)
0x100545d3b  test    rax, rax
0x100545d3e  jz      loc_100545B0A
0x100545d44  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x100545d4b  call    ?SNIErrorInitResourceDll@@YAXPEAUHINSTANCE__@@@Z; SNIErrorInitResourceDll(HINSTANCE__ *)
0x100545d50  xor     r8d, r8d; void *
0x100545d53  lea     edx, [r8+1]; unsigned int
0x100545d57  mov     rcx, cs:?g_hinstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x100545d5e  call    ?DllMain_Sni@@YAHPEAUHINSTANCE__@@KPEAX@Z; DllMain_Sni(HINSTANCE__ *,ulong,void *)
0x100545d63  mov     ebx, eax
0x100545d65  jmp     loc_100545B0C
```
