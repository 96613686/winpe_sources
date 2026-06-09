# myImpersonateSid(void *,ushort const *)

- ea: `0x180018620`
- end: `0x180018899`
- name: `?myImpersonateSid@@YAJPEAXPEBG@Z`
- size: `633`
- prototype: `__int64 __fastcall(PSID Sid, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800185b4`

## callees

- `0x180008400`
- `0x180008610`
- `0x180012450`
- `0x1800175e0`
- `0x180018060`
- `0x18001840c`
- `0x180018620`
- `0x1800382c0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800186ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800186ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800186a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800186a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018742`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001874b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018754`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018742`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001874b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018754`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800187a8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800187a8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018873`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018873`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180018786`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001884f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180018786`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001884f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018737`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018737`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x18001882e`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x18001882e`

## string_xrefs

- `0x18001869e`: `kernel32.dll`

## pseudocode

```c
__int64 __fastcall myImpersonateSid(PSID Sid, const unsigned __int16 *a2)
{
  WCHAR *v2; // rsi
  unsigned __int16 *v3; // rdi
  unsigned int SidFromRid; // eax
  unsigned int v6; // ebx
  int v7; // edx
  unsigned int v8; // ecx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v11; // rbx
  void *ProcessTokenIfSidMatch; // rax
  int AccountNameFromSID; // eax
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
  v6 = SidFromRid;
  if ( SidFromRid )
  {
    v7 = SidFromRid;
    v8 = 635634074;
LABEL_12:
    CSPrintErrorLineFile(v8, v7);
    goto LABEL_13;
  }
  ProcAddress = (FARPROC)qword_1800C4CB0;
  v17 = 256;
  if ( !qword_1800C4CB0
    && ((ModuleHandleW = GetModuleHandleW(L"kernel32.dll")) == 0
     || (ProcAddress = GetProcAddress(ModuleHandleW, "K32EnumProcesses"), (qword_1800C4CB0 = (__int64)ProcAddress) == 0))
    || !((unsigned int (__fastcall *)(DWORD *, __int64, unsigned int *))ProcAddress)(dwProcessId, 256, &v17) )
  {
    v6 = myHLastError();
    v7 = v6;
    v8 = 636354970;
    goto LABEL_12;
  }
  v11 = 0;
  if ( (v17 & 0xFFFFFFFC) == 0 )
  {
LABEL_11:
    v6 = -2147024891;
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
    v6 = myHLastError();
    v7 = v6;
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
  v6 = AccountNameFromSID;
  v2 = (WCHAR *)lpszDomain;
  if ( AccountNameFromSID )
  {
    CSPrintErrorLineFile(0x260C019Au, AccountNameFromSID);
    goto LABEL_27;
  }
  if ( LogonUserExW(lpszUsername, lpszDomain, 0, 5u, 0, &hObject, 0, 0, 0, 0) || (v15 = myHLastError(), (v6 = v15) == 0) )
  {
    if ( !ImpersonateLoggedOnUser(hObject) )
    {
      v15 = myHLastError();
      v6 = v15;
      v16 = 639697306;
      goto LABEL_26;
    }
LABEL_29:
    v6 = 0;
    goto LABEL_13;
  }
  v16 = 639369626;
LABEL_26:
  CSPrintErrorLineFileData2(v3, v16, v15, 0);
LABEL_27:
  if ( !RevertToSelf() )
  {
    v7 = myHLastError();
    v8 = 640418202;
    goto LABEL_12;
  }
LABEL_13:
  if ( hObject )
    CloseHandle(hObject);
  LocalFree(hMem);
  LocalFree(v3);
  LocalFree(v2);
  return v6;
}

```

## disassembly

```asm
0x180018620  mov     [rsp-8+arg_8], rbx
0x180018625  mov     [rsp-8+arg_10], rsi
0x18001862a  push    rbp
0x18001862b  push    rdi
0x18001862c  push    r14
0x18001862e  lea     rbp, [rsp-90h]
0x180018636  sub     rsp, 190h
0x18001863d  mov     rax, cs:__security_cookie
0x180018644  xor     rax, rsp
0x180018647  mov     [rbp+0A0h+var_20], rax
0x18001864e  xor     esi, esi
0x180018650  mov     [rsp+1A0h+hMem], 0
0x180018659  xor     edi, edi
0x18001865b  mov     [rsp+1A0h+lpszDomain], rsi
0x180018660  lea     rdx, [rsp+1A0h+hMem]; void **
0x180018665  mov     [rsp+1A0h+lpszUsername], rdi
0x18001866a  mov     [rsp+1A0h+hObject], rsi
0x18001866f  mov     r14, rcx
0x180018672  call    ?myGetSidFromRid@@YAJW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; myGetSidFromRid(WELL_KNOWN_SID_TYPE,void * *)
0x180018677  mov     ebx, eax
0x180018679  test    eax, eax
0x18001867b  jz      short loc_180018689
0x18001867d  mov     edx, eax
0x18001867f  mov     ecx, 25E3019Ah
0x180018684  jmp     loc_180018728
0x180018689  mov     rax, cs:qword_1800C4CB0
0x180018690  mov     ebx, 100h
0x180018695  mov     [rsp+1A0h+var_150], ebx
0x180018699  test    rax, rax
0x18001869c  jnz     short loc_1800186CC
0x18001869e  lea     rcx, ModuleName; "kernel32.dll"
0x1800186a5  call    cs:__imp_GetModuleHandleW
0x1800186ab  test    rax, rax
0x1800186ae  jz      short loc_1800186E0
0x1800186b0  lea     rdx, aK32enumprocess; "K32EnumProcesses"
0x1800186b7  mov     rcx, rax; hModule
0x1800186ba  call    cs:__imp_GetProcAddress
0x1800186c0  mov     cs:qword_1800C4CB0, rax
0x1800186c7  test    rax, rax
0x1800186ca  jz      short loc_1800186E0
0x1800186cc  lea     r8, [rsp+1A0h+var_150]
0x1800186d1  mov     edx, ebx
0x1800186d3  lea     rcx, [rbp+0A0h+dwProcessId]
0x1800186d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186dc  test    eax, eax
0x1800186de  jnz     short loc_1800186F0
0x1800186e0  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800186e5  mov     ebx, eax
0x1800186e7  mov     edx, eax
0x1800186e9  mov     ecx, 25EE019Ah
0x1800186ee  jmp     short loc_180018728
0x1800186f0  xor     ebx, ebx
0x1800186f2  test    [rsp+1A0h+var_150], 0FFFFFFFCh
0x1800186fa  jbe     short loc_18001871C
0x1800186fc  mov     rdx, [rsp+1A0h+hMem]; pSid1
0x180018701  mov     ecx, [rbp+rbx*4+0A0h+dwProcessId]; dwProcessId
0x180018705  call    ?GetProcessTokenIfSidMatch@@YAPEAXKPEAX@Z; GetProcessTokenIfSidMatch(ulong,void *)
0x18001870a  test    rax, rax
0x18001870d  jnz     short loc_180018783
0x18001870f  mov     eax, [rsp+1A0h+var_150]
0x180018713  inc     ebx
0x180018715  shr     eax, 2
0x180018718  cmp     ebx, eax
0x18001871a  jb      short loc_1800186FC
0x18001871c  mov     ebx, 80070005h
0x180018721  mov     ecx, 2600019Ah; unsigned int
0x180018726  mov     edx, ebx; int
0x180018728  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001872d  mov     rcx, [rsp+1A0h+hObject]; hObject
0x180018732  test    rcx, rcx
0x180018735  jz      short loc_18001873D
0x180018737  call    cs:__imp_CloseHandle
0x18001873d  mov     rcx, [rsp+1A0h+hMem]; hMem
0x180018742  call    cs:__imp_LocalFree
0x180018748  mov     rcx, rdi; hMem
0x18001874b  call    cs:__imp_LocalFree
0x180018751  mov     rcx, rsi; hMem
0x180018754  call    cs:__imp_LocalFree
0x18001875a  mov     eax, ebx
0x18001875c  mov     rcx, [rbp+0A0h+var_20]
0x180018763  xor     rcx, rsp; StackCookie
0x180018766  call    __security_check_cookie
0x18001876b  lea     r11, [rsp+1A0h+var_10]
0x180018773  mov     rbx, [r11+28h]
0x180018777  mov     rsi, [r11+30h]
0x18001877b  mov     rsp, r11
0x18001877e  pop     r14
0x180018780  pop     rdi
0x180018781  pop     rbp
0x180018782  retn
0x180018783  mov     rcx, rax; hToken
0x180018786  call    cs:__imp_ImpersonateLoggedOnUser
0x18001878c  test    eax, eax
0x18001878e  jnz     short loc_1800187A0
0x180018790  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180018795  mov     ebx, eax
0x180018797  mov     edx, eax
0x180018799  mov     ecx, 2605019Ah
0x18001879e  jmp     short loc_180018728
0x1800187a0  mov     rdx, [rsp+1A0h+hMem]; pSid2
0x1800187a5  mov     rcx, r14; pSid1
0x1800187a8  call    cs:__imp_EqualSid
0x1800187ae  test    eax, eax
0x1800187b0  jnz     loc_180018892
0x1800187b6  lea     r8, [rsp+1A0h+lpszDomain]; unsigned __int16 **
0x1800187bb  mov     rcx, r14; Sid
0x1800187be  lea     rdx, [rsp+1A0h+lpszUsername]; unsigned __int16 **
0x1800187c3  call    ?myGetAccountNameFromSID@@YAJPEAXPEAPEAG1@Z; myGetAccountNameFromSID(void *,ushort * *,ushort * *)
0x1800187c8  mov     rdi, [rsp+1A0h+lpszUsername]
0x1800187cd  mov     ebx, eax
0x1800187cf  mov     rsi, [rsp+1A0h+lpszDomain]
0x1800187d4  test    eax, eax
0x1800187d6  jz      short loc_1800187E9
0x1800187d8  mov     edx, eax; int
0x1800187da  mov     ecx, 260C019Ah; unsigned int
0x1800187df  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800187e4  jmp     loc_180018873
0x1800187e9  mov     [rsp+1A0h+pQuotaLimits], 0; pQuotaLimits
0x1800187f2  lea     rax, [rsp+1A0h+hObject]
0x1800187f7  mov     [rsp+1A0h+pdwProfileLength], 0; pdwProfileLength
0x180018800  mov     r9d, 5; dwLogonType
0x180018806  mov     [rsp+1A0h+ppProfileBuffer], 0; ppProfileBuffer
0x18001880f  xor     r8d, r8d; lpszPassword
0x180018812  mov     [rsp+1A0h+ppLogonSid], 0; ppLogonSid
0x18001881b  mov     rdx, rsi; lpszDomain
0x18001881e  mov     [rsp+1A0h+phToken], rax; phToken
0x180018823  mov     rcx, rdi; lpszUsername
0x180018826  mov     [rsp+1A0h+dwLogonProvider], 0; dwLogonProvider
0x18001882e  call    cs:__imp_LogonUserExW
0x180018834  test    eax, eax
0x180018836  jnz     short loc_18001884A
0x180018838  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001883d  mov     ebx, eax
0x18001883f  test    eax, eax
0x180018841  jz      short loc_18001884A
0x180018843  mov     edx, 261C019Ah
0x180018848  jmp     short loc_180018865
0x18001884a  mov     rcx, [rsp+1A0h+hObject]; hToken
0x18001884f  call    cs:__imp_ImpersonateLoggedOnUser
0x180018855  test    eax, eax
0x180018857  jnz     short loc_180018892
0x180018859  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001885e  mov     ebx, eax
0x180018860  mov     edx, 2621019Ah; unsigned int
0x180018865  xor     r9d, r9d; int
0x180018868  mov     r8d, eax; int
0x18001886b  mov     rcx, rdi; unsigned __int16 *
0x18001886e  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180018873  call    cs:__imp_RevertToSelf
0x180018879  test    eax, eax
0x18001887b  jnz     loc_18001872D
0x180018881  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180018886  mov     edx, eax
0x180018888  mov     ecx, 262C019Ah
0x18001888d  jmp     loc_180018728
0x180018892  xor     ebx, ebx
0x180018894  jmp     loc_18001872D
```
