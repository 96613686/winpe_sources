# PATHMAP_TABLE::Create(ushort const *)

- ea: `0x180019564`
- end: `0x180019996`
- name: `?Create@PATHMAP_TABLE@@QEAAJPEBG@Z`
- size: `1074`
- prototype: `__int64 __fastcall(PATHMAP_TABLE *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18005329c`

## callees

- `0x180018d88`
- `0x180019564`
- `0x18001c250`
- `0x18004414c`
- `0x180044348`
- `0x180044414`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18001993b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180019945`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180019959`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180019963`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001993b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180019945`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180019959`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180019963`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001964f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001972a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180019807`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800198ce`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001964f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001972a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180019807`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800198ce`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800195bf`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800195e5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800195bf`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800195e5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800195f3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800196d4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800195f3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800196d4`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800196a0`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18001977d`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180019857`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18001991e`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800196a0`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18001977d`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180019857`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18001991e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001960f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800196f0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800197cd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180019894`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001960f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800196f0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800197cd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180019894`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800197b1`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180019878`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800197b1`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180019878`

## string_xrefs

- `0x180019603`: `\CONFIG\machine.config`
- `0x1800196e4`: `\CONFIG\web.config`
- `0x1800197c1`: `\config\redirection.config`
- `0x180019888`: `\config\applicationHost.config`

## pseudocode

