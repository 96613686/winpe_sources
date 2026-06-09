# CSessionUserHelper::ForEachSessionUser__lambda_fc4c7cf5ddf10be52cdadf01ede06ef6___

- ea: `0x18019b404`
- end: `0x18019b6fb`
- name: `CSessionUserHelper::ForEachSessionUser__lambda_fc4c7cf5ddf10be52cdadf01ede06ef6___`
- size: `759`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18019dbd0`

## callees

- `0x18000f880`
- `0x1800f8f24`
- `0x180129d58`
- `0x18012a138`
- `0x18019b3b4`
- `0x18019b404`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019b4c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019b4c9`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18019b49a`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18019b49a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18019b544`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18019b544`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18019b4bf`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18019b4bf`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18019b449`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18019b449`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x18019b660`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x18019b660`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18019b5db`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18019b5db`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18019b56b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18019b56b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18019b4fe`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18019b693`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18019b4fe`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18019b693`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x18019b64f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x18019b64f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18019b630`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18019b6d7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18019b630`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18019b6d7`

## string_xrefs

- `0x18019b457`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`
- `0x18019b57e`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`
- `0x18019b60f`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`
- `0x18019b66e`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSessionUserHelper::ForEachSessionUser__lambda_fc4c7cf5ddf10be52cdadf01ede06ef6___(
        DWORD a1,
        __int64 a2)
{
  signed int v3; // ebx
  const char *v4; // r9
  __int64 i; // rdi
  ULONG SessionId; // esi
  WTS_CONNECTSTATE_CLASS State; // r14d
  signed int LastError; // eax
  int v10; // eax
  unsigned int v11; // edi
  DWORD j; // edi
  __int64 v13; // rsi
  unsigned int v14; // r14d
  __int64 v15; // rdx
  const char *v16; // r9
  int pCount; // [rsp+20h] [rbp-50h]
  __int64 v18; // [rsp+30h] [rbp-40h] BYREF
  __int64 v19; // [rsp+38h] [rbp-38h] BYREF
  __int64 v20; // [rsp+40h] [rbp-30h]
  PWTS_SESSION_INFOW *p_ppSessionInfo; // [rsp+48h] [rbp-28h] BYREF
  __int64 v22; // [rsp+50h] [rbp-20h]
  void **p_phToken; // [rsp+58h] [rbp-18h]
  char v24; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  DWORD v26; // [rsp+A0h] [rbp+30h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+B0h] [rbp+40h] BYREF
  void *phToken; // [rsp+B8h] [rbp+48h] BYREF

  v26 = a1;
  v3 = 0;
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    v26 = 0;
    ppSessionInfo = 0;
    if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &v26) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x26,
               (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
               v4);
    p_ppSessionInfo = &ppSessionInfo;
    LOBYTE(v22) = 1;
    for ( i = 0; (unsigned int)i < v26; i = (unsigned int)(i + 1) )
    {
      if ( v3 )
        break;
      SessionId = ppSessionInfo[i].SessionId;
      State = ppSessionInfo[i].State;
      if ( SessionId != (unsigned int)RtlGetCurrentServiceSessionId() && (State & 0xFFFFFFFB) == 0 )
      {
        phToken = 0;
        if ( WTSQueryUserToken(SessionId, &phToken) )
          goto LABEL_14;
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 >= 0 )
        {
LABEL_14:
          v18 = 0;
          v3 = UMgrQueryUserContext(phToken, &v18);
          if ( v3 >= 0 )
          {
            v19 = SessionId;
            v20 = v18;
            v3 = CSessionUserHelper::CallbackUserToken__lambda_fc4c7cf5ddf10be52cdadf01ede06ef6___(&v19, phToken, a2);
          }
        }
        else if ( v3 == -2147023584 )
        {
          v3 = 0;
        }
      }
    }
    if ( ppSessionInfo )
      WTSFreeMemory(ppSessionInfo);
    goto LABEL_42;
  }
  if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    v26 = 0;
    phToken = 0;
    v10 = UMgrEnumerateSessionUsers(&v26, &phToken);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
        (const char *)(unsigned int)v10,
        pCount);
      return v11;
    }
    p_phToken = &phToken;
    v24 = 1;
    for ( j = 0; j < v26; ++j )
    {
      if ( v3 )
        goto LABEL_40;
      v13 = *((_QWORD *)phToken + 2 * j);
      if ( v13 )
      {
        v14 = *((_DWORD *)phToken + 4 * j + 2);
        ppSessionInfo = 0;
        v3 = UMgrQueryUserToken(v13, &ppSessionInfo);
        if ( v3 < 0 )
        {
          v15 = 123;
          goto LABEL_30;
        }
        v19 = v14;
        v20 = v13;
        v3 = CSessionUserHelper::CallbackUserToken__lambda_fc4c7cf5ddf10be52cdadf01ede06ef6___(&v19, ppSessionInfo, a2);
      }
    }
    if ( !v3 )
    {
      v18 = 0;
      if ( (int)UMgrQueryDefaultAccountToken(&v18) >= 0 )
      {
        LODWORD(ppSessionInfo) = 0;
        if ( !(unsigned int)QueryActiveSession(&ppSessionInfo) )
        {
          v3 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x88,
                 (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
                 v16);
          goto LABEL_31;
        }
        v19 = 0;
        v3 = UMgrQueryUserContext(v18, &v19);
        if ( v3 < 0 )
        {
          v15 = 139;
LABEL_30:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
            (const char *)(unsigned int)v3,
            pCount);
LABEL_31:
          if ( phToken )
            UMgrFreeSessionUsers();
          return (unsigned int)v3;
        }
        p_ppSessionInfo = (PWTS_SESSION_INFOW *)(unsigned int)ppSessionInfo;
        v22 = v19;
        v3 = CSessionUserHelper::CallbackUserToken__lambda_fc4c7cf5ddf10be52cdadf01ede06ef6___(
               &p_ppSessionInfo,
               v18,
               a2);
      }
    }
LABEL_40:
    if ( phToken )
      UMgrFreeSessionUsers();
LABEL_42:
    if ( v3 == 1 )
      return 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18019b404  mov     [rsp-28h+arg_8], rbx
0x18019b409  mov     [rsp-28h+arg_0], ecx
0x18019b40d  push    rbp
0x18019b40e  push    rsi
0x18019b40f  push    rdi
0x18019b410  push    r14
0x18019b412  push    r15
0x18019b414  mov     rbp, rsp
0x18019b417  sub     rsp, 70h
0x18019b41b  mov     r15, rdx
0x18019b41e  xor     ebx, ebx
0x18019b420  call    IsWTSEnumerateSessionsWPresent
0x18019b425  test    al, al
0x18019b427  jz      loc_18019B54F
0x18019b42d  mov     [rbp+arg_0], ebx
0x18019b430  mov     [rbp+ppSessionInfo], rbx
0x18019b434  lea     rax, [rbp+arg_0]
0x18019b438  mov     qword ptr [rsp+70h+pCount], rax; pCount
0x18019b43d  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x18019b441  xor     edx, edx; Reserved
0x18019b443  xor     ecx, ecx; hServer
0x18019b445  lea     r8d, [rbx+1]; Version
0x18019b449  call    cs:__imp_WTSEnumerateSessionsW
0x18019b44f  test    eax, eax
0x18019b451  jnz     short loc_18019B46B
0x18019b453  mov     rcx, [rbp+28h]; this
0x18019b457  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18019b45e  lea     edx, [rbx+26h]; void *
0x18019b461  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18019b466  jmp     loc_18019B6E7
0x18019b46b  lea     rax, [rbp+ppSessionInfo]
0x18019b46f  mov     [rbp+var_28], rax
0x18019b473  mov     byte ptr [rbp+var_20], 1
0x18019b477  xor     edi, edi
0x18019b479  cmp     [rbp+arg_0], edi
0x18019b47c  jbe     loc_18019B537
0x18019b482  test    ebx, ebx
0x18019b484  jnz     loc_18019B537
0x18019b48a  lea     rcx, [rdi+rdi*2]
0x18019b48e  mov     rax, [rbp+ppSessionInfo]
0x18019b492  mov     esi, [rax+rcx*8]
0x18019b495  mov     r14d, [rax+rcx*8+10h]
0x18019b49a  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18019b4a0  cmp     esi, eax
0x18019b4a2  jz      loc_18019B52C
0x18019b4a8  test    r14d, 0FFFFFFFBh
0x18019b4af  jnz     short loc_18019B52C
0x18019b4b1  mov     [rbp+phToken], 0
0x18019b4b9  lea     rdx, [rbp+phToken]; phToken
0x18019b4bd  mov     ecx, esi; SessionId
0x18019b4bf  call    cs:__imp_WTSQueryUserToken
0x18019b4c5  test    eax, eax
0x18019b4c7  jnz     short loc_18019B4EE
0x18019b4c9  call    cs:__imp_GetLastError
0x18019b4cf  mov     ebx, eax
0x18019b4d1  test    eax, eax
0x18019b4d3  jle     short loc_18019B4DE
0x18019b4d5  movzx   ebx, ax
0x18019b4d8  or      ebx, 80070000h
0x18019b4de  test    ebx, ebx
0x18019b4e0  jns     short loc_18019B4EE
0x18019b4e2  cmp     ebx, 80070520h
0x18019b4e8  jnz     short loc_18019B52C
0x18019b4ea  xor     ebx, ebx
0x18019b4ec  jmp     short loc_18019B52C
0x18019b4ee  mov     [rbp+var_40], 0
0x18019b4f6  lea     rdx, [rbp+var_40]
0x18019b4fa  mov     rcx, [rbp+phToken]
0x18019b4fe  call    cs:__imp_UMgrQueryUserContext
0x18019b504  mov     ebx, eax
0x18019b506  test    eax, eax
0x18019b508  js      short loc_18019B52C
0x18019b50a  mov     dword ptr [rbp+var_38], esi
0x18019b50d  xor     eax, eax
0x18019b50f  mov     dword ptr [rbp+var_38+4], eax
0x18019b512  mov     rax, [rbp+var_40]
0x18019b516  mov     [rbp+var_30], rax
0x18019b51a  mov     r8, r15
0x18019b51d  mov     rdx, [rbp+phToken]
0x18019b521  lea     rcx, [rbp+var_38]
0x18019b525  call    CSessionUserHelper__CallbackUserToken__lambda_fc4c7cf5ddf10be52cdadf01ede06ef6___
0x18019b52a  mov     ebx, eax
0x18019b52c  inc     edi
0x18019b52e  cmp     edi, [rbp+arg_0]
0x18019b531  jb      loc_18019B482
0x18019b537  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x18019b53b  test    rcx, rcx
0x18019b53e  jz      loc_18019B6DD
0x18019b544  call    cs:__imp_WTSFreeMemory
0x18019b54a  jmp     loc_18019B6DD
0x18019b54f  call    IsUMgrEnumerateSessionUsersPresent
0x18019b554  test    al, al
0x18019b556  jz      loc_18019B6E5
0x18019b55c  mov     [rbp+arg_0], ebx
0x18019b55f  mov     [rbp+phToken], rbx
0x18019b563  lea     rdx, [rbp+phToken]
0x18019b567  lea     rcx, [rbp+arg_0]
0x18019b56b  call    cs:__imp_UMgrEnumerateSessionUsers
0x18019b571  mov     edi, eax
0x18019b573  test    eax, eax
0x18019b575  jns     short loc_18019B596
0x18019b577  mov     rcx, [rbp+28h]; this
0x18019b57b  mov     r9d, eax; char *
0x18019b57e  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18019b585  mov     edx, 69h ; 'i'; void *
0x18019b58a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019b58f  mov     eax, edi
0x18019b591  jmp     loc_18019B6E7
0x18019b596  lea     rax, [rbp+phToken]
0x18019b59a  mov     [rbp+var_18], rax
0x18019b59e  mov     [rbp+var_10], 1
0x18019b5a2  xor     edi, edi
0x18019b5a4  cmp     edi, [rbp+arg_0]
0x18019b5a7  jnb     loc_18019B63B
0x18019b5ad  test    ebx, ebx
0x18019b5af  jnz     loc_18019B6CE
0x18019b5b5  mov     eax, edi
0x18019b5b7  add     rax, rax
0x18019b5ba  mov     rcx, [rbp+phToken]
0x18019b5be  mov     rsi, [rcx+rax*8]
0x18019b5c2  test    rsi, rsi
0x18019b5c5  jz      short loc_18019B606
0x18019b5c7  mov     r14d, [rcx+rax*8+8]
0x18019b5cc  mov     [rbp+ppSessionInfo], 0
0x18019b5d4  lea     rdx, [rbp+ppSessionInfo]
0x18019b5d8  mov     rcx, rsi
0x18019b5db  call    cs:__imp_UMgrQueryUserToken
0x18019b5e1  mov     ebx, eax
0x18019b5e3  test    eax, eax
0x18019b5e5  js      short loc_18019B60A
0x18019b5e7  mov     dword ptr [rbp+var_38], r14d
0x18019b5eb  xor     eax, eax
0x18019b5ed  mov     dword ptr [rbp+var_38+4], eax
0x18019b5f0  mov     [rbp+var_30], rsi
0x18019b5f4  mov     r8, r15
0x18019b5f7  mov     rdx, [rbp+ppSessionInfo]
0x18019b5fb  lea     rcx, [rbp+var_38]
0x18019b5ff  call    CSessionUserHelper__CallbackUserToken__lambda_fc4c7cf5ddf10be52cdadf01ede06ef6___
0x18019b604  mov     ebx, eax
0x18019b606  inc     edi
0x18019b608  jmp     short loc_18019B5A4
0x18019b60a  mov     edx, 7Bh ; '{'; void *
0x18019b60f  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18019b616  mov     r9d, ebx; char *
0x18019b619  mov     rcx, [rbp+28h]; this
0x18019b61d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019b622  nop
0x18019b623  mov     rcx, [rbp+phToken]
0x18019b627  test    rcx, rcx
0x18019b62a  jz      loc_18019B6E5
0x18019b630  call    cs:__imp_UMgrFreeSessionUsers
0x18019b636  jmp     loc_18019B6E5
0x18019b63b  test    ebx, ebx
0x18019b63d  jnz     loc_18019B6CE
0x18019b643  mov     [rbp+var_40], 0
0x18019b64b  lea     rcx, [rbp+var_40]
0x18019b64f  call    cs:__imp_UMgrQueryDefaultAccountToken
0x18019b655  test    eax, eax
0x18019b657  js      short loc_18019B6CE
0x18019b659  mov     dword ptr [rbp+ppSessionInfo], ebx
0x18019b65c  lea     rcx, [rbp+ppSessionInfo]
0x18019b660  call    cs:__imp_QueryActiveSession
0x18019b666  test    eax, eax
0x18019b668  jnz     short loc_18019B683
0x18019b66a  mov     rcx, [rbp+28h]; this
0x18019b66e  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18019b675  mov     edx, 88h; void *
0x18019b67a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18019b67f  mov     ebx, eax
0x18019b681  jmp     short loc_18019B623
0x18019b683  mov     [rbp+var_38], 0
0x18019b68b  lea     rdx, [rbp+var_38]
0x18019b68f  mov     rcx, [rbp+var_40]
0x18019b693  call    cs:__imp_UMgrQueryUserContext
0x18019b699  mov     ebx, eax
0x18019b69b  test    eax, eax
0x18019b69d  jns     short loc_18019B6A9
0x18019b69f  mov     edx, 8Bh
0x18019b6a4  jmp     loc_18019B60F
0x18019b6a9  mov     eax, dword ptr [rbp+ppSessionInfo]
0x18019b6ac  mov     dword ptr [rbp+var_28], eax
0x18019b6af  xor     eax, eax
0x18019b6b1  mov     dword ptr [rbp+var_28+4], eax
0x18019b6b4  mov     rax, [rbp+var_38]
0x18019b6b8  mov     [rbp+var_20], rax
0x18019b6bc  mov     r8, r15
0x18019b6bf  mov     rdx, [rbp+var_40]
0x18019b6c3  lea     rcx, [rbp+var_28]
0x18019b6c7  call    CSessionUserHelper__CallbackUserToken__lambda_fc4c7cf5ddf10be52cdadf01ede06ef6___
0x18019b6cc  mov     ebx, eax
0x18019b6ce  mov     rcx, [rbp+phToken]
0x18019b6d2  test    rcx, rcx
0x18019b6d5  jz      short loc_18019B6DD
0x18019b6d7  call    cs:__imp_UMgrFreeSessionUsers
0x18019b6dd  xor     eax, eax
0x18019b6df  cmp     ebx, 1
0x18019b6e2  cmovz   ebx, eax
0x18019b6e5  mov     eax, ebx
0x18019b6e7  mov     rbx, [rsp+70h+arg_8]
0x18019b6ef  add     rsp, 70h
0x18019b6f3  pop     r15
0x18019b6f5  pop     r14
0x18019b6f7  pop     rdi
0x18019b6f8  pop     rsi
0x18019b6f9  pop     rbp
0x18019b6fa  retn
```
