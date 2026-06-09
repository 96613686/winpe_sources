# MAPPING_CONTEXT::Create(CONFIG_ELEMENT *)

- ea: `0x180040f24`
- end: `0x1800410fe`
- name: `?Create@MAPPING_CONTEXT@@QEAAJPEAVCONFIG_ELEMENT@@@Z`
- size: `474`
- prototype: `int(MAPPING_CONTEXT *__hidden this, struct CONFIG_ELEMENT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180040358`

## callees

- `0x180018d88`
- `0x18001c250`
- `0x1800222a8`
- `0x18002ff78`
- `0x1800307c4`
- `0x180031d00`
- `0x180040f24`
- `0x18004127c`
- `0x18005b010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004102f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004102f`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180041049`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18004105f`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180041049`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18004105f`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180041087`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180041087`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18004100d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18004100d`

## pseudocode

```c
__int64 __fastcall MAPPING_CONTEXT::Create(MAPPING_CONTEXT *this, struct CONFIG_ELEMENT *a2)
{
  signed int SiteIdInternal; // ebx
  _QWORD *v4; // rdi
  int DefaultInternalCollection; // eax
  struct CONFIG_COLLECTION *v6; // rbp
  __int64 i; // rsi
  CONFIG_ELEMENT *v8; // r15
  unsigned int v9; // eax
  const unsigned __int16 *v10; // rdx
  __int64 v11; // rcx
  const unsigned __int16 *Str; // rax
  __int64 v13; // rcx
  unsigned int v15; // [rsp+68h] [rbp+10h] BYREF
  struct CONFIG_COLLECTION *v16; // [rsp+70h] [rbp+18h] BYREF
  const unsigned __int16 *v17; // [rsp+78h] [rbp+20h] BYREF

  v16 = 0;
  v17 = 0;
  v15 = 0;
  if ( a2 )
  {
    v4 = 0;
    DefaultInternalCollection = CONFIG_ELEMENT::GetDefaultInternalCollection(a2, &v16);
    v6 = v16;
    SiteIdInternal = DefaultInternalCollection;
    if ( DefaultInternalCollection >= 0 )
    {
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= *((_DWORD *)v6 + 8) )
        {
          SiteIdInternal = 0;
          goto LABEL_21;
        }
        v8 = *(CONFIG_ELEMENT **)(*((_QWORD *)v6 + 5) + 24 * i);
        SiteIdInternal = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*((_QWORD *)v8 + 2) + 64LL))(
                           (_QWORD *)v8 + 2,
                           L"name",
                           &v17,
                           0,
                           0);
        if ( SiteIdInternal < 0 )
          goto LABEL_21;
        SiteIdInternal = CONFIG_ELEMENT::GetSiteIdInternal(v8, &v15);
        if ( SiteIdInternal < 0 )
          goto LABEL_21;
        v4 = operator new(0x50u);
        if ( !v4 )
        {
          SiteIdInternal = -2147024888;
LABEL_21:
          v4 = 0;
          goto LABEL_22;
        }
        v4[1] = 1;
        *v4 = &SITE_ENTRY::`vftable';
        STRU::STRU((STRU *)(v4 + 2));
        v9 = v15;
        v4[9] = 0;
        v10 = v17;
        *((_DWORD *)v4 + 3) = v9;
        v4[9] = v8;
        SiteIdInternal = STRU::Copy((STRU *)(v4 + 2), v10);
        if ( SiteIdInternal < 0 )
          goto LABEL_22;
        SiteIdInternal = CLKRHashTable::InsertRecord((char *)this + 8, v4, 0);
        if ( SiteIdInternal )
          break;
        SiteIdInternal = CLKRHashTable::InsertRecord((char *)this + 80, v4, 0);
        if ( SiteIdInternal )
        {
          if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 4) != 0 )
          {
            Str = STRU::QueryStr((STRU *)(v4 + 2));
            McTemplateU0z_EtwEventWriteTransfer(v13, NATIVERD_EVENT_DUPLICATE_SITE_NAME_DETECTED, Str);
          }
          goto LABEL_17;
        }
        SCHEMA_FILE_LIST::DereferenceSchemaFileList((SCHEMA_FILE_LIST *)v4);
      }
      if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 4) != 0 )
        McTemplateU0q_EtwEventWriteTransfer(v11, NATIVERD_EVENT_DUPLICATE_SITE_ID_DETECTED, *((unsigned int *)v4 + 3));
LABEL_17:
      if ( SiteIdInternal > 0 )
        SiteIdInternal = (unsigned __int16)SiteIdInternal | 0x80070000;
    }
LABEL_22:
    if ( v6 )
      CONFIG_COLLECTION::DereferenceConfigCollection(v6);
    if ( v4 )
      SCHEMA_FILE_LIST::DereferenceSchemaFileList((SCHEMA_FILE_LIST *)v4);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)SiteIdInternal;
}

```

