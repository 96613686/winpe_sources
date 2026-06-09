# CSyncItemProgress::_ReportErrorToSyncMgr(SYNCMGR_EVENT_LEVEL,ushort const *,long,IOfflineFilesSyncErrorInfo *)

- ea: `0x1800409c8`
- end: `0x180040db9`
- name: `?_ReportErrorToSyncMgr@CSyncItemProgress@@AEAAJW4SYNCMGR_EVENT_LEVEL@@PEBGJPEAUIOfflineFilesSyncErrorInfo@@@Z`
- size: `1009`
- prototype: `int(CSyncItemProgress *__hidden this, enum SYNCMGR_EVENT_LEVEL, const unsigned __int16 *, int, struct IOfflineFilesSyncErrorInfo *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180040440`
- `0x180040740`

## callees

- `0x180002810`
- `0x180003c20`
- `0x180005960`
- `0x180005b70`
- `0x18001101c`
- `0x180011a54`
- `0x180011a7c`
- `0x180013d9c`
- `0x1800321b8`
- `0x180032204`
- `0x18003223c`
- `0x180032a30`
- `0x1800408c4`
- `0x1800409c8`
- `0x1800412ac`
- `0x180041340`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHLWAPI!PathCompactPathExW` at `0x180040bfc`
- `SHLWAPI!PathCompactPathExW` at `0x180040c4e`
- `SHLWAPI!PathCompactPathExW` at `0x180040bfc`
- `SHLWAPI!PathCompactPathExW` at `0x180040c4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d6b`

## pseudocode

```c
__int64 __fastcall CSyncItemProgress::_ReportErrorToSyncMgr(
        CSyncItemProgress *this,
        enum SYNCMGR_EVENT_LEVEL a2,
        WCHAR *a3,
        unsigned int a4,
        struct IOfflineFilesSyncErrorInfo *a5)
{
  int v7; // eax
  int v8; // ecx
  int v9; // ebx
  int v10; // eax
  int v11; // r8d
  int v12; // r9d
  CSyncItemProgress *v13; // rcx
  void *v14; // r15
  unsigned __int16 *v15; // rbx
  LPWSTR v16; // r13
  const WCHAR *v17; // rdi
  const WCHAR *FileName; // rax
  __int64 v19; // rcx
  __int64 v20; // r12
  const WCHAR *v21; // rdx
  LPWSTR v22; // rdi
  void *v23; // rdx
  __int64 v24; // rcx
  int v25; // edi
  void *v26; // rdx
  int v27; // edx
  int v28; // r8d
  void *v29; // rdx
  void *v30; // rdx
  void *v31; // rdx
  unsigned __int16 *v33; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v34; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR v35; // [rsp+70h] [rbp-90h] BYREF
  int v36; // [rsp+78h] [rbp-88h]
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  void *lpMem; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v39; // [rsp+90h] [rbp-70h] BYREF
  __int128 v40; // [rsp+98h] [rbp-68h] BYREF
  _WORD v41[260]; // [rsp+B0h] [rbp-50h] BYREF
  int v42; // [rsp+2B8h] [rbp+1B8h]
  const WCHAR *v43; // [rsp+2C0h] [rbp+1C0h]
  LPCWSTR pszSrc; // [rsp+2C8h] [rbp+1C8h]
  const WCHAR *v45; // [rsp+2D0h] [rbp+1D0h]
  __int64 v46; // [rsp+2D8h] [rbp+1D8h]
  __int64 v47; // [rsp+2E0h] [rbp+1E0h]
  WCHAR pszOut[80]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v35 = a3;
  v7 = ShouldSuppressError(a4);
  if ( ((unsigned __int16)a4 != 1223 || !*((_DWORD *)this + 26)) && !v7 )
  {
    pv = 0;
    v34 = 0;
    lpMem = 0;
    v39 = 0;
    v10 = ShouldTreatSyncErrorAsWarning(v8);
    v36 = v10;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
    {
      WPP_SF_SDc(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v11, v12, a4, v10 != 0 ? 89 : 78);
    }
    if ( CSyncItemProgress::_GetResultMessageText(v13, a4, v11, &v34, (unsigned __int16 **)&lpMem, &v39) )
    {
      if ( !a5
        || ((int (__fastcall *)(struct IOfflineFilesSyncErrorInfo *, LPVOID *))a5->lpVtbl->GetDescription)(a5, &pv) < 0 )
      {
LABEL_16:
        v9 = CscUtil_FormatSystemError(&v34, a4);
        if ( v9 < 0 )
        {
LABEL_44:
          CoTaskMemFree(pv);
          CscUtil_HeapFree(v34, v29);
          CscUtil_HeapFree(lpMem, v30);
          CscUtil_HeapFree(v39, v31);
          return (unsigned int)v9;
        }
        v14 = v34;
LABEL_18:
        v15 = (unsigned __int16 *)*((_QWORD *)this + 5);
        v33 = 0;
        if ( (unsigned __int16)a4 == 1223 )
        {
          v9 = CscUtil_CreateStringCopy(v15, &v33);
        }
        else
        {
          v16 = v35;
          pszSrc = v41;
          v46 = 520;
          v45 = v41;
          v47 = 520;
          v41[0] = 0;
          v43 = v41;
          v42 = 34078720;
          if ( (int)CPath::Copy((CPath *)v41, v35) >= 0 )
          {
            v17 = v43;
            if ( pszSrc != v45 )
              v17 = pszSrc;
            FileName = CscPath_FindFileName(v17);
            v15 = (unsigned __int16 *)FileName;
            if ( FileName > v17 )
              *((_WORD *)FileName - 1) = 0;
            if ( PathCompactPathExW(pszOut, FileName, 0x50u, 0) )
            {
              v19 = -1;
              do
                ++v19;
              while ( pszOut[v19] );
              v35 = 0;
              v20 = (unsigned int)(125 - v19);
              if ( (int)CscUtil_HeapAllocArray<unsigned short>(v20, &v35) >= 0 )
              {
                v21 = v17;
                v22 = v35;
                if ( PathCompactPathExW(v35, v21, v20, 0) )
                  CscUtil_FormatString(&v33, L"%1 (%2)", pszOut, v22);
                CscUtil_HeapFree(v22, v23);
              }
            }
            else if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_841bf00f62313081547796870f30ef11_Traceguids, v15);
            }
          }
          v24 = *((_QWORD *)this + 10);
          v25 = v36;
          v40 = 0;
          if ( v33 )
            v15 = v33;
          v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, unsigned __int16 *, void *, void *, unsigned __int16 *, _QWORD, __int128 *))(*(_QWORD *)v24 + 40LL))(
                 v24,
                 *((_QWORD *)this + 4),
                 3 - (unsigned int)(v36 != 0),
                 0,
                 v15,
                 v14,
                 lpMem,
                 v39,
                 0,
                 &v40);
          CscUtil_HeapFree(v33, v26);
          v33 = 0;
          if ( v9 < 0 )
          {
            if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_SSSD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v27,
                v28,
                *((_QWORD *)this + 4),
                (__int64)v16,
                (__int64)v14,
                v9);
            }
          }
          else if ( !v25 )
          {
            ++*((_DWORD *)this + 13);
          }
          CPath::~CPath((CPath *)v41);
        }
        goto LABEL_44;
      }
      v14 = pv;
    }
    else
    {
      v14 = v34;
    }
    if ( v14 )
      goto LABEL_18;
    goto LABEL_16;
  }
  v9 = 0;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_841bf00f62313081547796870f30ef11_Traceguids, a4);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800409c8  mov     [rsp-8+arg_8], rbx
