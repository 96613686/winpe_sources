# FwMoneisCreateInterfaceContainer

- ea: `0x1800c53e4`
- end: `0x1800c5b60`
- name: `FwMoneisCreateInterfaceContainer`
- size: `1916`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c3ea0`
- `0x1800cddf0`

## callees

- `0x18000a66c`
- `0x18002b660`
- `0x18003d708`
- `0x18003d990`
- `0x180054d10`
- `0x18006d210`
- `0x1800729c0`
- `0x180073488`
- `0x1800c4cbc`
- `0x1800c53e4`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800c5750`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800c5750`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800c553c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800c553c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5b27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5b27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c55b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c55b8`
- `fwbase!FwHResultToWindowsError` at `0x1800c554a`
- `fwbase!FwHResultToWindowsError` at `0x1800c55d3`
- `fwbase!FwHResultToWindowsError` at `0x1800c5631`
- `fwbase!FwHResultToWindowsError` at `0x1800c554a`
- `fwbase!FwHResultToWindowsError` at `0x1800c55d3`
- `fwbase!FwHResultToWindowsError` at `0x1800c5631`
- `fwbase!FwStringBuild` at `0x1800c5957`
- `fwbase!FwStringBuild` at `0x1800c5994`
- `fwbase!FwStringBuild` at `0x1800c5957`
- `fwbase!FwStringBuild` at `0x1800c5994`
- `fwbase!FwFree` at `0x1800c5a64`
- `fwbase!FwFree` at `0x1800c5a81`
- `fwbase!FwFree` at `0x1800c5ae8`
- `fwbase!FwFree` at `0x1800c5b05`
- `fwbase!FwFree` at `0x1800c5a64`
- `fwbase!FwFree` at `0x1800c5a81`
- `fwbase!FwFree` at `0x1800c5ae8`
- `fwbase!FwFree` at `0x1800c5b05`

## string_xrefs

