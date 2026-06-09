# std::unique_ptr<tagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW,CatalogSignerInfoDeleter>::_Delete(void)

- ea: `0x1800370e8`
- end: `0x18003714d`
- name: `?_Delete@?$unique_ptr@UtagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW@@UCatalogSignerInfoDeleter@@@std@@AEAAXXZ`
- size: `101`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180034d8c`
- `0x180036160`
- `0x180036ff0`

## callees

- `0x1800370e8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180037124`
- `msvcrt!??3@YAXPEAX@Z` at `0x180037133`
- `msvcrt!??3@YAXPEAX@Z` at `0x180037124`
- `msvcrt!??3@YAXPEAX@Z` at `0x180037133`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003710e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003713c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003710e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003713c`

## pseudocode

```c
HLOCAL __fastcall std::unique_ptr<tagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW,CatalogSignerInfoDeleter>::_Delete(
        __int64 *a1)
{
  __int64 v1; // rbx
  __int64 i; // rdi
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  HLOCAL result; // rax

  v1 = *a1;
  if ( *a1 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(v1 + 8); i = (unsigned int)(i + 1) )
    {
      v3 = *(void **)(*(_QWORD *)(v1 + 16) + 8 * i);
      if ( v3 )
        LocalFree(v3);
    }
    v4 = *(void **)(v1 + 32);
    if ( v4 )
      operator delete(v4);
    v5 = *(void **)(v1 + 48);
    if ( v5 )
      operator delete(v5);
    return LocalFree((HLOCAL)v1);
  }
  return result;
}

```

## disassembly

```asm
0x1800370e8  mov     [rsp+arg_0], rbx
0x1800370ed  push    rdi
0x1800370ee  sub     rsp, 20h
0x1800370f2  mov     rbx, [rcx]
0x1800370f5  test    rbx, rbx
0x1800370f8  jz      short loc_180037142
0x1800370fa  xor     edi, edi
0x1800370fc  cmp     [rbx+8], edi
0x1800370ff  jbe     short loc_18003711B
0x180037101  mov     rax, [rbx+10h]
0x180037105  mov     rcx, [rax+rdi*8]; hMem
0x180037109  test    rcx, rcx
0x18003710c  jz      short loc_180037114
0x18003710e  call    cs:__imp_LocalFree
0x180037114  inc     edi
0x180037116  cmp     edi, [rbx+8]
0x180037119  jb      short loc_180037101
0x18003711b  mov     rcx, [rbx+20h]
0x18003711f  test    rcx, rcx
0x180037122  jz      short loc_18003712A
0x180037124  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003712a  mov     rcx, [rbx+30h]
0x18003712e  test    rcx, rcx
0x180037131  jz      short loc_180037139
0x180037133  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180037139  mov     rcx, rbx; hMem
0x18003713c  call    cs:__imp_LocalFree
0x180037142  mov     rbx, [rsp+28h+arg_0]
0x180037147  add     rsp, 20h
0x18003714b  pop     rdi
0x18003714c  retn
```
