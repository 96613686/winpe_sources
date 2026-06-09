# ImpersonateLoggedOnUserUsingWTSAPI(void * *)

- ea: `0x140012120`
- end: `0x1400123a9`
- name: `?ImpersonateLoggedOnUserUsingWTSAPI@@YAJPEAPEAX@Z`
- size: `649`
- prototype: `__int64 __fastcall(PHANDLE phToken)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400119f0`

## callees

- `0x140001008`
- `0x140001bb4`
- `0x140003024`
- `0x140011580`
- `0x140012120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400121bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001226e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400122c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400121bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001226e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400122c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012362`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012362`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400122b1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400122b1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x14001225e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x14001225e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x1400121af`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x1400121af`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x140012392`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x140012392`

## string_xrefs

- `0x1400122ea`: `ImpersonateLoggedOnUser failed`
- `0x140012179`: `Attempting to impersonate with WTS APIs`

## pseudocode

```c
__int64 __fastcall ImpersonateLoggedOnUserUsingWTSAPI(PHANDLE phToken)
{
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
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
    if ( (unsigned int)dword_140028000 <= 5 )
      goto LABEL_34;
    LODWORD(v21) = -2147024846;
    v8 = "WTS APIs not present.";
    v9 = (__int16 *)byte_14002335D;
LABEL_33:
    v18 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v3,
      (_DWORD)v9,
      v4,
      v5,
      (__int64)&v18,
      (__int64)&v21);
