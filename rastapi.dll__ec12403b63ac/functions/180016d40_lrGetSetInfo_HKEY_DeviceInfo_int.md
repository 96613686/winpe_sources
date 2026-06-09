# lrGetSetInfo(HKEY__ *,DeviceInfo *,int)

- ea: `0x180016d40`
- end: `0x18001739b`
- name: `?lrGetSetInfo@@YAJPEAUHKEY__@@PEAUDeviceInfo@@H@Z`
- size: `1627`
- prototype: `__int64 __fastcall(HKEY hKey, struct DeviceInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800030f0`

## callees

- `0x180016d40`
- `0x180017740`
- `0x180020a20`
- `0x180020c5c`
- `0x180029266`
- `0x18002927e`
- `0x1800292b0`

## import_xrefs

- `msvcrt!wcstoul` at `0x1800170c9`
- `msvcrt!wcstoul` at `0x1800170e3`
- `msvcrt!wcstoul` at `0x1800170fd`
- `msvcrt!wcstoul` at `0x180017117`
- `msvcrt!wcstoul` at `0x180017131`
- `msvcrt!wcstoul` at `0x18001714b`
- `msvcrt!wcstoul` at `0x180017165`
- `msvcrt!wcstoul` at `0x18001717f`
- `msvcrt!wcstoul` at `0x180017199`
- `msvcrt!wcstoul` at `0x1800171b4`
- `msvcrt!wcstoul` at `0x1800171cf`
- `msvcrt!wcstoul` at `0x1800170c9`
- `msvcrt!wcstoul` at `0x1800170e3`
- `msvcrt!wcstoul` at `0x1800170fd`
- `msvcrt!wcstoul` at `0x180017117`
- `msvcrt!wcstoul` at `0x180017131`
- `msvcrt!wcstoul` at `0x18001714b`
- `msvcrt!wcstoul` at `0x180017165`
- `msvcrt!wcstoul` at `0x18001717f`
- `msvcrt!wcstoul` at `0x180017199`
- `msvcrt!wcstoul` at `0x1800171b4`
- `msvcrt!wcstoul` at `0x1800171cf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016eee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016eee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016f42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016f42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016efc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016efc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016fb7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017011`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800172a3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800172eb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016fb7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017011`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800172a3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800172eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016ed6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016f23`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016ed6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016f23`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001734b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001734b`

## pseudocode

