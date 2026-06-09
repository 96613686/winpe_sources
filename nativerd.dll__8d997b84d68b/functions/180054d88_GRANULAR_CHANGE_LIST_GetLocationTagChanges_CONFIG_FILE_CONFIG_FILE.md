# GRANULAR_CHANGE_LIST::GetLocationTagChanges(CONFIG_FILE *,CONFIG_FILE *)

- ea: `0x180054d88`
- end: `0x1800551c5`
- name: `?GetLocationTagChanges@GRANULAR_CHANGE_LIST@@AEAAJPEAVCONFIG_FILE@@0@Z`
- size: `1085`
- prototype: `__int64 __fastcall(GRANULAR_CHANGE_LIST *__hidden this, struct CONFIG_FILE *, struct CONFIG_FILE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180055af0`

## callees

- `0x180025f10`
- `0x180026b24`
- `0x1800541c4`
- `0x180054698`
- `0x180054c70`
- `0x180054d3c`
- `0x180054d88`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054fba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054fba`
- `iisutil!?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z` at `0x18005507d`
- `iisutil!?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z` at `0x18005507d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180055193`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180055193`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180054f40`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180055117`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180054f40`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180055117`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180054e03`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180054e03`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180054f11`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800550f0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180054f11`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800550f0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180054f2b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180055106`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180054f2b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180055106`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180054f71`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180054f71`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180054e0d`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180054e0d`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180055188`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180055188`

## pseudocode

