# IkeGwSvcDelayLoad

- ea: `0x180095274`
- end: `0x1800955be`
- name: `IkeGwSvcDelayLoad`
- size: `842`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180094780`
- `0x180095208`
- `0x1800955c4`
- `0x180095620`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800061ec`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x180074314`
- `0x180095060`
- `0x180095274`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180095497`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180095497`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800953f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180095411`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180095431`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180095451`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800953f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180095411`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180095431`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180095451`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800953c3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800953c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800953d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800953d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095463`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180095574`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180095574`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800952da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800952da`

## string_xrefs

- `0x1800953e7`: `CreateTunnel`
- `0x1800953db`: `LoadLibraryExW`
- `0x18009542a`: `NewRasIncomingCall`

## pseudocode

```c
__int64 IkeGwSvcDelayLoad()
{
  unsigned int v0; // r14d
  signed __int32 v1; // eax
  signed __int32 v2; // ett
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  int TlsMmLuid; // eax
  __int64 v14; // rcx
  __int64 v15; // rax
  int v16; // r8d
  int v17; // r9d
  HMODULE Library; // rax
  DWORD LastError; // eax
  __int64 v20; // rcx
  const char *v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rax
  __int64 v27; // rdi
  __int64 v28; // rbx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // rax
  int v36; // r8d
  __int64 result; // rax
  _QWORD v38[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v39[32]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v40; // [rsp+60h] [rbp-A0h]
  __int64 v41; // [rsp+68h] [rbp-98h]
  _BYTE v42[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v43[16]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR LibFileName[264]; // [rsp+90h] [rbp-70h] BYREF

  v0 = 0;
  TraceLogHelper("IkeGwSvcDelayLoad", 1);
  _m_prefetchw(&g_IsGwSvcIkeModuleLoaded);
  v1 = g_IsGwSvcIkeModuleLoaded;
  do
  {
    v2 = v1;
    v1 = _InterlockedCompareExchange(&g_IsGwSvcIkeModuleLoaded, v1, v1);
  }
  while ( v2 != v1 );
  if ( v1 == 1 )
    goto LABEL_28;
  EnterCriticalSection(&g_ikeGwSvcLock);
  if ( !g_gwSvcIkeModule )
  {
    IkeGetGwSvcIkeDllName((BYTE *)LibFileName);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      TlsPeerAddr = IkeGetTlsPeerAddr(v4);
      TlsMmLuid = IkeGetTlsMmLuid(v10, v9, v11, v12);
      WPP_SF_iSS(
        v7,
        11,
        (unsigned int)WPP_689a915fb9f93bdb61c12c2fd59547e5_Traceguids,
        TlsMmLuid,
        TlsPeerAddr,
        (__int64)LibFileName);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v38[0] = IkeGetTlsMmLuid(v4, v3, v5, v6);
      v40 = v38;
      v41 = 8;
      v15 = IkeGetTlsPeerAddr(v14);
      tlgCreate1Sz_wchar_t(v42, v15);
      tlgCreate1Sz_wchar_t(v43, LibFileName);
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&unk_180158B18,
        v16,
        v17,
        5,
        (__int64)v39);
    }
    Library = LoadLibraryExW(LibFileName, 0, 0x800u);
    g_gwSvcIkeModule = Library;
    if ( Library && (g_fpGwSvcCreateTunnel = (__int64)GetProcAddress(Library, "CreateTunnel")) != 0 )
    {
      g_fpGwSvcCloseTunnel = (__int64)GetProcAddress(g_gwSvcIkeModule, "CloseTunnel");
      if ( g_fpGwSvcCloseTunnel )
      {
        g_fpGwSvcNewIncomingCall = (__int64)GetProcAddress(g_gwSvcIkeModule, "NewRasIncomingCall");
        if ( g_fpGwSvcNewIncomingCall )
        {
          g_fpGwSvcNewDemandDialCall = (__int64)GetProcAddress(g_gwSvcIkeModule, "NewRasDemandDialCall");
          if ( g_fpGwSvcNewDemandDialCall )
          {
            _InterlockedExchange(&g_IsGwSvcIkeModuleLoaded, 1);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              v27 = *((_QWORD *)WPP_GLOBAL_Control + 2);
              v28 = IkeGetTlsPeerAddr(v23);
              v33 = IkeGetTlsMmLuid(v30, v29, v31, v32);
              WPP_SF_iSS(
                v27,
                12,
                (unsigned int)WPP_689a915fb9f93bdb61c12c2fd59547e5_Traceguids,
                v33,
                v28,
                (__int64)LibFileName);
            }
            if ( (unsigned int)dword_180173278 > 4 )
            {
              v38[0] = IkeGetTlsMmLuid(v23, v22, v24, v25);
              v40 = v38;
              v41 = 8;
              v35 = IkeGetTlsPeerAddr(v34);
              tlgCreate1Sz_wchar_t(v42, v35);
              tlgCreate1Sz_wchar_t(v43, LibFileName);
              tlgWriteTransfer_EtwEventWriteTransfer(
                (unsigned int)&dword_180173278,
                (unsigned int)&unk_180158AC8,
                v36,
                (unsigned int)v39,
                5,
                (__int64)v39);
            }
            goto LABEL_27;
          }
        }
      }
      LastError = GetLastError();
      v21 = "GetProcAddress";
    }
    else
    {
      LastError = GetLastError();
      v21 = "LoadLibraryExW";
    }
    v26 = WfpReportSysErrorAsWinError(v20, v21, LastError, 1);
    v0 = v26;
    if ( v26 && g_gwSvcIkeModule )
    {
      FreeLibrary(g_gwSvcIkeModule);
      g_gwSvcIkeModule = 0;
    }
  }
