# CComExport::FreeAppInfo(CComExport::AppExportInfo *)

- ea: `0x1800524f0`
- end: `0x1800525fe`
- name: `?FreeAppInfo@CComExport@@KAXPEAUAppExportInfo@1@@Z`
- size: `270`
- prototype: `void __fastcall(struct CComExport::AppExportInfo *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180051a60`
- `0x180052ea4`

## callees

- `0x1800524f0`
- `0x180052604`
- `0x1800526e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052506`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052516`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052524`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052558`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052569`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800525d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800525e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052506`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052516`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052524`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052558`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052569`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800525d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800525e1`

## pseudocode

```c
void __fastcall CComExport::FreeAppInfo(struct CComExport::AppExportInfo *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  unsigned int i; // edi
  void *v6; // rcx
  struct _tagDLLINFO *v7; // rcx
  struct _tagPSDLLINFO *v8; // rcx
  unsigned int j; // edi
  void *v10; // rcx

  CoTaskMemFree(*((LPVOID *)a1 + 2));
  v2 = (void *)*((_QWORD *)a1 + 3);
  *((_QWORD *)a1 + 2) = 0;
  CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)a1 + 4);
  *((_QWORD *)a1 + 3) = 0;
  CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)a1 + 5);
  *((_QWORD *)a1 + 4) = 0;
  CoTaskMemFree(v4);
  *((_QWORD *)a1 + 5) = 0;
  if ( *((_QWORD *)a1 + 6) )
  {
    for ( i = 0; i < *((_DWORD *)a1 + 14); ++i )
    {
      v6 = *(void **)(*((_QWORD *)a1 + 6) + 8LL * i);
      if ( v6 )
        CoTaskMemFree(v6);
    }
    CoTaskMemFree(*((LPVOID *)a1 + 6));
    *((_QWORD *)a1 + 6) = 0;
    *((_DWORD *)a1 + 14) = 0;
  }
  v7 = (struct _tagDLLINFO *)*((_QWORD *)a1 + 8);
  if ( v7 )
  {
    CComExport::FreeDllInfo(v7, *((_DWORD *)a1 + 18));
    *((_QWORD *)a1 + 8) = 0;
    *((_DWORD *)a1 + 24) = 0;
  }
  CoTaskMemFree(*((LPVOID *)a1 + 10));
  v8 = (struct _tagPSDLLINFO *)*((_QWORD *)a1 + 11);
  *((_QWORD *)a1 + 10) = 0;
  if ( v8 )
  {
    CComExport::FreePSDllInfo(v8, *((_DWORD *)a1 + 24));
    *((_QWORD *)a1 + 11) = 0;
    *((_DWORD *)a1 + 24) = 0;
  }
  if ( *((_QWORD *)a1 + 13) )
  {
    for ( j = 0; j < *((_DWORD *)a1 + 28); ++j )
    {
      v10 = *(void **)(*((_QWORD *)a1 + 13) + 8LL * j);
      if ( v10 )
        CoTaskMemFree(v10);
    }
    CoTaskMemFree(*((LPVOID *)a1 + 13));
    *((_QWORD *)a1 + 13) = 0;
    *((_DWORD *)a1 + 28) = 0;
  }
}

```

## disassembly

