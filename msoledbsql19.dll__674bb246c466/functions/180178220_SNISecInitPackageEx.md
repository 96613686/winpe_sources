# SNISecInitPackageEx

- ea: `0x180178220`
- end: `0x1801788cb`
- name: `SNISecInitPackageEx`
- size: `1707`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180178190`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x180157620`
- `0x18015a6f0`
- `0x18015a880`
- `0x180178220`
- `0x180182ee0`
- `0x1801832e0`
- `0x1801a65f0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1801787c7`
- `KERNEL32!FreeLibrary` at `0x1801787c7`
- `KERNEL32!GetLastError` at `0x1801783ae`
- `KERNEL32!GetLastError` at `0x180178409`
- `KERNEL32!GetLastError` at `0x1801783ae`
- `KERNEL32!GetLastError` at `0x180178409`
- `KERNEL32!GetProcAddress` at `0x1801783a3`
- `KERNEL32!GetProcAddress` at `0x1801783a3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801784da`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801784ee`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801785cc`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801785e0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801786b7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801786cb`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801784da`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801784ee`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801785cc`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801785e0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801786b7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801786cb`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1801784fa`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1801785ec`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1801786d7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1801784fa`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1801785ec`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1801786d7`

## string_xrefs

- `0x18017833b`: `secur32.dll`
- `0x180178399`: `InitSecurityInterfaceW`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SNISecInitPackageEx(_DWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  struct CCriticalSectionNT_SNI *v5; // rbp
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  HMODULE v9; // rax
  DWORD LastError; // edi
  unsigned int v11; // ebx
  wchar_t *v12; // r8
  __int64 v13; // rdx
  char *v14; // rcx
  __int64 (*ProcAddress)(void); // rax
  char v16; // bl
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  unsigned int v22; // eax
  __int64 v24; // [rsp+30h] [rbp-28h] BYREF
  __int64 v25; // [rsp+38h] [rbp-20h] BYREF

  v25 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266D40[0] )
    bidScopeEnterW(&v25, off_180266D40[0], a1, a4);
  v24 = 0;
  qword_180253A38 = -1;
  ghSspiCred.dwLower = -1;
  v5 = g_csSecPackageInitialize;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)g_csSecPackageInitialize + 2) + 32LL) + 8LL))(*((_QWORD *)g_csSecPackageInitialize + 2) + 32LL);
  if ( _InterlockedIncrement(&g_cSNISecPackageInitialized) != 1 )
  {
    *a1 = g_cbSspiMaxToken;
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265158[0] )
      bidTraceW(off_180261E10[0], 269312, off_180265158[0], 0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v5 + 2) + 32LL) + 24LL))(*((_QWORD *)v5 + 2) + 32LL);