```c
__int64 __fastcall GRANULAR_CHANGE_LIST::GetLocationTagChanges(
        GRANULAR_CHANGE_LIST *this,
        struct CONFIG_FILE *a2,
        struct CONFIG_FILE *a3)
{
  unsigned int v3; // r14d
  CONFIG_ELEMENT_TABLE *v7; // rdi
  CONFIG_ELEMENT_TABLE *v8; // rsi
  signed int appended; // ebx
  int LocationByIndexInternal; // eax
  int LocationInternal; // eax
  GRANULAR_CHANGE_LIST *v12; // rcx
  int v13; // eax
  const unsigned __int16 *Str; // rax
  unsigned int v15; // r14d
  int v16; // eax
  int v17; // eax
  GRANULAR_CHANGE_LIST *v18; // rcx
  int v19; // eax
  const unsigned __int16 *v20; // rax
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v23; // [rsp+28h] [rbp-D8h] BYREF
  CONFIG_ELEMENT_TABLE *v24; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v25; // [rsp+38h] [rbp-C8h] BYREF
  CONFIG_ELEMENT_TABLE *v26; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v27; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v28[56]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v29[56]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v30[128]; // [rsp+C0h] [rbp-40h] BYREF

  v3 = 0;
  v27 = 0;
  v25 = 0;
  v24 = 0;
  v26 = 0;
  v23 = 0;
  v7 = 0;
  v8 = 0;
  memset_0(v30, 0, sizeof(v30));
  STRU::STRU((STRU *)v28, v30, 0x80u);
  MULTISZ::MULTISZ((MULTISZ *)v29);
  appended = (*(__int64 (__fastcall **)(char *, unsigned int *))(*((_QWORD *)a2 + 2) + 24LL))((char *)a2 + 16, &v27);
  if ( appended >= 0 )
  {
    while ( v3 < v27 )
    {
      LocationByIndexInternal = CONFIG_FILE::GetLocationByIndexInternal(a2, v3, &v24);
      v7 = v24;
      appended = LocationByIndexInternal;
      if ( LocationByIndexInternal < 0 )
        goto LABEL_46;
      appended = (*(__int64 (__fastcall **)(char *, unsigned __int16 **))(*((_QWORD *)v24 + 2) + 24LL))(
                   (char *)v24 + 16,
                   &v23);
      if ( appended < 0 )
        goto LABEL_46;
      if ( !*v23 || *v23 == 46 && !v23[1] || (unsigned int)GRANULAR_CHANGE_LIST::ContainsChangedPath(this, v23) )
      {
        CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(v7);
        v7 = 0;
        v24 = 0;
      }
      else
      {
        v22 = 0;
        LocationInternal = CONFIG_FILE::FindLocationInternal(a3, v23, &v26);
        v8 = v26;
        appended = LocationInternal;
        if ( LocationInternal >= 0 )
        {
          appended = GRANULAR_CHANGE_LIST::CompareLocations(v12, v7, v26, &v22);
          v13 = v22;
        }
        else
        {
          if ( LocationInternal != -2147024893 )
            goto LABEL_46;
          v13 = 1;
          appended = 0;
        }
        if ( appended < 0 )
          goto LABEL_46;
        if ( v13 )
        {
          appended = STRU::Copy((STRU *)v28, L"MACHINE/WEBROOT/APPHOST/");
          if ( appended < 0 )
            goto LABEL_46;
          appended = STRU::Append((STRU *)v28, v23);
          if ( appended < 0 )
            goto LABEL_46;
          Str = STRU::QueryStr((STRU *)v28);
          appended = GRANULAR_CHANGE_LIST::AppendChangedPath(this, Str, 1, 1);
          if ( appended < 0 )
            goto LABEL_46;
        }
        if ( !MULTISZ::Append((MULTISZ *)v29, v23) )
        {
          appended = GetLastError();
          if ( appended > 0 )
            appended = (unsigned __int16)appended | 0x80070000;
          goto LABEL_46;
        }
        CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(v7);
        v24 = 0;
        v7 = 0;
        if ( v8 )
        {
          CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(v8);
          v8 = 0;
          v26 = 0;
        }
      }
      ++v3;
    }
    appended = (*(__int64 (__fastcall **)(char *, unsigned int *))(*((_QWORD *)a3 + 2) + 24LL))((char *)a3 + 16, &v25);
    if ( appended < 0 )
      goto LABEL_48;
    v15 = 0;
    if ( !v25 )
      goto LABEL_48;
    do
    {
      v16 = CONFIG_FILE::GetLocationByIndexInternal(a3, v15, &v26);
      v8 = v26;
      appended = v16;
      if ( v16 < 0 )
        break;
      appended = (*(__int64 (__fastcall **)(char *, unsigned __int16 **))(*((_QWORD *)v26 + 2) + 24LL))(
                   (char *)v26 + 16,
                   &v23);
      if ( appended < 0 )
        break;
      if ( *v23
        && (*v23 != 46 || v23[1])
        && !(unsigned int)GRANULAR_CHANGE_LIST::ContainsChangedPath(this, v23)
        && !MULTISZ::FindStringNoCase((MULTISZ *)v29, v23) )
      {
        v22 = 0;
        v17 = CONFIG_FILE::FindLocationInternal(a2, v23, &v24);
        v7 = v24;
        appended = v17;
        if ( v17 >= 0 )
        {
          appended = GRANULAR_CHANGE_LIST::CompareLocations(v18, v24, v8, &v22);
          v19 = v22;
        }
        else
        {
          if ( v17 != -2147024893 )
            break;
          v19 = 1;
          appended = 0;
        }
        if ( appended < 0 )
          break;
        if ( v19 )
        {
          appended = STRU::Copy((STRU *)v28, L"MACHINE/WEBROOT/APPHOST/");
          if ( appended < 0 )
            break;
          appended = STRU::Append((STRU *)v28, v23);
          if ( appended < 0 )
            break;
          v20 = STRU::QueryStr((STRU *)v28);
          appended = GRANULAR_CHANGE_LIST::AppendChangedPath(this, v20, 1, 1);
          if ( appended < 0 )
            break;
        }
        if ( v7 )
        {
          CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(v7);
          v7 = 0;
          v24 = 0;
        }
      }
      CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(v8);
      v8 = 0;
      ++v15;
      v26 = 0;
    }
    while ( v15 < v25 );
LABEL_46:
    if ( v7 )
      CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(v7);
LABEL_48:
    if ( v8 )
      CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(v8);
  }
  MULTISZ::~MULTISZ((MULTISZ *)v29);
  STRU::~STRU((STRU *)v28);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180054d88  mov     [rsp-8+arg_18], rbx
0x180054d8d  push    rbp
0x180054d8e  push    rsi
0x180054d8f  push    rdi
0x180054d90  push    r12
0x180054d92  push    r13
0x180054d94  push    r14
0x180054d96  push    r15
0x180054d98  lea     rbp, [rsp-0D0h]
0x180054da0  sub     rsp, 1D0h
0x180054da7  mov     rax, cs:__security_cookie
0x180054dae  xor     rax, rsp
0x180054db1  mov     [rbp+100h+var_40], rax
0x180054db8  xor     r14d, r14d
0x180054dbb  mov     r13, r8
0x180054dbe  mov     r12, rdx
0x180054dc1  mov     [rsp+200h+var_1B8], r14d
0x180054dc6  mov     r15, rcx
0x180054dc9  mov     [rsp+200h+var_1C8], r14d
0x180054dce  xor     edx, edx; Val
0x180054dd0  mov     [rsp+200h+var_1D0], r14
0x180054dd5  mov     r8d, 100h; Size
0x180054ddb  mov     [rsp+200h+var_1C0], r14
0x180054de0  lea     rcx, [rbp+100h+var_140]; void *
0x180054de4  mov     [rsp+200h+var_1D8], r14
0x180054de9  mov     edi, r14d
0x180054dec  mov     esi, r14d
0x180054def  call    memset_0
0x180054df4  mov     r8d, 80h
0x180054dfa  lea     rdx, [rbp+100h+var_140]
0x180054dfe  lea     rcx, [rsp+200h+var_1B0]
0x180054e03  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180054e09  lea     rcx, [rbp+100h+var_178]
0x180054e0d  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180054e13  lea     rcx, [r12+10h]
0x180054e18  mov     rax, [rcx]
0x180054e1b  lea     rdx, [rsp+200h+var_1B8]
0x180054e20  mov     rax, [rax+18h]
0x180054e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e29  mov     ebx, eax
0x180054e2b  test    eax, eax
0x180054e2d  js      loc_180055184
0x180054e33  cmp     r14d, [rsp+200h+var_1B8]
0x180054e38  jnb     loc_180054FD8
0x180054e3e  lea     r8, [rsp+200h+var_1D0]; struct CONFIG_ELEMENT_TABLE **
0x180054e43  mov     edx, r14d; unsigned int
0x180054e46  mov     rcx, r12; this
0x180054e49  call    ?GetLocationByIndexInternal@CONFIG_FILE@@QEAAJKPEAPEAVCONFIG_ELEMENT_TABLE@@@Z; CONFIG_FILE::GetLocationByIndexInternal(ulong,CONFIG_ELEMENT_TABLE * *)
0x180054e4e  mov     rdi, [rsp+200h+var_1D0]
0x180054e53  mov     ebx, eax
0x180054e55  test    eax, eax
0x180054e57  js      loc_18005516A
0x180054e5d  lea     rcx, [rdi+10h]
0x180054e61  mov     rax, [rcx]
0x180054e64  lea     rdx, [rsp+200h+var_1D8]
0x180054e69  mov     rax, [rax+18h]
0x180054e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e72  mov     ebx, eax
0x180054e74  test    eax, eax
0x180054e76  js      loc_18005516A
0x180054e7c  mov     rdx, [rsp+200h+var_1D8]; unsigned __int16 *
0x180054e81  xor     ebx, ebx
0x180054e83  cmp     [rdx], bx
0x180054e86  jz      loc_180054FA2
0x180054e8c  cmp     word ptr [rdx], 2Eh ; '.'
0x180054e90  jnz     short loc_180054E9C
0x180054e92  cmp     [rdx+2], bx
0x180054e96  jz      loc_180054FA2
0x180054e9c  mov     rcx, r15; this
0x180054e9f  call    ?ContainsChangedPath@GRANULAR_CHANGE_LIST@@AEAAHPEBG@Z; GRANULAR_CHANGE_LIST::ContainsChangedPath(ushort const *)
0x180054ea4  test    eax, eax
0x180054ea6  jnz     loc_180054FA2
0x180054eac  mov     rdx, [rsp+200h+var_1D8]; unsigned __int16 *
0x180054eb1  lea     r8, [rsp+200h+var_1C0]; struct CONFIG_ELEMENT_TABLE **
0x180054eb6  mov     rcx, r13; this
0x180054eb9  mov     [rsp+200h+var_1E0], ebx
0x180054ebd  call    ?FindLocationInternal@CONFIG_FILE@@QEAAJPEBGPEAPEAVCONFIG_ELEMENT_TABLE@@@Z; CONFIG_FILE::FindLocationInternal(ushort const *,CONFIG_ELEMENT_TABLE * *)
0x180054ec2  mov     rsi, [rsp+200h+var_1C0]
0x180054ec7  mov     ebx, eax
0x180054ec9  test    eax, eax
0x180054ecb  jns     short loc_180054EE1
0x180054ecd  cmp     eax, 80070003h
0x180054ed2  jnz     loc_18005516A
0x180054ed8  mov     eax, 1
0x180054edd  xor     ebx, ebx
0x180054edf  jmp     short loc_180054EF7
0x180054ee1  lea     r9, [rsp+200h+var_1E0]; int *
0x180054ee6  mov     r8, rsi; struct CONFIG_ELEMENT_TABLE *
0x180054ee9  mov     rdx, rdi; struct CONFIG_ELEMENT_TABLE *
0x180054eec  call    ?CompareLocations@GRANULAR_CHANGE_LIST@@AEAAJPEAVCONFIG_ELEMENT_TABLE@@0PEAH@Z; GRANULAR_CHANGE_LIST::CompareLocations(CONFIG_ELEMENT_TABLE *,CONFIG_ELEMENT_TABLE *,int *)
0x180054ef1  mov     ebx, eax
0x180054ef3  mov     eax, [rsp+200h+var_1E0]
0x180054ef7  test    ebx, ebx
0x180054ef9  js      loc_18005516A
0x180054eff  xor     ebx, ebx
0x180054f01  test    eax, eax
0x180054f03  jz      short loc_180054F68
0x180054f05  lea     rdx, aMachineWebroot_1; "MACHINE/WEBROOT/APPHOST/"
0x180054f0c  lea     rcx, [rsp+200h+var_1B0]
0x180054f11  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180054f17  mov     ebx, eax
0x180054f19  test    eax, eax
0x180054f1b  js      loc_18005516A
0x180054f21  mov     rdx, [rsp+200h+var_1D8]
0x180054f26  lea     rcx, [rsp+200h+var_1B0]
0x180054f2b  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180054f31  mov     ebx, eax
0x180054f33  test    eax, eax
0x180054f35  js      loc_18005516A
0x180054f3b  lea     rcx, [rsp+200h+var_1B0]
0x180054f40  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180054f46  mov     rdx, rax; unsigned __int16 *
0x180054f49  mov     rcx, r15; this
0x180054f4c  mov     eax, 1
0x180054f51  mov     r9d, eax; int
0x180054f54  mov     r8d, eax; int
0x180054f57  call    ?AppendChangedPath@GRANULAR_CHANGE_LIST@@AEAAJPEBGHH@Z; GRANULAR_CHANGE_LIST::AppendChangedPath(ushort const *,int,int)
0x180054f5c  mov     ebx, eax
0x180054f5e  test    eax, eax
0x180054f60  js      loc_18005516A
0x180054f66  xor     ebx, ebx
0x180054f68  mov     rdx, [rsp+200h+var_1D8]
0x180054f6d  lea     rcx, [rbp+100h+var_178]
0x180054f71  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x180054f77  test    eax, eax
0x180054f79  jz      short loc_180054FBA
0x180054f7b  mov     rcx, rdi; this
0x180054f7e  call    ?DereferenceConfigElementTable@CONFIG_ELEMENT_TABLE@@QEAAXXZ; CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(void)
0x180054f83  mov     [rsp+200h+var_1D0], rbx
0x180054f88  mov     rdi, rbx
0x180054f8b  test    rsi, rsi
0x180054f8e  jz      short loc_180054FB2
0x180054f90  mov     rcx, rsi; this
0x180054f93  call    ?DereferenceConfigElementTable@CONFIG_ELEMENT_TABLE@@QEAAXXZ; CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(void)
0x180054f98  mov     rsi, rbx
0x180054f9b  mov     [rsp+200h+var_1C0], rbx
0x180054fa0  jmp     short loc_180054FB2
0x180054fa2  mov     rcx, rdi; this
0x180054fa5  call    ?DereferenceConfigElementTable@CONFIG_ELEMENT_TABLE@@QEAAXXZ; CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(void)
0x180054faa  mov     rdi, rbx
0x180054fad  mov     [rsp+200h+var_1D0], rbx
0x180054fb2  inc     r14d
0x180054fb5  jmp     loc_180054E33
0x180054fba  call    cs:__imp_GetLastError
0x180054fc0  mov     ebx, eax
0x180054fc2  test    eax, eax
0x180054fc4  jle     loc_18005516A
0x180054fca  movzx   ebx, bx
0x180054fcd  or      ebx, 80070000h
0x180054fd3  jmp     loc_18005516A
0x180054fd8  lea     rcx, [r13+10h]
0x180054fdc  mov     rax, [rcx]
0x180054fdf  lea     rdx, [rsp+200h+var_1C8]
0x180054fe4  mov     rax, [rax+18h]
0x180054fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054fed  mov     ebx, eax
0x180054fef  xor     eax, eax
0x180054ff1  test    ebx, ebx
0x180054ff3  js      loc_180055177
0x180054ff9  mov     r14d, eax
0x180054ffc  cmp     [rsp+200h+var_1C8], eax
0x180055000  jbe     loc_180055177
0x180055006  lea     r8, [rsp+200h+var_1C0]; struct CONFIG_ELEMENT_TABLE **
0x18005500b  mov     edx, r14d; unsigned int
0x18005500e  mov     rcx, r13; this
0x180055011  call    ?GetLocationByIndexInternal@CONFIG_FILE@@QEAAJKPEAPEAVCONFIG_ELEMENT_TABLE@@@Z; CONFIG_FILE::GetLocationByIndexInternal(ulong,CONFIG_ELEMENT_TABLE * *)
0x180055016  mov     rsi, [rsp+200h+var_1C0]
0x18005501b  mov     ebx, eax
0x18005501d  test    eax, eax
0x18005501f  js      loc_18005516A
0x180055025  lea     rcx, [rsi+10h]
0x180055029  mov     rax, [rcx]
0x18005502c  lea     rdx, [rsp+200h+var_1D8]
0x180055031  mov     rax, [rax+18h]
0x180055035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005503a  mov     ebx, eax
0x18005503c  xor     eax, eax
0x18005503e  test    ebx, ebx
0x180055040  js      loc_18005516A
0x180055046  mov     rdx, [rsp+200h+var_1D8]; unsigned __int16 *
0x18005504b  cmp     [rdx], ax
0x18005504e  jz      loc_18005514D
0x180055054  cmp     word ptr [rdx], 2Eh ; '.'
0x180055058  jnz     short loc_180055064
0x18005505a  cmp     [rdx+2], ax
0x18005505e  jz      loc_18005514D
0x180055064  mov     rcx, r15; this
0x180055067  call    ?ContainsChangedPath@GRANULAR_CHANGE_LIST@@AEAAHPEBG@Z; GRANULAR_CHANGE_LIST::ContainsChangedPath(ushort const *)
0x18005506c  test    eax, eax
0x18005506e  jnz     loc_18005514D
0x180055074  mov     rdx, [rsp+200h+var_1D8]
0x180055079  lea     rcx, [rbp+100h+var_178]
0x18005507d  call    cs:__imp_?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z; MULTISZ::FindStringNoCase(ushort const *)
0x180055083  xor     ecx, ecx
0x180055085  test    eax, eax
0x180055087  jnz     loc_18005514D
0x18005508d  mov     rdx, [rsp+200h+var_1D8]; unsigned __int16 *
0x180055092  lea     r8, [rsp+200h+var_1D0]; struct CONFIG_ELEMENT_TABLE **
0x180055097  mov     [rsp+200h+var_1E0], ecx
0x18005509b  mov     rcx, r12; this
0x18005509e  call    ?FindLocationInternal@CONFIG_FILE@@QEAAJPEBGPEAPEAVCONFIG_ELEMENT_TABLE@@@Z; CONFIG_FILE::FindLocationInternal(ushort const *,CONFIG_ELEMENT_TABLE * *)
0x1800550a3  mov     rdi, [rsp+200h+var_1D0]
0x1800550a8  mov     ebx, eax
0x1800550aa  test    eax, eax
0x1800550ac  jns     short loc_1800550C2
0x1800550ae  cmp     eax, 80070003h
0x1800550b3  jnz     loc_18005516A
0x1800550b9  mov     eax, 1
0x1800550be  xor     ebx, ebx
0x1800550c0  jmp     short loc_1800550D8
0x1800550c2  lea     r9, [rsp+200h+var_1E0]; int *
0x1800550c7  mov     r8, rsi; struct CONFIG_ELEMENT_TABLE *
0x1800550ca  mov     rdx, rdi; struct CONFIG_ELEMENT_TABLE *
0x1800550cd  call    ?CompareLocations@GRANULAR_CHANGE_LIST@@AEAAJPEAVCONFIG_ELEMENT_TABLE@@0PEAH@Z; GRANULAR_CHANGE_LIST::CompareLocations(CONFIG_ELEMENT_TABLE *,CONFIG_ELEMENT_TABLE *,int *)
0x1800550d2  mov     ebx, eax
0x1800550d4  mov     eax, [rsp+200h+var_1E0]
0x1800550d8  test    ebx, ebx
0x1800550da  js      loc_18005516A
0x1800550e0  test    eax, eax
0x1800550e2  jz      short loc_180055139
0x1800550e4  lea     rdx, aMachineWebroot_1; "MACHINE/WEBROOT/APPHOST/"
0x1800550eb  lea     rcx, [rsp+200h+var_1B0]
0x1800550f0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800550f6  mov     ebx, eax
0x1800550f8  test    eax, eax
0x1800550fa  js      short loc_18005516A
0x1800550fc  mov     rdx, [rsp+200h+var_1D8]
0x180055101  lea     rcx, [rsp+200h+var_1B0]
0x180055106  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18005510c  mov     ebx, eax
0x18005510e  test    eax, eax
0x180055110  js      short loc_18005516A
0x180055112  lea     rcx, [rsp+200h+var_1B0]
0x180055117  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18005511d  mov     rdx, rax; unsigned __int16 *
0x180055120  mov     rcx, r15; this
0x180055123  mov     eax, 1
0x180055128  mov     r9d, eax; int
0x18005512b  mov     r8d, eax; int
0x18005512e  call    ?AppendChangedPath@GRANULAR_CHANGE_LIST@@AEAAJPEBGHH@Z; GRANULAR_CHANGE_LIST::AppendChangedPath(ushort const *,int,int)
0x180055133  mov     ebx, eax
0x180055135  test    eax, eax
0x180055137  js      short loc_18005516A
0x180055139  test    rdi, rdi
0x18005513c  jz      short loc_18005514D
0x18005513e  mov     rcx, rdi; this
0x180055141  call    ?DereferenceConfigElementTable@CONFIG_ELEMENT_TABLE@@QEAAXXZ; CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(void)
0x180055146  xor     edi, edi
0x180055148  mov     [rsp+200h+var_1D0], rdi
0x18005514d  mov     rcx, rsi; this
0x180055150  call    ?DereferenceConfigElementTable@CONFIG_ELEMENT_TABLE@@QEAAXXZ; CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(void)
0x180055155  xor     esi, esi
0x180055157  inc     r14d
0x18005515a  mov     [rsp+200h+var_1C0], rsi
0x18005515f  cmp     r14d, [rsp+200h+var_1C8]
0x180055164  jb      loc_180055006
0x18005516a  test    rdi, rdi
0x18005516d  jz      short loc_180055177
0x18005516f  mov     rcx, rdi; this
0x180055172  call    ?DereferenceConfigElementTable@CONFIG_ELEMENT_TABLE@@QEAAXXZ; CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(void)
0x180055177  test    rsi, rsi
0x18005517a  jz      short loc_180055184
0x18005517c  mov     rcx, rsi; this
0x18005517f  call    ?DereferenceConfigElementTable@CONFIG_ELEMENT_TABLE@@QEAAXXZ; CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(void)
0x180055184  lea     rcx, [rbp+100h+var_178]
0x180055188  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18005518e  lea     rcx, [rsp+200h+var_1B0]
0x180055193  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180055199  mov     eax, ebx
0x18005519b  mov     rcx, [rbp+100h+var_40]
0x1800551a2  xor     rcx, rsp; StackCookie
0x1800551a5  call    __security_check_cookie
0x1800551aa  mov     rbx, [rsp+200h+arg_18]
0x1800551b2  add     rsp, 1D0h
0x1800551b9  pop     r15
0x1800551bb  pop     r14
0x1800551bd  pop     r13
0x1800551bf  pop     r12
0x1800551c1  pop     rdi
0x1800551c2  pop     rsi
0x1800551c3  pop     rbp
0x1800551c4  retn
```
