# IkeOptionalConstructAuthipInitiatorKeDhGroupVendorId

- ea: `0x180046510`
- end: `0x180046a9d`
- name: `IkeOptionalConstructAuthipInitiatorKeDhGroupVendorId`
- size: `1421`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180043270`
- `0x1800e7294`

## callees

- `0x180008388`
- `0x18001fc40`
- `0x180045dd0`
- `0x180046510`
- `0x180050850`
- `0x18005bce4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800465aa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800465ef`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046727`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046760`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800467be`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046803`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046945`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004698a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800465aa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800465ef`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046727`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046760`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800467be`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046803`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046945`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004698a`
- `ntdll!EtwEventWriteTransfer` at `0x1800466c6`
- `ntdll!EtwEventWriteTransfer` at `0x1800468d9`
- `ntdll!EtwEventWriteTransfer` at `0x180046a5c`
- `ntdll!EtwEventWriteTransfer` at `0x1800466c6`
- `ntdll!EtwEventWriteTransfer` at `0x1800468d9`
- `ntdll!EtwEventWriteTransfer` at `0x180046a5c`

## pseudocode

```c
__int64 __fastcall IkeOptionalConstructAuthipInitiatorKeDhGroupVendorId(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // r14
  __int64 v7; // rbx
  LPCRITICAL_SECTION v8; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v11; // rcx
  DWORD v12; // ecx
  char *v13; // rax
  const WCHAR *v14; // rdx
  __int64 v15; // rax
  bool v16; // zf
  int v17; // eax
  unsigned int v18; // esi
  _QWORD *v19; // rcx
  LPCRITICAL_SECTION v20; // rdx
  DWORD v21; // eax
  LPVOID v22; // rax
  LPVOID v23; // r8
  __int64 v24; // rdi
  DWORD v25; // eax
  __int64 *v26; // rax
  __int64 v27; // r9
  LPCRITICAL_SECTION v28; // rax
  DWORD v29; // ecx
  __int64 *v30; // rax
  __int64 v31; // rcx
  DWORD v32; // ecx
  char *v33; // rax
  const WCHAR *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  LPCRITICAL_SECTION v37; // rax
  DWORD v38; // ecx
  __int64 *v39; // rax
  __int64 v40; // rcx
  DWORD v41; // ecx
  char *v42; // rax
  const WCHAR *v43; // rdx
  int v44; // ebx
  __int64 v46; // [rsp+28h] [rbp-61h]
  unsigned int v47; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v48; // [rsp+34h] [rbp-55h] BYREF
  __int64 v49; // [rsp+38h] [rbp-51h] BYREF
  int v50; // [rsp+40h] [rbp-49h] BYREF
  int v51; // [rsp+44h] [rbp-45h]
  __int64 v52; // [rsp+48h] [rbp-41h]
  char *v53; // [rsp+50h] [rbp-39h] BYREF
  int v54; // [rsp+58h] [rbp-31h]
  int v55; // [rsp+5Ch] [rbp-2Dh]
  int *v56; // [rsp+60h] [rbp-29h]
  int v57; // [rsp+68h] [rbp-21h]
  int v58; // [rsp+6Ch] [rbp-1Dh]
  __int64 *v59; // [rsp+70h] [rbp-19h]
  __int64 v60; // [rsp+78h] [rbp-11h]
  const WCHAR *v61; // [rsp+80h] [rbp-9h]
  int v62; // [rsp+88h] [rbp-1h]
  int v63; // [rsp+8Ch] [rbp+3h]
  unsigned int *v64; // [rsp+90h] [rbp+7h]
  __int64 v65; // [rsp+98h] [rbp+Fh]

  v47 = 0;
  v6 = 0;
  v7 = -1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v8 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v8 = gIkeExtGlobals;
LABEL_9:
    v11 = 0;
    goto LABEL_10;
  }
  v11 = *Value;
  v8 = gIkeExtGlobals;
