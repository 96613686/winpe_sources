# IkeConstructMMSA

- ea: `0x180045400`
- end: `0x180045dc4`
- name: `IkeConstructMMSA`
- size: `2500`
- prototype: ``
- caller_count: `9`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800428c0`
- `0x180043270`
- `0x1800e6040`
- `0x1800e66d8`
- `0x1800e6c28`
- `0x1800e6e2c`
- `0x1800e7294`
- `0x1800e77b4`
- `0x1800e7b04`

## callees

- `0x180008388`
- `0x180008b70`
- `0x1800096c0`
- `0x1800107d0`
- `0x180045400`
- `0x180050850`
- `0x18005bc40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045499`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800454de`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045607`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045642`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004569e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800456e3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045878`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800458bc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045a96`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045ada`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045c74`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045cbc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045499`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800454de`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045607`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045642`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004569e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800456e3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045878`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800458bc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045a96`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045ada`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045c74`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045cbc`
- `ntdll!EtwEventWriteTransfer` at `0x1800455bd`
- `ntdll!EtwEventWriteTransfer` at `0x1800457ba`
- `ntdll!EtwEventWriteTransfer` at `0x18004599e`
- `ntdll!EtwEventWriteTransfer` at `0x180045bb3`
- `ntdll!EtwEventWriteTransfer` at `0x180045d88`
- `ntdll!EtwEventWriteTransfer` at `0x1800455bd`
- `ntdll!EtwEventWriteTransfer` at `0x1800457ba`
- `ntdll!EtwEventWriteTransfer` at `0x18004599e`
- `ntdll!EtwEventWriteTransfer` at `0x180045bb3`
- `ntdll!EtwEventWriteTransfer` at `0x180045d88`
- `WS2_32!__imp_htonl` at `0x180045bed`
- `WS2_32!__imp_htonl` at `0x180045bfb`
- `WS2_32!__imp_htonl` at `0x180045bed`
- `WS2_32!__imp_htonl` at `0x180045bfb`
- `WS2_32!__imp_htons` at `0x180045bde`
- `WS2_32!__imp_htons` at `0x180045bde`
- `WS2_32!__imp_ntohs` at `0x180045a35`
- `WS2_32!__imp_ntohs` at `0x180045a35`

## pseudocode

```c
__int64 __fastcall IkeConstructMMSA(__int64 *a1, __int64 a2, __int64 a3, unsigned int *a4, __int64 a5)
{
  __int64 v9; // rdi
  LPCRITICAL_SECTION v10; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v13; // rcx
  DWORD v14; // ecx
  char *v15; // rax
  const WCHAR *v16; // rdx
  __int64 v17; // rax
  bool v18; // zf
  int v19; // eax
  _QWORD *v20; // rcx
  LPCRITICAL_SECTION v21; // rdx
  DWORD v22; // eax
  LPVOID v23; // rax
  LPVOID v24; // r8
  __int64 v25; // rbx
  DWORD v26; // eax
  __int64 *v27; // rax
  __int64 v28; // r9
  LPCRITICAL_SECTION v29; // rax
  DWORD v30; // ecx
  __int64 *v31; // rax
  __int64 v32; // rcx
  DWORD v33; // ecx
  char *v34; // rax
  const WCHAR *v35; // rdx
  __int64 v36; // rax
  int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rbx
  __int64 v41; // r14
  __int64 v42; // rax
  LPCRITICAL_SECTION v43; // rax
  DWORD v44; // ecx
  __int64 *v45; // rax
  __int64 v46; // rcx
  DWORD v47; // ecx
  char *v48; // rax
  const WCHAR *v49; // rdx
  __int64 v50; // rax
  int v51; // eax
  __int64 v52; // rsi
  __int64 v53; // rbx
  __int64 v54; // rcx
  LPCRITICAL_SECTION v55; // rax
  DWORD v56; // ecx
  __int64 *v57; // rax
  __int64 v58; // rcx
  DWORD v59; // ecx
  char *v60; // rax
  const WCHAR *v61; // rdx
  __int64 v62; // rax
  int v63; // eax
  u_long v64; // eax
  __int64 v65; // rcx
  LPCRITICAL_SECTION v66; // rax
  DWORD v67; // ecx
  __int64 *v68; // rax
  __int64 v69; // rcx
  DWORD v70; // ecx
  char *v71; // rax
  const WCHAR *v72; // rdx
  int v73; // eax
  int v75; // [rsp+28h] [rbp-89h]
  __int64 v76; // [rsp+30h] [rbp-81h]
  _QWORD v77[2]; // [rsp+40h] [rbp-71h] BYREF
  char *v78; // [rsp+50h] [rbp-61h] BYREF
  int v79; // [rsp+58h] [rbp-59h]
  int v80; // [rsp+5Ch] [rbp-55h]
  char *v81; // [rsp+60h] [rbp-51h]
  int v82; // [rsp+68h] [rbp-49h]
  int v83; // [rsp+6Ch] [rbp-45h]
  _QWORD *v84; // [rsp+70h] [rbp-41h]
  __int64 v85; // [rsp+78h] [rbp-39h]
  const WCHAR *v86; // [rsp+80h] [rbp-31h]
  int v87; // [rsp+88h] [rbp-29h]
  int v88; // [rsp+8Ch] [rbp-25h]
  const char *v89; // [rsp+90h] [rbp-21h]
  __int64 v90; // [rsp+98h] [rbp-19h]
  __int64 v91; // [rsp+A0h] [rbp-11h] BYREF
  __int64 v92; // [rsp+A8h] [rbp-9h]
  int v93; // [rsp+B0h] [rbp-1h] BYREF
  int v94; // [rsp+B4h] [rbp+3h]
  __int64 v95; // [rsp+B8h] [rbp+7h]

  v9 = -1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v10 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v10 = gIkeExtGlobals;
LABEL_9:
    v13 = 0;
    goto LABEL_10;
  }
  v13 = *Value;
  v10 = gIkeExtGlobals;
