# IsFolder(tagPROPVARIANT const &)

- ea: `0x180016918`
- end: `0x180016982`
- name: `?IsFolder@@YAHAEBUtagPROPVARIANT@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016ce4`
- `0x180018864`

## callees

- `0x180016918`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001695c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001695c`

## pseudocode

```c
__int64 __fastcall IsFolder(const struct tagPROPVARIANT *a1)
{
  unsigned int v1; // esi
  __int64 i; // rbx
  const WCHAR *v4; // rcx

  v1 = 0;
  if ( a1->vt == 4127 )
  {
    for ( i = 0; (unsigned int)i < a1->lVal; i = (unsigned int)(i + 1) )
    {
      v4 = *(const WCHAR **)&a1->bstrblobVal.pData[8 * i];
      if ( v4 && CompareStringOrdinal(v4, -1, L"folder", -1, 0) == 2 )
        return 1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180016918  mov     [rsp+arg_0], rbx
0x18001691d  mov     [rsp+arg_8], rsi
0x180016922  push    rdi
0x180016923  sub     rsp, 30h
0x180016927  xor     esi, esi
0x180016929  mov     eax, 101Fh
0x18001692e  mov     rdi, rcx
0x180016931  cmp     [rcx], ax
0x180016934  jnz     short loc_180016970
0x180016936  xor     ebx, ebx
0x180016938  cmp     ebx, [rdi+8]
0x18001693b  jnb     short loc_180016970
0x18001693d  mov     rax, [rdi+10h]
0x180016941  mov     rcx, [rax+rbx*8]; lpString1
0x180016945  test    rcx, rcx
0x180016948  jz      short loc_180016967
0x18001694a  or      r9d, 0FFFFFFFFh; cchCount2
0x18001694e  mov     [rsp+38h+bIgnoreCase], esi; bIgnoreCase
0x180016952  or      edx, r9d; cchCount1
0x180016955  lea     r8, aFolder_0; "folder"
0x18001695c  call    cs:__imp_CompareStringOrdinal
0x180016962  cmp     eax, 2
0x180016965  jz      short loc_18001696B
0x180016967  inc     ebx
0x180016969  jmp     short loc_180016938
0x18001696b  mov     esi, 1
0x180016970  mov     rbx, [rsp+38h+arg_0]
0x180016975  mov     eax, esi
0x180016977  mov     rsi, [rsp+38h+arg_8]
0x18001697c  add     rsp, 30h
0x180016980  pop     rdi
0x180016981  retn
```
