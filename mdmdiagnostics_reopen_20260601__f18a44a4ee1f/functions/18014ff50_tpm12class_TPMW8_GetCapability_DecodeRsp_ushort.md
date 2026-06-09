# tpm12class::TPMW8_GetCapability::DecodeRsp(ushort *)

- ea: `0x18014ff50`
- end: `0x180150700`
- name: `?DecodeRsp@TPMW8_GetCapability@tpm12class@@UEAAJPEAG@Z`
- size: `1968`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_GetCapability *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800edd78`
- `0x18014de40`
- `0x18014ff50`
- `0x180153c74`
- `0x180154138`
- `0x1801541e4`
- `0x180154938`
- `0x180154c34`
- `0x180154f2c`
- `0x180193010`

## string_xrefs

- `0x180150105`: `commandCode`
- `0x18015017f`: `commandCode`
- `0x1801501f9`: `commandCode`
- `0x1801500de`: `%sauditCommands[%d].`
- `0x180150158`: `%sppCommands[%d].`
- `0x1801501d2`: `%scommands[%d].`

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
0x18014ff50  mov     [rsp-8+arg_10], rbx
0x18014ff55  push    rbp
0x18014ff56  push    rsi
0x18014ff57  push    rdi
0x18014ff58  push    r12
0x18014ff5a  push    r13
0x18014ff5c  push    r14
0x18014ff5e  push    r15
0x18014ff60  lea     rbp, [rsp-140h]
0x18014ff68  sub     rsp, 240h
0x18014ff6f  mov     rax, cs:__security_cookie
0x18014ff76  xor     rax, rsp
0x18014ff79  mov     [rbp+170h+var_40], rax
0x18014ff80  mov     rsi, rdx
0x18014ff83  mov     rdi, rcx
0x18014ff86  xor     r13d, r13d
0x18014ff89  lea     rcx, [rsp+270h+var_23E]; void *
0x18014ff8e  xor     edx, edx; Val
0x18014ff90  mov     [rsp+270h+var_240], r13w
0x18014ff96  mov     r8d, 1FEh; Size
0x18014ff9c  mov     ebx, r13d
0x18014ff9f  call    memset_0
0x18014ffa4  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x18014ffa9  test    al, al
0x18014ffab  jz      loc_1801506D3
0x18014ffb1  mov     rdx, rsi; unsigned __int16 *
0x18014ffb4  mov     rcx, rdi; this
0x18014ffb7  call    ?DecodeRsp@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeRsp(ushort *)
0x18014ffbc  mov     ebx, eax
0x18014ffbe  test    eax, eax
0x18014ffc0  js      loc_1801506D3
0x18014ffc6  lea     rcx, aTpm2Getcapabil; "--TPM2_GetCapability: Parameters-------"...
0x18014ffcd  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x18014ffd2  mov     ebx, eax
0x18014ffd4  test    eax, eax
0x18014ffd6  js      loc_1801506D3
0x18014ffdc  mov     r8b, [rdi+0CCh]; unsigned __int8
0x18014ffe3  lea     rax, ?st_TPMW8I_YES_NO@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8I_YES_NO
0x18014ffea  mov     [rsp+270h+var_248], r13b; char
0x18014ffef  lea     rdx, aMoredata; "moreData"
0x18014fff6  mov     rcx, rsi; unsigned __int16 *
0x18014fff9  mov     [rsp+270h+var_250], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x18014fffe  call    ?TraceUINT8Value@@YAJPEAG0EEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT8Value(ushort *,ushort *,uchar,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x180150003  mov     ebx, eax
0x180150005  test    eax, eax
0x180150007  js      loc_1801506D3
0x18015000d  mov     r8d, [rdi+0D0h]; unsigned int
0x180150014  lea     rax, ?st_TPMW8_CAP@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CAP
0x18015001b  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x180150020  lea     rdx, aCapability; "capability"
0x180150027  xor     r9d, r9d; unsigned __int8
0x18015002a  mov     [rsp+270h+var_250], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x18015002f  mov     rcx, rsi; unsigned __int16 *
0x180150032  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x180150037  mov     ebx, eax
0x180150039  test    eax, eax
0x18015003b  js      loc_1801506D3
0x180150041  cmp     dword ptr [rdi+0D0h], 100h
0x18015004b  lea     r12d, [r13+1]
0x18015004f  jz      short loc_18015007E
0x180150051  mov     r8d, [rdi+0D4h]; unsigned int
0x180150058  lea     rdx, aCount; "count"
0x18015005f  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x180150064  mov     r9b, r12b; unsigned __int8
0x180150067  mov     rcx, rsi; unsigned __int16 *
0x18015006a  mov     [rsp+270h+var_250], r13; struct TPM_SYMBOLTABLE_ENTRY *
0x18015006f  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x180150074  mov     ebx, eax
0x180150076  test    eax, eax
0x180150078  js      loc_1801506D3
0x18015007e  mov     eax, [rdi+0D0h]
0x180150084  cmp     eax, 5
0x180150087  ja      loc_1801503E0
0x18015008d  jz      loc_180150360
0x180150093  test    eax, eax
0x180150095  jz      loc_1801502A7
0x18015009b  sub     eax, r12d
0x18015009e  jz      loc_18015022D
0x1801500a4  sub     eax, r12d
0x1801500a7  jz      loc_1801501B3
0x1801500ad  sub     eax, r12d
0x1801500b0  jz      loc_180150139
0x1801500b6  cmp     eax, r12d
0x1801500b9  jnz     loc_180150407
0x1801500bf  mov     r14d, r13d
0x1801500c2  lea     r15, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x1801500c9  cmp     r14d, [rdi+0D4h]
0x1801500d0  jnb     loc_1801506D3
0x1801500d6  mov     r9, rsi
0x1801500d9  mov     dword ptr [rsp+270h+var_250], r14d
0x1801500de  lea     r8, aSauditcommands; "%sauditCommands[%d]."
0x1801500e5  mov     edx, 100h; unsigned __int64
0x1801500ea  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1801500ef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801500f4  mov     ebx, eax
0x1801500f6  test    eax, eax
0x1801500f8  js      loc_1801506D3
0x1801500fe  mov     r8, [rdi+0F8h]
0x180150105  lea     rdx, aCommandcode; "commandCode"
0x18015010c  mov     eax, r14d
0x18015010f  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180150114  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x180150119  xor     r9d, r9d; unsigned __int8
0x18015011c  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x180150121  mov     r8d, [r8+rax*4]; unsigned int
0x180150125  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18015012a  mov     ebx, eax
0x18015012c  test    eax, eax
0x18015012e  js      loc_1801506D3
0x180150134  add     r14d, r12d
0x180150137  jmp     short loc_1801500C9
0x180150139  mov     r14d, r13d
0x18015013c  lea     r15, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x180150143  cmp     r14d, [rdi+0D4h]
0x18015014a  jnb     loc_1801506D3
0x180150150  mov     r9, rsi
0x180150153  mov     dword ptr [rsp+270h+var_250], r14d
0x180150158  lea     r8, aSppcommandsD; "%sppCommands[%d]."
0x18015015f  mov     edx, 100h; unsigned __int64
0x180150164  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180150169  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18015016e  mov     ebx, eax
0x180150170  test    eax, eax
0x180150172  js      loc_1801506D3
0x180150178  mov     r8, [rdi+0F0h]
0x18015017f  lea     rdx, aCommandcode; "commandCode"
0x180150186  mov     eax, r14d
0x180150189  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18015018e  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x180150193  xor     r9d, r9d; unsigned __int8
0x180150196  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x18015019b  mov     r8d, [r8+rax*4]; unsigned int
0x18015019f  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1801501a4  mov     ebx, eax
0x1801501a6  test    eax, eax
0x1801501a8  js      loc_1801506D3
0x1801501ae  add     r14d, r12d
0x1801501b1  jmp     short loc_180150143
0x1801501b3  mov     r14d, r13d
0x1801501b6  lea     r15, ?st_TPMW8_CC@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_CC
0x1801501bd  cmp     r14d, [rdi+0D4h]
0x1801501c4  jnb     loc_1801506D3
0x1801501ca  mov     r9, rsi
0x1801501cd  mov     dword ptr [rsp+270h+var_250], r14d
0x1801501d2  lea     r8, aScommandsD; "%scommands[%d]."
0x1801501d9  mov     edx, 100h; unsigned __int64
0x1801501de  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1801501e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801501e8  mov     ebx, eax
0x1801501ea  test    eax, eax
0x1801501ec  js      loc_1801506D3
0x1801501f2  mov     r8, [rdi+0E8h]
0x1801501f9  lea     rdx, aCommandcode; "commandCode"
0x180150200  mov     eax, r14d
0x180150203  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180150208  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x18015020d  xor     r9d, r9d; unsigned __int8
0x180150210  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x180150215  mov     r8d, [r8+rax*4]; unsigned int
0x180150219  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18015021e  mov     ebx, eax
0x180150220  test    eax, eax
0x180150222  js      loc_1801506D3
0x180150228  add     r14d, r12d
0x18015022b  jmp     short loc_1801501BD
0x18015022d  mov     r14d, r13d
0x180150230  cmp     r14d, [rdi+0D4h]
0x180150237  jnb     loc_1801506D3
0x18015023d  mov     r9, rsi
0x180150240  mov     dword ptr [rsp+270h+var_250], r14d
0x180150245  lea     r8, aShandlesD; "%shandles[%d]."
0x18015024c  mov     edx, 100h; unsigned __int64
0x180150251  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180150256  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18015025b  mov     ebx, eax
0x18015025d  test    eax, eax
0x18015025f  js      loc_1801506D3
0x180150265  mov     r8, [rdi+0E0h]
0x18015026c  lea     rcx, ?st_TPMW8_RH@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_RH
0x180150273  mov     eax, r14d
0x180150276  lea     rdx, aHandle; "handle"
0x18015027d  mov     [rsp+270h+var_248], r12b; unsigned __int8
0x180150282  xor     r9d, r9d; unsigned __int8
0x180150285  mov     [rsp+270h+var_250], rcx; struct TPM_SYMBOLTABLE_ENTRY *
0x18015028a  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18015028f  mov     r8d, [r8+rax*4]; unsigned int
0x180150293  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x180150298  mov     ebx, eax
0x18015029a  test    eax, eax
0x18015029c  js      loc_1801506D3
0x1801502a2  add     r14d, r12d
0x1801502a5  jmp     short loc_180150230
0x1801502a7  mov     r14d, r13d
0x1801502aa  lea     r15, ?st_TPMW8_ALG@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_ALG
0x1801502b1  cmp     r14d, [rdi+0D4h]
0x1801502b8  jnb     loc_1801506D3
0x1801502be  mov     r9, rsi
0x1801502c1  mov     dword ptr [rsp+270h+var_250], r14d
0x1801502c6  lea     r8, aSalgorithmsD; "%salgorithms[%d]."
0x1801502cd  mov     edx, 100h; unsigned __int64
0x1801502d2  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1801502d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801502dc  mov     ebx, eax
0x1801502de  test    eax, eax
0x1801502e0  js      loc_1801506D3
0x1801502e6  mov     r8, [rdi+0D8h]
0x1801502ed  lea     rdx, aAlg; "alg"
0x1801502f4  mov     r12d, r14d
0x1801502f7  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1801502fc  mov     [rsp+270h+var_248], r13b; char
0x180150301  xor     r9d, r9d; unsigned __int8
0x180150304  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x180150309  movzx   r8d, word ptr [r8+r12*8]; unsigned __int16
0x18015030e  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x180150313  mov     ebx, eax
0x180150315  test    eax, eax
0x180150317  js      loc_1801506D3
0x18015031d  mov     rax, [rdi+0D8h]
0x180150324  lea     rdx, aAlg; "alg"
0x18015032b  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x180150330  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180150335  xor     r9d, r9d; unsigned __int8
0x180150338  movzx   r8d, word ptr [rax+r12*8]; unsigned int
0x18015033d  lea     rax, ?st_TPMW8A_ALGORITHM@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8A_ALGORITHM
0x180150344  mov     [rsp+270h+var_250], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x180150349  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x18015034e  mov     ebx, eax
0x180150350  test    eax, eax
0x180150352  js      loc_1801506D3
0x180150358  inc     r14d
0x18015035b  jmp     loc_1801502B1
0x180150360  mov     r14d, r13d
0x180150363  lea     r15, ?st_TPMW8_ALG@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPMW8_ALG
0x18015036a  cmp     r14d, [rdi+0D4h]
0x180150371  jnb     loc_1801506D3
0x180150377  mov     r9, rsi
0x18015037a  mov     dword ptr [rsp+270h+var_250], r14d
0x18015037f  lea     r8, aSpcrsD; "%spcrs[%d]."
0x180150386  mov     edx, 100h; unsigned __int64
0x18015038b  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180150390  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180150395  mov     ebx, eax
0x180150397  test    eax, eax
0x180150399  js      loc_1801506D3
0x18015039f  mov     eax, r14d
0x1801503a2  lea     rdx, aHashalg; "hashAlg"
0x1801503a9  mov     [rsp+270h+var_248], r13b; unsigned __int8
0x1801503ae  xor     r9d, r9d; unsigned __int8
0x1801503b1  mov     [rsp+270h+var_250], r15; struct TPM_SYMBOLTABLE_ENTRY *
0x1801503b6  lea     rcx, [rax+rax*8]
0x1801503ba  mov     rax, [rdi+100h]
0x1801503c1  movzx   r8d, word ptr [rax+rcx*8+38h]; unsigned int
0x1801503c7  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x1801503cc  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1801503d1  mov     ebx, eax
0x1801503d3  test    eax, eax
0x1801503d5  js      loc_1801506D3
0x1801503db  add     r14d, r12d
0x1801503de  jmp     short loc_18015036A
0x1801503e0  sub     eax, 6
0x1801503e3  jz      loc_180150626
0x1801503e9  sub     eax, r12d
0x1801503ec  jz      loc_180150579
0x1801503f2  sub     eax, r12d
0x1801503f5  jz      loc_1801504FE
0x1801503fb  sub     eax, r12d
0x1801503fe  jz      short loc_180150458
0x180150400  cmp     eax, 0F7h
0x180150405  jz      short loc_180150411
0x180150407  mov     eax, 80004001h
0x18015040c  jmp     loc_1801506D5
0x180150411  mov     r9, rsi
0x180150414  lea     r8, aSvendorpropert; "%svendorProperties."
0x18015041b  mov     edx, 100h; unsigned __int64
0x180150420  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180150425  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18015042a  mov     ebx, eax
0x18015042c  test    eax, eax
0x18015042e  js      loc_1801506D3
0x180150434  mov     r9d, [rdi+130h]; unsigned int
0x18015043b  lea     rdx, aVendorspecific_1; "vendorSpecificData"
0x180150442  mov     r8, [rdi+128h]; unsigned __int8 *
0x180150449  mov     rcx, rsi; unsigned __int16 *
0x18015044c  call    ?TraceBufferValue@@YAJPEAG0PEAEI@Z; TraceBufferValue(ushort *,ushort *,uchar *,uint)
0x180150451  mov     ebx, eax
0x180150453  jmp     loc_1801506D3
0x180150458  mov     r14d, r13d
0x18015045b  cmp     r14d, [rdi+0D4h]
0x180150462  jnb     loc_1801506D3
0x180150468  mov     r9, rsi
0x18015046b  mov     dword ptr [rsp+270h+var_250], r14d
0x180150470  lea     r8, aSauthpoliciesD; "%sauthPolicies[%d]."
0x180150477  mov     edx, 100h; unsigned __int64
0x18015047c  lea     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x180150481  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180150486  mov     ebx, eax
0x180150488  test    eax, eax
0x18015048a  js      loc_1801506D3
0x180150490  mov     r8, [rdi+120h]
0x180150497  lea     rdx, aHandle; "handle"
  ... truncated ...
```