LABEL_10:
  v77[0] = v13;
  v84 = v77;
  v85 = 8;
  if ( !v10 )
    goto LABEL_18;
  v14 = (DWORD)v10[86].LockSemaphore;
  if ( v14 == -1 )
    goto LABEL_18;
  v15 = (char *)TlsGetValue(v14);
  v16 = (const WCHAR *)(v15 + 8);
  if ( !v15 )
    v16 = 0;
  if ( v16 )
  {
    v17 = -1;
    do
      v18 = v16[++v17] == 0;
    while ( !v18 );
    v19 = 2 * v17 + 2;
  }
  else
  {
LABEL_18:
    v16 = &LocaleName;
    v19 = 2;
  }
  v87 = v19;
  v86 = v16;
  v89 = "IkeConstructMMSA";
  v78 = off_180173280;
  v88 = 0;
  v90 = 17;
  v91 = 0x50B000000LL;
  v92 = 1;
  v79 = *(unsigned __int16 *)off_180173280;
  v81 = (char *)&dword_180166EA4;
  v80 = 2;
  v82 = 45;
  v83 = 1;
  EtwEventWriteTransfer(qword_180173298, &v91, 0, 0, 5, &v78);
LABEL_20:
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v21 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (v22 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v22 == -1) )
    {
      v24 = 0;
    }
    else
    {
      v23 = TlsGetValue(v22);
      v20 = WPP_GLOBAL_Control;
      v24 = v23;
      v21 = gIkeExtGlobals;
    }
    v25 = (__int64)v24 + 8;
    if ( !v24 )
      v25 = 0;
    if ( v21
      && (v26 = (DWORD)v21[86].LockSemaphore, v26 != -1)
      && (v27 = (__int64 *)TlsGetValue(v26), v20 = WPP_GLOBAL_Control, v27) )
    {
      v28 = *v27;
    }
    else
    {
      LODWORD(v28) = 0;
    }
    WPP_SF_iS(v20[2], 10, (unsigned int)WPP_9e20c17f942b384098f687a4d4c27433_Traceguids, v28, v25);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v29 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v30 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v30 != -1 )
      {
        v31 = (__int64 *)TlsGetValue(v30);
        if ( v31 )
        {
          v32 = *v31;
          v29 = gIkeExtGlobals;
LABEL_42:
          v77[0] = v32;
          v84 = v77;
          v85 = 8;
          if ( !v29 )
            goto LABEL_50;
          v33 = (DWORD)v29[86].LockSemaphore;
          if ( v33 == -1 )
            goto LABEL_50;
          v34 = (char *)TlsGetValue(v33);
          v35 = (const WCHAR *)(v34 + 8);
          if ( !v34 )
            v35 = 0;
          if ( v35 )
          {
            v36 = -1;
            do
              v18 = v35[++v36] == 0;
            while ( !v18 );
            v37 = 2 * v36 + 2;
          }
          else
          {
LABEL_50:
            v35 = &LocaleName;
            v37 = 2;
          }
          v87 = v37;
          v86 = v35;
          v89 = "Construct MM SA";
          v78 = off_180173280;
          v88 = 0;
          v90 = 16;
          v91 = 0x40B000000LL;
          v92 = 0;
          v79 = *(unsigned __int16 *)off_180173280;
          v81 = byte_180163FAB;
          v80 = 2;
          v82 = 51;
          v83 = 1;
          EtwEventWriteTransfer(qword_180173298, &v91, 0, 0, 5, &v78);
          goto LABEL_52;
        }
        v29 = gIkeExtGlobals;
      }
    }
    v32 = 0;
    goto LABEL_42;
  }
