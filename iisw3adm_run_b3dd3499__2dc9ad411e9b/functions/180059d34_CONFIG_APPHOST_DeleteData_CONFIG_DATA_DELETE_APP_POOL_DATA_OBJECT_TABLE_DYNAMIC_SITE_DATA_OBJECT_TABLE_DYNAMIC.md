# CONFIG_APPHOST::DeleteData(CONFIG_DATA_DELETE *,APP_POOL_DATA_OBJECT_TABLE_DYNAMIC *,SITE_DATA_OBJECT_TABLE_DYNAMIC *,APPLICATION_DATA_OBJECT_TABLE_DYNAMIC *)

- ea: `0x180059d34`
- end: `0x18005a31f`
- name: `?DeleteData@CONFIG_APPHOST@@QEAAJPEAUCONFIG_DATA_DELETE@@PEAVAPP_POOL_DATA_OBJECT_TABLE_DYNAMIC@@PEAVSITE_DATA_OBJECT_TABLE_DYNAMIC@@PEAVAPPLICATION_DATA_OBJECT_TABLE_DYNAMIC@@@Z`
- size: `1515`
- prototype: `__int64 __fastcall(CONFIG_APPHOST *__hidden this, struct CONFIG_DATA_DELETE *, struct APP_POOL_DATA_OBJECT_TABLE_DYNAMIC *, struct SITE_DATA_OBJECT_TABLE_DYNAMIC *, struct APPLICATION_DATA_OBJECT_TABLE_DYNAMIC *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800300b4`

## callees

- `0x18003a528`
- `0x180059d34`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180059e0a`
- `OLEAUT32!__imp_SysAllocString` at `0x180059f48`
- `OLEAUT32!__imp_SysAllocString` at `0x180059e0a`
- `OLEAUT32!__imp_SysAllocString` at `0x180059f48`
- `OLEAUT32!__imp_SysFreeString` at `0x180059ee9`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a0c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a13b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a267`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a277`
- `OLEAUT32!__imp_SysFreeString` at `0x180059ee9`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a0c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a13b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a267`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a277`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180059e8e`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180059fca`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18005a087`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18005a1b2`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180059e8e`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180059fca`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18005a087`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18005a1b2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005a2d7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005a2f7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005a2d7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005a2f7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180059da3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180059db8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180059da3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180059db8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005a059`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005a190`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005a059`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005a190`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180059df5`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180059f30`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180059df5`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180059f30`

## pseudocode

