# CLoggedOnUsers::FindUserSession(SidHandle,unsigned __int64 *)

- ea: `0x18002d330`
- end: `0x18002da7f`
- name: `?FindUserSession@CLoggedOnUsers@@QEAAPEAVCUserSession@@VSidHandle@@PEA_K@Z`
- size: `1871`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001a6fc`
- `0x180076344`
- `0x1800765dc`
- `0x18007b438`

## callees

- `0x18000c2d0`
- `0x18002d330`
- `0x18002e5c0`
- `0x180032720`
- `0x1800634e0`
- `0x180075e94`
- `0x180091afc`
- `0x18009d024`
- `0x1800a3444`
- `0x1800a7558`
- `0x1800b188c`
- `0x1800c178c`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d3d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d3d5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d4bf`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d4d2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d4ec`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d4ff`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d811`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d829`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d841`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d859`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d4bf`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d4d2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d4ec`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d4ff`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d811`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d829`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d841`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d859`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d45d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d469`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d47d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d489`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d4a6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d797`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d7a5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d7be`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d7cc`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d7f0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d45d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d469`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d47d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d489`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d4a6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d797`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d7a5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d7be`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d7cc`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d7f0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002d6da`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002d6da`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18002d971`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18002d971`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002d66a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002d66a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void *__fastcall CLoggedOnUsers::FindUserSession(__int64 a1, PSID *a2, unsigned __int64 *a3)
{
  unsigned __int64 *v3; // r15
  PSID *v4; // r14
  __int64 v5; // rsi
  unsigned __int64 v6; // r8
  const wchar_t *v7; // rax
  TaskScheduler *v8; // rdi
  char v9; // r12
  __int64 v10; // rcx
  __int64 v11; // r9
  void *v12; // r13
  char *v13; // rbx
  char *v14; // rdi
  PSID v15; // r12
  PUCHAR SidSubAuthorityCount; // rbx
  PUCHAR v17; // rax
  PUCHAR v18; // rbx
  PUCHAR v19; // rax
  UCHAR i; // bl
  PDWORD SidSubAuthority; // rbx
  PDWORD v22; // rax
  PDWORD v23; // rbx
  PDWORD v24; // rax
  __int64 v25; // rdi
  void *v26; // rcx
  void *v27; // rcx
  __int64 v28; // r8
  _QWORD *v29; // rax
  __int64 inserted; // r13
  unsigned __int64 v31; // rdx
  _QWORD *v32; // rax
  __int64 v33; // rbx
  PSID v34; // rcx
  PSID v35; // rdi
  char **v36; // rax
  char *v37; // r15
  PSID v38; // rax
  PUCHAR v39; // rdi
  PUCHAR v40; // rdi
  UCHAR j; // di
  PUCHAR v42; // rax
  PDWORD v43; // rdi
  PDWORD v44; // rax
  PDWORD v45; // rdi
  __int64 v46; // rdi
  void *v47; // rcx
  __int64 Sid; // rax
  signed __int32 v49; // eax
  PSID pSid; // [rsp+30h] [rbp-B8h] BYREF
  volatile signed __int32 *v52; // [rsp+38h] [rbp-B0h]
  void *v53; // [rsp+40h] [rbp-A8h]
  void *v54[2]; // [rsp+50h] [rbp-98h] BYREF
  TaskScheduler *v55; // [rsp+70h] [rbp-78h]
  TaskScheduler *v56; // [rsp+78h] [rbp-70h]
  char v57; // [rsp+80h] [rbp-68h]
  int v58; // [rsp+94h] [rbp-54h]
  const ComError *v59; // [rsp+A0h] [rbp-48h] BYREF
  UCHAR v61; // [rsp+F0h] [rbp+8h]
  UCHAR v62; // [rsp+F0h] [rbp+8h]
  __int64 nSubAuthoritya; // [rsp+100h] [rbp+18h]
  __int64 nSubAuthorityb; // [rsp+100h] [rbp+18h]
  PSID v67; // [rsp+108h] [rbp+20h] BYREF

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    if ( a3 )
      v6 = *a3;
    else
      v6 = 0;
    v7 = L"YES";
    if ( v3 )
      v7 = L"NO";
    WPP_SF__sid_Si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      64,
      &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids,
      *a2,
      v7,
      v6);
  }
  v8 = *(TaskScheduler **)v5;
  v55 = v8;
  v56 = v8;
  v9 = 0;
  v57 = 0;
  if ( *((_DWORD *)v8 + 14) != GetCurrentThreadId() )
  {
    TaskScheduler::LockReader(v8);
    v9 = 1;
    v57 = 1;
  }
  if ( v3 )
  {
    v28 = *(_QWORD *)(v5 + 16);
    v29 = *(_QWORD **)(v28 + 8);
    v54[0] = v29;
    v54[1] = 0;
    inserted = v28;
    if ( !*((_BYTE *)v29 + 25) )
    {
      v31 = *v3;
      do
      {
        v54[0] = v29;
        if ( v29[4] >= v31 )
        {
          LODWORD(v54[1]) = 1;
          inserted = (__int64)v29;
        }
        else
        {
          LODWORD(v54[1]) = 0;
          v29 += 2;
        }
        v29 = (_QWORD *)*v29;
      }
      while ( !*((_BYTE *)v29 + 25) );
    }
    try
    {
      if ( *(_BYTE *)(inserted + 25) || *v3 < *(_QWORD *)(inserted + 32) )
      {
        if ( *(_QWORD *)(v5 + 24) == 0x555555555555555LL )
          std::_Xlength_error("map/set too long");
        v67 = v3;
        v32 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,UserManagerUserSession *>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,UserManagerUserSession *>,void *>>>(
                &pSid,
                v5 + 16,
                v28,
                v11,
                (_QWORD **)&v67);
        v33 = v32[1];
        v32[1] = 0;
        std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum _CRM_CLIENT_ID const,void *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum _CRM_CLIENT_ID const,void *>,void *>>>((__int64)&pSid);
        inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CEncryptedCredentials *>>>::_Insert_node(
                     v5 + 16,
                     v54,
                     v33);
      }
      v12 = *(void **)(inserted + 40);
      if ( v12 && !EqualSid(*((PSID *)v12 + 5), *v4) )
        v12 = 0;
    }
    catch ( const ComError *v59 )
    {
      v67 = 0;
      v5 = a1;
      v3 = a3;
      v4 = a2;
      v55 = v56;
      v12 = 0;
      v9 = v57;
      goto LABEL_55;
    }
    goto LABEL_53;
  }
  v12 = 0;
  v54[0] = 0;
  pSid = *v4;
  v53 = v4[1];
  v52 = (volatile signed __int32 *)v53;
  _InterlockedIncrement((volatile signed __int32 *)v53);
  v13 = *(char **)(v5 + 32);
  v67 = v13;
  v14 = (char *)*((_QWORD *)v13 + 1);
  v58 = 0;
  if ( !v14[25] )
  {
    while ( 1 )
    {
      v15 = (PSID)*((_QWORD *)v14 + 4);
      if ( v15 && pSid )
      {
        SidSubAuthorityCount = GetSidSubAuthorityCount(pSid);
        v17 = GetSidSubAuthorityCount(v15);
        v10 = *SidSubAuthorityCount;
        if ( *v17 < (unsigned __int8)v10 )
        {
LABEL_34:
          v13 = (char *)v67;
LABEL_35:
          v14 += 16;
          goto LABEL_24;
        }
        v18 = GetSidSubAuthorityCount(pSid);
        v19 = GetSidSubAuthorityCount(v15);
        v10 = *v18;
        if ( *v19 <= (unsigned __int8)v10 )
        {
          for ( i = 0; ; i = v61 + 1 )
          {
            v61 = i;
            if ( i >= *GetSidSubAuthorityCount(v15) )
              break;
            LODWORD(nSubAuthoritya) = i;
            SidSubAuthority = GetSidSubAuthority(pSid, i);
            v22 = GetSidSubAuthority(v15, nSubAuthoritya);
            v10 = *SidSubAuthority;
            if ( *v22 < (unsigned int)v10 )
              goto LABEL_34;
            v23 = GetSidSubAuthority(pSid, nSubAuthoritya);
            v24 = GetSidSubAuthority(v15, nSubAuthoritya);
            v10 = *v23;
            if ( *v24 > (unsigned int)v10 )
              break;
          }
        }
      }
      else if ( (__int64)v15 < (__int64)pSid )
      {
        goto LABEL_35;
      }
      v13 = v14;
      v67 = v14;
LABEL_24:
      v14 = *(char **)v14;
      if ( v14[25] )
      {
        v12 = v54[0];
        v9 = v57;
        break;
      }
    }
  }
  if ( v13[25] || (unsigned __int8)CSidSorter::operator()(v10, &pSid, v13 + 32) || v13 == *(char **)(v5 + 32) )
  {
    v27 = v53;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v53, 0xFFFFFFFF) == 1 )
    {
      operator delete(v27, 4u);
      operator delete(pSid, 0);
    }
    goto LABEL_56;
  }
  v25 = *((_QWORD *)v13 + 6);
  v26 = v53;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v53, 0xFFFFFFFF) == 1 )
  {
    operator delete(v26, 4u);
    operator delete(pSid, 0);
  }
  if ( v25 )
  {
    if ( *(_QWORD *)(v25 + 8) == *(_QWORD *)v25 )
      goto LABEL_87;
    v12 = **(void ***)v25;
LABEL_53:
    if ( v12 )
      goto LABEL_89;
    if ( v3 )
    {
LABEL_55:
      if ( *v3 )
        goto LABEL_95;
    }
  }
LABEL_56:
  v34 = *v4;
  pSid = *v4;
  v35 = v4[1];
  v54[0] = v35;
  v52 = (volatile signed __int32 *)v35;
  _InterlockedIncrement((volatile signed __int32 *)v35);
  v36 = *(char ***)(v5 + 48);
  v53 = v36;
  v37 = v36[1];
  v58 = 0;
  if ( !v37[25] )
  {
    while ( 1 )
    {
      v38 = (PSID)*((_QWORD *)v37 + 4);
      v67 = v38;
      if ( v38 && v34 )
      {
        v39 = GetSidSubAuthorityCount(v38);
        if ( *v39 >= *GetSidSubAuthorityCount(pSid) )
        {
          v40 = GetSidSubAuthorityCount(v67);
          if ( *v40 > *GetSidSubAuthorityCount(pSid) )
          {
LABEL_70:
            v34 = pSid;
          }
          else
          {
            for ( j = 0; ; j = v62 + 1 )
            {
              v62 = j;
              v42 = GetSidSubAuthorityCount(v67);
              v34 = pSid;
              if ( j >= *v42 )
                break;
              LODWORD(nSubAuthorityb) = j;
              v43 = GetSidSubAuthority(pSid, j);
              v44 = GetSidSubAuthority(v67, nSubAuthorityb);
              v34 = pSid;
              if ( *v44 < *v43 )
                goto LABEL_69;
              v45 = GetSidSubAuthority(pSid, nSubAuthorityb);
              if ( *GetSidSubAuthority(v67, nSubAuthorityb) > *v45 )
                goto LABEL_70;
            }
          }
LABEL_71:
          v36 = (char **)v37;
          v53 = v37;
          goto LABEL_72;
        }
        v34 = pSid;
      }
      else if ( (__int64)v38 >= (__int64)v34 )
      {
        goto LABEL_71;
      }
LABEL_69:
      v37 += 16;
      v36 = (char **)v53;
LABEL_72:
      v37 = *(char **)v37;
      if ( v37[25] )
      {
        v35 = v54[0];
        break;
      }
    }
  }
  if ( *((_BYTE *)v36 + 25)
    || (unsigned __int8)CSidSorter::operator()(v34, &pSid, v36 + 4)
    || v53 == *(void **)(v5 + 48) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v35, 0xFFFFFFFF) == 1 )
    {
      operator delete(v35, 4u);
      operator delete(pSid, 0);
    }
  }
  else
  {
    v46 = *((_QWORD *)v53 + 6);
    v47 = v54[0];
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v54[0], 0xFFFFFFFF) == 1 )
    {
      operator delete(v47, 4u);
      operator delete(pSid, 0);
    }
    if ( v46 )
    {
      if ( *(_QWORD *)(v46 + 8) == *(_QWORD *)v46 )
        goto LABEL_87;
      v12 = **(void ***)v46;
      if ( v12 )
      {
LABEL_89:
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
        v49 = _InterlockedIncrement((volatile signed __int32 *)v12 + 2);
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids, v12, v49);
        goto LABEL_98;
      }
    }
  }
  pSid = *v4;
  v52 = (volatile signed __int32 *)v4[1];
  _InterlockedIncrement(v52);
  Sid = CUserList<RemotePowerShellSession>::FindSid(v5 + 88, &pSid);
  if ( Sid )
  {
    if ( *(_QWORD *)(Sid + 8) == *(_QWORD *)Sid )
    {
LABEL_87:
      std::_Xout_of_range("invalid vector subscript");
      __debugbreak();
    }
    v12 = **(void ***)Sid;
    if ( v12 )
      goto LABEL_89;
  }
LABEL_95:
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids);
LABEL_98:
  if ( v9 )
    TaskScheduler::UnlockReader(v55);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4[1], 0xFFFFFFFF) == 1 )
  {
    operator delete(v4[1], 4u);
    operator delete(*v4, 0);
    v4[1] = 0;
    *v4 = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x18002d330  mov     [rsp+nSubAuthority], r8
0x18002d335  mov     [rsp+arg_8], rdx
0x18002d33a  mov     [rsp+arg_0], rcx
0x18002d33f  push    rbx
0x18002d340  push    rsi
0x18002d341  push    rdi
0x18002d342  push    r12
0x18002d344  push    r13
0x18002d346  push    r14
0x18002d348  push    r15
0x18002d34a  sub     rsp, 0B0h
0x18002d351  mov     r15, r8
0x18002d354  mov     r14, rdx
0x18002d357  mov     rsi, rcx
0x18002d35a  lea     rax, WPP_GLOBAL_Control
0x18002d361  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d368  cmp     rcx, rax
0x18002d36b  jz      short loc_18002D3BB
0x18002d36d  test    byte ptr [rcx+1Ch], 1
0x18002d371  jz      short loc_18002D3BB
0x18002d373  xor     ebx, ebx
0x18002d375  test    r8, r8
0x18002d378  jnz     short loc_18002D37F
0x18002d37a  mov     r8d, ebx
0x18002d37d  jmp     short loc_18002D382
0x18002d37f  mov     r8, [r8]
0x18002d382  lea     rdx, aNo; "NO"
0x18002d389  lea     rax, aYes; "YES"
0x18002d390  test    r15, r15
0x18002d393  cmovnz  rax, rdx
0x18002d397  mov     edx, 40h ; '@'
0x18002d39c  mov     [rsp+0E8h+var_C0], r8
0x18002d3a1  mov     [rsp+0E8h+var_C8], rax
0x18002d3a6  mov     r9, [r14]
0x18002d3a9  lea     r8, WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids
0x18002d3b0  mov     rcx, [rcx+10h]
0x18002d3b4  call    WPP_SF__sid_Si
0x18002d3b9  jmp     short loc_18002D3BD
0x18002d3bb  xor     ebx, ebx
0x18002d3bd  mov     rdi, [rsi]
0x18002d3c0  mov     [rsp+0E8h+var_78], rdi
0x18002d3c5  mov     [rsp+0E8h+var_70], rdi
0x18002d3ca  xor     r12b, r12b
0x18002d3cd  mov     [rsp+0E8h+var_68], r12b
0x18002d3d5  call    cs:__imp_GetCurrentThreadId
0x18002d3db  cmp     [rdi+38h], eax
0x18002d3de  jz      short loc_18002D3F3
0x18002d3e0  mov     rcx, rdi; this
0x18002d3e3  call    ?LockReader@TaskScheduler@@QEAA_NXZ; TaskScheduler::LockReader(void)
0x18002d3e8  mov     r12b, 1
0x18002d3eb  mov     [rsp+0E8h+var_68], r12b
0x18002d3f3  test    r15, r15
0x18002d3f6  jnz     loc_18002D5F7
0x18002d3fc  mov     r13, rbx
0x18002d3ff  mov     [rsp+0E8h+var_98], rbx
0x18002d404  mov     rax, [r14]
0x18002d407  mov     [rsp+0E8h+pSid], rax
0x18002d40c  mov     rax, [r14+8]
0x18002d410  mov     [rsp+0E8h+var_A8], rax
0x18002d415  mov     [rsp+0E8h+var_B0], rax
0x18002d41a  lock inc dword ptr [rax]
0x18002d41d  mov     rbx, [rsi+20h]
0x18002d421  mov     [rsp+0E8h+arg_18], rbx
0x18002d429  mov     rdi, [rbx+8]
0x18002d42d  xor     eax, eax
0x18002d42f  mov     [rsp+0E8h+var_54], eax
0x18002d436  cmp     [rdi+19h], al
0x18002d439  jnz     loc_18002D546
0x18002d43f  mov     r13, [rsp+0E8h+pSid]
0x18002d444  mov     r12, [rdi+20h]
0x18002d448  test    r12, r12
0x18002d44b  jz      loc_18002D517
0x18002d451  test    r13, r13
0x18002d454  jz      loc_18002D517
0x18002d45a  mov     rcx, r13; pSid
0x18002d45d  call    cs:__imp_GetSidSubAuthorityCount
0x18002d463  mov     rbx, rax
0x18002d466  mov     rcx, r12; pSid
0x18002d469  call    cs:__imp_GetSidSubAuthorityCount
0x18002d46f  movzx   ecx, byte ptr [rbx]
0x18002d472  cmp     [rax], cl
0x18002d474  jb      loc_18002D5B2
0x18002d47a  mov     rcx, r13; pSid
0x18002d47d  call    cs:__imp_GetSidSubAuthorityCount
0x18002d483  mov     rbx, rax
0x18002d486  mov     rcx, r12; pSid
0x18002d489  call    cs:__imp_GetSidSubAuthorityCount
0x18002d48f  movzx   ecx, byte ptr [rbx]
0x18002d492  cmp     [rax], cl
0x18002d494  ja      loc_18002D520
0x18002d49a  xor     bl, bl
0x18002d49c  mov     byte ptr [rsp+0E8h+arg_0], bl
0x18002d4a3  mov     rcx, r12; pSid
0x18002d4a6  call    cs:__imp_GetSidSubAuthorityCount
0x18002d4ac  cmp     bl, [rax]
0x18002d4ae  jnb     short loc_18002D520
0x18002d4b0  movzx   eax, bl
0x18002d4b3  mov     dword ptr [rsp+0E8h+nSubAuthority], eax
0x18002d4ba  mov     edx, eax; nSubAuthority
0x18002d4bc  mov     rcx, r13; pSid
0x18002d4bf  call    cs:__imp_GetSidSubAuthority
0x18002d4c5  mov     rbx, rax
0x18002d4c8  mov     edx, dword ptr [rsp+0E8h+nSubAuthority]; nSubAuthority
0x18002d4cf  mov     rcx, r12; pSid
0x18002d4d2  call    cs:__imp_GetSidSubAuthority
0x18002d4d8  mov     ecx, [rbx]
0x18002d4da  cmp     [rax], ecx
0x18002d4dc  jb      loc_18002D5B2
0x18002d4e2  mov     edx, dword ptr [rsp+0E8h+nSubAuthority]; nSubAuthority
0x18002d4e9  mov     rcx, r13; pSid
0x18002d4ec  call    cs:__imp_GetSidSubAuthority
0x18002d4f2  mov     rbx, rax
0x18002d4f5  mov     edx, dword ptr [rsp+0E8h+nSubAuthority]; nSubAuthority
0x18002d4fc  mov     rcx, r12; pSid
0x18002d4ff  call    cs:__imp_GetSidSubAuthority
0x18002d505  mov     ecx, [rbx]
0x18002d507  cmp     [rax], ecx
0x18002d509  ja      short loc_18002D520
0x18002d50b  movzx   ebx, byte ptr [rsp+0E8h+arg_0]
0x18002d513  inc     bl
0x18002d515  jmp     short loc_18002D49C
0x18002d517  cmp     r12, r13
0x18002d51a  jl      loc_18002D5BA
0x18002d520  mov     rbx, rdi
0x18002d523  mov     [rsp+0E8h+arg_18], rbx
0x18002d52b  mov     rdi, [rdi]
0x18002d52e  cmp     byte ptr [rdi+19h], 0
0x18002d532  jz      loc_18002D444
0x18002d538  mov     r13, [rsp+0E8h+var_98]
0x18002d53d  movzx   r12d, [rsp+0E8h+var_68]
0x18002d546  cmp     byte ptr [rbx+19h], 0
0x18002d54a  jnz     short loc_18002D5C3
0x18002d54c  lea     r8, [rbx+20h]
0x18002d550  lea     rdx, [rsp+0E8h+pSid]
0x18002d555  call    ??RCSidSorter@@QEBA_NAEBVSidHandle@@0@Z; CSidSorter::operator()(SidHandle const &,SidHandle const &)
0x18002d55a  test    al, al
0x18002d55c  jnz     short loc_18002D5C3
0x18002d55e  cmp     rbx, [rsi+20h]
0x18002d562  jz      short loc_18002D5C3
0x18002d564  mov     rdi, [rbx+30h]
0x18002d568  mov     ebx, 0FFFFFFFFh
0x18002d56d  mov     eax, ebx
0x18002d56f  mov     rcx, [rsp+0E8h+var_A8]; void *
0x18002d574  lock xadd [rcx], eax
0x18002d578  cmp     eax, 1
0x18002d57b  jnz     short loc_18002D593
0x18002d57d  mov     edx, 4; unsigned __int64
0x18002d582  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d587  xor     edx, edx; unsigned __int64
0x18002d589  mov     rcx, [rsp+0E8h+pSid]; void *
0x18002d58e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d593  test    rdi, rdi
0x18002d596  jz      loc_18002D73D
0x18002d59c  mov     r13, [rdi]
0x18002d59f  cmp     [rdi+8], r13
0x18002d5a3  jz      loc_18002D96A
0x18002d5a9  mov     r13, [r13+0]
0x18002d5ad  jmp     loc_18002D6EB
0x18002d5b2  mov     rbx, [rsp+0E8h+arg_18]
0x18002d5ba  add     rdi, 10h
0x18002d5be  jmp     loc_18002D52B
0x18002d5c3  mov     ebx, 0FFFFFFFFh
0x18002d5c8  mov     eax, ebx
0x18002d5ca  mov     rcx, [rsp+0E8h+var_A8]; void *
0x18002d5cf  lock xadd [rcx], eax
0x18002d5d3  cmp     eax, 1
0x18002d5d6  jnz     loc_18002D73D
0x18002d5dc  mov     edx, 4; unsigned __int64
0x18002d5e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d5e6  xor     edx, edx; unsigned __int64
0x18002d5e8  mov     rcx, [rsp+0E8h+pSid]; void *
0x18002d5ed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d5f2  jmp     loc_18002D73D
0x18002d5f7  mov     r8, [rsi+10h]
0x18002d5fb  mov     rax, [r8+8]
0x18002d5ff  mov     [rsp+0E8h+var_98], rax
0x18002d604  mov     [rsp+0E8h+var_98+8], 0
0x18002d60d  mov     r13, r8
0x18002d610  cmp     byte ptr [rax+19h], 0
0x18002d614  jnz     short loc_18002D643
0x18002d616  mov     rdx, [r15]
0x18002d619  mov     ecx, 1
0x18002d61e  mov     [rsp+0E8h+var_98], rax
0x18002d623  cmp     [rax+20h], rdx
0x18002d627  jnb     short loc_18002D633
0x18002d629  mov     dword ptr [rsp+0E8h+var_98+8], ebx
0x18002d62d  add     rax, 10h
0x18002d631  jmp     short loc_18002D63A
0x18002d633  mov     dword ptr [rsp+0E8h+var_98+8], ecx
0x18002d637  mov     r13, rax
0x18002d63a  mov     rax, [rax]
0x18002d63d  cmp     byte ptr [rax+19h], 0
0x18002d641  jz      short loc_18002D61E
0x18002d643  cmp     byte ptr [r13+19h], 0
0x18002d648  jnz     short loc_18002D653
0x18002d64a  mov     rax, [r13+20h]
0x18002d64e  cmp     [r15], rax
0x18002d651  jnb     short loc_18002D6CA
0x18002d653  mov     rax, 555555555555555h
0x18002d65d  cmp     [rsi+18h], rax
0x18002d661  jnz     short loc_18002D670
0x18002d663  lea     rcx, aMapSetTooLong; "map/set too long"
0x18002d66a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002d670  mov     [rsp+0E8h+arg_18], r15
0x18002d678  lea     rax, [rsp+0E8h+arg_18]
0x18002d680  mov     [rsp+0E8h+var_C8], rax
0x18002d685  lea     rdx, [rsi+10h]
0x18002d689  lea     rcx, [rsp+0E8h+pSid]
0x18002d68e  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@AEB_K@1@V?$tuple@$$V@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KPEAVUserManagerUserSession@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KPEAVUserManagerUserSession@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KPEAVUserManagerUserSession@@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEB_K@1@$$QEAV?$tuple@$$V@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,UserManagerUserSession *>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,UserManagerUserSession *>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,UserManagerUserSession *>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,UserManagerUserSession *>,void *> *,std::piecewise_construct_t const &,std::tuple<unsigned __int64 const &> &&,std::tuple<> &&)
0x18002d693  mov     rcx, rax
0x18002d696  mov     rbx, [rax+8]
0x18002d69a  xor     eax, eax
0x18002d69c  mov     [rcx+8], rax
0x18002d6a0  lea     rcx, [rsp+0E8h+pSid]
0x18002d6a5  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4_CRM_CLIENT_ID@@PEAX@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_CRM_CLIENT_ID const,void *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_CRM_CLIENT_ID const,void *>,void *>>>(void)
0x18002d6aa  movups  xmm0, xmmword ptr [rsp+0E8h+var_98]
0x18002d6af  movaps  xmmword ptr [rsp+0E8h+var_98], xmm0
0x18002d6b4  mov     r8, rbx
0x18002d6b7  lea     rdx, [rsp+0E8h+var_98]
0x18002d6bc  lea     rcx, [rsi+10h]
0x18002d6c0  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CEncryptedCredentials *>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ulong const,CEncryptedCredentials *>,void *> *>,std::_Tree_node<std::pair<ulong const,CEncryptedCredentials *>,void *> * const)
0x18002d6c5  mov     r13, rax
0x18002d6c8  xor     ebx, ebx
0x18002d6ca  mov     r13, [r13+28h]
0x18002d6ce  test    r13, r13
0x18002d6d1  jz      short loc_18002D6E6
0x18002d6d3  mov     rdx, [r14]; pSid2
0x18002d6d6  mov     rcx, [r13+28h]; pSid1
0x18002d6da  call    cs:__imp_EqualSid
0x18002d6e0  test    eax, eax
0x18002d6e2  cmovz   r13, rbx
0x18002d6e6  mov     ebx, 0FFFFFFFFh
0x18002d6eb  test    r13, r13
0x18002d6ee  jnz     loc_18002D981
0x18002d6f4  test    r15, r15
0x18002d6f7  jnz     short loc_18002D733
0x18002d6f9  jmp     short loc_18002D73D
0x18002d6fb  mov     ebx, 0FFFFFFFFh
0x18002d700  mov     rsi, [rsp+0E8h+arg_0]
0x18002d708  mov     r15, [rsp+0E8h+nSubAuthority]
0x18002d710  mov     r14, [rsp+0E8h+arg_8]
0x18002d718  mov     rax, [rsp+0E8h+var_70]
0x18002d71d  mov     [rsp+0E8h+var_78], rax
0x18002d722  mov     r13, [rsp+0E8h+arg_18]
0x18002d72a  movzx   r12d, [rsp+0E8h+var_68]
0x18002d733  cmp     qword ptr [r15], 0
0x18002d737  jnz     loc_18002D9FC
0x18002d73d  mov     rcx, [r14]
0x18002d740  mov     [rsp+0E8h+pSid], rcx
0x18002d745  mov     rdi, [r14+8]
0x18002d749  mov     [rsp+0E8h+var_98], rdi
0x18002d74e  mov     [rsp+0E8h+var_B0], rdi
0x18002d753  lock inc dword ptr [rdi]
0x18002d756  mov     rax, [rsi+30h]
0x18002d75a  mov     [rsp+0E8h+var_A8], rax
0x18002d75f  mov     r15, [rax+8]
0x18002d763  xor     edx, edx
0x18002d765  mov     [rsp+0E8h+var_54], edx
0x18002d76c  cmp     [r15+19h], dl
0x18002d770  jnz     loc_18002D8AC
0x18002d776  mov     rax, [r15+20h]
0x18002d77a  mov     [rsp+0E8h+arg_18], rax
0x18002d782  test    rax, rax
0x18002d785  jz      loc_18002D875
0x18002d78b  test    rcx, rcx
0x18002d78e  jz      loc_18002D875
0x18002d794  mov     rcx, rax; pSid
0x18002d797  call    cs:__imp_GetSidSubAuthorityCount
0x18002d79d  mov     rdi, rax
0x18002d7a0  mov     rcx, [rsp+0E8h+pSid]; pSid
0x18002d7a5  call    cs:__imp_GetSidSubAuthorityCount
0x18002d7ab  movzx   ecx, byte ptr [rax]
0x18002d7ae  cmp     [rdi], cl
0x18002d7b0  jb      loc_18002D87C
0x18002d7b6  mov     rcx, [rsp+0E8h+arg_18]; pSid
0x18002d7be  call    cs:__imp_GetSidSubAuthorityCount
0x18002d7c4  mov     rdi, rax
0x18002d7c7  mov     rcx, [rsp+0E8h+pSid]; pSid
0x18002d7cc  call    cs:__imp_GetSidSubAuthorityCount
0x18002d7d2  movzx   ecx, byte ptr [rax]
0x18002d7d5  cmp     [rdi], cl
0x18002d7d7  ja      loc_18002D88C
0x18002d7dd  xor     dil, dil
0x18002d7e0  mov     byte ptr [rsp+0E8h+arg_0], dil
0x18002d7e8  mov     rcx, [rsp+0E8h+arg_18]; pSid
0x18002d7f0  call    cs:__imp_GetSidSubAuthorityCount
0x18002d7f6  mov     rcx, [rsp+0E8h+pSid]; pSid
0x18002d7fb  cmp     dil, [rax]
0x18002d7fe  jnb     loc_18002D891
0x18002d804  movzx   eax, dil
0x18002d808  mov     dword ptr [rsp+0E8h+nSubAuthority], eax
0x18002d80f  mov     edx, eax; nSubAuthority
0x18002d811  call    cs:__imp_GetSidSubAuthority
0x18002d817  mov     rdi, rax
0x18002d81a  mov     edx, dword ptr [rsp+0E8h+nSubAuthority]; nSubAuthority
0x18002d821  mov     rcx, [rsp+0E8h+arg_18]; pSid
0x18002d829  call    cs:__imp_GetSidSubAuthority
0x18002d82f  mov     ecx, [rdi]
0x18002d831  cmp     [rax], ecx
0x18002d833  mov     rcx, [rsp+0E8h+pSid]; pSid
  ... truncated ...
```
