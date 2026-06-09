# CSslSerializeHelper::DeserializeContextWorker(CSslUserContext *,ulong)

- ea: `0x140002510`
- end: `0x140002c17`
- name: `?DeserializeContextWorker@CSslSerializeHelper@@AEAAJPEAUCSslUserContext@@K@Z`
- size: `1799`
- prototype: `__int64 __fastcall(CSslSerializeHelper *__hidden this, struct CSslUserContext *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140002410`

## callees

- `0x140002510`
- `0x140003d90`
- `0x14000a970`
- `0x14000a9e4`
- `0x14000aaf8`
- `0x1400102c0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400026e1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002b14`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400026e1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002b14`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002775`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002af1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002b75`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002775`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002af1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002b75`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140002b29`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140002b29`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400026f6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400026f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140002769`
- `ntoskrnl!ExReleaseResourceLite` at `0x140002ae5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140002b69`
- `ntoskrnl!ExReleaseResourceLite` at `0x140002769`
- `ntoskrnl!ExReleaseResourceLite` at `0x140002ae5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140002b69`
- `cng!SslImportKey` at `0x14000264c`
- `cng!SslImportKey` at `0x14000264c`
- `cng!SslIncrementProviderReferenceCount` at `0x14000278f`
- `cng!SslIncrementProviderReferenceCount` at `0x14000278f`

## pseudocode