```asm
0x1800524f0  mov     [rsp+arg_0], rbx
0x1800524f5  mov     [rsp+arg_8], rsi
0x1800524fa  push    rdi
0x1800524fb  sub     rsp, 20h
0x1800524ff  mov     rbx, rcx
0x180052502  mov     rcx, [rcx+10h]; pv
0x180052506  call    cs:__imp_CoTaskMemFree
0x18005250c  mov     rcx, [rbx+18h]; pv
0x180052510  xor     esi, esi
0x180052512  mov     [rbx+10h], rsi
0x180052516  call    cs:__imp_CoTaskMemFree
0x18005251c  mov     rcx, [rbx+20h]; pv
0x180052520  mov     [rbx+18h], rsi
0x180052524  call    cs:__imp_CoTaskMemFree
0x18005252a  mov     rcx, [rbx+28h]; pv
0x18005252e  mov     [rbx+20h], rsi
0x180052532  call    cs:__imp_CoTaskMemFree
0x180052538  mov     [rbx+28h], rsi
0x18005253c  cmp     [rbx+30h], rsi
0x180052540  jz      short loc_180052576
0x180052542  mov     edi, esi
0x180052544  cmp     [rbx+38h], esi
0x180052547  jbe     short loc_180052565
0x180052549  mov     rax, [rbx+30h]
0x18005254d  mov     ecx, edi
0x18005254f  mov     rcx, [rax+rcx*8]; pv
0x180052553  test    rcx, rcx
0x180052556  jz      short loc_18005255E
0x180052558  call    cs:__imp_CoTaskMemFree
0x18005255e  inc     edi
0x180052560  cmp     edi, [rbx+38h]
0x180052563  jb      short loc_180052549
0x180052565  mov     rcx, [rbx+30h]; pv
0x180052569  call    cs:__imp_CoTaskMemFree
0x18005256f  mov     [rbx+30h], rsi
0x180052573  mov     [rbx+38h], esi
0x180052576  mov     rcx, [rbx+40h]; struct _tagDLLINFO *
0x18005257a  test    rcx, rcx
0x18005257d  jz      short loc_18005258E
0x18005257f  mov     edx, [rbx+48h]; unsigned int
0x180052582  call    ?FreeDllInfo@CComExport@@KAXPEAU_tagDLLINFO@@K@Z; CComExport::FreeDllInfo(_tagDLLINFO *,ulong)
0x180052587  mov     [rbx+40h], rsi
0x18005258b  mov     [rbx+60h], esi
0x18005258e  mov     rcx, [rbx+50h]; pv
0x180052592  call    cs:__imp_CoTaskMemFree
0x180052598  mov     rcx, [rbx+58h]; struct _tagPSDLLINFO *
0x18005259c  mov     [rbx+50h], rsi
0x1800525a0  test    rcx, rcx
0x1800525a3  jz      short loc_1800525B4
0x1800525a5  mov     edx, [rbx+60h]; unsigned int
0x1800525a8  call    ?FreePSDllInfo@CComExport@@KAXPEAU_tagPSDLLINFO@@K@Z; CComExport::FreePSDllInfo(_tagPSDLLINFO *,ulong)
0x1800525ad  mov     [rbx+58h], rsi
0x1800525b1  mov     [rbx+60h], esi
0x1800525b4  cmp     [rbx+68h], rsi
0x1800525b8  jz      short loc_1800525EE
0x1800525ba  mov     edi, esi
0x1800525bc  cmp     [rbx+70h], esi
0x1800525bf  jbe     short loc_1800525DD
0x1800525c1  mov     rax, [rbx+68h]
0x1800525c5  mov     ecx, edi
0x1800525c7  mov     rcx, [rax+rcx*8]; pv
0x1800525cb  test    rcx, rcx
0x1800525ce  jz      short loc_1800525D6
0x1800525d0  call    cs:__imp_CoTaskMemFree
0x1800525d6  inc     edi
0x1800525d8  cmp     edi, [rbx+70h]
0x1800525db  jb      short loc_1800525C1
0x1800525dd  mov     rcx, [rbx+68h]; pv
0x1800525e1  call    cs:__imp_CoTaskMemFree
0x1800525e7  mov     [rbx+68h], rsi
0x1800525eb  mov     [rbx+70h], esi
0x1800525ee  mov     rbx, [rsp+28h+arg_0]
0x1800525f3  mov     rsi, [rsp+28h+arg_8]
0x1800525f8  add     rsp, 20h
0x1800525fc  pop     rdi
0x1800525fd  retn
```
