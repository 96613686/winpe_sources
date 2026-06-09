# FwMoneisCreateInterfaceContainer

- ea: `0x1800be78c`
- end: `0x1800beeb9`
- name: `FwMoneisCreateInterfaceContainer`
- size: `1837`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800bcae0`
- `0x1800c6910`

## callees

- `0x18000ae9c`
- `0x180027fc0`
- `0x18003d0d8`
- `0x18003d5b0`
- `0x180050a6c`
- `0x18006a41c`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800be064`
- `0x1800be78c`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800beada`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800beada`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800be8e4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800be8e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bee87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bee87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be954`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be954`
- `fwbase!FwHResultToWindowsError` at `0x1800be8ec`
- `fwbase!FwHResultToWindowsError` at `0x1800be969`
- `fwbase!FwHResultToWindowsError` at `0x1800be9c1`
- `fwbase!FwHResultToWindowsError` at `0x1800be8ec`
- `fwbase!FwHResultToWindowsError` at `0x1800be969`
- `fwbase!FwHResultToWindowsError` at `0x1800be9c1`
- `fwbase!FwStringBuild` at `0x1800becdb`
- `fwbase!FwStringBuild` at `0x1800bed12`
- `fwbase!FwStringBuild` at `0x1800becdb`
- `fwbase!FwStringBuild` at `0x1800bed12`
- `fwbase!FwFree` at `0x1800beddc`
- `fwbase!FwFree` at `0x1800bedf3`
- `fwbase!FwFree` at `0x1800bee54`
- `fwbase!FwFree` at `0x1800bee6b`
- `fwbase!FwFree` at `0x1800beddc`
- `fwbase!FwFree` at `0x1800bedf3`
- `fwbase!FwFree` at `0x1800bee54`
- `fwbase!FwFree` at `0x1800bee6b`

## string_xrefs

- `0x1800be922`: `StringFromCLSID`
- `0x1800be8ce`: `FwMoneisOpenIfIsoStore`
- `0x1800be9f8`: `StringCchCopy`
- `0x1800be9a0`: `CoTaskMemAlloc`

## pseudocode

