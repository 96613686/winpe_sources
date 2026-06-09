# CDefragEngine::_GetVolumeDescription(ushort *,CBsString *,CBsString *,CBsString *,CBsString *,int *,int *,int *)

- ea: `0x180019b08`
- end: `0x18001a114`
- name: `?_GetVolumeDescription@CDefragEngine@@AEAAJPEAGPEAVCBsString@@111PEAH22@Z`
- size: `1548`
- prototype: `__int64 __fastcall(CDefragEngine *this, unsigned __int16 *, struct CBsString *, struct CBsString *, struct CBsString *, struct CBsString *, int *, int *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800136d0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180013520`
- `0x1800156a0`
- `0x18001913c`
- `0x180019228`
- `0x180019b08`
- `0x18001a11c`
- `0x18001a630`
- `0x1800244ac`
- `0x180067b0a`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180019d07`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180019d07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019eb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019eb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f18`
- `ntdll!RtlSetThreadErrorMode` at `0x180019b9a`
- `ntdll!RtlSetThreadErrorMode` at `0x180019be6`
- `ntdll!RtlSetThreadErrorMode` at `0x180019b9a`
- `ntdll!RtlSetThreadErrorMode` at `0x180019be6`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180019dd6`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180019dd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019cab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019d95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019cab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019d95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019bd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019bdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019c9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019d86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019bd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019bdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019c9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019d86`

## pseudocode

