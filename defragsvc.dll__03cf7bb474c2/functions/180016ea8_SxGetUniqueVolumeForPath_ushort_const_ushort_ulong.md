# SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)

- ea: `0x180016ea8`
- end: `0x18001724b`
- name: `?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z`
- size: `931`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, LPWSTR lpszVolumeName, unsigned int)`
- caller_count: `8`
- callee_count: `12`
- tags: `reparse_path`

## callers

- `0x18001727c`
- `0x180017f60`
- `0x18001bf30`
- `0x18001df64`
- `0x18003d58c`
- `0x18004deb0`
- `0x1800548f0`
- `0x180061b48`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180010bc0`
- `0x1800157fc`
- `0x180016ea8`
- `0x180017e34`
- `0x1800192b4`
- `0x18001a630`
- `0x18004bcd4`
- `0x180067af2`
- `0x180067b0a`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18001708f`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18001708f`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800170bd`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800170e6`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800170bd`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800170e6`

## string_xrefs

- `0x180016f03`: `SxGetUniqueVolumeForPath`
- `0x1800171c0`: `::GetVolumePathName( strPath, STRING_CCH_PARAM( wszRootPath ) )`
- `0x180017175`: `::GetVolumeNameForVolumeMountPoint( wszRootPath, STRING_CCH_PARAM( wszVolume ) )`
- `0x1800171f2`: `::GetVolumeNameForVolumeMountPoint( wszVolume, pwszUnique, cchUnique )`

## pseudocode

