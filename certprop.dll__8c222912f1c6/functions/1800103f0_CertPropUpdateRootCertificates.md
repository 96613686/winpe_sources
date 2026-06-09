# CertPropUpdateRootCertificates

- ea: `0x1800103f0`
- end: `0x180010b4c`
- name: `CertPropUpdateRootCertificates`
- size: `1884`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18000f240`
- `0x1800185d8`

## callees

- `0x180004600`
- `0x1800103f0`
- `0x180014a30`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`
- `0x180021674`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010a8f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001055c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001055c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105e0`
- `CRYPT32!CertCloseStore` at `0x1800105f2`
- `CRYPT32!CertCloseStore` at `0x1800105f2`
- `CRYPT32!CertAddStoreToCollection` at `0x1800105d6`
- `CRYPT32!CertAddStoreToCollection` at `0x1800105d6`
- `CRYPT32!CertOpenStore` at `0x18001054e`
- `CRYPT32!CertOpenStore` at `0x1800105b4`
- `CRYPT32!CertOpenStore` at `0x18001054e`
- `CRYPT32!CertOpenStore` at `0x1800105b4`

## pseudocode

```c
__int64 __fastcall CertPropUpdateRootCertificates(__int64 a1)
{
  DWORD LastError; // esi
  STRSAFE_LPSTR v3; // rcx
  __int64 i; // rdi
  STRSAFE_LPSTR v5; // rcx
  bool v6; // zf
  HCERTSTORE v7; // rax
  __int64 v8; // rdx
  void *v9; // rbx
  HCERTSTORE v10; // rax
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  int v14; // eax
  __int64 *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  __int64 *v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  __int64 *v21; // rcx
  __int64 v22; // rax
  int v23; // eax
  __int64 *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  __int64 *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  __int64 *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v36; // [rsp+48h] [rbp-C0h] BYREF
  int v37; // [rsp+4Ch] [rbp-BCh] BYREF
  int v38; // [rsp+50h] [rbp-B8h] BYREF
  int v39; // [rsp+54h] [rbp-B4h] BYREF
  int v40; // [rsp+58h] [rbp-B0h] BYREF
  int v41; // [rsp+5Ch] [rbp-ACh] BYREF
  int v42; // [rsp+60h] [rbp-A8h] BYREF
  int v43; // [rsp+64h] [rbp-A4h] BYREF
  int v44; // [rsp+68h] [rbp-A0h] BYREF
  int v45; // [rsp+6Ch] [rbp-9Ch] BYREF
  int v46; // [rsp+70h] [rbp-98h] BYREF
  _DWORD v47[3]; // [rsp+74h] [rbp-94h] BYREF
  __int128 pvPara; // [rsp+80h] [rbp-88h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+90h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A8h] [rbp-60h] BYREF
  int *v51; // [rsp+B8h] [rbp-50h]
  int v52; // [rsp+C0h] [rbp-48h]
  int v53; // [rsp+C4h] [rbp-44h]
  __int64 *v54; // [rsp+C8h] [rbp-40h]
  int v55; // [rsp+D0h] [rbp-38h]
  int v56; // [rsp+D4h] [rbp-34h]
  int *v57; // [rsp+D8h] [rbp-30h]
  __int64 v58; // [rsp+E0h] [rbp-28h]
  __int64 *v59; // [rsp+E8h] [rbp-20h]
  int v60; // [rsp+F0h] [rbp-18h]
  int v61; // [rsp+F4h] [rbp-14h]
  __int64 *v62; // [rsp+F8h] [rbp-10h]
  int v63; // [rsp+100h] [rbp-8h]
  int v64; // [rsp+104h] [rbp-4h]
  __int64 *v65; // [rsp+108h] [rbp+0h]
  int v66; // [rsp+110h] [rbp+8h]
  int v67; // [rsp+114h] [rbp+Ch]
  __int64 *v68; // [rsp+118h] [rbp+10h]
  int v69; // [rsp+120h] [rbp+18h]
  int v70; // [rsp+124h] [rbp+1Ch]
  __int64 *v71; // [rsp+128h] [rbp+20h]
  int v72; // [rsp+130h] [rbp+28h]
  int v73; // [rsp+134h] [rbp+2Ch]
  __int64 *v74; // [rsp+138h] [rbp+30h]
  int v75; // [rsp+140h] [rbp+38h]
  int v76; // [rsp+144h] [rbp+3Ch]
  int *v77; // [rsp+148h] [rbp+40h]
  __int64 v78; // [rsp+150h] [rbp+48h]
  int *v79; // [rsp+158h] [rbp+50h]
  __int64 v80; // [rsp+160h] [rbp+58h]
  int *v81; // [rsp+168h] [rbp+60h]
  __int64 v82; // [rsp+170h] [rbp+68h]
  int *v83; // [rsp+178h] [rbp+70h]
  __int64 v84; // [rsp+180h] [rbp+78h]
  int *v85; // [rsp+188h] [rbp+80h]
  __int64 v86; // [rsp+190h] [rbp+88h]
  int *v87; // [rsp+198h] [rbp+90h]
  __int64 v88; // [rsp+1A0h] [rbp+98h]
  int *v89; // [rsp+1A8h] [rbp+A0h]
  __int64 v90; // [rsp+1B0h] [rbp+A8h]
  int *v91; // [rsp+1B8h] [rbp+B0h]
  __int64 v92; // [rsp+1C0h] [rbp+B8h]
  int *v93; // [rsp+1C8h] [rbp+C0h]
  __int64 v94; // [rsp+1D0h] [rbp+C8h]
  int *v95; // [rsp+1D8h] [rbp+D0h]
  __int64 v96; // [rsp+1E0h] [rbp+D8h]
  _DWORD *v97; // [rsp+1E8h] [rbp+E0h]
  __int64 v98; // [rsp+1F0h] [rbp+E8h]

  LastError = 0;
  WppTraceIndent(a1, 2);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids, WPP_pszIndent);
  }
  for ( i = *(_QWORD *)(a1 + 136); i; i = *(_QWORD *)(i + 240) )
  {
    if ( *(_DWORD *)(i + 156) != 1 )
    {
      LastError = 0;
      WppTraceIndent(v3, 2);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          &WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
          WPP_pszIndent);
      }
      if ( *(_QWORD *)(i + 176) && *(_DWORD *)(a1 + 568) )
      {
        v6 = *(_DWORD *)(a1 + 576) == 1;
        pvPara = 0;
        if ( v6 )
        {
          v7 = CertOpenStore((LPCSTR)0xD, 0, 0, 0x40021000u, L"SmartCardRootCtrl");
        }
        else
        {
          *(_QWORD *)&pvPara = -2147483647;
          *((_QWORD *)&pvPara + 1) = L"SmartCardRootCtrl";
          v7 = CertOpenStore((LPCSTR)0xD, 0, 0, 0xC0011000, &pvPara);
        }
        v9 = v7;
        if ( v7 || (LastError = GetLastError()) == 0 )
        {
          LastError = RootInfoMergeRootsIntoStore(a1 + 592, v8, *(_QWORD *)(i + 176), v9, a1 + 592, i + 24);
          if ( !LastError )
          {
            if ( (v10 = *(HCERTSTORE *)(a1 + 584)) == 0
              && (v10 = CertOpenStore((LPCSTR)0xB, 0, 0, 0, 0), (*(_QWORD *)(a1 + 584) = v10) == 0)
              || !CertAddStoreToCollection(v10, *(HCERTSTORE *)(i + 176), 0, 0) )
            {
              LastError = GetLastError();
            }
          }
          if ( v9 )
            CertCloseStore(v9, 0);
        }
      }
      WppTraceIndent(v5, 2);
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
          WPP_pszIndent,
          LastError);
      }
      if ( LastError )
        goto LABEL_73;
      *(_DWORD *)(i + 156) = 1;
      if ( (unsigned int)dword_180031008 > 5 )
      {
        v11 = *(__int64 **)i;
        if ( *(_QWORD *)i )
        {
          v12 = -1;
          do
            v6 = *((_WORD *)v11 + ++v12) == 0;
          while ( !v6 );
          v13 = 2 * v12 + 2;
        }
        else
        {
          v11 = &qword_180027F58;
          v13 = 2;
        }
        v55 = v13;
        v14 = *(_DWORD *)(i + 8);
        v54 = v11;
        v15 = *(__int64 **)(i + 16);
        v44 = v14;
        v57 = &v44;
        v56 = 0;
        v58 = 4;
        if ( v15 )
        {
          v16 = -1;
          do
            v6 = *((_WORD *)v15 + ++v16) == 0;
          while ( !v6 );
          v17 = 2 * v16 + 2;
        }
        else
        {
          v15 = &qword_180027F58;
          v17 = 2;
        }
        v59 = v15;
        v18 = *(__int64 **)(i + 80);
        v60 = v17;
        v61 = 0;
        if ( v18 )
        {
          v19 = -1;
          do
            v6 = *((_WORD *)v18 + ++v19) == 0;
          while ( !v6 );
          v20 = 2 * v19 + 2;
        }
        else
        {
          v18 = &qword_180027F58;
          v20 = 2;
        }
        v62 = v18;
        v21 = *(__int64 **)(i + 88);
        v63 = v20;
        v64 = 0;
        if ( v21 )
        {
          v22 = -1;
          do
            v6 = *((_WORD *)v21 + ++v22) == 0;
          while ( !v6 );
          v23 = 2 * v22 + 2;
        }
        else
        {
          v21 = &qword_180027F58;
          v23 = 2;
        }
        v65 = v21;
        v24 = *(__int64 **)(i + 96);
        v66 = v23;
        v67 = 0;
        if ( v24 )
        {
          v25 = -1;
          do
            v6 = *((_WORD *)v24 + ++v25) == 0;
          while ( !v6 );
          v26 = 2 * v25 + 2;
        }
        else
        {
          v24 = &qword_180027F58;
          v26 = 2;
        }
        v68 = v24;
        v27 = *(__int64 **)(i + 104);
        v69 = v26;
        v70 = 0;
        if ( v27 )
        {
          v28 = -1;
          do
            v6 = *((_WORD *)v27 + ++v28) == 0;
          while ( !v6 );
          v29 = 2 * v28 + 2;
        }
        else
        {
          v27 = &qword_180027F58;
          v29 = 2;
        }
        v71 = v27;
        v30 = *(__int64 **)(i + 112);
        v72 = v29;
        v73 = 0;
        if ( v30 )
        {
          v31 = -1;
          do
            v6 = *((_WORD *)v30 + ++v31) == 0;
          while ( !v6 );
          v32 = 2 * v31 + 2;
        }
        else
        {
          v30 = &qword_180027F58;
          v32 = 2;
        }
        v75 = v32;
        v45 = *(_DWORD *)(i + 120);
        v77 = &v45;
        v33 = *(_DWORD *)(i + 160);
        v74 = v30;
        v46 = v33;
        v79 = &v46;
        v76 = 0;
        v78 = 4;
        v80 = 4;
        v82 = 4;
        v84 = 4;
        v86 = 4;
        v88 = 4;
        v90 = 4;
        v92 = 4;
        v94 = 4;
        if ( a1 == -24 )
        {
          v36 = 0;
          v81 = &v36;
          v83 = &v37;
          v85 = &v38;
          v87 = &v39;
          v89 = &v40;
          v91 = &v41;
          v93 = &v42;
          v95 = &v43;
          v34 = 0;
          v37 = 0;
          v38 = 0;
          v39 = 0;
          v40 = 0;
          v41 = 0;
          v42 = 0;
          v43 = 0;
        }
        else
        {
          v36 = *(_DWORD *)(a1 + 280);
          v81 = &v36;
          v37 = *(_DWORD *)(a1 + 24);
          v83 = &v37;
          v38 = *(_DWORD *)(a1 + 28);
          v85 = &v38;
          v39 = *(_DWORD *)(a1 + 32);
          v87 = &v39;
          v40 = *(_DWORD *)(a1 + 36);
          v89 = &v40;
          v41 = *(_DWORD *)(a1 + 40);
          v91 = &v41;
          v42 = *(_DWORD *)(a1 + 44);
          v93 = &v42;
          v43 = *(_DWORD *)(a1 + 64);
          v95 = &v43;
          v34 = *(_DWORD *)(a1 + 48);
        }
        v47[0] = v34;
        v96 = 4;
        v97 = v47;
        *(_DWORD *)&EventDescriptor.Level = 5;
        UserData.Ptr = (ULONGLONG)off_180031010;
        v98 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)off_180031010;
        UserData.Reserved = 2;
        v51 = &dword_180029BC4;
        v52 = 629;
        v53 = 1;
        v47[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, (LPCGUID)(i + 200), 0x15u, &UserData);
      }
    }
  }
  if ( g_RootsCleanupOption == 1 )
    LastError = CertPropRemoveRootCertificatesPerReaderList(a1, *(_QWORD *)(a1 + 136));
