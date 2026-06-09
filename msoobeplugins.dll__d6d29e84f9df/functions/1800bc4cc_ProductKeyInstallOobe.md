# ProductKeyInstallOobe

- ea: `0x1800bc4cc`
- end: `0x1800bc8a1`
- name: `ProductKeyInstallOobe`
- size: `981`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180045bb0`

## callees

- `0x180003470`
- `0x180003ffc`
- `0x1800ba518`
- `0x1800ba648`
- `0x1800ba668`
- `0x1800ba93c`
- `0x1800bb324`
- `0x1800bb814`
- `0x1800bba40`
- `0x1800bbb94`
- `0x1800bbbc0`
- `0x1800bbc78`
- `0x1800bc1b0`
- `0x1800bc4cc`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc737`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc737`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800bc54d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800bc605`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800bc54d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800bc605`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc58d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc5a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc5bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc5d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc5ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc638`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc58d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc5a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc5bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc5d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc5ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc56a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc56a`

## string_xrefs

- `0x1800bc538`: `SPPC.DLL`
- `0x1800bc5fc`: `SLC.DLL`
- `0x1800bc57e`: `SLOpen`
- `0x1800bc5b3`: `SLInstallProofOfPurchaseEx`

## pseudocode

```c
__int64 __fastcall ProductKeyInstallOobe(void *Src)
{
  void (*v2)(void); // r15
  FARPROC v3; // r14
  HMODULE Library; // rdi
  DWORD LastError; // eax
  int WindowsPKeyInfo; // eax
  int v7; // ebx
  FARPROC ProcAddress; // rsi
  FARPROC v9; // r13
  HMODULE v10; // rbx
  int v11; // eax
  _WORD *v12; // rdi
  unsigned __int16 *v13; // rax
  char *v14; // r8
  __int64 v15; // rdx
  int v16; // ecx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int16 *v21; // rcx
  int v22; // eax
  _WORD *v24; // [rsp+50h] [rbp-B0h] BYREF
  void *v25; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE v26; // [rsp+60h] [rbp-A0h] BYREF
  HMODULE v27; // [rsp+68h] [rbp-98h] BYREF
  void *Srca; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h] BYREF
  __int128 v30; // [rsp+80h] [rbp-80h] BYREF
  __int128 v31; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v32[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v33; // [rsp+128h] [rbp+28h] BYREF
  char v34; // [rsp+12Ah] [rbp+2Ah] BYREF
  __int16 v35; // [rsp+172h] [rbp+72h]
  _BYTE v36[264]; // [rsp+498h] [rbp+398h] BYREF

  Srca = 0;
  v24 = 0;
  memset_0(v32, 0, 0x4F8u);
  v29 = 0;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  v2 = 0;
  v31 = 0;
  v3 = 0;
  v30 = 0;
  Library = LoadLibraryExW(L"SPPC.DLL", 0, 0);
  SH<HINSTANCE__ *,SH_HMODULE>::Reset(&v26);
  if ( !Library )
  {
    v26 = 0;
LABEL_3:
    LastError = GetLastError();
    WindowsPKeyInfo = SErrorConverter::C_LR2HR(LastError);
    v7 = WindowsPKeyInfo;
LABEL_49:
    v18 = (unsigned int)WindowsPKeyInfo;
    goto LABEL_50;
  }
  v26 = Library;
  ProcAddress = GetProcAddress(Library, "SLOpen");
  if ( !ProcAddress )
    goto LABEL_3;
  v2 = (void (*)(void))GetProcAddress(Library, "SLClose");
  if ( !v2 )
    goto LABEL_3;
  v9 = GetProcAddress(Library, "SLInstallProofOfPurchaseEx");
  if ( !v9 || !GetProcAddress(Library, "SLGetPKeyId") || !GetProcAddress(Library, "SLFireEvent") )
    goto LABEL_3;
  v10 = LoadLibraryExW(L"SLC.DLL", 0, 0);
  SH<HINSTANCE__ *,SH_HMODULE>::Reset(&v27);
  if ( !v10 )
  {
    v27 = 0;
    goto LABEL_3;
  }
  v27 = v10;
  v3 = GetProcAddress(v10, "SLConsumeWindowsRight");
  if ( !v3 )
    goto LABEL_3;
  WindowsPKeyInfo = ((__int64 (__fastcall *)(void **))ProcAddress)(&v25);
  v7 = WindowsPKeyInfo;
  if ( WindowsPKeyInfo < 0 )
    goto LABEL_49;
  InstallLicensesInOobe(v25, Library);
  if ( !Src )
  {
    v11 = ReadProductKeyFromRegistry(1, &Srca);
    v7 = v11;
    if ( v11 == -2147024894 )
    {
      v11 = ReadProductKeyFromRegistry(0, &Srca);
      v7 = v11;
    }
    if ( v11 < 0
      || (v11 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(Srca), v7 = v11, v11 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v11);
LABEL_54:
      ((void (__fastcall *)(_QWORD))v3)(0);
      goto LABEL_55;
    }
    v12 = v24;
    v13 = v24;
    v14 = (char *)((char *)L"BBBBB-BBBBB-BBBBB-BBBBB-BBBBB" - (char *)v24);
    do
    {
      v15 = *(unsigned __int16 *)&v14[(_QWORD)v13];
      v16 = *v13 - (_DWORD)v15;
      if ( v16 )
        break;
      ++v13;
    }
    while ( (_DWORD)v15 );
    if ( !v16 )
    {
      v7 = 0;
      goto LABEL_54;
    }
LABEL_27:
    WindowsPKeyInfo = GetWindowsPKeyInfo(v12, v15, (__int64)v14, v32);
    v7 = WindowsPKeyInfo;
    if ( WindowsPKeyInfo < 0 )
      goto LABEL_49;
    if ( !(unsigned int)_o__wcsicmp(v36, L"Volume:CSVLK") )
    {
      v7 = -1073418220;
      goto LABEL_30;
    }
    v19 = -1;
    do
      ++v19;
    while ( *(&v33 + v19) );
    v20 = 2147942487LL;
    if ( v19 == 38 )
    {
      if ( v33 == 123 && v35 == 125 )
      {
        v21 = (__int16 *)&v34;
LABEL_37:
        v22 = CMiscHelpersT<CEmptyType>::DecodeGuid(v21, &v30);
        v7 = v22;
        if ( v22 >= 0 )
          goto LABEL_43;
        v20 = (unsigned int)v22;
LABEL_42:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v20);
LABEL_43:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
        if ( v7 == -2147024809 )
        {
          v7 = -1073422330;
        }
        else if ( v7 >= 0 )
        {
          goto LABEL_47;
        }
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v7);
LABEL_47:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
        if ( v7 >= 0 )
        {
          WindowsPKeyInfo = ((__int64 (__fastcall *)(void *, const GUID *, __int128 *, const wchar_t *, _WORD *, _DWORD, _QWORD, __int128 *))v9)(
                              v25,
                              &WINDOWS_SLID,
                              &v30,
                              L"msft:rm/algorithm/pkey/detect",
                              v12,
                              0,
                              0,
                              &v31);
          v7 = WindowsPKeyInfo;
          if ( WindowsPKeyInfo >= 0 )
            goto LABEL_51;
          goto LABEL_49;
        }
LABEL_30:
        v18 = (unsigned int)v7;
LABEL_50:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v18);
LABEL_51:
        if ( Src && v7 < 0 || !v3 )
          goto LABEL_55;
        goto LABEL_54;
      }
    }
    else if ( v19 == 36 )
    {
      v21 = &v33;
      goto LABEL_37;
    }
    v7 = -2147024809;
    goto LABEL_42;
  }
  v17 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(Src);
  v7 = v17;
  if ( v17 >= 0 )
  {
    v12 = v24;
    goto LABEL_27;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v17);