```c
__int64 __fastcall CONFIG_APPHOST::DeleteData(
        CONFIG_APPHOST *this,
        struct CONFIG_DATA_DELETE *a2,
        struct APP_POOL_DATA_OBJECT_TABLE_DYNAMIC *a3,
        struct SITE_DATA_OBJECT_TABLE_DYNAMIC *a4,
        struct APPLICATION_DATA_OBJECT_TABLE_DYNAMIC *a5)
{
  int v6; // ebx
  MULTISZ *v7; // r13
  SITE_DATA_OBJECT *v8; // rdi
  struct CONFIG_DATA_DELETE *v9; // r14
  SITE_DATA_OBJECT *v10; // r15
  const OLECHAR *v11; // r12
  BSTR v12; // rax
  OLECHAR *v13; // rsi
  int Key; // eax
  __int64 v15; // rax
  const OLECHAR *v16; // r12
  int v17; // eax
  int v18; // r13d
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  int v23; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v24; // [rsp+28h] [rbp-D8h] BYREF
  SITE_DATA_OBJECT *v25; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  struct CONFIG_DATA_DELETE *v29; // [rsp+50h] [rbp-B0h] BYREF
  CONFIG_APPHOST *v30; // [rsp+58h] [rbp-A8h]
  struct SITE_DATA_OBJECT_TABLE_DYNAMIC *v31; // [rsp+60h] [rbp-A0h]
  void **v32; // [rsp+68h] [rbp-98h] BYREF
  int v33; // [rsp+70h] [rbp-90h]
  struct APPLICATION_DATA_OBJECT_TABLE_DYNAMIC *v34; // [rsp+78h] [rbp-88h]
  struct APP_POOL_DATA_OBJECT_TABLE_DYNAMIC *v35; // [rsp+80h] [rbp-80h]
  void **v36; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v37[56]; // [rsp+98h] [rbp-68h] BYREF
  int v38; // [rsp+D0h] [rbp-30h]
  void **v39; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v40[56]; // [rsp+E8h] [rbp-18h] BYREF

  v34 = a5;
  v30 = this;
  v32 = &SITE_DATA_OBJECT_KEY::`vftable';
  v31 = a4;
  v39 = &APP_POOL_DATA_OBJECT_KEY::`vftable';
  v6 = 0;
  v35 = a3;
  v29 = a2;
  v33 = 0;
  STRU::STRU((STRU *)v40);
  v36 = &APPLICATION_DATA_OBJECT_KEY::`vftable';
  STRU::STRU((STRU *)v37);
  v7 = (struct CONFIG_DATA_DELETE *)((char *)a2 + 56);
  v38 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  bstrString = 0;
  v23 = 0;
  v24 = 0;
  v27 = 0;
  v28 = 0;
  if ( *((_DWORD *)a2 + 12) )
  {
    v11 = MULTISZ::First((struct CONFIG_DATA_DELETE *)((char *)a2 + 56));
    if ( v11 )
    {
      do
      {
        v12 = SysAllocString(v11);
        v13 = v12;
        if ( !v12 )
          goto LABEL_34;
        v6 = (*(__int64 (__fastcall **)(_QWORD, BSTR, __int64 *))(**((_QWORD **)v30 + 5) + 80LL))(
               *((_QWORD *)v30 + 5),
               v12,
               &v24);
        if ( v6 < 0 )
          goto LABEL_49;
        if ( !v24 )
          goto LABEL_49;
        v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 64LL))(v24, &v23);
        if ( v6 < 0 )
          goto LABEL_49;
        v25 = 0;
        v33 = v23;
        Key = CLKRHashTable::FindKey((char *)v31 + 8, &v32, &v25);
        v8 = v25;
        if ( !Key )
        {
          if ( *(_DWORD *)(*((_QWORD *)v25 + 7) + 8LL) > 1u
            || !SITE_DATA_OBJECT::QueryContainsAppPool(v25, *((const unsigned __int16 **)v29 + 4)) )
          {
            v6 = -2147467259;
            goto LABEL_49;
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 3, 0xFFFFFFFF) == 1 )
            (**(void (__fastcall ***)(SITE_DATA_OBJECT *, __int64))v8)(v8, 1);
          v8 = 0;
        }
        SysFreeString(v13);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        v24 = 0;
        v15 = -1;
        do
          ++v15;
        while ( v11[v15] );
        v11 += v15 + 1;
      }
      while ( *v11 && v11 );
    }
  }
  v16 = MULTISZ::First(v7);
  if ( v16 )
  {
    while ( 1 )
    {
      v13 = SysAllocString(v16);
      if ( !v13 )
        break;
      v6 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int64 *))(**((_QWORD **)v30 + 5) + 80LL))(
             *((_QWORD *)v30 + 5),
             v13,
             &v24);
      if ( v6 < 0 )
        goto LABEL_49;
      if ( !v24 )
        goto LABEL_49;
      v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 64LL))(v24, &v23);
      if ( v6 < 0 )
        goto LABEL_49;
      v33 = v23;
      v25 = 0;
      v17 = CLKRHashTable::FindKey((char *)v31 + 8, &v32, &v25);
      v8 = v25;
      if ( !v17 )
      {
        *((_DWORD *)v25 + 5) = 1;
        v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 112LL))(v24, &v27);
        if ( v6 < 0 )
          goto LABEL_49;
        while ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 56LL))(v27, &v28) >= 0 && v28 )
        {
          v6 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v28 + 56LL))(v28, &bstrString);
          if ( v6 < 0 )
            goto LABEL_49;
          v18 = v23;
          v6 = STRU::Copy((STRU *)v37, bstrString);
          if ( v6 < 0 )
            goto LABEL_49;
          v38 = v18;
          v25 = 0;
          v19 = CLKRHashTable::FindKey((char *)v34 + 8, &v36, &v25);
          v10 = v25;
          if ( !v19 )
          {
            *((_DWORD *)v25 + 5) = 1;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 3, 0xFFFFFFFF) == 1 )
              (**(void (__fastcall ***)(SITE_DATA_OBJECT *, __int64))v10)(v10, 1);
            v10 = 0;
          }
          SysFreeString(bstrString);
          bstrString = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          v28 = 0;
          v6 = 0;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        v27 = 0;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 3, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(SITE_DATA_OBJECT *, __int64))v8)(v8, 1);
        v8 = 0;
      }
      SysFreeString(v13);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      v20 = -1;
      v24 = 0;
      do
        ++v20;
      while ( v16[v20] );
      v16 += v20 + 1;
      if ( !*v16 || !v16 )
        goto LABEL_42;
    }
