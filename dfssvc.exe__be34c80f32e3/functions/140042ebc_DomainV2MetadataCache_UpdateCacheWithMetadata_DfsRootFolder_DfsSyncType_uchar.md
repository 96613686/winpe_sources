# DomainV2MetadataCache::UpdateCacheWithMetadata(DfsRootFolder::DfsSyncType,uchar)

- ea: `0x140042ebc`
- end: `0x14004322e`
- name: `?UpdateCacheWithMetadata@DomainV2MetadataCache@@AEAAKW4DfsSyncType@DfsRootFolder@@E@Z`
- size: `882`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update`

## callers

- `0x14003f344`

## callees

- `0x140005b28`
- `0x140006bf0`
- `0x1400096ac`
- `0x1400096d8`
- `0x14000971c`
- `0x1400333f0`
- `0x140035f14`
- `0x14003ef48`
- `0x1400401ac`
- `0x1400413a8`
- `0x140042a38`
- `0x140042ebc`
- `0x140049a00`
- `0x14004a0a8`
- `0x14005bf90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140043194`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140043194`
- `WLDAP32!__imp_ldap_first_entry` at `0x1400430b2`
- `WLDAP32!__imp_ldap_first_entry` at `0x1400430b2`
- `WLDAP32!__imp_ldap_next_entry` at `0x14004317d`
- `WLDAP32!__imp_ldap_next_entry` at `0x14004317d`
- `WLDAP32!__imp_ldap_msgfree` at `0x140043138`
- `WLDAP32!__imp_ldap_msgfree` at `0x140043138`

## string_xrefs

- `0x140043016`: `(|(objectClass=msDFS-Namespacev2)(objectClass=msDFS-Linkv2)(objectClass=msDFS-DeletedLinkv2))`
- `0x140042fca`: `(|(objectClass=msDFS-Namespacev2)(objectClass=msDFS-Linkv2))`

## pseudocode

