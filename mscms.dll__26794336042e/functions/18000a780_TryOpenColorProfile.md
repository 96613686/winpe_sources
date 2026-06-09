# TryOpenColorProfile

- ea: `0x18000a780`
- end: `0x18000b067`
- name: `TryOpenColorProfile`
- size: `2279`
- prototype: `DWORD *__fastcall(struct tagPROFILE *, struct tagPROFILE *, struct tagPROFILE *, unsigned int, unsigned int, unsigned int, char, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a740`
- `0x18001ffe0`

## callees

- `0x180006b40`
- `0x18000a780`
- `0x18000b070`
- `0x18000b490`
- `0x18000b6b0`
- `0x18000bce0`
- `0x18000be44`
- `0x18002e5f0`
- `0x18003b3cc`

## import_xrefs

- `ntdll!WinSqmIsOptedIn` at `0x18000a80b`
- `ntdll!WinSqmIsOptedIn` at `0x18000a80b`
- `ntdll!WinSqmAddToStream` at `0x18000abe9`
- `ntdll!WinSqmAddToStream` at `0x18000af7d`
- `ntdll!WinSqmAddToStream` at `0x18000afdd`
- `ntdll!WinSqmAddToStream` at `0x18000abe9`
- `ntdll!WinSqmAddToStream` at `0x18000af7d`
- `ntdll!WinSqmAddToStream` at `0x18000afdd`
- `ntdll!EtwEventWrite` at `0x18000a978`
- `ntdll!EtwEventWrite` at `0x18000ab5b`
- `ntdll!EtwEventWrite` at `0x18000ac08`
- `ntdll!EtwEventWrite` at `0x18000ac22`
- `ntdll!EtwEventWrite` at `0x18000ac44`
- `ntdll!EtwEventWrite` at `0x18000aff7`
- `ntdll!EtwEventWrite` at `0x18000b035`
- `ntdll!EtwEventWrite` at `0x18000a978`
- `ntdll!EtwEventWrite` at `0x18000ab5b`
- `ntdll!EtwEventWrite` at `0x18000ac08`
- `ntdll!EtwEventWrite` at `0x18000ac22`
- `ntdll!EtwEventWrite` at `0x18000ac44`
- `ntdll!EtwEventWrite` at `0x18000aff7`
- `ntdll!EtwEventWrite` at `0x18000b035`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ad06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b03f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ad06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b03f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b002`

## pseudocode

```c
DWORD *__fastcall TryOpenColorProfile(
        struct tagPROFILE *a1,
        struct tagPROFILE *a2,
        struct tagPROFILE *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        char a7,
        int a8)
{
  DWORD *v11; // rdi
  int v12; // esi
  unsigned int LastError; // r13d
  int IsProcessAppContainer; // eax
  int v15; // r15d
  DWORD dwType; // eax
  const OLECHAR *v17; // rdx
  unsigned int v18; // ecx
  const OLECHAR *v19; // r11
  int v20; // r10d
  const OLECHAR *v21; // rsi
  int v22; // edi
  _WORD *pProfileData; // rax
  unsigned __int64 v24; // rcx
  int v25; // r9d
  unsigned __int64 v26; // rax
  unsigned int *v27; // r8
  unsigned __int32 v28; // ecx
  __int64 v29; // rax
  __int64 v30; // rcx
  bool v31; // zf
  unsigned __int32 v32; // edx
  __int64 v33; // rcx
  unsigned __int32 v34; // edx
  void *WcsProfileFromTag; // rbx
  _WORD *v37; // rax
  unsigned __int64 v38; // rcx
  int v39; // r8d
  _WORD *v40; // rax
  unsigned __int64 v41; // rcx
  int v42; // r8d
  __int64 v43; // xmm1_8
  __int64 v44; // xmm1_8
  __int64 v45; // xmm1_8
  DWORD dwErrCode; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int32 v47; // [rsp+34h] [rbp-CCh] BYREF
  int v48; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v49; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v50; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v51; // [rsp+50h] [rbp-B0h] BYREF
  int v52; // [rsp+58h] [rbp-A8h] BYREF
  int v53; // [rsp+5Ch] [rbp-A4h] BYREF
  int v54; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v55; // [rsp+64h] [rbp-9Ch] BYREF
  struct tagPROFILE v56; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v57[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v58[2]; // [rsp+90h] [rbp-70h] BYREF
  LPVOID lpMem[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v60[2]; // [rsp+A8h] [rbp-58h] BYREF
  DWORD *v61; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v62; // [rsp+B8h] [rbp-48h]
  DWORD *v63; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v64; // [rsp+C8h] [rbp-38h]
  unsigned __int32 *v65; // [rsp+D0h] [rbp-30h]
  __int64 v66; // [rsp+D8h] [rbp-28h]
  unsigned __int32 *v67; // [rsp+E0h] [rbp-20h]
  __int64 v68; // [rsp+E8h] [rbp-18h]
  const OLECHAR *v69; // [rsp+F0h] [rbp-10h]
  int v70; // [rsp+F8h] [rbp-8h]
  int v71; // [rsp+FCh] [rbp-4h]
  DWORD *p_dwErrCode; // [rsp+100h] [rbp+0h]
  __int64 v73; // [rsp+108h] [rbp+8h]
  const OLECHAR *v74; // [rsp+110h] [rbp+10h]
  int v75; // [rsp+118h] [rbp+18h]
  int v76; // [rsp+11Ch] [rbp+1Ch]
  unsigned int *v77; // [rsp+120h] [rbp+20h]
  __int64 v78; // [rsp+128h] [rbp+28h]
  unsigned int *v79; // [rsp+130h] [rbp+30h]
  __int64 v80; // [rsp+138h] [rbp+38h]
  unsigned int *v81; // [rsp+140h] [rbp+40h]
  __int64 v82; // [rsp+148h] [rbp+48h]
  _WORD v83[8]; // [rsp+150h] [rbp+50h] BYREF
  _WORD v84[8]; // [rsp+160h] [rbp+60h] BYREF
  _WORD v85[8]; // [rsp+170h] [rbp+70h] BYREF

  v50 = a5;
  v49 = a6;
  v51 = a4;
  *(_QWORD *)v58 = 0;
  *(_QWORD *)v60 = 0;
  v11 = 0;
  memset(&v56, 0, sizeof(v56));
  v52 = 0;
  *(_OWORD *)v57 = 0;
  v53 = 0;
  *(_OWORD *)lpMem = 0;
  v54 = 0;
  v48 = 0;
  LODWORD(v61) = WinSqmIsOptedIn();
  v12 = (int)v61;
  if ( !a1 || a1->dwType - 1 > 1 )
  {
    LastError = 87;
LABEL_53:
    v15 = a8;
    goto LABEL_54;
  }
  LastError = 0;
  IsProcessAppContainer = WcsIsProcessAppContainer(&v48);
  if ( IsProcessAppContainer < 0 )
  {
    LastError = (unsigned __int16)IsProcessAppContainer;
    if ( (IsProcessAppContainer & 0x1FFF0000) != 0x70000 )
      LastError = IsProcessAppContainer;
    if ( LastError )
      goto LABEL_53;
  }
  if ( v48 == 1 && (a2 || a3) )
  {
    LastError = 2011;
    goto LABEL_53;
  }
  v15 = a8;
  if ( a8 )
  {
    dwType = a1->dwType;
    v17 = &word_1800884E0;
    v47 = -1;
    v18 = 2;
    dwErrCode = -1;
    v19 = &word_1800884E0;
    v55 = dwType;
    v20 = 2;
    v21 = &word_1800884E0;
    v22 = 2;
    if ( dwType == 1 )
    {
      if ( !a1->pProfileData )
        goto LABEL_12;
      pProfileData = a1->pProfileData;
      v24 = (unsigned __int64)a1->cbDataSize >> 1;
      if ( v24 )
      {
        while ( *pProfileData )
        {
          ++pProfileData;
          if ( !--v24 )
            goto LABEL_11;
        }
        v25 = (a1->cbDataSize >> 1) - v24;
      }
      else
      {
LABEL_11:
        v25 = 0;
      }
      if ( v24 )
      {
        v17 = (const OLECHAR *)a1->pProfileData;
        v18 = 2 * v25 + 2;
      }
      else
      {
LABEL_12:
        v18 = 2;
      }
    }
    v64 = 4;
    v65 = (unsigned __int32 *)v17;
    v63 = &v55;
    v66 = v18;
    if ( a2 )
    {
      v47 = a2->dwType;
      if ( v47 == 1 )
      {
        if ( a2->pProfileData )
        {
          v40 = a2->pProfileData;
          v41 = (unsigned __int64)a2->cbDataSize >> 1;
          if ( v41 )
          {
            while ( *v40 )
            {
              ++v40;
              if ( !--v41 )
                goto LABEL_50;
            }
            v42 = (a2->cbDataSize >> 1) - v41;
          }
          else
          {
LABEL_50:
            v42 = 0;
          }
          if ( v41 )
          {
            v19 = (const OLECHAR *)a2->pProfileData;
            v20 = 2 * v42 + 2;
          }
        }
      }
    }
    v68 = 4;
    v67 = &v47;
    v69 = v19;
    v70 = v20;
    v71 = 0;
    if ( a3 )
    {
      dwErrCode = a3->dwType;
      if ( dwErrCode == 1 )
      {
        if ( a3->pProfileData )
        {
          v37 = a3->pProfileData;
          v38 = (unsigned __int64)a3->cbDataSize >> 1;
          if ( v38 )
          {
            while ( *v37 )
            {
              ++v37;
              if ( !--v38 )
                goto LABEL_44;
            }
            v39 = (a3->cbDataSize >> 1) - v38;
          }
          else
          {
LABEL_44:
            v39 = 0;
          }
          if ( v38 )
          {
            v21 = (const OLECHAR *)a3->pProfileData;
            v22 = 2 * v39 + 2;
          }
        }
      }
    }
    p_dwErrCode = &dwErrCode;
    v76 = 0;
    v77 = &v51;
    v73 = 4;
    v79 = &v50;
    v74 = v21;
    v81 = &v49;
    v75 = v22;
    v78 = 4;
    v80 = 4;
    v82 = 4;
    EtwEventWrite(g_etwHandle, OPENING_COLOR_PROFILE, 9, &v63);
    v12 = (int)v61;
  }
  dwErrCode = 0;
  v26 = (unsigned __int64)InternalOpenColorProfile(a1, v51, v50, v49, (int *)&dwErrCode);
  v11 = (DWORD *)v26;
  if ( !v26 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 2011;
    goto LABEL_54;
  }
  if ( !dwErrCode )
  {
    if ( v48 == 1 )
      LastError = 2011;
    CloseColorProfile((HPROFILE)v26);
    v11 = 0;
    v61 = 0;
    if ( LastError )
      goto LABEL_54;
    if ( a2 && (!a2->pProfileData || !a2->cbDataSize || a2->dwType - 1 > 1) )
      LastError = 87;
    if ( !a3 || a3->pProfileData && a3->cbDataSize && a3->dwType - 1 <= 1 )
    {
      if ( LastError )
        goto LABEL_54;
      v31 = a1->dwType == 1;
      v43 = *(_QWORD *)&a1->cbDataSize;
      *(_OWORD *)&v56.dwType = *(_OWORD *)&a1->dwType;
      *(_QWORD *)&v56.cbDataSize = v43;
      if ( v31 )
      {
        LastError = SetProfileFilePath(a1->cbDataSize, a1->pProfileData, &v56.cbDataSize, &v56.pProfileData, &v52);
        if ( LastError )
          goto LABEL_54;
      }
      if ( a2 )
      {
        v31 = a2->dwType == 1;
        v44 = *(_QWORD *)&a2->cbDataSize;
        *(_OWORD *)v57 = *(_OWORD *)&a2->dwType;
        *(_QWORD *)v58 = v44;
        if ( v31 )
        {
          LastError = SetProfileFilePath(a2->cbDataSize, a2->pProfileData, v58, &v57[1], &v53);
          if ( LastError )
            goto LABEL_54;
        }
        a2 = (struct tagPROFILE *)v57;
      }
      if ( a3 )
      {
        v31 = a3->dwType == 1;
        v45 = *(_QWORD *)&a3->cbDataSize;
        *(_OWORD *)lpMem = *(_OWORD *)&a3->dwType;
        *(_QWORD *)v60 = v45;
        if ( v31 )
        {
          LastError = SetProfileFilePath(a3->cbDataSize, a3->pProfileData, v60, &lpMem[1], &v54);
          if ( LastError )
            goto LABEL_54;
        }
        a3 = (struct tagPROFILE *)lpMem;
      }
      CITEOpenColorProfile(&v56, a2, a3, a8, (__int64)&v61);
      v11 = v61;
      goto LABEL_55;
    }
    LastError = 87;
LABEL_54:
    SetLastError(LastError);
LABEL_55:
    if ( v15 )
    {
      if ( LastError )
      {
        dwErrCode = GetLastError();
        v62 = 4;
        v61 = &dwErrCode;
        EtwEventWrite(g_etwHandle, OPEN_COLOR_PROFILE_FAILED, 1, &v61);
        SetLastError(dwErrCode);
      }
      else
      {
        if ( v12 )
        {
          LODWORD(v61) = 1;
          v62 = 2;
          WinSqmAddToStream(0, 10983, 1, &v61);
        }
        EtwEventWrite(g_etwHandle, OPENED_COLOR_PROFILE, 0, 0);
      }
    }
    if ( v52 )
      MemFree(v56.pProfileData);
    if ( v53 )
      MemFree(v57[1]);
    if ( v54 )
      MemFree(lpMem[1]);
    return v11;
  }
  if ( a8 )
  {
    dwErrCode = 0;
    v47 = 0;
    v27 = *(unsigned int **)((v26 ^ 0x49434D20) + 0x38);
    dwErrCode = _byteswap_ulong(*v27);
    v63 = &dwErrCode;
    v64 = 4;
    v47 = _byteswap_ulong(v27[2]);
    v65 = &v47;
    v66 = 4;
    v28 = _byteswap_ulong(v27[3]);
    v83[4] = 0;
    v83[0] = SHIBYTE(v28);
    v83[1] = SBYTE2(v28);
    v83[2] = SBYTE1(v28);
    v83[3] = (char)v28;
    v29 = -1;
    v30 = -1;
    do
      v31 = v83[++v30] == 0;
    while ( !v31 );
    v68 = (unsigned int)(2 * v30 + 2);
    v67 = (unsigned __int32 *)v83;
    v32 = _byteswap_ulong(v27[4]);
    v84[4] = 0;
    v84[0] = SHIBYTE(v32);
    v84[1] = SBYTE2(v32);
    v84[2] = SBYTE1(v32);
    v84[3] = (char)v32;
    v33 = -1;
    do
      v31 = v84[++v33] == 0;
    while ( !v31 );
    v71 = 0;
    v70 = 2 * v33 + 2;
    v69 = v84;
    v34 = _byteswap_ulong(v27[5]);
    v85[4] = 0;
    v85[0] = SHIBYTE(v34);
    v85[1] = SBYTE2(v34);
    v85[2] = SBYTE1(v34);
    v85[3] = (char)v34;
    do
      v31 = v85[++v29] == 0;
    while ( !v31 );
    p_dwErrCode = (DWORD *)v85;
    v73 = (unsigned int)(2 * v29 + 2);
    EtwEventWrite(g_etwHandle, "#", 5, &v63);
  }
  if ( v48 || (a7 & 1) != 0 || (WcsProfileFromTag = ExtractWcsProfileFromTag(v11)) == 0 )
  {
    if ( v12 )
    {
      LODWORD(v61) = 1;
      v62 = 8;
      WinSqmAddToStream(0, 10983, 1, &v61);
    }
    if ( a8 )
      EtwEventWrite(g_etwHandle, OPENED_COLOR_PROFILE, 0, 0);
    return v11;
  }
  CloseColorProfile(v11);
  if ( v12 )
  {
    LODWORD(v61) = 1;
    v62 = 16;
    WinSqmAddToStream(0, 10983, 1, &v61);
  }
  if ( a8 )
  {
    EtwEventWrite(g_etwHandle, EXTRACTED_WCS_PROFILE, 0, 0);
    EtwEventWrite(g_etwHandle, OPENED_COLOR_PROFILE, 0, 0);
  }
  return (DWORD *)WcsProfileFromTag;
}

```

## disassembly

```asm
0x18000a780  push    rbp
0x18000a782  push    rbx
0x18000a783  push    rsi
0x18000a784  push    rdi
0x18000a785  push    r12
0x18000a787  push    r13
0x18000a789  push    r14
0x18000a78b  push    r15
0x18000a78d  lea     rbp, [rsp-98h]
0x18000a795  sub     rsp, 198h
0x18000a79c  mov     rax, cs:__security_cookie
0x18000a7a3  xor     rax, rsp
0x18000a7a6  mov     [rbp+0D0h+var_50], rax
0x18000a7ad  mov     eax, [rbp+0D0h+arg_20]
0x18000a7b3  xor     r15d, r15d
0x18000a7b6  mov     [rsp+1D0h+var_188], eax
0x18000a7ba  xorps   xmm0, xmm0
0x18000a7bd  mov     eax, [rbp+0D0h+arg_28]
0x18000a7c3  xorps   xmm1, xmm1
0x18000a7c6  mov     [rsp+1D0h+var_190], eax
0x18000a7ca  mov     r14, r8
0x18000a7cd  xor     eax, eax
0x18000a7cf  mov     [rsp+1D0h+var_180], r9d
0x18000a7d4  mov     qword ptr [rsp+1D0h+var_158], rax
0x18000a7d9  mov     r12, rdx
0x18000a7dc  mov     qword ptr [rbp+0D0h+var_140], rax
0x18000a7e0  mov     rbx, rcx
0x18000a7e3  mov     qword ptr [rbp+0D0h+var_128], rax
0x18000a7e7  mov     edi, r15d
0x18000a7ea  movups  xmmword ptr [rsp+1D0h+var_168], xmm0
0x18000a7ef  mov     [rsp+1D0h+var_178], r15d
0x18000a7f4  movups  xmmword ptr [rbp+0D0h+var_150], xmm1
0x18000a7f8  mov     [rsp+1D0h+var_174], r15d
0x18000a7fd  movups  xmmword ptr [rbp+0D0h+lpMem], xmm0
0x18000a801  mov     [rsp+1D0h+var_170], r15d
0x18000a806  mov     [rsp+1D0h+var_198], r15d
0x18000a80b  call    cs:__imp_WinSqmIsOptedIn
0x18000a811  mov     dword ptr [rbp+0D0h+var_120], eax
0x18000a814  mov     esi, eax
0x18000a816  test    rbx, rbx
0x18000a819  jz      loc_18000ACEB
0x18000a81f  mov     ecx, [rbx]
0x18000a821  dec     ecx
0x18000a823  cmp     ecx, 1
0x18000a826  ja      loc_18000ACEB
0x18000a82c  lea     rcx, [rsp+1D0h+var_198]
0x18000a831  mov     r13d, r15d
0x18000a834  call    WcsIsProcessAppContainer
0x18000a839  test    eax, eax
0x18000a83b  js      loc_18000AECB
0x18000a841  cmp     [rsp+1D0h+var_198], 1
0x18000a846  jz      loc_18000AEEB
0x18000a84c  mov     r15d, [rbp+0D0h+arg_38]
0x18000a853  test    r15d, r15d
0x18000a856  jz      loc_18000A981
0x18000a85c  mov     eax, [rbx]
0x18000a85e  lea     rdx, word_1800884E0
0x18000a865  mov     [rsp+1D0h+var_19C], 0FFFFFFFFh
0x18000a86d  mov     ecx, 2
0x18000a872  mov     [rsp+1D0h+dwErrCode], 0FFFFFFFFh
0x18000a87a  mov     r11, rdx
0x18000a87d  mov     [rsp+1D0h+var_16C], eax
0x18000a881  mov     r10d, ecx
0x18000a884  mov     rsi, rdx
0x18000a887  mov     edi, ecx
0x18000a889  cmp     eax, 1
0x18000a88c  jnz     short loc_18000A8C3
0x18000a88e  mov     r8, [rbx+8]
0x18000a892  test    r8, r8
0x18000a895  jz      short loc_18000A8C0
0x18000a897  mov     ecx, [rbx+10h]
0x18000a89a  mov     rax, r8
0x18000a89d  shr     rcx, 1
0x18000a8a0  mov     r9, rcx
0x18000a8a3  jz      short loc_18000A8B8
0x18000a8a5  cmp     word ptr [rax], 0
0x18000a8a9  jz      loc_18000AF04
0x18000a8af  add     rax, rdi
0x18000a8b2  sub     rcx, 1
0x18000a8b6  jnz     short loc_18000A8A5
0x18000a8b8  xor     r9d, r9d
0x18000a8bb  jmp     loc_18000AF07
0x18000a8c0  mov     rcx, rdi
0x18000a8c3  xor     r9d, r9d
0x18000a8c6  mov     [rbp+0D0h+var_108], 4
0x18000a8ce  mov     [rbp+0D0h+var_100], rdx
0x18000a8d2  lea     rax, [rsp+1D0h+var_16C]
0x18000a8d7  mov     [rbp+0D0h+var_110], rax
0x18000a8db  mov     dword ptr [rbp+0D0h+var_F8], ecx
0x18000a8de  mov     dword ptr [rbp+0D0h+var_F8+4], r9d
0x18000a8e2  test    r12, r12
0x18000a8e5  jnz     loc_18000AC9B
0x18000a8eb  mov     [rbp+0D0h+var_E8], 4
0x18000a8f3  lea     rax, [rsp+1D0h+var_19C]
0x18000a8f8  mov     [rbp+0D0h+var_F0], rax
0x18000a8fc  mov     [rbp+0D0h+var_E0], r11
0x18000a900  mov     [rbp+0D0h+var_D8], r10d
0x18000a904  mov     [rbp+0D0h+var_D4], r9d
0x18000a908  test    r14, r14
0x18000a90b  jnz     loc_18000AC4F
0x18000a911  mov     rcx, cs:g_etwHandle
0x18000a918  lea     rax, [rsp+1D0h+dwErrCode]
0x18000a91d  mov     [rbp+0D0h+var_D0], rax
0x18000a921  lea     rdx, OPENING_COLOR_PROFILE
0x18000a928  lea     rax, [rsp+1D0h+var_180]
0x18000a92d  mov     [rbp+0D0h+var_B4], r9d
0x18000a931  mov     [rbp+0D0h+var_B0], rax
0x18000a935  lea     r9, [rbp+0D0h+var_110]
0x18000a939  lea     rax, [rsp+1D0h+var_188]
0x18000a93e  mov     [rbp+0D0h+var_C8], 4
0x18000a946  mov     [rbp+0D0h+var_A0], rax
0x18000a94a  mov     r8d, 9
0x18000a950  lea     rax, [rsp+1D0h+var_190]
0x18000a955  mov     [rbp+0D0h+var_C0], rsi
0x18000a959  mov     [rbp+0D0h+var_90], rax
0x18000a95d  mov     [rbp+0D0h+var_B8], edi
0x18000a960  mov     [rbp+0D0h+var_A8], 4
0x18000a968  mov     [rbp+0D0h+var_98], 4
0x18000a970  mov     [rbp+0D0h+var_88], 4
0x18000a978  call    cs:__imp_EtwEventWrite
0x18000a97e  mov     esi, dword ptr [rbp+0D0h+var_120]
0x18000a981  mov     r9d, [rsp+1D0h+var_190]; unsigned int
0x18000a986  lea     rax, [rsp+1D0h+dwErrCode]
0x18000a98b  mov     r8d, [rsp+1D0h+var_188]; unsigned int
0x18000a990  mov     rcx, rbx; struct tagPROFILE *
0x18000a993  mov     edx, [rsp+1D0h+var_180]; unsigned int
0x18000a997  mov     [rsp+1D0h+var_1B0], rax; int *
0x18000a99c  mov     [rsp+1D0h+dwErrCode], 0
0x18000a9a4  call    ?InternalOpenColorProfile@@YAPEAXPEAUtagPROFILE@@KKKPEAH@Z; InternalOpenColorProfile(tagPROFILE *,ulong,ulong,ulong,int *)
0x18000a9a9  mov     rdi, rax
0x18000a9ac  test    rax, rax
0x18000a9af  jz      loc_18000AF93
0x18000a9b5  cmp     [rsp+1D0h+dwErrCode], 0
0x18000a9ba  jz      loc_18000AE27
0x18000a9c0  test    r15d, r15d
0x18000a9c3  jz      loc_18000AB61
0x18000a9c9  xor     rax, 49434D20h
0x18000a9cf  lea     rdx, [rbp+0D0h+var_80]
0x18000a9d3  xor     r9d, r9d
0x18000a9d6  mov     [rsp+1D0h+dwErrCode], r9d
0x18000a9db  mov     [rsp+1D0h+var_19C], r9d
0x18000a9e0  mov     r8, [rax+38h]
0x18000a9e4  mov     eax, [r8]
0x18000a9e7  bswap   eax
0x18000a9e9  mov     [rsp+1D0h+dwErrCode], eax
0x18000a9ed  lea     rax, [rsp+1D0h+dwErrCode]
0x18000a9f2  mov     [rbp+0D0h+var_110], rax
0x18000a9f6  mov     [rbp+0D0h+var_108], 4
0x18000a9fe  mov     eax, [r8+8]
0x18000aa02  bswap   eax
0x18000aa04  mov     [rsp+1D0h+var_19C], eax
0x18000aa08  lea     rax, [rsp+1D0h+var_19C]
0x18000aa0d  mov     [rbp+0D0h+var_100], rax
0x18000aa11  mov     [rbp+0D0h+var_F8], 4
0x18000aa19  mov     ecx, [r8+0Ch]
0x18000aa1d  bswap   ecx
0x18000aa1f  mov     eax, ecx
0x18000aa21  mov     [rbp+0D0h+var_78], r9w
0x18000aa26  shr     eax, 18h
0x18000aa29  movsx   eax, al
0x18000aa2c  mov     [rbp+0D0h+var_80], ax
0x18000aa30  mov     eax, ecx
0x18000aa32  shr     eax, 10h
0x18000aa35  movsx   eax, al
0x18000aa38  mov     [rbp+0D0h+var_7E], ax
0x18000aa3c  mov     eax, ecx
0x18000aa3e  shr     eax, 8
0x18000aa41  movsx   eax, al
0x18000aa44  mov     [rbp+0D0h+var_7C], ax
0x18000aa48  movsx   eax, cl
0x18000aa4b  mov     [rbp+0D0h+var_7A], ax
0x18000aa4f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000aa56  mov     rcx, rax
0x18000aa59  nop     dword ptr [rax+00000000h]
0x18000aa60  cmp     [rdx+rcx*2+2], r9w
0x18000aa66  lea     rcx, [rcx+1]
0x18000aa6a  jnz     short loc_18000AA60
0x18000aa6c  lea     rcx, ds:2[rcx*2]
0x18000aa74  mov     dword ptr [rbp+0D0h+var_E8+4], r9d
0x18000aa78  mov     dword ptr [rbp+0D0h+var_E8], ecx
0x18000aa7b  lea     rdx, [rbp+0D0h+var_80]
0x18000aa7f  mov     [rbp+0D0h+var_F0], rdx
0x18000aa83  mov     edx, [r8+10h]
0x18000aa87  bswap   edx
0x18000aa89  mov     ecx, edx
0x18000aa8b  mov     [rbp+0D0h+var_68], r9w
0x18000aa90  shr     ecx, 18h
0x18000aa93  movsx   ecx, cl
0x18000aa96  mov     [rbp+0D0h+var_70], cx
0x18000aa9a  mov     ecx, edx
0x18000aa9c  shr     ecx, 10h
0x18000aa9f  movsx   ecx, cl
0x18000aaa2  mov     [rbp+0D0h+var_6E], cx
0x18000aaa6  mov     ecx, edx
0x18000aaa8  shr     ecx, 8
0x18000aaab  movsx   ecx, cl
0x18000aaae  mov     [rbp+0D0h+var_6C], cx
0x18000aab2  movsx   ecx, dl
0x18000aab5  lea     rdx, [rbp+0D0h+var_70]
0x18000aab9  mov     [rbp+0D0h+var_6A], cx
0x18000aabd  mov     rcx, rax
0x18000aac0  cmp     [rdx+rcx*2+2], r9w
0x18000aac6  lea     rcx, [rcx+1]
0x18000aaca  jnz     short loc_18000AAC0
0x18000aacc  lea     rcx, ds:2[rcx*2]
0x18000aad4  mov     [rbp+0D0h+var_D4], r9d
0x18000aad8  mov     [rbp+0D0h+var_D8], ecx
0x18000aadb  lea     rdx, [rbp+0D0h+var_70]
0x18000aadf  mov     [rbp+0D0h+var_E0], rdx
0x18000aae3  mov     edx, [r8+14h]
0x18000aae7  bswap   edx
0x18000aae9  mov     ecx, edx
0x18000aaeb  mov     [rbp+0D0h+var_58], r9w
0x18000aaf0  shr     ecx, 18h
0x18000aaf3  movsx   ecx, cl
0x18000aaf6  mov     [rbp+0D0h+var_60], cx
0x18000aafa  mov     ecx, edx
0x18000aafc  shr     ecx, 10h
0x18000aaff  movsx   ecx, cl
0x18000ab02  mov     [rbp+0D0h+var_5E], cx
0x18000ab06  mov     ecx, edx
0x18000ab08  shr     ecx, 8
0x18000ab0b  movsx   ecx, cl
0x18000ab0e  mov     [rbp+0D0h+var_5C], cx
0x18000ab12  movsx   ecx, dl
0x18000ab15  mov     [rbp+0D0h+var_5A], cx
0x18000ab19  lea     rcx, [rbp+0D0h+var_60]
0x18000ab1d  nop     dword ptr [rax]
0x18000ab20  cmp     [rcx+rax*2+2], r9w
0x18000ab26  lea     rax, [rax+1]
0x18000ab2a  jnz     short loc_18000AB20
0x18000ab2c  lea     rcx, [rbp+0D0h+var_60]
0x18000ab30  mov     dword ptr [rbp+0D0h+var_C8+4], r9d
0x18000ab34  mov     [rbp+0D0h+var_D0], rcx
0x18000ab38  lea     rax, ds:2[rax*2]
0x18000ab40  mov     rcx, cs:g_etwHandle
0x18000ab47  lea     r9, [rbp+0D0h+var_110]
0x18000ab4b  mov     r8d, 5
0x18000ab51  mov     dword ptr [rbp+0D0h+var_C8], eax
0x18000ab54  lea     rdx, ICC_PROFILE_INFO; "#"
0x18000ab5b  call    cs:__imp_EtwEventWrite
0x18000ab61  cmp     [rsp+1D0h+var_198], 0
0x18000ab66  jz      short loc_18000AB9F
0x18000ab68  test    esi, esi
0x18000ab6a  jnz     loc_18000AF58
0x18000ab70  test    r15d, r15d
0x18000ab73  jnz     loc_18000AC30
0x18000ab79  mov     rax, rdi
0x18000ab7c  mov     rcx, [rbp+0D0h+var_50]
0x18000ab83  xor     rcx, rsp; StackCookie
0x18000ab86  call    __security_check_cookie
0x18000ab8b  add     rsp, 198h
0x18000ab92  pop     r15
0x18000ab94  pop     r14
0x18000ab96  pop     r13
0x18000ab98  pop     r12
0x18000ab9a  pop     rdi
0x18000ab9b  pop     rsi
0x18000ab9c  pop     rbx
0x18000ab9d  pop     rbp
0x18000ab9e  retn
0x18000ab9f  test    [rbp+0D0h+arg_30], 1
0x18000aba6  jnz     short loc_18000AB68
0x18000aba8  mov     rcx, rdi; void *
0x18000abab  call    ?ExtractWcsProfileFromTag@@YAPEAXPEAX@Z; ExtractWcsProfileFromTag(void *)
0x18000abb0  mov     rbx, rax
0x18000abb3  test    rax, rax
0x18000abb6  jz      short loc_18000AB68
0x18000abb8  mov     rcx, rdi; hProfile
0x18000abbb  call    CloseColorProfile
0x18000abc0  test    esi, esi
0x18000abc2  jz      short loc_18000ABEF
0x18000abc4  xor     eax, eax
0x18000abc6  mov     dword ptr [rbp+0D0h+var_120], 1
0x18000abcd  mov     [rbp+0D0h+var_118], rax
0x18000abd1  lea     r9, [rbp+0D0h+var_120]
0x18000abd5  mov     edx, 2AE7h
0x18000abda  mov     dword ptr [rbp+0D0h+var_118], 10h
0x18000abe1  xor     ecx, ecx
0x18000abe3  mov     r8d, 1
0x18000abe9  call    cs:__imp_WinSqmAddToStream
0x18000abef  test    r15d, r15d
0x18000abf2  jz      short loc_18000AC28
0x18000abf4  mov     rcx, cs:g_etwHandle
0x18000abfb  lea     rdx, EXTRACTED_WCS_PROFILE
0x18000ac02  xor     r9d, r9d
0x18000ac05  xor     r8d, r8d
0x18000ac08  call    cs:__imp_EtwEventWrite
0x18000ac0e  mov     rcx, cs:g_etwHandle
0x18000ac15  lea     rdx, OPENED_COLOR_PROFILE
0x18000ac1c  xor     r9d, r9d
0x18000ac1f  xor     r8d, r8d
0x18000ac22  call    cs:__imp_EtwEventWrite
0x18000ac28  mov     rax, rbx
0x18000ac2b  jmp     loc_18000AB7C
0x18000ac30  mov     rcx, cs:g_etwHandle
0x18000ac37  lea     rdx, OPENED_COLOR_PROFILE
0x18000ac3e  xor     r9d, r9d
0x18000ac41  xor     r8d, r8d
0x18000ac44  call    cs:__imp_EtwEventWrite
  ... truncated ...
```
