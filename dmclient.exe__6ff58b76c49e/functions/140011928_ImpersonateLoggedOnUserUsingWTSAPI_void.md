# ImpersonateLoggedOnUserUsingWTSAPI(void * *)

- ea: `0x140011928`
- end: `0x140011b80`
- name: `?ImpersonateLoggedOnUserUsingWTSAPI@@YAJPEAPEAX@Z`
- size: `600`
- prototype: `__int64 __fastcall(PHANDLE phToken)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140011250`

## callees

- `0x140001008`
- `0x140001b9c`
- `0x140002fe4`
- `0x140010e70`
- `0x140011928`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400119c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011a64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400119c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011a64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011aab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011b46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011b46`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140011aa1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140011aa1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x140011a5a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x140011a5a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x1400119b7`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x1400119b7`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x140011b70`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x140011b70`

## string_xrefs

- `0x140011ace`: `ImpersonateLoggedOnUser failed`
- `0x140011981`: `Attempting to impersonate with WTS APIs`

## pseudocode

```c
__int64 __fastcall ImpersonateLoggedOnUserUsingWTSAPI(PHANDLE phToken)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  signed int LastError; // eax
  unsigned int v7; // ebx
  const char *v8; // rax
  __int16 *v9; // rdx
  int v10; // edx
  DWORD v11; // r10d
  int v12; // r11d
  DWORD v13; // r8d
  bool v14; // zf
  DWORD v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  const char *v18; // [rsp+30h] [rbp-10h] BYREF
  DWORD NumberOfEntries; // [rsp+60h] [rbp+20h] BYREF
  DWORD pLevel; // [rsp+68h] [rbp+28h] BYREF
  const char *v21; // [rsp+70h] [rbp+30h] BYREF
  PWTS_SESSION_INFO_1W ppSessionInfo; // [rsp+78h] [rbp+38h] BYREF

  ppSessionInfo = 0;
  pLevel = 1;
  NumberOfEntries = 0;
  if ( !phToken )
    return 2147942487LL;
  if ( !(unsigned __int8)IsWTSFreeMemoryExWPresent() || !(unsigned __int8)IsWTSFreeMemoryExWPresent() )
  {
    v7 = -2147024846;
    if ( (unsigned int)dword_140027000 <= 5 )
      goto LABEL_34;
    LODWORD(v21) = -2147024846;
    v8 = "WTS APIs not present.";
    v9 = (__int16 *)byte_140022355;
LABEL_33:
    v18 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v3,
      (__int64)v9,
      v4,
      v5,
      (const unsigned __int16 **)&v18,
      (__int64)&v21);
LABEL_34:
    if ( (char *)*phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(*phToken);
      *phToken = (void *)-1LL;
    }
    goto LABEL_36;
  }
  if ( (unsigned int)dword_140027000 > 5 )
  {
    v21 = "Attempting to impersonate with WTS APIs";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v3,
      (__int64)byte_1400221EB,
      v4,
      v5,
      (const unsigned __int16 **)&v21);
  }
  if ( !WTSEnumerateSessionsExW(0, &pLevel, 0, &ppSessionInfo, &NumberOfEntries) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_140027000 <= 5 )
      goto LABEL_34;
    LODWORD(v21) = v7;
    v8 = "WTSEnumerateSessionsExW failed";
    v9 = &word_1400223FE;
    goto LABEL_33;
  }
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( !NumberOfEntries )
    goto LABEL_30;
  do
  {
    if ( ppSessionInfo[v13].State == WTSActive )
    {
      v14 = v12 == 0;
      v15 = v13;
      v12 = 1;
      if ( !v14 )
        v15 = v11;
      ++v10;
      v11 = v15;
    }
    ++v13;
  }
  while ( v13 < NumberOfEntries );
  if ( v10 != 1 )
  {
LABEL_30:
    v7 = v10 != 0 ? -2147023604 : -2147023584;
    goto LABEL_34;
  }
  if ( !WTSQueryUserToken(ppSessionInfo[v11].SessionId, phToken) )
  {
    v16 = GetLastError();
    v7 = v16;
    if ( v16 > 0 )
      v7 = (unsigned __int16)v16 | 0x80070000;
    if ( (unsigned int)dword_140027000 <= 5 )
      goto LABEL_34;
    LODWORD(v21) = v7;
    v8 = "WTSEnumerateSessionsExW failed";
    v9 = word_1400224E2;
    goto LABEL_33;
  }
  if ( !ImpersonateLoggedOnUser(*phToken) )
  {
    v17 = GetLastError();
    v7 = v17;
    if ( v17 > 0 )
      v7 = (unsigned __int16)v17 | 0x80070000;
    if ( (unsigned int)dword_140027000 <= 5 )
      goto LABEL_34;
    LODWORD(v21) = v7;
    v8 = "ImpersonateLoggedOnUser failed";
    v9 = &word_140022496;
    goto LABEL_33;
  }
  v7 = 0;
  DumpSIDString((int *)*phToken);