LABEL_27:
  LeaveCriticalSection(&g_ikeGwSvcLock);
LABEL_28:
  TraceLogHelper("IkeGwSvcDelayLoad", 0);
  result = (unsigned __int16)v0;
  if ( (v0 & 0x1FFF0000) != 0x70000 )
    return v0;
  return result;
}

```

## disassembly

```asm
0x180095274  push    rbp
0x180095276  push    rbx
0x180095277  push    rsi
0x180095278  push    rdi
0x180095279  push    r12
0x18009527b  push    r14
0x18009527d  lea     rbp, [rsp-1B8h]
0x180095285  sub     rsp, 2B8h
0x18009528c  mov     rax, cs:__security_cookie
0x180095293  xor     rax, rsp
0x180095296  mov     [rbp+1E0h+var_40], rax
0x18009529d  xor     r14d, r14d
0x1800952a0  lea     rcx, aIkegwsvcdelayl; "IkeGwSvcDelayLoad"
0x1800952a7  lea     esi, [r14+1]
0x1800952ab  mov     edx, esi
0x1800952ad  call    TraceLogHelper
0x1800952b2  prefetchw byte ptr cs:g_IsGwSvcIkeModuleLoaded
0x1800952b9  mov     eax, cs:g_IsGwSvcIkeModuleLoaded
0x1800952bf  mov     ecx, eax
0x1800952c1  lock cmpxchg cs:g_IsGwSvcIkeModuleLoaded, ecx
0x1800952c9  jnz     short loc_1800952BF
0x1800952cb  cmp     eax, esi
0x1800952cd  jz      loc_18009557A
0x1800952d3  lea     rcx, g_ikeGwSvcLock; lpCriticalSection
0x1800952da  call    cs:__imp_EnterCriticalSection
0x1800952e0  cmp     cs:g_gwSvcIkeModule, r14
0x1800952e7  jnz     loc_18009556D
0x1800952ed  lea     rcx, [rbp+1E0h+LibFileName]; pszDest
0x1800952f1  call    IkeGetGwSvcIkeDllName
0x1800952f6  mov     rdi, cs:WPP_GLOBAL_Control
0x1800952fd  lea     r12, WPP_GLOBAL_Control
0x180095304  cmp     rdi, r12
0x180095307  jz      short loc_18009534B
0x180095309  cmp     byte ptr [rdi+19h], 4
0x18009530d  jb      short loc_18009534B
0x18009530f  test    byte ptr [rdi+1Ch], 10h
0x180095313  jz      short loc_18009534B
0x180095315  mov     rdi, [rdi+10h]
0x180095319  call    IkeGetTlsPeerAddr
0x18009531e  mov     rbx, rax
0x180095321  call    IkeGetTlsMmLuid
0x180095326  mov     r9, rax
0x180095329  lea     r8, WPP_689a915fb9f93bdb61c12c2fd59547e5_Traceguids
0x180095330  lea     rax, [rbp+1E0h+LibFileName]
0x180095334  mov     edx, 0Bh
0x180095339  mov     [rsp+2E0h+var_2B8], rax
0x18009533e  mov     rcx, rdi
0x180095341  mov     [rsp+2E0h+var_2C0], rbx
0x180095346  call    WPP_SF_iSS
0x18009534b  mov     eax, cs:dword_180173278
0x180095351  cmp     eax, 4
0x180095354  jbe     short loc_1800953B7
0x180095356  call    IkeGetTlsMmLuid
0x18009535b  mov     [rsp+2E0h+var_2B0], rax
0x180095360  lea     rax, [rsp+2E0h+var_2B0]
0x180095365  mov     [rsp+2E0h+var_280], rax
0x18009536a  mov     [rsp+2E0h+var_278], 8
0x180095373  call    IkeGetTlsPeerAddr
0x180095378  mov     rdx, rax
0x18009537b  lea     rcx, [rsp+2E0h+var_270]
0x180095380  call    _tlgCreate1Sz_wchar_t
0x180095385  lea     rdx, [rbp+1E0h+LibFileName]
0x180095389  lea     rcx, [rbp+1E0h+var_260]
0x18009538d  call    _tlgCreate1Sz_wchar_t
0x180095392  lea     rcx, [rsp+2E0h+var_2A0]
0x180095397  mov     [rsp+2E0h+var_2B8], rcx
0x18009539c  lea     rdx, unk_180158B18
0x1800953a3  lea     rcx, dword_180173278
0x1800953aa  mov     dword ptr [rsp+2E0h+var_2C0], 5
0x1800953b2  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800953b7  xor     edx, edx; hFile
0x1800953b9  lea     rcx, [rbp+1E0h+LibFileName]; lpLibFileName
0x1800953bd  mov     r8d, 800h; dwFlags
0x1800953c3  call    cs:__imp_LoadLibraryExW
0x1800953c9  mov     cs:g_gwSvcIkeModule, rax
0x1800953d0  test    rax, rax
0x1800953d3  jnz     short loc_1800953E7
0x1800953d5  call    cs:__imp_GetLastError
0x1800953db  lea     rdx, aLoadlibraryexw; "LoadLibraryExW"
0x1800953e2  jmp     loc_180095470
0x1800953e7  lea     rdx, aCreatetunnel; "CreateTunnel"
0x1800953ee  mov     rcx, rax; hModule
0x1800953f1  call    cs:__imp_GetProcAddress
0x1800953f7  mov     cs:g_fpGwSvcCreateTunnel, rax
0x1800953fe  test    rax, rax
0x180095401  jz      short loc_1800953D5
0x180095403  mov     rcx, cs:g_gwSvcIkeModule; hModule
0x18009540a  lea     rdx, aClosetunnel; "CloseTunnel"
0x180095411  call    cs:__imp_GetProcAddress
0x180095417  mov     cs:g_fpGwSvcCloseTunnel, rax
0x18009541e  test    rax, rax
0x180095421  jz      short loc_180095463
0x180095423  mov     rcx, cs:g_gwSvcIkeModule; hModule
0x18009542a  lea     rdx, aNewrasincoming; "NewRasIncomingCall"
0x180095431  call    cs:__imp_GetProcAddress
0x180095437  mov     cs:g_fpGwSvcNewIncomingCall, rax
0x18009543e  test    rax, rax
0x180095441  jz      short loc_180095463
0x180095443  mov     rcx, cs:g_gwSvcIkeModule; hModule
0x18009544a  lea     rdx, aNewrasdemanddi; "NewRasDemandDialCall"
0x180095451  call    cs:__imp_GetProcAddress
0x180095457  mov     cs:g_fpGwSvcNewDemandDialCall, rax
0x18009545e  test    rax, rax
0x180095461  jnz     short loc_1800954AD
0x180095463  call    cs:__imp_GetLastError
0x180095469  lea     rdx, aGetprocaddress; "GetProcAddress"
0x180095470  mov     r9d, esi
0x180095473  mov     r8d, eax
0x180095476  call    WfpReportSysErrorAsWinError
0x18009547b  mov     r14, rax
0x18009547e  test    rax, rax
0x180095481  jz      loc_18009556D
0x180095487  mov     rcx, cs:g_gwSvcIkeModule; hLibModule
0x18009548e  test    rcx, rcx
0x180095491  jz      loc_18009556D
0x180095497  call    cs:__imp_FreeLibrary
0x18009549d  mov     cs:g_gwSvcIkeModule, 0
0x1800954a8  jmp     loc_18009556D
0x1800954ad  xchg    esi, cs:g_IsGwSvcIkeModuleLoaded
0x1800954b3  mov     rdi, cs:WPP_GLOBAL_Control
0x1800954ba  cmp     rdi, r12
0x1800954bd  jz      short loc_180095501
0x1800954bf  cmp     byte ptr [rdi+19h], 4
0x1800954c3  jb      short loc_180095501
0x1800954c5  test    byte ptr [rdi+1Ch], 10h
0x1800954c9  jz      short loc_180095501
0x1800954cb  mov     rdi, [rdi+10h]
0x1800954cf  call    IkeGetTlsPeerAddr
0x1800954d4  mov     rbx, rax
0x1800954d7  call    IkeGetTlsMmLuid
0x1800954dc  mov     r9, rax
0x1800954df  lea     r8, WPP_689a915fb9f93bdb61c12c2fd59547e5_Traceguids
0x1800954e6  lea     rax, [rbp+1E0h+LibFileName]
0x1800954ea  mov     edx, 0Ch
0x1800954ef  mov     [rsp+2E0h+var_2B8], rax
0x1800954f4  mov     rcx, rdi
0x1800954f7  mov     [rsp+2E0h+var_2C0], rbx
0x1800954fc  call    WPP_SF_iSS
0x180095501  mov     eax, cs:dword_180173278
0x180095507  cmp     eax, 4
0x18009550a  jbe     short loc_18009556D
0x18009550c  call    IkeGetTlsMmLuid
0x180095511  mov     [rsp+2E0h+var_2B0], rax
0x180095516  lea     rax, [rsp+2E0h+var_2B0]
0x18009551b  mov     [rsp+2E0h+var_280], rax
0x180095520  mov     [rsp+2E0h+var_278], 8
0x180095529  call    IkeGetTlsPeerAddr
0x18009552e  mov     rdx, rax
0x180095531  lea     rcx, [rsp+2E0h+var_270]
0x180095536  call    _tlgCreate1Sz_wchar_t
0x18009553b  lea     rdx, [rbp+1E0h+LibFileName]
0x18009553f  lea     rcx, [rbp+1E0h+var_260]
0x180095543  call    _tlgCreate1Sz_wchar_t
0x180095548  lea     r9, [rsp+2E0h+var_2A0]
0x18009554d  mov     [rsp+2E0h+var_2B8], r9
0x180095552  lea     rdx, unk_180158AC8
0x180095559  lea     rcx, dword_180173278
0x180095560  mov     dword ptr [rsp+2E0h+var_2C0], 5
0x180095568  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18009556d  lea     rcx, g_ikeGwSvcLock; lpCriticalSection
0x180095574  call    cs:__imp_LeaveCriticalSection
0x18009557a  xor     edx, edx
0x18009557c  lea     rcx, aIkegwsvcdelayl; "IkeGwSvcDelayLoad"
0x180095583  call    TraceLogHelper
0x180095588  mov     ecx, r14d
0x18009558b  movzx   eax, r14w
0x18009558f  and     ecx, 1FFF0000h
0x180095595  cmp     ecx, 70000h
0x18009559b  cmovnz  eax, r14d
0x18009559f  mov     rcx, [rbp+1E0h+var_40]
0x1800955a6  xor     rcx, rsp; StackCookie
0x1800955a9  call    __security_check_cookie
0x1800955ae  add     rsp, 2B8h
0x1800955b5  pop     r14
0x1800955b7  pop     r12
0x1800955b9  pop     rdi
0x1800955ba  pop     rsi
0x1800955bb  pop     rbx
0x1800955bc  pop     rbp
0x1800955bd  retn
```