LABEL_52:
  v38 = *((unsigned __int16 *)a1 + 7);
  v39 = *a1;
  LODWORD(v91) = 0;
  *(_BYTE *)(v38 + v39) = 1;
  v40 = IkeExpandPacket(a1, 12);
  if ( v40 )
    goto LABEL_99;
  v41 = *((unsigned __int16 *)a1 + 6);
  *((_WORD *)a1 + 7) = v41;
  *((_WORD *)a1 + 6) = v41 + 12;
  if ( (*(_BYTE *)(a2 + 8) & 1) != 0 )
  {
    v42 = IkeConstructMMProposalInitiator(a1, a3, a5, *(_DWORD *)a2 == 1);
    goto LABEL_97;
  }
  if ( (unsigned int)dword_180173278 > 5 && (qword_180173288 & 1) != 0 && (qword_180173290 & 1) == qword_180173290 )
  {
    v43 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v44 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v44 != -1 )
      {
        v45 = (__int64 *)TlsGetValue(v44);
        if ( v45 )
        {
          v46 = *v45;
          v43 = gIkeExtGlobals;
LABEL_64:
          v77[0] = v46;
          v84 = v77;
          v85 = 8;
          if ( !v43 )
            goto LABEL_72;
          v47 = (DWORD)v43[86].LockSemaphore;
          if ( v47 == -1 )
            goto LABEL_72;
          v48 = (char *)TlsGetValue(v47);
          v49 = (const WCHAR *)(v48 + 8);
          if ( !v48 )
            v49 = 0;
          if ( v49 )
          {
            v50 = -1;
            do
              v18 = v49[++v50] == 0;
            while ( !v18 );
            v51 = 2 * v50 + 2;
          }
          else
          {
LABEL_72:
            v49 = &LocaleName;
            v51 = 2;
          }
          v87 = v51;
          v94 = 5;
          v78 = off_180173280;
          v86 = v49;
          v88 = 0;
          v89 = "IkeConstructMMProposalResponder";
          v90 = 32;
          v93 = 184549376;
          v95 = 1;
          v79 = *(unsigned __int16 *)off_180173280;
          v81 = (char *)&dword_180166EA4;
          v80 = 2;
          v82 = 45;
          v83 = 1;
          EtwEventWriteTransfer(qword_180173298, &v93, 0, 0, 5, &v78);
          goto LABEL_74;
        }
        v43 = gIkeExtGlobals;
      }
    }
    v46 = 0;
    goto LABEL_64;
  }
