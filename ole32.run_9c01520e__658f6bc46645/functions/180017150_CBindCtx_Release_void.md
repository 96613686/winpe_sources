# CBindCtx::Release(void)

- ea: `0x180017150`
- end: `0x18001736a`
- name: `?Release@CBindCtx@@UEAAKXZ`
- size: `538`
- prototype: `unsigned int __fastcall(CBindCtx *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180017150`
- `0x1800555d8`
- `0x1800ce967`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001728f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800172b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800172cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001728f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800172b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800172cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001731f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001733d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001731f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001733d`

## pseudocode

```c
__int64 __fastcall CBindCtx::Release(CBindCtx *this, unsigned int a2)
{
  __int64 v2; // rdi
  unsigned int m_refs; // ecx
  CBindCtx::CObjList *m_pFirstObj; // rcx
  CMapStringToPtr *m_pMap; // rax
  CMapStringToPtr *v7; // r11
  __int64 v8; // r9
  unsigned int m_nHashTableSize; // edx
  unsigned int v10; // ecx
  CMapKeyToValue::CAssoc **m_pHashTable; // rax
  unsigned int v12; // r10d
  __int64 v13; // rdx
  __int64 *v14; // r8
  CMapStringToPtr *v15; // rdi
  CPlex *m_pBlocks; // r8
  CPlex *pNext; // rbx
  HANDLE v18; // rcx
  HANDLE v19; // rcx
  unsigned int i; // ebx
  CMapKeyToValue::CAssoc *j; // rsi
  CBindCtx::CObjList *m_pNext; // rbx
  __int64 v24; // [rsp+40h] [rbp+8h] BYREF

  v2 = -1;
  m_refs = this->m_refs;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&this->m_refs, 0xFFFFFFFF) != 1 )
    return m_refs - 1;
  if ( this )
  {
    m_pFirstObj = this->m_pFirstObj;
    this->lpVtbl = (struct IBindCtxVtbl *)CBindCtx::`vftable';
    v24 = 0;
    this->m_pFirstObj = 0;
    if ( m_pFirstObj )
    {
      do
      {
        m_pNext = m_pFirstObj->m_pNext;
        CBindCtx::CObjList::`scalar deleting destructor'(m_pFirstObj, a2);
        m_pFirstObj = m_pNext;
      }
      while ( m_pNext );
    }
    m_pMap = this->m_pMap;
    if ( m_pMap )
    {
      if ( m_pMap->m_mkv.m_nCount )
      {
        do
        {
          v7 = this->m_pMap;
          v8 = v2;
          if ( v2 == -1 )
          {
            m_nHashTableSize = v7->m_mkv.m_nHashTableSize;
            v10 = 0;
            if ( m_nHashTableSize )
            {
              m_pHashTable = v7->m_mkv.m_pHashTable;
              do
              {
                v8 = (__int64)*m_pHashTable;
                if ( *m_pHashTable )
                  break;
                ++v10;
                ++m_pHashTable;
              }
              while ( v10 < m_nHashTableSize );
            }
          }
          v2 = *(_QWORD *)v8;
          if ( !*(_QWORD *)v8 )
          {
            v12 = v7->m_mkv.m_nHashTableSize;
            v13 = (unsigned int)(*(_DWORD *)(v8 + 8) + 1);
            if ( (unsigned int)v13 < v12 )
            {
              v14 = (__int64 *)&v7->m_mkv.m_pHashTable[v13];
              do
              {
                v2 = *v14;
                if ( *v14 )
                  break;
                LODWORD(v13) = v13 + 1;
                ++v14;
              }
              while ( (unsigned int)v13 < v12 );
            }
          }
          memcpy_0(&v24, (const void *)(v8 + v7->m_mkv.m_cbKeyInAssoc + 16LL), v7->m_mkv.m_cbValue);
          if ( v24 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
        while ( v2 );
      }
      v15 = this->m_pMap;
      if ( v15 )
      {
        if ( v15->m_mkv.m_pHashTable )
        {
          for ( i = 0; i < v15->m_mkv.m_nHashTableSize; ++i )
          {
            for ( j = v15->m_mkv.m_pHashTable[i]; j; j = j->pNext )
            {
              if ( !v15->m_mkv.m_cbKey )
                CoTaskMemFree(j->key.pKey);
            }
          }
          CoTaskMemFree(v15->m_mkv.m_pHashTable);
          v15->m_mkv.m_pHashTable = 0;
        }
        m_pBlocks = v15->m_mkv.m_pBlocks;
        v15->m_mkv.m_nCount = 0;
        v15->m_mkv.m_pFreeList = 0;
        if ( m_pBlocks )
        {
          do
          {
            pNext = m_pBlocks->pNext;
            v18 = g_hHeap;
            m_pBlocks->pNext = 0;
            HeapFree(v18, 0, m_pBlocks);
            m_pBlocks = pNext;
          }
          while ( pNext );
        }
        v19 = g_hHeap;
        v15->m_mkv.m_pBlocks = 0;
        HeapFree(v19, 0, v15);
      }
    }
    HeapFree(g_hHeap, 0, this);
  }
  return 0;
}

