# PROTOCOL_BINDING_TABLE::PopulateNoLock(void)

- ea: `0x180058b64`
- end: `0x180059281`
- name: `?PopulateNoLock@PROTOCOL_BINDING_TABLE@@QEAAJXZ`
- size: `1821`
- prototype: `__int64 __fastcall(PROTOCOL_BINDING_TABLE *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18005aaa0`

## callees

- `0x180001234`
- `0x180005878`
- `0x1800058e4`
- `0x180030578`
- `0x180050f2c`
- `0x180050ff0`
- `0x180057ebc`
- `0x1800584f0`
- `0x1800588e8`
- `0x180058b64`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180058ffc`
- `msvcrt!wcsncpy_s` at `0x180058ffc`
- `msvcrt!_ultow` at `0x180058f1c`
- `msvcrt!_ultow` at `0x180058f1c`
- `OLEAUT32!__imp_SysFreeString` at `0x180058cc7`
- `OLEAUT32!__imp_SysFreeString` at `0x180058cdf`
- `OLEAUT32!__imp_SysFreeString` at `0x180058e5a`
- `OLEAUT32!__imp_SysFreeString` at `0x18005911d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005912c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800591fd`
- `OLEAUT32!__imp_SysFreeString` at `0x180059211`
- `OLEAUT32!__imp_SysFreeString` at `0x180058cc7`
- `OLEAUT32!__imp_SysFreeString` at `0x180058cdf`
- `OLEAUT32!__imp_SysFreeString` at `0x180058e5a`
- `OLEAUT32!__imp_SysFreeString` at `0x18005911d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005912c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800591fd`
- `OLEAUT32!__imp_SysFreeString` at `0x180059211`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180059251`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180059251`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180058bb5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005907b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180058bb5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005907b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180058f73`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005909d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180058f73`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005909d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180058f8e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005900a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180058f8e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005900a`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180058e37`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180058e4b`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180058e37`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180058e4b`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18005901f`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18005901f`
- `iisutil!?FastAppend@MULTISZ@@QEAAHPEBG@Z` at `0x180058ee5`
- `iisutil!?FastAppend@MULTISZ@@QEAAHPEBG@Z` at `0x180058ee5`

## pseudocode

