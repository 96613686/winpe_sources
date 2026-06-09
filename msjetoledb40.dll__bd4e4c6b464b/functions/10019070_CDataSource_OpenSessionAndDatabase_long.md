# CDataSource::OpenSessionAndDatabase(long &)

- ea: `0x10019070`
- end: `0x1001965e`
- name: `?OpenSessionAndDatabase@CDataSource@@QAEJAAJ@Z`
- size: `1518`
- prototype: `int __userpurge@<eax>(CDataSource *this@<ecx>, const wchar_t *@<edi>, const struct _GUID *@<esi>, int *)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x10018f30`
- `0x1001a7b0`
- `0x1001a970`

## callees

- `0x100177d0`
- `0x10017880`
- `0x10019070`
- `0x100196e0`
- `0x100198d0`
- `0x1001a140`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001f2d0`
- `0x1001fcb0`
- `0x10020200`
- `0x10020250`
- `0x1004d420`

## import_xrefs

- `msjet40!__imp__JetCloseDatabase@12` at `0x1001961b`
- `msjet40!__imp__JetCloseDatabase@12` at `0x1001961b`
- `msjet40!__imp__JetEndSession@8` at `0x10019639`
- `msjet40!__imp__JetEndSession@8` at `0x10019639`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10019210`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10019276`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100192a5`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100194b6`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001951c`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100195f0`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10019210`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10019276`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100192a5`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100194b6`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001951c`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100195f0`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10019592`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10019592`

## pseudocode

```c
int __userpurge CDataSource::OpenSessionAndDatabase@<eax>(
        CDataSource *this@<ecx>,
        const wchar_t *a2@<edi>,
        const struct _GUID *a3@<esi>,
        int *a4)
{
  JoltProperties *v5; // esi
  int v6; // eax
  size_t v7; // eax
  JoltProperties *v8; // esi
  int v9; // eax
  const unsigned __int16 *v10; // ebx
  int v11; // esi
  _DWORD *v12; // ebx
  int DatabaseInfo; // eax
  int v14; // eax
  int v15; // eax
  unsigned int v16; // ecx
  int v17; // eax
  int v18; // eax
  JoltProperties *v19; // ecx
  int v20; // eax
  JET_DBID v21; // eax
  JET_SESID v22; // eax
  const wchar_t *v24; // [esp-Ch] [ebp-44Ch]
  const unsigned __int16 *v25; // [esp-Ch] [ebp-44Ch]
  const struct _GUID *v26; // [esp-8h] [ebp-448h]
  unsigned int v27; // [esp-8h] [ebp-448h]
  int v28; // [esp+4h] [ebp-43Ch] BYREF
  unsigned int v29; // [esp+Ch] [ebp-434h] BYREF
  int *v30; // [esp+10h] [ebp-430h]
  unsigned int v31; // [esp+14h] [ebp-42Ch] BYREF
  _BYTE v32[4]; // [esp+18h] [ebp-428h] BYREF
  int v33; // [esp+1Ch] [ebp-424h]
  int v34; // [esp+20h] [ebp-420h]
  unsigned __int16 v35[516]; // [esp+24h] [ebp-41Ch] BYREF
  __int64 v36; // [esp+42Ch] [ebp-14h]
  int v37; // [esp+434h] [ebp-Ch]

  v26 = a3;
  v24 = a2;
  v37 = *(_DWORD *)L"=";
  v30 = a4;
  *a4 = 0;
  v5 = (JoltProperties *)*((_DWORD *)this + 40);
  v36 = *(_QWORD *)L";pwd=";
  if ( JoltProperties::BinarySearch(v5, 0xA0u, &v29) >= 0 )
  {
    v6 = *((_DWORD *)v5 + 4);
    if ( *(_WORD *)(v6 + 48 * v29 + 16) == 8 )
    {
      v7 = *(_DWORD *)(v6 + 48 * v29 + 24);
      if ( v7 )
        StringCopyWorkerW((STRSAFE_LPWSTR)(48 * v29), v7, (size_t *)0x200, v24, (size_t)v26);
    }
  }
  v8 = (JoltProperties *)*((_DWORD *)this + 41);
  v35[512] = 0;
  if ( JoltProperties::BinarySearch(v8, 0x100u, &v29) >= 0 )
  {
    v9 = *((_DWORD *)v8 + 4);
    if ( *(_WORD *)(v9 + 48 * v29 + 16) == 8 )
    {
      v10 = *(const unsigned __int16 **)(v9 + 48 * v29 + 24);
      if ( v10 )
      {
        if ( wcslen(v35) + wcslen(v10) + 6 < 0x200 )
        {
          WCSCAT((unsigned __int16 *)0x201, v24, (unsigned int)v26);
          WCSCAT((unsigned __int16 *)0x201, v25, v27);
        }
      }
    }
  }
  v11 = CDataSource::ValidateStateForJetOpenDatabase(this, &v29);
  if ( v11 >= 0 )
  {
    v12 = (_DWORD *)((char *)this + 144);
    v11 = CDataSource::JETBeginSession(this, (unsigned int *)this + 36, v30);
    if ( v11 >= 0 )
    {
      v11 = CDataSource::JETOpenDatabase(
              this,
              (unsigned int *)this + 36,
              (unsigned int *)this + 37,
              (unsigned int *)v30,
              0,
              0);
      if ( v11 < 0 )
        goto LABEL_72;
      DatabaseInfo = JetGetDatabaseInfo(*v12, *((_DWORD *)this + 37), &v31, 4, 18);
      *v30 = DatabaseInfo;
      if ( DatabaseInfo >= 0 )
      {
        JoltProperties::SetPropertyRW(*((JoltProperties **)this + 40), 0xBAu);
        JoltProperties::SetIntValue(*((JoltProperties **)this + 40), 0xBAu, &v31);
        JoltProperties::SetPropertyRO(*((JoltProperties **)this + 40), 0xBAu);
        v14 = JetGetDatabaseInfo(*v12, *((_DWORD *)this + 37), &v31, 4, 8);
        *v30 = v14;
        if ( v14 >= 0 )
        {
          v15 = JetGetDatabaseInfo(*v12, *((_DWORD *)this + 37), &v28, 8, 9);
          *v30 = v15;
          if ( v15 >= 0 )
          {
            v16 = 0;
            switch ( v28 )
            {
              case 1:
              case 21:
                switch ( v31 )
                {
                  case 0x10000u:
                    v16 = 1;
                    break;
                  case 0x10001u:
                    v16 = 2;
                    break;
                  case 0x20000u:
                    v16 = 3;
                    break;
                  default:
                    if ( HIWORD(v31) == 3 )
                    {
                      v16 = 4;
                    }
                    else if ( HIWORD(v31) == 4 )
                    {
                      v16 = 5;
                    }
                    break;
                }
                break;
              case 24:
                switch ( HIWORD(v31) )
                {
                  case 3u:
                    v16 = 80;
                    break;
                  case 4u:
                    v16 = 81;
                    break;
                  case 5u:
                    v16 = 82;
                    break;
                  case 7u:
                    v16 = 83;
                    break;
                  default:
                    goto LABEL_59;
                }
                break;
              case 25:
                switch ( HIWORD(v31) )
                {
                  case 3u:
                    v16 = 16;
                    break;
                  case 4u:
                    v16 = 17;
                    break;
                  case 5u:
                    v16 = 18;
                    break;
                }
                break;
              case 27:
                if ( HIWORD(v31) == 1 )
                  v16 = HIWORD(v31) - 1 + 96;
                break;
              case 28:
                switch ( HIWORD(v31) )
                {
                  case 3u:
                    v16 = 32;
                    break;
                  case 4u:
                    v16 = 33;
                    break;
                  case 5u:
                    v16 = 34;
                    break;
                  case 8u:
                    v16 = 35;
                    break;
                  case 9u:
                    v16 = 36;
                    break;
                  default:
                    goto LABEL_59;
                }
                break;
              case 29:
                switch ( HIWORD(v31) )
                {
                  case 2u:
                    v16 = 64;
                    break;
                  case 3u:
                    v16 = 65;
                    break;
                  case 4u:
                    v16 = 66;
                    break;
                }
                break;
              case 30:
                if ( (v31 & 0xFFFF0000) == 0x40000 )
                  v16 = 48;
                break;
              case 31:
                if ( HIWORD(v31) == 1 )
                  v16 = HIWORD(v31) - 1 + 112;
                break;
              default:
                break;
            }
LABEL_59:
            v31 = v16;
            JoltProperties::SetPropertyRW(*((JoltProperties **)this + 41), 0x103u);
            JoltProperties::SetIntValue(*((JoltProperties **)this + 41), 0x103u, &v31);
            JoltProperties::SetPropertyRO(*((JoltProperties **)this + 41), 0x103u);
            v17 = JetGetDatabaseInfo(*v12, *((_DWORD *)this + 37), &v31, 4, 20);
            *v30 = v17;
            if ( v17 < 0 )
              v31 = 0;
            JoltProperties::SetPropertyRW(*((JoltProperties **)this + 41), 0x106u);
            JoltProperties::SetIntValue(*((JoltProperties **)this + 41), 0x106u, &v31);
            JoltProperties::SetPropertyRO(*((JoltProperties **)this + 41), 0x106u);
            v18 = JetGetDatabaseInfo(*v12, *((_DWORD *)this + 37), v32, 12, 10);
            *v30 = v18;
            if ( v18 >= 0 )
            {
              JoltProperties::SetPropertyRW(*((JoltProperties **)this + 41), 0x11Au);
              v19 = (JoltProperties *)*((_DWORD *)this + 41);
              v29 = v34 + v33;
              JoltProperties::SetIntValue(v19, 0x11Au, &v29);
              JoltProperties::SetPropertyRO(*((JoltProperties **)this + 41), 0x11Au);
            }
            *v30 = 0;
            v20 = JetSetSystemParameter((char *)this + 96, *v12, 2, StatusCallback, 0);
            *v30 = v20;
            if ( v20 < 0 )
              v11 = -2147467259;
          }
          else
          {
            v11 = -2147467259;
          }
        }
        else
        {
          v11 = -2147467259;
        }
      }
      else
      {
        v11 = -2147467259;
      }
    }
  }
  if ( *v30 )
  {
    CExtError::SendJetErrortoOLEAuto(*v30, (int)&IID_IDBInitialize, (int)v24, v26);
    if ( v11 >= 0 )
      return v11;
  }
  else
  {
    if ( v11 >= 0 )
      return v11;
    if ( v11 != -2147024882 && !JetGetDatabaseInfo(*((_DWORD *)this + 36), -1, &v29, 4, 3) )
      CExtError::SendHRtoOLEAuto((int)&IID_IDBInitialize, 0, (const struct _GUID *)v24, (int)v26);
  }
LABEL_72:
  v21 = *((_DWORD *)this + 37);
  if ( v21 != -1 )
  {
    JetCloseDatabase(*((_DWORD *)this + 36), v21, 0);
    *((_DWORD *)this + 37) = -1;
  }
  v22 = *((_DWORD *)this + 36);
  if ( v22 != -1 )
  {
    JetEndSession(v22, 1u);
    *((_DWORD *)this + 36) = -1;
  }
  return v11;
}