```c
__int64 __fastcall PATHMAP_TABLE::Create(PATHMAP_TABLE *this, const unsigned __int16 *a2)
{
  signed int IISDirectory; // ebx
  PATHMAP_ENTRY *v5; // rax
  SCHEMA_FILE_LIST *v6; // rdi
  unsigned __int16 *Str; // rax
  char *v8; // rsi
  signed int inserted; // eax
  bool v10; // cc
  PATHMAP_ENTRY *v11; // rax
  unsigned __int16 *v12; // rax
  PATHMAP_ENTRY *v13; // rax
  unsigned __int16 *v14; // rax
  PATHMAP_ENTRY *v15; // rax
  unsigned __int16 *v16; // rax
  _BYTE v18[56]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[56]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v20[264]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v21[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  memset_0(v20, 0, 0x208u);
  STRU::STRU((STRU *)v19, v20, 0x104u);
  memset_0(v21, 0, 0x208u);
  STRU::STRU((STRU *)v18, v21, 0x104u);
  IISDirectory = STRU::Copy((STRU *)v18, a2);
  if ( IISDirectory < 0 )
    goto LABEL_31;
  IISDirectory = STRU::Append((STRU *)v18, L"\\CONFIG\\machine.config");
  if ( IISDirectory < 0 )
    goto LABEL_31;
  v5 = (PATHMAP_ENTRY *)operator new(0x38u);
  if ( !v5 )
    goto LABEL_30;
  v6 = PATHMAP_ENTRY::PATHMAP_ENTRY(v5);
  if ( !v6 )
    goto LABEL_30;
  Str = STRU::QueryStr((STRU *)v18);
  IISDirectory = PATHMAP_ENTRY::Create(v6, L"MACHINE", Str, 0, 0, 1, 1, 0, 1);
  if ( IISDirectory < 0 )
    goto LABEL_9;
  v8 = (char *)this + 8;
  inserted = CLKRHashTable::InsertRecord(v8, v6, 0);
  IISDirectory = inserted;
  v10 = inserted <= 0;
  if ( inserted )
    goto LABEL_7;
  SCHEMA_FILE_LIST::DereferenceSchemaFileList(v6);
  IISDirectory = STRU::Copy((STRU *)v18, a2);
  if ( IISDirectory < 0 )
    goto LABEL_31;
  IISDirectory = STRU::Append((STRU *)v18, L"\\CONFIG\\web.config");
  if ( IISDirectory < 0 )
    goto LABEL_31;
  v11 = (PATHMAP_ENTRY *)operator new(0x38u);
  if ( !v11 )
    goto LABEL_30;
  v6 = PATHMAP_ENTRY::PATHMAP_ENTRY(v11);
  if ( !v6 )
    goto LABEL_30;
  v12 = STRU::QueryStr((STRU *)v18);
  IISDirectory = PATHMAP_ENTRY::Create(v6, L"MACHINE/WEBROOT", v12, 0, 0, 2, 1, 0, 1);
  if ( IISDirectory < 0 )
    goto LABEL_9;
  inserted = CLKRHashTable::InsertRecord(v8, v6, 0);
  IISDirectory = inserted;
  v10 = inserted <= 0;
  if ( inserted )
  {
LABEL_7:
    if ( !v10 )
      IISDirectory = (unsigned __int16)inserted | 0x80070000;
    goto LABEL_9;
  }
  SCHEMA_FILE_LIST::DereferenceSchemaFileList(v6);
  IISDirectory = PATHMAP_TABLE::FindIISDirectory((struct STRU *)v19);
  if ( IISDirectory < 0 )
    goto LABEL_31;
  IISDirectory = STRU::Copy((STRU *)v18, (const struct STRU *)v19);
  if ( IISDirectory < 0 )
    goto LABEL_31;
  IISDirectory = STRU::Append((STRU *)v18, L"\\config\\redirection.config");
  if ( IISDirectory < 0 )
    goto LABEL_31;
  v13 = (PATHMAP_ENTRY *)operator new(0x38u);
  if ( !v13 || (v6 = PATHMAP_ENTRY::PATHMAP_ENTRY(v13)) == 0 )
  {
LABEL_30:
    IISDirectory = -2147024888;
    goto LABEL_31;
  }
  v14 = STRU::QueryStr((STRU *)v18);
  IISDirectory = PATHMAP_ENTRY::Create(v6, L"MACHINE/REDIRECTION", v14, 0, 0, 2, 1, 0, 0);
  if ( IISDirectory < 0 )
    goto LABEL_9;
  inserted = CLKRHashTable::InsertRecord(v8, v6, 0);
  IISDirectory = inserted;
  v10 = inserted <= 0;
  if ( inserted )
    goto LABEL_7;
  SCHEMA_FILE_LIST::DereferenceSchemaFileList(v6);
  IISDirectory = STRU::Copy((STRU *)v18, (const struct STRU *)v19);
  if ( IISDirectory < 0 )
    goto LABEL_31;
  IISDirectory = STRU::Append((STRU *)v18, L"\\config\\applicationHost.config");
  if ( IISDirectory < 0 )
    goto LABEL_31;
  v15 = (PATHMAP_ENTRY *)operator new(0x38u);
  if ( !v15 )
    goto LABEL_30;
  v6 = PATHMAP_ENTRY::PATHMAP_ENTRY(v15);
  if ( !v6 )
    goto LABEL_30;
  v16 = STRU::QueryStr((STRU *)v18);
  IISDirectory = PATHMAP_ENTRY::Create(v6, L"MACHINE/WEBROOT/APPHOST", v16, 0, 0, 3, 1, 1, 0);
  if ( IISDirectory >= 0 )
  {
    inserted = CLKRHashTable::InsertRecord(v8, v6, 0);
    IISDirectory = inserted;
    v10 = inserted <= 0;
    if ( !inserted )
    {
      SCHEMA_FILE_LIST::DereferenceSchemaFileList(v6);
      STRU::~STRU((STRU *)v18);
      STRU::~STRU((STRU *)v19);
      return 0;
    }
    goto LABEL_7;
  }
LABEL_9:
  SCHEMA_FILE_LIST::DereferenceSchemaFileList(v6);
LABEL_31:
  STRU::~STRU((STRU *)v18);
  STRU::~STRU((STRU *)v19);
  return (unsigned int)IISDirectory;
}

```

## disassembly

