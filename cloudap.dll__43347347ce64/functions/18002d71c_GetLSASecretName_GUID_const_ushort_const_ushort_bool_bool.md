# GetLSASecretName(_GUID const *,ushort const *,ushort * *,bool,bool)

- ea: `0x18002d71c`
- end: `0x18002db45`
- name: `?GetLSASecretName@@YAJPEBU_GUID@@PEBGPEAPEAG_N3@Z`
- size: `1065`
- prototype: `__int64 __usercall@<rax>(UUID *Uuid@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int16 **@<r8>, bool@<r9b>, bool)`
- caller_count: `5`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18000e1ec`
- `0x18002d0a4`
- `0x18003243c`
- `0x18005ae90`
- `0x18005b1a4`

## callees

- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x18000b0c0`
- `0x1800156f0`
- `0x18002d71c`
- `0x180042410`
- `0x1800429c0`
- `0x180042a28`
- `0x180081010`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18002dae2`
- `RPCRT4!RpcStringFreeW` at `0x18002dae2`
- `RPCRT4!UuidToStringW` at `0x18002d7d9`
- `RPCRT4!UuidToStringW` at `0x18002d7d9`

## string_xrefs

- `0x18002d7f4`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18002d8cd`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18002d92f`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18002d995`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18002d9d1`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18002da2b`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18002da98`: `onecore\ds\ext\cloudap\dll\tbal.cpp`

## pseudocode

```c
__int64 __fastcall GetLSASecretName(UUID *Uuid, const unsigned __int16 *a2, unsigned __int16 **a3, char a4, bool a5)
{
  const wchar_t *v6; // rsi
  __int64 v8; // rbx
  UCHAR *v9; // r15
  const wchar_t *v12; // rdx
  __int64 v13; // rax
  unsigned __int16 *v14; // r12
  unsigned int v15; // eax
  const char *v16; // rbx
  const char *v17; // r9
  const char *v18; // rcx
  bool v19; // zf
  __int64 v20; // r8
  unsigned int HashStringPreRS2; // edi
  const char *v22; // rax
  bool v23; // zf
  const char *v24; // r9
  __int64 v25; // rax
  unsigned int v26; // ebx
  unsigned __int16 *v27; // rax
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // rbx
  const char *v31; // rax
  bool v32; // zf
  const char *v33; // r9
  __int64 v34; // r8
  __int64 v36; // [rsp+20h] [rbp-108h]
  const char *v37; // [rsp+28h] [rbp-100h]
  RPC_WSTR StringUuid[2]; // [rsp+40h] [rbp-E8h] BYREF
  unsigned __int16 v39[72]; // [rsp+50h] [rbp-D8h] BYREF

  v6 = L"M$_CLOUDAP_TBAL_{8283D8D4-55B6-466F-B7D7-17A1352D9CAB}_";
  v8 = -1;
  v9 = 0;
  if ( dword_18009B478 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18009B478);
    if ( dword_18009B478 == -1 )
    {
      v12 = L"M$_CLOUDAP_TBAL_{8283D8D4-55B6-466F-B7D7-17A1352D9CAB}_";
      v13 = -1;
      if ( !a4 )
        v12 = L"M$_CLOUDAP_TBAL_{4416F0BD-3A59-4590-9579-DA6E08AF19B3}_";
      do
        ++v13;
      while ( v12[v13] );
      LODWORD(dword_18009B47C) = v13 + 65;
      Init_thread_footer(&dword_18009B478);
    }
  }
  StringUuid[0] = 0;
  v14 = 0;
  v15 = UuidToStringW(Uuid, StringUuid);
  if ( v15 )
  {
    v16 = "";
    v17 = "";
    while ( 1 )
    {
      v18 = v17--;
      v19 = *v17 == 92;
      if ( *v17 == 92 )
        break;
      if ( v17 <= "onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp" )
      {
        v19 = *v17 == 92;
        break;
      }
    }
    if ( v19 )
      v17 = v18;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v15, v17, 43, "UuidToStringW", &Class);
    v20 = 3221225495LL;
    HashStringPreRS2 = -1073741801;
    while ( 1 )
    {
      v22 = v16--;
      v23 = *v16 == 92;
      if ( *v16 == 92 )
        break;
      if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp" )
      {
        v23 = *v16 == 92;
        break;
      }
    }
    if ( v23 )
      v16 = v22;
    v37 = "UuidToStringW";
    v24 = v16;
    LODWORD(v36) = 45;
    goto LABEL_21;
  }
  v25 = -1;
  do
    ++v25;
  while ( StringUuid[0][v25] );
  do
    ++v8;
  while ( a2[v8] );
  v26 = v25 + 1 + v8;
  v27 = (unsigned __int16 *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(2 * v26);
  v9 = (UCHAR *)v27;
  if ( !v27 )
  {
    HashStringPreRS2 = -1073741801;
    v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v29, v28, 54, "AllocateLsaHeap", &Class);
    goto LABEL_49;
  }
  HashStringPreRS2 = RtlStringCchPrintfW(v27, v26, L"%ws%ws", StringUuid[0], a2);
  if ( HashStringPreRS2 )
  {
    v30 = "";
    while ( 1 )
    {
      v31 = v30--;
      v32 = *v30 == 92;
      if ( *v30 == 92 )
        break;
      if ( v30 <= "onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp" )
      {
        v32 = *v30 == 92;
        break;
      }
    }
    if ( v32 )
      v30 = v31;
    v37 = "RtlStringCchPrintfW";
    v24 = v30;
    LODWORD(v36) = 63;
    goto LABEL_36;
  }
  if ( a5 )
  {
    HashStringPreRS2 = GetHashStringPreRS2(v9, v39);
    if ( HashStringPreRS2 )
    {
      v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
      v37 = "GetHashStringPreRS2";
      LODWORD(v36) = 73;
      goto LABEL_36;
    }
LABEL_42:
    v14 = (unsigned __int16 *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)((unsigned int)(2 * dword_18009B47C));
    if ( !v14 )
    {
      HashStringPreRS2 = -1073741801;
      v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
      LODWORD(v36) = 80;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v34, v33, v36, "AllocateLsaHeap", &Class);
      goto LABEL_49;
    }
    if ( !a4 )
      v6 = L"M$_CLOUDAP_TBAL_{4416F0BD-3A59-4590-9579-DA6E08AF19B3}_";
    HashStringPreRS2 = RtlStringCchPrintfW(v14, (unsigned int)dword_18009B47C, L"%ws%ws", v6, v39);
    if ( !HashStringPreRS2 )
    {
      *a3 = v14;
      v14 = 0;
      HashStringPreRS2 = 0;
      goto LABEL_49;
    }
    v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
    v37 = "RtlStringCchPrintfW";
    LODWORD(v36) = 89;
    goto LABEL_36;
  }
  HashStringPreRS2 = GetHashString(v9, v39);
  if ( !HashStringPreRS2 )
    goto LABEL_42;
  v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
  v37 = "GetHashString";
  LODWORD(v36) = 68;
