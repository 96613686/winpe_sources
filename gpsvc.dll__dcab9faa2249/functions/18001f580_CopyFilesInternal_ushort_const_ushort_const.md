# CopyFilesInternal(ushort const *,ushort const *)

- ea: `0x18001f580`
- end: `0x18001fdc5`
- name: `?CopyFilesInternal@@YAKPEBG0@Z`
- size: `2117`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001f24c`
- `0x18001f580`

## callees

- `0x180003770`
- `0x18000a504`
- `0x18001f580`
- `0x18001fdd0`
- `0x180020058`
- `0x1800204d0`
- `0x180075ec0`
- `0x18007d320`
- `0x18007de08`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001f7ea`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001f81c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001f7ea`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001f81c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f68b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f8ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f9ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f68b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f8ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f9ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f78f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fb1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f78f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fb1f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001f72c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001f72c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001f780`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001f780`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001f771`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001f771`

## string_xrefs

- `0x18001fc0c`: `CopySubFolder: failed to do PathAppend %s with error: %d.`
- `0x18001fc45`: `CopySubFolder: failed to do PathAppend %s with error: %d.`
- `0x18001fcd8`: `CopySubFolder: failed to CopyFilesInternal from %s to %s with error: %d.`
- `0x18001fd11`: `CopySubFolder: failed to CopyFilesInternal from %s to %s with error: %d.`
- `0x18001f6fd`: `CopyFilesInternal: failed to CheckAndCreateSubFolders for path %s with error: %d.`
- `0x18001fb78`: `CopyFilesInternal: failed to CheckAndCreateSubFolders for path %s with error: %d.`
- `0x18001fb01`: `CopyFilesInternal: failed to do PathAppend %s with error: %d.`
- `0x18001fb44`: `CopyFilesInternal: failed to do PathAppend %s with error: %d.`
- `0x18001fbc2`: `CopyFilesInternal: failed to FindFirstFile for path: %s with error: %d.`
- `0x18001fbe8`: `CopyFilesInternal: failed to FindFirstFile for path: %s with error: %d.`
- `0x18001faba`: `CopyFilesInternal: failed to CopySubFolder %s from: %s to %s with error: %d.`
- `0x18001fd3f`: `CopyFilesInternal: failed to CopySubFolder %s from: %s to %s with error: %d.`
- `0x18001fd60`: `CopyFilesInternal: failed to CopySingleFile %s from: %s to %s with error: %d.`
- `0x18001fd9f`: `CopyFilesInternal: failed to CopySingleFile %s from: %s to %s with error: %d.`

## pseudocode

```c
__int64 __fastcall CopyFilesInternal(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  const unsigned __int16 *v4; // rdi
  WCHAR *v5; // rbx
  unsigned int v6; // r14d
  size_t v7; // rdx
  const unsigned __int16 *v8; // rax
  HRESULT v9; // eax
  size_t v10; // rdx
  HRESULT v11; // eax
  __int64 v12; // r10
  unsigned __int64 v13; // rsi
  unsigned __int16 *v14; // rdi
  int v15; // eax
  void (*v16)(unsigned int, const unsigned __int16 *, ...); // rax
  const unsigned __int16 *v17; // r8
  const wchar_t *v18; // rdx
  const unsigned __int16 *v20; // rsi
  size_t v21; // rdx
  const unsigned __int16 *v22; // rax
  HRESULT v23; // eax
  size_t v24; // rdx
  __int64 v25; // r10
  unsigned __int64 v26; // r14
  unsigned __int16 *v27; // rdi
  int v28; // eax
  size_t v29; // rdx
  const unsigned __int16 *v30; // rax
  HRESULT v31; // eax
  size_t v32; // rdx
  __int64 v33; // r10
  unsigned __int16 *v34; // r14
  void (*v35)(unsigned int, const unsigned __int16 *, ...); // rax
  const unsigned __int16 *v36; // r8
  void (*v37)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v38; // rdx
  const unsigned __int16 *v39; // r8
  const unsigned __int16 *v40; // rdx
  const unsigned __int16 *v41; // r8
  const unsigned __int16 *v42; // rdx
  PCNZWCH lpString2; // [rsp+20h] [rbp-E0h]
  int cchCount2[2]; // [rsp+28h] [rbp-D8h]
  size_t pcchLength; // [rsp+40h] [rbp-C0h] BYREF
  size_t v46; // [rsp+48h] [rbp-B8h] BYREF
  size_t v47; // [rsp+50h] [rbp-B0h] BYREF
  size_t v48; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hFindFile; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v50; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v51; // [rsp+70h] [rbp-90h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF

  v4 = 0;
  v5 = 0;
  v50 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 || !a2 )
    return 87;
  v6 = CheckAndCreateSubFolders(a2);
  if ( v6 )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_23;
    v16 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(
          2u,
          L"CopyFilesInternal: failed to CheckAndCreateSubFolders for path %s with error: %d.",
          a2,
          v6);
      goto LABEL_23;
    }
    v17 = a2;
    v18 = L"CopyFilesInternal: failed to CheckAndCreateSubFolders for path %s with error: %d.";
    goto LABEL_72;
  }
  hFindFile = 0;
  v50 = 0;
  pcchLength = 0;
  v47 = 0;
  v7 = 0x7FFFFFFF;
  v8 = a1;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v7;
  }
  while ( v7 );
  if ( v7 )
  {
    v9 = StringLengthWorkerW(L"\\*", v7, &pcchLength);
    if ( v9 < 0 )
    {
      v6 = (unsigned __int16)v9;
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&hFindFile);
    }
    else
    {
      v11 = StringLengthWorkerW(&DomainName, v10, &v47);
      if ( v11 < 0 )
      {
        v6 = (unsigned __int16)v11;
      }
      else
      {
        v13 = v12 + v47 + pcchLength + 2;
        v14 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v13);
        if ( !v14 )
        {
          v6 = 14;
          goto LABEL_63;
        }
        v15 = StringCchPrintfW(v14, v13, L"%s%s%s", a1, &DomainName, L"\\*");
        if ( !v15 )
        {
          v5 = v14;
          v50 = v14;
          v4 = 0;
          goto LABEL_18;
        }
        v6 = (unsigned __int16)v15;
        LocalFree(v14);
        v4 = 0;
      }
    }
  }
  else
  {
    v6 = 87;
  }
  if ( v6 )
  {
LABEL_63:
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_23;
    v16 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_23;
      v39 = a1;
      v40 = L"CopyFilesInternal: failed to do PathAppend %s with error: %d.";
      goto LABEL_68;
    }
    v17 = a1;
    v18 = L"CopyFilesInternal: failed to do PathAppend %s with error: %d.";