```asm
0x180019564  mov     [rsp-8+arg_10], rbx
0x180019569  mov     [rsp-8+arg_18], rsi
0x18001956e  push    rbp
0x18001956f  push    rdi
0x180019570  push    r12
0x180019572  push    r13
0x180019574  push    r14
0x180019576  lea     rbp, [rsp-3F0h]
0x18001957e  sub     rsp, 4F0h
0x180019585  mov     rax, cs:__security_cookie
0x18001958c  xor     rax, rsp
0x18001958f  mov     [rbp+410h+var_30], rax
0x180019596  mov     r14, rdx
0x180019599  mov     rsi, rcx
0x18001959c  mov     edi, 208h
0x1800195a1  lea     rcx, [rbp+410h+var_450]; void *
0x1800195a5  mov     r8d, edi; Size
0x1800195a8  xor     edx, edx; Val
0x1800195aa  call    memset_0
0x1800195af  mov     ebx, 104h
0x1800195b4  lea     rdx, [rbp+410h+var_450]
0x1800195b8  mov     r8d, ebx
0x1800195bb  lea     rcx, [rbp+410h+var_488]
0x1800195bf  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800195c5  mov     r8d, edi; Size
0x1800195c8  lea     rcx, [rbp+410h+var_240]; void *
0x1800195cf  xor     edx, edx; Val
0x1800195d1  call    memset_0
0x1800195d6  mov     r8d, ebx
0x1800195d9  lea     rdx, [rbp+410h+var_240]
0x1800195e0  lea     rcx, [rsp+510h+var_4C0]
0x1800195e5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800195eb  mov     rdx, r14
0x1800195ee  lea     rcx, [rsp+510h+var_4C0]
0x1800195f3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800195f9  mov     ebx, eax
0x1800195fb  test    eax, eax
0x1800195fd  js      loc_180019954
0x180019603  lea     rdx, aConfigMachineC; "\\CONFIG\\machine.config"
0x18001960a  lea     rcx, [rsp+510h+var_4C0]
0x18001960f  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180019615  mov     ebx, eax
0x180019617  test    eax, eax
0x180019619  js      loc_180019954
0x18001961f  mov     r13d, 38h ; '8'
0x180019625  mov     ecx, r13d; Size
0x180019628  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001962d  test    rax, rax
0x180019630  jz      loc_18001994F
0x180019636  mov     rcx, rax; this
0x180019639  call    ??0PATHMAP_ENTRY@@QEAA@XZ; PATHMAP_ENTRY::PATHMAP_ENTRY(void)
0x18001963e  mov     rdi, rax
0x180019641  test    rax, rax
0x180019644  jz      loc_18001994F
0x18001964a  lea     rcx, [rsp+510h+var_4C0]
0x18001964f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180019655  lea     r12d, [r13-37h]
0x180019659  xor     r9d, r9d
0x18001965c  mov     [rsp+510h+var_4D0], r12d
0x180019661  lea     rdx, aMachine; "MACHINE"
0x180019668  mov     [rsp+510h+var_4D8], 0
0x180019670  mov     r8, rax
0x180019673  mov     [rsp+510h+var_4E0], r12d
0x180019678  mov     rcx, rdi
0x18001967b  mov     [rsp+510h+var_4E8], r12d
0x180019680  mov     [rsp+510h+var_4F0], 0
0x180019688  call    ?Create@PATHMAP_ENTRY@@QEAAJPEBG0HHW4_ALLOW_DEFINITION_LEVEL@@HHH@Z; PATHMAP_ENTRY::Create(ushort const *,ushort const *,int,int,_ALLOW_DEFINITION_LEVEL,int,int,int)
0x18001968d  mov     ebx, eax
0x18001968f  test    eax, eax
0x180019691  js      short loc_1800196B7
0x180019693  add     rsi, 8
0x180019697  xor     r8d, r8d
0x18001969a  mov     rcx, rsi
0x18001969d  mov     rdx, rdi
0x1800196a0  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x1800196a6  mov     ebx, eax
0x1800196a8  test    eax, eax
0x1800196aa  jz      short loc_1800196C4
0x1800196ac  jle     short loc_1800196B7
0x1800196ae  movzx   ebx, ax
0x1800196b1  or      ebx, 80070000h
0x1800196b7  mov     rcx, rdi; this
0x1800196ba  call    ?DereferenceSchemaFileList@SCHEMA_FILE_LIST@@QEAAXXZ; SCHEMA_FILE_LIST::DereferenceSchemaFileList(void)
0x1800196bf  jmp     loc_180019954
0x1800196c4  mov     rcx, rdi; this
0x1800196c7  call    ?DereferenceSchemaFileList@SCHEMA_FILE_LIST@@QEAAXXZ; SCHEMA_FILE_LIST::DereferenceSchemaFileList(void)
0x1800196cc  mov     rdx, r14
0x1800196cf  lea     rcx, [rsp+510h+var_4C0]
0x1800196d4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800196da  mov     ebx, eax
0x1800196dc  test    eax, eax
0x1800196de  js      loc_180019954
0x1800196e4  lea     rdx, aConfigWebConfi_0; "\\CONFIG\\web.config"
0x1800196eb  lea     rcx, [rsp+510h+var_4C0]
0x1800196f0  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800196f6  mov     ebx, eax
0x1800196f8  test    eax, eax
0x1800196fa  js      loc_180019954
0x180019700  mov     rcx, r13; Size
0x180019703  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019708  test    rax, rax
0x18001970b  jz      loc_18001994F
0x180019711  mov     rcx, rax; this
0x180019714  call    ??0PATHMAP_ENTRY@@QEAA@XZ; PATHMAP_ENTRY::PATHMAP_ENTRY(void)
0x180019719  mov     rdi, rax
0x18001971c  test    rax, rax
0x18001971f  jz      loc_18001994F
0x180019725  lea     rcx, [rsp+510h+var_4C0]
0x18001972a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180019730  mov     [rsp+510h+var_4D0], r12d
0x180019735  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT"
0x18001973c  mov     [rsp+510h+var_4D8], 0
0x180019744  mov     r14d, 2
0x18001974a  mov     [rsp+510h+var_4E0], r12d
0x18001974f  mov     r8, rax
0x180019752  mov     [rsp+510h+var_4E8], r14d
0x180019757  xor     r9d, r9d
0x18001975a  mov     rcx, rdi
0x18001975d  mov     [rsp+510h+var_4F0], 0
0x180019765  call    ?Create@PATHMAP_ENTRY@@QEAAJPEBG0HHW4_ALLOW_DEFINITION_LEVEL@@HHH@Z; PATHMAP_ENTRY::Create(ushort const *,ushort const *,int,int,_ALLOW_DEFINITION_LEVEL,int,int,int)
0x18001976a  mov     ebx, eax
0x18001976c  test    eax, eax
0x18001976e  js      loc_1800196B7
0x180019774  xor     r8d, r8d
0x180019777  mov     rdx, rdi
0x18001977a  mov     rcx, rsi
0x18001977d  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180019783  mov     ebx, eax
0x180019785  test    eax, eax
0x180019787  jnz     loc_1800196AC
0x18001978d  mov     rcx, rdi; this
0x180019790  call    ?DereferenceSchemaFileList@SCHEMA_FILE_LIST@@QEAAXXZ; SCHEMA_FILE_LIST::DereferenceSchemaFileList(void)
0x180019795  lea     rcx, [rbp+410h+var_488]; struct STRU *
0x180019799  call    ?FindIISDirectory@PATHMAP_TABLE@@SAJPEAVSTRU@@@Z; PATHMAP_TABLE::FindIISDirectory(STRU *)
0x18001979e  mov     ebx, eax
0x1800197a0  test    eax, eax
0x1800197a2  js      loc_180019954
0x1800197a8  lea     rdx, [rbp+410h+var_488]
0x1800197ac  lea     rcx, [rsp+510h+var_4C0]
0x1800197b1  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x1800197b7  mov     ebx, eax
0x1800197b9  test    eax, eax
0x1800197bb  js      loc_180019954
0x1800197c1  lea     rdx, aConfigRedirect; "\\config\\redirection.config"
0x1800197c8  lea     rcx, [rsp+510h+var_4C0]
0x1800197cd  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800197d3  mov     ebx, eax
0x1800197d5  test    eax, eax
0x1800197d7  js      loc_180019954
0x1800197dd  mov     rcx, r13; Size
0x1800197e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800197e5  test    rax, rax
0x1800197e8  jz      loc_18001994F
0x1800197ee  mov     rcx, rax; this
0x1800197f1  call    ??0PATHMAP_ENTRY@@QEAA@XZ; PATHMAP_ENTRY::PATHMAP_ENTRY(void)
0x1800197f6  mov     rdi, rax
0x1800197f9  test    rax, rax
0x1800197fc  jz      loc_18001994F
0x180019802  lea     rcx, [rsp+510h+var_4C0]
0x180019807  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001980d  mov     [rsp+510h+var_4D0], 0
0x180019815  lea     rdx, Str; "MACHINE/REDIRECTION"
0x18001981c  mov     [rsp+510h+var_4D8], 0
0x180019824  mov     r8, rax
0x180019827  mov     [rsp+510h+var_4E0], r12d
0x18001982c  xor     r9d, r9d
0x18001982f  mov     [rsp+510h+var_4E8], r14d
0x180019834  mov     rcx, rdi
0x180019837  mov     [rsp+510h+var_4F0], 0
0x18001983f  call    ?Create@PATHMAP_ENTRY@@QEAAJPEBG0HHW4_ALLOW_DEFINITION_LEVEL@@HHH@Z; PATHMAP_ENTRY::Create(ushort const *,ushort const *,int,int,_ALLOW_DEFINITION_LEVEL,int,int,int)
0x180019844  mov     ebx, eax
0x180019846  test    eax, eax
0x180019848  js      loc_1800196B7
0x18001984e  xor     r8d, r8d
0x180019851  mov     rdx, rdi
0x180019854  mov     rcx, rsi
0x180019857  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18001985d  mov     ebx, eax
0x18001985f  test    eax, eax
0x180019861  jnz     loc_1800196AC
0x180019867  mov     rcx, rdi; this
0x18001986a  call    ?DereferenceSchemaFileList@SCHEMA_FILE_LIST@@QEAAXXZ; SCHEMA_FILE_LIST::DereferenceSchemaFileList(void)
0x18001986f  lea     rdx, [rbp+410h+var_488]
0x180019873  lea     rcx, [rsp+510h+var_4C0]
0x180019878  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18001987e  mov     ebx, eax
0x180019880  test    eax, eax
0x180019882  js      loc_180019954
0x180019888  lea     rdx, aConfigApplicat; "\\config\\applicationHost.config"
0x18001988f  lea     rcx, [rsp+510h+var_4C0]
0x180019894  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001989a  mov     ebx, eax
0x18001989c  test    eax, eax
0x18001989e  js      loc_180019954
0x1800198a4  mov     rcx, r13; Size
0x1800198a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800198ac  test    rax, rax
0x1800198af  jz      loc_18001994F
0x1800198b5  mov     rcx, rax; this
0x1800198b8  call    ??0PATHMAP_ENTRY@@QEAA@XZ; PATHMAP_ENTRY::PATHMAP_ENTRY(void)
0x1800198bd  mov     rdi, rax
0x1800198c0  test    rax, rax
0x1800198c3  jz      loc_18001994F
0x1800198c9  lea     rcx, [rsp+510h+var_4C0]
0x1800198ce  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800198d4  mov     [rsp+510h+var_4D0], 0
0x1800198dc  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800198e3  mov     [rsp+510h+var_4D8], r12d
0x1800198e8  mov     r8, rax
0x1800198eb  mov     [rsp+510h+var_4E0], r12d
0x1800198f0  xor     r9d, r9d
0x1800198f3  mov     [rsp+510h+var_4E8], 3
0x1800198fb  mov     rcx, rdi
0x1800198fe  mov     [rsp+510h+var_4F0], 0
0x180019906  call    ?Create@PATHMAP_ENTRY@@QEAAJPEBG0HHW4_ALLOW_DEFINITION_LEVEL@@HHH@Z; PATHMAP_ENTRY::Create(ushort const *,ushort const *,int,int,_ALLOW_DEFINITION_LEVEL,int,int,int)
0x18001990b  mov     ebx, eax
0x18001990d  test    eax, eax
0x18001990f  js      loc_1800196B7
0x180019915  xor     r8d, r8d
0x180019918  mov     rdx, rdi
0x18001991b  mov     rcx, rsi
0x18001991e  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180019924  mov     ebx, eax
0x180019926  test    eax, eax
0x180019928  jnz     loc_1800196AC
0x18001992e  mov     rcx, rdi; this
0x180019931  call    ?DereferenceSchemaFileList@SCHEMA_FILE_LIST@@QEAAXXZ; SCHEMA_FILE_LIST::DereferenceSchemaFileList(void)
0x180019936  lea     rcx, [rsp+510h+var_4C0]
0x18001993b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180019941  lea     rcx, [rbp+410h+var_488]
0x180019945  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001994b  xor     eax, eax
0x18001994d  jmp     short loc_18001996B
0x18001994f  mov     ebx, 80070008h
0x180019954  lea     rcx, [rsp+510h+var_4C0]
0x180019959  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001995f  lea     rcx, [rbp+410h+var_488]
0x180019963  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180019969  mov     eax, ebx
0x18001996b  mov     rcx, [rbp+410h+var_30]
0x180019972  xor     rcx, rsp; StackCookie
0x180019975  call    __security_check_cookie
0x18001997a  lea     r11, [rsp+510h+var_20]
0x180019982  mov     rbx, [r11+40h]
0x180019986  mov     rsi, [r11+48h]
0x18001998a  mov     rsp, r11
0x18001998d  pop     r14
0x18001998f  pop     r13
0x180019991  pop     r12
0x180019993  pop     rdi
0x180019994  pop     rbp
0x180019995  retn
```