```c
__int64 __fastcall CDefragEngine::_GetVolumeDescription(
        CDefragEngine *this,
        unsigned __int16 *a2,
        struct CBsString *a3,
        struct CBsString *a4,
        struct CBsString *a5,
        struct CBsString *a6,
        int *a7,
        int *a8,
        int *a9)
{
  _WORD *v12; // r13
  struct CBsString *v13; // rsi
  struct CBsString *v14; // r15
  unsigned int v15; // eax
  __int16 v16; // ax
  void *v17; // rax
  unsigned int v18; // ebx
  int *v20; // rdx
  int *v21; // rcx
  __int64 v22; // rdi
  __int16 v23; // ax
  unsigned int v24; // ecx
  DWORD v25; // r14d
  const unsigned __int16 *v26; // rdi
  BOOL VolumePathNamesForVolumeNameW; // eax
  int v28; // r14d
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  const unsigned __int16 *v38; // rdi
  __int16 v39; // r9
  unsigned __int16 v40; // dx
  unsigned __int16 v41; // dx
  __int64 v42; // rax
  DWORD MaximumComponentLength; // [rsp+40h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-49h]
  int LastFailureAsHRESULT; // [rsp+50h] [rbp-41h] BYREF
  __int16 v46; // [rsp+54h] [rbp-3Dh]
  __int16 v47; // [rsp+56h] [rbp-3Bh]
  CDefragEngine *cchReturnLength; // [rsp+E0h] [rbp+4Fh] BYREF
  LPCWSTR lpszVolumeName; // [rsp+E8h] [rbp+57h]
  ULONG OldMode; // [rsp+F0h] [rbp+5Fh] BYREF
  DWORD FileSystemFlags; // [rsp+F8h] [rbp+67h] BYREF

  lpszVolumeName = a2;
  cchReturnLength = this;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CDefragEngine::_GetVolumeDescription",
    2999,
    1);
  pv = 0;
  v12 = 0;
  LODWORD(cchReturnLength) = 0;
  FileSystemFlags = 0;
  MaximumComponentLength = 0;
  OldMode = 0;
  if ( a3 )
    CBsString::Empty(a3);
  if ( a4 )
    CBsString::Empty(a4);
  v13 = a5;
  if ( a5 )
    CBsString::Empty(a5);
  v14 = a6;
  if ( a6 )
    CBsString::Empty(a6);
  v15 = RtlSetThreadErrorMode(0x10u, &OldMode);
  LastFailureAsHRESULT = HRESULTFromNTSTATUS(v15);
  v16 = 3016;
  if ( LastFailureAsHRESULT >= 0 )
  {
    v46 = 3016;
    v16 = 3018;
    if ( !a3 )
      goto LABEL_11;
    v46 = 3018;
    v16 = 3019;
    if ( !a4 )
      goto LABEL_11;
    v46 = 3019;
    v16 = 3020;
    if ( !v13 )
      goto LABEL_11;
    v46 = 3020;
    v20 = a7;
    v16 = 3021;
    if ( !a7 )
      goto LABEL_11;
    v46 = 3021;
    v16 = 3022;
    if ( a8 && (v46 = 3022, v16 = 3023, v14) && (v46 = 3023, v21 = a9, v16 = 3024, a9) )
    {
      LastFailureAsHRESULT = 0;
      *a8 = 0;
      *v20 = 0;
      *v21 = 0;
      LODWORD(v22) = 32;
      while ( 1 )
      {
        v46 = v16;
        v22 = SxScaledGrowth(v22);
        CoTaskMemFree(v12);
        v12 = CoTaskMemAlloc(2LL * (unsigned int)(v22 + 1));
        if ( !v12 )
        {
          LastFailureAsHRESULT = -2147024882;
          v23 = 3036;
          goto LABEL_23;
        }
        LastFailureAsHRESULT = 0;
        v46 = 3036;
        if ( GetVolumeInformationW(a2, v12, v22, 0, &MaximumComponentLength, &FileSystemFlags, 0, 0) )
          break;
        if ( GetLastError() != 234 )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v31, v30, v32, v33);
          v23 = 3043;
          goto LABEL_23;
        }
        LastFailureAsHRESULT = 0;
        v16 = 3043;
      }
      v12[v22] = 0;
      if ( !*v12 )
      {
LABEL_30:
        v24 = 64;
        LODWORD(cchReturnLength) = 64;
        while ( 1 )
        {
          v25 = SxScaledGrowth(v24);
          CoTaskMemFree(pv);
          v17 = CoTaskMemAlloc(2LL * v25);
          pv = v17;
          if ( !v17 )
          {
            LastFailureAsHRESULT = -2147024882;
            v47 = 3060;
            goto LABEL_13;
          }
          LastFailureAsHRESULT = 0;
          v46 = 3060;
          memset_0(pv, 0, 2LL * v25);
          v26 = lpszVolumeName;
          VolumePathNamesForVolumeNameW = GetVolumePathNamesForVolumeNameW(
                                            lpszVolumeName,
                                            (LPWCH)pv,
                                            v25,
                                            (PDWORD)&cchReturnLength);
          v28 = 0;
          if ( VolumePathNamesForVolumeNameW )
            break;
          if ( GetLastError() != 234 )
          {
            LastFailureAsHRESULT = GetLastFailureAsHRESULT(v35, v34, v36, v37);
            v23 = 3068;
            goto LABEL_23;
          }
          LastFailureAsHRESULT = 0;
          v46 = 3068;
          v24 = (unsigned int)cchReturnLength;
        }
        v29 = -1;
        do
          ++v29;
        while ( *((_WORD *)pv + v29) );
        if ( v29 )
        {
          if ( *v12 )
          {
            LastFailureAsHRESULT = CBsString::Append(a3, L" ");
            v23 = 3078;
            if ( LastFailureAsHRESULT < 0 )
              goto LABEL_23;
            v46 = 3078;
          }
          LastFailureAsHRESULT = CBsString::Append(a3, L"(");
          v23 = 3080;
          if ( LastFailureAsHRESULT < 0 )
            goto LABEL_23;
          v46 = 3080;
          v38 = (const unsigned __int16 *)pv;
          v39 = 0;
          while ( *v38 != v39 )
          {
            *a7 = 1;
            if ( !v28 )
            {
              LastFailureAsHRESULT = CBsString::Set(v14, v38);
              v23 = 3089;
              if ( LastFailureAsHRESULT < 0 )
                goto LABEL_23;
              v46 = 3089;
              v28 = 1;
            }
            if ( v38 != pv )
            {
              LastFailureAsHRESULT = CBsString::Append(a3, L", ");
              v23 = 3095;
              if ( LastFailureAsHRESULT < 0 )
                goto LABEL_23;
              v46 = 3095;
              LastFailureAsHRESULT = CBsString::Append(v13, L", ");
              v23 = 3096;
              if ( LastFailureAsHRESULT < 0 )
                goto LABEL_23;
              v46 = 3096;
            }
            LastFailureAsHRESULT = CBsString::Append(a3, v38);
            v23 = 3098;
            if ( LastFailureAsHRESULT < 0 )
              goto LABEL_23;
            v46 = 3098;
            LastFailureAsHRESULT = CBsString::Append(v13, v38);
            v23 = 3099;
            if ( LastFailureAsHRESULT < 0 )
              goto LABEL_23;
            v46 = 3099;
            CBsString::UnTrailing(a3, v40);
            CBsString::UnTrailing(v13, v41);
            v42 = -1;
            do
              ++v42;
            while ( v38[v42] != v39 );
            v38 += v42 + 1;
          }
          LastFailureAsHRESULT = CBsString::Append(a3, L")");
          v23 = 3104;
          if ( LastFailureAsHRESULT < 0 )
            goto LABEL_23;
          v26 = lpszVolumeName;
        }
        else
        {
          if ( !*v12 )
          {
LABEL_37:
            if ( !*((_DWORD *)a3 + 2) )
            {
              LastFailureAsHRESULT = CBsString::Set(a3, v26);
              v23 = 3119;
              if ( LastFailureAsHRESULT < 0 )
                goto LABEL_23;
              v46 = 3119;
            }
            if ( *((_DWORD *)v13 + 2) )
              goto LABEL_39;
            *a8 = 1;
            LastFailureAsHRESULT = CBsString::Set(v13, v26);
            v23 = 3125;
            if ( LastFailureAsHRESULT >= 0 )
            {
              v46 = 3125;
LABEL_39:
              if ( !*((_DWORD *)v14 + 2) )
              {
                LastFailureAsHRESULT = CBsString::Set(v14, v26);
                v23 = 3130;
                if ( LastFailureAsHRESULT < 0 )
                  goto LABEL_23;
                v46 = 3130;
              }
              if ( !*((_DWORD *)a4 + 2) )
              {
                *a9 = 0;
                LastFailureAsHRESULT = CBsString::Set(a4, v26);
                v23 = 3136;
                if ( LastFailureAsHRESULT < 0 )
                  goto LABEL_23;
                v46 = 3136;
              }
              goto LABEL_24;
            }
LABEL_23:
            v47 = v23;
LABEL_24:
            v17 = pv;
            goto LABEL_13;
          }
          LastFailureAsHRESULT = CBsString::Append(v13, v12);
          v23 = 3112;
          if ( LastFailureAsHRESULT < 0 )
            goto LABEL_23;
        }
        v46 = v23;
        goto LABEL_37;
      }
      LastFailureAsHRESULT = CBsString::Append(a3, v12);
      v16 = 3049;
      if ( LastFailureAsHRESULT >= 0 )
      {
        v46 = 3049;
        LastFailureAsHRESULT = CBsString::Append(a4, v12);
        v16 = 3050;
        if ( LastFailureAsHRESULT >= 0 )
        {
          v46 = 3050;
          *a9 = 1;
          goto LABEL_30;
        }
      }
    }
    else
    {
LABEL_11:
      LastFailureAsHRESULT = -2147024809;
    }
  }
  v47 = v16;
  v17 = 0;
LABEL_13:
  CoTaskMemFree(v17);
  CoTaskMemFree(v12);
  RtlSetThreadErrorMode(OldMode, 0);
  v18 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v18;
}

```

