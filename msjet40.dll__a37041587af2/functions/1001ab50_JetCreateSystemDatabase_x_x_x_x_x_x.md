# JetCreateSystemDatabase(x,x,x,x,x,x)

- ea: `0x1001ab50`
- end: `0x1001b304`
- name: `_JetCreateSystemDatabase@24`
- size: `1972`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation`

## callees

- `0x10018c40`
- `0x10019170`
- `0x1001a2c0`
- `0x1001a840`
- `0x1001aa30`
- `0x1001ab50`
- `0x10026bf0`
- `0x10027a90`
- `0x100287e0`
- `0x1003a420`
- `0x1003be40`
- `0x1003c0e0`
- `0x1003e830`
- `0x1003ee40`
- `0x10042b60`
- `0x10043220`
- `0x100433f0`
- `0x100439d0`
- `0x1004923e`
- `0x1008baf0`
- `0x10094fe0`
- `0x10117340`
- `0x10123110`
- `0x10123b3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001ac3b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001ac3b`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1001adb9`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1001adda`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1001ae04`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1001adb9`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1001adda`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1001ae04`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1001ac6c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1001ac6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001ac96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001aceb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001ac96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001aceb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001ac7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001ac7b`

## string_xrefs

- `0x1001b076`: `Procedure	MSysUserMemberships UserName Text; Select		Distinct MSysAccounts_1.Name From		(MSysAccounts inner join MSysGroups on MSysAccounts.SID = MSysGroups.UserSID) 			inner join MSysAccounts as MSysAccounts_1 on MSysGroups.GroupSID = MSysAccounts_1.SID Where		MSysAccounts.name = UserName and 			MSysAccounts.FGroup = 0 and 			MSysAccounts_1.FGroup <> 0;`
- `0x1001b10c`: `Procedure	MSysGroupMembers GroupName Text; Select		Distinct MSysAccounts_1.Name From		(MSysAccounts inner join MSysGroups on MSysAccounts.SID = MSysGroups.GroupSID) 			inner join MSysAccounts as MSysAccounts_1 on MSysGroups.UserSID = MSysAccounts_1.SID Where		MSysAccounts.name = GroupName and 			MSysAccounts.FGroup <> 0 and 			MSysAccounts_1.FGroup = 0;`

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
  int savedregs; // [esp+C0h] [ebp+0h] BYREF

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
    v13 = ErrInit(v39, (int)&savedregs, v39);
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
      Database = ErrBeginSession(v12, (int)&v41, (void *)&dword_100086F8, (int)&dword_100086F8);
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
          mpdbidiiscb[v42] = dword_1016EB98[26 * IsibOfSesid];
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
                      Database = ErrCreateAccount(v37, L"admin", &dword_100086F8, rgbSidAdmin, 2, 0);
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
0x1001ab50  mov     edi, edi
0x1001ab52  push    ebp
0x1001ab53  mov     ebp, esp
0x1001ab55  and     esp, 0FFFFFFF8h
0x1001ab58  sub     esp, 0B4h
0x1001ab5e  mov     eax, ___security_cookie
0x1001ab63  xor     eax, esp
0x1001ab65  mov     [esp+0B4h+var_4], eax
0x1001ab6c  mov     ecx, [ebp+arg_8]
0x1001ab6f  mov     eax, [ebp+arg_4]
0x1001ab72  mov     edx, [ebp+arg_10]
0x1001ab75  mov     [esp+0B4h+var_9C], eax
0x1001ab79  mov     [esp+0B4h+var_94], ecx
0x1001ab7d  mov     [esp+0B4h+var_8C], edx
0x1001ab81  push    ebx
0x1001ab82  mov     ebx, [ebp+arg_0]
0x1001ab85  mov     [esp+0B8h+var_98], ebx
0x1001ab89  push    esi
0x1001ab8a  mov     esi, [ebp+arg_C]
0x1001ab8d  mov     [esp+0BCh+var_90], esi
0x1001ab91  push    edi
0x1001ab92  test    ecx, ecx
0x1001ab94  jz      loc_1001B2E8
0x1001ab9a  test    esi, esi
0x1001ab9c  jz      loc_1001B2E8
0x1001aba2  test    edx, edx
0x1001aba4  jz      loc_1001B2E8
0x1001abaa  lea     edi, [ecx+2]
0x1001abad  nop     dword ptr [eax]
0x1001abb0  mov     ax, [ecx]
0x1001abb3  add     ecx, 2
0x1001abb6  test    ax, ax
0x1001abb9  jnz     short loc_1001ABB0
0x1001abbb  sub     ecx, edi
0x1001abbd  sar     ecx, 1
0x1001abbf  cmp     ecx, 14h
0x1001abc2  ja      loc_1001B2E8
0x1001abc8  mov     ecx, esi
0x1001abca  lea     esi, [ecx+2]
0x1001abcd  nop     dword ptr [eax]
0x1001abd0  mov     ax, [ecx]
0x1001abd3  add     ecx, 2
0x1001abd6  test    ax, ax
0x1001abd9  jnz     short loc_1001ABD0
0x1001abdb  sub     ecx, esi
0x1001abdd  sar     ecx, 1
0x1001abdf  cmp     ecx, 27h ; '''
0x1001abe2  ja      loc_1001B2E8
0x1001abe8  mov     ecx, edx
0x1001abea  lea     edx, [ecx+2]
0x1001abed  nop     dword ptr [eax]
0x1001abf0  mov     ax, [ecx]
0x1001abf3  add     ecx, 2
0x1001abf6  test    ax, ax
0x1001abf9  jnz     short loc_1001ABF0
0x1001abfb  sub     ecx, edx
0x1001abfd  sar     ecx, 1
0x1001abff  cmp     ecx, 27h ; '''
0x1001ac02  ja      loc_1001B2E8
0x1001ac08  test    ebx, ebx
0x1001ac0a  jz      loc_1001B2E8
0x1001ac10  mov     ecx, ebx
0x1001ac12  lea     edx, [ecx+2]
0x1001ac15  mov     ax, [ecx]
0x1001ac18  add     ecx, 2
0x1001ac1b  test    ax, ax
0x1001ac1e  jnz     short loc_1001AC15
0x1001ac20  sub     ecx, edx
0x1001ac22  sar     ecx, 1
0x1001ac24  cmp     ecx, 104h
0x1001ac2a  ja      loc_1001B2E8
0x1001ac30  mov     eax, _critJet
0x1001ac35  test    eax, eax
0x1001ac37  jnz     short loc_1001AC7A
0x1001ac39  push    18h; Size
0x1001ac3b  call    ds:__imp__malloc
0x1001ac41  add     esp, 4
0x1001ac44  mov     _critJet, eax
0x1001ac49  test    eax, eax
0x1001ac4b  jnz     short loc_1001AC6B
0x1001ac4d  mov     esi, 0FFFFFC0Dh
0x1001ac52  mov     eax, esi
0x1001ac54  pop     edi
0x1001ac55  pop     esi
0x1001ac56  pop     ebx
0x1001ac57  mov     ecx, [esp+0B4h+var_4]
0x1001ac5e  xor     ecx, esp; StackCookie
0x1001ac60  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001ac65  mov     esp, ebp
0x1001ac67  pop     ebp
0x1001ac68  retn    18h
0x1001ac6b  push    eax; lpCriticalSection
0x1001ac6c  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x1001ac72  push    _critJet
0x1001ac78  jmp     short loc_1001AC7B
0x1001ac7a  push    eax; lpCriticalSection
0x1001ac7b  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001ac81  lea     ecx, [esp+0C0h+var_AC]
0x1001ac85  call    _ErrInitInstance@4; ErrInitInstance(x)
0x1001ac8a  mov     esi, eax
0x1001ac8c  test    esi, esi
0x1001ac8e  jns     short loc_1001ACB5
0x1001ac90  push    _critJet; lpCriticalSection
0x1001ac96  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001ac9c  mov     eax, esi
0x1001ac9e  pop     edi
0x1001ac9f  pop     esi
0x1001aca0  pop     ebx
0x1001aca1  mov     ecx, [esp+0B4h+var_4]
0x1001aca8  xor     ecx, esp; StackCookie
0x1001acaa  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001acaf  mov     esp, ebp
0x1001acb1  pop     ebp
0x1001acb2  retn    18h
0x1001acb5  mov     edi, [esp+0C0h+var_AC]
0x1001acb9  mov     ecx, edi
0x1001acbb  lea     ebx, [edi+90h]
0x1001acc1  mov     [esp+0C0h+var_A8], ebx
0x1001acc5  call    _ErrInit@8; ErrInit(x,x)
0x1001acca  mov     esi, eax
0x1001accc  test    esi, esi
0x1001acce  jns     short loc_1001ACE5
0x1001acd0  cmp     esi, 0FFFFFBFAh
0x1001acd6  jz      short loc_1001ACDF
0x1001acd8  mov     ecx, edi
0x1001acda  call    _ReleaseTib@4; ReleaseTib(x)
0x1001acdf  xor     ebx, ebx
0x1001ace1  mov     [esp+0C0h+var_A8], ebx
0x1001ace5  push    _critJet; lpCriticalSection
0x1001aceb  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001acf1  test    esi, esi
0x1001acf3  js      loc_1001B2CF
0x1001acf9  push    offset dword_100086F8; int
0x1001acfe  push    offset dword_100086F8; Src
0x1001ad03  lea     eax, [esp+0C8h+var_A4]
0x1001ad07  push    eax; int
0x1001ad08  push    ebx; int
0x1001ad09  call    _ErrBeginSession@16; ErrBeginSession(x,x,x,x)
0x1001ad0e  mov     esi, eax
0x1001ad10  mov     eax, ebx
0x1001ad12  test    esi, esi
0x1001ad14  js      loc_1001B2C9
0x1001ad1a  mov     eax, [ebp+arg_14]
0x1001ad1d  mov     edi, [esp+0C0h+var_A4]
0x1001ad21  or      eax, 80h
0x1001ad26  mov     edx, [esp+0C0h+var_98]
0x1001ad2a  mov     ecx, edi; int
0x1001ad2c  push    eax; int
0x1001ad2d  lea     eax, [esp+0C4h+var_A0]
0x1001ad31  push    eax; int
0x1001ad32  push    [esp+0C8h+var_9C]; int
0x1001ad36  call    _ErrIsamCreateDatabase@20; ErrIsamCreateDatabase(x,x,x,x,x)
0x1001ad3b  mov     esi, eax
0x1001ad3d  mov     [esp+0C0h+var_AC], ebx
0x1001ad41  test    esi, esi
0x1001ad43  js      loc_1001B2BF
0x1001ad49  mov     ecx, edi
0x1001ad4b  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x1001ad50  mov     ebx, [esp+0C0h+var_A0]
0x1001ad54  push    0
0x1001ad56  imul    eax, 68h ; 'h'
0x1001ad59  push    0FFFFh
0x1001ad5e  push    [ebp+arg_14]
0x1001ad61  push    ebx
0x1001ad62  push    edi
0x1001ad63  mov     eax, dword_1016EB98[eax]
0x1001ad69  mov     _mpdbidiiscb[ebx*4], eax
0x1001ad70  call    _ErrREPOpenDatabase@20; ErrREPOpenDatabase(x,x,x,x,x)
0x1001ad75  mov     esi, eax
0x1001ad77  test    esi, esi
0x1001ad79  jns     short loc_1001AD91
0x1001ad7b  push    0
0x1001ad7d  push    ebx
0x1001ad7e  push    edi
0x1001ad7f  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x1001ad84  mov     eax, [esp+0C0h+var_A8]
0x1001ad88  mov     [esp+0C0h+var_AC], eax
0x1001ad8c  jmp     loc_1001B2BF
0x1001ad91  push    80h; Size
0x1001ad96  lea     eax, [esp+0C4h+var_88]
0x1001ad9a  push    20h ; ' '; Val
0x1001ad9c  push    eax; void *
0x1001ad9d  call    _memset
0x1001ada2  mov     eax, [esp+0CCh+var_A8]
0x1001ada6  lea     esi, [esp+0CCh+var_87]
0x1001adaa  mov     edi, [esp+0CCh+var_94]
0x1001adae  add     esp, 0Ch
0x1001adb1  mov     [esp+0C0h+var_AC], eax
0x1001adb5  movzx   eax, word ptr [edi]
0x1001adb8  push    eax; C
0x1001adb9  call    ds:__imp__towupper
0x1001adbf  add     esp, 4
0x1001adc2  mov     [esi], al
0x1001adc4  lea     edi, [edi+2]
0x1001adc7  lea     esi, [esi+1]
0x1001adca  test    al, al
0x1001adcc  jnz     short loc_1001ADB5
0x1001adce  mov     ebx, [esp+0C0h+var_90]
0x1001add2  lea     esi, [esp+0C0h+var_72]
0x1001add6  movzx   eax, word ptr [ebx]
0x1001add9  push    eax; C
0x1001adda  call    ds:__imp__towupper
0x1001ade0  add     esp, 4
0x1001ade3  mov     [esi], al
0x1001ade5  lea     ebx, [ebx+2]
0x1001ade8  lea     esi, [esi+1]
0x1001adeb  test    al, al
0x1001aded  jnz     short loc_1001ADD6
0x1001adef  mov     edi, [esp+0C0h+var_8C]
0x1001adf3  lea     esi, [esp+0C0h+var_4A]
0x1001adf7  nop     word ptr [eax+eax+00000000h]
0x1001ae00  movzx   eax, word ptr [edi]
0x1001ae03  push    eax; C
0x1001ae04  call    ds:__imp__towupper
0x1001ae0a  add     esp, 4
0x1001ae0d  mov     [esi], al
0x1001ae0f  lea     edi, [edi+2]
0x1001ae12  lea     esi, [esi+1]
0x1001ae15  test    al, al
0x1001ae17  jnz     short loc_1001AE00
0x1001ae19  mov     edi, [esp+0C0h+var_A4]
0x1001ae1d  xor     ebx, ebx
0x1001ae1f  nop
0x1001ae20  lea     esi, [esp+0C0h+var_87]
0x1001ae24  mov     ecx, offset _rgbKeyLeft; "rkatpvjg"
0x1001ae29  add     esi, ebx
0x1001ae2b  call    _DesSetKey
0x1001ae30  xor     edx, edx
0x1001ae32  mov     ecx, esi
0x1001ae34  call    _DesDoDES
0x1001ae39  mov     ecx, offset _rgbKeyRight; "jshcsabn"
0x1001ae3e  call    _DesSetKey
0x1001ae43  mov     edx, 1
0x1001ae48  mov     ecx, esi
0x1001ae4a  call    _DesDoDES
0x1001ae4f  mov     ecx, offset _rgbKeyLeft; "rkatpvjg"
0x1001ae54  call    _DesSetKey
0x1001ae59  xor     edx, edx
0x1001ae5b  mov     ecx, esi
0x1001ae5d  call    _DesDoDES
0x1001ae62  add     ebx, 8
0x1001ae65  cmp     ebx, 68h ; 'h'
0x1001ae68  jnz     short loc_1001AE20
0x1001ae6a  mov     ebx, [esp+0C0h+var_A0]
0x1001ae6e  lea     eax, [esp+0C0h+var_B4]
0x1001ae72  push    80000000h
0x1001ae77  push    offset _wszSaTable; "MSysAccounts"
0x1001ae7c  push    eax
0x1001ae7d  push    ebx
0x1001ae7e  push    edi
0x1001ae7f  mov     [esp+0D4h+var_88], 1
0x1001ae84  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x1001ae89  mov     esi, eax
0x1001ae8b  test    esi, esi
0x1001ae8d  jns     short loc_1001AEA5
0x1001ae8f  cmp     esi, 0FFFFFAE7h
0x1001ae95  jnz     loc_1001B2BF
0x1001ae9b  mov     esi, 0FFFFF88Ch
0x1001aea0  jmp     loc_1001B2BF
0x1001aea5  push    1
0x1001aea7  push    66h ; 'f'
0x1001aea9  lea     eax, [esp+0C8h+var_88]
0x1001aead  mov     edx, ebx
0x1001aeaf  push    eax
0x1001aeb0  push    0
0x1001aeb2  push    offset aAdmins; "Admins"
0x1001aeb7  push    [esp+0D4h+var_B4]
0x1001aebb  mov     ecx, edi
0x1001aebd  call    ErrCreateAccount
0x1001aec2  mov     esi, eax
0x1001aec4  test    esi, esi
0x1001aec6  js      loc_1001B2BF
0x1001aecc  push    1
0x1001aece  push    2
0x1001aed0  push    offset _rgbSidUsers
0x1001aed5  push    0
0x1001aed7  push    offset aUsers; "Users"
0x1001aedc  push    [esp+0D4h+var_B4]
0x1001aee0  mov     edx, ebx
0x1001aee2  mov     ecx, edi
0x1001aee4  call    ErrCreateAccount
0x1001aee9  mov     esi, eax
0x1001aeeb  test    esi, esi
0x1001aeed  js      loc_1001B2BF
0x1001aef3  push    0
0x1001aef5  push    2
0x1001aef7  push    offset _rgbSidEngine
0x1001aefc  push    0
0x1001aefe  push    offset aEngine; "Engine"
0x1001af03  push    [esp+0D4h+var_B4]
0x1001af07  mov     edx, ebx
0x1001af09  mov     ecx, edi
0x1001af0b  call    ErrCreateAccount
0x1001af10  mov     esi, eax
0x1001af12  test    esi, esi
0x1001af14  js      loc_1001B2BF
0x1001af1a  push    0
0x1001af1c  push    2
0x1001af1e  push    offset _rgbSidCreator
0x1001af23  push    0
  ... truncated ...
```