LABEL_74:
  v76 = 0x10000080000LL;
  BYTE4(v76) = *((_BYTE *)a4 + 8);
  v52 = IkeExpandPacket(a1, 8);
  if ( !v52 )
  {
    v53 = *((unsigned __int16 *)a1 + 6);
    *((_WORD *)a1 + 7) = v53;
    *((_WORD *)a1 + 6) = v53 + 8;
    v54 = 80LL * *a4;
    LOBYTE(v75) = a4[v54 + 18];
    v52 = IkeConstructMMTransform(0, (_DWORD)a1, a4[v54 + 12], (int)(v54 * 4) + (int)a4 + 16, a5, v75);
    if ( !v52 )
    {
      HIBYTE(v76) = 1;
      LOBYTE(v76) = 0;
      WORD1(v76) = ntohs(*((_WORD *)a1 + 6) - v53);
      *(_QWORD *)(v53 + *a1) = v76;
    }
  }
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_96;
  v55 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_85;
  v56 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v56 == -1 )
    goto LABEL_85;
  v57 = (__int64 *)TlsGetValue(v56);
  if ( !v57 )
  {
    v55 = gIkeExtGlobals;
LABEL_85:
    v58 = 0;
    goto LABEL_86;
  }
  v58 = *v57;
  v55 = gIkeExtGlobals;
LABEL_86:
  v77[0] = v58;
  v84 = v77;
  v85 = 8;
  if ( !v55 )
    goto LABEL_94;
  v59 = (DWORD)v55[86].LockSemaphore;
  if ( v59 == -1 )
    goto LABEL_94;
  v60 = (char *)TlsGetValue(v59);
  v61 = (const WCHAR *)(v60 + 8);
  if ( !v60 )
    v61 = 0;
  if ( v61 )
  {
    v62 = -1;
    do
      v18 = v61[++v62] == 0;
    while ( !v18 );
    v63 = 2 * v62 + 2;
  }
  else
  {
LABEL_94:
    v61 = &LocaleName;
    v63 = 2;
  }
  v87 = v63;
  v94 = 5;
  v78 = off_180173280;
  v86 = v61;
  v88 = 0;
  v89 = "IkeConstructMMProposalResponder";
  v90 = 32;
  v93 = 184549376;
  v95 = 1;
  v79 = *(unsigned __int16 *)off_180173280;
  v80 = 2;
  v81 = byte_180166E6B;
  v82 = 45;
  v83 = 1;
  EtwEventWriteTransfer(qword_180173298, &v93, 0, 0, 5, &v78);
LABEL_96:
  v42 = IkeReturnError(v52, "IkeConstructMMProposalResponder");
LABEL_97:
  v40 = v42;
  if ( !v42 )
  {
    WORD1(v91) = htons(*((_WORD *)a1 + 6) - v41);
    HIDWORD(v91) = htonl(1u);
    v64 = htonl(1u);
    v65 = *a1;
    *(_QWORD *)(v41 + v65) = v91;
    *(_DWORD *)(v41 + v65 + 8) = v64;
    *((_WORD *)a1 + 7) = v41;
  }
LABEL_99:
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    return IkeReturnError(v40, "IkeConstructMMSA");
  v66 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_107;
  v67 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v67 == -1 )
    goto LABEL_107;
  v68 = (__int64 *)TlsGetValue(v67);
  if ( !v68 )
  {
    v66 = gIkeExtGlobals;
LABEL_107:
    v69 = 0;
    goto LABEL_108;
  }
  v69 = *v68;
  v66 = gIkeExtGlobals;
LABEL_108:
  v77[0] = v69;
  v84 = v77;
  v85 = 8;
  if ( !v66 )
    goto LABEL_115;
  v70 = (DWORD)v66[86].LockSemaphore;
  if ( v70 == -1 )
    goto LABEL_115;
  v71 = (char *)TlsGetValue(v70);
  v72 = (const WCHAR *)(v71 + 8);
  if ( !v71 )
    v72 = 0;
  if ( v72 )
  {
    do
      v18 = v72[++v9] == 0;
    while ( !v18 );
    v73 = 2 * v9 + 2;
  }
  else
  {
LABEL_115:
    v72 = &LocaleName;
    v73 = 2;
  }
  v87 = v73;
  v86 = v72;
  v89 = "IkeConstructMMSA";
  v94 = 5;
  v78 = off_180173280;
  v88 = 0;
  v90 = 17;
  v93 = 184549376;
  v95 = 1;
  v79 = *(unsigned __int16 *)off_180173280;
  v80 = 2;
  v81 = byte_180166E6B;
  v82 = 45;
  v83 = 1;
  EtwEventWriteTransfer(qword_180173298, &v93, 0, 0, 5, &v78);
  return IkeReturnError(v40, "IkeConstructMMSA");
}

