# FwAuditInitialize

- ea: `0x18007df70`
- end: `0x18007e3bc`
- name: `FwAuditInitialize`
- size: `1100`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callees

- `0x180001784`
- `0x180061c90`
- `0x18006e454`
- `0x1800708b0`
- `0x180070a80`
- `0x1800729c0`
- `0x18007d4f4`
- `0x18007d580`
- `0x18007d7fc`
- `0x18007d8c8`
- `0x18007df70`
- `0x18007f2ec`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007e09e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007e09e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007e081`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007e081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dfca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e0b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dfca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e0b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007dfec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e031`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e060`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007dfec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e031`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e060`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007dfa4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007dfa4`
- `AUTHZ!AuthzInitializeResourceManager` at `0x18007e1ce`
- `AUTHZ!AuthzInitializeResourceManager` at `0x18007e1ce`
- `fwbase!FwReportErrorAsWinError` at `0x18007e0ce`
- `fwbase!FwReportErrorAsWinError` at `0x18007e0ce`
- `fwbase!FwLookupAccountSid` at `0x18007e36e`
- `fwbase!FwLookupAccountSid` at `0x18007e36e`
- `fwbase!FwSidCreate` at `0x18007e33b`
- `fwbase!FwSidCreate` at `0x18007e33b`
- `fwbase!FwGetTokenInformation` at `0x18007e287`
- `fwbase!FwGetTokenInformation` at `0x18007e287`
- `fwbase!FwCloseHandle` at `0x18007e13f`
- `fwbase!FwCloseHandle` at `0x18007e13f`
- `fwbase!FwReportReturnError` at `0x18007e154`
- `fwbase!FwReportReturnError` at `0x18007e19b`
- `fwbase!FwReportReturnError` at `0x18007e154`
- `fwbase!FwReportReturnError` at `0x18007e19b`
- `fwbase!FwAlloc` at `0x18007e1ef`
- `fwbase!FwAlloc` at `0x18007e1ef`

## string_xrefs

- `0x18007e30c`: `FwAuditInitFirewallServiceSid`
- `0x18007e323`: `FwAuditInitFirewallServiceBinary`
- `0x18007dfc3`: `LoadLibraryExW(authz.dll)`
- `0x18007df9d`: `authz.dll`
- `0x18007dfd6`: `LoadLibraryW`
- `0x18007e0b2`: `OpenProcessToken`
- `0x18007e18f`: `SetPrivilege`
- `0x18007e21c`: `FwAuditEventTypeCreate`
- `0x18007e299`: `FwGetTokenInformation`
- `0x18007e2c1`: `FwStringTableCreate(NUM_FW_SE_AUDIT_IDS)`
- `0x18007e2e9`: `FwStringTableCreate(NUM_FW_SE_AUDIT_IDS2)`
- `0x18007e34d`: `FwSidCreate`
- `0x18007e380`: `FwLookupAccountSid`

## pseudocode

