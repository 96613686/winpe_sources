# IsUserAnInteractiveUser(void *)

- ea: `0x180088590`
- end: `0x1800887b9`
- name: `?IsUserAnInteractiveUser@@YAHPEAX@Z`
- size: `553`
- prototype: `__int64 __fastcall(HANDLE hExistingToken)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180071890`

## callees

- `0x180075ec0`
- `0x18007d320`
- `0x180088590`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800886c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800886f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008872c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008875d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800886c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800886f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008872c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008875d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088780`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088780`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800885fb`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800885fb`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180088627`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180088627`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800886a6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800886a6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18008878f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18008878f`

## string_xrefs

- `0x18008864e`: `IsUserAnInteractiveUser: DuplicateTokenEx failed with error %d`
- `0x18008867a`: `IsUserAnInteractiveUser: DuplicateTokenEx failed with error %d`
- `0x1800886ce`: `IsUserAnInteractiveUser: CheckTokenMembership failed for InteractiveSid with error %d`
- `0x1800886ff`: `IsUserAnInteractiveUser: CheckTokenMembership failed for InteractiveSid with error %d`
- `0x180088732`: `IsUserAnInteractiveUser: AllocateAndInitializeSid failed for InteractiveSid with error %d`
- `0x180088763`: `IsUserAnInteractiveUser: AllocateAndInitializeSid failed for InteractiveSid with error %d`

## pseudocode

```c
__int64 __fastcall IsUserAnInteractiveUser(HANDLE hExistingToken)
{
  void (*v2)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD LastError; // eax
  DWORD v4; // eax
  void (*v5)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v6; // eax
  DWORD v7; // eax
  void (*v8)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v9; // eax
  DWORD v10; // eax
  WINBOOL IsMember; // [rsp+68h] [rbp+27h] BYREF
  void *phNewToken; // [rsp+70h] [rbp+2Fh] BYREF
  PSID SidToCheck; // [rsp+78h] [rbp+37h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+3Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  IsMember = 0;
  SidToCheck = 0;
  phNewToken = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( !DuplicateTokenEx(hExistingToken, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v2 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          LastError = GetLastError();
          v2(2u, L"IsUserAnInteractiveUser: DuplicateTokenEx failed with error %d", LastError);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v4 = GetLastError();
          RedirectDebugMsg(2u, L"IsUserAnInteractiveUser: DuplicateTokenEx failed with error %d", v4);
        }
      }
      IsMember = 0;
      phNewToken = 0;
      goto LABEL_26;
    }
    if ( !CheckTokenMembership(phNewToken, SidToCheck, &IsMember) )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v5 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v6 = GetLastError();
          v5(2u, L"IsUserAnInteractiveUser: CheckTokenMembership failed for InteractiveSid with error %d", v6);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v7 = GetLastError();
          RedirectDebugMsg(
            2u,
            L"IsUserAnInteractiveUser: CheckTokenMembership failed for InteractiveSid with error %d",
            v7);
        }
      }
      IsMember = 0;
    }
  }
  else if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v8 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v9 = GetLastError();
      v8(2u, L"IsUserAnInteractiveUser: AllocateAndInitializeSid failed for InteractiveSid with error %d", v9);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v10 = GetLastError();
      RedirectDebugMsg(
        2u,
        L"IsUserAnInteractiveUser: AllocateAndInitializeSid failed for InteractiveSid with error %d",
        v10);
    }
  }
  if ( phNewToken )
    CloseHandle(phNewToken);
