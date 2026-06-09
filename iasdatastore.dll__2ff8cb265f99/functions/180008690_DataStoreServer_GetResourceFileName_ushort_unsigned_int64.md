# DataStoreServer::GetResourceFileName(ushort *,unsigned __int64)

- ea: `0x180008690`
- end: `0x1800086c1`
- name: `?GetResourceFileName@DataStoreServer@@MEAAJPEAG_K@Z`
- size: `49`
- prototype: `__int64 __fastcall(DataStoreServer *this, unsigned __int16 *, rsize_t)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008690`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800086b4`
- `msvcrt!wcscpy_s` at `0x1800086b4`

## string_xrefs

- `0x1800086a7`: `iasdatastore.dll`

## pseudocode

```c
__int64 __fastcall DataStoreServer::GetResourceFileName(DataStoreServer *this, unsigned __int16 *a2, rsize_t a3)
{
  if ( a3 < 0x10 )
    return 2147942634LL;
  wcscpy_s(a2, a3, L"iasdatastore.dll");
  return 0;
}

```

## disassembly

```asm
0x180008690  sub     rsp, 28h
0x180008694  mov     rax, r8
0x180008697  mov     r9, rdx
0x18000869a  cmp     r8, 10h
0x18000869e  jnb     short loc_1800086A7
0x1800086a0  mov     eax, 800700EAh
0x1800086a5  jmp     short loc_1800086BC
0x1800086a7  lea     r8, ?m_resourceDLLFileName@DataStoreServer@@0QBGB; "iasdatastore.dll"
0x1800086ae  mov     rdx, rax; SizeInWords
0x1800086b1  mov     rcx, r9; Destination
0x1800086b4  call    cs:__imp_wcscpy_s
0x1800086ba  xor     eax, eax
0x1800086bc  add     rsp, 28h
0x1800086c0  retn
```