LABEL_72:
    v16(2u, v18, v17, v6);
    goto LABEL_23;
  }
LABEL_18:
  hFindFile = FindFirstFileW(v5, &FindFileData);
  if ( hFindFile == (HANDLE)-1LL )
  {
    v6 = 6;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_23;
    v16 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v17 = v5;
      v18 = L"CopyFilesInternal: failed to FindFirstFile for path: %s with error: %d.";
      goto LABEL_72;
    }
    if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
      goto LABEL_23;
    v39 = v5;
    v40 = L"CopyFilesInternal: failed to FindFirstFile for path: %s with error: %d.";
LABEL_68:
    RedirectDebugMsg(2u, v40, v39, v6);
    goto LABEL_23;
  }
  while ( (FindFileData.dwFileAttributes & 0x10) == 0 )
  {
    v6 = CopySingleFile(a1, a2, FindFileData.cFileName);
    if ( v6 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_22;
      v37 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v38 = L"CopyFilesInternal: failed to CopySingleFile %s from: %s to %s with error: %d.";
        goto LABEL_110;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v42 = L"CopyFilesInternal: failed to CopySingleFile %s from: %s to %s with error: %d.";
        goto LABEL_114;
      }
      goto LABEL_22;
    }
LABEL_21:
    if ( !FindNextFileW(hFindFile, &FindFileData) )
      goto LABEL_22;
  }
  v47 = 0;
  if ( CompareStringW(0x7Fu, 1u, FindFileData.cFileName, -1, L".", -1) == 2
    || CompareStringW(0x7Fu, 1u, FindFileData.cFileName, -1, L"..", -1) == 2 )
  {
    v6 = 0;
    goto LABEL_21;
  }
  pcchLength = 0;
  v20 = 0;
  v51 = 0;
  v46 = 0;
  v48 = 0;
  v21 = 0x7FFFFFFF;
  v22 = a1;
  do
  {
    if ( !*v22 )
      break;
    ++v22;
    --v21;
  }
  while ( v21 );
  if ( !v21 )
  {
    v6 = 87;
LABEL_40:
    if ( !v6 )
      goto LABEL_41;
    goto LABEL_51;
  }
  v23 = StringLengthWorkerW(FindFileData.cFileName, v21, &v46);
  if ( v23 < 0 || (v23 = StringLengthWorkerW(L"\\", v24, &v48), v23 < 0) )
  {
    v6 = (unsigned __int16)v23;
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&pcchLength);
    goto LABEL_40;
  }
  v26 = v25 + v48 + v46 + 2;
  v27 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v26);
  pcchLength = (size_t)v27;
  if ( !v27 )
  {
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&pcchLength);
    v4 = 0;
    v6 = 14;
