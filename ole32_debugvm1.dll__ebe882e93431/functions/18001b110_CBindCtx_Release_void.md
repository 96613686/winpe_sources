# CBindCtx::Release(void)

- ea: `0x18001b110`
- end: `0x18001b317`
- name: `?Release@CBindCtx@@UEAAKXZ`
- size: `519`
- prototype: `unsigned int __fastcall(CBindCtx *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001b110`
- `0x1800633fc`
- `0x1800c4651`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b24f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b26d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b27f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b24f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b26d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b27f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b2cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b2e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b2cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b2e9`

## pseudocode

```c
__int64 __fastcall CBindCtx::Release(CBindCtx *this, unsigned int a2)
{
  __int64 pNext; // rdi
  unsigned int m_refs; // ecx
  CBindCtx::CObjList *m_pFirstObj; // rcx
  CMapStringToPtr *m_pMap; // rax
  CMapStringToPtr *v7; // r10
  CMapKeyToValue::CAssoc *v8; // rdx
  unsigned int m_nHashTableSize; // r8d
  unsigned int i; // ecx
  unsigned int v11; // r8d
  __int64 j; // rcx
  CMapStringToPtr *v13; // rdi
  CPlex *m_pBlocks; // r8
  CPlex *v15; // rbx
  HANDLE v16; // rcx
  HANDLE v17; // rcx
  unsigned int k; // ebx
  CMapKeyToValue::CAssoc *m; // rsi
  CBindCtx::CObjList *m_pNext; // rbx
  __int64 v22; // [rsp+40h] [rbp+8h] BYREF

  pNext = -1;
  m_refs = this->m_refs;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&this->m_refs, 0xFFFFFFFF) != 1 )
    return m_refs - 1;
  if ( this )
  {
    m_pFirstObj = this->m_pFirstObj;
    this->lpVtbl = (struct IBindCtxVtbl *)CBindCtx::`vftable';
    v22 = 0;
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
          v8 = (CMapKeyToValue::CAssoc *)pNext;
          if ( pNext == -1 )
          {
            m_nHashTableSize = v7->m_mkv.m_nHashTableSize;
            if ( m_nHashTableSize )
            {
              for ( i = 0; i < m_nHashTableSize; ++i )
              {
                v8 = v7->m_mkv.m_pHashTable[i];
                if ( v8 )
                  break;
              }
            }
          }
          pNext = (__int64)v8->pNext;
          if ( !v8->pNext )
          {
            v11 = v7->m_mkv.m_nHashTableSize;
            for ( j = v8->nHashValue + 1; (unsigned int)j < v11; j = (unsigned int)(j + 1) )
            {
              pNext = (__int64)v7->m_mkv.m_pHashTable[j];
              if ( pNext )
                break;
            }
          }
          memcpy_0(&v22, &v8->key.rgbKey[v7->m_mkv.m_cbKeyInAssoc], v7->m_mkv.m_cbValue);
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        while ( pNext );
      }
      v13 = this->m_pMap;
      if ( v13 )
      {
        if ( v13->m_mkv.m_pHashTable )
        {
          for ( k = 0; k < v13->m_mkv.m_nHashTableSize; ++k )
          {
            for ( m = v13->m_mkv.m_pHashTable[k]; m; m = m->pNext )
            {
              if ( !v13->m_mkv.m_cbKey )
                CoTaskMemFree(m->key.pKey);
            }
          }
          CoTaskMemFree(v13->m_mkv.m_pHashTable);
          v13->m_mkv.m_pHashTable = 0;
        }
        m_pBlocks = v13->m_mkv.m_pBlocks;
        v13->m_mkv.m_nCount = 0;
        v13->m_mkv.m_pFreeList = 0;
        if ( m_pBlocks )
        {
          do
          {
            v15 = m_pBlocks->pNext;
            v16 = g_hHeap;
            m_pBlocks->pNext = 0;
            HeapFree(v16, 0, m_pBlocks);
            m_pBlocks = v15;
          }
          while ( v15 );
        }
        v17 = g_hHeap;
        v13->m_mkv.m_pBlocks = 0;
        HeapFree(v17, 0, v13);
      }
    }
    HeapFree(g_hHeap, 0, this);
  }
  return 0;
}

```

## disassembly

```asm
0x18001b110  push    rdi
0x18001b112  push    r14
0x18001b114  sub     rsp, 28h
0x18001b118  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001b11f  mov     r14, this
0x18001b122  mov     ecx, [this+8]
0x18001b125  mov     eax, edi
0x18001b127  lock xadd [r14+8], eax
0x18001b12d  cmp     eax, 1
0x18001b130  jnz     loc_18001B299
0x18001b136  mov     [rsp+38h+arg_10], rbp
0x18001b13b  xor     ebp, ebp
0x18001b13d  test    r14, r14
0x18001b140  jz      loc_18001B28A
0x18001b146  mov     this, [r14+40h]; this
0x18001b14a  lea     rax, ??_7CBindCtx@@6B@; const CBindCtx::`vftable'
0x18001b151  mov     [rsp+38h+arg_8], rbx
0x18001b156  mov     [r14], rax
0x18001b159  mov     [rsp+38h+arg_0], rbp
0x18001b15e  mov     [r14+40h], rbp
0x18001b162  test    this, this
0x18001b165  jnz     loc_18001B300
0x18001b16b  mov     rax, [r14+48h]
0x18001b16f  test    rax, rax
0x18001b172  jz      loc_18001B273
0x18001b178  cmp     [rax+28h], ebp
0x18001b17b  jz      loc_18001B217
0x18001b181  mov     r10, [r14+48h]
0x18001b185  mov     rdx, rdi
0x18001b188  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001b18c  jnz     short loc_18001B1B2
0x18001b18e  mov     r8d, [r10+18h]
0x18001b192  test    r8d, r8d
0x18001b195  jz      short loc_18001B1B2
0x18001b197  mov     r9, [r10+10h]
0x18001b19b  mov     ecx, ebp
0x18001b19d  nop     dword ptr [rax]
0x18001b1a0  mov     eax, ecx
0x18001b1a2  mov     rdx, [r9+rax*8]
0x18001b1a6  test    rdx, rdx
0x18001b1a9  jnz     short loc_18001B1B2
0x18001b1ab  inc     ecx
0x18001b1ad  cmp     ecx, r8d
0x18001b1b0  jb      short loc_18001B1A0
0x18001b1b2  mov     rdi, [rdx]
0x18001b1b5  test    rdi, rdi
0x18001b1b8  jnz     short loc_18001B1E0
0x18001b1ba  mov     ecx, [rdx+8]
0x18001b1bd  mov     r8d, [r10+18h]
0x18001b1c1  inc     ecx
0x18001b1c3  cmp     ecx, r8d
0x18001b1c6  jnb     short loc_18001B1E0
0x18001b1c8  mov     r9, [r10+10h]
0x18001b1cc  nop     dword ptr [rax+00h]
0x18001b1d0  mov     rdi, [r9+this*8]
0x18001b1d4  test    rdi, rdi
0x18001b1d7  jnz     short loc_18001B1E0
0x18001b1d9  inc     ecx
0x18001b1db  cmp     ecx, r8d
0x18001b1de  jb      short loc_18001B1D0
0x18001b1e0  mov     eax, [r10+8]
0x18001b1e4  lea     this, [rsp+38h+arg_0]; void *
0x18001b1e9  mov     r8d, [r10]; Size
0x18001b1ec  add     rax, 10h
0x18001b1f0  add     rdx, rax; Src
0x18001b1f3  call    memcpy_0
0x18001b1f8  mov     this, [rsp+38h+arg_0]
0x18001b1fd  test    this, this
0x18001b200  jz      short loc_18001B20E
0x18001b202  mov     rax, [this]
0x18001b205  mov     rax, [rax+10h]
0x18001b209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b20e  test    rdi, rdi
0x18001b211  jnz     loc_18001B181
0x18001b217  mov     rdi, [r14+48h]
0x18001b21b  test    rdi, rdi
0x18001b21e  jz      short loc_18001B273
0x18001b220  cmp     [rdi+10h], rbp
0x18001b224  jnz     short loc_18001B29E
0x18001b226  mov     r8, [rdi+38h]; lpMem
0x18001b22a  mov     [rdi+28h], ebp
0x18001b22d  mov     [rdi+30h], rbp
0x18001b231  test    r8, r8
0x18001b234  jz      short loc_18001B25D
0x18001b236  nop     word ptr [rax+rax+00000000h]
0x18001b240  mov     rbx, [r8]
0x18001b243  xor     edx, edx; dwFlags
0x18001b245  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001b24c  mov     [r8], rbp
0x18001b24f  call    cs:__imp_HeapFree
0x18001b255  mov     r8, rbx
0x18001b258  test    rbx, rbx
0x18001b25b  jnz     short loc_18001B240
0x18001b25d  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001b264  mov     r8, rdi; lpMem
0x18001b267  xor     edx, edx; dwFlags
0x18001b269  mov     [rdi+38h], rbp
0x18001b26d  call    cs:__imp_HeapFree
0x18001b273  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001b27a  mov     r8, r14; lpMem
0x18001b27d  xor     edx, edx; dwFlags
0x18001b27f  call    cs:__imp_HeapFree
0x18001b285  mov     rbx, [rsp+38h+arg_8]
0x18001b28a  mov     eax, ebp
0x18001b28c  mov     rbp, [rsp+38h+arg_10]
0x18001b291  add     rsp, 28h
0x18001b295  pop     r14
0x18001b297  pop     rdi
0x18001b298  retn
0x18001b299  lea     eax, [this-1]
0x18001b29c  jmp     short loc_18001B291
0x18001b29e  mov     ebx, ebp
0x18001b2a0  cmp     [rdi+18h], ebx
0x18001b2a3  jbe     short loc_18001B2CB
0x18001b2a5  mov     [rsp+38h+var_18], rsi
0x18001b2aa  nop     word ptr [rax+rax+00h]
0x18001b2b0  mov     rax, [rdi+10h]
0x18001b2b4  mov     ecx, ebx
0x18001b2b6  mov     rsi, [rax+this*8]
0x18001b2ba  test    rsi, rsi
0x18001b2bd  jnz     short loc_18001B2E0
0x18001b2bf  inc     ebx
0x18001b2c1  cmp     ebx, [rdi+18h]
0x18001b2c4  jb      short loc_18001B2B0
0x18001b2c6  mov     rsi, [rsp+38h+var_18]
0x18001b2cb  mov     this, [rdi+10h]; pv
0x18001b2cf  call    cs:__imp_CoTaskMemFree
0x18001b2d5  mov     [rdi+10h], rbp
0x18001b2d9  jmp     loc_18001B226
0x18001b2e0  cmp     [rdi+4], ebp
0x18001b2e3  jnz     short loc_18001B2EF
0x18001b2e5  mov     this, [rsi+10h]; pv
0x18001b2e9  call    cs:__imp_CoTaskMemFree
0x18001b2ef  mov     rsi, [rsi]
0x18001b2f2  test    rsi, rsi
0x18001b2f5  jz      short loc_18001B2BF
0x18001b2f7  jmp     short loc_18001B2E0
0x18001b300  mov     rbx, [this+8]
0x18001b304  call    ??_GCObjList@CBindCtx@@QEAAPEAXI@Z; CBindCtx::CObjList::`scalar deleting destructor'(uint)
0x18001b309  mov     this, rbx
0x18001b30c  test    rbx, rbx
0x18001b30f  jz      loc_18001B16B
0x18001b315  jmp     short loc_18001B300
```