LABEL_26:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x180088590  mov     r11, rsp
0x180088593  mov     [r11+10h], rsi
0x180088597  mov     [r11+18h], rdi
0x18008859b  push    rbp
0x18008859c  lea     rbp, [r11-5Fh]
0x1800885a0  sub     rsp, 90h
0x1800885a7  mov     rax, cs:__security_cookie
0x1800885ae  xor     rax, rsp
0x1800885b1  mov     [rbp+57h+var_10], rax
0x1800885b5  xor     esi, esi
0x1800885b7  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800885bd  lea     rax, [rbp+57h+SidToCheck]
0x1800885c1  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x1800885c4  mov     [r11-48h], rax
0x1800885c8  mov     rdi, rcx
0x1800885cb  mov     [rsp+90h+nSubAuthority7], esi; nSubAuthority7
0x1800885cf  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800885d3  mov     [rsp+90h+nSubAuthority6], esi; nSubAuthority6
0x1800885d7  lea     r8d, [rsi+4]; nSubAuthority0
0x1800885db  mov     [rsp+90h+nSubAuthority5], esi; nSubAuthority5
0x1800885df  xor     r9d, r9d; nSubAuthority1
0x1800885e2  mov     [rsp+90h+nSubAuthority4], esi; nSubAuthority4
0x1800885e6  mov     dl, 1; nSubAuthorityCount
0x1800885e8  mov     [rsp+90h+nSubAuthority3], esi; nSubAuthority3
0x1800885ec  mov     [rsp+90h+nSubAuthority2], esi; nSubAuthority2
0x1800885f0  mov     [rbp+57h+IsMember], esi
0x1800885f3  mov     [rbp+57h+SidToCheck], rsi
0x1800885f7  mov     [rbp+57h+phNewToken], rsi
0x1800885fb  call    cs:__imp_AllocateAndInitializeSid
0x180088601  test    eax, eax
0x180088603  jz      loc_180088718
0x180088609  lea     rax, [rbp+57h+phNewToken]
0x18008860d  xor     r8d, r8d; lpTokenAttributes
0x180088610  mov     qword ptr [rsp+90h+nSubAuthority3], rax; phNewToken
0x180088615  lea     r9d, [rsi+2]; ImpersonationLevel
0x180088619  lea     edx, [rsi+0Ch]; dwDesiredAccess
0x18008861c  mov     [rsp+90h+nSubAuthority2], 2; TokenType
0x180088624  mov     rcx, rdi; hExistingToken
0x180088627  call    cs:__imp_DuplicateTokenEx
0x18008862d  test    eax, eax
0x18008862f  jnz     short loc_18008869A
0x180088631  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180088637  jz      short loc_18008868E
0x180088639  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180088640  test    rdi, rdi
0x180088643  jz      short loc_180088662
0x180088645  call    cs:__imp_GetLastError
0x18008864b  mov     r8d, eax
0x18008864e  lea     rdx, aIsuseranintera; "IsUserAnInteractiveUser: DuplicateToken"...
0x180088655  mov     rax, rdi
0x180088658  lea     ecx, [rsi+2]
0x18008865b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088660  jmp     short loc_18008868E
0x180088662  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180088669  jz      short loc_18008868E
0x18008866b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180088672  jz      short loc_18008868E
0x180088674  call    cs:__imp_GetLastError
0x18008867a  lea     rdx, aIsuseranintera; "IsUserAnInteractiveUser: DuplicateToken"...
0x180088681  mov     ecx, 2; unsigned int
0x180088686  mov     r8d, eax
0x180088689  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18008868e  mov     [rbp+57h+IsMember], esi
0x180088691  mov     [rbp+57h+phNewToken], rsi
0x180088695  jmp     loc_180088786
0x18008869a  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18008869e  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800886a2  mov     rcx, [rbp+57h+phNewToken]; TokenHandle
0x1800886a6  call    cs:__imp_CheckTokenMembership
0x1800886ac  test    eax, eax
0x1800886ae  jnz     loc_180088777
0x1800886b4  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800886ba  jz      short loc_180088713
0x1800886bc  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800886c3  test    rdi, rdi
0x1800886c6  jz      short loc_1800886E7
0x1800886c8  call    cs:__imp_GetLastError
0x1800886ce  lea     rdx, aIsuseranintera_1; "IsUserAnInteractiveUser: CheckTokenMemb"...
0x1800886d5  mov     ecx, 2
0x1800886da  mov     r8d, eax
0x1800886dd  mov     rax, rdi
0x1800886e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800886e5  jmp     short loc_180088713
0x1800886e7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800886ee  jz      short loc_180088713
0x1800886f0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800886f7  jz      short loc_180088713
0x1800886f9  call    cs:__imp_GetLastError
0x1800886ff  lea     rdx, aIsuseranintera_1; "IsUserAnInteractiveUser: CheckTokenMemb"...
0x180088706  mov     ecx, 2; unsigned int
0x18008870b  mov     r8d, eax
0x18008870e  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180088713  mov     [rbp+57h+IsMember], esi
0x180088716  jmp     short loc_180088777
0x180088718  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18008871e  jz      short loc_180088777
0x180088720  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180088727  test    rdi, rdi
0x18008872a  jz      short loc_18008874B
0x18008872c  call    cs:__imp_GetLastError
0x180088732  lea     rdx, aIsuseranintera_0; "IsUserAnInteractiveUser: AllocateAndIni"...
0x180088739  mov     ecx, 2
0x18008873e  mov     r8d, eax
0x180088741  mov     rax, rdi
0x180088744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088749  jmp     short loc_180088777
0x18008874b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180088752  jz      short loc_180088777
0x180088754  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18008875b  jz      short loc_180088777
0x18008875d  call    cs:__imp_GetLastError
0x180088763  lea     rdx, aIsuseranintera_0; "IsUserAnInteractiveUser: AllocateAndIni"...
0x18008876a  mov     ecx, 2; unsigned int
0x18008876f  mov     r8d, eax
0x180088772  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180088777  mov     rcx, [rbp+57h+phNewToken]; hObject
0x18008877b  test    rcx, rcx
0x18008877e  jz      short loc_180088786
0x180088780  call    cs:__imp_CloseHandle
0x180088786  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18008878a  test    rcx, rcx
0x18008878d  jz      short loc_180088795
0x18008878f  call    cs:__imp_FreeSid
0x180088795  mov     eax, [rbp+57h+IsMember]
0x180088798  mov     rcx, [rbp+57h+var_10]
0x18008879c  xor     rcx, rsp; StackCookie
0x18008879f  call    __security_check_cookie
0x1800887a4  lea     r11, [rsp+90h+var_s0]
0x1800887ac  mov     rsi, [r11+18h]
0x1800887b0  mov     rdi, [r11+20h]
0x1800887b4  mov     rsp, r11
0x1800887b7  pop     rbp
0x1800887b8  retn
```
