# CONFIG_ELEMENT::CheckLockAttributes(CONFIG_EXCEPTION * *)

- ea: `0x18002e0c8`
- end: `0x18002eada`
- name: `?CheckLockAttributes@CONFIG_ELEMENT@@AEAAJPEAPEAVCONFIG_EXCEPTION@@@Z`
- size: `2578`
- prototype: `__int64 __fastcall(CONFIG_ELEMENT *__hidden this, struct CONFIG_EXCEPTION **)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014098`
- `0x18002f8a0`
- `0x18003424c`

## callees

- `0x18000c7e4`
- `0x180016520`
- `0x18001c250`
- `0x18001e678`
- `0x18001fda0`
- `0x18002d998`
- `0x18002e0c8`
- `0x18002fbf4`
- `0x180033228`
- `0x180037730`
- `0x18004ab70`
- `0x180059c30`

## import_xrefs

- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x18002e2d1`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x18002e4cf`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x18002e6b3`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x18002ea2a`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x18002e2d1`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x18002e4cf`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x18002e6b3`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x18002ea2a`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18002e101`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18002e101`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18002eaab`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18002eaab`
- `iisutil!SplitCommaDelimitedString` at `0x18002e252`
- `iisutil!SplitCommaDelimitedString` at `0x18002e458`
- `iisutil!SplitCommaDelimitedString` at `0x18002e615`
- `iisutil!SplitCommaDelimitedString` at `0x18002e8ed`
- `iisutil!SplitCommaDelimitedString` at `0x18002e252`
- `iisutil!SplitCommaDelimitedString` at `0x18002e458`
- `iisutil!SplitCommaDelimitedString` at `0x18002e615`
- `iisutil!SplitCommaDelimitedString` at `0x18002e8ed`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002e266`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002e47c`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002e629`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002e901`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002e266`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002e47c`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002e629`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002e901`

## pseudocode

