# _dynamic_atexit_destructor_for__g_CatToSDK__

- ea: `0x1800040b0`
- end: `0x1800041b3`
- name: `_dynamic_atexit_destructor_for__g_CatToSDK__`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800040b0`
- `0x180007494`
- `0x180021c34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000413f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000413f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *dynamic_atexit_destructor_for__g_CatToSDK__()
{
  LPVOID *v0; // rdi
  LPVOID *v1; // rbx
  _QWORD *v2; // rcx
  _QWORD *v3; // rdx
  __int64 v4; // rax
  _QWORD *i; // rcx
  _UNKNOWN **v6; // rcx
  _QWORD *result; // rax
  CTableInfo *v8; // rcx

  v0 = &pv;
LABEL_2:
  v1 = (LPVOID *)*v0;
  if ( v0 != &pv )
    Map<_GUID,CTableInfo *,HashGUID,CNonFailFastingAllocatorPrivate>::releaseAssoc(&g_CatToSDK, v0);
  while ( v1 != &pv )
  {
    if ( *((int *)v1 + 6) < 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v1 + 6);
      v0 = v1;
      v8 = (CTableInfo *)v1[6];
      if ( v8 )
        CTableInfo::`scalar deleting destructor'(v8);
      goto LABEL_2;
    }
    v1 = (LPVOID *)*v1;
  }
  while ( 1 )
  {
    v2 = pv;
    if ( pv == &pv )
      break;
    if ( pv )
    {
      v3 = (_QWORD *)*((_QWORD *)pv + 1);
      v4 = *(_QWORD *)pv;
      *v3 = *(_QWORD *)pv;
      *(_QWORD *)(v4 + 8) = v3;
      *v2 = v2;
      v2[1] = v2;
      CoTaskMemFree(v2);
    }
  }
  for ( i = qword_1800721E0; qword_1800721E0; i = qword_1800721E0 )
  {
    qword_1800721E0 = (LPVOID)i[2];
    CoTaskMemFree(i);
  }
  CoTaskMemFree(g_CatToSDK);
  v6 = off_1800721F0;
  result = pv;
  *off_1800721F0 = pv;
  result[1] = v6;
  pv = &pv;
  off_1800721F0 = (_UNKNOWN **)&pv;
  return result;
}

```

## disassembly

```asm
0x1800040b0  push    rbx
0x1800040b2  push    rbp
0x1800040b3  push    rsi
0x1800040b4  push    rdi
0x1800040b5  sub     rsp, 28h
0x1800040b9  lea     rsi, pv
0x1800040c0  mov     rdi, rsi
0x1800040c3  lea     rbp, pv
0x1800040ca  mov     rbx, [rdi]
0x1800040cd  cmp     rdi, rbp
0x1800040d0  jnz     loc_180004181
0x1800040d6  cmp     rbx, rbp
0x1800040d9  jnz     loc_180004172
0x1800040df  mov     rcx, cs:pv; pv
0x1800040e6  cmp     rcx, rsi
0x1800040e9  jz      short loc_18000410E
0x1800040eb  test    rcx, rcx
0x1800040ee  jz      short loc_1800040DF
0x1800040f0  mov     rdx, [rcx+8]
0x1800040f4  mov     rax, [rcx]
0x1800040f7  mov     [rdx], rax
0x1800040fa  mov     [rax+8], rdx
0x1800040fe  mov     [rcx], rcx
0x180004101  mov     [rcx+8], rcx
0x180004105  call    cs:__imp_CoTaskMemFree
0x18000410b  nop
0x18000410c  jmp     short loc_1800040DF
0x18000410e  mov     rcx, cs:qword_1800721E0; pv
0x180004115  test    rcx, rcx
0x180004118  jz      short loc_180004138
0x18000411a  mov     rax, [rcx+10h]
0x18000411e  mov     cs:qword_1800721E0, rax
0x180004125  call    cs:__imp_CoTaskMemFree
0x18000412b  nop
0x18000412c  mov     rcx, cs:qword_1800721E0
0x180004133  test    rcx, rcx
0x180004136  jnz     short loc_18000411A
0x180004138  mov     rcx, cs:?g_CatToSDK@@3VCComplusCatalogToSDK@@A; pv
0x18000413f  call    cs:__imp_CoTaskMemFree
0x180004145  nop
0x180004146  mov     rcx, cs:off_1800721F0
0x18000414d  mov     rax, cs:pv
0x180004154  mov     [rcx], rax
0x180004157  mov     [rax+8], rcx
0x18000415b  mov     cs:pv, rsi
0x180004162  mov     cs:off_1800721F0, rsi
0x180004169  add     rsp, 28h
0x18000416d  pop     rdi
0x18000416e  pop     rsi
0x18000416f  pop     rbp
0x180004170  pop     rbx
0x180004171  retn
0x180004172  mov     eax, [rbx+18h]
0x180004175  test    eax, eax
0x180004177  js      short loc_180004195
0x180004179  mov     rbx, [rbx]
0x18000417c  jmp     loc_1800040D6
0x180004181  mov     rdx, rdi
0x180004184  lea     rcx, ?g_CatToSDK@@3VCComplusCatalogToSDK@@A; CComplusCatalogToSDK g_CatToSDK
0x18000418b  call    ?releaseAssoc@?$Map@U_GUID@@PEAVCTableInfo@@VHashGUID@@VCNonFailFastingAllocatorPrivate@@@@AEAAXPEAVAssoc@1@@Z; Map<_GUID,CTableInfo *,HashGUID,CNonFailFastingAllocatorPrivate>::releaseAssoc(Map<_GUID,CTableInfo *,HashGUID,CNonFailFastingAllocatorPrivate>::Assoc *)
0x180004190  jmp     loc_1800040D6
0x180004195  lock inc dword ptr [rbx+18h]
0x180004199  mov     rdi, rbx
0x18000419c  mov     rcx, [rbx+30h]; this
0x1800041a0  test    rcx, rcx
0x1800041a3  jz      loc_1800040CA
0x1800041a9  call    ??_GCTableInfo@@QEAAPEAXI@Z; CTableInfo::`scalar deleting destructor'(uint)
0x1800041ae  jmp     loc_1800040CA
```
