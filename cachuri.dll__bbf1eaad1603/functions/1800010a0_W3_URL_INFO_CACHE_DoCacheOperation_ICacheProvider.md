# W3_URL_INFO_CACHE::DoCacheOperation(ICacheProvider *)

- ea: `0x1800010a0`
- end: `0x180001375`
- name: `?DoCacheOperation@W3_URL_INFO_CACHE@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVICacheProvider@@@Z`
- size: `725`
- prototype: `__int64 __fastcall(void *, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001080`

## callees

- `0x1800010a0`
- `0x180003010`

## import_xrefs

- `msvcrt!wcschr` at `0x180001167`
- `msvcrt!wcschr` at `0x180001167`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800011ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800011ca`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x180001365`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x180001365`
- `iisutil!?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z` at `0x180001238`
- `iisutil!?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z` at `0x180001238`
- `iisutil!?InsertRecord@TREE_HASH_TABLE@@QEAAJPEAX@Z` at `0x1800012f5`
- `iisutil!?InsertRecord@TREE_HASH_TABLE@@QEAAJPEAX@Z` at `0x1800012f5`

## pseudocode

```c
__int64 __fastcall W3_URL_INFO_CACHE::DoCacheOperation(void *a1, __int64 *a2)
{
  __int64 v2; // rax
  TREE_HASH_TABLE *v3; // rbp
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rdx
  int v8; // r8d
  __int64 v9; // r8
  __int64 v10; // r14
  const unsigned __int16 *v11; // rbx
  int v12; // eax
  int v13; // edi
  const wchar_t *i; // rcx
  wchar_t *v15; // rax
  unsigned __int16 j; // cx
  unsigned int v17; // ebx
  DWORD TickCount; // eax
  __int64 v19; // rdx
  _QWORD *v20; // r8
  __int64 v21; // rdx
  __int64 (*v23)(void); // rax
  void (__fastcall ***v24)(_QWORD, __int64, __int64); // rax
  void (__fastcall ***v25)(_QWORD, __int64, __int64); // rax
  void *v26; // rax
  void (__fastcall ***v27)(_QWORD, __int64, __int64); // rbx
  void *v28; // [rsp+40h] [rbp+8h] BYREF
  __int64 v29; // [rsp+48h] [rbp+10h]

  v28 = a1;
  v2 = *a2;
  v3 = (TREE_HASH_TABLE *)g_pUriCache;
  v28 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *))(v2 + 16))(a2);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  v7 = 0;
  do
  {
    v8 = *(unsigned __int16 *)(v6 + 2 * v7++);
    v9 = v8 - (unsigned int)aUri[v7 - 1];
  }
  while ( !(_DWORD)v9 && v7 != 4 );
  if ( (_DWORD)v9 )
    return 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, const wchar_t *))(*a2 + 16))(a2, v7, v9, L"URI");
  v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 72LL))(v10);
  v12 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 8))(a2);
  if ( v12 == 1 )
  {
    v13 = 0;
    for ( i = v11; ; i = v15 + 1 )
    {
      v15 = wcschr(i, 0x2Fu);
      if ( !v15 )
        break;
      if ( ++v13 > g_dwMaxSegments )
        return 1;
    }
    for ( j = *v11; *v11; j = *v11 )
    {
      ++v11;
      LODWORD(v15) = j + 101 * (_DWORD)v15;
    }
    v17 = 314159269 * (int)v15 % 0x3B9ACA07u;
    LODWORD(v29) = v17;
    TickCount = GetTickCount();
    v19 = *((_QWORD *)v3 + 6);
    HIDWORD(v29) = TickCount;
    if ( v19 )
    {
      v20 = (_QWORD *)(v19 + 8LL * (v17 & 0x3FF));
      v21 = HIDWORD(*v20);
      if ( v17 == (unsigned int)*v20 )
      {
        *v20 = 0;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 64LL))(v10, v21);
        v26 = (void *)(*(__int64 (__fastcall **)(__int64 *))(*a2 + 24))(a2);
        if ( (int)TREE_HASH_TABLE::InsertRecord(v3, v26) >= 0 )
        {
          v27 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
          (**v27)(v27, 5, 1);
          (**v27)(v27, 6, 1);
        }
        return 1;
      }
      if ( TickCount - (unsigned int)v21 > 0x3E8 )
        *v20 = v29;
    }
    return 0;
  }
  if ( !v12 )
  {
    TREE_HASH_TABLE::FindRecord(v3, v11, &v28);
    v23 = *(__int64 (**)(void))(*(_QWORD *)g_pGlobalInfo + 96LL);
    if ( v28 )
    {
      v24 = (void (__fastcall ***)(_QWORD, __int64, __int64))v23();
      (**v24)(v24, 8, 1);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v28 + 24LL))(v28);
      (*(void (__fastcall **)(__int64 *, void *))(*a2 + 32))(a2, v28);
      return 1;
    }
    v25 = (void (__fastcall ***)(_QWORD, __int64, __int64))v23();
    (**v25)(v25, 9, 1);
    return 0;
  }
  if ( (unsigned int)(v12 - 2) > 1 )
    return 0;
  TREE_HASH_TABLE::DeletePath(v3, v11);
  return 1;
}