LABEL_51:
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_58;
    v35 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_58;
      v41 = a1;
LABEL_90:
      RedirectDebugMsg(2u, L"CopySubFolder: failed to do PathAppend %s with error: %d.", v41, v6);
      goto LABEL_58;
    }
    v36 = a1;
LABEL_86:
    v35(2u, L"CopySubFolder: failed to do PathAppend %s with error: %d.", v36, v6);
    goto LABEL_58;
  }
  v28 = StringCchPrintfW(v27, v26, L"%s%s%s", a1, L"\\", FindFileData.cFileName);
  if ( v28 )
  {
    v6 = (unsigned __int16)v28;
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&pcchLength);
    v4 = 0;
    goto LABEL_40;
  }
  v20 = v27;
  v51 = v27;
  v4 = 0;
LABEL_41:
  pcchLength = 0;
  v47 = 0;
  v46 = 0;
  v48 = 0;
  v29 = 0x7FFFFFFF;
  v30 = a2;
  do
  {
    if ( !*v30 )
      break;
    ++v30;
    --v29;
  }
  while ( v29 );
  if ( !v29 )
  {
    v6 = 87;
LABEL_55:
    if ( !v6 )
      goto LABEL_56;
    goto LABEL_93;
  }
  v31 = StringLengthWorkerW(FindFileData.cFileName, v29, &v46);
  if ( v31 < 0 )
    goto LABEL_54;
  v31 = StringLengthWorkerW(L"\\", v32, &v48);
  if ( v31 < 0 )
    goto LABEL_54;
  v46 += v33 + v48 + 2;
  v34 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v46);
  pcchLength = (size_t)v34;
  if ( !v34 )
  {
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&pcchLength);
    v6 = 14;
LABEL_93:
    v4 = 0;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_58;
    v35 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_58;
      v41 = a2;
      goto LABEL_90;
    }
    v36 = a2;
    goto LABEL_86;
  }
  v31 = StringCchPrintfW(v34, v46, L"%s%s%s", a2, L"\\", FindFileData.cFileName);
  if ( v31 )
  {
LABEL_54:
    v6 = (unsigned __int16)v31;
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&pcchLength);
    goto LABEL_55;
  }
  v4 = v34;
  v47 = (size_t)v34;
LABEL_56:
  v6 = CopyFilesInternal(v20, v4);
  if ( v6 && *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      LODWORD(lpString2) = v6;
      g_lpDebugMsg(2u, L"CopySubFolder: failed to CopyFilesInternal from %s to %s with error: %d.", v20, v4, lpString2);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      LODWORD(lpString2) = v6;
      RedirectDebugMsg(
        2u,
        L"CopySubFolder: failed to CopyFilesInternal from %s to %s with error: %d.",
        v20,
        v4,
        lpString2);
    }
  }
  v4 = 0;
LABEL_58:
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v47);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v51);
  if ( !v6 )
    goto LABEL_21;
  if ( !*(_DWORD *)&g_dwDebugLevel )
    goto LABEL_22;
  v37 = g_lpDebugMsg;
  if ( g_lpDebugMsg )
  {
    v38 = L"CopyFilesInternal: failed to CopySubFolder %s from: %s to %s with error: %d.";
LABEL_110:
    v37(2u, v38, FindFileData.cFileName, a1, a2, v6);
    goto LABEL_22;
  }
  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
  {
    v42 = L"CopyFilesInternal: failed to CopySubFolder %s from: %s to %s with error: %d.";
LABEL_114:
    cchCount2[0] = v6;
    RedirectDebugMsg(2u, v42, FindFileData.cFileName, a1, a2, *(_QWORD *)cchCount2);
  }
