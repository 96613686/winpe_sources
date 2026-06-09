# KerbPurgeCompoundedTickets(void)

- ea: `0x18004f220`
- end: `0x18004fa22`
- name: `?KerbPurgeCompoundedTickets@@YAJXZ`
- size: `2050`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180088264`
- `0x1800a1e50`
- `0x1800a2d40`
- `0x1800a3040`
- `0x1800acc7c`

## callees

- `0x18000a650`
- `0x18004f220`
- `0x180061d14`
- `0x18006557c`
- `0x180066994`
- `0x180067c48`
- `0x180070680`
- `0x180070a50`
- `0x18007108c`
- `0x18008b70c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f297`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f297`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f9f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f9f7`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18004f2e7`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18004f30e`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18004f2e7`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18004f30e`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18004f3ad`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18004f7ee`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18004f3ad`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18004f7ee`
- `ntdll!RtlReleaseResource` at `0x18004f320`
- `ntdll!RtlReleaseResource` at `0x18004f3cf`
- `ntdll!RtlReleaseResource` at `0x18004f4bf`
- `ntdll!RtlReleaseResource` at `0x18004f660`
- `ntdll!RtlReleaseResource` at `0x18004f80c`
- `ntdll!RtlReleaseResource` at `0x18004f8fe`
- `ntdll!RtlReleaseResource` at `0x18004f320`
- `ntdll!RtlReleaseResource` at `0x18004f3cf`
- `ntdll!RtlReleaseResource` at `0x18004f4bf`
- `ntdll!RtlReleaseResource` at `0x18004f660`
- `ntdll!RtlReleaseResource` at `0x18004f80c`
- `ntdll!RtlReleaseResource` at `0x18004f8fe`
- `ntdll!RtlAcquireResourceShared` at `0x18004f39b`
- `ntdll!RtlAcquireResourceShared` at `0x18004f7dc`
- `ntdll!RtlAcquireResourceShared` at `0x18004f39b`
- `ntdll!RtlAcquireResourceShared` at `0x18004f7dc`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004f2d8`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004f41b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004f5c0`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004f85a`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004f2d8`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004f41b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004f5c0`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004f85a`
- `ntdll!RtlEnterCriticalSection` at `0x18004f55c`
- `ntdll!RtlEnterCriticalSection` at `0x18004f74a`
- `ntdll!RtlEnterCriticalSection` at `0x18004f55c`
- `ntdll!RtlEnterCriticalSection` at `0x18004f74a`
- `ntdll!RtlLeaveCriticalSection` at `0x18004f709`
- `ntdll!RtlLeaveCriticalSection` at `0x18004f9cc`
- `ntdll!RtlLeaveCriticalSection` at `0x18004f709`
- `ntdll!RtlLeaveCriticalSection` at `0x18004f9cc`

## string_xrefs

- `0x18004f53a`: `Purged compound ticket from %#x:%x primary creds\n`
- `0x18004f547`: `KerbPurgeCompoundedTickets`
- `0x18004f6e7`: `KerbPurgeCompoundedTickets`
- `0x18004f983`: `KerbPurgeCompoundedTickets`
- `0x18004f6da`: `Purged compound ticket from %#x:%x credman creds\n`
- `0x18004f976`: `Purged compound ticket from %#x:%x supplied creds\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 KerbPurgeCompoundedTickets(void)
{
  ULONG NumberGenericTableElements; // esi
  size_t v1; // rdi
  void *v2; // r15
  HLOCAL v4; // rax
  _QWORD *v5; // r14
  ULONG v6; // ebx
  PVOID i; // rax
  __int64 v8; // rax
  char *v9; // rbx
  HLOCAL *v10; // rax
  struct _KERB_TICKET_CACHE_ENTRY *v11; // rdi
  struct _KERB_TICKET_CACHE_ENTRY **v12; // rsi
  struct _KERB_TICKET_CACHE_ENTRY **v13; // r15
  int v14; // r14d
  struct _KERB_TICKET_CACHE_ENTRY *v15; // rbx
  struct _KERB_TICKET_CACHE_ENTRY *v16; // rcx
  struct _KERB_TICKET_CACHE_ENTRY *k; // rbx
  struct _KERB_TICKET_CACHE_ENTRY *v18; // rcx
  struct _KERB_TICKET_CACHE_ENTRY *m; // rbx
  struct _KERB_TICKET_CACHE_ENTRY *v20; // rcx
  _QWORD *v21; // rdi
  _BYTE *v22; // rbx
  __int64 v23; // rbx
  utl::_RefCountBase *v24; // rcx
  char *v25; // rdi
  char *n; // r12
  _QWORD *v27; // rbx
  struct _KERB_TICKET_CACHE_ENTRY *v28; // rdi
  struct _KERB_TICKET_CACHE_ENTRY **v29; // rsi
  struct _KERB_TICKET_CACHE_ENTRY **v30; // r15
  int v31; // r14d
  struct _KERB_TICKET_CACHE_ENTRY *v32; // rbx
  struct _KERB_TICKET_CACHE_ENTRY *v33; // rcx
  struct _KERB_TICKET_CACHE_ENTRY *ii; // rbx
  struct _KERB_TICKET_CACHE_ENTRY *v35; // rcx
  struct _KERB_TICKET_CACHE_ENTRY *jj; // rbx
  struct _KERB_TICKET_CACHE_ENTRY *v37; // rcx
  _QWORD *v38; // rdi
  _BYTE *v39; // rbx
  __int64 v40; // rbx
  utl::_RefCountBase *v41; // rcx
  __int64 *kk; // r13
  __int64 v43; // r15
  __int64 *v44; // rax
  _QWORD *v45; // rbx
  struct _KERB_TICKET_CACHE_ENTRY *v46; // rdi
  struct _KERB_TICKET_CACHE_ENTRY **v47; // r14
  struct _KERB_TICKET_CACHE_ENTRY **v48; // r12
  int v49; // esi
  struct _KERB_TICKET_CACHE_ENTRY *v50; // rbx
  struct _KERB_TICKET_CACHE_ENTRY *v51; // rcx
  struct _KERB_TICKET_CACHE_ENTRY *mm; // rbx
  struct _KERB_TICKET_CACHE_ENTRY *v53; // rcx
  struct _KERB_TICKET_CACHE_ENTRY *nn; // rbx
  struct _KERB_TICKET_CACHE_ENTRY *v55; // rcx
  _QWORD *v56; // rdi
  _BYTE *v57; // rbx
  __int64 v58; // rbx
  utl::_RefCountBase *v59; // rcx
  char *v60; // [rsp+30h] [rbp-D0h]
  int j; // [rsp+38h] [rbp-C8h]
  ULONG v62; // [rsp+3Ch] [rbp-C4h]
  void *v63; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v64; // [rsp+48h] [rbp-B8h]
  __int128 v65; // [rsp+58h] [rbp-A8h]
  _QWORD *v66; // [rsp+68h] [rbp-98h]
  HLOCAL hMem; // [rsp+70h] [rbp-90h]
  _BYTE *Buffer; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v69[64]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v70; // [rsp+C0h] [rbp-40h]
  _BYTE v71[184]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v72; // [rsp+1B0h] [rbp+B0h]
  __int64 v73; // [rsp+1D8h] [rbp+D8h]
  __int64 v74; // [rsp+1E0h] [rbp+E0h]
  __int128 v75; // [rsp+200h] [rbp+100h]
  __int64 v76; // [rsp+228h] [rbp+128h]
  int v77; // [rsp+230h] [rbp+130h]
  __int64 v78; // [rsp+3A0h] [rbp+2A0h]
  __int128 v79; // [rsp+3A8h] [rbp+2A8h]
  __int128 v80; // [rsp+3B8h] [rbp+2B8h]

  NumberGenericTableElements = KerbGlobalLogonSessionTable.NumberGenericTableElements;
  v62 = KerbGlobalLogonSessionTable.NumberGenericTableElements;
  v1 = 8LL * KerbGlobalLogonSessionTable.NumberGenericTableElements;
  if ( KerbGlobalPackageState == 1 )
  {
    v2 = (void *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocateLsaHeap)((unsigned int)v1);
    hMem = v2;
  }
  else
  {
    v4 = LocalAlloc(0, 8LL * KerbGlobalLogonSessionTable.NumberGenericTableElements);
    v2 = v4;
    hMem = v4;
    if ( v4 )
    {
      memset_0(v4, 0, v1);
      goto LABEL_7;
    }
  }
  if ( !v2 )
    return 3221225495LL;
LABEL_7:
  v5 = v2;
  v66 = v2;
  v6 = 0;
  memset_0(v2, 0, v1);
  RtlAcquireResourceExclusive(&KerbGlobalLogonSessionTableLock, 1u);
  for ( i = RtlEnumerateGenericTableAvl(&KerbGlobalLogonSessionTable, 1u);
        i;
        i = RtlEnumerateGenericTableAvl(&KerbGlobalLogonSessionTable, 0) )
  {
    if ( v6 >= NumberGenericTableElements )
      break;
    *((_QWORD *)v2 + v6++) = *(_QWORD *)(*(_QWORD *)i + 64LL);
  }
  RtlReleaseResource(&KerbGlobalLogonSessionTableLock);
  v8 = 0;
  for ( j = 0; (unsigned int)v8 < NumberGenericTableElements; j = v8 )
  {
    v72 = 0;
    v73 = 0;
    v74 = 0;
    v75 = 0;
    v76 = 0;
    v77 = 0;
    v78 = 0;
    v79 = 0;
    v80 = 0;
    v9 = 0;
    v60 = 0;
    v70 = v5[v8];
    Buffer = v69;
    RtlAcquireResourceShared(&KerbGlobalLogonSessionTableLock, 1u);
    v10 = (HLOCAL *)RtlLookupElementGenericTableAvl(&KerbGlobalLogonSessionTable, &Buffer);
    if ( v10 )
    {
      v9 = (char *)*v10;
      v60 = (char *)*v10;
      if ( *v10 )
        _InterlockedIncrement((volatile signed __int32 *)v9);
    }
    RtlReleaseResource(&KerbGlobalLogonSessionTableLock);
    _KERB_PRIMARY_CREDENTIAL::~_KERB_PRIMARY_CREDENTIAL((_KERB_PRIMARY_CREDENTIAL *)v71);
    if ( v9 )
    {
      kerb_credential_lock_guard::kerb_credential_lock_guard(&v63, v9 + 120);
      v11 = (struct _KERB_TICKET_CACHE_ENTRY *)(v9 + 360);
      v12 = (struct _KERB_TICKET_CACHE_ENTRY **)(v9 + 280);
      v13 = (struct _KERB_TICKET_CACHE_ENTRY **)(v9 + 320);
      v14 = -1073741772;
      RtlAcquireResourceExclusive(&KerberosTicketCacheLock, 1u);
      _mm_lfence();
      v15 = (struct _KERB_TICKET_CACHE_ENTRY *)*((_QWORD *)v9 + 45);
      if ( *(struct _KERB_TICKET_CACHE_ENTRY **)v11 != v11 )
      {
        do
        {
          v65 = 0;
          if ( *((char *)v15 + 164) < 0 )
          {
            v16 = v15;
            v14 = 0;
            v15 = (struct _KERB_TICKET_CACHE_ENTRY *)*((_QWORD *)v15 + 1);
            KerbRemoveTicketCacheEntry(v16);
          }
          v15 = *(struct _KERB_TICKET_CACHE_ENTRY **)v15;
        }
        while ( v15 != v11 );
      }
      for ( k = *v12; k != (struct _KERB_TICKET_CACHE_ENTRY *)v12; k = *(struct _KERB_TICKET_CACHE_ENTRY **)k )
      {
        v65 = 0;
        if ( *((char *)k + 164) < 0 )
        {
          v18 = k;
          v14 = 0;
          k = (struct _KERB_TICKET_CACHE_ENTRY *)*((_QWORD *)k + 1);
          KerbRemoveTicketCacheEntry(v18);
        }
      }
      for ( m = *v13; m != (struct _KERB_TICKET_CACHE_ENTRY *)v13; m = *(struct _KERB_TICKET_CACHE_ENTRY **)m )
      {
        v65 = 0;
        if ( *((char *)m + 164) < 0 )
        {
          v20 = m;
          v14 = 0;
          m = (struct _KERB_TICKET_CACHE_ENTRY *)*((_QWORD *)m + 1);
          KerbRemoveTicketCacheEntry(v20);
        }
      }
      RtlReleaseResource(&KerberosTicketCacheLock);
      v21 = v63;
      if ( v63 != (void *)-1LL )
      {
        v22 = v64;
        v64 = v63;
        v23 = (v22 - (_BYTE *)v63) >> 4;
        if ( v23 )
        {
          do
          {
            --v23;
            v24 = (utl::_RefCountBase *)v21[2 * v23 + 1];
            if ( v24 )
              utl::_RefCountBase::_DecStrong(v24);
          }
          while ( v23 );
          v21 = v63;
        }
        operator delete(v21, (const struct std::nothrow_t *)std::nothrow);
      }
      v25 = v60;
      if ( v14 >= 0 )
        KerbTracerT::Log(
          3,
          "KerbPurgeCompoundedTickets",
          1359,
          "Purged compound ticket from %#x:%x primary creds\n",
          *((_DWORD *)v60 + 17),
          *((_DWORD *)v60 + 16));
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v60 + 24));
      for ( n = (char *)*((_QWORD *)v60 + 1); n != v60 + 8; n = *(char **)n )
      {
        v27 = (_QWORD *)*((_QWORD *)n + 8);
        if ( v27 )
        {
          kerb_credential_lock_guard::kerb_credential_lock_guard(&v63, *((_QWORD *)n + 8));
          v28 = (struct _KERB_TICKET_CACHE_ENTRY *)(v27 + 30);
          v29 = (struct _KERB_TICKET_CACHE_ENTRY **)(v27 + 20);
          v30 = (struct _KERB_TICKET_CACHE_ENTRY **)(v27 + 25);
          v31 = -1073741772;
          RtlAcquireResourceExclusive(&KerberosTicketCacheLock, 1u);
          _mm_lfence();
          v32 = (struct _KERB_TICKET_CACHE_ENTRY *)v27[30];
          if ( *(struct _KERB_TICKET_CACHE_ENTRY **)v28 != v28 )
          {
            do
            {
              v65 = 0;
              if ( *((char *)v32 + 164) < 0 )
              {
                v33 = v32;
                v31 = 0;
                v32 = (struct _KERB_TICKET_CACHE_ENTRY *)*((_QWORD *)v32 + 1);
                KerbRemoveTicketCacheEntry(v33);
              }
              v32 = *(struct _KERB_TICKET_CACHE_ENTRY **)v32;
            }
            while ( v32 != v28 );
          }
          for ( ii = *v29; ii != (struct _KERB_TICKET_CACHE_ENTRY *)v29; ii = *(struct _KERB_TICKET_CACHE_ENTRY **)ii )
          {
            v65 = 0;
            if ( *((char *)ii + 164) < 0 )
            {
              v35 = ii;
              v31 = 0;
              ii = (struct _KERB_TICKET_CACHE_ENTRY *)*((_QWORD *)ii + 1);
              KerbRemoveTicketCacheEntry(v35);
            }
          }
          for ( jj = *v30; jj != (struct _KERB_TICKET_CACHE_ENTRY *)v30; jj = *(struct _KERB_TICKET_CACHE_ENTRY **)jj )
          {
            v65 = 0;
            if ( *((char *)jj + 164) < 0 )
            {
              v37 = jj;
              v31 = 0;
              jj = (struct _KERB_TICKET_CACHE_ENTRY *)*((_QWORD *)jj + 1);
              KerbRemoveTicketCacheEntry(v37);
            }
          }
          RtlReleaseResource(&KerberosTicketCacheLock);
          v38 = v63;
          if ( v63 != (void *)-1LL )
          {
            v39 = v64;
            v64 = v63;
            v40 = (v39 - (_BYTE *)v63) >> 4;
            if ( v40 )
            {
              do
              {
                --v40;
                v41 = (utl::_RefCountBase *)v38[2 * v40 + 1];
                if ( v41 )
                  utl::_RefCountBase::_DecStrong(v41);
              }
              while ( v40 );
              v38 = v63;
            }
            operator delete(v38, (const struct std::nothrow_t *)std::nothrow);
          }
          v25 = v60;
          if ( v31 >= 0 )
            KerbTracerT::Log(
              3,
              "KerbPurgeCompoundedTickets",
              1384,
              "Purged compound ticket from %#x:%x credman creds\n",
              *((_DWORD *)v60 + 17),
              *((_DWORD *)v60 + 16));
        }
      }
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v25 + 24));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25, 0xFFFFFFFF) == 1 )
        KerbFreeLogonSession(v25);
      v5 = v66;
      NumberGenericTableElements = v62;
    }
    v8 = (unsigned int)(j + 1);
  }
  RtlEnterCriticalSection(&stru_180144A70);
  for ( kk = (__int64 *)KerbCredentialList; kk != (__int64 *)&KerbCredentialList; kk = (__int64 *)*kk )
  {
    if ( kk[9] )
    {
      v72 = 0;
      v73 = 0;
      v74 = 0;
      v75 = 0;
      v76 = 0;
      v77 = 0;
      v78 = 0;
      v79 = 0;
      v80 = 0;
      v43 = 0;
      v70 = *(__int64 *)((char *)kk + 28);
      Buffer = v69;
      RtlAcquireResourceShared(&KerbGlobalLogonSessionTableLock, 1u);
      v44 = (__int64 *)RtlLookupElementGenericTableAvl(&KerbGlobalLogonSessionTable, &Buffer);
      if ( v44 )
      {
        v43 = *v44;
        if ( *v44 )
          _InterlockedIncrement((volatile signed __int32 *)v43);
      }
      RtlReleaseResource(&KerbGlobalLogonSessionTableLock);
      _KERB_PRIMARY_CREDENTIAL::~_KERB_PRIMARY_CREDENTIAL((_KERB_PRIMARY_CREDENTIAL *)v71);
      if ( v43 )
      {
        v45 = (_QWORD *)kk[9];
        kerb_credential_lock_guard::kerb_credential_lock_guard(&v63, v45);
        v46 = (struct _KERB_TICKET_CACHE_ENTRY *)(v45 + 30);
        v47 = (struct _KERB_TICKET_CACHE_ENTRY **)(v45 + 20);
        v48 = (struct _KERB_TICKET_CACHE_ENTRY **)(v45 + 25);
        v49 = -1073741772;
        RtlAcquireResourceExclusive(&KerberosTicketCacheLock, 1u);
        _mm_lfence();
        v50 = (struct _KERB_TICKET_CACHE_ENTRY *)v45[30];
        if ( *(struct _KERB_TICKET_CACHE_ENTRY **)v46 != v46 )
        {
          do
          {
            v65 = 0;
            if ( *((char *)v50 + 164) < 0 )
            {
              v51 = v50;
              v49 = 0;
              v50 = (struct _KERB_TICKET_CACHE_ENTRY *)*((_QWORD *)v50 + 1);
              KerbRemoveTicketCacheEntry(v51);
            }
            v50 = *(struct _KERB_TICKET_CACHE_ENTRY **)v50;
          }
          while ( v50 != v46 );
        }
        for ( mm = *v47; mm != (struct _KERB_TICKET_CACHE_ENTRY *)v47; mm = *(struct _KERB_TICKET_CACHE_ENTRY **)mm )
        {
          v65 = 0;
          if ( *((char *)mm + 164) < 0 )
          {
            v53 = mm;
            v49 = 0;
            mm = (struct _KERB_TICKET_CACHE_ENTRY *)*((_QWORD *)mm + 1);
            KerbRemoveTicketCacheEntry(v53);
          }
        }
        for ( nn = *v48; nn != (struct _KERB_TICKET_CACHE_ENTRY *)v48; nn = *(struct _KERB_TICKET_CACHE_ENTRY **)nn )
        {
          v65 = 0;
          if ( *((char *)nn + 164) < 0 )
          {
            v55 = nn;
            v49 = 0;
            nn = (struct _KERB_TICKET_CACHE_ENTRY *)*((_QWORD *)nn + 1);
            KerbRemoveTicketCacheEntry(v55);
          }
        }
        RtlReleaseResource(&KerberosTicketCacheLock);
        v56 = v63;
        if ( v63 != (void *)-1LL )
        {
          v57 = v64;
          v64 = v63;
          v58 = (v57 - (_BYTE *)v63) >> 4;
          if ( v58 )
          {
            do
            {
              --v58;
              v59 = (utl::_RefCountBase *)v56[2 * v58 + 1];
              if ( v59 )
                utl::_RefCountBase::_DecStrong(v59);
            }
            while ( v58 );
            v56 = v63;
          }
          operator delete(v56, (const struct std::nothrow_t *)std::nothrow);
        }
        if ( v49 >= 0 )
          KerbTracerT::Log(
            3,
            "KerbPurgeCompoundedTickets",
            1422,
            "Purged compound ticket from %#x:%x supplied creds\n",
            *(_DWORD *)(v43 + 68),
            *(_DWORD *)(v43 + 64));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v43, 0xFFFFFFFF) == 1 )
          KerbFreeLogonSession((char *)v43);
      }
    }
  }
  RtlLeaveCriticalSection(&stru_180144A70);
  if ( KerbGlobalPackageState == 1 )
    ((void (__fastcall *)(HLOCAL))LsaFunctions->FreeLsaHeap)(hMem);
  else
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x18004f220  push    rbp
0x18004f222  push    rbx
0x18004f223  push    rsi
0x18004f224  push    rdi
0x18004f225  push    r12
0x18004f227  push    r13
0x18004f229  push    r14
0x18004f22b  push    r15
0x18004f22d  lea     rbp, [rsp-348h]
0x18004f235  sub     rsp, 448h
0x18004f23c  mov     rax, cs:__security_cookie
0x18004f243  xor     rax, rsp
0x18004f246  mov     [rbp+380h+var_50], rax
0x18004f24d  xor     r12d, r12d
0x18004f250  mov     esi, cs:?KerbGlobalLogonSessionTable@@3U_RTL_AVL_TABLE@@A.NumberGenericTableElements; _RTL_AVL_TABLE KerbGlobalLogonSessionTable ...
0x18004f256  mov     [rsp+480h+var_444], esi
0x18004f25a  mov     edi, esi
0x18004f25c  shl     rdi, 3
0x18004f260  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18004f267  jnz     short loc_18004F292
0x18004f269  mov     ecx, edi
0x18004f26b  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18004f272  mov     rax, [rax+28h]
0x18004f276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f27b  mov     r15, rax
0x18004f27e  mov     [rsp+480h+hMem], rax
0x18004f283  test    r15, r15
0x18004f286  jnz     short loc_18004F2B7
0x18004f288  mov     eax, 0C0000017h
0x18004f28d  jmp     loc_18004F9FF
0x18004f292  mov     rdx, rdi; uBytes
0x18004f295  xor     ecx, ecx; uFlags
0x18004f297  call    cs:__imp_LocalAlloc
0x18004f29d  mov     r15, rax
0x18004f2a0  mov     [rsp+480h+hMem], rax
0x18004f2a5  test    rax, rax
0x18004f2a8  jz      short loc_18004F283
0x18004f2aa  mov     r8, rdi; Size
0x18004f2ad  xor     edx, edx; Val
0x18004f2af  mov     rcx, rax; void *
0x18004f2b2  call    memset_0
0x18004f2b7  mov     r14, r15
0x18004f2ba  mov     [rsp+480h+var_418], r15
0x18004f2bf  mov     ebx, r12d
0x18004f2c2  mov     r8, rdi; Size
0x18004f2c5  xor     edx, edx; Val
0x18004f2c7  mov     rcx, r15; void *
0x18004f2ca  call    memset_0
0x18004f2cf  mov     dl, 1; Wait
0x18004f2d1  lea     rcx, ?KerbGlobalLogonSessionTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18004f2d8  call    cs:__imp_RtlAcquireResourceExclusive
0x18004f2de  mov     dl, 1; Restart
0x18004f2e0  lea     rcx, ?KerbGlobalLogonSessionTable@@3U_RTL_AVL_TABLE@@A; Table
0x18004f2e7  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18004f2ed  test    rax, rax
0x18004f2f0  jz      short loc_18004F319
0x18004f2f2  cmp     ebx, esi
0x18004f2f4  jnb     short loc_18004F319
0x18004f2f6  mov     rax, [rax]
0x18004f2f9  mov     ecx, ebx
0x18004f2fb  mov     rax, [rax+40h]
0x18004f2ff  mov     [r14+rcx*8], rax
0x18004f303  inc     ebx
0x18004f305  xor     edx, edx; Restart
0x18004f307  lea     rcx, ?KerbGlobalLogonSessionTable@@3U_RTL_AVL_TABLE@@A; Table
0x18004f30e  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18004f314  test    rax, rax
0x18004f317  jnz     short loc_18004F2F2
0x18004f319  lea     rcx, ?KerbGlobalLogonSessionTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18004f320  call    cs:__imp_RtlReleaseResource
0x18004f326  mov     eax, r12d
0x18004f329  mov     [rsp+480h+var_448], eax
0x18004f32d  test    esi, esi
0x18004f32f  jz      loc_18004F743
0x18004f335  xorps   xmm0, xmm0
0x18004f338  movdqa  [rbp+380h+var_2D0], xmm0
0x18004f340  mov     [rbp+380h+var_2A8], r12
0x18004f347  mov     [rbp+380h+var_2A0], r12
0x18004f34e  movdqa  [rbp+380h+var_280], xmm0
0x18004f356  mov     [rbp+380h+var_258], r12
0x18004f35d  mov     [rbp+380h+var_250], r12d
0x18004f364  mov     [rbp+380h+var_E0], r12
0x18004f36b  movups  [rbp+380h+var_D8], xmm0
0x18004f372  movups  [rbp+380h+var_C8], xmm0
0x18004f379  mov     rbx, r12
0x18004f37c  mov     [rsp+480h+var_450], rbx
0x18004f381  mov     rcx, [r14+rax*8]
0x18004f385  mov     [rbp+380h+var_3C0], rcx
0x18004f389  lea     rax, [rbp+380h+var_400]
0x18004f38d  mov     [rsp+480h+Buffer], rax
0x18004f392  mov     dl, 1; Wait
0x18004f394  lea     rcx, ?KerbGlobalLogonSessionTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18004f39b  call    cs:__imp_RtlAcquireResourceShared
0x18004f3a1  lea     rdx, [rsp+480h+Buffer]; Buffer
0x18004f3a6  lea     rcx, ?KerbGlobalLogonSessionTable@@3U_RTL_AVL_TABLE@@A; Table
0x18004f3ad  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18004f3b3  test    rax, rax
0x18004f3b6  jz      short loc_18004F3C8
0x18004f3b8  mov     rbx, [rax]
0x18004f3bb  mov     [rsp+480h+var_450], rbx
0x18004f3c0  test    rbx, rbx
0x18004f3c3  jz      short loc_18004F3C8
0x18004f3c5  lock inc dword ptr [rbx]
0x18004f3c8  lea     rcx, ?KerbGlobalLogonSessionTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18004f3cf  call    cs:__imp_RtlReleaseResource
0x18004f3d5  nop
0x18004f3d6  lea     rcx, [rbp+380h+var_388]; this
0x18004f3da  call    ??1_KERB_PRIMARY_CREDENTIAL@@QEAA@XZ; _KERB_PRIMARY_CREDENTIAL::~_KERB_PRIMARY_CREDENTIAL(void)
0x18004f3df  test    rbx, rbx
0x18004f3e2  jz      loc_18004F731
0x18004f3e8  lea     rdx, [rbx+78h]
0x18004f3ec  lea     rcx, [rsp+480h+var_440]
0x18004f3f1  call    ??0kerb_credential_lock_guard@@QEAA@AEAU_KERB_PRIMARY_CREDENTIAL@@W4KerbLockType@@@Z; kerb_credential_lock_guard::kerb_credential_lock_guard(_KERB_PRIMARY_CREDENTIAL &,KerbLockType)
0x18004f3f6  nop
0x18004f3f7  lea     rdi, [rbx+168h]
0x18004f3fe  lea     rsi, [rbx+118h]
0x18004f405  lea     r15, [rbx+140h]
0x18004f40c  mov     r14d, 0C0000034h
0x18004f412  mov     dl, 1; Wait
0x18004f414  lea     rcx, ?KerberosTicketCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18004f41b  call    cs:__imp_RtlAcquireResourceExclusive
0x18004f421  lfence
0x18004f424  mov     rbx, [rdi]
0x18004f427  cmp     rbx, rdi
0x18004f42a  jz      short loc_18004F458
0x18004f42c  nop     dword ptr [rax+00h]
0x18004f430  xorps   xmm0, xmm0
0x18004f433  movups  [rsp+480h+var_428], xmm0
0x18004f438  test    byte ptr [rbx+0A4h], 80h
0x18004f43f  jz      short loc_18004F450
0x18004f441  mov     rcx, rbx; struct _KERB_TICKET_CACHE_ENTRY *
0x18004f444  mov     r14d, r12d
0x18004f447  mov     rbx, [rbx+8]
0x18004f44b  call    ?KerbRemoveTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbRemoveTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x18004f450  mov     rbx, [rbx]
0x18004f453  cmp     rbx, rdi
0x18004f456  jnz     short loc_18004F430
0x18004f458  mov     rbx, [rsi]
0x18004f45b  cmp     rbx, rsi
0x18004f45e  jz      short loc_18004F488
0x18004f460  xorps   xmm0, xmm0
0x18004f463  movups  [rsp+480h+var_428], xmm0
0x18004f468  test    byte ptr [rbx+0A4h], 80h
0x18004f46f  jz      short loc_18004F480
0x18004f471  mov     rcx, rbx; struct _KERB_TICKET_CACHE_ENTRY *
0x18004f474  mov     r14d, r12d
0x18004f477  mov     rbx, [rbx+8]
0x18004f47b  call    ?KerbRemoveTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbRemoveTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x18004f480  mov     rbx, [rbx]
0x18004f483  cmp     rbx, rsi
0x18004f486  jnz     short loc_18004F460
0x18004f488  mov     rbx, [r15]
0x18004f48b  cmp     rbx, r15
0x18004f48e  jz      short loc_18004F4B8
0x18004f490  xorps   xmm0, xmm0
0x18004f493  movups  [rsp+480h+var_428], xmm0
0x18004f498  test    byte ptr [rbx+0A4h], 80h
0x18004f49f  jz      short loc_18004F4B0
0x18004f4a1  mov     rcx, rbx; struct _KERB_TICKET_CACHE_ENTRY *
0x18004f4a4  mov     r14d, r12d
0x18004f4a7  mov     rbx, [rbx+8]
0x18004f4ab  call    ?KerbRemoveTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbRemoveTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x18004f4b0  mov     rbx, [rbx]
0x18004f4b3  cmp     rbx, r15
0x18004f4b6  jnz     short loc_18004F490
0x18004f4b8  lea     rcx, ?KerberosTicketCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18004f4bf  call    cs:__imp_RtlReleaseResource
0x18004f4c5  nop
0x18004f4c6  mov     rdi, [rsp+480h+var_440]
0x18004f4cb  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18004f4cf  jz      short loc_18004F522
0x18004f4d1  mov     rbx, [rsp+480h+var_438]
0x18004f4d6  mov     [rsp+480h+var_438], rdi
0x18004f4db  sub     rbx, rdi
0x18004f4de  sar     rbx, 4
0x18004f4e2  test    rbx, rbx
0x18004f4e5  jz      short loc_18004F513
0x18004f4e7  nop     word ptr [rax+rax+00000000h]
0x18004f4f0  dec     rbx
0x18004f4f3  mov     rax, rbx
0x18004f4f6  add     rax, rax
0x18004f4f9  mov     rcx, [rdi+rax*8+8]; this
0x18004f4fe  test    rcx, rcx
0x18004f501  jz      short loc_18004F509
0x18004f503  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18004f508  nop
0x18004f509  test    rbx, rbx
0x18004f50c  jnz     short loc_18004F4F0
0x18004f50e  mov     rdi, [rsp+480h+var_440]
0x18004f513  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004f51a  mov     rcx, rdi; void *
0x18004f51d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004f522  mov     rdi, [rsp+480h+var_450]
0x18004f527  test    r14d, r14d
0x18004f52a  js      short loc_18004F558
0x18004f52c  mov     eax, [rdi+40h]
0x18004f52f  mov     [rsp+480h+var_458], eax
0x18004f533  mov     eax, [rdi+44h]
0x18004f536  mov     [rsp+480h+var_460], eax
0x18004f53a  lea     r9, aPurgedCompound; "Purged compound ticket from %#x:%x prim"...
0x18004f541  mov     r8d, 54Fh
0x18004f547  lea     rdx, aKerbpurgecompo; "KerbPurgeCompoundedTickets"
0x18004f54e  mov     ecx, 3
0x18004f553  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18004f558  lea     rcx, [rdi+18h]; CriticalSection
0x18004f55c  call    cs:__imp_RtlEnterCriticalSection
0x18004f562  lea     r13, [rdi+8]
0x18004f566  mov     r12, [r13+0]
0x18004f56a  cmp     r12, r13
0x18004f56d  jz      loc_18004F705
0x18004f573  nop     dword ptr [rax+00h]
0x18004f577  nop     word ptr [rax+rax+00000000h]
0x18004f580  mov     rbx, [r12+40h]
0x18004f585  test    rbx, rbx
0x18004f588  jz      loc_18004F6F8
0x18004f58e  mov     rdx, rbx
0x18004f591  lea     rcx, [rsp+480h+var_440]
0x18004f596  call    ??0kerb_credential_lock_guard@@QEAA@AEAU_KERB_PRIMARY_CREDENTIAL@@W4KerbLockType@@@Z; kerb_credential_lock_guard::kerb_credential_lock_guard(_KERB_PRIMARY_CREDENTIAL &,KerbLockType)
0x18004f59b  nop
0x18004f59c  lea     rdi, [rbx+0F0h]
0x18004f5a3  lea     rsi, [rbx+0A0h]
0x18004f5aa  lea     r15, [rbx+0C8h]
0x18004f5b1  mov     r14d, 0C0000034h
0x18004f5b7  mov     dl, 1; Wait
0x18004f5b9  lea     rcx, ?KerberosTicketCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18004f5c0  call    cs:__imp_RtlAcquireResourceExclusive
0x18004f5c6  lfence
0x18004f5c9  mov     rbx, [rdi]
0x18004f5cc  cmp     rbx, rdi
0x18004f5cf  jz      short loc_18004F5F9
0x18004f5d1  xorps   xmm0, xmm0
0x18004f5d4  movups  [rsp+480h+var_428], xmm0
0x18004f5d9  test    byte ptr [rbx+0A4h], 80h
0x18004f5e0  jz      short loc_18004F5F1
0x18004f5e2  mov     rcx, rbx; struct _KERB_TICKET_CACHE_ENTRY *
0x18004f5e5  xor     r14d, r14d
0x18004f5e8  mov     rbx, [rbx+8]
0x18004f5ec  call    ?KerbRemoveTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbRemoveTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x18004f5f1  mov     rbx, [rbx]
0x18004f5f4  cmp     rbx, rdi
0x18004f5f7  jnz     short loc_18004F5D1
0x18004f5f9  mov     rbx, [rsi]
0x18004f5fc  cmp     rbx, rsi
0x18004f5ff  jz      short loc_18004F629
0x18004f601  xorps   xmm0, xmm0
0x18004f604  movups  [rsp+480h+var_428], xmm0
0x18004f609  test    byte ptr [rbx+0A4h], 80h
0x18004f610  jz      short loc_18004F621
0x18004f612  mov     rcx, rbx; struct _KERB_TICKET_CACHE_ENTRY *
0x18004f615  xor     r14d, r14d
0x18004f618  mov     rbx, [rbx+8]
0x18004f61c  call    ?KerbRemoveTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbRemoveTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x18004f621  mov     rbx, [rbx]
0x18004f624  cmp     rbx, rsi
0x18004f627  jnz     short loc_18004F601
0x18004f629  mov     rbx, [r15]
0x18004f62c  cmp     rbx, r15
0x18004f62f  jz      short loc_18004F659
0x18004f631  xorps   xmm0, xmm0
0x18004f634  movups  [rsp+480h+var_428], xmm0
0x18004f639  test    byte ptr [rbx+0A4h], 80h
0x18004f640  jz      short loc_18004F651
0x18004f642  mov     rcx, rbx; struct _KERB_TICKET_CACHE_ENTRY *
0x18004f645  xor     r14d, r14d
0x18004f648  mov     rbx, [rbx+8]
0x18004f64c  call    ?KerbRemoveTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbRemoveTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x18004f651  mov     rbx, [rbx]
0x18004f654  cmp     rbx, r15
0x18004f657  jnz     short loc_18004F631
0x18004f659  lea     rcx, ?KerberosTicketCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18004f660  call    cs:__imp_RtlReleaseResource
0x18004f666  nop
0x18004f667  mov     rdi, [rsp+480h+var_440]
0x18004f66c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18004f670  jz      short loc_18004F6C2
0x18004f672  mov     rbx, [rsp+480h+var_438]
0x18004f677  mov     [rsp+480h+var_438], rdi
0x18004f67c  sub     rbx, rdi
0x18004f67f  sar     rbx, 4
0x18004f683  test    rbx, rbx
0x18004f686  jz      short loc_18004F6B3
0x18004f688  nop     dword ptr [rax+rax+00000000h]
0x18004f690  dec     rbx
0x18004f693  mov     rax, rbx
0x18004f696  add     rax, rax
0x18004f699  mov     rcx, [rdi+rax*8+8]; this
0x18004f69e  test    rcx, rcx
0x18004f6a1  jz      short loc_18004F6A9
0x18004f6a3  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18004f6a8  nop
0x18004f6a9  test    rbx, rbx
0x18004f6ac  jnz     short loc_18004F690
0x18004f6ae  mov     rdi, [rsp+480h+var_440]
0x18004f6b3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004f6ba  mov     rcx, rdi; void *
0x18004f6bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004f6c2  mov     rdi, [rsp+480h+var_450]
0x18004f6c7  test    r14d, r14d
0x18004f6ca  js      short loc_18004F6F8
0x18004f6cc  mov     eax, [rdi+40h]
  ... truncated ...
```