```c
__int64 __fastcall PROTOCOL_BINDING_TABLE::PopulateNoLock(PROTOCOL_BINDING_TABLE *this)
{
  __int64 *v2; // rcx
  __int64 v3; // rax
  int updated; // ebx
  __int64 *v5; // rdi
  __int64 v6; // rax
  int v7; // r8d
  struct STATIC_WSTRING_HASH_RECORD *Key; // rax
  struct BINDING_APPPOOL_ENTRY *v9; // rax
  struct STATIC_WSTRING_HASH_RECORD *v10; // rdx
  OLECHAR *v11; // rcx
  __int64 v12; // rcx
  struct IAppHostProvider *v13; // rdx
  struct BINDING_SITE_ENTRY *v14; // rsi
  const unsigned __int16 *v15; // rdi
  struct PROTOCOL_BINDING_ENTRY *v16; // rbx
  BSTR v17; // rdi
  int v18; // r8d
  OLECHAR *v19; // r9
  int v20; // eax
  __int64 v21; // rcx
  OLECHAR *v22; // r8
  struct STATIC_WSTRING_HASH_RECORD *v23; // rax
  _DWORD *v24; // rdi
  unsigned __int16 *v25; // rbx
  int v26; // eax
  __int16 v28[2]; // [rsp+30h] [rbp-99h] BYREF
  __int16 v29; // [rsp+34h] [rbp-95h] BYREF
  BSTR v30; // [rsp+38h] [rbp-91h] BYREF
  __int64 v31; // [rsp+40h] [rbp-89h] BYREF
  struct IAppHostSite *v32; // [rsp+48h] [rbp-81h] BYREF
  BSTR v33; // [rsp+50h] [rbp-79h] BYREF
  __int64 v34; // [rsp+58h] [rbp-71h] BYREF
  __int64 *v35; // [rsp+60h] [rbp-69h] BYREF
  __int64 v36; // [rsp+68h] [rbp-61h] BYREF
  __int64 v37; // [rsp+70h] [rbp-59h] BYREF
  struct BINDING_APPPOOL_ENTRY *v38[2]; // [rsp+78h] [rbp-51h] BYREF
  struct BINDING_SITE_ENTRY *v39; // [rsp+88h] [rbp-41h] BYREF
  struct PROTOCOL_BINDING_ENTRY *v40; // [rsp+90h] [rbp-39h] BYREF
  _BYTE v41[32]; // [rsp+98h] [rbp-31h] BYREF
  unsigned __int16 *v42; // [rsp+B8h] [rbp-11h]
  BSTR bstrString; // [rsp+D0h] [rbp+7h] BYREF
  int v44; // [rsp+D8h] [rbp+Fh]
  wchar_t Buffer[12]; // [rsp+E0h] [rbp+17h] BYREF

  v37 = 0;
  v34 = 0;
  v32 = 0;
  v31 = 0;
  v30 = 0;
  v33 = 0;
  STRU::STRU((STRU *)v41);
  v2 = (__int64 *)*((_QWORD *)this + 135);
  v35 = 0;
  v36 = 0;
  v28[0] = 0;
  v3 = *v2;
  v40 = 0;
  v39 = 0;
  updated = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v3 + 72))(v2, &v36);
  if ( updated < 0 )
    goto LABEL_69;
  while ( (*(int (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v36 + 56LL))(v36, &v35) >= 0 )
  {
    v5 = v35;
    if ( !v35 )
      break;
    v6 = *v35;
    bstrString = 0;
    v29 = 0;
    updated = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v6 + 56))(v35, &bstrString);
    if ( updated >= 0 )
    {
      Key = STATIC_WSTRING_HASH::FindKey((PROTOCOL_BINDING_TABLE *)((char *)this + 3256), bstrString, v7);
      v38[0] = (struct BINDING_APPPOOL_ENTRY *)(((unsigned __int64)Key - 8) & -(__int64)(Key != 0));
      if ( v38[0] )
        goto LABEL_13;
      updated = BINDING_APPPOOL_ENTRY::Create(bstrString, v38);
      if ( updated >= 0 )
      {
        updated = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(*v5 + 72))(v5, &v29);
        if ( updated >= 0 )
        {
          v9 = v38[0];
          if ( !v29 )
            *((_DWORD *)v38[0] + 22) = 4;
          v10 = (struct BINDING_APPPOOL_ENTRY *)((char *)v9 + 8);
          if ( !v9 )
            v10 = 0;
          STATIC_WSTRING_HASH::InsertRecord((PROTOCOL_BINDING_TABLE *)((char *)this + 3256), v10);
          ++*((_DWORD *)this + 1078);
LABEL_13:
          SysFreeString(bstrString);
          v11 = 0;
          bstrString = 0;
          goto LABEL_15;
        }
      }
    }
    v11 = bstrString;
LABEL_15:
    if ( v11 )
      SysFreeString(v11);
    if ( updated < 0 )
      goto LABEL_69;
    (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
    v35 = 0;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  v12 = *((_QWORD *)this + 135);
  v36 = 0;
  updated = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 64LL))(v12, &v37);
  if ( updated < 0 )
    goto LABEL_69;
LABEL_20:
  if ( (*(int (__fastcall **)(__int64, struct IAppHostSite **))(*(_QWORD *)v37 + 56LL))(v37, &v32) >= 0 )
  {
    if ( v32 )
    {
      updated = (*(__int64 (__fastcall **)(struct IAppHostSite *, __int16 *))(*(_QWORD *)v32 + 72LL))(v32, v28);
      if ( updated >= 0 )
      {
        updated = BINDING_SITE_TABLE::Insert(
                    (PROTOCOL_BINDING_TABLE *)((char *)this + 2176),
                    v13,
                    v32,
                    (PROTOCOL_BINDING_TABLE *)((char *)this + 3248),
                    &v39);
        if ( updated >= 0 )
        {
          v14 = v39;
          if ( !v28[0] )
            *((_DWORD *)v39 + 23) = 4;
          updated = (*(__int64 (__fastcall **)(struct IAppHostSite *, __int64 *))(*(_QWORD *)v32 + 80LL))(v32, &v34);
          if ( updated >= 0 )
          {
            while ( 1 )
            {
              if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 56LL))(v34, &v31) < 0 || !v31 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                v34 = 0;
                (*(void (__fastcall **)(struct IAppHostSite *))(*(_QWORD *)v32 + 16LL))(v32);
                v32 = 0;
                goto LABEL_20;
              }
              updated = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v31 + 56LL))(v31, &v30);
              if ( updated < 0 )
                break;
              v15 = v30;
              if ( IsStringEqualOrdinalIgnoreCase(L"http", v30) || IsStringEqualOrdinalIgnoreCase(L"https", v15) )
              {
                updated = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v31 + 64LL))(v31, &v33);
                if ( updated < 0 )
                  break;
                if ( (unsigned int)QueryIsIpPortHostOrStarPortBinding(v33) )
                {
                  updated = PROTOCOL_BINDING_TABLE::InsertOrUpdateNoLock(this, v32, v30, v33, &v40);
                  if ( updated < 0 )
                    break;
                  v16 = v40;
                  if ( !MULTISZ::FastAppend(
                          (struct BINDING_SITE_ENTRY *)((char *)v14 + 120),
                          *((const unsigned __int16 **)v40 + 8)) )
                  {
LABEL_68:
                    updated = -2147024882;
                    break;
                  }
                  if ( v28[0] == -1 )
                  {
                    if ( *((_DWORD *)v16 + 22) )
                    {
                      *((_DWORD *)v14 + 23) = 4;
                      *(_OWORD *)v38 = 0;
                      _ultow(*((_DWORD *)v14 + 22), Buffer, 10);
                      v38[0] = *((struct BINDING_APPPOOL_ENTRY **)v16 + 8);
                      v38[1] = (struct BINDING_APPPOOL_ENTRY *)Buffer;
                      WEB_ADMIN_SERVICE::LogW3svcEvent(
                        g_pWebAdminService,
                        0xC00003EF,
                        2u,
                        (const unsigned __int16 **const)v38,
                        0x800700B7);
                    }
                    else
                    {
                      *((_DWORD *)v16 + 22) = *((_DWORD *)v14 + 22);
                    }
                  }
                  v17 = v33;
                  bstrString = 0;
                  v44 = 0;
                  updated = STRU::Copy((STRU *)v41, v30);
                  if ( updated >= 0 )
                  {
                    updated = STRU::Append((STRU *)v41, L"://*:");
                    if ( updated >= 0 )
                    {
                      v19 = 0;
                      v20 = 0;
                      v21 = -1;
                      do
                        ++v21;
                      while ( v17[v21] );
                      v22 = &v17[v21];
                      if ( v22 == v17 )
                        goto LABEL_52;
                      do
                      {
                        if ( *v22 == 58 )
                        {
                          if ( ++v20 == 2 )
                            break;
                          v19 = v22;
                        }
                        --v22;
                      }
                      while ( v22 != v17 );
                      if ( v22 == v17 )
                      {
LABEL_52:
                        if ( *v22 == 58 )
                          ++v20;
                      }
                      if ( v20 != 2 )
                      {
                        updated = -2147024809;
                        break;
                      }
                      wcsncpy_s((wchar_t *)&bstrString, 6u, v22 + 1, v19 - (v22 + 1));
                      updated = STRU::Append((STRU *)v41, (const unsigned __int16 *)&bstrString);
                      if ( updated >= 0 )
                        updated = STRU::Append((STRU *)v41, 0x2Fu);
                    }
                  }
                  if ( updated < 0 )
                    break;
                  v23 = STATIC_WSTRING_HASH::FindKey((PROTOCOL_BINDING_TABLE *)((char *)this + 1096), v42, v18);
                  v24 = (_DWORD *)(((unsigned __int64)v23 - 8) & -(__int64)(v23 != 0));
                  if ( !v24 )
                  {
                    v25 = v42;
                    v24 = operator new(0x68u);
                    if ( !v24 )
                      goto LABEL_68;
                    *(_QWORD *)v24 = &PROTOCOL_PORT_ENTRY::`vftable';
                    STRU::STRU((STRU *)(v24 + 8));
                    v24[22] = 0;
                    *((_QWORD *)v24 + 12) = 0;
                    *((_QWORD *)v24 + 1) = 0;
                    *((_WORD *)v24 + 12) = 0;
                    *((_QWORD *)v24 + 2) = 0;
                    updated = STRU::Copy((STRU *)(v24 + 8), v25);
                    if ( updated < 0 )
                    {
                      (**(void (__fastcall ***)(void *, __int64))v24)(v24, 1);
                      break;
                    }
                    *((_QWORD *)v24 + 1) = *((_QWORD *)v24 + 8);
                    *((_WORD *)v24 + 12) = *((_WORD *)v24 + 40);
                    STATIC_WSTRING_HASH::InsertRecord(
                      (PROTOCOL_BINDING_TABLE *)((char *)this + 1096),
                      (struct STATIC_WSTRING_HASH_RECORD *)((unsigned __int64)(v24 + 2)
                                                          & ((unsigned __int128)-(__int128)(unsigned __int64)v24 >> 64)));
                    ++*((_DWORD *)this + 538);
                  }
                  v26 = *((_DWORD *)v14 + 22);
                  *((_QWORD *)v24 + 12) = *((_QWORD *)v14 + 8);
                  v24[22] = v26;
                }
                else
                {
                  v38[0] = (struct BINDING_APPPOOL_ENTRY *)v33;
                  WEB_ADMIN_SERVICE::LogEvent(
                    g_pWebAdminService,
                    0x8000145D,
                    1u,
                    (const unsigned __int16 **const)v38,
                    0);
                }
                SysFreeString(v30);
                v30 = 0;
                SysFreeString(v33);
                v33 = 0;
              }
              else
              {
                SysFreeString(v30);
                v30 = 0;
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
              v31 = 0;
            }
          }
        }
      }
    }
  }