```c
__int64 __fastcall CONFIG_ELEMENT::CheckLockAttributes(CONFIG_ELEMENT *this, struct CONFIG_EXCEPTION **a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rax
  unsigned int i; // r8d
  __int64 v7; // rdx
  unsigned int j; // r8d
  _WORD *v9; // rcx
  unsigned __int16 v10; // ax
  __int64 v11; // rdx
  __int64 v12; // rsi
  int LockingAttributeValue; // ebx
  unsigned __int16 *v14; // r14
  unsigned int v15; // esi
  LOCKING_BEHAVIOR *v16; // rax
  unsigned __int64 v17; // rdx
  void *(*v18)(void *); // r9
  LOCKING_BEHAVIOR *v19; // rbx
  const unsigned __int16 *k; // rax
  const unsigned __int16 *v21; // rbx
  int v22; // edx
  unsigned __int16 v23; // si
  const unsigned __int16 *AttributeName; // rax
  const unsigned __int16 *v25; // rcx
  signed __int64 v26; // rax
  int v27; // edx
  int v28; // r8d
  CONFIG_EXCEPTION *v29; // rax
  CONFIG_EXCEPTION *v30; // rax
  struct CONFIG_EXCEPTION *v31; // rdi
  unsigned int v32; // edx
  CONFIG_EXCEPTION *v33; // rax
  __int64 v34; // rsi
  unsigned __int16 *v35; // r14
  unsigned int v36; // esi
  LOCKING_BEHAVIOR *v37; // rax
  unsigned __int64 v38; // rdx
  void *(*v39)(void *); // r9
  LOCKING_BEHAVIOR *v40; // rbx
  int v41; // r14d
  unsigned __int16 v42; // bx
  const unsigned __int16 *m; // rax
  const unsigned __int16 *v44; // rsi
  struct SCHEMA_ATTRIBUTE *Attribute; // rax
  const unsigned __int16 *v46; // rax
  const unsigned __int16 *v47; // rcx
  signed __int64 v48; // rax
  int v49; // edx
  int v50; // r8d
  struct SCHEMA_ATTRIBUTE *v51; // rax
  char *v52; // r15
  CONFIG_EXCEPTION *v53; // rax
  __int64 v54; // rsi
  unsigned __int16 *v55; // r14
  _WORD *v56; // rcx
  unsigned __int16 v57; // ax
  unsigned int v58; // esi
  LOCKING_BEHAVIOR *v59; // rax
  unsigned __int64 v60; // rdx
  void *(*v61)(void *); // r9
  LOCKING_BEHAVIOR *v62; // rbx
  const unsigned __int16 *n; // rax
  const unsigned __int16 *v64; // rbx
  int v65; // edx
  unsigned __int16 jj; // dx
  __int64 v67; // rax
  unsigned __int16 *v68; // rcx
  __int64 v69; // rcx
  unsigned __int16 ii; // si
  __int64 v71; // rax
  unsigned __int16 *v72; // rcx
  const unsigned __int16 *ChildElementName; // rax
  const unsigned __int16 *v74; // rcx
  signed __int64 v75; // rax
  int v76; // edx
  int v77; // r8d
  __int64 v78; // rsi
  __int64 v79; // rax
  const WCHAR *v80; // r8
  const unsigned __int16 *v81; // rax
  signed __int64 v82; // r8
  int v83; // edx
  int v84; // ecx
  __int64 v85; // rax
  const WCHAR *v86; // rcx
  const unsigned __int16 *v87; // rax
  signed __int64 v88; // rcx
  int v89; // r8d
  int v90; // edx
  CONFIG_EXCEPTION *v91; // rax
  __int64 v92; // rsi
  unsigned __int16 *v93; // r14
  _WORD *v94; // rcx
  unsigned __int16 v95; // ax
  unsigned int v96; // esi
  LOCKING_BEHAVIOR *v97; // rax
  unsigned __int64 v98; // rdx
  void *(*v99)(void *); // r9
  LOCKING_BEHAVIOR *v100; // rbx
  unsigned __int16 kk; // dx
  unsigned __int16 *v102; // rcx
  __int64 v103; // rcx
  __int64 v104; // rax
  const unsigned __int16 *v105; // rax
  const unsigned __int16 *v106; // rbx
  unsigned __int16 mm; // si
  __int64 v108; // rax
  unsigned __int16 *v109; // rcx
  const unsigned __int16 *v110; // rax
  const unsigned __int16 *v111; // rcx
  signed __int64 v112; // rax
  int v113; // r8d
  int v114; // edx
  __int64 v115; // rsi
  __int64 v116; // rax
  const WCHAR *v117; // rcx
  const unsigned __int16 *v118; // rax
  signed __int64 v119; // rcx
  int v120; // r8d
  int v121; // edx
  __int64 v122; // rax
  const WCHAR *v123; // rcx
  const unsigned __int16 *v124; // rax
  signed __int64 v125; // rcx
  int v126; // r8d
  int v127; // edx
  CONFIG_EXCEPTION *v128; // rax
  unsigned __int16 *v130; // [rsp+20h] [rbp-60h] BYREF
  char *v131[2]; // [rsp+28h] [rbp-58h] BYREF
  _BYTE v132[56]; // [rsp+38h] [rbp-48h] BYREF

  v130 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v132);
  v4 = (_QWORD *)*((_QWORD *)this + 13);
  *(_OWORD *)v131 = 0;
  if ( !v4 || !*v4 )
  {
LABEL_194:
    LockingAttributeValue = 0;
    goto LABEL_195;
  }
  v5 = *((_QWORD *)this + 11);
  *((_BYTE *)this + 69) = 0;
  if ( v5 )
  {
    *(_BYTE *)(v5 + 205) = 0;
    *(_BYTE *)(*((_QWORD *)this + 11) + 207LL) = 0;
    *(_BYTE *)(*((_QWORD *)this + 11) + 209LL) = 0;
  }
  if ( *(_QWORD *)(*((_QWORD *)this + 13) + 8LL) )
  {
    for ( i = 0;
          i < *((unsigned __int16 *)this + 19);
          *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 13) + 8LL) + 2 * v7 + 1) = 0 )
    {
      v7 = i++;
    }
  }
  if ( *(_QWORD *)(*((_QWORD *)this + 13) + 16LL) )
  {
    for ( j = 0; ; ++j )
    {
      v9 = *(_WORD **)(*((_QWORD *)this + 10) + 88LL);
      v10 = v9 ? *v9 : 0;
      if ( j >= v10 )
        break;
      v11 = j;
      *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 13) + 16LL) + 2 * v11 + 1) = 0;
    }
  }
  v12 = *((_QWORD *)this + 13);
  LockingAttributeValue = LOCKING_ATTRIBUTES::GetLockingAttributeValue(
                            *(LOCKING_ATTRIBUTES **)v12,
                            L"lockAttributes",
                            (const unsigned __int16 **)&v130);
  if ( LockingAttributeValue >= 0 )
  {
    v14 = v130;
    if ( v130 )
    {
      if ( !*(_QWORD *)(v12 + 8) )
      {
        v15 = *((unsigned __int16 *)this + 19);
        v16 = (LOCKING_BEHAVIOR *)operator new(saturated_mul(*((unsigned __int16 *)this + 19), 2u));
        v19 = v16;
        if ( v16 )
          `vector constructor iterator'(v16, v17, v15, v18);
        else
          v19 = 0;
        *(_QWORD *)(*((_QWORD *)this + 13) + 8LL) = v19;
        if ( !*(_QWORD *)(*((_QWORD *)this + 13) + 8LL) )
          goto LABEL_22;
      }
      LockingAttributeValue = SplitCommaDelimitedString(v14, 1, 1, (struct MULTISZ *)v132);
      if ( LockingAttributeValue < 0 )
        goto LABEL_195;
      for ( k = MULTISZ::First((MULTISZ *)v132); ; k = MULTISZ::Next((MULTISZ *)v132, v21) )
      {
        v21 = k;
        if ( !k )
          goto LABEL_51;
        v22 = *k - 42;
        if ( *k == 42 )
          v22 = k[1];
        v23 = 0;
        if ( v22 )
          break;
        if ( *((_WORD *)this + 19) )
        {
          do
          {
            if ( (*((_BYTE *)SCHEMA_ELEMENT::QueryAttribute(*((SCHEMA_ELEMENT **)this + 10), v23) + 20) & 0x10) == 0 )
              *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 13) + 8LL) + 2LL * v23 + 1) = 1;
            ++v23;
          }
          while ( v23 < *((_WORD *)this + 19) );
        }
LABEL_33:
        ;
      }
      while ( v23 < *((_WORD *)this + 19) )
      {
        AttributeName = SCHEMA_ELEMENT::QueryAttributeName(*((SCHEMA_ELEMENT **)this + 10), v23);
        v25 = v21;
        v26 = (char *)AttributeName - (char *)v21;
        do
        {
          v27 = *(const unsigned __int16 *)((char *)v25 + v26);
          v28 = *v25 - v27;
          if ( v28 )
            break;
          ++v25;
        }
        while ( v27 );
        if ( !v28 )
        {
          if ( (*((_BYTE *)SCHEMA_ELEMENT::QueryAttribute(*((SCHEMA_ELEMENT **)this + 10), v23) + 20) & 0x10) == 0 )
          {
            if ( (*((_BYTE *)SCHEMA_ELEMENT::QueryAttribute(*((SCHEMA_ELEMENT **)this + 10), v23) + 20) & 1) == 0
              && (*((_BYTE *)SCHEMA_ELEMENT::QueryAttribute(*((SCHEMA_ELEMENT **)this + 10), v23) + 20) & 2) == 0 )
            {
              *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 13) + 8LL) + 2LL * v23 + 1) = 1;
              goto LABEL_33;
            }
            v131[0] = (char *)v21;
            goto LABEL_45;
          }
          break;
        }
        ++v23;
      }
      v131[0] = (char *)v21;
      v33 = (CONFIG_EXCEPTION *)operator new(0x178u);
      if ( !v33 )
        goto LABEL_187;
      v30 = CONFIG_EXCEPTION::CONFIG_EXCEPTION(v33);
      v31 = v30;
      if ( v30 )
      {
        v32 = -1073739103;
        goto LABEL_186;
      }
      goto LABEL_188;
    }
