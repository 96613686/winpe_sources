# SortCertificatesInPlace(_CERT_CONTEXT const * * const,ulong)

- ea: `0x180046728`
- end: `0x18004697b`
- name: `?SortCertificatesInPlace@@YAJQEAPEBU_CERT_CONTEXT@@K@Z`
- size: `595`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT **const, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800461d8`

## callees

- `0x18001b65c`
- `0x180027278`
- `0x180027448`
- `0x18002aee4`
- `0x18002bc58`
- `0x18002e664`
- `0x18002e850`
- `0x18002f710`
- `0x18002f7e7`
- `0x180046728`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800468be`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800468be`

## string_xrefs

- `0x180046943`: `StringCompare`

## pseudocode

```c
__int64 __fastcall SortCertificatesInPlace(const struct _CERT_CONTEXT **const a1, unsigned int a2)
{
  unsigned __int16 **v2; // r14
  __int64 v3; // r12
  unsigned int v5; // ebp
  unsigned __int64 v7; // rax
  unsigned __int16 **v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 i; // rbx
  int TenantId; // eax
  const unsigned __int16 *v13; // r8
  __int64 v14; // rdi
  unsigned __int16 **v15; // rsi
  int j; // r15d
  int v17; // ebx
  const struct _CERT_CONTEXT *v18; // rsi
  const unsigned __int16 *v19; // rax
  int v20; // ecx
  __int64 v21; // rsi
  __int64 v22; // rbx
  size_t v23; // rdi
  unsigned int v24; // [rsp+20h] [rbp-48h]
  int v25; // [rsp+70h] [rbp+8h] BYREF
  const unsigned __int16 *v26; // [rsp+80h] [rbp+18h]
  const struct _CERT_CONTEXT *v27; // [rsp+88h] [rbp+20h]

  v2 = 0;
  v3 = a2;
  if ( a1 )
  {
    v5 = 0;
    if ( a2 != 1 )
    {
      v7 = 8LL * a2;
      if ( !is_mul_ok(a2, 8u) )
        v7 = -1;
      v8 = (unsigned __int16 **)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
      v2 = v8;
      if ( !v8 )
      {
        v5 = -2147024882;
        Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"SortCertificatesInPlace");
        goto LABEL_3;
      }
      memset_0(v8, 0, 8 * v3);
      for ( i = 0; (unsigned int)i < (unsigned int)v3; i = (unsigned int)(i + 1) )
      {
        TenantId = RegistrationCertStatus::GetTenantId(a1[i], &v2[i], 0);
        v5 = TenantId;
        if ( TenantId < 0 )
        {
          v13 = L"RegistrationCertStatus::GetTenantId";
LABEL_14:
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"SortCertificatesInPlace",
            v13,
            (unsigned int)TenantId);
          v14 = 0;
          v15 = v2;
          goto LABEL_28;
        }
      }
      for ( j = 1; j < (int)v3; ++j )
      {
        v17 = j - 1;
        v18 = a1[j];
        v19 = v2[j];
        v26 = v19;
        v27 = v18;
        do
        {
          v25 = 0;
          TenantId = CompareStringInternal(v2[v17], v9, v19, v10, v24, (enum COMPARE_STR_RESULT *)&v25);
          v5 = TenantId;
          if ( TenantId < 0 )
          {
            v13 = L"StringCompare";
            goto LABEL_14;
          }
          if ( v25 == 1 || v25 == 2 && CompareFileTime(&a1[v17]->pCertInfo->NotBefore, &v18->pCertInfo->NotBefore) <= 0 )
            break;
          --v17;
          v19 = v26;
        }
        while ( v17 >= 0 );
        v20 = v17 + 1;
        if ( v17 + 1 != j )
        {
          v21 = v17;
          v22 = v17 + 2;
          v23 = 8LL * (j - v20);
          memmove_0(&a1[v22], &a1[v21 + 1], v23);
          memmove_0(&v2[v22], &v2[v21 + 1], v23);
          a1[v21 + 1] = v27;
          v2[v21 + 1] = (unsigned __int16 *)v26;
        }
      }
    }
    v14 = 0;
    v15 = v2;
    if ( v2 )
    {
LABEL_28:
      while ( (unsigned int)v14 < (unsigned int)v3 )
      {
        operator delete(v15[v14]);
        v15[v14] = 0;
        v14 = (unsigned int)(v14 + 1);
      }
    }
  }
  else
  {
    v5 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"SortCertificatesInPlace", L"pCertContexts");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"SortCertificatesInPlace", L"pCertContexts");
  }
