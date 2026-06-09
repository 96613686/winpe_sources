# InternalCreateColorTransform(tagLOGCOLORSPACEW *,void *,void *,ulong)

- ea: `0x18003cec4`
- end: `0x18003d697`
- name: `?InternalCreateColorTransform@@YAPEAXPEAUtagLOGCOLORSPACEW@@PEAX1K@Z`
- size: `2003`
- prototype: `void *__fastcall(struct tagLOGCOLORSPACEW *, void *, void *, unsigned int)`
- caller_count: `2`
- callee_count: `19`
- tags: `loader_planting`

## callers

- `0x18003dbd0`
- `0x18003dd10`

## callees

- `0x18000a740`
- `0x18000b828`
- `0x18000bce0`
- `0x18000be44`
- `0x18000bf9c`
- `0x18000c310`
- `0x18000c38c`
- `0x18000e184`
- `0x18000ef40`
- `0x18000efa0`
- `0x18000fe30`
- `0x1800181d0`
- `0x180018eb0`
- `0x180021aec`
- `0x18002e5f0`
- `0x18003cec4`
- `0x18003d8c8`
- `0x180051480`
- `0x180084010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18003d0d6`
- `ntdll!EtwEventWrite` at `0x18003d3ce`
- `ntdll!EtwEventWrite` at `0x18003d65d`
- `ntdll!EtwEventWrite` at `0x18003d0d6`
- `ntdll!EtwEventWrite` at `0x18003d3ce`
- `ntdll!EtwEventWrite` at `0x18003d65d`
- `ntdll!EtwEventEnabled` at `0x18003cf39`
- `ntdll!EtwEventEnabled` at `0x18003cf39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d1cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d373`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d571`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d5df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d667`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d1cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d373`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d571`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d5df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d62a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d62a`

## pseudocode

```c
__int64 __fastcall InternalCreateColorTransform(
        struct tagLOGCOLORSPACEW *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned int a4)
{
  unsigned __int64 v5; // r13
  __int64 v6; // rsi
  __int64 v7; // r14
  DWORD v8; // r12d
  __int64 v11; // r8
  const OLECHAR *v12; // r9
  const OLECHAR *v13; // r11
  WCHAR *lcsFilename; // r10
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  int v19; // eax
  unsigned int v20; // r9d
  int valid; // r8d
  int v22; // eax
  unsigned int v23; // r9d
  unsigned int v24; // eax
  __int64 v25; // rcx
  __int64 FPU; // r12
  _OWORD *v27; // rax
  char *v28; // r8
  DWORD v29; // ecx
  __int64 v30; // rdx
  struct tagLOGCOLORSPACEW *v31; // rcx
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  signed int v34; // ebx
  enum COLORPROFILESUBTYPE v35; // edi
  enum COLORPROFILESUBTYPE v36; // r9d
  void *v37; // r11
  DWORD v38; // ecx
  HPROFILE v39; // rax
  HPROFILE v40; // r8
  DWORD v41; // r11d
  __int64 v42; // rdi
  int v43; // ebx
  LPVOID v44; // r15
  int v45; // eax
  __int64 PreferredCMM; // rbx
  __int64 HeapObject; // rax
  __int64 v48; // r8
  unsigned __int64 v49; // rax
  unsigned int lcsCSType; // [rsp+40h] [rbp-C0h] BYREF
  int v52; // [rsp+44h] [rbp-BCh]
  DWORD dwErrCode; // [rsp+48h] [rbp-B8h] BYREF
  int v54; // [rsp+4Ch] [rbp-B4h]
  unsigned int v55; // [rsp+50h] [rbp-B0h]
  unsigned int v56; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v57; // [rsp+60h] [rbp-A0h]
  LPVOID lpMem; // [rsp+68h] [rbp-98h]
  LCSGAMUTMATCH lcsIntent; // [rsp+70h] [rbp-90h] BYREF
  int v60; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned __int64 v61; // [rsp+78h] [rbp-88h] BYREF
  __int64 v62; // [rsp+80h] [rbp-80h] BYREF
  PROFILE pCDMPProfile; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 p_dwErrCode; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v65; // [rsp+A8h] [rbp-58h]
  _QWORD v66[5]; // [rsp+B0h] [rbp-50h] BYREF
  int v67; // [rsp+D8h] [rbp-28h]
  int v68; // [rsp+DCh] [rbp-24h]
  int *v69; // [rsp+E0h] [rbp-20h]
  __int64 v70; // [rsp+E8h] [rbp-18h]
  const OLECHAR *v71; // [rsp+F0h] [rbp-10h]
  int v72; // [rsp+F8h] [rbp-8h]
  int v73; // [rsp+FCh] [rbp-4h]
  unsigned __int64 *v74; // [rsp+100h] [rbp+0h]
  __int64 v75; // [rsp+108h] [rbp+8h]
  const OLECHAR *v76; // [rsp+110h] [rbp+10h]
  int v77; // [rsp+118h] [rbp+18h]
  int v78; // [rsp+11Ch] [rbp+1Ch]
  unsigned int *v79; // [rsp+120h] [rbp+20h]
  __int64 v80; // [rsp+128h] [rbp+28h]