LABEL_51:
    v34 = *((_QWORD *)this + 13);
    LockingAttributeValue = LOCKING_ATTRIBUTES::GetLockingAttributeValue(
                              *(LOCKING_ATTRIBUTES **)v34,
                              L"lockAllAttributesExcept",
                              (const unsigned __int16 **)&v130);
    if ( LockingAttributeValue < 0 )
      goto LABEL_195;
    v35 = v130;
    if ( v130 )
    {
      if ( !*(_QWORD *)(v34 + 8) )
      {
        v36 = *((unsigned __int16 *)this + 19);
        v37 = (LOCKING_BEHAVIOR *)operator new(saturated_mul(*((unsigned __int16 *)this + 19), 2u));
        v40 = v37;
        if ( v37 )
          `vector constructor iterator'(v37, v38, v36, v39);
        else
          v40 = 0;
        *(_QWORD *)(*((_QWORD *)this + 13) + 8LL) = v40;
        if ( !*(_QWORD *)(*((_QWORD *)this + 13) + 8LL) )
          goto LABEL_22;
      }
      LockingAttributeValue = SplitCommaDelimitedString(v35, 1, 1, (struct MULTISZ *)v132);
      if ( LockingAttributeValue < 0 )
        goto LABEL_195;
      v41 = 0;
      v42 = 0;
LABEL_60:
      if ( v42 < *((_WORD *)this + 19) )
      {
        for ( m = MULTISZ::First((MULTISZ *)v132); ; m = MULTISZ::Next((MULTISZ *)v132, v44) )
        {
          v44 = m;
          Attribute = SCHEMA_ELEMENT::QueryAttribute(*((SCHEMA_ELEMENT **)this + 10), v42);
          if ( !v44 )
            break;
          if ( (*((_BYTE *)Attribute + 20) & 0x10) == 0 )
          {
            v46 = SCHEMA_ELEMENT::QueryAttributeName(*((SCHEMA_ELEMENT **)this + 10), v42);
            v47 = v44;
            v48 = (char *)v46 - (char *)v44;
            do
            {
              v49 = *(const unsigned __int16 *)((char *)v47 + v48);
              v50 = *v47 - v49;
              if ( v50 )
                break;
              ++v47;
            }
            while ( v49 );
            if ( !v50 )
            {
              v41 = 1;
LABEL_73:
              ++v42;
              goto LABEL_60;
            }
          }
        }
        if ( (*((_BYTE *)Attribute + 20) & 1) == 0
          && (*((_BYTE *)SCHEMA_ELEMENT::QueryAttribute(*((SCHEMA_ELEMENT **)this + 10), v42) + 20) & 2) == 0 )
        {
          *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 13) + 8LL) + 2LL * v42 + 1) = 1;
          goto LABEL_73;
        }
        v51 = SCHEMA_ELEMENT::QueryAttribute(*((SCHEMA_ELEMENT **)this + 10), v42);
        v52 = (char *)&szDomain;
        if ( *((_QWORD *)v51 + 3) )
          v52 = (char *)*((_QWORD *)v51 + 3);
        v131[0] = v52;
LABEL_45:
        v29 = (CONFIG_EXCEPTION *)operator new(0x178u);
        if ( v29 )
        {
          v30 = CONFIG_EXCEPTION::CONFIG_EXCEPTION(v29);
          v31 = v30;
          if ( !v30 )
            goto LABEL_188;
          v32 = -1073739058;
LABEL_186:
          CONFIG_EXCEPTION::CreateFromErrorId(v30, v32, (const char **)v131);
          goto LABEL_188;
        }
        goto LABEL_187;
      }
      if ( !v41 )
      {
        v53 = (CONFIG_EXCEPTION *)operator new(0x178u);
        if ( v53 )
        {
          v30 = CONFIG_EXCEPTION::CONFIG_EXCEPTION(v53);
          v31 = v30;
          if ( !v30 )
            goto LABEL_188;
          v32 = -1073739101;
          goto LABEL_186;
        }
LABEL_187:
        v31 = 0;
LABEL_188:
        LockingAttributeValue = -2147024883;
        if ( v31 )
        {
          if ( a2 )
            *a2 = v31;
          else
            CONFIG_EXCEPTION::DereferenceSectionException(v31);
        }
        goto LABEL_195;
      }
    }
    v54 = *((_QWORD *)this + 13);
    LockingAttributeValue = LOCKING_ATTRIBUTES::GetLockingAttributeValue(
                              *(LOCKING_ATTRIBUTES **)v54,
                              L"lockElements",
                              (const unsigned __int16 **)&v130);
    if ( LockingAttributeValue < 0 )
      goto LABEL_195;
    v55 = v130;
    if ( v130 )
    {
      if ( *(_QWORD *)(v54 + 16) )
        goto LABEL_91;
      v56 = *(_WORD **)(*((_QWORD *)this + 10) + 88LL);
      v57 = v56 ? *v56 : 0;
      v58 = v57;
      v59 = (LOCKING_BEHAVIOR *)operator new(saturated_mul(v57, 2u));
      v62 = v59;
      if ( v59 )
        `vector constructor iterator'(v59, v60, v58, v61);
      else
        v62 = 0;
      *(_QWORD *)(*((_QWORD *)this + 13) + 16LL) = v62;
      if ( *(_QWORD *)(*((_QWORD *)this + 13) + 16LL) )
      {
LABEL_91:
        LockingAttributeValue = SplitCommaDelimitedString(v55, 1, 1, (struct MULTISZ *)v132);
        if ( LockingAttributeValue < 0 )
          goto LABEL_195;
        for ( n = MULTISZ::First((MULTISZ *)v132); ; n = MULTISZ::Next((MULTISZ *)v132, v64) )
        {
          v64 = n;
          if ( !n )
            goto LABEL_135;
          v65 = *n - 42;
          if ( *n == 42 )
            v65 = n[1];
          if ( v65 )
          {
            for ( ii = 0; ; ++ii )
            {
              v71 = *((_QWORD *)this + 10);
              v72 = *(unsigned __int16 **)(v71 + 88);
              if ( !v72 || ii >= *v72 )
                break;
              ChildElementName = SCHEMA_ELEMENT::QueryChildElementName(*((SCHEMA_ELEMENT **)this + 10), ii);
              v74 = v64;
              v75 = (char *)ChildElementName - (char *)v64;
              do
              {
                v76 = *(const unsigned __int16 *)((char *)v74 + v75);
                v77 = *v74 - v76;
                if ( v77 )
                  break;
                ++v74;
              }
              while ( v76 );
              if ( !v77 )
              {
                *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 13) + 16LL) + 2LL * ii + 1) = 1;
                goto LABEL_104;
              }
            }
            v78 = *(_QWORD *)(v71 + 176);
            if ( !v78 )
            {
LABEL_132:
              v131[0] = (char *)v64;
              v91 = (CONFIG_EXCEPTION *)operator new(0x178u);
              if ( !v91 )
                goto LABEL_187;
              v30 = CONFIG_EXCEPTION::CONFIG_EXCEPTION(v91);
              v31 = v30;
              if ( v30 )
              {
                v32 = -1073739100;
                goto LABEL_186;
              }
              goto LABEL_188;
            }
            if ( SCHEMA_COLLECTION::FindAddSchemaElement(*(SCHEMA_COLLECTION **)(v71 + 176), v64) )
            {
              *(_BYTE *)(*((_QWORD *)this + 11) + 205LL) = 1;
            }
            else
            {
              v79 = *(_QWORD *)(v78 + 56);
              if ( !v79 )
                goto LABEL_125;
              v80 = &szDomain;
              if ( *(_QWORD *)(v79 + 24) )
                v80 = *(const WCHAR **)(v79 + 24);
              v81 = v64;
              v82 = (char *)v80 - (char *)v64;
              do
              {
                v83 = *(const unsigned __int16 *)((char *)v81 + v82);
                v84 = *v81 - v83;
                if ( v84 )
                  break;
                ++v81;
              }
              while ( v83 );
              if ( v84 )
              {
LABEL_125:
                v85 = *(_QWORD *)(v78 + 48);
                if ( !v85 )
                  goto LABEL_132;
                v86 = &szDomain;
                if ( *(_QWORD *)(v85 + 24) )
                  v86 = *(const WCHAR **)(v85 + 24);
                v87 = v64;
                v88 = (char *)v86 - (char *)v64;
                do
                {
                  v89 = *(const unsigned __int16 *)((char *)v87 + v88);
                  v90 = *v87 - v89;
                  if ( v90 )
                    break;
                  ++v87;
                }
                while ( v89 );
                if ( v90 )
                  goto LABEL_132;
                goto LABEL_103;
              }
              *(_BYTE *)(*((_QWORD *)this + 11) + 207LL) = 1;
            }
          }
          else
          {
            for ( jj = 0; ; ++jj )
            {
              v67 = *((_QWORD *)this + 10);
              v68 = *(unsigned __int16 **)(v67 + 88);
              if ( !v68 || jj >= *v68 )
                break;
              v69 = jj;
              *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 13) + 16LL) + 2 * v69 + 1) = 1;
            }
            if ( *(_QWORD *)(v67 + 176) )
            {
              *(_BYTE *)(*((_QWORD *)this + 11) + 205LL) = 1;
              *(_BYTE *)(*((_QWORD *)this + 11) + 207LL) = 1;
LABEL_103:
              *(_BYTE *)(*((_QWORD *)this + 11) + 209LL) = 1;
              continue;
            }
          }