LABEL_34:
    if ( (char *)*phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(*phToken);
      *phToken = (void *)-1LL;
    }
    goto LABEL_36;
  }
  if ( (unsigned int)dword_140028000 > 5 )
  {
    v21 = "Attempting to impersonate with WTS APIs";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v3,
      (unsigned int)byte_1400231F3,
      v4,
      v5,
      (__int64)&v21);
  }
  if ( !WTSEnumerateSessionsExW(0, &pLevel, 0, &ppSessionInfo, &NumberOfEntries) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_140028000 <= 5 )
      goto LABEL_34;
    LODWORD(v21) = v7;
    v8 = "WTSEnumerateSessionsExW failed";
    v9 = &word_140023406;
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
    if ( (unsigned int)dword_140028000 <= 5 )
      goto LABEL_34;
    LODWORD(v21) = v7;
    v8 = "WTSEnumerateSessionsExW failed";
    v9 = word_1400234EA;
    goto LABEL_33;
  }
  if ( !ImpersonateLoggedOnUser(*phToken) )
  {
    v17 = GetLastError();
    v7 = v17;
    if ( v17 > 0 )
      v7 = (unsigned __int16)v17 | 0x80070000;
    if ( (unsigned int)dword_140028000 <= 5 )
      goto LABEL_34;
    LODWORD(v21) = v7;
    v8 = "ImpersonateLoggedOnUser failed";
    v9 = &word_14002349E;
    goto LABEL_33;
  }
  v7 = 0;
  DumpSIDString((WCHAR *)*phToken);
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
0x140012120  push    rbp
0x140012122  push    rbx
0x140012123  push    rdi
0x140012124  mov     rbp, rsp
0x140012127  sub     rsp, 40h
0x14001212b  mov     [rbp+ppSessionInfo], 0
0x140012133  mov     ebx, 1
0x140012138  mov     [rbp+pLevel], ebx
0x14001213b  mov     rdi, rcx
0x14001213e  mov     [rbp+NumberOfEntries], 0
0x140012145  test    rcx, rcx
0x140012148  jnz     short loc_140012154
0x14001214a  mov     eax, 80070057h
0x14001214f  jmp     loc_1400123A0
0x140012154  call    IsWTSFreeMemoryExWPresent
0x140012159  test    al, al
0x14001215b  jz      loc_140012315
0x140012161  call    IsWTSFreeMemoryExWPresent
0x140012166  test    al, al
0x140012168  jz      loc_140012315
0x14001216e  mov     eax, cs:dword_140028000
0x140012174  cmp     eax, 5
0x140012177  jbe     short loc_140012199
0x140012179  lea     rax, aAttemptingToIm; "Attempting to impersonate with WTS APIs"
0x140012180  mov     [rbp+arg_10], rax
0x140012184  lea     rdx, byte_1400231F3
0x14001218b  lea     rax, [rbp+arg_10]
0x14001218f  mov     [rsp+40h+pCount], rax
0x140012194  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140012199  lea     rax, [rbp+NumberOfEntries]
0x14001219d  xor     r8d, r8d; Filter
0x1400121a0  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x1400121a4  mov     [rsp+40h+pCount], rax; pCount
0x1400121a9  lea     rdx, [rbp+pLevel]; pLevel
0x1400121ad  xor     ecx, ecx; hServer
0x1400121af  call    cs:__imp_WTSEnumerateSessionsExW
0x1400121b6  nop     dword ptr [rax+rax+00h]
0x1400121bb  test    eax, eax
0x1400121bd  jnz     short loc_1400121FF
0x1400121bf  call    cs:__imp_GetLastError
0x1400121c6  nop     dword ptr [rax+rax+00h]
0x1400121cb  mov     ebx, eax
0x1400121cd  test    eax, eax
0x1400121cf  jle     short loc_1400121DA
0x1400121d1  movzx   ebx, ax
0x1400121d4  or      ebx, 80070000h
0x1400121da  mov     eax, cs:dword_140028000
0x1400121e0  cmp     eax, 5
0x1400121e3  jbe     loc_140012355
0x1400121e9  mov     dword ptr [rbp+arg_10], ebx
0x1400121ec  lea     rax, aWtsenumeratese_0; "WTSEnumerateSessionsExW failed"
0x1400121f3  lea     rdx, word_140023406
0x1400121fa  jmp     loc_14001233A
0x1400121ff  mov     r9d, [rbp+NumberOfEntries]
0x140012203  xor     edx, edx
0x140012205  xor     r10d, r10d
0x140012208  xor     r11d, r11d
0x14001220b  xor     r8d, r8d
0x14001220e  test    r9d, r9d
0x140012211  jz      loc_140012306
0x140012217  mov     eax, r8d
0x14001221a  imul    rcx, rax, 38h ; '8'
0x14001221e  mov     rax, [rbp+ppSessionInfo]
0x140012222  cmp     dword ptr [rcx+rax+4], 0
0x140012227  jnz     short loc_14001223B
0x140012229  test    r11d, r11d
0x14001222c  mov     eax, r8d
0x14001222f  mov     r11d, ebx
0x140012232  cmovnz  eax, r10d
0x140012236  add     edx, ebx
0x140012238  mov     r10d, eax
0x14001223b  add     r8d, ebx
0x14001223e  cmp     r8d, r9d
0x140012241  jb      short loc_140012217
0x140012243  cmp     edx, ebx
0x140012245  jnz     loc_140012306
0x14001224b  mov     rcx, [rbp+ppSessionInfo]
0x14001224f  mov     rdx, rdi; phToken
0x140012252  mov     eax, r10d
0x140012255  imul    r8, rax, 38h ; '8'
0x140012259  mov     ecx, [r8+rcx+8]; SessionId
0x14001225e  call    cs:__imp_WTSQueryUserToken
0x140012265  nop     dword ptr [rax+rax+00h]
0x14001226a  test    eax, eax
0x14001226c  jnz     short loc_1400122AE
0x14001226e  call    cs:__imp_GetLastError
0x140012275  nop     dword ptr [rax+rax+00h]
0x14001227a  mov     ebx, eax
0x14001227c  test    eax, eax
0x14001227e  jle     short loc_140012289
0x140012280  movzx   ebx, ax
0x140012283  or      ebx, 80070000h
0x140012289  mov     eax, cs:dword_140028000
0x14001228f  cmp     eax, 5
0x140012292  jbe     loc_140012355
0x140012298  mov     dword ptr [rbp+arg_10], ebx
0x14001229b  lea     rax, aWtsenumeratese_0; "WTSEnumerateSessionsExW failed"
0x1400122a2  lea     rdx, word_1400234EA
0x1400122a9  jmp     loc_14001233A
0x1400122ae  mov     rcx, [rdi]; hToken
0x1400122b1  call    cs:__imp_ImpersonateLoggedOnUser
0x1400122b8  nop     dword ptr [rax+rax+00h]
0x1400122bd  test    eax, eax
0x1400122bf  jnz     short loc_1400122FA
0x1400122c1  call    cs:__imp_GetLastError
0x1400122c8  nop     dword ptr [rax+rax+00h]
0x1400122cd  mov     ebx, eax
0x1400122cf  test    eax, eax
0x1400122d1  jle     short loc_1400122DC
0x1400122d3  movzx   ebx, ax
0x1400122d6  or      ebx, 80070000h
0x1400122dc  mov     eax, cs:dword_140028000
0x1400122e2  cmp     eax, 5
0x1400122e5  jbe     short loc_140012355
0x1400122e7  mov     dword ptr [rbp+arg_10], ebx
0x1400122ea  lea     rax, aImpersonatelog; "ImpersonateLoggedOnUser failed"
0x1400122f1  lea     rdx, word_14002349E
0x1400122f8  jmp     short loc_14001233A
0x1400122fa  mov     rcx, [rdi]; TokenHandle
0x1400122fd  xor     ebx, ebx
0x1400122ff  call    ?DumpSIDString@@YAXPEAX@Z; DumpSIDString(void *)
0x140012304  jmp     short loc_140012375
0x140012306  neg     edx
0x140012308  sbb     ebx, ebx
0x14001230a  and     ebx, 0FFFFFFECh
0x14001230d  add     ebx, 80070520h
0x140012313  jmp     short loc_140012355
0x140012315  mov     eax, cs:dword_140028000
0x14001231b  mov     ebx, 80070032h
0x140012320  cmp     eax, 5
0x140012323  jbe     short loc_140012355
0x140012325  mov     dword ptr [rbp+arg_10], 80070032h
0x14001232c  lea     rax, aWtsApisNotPres; "WTS APIs not present."
0x140012333  lea     rdx, byte_14002335D
0x14001233a  mov     [rbp+var_10], rax
0x14001233e  lea     rax, [rbp+arg_10]
0x140012342  mov     [rsp+40h+var_18], rax
0x140012347  lea     rax, [rbp+var_10]
0x14001234b  mov     [rsp+40h+pCount], rax
0x140012350  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140012355  mov     rcx, [rdi]; hObject
0x140012358  lea     rax, [rcx-1]
0x14001235c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140012360  ja      short loc_140012375
0x140012362  call    cs:__imp_CloseHandle
0x140012369  nop     dword ptr [rax+rax+00h]
0x14001236e  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x140012375  cmp     [rbp+ppSessionInfo], 0
0x14001237a  jz      short loc_14001239E
0x14001237c  call    IsWTSFreeMemoryExWPresent
0x140012381  test    al, al
0x140012383  jz      short loc_14001239E
0x140012385  mov     r8d, [rbp+NumberOfEntries]; NumberOfEntries
0x140012389  mov     ecx, 2; WTSTypeClass
0x14001238e  mov     rdx, [rbp+ppSessionInfo]; pMemory
0x140012392  call    cs:__imp_WTSFreeMemoryExW
0x140012399  nop     dword ptr [rax+rax+00h]
0x14001239e  mov     eax, ebx
0x1400123a0  add     rsp, 40h
0x1400123a4  pop     rdi
0x1400123a5  pop     rbx
0x1400123a6  pop     rbp
0x1400123a7  retn
```