```

## disassembly

```asm
0x180017150  push    rdi
0x180017152  push    r14
0x180017154  sub     rsp, 28h
0x180017158  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001715f  mov     r14, this
0x180017162  mov     ecx, [this+8]
0x180017165  mov     eax, edi
0x180017167  lock xadd [r14+8], eax
0x18001716d  cmp     eax, 1
0x180017170  jnz     loc_1800172EC
0x180017176  mov     [rsp+38h+arg_10], rbp
0x18001717b  xor     ebp, ebp
0x18001717d  test    r14, r14
0x180017180  jz      loc_1800172DC
0x180017186  mov     this, [r14+40h]; this
0x18001718a  lea     rax, ??_7CBindCtx@@6B@; const CBindCtx::`vftable'
0x180017191  mov     [rsp+38h+arg_8], rbx
0x180017196  mov     [r14], rax
0x180017199  mov     [rsp+38h+arg_0], rbp
0x18001719e  mov     [r14+40h], rbp
0x1800171a2  test    this, this
0x1800171a5  jnz     loc_180017353
0x1800171ab  mov     rax, [r14+48h]
0x1800171af  test    rax, rax
0x1800171b2  jz      loc_1800172BF
0x1800171b8  cmp     [rax+28h], ebp
0x1800171bb  jz      loc_18001725B
0x1800171c1  mov     r11, [r14+48h]
0x1800171c5  mov     r9, rdi
0x1800171c8  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800171cc  jnz     short loc_1800171F2
0x1800171ce  mov     edx, [r11+18h]
0x1800171d2  mov     ecx, ebp
0x1800171d4  test    edx, edx
0x1800171d6  jz      short loc_1800171F2
0x1800171d8  mov     rax, [r11+10h]
0x1800171dc  nop     dword ptr [rax+00h]
0x1800171e0  mov     r9, [rax]
0x1800171e3  test    r9, r9
0x1800171e6  jnz     short loc_1800171F2
0x1800171e8  inc     ecx
0x1800171ea  add     rax, 8
0x1800171ee  cmp     ecx, edx
0x1800171f0  jb      short loc_1800171E0
0x1800171f2  mov     rdi, [r9]
0x1800171f5  test    rdi, rdi
0x1800171f8  jnz     short loc_180017224
0x1800171fa  mov     edx, [r9+8]
0x1800171fe  mov     r10d, [r11+18h]
0x180017202  inc     edx
0x180017204  cmp     edx, r10d
0x180017207  jnb     short loc_180017224
0x180017209  mov     rax, [r11+10h]
0x18001720d  lea     r8, [rax+rdx*8]
0x180017211  mov     rdi, [r8]
0x180017214  test    rdi, rdi
0x180017217  jnz     short loc_180017224
0x180017219  inc     edx
0x18001721b  add     r8, 8
0x18001721f  cmp     edx, r10d
0x180017222  jb      short loc_180017211
0x180017224  mov     edx, [r11+8]
0x180017228  lea     this, [rsp+38h+arg_0]; void *
0x18001722d  mov     r8d, [r11]; Size
0x180017230  add     rdx, 10h
0x180017234  add     rdx, r9; Src
0x180017237  call    memcpy_0
0x18001723c  mov     this, [rsp+38h+arg_0]
0x180017241  test    this, this
0x180017244  jz      short loc_180017252
0x180017246  mov     rax, [this]
0x180017249  mov     rax, [rax+10h]
0x18001724d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017252  test    rdi, rdi
0x180017255  jnz     loc_1800171C1
0x18001725b  mov     rdi, [r14+48h]
0x18001725f  test    rdi, rdi
0x180017262  jz      short loc_1800172BF
0x180017264  cmp     [rdi+10h], rbp
0x180017268  jnz     loc_1800172F1
0x18001726e  mov     r8, [rdi+38h]; lpMem
0x180017272  mov     [rdi+28h], ebp
0x180017275  mov     [rdi+30h], rbp
0x180017279  test    r8, r8
0x18001727c  jz      short loc_1800172A3
0x18001727e  xchg    ax, ax
0x180017280  mov     rbx, [r8]
0x180017283  xor     edx, edx; dwFlags
0x180017285  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001728c  mov     [r8], rbp
0x18001728f  call    cs:__imp_HeapFree
0x180017296  nop     dword ptr [rax+rax+00h]
0x18001729b  mov     r8, rbx
0x18001729e  test    rbx, rbx
0x1800172a1  jnz     short loc_180017280
0x1800172a3  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800172aa  mov     r8, rdi; lpMem
0x1800172ad  xor     edx, edx; dwFlags
0x1800172af  mov     [rdi+38h], rbp
0x1800172b3  call    cs:__imp_HeapFree
0x1800172ba  nop     dword ptr [rax+rax+00h]
0x1800172bf  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800172c6  mov     r8, r14; lpMem
0x1800172c9  xor     edx, edx; dwFlags
0x1800172cb  call    cs:__imp_HeapFree
0x1800172d2  nop     dword ptr [rax+rax+00h]
0x1800172d7  mov     rbx, [rsp+38h+arg_8]
0x1800172dc  mov     eax, ebp
0x1800172de  mov     rbp, [rsp+38h+arg_10]
0x1800172e3  add     rsp, 28h
0x1800172e7  pop     r14
0x1800172e9  pop     rdi
0x1800172ea  retn
0x1800172ec  lea     eax, [this-1]
0x1800172ef  jmp     short loc_1800172E3
0x1800172f1  mov     ebx, ebp
0x1800172f3  cmp     [rdi+18h], ebx
0x1800172f6  jbe     short loc_18001731B
0x1800172f8  mov     [rsp+38h+var_18], rsi
0x1800172fd  nop     dword ptr [rax]
0x180017300  mov     rax, [rdi+10h]
0x180017304  mov     ecx, ebx
0x180017306  mov     rsi, [rax+this*8]
0x18001730a  test    rsi, rsi
0x18001730d  jnz     short loc_180017334
0x18001730f  inc     ebx
0x180017311  cmp     ebx, [rdi+18h]
0x180017314  jb      short loc_180017300
0x180017316  mov     rsi, [rsp+38h+var_18]
0x18001731b  mov     this, [rdi+10h]; pv
0x18001731f  call    cs:__imp_CoTaskMemFree
0x180017326  nop     dword ptr [rax+rax+00h]
0x18001732b  mov     [rdi+10h], rbp
0x18001732f  jmp     loc_18001726E
0x180017334  cmp     [rdi+4], ebp
0x180017337  jnz     short loc_180017349
0x180017339  mov     this, [rsi+10h]; pv
0x18001733d  call    cs:__imp_CoTaskMemFree
0x180017344  nop     dword ptr [rax+rax+00h]
0x180017349  mov     rsi, [rsi]
0x18001734c  test    rsi, rsi
0x18001734f  jz      short loc_18001730F
0x180017351  jmp     short loc_180017334
0x180017353  mov     rbx, [this+8]
0x180017357  call    ??_GCObjList@CBindCtx@@QEAAPEAXI@Z; CBindCtx::CObjList::`scalar deleting destructor'(uint)
0x18001735c  mov     this, rbx
0x18001735f  test    rbx, rbx
0x180017362  jz      loc_1800171AB
0x180017368  jmp     short loc_180017353
```
