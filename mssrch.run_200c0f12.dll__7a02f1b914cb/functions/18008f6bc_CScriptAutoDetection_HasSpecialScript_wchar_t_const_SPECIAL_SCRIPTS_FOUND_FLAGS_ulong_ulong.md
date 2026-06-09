# CScriptAutoDetection::HasSpecialScript(wchar_t const *,SPECIAL_SCRIPTS_FOUND_FLAGS *,ulong *,ulong *)

- ea: `0x18008f6bc`
- end: `0x18008f925`
- name: `?HasSpecialScript@CScriptAutoDetection@@QEAAJPEB_WPEAW4SPECIAL_SCRIPTS_FOUND_FLAGS@@PEAK2@Z`
- size: `617`
- prototype: `__int64 __usercall@<rax>(PMAPPING_SERVICE_INFO *prgServices@<rcx>, LPCWSTR pszText@<rdx>, enum SPECIAL_SCRIPTS_FOUND_FLAGS *@<r8>, unsigned int *@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008f3b8`

## callees

- `0x18008f6bc`
- `0x18012540e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008f8b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008f8b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008f898`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008f898`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008f820`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008f820`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x18008f754`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x18008f754`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x18008f7e5`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x18008f7e5`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18008f8ea`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18008f8ea`

## pseudocode

```c
__int64 __fastcall CScriptAutoDetection::HasSpecialScript(
        PMAPPING_SERVICE_INFO *prgServices,
        LPCWSTR pszText,
        enum SPECIAL_SCRIPTS_FOUND_FLAGS *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  unsigned int *v5; // r13
  __int64 v9; // r8
  HRESULT Services; // ebx
  int v12; // edi
  unsigned int v13; // esi
  unsigned int v14; // r13d
  __int64 v15; // r10
  _WORD *v16; // rcx
  unsigned int i; // r15d
  int v18; // eax
  unsigned int v19; // eax
  __int128 v20; // [rsp+30h] [rbp-41h] BYREF
  struct _MAPPING_ENUM_OPTIONS pBag; // [rsp+40h] [rbp-31h] BYREF
  HRESULT v22; // [rsp+D0h] [rbp+5Fh]

  v5 = a4;
  *(_DWORD *)a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  v20 = xmmword_180267068;
  if ( *((_BYTE *)prgServices + 12) )
    goto LABEL_44;
  Services = 0;
  AcquireSRWLockExclusive(&s_srwElsServiceLock);
  if ( !*((_BYTE *)prgServices + 12) )
  {
    memset_0(&pBag, 0, sizeof(pBag));
    pBag.Size = 80;
    pBag.pGuid = (GUID *)&v20;
    Services = MappingGetServices(&pBag, prgServices, (DWORD *)prgServices + 2);
    if ( Services >= 0 )
    {
      if ( *((_DWORD *)prgServices + 2) )
        *((_BYTE *)prgServices + 12) = 1;
      else
        Services = -2147467259;
    }
  }
  ReleaseSRWLockExclusive(&s_srwElsServiceLock);
  if ( Services >= 0 )
  {
LABEL_44:
    memset_0(&pBag, 0, 0x40u);
    v9 = -1;
    pBag.Size = 64;
    do
      ++v9;
    while ( pszText[v9] );
    v22 = MappingRecognizeText(*prgServices, pszText, v9, 0, 0, (PMAPPING_PROPERTY_BAG)&pBag);
    Services = v22;
    if ( v22 >= 0 )
    {
      v12 = 0;
      v13 = 0;
      if ( LODWORD(pBag.pszInputLanguage) )
      {
        v14 = 0;
        do
        {
          v15 = 9LL * v14;
          v16 = *(_WORD **)&pBag.pszCategory[36 * v14 + 12];
          if ( v16 && *v16 )
          {
            for ( i = 0; i < 0x22; ++i )
            {
              if ( CompareStringOrdinal(
                     *(LPCWCH *)&pBag.pszCategory[4 * v15 + 12],
                     -1,
                     (&off_180245300)[3 * (int)i],
                     -1,
                     1) == 2 )
              {
                v18 = *((_DWORD *)&off_180245300 + 6 * (int)i + 2);
                if ( (v18 & *(_DWORD *)a3) == 0 )
                {
                  ++v12;
                  *(_DWORD *)a3 |= v18;
                  v19 = (unsigned int)(&off_180245300)[3 * (int)i + 1];
                  if ( v19 )
                  {
                    v13 = (unsigned int)(&off_180245300)[3 * (int)i + 1];
                    if ( *((_BYTE *)&off_180245300 + 24 * (int)i + 12) )
                    {
                      if ( a5 && !*a5 )
                        *a5 = v19;
                    }
                  }
                }
                goto LABEL_14;
              }
              v15 = 9LL * v14;
            }
            if ( (*(_DWORD *)a3 & 0x2000000) == 0 )
            {
              *(_DWORD *)a3 |= 0x2000000u;
              ++v12;
            }
          }
LABEL_14:
          ++v14;
        }
        while ( v14 < LODWORD(pBag.pszInputLanguage) );
        Services = v22;
        v5 = a4;
      }
      if ( v5 && v12 == 1 )
        *v5 = v13;
      if ( !*(_DWORD *)a3 )
        Services = 1;
      MappingFreePropertyBag((PMAPPING_PROPERTY_BAG)&pBag);
    }
  }
  return (unsigned int)Services;
}

