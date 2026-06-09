# CONFIG_VDIR_TABLE::Initialize(CONFIG_FILE *)

- ea: `0x180056c80`
- end: `0x180056f0e`
- name: `?Initialize@CONFIG_VDIR_TABLE@@QEAAJPEAVCONFIG_FILE@@@Z`
- size: `654`
- prototype: `__int64 __fastcall(CONFIG_VDIR_TABLE *__hidden this, struct CONFIG_FILE *)`
- caller_count: `7`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180003970`
- `0x1800048d0`
- `0x180004a70`
- `0x180005b80`
- `0x180006a20`
- `0x180008d00`
- `0x180016ba0`

## callees

- `0x180014b34`
- `0x18001be64`
- `0x1800266e4`
- `0x18002ff78`
- `0x1800307c4`
- `0x180056948`
- `0x180056c80`
- `0x18005b010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180056ccd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180056ccd`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180056ea4`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180056ea4`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180056eb8`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180056eb8`

## pseudocode

```c
__int64 __fastcall CONFIG_VDIR_TABLE::Initialize(CONFIG_VDIR_TABLE *this, struct CONFIG_FILE *a2)
{
  struct CONFIG_COLLECTION *v2; // rsi
  struct CONFIG_COLLECTION *v4; // rdi
  CONFIG_COLLECTION *v5; // r14
  const unsigned __int16 *ParseErrorFileName; // rax
  int v8; // ebx
  int ConfigElement; // eax
  CONFIG_ELEMENT *v10; // r15
  int DefaultInternalCollection; // eax
  __int64 v12; // rax
  CONFIG_ELEMENT *v13; // r12
  int v14; // eax
  __int64 i; // r12
  struct CONFIG_ELEMENT *v16; // rcx
  struct CONFIG_ELEMENT *v17; // r10
  BOOL v18; // ebx
  __int64 v19; // r14
  struct CONFIG_COLLECTION *v20; // r15
  struct CONFIG_ELEMENT *v21; // rsi
  int v22; // eax
  struct CONFIG_COLLECTION *v24; // [rsp+30h] [rbp-30h] BYREF
  CONFIG_ELEMENT *v25; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int16 *v26; // [rsp+40h] [rbp-20h] BYREF
  struct CONFIG_COLLECTION *v27; // [rsp+48h] [rbp-18h] BYREF
  struct CONFIG_COLLECTION *v28; // [rsp+50h] [rbp-10h]
  int v29; // [rsp+A0h] [rbp+40h] BYREF
  int v30; // [rsp+B0h] [rbp+50h]
  struct CONFIG_COLLECTION *v31; // [rsp+B8h] [rbp+58h] BYREF

  v2 = 0;
  v25 = 0;
  v27 = 0;
  v4 = 0;
  v26 = 0;
  v5 = 0;
  v24 = 0;
  v31 = 0;
  v29 = 0;
  ParseErrorFileName = CONFIG_FILE::QueryParseErrorFileName(a2);
  v8 = STRU::Copy(this, ParseErrorFileName);
  if ( v8 >= 0 )
  {
    ConfigElement = CONFIG_FILE::GetConfigElement(
                      a2,
                      &szDomain,
                      L"system.applicationHost/sites",
                      &v25,
                      (CONFIG_VDIR_TABLE *)((char *)this + 56));
    v10 = v25;
    v8 = ConfigElement;
    if ( ConfigElement >= 0 )
    {
      DefaultInternalCollection = CONFIG_ELEMENT::GetDefaultInternalCollection(v25, &v27);
      v2 = v27;
      v8 = DefaultInternalCollection;
      if ( DefaultInternalCollection >= 0 )
      {
        v12 = 0;
        v28 = v27;
LABEL_5:
        v30 = v12;
        if ( (unsigned int)v12 >= *((_DWORD *)v2 + 8) )
        {
          CONFIG_COLLECTION::DereferenceConfigCollection(v2);
          v2 = 0;
          CONFIG_ELEMENT::DereferenceConfigElement(v10);
          v10 = 0;
          CReaderWriterLock3::WriteLock((CONFIG_VDIR_TABLE *)((char *)this + 144));
          *((_DWORD *)this + 39) = 1;
          CReaderWriterLock3::WriteUnlock((CONFIG_VDIR_TABLE *)((char *)this + 144));
          v8 = 0;
        }
        else
        {
          v13 = *(CONFIG_ELEMENT **)(*((_QWORD *)v2 + 5) + 24 * v12);
          v8 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*((_QWORD *)v13 + 2) + 64LL))(
                 (_QWORD *)v13 + 2,
                 L"name",
                 &v26,
                 0,
                 0);
          if ( v8 >= 0 )
          {
            v14 = CONFIG_ELEMENT::GetDefaultInternalCollection(v13, &v24);
            v4 = v24;
            v8 = v14;
            if ( v14 >= 0 )
            {
              for ( i = 0; ; i = (unsigned int)(i + 1) )
              {
                if ( (unsigned int)i >= *((_DWORD *)v4 + 8) )
                {
                  CONFIG_COLLECTION::DereferenceConfigCollection(v4);
                  v4 = 0;
                  v12 = (unsigned int)(v30 + 1);
                  v24 = 0;
                  goto LABEL_5;
                }
                v27 = *(struct CONFIG_COLLECTION **)(*((_QWORD *)v4 + 5) + 24 * i);
                v8 = CONFIG_ELEMENT::GetDefaultInternalCollection(v27, &v31);
                if ( v8 < 0 )
                {
                  v5 = v31;
                  goto LABEL_24;
                }
                v18 = 0;
                v19 = 0;
                if ( !*((_DWORD *)v31 + 8) )
                  goto LABEL_19;
                v20 = v31;
                v21 = v16;
                do
                {
                  v22 = CONFIG_VDIR_TABLE::AddVdir(
                          this,
                          v21,
                          *(struct CONFIG_ELEMENT **)(*((_QWORD *)v20 + 5) + 24 * v19),
                          v26,
                          &v29);
                  if ( !v18 && v22 >= 0 )
                    v18 = v29 != 0;
                  v19 = (unsigned int)(v19 + 1);
                }
                while ( (unsigned int)v19 < *((_DWORD *)v20 + 8) );
                v4 = v24;
                v2 = v28;
                v10 = v25;
                if ( !v18 )
                  break;
LABEL_20:
                CONFIG_COLLECTION::DereferenceConfigCollection(v31);
                v5 = 0;
                v31 = 0;
              }
              v17 = v27;
LABEL_19:
              CONFIG_VDIR_TABLE::AddVdir(this, v17, 0, v26, 0);
              goto LABEL_20;
            }
          }
        }
      }
    }