```c
__int64 __fastcall lrGetSetInfo(HKEY hKey, struct DeviceInfo *a2)
{
  _DWORD *v4; // r15
  int v5; // ecx
  __int64 i; // rdi
  BYTE *lpData; // r14
  const WCHAR *v8; // r13
  DWORD LastError; // ebx
  BYTE *v10; // r15
  int v11; // ecx
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  wchar_t *v14; // r8
  __int64 v15; // rdx
  wchar_t *v16; // rax
  wchar_t *v17; // rcx
  char v18; // al
  char v19; // al
  char v20; // al
  char v21; // al
  char v22; // al
  char v23; // al
  char v24; // al
  char v25; // al
  __int16 v26; // ax
  __int16 v27; // ax
  BOOL v28; // r14d
  unsigned int v29; // eax
  int v30; // ecx
  size_t Size; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int RestrictedPortCount; // [rsp+50h] [rbp-B0h]
  LPCWSTR lpValueName; // [rsp+60h] [rbp-A0h]
  LPBYTE v37; // [rsp+68h] [rbp-98h]
  _DWORD v38[2]; // [rsp+70h] [rbp-90h]
  const WCHAR *v39; // [rsp+78h] [rbp-88h]
  char *v40; // [rsp+80h] [rbp-80h]
  int v41; // [rsp+88h] [rbp-78h]
  int v42; // [rsp+8Ch] [rbp-74h]
  const WCHAR *v43; // [rsp+90h] [rbp-70h]
  char *v44; // [rsp+98h] [rbp-68h]
  int v45; // [rsp+A0h] [rbp-60h]
  int v46; // [rsp+A4h] [rbp-5Ch]
  const wchar_t *v47; // [rsp+A8h] [rbp-58h]
  char *v48; // [rsp+B0h] [rbp-50h]
  int v49; // [rsp+B8h] [rbp-48h]
  int v50; // [rsp+BCh] [rbp-44h]
  const wchar_t *v51; // [rsp+C0h] [rbp-40h]
  char *v52; // [rsp+C8h] [rbp-38h]
  int v53; // [rsp+D0h] [rbp-30h]
  int v54; // [rsp+D4h] [rbp-2Ch]
  const wchar_t *v55; // [rsp+D8h] [rbp-28h]
  char *v56; // [rsp+E0h] [rbp-20h]
  int v57; // [rsp+E8h] [rbp-18h]
  int v58; // [rsp+ECh] [rbp-14h]
  const wchar_t *v59; // [rsp+F0h] [rbp-10h]
  char *v60; // [rsp+F8h] [rbp-8h]
  int v61; // [rsp+100h] [rbp+0h]
  int v62; // [rsp+104h] [rbp+4h]
  const WCHAR *v63; // [rsp+108h] [rbp+8h]
  _BYTE *v64; // [rsp+110h] [rbp+10h]
  int v65; // [rsp+118h] [rbp+18h]
  int v66; // [rsp+11Ch] [rbp+1Ch]
  wchar_t v67[9]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t v68[5]; // [rsp+132h] [rbp+32h] BYREF
  wchar_t v69[5]; // [rsp+13Ch] [rbp+3Ch] BYREF
  wchar_t v70[2]; // [rsp+146h] [rbp+46h] BYREF
  wchar_t v71[3]; // [rsp+14Ah] [rbp+4Ah] BYREF
  wchar_t v72[2]; // [rsp+150h] [rbp+50h] BYREF
  wchar_t v73; // [rsp+154h] [rbp+54h] BYREF
  wchar_t v74[2]; // [rsp+158h] [rbp+58h] BYREF
  wchar_t v75; // [rsp+15Ch] [rbp+5Ch] BYREF
  wchar_t v76[2]; // [rsp+160h] [rbp+60h] BYREF
  wchar_t String[6]; // [rsp+164h] [rbp+64h] BYREF
  _WORD v78[1]; // [rsp+170h] [rbp+70h] BYREF
  char v79; // [rsp+172h] [rbp+72h] BYREF

  memset_0(v78, 0, 0x4Eu);
  v61 = 258;
  v38[0] = 4;
  lpValueName = L"WanEndpoints";
  v38[1] = 4;
  v39 = L"EnableForRas";
  v4 = (_DWORD *)((char *)a2 + 76);
  v41 = 4;
  v40 = (char *)a2 + 56;
  v43 = L"EnableForRouting";
  v44 = (char *)a2 + 60;
  v47 = L"EnableForOutboundRouting";
  v48 = (char *)a2 + 64;
  v51 = L"MinWanEndPoints";
  v52 = (char *)a2 + 88;
  v55 = L"MaxWanEndPoints";
  v56 = (char *)a2 + 92;
  v59 = L"DriverDesc";
  v60 = (char *)a2 + 262;
  v42 = 4;
  v45 = 4;
  v46 = 4;
  v49 = 4;
  v50 = 4;
  v53 = 4;
  v54 = 4;
  v57 = 4;
  v58 = 4;
  v5 = *((_DWORD *)a2 + 24);
  v63 = L"NetCfgInstanceID";
  v64 = v78;
  v37 = (LPBYTE)a2 + 76;
  v62 = 1;
  v65 = 78;
  v66 = 1;
  cbData = 0;
  Type = 0;
  if ( (unsigned int)(unsigned __int16)v5 - 8 <= 1
    || (unsigned int)(unsigned __int16)v5 - 14 <= 1
    || (RestrictedPortCount = 30000, (unsigned __int16)v5 == 16) )
  {
    RestrictedPortCount = GetRestrictedPortCount();
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    while ( 1 )
    {
      lpData = *(BYTE **)&v38[6 * i - 2];
      v8 = (&lpValueName)[3 * i];
      LODWORD(Size) = v38[6 * i];
      cbData = Size;
      LastError = RegQueryValueExW(hKey, v8, 0, &Type, lpData, &cbData);
      if ( LastError == 234 )
      {
        v10 = (BYTE *)LocalAlloc(0x40u, cbData);
        if ( v10 )
        {
          LastError = RegQueryValueExW(hKey, v8, 0, &Type, v10, &cbData);
          if ( !LastError )
            memcpy_0(lpData, v10, (unsigned int)Size);
          LocalFree(v10);
        }
        else
        {
          LastError = GetLastError();
        }
        v4 = (_DWORD *)((char *)a2 + 76);
      }
      v11 = (unsigned __int16)*((_DWORD *)a2 + 24);
      if ( ((unsigned int)(v11 - 8) <= 1 || (unsigned int)(v11 - 14) <= 2) && !LastError )
      {
        if ( (i & 0xFFFFFFFA) != 0 || (_DWORD)i == 1 || Type != 4 || *(_DWORD *)lpData <= RestrictedPortCount )
          goto LABEL_31;
        *(_DWORD *)lpData = RestrictedPortCount;
        LastError = RegSetValueExW(hKey, v8, 0, Type, lpData, cbData);
      }
      if ( LastError && !(_DWORD)i )
      {
        *v4 = -1;
        LastError = 0;
LABEL_24:
        if ( (_DWORD)i == 2 )
        {
          if ( LastError != 2 )
            goto LABEL_64;
          LODWORD(Size) = 0;
          LastError = RegSetValueExW(hKey, L"EnableForRouting", 0, 4u, (const BYTE *)&Size, 4u);
          if ( LastError )
            goto LABEL_64;
          *((_DWORD *)a2 + 15) = 0;
          goto LABEL_28;
        }
        goto LABEL_42;
      }
LABEL_31:
      if ( (_DWORD)i == 7 )
        break;
      if ( (_DWORD)i != 1 )
        goto LABEL_24;
      if ( LastError != 2 )
        goto LABEL_64;
      LODWORD(Size) = 0;
      lrGetProductType(&Size);
      if ( (_DWORD)Size == 2 )
      {
        v29 = (unsigned __int16)*((_DWORD *)a2 + 24);
        if ( v29 > 0xD || (v30 = 11008, !_bittest(&v30, v29)) )
        {
          LODWORD(Size) = 1;
          LastError = RegSetValueExW(hKey, L"EnableForRas", 0, 4u, (const BYTE *)&Size, 4u);
          if ( LastError )
            goto LABEL_64;
          *((_DWORD *)a2 + 14) = 1;
          goto LABEL_55;
        }
      }
      LODWORD(Size) = 0;
      LastError = RegSetValueExW(hKey, L"EnableForRas", 0, 4u, (const BYTE *)&Size, 4u);
      if ( LastError )
        goto LABEL_64;
      *((_DWORD *)a2 + 14) = 0;
LABEL_28:
      if ( (_DWORD)i != 5 )
      {
        if ( (_DWORD)i != 6 || WideCharToMultiByte(0, 0x400u, (LPCWCH)a2 + 131, -1, (LPSTR)a2 + 133, 129, 0, 0) )
          goto LABEL_64;
        *((_BYTE *)a2 + 133) = 0;
        goto LABEL_55;
      }
      if ( LastError == 2 )
      {
        *((_DWORD *)a2 + 23) = *v4;
        goto LABEL_55;
      }
LABEL_64:
      i = (unsigned int)(i + 1);
      if ( (unsigned int)i >= 8 )
        return LastError;
    }
    Size = 0;
    v12 = -1;
    do
      ++v12;
    while ( v78[v12] );
    if ( v12 < 0x26 )
      break;
    v13 = 2147483646;
    v14 = (wchar_t *)&v79;
    v15 = 39;
    v16 = v67;
    do
    {
      if ( !v13 )
        break;
      if ( !*v14 )
        break;
      *v16++ = *v14++;
      --v13;
      --v15;
    }
    while ( v15 );
    v17 = v16 - 1;
    if ( v15 )
      v17 = v16;
    *v17 = 0;
    String[2] = 0;
    v18 = wcstoul(String, (wchar_t **)&Size, 16);
    String[0] = 0;
    *((_BYTE *)a2 + 115) = v18;
    v19 = wcstoul(v76, (wchar_t **)&Size, 16);
    v76[0] = 0;
    *((_BYTE *)a2 + 114) = v19;
    v20 = wcstoul(&v75, (wchar_t **)&Size, 16);
    v75 = 0;
    *((_BYTE *)a2 + 113) = v20;
    v21 = wcstoul(v74, (wchar_t **)&Size, 16);
    v74[0] = 0;
    *((_BYTE *)a2 + 112) = v21;
    v22 = wcstoul(&v73, (wchar_t **)&Size, 16);
    v73 = 0;
    *((_BYTE *)a2 + 111) = v22;
    v23 = wcstoul(v72, (wchar_t **)&Size, 16);
    v71[2] = 0;
    *((_BYTE *)a2 + 110) = v23;
    v24 = wcstoul(v71, (wchar_t **)&Size, 16);
    v71[0] = 0;
    *((_BYTE *)a2 + 109) = v24;
    v25 = wcstoul(v70, (wchar_t **)&Size, 16);
    v69[4] = 0;
    *((_BYTE *)a2 + 108) = v25;
    v26 = wcstoul(v69, (wchar_t **)&Size, 16);
    v68[4] = 0;
    *((_WORD *)a2 + 53) = v26;
    v27 = wcstoul(v68, (wchar_t **)&Size, 16);
    v67[8] = 0;
    *((_WORD *)a2 + 52) = v27;
    *((_DWORD *)a2 + 25) = wcstoul(v67, (wchar_t **)&Size, 16);
    LastError = 0;
LABEL_42:
    if ( (_DWORD)i == 3 )
    {
      if ( LastError != 2 )
        goto LABEL_64;
      LODWORD(Size) = 0;
      v28 = 0;
      lrGetProductType(&Size);
      if ( (_DWORD)Size == 2 )
        v28 = (unsigned __int16)*((_DWORD *)a2 + 24) == 13;
      LastError = lrRasEnableDevice(hKey, L"EnableForOutboundRouting", v28);
      if ( LastError )
        goto LABEL_64;
      *((_DWORD *)a2 + 16) = v28;
      goto LABEL_28;
    }
    if ( (_DWORD)i != 4 )
      goto LABEL_28;
    if ( LastError != 2 )
      goto LABEL_64;
    *((_DWORD *)a2 + 22) = *v4;
LABEL_55:
    ;
  }
  return (DWORD)-2147024809;
}

```

