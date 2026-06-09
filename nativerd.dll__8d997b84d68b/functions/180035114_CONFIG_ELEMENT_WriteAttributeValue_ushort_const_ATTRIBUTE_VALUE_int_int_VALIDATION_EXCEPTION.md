# CONFIG_ELEMENT::WriteAttributeValue(ushort const *,ATTRIBUTE_VALUE *,int,int,VALIDATION_EXCEPTION * *)

- ea: `0x180035114`
- end: `0x1800357c5`
- name: `?WriteAttributeValue@CONFIG_ELEMENT@@QEAAJPEBGPEAVATTRIBUTE_VALUE@@HHPEAPEAVVALIDATION_EXCEPTION@@@Z`
- size: `1713`
- prototype: `__int64 __usercall@<rax>(CONFIG_ELEMENT *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, struct ATTRIBUTE_VALUE *@<r8>, int@<r9d>, int, struct VALIDATION_EXCEPTION **)`
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800340e4`
- `0x180058160`

## callees

- `0x18000c4fc`
- `0x18000c7e4`
- `0x18000d964`
- `0x18000d9a0`
- `0x180011428`
- `0x180011af8`
- `0x1800124bc`
- `0x180014d8c`
- `0x180016520`
- `0x180019f88`
- `0x18001b1b8`
- `0x18001bdc4`
- `0x18001c250`
- `0x18001d2fc`
- `0x18001d518`
- `0x18001d530`
- `0x18001d5c4`
- `0x18001d640`
- `0x18001d700`
- `0x18001d760`
- `0x18002d45c`
- `0x18002dbd0`
- `0x180030bcc`
- `0x180031fa4`
- `0x1800331d0`
- `0x180033f58`
- `0x180035114`
- `0x1800366e4`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180035788`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180035788`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800351ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800351ad`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180035793`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180035793`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180035455`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003550d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180035455`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003550d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003518e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003518e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003543d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800356bb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003543d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800356bb`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x1800351e2`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180035630`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x1800351e2`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180035630`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18003567c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18003567c`

## pseudocode