LABEL_24:
    if ( v10 )
      CONFIG_ELEMENT::DereferenceConfigElement(v10);
    if ( v2 )
      CONFIG_COLLECTION::DereferenceConfigCollection(v2);
    if ( v4 )
      CONFIG_COLLECTION::DereferenceConfigCollection(v4);
    if ( v5 )
      CONFIG_COLLECTION::DereferenceConfigCollection(v5);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180056c80  mov     [rsp-38h+arg_8], rbx
0x180056c85  push    rbp
0x180056c86  push    rsi
0x180056c87  push    rdi
0x180056c88  push    r12
0x180056c8a  push    r13
0x180056c8c  push    r14
0x180056c8e  push    r15
0x180056c90  mov     rbp, rsp
0x180056c93  sub     rsp, 60h
0x180056c97  xor     esi, esi
0x180056c99  mov     [rbp+var_28], 0
0x180056ca1  mov     r13, rcx
0x180056ca4  mov     [rbp+var_18], rsi
0x180056ca8  xor     edi, edi
0x180056caa  mov     [rbp+var_20], rsi
0x180056cae  xor     r14d, r14d
0x180056cb1  mov     [rbp+var_30], rdi
0x180056cb5  mov     rcx, rdx; this
0x180056cb8  mov     [rbp+arg_18], r14
0x180056cbc  mov     [rbp+arg_0], esi
0x180056cbf  mov     r15, rdx
0x180056cc2  call    ?QueryParseErrorFileName@CONFIG_FILE@@QEBAPEBGXZ; CONFIG_FILE::QueryParseErrorFileName(void)
0x180056cc7  mov     rdx, rax
0x180056cca  mov     rcx, r13
0x180056ccd  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180056cd3  mov     ebx, eax
0x180056cd5  test    eax, eax
0x180056cd7  js      loc_180056EF4
0x180056cdd  lea     rax, [r13+38h]
0x180056ce1  mov     rcx, r15; this
0x180056ce4  lea     r9, [rbp+var_28]; struct CONFIG_ELEMENT **
0x180056ce8  mov     [rsp+60h+var_40], rax; struct PARSE_ERROR_INFO *
0x180056ced  lea     r8, aSystemApplicat_4; "system.applicationHost/sites"
0x180056cf4  lea     rdx, szDomain; unsigned __int16 *
0x180056cfb  call    ?GetConfigElement@CONFIG_FILE@@QEAAJPEBG0PEAPEAVCONFIG_ELEMENT@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_FILE::GetConfigElement(ushort const *,ushort const *,CONFIG_ELEMENT * *,PARSE_ERROR_INFO *)
0x180056d00  mov     r15, [rbp+var_28]
0x180056d04  mov     ebx, eax
0x180056d06  test    eax, eax
0x180056d08  js      loc_180056EC0
0x180056d0e  lea     rdx, [rbp+var_18]; struct CONFIG_COLLECTION **
0x180056d12  mov     rcx, r15; this
0x180056d15  call    ?GetDefaultInternalCollection@CONFIG_ELEMENT@@QEAAJPEAPEAVCONFIG_COLLECTION@@@Z; CONFIG_ELEMENT::GetDefaultInternalCollection(CONFIG_COLLECTION * *)
0x180056d1a  mov     rsi, [rbp+var_18]
0x180056d1e  mov     ebx, eax
0x180056d20  test    eax, eax
0x180056d22  js      loc_180056EC0
0x180056d28  xor     eax, eax
0x180056d2a  mov     [rbp+var_10], rsi
0x180056d2e  mov     [rbp+arg_10], eax
0x180056d31  cmp     eax, [rsi+20h]
0x180056d34  jnb     loc_180056E85
0x180056d3a  lea     rcx, [rax+rax*2]
0x180056d3e  mov     [rsp+60h+var_40], 0
0x180056d47  mov     rax, [rsi+28h]
0x180056d4b  lea     r8, [rbp+var_20]
0x180056d4f  xor     r9d, r9d
0x180056d52  lea     rdx, aName; "name"
0x180056d59  mov     r12, [rax+rcx*8]
0x180056d5d  lea     rcx, [r12+10h]
0x180056d62  mov     rax, [rcx]
0x180056d65  mov     rax, [rax+40h]
0x180056d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d6e  mov     ebx, eax
0x180056d70  test    eax, eax
0x180056d72  js      loc_180056EC0
0x180056d78  lea     rdx, [rbp+var_30]; struct CONFIG_COLLECTION **
0x180056d7c  mov     rcx, r12; this
0x180056d7f  call    ?GetDefaultInternalCollection@CONFIG_ELEMENT@@QEAAJPEAPEAVCONFIG_COLLECTION@@@Z; CONFIG_ELEMENT::GetDefaultInternalCollection(CONFIG_COLLECTION * *)
0x180056d84  mov     rdi, [rbp+var_30]
0x180056d88  mov     ebx, eax
0x180056d8a  test    eax, eax
0x180056d8c  js      loc_180056EC0
0x180056d92  xor     r12d, r12d
0x180056d95  lea     ebx, [r12+1]
0x180056d9a  cmp     r12d, [rdi+20h]
0x180056d9e  jnb     loc_180056E67
0x180056da4  mov     rax, [rdi+28h]
0x180056da8  lea     rcx, [r12+r12*2]
0x180056dac  lea     rdx, [rbp+arg_18]; struct CONFIG_COLLECTION **
0x180056db0  mov     r10, [rax+rcx*8]
0x180056db4  mov     rcx, r10; this
0x180056db7  mov     [rbp+var_18], r10
0x180056dbb  call    ?GetDefaultInternalCollection@CONFIG_ELEMENT@@QEAAJPEAPEAVCONFIG_COLLECTION@@@Z; CONFIG_ELEMENT::GetDefaultInternalCollection(CONFIG_COLLECTION * *)
0x180056dc0  mov     ebx, eax
0x180056dc2  test    eax, eax
0x180056dc4  js      loc_180056E7F
0x180056dca  mov     rax, [rbp+arg_18]
0x180056dce  xor     ebx, ebx
0x180056dd0  xor     r14d, r14d
0x180056dd3  cmp     [rax+20h], ebx
0x180056dd6  jbe     short loc_180056E30
0x180056dd8  mov     r15, rax
0x180056ddb  lea     edi, [rbx+1]
0x180056dde  mov     rsi, rcx
0x180056de1  mov     r8, [r15+28h]
0x180056de5  lea     rcx, [r14+r14*2]
0x180056de9  mov     r9, [rbp+var_20]; unsigned __int16 *
0x180056ded  lea     rax, [rbp+arg_0]
0x180056df1  mov     rdx, rsi; struct CONFIG_ELEMENT *
0x180056df4  mov     [rsp+60h+var_40], rax; int *
0x180056df9  mov     r8, [r8+rcx*8]; struct CONFIG_ELEMENT *
0x180056dfd  mov     rcx, r13; this
0x180056e00  call    ?AddVdir@CONFIG_VDIR_TABLE@@AEAAJPEAVCONFIG_ELEMENT@@0PEBGPEAH@Z; CONFIG_VDIR_TABLE::AddVdir(CONFIG_ELEMENT *,CONFIG_ELEMENT *,ushort const *,int *)
0x180056e05  test    ebx, ebx
0x180056e07  jnz     short loc_180056E13
0x180056e09  test    eax, eax
0x180056e0b  js      short loc_180056E13
0x180056e0d  cmp     [rbp+arg_0], ebx
0x180056e10  cmovnz  ebx, edi
0x180056e13  add     r14d, edi
0x180056e16  cmp     r14d, [r15+20h]
0x180056e1a  jb      short loc_180056DE1
0x180056e1c  mov     rdi, [rbp+var_30]
0x180056e20  mov     rsi, [rbp+var_10]
0x180056e24  mov     r15, [rbp+var_28]
0x180056e28  test    ebx, ebx
0x180056e2a  jnz     short loc_180056E4B
0x180056e2c  mov     r10, [rbp+var_18]
0x180056e30  mov     r9, [rbp+var_20]; unsigned __int16 *
0x180056e34  xor     r8d, r8d; struct CONFIG_ELEMENT *
0x180056e37  mov     rdx, r10; struct CONFIG_ELEMENT *
0x180056e3a  mov     [rsp+60h+var_40], 0; int *
0x180056e43  mov     rcx, r13; this
0x180056e46  call    ?AddVdir@CONFIG_VDIR_TABLE@@AEAAJPEAVCONFIG_ELEMENT@@0PEBGPEAH@Z; CONFIG_VDIR_TABLE::AddVdir(CONFIG_ELEMENT *,CONFIG_ELEMENT *,ushort const *,int *)
0x180056e4b  mov     rcx, [rbp+arg_18]; this
0x180056e4f  call    ?DereferenceConfigCollection@CONFIG_COLLECTION@@QEAAXXZ; CONFIG_COLLECTION::DereferenceConfigCollection(void)
0x180056e54  xor     r14d, r14d
0x180056e57  mov     [rbp+arg_18], r14
0x180056e5b  lea     ebx, [r14+1]
0x180056e5f  add     r12d, ebx
0x180056e62  jmp     loc_180056D9A
0x180056e67  mov     rcx, rdi; this
0x180056e6a  call    ?DereferenceConfigCollection@CONFIG_COLLECTION@@QEAAXXZ; CONFIG_COLLECTION::DereferenceConfigCollection(void)
0x180056e6f  mov     eax, [rbp+arg_10]
0x180056e72  xor     edi, edi
0x180056e74  add     eax, ebx
0x180056e76  mov     [rbp+var_30], rdi
0x180056e7a  jmp     loc_180056D2E
0x180056e7f  mov     r14, [rbp+arg_18]
0x180056e83  jmp     short loc_180056EC0
0x180056e85  mov     rcx, rsi; this
0x180056e88  call    ?DereferenceConfigCollection@CONFIG_COLLECTION@@QEAAXXZ; CONFIG_COLLECTION::DereferenceConfigCollection(void)
0x180056e8d  mov     rcx, r15; this
0x180056e90  xor     esi, esi
0x180056e92  call    ?DereferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::DereferenceConfigElement(void)
0x180056e97  lea     rbx, [r13+90h]
0x180056e9e  xor     r15d, r15d
0x180056ea1  mov     rcx, rbx
0x180056ea4  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180056eaa  mov     rcx, rbx
0x180056ead  mov     dword ptr [r13+9Ch], 1
0x180056eb8  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180056ebe  xor     ebx, ebx
0x180056ec0  test    r15, r15
0x180056ec3  jz      short loc_180056ECD
0x180056ec5  mov     rcx, r15; this
0x180056ec8  call    ?DereferenceConfigElement@CONFIG_ELEMENT@@QEAAXXZ; CONFIG_ELEMENT::DereferenceConfigElement(void)
0x180056ecd  test    rsi, rsi
0x180056ed0  jz      short loc_180056EDA
0x180056ed2  mov     rcx, rsi; this
0x180056ed5  call    ?DereferenceConfigCollection@CONFIG_COLLECTION@@QEAAXXZ; CONFIG_COLLECTION::DereferenceConfigCollection(void)
0x180056eda  test    rdi, rdi
0x180056edd  jz      short loc_180056EE7
0x180056edf  mov     rcx, rdi; this
0x180056ee2  call    ?DereferenceConfigCollection@CONFIG_COLLECTION@@QEAAXXZ; CONFIG_COLLECTION::DereferenceConfigCollection(void)
0x180056ee7  test    r14, r14
0x180056eea  jz      short loc_180056EF4
0x180056eec  mov     rcx, r14; this
0x180056eef  call    ?DereferenceConfigCollection@CONFIG_COLLECTION@@QEAAXXZ; CONFIG_COLLECTION::DereferenceConfigCollection(void)
0x180056ef4  mov     eax, ebx
0x180056ef6  mov     rbx, [rsp+60h+arg_8]
0x180056efe  add     rsp, 60h
0x180056f02  pop     r15
0x180056f04  pop     r14
0x180056f06  pop     r13
0x180056f08  pop     r12
0x180056f0a  pop     rdi
0x180056f0b  pop     rsi
0x180056f0c  pop     rbp
0x180056f0d  retn
```
