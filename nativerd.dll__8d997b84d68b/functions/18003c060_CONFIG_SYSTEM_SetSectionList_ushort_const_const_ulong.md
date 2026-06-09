# CONFIG_SYSTEM::SetSectionList(ushort const * * const,ulong)

- ea: `0x18003c060`
- end: `0x18003c1a4`
- name: `?SetSectionList@CONFIG_SYSTEM@@UEAAJQEAPEBGK@Z`
- size: `324`
- prototype: `__int64 __fastcall(CONFIG_SYSTEM *__hidden this, const unsigned __int16 **const, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18001a684`
- `0x18001a7d0`
- `0x18001c250`
- `0x180039778`
- `0x18003c060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c0e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c0e4`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003c11f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003c11f`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003c179`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003c179`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18003c0d6`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18003c0d6`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18003c0af`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18003c0af`

## pseudocode

```c
__int64 __fastcall CONFIG_SYSTEM::SetSectionList(
        CONFIG_SYSTEM *this,
        const unsigned __int16 **const a2,
        unsigned int a3)
{
  int v6; // ebx
  MULTISZ *v7; // rax
  MULTISZ *v8; // rax
  __int64 i; // rbx
  signed int LastError; // eax
  SCHEMA_TABLE *v11; // rcx
  int v12; // eax

  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  if ( *((_QWORD *)this + 138) )
    return (unsigned int)-2147024846;
  v7 = (MULTISZ *)operator new(0x38u);
  if ( !v7 )
  {
    *((_QWORD *)this + 138) = 0;
    return (unsigned int)-2147024888;
  }
  v8 = MULTISZ::MULTISZ(v7);
  *((_QWORD *)this + 138) = v8;
  if ( !v8 )
    return (unsigned int)-2147024888;
  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
  {
    if ( !MULTISZ::Append(*((MULTISZ **)this + 138), a2[i]) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return (unsigned int)v6;
    }
  }
  v6 = CONFIG_CACHE::PurgeCache((CONFIG_SYSTEM *)((char *)this + 32));
  if ( v6 >= 0 )
  {
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_schemaTableLock);
    v11 = (SCHEMA_TABLE *)*((_QWORD *)this + 129);
    if ( v11 )
    {
      v12 = SCHEMA_TABLE::TrimSchema(v11, *((struct MULTISZ **)this + 138));
      if ( v12 >= 0 )
      {
        v6 = v12;
        if ( *((SCHEMA_TABLE **)this + 129) == g_pSchemaTable )
        {
          SCHEMA_TABLE::DereferenceSchemaTable(g_pSchemaTable);
          g_pSchemaTable = 0;
        }
      }
      else
      {
        v6 = 0;
        if ( v12 != -2147024864 )
          v6 = v12;
      }
    }
    else
    {
      v6 = -2147024883;
    }
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_schemaTableLock);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003c060  push    rbx
0x18003c062  push    rsi
0x18003c063  push    rdi
0x18003c064  push    r14
0x18003c066  sub     rsp, 28h
0x18003c06a  mov     esi, r8d
0x18003c06d  mov     r14, rdx
0x18003c070  mov     rdi, rcx
0x18003c073  test    rdx, rdx
0x18003c076  jz      loc_18003C193
0x18003c07c  test    r8d, r8d
0x18003c07f  jz      loc_18003C193
0x18003c085  cmp     qword ptr [rcx+450h], 0
0x18003c08d  jz      short loc_18003C099
0x18003c08f  mov     ebx, 80070032h
0x18003c094  jmp     loc_18003C198
0x18003c099  mov     ecx, 38h ; '8'; Size
0x18003c09e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c0a3  test    rax, rax
0x18003c0a6  jz      loc_18003C181
0x18003c0ac  mov     rcx, rax
0x18003c0af  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18003c0b5  mov     [rdi+450h], rax
0x18003c0bc  test    rax, rax
0x18003c0bf  jz      loc_18003C18C
0x18003c0c5  xor     ebx, ebx
0x18003c0c7  cmp     ebx, esi
0x18003c0c9  jnb     short loc_18003C102
0x18003c0cb  mov     rdx, [r14+rbx*8]
0x18003c0cf  mov     rcx, [rdi+450h]
0x18003c0d6  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18003c0dc  test    eax, eax
0x18003c0de  jz      short loc_18003C0E4
0x18003c0e0  inc     ebx
0x18003c0e2  jmp     short loc_18003C0C7
0x18003c0e4  call    cs:__imp_GetLastError
0x18003c0ea  mov     ebx, eax
0x18003c0ec  test    eax, eax
0x18003c0ee  jle     loc_18003C198
0x18003c0f4  movzx   ebx, ax
0x18003c0f7  or      ebx, 80070000h
0x18003c0fd  jmp     loc_18003C198
0x18003c102  lea     rcx, [rdi+20h]; this
0x18003c106  call    ?PurgeCache@CONFIG_CACHE@@QEAAJXZ; CONFIG_CACHE::PurgeCache(void)
0x18003c10b  mov     ebx, eax
0x18003c10d  test    eax, eax
0x18003c10f  js      loc_18003C198
0x18003c115  lea     rsi, ?g_schemaTableLock@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_schemaTableLock
0x18003c11c  mov     rcx, rsi
0x18003c11f  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18003c125  mov     rcx, [rdi+408h]; this
0x18003c12c  test    rcx, rcx
0x18003c12f  jnz     short loc_18003C138
0x18003c131  mov     ebx, 8007000Dh
0x18003c136  jmp     short loc_18003C176
0x18003c138  mov     rdx, [rdi+450h]; struct MULTISZ *
0x18003c13f  call    ?TrimSchema@SCHEMA_TABLE@@QEAAJPEAVMULTISZ@@@Z; SCHEMA_TABLE::TrimSchema(MULTISZ *)
0x18003c144  test    eax, eax
0x18003c146  jns     short loc_18003C154
0x18003c148  xor     ebx, ebx
0x18003c14a  cmp     eax, 80070020h
0x18003c14f  cmovnz  ebx, eax
0x18003c152  jmp     short loc_18003C176
0x18003c154  mov     rcx, cs:?g_pSchemaTable@@3PEAVSCHEMA_TABLE@@EA; this
0x18003c15b  mov     ebx, eax
0x18003c15d  cmp     [rdi+408h], rcx
0x18003c164  jnz     short loc_18003C176
0x18003c166  call    ?DereferenceSchemaTable@SCHEMA_TABLE@@QEAAXXZ; SCHEMA_TABLE::DereferenceSchemaTable(void)
0x18003c16b  mov     cs:?g_pSchemaTable@@3PEAVSCHEMA_TABLE@@EA, 0; SCHEMA_TABLE * g_pSchemaTable
0x18003c176  mov     rcx, rsi
0x18003c179  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18003c17f  jmp     short loc_18003C198
0x18003c181  mov     qword ptr [rdi+450h], 0
0x18003c18c  mov     ebx, 80070008h
0x18003c191  jmp     short loc_18003C198
0x18003c193  mov     ebx, 80070057h
0x18003c198  mov     eax, ebx
0x18003c19a  add     rsp, 28h
0x18003c19e  pop     r14
0x18003c1a0  pop     rdi
0x18003c1a1  pop     rsi
0x18003c1a2  pop     rbx
0x18003c1a3  retn
```