```c
__int64 __fastcall CSslSerializeHelper::DeserializeContextWorker(CSslSerializeHelper *this, struct CSslUserContext *a2)
{
  __int64 v2; // rbx
  unsigned int v4; // r13d
  _OWORD *v5; // r15
  int i; // r8d
  _DWORD *v7; // r9
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned int v11; // eax
  unsigned int CachedSslProv; // edi
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r12
  const unsigned __int16 *v16; // rbp
  _QWORD *v17; // r11
  unsigned int v18; // r10d
  unsigned int v19; // r9d
  const unsigned __int16 *v20; // rax
  int v21; // ecx
  int v22; // edx
  unsigned __int64 SslProvHandleInCache; // rsi
  int v24; // ebp
  _QWORD *v25; // rcx
  __int64 v26; // rax
  __int128 v27; // xmm0
  __int64 v29; // rax
  _OWORD v30[5]; // [rsp+30h] [rbp-58h] BYREF

  v2 = *((_QWORD *)this + 1);
  if ( *(_DWORD *)v2 != 1 )
    return 2148074244LL;
  v4 = 1;
  v5 = (_OWORD *)((char *)a2 + 528);
  for ( i = 1; ; i = *(_DWORD *)v2 )
  {
LABEL_3:
    while ( 1 )
    {
      v7 = (_DWORD *)(v2 + 16);
      if ( i != 5 )
        break;
      *((_QWORD *)a2 + 25) = v5;
      memmove(v5, (const void *)(v2 + 16), *(unsigned int *)(v2 + 8));
      *((_DWORD *)a2 + 52) = *(_DWORD *)(v2 + 8);
LABEL_9:
      v8 = *(unsigned int *)(v2 + 8) + 7LL;
LABEL_10:
      v5 = (_OWORD *)((char *)v5 + (v8 & 0xFFFFFFFFFFFFFFF8uLL));
LABEL_11:
      v2 += (unsigned int)(*(_DWORD *)(v2 + 4) + 16);
      i = *(_DWORD *)v2;
    }
    if ( i == 18 )
    {
LABEL_12:
      if ( !a2 )
        return (unsigned int)-2146893052;
      v9 = *((_QWORD *)a2 + 11);
      if ( !v9 )
        return (unsigned int)-2146893052;
      if ( i == 2 )
      {
        v10 = 40;
      }
      else
      {
        v10 = 48;
        if ( i != 3 )
          v10 = 472;
      }
      v11 = SslImportKey(v9, (char *)a2 + v10, L"OpaqueKeyBlob", v7, *(_DWORD *)(v2 + 8), 0);
      goto LABEL_18;
    }
    if ( i != 19 )
      break;
LABEL_20:
    if ( !a2 )
      return (unsigned int)-2146893052;
    v13 = *((_QWORD *)a2 + 11);
    if ( !v13 )
      return (unsigned int)-2146893052;
    v14 = 480;
    if ( i != 19 )
      v14 = 488;
    v11 = SslImportKey(v13, (char *)a2 + v14, L"OpaqueKeyBlob", v7, *(_DWORD *)(v2 + 8), 0);
LABEL_18:
    CachedSslProv = v11;
    if ( v11 )
      return CachedSslProv;
    v2 += (unsigned int)(*(_DWORD *)(v2 + 4) + 16);
  }
  switch ( i )
  {
    case 0:
      return 0;
    case 1:
      v4 = *(_DWORD *)(v2 + 20);
      if ( v4 > 1 || *(_DWORD *)(v2 + 4) < 0xC2u )
        return (unsigned int)-2146893052;
      if ( !a2 )
        goto LABEL_11;
      *((_DWORD *)a2 + 2) = *v7;
      *((_DWORD *)a2 + 3) = *(_DWORD *)(v2 + 20);
      *((_QWORD *)a2 + 2) = *(_QWORD *)(v2 + 24);
      *((_DWORD *)a2 + 6) = *(_DWORD *)(v2 + 32);
      *((_BYTE *)a2 + 32) = *(_BYTE *)(v2 + 60);
      *((_DWORD *)a2 + 7) = *(_DWORD *)(v2 + 44);
      *((_QWORD *)a2 + 12) = *(_QWORD *)(v2 + 64);
      *((_QWORD *)a2 + 13) = *(_QWORD *)(v2 + 72);
      *((_DWORD *)a2 + 14) = *(_DWORD *)(v2 + 36);
      *((_DWORD *)a2 + 15) = *(_DWORD *)(v2 + 40);
      *((_DWORD *)a2 + 16) = *(_DWORD *)(v2 + 48);
      *((_DWORD *)a2 + 18) = *(_DWORD *)(v2 + 52);
      *((_DWORD *)a2 + 17) = *(_DWORD *)(v2 + 168);
      *((_DWORD *)a2 + 29) = *(_DWORD *)(v2 + 192);
      *((_QWORD *)a2 + 15) = *(_QWORD *)(v2 + 176);
      *((_QWORD *)a2 + 16) = *(_QWORD *)(v2 + 184);
      *((_WORD *)a2 + 68) = *(_WORD *)(v2 + 196);
      *((_WORD *)a2 + 69) = *(_WORD *)(v2 + 198);
      *((_DWORD *)a2 + 36) = *(_DWORD *)(v2 + 200);
      *((_DWORD *)a2 + 125) = *(_DWORD *)(v2 + 204);
      *((_BYTE *)a2 + 496) = *(_BYTE *)(v2 + 208);
      *((_BYTE *)a2 + 504) = *(_BYTE *)(v2 + 209);
      *((_DWORD *)a2 + 57) = *(_DWORD *)(v2 + 56);
      *((_DWORD *)a2 + 105) = *(_DWORD *)(v2 + 164);
      *((_DWORD *)a2 + 104) = *(_DWORD *)(v2 + 160);
      *((_QWORD *)a2 + 35) = *(_QWORD *)(v2 + 80);
      *((_DWORD *)a2 + 72) = *(_DWORD *)(v2 + 88);
      *((_QWORD *)a2 + 39) = *(_QWORD *)(v2 + 96);
      v2 += (unsigned int)(*(_DWORD *)(v2 + 4) + 16);
      i = *(_DWORD *)v2;
      goto LABEL_3;
    case 2:
    case 3:
      goto LABEL_12;
    case 4:
      if ( v4 )
        return (unsigned int)-2146893052;
      *((_QWORD *)a2 + 19) = v5;
      memmove(v5, (const void *)(v2 + 16), *(unsigned int *)(v2 + 8));
      *((_DWORD *)a2 + 40) = *(_DWORD *)(v2 + 8);
      goto LABEL_9;
    case 6:
      *((_QWORD *)a2 + 27) = v5;
      memmove(v5, (const void *)(v2 + 16), *(unsigned int *)(v2 + 8));
      *((_DWORD *)a2 + 56) = *(_DWORD *)(v2 + 8);
      goto LABEL_9;
    case 7:
      if ( v4 )
        return (unsigned int)-2146893052;
      *((_QWORD *)a2 + 21) = v5;
      memmove(v5, (const void *)(v2 + 16), *(unsigned int *)(v2 + 8));
      *((_DWORD *)a2 + 44) = *(_DWORD *)(v2 + 8);
      goto LABEL_9;
    case 8:
      if ( v4 )
        return (unsigned int)-2146893052;
      *((_QWORD *)a2 + 23) = v5;
      memmove(v5, (const void *)(v2 + 16), *(unsigned int *)(v2 + 8));
      *((_DWORD *)a2 + 48) = *(_DWORD *)(v2 + 8);
      goto LABEL_9;
    case 9:
      *((_QWORD *)a2 + 10) = v5;
      memmove(v5, (const void *)(v2 + 16), *(unsigned int *)(v2 + 8));
      v15 = *(unsigned int *)(v2 + 8);
      v16 = (const unsigned __int16 *)*((_QWORD *)a2 + 10);
      v30[0] = 0;
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite(g_pSslProvCacheRWLock, 1u);
      v17 = &g_rgCachedPagedSslProvs;
      v18 = dword_1400190F8;
      if ( dword_140019528 )
        v18 = g_cCachedPagedSslProvs;
      else
        v17 = &unk_140019100;
      v19 = 0;
      break;
    case 10:
      *((_QWORD *)a2 + 31) = v5;
      memmove(v5, (const void *)(v2 + 16), *(unsigned int *)(v2 + 8));
      *((_DWORD *)a2 + 64) = *(_DWORD *)(v2 + 8);
      goto LABEL_9;
    case 11:
      *((_QWORD *)a2 + 33) = v5;
      memmove(v5, (const void *)(v2 + 16), *(unsigned int *)(v2 + 8));
      *((_DWORD *)a2 + 68) = *(_DWORD *)(v2 + 8);
      goto LABEL_9;
    case 12:
      *((_QWORD *)a2 + 54) = v5;
      v25 = v5;
      v26 = 2;
      do
      {
        v25 += 16;
        v27 = *(_OWORD *)v7;
        v7 += 32;
        *((_OWORD *)v25 - 8) = v27;
        *((_OWORD *)v25 - 7) = *((_OWORD *)v7 - 7);
        *((_OWORD *)v25 - 6) = *((_OWORD *)v7 - 6);
        *((_OWORD *)v25 - 5) = *((_OWORD *)v7 - 5);
        *((_OWORD *)v25 - 4) = *((_OWORD *)v7 - 4);
        *((_OWORD *)v25 - 3) = *((_OWORD *)v7 - 3);
        *((_OWORD *)v25 - 2) = *((_OWORD *)v7 - 2);
        *((_OWORD *)v25 - 1) = *((_OWORD *)v7 - 1);
        --v26;
      }
      while ( v26 );
      *v25 = *(_QWORD *)v7;
      v8 = *(unsigned int *)(v2 + 8) + 7LL;
      goto LABEL_10;
    case 13:
      *((_QWORD *)a2 + 55) = v5;
      goto LABEL_68;
    case 14:
      v29 = *((_QWORD *)a2 + 55);
      goto LABEL_71;
    case 15:
      *((_QWORD *)a2 + 56) = v5;
LABEL_68:
      *v5 = *(_OWORD *)v7;
      v8 = *(unsigned int *)(v2 + 8) + 7LL;
      goto LABEL_10;
    case 16:
      v29 = *((_QWORD *)a2 + 56);
LABEL_71:
      *(_QWORD *)(v29 + 8) = v5;
      memmove(v5, (const void *)(v2 + 16), *(unsigned int *)(v2 + 8));
      goto LABEL_9;
    case 17:
      *((_QWORD *)a2 + 58) = v5;
      memmove(v5, (const void *)(v2 + 16), *(unsigned int *)(v2 + 8));
      *((_DWORD *)a2 + 114) = *(_DWORD *)(v2 + 8);
      goto LABEL_9;
    case 20:
      goto LABEL_20;
    case 21:
      if ( !v4 )
        return (unsigned int)-2146893052;
      *((_QWORD *)a2 + 30) = v5;
      memmove(v5, (const void *)(v2 + 16), *(unsigned int *)(v2 + 8));
      *((_DWORD *)a2 + 58) = *(_DWORD *)(v2 + 8);
      goto LABEL_9;
    default:
      return 2148074244LL;
  }
  while ( 1 )
  {
    if ( v19 >= v18 )
    {
      ExReleaseResourceLite(g_pSslProvCacheRWLock);
      KeLeaveCriticalRegion();
      goto LABEL_61;
    }
    v20 = v16;
    do
    {
      v21 = *(const unsigned __int16 *)((char *)v20 + v17[2 * v19 + 1] - (_QWORD)v16);
      v22 = *v20 - v21;
      if ( v22 )
        break;
      ++v20;
    }
    while ( v21 );
    if ( !v22 )
      break;
    ++v19;
  }
  SslProvHandleInCache = v17[2 * v19];
  ExReleaseResourceLite(g_pSslProvCacheRWLock);
  KeLeaveCriticalRegion();
  if ( SslProvHandleInCache )
  {
    v24 = 0;
    goto LABEL_37;
  }
LABEL_61:
  CachedSslProv = CreateCachedSslProv((struct CACHED_SSL_PROVIDER *)v30, v16);
  if ( CachedSslProv )
    return CachedSslProv;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(g_pSslProvCacheRWLock, 1u);
  SslProvHandleInCache = FindSslProvHandleInCache(v16);
  if ( SslProvHandleInCache )
  {
    DestroyCachedSslProv((struct CACHED_SSL_PROVIDER *)v30);
    v24 = 0;
  }
  else
  {
    SslProvHandleInCache = *(_QWORD *)&v30[0];
    v24 = 1;
    CacheClientSideSslProv((struct CACHED_SSL_PROVIDER *)v30);
  }
  ExReleaseResourceLite(g_pSslProvCacheRWLock);
  KeLeaveCriticalRegion();
LABEL_37:
  CachedSslProv = SslIncrementProviderReferenceCount(SslProvHandleInCache);
  if ( !CachedSslProv )
  {
    *((_QWORD *)a2 + 11) = SslProvHandleInCache;
    v8 = v15 + 7;
    goto LABEL_10;
  }
  if ( v24 )
    DestroyCachedSslProv((struct CACHED_SSL_PROVIDER *)v30);
  return CachedSslProv;
}

```

