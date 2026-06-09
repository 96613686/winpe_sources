# FwAuditInitialize

- ea: `0x18007a220`
- end: `0x18007a5ff`
- name: `FwAuditInitialize`
- size: `991`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callees

- `0x18000177c`
- `0x18005cf9c`
- `0x18006b3b4`
- `0x18006d5b0`
- `0x18006d738`
- `0x18006f520`
- `0x180079870`
- `0x1800798f0`
- `0x180079b30`
- `0x180079bfc`
- `0x18007a220`
- `0x18007b42c`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007a30d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007a30d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007a324`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007a324`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a2a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a2a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a339`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007a254`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007a254`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007a290`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007a2c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007a2f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007a290`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007a2c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007a2f2`
- `AUTHZ!AuthzInitializeResourceManager` at `0x18007a42f`
- `AUTHZ!AuthzInitializeResourceManager` at `0x18007a42f`
- `fwbase!FwLookupAccountSid` at `0x18007a5b7`
- `fwbase!FwLookupAccountSid` at `0x18007a5b7`
- `fwbase!FwSidCreate` at `0x18007a58a`
- `fwbase!FwSidCreate` at `0x18007a58a`
- `fwbase!FwGetTokenInformation` at `0x18007a4dc`
- `fwbase!FwGetTokenInformation` at `0x18007a4dc`
- `fwbase!FwCloseHandle` at `0x18007a3b3`
- `fwbase!FwCloseHandle` at `0x18007a3b3`
- `fwbase!FwReportReturnError` at `0x18007a3c2`
- `fwbase!FwReportReturnError` at `0x18007a402`
- `fwbase!FwReportReturnError` at `0x18007a3c2`
- `fwbase!FwReportReturnError` at `0x18007a402`
- `fwbase!FwAlloc` at `0x18007a44a`
- `fwbase!FwAlloc` at `0x18007a44a`
- `fwbase!FwReportErrorAsWinError` at `0x18007a348`
- `fwbase!FwReportErrorAsWinError` at `0x18007a348`

## string_xrefs