0x1800409cd  push    rbp
0x1800409ce  push    rsi
0x1800409cf  push    rdi
0x1800409d0  push    r12
0x1800409d2  push    r13
0x1800409d4  push    r14
0x1800409d6  push    r15
0x1800409d8  lea     rbp, [rsp-2A0h]
0x1800409e0  sub     rsp, 3A0h
0x1800409e7  mov     rax, cs:__security_cookie
0x1800409ee  xor     rax, rsp
0x1800409f1  mov     [rbp+2D0h+var_40], rax
0x1800409f8  mov     rbx, [rbp+2D0h+arg_20]
0x1800409ff  mov     edi, r9d
0x180040a02  mov     rsi, rcx
0x180040a05  mov     [rsp+3D0h+var_360], r8
0x180040a0a  mov     ecx, edi; int
0x180040a0c  mov     r9, r8
0x180040a0f  call    ?ShouldSuppressError@@YAHJ@Z; ShouldSuppressError(long)
0x180040a14  movzx   r13d, di
0x180040a18  xor     r15d, r15d
0x180040a1b  cmp     r13d, 4C7h
0x180040a22  jnz     short loc_180040A2A
0x180040a24  cmp     [rsi+68h], r15d
0x180040a28  jnz     short loc_180040A2E
0x180040a2a  test    eax, eax
0x180040a2c  jz      short loc_180040A75
0x180040a2e  mov     ebx, r15d
0x180040a31  mov     rcx, cs:WPP_GLOBAL_Control
0x180040a38  lea     r14, WPP_GLOBAL_Control
0x180040a3f  cmp     rcx, r14
0x180040a42  jz      loc_180040D8D
0x180040a48  mov     r12d, 100000h
0x180040a4e  test    [rcx+1Ch], r12d
0x180040a52  jz      loc_180040D8D
0x180040a58  mov     rcx, [rcx+10h]
0x180040a5c  lea     r8, WPP_841bf00f62313081547796870f30ef11_Traceguids
0x180040a63  mov     edx, 12h
0x180040a68  mov     r9d, edi
0x180040a6b  call    WPP_SF_d
0x180040a70  jmp     loc_180040D8D
0x180040a75  mov     [rbp+2D0h+pv], r15
0x180040a79  mov     [rsp+3D0h+var_368], r15
0x180040a7e  mov     [rbp+2D0h+lpMem], r15
0x180040a82  mov     [rbp+2D0h+var_340], r15
0x180040a86  call    ?ShouldTreatSyncErrorAsWarning@@YAHJ@Z; ShouldTreatSyncErrorAsWarning(long)
0x180040a8b  mov     [rsp+3D0h+var_358], eax
0x180040a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180040a96  lea     r14, WPP_GLOBAL_Control
0x180040a9d  mov     r12d, 100000h
0x180040aa3  cmp     rcx, r14
0x180040aa6  jz      short loc_180040ACE
0x180040aa8  test    [rcx+1Ch], r12d
0x180040aac  jz      short loc_180040ACE
0x180040aae  mov     rcx, [rcx+10h]
0x180040ab2  mov     edx, eax
0x180040ab4  neg     edx
0x180040ab6  mov     edx, 13h
0x180040abb  sbb     al, al
0x180040abd  and     al, 0Bh
0x180040abf  add     al, 4Eh ; 'N'
0x180040ac1  mov     byte ptr [rsp+3D0h+var_3A8], al
0x180040ac5  mov     dword ptr [rsp+3D0h+var_3B0], edi
0x180040ac9  call    WPP_SF_SDc
0x180040ace  lea     rax, [rbp+2D0h+var_340]
0x180040ad2  mov     edx, edi; int
0x180040ad4  mov     [rsp+3D0h+var_3A8], rax; unsigned __int16 **
0x180040ad9  lea     r9, [rsp+3D0h+var_368]; unsigned __int16 **
0x180040ade  lea     rax, [rbp+2D0h+lpMem]
0x180040ae2  mov     [rsp+3D0h+var_3B0], rax; unsigned __int16 **
0x180040ae7  call    ?_GetResultMessageText@CSyncItemProgress@@AEAAJJHPEAPEAG00@Z; CSyncItemProgress::_GetResultMessageText(long,int,ushort * *,ushort * *,ushort * *)
0x180040aec  test    eax, eax
0x180040aee  jnz     short loc_180040AF7
0x180040af0  mov     r15, [rsp+3D0h+var_368]
0x180040af5  jmp     short loc_180040B17
0x180040af7  test    rbx, rbx
0x180040afa  jz      short loc_180040B1E
0x180040afc  mov     rax, [rbx]
0x180040aff  lea     rdx, [rbp+2D0h+pv]
0x180040b03  mov     rcx, rbx
0x180040b06  mov     rax, [rax+20h]
0x180040b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b0f  test    eax, eax
0x180040b11  js      short loc_180040B1E
0x180040b13  mov     r15, [rbp+2D0h+pv]
0x180040b17  xor     edx, edx
0x180040b19  test    r15, r15
0x180040b1c  jnz     short loc_180040B3B
0x180040b1e  mov     edx, edi; unsigned int
0x180040b20  lea     rcx, [rsp+3D0h+var_368]; unsigned __int16 **
0x180040b25  call    ?CscUtil_FormatSystemError@@YAJPEAPEAGK@Z; CscUtil_FormatSystemError(ushort * *,ulong)
0x180040b2a  mov     ebx, eax
0x180040b2c  test    eax, eax
0x180040b2e  js      loc_180040D67
0x180040b34  mov     r15, [rsp+3D0h+var_368]
0x180040b39  xor     edx, edx
0x180040b3b  mov     rbx, [rsi+28h]
0x180040b3f  mov     [rsp+3D0h+var_370], rdx
0x180040b44  cmp     r13d, 4C7h
0x180040b4b  jnz     short loc_180040B61
0x180040b4d  lea     rdx, [rsp+3D0h+var_370]; unsigned __int16 **
0x180040b52  mov     rcx, rbx; unsigned __int16 *
0x180040b55  call    ?CscUtil_CreateStringCopy@@YAJPEBGPEAPEAG@Z; CscUtil_CreateStringCopy(ushort const *,ushort * *)
0x180040b5a  mov     ebx, eax
0x180040b5c  jmp     loc_180040D67
0x180040b61  mov     r13, [rsp+3D0h+var_360]
0x180040b66  lea     rax, [rbp+2D0h+var_320]
0x180040b6a  mov     [rbp+2D0h+pszSrc], rax
0x180040b71  mov     ecx, 208h
0x180040b76  lea     rax, [rbp+2D0h+var_320]
0x180040b7a  mov     [rbp+2D0h+var_F8], rcx
0x180040b81  mov     [rbp+2D0h+var_100], rax
0x180040b88  lea     rax, [rbp+2D0h+var_320]
0x180040b8c  mov     [rbp+2D0h+var_F0], rcx
0x180040b93  lea     rcx, [rbp+2D0h+var_320]; this
0x180040b97  mov     [rbp+2D0h+var_320], dx
0x180040b9b  mov     rdx, r13; unsigned __int16 *
0x180040b9e  mov     [rbp+2D0h+var_110], rax
0x180040ba5  mov     [rbp+2D0h+var_118], 2080000h
0x180040baf  call    ?Copy@CPath@@QEAAJPEBG@Z; CPath::Copy(ushort const *)
0x180040bb4  test    eax, eax
0x180040bb6  js      loc_180040CA7
0x180040bbc  mov     rax, [rbp+2D0h+pszSrc]
0x180040bc3  cmp     rax, [rbp+2D0h+var_100]
0x180040bca  mov     rdi, [rbp+2D0h+var_110]
0x180040bd1  cmovnz  rdi, rax
0x180040bd5  mov     rcx, rdi; SourceString
0x180040bd8  call    ?CscPath_FindFileName@@YAPEBGPEBG@Z; CscPath_FindFileName(ushort const *)
0x180040bdd  mov     rbx, rax
0x180040be0  cmp     rax, rdi
0x180040be3  jbe     short loc_180040BEB
0x180040be5  xor     ecx, ecx
0x180040be7  mov     [rax-2], cx
0x180040beb  xor     r9d, r9d; dwFlags
0x180040bee  lea     rcx, [rbp+2D0h+pszOut]; pszOut
0x180040bf5  mov     rdx, rbx; pszSrc
0x180040bf8  lea     r8d, [r9+50h]; cchMax
0x180040bfc  call    cs:__imp_PathCompactPathExW
0x180040c02  xor     r10d, r10d
0x180040c05  test    eax, eax
0x180040c07  jz      short loc_180040C7D
0x180040c09  lea     rax, [rbp+2D0h+pszOut]
0x180040c10  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180040c14  inc     rcx
0x180040c17  cmp     [rax+rcx*2], r10w
0x180040c1c  jnz     short loc_180040C14
0x180040c1e  mov     eax, 7Dh ; '}'
0x180040c23  mov     [rsp+3D0h+var_360], r10
0x180040c28  sub     eax, ecx
0x180040c2a  lea     rdx, [rsp+3D0h+var_360]
0x180040c2f  mov     ecx, eax
0x180040c31  mov     r12d, eax
0x180040c34  call    ??$CscUtil_HeapAllocArray@G@@YAJ_KPEAPEAG@Z; CscUtil_HeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x180040c39  test    eax, eax
0x180040c3b  js      short loc_180040CA7
0x180040c3d  mov     rdx, rdi; pszSrc
0x180040c40  xor     r9d, r9d; dwFlags
0x180040c43  mov     rdi, [rsp+3D0h+var_360]
0x180040c48  mov     r8d, r12d; cchMax
0x180040c4b  mov     rcx, rdi; pszOut
0x180040c4e  call    cs:__imp_PathCompactPathExW
0x180040c54  test    eax, eax
0x180040c56  jz      short loc_180040C73
0x180040c58  mov     r9, rdi
0x180040c5b  lea     r8, [rbp+2D0h+pszOut]
0x180040c62  lea     rdx, a12; "%1 (%2)"
0x180040c69  lea     rcx, [rsp+3D0h+var_370]; unsigned __int16 **
0x180040c6e  call    ?CscUtil_FormatString@@YAJPEAPEAGPEBGZZ; CscUtil_FormatString(ushort * *,ushort const *,...)
0x180040c73  mov     rcx, rdi; lpMem
0x180040c76  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180040c7b  jmp     short loc_180040CA7
0x180040c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c84  cmp     rcx, r14
0x180040c87  jz      short loc_180040CA7
0x180040c89  test    [rcx+1Ch], r12d
0x180040c8d  jz      short loc_180040CA7
0x180040c8f  mov     rcx, [rcx+10h]
0x180040c93  lea     r8, WPP_841bf00f62313081547796870f30ef11_Traceguids
0x180040c9a  mov     edx, 14h
0x180040c9f  mov     r9, rbx
0x180040ca2  call    WPP_SF_S
0x180040ca7  mov     rdx, [rbp+2D0h+var_340]
0x180040cab  xorps   xmm0, xmm0
0x180040cae  mov     rcx, [rsi+50h]
0x180040cb2  mov     edi, [rsp+3D0h+var_358]
0x180040cb6  movups  [rbp+2D0h+var_338], xmm0
0x180040cba  mov     rax, [rcx]
0x180040cbd  mov     r10, [rax+28h]
0x180040cc1  mov     rax, [rsp+3D0h+var_370]
0x180040cc6  test    rax, rax
0x180040cc9  cmovnz  rbx, rax
0x180040ccd  mov     eax, edi
0x180040ccf  neg     eax
0x180040cd1  lea     rax, [rbp+2D0h+var_338]
0x180040cd5  mov     [rsp+3D0h+var_388], rax
0x180040cda  sbb     r8d, r8d
0x180040cdd  mov     [rsp+3D0h+var_390], 0
0x180040ce6  add     r8d, 3
0x180040cea  mov     [rsp+3D0h+var_398], rdx
0x180040cef  xor     r9d, r9d
0x180040cf2  mov     rdx, [rbp+2D0h+lpMem]
0x180040cf6  mov     rax, r10
0x180040cf9  mov     [rsp+3D0h+var_3A0], rdx
0x180040cfe  mov     rdx, [rsi+20h]
0x180040d02  mov     [rsp+3D0h+var_3A8], r15
0x180040d07  mov     [rsp+3D0h+var_3B0], rbx
0x180040d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d11  mov     rcx, [rsp+3D0h+var_370]; lpMem
0x180040d16  mov     ebx, eax
0x180040d18  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180040d1d  xor     eax, eax
0x180040d1f  mov     [rsp+3D0h+var_370], rax
0x180040d24  test    ebx, ebx
0x180040d26  js      short loc_180040D31
0x180040d28  test    edi, edi
0x180040d2a  jnz     short loc_180040D5E
0x180040d2c  inc     dword ptr [rsi+34h]
0x180040d2f  jmp     short loc_180040D5E
0x180040d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180040d38  cmp     rcx, r14
0x180040d3b  jz      short loc_180040D5E
0x180040d3d  test    byte ptr [rcx+1Ch], 2
0x180040d41  jz      short loc_180040D5E
0x180040d43  mov     r9, [rsi+20h]
0x180040d47  mov     rcx, [rcx+10h]
0x180040d4b  mov     dword ptr [rsp+3D0h+var_3A0], ebx
0x180040d4f  mov     [rsp+3D0h+var_3A8], r15
0x180040d54  mov     [rsp+3D0h+var_3B0], r13
0x180040d59  call    WPP_SF_SSSD
0x180040d5e  lea     rcx, [rbp+2D0h+var_320]; this
0x180040d62  call    ??1CPath@@QEAA@XZ; CPath::~CPath(void)
0x180040d67  mov     rcx, [rbp+2D0h+pv]; pv
0x180040d6b  call    cs:__imp_CoTaskMemFree
0x180040d71  mov     rcx, [rsp+3D0h+var_368]; lpMem
0x180040d76  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180040d7b  mov     rcx, [rbp+2D0h+lpMem]; lpMem
0x180040d7f  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180040d84  mov     rcx, [rbp+2D0h+var_340]; lpMem
0x180040d88  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180040d8d  mov     eax, ebx
0x180040d8f  mov     rcx, [rbp+2D0h+var_40]
0x180040d96  xor     rcx, rsp; StackCookie
0x180040d99  call    __security_check_cookie
0x180040d9e  mov     rbx, [rsp+3D0h+arg_8]
0x180040da6  add     rsp, 3A0h
0x180040dad  pop     r15
0x180040daf  pop     r14
0x180040db1  pop     r13
0x180040db3  pop     r12
0x180040db5  pop     rdi
0x180040db6  pop     rsi
0x180040db7  pop     rbp
0x180040db8  retn
```