LABEL_36:
  if ( ppSessionInfo )
  {
    if ( (unsigned __int8)IsWTSFreeMemoryExWPresent() )
      WTSFreeMemoryExW(WTSTypeSessionInfoLevel1, ppSessionInfo, NumberOfEntries);
  }
  return v7;
}

```

## disassembly

```asm
0x140011928  push    rbp
0x14001192a  push    rbx
0x14001192b  push    rdi
0x14001192c  mov     rbp, rsp
0x14001192f  sub     rsp, 40h
0x140011933  mov     [rbp+ppSessionInfo], 0
0x14001193b  mov     ebx, 1
0x140011940  mov     [rbp+pLevel], ebx
0x140011943  mov     rdi, rcx
0x140011946  mov     [rbp+NumberOfEntries], 0
0x14001194d  test    rcx, rcx
0x140011950  jnz     short loc_14001195C
0x140011952  mov     eax, 80070057h
0x140011957  jmp     loc_140011B78
0x14001195c  call    IsWTSFreeMemoryExWPresent
0x140011961  test    al, al
0x140011963  jz      loc_140011AF9
0x140011969  call    IsWTSFreeMemoryExWPresent
0x14001196e  test    al, al
0x140011970  jz      loc_140011AF9
0x140011976  mov     eax, cs:dword_140027000
0x14001197c  cmp     eax, 5
0x14001197f  jbe     short loc_1400119A1
0x140011981  lea     rax, aAttemptingToIm; "Attempting to impersonate with WTS APIs"
0x140011988  mov     [rbp+arg_10], rax
0x14001198c  lea     rdx, byte_1400221EB
0x140011993  lea     rax, [rbp+arg_10]
0x140011997  mov     [rsp+40h+pCount], rax
0x14001199c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1400119a1  lea     rax, [rbp+NumberOfEntries]
0x1400119a5  xor     r8d, r8d; Filter
0x1400119a8  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x1400119ac  mov     [rsp+40h+pCount], rax; pCount
0x1400119b1  lea     rdx, [rbp+pLevel]; pLevel
0x1400119b5  xor     ecx, ecx; hServer
0x1400119b7  call    cs:__imp_WTSEnumerateSessionsExW
0x1400119bd  test    eax, eax
0x1400119bf  jnz     short loc_1400119FB
0x1400119c1  call    cs:__imp_GetLastError
0x1400119c7  mov     ebx, eax
0x1400119c9  test    eax, eax
0x1400119cb  jle     short loc_1400119D6
0x1400119cd  movzx   ebx, ax
0x1400119d0  or      ebx, 80070000h
0x1400119d6  mov     eax, cs:dword_140027000
0x1400119dc  cmp     eax, 5
0x1400119df  jbe     loc_140011B39
0x1400119e5  mov     dword ptr [rbp+arg_10], ebx
0x1400119e8  lea     rax, aWtsenumeratese_0; "WTSEnumerateSessionsExW failed"
0x1400119ef  lea     rdx, word_1400223FE
0x1400119f6  jmp     loc_140011B1E
0x1400119fb  mov     r9d, [rbp+NumberOfEntries]
0x1400119ff  xor     edx, edx
0x140011a01  xor     r10d, r10d
0x140011a04  xor     r11d, r11d
0x140011a07  xor     r8d, r8d
0x140011a0a  test    r9d, r9d
0x140011a0d  jz      loc_140011AEA
0x140011a13  mov     eax, r8d
0x140011a16  imul    rcx, rax, 38h ; '8'
0x140011a1a  mov     rax, [rbp+ppSessionInfo]
0x140011a1e  cmp     dword ptr [rcx+rax+4], 0
0x140011a23  jnz     short loc_140011A37
0x140011a25  test    r11d, r11d
0x140011a28  mov     eax, r8d
0x140011a2b  mov     r11d, ebx
0x140011a2e  cmovnz  eax, r10d
0x140011a32  add     edx, ebx
0x140011a34  mov     r10d, eax
0x140011a37  add     r8d, ebx
0x140011a3a  cmp     r8d, r9d
0x140011a3d  jb      short loc_140011A13
0x140011a3f  cmp     edx, ebx
0x140011a41  jnz     loc_140011AEA
0x140011a47  mov     rcx, [rbp+ppSessionInfo]
0x140011a4b  mov     rdx, rdi; phToken
0x140011a4e  mov     eax, r10d
0x140011a51  imul    r8, rax, 38h ; '8'
0x140011a55  mov     ecx, [r8+rcx+8]; SessionId
0x140011a5a  call    cs:__imp_WTSQueryUserToken
0x140011a60  test    eax, eax
0x140011a62  jnz     short loc_140011A9E
0x140011a64  call    cs:__imp_GetLastError
0x140011a6a  mov     ebx, eax
0x140011a6c  test    eax, eax
0x140011a6e  jle     short loc_140011A79
0x140011a70  movzx   ebx, ax
0x140011a73  or      ebx, 80070000h
0x140011a79  mov     eax, cs:dword_140027000
0x140011a7f  cmp     eax, 5
0x140011a82  jbe     loc_140011B39
0x140011a88  mov     dword ptr [rbp+arg_10], ebx
0x140011a8b  lea     rax, aWtsenumeratese_0; "WTSEnumerateSessionsExW failed"
0x140011a92  lea     rdx, word_1400224E2
0x140011a99  jmp     loc_140011B1E
0x140011a9e  mov     rcx, [rdi]; hToken
0x140011aa1  call    cs:__imp_ImpersonateLoggedOnUser
0x140011aa7  test    eax, eax
0x140011aa9  jnz     short loc_140011ADE
0x140011aab  call    cs:__imp_GetLastError
0x140011ab1  mov     ebx, eax
0x140011ab3  test    eax, eax
0x140011ab5  jle     short loc_140011AC0
0x140011ab7  movzx   ebx, ax
0x140011aba  or      ebx, 80070000h
0x140011ac0  mov     eax, cs:dword_140027000
0x140011ac6  cmp     eax, 5
0x140011ac9  jbe     short loc_140011B39
0x140011acb  mov     dword ptr [rbp+arg_10], ebx
0x140011ace  lea     rax, aImpersonatelog; "ImpersonateLoggedOnUser failed"
0x140011ad5  lea     rdx, word_140022496
0x140011adc  jmp     short loc_140011B1E
0x140011ade  mov     rcx, [rdi]; TokenHandle
0x140011ae1  xor     ebx, ebx
0x140011ae3  call    ?DumpSIDString@@YAXPEAX@Z; DumpSIDString(void *)
0x140011ae8  jmp     short loc_140011B53
0x140011aea  neg     edx
0x140011aec  sbb     ebx, ebx
0x140011aee  and     ebx, 0FFFFFFECh
0x140011af1  add     ebx, 80070520h
0x140011af7  jmp     short loc_140011B39
0x140011af9  mov     eax, cs:dword_140027000
0x140011aff  mov     ebx, 80070032h
0x140011b04  cmp     eax, 5
0x140011b07  jbe     short loc_140011B39
0x140011b09  mov     dword ptr [rbp+arg_10], 80070032h
0x140011b10  lea     rax, aWtsApisNotPres; "WTS APIs not present."
0x140011b17  lea     rdx, byte_140022355
0x140011b1e  mov     [rbp+var_10], rax
0x140011b22  lea     rax, [rbp+arg_10]
0x140011b26  mov     [rsp+40h+var_18], rax
0x140011b2b  lea     rax, [rbp+var_10]
0x140011b2f  mov     [rsp+40h+pCount], rax
0x140011b34  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140011b39  mov     rcx, [rdi]; hObject
0x140011b3c  lea     rax, [rcx-1]
0x140011b40  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140011b44  ja      short loc_140011B53
0x140011b46  call    cs:__imp_CloseHandle
0x140011b4c  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x140011b53  cmp     [rbp+ppSessionInfo], 0
0x140011b58  jz      short loc_140011B76
0x140011b5a  call    IsWTSFreeMemoryExWPresent
0x140011b5f  test    al, al
0x140011b61  jz      short loc_140011B76
0x140011b63  mov     r8d, [rbp+NumberOfEntries]; NumberOfEntries
0x140011b67  mov     ecx, 2; WTSTypeClass
0x140011b6c  mov     rdx, [rbp+ppSessionInfo]; pMemory
0x140011b70  call    cs:__imp_WTSFreeMemoryExW
0x140011b76  mov     eax, ebx
0x140011b78  add     rsp, 40h
0x140011b7c  pop     rdi
0x140011b7d  pop     rbx
0x140011b7e  pop     rbp
0x140011b7f  retn
```