  p_dwErrCode = a2;
  v56 = a4;
  v5 = 0;
  v57 = 0;
  v6 = 0;
  v62 = 0;
  v7 = 0;
  lpMem = 0;
  v8 = 0;
  dwErrCode = 0;
  v54 = 0;
  v52 = 0;
  v55 = 0;
  if ( (unsigned __int8)EtwEventEnabled(g_etwHandle, CREATING_COLOR_TRANSFORM) )
  {
    v11 = -1;
    v60 = -1;
    lcsCSType = -1;
    v12 = &word_1800884E0;
    lcsIntent = -1;
    v13 = &word_1800884E0;
    LODWORD(v61) = -1;
    if ( a1 )
    {
      lcsFilename = a1->lcsFilename;
      lcsCSType = a1->lcsCSType;
      lcsIntent = a1->lcsIntent;
    }
    else
    {
      lcsFilename = (WCHAR *)&word_1800884E0;
    }
    if ( a2 )
    {
      if ( (unsigned int)ValidHandle(a2, 1347569228) )
      {
        if ( a2 != 0x49434D20 )
        {
          v60 = *(_DWORD *)((a2 ^ 0x49434D20) + 8);
          if ( v60 == 1 )
            v12 = *(const OLECHAR **)((a2 ^ 0x49434D20) + 0x10);
        }
      }
    }
    if ( a3 )
    {
      if ( (unsigned int)ValidHandle(a3, 1347569228) )
      {
        v5 = a3 ^ 0x49434D20;
        if ( a3 != 0x49434D20 )
        {
          LODWORD(v61) = *(_DWORD *)((a3 ^ 0x49434D20) + 8);
          if ( (_DWORD)v61 == 1 )
            v13 = *(const OLECHAR **)((a3 ^ 0x49434D20) + 0x10);
        }
      }
    }
    v66[1] = 4;
    v66[0] = &lcsCSType;
    v66[2] = &lcsIntent;
    v66[3] = 4;
    if ( lcsFilename )
    {
      v15 = v11;
      do
        ++v15;
      while ( lcsFilename[v15] );
      v16 = 2 * v15 + 2;
    }
    else
    {
      v16 = 0;
    }
    v67 = v16;
    v69 = &v60;
    v66[4] = lcsFilename;
    v68 = 0;
    v70 = 4;
    if ( v12 )
    {
      v17 = v11;
      do
        ++v17;
      while ( v12[v17] );
      v18 = 2 * v17 + 2;
    }
    else
    {
      v18 = 0;
    }
    v72 = v18;
    v74 = &v61;
    v71 = v12;
    v73 = 0;
    v75 = 4;
    if ( v13 )
    {
      do
        ++v11;
      while ( v13[v11] );
      v19 = 2 * v11 + 2;
    }
    else
    {
      v19 = 0;
    }
    v77 = v19;
    v78 = 0;
    v79 = &v56;
    v76 = v13;
    v80 = 4;
    EtwEventWrite(g_etwHandle, CREATING_COLOR_TRANSFORM, 8, v66);
  }
  if ( a2 )
  {
    dwErrCode = ValidHandle(a2, 1347569228);
    v8 = dwErrCode;
    if ( dwErrCode )
    {
      valid = 0;
    }
    else
    {
      valid = ValidHandle(a2, v20);
      v54 = valid;
    }
  }
  else
  {
    valid = 0;
  }
  if ( a3 )
  {
    v22 = ValidHandle(a3, 1347569228);
    v52 = v22;
    if ( v22 )
    {
      v25 = 0;
    }
    else
    {
      v24 = ValidHandle(a3, v23);
      v25 = v24;
      v55 = v24;
      v22 = v52;
    }
  }
  else
  {
    v22 = 0;
    v25 = 0;
  }
  if ( !a1 || a1->lcsSignature != 1347637059 || a1->lcsVersion < 0x400 || !v8 && !valid || a3 && !v22 && !(_DWORD)v25 )
  {
    FPU = 0;
    v29 = 87;
    goto LABEL_51;
  }
  FPU = CreateFPU(v25, 0);
  if ( FPU )
  {
    v27 = (_OWORD *)MemAlloc(604);
    lpMem = v27;
    v28 = (char *)v27;
    if ( !v27 )
    {
      v29 = 8;
LABEL_51:
      SetLastError(v29);
      goto LABEL_72;
    }
    v30 = 4;
    v31 = a1;
    do
    {
      *v27 = *(_OWORD *)&v31->lcsSignature;
      v27[1] = *(_OWORD *)&v31->lcsIntent;
      v27[2] = *(_OWORD *)&v31->lcsEndpoints.ciexyzGreen.ciexyzX;
      v27[3] = *(_OWORD *)&v31->lcsEndpoints.ciexyzBlue.ciexyzY;
      v27[4] = *(_OWORD *)&v31->lcsGammaBlue;
      v27[5] = *(_OWORD *)&v31->lcsFilename[6];
      v27[6] = *(_OWORD *)&v31->lcsFilename[14];
      v32 = *(_OWORD *)&v31->lcsFilename[22];
      v31 = (struct tagLOGCOLORSPACEW *)((char *)v31 + 128);
      v27[7] = v32;
      v27 += 8;
      --v30;
    }
    while ( v30 );
    *v27 = *(_OWORD *)&v31->lcsSignature;
    v27[1] = *(_OWORD *)&v31->lcsIntent;
    v27[2] = *(_OWORD *)&v31->lcsEndpoints.ciexyzGreen.ciexyzX;
    v27[3] = *(_OWORD *)&v31->lcsEndpoints.ciexyzBlue.ciexyzY;
    v33 = *(_OWORD *)&v31->lcsGammaGreen;
    *(_QWORD *)(v28 + 588) = a2;
    *(_QWORD *)(v28 + 596) = a3;
    *(_OWORD *)((char *)v27 + 60) = v33;
    v34 = *((_DWORD *)v28 + 3);
    if ( v34 <= 2 )
    {
      if ( !a1->lcsFilename[0] && !v34 )
        LODWORD(v6) = 1;
    }
    else
    {
      lcsCSType = 520;
      v35 = CPST_CUSTOM_WORKING_SPACE;
      if ( v34 == 1934772034 || (v36 = CPST_CUSTOM_WORKING_SPACE, v34 == 1466527264) )
        v36 = CPST_RGB_WORKING_SPACE;
      if ( !(unsigned int)InternalGetDefaultColorProfile(
                            WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER,
                            0,
                            CPT_ICC,
                            v36,
                            v34,
                            0,
                            &lcsCSType,
                            0) )
        goto LABEL_71;
      if ( lpMem == (LPVOID)-68LL || lcsCSType > 0x208 )
      {
        v38 = 122;
        goto LABEL_70;
      }
      if ( v34 == 1934772034 || v34 == 1466527264 )
        v35 = CPST_RGB_WORKING_SPACE;
      if ( !(unsigned int)InternalGetDefaultColorProfile(
                            WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER,
                            0,
                            CPT_ICC,
                            v35,
                            v34,
                            (unsigned __int16 *)lpMem + 34,
                            &lcsCSType,
                            0) )
        goto LABEL_71;
      v28 = (char *)lpMem;
    }
    if ( *((_WORD *)v28 + 34) )
    {
      v61 = 0;
      memset(&pCDMPProfile, 0, sizeof(pCDMPProfile));
      if ( (int)StringCchLengthW((const unsigned __int16 *)v28 + 34, 0x104u, &v61) < 0 )
      {
LABEL_68:
        v38 = 2011;
LABEL_70:
        SetLastError(v38);
LABEL_71:
        v6 = v57;
        goto LABEL_72;
      }
      pCDMPProfile.dwType = 1;
      pCDMPProfile.pProfileData = v37;
      pCDMPProfile.cbDataSize = 2 * v61 + 2;
      v39 = WcsOpenColorProfileW(&pCDMPProfile, 0, 0, 1u, 1u, 3u, 0);
      if ( !v39 )
        goto LABEL_71;
      LODWORD(v6) = ValidHandle(v39, 1347569228);
      CloseColorProfile(v40);
    }
    v41 = dwErrCode;
    v42 = p_dwErrCode ^ 0x49434D20;
    if ( dwErrCode && !ValidProfile(p_dwErrCode ^ 0x49434D20) )
      goto LABEL_68;
    if ( v54 && !*(_QWORD *)(v42 + 64) )
      goto LABEL_68;
    v43 = v52;
    if ( a3 )
    {
      v5 = a3 ^ 0x49434D20;
      if ( v52 )
      {
        if ( !ValidProfile(a3 ^ 0x49434D20) )
          goto LABEL_68;
      }
      if ( v55 && !*(_QWORD *)((a3 ^ 0x49434D20) + 0x40) )
        goto LABEL_68;
    }
    if ( (_DWORD)v6 && v41 && (!a3 || v43) && (v56 & 0x200000) == 0 )
    {
      v6 = v57;
      v44 = lpMem;
    }
    else
    {
      v44 = lpMem;
      v45 = CITECreateWcsTransform((struct tagLOGCOLORSPACEW *)lpMem, (__int64)&v62);
      if ( v45 < 0 )
      {
        SetLastErrorFromHRESULT((unsigned int)v45, 2011);
        v6 = v62;
        goto LABEL_72;
      }
      v6 = v62;
      if ( v62 )
        goto LABEL_72;
    }
    PreferredCMM = GetPreferredCMM();
    if ( !PreferredCMM )
    {
      PreferredCMM = (__int64)GetColorMatchingModule(_byteswap_ulong(*(_DWORD *)(*(_QWORD *)(v42 + 56) + 4LL)));
      if ( !PreferredCMM )
      {
        PreferredCMM = (__int64)GetColorMatchingModule(0x57696E20u);
        if ( !PreferredCMM )
        {
          v29 = 2010;
          goto LABEL_51;
        }
      }
    }
    HeapObject = AllocateHeapObject(1481003597);
    v6 = HeapObject;
    if ( HeapObject )
    {
      v7 = HeapObject ^ 0x49434D20;
      *(_QWORD *)(v7 + 8) = PreferredCMM;
      *(_DWORD *)(v7 + 4) = 1;
      if ( v5 )
        v48 = *(_QWORD *)(v5 + 56);
      else
        v48 = 0;
      v49 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, _QWORD))(PreferredCMM + 40))(
              v44,
              *(_QWORD *)(v42 + 56),
              v48,
              v56);
      *(_QWORD *)((v6 ^ 0x49434D20) + 0x10) = v49;
      if ( v49 <= 0xFF )
      {
        if ( !GetLastError() )
          SetLastError(0x7DBu);
        ReleaseColorMatchingModule(*(_QWORD *)((v6 ^ 0x49434D20) + 8));
        --*(_DWORD *)((v6 ^ 0x49434D20) + 4);
        *(_DWORD *)v7 = 0;
        MemFree((LPVOID)(v6 ^ 0x49434D20));
        v6 = 0;
        v7 = 0;
      }
    }
    else
    {
      SetLastError(8u);
      ReleaseColorMatchingModule(PreferredCMM);
    }
  }