LABEL_81:
    LastError = 0;
    goto LABEL_82;
  }
  *a1 = 0;
  v9 = SNILoadSystemLibA("secur32.dll", v6, v7, v8);
  g_hSspiLib = v9;
  if ( !v9 )
  {
    LastError = -1;
    v11 = 50122;
    if ( (bidGblFlags & 2) == 0 || !off_180265160[0] )
      goto LABEL_68;
    SniErrorIdFromStringId(0xC3CAu);
    v12 = off_180265160[0];
    v13 = 289792;
    v14 = off_180261E18[0];
    goto LABEL_67;
  }
  ProcAddress = GetProcAddress(v9, "InitSecurityInterfaceW");
  if ( !ProcAddress )
  {
    LastError = GetLastError();
    v11 = 50100;
    if ( (bidGblFlags & 2) == 0 || !off_180265168[0] )
      goto LABEL_68;
    SniErrorIdFromStringId(0xC3B4u);
    v12 = off_180265168[0];
    v13 = 304128;
    v14 = off_180261E20[0];
    goto LABEL_67;
  }
  g_pFuncs = (struct _SECURITY_FUNCTION_TABLE_W *)ProcAddress();
  if ( !g_pFuncs )
  {
    LastError = GetLastError();
    v11 = 50100;
    if ( (bidGblFlags & 2) == 0 || !off_180265170[0] )
      goto LABEL_68;
    SniErrorIdFromStringId(0xC3B4u);
    v12 = off_180265170[0];
    v13 = 316416;
    v14 = off_180261E28[0];
    goto LABEL_67;
  }
  v16 = 0;
  _mm_lfence();
  if ( !((unsigned int (__fastcall *)(void *, __int64 *))g_pFuncs->QuerySecurityPackageInfoW)(g_rgszSSP, &v24) )
  {
    LODWORD(g_rgfSSPIPackageAvailable) = 1;
    if ( (_DWORD)g_rgcchSSP )
    {
      if ( !g_rgszSSP || (unsigned __int64)(int)g_rgcchSSP > 0x28 )
      {
        *(_OWORD *)&g_szSSP = 0;
        xmmword_180253A08 = 0;
        qword_180253A18 = 0;
        if ( g_rgszSSP )
        {
          if ( (unsigned __int64)(int)g_rgcchSSP <= 0x28 )
            goto LABEL_31;
          *_errno() = 34;
        }
        else
        {
          *_errno() = 22;
        }
        _invalid_parameter_noinfo();
        goto LABEL_31;
      }
      memcpy_0(&g_szSSP, g_rgszSSP, (int)g_rgcchSSP);
    }
LABEL_31:
    g_cbSspiMaxToken = *(_DWORD *)(v24 + 8);
    v16 = 1;
    if ( *(_DWORD *)(v24 + 8) > g_cbSspiMaxToken )
      g_cbSspiMaxToken = *(_DWORD *)(v24 + 8);
    ((void (*)(void))g_pFuncs->FreeContextBuffer)();
  }
  if ( ((unsigned int (__fastcall *)(void *, __int64 *))g_pFuncs->QuerySecurityPackageInfoW)(Src, &v24) )
    goto LABEL_47;
  dword_180253A24 = 1;
  if ( !v16 )
  {
    if ( dword_18024E164 )
    {
      if ( Src && (unsigned __int64)dword_18024E164 <= 0x28 )
      {
        memcpy_0(&g_szSSP, Src, dword_18024E164);
        g_cbSspiMaxToken = *(_DWORD *)(v24 + 8);
        v16 = 1;
        goto LABEL_46;
      }
      *(_OWORD *)&g_szSSP = 0;
      xmmword_180253A08 = 0;
      qword_180253A18 = 0;
      if ( !Src )
      {
        *_errno() = 22;
LABEL_44:
        _invalid_parameter_noinfo();
        goto LABEL_45;
      }
      if ( (unsigned __int64)dword_18024E164 > 0x28 )
      {
        *_errno() = 34;
        goto LABEL_44;
      }
    }
LABEL_45:
    g_cbSspiMaxToken = *(_DWORD *)(v24 + 8);
    v16 = 1;
  }
LABEL_46:
  ((void (*)(void))g_pFuncs->FreeContextBuffer)();
LABEL_47:
  LastError = ((__int64 (__fastcall *)(void *, __int64 *))g_pFuncs->QuerySecurityPackageInfoW)(off_18024E158, &v24);
  if ( LastError )
    goto LABEL_63;
  dword_180253A28 = 1;
  if ( v16 )
  {
    v21 = v24;
    v22 = g_cbSspiMaxToken;
    goto LABEL_60;
  }
  if ( !dword_18024E168 )
    goto LABEL_58;
  if ( !off_18024E158 || (unsigned __int64)dword_18024E168 > 0x28 )
  {
    *(_OWORD *)&g_szSSP = 0;
    xmmword_180253A08 = 0;
    qword_180253A18 = 0;
    if ( off_18024E158 )
    {
      if ( (unsigned __int64)dword_18024E168 <= 0x28 )
      {
LABEL_58:
        v21 = v24;
        v22 = *(_DWORD *)(v24 + 8);
        g_cbSspiMaxToken = v22;
        v16 = 1;
        goto LABEL_60;
      }
      *_errno() = 34;
    }
    else
    {
      *_errno() = 22;
    }
    _invalid_parameter_noinfo();
    goto LABEL_58;
  }
  memcpy_0(&g_szSSP, off_18024E158, dword_18024E168);
  v21 = v24;
  v22 = *(_DWORD *)(v24 + 8);
  g_cbSspiMaxToken = v22;
  v16 = 1;
