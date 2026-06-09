# CONFIG_SYSTEM::GetSchemaTable(void)

- ea: `0x18003b1ec`
- end: `0x18003b432`
- name: `?GetSchemaTable@CONFIG_SYSTEM@@AEAAJXZ`
- size: `582`
- prototype: `__int64 __fastcall(CONFIG_SYSTEM *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003a00c`

## callees

- `0x180018d88`
- `0x18001a684`
- `0x18001c250`
- `0x180039114`
- `0x18003b1ec`
- `0x180055d04`
- `0x180056070`

## import_xrefs

- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18003b314`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18003b314`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003b388`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003b388`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003b412`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003b412`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003b259`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003b259`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003b2ae`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003b400`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003b2ae`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003b400`

## pseudocode

```c
__int64 __fastcall CONFIG_SYSTEM::GetSchemaTable(CONFIG_SYSTEM *this)
{
  _DWORD *v2; // rdi
  int v3; // r14d
  int v4; // r15d
  int IsEqual; // ebx
  SCHEMA_FILE_LIST *v6; // rcx
  volatile signed __int32 *v7; // rax
  _QWORD *v8; // rax
  SCHEMA_TABLE *v9; // rbx
  int v10; // ebp
  bool v11; // zf
  int v13; // [rsp+A8h] [rbp+10h] BYREF

  v13 = 0;
  v2 = operator new(0x20u);
  if ( !v2 )
    return (unsigned int)-2147024888;
  *(_QWORD *)v2 = &SCHEMA_FILE_LIST::`vftable';
  v2[2] = 1;
  v3 = 0;
  *((_QWORD *)v2 + 2) = 0;
  v4 = 0;
  *((_QWORD *)v2 + 3) = 0;
  IsEqual = SCHEMA_FILE_LIST::Initialize((SCHEMA_FILE_LIST *)v2);
  if ( IsEqual >= 0 )
  {
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_schemaTableLock);
    if ( g_pSchemaTable )
    {
      v6 = (SCHEMA_FILE_LIST *)*((_QWORD *)g_pSchemaTable + 11);
      if ( v6 )
      {
        SCHEMA_FILE_LIST::IsEqual(v6, (struct SCHEMA_FILE_LIST *)v2, &v13);
        if ( v13 )
        {
          v7 = (volatile signed __int32 *)g_pSchemaTable;
          v3 = 1;
          *((_QWORD *)this + 130) = g_pSchemaTable;
          IsEqual = 0;
LABEL_22:
          _InterlockedAdd(v7 + 20, 1u);
          goto LABEL_23;
        }
      }
    }
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_schemaTableLock);
    v8 = operator new(0x60u);
    v9 = (SCHEMA_TABLE *)v8;
    if ( v8 )
    {
      CLKRHashTable::CLKRHashTable(
        (CLKRHashTable *)(v8 + 1),
        "SCHEMA_TABLE",
        (unsigned __int64 (*)(const void *))CTypedHashTable<SCHEMA_TABLE,SCHEMA_ENTRY,unsigned short const *,CLKRHashTable>::_ExtractKey,
        (unsigned int (*)(unsigned __int64))CTypedHashTable<SCHEMA_TABLE,SCHEMA_ENTRY,unsigned short const *,CLKRHashTable>::_CalcKeyHash,
        (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<SCHEMA_TABLE,SCHEMA_ENTRY,unsigned short const *,CLKRHashTable>::_EqualKeys,
        (void (*)(const void *, int))CTypedHashTable<SCHEMA_TABLE,SCHEMA_ENTRY,unsigned short const *,CLKRHashTable>::_AddRefRecord,
        4.0,
        1u,
        0,
        0);
      *((_QWORD *)v9 + 10) = 1;
      *(_QWORD *)v9 = &SCHEMA_TABLE::`vftable';
      *((_QWORD *)v9 + 11) = 0;
    }
    else
    {
      v9 = 0;
    }
    *((_QWORD *)this + 130) = v9;
    if ( v9 )
    {
      v10 = SCHEMA_TABLE::Create(v9, (struct SCHEMA_FILE_LIST *)v2, (CONFIG_SYSTEM *)((char *)this + 1048));
      if ( v10 < 0 )
      {
        SCHEMA_TABLE::DereferenceSchemaTable(*((SCHEMA_TABLE **)this + 130));
        v11 = *((_DWORD *)this + 264) == 1;
        IsEqual = 0;
        *((_QWORD *)this + 130) = 0;
        if ( v11 )
          IsEqual = v10;
        goto LABEL_23;
      }
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_schemaTableLock);
      v4 = 1;
      v13 = 0;
      if ( g_pSchemaTable )
      {
        IsEqual = SCHEMA_FILE_LIST::IsEqual(
                    *((SCHEMA_FILE_LIST **)g_pSchemaTable + 11),
                    (struct SCHEMA_FILE_LIST *)v2,
                    &v13);
        if ( IsEqual < 0 || v13 )
          goto LABEL_23;
        SCHEMA_TABLE::DereferenceSchemaTable(g_pSchemaTable);
      }
      else
      {
        IsEqual = v10;
      }
      v7 = (volatile signed __int32 *)*((_QWORD *)this + 130);
      g_pSchemaTable = (SCHEMA_TABLE *)v7;
      goto LABEL_22;
    }
    IsEqual = -2147024888;
  }
LABEL_23:
  SCHEMA_FILE_LIST::DereferenceSchemaFileList((SCHEMA_FILE_LIST *)v2);
  if ( v3 )
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_schemaTableLock);
  if ( v4 )
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_schemaTableLock);
  return (unsigned int)IsEqual;
}

```

## disassembly

```asm
0x18003b1ec  mov     rax, rsp
0x18003b1ef  push    rbx
0x18003b1f0  push    rbp
0x18003b1f1  push    rsi
0x18003b1f2  push    rdi
0x18003b1f3  push    r12
0x18003b1f5  push    r13
0x18003b1f7  push    r14
0x18003b1f9  push    r15
0x18003b1fb  sub     rsp, 58h
0x18003b1ff  xor     r12d, r12d
0x18003b202  mov     rsi, rcx
0x18003b205  mov     [rax+10h], r12d
0x18003b209  lea     ecx, [r12+20h]; Size
0x18003b20e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b213  mov     rdi, rax
0x18003b216  test    rax, rax
0x18003b219  jz      loc_18003B41A
0x18003b21f  lea     rax, ??_7SCHEMA_FILE_LIST@@6B@; const SCHEMA_FILE_LIST::`vftable'
0x18003b226  mov     rcx, rdi; this
0x18003b229  mov     [rdi], rax
0x18003b22c  lea     r13d, [r12+1]
0x18003b231  mov     [rdi+8], r13d
0x18003b235  mov     r14d, r12d
0x18003b238  mov     [rdi+10h], r12
0x18003b23c  mov     r15d, r12d
0x18003b23f  mov     [rdi+18h], r12
0x18003b243  call    ?Initialize@SCHEMA_FILE_LIST@@QEAAJXZ; SCHEMA_FILE_LIST::Initialize(void)
0x18003b248  mov     ebx, eax
0x18003b24a  test    eax, eax
0x18003b24c  js      loc_18003B3EC
0x18003b252  lea     rcx, ?g_schemaTableLock@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_schemaTableLock
0x18003b259  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18003b25f  mov     rax, cs:?g_pSchemaTable@@3PEAVSCHEMA_TABLE@@EA; SCHEMA_TABLE * g_pSchemaTable
0x18003b266  test    rax, rax
0x18003b269  jz      short loc_18003B2A7
0x18003b26b  mov     rcx, [rax+58h]; this
0x18003b26f  test    rcx, rcx
0x18003b272  jz      short loc_18003B2A7
0x18003b274  lea     r8, [rsp+98h+arg_8]; int *
0x18003b27c  mov     rdx, rdi; struct SCHEMA_FILE_LIST *
0x18003b27f  call    ?IsEqual@SCHEMA_FILE_LIST@@QEAAJPEAV1@PEAH@Z; SCHEMA_FILE_LIST::IsEqual(SCHEMA_FILE_LIST *,int *)
0x18003b284  cmp     [rsp+98h+arg_8], r12d
0x18003b28c  jz      short loc_18003B2A7
0x18003b28e  mov     rax, cs:?g_pSchemaTable@@3PEAVSCHEMA_TABLE@@EA; SCHEMA_TABLE * g_pSchemaTable
0x18003b295  mov     r14d, r13d
0x18003b298  mov     [rsi+410h], rax
0x18003b29f  mov     ebx, r12d
0x18003b2a2  jmp     loc_18003B3E7
0x18003b2a7  lea     rcx, ?g_schemaTableLock@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_schemaTableLock
0x18003b2ae  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18003b2b4  mov     ecx, 60h ; '`'; Size
0x18003b2b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b2be  mov     rbx, rax
0x18003b2c1  test    rax, rax
0x18003b2c4  jz      short loc_18003B32E
0x18003b2c6  movsd   xmm0, cs:__real@4010000000000000
0x18003b2ce  lea     rcx, [rax+8]
0x18003b2d2  mov     [rsp+98h+var_50], r12b
0x18003b2d7  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VSCHEMA_TABLE@@VSCHEMA_ENTRY@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<SCHEMA_TABLE,SCHEMA_ENTRY,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x18003b2de  mov     [rsp+98h+var_58], r12d
0x18003b2e3  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VSCHEMA_TABLE@@VSCHEMA_ENTRY@@PEBGVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<SCHEMA_TABLE,SCHEMA_ENTRY,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x18003b2ea  mov     [rsp+98h+var_60], r13d
0x18003b2ef  lea     r8, ?_ExtractKey@?$CTypedHashTable@VSCHEMA_TABLE@@VSCHEMA_ENTRY@@PEBGVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<SCHEMA_TABLE,SCHEMA_ENTRY,ushort const *,CLKRHashTable>::_ExtractKey(void const *)
0x18003b2f6  movsd   [rsp+98h+var_68], xmm0
0x18003b2fc  lea     rdx, aSchemaTable; "SCHEMA_TABLE"
0x18003b303  mov     [rsp+98h+var_70], rax
0x18003b308  lea     rax, ?_EqualKeys@?$CTypedHashTable@VSCHEMA_TABLE@@VSCHEMA_ENTRY@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<SCHEMA_TABLE,SCHEMA_ENTRY,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x18003b30f  mov     [rsp+98h+var_78], rax
0x18003b314  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x18003b31a  lea     rax, ??_7SCHEMA_TABLE@@6B@; const SCHEMA_TABLE::`vftable'
0x18003b321  mov     [rbx+50h], r13
0x18003b325  mov     [rbx], rax
0x18003b328  mov     [rbx+58h], r12
0x18003b32c  jmp     short loc_18003B331
0x18003b32e  mov     rbx, r12
0x18003b331  mov     [rsi+410h], rbx
0x18003b338  test    rbx, rbx
0x18003b33b  jnz     short loc_18003B347
0x18003b33d  mov     ebx, 80070008h
0x18003b342  jmp     loc_18003B3EC
0x18003b347  lea     r8, [rsi+418h]; struct PARSE_ERROR_INFO *
0x18003b34e  mov     rdx, rdi; struct SCHEMA_FILE_LIST *
0x18003b351  mov     rcx, rbx; this
0x18003b354  call    ?Create@SCHEMA_TABLE@@QEAAJPEAVSCHEMA_FILE_LIST@@PEAVPARSE_ERROR_INFO@@@Z; SCHEMA_TABLE::Create(SCHEMA_FILE_LIST *,PARSE_ERROR_INFO *)
0x18003b359  mov     ebp, eax
0x18003b35b  test    eax, eax
0x18003b35d  jns     short loc_18003B381
0x18003b35f  mov     rcx, [rsi+410h]; this
0x18003b366  call    ?DereferenceSchemaTable@SCHEMA_TABLE@@QEAAXXZ; SCHEMA_TABLE::DereferenceSchemaTable(void)
0x18003b36b  cmp     [rsi+420h], r13d
0x18003b372  mov     ebx, r12d
0x18003b375  mov     [rsi+410h], r12
0x18003b37c  cmovz   ebx, ebp
0x18003b37f  jmp     short loc_18003B3EC
0x18003b381  lea     rcx, ?g_schemaTableLock@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_schemaTableLock
0x18003b388  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18003b38e  mov     rcx, cs:?g_pSchemaTable@@3PEAVSCHEMA_TABLE@@EA; SCHEMA_TABLE * g_pSchemaTable
0x18003b395  mov     r15d, r13d
0x18003b398  mov     [rsp+98h+arg_8], r12d
0x18003b3a0  test    rcx, rcx
0x18003b3a3  jz      short loc_18003B3D7
0x18003b3a5  mov     rcx, [rcx+58h]; this
0x18003b3a9  lea     r8, [rsp+98h+arg_8]; int *
0x18003b3b1  mov     rdx, rdi; struct SCHEMA_FILE_LIST *
0x18003b3b4  call    ?IsEqual@SCHEMA_FILE_LIST@@QEAAJPEAV1@PEAH@Z; SCHEMA_FILE_LIST::IsEqual(SCHEMA_FILE_LIST *,int *)
0x18003b3b9  mov     ebx, eax
0x18003b3bb  test    eax, eax
0x18003b3bd  js      short loc_18003B3EC
0x18003b3bf  cmp     [rsp+98h+arg_8], r12d
0x18003b3c7  jnz     short loc_18003B3EC
0x18003b3c9  mov     rcx, cs:?g_pSchemaTable@@3PEAVSCHEMA_TABLE@@EA; this
0x18003b3d0  call    ?DereferenceSchemaTable@SCHEMA_TABLE@@QEAAXXZ; SCHEMA_TABLE::DereferenceSchemaTable(void)
0x18003b3d5  jmp     short loc_18003B3D9
0x18003b3d7  mov     ebx, ebp
0x18003b3d9  mov     rax, [rsi+410h]
0x18003b3e0  mov     cs:?g_pSchemaTable@@3PEAVSCHEMA_TABLE@@EA, rax; SCHEMA_TABLE * g_pSchemaTable
0x18003b3e7  lock add [rax+50h], r13d
0x18003b3ec  mov     rcx, rdi; this
0x18003b3ef  call    ?DereferenceSchemaFileList@SCHEMA_FILE_LIST@@QEAAXXZ; SCHEMA_FILE_LIST::DereferenceSchemaFileList(void)
0x18003b3f4  test    r14d, r14d
0x18003b3f7  jz      short loc_18003B406
0x18003b3f9  lea     rcx, ?g_schemaTableLock@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_schemaTableLock
0x18003b400  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18003b406  test    r15d, r15d
0x18003b409  jz      short loc_18003B41F
0x18003b40b  lea     rcx, ?g_schemaTableLock@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_schemaTableLock
0x18003b412  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18003b418  jmp     short loc_18003B41F
0x18003b41a  mov     ebx, 80070008h
0x18003b41f  mov     eax, ebx
0x18003b421  add     rsp, 58h
0x18003b425  pop     r15
0x18003b427  pop     r14
0x18003b429  pop     r13
0x18003b42b  pop     r12
0x18003b42d  pop     rdi
0x18003b42e  pop     rsi
0x18003b42f  pop     rbp
0x18003b430  pop     rbx
0x18003b431  retn
```