```c
__int64 __fastcall CONFIG_ELEMENT::WriteAttributeValue(
        CONFIG_ELEMENT *this,
        const unsigned __int16 *a2,
        struct ATTRIBUTE_VALUE *a3,
        int a4,
        int a5,
        struct VALIDATION_EXCEPTION **a6)
{
  int v9; // r12d
  struct SCHEMA_ATTRIBUTE *v10; // rdi
  RTL_SRWLOCK *v11; // r15
  SCHEMA_ATTRIBUTE *v12; // r14
  unsigned __int16 i; // r15
  SCHEMA_ELEMENT *v14; // rcx
  const unsigned __int16 *AttributeName; // rax
  SCHEMA_ATTRIBUTE *Attribute; // rax
  VALIDATION_EXCEPTION *v17; // rax
  VALIDATION_EXCEPTION *v18; // rax
  __int64 v19; // rdx
  DWORD ErrorIdFromEditMode; // eax
  struct STRU *v21; // r8
  int GeneratedSchema; // ebx
  struct SCHEMA_ATTRIBUTE *v23; // rax
  int v24; // r8d
  VALIDATION_EXCEPTION *v25; // rax
  VALIDATION_EXCEPTION *v26; // rax
  int v27; // eax
  wchar_t *Str; // rax
  struct ATTRIBUTE_VALUE *v29; // rax
  struct ATTRIBUTE_VALUE *v30; // r12
  wchar_t *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // r15
  ATTRIBUTE_VALUE *v35; // rcx
  ATTRIBUTE_VALUE *v36; // rcx
  wchar_t *ProviderName; // rax
  struct PROVIDER_ENTRY *ProviderEntry; // rax
  __int64 v39; // rax
  STRU *v40; // rax
  STRU *v41; // rcx
  STRU *v42; // rcx
  int j; // r8d
  unsigned int v44; // r9d
  struct ATTRIBUTE_VALUE *v46; // [rsp+40h] [rbp-C0h]
  VALIDATION_EXCEPTION *v47; // [rsp+50h] [rbp-B0h] BYREF
  int v48; // [rsp+58h] [rbp-A8h]
  va_list Arguments; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v50; // [rsp+68h] [rbp-98h]
  struct VALIDATION_EXCEPTION **v51; // [rsp+70h] [rbp-90h]
  _BYTE v52[56]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v53[256]; // [rsp+B0h] [rbp-50h] BYREF

  v50 = a2;
  v51 = a6;
  v9 = 0;
  v48 = a4;
  v47 = 0;
  v10 = 0;
  memset_0(v53, 0, sizeof(v53));
  STRU::STRU((STRU *)v52, v53, 0x100u);
  v11 = (RTL_SRWLOCK *)((char *)this + 48);
  Arguments = 0;
  v46 = 0;
  v12 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 6);
  if ( !a2 || !a3 )
  {
    GeneratedSchema = -2147024809;
    goto LABEL_89;
  }
  for ( i = 0; ; ++i )
  {
    v14 = (SCHEMA_ELEMENT *)*((_QWORD *)this + 10);
    if ( i >= *((_WORD *)v14 + 16) )
      goto LABEL_10;
    AttributeName = SCHEMA_ELEMENT::QueryAttributeName(v14, i);
    if ( IsStringEqualOrdinalIgnoreCase(a2, AttributeName) )
      break;
  }
  Attribute = SCHEMA_ELEMENT::QueryAttribute(*((SCHEMA_ELEMENT **)this + 10), i);
  v12 = Attribute;
  if ( !Attribute || !SCHEMA_ATTRIBUTE::QueryExtension(Attribute) || (*((_DWORD *)this + 34) & 0xF0000) != 0x30000 )
  {
LABEL_10:
    if ( (*((_DWORD *)this + 34) & 0xF0000) != 0 && !a5 )
    {
      v17 = (VALIDATION_EXCEPTION *)operator new(0x1E8u);
      if ( v17 )
      {
        v18 = VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(v17);
        v47 = v18;
        if ( v18 )
        {
          ErrorIdFromEditMode = CONFIG_ELEMENT::GetErrorIdFromEditMode(
                                  (unsigned int)((int)(*((_DWORD *)this + 34) << 12) >> 28),
                                  v19,
                                  (char *)v18 + 208);
          AdminFormatMessage(ErrorIdFromEditMode, &Arguments, v21, 0);
        }
      }
      else
      {
        v47 = 0;
      }
      GeneratedSchema = -2147024863;
      goto LABEL_17;
    }
  }
  if ( (*(_BYTE *)(*((_QWORD *)this + 10) + 128LL) & 1) == 0 )
    goto LABEL_101;
  if ( !v12 )
  {
    v23 = (struct SCHEMA_ATTRIBUTE *)operator new(0x40u);
    v10 = v23;
    if ( !v23 )
    {
      GeneratedSchema = -2147024888;
      goto LABEL_29;
    }
    _InterlockedAdd(&g_cModuleRefs, 1u);
    *((_QWORD *)v23 + 1) = 0;
    *((_QWORD *)v23 + 2) = 1;
    *(_QWORD *)v23 = &SCHEMA_ATTRIBUTE::`vftable';
    *((_QWORD *)v23 + 3) = 0;
    *((_QWORD *)v23 + 4) = 0;
    *((_DWORD *)v23 + 10) = 0;
    *((_QWORD *)v23 + 6) = 0;
    *((_QWORD *)v23 + 7) = 0;
    GeneratedSchema = SCHEMA_ATTRIBUTE::CreateGeneratedSchema(v23, a2);
    if ( GeneratedSchema < 0 )
      goto LABEL_17;
    GeneratedSchema = SCHEMA_ELEMENT::AddAttribute(*((SCHEMA_ELEMENT **)this + 10), v10);
    if ( GeneratedSchema < 0 )
      goto LABEL_17;
    v12 = v10;
    i = *(_WORD *)(*((_QWORD *)this + 10) + 32LL) - 1;
  }
  GeneratedSchema = CONFIG_ELEMENT::SyncAttributeCountWithSchema(this);
  v10 = 0;
  if ( GeneratedSchema >= 0 )
  {
LABEL_101:
    if ( !v12 )
    {
      GeneratedSchema = -2147023483;
LABEL_29:
      v10 = 0;
LABEL_17:
      v12 = 0;
      goto LABEL_18;
    }
    if ( !(unsigned int)CONFIG_ELEMENT::QueryAttributeAllowCommit(this, i) )
    {
      v25 = (VALIDATION_EXCEPTION *)operator new(0x1E8u);
      if ( v25 )
      {
        v26 = VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(v25);
        v47 = v26;
        if ( v26 )
          AdminFormatMessage(0xC0000AA6, &Arguments, (VALIDATION_EXCEPTION *)((char *)v26 + 208), 0);
      }
      else
      {
        v47 = 0;
      }
      GeneratedSchema = -2147024863;
      goto LABEL_29;
    }
    v27 = (int)(*((_DWORD *)a3 + 1) << 27) >> 27;
    if ( v27 == 2 )
    {
      switch ( *((_DWORD *)v12 + 10) )
      {
        case 6:
          ATTRIBUTE_VALUE::SetEnum(a3, **((_DWORD **)a3 + 1));
          break;
        case 5:
          ATTRIBUTE_VALUE::SetFlags(a3, **((_DWORD **)a3 + 1));
          break;
        case 9:
          ATTRIBUTE_VALUE::SetUInt(a3, **((_DWORD **)a3 + 1));
          break;
      }
    }
    else if ( v27 == v24 && *((_DWORD *)v12 + 10) != v24 )
    {
      GeneratedSchema = STRU::Copy((STRU *)v52, *((const unsigned __int16 **)a3 + 1));
      v10 = 0;
      if ( GeneratedSchema < 0 )
        goto LABEL_63;
      Str = STRU::QueryStr((STRU *)v52);
      GeneratedSchema = SCHEMA_ATTRIBUTE::CopyString(v12, Str, a3, 0, &v47, 42, 0);
      if ( GeneratedSchema < 0 )
        goto LABEL_63;
      v9 = 1;
    }
    if ( *((_DWORD *)v12 + 10) != (int)(*((_DWORD *)a3 + 1) << 27) >> 27 && !v48 )
    {
      GeneratedSchema = -2147024883;
      goto LABEL_29;
    }
    v10 = 0;
    GeneratedSchema = SCHEMA_ATTRIBUTE::CopyAttribute(v12, a3, (struct STRU *)v52);
    if ( GeneratedSchema < 0 )
      goto LABEL_63;
    if ( !v48 )
    {
      if ( !v9 )
      {
        v29 = (struct ATTRIBUTE_VALUE *)operator new(0x20u);
        v46 = v29;
        v30 = v29;
        if ( !v29 )
        {
          GeneratedSchema = -2147024888;
          goto LABEL_17;
        }
        *(_QWORD *)v29 = 1;
        *((_QWORD *)v29 + 1) = 0;
        *((_QWORD *)v29 + 3) = 0;
        v31 = STRU::QueryStr((STRU *)v52);
        GeneratedSchema = SCHEMA_ATTRIBUTE::CopyString(v12, v31, v30, 0, &v47, 42, 0);
        if ( GeneratedSchema < 0 )
          goto LABEL_63;
      }
      v32 = *((_QWORD *)v12 + 6);
      if ( v32 )
      {
        v33 = *(_QWORD *)(v32 + 16);
        if ( v33 )
        {
          GeneratedSchema = (*(__int64 (__fastcall **)(__int64, struct ATTRIBUTE_VALUE *, const WCHAR *, VALIDATION_EXCEPTION **))(*(_QWORD *)v33 + 16LL))(
                              v33,
                              a3,
                              &szDomain,
                              &v47);
          v10 = 0;
          if ( GeneratedSchema < 0 )
            goto LABEL_63;
          if ( v47 )
          {
            GeneratedSchema = -2147024883;
            goto LABEL_63;
          }
        }
      }
    }
    GeneratedSchema = CONFIG_ELEMENT::InitializeOrResizeOriginalAttributesLogIfNeeded(this, *((_WORD *)this + 19), 1);
    v10 = 0;
    if ( GeneratedSchema >= 0 )
    {
      v34 = 16LL * i;
      v35 = *(ATTRIBUTE_VALUE **)(v34 + *((_QWORD *)this + 5));
      if ( !v35 )
        goto LABEL_82;
      if ( !ATTRIBUTE_VALUE::QueryProviderName(v35)
        || (ProviderName = (wchar_t *)ATTRIBUTE_VALUE::QueryProviderName(v36),
            GeneratedSchema = ATTRIBUTE_VALUE::SetProviderName(a3, ProviderName),
            GeneratedSchema >= 0) )
      {
        ProviderEntry = ATTRIBUTE_VALUE::QueryProviderEntry(*(ATTRIBUTE_VALUE **)(v34 + *((_QWORD *)this + 5)));
        if ( ProviderEntry )
          ATTRIBUTE_VALUE::SetProviderEntry(a3, ProviderEntry);
        if ( (*(_BYTE *)(*((_QWORD *)this + 10) + 20LL) & 8) == 0 )
          goto LABEL_81;
        if ( !IsStringEqualOrdinalIgnoreCase(v50, L"name") )
          goto LABEL_81;
        v39 = *((_QWORD *)this + 16);
        if ( v39 )
        {
          if ( *(_QWORD *)(v39 + 24) )
            goto LABEL_81;
        }
        GeneratedSchema = CONFIG_ELEMENT::AllocateFieldMemory(this, 3);
        v10 = 0;
        if ( GeneratedSchema < 0 )
          goto LABEL_63;
        v40 = (STRU *)operator new(0x38u);
        if ( v40 )
          v41 = STRU::STRU(v40);
        else
          v41 = 0;
        *(_QWORD *)(*((_QWORD *)this + 16) + 24LL) = v41;
        v42 = *(STRU **)(*((_QWORD *)this + 16) + 24LL);
        if ( !v42 )
        {
          GeneratedSchema = -2147024888;
          goto LABEL_63;
        }
        GeneratedSchema = STRU::Copy(v42, *(const unsigned __int16 **)(*(_QWORD *)(v34 + *((_QWORD *)this + 5)) + 8LL));
        if ( GeneratedSchema >= 0 )
        {
LABEL_81:
          ATTRIBUTE_VALUE::DereferenceAttributeValue(*(ATTRIBUTE_VALUE **)(v34 + *((_QWORD *)this + 5)));
LABEL_82:
          *(_QWORD *)(v34 + *((_QWORD *)this + 5)) = a3;
          ATTRIBUTE_VALUE::ReferenceAttributeValue(a3);
          for ( j = -3; j != -1; ++j )
            *(_DWORD *)(v34 + *((_QWORD *)this + 5) + 8) &= j;
          *(_DWORD *)(v34 + *((_QWORD *)this + 5) + 8) |= 4u;
          if ( !SCHEMA_ATTRIBUTE::QueryExtension(v12) )
            CONFIG_ELEMENT::SetEditType(this, v44);
          v10 = 0;
        }
      }
    }
  }