LABEL_60:
  if ( *(_DWORD *)(v21 + 8) > v22 )
    g_cbSspiMaxToken = *(_DWORD *)(v21 + 8);
  ((void (*)(void))g_pFuncs->FreeContextBuffer)();
LABEL_63:
  if ( v16 )
  {
    if ( !(unsigned int)SNI_Spn::SpnInit(v18, v17, v19, v20) )
      g_fSPNInitialized = 1;
    *a1 = g_cbSspiMaxToken;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v5 + 2) + 32LL) + 24LL))(*((_QWORD *)v5 + 2) + 32LL);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265180[0] )
      bidTraceW(off_180261E38[0], 384000, off_180265180[0], 0);
    goto LABEL_81;
  }
  v11 = 50100;
  if ( (bidGblFlags & 2) != 0 && off_180265178[0] )
  {
    SniErrorIdFromStringId(0xC3B4u);
    v12 = off_180265178[0];
    v13 = 362496;
    v14 = off_180261E30[0];
LABEL_67:
    bidTraceW(v14, v13, v12, 8);
  }
LABEL_68:
  SNISetLastError(8, LastError, v11);
  if ( ghSspiCred.dwLower != -1 && qword_180253A38 != -1 )
  {
    ((void (__fastcall *)(struct _SecHandle *))g_pFuncs->FreeCredentialsHandle)(&ghSspiCred);
    qword_180253A38 = -1;
    ghSspiCred.dwLower = -1;
  }
  if ( g_hSspiLib )
    FreeLibrary(g_hSspiLib);
  SNI_Spn::SpnTerminate();
  _InterlockedDecrement(&g_cSNISecPackageInitialized);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v5 + 2) + 32LL) + 24LL))(*((_QWORD *)v5 + 2) + 32LL);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265188[0] )
    bidTraceW(off_180261E40[0], 409600, off_180265188[0], LastError);
LABEL_82:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v25);
  return LastError;
}

