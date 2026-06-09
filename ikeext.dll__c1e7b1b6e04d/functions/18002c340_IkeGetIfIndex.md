# IkeGetIfIndex

- ea: `0x18002c340`
- end: `0x18002cc0c`
- name: `IkeGetIfIndex`
- size: `2252`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180014b60`
- `0x18002d940`

## callees

- `0x180008388`
- `0x180019994`
- `0x18002c340`
- `0x180050850`
- `0x18005bce4`
- `0x180072940`
- `0x180117fa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c3e2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c429`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c562`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c59d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c608`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c64f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c859`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c894`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c8f5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c939`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ca6b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002cab3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c3e2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c429`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c562`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c59d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c608`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c64f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c859`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c894`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c8f5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c939`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ca6b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002cab3`
- `ntdll!EtwEventWriteTransfer` at `0x18002c4ff`
- `ntdll!EtwEventWriteTransfer` at `0x18002c76c`
- `ntdll!EtwEventWriteTransfer` at `0x18002ca1a`
- `ntdll!EtwEventWriteTransfer` at `0x18002cb8d`
- `ntdll!EtwEventWriteTransfer` at `0x18002c4ff`
- `ntdll!EtwEventWriteTransfer` at `0x18002c76c`
- `ntdll!EtwEventWriteTransfer` at `0x18002ca1a`
- `ntdll!EtwEventWriteTransfer` at `0x18002cb8d`

## pseudocode

```c
__int64 __fastcall IkeGetIfIndex(_BYTE *a1, __int64 a2, __int64 a3, unsigned int *a4)
{
  __int64 v8; // rbx
  LPCRITICAL_SECTION v9; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v12; // rcx
  DWORD v13; // ecx
  char *v14; // rax
  const WCHAR *v15; // rdx
  __int64 v16; // rax
  bool v17; // zf
  int v18; // eax
  LPCRITICAL_SECTION v19; // rcx
  __int64 v20; // rsi
  _QWORD *v21; // rdx
  DWORD v22; // eax
  LPVOID v23; // rax
  LPVOID v24; // r8
  __int64 v25; // rdi
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
  int v37; // ecx
  int v38; // ecx
  int v39; // r9d
  const void *v40; // rdx
  size_t v41; // r8
  unsigned int v42; // ecx
  _QWORD *v43; // rcx
  LPCRITICAL_SECTION v44; // rdx
  DWORD v45; // eax
  LPVOID v46; // rax
  LPVOID v47; // r8
  __int64 v48; // rdi
  DWORD v49; // eax
  __int64 *v50; // rax
  __int64 v51; // r9
  LPCRITICAL_SECTION v52; // rax
  DWORD v53; // ecx
  __int64 *v54; // rax
  __int64 v55; // rcx
  DWORD v56; // ecx
  char *v57; // rax
  const WCHAR *v58; // rdx
  __int64 v59; // rax
  int v60; // eax
  LPCRITICAL_SECTION v61; // rax
  DWORD v62; // ecx
  __int64 *v63; // rax
  __int64 v64; // rcx
  DWORD v65; // ecx
  char *v66; // rax
  const WCHAR *v67; // rdx
  int v68; // ebx
  __int64 v70; // [rsp+28h] [rbp-D8h]
  __int128 v71; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v72; // [rsp+50h] [rbp-B0h]
  __int64 v73; // [rsp+60h] [rbp-A0h]
  unsigned int v74; // [rsp+68h] [rbp-98h] BYREF
  __int64 v75; // [rsp+70h] [rbp-90h] BYREF
  ULONG_PTR SpinCount; // [rsp+78h] [rbp-88h] BYREF
  int v77; // [rsp+80h] [rbp-80h] BYREF
  int v78; // [rsp+84h] [rbp-7Ch]
  __int64 v79; // [rsp+88h] [rbp-78h]
  _QWORD v80[2]; // [rsp+90h] [rbp-70h] BYREF
  char *v81; // [rsp+A0h] [rbp-60h] BYREF
  int v82; // [rsp+A8h] [rbp-58h]
  int v83; // [rsp+ACh] [rbp-54h]
  char *v84; // [rsp+B0h] [rbp-50h]
  int v85; // [rsp+B8h] [rbp-48h]
  int v86; // [rsp+BCh] [rbp-44h]
  __int64 *v87; // [rsp+C0h] [rbp-40h]
  __int64 v88; // [rsp+C8h] [rbp-38h]
  const WCHAR *v89; // [rsp+D0h] [rbp-30h]
  int v90; // [rsp+D8h] [rbp-28h]
  int v91; // [rsp+DCh] [rbp-24h]
  const char *v92; // [rsp+E0h] [rbp-20h]
  __int64 v93; // [rsp+E8h] [rbp-18h]
  ULONG_PTR *p_SpinCount; // [rsp+F0h] [rbp-10h]
  __int64 v95; // [rsp+F8h] [rbp-8h]
  _QWORD *v96; // [rsp+100h] [rbp+0h]
  __int64 v97; // [rsp+108h] [rbp+8h]

  v73 = 0;
  v8 = -1;
  v71 = 0;
  v72 = 0;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v9 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v9 = gIkeExtGlobals;
LABEL_9:
    v12 = 0;
    goto LABEL_10;
  }
  v12 = *Value;
  v9 = gIkeExtGlobals;
