# AppendDnsSuffixSearchListToGlobalList

- ea: `0x1800b06e4`
- end: `0x1800b1073`
- name: `AppendDnsSuffixSearchListToGlobalList`
- size: `2447`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x1800de7e0`
- `0x1800e0a90`
- `0x1800e0e34`

## callees

- `0x1800039ac`
- `0x1800039fc`
- `0x180005bfc`
- `0x1800adb64`
- `0x1800aefc8`
- `0x1800af2f8`
- `0x1800af408`
- `0x1800b00b4`
- `0x1800b06e4`
- `0x1800e8ef0`

## import_xrefs

- `msvcrt!wcstok_s` at `0x1800b0b3e`
- `msvcrt!wcstok_s` at `0x1800b0bd5`
- `msvcrt!wcstok_s` at `0x1800b0d49`
- `msvcrt!wcstok_s` at `0x1800b0b3e`
- `msvcrt!wcstok_s` at `0x1800b0bd5`
- `msvcrt!wcstok_s` at `0x1800b0d49`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800b07f1`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800b07f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b082b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b082b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1020`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1020`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b0a1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b0a1e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b08f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b09a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b08f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b09a3`
- `IPHLPAPI!FreeDnsSettings` at `0x1800b09fb`
- `IPHLPAPI!FreeDnsSettings` at `0x1800b09fb`
- `IPHLPAPI!SetDnsSettings` at `0x1800b0f9c`
- `IPHLPAPI!SetDnsSettings` at `0x1800b0f9c`
- `IPHLPAPI!GetDnsSettings` at `0x1800b0894`
- `IPHLPAPI!GetDnsSettings` at `0x1800b0894`

## string_xrefs

- `0x1800b07fd`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800b0804`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AppendDnsSuffixSearchListToGlobalList(__int64 a1, unsigned int a2)
{
  struct _LIST_ENTRY *v2; // rcx
  BYTE *v3; // rdi
  char IsStateSeparationEnabled; // al
  const WCHAR *v5; // rdx
  unsigned int DnsSettings; // eax
  unsigned int v7; // r12d
  struct _LIST_ENTRY *v8; // rcx
  __int64 v9; // rdx
  BYTE *v10; // rbx
  PWSTR SearchList; // rbx
  unsigned int v12; // eax
  unsigned int v13; // eax
  struct _LIST_ENTRY *v14; // rcx
  __int64 v15; // rdx
  __int64 result; // rax
  wchar_t *i; // rcx
  wchar_t *v18; // rax
  __int64 v19; // r8
  wchar_t *v20; // rax
  _QWORD *v21; // rdi
  _QWORD *v22; // rsi
  __int64 v23; // r8
  _QWORD *j; // rbx
  _WORD *v25; // rdx
  unsigned __int64 v26; // r10
  unsigned __int64 v27; // r8
  _QWORD *v28; // rcx
  _QWORD *k; // r15
  _QWORD *v30; // r13
  _QWORD *v31; // rbx
  __int64 v32; // rbx
  unsigned int m; // r15d
  __int64 v34; // rdx
  __int64 v35; // r8
  _QWORD *n; // rbx
  _WORD *v37; // rdx
  unsigned __int64 v38; // r9
  unsigned __int64 v39; // r8
  _QWORD *v40; // rcx
  bool v41; // zf
  __int64 v42; // rdx
  __int64 v43; // r8
  _QWORD *v44; // rdx
  WCHAR *p_Block; // rax
  const BYTE *p_lpData; // rcx
  BYTE *v47; // [rsp+30h] [rbp-1A8h]
  DWORD cbData; // [rsp+38h] [rbp-1A0h] BYREF
  int v49; // [rsp+3Ch] [rbp-19Ch]
  HKEY hKey; // [rsp+40h] [rbp-198h] BYREF
  wchar_t *Context; // [rsp+48h] [rbp-190h] BYREF
  BYTE *v52; // [rsp+50h] [rbp-188h]
  unsigned int v53; // [rsp+58h] [rbp-180h]
  __int64 v54; // [rsp+60h] [rbp-178h]
  char v55[8]; // [rsp+68h] [rbp-170h] BYREF
  __int128 v56; // [rsp+70h] [rbp-168h]
  __int64 v57; // [rsp+80h] [rbp-158h]
  DNS_SETTINGS v58; // [rsp+88h] [rbp-150h] BYREF
  DNS_SETTINGS Settings; // [rsp+B0h] [rbp-128h] BYREF
  char v60[8]; // [rsp+D8h] [rbp-100h] BYREF
  BYTE *lpData; // [rsp+E0h] [rbp-F8h] BYREF
  __int64 v62; // [rsp+F0h] [rbp-E8h]
  unsigned __int64 v63; // [rsp+F8h] [rbp-E0h]
  char v64[8]; // [rsp+100h] [rbp-D8h] BYREF
  void *v65; // [rsp+108h] [rbp-D0h]
  __int64 v66; // [rsp+118h] [rbp-C0h]
  unsigned __int64 v67; // [rsp+120h] [rbp-B8h]
  char v68[8]; // [rsp+128h] [rbp-B0h] BYREF
  void *Block; // [rsp+130h] [rbp-A8h] BYREF
  __int64 v70; // [rsp+140h] [rbp-98h]
  unsigned __int64 v71; // [rsp+148h] [rbp-90h]
  char v72[8]; // [rsp+150h] [rbp-88h] BYREF
  void *v73; // [rsp+158h] [rbp-80h] BYREF
  unsigned __int64 v74; // [rsp+168h] [rbp-70h]
  unsigned __int64 v75; // [rsp+170h] [rbp-68h]
  char v76[8]; // [rsp+178h] [rbp-60h] BYREF
  void *v77; // [rsp+180h] [rbp-58h] BYREF
  unsigned __int64 v78; // [rsp+190h] [rbp-48h]
  unsigned __int64 v79; // [rsp+198h] [rbp-40h]
  std::bad_alloc *v80; // [rsp+1A0h] [rbp-38h] BYREF

  v53 = a2;
  v54 = a1;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 10, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, a2);
  }
  v3 = 0;
  v47 = 0;
  v52 = 0;
  cbData = 0;
  memset(&Settings, 0, sizeof(Settings));
  memset(&v58, 0, sizeof(v58));
  hKey = 0;
  v56 = 0;
  v57 = 0;
  v63 = 7;
  v62 = 0;
  LOWORD(lpData) = 0;
  v71 = 7;
  v70 = 0;
  LOWORD(Block) = 0;
  Context = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v2);
  v5 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  if ( !IsStateSeparationEnabled )
    v5 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  DnsSettings = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20007u, &hKey);
  v7 = DnsSettings;
  if ( DnsSettings )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v9 = 11;