```c
__int64 FwAuditInitialize()
{
  HMODULE Library; // rax
  const char *v1; // rdi
  DWORD LastError; // eax
  const char *v3; // rdx
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  HANDLE CurrentProcess; // rax
  __int64 v8; // r8
  int v9; // ebx
  int TokenInformation; // eax
  __int64 v12; // rax
  unsigned __int16 v13; // bx
  __int64 v14; // [rsp+30h] [rbp-58h] BYREF
  __int64 v15; // [rsp+38h] [rbp-50h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-48h] BYREF

  TokenHandle = 0;
  Library = LoadLibraryExW(L"authz.dll", 0, 0x800u);
  hLibModule = Library;
  if ( !Library )
  {
    v1 = "LoadLibraryExW(authz.dll)";
    LastError = GetLastError();
    v3 = "LoadLibraryW";
LABEL_13:
    v8 = LastError;
LABEL_14:
    v9 = FwReportErrorAsWinError("FwAuditInitialize", v3, v8);
    goto LABEL_15;
  }
  ProcAddress = GetProcAddress(Library, "AuthziInitializeAuditEventType");
  if ( !ProcAddress )
  {
    v1 = "GetProcAddress(AuthziInitializeAuditEventType)";
LABEL_5:
    LastError = GetLastError();
    v3 = "GetProcAddress";
    goto LABEL_13;
  }
  qword_180134238 = (__int64)ProcAddress;
  v5 = GetProcAddress(hLibModule, "AuthziFreeAuditEventType");
  if ( !v5 )
  {
    v1 = "GetProcAddress(AuthziFreeAuditEventType)";
    goto LABEL_5;
  }
  qword_180134240 = (__int64)v5;
  v6 = GetProcAddress(hLibModule, "AuthziInitializeAuditEvent");
  if ( !v6 )
  {
    v1 = "GetProcAddress(AuthziInitializeAuditEvent)";
    goto LABEL_5;
  }
  qword_180134248 = (__int64)v6;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    v1 = "OpenProcessToken";
LABEL_12:
    LastError = GetLastError();
    v3 = v1;
    goto LABEL_13;
  }
  TokenInformation = SetPrivilege(TokenHandle);
  v9 = TokenInformation;
  if ( TokenInformation >= 0 )
  {
    if ( AuthzInitializeResourceManager(0, 0, 0, 0, L"Windows Firewall", &gFwAudit) )
    {
      v12 = FwAlloc(320);
      qword_1801341B8 = v12;
      if ( !v12 )
      {
        v1 = "FwAlloc";
        v3 = "FwAlloc";
        v8 = 8;
        goto LABEL_14;
      }
      v13 = 0;
      v1 = "FwAuditEventTypeCreate";
      while ( (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, __int64))qword_180134238)(
                              0,
                              *(unsigned __int16 *)&byte_180130E90[10 * v13],
                              *(unsigned __int16 *)&byte_180130E90[10 * v13 + 2],
                              *(unsigned __int16 *)&byte_180130E90[10 * v13 + 4],
                              v12 + 8LL * v13) )
      {
        if ( ++v13 >= 0x28u )
        {
          TokenInformation = FwGetTokenInformation(TokenHandle, 1, &qword_1801341C8, 0);
          v9 = TokenInformation;
          if ( TokenInformation < 0 )
          {
            v1 = "FwGetTokenInformation";
            goto LABEL_25;
          }
          TokenInformation = FwStringTableCreate(0xC8u, 0x5A3Cu, (struct FW_STRINGTABLE_ *)&dword_1801341D0);
          v9 = TokenInformation;
          if ( TokenInformation < 0 )
          {
            v1 = "FwStringTableCreate(NUM_FW_SE_AUDIT_IDS)";
            goto LABEL_25;
          }
          TokenInformation = FwStringTableCreate(0x52u, 0x5B68u, (struct FW_STRINGTABLE_ *)&dword_1801341E8);
          v9 = TokenInformation;
          if ( TokenInformation < 0 )
          {
            v1 = "FwStringTableCreate(NUM_FW_SE_AUDIT_IDS2)";
            goto LABEL_25;
          }
          FwFillProfileTypesStringTable((const struct FW_STRINGTABLE_ *)&dword_1801341D0);
          TokenInformation = FwAuditInitFirewallServiceSid();
          v9 = TokenInformation;
          if ( TokenInformation < 0 )
          {
            v1 = "FwAuditInitFirewallServiceSid";
            goto LABEL_25;
          }
          TokenInformation = FwAuditInitFirewallServiceBinary();
          v9 = TokenInformation;
          if ( TokenInformation < 0 )
          {
            v1 = "FwAuditInitFirewallServiceBinary";
            goto LABEL_25;
          }
          TokenInformation = FwSidCreate(18, 0, &qword_180134210);
          v9 = TokenInformation;
          if ( TokenInformation < 0 )
          {
            v1 = "FwSidCreate";
            goto LABEL_25;
          }
          TokenInformation = FwLookupAccountSid(qword_180134210, &qword_180134218, &qword_180134220);
          v9 = TokenInformation;
          if ( TokenInformation < 0 )
          {
            v1 = "FwLookupAccountSid";
            goto LABEL_25;
          }
          FwRegisterEventProvider();
          TokenInformation = FwAuditPolicyNotifyRegister();
          v9 = TokenInformation;
          if ( TokenInformation < 0 )
          {
            v1 = "FwAuditPolicyNotifyRegister";
            goto LABEL_25;
          }
          byte_180134250 = 1;
          v1 = 0;
          dword_18013426C = 1;
          goto LABEL_15;
        }
        v12 = qword_1801341B8;
      }
    }
    else
    {
      v1 = "AuthzInitializeResourceManager";
    }
    goto LABEL_12;
  }
  v1 = "SetPrivilege";
LABEL_25:
  FwReportReturnError("FwAuditInitialize", (unsigned int)TokenInformation);
LABEL_15:
  if ( (unsigned int)dword_18012C3B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18012C3B0, 0x4000000000000LL) )
  {
    LODWORD(v14) = v9;
    v15 = (__int64)v1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (int)&dword_18012C3B0,
      (__int64)&v15,
      (__int64)&v14);
  }
  if ( v9 < 0 )
    FwAuditShutdown();
  FwCloseHandle(TokenHandle);
  if ( v9 < 0 )
    return (unsigned int)FwReportReturnError("FwAuditInitialize", (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18007df70  push    rbx
0x18007df72  push    rbp
0x18007df73  push    rsi
0x18007df74  push    rdi
0x18007df75  push    r14
0x18007df77  push    r15
0x18007df79  sub     rsp, 58h
0x18007df7d  mov     rax, cs:__security_cookie
0x18007df84  xor     rax, rsp
0x18007df87  mov     [rsp+88h+var_40], rax
0x18007df8c  xor     edx, edx; hFile
0x18007df8e  mov     [rsp+88h+TokenHandle], 0
0x18007df97  mov     r8d, 800h; dwFlags
0x18007df9d  lea     rcx, LibFileName; "authz.dll"
0x18007dfa4  call    cs:__imp_LoadLibraryExW
0x18007dfab  nop     dword ptr [rax+rax+00h]
0x18007dfb0  mov     cs:hLibModule, rax
0x18007dfb7  lea     rsi, aFwauditinitial; "FwAuditInitialize"
0x18007dfbe  test    rax, rax
0x18007dfc1  jnz     short loc_18007DFE2
0x18007dfc3  lea     rdi, aLoadlibraryexw; "LoadLibraryExW(authz.dll)"
0x18007dfca  call    cs:__imp_GetLastError
0x18007dfd1  nop     dword ptr [rax+rax+00h]
0x18007dfd6  lea     rdx, aLoadlibraryw; "LoadLibraryW"
0x18007dfdd  jmp     loc_18007E0C8
0x18007dfe2  lea     rdx, aAuthziinitiali_0; "AuthziInitializeAuditEventType"
0x18007dfe9  mov     rcx, rax; hModule
0x18007dfec  call    cs:__imp_GetProcAddress
0x18007dff3  nop     dword ptr [rax+rax+00h]
0x18007dff8  test    rax, rax
0x18007dffb  jnz     short loc_18007E01C
0x18007dffd  lea     rdi, aGetprocaddress_0; "GetProcAddress(AuthziInitializeAuditEve"...
0x18007e004  call    cs:__imp_GetLastError
0x18007e00b  nop     dword ptr [rax+rax+00h]
0x18007e010  lea     rdx, aGetprocaddress_2; "GetProcAddress"
0x18007e017  jmp     loc_18007E0C8
0x18007e01c  mov     rcx, cs:hLibModule; hModule
0x18007e023  lea     rdx, aAuthzifreeaudi; "AuthziFreeAuditEventType"
0x18007e02a  mov     cs:qword_180134238, rax
0x18007e031  call    cs:__imp_GetProcAddress
0x18007e038  nop     dword ptr [rax+rax+00h]
0x18007e03d  test    rax, rax
0x18007e040  jnz     short loc_18007E04B
0x18007e042  lea     rdi, aGetprocaddress; "GetProcAddress(AuthziFreeAuditEventType"...
0x18007e049  jmp     short loc_18007E004
0x18007e04b  mov     rcx, cs:hLibModule; hModule
0x18007e052  lea     rdx, aAuthziinitiali; "AuthziInitializeAuditEvent"
0x18007e059  mov     cs:qword_180134240, rax
0x18007e060  call    cs:__imp_GetProcAddress
0x18007e067  nop     dword ptr [rax+rax+00h]
0x18007e06c  test    rax, rax
0x18007e06f  jnz     short loc_18007E07A
0x18007e071  lea     rdi, aGetprocaddress_1; "GetProcAddress(AuthziInitializeAuditEve"...
0x18007e078  jmp     short loc_18007E004
0x18007e07a  mov     cs:qword_180134248, rax
0x18007e081  call    cs:__imp_GetCurrentProcess
0x18007e088  nop     dword ptr [rax+rax+00h]
0x18007e08d  mov     r14d, 28h ; '('
0x18007e093  lea     r8, [rsp+88h+TokenHandle]; TokenHandle
0x18007e098  mov     rcx, rax; ProcessHandle
0x18007e09b  mov     edx, r14d; DesiredAccess
0x18007e09e  call    cs:__imp_OpenProcessToken
0x18007e0a5  nop     dword ptr [rax+rax+00h]
0x18007e0aa  test    eax, eax
0x18007e0ac  jnz     loc_18007E17F
0x18007e0b2  lea     rdi, aOpenprocesstok; "OpenProcessToken"
0x18007e0b9  call    cs:__imp_GetLastError
0x18007e0c0  nop     dword ptr [rax+rax+00h]
0x18007e0c5  mov     rdx, rdi
0x18007e0c8  mov     r8d, eax
0x18007e0cb  mov     rcx, rsi
0x18007e0ce  call    cs:__imp_FwReportErrorAsWinError
0x18007e0d5  nop     dword ptr [rax+rax+00h]
0x18007e0da  mov     ebx, eax
0x18007e0dc  mov     eax, cs:dword_18012C3B0
0x18007e0e2  cmp     eax, 4
0x18007e0e5  jbe     short loc_18007E131
0x18007e0e7  mov     rdx, 4000000000000h
0x18007e0f1  lea     rcx, dword_18012C3B0
0x18007e0f8  call    _tlgKeywordOn
0x18007e0fd  test    al, al
0x18007e0ff  jz      short loc_18007E131
0x18007e101  lea     rax, [rsp+88h+var_58]
0x18007e106  mov     dword ptr [rsp+88h+var_58], ebx
0x18007e10a  mov     [rsp+88h+phAuthzResourceManager], rax; __int64
0x18007e10f  lea     rdx, word_1801147DE
0x18007e116  lea     rax, [rsp+88h+var_50]
0x18007e11b  mov     [rsp+88h+var_50], rdi
0x18007e120  lea     rcx, dword_18012C3B0; int
0x18007e127  mov     [rsp+88h+szResourceManagerName], rax; __int64
0x18007e12c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007e131  test    ebx, ebx
0x18007e133  jns     short loc_18007E13A
0x18007e135  call    FwAuditShutdown
0x18007e13a  mov     rcx, [rsp+88h+TokenHandle]
0x18007e13f  call    cs:__imp_FwCloseHandle
0x18007e146  nop     dword ptr [rax+rax+00h]
0x18007e14b  test    ebx, ebx
0x18007e14d  jns     short loc_18007E162
0x18007e14f  mov     edx, ebx
0x18007e151  mov     rcx, rsi
0x18007e154  call    cs:__imp_FwReportReturnError
0x18007e15b  nop     dword ptr [rax+rax+00h]
0x18007e160  mov     ebx, eax
0x18007e162  mov     eax, ebx
0x18007e164  mov     rcx, [rsp+88h+var_40]
0x18007e169  xor     rcx, rsp; StackCookie
0x18007e16c  call    __security_check_cookie
0x18007e171  add     rsp, 58h
0x18007e175  pop     r15
0x18007e177  pop     r14
0x18007e179  pop     rdi
0x18007e17a  pop     rsi
0x18007e17b  pop     rbp
0x18007e17c  pop     rbx
0x18007e17d  retn
0x18007e17f  mov     rcx, [rsp+88h+TokenHandle]
0x18007e184  call    SetPrivilege
0x18007e189  mov     ebx, eax
0x18007e18b  test    eax, eax
0x18007e18d  jns     short loc_18007E1AC
0x18007e18f  lea     rdi, aSetprivilege; "SetPrivilege"
0x18007e196  mov     edx, eax
0x18007e198  mov     rcx, rsi
0x18007e19b  call    cs:__imp_FwReportReturnError
0x18007e1a2  nop     dword ptr [rax+rax+00h]
0x18007e1a7  jmp     loc_18007E0DC
0x18007e1ac  lea     rax, gFwAudit
0x18007e1b3  xor     r9d, r9d; pfnFreeDynamicGroups
0x18007e1b6  mov     [rsp+88h+phAuthzResourceManager], rax; phAuthzResourceManager
0x18007e1bb  xor     r8d, r8d; pfnComputeDynamicGroups
0x18007e1be  lea     rax, FW_AUDIT_SUBSYTEM_NAME; "Windows Firewall"
0x18007e1c5  xor     edx, edx; pfnDynamicAccessCheck
0x18007e1c7  xor     ecx, ecx; Flags
0x18007e1c9  mov     [rsp+88h+szResourceManagerName], rax; szResourceManagerName
0x18007e1ce  call    cs:__imp_AuthzInitializeResourceManager
0x18007e1d5  nop     dword ptr [rax+rax+00h]
0x18007e1da  test    eax, eax
0x18007e1dc  jnz     short loc_18007E1EA
0x18007e1de  lea     rdi, aAuthzinitializ_0; "AuthzInitializeResourceManager"
0x18007e1e5  jmp     loc_18007E0B9
0x18007e1ea  mov     ecx, 140h
0x18007e1ef  call    cs:__imp_FwAlloc
0x18007e1f6  nop     dword ptr [rax+rax+00h]
0x18007e1fb  mov     cs:qword_1801341B8, rax
0x18007e202  test    rax, rax
0x18007e205  jnz     short loc_18007E21A
0x18007e207  lea     rdi, aFwalloc_0; "FwAlloc"
0x18007e20e  mov     rdx, rdi
0x18007e211  lea     r8d, [rax+8]
0x18007e215  jmp     loc_18007E0CB
0x18007e21a  xor     ebx, ebx
0x18007e21c  lea     rdi, aFwauditeventty; "FwAuditEventTypeCreate"
0x18007e223  lea     r15, byte_180130E90
0x18007e22a  lea     ebp, [rbx+1]
0x18007e22d  movzx   ecx, bx
0x18007e230  lea     rdx, [rax+rcx*8]
0x18007e234  mov     rax, cs:qword_180134238
0x18007e23b  lea     r10, [rcx+rcx*4]
0x18007e23f  mov     [rsp+88h+szResourceManagerName], rdx
0x18007e244  movzx   edx, word ptr [r15+r10*2]
0x18007e249  xor     ecx, ecx
0x18007e24b  movzx   r9d, word ptr [r15+r10*2+4]
0x18007e251  movzx   r8d, word ptr [r15+r10*2+2]
0x18007e257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e25c  test    eax, eax
0x18007e25e  jz      loc_18007E0B9
0x18007e264  add     bx, bp
0x18007e267  cmp     bx, r14w
0x18007e26b  jnb     short loc_18007E276
0x18007e26d  mov     rax, cs:qword_1801341B8
0x18007e274  jmp     short loc_18007E22D
0x18007e276  mov     rcx, [rsp+88h+TokenHandle]
0x18007e27b  lea     r8, qword_1801341C8
0x18007e282  xor     r9d, r9d
0x18007e285  mov     edx, ebp
0x18007e287  call    cs:__imp_FwGetTokenInformation
0x18007e28e  nop     dword ptr [rax+rax+00h]
0x18007e293  mov     ebx, eax
0x18007e295  test    eax, eax
0x18007e297  jns     short loc_18007E2A5
0x18007e299  lea     rdi, aFwgettokeninfo_0; "FwGetTokenInformation"
0x18007e2a0  jmp     loc_18007E196
0x18007e2a5  lea     r8, dword_1801341D0; struct FW_STRINGTABLE_ *
0x18007e2ac  mov     edx, 5A3Ch; unsigned int
0x18007e2b1  mov     ecx, 0C8h; unsigned int
0x18007e2b6  call    ?FwStringTableCreate@@YAJKIPEAUFW_STRINGTABLE_@@@Z; FwStringTableCreate(ulong,uint,FW_STRINGTABLE_ *)
0x18007e2bb  mov     ebx, eax
0x18007e2bd  test    eax, eax
0x18007e2bf  jns     short loc_18007E2CD
0x18007e2c1  lea     rdi, aFwstringtablec_0; "FwStringTableCreate(NUM_FW_SE_AUDIT_IDS"...
0x18007e2c8  jmp     loc_18007E196
0x18007e2cd  lea     r8, dword_1801341E8; struct FW_STRINGTABLE_ *
0x18007e2d4  mov     edx, 5B68h; unsigned int
0x18007e2d9  mov     ecx, 52h ; 'R'; unsigned int
0x18007e2de  call    ?FwStringTableCreate@@YAJKIPEAUFW_STRINGTABLE_@@@Z; FwStringTableCreate(ulong,uint,FW_STRINGTABLE_ *)
0x18007e2e3  mov     ebx, eax
0x18007e2e5  test    eax, eax
0x18007e2e7  jns     short loc_18007E2F5
0x18007e2e9  lea     rdi, aFwstringtablec_1; "FwStringTableCreate(NUM_FW_SE_AUDIT_IDS"...
0x18007e2f0  jmp     loc_18007E196
0x18007e2f5  lea     rcx, dword_1801341D0; struct FW_STRINGTABLE_ *
0x18007e2fc  call    ?FwFillProfileTypesStringTable@@YAXPEBUFW_STRINGTABLE_@@@Z; FwFillProfileTypesStringTable(FW_STRINGTABLE_ const *)
0x18007e301  call    ?FwAuditInitFirewallServiceSid@@YAJXZ; FwAuditInitFirewallServiceSid(void)
0x18007e306  mov     ebx, eax
0x18007e308  test    eax, eax
0x18007e30a  jns     short loc_18007E318
0x18007e30c  lea     rdi, aFwauditinitfir; "FwAuditInitFirewallServiceSid"
0x18007e313  jmp     loc_18007E196
0x18007e318  call    ?FwAuditInitFirewallServiceBinary@@YAJXZ; FwAuditInitFirewallServiceBinary(void)
0x18007e31d  mov     ebx, eax
0x18007e31f  test    eax, eax
0x18007e321  jns     short loc_18007E32F
0x18007e323  lea     rdi, aFwauditinitfir_0; "FwAuditInitFirewallServiceBinary"
0x18007e32a  jmp     loc_18007E196
0x18007e32f  xor     edx, edx
0x18007e331  lea     r8, qword_180134210
0x18007e338  lea     ecx, [rdx+12h]
0x18007e33b  call    cs:__imp_FwSidCreate
0x18007e342  nop     dword ptr [rax+rax+00h]
0x18007e347  mov     ebx, eax
0x18007e349  test    eax, eax
0x18007e34b  jns     short loc_18007E359
0x18007e34d  lea     rdi, aFwsidcreate_0; "FwSidCreate"
0x18007e354  jmp     loc_18007E196
0x18007e359  mov     rcx, cs:qword_180134210
0x18007e360  lea     r8, qword_180134220
0x18007e367  lea     rdx, qword_180134218
0x18007e36e  call    cs:__imp_FwLookupAccountSid
0x18007e375  nop     dword ptr [rax+rax+00h]
0x18007e37a  mov     ebx, eax
0x18007e37c  test    eax, eax
0x18007e37e  jns     short loc_18007E38C
0x18007e380  lea     rdi, aFwlookupaccoun_0; "FwLookupAccountSid"
0x18007e387  jmp     loc_18007E196
0x18007e38c  call    FwRegisterEventProvider
0x18007e391  call    FwAuditPolicyNotifyRegister
0x18007e396  mov     ebx, eax
0x18007e398  test    eax, eax
0x18007e39a  jns     short loc_18007E3A8
0x18007e39c  lea     rdi, aFwauditpolicyn; "FwAuditPolicyNotifyRegister"
0x18007e3a3  jmp     loc_18007E196
0x18007e3a8  mov     cs:byte_180134250, bpl
0x18007e3af  xor     edi, edi
0x18007e3b1  mov     cs:dword_18013426C, ebp
0x18007e3b7  jmp     loc_18007E0DC
```
