# CTypedHashTable<W3_SITE_TABLE_BY_NAME,W3_SITE,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)

- ea: `0x180020d50`
- end: `0x180020d9a`
- name: `?_AddRefRecord@?$CTypedHashTable@VW3_SITE_TABLE_BY_NAME@@VW3_SITE@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z`
- size: `74`
- prototype: `__int64 __fastcall(W3_SITE *this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180017a34`
- `0x180020d50`

## import_xrefs

- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180020d7f`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180020d7f`

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
0x180020d50  push    rbx
0x180020d52  sub     rsp, 20h
0x180020d56  mov     rbx, rcx
0x180020d59  cmp     edx, 1
0x180020d5c  jnz     short loc_180020D69
0x180020d5e  lock inc dword ptr [rcx+0Ch]
0x180020d62  add     rsp, 20h
0x180020d66  pop     rbx
0x180020d67  retn
0x180020d69  cmp     edx, 0FFFFFFFFh
0x180020d6c  jnz     short loc_180020D93
0x180020d6e  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180020d75  mov     rdx, rbx
0x180020d78  add     rcx, 4D8h
0x180020d7f  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x180020d86  nop     dword ptr [rax+rax+00h]
0x180020d8b  mov     rcx, rbx; this
0x180020d8e  call    ?DereferenceSiteInfo@W3_SITE@@QEAAXXZ; W3_SITE::DereferenceSiteInfo(void)
0x180020d93  add     rsp, 20h
0x180020d97  pop     rbx
0x180020d98  retn
```