LABEL_10:
  v49 = v11;
  v59 = &v49;
  v60 = 8;
  if ( !v8 )
    goto LABEL_18;
  v12 = (DWORD)v8[86].LockSemaphore;
  if ( v12 == -1 )
    goto LABEL_18;
  v13 = (char *)TlsGetValue(v12);
  v14 = (const WCHAR *)(v13 + 8);
  if ( !v13 )
    v14 = 0;
  if ( v14 )
  {
    v15 = -1;
    do
      v16 = v14[++v15] == 0;
    while ( !v16 );
    v17 = 2 * v15 + 2;
  }
  else
  {
LABEL_18:
    v14 = &LocaleName;
    v17 = 2;
  }
  v62 = v17;
  v51 = 5;
  v53 = off_180173280;
  v61 = v14;
  v63 = 0;
  v64 = (unsigned int *)"IkeOptionalConstructAuthipInitiatorKeDhGroupVendorId";
  v65 = 53;
  v50 = 184549376;
  v52 = 1;
  v54 = *(unsigned __int16 *)off_180173280;
  v56 = &dword_180166EA4;
  v55 = 2;
  v57 = 45;
  v58 = 1;
  v48 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EtwEventWriteTransfer(qword_180173298, &v50, 0, 0, 5, &v53);
LABEL_20:
  IkeInitiatorFindDHGroupForKEPayload(a4, &v47);
  v18 = v47;
  if ( v47 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v20 = gIkeExtGlobals;
      if ( !gIkeExtGlobals || (v21 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v21 == -1) )
      {
        v23 = 0;
      }
      else
      {
        v22 = TlsGetValue(v21);
        v19 = WPP_GLOBAL_Control;
        v23 = v22;
        v20 = gIkeExtGlobals;
      }
      v24 = (__int64)v23 + 8;
      if ( !v23 )
        v24 = 0;
      if ( v20
        && (v25 = (DWORD)v20[86].LockSemaphore, v25 != -1)
        && (v26 = (__int64 *)TlsGetValue(v25), v19 = WPP_GLOBAL_Control, v26) )
      {
        v27 = *v26;
      }
      else
      {
        LODWORD(v27) = 0;
      }
      LODWORD(v46) = v18;
      WPP_SF_iSL(v19[2], 21, (unsigned int)WPP_654feddb4d903c5f7d7e848d4643eb5d_Traceguids, v27, v24, v46);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
      goto LABEL_53;
    v28 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v29 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v29 != -1 )
      {
        v30 = (__int64 *)TlsGetValue(v29);
        if ( v30 )
        {
          v31 = *v30;
          v28 = gIkeExtGlobals;
LABEL_43:
          v49 = v31;
          v59 = &v49;
          v60 = 8;
          if ( !v28 )
            goto LABEL_51;
          v32 = (DWORD)v28[86].LockSemaphore;
          if ( v32 == -1 )
            goto LABEL_51;
          v33 = (char *)TlsGetValue(v32);
          v34 = (const WCHAR *)(v33 + 8);
          if ( !v33 )
            v34 = 0;
          if ( v34 )
          {
            v35 = -1;
            do
              v16 = v34[++v35] == 0;
            while ( !v16 );
            v36 = 2 * v35 + 2;
          }
          else
          {
LABEL_51:
            v34 = &LocaleName;
            v36 = 2;
          }
          v62 = v36;
          v61 = v34;
          v64 = &v48;
          v51 = 4;
          v53 = off_180173280;
          v63 = 0;
          v48 = v18;
          v65 = 4;
          v50 = 184549376;
          v52 = 0;
          v54 = *(unsigned __int16 *)off_180173280;
          v56 = (int *)&unk_180164590;
          v55 = 2;
          v57 = 77;
          v58 = 1;
          v47 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v50, 0, 0, 5, &v53);
LABEL_53:
          v6 = IkeConstructVendor(a1, 11, 0, 0, v18);
          goto LABEL_54;
        }
        v28 = gIkeExtGlobals;
      }
    }
    v31 = 0;
    goto LABEL_43;
  }
LABEL_54:
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    return IkeReturnError(v6, "IkeOptionalConstructAuthipInitiatorKeDhGroupVendorId");
  v37 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_62;
  v38 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v38 == -1 )
    goto LABEL_62;
  v39 = (__int64 *)TlsGetValue(v38);
  if ( !v39 )
  {
    v37 = gIkeExtGlobals;
LABEL_62:
    v40 = 0;
    goto LABEL_63;
  }
  v40 = *v39;
  v37 = gIkeExtGlobals;