LABEL_63:
  v12 = v46;
LABEL_18:
  v11 = (RTL_SRWLOCK *)((char *)this + 48);
LABEL_89:
  if ( v51 && v47 )
  {
    *v51 = v47;
    v47 = 0;
  }
  if ( v10 )
    SCHEMA_ATTRIBUTE::DereferenceSchemaAttribute(v10);
  if ( v47 )
  {
    VALIDATION_EXCEPTION::DereferenceValidationException(v47);
    v47 = 0;
  }
  if ( v12 )
    ATTRIBUTE_VALUE::DereferenceAttributeValue(v12);
  ReleaseSRWLockExclusive(v11);
  STRU::~STRU((STRU *)v52);
  return (unsigned int)GeneratedSchema;
}

```

## disassembly

```asm
0x180035114  mov     [rsp-8+arg_18], rbx
0x180035119  push    rbp
0x18003511a  push    rsi
0x18003511b  push    rdi
0x18003511c  push    r12
0x18003511e  push    r13
0x180035120  push    r14
0x180035122  push    r15
0x180035124  lea     rbp, [rsp-1C0h]
0x18003512c  sub     rsp, 2C0h
0x180035133  mov     rax, cs:__security_cookie
0x18003513a  xor     rax, rsp
0x18003513d  mov     [rbp+1F0h+var_40], rax
0x180035144  mov     rax, [rbp+1F0h+arg_28]
0x18003514b  mov     r13, r8
0x18003514e  mov     rbx, rdx
0x180035151  mov     [rsp+2F0h+var_288], rdx
0x180035156  mov     rsi, rcx
0x180035159  mov     [rsp+2F0h+var_280], rax
0x18003515e  xor     r12d, r12d
0x180035161  mov     [rsp+2F0h+var_298], r9d
0x180035166  xor     edx, edx; Val
0x180035168  mov     [rsp+2F0h+var_2A0], r12
0x18003516d  mov     r8d, 200h; Size
0x180035173  lea     rcx, [rbp+1F0h+var_240]; void *
0x180035177  mov     edi, r12d
0x18003517a  call    memset_0
0x18003517f  mov     r8d, 100h
0x180035185  lea     rdx, [rbp+1F0h+var_240]
0x180035189  lea     rcx, [rsp+2F0h+var_278]
0x18003518e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180035194  lea     r15, [rsi+30h]
0x180035198  mov     [rsp+2F0h+Arguments], r12
0x18003519d  mov     rcx, r15; SRWLock
0x1800351a0  mov     [rsp+2F0h+var_2B0], r12
0x1800351a5  mov     r14d, r12d
0x1800351a8  mov     [rsp+2F0h+SRWLock], r15
0x1800351ad  call    cs:__imp_AcquireSRWLockExclusive
0x1800351b3  test    rbx, rbx
0x1800351b6  jz      loc_180035736
0x1800351bc  test    r13, r13
0x1800351bf  jz      loc_180035736
0x1800351c5  mov     r15d, r12d
0x1800351c8  mov     rcx, [rsi+50h]; this
0x1800351cc  cmp     r15w, [rcx+20h]
0x1800351d1  jnb     short loc_180035228
0x1800351d3  movzx   edx, r15w; unsigned __int16
0x1800351d7  call    ?QueryAttributeName@SCHEMA_ELEMENT@@QEAAPEBGG@Z; SCHEMA_ELEMENT::QueryAttributeName(ushort)
0x1800351dc  mov     rdx, rax
0x1800351df  mov     rcx, rbx
0x1800351e2  call    cs:__imp_?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z; IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)
0x1800351e8  test    al, al
0x1800351ea  jnz     short loc_1800351F2
0x1800351ec  inc     r15w
0x1800351f0  jmp     short loc_1800351C8
0x1800351f2  mov     rcx, [rsi+50h]; this
0x1800351f6  movzx   edx, r15w; unsigned __int16
0x1800351fa  call    ?QueryAttribute@SCHEMA_ELEMENT@@QEAAPEAVSCHEMA_ATTRIBUTE@@G@Z; SCHEMA_ELEMENT::QueryAttribute(ushort)
0x1800351ff  mov     r14, rax
0x180035202  test    rax, rax
0x180035205  jz      short loc_180035228
0x180035207  mov     rcx, rax; this
0x18003520a  call    ?QueryExtension@SCHEMA_ATTRIBUTE@@QEBAPEBGXZ; SCHEMA_ATTRIBUTE::QueryExtension(void)
0x18003520f  test    rax, rax
0x180035212  jz      short loc_180035228
0x180035214  mov     ecx, [rsi+88h]
0x18003521a  and     ecx, 0F0000h
0x180035220  cmp     ecx, 30000h
0x180035226  jz      short loc_18003529E
0x180035228  test    dword ptr [rsi+88h], 0F0000h
0x180035232  jz      short loc_18003529E
0x180035234  cmp     [rbp+1F0h+arg_20], r12d
0x18003523b  jnz     short loc_18003529E
0x18003523d  mov     ecx, 1E8h; Size
0x180035242  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035247  test    rax, rax
0x18003524a  jz      short loc_180035287
0x18003524c  mov     rcx, rax; this
0x18003524f  call    ??0VALIDATION_EXCEPTION@@QEAA@XZ; VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(void)
0x180035254  mov     [rsp+2F0h+var_2A0], rax
0x180035259  test    rax, rax
0x18003525c  jz      short loc_18003528C
0x18003525e  mov     ecx, [rsi+88h]
0x180035264  lea     r8, [rax+0D0h]
0x18003526b  shl     ecx, 0Ch
0x18003526e  sar     ecx, 1Ch
0x180035271  call    ?GetErrorIdFromEditMode@CONFIG_ELEMENT@@SAKW4ELEMENT_EDIT_MODE@@@Z; CONFIG_ELEMENT::GetErrorIdFromEditMode(ELEMENT_EDIT_MODE)
0x180035276  mov     ecx, eax; dwMessageId
0x180035278  lea     rdx, [rsp+2F0h+Arguments]; Arguments
0x18003527d  xor     r9d, r9d; struct SMALL_STRU *
0x180035280  call    ?AdminFormatMessage@@YAJKQEAPEBDPEAVSTRU@@PEAVSMALL_STRU@@@Z; AdminFormatMessage(ulong,char const * * const,STRU *,SMALL_STRU *)
0x180035285  jmp     short loc_18003528C
0x180035287  mov     [rsp+2F0h+var_2A0], r12
0x18003528c  mov     ebx, 80070021h
0x180035291  mov     r14, r12
0x180035294  mov     r15, [rsp+2F0h+SRWLock]
0x180035299  jmp     loc_18003573B
0x18003529e  mov     rax, [rsi+50h]
0x1800352a2  mov     r8d, 1
0x1800352a8  test    [rax+80h], r8b
0x1800352af  jz      loc_18003535E
0x1800352b5  test    r14, r14
0x1800352b8  jnz     loc_180035343
0x1800352be  lea     ecx, [r8+3Fh]; Size
0x1800352c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800352c7  mov     rdi, rax
0x1800352ca  test    rax, rax
0x1800352cd  jz      loc_18003536A
0x1800352d3  lea     r15d, [r14+1]
0x1800352d7  lock add cs:?g_cModuleRefs@@3JC, r15d; long volatile g_cModuleRefs
0x1800352df  mov     [rax+8], r12
0x1800352e3  mov     rdx, rbx; unsigned __int16 *
0x1800352e6  lea     rax, ??_7SCHEMA_ATTRIBUTE@@6B@; const SCHEMA_ATTRIBUTE::`vftable'
0x1800352ed  mov     [rdi+10h], r15
0x1800352f1  mov     [rdi], rax
0x1800352f4  mov     rcx, rdi; this
0x1800352f7  mov     [rdi+18h], r12
0x1800352fb  mov     [rdi+20h], r12
0x1800352ff  mov     [rdi+28h], r12d
0x180035303  mov     [rdi+30h], r12
0x180035307  mov     [rdi+38h], r12
0x18003530b  call    ?CreateGeneratedSchema@SCHEMA_ATTRIBUTE@@QEAAJPEBG@Z; SCHEMA_ATTRIBUTE::CreateGeneratedSchema(ushort const *)
0x180035310  mov     ebx, eax
0x180035312  test    eax, eax
0x180035314  js      loc_180035291
0x18003531a  mov     rcx, [rsi+50h]; this
0x18003531e  mov     rdx, rdi; struct SCHEMA_ATTRIBUTE *
0x180035321  call    ?AddAttribute@SCHEMA_ELEMENT@@QEAAJPEAVSCHEMA_ATTRIBUTE@@@Z; SCHEMA_ELEMENT::AddAttribute(SCHEMA_ATTRIBUTE *)
0x180035326  mov     ebx, eax
0x180035328  test    eax, eax
0x18003532a  js      loc_180035291
0x180035330  mov     rax, [rsi+50h]
0x180035334  mov     r14, rdi
0x180035337  movzx   ecx, word ptr [rax+20h]
0x18003533b  sub     cx, r15w
0x18003533f  movzx   r15d, cx
0x180035343  mov     rcx, rsi; this
0x180035346  call    ?SyncAttributeCountWithSchema@CONFIG_ELEMENT@@QEAAJXZ; CONFIG_ELEMENT::SyncAttributeCountWithSchema(void)
0x18003534b  mov     ebx, eax
0x18003534d  mov     rdi, r12
0x180035350  test    eax, eax
0x180035352  js      loc_180035598
0x180035358  mov     r8d, 1
0x18003535e  test    r14, r14
0x180035361  jnz     short loc_180035377
0x180035363  mov     ebx, 80070585h
0x180035368  jmp     short loc_18003536F
0x18003536a  mov     ebx, 80070008h
0x18003536f  mov     rdi, r12
0x180035372  jmp     loc_180035291
0x180035377  movzx   edx, r15w; unsigned __int16
0x18003537b  mov     rcx, rsi; this
0x18003537e  call    ?QueryAttributeAllowCommit@CONFIG_ELEMENT@@QEAAHG@Z; CONFIG_ELEMENT::QueryAttributeAllowCommit(ushort)
0x180035383  test    eax, eax
0x180035385  jnz     short loc_1800353CF
0x180035387  mov     ecx, 1E8h; Size
0x18003538c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035391  test    rax, rax
0x180035394  jz      short loc_1800353C3
0x180035396  mov     rcx, rax; this
0x180035399  call    ??0VALIDATION_EXCEPTION@@QEAA@XZ; VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(void)
0x18003539e  mov     [rsp+2F0h+var_2A0], rax
0x1800353a3  test    rax, rax
0x1800353a6  jz      short loc_1800353C8
0x1800353a8  lea     r8, [rax+0D0h]; struct STRU *
0x1800353af  xor     r9d, r9d; struct SMALL_STRU *
0x1800353b2  lea     rdx, [rsp+2F0h+Arguments]; Arguments
0x1800353b7  mov     ecx, 0C0000AA6h; dwMessageId
0x1800353bc  call    ?AdminFormatMessage@@YAJKQEAPEBDPEAVSTRU@@PEAVSMALL_STRU@@@Z; AdminFormatMessage(ulong,char const * * const,STRU *,SMALL_STRU *)
0x1800353c1  jmp     short loc_1800353C8
0x1800353c3  mov     [rsp+2F0h+var_2A0], r12
0x1800353c8  mov     ebx, 80070021h
0x1800353cd  jmp     short loc_18003536F
0x1800353cf  mov     eax, [r13+4]
0x1800353d3  shl     eax, 1Bh
0x1800353d6  sar     eax, 1Bh
0x1800353d9  cmp     eax, 2
0x1800353dc  jnz     short loc_180035429
0x1800353de  cmp     dword ptr [r14+28h], 6
0x1800353e3  jnz     short loc_1800353F8
0x1800353e5  mov     rdx, [r13+8]
0x1800353e9  mov     rcx, r13; this
0x1800353ec  mov     edx, [rdx]; unsigned int
0x1800353ee  call    ?SetEnum@ATTRIBUTE_VALUE@@QEAAJK@Z; ATTRIBUTE_VALUE::SetEnum(ulong)
0x1800353f3  jmp     loc_180035493
0x1800353f8  cmp     dword ptr [r14+28h], 5
0x1800353fd  jnz     short loc_180035412
0x1800353ff  mov     rdx, [r13+8]
0x180035403  mov     rcx, r13; this
0x180035406  mov     edx, [rdx]; unsigned int
0x180035408  call    ?SetFlags@ATTRIBUTE_VALUE@@QEAAJK@Z; ATTRIBUTE_VALUE::SetFlags(ulong)
0x18003540d  jmp     loc_180035493
0x180035412  cmp     dword ptr [r14+28h], 9
0x180035417  jnz     short loc_180035493
0x180035419  mov     rdx, [r13+8]
0x18003541d  mov     rcx, r13; this
0x180035420  mov     edx, [rdx]; unsigned int
0x180035422  call    ?SetUInt@ATTRIBUTE_VALUE@@QEAAJI@Z; ATTRIBUTE_VALUE::SetUInt(uint)
0x180035427  jmp     short loc_180035493
0x180035429  cmp     eax, r8d
0x18003542c  jnz     short loc_180035493
0x18003542e  cmp     [r14+28h], r8d
0x180035432  jz      short loc_180035493
0x180035434  mov     rdx, [r13+8]
0x180035438  lea     rcx, [rsp+2F0h+var_278]
0x18003543d  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180035443  mov     ebx, eax
0x180035445  mov     rdi, r12
0x180035448  test    eax, eax
0x18003544a  js      loc_180035598
0x180035450  lea     rcx, [rsp+2F0h+var_278]
0x180035455  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18003545b  mov     [rsp+2F0h+var_2C0], r12; int *
0x180035460  xor     r9d, r9d; struct CONFIG_FILE *
0x180035463  mov     rdx, rax; String1
0x180035466  mov     [rsp+2F0h+var_2C8], 2Ah ; '*'; unsigned int
0x18003546e  lea     rax, [rsp+2F0h+var_2A0]
0x180035473  mov     r8, r13; struct ATTRIBUTE_VALUE *
0x180035476  mov     rcx, r14; this
0x180035479  mov     [rsp+2F0h+var_2D0], rax; struct VALIDATION_EXCEPTION **
0x18003547e  call    ?CopyString@SCHEMA_ATTRIBUTE@@QEAAJPEBGPEAVATTRIBUTE_VALUE@@PEAVCONFIG_FILE@@PEAPEAVVALIDATION_EXCEPTION@@KPEAH@Z; SCHEMA_ATTRIBUTE::CopyString(ushort const *,ATTRIBUTE_VALUE *,CONFIG_FILE *,VALIDATION_EXCEPTION * *,ulong,int *)
0x180035483  mov     ebx, eax
0x180035485  test    eax, eax
0x180035487  js      loc_180035598
0x18003548d  mov     r12d, 1
0x180035493  mov     eax, [r13+4]
0x180035497  shl     eax, 1Bh
0x18003549a  sar     eax, 1Bh
0x18003549d  cmp     [r14+28h], eax
0x1800354a1  jz      short loc_1800354B7
0x1800354a3  cmp     [rsp+2F0h+var_298], 0
0x1800354a8  jnz     short loc_1800354B7
0x1800354aa  mov     ebx, 8007000Dh
0x1800354af  xor     r12d, r12d
0x1800354b2  jmp     loc_18003536F
0x1800354b7  lea     r8, [rsp+2F0h+var_278]; struct STRU *
0x1800354bc  mov     rdx, r13; struct ATTRIBUTE_VALUE *
0x1800354bf  mov     rcx, r14; this
0x1800354c2  call    ?CopyAttribute@SCHEMA_ATTRIBUTE@@QEAAJPEAVATTRIBUTE_VALUE@@PEAVSTRU@@@Z; SCHEMA_ATTRIBUTE::CopyAttribute(ATTRIBUTE_VALUE *,STRU *)
0x1800354c7  xor     edi, edi
0x1800354c9  mov     ebx, eax
0x1800354cb  test    eax, eax
0x1800354cd  js      loc_18003572E
0x1800354d3  xor     ebx, ebx
0x1800354d5  cmp     [rsp+2F0h+var_298], ebx
0x1800354d9  jnz     loc_1800355A2
0x1800354df  test    r12d, r12d
0x1800354e2  jnz     short loc_180035553
0x1800354e4  lea     ecx, [rdi+20h]; Size
0x1800354e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800354ec  mov     [rsp+2F0h+var_2B0], rax
0x1800354f1  mov     r12, rax
0x1800354f4  test    rax, rax
0x1800354f7  jz      short loc_180035546
0x1800354f9  lea     rcx, [rsp+2F0h+var_278]
0x1800354fe  mov     qword ptr [rax], 1
0x180035505  mov     [rax+8], rbx
0x180035509  mov     [rax+18h], rbx
0x18003550d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180035513  mov     [rsp+2F0h+var_2C0], rbx; int *
0x180035518  xor     r9d, r9d; struct CONFIG_FILE *
0x18003551b  mov     rdx, rax; String1
0x18003551e  mov     [rsp+2F0h+var_2C8], 2Ah ; '*'; unsigned int
0x180035526  lea     rax, [rsp+2F0h+var_2A0]
0x18003552b  mov     r8, r12; struct ATTRIBUTE_VALUE *
0x18003552e  mov     rcx, r14; this
0x180035531  mov     [rsp+2F0h+var_2D0], rax; struct VALIDATION_EXCEPTION **
0x180035536  call    ?CopyString@SCHEMA_ATTRIBUTE@@QEAAJPEBGPEAVATTRIBUTE_VALUE@@PEAVCONFIG_FILE@@PEAPEAVVALIDATION_EXCEPTION@@KPEAH@Z; SCHEMA_ATTRIBUTE::CopyString(ushort const *,ATTRIBUTE_VALUE *,CONFIG_FILE *,VALIDATION_EXCEPTION * *,ulong,int *)
0x18003553b  xor     r12d, r12d
0x18003553e  mov     ebx, eax
0x180035540  test    eax, eax
0x180035542  js      short loc_180035598
0x180035544  jmp     short loc_180035556
0x180035546  mov     ebx, 80070008h
0x18003554b  xor     r12d, r12d
0x18003554e  jmp     loc_180035291
0x180035553  xor     r12d, r12d
0x180035556  mov     rax, [r14+30h]
0x18003555a  test    rax, rax
0x18003555d  jz      short loc_1800355A5
0x18003555f  mov     rcx, [rax+10h]
0x180035563  test    rcx, rcx
0x180035566  jz      short loc_1800355A5
0x180035568  mov     rax, [rcx]
0x18003556b  lea     r9, [rsp+2F0h+var_2A0]
0x180035570  lea     r8, szDomain
0x180035577  mov     rdx, r13
0x18003557a  mov     rax, [rax+10h]
0x18003557e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035583  mov     ebx, eax
0x180035585  mov     rdi, r12
0x180035588  test    eax, eax
0x18003558a  js      short loc_180035598
0x18003558c  cmp     [rsp+2F0h+var_2A0], r12
0x180035591  jz      short loc_1800355A5
0x180035593  mov     ebx, 8007000Dh
0x180035598  mov     r14, [rsp+2F0h+var_2B0]
0x18003559d  jmp     loc_180035294
0x1800355a2  xor     r12d, r12d
0x1800355a5  movzx   edx, word ptr [rsi+26h]; unsigned __int16
  ... truncated ...
```