LABEL_22:
  FindClose(hFindFile);
LABEL_23:
  if ( v5 )
    LocalFree(v5);
  return v6;
}

```

## disassembly

```asm
0x18001f580  mov     [rsp-8+arg_10], rbx
0x18001f585  push    rbp
0x18001f586  push    rsi
0x18001f587  push    rdi
0x18001f588  push    r12
0x18001f58a  push    r13
0x18001f58c  push    r14
0x18001f58e  push    r15
0x18001f590  lea     rbp, [rsp-1E0h]
0x18001f598  sub     rsp, 2E0h
0x18001f59f  mov     rax, cs:__security_cookie
0x18001f5a6  xor     rax, rsp
0x18001f5a9  mov     [rbp+210h+var_40], rax
0x18001f5b0  mov     r13, rdx
0x18001f5b3  mov     r12, rcx
0x18001f5b6  xor     edi, edi
0x18001f5b8  mov     ebx, edi
0x18001f5ba  mov     [rsp+310h+var_2A8], rbx
0x18001f5bf  xor     edx, edx; Val
0x18001f5c1  mov     r8d, 250h; Size
0x18001f5c7  lea     rcx, [rbp+210h+FindFileData]; void *
0x18001f5cb  call    memset_0
0x18001f5d0  test    r12, r12
0x18001f5d3  jz      loc_18001F917
0x18001f5d9  test    r13, r13
0x18001f5dc  jz      loc_18001F917
0x18001f5e2  mov     rcx, r13; unsigned __int16 *
0x18001f5e5  call    ?CheckAndCreateSubFolders@@YAKPEBG@Z; CheckAndCreateSubFolders(ushort const *)
0x18001f5ea  mov     r14d, eax
0x18001f5ed  test    eax, eax
0x18001f5ef  jnz     loc_18001F6DE
0x18001f5f5  mov     [rsp+310h+hFindFile], rdi
0x18001f5fa  mov     [rsp+310h+var_2A8], rbx
0x18001f5ff  mov     [rsp+310h+pcchLength], rdi
0x18001f604  mov     [rsp+310h+var_2C0], rdi
0x18001f609  mov     ecx, 7FFFFFFFh
0x18001f60e  mov     edx, ecx
0x18001f610  mov     rax, r12
0x18001f613  lea     r15d, [rdi+2]
0x18001f617  cmp     [rax], di
0x18001f61a  jz      short loc_18001F625
0x18001f61c  add     rax, r15
0x18001f61f  sub     rdx, 1; cchMax
0x18001f623  jnz     short loc_18001F617
0x18001f625  mov     rax, rdx
0x18001f628  sub     rcx, rdx
0x18001f62b  neg     rax
0x18001f62e  sbb     r10, r10
0x18001f631  and     r10, rcx
0x18001f634  test    rdx, rdx
0x18001f637  jz      loc_18001FB86
0x18001f63d  lea     r8, [rsp+310h+pcchLength]; pcchLength
0x18001f642  lea     rcx, asc_1800C3AB8; "\\*"
0x18001f649  call    StringLengthWorkerW
0x18001f64e  test    eax, eax
0x18001f650  js      loc_18001F70E
0x18001f656  lea     r8, [rsp+310h+var_2C0]; pcchLength
0x18001f65b  lea     rcx, DomainName; psz
0x18001f662  call    StringLengthWorkerW
0x18001f667  test    eax, eax
0x18001f669  js      loc_18001FB98
0x18001f66f  mov     rcx, [rsp+310h+var_2C0]
0x18001f674  add     rcx, r10
0x18001f677  mov     rsi, [rsp+310h+pcchLength]
0x18001f67c  add     rsi, r15
0x18001f67f  add     rsi, rcx
0x18001f682  lea     rdx, [rsi+rsi]; uBytes
0x18001f686  mov     ecx, 40h ; '@'; uFlags
0x18001f68b  call    cs:__imp_LocalAlloc
0x18001f691  mov     rdi, rax
0x18001f694  test    rax, rax
0x18001f697  jz      loc_18001FAC6
0x18001f69d  lea     rax, asc_1800C3AB8; "\\*"
0x18001f6a4  mov     qword ptr [rsp+310h+cchCount2], rax
0x18001f6a9  lea     rax, DomainName
0x18001f6b0  mov     [rsp+310h+lpString2], rax
0x18001f6b5  mov     r9, r12
0x18001f6b8  lea     r8, aSSS; "%s%s%s"
0x18001f6bf  mov     rdx, rsi; unsigned __int64
0x18001f6c2  mov     rcx, rdi; unsigned __int16 *
0x18001f6c5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f6ca  test    eax, eax
0x18001f6cc  jnz     loc_18001FB18
0x18001f6d2  mov     rbx, rdi
0x18001f6d5  mov     [rsp+310h+var_2A8], rbx
0x18001f6da  xor     edi, edi
0x18001f6dc  jmp     short loc_18001F725
0x18001f6de  cmp     cs:?g_dwDebugLevel@@3KA, edi; ulong g_dwDebugLevel
0x18001f6e4  jz      loc_18001F787
0x18001f6ea  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001f6f1  test    rax, rax
0x18001f6f4  jz      loc_18001FB5B
0x18001f6fa  mov     r8, r13
0x18001f6fd  lea     rdx, aCopyfilesinter_1; "CopyFilesInternal: failed to CheckAndCr"...
0x18001f704  mov     ecx, 2
0x18001f709  jmp     loc_18001FB4E
0x18001f70e  movzx   r14d, ax
0x18001f712  lea     rcx, [rsp+310h+hFindFile]
0x18001f717  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18001f71c  test    r14d, r14d
0x18001f71f  jnz     loc_18001FACC
0x18001f725  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x18001f729  mov     rcx, rbx; lpFileName
0x18001f72c  call    cs:__imp_FindFirstFileW
0x18001f732  mov     [rsp+310h+hFindFile], rax
0x18001f737  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001f73b  jz      loc_18001FBA1
0x18001f741  lea     r14, asc_1800C3A8C; "\\"
0x18001f748  test    byte ptr [rbp+210h+FindFileData.dwFileAttributes], 10h
0x18001f74c  jnz     short loc_18001F7C2
0x18001f74e  lea     r8, [rbp+210h+FindFileData.cFileName]; unsigned __int16 *
0x18001f752  mov     rdx, r13; unsigned __int16 *
0x18001f755  mov     rcx, r12; unsigned __int16 *
0x18001f758  call    ?CopySingleFile@@YAKPEBG00@Z; CopySingleFile(ushort const *,ushort const *,ushort const *)
0x18001f75d  mov     r14d, eax
0x18001f760  test    eax, eax
0x18001f762  jnz     loc_18001FD48
0x18001f768  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x18001f76c  mov     rcx, [rsp+310h+hFindFile]; hFindFile
0x18001f771  call    cs:__imp_FindNextFileW
0x18001f777  test    eax, eax
0x18001f779  jnz     short loc_18001F741
0x18001f77b  mov     rcx, [rsp+310h+hFindFile]; hFindFile
0x18001f780  call    cs:__imp_FindClose
0x18001f786  nop
0x18001f787  test    rbx, rbx
0x18001f78a  jz      short loc_18001F795
0x18001f78c  mov     rcx, rbx; hMem
0x18001f78f  call    cs:__imp_LocalFree
0x18001f795  mov     eax, r14d
0x18001f798  mov     rcx, [rbp+210h+var_40]
0x18001f79f  xor     rcx, rsp; StackCookie
0x18001f7a2  call    __security_check_cookie
0x18001f7a7  mov     rbx, [rsp+310h+arg_10]
0x18001f7af  add     rsp, 2E0h
0x18001f7b6  pop     r15
0x18001f7b8  pop     r14
0x18001f7ba  pop     r13
0x18001f7bc  pop     r12
0x18001f7be  pop     rdi
0x18001f7bf  pop     rsi
0x18001f7c0  pop     rbp
0x18001f7c1  retn
0x18001f7c2  mov     [rsp+310h+var_2C0], rdi
0x18001f7c7  mov     [rsp+310h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001f7cf  lea     rax, asc_1800C3A80; "."
0x18001f7d6  mov     [rsp+310h+lpString2], rax; lpString2
0x18001f7db  or      r9d, 0FFFFFFFFh; cchCount1
0x18001f7df  lea     r8, [rbp+210h+FindFileData.cFileName]; lpString1
0x18001f7e3  lea     edx, [r9+2]; dwCmpFlags
0x18001f7e7  lea     ecx, [rdx+7Eh]; Locale
0x18001f7ea  call    cs:__imp_CompareStringW
0x18001f7f0  cmp     eax, r15d
0x18001f7f3  jz      loc_18001F90F
0x18001f7f9  mov     [rsp+310h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001f801  lea     rax, asc_1800C3A84; ".."
0x18001f808  mov     [rsp+310h+lpString2], rax; lpString2
0x18001f80d  or      r9d, 0FFFFFFFFh; cchCount1
0x18001f811  lea     r8, [rbp+210h+FindFileData.cFileName]; lpString1
0x18001f815  lea     edx, [r9+2]; dwCmpFlags
0x18001f819  lea     ecx, [rdx+7Eh]; Locale
0x18001f81c  call    cs:__imp_CompareStringW
0x18001f822  cmp     eax, r15d
0x18001f825  jz      loc_18001F90F
0x18001f82b  mov     [rsp+310h+pcchLength], rdi
0x18001f830  mov     rsi, rdi
0x18001f833  mov     [rsp+310h+var_2A0], rdi
0x18001f838  mov     [rsp+310h+var_2C8], rdi
0x18001f83d  mov     [rsp+310h+var_2B8], rdi
0x18001f842  mov     ecx, 7FFFFFFFh
0x18001f847  mov     edx, ecx
0x18001f849  mov     rax, r12
0x18001f84c  cmp     [rax], di
0x18001f84f  jz      short loc_18001F85A
0x18001f851  add     rax, r15
0x18001f854  sub     rdx, 1; cchMax
0x18001f858  jnz     short loc_18001F84C
0x18001f85a  mov     rax, rdx
0x18001f85d  sub     rcx, rdx
0x18001f860  neg     rax
0x18001f863  sbb     r10, r10
0x18001f866  and     r10, rcx
0x18001f869  test    rdx, rdx
0x18001f86c  jz      loc_18001FBF4
0x18001f872  lea     r8, [rsp+310h+var_2C8]; pcchLength
0x18001f877  lea     rcx, [rbp+210h+FindFileData.cFileName]; psz
0x18001f87b  call    StringLengthWorkerW
0x18001f880  test    eax, eax
0x18001f882  js      loc_18001F921
0x18001f888  lea     r8, [rsp+310h+var_2B8]; pcchLength
0x18001f88d  mov     rcx, r14; psz
0x18001f890  call    StringLengthWorkerW
0x18001f895  test    eax, eax
0x18001f897  js      loc_18001F921
0x18001f89d  mov     rcx, [rsp+310h+var_2B8]
0x18001f8a2  add     rcx, r10
0x18001f8a5  mov     r14, [rsp+310h+var_2C8]
0x18001f8aa  add     r14, 2
0x18001f8ae  add     r14, rcx
0x18001f8b1  lea     rdx, [r14+r14]; uBytes
0x18001f8b5  mov     ecx, 40h ; '@'; uFlags
0x18001f8ba  call    cs:__imp_LocalAlloc
0x18001f8c0  mov     rdi, rax
0x18001f8c3  mov     [rsp+310h+pcchLength], rax
0x18001f8c8  test    rax, rax
0x18001f8cb  jz      loc_18001FA1F
0x18001f8d1  lea     rax, [rbp+210h+FindFileData.cFileName]
0x18001f8d5  mov     qword ptr [rsp+310h+cchCount2], rax
0x18001f8da  lea     rax, asc_1800C3A8C; "\\"
0x18001f8e1  mov     [rsp+310h+lpString2], rax
0x18001f8e6  mov     r9, r12
0x18001f8e9  lea     r8, aSSS; "%s%s%s"
0x18001f8f0  mov     rdx, r14; unsigned __int64
0x18001f8f3  mov     rcx, rdi; unsigned __int16 *
0x18001f8f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f8fb  test    eax, eax
0x18001f8fd  jnz     loc_18001FB2C
0x18001f903  mov     rsi, rdi
0x18001f906  mov     [rsp+310h+var_2A0], rdi
0x18001f90b  xor     edi, edi
0x18001f90d  jmp     short loc_18001F938
0x18001f90f  mov     r14d, edi
0x18001f912  jmp     loc_18001F768
0x18001f917  mov     eax, 57h ; 'W'
0x18001f91c  jmp     loc_18001F798
0x18001f921  movzx   r14d, ax
0x18001f925  lea     rcx, [rsp+310h+pcchLength]
0x18001f92a  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18001f92f  test    r14d, r14d
0x18001f932  jnz     loc_18001FA2F
0x18001f938  mov     [rsp+310h+pcchLength], rdi
0x18001f93d  mov     [rsp+310h+var_2C0], rdi
0x18001f942  xor     r14d, r14d
0x18001f945  mov     [rsp+310h+var_2C8], r14
0x18001f94a  mov     [rsp+310h+var_2B8], r14
0x18001f94f  mov     ecx, 7FFFFFFFh
0x18001f954  mov     edx, ecx
0x18001f956  mov     rax, r13
0x18001f959  cmp     [rax], r14w
0x18001f95d  jz      short loc_18001F968
0x18001f95f  add     rax, r15
0x18001f962  sub     rdx, 1; cchMax
0x18001f966  jnz     short loc_18001F959
0x18001f968  mov     rax, rdx
0x18001f96b  sub     rcx, rdx
0x18001f96e  neg     rax
0x18001f971  sbb     r10, r10
0x18001f974  and     r10, rcx
0x18001f977  test    rdx, rdx
0x18001f97a  jz      loc_18001FC59
0x18001f980  lea     r8, [rsp+310h+var_2C8]; pcchLength
0x18001f985  lea     rcx, [rbp+210h+FindFileData.cFileName]; psz
0x18001f989  call    StringLengthWorkerW
0x18001f98e  test    eax, eax
0x18001f990  js      loc_18001FA4F
0x18001f996  lea     r8, [rsp+310h+var_2B8]; pcchLength
0x18001f99b  lea     rcx, asc_1800C3A8C; "\\"
0x18001f9a2  call    StringLengthWorkerW
0x18001f9a7  test    eax, eax
0x18001f9a9  js      loc_18001FA4F
0x18001f9af  mov     rax, [rsp+310h+var_2B8]
0x18001f9b4  add     rax, 2
0x18001f9b8  add     rax, [rsp+310h+var_2C8]
0x18001f9bd  add     rax, r10
0x18001f9c0  mov     [rsp+310h+var_2C8], rax
0x18001f9c5  lea     rdx, [rax+rax]; uBytes
0x18001f9c9  mov     ecx, 40h ; '@'; uFlags
0x18001f9ce  call    cs:__imp_LocalAlloc
0x18001f9d4  mov     r14, rax
0x18001f9d7  mov     [rsp+310h+pcchLength], rax
0x18001f9dc  test    rax, rax
0x18001f9df  jz      loc_18001FC6B
0x18001f9e5  lea     rax, [rbp+210h+FindFileData.cFileName]
0x18001f9e9  mov     qword ptr [rsp+310h+cchCount2], rax
0x18001f9ee  lea     rax, asc_1800C3A8C; "\\"
0x18001f9f5  mov     [rsp+310h+lpString2], rax
0x18001f9fa  mov     r9, r13
0x18001f9fd  lea     r8, aSSS; "%s%s%s"
0x18001fa04  mov     rdx, [rsp+310h+var_2C8]; unsigned __int64
0x18001fa09  mov     rcx, r14; unsigned __int16 *
0x18001fa0c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001fa11  test    eax, eax
0x18001fa13  jnz     short loc_18001FA4F
0x18001fa15  mov     rdi, r14
0x18001fa18  mov     [rsp+310h+var_2C0], r14
0x18001fa1d  jmp     short loc_18001FA66
0x18001fa1f  lea     rcx, [rsp+310h+pcchLength]
0x18001fa24  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18001fa29  xor     edi, edi
0x18001fa2b  lea     r14d, [rdi+0Eh]
0x18001fa2f  cmp     cs:?g_dwDebugLevel@@3KA, edi; ulong g_dwDebugLevel
0x18001fa35  jz      short loc_18001FA80
0x18001fa37  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001fa3e  test    rax, rax
0x18001fa41  jz      loc_18001FC20
0x18001fa47  mov     r8, r12
0x18001fa4a  jmp     loc_18001FC09
0x18001fa4f  movzx   r14d, ax
0x18001fa53  lea     rcx, [rsp+310h+pcchLength]
0x18001fa58  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
  ... truncated ...
```
