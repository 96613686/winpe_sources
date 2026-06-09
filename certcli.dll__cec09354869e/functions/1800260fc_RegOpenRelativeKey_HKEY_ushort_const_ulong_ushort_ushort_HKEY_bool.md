# _RegOpenRelativeKey(HKEY__ *,ushort const *,ulong,ushort * *,ushort * *,HKEY__ * *,bool *)

- ea: `0x1800260fc`
- end: `0x180026518`
- name: `?_RegOpenRelativeKey@@YAJPEAUHKEY__@@PEBGKPEAPEAG2PEAPEAU1@PEA_N@Z`
- size: `1052`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *, __int64, unsigned __int16 **, unsigned __int16 **, HKEY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002746c`

## callees

- `0x18000b940`
- `0x18000b9cc`
- `0x1800213f0`
- `0x180025f04`
- `0x1800260fc`
- `0x180026dcc`
- `0x180039740`

## import_xrefs

- `msvcrt!wcschr` at `0x1800262fa`
- `msvcrt!wcschr` at `0x1800262fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800261dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800263da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800261dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800263da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002627b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002627b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800264a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800264b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800264a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800264b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002642d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002642d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800264c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800264de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800264c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800264de`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180026174`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800261ef`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800261fc`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180026174`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800261ef`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800261fc`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180026296`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x1800263f3`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180026296`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x1800263f3`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x18002637a`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x18002637a`

## string_xrefs

- `0x1800261d5`: `SYSTEM\CurrentControlSet\Services\CertSvc\Configuration`

## pseudocode

```c
__int64 __fastcall _RegOpenRelativeKey(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        HKEY *a6)
{
  unsigned __int16 *v7; // r13
  int v8; // ebx
  unsigned int v9; // ecx
  int v10; // edx
  int RegKey; // eax
  struct _CSREGKEY *v12; // r14
  const unsigned __int16 *v13; // r15
  REGSAM v14; // esi
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  int v17; // r8d
  unsigned int v18; // edx
  const unsigned __int16 *v19; // rcx
  wchar_t *v20; // rax
  __int64 v21; // rcx
  wchar_t v22; // dx
  const wchar_t *v23; // r8
  const unsigned __int16 *v24; // rbx
  int v25; // eax
  HKEY v26; // rcx
  LSTATUS v27; // eax
  __int64 v28; // rax
  unsigned __int16 *v29; // rax
  unsigned __int64 v30; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v35; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v36; // [rsp+48h] [rbp-B8h] BYREF
  struct _CSREGKEY *v37; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h]
  WCHAR Data[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = (HKEY)a1;
  phkResult = 0;
  v7 = 0;
  v35 = 0;
  v36 = 0;
  Type = 0;
  cbData = 0;
  if ( a6 )
    *a6 = 0;
  if ( !a4 )
  {
    v8 = -2147467261;
    v9 = 170590645;
LABEL_5:
    v10 = v8;
LABEL_6:
    CSPrintErrorLineFile(v9, v10);
    goto LABEL_54;
  }
  *a4 = 0;
  v37 = 0;
  RegKey = _FindRegKey(a1, &v37);
  v8 = RegKey;
  if ( RegKey )
  {
    v10 = RegKey;
    v9 = 171311541;
    goto LABEL_6;
  }
  v12 = v37;
  v13 = (const unsigned __int16 *)*((_QWORD *)v37 + 2);
  v14 = (8 * (*((_DWORD *)v37 + 3) & 0x20)) | 0x20019;
  if ( (*((_BYTE *)v37 + 12) & 7) != 0 )
  {
    v15 = RegOpenKeyExW(hKey, L"SYSTEM\\CurrentControlSet\\Services\\CertSvc\\Configuration", 0, v14, &phkResult);
    v8 = v15;
    if ( v15 )
    {
      CSPrintErrorLineFile(0xA5501B5u, v15);
      CSPrintErrorLineFile(0xA6401B5u, v8);
      goto LABEL_54;
    }
  }
  if ( (*((_BYTE *)v12 + 12) & 1) != 0 )
  {
    v35 = phkResult;
    phkResult = 0;
    Data[0] = 0;
    goto LABEL_38;
  }
  if ( (*((_BYTE *)v12 + 12) & 7) != 0 )
  {
    cbData = 520;
    Data[0] = 0;
    v16 = RegQueryValueExW(phkResult, L"Active", 0, &Type, (LPBYTE)Data, &cbData);
    v8 = v16;
    if ( v16 )
    {
      v17 = v16;
      v18 = 176488885;
LABEL_17:
      v19 = L"Active";
LABEL_18:
      CSPrintErrorLineFileData(v19, v18, v17);
      goto LABEL_54;
    }
    if ( Type != 1 && Type != 7 )
    {
      v8 = -2147024883;
      v18 = 176816565;
      v17 = -2147024883;
      goto LABEL_17;
    }
    if ( v13 )
    {
      StringCchCatW(Data, 0x104u, L"\\");
      StringCchCatW(Data, 0x104u, v13);
    }
    v20 = wcschr(L"ca", 0x5Cu);
    if ( v20 )
      StringCchCatW(Data, 0x104u, v20);
  }
  else
  {
    v21 = *((unsigned int *)v12 + 2);
    if ( aCa_0[v21] == 92 )
      v22 = aCa_0[v21 + 1];
    else
      v22 = aCa_0[v21];
    v23 = L"a";
    if ( aCa_0[v21] != 92 )
      v23 = L"ca";
    if ( v22 && (*((_BYTE *)v12 + 12) & 0x10) != 0 )
    {
      v24 = &v23[v21];
      v25 = regHashURLPath(v24, &v36);
      if ( v25 )
        CSPrintErrorLineFileData2(v24, 0xAD801B5u, v25, v25);
      v7 = v36;
    }
    Data[0] = 0;
    if ( v13 )
      StringCchCopyW(Data, 0x104u, v13);
  }
LABEL_38:
  if ( !v35 )
  {
    v26 = hKey;
    if ( phkResult )
      v26 = phkResult;
    v27 = RegOpenKeyExW(v26, Data, 0, v14, &v35);
    v8 = v27;
    if ( v27 )
    {
      CSPrintErrorLineFileData(Data, 0xAF001B5u, v27);
      v17 = v8;
      v19 = Data;
      v18 = 184680885;
      goto LABEL_18;
    }
  }
  v28 = -1;
  do
    ++v28;
  while ( Data[v28] );
  cbData = 2 * v28 + 2;
  v29 = (unsigned __int16 *)LocalAlloc(0, cbData);
  *a4 = v29;
  if ( !v29 )
  {
    v8 = -2147024882;
    v9 = 187171253;
    goto LABEL_5;
  }
  *v29 = 0;
  StringCchCatW(*a4, (unsigned __int64)cbData >> 1, Data);
  if ( !Data[0] && cbData > 2 )
  {
    v30 = (unsigned __int64)cbData >> 1;
    if ( (*a4)[v30 - 2] == 92 )
      (*a4)[v30 - 2] = 0;
  }
  if ( a6 )
  {
    *a6 = v35;
    v35 = 0;
  }
  v8 = 0;
LABEL_54:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v35 )
    RegCloseKey(v35);
  if ( v7 )
    LocalFree(v7);
  if ( v8 && a4 && *a4 )
  {
    LocalFree(*a4);
    *a4 = 0;
  }
  return myHError(v8);
}