```c
__int64 __fastcall FwMoneisCreateInterfaceContainer(
        __int64 a1,
        const IID *a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        unsigned int a6,
        unsigned int a7,
        __int64 a8,
        LPCWSTR lpString1)
{
  const unsigned __int16 *v9; // rsi
  unsigned int v12; // ebx
  __int64 v13; // rax
  int v14; // edx
  const char *v15; // rcx
  unsigned int v16; // eax
  const WCHAR *v17; // rax
  __int64 v18; // rax
  unsigned __int64 v19; // r14
  OLECHAR *v20; // rax
  unsigned int v21; // eax
  _DWORD *v22; // rax
  void *v23; // r14
  unsigned int v24; // esi
  __int64 v25; // r10
  int v26; // edx
  const IID *v27; // r15
  __int64 v28; // rdx
  _OWORD *v29; // rax
  char *v30; // rcx
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int64 v44; // rax
  int v45; // eax
  __int64 v46; // rcx
  int v47; // eax
  __int64 v48; // rcx
  _DWORD *v49; // rax
  int v50; // eax
  __int64 v51; // rax
  unsigned int i; // edi
  void *v55; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v56; // [rsp+40h] [rbp-C0h]
  const IID *v57; // [rsp+48h] [rbp-B8h]
  __int64 v58; // [rsp+50h] [rbp-B0h]
  LPOLESTR lpsz; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v60; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v61; // [rsp+70h] [rbp-90h] BYREF
  __int64 v62; // [rsp+78h] [rbp-88h] BYREF
  char v63[8]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v64; // [rsp+88h] [rbp-78h]
  __int64 v65; // [rsp+98h] [rbp-68h]
  __int64 v66; // [rsp+A0h] [rbp-60h]
  int v67; // [rsp+A8h] [rbp-58h]
  int v68; // [rsp+ACh] [rbp-54h]
  __int16 v69; // [rsp+B0h] [rbp-50h]
  BOOL v70; // [rsp+178h] [rbp+78h]
  const IID *v71; // [rsp+180h] [rbp+80h]
  int v72; // [rsp+1A0h] [rbp+A0h]
  __int16 v73; // [rsp+1A4h] [rbp+A4h]
  LPOLESTR v74; // [rsp+1B8h] [rbp+B8h]
  int v75; // [rsp+210h] [rbp+110h]
  _DWORD *v76; // [rsp+218h] [rbp+118h]
  __int16 v77; // [rsp+228h] [rbp+128h]

  v9 = lpString1;
  v56 = a3;
  v57 = a2;
  v58 = a8;
  lpsz = 0;
  v55 = 0;
  memset_0(v63, 0, 0x1F8u);
  v61 = 0;
  v62 = 0;
  v60 = 0;
  if ( a5 && *a5 == 2 && (v12 = FwMoneisEdpNamesStringToNetNames(*((_QWORD *)a5 + 1), L",", &v60)) != 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v14 = 22;
      v15 = "FwMoneisEdpNamesStringToNetNames";
LABEL_7:
      WPP_SF_Ds(*(_QWORD *)(v13 + 16), v14, (unsigned int)"A", v12, (__int64)v15);
    }
  }
  else
  {
    v12 = FwMoneisOpenIfIsoStore(a6, &v55);
    if ( !v12 )
    {
      if ( a2 )
      {
        v16 = StringFromCLSID(a2, &lpsz);
        v12 = FwHResultToWindowsError(v16);
        if ( v12 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v14 = 24;
            v15 = "StringFromCLSID";
            goto LABEL_7;
          }
          goto LABEL_92;
        }
      }
      else
      {
        v17 = L"AllInterfacesContainerGroupIdzzz";
        if ( lpString1 )
          v17 = lpString1;
        v9 = v17;
        v18 = -1;
        do
          ++v18;
        while ( v9[v18] );
        v19 = v18 + 1;
        v20 = (OLECHAR *)CoTaskMemAlloc(2 * (v18 + 1));
        lpsz = v20;
        if ( !v20 )
        {
          v12 = FwHResultToWindowsError(2147942414LL);
          if ( v12 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v14 = 25;
              v15 = "CoTaskMemAlloc";
              goto LABEL_7;
            }
            goto LABEL_92;
          }
          v20 = lpsz;
        }
        v21 = StringCchCopyW(v20, v19, v9);
        v12 = FwHResultToWindowsError(v21);
        if ( v12 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v14 = 26;
            v15 = "StringCchCopy";
            goto LABEL_7;
          }
          goto LABEL_92;
        }
      }
      memset_0(v63, 0, 0x1F8u);
      v73 = 1;
      v65 = a3;
      v64 = 545;
      v66 = a4;
      v74 = lpsz;
      v69 = 256;
      v71 = a2;
      v70 = a2 != 0;
      v67 = 0x7FFFFFFF;
      if ( a5 )
      {
        if ( *a5 )
        {
          if ( *a5 == 1 )
          {
            v75 = 1;
            v22 = a5 + 2;
          }
          else
          {
            v75 = v60;
            v22 = (_DWORD *)*((_QWORD *)&v60 + 1);
          }
          v76 = v22;
        }
        else
        {
          v67 = a5[2];
        }
      }
      if ( (a6 & 8) != 0 )
        v77 |= 0x80u;
      v72 = ((a6 & 0x10) != 0) + 2;
      if ( !lstrcmpiW(v9, L"EDPAllInterfacesContainerGroupIdzzz") )
        v77 |= 0x400u;
      v68 = 1;
      v23 = v55;
      v24 = 0;
      v12 = FwMoneisAddRule(v55, v63, 0);
      if ( v12 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_92;
        v26 = 27;
      }
      else
      {
        v68 = 2;
        v12 = FwMoneisAddRule(v23, v63, 0);
        if ( !v12 )
        {
          v77 &= ~0x80u;
          v12 = FwMoneisAddCoreNetworkingToInterfaceContainer(v23, a6, (struct _tag_FW_RULE *)v63);
          if ( v12 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v14 = 29;
              v15 = "FwMoneisAddCoreNetworkingToInterfaceContainer";
              goto LABEL_7;
            }
          }
          else
          {
            v27 = v57;
            while ( 1 )
            {
              v28 = 3;
              if ( v24 >= a7 )
                break;
              v29 = (_OWORD *)(504LL * v24 + v58);
              v30 = v63;
              do
              {
                v31 = v29[1];
                *(_OWORD *)v30 = *v29;
                v32 = v29[2];
                *((_OWORD *)v30 + 1) = v31;
                v33 = v29[3];
                *((_OWORD *)v30 + 2) = v32;
                v34 = v29[4];
                *((_OWORD *)v30 + 3) = v33;
                v35 = v29[5];
                *((_OWORD *)v30 + 4) = v34;
                v36 = v29[6];
                *((_OWORD *)v30 + 5) = v35;
                v37 = v29[7];
                v29 += 8;
                *((_OWORD *)v30 + 6) = v36;
                *((_OWORD *)v30 + 7) = v37;
                v30 += 128;
                --v28;
              }
              while ( v28 );
              v38 = v29[1];
              *(_OWORD *)v30 = *v29;
              v39 = v29[2];
              *((_OWORD *)v30 + 1) = v38;
              v40 = v29[3];
              *((_OWORD *)v30 + 2) = v39;
              v41 = v29[4];
              *((_OWORD *)v30 + 3) = v40;
              v42 = v29[5];
              *((_OWORD *)v30 + 4) = v41;
              v43 = v29[6];
              v44 = *((_QWORD *)v29 + 14);
              *((_OWORD *)v30 + 5) = v42;
              *((_OWORD *)v30 + 6) = v43;
              *((_QWORD *)v30 + 14) = v44;
              v64 = 545;
              v73 |= 1u;
              if ( v65 )
              {
                v45 = FwStringBuild(&v61, v56, v65, 0);
                v46 = v65;
                if ( v45 >= 0 )
                  v46 = v61;
                v65 = v46;
              }
              else
              {
                v65 = v56;
              }
              if ( v66 )
              {
                v47 = FwStringBuild(&v62, a4, v66, 0);
                v48 = v66;
                if ( v47 >= 0 )
                  v48 = v62;
                v66 = v48;
              }
              else
              {
                v66 = a4;
              }
              v74 = lpsz;
              v71 = v27;
              v70 = v27 != 0;
              v67 = 0x7FFFFFFF;
              if ( a5 && (v77 & 0x40) == 0 )
              {
                if ( *a5 )
                {
                  if ( *a5 == 1 )
                  {
                    v75 = 1;
                    v49 = a5 + 2;
                  }
                  else
                  {
                    v75 = v60;
                    v49 = (_DWORD *)*((_QWORD *)&v60 + 1);
                  }
                  v76 = v49;
                }
                else
                {
                  v67 = a5[2];
                }
              }
              v50 = v72;
              if ( v72 == 2 )
              {
                if ( (a6 & 8) != 0 )
                  v77 |= v72 + 126;
                if ( (a6 & 0x10) != 0 )
                  v50 = 3;
                v72 = v50;
              }
              v12 = FwMoneisAddRule(v23, v63, 0);
              if ( v12 )
              {
                v25 = WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                {
                  v26 = 30;
                  goto LABEL_46;
                }
                goto LABEL_92;
              }
              if ( v61 )
              {
                FwFree(v61);
                v61 = 0;
              }
              if ( v62 )
              {
                FwFree(v62);
                v62 = 0;
              }
              ++v24;
            }
          }
          goto LABEL_92;
        }
        v25 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_92;
        v26 = 28;
      }
LABEL_46:
      WPP_SF_Ds(*(_QWORD *)(v25 + 16), v26, (unsigned int)"A", v12, (__int64)"FwMoneisAddRule");
      goto LABEL_92;
    }
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v14 = 23;
      v15 = "FwMoneisOpenIfIsoStore";
      goto LABEL_7;
    }
  }
LABEL_92:
  v51 = *((_QWORD *)&v60 + 1);
  if ( *((_QWORD *)&v60 + 1) )
  {
    for ( i = 0; i < (unsigned int)v60; ++i )
    {
      FwFree(*(_QWORD *)(v51 + 8LL * i));
      v51 = *((_QWORD *)&v60 + 1);
    }
    FwFree(v51);
  }
  SvrImpl_FWClosePolicyStore(0, &v55);
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return v12;
}

```