LABEL_10:
  v75 = v12;
  v87 = &v75;
  v88 = 8;
  if ( !v9 )
    goto LABEL_18;
  v13 = (DWORD)v9[86].LockSemaphore;
  if ( v13 == -1 )
    goto LABEL_18;
  v14 = (char *)TlsGetValue(v13);
  v15 = (const WCHAR *)(v14 + 8);
  if ( !v14 )
    v15 = 0;
  if ( v15 )
  {
    v16 = -1;
    do
      v17 = v15[++v16] == 0;
    while ( !v17 );
    v18 = 2 * v16 + 2;
  }
  else
  {
LABEL_18:
    v15 = &LocaleName;
    v18 = 2;
  }
  v90 = v18;
  v89 = v15;
  v92 = "IkeGetIfIndex";
  v81 = off_180173280;
  v91 = 0;
  v93 = 14;
  v80[0] = 0x50B000000LL;
  v80[1] = 1;
  v82 = *(unsigned __int16 *)off_180173280;
  v84 = (char *)&dword_180166EA4;
  v83 = 2;
  v85 = 45;
  v86 = 1;
  v74 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EtwEventWriteTransfer(qword_180173298, v80, 0, 0, 5, &v81);
LABEL_20:
  *a4 = 0;
  v19 = gIkeExtGlobals;
  if ( gIkeExtGlobals[84].SpinCount == *(_QWORD *)a3 )
  {
    v20 = 0;
    *a4 = *(_DWORD *)(a3 + 8);
    goto LABEL_62;
  }
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v22 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
    if ( v22 == -1 )
    {
      v24 = 0;
    }
    else
    {
      v23 = TlsGetValue(v22);
      v19 = gIkeExtGlobals;
      v24 = v23;
      v21 = WPP_GLOBAL_Control;
    }
    v25 = (__int64)v24 + 8;
    if ( !v24 )
      v25 = 0;
    if ( v19
      && (v26 = (DWORD)v19[86].LockSemaphore, v26 != -1)
      && (v27 = (__int64 *)TlsGetValue(v26), v19 = gIkeExtGlobals, v21 = WPP_GLOBAL_Control, v27) )
    {
      v28 = *v27;
    }
    else
    {
      LODWORD(v28) = 0;
    }
    WPP_SF_iSii(v21[2], (_DWORD)v21, (_DWORD)v24, v28, v25, v19[84].SpinCount, *(_QWORD *)a3);
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
LABEL_43:
          v75 = v32;
          v87 = &v75;
          v88 = 8;
          if ( v29 )
          {
            v33 = (DWORD)v29[86].LockSemaphore;
            if ( v33 != -1 )
            {
              v34 = (char *)TlsGetValue(v33);
              v35 = (const WCHAR *)(v34 + 8);
              if ( !v34 )
                v35 = 0;
              if ( v35 )
              {
                v36 = -1;
                do
                  v17 = v35[++v36] == 0;
                while ( !v17 );
                v37 = 2 * v36 + 2;
                v29 = gIkeExtGlobals;
                goto LABEL_53;
              }
              v29 = gIkeExtGlobals;
            }
          }
          v35 = &LocaleName;
          v37 = 2;