```

## disassembly

```asm
0x18008f6bc  mov     [rsp-8+arg_8], rbx
0x18008f6c1  mov     [rsp-8+arg_18], r9
0x18008f6c6  push    rbp
0x18008f6c7  push    rsi
0x18008f6c8  push    rdi
0x18008f6c9  push    r12
0x18008f6cb  push    r13
0x18008f6cd  push    r14
0x18008f6cf  push    r15
0x18008f6d1  lea     rbp, [rsp-1Fh]
0x18008f6d6  sub     rsp, 90h
0x18008f6dd  xor     esi, esi
0x18008f6df  mov     r13, r9
0x18008f6e2  mov     [r8], esi
0x18008f6e5  mov     r12, r8
0x18008f6e8  mov     r15, rdx
0x18008f6eb  mov     rdi, rcx
0x18008f6ee  test    r9, r9
0x18008f6f1  jz      short loc_18008F6F6
0x18008f6f3  mov     [r9], esi
0x18008f6f6  mov     r14, [rbp+4Fh+arg_20]
0x18008f6fa  test    r14, r14
0x18008f6fd  jz      short loc_18008F702
0x18008f6ff  mov     [r14], esi
0x18008f702  movups  xmm0, cs:xmmword_180267068
0x18008f709  movdqu  [rbp+4Fh+var_90], xmm0
0x18008f70e  cmp     [rcx+0Ch], sil
0x18008f712  jz      loc_18008F8AB
0x18008f718  mov     ebx, 40h ; '@'
0x18008f71d  lea     rcx, [rbp+4Fh+pBag]; void *
0x18008f721  mov     r8d, ebx; Size
0x18008f724  xor     edx, edx; Val
0x18008f726  call    memset_0
0x18008f72b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008f72f  mov     [rbp+4Fh+pBag.Size], rbx
0x18008f733  inc     r8; dwLength
0x18008f736  cmp     [r15+r8*2], si
0x18008f73b  jnz     short loc_18008F733
0x18008f73d  mov     rcx, [rdi]; pServiceInfo
0x18008f740  lea     rax, [rbp+4Fh+pBag]
0x18008f744  mov     [rsp+0C0h+pbag], rax; pbag
0x18008f749  xor     r9d, r9d; dwIndex
0x18008f74c  mov     rdx, r15; pszText
0x18008f74f  mov     [rsp+0C0h+pOptions], rsi; pOptions
0x18008f754  call    cs:__imp_MappingRecognizeText
0x18008f75a  xor     edx, edx
0x18008f75c  mov     [rbp+4Fh+arg_0], eax
0x18008f75f  mov     ebx, eax
0x18008f761  test    eax, eax
0x18008f763  jns     short loc_18008F782
0x18008f765  mov     eax, ebx
0x18008f767  mov     rbx, [rsp+0C0h+arg_8]
0x18008f76f  add     rsp, 90h
0x18008f776  pop     r15
0x18008f778  pop     r14
0x18008f77a  pop     r13
0x18008f77c  pop     r12
0x18008f77e  pop     rdi
0x18008f77f  pop     rsi
0x18008f780  pop     rbp
0x18008f781  retn
0x18008f782  mov     edi, edx
0x18008f784  mov     esi, edx
0x18008f786  cmp     [rbp+4Fh+pBag.dwRangesCount], edx
0x18008f789  jbe     short loc_18008F7C8
0x18008f78b  lea     r8, off_180245300; "Hira"
0x18008f792  mov     r13d, edx
0x18008f795  mov     ebx, 1
0x18008f79a  mov     eax, r13d
0x18008f79d  lea     r10, [rax+rax*8]
0x18008f7a1  mov     rax, [rbp+4Fh+pBag.prgResultRanges]
0x18008f7a5  mov     [rbp+4Fh+arg_20], r10
0x18008f7a9  mov     rcx, [rax+r10*8+18h]
0x18008f7ae  test    rcx, rcx
0x18008f7b1  jz      short loc_18008F7B8
0x18008f7b3  cmp     [rcx], dx
0x18008f7b6  jnz     short loc_18008F7F0
0x18008f7b8  add     r13d, ebx
0x18008f7bb  cmp     r13d, [rbp+4Fh+pBag.dwRangesCount]
0x18008f7bf  jb      short loc_18008F79A
0x18008f7c1  mov     ebx, [rbp+4Fh+arg_0]
0x18008f7c4  mov     r13, [rbp+4Fh+arg_18]
0x18008f7c8  mov     eax, 1
0x18008f7cd  test    r13, r13
0x18008f7d0  jz      short loc_18008F7DA
0x18008f7d2  cmp     edi, eax
0x18008f7d4  jnz     short loc_18008F7DA
0x18008f7d6  mov     [r13+0], esi
0x18008f7da  cmp     [r12], edx
0x18008f7de  lea     rcx, [rbp+4Fh+pBag]; pBag
0x18008f7e2  cmovz   ebx, eax
0x18008f7e5  call    cs:__imp_MappingFreePropertyBag
0x18008f7eb  jmp     loc_18008F765
0x18008f7f0  mov     r15d, edx
0x18008f7f3  cmp     r15d, 22h ; '"'
0x18008f7f7  jnb     loc_18008F908
0x18008f7fd  mov     rcx, [rbp+4Fh+pBag.prgResultRanges]
0x18008f801  or      r9d, 0FFFFFFFFh; cchCount2
0x18008f805  movsxd  rax, r15d
0x18008f808  or      edx, r9d; cchCount1
0x18008f80b  mov     dword ptr [rsp+0C0h+pOptions], ebx; bIgnoreCase
0x18008f80f  mov     rcx, [rcx+r10*8+18h]; lpString1
0x18008f814  lea     rax, [rax+rax*2]
0x18008f818  mov     r8, [r8+rax*8]; lpString2
0x18008f81c  mov     [rbp+4Fh+arg_10], rax
0x18008f820  call    cs:__imp_CompareStringOrdinal
0x18008f826  lea     r8, off_180245300; "Hira"
0x18008f82d  cmp     eax, 2
0x18008f830  jz      short loc_18008F83B
0x18008f832  mov     r10, [rbp+4Fh+arg_20]
0x18008f836  add     r15d, ebx
0x18008f839  jmp     short loc_18008F7F3
0x18008f83b  mov     rcx, [rbp+4Fh+arg_10]
0x18008f83f  mov     edx, [r12]
0x18008f843  mov     eax, [r8+rcx*8+8]
0x18008f848  test    edx, eax
0x18008f84a  jz      short loc_18008F853
0x18008f84c  xor     edx, edx
0x18008f84e  jmp     loc_18008F7B8
0x18008f853  or      eax, edx
0x18008f855  add     edi, ebx
0x18008f857  mov     [r12], eax
0x18008f85b  xor     edx, edx
0x18008f85d  mov     eax, [r8+rcx*8+10h]
0x18008f862  test    eax, eax
0x18008f864  jz      loc_18008F7B8
0x18008f86a  mov     esi, eax
0x18008f86c  cmp     [r8+rcx*8+0Ch], dl
0x18008f871  jz      loc_18008F7B8
0x18008f877  test    r14, r14
0x18008f87a  jz      loc_18008F7B8
0x18008f880  cmp     [r14], edx
0x18008f883  jnz     loc_18008F7B8
0x18008f889  mov     [r14], eax
0x18008f88c  jmp     loc_18008F7B8
0x18008f891  lea     rcx, ?s_srwElsServiceLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18008f898  call    cs:__imp_ReleaseSRWLockExclusive
0x18008f89e  test    ebx, ebx
0x18008f8a0  js      loc_18008F765
0x18008f8a6  jmp     loc_18008F718
0x18008f8ab  lea     rcx, ?s_srwElsServiceLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18008f8b2  mov     ebx, esi
0x18008f8b4  call    cs:__imp_AcquireSRWLockExclusive
0x18008f8ba  cmp     [rdi+0Ch], sil
0x18008f8be  jnz     short loc_18008F891
0x18008f8c0  mov     ebx, 50h ; 'P'
0x18008f8c5  lea     rcx, [rbp+4Fh+pBag]; void *
0x18008f8c9  mov     r8d, ebx; Size
0x18008f8cc  xor     edx, edx; Val
0x18008f8ce  call    memset_0
0x18008f8d3  lea     rax, [rbp+4Fh+var_90]
0x18008f8d7  mov     [rbp+4Fh+pBag.Size], rbx
0x18008f8db  lea     r8, [rdi+8]; pdwServicesCount
0x18008f8df  mov     [rbp+4Fh+var_40], rax
0x18008f8e3  mov     rdx, rdi; prgServices
0x18008f8e6  lea     rcx, [rbp+4Fh+pBag]; pOptions
0x18008f8ea  call    cs:__imp_MappingGetServices
0x18008f8f0  mov     ebx, eax
0x18008f8f2  test    eax, eax
0x18008f8f4  js      short loc_18008F891
0x18008f8f6  cmp     [rdi+8], esi
0x18008f8f9  jbe     short loc_18008F901
0x18008f8fb  mov     byte ptr [rdi+0Ch], 1
0x18008f8ff  jmp     short loc_18008F891
0x18008f901  mov     ebx, 80004005h
0x18008f906  jmp     short loc_18008F891
0x18008f908  mov     eax, [r12]
0x18008f90c  bt      eax, 19h
0x18008f910  jb      loc_18008F84C
0x18008f916  bts     eax, 19h
0x18008f91a  mov     [r12], eax
0x18008f91e  inc     edi
0x18008f920  jmp     loc_18008F84C
```
