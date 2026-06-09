# VerifyFileSignature(_DRIVER_VALIDATION_LEVEL,ushort const *,ushort const *,_GUID *)

- ea: `0x1800260c4`
- end: `0x180026491`
- name: `?VerifyFileSignature@@YAHW4_DRIVER_VALIDATION_LEVEL@@PEBG1PEAU_GUID@@@Z`
- size: `973`
- prototype: `int __high(enum _DRIVER_VALIDATION_LEVEL, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x1800281a0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000d57c`
- `0x180025db8`
- `0x180025f6c`
- `0x1800260c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026325`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002643e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002643e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002612b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002612b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026400`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026400`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002633d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002633d`
- `CRYPT32!CertFreeCertificateContext` at `0x180026412`
- `CRYPT32!CertFreeCertificateContext` at `0x180026412`
- `WINTRUST!WinVerifyTrust` at `0x1800263e1`
- `WINTRUST!WinVerifyTrust` at `0x180026430`
- `WINTRUST!WinVerifyTrust` at `0x1800263e1`
- `WINTRUST!WinVerifyTrust` at `0x180026430`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002631b`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002635d`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002631b`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002635d`

## pseudocode

```c
_BOOL8 __fastcall VerifyFileSignature(int a1, const WCHAR *a2, __int64 a3, __int64 a4)
{
  BOOL v5; // ebx
  __int64 v7; // r15
  HANDLE FileW; // rax
  void *v10; // r12
  int v11; // esi
  int v12; // r14d
  int v13; // r14d
  bool v14; // zf
  BYTE *v15; // rax
  BYTE *v16; // r15
  int v17; // eax
  LONG v18; // eax
  signed int v19; // ebx
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD pcbHash; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+44h] [rbp-BCh] BYREF
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  int pWVTData; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v27; // [rsp+68h] [rbp-98h]
  __int64 v28; // [rsp+78h] [rbp-88h]
  int v29; // [rsp+80h] [rbp-80h]
  int *v30; // [rsp+88h] [rbp-78h]
  int v31; // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  int v33; // [rsp+A8h] [rbp-58h]
  int v34; // [rsp+ACh] [rbp-54h]
  int v35; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v36; // [rsp+C8h] [rbp-38h]
  const WCHAR *v37; // [rsp+D8h] [rbp-28h]
  void *v38; // [rsp+E0h] [rbp-20h]
  BYTE *v39; // [rsp+E8h] [rbp-18h]
  DWORD v40; // [rsp+F0h] [rbp-10h]
  _DWORD v41[268]; // [rsp+110h] [rbp+10h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+540h] [rbp+440h]

  v25 = a3;
  v5 = 0;
  v7 = a3;
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v10 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return v5;
  pcbHash = 0;
  v11 = 0;
  if ( v7 )
  {
    memset_0(&pWVTData, 0, 0x58u);
    memset_0(v41, 0, 0x450u);
    memset_0(&v35, 0, 0x48u);
    if ( CryptCATAdminCalcHashFromFileHandle(v10, &pcbHash, 0, 0) || GetLastError() == 122 )
    {
      v15 = (BYTE *)LocalAlloc(0x40u, pcbHash);
      v16 = v15;
      if ( v15 && CryptCATAdminCalcHashFromFileHandle(v10, &pcbHash, v15, 0) )
      {
        v36 = v25;
        v40 = pcbHash;
        v41[0] = 1104;
        v28 = 2;
        v29 = 2;
        v30 = &v35;
        v31 = 1;
        v34 = 1;
        v27 = v41;
        v17 = v33;
        if ( !a1 )
          v17 = 1024;
        v35 = 72;
        v33 = v17;
        v37 = a2;
        v38 = v10;
        v39 = v16;
        pWVTData = 88;
        v18 = WinVerifyTrust(0, (GUID *)a4, &pWVTData);
        v19 = v18;
        if ( v18 > 0 )
          v19 = (unsigned __int16)v18 | 0x80070000;
        v11 = v19;
        v5 = v19 >= 0;
        LocalFree(v16);
        if ( pCertContext )
          CertFreeCertificateContext(pCertContext);
        if ( v32 )
        {
          v31 = 2;
          WinVerifyTrust(0, (GUID *)a4, &pWVTData);
        }
      }
      v7 = v25;
    }
    goto LABEL_40;
  }
  v23 = 0;
  v24 = 0;
  LODWORD(v25) = 0;
  *(_DWORD *)a4 = -145692989;
  *(_DWORD *)(a4 + 4) = 298924270;
  *(_DWORD *)(a4 + 8) = -1073683067;
  *(_DWORD *)(a4 + 12) = -292175281;
  if ( a1 )
  {
    v12 = a1 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        if ( v13 != 1 )
          goto LABEL_40;
        v11 = VerifyDriverFileAndSigning(a2, FileW, &v23, (int *)&pcbHash);
        if ( v11 < 0 || !v23 && !pcbHash )
        {
          v11 = VerifyDriverFileAndTrustStoreSigning(a2, v10, 0, &v24);
          if ( v11 >= 0 && v24 )
          {
LABEL_15:
            *(_DWORD *)a4 = 11191659;
            v5 = 1;
            *(_DWORD *)(a4 + 4) = 298896708;
            *(_DWORD *)(a4 + 8) = -1073692020;
            *(_DWORD *)(a4 + 12) = -292175281;
            goto LABEL_40;
          }
          v11 = VerifyDriverFileAndTrustStoreSigning(a2, v10, 1, &v25);
          if ( v11 < 0 )
            goto LABEL_40;
          v14 = (_DWORD)v25 == 0;
LABEL_14:
          if ( v14 )
            goto LABEL_40;
          goto LABEL_15;
        }
        goto LABEL_26;
      }
      v11 = VerifyDriverFileAndSigning(a2, FileW, &v23, (int *)&pcbHash);
      if ( v11 >= 0 && (v23 || pcbHash) )
      {
LABEL_26:
        v5 = 1;
        goto LABEL_40;
      }
    }
    else
    {
      v11 = VerifyDriverFileAndSigning(a2, FileW, &v23, (int *)&pcbHash);
      if ( v11 >= 0 && v23 )
        goto LABEL_26;
    }
    v11 = VerifyDriverFileAndTrustStoreSigning(a2, v10, 0, &v24);
    if ( v11 >= 0 )
    {
      v14 = v24 == 0;
      goto LABEL_14;
    }
  }
  else
  {
    v11 = VerifyDriverFileAndSigning(a2, FileW, &v23, (int *)&pcbHash);
    if ( v11 >= 0 && v23 )
      goto LABEL_26;
  }