## disassembly

```asm
0x180016d40  mov     [rsp-8+arg_10], rbx
0x180016d45  push    rbp
0x180016d46  push    rsi
0x180016d47  push    rdi
0x180016d48  push    r12
0x180016d4a  push    r13
0x180016d4c  push    r14
0x180016d4e  push    r15
0x180016d50  lea     rbp, [rsp-0D0h]
0x180016d58  sub     rsp, 1D0h
0x180016d5f  mov     rax, cs:__security_cookie
0x180016d66  xor     rax, rsp
0x180016d69  mov     [rbp+100h+var_40], rax
0x180016d70  mov     rsi, rdx
0x180016d73  mov     r12, rcx
0x180016d76  mov     ebx, 4Eh ; 'N'
0x180016d7b  lea     rcx, [rbp+100h+var_90]; void *
0x180016d7f  mov     r8d, ebx; Size
0x180016d82  xor     edx, edx; Val
0x180016d84  call    memset_0
0x180016d89  lea     ecx, [rbx-4Ah]
0x180016d8c  mov     [rbp+100h+var_100], 102h
0x180016d93  lea     rax, aWanendpoints; "WanEndpoints"
0x180016d9a  mov     [rsp+200h+var_190], ecx
0x180016d9e  mov     [rsp+200h+lpValueName], rax
0x180016da3  lea     edx, [rbx-4Dh]
0x180016da6  lea     rax, aEnableforras; "EnableForRas"
0x180016dad  mov     [rsp+200h+var_18C], ecx
0x180016db1  mov     [rsp+200h+var_188], rax
0x180016db6  lea     r15, [rsi+4Ch]
0x180016dba  lea     rax, [rsi+38h]
0x180016dbe  mov     [rbp+100h+var_178], ecx
0x180016dc1  mov     [rbp+100h+var_180], rax
0x180016dc5  lea     rax, aEnableforrouti; "EnableForRouting"
0x180016dcc  mov     [rbp+100h+var_170], rax
0x180016dd0  lea     rax, [rsi+3Ch]
0x180016dd4  mov     [rbp+100h+var_168], rax
0x180016dd8  lea     rax, aEnableforoutbo; "EnableForOutboundRouting"
0x180016ddf  mov     [rbp+100h+var_158], rax
0x180016de3  lea     rax, [rsi+40h]
0x180016de7  mov     [rbp+100h+var_150], rax
0x180016deb  lea     rax, aMinwanendpoint; "MinWanEndPoints"
0x180016df2  mov     [rbp+100h+var_140], rax
0x180016df6  lea     rax, [rsi+58h]
0x180016dfa  mov     [rbp+100h+var_138], rax
0x180016dfe  lea     rax, aMaxwanendpoint_0; "MaxWanEndPoints"
0x180016e05  mov     [rbp+100h+var_128], rax
0x180016e09  lea     rax, [rsi+5Ch]
0x180016e0d  mov     [rbp+100h+var_120], rax
0x180016e11  lea     rax, aDriverdesc; "DriverDesc"
0x180016e18  mov     [rbp+100h+var_110], rax
0x180016e1c  lea     rax, [rsi+106h]
0x180016e23  mov     [rbp+100h+var_108], rax
0x180016e27  lea     rax, aNetcfginstance; "NetCfgInstanceID"
0x180016e2e  mov     [rbp+100h+var_174], ecx
0x180016e31  mov     [rbp+100h+var_160], ecx
0x180016e34  mov     [rbp+100h+var_15C], ecx
0x180016e37  mov     [rbp+100h+var_148], ecx
0x180016e3a  mov     [rbp+100h+var_144], ecx
0x180016e3d  mov     [rbp+100h+var_130], ecx
0x180016e40  mov     [rbp+100h+var_12C], ecx
0x180016e43  mov     [rbp+100h+var_118], ecx
0x180016e46  mov     [rbp+100h+var_114], ecx
0x180016e49  mov     ecx, [rsi+60h]
0x180016e4c  mov     [rbp+100h+var_F8], rax
0x180016e50  lea     rax, [rbp+100h+var_90]
0x180016e54  movzx   ecx, cx
0x180016e57  mov     [rbp+100h+var_F0], rax
0x180016e5b  mov     [rsp+200h+var_198], r15
0x180016e60  mov     [rbp+100h+var_FC], edx
0x180016e63  lea     eax, [rcx-8]
0x180016e66  mov     [rbp+100h+var_E8], ebx
0x180016e69  mov     [rbp+100h+var_E4], edx
0x180016e6c  mov     [rsp+200h+cbData], 0
0x180016e74  mov     [rsp+200h+Type], 0
0x180016e7c  cmp     eax, edx
0x180016e7e  jbe     short loc_180016E94
0x180016e80  lea     eax, [rcx-0Eh]
0x180016e83  cmp     eax, edx
0x180016e85  jbe     short loc_180016E94
0x180016e87  mov     [rsp+200h+var_1B0], 7530h
0x180016e8f  cmp     ecx, 10h
0x180016e92  jnz     short loc_180016E9D
0x180016e94  call    GetRestrictedPortCount
0x180016e99  mov     [rsp+200h+var_1B0], eax
0x180016e9d  xor     edi, edi
0x180016e9f  lea     rdx, [rdi+rdi*2]
0x180016ea3  xor     r8d, r8d; lpReserved
0x180016ea6  mov     eax, [rsp+rdx*8+200h+var_190]
0x180016eaa  lea     r9, [rsp+200h+Type]; lpType
0x180016eaf  mov     r14, [rsp+rdx*8+200h+var_198]
0x180016eb4  mov     rcx, r12; hKey
0x180016eb7  mov     r13, [rsp+rdx*8+200h+lpValueName]
0x180016ebc  mov     dword ptr [rsp+200h+Size], eax
0x180016ec0  mov     rdx, r13; lpValueName
0x180016ec3  mov     [rsp+200h+cbData], eax
0x180016ec7  lea     rax, [rsp+200h+cbData]
0x180016ecc  mov     [rsp+200h+lpcbData], rax; lpcbData
0x180016ed1  mov     [rsp+200h+lpData], r14; lpData
0x180016ed6  call    cs:__imp_RegQueryValueExW
0x180016edc  mov     ebx, eax
0x180016ede  cmp     eax, 0EAh
0x180016ee3  jnz     short loc_180016F4C
0x180016ee5  mov     edx, [rsp+200h+cbData]; uBytes
0x180016ee9  mov     ecx, 40h ; '@'; uFlags
0x180016eee  call    cs:__imp_LocalAlloc
0x180016ef4  mov     r15, rax
0x180016ef7  test    rax, rax
0x180016efa  jnz     short loc_180016F06
0x180016efc  call    cs:__imp_GetLastError
0x180016f02  mov     ebx, eax
0x180016f04  jmp     short loc_180016F48
0x180016f06  lea     rax, [rsp+200h+cbData]
0x180016f0b  xor     r8d, r8d; lpReserved
0x180016f0e  mov     [rsp+200h+lpcbData], rax; lpcbData
0x180016f13  lea     r9, [rsp+200h+Type]; lpType
0x180016f18  mov     rdx, r13; lpValueName
0x180016f1b  mov     [rsp+200h+lpData], r15; lpData
0x180016f20  mov     rcx, r12; hKey
0x180016f23  call    cs:__imp_RegQueryValueExW
0x180016f29  mov     ebx, eax
0x180016f2b  test    eax, eax
0x180016f2d  jnz     short loc_180016F3F
0x180016f2f  mov     r8d, dword ptr [rsp+200h+Size]; Size
0x180016f34  mov     rdx, r15; Src
0x180016f37  mov     rcx, r14; void *
0x180016f3a  call    memcpy_0
0x180016f3f  mov     rcx, r15; hMem
0x180016f42  call    cs:__imp_LocalFree
0x180016f48  lea     r15, [rsi+4Ch]
0x180016f4c  mov     ecx, [rsi+60h]
0x180016f4f  mov     r10d, 1
0x180016f55  movzx   ecx, cx
0x180016f58  lea     eax, [rcx-8]
0x180016f5b  cmp     eax, r10d
0x180016f5e  jbe     short loc_180016F68
0x180016f60  lea     eax, [rcx-0Eh]
0x180016f63  cmp     eax, 2
0x180016f66  ja      short loc_180016FC5
0x180016f68  test    ebx, ebx
0x180016f6a  jnz     short loc_180016FC5
0x180016f6c  test    edi, 0FFFFFFFAh
0x180016f72  jnz     loc_180017042
0x180016f78  cmp     edi, r10d
0x180016f7b  jz      loc_180017042
0x180016f81  cmp     [rsp+200h+Type], 4
0x180016f86  jnz     loc_180017042
0x180016f8c  mov     eax, [rsp+200h+var_1B0]
0x180016f90  cmp     [r14], eax
0x180016f93  jbe     loc_180017042
0x180016f99  mov     [r14], eax
0x180016f9c  xor     r8d, r8d; Reserved
0x180016f9f  mov     eax, [rsp+200h+cbData]
0x180016fa3  mov     rdx, r13; lpValueName
0x180016fa6  mov     r9d, [rsp+200h+Type]; dwType
0x180016fab  mov     rcx, r12; hKey
0x180016fae  mov     dword ptr [rsp+200h+lpcbData], eax; cbData
0x180016fb2  mov     [rsp+200h+lpData], r14; lpData
0x180016fb7  call    cs:__imp_RegSetValueExW
0x180016fbd  mov     ebx, eax
0x180016fbf  mov     r10d, 1
0x180016fc5  xor     r13d, r13d
0x180016fc8  test    ebx, ebx
0x180016fca  jz      short loc_180017045
0x180016fcc  test    edi, edi
0x180016fce  jnz     short loc_180017045
0x180016fd0  mov     dword ptr [r15], 0FFFFFFFFh
0x180016fd7  mov     ebx, r13d
0x180016fda  cmp     edi, 2
0x180016fdd  jnz     loc_1800171DB
0x180016fe3  cmp     ebx, edi
0x180016fe5  jnz     loc_18001735D
0x180016feb  lea     ecx, [rdi+2]
0x180016fee  mov     dword ptr [rsp+200h+Size], r13d
0x180016ff3  mov     dword ptr [rsp+200h+lpcbData], ecx; cbData
0x180016ff7  lea     rax, [rsp+200h+Size]
0x180016ffc  mov     r9d, ecx; dwType
0x180016fff  mov     [rsp+200h+lpData], rax; lpData
0x180017004  mov     rcx, r12; hKey
0x180017007  lea     rdx, aEnableforrouti; "EnableForRouting"
0x18001700e  xor     r8d, r8d; Reserved
0x180017011  call    cs:__imp_RegSetValueExW
0x180017017  mov     ebx, eax
0x180017019  test    eax, eax
0x18001701b  jnz     loc_18001735D
0x180017021  mov     [rsi+3Ch], r13d
0x180017025  cmp     edi, 5
0x180017028  jnz     loc_180017316
0x18001702e  cmp     ebx, 2
0x180017031  jnz     loc_18001735D
0x180017037  mov     eax, [r15]
0x18001703a  mov     [rsi+5Ch], eax
0x18001703d  jmp     loc_1800172BA
0x180017042  xor     r13d, r13d
0x180017045  cmp     edi, 7
0x180017048  jnz     loc_18001723A
0x18001704e  mov     [rsp+200h+Size], r13
0x180017053  lea     rcx, [rbp+100h+var_90]
0x180017057  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001705b  inc     rax
0x18001705e  cmp     [rcx+rax*2], r13w
0x180017063  jnz     short loc_18001705B
0x180017065  cmp     rax, 26h ; '&'
0x180017069  jb      loc_18001736A
0x18001706f  mov     ecx, 7FFFFFFEh
0x180017074  lea     r8, [rbp+100h+var_8E]
0x180017078  mov     edx, 27h ; '''
0x18001707d  lea     rax, [rbp+100h+var_E0]
0x180017081  test    rcx, rcx
0x180017084  jz      short loc_1800170A4
0x180017086  movzx   r9d, word ptr [r8]
0x18001708a  test    r9w, r9w
0x18001708e  jz      short loc_1800170A4
0x180017090  mov     [rax], r9w
0x180017094  add     r8, 2
0x180017098  add     rax, 2
0x18001709c  sub     rcx, r10
0x18001709f  sub     rdx, r10
0x1800170a2  jnz     short loc_180017081
0x1800170a4  test    rdx, rdx
0x1800170a7  lea     rcx, [rax-2]
0x1800170ab  mov     ebx, 10h
0x1800170b0  lea     rdx, [rsp+200h+Size]; EndPtr
0x1800170b5  cmovnz  rcx, rax
0x1800170b9  mov     r8d, ebx; Radix
0x1800170bc  mov     [rcx], r13w
0x1800170c0  lea     rcx, [rbp+100h+String]; String
0x1800170c4  mov     [rbp+100h+var_98], r13w
0x1800170c9  call    cs:__imp_wcstoul
0x1800170cf  mov     r8d, ebx; Radix
0x1800170d2  mov     [rbp+100h+String], r13w
0x1800170d7  lea     rdx, [rsp+200h+Size]; EndPtr
0x1800170dc  mov     [rsi+73h], al
0x1800170df  lea     rcx, [rbp+100h+var_A0]; String
0x1800170e3  call    cs:__imp_wcstoul
0x1800170e9  mov     r8d, ebx; Radix
0x1800170ec  mov     [rbp+100h+var_A0], r13w
0x1800170f1  lea     rdx, [rsp+200h+Size]; EndPtr
0x1800170f6  mov     [rsi+72h], al
0x1800170f9  lea     rcx, [rbp+100h+var_A4]; String
0x1800170fd  call    cs:__imp_wcstoul
0x180017103  mov     r8d, ebx; Radix
0x180017106  mov     [rbp+100h+var_A4], r13w
0x18001710b  lea     rdx, [rsp+200h+Size]; EndPtr
0x180017110  mov     [rsi+71h], al
0x180017113  lea     rcx, [rbp+100h+var_A8]; String
0x180017117  call    cs:__imp_wcstoul
0x18001711d  mov     r8d, ebx; Radix
0x180017120  mov     [rbp+100h+var_A8], r13w
0x180017125  lea     rdx, [rsp+200h+Size]; EndPtr
0x18001712a  mov     [rsi+70h], al
0x18001712d  lea     rcx, [rbp+100h+var_AC]; String
0x180017131  call    cs:__imp_wcstoul
0x180017137  mov     r8d, ebx; Radix
0x18001713a  mov     [rbp+100h+var_AC], r13w
0x18001713f  lea     rdx, [rsp+200h+Size]; EndPtr
0x180017144  mov     [rsi+6Fh], al
0x180017147  lea     rcx, [rbp+100h+var_B0]; String
0x18001714b  call    cs:__imp_wcstoul
0x180017151  mov     r8d, ebx; Radix
0x180017154  mov     [rbp+100h+var_B2], r13w
0x180017159  lea     rdx, [rsp+200h+Size]; EndPtr
0x18001715e  mov     [rsi+6Eh], al
0x180017161  lea     rcx, [rbp+100h+var_B6]; String
0x180017165  call    cs:__imp_wcstoul
0x18001716b  mov     r8d, ebx; Radix
0x18001716e  mov     [rbp+100h+var_B6], r13w
0x180017173  lea     rdx, [rsp+200h+Size]; EndPtr
0x180017178  mov     [rsi+6Dh], al
0x18001717b  lea     rcx, [rbp+100h+var_BA]; String
0x18001717f  call    cs:__imp_wcstoul
0x180017185  mov     r8d, ebx; Radix
0x180017188  mov     [rbp+100h+var_BC], r13w
0x18001718d  lea     rdx, [rsp+200h+Size]; EndPtr
0x180017192  mov     [rsi+6Ch], al
0x180017195  lea     rcx, [rbp+100h+var_C4]; String
0x180017199  call    cs:__imp_wcstoul
0x18001719f  mov     r8d, ebx; Radix
0x1800171a2  mov     [rbp+100h+var_C6], r13w
0x1800171a7  lea     rdx, [rsp+200h+Size]; EndPtr
0x1800171ac  mov     [rsi+6Ah], ax
0x1800171b0  lea     rcx, [rbp+100h+var_CE]; String
0x1800171b4  call    cs:__imp_wcstoul
0x1800171ba  mov     r8d, ebx; Radix
0x1800171bd  mov     [rbp+100h+var_D0], r13w
0x1800171c2  lea     rdx, [rsp+200h+Size]; EndPtr
0x1800171c7  mov     [rsi+68h], ax
0x1800171cb  lea     rcx, [rbp+100h+var_E0]; String
0x1800171cf  call    cs:__imp_wcstoul
0x1800171d5  mov     [rsi+64h], eax
0x1800171d8  mov     ebx, r13d
0x1800171db  mov     eax, ebx
0x1800171dd  cmp     edi, 3
0x1800171e0  jnz     loc_180017300
0x1800171e6  cmp     ebx, 2
0x1800171e9  jnz     loc_18001735D
0x1800171ef  lea     rcx, [rsp+200h+Size]
0x1800171f4  mov     dword ptr [rsp+200h+Size], r13d
0x1800171f9  mov     r14d, r13d
0x1800171fc  call    lrGetProductType
  ... truncated ...
```