LABEL_72:
  MemFree(lpMem);
  DeleteFPU(FPU);
  if ( v7 && *(_QWORD *)(v7 + 16) > 0xFFu )
  {
    p_dwErrCode = v7 + 16;
    v65 = 8;
    EtwEventWrite(g_etwHandle, CREATED_COLOR_TRANSFORM, 1, &p_dwErrCode);
  }
  else
  {
    dwErrCode = GetLastError();
    v65 = 4;
    p_dwErrCode = (unsigned __int64)&dwErrCode;
    EtwEventWrite(g_etwHandle, COLOR_TRANSFORM_CREATION_FAILED, 1, &p_dwErrCode);
    SetLastError(dwErrCode);
  }
  return v6;
}

```

## disassembly

```asm
0x18003cec4  mov     [rsp-8+arg_0], rbx
0x18003cec9  push    rbp
0x18003ceca  push    rsi
0x18003cecb  push    rdi
0x18003cecc  push    r12
0x18003cece  push    r13
0x18003ced0  push    r14
0x18003ced2  push    r15
0x18003ced4  lea     rbp, [rsp-40h]
0x18003ced9  sub     rsp, 140h
0x18003cee0  mov     rax, cs:__security_cookie
0x18003cee7  xor     rax, rsp
0x18003ceea  mov     [rbp+70h+var_40], rax
0x18003ceee  mov     rdi, rcx
0x18003cef1  mov     [rbp+70h+var_D0], rdx
0x18003cef5  xor     ecx, ecx
0x18003cef7  mov     [rsp+170h+var_118], r9d
0x18003cefc  mov     r13d, ecx
0x18003ceff  mov     [rsp+170h+var_110], rcx
0x18003cf04  mov     esi, ecx
0x18003cf06  mov     [rbp+70h+var_F0], rcx
0x18003cf0a  mov     r14d, ecx
0x18003cf0d  mov     [rsp+170h+lpMem], rcx
0x18003cf12  mov     r12d, ecx
0x18003cf15  mov     [rsp+170h+dwErrCode], ecx
0x18003cf19  mov     [rsp+170h+var_124], ecx
0x18003cf1d  mov     rbx, rdx
0x18003cf20  mov     [rsp+170h+var_12C], ecx
0x18003cf24  lea     rdx, CREATING_COLOR_TRANSFORM
0x18003cf2b  mov     [rsp+170h+var_120], ecx
0x18003cf2f  mov     r15, r8
0x18003cf32  mov     rcx, cs:g_etwHandle
0x18003cf39  call    cs:__imp_EtwEventEnabled
0x18003cf3f  or      ecx, 0FFFFFFFFh
0x18003cf42  xor     edx, edx
0x18003cf44  test    al, al
0x18003cf46  jz      loc_18003D0DE
0x18003cf4c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003cf50  mov     [rsp+170h+var_FC], ecx
0x18003cf54  mov     [rsp+170h+var_130], r8d
0x18003cf59  lea     r9, word_1800884E0
0x18003cf60  mov     [rsp+170h+var_100], r8d
0x18003cf65  mov     r11, r9
0x18003cf68  mov     dword ptr [rsp+170h+var_F8], ecx
0x18003cf6c  test    rdi, rdi
0x18003cf6f  jz      short loc_18003CF85
0x18003cf71  mov     eax, [rdi+0Ch]
0x18003cf74  lea     r10, [rdi+44h]
0x18003cf78  mov     [rsp+170h+var_130], eax
0x18003cf7c  mov     eax, [rdi+10h]
0x18003cf7f  mov     [rsp+170h+var_100], eax
0x18003cf83  jmp     short loc_18003CF88
0x18003cf85  mov     r10, r9
0x18003cf88  test    rbx, rbx
0x18003cf8b  jz      short loc_18003CFBC
0x18003cf8d  mov     edx, 5052464Ch
0x18003cf92  mov     rcx, rbx
0x18003cf95  call    ValidHandle
0x18003cf9a  xor     edx, edx
0x18003cf9c  test    eax, eax
0x18003cf9e  jz      short loc_18003CFBC
0x18003cfa0  mov     rcx, rbx
0x18003cfa3  xor     rcx, 49434D20h
0x18003cfaa  jz      short loc_18003CFBC
0x18003cfac  mov     eax, [rcx+8]
0x18003cfaf  mov     [rsp+170h+var_FC], eax
0x18003cfb3  cmp     eax, 1
0x18003cfb6  jnz     short loc_18003CFBC
0x18003cfb8  mov     r9, [rcx+10h]
0x18003cfbc  test    r15, r15
0x18003cfbf  jz      short loc_18003CFF1
0x18003cfc1  mov     edx, 5052464Ch
0x18003cfc6  mov     rcx, r15
0x18003cfc9  call    ValidHandle
0x18003cfce  xor     edx, edx
0x18003cfd0  test    eax, eax
0x18003cfd2  jz      short loc_18003CFF1
0x18003cfd4  mov     r13, r15
0x18003cfd7  xor     r13, 49434D20h
0x18003cfde  jz      short loc_18003CFF1
0x18003cfe0  mov     eax, [r13+8]
0x18003cfe4  mov     dword ptr [rsp+170h+var_F8], eax
0x18003cfe8  cmp     eax, 1
0x18003cfeb  jnz     short loc_18003CFF1
0x18003cfed  mov     r11, [r13+10h]
0x18003cff1  mov     [rbp+70h+var_B8], 4
0x18003cff9  lea     rax, [rsp+170h+var_130]
0x18003cffe  mov     [rbp+70h+var_C0], rax
0x18003d002  lea     rax, [rsp+170h+var_100]
0x18003d007  mov     [rbp+70h+var_B0], rax
0x18003d00b  mov     [rbp+70h+var_A8], 4
0x18003d013  test    r10, r10
0x18003d016  jz      short loc_18003D02F
0x18003d018  mov     rax, r8
0x18003d01b  inc     rax
0x18003d01e  cmp     [r10+rax*2], dx
0x18003d023  jnz     short loc_18003D01B
0x18003d025  lea     rax, ds:2[rax*2]
0x18003d02d  jmp     short loc_18003D032
0x18003d02f  mov     rax, rdx
0x18003d032  mov     [rbp+70h+var_98], eax
0x18003d035  lea     rax, [rsp+170h+var_FC]
0x18003d03a  mov     [rbp+70h+var_90], rax
0x18003d03e  mov     [rbp+70h+var_A0], r10
0x18003d042  mov     [rbp+70h+var_94], edx
0x18003d045  mov     [rbp+70h+var_88], 4
0x18003d04d  test    r9, r9
0x18003d050  jz      short loc_18003D069
0x18003d052  mov     rax, r8
0x18003d055  inc     rax
0x18003d058  cmp     [r9+rax*2], dx
0x18003d05d  jnz     short loc_18003D055
0x18003d05f  lea     rax, ds:2[rax*2]
0x18003d067  jmp     short loc_18003D06C
0x18003d069  mov     rax, rdx
0x18003d06c  mov     [rbp+70h+var_78], eax
0x18003d06f  lea     rax, [rsp+170h+var_F8]
0x18003d074  mov     [rbp+70h+var_70], rax
0x18003d078  mov     [rbp+70h+var_80], r9
0x18003d07c  mov     [rbp+70h+var_74], edx
0x18003d07f  mov     [rbp+70h+var_68], 4
0x18003d087  test    r11, r11
0x18003d08a  jz      short loc_18003D0A0
0x18003d08c  inc     r8
0x18003d08f  cmp     [r11+r8*2], dx
0x18003d094  jnz     short loc_18003D08C
0x18003d096  lea     rax, ds:2[r8*2]
0x18003d09e  jmp     short loc_18003D0A3
0x18003d0a0  mov     rax, rdx
0x18003d0a3  mov     rcx, cs:g_etwHandle
0x18003d0aa  lea     r9, [rbp+70h+var_C0]
0x18003d0ae  mov     [rbp+70h+var_58], eax
0x18003d0b1  mov     r8d, 8
0x18003d0b7  lea     rax, [rsp+170h+var_118]
0x18003d0bc  mov     [rbp+70h+var_54], edx
0x18003d0bf  lea     rdx, CREATING_COLOR_TRANSFORM
0x18003d0c6  mov     [rbp+70h+var_50], rax
0x18003d0ca  mov     [rbp+70h+var_60], r11
0x18003d0ce  mov     [rbp+70h+var_48], 4
0x18003d0d6  call    cs:__imp_EtwEventWrite
0x18003d0dc  xor     edx, edx
0x18003d0de  mov     r9d, 43584D4Ch
0x18003d0e4  test    rbx, rbx
0x18003d0e7  jz      short loc_18003D119
0x18003d0e9  mov     edx, 5052464Ch
0x18003d0ee  mov     rcx, rbx
0x18003d0f1  call    ValidHandle
0x18003d0f6  xor     edx, edx
0x18003d0f8  mov     [rsp+170h+dwErrCode], eax
0x18003d0fc  mov     r12d, eax
0x18003d0ff  test    eax, eax
0x18003d101  jnz     short loc_18003D11E
0x18003d103  mov     edx, r9d
0x18003d106  mov     rcx, rbx
0x18003d109  call    ValidHandle
0x18003d10e  mov     r8d, eax
0x18003d111  mov     [rsp+170h+var_124], eax
0x18003d115  xor     edx, edx
0x18003d117  jmp     short loc_18003D121
0x18003d119  mov     r8d, esi
0x18003d11c  jmp     short loc_18003D121
0x18003d11e  mov     r8d, edx
0x18003d121  test    r15, r15
0x18003d124  jz      short loc_18003D156
0x18003d126  mov     edx, 5052464Ch
0x18003d12b  mov     rcx, r15
0x18003d12e  call    ValidHandle
0x18003d133  xor     edx, edx
0x18003d135  mov     [rsp+170h+var_12C], eax
0x18003d139  test    eax, eax
0x18003d13b  jnz     short loc_18003D15C
0x18003d13d  mov     edx, r9d
0x18003d140  mov     rcx, r15
0x18003d143  call    ValidHandle
0x18003d148  mov     ecx, eax
0x18003d14a  mov     [rsp+170h+var_120], eax
0x18003d14e  mov     eax, [rsp+170h+var_12C]
0x18003d152  xor     edx, edx
0x18003d154  jmp     short loc_18003D15E
0x18003d156  mov     eax, esi
0x18003d158  mov     ecx, esi
0x18003d15a  jmp     short loc_18003D15E
0x18003d15c  mov     ecx, edx
0x18003d15e  test    rdi, rdi
0x18003d161  jz      loc_18003D61D
0x18003d167  cmp     dword ptr [rdi], 50534F43h
0x18003d16d  jnz     loc_18003D61D
0x18003d173  cmp     dword ptr [rdi+4], 400h
0x18003d17a  jb      loc_18003D61D
0x18003d180  test    r12d, r12d
0x18003d183  jnz     short loc_18003D18E
0x18003d185  test    r8d, r8d
0x18003d188  jz      loc_18003D61D
0x18003d18e  test    r15, r15
0x18003d191  jz      short loc_18003D19F
0x18003d193  test    eax, eax
0x18003d195  jnz     short loc_18003D19F
0x18003d197  test    ecx, ecx
0x18003d199  jz      loc_18003D61D
0x18003d19f  call    CreateFPU
0x18003d1a4  mov     r12, rax
0x18003d1a7  test    rax, rax
0x18003d1aa  jz      loc_18003D37E
0x18003d1b0  mov     ecx, 25Ch
0x18003d1b5  call    MemAlloc
0x18003d1ba  xor     r10d, r10d
0x18003d1bd  mov     [rsp+170h+lpMem], rax
0x18003d1c2  mov     r8, rax
0x18003d1c5  test    rax, rax
0x18003d1c8  jnz     short loc_18003D1D8
0x18003d1ca  lea     ecx, [rax+8]; dwErrCode
0x18003d1cd  call    cs:__imp_SetLastError
0x18003d1d3  jmp     loc_18003D37E
0x18003d1d8  mov     edx, 4
0x18003d1dd  mov     rcx, rdi
0x18003d1e0  lea     r9d, [rdx+7Ch]
0x18003d1e4  movups  xmm0, xmmword ptr [rcx]
0x18003d1e7  movups  xmmword ptr [rax], xmm0
0x18003d1ea  movups  xmm1, xmmword ptr [rcx+10h]
0x18003d1ee  movups  xmmword ptr [rax+10h], xmm1
0x18003d1f2  movups  xmm0, xmmword ptr [rcx+20h]
0x18003d1f6  movups  xmmword ptr [rax+20h], xmm0
0x18003d1fa  movups  xmm1, xmmword ptr [rcx+30h]
0x18003d1fe  movups  xmmword ptr [rax+30h], xmm1
0x18003d202  movups  xmm0, xmmword ptr [rcx+40h]
0x18003d206  movups  xmmword ptr [rax+40h], xmm0
0x18003d20a  movups  xmm1, xmmword ptr [rcx+50h]
0x18003d20e  movups  xmmword ptr [rax+50h], xmm1
0x18003d212  movups  xmm0, xmmword ptr [rcx+60h]
0x18003d216  movups  xmmword ptr [rax+60h], xmm0
0x18003d21a  movups  xmm1, xmmword ptr [rcx+70h]
0x18003d21e  add     rcx, r9
0x18003d221  movups  xmmword ptr [rax+70h], xmm1
0x18003d225  add     rax, r9
0x18003d228  sub     rdx, 1
0x18003d22c  jnz     short loc_18003D1E4
0x18003d22e  movups  xmm0, xmmword ptr [rcx]
0x18003d231  movups  xmmword ptr [rax], xmm0
0x18003d234  movups  xmm1, xmmword ptr [rcx+10h]
0x18003d238  movups  xmmword ptr [rax+10h], xmm1
0x18003d23c  movups  xmm0, xmmword ptr [rcx+20h]
0x18003d240  movups  xmmword ptr [rax+20h], xmm0
0x18003d244  movups  xmm1, xmmword ptr [rcx+30h]
0x18003d248  movups  xmmword ptr [rax+30h], xmm1
0x18003d24c  movups  xmm0, xmmword ptr [rcx+3Ch]
0x18003d250  mov     [r8+24Ch], rbx
0x18003d257  mov     [r8+254h], r15
0x18003d25e  movups  xmmword ptr [rax+3Ch], xmm0
0x18003d262  mov     ebx, [r8+0Ch]
0x18003d266  cmp     ebx, 2
0x18003d269  jle     loc_18003D3D9
0x18003d26f  mov     [rsp+170h+var_130], 208h
0x18003d277  lea     edi, [rdx+6]
0x18003d27a  cmp     ebx, 73524742h
0x18003d280  jz      short loc_18003D28D
0x18003d282  mov     r9d, edi
0x18003d285  cmp     ebx, 57696E20h
0x18003d28b  jnz     short loc_18003D293
0x18003d28d  mov     r9d, 5; enum COLORPROFILESUBTYPE
0x18003d293  mov     [rsp+170h+var_138], r10d; int
0x18003d298  lea     rax, [rsp+170h+var_130]
0x18003d29d  mov     qword ptr [rsp+170h+dwFlags], rax; unsigned int *
0x18003d2a2  xor     edx, edx; unsigned __int16 *
0x18003d2a4  mov     qword ptr [rsp+170h+dwCreationMode], r10; unsigned __int16 *
0x18003d2a9  xor     r8d, r8d; enum COLORPROFILETYPE
0x18003d2ac  mov     [rsp+170h+dwShareMode], ebx; unsigned int
0x18003d2b0  lea     ecx, [rdx+1]; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x18003d2b3  call    ?InternalGetDefaultColorProfile@@YAHW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGW4COLORPROFILETYPE@@W4COLORPROFILESUBTYPE@@KPEAGPEAKH@Z; InternalGetDefaultColorProfile(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,COLORPROFILETYPE,COLORPROFILESUBTYPE,ulong,ushort *,ulong *,int)
0x18003d2b8  xor     ecx, ecx
0x18003d2ba  test    eax, eax
0x18003d2bc  jz      loc_18003D379
0x18003d2c2  mov     rax, [rsp+170h+lpMem]
0x18003d2c7  add     rax, 44h ; 'D'
0x18003d2cb  jz      loc_18003D36E
0x18003d2d1  cmp     [rsp+170h+var_130], 208h
0x18003d2d9  ja      loc_18003D36E
0x18003d2df  cmp     ebx, 73524742h
0x18003d2e5  jz      short loc_18003D2EF
0x18003d2e7  cmp     ebx, 57696E20h
0x18003d2ed  jnz     short loc_18003D2F4
0x18003d2ef  mov     edi, 5
0x18003d2f4  mov     [rsp+170h+var_138], ecx; int
0x18003d2f8  xor     edx, edx; unsigned __int16 *
0x18003d2fa  lea     rcx, [rsp+170h+var_130]
0x18003d2ff  mov     r9d, edi; enum COLORPROFILESUBTYPE
0x18003d302  mov     qword ptr [rsp+170h+dwFlags], rcx; unsigned int *
0x18003d307  xor     r8d, r8d; enum COLORPROFILETYPE
0x18003d30a  mov     qword ptr [rsp+170h+dwCreationMode], rax; unsigned __int16 *
0x18003d30f  lea     ecx, [rdx+1]; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x18003d312  mov     [rsp+170h+dwShareMode], ebx; unsigned int
0x18003d316  call    ?InternalGetDefaultColorProfile@@YAHW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGW4COLORPROFILETYPE@@W4COLORPROFILESUBTYPE@@KPEAGPEAKH@Z; InternalGetDefaultColorProfile(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,COLORPROFILETYPE,COLORPROFILESUBTYPE,ulong,ushort *,ulong *,int)
0x18003d31b  xor     ecx, ecx
0x18003d31d  test    eax, eax
0x18003d31f  jz      short loc_18003D379
0x18003d321  mov     r8, [rsp+170h+lpMem]
0x18003d326  mov     ebx, 1
0x18003d32b  lea     r11, [r8+44h]
0x18003d32f  cmp     [r11], cx
0x18003d333  jz      loc_18003D44D
0x18003d339  xor     eax, eax
  ... truncated ...
```