LABEL_3:
  operator delete(v2);
  return v5;
}

```

## disassembly

```asm
0x180046728  mov     [rsp+arg_8], rbx
0x18004672d  push    rbp
0x18004672e  push    rsi
0x18004672f  push    rdi
0x180046730  push    r12
0x180046732  push    r13
0x180046734  push    r14
0x180046736  push    r15
0x180046738  sub     rsp, 30h
0x18004673c  xor     r14d, r14d
0x18004673f  mov     r12d, edx
0x180046742  mov     r13, rcx
0x180046745  test    rcx, rcx
0x180046748  jnz     short loc_18004679B
0x18004674a  lea     r8, aPcertcontexts; "pCertContexts"
0x180046751  mov     ebp, 80070057h
0x180046756  lea     rdx, aSortcertificat; "SortCertificatesInPlace"
0x18004675d  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180046764  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180046769  lea     rdx, aPcertcontexts; "pCertContexts"
0x180046770  lea     rcx, aSortcertificat; "SortCertificatesInPlace"
0x180046777  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18004677c  mov     rcx, r14; Block
0x18004677f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180046784  mov     rbx, [rsp+68h+arg_8]
0x180046789  mov     eax, ebp
0x18004678b  add     rsp, 30h
0x18004678f  pop     r15
0x180046791  pop     r14
0x180046793  pop     r13
0x180046795  pop     r12
0x180046797  pop     rdi
0x180046798  pop     rsi
0x180046799  pop     rbp
0x18004679a  retn
0x18004679b  xor     ebp, ebp
0x18004679d  cmp     r12d, 1
0x1800467a1  jz      loc_18004694F
0x1800467a7  lea     rcx, [rbp-1]
0x1800467ab  lea     eax, [rbp+8]
0x1800467ae  mul     r12
0x1800467b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800467b8  cmovb   rax, rcx
0x1800467bc  mov     rcx, rax; unsigned __int64
0x1800467bf  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800467c4  mov     r14, rax
0x1800467c7  test    rax, rax
0x1800467ca  jnz     short loc_1800467E6
0x1800467cc  lea     rdx, aSortcertificat; "SortCertificatesInPlace"
0x1800467d3  mov     ebp, 8007000Eh
0x1800467d8  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x1800467df  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800467e4  jmp     short loc_18004677C
0x1800467e6  lea     r8, ds:0[r12*8]; Size
0x1800467ee  xor     edx, edx; Val
0x1800467f0  mov     rcx, r14; void *
0x1800467f3  call    memset_0
0x1800467f8  xor     ebx, ebx
0x1800467fa  cmp     ebx, r12d
0x1800467fd  jnb     short loc_180046841
0x1800467ff  mov     rcx, [r13+rbx*8+0]; struct _CERT_CONTEXT *
0x180046804  lea     rdx, [r14+rbx*8]; unsigned __int16 **
0x180046808  xor     r8d, r8d; int *
0x18004680b  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x180046810  mov     ebp, eax
0x180046812  test    eax, eax
0x180046814  js      short loc_18004681A
0x180046816  inc     ebx
0x180046818  jmp     short loc_1800467FA
0x18004681a  lea     r8, aRegistrationce_3; "RegistrationCertStatus::GetTenantId"
0x180046821  mov     r9d, eax
0x180046824  lea     rdx, aSortcertificat; "SortCertificatesInPlace"
0x18004682b  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180046832  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180046837  xor     edi, edi
0x180046839  mov     rsi, r14
0x18004683c  jmp     loc_18004695D
0x180046841  mov     r15d, 1
0x180046847  cmp     r15d, r12d
0x18004684a  jge     loc_18004694F
0x180046850  movsxd  rax, r15d
0x180046853  lea     ebx, [r15-1]
0x180046857  mov     rsi, [r13+rax*8+0]
0x18004685c  mov     rax, [r14+rax*8]
0x180046860  mov     [rsp+68h+arg_10], rax
0x180046868  mov     [rsp+68h+arg_18], rsi
0x180046870  lea     rcx, [rsp+68h+arg_0]
0x180046875  movsxd  rdi, ebx
0x180046878  mov     [rsp+68h+var_40], rcx; enum COMPARE_STR_RESULT *
0x18004687d  mov     r8, rax; unsigned __int16 *
0x180046880  mov     [rsp+68h+arg_0], 0
0x180046888  mov     rcx, [r14+rdi*8]; lpString1
0x18004688c  call    ?CompareStringInternal@@YAJPEBGH0HKPEAW4COMPARE_STR_RESULT@@@Z; CompareStringInternal(ushort const *,int,ushort const *,int,ulong,COMPARE_STR_RESULT *)
0x180046891  mov     ebp, eax
0x180046893  test    eax, eax
0x180046895  js      loc_180046943
0x18004689b  cmp     [rsp+68h+arg_0], 1
0x1800468a0  jz      short loc_1800468D5
0x1800468a2  cmp     [rsp+68h+arg_0], 2
0x1800468a7  jnz     short loc_1800468C8
0x1800468a9  mov     rax, [r13+rdi*8+0]
0x1800468ae  mov     rdx, [rsi+18h]
0x1800468b2  add     rdx, 40h ; '@'; lpFileTime2
0x1800468b6  mov     rcx, [rax+18h]
0x1800468ba  add     rcx, 40h ; '@'; lpFileTime1
0x1800468be  call    cs:__imp_CompareFileTime
0x1800468c4  test    eax, eax
0x1800468c6  jle     short loc_1800468D5
0x1800468c8  sub     ebx, 1
0x1800468cb  mov     rax, [rsp+68h+arg_10]
0x1800468d3  jns     short loc_180046870
0x1800468d5  lea     ecx, [rbx+1]
0x1800468d8  cmp     ecx, r15d
0x1800468db  jz      short loc_18004693B
0x1800468dd  mov     eax, r15d
0x1800468e0  movsxd  rsi, ebx
0x1800468e3  sub     eax, ecx
0x1800468e5  lea     rdx, [r13+8]
0x1800468e9  movsxd  rdi, eax
0x1800468ec  lea     eax, [rcx+1]
0x1800468ef  movsxd  rbx, eax
0x1800468f2  shl     rdi, 3
0x1800468f6  lea     rdx, [rdx+rsi*8]; Src
0x1800468fa  mov     r8, rdi; Size
0x1800468fd  lea     rcx, ds:0[rbx*8]
0x180046905  add     rcx, r13; void *
0x180046908  call    memmove_0
0x18004690d  lea     rdx, [r14+8]
0x180046911  mov     r8, rdi; Size
0x180046914  lea     rdx, [rdx+rsi*8]; Src
0x180046918  lea     rcx, [r14+rbx*8]; void *
0x18004691c  call    memmove_0
0x180046921  mov     rax, [rsp+68h+arg_18]
0x180046929  mov     [r13+rsi*8+8], rax
0x18004692e  mov     rax, [rsp+68h+arg_10]
0x180046936  mov     [r14+rsi*8+8], rax
0x18004693b  inc     r15d
0x18004693e  jmp     loc_180046847
0x180046943  lea     r8, aStringcompare; "StringCompare"
0x18004694a  jmp     loc_180046821
0x18004694f  xor     edi, edi
0x180046951  mov     rsi, r14
0x180046954  test    r14, r14
0x180046957  jz      loc_18004677C
0x18004695d  cmp     edi, r12d
0x180046960  jnb     loc_18004677C
0x180046966  mov     rcx, [rsi+rdi*8]; Block
0x18004696a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004696f  mov     qword ptr [rsi+rdi*8], 0
0x180046977  inc     edi
0x180046979  jmp     short loc_18004695D
```
