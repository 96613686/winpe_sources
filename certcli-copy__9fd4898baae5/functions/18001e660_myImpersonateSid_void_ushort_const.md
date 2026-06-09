# myImpersonateSid(void *,ushort const *)

- ea: `0x18001e660`
- end: `0x18001e8dd`
- name: `?myImpersonateSid@@YAJPEAXPEBG@Z`
- size: `637`
- prototype: `__int64 __fastcall(PSID Sid, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001e5f8`

## callees

- `0x18001d27c`
- `0x18001e004`
- `0x18001e46c`
- `0x18001e660`
- `0x180021438`
- `0x180039740`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001e6e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001e6e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e6fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e6fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e784`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e78d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e796`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e784`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e78d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e796`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e779`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e779`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001e7eb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001e7eb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001e7c8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001e893`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001e7c8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001e893`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001e8b6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001e8b6`
- `certca!__imp_?myHGetLastError@@YAJXZ` at `0x18001e720`
- `certca!__imp_?myHGetLastError@@YAJXZ` at `0x18001e7d2`
- `certca!__imp_?myHGetLastError@@YAJXZ` at `0x18001e89d`
- `certca!__imp_?myHGetLastError@@YAJXZ` at `0x18001e8c4`
- `certca!__imp_?myHGetLastError@@YAJXZ` at `0x18001e720`
- `certca!__imp_?myHGetLastError@@YAJXZ` at `0x18001e7d2`
- `certca!__imp_?myHGetLastError@@YAJXZ` at `0x18001e89d`
- `certca!__imp_?myHGetLastError@@YAJXZ` at `0x18001e8c4`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001e769`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001e822`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001e769`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001e822`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18001e8b0`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18001e8b0`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x18001e872`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x18001e872`

## string_xrefs

- `0x18001e6de`: `kernel32.dll`

## pseudocode

```c
__int64 __fastcall myImpersonateSid(PSID Sid, const unsigned __int16 *a2)
{
  WCHAR *v2; // rsi
  unsigned __int16 *v3; // rdi
  unsigned int SidFromRid; // eax
  unsigned int Error; // ebx
  int v7; // edx
  unsigned int v8; // ecx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v11; // rbx
  void *ProcessTokenIfSidMatch; // rax
  unsigned int AccountNameFromSID; // eax
  int v15; // eax
  unsigned int v16; // edx
  unsigned int v17; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpszUsername; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpszDomain; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwProcessId[64]; // [rsp+80h] [rbp-80h] BYREF

  v2 = 0;
  hMem = 0;
  v3 = 0;
  lpszDomain = 0;
  lpszUsername = 0;
  hObject = 0;
  SidFromRid = myGetSidFromRid((enum WELL_KNOWN_SID_TYPE)Sid, &hMem);
  Error = SidFromRid;
  if ( SidFromRid )
  {
    v7 = SidFromRid;
    v8 = 635634074;
LABEL_12:
    CSPrintErrorLineFile(v8, v7);
    goto LABEL_13;
  }
  ProcAddress = (FARPROC)qword_18006B0A8;
  v17 = 256;
  if ( !qword_18006B0A8
    && ((ModuleHandleW = GetModuleHandleW(L"kernel32.dll")) == 0
     || (ProcAddress = GetProcAddress(ModuleHandleW, "K32EnumProcesses"), (qword_18006B0A8 = (__int64)ProcAddress) == 0))
    || !((unsigned int (__fastcall *)(DWORD *, __int64, unsigned int *))ProcAddress)(dwProcessId, 256, &v17) )
  {
    Error = myHGetLastError();
    v7 = Error;
    v8 = 636354970;
    goto LABEL_12;
  }
  v11 = 0;
  if ( (v17 & 0xFFFFFFFC) == 0 )
  {
LABEL_11:
    Error = -2147024891;
    v8 = 637534618;
    v7 = -2147024891;
    goto LABEL_12;
  }
  while ( 1 )
  {
    ProcessTokenIfSidMatch = GetProcessTokenIfSidMatch(dwProcessId[v11], hMem);
    if ( ProcessTokenIfSidMatch )
      break;
    v11 = (unsigned int)(v11 + 1);
    if ( (unsigned int)v11 >= v17 >> 2 )
      goto LABEL_11;
  }
  if ( !ImpersonateLoggedOnUser(ProcessTokenIfSidMatch) )
  {
    Error = myHGetLastError();
    v7 = Error;
    v8 = 637862298;
    goto LABEL_12;
  }
  if ( EqualSid(Sid, hMem) )
    goto LABEL_29;
  AccountNameFromSID = myGetAccountNameFromSID(
                         Sid,
                         (unsigned __int16 **)&lpszUsername,
                         (unsigned __int16 **)&lpszDomain);
  v3 = (unsigned __int16 *)lpszUsername;
  Error = AccountNameFromSID;
  v2 = (WCHAR *)lpszDomain;
  if ( AccountNameFromSID )
  {
    CSPrintErrorLineFile(0x260C019Au, AccountNameFromSID);
    goto LABEL_27;
  }
  if ( LogonUserExW(lpszUsername, lpszDomain, 0, 5u, 0, &hObject, 0, 0, 0, 0)
    || (v15 = myHLastError(), (Error = v15) == 0) )
  {
    if ( !ImpersonateLoggedOnUser(hObject) )
    {
      v15 = myHGetLastError();
      Error = v15;
      v16 = 639697306;
      goto LABEL_26;
    }
LABEL_29:
    Error = 0;
    goto LABEL_13;
  }
  v16 = 639369626;
LABEL_26:
  CSPrintErrorLineFileData(v3, v16, v15);
LABEL_27:
  if ( !RevertToSelf() )
  {
    v7 = myHGetLastError();
    v8 = 640418202;
    goto LABEL_12;
  }
LABEL_13:
  if ( hObject )
    CloseHandle(hObject);
  LocalFree(hMem);
  LocalFree(v3);
  LocalFree(v2);
  return Error;
}