## disassembly

```asm
0x180019b08  mov     [rsp-8+lpszVolumeName], rdx
0x180019b0d  mov     [rsp-8+cchReturnLength], rcx
0x180019b12  push    rbp
0x180019b13  push    rbx
0x180019b14  push    rsi
0x180019b15  push    rdi
0x180019b16  push    r12
0x180019b18  push    r13
0x180019b1a  push    r14
0x180019b1c  push    r15
0x180019b1e  lea     rbp, [rsp-7]
0x180019b23  sub     rsp, 98h
0x180019b2a  mov     r12, r9
0x180019b2d  mov     rbx, r8
0x180019b30  mov     r14, rdx
0x180019b33  mov     r9d, 1; unsigned __int16
0x180019b39  mov     r8d, 0BB7h; unsigned __int16
0x180019b3f  lea     rdx, aCdefragengineG_4; "CDefragEngine::_GetVolumeDescription"
0x180019b46  lea     rcx, [rbp+3Fh+var_80]; this
0x180019b4a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180019b4f  nop
0x180019b50  xor     edi, edi
0x180019b52  mov     [rbp+3Fh+pv], rdi
0x180019b56  mov     r13d, edi
0x180019b59  mov     dword ptr [rbp+3Fh+cchReturnLength], edi
0x180019b5c  mov     [rbp+3Fh+FileSystemFlags], edi
0x180019b5f  mov     [rbp+3Fh+MaximumComponentLength], edi
0x180019b62  mov     [rbp+3Fh+OldMode], edi
0x180019b65  test    rbx, rbx
0x180019b68  jnz     loc_180019EE4
0x180019b6e  test    r12, r12
0x180019b71  jnz     loc_180019EF1
0x180019b77  mov     rsi, [rbp+3Fh+arg_20]
0x180019b7b  test    rsi, rsi
0x180019b7e  jnz     loc_180019EFE
0x180019b84  mov     r15, [rbp+3Fh+arg_28]
0x180019b88  test    r15, r15
0x180019b8b  jnz     loc_180019F0B
0x180019b91  lea     rdx, [rbp+3Fh+OldMode]; OldMode
0x180019b95  mov     ecx, 10h; NewMode
0x180019b9a  call    cs:__imp_RtlSetThreadErrorMode
0x180019ba0  mov     ecx, eax
0x180019ba2  call    HRESULTFromNTSTATUS
0x180019ba7  mov     [rbp+3Fh+var_80], eax
0x180019baa  test    eax, eax
0x180019bac  mov     eax, 0BC8h
0x180019bb1  js      short loc_180019BC8
0x180019bb3  mov     [rbp+3Fh+var_7C], ax
0x180019bb7  mov     eax, 0BCAh
0x180019bbc  test    rbx, rbx
0x180019bbf  jnz     short loc_180019C0E
0x180019bc1  mov     [rbp+3Fh+var_80], 80070057h
0x180019bc8  mov     [rbp+3Fh+var_7A], ax
0x180019bcc  mov     rax, rdi
0x180019bcf  mov     rcx, rax; pv
0x180019bd2  call    cs:__imp_CoTaskMemFree
0x180019bd8  mov     rcx, r13; pv
0x180019bdb  call    cs:__imp_CoTaskMemFree
0x180019be1  xor     edx, edx; OldMode
0x180019be3  mov     ecx, [rbp+3Fh+OldMode]; NewMode
0x180019be6  call    cs:__imp_RtlSetThreadErrorMode
0x180019bec  mov     ebx, [rbp+3Fh+var_80]
0x180019bef  lea     rcx, [rbp+3Fh+var_80]; this
0x180019bf3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180019bf8  mov     eax, ebx
0x180019bfa  add     rsp, 98h
0x180019c01  pop     r15
0x180019c03  pop     r14
0x180019c05  pop     r13
0x180019c07  pop     r12
0x180019c09  pop     rdi
0x180019c0a  pop     rsi
0x180019c0b  pop     rbx
0x180019c0c  pop     rbp
0x180019c0d  retn
0x180019c0e  mov     [rbp+3Fh+var_7C], ax
0x180019c12  mov     eax, 0BCBh
0x180019c17  test    r12, r12
0x180019c1a  jz      short loc_180019BC1
0x180019c1c  mov     [rbp+3Fh+var_7C], ax
0x180019c20  mov     eax, 0BCCh
0x180019c25  test    rsi, rsi
0x180019c28  jz      short loc_180019BC1
0x180019c2a  mov     [rbp+3Fh+var_7C], ax
0x180019c2e  mov     rdx, [rbp+3Fh+arg_30]
0x180019c32  mov     eax, 0BCDh
0x180019c37  test    rdx, rdx
0x180019c3a  jz      short loc_180019BC1
0x180019c3c  mov     [rbp+3Fh+var_7C], ax
0x180019c40  mov     r8, [rbp+3Fh+arg_38]
0x180019c47  mov     eax, 0BCEh
0x180019c4c  test    r8, r8
0x180019c4f  jz      loc_180019BC1
0x180019c55  mov     [rbp+3Fh+var_7C], ax
0x180019c59  mov     eax, 0BCFh
0x180019c5e  test    r15, r15
0x180019c61  jz      loc_180019BC1
0x180019c67  mov     [rbp+3Fh+var_7C], ax
0x180019c6b  mov     rcx, [rbp+3Fh+arg_40]
0x180019c72  mov     eax, 0BD0h
0x180019c77  test    rcx, rcx
0x180019c7a  jz      loc_180019BC1
0x180019c80  mov     [rbp+3Fh+var_80], edi
0x180019c83  mov     [r8], edi
0x180019c86  mov     [rdx], edi
0x180019c88  mov     [rcx], edi
0x180019c8a  mov     edi, 20h ; ' '
0x180019c8f  mov     [rbp+3Fh+var_7C], ax
0x180019c93  mov     ecx, edi; unsigned int
0x180019c95  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180019c9a  mov     edi, eax
0x180019c9c  mov     rcx, r13; pv
0x180019c9f  call    cs:__imp_CoTaskMemFree
0x180019ca5  lea     ecx, [rdi+1]
0x180019ca8  add     rcx, rcx; cb
0x180019cab  call    cs:__imp_CoTaskMemAlloc
0x180019cb1  mov     r13, rax
0x180019cb4  xor     eax, eax
0x180019cb6  test    r13, r13
0x180019cb9  jnz     short loc_180019CD4
0x180019cbb  mov     [rbp+3Fh+var_80], 8007000Eh
0x180019cc2  mov     eax, 0BDCh
0x180019cc7  mov     [rbp+3Fh+var_7A], ax
0x180019ccb  mov     rax, [rbp+3Fh+pv]
0x180019ccf  jmp     loc_180019BCF
0x180019cd4  mov     [rbp+3Fh+var_80], eax
0x180019cd7  mov     ecx, 0BDCh
0x180019cdc  mov     [rbp+3Fh+var_7C], cx
0x180019ce0  mov     [rsp+0D0h+nFileSystemNameSize], eax; nFileSystemNameSize
0x180019ce4  mov     [rsp+0D0h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x180019ce9  lea     rax, [rbp+3Fh+FileSystemFlags]
0x180019ced  mov     [rsp+0D0h+lpFileSystemFlags], rax; lpFileSystemFlags
0x180019cf2  lea     rax, [rbp+3Fh+MaximumComponentLength]
0x180019cf6  mov     [rsp+0D0h+lpMaximumComponentLength], rax; lpMaximumComponentLength
0x180019cfb  xor     r9d, r9d; lpVolumeSerialNumber
0x180019cfe  mov     r8d, edi; nVolumeNameSize
0x180019d01  mov     rdx, r13; lpVolumeNameBuffer
0x180019d04  mov     rcx, r14; lpRootPathName
0x180019d07  call    cs:__imp_GetVolumeInformationW
0x180019d0d  test    eax, eax
0x180019d0f  jz      loc_180019EB4
0x180019d15  mov     rcx, rdi
0x180019d18  xor     edi, edi
0x180019d1a  mov     [r13+rcx*2+0], di
0x180019d20  cmp     [r13+0], di
0x180019d25  jz      short loc_180019D72
0x180019d27  mov     rdx, r13; unsigned __int16 *
0x180019d2a  mov     rcx, rbx; this
0x180019d2d  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180019d32  mov     [rbp+3Fh+var_80], eax
0x180019d35  test    eax, eax
0x180019d37  mov     eax, 0BE9h
0x180019d3c  js      loc_180019BC8
0x180019d42  mov     [rbp+3Fh+var_7C], ax
0x180019d46  mov     rdx, r13; unsigned __int16 *
0x180019d49  mov     rcx, r12; this
0x180019d4c  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180019d51  mov     [rbp+3Fh+var_80], eax
0x180019d54  test    eax, eax
0x180019d56  mov     eax, 0BEAh
0x180019d5b  js      loc_180019BC8
0x180019d61  mov     [rbp+3Fh+var_7C], ax
0x180019d65  mov     rax, [rbp+3Fh+arg_40]
0x180019d6c  mov     dword ptr [rax], 1
0x180019d72  mov     ecx, 40h ; '@'; unsigned int
0x180019d77  mov     dword ptr [rbp+3Fh+cchReturnLength], ecx
0x180019d7a  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180019d7f  mov     r14d, eax
0x180019d82  mov     rcx, [rbp+3Fh+pv]; pv
0x180019d86  call    cs:__imp_CoTaskMemFree
0x180019d8c  mov     edi, r14d
0x180019d8f  add     rdi, rdi
0x180019d92  mov     rcx, rdi; cb
0x180019d95  call    cs:__imp_CoTaskMemAlloc
0x180019d9b  mov     [rbp+3Fh+pv], rax
0x180019d9f  xor     ecx, ecx
0x180019da1  test    rax, rax
0x180019da4  jz      loc_180019E7B
0x180019daa  mov     [rbp+3Fh+var_80], ecx
0x180019dad  mov     eax, 0BF4h
0x180019db2  mov     [rbp+3Fh+var_7C], ax
0x180019db6  mov     r8, rdi; Size
0x180019db9  xor     edx, edx; Val
0x180019dbb  mov     rcx, [rbp+3Fh+pv]; void *
0x180019dbf  call    memset_0
0x180019dc4  lea     r9, [rbp+3Fh+cchReturnLength]; lpcchReturnLength
0x180019dc8  mov     r8d, r14d; cchBufferLength
0x180019dcb  mov     rdx, [rbp+3Fh+pv]; lpszVolumePathNames
0x180019dcf  mov     rdi, [rbp+3Fh+lpszVolumeName]
0x180019dd3  mov     rcx, rdi; lpszVolumeName
0x180019dd6  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180019ddc  xor     r14d, r14d
0x180019ddf  test    eax, eax
0x180019de1  jz      loc_180019F18
0x180019de7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019deb  mov     rcx, [rbp+3Fh+pv]
0x180019def  inc     rax
0x180019df2  cmp     [rcx+rax*2], r14w
0x180019df7  jnz     short loc_180019DEF
0x180019df9  test    rax, rax
0x180019dfc  jnz     loc_180019F4C
0x180019e02  cmp     [r13+0], r14w
0x180019e07  jnz     loc_18001A0BE
0x180019e0d  cmp     [rbx+8], r14d
0x180019e11  jz      short loc_180019E90
0x180019e13  cmp     [rsi+8], r14d
0x180019e17  jz      loc_18001A0E2
0x180019e1d  cmp     [r15+8], r14d
0x180019e21  jnz     short loc_180019E42
0x180019e23  mov     rdx, rdi; unsigned __int16 *
0x180019e26  mov     rcx, r15; this
0x180019e29  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180019e2e  mov     [rbp+3Fh+var_80], eax
0x180019e31  test    eax, eax
0x180019e33  mov     eax, 0C3Ah
0x180019e38  js      loc_180019CC7
0x180019e3e  mov     [rbp+3Fh+var_7C], ax
0x180019e42  cmp     [r12+8], r14d
0x180019e47  jnz     loc_180019CCB
0x180019e4d  mov     rax, [rbp+3Fh+arg_40]
0x180019e54  mov     [rax], r14d
0x180019e57  mov     rdx, rdi; unsigned __int16 *
0x180019e5a  mov     rcx, r12; this
0x180019e5d  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180019e62  mov     [rbp+3Fh+var_80], eax
0x180019e65  test    eax, eax
0x180019e67  mov     eax, 0C40h
0x180019e6c  js      loc_180019CC7
0x180019e72  mov     [rbp+3Fh+var_7C], ax
0x180019e76  jmp     loc_180019CCB
0x180019e7b  mov     [rbp+3Fh+var_80], 8007000Eh
0x180019e82  mov     ecx, 0BF4h
0x180019e87  mov     [rbp+3Fh+var_7A], cx
0x180019e8b  jmp     loc_180019BCF
0x180019e90  mov     rdx, rdi; unsigned __int16 *
0x180019e93  mov     rcx, rbx; this
0x180019e96  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180019e9b  mov     [rbp+3Fh+var_80], eax
0x180019e9e  test    eax, eax
0x180019ea0  mov     eax, 0C2Fh
0x180019ea5  js      loc_180019CC7
0x180019eab  mov     [rbp+3Fh+var_7C], ax
0x180019eaf  jmp     loc_180019E13
0x180019eb4  call    cs:__imp_GetLastError
0x180019eba  cmp     eax, 0EAh
0x180019ebf  jnz     short loc_180019ED2
0x180019ec1  mov     [rbp+3Fh+var_80], 0
0x180019ec8  mov     eax, 0BE3h
0x180019ecd  jmp     loc_180019C8F
0x180019ed2  call    GetLastFailureAsHRESULT
0x180019ed7  mov     [rbp+3Fh+var_80], eax
0x180019eda  mov     eax, 0BE3h
0x180019edf  jmp     loc_180019CC7
0x180019ee4  mov     rcx, rbx; this
0x180019ee7  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180019eec  jmp     loc_180019B6E
0x180019ef1  mov     rcx, r12; this
0x180019ef4  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180019ef9  jmp     loc_180019B77
0x180019efe  mov     rcx, rsi; this
0x180019f01  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180019f06  jmp     loc_180019B84
0x180019f0b  mov     rcx, r15; this
0x180019f0e  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180019f13  jmp     loc_180019B91
0x180019f18  call    cs:__imp_GetLastError
0x180019f1e  cmp     eax, 0EAh
0x180019f23  jnz     short loc_180019F3A
0x180019f25  mov     [rbp+3Fh+var_80], r14d
0x180019f29  mov     eax, 0BFCh
0x180019f2e  mov     [rbp+3Fh+var_7C], ax
0x180019f32  mov     ecx, dword ptr [rbp+3Fh+cchReturnLength]
0x180019f35  jmp     loc_180019D7A
0x180019f3a  call    GetLastFailureAsHRESULT
0x180019f3f  mov     [rbp+3Fh+var_80], eax
0x180019f42  mov     eax, 0BFCh
0x180019f47  jmp     loc_180019CC7
0x180019f4c  cmp     [r13+0], r14w
0x180019f51  jz      short loc_180019F76
0x180019f53  lea     rdx, asc_180073D24; " "
0x180019f5a  mov     rcx, rbx; this
0x180019f5d  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180019f62  mov     [rbp+3Fh+var_80], eax
0x180019f65  test    eax, eax
0x180019f67  mov     eax, 0C06h
0x180019f6c  js      loc_180019CC7
0x180019f72  mov     [rbp+3Fh+var_7C], ax
0x180019f76  lea     rdx, asc_180073D28; "("
0x180019f7d  mov     rcx, rbx; this
0x180019f80  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180019f85  mov     [rbp+3Fh+var_80], eax
0x180019f88  test    eax, eax
0x180019f8a  mov     eax, 0C08h
0x180019f8f  js      loc_180019CC7
0x180019f95  mov     [rbp+3Fh+var_7C], ax
0x180019f99  mov     rdi, [rbp+3Fh+pv]
0x180019f9d  xor     r9d, r9d
0x180019fa0  cmp     [rdi], r9w
0x180019fa4  jz      loc_18001A096
0x180019faa  mov     rax, [rbp+3Fh+arg_30]
  ... truncated ...
```