LABEL_12:
      WPP_SF_d(v8[1].Flink, v9, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, DnsSettings);
      v10 = 0;
      goto LABEL_33;
    }
    goto LABEL_32;
  }
  Settings.Version = 1;
  DnsSettings = GetDnsSettings(&Settings);
  if ( DnsSettings )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v9 = 12;
      goto LABEL_12;
    }
    goto LABEL_32;
  }
  SearchList = Settings.SearchList;
  v12 = RegQueryValueExW(hKey, L"AppendedDnsSuffixSearchList", 0, 0, 0, &cbData);
  v7 = v12;
  v49 = v12;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 13, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, v12);
    }
    if ( v7 != 2 )
    {
LABEL_32:
      v10 = v47;
      goto LABEL_33;
    }
  }
  if ( cbData )
  {
    try
    {
      v3 = (BYTE *)operator new(saturated_mul(cbData + 1, 2u));
      v47 = v3;
      v52 = v3;
    }
    catch ( std::bad_alloc *v80 )
    {
      v49 = 14;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 14, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, 14);
      }
      v10 = 0;
      goto LABEL_47;
    }
    v13 = RegQueryValueExW(hKey, L"AppendedDnsSuffixSearchList", 0, 0, v3, &cbData);
    v7 = v13;
    v49 = v13;
    if ( v13 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_32;
      }
      v15 = 15;
      goto LABEL_31;
    }
    *(_WORD *)&v3[2 * cbData] = 0;
  }
  try
  {
    if ( SearchList )
    {
      for ( i = SearchList; ; i = 0 )
      {
        v18 = wcstok_s(i, L",", &Context);
        if ( !v18 )
          break;
        v67 = 7;
        v66 = 0;
        LOWORD(v65) = 0;
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        std::wstring::assign(v64);
        std::vector<std::wstring>::push_back(v55, v64);
        if ( v67 >= 8 )
          operator delete(v65);
      }
    }
    if ( v3 )
    {
      v20 = wcstok_s((wchar_t *)v3, L",", &Context);
      v21 = (_QWORD *)*((_QWORD *)&v56 + 1);
      v22 = (_QWORD *)v56;
      while ( v20 )
      {
        v75 = 7;
        v74 = 0;
        LOWORD(v73) = 0;
        v23 = -1;
        do
          ++v23;
        while ( v20[v23] );
        std::wstring::assign(v72);
        for ( j = v22; j != v21; j += 5 )
        {
          v25 = &v73;
          if ( v75 >= 8 )
            v25 = v73;
          v26 = j[3];
          v27 = v74;
          if ( v26 < v74 )
            v27 = j[3];
          v28 = j + 1;
          if ( j[4] >= 8u )
            v28 = (_QWORD *)*v28;
          if ( v27 )
          {
            while ( *(_WORD *)v28 == *v25 )
            {
              v28 = (_QWORD *)((char *)v28 + 2);
              ++v25;
              if ( !--v27 )
                goto LABEL_72;
            }
          }
          else
          {
LABEL_72:
            if ( v26 >= v74 && v26 == v74 )
              break;
          }
        }
        if ( v75 >= 8 )
          operator delete(v73);
        v75 = 7;
        v74 = 0;
        LOWORD(v73) = 0;
        if ( j != v21 )
        {
          for ( k = j + 5; k != v21; k += 5 )
          {
            std::wstring::assign(j, k, 0, -1);
            j += 5;
          }
          v30 = v21 - 5;
          v31 = v21 - 5;
          do
          {
            if ( v31[4] >= 8u )
              operator delete((void *)v31[1]);
            v31[4] = 7;
            v31[3] = 0;
            *((_WORD *)v31 + 4) = 0;
            v31 += 5;
          }
          while ( v31 != v21 );
          v21 -= 5;
          *((_QWORD *)&v56 + 1) = v30;
        }
        v20 = wcstok_s(0, L",", &Context);
      }
    }
    else
    {
      v21 = (_QWORD *)*((_QWORD *)&v56 + 1);
      v22 = (_QWORD *)v56;
    }
    v32 = v54;
    if ( v54 )
    {
      for ( m = 0; m < v53; ++m )
      {
        v34 = *(_QWORD *)(v32 + 8LL * m);
        v79 = 7;
        v78 = 0;
        LOWORD(v77) = 0;
        v35 = -1;
        do
          ++v35;
        while ( *(_WORD *)(v34 + 2 * v35) );
        std::wstring::assign(v76);
        for ( n = v22; n != v21; n += 5 )
        {
          v37 = &v77;
          if ( v79 >= 8 )
            v37 = v77;
          v38 = n[3];
          v39 = v78;
          if ( v38 < v78 )
            v39 = n[3];
          v40 = n + 1;
          if ( n[4] >= 8u )
            v40 = (_QWORD *)*v40;
          if ( v39 )
          {
            while ( *(_WORD *)v40 == *v37 )
            {
              v40 = (_QWORD *)((char *)v40 + 2);
              ++v37;
              if ( !--v39 )
                goto LABEL_104;
            }
          }
          else
          {
LABEL_104:
            if ( v38 >= v78 && v38 == v78 )
              break;
          }
        }
        if ( v79 >= 8 )
          operator delete(v77);
        v41 = n == v21;
        v32 = v54;
        if ( v41 )
        {
          v42 = *(_QWORD *)(v54 + 8LL * m);
          v67 = 7;
          v66 = 0;
          LOWORD(v65) = 0;
          v43 = -1;
          do
            ++v43;
          while ( *(_WORD *)(v42 + 2 * v43) );
          std::wstring::assign(v64);
          std::vector<std::wstring>::push_back(v55, v64);
          if ( v67 >= 8 )
            operator delete(v65);
          LOWORD(v65) = 0;
          if ( v62 )
            std::wstring::append(v60, L",");
          std::wstring::append(v60, *(_QWORD *)(v32 + 8LL * m));
          v21 = (_QWORD *)*((_QWORD *)&v56 + 1);
          v22 = (_QWORD *)v56;
        }
      }
    }
    while ( v22 != v21 )
    {
      if ( v70 )
        std::wstring::append(v68, L",");
      v44 = v22 + 1;
      if ( v22[4] >= 8u )
        v44 = (_QWORD *)*v44;
      std::wstring::append(v68, v44);
      v22 += 5;
    }
  }
  catch ( ... )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 16, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, 14);
    }
    v10 = v52;
