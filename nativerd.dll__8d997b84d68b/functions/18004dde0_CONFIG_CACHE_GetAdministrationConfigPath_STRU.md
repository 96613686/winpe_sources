# CONFIG_CACHE::GetAdministrationConfigPath(STRU *)

- ea: `0x18004dde0`
- end: `0x18004dfaf`
- name: `?GetAdministrationConfigPath@CONFIG_CACHE@@QEAAJPEAVSTRU@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(CONFIG_CACHE *__hidden this, struct STRU *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18003b960`

## callees

- `0x180016440`
- `0x18001780c`
- `0x180018d88`
- `0x1800444b0`
- `0x18004dde0`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18004df0e`
- `msvcrt!wcsrchr` at `0x18004df0e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004df84`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004df84`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004df02`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004df27`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004df37`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004df02`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004df27`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004df37`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004de37`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004de37`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18004df46`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18004df46`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18004df5c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18004df5c`

## string_xrefs

- `0x18004df52`: `\administration.config`

## pseudocode

```c
__int64 __fastcall CONFIG_CACHE::GetAdministrationConfigPath(CONFIG_CACHE *this, struct STRU *a2)
{
  signed int ConfigFileMapping; // ebx
  int Key; // eax
  const wchar_t *Str; // rax
  wchar_t *v7; // rbx
  __int64 v8; // rbx
  const unsigned __int16 *v9; // rax
  SCHEMA_FILE_LIST *v11; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v12[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v13; // [rsp+60h] [rbp-A0h]
  __int64 v14; // [rsp+68h] [rbp-98h]
  __int128 v15; // [rsp+70h] [rbp-90h]
  __int128 v16; // [rsp+80h] [rbp-80h]
  _BYTE v17[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v18[264]; // [rsp+D0h] [rbp-30h] BYREF

  v11 = 0;
  memset_0(v18, 0, 0x208u);
  STRU::STRU((STRU *)v17, v18, 0x104u);
  v12[1] = 1;
  v12[0] = &PARSE_ERROR_INFO::`vftable';
  v15 = 0;
  v16 = 0;
  v13 = 0;
  v14 = 0;
  if ( a2 )
  {
    Key = CTypedHashTable<SCHEMA_TABLE,SCHEMA_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
            *((_QWORD *)this + 32) + 8LL,
            L"MACHINE/WEBROOT/APPHOST",
            &v11);
    ConfigFileMapping = Key;
    if ( Key )
    {
      if ( Key > 0 )
        ConfigFileMapping = (unsigned __int16)Key | 0x80070000;
    }
    else
    {
      ConfigFileMapping = PATHMAP_ENTRY::GetConfigFileMapping(
                            v11,
                            this,
                            (struct PARSE_ERROR_INFO *)v12,
                            (struct STRU *)v17,
                            0,
                            0,
                            0,
                            0);
      if ( ConfigFileMapping >= 0 )
      {
        Str = STRU::QueryStr((STRU *)v17);
        v7 = wcsrchr(Str, 0x5Cu);
        if ( v7 )
        {
          v8 = v7 - STRU::QueryStr((STRU *)v17);
          v9 = STRU::QueryStr((STRU *)v17);
          ConfigFileMapping = STRU::Copy(a2, v9, v8);
          if ( ConfigFileMapping >= 0 )
            ConfigFileMapping = STRU::Append(a2, L"\\administration.config");
        }
        else
        {
          ConfigFileMapping = -2147024883;
        }
      }
    }
    if ( v11 )
      SCHEMA_FILE_LIST::DereferenceSchemaFileList(v11);
  }
  else
  {
    ConfigFileMapping = -2147024809;
  }
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((PARSE_ERROR_INFO *)v12);
  STRU::~STRU((STRU *)v17);
  return (unsigned int)ConfigFileMapping;
}

```

## disassembly

```asm
0x18004dde0  mov     [rsp-8+arg_10], rbx
0x18004dde5  push    rbp
0x18004dde6  push    rsi
0x18004dde7  push    r14
0x18004dde9  lea     rbp, [rsp-1F0h]
0x18004ddf1  sub     rsp, 2F0h
0x18004ddf8  mov     rax, cs:__security_cookie
0x18004ddff  xor     rax, rsp
0x18004de02  mov     [rbp+200h+var_20], rax
0x18004de09  mov     r14, rdx
0x18004de0c  mov     [rsp+300h+var_2C0], 0
0x18004de15  mov     rsi, rcx
0x18004de18  xor     edx, edx; Val
0x18004de1a  lea     rcx, [rbp+200h+var_230]; void *
0x18004de1e  mov     r8d, 208h; Size
0x18004de24  call    memset_0
0x18004de29  mov     r8d, 104h
0x18004de2f  lea     rdx, [rbp+200h+var_230]
0x18004de33  lea     rcx, [rbp+200h+var_270]
0x18004de37  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004de3d  mov     [rsp+300h+var_2A8], 1
0x18004de46  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x18004de4d  mov     [rsp+300h+var_2B0], rax
0x18004de52  xorps   xmm0, xmm0
0x18004de55  movdqa  [rsp+300h+var_290], xmm0
0x18004de5b  xorps   xmm1, xmm1
0x18004de5e  movdqa  [rbp+200h+var_280], xmm1
0x18004de63  mov     [rsp+300h+var_2A0], 0
0x18004de6b  mov     [rsp+300h+var_298], 0
0x18004de74  test    r14, r14
0x18004de77  jnz     short loc_18004DE83
0x18004de79  mov     ebx, 80070057h
0x18004de7e  jmp     loc_18004DF76
0x18004de83  mov     rcx, [rsi+100h]
0x18004de8a  lea     r8, [rsp+300h+var_2C0]
0x18004de8f  add     rcx, 8
0x18004de93  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18004de9a  call    ?FindKey@?$CTypedHashTable@VSCHEMA_TABLE@@VSCHEMA_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVSCHEMA_ENTRY@@@Z; CTypedHashTable<SCHEMA_TABLE,SCHEMA_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,SCHEMA_ENTRY * *)
0x18004de9f  mov     ebx, eax
0x18004dea1  test    eax, eax
0x18004dea3  jz      short loc_18004DEB9
0x18004dea5  jle     loc_18004DF64
0x18004deab  movzx   ebx, ax
0x18004deae  or      ebx, 80070000h
0x18004deb4  jmp     loc_18004DF64
0x18004deb9  mov     rcx, [rsp+300h+var_2C0]; this
0x18004debe  lea     r9, [rbp+200h+var_270]; struct STRU *
0x18004dec2  mov     [rsp+300h+var_2C8], 0; int *
0x18004decb  lea     r8, [rsp+300h+var_2B0]; struct PARSE_ERROR_INFO *
0x18004ded0  mov     [rsp+300h+var_2D0], 0; int *
0x18004ded9  mov     rdx, rsi; struct CONFIG_CACHE *
0x18004dedc  mov     [rsp+300h+var_2D8], 0; int *
0x18004dee5  mov     [rsp+300h+DuplicateTokenHandle], 0; DuplicateTokenHandle
0x18004deee  call    ?GetConfigFileMapping@PATHMAP_ENTRY@@QEAAJPEAVCONFIG_CACHE@@PEAVPARSE_ERROR_INFO@@PEAVSTRU@@PEAPEAXPEAH44@Z; PATHMAP_ENTRY::GetConfigFileMapping(CONFIG_CACHE *,PARSE_ERROR_INFO *,STRU *,void * *,int *,int *,int *)
0x18004def3  mov     ebx, eax
0x18004def5  test    eax, eax
0x18004def7  js      short loc_18004DF64
0x18004def9  lea     rcx, [rbp+200h+var_270]
0x18004defd  mov     ebx, 5Ch ; '\'
0x18004df02  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004df08  mov     rcx, rax; Str
0x18004df0b  movzx   edx, bx; Ch
0x18004df0e  call    cs:__imp_wcsrchr
0x18004df14  mov     rbx, rax
0x18004df17  test    rax, rax
0x18004df1a  jnz     short loc_18004DF23
0x18004df1c  mov     ebx, 8007000Dh
0x18004df21  jmp     short loc_18004DF64
0x18004df23  lea     rcx, [rbp+200h+var_270]
0x18004df27  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004df2d  sub     rbx, rax
0x18004df30  lea     rcx, [rbp+200h+var_270]
0x18004df34  sar     rbx, 1
0x18004df37  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004df3d  mov     r8d, ebx
0x18004df40  mov     rcx, r14
0x18004df43  mov     rdx, rax
0x18004df46  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18004df4c  mov     ebx, eax
0x18004df4e  test    eax, eax
0x18004df50  js      short loc_18004DF64
0x18004df52  lea     rdx, aAdministration; "\\administration.config"
0x18004df59  mov     rcx, r14
0x18004df5c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18004df62  mov     ebx, eax
0x18004df64  cmp     [rsp+300h+var_2C0], 0
0x18004df6a  jz      short loc_18004DF76
0x18004df6c  mov     rcx, [rsp+300h+var_2C0]; this
0x18004df71  call    ?DereferenceSchemaFileList@SCHEMA_FILE_LIST@@QEAAXXZ; SCHEMA_FILE_LIST::DereferenceSchemaFileList(void)
0x18004df76  lea     rcx, [rsp+300h+var_2B0]; this
0x18004df7b  call    ??1PARSE_ERROR_INFO@@UEAA@XZ; PARSE_ERROR_INFO::~PARSE_ERROR_INFO(void)
0x18004df80  lea     rcx, [rbp+200h+var_270]
0x18004df84  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004df8a  mov     eax, ebx
0x18004df8c  mov     rcx, [rbp+200h+var_20]
0x18004df93  xor     rcx, rsp; StackCookie
0x18004df96  call    __security_check_cookie
0x18004df9b  mov     rbx, [rsp+300h+arg_10]
0x18004dfa3  add     rsp, 2F0h
0x18004dfaa  pop     r14
0x18004dfac  pop     rsi
0x18004dfad  pop     rbp
0x18004dfae  retn
```