## disassembly

```asm
0x1800be78c  mov     [rsp-8+arg_0], rbx
0x1800be791  push    rbp
0x1800be792  push    rsi
0x1800be793  push    rdi
0x1800be794  push    r12
0x1800be796  push    r13
0x1800be798  push    r14
0x1800be79a  push    r15
0x1800be79c  lea     rbp, [rsp-190h]
0x1800be7a4  sub     rsp, 290h
0x1800be7ab  mov     rax, cs:__security_cookie
0x1800be7b2  xor     rax, rsp
0x1800be7b5  mov     [rbp+1C0h+var_40], rax
0x1800be7bc  mov     rax, [rbp+1C0h+arg_38]
0x1800be7c3  lea     rcx, [rbp+1C0h+var_240]; void *
0x1800be7c7  mov     rsi, [rbp+1C0h+lpString1]
0x1800be7ce  mov     r13, r8
0x1800be7d1  mov     rdi, [rbp+1C0h+arg_20]
0x1800be7d8  mov     r12, rdx
0x1800be7db  mov     [rsp+2C0h+var_280], r8
0x1800be7e0  xor     ebx, ebx
0x1800be7e2  mov     [rsp+2C0h+var_278], rdx
0x1800be7e7  mov     r8d, 1F8h; Size
0x1800be7ed  xor     edx, edx; Val
0x1800be7ef  mov     [rsp+2C0h+var_270], rax
0x1800be7f4  mov     [rsp+2C0h+lpsz], rbx
0x1800be7f9  mov     [rsp+2C0h+var_288], rbx
0x1800be7fe  mov     [rsp+2C0h+var_290], r9
0x1800be803  call    memset_0
0x1800be808  mov     [rsp+2C0h+var_250], rbx
0x1800be80d  xorps   xmm0, xmm0
0x1800be810  mov     [rsp+2C0h+var_248], rbx
0x1800be815  lea     r14d, [rbx+1]
0x1800be819  movups  [rsp+2C0h+var_260], xmm0
0x1800be81e  test    rdi, rdi
0x1800be821  jz      short loc_1800BE88C
0x1800be823  cmp     dword ptr [rdi], 2
0x1800be826  jnz     short loc_1800BE88C
0x1800be828  mov     rcx, [rdi+8]
0x1800be82c  lea     r8, [rsp+2C0h+var_260]
0x1800be831  lea     rdx, asc_1800F7CB0; ","
0x1800be838  call    FwMoneisEdpNamesStringToNetNames
0x1800be83d  mov     ebx, eax
0x1800be83f  test    eax, eax
0x1800be841  jz      short loc_1800BE88C
0x1800be843  mov     rax, cs:WPP_GLOBAL_Control
0x1800be84a  lea     rcx, WPP_GLOBAL_Control
0x1800be851  cmp     rax, rcx
0x1800be854  jz      loc_1800BEE37
0x1800be85a  test    [rax+1Ch], r14b
0x1800be85e  jz      loc_1800BEE37
0x1800be864  lea     edx, [r14+15h]
0x1800be868  lea     rcx, aFwmoneisedpnam; "FwMoneisEdpNamesStringToNetNames"
0x1800be86f  mov     [rsp+2C0h+var_2A0], rcx
0x1800be874  mov     rcx, [rax+10h]
0x1800be878  lea     r8, WPP_e0d30041b2973bba096172aea683b919_Traceguids; "A"
0x1800be87f  mov     r9d, ebx
0x1800be882  call    WPP_SF_Ds
0x1800be887  jmp     loc_1800BEE37
0x1800be88c  mov     r15d, [rbp+1C0h+arg_28]
0x1800be893  lea     rdx, [rsp+2C0h+var_288]; void **
0x1800be898  mov     ecx, r15d; unsigned int
0x1800be89b  call    ?FwMoneisOpenIfIsoStore@@YAKKPEAPEAX@Z; FwMoneisOpenIfIsoStore(ulong,void * *)
0x1800be8a0  xor     ecx, ecx
0x1800be8a2  mov     ebx, eax
0x1800be8a4  test    eax, eax
0x1800be8a6  jz      short loc_1800BE8D7
0x1800be8a8  mov     rax, cs:WPP_GLOBAL_Control
0x1800be8af  lea     rcx, WPP_GLOBAL_Control
0x1800be8b6  cmp     rax, rcx
0x1800be8b9  jz      loc_1800BEE37
0x1800be8bf  test    [rax+1Ch], r14b
0x1800be8c3  jz      loc_1800BEE37
0x1800be8c9  mov     edx, 17h
0x1800be8ce  lea     rcx, aFwmoneisopenif; "FwMoneisOpenIfIsoStore"
0x1800be8d5  jmp     short loc_1800BE86F
0x1800be8d7  test    r12, r12
0x1800be8da  jz      short loc_1800BE92E
0x1800be8dc  lea     rdx, [rsp+2C0h+lpsz]; lplpsz
0x1800be8e1  mov     rcx, r12; rclsid
0x1800be8e4  call    cs:__imp_StringFromCLSID
0x1800be8ea  mov     ecx, eax
0x1800be8ec  call    cs:__imp_FwHResultToWindowsError
0x1800be8f2  mov     ebx, eax
0x1800be8f4  test    eax, eax
0x1800be8f6  jz      loc_1800BEA0A
0x1800be8fc  mov     rax, cs:WPP_GLOBAL_Control
0x1800be903  lea     rcx, WPP_GLOBAL_Control
0x1800be90a  cmp     rax, rcx
0x1800be90d  jz      loc_1800BEE37
0x1800be913  test    [rax+1Ch], r14b
0x1800be917  jz      loc_1800BEE37
0x1800be91d  mov     edx, 18h
0x1800be922  lea     rcx, aStringfromclsi_0; "StringFromCLSID"
0x1800be929  jmp     loc_1800BE86F
0x1800be92e  test    rsi, rsi
0x1800be931  lea     rax, aAllinterfacesc; "AllInterfacesContainerGroupIdzzz"
0x1800be938  cmovnz  rax, rsi
0x1800be93c  mov     rsi, rax
0x1800be93f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800be943  inc     rax
0x1800be946  cmp     [rsi+rax*2], cx
0x1800be94a  jnz     short loc_1800BE943
0x1800be94c  lea     r14, [rax+1]
0x1800be950  lea     rcx, [r14+r14]; cb
0x1800be954  call    cs:__imp_CoTaskMemAlloc
0x1800be95a  mov     [rsp+2C0h+lpsz], rax
0x1800be95f  test    rax, rax
0x1800be962  jnz     short loc_1800BE9B1
0x1800be964  mov     ecx, 8007000Eh
0x1800be969  call    cs:__imp_FwHResultToWindowsError
0x1800be96f  mov     ebx, eax
0x1800be971  test    eax, eax
0x1800be973  jz      short loc_1800BE9AC
0x1800be975  mov     rax, cs:WPP_GLOBAL_Control
0x1800be97c  lea     rcx, WPP_GLOBAL_Control
0x1800be983  mov     r14d, 1
0x1800be989  cmp     rax, rcx
0x1800be98c  jz      loc_1800BEE37
0x1800be992  test    [rax+1Ch], r14b
0x1800be996  jz      loc_1800BEE37
0x1800be99c  lea     edx, [r14+18h]
0x1800be9a0  lea     rcx, aCotaskmemalloc_0; "CoTaskMemAlloc"
0x1800be9a7  jmp     loc_1800BE86F
0x1800be9ac  mov     rax, [rsp+2C0h+lpsz]
0x1800be9b1  mov     r8, rsi; unsigned __int16 *
0x1800be9b4  mov     rdx, r14; unsigned __int64
0x1800be9b7  mov     rcx, rax; unsigned __int16 *
0x1800be9ba  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800be9bf  mov     ecx, eax
0x1800be9c1  call    cs:__imp_FwHResultToWindowsError
0x1800be9c7  mov     ebx, eax
0x1800be9c9  test    eax, eax
0x1800be9cb  jz      short loc_1800BEA04
0x1800be9cd  mov     rax, cs:WPP_GLOBAL_Control
0x1800be9d4  lea     rcx, WPP_GLOBAL_Control
0x1800be9db  mov     r14d, 1
0x1800be9e1  cmp     rax, rcx
0x1800be9e4  jz      loc_1800BEE37
0x1800be9ea  test    [rax+1Ch], r14b
0x1800be9ee  jz      loc_1800BEE37
0x1800be9f4  lea     edx, [r14+19h]
0x1800be9f8  lea     rcx, aStringcchcopy; "StringCchCopy"
0x1800be9ff  jmp     loc_1800BE86F
0x1800bea04  mov     r14d, 1
0x1800bea0a  xor     edx, edx; Val
0x1800bea0c  lea     rcx, [rbp+1C0h+var_240]; void *
0x1800bea10  mov     r8d, 1F8h; Size
0x1800bea16  call    memset_0
0x1800bea1b  xor     ebx, ebx
0x1800bea1d  mov     [rbp+1C0h+var_11C], r14w
0x1800bea25  mov     eax, 221h
0x1800bea2a  mov     [rbp+1C0h+var_228], r13
0x1800bea2e  mov     [rbp+1C0h+var_238], ax
0x1800bea32  test    r12, r12
0x1800bea35  mov     rax, [rsp+2C0h+var_290]
0x1800bea3a  mov     [rbp+1C0h+var_220], rax
0x1800bea3e  mov     rax, [rsp+2C0h+lpsz]
0x1800bea43  mov     [rbp+1C0h+var_108], rax
0x1800bea4a  mov     eax, 100h
0x1800bea4f  mov     [rbp+1C0h+var_210], ax
0x1800bea53  mov     eax, ebx
0x1800bea55  setnz   al
0x1800bea58  mov     [rbp+1C0h+var_140], r12
0x1800bea5f  mov     [rbp+1C0h+var_148], eax
0x1800bea62  mov     [rbp+1C0h+var_218], 7FFFFFFFh
0x1800bea69  test    rdi, rdi
0x1800bea6c  jz      short loc_1800BEAA2
0x1800bea6e  cmp     [rdi], ebx
0x1800bea70  jnz     short loc_1800BEA7A
0x1800bea72  mov     eax, [rdi+8]
0x1800bea75  mov     [rbp+1C0h+var_218], eax
0x1800bea78  jmp     short loc_1800BEAA2
0x1800bea7a  cmp     [rdi], r14d
0x1800bea7d  jnz     short loc_1800BEA8C
0x1800bea7f  mov     [rbp+1C0h+var_B0], r14d
0x1800bea86  lea     rax, [rdi+8]
0x1800bea8a  jmp     short loc_1800BEA9B
0x1800bea8c  mov     eax, dword ptr [rsp+2C0h+var_260]
0x1800bea90  mov     [rbp+1C0h+var_B0], eax
0x1800bea96  mov     rax, qword ptr [rsp+2C0h+var_260+8]
0x1800bea9b  mov     [rbp+1C0h+var_A8], rax
0x1800beaa2  mov     r12d, r15d
0x1800beaa5  mov     eax, 80h
0x1800beaaa  and     r12d, 8
0x1800beaae  jz      short loc_1800BEAB7
0x1800beab0  or      [rbp+1C0h+var_98], ax
0x1800beab7  mov     r13d, r15d
0x1800beaba  mov     rcx, rsi; lpString1
0x1800beabd  and     r13d, 10h
0x1800beac1  mov     eax, r13d
0x1800beac4  neg     eax
0x1800beac6  sbb     edx, edx
0x1800beac8  neg     edx
0x1800beaca  add     edx, 2
0x1800beacd  mov     [rbp+1C0h+var_120], edx
0x1800bead3  lea     rdx, aEdpallinterfac; "EDPAllInterfacesContainerGroupIdzzz"
0x1800beada  call    cs:__imp_lstrcmpiW
0x1800beae0  test    eax, eax
0x1800beae2  jnz     short loc_1800BEAF0
0x1800beae4  mov     eax, 400h
0x1800beae9  or      [rbp+1C0h+var_98], ax
0x1800beaf0  mov     [rbp+1C0h+var_214], r14d
0x1800beaf4  lea     rdx, [rbp+1C0h+var_240]
0x1800beaf8  mov     r14, [rsp+2C0h+var_288]
0x1800beafd  xor     r8d, r8d
0x1800beb00  mov     rcx, r14
0x1800beb03  call    ?FwMoneisAddRule@@YAKPEAXPEAU_tag_FW_RULE@@W4customRuleId@@@Z; FwMoneisAddRule(void *,_tag_FW_RULE *,customRuleId)
0x1800beb08  xor     esi, esi
0x1800beb0a  mov     ebx, eax
0x1800beb0c  test    eax, eax
0x1800beb0e  jz      short loc_1800BEB4D
0x1800beb10  mov     r10, cs:WPP_GLOBAL_Control
0x1800beb17  lea     rcx, WPP_GLOBAL_Control
0x1800beb1e  lea     r14d, [rsi+1]
0x1800beb22  cmp     r10, rcx
0x1800beb25  jz      loc_1800BEE37
0x1800beb2b  test    [r10+1Ch], r14b
0x1800beb2f  jz      loc_1800BEE37
0x1800beb35  lea     edx, [rsi+1Bh]
0x1800beb38  mov     rcx, [r10+10h]
0x1800beb3c  lea     rax, aFwmoneisaddrul; "FwMoneisAddRule"
0x1800beb43  mov     [rsp+2C0h+var_2A0], rax
0x1800beb48  jmp     loc_1800BE878
0x1800beb4d  xor     r8d, r8d
0x1800beb50  mov     [rbp+1C0h+var_214], 2
0x1800beb57  lea     rdx, [rbp+1C0h+var_240]
0x1800beb5b  mov     rcx, r14
0x1800beb5e  call    ?FwMoneisAddRule@@YAKPEAXPEAU_tag_FW_RULE@@W4customRuleId@@@Z; FwMoneisAddRule(void *,_tag_FW_RULE *,customRuleId)
0x1800beb63  mov     ebx, eax
0x1800beb65  test    eax, eax
0x1800beb67  jz      short loc_1800BEB96
0x1800beb69  mov     r10, cs:WPP_GLOBAL_Control
0x1800beb70  lea     rcx, WPP_GLOBAL_Control
0x1800beb77  mov     r14d, 1
0x1800beb7d  cmp     r10, rcx
0x1800beb80  jz      loc_1800BEE37
0x1800beb86  test    [r10+1Ch], r14b
0x1800beb8a  jz      loc_1800BEE37
0x1800beb90  lea     edx, [r14+1Bh]
0x1800beb94  jmp     short loc_1800BEB38
0x1800beb96  mov     eax, 0FF7Fh
0x1800beb9b  lea     r8, [rbp+1C0h+var_240]; struct _tag_FW_RULE *
0x1800beb9f  and     [rbp+1C0h+var_98], ax
0x1800beba6  mov     edx, r15d; unsigned int
0x1800beba9  mov     rcx, r14; void *
0x1800bebac  call    ?FwMoneisAddCoreNetworkingToInterfaceContainer@@YAKPEAXKPEAU_tag_FW_RULE@@@Z; FwMoneisAddCoreNetworkingToInterfaceContainer(void *,ulong,_tag_FW_RULE *)
0x1800bebb1  mov     ebx, eax
0x1800bebb3  test    eax, eax
0x1800bebb5  jz      short loc_1800BEBEE
0x1800bebb7  mov     rax, cs:WPP_GLOBAL_Control
0x1800bebbe  lea     rcx, WPP_GLOBAL_Control
0x1800bebc5  mov     r14d, 1
0x1800bebcb  cmp     rax, rcx
0x1800bebce  jz      loc_1800BEE37
0x1800bebd4  test    [rax+1Ch], r14b
0x1800bebd8  jz      loc_1800BEE37
0x1800bebde  lea     edx, [r14+1Ch]
0x1800bebe2  lea     rcx, aFwmoneisaddcor; "FwMoneisAddCoreNetworkingToInterfaceCon"...
0x1800bebe9  jmp     loc_1800BE86F
0x1800bebee  mov     r15, [rsp+2C0h+var_278]
0x1800bebf3  mov     edx, 3
0x1800bebf8  cmp     esi, [rbp+1C0h+arg_30]
0x1800bebfe  jnb     loc_1800BEE31
0x1800bec04  mov     eax, esi
0x1800bec06  lea     r8d, [rdx+7Dh]
0x1800bec0a  imul    rcx, rax, 1F8h
0x1800bec11  mov     rax, [rsp+2C0h+var_270]
0x1800bec16  add     rax, rcx
0x1800bec19  lea     rcx, [rbp+1C0h+var_240]
0x1800bec1d  movups  xmm0, xmmword ptr [rax]
0x1800bec20  movups  xmm1, xmmword ptr [rax+10h]
0x1800bec24  movups  xmmword ptr [rcx], xmm0
0x1800bec27  movups  xmm0, xmmword ptr [rax+20h]
0x1800bec2b  movups  xmmword ptr [rcx+10h], xmm1
0x1800bec2f  movups  xmm1, xmmword ptr [rax+30h]
0x1800bec33  movups  xmmword ptr [rcx+20h], xmm0
0x1800bec37  movups  xmm0, xmmword ptr [rax+40h]
0x1800bec3b  movups  xmmword ptr [rcx+30h], xmm1
0x1800bec3f  movups  xmm1, xmmword ptr [rax+50h]
0x1800bec43  movups  xmmword ptr [rcx+40h], xmm0
0x1800bec47  movups  xmm0, xmmword ptr [rax+60h]
0x1800bec4b  movups  xmmword ptr [rcx+50h], xmm1
0x1800bec4f  movups  xmm1, xmmword ptr [rax+70h]
0x1800bec53  add     rax, r8
0x1800bec56  movups  xmmword ptr [rcx+60h], xmm0
0x1800bec5a  movups  xmmword ptr [rcx+70h], xmm1
0x1800bec5e  add     rcx, r8
0x1800bec61  sub     rdx, 1
0x1800bec65  jnz     short loc_1800BEC1D
0x1800bec67  movups  xmm0, xmmword ptr [rax]
0x1800bec6a  xor     ebx, ebx
0x1800bec6c  movups  xmm1, xmmword ptr [rax+10h]
0x1800bec70  movups  xmmword ptr [rcx], xmm0
0x1800bec73  movups  xmm0, xmmword ptr [rax+20h]
0x1800bec77  movups  xmmword ptr [rcx+10h], xmm1
0x1800bec7b  movups  xmm1, xmmword ptr [rax+30h]
0x1800bec7f  movups  xmmword ptr [rcx+20h], xmm0
0x1800bec83  movups  xmm0, xmmword ptr [rax+40h]
0x1800bec87  movups  xmmword ptr [rcx+30h], xmm1
  ... truncated ...
```
