# CTypedHashTable<W3_SITE_TABLE_BY_NAME,W3_SITE,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)

- ea: `0x18001f1d0`
- end: `0x18001f212`
- name: `?_AddRefRecord@?$CTypedHashTable@VW3_SITE_TABLE_BY_NAME@@VW3_SITE@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z`
- size: `66`
- prototype: `__int64 __fastcall(W3_SITE *this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180016700`
- `0x18001f1d0`

## import_xrefs

- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18001f1fe`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18001f1fe`

## pseudocode

```c
void __fastcall CTypedHashTable<W3_SITE_TABLE_BY_NAME,W3_SITE,unsigned short const *,CLKRHashTable>::_AddRefRecord(
        W3_SITE *this,
        int a2)
{
  if ( a2 == 1 )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 3);
  }
  else if ( a2 == -1 )
  {
    CLKRHashTable::DeleteRecord((char *)g_pW3Server + 1240, this);
    W3_SITE::DereferenceSiteInfo(this);
  }
}

```

## disassembly

```asm
0x18001f1d0  push    rbx
0x18001f1d2  sub     rsp, 20h
0x18001f1d6  mov     rbx, rcx
0x18001f1d9  cmp     edx, 1
0x18001f1dc  jnz     short loc_18001F1E8
0x18001f1de  lock inc dword ptr [rcx+0Ch]
0x18001f1e2  add     rsp, 20h
0x18001f1e6  pop     rbx
0x18001f1e7  retn
0x18001f1e8  cmp     edx, 0FFFFFFFFh
0x18001f1eb  jnz     short loc_18001F20C
0x18001f1ed  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18001f1f4  mov     rdx, rbx
0x18001f1f7  add     rcx, 4D8h
0x18001f1fe  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x18001f204  mov     rcx, rbx; this
0x18001f207  call    ?DereferenceSiteInfo@W3_SITE@@QEAAXXZ; W3_SITE::DereferenceSiteInfo(void)
0x18001f20c  add     rsp, 20h
0x18001f210  pop     rbx
0x18001f211  retn
```
