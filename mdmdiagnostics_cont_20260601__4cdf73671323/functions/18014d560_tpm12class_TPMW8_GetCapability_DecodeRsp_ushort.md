# tpm12class::TPMW8_GetCapability::DecodeRsp(ushort *)

- ea: `0x18014d560`
- end: `0x18014dd0f`
- name: `?DecodeRsp@TPMW8_GetCapability@tpm12class@@UEAAJPEAG@Z`
- size: `1967`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_GetCapability *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800ed730`
- `0x18014b450`
- `0x18014d560`
- `0x18015125c`
- `0x180151720`
- `0x1801517cc`
- `0x180151f14`
- `0x180152210`
- `0x180152508`
- `0x180191010`

## string_xrefs

- `0x18014d715`: `commandCode`
- `0x18014d78f`: `commandCode`
- `0x18014d809`: `commandCode`
- `0x18014d6ee`: `%sauditCommands[%d].`
- `0x18014d768`: `%sppCommands[%d].`
- `0x18014d7e2`: `%scommands[%d].`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_GetCapability::DecodeRsp(
        tpm12class::TPMW8_GetCapability *this,
        unsigned __int16 *a2)
{
  int v4; // ebx
  unsigned __int8 v5; // r9
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int nn; // r14d
  unsigned int mm; // r14d
  unsigned int kk; // r14d
  unsigned int jj; // r14d
  unsigned int ii; // r14d
  unsigned int n; // r14d
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int m; // r14d
  __int64 v22; // r15
  unsigned int k; // r14d
  unsigned int j; // r14d
  unsigned int i; // r14d
  struct TPM_SYMBOLTABLE_ENTRY *v26; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v27; // [rsp+30h] [rbp-D0h] BYREF
  char v28[510]; // [rsp+32h] [rbp-CEh] BYREF

  v27 = 0;
  v4 = 0;
  memset_0(v28, 0, sizeof(v28));
  if ( TraceEnabled() )
  {
    v4 = tpm12class::TPMW8_COMMAND::DecodeRsp(this, a2);
    if ( v4 >= 0 )
    {
      v4 = TraceDirect(L"--TPM2_GetCapability: Parameters---------------------------------------\r\n");
      if ( v4 >= 0 )
      {
        v4 = TraceUINT8Value(
               a2,
               L"moreData",
               *((_BYTE *)this + 204),
               v5,
               (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8I_YES_NO,
               0);
        if ( v4 >= 0 )
        {
          v4 = TraceUINT32Value(
                 a2,
                 L"capability",
                 *((_DWORD *)this + 52),
                 0,
                 (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_CAP,
                 0);
          if ( v4 >= 0 )
          {
            if ( *((_DWORD *)this + 52) == 256
              || (v4 = TraceUINT32Value(a2, L"count", *((_DWORD *)this + 53), 1u, 0, 0), v4 >= 0) )
            {
              v6 = *((_DWORD *)this + 52);
              if ( v6 > 5 )
              {
                v16 = v6 - 6;
                if ( !v16 )
                {
                  for ( i = 0; i < *((_DWORD *)this + 53); ++i )
                  {
                    LODWORD(v26) = i;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%stpmProperties[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(
                           &v27,
                           L"property",
                           *(_DWORD *)(*((_QWORD *)this + 33) + 8LL * i),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_PT,
                           1u);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(&v27, L"value", *(_DWORD *)(*((_QWORD *)this + 33) + 8LL * i + 4), 1u, 0, 0);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                v17 = v16 - 1;
                if ( !v17 )
                {
                  for ( j = 0; j < *((_DWORD *)this + 53); ++j )
                  {
                    LODWORD(v26) = j;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%spcrProperties[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(
                           &v27,
                           L"property",
                           *(_DWORD *)(*((_QWORD *)this + 34) + 8LL * j),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_PT_PCR,
                           0);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceBufferValue(
                           &v27,
                           L"pcrSelect",
                           (unsigned __int8 *)(*((_QWORD *)this + 34) + 5LL + 8LL * j),
                           *(unsigned __int8 *)(*((_QWORD *)this + 34) + 8LL * j + 4));
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                v18 = v17 - 1;
                if ( !v18 )
                {
                  for ( k = 0; k < *((_DWORD *)this + 53); ++k )
                  {
                    LODWORD(v26) = k;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%seccCurves[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT16Value(
                           &v27,
                           L"curveID",
                           *(_WORD *)(*((_QWORD *)this + 35) + 2LL * k),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_ECC_CURVE,
                           0);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                v19 = v18 - 1;
                if ( !v19 )
                {
                  for ( m = 0; m < *((_DWORD *)this + 53); ++m )
                  {
                    LODWORD(v26) = m;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%sauthPolicies[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v22 = 136LL * m;
                    v4 = TraceUINT32Value(&v27, L"handle", *(_DWORD *)(v22 + *((_QWORD *)this + 36)), 0, 0, 0);
                    if ( v4 < 0 )
                      break;
                    v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)(v22
                                                                                            + *((_QWORD *)this + 36)
                                                                                            + 8LL)
                                                                                + 40LL))(
                           v22 + *((_QWORD *)this + 36) + 8LL,
                           &v27);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                if ( v19 == 247 )
                {
                  v4 = StringCchPrintfW(&v27, 0x100u, L"%svendorProperties.", a2);
                  if ( v4 >= 0 )
                    return (unsigned int)TraceBufferValue(
                                           a2,
                                           L"vendorSpecificData",
                                           *((unsigned __int8 **)this + 37),
                                           *((_DWORD *)this + 76));
                  return (unsigned int)v4;
                }
              }
              else
              {
                if ( v6 == 5 )
                {
                  for ( n = 0; n < *((_DWORD *)this + 53); ++n )
                  {
                    LODWORD(v26) = n;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%spcrs[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(
                           &v27,
                           L"hashAlg",
                           *(unsigned __int16 *)(*((_QWORD *)this + 32) + 72LL * n + 56),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_ALG,
                           0);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                if ( !v6 )
                {
                  for ( ii = 0; ii < *((_DWORD *)this + 53); ++ii )
                  {
                    LODWORD(v26) = ii;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%salgorithms[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT16Value(
                           &v27,
                           L"alg",
                           *(_WORD *)(*((_QWORD *)this + 27) + 8LL * ii),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_ALG,
                           0);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(
                           &v27,
                           L"alg",
                           *(unsigned __int16 *)(*((_QWORD *)this + 27) + 8LL * ii),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8A_ALGORITHM,
                           0);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                v7 = v6 - 1;
                if ( !v7 )
                {
                  for ( jj = 0; jj < *((_DWORD *)this + 53); ++jj )
                  {
                    LODWORD(v26) = jj;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%shandles[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(
                           &v27,
                           L"handle",
                           *(_DWORD *)(*((_QWORD *)this + 28) + 4LL * jj),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_RH,
                           1u);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                v8 = v7 - 1;
                if ( !v8 )
                {
                  for ( kk = 0; kk < *((_DWORD *)this + 53); ++kk )
                  {
                    LODWORD(v26) = kk;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%scommands[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(
                           &v27,
                           L"commandCode",
                           *(_DWORD *)(*((_QWORD *)this + 29) + 4LL * kk),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_CC,
                           0);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                v9 = v8 - 1;
                if ( !v9 )
                {
                  for ( mm = 0; mm < *((_DWORD *)this + 53); ++mm )
                  {
                    LODWORD(v26) = mm;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%sppCommands[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(
                           &v27,
                           L"commandCode",
                           *(_DWORD *)(*((_QWORD *)this + 30) + 4LL * mm),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_CC,
                           0);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
                if ( v9 == 1 )
                {
                  for ( nn = 0; nn < *((_DWORD *)this + 53); ++nn )
                  {
                    LODWORD(v26) = nn;
                    v4 = StringCchPrintfW(&v27, 0x100u, L"%sauditCommands[%d].", a2, v26);
                    if ( v4 < 0 )
                      break;
                    v4 = TraceUINT32Value(
                           &v27,
                           L"commandCode",
                           *(_DWORD *)(*((_QWORD *)this + 31) + 4LL * nn),
                           0,
                           (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPMW8_CC,
                           0);
                    if ( v4 < 0 )
                      break;
                  }
                  return (unsigned int)v4;
                }
              }
              return 2147500033LL;
            }
          }
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18014d560  mov     [rsp-8+arg_10], rbx
0x18014d565  push    rbp
0x18014d566  push    rsi
0x18014d567  push    rdi
0x18014d568  push    r12
0x18014d56a  push    r13
0x18014d56c  push    r14
0x18014d56e  push    r15
0x18014d570  lea     rbp, [rsp-140h]
0x18014d578  sub     rsp, 240h
0x18014d57f  mov     rax, cs:__security_cookie
0x18014d586  xor     rax, rsp
0x18014d589  mov     [rbp+170h+var_40], rax
0x18014d590  mov     rsi, rdx
0x18014d593  mov     rdi, rcx
0x18014d596  xor     r13d, r13d
0x18014d599  lea     rcx, [rsp+270h+var_23E]; void *
0x18014d59e  xor     edx, edx; Val
0x18014d5a0  mov     [rsp+270h+var_240], r13w
0x18014d5a6  mov     r8d, 1FEh; Size
0x18014d5ac  mov     ebx, r13d
0x18014d5af  call    memset_0
0x18014d5b4  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x18014d5b9  test    al, al
0x18014d5bb  jz      loc_18014DCE3
0x18014d5c1  mov     rdx, rsi; unsigned __int16 *
0x18014d5c4  mov     rcx, rdi; this
0x18014d5c7  call    ?DecodeRsp@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeRsp(ushort *)
0x18014d5cc  mov     ebx, eax
0x18014d5ce  test    eax, eax
0x18014d5d0  js      loc_18014DCE3
0x18014d5d6  lea     rcx, aTpm2Getcapabil; "--TPM2_GetCapability: Parameters-------"...
0x18014d5dd  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x18014d5e2  mov     ebx, eax
0x18014d5e4  test    eax, eax
0x18014d5e6  js      loc_18014DCE3
0x18014d5ec  mov     r8b, [rdi+0CCh]; unsigned __int8
0x18014d5f3  lea     rax, ?st_TPMW8I_YES_NO@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8I_YES_NO
0x18014d5fa  mov     [rsp+270h+var_248], r13b; char
0x18014d5ff  lea     rdx, aMoredata; "moreData"
0x18014d606  mov     rcx, rsi; unsigned __int16 *
0x18014d609  mov     [rsp+270h+var_250], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x18014d60e  call    ?TraceUINT8Value@@YAJPEAG0EEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT8Value(ushort *,ushort *,uchar,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18014d613  mov     ebx, eax
0x18014d615  test    eax, eax
0x18014d617  js      loc_18014DCE3
0x18014d61d  mov     r8d, [rdi+0D0h]; unsigned int
0x18014d624  lea     rax, ?st_TPMW8_CAP@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CAP
0x18014d62b  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x18014d630  lea     rdx, aCapability; "capability"
0x18014d637  xor     r9d, r9d; unsigned __int8
0x18014d63a  mov     [rsp+270h+var_250], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x18014d63f  mov     rcx, rsi; unsigned __int16 *
0x18014d642  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18014d647  mov     ebx, eax
0x18014d649  test    eax, eax
0x18014d64b  js      loc_18014DCE3
0x18014d651  cmp     dword ptr [rdi+0D0h], 100h
0x18014d65b  lea     r12d, [r13+1]
0x18014d65f  jz      short loc_18014D68E
0x18014d661  mov     r8d, [rdi+0D4h]; unsigned int
0x18014d668  lea     rdx, aCount; "count"
0x18014d66f  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x18014d674  mov     r9b, r12b; unsigned __int8
0x18014d677  mov     rcx, rsi; unsigned __int16 *
0x18014d67a  mov     [rsp+270h+var_250], r13; struct TPM_SYMBOLTABLE_ENTRY *
0x18014d67f  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18014d684  mov     ebx, eax
0x18014d686  test    eax, eax
0x18014d688  js      loc_18014DCE3
0x18014d68e  mov     eax, [rdi+0D0h]
0x18014d694  cmp     eax, 5
0x18014d697  ja      loc_18014D9F0
0x18014d69d  jz      loc_18014D970
0x18014d6a3  test    eax, eax
0x18014d6a5  jz      loc_18014D8B7
0x18014d6ab  sub     eax, r12d
0x18014d6ae  jz      loc_18014D83D
0x18014d6b4  sub     eax, r12d
0x18014d6b7  jz      loc_18014D7C3
0x18014d6bd  sub     eax, r12d
0x18014d6c0  jz      loc_18014D749
0x18014d6c6  cmp     eax, r12d
0x18014d6c9  jnz     loc_18014DA17
0x18014d6cf  mov     r14d, r13d
0x18014d6d2  lea     r15, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x18014d6d9  cmp     r14d, [rdi+0D4h]
0x18014d6e0  jnb     loc_18014DCE3
0x18014d6e6  mov     r9, rsi
0x18014d6e9  mov     dword ptr [rsp+270h+var_250], r14d
0x18014d6ee  lea     r8, aSauditcommands; "%sauditCommands[%d]."
0x18014d6f5  mov     edx, 100h; unsigned __int64
0x18014d6fa  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18014d6ff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18014d704  mov     ebx, eax
0x18014d706  test    eax, eax
0x18014d708  js      loc_18014DCE3
0x18014d70e  mov     r8, [rdi+0F8h]
0x18014d715  lea     rdx, aCommandcode; "commandCode"
0x18014d71c  mov     eax, r14d
0x18014d71f  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18014d724  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x18014d729  xor     r9d, r9d; unsigned __int8
0x18014d72c  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x18014d731  mov     r8d, [r8+rax*4]; unsigned int
0x18014d735  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18014d73a  mov     ebx, eax
0x18014d73c  test    eax, eax
0x18014d73e  js      loc_18014DCE3
0x18014d744  add     r14d, r12d
0x18014d747  jmp     short loc_18014D6D9
0x18014d749  mov     r14d, r13d
0x18014d74c  lea     r15, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x18014d753  cmp     r14d, [rdi+0D4h]
0x18014d75a  jnb     loc_18014DCE3
0x18014d760  mov     r9, rsi
0x18014d763  mov     dword ptr [rsp+270h+var_250], r14d
0x18014d768  lea     r8, aSppcommandsD; "%sppCommands[%d]."
0x18014d76f  mov     edx, 100h; unsigned __int64
0x18014d774  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18014d779  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18014d77e  mov     ebx, eax
0x18014d780  test    eax, eax
0x18014d782  js      loc_18014DCE3
0x18014d788  mov     r8, [rdi+0F0h]
0x18014d78f  lea     rdx, aCommandcode; "commandCode"
0x18014d796  mov     eax, r14d
0x18014d799  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18014d79e  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x18014d7a3  xor     r9d, r9d; unsigned __int8
0x18014d7a6  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x18014d7ab  mov     r8d, [r8+rax*4]; unsigned int
0x18014d7af  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18014d7b4  mov     ebx, eax
0x18014d7b6  test    eax, eax
0x18014d7b8  js      loc_18014DCE3
0x18014d7be  add     r14d, r12d
0x18014d7c1  jmp     short loc_18014D753
0x18014d7c3  mov     r14d, r13d
0x18014d7c6  lea     r15, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x18014d7cd  cmp     r14d, [rdi+0D4h]
0x18014d7d4  jnb     loc_18014DCE3
0x18014d7da  mov     r9, rsi
0x18014d7dd  mov     dword ptr [rsp+270h+var_250], r14d
0x18014d7e2  lea     r8, aScommandsD; "%scommands[%d]."
0x18014d7e9  mov     edx, 100h; unsigned __int64
0x18014d7ee  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18014d7f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18014d7f8  mov     ebx, eax
0x18014d7fa  test    eax, eax
0x18014d7fc  js      loc_18014DCE3
0x18014d802  mov     r8, [rdi+0E8h]
0x18014d809  lea     rdx, aCommandcode; "commandCode"
0x18014d810  mov     eax, r14d
0x18014d813  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18014d818  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x18014d81d  xor     r9d, r9d; unsigned __int8
0x18014d820  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x18014d825  mov     r8d, [r8+rax*4]; unsigned int
0x18014d829  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18014d82e  mov     ebx, eax
0x18014d830  test    eax, eax
0x18014d832  js      loc_18014DCE3
0x18014d838  add     r14d, r12d
0x18014d83b  jmp     short loc_18014D7CD
0x18014d83d  mov     r14d, r13d
0x18014d840  cmp     r14d, [rdi+0D4h]
0x18014d847  jnb     loc_18014DCE3
0x18014d84d  mov     r9, rsi
0x18014d850  mov     dword ptr [rsp+270h+var_250], r14d
0x18014d855  lea     r8, aShandlesD; "%shandles[%d]."
0x18014d85c  mov     edx, 100h; unsigned __int64
0x18014d861  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18014d866  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18014d86b  mov     ebx, eax
0x18014d86d  test    eax, eax
0x18014d86f  js      loc_18014DCE3
0x18014d875  mov     r8, [rdi+0E0h]
0x18014d87c  lea     rcx, ?st_TPMW8_RH@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_RH
0x18014d883  mov     eax, r14d
0x18014d886  lea     rdx, aHandle; "handle"
0x18014d88d  mov     [rsp+270h+var_248], r12b; unsigned __int8
0x18014d892  xor     r9d, r9d; unsigned __int8
0x18014d895  mov     [rsp+270h+var_250], rcx; struct TPM_SYMBOLTABLE_ENTRY *
0x18014d89a  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18014d89f  mov     r8d, [r8+rax*4]; unsigned int
0x18014d8a3  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18014d8a8  mov     ebx, eax
0x18014d8aa  test    eax, eax
0x18014d8ac  js      loc_18014DCE3
0x18014d8b2  add     r14d, r12d
0x18014d8b5  jmp     short loc_18014D840
0x18014d8b7  mov     r14d, r13d
0x18014d8ba  lea     r15, ?st_TPMW8_ALG@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_ALG
0x18014d8c1  cmp     r14d, [rdi+0D4h]
0x18014d8c8  jnb     loc_18014DCE3
0x18014d8ce  mov     r9, rsi
0x18014d8d1  mov     dword ptr [rsp+270h+var_250], r14d
0x18014d8d6  lea     r8, aSalgorithmsD; "%salgorithms[%d]."
0x18014d8dd  mov     edx, 100h; unsigned __int64
0x18014d8e2  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18014d8e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18014d8ec  mov     ebx, eax
0x18014d8ee  test    eax, eax
0x18014d8f0  js      loc_18014DCE3
0x18014d8f6  mov     r8, [rdi+0D8h]
0x18014d8fd  lea     rdx, aAlg; "alg"
0x18014d904  mov     r12d, r14d
0x18014d907  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18014d90c  mov     [rsp+270h+var_248], r13b; char
0x18014d911  xor     r9d, r9d; unsigned __int8
0x18014d914  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x18014d919  movzx   r8d, word ptr [r8+r12*8]; unsigned __int16
0x18014d91e  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18014d923  mov     ebx, eax
0x18014d925  test    eax, eax
0x18014d927  js      loc_18014DCE3
0x18014d92d  mov     rax, [rdi+0D8h]
0x18014d934  lea     rdx, aAlg; "alg"
0x18014d93b  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x18014d940  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18014d945  xor     r9d, r9d; unsigned __int8
0x18014d948  movzx   r8d, word ptr [rax+r12*8]; unsigned int
0x18014d94d  lea     rax, ?st_TPMW8A_ALGORITHM@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8A_ALGORITHM
0x18014d954  mov     [rsp+270h+var_250], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x18014d959  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18014d95e  mov     ebx, eax
0x18014d960  test    eax, eax
0x18014d962  js      loc_18014DCE3
0x18014d968  inc     r14d
0x18014d96b  jmp     loc_18014D8C1
0x18014d970  mov     r14d, r13d
0x18014d973  lea     r15, ?st_TPMW8_ALG@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_ALG
0x18014d97a  cmp     r14d, [rdi+0D4h]
0x18014d981  jnb     loc_18014DCE3
0x18014d987  mov     r9, rsi
0x18014d98a  mov     dword ptr [rsp+270h+var_250], r14d
0x18014d98f  lea     r8, aSpcrsD; "%spcrs[%d]."
0x18014d996  mov     edx, 100h; unsigned __int64
0x18014d99b  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18014d9a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18014d9a5  mov     ebx, eax
0x18014d9a7  test    eax, eax
0x18014d9a9  js      loc_18014DCE3
0x18014d9af  mov     eax, r14d
0x18014d9b2  lea     rdx, aHashalg; "hashAlg"
0x18014d9b9  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x18014d9be  xor     r9d, r9d; unsigned __int8
0x18014d9c1  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x18014d9c6  lea     rcx, [rax+rax*8]
0x18014d9ca  mov     rax, [rdi+100h]
0x18014d9d1  movzx   r8d, word ptr [rax+rcx*8+38h]; unsigned int
0x18014d9d7  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18014d9dc  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18014d9e1  mov     ebx, eax
0x18014d9e3  test    eax, eax
0x18014d9e5  js      loc_18014DCE3
0x18014d9eb  add     r14d, r12d
0x18014d9ee  jmp     short loc_18014D97A
0x18014d9f0  sub     eax, 6
0x18014d9f3  jz      loc_18014DC36
0x18014d9f9  sub     eax, r12d
0x18014d9fc  jz      loc_18014DB89
0x18014da02  sub     eax, r12d
0x18014da05  jz      loc_18014DB0E
0x18014da0b  sub     eax, r12d
0x18014da0e  jz      short loc_18014DA68
0x18014da10  cmp     eax, 0F7h
0x18014da15  jz      short loc_18014DA21
0x18014da17  mov     eax, 80004001h
0x18014da1c  jmp     loc_18014DCE5
0x18014da21  mov     r9, rsi
0x18014da24  lea     r8, aSvendorpropert; "%svendorProperties."
0x18014da2b  mov     edx, 100h; unsigned __int64
0x18014da30  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18014da35  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18014da3a  mov     ebx, eax
0x18014da3c  test    eax, eax
0x18014da3e  js      loc_18014DCE3
0x18014da44  mov     r9d, [rdi+130h]; unsigned int
0x18014da4b  lea     rdx, aVendorspecific_1; "vendorSpecificData"
0x18014da52  mov     r8, [rdi+128h]; unsigned __int8 *
0x18014da59  mov     rcx, rsi; unsigned __int16 *
0x18014da5c  call    ?TraceBufferValue@@YAJPEAG0PEAEI@Z; TraceBufferValue(ushort *,ushort *,uchar *,uint)
0x18014da61  mov     ebx, eax
0x18014da63  jmp     loc_18014DCE3
0x18014da68  mov     r14d, r13d
0x18014da6b  cmp     r14d, [rdi+0D4h]
0x18014da72  jnb     loc_18014DCE3
0x18014da78  mov     r9, rsi
0x18014da7b  mov     dword ptr [rsp+270h+var_250], r14d
0x18014da80  lea     r8, aSauthpoliciesD; "%sauthPolicies[%d]."
0x18014da87  mov     edx, 100h; unsigned __int64
0x18014da8c  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18014da91  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18014da96  mov     ebx, eax
0x18014da98  test    eax, eax
0x18014da9a  js      loc_18014DCE3
0x18014daa0  mov     r8, [rdi+120h]
0x18014daa7  lea     rdx, aHandle; "handle"
  ... truncated ...
```