```

## disassembly

```asm
0x180045400  mov     [rsp-8+arg_8], rbx
0x180045405  push    rbp
0x180045406  push    rsi
0x180045407  push    rdi
0x180045408  push    r12
0x18004540a  push    r13
0x18004540c  push    r14
0x18004540e  push    r15
0x180045410  lea     rbp, [rsp-1Fh]
0x180045415  sub     rsp, 0D0h
0x18004541c  mov     rax, cs:__security_cookie
0x180045423  xor     rax, rsp
0x180045426  mov     [rbp+4Fh+var_40], rax
0x18004542a  mov     rax, [rbp+4Fh+arg_20]
0x18004542e  lea     r14, _TraceLoggingMetadataEnd
0x180045435  mov     [rbp+4Fh+var_C8], rax
0x180045439  xor     ebx, ebx
0x18004543b  mov     eax, cs:dword_180173278
0x180045441  mov     r13, r9
0x180045444  mov     r12, r8
0x180045447  mov     rsi, rdx
0x18004544a  mov     r15, rcx
0x18004544d  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180045454  cmp     eax, 5
0x180045457  jbe     loc_1800455C3
0x18004545d  mov     rcx, cs:qword_180173290
0x180045464  mov     rax, cs:qword_180173288
0x18004546b  test    al, 1
0x18004546d  jz      loc_1800455C3
0x180045473  mov     rax, rcx
0x180045476  and     eax, 1
0x180045479  cmp     rax, rcx
0x18004547c  jnz     loc_1800455C3
0x180045482  mov     rax, cs:gIkeExtGlobals
0x180045489  test    rax, rax
0x18004548c  jz      short loc_1800454B7
0x18004548e  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180045494  cmp     ecx, 0FFFFFFFFh
0x180045497  jz      short loc_1800454B7
0x180045499  call    cs:__imp_TlsGetValue
0x18004549f  test    rax, rax
0x1800454a2  jz      short loc_1800454B0
0x1800454a4  mov     rcx, [rax]
0x1800454a7  mov     rax, cs:gIkeExtGlobals
0x1800454ae  jmp     short loc_1800454BA
0x1800454b0  mov     rax, cs:gIkeExtGlobals
0x1800454b7  mov     rcx, rbx
0x1800454ba  mov     [rbp+4Fh+var_C0], rcx
0x1800454be  lea     rcx, [rbp+4Fh+var_C0]
0x1800454c2  mov     [rbp+4Fh+var_90], rcx
0x1800454c6  mov     [rbp+4Fh+var_88], 8
0x1800454ce  test    rax, rax
0x1800454d1  jz      short loc_180045514
0x1800454d3  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800454d9  cmp     ecx, 0FFFFFFFFh
0x1800454dc  jz      short loc_180045514
0x1800454de  call    cs:__imp_TlsGetValue
0x1800454e4  test    rax, rax
0x1800454e7  lea     rdx, [rax+8]
0x1800454eb  cmovz   rdx, rbx
0x1800454ef  test    rdx, rdx
0x1800454f2  jz      short loc_180045514
0x1800454f4  mov     rax, rdi
0x1800454f7  nop     word ptr [rax+rax+00000000h]
0x180045500  cmp     [rdx+rax*2+2], bx
0x180045505  lea     rax, [rax+1]
0x180045509  jnz     short loc_180045500
0x18004550b  lea     eax, ds:2[rax*2]
0x180045512  jmp     short loc_180045520
0x180045514  lea     rdx, LocaleName
0x18004551b  mov     eax, 2
0x180045520  mov     [rbp+4Fh+var_78], eax
0x180045523  lea     rcx, _TraceLoggingMetadata
0x18004552a  mov     [rbp+4Fh+var_80], rdx
0x18004552e  lea     rax, aIkeconstructmm_5; "IkeConstructMMSA"
0x180045535  mov     [rbp+4Fh+var_70], rax
0x180045539  lea     rdx, [rbp+4Fh+var_60]
0x18004553d  movzx   eax, cs:word_180166E9A
0x180045544  xor     r9d, r9d
0x180045547  mov     dword ptr [rbp+4Fh+var_60+4], eax
0x18004554a  xor     r8d, r8d
0x18004554d  mov     rax, cs:off_180173280
0x180045554  mov     [rbp+4Fh+var_B0], rax
0x180045558  mov     [rbp+4Fh+var_74], ebx
0x18004555b  mov     [rbp+4Fh+var_68], 11h
0x180045563  mov     dword ptr [rbp+4Fh+var_60], 0B000000h
0x18004556a  mov     [rbp+4Fh+var_58], 1
0x180045572  movzx   eax, word ptr [rax]
0x180045575  mov     [rbp+4Fh+var_A8], eax
0x180045578  lea     rax, dword_180166EA4
0x18004557f  mov     [rbp+4Fh+var_A0], rax
0x180045583  mov     rax, r14
0x180045586  sub     eax, ecx
0x180045588  mov     [rbp+4Fh+var_A4], 2
0x18004558f  mov     [rbp+4Fh+var_98], 2Dh ; '-'
0x180045596  mov     [rbp+4Fh+var_94], 1
0x18004559d  mov     dword ptr [rsp+100h+var_D0], eax
0x1800455a1  mov     eax, dword ptr [rsp+100h+var_D0]
0x1800455a5  mov     rcx, cs:qword_180173298
0x1800455ac  lea     rax, [rbp+4Fh+var_B0]
0x1800455b0  mov     [rsp+100h+var_D8], rax
0x1800455b5  mov     dword ptr [rsp+100h+var_E0], 5
0x1800455bd  call    cs:__imp_EtwEventWriteTransfer
0x1800455c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800455ca  lea     rax, WPP_GLOBAL_Control
0x1800455d1  cmp     rcx, rax
0x1800455d4  jz      loc_180045678
0x1800455da  cmp     byte ptr [rcx+19h], 4
0x1800455de  jb      loc_180045678
0x1800455e4  test    byte ptr [rcx+1Ch], 10h
0x1800455e8  jz      loc_180045678
0x1800455ee  mov     rdx, cs:gIkeExtGlobals
0x1800455f5  test    rdx, rdx
0x1800455f8  jz      short loc_180045620
0x1800455fa  mov     eax, [rdx+0D88h]
0x180045600  cmp     eax, 0FFFFFFFFh
0x180045603  jz      short loc_180045620
0x180045605  mov     ecx, eax; dwTlsIndex
0x180045607  call    cs:__imp_TlsGetValue
0x18004560d  mov     rcx, cs:WPP_GLOBAL_Control
0x180045614  mov     r8, rax
0x180045617  mov     rdx, cs:gIkeExtGlobals
0x18004561e  jmp     short loc_180045623
0x180045620  mov     r8, rbx
0x180045623  xor     eax, eax
0x180045625  lea     rbx, [r8+8]
0x180045629  test    r8, r8
0x18004562c  cmovz   rbx, rax
0x180045630  test    rdx, rdx
0x180045633  jz      short loc_180045659
0x180045635  mov     eax, [rdx+0D88h]
0x18004563b  cmp     eax, 0FFFFFFFFh
0x18004563e  jz      short loc_180045659
0x180045640  mov     ecx, eax; dwTlsIndex
0x180045642  call    cs:__imp_TlsGetValue
0x180045648  mov     rcx, cs:WPP_GLOBAL_Control
0x18004564f  test    rax, rax
0x180045652  jz      short loc_180045659
0x180045654  mov     r9, [rax]
0x180045657  jmp     short loc_18004565C
0x180045659  xor     r9d, r9d
0x18004565c  mov     rcx, [rcx+10h]
0x180045660  lea     r8, WPP_9e20c17f942b384098f687a4d4c27433_Traceguids
0x180045667  mov     edx, 0Ah
0x18004566c  mov     [rsp+100h+var_E0], rbx
0x180045671  call    WPP_SF_iS
0x180045676  xor     ebx, ebx
0x180045678  mov     eax, cs:dword_180173278
0x18004567e  cmp     eax, 4
0x180045681  jbe     loc_1800457C0
0x180045687  mov     rax, cs:gIkeExtGlobals
0x18004568e  test    rax, rax
0x180045691  jz      short loc_1800456BC
0x180045693  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180045699  cmp     ecx, 0FFFFFFFFh
0x18004569c  jz      short loc_1800456BC
0x18004569e  call    cs:__imp_TlsGetValue
0x1800456a4  test    rax, rax
0x1800456a7  jz      short loc_1800456B5
0x1800456a9  mov     rcx, [rax]
0x1800456ac  mov     rax, cs:gIkeExtGlobals
0x1800456b3  jmp     short loc_1800456BF
0x1800456b5  mov     rax, cs:gIkeExtGlobals
0x1800456bc  mov     rcx, rbx
0x1800456bf  mov     [rbp+4Fh+var_C0], rcx
0x1800456c3  lea     rcx, [rbp+4Fh+var_C0]
0x1800456c7  mov     [rbp+4Fh+var_90], rcx
0x1800456cb  mov     [rbp+4Fh+var_88], 8
0x1800456d3  test    rax, rax
0x1800456d6  jz      short loc_180045715
0x1800456d8  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800456de  cmp     ecx, 0FFFFFFFFh
0x1800456e1  jz      short loc_180045715
0x1800456e3  call    cs:__imp_TlsGetValue
0x1800456e9  test    rax, rax
0x1800456ec  lea     rdx, [rax+8]
0x1800456f0  cmovz   rdx, rbx
0x1800456f4  test    rdx, rdx
0x1800456f7  jz      short loc_180045715
0x1800456f9  mov     rax, rdi
0x1800456fc  nop     dword ptr [rax+00h]
0x180045700  cmp     word ptr [rdx+rax*2+2], 0
0x180045706  lea     rax, [rax+1]
0x18004570a  jnz     short loc_180045700
0x18004570c  lea     eax, ds:2[rax*2]
0x180045713  jmp     short loc_180045721
0x180045715  lea     rdx, LocaleName
0x18004571c  mov     eax, 2
0x180045721  mov     [rbp+4Fh+var_78], eax
0x180045724  lea     rcx, _TraceLoggingMetadata
0x18004572b  mov     [rbp+4Fh+var_80], rdx
0x18004572f  lea     rax, aConstructMmSa; "Construct MM SA"
0x180045736  mov     [rbp+4Fh+var_70], rax
0x18004573a  lea     rdx, [rbp+4Fh+var_60]
0x18004573e  movzx   eax, cs:word_180163FA1
0x180045745  xor     r9d, r9d
0x180045748  mov     dword ptr [rbp+4Fh+var_60+4], eax
0x18004574b  xor     r8d, r8d
0x18004574e  mov     rax, cs:off_180173280
0x180045755  mov     [rbp+4Fh+var_B0], rax
0x180045759  mov     [rbp+4Fh+var_74], ebx
0x18004575c  mov     [rbp+4Fh+var_68], 10h
0x180045764  mov     dword ptr [rbp+4Fh+var_60], 0B000000h
0x18004576b  mov     [rbp+4Fh+var_58], rbx
0x18004576f  movzx   eax, word ptr [rax]
0x180045772  mov     [rbp+4Fh+var_A8], eax
0x180045775  lea     rax, byte_180163FAB
0x18004577c  mov     [rbp+4Fh+var_A0], rax
0x180045780  mov     rax, r14
0x180045783  sub     eax, ecx
0x180045785  mov     [rbp+4Fh+var_A4], 2
0x18004578c  mov     [rbp+4Fh+var_98], 33h ; '3'
0x180045793  mov     [rbp+4Fh+var_94], 1
0x18004579a  mov     dword ptr [rsp+100h+var_D0], eax
0x18004579e  mov     eax, dword ptr [rsp+100h+var_D0]
0x1800457a2  mov     rcx, cs:qword_180173298
0x1800457a9  lea     rax, [rbp+4Fh+var_B0]
0x1800457ad  mov     [rsp+100h+var_D8], rax
0x1800457b2  mov     dword ptr [rsp+100h+var_E0], 5
0x1800457ba  call    cs:__imp_EtwEventWriteTransfer
0x1800457c0  movzx   ecx, word ptr [r15+0Eh]
0x1800457c5  mov     edx, 0Ch
0x1800457ca  mov     rax, [r15]
0x1800457cd  mov     dword ptr [rbp+4Fh+var_60], ebx
0x1800457d0  mov     byte ptr [rcx+rax], 1
0x1800457d4  mov     rcx, r15
0x1800457d7  call    IkeExpandPacket
0x1800457dc  mov     rbx, rax
0x1800457df  test    rax, rax
0x1800457e2  jnz     loc_180045C22
0x1800457e8  movzx   r14d, word ptr [r15+0Ch]
0x1800457ed  mov     [r15+0Eh], r14w
0x1800457f2  lea     eax, [r14+0Ch]
0x1800457f6  mov     [r15+0Ch], ax
0x1800457fb  test    byte ptr [rsi+8], 1
0x1800457ff  jz      short loc_180045826
0x180045801  mov     r8, [rbp+4Fh+var_C8]
0x180045805  xor     r9d, r9d
0x180045808  cmp     dword ptr [rsi], 1
0x18004580b  mov     rdx, r12
0x18004580e  mov     rcx, r15
0x180045811  setz    r9b
0x180045815  call    IkeConstructMMProposalInitiator
0x18004581a  lea     r13, byte_180166E6B
0x180045821  jmp     loc_180045BCD
0x180045826  mov     eax, cs:dword_180173278
0x18004582c  lea     r12, aIkeconstructmm_7; "IkeConstructMMProposalResponder"
0x180045833  cmp     eax, 5
0x180045836  jbe     loc_1800459A4
0x18004583c  mov     rcx, cs:qword_180173290
0x180045843  mov     rax, cs:qword_180173288
0x18004584a  test    al, 1
0x18004584c  jz      loc_1800459A4
0x180045852  mov     rax, rcx
0x180045855  and     eax, 1
0x180045858  cmp     rax, rcx
0x18004585b  jnz     loc_1800459A4
0x180045861  mov     rax, cs:gIkeExtGlobals
0x180045868  test    rax, rax
0x18004586b  jz      short loc_180045896
0x18004586d  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180045873  cmp     ecx, 0FFFFFFFFh
0x180045876  jz      short loc_180045896
0x180045878  call    cs:__imp_TlsGetValue
0x18004587e  test    rax, rax
0x180045881  jz      short loc_18004588F
0x180045883  mov     rcx, [rax]
0x180045886  mov     rax, cs:gIkeExtGlobals
0x18004588d  jmp     short loc_180045898
0x18004588f  mov     rax, cs:gIkeExtGlobals
0x180045896  xor     ecx, ecx
0x180045898  mov     [rbp+4Fh+var_C0], rcx
0x18004589c  lea     rcx, [rbp+4Fh+var_C0]
0x1800458a0  mov     [rbp+4Fh+var_90], rcx
0x1800458a4  mov     [rbp+4Fh+var_88], 8
0x1800458ac  test    rax, rax
0x1800458af  jz      short loc_1800458F4
0x1800458b1  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800458b7  cmp     ecx, 0FFFFFFFFh
0x1800458ba  jz      short loc_1800458F4
0x1800458bc  call    cs:__imp_TlsGetValue
0x1800458c2  xor     ecx, ecx
0x1800458c4  test    rax, rax
0x1800458c7  lea     rdx, [rax+8]
0x1800458cb  cmovz   rdx, rcx
0x1800458cf  test    rdx, rdx
0x1800458d2  jz      short loc_1800458F4
0x1800458d4  mov     rax, rdi
0x1800458d7  nop     word ptr [rax+rax+00000000h]
0x1800458e0  cmp     [rdx+rax*2+2], cx
0x1800458e5  lea     rax, [rax+1]
0x1800458e9  jnz     short loc_1800458E0
0x1800458eb  lea     eax, ds:2[rax*2]
0x1800458f2  jmp     short loc_180045900
0x1800458f4  lea     rdx, LocaleName
0x1800458fb  mov     eax, 2
0x180045900  mov     [rbp+4Fh+var_78], eax
0x180045903  lea     rcx, _TraceLoggingMetadata
0x18004590a  movzx   eax, cs:word_180166E9A
0x180045911  xor     r9d, r9d
  ... truncated ...
```