LABEL_34:
    v6 = -2147024882;
    goto LABEL_49;
  }
LABEL_42:
  if ( *((_DWORD *)v29 + 12) )
  {
    v6 = STRU::Copy((STRU *)v40, *((const unsigned __int16 **)v29 + 4));
    if ( v6 >= 0 )
    {
      v29 = 0;
      v21 = CLKRHashTable::FindKey((char *)v35 + 8, &v39, &v29);
      v9 = v29;
      if ( !v21 )
      {
        *((_DWORD *)v29 + 5) = 1;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 3, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(struct CONFIG_DATA_DELETE *, __int64))v9)(v9, 1);
        v9 = 0;
      }
    }
  }
  v13 = 0;
LABEL_49:
  if ( v8 && _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 3, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(SITE_DATA_OBJECT *, __int64))v8)(v8, 1);
  if ( v9 && _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 3, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(struct CONFIG_DATA_DELETE *, __int64))v9)(v9, 1);
  if ( v10 && _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 3, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(SITE_DATA_OBJECT *, __int64))v10)(v10, 1);
  if ( v13 )
    SysFreeString(v13);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  STRU::~STRU((STRU *)v37);
  v36 = &DATA_OBJECT_KEY::`vftable';
  v39 = &APP_POOL_DATA_OBJECT_KEY::`vftable';
  STRU::~STRU((STRU *)v40);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180059d34  push    rbp