LABEL_36:
  v20 = HashStringPreRS2;
LABEL_21:
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v20, v24, v36, v37, &Class);
LABEL_49:
  if ( StringUuid[0] )
    RpcStringFreeW(StringUuid);
  if ( v9 )
    ((void (__fastcall *)(UCHAR *))g_pLsaFunctionTable->FreeLsaHeap)(v9);
  if ( v14 )
    ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v14);
  return HashStringPreRS2;
}

```

## disassembly

```asm
0x18002d71c  mov     [rsp+arg_18], rbx
0x18002d721  push    rbp
0x18002d722  push    rsi
0x18002d723  push    rdi
0x18002d724  push    r12
0x18002d726  push    r13
0x18002d728  push    r14
0x18002d72a  push    r15
0x18002d72c  sub     rsp, 0F0h
0x18002d733  mov     rax, cs:__security_cookie
0x18002d73a  xor     rax, rsp
0x18002d73d  mov     [rsp+128h+var_48], rax
0x18002d745  mov     rax, gs:58h
0x18002d74e  lea     r12, aMCloudapTbal44; "M$_CLOUDAP_TBAL_{4416F0BD-3A59-4590-957"...
0x18002d755  mov     rdi, rcx
0x18002d758  lea     rsi, aMCloudapTbal82; "M$_CLOUDAP_TBAL_{8283D8D4-55B6-466F-B7D"...
0x18002d75f  mov     ecx, cs:_tls_index
0x18002d765  mov     rbp, rdx
0x18002d768  mov     edx, 4
0x18002d76d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002d771  xor     r15d, r15d
0x18002d774  mov     r14b, r9b
0x18002d777  mov     r13, r8
0x18002d77a  mov     rax, [rax+rcx*8]
0x18002d77e  mov     eax, [rdx+rax]
0x18002d781  cmp     cs:dword_18009B478, eax
0x18002d787  jle     short loc_18002D7C9
0x18002d789  lea     rcx, dword_18009B478
0x18002d790  call    _Init_thread_header
0x18002d795  cmp     cs:dword_18009B478, ebx
0x18002d79b  jnz     short loc_18002D7C9
0x18002d79d  test    r14b, r14b
0x18002d7a0  mov     rdx, rsi
0x18002d7a3  mov     rax, rbx
0x18002d7a6  cmovz   rdx, r12
0x18002d7aa  inc     rax
0x18002d7ad  cmp     [rdx+rax*2], r15w
0x18002d7b2  jnz     short loc_18002D7AA
0x18002d7b4  add     eax, 41h ; 'A'
0x18002d7b7  lea     rcx, dword_18009B478
0x18002d7be  mov     cs:dword_18009B47C, eax
0x18002d7c4  call    _Init_thread_footer
0x18002d7c9  lea     rdx, [rsp+128h+StringUuid]; StringUuid
0x18002d7ce  mov     [rsp+128h+StringUuid], r15
0x18002d7d3  mov     rcx, rdi; Uuid
0x18002d7d6  mov     r12, r15
0x18002d7d9  call    cs:__imp_UuidToStringW
0x18002d7df  test    eax, eax
0x18002d7e1  jz      loc_18002D88B
0x18002d7e7  lea     rbx, aOnecoreDsExtCl_8+23h; ""
0x18002d7ee  mov     r14b, 5Ch ; '\'
0x18002d7f1  mov     r9, rbx
0x18002d7f4  lea     rsi, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18002d7fb  mov     rcx, r9
0x18002d7fe  dec     r9
0x18002d801  cmp     [r9], r14b
0x18002d804  jz      short loc_18002D80E
0x18002d806  cmp     r9, rsi
0x18002d809  ja      short loc_18002D7FB
0x18002d80b  cmp     [r9], r14b
0x18002d80e  cmovz   r9, rcx
0x18002d812  lea     rbp, Class
0x18002d819  mov     [rsp+128h+var_F8], rbp
0x18002d81e  lea     r13, aUuidtostringw; "UuidToStringW"
0x18002d825  mov     [rsp+128h+var_100], r13
0x18002d82a  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002d831  mov     r8d, eax
0x18002d834  mov     dword ptr [rsp+128h+var_108], 2Bh ; '+'
0x18002d83c  xor     ecx, ecx
0x18002d83e  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002d843  mov     r8d, 0C0000017h
0x18002d849  mov     edi, r8d
0x18002d84c  mov     rax, rbx
0x18002d84f  dec     rbx
0x18002d852  cmp     [rbx], r14b
0x18002d855  jz      short loc_18002D85F
0x18002d857  cmp     rbx, rsi
0x18002d85a  ja      short loc_18002D84C
0x18002d85c  cmp     [rbx], r14b
0x18002d85f  mov     [rsp+128h+var_F8], rbp
0x18002d864  cmovz   rbx, rax
0x18002d868  mov     [rsp+128h+var_100], r13
0x18002d86d  mov     r9, rbx
0x18002d870  mov     dword ptr [rsp+128h+var_108], 2Dh ; '-'
0x18002d878  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002d87f  xor     ecx, ecx
0x18002d881  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002d886  jmp     loc_18002DAD5
0x18002d88b  mov     rcx, [rsp+128h+StringUuid]
0x18002d890  mov     rax, rbx
0x18002d893  inc     rax
0x18002d896  cmp     [rcx+rax*2], r15w
0x18002d89b  jnz     short loc_18002D893
0x18002d89d  inc     rbx
0x18002d8a0  cmp     [rbp+rbx*2+0], r15w
0x18002d8a6  jnz     short loc_18002D89D
0x18002d8a8  inc     eax
0x18002d8aa  add     ebx, eax
0x18002d8ac  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18002d8b3  mov     rax, [rax+28h]
0x18002d8b7  lea     ecx, [rbx+rbx]
0x18002d8ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8bf  mov     r15, rax
0x18002d8c2  test    rax, rax
0x18002d8c5  jnz     short loc_18002D904
0x18002d8c7  mov     r8d, 0C0000017h
0x18002d8cd  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18002d8d4  mov     edi, r8d
0x18002d8d7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002d8dc  mov     r9, rax
0x18002d8df  lea     rbp, Class
0x18002d8e6  mov     [rsp+128h+var_F8], rbp
0x18002d8eb  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18002d8f2  mov     [rsp+128h+var_100], rax
0x18002d8f7  mov     dword ptr [rsp+128h+var_108], 36h ; '6'
0x18002d8ff  jmp     loc_18002D878
0x18002d904  mov     r9, [rsp+128h+StringUuid]
0x18002d909  lea     r8, aWsWs; "%ws%ws"
0x18002d910  mov     edx, ebx; unsigned __int64
0x18002d912  mov     rcx, r15; unsigned __int16 *
0x18002d915  mov     [rsp+128h+var_108], rbp
0x18002d91a  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d91f  mov     edi, eax
0x18002d921  test    eax, eax
0x18002d923  jz      short loc_18002D978
0x18002d925  lea     rbx, aOnecoreDsExtCl_8+23h; ""
0x18002d92c  mov     r14b, 5Ch ; '\'
0x18002d92f  lea     rsi, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18002d936  mov     rax, rbx
0x18002d939  dec     rbx
0x18002d93c  cmp     [rbx], r14b
0x18002d93f  jz      short loc_18002D949
0x18002d941  cmp     rbx, rsi
0x18002d944  ja      short loc_18002D936
0x18002d946  cmp     [rbx], r14b
0x18002d949  cmovz   rbx, rax
0x18002d94d  lea     rbp, Class
0x18002d954  mov     [rsp+128h+var_F8], rbp
0x18002d959  lea     rax, aRtlstringcchpr; "RtlStringCchPrintfW"
0x18002d960  mov     [rsp+128h+var_100], rax
0x18002d965  mov     r9, rbx
0x18002d968  mov     dword ptr [rsp+128h+var_108], 3Fh ; '?'
0x18002d970  mov     r8d, edi
0x18002d973  jmp     loc_18002D878
0x18002d978  lea     rdx, [rsp+128h+var_D8]; unsigned __int16 *
0x18002d97d  mov     rcx, r15; pbInput
0x18002d980  cmp     [rsp+128h+arg_20], r12b
0x18002d988  jnz     short loc_18002D9C6
0x18002d98a  call    ?GetHashString@@YAJPEBGQEAG@Z; GetHashString(ushort const *,ushort * const)
0x18002d98f  mov     edi, eax
0x18002d991  test    eax, eax
0x18002d993  jz      short loc_18002DA05
0x18002d995  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18002d99c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002d9a1  mov     r9, rax
0x18002d9a4  lea     rbp, Class
0x18002d9ab  mov     [rsp+128h+var_F8], rbp
0x18002d9b0  lea     rax, aGethashstring; "GetHashString"
0x18002d9b7  mov     [rsp+128h+var_100], rax
0x18002d9bc  mov     dword ptr [rsp+128h+var_108], 44h ; 'D'
0x18002d9c4  jmp     short loc_18002D970
0x18002d9c6  call    ?GetHashStringPreRS2@@YAJPEBGQEAG@Z; GetHashStringPreRS2(ushort const *,ushort * const)
0x18002d9cb  mov     edi, eax
0x18002d9cd  test    eax, eax
0x18002d9cf  jz      short loc_18002DA05
0x18002d9d1  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18002d9d8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002d9dd  mov     r9, rax
0x18002d9e0  lea     rbp, Class
0x18002d9e7  mov     [rsp+128h+var_F8], rbp
0x18002d9ec  lea     rax, aGethashstringp; "GetHashStringPreRS2"
0x18002d9f3  mov     [rsp+128h+var_100], rax
0x18002d9f8  mov     dword ptr [rsp+128h+var_108], 49h ; 'I'
0x18002da00  jmp     loc_18002D970
0x18002da05  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18002da0c  mov     ecx, cs:dword_18009B47C
0x18002da12  add     ecx, ecx
0x18002da14  mov     rax, [rax+28h]
0x18002da18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da1d  mov     r12, rax
0x18002da20  test    rax, rax
0x18002da23  jnz     short loc_18002DA62
0x18002da25  mov     r8d, 0C0000017h
0x18002da2b  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18002da32  mov     edi, r8d
0x18002da35  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002da3a  mov     r9, rax
0x18002da3d  lea     rbp, Class
0x18002da44  mov     [rsp+128h+var_F8], rbp
0x18002da49  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18002da50  mov     [rsp+128h+var_100], rax
0x18002da55  mov     dword ptr [rsp+128h+var_108], 50h ; 'P'
0x18002da5d  jmp     loc_18002D878
0x18002da62  mov     edx, cs:dword_18009B47C; unsigned __int64
0x18002da68  lea     rax, aMCloudapTbal44; "M$_CLOUDAP_TBAL_{4416F0BD-3A59-4590-957"...
0x18002da6f  test    r14b, r14b
0x18002da72  lea     r8, aWsWs; "%ws%ws"
0x18002da79  mov     rcx, r12; unsigned __int16 *
0x18002da7c  cmovz   rsi, rax
0x18002da80  lea     rax, [rsp+128h+var_D8]
0x18002da85  mov     r9, rsi
0x18002da88  mov     [rsp+128h+var_108], rax
0x18002da8d  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002da92  mov     edi, eax
0x18002da94  test    eax, eax
0x18002da96  jz      short loc_18002DACC
0x18002da98  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18002da9f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002daa4  mov     r9, rax
0x18002daa7  lea     rbp, Class
0x18002daae  mov     [rsp+128h+var_F8], rbp
0x18002dab3  lea     rax, aRtlstringcchpr; "RtlStringCchPrintfW"
0x18002daba  mov     [rsp+128h+var_100], rax
0x18002dabf  mov     dword ptr [rsp+128h+var_108], 59h ; 'Y'
0x18002dac7  jmp     loc_18002D970
0x18002dacc  mov     [r13+0], r12
0x18002dad0  xor     r12d, r12d
0x18002dad3  xor     edi, edi
0x18002dad5  cmp     [rsp+128h+StringUuid], 0
0x18002dadb  jz      short loc_18002DAE8
0x18002dadd  lea     rcx, [rsp+128h+StringUuid]; String
0x18002dae2  call    cs:__imp_RpcStringFreeW
0x18002dae8  test    r15, r15
0x18002daeb  jz      short loc_18002DB00
0x18002daed  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18002daf4  mov     rcx, r15
0x18002daf7  mov     rax, [rax+30h]
0x18002dafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db00  test    r12, r12
0x18002db03  jz      short loc_18002DB18
0x18002db05  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18002db0c  mov     rcx, r12
0x18002db0f  mov     rax, [rax+30h]
0x18002db13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db18  mov     eax, edi
0x18002db1a  mov     rcx, [rsp+128h+var_48]
0x18002db22  xor     rcx, rsp; StackCookie
0x18002db25  call    __security_check_cookie
0x18002db2a  mov     rbx, [rsp+128h+arg_18]
0x18002db32  add     rsp, 0F0h
0x18002db39  pop     r15
0x18002db3b  pop     r14
0x18002db3d  pop     r13
0x18002db3f  pop     r12
0x18002db41  pop     rdi
0x18002db42  pop     rsi
0x18002db43  pop     rbp
0x18002db44  retn
```