## disassembly

```asm
0x180040f24  mov     [rsp+arg_0], rbx
0x180040f29  push    rbp
0x180040f2a  push    rsi
0x180040f2b  push    rdi
0x180040f2c  push    r14
0x180040f2e  push    r15
0x180040f30  sub     rsp, 30h
0x180040f34  mov     [rsp+58h+arg_10], 0
0x180040f3d  mov     rax, rdx
0x180040f40  mov     [rsp+58h+arg_18], 0
0x180040f49  mov     r14, rcx
0x180040f4c  mov     [rsp+58h+arg_8], 0
0x180040f54  test    rdx, rdx
0x180040f57  jnz     short loc_180040F63
0x180040f59  mov     ebx, 80070057h
0x180040f5e  jmp     loc_1800410EB
0x180040f63  lea     rdx, [rsp+58h+arg_10]; struct CONFIG_COLLECTION **
0x180040f68  mov     rcx, rax; this
0x180040f6b  xor     edi, edi
0x180040f6d  call    ?GetDefaultInternalCollection@CONFIG_ELEMENT@@QEAAJPEAPEAVCONFIG_COLLECTION@@@Z; CONFIG_ELEMENT::GetDefaultInternalCollection(CONFIG_COLLECTION * *)
0x180040f72  mov     rbp, [rsp+58h+arg_10]
0x180040f77  mov     ebx, eax
0x180040f79  test    eax, eax
0x180040f7b  js      loc_1800410D1
0x180040f81  xor     esi, esi
0x180040f83  cmp     esi, [rbp+20h]
0x180040f86  jnb     loc_1800410CD
0x180040f8c  mov     rax, [rbp+28h]
0x180040f90  lea     rcx, [rsi+rsi*2]
0x180040f94  xor     r9d, r9d
0x180040f97  mov     [rsp+58h+var_38], 0
0x180040fa0  lea     r8, [rsp+58h+arg_18]
0x180040fa5  lea     rdx, aName; "name"
0x180040fac  mov     r15, [rax+rcx*8]
0x180040fb0  lea     rcx, [r15+10h]
0x180040fb4  mov     rax, [rcx]
0x180040fb7  mov     rax, [rax+40h]
0x180040fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040fc0  mov     ebx, eax
0x180040fc2  test    eax, eax
0x180040fc4  js      loc_1800410CF
0x180040fca  lea     rdx, [rsp+58h+arg_8]; unsigned int *
0x180040fcf  mov     rcx, r15; this
0x180040fd2  call    ?GetSiteIdInternal@CONFIG_ELEMENT@@QEBAJPEAK@Z; CONFIG_ELEMENT::GetSiteIdInternal(ulong *)
0x180040fd7  mov     ebx, eax
0x180040fd9  test    eax, eax
0x180040fdb  js      loc_1800410CF
0x180040fe1  mov     ecx, 50h ; 'P'; Size
0x180040fe6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040feb  mov     rdi, rax
0x180040fee  test    rax, rax
0x180040ff1  jz      loc_1800410C6
0x180040ff7  lea     rax, ??_7SITE_ENTRY@@6B@; const SITE_ENTRY::`vftable'
0x180040ffe  mov     qword ptr [rdi+8], 1
0x180041006  lea     rcx, [rdi+10h]
0x18004100a  mov     [rdi], rax
0x18004100d  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180041013  mov     eax, [rsp+58h+arg_8]
0x180041017  lea     rcx, [rdi+10h]
0x18004101b  mov     qword ptr [rdi+48h], 0
0x180041023  mov     rdx, [rsp+58h+arg_18]
0x180041028  mov     [rdi+0Ch], eax
0x18004102b  mov     [rdi+48h], r15
0x18004102f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180041035  mov     ebx, eax
0x180041037  test    eax, eax
0x180041039  js      loc_1800410D1
0x18004103f  lea     rcx, [r14+8]
0x180041043  xor     r8d, r8d
0x180041046  mov     rdx, rdi
0x180041049  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18004104f  mov     ebx, eax
0x180041051  test    eax, eax
0x180041053  jnz     short loc_18004109E
0x180041055  lea     rcx, [r14+50h]
0x180041059  xor     r8d, r8d
0x18004105c  mov     rdx, rdi
0x18004105f  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180041065  mov     ebx, eax
0x180041067  test    eax, eax
0x180041069  jnz     short loc_18004107A
0x18004106b  mov     rcx, rdi; this
0x18004106e  call    ?DereferenceSchemaFileList@SCHEMA_FILE_LIST@@QEAAXXZ; SCHEMA_FILE_LIST::DereferenceSchemaFileList(void)
0x180041073  inc     esi
0x180041075  jmp     loc_180040F83
0x18004107a  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 4
0x180041081  jz      short loc_1800410B7
0x180041083  lea     rcx, [rdi+10h]
0x180041087  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18004108d  mov     r8, rax
0x180041090  lea     rdx, NATIVERD_EVENT_DUPLICATE_SITE_NAME_DETECTED
0x180041097  call    McTemplateU0z_EtwEventWriteTransfer
0x18004109c  jmp     short loc_1800410B7
0x18004109e  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 4
0x1800410a5  jz      short loc_1800410B7
0x1800410a7  mov     r8d, [rdi+0Ch]
0x1800410ab  lea     rdx, NATIVERD_EVENT_DUPLICATE_SITE_ID_DETECTED
0x1800410b2  call    McTemplateU0q_EtwEventWriteTransfer
0x1800410b7  test    ebx, ebx
0x1800410b9  jle     short loc_1800410D1
0x1800410bb  movzx   ebx, bx
0x1800410be  or      ebx, 80070000h
0x1800410c4  jmp     short loc_1800410D1
0x1800410c6  mov     ebx, 80070008h
0x1800410cb  jmp     short loc_1800410CF
0x1800410cd  xor     ebx, ebx
0x1800410cf  xor     edi, edi
0x1800410d1  test    rbp, rbp
0x1800410d4  jz      short loc_1800410DE
0x1800410d6  mov     rcx, rbp; this
0x1800410d9  call    ?DereferenceConfigCollection@CONFIG_COLLECTION@@QEAAXXZ; CONFIG_COLLECTION::DereferenceConfigCollection(void)
0x1800410de  test    rdi, rdi
0x1800410e1  jz      short loc_1800410EB
0x1800410e3  mov     rcx, rdi; this
0x1800410e6  call    ?DereferenceSchemaFileList@SCHEMA_FILE_LIST@@QEAAXXZ; SCHEMA_FILE_LIST::DereferenceSchemaFileList(void)
0x1800410eb  mov     eax, ebx
0x1800410ed  mov     rbx, [rsp+58h+arg_0]
0x1800410f2  add     rsp, 30h
0x1800410f6  pop     r15
0x1800410f8  pop     r14
0x1800410fa  pop     rdi
0x1800410fb  pop     rsi
0x1800410fc  pop     rbp
0x1800410fd  retn
```