```

## disassembly

```asm
0x1800010a0  mov     [rsp+arg_0], rcx
0x1800010a5  push    rbp
0x1800010a6  push    rsi
0x1800010a7  sub     rsp, 28h
0x1800010ab  mov     rax, [rdx]
0x1800010ae  mov     rcx, rdx
0x1800010b1  mov     rbp, cs:?g_pUriCache@@3PEAVW3_URL_INFO_CACHE@@EA; W3_URL_INFO_CACHE * g_pUriCache
0x1800010b8  mov     rsi, rdx
0x1800010bb  mov     [rsp+38h+arg_0], 0
0x1800010c4  mov     rax, [rax+10h]
0x1800010c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010cd  mov     r8, rax
0x1800010d0  mov     rcx, [rax]
0x1800010d3  mov     rax, [rcx+8]
0x1800010d7  mov     rcx, r8
0x1800010da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010df  xor     edx, edx
0x1800010e1  lea     r9, aUri; "URI"
0x1800010e8  nop     dword ptr [rax+rax+00000000h]
0x1800010f0  movzx   r8d, word ptr [rax+rdx*2]
0x1800010f5  inc     rdx
0x1800010f8  movzx   ecx, word ptr [r9+rdx*2-2]
0x1800010fe  sub     r8d, ecx
0x180001101  jnz     short loc_180001109
0x180001103  cmp     rdx, 4
0x180001107  jnz     short loc_1800010F0
0x180001109  mov     [rsp+38h+arg_10], rbx
0x18000110e  mov     [rsp+38h+arg_18], rdi
0x180001113  mov     [rsp+38h+var_18], r14
0x180001118  test    r8d, r8d
0x18000111b  jnz     loc_18000120D
0x180001121  mov     rax, [rsi]
0x180001124  mov     rcx, rsi
0x180001127  mov     rax, [rax+10h]
0x18000112b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001130  mov     r14, rax
0x180001133  mov     rcx, [rax]
0x180001136  mov     rax, [rcx+48h]
0x18000113a  mov     rcx, r14
0x18000113d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001142  mov     rcx, [rsi]
0x180001145  mov     rbx, rax
0x180001148  mov     rax, [rcx+8]
0x18000114c  mov     rcx, rsi
0x18000114f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001154  cmp     eax, 1
0x180001157  jnz     loc_180001225
0x18000115d  xor     edi, edi
0x18000115f  mov     rcx, rbx; Str
0x180001162  mov     edx, 2Fh ; '/'; Ch
0x180001167  call    cs:__imp_wcschr
0x18000116d  test    rax, rax
0x180001170  jz      short loc_180001186
0x180001172  inc     edi
0x180001174  cmp     edi, cs:?g_dwMaxSegments@@3KA; ulong g_dwMaxSegments
0x18000117a  ja      loc_180001347
0x180001180  lea     rcx, [rax+2]
0x180001184  jmp     short loc_180001162
0x180001186  movzx   ecx, word ptr [rbx]
0x180001189  test    cx, cx
0x18000118c  jz      short loc_1800011A4
0x18000118e  xchg    ax, ax
0x180001190  imul    eax, 65h ; 'e'
0x180001193  lea     rbx, [rbx+2]
0x180001197  movzx   ecx, cx
0x18000119a  add     eax, ecx
0x18000119c  movzx   ecx, word ptr [rbx]
0x18000119f  test    cx, cx
0x1800011a2  jnz     short loc_180001190
0x1800011a4  imul    ecx, eax, 12B9B0A5h
0x1800011aa  mov     eax, 12E0BE63h
0x1800011af  mul     ecx
0x1800011b1  mov     eax, ecx
0x1800011b3  sub     eax, edx
0x1800011b5  shr     eax, 1
0x1800011b7  add     eax, edx
0x1800011b9  shr     eax, 1Dh
0x1800011bc  imul    eax, 3B9ACA07h
0x1800011c2  sub     ecx, eax
0x1800011c4  mov     ebx, ecx
0x1800011c6  mov     dword ptr [rsp+38h+arg_8], ecx
0x1800011ca  call    cs:__imp_GetTickCount
0x1800011d0  mov     rdx, [rbp+30h]
0x1800011d4  mov     dword ptr [rsp+38h+arg_8+4], eax
0x1800011d8  test    rdx, rdx
0x1800011db  jz      short loc_18000120D
0x1800011dd  mov     ecx, ebx
0x1800011df  and     ecx, 3FFh
0x1800011e5  lea     r8, [rdx+rcx*8]
0x1800011e9  mov     rcx, [rdx+rcx*8]
0x1800011ed  mov     rdx, rcx
0x1800011f0  shr     rdx, 20h
0x1800011f4  cmp     ebx, ecx
0x1800011f6  jz      loc_1800012CA
0x1800011fc  sub     eax, edx
0x1800011fe  cmp     eax, 3E8h
0x180001203  jbe     short loc_18000120D
0x180001205  mov     rax, [rsp+38h+arg_8]
0x18000120a  mov     [r8], rax
0x18000120d  xor     eax, eax
0x18000120f  mov     r14, [rsp+38h+var_18]
0x180001214  mov     rdi, [rsp+38h+arg_18]
0x180001219  mov     rbx, [rsp+38h+arg_10]
0x18000121e  add     rsp, 28h
0x180001222  pop     rsi
0x180001223  pop     rbp
0x180001224  retn
0x180001225  test    eax, eax
0x180001227  jnz     loc_180001351
0x18000122d  lea     r8, [rsp+38h+arg_0]
0x180001232  mov     rdx, rbx
0x180001235  mov     rcx, rbp
0x180001238  call    cs:__imp_?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z; TREE_HASH_TABLE::FindRecord(ushort const *,void * *)
0x18000123e  cmp     [rsp+38h+arg_0], 0
0x180001244  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000124b  mov     rax, [rcx]
0x18000124e  mov     rax, [rax+60h]
0x180001252  jz      short loc_1800012A4
0x180001254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001259  mov     r9, rax
0x18000125c  mov     edx, 8
0x180001261  mov     r8d, 1
0x180001267  mov     rcx, [rax]
0x18000126a  mov     rax, [rcx]
0x18000126d  mov     rcx, r9
0x180001270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001275  mov     rcx, [rsp+38h+arg_0]
0x18000127a  mov     rax, [rcx]
0x18000127d  mov     rax, [rax+18h]
0x180001281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001286  mov     rax, [rsi]
0x180001289  mov     rcx, rsi
0x18000128c  mov     rdx, [rsp+38h+arg_0]
0x180001291  mov     rax, [rax+20h]
0x180001295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000129a  mov     eax, 1
0x18000129f  jmp     loc_18000120F
0x1800012a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012a9  mov     r9, rax
0x1800012ac  mov     edx, 9
0x1800012b1  mov     r8d, 1
0x1800012b7  mov     rcx, [rax]
0x1800012ba  mov     rax, [rcx]
0x1800012bd  mov     rcx, r9
0x1800012c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012c5  jmp     loc_18000120D
0x1800012ca  mov     qword ptr [r8], 0
0x1800012d1  mov     rcx, r14
0x1800012d4  mov     rax, [r14]
0x1800012d7  mov     rax, [rax+40h]
0x1800012db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012e0  mov     rax, [rsi]
0x1800012e3  mov     rcx, rsi
0x1800012e6  mov     rax, [rax+18h]
0x1800012ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012ef  mov     rdx, rax
0x1800012f2  mov     rcx, rbp
0x1800012f5  call    cs:__imp_?InsertRecord@TREE_HASH_TABLE@@QEAAJPEAX@Z; TREE_HASH_TABLE::InsertRecord(void *)
0x1800012fb  test    eax, eax
0x1800012fd  js      short loc_180001347
0x1800012ff  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180001306  mov     rax, [rcx]
0x180001309  mov     rax, [rax+60h]
0x18000130d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001312  mov     rbx, rax
0x180001315  mov     edx, 5
0x18000131a  mov     r8d, 1
0x180001320  mov     rcx, [rax]
0x180001323  mov     rax, [rcx]
0x180001326  mov     rcx, rbx
0x180001329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000132e  mov     rcx, [rbx]
0x180001331  mov     edx, 6
0x180001336  mov     r8d, 1
0x18000133c  mov     rax, [rcx]
0x18000133f  mov     rcx, rbx
0x180001342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001347  mov     eax, 1
0x18000134c  jmp     loc_18000120F
0x180001351  sub     eax, 2
0x180001354  jz      short loc_18000135F
0x180001356  cmp     eax, 1
0x180001359  jnz     loc_18000120D
0x18000135f  mov     rdx, rbx
0x180001362  mov     rcx, rbp
0x180001365  call    cs:__imp_?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z; TREE_HASH_TABLE::DeletePath(ushort const *)
0x18000136b  mov     eax, 1
0x180001370  jmp     loc_18000120F
```
