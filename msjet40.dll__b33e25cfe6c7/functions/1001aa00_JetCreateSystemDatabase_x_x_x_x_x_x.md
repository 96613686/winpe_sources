# JetCreateSystemDatabase(x,x,x,x,x,x)

- ea: `0x1001aa00`
- end: `0x1001b1b4`
- name: `_JetCreateSystemDatabase@24`
- size: `1972`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation`

## callees

- `0x10018b00`
- `0x10019030`
- `0x1001a180`
- `0x1001a700`
- `0x1001a8f0`
- `0x1001aa00`
- `0x10026a90`
- `0x10027930`
- `0x10028610`
- `0x1003a2a0`
- `0x1003bcc0`
- `0x1003bf60`
- `0x1003e6a0`
- `0x1003ecb0`
- `0x100429d0`
- `0x10043090`
- `0x10043260`
- `0x10043840`
- `0x100490be`
- `0x1008b960`
- `0x10094e50`
- `0x10117190`
- `0x10122f60`
- `0x1012398c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001aaeb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001aaeb`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1001ac69`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1001ac8a`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1001acb4`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1001ac69`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1001ac8a`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1001acb4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1001ab1c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1001ab1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001ab46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001ab9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001ab46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001ab9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001ab2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001ab2b`

## string_xrefs

- `0x1001af26`: `Procedure	MSysUserMemberships UserName Text; Select		Distinct MSysAccounts_1.Name From		(MSysAccounts inner join MSysGroups on MSysAccounts.SID = MSysGroups.UserSID) 			inner join MSysAccounts as MSysAccounts_1 on MSysGroups.GroupSID = MSysAccounts_1.SID Where		MSysAccounts.name = UserName and 			MSysAccounts.FGroup = 0 and 			MSysAccounts_1.FGroup <> 0;`
- `0x1001afbc`: `Procedure	MSysGroupMembers GroupName Text; Select		Distinct MSysAccounts_1.Name From		(MSysAccounts inner join MSysGroups on MSysAccounts.SID = MSysGroups.GroupSID) 			inner join MSysAccounts as MSysAccounts_1 on MSysGroups.UserSID = MSysAccounts_1.SID Where		MSysAccounts.name = GroupName and 			MSysAccounts.FGroup <> 0 and 			MSysAccounts_1.FGroup = 0;`

## pseudocode

```c
int __stdcall JetCreateSystemDatabase(
        const unsigned __int16 *a1,
        int a2,
        _WORD *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        int a6)
{
  _WORD *v6; // ecx
  struct _RTL_CRITICAL_SECTION *v8; // eax
  int inited; // esi
  unsigned int v11; // edi
  int v12; // ebx
  int v13; // eax
  int Database; // esi
  JET_INSTANCE v15; // eax
  Session *v16; // edi
  int IsibOfSesid; // eax
  int v18; // ebx
  _BYTE *v19; // esi
  wint_t *v20; // edi
  char v21; // al
  wint_t *v22; // ebx
  _BYTE *v23; // esi
  char v24; // al
  wint_t *v25; // edi
  _BYTE *v26; // esi
  char v27; // al
  int i; // ebx
  int v29; // ebx
  int v30; // eax
  int v31; // eax
  int v32; // [esp-10h] [ebp-D0h]
  int v33; // [esp-8h] [ebp-C8h]
  int v34; // [esp-8h] [ebp-C8h]
  int v35; // [esp-4h] [ebp-C4h]
  int v36; // [esp-4h] [ebp-C4h]
  int v37; // [esp+Ch] [ebp-B4h] BYREF
  int v38; // [esp+10h] [ebp-B0h] BYREF
  DWORD v39; // [esp+14h] [ebp-ACh] BYREF
  DWORD v40; // [esp+18h] [ebp-A8h]
  Session *v41; // [esp+1Ch] [ebp-A4h] BYREF
  int v42; // [esp+20h] [ebp-A0h] BYREF
  int v43; // [esp+24h] [ebp-9Ch]
  const unsigned __int16 *v44; // [esp+28h] [ebp-98h]
  wint_t *v45; // [esp+2Ch] [ebp-94h]
  wint_t *v46; // [esp+30h] [ebp-90h]
  wint_t *v47; // [esp+34h] [ebp-8Ch]
  _BYTE v48[132]; // [esp+38h] [ebp-88h] BYREF

  v6 = a3;
  v43 = a2;
  v45 = a3;
  v47 = (wint_t *)a5;
  v44 = a1;
  v46 = (wint_t *)a4;
  if ( !a3 || !a4 || !a5 )
    return -1003;
  while ( *v6++ )
    ;
  if ( (unsigned int)(v6 - (a3 + 1)) > 0x14 || wcslen(a4) > 0x27 || wcslen(a5) > 0x27 || !a1 || wcslen(a1) > 0x104 )
    return -1003;
  if ( critJet )
  {
    EnterCriticalSection(critJet);
  }
  else
  {
    v8 = (struct _RTL_CRITICAL_SECTION *)_malloc(0x18u);
    critJet = v8;
    if ( !v8 )
      return -1011;
    InitializeCriticalSection(v8);
    EnterCriticalSection(critJet);
  }
  inited = ErrInitInstance(&v39);
  if ( inited >= 0 )
  {
    v11 = v39;
    v12 = v39 + 144;
    v40 = v39 + 144;
    v13 = ErrInit(v39);
    Database = v13;
    if ( v13 < 0 )
    {
      if ( v13 != -1030 )
        ReleaseTib(v11);
      v12 = 0;
      v40 = 0;
    }
    LeaveCriticalSection(critJet);
    if ( Database >= 0 )
    {
      Database = ErrBeginSession(v12, (int)&v41, (void *)&dword_10008698, (int)&dword_10008698);
      v15 = v12;
      if ( Database >= 0 )
      {
        v16 = v41;
        Database = ErrIsamCreateDatabase((int)v41, v43, (int)&v42, a6 | 0x80);
        v39 = v12;
        if ( Database >= 0 )
        {
          IsibOfSesid = UtilGetIsibOfSesid(v16);
          v18 = v42;
          v32 = v42;
          mpdbidiiscb[v42] = dword_1016EAF8[26 * IsibOfSesid];
          Database = ErrREPOpenDatabase(v16, v32, a6, 0xFFFF, 0);
          if ( Database >= 0 )
          {
            memset(v48, 32, 0x80u);
            v19 = &v48[1];
            v20 = v45;
            v39 = v40;
            do
            {
              v21 = _towupper(*v20);
              *v19 = v21;
              ++v20;
              ++v19;
            }
            while ( v21 );
            v22 = v46;
            v23 = &v48[22];
            do
            {
              v24 = _towupper(*v22);
              *v23 = v24;
              ++v22;
              ++v23;
            }
            while ( v24 );
            v25 = v47;
            v26 = &v48[62];
            do
            {
              v27 = _towupper(*v25);
              *v26 = v27;
              ++v25;
              ++v26;
            }
            while ( v27 );
            v16 = v41;
            for ( i = 0; i != 104; i += 8 )
            {
              DesSetKey("rkatpvjg");
              DesDoDES(&v48[i + 1], 0);
              DesSetKey("jshcsabn");
              DesDoDES(&v48[i + 1], 1);
              DesSetKey("rkatpvjg");
              DesDoDES(&v48[i + 1], 0);
            }
            v29 = v42;
            v48[0] = 1;
            v30 = ErrDispOpenTable(v16, v42, &v37, L"MSysAccounts", 0x80000000);
            Database = v30;
            if ( v30 >= 0 )
            {
              Database = ErrCreateAccount(v37, L"Admins", 0, v48, 102, 1);
              if ( Database >= 0 )
              {
                Database = ErrCreateAccount(v37, L"Users", 0, &rgbSidUsers, 2, 1);
                if ( Database >= 0 )
                {
                  Database = ErrCreateAccount(v37, L"Engine", 0, &rgbSidEngine, 2, 0);
                  if ( Database >= 0 )
                  {
                    Database = ErrCreateAccount(v37, L"Creator", 0, &rgbSidCreator, 2, 0);
                    if ( Database >= 0 )
                    {
                      Database = ErrCreateAccount(v37, L"admin", &dword_10008698, rgbSidAdmin, 2, 0);
                      if ( Database >= 0 )
                      {
                        Database = ErrDispCloseTable(v16, v37);
                        if ( Database >= 0 )
                        {
                          v31 = ErrDispOpenTable(v16, v29, &v37, L"MSysGroups", 0x80000000);
                          Database = v31;
                          if ( v31 >= 0 )
                          {
                            Database = ErrCreateGroup(v48, 102, v33, v35);
                            if ( Database >= 0 )
                            {
                              Database = ErrCreateGroup(&rgbSidUsers, 2, v34, v36);
                              if ( Database >= 0 )
                              {
                                Database = ErrDispCloseTable(v16, v37);
                                if ( Database >= 0 )
                                {
                                  Database = ErrQodefSecCreateVtQoDef(v16, v29, (int)L"MSysUserList", (int)&v37, 0, 1);
                                  if ( Database >= 0 )
                                  {
                                    Database = JetSetQoSql(
                                                 v16,
                                                 v37,
                                                 L"Procedure\tMSysUserList; Select\t\tMSysAccounts.Name From\t\tMSysAccoun"
                                                  "ts Where\t\tMSysAccounts.FGroup = 0 Order by\tMSysAccounts.Name ",
                                                 128,
                                                 0,
                                                 0);
                                    if ( Database >= 0 )
                                    {
                                      ErrDispCloseTable(v16, v37);
                                      Database = ErrQodefSecCreateVtQoDef(
                                                   v16,
                                                   v29,
                                                   (int)L"MSysUserMemberships",
                                                   (int)&v37,
                                                   0,
                                                   1);
                                      if ( Database >= 0 )
                                      {
                                        Database = JetSetQoSql(
                                                     v16,
                                                     v37,
                                                     L"Procedure\tMSysUserMemberships UserName Text; Select\t\tDistinct MS"
                                                      "ysAccounts_1.Name From\t\t(MSysAccounts inner join MSysGroups on M"
                                                      "SysAccounts.SID = MSysGroups.UserSID) \t\t\tinner join MSysAccount"
                                                      "s as MSysAccounts_1 on MSysGroups.GroupSID = MSysAccounts_1.SID Wh"
                                                      "ere\t\tMSysAccounts.name = UserName and \t\t\tMSysAccounts.FGroup "
                                                      "= 0 and \t\t\tMSysAccounts_1.FGroup <> 0;",
                                                     357,
                                                     0,
                                                     0);
                                        if ( Database >= 0 )
                                        {
                                          ErrDispCloseTable(v16, v37);
                                          Database = ErrQodefSecCreateVtQoDef(
                                                       v16,
                                                       v29,
                                                       (int)L"MSysGroupList",
                                                       (int)&v37,
                                                       0,
                                                       1);
                                          if ( Database >= 0 )
                                          {
                                            Database = JetSetQoSql(
                                                         v16,
                                                         v37,
                                                         L"Procedure\tMSysGroupList; Select\t\tMSysAccounts.Name From\t\tM"
                                                          "SysAccounts Where\t\tMSysAccounts.FGroup <> 0 Order by\tMSysAccounts.Name ",
                                                         130,
                                                         0,
                                                         0);
                                            if ( Database >= 0 )
                                            {
                                              ErrDispCloseTable(v16, v37);
                                              Database = ErrQodefSecCreateVtQoDef(
                                                           v16,
                                                           v29,
                                                           (int)L"MSysGroupMembers",
                                                           (int)&v37,
                                                           0,
                                                           1);
                                              if ( Database >= 0 )
                                              {
                                                Database = JetSetQoSql(
                                                             v16,
                                                             v37,
                                                             L"Procedure\tMSysGroupMembers GroupName Text; Select\t\tDisti"
                                                              "nct MSysAccounts_1.Name From\t\t(MSysAccounts inner join M"
                                                              "SysGroups on MSysAccounts.SID = MSysGroups.GroupSID) \t\t\t"
                                                              "inner join MSysAccounts as MSysAccounts_1 on MSysGroups.Us"
                                                              "erSID = MSysAccounts_1.SID Where\t\tMSysAccounts.name = Gr"
                                                              "oupName and \t\t\tMSysAccounts.FGroup <> 0 and \t\t\tMSysA"
                                                              "ccounts_1.FGroup = 0;",
                                                             356,
                                                             0,
                                                             0);
                                                if ( Database >= 0 )
                                                {
                                                  ErrDispCloseTable(v16, v37);
                                                  Database = ErrDispGetObjidFromName(
                                                               v16,
                                                               v29,
                                                               L"Tables",
                                                               L"MSysUserList",
                                                               &v38);
                                                  if ( Database >= 0 )
                                                  {
                                                    Database = ErrSecSetOwner(v16, v29, v38, &rgbSidEngine, 2);
                                                    if ( Database >= 0 )
                                                    {
                                                      Database = ErrDispGetObjidFromName(
                                                                   v16,
                                                                   v29,
                                                                   L"Tables",
                                                                   L"MSysUserMemberships",
                                                                   &v38);
                                                      if ( Database >= 0 )
                                                      {
                                                        Database = ErrSecSetOwner(v16, v29, v38, &rgbSidEngine, 2);
                                                        if ( Database >= 0 )
                                                        {
                                                          Database = ErrDispGetObjidFromName(
                                                                       v16,
                                                                       v29,
                                                                       L"Tables",
                                                                       L"MSysGroupList",
                                                                       &v38);
                                                          if ( Database >= 0 )
                                                          {
                                                            Database = ErrSecSetOwner(v16, v29, v38, &rgbSidEngine, 2);
                                                            if ( Database >= 0 )
                                                            {
                                                              Database = ErrDispGetObjidFromName(
                                                                           v16,
                                                                           v29,
                                                                           L"Tables",
                                                                           L"MSysGroupMembers",
                                                                           &v38);
                                                              if ( Database >= 0 )
                                                              {
                                                                Database = ErrSecSetOwner(
                                                                             v16,
                                                                             v29,
                                                                             v38,
                                                                             &rgbSidEngine,
                                                                             2);
                                                                if ( Database >= 0 )
                                                                {
                                                                  Database = ErrSecGiveDefPermissions(v16, v43, v29, 0);
                                                                  if ( Database >= 0 )
                                                                  {
                                                                    Database = ErrSecGiveDefPermissions(
                                                                                 v16,
                                                                                 v43,
                                                                                 v29,
                                                                                 0x80000000);
                                                                    if ( Database >= 0 )
                                                                    {
                                                                      Database = ErrDispGetObjidFromName(
                                                                                   v16,
                                                                                   v29,
                                                                                   L"Tables",
                                                                                   L"MSysAccounts",
                                                                                   &v38);
                                                                      if ( Database >= 0 )
                                                                      {
                                                                        Database = ErrSecSetOwner(
                                                                                     v16,
                                                                                     v29,
                                                                                     v38,
                                                                                     v48,
                                                                                     102);
                                                                        if ( Database >= 0 )
                                                                        {
                                                                          Database = ErrDispGetObjidFromName(
                                                                                       v16,
                                                                                       v29,
                                                                                       L"Tables",
                                                                                       L"MSysGroups",
                                                                                       &v38);
                                                                          if ( Database >= 0 )
                                                                          {
                                                                            Database = ErrSecSetOwner(
                                                                                         v16,
                                                                                         v29,
                                                                                         v38,
                                                                                         v48,
                                                                                         102);
                                                                            if ( Database >= 0 )
                                                                              Database = ErrDispCloseDatabase(
                                                                                           v16,
                                                                                           v29,
                                                                                           0);
                                                                          }
                                                                        }
                                                                      }
                                                                    }
                                                                  }
                                                                }
                                                              }
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                          else if ( v31 == -1305 )
                          {
                            Database = -1909;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
            else if ( v30 == -1305 )
            {
              Database = -1908;
            }
          }
          else
          {
            ErrDispCloseDatabase(v16, v18, 0);
            v39 = v40;
          }
        }
        ErrEndSession(v16);
        v15 = v39;
      }
      JetTerm(v15);
    }
    return Database;
  }
  else
  {
    LeaveCriticalSection(critJet);
    return inited;
  }
}

```

## disassembly

```asm
0x1001aa00  mov     edi, edi
0x1001aa02  push    ebp
0x1001aa03  mov     ebp, esp
0x1001aa05  and     esp, 0FFFFFFF8h
0x1001aa08  sub     esp, 0B4h
0x1001aa0e  mov     eax, ___security_cookie
0x1001aa13  xor     eax, esp
0x1001aa15  mov     [esp+0B4h+var_4], eax
0x1001aa1c  mov     ecx, [ebp+arg_8]
0x1001aa1f  mov     eax, [ebp+arg_4]
0x1001aa22  mov     edx, [ebp+arg_10]
0x1001aa25  mov     [esp+0B4h+var_9C], eax
0x1001aa29  mov     [esp+0B4h+var_94], ecx
0x1001aa2d  mov     [esp+0B4h+var_8C], edx
0x1001aa31  push    ebx
0x1001aa32  mov     ebx, [ebp+arg_0]
0x1001aa35  mov     [esp+0B8h+var_98], ebx
0x1001aa39  push    esi
0x1001aa3a  mov     esi, [ebp+arg_C]
0x1001aa3d  mov     [esp+0BCh+var_90], esi
0x1001aa41  push    edi
0x1001aa42  test    ecx, ecx
0x1001aa44  jz      loc_1001B198
0x1001aa4a  test    esi, esi
0x1001aa4c  jz      loc_1001B198
0x1001aa52  test    edx, edx
0x1001aa54  jz      loc_1001B198
0x1001aa5a  lea     edi, [ecx+2]
0x1001aa5d  nop     dword ptr [eax]
0x1001aa60  mov     ax, [ecx]
0x1001aa63  add     ecx, 2
0x1001aa66  test    ax, ax
0x1001aa69  jnz     short loc_1001AA60
0x1001aa6b  sub     ecx, edi
0x1001aa6d  sar     ecx, 1
0x1001aa6f  cmp     ecx, 14h
0x1001aa72  ja      loc_1001B198
0x1001aa78  mov     ecx, esi
0x1001aa7a  lea     esi, [ecx+2]
0x1001aa7d  nop     dword ptr [eax]
0x1001aa80  mov     ax, [ecx]
0x1001aa83  add     ecx, 2
0x1001aa86  test    ax, ax
0x1001aa89  jnz     short loc_1001AA80
0x1001aa8b  sub     ecx, esi
0x1001aa8d  sar     ecx, 1
0x1001aa8f  cmp     ecx, 27h ; '''
0x1001aa92  ja      loc_1001B198
0x1001aa98  mov     ecx, edx
0x1001aa9a  lea     edx, [ecx+2]
0x1001aa9d  nop     dword ptr [eax]
0x1001aaa0  mov     ax, [ecx]
0x1001aaa3  add     ecx, 2
0x1001aaa6  test    ax, ax
0x1001aaa9  jnz     short loc_1001AAA0
0x1001aaab  sub     ecx, edx
0x1001aaad  sar     ecx, 1
0x1001aaaf  cmp     ecx, 27h ; '''
0x1001aab2  ja      loc_1001B198
0x1001aab8  test    ebx, ebx
0x1001aaba  jz      loc_1001B198
0x1001aac0  mov     ecx, ebx
0x1001aac2  lea     edx, [ecx+2]
0x1001aac5  mov     ax, [ecx]
0x1001aac8  add     ecx, 2
0x1001aacb  test    ax, ax
0x1001aace  jnz     short loc_1001AAC5
0x1001aad0  sub     ecx, edx
0x1001aad2  sar     ecx, 1
0x1001aad4  cmp     ecx, 104h
0x1001aada  ja      loc_1001B198
0x1001aae0  mov     eax, _critJet
0x1001aae5  test    eax, eax
0x1001aae7  jnz     short loc_1001AB2A
0x1001aae9  push    18h; Size
0x1001aaeb  call    ds:__imp__malloc
0x1001aaf1  add     esp, 4
0x1001aaf4  mov     _critJet, eax
0x1001aaf9  test    eax, eax
0x1001aafb  jnz     short loc_1001AB1B
0x1001aafd  mov     esi, 0FFFFFC0Dh
0x1001ab02  mov     eax, esi
0x1001ab04  pop     edi
0x1001ab05  pop     esi
0x1001ab06  pop     ebx
0x1001ab07  mov     ecx, [esp+0B4h+var_4]
0x1001ab0e  xor     ecx, esp; StackCookie
0x1001ab10  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001ab15  mov     esp, ebp
0x1001ab17  pop     ebp
0x1001ab18  retn    18h
0x1001ab1b  push    eax; lpCriticalSection
0x1001ab1c  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x1001ab22  push    _critJet
0x1001ab28  jmp     short loc_1001AB2B
0x1001ab2a  push    eax; lpCriticalSection
0x1001ab2b  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001ab31  lea     ecx, [esp+0C0h+var_AC]
0x1001ab35  call    _ErrInitInstance@4; ErrInitInstance(x)
0x1001ab3a  mov     esi, eax
0x1001ab3c  test    esi, esi
0x1001ab3e  jns     short loc_1001AB65
0x1001ab40  push    _critJet; lpCriticalSection
0x1001ab46  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001ab4c  mov     eax, esi
0x1001ab4e  pop     edi
0x1001ab4f  pop     esi
0x1001ab50  pop     ebx
0x1001ab51  mov     ecx, [esp+0B4h+var_4]
0x1001ab58  xor     ecx, esp; StackCookie
0x1001ab5a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001ab5f  mov     esp, ebp
0x1001ab61  pop     ebp
0x1001ab62  retn    18h
0x1001ab65  mov     edi, [esp+0C0h+var_AC]
0x1001ab69  mov     ecx, edi
0x1001ab6b  lea     ebx, [edi+90h]
0x1001ab71  mov     [esp+0C0h+var_A8], ebx
0x1001ab75  call    _ErrInit@8; ErrInit(x,x)
0x1001ab7a  mov     esi, eax
0x1001ab7c  test    esi, esi
0x1001ab7e  jns     short loc_1001AB95
0x1001ab80  cmp     esi, 0FFFFFBFAh
0x1001ab86  jz      short loc_1001AB8F
0x1001ab88  mov     ecx, edi
0x1001ab8a  call    _ReleaseTib@4; ReleaseTib(x)
0x1001ab8f  xor     ebx, ebx
0x1001ab91  mov     [esp+0C0h+var_A8], ebx
0x1001ab95  push    _critJet; lpCriticalSection
0x1001ab9b  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001aba1  test    esi, esi
0x1001aba3  js      loc_1001B17F
0x1001aba9  push    offset dword_10008698; int
0x1001abae  push    offset dword_10008698; Src
0x1001abb3  lea     eax, [esp+0C8h+var_A4]
0x1001abb7  push    eax; int
0x1001abb8  push    ebx; int
0x1001abb9  call    _ErrBeginSession@16; ErrBeginSession(x,x,x,x)
0x1001abbe  mov     esi, eax
0x1001abc0  mov     eax, ebx
0x1001abc2  test    esi, esi
0x1001abc4  js      loc_1001B179
0x1001abca  mov     eax, [ebp+arg_14]
0x1001abcd  mov     edi, [esp+0C0h+var_A4]
0x1001abd1  or      eax, 80h
0x1001abd6  mov     edx, [esp+0C0h+var_98]
0x1001abda  mov     ecx, edi; int
0x1001abdc  push    eax; int
0x1001abdd  lea     eax, [esp+0C4h+var_A0]
0x1001abe1  push    eax; int
0x1001abe2  push    [esp+0C8h+var_9C]; int
0x1001abe6  call    _ErrIsamCreateDatabase@20; ErrIsamCreateDatabase(x,x,x,x,x)
0x1001abeb  mov     esi, eax
0x1001abed  mov     [esp+0C0h+var_AC], ebx
0x1001abf1  test    esi, esi
0x1001abf3  js      loc_1001B16F
0x1001abf9  mov     ecx, edi
0x1001abfb  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x1001ac00  mov     ebx, [esp+0C0h+var_A0]
0x1001ac04  push    0
0x1001ac06  imul    eax, 68h ; 'h'
0x1001ac09  push    0FFFFh
0x1001ac0e  push    [ebp+arg_14]
0x1001ac11  push    ebx
0x1001ac12  push    edi
0x1001ac13  mov     eax, dword_1016EAF8[eax]
0x1001ac19  mov     _mpdbidiiscb[ebx*4], eax
0x1001ac20  call    _ErrREPOpenDatabase@20; ErrREPOpenDatabase(x,x,x,x,x)
0x1001ac25  mov     esi, eax
0x1001ac27  test    esi, esi
0x1001ac29  jns     short loc_1001AC41
0x1001ac2b  push    0
0x1001ac2d  push    ebx
0x1001ac2e  push    edi
0x1001ac2f  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x1001ac34  mov     eax, [esp+0C0h+var_A8]
0x1001ac38  mov     [esp+0C0h+var_AC], eax
0x1001ac3c  jmp     loc_1001B16F
0x1001ac41  push    80h; Size
0x1001ac46  lea     eax, [esp+0C4h+var_88]
0x1001ac4a  push    20h ; ' '; Val
0x1001ac4c  push    eax; void *
0x1001ac4d  call    _memset
0x1001ac52  mov     eax, [esp+0CCh+var_A8]
0x1001ac56  lea     esi, [esp+0CCh+var_87]
0x1001ac5a  mov     edi, [esp+0CCh+var_94]
0x1001ac5e  add     esp, 0Ch
0x1001ac61  mov     [esp+0C0h+var_AC], eax
0x1001ac65  movzx   eax, word ptr [edi]
0x1001ac68  push    eax; C
0x1001ac69  call    ds:__imp__towupper
0x1001ac6f  add     esp, 4
0x1001ac72  mov     [esi], al
0x1001ac74  lea     edi, [edi+2]
0x1001ac77  lea     esi, [esi+1]
0x1001ac7a  test    al, al
0x1001ac7c  jnz     short loc_1001AC65
0x1001ac7e  mov     ebx, [esp+0C0h+var_90]
0x1001ac82  lea     esi, [esp+0C0h+var_72]
0x1001ac86  movzx   eax, word ptr [ebx]
0x1001ac89  push    eax; C
0x1001ac8a  call    ds:__imp__towupper
0x1001ac90  add     esp, 4
0x1001ac93  mov     [esi], al
0x1001ac95  lea     ebx, [ebx+2]
0x1001ac98  lea     esi, [esi+1]
0x1001ac9b  test    al, al
0x1001ac9d  jnz     short loc_1001AC86
0x1001ac9f  mov     edi, [esp+0C0h+var_8C]
0x1001aca3  lea     esi, [esp+0C0h+var_4A]
0x1001aca7  nop     word ptr [eax+eax+00000000h]
0x1001acb0  movzx   eax, word ptr [edi]
0x1001acb3  push    eax; C
0x1001acb4  call    ds:__imp__towupper
0x1001acba  add     esp, 4
0x1001acbd  mov     [esi], al
0x1001acbf  lea     edi, [edi+2]
0x1001acc2  lea     esi, [esi+1]
0x1001acc5  test    al, al
0x1001acc7  jnz     short loc_1001ACB0
0x1001acc9  mov     edi, [esp+0C0h+var_A4]
0x1001accd  xor     ebx, ebx
0x1001accf  nop
0x1001acd0  lea     esi, [esp+0C0h+var_87]
0x1001acd4  mov     ecx, offset _rgbKeyLeft; "rkatpvjg"
0x1001acd9  add     esi, ebx
0x1001acdb  call    _DesSetKey
0x1001ace0  xor     edx, edx
0x1001ace2  mov     ecx, esi
0x1001ace4  call    _DesDoDES
0x1001ace9  mov     ecx, offset _rgbKeyRight; "jshcsabn"
0x1001acee  call    _DesSetKey
0x1001acf3  mov     edx, 1
0x1001acf8  mov     ecx, esi
0x1001acfa  call    _DesDoDES
0x1001acff  mov     ecx, offset _rgbKeyLeft; "rkatpvjg"
0x1001ad04  call    _DesSetKey
0x1001ad09  xor     edx, edx
0x1001ad0b  mov     ecx, esi
0x1001ad0d  call    _DesDoDES
0x1001ad12  add     ebx, 8
0x1001ad15  cmp     ebx, 68h ; 'h'
0x1001ad18  jnz     short loc_1001ACD0
0x1001ad1a  mov     ebx, [esp+0C0h+var_A0]
0x1001ad1e  lea     eax, [esp+0C0h+var_B4]
0x1001ad22  push    80000000h
0x1001ad27  push    offset _wszSaTable; "MSysAccounts"
0x1001ad2c  push    eax
0x1001ad2d  push    ebx
0x1001ad2e  push    edi
0x1001ad2f  mov     [esp+0D4h+var_88], 1
0x1001ad34  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x1001ad39  mov     esi, eax
0x1001ad3b  test    esi, esi
0x1001ad3d  jns     short loc_1001AD55
0x1001ad3f  cmp     esi, 0FFFFFAE7h
0x1001ad45  jnz     loc_1001B16F
0x1001ad4b  mov     esi, 0FFFFF88Ch
0x1001ad50  jmp     loc_1001B16F
0x1001ad55  push    1
0x1001ad57  push    66h ; 'f'
0x1001ad59  lea     eax, [esp+0C8h+var_88]
0x1001ad5d  mov     edx, ebx
0x1001ad5f  push    eax
0x1001ad60  push    0
0x1001ad62  push    offset aAdmins; "Admins"
0x1001ad67  push    [esp+0D4h+var_B4]
0x1001ad6b  mov     ecx, edi
0x1001ad6d  call    ErrCreateAccount
0x1001ad72  mov     esi, eax
0x1001ad74  test    esi, esi
0x1001ad76  js      loc_1001B16F
0x1001ad7c  push    1
0x1001ad7e  push    2
0x1001ad80  push    offset _rgbSidUsers
0x1001ad85  push    0
0x1001ad87  push    offset aUsers; "Users"
0x1001ad8c  push    [esp+0D4h+var_B4]
0x1001ad90  mov     edx, ebx
0x1001ad92  mov     ecx, edi
0x1001ad94  call    ErrCreateAccount
0x1001ad99  mov     esi, eax
0x1001ad9b  test    esi, esi
0x1001ad9d  js      loc_1001B16F
0x1001ada3  push    0
0x1001ada5  push    2
0x1001ada7  push    offset _rgbSidEngine
0x1001adac  push    0
0x1001adae  push    offset aEngine; "Engine"
0x1001adb3  push    [esp+0D4h+var_B4]
0x1001adb7  mov     edx, ebx
0x1001adb9  mov     ecx, edi
0x1001adbb  call    ErrCreateAccount
0x1001adc0  mov     esi, eax
0x1001adc2  test    esi, esi
0x1001adc4  js      loc_1001B16F
0x1001adca  push    0
0x1001adcc  push    2
0x1001adce  push    offset _rgbSidCreator
0x1001add3  push    0
  ... truncated ...
```
