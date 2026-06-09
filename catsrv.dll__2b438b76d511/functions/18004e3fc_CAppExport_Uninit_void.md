# CAppExport::Uninit(void)

- ea: `0x18004e3fc`
- end: `0x18004e742`
- name: `?Uninit@CAppExport@@AEAAXXZ`
- size: `838`
- prototype: `void __fastcall(CAppExport *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180049be0`

## callees

- `0x18003e5e4`
- `0x18004e3fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e42e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e44a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e46f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e48d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e4bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e4f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e51b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e558`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e5c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e5e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e613`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e649`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e68b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e6c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e6f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e719`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e42e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e44a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e46f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e48d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e4bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e4f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e51b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e558`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e5c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e5e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e613`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e649`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e68b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e6c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e6f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e719`

## pseudocode

```c
void __fastcall CAppExport::Uninit(CAppExport *this)
{
  LPVOID *v1; // rdi
  unsigned int i; // esi
  void *v4; // rcx
  unsigned int v5; // edi
  void *v6; // rcx
  void *v7; // rcx
  unsigned int v8; // ebp
  __int64 v9; // rdi
  void *v10; // rcx
  __int64 v11; // rcx
  unsigned int v12; // r15d
  void *v13; // rcx
  void *v14; // rcx
  __int64 v15; // rcx
  unsigned int v16; // r14d
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  unsigned int v21; // ebp
  void *v22; // rcx
  __int64 v23; // rcx
  unsigned int v24; // r14d
  void *v25; // rcx
  __int64 v26; // rcx
  unsigned int v27; // r15d
  void *v28; // rcx
  void *v29; // rcx
  void *v30; // rcx
  void *v31; // rcx

  v1 = (LPVOID *)((char *)this + 24);
  for ( i = 0; i < *((_DWORD *)this + 4); ++i )
  {
    v4 = (void *)*((_QWORD *)*v1 + i);
    if ( v4 )
    {
      CoTaskMemFree(v4);
      *((_QWORD *)*v1 + i) = 0;
    }
  }
  if ( *v1 )
  {
    CoTaskMemFree(*v1);
    *v1 = 0;
  }
  v5 = 0;
  for ( *((_DWORD *)this + 4) = 0; v5 < *((_DWORD *)this + 8); ++v5 )
  {
    v6 = *(void **)(*((_QWORD *)this + 5) + 8LL * v5);
    if ( v6 )
    {
      CoTaskMemFree(v6);
      *(_QWORD *)(*((_QWORD *)this + 5) + 8LL * v5) = 0;
    }
  }
  v7 = (void *)*((_QWORD *)this + 5);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *((_QWORD *)this + 5) = 0;
  }
  v8 = 0;
  for ( *((_DWORD *)this + 8) = 0; v8 < *((_DWORD *)this + 12); ++v8 )
  {
    v9 = 32LL * v8;
    v10 = *(void **)(v9 + *((_QWORD *)this + 7));
    if ( v10 )
    {
      CoTaskMemFree(v10);
      *(_QWORD *)(v9 + *((_QWORD *)this + 7)) = 0;
    }
    v11 = *((_QWORD *)this + 7);
    if ( *(_DWORD *)(v11 + v9 + 8) )
    {
      v12 = 0;
      do
      {
        v13 = *(void **)(*(_QWORD *)(v9 + v11 + 16) + 48LL * v12 + 16);
        if ( v13 )
        {
          CoTaskMemFree(v13);
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + v9 + 16) + 48LL * v12 + 16) = 0;
        }
        v14 = *(void **)(*(_QWORD *)(*((_QWORD *)this + 7) + v9 + 16) + 48LL * v12 + 32);
        if ( v14 )
        {
          CoTaskMemFree(v14);
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + v9 + 16) + 48LL * v12 + 32) = 0;
        }
        v15 = *((_QWORD *)this + 7);
        if ( *(_DWORD *)(*(_QWORD *)(v15 + v9 + 16) + 48LL * v12 + 24) )
        {
          v16 = 0;
          do
          {
            v17 = *(void **)(*(_QWORD *)(*(_QWORD *)(v9 + v15 + 16) + 48LL * v12 + 40) + 8LL * v16);
            if ( v17 )
            {
              CoTaskMemFree(v17);
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + v9 + 16) + 48LL * v12 + 40) + 8LL * v16) = 0;
            }
            v15 = *((_QWORD *)this + 7);
            ++v16;
          }
          while ( v16 < *(_DWORD *)(*(_QWORD *)(v9 + v15 + 16) + 48LL * v12 + 24) );
        }
        v18 = *(void **)(*(_QWORD *)(v9 + v15 + 16) + 48LL * v12 + 40);
        if ( v18 )
        {
          CoTaskMemFree(v18);
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + v9 + 16) + 48LL * v12 + 40) = 0;
        }
        v11 = *((_QWORD *)this + 7);
        ++v12;
      }
      while ( v12 < *(_DWORD *)(v9 + v11 + 8) );
    }
    v19 = *(void **)(v11 + v9 + 16);
    if ( v19 )
    {
      CoTaskMemFree(v19);
      *(_QWORD *)(*((_QWORD *)this + 7) + v9 + 16) = 0;
    }
  }
  v20 = (void *)*((_QWORD *)this + 7);
  if ( v20 )
  {
    CoTaskMemFree(v20);
    *((_QWORD *)this + 7) = 0;
  }
  v21 = 0;
  for ( *((_DWORD *)this + 12) = 0; v21 < *((_DWORD *)this + 16); ++v21 )
  {
    v22 = *(void **)(*((_QWORD *)this + 9) + 24LL * v21);
    if ( v22 )
    {
      CoTaskMemFree(v22);
      *(_QWORD *)(*((_QWORD *)this + 9) + 24LL * v21) = 0;
    }
    v23 = *((_QWORD *)this + 9);
    if ( *(_DWORD *)(v23 + 24LL * v21 + 8) )
    {
      v24 = 0;
      do
      {
        v25 = *(void **)(*(_QWORD *)(v23 + 24LL * v21 + 16) + 40LL * v24 + 16);
        if ( v25 )
        {
          CoTaskMemFree(v25);
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 9) + 24LL * v21 + 16) + 40LL * v24 + 16) = 0;
        }
        v26 = *((_QWORD *)this + 9);
        if ( *(_DWORD *)(*(_QWORD *)(v26 + 24LL * v21 + 16) + 40LL * v24 + 24) )
        {
          v27 = 0;
          do
          {
            v28 = *(void **)(*(_QWORD *)(*(_QWORD *)(v26 + 24LL * v21 + 16) + 40LL * v24 + 32) + 24LL * v27 + 16);
            if ( v28 )
            {
              CoTaskMemFree(v28);
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 9) + 24LL * v21 + 16) + 40LL * v24 + 32)
                        + 24LL * v27
                        + 16) = 0;
            }
            v26 = *((_QWORD *)this + 9);
            ++v27;
          }
          while ( v27 < *(_DWORD *)(*(_QWORD *)(v26 + 24LL * v21 + 16) + 40LL * v24 + 24) );
        }
        v29 = *(void **)(*(_QWORD *)(v26 + 24LL * v21 + 16) + 40LL * v24 + 32);
        if ( v29 )
        {
          CoTaskMemFree(v29);
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 9) + 24LL * v21 + 16) + 40LL * v24 + 32) = 0;
        }
        v23 = *((_QWORD *)this + 9);
        ++v24;
      }
      while ( v24 < *(_DWORD *)(v23 + 24LL * v21 + 8) );
    }
    v30 = *(void **)(v23 + 24LL * v21 + 16);
    if ( v30 )
    {
      CoTaskMemFree(v30);
      *(_QWORD *)(*((_QWORD *)this + 9) + 24LL * v21 + 16) = 0;
    }
  }
  v31 = (void *)*((_QWORD *)this + 9);
  if ( v31 )
  {
    CoTaskMemFree(v31);
    *((_QWORD *)this + 9) = 0;
  }
  *((_DWORD *)this + 16) = 0;
  CArray<DllInfo *,DllInfo * const &>::SetSize((char *)this + 80, 0);
}

