# CCertThumbprintsAndSidsMapping::GetSidsForThumbs(CHashValueStringList *,tagBLOB * *,ulong *)

- ea: `0x18001f7b8`
- end: `0x18001f948`
- name: `?GetSidsForThumbs@CCertThumbprintsAndSidsMapping@@QEAAJPEAVCHashValueStringList@@PEAPEAUtagBLOB@@PEAK@Z`
- size: `400`
- prototype: `__int64 __fastcall(CCertThumbprintsAndSidsMapping *__hidden this, struct CHashValueStringList *, struct tagBLOB **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800219a0`

## callees

- `0x18001f1a4`
- `0x18001f318`
- `0x18001f5f0`
- `0x18001f7b8`
- `0x18001fae0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f908`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f91e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f908`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f91e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f849`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f849`

## pseudocode

```c
__int64 __fastcall CCertThumbprintsAndSidsMapping::GetSidsForThumbs(
        CCertThumbprintsAndSidsMapping *this,
        struct CHashValueStringList *a2,
        struct tagBLOB **a3,
        unsigned int *a4)
{
  int v6; // edi
  unsigned int v7; // ebx
  char *v8; // r12
  __int64 v9; // rax
  __int64 v10; // rax
  int v11; // ecx
  _QWORD *i; // rax
  struct tagBLOB *v13; // r15
  struct tagBLOB *v14; // rsi
  unsigned int j; // ecx
  __int64 v16; // rax
  int v17; // r14d
  __int64 v18; // rax
  unsigned int k; // r14d
  char *v21; // [rsp+30h] [rbp-38h] BYREF
  __int128 v22; // [rsp+38h] [rbp-30h]
  _BYTE v23[32]; // [rsp+48h] [rbp-20h] BYREF
  int Sid; // [rsp+B8h] [rbp+50h] BYREF
  struct tagBLOB **v26; // [rsp+C0h] [rbp+58h]
  struct tagBLOB *v27; // [rsp+C8h] [rbp+60h]

  v26 = a3;
  v6 = 0;
  *a4 = 0;
  *a3 = 0;
  v7 = 0;
  v8 = (char *)a2 + 48;
  v21 = (char *)a2 + 48;
  v22 = 0;
  while ( 1 )
  {
    v9 = CTPLiteSListIterator<CHashValueStringList,CTPKeyedLiteSList<CStringHashKey,CHashValueStringList>>::operator++(&v21);
    if ( !v9 )
      break;
    CStringHashKey::CStringHashKey((CStringHashKey *)v23, *(const wchar_t **)(v9 + 24));
    v10 = CTKPLiteHashMap<CStringHashKey,CHashValueStringList>::Lookup((char *)this + 24, v23);
    v11 = 0;
    if ( v10 )
    {
      for ( i = *(_QWORD **)(v10 + 48); i; i = (_QWORD *)*i )
        ++v11;
    }
    v7 += v11;
  }
  v13 = 0;
  if ( v7 )
  {
    v14 = (struct tagBLOB *)CoTaskMemAlloc(16LL * v7);
    v13 = v14;
    v27 = v14;
    if ( v14 )
    {
      for ( j = 0; j < v7; ++j )
      {
        v16 = j;
        v14[v16].cbSize = 0;
        v14[v16].pBlobData = 0;
      }
    }
    else
    {
      v7 = 0;
      v6 = -2147024882;
    }
    v17 = 0;
    v21 = v8;
    v22 = 0;
    v18 = CTPLiteSListIterator<CHashValueStringList,CTPKeyedLiteSList<CStringHashKey,CHashValueStringList>>::operator++(&v21);
    if ( v6 < 0 )
    {
LABEL_19:
      for ( k = 0; k < v7; ++k )
      {
        if ( v14[k].cbSize )
          CoTaskMemFree(v14[k].pBlobData);
      }
    }
    else
    {
      while ( v18 )
      {
        Sid = 0;
        v6 = CCertThumbprintsAndSidsMapping::CopySidsToBuffer(
               this,
               *(const wchar_t **)(v18 + 24),
               v7 - v17,
               &v14[v17],
               &Sid);
        if ( v6 >= 0 )
          v17 += Sid;
        v18 = CTPLiteSListIterator<CHashValueStringList,CTPKeyedLiteSList<CStringHashKey,CHashValueStringList>>::operator++(&v21);
        if ( v6 < 0 )
          goto LABEL_19;
      }
      v13 = 0;
      *v26 = v14;
      *a4 = v7;
    }
  }
  if ( v13 )
    CoTaskMemFree(v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001f7b8  mov     [rsp-40h+arg_10], r8
0x18001f7bd  mov     [rsp-40h+arg_0], rcx
0x18001f7c2  push    rbp
0x18001f7c3  push    rbx
0x18001f7c4  push    rsi
0x18001f7c5  push    rdi
0x18001f7c6  push    r12
0x18001f7c8  push    r13
0x18001f7ca  push    r14
0x18001f7cc  push    r15
0x18001f7ce  mov     rbp, rsp
0x18001f7d1  sub     rsp, 68h
0x18001f7d5  mov     r13, r9
0x18001f7d8  mov     rsi, rcx
0x18001f7db  xor     edi, edi
0x18001f7dd  mov     [r9], edi
0x18001f7e0  mov     [r8], rdi
0x18001f7e3  xor     ebx, ebx
0x18001f7e5  lea     r12, [rdx+30h]
0x18001f7e9  mov     [rbp+var_38], r12
0x18001f7ed  xorps   xmm0, xmm0
0x18001f7f0  movdqu  [rbp+var_30], xmm0
0x18001f7f5  lea     rcx, [rbp+var_38]
0x18001f7f9  call    ??E?$CTPLiteSListIterator@VCHashValueStringList@@V?$CTPKeyedLiteSList@VCStringHashKey@@VCHashValueStringList@@@@@@QEAAPEAVCHashValueStringList@@XZ; CTPLiteSListIterator<CHashValueStringList,CTPKeyedLiteSList<CStringHashKey,CHashValueStringList>>::operator++(void)
0x18001f7fe  test    rax, rax
0x18001f801  jz      short loc_18001F838
0x18001f803  mov     rdx, [rax+18h]; wchar_t *
0x18001f807  lea     rcx, [rbp+var_20]; this
0x18001f80b  call    ??0CStringHashKey@@QEAA@PEB_W@Z; CStringHashKey::CStringHashKey(wchar_t const *)
0x18001f810  lea     rcx, [rsi+18h]
0x18001f814  lea     rdx, [rbp+var_20]
0x18001f818  call    ?Lookup@?$CTKPLiteHashMap@VCStringHashKey@@VCHashValueStringList@@@@QEBAPEAVCHashValueStringList@@PEBVCStringHashKey@@@Z; CTKPLiteHashMap<CStringHashKey,CHashValueStringList>::Lookup(CStringHashKey const *)
0x18001f81d  xor     ecx, ecx
0x18001f81f  test    rax, rax
0x18001f822  jz      short loc_18001F834
0x18001f824  mov     rax, [rax+30h]
0x18001f828  jmp     short loc_18001F82F
0x18001f82a  inc     ecx
0x18001f82c  mov     rax, [rax]
0x18001f82f  test    rax, rax
0x18001f832  jnz     short loc_18001F82A
0x18001f834  add     ebx, ecx
0x18001f836  jmp     short loc_18001F7F5
0x18001f838  xor     r15d, r15d
0x18001f83b  test    ebx, ebx
0x18001f83d  jz      loc_18001F916
0x18001f843  mov     ecx, ebx
0x18001f845  shl     rcx, 4; cb
0x18001f849  call    cs:__imp_CoTaskMemAlloc
0x18001f84f  mov     rsi, rax
0x18001f852  mov     r15, rax
0x18001f855  mov     [rbp+arg_18], rax
0x18001f859  test    rax, rax
0x18001f85c  jz      short loc_18001F87D
0x18001f85e  xor     ecx, ecx
0x18001f860  mov     eax, ecx
0x18001f862  add     rax, rax
0x18001f865  mov     dword ptr [rsi+rax*8], 0
0x18001f86c  mov     qword ptr [rsi+rax*8+8], 0
0x18001f875  inc     ecx
0x18001f877  cmp     ecx, ebx
0x18001f879  jb      short loc_18001F860
0x18001f87b  jmp     short loc_18001F884
0x18001f87d  xor     ebx, ebx
0x18001f87f  mov     edi, 8007000Eh
0x18001f884  xor     r14d, r14d
0x18001f887  mov     [rbp+var_38], r12
0x18001f88b  xorps   xmm0, xmm0
0x18001f88e  movdqu  [rbp+var_30], xmm0
0x18001f893  lea     rcx, [rbp+var_38]
0x18001f897  call    ??E?$CTPLiteSListIterator@VCHashValueStringList@@V?$CTPKeyedLiteSList@VCStringHashKey@@VCHashValueStringList@@@@@@QEAAPEAVCHashValueStringList@@XZ; CTPLiteSListIterator<CHashValueStringList,CTPKeyedLiteSList<CStringHashKey,CHashValueStringList>>::operator++(void)
0x18001f89c  test    edi, edi
0x18001f89e  js      short loc_18001F8F0
0x18001f8a0  mov     r12, [rbp+arg_0]
0x18001f8a4  test    rax, rax
0x18001f8a7  jz      loc_18001F937
0x18001f8ad  mov     [rbp+arg_8], 0
0x18001f8b4  mov     r9d, r14d
0x18001f8b7  shl     r9, 4
0x18001f8bb  add     r9, rsi; struct tagBLOB *
0x18001f8be  mov     r8d, ebx
0x18001f8c1  sub     r8d, r14d; unsigned int
0x18001f8c4  lea     rcx, [rbp+arg_8]
0x18001f8c8  mov     [rsp+68h+Sid], rcx; Sid
0x18001f8cd  mov     rdx, [rax+18h]; wchar_t *
0x18001f8d1  mov     rcx, r12; this
0x18001f8d4  call    ?CopySidsToBuffer@CCertThumbprintsAndSidsMapping@@AEAAJPEB_WKPEAUtagBLOB@@PEAK@Z; CCertThumbprintsAndSidsMapping::CopySidsToBuffer(wchar_t const *,ulong,tagBLOB *,ulong *)
0x18001f8d9  mov     edi, eax
0x18001f8db  test    eax, eax
0x18001f8dd  js      short loc_18001F8E3
0x18001f8df  add     r14d, [rbp+arg_8]
0x18001f8e3  lea     rcx, [rbp+var_38]
0x18001f8e7  call    ??E?$CTPLiteSListIterator@VCHashValueStringList@@V?$CTPKeyedLiteSList@VCStringHashKey@@VCHashValueStringList@@@@@@QEAAPEAVCHashValueStringList@@XZ; CTPLiteSListIterator<CHashValueStringList,CTPKeyedLiteSList<CStringHashKey,CHashValueStringList>>::operator++(void)
0x18001f8ec  test    edi, edi
0x18001f8ee  jns     short loc_18001F8A4
0x18001f8f0  xor     r14d, r14d
0x18001f8f3  test    ebx, ebx
0x18001f8f5  jz      short loc_18001F916
0x18001f8f7  mov     ecx, r14d
0x18001f8fa  add     rcx, rcx
0x18001f8fd  cmp     dword ptr [rsi+rcx*8], 0
0x18001f901  jz      short loc_18001F90E
0x18001f903  mov     rcx, [rsi+rcx*8+8]; pv
0x18001f908  call    cs:__imp_CoTaskMemFree
0x18001f90e  inc     r14d
0x18001f911  cmp     r14d, ebx
0x18001f914  jb      short loc_18001F8F7
0x18001f916  test    r15, r15
0x18001f919  jz      short loc_18001F924
0x18001f91b  mov     rcx, r15; pv
0x18001f91e  call    cs:__imp_CoTaskMemFree
0x18001f924  mov     eax, edi
0x18001f926  add     rsp, 68h
0x18001f92a  pop     r15
0x18001f92c  pop     r14
0x18001f92e  pop     r13
0x18001f930  pop     r12
0x18001f932  pop     rdi
0x18001f933  pop     rsi
0x18001f934  pop     rbx
0x18001f935  pop     rbp
0x18001f936  retn
0x18001f937  xor     r15d, r15d
0x18001f93a  mov     rax, [rbp+arg_10]
0x18001f93e  mov     [rax], rsi
0x18001f941  mov     [r13+0], ebx
0x18001f945  jmp     short loc_18001F916
```