```c
__int64 __fastcall DomainV2MetadataCache::UpdateCacheWithMetadata(__int64 a1, int a2, char a3)
{
  unsigned int LastError; // ebx
  LONG v7; // r9d
  _UNKNOWN **v8; // rdx
  unsigned int *v9; // rcx
  const unsigned __int16 *v10; // rdi
  LDAP **v11; // r15
  CLdap *v12; // rcx
  int v13; // r14d
  LDAPMessage *v14; // rax
  LDAPMessage *v15; // r12
  LDAPMessage *i; // rax
  LDAPMessage *v17; // rdi
  DomainV2MetadataCache *v18; // rcx
  struct _DFS_DOMAINV2_METADATA *v19; // rdx
  struct _DFS_DOMAINV2_METADATA *v20; // rcx
  CLdap *v21; // rcx
  struct _DFS_DOMAINV2_METADATA *Block; // [rsp+80h] [rbp+48h] BYREF
  int v24; // [rsp+88h] [rbp+50h]
  unsigned __int8 v25; // [rsp+90h] [rbp+58h] BYREF
  struct l_timeval v26; // [rsp+98h] [rbp+60h] BYREF

  v24 = a2;
  LastError = 0;
  v25 = 0;
  Block = 0;
  v7 = *((_DWORD *)CConfigurationSettings::_GetInstance((unsigned int *)a1) + 7);
  v26.tv_usec = 0;
  v26.tv_sec = v7;
  v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
  v9 = pWppControl;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x200) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_q(*((_QWORD *)pWppControl + 2), 10, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, a1);
    v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
    v9 = pWppControl;
  }
  if ( a3 )
  {
    if ( v8 != &WPP_GLOBAL_Control && v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)v9 + 2), 11, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids);
      v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
      v9 = pWppControl;
    }
    v10 = L"(objectClass=msDFS-Namespacev2)";
  }
  else if ( a2 == 1 )
  {
    if ( v8 != &WPP_GLOBAL_Control && v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)v9 + 2), 13, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids);
      v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
      v9 = pWppControl;
    }
    v10 = L"(|(objectClass=msDFS-Namespacev2)(objectClass=msDFS-Linkv2)(objectClass=msDFS-DeletedLinkv2))";
    if ( *(_QWORD *)(a1 + 1168) )
      v10 = *(const unsigned __int16 **)(a1 + 1168);
  }
  else
  {
    if ( v8 != &WPP_GLOBAL_Control && v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 2u )
      WPP_SF_(*((_QWORD *)v9 + 2), 12, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids);
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 52));
    v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
    v10 = L"(|(objectClass=msDFS-Namespacev2)(objectClass=msDFS-Linkv2))";
    v9 = pWppControl;
  }
  if ( v8 != &WPP_GLOBAL_Control && v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
    WPP_SF_S(*((_QWORD *)v9 + 2), 14, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, v10);
  v11 = (LDAP **)(a1 + 64);
  if ( (unsigned int)CLdap::InitPagedSearch(
                       (CLdap *)(a1 + 64),
                       *(const unsigned __int16 **)(a1 + 1144),
                       0,
                       v10,
                       a3 == 0 ? 2 : 0) )
  {
    v13 = 1;
    while ( v13 )
    {
      v14 = CLdap::ContinuePagedSearch((CLdap *)(a1 + 64), &v26);
      v15 = v14;
      if ( !v14 )
      {
        if ( (unsigned int)TlsGetValue(CLdap::gm_LdapErrorTlsIndex) != 94 )
          LastError = CLdap::GetLastError(v21);
        break;
      }
      for ( i = ldap_first_entry(*v11, v14); ; i = ldap_next_entry(*v11, v17) )
      {
        v17 = i;
        if ( !i )
          break;
        Block = 0;
        v25 = 0;
        LastError = DomainV2MetadataCache::GetMetadataFromLdapEntry((LDAP **)a1, i, &Block, &v25);
        if ( LastError && !v25 )
          goto LABEL_50;
        if ( v25 )
        {
          if ( Block )
          {
            --*((_DWORD *)Block + 14);
            if ( *((_QWORD *)Block + 13) )
              SHashReleaseReference(*(_QWORD *)(a1 + 16), Block);
            else
              DomainV2MetadataCache::ReleaseRootMetadataReference(v18, Block);
          }
          LastError = 0;
        }
        else
        {
          v19 = Block;
          if ( *((_QWORD *)Block + 13) )
          {
            if ( v24 == 1 )
            {
              *((_DWORD *)Block + 8) |= 1u;
              v19 = Block;
            }
            LastError = DomainV2MetadataCache::AddMetadataToCache((DomainV2MetadataCache *)a1, v19);
          }
          else
          {
            v20 = *(struct _DFS_DOMAINV2_METADATA **)(a1 + 24);
            if ( v20 )
            {
              DfsDomainV2FreeMetadata(v20);
              v19 = Block;
            }
            *(_QWORD *)(a1 + 24) = v19;
          }
          if ( LastError )
          {
LABEL_50:
            v13 = 0;
            break;
          }
        }
        Block = 0;
      }
      ldap_msgfree(v15);
    }
    CLdap::ClosePagedSearch((CLdap *)(a1 + 64));
  }
  else
  {
    LastError = CLdap::GetLastError(v12);
  }
  if ( LastError && Block )
    DfsDomainV2FreeMetadata(Block);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (((1 << (LastError != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_qd(*((_QWORD *)pWppControl + 2), 15, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, a1, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x140042ebc  mov     [rsp-40h+arg_8], edx
0x140042ec0  push    rbp
0x140042ec1  push    rbx
0x140042ec2  push    rsi
0x140042ec3  push    rdi
0x140042ec4  push    r12
0x140042ec6  push    r13
0x140042ec8  push    r14
0x140042eca  push    r15
0x140042ecc  mov     rbp, rsp
0x140042ecf  sub     rsp, 38h
0x140042ed3  xor     ebx, ebx
0x140042ed5  mov     [rbp+arg_10], 0
0x140042ed9  and     [rbp+Block], rbx
0x140042edd  mov     r14b, r8b
0x140042ee0  mov     edi, edx
0x140042ee2  mov     rsi, rcx
0x140042ee5  call    ?_GetInstance@CConfigurationSettings@@SAPEAV1@PEAK@Z; CConfigurationSettings::_GetInstance(ulong *)
0x140042eea  mov     r9d, [rax+1Ch]
0x140042eee  and     [rbp+arg_18.tv_usec], ebx
0x140042ef1  mov     [rbp+arg_18.tv_sec], r9d
0x140042ef5  mov     rdx, cs:WPP_GLOBAL_Control
0x140042efc  lea     r12, WPP_GLOBAL_Control
0x140042f03  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140042f0a  mov     r13d, 200h
0x140042f10  lea     r15, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x140042f17  cmp     rdx, r12
0x140042f1a  jz      short loc_140042F4D
0x140042f1c  test    rcx, rcx
0x140042f1f  jz      short loc_140042F4D
0x140042f21  test    [rcx+1Ch], r13d
0x140042f25  jz      short loc_140042F4D
0x140042f27  cmp     byte ptr [rcx+19h], 3
0x140042f2b  jb      short loc_140042F4D
0x140042f2d  mov     rcx, [rcx+10h]
0x140042f31  lea     edx, [rbx+0Ah]
0x140042f34  mov     r9, rsi
0x140042f37  mov     r8, r15
0x140042f3a  call    WPP_SF_q
0x140042f3f  mov     rdx, cs:WPP_GLOBAL_Control
0x140042f46  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140042f4d  test    r14b, r14b
0x140042f50  jz      short loc_140042F93
0x140042f52  cmp     rdx, r12
0x140042f55  jz      short loc_140042F87
0x140042f57  test    rcx, rcx
0x140042f5a  jz      short loc_140042F87
0x140042f5c  test    byte ptr [rcx+1Ch], 20h
0x140042f60  jz      short loc_140042F87
0x140042f62  cmp     byte ptr [rcx+19h], 2
0x140042f66  jb      short loc_140042F87
0x140042f68  mov     rcx, [rcx+10h]
0x140042f6c  mov     edx, 0Bh
0x140042f71  mov     r8, r15
0x140042f74  call    WPP_SF_
0x140042f79  mov     rdx, cs:WPP_GLOBAL_Control
0x140042f80  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140042f87  lea     rdi, aObjectclassMsd; "(objectClass=msDFS-Namespacev2)"
0x140042f8e  jmp     loc_140043024
0x140042f93  cmp     edi, 1
0x140042f96  jz      short loc_140042FDA
0x140042f98  cmp     rdx, r12
0x140042f9b  jz      short loc_140042FBF
0x140042f9d  test    rcx, rcx
0x140042fa0  jz      short loc_140042FBF
0x140042fa2  test    byte ptr [rcx+1Ch], 20h
0x140042fa6  jz      short loc_140042FBF
0x140042fa8  cmp     byte ptr [rcx+19h], 2
0x140042fac  jb      short loc_140042FBF
0x140042fae  mov     rcx, [rcx+10h]
0x140042fb2  mov     edx, 0Ch
0x140042fb7  mov     r8, r15
0x140042fba  call    WPP_SF_
0x140042fbf  lock inc dword ptr [rsi+34h]
0x140042fc3  mov     rdx, cs:WPP_GLOBAL_Control
0x140042fca  lea     rdi, aObjectclassMsd_0; "(|(objectClass=msDFS-Namespacev2)(objec"...
0x140042fd1  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140042fd8  jmp     short loc_140043024
0x140042fda  cmp     rdx, r12
0x140042fdd  jz      short loc_14004300F
0x140042fdf  test    rcx, rcx
0x140042fe2  jz      short loc_14004300F
0x140042fe4  test    byte ptr [rcx+1Ch], 20h
0x140042fe8  jz      short loc_14004300F
0x140042fea  cmp     byte ptr [rcx+19h], 2
0x140042fee  jb      short loc_14004300F
0x140042ff0  mov     rcx, [rcx+10h]
0x140042ff4  mov     edx, 0Dh
0x140042ff9  mov     r8, r15
0x140042ffc  call    WPP_SF_
0x140043001  mov     rdx, cs:WPP_GLOBAL_Control
0x140043008  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14004300f  mov     rax, [rsi+490h]
0x140043016  lea     rdi, aObjectclassMsd_1; "(|(objectClass=msDFS-Namespacev2)(objec"...
0x14004301d  test    rax, rax
0x140043020  cmovnz  rdi, rax
0x140043024  cmp     rdx, r12
0x140043027  jz      short loc_14004304E
0x140043029  test    rcx, rcx
0x14004302c  jz      short loc_14004304E
0x14004302e  test    byte ptr [rcx+1Ch], 20h
0x140043032  jz      short loc_14004304E
0x140043034  cmp     byte ptr [rcx+19h], 3
0x140043038  jb      short loc_14004304E
0x14004303a  mov     rcx, [rcx+10h]
0x14004303e  mov     edx, 0Eh
0x140043043  mov     r9, rdi
0x140043046  mov     r8, r15
0x140043049  call    WPP_SF_S
0x14004304e  mov     rdx, [rsi+478h]; unsigned __int16 *
0x140043055  lea     r15, [rsi+40h]
0x140043059  neg     r14b
0x14004305c  mov     r9, rdi; unsigned __int16 *
0x14004305f  mov     rcx, r15; this
0x140043062  sbb     eax, eax
0x140043064  xor     r8d, r8d; unsigned __int16 **
0x140043067  not     eax
0x140043069  and     eax, 2
0x14004306c  mov     [rsp+38h+ScopeOfSearch], eax; ScopeOfSearch
0x140043070  call    ?InitPagedSearch@CLdap@@QEAAHPEBGPEAPEBG0K@Z; CLdap::InitPagedSearch(ushort const *,ushort const * *,ushort const *,ulong)
0x140043075  test    eax, eax
0x140043077  jnz     short loc_140043085
0x140043079  call    ?GetLastError@CLdap@@QEAAKXZ; CLdap::GetLastError(void)
0x14004307e  mov     ebx, eax
0x140043080  jmp     loc_1400431BB
0x140043085  mov     r14d, 1
0x14004308b  test    r14d, r14d
0x14004308e  jz      loc_1400431AC
0x140043094  lea     rdx, [rbp+arg_18]; struct l_timeval *
0x140043098  mov     rcx, r15; this
0x14004309b  call    ?ContinuePagedSearch@CLdap@@QEAAPEAUldapmsg@@PEAUl_timeval@@@Z; CLdap::ContinuePagedSearch(l_timeval *)
0x1400430a0  mov     r12, rax
0x1400430a3  test    rax, rax
0x1400430a6  jz      loc_14004318E
0x1400430ac  mov     rcx, [r15]; ld
0x1400430af  mov     rdx, rax; res
0x1400430b2  call    cs:__imp_ldap_first_entry
0x1400430b9  nop     dword ptr [rax+rax+00h]
0x1400430be  mov     rdi, rax
0x1400430c1  test    rax, rax
0x1400430c4  jz      short loc_140043135
0x1400430c6  and     [rbp+Block], 0
0x1400430cb  lea     r9, [rbp+arg_10]; unsigned __int8 *
0x1400430cf  lea     r8, [rbp+Block]; struct _DFS_DOMAINV2_METADATA **
0x1400430d3  mov     [rbp+arg_10], 0
0x1400430d7  mov     rdx, rax; entry
0x1400430da  mov     rcx, rsi; this
0x1400430dd  call    ?GetMetadataFromLdapEntry@DomainV2MetadataCache@@AEAAKPEAUldapmsg@@PEAPEAU_DFS_DOMAINV2_METADATA@@PEAE@Z; DomainV2MetadataCache::GetMetadataFromLdapEntry(ldapmsg *,_DFS_DOMAINV2_METADATA * *,uchar *)
0x1400430e2  mov     ebx, eax
0x1400430e4  mov     al, [rbp+arg_10]
0x1400430e7  test    ebx, ebx
0x1400430e9  jz      short loc_1400430EF
0x1400430eb  test    al, al
0x1400430ed  jz      short loc_140043132
0x1400430ef  test    al, al
0x1400430f1  jnz     short loc_140043149
0x1400430f3  mov     rdx, [rbp+Block]
0x1400430f7  cmp     qword ptr [rdx+68h], 0
0x1400430fc  jnz     short loc_140043116
0x1400430fe  mov     rcx, [rsi+18h]; Block
0x140043102  test    rcx, rcx
0x140043105  jz      short loc_140043110
0x140043107  call    ?DfsDomainV2FreeMetadata@@YAXPEAU_DFS_DOMAINV2_METADATA@@@Z; DfsDomainV2FreeMetadata(_DFS_DOMAINV2_METADATA *)
0x14004310c  mov     rdx, [rbp+Block]
0x140043110  mov     [rsi+18h], rdx
0x140043114  jmp     short loc_14004312E
0x140043116  cmp     [rbp+arg_8], 1
0x14004311a  jnz     short loc_140043124
0x14004311c  or      dword ptr [rdx+20h], 1
0x140043120  mov     rdx, [rbp+Block]; struct _DFS_DOMAINV2_METADATA *
0x140043124  mov     rcx, rsi; this
0x140043127  call    ?AddMetadataToCache@DomainV2MetadataCache@@QEAAKPEAU_DFS_DOMAINV2_METADATA@@@Z; DomainV2MetadataCache::AddMetadataToCache(_DFS_DOMAINV2_METADATA *)
0x14004312c  mov     ebx, eax
0x14004312e  test    ebx, ebx
0x140043130  jz      short loc_140043172
0x140043132  xor     r14d, r14d
0x140043135  mov     rcx, r12; res
0x140043138  call    cs:__imp_ldap_msgfree
0x14004313f  nop     dword ptr [rax+rax+00h]
0x140043144  jmp     loc_14004308B
0x140043149  mov     rax, [rbp+Block]
0x14004314d  test    rax, rax
0x140043150  jz      short loc_140043170
0x140043152  dec     dword ptr [rax+38h]
0x140043155  mov     rdx, [rbp+Block]; struct _DFS_DOMAINV2_METADATA *
0x140043159  cmp     qword ptr [rdx+68h], 0
0x14004315e  jnz     short loc_140043167
0x140043160  call    ?ReleaseRootMetadataReference@DomainV2MetadataCache@@AEAAXPEAU_DFS_DOMAINV2_METADATA@@@Z; DomainV2MetadataCache::ReleaseRootMetadataReference(_DFS_DOMAINV2_METADATA *)
0x140043165  jmp     short loc_140043170
0x140043167  mov     rcx, [rsi+10h]
0x14004316b  call    SHashReleaseReference
0x140043170  xor     ebx, ebx
0x140043172  and     [rbp+Block], 0
0x140043177  mov     rdx, rdi; entry
0x14004317a  mov     rcx, [r15]; ld
0x14004317d  call    cs:__imp_ldap_next_entry
0x140043184  nop     dword ptr [rax+rax+00h]
0x140043189  jmp     loc_1400430BE
0x14004318e  mov     ecx, cs:?gm_LdapErrorTlsIndex@CLdap@@0KA; dwTlsIndex
0x140043194  call    cs:__imp_TlsGetValue
0x14004319b  nop     dword ptr [rax+rax+00h]
0x1400431a0  cmp     eax, 5Eh ; '^'
0x1400431a3  jz      short loc_1400431AC
0x1400431a5  call    ?GetLastError@CLdap@@QEAAKXZ; CLdap::GetLastError(void)
0x1400431aa  mov     ebx, eax
0x1400431ac  mov     rcx, r15; this
0x1400431af  call    ?ClosePagedSearch@CLdap@@QEAAXXZ; CLdap::ClosePagedSearch(void)
0x1400431b4  lea     r12, WPP_GLOBAL_Control
0x1400431bb  test    ebx, ebx
0x1400431bd  jz      short loc_1400431CD
0x1400431bf  mov     rcx, [rbp+Block]; Block
0x1400431c3  test    rcx, rcx
0x1400431c6  jz      short loc_1400431CD
0x1400431c8  call    ?DfsDomainV2FreeMetadata@@YAXPEAU_DFS_DOMAINV2_METADATA@@@Z; DfsDomainV2FreeMetadata(_DFS_DOMAINV2_METADATA *)
0x1400431cd  cmp     cs:WPP_GLOBAL_Control, r12
0x1400431d4  jz      short loc_14004321A
0x1400431d6  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400431dd  test    rcx, rcx
0x1400431e0  jz      short loc_14004321A
0x1400431e2  mov     eax, ebx
0x1400431e4  neg     eax
0x1400431e6  sbb     edx, edx
0x1400431e8  and     edx, 0FFFFFFECh
0x1400431eb  add     edx, 1Fh
0x1400431ee  bts     r13d, edx
0x1400431f2  test    [rcx+1Ch], r13d
0x1400431f6  jz      short loc_14004321A
0x1400431f8  cmp     byte ptr [rcx+19h], 3
0x1400431fc  jb      short loc_14004321A
0x1400431fe  mov     rcx, [rcx+10h]
0x140043202  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x140043209  mov     edx, 0Fh
0x14004320e  mov     [rsp+38h+ScopeOfSearch], ebx
0x140043212  mov     r9, rsi
0x140043215  call    WPP_SF_qd
0x14004321a  mov     eax, ebx
0x14004321c  add     rsp, 38h
0x140043220  pop     r15
0x140043222  pop     r14
0x140043224  pop     r13
0x140043226  pop     r12
0x140043228  pop     rdi
0x140043229  pop     rsi
0x14004322a  pop     rbx
0x14004322b  pop     rbp
0x14004322c  retn
```