LABEL_47:
    v7 = v49;
LABEL_33:
    FreeDnsSettings(&Settings);
    if ( v10 )
      operator delete(v10);
    if ( hKey )
      RegCloseKey(hKey);
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 19, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, v7);
    }
    if ( v71 >= 8 )
      operator delete(Block);
    v71 = 7;
    v70 = 0;
    LOWORD(Block) = 0;
    if ( v63 >= 8 )
      operator delete(lpData);
    v63 = 7;
    v62 = 0;
    LOWORD(lpData) = 0;
    std::vector<std::wstring>::~vector<std::wstring>(v55);
    result = v7;
  }
  v58.Version = 1;
  v58.Flags = 4;
  p_Block = (WCHAR *)&Block;
  if ( v71 >= 8 )
    p_Block = (WCHAR *)Block;
  v58.SearchList = p_Block;
  v13 = SetDnsSettings(&v58);
  if ( v13 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_32;
    }
    v15 = 17;
  }
  else
  {
    p_lpData = (const BYTE *)&lpData;
    if ( v63 >= 8 )
      p_lpData = lpData;
    v13 = RegSetValueExW(hKey, L"AppendedDnsSuffixSearchList", 0, 1u, p_lpData, 2 * v62 + 2);
    v7 = v13;
    if ( !v13 )
      goto LABEL_32;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_32;
    }
    v15 = 18;
  }