LABEL_53:
          v90 = v37;
          v89 = v35;
          v92 = "Querying IF index";
          v91 = 0;
          v93 = 18;
          SpinCount = v29[84].SpinCount;
          p_SpinCount = &SpinCount;
          v80[0] = *(_QWORD *)a3;
          v96 = v80;
          v78 = 4;
          v81 = off_180173280;
          v95 = 8;
          v97 = 8;
          v77 = 184549376;
          v79 = 0;
          v82 = *(unsigned __int16 *)off_180173280;
          v84 = byte_18015346B;
          v83 = 2;
          v85 = 80;
          v86 = 1;
          v74 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v77, 0, 0, 7, &v81);
          goto LABEL_54;
        }
        v29 = gIkeExtGlobals;
      }
    }
    v32 = 0;
    goto LABEL_43;
  }
LABEL_54:
  *(_QWORD *)a3 = gIkeExtGlobals[84].SpinCount;
  v38 = (unsigned __int8)*a1 - 1;
  switch ( *a1 )
  {
    case 1:
    case 4:
    case 7:
      v39 = 0;
      break;
    case 5:
    case 6:
    case 8:
      v39 = 1;
      break;
    default:
LABEL_113:
      __fastfail(5u);
  }
  DWORD1(v71) = v39;
  switch ( v38 )
  {
    case 0:
    case 3:
    case 6:
      v40 = a1 + 8;
      v41 = 4;
      goto LABEL_60;
    case 4:
    case 5:
    case 7:
      v40 = a1 + 12;
      v41 = 16;
LABEL_60:
      memcpy_0((char *)&v71 + 8, v40, v41);
      *((_QWORD *)&v72 + 1) = a2;
      v20 = WfpPnPLookupLocalIFProperties(&v71);
      if ( v20 )
        goto LABEL_94;
      v42 = v73;
      *(_DWORD *)(a3 + 8) = v73;
      *a4 = v42;
      break;
    default:
      goto LABEL_113;
  }
LABEL_62:
  v43 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v44 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (v45 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v45 == -1) )
    {
      v47 = 0;
    }
    else
    {
      v46 = TlsGetValue(v45);
      v44 = gIkeExtGlobals;
      v47 = v46;
      v43 = WPP_GLOBAL_Control;
    }
    v48 = (__int64)v47 + 8;
    if ( !v47 )
      v48 = 0;
    if ( v44
      && (v49 = (DWORD)v44[86].LockSemaphore, v49 != -1)
      && (v50 = (__int64 *)TlsGetValue(v49), v43 = WPP_GLOBAL_Control, v50) )
    {
      v51 = *v50;
    }
    else
    {
      LODWORD(v51) = 0;
    }
    LODWORD(v70) = *a4;
    WPP_SF_iSL(v43[2], 31, (unsigned int)WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids, v51, v48, v70);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v52 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v53 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v53 != -1 )
      {
        v54 = (__int64 *)TlsGetValue(v53);
        if ( v54 )
        {
          v55 = *v54;
          v52 = gIkeExtGlobals;
LABEL_84:
          v80[0] = v55;
          v87 = v80;
          v88 = 8;
          if ( !v52 )
            goto LABEL_92;
          v56 = (DWORD)v52[86].LockSemaphore;
          if ( v56 == -1 )
            goto LABEL_92;
          v57 = (char *)TlsGetValue(v56);
          v58 = (const WCHAR *)(v57 + 8);
          if ( !v57 )
            v58 = 0;
          if ( v58 )
          {
            v59 = -1;
            do
              v17 = v58[++v59] == 0;
            while ( !v17 );
            v60 = 2 * v59 + 2;
          }
          else
          {
LABEL_92:
            v58 = &LocaleName;
            v60 = 2;
          }
          v90 = v60;
          v74 = *a4;
          v89 = v58;
          v92 = (const char *)&v74;
          v78 = 4;
          v81 = off_180173280;
          v91 = 0;
          v93 = 4;
          v77 = 184549376;
          v79 = 0;
          v82 = *(unsigned __int16 *)off_180173280;
          v84 = (char *)&word_18015351E;
          v83 = 2;
          v85 = 48;
          v86 = 1;
          LODWORD(v75) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v77, 0, 0, 5, &v81);
          goto LABEL_94;
        }
        v52 = gIkeExtGlobals;
      }
    }
    v55 = 0;
    goto LABEL_84;
  }
