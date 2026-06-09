# CAccountData::ReadUserData(ACCOUNTTYPE)

- ea: `0x180008184`
- end: `0x180008275`
- name: `?ReadUserData@CAccountData@@QEAAXW4ACCOUNTTYPE@@@Z`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180009b5c`
- `0x180017f60`

## callees

- `0x180008184`
- `0x180008408`
- `0x18000849c`
- `0x1800085b8`
- `0x1800086cc`
- `0x180026df0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008244`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008244`

## string_xrefs

- `0x1800081e3`: `TempKey`

## pseudocode

```c
void __fastcall CAccountData::ReadUserData(__int64 a1, int a2)
{
  unsigned __int16 *v2; // rdi
  int v4; // edx
  const unsigned __int16 *v5; // rcx
  HKEY v6; // rcx
  const unsigned __int16 *v7; // rcx
  unsigned int v8; // [rsp+38h] [rbp+10h] BYREF

  *(_DWORD *)(a1 + 600) = a2;
  v2 = (unsigned __int16 *)(a1 + 4);
  *(_WORD *)(a1 + 260) = 0;
  *(_WORD *)(a1 + 4) = 0;
  *(_WORD *)(a1 + 430) = 0;
  *(_DWORD *)(a1 + 604) = 0;
  *(_DWORD *)(a1 + 624) = 0;
  *(_DWORD *)a1 = 0;
  if ( (unsigned int)CAccountData::_OpenRegRoot((CAccountData *)a1) )
  {
    v4 = *(_DWORD *)(a1 + 600);
    if ( v4 == 1 )
    {
      v5 = L".DEFAULT";
    }
    else
    {
      v5 = L"TempKey";
      if ( v4 != 2 )
        v5 = 0;
    }
    *v2 = 0;
    if ( g_pfnGetDefaultLayout )
    {
      v8 = 128;
      g_pfnGetDefaultLayout(v5, v2, &v8);
    }
    CAccountData::_ReadDisplayLanguage((CAccountData *)a1);
    CAccountData::_ReadLocation((CAccountData *)a1);
    CAccountData::_ReadUserLocale((CAccountData *)a1);
    v6 = *(HKEY *)(a1 + 616);
    if ( v6 && v6 != HKEY_CURRENT_USER )
    {
      RegCloseKey(v6);
      if ( *(_DWORD *)(a1 + 600) == 2 )
        Intl_UnloadNtUserHive(v7, (char *)(a1 + 608));
    }
    *(_QWORD *)(a1 + 616) = 0;
  }
}

```

## disassembly

```asm
0x180008184  mov     [rsp+arg_0], rbx
0x180008189  push    rdi
0x18000818a  sub     rsp, 20h
0x18000818e  xor     eax, eax
0x180008190  mov     [rcx+258h], edx
0x180008196  lea     rdi, [rcx+4]
0x18000819a  mov     [rcx+104h], ax
0x1800081a1  mov     [rdi], ax
0x1800081a4  mov     rbx, rcx
0x1800081a7  mov     [rcx+1AEh], ax
0x1800081ae  mov     [rcx+25Ch], eax
0x1800081b4  mov     [rcx+270h], eax
0x1800081ba  mov     dword ptr [rcx], 0
0x1800081c0  call    ?_OpenRegRoot@CAccountData@@AEAAHXZ; CAccountData::_OpenRegRoot(void)
0x1800081c5  test    eax, eax
0x1800081c7  jz      loc_18000826A
0x1800081cd  mov     edx, [rbx+258h]
0x1800081d3  cmp     edx, 1
0x1800081d6  jnz     short loc_1800081E1
0x1800081d8  lea     rcx, aDefault; ".DEFAULT"
0x1800081df  jmp     short loc_1800081F1
0x1800081e1  xor     eax, eax
0x1800081e3  lea     rcx, aTempkey; "TempKey"
0x1800081ea  cmp     edx, 2
0x1800081ed  cmovnz  rcx, rax
0x1800081f1  xor     eax, eax
0x1800081f3  mov     [rdi], ax
0x1800081f6  mov     rax, cs:?g_pfnGetDefaultLayout@@3P6AJPEBGPEAGPEAK@ZEA; long (*g_pfnGetDefaultLayout)(ushort const *,ushort *,ulong *)
0x1800081fd  test    rax, rax
0x180008200  jz      short loc_180008217
0x180008202  lea     r8, [rsp+28h+arg_8]
0x180008207  mov     [rsp+28h+arg_8], 80h
0x18000820f  mov     rdx, rdi
0x180008212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008217  mov     rcx, rbx; this
0x18000821a  call    ?_ReadDisplayLanguage@CAccountData@@AEAAXXZ; CAccountData::_ReadDisplayLanguage(void)
0x18000821f  mov     rcx, rbx; this
0x180008222  call    ?_ReadLocation@CAccountData@@AEAAXXZ; CAccountData::_ReadLocation(void)
0x180008227  mov     rcx, rbx; this
0x18000822a  call    ?_ReadUserLocale@CAccountData@@AEAAXXZ; CAccountData::_ReadUserLocale(void)
0x18000822f  mov     rcx, [rbx+268h]; hKey
0x180008236  test    rcx, rcx
0x180008239  jz      short loc_18000825F
0x18000823b  cmp     rcx, 0FFFFFFFF80000001h
0x180008242  jz      short loc_18000825F
0x180008244  call    cs:__imp_RegCloseKey
0x18000824a  cmp     dword ptr [rbx+258h], 2
0x180008251  jnz     short loc_18000825F
0x180008253  lea     rdx, [rbx+260h]; unsigned __int8 *
0x18000825a  call    ?Intl_UnloadNtUserHive@@YAXPEBGPEAE@Z; Intl_UnloadNtUserHive(ushort const *,uchar *)
0x18000825f  mov     qword ptr [rbx+268h], 0
0x18000826a  mov     rbx, [rsp+28h+arg_0]
0x18000826f  add     rsp, 20h
0x180008273  pop     rdi
0x180008274  retn
```
