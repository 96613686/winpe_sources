# PSetupValidateDriver

- ea: `0x1800281a0`
- end: `0x1800284ca`
- name: `PSetupValidateDriver`
- size: `810`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18000f698`

## callees

- `0x180002300`
- `0x18000d57c`
- `0x18001c660`
- `0x180024e00`
- `0x1800260c4`
- `0x1800281a0`
- `0x1800362e4`
- `0x180036ea4`
- `0x180037098`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800283ba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180028409`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800283ba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180028409`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800283d1`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800283ed`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800283d1`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800283ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002833f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002833f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180028333`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180028333`

## string_xrefs

- `0x18002826f`: `*.dll`
- `0x180028458`: `BuildFileListFromPath failed to get a list of files! Error %d`

## pseudocode

```c
__int64 __fastcall PSetupValidateDriver(unsigned int a1, const wchar_t *a2)
{
  int v4; // edi
  unsigned __int16 *v5; // r14
  LPCWSTR v6; // rsi
  unsigned __int16 *v7; // rbx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  int v11; // edx
  unsigned __int16 *v12; // rbx
  int v13; // eax
  __int64 v14; // rcx
  unsigned __int16 *CatalogPathFromFilePath; // rax
  unsigned __int16 *v16; // rsi
  int v17; // r12d
  const WCHAR *i; // rbx
  DWORD LastError; // eax
  __int64 v20; // rax
  unsigned int v21; // eax
  wchar_t *v22; // rbx
  unsigned int v23; // r15d
  wchar_t *v24; // rax
  const wchar_t *v25; // rax
  wchar_t *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  LPCWSTR lpFileName; // [rsp+20h] [rbp-40h] BYREF
  unsigned __int16 *v31; // [rsp+28h] [rbp-38h] BYREF
  unsigned int v32; // [rsp+30h] [rbp-30h]
  wchar_t *Str; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int16 *v34; // [rsp+40h] [rbp-20h] BYREF
  _DWORD v35[4]; // [rsp+48h] [rbp-18h] BYREF

  v32 = a1;
  v31 = 0;
  v34 = 0;
  lpFileName = 0;
  Str = 0;
  v35[0] = -145692989;
  v4 = 1;
  v35[1] = 298924270;
  v5 = 0;
  v35[2] = -1073683067;
  v6 = 0;
  v35[3] = -292175281;
  if ( (unsigned int)BuildFileListFromPath(a2, L"*.inf", &v31) || !v31 )
    goto LABEL_10;
  v7 = v31;
  do
  {
    if ( !v7 )
      break;
    if ( !*v7 )
      break;
    v8 = IsDriverFileInExclusionList(v7);
    v4 = v8 == 0;
    v9 = -1;
    do
      ++v9;
    while ( v7[v9] );
    v7 += v9 + 1;
  }
  while ( !v8 );
  if ( v4 )
  {
LABEL_10:
    v10 = BuildFileListFromPath(a2, L"*.dll", &v34);
    v5 = v34;
    if ( !v10 && v34 )
    {
      v12 = v34;
      v11 = 0;
      do
      {
        if ( !v12 )
          break;
        if ( !*v12 )
          break;
        v13 = IsDriverFileInExclusionList(v12);
        v11 = 0;
        v4 = v13 == 0;
        v14 = -1;
        do
          ++v14;
        while ( v12[v14] );
        v12 += v14 + 1;
      }
      while ( !v13 );
    }
    if ( v4 )
    {
      CatalogPathFromFilePath = GetCatalogPathFromFilePath(a2, v11);
      v16 = CatalogPathFromFilePath;
      if ( !CatalogPathFromFilePath || (v4 = VerifyFileSignature(a1, CatalogPathFromFilePath, 0, v35)) != 0 )
      {
        v17 = 0;
        if ( !(unsigned int)BuildFileListFromPath(a2, L"*.pnf", (unsigned __int16 **)&lpFileName) )
        {
          for ( i = lpFileName; i && *i; i += v20 + 1 )
          {
            if ( !(unsigned int)IsPathInDriverStore(i) && !DeleteFileW(i) )
            {
              LastError = GetLastError();
              ClassInstallerTelemetry::WriteDbgTraceError(
                "PSetupValidateDriver",
                L"Deleting PNF file %ws failed! Error %d",
                i,
                LastError);
              v17 = 1;
            }
            v20 = -1;
            do
              ++v20;
            while ( i[v20] );
          }
        }
        v21 = BuildFileListFromPath(a2, L"*.*", &Str);
        if ( v21 )
        {
          ClassInstallerTelemetry::WriteDbgTraceError(
            "PSetupValidateDriver",
            L"BuildFileListFromPath failed to get a list of files! Error %d",
            v21);
          v4 = 0;
        }
        else
        {
          v22 = Str;
          v23 = v32;
          do
          {
            if ( !v22 || !*v22 )
              break;
            if ( (unsigned int)_o__wcsicmp(v22, v16) )
            {
              if ( v17
                || ((v24 = wcsrchr(v22, 0x5Cu)) == 0 ? (v25 = v22) : (v25 = v24 + 1),
                    (v26 = wcsrchr(v25, 0x2Eu), (v27 = (unsigned __int64)(v26 + 1) & -(__int64)(v26 != 0)) == 0)
                 || (unsigned int)_o__wcsicmp(v27, L"PNF")) )
              {
                v4 = VerifyFileSignature(v23, v22, v16, v35);
              }
            }
            v28 = -1;
            do
              ++v28;
            while ( v22[v28] );
            v22 += v28 + 1;
          }
          while ( v4 );
          DllFreeSplMem(Str);
        }
      }
      v6 = lpFileName;
    }
  }
  if ( v31 )
    DllFreeSplMem(v31);
  if ( v5 )
    DllFreeSplMem(v5);
  if ( v6 )
    DllFreeSplMem(v6);
  return v4 == 0 ? 0x800B0004 : 0;
}

```

