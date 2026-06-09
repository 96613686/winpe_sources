# CONFIG_ELEMENT::CommitChanges(CONFIG_FILE *)

- ea: `0x18002eb10`
- end: `0x18002f36c`
- name: `?CommitChanges@CONFIG_ELEMENT@@QEAAJPEAVCONFIG_FILE@@@Z`
- size: `2140`
- prototype: `__int64 __fastcall(CONFIG_ELEMENT *__hidden this, struct CONFIG_FILE *)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024780`
- `0x18002eb10`

## callees

- `0x18000bc88`
- `0x18000c4fc`
- `0x18000c7e4`
- `0x18000d964`
- `0x180016440`
- `0x180016520`
- `0x18001b004`
- `0x18001d518`
- `0x18001d530`
- `0x180025fac`
- `0x180026c3c`
- `0x180027e44`
- `0x180029e60`
- `0x18002eb10`
- `0x180032770`
- `0x180033bc0`
- `0x18003d15c`
- `0x18003d660`
- `0x18003eac0`
- `0x180047964`
- `0x180047b0c`
- `0x18004a9c0`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18002f326`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002f330`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002f33a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002f326`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002f330`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002f33a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ecbe`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002eed0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002efb3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ecbe`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002eed0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002efb3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002eb6c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002eb91`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002ebc1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002eb6c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002eb91`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002ebc1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002ef1f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002ef1f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002ef3e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002ef59`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002ef8c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002ef3e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002ef59`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002ef8c`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002eedd`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002eedd`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18002eded`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18002eded`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18002ef71`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18002ef71`

## string_xrefs

- `0x18002ecd0`: `CONFIG_ELEMENT::CommitChanges`
- `0x18002f043`: `configSource`

## pseudocode

```c
__int64 __fastcall CONFIG_ELEMENT::CommitChanges(CONFIG_ELEMENT *this, struct CONFIG_FILE *a2)
{
  struct CONFIG_FILE *v2; // r13
  unsigned int v4; // edi
  PROVIDER_ENTRY *v5; // r15
  int v6; // ebx
  int v7; // ecx
  _QWORD *v8; // rax
  __int64 v9; // rcx
  struct IConfigDomNode **v10; // rdi
  struct LOCATION_CONTEXT *v11; // rsi
  int v12; // ebx
  const unsigned __int16 *Str; // rax
  struct IConfigDomNode **v14; // r12
  struct IConfigDomNode *v15; // r12
  unsigned __int16 i; // si
  struct SCHEMA_ATTRIBUTE *Attribute; // r13
  SCHEMA_ATTRIBUTE *v18; // rax
  volatile signed __int32 *ProviderEntry; // rax
  ATTRIBUTE_VALUE *v20; // rcx
  const unsigned __int16 *ProviderName; // rax
  ATTRIBUTE_VALUE *v22; // rcx
  int v23; // eax
  const unsigned __int16 *v24; // rbx
  const unsigned __int16 *v25; // rax
  const unsigned __int16 *v26; // rdx
  const unsigned __int16 *Name; // rax
  __int64 (__fastcall *v28)(struct IConfigDomNode *, const unsigned __int16 *, unsigned __int16 *); // rdi
  unsigned __int16 *v29; // rbx
  const unsigned __int16 *AttributeName; // rax
  int v31; // eax
  LOCKING_ATTRIBUTES **v32; // rax
  __int64 v33; // rax
  const wchar_t *v34; // rdx
  PROVIDER_ENTRY **v35; // rax
  PROVIDER_ENTRY *v36; // r12
  CONFIG_COLLECTION *v37; // rcx
  __int64 v38; // rdi
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rax
  BOOL v42; // r13d
  __int64 v43; // rax
  __int64 v44; // rdx
  CONFIG_ELEMENT *v45; // rsi
  __int64 v46; // rcx
  const WCHAR *v47; // rdx
  _WORD *v48; // rcx
  CONFIG_ELEMENT *v49; // rsi
  __int64 v50; // rcx
  const WCHAR *v51; // rdx
  PROVIDER_ENTRY *v54; // [rsp+58h] [rbp-A8h] BYREF
  int v55; // [rsp+60h] [rbp-A0h] BYREF
  struct IConfigDomNode *v56; // [rsp+68h] [rbp-98h]
  _QWORD v57[2]; // [rsp+70h] [rbp-90h] BYREF
  int v58; // [rsp+80h] [rbp-80h]
  __int64 v59; // [rsp+88h] [rbp-78h]
  __int128 v60; // [rsp+90h] [rbp-70h]
  __int128 v61; // [rsp+A0h] [rbp-60h]
  _BYTE v62[56]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v63[56]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v64[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v65[64]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v66[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v67[256]; // [rsp+260h] [rbp+160h] BYREF

  v2 = a2;
  memset_0(v65, 0, sizeof(v65));
  STRU::STRU((STRU *)v62, v65, 0x40u);
  memset_0(v66, 0, sizeof(v66));
  STRU::STRU((STRU *)v64, v66, 0x40u);
  v4 = 0;
  v5 = 0;
  memset_0(v67, 0, sizeof(v67));
  STRU::STRU((STRU *)v63, v67, 0x100u);
  v55 = 0;
  v57[0] = &PARSE_ERROR_INFO::`vftable';
  v60 = 0;
  v61 = 0;
  v57[1] = 1;
  v58 = 0;
  v59 = 0;
  if ( !v2 )
  {
    v6 = -2147024809;
    goto LABEL_115;
  }
  v7 = *((_DWORD *)this + 34);
  if ( (v7 & 0xF0000) != 0 )
  {
    v6 = -2147024846;
    goto LABEL_115;
  }
  v8 = (_QWORD *)*((_QWORD *)this + 14);
  v6 = 0;
  if ( (v7 & 0xF00000) == 0x200000 )
  {
    if ( v8 && *v8 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 40LL))(*v8);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 40LL))(*((_QWORD *)this + 7));
    goto LABEL_115;
  }
  v56 = 0;
  if ( !v8 )
    goto LABEL_20;
  v9 = *v8;
  if ( v8[1] )
  {
    if ( !v9 )
    {
      v6 = (***((__int64 (__fastcall ****)(_QWORD, _BYTE *, _QWORD))this + 7))(*((_QWORD *)this + 7), v64, 0);
      if ( v6 < 0 )
        goto LABEL_115;
      v10 = (struct IConfigDomNode **)*((_QWORD *)this + 14);
      v11 = (struct LOCATION_CONTEXT *)*((_QWORD *)this + 19);
      v12 = *((_WORD *)this + 18) & 1;
      Str = STRU::QueryStr((STRU *)v64);
      v6 = CONFIG_FILE::OpenConfigSourceDom(
             v2,
             L"CONFIG_ELEMENT::CommitChanges",
             *(const unsigned __int16 **)(*((_QWORD *)this + 14) + 8LL),
             Str,
             v11,
             (struct PARSE_ERROR_INFO *)v57,
             1,
             v12,
             v10,
             0);
      if ( v6 < 0 )
        goto LABEL_115;
      (*(void (__fastcall **)(_QWORD))(***((_QWORD ***)this + 14) + 104LL))(**((_QWORD **)this + 14));
      goto LABEL_18;
    }
  }
  else if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 40LL))(v9);
    (*(void (__fastcall **)(_QWORD))(***((_QWORD ***)this + 14) + 120LL))(**((_QWORD **)this + 14));
    **((_QWORD **)this + 14) = 0;
LABEL_18:
    v56 = (struct IConfigDomNode *)*((_QWORD *)this + 7);
    (*(void (__fastcall **)(struct IConfigDomNode *))(*(_QWORD *)v56 + 128LL))(v56);
    CONFIG_ELEMENT::SetDomNode(this, 0);
    v6 = CONFIG_ELEMENT::MarkNodesForRecreation(this);
    if ( v6 < 0 )
      goto LABEL_111;
    CONFIG_ELEMENT::SetDomNode(this, v56);
    v4 = 0;
  }
LABEL_20:
  if ( (*((_DWORD *)this + 34) & 0xF00000) != 0x100000 )
    goto LABEL_65;
  v14 = (struct IConfigDomNode **)*((_QWORD *)this + 14);
  if ( !v14 || (v15 = *v14) == 0 || (*((_BYTE *)this + 36) & 1) != 0 )
    v15 = (struct IConfigDomNode *)*((_QWORD *)this + 7);
  (*(void (__fastcall **)(struct IConfigDomNode *))(*(_QWORD *)v15 + 88LL))(v15);
  for ( i = 0; i < *((_WORD *)this + 19); ++i )
  {
    STRU::Reset((STRU *)v63);
    if ( (*(_BYTE *)(*((_QWORD *)this + 5) + 16LL * i + 8) & 4) == 0 )
      goto LABEL_53;
    Attribute = SCHEMA_ELEMENT::QueryAttribute(*((SCHEMA_ELEMENT **)this + 10), i);
    if ( SCHEMA_ATTRIBUTE::QueryExtension(Attribute) )
    {
      v2 = a2;
LABEL_53:
      v4 = 0;
      continue;
    }
    v18 = SCHEMA_ELEMENT::QueryAttribute(*((SCHEMA_ELEMENT **)this + 10), i);
    v6 = SCHEMA_ATTRIBUTE::CopyAttribute(
           v18,
           *(struct ATTRIBUTE_VALUE **)(*((_QWORD *)this + 5) + 16LL * i),
           (struct STRU *)v62);
    if ( v6 < 0 )
      goto LABEL_111;
    ProviderEntry = (volatile signed __int32 *)ATTRIBUTE_VALUE::QueryProviderEntry(*(ATTRIBUTE_VALUE **)(*((_QWORD *)this + 5) + 16LL * i));
    v54 = (PROVIDER_ENTRY *)ProviderEntry;
    v5 = (PROVIDER_ENTRY *)ProviderEntry;
    if ( ProviderEntry )
    {
      _InterlockedIncrement(ProviderEntry + 2);
    }
    else
    {
      ProviderName = ATTRIBUTE_VALUE::QueryProviderName(v20);
      if ( ProviderName )
      {
        if ( *ProviderName )
          goto LABEL_36;
      }
      else if ( (*((_BYTE *)Attribute + 20) & 8) != 0 )
      {
        v22 = (ATTRIBUTE_VALUE *)*((_QWORD *)Attribute + 4);
        if ( v22 )
          ProviderName = ATTRIBUTE_VALUE::QueryProviderName(v22);
LABEL_36:
        v2 = a2;
        v23 = CONFIG_FILE::GetProviderEntry(a2, ProviderName, &v54);
        v5 = v54;
        v6 = v23;
        if ( v23 < 0 )
          goto LABEL_111;
        goto LABEL_40;
      }
    }
    v2 = a2;
LABEL_40:
    if ( v5 )
    {
      v24 = STRU::QueryStr((STRU *)v62);
      v25 = STRU::QueryStr((struct CONFIG_FILE *)((char *)v2 + 72));
      v26 = &szDomain;
      if ( *((_QWORD *)v2 + 5) )
        v26 = (const unsigned __int16 *)*((_QWORD *)v2 + 5);
      v6 = PROVIDER_ENTRY::EncryptValue(v5, v26, v25, v24, (struct STRU *)v63);
      if ( v6 < 0 )
        goto LABEL_111;
      v6 = STRU::Copy((STRU *)v62, L"[enc:");
      if ( v6 < 0 )
        goto LABEL_111;
      Name = PROVIDER_ENTRY::QueryName(v5);
      v6 = STRU::Append((STRU *)v62, Name);
      if ( v6 < 0 )
        goto LABEL_111;
      v6 = STRU::Append((STRU *)v62, L":");
      if ( v6 < 0 )
        goto LABEL_111;
      v6 = STRU::Append((STRU *)v62, (const struct STRU *)v63);
      if ( v6 < 0 )
        goto LABEL_111;
      v6 = STRU::Append((STRU *)v62, L":enc]");
      if ( v6 < 0 )
        goto LABEL_111;
      PROVIDER_ENTRY::DereferenceProviderEntry(v5);
      v5 = 0;
    }
    v28 = *(__int64 (__fastcall **)(struct IConfigDomNode *, const unsigned __int16 *, unsigned __int16 *))(*(_QWORD *)v15 + 80LL);
    v29 = STRU::QueryStr((STRU *)v62);
    AttributeName = SCHEMA_ELEMENT::QueryAttributeName(*((SCHEMA_ELEMENT **)this + 10), i);
    v31 = v28(v15, AttributeName, v29);
    v4 = 0;
    v6 = v31;
    if ( v31 < 0 )
      goto LABEL_111;
  }
  v32 = (LOCKING_ATTRIBUTES **)*((_QWORD *)this + 13);
  if ( v32 )
  {
    if ( *v32 )
    {
      v6 = LOCKING_ATTRIBUTES::CommitChanges(*v32, v15);
      if ( v6 < 0 )
        goto LABEL_111;
    }
  }
  v33 = *((_QWORD *)this + 14);
  if ( v33 && *(_QWORD *)(v33 + 8) )
  {
    if ( (*((_BYTE *)this + 36) & 1) == 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 88LL))(*((_QWORD *)this + 7));
    v34 = L"childSource";
    if ( (*((_BYTE *)this + 36) & 1) == 0 )
      v34 = L"configSource";
    v6 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD))(**((_QWORD **)this + 7) + 80LL))(
           *((_QWORD *)this + 7),
           v34,
           *(_QWORD *)(*((_QWORD *)this + 14) + 8LL));
    if ( v6 < 0 )
      goto LABEL_111;
  }
LABEL_65:
  v35 = (PROVIDER_ENTRY **)*((_QWORD *)this + 14);
  if ( !v35 || (v36 = *v35, (v54 = v36) == 0) )
  {
    v36 = (PROVIDER_ENTRY *)*((_QWORD *)this + 7);
    v54 = v36;
  }
  if ( !*(_QWORD *)(*((_QWORD *)this + 10) + 176LL) )
  {
LABEL_99:
    while ( 1 )
    {
      v48 = *(_WORD **)(*((_QWORD *)this + 10) + 88LL);
      if ( !v48 || (unsigned __int16)v4 >= *v48 )
        break;
      v49 = *(CONFIG_ELEMENT **)(*((_QWORD *)this + 9) + 8LL * (unsigned __int16)v4);
      if ( (unsigned int)CONFIG_ELEMENT::QueryHasElementChanged(v49) )
      {
        if ( !*((_QWORD *)v49 + 7) )
        {
          v50 = *((_QWORD *)v49 + 10);
          v51 = &szDomain;
          if ( *(_QWORD *)(v50 + 24) )
            v51 = *(const WCHAR **)(v50 + 24);
          v6 = (*(__int64 (__fastcall **)(PROVIDER_ENTRY *, const WCHAR *, _QWORD *, __int64, int))(*(_QWORD *)v36 + 72LL))(
                 v36,
                 v51,
                 (_QWORD *)v49 + 7,
                 0xFFFFFFFFLL,
                 1);
          if ( v6 < 0 )
            goto LABEL_111;
        }
        v6 = CONFIG_ELEMENT::CommitChanges(v49, v2);
        if ( v6 < 0 )
          goto LABEL_111;
      }
      LOWORD(v4) = v4 + 1;
    }
    if ( (unsigned int)CONFIG_ELEMENT::QueryIsEmptyElementWithVisibilityOf(this, 0)
      && !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 152LL))(*((_QWORD *)this + 7)) )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 40LL))(*((_QWORD *)this + 7));
    }
    goto LABEL_111;
  }
  v37 = (CONFIG_COLLECTION *)*((_QWORD *)this + 11);
  if ( *((_DWORD *)v37 + 36)
    || *((_DWORD *)v37 + 44)
    || !(unsigned int)CONFIG_COLLECTION::QueryHasCollectionChanged(v37) )
  {
LABEL_79:
    v6 = CONFIG_COLLECTION::CheckDuplicateValidation(*((CONFIG_COLLECTION **)this + 11), &v55);
    if ( v6 >= 0 )
    {
      if ( v55 )
      {
        v39 = *((_QWORD *)this + 11);
        if ( *(_DWORD *)(v39 + 176) )
        {
          do
          {
            v40 = *(_QWORD *)(*(_QWORD *)(v39 + 168) + 8LL * v4);
            v41 = v40 + 48;
            if ( !v40 )
              v41 = 56;
            if ( *(_QWORD *)v41 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 40LL))(*(_QWORD *)v41);
            v39 = *((_QWORD *)this + 11);
            ++v4;
          }
          while ( v4 < *(_DWORD *)(v39 + 176) );
          v36 = v54;
          v4 = 0;
        }
        v42 = *(_DWORD *)(v39 + 176) != 0;
        while ( 1 )
        {
          v43 = *((_QWORD *)this + 11);
          if ( v4 >= *(_DWORD *)(v43 + 144) )
          {
            v2 = a2;
            LOWORD(v4) = 0;
            goto LABEL_99;
          }
          v44 = *(_QWORD *)(*(_QWORD *)(v43 + 136) + 8LL * v4);
          v45 = (CONFIG_ELEMENT *)((v44 - 8) & -(__int64)(v44 != 0));
          if ( (unsigned int)CONFIG_ELEMENT::QueryHasElementChanged(v45) )
          {
            if ( !*((_QWORD *)v45 + 7) )
            {
              v46 = *((_QWORD *)v45 + 10);
              v47 = &szDomain;
              if ( *(_QWORD *)(v46 + 24) )
                v47 = *(const WCHAR **)(v46 + 24);
              v6 = (*(__int64 (__fastcall **)(PROVIDER_ENTRY *, const WCHAR *, _QWORD *, _QWORD, BOOL))(*(_QWORD *)v36 + 72LL))(
                     v36,
                     v47,
                     (_QWORD *)v45 + 7,
                     v4,
                     v42);
              if ( v6 < 0 )
                break;
            }
            v6 = CONFIG_ELEMENT::CommitChanges(v45, a2);
            if ( v6 < 0 )
              break;
          }
          ++v4;
        }
      }
      else
      {
        v6 = -2147024713;
      }
    }
    goto LABEL_111;
  }
  v38 = *((_QWORD *)this + 11);
  if ( (*(_BYTE *)(v38 + 200) & 1) == 0 )
  {
    v4 = 0;
    goto LABEL_79;
  }
  if ( *(_DWORD *)(v38 + 144) )
  {
    v6 = -2147024883;
    goto LABEL_111;
  }
  v6 = CONFIG_COLLECTION::CopyInheritedElements(*((CONFIG_COLLECTION **)this + 11), 0, 0);
  if ( v6 >= 0 )
  {
    v6 = CONFIG_COLLECTION::CalculateEffectiveCollection((CONFIG_COLLECTION *)v38, 0);
    v4 = 0;
    if ( v6 >= 0 )
      goto LABEL_79;
  }
LABEL_111:
  if ( v56 )
    (*(void (__fastcall **)(struct IConfigDomNode *))(*(_QWORD *)v56 + 120LL))(v56);
  if ( v5 )
    PROVIDER_ENTRY::DereferenceProviderEntry(v5);
LABEL_115:
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((PARSE_ERROR_INFO *)v57);
  STRU::~STRU((STRU *)v63);
  STRU::~STRU((STRU *)v64);
  STRU::~STRU((STRU *)v62);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002eb10  mov     [rsp-8+arg_10], rbx
0x18002eb15  push    rbp
0x18002eb16  push    rsi
0x18002eb17  push    rdi
0x18002eb18  push    r12
0x18002eb1a  push    r13
0x18002eb1c  push    r14
0x18002eb1e  push    r15
0x18002eb20  lea     rbp, [rsp-370h]
0x18002eb28  sub     rsp, 470h
0x18002eb2f  mov     rax, cs:__security_cookie
0x18002eb36  xor     rax, rsp
0x18002eb39  mov     [rbp+3A0h+var_40], rax
0x18002eb40  mov     r13, rdx
0x18002eb43  mov     [rsp+4A0h+var_450], rdx
0x18002eb48  mov     r14, rcx
0x18002eb4b  mov     edi, 80h
0x18002eb50  mov     r8d, edi; Size
0x18002eb53  lea     rcx, [rbp+3A0h+var_340]; void *
0x18002eb57  xor     edx, edx; Val
0x18002eb59  call    memset_0
0x18002eb5e  lea     ebx, [rdi-40h]
0x18002eb61  mov     r8d, ebx
0x18002eb64  lea     rdx, [rbp+3A0h+var_340]
0x18002eb68  lea     rcx, [rbp+3A0h+var_3F0]
0x18002eb6c  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002eb72  mov     r8d, edi; Size
0x18002eb75  lea     rcx, [rbp+3A0h+var_2C0]; void *
0x18002eb7c  xor     edx, edx; Val
0x18002eb7e  call    memset_0
0x18002eb83  mov     r8d, ebx
0x18002eb86  lea     rdx, [rbp+3A0h+var_2C0]
0x18002eb8d  lea     rcx, [rbp+3A0h+var_380]
0x18002eb91  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002eb97  xor     edi, edi
0x18002eb99  lea     rcx, [rbp+3A0h+var_240]; void *
0x18002eba0  xor     edx, edx; Val
0x18002eba2  mov     r8d, 200h; Size
0x18002eba8  mov     r15d, edi
0x18002ebab  call    memset_0
0x18002ebb0  mov     r8d, 100h
0x18002ebb6  lea     rdx, [rbp+3A0h+var_240]
0x18002ebbd  lea     rcx, [rbp+3A0h+var_3B8]
0x18002ebc1  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002ebc7  mov     [rsp+4A0h+var_440], edi
0x18002ebcb  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x18002ebd2  mov     [rsp+4A0h+var_430], rax
0x18002ebd7  xorps   xmm0, xmm0
0x18002ebda  movdqa  [rbp+3A0h+var_410], xmm0
0x18002ebdf  xorps   xmm1, xmm1
0x18002ebe2  movdqa  [rbp+3A0h+var_400], xmm1
0x18002ebe7  lea     esi, [rbx-3Fh]
0x18002ebea  mov     [rsp+4A0h+var_428], rsi
0x18002ebef  mov     [rbp+3A0h+var_420], edi
0x18002ebf2  mov     [rbp+3A0h+var_418], rdi
0x18002ebf6  test    r13, r13
0x18002ebf9  jnz     short loc_18002EC05
0x18002ebfb  mov     ebx, 80070057h
0x18002ec00  jmp     loc_18002F318
0x18002ec05  mov     ecx, [r14+88h]
0x18002ec0c  test    ecx, 0F0000h
0x18002ec12  jz      short loc_18002EC1E
0x18002ec14  mov     ebx, 80070032h
0x18002ec19  jmp     loc_18002F318
0x18002ec1e  mov     rax, [r14+70h]
0x18002ec22  and     ecx, 0F00000h
0x18002ec28  mov     ebx, edi
0x18002ec2a  cmp     ecx, 200000h
0x18002ec30  jnz     short loc_18002EC60
0x18002ec32  test    rax, rax
0x18002ec35  jz      short loc_18002EC4B
0x18002ec37  mov     rcx, [rax]
0x18002ec3a  test    rcx, rcx
0x18002ec3d  jz      short loc_18002EC4B
0x18002ec3f  mov     rax, [rcx]
0x18002ec42  mov     rax, [rax+28h]
0x18002ec46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec4b  mov     rcx, [r14+38h]
0x18002ec4f  mov     rax, [rcx]
0x18002ec52  mov     rax, [rax+28h]
0x18002ec56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec5b  jmp     loc_18002F318
0x18002ec60  mov     [rsp+4A0h+var_438], rdi
0x18002ec65  test    rax, rax
0x18002ec68  jz      loc_18002ED99
0x18002ec6e  mov     rcx, [rax]
0x18002ec71  cmp     [rax+8], rdi
0x18002ec75  jz      loc_18002ED2A
0x18002ec7b  test    rcx, rcx
0x18002ec7e  jnz     loc_18002ED99
0x18002ec84  mov     rcx, [r14+38h]
0x18002ec88  lea     rdx, [rbp+3A0h+var_380]
0x18002ec8c  xor     r8d, r8d
0x18002ec8f  mov     rax, [rcx]
0x18002ec92  mov     rax, [rax]
0x18002ec95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec9a  mov     ebx, eax
0x18002ec9c  test    eax, eax
0x18002ec9e  js      loc_18002F318
0x18002eca4  movzx   eax, word ptr [r14+24h]
0x18002eca9  lea     rcx, [rbp+3A0h+var_380]
0x18002ecad  mov     rdi, [r14+70h]
0x18002ecb1  and     ax, si
0x18002ecb4  mov     rsi, [r14+98h]
0x18002ecbb  movzx   ebx, ax
0x18002ecbe  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002ecc4  mov     r8, [r14+70h]
0x18002ecc8  lea     rcx, [rsp+4A0h+var_430]
0x18002eccd  xor     r12d, r12d
0x18002ecd0  lea     rdx, aConfigElementC; "CONFIG_ELEMENT::CommitChanges"
0x18002ecd7  mov     [rsp+4A0h+var_458], r12; struct CONFIG_SOURCE_ENTRY **
0x18002ecdc  mov     r9, rax; unsigned __int16 *
0x18002ecdf  mov     [rsp+4A0h+var_460], rdi; struct IConfigDomNode **
0x18002ece4  mov     r8, [r8+8]; unsigned __int16 *
0x18002ece8  mov     [rsp+4A0h+var_468], ebx; int
0x18002ecec  mov     [rsp+4A0h+var_470], 1; int
0x18002ecf4  mov     [rsp+4A0h+var_478], rcx; struct PARSE_ERROR_INFO *
0x18002ecf9  mov     rcx, r13; this
0x18002ecfc  mov     [rsp+4A0h+var_480], rsi; struct LOCATION_CONTEXT *
0x18002ed01  call    ?OpenConfigSourceDom@CONFIG_FILE@@QEAAJPEBG00PEAVLOCATION_CONTEXT@@PEAVPARSE_ERROR_INFO@@HHPEAPEAVIConfigDomNode@@PEAPEAVCONFIG_SOURCE_ENTRY@@@Z; CONFIG_FILE::OpenConfigSourceDom(ushort const *,ushort const *,ushort const *,LOCATION_CONTEXT *,PARSE_ERROR_INFO *,int,int,IConfigDomNode * *,CONFIG_SOURCE_ENTRY * *)
0x18002ed06  mov     ebx, eax
0x18002ed08  test    eax, eax
0x18002ed0a  js      loc_18002F318
0x18002ed10  mov     rax, [r14+70h]
0x18002ed14  mov     rcx, [rax]
0x18002ed17  mov     rax, [rcx]
0x18002ed1a  mov     rax, [rax+68h]
0x18002ed1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed23  lea     esi, [r12+1]
0x18002ed28  jmp     short loc_18002ED55
0x18002ed2a  test    rcx, rcx
0x18002ed2d  jz      short loc_18002ED99
0x18002ed2f  mov     rax, [rcx]
0x18002ed32  mov     rax, [rax+28h]
0x18002ed36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed3b  mov     rax, [r14+70h]
0x18002ed3f  mov     rcx, [rax]
0x18002ed42  mov     rax, [rcx]
0x18002ed45  mov     rax, [rax+78h]
0x18002ed49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed4e  mov     rax, [r14+70h]
0x18002ed52  mov     [rax], rdi
0x18002ed55  mov     rdi, [r14+38h]
0x18002ed59  mov     rcx, rdi
0x18002ed5c  mov     [rsp+4A0h+var_438], rdi
0x18002ed61  mov     rax, [rdi]
0x18002ed64  mov     rax, [rax+80h]
0x18002ed6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed70  xor     edx, edx; struct IConfigDomNode *
0x18002ed72  mov     rcx, r14; this
0x18002ed75  call    ?SetDomNode@CONFIG_ELEMENT@@QEAAXPEAVIConfigDomNode@@@Z; CONFIG_ELEMENT::SetDomNode(IConfigDomNode *)
0x18002ed7a  mov     rcx, r14; this
0x18002ed7d  call    ?MarkNodesForRecreation@CONFIG_ELEMENT@@AEAAJXZ; CONFIG_ELEMENT::MarkNodesForRecreation(void)
0x18002ed82  mov     ebx, eax
0x18002ed84  test    eax, eax
0x18002ed86  js      loc_18002F2F5
0x18002ed8c  mov     rdx, rdi; struct IConfigDomNode *
0x18002ed8f  mov     rcx, r14; this
0x18002ed92  call    ?SetDomNode@CONFIG_ELEMENT@@QEAAXPEAVIConfigDomNode@@@Z; CONFIG_ELEMENT::SetDomNode(IConfigDomNode *)
0x18002ed97  xor     edi, edi
0x18002ed99  mov     eax, [r14+88h]
0x18002eda0  and     eax, 0F00000h
0x18002eda5  cmp     eax, 100000h
0x18002edaa  jnz     loc_18002F078
0x18002edb0  mov     r12, [r14+70h]
0x18002edb4  test    r12, r12
0x18002edb7  jz      short loc_18002EDC8
0x18002edb9  mov     r12, [r12]
0x18002edbd  test    r12, r12
0x18002edc0  jz      short loc_18002EDC8
0x18002edc2  test    [r14+24h], sil
0x18002edc6  jz      short loc_18002EDCC
0x18002edc8  mov     r12, [r14+38h]
0x18002edcc  mov     rax, [r12]
0x18002edd0  mov     rcx, r12
0x18002edd3  mov     rax, [rax+58h]
0x18002edd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eddc  mov     esi, edi
0x18002edde  cmp     si, [r14+26h]
0x18002ede3  jnb     loc_18002EFF6
0x18002ede9  lea     rcx, [rbp+3A0h+var_3B8]
0x18002eded  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18002edf3  mov     rax, [r14+28h]
0x18002edf7  movzx   edi, si
0x18002edfa  add     rdi, rdi
0x18002edfd  test    byte ptr [rax+rdi*8+8], 4
0x18002ee02  jz      loc_18002EFEC
0x18002ee08  mov     rcx, [r14+50h]; this
0x18002ee0c  movzx   edx, si; unsigned __int16
0x18002ee0f  call    ?QueryAttribute@SCHEMA_ELEMENT@@QEAAPEAVSCHEMA_ATTRIBUTE@@G@Z; SCHEMA_ELEMENT::QueryAttribute(ushort)
0x18002ee14  mov     rcx, rax; this
0x18002ee17  mov     r13, rax
0x18002ee1a  call    ?QueryExtension@SCHEMA_ATTRIBUTE@@QEBAPEBGXZ; SCHEMA_ATTRIBUTE::QueryExtension(void)
0x18002ee1f  test    rax, rax
0x18002ee22  jnz     loc_18002EFE7
0x18002ee28  mov     rcx, [r14+50h]; this
0x18002ee2c  movzx   edx, si; unsigned __int16
0x18002ee2f  call    ?QueryAttribute@SCHEMA_ELEMENT@@QEAAPEAVSCHEMA_ATTRIBUTE@@G@Z; SCHEMA_ELEMENT::QueryAttribute(ushort)
0x18002ee34  mov     rdx, [r14+28h]
0x18002ee38  lea     r8, [rbp+3A0h+var_3F0]; struct STRU *
0x18002ee3c  mov     rcx, rax; this
0x18002ee3f  mov     rdx, [rdx+rdi*8]; struct ATTRIBUTE_VALUE *
0x18002ee43  call    ?CopyAttribute@SCHEMA_ATTRIBUTE@@QEAAJPEAVATTRIBUTE_VALUE@@PEAVSTRU@@@Z; SCHEMA_ATTRIBUTE::CopyAttribute(ATTRIBUTE_VALUE *,STRU *)
0x18002ee48  mov     ebx, eax
0x18002ee4a  test    eax, eax
0x18002ee4c  js      loc_18002F2F5
0x18002ee52  mov     rax, [r14+28h]
0x18002ee56  mov     rcx, [rax+rdi*8]; this
0x18002ee5a  call    ?QueryProviderEntry@ATTRIBUTE_VALUE@@QEBAPEAVPROVIDER_ENTRY@@XZ; ATTRIBUTE_VALUE::QueryProviderEntry(void)
0x18002ee5f  xor     edi, edi
0x18002ee61  mov     [rsp+4A0h+var_448], rax
0x18002ee66  mov     r15, rax
0x18002ee69  test    rax, rax
0x18002ee6c  jnz     short loc_18002EEBA
0x18002ee6e  call    ?QueryProviderName@ATTRIBUTE_VALUE@@QEBAPEBGXZ; ATTRIBUTE_VALUE::QueryProviderName(void)
0x18002ee73  test    rax, rax
0x18002ee76  jnz     short loc_18002EE8F
0x18002ee78  test    byte ptr [r13+14h], 8
0x18002ee7d  jz      short loc_18002EEBE
0x18002ee7f  mov     rcx, [r13+20h]; this
0x18002ee83  test    rcx, rcx
0x18002ee86  jz      short loc_18002EE94
0x18002ee88  call    ?QueryProviderName@ATTRIBUTE_VALUE@@QEBAPEBGXZ; ATTRIBUTE_VALUE::QueryProviderName(void)
0x18002ee8d  jmp     short loc_18002EE94
0x18002ee8f  cmp     [rax], di
0x18002ee92  jz      short loc_18002EEBE
0x18002ee94  mov     r13, [rsp+4A0h+var_450]
0x18002ee99  lea     r8, [rsp+4A0h+var_448]; struct PROVIDER_ENTRY **
0x18002ee9e  mov     rcx, r13; this
0x18002eea1  mov     rdx, rax; unsigned __int16 *
0x18002eea4  call    ?GetProviderEntry@CONFIG_FILE@@QEAAJPEBGPEAPEAVPROVIDER_ENTRY@@@Z; CONFIG_FILE::GetProviderEntry(ushort const *,PROVIDER_ENTRY * *)
0x18002eea9  mov     r15, [rsp+4A0h+var_448]
0x18002eeae  mov     ebx, eax
0x18002eeb0  test    eax, eax
0x18002eeb2  js      loc_18002F2F5
0x18002eeb8  jmp     short loc_18002EEC3
0x18002eeba  lock inc dword ptr [rax+8]
0x18002eebe  mov     r13, [rsp+4A0h+var_450]
0x18002eec3  test    r15, r15
0x18002eec6  jz      loc_18002EFA7
0x18002eecc  lea     rcx, [rbp+3A0h+var_3F0]
0x18002eed0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002eed6  lea     rcx, [r13+48h]
0x18002eeda  mov     rbx, rax
0x18002eedd  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18002eee3  cmp     [r13+28h], rdi
0x18002eee7  lea     rcx, [rbp+3A0h+var_3B8]
0x18002eeeb  mov     [rsp+4A0h+var_480], rcx; struct STRU *
0x18002eef0  lea     rdx, szDomain
0x18002eef7  cmovnz  rdx, [r13+28h]; unsigned __int16 *
0x18002eefc  mov     rcx, r15; this
0x18002eeff  mov     r9, rbx; unsigned __int16 *
0x18002ef02  mov     r8, rax; unsigned __int16 *
0x18002ef05  call    ?EncryptValue@PROVIDER_ENTRY@@QEAAJPEBG00PEAVSTRU@@@Z; PROVIDER_ENTRY::EncryptValue(ushort const *,ushort const *,ushort const *,STRU *)
0x18002ef0a  mov     ebx, eax
0x18002ef0c  test    eax, eax
0x18002ef0e  js      loc_18002F2F5
0x18002ef14  lea     rdx, aEnc; "[enc:"
0x18002ef1b  lea     rcx, [rbp+3A0h+var_3F0]
0x18002ef1f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002ef25  mov     ebx, eax
0x18002ef27  test    eax, eax
0x18002ef29  js      loc_18002F2F5
0x18002ef2f  mov     rcx, r15; this
0x18002ef32  call    ?QueryName@PROVIDER_ENTRY@@QEAAPEBGXZ; PROVIDER_ENTRY::QueryName(void)
0x18002ef37  mov     rdx, rax
0x18002ef3a  lea     rcx, [rbp+3A0h+var_3F0]
0x18002ef3e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002ef44  mov     ebx, eax
0x18002ef46  test    eax, eax
0x18002ef48  js      loc_18002F2F5
0x18002ef4e  lea     rdx, asc_180060FAC; ":"
0x18002ef55  lea     rcx, [rbp+3A0h+var_3F0]
0x18002ef59  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002ef5f  mov     ebx, eax
0x18002ef61  test    eax, eax
0x18002ef63  js      loc_18002F2F5
0x18002ef69  lea     rdx, [rbp+3A0h+var_3B8]
0x18002ef6d  lea     rcx, [rbp+3A0h+var_3F0]
0x18002ef71  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x18002ef77  mov     ebx, eax
0x18002ef79  test    eax, eax
0x18002ef7b  js      loc_18002F2F5
0x18002ef81  lea     rdx, aEnc_0; ":enc]"
0x18002ef88  lea     rcx, [rbp+3A0h+var_3F0]
0x18002ef8c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002ef92  mov     ebx, eax
0x18002ef94  test    eax, eax
0x18002ef96  js      loc_18002F2F5
0x18002ef9c  mov     rcx, r15; this
0x18002ef9f  call    ?DereferenceProviderEntry@PROVIDER_ENTRY@@QEAAXXZ; PROVIDER_ENTRY::DereferenceProviderEntry(void)
0x18002efa4  mov     r15, rdi
0x18002efa7  mov     rax, [r12]
0x18002efab  lea     rcx, [rbp+3A0h+var_3F0]
0x18002efaf  mov     rdi, [rax+50h]
0x18002efb3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002efb9  mov     rcx, [r14+50h]; this
0x18002efbd  movzx   edx, si; unsigned __int16
0x18002efc0  mov     rbx, rax
0x18002efc3  call    ?QueryAttributeName@SCHEMA_ELEMENT@@QEAAPEBGG@Z; SCHEMA_ELEMENT::QueryAttributeName(ushort)
  ... truncated ...
```
