# IkeAddrDump

- ea: `0x1800261c0`
- end: `0x180026c24`
- name: `IkeAddrDump`
- size: `2660`
- prototype: `__int64 __fastcall(__int16 *, unsigned __int8 *)`
- caller_count: `14`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180014b60`
- `0x18002d940`
- `0x1800356c0`
- `0x180038fc0`
- `0x1800738c8`
- `0x18007a28c`
- `0x1800c761c`
- `0x1800c9180`
- `0x1800c9d60`
- `0x1800caaa4`
- `0x1800d3658`
- `0x1800f4130`
- `0x1800f4550`
- `0x1800f68f4`

## callees

- `0x18000b890`
- `0x1800261c0`
- `0x18004890c`
- `0x180050850`
- `0x1800510ee`
- `0x18005e938`
- `0x18005ed00`
- `0x18005eeb4`
- `0x18005f080`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800262c5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002634a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026398`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800265a5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026636`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026684`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800268f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800269a1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800269ed`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800262c5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002634a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026398`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800265a5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026636`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026684`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800268f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800269a1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800269ed`
- `ntdll!RtlIpv6AddressToStringW` at `0x180026843`
- `ntdll!RtlIpv6AddressToStringW` at `0x180026843`
- `ntdll!RtlIpv4AddressToStringW` at `0x180026867`
- `ntdll!RtlIpv4AddressToStringW` at `0x180026867`
- `ntdll!EtwEventWriteTransfer` at `0x1800264ed`
- `ntdll!EtwEventWriteTransfer` at `0x1800264ed`
- `WS2_32!__imp_ntohl` at `0x18002684f`
- `WS2_32!__imp_ntohl` at `0x18002684f`
- `WS2_32!__imp_ntohs` at `0x1800262e0`
- `WS2_32!__imp_ntohs` at `0x180026435`
- `WS2_32!__imp_ntohs` at `0x1800265c0`
- `WS2_32!__imp_ntohs` at `0x180026725`
- `WS2_32!__imp_ntohs` at `0x180026919`
- `WS2_32!__imp_ntohs` at `0x180026925`
- `WS2_32!__imp_ntohs` at `0x180026a95`
- `WS2_32!__imp_ntohs` at `0x180026aea`
- `WS2_32!__imp_ntohs` at `0x1800262e0`
- `WS2_32!__imp_ntohs` at `0x180026435`
- `WS2_32!__imp_ntohs` at `0x1800265c0`
- `WS2_32!__imp_ntohs` at `0x180026725`
- `WS2_32!__imp_ntohs` at `0x180026919`
- `WS2_32!__imp_ntohs` at `0x180026925`
- `WS2_32!__imp_ntohs` at `0x180026a95`
- `WS2_32!__imp_ntohs` at `0x180026aea`

## pseudocode

```c
__int64 __fastcall IkeAddrDump(__int16 *a1, unsigned __int8 *a2)
{
  u_short v4; // si
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v7; // r14
  char v8; // di
  char v9; // bl
  __int64 v10; // rsi
  __int64 v11; // rcx
  __int64 TlsPeerAddr; // rax
  int v13; // edx
  int v14; // r8d
  __int64 result; // rax
  LPCRITICAL_SECTION v16; // rax
  DWORD v17; // ecx
  __int64 *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rbx
  DWORD v21; // ecx
  char *v22; // rax
  const WCHAR *v23; // rcx
  __int64 v24; // rax
  bool v25; // zf
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  u_short v29; // ax
  u_short v30; // di
  DWORD v31; // ecx
  __int64 *v32; // rax
  __int64 v33; // r14
  char v34; // bl
  char v35; // di
  __int64 v36; // rsi
  __int64 v37; // rcx
  __int64 v38; // rax
  int v39; // edx
  int v40; // r8d
  LPCRITICAL_SECTION v41; // rax
  DWORD v42; // ecx
  __int64 *v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rbx
  DWORD v46; // ecx
  char *v47; // rax
  const WCHAR *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  __int64 v51; // rax
  int v52; // eax
  __int64 v53; // rax
  int v54; // ecx
  int v55; // ecx
  u_short v56; // bx
  u_short v57; // di
  DWORD v58; // ecx
  __int64 *v59; // rax
  char v60; // si
  char v61; // bl
  char v62; // di
  __int64 v63; // r14
  __int64 v64; // rcx
  __int64 v65; // rax
  int v66; // edx
  int v67; // r8d
  LPCRITICAL_SECTION v68; // rax
  DWORD v69; // ecx
  __int64 *v70; // rax
  __int64 v71; // rcx
  __int64 v72; // rbx
  DWORD v73; // ecx
  char *v74; // rax
  const WCHAR *v75; // rcx
  __int64 v76; // rax
  int v77; // eax
  __int64 v78; // rax
  int v79; // eax
  __int64 v80; // rax
  u_short v81; // ax
  int v82; // [rsp+20h] [rbp-E0h]
  unsigned int v83; // [rsp+60h] [rbp-A0h] BYREF
  int v84; // [rsp+64h] [rbp-9Ch] BYREF
  struct in_addr v85; // [rsp+68h] [rbp-98h] BYREF
  __int64 v86; // [rsp+70h] [rbp-90h] BYREF
  struct in6_addr Addr; // [rsp+78h] [rbp-88h] BYREF
  __int64 v88; // [rsp+88h] [rbp-78h] BYREF
  __int64 v89; // [rsp+90h] [rbp-70h]
  char *v90; // [rsp+A0h] [rbp-60h] BYREF
  int v91; // [rsp+A8h] [rbp-58h]
  int v92; // [rsp+ACh] [rbp-54h]
  int *v93; // [rsp+B0h] [rbp-50h]
  int v94; // [rsp+B8h] [rbp-48h]
  int v95; // [rsp+BCh] [rbp-44h]
  __int64 *v96; // [rsp+C0h] [rbp-40h]
  __int64 v97; // [rsp+C8h] [rbp-38h]
  const WCHAR *v98; // [rsp+D0h] [rbp-30h]
  int v99; // [rsp+D8h] [rbp-28h]
  int v100; // [rsp+DCh] [rbp-24h]
  __int16 *v101; // [rsp+E0h] [rbp-20h]
  int v102; // [rsp+E8h] [rbp-18h]
  int v103; // [rsp+ECh] [rbp-14h]
  WCHAR *v104; // [rsp+F0h] [rbp-10h]
  int v105; // [rsp+F8h] [rbp-8h]
  int v106; // [rsp+FCh] [rbp-4h]
  struct in_addr *v107; // [rsp+100h] [rbp+0h]
  __int64 v108; // [rsp+108h] [rbp+8h]
  WCHAR *v109; // [rsp+110h] [rbp+10h]
  __int64 v110; // [rsp+118h] [rbp+18h]
  int *v111; // [rsp+120h] [rbp+20h]
  __int64 v112; // [rsp+128h] [rbp+28h]
  __int64 *v113; // [rsp+130h] [rbp+30h]
  __int64 v114; // [rsp+138h] [rbp+38h]
  WCHAR v115[80]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR S[80]; // [rsp+1E0h] [rbp+E0h] BYREF
  _WORD v117[80]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(v115, 0, sizeof(v115));
  memset_0(S, 0, sizeof(S));
  memset_0(v117, 0, sizeof(v117));
  switch ( *a2 )
  {
    case 1u:
    case 5u:
      IkeAddrGetAddrString(a2, v115);
      switch ( *a2 )
      {
        case 1u:
        case 4u:
        case 5u:
        case 6u:
        case 7u:
        case 8u:
          v4 = *((_WORD *)a2 + 3);
          LOWORD(v83) = v4;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            if ( gIkeExtGlobals
              && (LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore, LockSemaphore != -1)
              && (Value = (__int64 *)TlsGetValue(LockSemaphore)) != 0 )
            {
              v7 = *Value;
            }
            else
            {
              LODWORD(v7) = 0;
            }
            v8 = a2[1];
            v9 = ntohs(v4);
            v10 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            TlsPeerAddr = IkeGetTlsPeerAddr(v11);
            WPP_SF_iSsSdd(v10, v13, v14, v7, TlsPeerAddr, (__int64)a1, (__int64)v115, v9, v8);
            v4 = v83;
          }
          result = (unsigned int)dword_180173278;
          if ( (unsigned int)dword_180173278 <= 4 )
            return result;
          v16 = gIkeExtGlobals;
          if ( !gIkeExtGlobals )
            goto LABEL_18;
          v17 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
          if ( v17 == -1 )
            goto LABEL_18;
          v18 = (__int64 *)TlsGetValue(v17);
          if ( v18 )
          {
            v19 = *v18;
            v16 = gIkeExtGlobals;
          }
          else
          {
            v16 = gIkeExtGlobals;
LABEL_18:
            v19 = 0;
          }
          v86 = v19;
          v96 = &v86;
          v20 = -1;
          v97 = 8;
          if ( !v16 )
            goto LABEL_27;
          v21 = (DWORD)v16[86].LockSemaphore;
          if ( v21 == -1 )
            goto LABEL_27;
          v22 = (char *)TlsGetValue(v21);
          v23 = (const WCHAR *)(v22 + 8);
          if ( !v22 )
            v23 = 0;
          if ( v23 )
          {
            v24 = -1;
            do
              v25 = v23[++v24] == 0;
            while ( !v25 );
            v26 = 2 * v24 + 2;
          }
          else
          {
LABEL_27:
            v23 = &LocaleName;
            v26 = 2;
          }
          v98 = v23;
          v99 = v26;
          v100 = 0;
          if ( a1 )
          {
            v27 = -1;
            do
              ++v27;
            while ( *((_BYTE *)a1 + v27) );
            v28 = v27 + 1;
          }
          else
          {
            a1 = word_180122432;
            v28 = 1;
          }
          v102 = v28;
          v101 = a1;
          v103 = 0;
          do
            v25 = v115[++v20] == 0;
          while ( !v25 );
          v106 = 0;
          v104 = v115;
          v105 = 2 * v20 + 2;
          v29 = ntohs(v4);
          v108 = 4;
          v84 = v29;
          v107 = (struct in_addr *)&v84;
          v83 = a2[1];
          v109 = (WCHAR *)&v83;
          v90 = off_180173280;
          v110 = 4;
          v88 = 0x40B000000LL;
          v89 = 0;
          v91 = *(unsigned __int16 *)off_180173280;
          v93 = &dword_18014F924;
          v92 = 2;
          v94 = 73;
          v95 = 1;
          v85 = (struct in_addr)((unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata);
          v82 = 8;
          break;
        default:
          goto LABEL_118;
      }
      return EtwEventWriteTransfer(qword_180173298, &v88, 0, 0, v82, &v90);
    case 4u:
    case 6u:
      IkeAddrGetAddrString(a2, v115);
      IkeAddrGetMaskString(a2, v117);
      switch ( *a2 )
      {
        case 1u:
        case 4u:
        case 5u:
        case 6u:
        case 7u:
        case 8u:
          v30 = *((_WORD *)a2 + 3);
          LOWORD(v83) = v30;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            if ( gIkeExtGlobals
              && (v31 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v31 != -1)
              && (v32 = (__int64 *)TlsGetValue(v31)) != 0 )
            {
              v33 = *v32;
            }
            else
            {
              LODWORD(v33) = 0;
            }
            v34 = a2[1];
            v35 = ntohs(v30);
            v36 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            v38 = IkeGetTlsPeerAddr(v37);
            WPP_SF_iSsSdSd(v36, v39, v40, v33, v38, (__int64)a1, (__int64)v115, v35, (__int64)v117, v34);
            v30 = v83;
          }
          result = (unsigned int)dword_180173278;
          if ( (unsigned int)dword_180173278 <= 4 )
            return result;
          v41 = gIkeExtGlobals;
          if ( !gIkeExtGlobals )
            goto LABEL_54;
          v42 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
          if ( v42 == -1 )
            goto LABEL_54;
          v43 = (__int64 *)TlsGetValue(v42);
          if ( v43 )
          {
            v44 = *v43;
            v41 = gIkeExtGlobals;
          }
          else
          {
            v41 = gIkeExtGlobals;
LABEL_54:
            v44 = 0;
          }
          v86 = v44;
          v96 = &v86;
          v45 = -1;
          v97 = 8;
          if ( !v41 )
            goto LABEL_63;
          v46 = (DWORD)v41[86].LockSemaphore;
          if ( v46 == -1 )
            goto LABEL_63;
          v47 = (char *)TlsGetValue(v46);
          v48 = (const WCHAR *)(v47 + 8);
          if ( !v47 )
            v48 = 0;
          if ( v48 )
          {
            v49 = -1;
            do
              v25 = v48[++v49] == 0;
            while ( !v25 );
            v50 = 2 * v49 + 2;
          }
          else
          {
LABEL_63:
            v48 = &LocaleName;
            v50 = 2;
          }
          v98 = v48;
          v99 = v50;
          v100 = 0;
          if ( a1 )
          {
            v51 = -1;
            do
              ++v51;
            while ( *((_BYTE *)a1 + v51) );
            v52 = v51 + 1;
          }
          else
          {
            a1 = word_180122432;
            v52 = 1;
          }
          v102 = v52;
          v53 = -1;
          v101 = a1;
          v103 = 0;
          do
            v25 = v115[++v53] == 0;
          while ( !v25 );
          v106 = 0;
          v104 = v115;
          v105 = 2 * v53 + 2;
          v85 = (struct in_addr)ntohs(v30);
          v107 = &v85;
          v108 = 4;
          do
            v25 = v117[++v45] == 0;
          while ( !v25 );
          v109 = v117;
          v112 = 4;
          v110 = (unsigned int)(2 * v45 + 2);
          v84 = a2[1];
          v111 = &v84;
          v90 = off_180173280;
          v88 = 0x40B000000LL;
          v89 = 0;
          v91 = *(unsigned __int16 *)off_180173280;
          v93 = (int *)byte_18014F8C3;
          v92 = 2;
          v94 = 85;
          v95 = 1;
          v83 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          v82 = 9;
          break;
        default:
          goto LABEL_118;
      }
      return EtwEventWriteTransfer(qword_180173298, &v88, 0, 0, v82, &v90);
    case 7u:
    case 8u:
      IkeAddrGetAddrString(a2, v115);
      v54 = *a2;
      S[0] = 0;
      v55 = v54 - 7;
      if ( v55 )
      {
        if ( v55 != 1 )
LABEL_118:
          __fastfail(5u);
        Addr = *(struct in6_addr *)(a2 + 40);
        RtlIpv6AddressToStringW(&Addr, S);
      }
      else
      {
        v85 = (struct in_addr)_byteswap_ulong(ntohl(*((_DWORD *)a2 + 6)));
        RtlIpv4AddressToStringW(&v85, S);
      }
      switch ( *a2 )
      {
        case 1u:
        case 4u:
        case 5u:
        case 6u:
        case 7u:
        case 8u:
          if ( *a2 == 7 )
          {
            v56 = *((_WORD *)a2 + 11);
            goto LABEL_83;
          }
          if ( *a2 != 8 )
            goto LABEL_118;
          v56 = *((_WORD *)a2 + 17);
LABEL_83:
          LOWORD(v83) = v56;
          v57 = *((_WORD *)a2 + 3);
          LOWORD(v84) = v57;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            if ( gIkeExtGlobals
              && (v58 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v58 != -1)
              && (v59 = (__int64 *)TlsGetValue(v58)) != 0 )
            {
              v86 = *v59;
            }
            else
            {
              v86 = 0;
            }
            v60 = a2[1];
            v61 = ntohs(v56);
            v62 = ntohs(v57);
            v63 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            v65 = IkeGetTlsPeerAddr(v64);
            WPP_SF_iSsSdSdd(v63, v66, v67, v86, v65, (__int64)a1, (__int64)v115, v62, (__int64)S, v61, v60);
            v57 = v84;
          }
          result = (unsigned int)dword_180173278;
          if ( (unsigned int)dword_180173278 > 4 )
          {
            v68 = gIkeExtGlobals;
            if ( gIkeExtGlobals )
            {
              v69 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
              if ( v69 != -1 )
              {
                v70 = (__int64 *)TlsGetValue(v69);
                if ( v70 )
                {
                  v71 = *v70;
                  v68 = gIkeExtGlobals;
LABEL_99:
                  v88 = v71;
                  v96 = &v88;
                  v72 = -1;
                  v97 = 8;
                  if ( !v68 )
                    goto LABEL_107;
                  v73 = (DWORD)v68[86].LockSemaphore;
                  if ( v73 == -1 )
                    goto LABEL_107;
                  v74 = (char *)TlsGetValue(v73);
                  v75 = (const WCHAR *)(v74 + 8);
                  if ( !v74 )
                    v75 = 0;
                  if ( v75 )
                  {
                    v76 = -1;
                    do
                      v25 = v75[++v76] == 0;
                    while ( !v25 );
                    v77 = 2 * v76 + 2;
                  }
                  else
                  {
LABEL_107:
                    v75 = &LocaleName;
                    v77 = 2;
                  }
                  v98 = v75;
                  v99 = v77;
                  v100 = 0;
                  if ( a1 )
                  {
                    v78 = -1;
                    do
                      ++v78;
                    while ( *((_BYTE *)a1 + v78) );
                    v79 = v78 + 1;
                  }
                  else
                  {
                    a1 = word_180122432;
                    v79 = 1;
                  }
                  v102 = v79;
                  v80 = -1;
                  v101 = a1;
                  v103 = 0;
                  do
                    v25 = v115[++v80] == 0;
                  while ( !v25 );
                  v106 = 0;
                  v104 = v115;
                  v105 = 2 * v80 + 2;
                  v85 = (struct in_addr)ntohs(v57);
                  v107 = &v85;
                  v108 = 4;
                  do
                    v25 = S[++v72] == 0;
                  while ( !v25 );
                  v109 = S;
                  v110 = (unsigned int)(2 * v72 + 2);
                  v81 = ntohs(v83);
                  v112 = 4;
                  v84 = v81;
                  v111 = &v84;
                  LODWORD(v86) = a2[1];
                  v113 = &v86;
                  v90 = off_180173280;
                  v114 = 4;
                  Addr = (struct in6_addr)0x40B000000uLL;
                  v91 = *(unsigned __int16 *)off_180173280;
                  v93 = &dword_18014F864;
                  v92 = 2;
                  v94 = 83;
                  v95 = 1;
                  v83 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                  return EtwEventWriteTransfer(qword_180173298, &Addr, 0, 0, 10, &v90);
                }
                v68 = gIkeExtGlobals;
              }
            }
            v71 = 0;
            goto LABEL_99;
          }
          return result;
        default:
          goto LABEL_118;
      }
    default:
      goto LABEL_118;
  }
}