```

## disassembly

```asm
0x1800260fc  mov     [rsp-8+arg_8], rbx
0x180026101  push    rbp
0x180026102  push    rsi
0x180026103  push    rdi
0x180026104  push    r12
0x180026106  push    r13
0x180026108  push    r14
0x18002610a  push    r15
0x18002610c  lea     rbp, [rsp-180h]
0x180026114  sub     rsp, 280h
0x18002611b  mov     rax, cs:__security_cookie
0x180026122  xor     rax, rsp
0x180026125  mov     [rbp+1B0h+var_40], rax
0x18002612c  mov     r12, [rbp+1B0h+arg_28]
0x180026133  xor     r14d, r14d
0x180026136  mov     [rsp+2B0h+hKey], rcx
0x18002613b  mov     rdi, r9
0x18002613e  mov     [rsp+2B0h+var_278], r14
0x180026143  mov     r13d, r14d
0x180026146  mov     [rsp+2B0h+var_270], r14
0x18002614b  mov     [rsp+2B0h+var_268], r14
0x180026150  mov     [rsp+2B0h+Type], r14d
0x180026155  mov     [rsp+2B0h+cbData], r14d
0x18002615a  test    r12, r12
0x18002615d  jz      short loc_180026163
0x18002615f  mov     [r12], r14
0x180026163  test    rdi, rdi
0x180026166  jnz     short loc_18002617F
0x180026168  mov     ebx, 80004003h
0x18002616d  mov     ecx, 0A2B01B5h
0x180026172  mov     edx, ebx
0x180026174  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002617a  jmp     loc_18002649F
0x18002617f  lea     rdx, [rsp+2B0h+var_260]; struct _CSREGKEY **
0x180026184  mov     [r9], r14
0x180026187  mov     [rsp+2B0h+var_260], r14
0x18002618c  call    ?_FindRegKey@@YAJPEBGPEAPEBU_CSREGKEY@@@Z; _FindRegKey(ushort const *,_CSREGKEY const * *)
0x180026191  mov     ebx, eax
0x180026193  test    eax, eax
0x180026195  jz      short loc_1800261A0
0x180026197  mov     edx, eax
0x180026199  mov     ecx, 0A3601B5h
0x18002619e  jmp     short loc_180026174
0x1800261a0  mov     r14, [rsp+2B0h+var_260]
0x1800261a5  mov     esi, [r14+0Ch]
0x1800261a9  mov     r15, [r14+10h]
0x1800261ad  and     esi, 20h
0x1800261b0  shl     esi, 3
0x1800261b3  or      esi, 20019h
0x1800261b9  test    byte ptr [r14+0Ch], 7
0x1800261be  jz      short loc_18002620A
0x1800261c0  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800261c5  lea     rax, [rsp+2B0h+var_278]
0x1800261ca  mov     r9d, esi; samDesired
0x1800261cd  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1800261d2  xor     r8d, r8d; ulOptions
0x1800261d5  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ce"...
0x1800261dc  call    cs:__imp_RegOpenKeyExW
0x1800261e2  mov     ebx, eax
0x1800261e4  test    eax, eax
0x1800261e6  jz      short loc_18002620A
0x1800261e8  mov     edx, eax
0x1800261ea  mov     ecx, 0A5501B5h
0x1800261ef  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800261f5  mov     edx, ebx
0x1800261f7  mov     ecx, 0A6401B5h
0x1800261fc  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180026202  xor     r14d, r14d
0x180026205  jmp     loc_18002649F
0x18002620a  test    byte ptr [r14+0Ch], 1
0x18002620f  mov     r9d, 5Ch ; '\'
0x180026215  jz      short loc_180026237
0x180026217  mov     rax, [rsp+2B0h+var_278]
0x18002621c  xor     r14d, r14d
0x18002621f  mov     [rsp+2B0h+var_270], rax
0x180026224  mov     r15d, r9d
0x180026227  mov     [rsp+2B0h+var_278], r14
0x18002622c  mov     [rsp+2B0h+Data], r14w
0x180026232  jmp     loc_1800263AD
0x180026237  test    byte ptr [r14+0Ch], 7
0x18002623c  jz      loc_18002631E
0x180026242  mov     rcx, [rsp+2B0h+var_278]; hKey
0x180026247  lea     rax, [rsp+2B0h+cbData]
0x18002624c  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x180026251  lea     r9, [rsp+2B0h+Type]; lpType
0x180026256  lea     rax, [rsp+2B0h+Data]
0x18002625b  mov     [rsp+2B0h+cbData], 208h
0x180026263  xor     r14d, r14d
0x180026266  mov     [rsp+2B0h+phkResult], rax; lpData
0x18002626b  xor     r8d, r8d; lpReserved
0x18002626e  mov     [rsp+2B0h+Data], r14w
0x180026274  lea     rdx, aActive; "Active"
0x18002627b  call    cs:__imp_RegQueryValueExW
0x180026281  mov     ebx, eax
0x180026283  test    eax, eax
0x180026285  jz      short loc_1800262A1
0x180026287  mov     r8d, eax
0x18002628a  mov     edx, 0A8501B5h
0x18002628f  lea     rcx, aActive; "Active"
0x180026296  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18002629c  jmp     loc_18002649F
0x1800262a1  cmp     [rsp+2B0h+Type], 1
0x1800262a6  jz      short loc_1800262BE
0x1800262a8  cmp     [rsp+2B0h+Type], 7
0x1800262ad  jz      short loc_1800262BE
0x1800262af  mov     ebx, 8007000Dh
0x1800262b4  mov     edx, 0A8A01B5h
0x1800262b9  mov     r8d, ebx
0x1800262bc  jmp     short loc_18002628F
0x1800262be  mov     ebx, 104h
0x1800262c3  test    r15, r15
0x1800262c6  jz      short loc_1800262EA
0x1800262c8  lea     r8, SubStr; "\\"
0x1800262cf  mov     edx, ebx; unsigned __int64
0x1800262d1  lea     rcx, [rsp+2B0h+Data]; unsigned __int16 *
0x1800262d6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800262db  mov     r8, r15; unsigned __int16 *
0x1800262de  lea     rcx, [rsp+2B0h+Data]; unsigned __int16 *
0x1800262e3  mov     edx, ebx; unsigned __int64
0x1800262e5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800262ea  mov     r15d, 5Ch ; '\'
0x1800262f0  lea     rcx, aCa_0; "ca"
0x1800262f7  mov     edx, r15d; Ch
0x1800262fa  call    cs:__imp_wcschr
0x180026300  test    rax, rax
0x180026303  jz      loc_1800263AD
0x180026309  mov     r8, rax; unsigned __int16 *
0x18002630c  lea     rcx, [rsp+2B0h+Data]; unsigned __int16 *
0x180026311  mov     rdx, rbx; unsigned __int64
0x180026314  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180026319  jmp     loc_1800263AD
0x18002631e  mov     ecx, [r14+8]
0x180026322  lea     rax, aCa_0; "ca"
0x180026329  cmp     r9w, [rax+rcx*2]
0x18002632e  jnz     short loc_180026337
0x180026330  movzx   edx, word ptr [rax+rcx*2+2]
0x180026335  jmp     short loc_18002633B
0x180026337  movzx   edx, word ptr [rax+rcx*2]
0x18002633b  lea     r8, aCa_0+2; "a"
0x180026342  cmovnz  r8, rax
0x180026346  xor     eax, eax
0x180026348  cmp     ax, dx
0x18002634b  jz      short loc_180026387
0x18002634d  test    byte ptr [r14+0Ch], 10h
0x180026352  jz      short loc_180026387
0x180026354  lea     rbx, [r8+rcx*2]
0x180026358  mov     rcx, rbx; Src
0x18002635b  lea     rdx, [rsp+2B0h+var_268]; unsigned __int16 **
0x180026360  call    ?regHashURLPath@@YAJPEBGPEAPEAG@Z; regHashURLPath(ushort const *,ushort * *)
0x180026365  xor     r14d, r14d
0x180026368  test    eax, eax
0x18002636a  jz      short loc_180026380
0x18002636c  mov     r9d, eax
0x18002636f  mov     r8d, eax
0x180026372  mov     edx, 0AD801B5h
0x180026377  mov     rcx, rbx
0x18002637a  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180026380  mov     r13, [rsp+2B0h+var_268]
0x180026385  jmp     short loc_18002638A
0x180026387  xor     r14d, r14d
0x18002638a  mov     [rsp+2B0h+Data], r14w
0x180026390  test    r15, r15
0x180026393  jz      short loc_1800263A7
0x180026395  mov     r8, r15; unsigned __int16 *
0x180026398  lea     rcx, [rsp+2B0h+Data]; unsigned __int16 *
0x18002639d  mov     edx, 104h; unsigned __int64
0x1800263a2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800263a7  mov     r15d, 5Ch ; '\'
0x1800263ad  cmp     [rsp+2B0h+var_270], r14
0x1800263b2  jnz     short loc_18002640B
0x1800263b4  mov     rax, [rsp+2B0h+var_278]
0x1800263b9  lea     rdx, [rsp+2B0h+Data]; lpSubKey
0x1800263be  mov     rcx, [rsp+2B0h+hKey]
0x1800263c3  test    rax, rax
0x1800263c6  mov     r9d, esi; samDesired
0x1800263c9  cmovnz  rcx, rax; hKey
0x1800263cd  lea     rax, [rsp+2B0h+var_270]
0x1800263d2  xor     r8d, r8d; ulOptions
0x1800263d5  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1800263da  call    cs:__imp_RegOpenKeyExW
0x1800263e0  mov     ebx, eax
0x1800263e2  test    eax, eax
0x1800263e4  jz      short loc_18002640B
0x1800263e6  mov     r8d, eax
0x1800263e9  lea     rcx, [rsp+2B0h+Data]
0x1800263ee  mov     edx, 0AF001B5h
0x1800263f3  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x1800263f9  mov     r8d, ebx
0x1800263fc  lea     rcx, [rsp+2B0h+Data]
0x180026401  mov     edx, 0B0201B5h
0x180026406  jmp     loc_180026296
0x18002640b  lea     rcx, [rsp+2B0h+Data]
0x180026410  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026414  inc     rax
0x180026417  cmp     [rcx+rax*2], r14w
0x18002641c  jnz     short loc_180026414
0x18002641e  lea     eax, ds:2[rax*2]
0x180026425  xor     ecx, ecx; uFlags
0x180026427  mov     edx, eax; uBytes
0x180026429  mov     [rsp+2B0h+cbData], eax
0x18002642d  call    cs:__imp_LocalAlloc
0x180026433  mov     [rdi], rax
0x180026436  test    rax, rax
0x180026439  jnz     short loc_18002644A
0x18002643b  mov     ebx, 8007000Eh
0x180026440  mov     ecx, 0B2801B5h
0x180026445  jmp     loc_180026172
0x18002644a  mov     [rax], r14w
0x18002644e  lea     r8, [rsp+2B0h+Data]; unsigned __int16 *
0x180026453  mov     edx, [rsp+2B0h+cbData]
0x180026457  mov     rcx, [rdi]; unsigned __int16 *
0x18002645a  shr     rdx, 1; unsigned __int64
0x18002645d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180026462  cmp     r14w, [rsp+2B0h+Data]
0x180026468  jnz     short loc_180026489
0x18002646a  cmp     [rsp+2B0h+cbData], 2
0x18002646f  jbe     short loc_180026489
0x180026471  mov     ecx, [rsp+2B0h+cbData]
0x180026475  mov     rdx, [rdi]
0x180026478  shr     rcx, 1
0x18002647b  cmp     r15w, [rdx+rcx*2-4]
0x180026481  jnz     short loc_180026489
0x180026483  mov     [rdx+rcx*2-4], r14w
0x180026489  test    r12, r12
0x18002648c  jz      short loc_18002649C
0x18002648e  mov     rax, [rsp+2B0h+var_270]
0x180026493  mov     [r12], rax
0x180026497  mov     [rsp+2B0h+var_270], r14
0x18002649c  mov     ebx, r14d
0x18002649f  mov     rcx, [rsp+2B0h+var_278]; hKey
0x1800264a4  test    rcx, rcx
0x1800264a7  jz      short loc_1800264AF
0x1800264a9  call    cs:__imp_RegCloseKey
0x1800264af  mov     rcx, [rsp+2B0h+var_270]; hKey
0x1800264b4  test    rcx, rcx
0x1800264b7  jz      short loc_1800264BF
0x1800264b9  call    cs:__imp_RegCloseKey
0x1800264bf  test    r13, r13
0x1800264c2  jz      short loc_1800264CD
0x1800264c4  mov     rcx, r13; hMem
0x1800264c7  call    cs:__imp_LocalFree
0x1800264cd  test    ebx, ebx
0x1800264cf  jz      short loc_1800264E7
0x1800264d1  test    rdi, rdi
0x1800264d4  jz      short loc_1800264E7
0x1800264d6  mov     rcx, [rdi]; hMem
0x1800264d9  test    rcx, rcx
0x1800264dc  jz      short loc_1800264E7
0x1800264de  call    cs:__imp_LocalFree
0x1800264e4  mov     [rdi], r14
0x1800264e7  mov     ecx, ebx; int
0x1800264e9  call    ?myHError@@YAJJ@Z; myHError(long)
0x1800264ee  mov     rcx, [rbp+1B0h+var_40]
0x1800264f5  xor     rcx, rsp; StackCookie
0x1800264f8  call    __security_check_cookie
0x1800264fd  mov     rbx, [rsp+2B0h+arg_8]
0x180026505  add     rsp, 280h
0x18002650c  pop     r15
0x18002650e  pop     r14
0x180026510  pop     r13
0x180026512  pop     r12
0x180026514  pop     rdi
0x180026515  pop     rsi
0x180026516  pop     rbp
0x180026517  retn
```