```

## disassembly

```asm
0x18001e660  mov     [rsp-8+arg_8], rbx
0x18001e665  mov     [rsp-8+arg_10], rsi
0x18001e66a  push    rbp
0x18001e66b  push    rdi
0x18001e66c  push    r14
0x18001e66e  lea     rbp, [rsp-90h]
0x18001e676  sub     rsp, 190h
0x18001e67d  mov     rax, cs:__security_cookie
0x18001e684  xor     rax, rsp
0x18001e687  mov     [rbp+0A0h+var_20], rax
0x18001e68e  xor     esi, esi
0x18001e690  mov     [rsp+1A0h+hMem], 0
0x18001e699  xor     edi, edi
0x18001e69b  mov     [rsp+1A0h+lpszDomain], rsi
0x18001e6a0  lea     rdx, [rsp+1A0h+hMem]; void **
0x18001e6a5  mov     [rsp+1A0h+lpszUsername], rdi
0x18001e6aa  mov     [rsp+1A0h+hObject], rsi
0x18001e6af  mov     r14, rcx
0x18001e6b2  call    ?myGetSidFromRid@@YAJW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; myGetSidFromRid(WELL_KNOWN_SID_TYPE,void * *)
0x18001e6b7  mov     ebx, eax
0x18001e6b9  test    eax, eax
0x18001e6bb  jz      short loc_18001E6C9
0x18001e6bd  mov     edx, eax
0x18001e6bf  mov     ecx, 25E3019Ah
0x18001e6c4  jmp     loc_18001E769
0x18001e6c9  mov     rax, cs:qword_18006B0A8
0x18001e6d0  mov     ebx, 100h
0x18001e6d5  mov     [rsp+1A0h+var_150], ebx
0x18001e6d9  test    rax, rax
0x18001e6dc  jnz     short loc_18001E70C
0x18001e6de  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18001e6e5  call    cs:__imp_GetModuleHandleW
0x18001e6eb  test    rax, rax
0x18001e6ee  jz      short loc_18001E720
0x18001e6f0  lea     rdx, aK32enumprocess; "K32EnumProcesses"
0x18001e6f7  mov     rcx, rax; hModule
0x18001e6fa  call    cs:__imp_GetProcAddress
0x18001e700  mov     cs:qword_18006B0A8, rax
0x18001e707  test    rax, rax
0x18001e70a  jz      short loc_18001E720
0x18001e70c  lea     r8, [rsp+1A0h+var_150]
0x18001e711  mov     edx, ebx
0x18001e713  lea     rcx, [rbp+0A0h+dwProcessId]
0x18001e717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e71c  test    eax, eax
0x18001e71e  jnz     short loc_18001E731
0x18001e720  call    cs:__imp_?myHGetLastError@@YAJXZ; myHGetLastError(void)
0x18001e726  mov     ebx, eax
0x18001e728  mov     edx, eax
0x18001e72a  mov     ecx, 25EE019Ah
0x18001e72f  jmp     short loc_18001E769
0x18001e731  xor     ebx, ebx
0x18001e733  test    [rsp+1A0h+var_150], 0FFFFFFFCh
0x18001e73b  jbe     short loc_18001E75D
0x18001e73d  mov     rdx, [rsp+1A0h+hMem]; pSid1
0x18001e742  mov     ecx, [rbp+rbx*4+0A0h+dwProcessId]; dwProcessId
0x18001e746  call    ?GetProcessTokenIfSidMatch@@YAPEAXKPEAX@Z; GetProcessTokenIfSidMatch(ulong,void *)
0x18001e74b  test    rax, rax
0x18001e74e  jnz     short loc_18001E7C5
0x18001e750  mov     eax, [rsp+1A0h+var_150]
0x18001e754  inc     ebx
0x18001e756  shr     eax, 2
0x18001e759  cmp     ebx, eax
0x18001e75b  jb      short loc_18001E73D
0x18001e75d  mov     ebx, 80070005h
0x18001e762  mov     ecx, 2600019Ah
0x18001e767  mov     edx, ebx
0x18001e769  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001e76f  mov     rcx, [rsp+1A0h+hObject]; hObject
0x18001e774  test    rcx, rcx
0x18001e777  jz      short loc_18001E77F
0x18001e779  call    cs:__imp_CloseHandle
0x18001e77f  mov     rcx, [rsp+1A0h+hMem]; hMem
0x18001e784  call    cs:__imp_LocalFree
0x18001e78a  mov     rcx, rdi; hMem
0x18001e78d  call    cs:__imp_LocalFree
0x18001e793  mov     rcx, rsi; hMem
0x18001e796  call    cs:__imp_LocalFree
0x18001e79c  mov     eax, ebx
0x18001e79e  mov     rcx, [rbp+0A0h+var_20]
0x18001e7a5  xor     rcx, rsp; StackCookie
0x18001e7a8  call    __security_check_cookie
0x18001e7ad  lea     r11, [rsp+1A0h+var_10]
0x18001e7b5  mov     rbx, [r11+28h]
0x18001e7b9  mov     rsi, [r11+30h]
0x18001e7bd  mov     rsp, r11
0x18001e7c0  pop     r14
0x18001e7c2  pop     rdi
0x18001e7c3  pop     rbp
0x18001e7c4  retn
0x18001e7c5  mov     rcx, rax; hToken
0x18001e7c8  call    cs:__imp_ImpersonateLoggedOnUser
0x18001e7ce  test    eax, eax
0x18001e7d0  jnz     short loc_18001E7E3
0x18001e7d2  call    cs:__imp_?myHGetLastError@@YAJXZ; myHGetLastError(void)
0x18001e7d8  mov     ebx, eax
0x18001e7da  mov     edx, eax
0x18001e7dc  mov     ecx, 2605019Ah
0x18001e7e1  jmp     short loc_18001E769
0x18001e7e3  mov     rdx, [rsp+1A0h+hMem]; pSid2
0x18001e7e8  mov     rcx, r14; pSid1
0x18001e7eb  call    cs:__imp_EqualSid
0x18001e7f1  test    eax, eax
0x18001e7f3  jnz     loc_18001E8D6
0x18001e7f9  lea     r8, [rsp+1A0h+lpszDomain]; unsigned __int16 **
0x18001e7fe  mov     rcx, r14; Sid
0x18001e801  lea     rdx, [rsp+1A0h+lpszUsername]; unsigned __int16 **
0x18001e806  call    ?myGetAccountNameFromSID@@YAJPEAXPEAPEAG1@Z; myGetAccountNameFromSID(void *,ushort * *,ushort * *)
0x18001e80b  mov     rdi, [rsp+1A0h+lpszUsername]
0x18001e810  mov     ebx, eax
0x18001e812  mov     rsi, [rsp+1A0h+lpszDomain]
0x18001e817  test    eax, eax
0x18001e819  jz      short loc_18001E82D
0x18001e81b  mov     edx, eax
0x18001e81d  mov     ecx, 260C019Ah
0x18001e822  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001e828  jmp     loc_18001E8B6
0x18001e82d  mov     [rsp+1A0h+pQuotaLimits], 0; pQuotaLimits
0x18001e836  lea     rax, [rsp+1A0h+hObject]
0x18001e83b  mov     [rsp+1A0h+pdwProfileLength], 0; pdwProfileLength
0x18001e844  mov     r9d, 5; dwLogonType
0x18001e84a  mov     [rsp+1A0h+ppProfileBuffer], 0; ppProfileBuffer
0x18001e853  xor     r8d, r8d; lpszPassword
0x18001e856  mov     [rsp+1A0h+ppLogonSid], 0; ppLogonSid
0x18001e85f  mov     rdx, rsi; lpszDomain
0x18001e862  mov     [rsp+1A0h+phToken], rax; phToken
0x18001e867  mov     rcx, rdi; lpszUsername
0x18001e86a  mov     [rsp+1A0h+dwLogonProvider], 0; dwLogonProvider
0x18001e872  call    cs:__imp_LogonUserExW
0x18001e878  test    eax, eax
0x18001e87a  jnz     short loc_18001E88E
0x18001e87c  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001e881  mov     ebx, eax
0x18001e883  test    eax, eax
0x18001e885  jz      short loc_18001E88E
0x18001e887  mov     edx, 261C019Ah
0x18001e88c  jmp     short loc_18001E8AA
0x18001e88e  mov     rcx, [rsp+1A0h+hObject]; hToken
0x18001e893  call    cs:__imp_ImpersonateLoggedOnUser
0x18001e899  test    eax, eax
0x18001e89b  jnz     short loc_18001E8D6
0x18001e89d  call    cs:__imp_?myHGetLastError@@YAJXZ; myHGetLastError(void)
0x18001e8a3  mov     ebx, eax
0x18001e8a5  mov     edx, 2621019Ah
0x18001e8aa  mov     r8d, eax
0x18001e8ad  mov     rcx, rdi
0x18001e8b0  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18001e8b6  call    cs:__imp_RevertToSelf
0x18001e8bc  test    eax, eax
0x18001e8be  jnz     loc_18001E76F
0x18001e8c4  call    cs:__imp_?myHGetLastError@@YAJXZ; myHGetLastError(void)
0x18001e8ca  mov     edx, eax
0x18001e8cc  mov     ecx, 262C019Ah
0x18001e8d1  jmp     loc_18001E769
0x18001e8d6  xor     ebx, ebx
0x18001e8d8  jmp     loc_18001E76F
```