LABEL_55:
  if ( v25 && v2 )
    v2();
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  SH<HINSTANCE__ *,SH_HMODULE>::Reset(&v26);
  SH<HINSTANCE__ *,SH_HMODULE>::Reset(&v27);
  SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v29);
  SH<unsigned short *,SH_SSTRING>::Reset(&v24);
  SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&Srca);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800bc4cc  push    rbp
0x1800bc4ce  push    rbx
0x1800bc4cf  push    rsi
0x1800bc4d0  push    rdi
0x1800bc4d1  push    r12
0x1800bc4d3  push    r13
0x1800bc4d5  push    r14
0x1800bc4d7  push    r15
0x1800bc4d9  lea     rbp, [rsp-4B8h]
0x1800bc4e1  sub     rsp, 5B8h
0x1800bc4e8  mov     rax, cs:__security_cookie
0x1800bc4ef  xor     rax, rsp
0x1800bc4f2  mov     [rbp+4F0h+var_50], rax
0x1800bc4f9  mov     r12, rcx
0x1800bc4fc  xor     esi, esi
0x1800bc4fe  lea     rcx, [rbp+4F0h+var_550]; void *
0x1800bc502  mov     [rsp+5F0h+Src], rsi
0x1800bc507  xor     edx, edx; Val
0x1800bc509  mov     [rsp+5F0h+var_5A0], rsi
0x1800bc50e  mov     r8d, 4F8h; Size
0x1800bc514  call    memset_0
0x1800bc519  xorps   xmm0, xmm0
0x1800bc51c  mov     [rsp+5F0h+var_578], rsi
0x1800bc521  xorps   xmm1, xmm1
0x1800bc524  mov     [rsp+5F0h+var_588], rsi
0x1800bc529  xor     r8d, r8d; dwFlags
0x1800bc52c  mov     [rsp+5F0h+var_590], rsi
0x1800bc531  xor     edx, edx; hFile
0x1800bc533  mov     [rsp+5F0h+var_598], rsi
0x1800bc538  lea     rcx, aSppcDll
0x1800bc53f  mov     r15d, esi
0x1800bc542  movups  [rbp+4F0h+var_560], xmm0
0x1800bc546  mov     r14d, esi
0x1800bc549  movups  [rbp+4F0h+var_570], xmm1
0x1800bc54d  call    cs:__imp_LoadLibraryExW
0x1800bc553  lea     rcx, [rsp+5F0h+var_590]
0x1800bc558  mov     rdi, rax
0x1800bc55b  call    ?Reset@?$SH@PEAUHINSTANCE__@@VSH_HMODULE@@@@QEAAXXZ
0x1800bc560  test    rdi, rdi
0x1800bc563  jnz     short loc_1800BC57E
0x1800bc565  mov     [rsp+5F0h+var_590], rsi
0x1800bc56a  call    cs:__imp_GetLastError
0x1800bc570  mov     ecx, eax; unsigned int
0x1800bc572  call    ?C_LR2HR@SErrorConverter@@SAJK@Z
0x1800bc577  mov     ebx, eax
0x1800bc579  jmp     loc_1800BC80D
0x1800bc57e  lea     rdx, aSlopen
0x1800bc585  mov     [rsp+5F0h+var_590], rdi
0x1800bc58a  mov     rcx, rdi; hModule
0x1800bc58d  call    cs:__imp_GetProcAddress
0x1800bc593  mov     rsi, rax
0x1800bc596  test    rax, rax
0x1800bc599  jz      short loc_1800BC56A
0x1800bc59b  lea     rdx, aSlclose
0x1800bc5a2  mov     rcx, rdi; hModule
0x1800bc5a5  call    cs:__imp_GetProcAddress
0x1800bc5ab  mov     r15, rax
0x1800bc5ae  test    rax, rax
0x1800bc5b1  jz      short loc_1800BC56A
0x1800bc5b3  lea     rdx, aSlinstallproof
0x1800bc5ba  mov     rcx, rdi; hModule
0x1800bc5bd  call    cs:__imp_GetProcAddress
0x1800bc5c3  mov     r13, rax
0x1800bc5c6  test    rax, rax
0x1800bc5c9  jz      short loc_1800BC56A
0x1800bc5cb  lea     rdx, aSlgetpkeyid
0x1800bc5d2  mov     rcx, rdi; hModule
0x1800bc5d5  call    cs:__imp_GetProcAddress
0x1800bc5db  test    rax, rax
0x1800bc5de  jz      short loc_1800BC56A
0x1800bc5e0  lea     rdx, aSlfireevent
0x1800bc5e7  mov     rcx, rdi; hModule
0x1800bc5ea  call    cs:__imp_GetProcAddress
0x1800bc5f0  test    rax, rax
0x1800bc5f3  jz      loc_1800BC56A
0x1800bc5f9  xor     r8d, r8d; dwFlags
0x1800bc5fc  lea     rcx, aSlcDll
0x1800bc603  xor     edx, edx; hFile
0x1800bc605  call    cs:__imp_LoadLibraryExW
0x1800bc60b  lea     rcx, [rsp+5F0h+var_588]
0x1800bc610  mov     rbx, rax
0x1800bc613  call    ?Reset@?$SH@PEAUHINSTANCE__@@VSH_HMODULE@@@@QEAAXXZ
0x1800bc618  test    rbx, rbx
0x1800bc61b  jnz     short loc_1800BC629
0x1800bc61d  xor     esi, esi
0x1800bc61f  mov     [rsp+5F0h+var_588], rsi
0x1800bc624  jmp     loc_1800BC56A
0x1800bc629  lea     rdx, aSlconsumewindo
0x1800bc630  mov     [rsp+5F0h+var_588], rbx
0x1800bc635  mov     rcx, rbx; hModule
0x1800bc638  call    cs:__imp_GetProcAddress
0x1800bc63e  mov     r14, rax
0x1800bc641  test    rax, rax
0x1800bc644  jz      loc_1800BC56A
0x1800bc64a  lea     rcx, [rsp+5F0h+var_598]
0x1800bc64f  mov     rax, rsi
0x1800bc652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc657  xor     esi, esi
0x1800bc659  mov     ebx, eax
0x1800bc65b  test    eax, eax
0x1800bc65d  js      loc_1800BC80D
0x1800bc663  mov     rcx, [rsp+5F0h+var_598]; void *
0x1800bc668  mov     rdx, rdi; HINSTANCE
0x1800bc66b  call    ?InstallLicensesInOobe@@YAJPEAXPEAUHINSTANCE__@@@Z
0x1800bc670  test    r12, r12
0x1800bc673  jnz     short loc_1800BC6EF
0x1800bc675  lea     rdx, [rsp+5F0h+Src]
0x1800bc67a  lea     ecx, [rsi+1]
0x1800bc67d  call    ?ReadProductKeyFromRegistry@@YAJW4PKEY_LOCATION@@PEAPEAG@Z
0x1800bc682  mov     ebx, eax
0x1800bc684  cmp     eax, 80070002h
0x1800bc689  jnz     short loc_1800BC699
0x1800bc68b  lea     rdx, [rsp+5F0h+Src]
0x1800bc690  xor     ecx, ecx
0x1800bc692  call    ?ReadProductKeyFromRegistry@@YAJW4PKEY_LOCATION@@PEAPEAG@Z
0x1800bc697  mov     ebx, eax
0x1800bc699  test    eax, eax
0x1800bc69b  jns     short loc_1800BC6A9
0x1800bc69d  mov     ecx, eax
0x1800bc69f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z
0x1800bc6a4  jmp     loc_1800BC822
0x1800bc6a9  mov     rcx, [rsp+5F0h+Src]; Src
0x1800bc6ae  lea     rdx, [rsp+5F0h+var_5A0]
0x1800bc6b3  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z
0x1800bc6b8  mov     ebx, eax
0x1800bc6ba  test    eax, eax
0x1800bc6bc  js      short loc_1800BC69D
0x1800bc6be  mov     rdi, [rsp+5F0h+var_5A0]
0x1800bc6c3  lea     r8, aBbbbbBbbbbBbbb
0x1800bc6ca  mov     rax, rdi
0x1800bc6cd  sub     r8, rdi
0x1800bc6d0  movzx   ecx, word ptr [rax]
0x1800bc6d3  movzx   edx, word ptr [rax+r8]
0x1800bc6d8  sub     ecx, edx
0x1800bc6da  jnz     short loc_1800BC6E4
0x1800bc6dc  add     rax, 2
0x1800bc6e0  test    edx, edx
0x1800bc6e2  jnz     short loc_1800BC6D0
0x1800bc6e4  test    ecx, ecx
0x1800bc6e6  jnz     short loc_1800BC713
0x1800bc6e8  mov     ebx, esi
0x1800bc6ea  jmp     loc_1800BC822
0x1800bc6ef  lea     rdx, [rsp+5F0h+var_5A0]
0x1800bc6f4  mov     rcx, r12; Src
0x1800bc6f7  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z
0x1800bc6fc  mov     ebx, eax
0x1800bc6fe  test    eax, eax
0x1800bc700  jns     short loc_1800BC70E
0x1800bc702  mov     ecx, eax
0x1800bc704  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z
0x1800bc709  jmp     loc_1800BC82C
0x1800bc70e  mov     rdi, [rsp+5F0h+var_5A0]
0x1800bc713  lea     r9, [rbp+4F0h+var_550]
0x1800bc717  mov     rcx, rdi
0x1800bc71a  call    GetWindowsPKeyInfo
0x1800bc71f  mov     ebx, eax
0x1800bc721  test    eax, eax
0x1800bc723  js      loc_1800BC80D
0x1800bc729  lea     rdx, aVolumeCsvlk
0x1800bc730  lea     rcx, [rbp+4F0h+var_158]
0x1800bc737  call    cs:__imp__o__wcsicmp
0x1800bc73d  test    eax, eax
0x1800bc73f  jnz     short loc_1800BC74D
0x1800bc741  mov     ebx, 0C004F014h
0x1800bc746  mov     ecx, ebx
0x1800bc748  jmp     loc_1800BC80F
0x1800bc74d  lea     rcx, [rbp+4F0h+var_4C8]
0x1800bc751  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bc755  inc     rax
0x1800bc758  cmp     [rcx+rax*2], si
0x1800bc75c  jnz     short loc_1800BC755
0x1800bc75e  mov     ecx, 80070057h
0x1800bc763  cmp     rax, 26h ; '&'
0x1800bc767  jnz     short loc_1800BC78E
0x1800bc769  cmp     [rbp+4F0h+var_4C8], 7Bh ; '{'
0x1800bc76e  jnz     short loc_1800BC79A
0x1800bc770  cmp     [rbp+4F0h+var_47E], 7Dh ; '}'
0x1800bc775  jnz     short loc_1800BC79A
0x1800bc777  lea     rcx, [rbp+4F0h+var_4C6]
0x1800bc77b  lea     rdx, [rbp+4F0h+var_570]
0x1800bc77f  call    ?DecodeGuid@?$CMiscHelpersT@VCEmptyType@@@@CAJPEBGPEAU_GUID@@@Z
0x1800bc784  mov     ebx, eax
0x1800bc786  test    eax, eax
0x1800bc788  jns     short loc_1800BC7A1
0x1800bc78a  mov     ecx, eax
0x1800bc78c  jmp     short loc_1800BC79C
0x1800bc78e  cmp     rax, 24h ; '$'
0x1800bc792  jnz     short loc_1800BC79A
0x1800bc794  lea     rcx, [rbp+4F0h+var_4C8]
0x1800bc798  jmp     short loc_1800BC77B
0x1800bc79a  mov     ebx, ecx
0x1800bc79c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z
0x1800bc7a1  mov     ecx, ebx
0x1800bc7a3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z
0x1800bc7a8  cmp     ebx, 80070057h
0x1800bc7ae  jnz     short loc_1800BC7B7
0x1800bc7b0  mov     ebx, 0C004E006h
0x1800bc7b5  jmp     short loc_1800BC7BB
0x1800bc7b7  test    ebx, ebx
0x1800bc7b9  jns     short loc_1800BC7C2
0x1800bc7bb  mov     ecx, ebx
0x1800bc7bd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z
0x1800bc7c2  mov     ecx, ebx
0x1800bc7c4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z
0x1800bc7c9  test    ebx, ebx
0x1800bc7cb  js      loc_1800BC746
0x1800bc7d1  mov     rcx, [rsp+5F0h+var_598]
0x1800bc7d6  lea     rax, [rbp+4F0h+var_560]
0x1800bc7da  mov     [rsp+5F0h+var_5B8], rax
0x1800bc7df  lea     r9, aMsftRmAlgorith
0x1800bc7e6  mov     [rsp+5F0h+var_5C0], rsi
0x1800bc7eb  lea     r8, [rbp+4F0h+var_570]
0x1800bc7ef  mov     [rsp+5F0h+var_5C8], esi
0x1800bc7f3  lea     rdx, WINDOWS_SLID
0x1800bc7fa  mov     rax, r13
0x1800bc7fd  mov     [rsp+5F0h+var_5D0], rdi
0x1800bc802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc807  mov     ebx, eax
0x1800bc809  test    eax, eax
0x1800bc80b  jns     short loc_1800BC814
0x1800bc80d  mov     ecx, eax
0x1800bc80f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z
0x1800bc814  test    r12, r12
0x1800bc817  jz      short loc_1800BC81D
0x1800bc819  test    ebx, ebx
0x1800bc81b  js      short loc_1800BC82C
0x1800bc81d  test    r14, r14
0x1800bc820  jz      short loc_1800BC82C
0x1800bc822  xor     ecx, ecx
0x1800bc824  mov     rax, r14
0x1800bc827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc82c  mov     rcx, [rsp+5F0h+var_598]
0x1800bc831  test    rcx, rcx
0x1800bc834  jz      short loc_1800BC843
0x1800bc836  test    r15, r15
0x1800bc839  jz      short loc_1800BC843
0x1800bc83b  mov     rax, r15
0x1800bc83e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc843  mov     ecx, ebx
0x1800bc845  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z
0x1800bc84a  lea     rcx, [rsp+5F0h+var_590]
0x1800bc84f  call    ?Reset@?$SH@PEAUHINSTANCE__@@VSH_HMODULE@@@@QEAAXXZ
0x1800bc854  lea     rcx, [rsp+5F0h+var_588]
0x1800bc859  call    ?Reset@?$SH@PEAUHINSTANCE__@@VSH_HMODULE@@@@QEAAXXZ
0x1800bc85e  lea     rcx, [rsp+5F0h+var_578]
0x1800bc863  call    ?Reset@?$SP@EV?$SP_HLOCAL@E@@@@QEAAXXZ
0x1800bc868  lea     rcx, [rsp+5F0h+var_5A0]
0x1800bc86d  call    ?Reset@?$SH@PEAGVSH_SSTRING@@@@QEAAXXZ
0x1800bc872  lea     rcx, [rsp+5F0h+Src]
0x1800bc877  call    ?Reset@?$SP@EV?$SP_HLOCAL@E@@@@QEAAXXZ
0x1800bc87c  mov     eax, ebx
0x1800bc87e  mov     rcx, [rbp+4F0h+var_50]
0x1800bc885  xor     rcx, rsp; StackCookie
0x1800bc888  call    __security_check_cookie
0x1800bc88d  add     rsp, 5B8h
0x1800bc894  pop     r15
0x1800bc896  pop     r14
0x1800bc898  pop     r13
0x1800bc89a  pop     r12
0x1800bc89c  pop     rdi
0x1800bc89d  pop     rsi
0x1800bc89e  pop     rbx
0x1800bc89f  pop     rbp
0x1800bc8a0  retn
```
