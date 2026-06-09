# CUnsquish::GetTypes(__MIDL___MIDL_itf_mfobjects_0000_0009_0003 * *,uint *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 * *,uint *)

- ea: `0x1800b1578`
- end: `0x1800b180b`
- name: `?GetTypes@CUnsquish@@QEAAJPEAPEAU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@PEAI01@Z`
- size: `659`
- prototype: `__int64 __fastcall(CUnsquish *this, LPVOID *, unsigned int *, struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180084128`

## callees

- `0x18002146c`
- `0x180024390`
- `0x1800b1578`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b1722`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b172e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b1722`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b172e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b15f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b168e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b15f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b168e`

## pseudocode

```c
__int64 __fastcall CUnsquish::GetTypes(
        CUnsquish *this,
        LPVOID *a2,
        unsigned int *a3,
        struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 **a4,
        unsigned int *a5)
{
  __int64 v5; // rax
  unsigned int v9; // r8d
  __int64 v11; // r9
  unsigned int i; // edx
  int v13; // eax
  struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *v14; // rbx
  struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *v15; // rax
  CallStackTracing *v16; // rcx
  unsigned int v17; // ebp
  struct CallStackContext *ThreadRelativeContext; // rax
  int v19; // r8d
  struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *v20; // r10
  struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *v21; // rax
  CallStackTracing *v22; // rcx
  void *v23; // rcx
  __int64 v24; // rcx
  unsigned int v25; // r9d
  __int64 v26; // r11
  unsigned int v27; // edi
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rdx

  v5 = *((_QWORD *)this + 3);
  *a3 = 0;
  *a2 = 0;
  v9 = *(_DWORD *)(v5 + 8);
  *a4 = 0;
  *a5 = 0;
  if ( v9 )
  {
    v11 = *(_QWORD *)(v5 + 16);
    for ( i = 0; i < v9; ++i )
    {
      v13 = *(_DWORD *)(v11 + 48LL * i + 8);
      if ( (*(_BYTE *)(v11 + 48LL * i) & 8) != 0 )
        *a5 += v13;
      else
        *a3 += v13;
    }
  }
  v14 = 0;
  if ( *a3 )
  {
    v15 = (struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *)CoTaskMemAlloc(32LL * *a3);
    *a2 = v15;
    v14 = v15;
    if ( !v15 )
    {
      v16 = CallStackTracing::s_wpInstance;
      v17 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v16 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( !v16->m_fEnabled )
        goto LABEL_26;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v16);
      if ( ThreadRelativeContext->m_result == -2147024882 )
        goto LABEL_26;
      v19 = 808;
LABEL_25:
      CallStackContext::TraceFailure(ThreadRelativeContext, "CUnsquish::GetTypes", v19, -2147024882);
LABEL_26:
      CoTaskMemFree(*a2);
      v23 = *a4;
      *a2 = 0;
      CoTaskMemFree(v23);
      *a4 = 0;
      *a3 = 0;
      *a5 = 0;
      return v17;
    }
  }
  v20 = 0;
  if ( *a5 )
  {
    v21 = (struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *)CoTaskMemAlloc(32LL * *a5);
    *a4 = v21;
    v20 = v21;
    if ( !v21 )
    {
      v22 = CallStackTracing::s_wpInstance;
      v17 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v22 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( !v22->m_fEnabled )
        goto LABEL_26;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v22);
      if ( ThreadRelativeContext->m_result == -2147024882 )
        goto LABEL_26;
      v19 = 817;
      goto LABEL_25;
    }
  }
  v24 = *((_QWORD *)this + 3);
  v17 = 0;
  if ( *(_DWORD *)(v24 + 8) )
  {
    v25 = 0;
    do
    {
      v26 = *(_QWORD *)(v24 + 16);
      v27 = 0;
      v28 = *(_DWORD *)(v26 + 48LL * v25 + 8);
      if ( (*(_BYTE *)(v26 + 48LL * v25) & 8) != 0 )
      {
        if ( v28 )
        {
          do
          {
            v30 = v27++;
            v30 *= 2;
            *(_OWORD *)v20 = *(_OWORD *)*(_QWORD *)(*(_QWORD *)(v26 + 48LL * v25 + 16) + 8 * v30);
            *((_OWORD *)v20 + 1) = *(_OWORD *)*(_QWORD *)(*(_QWORD *)(v26 + 48LL * v25 + 16) + 8 * v30 + 8);
            v20 = (struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *)((char *)v20 + 32);
          }
          while ( v27 < *(_DWORD *)(v26 + 48LL * v25 + 8) );
        }
      }
      else if ( v28 )
      {
        do
        {
          v29 = v27++;
          v29 *= 2;
          *(_OWORD *)v14 = *(_OWORD *)*(_QWORD *)(*(_QWORD *)(v26 + 48LL * v25 + 16) + 8 * v29);
          *((_OWORD *)v14 + 1) = *(_OWORD *)*(_QWORD *)(*(_QWORD *)(v26 + 48LL * v25 + 16) + 8 * v29 + 8);
          v14 = (struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *)((char *)v14 + 32);
        }
        while ( v27 < *(_DWORD *)(v26 + 48LL * v25 + 8) );
      }
      v24 = *((_QWORD *)this + 3);
      ++v25;
    }
    while ( v25 < *(_DWORD *)(v24 + 8) );
  }
  return v17;
}