LABEL_31:
  WPP_SF_d(v14[1].Flink, v15, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids, v13);
  goto LABEL_32;
}

```

## disassembly

```asm
0x1800b06e4  mov     [rsp+arg_10], rbx
0x1800b06e9  mov     [rsp+arg_18], rsi
0x1800b06ee  push    rdi
0x1800b06ef  push    r12
0x1800b06f1  push    r13
0x1800b06f3  push    r14
0x1800b06f5  push    r15
0x1800b06f7  sub     rsp, 1B0h
0x1800b06fe  mov     rax, cs:__security_cookie
0x1800b0705  xor     rax, rsp
0x1800b0708  mov     [rsp+1D8h+var_30], rax
0x1800b0710  mov     eax, edx
0x1800b0712  mov     [rsp+1D8h+var_180], edx
0x1800b0716  mov     [rsp+1D8h+var_178], rcx
0x1800b071b  lea     r13, WPP_GLOBAL_Control
0x1800b0722  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0729  cmp     rcx, r13
0x1800b072c  jz      short loc_1800B0752
0x1800b072e  test    byte ptr [rcx+1Ch], 1
0x1800b0732  jz      short loc_1800B0752
0x1800b0734  cmp     byte ptr [rcx+19h], 6
0x1800b0738  jb      short loc_1800B0752
0x1800b073a  mov     edx, 0Ah
0x1800b073f  mov     r9d, eax
0x1800b0742  lea     r8, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids
0x1800b0749  mov     rcx, [rcx+10h]
0x1800b074d  call    WPP_SF_d
0x1800b0752  xor     r14d, r14d
0x1800b0755  mov     edi, r14d
0x1800b0758  mov     [rsp+1D8h+var_1A8], r14
0x1800b075d  mov     [rsp+1D8h+var_188], r14
0x1800b0762  mov     [rsp+1D8h+cbData], r14d
0x1800b0767  xorps   xmm0, xmm0
0x1800b076a  xor     eax, eax
0x1800b076c  movups  xmmword ptr [rsp+1D8h+Settings.Version], xmm0
0x1800b0774  movups  xmmword ptr [rsp+1D8h+Settings.Hostname], xmm0
0x1800b077c  mov     [rsp+1D8h+Settings.SearchList], rax
0x1800b0784  xorps   xmm1, xmm1
0x1800b0787  movups  xmmword ptr [rsp+1D8h+var_150.Version], xmm1
0x1800b078f  movups  xmmword ptr [rsp+1D8h+var_150.Hostname], xmm1
0x1800b0797  mov     [rsp+1D8h+var_150.SearchList], rax
0x1800b079f  mov     [rsp+1D8h+hKey], r14
0x1800b07a4  movdqu  [rsp+1D8h+var_168], xmm0
0x1800b07aa  mov     [rsp+1D8h+var_158], r14
0x1800b07b2  mov     [rsp+1D8h+var_E0], 7
0x1800b07be  mov     [rsp+1D8h+var_E8], r14
0x1800b07c6  mov     word ptr [rsp+1D8h+lpData], r14w
0x1800b07cf  mov     [rsp+1D8h+var_90], 7
0x1800b07db  mov     [rsp+1D8h+var_98], r14
0x1800b07e3  mov     word ptr [rsp+1D8h+Block], r14w
0x1800b07ec  mov     [rsp+1D8h+Context], r14
0x1800b07f1  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800b07f8  nop     dword ptr [rax+rax+00h]
0x1800b07fd  lea     rcx, aSystemCurrentc_21; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800b0804  lea     rdx, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800b080b  test    al, al
0x1800b080d  cmovz   rdx, rcx; lpSubKey
0x1800b0811  lea     rax, [rsp+1D8h+hKey]
0x1800b0816  mov     [rsp+1D8h+phkResult], rax; phkResult
0x1800b081b  mov     r9d, 20007h; samDesired
0x1800b0821  xor     r8d, r8d; ulOptions
0x1800b0824  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b082b  call    cs:__imp_RegOpenKeyExW
0x1800b0832  nop     dword ptr [rax+rax+00h]
0x1800b0837  mov     r12d, eax
0x1800b083a  test    eax, eax
0x1800b083c  jz      short loc_1800B0881
0x1800b083e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0845  cmp     rcx, r13
0x1800b0848  jz      loc_1800B09EE
0x1800b084e  test    byte ptr [rcx+1Ch], 1
0x1800b0852  jz      loc_1800B09EE
0x1800b0858  cmp     byte ptr [rcx+19h], 2
0x1800b085c  jb      loc_1800B09EE
0x1800b0862  lea     edx, [r14+0Bh]
0x1800b0866  mov     r9d, eax
0x1800b0869  lea     r8, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids
0x1800b0870  mov     rcx, [rcx+10h]
0x1800b0874  call    WPP_SF_d
0x1800b0879  mov     rbx, r14
0x1800b087c  jmp     loc_1800B09F3
0x1800b0881  mov     [rsp+1D8h+Settings.Version], 1
0x1800b088c  lea     rcx, [rsp+1D8h+Settings]; Settings
0x1800b0894  call    cs:__imp_GetDnsSettings
0x1800b089b  nop     dword ptr [rax+rax+00h]
0x1800b08a0  test    eax, eax
0x1800b08a2  jz      short loc_1800B08CF
0x1800b08a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b08ab  cmp     rcx, r13
0x1800b08ae  jz      loc_1800B09EE
0x1800b08b4  test    byte ptr [rcx+1Ch], 1
0x1800b08b8  jz      loc_1800B09EE
0x1800b08be  cmp     byte ptr [rcx+19h], 2
0x1800b08c2  jb      loc_1800B09EE
0x1800b08c8  mov     edx, 0Ch
0x1800b08cd  jmp     short loc_1800B0866
0x1800b08cf  mov     rbx, [rsp+1D8h+Settings.SearchList]
0x1800b08d7  lea     rax, [rsp+1D8h+cbData]
0x1800b08dc  mov     [rsp+1D8h+lpcbData], rax; lpcbData
0x1800b08e1  mov     [rsp+1D8h+phkResult], r14; lpData
0x1800b08e6  xor     r9d, r9d; lpType
0x1800b08e9  xor     r8d, r8d; lpReserved
0x1800b08ec  lea     rdx, aAppendeddnssuf; "AppendedDnsSuffixSearchList"
0x1800b08f3  mov     rcx, [rsp+1D8h+hKey]; hKey
0x1800b08f8  call    cs:__imp_RegQueryValueExW
0x1800b08ff  nop     dword ptr [rax+rax+00h]
0x1800b0904  mov     r12d, eax
0x1800b0907  mov     [rsp+1D8h+var_19C], eax
0x1800b090b  test    eax, eax
0x1800b090d  jz      short loc_1800B0949
0x1800b090f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0916  cmp     rcx, r13
0x1800b0919  jz      short loc_1800B093F
0x1800b091b  test    byte ptr [rcx+1Ch], 1
0x1800b091f  jz      short loc_1800B093F
0x1800b0921  cmp     byte ptr [rcx+19h], 2
0x1800b0925  jb      short loc_1800B093F
0x1800b0927  mov     edx, 0Dh
0x1800b092c  mov     r9d, eax
0x1800b092f  lea     r8, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids
0x1800b0936  mov     rcx, [rcx+10h]
0x1800b093a  call    WPP_SF_d
0x1800b093f  cmp     r12d, 2
0x1800b0943  jnz     loc_1800B09EE
0x1800b0949  cmp     [rsp+1D8h+cbData], r14d
0x1800b094e  jbe     loc_1800B0B22
0x1800b0954  mov     ecx, [rsp+1D8h+cbData]
0x1800b0958  inc     ecx
0x1800b095a  mov     eax, 2
0x1800b095f  mul     rcx
0x1800b0962  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800b0969  cmovb   rax, rsi
0x1800b096d  mov     rcx, rax; Size
0x1800b0970  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b0975  mov     rdi, rax
0x1800b0978  mov     [rsp+1D8h+var_1A8], rax
0x1800b097d  mov     [rsp+1D8h+var_188], rax
0x1800b0982  lea     rax, [rsp+1D8h+cbData]
0x1800b0987  mov     [rsp+1D8h+lpcbData], rax; lpcbData
0x1800b098c  mov     [rsp+1D8h+phkResult], rdi; lpData
0x1800b0991  xor     r9d, r9d; lpType
0x1800b0994  xor     r8d, r8d; lpReserved
0x1800b0997  lea     rdx, aAppendeddnssuf; "AppendedDnsSuffixSearchList"
0x1800b099e  mov     rcx, [rsp+1D8h+hKey]; hKey
0x1800b09a3  call    cs:__imp_RegQueryValueExW
0x1800b09aa  nop     dword ptr [rax+rax+00h]
0x1800b09af  mov     r12d, eax
0x1800b09b2  mov     [rsp+1D8h+var_19C], eax
0x1800b09b6  test    eax, eax
0x1800b09b8  jz      loc_1800B0B00
0x1800b09be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b09c5  cmp     rcx, r13
0x1800b09c8  jz      short loc_1800B09EE
0x1800b09ca  test    byte ptr [rcx+1Ch], 1
0x1800b09ce  jz      short loc_1800B09EE
0x1800b09d0  cmp     byte ptr [rcx+19h], 2
0x1800b09d4  jb      short loc_1800B09EE
0x1800b09d6  mov     edx, 0Fh
0x1800b09db  mov     r9d, eax
0x1800b09de  lea     r8, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids
0x1800b09e5  mov     rcx, [rcx+10h]
0x1800b09e9  call    WPP_SF_d
0x1800b09ee  mov     rbx, [rsp+1D8h+var_1A8]
0x1800b09f3  lea     rcx, [rsp+1D8h+Settings]; Settings
0x1800b09fb  call    cs:__imp_FreeDnsSettings
0x1800b0a02  nop     dword ptr [rax+rax+00h]
0x1800b0a07  test    rbx, rbx
0x1800b0a0a  jz      short loc_1800B0A14
0x1800b0a0c  mov     rcx, rbx; Block
0x1800b0a0f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b0a14  mov     rcx, [rsp+1D8h+hKey]; hKey
0x1800b0a19  test    rcx, rcx
0x1800b0a1c  jz      short loc_1800B0A2A
0x1800b0a1e  call    cs:__imp_RegCloseKey
0x1800b0a25  nop     dword ptr [rax+rax+00h]
0x1800b0a2a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0a31  cmp     rcx, r13
0x1800b0a34  jz      short loc_1800B0A5B
0x1800b0a36  test    byte ptr [rcx+1Ch], 1
0x1800b0a3a  jz      short loc_1800B0A5B
0x1800b0a3c  cmp     byte ptr [rcx+19h], 6
0x1800b0a40  jb      short loc_1800B0A5B
0x1800b0a42  mov     edx, 13h
0x1800b0a47  mov     r9d, r12d
0x1800b0a4a  lea     r8, WPP_3de79e80536e36f8d8b993792bf9b1d7_Traceguids
0x1800b0a51  mov     rcx, [rcx+10h]
0x1800b0a55  call    WPP_SF_d
0x1800b0a5a  nop
0x1800b0a5b  cmp     [rsp+1D8h+var_90], 8
0x1800b0a64  jb      short loc_1800B0A73
0x1800b0a66  mov     rcx, [rsp+1D8h+Block]; Block
0x1800b0a6e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b0a73  mov     [rsp+1D8h+var_90], 7
0x1800b0a7f  mov     [rsp+1D8h+var_98], r14
0x1800b0a87  mov     word ptr [rsp+1D8h+Block], r14w
0x1800b0a90  cmp     [rsp+1D8h+var_E0], 8
0x1800b0a99  jb      short loc_1800B0AA8
0x1800b0a9b  mov     rcx, [rsp+1D8h+lpData]; Block
0x1800b0aa3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b0aa8  mov     [rsp+1D8h+var_E0], 7
0x1800b0ab4  mov     [rsp+1D8h+var_E8], r14
0x1800b0abc  mov     word ptr [rsp+1D8h+lpData], r14w
0x1800b0ac5  lea     rcx, [rsp+1D8h+var_170]
0x1800b0aca  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x1800b0acf  mov     eax, r12d
0x1800b0ad2  mov     rcx, [rsp+1D8h+var_30]
0x1800b0ada  xor     rcx, rsp; StackCookie
0x1800b0add  call    __security_check_cookie
0x1800b0ae2  lea     r11, [rsp+1D8h+var_28]
0x1800b0aea  mov     rbx, [r11+40h]
0x1800b0aee  mov     rsi, [r11+48h]
0x1800b0af2  mov     rsp, r11
0x1800b0af5  pop     r15
0x1800b0af7  pop     r14
0x1800b0af9  pop     r13
0x1800b0afb  pop     r12
0x1800b0afd  pop     rdi
0x1800b0afe  retn
0x1800b0b00  mov     eax, [rsp+1D8h+cbData]
0x1800b0b04  mov     [rdi+rax*2], r14w
0x1800b0b09  jmp     short loc_1800B0B26
0x1800b0b0b  xor     r14d, r14d
0x1800b0b0e  mov     ebx, r14d
0x1800b0b11  lea     r13, WPP_GLOBAL_Control
0x1800b0b18  mov     r12d, [rsp+1D8h+var_19C]
0x1800b0b1d  jmp     loc_1800B09F3
0x1800b0b22  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800b0b26  test    rbx, rbx
0x1800b0b29  jz      loc_1800B0BBD
0x1800b0b2f  mov     rcx, rbx; String
0x1800b0b32  lea     r8, [rsp+1D8h+Context]; Context
0x1800b0b37  lea     rdx, Delimiter; ","
0x1800b0b3e  call    cs:__imp_wcstok_s
0x1800b0b45  nop     dword ptr [rax+rax+00h]
0x1800b0b4a  test    rax, rax
0x1800b0b4d  jz      short loc_1800B0BBD
0x1800b0b4f  mov     [rsp+1D8h+var_B8], 7
0x1800b0b5b  mov     [rsp+1D8h+var_C0], r14
0x1800b0b63  mov     word ptr [rsp+1D8h+var_D0], r14w
0x1800b0b6c  mov     r8, rsi
0x1800b0b6f  inc     r8
0x1800b0b72  cmp     [rax+r8*2], r14w
0x1800b0b77  jnz     short loc_1800B0B6F
0x1800b0b79  mov     rdx, rax
0x1800b0b7c  lea     rcx, [rsp+1D8h+var_D8]
0x1800b0b84  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800b0b89  nop
0x1800b0b8a  lea     rdx, [rsp+1D8h+var_D8]
0x1800b0b92  lea     rcx, [rsp+1D8h+var_170]
0x1800b0b97  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x1800b0b9c  nop
0x1800b0b9d  cmp     [rsp+1D8h+var_B8], 8
0x1800b0ba6  jb      short loc_1800B0BB6
0x1800b0ba8  mov     rcx, [rsp+1D8h+var_D0]; Block
0x1800b0bb0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b0bb5  nop
0x1800b0bb6  xor     ecx, ecx
0x1800b0bb8  jmp     loc_1800B0B32
0x1800b0bbd  test    rdi, rdi
0x1800b0bc0  jz      loc_1800B0D5A
0x1800b0bc6  lea     r8, [rsp+1D8h+Context]; Context
0x1800b0bcb  lea     rdx, Delimiter; ","
0x1800b0bd2  mov     rcx, rdi; String
0x1800b0bd5  call    cs:__imp_wcstok_s
0x1800b0bdc  nop     dword ptr [rax+rax+00h]
0x1800b0be1  mov     rdi, qword ptr [rsp+1D8h+var_168+8]
0x1800b0be6  mov     rsi, qword ptr [rsp+1D8h+var_168]
0x1800b0beb  test    rax, rax
0x1800b0bee  jz      loc_1800B0D66
0x1800b0bf4  mov     r15d, 7
0x1800b0bfa  mov     [rsp+1D8h+var_68], r15
0x1800b0c02  mov     [rsp+1D8h+var_70], r14
0x1800b0c0a  mov     word ptr [rsp+1D8h+var_80], r14w
0x1800b0c13  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800b0c17  mov     r8, r13
0x1800b0c1a  inc     r8
0x1800b0c1d  cmp     [rax+r8*2], r14w
0x1800b0c22  jnz     short loc_1800B0C1A
0x1800b0c24  mov     rdx, rax
0x1800b0c27  lea     rcx, [rsp+1D8h+var_88]
0x1800b0c2f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800b0c34  nop
0x1800b0c35  mov     rbx, rsi
0x1800b0c38  mov     r9, [rsp+1D8h+var_70]
0x1800b0c40  cmp     rbx, rdi
0x1800b0c43  jz      short loc_1800B0CA3
0x1800b0c45  lea     rdx, [rsp+1D8h+var_80]
0x1800b0c4d  cmp     [rsp+1D8h+var_68], 8
0x1800b0c56  cmovnb  rdx, [rsp+1D8h+var_80]
0x1800b0c5f  mov     r10, [rbx+18h]
0x1800b0c63  mov     r8, r9
0x1800b0c66  cmp     r10, r9
0x1800b0c69  cmovb   r8, r10
0x1800b0c6d  lea     rcx, [rbx+8]
0x1800b0c71  cmp     qword ptr [rbx+20h], 8
0x1800b0c76  jb      short loc_1800B0C7B
0x1800b0c78  mov     rcx, [rcx]
0x1800b0c7b  test    r8, r8
0x1800b0c7e  jz      short loc_1800B0C96
0x1800b0c80  movzx   eax, word ptr [rdx]
  ... truncated ...
```