LABEL_94:
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    return IkeReturnError(v20, "IkeGetIfIndex");
  v61 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_102;
  v62 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v62 == -1 )
    goto LABEL_102;
  v63 = (__int64 *)TlsGetValue(v62);
  if ( !v63 )
  {
    v61 = gIkeExtGlobals;
LABEL_102:
    v64 = 0;
    goto LABEL_103;
  }
  v64 = *v63;
  v61 = gIkeExtGlobals;
LABEL_103:
  v80[0] = v64;
  v87 = v80;
  v88 = 8;
  if ( !v61 )
    goto LABEL_110;
  v65 = (DWORD)v61[86].LockSemaphore;
  if ( v65 == -1 )
    goto LABEL_110;
  v66 = (char *)TlsGetValue(v65);
  v67 = (const WCHAR *)(v66 + 8);
  if ( !v66 )
    v67 = 0;
  if ( v67 )
  {
    do
      v17 = v67[++v8] == 0;
    while ( !v17 );
    v68 = 2 * v8 + 2;
  }
  else
  {
LABEL_110:
    v67 = &LocaleName;
    v68 = 2;
  }
  v89 = v67;
  v92 = "IkeGetIfIndex";
  v78 = 5;
  v81 = off_180173280;
  v90 = v68;
  v91 = 0;
  v93 = 14;
  v77 = 184549376;
  v79 = 1;
  v82 = *(unsigned __int16 *)off_180173280;
  v84 = byte_180166E6B;
  v83 = 2;
  v85 = 45;
  v86 = 1;
  LODWORD(v75) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EtwEventWriteTransfer(qword_180173298, &v77, 0, 0, 5, &v81);
  return IkeReturnError(v20, "IkeGetIfIndex");
}

