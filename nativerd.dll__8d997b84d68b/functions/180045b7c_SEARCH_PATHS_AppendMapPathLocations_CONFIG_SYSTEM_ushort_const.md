# SEARCH_PATHS::AppendMapPathLocations(CONFIG_SYSTEM *,ushort const *)

- ea: `0x180045b7c`
- end: `0x1800461d9`
- name: `?AppendMapPathLocations@SEARCH_PATHS@@AEAAJPEAVCONFIG_SYSTEM@@PEBG@Z`
- size: `1629`
- prototype: `__int64 __fastcall(SEARCH_PATHS *__hidden this, struct CONFIG_SYSTEM *, wchar_t *String2)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x1800462b0`

## callees

- `0x18000c3f0`
- `0x180014b08`
- `0x180014b34`
- `0x180016440`
- `0x180017850`
- `0x1800266e4`
- `0x18002ff78`
- `0x1800307c4`
- `0x18003a620`
- `0x180045b7c`
- `0x1800461e0`
- `0x180046348`
- `0x1800463c8`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180046163`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180046170`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004617a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180046187`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180046191`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004619e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180046163`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180046170`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004617a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180046187`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180046191`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004619e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180045df3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180045e23`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180045e3c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180045ef1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180045f1d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180045f36`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180045fef`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004601b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180046035`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180045df3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180045e23`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180045e3c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180045ef1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180045f1d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180045f36`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180045fef`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004601b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180046035`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180045c2c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180045c51`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180045c84`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180045ca9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180045cde`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180045d03`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180045c2c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180045c51`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180045c84`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180045ca9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180045cde`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180045d03`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180045ddc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180045ddc`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180045eda`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180045fd8`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180045eda`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180045fd8`

## pseudocode

```c
__int64 __fastcall SEARCH_PATHS::AppendMapPathLocations(SEARCH_PATHS *this, struct CONFIG_SYSTEM *a2, wchar_t *String2)
{
  struct CONFIG_COLLECTION *v3; // rsi
  wchar_t *v4; // r13
  SEARCH_PATHS *v6; // r15
  struct CONFIG_COLLECTION *v7; // rdi
  int ConfigFile; // ebx
  struct CONFIG_COLLECTION *v9; // rdx
  __int64 v10; // r14
  unsigned int v11; // eax
  CONFIG_ELEMENT *v12; // r12
  const unsigned __int16 *Str; // rax
  wchar_t *v14; // rax
  const unsigned __int16 *v15; // rax
  int DefaultInternalCollection; // eax
  unsigned int v17; // eax
  __int64 v18; // r15
  CONFIG_ELEMENT *v19; // r14
  const unsigned __int16 *v20; // rax
  wchar_t *v21; // rax
  const unsigned __int16 *v22; // rax
  int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // r13
  CONFIG_ELEMENT *v26; // r15
  const unsigned __int16 *v27; // rax
  wchar_t *v28; // rax
  const unsigned __int16 *v29; // rax
  int appended; // eax
  int v32; // [rsp+30h] [rbp-D0h] BYREF
  struct CONFIG_COLLECTION *v33; // [rsp+38h] [rbp-C8h] BYREF
  struct CONFIG_COLLECTION *v34; // [rsp+40h] [rbp-C0h] BYREF
  struct ATTRIBUTE_ENTRY *v35; // [rsp+48h] [rbp-B8h] BYREF
  int v36; // [rsp+50h] [rbp-B0h]
  struct IAppHostConfigFile *v37; // [rsp+58h] [rbp-A8h] BYREF
  struct CONFIG_COLLECTION *v38; // [rsp+60h] [rbp-A0h] BYREF
  CONFIG_ELEMENT *v39; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v40; // [rsp+70h] [rbp-90h]
  SEARCH_PATHS *v41; // [rsp+78h] [rbp-88h]
  struct ATTRIBUTE_ENTRY *v42; // [rsp+80h] [rbp-80h] BYREF
  struct ATTRIBUTE_ENTRY *v43; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *String2a; // [rsp+90h] [rbp-70h]
  _QWORD v45[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v46; // [rsp+B0h] [rbp-50h]
  __int64 v47; // [rsp+B8h] [rbp-48h]
  __int128 v48; // [rsp+C0h] [rbp-40h]
  __int128 v49; // [rsp+D0h] [rbp-30h]
  _BYTE v50[56]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v51[56]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v52[56]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v53[56]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v54[56]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v55[56]; // [rsp+1F8h] [rbp+F8h] BYREF
  unsigned __int16 v56[256]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v57[256]; // [rsp+430h] [rbp+330h] BYREF
  unsigned __int16 v58[256]; // [rsp+630h] [rbp+530h] BYREF
  unsigned __int16 v59[256]; // [rsp+830h] [rbp+730h] BYREF
  unsigned __int16 v60[256]; // [rsp+A30h] [rbp+930h] BYREF
  unsigned __int16 v61[256]; // [rsp+C30h] [rbp+B30h] BYREF

  v3 = 0;
  String2a = String2;
  v4 = String2;
  v41 = this;
  v37 = 0;
  v6 = this;
  v45[1] = 1;
  v46 = 0;
  v45[0] = &PARSE_ERROR_INFO::`vftable';
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v39 = 0;
  v38 = 0;
  v35 = 0;
  memset_0(v56, 0, sizeof(v56));
  STRU::STRU((STRU *)v55, v56, 0x100u);
  memset_0(v57, 0, sizeof(v57));
  STRU::STRU((STRU *)v51, v57, 0x100u);
  v34 = 0;
  v43 = 0;
  v7 = 0;
  memset_0(v58, 0, sizeof(v58));
  STRU::STRU((STRU *)v54, v58, 0x100u);
  memset_0(v59, 0, sizeof(v59));
  STRU::STRU((STRU *)v50, v59, 0x100u);
  v32 = 0;
  v33 = 0;
  v42 = 0;
  memset_0(v60, 0, sizeof(v60));
  STRU::STRU((STRU *)v53, v60, 0x100u);
  memset_0(v61, 0, sizeof(v61));
  STRU::STRU((STRU *)v52, v61, 0x100u);
  ConfigFile = CONFIG_SYSTEM::GetConfigFile(a2, L"MACHINE/WEBROOT/APPHOST", &v37);
  if ( ConfigFile >= 0 )
  {
    if ( !v37 )
      goto LABEL_55;
    ConfigFile = CONFIG_FILE::GetConfigElement(
                   (CONFIG_FILE *)v37,
                   &szDomain,
                   L"system.applicationHost/sites",
                   &v39,
                   (struct PARSE_ERROR_INFO *)v45);
    if ( ConfigFile >= 0 )
    {
      ConfigFile = CONFIG_ELEMENT::GetDefaultInternalCollection(v39, &v38);
      if ( ConfigFile >= 0 )
      {
        v9 = v38;
        v10 = 0;
        v11 = *((_DWORD *)v38 + 8);
        v40 = v11;
        while ( 1 )
        {
          v36 = v10;
          if ( (unsigned int)v10 >= v11 )
            goto LABEL_49;
          v12 = *(CONFIG_ELEMENT **)(*((_QWORD *)v9 + 5) + 24 * v10);
          CONFIG_ELEMENT::ReferenceConfigElement(v12);
          ConfigFile = CONFIG_ELEMENT::GetAttributeEntry(v12, L"name", &v35, (struct STRU *)v55);
          if ( ConfigFile < 0 )
            goto LABEL_47;
          ConfigFile = STRU::Copy((STRU *)v51, L"MACHINE/WEBROOT/APPHOST");
          if ( ConfigFile < 0 )
            goto LABEL_47;
          Str = STRU::QueryStr((STRU *)v55);
          ConfigFile = SEARCH_PATHS::UpdateConfigPath((struct STRU *)v51, Str, &v32);
          if ( ConfigFile < 0 )
            goto LABEL_47;
          if ( !v32 )
            break;
          v14 = STRU::QueryStr((STRU *)v51);
          if ( (unsigned int)SEARCH_PATHS::IsSubPath(v4, v14) )
          {
            v15 = STRU::QueryStr((STRU *)v51);
            ConfigFile = SEARCH_PATHS::AppendSearchPath(v6, v15);
            if ( (int)(ConfigFile + 0x80000000) >= 0 && ConfigFile != -2147024713 )
              goto LABEL_47;
          }
          DefaultInternalCollection = CONFIG_ELEMENT::GetDefaultInternalCollection(v12, &v34);
          v7 = v34;
          ConfigFile = DefaultInternalCollection;
          if ( DefaultInternalCollection < 0 )
            goto LABEL_45;
          v17 = *((_DWORD *)v34 + 8);
          v18 = 0;
          LODWORD(v34) = v17;
LABEL_16:
          LODWORD(v35) = v18;
          if ( (unsigned int)v18 < v17 )
          {
            v19 = *(CONFIG_ELEMENT **)(*((_QWORD *)v7 + 5) + 24 * v18);
            CONFIG_ELEMENT::ReferenceConfigElement(v19);
            ConfigFile = CONFIG_ELEMENT::GetAttributeEntry(v19, L"path", &v43, (struct STRU *)v54);
            if ( ConfigFile >= 0 )
            {
              ConfigFile = STRU::Copy((STRU *)v50, (const struct STRU *)v51);
              if ( ConfigFile >= 0 )
              {
                v20 = STRU::QueryStr((STRU *)v54);
                ConfigFile = SEARCH_PATHS::UpdateConfigPath((struct STRU *)v50, v20, &v32);
                if ( ConfigFile >= 0 )
                {
                  if ( !v32
                    || (v21 = STRU::QueryStr((STRU *)v50), !(unsigned int)SEARCH_PATHS::IsSubPath(v4, v21))
                    || (v22 = STRU::QueryStr((STRU *)v50),
                        ConfigFile = SEARCH_PATHS::AppendSearchPath(v41, v22),
                        (int)(ConfigFile + 0x80000000) < 0)
                    || ConfigFile == -2147024713 )
                  {
                    v23 = CONFIG_ELEMENT::GetDefaultInternalCollection(v19, &v33);
                    v3 = v33;
                    ConfigFile = v23;
                    if ( v23 >= 0 )
                    {
                      v24 = *((_DWORD *)v33 + 8);
                      v25 = 0;
                      LODWORD(v33) = v24;
                      while ( 1 )
                      {
                        if ( (unsigned int)v25 >= v24 )
                        {
                          CONFIG_COLLECTION::DereferenceConfigCollection(v3);
                          v3 = 0;
                          v33 = 0;
                          CONFIG_ELEMENT::DereferenceConfigElement(v19);
                          v4 = String2a;
                          v18 = (unsigned int)((_DWORD)v35 + 1);
                          v17 = (unsigned int)v34;
                          v43 = 0;
                          goto LABEL_16;
                        }
                        v26 = *(CONFIG_ELEMENT **)(*((_QWORD *)v3 + 5) + 24 * v25);
                        CONFIG_ELEMENT::ReferenceConfigElement(v26);
                        ConfigFile = CONFIG_ELEMENT::GetAttributeEntry(v26, L"path", &v42, (struct STRU *)v53);
                        if ( ConfigFile < 0 )
                          break;
                        ConfigFile = STRU::Copy((STRU *)v52, (const struct STRU *)v50);
                        if ( ConfigFile < 0 )
                          break;
                        v27 = STRU::QueryStr((STRU *)v53);
                        ConfigFile = SEARCH_PATHS::UpdateConfigPath((struct STRU *)v52, v27, &v32);
                        if ( ConfigFile < 0 )
                          break;
                        if ( v32 )
                        {
                          v28 = STRU::QueryStr((STRU *)v52);
                          if ( (unsigned int)SEARCH_PATHS::IsSubPath(String2a, v28) )
                          {
                            v29 = STRU::QueryStr((STRU *)v52);
                            appended = SEARCH_PATHS::AppendSearchPath(v41, v29);
                            ConfigFile = appended;
                            if ( appended < 0 )
                            {
                              if ( appended != -2147024713 )
                                break;
                              ConfigFile = 0;
                            }
                          }
                        }
                        CONFIG_ELEMENT::DereferenceConfigElement(v26);
                        v24 = (unsigned int)v33;
                        v25 = (unsigned int)(v25 + 1);
                        v42 = 0;
                      }
                      if ( v26 )
                        CONFIG_ELEMENT::DereferenceConfigElement(v26);
                    }
LABEL_41:
                    if ( v3 )
                      CONFIG_COLLECTION::DereferenceConfigCollection(v3);
                  }
                }
              }
            }
            if ( v19 )
              CONFIG_ELEMENT::DereferenceConfigElement(v19);
LABEL_45:
            if ( v7 )
              CONFIG_COLLECTION::DereferenceConfigCollection(v7);
LABEL_47:
            if ( v12 )
              CONFIG_ELEMENT::DereferenceConfigElement(v12);
            goto LABEL_49;
          }
          CONFIG_COLLECTION::DereferenceConfigCollection(v7);
          v7 = 0;
          v34 = 0;
          CONFIG_ELEMENT::DereferenceConfigElement(v12);
          v9 = v38;
          v10 = (unsigned int)(v36 + 1);
          v6 = v41;
          v11 = v40;
          v35 = 0;
        }
        ConfigFile = -2147024883;
        v19 = 0;
        goto LABEL_41;
      }
LABEL_49:
      if ( v38 )
        CONFIG_COLLECTION::DereferenceConfigCollection(v38);
    }
    if ( v39 )
      CONFIG_ELEMENT::DereferenceConfigElement(v39);
  }
  if ( v37 )
    CONFIG_FILE::DereferenceConfigFile((CONFIG_FILE *)v37);
LABEL_55:
  STRU::~STRU((STRU *)v52);
  STRU::~STRU((STRU *)v53);
  STRU::~STRU((STRU *)v50);
  STRU::~STRU((STRU *)v54);
  STRU::~STRU((STRU *)v51);
  STRU::~STRU((STRU *)v55);
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((PARSE_ERROR_INFO *)v45);
  return (unsigned int)ConfigFile;
}

```

## disassembly

```asm
0x180045b7c  mov     [rsp-8+arg_18], rbx
0x180045b81  push    rbp
0x180045b82  push    rsi
0x180045b83  push    rdi
0x180045b84  push    r12
0x180045b86  push    r13
0x180045b88  push    r14
0x180045b8a  push    r15
0x180045b8c  lea     rbp, [rsp-0D40h]
0x180045b94  sub     rsp, 0E40h
0x180045b9b  mov     rax, cs:__security_cookie
0x180045ba2  xor     rax, rsp
0x180045ba5  mov     [rbp+0D70h+var_40], rax
0x180045bac  xor     esi, esi
0x180045bae  mov     [rbp+0D70h+String2], r8
0x180045bb2  mov     r13, r8
0x180045bb5  mov     [rsp+0E70h+var_DF8], rcx
0x180045bba  mov     rbx, rdx
0x180045bbd  mov     [rsp+0E70h+var_E18], rsi
0x180045bc2  mov     r15, rcx
0x180045bc5  mov     [rbp+0D70h+var_DC8], 1
0x180045bcd  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x180045bd4  mov     [rbp+0D70h+var_DC0], esi
0x180045bd7  xorps   xmm0, xmm0
0x180045bda  mov     [rbp+0D70h+var_DD0], rax
0x180045bde  xorps   xmm1, xmm1
0x180045be1  mov     [rbp+0D70h+var_DB8], rsi
0x180045be5  mov     r12d, 200h
0x180045beb  movdqa  [rbp+0D70h+var_DB0], xmm0
0x180045bf0  mov     r8d, r12d; Size
0x180045bf3  movdqa  [rbp+0D70h+var_DA0], xmm1
0x180045bf8  xor     edx, edx; Val
0x180045bfa  mov     [rsp+0E70h+var_E08], rsi
0x180045bff  lea     rcx, [rbp+0D70h+var_C40]; void *
0x180045c06  mov     [rsp+0E70h+var_E10], rsi
0x180045c0b  mov     [rsp+0E70h+var_E28], rsi
0x180045c10  call    memset_0
0x180045c15  mov     r14d, 100h
0x180045c1b  lea     rdx, [rbp+0D70h+var_C40]
0x180045c22  mov     r8d, r14d
0x180045c25  lea     rcx, [rbp+0D70h+var_C78]
0x180045c2c  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180045c32  mov     r8d, r12d; Size
0x180045c35  lea     rcx, [rbp+0D70h+var_A40]; void *
0x180045c3c  xor     edx, edx; Val
0x180045c3e  call    memset_0
0x180045c43  mov     r8d, r14d
0x180045c46  lea     rdx, [rbp+0D70h+var_A40]
0x180045c4d  lea     rcx, [rbp+0D70h+var_D58]
0x180045c51  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180045c57  mov     r8d, r12d; Size
0x180045c5a  mov     [rsp+0E70h+var_E30], rsi
0x180045c5f  xor     edx, edx; Val
0x180045c61  mov     [rbp+0D70h+var_DE8], rsi
0x180045c65  lea     rcx, [rbp+0D70h+var_840]; void *
0x180045c6c  mov     edi, esi
0x180045c6e  call    memset_0
0x180045c73  mov     r8d, r14d
0x180045c76  lea     rdx, [rbp+0D70h+var_840]
0x180045c7d  lea     rcx, [rbp+0D70h+var_CB0]
0x180045c84  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180045c8a  mov     r8d, r12d; Size
0x180045c8d  lea     rcx, [rbp+0D70h+var_640]; void *
0x180045c94  xor     edx, edx; Val
0x180045c96  call    memset_0
0x180045c9b  mov     r8d, r14d
0x180045c9e  lea     rdx, [rbp+0D70h+var_640]
0x180045ca5  lea     rcx, [rbp+0D70h+var_D90]
0x180045ca9  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180045caf  mov     r8d, r12d; Size
0x180045cb2  mov     [rsp+0E70h+var_E40], esi
0x180045cb6  xor     edx, edx; Val
0x180045cb8  mov     [rsp+0E70h+var_E38], rsi
0x180045cbd  lea     rcx, [rbp+0D70h+var_440]; void *
0x180045cc4  mov     [rbp+0D70h+var_DF0], rsi
0x180045cc8  call    memset_0
0x180045ccd  mov     r8d, r14d
0x180045cd0  lea     rdx, [rbp+0D70h+var_440]
0x180045cd7  lea     rcx, [rbp+0D70h+var_CE8]
0x180045cde  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180045ce4  mov     r8d, r12d; Size
0x180045ce7  lea     rcx, [rbp+0D70h+var_240]; void *
0x180045cee  xor     edx, edx; Val
0x180045cf0  call    memset_0
0x180045cf5  mov     r8d, r14d
0x180045cf8  lea     rdx, [rbp+0D70h+var_240]
0x180045cff  lea     rcx, [rbp+0D70h+var_D20]
0x180045d03  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180045d09  lea     r8, [rsp+0E70h+var_E18]; struct IAppHostConfigFile **
0x180045d0e  mov     rcx, rbx; this
0x180045d11  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180045d18  call    ?GetConfigFile@CONFIG_SYSTEM@@QEAAJPEAGPEAPEAUIAppHostConfigFile@@@Z; CONFIG_SYSTEM::GetConfigFile(ushort *,IAppHostConfigFile * *)
0x180045d1d  mov     ebx, eax
0x180045d1f  test    eax, eax
0x180045d21  js      loc_18004614D
0x180045d27  cmp     [rsp+0E70h+var_E18], rsi
0x180045d2c  jz      loc_18004615F
0x180045d32  mov     rcx, [rsp+0E70h+var_E18]; this
0x180045d37  lea     rax, [rbp+0D70h+var_DD0]
0x180045d3b  lea     r9, [rsp+0E70h+var_E08]; struct CONFIG_ELEMENT **
0x180045d40  mov     [rsp+0E70h+var_E50], rax; struct PARSE_ERROR_INFO *
0x180045d45  lea     r8, aSystemApplicat_4; "system.applicationHost/sites"
0x180045d4c  lea     rdx, szDomain; unsigned __int16 *
0x180045d53  call    ?GetConfigElement@CONFIG_FILE@@QEAAJPEBG0PEAPEAVCONFIG_ELEMENT@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_FILE::GetConfigElement(ushort const *,ushort const *,CONFIG_ELEMENT * *,PARSE_ERROR_INFO *)
0x180045d58  mov     ebx, eax
0x180045d5a  test    eax, eax
0x180045d5c  js      loc_18004613B
0x180045d62  mov     rcx, [rsp+0E70h+var_E08]; this
0x180045d67  lea     rdx, [rsp+0E70h+var_E10]; struct CONFIG_COLLECTION **
0x180045d6c  call    ?GetDefaultInternalCollection@CONFIG_ELEMENT@@QEAAJPEAPEAVCONFIG_COLLECTION@@@Z; CONFIG_ELEMENT::GetDefaultInternalCollection(CONFIG_COLLECTION * *)
0x180045d71  mov     ebx, eax
0x180045d73  test    eax, eax
0x180045d75  js      loc_180046129
0x180045d7b  mov     rdx, [rsp+0E70h+var_E10]
0x180045d80  xor     r14d, r14d
0x180045d83  mov     eax, [rdx+20h]
0x180045d86  mov     [rsp+0E70h+var_E00], eax
0x180045d8a  mov     [rsp+0E70h+var_E20], r14d
0x180045d8f  cmp     r14d, eax
0x180045d92  jnb     loc_180046129
0x180045d98  mov     rax, [rdx+28h]
0x180045d9c  lea     rcx, [r14+r14*2]
0x180045da0  mov     r12, [rax+rcx*8]
0x180045da4  mov     rcx, r12; this
0x180045da7  call    ?ReferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::ReferenceConfigElement(void)
0x180045dac  lea     r9, [rbp+0D70h+var_C78]; struct STRU *
0x180045db3  mov     rcx, r12; this
0x180045db6  lea     r8, [rsp+0E70h+var_E28]; struct ATTRIBUTE_ENTRY **
0x180045dbb  lea     rdx, aName; "name"
0x180045dc2  call    ?GetAttributeEntry@CONFIG_ELEMENT@@QEAAJPEBGPEAPEAUATTRIBUTE_ENTRY@@PEAVSTRU@@@Z; CONFIG_ELEMENT::GetAttributeEntry(ushort const *,ATTRIBUTE_ENTRY * *,STRU *)
0x180045dc7  mov     ebx, eax
0x180045dc9  test    eax, eax
0x180045dcb  js      loc_18004611C
0x180045dd1  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180045dd8  lea     rcx, [rbp+0D70h+var_D58]
0x180045ddc  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180045de2  mov     ebx, eax
0x180045de4  test    eax, eax
0x180045de6  js      loc_18004611C
0x180045dec  lea     rcx, [rbp+0D70h+var_C78]
0x180045df3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180045df9  mov     rdx, rax; unsigned __int16 *
0x180045dfc  lea     r8, [rsp+0E70h+var_E40]; int *
0x180045e01  lea     rcx, [rbp+0D70h+var_D58]; struct STRU *
0x180045e05  call    ?UpdateConfigPath@SEARCH_PATHS@@CAJPEAVSTRU@@PEBGPEAH@Z; SEARCH_PATHS::UpdateConfigPath(STRU *,ushort const *,int *)
0x180045e0a  mov     ebx, eax
0x180045e0c  test    eax, eax
0x180045e0e  js      loc_18004611C
0x180045e14  cmp     [rsp+0E70h+var_E40], 0
0x180045e19  jz      loc_1800460ED
0x180045e1f  lea     rcx, [rbp+0D70h+var_D58]
0x180045e23  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180045e29  mov     rdx, rax; String1
0x180045e2c  mov     rcx, r13; String2
0x180045e2f  call    ?IsSubPath@SEARCH_PATHS@@CAHPEBG0@Z; SEARCH_PATHS::IsSubPath(ushort const *,ushort const *)
0x180045e34  test    eax, eax
0x180045e36  jz      short loc_180045E66
0x180045e38  lea     rcx, [rbp+0D70h+var_D58]
0x180045e3c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180045e42  mov     rdx, rax; unsigned __int16 *
0x180045e45  mov     rcx, r15; this
0x180045e48  call    ?AppendSearchPath@SEARCH_PATHS@@QEAAJPEBG@Z; SEARCH_PATHS::AppendSearchPath(ushort const *)
0x180045e4d  mov     ecx, 80000000h
0x180045e52  mov     ebx, eax
0x180045e54  add     eax, ecx
0x180045e56  test    ecx, eax
0x180045e58  jnz     short loc_180045E66
0x180045e5a  cmp     ebx, 800700B7h
0x180045e60  jnz     loc_18004611C
0x180045e66  lea     rdx, [rsp+0E70h+var_E30]; struct CONFIG_COLLECTION **
0x180045e6b  mov     rcx, r12; this
0x180045e6e  call    ?GetDefaultInternalCollection@CONFIG_ELEMENT@@QEAAJPEAPEAVCONFIG_COLLECTION@@@Z; CONFIG_ELEMENT::GetDefaultInternalCollection(CONFIG_COLLECTION * *)
0x180045e73  mov     rdi, [rsp+0E70h+var_E30]
0x180045e78  mov     ebx, eax
0x180045e7a  test    eax, eax
0x180045e7c  js      loc_18004610F
0x180045e82  mov     eax, [rdi+20h]
0x180045e85  xor     r15d, r15d
0x180045e88  mov     dword ptr [rsp+0E70h+var_E30], eax
0x180045e8c  mov     dword ptr [rsp+0E70h+var_E28], r15d
0x180045e91  cmp     r15d, eax
0x180045e94  jnb     loc_1800460A7
0x180045e9a  mov     rax, [rdi+28h]
0x180045e9e  lea     rcx, [r15+r15*2]
0x180045ea2  mov     r14, [rax+rcx*8]
0x180045ea6  mov     rcx, r14; this
0x180045ea9  call    ?ReferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::ReferenceConfigElement(void)
0x180045eae  lea     r9, [rbp+0D70h+var_CB0]; struct STRU *
0x180045eb5  mov     rcx, r14; this
0x180045eb8  lea     r8, [rbp+0D70h+var_DE8]; struct ATTRIBUTE_ENTRY **
0x180045ebc  lea     rdx, aPath; "path"
0x180045ec3  call    ?GetAttributeEntry@CONFIG_ELEMENT@@QEAAJPEBGPEAPEAUATTRIBUTE_ENTRY@@PEAVSTRU@@@Z; CONFIG_ELEMENT::GetAttributeEntry(ushort const *,ATTRIBUTE_ENTRY * *,STRU *)
0x180045ec8  mov     ebx, eax
0x180045eca  test    eax, eax
0x180045ecc  js      loc_180046102
0x180045ed2  lea     rdx, [rbp+0D70h+var_D58]
0x180045ed6  lea     rcx, [rbp+0D70h+var_D90]
0x180045eda  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180045ee0  mov     ebx, eax
0x180045ee2  test    eax, eax
0x180045ee4  js      loc_180046102
0x180045eea  lea     rcx, [rbp+0D70h+var_CB0]
0x180045ef1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180045ef7  mov     rdx, rax; unsigned __int16 *
0x180045efa  lea     r8, [rsp+0E70h+var_E40]; int *
0x180045eff  lea     rcx, [rbp+0D70h+var_D90]; struct STRU *
0x180045f03  call    ?UpdateConfigPath@SEARCH_PATHS@@CAJPEAVSTRU@@PEBGPEAH@Z; SEARCH_PATHS::UpdateConfigPath(STRU *,ushort const *,int *)
0x180045f08  mov     ebx, eax
0x180045f0a  test    eax, eax
0x180045f0c  js      loc_180046102
0x180045f12  cmp     [rsp+0E70h+var_E40], 0
0x180045f17  jz      short loc_180045F62
0x180045f19  lea     rcx, [rbp+0D70h+var_D90]
0x180045f1d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180045f23  mov     rdx, rax; String1
0x180045f26  mov     rcx, r13; String2
0x180045f29  call    ?IsSubPath@SEARCH_PATHS@@CAHPEBG0@Z; SEARCH_PATHS::IsSubPath(ushort const *,ushort const *)
0x180045f2e  test    eax, eax
0x180045f30  jz      short loc_180045F62
0x180045f32  lea     rcx, [rbp+0D70h+var_D90]
0x180045f36  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180045f3c  mov     rcx, [rsp+0E70h+var_DF8]; this
0x180045f41  mov     rdx, rax; unsigned __int16 *
0x180045f44  call    ?AppendSearchPath@SEARCH_PATHS@@QEAAJPEBG@Z; SEARCH_PATHS::AppendSearchPath(ushort const *)
0x180045f49  mov     ecx, 80000000h
0x180045f4e  mov     ebx, eax
0x180045f50  add     eax, ecx
0x180045f52  test    ecx, eax
0x180045f54  jnz     short loc_180045F62
0x180045f56  cmp     ebx, 800700B7h
0x180045f5c  jnz     loc_180046102
0x180045f62  lea     rdx, [rsp+0E70h+var_E38]; struct CONFIG_COLLECTION **
0x180045f67  mov     rcx, r14; this
0x180045f6a  call    ?GetDefaultInternalCollection@CONFIG_ELEMENT@@QEAAJPEAPEAVCONFIG_COLLECTION@@@Z; CONFIG_ELEMENT::GetDefaultInternalCollection(CONFIG_COLLECTION * *)
0x180045f6f  mov     rsi, [rsp+0E70h+var_E38]
0x180045f74  mov     ebx, eax
0x180045f76  test    eax, eax
0x180045f78  js      loc_1800460F5
0x180045f7e  mov     eax, [rsi+20h]
0x180045f81  xor     r13d, r13d
0x180045f84  mov     dword ptr [rsp+0E70h+var_E38], eax
0x180045f88  cmp     r13d, eax
0x180045f8b  jnb     loc_180046077
0x180045f91  mov     rax, [rsi+28h]
0x180045f95  lea     rcx, ds:0[r13*2]
0x180045f9d  add     rcx, r13
0x180045fa0  mov     r15, [rax+rcx*8]
0x180045fa4  mov     rcx, r15; this
0x180045fa7  call    ?ReferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::ReferenceConfigElement(void)
0x180045fac  lea     r9, [rbp+0D70h+var_CE8]; struct STRU *
0x180045fb3  mov     rcx, r15; this
0x180045fb6  lea     r8, [rbp+0D70h+var_DF0]; struct ATTRIBUTE_ENTRY **
0x180045fba  lea     rdx, aPath; "path"
0x180045fc1  call    ?GetAttributeEntry@CONFIG_ELEMENT@@QEAAJPEBGPEAPEAUATTRIBUTE_ENTRY@@PEAVSTRU@@@Z; CONFIG_ELEMENT::GetAttributeEntry(ushort const *,ATTRIBUTE_ENTRY * *,STRU *)
0x180045fc6  mov     ebx, eax
0x180045fc8  test    eax, eax
0x180045fca  js      loc_1800460DE
0x180045fd0  lea     rdx, [rbp+0D70h+var_D90]
0x180045fd4  lea     rcx, [rbp+0D70h+var_D20]
0x180045fd8  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180045fde  mov     ebx, eax
0x180045fe0  test    eax, eax
0x180045fe2  js      loc_1800460DE
0x180045fe8  lea     rcx, [rbp+0D70h+var_CE8]
0x180045fef  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180045ff5  mov     rdx, rax; unsigned __int16 *
0x180045ff8  lea     r8, [rsp+0E70h+var_E40]; int *
0x180045ffd  lea     rcx, [rbp+0D70h+var_D20]; struct STRU *
0x180046001  call    ?UpdateConfigPath@SEARCH_PATHS@@CAJPEAVSTRU@@PEBGPEAH@Z; SEARCH_PATHS::UpdateConfigPath(STRU *,ushort const *,int *)
0x180046006  mov     ebx, eax
0x180046008  test    eax, eax
0x18004600a  js      loc_1800460DE
0x180046010  cmp     [rsp+0E70h+var_E40], 0
0x180046015  jz      short loc_18004605B
0x180046017  lea     rcx, [rbp+0D70h+var_D20]
0x18004601b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180046021  mov     rcx, [rbp+0D70h+String2]; String2
0x180046025  mov     rdx, rax; String1
0x180046028  call    ?IsSubPath@SEARCH_PATHS@@CAHPEBG0@Z; SEARCH_PATHS::IsSubPath(ushort const *,ushort const *)
0x18004602d  test    eax, eax
0x18004602f  jz      short loc_18004605B
0x180046031  lea     rcx, [rbp+0D70h+var_D20]
0x180046035  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004603b  mov     rcx, [rsp+0E70h+var_DF8]; this
0x180046040  mov     rdx, rax; unsigned __int16 *
0x180046043  call    ?AppendSearchPath@SEARCH_PATHS@@QEAAJPEBG@Z; SEARCH_PATHS::AppendSearchPath(ushort const *)
0x180046048  mov     ebx, eax
0x18004604a  test    eax, eax
0x18004604c  jns     short loc_18004605B
0x18004604e  cmp     eax, 800700B7h
0x180046053  jnz     loc_1800460DE
0x180046059  xor     ebx, ebx
0x18004605b  mov     rcx, r15; this
0x18004605e  call    ?DereferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::DereferenceConfigElement(void)
0x180046063  mov     eax, dword ptr [rsp+0E70h+var_E38]
0x180046067  inc     r13d
0x18004606a  mov     [rbp+0D70h+var_DF0], 0
0x180046072  jmp     loc_180045F88
0x180046077  mov     rcx, rsi; this
0x18004607a  call    ?DereferenceConfigCollection@CONFIG_COLLECTION@@QEAAXXZ; CONFIG_COLLECTION::DereferenceConfigCollection(void)
  ... truncated ...
```