0x180059d36  push    rbx
0x180059d37  push    rsi
0x180059d38  push    rdi
0x180059d39  push    r12
0x180059d3b  push    r13
0x180059d3d  push    r14
0x180059d3f  push    r15
0x180059d41  lea     rbp, [rsp-38h]
0x180059d46  sub     rsp, 138h
0x180059d4d  mov     rax, cs:__security_cookie
0x180059d54  xor     rax, rsp
0x180059d57  mov     [rbp+70h+var_50], rax
0x180059d5b  mov     rax, [rbp+70h+arg_20]
0x180059d62  xor     r12d, r12d
0x180059d65  mov     [rsp+170h+var_F8], rax
0x180059d6a  mov     rsi, rdx
0x180059d6d  lea     rax, ??_7SITE_DATA_OBJECT_KEY@@6B@; const SITE_DATA_OBJECT_KEY::`vftable'
0x180059d74  mov     [rsp+170h+var_118], rcx
0x180059d79  mov     [rsp+170h+var_108], rax
0x180059d7e  lea     rcx, [rbp+70h+var_88]
0x180059d82  lea     rax, ??_7APP_POOL_DATA_OBJECT_KEY@@6B@; const APP_POOL_DATA_OBJECT_KEY::`vftable'
0x180059d89  mov     [rsp+170h+var_110], r9
0x180059d8e  mov     [rbp+70h+var_90], rax
0x180059d92  mov     ebx, r12d
0x180059d95  mov     [rbp+70h+var_F0], r8
0x180059d99  mov     [rsp+170h+var_120], rdx
0x180059d9e  mov     [rsp+170h+var_100], r12d
0x180059da3  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180059da9  lea     rax, ??_7APPLICATION_DATA_OBJECT_KEY@@6B@; const APPLICATION_DATA_OBJECT_KEY::`vftable'
0x180059db0  lea     rcx, [rbp+70h+var_D8]
0x180059db4  mov     [rbp+70h+var_E0], rax
0x180059db8  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180059dbe  lea     r13, [rsi+38h]
0x180059dc2  mov     [rbp+70h+var_A0], r12d
0x180059dc6  mov     edi, r12d
0x180059dc9  mov     r14d, r12d
0x180059dcc  mov     r15d, r12d
0x180059dcf  mov     [rsp+170h+bstrString], r12
0x180059dd4  mov     [rsp+170h+var_150], r12d
0x180059dd9  mov     [rsp+170h+var_148], r12
0x180059dde  mov     [rsp+170h+var_130], r12
0x180059de3  mov     [rsp+170h+var_128], r12
0x180059de8  cmp     [rsi+30h], r12d
0x180059dec  jbe     loc_180059F2D
0x180059df2  mov     rcx, r13
0x180059df5  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x180059dfb  mov     r12, rax
0x180059dfe  test    rax, rax
0x180059e01  jz      loc_180059F2D
0x180059e07  mov     rcx, r12; psz
0x180059e0a  call    cs:__imp_SysAllocString
0x180059e10  mov     rsi, rax
0x180059e13  test    rax, rax
0x180059e16  jz      loc_18005A0F5
0x180059e1c  mov     rax, [rsp+170h+var_118]
0x180059e21  lea     r8, [rsp+170h+var_148]
0x180059e26  mov     rdx, rsi
0x180059e29  mov     rcx, [rax+28h]
0x180059e2d  mov     rax, [rcx]
0x180059e30  mov     rax, [rax+50h]
0x180059e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e39  mov     ebx, eax
0x180059e3b  test    eax, eax
0x180059e3d  js      loc_18005A1EB
0x180059e43  mov     rcx, [rsp+170h+var_148]
0x180059e48  test    rcx, rcx
0x180059e4b  jz      loc_18005A1EB
0x180059e51  mov     rax, [rcx]
0x180059e54  lea     rdx, [rsp+170h+var_150]
0x180059e59  mov     rax, [rax+40h]
0x180059e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e62  xor     ecx, ecx
0x180059e64  mov     ebx, eax
0x180059e66  test    eax, eax
0x180059e68  js      loc_18005A1EB
0x180059e6e  mov     eax, [rsp+170h+var_150]
0x180059e72  lea     r8, [rsp+170h+var_140]
0x180059e77  mov     [rsp+170h+var_140], rcx
0x180059e7c  lea     rdx, [rsp+170h+var_108]
0x180059e81  mov     rcx, [rsp+170h+var_110]
0x180059e86  add     rcx, 8
0x180059e8a  mov     [rsp+170h+var_100], eax
0x180059e8e  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180059e94  mov     rdi, [rsp+170h+var_140]
0x180059e99  test    eax, eax
0x180059e9b  jnz     short loc_180059EE6
0x180059e9d  mov     rax, [rdi+38h]
0x180059ea1  cmp     dword ptr [rax+8], 1
0x180059ea5  ja      loc_18005A0EB
0x180059eab  mov     rax, [rsp+170h+var_120]
0x180059eb0  mov     rcx, rdi; this
0x180059eb3  mov     rdx, [rax+20h]; unsigned __int16 *
0x180059eb7  call    ?QueryContainsAppPool@SITE_DATA_OBJECT@@QEAAHPEBG@Z; SITE_DATA_OBJECT::QueryContainsAppPool(ushort const *)
0x180059ebc  test    eax, eax
0x180059ebe  jz      loc_18005A0EB
0x180059ec4  or      eax, 0FFFFFFFFh
0x180059ec7  lock xadd [rdi+0Ch], eax
0x180059ecc  cmp     eax, 1
0x180059ecf  jnz     short loc_180059EE4
0x180059ed1  mov     rax, [rdi]
0x180059ed4  mov     edx, 1
0x180059ed9  mov     rcx, rdi
0x180059edc  mov     rax, [rax]
0x180059edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ee4  xor     edi, edi
0x180059ee6  mov     rcx, rsi; bstrString
0x180059ee9  call    cs:__imp_SysFreeString
0x180059eef  mov     rcx, [rsp+170h+var_148]
0x180059ef4  mov     rax, [rcx]
0x180059ef7  mov     rax, [rax+10h]
0x180059efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f00  xor     ecx, ecx
0x180059f02  mov     [rsp+170h+var_148], rcx
0x180059f07  or      rax, 0FFFFFFFFFFFFFFFFh
0x180059f0b  inc     rax
0x180059f0e  cmp     [r12+rax*2], cx
0x180059f13  jnz     short loc_180059F0B
0x180059f15  lea     r12, [r12+rax*2]
0x180059f19  add     r12, 2
0x180059f1d  cmp     [r12], cx
0x180059f22  jz      short loc_180059F2D
0x180059f24  test    r12, r12
0x180059f27  jnz     loc_180059E07
0x180059f2d  mov     rcx, r13
0x180059f30  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x180059f36  xor     r13d, r13d
0x180059f39  mov     r12, rax
0x180059f3c  test    rax, rax
0x180059f3f  jz      loc_18005A17D
0x180059f45  mov     rcx, r12; psz
0x180059f48  call    cs:__imp_SysAllocString
0x180059f4e  mov     rsi, rax
0x180059f51  test    rax, rax
0x180059f54  jz      loc_18005A0F5
0x180059f5a  mov     rax, [rsp+170h+var_118]
0x180059f5f  lea     r8, [rsp+170h+var_148]
0x180059f64  mov     rcx, [rax+28h]
0x180059f68  mov     rdx, [rcx]
0x180059f6b  mov     rax, [rdx+50h]
0x180059f6f  mov     rdx, rsi
0x180059f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f77  mov     ebx, eax
0x180059f79  test    eax, eax
0x180059f7b  js      loc_18005A1EB
0x180059f81  mov     rcx, [rsp+170h+var_148]
0x180059f86  test    rcx, rcx
0x180059f89  jz      loc_18005A1EB
0x180059f8f  mov     rax, [rcx]
0x180059f92  lea     rdx, [rsp+170h+var_150]
0x180059f97  mov     rax, [rax+40h]
0x180059f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059fa0  mov     ebx, eax
0x180059fa2  test    eax, eax
0x180059fa4  js      loc_18005A1EB
0x180059faa  mov     eax, [rsp+170h+var_150]
0x180059fae  lea     r8, [rsp+170h+var_140]
0x180059fb3  mov     rcx, [rsp+170h+var_110]
0x180059fb8  lea     rdx, [rsp+170h+var_108]
0x180059fbd  add     rcx, 8
0x180059fc1  mov     [rsp+170h+var_100], eax
0x180059fc5  mov     [rsp+170h+var_140], r13
0x180059fca  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180059fd0  mov     rdi, [rsp+170h+var_140]
0x180059fd5  test    eax, eax
0x180059fd7  jnz     loc_18005A138
0x180059fdd  mov     dword ptr [rdi+14h], 1
0x180059fe4  lea     rdx, [rsp+170h+var_130]
0x180059fe9  mov     rcx, [rsp+170h+var_148]
0x180059fee  mov     rax, [rcx]
0x180059ff1  mov     rax, [rax+70h]
0x180059ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ffa  mov     ebx, eax
0x180059ffc  test    eax, eax
0x180059ffe  js      loc_18005A1EB
0x18005a004  mov     rcx, [rsp+170h+var_130]
0x18005a009  lea     rdx, [rsp+170h+var_128]
0x18005a00e  mov     rax, [rcx]
0x18005a011  mov     rax, [rax+38h]
0x18005a015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a01a  test    eax, eax
0x18005a01c  js      loc_18005A0FF
0x18005a022  mov     rcx, [rsp+170h+var_128]
0x18005a027  test    rcx, rcx
0x18005a02a  jz      loc_18005A0FF
0x18005a030  mov     rax, [rcx]
0x18005a033  lea     rdx, [rsp+170h+bstrString]
0x18005a038  mov     rax, [rax+38h]
0x18005a03c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a041  mov     ebx, eax
0x18005a043  test    eax, eax
0x18005a045  js      loc_18005A1EB
0x18005a04b  mov     rdx, [rsp+170h+bstrString]
0x18005a050  lea     rcx, [rbp+70h+var_D8]
0x18005a054  mov     r13d, [rsp+170h+var_150]
0x18005a059  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005a05f  mov     ebx, eax
0x18005a061  test    eax, eax
0x18005a063  js      loc_18005A1EB
0x18005a069  mov     rcx, [rsp+170h+var_F8]
0x18005a06e  lea     r8, [rsp+170h+var_140]
0x18005a073  mov     [rbp+70h+var_A0], r13d
0x18005a077  lea     rdx, [rbp+70h+var_E0]
0x18005a07b  xor     r13d, r13d
0x18005a07e  add     rcx, 8
0x18005a082  mov     [rsp+170h+var_140], r13
0x18005a087  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18005a08d  mov     r15, [rsp+170h+var_140]
0x18005a092  test    eax, eax
0x18005a094  jnz     short loc_18005A0BD
0x18005a096  lea     ecx, [rax+1]
0x18005a099  or      eax, 0FFFFFFFFh
0x18005a09c  mov     [r15+14h], ecx
0x18005a0a0  lock xadd [r15+0Ch], eax
0x18005a0a6  cmp     eax, ecx
0x18005a0a8  jnz     short loc_18005A0BA
0x18005a0aa  mov     rax, [r15]
0x18005a0ad  mov     edx, ecx
0x18005a0af  mov     rcx, r15
0x18005a0b2  mov     rax, [rax]
0x18005a0b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a0ba  mov     r15, r13
0x18005a0bd  mov     rcx, [rsp+170h+bstrString]; bstrString
0x18005a0c2  call    cs:__imp_SysFreeString
0x18005a0c8  mov     rcx, [rsp+170h+var_128]
0x18005a0cd  mov     [rsp+170h+bstrString], r13
0x18005a0d2  mov     rax, [rcx]
0x18005a0d5  mov     rax, [rax+10h]
0x18005a0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a0de  mov     [rsp+170h+var_128], r13
0x18005a0e3  mov     ebx, r13d
0x18005a0e6  jmp     loc_18005A004
0x18005a0eb  mov     ebx, 80004005h
0x18005a0f0  jmp     loc_18005A1EB
0x18005a0f5  mov     ebx, 8007000Eh
0x18005a0fa  jmp     loc_18005A1EB
0x18005a0ff  mov     rcx, [rsp+170h+var_130]
0x18005a104  mov     rax, [rcx]
0x18005a107  mov     rax, [rax+10h]
0x18005a10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a110  or      eax, 0FFFFFFFFh
0x18005a113  mov     [rsp+170h+var_130], r13
0x18005a118  lock xadd [rdi+0Ch], eax
0x18005a11d  cmp     eax, 1
0x18005a120  jnz     short loc_18005A135
0x18005a122  mov     rax, [rdi]
0x18005a125  mov     edx, 1
0x18005a12a  mov     rcx, rdi
0x18005a12d  mov     rax, [rax]
0x18005a130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a135  mov     rdi, r13
0x18005a138  mov     rcx, rsi; bstrString
0x18005a13b  call    cs:__imp_SysFreeString
0x18005a141  mov     rcx, [rsp+170h+var_148]
0x18005a146  mov     rax, [rcx]
0x18005a149  mov     rax, [rax+10h]
0x18005a14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a152  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005a156  mov     [rsp+170h+var_148], r13
0x18005a15b  inc     rax
0x18005a15e  cmp     [r12+rax*2], r13w
0x18005a163  jnz     short loc_18005A15B
0x18005a165  lea     r12, [r12+rax*2]
0x18005a169  add     r12, 2
0x18005a16d  cmp     [r12], r13w
0x18005a172  jz      short loc_18005A17D
0x18005a174  test    r12, r12
0x18005a177  jnz     loc_180059F45
0x18005a17d  mov     rax, [rsp+170h+var_120]
0x18005a182  cmp     [rax+30h], r13d
0x18005a186  jbe     short loc_18005A1E8
0x18005a188  mov     rdx, [rax+20h]
0x18005a18c  lea     rcx, [rbp+70h+var_88]
0x18005a190  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005a196  mov     ebx, eax
0x18005a198  test    eax, eax
0x18005a19a  js      short loc_18005A1E8
0x18005a19c  mov     rcx, [rbp+70h+var_F0]
0x18005a1a0  lea     r8, [rsp+170h+var_120]
0x18005a1a5  add     rcx, 8
0x18005a1a9  mov     [rsp+170h+var_120], r13
0x18005a1ae  lea     rdx, [rbp+70h+var_90]
0x18005a1b2  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18005a1b8  mov     r14, [rsp+170h+var_120]
0x18005a1bd  test    eax, eax
0x18005a1bf  jnz     short loc_18005A1E8
0x18005a1c1  lea     ecx, [rax+1]
0x18005a1c4  or      eax, 0FFFFFFFFh
0x18005a1c7  mov     [r14+14h], ecx
0x18005a1cb  lock xadd [r14+0Ch], eax
0x18005a1d1  cmp     eax, ecx
0x18005a1d3  jnz     short loc_18005A1E5
0x18005a1d5  mov     rax, [r14]
0x18005a1d8  mov     edx, ecx
0x18005a1da  mov     rcx, r14
0x18005a1dd  mov     rax, [rax]
0x18005a1e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a1e5  mov     r14, r13
0x18005a1e8  mov     rsi, r13
0x18005a1eb  xor     r12d, r12d
  ... truncated ...
```