LABEL_104:
          ;
        }
      }
LABEL_22:
      LockingAttributeValue = -2147024888;
      goto LABEL_195;
    }
LABEL_135:
    v92 = *((_QWORD *)this + 13);
    LockingAttributeValue = LOCKING_ATTRIBUTES::GetLockingAttributeValue(
                              *(LOCKING_ATTRIBUTES **)v92,
                              L"lockAllElementsExcept",
                              (const unsigned __int16 **)&v130);
    if ( LockingAttributeValue < 0 )
      goto LABEL_195;
    v93 = v130;
    if ( !v130 )
      goto LABEL_192;
    if ( !*(_QWORD *)(v92 + 16) )
    {
      v94 = *(_WORD **)(*((_QWORD *)this + 10) + 88LL);
      v95 = v94 ? *v94 : 0;
      v96 = v95;
      v97 = (LOCKING_BEHAVIOR *)operator new(saturated_mul(v95, 2u));
      v100 = v97;
      if ( v97 )
        `vector constructor iterator'(v97, v98, v96, v99);
      else
        v100 = 0;
      *(_QWORD *)(*((_QWORD *)this + 13) + 16LL) = v100;
      if ( !*(_QWORD *)(*((_QWORD *)this + 13) + 16LL) )
        goto LABEL_22;
    }
    for ( kk = 0; ; ++kk )
    {
      v102 = *(unsigned __int16 **)(*((_QWORD *)this + 10) + 88LL);
      if ( !v102 || kk >= *v102 )
        break;
      v103 = kk;
      *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 13) + 16LL) + 2 * v103 + 1) = 1;
    }
    v104 = *((_QWORD *)this + 11);
    if ( v104 )
    {
      *(_BYTE *)(v104 + 205) = 1;
      *(_BYTE *)(*((_QWORD *)this + 11) + 207LL) = 1;
      *(_BYTE *)(*((_QWORD *)this + 11) + 209LL) = 1;
    }
    LockingAttributeValue = SplitCommaDelimitedString(v93, 1, 1, (struct MULTISZ *)v132);
    if ( LockingAttributeValue >= 0 )
    {
      v105 = MULTISZ::First((MULTISZ *)v132);
LABEL_153:
      v106 = v105;
      if ( v105 )
      {
        for ( mm = 0; ; ++mm )
        {
          v108 = *((_QWORD *)this + 10);
          v109 = *(unsigned __int16 **)(v108 + 88);
          if ( !v109 || mm >= *v109 )
            break;
          v110 = SCHEMA_ELEMENT::QueryChildElementName(*((SCHEMA_ELEMENT **)this + 10), mm);
          v111 = v106;
          v112 = (char *)v110 - (char *)v106;
          do
          {
            v113 = *(const unsigned __int16 *)((char *)v111 + v112);
            v114 = *v111 - v113;
            if ( v114 )
              break;
            ++v111;
          }
          while ( v113 );
          if ( !v114 )
          {
            *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 13) + 16LL) + 2LL * mm + 1) = 0;
LABEL_182:
            v105 = MULTISZ::Next((MULTISZ *)v132, v106);
            goto LABEL_153;
          }
        }
        v115 = *(_QWORD *)(v108 + 176);
        if ( v115 )
        {
          if ( SCHEMA_COLLECTION::FindAddSchemaElement(*(SCHEMA_COLLECTION **)(v108 + 176), v106) )
          {
            *(_BYTE *)(*((_QWORD *)this + 11) + 205LL) = 0;
            goto LABEL_182;
          }
          v116 = *(_QWORD *)(v115 + 56);
          if ( v116 )
          {
            v117 = &szDomain;
            if ( *(_QWORD *)(v116 + 24) )
              v117 = *(const WCHAR **)(v116 + 24);
            v118 = v106;
            v119 = (char *)v117 - (char *)v106;
            do
            {
              v120 = *(const unsigned __int16 *)((char *)v118 + v119);
              v121 = *v118 - v120;
              if ( v121 )
                break;
              ++v118;
            }
            while ( v120 );
            if ( !v121 )
            {
              *(_BYTE *)(*((_QWORD *)this + 11) + 207LL) = 0;
              goto LABEL_182;
            }
          }
          v122 = *(_QWORD *)(v115 + 48);
          if ( v122 )
          {
            v123 = &szDomain;
            if ( *(_QWORD *)(v122 + 24) )
              v123 = *(const WCHAR **)(v122 + 24);
            v124 = v106;
            v125 = (char *)v123 - (char *)v106;
            do
            {
              v126 = *(const unsigned __int16 *)((char *)v124 + v125);
              v127 = *v124 - v126;
              if ( v127 )
                break;
              ++v124;
            }
            while ( v126 );
            if ( !v127 )
            {
              *(_BYTE *)(*((_QWORD *)this + 11) + 209LL) = 0;
              goto LABEL_182;
            }
          }
        }
        v131[0] = (char *)v106;
        v128 = (CONFIG_EXCEPTION *)operator new(0x178u);
        if ( v128 )
        {
          v30 = CONFIG_EXCEPTION::CONFIG_EXCEPTION(v128);
          v31 = v30;
          if ( !v30 )
            goto LABEL_188;
          v32 = -1073739060;
          goto LABEL_186;
        }
        goto LABEL_187;
      }
LABEL_192:
      if ( *(_BYTE *)(**((_QWORD **)this + 13) + 21LL) )
        *((_BYTE *)this + 69) = 1;
      goto LABEL_194;
    }
  }
LABEL_195:
  MULTISZ::~MULTISZ((MULTISZ *)v132);
  return (unsigned int)LockingAttributeValue;
}

```

## disassembly

```asm
0x18002e0c8  mov     [rsp-38h+arg_10], rbx
0x18002e0cd  push    rbp
0x18002e0ce  push    rsi
0x18002e0cf  push    rdi
0x18002e0d0  push    r12
0x18002e0d2  push    r13
0x18002e0d4  push    r14
0x18002e0d6  push    r15
0x18002e0d8  mov     rbp, rsp
0x18002e0db  sub     rsp, 80h
0x18002e0e2  mov     rax, cs:__security_cookie
0x18002e0e9  xor     rax, rsp
0x18002e0ec  mov     [rbp+var_10], rax
0x18002e0f0  mov     rdi, rcx
0x18002e0f3  xor     r13d, r13d
0x18002e0f6  lea     rcx, [rbp+var_48]
0x18002e0fa  mov     [rbp+var_60], r13
0x18002e0fe  mov     r12, rdx
0x18002e101  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18002e107  mov     rax, [rdi+68h]
0x18002e10b  xorps   xmm0, xmm0
0x18002e10e  movups  xmmword ptr [rbp+var_58], xmm0
0x18002e112  test    rax, rax
0x18002e115  jz      loc_18002EAA4
0x18002e11b  cmp     [rax], r13
0x18002e11e  jz      loc_18002EAA4
0x18002e124  mov     rax, [rdi+58h]
0x18002e128  mov     [rdi+45h], r13b
0x18002e12c  test    rax, rax
0x18002e12f  jz      short loc_18002E14E
0x18002e131  mov     [rax+0CDh], r13b
0x18002e138  mov     rax, [rdi+58h]
0x18002e13c  mov     [rax+0CFh], r13b
0x18002e143  mov     rax, [rdi+58h]
0x18002e147  mov     [rax+0D1h], r13b
0x18002e14e  mov     rax, [rdi+68h]
0x18002e152  mov     r15d, 1
0x18002e158  cmp     [rax+8], r13
0x18002e15c  jz      short loc_18002E184
0x18002e15e  mov     r8d, r13d
0x18002e161  cmp     r13w, [rdi+26h]
0x18002e166  jnb     short loc_18002E184
0x18002e168  mov     rax, [rdi+68h]
0x18002e16c  mov     edx, r8d
0x18002e16f  add     r8d, r15d
0x18002e172  mov     rcx, [rax+8]
0x18002e176  mov     [rcx+rdx*2+1], r13b
0x18002e17b  movzx   eax, word ptr [rdi+26h]
0x18002e17f  cmp     r8d, eax
0x18002e182  jb      short loc_18002E168
0x18002e184  mov     rax, [rdi+68h]
0x18002e188  cmp     [rax+10h], r13
0x18002e18c  jz      short loc_18002E1C3
0x18002e18e  mov     r8d, r13d
0x18002e191  mov     rax, [rdi+50h]
0x18002e195  mov     rcx, [rax+58h]
0x18002e199  test    rcx, rcx
0x18002e19c  jnz     short loc_18002E1A3
0x18002e19e  mov     eax, r13d
0x18002e1a1  jmp     short loc_18002E1A6
0x18002e1a3  movzx   eax, word ptr [rcx]
0x18002e1a6  movzx   eax, ax
0x18002e1a9  cmp     r8d, eax
0x18002e1ac  jnb     short loc_18002E1C3
0x18002e1ae  mov     rax, [rdi+68h]
0x18002e1b2  mov     edx, r8d
0x18002e1b5  add     r8d, r15d
0x18002e1b8  mov     rcx, [rax+10h]
0x18002e1bc  mov     [rcx+rdx*2+1], r13b
0x18002e1c1  jmp     short loc_18002E191
0x18002e1c3  mov     rsi, [rdi+68h]
0x18002e1c7  lea     r8, [rbp+var_60]; unsigned __int16 **
0x18002e1cb  lea     rdx, aLockattributes; "lockAttributes"
0x18002e1d2  mov     rcx, [rsi]; this
0x18002e1d5  call    ?GetLockingAttributeValue@LOCKING_ATTRIBUTES@@QEAAJPEBGPEAPEBG@Z; LOCKING_ATTRIBUTES::GetLockingAttributeValue(ushort const *,ushort const * *)
0x18002e1da  mov     ebx, eax
0x18002e1dc  test    eax, eax
0x18002e1de  js      loc_18002EAA7
0x18002e1e4  mov     r14, [rbp+var_60]
0x18002e1e8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002e1ec  test    r14, r14
0x18002e1ef  jz      loc_18002E3CA
0x18002e1f5  cmp     [rsi+8], r13
0x18002e1f9  jnz     short loc_18002E245
0x18002e1fb  movzx   esi, word ptr [rdi+26h]
0x18002e1ff  lea     eax, [rcx+3]
0x18002e202  mul     rsi
0x18002e205  cmovb   rax, rcx
0x18002e209  mov     rcx, rax; Size
0x18002e20c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e211  mov     rbx, rax
0x18002e214  test    rax, rax
0x18002e217  jz      short loc_18002E226
0x18002e219  mov     r8d, esi; unsigned __int64
0x18002e21c  mov     rcx, rax; this
0x18002e21f  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18002e224  jmp     short loc_18002E229
0x18002e226  mov     rbx, r13
0x18002e229  mov     rax, [rdi+68h]
0x18002e22d  mov     [rax+8], rbx
0x18002e231  mov     rax, [rdi+68h]
0x18002e235  cmp     [rax+8], r13
0x18002e239  jnz     short loc_18002E245
0x18002e23b  mov     ebx, 80070008h
0x18002e240  jmp     loc_18002EAA7
0x18002e245  lea     r9, [rbp+var_48]
0x18002e249  mov     r8d, r15d
0x18002e24c  mov     edx, r15d
0x18002e24f  mov     rcx, r14
0x18002e252  call    cs:__imp_?SplitCommaDelimitedString@@YAJPEBGHHPEAVMULTISZ@@@Z; SplitCommaDelimitedString(ushort const *,int,int,MULTISZ *)
0x18002e258  mov     ebx, eax
0x18002e25a  test    eax, eax
0x18002e25c  js      loc_18002EAA7
0x18002e262  lea     rcx, [rbp+var_48]
0x18002e266  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x18002e26c  mov     r14d, 2Ah ; '*'
0x18002e272  mov     rbx, rax
0x18002e275  test    rax, rax
0x18002e278  jz      loc_18002E3CA
0x18002e27e  movzx   edx, word ptr [rax]
0x18002e281  sub     edx, r14d
0x18002e284  jnz     short loc_18002E290
0x18002e286  movzx   edx, word ptr [rax+2]
0x18002e28a  movzx   ecx, r13w
0x18002e28e  sub     edx, ecx
0x18002e290  mov     esi, r13d
0x18002e293  test    edx, edx
0x18002e295  jnz     short loc_18002E2D9
0x18002e297  cmp     r13w, [rdi+26h]
0x18002e29c  jnb     short loc_18002E2CA
0x18002e29e  mov     rcx, [rdi+50h]; this
0x18002e2a2  movzx   edx, si; unsigned __int16
0x18002e2a5  call    ?QueryAttribute@SCHEMA_ELEMENT@@QEAAPEAVSCHEMA_ATTRIBUTE@@G@Z; SCHEMA_ELEMENT::QueryAttribute(ushort)
0x18002e2aa  test    byte ptr [rax+14h], 10h
0x18002e2ae  jnz     short loc_18002E2C0
0x18002e2b0  mov     rax, [rdi+68h]
0x18002e2b4  movzx   edx, si
0x18002e2b7  mov     rcx, [rax+8]
0x18002e2bb  mov     [rcx+rdx*2+1], r15b
0x18002e2c0  add     si, r15w
0x18002e2c4  cmp     si, [rdi+26h]
0x18002e2c8  jb      short loc_18002E29E
0x18002e2ca  mov     rdx, rbx
0x18002e2cd  lea     rcx, [rbp+var_48]
0x18002e2d1  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x18002e2d7  jmp     short loc_18002E272
0x18002e2d9  cmp     si, [rdi+26h]
0x18002e2dd  jnb     loc_18002E395
0x18002e2e3  mov     rcx, [rdi+50h]; this
0x18002e2e7  movzx   edx, si; unsigned __int16
0x18002e2ea  call    ?QueryAttributeName@SCHEMA_ELEMENT@@QEAAPEBGG@Z; SCHEMA_ELEMENT::QueryAttributeName(ushort)
0x18002e2ef  mov     rcx, rbx
0x18002e2f2  sub     rax, rbx
0x18002e2f5  movzx   r8d, word ptr [rcx]
0x18002e2f9  movzx   edx, word ptr [rcx+rax]
0x18002e2fd  sub     r8d, edx
0x18002e300  jnz     short loc_18002E30A
0x18002e302  add     rcx, 2
0x18002e306  test    edx, edx
0x18002e308  jnz     short loc_18002E2F5
0x18002e30a  test    r8d, r8d
0x18002e30d  jz      short loc_18002E315
0x18002e30f  add     si, r15w
0x18002e313  jmp     short loc_18002E2D9
0x18002e315  mov     rcx, [rdi+50h]; this
0x18002e319  movzx   edx, si; unsigned __int16
0x18002e31c  call    ?QueryAttribute@SCHEMA_ELEMENT@@QEAAPEAVSCHEMA_ATTRIBUTE@@G@Z; SCHEMA_ELEMENT::QueryAttribute(ushort)
0x18002e321  test    byte ptr [rax+14h], 10h
0x18002e325  jnz     short loc_18002E395
0x18002e327  mov     rcx, [rdi+50h]; this
0x18002e32b  movzx   edx, si; unsigned __int16
0x18002e32e  call    ?QueryAttribute@SCHEMA_ELEMENT@@QEAAPEAVSCHEMA_ATTRIBUTE@@G@Z; SCHEMA_ELEMENT::QueryAttribute(ushort)
0x18002e333  test    [rax+14h], r15b
0x18002e337  jnz     short loc_18002E360
0x18002e339  mov     rcx, [rdi+50h]; this
0x18002e33d  movzx   edx, si; unsigned __int16
0x18002e340  call    ?QueryAttribute@SCHEMA_ELEMENT@@QEAAPEAVSCHEMA_ATTRIBUTE@@G@Z; SCHEMA_ELEMENT::QueryAttribute(ushort)
0x18002e345  test    byte ptr [rax+14h], 2
0x18002e349  jnz     short loc_18002E360
0x18002e34b  mov     rax, [rdi+68h]
0x18002e34f  movzx   edx, si
0x18002e352  mov     rcx, [rax+8]
0x18002e356  mov     [rcx+rdx*2+1], r15b
0x18002e35b  jmp     loc_18002E2CA
0x18002e360  mov     [rbp+var_58], rbx
0x18002e364  mov     ecx, 178h; Size
0x18002e369  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e36e  test    rax, rax
0x18002e371  jz      loc_18002EA6B
0x18002e377  mov     rcx, rax; this
0x18002e37a  call    ??0CONFIG_EXCEPTION@@QEAA@XZ; CONFIG_EXCEPTION::CONFIG_EXCEPTION(void)
0x18002e37f  mov     rdi, rax
0x18002e382  test    rax, rax
0x18002e385  jz      loc_18002EA6E
0x18002e38b  mov     edx, 0C0000ACEh
0x18002e390  jmp     loc_18002EA5D
0x18002e395  mov     ecx, 178h; Size
0x18002e39a  mov     [rbp+var_58], rbx
0x18002e39e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e3a3  test    rax, rax
0x18002e3a6  jz      loc_18002EA6B
0x18002e3ac  mov     rcx, rax; this
0x18002e3af  call    ??0CONFIG_EXCEPTION@@QEAA@XZ; CONFIG_EXCEPTION::CONFIG_EXCEPTION(void)
0x18002e3b4  mov     rdi, rax
0x18002e3b7  test    rax, rax
0x18002e3ba  jz      loc_18002EA6E
0x18002e3c0  mov     edx, 0C0000AA1h
0x18002e3c5  jmp     loc_18002EA5D
0x18002e3ca  mov     rsi, [rdi+68h]
0x18002e3ce  lea     r8, [rbp+var_60]; unsigned __int16 **
0x18002e3d2  lea     rdx, aLockallattribu; "lockAllAttributesExcept"
0x18002e3d9  mov     rcx, [rsi]; this
0x18002e3dc  call    ?GetLockingAttributeValue@LOCKING_ATTRIBUTES@@QEAAJPEBGPEAPEBG@Z; LOCKING_ATTRIBUTES::GetLockingAttributeValue(ushort const *,ushort const * *)
0x18002e3e1  mov     ebx, eax
0x18002e3e3  test    eax, eax
0x18002e3e5  js      loc_18002EAA7
0x18002e3eb  mov     r14, [rbp+var_60]
0x18002e3ef  test    r14, r14
0x18002e3f2  jz      loc_18002E568
0x18002e3f8  cmp     [rsi+8], r13
0x18002e3fc  jnz     short loc_18002E44B
0x18002e3fe  movzx   esi, word ptr [rdi+26h]
0x18002e402  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002e409  mov     eax, 2
0x18002e40e  mul     rsi
0x18002e411  cmovb   rax, rcx
0x18002e415  mov     rcx, rax; Size
0x18002e418  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e41d  mov     rbx, rax
0x18002e420  test    rax, rax
0x18002e423  jz      short loc_18002E432
0x18002e425  mov     r8d, esi; unsigned __int64
0x18002e428  mov     rcx, rax; this
0x18002e42b  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18002e430  jmp     short loc_18002E435
0x18002e432  mov     rbx, r13
0x18002e435  mov     rax, [rdi+68h]
0x18002e439  mov     [rax+8], rbx
0x18002e43d  mov     rax, [rdi+68h]
0x18002e441  cmp     [rax+8], r13
0x18002e445  jz      loc_18002E23B
0x18002e44b  lea     r9, [rbp+var_48]
0x18002e44f  mov     r8d, r15d
0x18002e452  mov     edx, r15d
0x18002e455  mov     rcx, r14
0x18002e458  call    cs:__imp_?SplitCommaDelimitedString@@YAJPEBGHHPEAVMULTISZ@@@Z; SplitCommaDelimitedString(ushort const *,int,int,MULTISZ *)
0x18002e45e  mov     ebx, eax
0x18002e460  test    eax, eax
0x18002e462  js      loc_18002EAA7
0x18002e468  mov     r14d, r13d
0x18002e46b  mov     ebx, r13d
0x18002e46e  cmp     bx, [rdi+26h]
0x18002e472  jnb     loc_18002E532
0x18002e478  lea     rcx, [rbp+var_48]
0x18002e47c  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x18002e482  mov     rcx, [rdi+50h]; this
0x18002e486  movzx   edx, bx; unsigned __int16
0x18002e489  mov     rsi, rax
0x18002e48c  call    ?QueryAttribute@SCHEMA_ELEMENT@@QEAAPEAVSCHEMA_ATTRIBUTE@@G@Z; SCHEMA_ELEMENT::QueryAttribute(ushort)
0x18002e491  test    rsi, rsi
0x18002e494  jz      short loc_18002E4DC
0x18002e496  test    byte ptr [rax+14h], 10h
0x18002e49a  jnz     short loc_18002E4C8
0x18002e49c  mov     rcx, [rdi+50h]; this
0x18002e4a0  movzx   edx, bx; unsigned __int16
0x18002e4a3  call    ?QueryAttributeName@SCHEMA_ELEMENT@@QEAAPEBGG@Z; SCHEMA_ELEMENT::QueryAttributeName(ushort)
0x18002e4a8  mov     rcx, rsi
0x18002e4ab  sub     rax, rsi
0x18002e4ae  movzx   r8d, word ptr [rcx]
0x18002e4b2  movzx   edx, word ptr [rcx+rax]
0x18002e4b6  sub     r8d, edx
0x18002e4b9  jnz     short loc_18002E4C3
0x18002e4bb  add     rcx, 2
0x18002e4bf  test    edx, edx
0x18002e4c1  jnz     short loc_18002E4AE
0x18002e4c3  test    r8d, r8d
0x18002e4c6  jz      short loc_18002E4D7
0x18002e4c8  mov     rdx, rsi
0x18002e4cb  lea     rcx, [rbp+var_48]
0x18002e4cf  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x18002e4d5  jmp     short loc_18002E482
0x18002e4d7  mov     r14d, r15d
0x18002e4da  jmp     short loc_18002E504
0x18002e4dc  test    [rax+14h], r15b
0x18002e4e0  jnz     short loc_18002E50D
0x18002e4e2  mov     rcx, [rdi+50h]; this
0x18002e4e6  movzx   edx, bx; unsigned __int16
0x18002e4e9  call    ?QueryAttribute@SCHEMA_ELEMENT@@QEAAPEAVSCHEMA_ATTRIBUTE@@G@Z; SCHEMA_ELEMENT::QueryAttribute(ushort)
0x18002e4ee  test    byte ptr [rax+14h], 2
0x18002e4f2  jnz     short loc_18002E50D
0x18002e4f4  mov     rax, [rdi+68h]
0x18002e4f8  movzx   edx, bx
0x18002e4fb  mov     rcx, [rax+8]
0x18002e4ff  mov     [rcx+rdx*2+1], r15b
0x18002e504  add     bx, r15w
0x18002e508  jmp     loc_18002E46E
0x18002e50d  mov     rcx, [rdi+50h]; this
0x18002e511  movzx   edx, bx; unsigned __int16
0x18002e514  call    ?QueryAttribute@SCHEMA_ELEMENT@@QEAAPEAVSCHEMA_ATTRIBUTE@@G@Z; SCHEMA_ELEMENT::QueryAttribute(ushort)
0x18002e519  lea     r15, szDomain
  ... truncated ...
```