LABEL_40:
  CloseHandle(v10);
  if ( v11 < 0 )
  {
    LODWORD(dwCreationDisposition) = v11;
    ClassInstallerTelemetry::WriteDbgTraceError(
      "VerifyFileSignature",
      L"Error verifying driver file: %ws against catalog: %ws. Error hr: 0x%x",
      a2,
      v7,
      dwCreationDisposition);
  }
  return v5;
}

```

## disassembly

```asm
0x1800260c4  mov     [rsp-8+arg_0], rbx
0x1800260c9  push    rbp
0x1800260ca  push    rsi
0x1800260cb  push    rdi
0x1800260cc  push    r12
0x1800260ce  push    r13
0x1800260d0  push    r14
0x1800260d2  push    r15
0x1800260d4  lea     rbp, [rsp-470h]
0x1800260dc  sub     rsp, 570h
0x1800260e3  mov     rax, cs:__security_cookie
0x1800260ea  xor     rax, rsp
0x1800260ed  mov     [rbp+4A0h+var_40], rax
0x1800260f4  mov     r13, rdx
0x1800260f7  mov     [rsp+5A0h+var_550], r8
0x1800260fc  xor     ebx, ebx
0x1800260fe  mov     rdi, r9
0x180026101  mov     r15, r8
0x180026104  mov     [rsp+5A0h+hTemplateFile], rbx; hTemplateFile
0x180026109  mov     r14d, ecx
0x18002610c  mov     [rsp+5A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180026114  xor     r9d, r9d; lpSecurityAttributes
0x180026117  mov     dword ptr [rsp+5A0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002611f  lea     r8d, [rbx+1]; dwShareMode
0x180026123  mov     edx, 80000000h; dwDesiredAccess
0x180026128  mov     rcx, r13; lpFileName
0x18002612b  call    cs:__imp_CreateFileW
0x180026131  mov     r12, rax
0x180026134  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026138  jz      loc_180026465
0x18002613e  xor     ecx, ecx
0x180026140  mov     [rsp+5A0h+pcbHash], ecx
0x180026144  mov     esi, ecx
0x180026146  test    r15, r15
0x180026149  jnz     loc_1800262DD
0x18002614f  mov     [rsp+5A0h+var_55C], ecx
0x180026153  mov     [rsp+5A0h+var_558], ecx
0x180026157  mov     dword ptr [rsp+5A0h+var_550], ecx
0x18002615b  mov     dword ptr [rdi], 0F750E6C3h
0x180026161  mov     dword ptr [rdi+4], 11D138EEh
0x180026168  mov     dword ptr [rdi+8], 0C000E585h
0x18002616f  mov     dword ptr [rdi+0Ch], 0EE95C24Fh
0x180026176  test    r14d, r14d
0x180026179  jz      loc_1800262AA
0x18002617f  sub     r14d, 1
0x180026183  jz      loc_180026263
0x180026189  sub     r14d, 1
0x18002618d  jz      loc_18002623A
0x180026193  cmp     r14d, 1
0x180026197  jnz     loc_18002643B
0x18002619d  lea     r9, [rsp+5A0h+pcbHash]; int *
0x1800261a2  mov     rdx, rax; void *
0x1800261a5  lea     r8, [rsp+5A0h+var_55C]; int *
0x1800261aa  mov     rcx, r13; unsigned __int16 *
0x1800261ad  call    ?VerifyDriverFileAndSigning@@YAJPEBGPEAXPEAH2@Z; VerifyDriverFileAndSigning(ushort const *,void *,int *,int *)
0x1800261b2  mov     esi, eax
0x1800261b4  test    eax, eax
0x1800261b6  js      short loc_1800261CC
0x1800261b8  cmp     [rsp+5A0h+var_55C], ebx
0x1800261bc  jnz     loc_1800262D3
0x1800261c2  cmp     [rsp+5A0h+pcbHash], ebx
0x1800261c6  jnz     loc_1800262D3
0x1800261cc  lea     r9, [rsp+5A0h+var_558]
0x1800261d1  xor     r8d, r8d
0x1800261d4  mov     rdx, r12
0x1800261d7  mov     rcx, r13
0x1800261da  call    ?VerifyDriverFileAndTrustStoreSigning@@YAJPEBGPEAXW4_VALIDATION_TRUST_STORE@@PEAH@Z; VerifyDriverFileAndTrustStoreSigning(ushort const *,void *,_VALIDATION_TRUST_STORE,int *)
0x1800261df  mov     esi, eax
0x1800261e1  test    eax, eax
0x1800261e3  js      short loc_1800261EB
0x1800261e5  cmp     [rsp+5A0h+var_558], ebx
0x1800261e9  jnz     short loc_180026215
0x1800261eb  lea     r9, [rsp+5A0h+var_550]
0x1800261f0  mov     r8d, 1
0x1800261f6  mov     rdx, r12
0x1800261f9  mov     rcx, r13
0x1800261fc  call    ?VerifyDriverFileAndTrustStoreSigning@@YAJPEBGPEAXW4_VALIDATION_TRUST_STORE@@PEAH@Z; VerifyDriverFileAndTrustStoreSigning(ushort const *,void *,_VALIDATION_TRUST_STORE,int *)
0x180026201  mov     esi, eax
0x180026203  test    eax, eax
0x180026205  js      loc_18002643B
0x18002620b  cmp     dword ptr [rsp+5A0h+var_550], ebx
0x18002620f  jz      loc_18002643B
0x180026215  mov     dword ptr [rdi], 0AAC56Bh
0x18002621b  mov     ebx, 1
0x180026220  mov     dword ptr [rdi+4], 11D0CD44h
0x180026227  mov     dword ptr [rdi+8], 0C000C28Ch
0x18002622e  mov     dword ptr [rdi+0Ch], 0EE95C24Fh
0x180026235  jmp     loc_18002643B
0x18002623a  lea     r9, [rsp+5A0h+pcbHash]; int *
0x18002623f  mov     rdx, r12; void *
0x180026242  lea     r8, [rsp+5A0h+var_55C]; int *
0x180026247  mov     rcx, r13; unsigned __int16 *
0x18002624a  call    ?VerifyDriverFileAndSigning@@YAJPEBGPEAXPEAH2@Z; VerifyDriverFileAndSigning(ushort const *,void *,int *,int *)
0x18002624f  mov     esi, eax
0x180026251  test    eax, eax
0x180026253  js      short loc_180026284
0x180026255  cmp     [rsp+5A0h+var_55C], ebx
0x180026259  jnz     short loc_1800262D3
0x18002625b  cmp     [rsp+5A0h+pcbHash], ebx
0x18002625f  jz      short loc_180026284
0x180026261  jmp     short loc_1800262D3
0x180026263  lea     r9, [rsp+5A0h+pcbHash]; int *
0x180026268  mov     rdx, r12; void *
0x18002626b  lea     r8, [rsp+5A0h+var_55C]; int *
0x180026270  mov     rcx, r13; unsigned __int16 *
0x180026273  call    ?VerifyDriverFileAndSigning@@YAJPEBGPEAXPEAH2@Z; VerifyDriverFileAndSigning(ushort const *,void *,int *,int *)
0x180026278  mov     esi, eax
0x18002627a  test    eax, eax
0x18002627c  js      short loc_180026284
0x18002627e  cmp     [rsp+5A0h+var_55C], ebx
0x180026282  jnz     short loc_1800262D3
0x180026284  lea     r9, [rsp+5A0h+var_558]
0x180026289  xor     r8d, r8d
0x18002628c  mov     rdx, r12
0x18002628f  mov     rcx, r13
0x180026292  call    ?VerifyDriverFileAndTrustStoreSigning@@YAJPEBGPEAXW4_VALIDATION_TRUST_STORE@@PEAH@Z; VerifyDriverFileAndTrustStoreSigning(ushort const *,void *,_VALIDATION_TRUST_STORE,int *)
0x180026297  mov     esi, eax
0x180026299  test    eax, eax
0x18002629b  js      loc_18002643B
0x1800262a1  cmp     [rsp+5A0h+var_558], ebx
0x1800262a5  jmp     loc_18002620F
0x1800262aa  lea     r9, [rsp+5A0h+pcbHash]; int *
0x1800262af  mov     rdx, r12; void *
0x1800262b2  lea     r8, [rsp+5A0h+var_55C]; int *
0x1800262b7  mov     rcx, r13; unsigned __int16 *
0x1800262ba  call    ?VerifyDriverFileAndSigning@@YAJPEBGPEAXPEAH2@Z; VerifyDriverFileAndSigning(ushort const *,void *,int *,int *)
0x1800262bf  mov     esi, eax
0x1800262c1  test    eax, eax
0x1800262c3  js      loc_18002643B
0x1800262c9  cmp     [rsp+5A0h+var_55C], ebx
0x1800262cd  jz      loc_18002643B
0x1800262d3  mov     ebx, 1
0x1800262d8  jmp     loc_18002643B
0x1800262dd  xor     edx, edx; Val
0x1800262df  lea     rcx, [rsp+5A0h+pWVTData]; void *
0x1800262e4  lea     r8d, [rdx+58h]; Size
0x1800262e8  call    memset_0
0x1800262ed  xor     edx, edx; Val
0x1800262ef  lea     rcx, [rbp+4A0h+var_490]; void *
0x1800262f3  mov     r8d, 450h; Size
0x1800262f9  call    memset_0
0x1800262fe  xor     edx, edx; Val
0x180026300  lea     rcx, [rbp+4A0h+var_4E0]; void *
0x180026304  lea     r8d, [rdx+48h]; Size
0x180026308  call    memset_0
0x18002630d  xor     r9d, r9d; dwFlags
0x180026310  lea     rdx, [rsp+5A0h+pcbHash]; pcbHash
0x180026315  xor     r8d, r8d; pbHash
0x180026318  mov     rcx, r12; hFile
0x18002631b  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x180026321  test    eax, eax
0x180026323  jnz     short loc_180026334
0x180026325  call    cs:__imp_GetLastError
0x18002632b  cmp     eax, 7Ah ; 'z'
0x18002632e  jnz     loc_18002643B
0x180026334  mov     edx, [rsp+5A0h+pcbHash]; uBytes
0x180026338  mov     ecx, 40h ; '@'; uFlags
0x18002633d  call    cs:__imp_LocalAlloc
0x180026343  mov     r15, rax
0x180026346  test    rax, rax
0x180026349  jz      loc_180026436
0x18002634f  xor     r9d, r9d; dwFlags
0x180026352  lea     rdx, [rsp+5A0h+pcbHash]; pcbHash
0x180026357  mov     r8, rax; pbHash
0x18002635a  mov     rcx, r12; hFile
0x18002635d  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x180026363  test    eax, eax
0x180026365  jz      loc_180026436
0x18002636b  mov     rax, [rsp+5A0h+var_550]
0x180026370  lea     r8, [rsp+5A0h+pWVTData]; pWVTData
0x180026375  mov     [rbp+4A0h+var_4D8], rax
0x180026379  mov     ecx, 400h
0x18002637e  mov     eax, [rsp+5A0h+pcbHash]
0x180026382  test    r14d, r14d
0x180026385  mov     [rbp+4A0h+var_4B0], eax
0x180026388  mov     rdx, rdi; pgActionID
0x18002638b  mov     eax, 2
0x180026390  mov     [rbp+4A0h+var_490], 450h
0x180026397  mov     [rsp+5A0h+var_528], rax
0x18002639c  mov     [rbp+4A0h+var_520], eax
0x18002639f  lea     rax, [rbp+4A0h+var_4E0]
0x1800263a3  mov     [rbp+4A0h+var_518], rax
0x1800263a7  mov     eax, 1
0x1800263ac  mov     [rbp+4A0h+var_510], eax
0x1800263af  mov     [rbp+4A0h+var_4F4], eax
0x1800263b2  lea     rax, [rbp+4A0h+var_490]
0x1800263b6  mov     [rsp+5A0h+var_538], rax
0x1800263bb  mov     eax, [rbp+4A0h+var_4F8]
0x1800263be  cmovz   eax, ecx
0x1800263c1  mov     [rbp+4A0h+var_4E0], 48h ; 'H'
0x1800263c8  xor     ecx, ecx; hwnd
0x1800263ca  mov     [rbp+4A0h+var_4F8], eax
0x1800263cd  mov     [rbp+4A0h+var_4C8], r13
0x1800263d1  mov     [rbp+4A0h+var_4C0], r12
0x1800263d5  mov     [rbp+4A0h+var_4B8], r15
0x1800263d9  mov     [rsp+5A0h+pWVTData], 58h ; 'X'
0x1800263e1  call    cs:__imp_WinVerifyTrust
0x1800263e7  mov     ebx, eax
0x1800263e9  test    eax, eax
0x1800263eb  jle     short loc_1800263F6
0x1800263ed  movzx   ebx, ax
0x1800263f0  or      ebx, 80070000h
0x1800263f6  mov     esi, ebx
0x1800263f8  mov     rcx, r15; hMem
0x1800263fb  not     ebx
0x1800263fd  shr     ebx, 1Fh
0x180026400  call    cs:__imp_LocalFree
0x180026406  mov     rcx, [rbp+4A0h+pCertContext]; pCertContext
0x18002640d  test    rcx, rcx
0x180026410  jz      short loc_180026418
0x180026412  call    cs:__imp_CertFreeCertificateContext
0x180026418  cmp     [rbp+4A0h+var_508], 0
0x18002641d  jz      short loc_180026436
0x18002641f  lea     r8, [rsp+5A0h+pWVTData]; pWVTData
0x180026424  mov     [rbp+4A0h+var_510], 2
0x18002642b  mov     rdx, rdi; pgActionID
0x18002642e  xor     ecx, ecx; hwnd
0x180026430  call    cs:__imp_WinVerifyTrust
0x180026436  mov     r15, [rsp+5A0h+var_550]
0x18002643b  mov     rcx, r12; hObject
0x18002643e  call    cs:__imp_CloseHandle
0x180026444  test    esi, esi
0x180026446  jns     short loc_180026465
0x180026448  mov     r9, r15
0x18002644b  mov     dword ptr [rsp+5A0h+dwCreationDisposition], esi
0x18002644f  mov     r8, r13
0x180026452  lea     rdx, aErrorVerifying_0; "Error verifying driver file: %ws agains"...
0x180026459  lea     rcx, aVerifyfilesign; "VerifyFileSignature"
0x180026460  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180026465  mov     eax, ebx
0x180026467  mov     rcx, [rbp+4A0h+var_40]
0x18002646e  xor     rcx, rsp; StackCookie
0x180026471  call    __security_check_cookie
0x180026476  mov     rbx, [rsp+5A0h+arg_0]
0x18002647e  add     rsp, 570h
0x180026485  pop     r15
0x180026487  pop     r14
0x180026489  pop     r13
0x18002648b  pop     r12
0x18002648d  pop     rdi
0x18002648e  pop     rsi
0x18002648f  pop     rbp
0x180026490  retn
```
