# GRANULAR_CHANGE_LIST::GetSitesSectionChanges(CONFIG_FILE *,CONFIG_FILE *,int *)

- ea: `0x180055664`
- end: `0x180055ae8`
- name: `?GetSitesSectionChanges@GRANULAR_CHANGE_LIST@@AEAAJPEAVCONFIG_FILE@@0PEAH@Z`
- size: `1156`
- prototype: `int(GRANULAR_CHANGE_LIST *__hidden this, struct CONFIG_FILE *, struct CONFIG_FILE *, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x180055af0`

## callees

- `0x180014b08`
- `0x180014b34`
- `0x180016440`
- `0x18001c250`
- `0x1800266e4`
- `0x18002ff78`
- `0x1800306c0`
- `0x1800307c4`
- `0x180031d00`
- `0x18003219c`
- `0x1800541c4`
- `0x180054328`
- `0x1800551cc`
- `0x180055664`
- `0x18005b010`

## import_xrefs

- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180055994`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180055994`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180055a0a`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180055a0a`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180055964`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180055964`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800558ee`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800558ee`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800558b3`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800558b3`

## string_xrefs

- `0x1800556e5`: `virtualDirectoryDefaults`

## pseudocode

```c
__int64 __fastcall GRANULAR_CHANGE_LIST::GetSitesSectionChanges(
        GRANULAR_CHANGE_LIST *this,
        struct CONFIG_FILE *a2,
        struct CONFIG_FILE *a3,
        int *a4)
{
  CONFIG_ELEMENT *v4; // r12
  CONFIG_ELEMENT *v5; // rdi
  CONFIG_ELEMENT *v6; // r15
  struct CONFIG_COLLECTION *v7; // r13
  CONFIG_ELEMENT *v8; // rbx
  _QWORD *v9; // rsi
  int v10; // eax
  __int64 i; // r14
  const unsigned __int16 *v12; // rdi
  int ChildElement; // eax
  _QWORD *v14; // rax
  __int64 j; // r14
  signed int inserted; // eax
  __int64 v17; // r14
  unsigned int v18; // ebx
  int ConfigElement; // [rsp+58h] [rbp-79h] BYREF
  struct CONFIG_ELEMENT *v21; // [rsp+60h] [rbp-71h] BYREF
  CONFIG_ELEMENT *v22; // [rsp+68h] [rbp-69h] BYREF
  unsigned int v23; // [rsp+70h] [rbp-61h] BYREF
  struct CONFIG_ELEMENT *v24; // [rsp+78h] [rbp-59h] BYREF
  struct CONFIG_COLLECTION *v25[2]; // [rsp+80h] [rbp-51h] BYREF
  CONFIG_ELEMENT *v26; // [rsp+90h] [rbp-41h] BYREF
  struct CONFIG_COLLECTION *v27; // [rsp+98h] [rbp-39h] BYREF
  unsigned __int16 *v28; // [rsp+A0h] [rbp-31h] BYREF
  const wchar_t *v29; // [rsp+A8h] [rbp-29h]
  struct CONFIG_COLLECTION **v30; // [rsp+B0h] [rbp-21h]
  _QWORD v31[2]; // [rsp+B8h] [rbp-19h] BYREF
  int v32; // [rsp+C8h] [rbp-9h]
  __int64 v33; // [rsp+D0h] [rbp-1h]
  __int128 v34; // [rsp+D8h] [rbp+7h]
  __int128 v35; // [rsp+E8h] [rbp+17h]

  v4 = 0;
  v26 = 0;
  v22 = 0;
  v31[0] = &PARSE_ERROR_INFO::`vftable';
  v31[1] = 1;
  v28 = L"siteDefaults";
  v32 = 0;
  v29 = L"applicationDefaults";
  v33 = 0;
  v30 = (struct CONFIG_COLLECTION **)L"virtualDirectoryDefaults";
  v34 = 0;
  v5 = 0;
  v35 = 0;
  v6 = 0;
  v24 = 0;
  v7 = 0;
  v21 = 0;
  v8 = 0;
  v27 = 0;
  v25[0] = 0;
  v23 = 0;
  v9 = 0;
  ConfigElement = CONFIG_FILE::GetConfigElement(
                    a2,
                    L"MACHINE/WEBROOT/APPHOST",
                    L"system.applicationHost/sites",
                    &v26,
                    (struct PARSE_ERROR_INFO *)v31);
  if ( ConfigElement >= 0 )
  {
    v10 = CONFIG_FILE::GetConfigElement(
            a3,
            L"MACHINE/WEBROOT/APPHOST",
            L"system.applicationHost/sites",
            &v22,
            (struct PARSE_ERROR_INFO *)v31);
    v4 = v22;
    ConfigElement = v10;
    if ( v10 >= 0 )
    {
      for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
      {
        v12 = (&v28)[i];
        LODWORD(v22) = 1;
        ConfigElement = CONFIG_ELEMENT::GetChildElement(v26, v12, &v24);
        if ( ConfigElement < 0 )
        {
          v5 = v24;
          goto LABEL_35;
        }
        ChildElement = CONFIG_ELEMENT::GetChildElement(v4, v12, &v21);
        v6 = v21;
        v5 = v24;
        ConfigElement = ChildElement;
        if ( ChildElement < 0 )
          goto LABEL_35;
        ConfigElement = CONFIG_ELEMENT::IsEqual(v24, v21, (int *)&v22, 0);
        if ( ConfigElement < 0 )
          goto LABEL_35;
        CONFIG_ELEMENT::DereferenceConfigElement(v5);
        v5 = 0;
        v24 = 0;
        CONFIG_ELEMENT::DereferenceConfigElement(v6);
        v6 = 0;
        v21 = 0;
        if ( !(_DWORD)v22 )
        {
          *a4 = 1;
          goto LABEL_36;
        }
      }
      ConfigElement = CONFIG_ELEMENT::GetDefaultInternalCollection(v26, &v27);
      if ( ConfigElement >= 0 )
      {
        ConfigElement = CONFIG_ELEMENT::GetDefaultInternalCollection(v4, v25);
        if ( ConfigElement >= 0 )
        {
          v14 = operator new(0x50u);
          v9 = v14;
          if ( v14 )
          {
            CLKRHashTable::CLKRHashTable(
              (CLKRHashTable *)(v14 + 1),
              "SIMPLE_SITE_ID_TABLE",
              (unsigned __int64 (*)(const void *))CTypedHashTable<SIMPLE_SITE_ID_TABLE,CONFIG_ELEMENT,unsigned long,CLKRHashTable>::_ExtractKey,
              (unsigned int (*)(unsigned __int64))CTypedHashTable<SIMPLE_SITE_ID_TABLE,CONFIG_ELEMENT,unsigned long,CLKRHashTable>::_CalcKeyHash,
              (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<SIMPLE_SITE_ID_TABLE,CONFIG_ELEMENT,unsigned long,CLKRHashTable>::_EqualKeys,
              (void (*)(const void *, int))CTypedHashTable<SIMPLE_SITE_ID_TABLE,CONFIG_ELEMENT,unsigned long,CLKRHashTable>::_AddRefRecord,
              4.0,
              1u,
              0,
              0);
            v7 = v25[0];
            *v9 = &SIMPLE_SITE_ID_TABLE::`vftable';
            for ( j = 0; (unsigned int)j < *((_DWORD *)v7 + 8); j = (unsigned int)(j + 1) )
            {
              v8 = *(CONFIG_ELEMENT **)(*((_QWORD *)v7 + 5) + 24 * j);
              CONFIG_ELEMENT::ReferenceConfigElement(v8);
              inserted = CLKRHashTable::InsertRecord(v9 + 1, v8, 0);
              if ( inserted )
              {
                if ( inserted > 0 )
                  inserted = (unsigned __int16)inserted | 0x80070000;
                ConfigElement = inserted;
                goto LABEL_35;
              }
              CONFIG_ELEMENT::DereferenceConfigElement(v8);
            }
            v17 = 0;
            v8 = 0;
            while ( (unsigned int)v17 < *((_DWORD *)v27 + 8) )
            {
              v21 = *(struct CONFIG_ELEMENT **)(*((_QWORD *)v27 + 5) + 24 * v17);
              ConfigElement = CONFIG_ELEMENT::GetSiteIdInternal(v21, &v23);
              if ( ConfigElement < 0 )
                goto LABEL_35;
              v25[0] = 0;
              CLKRHashTable::FindKey(v9 + 1, v23, v25);
              v8 = v25[0];
              if ( v25[0] )
              {
                CLKRHashTable::DeleteRecord(v9 + 1, v25[0]);
                ConfigElement = GRANULAR_CHANGE_LIST::GetSiteElementChanges(this, v21, v8);
                if ( ConfigElement < 0 )
                  goto LABEL_35;
                CONFIG_ELEMENT::DereferenceConfigElement(v8);
                v8 = 0;
              }
              else
              {
                ConfigElement = GRANULAR_CHANGE_LIST::AppendChangedSite(this, v21);
                if ( ConfigElement < 0 )
                  goto LABEL_35;
              }
              v17 = (unsigned int)(v17 + 1);
            }
            if ( *((int *)this + 1) >= 2 )
            {
              v25[0] = this;
              v25[1] = (struct CONFIG_COLLECTION *)&ConfigElement;
              v28 = 0;
              v29 = (const wchar_t *)&SIMPLE_SITE_ID_TABLE::AddToGranularChangeListIfSiteChanged;
              v30 = v25;
              CLKRHashTable::Apply(
                v9 + 1,
                CTypedHashTable<SIMPLE_SITE_ID_TABLE,CONFIG_ELEMENT,unsigned long,CLKRHashTable>::_Action,
                &v28,
                1);
            }
            goto LABEL_35;
          }
          ConfigElement = -2147024888;
          v9 = 0;
        }
        v7 = v25[0];
      }
    }
  }
LABEL_35:
  if ( *a4 )
LABEL_36:
    ConfigElement = GRANULAR_CHANGE_LIST::AppendChangedPath(this, L"MACHINE/WEBROOT/APPHOST", 0, 1);
  if ( v9 )
    (*(void (__fastcall **)(_QWORD *, __int64))*v9)(v9, 1);
  if ( v27 )
    CONFIG_COLLECTION::DereferenceConfigCollection(v27);
  if ( v7 )
    CONFIG_COLLECTION::DereferenceConfigCollection(v7);
  if ( v5 )
    CONFIG_ELEMENT::DereferenceConfigElement(v5);
  if ( v6 )
    CONFIG_ELEMENT::DereferenceConfigElement(v6);
  if ( v26 )
    CONFIG_ELEMENT::DereferenceConfigElement(v26);
  if ( v4 )
    CONFIG_ELEMENT::DereferenceConfigElement(v4);
  if ( v8 )
    CONFIG_ELEMENT::DereferenceConfigElement(v8);
  v18 = ConfigElement;
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((PARSE_ERROR_INFO *)v31);
  return v18;
}

```

## disassembly

```asm
0x180055664  mov     rax, rsp
0x180055667  mov     [rax+10h], rbx
0x18005566b  mov     [rax+20h], r9
0x18005566f  mov     [rax+18h], r8
0x180055673  mov     [rax+8], rcx
0x180055677  push    rbp
0x180055678  push    rsi
0x180055679  push    rdi
0x18005567a  push    r12
0x18005567c  push    r13
0x18005567e  push    r14
0x180055680  push    r15
0x180055682  lea     rbp, [rax-5Fh]
0x180055686  sub     rsp, 0F0h
0x18005568d  mov     rax, rdx
0x180055690  mov     [rbp+57h+var_D0], 0
0x180055697  xor     r12d, r12d
0x18005569a  mov     [rbp+57h+var_98], 0
0x1800556a2  lea     rcx, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x1800556a9  mov     [rbp+57h+var_C0], r12
0x1800556ad  mov     [rbp+57h+var_70], rcx
0x1800556b1  lea     r9, [rbp+57h+var_98]; struct CONFIG_ELEMENT **
0x1800556b5  lea     rcx, aSitedefaults; "siteDefaults"
0x1800556bc  mov     [rbp+57h+var_68], 1
0x1800556c4  mov     [rbp+57h+var_88], rcx
0x1800556c8  lea     r8, aSystemApplicat_4; "system.applicationHost/sites"
0x1800556cf  lea     rcx, aApplicationdef; "applicationDefaults"
0x1800556d6  mov     [rbp+57h+var_60], r12d
0x1800556da  mov     [rbp+57h+var_80], rcx
0x1800556de  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800556e5  lea     rcx, aVirtualdirecto; "virtualDirectoryDefaults"
0x1800556ec  mov     [rbp+57h+var_58], r12
0x1800556f0  mov     [rbp+57h+var_78], rcx
0x1800556f4  xorps   xmm0, xmm0
0x1800556f7  lea     rcx, [rbp+57h+var_70]
0x1800556fb  movdqa  [rbp+57h+var_50], xmm0
0x180055700  mov     [rsp+120h+var_100], rcx; struct PARSE_ERROR_INFO *
0x180055705  xorps   xmm1, xmm1
0x180055708  xor     edi, edi
0x18005570a  movdqa  [rbp+57h+var_40], xmm1
0x18005570f  xor     r15d, r15d
0x180055712  mov     [rbp+57h+var_B0], rdi
0x180055716  xor     r13d, r13d
0x180055719  mov     [rbp+57h+var_C8], r15
0x18005571d  xor     ebx, ebx
0x18005571f  mov     [rbp+57h+var_90], rdi
0x180055723  mov     rcx, rax; this
0x180055726  mov     [rbp+57h+var_A8], r13
0x18005572a  mov     [rbp+57h+var_B8], ebx
0x18005572d  xor     esi, esi
0x18005572f  call    ?GetConfigElement@CONFIG_FILE@@QEAAJPEBG0PEAPEAVCONFIG_ELEMENT@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_FILE::GetConfigElement(ushort const *,ushort const *,CONFIG_ELEMENT * *,PARSE_ERROR_INFO *)
0x180055734  mov     [rbp+57h+var_D0], eax
0x180055737  test    eax, eax
0x180055739  js      loc_180055A1F
0x18005573f  mov     rcx, [rbp+57h+arg_10]; this
0x180055743  lea     rax, [rbp+57h+var_70]
0x180055747  lea     r9, [rbp+57h+var_C0]; struct CONFIG_ELEMENT **
0x18005574b  mov     [rsp+120h+var_100], rax; struct PARSE_ERROR_INFO *
0x180055750  lea     r8, aSystemApplicat_4; "system.applicationHost/sites"
0x180055757  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18005575e  call    ?GetConfigElement@CONFIG_FILE@@QEAAJPEBG0PEAPEAVCONFIG_ELEMENT@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_FILE::GetConfigElement(ushort const *,ushort const *,CONFIG_ELEMENT * *,PARSE_ERROR_INFO *)
0x180055763  mov     r12, [rbp+57h+var_C0]
0x180055767  mov     [rbp+57h+var_D0], eax
0x18005576a  test    eax, eax
0x18005576c  js      loc_180055A1F
0x180055772  xor     r14d, r14d
0x180055775  mov     rcx, [rbp+57h+var_98]; this
0x180055779  cmp     r14d, 3
0x18005577d  jnb     loc_180055823
0x180055783  mov     rdi, [rbp+r14*8+57h+var_88]
0x180055788  lea     r8, [rbp+57h+var_B0]; struct CONFIG_ELEMENT **
0x18005578c  mov     rdx, rdi; unsigned __int16 *
0x18005578f  mov     dword ptr [rbp+57h+var_C0], 1
0x180055796  call    ?GetChildElement@CONFIG_ELEMENT@@QEAAJPEBGPEAPEAV1@@Z; CONFIG_ELEMENT::GetChildElement(ushort const *,CONFIG_ELEMENT * *)
0x18005579b  mov     [rbp+57h+var_D0], eax
0x18005579e  test    eax, eax
0x1800557a0  js      short loc_18005581A
0x1800557a2  lea     r8, [rbp+57h+var_C8]; struct CONFIG_ELEMENT **
0x1800557a6  mov     rdx, rdi; unsigned __int16 *
0x1800557a9  mov     rcx, r12; this
0x1800557ac  call    ?GetChildElement@CONFIG_ELEMENT@@QEAAJPEBGPEAPEAV1@@Z; CONFIG_ELEMENT::GetChildElement(ushort const *,CONFIG_ELEMENT * *)
0x1800557b1  mov     r15, [rbp+57h+var_C8]
0x1800557b5  mov     rdi, [rbp+57h+var_B0]
0x1800557b9  mov     [rbp+57h+var_D0], eax
0x1800557bc  test    eax, eax
0x1800557be  js      loc_180055A1F
0x1800557c4  xor     r9d, r9d; int
0x1800557c7  lea     r8, [rbp+57h+var_C0]; int *
0x1800557cb  mov     rdx, r15; struct CONFIG_ELEMENT *
0x1800557ce  mov     rcx, rdi; this
0x1800557d1  call    ?IsEqual@CONFIG_ELEMENT@@QEAAJPEAV1@PEAHH@Z; CONFIG_ELEMENT::IsEqual(CONFIG_ELEMENT *,int *,int)
0x1800557d6  mov     [rbp+57h+var_D0], eax
0x1800557d9  test    eax, eax
0x1800557db  js      loc_180055A1F
0x1800557e1  mov     rcx, rdi; this
0x1800557e4  call    ?DereferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::DereferenceConfigElement(void)
0x1800557e9  xor     edi, edi
0x1800557eb  mov     rcx, r15; this
0x1800557ee  mov     [rbp+57h+var_B0], rdi
0x1800557f2  call    ?DereferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::DereferenceConfigElement(void)
0x1800557f7  xor     r15d, r15d
0x1800557fa  mov     [rbp+57h+var_C8], r15
0x1800557fe  cmp     dword ptr [rbp+57h+var_C0], ebx
0x180055801  jz      short loc_18005580B
0x180055803  inc     r14d
0x180055806  jmp     loc_180055775
0x18005580b  mov     rax, [rbp+57h+arg_18]
0x18005580f  mov     dword ptr [rax], 1
0x180055815  jmp     loc_180055A28
0x18005581a  mov     rdi, [rbp+57h+var_B0]
0x18005581e  jmp     loc_180055A1F
0x180055823  lea     rdx, [rbp+57h+var_90]; struct CONFIG_COLLECTION **
0x180055827  call    ?GetDefaultInternalCollection@CONFIG_ELEMENT@@QEAAJPEAPEAVCONFIG_COLLECTION@@@Z; CONFIG_ELEMENT::GetDefaultInternalCollection(CONFIG_COLLECTION * *)
0x18005582c  mov     [rbp+57h+var_D0], eax
0x18005582f  test    eax, eax
0x180055831  js      loc_180055A1F
0x180055837  lea     rdx, [rbp+57h+var_A8]; struct CONFIG_COLLECTION **
0x18005583b  mov     rcx, r12; this
0x18005583e  call    ?GetDefaultInternalCollection@CONFIG_ELEMENT@@QEAAJPEAPEAVCONFIG_COLLECTION@@@Z; CONFIG_ELEMENT::GetDefaultInternalCollection(CONFIG_COLLECTION * *)
0x180055843  mov     [rbp+57h+var_D0], eax
0x180055846  test    eax, eax
0x180055848  js      loc_180055A1B
0x18005584e  mov     ecx, 50h ; 'P'; Size
0x180055853  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180055858  mov     rsi, rax
0x18005585b  test    rax, rax
0x18005585e  jz      loc_180055A12
0x180055864  movsd   xmm0, cs:__real@4010000000000000
0x18005586c  lea     rcx, [rax+8]
0x180055870  mov     [rsp+48h], bl
0x180055874  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VSIMPLE_SITE_ID_TABLE@@VCONFIG_ELEMENT@@KVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<SIMPLE_SITE_ID_TABLE,CONFIG_ELEMENT,ulong,CLKRHashTable>::_AddRefRecord(void const *,int)
0x18005587b  mov     dword ptr [rsp+120h+var_E0], ebx
0x18005587f  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VSIMPLE_SITE_ID_TABLE@@VCONFIG_ELEMENT@@KVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<SIMPLE_SITE_ID_TABLE,CONFIG_ELEMENT,ulong,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x180055886  mov     [rsp+120h+var_E8], 1
0x18005588e  lea     r8, ?_ExtractKey@?$CTypedHashTable@VSIMPLE_SITE_ID_TABLE@@VCONFIG_ELEMENT@@KVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<SIMPLE_SITE_ID_TABLE,CONFIG_ELEMENT,ulong,CLKRHashTable>::_ExtractKey(void const *)
0x180055895  movsd   qword ptr [rsp+120h+var_F0], xmm0
0x18005589b  lea     rdx, aSimpleSiteIdTa; "SIMPLE_SITE_ID_TABLE"
0x1800558a2  mov     [rsp+120h+var_F8], rax
0x1800558a7  lea     rax, ?_EqualKeys@?$CTypedHashTable@VSIMPLE_SITE_ID_TABLE@@VCONFIG_ELEMENT@@KVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<SIMPLE_SITE_ID_TABLE,CONFIG_ELEMENT,ulong,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x1800558ae  mov     [rsp+120h+var_100], rax
0x1800558b3  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x1800558b9  mov     r13, [rbp+57h+var_A8]
0x1800558bd  lea     rax, ??_7SIMPLE_SITE_ID_TABLE@@6B@; const SIMPLE_SITE_ID_TABLE::`vftable'
0x1800558c4  mov     [rsi], rax
0x1800558c7  xor     r14d, r14d
0x1800558ca  cmp     r14d, [r13+20h]
0x1800558ce  jnb     short loc_180055917
0x1800558d0  mov     rax, [r13+28h]
0x1800558d4  lea     rcx, [r14+r14*2]
0x1800558d8  mov     rbx, [rax+rcx*8]
0x1800558dc  mov     rcx, rbx; this
0x1800558df  call    ?ReferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::ReferenceConfigElement(void)
0x1800558e4  xor     r8d, r8d
0x1800558e7  lea     rcx, [rsi+8]
0x1800558eb  mov     rdx, rbx
0x1800558ee  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x1800558f4  test    eax, eax
0x1800558f6  jnz     short loc_180055905
0x1800558f8  mov     rcx, rbx; this
0x1800558fb  call    ?DereferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::DereferenceConfigElement(void)
0x180055900  inc     r14d
0x180055903  jmp     short loc_1800558CA
0x180055905  jle     short loc_18005590F
0x180055907  movzx   eax, ax
0x18005590a  or      eax, 80070000h
0x18005590f  mov     [rbp+57h+var_D0], eax
0x180055912  jmp     loc_180055A1F
0x180055917  xor     r14d, r14d
0x18005591a  xor     ebx, ebx
0x18005591c  mov     rdx, [rbp+57h+var_90]
0x180055920  cmp     r14d, [rdx+20h]
0x180055924  jnb     loc_1800559C3
0x18005592a  mov     rax, [rdx+28h]
0x18005592e  lea     rcx, [r14+r14*2]
0x180055932  lea     rdx, [rbp+57h+var_B8]; unsigned int *
0x180055936  mov     rax, [rax+rcx*8]
0x18005593a  mov     rcx, rax; this
0x18005593d  mov     [rbp+57h+var_C8], rax
0x180055941  call    ?GetSiteIdInternal@CONFIG_ELEMENT@@QEBAJPEAK@Z; CONFIG_ELEMENT::GetSiteIdInternal(ulong *)
0x180055946  mov     [rbp+57h+var_D0], eax
0x180055949  test    eax, eax
0x18005594b  js      loc_180055A1F
0x180055951  mov     edx, [rbp+57h+var_B8]
0x180055954  lea     r8, [rbp+57h+var_A8]
0x180055958  lea     rcx, [rsi+8]
0x18005595c  mov     [rbp+57h+var_A8], 0
0x180055964  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18005596a  mov     rbx, [rbp+57h+var_A8]
0x18005596e  test    rbx, rbx
0x180055971  jnz     short loc_18005598D
0x180055973  mov     rdx, [rbp+57h+var_C8]; struct CONFIG_ELEMENT *
0x180055977  mov     rcx, [rbp+57h+arg_0]; this
0x18005597b  call    ?AppendChangedSite@GRANULAR_CHANGE_LIST@@AEAAJPEAVCONFIG_ELEMENT@@@Z; GRANULAR_CHANGE_LIST::AppendChangedSite(CONFIG_ELEMENT *)
0x180055980  mov     [rbp+57h+var_D0], eax
0x180055983  test    eax, eax
0x180055985  js      loc_180055A1F
0x18005598b  jmp     short loc_1800559BB
0x18005598d  mov     rdx, rbx
0x180055990  lea     rcx, [rsi+8]
0x180055994  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x18005599a  mov     rdx, [rbp+57h+var_C8]; struct CONFIG_ELEMENT *
0x18005599e  mov     r8, rbx; struct CONFIG_ELEMENT *
0x1800559a1  mov     rcx, [rbp+57h+arg_0]; this
0x1800559a5  call    ?GetSiteElementChanges@GRANULAR_CHANGE_LIST@@AEAAJPEAVCONFIG_ELEMENT@@0@Z; GRANULAR_CHANGE_LIST::GetSiteElementChanges(CONFIG_ELEMENT *,CONFIG_ELEMENT *)
0x1800559aa  mov     [rbp+57h+var_D0], eax
0x1800559ad  test    eax, eax
0x1800559af  js      short loc_180055A1F
0x1800559b1  mov     rcx, rbx; this
0x1800559b4  call    ?DereferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::DereferenceConfigElement(void)
0x1800559b9  xor     ebx, ebx
0x1800559bb  inc     r14d
0x1800559be  jmp     loc_18005591C
0x1800559c3  mov     r14, [rbp+57h+arg_0]
0x1800559c7  cmp     dword ptr [r14+4], 2
0x1800559cc  jl      short loc_180055A1F
0x1800559ce  lea     rax, [rbp+57h+var_D0]
0x1800559d2  mov     [rbp+57h+var_A8], r14
0x1800559d6  mov     [rbp+57h+var_A0], rax
0x1800559da  lea     r8, [rbp+57h+var_88]
0x1800559de  lea     rax, ?AddToGranularChangeListIfSiteChanged@SIMPLE_SITE_ID_TABLE@@SA?AW4LK_ACTION@@PEAVCONFIG_ELEMENT@@PEAX@Z; SIMPLE_SITE_ID_TABLE::AddToGranularChangeListIfSiteChanged(CONFIG_ELEMENT *,void *)
0x1800559e5  mov     [rbp+57h+var_88], 0
0x1800559ed  mov     [rbp+57h+var_80], rax
0x1800559f1  lea     rdx, ?_Action@?$CTypedHashTable@VSIMPLE_SITE_ID_TABLE@@VCONFIG_ELEMENT@@KVCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<SIMPLE_SITE_ID_TABLE,CONFIG_ELEMENT,ulong,CLKRHashTable>::_Action(void const *,void *)
0x1800559f8  lea     rax, [rbp+57h+var_A8]
0x1800559fc  mov     r9d, 1
0x180055a02  lea     rcx, [rsi+8]
0x180055a06  mov     [rbp+57h+var_78], rax
0x180055a0a  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x180055a10  jmp     short loc_180055A1F
0x180055a12  mov     [rbp+57h+var_D0], 80070008h
0x180055a19  xor     esi, esi
0x180055a1b  mov     r13, [rbp+57h+var_A8]
0x180055a1f  mov     rax, [rbp+57h+arg_18]
0x180055a23  cmp     dword ptr [rax], 0
0x180055a26  jz      short loc_180055A44
0x180055a28  mov     rcx, [rbp+57h+arg_0]; this
0x180055a2c  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180055a33  mov     r9d, 1; int
0x180055a39  xor     r8d, r8d; int
0x180055a3c  call    ?AppendChangedPath@GRANULAR_CHANGE_LIST@@AEAAJPEBGHH@Z; GRANULAR_CHANGE_LIST::AppendChangedPath(ushort const *,int,int)
0x180055a41  mov     [rbp+57h+var_D0], eax
0x180055a44  test    rsi, rsi
0x180055a47  jz      short loc_180055A5C
0x180055a49  mov     rax, [rsi]
0x180055a4c  mov     edx, 1
0x180055a51  mov     rcx, rsi
0x180055a54  mov     rax, [rax]
0x180055a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a5c  mov     rdx, [rbp+57h+var_90]
0x180055a60  test    rdx, rdx
0x180055a63  jz      short loc_180055A6D
0x180055a65  mov     rcx, rdx; this
0x180055a68  call    ?DereferenceConfigCollection@CONFIG_COLLECTION@@QEAAXXZ; CONFIG_COLLECTION::DereferenceConfigCollection(void)
0x180055a6d  test    r13, r13
0x180055a70  jz      short loc_180055A7A
0x180055a72  mov     rcx, r13; this
0x180055a75  call    ?DereferenceConfigCollection@CONFIG_COLLECTION@@QEAAXXZ; CONFIG_COLLECTION::DereferenceConfigCollection(void)
0x180055a7a  test    rdi, rdi
0x180055a7d  jz      short loc_180055A87
0x180055a7f  mov     rcx, rdi; this
0x180055a82  call    ?DereferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::DereferenceConfigElement(void)
0x180055a87  test    r15, r15
0x180055a8a  jz      short loc_180055A94
0x180055a8c  mov     rcx, r15; this
0x180055a8f  call    ?DereferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::DereferenceConfigElement(void)
0x180055a94  mov     rax, [rbp+57h+var_98]
0x180055a98  test    rax, rax
0x180055a9b  jz      short loc_180055AA5
0x180055a9d  mov     rcx, rax; this
0x180055aa0  call    ?DereferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::DereferenceConfigElement(void)
0x180055aa5  test    r12, r12
0x180055aa8  jz      short loc_180055AB2
0x180055aaa  mov     rcx, r12; this
0x180055aad  call    ?DereferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::DereferenceConfigElement(void)
0x180055ab2  test    rbx, rbx
0x180055ab5  jz      short loc_180055ABF
0x180055ab7  mov     rcx, rbx; this
0x180055aba  call    ?DereferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::DereferenceConfigElement(void)
0x180055abf  mov     ebx, [rbp+57h+var_D0]
0x180055ac2  lea     rcx, [rbp+57h+var_70]; this
0x180055ac6  call    ??1PARSE_ERROR_INFO@@UEAA@XZ; PARSE_ERROR_INFO::~PARSE_ERROR_INFO(void)
0x180055acb  mov     eax, ebx
0x180055acd  mov     rbx, [rsp+120h+arg_8]
0x180055ad5  add     rsp, 0F0h
0x180055adc  pop     r15
0x180055ade  pop     r14
0x180055ae0  pop     r13
0x180055ae2  pop     r12
0x180055ae4  pop     rdi
0x180055ae5  pop     rsi
0x180055ae6  pop     rbp
0x180055ae7  retn
```