LABEL_63:
  v49 = v40;
  v59 = &v49;
  v60 = 8;
  if ( !v37 )
    goto LABEL_70;
  v41 = (DWORD)v37[86].LockSemaphore;
  if ( v41 == -1 )
    goto LABEL_70;
  v42 = (char *)TlsGetValue(v41);
  v43 = (const WCHAR *)(v42 + 8);
  if ( !v42 )
    v43 = 0;
  if ( v43 )
  {
    do
      v16 = v43[++v7] == 0;
    while ( !v16 );
    v44 = 2 * v7 + 2;
  }
  else
  {
LABEL_70:
    v43 = &LocaleName;
    v44 = 2;
  }
  v51 = 5;
  v53 = off_180173280;
  v62 = v44;
  v61 = v43;
  v63 = 0;
  v64 = (unsigned int *)"IkeOptionalConstructAuthipInitiatorKeDhGroupVendorId";
  v65 = 53;
  v50 = 184549376;
  v52 = 1;
  v54 = *(unsigned __int16 *)off_180173280;
  v56 = (int *)byte_180166E6B;
  v55 = 2;
  v57 = 45;
  v58 = 1;
  v48 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EtwEventWriteTransfer(qword_180173298, &v50, 0, 0, 5, &v53);
  return IkeReturnError(v6, "IkeOptionalConstructAuthipInitiatorKeDhGroupVendorId");
}