- `0x1800c5526`: `FwMoneisOpenIfIsoStore`
- `0x1800c566e`: `StringCchCopy`
- `0x1800c5610`: `CoTaskMemAlloc`
- `0x1800c5586`: `StringFromCLSID`

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
      WPP_SF_Ds(
        *(_QWORD *)(v13 + 16),
        v14,
        (unsigned int)WPP_c1b1b84f9be43d56c172dc8519c16790_Traceguids,
        v12,
        (__int64)v15);
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
      WPP_SF_Ds(
        *(_QWORD *)(v25 + 16),
        v26,
        (unsigned int)WPP_c1b1b84f9be43d56c172dc8519c16790_Traceguids,
        v12,
        (__int64)"FwMoneisAddRule");
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
0x1800c53e4  mov     [rsp-8+arg_0], rbx
0x1800c53e9  push    rbp
0x1800c53ea  push    rsi
0x1800c53eb  push    rdi
0x1800c53ec  push    r12
0x1800c53ee  push    r13
0x1800c53f0  push    r14
0x1800c53f2  push    r15
0x1800c53f4  lea     rbp, [rsp-190h]
0x1800c53fc  sub     rsp, 290h
0x1800c5403  mov     rax, cs:__security_cookie
0x1800c540a  xor     rax, rsp
0x1800c540d  mov     [rbp+1C0h+var_40], rax
0x1800c5414  mov     rax, [rbp+1C0h+arg_38]
0x1800c541b  lea     rcx, [rbp+1C0h+var_240]; void *
0x1800c541f  mov     rsi, [rbp+1C0h+lpString1]
0x1800c5426  mov     r13, r8
0x1800c5429  mov     rdi, [rbp+1C0h+arg_20]
0x1800c5430  mov     r12, rdx
0x1800c5433  mov     [rsp+2C0h+var_280], r8
0x1800c5438  xor     ebx, ebx
0x1800c543a  mov     [rsp+2C0h+var_278], rdx
0x1800c543f  mov     r8d, 1F8h; Size
0x1800c5445  xor     edx, edx; Val
0x1800c5447  mov     [rsp+2C0h+var_270], rax
0x1800c544c  mov     [rsp+2C0h+lpsz], rbx
0x1800c5451  mov     [rsp+2C0h+var_288], rbx
0x1800c5456  mov     [rsp+2C0h+var_290], r9
0x1800c545b  call    memset_0
0x1800c5460  mov     [rsp+2C0h+var_250], rbx
0x1800c5465  xorps   xmm0, xmm0
0x1800c5468  mov     [rsp+2C0h+var_248], rbx
0x1800c546d  lea     r14d, [rbx+1]
0x1800c5471  movups  [rsp+2C0h+var_260], xmm0
0x1800c5476  test    rdi, rdi
0x1800c5479  jz      short loc_1800C54E4
0x1800c547b  cmp     dword ptr [rdi], 2
0x1800c547e  jnz     short loc_1800C54E4
0x1800c5480  mov     rcx, [rdi+8]
0x1800c5484  lea     r8, [rsp+2C0h+var_260]
0x1800c5489  lea     rdx, asc_1800FDD80; ","
0x1800c5490  call    FwMoneisEdpNamesStringToNetNames
0x1800c5495  mov     ebx, eax
0x1800c5497  test    eax, eax
0x1800c5499  jz      short loc_1800C54E4
0x1800c549b  mov     rax, cs:WPP_GLOBAL_Control
0x1800c54a2  lea     rcx, WPP_GLOBAL_Control
0x1800c54a9  cmp     rax, rcx
0x1800c54ac  jz      loc_1800C5ACB
0x1800c54b2  test    [rax+1Ch], r14b
0x1800c54b6  jz      loc_1800C5ACB
0x1800c54bc  lea     edx, [r14+15h]
0x1800c54c0  lea     rcx, aFwmoneisedpnam; "FwMoneisEdpNamesStringToNetNames"
0x1800c54c7  mov     [rsp+2C0h+var_2A0], rcx
0x1800c54cc  mov     rcx, [rax+10h]
0x1800c54d0  lea     r8, WPP_c1b1b84f9be43d56c172dc8519c16790_Traceguids
0x1800c54d7  mov     r9d, ebx
0x1800c54da  call    WPP_SF_Ds
0x1800c54df  jmp     loc_1800C5ACB
0x1800c54e4  mov     r15d, [rbp+1C0h+arg_28]
0x1800c54eb  lea     rdx, [rsp+2C0h+var_288]; void **
0x1800c54f0  mov     ecx, r15d; unsigned int
0x1800c54f3  call    ?FwMoneisOpenIfIsoStore@@YAKKPEAPEAX@Z; FwMoneisOpenIfIsoStore(ulong,void * *)
0x1800c54f8  xor     ecx, ecx
0x1800c54fa  mov     ebx, eax
0x1800c54fc  test    eax, eax
0x1800c54fe  jz      short loc_1800C552F
0x1800c5500  mov     rax, cs:WPP_GLOBAL_Control
0x1800c5507  lea     rcx, WPP_GLOBAL_Control
0x1800c550e  cmp     rax, rcx
0x1800c5511  jz      loc_1800C5ACB
0x1800c5517  test    [rax+1Ch], r14b
0x1800c551b  jz      loc_1800C5ACB
0x1800c5521  mov     edx, 17h
0x1800c5526  lea     rcx, aFwmoneisopenif; "FwMoneisOpenIfIsoStore"
0x1800c552d  jmp     short loc_1800C54C7
0x1800c552f  test    r12, r12
0x1800c5532  jz      short loc_1800C5592
0x1800c5534  lea     rdx, [rsp+2C0h+lpsz]; lplpsz
0x1800c5539  mov     rcx, r12; rclsid
0x1800c553c  call    cs:__imp_StringFromCLSID
0x1800c5543  nop     dword ptr [rax+rax+00h]
0x1800c5548  mov     ecx, eax
0x1800c554a  call    cs:__imp_FwHResultToWindowsError
0x1800c5551  nop     dword ptr [rax+rax+00h]
0x1800c5556  mov     ebx, eax
0x1800c5558  test    eax, eax
0x1800c555a  jz      loc_1800C5680
0x1800c5560  mov     rax, cs:WPP_GLOBAL_Control
0x1800c5567  lea     rcx, WPP_GLOBAL_Control
0x1800c556e  cmp     rax, rcx
0x1800c5571  jz      loc_1800C5ACB
0x1800c5577  test    [rax+1Ch], r14b
0x1800c557b  jz      loc_1800C5ACB
0x1800c5581  mov     edx, 18h
0x1800c5586  lea     rcx, aStringfromclsi_0; "StringFromCLSID"
0x1800c558d  jmp     loc_1800C54C7
0x1800c5592  test    rsi, rsi
0x1800c5595  lea     rax, aAllinterfacesc; "AllInterfacesContainerGroupIdzzz"
0x1800c559c  cmovnz  rax, rsi
0x1800c55a0  mov     rsi, rax
0x1800c55a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c55a7  inc     rax
0x1800c55aa  cmp     [rsi+rax*2], cx
0x1800c55ae  jnz     short loc_1800C55A7
0x1800c55b0  lea     r14, [rax+1]
0x1800c55b4  lea     rcx, [r14+r14]; cb
0x1800c55b8  call    cs:__imp_CoTaskMemAlloc
0x1800c55bf  nop     dword ptr [rax+rax+00h]
0x1800c55c4  mov     [rsp+2C0h+lpsz], rax
0x1800c55c9  test    rax, rax
0x1800c55cc  jnz     short loc_1800C5621
0x1800c55ce  mov     ecx, 8007000Eh
0x1800c55d3  call    cs:__imp_FwHResultToWindowsError
0x1800c55da  nop     dword ptr [rax+rax+00h]
0x1800c55df  mov     ebx, eax
0x1800c55e1  test    eax, eax
0x1800c55e3  jz      short loc_1800C561C
0x1800c55e5  mov     rax, cs:WPP_GLOBAL_Control
0x1800c55ec  lea     rcx, WPP_GLOBAL_Control
0x1800c55f3  mov     r14d, 1
0x1800c55f9  cmp     rax, rcx
0x1800c55fc  jz      loc_1800C5ACB
0x1800c5602  test    [rax+1Ch], r14b
0x1800c5606  jz      loc_1800C5ACB
0x1800c560c  lea     edx, [r14+18h]
0x1800c5610  lea     rcx, aCotaskmemalloc_0; "CoTaskMemAlloc"
0x1800c5617  jmp     loc_1800C54C7
0x1800c561c  mov     rax, [rsp+2C0h+lpsz]
0x1800c5621  mov     r8, rsi; unsigned __int16 *
0x1800c5624  mov     rdx, r14; unsigned __int64
0x1800c5627  mov     rcx, rax; unsigned __int16 *
0x1800c562a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c562f  mov     ecx, eax
0x1800c5631  call    cs:__imp_FwHResultToWindowsError
0x1800c5638  nop     dword ptr [rax+rax+00h]
0x1800c563d  mov     ebx, eax
0x1800c563f  test    eax, eax
0x1800c5641  jz      short loc_1800C567A
0x1800c5643  mov     rax, cs:WPP_GLOBAL_Control
0x1800c564a  lea     rcx, WPP_GLOBAL_Control
0x1800c5651  mov     r14d, 1
0x1800c5657  cmp     rax, rcx
0x1800c565a  jz      loc_1800C5ACB
0x1800c5660  test    [rax+1Ch], r14b
0x1800c5664  jz      loc_1800C5ACB
0x1800c566a  lea     edx, [r14+19h]
0x1800c566e  lea     rcx, aStringcchcopy; "StringCchCopy"
0x1800c5675  jmp     loc_1800C54C7
0x1800c567a  mov     r14d, 1
0x1800c5680  xor     edx, edx; Val
0x1800c5682  lea     rcx, [rbp+1C0h+var_240]; void *
0x1800c5686  mov     r8d, 1F8h; Size
0x1800c568c  call    memset_0
0x1800c5691  xor     ebx, ebx
0x1800c5693  mov     [rbp+1C0h+var_11C], r14w
0x1800c569b  mov     eax, 221h
0x1800c56a0  mov     [rbp+1C0h+var_228], r13
0x1800c56a4  mov     [rbp+1C0h+var_238], ax
0x1800c56a8  test    r12, r12
0x1800c56ab  mov     rax, [rsp+2C0h+var_290]
0x1800c56b0  mov     [rbp+1C0h+var_220], rax
0x1800c56b4  mov     rax, [rsp+2C0h+lpsz]
0x1800c56b9  mov     [rbp+1C0h+var_108], rax
0x1800c56c0  mov     eax, 100h
0x1800c56c5  mov     [rbp+1C0h+var_210], ax
0x1800c56c9  mov     eax, ebx
0x1800c56cb  setnz   al
0x1800c56ce  mov     [rbp+1C0h+var_140], r12
0x1800c56d5  mov     [rbp+1C0h+var_148], eax
0x1800c56d8  mov     [rbp+1C0h+var_218], 7FFFFFFFh
0x1800c56df  test    rdi, rdi
0x1800c56e2  jz      short loc_1800C5718
0x1800c56e4  cmp     [rdi], ebx
0x1800c56e6  jnz     short loc_1800C56F0
0x1800c56e8  mov     eax, [rdi+8]
0x1800c56eb  mov     [rbp+1C0h+var_218], eax
0x1800c56ee  jmp     short loc_1800C5718
0x1800c56f0  cmp     [rdi], r14d
0x1800c56f3  jnz     short loc_1800C5702
0x1800c56f5  mov     [rbp+1C0h+var_B0], r14d
0x1800c56fc  lea     rax, [rdi+8]
0x1800c5700  jmp     short loc_1800C5711
0x1800c5702  mov     eax, dword ptr [rsp+2C0h+var_260]
0x1800c5706  mov     [rbp+1C0h+var_B0], eax
0x1800c570c  mov     rax, qword ptr [rsp+2C0h+var_260+8]
0x1800c5711  mov     [rbp+1C0h+var_A8], rax
0x1800c5718  mov     r12d, r15d
0x1800c571b  mov     eax, 80h
0x1800c5720  and     r12d, 8
0x1800c5724  jz      short loc_1800C572D
0x1800c5726  or      [rbp+1C0h+var_98], ax
0x1800c572d  mov     r13d, r15d
0x1800c5730  mov     rcx, rsi; lpString1
0x1800c5733  and     r13d, 10h
0x1800c5737  mov     eax, r13d
0x1800c573a  neg     eax
0x1800c573c  sbb     edx, edx
0x1800c573e  neg     edx
0x1800c5740  add     edx, 2
0x1800c5743  mov     [rbp+1C0h+var_120], edx
0x1800c5749  lea     rdx, aEdpallinterfac; "EDPAllInterfacesContainerGroupIdzzz"
0x1800c5750  call    cs:__imp_lstrcmpiW
0x1800c5757  nop     dword ptr [rax+rax+00h]
0x1800c575c  test    eax, eax
0x1800c575e  jnz     short loc_1800C576C
0x1800c5760  mov     eax, 400h
0x1800c5765  or      [rbp+1C0h+var_98], ax
0x1800c576c  mov     [rbp+1C0h+var_214], r14d
0x1800c5770  lea     rdx, [rbp+1C0h+var_240]
0x1800c5774  mov     r14, [rsp+2C0h+var_288]
0x1800c5779  xor     r8d, r8d
0x1800c577c  mov     rcx, r14
0x1800c577f  call    ?FwMoneisAddRule@@YAKPEAXPEAU_tag_FW_RULE@@W4customRuleId@@@Z; FwMoneisAddRule(void *,_tag_FW_RULE *,customRuleId)
0x1800c5784  xor     esi, esi
0x1800c5786  mov     ebx, eax
0x1800c5788  test    eax, eax
0x1800c578a  jz      short loc_1800C57C9
0x1800c578c  mov     r10, cs:WPP_GLOBAL_Control
0x1800c5793  lea     rcx, WPP_GLOBAL_Control
0x1800c579a  lea     r14d, [rsi+1]
0x1800c579e  cmp     r10, rcx
0x1800c57a1  jz      loc_1800C5ACB
0x1800c57a7  test    [r10+1Ch], r14b
0x1800c57ab  jz      loc_1800C5ACB
0x1800c57b1  lea     edx, [rsi+1Bh]
0x1800c57b4  mov     rcx, [r10+10h]
0x1800c57b8  lea     rax, aFwmoneisaddrul; "FwMoneisAddRule"
0x1800c57bf  mov     [rsp+2C0h+var_2A0], rax
0x1800c57c4  jmp     loc_1800C54D0
0x1800c57c9  xor     r8d, r8d
0x1800c57cc  mov     [rbp+1C0h+var_214], 2
0x1800c57d3  lea     rdx, [rbp+1C0h+var_240]
0x1800c57d7  mov     rcx, r14
0x1800c57da  call    ?FwMoneisAddRule@@YAKPEAXPEAU_tag_FW_RULE@@W4customRuleId@@@Z; FwMoneisAddRule(void *,_tag_FW_RULE *,customRuleId)
0x1800c57df  mov     ebx, eax
0x1800c57e1  test    eax, eax
0x1800c57e3  jz      short loc_1800C5812
0x1800c57e5  mov     r10, cs:WPP_GLOBAL_Control
0x1800c57ec  lea     rcx, WPP_GLOBAL_Control
0x1800c57f3  mov     r14d, 1
0x1800c57f9  cmp     r10, rcx
0x1800c57fc  jz      loc_1800C5ACB
0x1800c5802  test    [r10+1Ch], r14b
0x1800c5806  jz      loc_1800C5ACB
0x1800c580c  lea     edx, [r14+1Bh]
0x1800c5810  jmp     short loc_1800C57B4
0x1800c5812  mov     eax, 0FF7Fh
0x1800c5817  lea     r8, [rbp+1C0h+var_240]; struct _tag_FW_RULE *
0x1800c581b  and     [rbp+1C0h+var_98], ax
0x1800c5822  mov     edx, r15d; unsigned int
0x1800c5825  mov     rcx, r14; void *
0x1800c5828  call    ?FwMoneisAddCoreNetworkingToInterfaceContainer@@YAKPEAXKPEAU_tag_FW_RULE@@@Z; FwMoneisAddCoreNetworkingToInterfaceContainer(void *,ulong,_tag_FW_RULE *)
0x1800c582d  mov     ebx, eax
0x1800c582f  test    eax, eax
0x1800c5831  jz      short loc_1800C586A
0x1800c5833  mov     rax, cs:WPP_GLOBAL_Control
0x1800c583a  lea     rcx, WPP_GLOBAL_Control
0x1800c5841  mov     r14d, 1
0x1800c5847  cmp     rax, rcx
0x1800c584a  jz      loc_1800C5ACB
0x1800c5850  test    [rax+1Ch], r14b
0x1800c5854  jz      loc_1800C5ACB
0x1800c585a  lea     edx, [r14+1Ch]
0x1800c585e  lea     rcx, aFwmoneisaddcor; "FwMoneisAddCoreNetworkingToInterfaceCon"...
0x1800c5865  jmp     loc_1800C54C7
0x1800c586a  mov     r15, [rsp+2C0h+var_278]
0x1800c586f  mov     edx, 3
0x1800c5874  cmp     esi, [rbp+1C0h+arg_30]
0x1800c587a  jnb     loc_1800C5AC5
0x1800c5880  mov     eax, esi
0x1800c5882  lea     r8d, [rdx+7Dh]
0x1800c5886  imul    rcx, rax, 1F8h
0x1800c588d  mov     rax, [rsp+2C0h+var_270]
0x1800c5892  add     rax, rcx
0x1800c5895  lea     rcx, [rbp+1C0h+var_240]
0x1800c5899  movups  xmm0, xmmword ptr [rax]
0x1800c589c  movups  xmm1, xmmword ptr [rax+10h]
0x1800c58a0  movups  xmmword ptr [rcx], xmm0
0x1800c58a3  movups  xmm0, xmmword ptr [rax+20h]
0x1800c58a7  movups  xmmword ptr [rcx+10h], xmm1
0x1800c58ab  movups  xmm1, xmmword ptr [rax+30h]
0x1800c58af  movups  xmmword ptr [rcx+20h], xmm0
0x1800c58b3  movups  xmm0, xmmword ptr [rax+40h]
0x1800c58b7  movups  xmmword ptr [rcx+30h], xmm1
0x1800c58bb  movups  xmm1, xmmword ptr [rax+50h]
0x1800c58bf  movups  xmmword ptr [rcx+40h], xmm0
0x1800c58c3  movups  xmm0, xmmword ptr [rax+60h]
0x1800c58c7  movups  xmmword ptr [rcx+50h], xmm1
0x1800c58cb  movups  xmm1, xmmword ptr [rax+70h]
0x1800c58cf  add     rax, r8
0x1800c58d2  movups  xmmword ptr [rcx+60h], xmm0
0x1800c58d6  movups  xmmword ptr [rcx+70h], xmm1
0x1800c58da  add     rcx, r8
0x1800c58dd  sub     rdx, 1
0x1800c58e1  jnz     short loc_1800C5899
0x1800c58e3  movups  xmm0, xmmword ptr [rax]
0x1800c58e6  xor     ebx, ebx
0x1800c58e8  movups  xmm1, xmmword ptr [rax+10h]
0x1800c58ec  movups  xmmword ptr [rcx], xmm0
  ... truncated ...
```