```

## disassembly

```asm
0x1800261c0  mov     [rsp-8+arg_10], rbx
0x1800261c5  push    rbp
0x1800261c6  push    rsi
0x1800261c7  push    rdi
0x1800261c8  push    r12
0x1800261ca  push    r13
0x1800261cc  push    r14
0x1800261ce  push    r15
0x1800261d0  lea     rbp, [rsp-230h]
0x1800261d8  sub     rsp, 330h
0x1800261df  mov     rax, cs:__security_cookie
0x1800261e6  xor     rax, rsp
0x1800261e9  mov     [rbp+260h+var_40], rax
0x1800261f0  mov     r13, rdx
0x1800261f3  mov     r15, rcx
0x1800261f6  xor     edx, edx; Val
0x1800261f8  lea     rcx, [rbp+260h+var_220]; void *
0x1800261fc  mov     r8d, 0A0h; Size
0x180026202  call    memset_0
0x180026207  xor     edx, edx; Val
0x180026209  lea     rcx, [rbp+260h+S]; void *
0x180026210  mov     r8d, 0A0h; Size
0x180026216  call    memset_0
0x18002621b  xor     edx, edx; Val
0x18002621d  lea     rcx, [rbp+260h+var_E0]; void *
0x180026224  mov     r8d, 0A0h; Size
0x18002622a  call    memset_0
0x18002622f  movzx   eax, byte ptr [r13+0]
0x180026234  dec     eax; switch 8 cases
0x180026236  cmp     eax, 7
0x180026239  ja      def_180026252; jumptable 0000000180026252 default case, cases 2,3
0x18002623f  cdqe
0x180026241  lea     rbx, __ImageBase
0x180026248  mov     eax, ds:(jpt_180026252 - 180000000h)[rbx+rax*4]
0x18002624f  add     rax, rbx
0x180026252  jmp     rax; switch jump
0x180026254  lea     rdx, [rbp+260h+var_220]; jumptable 0000000180026252 cases 1,5
0x180026258  mov     rcx, r13
0x18002625b  call    IkeAddrGetAddrString
0x180026260  movzx   eax, byte ptr [r13+0]
0x180026265  dec     eax; switch 8 cases
0x180026267  cmp     eax, 7
0x18002626a  ja      def_180026252; jumptable 0000000180026252 default case, cases 2,3
0x180026270  cdqe
0x180026272  mov     ecx, ds:(jpt_18002627C - 180000000h)[rbx+rax*4]
0x180026279  add     rcx, rbx
0x18002627c  jmp     rcx; switch jump
0x18002627e  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000018002627C cases 1,4-8
0x180026285  lea     rax, WPP_GLOBAL_Control
0x18002628c  movzx   esi, word ptr [r13+6]
0x180026291  xor     r12d, r12d
0x180026294  mov     word ptr [rsp+360h+var_300], si
0x180026299  cmp     rcx, rax
0x18002629c  jz      loc_180026324
0x1800262a2  cmp     byte ptr [rcx+19h], 4
0x1800262a6  jb      short loc_180026324
0x1800262a8  test    byte ptr [rcx+1Ch], 10h
0x1800262ac  jz      short loc_180026324
0x1800262ae  mov     rax, cs:gIkeExtGlobals
0x1800262b5  test    rax, rax
0x1800262b8  jz      short loc_1800262D5
0x1800262ba  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800262c0  cmp     ecx, 0FFFFFFFFh
0x1800262c3  jz      short loc_1800262D5
0x1800262c5  call    cs:__imp_TlsGetValue
0x1800262cb  test    rax, rax
0x1800262ce  jz      short loc_1800262D5
0x1800262d0  mov     r14, [rax]
0x1800262d3  jmp     short loc_1800262D8
0x1800262d5  mov     r14, r12
0x1800262d8  movzx   edi, byte ptr [r13+1]
0x1800262dd  movzx   ecx, si; netshort
0x1800262e0  call    cs:__imp_ntohs
0x1800262e6  movzx   ebx, ax
0x1800262e9  mov     rax, cs:WPP_GLOBAL_Control
0x1800262f0  mov     rsi, [rax+10h]
0x1800262f4  call    IkeGetTlsPeerAddr
0x1800262f9  mov     dword ptr [rsp+360h+var_320], edi
0x1800262fd  lea     rcx, [rbp+260h+var_220]
0x180026301  mov     [rsp+360h+var_328], ebx
0x180026305  mov     r9, r14
0x180026308  mov     [rsp+360h+var_330], rcx
0x18002630d  mov     rcx, rsi
0x180026310  mov     [rsp+360h+var_338], r15
0x180026315  mov     [rsp+360h+var_340], rax
0x18002631a  call    WPP_SF_iSsSdd
0x18002631f  movzx   esi, word ptr [rsp+360h+var_300]
0x180026324  mov     eax, cs:dword_180173278
0x18002632a  cmp     eax, 4
0x18002632d  jbe     loc_1800264F3
0x180026333  mov     rax, cs:gIkeExtGlobals
0x18002633a  test    rax, rax
0x18002633d  jz      short loc_180026368
0x18002633f  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180026345  cmp     ecx, 0FFFFFFFFh
0x180026348  jz      short loc_180026368
0x18002634a  call    cs:__imp_TlsGetValue
0x180026350  test    rax, rax
0x180026353  jz      short loc_180026361
0x180026355  mov     rcx, [rax]
0x180026358  mov     rax, cs:gIkeExtGlobals
0x18002635f  jmp     short loc_18002636B
0x180026361  mov     rax, cs:gIkeExtGlobals
0x180026368  mov     rcx, r12
0x18002636b  mov     [rsp+360h+var_2F0], rcx
0x180026370  lea     rcx, [rsp+360h+var_2F0]
0x180026375  mov     [rbp+260h+var_2A0], rcx
0x180026379  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180026380  mov     [rbp+260h+var_298], 8
0x180026388  test    rax, rax
0x18002638b  jz      short loc_1800263C6
0x18002638d  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180026393  cmp     ecx, 0FFFFFFFFh
0x180026396  jz      short loc_1800263C6
0x180026398  call    cs:__imp_TlsGetValue
0x18002639e  test    rax, rax
0x1800263a1  lea     rcx, [rax+8]
0x1800263a5  cmovz   rcx, r12
0x1800263a9  test    rcx, rcx
0x1800263ac  jz      short loc_1800263C6
0x1800263ae  mov     rax, rbx
0x1800263b1  cmp     [rcx+rax*2+2], r12w
0x1800263b7  lea     rax, [rax+1]
0x1800263bb  jnz     short loc_1800263B1
0x1800263bd  lea     eax, ds:2[rax*2]
0x1800263c4  jmp     short loc_1800263D2
0x1800263c6  lea     rcx, LocaleName
0x1800263cd  mov     eax, 2
0x1800263d2  mov     [rbp+260h+var_290], rcx
0x1800263d6  mov     [rbp+260h+var_288], eax
0x1800263d9  mov     [rbp+260h+var_284], r12d
0x1800263dd  test    r15, r15
0x1800263e0  jz      short loc_1800263F2
0x1800263e2  mov     rax, rbx
0x1800263e5  inc     rax
0x1800263e8  cmp     [r15+rax], r12b
0x1800263ec  jnz     short loc_1800263E5
0x1800263ee  inc     eax
0x1800263f0  jmp     short loc_1800263FE
0x1800263f2  lea     r15, word_180122432
0x1800263f9  mov     eax, 1
0x1800263fe  mov     [rbp+260h+var_278], eax
0x180026401  lea     rax, [rbp+260h+var_220]
0x180026405  mov     [rbp+260h+var_280], r15
0x180026409  mov     [rbp+260h+var_274], r12d
0x18002640d  nop     dword ptr [rax]
0x180026410  cmp     [rax+rbx*2+2], r12w
0x180026416  lea     rbx, [rbx+1]
0x18002641a  jnz     short loc_180026410
0x18002641c  lea     rax, [rbp+260h+var_220]
0x180026420  mov     [rbp+260h+var_264], r12d
0x180026424  mov     [rbp+260h+var_270], rax
0x180026428  movzx   ecx, si; netshort
0x18002642b  lea     eax, ds:2[rbx*2]
0x180026432  mov     [rbp+260h+var_268], eax
0x180026435  call    cs:__imp_ntohs
0x18002643b  mov     [rbp+260h+var_258], 4
0x180026443  lea     rcx, _TraceLoggingMetadata
0x18002644a  movzx   eax, ax
0x18002644d  mov     [rsp+360h+var_2FC], eax
0x180026451  lea     rax, [rsp+360h+var_2FC]
0x180026456  mov     [rbp+260h+var_260], rax
0x18002645a  movzx   eax, byte ptr [r13+1]
0x18002645f  mov     [rsp+360h+var_300], eax
0x180026463  lea     rax, [rsp+360h+var_300]
0x180026468  mov     [rbp+260h+var_250], rax
0x18002646c  movzx   eax, cs:word_18014F91A
0x180026473  mov     dword ptr [rbp+260h+var_2D8+4], eax
0x180026476  mov     rax, cs:off_180173280
0x18002647d  mov     [rbp+260h+var_2C0], rax
0x180026481  mov     [rbp+260h+var_248], 4
0x180026489  mov     dword ptr [rbp+260h+var_2D8], 0B000000h
0x180026490  mov     [rbp+260h+var_2D0], r12
0x180026494  movzx   eax, word ptr [rax]
0x180026497  mov     [rbp+260h+var_2B8], eax
0x18002649a  lea     rax, dword_18014F924
0x1800264a1  mov     [rbp+260h+var_2B0], rax
0x1800264a5  lea     rax, _TraceLoggingMetadataEnd
0x1800264ac  sub     eax, ecx
0x1800264ae  mov     [rbp+260h+var_2B4], 2
0x1800264b5  mov     [rbp+260h+var_2A8], 49h ; 'I'
0x1800264bc  mov     [rbp+260h+var_2A4], 1
0x1800264c3  mov     dword ptr [rsp+360h+var_2F8.S_un], eax
0x1800264c7  mov     eax, dword ptr [rsp+360h+var_2F8.S_un]
0x1800264cb  lea     rax, [rbp+260h+var_2C0]
0x1800264cf  mov     [rsp+360h+var_338], rax
0x1800264d4  mov     dword ptr [rsp+360h+var_340], 8
0x1800264dc  lea     rdx, [rbp+260h+var_2D8]
0x1800264e0  mov     rcx, cs:qword_180173298
0x1800264e7  xor     r9d, r9d
0x1800264ea  xor     r8d, r8d
0x1800264ed  call    cs:__imp_EtwEventWriteTransfer
0x1800264f3  mov     rcx, [rbp+260h+var_40]
0x1800264fa  xor     rcx, rsp; StackCookie
0x1800264fd  call    __security_check_cookie
0x180026502  mov     rbx, [rsp+360h+arg_10]
0x18002650a  add     rsp, 330h
0x180026511  pop     r15
0x180026513  pop     r14
0x180026515  pop     r13
0x180026517  pop     r12
0x180026519  pop     rdi
0x18002651a  pop     rsi
0x18002651b  pop     rbp
0x18002651c  retn
0x18002651d  lea     rdx, [rbp+260h+var_220]; jumptable 0000000180026252 cases 4,6
0x180026521  mov     rcx, r13
0x180026524  call    IkeAddrGetAddrString
0x180026529  lea     rdx, [rbp+260h+var_E0]
0x180026530  mov     rcx, r13
0x180026533  call    IkeAddrGetMaskString
0x180026538  movzx   eax, byte ptr [r13+0]
0x18002653d  dec     eax; switch 8 cases
0x18002653f  cmp     eax, 7
0x180026542  ja      def_180026252; jumptable 0000000180026252 default case, cases 2,3
0x180026548  cdqe
0x18002654a  mov     ecx, ds:(jpt_180026554 - 180000000h)[rbx+rax*4]
0x180026551  add     rcx, rbx
0x180026554  jmp     rcx; switch jump
0x180026556  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000180026554 cases 1,4-8
0x18002655d  lea     rax, WPP_GLOBAL_Control
0x180026564  movzx   edi, word ptr [r13+6]
0x180026569  xor     r12d, r12d
0x18002656c  mov     word ptr [rsp+360h+var_300], di
0x180026571  cmp     rcx, rax
0x180026574  jz      loc_180026610
0x18002657a  cmp     byte ptr [rcx+19h], 4
0x18002657e  jb      loc_180026610
0x180026584  test    byte ptr [rcx+1Ch], 10h
0x180026588  jz      loc_180026610
0x18002658e  mov     rax, cs:gIkeExtGlobals
0x180026595  test    rax, rax
0x180026598  jz      short loc_1800265B5
0x18002659a  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800265a0  cmp     ecx, 0FFFFFFFFh
0x1800265a3  jz      short loc_1800265B5
0x1800265a5  call    cs:__imp_TlsGetValue
0x1800265ab  test    rax, rax
0x1800265ae  jz      short loc_1800265B5
0x1800265b0  mov     r14, [rax]
0x1800265b3  jmp     short loc_1800265B8
0x1800265b5  mov     r14, r12
0x1800265b8  movzx   ebx, byte ptr [r13+1]
0x1800265bd  movzx   ecx, di; netshort
0x1800265c0  call    cs:__imp_ntohs
0x1800265c6  movzx   edi, ax
0x1800265c9  mov     rax, cs:WPP_GLOBAL_Control
0x1800265d0  mov     rsi, [rax+10h]
0x1800265d4  call    IkeGetTlsPeerAddr
0x1800265d9  mov     [rsp+360h+var_318], ebx
0x1800265dd  lea     rcx, [rbp+260h+var_E0]
0x1800265e4  mov     [rsp+360h+var_320], rcx
0x1800265e9  mov     r9, r14
0x1800265ec  mov     [rsp+360h+var_328], edi
0x1800265f0  lea     rcx, [rbp+260h+var_220]
0x1800265f4  mov     [rsp+360h+var_330], rcx
0x1800265f9  mov     rcx, rsi
0x1800265fc  mov     [rsp+360h+var_338], r15
0x180026601  mov     [rsp+360h+var_340], rax
0x180026606  call    WPP_SF_iSsSdSd
0x18002660b  movzx   edi, word ptr [rsp+360h+var_300]
0x180026610  mov     eax, cs:dword_180173278
0x180026616  cmp     eax, 4
0x180026619  jbe     loc_1800264F3
0x18002661f  mov     rax, cs:gIkeExtGlobals
0x180026626  test    rax, rax
0x180026629  jz      short loc_180026654
0x18002662b  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180026631  cmp     ecx, 0FFFFFFFFh
0x180026634  jz      short loc_180026654
0x180026636  call    cs:__imp_TlsGetValue
0x18002663c  test    rax, rax
0x18002663f  jz      short loc_18002664D
0x180026641  mov     rcx, [rax]
0x180026644  mov     rax, cs:gIkeExtGlobals
0x18002664b  jmp     short loc_180026657
0x18002664d  mov     rax, cs:gIkeExtGlobals
0x180026654  mov     rcx, r12
0x180026657  mov     [rsp+360h+var_2F0], rcx
0x18002665c  lea     rcx, [rsp+360h+var_2F0]
0x180026661  mov     [rbp+260h+var_2A0], rcx
0x180026665  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18002666c  mov     [rbp+260h+var_298], 8
0x180026674  test    rax, rax
0x180026677  jz      short loc_1800266B5
0x180026679  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002667f  cmp     ecx, 0FFFFFFFFh
0x180026682  jz      short loc_1800266B5
0x180026684  call    cs:__imp_TlsGetValue
0x18002668a  test    rax, rax
0x18002668d  lea     rcx, [rax+8]
0x180026691  cmovz   rcx, r12
0x180026695  test    rcx, rcx
0x180026698  jz      short loc_1800266B5
0x18002669a  mov     rax, rbx
0x18002669d  nop     dword ptr [rax]
0x1800266a0  cmp     [rcx+rax*2+2], r12w
0x1800266a6  lea     rax, [rax+1]
0x1800266aa  jnz     short loc_1800266A0
0x1800266ac  lea     eax, ds:2[rax*2]
  ... truncated ...
```