LABEL_73:
  WppTraceIndent(v3, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800103f0  mov     r11, rsp
0x1800103f3  push    rbp
0x1800103f4  push    rsi
0x1800103f5  lea     rbp, [r11-128h]
0x1800103fc  sub     rsp, 218h
0x180010403  mov     rax, cs:__security_cookie
0x18001040a  xor     rax, rsp
0x18001040d  mov     [rbp+120h+var_30], rax
0x180010414  mov     [r11+18h], rdi
0x180010418  mov     edx, 2
0x18001041d  mov     [r11+20h], r12
0x180010421  mov     [r11-20h], r14
0x180010425  mov     r14, rcx
0x180010428  mov     [r11-28h], r15
0x18001042c  xor     r15d, r15d
0x18001042f  mov     esi, r15d
0x180010432  call    WppTraceIndent
0x180010437  mov     rcx, cs:WPP_GLOBAL_Control
0x18001043e  lea     r12, WPP_GLOBAL_Control
0x180010445  cmp     rcx, r12
0x180010448  jz      short loc_180010472
0x18001044a  test    byte ptr [rcx+1Ch], 1
0x18001044e  jz      short loc_180010472
0x180010450  cmp     byte ptr [rcx+19h], 4
0x180010454  jb      short loc_180010472
0x180010456  mov     r9, cs:WPP_pszIndent
0x18001045d  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x180010464  mov     rcx, [rcx+10h]
0x180010468  mov     edx, 0Eh
0x18001046d  call    WPP_SF_s
0x180010472  mov     rdi, [r14+88h]
0x180010479  mov     [rsp+220h+arg_8], rbx
0x180010481  mov     [rsp+210h], r13
0x180010489  test    rdi, rdi
0x18001048c  jz      loc_180010AA5
0x180010492  lea     r13, aSmartcardrootc_0; "SmartCardRootCtrl"
0x180010499  lea     rbx, dword_180029BC4
0x1800104a0  cmp     dword ptr [rdi+9Ch], 1
0x1800104a7  jz      loc_180010A95
0x1800104ad  mov     edx, 2
0x1800104b2  mov     esi, r15d
0x1800104b5  call    WppTraceIndent
0x1800104ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104c1  cmp     rcx, r12
0x1800104c4  jz      short loc_1800104EE
0x1800104c6  test    byte ptr [rcx+1Ch], 1
0x1800104ca  jz      short loc_1800104EE
0x1800104cc  cmp     byte ptr [rcx+19h], 4
0x1800104d0  jb      short loc_1800104EE
0x1800104d2  mov     r9, cs:WPP_pszIndent
0x1800104d9  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x1800104e0  mov     rcx, [rcx+10h]
0x1800104e4  mov     edx, 0Ah
0x1800104e9  call    WPP_SF_s
0x1800104ee  cmp     [rdi+0B0h], rsi
0x1800104f5  jz      loc_1800105FF
0x1800104fb  cmp     [r14+238h], esi
0x180010502  jz      loc_1800105FF
0x180010508  xor     r8d, r8d; hCryptProv
0x18001050b  xor     edx, edx; dwEncodingType
0x18001050d  cmp     dword ptr [r14+240h], 1
0x180010515  xorps   xmm0, xmm0
0x180010518  movups  [rsp+220h+var_1B0+8], xmm0
0x18001051d  mov     ecx, 0Dh; lpszStoreProvider
0x180010522  jnz     short loc_180010531
0x180010524  mov     [rsp+220h+pvPara], r13
0x180010529  mov     r9d, 40021000h
0x18001052f  jmp     short loc_18001054E
0x180010531  lea     rax, [rsp+220h+var_1B0+8]
0x180010536  mov     qword ptr [rsp+220h+var_1B0+8], 0FFFFFFFF80000001h
0x18001053f  mov     [rsp+220h+pvPara], rax; pvPara
0x180010544  mov     r9d, 0C0011000h; dwFlags
0x18001054a  mov     [rbp+120h+var_1A0], r13
0x18001054e  call    cs:__imp_CertOpenStore
0x180010554  mov     rbx, rax
0x180010557  test    rax, rax
0x18001055a  jnz     short loc_18001056C
0x18001055c  call    cs:__imp_GetLastError
0x180010562  mov     esi, eax
0x180010564  test    eax, eax
0x180010566  jnz     loc_1800105F8
0x18001056c  mov     r8, [rdi+0B0h]
0x180010573  lea     rax, [rdi+18h]
0x180010577  lea     rcx, [r14+250h]
0x18001057e  mov     [rsp+28h], rax
0x180010583  mov     r9, rbx
0x180010586  mov     [rsp+220h+pvPara], rcx
0x18001058b  call    RootInfoMergeRootsIntoStore
0x180010590  mov     esi, eax
0x180010592  test    eax, eax
0x180010594  jnz     short loc_1800105E8
0x180010596  mov     rax, [r14+248h]
0x18001059d  test    rax, rax
0x1800105a0  jnz     short loc_1800105C6
0x1800105a2  xor     r9d, r9d; dwFlags
0x1800105a5  mov     [rsp+220h+pvPara], r15; pvPara
0x1800105aa  xor     r8d, r8d; hCryptProv
0x1800105ad  xor     edx, edx; dwEncodingType
0x1800105af  mov     ecx, 0Bh; lpszStoreProvider
0x1800105b4  call    cs:__imp_CertOpenStore
0x1800105ba  mov     [r14+248h], rax
0x1800105c1  test    rax, rax
0x1800105c4  jz      short loc_1800105E0
0x1800105c6  mov     rdx, [rdi+0B0h]; hSiblingStore
0x1800105cd  xor     r9d, r9d; dwPriority
0x1800105d0  xor     r8d, r8d; dwUpdateFlags
0x1800105d3  mov     rcx, rax; hCollectionStore
0x1800105d6  call    cs:__imp_CertAddStoreToCollection
0x1800105dc  test    eax, eax
0x1800105de  jnz     short loc_1800105E8
0x1800105e0  call    cs:__imp_GetLastError
0x1800105e6  mov     esi, eax
0x1800105e8  test    rbx, rbx
0x1800105eb  jz      short loc_1800105F8
0x1800105ed  xor     edx, edx; dwFlags
0x1800105ef  mov     rcx, rbx; hCertStore
0x1800105f2  call    cs:__imp_CertCloseStore
0x1800105f8  lea     rbx, dword_180029BC4
0x1800105ff  mov     edx, 2
0x180010604  call    WppTraceIndent
0x180010609  mov     rcx, cs:WPP_GLOBAL_Control
0x180010610  cmp     rcx, r12
0x180010613  jz      short loc_180010641
0x180010615  test    byte ptr [rcx+1Ch], 1
0x180010619  jz      short loc_180010641
0x18001061b  cmp     byte ptr [rcx+19h], 4
0x18001061f  jb      short loc_180010641
0x180010621  mov     r9, cs:WPP_pszIndent
0x180010628  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18001062f  mov     rcx, [rcx+10h]
0x180010633  mov     edx, 0Bh
0x180010638  mov     dword ptr [rsp+220h+pvPara], esi
0x18001063c  call    WPP_SF_sD
0x180010641  test    esi, esi
0x180010643  jnz     loc_180010ABF
0x180010649  mov     dword ptr [rdi+9Ch], 1
0x180010653  mov     eax, cs:dword_180031008
0x180010659  cmp     eax, 5
0x18001065c  jbe     loc_180010A95
0x180010662  mov     rcx, [rdi]
0x180010665  test    rcx, rcx
0x180010668  jz      short loc_180010686
0x18001066a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180010671  cmp     [rcx+rax*2+2], r15w
0x180010677  lea     rax, [rax+1]
0x18001067b  jnz     short loc_180010671
0x18001067d  lea     eax, ds:2[rax*2]
0x180010684  jmp     short loc_180010692
0x180010686  lea     rcx, qword_180027F58
0x18001068d  mov     eax, 2
0x180010692  mov     [rbp+120h+var_158], eax
0x180010695  mov     eax, [rdi+8]
0x180010698  mov     [rbp+120h+var_160], rcx
0x18001069c  mov     rcx, [rdi+10h]
0x1800106a0  mov     [rsp+220h+var_1C0], eax
0x1800106a4  lea     rax, [rsp+220h+var_1C0]
0x1800106a9  mov     [rbp+120h+var_150], rax
0x1800106ad  mov     [rbp+120h+var_154], r15d
0x1800106b1  mov     [rbp+120h+var_148], 4
0x1800106b9  test    rcx, rcx
0x1800106bc  jz      short loc_1800106E5
0x1800106be  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800106c5  nop     word ptr [rax+rax+00000000h]
0x1800106d0  cmp     [rcx+rax*2+2], r15w
0x1800106d6  lea     rax, [rax+1]
0x1800106da  jnz     short loc_1800106D0
0x1800106dc  lea     eax, ds:2[rax*2]
0x1800106e3  jmp     short loc_1800106F1
0x1800106e5  lea     rcx, qword_180027F58
0x1800106ec  mov     eax, 2
0x1800106f1  mov     [rbp+120h+var_140], rcx
0x1800106f5  mov     rcx, [rdi+50h]
0x1800106f9  mov     [rbp+120h+var_138], eax
0x1800106fc  mov     [rbp+120h+var_134], r15d
0x180010700  test    rcx, rcx
0x180010703  jz      short loc_180010725
0x180010705  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001070c  nop     dword ptr [rax+00h]
0x180010710  cmp     [rcx+rax*2+2], r15w
0x180010716  lea     rax, [rax+1]
0x18001071a  jnz     short loc_180010710
0x18001071c  lea     eax, ds:2[rax*2]
0x180010723  jmp     short loc_180010731
0x180010725  lea     rcx, qword_180027F58
0x18001072c  mov     eax, 2
0x180010731  mov     [rbp+120h+var_130], rcx
0x180010735  mov     rcx, [rdi+58h]
0x180010739  mov     [rbp+120h+var_128], eax
0x18001073c  mov     [rbp+120h+var_124], r15d
0x180010740  test    rcx, rcx
0x180010743  jz      short loc_180010765
0x180010745  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001074c  nop     dword ptr [rax+00h]
0x180010750  cmp     [rcx+rax*2+2], r15w
0x180010756  lea     rax, [rax+1]
0x18001075a  jnz     short loc_180010750
0x18001075c  lea     eax, ds:2[rax*2]
0x180010763  jmp     short loc_180010771
0x180010765  lea     rcx, qword_180027F58
0x18001076c  mov     eax, 2
0x180010771  mov     [rbp+120h+var_120], rcx
0x180010775  mov     rcx, [rdi+60h]
0x180010779  mov     [rbp+120h+var_118], eax
0x18001077c  mov     [rbp+120h+var_114], r15d
0x180010780  test    rcx, rcx
0x180010783  jz      short loc_1800107A5
0x180010785  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001078c  nop     dword ptr [rax+00h]
0x180010790  cmp     [rcx+rax*2+2], r15w
0x180010796  lea     rax, [rax+1]
0x18001079a  jnz     short loc_180010790
0x18001079c  lea     eax, ds:2[rax*2]
0x1800107a3  jmp     short loc_1800107B1
0x1800107a5  lea     rcx, qword_180027F58
0x1800107ac  mov     eax, 2
0x1800107b1  mov     [rbp+120h+var_110], rcx
0x1800107b5  mov     rcx, [rdi+68h]
0x1800107b9  mov     [rbp+120h+var_108], eax
0x1800107bc  mov     [rbp+120h+var_104], r15d
0x1800107c0  test    rcx, rcx
0x1800107c3  jz      short loc_1800107E5
0x1800107c5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800107cc  nop     dword ptr [rax+00h]
0x1800107d0  cmp     [rcx+rax*2+2], r15w
0x1800107d6  lea     rax, [rax+1]
0x1800107da  jnz     short loc_1800107D0
0x1800107dc  lea     eax, ds:2[rax*2]
0x1800107e3  jmp     short loc_1800107F1
0x1800107e5  lea     rcx, qword_180027F58
0x1800107ec  mov     eax, 2
0x1800107f1  mov     [rbp+120h+var_100], rcx
0x1800107f5  mov     rcx, [rdi+70h]
0x1800107f9  mov     [rbp+120h+var_F8], eax
0x1800107fc  mov     [rbp+120h+var_F4], r15d
0x180010800  test    rcx, rcx
0x180010803  jz      short loc_180010825
0x180010805  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001080c  nop     dword ptr [rax+00h]
0x180010810  cmp     [rcx+rax*2+2], r15w
0x180010816  lea     rax, [rax+1]
0x18001081a  jnz     short loc_180010810
0x18001081c  lea     eax, ds:2[rax*2]
0x180010823  jmp     short loc_180010831
0x180010825  lea     rcx, qword_180027F58
0x18001082c  mov     eax, 2
0x180010831  mov     [rbp+120h+var_E8], eax
0x180010834  mov     eax, [rdi+78h]
0x180010837  mov     [rsp+220h+var_1BC], eax
0x18001083b  lea     rax, [rsp+220h+var_1BC]
0x180010840  mov     [rbp+120h+var_E0], rax
0x180010844  mov     eax, [rdi+0A0h]
0x18001084a  mov     [rbp+120h+var_F0], rcx
0x18001084e  lea     rcx, [r14+18h]
0x180010852  mov     [rsp+220h+var_1B8], eax
0x180010856  lea     rax, [rsp+220h+var_1B8]
0x18001085b  mov     [rbp+120h+var_D0], rax
0x18001085f  mov     [rbp+120h+var_E4], r15d
0x180010863  mov     [rbp+120h+var_D8], 4
0x18001086b  mov     [rbp+120h+var_C8], 4
0x180010873  mov     [rbp+120h+var_B8], 4
0x18001087b  mov     [rbp+120h+var_A8], 4
0x180010883  mov     [rbp+120h+var_98], 4
0x18001088e  mov     [rbp+120h+var_88], 4
0x180010899  mov     [rbp+120h+var_78], 4
0x1800108a4  mov     [rbp+120h+var_68], 4
0x1800108af  mov     [rbp+120h+var_58], 4
0x1800108ba  test    rcx, rcx
0x1800108bd  jz      loc_180010967
0x1800108c3  mov     eax, [r14+118h]
0x1800108ca  mov     [rsp+220h+var_1E0], eax
0x1800108ce  lea     rax, [rsp+220h+var_1E0]
0x1800108d3  mov     [rbp+120h+var_C0], rax
0x1800108d7  mov     eax, [rcx]
0x1800108d9  mov     [rsp+220h+var_1DC], eax
0x1800108dd  lea     rax, [rsp+220h+var_1DC]
0x1800108e2  mov     [rbp+120h+var_B0], rax
0x1800108e6  mov     eax, [r14+1Ch]
0x1800108ea  mov     [rsp+220h+var_1D8], eax
0x1800108ee  lea     rax, [rsp+220h+var_1D8]
0x1800108f3  mov     [rbp+120h+var_A0], rax
0x1800108fa  mov     eax, [r14+20h]
0x1800108fe  mov     [rsp+220h+var_1D4], eax
0x180010902  lea     rax, [rsp+220h+var_1D4]
0x180010907  mov     [rbp+120h+var_90], rax
0x18001090e  mov     eax, [r14+24h]
0x180010912  mov     [rsp+220h+var_1D0], eax
0x180010916  lea     rax, [rsp+220h+var_1D0]
0x18001091b  mov     [rbp+120h+var_80], rax
0x180010922  mov     eax, [r14+28h]
0x180010926  mov     [rsp+220h+var_1CC], eax
0x18001092a  lea     rax, [rsp+220h+var_1CC]
0x18001092f  mov     [rbp+120h+var_70], rax
0x180010936  mov     eax, [r14+2Ch]
0x18001093a  mov     [rsp+220h+var_1C8], eax
0x18001093e  lea     rax, [rsp+220h+var_1C8]
0x180010943  mov     [rbp+120h+var_60], rax
0x18001094a  mov     eax, [r14+40h]
0x18001094e  mov     [rsp+220h+var_1C4], eax
0x180010952  lea     rax, [rsp+220h+var_1C4]
0x180010957  mov     [rbp+120h+var_50], rax
  ... truncated ...
```
