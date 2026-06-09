# DDMGetAddressesFromRegistry

- ea: `0x180009270`
- end: `0x1800098fb`
- name: `DDMGetAddressesFromRegistry`
- size: `1675`
- prototype: `__int64 __fastcall(struct _GUID *, wchar_t *String1)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009ab0`

## callees

- `0x180007b7c`
- `0x180008f74`
- `0x180009270`
- `0x18000995c`
- `0x18000a4dc`
- `0x18000a7a4`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `msvcrt!malloc` at `0x180009555`
- `msvcrt!malloc` at `0x180009555`
- `msvcrt!free` at `0x1800095cd`
- `msvcrt!free` at `0x1800095cd`
- `msvcrt!_wcsicmp` at `0x180009456`
- `msvcrt!_wcsicmp` at `0x180009456`
- `KERNEL32!LocalFree` at `0x1800098a1`
- `KERNEL32!LocalFree` at `0x1800098bd`
- `KERNEL32!LocalFree` at `0x1800098d0`
- `KERNEL32!LocalFree` at `0x1800098a1`
- `KERNEL32!LocalFree` at `0x1800098bd`
- `KERNEL32!LocalFree` at `0x1800098d0`
- `KERNEL32!LocalAlloc` at `0x180009671`
- `KERNEL32!LocalAlloc` at `0x180009671`
- `ADVAPI32!RegQueryValueExW` at `0x180009528`
- `ADVAPI32!RegQueryValueExW` at `0x180009593`
- `ADVAPI32!RegQueryValueExW` at `0x180009528`
- `ADVAPI32!RegQueryValueExW` at `0x180009593`
- `ADVAPI32!RegCloseKey` at `0x180009469`
- `ADVAPI32!RegCloseKey` at `0x180009879`
- `ADVAPI32!RegCloseKey` at `0x18000988e`
- `ADVAPI32!RegCloseKey` at `0x180009469`
- `ADVAPI32!RegCloseKey` at `0x180009879`
- `ADVAPI32!RegCloseKey` at `0x18000988e`

## string_xrefs

- `0x18000932f`: `DDMGetAddressesFromRegistry: Failed to open interfaces key, status = %d`
- `0x1800093ec`: `DDMGetAddressesFromRegistry: RegOpenInterfaceKey failed for keyIndex = %d, error = %d`
- `0x1800097bb`: `DDMGetAddressesFromRegistry: Invalid Value of S2S_PBK_INFO in Registry - %d`
- `0x180009838`: `DDMGetAddressesFromRegistry: Invalid Value of S2S_PBK_INFO in Registry - %d`
- `0x1800095e8`: `DDMGetAddressesFromRegistry: GetDestinationInfo failed with error = %d`
- `0x180009494`: `DDMGetAddressesFromRegistry: No interface with name (%s) found`
- `0x1800096d0`: `DDMGetAddressesFromRegistry: ResolveIpAddress failed for %s. error: %d`

## pseudocode