- `0x18007a55b`: `FwAuditInitFirewallServiceSid`
- `0x18007a572`: `FwAuditInitFirewallServiceBinary`
- `0x18007a26d`: `LoadLibraryExW(authz.dll)`
- `0x18007a24d`: `authz.dll`
- `0x18007a27a`: `LoadLibraryW`
- `0x18007a332`: `OpenProcessToken`
- `0x18007a3f6`: `SetPrivilege`
- `0x18007a471`: `FwAuditEventTypeCreate`
- `0x18007a4e8`: `FwGetTokenInformation`
- `0x18007a510`: `FwStringTableCreate(NUM_FW_SE_AUDIT_IDS)`
- `0x18007a538`: `FwStringTableCreate(NUM_FW_SE_AUDIT_IDS2)`
- `0x18007a596`: `FwSidCreate`
- `0x18007a5c3`: `FwLookupAccountSid`

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
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // r8
  int TokenInformation; // eax
  __int64 v15; // r8
  __int64 v16; // rax
  unsigned __int16 v17; // bx
  __int64 v18; // [rsp+30h] [rbp-58h] BYREF
  __int64 v19; // [rsp+38h] [rbp-50h] BYREF
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
  qword_18012E088 = (__int64)ProcAddress;
  v5 = GetProcAddress(hLibModule, "AuthziFreeAuditEventType");
  if ( !v5 )
  {
    v1 = "GetProcAddress(AuthziFreeAuditEventType)";
    goto LABEL_5;
  }
  qword_18012E090 = (__int64)v5;
  v6 = GetProcAddress(hLibModule, "AuthziInitializeAuditEvent");
  if ( !v6 )
  {
    v1 = "GetProcAddress(AuthziInitializeAuditEvent)";
    goto LABEL_5;
  }
  qword_18012E098 = (__int64)v6;
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
      v16 = FwAlloc(320);
      qword_18012E008 = v16;
      if ( !v16 )
      {
        v1 = "FwAlloc";
        v3 = "FwAlloc";
        v8 = 8;
        goto LABEL_14;
      }
      v17 = 0;
      v1 = "FwAuditEventTypeCreate";
      while ( (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, __int64))qword_18012E088)(
                              0,
                              *(unsigned __int16 *)&byte_18012AC90[10 * v17],
                              *(unsigned __int16 *)&byte_18012AC90[10 * v17 + 2],
                              *(unsigned __int16 *)&byte_18012AC90[10 * v17 + 4],
                              v16 + 8LL * v17) )
      {
        if ( ++v17 >= 0x28u )
        {
          TokenInformation = FwGetTokenInformation(TokenHandle, 1, &qword_18012E018, 0);
          v9 = TokenInformation;
          if ( TokenInformation < 0 )
          {
            v1 = "FwGetTokenInformation";
            goto LABEL_25;
          }
          TokenInformation = FwStringTableCreate(0xC8u, 0x5A3Cu, (struct FW_STRINGTABLE_ *)&dword_18012E020);
          v9 = TokenInformation;
          if ( TokenInformation < 0 )
          {
            v1 = "FwStringTableCreate(NUM_FW_SE_AUDIT_IDS)";
            goto LABEL_25;
          }
          TokenInformation = FwStringTableCreate(0x52u, 0x5B68u, (struct FW_STRINGTABLE_ *)&dword_18012E038);
          v9 = TokenInformation;
          if ( TokenInformation < 0 )
          {
            v1 = "FwStringTableCreate(NUM_FW_SE_AUDIT_IDS2)";
            goto LABEL_25;
          }
          FwFillProfileTypesStringTable((const struct FW_STRINGTABLE_ *)&dword_18012E020);
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
          TokenInformation = FwSidCreate(18, 0, &qword_18012E060);
          v9 = TokenInformation;
          if ( TokenInformation < 0 )
          {
            v1 = "FwSidCreate";
            goto LABEL_25;
          }
          TokenInformation = FwLookupAccountSid(qword_18012E060, &qword_18012E068, &qword_18012E070);
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
          byte_18012E0A0 = 1;
          v1 = 0;
          dword_18012E0BC = 1;
          goto LABEL_15;
        }
        v16 = qword_18012E008;
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
  FwReportReturnError("FwAuditInitialize", (unsigned int)TokenInformation, v15);
LABEL_15:
  if ( (unsigned int)dword_1801263B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801263B0, 0x4000000000000LL) )
  {
    LODWORD(v18) = v9;
    v19 = (__int64)v1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (int)&dword_1801263B0,
      (int)byte_18010E943,
      v10,
      v11,
      (const char **)&v19,
      (__int64)&v18);
  }
  if ( v9 < 0 )
    FwAuditShutdown();
  FwCloseHandle(TokenHandle);
  if ( v9 < 0 )
    return (unsigned int)FwReportReturnError("FwAuditInitialize", (unsigned int)v9, v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18007a220  push    rbx
0x18007a222  push    rbp
0x18007a223  push    rsi
0x18007a224  push    rdi
0x18007a225  push    r14
0x18007a227  push    r15
0x18007a229  sub     rsp, 58h
0x18007a22d  mov     rax, cs:__security_cookie
0x18007a234  xor     rax, rsp
0x18007a237  mov     [rsp+88h+var_40], rax
0x18007a23c  xor     edx, edx; hFile
0x18007a23e  mov     [rsp+88h+TokenHandle], 0
0x18007a247  mov     r8d, 800h; dwFlags
0x18007a24d  lea     rcx, LibFileName; "authz.dll"
0x18007a254  call    cs:__imp_LoadLibraryExW
0x18007a25a  mov     cs:hLibModule, rax
0x18007a261  lea     rsi, aFwauditinitial; "FwAuditInitialize"
0x18007a268  test    rax, rax
0x18007a26b  jnz     short loc_18007A286
0x18007a26d  lea     rdi, aLoadlibraryexw; "LoadLibraryExW(authz.dll)"
0x18007a274  call    cs:__imp_GetLastError
0x18007a27a  lea     rdx, aLoadlibraryw; "LoadLibraryW"
0x18007a281  jmp     loc_18007A342
0x18007a286  lea     rdx, aAuthziinitiali_0; "AuthziInitializeAuditEventType"
0x18007a28d  mov     rcx, rax; hModule
0x18007a290  call    cs:__imp_GetProcAddress
0x18007a296  test    rax, rax
0x18007a299  jnz     short loc_18007A2B4
0x18007a29b  lea     rdi, aGetprocaddress_0; "GetProcAddress(AuthziInitializeAuditEve"...
0x18007a2a2  call    cs:__imp_GetLastError
0x18007a2a8  lea     rdx, aGetprocaddress_2; "GetProcAddress"
0x18007a2af  jmp     loc_18007A342
0x18007a2b4  mov     rcx, cs:hLibModule; hModule
0x18007a2bb  lea     rdx, aAuthzifreeaudi; "AuthziFreeAuditEventType"
0x18007a2c2  mov     cs:qword_18012E088, rax
0x18007a2c9  call    cs:__imp_GetProcAddress
0x18007a2cf  test    rax, rax
0x18007a2d2  jnz     short loc_18007A2DD
0x18007a2d4  lea     rdi, aGetprocaddress; "GetProcAddress(AuthziFreeAuditEventType"...
0x18007a2db  jmp     short loc_18007A2A2
0x18007a2dd  mov     rcx, cs:hLibModule; hModule
0x18007a2e4  lea     rdx, aAuthziinitiali; "AuthziInitializeAuditEvent"
0x18007a2eb  mov     cs:qword_18012E090, rax
0x18007a2f2  call    cs:__imp_GetProcAddress
0x18007a2f8  test    rax, rax
0x18007a2fb  jnz     short loc_18007A306
0x18007a2fd  lea     rdi, aGetprocaddress_1; "GetProcAddress(AuthziInitializeAuditEve"...
0x18007a304  jmp     short loc_18007A2A2
0x18007a306  mov     cs:qword_18012E098, rax
0x18007a30d  call    cs:__imp_GetCurrentProcess
0x18007a313  mov     r14d, 28h ; '('
0x18007a319  lea     r8, [rsp+88h+TokenHandle]; TokenHandle
0x18007a31e  mov     rcx, rax; ProcessHandle
0x18007a321  mov     edx, r14d; DesiredAccess
0x18007a324  call    cs:__imp_OpenProcessToken
0x18007a32a  test    eax, eax
0x18007a32c  jnz     loc_18007A3E6
0x18007a332  lea     rdi, aOpenprocesstok; "OpenProcessToken"
0x18007a339  call    cs:__imp_GetLastError
0x18007a33f  mov     rdx, rdi
0x18007a342  mov     r8d, eax
0x18007a345  mov     rcx, rsi
0x18007a348  call    cs:__imp_FwReportErrorAsWinError
0x18007a34e  mov     ebx, eax
0x18007a350  mov     eax, cs:dword_1801263B0
0x18007a356  cmp     eax, 4
0x18007a359  jbe     short loc_18007A3A5
0x18007a35b  mov     rdx, 4000000000000h
0x18007a365  lea     rcx, dword_1801263B0
0x18007a36c  call    _tlgKeywordOn
0x18007a371  test    al, al
0x18007a373  jz      short loc_18007A3A5
0x18007a375  lea     rax, [rsp+88h+var_58]
0x18007a37a  mov     dword ptr [rsp+88h+var_58], ebx
0x18007a37e  mov     [rsp+88h+phAuthzResourceManager], rax; __int64
0x18007a383  lea     rdx, byte_18010E943
0x18007a38a  lea     rax, [rsp+88h+var_50]
0x18007a38f  mov     [rsp+88h+var_50], rdi
0x18007a394  lea     rcx, dword_1801263B0; int
0x18007a39b  mov     [rsp+88h+szResourceManagerName], rax; __int64
0x18007a3a0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007a3a5  test    ebx, ebx
0x18007a3a7  jns     short loc_18007A3AE
0x18007a3a9  call    FwAuditShutdown
0x18007a3ae  mov     rcx, [rsp+88h+TokenHandle]
0x18007a3b3  call    cs:__imp_FwCloseHandle
0x18007a3b9  test    ebx, ebx
0x18007a3bb  jns     short loc_18007A3CA
0x18007a3bd  mov     edx, ebx
0x18007a3bf  mov     rcx, rsi
0x18007a3c2  call    cs:__imp_FwReportReturnError
0x18007a3c8  mov     ebx, eax
0x18007a3ca  mov     eax, ebx
0x18007a3cc  mov     rcx, [rsp+88h+var_40]
0x18007a3d1  xor     rcx, rsp; StackCookie
0x18007a3d4  call    __security_check_cookie
0x18007a3d9  add     rsp, 58h
0x18007a3dd  pop     r15
0x18007a3df  pop     r14
0x18007a3e1  pop     rdi
0x18007a3e2  pop     rsi
0x18007a3e3  pop     rbp
0x18007a3e4  pop     rbx
0x18007a3e5  retn
0x18007a3e6  mov     rcx, [rsp+88h+TokenHandle]
0x18007a3eb  call    SetPrivilege
0x18007a3f0  mov     ebx, eax
0x18007a3f2  test    eax, eax
0x18007a3f4  jns     short loc_18007A40D
0x18007a3f6  lea     rdi, aSetprivilege; "SetPrivilege"
0x18007a3fd  mov     edx, eax
0x18007a3ff  mov     rcx, rsi
0x18007a402  call    cs:__imp_FwReportReturnError
0x18007a408  jmp     loc_18007A350
0x18007a40d  lea     rax, gFwAudit
0x18007a414  xor     r9d, r9d; pfnFreeDynamicGroups
0x18007a417  mov     [rsp+88h+phAuthzResourceManager], rax; phAuthzResourceManager
0x18007a41c  xor     r8d, r8d; pfnComputeDynamicGroups
0x18007a41f  lea     rax, FW_AUDIT_SUBSYTEM_NAME; "Windows Firewall"
0x18007a426  xor     edx, edx; pfnDynamicAccessCheck
0x18007a428  xor     ecx, ecx; Flags
0x18007a42a  mov     [rsp+88h+szResourceManagerName], rax; szResourceManagerName
0x18007a42f  call    cs:__imp_AuthzInitializeResourceManager
0x18007a435  test    eax, eax
0x18007a437  jnz     short loc_18007A445
0x18007a439  lea     rdi, aAuthzinitializ_0; "AuthzInitializeResourceManager"
0x18007a440  jmp     loc_18007A339
0x18007a445  mov     ecx, 140h
0x18007a44a  call    cs:__imp_FwAlloc
0x18007a450  mov     cs:qword_18012E008, rax
0x18007a457  test    rax, rax
0x18007a45a  jnz     short loc_18007A46F
0x18007a45c  lea     rdi, aFwalloc_0; "FwAlloc"
0x18007a463  mov     rdx, rdi
0x18007a466  lea     r8d, [rax+8]
0x18007a46a  jmp     loc_18007A345
0x18007a46f  xor     ebx, ebx
0x18007a471  lea     rdi, aFwauditeventty; "FwAuditEventTypeCreate"
0x18007a478  lea     r15, byte_18012AC90
0x18007a47f  lea     ebp, [rbx+1]
0x18007a482  movzx   ecx, bx
0x18007a485  lea     rdx, [rax+rcx*8]
0x18007a489  mov     rax, cs:qword_18012E088
0x18007a490  lea     r10, [rcx+rcx*4]
0x18007a494  mov     [rsp+88h+szResourceManagerName], rdx
0x18007a499  movzx   edx, word ptr [r15+r10*2]
0x18007a49e  xor     ecx, ecx
0x18007a4a0  movzx   r9d, word ptr [r15+r10*2+4]
0x18007a4a6  movzx   r8d, word ptr [r15+r10*2+2]
0x18007a4ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a4b1  test    eax, eax
0x18007a4b3  jz      loc_18007A339
0x18007a4b9  add     bx, bp
0x18007a4bc  cmp     bx, r14w
0x18007a4c0  jnb     short loc_18007A4CB
0x18007a4c2  mov     rax, cs:qword_18012E008
0x18007a4c9  jmp     short loc_18007A482
0x18007a4cb  mov     rcx, [rsp+88h+TokenHandle]
0x18007a4d0  lea     r8, qword_18012E018
0x18007a4d7  xor     r9d, r9d
0x18007a4da  mov     edx, ebp
0x18007a4dc  call    cs:__imp_FwGetTokenInformation
0x18007a4e2  mov     ebx, eax
0x18007a4e4  test    eax, eax
0x18007a4e6  jns     short loc_18007A4F4
0x18007a4e8  lea     rdi, aFwgettokeninfo_0; "FwGetTokenInformation"
0x18007a4ef  jmp     loc_18007A3FD
0x18007a4f4  lea     r8, dword_18012E020; struct FW_STRINGTABLE_ *
0x18007a4fb  mov     edx, 5A3Ch; unsigned int
0x18007a500  mov     ecx, 0C8h; unsigned int
0x18007a505  call    ?FwStringTableCreate@@YAJKIPEAUFW_STRINGTABLE_@@@Z; FwStringTableCreate(ulong,uint,FW_STRINGTABLE_ *)
0x18007a50a  mov     ebx, eax
0x18007a50c  test    eax, eax
0x18007a50e  jns     short loc_18007A51C
0x18007a510  lea     rdi, aFwstringtablec_0; "FwStringTableCreate(NUM_FW_SE_AUDIT_IDS"...
0x18007a517  jmp     loc_18007A3FD
0x18007a51c  lea     r8, dword_18012E038; struct FW_STRINGTABLE_ *
0x18007a523  mov     edx, 5B68h; unsigned int
0x18007a528  mov     ecx, 52h ; 'R'; unsigned int
0x18007a52d  call    ?FwStringTableCreate@@YAJKIPEAUFW_STRINGTABLE_@@@Z; FwStringTableCreate(ulong,uint,FW_STRINGTABLE_ *)
0x18007a532  mov     ebx, eax
0x18007a534  test    eax, eax
0x18007a536  jns     short loc_18007A544
0x18007a538  lea     rdi, aFwstringtablec_1; "FwStringTableCreate(NUM_FW_SE_AUDIT_IDS"...
0x18007a53f  jmp     loc_18007A3FD
0x18007a544  lea     rcx, dword_18012E020; struct FW_STRINGTABLE_ *
0x18007a54b  call    ?FwFillProfileTypesStringTable@@YAXPEBUFW_STRINGTABLE_@@@Z; FwFillProfileTypesStringTable(FW_STRINGTABLE_ const *)
0x18007a550  call    ?FwAuditInitFirewallServiceSid@@YAJXZ; FwAuditInitFirewallServiceSid(void)
0x18007a555  mov     ebx, eax
0x18007a557  test    eax, eax
0x18007a559  jns     short loc_18007A567
0x18007a55b  lea     rdi, aFwauditinitfir; "FwAuditInitFirewallServiceSid"
0x18007a562  jmp     loc_18007A3FD
0x18007a567  call    ?FwAuditInitFirewallServiceBinary@@YAJXZ; FwAuditInitFirewallServiceBinary(void)
0x18007a56c  mov     ebx, eax
0x18007a56e  test    eax, eax
0x18007a570  jns     short loc_18007A57E
0x18007a572  lea     rdi, aFwauditinitfir_0; "FwAuditInitFirewallServiceBinary"
0x18007a579  jmp     loc_18007A3FD
0x18007a57e  xor     edx, edx
0x18007a580  lea     r8, qword_18012E060
0x18007a587  lea     ecx, [rdx+12h]
0x18007a58a  call    cs:__imp_FwSidCreate
0x18007a590  mov     ebx, eax
0x18007a592  test    eax, eax
0x18007a594  jns     short loc_18007A5A2
0x18007a596  lea     rdi, aFwsidcreate_0; "FwSidCreate"
0x18007a59d  jmp     loc_18007A3FD
0x18007a5a2  mov     rcx, cs:qword_18012E060
0x18007a5a9  lea     r8, qword_18012E070
0x18007a5b0  lea     rdx, qword_18012E068
0x18007a5b7  call    cs:__imp_FwLookupAccountSid
0x18007a5bd  mov     ebx, eax
0x18007a5bf  test    eax, eax
0x18007a5c1  jns     short loc_18007A5CF
0x18007a5c3  lea     rdi, aFwlookupaccoun_0; "FwLookupAccountSid"
0x18007a5ca  jmp     loc_18007A3FD
0x18007a5cf  call    FwRegisterEventProvider
0x18007a5d4  call    FwAuditPolicyNotifyRegister
0x18007a5d9  mov     ebx, eax
0x18007a5db  test    eax, eax
0x18007a5dd  jns     short loc_18007A5EB
0x18007a5df  lea     rdi, aFwauditpolicyn; "FwAuditPolicyNotifyRegister"
0x18007a5e6  jmp     loc_18007A3FD
0x18007a5eb  mov     cs:byte_18012E0A0, bpl
0x18007a5f2  xor     edi, edi
0x18007a5f4  mov     cs:dword_18012E0BC, ebp
0x18007a5fa  jmp     loc_18007A350
```