## disassembly

```asm
0x1800281a0  mov     [rsp-28h+arg_10], rbx
0x1800281a5  mov     [rsp-28h+arg_18], rsi
0x1800281aa  push    rbp
0x1800281ab  push    rdi
0x1800281ac  push    r12
0x1800281ae  push    r14
0x1800281b0  push    r15
0x1800281b2  mov     rbp, rsp
0x1800281b5  sub     rsp, 60h
0x1800281b9  mov     rax, cs:__security_cookie
0x1800281c0  xor     rax, rsp
0x1800281c3  mov     [rbp+var_8], rax
0x1800281c7  xor     ebx, ebx
0x1800281c9  mov     [rbp+var_30], ecx
0x1800281cc  mov     r15, rdx
0x1800281cf  mov     [rbp+var_38], rbx
0x1800281d3  mov     r12d, ecx
0x1800281d6  mov     [rbp+var_20], rbx
0x1800281da  lea     r8, [rbp+var_38]; unsigned __int16 **
0x1800281de  mov     [rbp+lpFileName], rbx
0x1800281e2  lea     rdx, aInf_1; "*.inf"
0x1800281e9  mov     [rbp+Str], rbx
0x1800281ed  mov     rcx, r15; pszSrc
0x1800281f0  mov     [rbp+var_18], 0F750E6C3h
0x1800281f7  lea     edi, [rbx+1]
0x1800281fa  mov     [rbp+var_14], 11D138EEh
0x180028201  mov     r14d, ebx
0x180028204  mov     [rbp+var_10], 0C000E585h
0x18002820b  mov     esi, ebx
0x18002820d  mov     [rbp+var_C], 0EE95C24Fh
0x180028214  call    ?BuildFileListFromPath@@YAKPEBG0PEAPEAG@Z; BuildFileListFromPath(ushort const *,ushort const *,ushort * *)
0x180028219  test    eax, eax
0x18002821b  jnz     short loc_180028268
0x18002821d  cmp     [rbp+var_38], rbx
0x180028221  jz      short loc_180028268
0x180028223  mov     rbx, [rbp+var_38]
0x180028227  xor     edx, edx
0x180028229  test    rbx, rbx
0x18002822c  jz      short loc_18002825E
0x18002822e  cmp     [rbx], dx
0x180028231  jz      short loc_18002825E
0x180028233  mov     rcx, rbx; unsigned __int16 *
0x180028236  call    ?IsDriverFileInExclusionList@@YAHPEBG@Z; IsDriverFileInExclusionList(ushort const *)
0x18002823b  xor     edx, edx
0x18002823d  test    eax, eax
0x18002823f  mov     edi, edx
0x180028241  setz    dil
0x180028245  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180028249  inc     rcx
0x18002824c  cmp     [rbx+rcx*2], dx
0x180028250  jnz     short loc_180028249
0x180028252  lea     rbx, [rbx+rcx*2]
0x180028256  add     rbx, 2
0x18002825a  test    eax, eax
0x18002825c  jz      short loc_180028229
0x18002825e  xor     ebx, ebx
0x180028260  test    edi, edi
0x180028262  jz      loc_180028471
0x180028268  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18002826c  mov     rcx, r15; pszSrc
0x18002826f  lea     rdx, aDll; "*.dll"
0x180028276  call    ?BuildFileListFromPath@@YAKPEBG0PEAPEAG@Z; BuildFileListFromPath(ushort const *,ushort const *,ushort * *)
0x18002827b  mov     r14, [rbp+var_20]
0x18002827f  test    eax, eax
0x180028281  jnz     short loc_1800282C4
0x180028283  test    r14, r14
0x180028286  jz      short loc_1800282C4
0x180028288  mov     rbx, r14
0x18002828b  xor     edx, edx
0x18002828d  test    rbx, rbx
0x180028290  jz      short loc_1800282C2
0x180028292  cmp     [rbx], dx
0x180028295  jz      short loc_1800282C2
0x180028297  mov     rcx, rbx; unsigned __int16 *
0x18002829a  call    ?IsDriverFileInExclusionList@@YAHPEBG@Z; IsDriverFileInExclusionList(ushort const *)
0x18002829f  xor     edx, edx; int
0x1800282a1  test    eax, eax
0x1800282a3  mov     edi, edx
0x1800282a5  setz    dil
0x1800282a9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800282ad  inc     rcx
0x1800282b0  cmp     [rbx+rcx*2], dx
0x1800282b4  jnz     short loc_1800282AD
0x1800282b6  lea     rbx, [rbx+rcx*2]
0x1800282ba  add     rbx, 2
0x1800282be  test    eax, eax
0x1800282c0  jz      short loc_18002828D
0x1800282c2  xor     ebx, ebx
0x1800282c4  test    edi, edi
0x1800282c6  jz      loc_180028471
0x1800282cc  mov     rcx, r15; unsigned __int16 *
0x1800282cf  call    ?GetCatalogPathFromFilePath@@YAPEAGPEBGH@Z; GetCatalogPathFromFilePath(ushort const *,int)
0x1800282d4  mov     rsi, rax
0x1800282d7  test    rax, rax
0x1800282da  jz      short loc_1800282F8
0x1800282dc  lea     r9, [rbp+var_18]
0x1800282e0  xor     r8d, r8d
0x1800282e3  mov     rdx, rax
0x1800282e6  mov     ecx, r12d
0x1800282e9  call    ?VerifyFileSignature@@YAHW4_DRIVER_VALIDATION_LEVEL@@PEBG1PEAU_GUID@@@Z; VerifyFileSignature(_DRIVER_VALIDATION_LEVEL,ushort const *,ushort const *,_GUID *)
0x1800282ee  mov     edi, eax
0x1800282f0  test    eax, eax
0x1800282f2  jz      loc_18002846D
0x1800282f8  lea     r8, [rbp+lpFileName]; unsigned __int16 **
0x1800282fc  mov     rcx, r15; pszSrc
0x1800282ff  lea     rdx, aPnf; "*.pnf"
0x180028306  mov     r12d, ebx
0x180028309  call    ?BuildFileListFromPath@@YAKPEBG0PEAPEAG@Z; BuildFileListFromPath(ushort const *,ushort const *,ushort * *)
0x18002830e  test    eax, eax
0x180028310  jnz     short loc_18002837D
0x180028312  mov     rbx, [rbp+lpFileName]
0x180028316  xor     ecx, ecx
0x180028318  test    rbx, rbx
0x18002831b  jz      short loc_18002837B
0x18002831d  cmp     [rbx], cx
0x180028320  jz      short loc_18002837B
0x180028322  mov     rcx, rbx
0x180028325  call    IsPathInDriverStore
0x18002832a  xor     ecx, ecx
0x18002832c  test    eax, eax
0x18002832e  jnz     short loc_180028364
0x180028330  mov     rcx, rbx; lpFileName
0x180028333  call    cs:__imp_DeleteFileW
0x180028339  xor     ecx, ecx
0x18002833b  test    eax, eax
0x18002833d  jnz     short loc_180028364
0x18002833f  call    cs:__imp_GetLastError
0x180028345  mov     r8, rbx
0x180028348  lea     rdx, aDeletingPnfFil; "Deleting PNF file %ws failed! Error %d"
0x18002834f  mov     r9d, eax
0x180028352  lea     rcx, aPsetupvalidate; "PSetupValidateDriver"
0x180028359  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18002835e  xor     ecx, ecx
0x180028360  lea     r12d, [rcx+1]
0x180028364  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028368  inc     rax
0x18002836b  cmp     [rbx+rax*2], cx
0x18002836f  jnz     short loc_180028368
0x180028371  lea     rbx, [rbx+rax*2]
0x180028375  add     rbx, 2
0x180028379  jmp     short loc_180028318
0x18002837b  xor     ebx, ebx
0x18002837d  lea     r8, [rbp+Str]; unsigned __int16 **
0x180028381  mov     rcx, r15; pszSrc
0x180028384  lea     rdx, asc_18004A008; "*.*"
0x18002838b  call    ?BuildFileListFromPath@@YAKPEBG0PEAPEAG@Z; BuildFileListFromPath(ushort const *,ushort const *,ushort * *)
0x180028390  test    eax, eax
0x180028392  jnz     loc_180028455
0x180028398  mov     rbx, [rbp+Str]
0x18002839c  xor     ecx, ecx
0x18002839e  mov     r15d, [rbp+var_30]
0x1800283a2  test    rbx, rbx
0x1800283a5  jz      loc_180028448
0x1800283ab  cmp     [rbx], cx
0x1800283ae  jz      loc_180028448
0x1800283b4  mov     rdx, rsi
0x1800283b7  mov     rcx, rbx
0x1800283ba  call    cs:__imp__o__wcsicmp
0x1800283c0  xor     ecx, ecx
0x1800283c2  test    eax, eax
0x1800283c4  jz      short loc_18002842B
0x1800283c6  test    r12d, r12d
0x1800283c9  jnz     short loc_180028415
0x1800283cb  lea     edx, [rcx+5Ch]; Ch
0x1800283ce  mov     rcx, rbx; Str
0x1800283d1  call    cs:__imp_wcsrchr
0x1800283d7  test    rax, rax
0x1800283da  jz      short loc_1800283E2
0x1800283dc  add     rax, 2
0x1800283e0  jmp     short loc_1800283E5
0x1800283e2  mov     rax, rbx
0x1800283e5  mov     edx, 2Eh ; '.'; Ch
0x1800283ea  mov     rcx, rax; Str
0x1800283ed  call    cs:__imp_wcsrchr
0x1800283f3  lea     rdx, [rax+2]
0x1800283f7  neg     rax
0x1800283fa  sbb     rcx, rcx
0x1800283fd  and     rcx, rdx
0x180028400  jz      short loc_180028415
0x180028402  lea     rdx, aPnf_0; "PNF"
0x180028409  call    cs:__imp__o__wcsicmp
0x18002840f  xor     ecx, ecx
0x180028411  test    eax, eax
0x180028413  jz      short loc_18002842B
0x180028415  lea     r9, [rbp+var_18]
0x180028419  mov     r8, rsi
0x18002841c  mov     rdx, rbx
0x18002841f  mov     ecx, r15d
0x180028422  call    ?VerifyFileSignature@@YAHW4_DRIVER_VALIDATION_LEVEL@@PEBG1PEAU_GUID@@@Z; VerifyFileSignature(_DRIVER_VALIDATION_LEVEL,ushort const *,ushort const *,_GUID *)
0x180028427  mov     edi, eax
0x180028429  xor     ecx, ecx
0x18002842b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002842f  inc     rax
0x180028432  cmp     [rbx+rax*2], cx
0x180028436  jnz     short loc_18002842F
0x180028438  lea     rbx, [rbx+rax*2]
0x18002843c  add     rbx, 2
0x180028440  test    edi, edi
0x180028442  jnz     loc_1800283A2
0x180028448  mov     rcx, [rbp+Str]
0x18002844c  call    DllFreeSplMem
0x180028451  xor     ebx, ebx
0x180028453  jmp     short loc_18002846D
0x180028455  mov     r8d, eax
0x180028458  lea     rdx, aBuildfilelistf; "BuildFileListFromPath failed to get a l"...
0x18002845f  lea     rcx, aPsetupvalidate; "PSetupValidateDriver"
0x180028466  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18002846b  mov     edi, ebx
0x18002846d  mov     rsi, [rbp+lpFileName]
0x180028471  cmp     [rbp+var_38], rbx
0x180028475  jz      short loc_180028480
0x180028477  mov     rcx, [rbp+var_38]
0x18002847b  call    DllFreeSplMem
0x180028480  test    r14, r14
0x180028483  jz      short loc_18002848D
0x180028485  mov     rcx, r14
0x180028488  call    DllFreeSplMem
0x18002848d  test    rsi, rsi
0x180028490  jz      short loc_18002849A
0x180028492  mov     rcx, rsi
0x180028495  call    DllFreeSplMem
0x18002849a  neg     edi
0x18002849c  sbb     eax, eax
0x18002849e  not     eax
0x1800284a0  and     eax, 800B0004h
0x1800284a5  mov     rcx, [rbp+var_8]
0x1800284a9  xor     rcx, rsp; StackCookie
0x1800284ac  call    __security_check_cookie
0x1800284b1  lea     r11, [rsp+60h+var_s0]
0x1800284b6  mov     rbx, [r11+40h]
0x1800284ba  mov     rsi, [r11+48h]
0x1800284be  mov     rsp, r11
0x1800284c1  pop     r15
0x1800284c3  pop     r14
0x1800284c5  pop     r12
0x1800284c7  pop     rdi
0x1800284c8  pop     rbp
0x1800284c9  retn
```