```

## disassembly

```asm
0x1800b1578  push    rbx
0x1800b157a  push    rbp
0x1800b157b  push    rsi
0x1800b157c  push    rdi
0x1800b157d  push    r12
0x1800b157f  push    r13
0x1800b1581  push    r14
0x1800b1583  push    r15
0x1800b1585  sub     rsp, 28h
0x1800b1589  mov     rax, [rcx+18h]
0x1800b158d  xor     r12d, r12d
0x1800b1590  mov     rsi, [rsp+68h+arg_20]
0x1800b1598  mov     rdi, r8
0x1800b159b  mov     [r8], r12d
0x1800b159e  mov     r15, r9
0x1800b15a1  mov     r14, rdx
0x1800b15a4  mov     [rdx], r12
0x1800b15a7  mov     r8d, [rax+8]
0x1800b15ab  mov     r13, rcx
0x1800b15ae  mov     [r9], r12
0x1800b15b1  mov     [rsi], r12d
0x1800b15b4  test    r8d, r8d
0x1800b15b7  jz      short loc_1800B15E2
0x1800b15b9  mov     r9, [rax+10h]
0x1800b15bd  mov     edx, r12d
0x1800b15c0  mov     eax, edx
0x1800b15c2  lea     rcx, [rax+rax*2]
0x1800b15c6  add     rcx, rcx
0x1800b15c9  test    byte ptr [r9+rcx*8], 8
0x1800b15ce  mov     eax, [r9+rcx*8+8]
0x1800b15d3  jnz     short loc_1800B15D9
0x1800b15d5  add     [rdi], eax
0x1800b15d7  jmp     short loc_1800B15DB
0x1800b15d9  add     [rsi], eax
0x1800b15db  inc     edx
0x1800b15dd  cmp     edx, r8d
0x1800b15e0  jb      short loc_1800B15C0
0x1800b15e2  mov     rbx, r12
0x1800b15e5  cmp     [rdi], r12d
0x1800b15e8  jz      loc_1800B167C
0x1800b15ee  mov     ecx, [rdi]
0x1800b15f0  shl     rcx, 5; cb
0x1800b15f4  call    cs:__imp_CoTaskMemAlloc
0x1800b15fa  mov     [r14], rax
0x1800b15fd  mov     rbx, rax
0x1800b1600  test    rax, rax
0x1800b1603  jnz     short loc_1800B167C
0x1800b1605  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b160c  mov     ebx, 8007000Eh
0x1800b1611  mov     ebp, ebx
0x1800b1613  test    rcx, rcx
0x1800b1616  jnz     short loc_1800B1656
0x1800b1618  mov     rax, cs:stru_1801FC290.__vftable
0x1800b161f  lea     rcx, stru_1801FC290
0x1800b1626  mov     edx, 7F0h
0x1800b162b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1632  mov     rax, [rax+8]
0x1800b1636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b163b  test    eax, eax
0x1800b163d  jnz     short loc_1800B164F
0x1800b163f  lea     rcx, stru_1801F8A30
0x1800b1646  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b164d  jmp     short loc_1800B1656
0x1800b164f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b1656  cmp     [rcx+8], r12b
0x1800b165a  jz      loc_1800B171F
0x1800b1660  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b1665  cmp     [rax+7CCh], ebx
0x1800b166b  jz      loc_1800B171F
0x1800b1671  mov     r8d, 328h
0x1800b1677  jmp     loc_1800B170D
0x1800b167c  mov     r10, r12
0x1800b167f  cmp     [rsi], r12d
0x1800b1682  jz      loc_1800B1742
0x1800b1688  mov     ecx, [rsi]
0x1800b168a  shl     rcx, 5; cb
0x1800b168e  call    cs:__imp_CoTaskMemAlloc
0x1800b1694  mov     [r15], rax
0x1800b1697  mov     r10, rax
0x1800b169a  test    rax, rax
0x1800b169d  jnz     loc_1800B1742
0x1800b16a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b16aa  mov     ebx, 8007000Eh
0x1800b16af  mov     ebp, ebx
0x1800b16b1  test    rcx, rcx
0x1800b16b4  jnz     short loc_1800B16F4
0x1800b16b6  mov     rax, cs:stru_1801FC290.__vftable
0x1800b16bd  lea     rcx, stru_1801FC290
0x1800b16c4  mov     edx, 7F0h
0x1800b16c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b16d0  mov     rax, [rax+8]
0x1800b16d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b16d9  test    eax, eax
0x1800b16db  jnz     short loc_1800B16ED
0x1800b16dd  lea     rcx, stru_1801F8A30
0x1800b16e4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b16eb  jmp     short loc_1800B16F4
0x1800b16ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b16f4  cmp     [rcx+8], r12b
0x1800b16f8  jz      short loc_1800B171F
0x1800b16fa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b16ff  cmp     [rax+7CCh], ebx
0x1800b1705  jz      short loc_1800B171F
0x1800b1707  mov     r8d, 331h; int
0x1800b170d  mov     r9d, ebx; int
0x1800b1710  lea     rdx, aCunsquishGetty; "CUnsquish::GetTypes"
0x1800b1717  mov     rcx, rax; this
0x1800b171a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b171f  mov     rcx, [r14]; pv
0x1800b1722  call    cs:__imp_CoTaskMemFree
0x1800b1728  mov     rcx, [r15]; pv
0x1800b172b  mov     [r14], r12
0x1800b172e  call    cs:__imp_CoTaskMemFree
0x1800b1734  mov     [r15], r12
0x1800b1737  mov     [rdi], r12d
0x1800b173a  mov     [rsi], r12d
0x1800b173d  jmp     loc_1800B17F8
0x1800b1742  mov     rcx, [r13+18h]
0x1800b1746  mov     ebp, r12d
0x1800b1749  cmp     [rcx+8], r12d
0x1800b174d  jbe     loc_1800B17F8
0x1800b1753  mov     r9d, r12d
0x1800b1756  mov     r11, [rcx+10h]
0x1800b175a  mov     edi, r12d
0x1800b175d  mov     eax, r9d
0x1800b1760  lea     r8, [rax+rax*2]
0x1800b1764  add     r8, r8
0x1800b1767  test    byte ptr [r11+r8*8], 8
0x1800b176c  mov     eax, [r11+r8*8+8]
0x1800b1771  jnz     short loc_1800B17AD
0x1800b1773  test    eax, eax
0x1800b1775  jz      short loc_1800B17E7
0x1800b1777  mov     rax, [r11+r8*8+10h]
0x1800b177c  mov     edx, edi
0x1800b177e  inc     edi
0x1800b1780  add     rdx, rdx
0x1800b1783  mov     rcx, [rax+rdx*8]
0x1800b1787  movups  xmm0, xmmword ptr [rcx]
0x1800b178a  movdqu  xmmword ptr [rbx], xmm0
0x1800b178e  mov     rax, [r11+r8*8+10h]
0x1800b1793  mov     rcx, [rax+rdx*8+8]
0x1800b1798  movups  xmm0, xmmword ptr [rcx]
0x1800b179b  movdqu  xmmword ptr [rbx+10h], xmm0
0x1800b17a0  add     rbx, 20h ; ' '
0x1800b17a4  cmp     edi, [r11+r8*8+8]
0x1800b17a9  jb      short loc_1800B1777
0x1800b17ab  jmp     short loc_1800B17E7
0x1800b17ad  test    eax, eax
0x1800b17af  jz      short loc_1800B17E7
0x1800b17b1  mov     rax, [r11+r8*8+10h]
0x1800b17b6  mov     edx, edi
0x1800b17b8  inc     edi
0x1800b17ba  add     rdx, rdx
0x1800b17bd  mov     rcx, [rax+rdx*8]
0x1800b17c1  movups  xmm0, xmmword ptr [rcx]
0x1800b17c4  movdqu  xmmword ptr [r10], xmm0
0x1800b17c9  mov     rax, [r11+r8*8+10h]
0x1800b17ce  mov     rcx, [rax+rdx*8+8]
0x1800b17d3  movups  xmm0, xmmword ptr [rcx]
0x1800b17d6  movdqu  xmmword ptr [r10+10h], xmm0
0x1800b17dc  add     r10, 20h ; ' '
0x1800b17e0  cmp     edi, [r11+r8*8+8]
0x1800b17e5  jb      short loc_1800B17B1
0x1800b17e7  mov     rcx, [r13+18h]
0x1800b17eb  inc     r9d
0x1800b17ee  cmp     r9d, [rcx+8]
0x1800b17f2  jb      loc_1800B1756
0x1800b17f8  mov     eax, ebp
0x1800b17fa  add     rsp, 28h
0x1800b17fe  pop     r15
0x1800b1800  pop     r14
0x1800b1802  pop     r13
0x1800b1804  pop     r12
0x1800b1806  pop     rdi
0x1800b1807  pop     rsi
0x1800b1808  pop     rbp
0x1800b1809  pop     rbx
0x1800b180a  retn
```