```c
__int64 __fastcall SxGetUniqueVolumeForPath(const unsigned __int16 *Src, LPWSTR lpszVolumeName, DWORD a3)
{
  DWORD v3; // edi
  unsigned __int16 *v6; // rsi
  unsigned __int16 v7; // dx
  __int16 v8; // ax
  int LastFailureAsHRESULT; // ebx
  __int64 v11; // r14
  int v12; // eax
  int v13; // r15d
  WCHAR *v14; // rdi
  int v15; // r15d
  int v16; // eax
  bool v17; // sf
  __int16 v18; // ax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  int v31; // r8d
  int v32; // r8d
  int v33; // r8d
  LPCWSTR lpszFileName; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v35; // [rsp+38h] [rbp-C8h]
  int v36; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v37; // [rsp+44h] [rbp-BCh]
  __int16 v38; // [rsp+46h] [rbp-BAh]
  DWORD cchBufferLength; // [rsp+78h] [rbp-88h]
  WCHAR szVolumePathName[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR szVolumeName[264]; // [rsp+290h] [rbp+190h] BYREF

  v3 = a3;
  cchBufferLength = a3;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, Src);
  }
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v36, "SxGetUniqueVolumeForPath", 510, 1);
  v6 = (unsigned __int16 *)&qword_18006F470;
  lpszFileName = &qword_18006F470;
  v35 = 0;
  memset_0(szVolumePathName, 0, 0x20Au);
  memset_0(szVolumeName, 0, 0x20Au);
  v8 = 516;
  if ( !Src )
    goto LABEL_5;
  v37 = 516;
  if ( !lpszVolumeName )
  {
    v8 = 517;
LABEL_5:
    LastFailureAsHRESULT = -2147024809;
    v38 = v8;
LABEL_6:
    v36 = LastFailureAsHRESULT;
    goto LABEL_7;
  }
  v36 = 0;
  v37 = 518;
  v11 = -1;
  do
    ++v11;
  while ( Src[v11] );
  LastFailureAsHRESULT = 0;
  if ( (_DWORD)v11
    && (v12 = CBsString::ExtendBuffer((CBsString *)&lpszFileName, (int)v11 + 1),
        v6 = (unsigned __int16 *)lpszFileName,
        LastFailureAsHRESULT = v12,
        v12 >= 0) )
  {
    v13 = v35;
    v14 = (WCHAR *)&lpszFileName[(unsigned int)v35];
    memcpy_0(v14, Src, 2LL * (unsigned int)v11);
    v15 = v11 + v13;
    v14[(unsigned int)v11] = 0;
    v3 = cchBufferLength;
    LODWORD(v35) = v15;
  }
  else
  {
    v36 = LastFailureAsHRESULT;
    if ( LastFailureAsHRESULT < 0 )
    {
      v18 = 520;
      goto LABEL_30;
    }
    v15 = v35;
  }
  v37 = 520;
  v8 = 521;
  if ( !v15 )
    goto LABEL_5;
  v36 = 0;
  v37 = 521;
  v16 = CBsString::Trailing((CBsString *)&lpszFileName, v7);
  v6 = (unsigned __int16 *)lpszFileName;
  LastFailureAsHRESULT = v16;
  v36 = v16;
  v17 = v16 < 0;
  v18 = 523;
  if ( v17 )
  {
LABEL_30:
    v38 = v18;
    goto LABEL_7;
  }
  v37 = 523;
  if ( !GetVolumePathNameW(lpszFileName, szVolumePathName, 0x105u) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v20, v19, v21, v22);
    v36 = LastFailureAsHRESULT;
    v38 = 529;
    if ( WPP_GLOBAL_Control == (CSxGlobalTracer *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) == 0 )
    {
      goto LABEL_7;
    }
    WPP_SF_sSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      v32,
      (unsigned int)"::GetVolumePathName( strPath, STRING_CCH_PARAM( wszRootPath ) )",
      (__int64)v6,
      LastFailureAsHRESULT);
LABEL_31:
    LastFailureAsHRESULT = v36;
    goto LABEL_7;
  }
  v36 = 0;
  v37 = 529;
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x105u) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v24, v23, v25, v26);
    v36 = LastFailureAsHRESULT;
    v38 = 536;
    if ( WPP_GLOBAL_Control == (CSxGlobalTracer *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) == 0 )
    {
      goto LABEL_7;
    }
    WPP_SF_sSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      v31,
      (unsigned int)"::GetVolumeNameForVolumeMountPoint( wszRootPath, STRING_CCH_PARAM( wszVolume ) )",
      (__int64)szVolumePathName,
      LastFailureAsHRESULT);
    goto LABEL_31;
  }
  v36 = 0;
  v37 = 536;
  if ( GetVolumeNameForVolumeMountPointW(szVolumeName, lpszVolumeName, v3) )
  {
    LastFailureAsHRESULT = 0;
    v37 = 542;
    goto LABEL_6;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v28, v27, v29, v30);
  v36 = LastFailureAsHRESULT;
  v38 = 542;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    WPP_SF_sSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      v33,
      (unsigned int)"::GetVolumeNameForVolumeMountPoint( wszVolume, pwszUnique, cchUnique )",
      (__int64)szVolumeName,
      LastFailureAsHRESULT);
    goto LABEL_31;
  }
LABEL_7:
  CBsString::_FreeData(v6);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v36);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180016ea8  mov     [rsp-8+arg_18], rbx
0x180016ead  push    rbp
0x180016eae  push    rsi
0x180016eaf  push    rdi
0x180016eb0  push    r12
0x180016eb2  push    r13
0x180016eb4  push    r14
0x180016eb6  push    r15
0x180016eb8  lea     rbp, [rsp-3B0h]
0x180016ec0  sub     rsp, 4B0h
0x180016ec7  mov     rax, cs:__security_cookie
0x180016ece  xor     rax, rsp
0x180016ed1  mov     [rbp+3E0h+var_40], rax
0x180016ed8  mov     edi, r8d
0x180016edb  mov     [rsp+4E0h+cchBufferLength], r8d
0x180016ee0  mov     r13, rdx
0x180016ee3  mov     r12, rcx
0x180016ee6  mov     rcx, cs:WPP_GLOBAL_Control
0x180016eed  lea     rax, WPP_GLOBAL_Control
0x180016ef4  cmp     rcx, rax
0x180016ef7  jnz     loc_180017105
0x180016efd  mov     r9d, 1; unsigned __int16
0x180016f03  lea     rdx, aSxgetuniquevol; "SxGetUniqueVolumeForPath"
0x180016f0a  mov     r8d, 1FEh; unsigned __int16
0x180016f10  lea     rcx, [rsp+4E0h+var_4A0]; this
0x180016f15  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180016f1a  mov     ebx, 20Ah
0x180016f1f  lea     rsi, qword_18006F470
0x180016f26  xor     r15d, r15d
0x180016f29  mov     [rsp+4E0h+lpszFileName], rsi
0x180016f2e  mov     r8d, ebx; Size
0x180016f31  mov     [rsp+4E0h+var_4A8], r15
0x180016f36  xor     edx, edx; Val
0x180016f38  lea     rcx, [rbp+3E0h+szVolumePathName]; void *
0x180016f3c  call    memset_0
0x180016f41  mov     r8d, ebx; Size
0x180016f44  lea     rcx, [rbp+3E0h+szVolumeName]; void *
0x180016f4b  xor     edx, edx; Val
0x180016f4d  call    memset_0
0x180016f52  lea     eax, [rbx-6]
0x180016f55  test    r12, r12
0x180016f58  jz      short loc_180016F67
0x180016f5a  mov     [rsp+4E0h+var_49C], ax
0x180016f5f  test    r13, r13
0x180016f62  jnz     short loc_180016FB3
0x180016f64  lea     eax, [rbx-5]
0x180016f67  mov     ebx, 80070057h
0x180016f6c  mov     [rsp+4E0h+var_49A], ax
0x180016f71  mov     [rsp+4E0h+var_4A0], ebx
0x180016f75  mov     rcx, rsi; unsigned __int16 *
0x180016f78  call    ?_FreeData@CBsString@@CAXPEAGK@Z; CBsString::_FreeData(ushort *,ulong)
0x180016f7d  lea     rcx, [rsp+4E0h+var_4A0]; this
0x180016f82  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180016f87  mov     eax, ebx
0x180016f89  mov     rcx, [rbp+3E0h+var_40]
0x180016f90  xor     rcx, rsp; StackCookie
0x180016f93  call    __security_check_cookie
0x180016f98  mov     rbx, [rsp+4E0h+arg_18]
0x180016fa0  add     rsp, 4B0h
0x180016fa7  pop     r15
0x180016fa9  pop     r14
0x180016fab  pop     r13
0x180016fad  pop     r12
0x180016faf  pop     rdi
0x180016fb0  pop     rsi
0x180016fb1  pop     rbp
0x180016fb2  retn
0x180016fb3  mov     eax, 206h
0x180016fb8  mov     [rsp+4E0h+var_4A0], r15d
0x180016fbd  mov     [rsp+4E0h+var_49C], ax
0x180016fc2  or      r14, 0FFFFFFFFFFFFFFFFh
0x180016fc6  inc     r14
0x180016fc9  cmp     [r12+r14*2], r15w
0x180016fce  jnz     short loc_180016FC6
0x180016fd0  mov     ebx, r15d
0x180016fd3  test    r14d, r14d
0x180016fd6  jz      short loc_180017023
0x180016fd8  lea     edx, [r14+1]; unsigned int
0x180016fdc  lea     rcx, [rsp+4E0h+lpszFileName]; this
0x180016fe1  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180016fe6  mov     rsi, [rsp+4E0h+lpszFileName]
0x180016feb  mov     ebx, eax
0x180016fed  test    eax, eax
0x180016fef  js      short loc_180017023
0x180016ff1  mov     r15d, dword ptr [rsp+4E0h+var_4A8]
0x180016ff6  mov     rdx, r12; Src
0x180016ff9  mov     eax, r14d
0x180016ffc  lea     rdi, [rsi+r15*2]
0x180017000  lea     rbx, [rax+rax]
0x180017004  mov     rcx, rdi; void *
0x180017007  mov     r8, rbx; Size
0x18001700a  call    memcpy_0
0x18001700f  xor     eax, eax
0x180017011  add     r15d, r14d
0x180017014  mov     [rbx+rdi], ax
0x180017018  mov     edi, [rsp+4E0h+cchBufferLength]
0x18001701c  mov     dword ptr [rsp+4E0h+var_4A8], r15d
0x180017021  jmp     short loc_180017034
0x180017023  mov     [rsp+4E0h+var_4A0], ebx
0x180017027  test    ebx, ebx
0x180017029  js      loc_1800171D3
0x18001702f  mov     r15d, dword ptr [rsp+4E0h+var_4A8]
0x180017034  mov     eax, 208h
0x180017039  mov     [rsp+4E0h+var_49C], ax
0x18001703e  mov     eax, 209h
0x180017043  test    r15d, r15d
0x180017046  jz      loc_180016F67
0x18001704c  lea     rcx, [rsp+4E0h+lpszFileName]; this
0x180017051  mov     [rsp+4E0h+var_4A0], 0
0x180017059  mov     [rsp+4E0h+var_49C], ax
0x18001705e  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x180017063  mov     rsi, [rsp+4E0h+lpszFileName]
0x180017068  mov     ebx, eax
0x18001706a  mov     [rsp+4E0h+var_4A0], eax
0x18001706e  test    eax, eax
0x180017070  mov     eax, 20Bh
0x180017075  js      loc_1800171D8
0x18001707b  mov     ebx, 105h
0x180017080  mov     [rsp+4E0h+var_49C], ax
0x180017085  mov     r8d, ebx; cchBufferLength
0x180017088  lea     rdx, [rbp+3E0h+szVolumePathName]; lpszVolumePathName
0x18001708c  mov     rcx, rsi; lpszFileName
0x18001708f  call    cs:__imp_GetVolumePathNameW
0x180017095  test    eax, eax
0x180017097  jz      loc_180017183
0x18001709d  mov     eax, 211h
0x1800170a2  mov     [rsp+4E0h+var_4A0], 0
0x1800170aa  mov     r8d, ebx; cchBufferLength
0x1800170ad  mov     [rsp+4E0h+var_49C], ax
0x1800170b2  lea     rdx, [rbp+3E0h+szVolumeName]; lpszVolumeName
0x1800170b9  lea     rcx, [rbp+3E0h+szVolumePathName]; lpszVolumeMountPoint
0x1800170bd  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800170c3  test    eax, eax
0x1800170c5  jz      short loc_18001712F
0x1800170c7  mov     eax, 218h
0x1800170cc  mov     [rsp+4E0h+var_4A0], 0
0x1800170d4  mov     r8d, edi; cchBufferLength
0x1800170d7  mov     [rsp+4E0h+var_49C], ax
0x1800170dc  mov     rdx, r13; lpszVolumeName
0x1800170df  lea     rcx, [rbp+3E0h+szVolumeName]; lpszVolumeMountPoint
0x1800170e6  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800170ec  test    eax, eax
0x1800170ee  jz      loc_180017210
0x1800170f4  mov     eax, 21Eh
0x1800170f9  xor     ebx, ebx
0x1800170fb  mov     [rsp+4E0h+var_49C], ax
0x180017100  jmp     loc_180016F71
0x180017105  test    dword ptr [rcx+1Ch], 20000000h
0x18001710c  jz      loc_180016EFD
0x180017112  mov     rcx, [rcx+10h]
0x180017116  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x18001711d  mov     edx, 12h
0x180017122  mov     r9, r12
0x180017125  call    WPP_SF_S
0x18001712a  jmp     loc_180016EFD
0x18001712f  call    GetLastFailureAsHRESULT
0x180017134  mov     ebx, eax
0x180017136  mov     [rsp+4E0h+var_4A0], eax
0x18001713a  mov     eax, 218h
0x18001713f  mov     [rsp+4E0h+var_49A], ax
0x180017144  mov     rcx, cs:WPP_GLOBAL_Control
0x18001714b  lea     rax, WPP_GLOBAL_Control
0x180017152  cmp     rcx, rax
0x180017155  jz      loc_180016F75
0x18001715b  test    dword ptr [rcx+1Ch], 2000000h
0x180017162  jz      loc_180016F75
0x180017168  lea     rax, [rbp+3E0h+szVolumePathName]
0x18001716c  mov     [rsp+4E0h+var_4B8], ebx
0x180017170  mov     [rsp+4E0h+var_4C0], rax
0x180017175  lea     r9, aGetvolumenamef_0; "::GetVolumeNameForVolumeMountPoint( wsz"...
0x18001717c  mov     edx, 14h
0x180017181  jmp     short loc_1800171FE
0x180017183  call    GetLastFailureAsHRESULT
0x180017188  mov     ebx, eax
0x18001718a  mov     [rsp+4E0h+var_4A0], eax
0x18001718e  mov     eax, 211h
0x180017193  mov     [rsp+4E0h+var_49A], ax
0x180017198  mov     rcx, cs:WPP_GLOBAL_Control
0x18001719f  lea     rax, WPP_GLOBAL_Control
0x1800171a6  cmp     rcx, rax
0x1800171a9  jz      loc_180016F75
0x1800171af  test    dword ptr [rcx+1Ch], 2000000h
0x1800171b6  jz      loc_180016F75
0x1800171bc  mov     [rsp+4E0h+var_4B8], ebx
0x1800171c0  lea     r9, aGetvolumepathn; "::GetVolumePathName( strPath, STRING_CC"...
0x1800171c7  mov     [rsp+4E0h+var_4C0], rsi
0x1800171cc  mov     edx, 13h
0x1800171d1  jmp     short loc_1800171FE
0x1800171d3  mov     eax, 208h
0x1800171d8  mov     [rsp+4E0h+var_49A], ax
0x1800171dd  jmp     loc_180016F75
0x1800171e2  lea     rax, [rbp+3E0h+szVolumeName]
0x1800171e9  mov     [rsp+4E0h+var_4B8], ebx
0x1800171ed  mov     [rsp+4E0h+var_4C0], rax
0x1800171f2  lea     r9, aGetvolumenamef; "::GetVolumeNameForVolumeMountPoint( wsz"...
0x1800171f9  mov     edx, 15h
0x1800171fe  mov     rcx, [rcx+10h]
0x180017202  call    WPP_SF_sSd
0x180017207  mov     ebx, [rsp+4E0h+var_4A0]
0x18001720b  jmp     loc_180016F75
0x180017210  call    GetLastFailureAsHRESULT
0x180017215  mov     ebx, eax
0x180017217  mov     [rsp+4E0h+var_4A0], eax
0x18001721b  mov     eax, 21Eh
0x180017220  mov     [rsp+4E0h+var_49A], ax
0x180017225  mov     rcx, cs:WPP_GLOBAL_Control
0x18001722c  lea     rax, WPP_GLOBAL_Control
0x180017233  cmp     rcx, rax
0x180017236  jz      loc_180016F75
0x18001723c  test    dword ptr [rcx+1Ch], 2000000h
0x180017243  jz      loc_180016F75
0x180017249  jmp     short loc_1800171E2
```
