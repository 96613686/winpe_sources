# CCatalogCollectionWriter::WriteCollection(void)

- ea: `0x18002b458`
- end: `0x18002b4e4`
- name: `?WriteCollection@CCatalogCollectionWriter@@QEAAJXZ`
- size: `140`
- prototype: `__int64 __fastcall(CCatalogCollectionWriter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180023e00`

## callees

- `0x18002ac94`
- `0x18002afe4`
- `0x18002b458`
- `0x18002bda0`
- `0x18002be2c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002b49a`
- `msvcrt!_wcsicmp` at `0x18002b49a`

## string_xrefs

- `0x18002b484`: `IIsConfigObject`

## pseudocode

```c
__int64 __fastcall CCatalogCollectionWriter::WriteCollection(CCatalogCollectionWriter *this)
{
  __int64 result; // rax
  __int64 i; // rbx
  CCatalogPropertyWriter *v4; // rsi

  result = CCatalogCollectionWriter::BeginWriteCollection(this);
  if ( (int)result >= 0 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 39); i = (unsigned int)(i + 1) )
    {
      v4 = *(CCatalogPropertyWriter **)(*((_QWORD *)this + 18) + 8 * i);
      if ( _wcsicmp(*(const wchar_t **)(*((_QWORD *)v4 + 28) + 8LL), L"IIsConfigObject") )
        result = CCatalogPropertyWriter::WritePropertyShort(v4);
      else
        result = CCatalogPropertyWriter::WritePropertyLong(v4);
      if ( (int)result < 0 )
        return result;
    }
    return CWriter::WriteToFile(*(CWriter **)this, (char *)L"\t\t</Collection>\r\n", g_cchEndCollection, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18002b458  mov     [rsp+arg_0], rbx
0x18002b45d  mov     [rsp+arg_8], rsi
0x18002b462  push    rdi
0x18002b463  sub     rsp, 20h
0x18002b467  mov     rdi, rcx
0x18002b46a  call    ?BeginWriteCollection@CCatalogCollectionWriter@@AEAAJXZ; CCatalogCollectionWriter::BeginWriteCollection(void)
0x18002b46f  test    eax, eax
0x18002b471  js      short loc_18002B4D4
0x18002b473  xor     ebx, ebx
0x18002b475  cmp     ebx, [rdi+9Ch]
0x18002b47b  jnb     short loc_18002B4BB
0x18002b47d  mov     rax, [rdi+90h]
0x18002b484  lea     rdx, aIisconfigobjec; "IIsConfigObject"
0x18002b48b  mov     rsi, [rax+rbx*8]
0x18002b48f  mov     rcx, [rsi+0E0h]
0x18002b496  mov     rcx, [rcx+8]; String1
0x18002b49a  call    cs:__imp__wcsicmp
0x18002b4a0  mov     rcx, rsi; this
0x18002b4a3  test    eax, eax
0x18002b4a5  jnz     short loc_18002B4AE
0x18002b4a7  call    ?WritePropertyLong@CCatalogPropertyWriter@@AEAAJXZ; CCatalogPropertyWriter::WritePropertyLong(void)
0x18002b4ac  jmp     short loc_18002B4B3
0x18002b4ae  call    ?WritePropertyShort@CCatalogPropertyWriter@@AEAAJXZ; CCatalogPropertyWriter::WritePropertyShort(void)
0x18002b4b3  test    eax, eax
0x18002b4b5  js      short loc_18002B4D4
0x18002b4b7  inc     ebx
0x18002b4b9  jmp     short loc_18002B475
0x18002b4bb  mov     r8d, cs:?g_cchEndCollection@@3KA; unsigned int
0x18002b4c2  lea     rdx, aCollection; "\t\t</Collection>\r\n"
0x18002b4c9  mov     rcx, [rdi]; this
0x18002b4cc  xor     r9d, r9d; int
0x18002b4cf  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b4d4  mov     rbx, [rsp+28h+arg_0]
0x18002b4d9  mov     rsi, [rsp+28h+arg_8]
0x18002b4de  add     rsp, 20h
0x18002b4e2  pop     rdi
0x18002b4e3  retn
```