```c
__int64 __fastcall DDMGetAddressesFromRegistry(struct _GUID *a1, wchar_t *String1, unsigned int *a3, _QWORD *a4)
{
  LPWSTR *v8; // r12
  unsigned int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // r8
  __int64 v12; // rsi
  DWORD v13; // ebx
  __int64 v14; // rsi
  unsigned int v15; // eax
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // r8
  unsigned int v19; // r13d
  BYTE *lpData; // rbx
  unsigned int v21; // eax
  __int64 v22; // r8
  char *v23; // rbx
  unsigned int v24; // r12d
  SIZE_T v25; // rbx
  unsigned int v26; // r15d
  char *v27; // rax
  size_t v28; // r8
  bool v29; // zf
  __int64 v30; // rbx
  DWORD v31; // eax
  __int64 v32; // r8
  __int64 v33; // rax
  char *v34; // rax
  __int64 v35; // r8
  unsigned int v36; // esi
  unsigned int v37; // ebx
  unsigned int DestinationInfo; // [rsp+30h] [rbp-D0h]
  char *v40; // [rsp+38h] [rbp-C8h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v43; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v44; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v47; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v48; // [rsp+68h] [rbp-98h]
  unsigned int *v49; // [rsp+70h] [rbp-90h]
  _BYTE v50[16]; // [rsp+78h] [rbp-88h] BYREF
  int *v51; // [rsp+88h] [rbp-78h]
  int v52; // [rsp+90h] [rbp-70h]
  int v53; // [rsp+94h] [rbp-6Ch]
  int v54; // [rsp+A0h] [rbp-60h] BYREF
  char v55[2044]; // [rsp+A4h] [rbp-5Ch] BYREF
  wchar_t String2[264]; // [rsp+8A0h] [rbp+7A0h] BYREF

  v49 = a3;
  v48 = a4;
  v54 = 0;
  memset_0(v55, 0, sizeof(v55));
  *a4 = 0;
  v40 = 0;
  v47 = 0;
  v44 = 0;
  v8 = 0;
  hMem = 0;
  v43 = 0;
  hKey = 0;
  *a3 = 0;
  v9 = OpenRDInterfacesKey(a1, &v47, &v44);
  DestinationInfo = v9;
  v10 = v9;
  if ( v9 )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v54) = 0;
      FormatRRASErrorString(&v54, L"DDMGetAddressesFromRegistry: Failed to open interfaces key, status = %d", v9);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v12 = -1;
        do
          ++v12;
        while ( *(_WORD *)&v55[2 * v12 - 4] );
        v53 = 0;
        v52 = 2 * v12 + 2;
        v51 = &v54;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v11, 2, v50);
LABEL_61:
        v23 = 0;
        goto LABEL_62;
      }
    }
LABEL_47:
    v23 = v40;
    goto LABEL_62;
  }
  v13 = 0;
  v14 = -1;
  if ( !v44 )
  {
LABEL_17:
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v54) = 0;
      FormatRRASErrorString(&v54, L"DDMGetAddressesFromRegistry: No interface with name (%s) found", String1);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        do
          ++v14;
        while ( *(_WORD *)&v55[2 * v14 - 4] );
        v53 = 0;
        v52 = 2 * v14 + 2;
        v51 = &v54;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v18, 2, v50);
      }
    }
    v10 = 2;
    DestinationInfo = 2;
    goto LABEL_61;
  }
  while ( 1 )
  {
    v15 = RegOpenRDInterfaceKey(v47, v13, &hKey, (LPBYTE)String2);
    if ( v15 )
    {
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v54) = 0;
        FormatRRASErrorString(
          &v54,
          L"DDMGetAddressesFromRegistry: RegOpenInterfaceKey failed for keyIndex = %d, error = %d",
          v13,
          v15);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v17 = -1;
          do
            ++v17;
          while ( *(_WORD *)&v55[2 * v17 - 4] );
          v53 = 0;
          v52 = 2 * v17 + 2;
          v51 = &v54;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v16, 2, v50);
        }
      }
      goto LABEL_16;
    }
    if ( !_wcsicmp(String1, String2) )
      break;
    RegCloseKey(hKey);
    hKey = 0;
LABEL_16:
    if ( ++v13 >= v44 )
      goto LABEL_17;
  }
  v19 = 0;
  cbData = 0;
  Type = 0;
  DestinationInfo = RegQueryValueExW(hKey, L"InterfaceInfoPbk", 0, &Type, 0, &cbData);
  v10 = DestinationInfo;
  if ( DestinationInfo || Type != 3 || !cbData )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v54) = 0;
      FormatRRASErrorString(
        &v54,
        L"DDMGetAddressesFromRegistry: Invalid Value of S2S_PBK_INFO in Registry - %d",
        DestinationInfo);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        do
          ++v14;
        while ( *(_WORD *)&v55[2 * v14 - 4] );
        goto LABEL_53;
      }
    }
LABEL_54:
    if ( !v10 )
    {
      v10 = 1015;
      DestinationInfo = 1015;
    }
    goto LABEL_61;
  }
  lpData = (BYTE *)malloc(cbData);
  if ( !lpData )
  {
    v10 = 8;
    DestinationInfo = 8;
    goto LABEL_61;
  }
  v21 = RegQueryValueExW(hKey, L"InterfaceInfoPbk", 0, &Type, lpData, &cbData);
  DestinationInfo = v21;
  v10 = v21;
  if ( v21 || Type != 3 )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v54) = 0;
      FormatRRASErrorString(&v54, L"DDMGetAddressesFromRegistry: Invalid Value of S2S_PBK_INFO in Registry - %d", v21);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        do
          ++v14;
        while ( *(_WORD *)&v55[2 * v14 - 4] );
LABEL_53:
        v53 = 0;
        v52 = 2 * v14 + 2;
        v51 = &v54;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v35, 2, v50);
        goto LABEL_54;
      }
    }
    goto LABEL_54;
  }
  DestinationInfo = GetDestinationInfo(lpData, &hMem, &v43);
  v10 = DestinationInfo;
  free(lpData);
  if ( !DestinationInfo )
  {
    v24 = v43;
    DestinationInfo = 0;
    v25 = 32LL * v43;
    v26 = 0;
    v10 = 0;
    v27 = (char *)LocalAlloc(0x40u, v25);
    v28 = v25;
    v40 = v27;
    v23 = v27;
    memset_0(v27, 0, v28);
    v29 = v24 == 0;
    v8 = (LPWSTR *)hMem;
    if ( v29 )
      goto LABEL_62;
    do
    {
      v30 = 32LL * v26;
      v31 = ResolveIpAddress(v8[v19], (struct _ROUTER_IP_ADDRESS *)&v40[v30 + 8]);
      cbData = v31;
      if ( v31 )
      {
        if ( (byte_1800C8404 & 8) != 0 )
        {
          LOWORD(v54) = 0;
          FormatRRASErrorString(
            &v54,
            L"DDMGetAddressesFromRegistry: ResolveIpAddress failed for %s. error: %d",
            v8[v19],
            v31);
          if ( (byte_1800C8404 & 8) != 0 )
          {
            v33 = -1;
            do
              ++v33;
            while ( *(_WORD *)&v55[2 * v33 - 4] );
            v53 = 0;
            v52 = 2 * v33 + 2;
            v51 = &v54;
            McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v32, 2, v50);
          }
          v31 = cbData;
        }
        if ( !v10 )
          v10 = v31;
        v34 = v40;
      }
      else
      {
        v34 = v40;
        ++v26;
        *(_WORD *)&v40[v30] = 1;
      }
      ++v19;
    }
    while ( v19 < v43 );
    DestinationInfo = v10;
    if ( v26 )
    {
      v23 = 0;
      *v48 = v34;
      *v49 = v26;
      goto LABEL_62;
    }
    goto LABEL_47;
  }
  if ( (byte_1800C8404 & 8) != 0 )
  {
    LOWORD(v54) = 0;
    FormatRRASErrorString(
      &v54,
      L"DDMGetAddressesFromRegistry: GetDestinationInfo failed with error = %d",
      DestinationInfo);
    if ( (byte_1800C8404 & 8) != 0 )
    {
      do
        ++v14;
      while ( *(_WORD *)&v55[2 * v14 - 4] );
      v53 = 0;
      v52 = 2 * v14 + 2;
      v51 = &v54;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v22, 2, v50);
    }
  }
  v8 = (LPWSTR *)hMem;
  v23 = 0;
LABEL_62:
  if ( v47 )
  {
    RegCloseKey(v47);
    v47 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v23 )
    LocalFree(v23);
  if ( v8 )
  {
    v36 = v43;
    v37 = 0;
    if ( v43 )
    {
      do
        LocalFree(v8[v37++]);
      while ( v37 < v36 );
      v10 = DestinationInfo;
    }
    LocalFree(v8);
  }
  return v10;
}

```