LABEL_69:
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(struct IAppHostSite *))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v30 )
  {
    SysFreeString(v30);
    v30 = 0;
  }
  if ( v33 )
  {
    SysFreeString(v33);
    v33 = 0;
  }
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
    v35 = 0;
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  STRU::~STRU((STRU *)v41);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180058b64  mov     [rsp-8+arg_8], rbx
0x180058b69  mov     [rsp-8+arg_10], rsi
0x180058b6e  push    rbp
0x180058b6f  push    rdi
0x180058b70  push    r12
0x180058b72  push    r14
0x180058b74  push    r15
0x180058b76  lea     rbp, [rsp-37h]
0x180058b7b  sub     rsp, 100h
0x180058b82  mov     rax, cs:__security_cookie
0x180058b89  xor     rax, rsp
0x180058b8c  mov     [rbp+57h+var_28], rax
0x180058b90  xor     r12d, r12d
0x180058b93  mov     r15, rcx
0x180058b96  lea     rcx, [rbp+57h+var_88]
0x180058b9a  mov     [rbp+57h+var_B0], r12
0x180058b9e  mov     [rbp+57h+var_C8], r12
0x180058ba2  mov     [rsp+120h+var_D8], r12
0x180058ba7  mov     [rsp+120h+var_E0], r12
0x180058bac  mov     [rsp+120h+var_E8], r12
0x180058bb1  mov     [rbp+57h+var_D0], r12
0x180058bb5  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180058bbb  mov     rcx, [r15+438h]
0x180058bc2  lea     rdx, [rbp+57h+var_B8]
0x180058bc6  mov     [rbp+57h+var_C0], r12
0x180058bca  mov     [rbp+57h+var_B8], r12
0x180058bce  mov     [rsp+120h+var_F0], r12w
0x180058bd4  mov     rax, [rcx]
0x180058bd7  mov     [rbp+57h+var_90], r12
0x180058bdb  mov     [rbp+57h+var_98], r12
0x180058bdf  mov     rax, [rax+48h]
0x180058be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058be8  mov     ebx, eax
0x180058bea  test    eax, eax
0x180058bec  js      loc_18005918B
0x180058bf2  mov     rcx, [rbp+57h+var_B8]
0x180058bf6  lea     rdx, [rbp+57h+var_C0]
0x180058bfa  mov     rax, [rcx]
0x180058bfd  mov     rax, [rax+38h]
0x180058c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058c06  test    eax, eax
0x180058c08  js      loc_180058D06
0x180058c0e  mov     rdi, [rbp+57h+var_C0]
0x180058c12  test    rdi, rdi
0x180058c15  jz      loc_180058D06
0x180058c1b  mov     rax, [rdi]
0x180058c1e  lea     rdx, [rbp+57h+bstrString]
0x180058c22  mov     rcx, rdi
0x180058c25  mov     [rbp+57h+bstrString], r12
0x180058c29  mov     [rsp+120h+var_EC], r12w
0x180058c2f  mov     rax, [rax+38h]
0x180058c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058c38  mov     ebx, eax
0x180058c3a  test    eax, eax
0x180058c3c  js      loc_180058CD6
0x180058c42  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x180058c46  lea     rsi, [r15+0CB8h]
0x180058c4d  mov     rcx, rsi; this
0x180058c50  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x180058c55  lea     rcx, [rax-8]
0x180058c59  neg     rax
0x180058c5c  sbb     rax, rax
0x180058c5f  and     rax, rcx
0x180058c62  mov     [rbp+57h+var_A8], rax
0x180058c66  jnz     short loc_180058CC3
0x180058c68  mov     rcx, [rbp+57h+bstrString]; unsigned __int16 *
0x180058c6c  lea     rdx, [rbp+57h+var_A8]; struct BINDING_APPPOOL_ENTRY **
0x180058c70  call    ?Create@BINDING_APPPOOL_ENTRY@@SAJPEBGPEAPEAV1@@Z; BINDING_APPPOOL_ENTRY::Create(ushort const *,BINDING_APPPOOL_ENTRY * *)
0x180058c75  mov     ebx, eax
0x180058c77  test    eax, eax
0x180058c79  js      short loc_180058CD6
0x180058c7b  mov     rax, [rdi]
0x180058c7e  lea     rdx, [rsp+120h+var_EC]
0x180058c83  mov     rcx, rdi
0x180058c86  mov     rax, [rax+48h]
0x180058c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058c8f  mov     ebx, eax
0x180058c91  test    eax, eax
0x180058c93  js      short loc_180058CD6
0x180058c95  mov     rax, [rbp+57h+var_A8]
0x180058c99  cmp     [rsp+120h+var_EC], r12w
0x180058c9f  jnz     short loc_180058CA8
0x180058ca1  mov     dword ptr [rax+58h], 4
0x180058ca8  lea     rdx, [rax+8]
0x180058cac  test    rax, rax
0x180058caf  jnz     short loc_180058CB4
0x180058cb1  mov     rdx, r12; struct STATIC_WSTRING_HASH_RECORD *
0x180058cb4  mov     rcx, rsi; this
0x180058cb7  call    ?InsertRecord@STATIC_WSTRING_HASH@@QEAAXPEAUSTATIC_WSTRING_HASH_RECORD@@@Z; STATIC_WSTRING_HASH::InsertRecord(STATIC_WSTRING_HASH_RECORD *)
0x180058cbc  inc     dword ptr [r15+10D8h]
0x180058cc3  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180058cc7  call    cs:__imp_SysFreeString
0x180058ccd  mov     rcx, r12
0x180058cd0  mov     [rbp+57h+bstrString], rcx
0x180058cd4  jmp     short loc_180058CDA
0x180058cd6  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180058cda  test    rcx, rcx
0x180058cdd  jz      short loc_180058CE5
0x180058cdf  call    cs:__imp_SysFreeString
0x180058ce5  test    ebx, ebx
0x180058ce7  js      loc_18005918B
0x180058ced  mov     rcx, [rbp+57h+var_C0]
0x180058cf1  mov     rax, [rcx]
0x180058cf4  mov     rax, [rax+10h]
0x180058cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058cfd  mov     [rbp+57h+var_C0], r12
0x180058d01  jmp     loc_180058BF2
0x180058d06  mov     rcx, [rbp+57h+var_B8]
0x180058d0a  mov     rax, [rcx]
0x180058d0d  mov     rax, [rax+10h]
0x180058d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058d16  mov     rcx, [r15+438h]
0x180058d1d  lea     rdx, [rbp+57h+var_B0]
0x180058d21  mov     [rbp+57h+var_B8], r12
0x180058d25  mov     rax, [rcx]
0x180058d28  mov     rax, [rax+40h]
0x180058d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058d31  mov     ebx, eax
0x180058d33  test    eax, eax
0x180058d35  js      loc_18005918B
0x180058d3b  or      r14, 0FFFFFFFFFFFFFFFFh
0x180058d3f  mov     rcx, [rbp+57h+var_B0]
0x180058d43  lea     rdx, [rsp+120h+var_D8]
0x180058d48  mov     rax, [rcx]
0x180058d4b  mov     rax, [rax+38h]
0x180058d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058d54  test    eax, eax
0x180058d56  js      loc_18005918B
0x180058d5c  mov     rcx, [rsp+120h+var_D8]
0x180058d61  test    rcx, rcx
0x180058d64  jz      loc_18005918B
0x180058d6a  mov     rax, [rcx]
0x180058d6d  lea     rdx, [rsp+120h+var_F0]
0x180058d72  mov     rax, [rax+48h]
0x180058d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058d7b  mov     ebx, eax
0x180058d7d  test    eax, eax
0x180058d7f  js      loc_18005918B
0x180058d85  mov     r8, [rsp+120h+var_D8]; struct IAppHostSite *
0x180058d8a  lea     rax, [rbp+57h+var_98]
0x180058d8e  lea     r9, [r15+0CB0h]; struct BINDING_APPPOOL_TABLE *
0x180058d95  mov     [rsp+120h+var_100], rax; struct BINDING_SITE_ENTRY **
0x180058d9a  lea     rcx, [r15+880h]; this
0x180058da1  call    ?Insert@BINDING_SITE_TABLE@@QEAAJPEAUIAppHostProvider@@PEAUIAppHostSite@@PEAVBINDING_APPPOOL_TABLE@@PEAPEAVBINDING_SITE_ENTRY@@@Z; BINDING_SITE_TABLE::Insert(IAppHostProvider *,IAppHostSite *,BINDING_APPPOOL_TABLE *,BINDING_SITE_ENTRY * *)
0x180058da6  mov     ebx, eax
0x180058da8  test    eax, eax
0x180058daa  js      loc_18005918B
0x180058db0  mov     rsi, [rbp+57h+var_98]
0x180058db4  cmp     [rsp+120h+var_F0], r12w
0x180058dba  jnz     short loc_180058DC3
0x180058dbc  mov     dword ptr [rsi+5Ch], 4
0x180058dc3  mov     rcx, [rsp+120h+var_D8]
0x180058dc8  lea     rdx, [rbp+57h+var_C8]
0x180058dcc  mov     rax, [rcx]
0x180058dcf  mov     rax, [rax+50h]
0x180058dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058dd8  mov     ebx, eax
0x180058dda  test    eax, eax
0x180058ddc  js      loc_18005918B
0x180058de2  mov     rcx, [rbp+57h+var_C8]
0x180058de6  lea     rdx, [rsp+120h+var_E0]
0x180058deb  mov     rax, [rcx]
0x180058dee  mov     rax, [rax+38h]
0x180058df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058df7  test    eax, eax
0x180058df9  js      loc_18005913B
0x180058dff  mov     rcx, [rsp+120h+var_E0]
0x180058e04  test    rcx, rcx
0x180058e07  jz      loc_18005913B
0x180058e0d  mov     rax, [rcx]
0x180058e10  lea     rdx, [rsp+120h+var_E8]
0x180058e15  mov     rax, [rax+38h]
0x180058e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e1e  mov     ebx, eax
0x180058e20  test    eax, eax
0x180058e22  js      loc_18005918B
0x180058e28  mov     rdi, [rsp+120h+var_E8]
0x180058e2d  lea     rcx, aHttp_2; "http"
0x180058e34  mov     rdx, rdi
0x180058e37  call    cs:__imp_?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z; IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)
0x180058e3d  test    al, al
0x180058e3f  jnz     short loc_180058E80
0x180058e41  mov     rdx, rdi
0x180058e44  lea     rcx, aHttps_1; "https"
0x180058e4b  call    cs:__imp_?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z; IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)
0x180058e51  test    al, al
0x180058e53  jnz     short loc_180058E80
0x180058e55  mov     rcx, [rsp+120h+var_E8]; bstrString
0x180058e5a  call    cs:__imp_SysFreeString
0x180058e60  mov     [rsp+120h+var_E8], r12
0x180058e65  mov     rcx, [rsp+120h+var_E0]
0x180058e6a  mov     rax, [rcx]
0x180058e6d  mov     rax, [rax+10h]
0x180058e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e76  mov     [rsp+120h+var_E0], r12
0x180058e7b  jmp     loc_180058DE2
0x180058e80  mov     rcx, [rsp+120h+var_E0]
0x180058e85  lea     rdx, [rbp+57h+var_D0]
0x180058e89  mov     rax, [rcx]
0x180058e8c  mov     rax, [rax+40h]
0x180058e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e95  mov     ebx, eax
0x180058e97  test    eax, eax
0x180058e99  js      loc_18005918B
0x180058e9f  mov     rcx, [rbp+57h+var_D0]; unsigned __int16 *
0x180058ea3  call    ?QueryIsIpPortHostOrStarPortBinding@@YAHPEBG@Z; QueryIsIpPortHostOrStarPortBinding(ushort const *)
0x180058ea8  test    eax, eax
0x180058eaa  jz      loc_1800590F0
0x180058eb0  mov     r9, [rbp+57h+var_D0]; unsigned __int16 *
0x180058eb4  lea     rax, [rbp+57h+var_90]
0x180058eb8  mov     r8, [rsp+120h+var_E8]; unsigned __int16 *
0x180058ebd  mov     rcx, r15; this
0x180058ec0  mov     rdx, [rsp+120h+var_D8]; struct IAppHostSite *
0x180058ec5  mov     [rsp+120h+var_100], rax; struct PROTOCOL_BINDING_ENTRY **
0x180058eca  call    ?InsertOrUpdateNoLock@PROTOCOL_BINDING_TABLE@@QEAAJPEAUIAppHostSite@@PEBG1PEAPEAVPROTOCOL_BINDING_ENTRY@@@Z; PROTOCOL_BINDING_TABLE::InsertOrUpdateNoLock(IAppHostSite *,ushort const *,ushort const *,PROTOCOL_BINDING_ENTRY * *)
0x180058ecf  mov     ebx, eax
0x180058ed1  test    eax, eax
0x180058ed3  js      loc_18005918B
0x180058ed9  mov     rbx, [rbp+57h+var_90]
0x180058edd  lea     rcx, [rsi+78h]
0x180058ee1  mov     rdx, [rbx+40h]
0x180058ee5  call    cs:__imp_?FastAppend@MULTISZ@@QEAAHPEBG@Z; MULTISZ::FastAppend(ushort const *)
0x180058eeb  test    eax, eax
0x180058eed  jz      loc_180059186
0x180058ef3  cmp     [rsp+120h+var_F0], r14w
0x180058ef9  jnz     short loc_180058F5D
0x180058efb  cmp     [rbx+58h], r12d
0x180058eff  jz      short loc_180058F57
0x180058f01  mov     dword ptr [rsi+5Ch], 4
0x180058f08  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180058f0c  xorps   xmm0, xmm0
0x180058f0f  mov     r8d, 0Ah; Radix
0x180058f15  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x180058f19  mov     ecx, [rsi+58h]; Value
0x180058f1c  call    cs:__imp__ultow
0x180058f22  mov     rax, [rbx+40h]
0x180058f26  lea     r9, [rbp+57h+var_A8]; unsigned __int16 **
0x180058f2a  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x180058f31  mov     r8d, 2; unsigned __int16
0x180058f37  mov     [rbp+57h+var_A8], rax
0x180058f3b  mov     edx, 0C00003EFh; unsigned int
0x180058f40  lea     rax, [rbp+57h+Buffer]
0x180058f44  mov     dword ptr [rsp+120h+var_100], 800700B7h; unsigned int
0x180058f4c  mov     [rbp+57h+var_A8+8], rax
0x180058f50  call    ?LogW3svcEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogW3svcEvent(ulong,ushort,ushort const * * const,ulong)
0x180058f55  jmp     short loc_180058F5D
0x180058f57  mov     eax, [rsi+58h]
0x180058f5a  mov     [rbx+58h], eax
0x180058f5d  mov     rdx, [rsp+120h+var_E8]
0x180058f62  lea     rcx, [rbp+57h+var_88]
0x180058f66  mov     rdi, [rbp+57h+var_D0]
0x180058f6a  xor     eax, eax
0x180058f6c  mov     [rbp+57h+bstrString], rax
0x180058f70  mov     [rbp+57h+var_48], eax
0x180058f73  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180058f79  mov     ebx, eax
0x180058f7b  test    eax, eax
0x180058f7d  js      loc_180059027
0x180058f83  lea     rdx, asc_18007D628; "://*:"
0x180058f8a  lea     rcx, [rbp+57h+var_88]
0x180058f8e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180058f94  mov     ebx, eax
0x180058f96  test    eax, eax
0x180058f98  js      loc_180059027
0x180058f9e  mov     r9, r12
0x180058fa1  mov     eax, r12d
0x180058fa4  mov     rcx, r14
0x180058fa7  inc     rcx
0x180058faa  cmp     [rdi+rcx*2], r12w
0x180058faf  jnz     short loc_180058FA7
0x180058fb1  lea     r8, [rdi+rcx*2]
0x180058fb5  cmp     r8, rdi
0x180058fb8  jz      short loc_180058FD9
0x180058fba  cmp     word ptr [r8], 3Ah ; ':'
0x180058fbf  jnz     short loc_180058FCB
0x180058fc1  inc     eax
0x180058fc3  cmp     eax, 2
0x180058fc6  jz      short loc_180058FD4
0x180058fc8  mov     r9, r8
0x180058fcb  sub     r8, 2
0x180058fcf  cmp     r8, rdi
0x180058fd2  jnz     short loc_180058FBA
0x180058fd4  cmp     r8, rdi
0x180058fd7  jnz     short loc_180058FE2
0x180058fd9  cmp     word ptr [r8], 3Ah ; ':'
0x180058fde  jnz     short loc_180058FE2
0x180058fe0  inc     eax
0x180058fe2  cmp     eax, 2
0x180058fe5  jnz     loc_18005916A
0x180058feb  add     r8, 2; Source
0x180058fef  lea     edx, [rax+4]; SizeInWords
0x180058ff2  sub     r9, r8
0x180058ff5  lea     rcx, [rbp+57h+bstrString]; Destination
0x180058ff9  sar     r9, 1; MaxCount
0x180058ffc  call    cs:__imp_wcsncpy_s
0x180059002  lea     rdx, [rbp+57h+bstrString]
0x180059006  lea     rcx, [rbp+57h+var_88]
0x18005900a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180059010  mov     ebx, eax
0x180059012  test    eax, eax
  ... truncated ...
```