```

## disassembly

```asm
0x180178220  mov     [rsp+arg_8], rbx
0x180178225  mov     [rsp+arg_10], rbp
0x18017822a  mov     [rsp+arg_18], rsi
0x18017822f  push    rdi
0x180178230  sub     rsp, 50h
0x180178234  mov     rax, cs:__security_cookie
0x18017823b  xor     rax, rsp
0x18017823e  mov     [rsp+58h+var_18], rax
0x180178243  mov     rsi, rcx
0x180178246  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFFh
0x18017824f  mov     eax, cs:_bidGblFlags
0x180178255  and     eax, 20004h
0x18017825a  cmp     eax, 20004h
0x18017825f  jnz     short loc_180178281
0x180178261  mov     rax, cs:off_180266D40; "<SNISecInitPackageEx|API|SNI> pcbMaxTok"...
0x180178268  test    rax, rax
0x18017826b  jz      short loc_180178281
0x18017826d  mov     r8, rcx
0x180178270  mov     rdx, cs:off_180266D40; "<SNISecInitPackageEx|API|SNI> pcbMaxTok"...
0x180178277  lea     rcx, [rsp+58h+var_20]
0x18017827c  call    _bidScopeEnterW
0x180178281  mov     [rsp+58h+var_28], 0
0x18017828a  mov     cs:qword_180253A38, 0FFFFFFFFFFFFFFFFh
0x180178295  mov     cs:?ghSspiCred@@3U_SecHandle@@A, 0FFFFFFFFFFFFFFFFh; _SecHandle ghSspiCred
0x1801782a0  mov     rbp, cs:?g_csSecPackageInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_csSecPackageInitialize
0x1801782a7  mov     rcx, [rbp+10h]
0x1801782ab  add     rcx, 20h ; ' '
0x1801782af  mov     rax, [rcx]
0x1801782b2  mov     rax, [rax+8]
0x1801782b6  call    cs:__guard_dispatch_icall_fptr
0x1801782bc  mov     eax, 1
0x1801782c1  lock xadd cs:?g_cSNISecPackageInitialized@@3JA, eax; long g_cSNISecPackageInitialized
0x1801782c9  inc     eax
0x1801782cb  cmp     eax, 1
0x1801782ce  jz      short loc_180178335
0x1801782d0  mov     eax, cs:?g_cbSspiMaxToken@@3KA; ulong g_cbSspiMaxToken
0x1801782d6  mov     [rsi], eax
0x1801782d8  mov     eax, cs:_bidGblFlags
0x1801782de  and     eax, 20002h
0x1801782e3  cmp     eax, 20002h
0x1801782e8  jnz     short loc_18017831B
0x1801782ea  mov     rax, cs:off_180265158; "<SNISecInitPackageEx|RET|SNI> %d{WINERR"...
0x1801782f1  test    rax, rax
0x1801782f4  jz      short loc_18017831B
0x1801782f6  mov     eax, cs:?g_cSNISecPackageInitialized@@3JA; long g_cSNISecPackageInitialized
0x1801782fc  mov     [rsp+58h+var_38], eax
0x180178300  xor     r9d, r9d
0x180178303  mov     r8, cs:off_180265158; "<SNISecInitPackageEx|RET|SNI> %d{WINERR"...
0x18017830a  mov     edx, 41C00h
0x18017830f  mov     rcx, cs:off_180261E10; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180178316  call    _bidTraceW
0x18017831b  mov     rcx, [rbp+10h]
0x18017831f  add     rcx, 20h ; ' '
0x180178323  mov     rax, [rcx]
0x180178326  mov     rax, [rax+18h]
0x18017832a  call    cs:__guard_dispatch_icall_fptr
0x180178330  jmp     loc_18017889A
0x180178335  mov     dword ptr [rsi], 0
0x18017833b  lea     rcx, aSecur32Dll; "secur32.dll"
0x180178342  call    SNILoadSystemLibA
0x180178347  mov     cs:?g_hSspiLib@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hSspiLib
0x18017834e  test    rax, rax
0x180178351  jnz     short loc_180178399
0x180178353  mov     edi, 0FFFFFFFFh
0x180178358  mov     ebx, 0C3CAh
0x18017835d  test    byte ptr cs:_bidGblFlags, 2
0x180178364  jz      loc_18017876A
0x18017836a  mov     rax, cs:off_180265160; "<SNISecInitPackageEx|ERR|SNI> ProviderN"...
0x180178371  test    rax, rax
0x180178374  jz      loc_18017876A
0x18017837a  mov     ecx, ebx; unsigned int
0x18017837c  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x180178381  mov     r8, cs:off_180265160; "<SNISecInitPackageEx|ERR|SNI> ProviderN"...
0x180178388  mov     edx, 46C00h
0x18017838d  mov     rcx, cs:off_180261E18; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180178394  jmp     loc_180178757
0x180178399  lea     rdx, aInitsecurityin; "InitSecurityInterfaceW"
0x1801783a0  mov     rcx, rax; hModule
0x1801783a3  call    cs:__imp_GetProcAddress
0x1801783a9  test    rax, rax
0x1801783ac  jnz     short loc_1801783F7
0x1801783ae  call    cs:__imp_GetLastError
0x1801783b4  mov     edi, eax
0x1801783b6  mov     ebx, 0C3B4h
0x1801783bb  test    byte ptr cs:_bidGblFlags, 2
0x1801783c2  jz      loc_18017876A
0x1801783c8  mov     rax, cs:off_180265168; "<SNISecInitPackageEx|ERR|SNI> ProviderN"...
0x1801783cf  test    rax, rax
0x1801783d2  jz      loc_18017876A
0x1801783d8  mov     ecx, ebx; unsigned int
0x1801783da  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1801783df  mov     r8, cs:off_180265168; "<SNISecInitPackageEx|ERR|SNI> ProviderN"...
0x1801783e6  mov     edx, 4A400h
0x1801783eb  mov     rcx, cs:off_180261E20; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801783f2  jmp     loc_180178757
0x1801783f7  call    cs:__guard_dispatch_icall_fptr
0x1801783fd  mov     cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA, rax; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x180178404  test    rax, rax
0x180178407  jnz     short loc_180178452
0x180178409  call    cs:__imp_GetLastError
0x18017840f  mov     edi, eax
0x180178411  mov     ebx, 0C3B4h
0x180178416  test    byte ptr cs:_bidGblFlags, 2
0x18017841d  jz      loc_18017876A
0x180178423  mov     rax, cs:off_180265170; "<SNISecInitPackageEx|ERR|SNI> ProviderN"...
0x18017842a  test    rax, rax
0x18017842d  jz      loc_18017876A
0x180178433  mov     ecx, ebx; unsigned int
0x180178435  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18017843a  mov     r8, cs:off_180265170; "<SNISecInitPackageEx|ERR|SNI> ProviderN"...
0x180178441  mov     edx, 4D400h
0x180178446  mov     rcx, cs:off_180261E28; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017844d  jmp     loc_180178757
0x180178452  xor     bl, bl
0x180178454  lfence
0x180178457  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x18017845e  lea     rdx, [rsp+58h+var_28]
0x180178463  mov     rcx, cs:?g_rgszSSP@@3PAPEA_WA; wchar_t * near * g_rgszSSP
0x18017846a  mov     rax, [rax+88h]
0x180178471  call    cs:__guard_dispatch_icall_fptr
0x180178477  test    eax, eax
0x180178479  jnz     loc_180178531
0x18017847f  mov     cs:?g_rgfSSPIPackageAvailable@@3PAHA, 1; int near * g_rgfSSPIPackageAvailable
0x180178489  movsxd  rax, cs:?g_rgcchSSP@@3PAHA; int near * g_rgcchSSP
0x180178490  mov     rcx, cs:?g_rgszSSP@@3PAPEA_WA; wchar_t * near * g_rgszSSP
0x180178497  test    rax, rax
0x18017849a  jz      short loc_180178500
0x18017849c  test    rcx, rcx
0x18017849f  jz      short loc_1801784BB
0x1801784a1  cmp     rax, 28h ; '('
0x1801784a5  ja      short loc_1801784BB
0x1801784a7  mov     r8, rax; Size
0x1801784aa  mov     rdx, rcx; Src
0x1801784ad  lea     rcx, ?g_szSSP@@3PA_WA; void *
0x1801784b4  call    memcpy_0
0x1801784b9  jmp     short loc_180178500
0x1801784bb  xorps   xmm0, xmm0
0x1801784be  xor     edx, edx
0x1801784c0  movups  cs:?g_szSSP@@3PA_WA, xmm0; wchar_t near * g_szSSP
0x1801784c7  movups  cs:xmmword_180253A08, xmm0
0x1801784ce  mov     cs:qword_180253A18, rdx
0x1801784d5  test    rcx, rcx
0x1801784d8  jnz     short loc_1801784E8
0x1801784da  call    cs:__imp__errno
0x1801784e0  mov     dword ptr [rax], 16h
0x1801784e6  jmp     short loc_1801784FA
0x1801784e8  cmp     rax, 28h ; '('
0x1801784ec  jbe     short loc_180178500
0x1801784ee  call    cs:__imp__errno
0x1801784f4  mov     dword ptr [rax], 22h ; '"'
0x1801784fa  call    cs:__imp__invalid_parameter_noinfo
0x180178500  mov     rcx, [rsp+58h+var_28]
0x180178505  mov     eax, [rcx+8]
0x180178508  mov     cs:?g_cbSspiMaxToken@@3KA, eax; ulong g_cbSspiMaxToken
0x18017850e  mov     bl, 1
0x180178510  mov     edx, [rcx+8]
0x180178513  cmp     edx, eax
0x180178515  jbe     short loc_18017851D
0x180178517  mov     cs:?g_cbSspiMaxToken@@3KA, edx; ulong g_cbSspiMaxToken
0x18017851d  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x180178524  mov     rax, [rax+80h]
0x18017852b  call    cs:__guard_dispatch_icall_fptr
0x180178531  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x180178538  lea     rdx, [rsp+58h+var_28]
0x18017853d  mov     rcx, cs:Src
0x180178544  mov     rax, [rax+88h]
0x18017854b  call    cs:__guard_dispatch_icall_fptr
0x180178551  test    eax, eax
0x180178553  jnz     loc_18017861D
0x180178559  mov     cs:dword_180253A24, 1
0x180178563  test    bl, bl
0x180178565  jnz     loc_180178604
0x18017856b  movsxd  rax, cs:dword_18024E164
0x180178572  mov     rcx, cs:Src
0x180178579  test    rax, rax
0x18017857c  jz      short loc_1801785F2
0x18017857e  test    rcx, rcx
0x180178581  jz      short loc_1801785AD
0x180178583  cmp     rax, 28h ; '('
0x180178587  ja      short loc_1801785AD
0x180178589  mov     r8, rax; Size
0x18017858c  mov     rdx, rcx; Src
0x18017858f  lea     rcx, ?g_szSSP@@3PA_WA; void *
0x180178596  call    memcpy_0
0x18017859b  mov     rcx, [rsp+58h+var_28]
0x1801785a0  mov     eax, [rcx+8]
0x1801785a3  mov     cs:?g_cbSspiMaxToken@@3KA, eax; ulong g_cbSspiMaxToken
0x1801785a9  mov     bl, 1
0x1801785ab  jmp     short loc_180178609
0x1801785ad  xorps   xmm0, xmm0
0x1801785b0  xor     edx, edx
0x1801785b2  movups  cs:?g_szSSP@@3PA_WA, xmm0; wchar_t near * g_szSSP
0x1801785b9  movups  cs:xmmword_180253A08, xmm0
0x1801785c0  mov     cs:qword_180253A18, rdx
0x1801785c7  test    rcx, rcx
0x1801785ca  jnz     short loc_1801785DA
0x1801785cc  call    cs:__imp__errno
0x1801785d2  mov     dword ptr [rax], 16h
0x1801785d8  jmp     short loc_1801785EC
0x1801785da  cmp     rax, 28h ; '('
0x1801785de  jbe     short loc_1801785F2
0x1801785e0  call    cs:__imp__errno
0x1801785e6  mov     dword ptr [rax], 22h ; '"'
0x1801785ec  call    cs:__imp__invalid_parameter_noinfo
0x1801785f2  mov     rcx, [rsp+58h+var_28]
0x1801785f7  mov     eax, [rcx+8]
0x1801785fa  mov     cs:?g_cbSspiMaxToken@@3KA, eax; ulong g_cbSspiMaxToken
0x180178600  mov     bl, 1
0x180178602  jmp     short loc_180178609
0x180178604  mov     rcx, [rsp+58h+var_28]
0x180178609  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x180178610  mov     rax, [rax+80h]
0x180178617  call    cs:__guard_dispatch_icall_fptr
0x18017861d  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x180178624  lea     rdx, [rsp+58h+var_28]
0x180178629  mov     rcx, cs:off_18024E158; "ntlm"
0x180178630  mov     rax, [rax+88h]
0x180178637  call    cs:__guard_dispatch_icall_fptr
0x18017863d  mov     edi, eax
0x18017863f  test    eax, eax
0x180178641  jnz     loc_18017871B
0x180178647  mov     cs:dword_180253A28, 1
0x180178651  test    bl, bl
0x180178653  jnz     loc_1801786EF
0x180178659  movsxd  rax, cs:dword_18024E168
0x180178660  mov     rdx, cs:off_18024E158; Src
0x180178667  test    rax, rax
0x18017866a  jz      short loc_1801786DD
0x18017866c  test    rdx, rdx
0x18017866f  jz      short loc_180178698
0x180178671  cmp     rax, 28h ; '('
0x180178675  ja      short loc_180178698
0x180178677  mov     r8, rax; Size
0x18017867a  lea     rcx, ?g_szSSP@@3PA_WA; void *
0x180178681  call    memcpy_0
0x180178686  mov     rcx, [rsp+58h+var_28]
0x18017868b  mov     eax, [rcx+8]
0x18017868e  mov     cs:?g_cbSspiMaxToken@@3KA, eax; ulong g_cbSspiMaxToken
0x180178694  mov     bl, 1
0x180178696  jmp     short loc_1801786FA
0x180178698  xorps   xmm0, xmm0
0x18017869b  xor     ecx, ecx
0x18017869d  movups  cs:?g_szSSP@@3PA_WA, xmm0; wchar_t near * g_szSSP
0x1801786a4  movups  cs:xmmword_180253A08, xmm0
0x1801786ab  mov     cs:qword_180253A18, rcx
0x1801786b2  test    rdx, rdx
0x1801786b5  jnz     short loc_1801786C5
0x1801786b7  call    cs:__imp__errno
0x1801786bd  mov     dword ptr [rax], 16h
0x1801786c3  jmp     short loc_1801786D7
0x1801786c5  cmp     rax, 28h ; '('
0x1801786c9  jbe     short loc_1801786DD
0x1801786cb  call    cs:__imp__errno
0x1801786d1  mov     dword ptr [rax], 22h ; '"'
0x1801786d7  call    cs:__imp__invalid_parameter_noinfo
0x1801786dd  mov     rcx, [rsp+58h+var_28]
0x1801786e2  mov     eax, [rcx+8]
0x1801786e5  mov     cs:?g_cbSspiMaxToken@@3KA, eax; ulong g_cbSspiMaxToken
0x1801786eb  mov     bl, 1
0x1801786ed  jmp     short loc_1801786FA
0x1801786ef  mov     rcx, [rsp+58h+var_28]
0x1801786f4  mov     eax, cs:?g_cbSspiMaxToken@@3KA; ulong g_cbSspiMaxToken
0x1801786fa  mov     edx, [rcx+8]
0x1801786fd  cmp     edx, eax
0x1801786ff  jbe     short loc_180178707
0x180178701  mov     cs:?g_cbSspiMaxToken@@3KA, edx; ulong g_cbSspiMaxToken
0x180178707  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x18017870e  mov     rax, [rax+80h]
0x180178715  call    cs:__guard_dispatch_icall_fptr
0x18017871b  test    bl, bl
0x18017871d  jnz     loc_180178831
0x180178723  mov     ebx, 0C3B4h
0x180178728  test    byte ptr cs:_bidGblFlags, 2
0x18017872f  jz      short loc_18017876A
0x180178731  mov     rax, cs:off_180265178; "<SNISecInitPackageEx|ERR|SNI> ProviderN"...
0x180178738  test    rax, rax
0x18017873b  jz      short loc_18017876A
0x18017873d  mov     ecx, ebx; unsigned int
0x18017873f  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x180178744  mov     r8, cs:off_180265178; "<SNISecInitPackageEx|ERR|SNI> ProviderN"...
0x18017874b  mov     edx, 58800h
0x180178750  mov     rcx, cs:off_180261E30; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180178757  mov     [rsp+58h+var_30], edi
0x18017875b  mov     [rsp+58h+var_38], eax
0x18017875f  mov     r9d, 8
0x180178765  call    _bidTraceW
0x18017876a  mov     r8d, ebx
0x18017876d  mov     edx, edi
0x18017876f  mov     ecx, 8
0x180178774  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x180178779  cmp     cs:?ghSspiCred@@3U_SecHandle@@A, 0FFFFFFFFFFFFFFFFh; _SecHandle ghSspiCred
0x180178781  jz      short loc_1801787BB
0x180178783  cmp     cs:qword_180253A38, 0FFFFFFFFFFFFFFFFh
0x18017878b  jz      short loc_1801787BB
0x18017878d  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x180178794  lea     rcx, ?ghSspiCred@@3U_SecHandle@@A; _SecHandle ghSspiCred
0x18017879b  mov     rax, [rax+20h]
0x18017879f  call    cs:__guard_dispatch_icall_fptr
0x1801787a5  mov     cs:qword_180253A38, 0FFFFFFFFFFFFFFFFh
0x1801787b0  mov     cs:?ghSspiCred@@3U_SecHandle@@A, 0FFFFFFFFFFFFFFFFh; _SecHandle ghSspiCred
  ... truncated ...
```