```

## disassembly

```asm
0x180046510  mov     [rsp-8+arg_8], rbx
0x180046515  push    rbp
0x180046516  push    rsi
0x180046517  push    rdi
0x180046518  push    r12
0x18004651a  push    r13
0x18004651c  push    r14
0x18004651e  push    r15
0x180046520  lea     rbp, [rsp-27h]
0x180046525  sub     rsp, 0B0h
0x18004652c  mov     rax, cs:__security_cookie
0x180046533  xor     rax, rsp
0x180046536  mov     [rbp+57h+var_40], rax
0x18004653a  mov     eax, cs:dword_180173278
0x180046540  lea     rsi, aIkeoptionalcon_13; "IkeOptionalConstructAuthipInitiatorKeDh"...
0x180046547  xor     r13d, r13d
0x18004654a  lea     r12, _TraceLoggingMetadataEnd
0x180046551  mov     [rbp+57h+var_B0], r13d
0x180046555  mov     rdi, r9
0x180046558  mov     r15, rcx
0x18004655b  mov     r14d, r13d
0x18004655e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180046565  cmp     eax, 5
0x180046568  jbe     loc_1800466CC
0x18004656e  mov     rcx, cs:qword_180173290
0x180046575  mov     rax, cs:qword_180173288
0x18004657c  test    al, 1
0x18004657e  jz      loc_1800466CC
0x180046584  mov     rax, rcx
0x180046587  and     eax, 1
0x18004658a  cmp     rax, rcx
0x18004658d  jnz     loc_1800466CC
0x180046593  mov     rax, cs:gIkeExtGlobals
0x18004659a  test    rax, rax
0x18004659d  jz      short loc_1800465C8
0x18004659f  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800465a5  cmp     ecx, 0FFFFFFFFh
0x1800465a8  jz      short loc_1800465C8
0x1800465aa  call    cs:__imp_TlsGetValue
0x1800465b0  test    rax, rax
0x1800465b3  jz      short loc_1800465C1
0x1800465b5  mov     rcx, [rax]
0x1800465b8  mov     rax, cs:gIkeExtGlobals
0x1800465bf  jmp     short loc_1800465CB
0x1800465c1  mov     rax, cs:gIkeExtGlobals
0x1800465c8  mov     rcx, r13
0x1800465cb  mov     [rbp+57h+var_A8], rcx
0x1800465cf  lea     rcx, [rbp+57h+var_A8]
0x1800465d3  mov     [rbp+57h+var_70], rcx
0x1800465d7  mov     [rbp+57h+var_68], 8
0x1800465df  test    rax, rax
0x1800465e2  jz      short loc_180046625
0x1800465e4  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800465ea  cmp     ecx, 0FFFFFFFFh
0x1800465ed  jz      short loc_180046625
0x1800465ef  call    cs:__imp_TlsGetValue
0x1800465f5  test    rax, rax
0x1800465f8  lea     rdx, [rax+8]
0x1800465fc  cmovz   rdx, r13
0x180046600  test    rdx, rdx
0x180046603  jz      short loc_180046625
0x180046605  mov     rax, rbx
0x180046608  nop     dword ptr [rax+rax+00000000h]
0x180046610  cmp     [rdx+rax*2+2], r13w
0x180046616  lea     rax, [rax+1]
0x18004661a  jnz     short loc_180046610
0x18004661c  lea     eax, ds:2[rax*2]
0x180046623  jmp     short loc_180046631
0x180046625  lea     rdx, LocaleName
0x18004662c  mov     eax, 2
0x180046631  mov     [rbp+57h+var_58], eax
0x180046634  lea     rcx, _TraceLoggingMetadata
0x18004663b  movzx   eax, cs:word_180166E9A
0x180046642  xor     r9d, r9d
0x180046645  mov     [rbp+57h+var_9C], eax
0x180046648  xor     r8d, r8d
0x18004664b  mov     rax, cs:off_180173280
0x180046652  mov     [rbp+57h+var_90], rax
0x180046656  mov     [rbp+57h+var_60], rdx
0x18004665a  lea     rdx, [rbp+57h+var_A0]
0x18004665e  mov     [rbp+57h+var_54], r13d
0x180046662  mov     [rbp+57h+var_50], rsi
0x180046666  mov     [rbp+57h+var_48], 35h ; '5'
0x18004666e  mov     [rbp+57h+var_A0], 0B000000h
0x180046675  mov     [rbp+57h+var_98], 1
0x18004667d  movzx   eax, word ptr [rax]
0x180046680  mov     [rbp+57h+var_88], eax
0x180046683  lea     rax, dword_180166EA4
0x18004668a  mov     [rbp+57h+var_80], rax
0x18004668e  mov     rax, r12
0x180046691  sub     eax, ecx
0x180046693  mov     [rbp+57h+var_84], 2
0x18004669a  mov     [rbp+57h+var_78], 2Dh ; '-'
0x1800466a1  mov     [rbp+57h+var_74], 1
0x1800466a8  mov     [rbp+57h+var_AC], eax
0x1800466ab  mov     eax, [rbp+57h+var_AC]
0x1800466ae  mov     rcx, cs:qword_180173298
0x1800466b5  lea     rax, [rbp+57h+var_90]
0x1800466b9  mov     [rsp+0E0h+var_B8], rax
0x1800466be  mov     dword ptr [rsp+0E0h+var_C0], 5
0x1800466c6  call    cs:__imp_EtwEventWriteTransfer
0x1800466cc  lea     rdx, [rbp+57h+var_B0]
0x1800466d0  mov     rcx, rdi
0x1800466d3  call    IkeInitiatorFindDHGroupForKEPayload
0x1800466d8  mov     esi, [rbp+57h+var_B0]
0x1800466db  test    esi, esi
0x1800466dd  jz      loc_1800468F9
0x1800466e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800466ea  lea     rax, WPP_GLOBAL_Control
0x1800466f1  cmp     rcx, rax
0x1800466f4  jz      loc_180046798
0x1800466fa  cmp     byte ptr [rcx+19h], 4
0x1800466fe  jb      loc_180046798
0x180046704  test    byte ptr [rcx+1Ch], 10h
0x180046708  jz      loc_180046798
0x18004670e  mov     rdx, cs:gIkeExtGlobals
0x180046715  test    rdx, rdx
0x180046718  jz      short loc_180046740
0x18004671a  mov     eax, [rdx+0D88h]
0x180046720  cmp     eax, 0FFFFFFFFh
0x180046723  jz      short loc_180046740
0x180046725  mov     ecx, eax; dwTlsIndex
0x180046727  call    cs:__imp_TlsGetValue
0x18004672d  mov     rcx, cs:WPP_GLOBAL_Control
0x180046734  mov     r8, rax
0x180046737  mov     rdx, cs:gIkeExtGlobals
0x18004673e  jmp     short loc_180046743
0x180046740  mov     r8, r13
0x180046743  test    r8, r8
0x180046746  lea     rdi, [r8+8]
0x18004674a  cmovz   rdi, r13
0x18004674e  test    rdx, rdx
0x180046751  jz      short loc_180046777
0x180046753  mov     eax, [rdx+0D88h]
0x180046759  cmp     eax, 0FFFFFFFFh
0x18004675c  jz      short loc_180046777
0x18004675e  mov     ecx, eax; dwTlsIndex
0x180046760  call    cs:__imp_TlsGetValue
0x180046766  mov     rcx, cs:WPP_GLOBAL_Control
0x18004676d  test    rax, rax
0x180046770  jz      short loc_180046777
0x180046772  mov     r9, [rax]
0x180046775  jmp     short loc_18004677A
0x180046777  mov     r9, r13
0x18004677a  mov     rcx, [rcx+10h]
0x18004677e  lea     r8, WPP_654feddb4d903c5f7d7e848d4643eb5d_Traceguids
0x180046785  mov     edx, 15h
0x18004678a  mov     dword ptr [rsp+0E0h+var_B8], esi
0x18004678e  mov     [rsp+0E0h+var_C0], rdi
0x180046793  call    WPP_SF_iSL
0x180046798  mov     eax, cs:dword_180173278
0x18004679e  cmp     eax, 4
0x1800467a1  jbe     loc_1800468DF
0x1800467a7  mov     rax, cs:gIkeExtGlobals
0x1800467ae  test    rax, rax
0x1800467b1  jz      short loc_1800467DC
0x1800467b3  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800467b9  cmp     ecx, 0FFFFFFFFh
0x1800467bc  jz      short loc_1800467DC
0x1800467be  call    cs:__imp_TlsGetValue
0x1800467c4  test    rax, rax
0x1800467c7  jz      short loc_1800467D5
0x1800467c9  mov     rcx, [rax]
0x1800467cc  mov     rax, cs:gIkeExtGlobals
0x1800467d3  jmp     short loc_1800467DF
0x1800467d5  mov     rax, cs:gIkeExtGlobals
0x1800467dc  mov     rcx, r13
0x1800467df  mov     [rbp+57h+var_A8], rcx
0x1800467e3  lea     rcx, [rbp+57h+var_A8]
0x1800467e7  mov     [rbp+57h+var_70], rcx
0x1800467eb  mov     [rbp+57h+var_68], 8
0x1800467f3  test    rax, rax
0x1800467f6  jz      short loc_180046835
0x1800467f8  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800467fe  cmp     ecx, 0FFFFFFFFh
0x180046801  jz      short loc_180046835
0x180046803  call    cs:__imp_TlsGetValue
0x180046809  test    rax, rax
0x18004680c  lea     rdx, [rax+8]
0x180046810  cmovz   rdx, r13
0x180046814  test    rdx, rdx
0x180046817  jz      short loc_180046835
0x180046819  mov     rax, rbx
0x18004681c  nop     dword ptr [rax+00h]
0x180046820  cmp     [rdx+rax*2+2], r13w
0x180046826  lea     rax, [rax+1]
0x18004682a  jnz     short loc_180046820
0x18004682c  lea     eax, ds:2[rax*2]
0x180046833  jmp     short loc_180046841
0x180046835  lea     rdx, LocaleName
0x18004683c  mov     eax, 2
0x180046841  mov     [rbp+57h+var_58], eax
0x180046844  lea     rcx, _TraceLoggingMetadata
0x18004684b  mov     [rbp+57h+var_60], rdx
0x18004684f  lea     rax, [rbp+57h+var_AC]
0x180046853  mov     [rbp+57h+var_50], rax
0x180046857  lea     rdx, [rbp+57h+var_A0]
0x18004685b  movzx   eax, cs:word_180164586
0x180046862  xor     r9d, r9d
0x180046865  mov     [rbp+57h+var_9C], eax
0x180046868  xor     r8d, r8d
0x18004686b  mov     rax, cs:off_180173280
0x180046872  mov     [rbp+57h+var_90], rax
0x180046876  mov     [rbp+57h+var_54], r13d
0x18004687a  mov     [rbp+57h+var_AC], esi
0x18004687d  mov     [rbp+57h+var_48], 4
0x180046885  mov     [rbp+57h+var_A0], 0B000000h
0x18004688c  mov     [rbp+57h+var_98], r13
0x180046890  movzx   eax, word ptr [rax]
0x180046893  mov     [rbp+57h+var_88], eax
0x180046896  lea     rax, unk_180164590
0x18004689d  mov     [rbp+57h+var_80], rax
0x1800468a1  mov     rax, r12
0x1800468a4  sub     eax, ecx
0x1800468a6  mov     [rbp+57h+var_84], 2
0x1800468ad  mov     [rbp+57h+var_78], 4Dh ; 'M'
0x1800468b4  mov     [rbp+57h+var_74], 1
0x1800468bb  mov     [rbp+57h+var_B0], eax
0x1800468be  mov     eax, [rbp+57h+var_B0]
0x1800468c1  mov     rcx, cs:qword_180173298
0x1800468c8  lea     rax, [rbp+57h+var_90]
0x1800468cc  mov     [rsp+0E0h+var_B8], rax
0x1800468d1  mov     dword ptr [rsp+0E0h+var_C0], 5
0x1800468d9  call    cs:__imp_EtwEventWriteTransfer
0x1800468df  xor     r9d, r9d
0x1800468e2  mov     dword ptr [rsp+0E0h+var_C0], esi
0x1800468e6  xor     r8d, r8d
0x1800468e9  mov     edx, 0Bh
0x1800468ee  mov     rcx, r15
0x1800468f1  call    IkeConstructVendor
0x1800468f6  mov     r14, rax
0x1800468f9  mov     ecx, cs:dword_180173278
0x1800468ff  cmp     ecx, 5
0x180046902  jbe     loc_180046A64
0x180046908  mov     rdx, cs:qword_180173290
0x18004690f  mov     rcx, cs:qword_180173288
0x180046916  test    cl, 1
0x180046919  jz      loc_180046A64
0x18004691f  mov     rcx, rdx
0x180046922  and     ecx, 1
0x180046925  cmp     rcx, rdx
0x180046928  jnz     loc_180046A64
0x18004692e  mov     rax, cs:gIkeExtGlobals
0x180046935  test    rax, rax
0x180046938  jz      short loc_180046963
0x18004693a  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180046940  cmp     ecx, 0FFFFFFFFh
0x180046943  jz      short loc_180046963
0x180046945  call    cs:__imp_TlsGetValue
0x18004694b  test    rax, rax
0x18004694e  jz      short loc_18004695C
0x180046950  mov     rcx, [rax]
0x180046953  mov     rax, cs:gIkeExtGlobals
0x18004695a  jmp     short loc_180046966
0x18004695c  mov     rax, cs:gIkeExtGlobals
0x180046963  mov     rcx, r13
0x180046966  mov     [rbp+57h+var_A8], rcx
0x18004696a  lea     rcx, [rbp+57h+var_A8]
0x18004696e  mov     [rbp+57h+var_70], rcx
0x180046972  mov     [rbp+57h+var_68], 8
0x18004697a  test    rax, rax
0x18004697d  jz      short loc_1800469B5
0x18004697f  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180046985  cmp     ecx, 0FFFFFFFFh
0x180046988  jz      short loc_1800469B5
0x18004698a  call    cs:__imp_TlsGetValue
0x180046990  test    rax, rax
0x180046993  lea     rdx, [rax+8]
0x180046997  cmovz   rdx, r13
0x18004699b  test    rdx, rdx
0x18004699e  jz      short loc_1800469B5
0x1800469a0  cmp     [rdx+rbx*2+2], r13w
0x1800469a6  lea     rbx, [rbx+1]
0x1800469aa  jnz     short loc_1800469A0
0x1800469ac  lea     ebx, ds:2[rbx*2]
0x1800469b3  jmp     short loc_1800469C1
0x1800469b5  lea     rdx, LocaleName
0x1800469bc  mov     ebx, 2
0x1800469c1  movzx   eax, cs:word_180166E61
0x1800469c8  xor     r9d, r9d
0x1800469cb  mov     [rbp+57h+var_9C], eax
0x1800469ce  xor     r8d, r8d
0x1800469d1  mov     rax, cs:off_180173280
0x1800469d8  mov     [rbp+57h+var_90], rax
0x1800469dc  mov     [rbp+57h+var_58], ebx
0x1800469df  lea     rbx, aIkeoptionalcon_13; "IkeOptionalConstructAuthipInitiatorKeDh"...
0x1800469e6  mov     [rbp+57h+var_60], rdx
0x1800469ea  lea     rdx, [rbp+57h+var_A0]
0x1800469ee  mov     [rbp+57h+var_54], r13d
0x1800469f2  mov     [rbp+57h+var_50], rbx
0x1800469f6  mov     [rbp+57h+var_48], 35h ; '5'
0x1800469fe  mov     [rbp+57h+var_A0], 0B000000h
0x180046a05  mov     [rbp+57h+var_98], 1
0x180046a0d  movzx   eax, word ptr [rax]
0x180046a10  mov     [rbp+57h+var_88], eax
0x180046a13  lea     rax, byte_180166E6B
0x180046a1a  mov     [rbp+57h+var_80], rax
0x180046a1e  lea     rax, _TraceLoggingMetadata
0x180046a25  sub     r12d, eax
0x180046a28  mov     [rbp+57h+var_84], 2
  ... truncated ...
```