## disassembly

```asm
0x180009270  push    rbp
0x180009272  push    rbx
0x180009273  push    rsi
0x180009274  push    rdi
0x180009275  push    r12
0x180009277  push    r13
0x180009279  push    r14
0x18000927b  push    r15
0x18000927d  lea     rbp, [rsp-9C8h]
0x180009285  sub     rsp, 0AC8h
0x18000928c  mov     rax, cs:__security_cookie
0x180009293  xor     rax, rsp
0x180009296  mov     [rbp+0A00h+var_50], rax
0x18000929d  mov     rdi, r8
0x1800092a0  mov     [rsp+0B00h+var_A90], r8
0x1800092a5  mov     r13, rdx
0x1800092a8  mov     [rsp+0B00h+var_A98], r9
0x1800092ad  mov     rbx, rcx
0x1800092b0  xor     r14d, r14d
0x1800092b3  xor     edx, edx; Val
0x1800092b5  mov     [rbp+0A00h+var_A60], r14d
0x1800092b9  mov     r8d, 7FCh; Size
0x1800092bf  lea     rcx, [rbp+0A00h+var_A5C]; void *
0x1800092c3  mov     rsi, r9
0x1800092c6  call    memset_0
0x1800092cb  mov     [rsi], r14
0x1800092ce  lea     r8, [rsp+0B00h+var_AB4]; unsigned int *
0x1800092d3  lea     rdx, [rsp+0B00h+var_AA0]; HKEY *
0x1800092d8  mov     [rsp+0B00h+var_AC8], r14
0x1800092dd  mov     rcx, rbx; struct _GUID *
0x1800092e0  mov     [rsp+0B00h+var_AA0], r14
0x1800092e5  mov     [rsp+0B00h+var_AB4], r14d
0x1800092ea  mov     r12d, r14d
0x1800092ed  mov     [rsp+0B00h+hMem], r14
0x1800092f2  mov     [rsp+0B00h+var_AB8], r14d
0x1800092f7  mov     [rsp+0B00h+hKey], r14
0x1800092fc  mov     [rdi], r14d
0x1800092ff  call    ?OpenRDInterfacesKey@@YAKPEAU_GUID@@PEAPEAUHKEY__@@AEAK@Z; OpenRDInterfacesKey(_GUID *,HKEY__ * *,ulong &)
0x180009304  mov     [rsp+0B00h+var_AD0], eax
0x180009308  mov     edi, eax
0x18000930a  test    eax, eax
0x18000930c  jz      loc_18000939C
0x180009312  lea     r14d, [r12+8]
0x180009317  xor     r13d, r13d
0x18000931a  test    cs:byte_1800C8404, r14b
0x180009321  jz      loc_180009770
0x180009327  mov     r8d, eax
0x18000932a  mov     word ptr [rbp+0A00h+var_A60], r13w
0x18000932f  lea     rdx, aDdmgetaddresse_3; "DDMGetAddressesFromRegistry: Failed to "...
0x180009336  lea     rcx, [rbp+0A00h+var_A60]
0x18000933a  call    FormatRRASErrorString
0x18000933f  test    cs:byte_1800C8404, r14b
0x180009346  jz      loc_180009770
0x18000934c  lea     rax, [rbp+0A00h+var_A60]
0x180009350  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009354  inc     rsi
0x180009357  cmp     [rax+rsi*2], r13w
0x18000935c  jnz     short loc_180009354
0x18000935e  lea     eax, ds:2[rsi*2]
0x180009365  mov     [rbp+0A00h+var_A6C], r13d
0x180009369  lea     rcx, [rbp+0A00h+var_A60]
0x18000936d  mov     [rbp+0A00h+var_A70], eax
0x180009370  lea     rax, [rsp+0B00h+var_A88]
0x180009375  mov     [rbp+0A00h+var_A78], rcx
0x180009379  mov     r9d, 2
0x18000937f  mov     [rsp+0B00h+lpData], rax
0x180009384  lea     rdx, RasDdmTraceError
0x18000938b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009392  call    McGenEventWrite_EventWriteTransfer
0x180009397  jmp     loc_18000986C
0x18000939c  mov     ebx, r14d
0x18000939f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800093a3  mov     r14d, 8
0x1800093a9  xor     edi, edi
0x1800093ab  lea     r15d, [r14-6]
0x1800093af  cmp     [rsp+0B00h+var_AB4], edi
0x1800093b3  jbe     loc_180009480
0x1800093b9  mov     rcx, [rsp+0B00h+var_AA0]; hKey
0x1800093be  lea     r9, [rbp+0A00h+String2]; lpData
0x1800093c5  lea     r8, [rsp+0B00h+hKey]; phkResult
0x1800093ca  mov     edx, ebx; dwIndex
0x1800093cc  call    RegOpenRDInterfaceKey
0x1800093d1  mov     r9d, eax
0x1800093d4  test    eax, eax
0x1800093d6  jz      short loc_18000944C
0x1800093d8  test    cs:byte_1800C8404, r14b
0x1800093df  jz      loc_180009474
0x1800093e5  mov     r8d, ebx
0x1800093e8  mov     word ptr [rbp+0A00h+var_A60], di
0x1800093ec  lea     rdx, aDdmgetaddresse_2; "DDMGetAddressesFromRegistry: RegOpenInt"...
0x1800093f3  lea     rcx, [rbp+0A00h+var_A60]
0x1800093f7  call    FormatRRASErrorString
0x1800093fc  test    cs:byte_1800C8404, r14b
0x180009403  jz      short loc_180009474
0x180009405  lea     rcx, [rbp+0A00h+var_A60]
0x180009409  mov     rax, rsi
0x18000940c  inc     rax
0x18000940f  cmp     [rcx+rax*2], di
0x180009413  jnz     short loc_18000940C
0x180009415  lea     eax, ds:2[rax*2]
0x18000941c  mov     [rbp+0A00h+var_A6C], edi
0x18000941f  lea     rcx, [rbp+0A00h+var_A60]
0x180009423  mov     [rbp+0A00h+var_A70], eax
0x180009426  lea     rax, [rsp+0B00h+var_A88]
0x18000942b  mov     [rbp+0A00h+var_A78], rcx
0x18000942f  mov     r9d, r15d
0x180009432  mov     [rsp+0B00h+lpData], rax
0x180009437  lea     rdx, RasDdmTraceError
0x18000943e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009445  call    McGenEventWrite_EventWriteTransfer
0x18000944a  jmp     short loc_180009474
0x18000944c  lea     rdx, [rbp+0A00h+String2]; String2
0x180009453  mov     rcx, r13; String1
0x180009456  call    cs:__imp__wcsicmp
0x18000945c  mov     rcx, [rsp+0B00h+hKey]; hKey
0x180009461  test    eax, eax
0x180009463  jz      loc_1800094FD
0x180009469  call    cs:__imp_RegCloseKey
0x18000946f  mov     [rsp+0B00h+hKey], rdi
0x180009474  inc     ebx
0x180009476  cmp     ebx, [rsp+0B00h+var_AB4]
0x18000947a  jb      loc_1800093B9
0x180009480  test    cs:byte_1800C8404, r14b
0x180009487  jz      loc_180009861
0x18000948d  mov     r8, r13
0x180009490  mov     word ptr [rbp+0A00h+var_A60], di
0x180009494  lea     rdx, aDdmgetaddresse_0; "DDMGetAddressesFromRegistry: No interfa"...
0x18000949b  lea     rcx, [rbp+0A00h+var_A60]
0x18000949f  call    FormatRRASErrorString
0x1800094a4  xor     r13d, r13d
0x1800094a7  test    cs:byte_1800C8404, r14b
0x1800094ae  jz      loc_180009864
0x1800094b4  lea     rax, [rbp+0A00h+var_A60]
0x1800094b8  inc     rsi
0x1800094bb  cmp     [rax+rsi*2], r13w
0x1800094c0  jnz     short loc_1800094B8
0x1800094c2  lea     eax, ds:2[rsi*2]
0x1800094c9  mov     [rbp+0A00h+var_A6C], r13d
0x1800094cd  lea     rcx, [rbp+0A00h+var_A60]
0x1800094d1  mov     [rbp+0A00h+var_A70], eax
0x1800094d4  lea     rax, [rsp+0B00h+var_A88]
0x1800094d9  mov     [rbp+0A00h+var_A78], rcx
0x1800094dd  mov     r9d, r15d
0x1800094e0  mov     [rsp+0B00h+lpData], rax
0x1800094e5  lea     rdx, RasDdmTraceError
0x1800094ec  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800094f3  call    McGenEventWrite_EventWriteTransfer
0x1800094f8  jmp     loc_180009864
0x1800094fd  xor     r13d, r13d
0x180009500  lea     rax, [rsp+0B00h+cbData]
0x180009505  mov     [rsp+0B00h+lpcbData], rax; lpcbData
0x18000950a  lea     r9, [rsp+0B00h+Type]; lpType
0x18000950f  xor     r8d, r8d; lpReserved
0x180009512  mov     [rsp+0B00h+lpData], r13; lpData
0x180009517  lea     rdx, ValueName; "InterfaceInfoPbk"
0x18000951e  mov     [rsp+0B00h+cbData], r13d
0x180009523  mov     [rsp+0B00h+Type], r13d
0x180009528  call    cs:__imp_RegQueryValueExW
0x18000952e  mov     [rsp+0B00h+var_AD0], eax
0x180009532  mov     edi, eax
0x180009534  test    eax, eax
0x180009536  jnz     loc_180009827
0x18000953c  cmp     [rsp+0B00h+Type], 3
0x180009541  jnz     loc_180009827
0x180009547  mov     eax, [rsp+0B00h+cbData]
0x18000954b  test    eax, eax
0x18000954d  jz      loc_180009827
0x180009553  mov     ecx, eax; Size
0x180009555  call    cs:__imp_malloc
0x18000955b  mov     rbx, rax
0x18000955e  test    rax, rax
0x180009561  jnz     short loc_180009570
0x180009563  mov     edi, r14d
0x180009566  mov     [rsp+0B00h+var_AD0], r14d
0x18000956b  jmp     loc_18000986C
0x180009570  mov     rcx, [rsp+0B00h+hKey]; hKey
0x180009575  lea     rax, [rsp+0B00h+cbData]
0x18000957a  mov     [rsp+0B00h+lpcbData], rax; lpcbData
0x18000957f  lea     r9, [rsp+0B00h+Type]; lpType
0x180009584  xor     r8d, r8d; lpReserved
0x180009587  mov     [rsp+0B00h+lpData], rbx; lpData
0x18000958c  lea     rdx, ValueName; "InterfaceInfoPbk"
0x180009593  call    cs:__imp_RegQueryValueExW
0x180009599  mov     [rsp+0B00h+var_AD0], eax
0x18000959d  mov     edi, eax
0x18000959f  test    eax, eax
0x1800095a1  jnz     loc_1800097AA
0x1800095a7  cmp     [rsp+0B00h+Type], 3
0x1800095ac  jnz     loc_1800097AA
0x1800095b2  lea     r8, [rsp+0B00h+var_AB8]
0x1800095b7  mov     rcx, rbx
0x1800095ba  lea     rdx, [rsp+0B00h+hMem]
0x1800095bf  call    GetDestinationInfo
0x1800095c4  mov     rcx, rbx; Block
0x1800095c7  mov     [rsp+0B00h+var_AD0], eax
0x1800095cb  mov     edi, eax
0x1800095cd  call    cs:__imp_free
0x1800095d3  test    edi, edi
0x1800095d5  jz      short loc_180009652
0x1800095d7  test    cs:byte_1800C8404, r14b
0x1800095de  jz      short loc_180009645
0x1800095e0  mov     r8d, edi
0x1800095e3  mov     word ptr [rbp+0A00h+var_A60], r13w
0x1800095e8  lea     rdx, aDdmgetaddresse_1; "DDMGetAddressesFromRegistry: GetDestina"...
0x1800095ef  lea     rcx, [rbp+0A00h+var_A60]
0x1800095f3  call    FormatRRASErrorString
0x1800095f8  test    cs:byte_1800C8404, r14b
0x1800095ff  jz      short loc_180009645
0x180009601  lea     rax, [rbp+0A00h+var_A60]
0x180009605  inc     rsi
0x180009608  cmp     [rax+rsi*2], r13w
0x18000960d  jnz     short loc_180009605
0x18000960f  lea     eax, ds:2[rsi*2]
0x180009616  mov     [rbp+0A00h+var_A6C], r13d
0x18000961a  lea     rcx, [rbp+0A00h+var_A60]
0x18000961e  mov     [rbp+0A00h+var_A70], eax
0x180009621  lea     rax, [rsp+0B00h+var_A88]
0x180009626  mov     [rbp+0A00h+var_A78], rcx
0x18000962a  mov     r9d, r15d
0x18000962d  mov     [rsp+0B00h+lpData], rax
0x180009632  lea     rdx, RasDdmTraceError
0x180009639  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009640  call    McGenEventWrite_EventWriteTransfer
0x180009645  mov     r12, [rsp+0B00h+hMem]
0x18000964a  mov     rbx, r13
0x18000964d  jmp     loc_18000986F
0x180009652  mov     r12d, [rsp+0B00h+var_AB8]
0x180009657  mov     ecx, 40h ; '@'; uFlags
0x18000965c  mov     ebx, r12d
0x18000965f  mov     [rsp+0B00h+var_AD0], r13d
0x180009664  shl     rbx, 5
0x180009668  mov     r15d, r13d
0x18000966b  mov     rdx, rbx; uBytes
0x18000966e  mov     edi, r13d
0x180009671  call    cs:__imp_LocalAlloc
0x180009677  mov     r8, rbx; Size
0x18000967a  xor     edx, edx; Val
0x18000967c  mov     rcx, rax; void *
0x18000967f  mov     [rsp+0B00h+var_AC8], rax
0x180009684  mov     rbx, rax
0x180009687  call    memset_0
0x18000968c  test    r12d, r12d
0x18000968f  mov     r12, [rsp+0B00h+hMem]
0x180009694  jz      loc_18000986F
0x18000969a  mov     rdx, [rsp+0B00h+var_AC8]
0x18000969f  mov     eax, r13d
0x1800096a2  add     rdx, r14
0x1800096a5  mov     ebx, r15d
0x1800096a8  shl     rbx, 5
0x1800096ac  add     rdx, rbx; struct _ROUTER_IP_ADDRESS *
0x1800096af  mov     rcx, [r12+rax*8]; AddressString
0x1800096b3  call    ResolveIpAddress
0x1800096b8  mov     [rsp+0B00h+cbData], eax
0x1800096bc  test    eax, eax
0x1800096be  jz      loc_18000977A
0x1800096c4  test    cs:byte_1800C8404, r14b
0x1800096cb  jz      short loc_180009742
0x1800096cd  mov     r8d, r13d
0x1800096d0  lea     rdx, aDdmgetaddresse; "DDMGetAddressesFromRegistry: ResolveIpA"...
0x1800096d7  xor     ebx, ebx
0x1800096d9  lea     rcx, [rbp+0A00h+var_A60]
0x1800096dd  mov     word ptr [rbp+0A00h+var_A60], bx
0x1800096e1  mov     r9d, eax
0x1800096e4  mov     r8, [r12+r8*8]
0x1800096e8  call    FormatRRASErrorString
0x1800096ed  test    cs:byte_1800C8404, r14b
0x1800096f4  jz      short loc_18000973E
0x1800096f6  lea     rcx, [rbp+0A00h+var_A60]
0x1800096fa  mov     rax, rsi
0x1800096fd  inc     rax
0x180009700  cmp     [rcx+rax*2], bx
0x180009704  jnz     short loc_1800096FD
0x180009706  lea     eax, ds:2[rax*2]
0x18000970d  mov     [rbp+0A00h+var_A6C], ebx
0x180009710  lea     rcx, [rbp+0A00h+var_A60]
0x180009714  mov     [rbp+0A00h+var_A70], eax
0x180009717  lea     rax, [rsp+0B00h+var_A88]
0x18000971c  mov     [rbp+0A00h+var_A78], rcx
0x180009720  mov     r9d, 2
0x180009726  mov     [rsp+0B00h+lpData], rax
0x18000972b  lea     rdx, RasDdmTraceError
0x180009732  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009739  call    McGenEventWrite_EventWriteTransfer
0x18000973e  mov     eax, [rsp+0B00h+cbData]
0x180009742  mov     ecx, 1
0x180009747  test    edi, edi
0x180009749  jnz     short loc_18000974D
0x18000974b  mov     edi, eax
0x18000974d  mov     rax, [rsp+0B00h+var_AC8]
0x180009752  add     r13d, ecx
0x180009755  cmp     r13d, [rsp+0B00h+var_AB8]
0x18000975a  jb      loc_18000969A
0x180009760  xor     r13d, r13d
0x180009763  mov     [rsp+0B00h+var_AD0], edi
0x180009767  test    r15d, r15d
0x18000976a  jnz     short loc_180009792
0x18000976c  test    edi, edi
0x18000976e  jz      short loc_18000978D
0x180009770  mov     rbx, [rsp+0B00h+var_AC8]
0x180009775  jmp     loc_18000986F
  ... truncated ...
```