## disassembly

```asm
0x140002510  push    rbx
0x140002512  push    rbp
0x140002513  push    rsi
0x140002514  push    rdi
0x140002515  push    r12
0x140002517  push    r13
0x140002519  push    r14
0x14000251b  push    r15
0x14000251d  sub     rsp, 48h
0x140002521  mov     rbx, [rcx+8]
0x140002525  mov     r14, rdx
0x140002528  cmp     dword ptr [rbx], 1
0x14000252b  jnz     def_14000258F; jumptable 000000014000258F default case, cases 5,18,19
0x140002531  mov     r13d, 1
0x140002537  lea     r15, [rdx+210h]
0x14000253e  mov     r8d, r13d
0x140002541  lea     rdx, cs:140000000h
0x140002548  lea     rdi, unk_140019100
0x14000254f  mov     r11d, 1D8h
0x140002555  lea     r9, [rbx+10h]
0x140002559  mov     eax, 1E8h
0x14000255e  cmp     r8d, 5
0x140002562  jz      short loc_1400025B7
0x140002564  cmp     r8d, 12h
0x140002568  jz      loc_140002603; jumptable 000000014000258F cases 2,3
0x14000256e  cmp     r8d, 13h
0x140002572  jz      loc_140002687
0x140002578  cmp     r8d, 15h; switch 22 cases
0x14000257c  ja      def_14000258F; jumptable 000000014000258F default case, cases 5,18,19
0x140002582  movsxd  rax, r8d
0x140002585  mov     ecx, ds:(jpt_14000258F - 140000000h)[rdx+rax*4]
0x14000258c  add     rcx, rdx
0x14000258f  jmp     rcx; switch jump
0x140002595  mov     [r14+108h], r15; jumptable 000000014000258F case 11
0x14000259c  mov     rdx, r9; Src
0x14000259f  mov     r8d, [rbx+8]; Size
0x1400025a3  mov     rcx, r15; void *
0x1400025a6  call    memmove
0x1400025ab  mov     eax, [rbx+8]
0x1400025ae  mov     [r14+110h], eax
0x1400025b5  jmp     short loc_1400025D7
0x1400025b7  mov     [r14+0C8h], r15
0x1400025be  mov     rdx, r9; Src
0x1400025c1  mov     r8d, [rbx+8]; Size
0x1400025c5  mov     rcx, r15; void *
0x1400025c8  call    memmove
0x1400025cd  mov     eax, [rbx+8]
0x1400025d0  mov     [r14+0D0h], eax
0x1400025d7  mov     eax, [rbx+8]
0x1400025da  add     rax, 7
0x1400025de  mov     r11d, 1D8h
0x1400025e4  lea     rdx, cs:140000000h
0x1400025eb  and     rax, 0FFFFFFFFFFFFFFF8h
0x1400025ef  add     r15, rax
0x1400025f2  mov     eax, [rbx+4]
0x1400025f5  add     eax, 10h
0x1400025f8  add     rbx, rax
0x1400025fb  mov     r8d, [rbx]
0x1400025fe  jmp     loc_140002555
0x140002603  test    r14, r14; jumptable 000000014000258F cases 2,3
0x140002606  jz      loc_140002C01
0x14000260c  mov     rcx, [r14+58h]
0x140002610  test    rcx, rcx
0x140002613  jz      loc_140002C01
0x140002619  mov     r10d, [rbx+8]
0x14000261d  cmp     r8d, 2
0x140002621  jz      loc_1400027BC
0x140002627  cmp     r8d, 3
0x14000262b  mov     eax, 30h ; '0'
0x140002630  cmovnz  rax, r11
0x140002634  mov     [rsp+88h+var_60], 0
0x14000263c  lea     rdx, [rax+r14]
0x140002640  mov     [rsp+88h+var_68], r10d
0x140002645  lea     r8, pszBlobType; "OpaqueKeyBlob"
0x14000264c  call    cs:__imp_SslImportKey
0x140002653  nop     dword ptr [rax+rax+00h]
0x140002658  mov     edi, eax
0x14000265a  test    eax, eax
0x14000265c  jnz     loc_140002C06
0x140002662  mov     eax, [rbx+4]
0x140002665  lea     rdx, cs:140000000h
0x14000266c  add     eax, 10h
0x14000266f  lea     rdi, unk_140019100
0x140002676  add     rbx, rax
0x140002679  mov     r11d, 1D8h
0x14000267f  mov     r8d, [rbx]
0x140002682  jmp     loc_140002555
0x140002687  test    r14, r14
0x14000268a  jz      loc_140002C01
0x140002690  mov     rcx, [r14+58h]
0x140002694  test    rcx, rcx
0x140002697  jz      loc_140002C01
0x14000269d  cmp     r8d, 13h
0x1400026a1  mov     [rsp+88h+var_60], 0
0x1400026a9  mov     edx, 1E0h
0x1400026ae  cmovnz  rdx, rax
0x1400026b2  mov     eax, [rbx+8]
0x1400026b5  add     rdx, r14
0x1400026b8  mov     [rsp+88h+var_68], eax
0x1400026bc  jmp     short loc_140002645
0x1400026be  mov     [r14+50h], r15; jumptable 000000014000258F case 9
0x1400026c2  mov     rdx, r9; Src
0x1400026c5  mov     r8d, [rbx+8]; Size
0x1400026c9  mov     rcx, r15; void *
0x1400026cc  call    memmove
0x1400026d1  mov     r12d, [rbx+8]
0x1400026d5  xorps   xmm0, xmm0
0x1400026d8  mov     rbp, [r14+50h]
0x1400026dc  movups  [rsp+88h+var_58], xmm0
0x1400026e1  call    cs:__imp_KeEnterCriticalRegion
0x1400026e8  nop     dword ptr [rax+rax+00h]
0x1400026ed  mov     rcx, cs:?g_pSslProvCacheRWLock@@3PEAU_ERESOURCE@@EA; Resource
0x1400026f4  mov     dl, 1; Wait
0x1400026f6  call    cs:__imp_ExAcquireResourceSharedLite
0x1400026fd  nop     dword ptr [rax+rax+00h]
0x140002702  mov     ecx, cs:dword_140019528
0x140002708  lea     r11, ?g_rgCachedPagedSslProvs@@3PAUCACHED_SSL_PROVIDER@@A; CACHED_SSL_PROVIDER near * g_rgCachedPagedSslProvs
0x14000270f  mov     r10d, cs:dword_1400190F8
0x140002716  test    ecx, ecx
0x140002718  cmovnz  r10d, cs:?g_cCachedPagedSslProvs@@3KA; ulong g_cCachedPagedSslProvs
0x140002720  cmovz   r11, rdi
0x140002724  xor     r9d, r9d
0x140002727  cmp     r9d, r10d
0x14000272a  jnb     loc_140002ADE
0x140002730  mov     esi, r9d
0x140002733  mov     rax, rbp
0x140002736  add     rsi, rsi
0x140002739  mov     r8, [r11+rsi*8+8]
0x14000273e  sub     r8, rbp
0x140002741  movzx   edx, word ptr [rax]
0x140002744  movzx   ecx, word ptr [rax+r8]
0x140002749  sub     edx, ecx
0x14000274b  jnz     short loc_140002755
0x14000274d  add     rax, 2
0x140002751  test    ecx, ecx
0x140002753  jnz     short loc_140002741
0x140002755  test    edx, edx
0x140002757  jz      short loc_14000275E
0x140002759  inc     r9d
0x14000275c  jmp     short loc_140002727
0x14000275e  mov     rcx, cs:?g_pSslProvCacheRWLock@@3PEAU_ERESOURCE@@EA; Resource
0x140002765  mov     rsi, [r11+rsi*8]
0x140002769  call    cs:__imp_ExReleaseResourceLite
0x140002770  nop     dword ptr [rax+rax+00h]
0x140002775  call    cs:__imp_KeLeaveCriticalRegion
0x14000277c  nop     dword ptr [rax+rax+00h]
0x140002781  test    rsi, rsi
0x140002784  jz      loc_140002AFD
0x14000278a  xor     ebp, ebp
0x14000278c  mov     rcx, rsi
0x14000278f  call    cs:__imp_SslIncrementProviderReferenceCount
0x140002796  nop     dword ptr [rax+rax+00h]
0x14000279b  mov     edi, eax
0x14000279d  test    eax, eax
0x14000279f  jz      loc_1400028A0
0x1400027a5  test    ebp, ebp
0x1400027a7  jz      loc_140002C06
0x1400027ad  lea     rcx, [rsp+88h+var_58]; struct CACHED_SSL_PROVIDER *
0x1400027b2  call    ?DestroyCachedSslProv@@YAXPEAUCACHED_SSL_PROVIDER@@@Z; DestroyCachedSslProv(CACHED_SSL_PROVIDER *)
0x1400027b7  jmp     loc_140002C06
0x1400027bc  mov     eax, 28h ; '('
0x1400027c1  jmp     loc_140002634
0x1400027c6  mov     [r14+0F8h], r15; jumptable 000000014000258F case 10
0x1400027cd  mov     rdx, r9; Src
0x1400027d0  mov     r8d, [rbx+8]; Size
0x1400027d4  mov     rcx, r15; void *
0x1400027d7  call    memmove
0x1400027dc  mov     eax, [rbx+8]
0x1400027df  mov     [r14+100h], eax
0x1400027e6  jmp     loc_1400025D7
0x1400027eb  mov     [r14+1B0h], r15; jumptable 000000014000258F case 12
0x1400027f2  mov     rcx, r15
0x1400027f5  mov     eax, 2
0x1400027fa  lea     rcx, [rcx+80h]
0x140002801  movups  xmm0, xmmword ptr [r9]
0x140002805  lea     r9, [r9+80h]
0x14000280c  movups  xmmword ptr [rcx-80h], xmm0
0x140002810  movups  xmm1, xmmword ptr [r9-70h]
0x140002815  movups  xmmword ptr [rcx-70h], xmm1
0x140002819  movups  xmm0, xmmword ptr [r9-60h]
0x14000281e  movups  xmmword ptr [rcx-60h], xmm0
0x140002822  movups  xmm1, xmmword ptr [r9-50h]
0x140002827  movups  xmmword ptr [rcx-50h], xmm1
0x14000282b  movups  xmm0, xmmword ptr [r9-40h]
0x140002830  movups  xmmword ptr [rcx-40h], xmm0
0x140002834  movups  xmm1, xmmword ptr [r9-30h]
0x140002839  movups  xmmword ptr [rcx-30h], xmm1
0x14000283d  movups  xmm0, xmmword ptr [r9-20h]
0x140002842  movups  xmmword ptr [rcx-20h], xmm0
0x140002846  movups  xmm1, xmmword ptr [r9-10h]
0x14000284b  movups  xmmword ptr [rcx-10h], xmm1
0x14000284f  sub     rax, 1
0x140002853  jnz     short loc_1400027FA
0x140002855  mov     rax, [r9]
0x140002858  mov     [rcx], rax
0x14000285b  mov     eax, [rbx+8]
0x14000285e  add     rax, 7
0x140002862  jmp     loc_1400025EB
0x140002867  xor     eax, eax; jumptable 000000014000258F case 0
0x140002869  add     rsp, 48h
0x14000286d  pop     r15
0x14000286f  pop     r14
0x140002871  pop     r13
0x140002873  pop     r12
0x140002875  pop     rdi
0x140002876  pop     rsi
0x140002877  pop     rbp
0x140002878  pop     rbx
0x140002879  retn
0x14000287b  mov     [r14+0D8h], r15; jumptable 000000014000258F case 6
0x140002882  mov     rdx, r9; Src
0x140002885  mov     r8d, [rbx+8]; Size
0x140002889  mov     rcx, r15; void *
0x14000288c  call    memmove
0x140002891  mov     eax, [rbx+8]
0x140002894  mov     [r14+0E0h], eax
0x14000289b  jmp     loc_1400025D7
0x1400028a0  mov     [r14+58h], rsi
0x1400028a4  lea     rax, [r12+7]
0x1400028a9  lea     rdi, unk_140019100
0x1400028b0  jmp     loc_1400025DE
0x1400028b5  mov     r13d, [r9+4]; jumptable 000000014000258F case 1
0x1400028b9  mov     eax, r13d
0x1400028bc  test    r13d, r13d
0x1400028bf  jz      short loc_1400028CA
0x1400028c1  cmp     eax, 1
0x1400028c4  jnz     loc_140002C01
0x1400028ca  cmp     dword ptr [rbx+4], 0C2h
0x1400028d1  jb      loc_140002C01
0x1400028d7  test    r14, r14
0x1400028da  jz      loc_1400025F2
0x1400028e0  mov     eax, [r9]
0x1400028e3  mov     [r14+8], eax
0x1400028e7  mov     eax, [r9+4]
0x1400028eb  mov     [r14+0Ch], eax
0x1400028ef  mov     rax, [r9+8]
0x1400028f3  mov     [r14+10h], rax
0x1400028f7  mov     eax, [r9+10h]
0x1400028fb  mov     [r14+18h], eax
0x1400028ff  movzx   eax, byte ptr [r9+2Ch]
0x140002904  mov     [r14+20h], al
0x140002908  mov     eax, [r9+1Ch]
0x14000290c  mov     [r14+1Ch], eax
0x140002910  mov     rax, [r9+30h]
0x140002914  mov     [r14+60h], rax
0x140002918  mov     rax, [r9+38h]
0x14000291c  mov     [r14+68h], rax
0x140002920  mov     eax, [r9+14h]
0x140002924  mov     [r14+38h], eax
0x140002928  mov     eax, [r9+18h]
0x14000292c  mov     [r14+3Ch], eax
0x140002930  mov     eax, [r9+20h]
0x140002934  mov     [r14+40h], eax
0x140002938  mov     eax, [r9+24h]
0x14000293c  mov     [r14+48h], eax
0x140002940  mov     eax, [r9+98h]
0x140002947  mov     [r14+44h], eax
0x14000294b  mov     eax, [r9+0B0h]
0x140002952  mov     [r14+74h], eax
0x140002956  mov     rax, [r9+0A0h]
0x14000295d  mov     [r14+78h], rax
0x140002961  mov     rax, [r9+0A8h]
0x140002968  mov     [r14+80h], rax
0x14000296f  movzx   eax, word ptr [r9+0B4h]
0x140002977  mov     [r14+88h], ax
0x14000297f  movzx   eax, word ptr [r9+0B6h]
0x140002987  mov     [r14+8Ah], ax
0x14000298f  mov     eax, [r9+0B8h]
0x140002996  mov     [r14+90h], eax
0x14000299d  mov     eax, [r9+0BCh]
0x1400029a4  mov     [r14+1F4h], eax
0x1400029ab  movzx   eax, byte ptr [r9+0C0h]
0x1400029b3  mov     [r14+1F0h], al
0x1400029ba  movzx   eax, byte ptr [r9+0C1h]
0x1400029c2  mov     [r14+1F8h], al
0x1400029c9  mov     eax, [r9+28h]
0x1400029cd  mov     [r14+0E4h], eax
0x1400029d4  mov     eax, [r9+94h]
0x1400029db  mov     [r14+1A4h], eax
0x1400029e2  mov     eax, [r9+90h]
0x1400029e9  mov     [r14+1A0h], eax
0x1400029f0  mov     rax, [r9+40h]
0x1400029f4  mov     [r14+118h], rax
0x1400029fb  mov     eax, [r9+48h]
0x1400029ff  mov     [r14+120h], eax
0x140002a06  mov     rax, [r9+50h]
0x140002a0a  mov     [r14+138h], rax
0x140002a11  mov     eax, [rbx+4]
0x140002a14  add     eax, 10h
0x140002a17  add     rbx, rax
0x140002a1a  mov     r8d, [rbx]
0x140002a1d  jmp     loc_140002555
0x140002a22  cmp     r13d, 1; jumptable 000000014000258F case 4
0x140002a26  jnb     loc_140002C01
0x140002a2c  mov     [r14+98h], r15
0x140002a33  mov     rdx, r9; Src
0x140002a36  mov     r8d, [rbx+8]; Size
0x140002a3a  mov     rcx, r15; void *
0x140002a3d  call    memmove
0x140002a42  mov     eax, [rbx+8]
  ... truncated ...
```
