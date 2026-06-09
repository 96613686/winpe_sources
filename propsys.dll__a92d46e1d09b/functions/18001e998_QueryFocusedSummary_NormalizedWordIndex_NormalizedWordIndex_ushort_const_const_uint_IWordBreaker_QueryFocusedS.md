# QueryFocusedSummary::NormalizedWordIndex::NormalizedWordIndex(ushort const * const,uint,IWordBreaker *,QueryFocusedSummary::INormalizer *,uint,ulong)

- ea: `0x18001e998`
- end: `0x18001ed09`
- name: `??0NormalizedWordIndex@QueryFocusedSummary@@IEAA@QEBGIPEAUIWordBreaker@@PEAVINormalizer@1@IK@Z`
- size: `881`
- prototype: `QueryFocusedSummary::NormalizedWordIndex *__fastcall(QueryFocusedSummary::NormalizedWordIndex *this, const unsigned __int16 *, unsigned int, struct IWordBreaker *, struct QueryFocusedSummary::INormalizer *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18006be60`

## callees

- `0x18001bfbc`
- `0x18001d8f0`
- `0x18001e998`
- `0x18001ed10`
- `0x18001ed44`
- `0x180020274`
- `0x18002029c`
- `0x18002ecc0`
- `0x18006b87c`
- `0x18006fb98`
- `0x1800a5cf4`
- `0x1800a5dbc`
- `0x1800a6d4c`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswpunct` at `0x18001ebe8`
- `api-ms-win-crt-private-l1-1-0!_o_iswpunct` at `0x18001ebe8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001ebf8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001ebf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eb89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ecc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eb89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ecc3`

## pseudocode

```c
QueryFocusedSummary::NormalizedWordIndex *__fastcall QueryFocusedSummary::NormalizedWordIndex::NormalizedWordIndex(
        QueryFocusedSummary::NormalizedWordIndex *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct IWordBreaker *a4,
        struct QueryFocusedSummary::INormalizer *a5,
        unsigned int a6,
        unsigned int a7)
{
  struct QueryFocusedSummary::INormalizer *v8; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // r14
  QueryFocusedSummary::TokenInstance *v14; // rbx
  __int64 v15; // rsi
  void *v16; // rax
  bool v17; // zf
  QueryFocusedSummary::WordBreakerTokenizer *v18; // rax
  QueryFocusedSummary::RefCount *v19; // rax
  QueryFocusedSummary::RefCount *v20; // rsi
  __int64 v21; // rax
  __int64 (__fastcall *v22)(QueryFocusedSummary::RefCount *, struct QueryFocusedSummary::INormalizer **, unsigned int *, LPVOID *); // rax
  const unsigned __int16 *i; // rbx
  __int64 v24; // r14
  unsigned int v25; // r8d
  const unsigned __int16 *v26; // rdx
  unsigned int WordID; // eax
  const unsigned __int16 *v28; // r8
  __int64 v29; // rcx
  int v30; // edx
  int v32; // eax
  __int64 v33; // rax
  int HasScript; // ebx
  const unsigned __int16 *v35; // r8
  unsigned __int16 *v36; // [rsp+30h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+48h] BYREF

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &QueryFocusedSummary::NormalizedWordIndex::`vftable';
  v8 = a5;
  *((_DWORD *)this + 10) = 6;
  *((_QWORD *)this + 6) = v8;
  ++*((_DWORD *)v8 + 2);
  memset_0((char *)this + 56, 0, 0x7D08u);
  *((_DWORD *)this + 8020) = a7;
  *((_DWORD *)this + 8022) = 0;
  *((_DWORD *)this + 8021) = ~(unsigned __int8)GetSystemNormalization() & 2 | 0x8030001;
  v12 = operator new(0x58008u);
  if ( v12 )
  {
    v13 = v12 + 1;
    *v12 = 4096;
    v14 = (QueryFocusedSummary::TokenInstance *)(v12 + 1);
    v15 = 4096;
    do
    {
      QueryFocusedSummary::TokenInstance::TokenInstance(v14);
      v14 = (QueryFocusedSummary::TokenInstance *)((char *)v14 + 88);
      --v15;
    }
    while ( v15 );
  }
  else
  {
    v13 = 0;
  }
  *((_QWORD *)this + 2) = v13;
  v16 = operator new(0x10000u);
  v17 = *((_QWORD *)this + 2) == 0;
  *((_QWORD *)this + 3) = v16;
  if ( !v17 )
  {
    if ( v16 )
    {
      *((_QWORD *)this + 4009) = a2;
      v18 = (QueryFocusedSummary::WordBreakerTokenizer *)operator new(0x6048u);
      if ( v18 )
      {
        v19 = (QueryFocusedSummary::RefCount *)QueryFocusedSummary::WordBreakerTokenizer::WordBreakerTokenizer(
                                                 v18,
                                                 a4,
                                                 a2,
                                                 a3);
        v20 = v19;
        if ( v19 )
        {
          v21 = *(_QWORD *)v19;
          LODWORD(a5) = 0;
          a6 = 0;
          v22 = *(__int64 (__fastcall **)(QueryFocusedSummary::RefCount *, struct QueryFocusedSummary::INormalizer **, unsigned int *, LPVOID *))(v21 + 8);
          pv = 0;
          LOBYTE(a7) = 0;
          for ( i = (const unsigned __int16 *)v22(v20, &a5, &a6, &pv);
                i;
                i = (const unsigned __int16 *)(*(__int64 (__fastcall **)(QueryFocusedSummary::RefCount *, struct QueryFocusedSummary::INormalizer **, unsigned int *, LPVOID *))(*(_QWORD *)v20 + 16LL))(
                                                v20,
                                                &a5,
                                                &a6,
                                                &pv) )
          {
            if ( *((_DWORD *)this + 8) >= 0x1000u )
              break;
            if ( a6 != 1 || !(unsigned int)_o_iswpunct(*i) )
            {
              v24 = *((_QWORD *)this + 2) + 88LL * *((unsigned int *)this + 8);
              *(_DWORD *)(v24 + 4) = (_DWORD)a5;
              *(_DWORD *)(v24 + 8) = a6;
              if ( pv )
              {
                v32 = lstrlenW((LPCWSTR)pv);
                v26 = (const unsigned __int16 *)pv;
                v25 = v32;
              }
              else
              {
                v25 = a6;
                v26 = i;
              }
              WordID = QueryFocusedSummary::NormalizedWordIndex::getWordID(this, v26, v25);
              *(_DWORD *)(v24 + 12) = WordID;
              *(_DWORD *)v24 = *((_DWORD *)this + 8);
              *(_BYTE *)(v24 + 72) = a7;
              v29 = *((_QWORD *)this + 3);
              *(_QWORD *)(v24 + 80) = *(_QWORD *)(v29 + 16LL * WordID);
              *(_QWORD *)(v29 + 16LL * WordID) = v24;
              v30 = (int)pv;
              if ( pv && !*(_QWORD *)(*((_QWORD *)this + 3) + 16LL * *(unsigned int *)(v24 + 12) + 8) )
              {
                if ( *((_DWORD *)this + 8020) == 1042
                  && !CScriptAutoDetection::HasScript(
                        (CScriptAutoDetection *)g_scriptAutoDetection,
                        (const unsigned __int16 *)pv,
                        v28) )
                {
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v24 + 48);
                  *(_QWORD *)(v24 + 56) = -1;
                  *(_QWORD *)(v24 + 64) = -1;
                  CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                    (CKoreanDecomposition *)g_koreanDecomposition,
                    (const unsigned __int16 *)pv,
                    (unsigned __int16 **)(v24 + 48));
                }
                v30 = 2 * *(_DWORD *)(v24 + 12);
                *(_QWORD *)(*((_QWORD *)this + 3) + 16LL * *(unsigned int *)(v24 + 12) + 8) = pv;
                pv = 0;
              }
              if ( *((_DWORD *)this + 8020) == 1042 )
              {
                v33 = *((_QWORD *)this + 4009);
                v36 = 0;
                HasScript = _AllocStringWorker<CTCoAllocPolicy>(
                              (_DWORD)a5,
                              v30,
                              (int)v33 + 2 * (int)a5,
                              a6,
                              (unsigned int)&a7,
                              (__int64)&v36);
                if ( HasScript >= 0 )
                {
                  HasScript = CScriptAutoDetection::HasScript((CScriptAutoDetection *)g_scriptAutoDetection, v36, v35);
                  CoTaskMemFree(v36);
                }
                if ( !HasScript )
                {
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v24 + 24);
                  *(_QWORD *)(v24 + 32) = -1;
                  *(_QWORD *)(v24 + 40) = -1;
                  CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                    (CKoreanDecomposition *)g_koreanDecomposition,
                    (const unsigned __int16 *)(*((_QWORD *)this + 4009) + 2LL * (unsigned int)a5),
                    a6,
                    (unsigned __int16 **)(v24 + 24));
                }
              }
              ++*((_DWORD *)this + 8);
            }
            CoTaskMemFree(pv);
          }
          *((_DWORD *)this + 8022) = 1;
          QueryFocusedSummary::RefCount::Release(v20);
        }
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x18001e998  push    rbp
0x18001e99a  push    rbx
0x18001e99b  push    rsi
0x18001e99c  push    rdi
0x18001e99d  push    r12
0x18001e99f  push    r13
0x18001e9a1  push    r14
0x18001e9a3  push    r15
0x18001e9a5  mov     rbp, rsp
0x18001e9a8  sub     rsp, 48h
0x18001e9ac  mov     dword ptr [rcx+8], 1
0x18001e9b3  lea     rax, ??_7NormalizedWordIndex@QueryFocusedSummary@@6B@; const QueryFocusedSummary::NormalizedWordIndex::`vftable'
0x18001e9ba  mov     [rcx], rax
0x18001e9bd  mov     r13d, r8d
0x18001e9c0  mov     rax, [rbp+arg_20]
0x18001e9c4  mov     r15, rdx
0x18001e9c7  mov     dword ptr [rcx+28h], 6
0x18001e9ce  mov     rdi, rcx
0x18001e9d1  mov     [rcx+30h], rax
0x18001e9d5  xor     edx, edx; Val
0x18001e9d7  add     rcx, 38h ; '8'; void *
0x18001e9db  mov     r8d, 7D08h; Size
0x18001e9e1  inc     dword ptr [rax+8]
0x18001e9e4  mov     r12, r9
0x18001e9e7  call    memset_0
0x18001e9ec  mov     eax, [rbp+arg_30]
0x18001e9ef  mov     [rdi+7D50h], eax
0x18001e9f5  mov     dword ptr [rdi+7D58h], 0
0x18001e9ff  call    ?GetSystemNormalization@@YAKXZ; GetSystemNormalization(void)
0x18001ea04  not     eax
0x18001ea06  mov     ecx, 58008h; unsigned __int64
0x18001ea0b  and     eax, 2
0x18001ea0e  or      eax, 8030001h
0x18001ea13  mov     [rdi+7D54h], eax
0x18001ea19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ea1e  mov     ecx, 1000h
0x18001ea23  test    rax, rax
0x18001ea26  jz      loc_18001EC7B
0x18001ea2c  lea     r14, [rax+8]
0x18001ea30  mov     [rax], rcx
0x18001ea33  mov     rbx, r14
0x18001ea36  mov     esi, ecx
0x18001ea38  mov     rcx, rbx; this
0x18001ea3b  call    ??0TokenInstance@QueryFocusedSummary@@QEAA@XZ; QueryFocusedSummary::TokenInstance::TokenInstance(void)
0x18001ea40  add     rbx, 58h ; 'X'
0x18001ea44  sub     rsi, 1
0x18001ea48  jnz     short loc_18001EA38
0x18001ea4a  mov     ecx, 10000h; unsigned __int64
0x18001ea4f  mov     [rdi+10h], r14
0x18001ea53  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ea58  cmp     qword ptr [rdi+10h], 0
0x18001ea5d  mov     [rdi+18h], rax
0x18001ea61  jz      loc_18001EBD1
0x18001ea67  test    rax, rax
0x18001ea6a  jz      loc_18001EBD1
0x18001ea70  mov     ecx, 6048h; unsigned __int64
0x18001ea75  mov     [rdi+7D48h], r15
0x18001ea7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ea81  test    rax, rax
0x18001ea84  jz      loc_18001EBD1
0x18001ea8a  mov     r9d, r13d; unsigned int
0x18001ea8d  mov     r8, r15; unsigned __int16 *
0x18001ea90  mov     rdx, r12; struct IWordBreaker *
0x18001ea93  mov     rcx, rax; this
0x18001ea96  call    ??0WordBreakerTokenizer@QueryFocusedSummary@@QEAA@PEAUIWordBreaker@@QEBGI@Z; QueryFocusedSummary::WordBreakerTokenizer::WordBreakerTokenizer(IWordBreaker *,ushort const * const,uint)
0x18001ea9b  xor     r15d, r15d
0x18001ea9e  mov     rsi, rax
0x18001eaa1  test    rax, rax
0x18001eaa4  jz      loc_18001EBD1
0x18001eaaa  mov     rax, [rax]
0x18001eaad  lea     rcx, [rbp+arg_30]
0x18001eab1  mov     [rsp+48h+var_28], rcx
0x18001eab6  lea     r9, [rbp+pv]
0x18001eaba  lea     r8, [rbp+arg_28]
0x18001eabe  mov     dword ptr [rbp+arg_20], r15d
0x18001eac2  lea     rdx, [rbp+arg_20]
0x18001eac6  mov     [rbp+arg_28], r15d
0x18001eaca  mov     rax, [rax+8]
0x18001eace  mov     rcx, rsi
0x18001ead1  mov     [rbp+pv], r15
0x18001ead5  mov     byte ptr [rbp+arg_30], r15b
0x18001ead9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eade  mov     rbx, rax
0x18001eae1  test    rax, rax
0x18001eae4  jz      loc_18001EBBF
0x18001eaea  mov     r13d, 412h
0x18001eaf0  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001eaf4  cmp     dword ptr [rdi+20h], 1000h
0x18001eafb  jnb     loc_18001EBBF
0x18001eb01  cmp     [rbp+arg_28], 1
0x18001eb05  jz      loc_18001EBE5
0x18001eb0b  mov     eax, [rdi+20h]
0x18001eb0e  imul    r14, rax, 58h ; 'X'
0x18001eb12  mov     eax, dword ptr [rbp+arg_20]
0x18001eb15  add     r14, [rdi+10h]
0x18001eb19  mov     [r14+4], eax
0x18001eb1d  mov     eax, [rbp+arg_28]
0x18001eb20  mov     [r14+8], eax
0x18001eb24  mov     rcx, [rbp+pv]; lpString
0x18001eb28  test    rcx, rcx
0x18001eb2b  jnz     loc_18001EBF8
0x18001eb31  mov     r8d, [rbp+arg_28]; unsigned int
0x18001eb35  mov     rdx, rbx; unsigned __int16 *
0x18001eb38  mov     rcx, rdi; this
0x18001eb3b  call    ?getWordID@NormalizedWordIndex@QueryFocusedSummary@@IEAAIQEBGI@Z; QueryFocusedSummary::NormalizedWordIndex::getWordID(ushort const * const,uint)
0x18001eb40  mov     [r14+0Ch], eax
0x18001eb44  mov     ecx, eax
0x18001eb46  mov     eax, [rdi+20h]
0x18001eb49  mov     [r14], eax
0x18001eb4c  mov     al, byte ptr [rbp+arg_30]
0x18001eb4f  mov     [r14+48h], al
0x18001eb53  mov     edx, ecx
0x18001eb55  mov     rcx, [rdi+18h]
0x18001eb59  add     rdx, rdx
0x18001eb5c  mov     rax, [rcx+rdx*8]
0x18001eb60  mov     [r14+50h], rax
0x18001eb64  mov     [rcx+rdx*8], r14
0x18001eb68  mov     rdx, [rbp+pv]; unsigned __int16 *
0x18001eb6c  test    rdx, rdx
0x18001eb6f  jnz     loc_18001EC0A
0x18001eb75  cmp     [rdi+7D50h], r13d
0x18001eb7c  jz      loc_18001EC83
0x18001eb82  inc     dword ptr [rdi+20h]
0x18001eb85  mov     rcx, [rbp+pv]; pv
0x18001eb89  call    cs:__imp_CoTaskMemFree
0x18001eb8f  mov     rax, [rsi]
0x18001eb92  lea     rcx, [rbp+arg_30]
0x18001eb96  mov     [rsp+48h+var_28], rcx
0x18001eb9b  lea     r9, [rbp+pv]
0x18001eb9f  lea     r8, [rbp+arg_28]
0x18001eba3  mov     rcx, rsi
0x18001eba6  lea     rdx, [rbp+arg_20]
0x18001ebaa  mov     rax, [rax+10h]
0x18001ebae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebb3  mov     rbx, rax
0x18001ebb6  test    rax, rax
0x18001ebb9  jnz     loc_18001EAF4
0x18001ebbf  mov     rcx, rsi; this
0x18001ebc2  mov     dword ptr [rdi+7D58h], 1
0x18001ebcc  call    ?Release@RefCount@QueryFocusedSummary@@QEAAXXZ; QueryFocusedSummary::RefCount::Release(void)
0x18001ebd1  mov     rax, rdi
0x18001ebd4  add     rsp, 48h
0x18001ebd8  pop     r15
0x18001ebda  pop     r14
0x18001ebdc  pop     r13
0x18001ebde  pop     r12
0x18001ebe0  pop     rdi
0x18001ebe1  pop     rsi
0x18001ebe2  pop     rbx
0x18001ebe3  pop     rbp
0x18001ebe4  retn
0x18001ebe5  movzx   ecx, word ptr [rbx]
0x18001ebe8  call    cs:__imp__o_iswpunct
0x18001ebee  test    eax, eax
0x18001ebf0  jz      loc_18001EB0B
0x18001ebf6  jmp     short loc_18001EB85
0x18001ebf8  call    cs:__imp_lstrlenW
0x18001ebfe  mov     rdx, [rbp+pv]
0x18001ec02  mov     r8d, eax
0x18001ec05  jmp     loc_18001EB38
0x18001ec0a  mov     ecx, [r14+0Ch]
0x18001ec0e  mov     rax, [rdi+18h]
0x18001ec12  add     rcx, rcx
0x18001ec15  cmp     [rax+rcx*8+8], r15
0x18001ec1a  jnz     loc_18001EB75
0x18001ec20  cmp     [rdi+7D50h], r13d
0x18001ec27  jnz     short loc_18001EC5E
0x18001ec29  lea     rcx, ?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; this
0x18001ec30  call    ?HasScript@CScriptAutoDetection@@QEAAJPEBG0@Z; CScriptAutoDetection::HasScript(ushort const *,ushort const *)
0x18001ec35  test    eax, eax
0x18001ec37  jnz     short loc_18001EC5E
0x18001ec39  lea     rcx, [r14+30h]
0x18001ec3d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001ec42  mov     [r14+38h], r12
0x18001ec46  lea     r8, [r14+30h]; unsigned __int16 **
0x18001ec4a  mov     [r14+40h], r12
0x18001ec4e  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x18001ec55  mov     rdx, [rbp+pv]; unsigned __int16 *
0x18001ec59  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x18001ec5e  mov     edx, [r14+0Ch]
0x18001ec62  mov     rax, [rbp+pv]
0x18001ec66  add     rdx, rdx
0x18001ec69  mov     rcx, [rdi+18h]
0x18001ec6d  mov     [rcx+rdx*8+8], rax
0x18001ec72  mov     [rbp+pv], r15
0x18001ec76  jmp     loc_18001EB75
0x18001ec7b  xor     r14d, r14d
0x18001ec7e  jmp     loc_18001EA4A
0x18001ec83  mov     rax, [rdi+7D48h]
0x18001ec8a  mov     ecx, dword ptr [rbp+arg_20]
0x18001ec8d  mov     r9d, [rbp+arg_28]
0x18001ec91  mov     [rbp+var_18], r15
0x18001ec95  lea     r8, [rax+rcx*2]
0x18001ec99  lea     rax, [rbp+var_18]
0x18001ec9d  mov     [rsp+48h+var_20], rax
0x18001eca2  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18001eca7  mov     ebx, eax
0x18001eca9  test    eax, eax
0x18001ecab  js      short loc_18001ECC9
0x18001ecad  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x18001ecb1  lea     rcx, ?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; this
0x18001ecb8  call    ?HasScript@CScriptAutoDetection@@QEAAJPEBG0@Z; CScriptAutoDetection::HasScript(ushort const *,ushort const *)
0x18001ecbd  mov     rcx, [rbp+var_18]; pv
0x18001ecc1  mov     ebx, eax
0x18001ecc3  call    cs:__imp_CoTaskMemFree
0x18001ecc9  test    ebx, ebx
0x18001eccb  jnz     loc_18001EB82
0x18001ecd1  lea     rcx, [r14+18h]
0x18001ecd5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001ecda  mov     [r14+20h], r12
0x18001ecde  lea     r9, [r14+18h]; unsigned __int16 **
0x18001ece2  mov     [r14+28h], r12
0x18001ece6  mov     ecx, dword ptr [rbp+arg_20]
0x18001ece9  mov     rax, [rdi+7D48h]
0x18001ecf0  mov     r8d, [rbp+arg_28]; unsigned int
0x18001ecf4  lea     rdx, [rax+rcx*2]; unsigned __int16 *
0x18001ecf8  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x18001ecff  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGKPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ulong,ushort * *)
0x18001ed04  jmp     loc_18001EB82
```
