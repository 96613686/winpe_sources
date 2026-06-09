# CSessionUserHelper::ForEachSessionUser__lambda_a8ce1f54a402828de23b4e1bae796bdc___

- ea: `0x1801ba818`
- end: `0x1801baac8`
- name: `CSessionUserHelper::ForEachSessionUser__lambda_a8ce1f54a402828de23b4e1bae796bdc___`
- size: `688`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1801cb350`

## callees

- `0x18000f880`
- `0x1800f8f24`
- `0x180129d58`
- `0x18012a138`
- `0x1801ba7cc`
- `0x1801ba818`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ba8d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ba8d9`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1801ba8ae`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1801ba8ae`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1801ba940`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1801ba940`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1801ba8cf`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1801ba8cf`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x1801ba85d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x1801ba85d`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x1801baa1d`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x1801baa1d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1801ba9cd`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1801ba9cd`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1801ba967`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1801ba967`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1801ba90e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1801baa7a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1801ba90e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1801baa7a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x1801baa04`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x1801baa04`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1801baa62`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1801baaa4`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1801baa62`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1801baaa4`

## string_xrefs

- `0x1801ba86b`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`
- `0x1801ba97a`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`
- `0x1801baa2b`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`
- `0x1801baa45`: `onecoreuap\base\appmodel\Search\common\include\SessionUserHelper.h`

## pseudocode

```c
__int64 __fastcall CSessionUserHelper::ForEachSessionUser__lambda_a8ce1f54a402828de23b4e1bae796bdc___(
        DWORD a1,
        __int64 a2)
{
  signed int v3; // ebx
  const char *v4; // r9
  __int64 i; // rdi
  ULONG SessionId; // esi
  WTS_CONNECTSTATE_CLASS State; // r15d
  signed int LastError; // eax
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // edi
  unsigned int v13; // edi
  DWORD v14; // edx
  __int64 v15; // rcx
  __int64 v16; // rcx
  const char *v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rcx
  int pCount; // [rsp+20h] [rbp-40h]
  __int64 v21; // [rsp+30h] [rbp-30h] BYREF
  PWTS_SESSION_INFOW *p_ppSessionInfo; // [rsp+38h] [rbp-28h] BYREF
  char v23; // [rsp+40h] [rbp-20h]
  void **p_phToken; // [rsp+48h] [rbp-18h]
  char v25; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  DWORD v27; // [rsp+90h] [rbp+30h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+A0h] [rbp+40h] BYREF
  void *phToken; // [rsp+A8h] [rbp+48h] BYREF

  v27 = a1;
  v3 = 0;
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    v27 = 0;
    ppSessionInfo = 0;
    if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &v27) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x26,
               (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
               v4);
    p_ppSessionInfo = &ppSessionInfo;
    v23 = 1;
    for ( i = 0; (unsigned int)i < v27; i = (unsigned int)(i + 1) )
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
          v21 = 0;
          v3 = UMgrQueryUserContext(phToken, &v21);
          if ( v3 >= 0 )
            v3 = CSessionUserHelper::CallbackUserToken__lambda_a8ce1f54a402828de23b4e1bae796bdc___(v10, phToken, a2);
        }
        else if ( v3 == -2147023584 )
        {
          v3 = 0;
        }
      }
    }
    if ( ppSessionInfo )
      WTSFreeMemory(ppSessionInfo);
    goto LABEL_41;
  }
  if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    v27 = 0;
    phToken = 0;
    v11 = UMgrEnumerateSessionUsers(&v27, &phToken);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
        (const char *)(unsigned int)v11,
        pCount);
      return v12;
    }
    p_phToken = &phToken;
    v25 = 1;
    v13 = 0;
    v14 = v27;
    if ( v27 )
    {
      while ( !v3 )
      {
        v15 = *((_QWORD *)phToken + 2 * v13);
        if ( v15 )
        {
          ppSessionInfo = 0;
          v3 = UMgrQueryUserToken(v15, &ppSessionInfo);
          if ( v3 < 0 )
          {
            v18 = 123;
            goto LABEL_33;
          }
          v3 = CSessionUserHelper::CallbackUserToken__lambda_a8ce1f54a402828de23b4e1bae796bdc___(v16, ppSessionInfo, a2);
          v14 = v27;
        }
        if ( ++v13 >= v14 )
        {
          if ( v3 )
            goto LABEL_39;
          goto LABEL_29;
        }
      }
      goto LABEL_39;
    }