```

## disassembly

```asm
0x18002c340  push    rbp
0x18002c342  push    rbx
0x18002c343  push    rsi
0x18002c344  push    rdi
0x18002c345  push    r12
0x18002c347  push    r13
0x18002c349  push    r14
0x18002c34b  push    r15
0x18002c34d  lea     rbp, [rsp-28h]
0x18002c352  sub     rsp, 128h
0x18002c359  mov     rax, cs:__security_cookie
0x18002c360  xor     rax, rsp
0x18002c363  mov     [rbp+60h+var_50], rax
0x18002c367  xor     eax, eax
0x18002c369  lea     r13, _TraceLoggingMetadataEnd
0x18002c370  xorps   xmm0, xmm0
0x18002c373  mov     [rsp+160h+var_100], rax
0x18002c378  mov     eax, cs:dword_180173278
0x18002c37e  xor     edi, edi
0x18002c380  mov     r15, r9
0x18002c383  mov     r14, r8
0x18002c386  mov     r12, rdx
0x18002c389  mov     rsi, rcx
0x18002c38c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18002c393  movups  [rsp+160h+var_120], xmm0
0x18002c398  movups  [rsp+160h+var_110], xmm0
0x18002c39d  cmp     eax, 5
0x18002c3a0  jbe     loc_18002C505
0x18002c3a6  mov     rcx, cs:qword_180173290
0x18002c3ad  mov     rax, cs:qword_180173288
0x18002c3b4  test    al, 1
0x18002c3b6  jz      loc_18002C505
0x18002c3bc  mov     rax, rcx
0x18002c3bf  and     eax, 1
0x18002c3c2  cmp     rax, rcx
0x18002c3c5  jnz     loc_18002C505
0x18002c3cb  mov     rax, cs:gIkeExtGlobals
0x18002c3d2  test    rax, rax
0x18002c3d5  jz      short loc_18002C400
0x18002c3d7  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002c3dd  cmp     ecx, 0FFFFFFFFh
0x18002c3e0  jz      short loc_18002C400
0x18002c3e2  call    cs:__imp_TlsGetValue
0x18002c3e8  test    rax, rax
0x18002c3eb  jz      short loc_18002C3F9
0x18002c3ed  mov     rcx, [rax]
0x18002c3f0  mov     rax, cs:gIkeExtGlobals
0x18002c3f7  jmp     short loc_18002C403
0x18002c3f9  mov     rax, cs:gIkeExtGlobals
0x18002c400  mov     rcx, rdi
0x18002c403  mov     [rsp+160h+var_F0], rcx
0x18002c408  lea     rcx, [rsp+160h+var_F0]
0x18002c40d  mov     [rbp+60h+var_A0], rcx
0x18002c411  mov     [rbp+60h+var_98], 8
0x18002c419  test    rax, rax
0x18002c41c  jz      short loc_18002C456
0x18002c41e  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002c424  cmp     ecx, 0FFFFFFFFh
0x18002c427  jz      short loc_18002C456
0x18002c429  call    cs:__imp_TlsGetValue
0x18002c42f  test    rax, rax
0x18002c432  lea     rdx, [rax+8]
0x18002c436  cmovz   rdx, rdi
0x18002c43a  test    rdx, rdx
0x18002c43d  jz      short loc_18002C456
0x18002c43f  mov     rax, rbx
0x18002c442  cmp     [rdx+rax*2+2], di
0x18002c447  lea     rax, [rax+1]
0x18002c44b  jnz     short loc_18002C442
0x18002c44d  lea     eax, ds:2[rax*2]
0x18002c454  jmp     short loc_18002C462
0x18002c456  lea     rdx, LocaleName
0x18002c45d  mov     eax, 2
0x18002c462  mov     [rbp+60h+var_88], eax
0x18002c465  lea     rcx, _TraceLoggingMetadata
0x18002c46c  mov     [rbp+60h+var_90], rdx
0x18002c470  lea     rax, aIkegetifindex; "IkeGetIfIndex"
0x18002c477  mov     [rbp+60h+var_80], rax
0x18002c47b  lea     rdx, [rbp+60h+var_D0]
0x18002c47f  movzx   eax, cs:word_180166E9A
0x18002c486  xor     r9d, r9d
0x18002c489  mov     dword ptr [rbp+60h+var_D0+4], eax
0x18002c48c  xor     r8d, r8d
0x18002c48f  mov     rax, cs:off_180173280
0x18002c496  mov     [rbp+60h+var_C0], rax
0x18002c49a  mov     [rbp+60h+var_84], edi
0x18002c49d  mov     [rbp+60h+var_78], 0Eh
0x18002c4a5  mov     dword ptr [rbp+60h+var_D0], 0B000000h
0x18002c4ac  mov     [rbp+60h+var_C8], 1
0x18002c4b4  movzx   eax, word ptr [rax]
0x18002c4b7  mov     [rbp+60h+var_B8], eax
0x18002c4ba  lea     rax, dword_180166EA4
0x18002c4c1  mov     [rbp+60h+var_B0], rax
0x18002c4c5  mov     rax, r13
0x18002c4c8  sub     eax, ecx
0x18002c4ca  mov     [rbp+60h+var_B4], 2
0x18002c4d1  mov     [rbp+60h+var_A8], 2Dh ; '-'
0x18002c4d8  mov     [rbp+60h+var_A4], 1
0x18002c4df  mov     [rsp+160h+var_F8], eax
0x18002c4e3  mov     eax, [rsp+160h+var_F8]
0x18002c4e7  mov     rcx, cs:qword_180173298
0x18002c4ee  lea     rax, [rbp+60h+var_C0]
0x18002c4f2  mov     [rsp+160h+var_138], rax
0x18002c4f7  mov     dword ptr [rsp+160h+var_140], 5
0x18002c4ff  call    cs:__imp_EtwEventWriteTransfer
0x18002c505  mov     [r15], edi
0x18002c508  lea     r8, WPP_GLOBAL_Control
0x18002c50f  mov     rcx, cs:gIkeExtGlobals
0x18002c516  mov     rax, [r14]
0x18002c519  cmp     [rcx+0D40h], rax
0x18002c520  jnz     short loc_18002C531
0x18002c522  mov     eax, [r14+8]
0x18002c526  mov     rsi, rdi
0x18002c529  mov     [r15], eax
0x18002c52c  jmp     loc_18002C81C
0x18002c531  mov     rdx, cs:WPP_GLOBAL_Control
0x18002c538  cmp     rdx, r8
0x18002c53b  jz      loc_18002C5E2
0x18002c541  cmp     byte ptr [rdx+19h], 4
0x18002c545  jb      loc_18002C5E2
0x18002c54b  test    byte ptr [rdx+1Ch], 10h
0x18002c54f  jz      loc_18002C5E2
0x18002c555  mov     eax, [rcx+0D88h]
0x18002c55b  cmp     eax, 0FFFFFFFFh
0x18002c55e  jz      short loc_18002C57B
0x18002c560  mov     ecx, eax; dwTlsIndex
0x18002c562  call    cs:__imp_TlsGetValue
0x18002c568  mov     rcx, cs:gIkeExtGlobals
0x18002c56f  mov     r8, rax
0x18002c572  mov     rdx, cs:WPP_GLOBAL_Control
0x18002c579  jmp     short loc_18002C57E
0x18002c57b  mov     r8, rdi
0x18002c57e  xor     eax, eax
0x18002c580  lea     rdi, [r8+8]
0x18002c584  test    r8, r8
0x18002c587  cmovz   rdi, rax
0x18002c58b  test    rcx, rcx
0x18002c58e  jz      short loc_18002C5BB
0x18002c590  mov     eax, [rcx+0D88h]
0x18002c596  cmp     eax, 0FFFFFFFFh
0x18002c599  jz      short loc_18002C5BB
0x18002c59b  mov     ecx, eax; dwTlsIndex
0x18002c59d  call    cs:__imp_TlsGetValue
0x18002c5a3  mov     rcx, cs:gIkeExtGlobals
0x18002c5aa  mov     rdx, cs:WPP_GLOBAL_Control
0x18002c5b1  test    rax, rax
0x18002c5b4  jz      short loc_18002C5BB
0x18002c5b6  mov     r9, [rax]
0x18002c5b9  jmp     short loc_18002C5BE
0x18002c5bb  xor     r9d, r9d
0x18002c5be  mov     rax, [r14]
0x18002c5c1  mov     [rsp+160h+var_130], rax
0x18002c5c6  mov     rax, [rcx+0D40h]
0x18002c5cd  mov     rcx, [rdx+10h]
0x18002c5d1  mov     [rsp+160h+var_138], rax
0x18002c5d6  mov     [rsp+160h+var_140], rdi
0x18002c5db  call    WPP_SF_iSii
0x18002c5e0  xor     edi, edi
0x18002c5e2  mov     eax, cs:dword_180173278
0x18002c5e8  cmp     eax, 4
0x18002c5eb  jbe     loc_18002C772
0x18002c5f1  mov     rax, cs:gIkeExtGlobals
0x18002c5f8  test    rax, rax
0x18002c5fb  jz      short loc_18002C626
0x18002c5fd  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002c603  cmp     ecx, 0FFFFFFFFh
0x18002c606  jz      short loc_18002C626
0x18002c608  call    cs:__imp_TlsGetValue
0x18002c60e  test    rax, rax
0x18002c611  jz      short loc_18002C61F
0x18002c613  mov     rcx, [rax]
0x18002c616  mov     rax, cs:gIkeExtGlobals
0x18002c61d  jmp     short loc_18002C629
0x18002c61f  mov     rax, cs:gIkeExtGlobals
0x18002c626  mov     rcx, rdi
0x18002c629  mov     [rsp+160h+var_F0], rcx
0x18002c62e  lea     rcx, [rsp+160h+var_F0]
0x18002c633  mov     [rbp+60h+var_A0], rcx
0x18002c637  mov     [rbp+60h+var_98], 8
0x18002c63f  test    rax, rax
0x18002c642  jz      short loc_18002C693
0x18002c644  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002c64a  cmp     ecx, 0FFFFFFFFh
0x18002c64d  jz      short loc_18002C693
0x18002c64f  call    cs:__imp_TlsGetValue
0x18002c655  test    rax, rax
0x18002c658  lea     rdx, [rax+8]
0x18002c65c  cmovz   rdx, rdi
0x18002c660  test    rdx, rdx
0x18002c663  jz      short loc_18002C68C
0x18002c665  mov     rax, rbx
0x18002c668  nop     dword ptr [rax+rax+00000000h]
0x18002c670  cmp     word ptr [rdx+rax*2+2], 0
0x18002c676  lea     rax, [rax+1]
0x18002c67a  jnz     short loc_18002C670
0x18002c67c  lea     ecx, ds:2[rax*2]
0x18002c683  mov     rax, cs:gIkeExtGlobals
0x18002c68a  jmp     short loc_18002C69F
0x18002c68c  mov     rax, cs:gIkeExtGlobals
0x18002c693  lea     rdx, LocaleName
0x18002c69a  mov     ecx, 2
0x18002c69f  mov     [rbp+60h+var_88], ecx
0x18002c6a2  xor     r9d, r9d
0x18002c6a5  mov     [rbp+60h+var_90], rdx
0x18002c6a9  lea     rcx, aQueryingIfInde; "Querying IF index"
0x18002c6b0  mov     [rbp+60h+var_80], rcx
0x18002c6b4  lea     rdx, [rbp+60h+var_E0]
0x18002c6b8  mov     [rbp+60h+var_84], edi
0x18002c6bb  lea     rcx, _TraceLoggingMetadata
0x18002c6c2  mov     [rbp+60h+var_78], 12h
0x18002c6ca  xor     r8d, r8d
0x18002c6cd  mov     rax, [rax+0D40h]
0x18002c6d4  mov     [rsp+160h+var_E8], rax
0x18002c6d9  lea     rax, [rsp+160h+var_E8]
0x18002c6de  mov     [rbp+60h+var_70], rax
0x18002c6e2  mov     rax, [r14]
0x18002c6e5  mov     [rbp+60h+var_D0], rax
0x18002c6e9  lea     rax, [rbp+60h+var_D0]
0x18002c6ed  mov     [rbp+60h+var_60], rax
0x18002c6f1  movzx   eax, cs:word_180153461
0x18002c6f8  mov     [rbp+60h+var_DC], eax
0x18002c6fb  mov     rax, cs:off_180173280
0x18002c702  mov     [rbp+60h+var_C0], rax
0x18002c706  mov     [rbp+60h+var_68], 8
0x18002c70e  mov     [rbp+60h+var_58], 8
0x18002c716  mov     [rbp+60h+var_E0], 0B000000h
0x18002c71d  mov     [rbp+60h+var_D8], rdi
0x18002c721  movzx   eax, word ptr [rax]
0x18002c724  mov     [rbp+60h+var_B8], eax
0x18002c727  lea     rax, byte_18015346B
0x18002c72e  mov     [rbp+60h+var_B0], rax
0x18002c732  mov     rax, r13
0x18002c735  sub     eax, ecx
0x18002c737  mov     [rbp+60h+var_B4], 2
0x18002c73e  mov     [rbp+60h+var_A8], 50h ; 'P'
0x18002c745  mov     [rbp+60h+var_A4], 1
0x18002c74c  mov     [rsp+160h+var_F8], eax
0x18002c750  mov     eax, [rsp+160h+var_F8]
0x18002c754  mov     rcx, cs:qword_180173298
0x18002c75b  lea     rax, [rbp+60h+var_C0]
0x18002c75f  mov     [rsp+160h+var_138], rax
0x18002c764  mov     dword ptr [rsp+160h+var_140], 7
0x18002c76c  call    cs:__imp_EtwEventWriteTransfer
0x18002c772  mov     rax, cs:gIkeExtGlobals
0x18002c779  mov     rcx, [rax+0D40h]
0x18002c780  mov     [r14], rcx
0x18002c783  movzx   ecx, byte ptr [rsi]
0x18002c786  dec     ecx; switch 8 cases
0x18002c788  cmp     ecx, 7
0x18002c78b  ja      def_18002C7A5; jumptable 000000018002C7A5 default case, cases 2,3
0x18002c791  lea     rdx, __ImageBase
0x18002c798  movsxd  rax, ecx
0x18002c79b  mov     eax, ds:(jpt_18002C7A5 - 180000000h)[rdx+rax*4]
0x18002c7a2  add     rax, rdx
0x18002c7a5  jmp     rax; switch jump
0x18002c7a7  mov     r9d, edi; jumptable 000000018002C7A5 cases 1,4,7
0x18002c7aa  jmp     short loc_18002C7B2
0x18002c7ac  mov     r9d, 1; jumptable 000000018002C7A5 cases 5,6,8
0x18002c7b2  mov     dword ptr [rsp+160h+var_120+4], r9d
0x18002c7b7  cmp     ecx, 7; switch 8 cases
0x18002c7ba  ja      def_18002C7A5; jumptable 000000018002C7A5 default case, cases 2,3
0x18002c7c0  movsxd  rax, ecx
0x18002c7c3  mov     ecx, ds:(jpt_18002C7CD - 180000000h)[rdx+rax*4]
0x18002c7ca  add     rcx, rdx
0x18002c7cd  jmp     rcx; switch jump
0x18002c7cf  lea     rdx, [rsi+8]; jumptable 000000018002C7CD cases 0,3,6
0x18002c7d3  mov     r8d, 4
0x18002c7d9  jmp     short loc_18002C7E5
0x18002c7db  lea     rdx, [rsi+0Ch]; jumptable 000000018002C7CD cases 4,5,7
0x18002c7df  mov     r8d, 10h; Size
0x18002c7e5  lea     rcx, [rsp+160h+var_120+8]; void *
0x18002c7ea  call    memcpy_0
0x18002c7ef  lea     rcx, [rsp+160h+var_120]
0x18002c7f4  mov     qword ptr [rsp+160h+var_110+8], r12
0x18002c7f9  call    WfpPnPLookupLocalIFProperties
0x18002c7fe  mov     rsi, rax
0x18002c801  test    rax, rax
0x18002c804  jnz     loc_18002CA20
0x18002c80a  mov     ecx, dword ptr [rsp+160h+var_100]
0x18002c80e  lea     r8, WPP_GLOBAL_Control
0x18002c815  mov     [r14+8], ecx
0x18002c819  mov     [r15], ecx
0x18002c81c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c823  cmp     rcx, r8
0x18002c826  jz      loc_18002C8CF
0x18002c82c  cmp     byte ptr [rcx+19h], 4
0x18002c830  jb      loc_18002C8CF
0x18002c836  test    byte ptr [rcx+1Ch], 10h
0x18002c83a  jz      loc_18002C8CF
0x18002c840  mov     rdx, cs:gIkeExtGlobals
0x18002c847  test    rdx, rdx
0x18002c84a  jz      short loc_18002C872
0x18002c84c  mov     eax, [rdx+0D88h]
0x18002c852  cmp     eax, 0FFFFFFFFh
0x18002c855  jz      short loc_18002C872
0x18002c857  mov     ecx, eax; dwTlsIndex
0x18002c859  call    cs:__imp_TlsGetValue
0x18002c85f  mov     rdx, cs:gIkeExtGlobals
0x18002c866  mov     r8, rax
0x18002c869  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