```

## disassembly

```asm
0x10019070  mov     edi, edi
0x10019072  push    ebp
0x10019073  mov     ebp, esp
0x10019075  sub     esp, 440h
0x1001907b  mov     eax, ___security_cookie
0x10019080  xor     eax, ebp
0x10019082  mov     [ebp+var_8], eax
0x10019085  mov     eax, dword ptr ds:aPwd_0+8; "="
0x1001908a  movq    xmm0, qword ptr ds:aPwd_0; ";pwd="
0x10019092  push    ebx
0x10019093  push    esi; int
0x10019094  push    edi; struct _GUID *
0x10019095  mov     edi, ecx
0x10019097  mov     [ebp+var_C], eax
0x1001909a  mov     ecx, [ebp+arg_0]
0x1001909d  lea     eax, [ebp+var_434]
0x100190a3  push    eax; unsigned int *
0x100190a4  mov     [ebp+var_430], ecx
0x100190aa  push    0A0h; unsigned int
0x100190af  mov     dword ptr [ecx], 0
0x100190b5  mov     esi, [edi+0A0h]
0x100190bb  mov     ecx, esi; this
0x100190bd  movq    [ebp+var_14], xmm0
0x100190c2  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x100190c7  mov     ebx, 8
0x100190cc  test    eax, eax
0x100190ce  js      short loc_10019105
0x100190d0  mov     eax, [ebp+var_434]
0x100190d6  lea     ecx, [eax+eax*2]
0x100190d9  mov     eax, [esi+10h]
0x100190dc  shl     ecx, 4
0x100190df  cmp     bx, [eax+ecx+10h]
0x100190e4  jnz     short loc_10019105
0x100190e6  mov     eax, [eax+ecx+18h]
0x100190ea  test    eax, eax
0x100190ec  jz      short loc_10019105
0x100190ee  push    200h; pcchNewDestLength
0x100190f3  push    eax; cchDest
0x100190f4  push    ecx; pszDest
0x100190f5  mov     edx, 201h
0x100190fa  lea     ecx, [ebp+var_41C]
0x10019100  call    StringCopyWorkerW
0x10019105  mov     esi, [edi+0A4h]
0x1001910b  xor     eax, eax
0x1001910d  mov     [ebp+var_1C], ax
0x10019111  mov     ecx, esi; this
0x10019113  lea     eax, [ebp+var_434]
0x10019119  push    eax; unsigned int *
0x1001911a  push    100h; unsigned int
0x1001911f  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10019124  test    eax, eax
0x10019126  js      short loc_100191A4
0x10019128  mov     eax, [ebp+var_434]
0x1001912e  lea     ecx, [eax+eax*2]
0x10019131  mov     eax, [esi+10h]
0x10019134  add     ecx, ecx
0x10019136  cmp     bx, [eax+ecx*8+10h]
0x1001913b  jnz     short loc_100191A4
0x1001913d  mov     ebx, [eax+ecx*8+18h]
0x10019141  test    ebx, ebx
0x10019143  jz      short loc_100191A4
0x10019145  lea     ecx, [ebp+var_41C]
0x1001914b  lea     edx, [ecx+2]
0x1001914e  mov     edi, edi
0x10019150  mov     ax, [ecx]
0x10019153  add     ecx, 2
0x10019156  test    ax, ax
0x10019159  jnz     short loc_10019150
0x1001915b  mov     esi, ebx
0x1001915d  sub     ecx, edx
0x1001915f  sar     ecx, 1
0x10019161  lea     edx, [esi+2]
0x10019164  mov     ax, [esi]
0x10019167  add     esi, 2
0x1001916a  test    ax, ax
0x1001916d  jnz     short loc_10019164
0x1001916f  sub     esi, edx
0x10019171  sar     esi, 1
0x10019173  lea     eax, [esi+6]
0x10019176  add     eax, ecx
0x10019178  cmp     eax, 200h
0x1001917d  jnb     short loc_100191A4
0x1001917f  push    201h; unsigned __int16 *
0x10019184  lea     edx, [ebp+var_14]
0x10019187  lea     ecx, [ebp+var_41C]
0x1001918d  call    ?WCSCAT@@YGPAGPAGPBGI@Z; WCSCAT(ushort *,ushort const *,uint)
0x10019192  push    201h; unsigned __int16 *
0x10019197  mov     edx, ebx
0x10019199  lea     ecx, [ebp+var_41C]
0x1001919f  call    ?WCSCAT@@YGPAGPAGPBGI@Z; WCSCAT(ushort *,ushort const *,uint)
0x100191a4  lea     eax, [ebp+var_434]
0x100191aa  mov     ecx, edi; this
0x100191ac  push    eax; unsigned int *
0x100191ad  call    ?ValidateStateForJetOpenDatabase@CDataSource@@QAEJAAK@Z; CDataSource::ValidateStateForJetOpenDatabase(ulong &)
0x100191b2  mov     esi, eax
0x100191b4  test    esi, esi
0x100191b6  js      loc_100195AA
0x100191bc  push    [ebp+var_430]; int *
0x100191c2  lea     ebx, [edi+90h]
0x100191c8  mov     ecx, edi; this
0x100191ca  push    ebx; unsigned int *
0x100191cb  call    ?JETBeginSession@CDataSource@@QAEJAAKAAJ@Z; CDataSource::JETBeginSession(ulong &,long &)
0x100191d0  mov     esi, eax
0x100191d2  test    esi, esi
0x100191d4  js      loc_100195AA
0x100191da  push    0; unsigned int *
0x100191dc  push    0; unsigned __int16 *
0x100191de  push    [ebp+var_430]; int *
0x100191e4  lea     eax, [edi+94h]
0x100191ea  mov     ecx, edi; this
0x100191ec  push    eax; unsigned int *
0x100191ed  push    ebx; unsigned int *
0x100191ee  call    ?JETOpenDatabase@CDataSource@@QAEJAAK0AAJPAGPAK@Z; CDataSource::JETOpenDatabase(ulong &,ulong &,long &,ushort *,ulong *)
0x100191f3  mov     esi, eax
0x100191f5  test    esi, esi
0x100191f7  js      loc_10019607
0x100191fd  push    12h
0x100191ff  push    4
0x10019201  lea     eax, [ebp+var_42C]
0x10019207  push    eax
0x10019208  push    dword ptr [edi+94h]
0x1001920e  push    dword ptr [ebx]
0x10019210  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10019216  mov     ecx, [ebp+var_430]
0x1001921c  mov     [ecx], eax
0x1001921e  test    eax, eax
0x10019220  jns     short loc_1001922C
0x10019222  mov     esi, 80004005h
0x10019227  jmp     loc_100195AA
0x1001922c  mov     ecx, [edi+0A0h]; this
0x10019232  push    0BAh; unsigned int
0x10019237  call    ?SetPropertyRW@JoltProperties@@QAEJK@Z; JoltProperties::SetPropertyRW(ulong)
0x1001923c  mov     ecx, [edi+0A0h]; this
0x10019242  lea     eax, [ebp+var_42C]
0x10019248  push    eax; unsigned int *
0x10019249  push    0BAh; unsigned int
0x1001924e  call    ?SetIntValue@JoltProperties@@QAEJKABK@Z; JoltProperties::SetIntValue(ulong,ulong const &)
0x10019253  mov     ecx, [edi+0A0h]; this
0x10019259  push    0BAh; unsigned int
0x1001925e  call    ?SetPropertyRO@JoltProperties@@QAEJK@Z; JoltProperties::SetPropertyRO(ulong)
0x10019263  push    8
0x10019265  push    4
0x10019267  lea     eax, [ebp+var_42C]
0x1001926d  push    eax
0x1001926e  push    dword ptr [edi+94h]
0x10019274  push    dword ptr [ebx]
0x10019276  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1001927c  mov     ecx, [ebp+var_430]
0x10019282  mov     [ecx], eax
0x10019284  test    eax, eax
0x10019286  jns     short loc_10019292
0x10019288  mov     esi, 80004005h
0x1001928d  jmp     loc_100195AA
0x10019292  push    9
0x10019294  push    8
0x10019296  lea     eax, [ebp+var_43C]
0x1001929c  push    eax
0x1001929d  push    dword ptr [edi+94h]
0x100192a3  push    dword ptr [ebx]
0x100192a5  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x100192ab  mov     ecx, [ebp+var_430]
0x100192b1  mov     [ecx], eax
0x100192b3  test    eax, eax
0x100192b5  jns     short loc_100192C1
0x100192b7  mov     esi, 80004005h
0x100192bc  jmp     loc_100195AA
0x100192c1  mov     eax, [ebp+var_43C]
0x100192c7  xor     ecx, ecx
0x100192c9  dec     eax; switch 31 cases
0x100192ca  cmp     eax, 1Eh
0x100192cd  ja      def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x100192d3  movzx   eax, ds:byte_10019684[eax]
0x100192da  jmp     ds:jpt_100192DA[eax*4]; switch jump
0x100192e1  mov     edx, [ebp+var_42C]; jumptable 100192DA cases 1,21
0x100192e7  mov     eax, edx
0x100192e9  sub     eax, 10000h
0x100192ee  jz      short loc_10019331
0x100192f0  sub     eax, 1
0x100192f3  jz      short loc_10019327
0x100192f5  sub     eax, 0FFFFh
0x100192fa  jz      short loc_1001931D
0x100192fc  shr     edx, 10h
0x100192ff  cmp     edx, 3
0x10019302  jnz     short loc_1001930C
0x10019304  lea     ecx, [edx+1]
0x10019307  jmp     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x1001930c  cmp     edx, 4
0x1001930f  jnz     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x10019315  lea     ecx, [edx+1]
0x10019318  jmp     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x1001931d  mov     ecx, 3
0x10019322  jmp     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x10019327  mov     ecx, 2
0x1001932c  jmp     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x10019331  mov     ecx, 1
0x10019336  jmp     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x1001933b  mov     eax, [ebp+var_42C]; jumptable 100192DA case 25
0x10019341  shr     eax, 10h
0x10019344  sub     eax, 3
0x10019347  jz      short loc_10019369
0x10019349  sub     eax, 1
0x1001934c  jz      short loc_1001935F
0x1001934e  sub     eax, 1
0x10019351  jnz     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x10019357  lea     ecx, [eax+12h]
0x1001935a  jmp     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x1001935f  mov     ecx, 11h
0x10019364  jmp     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x10019369  mov     ecx, 10h
0x1001936e  jmp     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x10019373  mov     eax, [ebp+var_42C]; jumptable 100192DA case 24
0x10019379  shr     eax, 10h
0x1001937c  add     eax, 0FFFFFFFDh; switch 5 cases
0x1001937f  cmp     eax, 4
0x10019382  ja      def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x10019388  jmp     ds:jpt_10019388[eax*4]; switch jump
0x1001938f  mov     ecx, 50h ; 'P'; jumptable 10019388 case 3
0x10019394  jmp     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x10019399  mov     ecx, 51h ; 'Q'; jumptable 10019388 case 4
0x1001939e  jmp     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x100193a3  mov     ecx, 52h ; 'R'; jumptable 10019388 case 5
0x100193a8  jmp     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x100193ad  mov     ecx, 53h ; 'S'; jumptable 10019388 case 7
0x100193b2  jmp     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x100193b7  mov     eax, [ebp+var_42C]; jumptable 100192DA case 27
0x100193bd  shr     eax, 10h
0x100193c0  sub     eax, 1
0x100193c3  jnz     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x100193c9  lea     ecx, [eax+60h]
0x100193cc  jmp     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x100193d1  mov     eax, [ebp+var_42C]; jumptable 100192DA case 31
0x100193d7  shr     eax, 10h
0x100193da  sub     eax, 1
0x100193dd  jnz     def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x100193e3  lea     ecx, [eax+70h]
0x100193e6  jmp     short def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x100193e8  mov     eax, [ebp+var_42C]; jumptable 100192DA case 29
0x100193ee  shr     eax, 10h
0x100193f1  sub     eax, 2
0x100193f4  jz      short loc_1001940C
0x100193f6  sub     eax, 1
0x100193f9  jz      short loc_10019405
0x100193fb  sub     eax, 1
0x100193fe  jnz     short def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x10019400  lea     ecx, [eax+42h]
0x10019403  jmp     short def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x10019405  mov     ecx, 41h ; 'A'
0x1001940a  jmp     short def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x1001940c  mov     ecx, 40h ; '@'
0x10019411  jmp     short def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x10019413  mov     eax, [ebp+var_42C]; jumptable 100192DA case 28
0x10019419  shr     eax, 10h
0x1001941c  add     eax, 0FFFFFFFDh; switch 7 cases
0x1001941f  cmp     eax, 6
0x10019422  ja      short def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x10019424  jmp     ds:jpt_10019424[eax*4]; switch jump
0x1001942b  mov     ecx, 20h ; ' '; jumptable 10019424 case 3
0x10019430  jmp     short def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x10019432  mov     ecx, 21h ; '!'; jumptable 10019424 case 4
0x10019437  jmp     short def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x10019439  mov     ecx, 22h ; '"'; jumptable 10019424 case 5
0x1001943e  jmp     short def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x10019440  mov     ecx, 23h ; '#'; jumptable 10019424 case 8
0x10019445  jmp     short def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x10019447  mov     ecx, 24h ; '$'; jumptable 10019424 case 9
0x1001944c  jmp     short def_100192DA; jumptable 100192DA default case, cases 2-20,22,23,26
0x1001944e  mov     eax, [ebp+var_42C]; jumptable 100192DA case 30
0x10019454  mov     edx, 30h ; '0'
0x10019459  and     eax, 0FFFF0000h
0x1001945e  cmp     eax, 40000h
0x10019463  cmovz   ecx, edx
0x10019466  mov     [ebp+var_42C], ecx; jumptable 100192DA default case, cases 2-20,22,23,26
0x1001946c  mov     ecx, [edi+0A4h]; this
0x10019472  push    103h; unsigned int
0x10019477  call    ?SetPropertyRW@JoltProperties@@QAEJK@Z; JoltProperties::SetPropertyRW(ulong)
0x1001947c  mov     ecx, [edi+0A4h]; this
0x10019482  lea     eax, [ebp+var_42C]
0x10019488  push    eax; unsigned int *
0x10019489  push    103h; unsigned int
0x1001948e  call    ?SetIntValue@JoltProperties@@QAEJKABK@Z; JoltProperties::SetIntValue(ulong,ulong const &)
0x10019493  mov     ecx, [edi+0A4h]; this
0x10019499  push    103h; unsigned int
0x1001949e  call    ?SetPropertyRO@JoltProperties@@QAEJK@Z; JoltProperties::SetPropertyRO(ulong)
0x100194a3  push    14h
0x100194a5  push    4
0x100194a7  lea     eax, [ebp+var_42C]
0x100194ad  push    eax
0x100194ae  push    dword ptr [edi+94h]
0x100194b4  push    dword ptr [ebx]
0x100194b6  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x100194bc  mov     ecx, [ebp+var_430]
0x100194c2  mov     [ecx], eax
0x100194c4  test    eax, eax
0x100194c6  jns     short loc_100194D2
0x100194c8  mov     [ebp+var_42C], 0
0x100194d2  mov     ecx, [edi+0A4h]; this
0x100194d8  push    106h; unsigned int
0x100194dd  call    ?SetPropertyRW@JoltProperties@@QAEJK@Z; JoltProperties::SetPropertyRW(ulong)
0x100194e2  mov     ecx, [edi+0A4h]; this
0x100194e8  lea     eax, [ebp+var_42C]
  ... truncated ...
```