LABEL_29:
    v21 = 0;
    if ( (int)UMgrQueryDefaultAccountToken(&v21) >= 0 )
    {
      LODWORD(ppSessionInfo) = 0;
      if ( !(unsigned int)QueryActiveSession(&ppSessionInfo) )
      {
        v3 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x88,
               (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
               v17);
LABEL_34:
        if ( phToken )
          UMgrFreeSessionUsers();
        return (unsigned int)v3;
      }
      p_ppSessionInfo = 0;
      v3 = UMgrQueryUserContext(v21, &p_ppSessionInfo);
      if ( v3 < 0 )
      {
        v18 = 139;
LABEL_33:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\SessionUserHelper.h",
          (const char *)(unsigned int)v3,
          pCount);
        goto LABEL_34;
      }
      v3 = CSessionUserHelper::CallbackUserToken__lambda_a8ce1f54a402828de23b4e1bae796bdc___(v19, v21, a2);
    }
LABEL_39:
    if ( phToken )
      UMgrFreeSessionUsers();
LABEL_41:
    if ( v3 == 1 )
      return 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1801ba818  mov     [rsp-28h+arg_8], rbx
0x1801ba81d  mov     [rsp-28h+arg_0], ecx
0x1801ba821  push    rbp
0x1801ba822  push    rsi
0x1801ba823  push    rdi
0x1801ba824  push    r14
0x1801ba826  push    r15
0x1801ba828  mov     rbp, rsp
0x1801ba82b  sub     rsp, 60h
0x1801ba82f  mov     r14, rdx
0x1801ba832  xor     ebx, ebx
0x1801ba834  call    IsWTSEnumerateSessionsWPresent
0x1801ba839  test    al, al
0x1801ba83b  jz      loc_1801BA94B
0x1801ba841  mov     [rbp+arg_0], ebx
0x1801ba844  mov     [rbp+ppSessionInfo], rbx
0x1801ba848  lea     rax, [rbp+arg_0]
0x1801ba84c  mov     qword ptr [rsp+60h+pCount], rax; pCount
0x1801ba851  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x1801ba855  xor     edx, edx; Reserved
0x1801ba857  xor     ecx, ecx; hServer
0x1801ba859  lea     r8d, [rbx+1]; Version
0x1801ba85d  call    cs:__imp_WTSEnumerateSessionsW
0x1801ba863  test    eax, eax
0x1801ba865  jnz     short loc_1801BA87F
0x1801ba867  mov     rcx, [rbp+28h]; this
0x1801ba86b  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801ba872  lea     edx, [rbx+26h]; void *
0x1801ba875  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801ba87a  jmp     loc_1801BAAB4
0x1801ba87f  lea     rax, [rbp+ppSessionInfo]
0x1801ba883  mov     [rbp+var_28], rax
0x1801ba887  mov     [rbp+var_20], 1
0x1801ba88b  xor     edi, edi
0x1801ba88d  cmp     [rbp+arg_0], edi
0x1801ba890  jbe     loc_1801BA933
0x1801ba896  test    ebx, ebx
0x1801ba898  jnz     loc_1801BA933
0x1801ba89e  lea     rdx, [rdi+rdi*2]
0x1801ba8a2  mov     rax, [rbp+ppSessionInfo]
0x1801ba8a6  mov     esi, [rax+rdx*8]
0x1801ba8a9  mov     r15d, [rax+rdx*8+10h]
0x1801ba8ae  call    cs:__imp_RtlGetCurrentServiceSessionId
0x1801ba8b4  cmp     esi, eax
0x1801ba8b6  jz      short loc_1801BA928
0x1801ba8b8  test    r15d, 0FFFFFFFBh
0x1801ba8bf  jnz     short loc_1801BA928
0x1801ba8c1  mov     [rbp+phToken], 0
0x1801ba8c9  lea     rdx, [rbp+phToken]; phToken
0x1801ba8cd  mov     ecx, esi; SessionId
0x1801ba8cf  call    cs:__imp_WTSQueryUserToken
0x1801ba8d5  test    eax, eax
0x1801ba8d7  jnz     short loc_1801BA8FE
0x1801ba8d9  call    cs:__imp_GetLastError
0x1801ba8df  mov     ebx, eax
0x1801ba8e1  test    eax, eax
0x1801ba8e3  jle     short loc_1801BA8EE
0x1801ba8e5  movzx   ebx, ax
0x1801ba8e8  or      ebx, 80070000h
0x1801ba8ee  test    ebx, ebx
0x1801ba8f0  jns     short loc_1801BA8FE
0x1801ba8f2  cmp     ebx, 80070520h
0x1801ba8f8  jnz     short loc_1801BA928
0x1801ba8fa  xor     ebx, ebx
0x1801ba8fc  jmp     short loc_1801BA928
0x1801ba8fe  mov     [rbp+var_30], 0
0x1801ba906  lea     rdx, [rbp+var_30]
0x1801ba90a  mov     rcx, [rbp+phToken]
0x1801ba90e  call    cs:__imp_UMgrQueryUserContext
0x1801ba914  mov     ebx, eax
0x1801ba916  test    eax, eax
0x1801ba918  js      short loc_1801BA928
0x1801ba91a  mov     r8, r14
0x1801ba91d  mov     rdx, [rbp+phToken]
0x1801ba921  call    CSessionUserHelper__CallbackUserToken__lambda_a8ce1f54a402828de23b4e1bae796bdc___
0x1801ba926  mov     ebx, eax
0x1801ba928  inc     edi
0x1801ba92a  cmp     edi, [rbp+arg_0]
0x1801ba92d  jb      loc_1801BA896
0x1801ba933  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x1801ba937  test    rcx, rcx
0x1801ba93a  jz      loc_1801BAAAA
0x1801ba940  call    cs:__imp_WTSFreeMemory
0x1801ba946  jmp     loc_1801BAAAA
0x1801ba94b  call    IsUMgrEnumerateSessionUsersPresent
0x1801ba950  test    al, al
0x1801ba952  jz      loc_1801BAAB2
0x1801ba958  mov     [rbp+arg_0], ebx
0x1801ba95b  mov     [rbp+phToken], rbx
0x1801ba95f  lea     rdx, [rbp+phToken]
0x1801ba963  lea     rcx, [rbp+arg_0]
0x1801ba967  call    cs:__imp_UMgrEnumerateSessionUsers
0x1801ba96d  mov     edi, eax
0x1801ba96f  test    eax, eax
0x1801ba971  jns     short loc_1801BA992
0x1801ba973  mov     rcx, [rbp+28h]; this
0x1801ba977  mov     r9d, eax; char *
0x1801ba97a  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801ba981  mov     edx, 69h ; 'i'; void *
0x1801ba986  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ba98b  mov     eax, edi
0x1801ba98d  jmp     loc_1801BAAB4
0x1801ba992  lea     rax, [rbp+phToken]
0x1801ba996  mov     [rbp+var_18], rax
0x1801ba99a  mov     [rbp+var_10], 1
0x1801ba99e  xor     edi, edi
0x1801ba9a0  mov     edx, [rbp+arg_0]
0x1801ba9a3  test    edx, edx
0x1801ba9a5  jz      short loc_1801BA9F8
0x1801ba9a7  test    ebx, ebx
0x1801ba9a9  jnz     loc_1801BAA9B
0x1801ba9af  mov     ecx, edi
0x1801ba9b1  add     rcx, rcx
0x1801ba9b4  mov     rax, [rbp+phToken]
0x1801ba9b8  mov     rcx, [rax+rcx*8]
0x1801ba9bc  test    rcx, rcx
0x1801ba9bf  jz      short loc_1801BA9EA
0x1801ba9c1  mov     [rbp+ppSessionInfo], 0
0x1801ba9c9  lea     rdx, [rbp+ppSessionInfo]
0x1801ba9cd  call    cs:__imp_UMgrQueryUserToken
0x1801ba9d3  mov     ebx, eax
0x1801ba9d5  test    eax, eax
0x1801ba9d7  js      short loc_1801BAA40
0x1801ba9d9  mov     r8, r14
0x1801ba9dc  mov     rdx, [rbp+ppSessionInfo]
0x1801ba9e0  call    CSessionUserHelper__CallbackUserToken__lambda_a8ce1f54a402828de23b4e1bae796bdc___
0x1801ba9e5  mov     ebx, eax
0x1801ba9e7  mov     edx, [rbp+arg_0]
0x1801ba9ea  inc     edi
0x1801ba9ec  cmp     edi, edx
0x1801ba9ee  jb      short loc_1801BA9A7
0x1801ba9f0  test    ebx, ebx
0x1801ba9f2  jnz     loc_1801BAA9B
0x1801ba9f8  mov     [rbp+var_30], 0
0x1801baa00  lea     rcx, [rbp+var_30]
0x1801baa04  call    cs:__imp_UMgrQueryDefaultAccountToken
0x1801baa0a  test    eax, eax
0x1801baa0c  js      loc_1801BAA9B
0x1801baa12  mov     dword ptr [rbp+ppSessionInfo], 0
0x1801baa19  lea     rcx, [rbp+ppSessionInfo]
0x1801baa1d  call    cs:__imp_QueryActiveSession
0x1801baa23  test    eax, eax
0x1801baa25  jnz     short loc_1801BAA6A
0x1801baa27  mov     rcx, [rbp+28h]; this
0x1801baa2b  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801baa32  mov     edx, 88h; void *
0x1801baa37  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801baa3c  mov     ebx, eax
0x1801baa3e  jmp     short loc_1801BAA59
0x1801baa40  mov     edx, 7Bh ; '{'; void *
0x1801baa45  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801baa4c  mov     r9d, ebx; char *
0x1801baa4f  mov     rcx, [rbp+28h]; this
0x1801baa53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801baa58  nop
0x1801baa59  mov     rcx, [rbp+phToken]
0x1801baa5d  test    rcx, rcx
0x1801baa60  jz      short loc_1801BAAB2
0x1801baa62  call    cs:__imp_UMgrFreeSessionUsers
0x1801baa68  jmp     short loc_1801BAAB2
0x1801baa6a  mov     [rbp+var_28], 0
0x1801baa72  lea     rdx, [rbp+var_28]
0x1801baa76  mov     rcx, [rbp+var_30]
0x1801baa7a  call    cs:__imp_UMgrQueryUserContext
0x1801baa80  mov     ebx, eax
0x1801baa82  test    eax, eax
0x1801baa84  jns     short loc_1801BAA8D
0x1801baa86  mov     edx, 8Bh
0x1801baa8b  jmp     short loc_1801BAA45
0x1801baa8d  mov     r8, r14
0x1801baa90  mov     rdx, [rbp+var_30]
0x1801baa94  call    CSessionUserHelper__CallbackUserToken__lambda_a8ce1f54a402828de23b4e1bae796bdc___
0x1801baa99  mov     ebx, eax
0x1801baa9b  mov     rcx, [rbp+phToken]
0x1801baa9f  test    rcx, rcx
0x1801baaa2  jz      short loc_1801BAAAA
0x1801baaa4  call    cs:__imp_UMgrFreeSessionUsers
0x1801baaaa  xor     eax, eax
0x1801baaac  cmp     ebx, 1
0x1801baaaf  cmovz   ebx, eax
0x1801baab2  mov     eax, ebx
0x1801baab4  mov     rbx, [rsp+60h+arg_8]
0x1801baabc  add     rsp, 60h
0x1801baac0  pop     r15
0x1801baac2  pop     r14
0x1801baac4  pop     rdi
0x1801baac5  pop     rsi
0x1801baac6  pop     rbp
0x1801baac7  retn
```