```

## disassembly

```asm
0x18004e3fc  push    rbx
0x18004e3fe  push    rbp
0x18004e3ff  push    rsi
0x18004e400  push    rdi
0x18004e401  push    r12
0x18004e403  push    r13
0x18004e405  push    r14
0x18004e407  push    r15
0x18004e409  sub     rsp, 28h
0x18004e40d  xor     r13d, r13d
0x18004e410  lea     rdi, [rcx+18h]
0x18004e414  mov     rbx, rcx
0x18004e417  mov     esi, r13d
0x18004e41a  cmp     [rcx+10h], r13d
0x18004e41e  jbe     short loc_18004E442
0x18004e420  mov     rax, [rdi]
0x18004e423  mov     ebp, esi
0x18004e425  mov     rcx, [rax+rbp*8]; pv
0x18004e429  test    rcx, rcx
0x18004e42c  jz      short loc_18004E43B
0x18004e42e  call    cs:__imp_CoTaskMemFree
0x18004e434  mov     rax, [rdi]
0x18004e437  mov     [rax+rbp*8], r13
0x18004e43b  inc     esi
0x18004e43d  cmp     esi, [rbx+10h]
0x18004e440  jb      short loc_18004E420
0x18004e442  mov     rcx, [rdi]; pv
0x18004e445  test    rcx, rcx
0x18004e448  jz      short loc_18004E453
0x18004e44a  call    cs:__imp_CoTaskMemFree
0x18004e450  mov     [rdi], r13
0x18004e453  mov     edi, r13d
0x18004e456  mov     [rbx+10h], r13d
0x18004e45a  cmp     [rbx+20h], r13d
0x18004e45e  jbe     short loc_18004E484
0x18004e460  mov     rax, [rbx+28h]
0x18004e464  mov     esi, edi
0x18004e466  mov     rcx, [rax+rsi*8]; pv
0x18004e46a  test    rcx, rcx
0x18004e46d  jz      short loc_18004E47D
0x18004e46f  call    cs:__imp_CoTaskMemFree
0x18004e475  mov     rax, [rbx+28h]
0x18004e479  mov     [rax+rsi*8], r13
0x18004e47d  inc     edi
0x18004e47f  cmp     edi, [rbx+20h]
0x18004e482  jb      short loc_18004E460
0x18004e484  mov     rcx, [rbx+28h]; pv
0x18004e488  test    rcx, rcx
0x18004e48b  jz      short loc_18004E497
0x18004e48d  call    cs:__imp_CoTaskMemFree
0x18004e493  mov     [rbx+28h], r13
0x18004e497  mov     ebp, r13d
0x18004e49a  mov     [rbx+20h], r13d
0x18004e49e  cmp     [rbx+30h], r13d
0x18004e4a2  jbe     loc_18004E5DC
0x18004e4a8  mov     rax, [rbx+38h]
0x18004e4ac  mov     edi, ebp
0x18004e4ae  shl     rdi, 5
0x18004e4b2  mov     rcx, [rdi+rax]; pv
0x18004e4b6  test    rcx, rcx
0x18004e4b9  jz      short loc_18004E4C9
0x18004e4bb  call    cs:__imp_CoTaskMemFree
0x18004e4c1  mov     rax, [rbx+38h]
0x18004e4c5  mov     [rdi+rax], r13
0x18004e4c9  mov     rcx, [rbx+38h]
0x18004e4cd  cmp     [rcx+rdi+8], r13d
0x18004e4d2  jbe     loc_18004E5B8
0x18004e4d8  mov     r15d, r13d
0x18004e4db  mov     eax, r15d
0x18004e4de  lea     rsi, [rax+rax*2]
0x18004e4e2  mov     rax, [rdi+rcx+10h]
0x18004e4e7  add     rsi, rsi
0x18004e4ea  mov     rcx, [rax+rsi*8+10h]; pv
0x18004e4ef  test    rcx, rcx
0x18004e4f2  jz      short loc_18004E508
0x18004e4f4  call    cs:__imp_CoTaskMemFree
0x18004e4fa  mov     rax, [rbx+38h]
0x18004e4fe  mov     rcx, [rax+rdi+10h]
0x18004e503  mov     [rcx+rsi*8+10h], r13
0x18004e508  mov     rax, [rbx+38h]
0x18004e50c  mov     rcx, [rax+rdi+10h]
0x18004e511  mov     rcx, [rcx+rsi*8+20h]; pv
0x18004e516  test    rcx, rcx
0x18004e519  jz      short loc_18004E52F
0x18004e51b  call    cs:__imp_CoTaskMemFree
0x18004e521  mov     rax, [rbx+38h]
0x18004e525  mov     rcx, [rax+rdi+10h]
0x18004e52a  mov     [rcx+rsi*8+20h], r13
0x18004e52f  mov     rcx, [rbx+38h]
0x18004e533  mov     rax, [rcx+rdi+10h]
0x18004e538  cmp     [rax+rsi*8+18h], r13d
0x18004e53d  jbe     short loc_18004E583
0x18004e53f  mov     r14d, r13d
0x18004e542  mov     rax, [rdi+rcx+10h]
0x18004e547  mov     r12d, r14d
0x18004e54a  mov     rcx, [rax+rsi*8+28h]
0x18004e54f  mov     rcx, [rcx+r12*8]; pv
0x18004e553  test    rcx, rcx
0x18004e556  jz      short loc_18004E570
0x18004e558  call    cs:__imp_CoTaskMemFree
0x18004e55e  mov     rax, [rbx+38h]
0x18004e562  mov     rcx, [rax+rdi+10h]
0x18004e567  mov     rax, [rcx+rsi*8+28h]
0x18004e56c  mov     [rax+r12*8], r13
0x18004e570  mov     rcx, [rbx+38h]
0x18004e574  inc     r14d
0x18004e577  mov     rax, [rdi+rcx+10h]
0x18004e57c  cmp     r14d, [rax+rsi*8+18h]
0x18004e581  jb      short loc_18004E542
0x18004e583  mov     rax, [rdi+rcx+10h]
0x18004e588  mov     rcx, [rax+rsi*8+28h]; pv
0x18004e58d  test    rcx, rcx
0x18004e590  jz      short loc_18004E5A6
0x18004e592  call    cs:__imp_CoTaskMemFree
0x18004e598  mov     rax, [rbx+38h]
0x18004e59c  mov     rcx, [rax+rdi+10h]
0x18004e5a1  mov     [rcx+rsi*8+28h], r13
0x18004e5a6  mov     rcx, [rbx+38h]
0x18004e5aa  inc     r15d
0x18004e5ad  cmp     r15d, [rdi+rcx+8]
0x18004e5b2  jb      loc_18004E4DB
0x18004e5b8  mov     rcx, [rcx+rdi+10h]; pv
0x18004e5bd  test    rcx, rcx
0x18004e5c0  jz      short loc_18004E5D1
0x18004e5c2  call    cs:__imp_CoTaskMemFree
0x18004e5c8  mov     rax, [rbx+38h]
0x18004e5cc  mov     [rax+rdi+10h], r13
0x18004e5d1  inc     ebp
0x18004e5d3  cmp     ebp, [rbx+30h]
0x18004e5d6  jb      loc_18004E4A8
0x18004e5dc  mov     rcx, [rbx+38h]; pv
0x18004e5e0  test    rcx, rcx
0x18004e5e3  jz      short loc_18004E5EF
0x18004e5e5  call    cs:__imp_CoTaskMemFree
0x18004e5eb  mov     [rbx+38h], r13
0x18004e5ef  mov     ebp, r13d
0x18004e5f2  mov     [rbx+30h], r13d
0x18004e5f6  cmp     [rbx+40h], r13d
0x18004e5fa  jbe     loc_18004E710
0x18004e600  mov     eax, ebp
0x18004e602  lea     rdi, [rax+rax*2]
0x18004e606  mov     rax, [rbx+48h]
0x18004e60a  mov     rcx, [rax+rdi*8]; pv
0x18004e60e  test    rcx, rcx
0x18004e611  jz      short loc_18004E621
0x18004e613  call    cs:__imp_CoTaskMemFree
0x18004e619  mov     rax, [rbx+48h]
0x18004e61d  mov     [rax+rdi*8], r13
0x18004e621  mov     rcx, [rbx+48h]
0x18004e625  cmp     [rcx+rdi*8+8], r13d
0x18004e62a  jbe     loc_18004E6EC
0x18004e630  mov     r14d, r13d
0x18004e633  mov     eax, r14d
0x18004e636  lea     rsi, [rax+rax*4]
0x18004e63a  mov     rax, [rcx+rdi*8+10h]
0x18004e63f  mov     rcx, [rax+rsi*8+10h]; pv
0x18004e644  test    rcx, rcx
0x18004e647  jz      short loc_18004E65D
0x18004e649  call    cs:__imp_CoTaskMemFree
0x18004e64f  mov     rax, [rbx+48h]
0x18004e653  mov     rcx, [rax+rdi*8+10h]
0x18004e658  mov     [rcx+rsi*8+10h], r13
0x18004e65d  mov     rcx, [rbx+48h]
0x18004e661  mov     rax, [rcx+rdi*8+10h]
0x18004e666  cmp     [rax+rsi*8+18h], r13d
0x18004e66b  jbe     short loc_18004E6B7
0x18004e66d  mov     r15d, r13d
0x18004e670  mov     eax, r15d
0x18004e673  lea     r12, [rax+rax*2]
0x18004e677  mov     rax, [rcx+rdi*8+10h]
0x18004e67c  mov     rcx, [rax+rsi*8+20h]
0x18004e681  mov     rcx, [rcx+r12*8+10h]; pv
0x18004e686  test    rcx, rcx
0x18004e689  jz      short loc_18004E6A4
0x18004e68b  call    cs:__imp_CoTaskMemFree
0x18004e691  mov     rax, [rbx+48h]
0x18004e695  mov     rcx, [rax+rdi*8+10h]
0x18004e69a  mov     rax, [rcx+rsi*8+20h]
0x18004e69f  mov     [rax+r12*8+10h], r13
0x18004e6a4  mov     rcx, [rbx+48h]
0x18004e6a8  inc     r15d
0x18004e6ab  mov     rax, [rcx+rdi*8+10h]
0x18004e6b0  cmp     r15d, [rax+rsi*8+18h]
0x18004e6b5  jb      short loc_18004E670
0x18004e6b7  mov     rax, [rcx+rdi*8+10h]
0x18004e6bc  mov     rcx, [rax+rsi*8+20h]; pv
0x18004e6c1  test    rcx, rcx
0x18004e6c4  jz      short loc_18004E6DA
0x18004e6c6  call    cs:__imp_CoTaskMemFree
0x18004e6cc  mov     rax, [rbx+48h]
0x18004e6d0  mov     rcx, [rax+rdi*8+10h]
0x18004e6d5  mov     [rcx+rsi*8+20h], r13
0x18004e6da  mov     rcx, [rbx+48h]
0x18004e6de  inc     r14d
0x18004e6e1  cmp     r14d, [rcx+rdi*8+8]
0x18004e6e6  jb      loc_18004E633
0x18004e6ec  mov     rcx, [rcx+rdi*8+10h]; pv
0x18004e6f1  test    rcx, rcx
0x18004e6f4  jz      short loc_18004E705
0x18004e6f6  call    cs:__imp_CoTaskMemFree
0x18004e6fc  mov     rax, [rbx+48h]
0x18004e700  mov     [rax+rdi*8+10h], r13
0x18004e705  inc     ebp
0x18004e707  cmp     ebp, [rbx+40h]
0x18004e70a  jb      loc_18004E600
0x18004e710  mov     rcx, [rbx+48h]; pv
0x18004e714  test    rcx, rcx
0x18004e717  jz      short loc_18004E723
0x18004e719  call    cs:__imp_CoTaskMemFree
0x18004e71f  mov     [rbx+48h], r13
0x18004e723  lea     rcx, [rbx+50h]
0x18004e727  mov     [rbx+40h], r13d
0x18004e72b  xor     edx, edx
0x18004e72d  add     rsp, 28h
0x18004e731  pop     r15
0x18004e733  pop     r14
0x18004e735  pop     r13
0x18004e737  pop     r12
0x18004e739  pop     rdi
0x18004e73a  pop     rsi
0x18004e73b  pop     rbp
0x18004e73c  pop     rbx
0x18004e73d  jmp     ?SetSize@?$CArray@PEAUDllInfo@@AEBQEAU1@@@QEAAXHH@Z; CArray<DllInfo *,DllInfo * const &>::SetSize(int,int)
```
