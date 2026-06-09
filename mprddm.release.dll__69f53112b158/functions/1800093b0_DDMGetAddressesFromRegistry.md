# DDMGetAddressesFromRegistry

- ea: `0x1800093b0`
- end: `0x180009a72`
- name: `DDMGetAddressesFromRegistry`
- size: `1730`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009c70`

## callees

- `0x180007c0c`
- `0x18000908c`
- `0x1800093b0`
- `0x180009ad4`
- `0x18000a728`
- `0x18000aa08`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `msvcrt!malloc` at `0x180009759`
- `msvcrt!malloc` at `0x180009759`
- `msvcrt!free` at `0x1800097d0`
- `msvcrt!free` at `0x1800097d0`
- `msvcrt!_wcsicmp` at `0x18000958f`
- `msvcrt!_wcsicmp` at `0x18000958f`
- `KERNEL32!LocalFree` at `0x18000968a`
- `KERNEL32!LocalFree` at `0x1800096af`
- `KERNEL32!LocalFree` at `0x1800096cb`
- `KERNEL32!LocalFree` at `0x18000968a`
- `KERNEL32!LocalFree` at `0x1800096af`
- `KERNEL32!LocalFree` at `0x1800096cb`
- `KERNEL32!LocalAlloc` at `0x180009874`
- `KERNEL32!LocalAlloc` at `0x180009874`
- `ADVAPI32!RegQueryValueExW` at `0x18000972a`
- `ADVAPI32!RegQueryValueExW` at `0x180009798`
- `ADVAPI32!RegQueryValueExW` at `0x18000972a`
- `ADVAPI32!RegQueryValueExW` at `0x180009798`
- `ADVAPI32!RegCloseKey` at `0x1800095ad`
- `ADVAPI32!RegCloseKey` at `0x180009656`
- `ADVAPI32!RegCloseKey` at `0x180009671`
- `ADVAPI32!RegCloseKey` at `0x1800095ad`
- `ADVAPI32!RegCloseKey` at `0x180009656`
- `ADVAPI32!RegCloseKey` at `0x180009671`

## string_xrefs

- `0x180009468`: `DDMGetAddressesFromRegistry: Failed to open interfaces key, status = %d`
- `0x18000951a`: `DDMGetAddressesFromRegistry: RegOpenInterfaceKey failed for keyIndex = %d, error = %d`
- `0x1800099ce`: `DDMGetAddressesFromRegistry: Invalid Value of S2S_PBK_INFO in Registry - %d`
- `0x180009a4a`: `DDMGetAddressesFromRegistry: Invalid Value of S2S_PBK_INFO in Registry - %d`
- `0x1800097f2`: `DDMGetAddressesFromRegistry: GetDestinationInfo failed with error = %d`
- `0x1800095e7`: `DDMGetAddressesFromRegistry: No interface with name (%s) found`
- `0x1800098d8`: `DDMGetAddressesFromRegistry: ResolveIpAddress failed for %s. error: %d`

## pseudocode

```c
__int64 __fastcall DDMGetAddressesFromRegistry(struct _GUID *a1, wchar_t *a2, unsigned int *a3, _QWORD *a4)
{
  char *v7; // r13
  HLOCAL *v8; // r12
  unsigned int v9; // eax
  DWORD v10; // ebx
  unsigned int DestinationInfo; // edi
  __int64 v12; // r8
  __int64 v13; // rsi
  __int64 v14; // rsi
  unsigned int v15; // eax
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // r8
  unsigned int v19; // r15d
  HLOCAL *v20; // rbx
  __int64 v21; // rsi
  BYTE *lpData; // rbx
  unsigned int v24; // eax
  __int64 v25; // r8
  SIZE_T v26; // rbx
  LPWSTR *v27; // r15
  unsigned int v28; // r12d
  __int64 v29; // rbx
  unsigned int v30; // eax
  unsigned int v31; // r13d
  __int64 v32; // r8
  __int64 v33; // rax
  bool v34; // zf
  unsigned int v35; // eax
  __int64 v36; // r8
  unsigned int v37; // [rsp+30h] [rbp-D0h] BYREF
  char *v38; // [rsp+38h] [rbp-C8h]
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v41; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v42; // [rsp+54h] [rbp-ACh]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL *v44; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v45; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v46; // [rsp+70h] [rbp-90h]
  unsigned int *v47; // [rsp+78h] [rbp-88h]
  _BYTE v48[16]; // [rsp+80h] [rbp-80h] BYREF
  int *v49; // [rsp+90h] [rbp-70h]
  int v50; // [rsp+98h] [rbp-68h]
  int v51; // [rsp+9Ch] [rbp-64h]
  int v52; // [rsp+A0h] [rbp-60h] BYREF
  char v53[2044]; // [rsp+A4h] [rbp-5Ch] BYREF
  wchar_t String2[264]; // [rsp+8A0h] [rbp+7A0h] BYREF

  v47 = a3;
  String1 = a2;
  v46 = a4;
  v52 = 0;
  memset_0(v53, 0, sizeof(v53));
  *a4 = 0;
  v45 = 0;
  v41 = 0;
  v7 = 0;
  v44 = 0;
  v8 = 0;
  v37 = 0;
  hKey = 0;
  *a3 = 0;
  v9 = OpenRDInterfacesKey(a1, &v45, &v41);
  v10 = 0;
  DestinationInfo = v9;
  if ( v9 )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v52) = 0;
      FormatRRASErrorString(&v52, L"DDMGetAddressesFromRegistry: Failed to open interfaces key, status = %d", v9);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)&v53[2 * v13 - 4] );
        v51 = 0;
        v50 = 2 * v13 + 2;
        v49 = &v52;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v12, 2, v48);
      }
    }
    goto LABEL_23;
  }
  v14 = -1;
  if ( !v41 )
  {
LABEL_17:
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v52) = 0;
      FormatRRASErrorString(&v52, L"DDMGetAddressesFromRegistry: No interface with name (%s) found", String1);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        do
          ++v14;
        while ( *(_WORD *)&v53[2 * v14 - 4] );
        v51 = 0;
        v50 = 2 * v14 + 2;
        v49 = &v52;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v18, 2, v48);
      }
    }
    DestinationInfo = 2;
LABEL_22:
    v7 = 0;
    goto LABEL_23;
  }
  while ( 1 )
  {
    v15 = RegOpenRDInterfaceKey(v45, v10, &hKey, (LPBYTE)String2);
    if ( v15 )
    {
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v52) = 0;
        FormatRRASErrorString(
          &v52,
          L"DDMGetAddressesFromRegistry: RegOpenInterfaceKey failed for keyIndex = %d, error = %d",
          v10,
          v15);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          v17 = -1;
          do
            ++v17;
          while ( *(_WORD *)&v53[2 * v17 - 4] );
          v51 = 0;
          v50 = 2 * v17 + 2;
          v49 = &v52;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v16, 2, v48);
        }
      }
      goto LABEL_16;
    }
    if ( !_wcsicmp(String1, String2) )
      break;
    RegCloseKey(hKey);
    hKey = 0;
LABEL_16:
    if ( ++v10 >= v41 )
      goto LABEL_17;
  }
  LODWORD(String1) = 0;
  Type = 0;
  DestinationInfo = RegQueryValueExW(hKey, L"InterfaceInfoPbk", 0, &Type, 0, (LPDWORD)&String1);
  if ( DestinationInfo || Type != 3 || !(_DWORD)String1 )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v52) = 0;
      FormatRRASErrorString(
        &v52,
        L"DDMGetAddressesFromRegistry: Invalid Value of S2S_PBK_INFO in Registry - %d",
        DestinationInfo);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        do
          ++v14;
        while ( *(_WORD *)&v53[2 * v14 - 4] );
        goto LABEL_71;
      }
    }
LABEL_72:
    if ( !DestinationInfo )
      DestinationInfo = 1015;
    goto LABEL_22;
  }
  lpData = (BYTE *)malloc((unsigned int)String1);
  if ( !lpData )
  {
    DestinationInfo = 8;
    goto LABEL_22;
  }
  v24 = RegQueryValueExW(hKey, L"InterfaceInfoPbk", 0, &Type, lpData, (LPDWORD)&String1);
  DestinationInfo = v24;
  if ( v24 || Type != 3 )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v52) = 0;
      FormatRRASErrorString(&v52, L"DDMGetAddressesFromRegistry: Invalid Value of S2S_PBK_INFO in Registry - %d", v24);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        do
          ++v14;
        while ( *(_WORD *)&v53[2 * v14 - 4] );
LABEL_71:
        v51 = 0;
        v50 = 2 * v14 + 2;
        v49 = &v52;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v36, 2, v48);
        goto LABEL_72;
      }
    }
    goto LABEL_72;
  }
  DestinationInfo = GetDestinationInfo(lpData, &v44, &v37);
  free(lpData);
  if ( DestinationInfo )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v52) = 0;
      FormatRRASErrorString(
        &v52,
        L"DDMGetAddressesFromRegistry: GetDestinationInfo failed with error = %d",
        DestinationInfo);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        do
          ++v14;
        while ( *(_WORD *)&v53[2 * v14 - 4] );
        v51 = 0;
        v50 = 2 * v14 + 2;
        v49 = &v52;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v25, 2, v48);
      }
    }
    v8 = v44;
    v7 = 0;
    goto LABEL_23;
  }
  v19 = v37;
  DestinationInfo = 0;
  String1 = (wchar_t *)v37;
  v26 = 32LL * v37;
  v38 = (char *)LocalAlloc(0x40u, v26);
  v7 = v38;
  memset_0(v38, 0, v26);
  if ( v19 )
  {
    v27 = (LPWSTR *)v44;
    v28 = 0;
    do
    {
      v29 = 32LL * v28;
      v30 = ResolveIpAddress(*v27, (struct _ROUTER_IP_ADDRESS *)&v7[v29 + 8]);
      v31 = v30;
      if ( v30 )
      {
        if ( (byte_1800CF404 & 8) != 0 )
        {
          LOWORD(v52) = 0;
          FormatRRASErrorString(
            &v52,
            L"DDMGetAddressesFromRegistry: ResolveIpAddress failed for %s. error: %d",
            *v27,
            v30);
          if ( (byte_1800CF404 & 8) != 0 )
          {
            v33 = -1;
            do
              ++v33;
            while ( *(_WORD *)&v53[2 * v33 - 4] );
            v51 = 0;
            v50 = 2 * v33 + 2;
            v49 = &v52;
            McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v32, 2, v48);
          }
        }
        if ( !DestinationInfo )
          DestinationInfo = v31;
        v7 = v38;
      }
      else
      {
        v7 = v38;
        ++v28;
        *(_WORD *)&v38[v29] = 1;
      }
      ++v27;
      String1 = (wchar_t *)((char *)String1 - 1);
    }
    while ( String1 );
    v42 = v28;
    v34 = v28 == 0;
    v8 = v44;
    if ( v34 && DestinationInfo )
    {
LABEL_23:
      v19 = v37;
    }
    else
    {
      v35 = v42;
      v19 = v37;
      if ( v42 )
      {
        *v46 = v7;
        v7 = 0;
        *v47 = v35;
      }
    }
  }
  else
  {
    v8 = v44;
  }
  if ( v45 )
  {
    RegCloseKey(v45);
    v45 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v7 )
    LocalFree(v7);
  if ( v8 )
  {
    if ( v19 )
    {
      v20 = v8;
      v21 = v19;
      do
      {
        LocalFree(*v20++);
        --v21;
      }
      while ( v21 );
      v8 = v44;
    }
    LocalFree(v8);
  }
  return DestinationInfo;
}

```

## disassembly

```asm
0x1800093b0  push    rbp
0x1800093b2  push    rbx
0x1800093b3  push    rsi
0x1800093b4  push    rdi
0x1800093b5  push    r12
0x1800093b7  push    r13
0x1800093b9  push    r14
0x1800093bb  push    r15
0x1800093bd  lea     rbp, [rsp-9C8h]
0x1800093c5  sub     rsp, 0AC8h
0x1800093cc  mov     rax, cs:__security_cookie
0x1800093d3  xor     rax, rsp
0x1800093d6  mov     [rbp+0A00h+var_50], rax
0x1800093dd  mov     rdi, r8
0x1800093e0  mov     [rsp+0B00h+var_A88], r8
0x1800093e5  mov     [rsp+0B00h+String1], rdx
0x1800093ea  mov     rbx, rcx
0x1800093ed  xor     r14d, r14d
0x1800093f0  mov     [rsp+0B00h+var_A90], r9
0x1800093f5  xor     edx, edx; Val
0x1800093f7  mov     [rbp+0A00h+var_A60], r14d
0x1800093fb  mov     r8d, 7FCh; Size
0x180009401  lea     rcx, [rbp+0A00h+var_A5C]; void *
0x180009405  mov     rsi, r9
0x180009408  call    memset_0
0x18000940d  mov     [rsi], r14
0x180009410  lea     r8, [rsp+0B00h+var_AB0]; unsigned int *
0x180009415  lea     rdx, [rsp+0B00h+var_A98]; HKEY *
0x18000941a  mov     [rsp+0B00h+var_A98], r14
0x18000941f  mov     rcx, rbx; struct _GUID *
0x180009422  mov     [rsp+0B00h+var_AB0], r14d
0x180009427  mov     r13d, r14d
0x18000942a  mov     [rsp+0B00h+var_AA0], r14
0x18000942f  mov     r12d, r14d
0x180009432  mov     [rsp+0B00h+var_AD0], r14d
0x180009437  mov     r15d, r14d
0x18000943a  mov     [rsp+0B00h+hKey], r14
0x18000943f  mov     [rdi], r14d
0x180009442  call    ?OpenRDInterfacesKey@@YAKPEAU_GUID@@PEAPEAUHKEY__@@AEAK@Z; OpenRDInterfacesKey(_GUID *,HKEY__ * *,ulong &)
0x180009447  xor     ebx, ebx
0x180009449  lea     r14d, [r12+8]
0x18000944e  mov     edi, eax
0x180009450  test    eax, eax
0x180009452  jz      short loc_1800094D2
0x180009454  test    cs:byte_1800CF404, r14b
0x18000945b  jz      loc_180009647
0x180009461  mov     r8d, eax
0x180009464  mov     word ptr [rbp+0A00h+var_A60], bx
0x180009468  lea     rdx, aDdmgetaddresse_3; "DDMGetAddressesFromRegistry: Failed to "...
0x18000946f  lea     rcx, [rbp+0A00h+var_A60]
0x180009473  call    FormatRRASErrorString
0x180009478  test    cs:byte_1800CF404, r14b
0x18000947f  jz      loc_180009647
0x180009485  lea     rax, [rbp+0A00h+var_A60]
0x180009489  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000948d  inc     rsi
0x180009490  cmp     [rax+rsi*2], bx
0x180009494  jnz     short loc_18000948D
0x180009496  lea     eax, ds:2[rsi*2]
0x18000949d  mov     [rbp+0A00h+var_A64], ebx
0x1800094a0  lea     rcx, [rbp+0A00h+var_A60]
0x1800094a4  mov     [rbp+0A00h+var_A68], eax
0x1800094a7  lea     rax, [rbp+0A00h+var_A80]
0x1800094ab  mov     [rbp+0A00h+var_A70], rcx
0x1800094af  mov     r9d, 2
0x1800094b5  mov     [rsp+0B00h+lpData], rax
0x1800094ba  lea     rdx, RasDdmTraceError
0x1800094c1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800094c8  call    McGenEventWrite_EventWriteTransfer
0x1800094cd  jmp     loc_180009647
0x1800094d2  mov     rdi, [rsp+0B00h+String1]
0x1800094d7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800094db  xor     eax, eax
0x1800094dd  lea     r13d, [rsi+3]
0x1800094e1  cmp     [rsp+0B00h+var_AB0], eax
0x1800094e5  jbe     loc_1800095D7
0x1800094eb  mov     rcx, [rsp+0B00h+var_A98]; hKey
0x1800094f0  lea     r9, [rbp+0A00h+String2]; lpData
0x1800094f7  lea     r8, [rsp+0B00h+hKey]; phkResult
0x1800094fc  mov     edx, ebx; dwIndex
0x1800094fe  call    RegOpenRDInterfaceKey
0x180009503  xor     ecx, ecx
0x180009505  test    eax, eax
0x180009507  jz      short loc_180009585
0x180009509  test    cs:byte_1800CF404, r14b
0x180009510  jz      loc_1800095C0
0x180009516  mov     word ptr [rbp+0A00h+var_A60], cx
0x18000951a  lea     rdx, aDdmgetaddresse_2; "DDMGetAddressesFromRegistry: RegOpenInt"...
0x180009521  lea     rcx, [rbp+0A00h+var_A60]
0x180009525  mov     r9d, eax
0x180009528  mov     r8d, ebx
0x18000952b  call    FormatRRASErrorString
0x180009530  test    cs:byte_1800CF404, r14b
0x180009537  jz      loc_1800095C0
0x18000953d  lea     rcx, [rbp+0A00h+var_A60]
0x180009541  mov     rax, rsi
0x180009544  xor     edx, edx
0x180009546  inc     rax
0x180009549  cmp     [rcx+rax*2], dx
0x18000954d  jnz     short loc_180009546
0x18000954f  lea     eax, ds:2[rax*2]
0x180009556  mov     [rbp+0A00h+var_A64], edx
0x180009559  lea     rcx, [rbp+0A00h+var_A60]
0x18000955d  mov     [rbp+0A00h+var_A68], eax
0x180009560  lea     rax, [rbp+0A00h+var_A80]
0x180009564  mov     [rbp+0A00h+var_A70], rcx
0x180009568  mov     r9d, r13d
0x18000956b  mov     [rsp+0B00h+lpData], rax
0x180009570  lea     rdx, RasDdmTraceError
0x180009577  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000957e  call    McGenEventWrite_EventWriteTransfer
0x180009583  jmp     short loc_1800095C0
0x180009585  lea     rdx, [rbp+0A00h+String2]; String2
0x18000958c  mov     rcx, rdi; String1
0x18000958f  call    cs:__imp__wcsicmp
0x180009596  nop     dword ptr [rax+rax+00h]
0x18000959b  xor     ecx, ecx
0x18000959d  test    eax, eax
0x18000959f  jz      loc_1800096FD
0x1800095a5  mov     r15d, ecx
0x1800095a8  mov     rcx, [rsp+0B00h+hKey]; hKey
0x1800095ad  call    cs:__imp_RegCloseKey
0x1800095b4  nop     dword ptr [rax+rax+00h]
0x1800095b9  xor     eax, eax
0x1800095bb  mov     [rsp+0B00h+hKey], rax
0x1800095c0  inc     ebx
0x1800095c2  cmp     ebx, [rsp+0B00h+var_AB0]
0x1800095c6  jb      loc_1800094EB
0x1800095cc  xor     ebx, ebx
0x1800095ce  test    r15d, r15d
0x1800095d1  jnz     loc_1800096FF
0x1800095d7  test    cs:byte_1800CF404, r14b
0x1800095de  jz      short loc_180009641
0x1800095e0  mov     r8, rdi
0x1800095e3  mov     word ptr [rbp+0A00h+var_A60], bx
0x1800095e7  lea     rdx, aDdmgetaddresse_0; "DDMGetAddressesFromRegistry: No interfa"...
0x1800095ee  lea     rcx, [rbp+0A00h+var_A60]
0x1800095f2  call    FormatRRASErrorString
0x1800095f7  test    cs:byte_1800CF404, r14b
0x1800095fe  jz      short loc_180009641
0x180009600  lea     rax, [rbp+0A00h+var_A60]
0x180009604  inc     rsi
0x180009607  cmp     [rax+rsi*2], bx
0x18000960b  jnz     short loc_180009604
0x18000960d  lea     eax, ds:2[rsi*2]
0x180009614  mov     [rbp+0A00h+var_A64], ebx
0x180009617  lea     rcx, [rbp+0A00h+var_A60]
0x18000961b  mov     [rbp+0A00h+var_A68], eax
0x18000961e  lea     rax, [rbp+0A00h+var_A80]
0x180009622  mov     [rbp+0A00h+var_A70], rcx
0x180009626  mov     r9d, r13d
0x180009629  mov     [rsp+0B00h+lpData], rax
0x18000962e  lea     rdx, RasDdmTraceError
0x180009635  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000963c  call    McGenEventWrite_EventWriteTransfer
0x180009641  mov     edi, r13d
0x180009644  mov     r13, r12
0x180009647  mov     r15d, [rsp+0B00h+var_AD0]
0x18000964c  mov     rcx, [rsp+0B00h+var_A98]; hKey
0x180009651  test    rcx, rcx
0x180009654  jz      short loc_180009667
0x180009656  call    cs:__imp_RegCloseKey
0x18000965d  nop     dword ptr [rax+rax+00h]
0x180009662  mov     [rsp+0B00h+var_A98], rbx
0x180009667  mov     rcx, [rsp+0B00h+hKey]; hKey
0x18000966c  test    rcx, rcx
0x18000966f  jz      short loc_180009682
0x180009671  call    cs:__imp_RegCloseKey
0x180009678  nop     dword ptr [rax+rax+00h]
0x18000967d  mov     [rsp+0B00h+hKey], rbx
0x180009682  test    r13, r13
0x180009685  jz      short loc_180009696
0x180009687  mov     rcx, r13; hMem
0x18000968a  call    cs:__imp_LocalFree
0x180009691  nop     dword ptr [rax+rax+00h]
0x180009696  test    r12, r12
0x180009699  jz      short loc_1800096D7
0x18000969b  test    r15d, r15d
0x18000969e  jz      short loc_1800096C8
0x1800096a0  mov     rbx, r12
0x1800096a3  mov     esi, r15d
0x1800096a6  mov     r12d, 1
0x1800096ac  mov     rcx, [rbx]; hMem
0x1800096af  call    cs:__imp_LocalFree
0x1800096b6  nop     dword ptr [rax+rax+00h]
0x1800096bb  add     rbx, r14
0x1800096be  sub     rsi, r12
0x1800096c1  jnz     short loc_1800096AC
0x1800096c3  mov     r12, [rsp+0B00h+var_AA0]
0x1800096c8  mov     rcx, r12; hMem
0x1800096cb  call    cs:__imp_LocalFree
0x1800096d2  nop     dword ptr [rax+rax+00h]
0x1800096d7  mov     eax, edi
0x1800096d9  mov     rcx, [rbp+0A00h+var_50]
0x1800096e0  xor     rcx, rsp; StackCookie
0x1800096e3  call    __security_check_cookie
0x1800096e8  add     rsp, 0AC8h
0x1800096ef  pop     r15
0x1800096f1  pop     r14
0x1800096f3  pop     r13
0x1800096f5  pop     r12
0x1800096f7  pop     rdi
0x1800096f8  pop     rsi
0x1800096f9  pop     rbx
0x1800096fa  pop     rbp
0x1800096fb  retn
0x1800096fd  xor     ebx, ebx
0x1800096ff  mov     rcx, [rsp+0B00h+hKey]; hKey
0x180009704  lea     rax, [rsp+0B00h+String1]
0x180009709  mov     [rsp+0B00h+lpcbData], rax; lpcbData
0x18000970e  lea     r9, [rsp+0B00h+Type]; lpType
0x180009713  xor     r8d, r8d; lpReserved
0x180009716  mov     [rsp+0B00h+lpData], rbx; lpData
0x18000971b  lea     rdx, ValueName; "InterfaceInfoPbk"
0x180009722  mov     dword ptr [rsp+0B00h+String1], ebx
0x180009726  mov     [rsp+0B00h+Type], ebx
0x18000972a  call    cs:__imp_RegQueryValueExW
0x180009731  nop     dword ptr [rax+rax+00h]
0x180009736  mov     edi, eax
0x180009738  test    eax, eax
0x18000973a  jnz     loc_180009A3A
0x180009740  cmp     [rsp+0B00h+Type], 3
0x180009745  jnz     loc_180009A3A
0x18000974b  mov     eax, dword ptr [rsp+0B00h+String1]
0x18000974f  test    eax, eax
0x180009751  jz      loc_180009A3A
0x180009757  mov     ecx, eax; Size
0x180009759  call    cs:__imp_malloc
0x180009760  nop     dword ptr [rax+rax+00h]
0x180009765  mov     rbx, rax
0x180009768  test    rax, rax
0x18000976b  jnz     short loc_180009775
0x18000976d  mov     edi, r14d
0x180009770  jmp     loc_180009644
0x180009775  mov     rcx, [rsp+0B00h+hKey]; hKey
0x18000977a  lea     rax, [rsp+0B00h+String1]
0x18000977f  mov     [rsp+0B00h+lpcbData], rax; lpcbData
0x180009784  lea     r9, [rsp+0B00h+Type]; lpType
0x180009789  xor     r8d, r8d; lpReserved
0x18000978c  mov     [rsp+0B00h+lpData], rbx; lpData
0x180009791  lea     rdx, ValueName; "InterfaceInfoPbk"
0x180009798  call    cs:__imp_RegQueryValueExW
0x18000979f  nop     dword ptr [rax+rax+00h]
0x1800097a4  mov     edi, eax
0x1800097a6  test    eax, eax
0x1800097a8  jnz     loc_1800099BC
0x1800097ae  cmp     [rsp+0B00h+Type], 3
0x1800097b3  jnz     loc_1800099BC
0x1800097b9  lea     r8, [rsp+0B00h+var_AD0]
0x1800097be  mov     rcx, rbx
0x1800097c1  lea     rdx, [rsp+0B00h+var_AA0]
0x1800097c6  call    GetDestinationInfo
0x1800097cb  mov     rcx, rbx; Block
0x1800097ce  mov     edi, eax
0x1800097d0  call    cs:__imp_free
0x1800097d7  nop     dword ptr [rax+rax+00h]
0x1800097dc  xor     ebx, ebx
0x1800097de  test    edi, edi
0x1800097e0  jz      short loc_180009859
0x1800097e2  test    cs:byte_1800CF404, r14b
0x1800097e9  jz      short loc_18000984C
0x1800097eb  mov     r8d, edi
0x1800097ee  mov     word ptr [rbp+0A00h+var_A60], bx
0x1800097f2  lea     rdx, aDdmgetaddresse_1; "DDMGetAddressesFromRegistry: GetDestina"...
0x1800097f9  lea     rcx, [rbp+0A00h+var_A60]
0x1800097fd  call    FormatRRASErrorString
0x180009802  test    cs:byte_1800CF404, r14b
0x180009809  jz      short loc_18000984C
0x18000980b  lea     rax, [rbp+0A00h+var_A60]
0x18000980f  inc     rsi
0x180009812  cmp     [rax+rsi*2], bx
0x180009816  jnz     short loc_18000980F
0x180009818  lea     eax, ds:2[rsi*2]
0x18000981f  mov     [rbp+0A00h+var_A64], ebx
0x180009822  lea     rcx, [rbp+0A00h+var_A60]
0x180009826  mov     [rbp+0A00h+var_A68], eax
0x180009829  lea     rax, [rbp+0A00h+var_A80]
0x18000982d  mov     [rbp+0A00h+var_A70], rcx
0x180009831  mov     r9d, r13d
0x180009834  mov     [rsp+0B00h+lpData], rax
0x180009839  lea     rdx, RasDdmTraceError
0x180009840  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009847  call    McGenEventWrite_EventWriteTransfer
0x18000984c  mov     r12, [rsp+0B00h+var_AA0]
0x180009851  mov     r13, rbx
0x180009854  jmp     loc_180009647
0x180009859  mov     r15d, [rsp+0B00h+var_AD0]
0x18000985e  mov     edi, ebx
0x180009860  mov     ebx, r15d
0x180009863  mov     [rsp+0B00h+String1], r15
0x180009868  shl     rbx, 5
0x18000986c  mov     ecx, 40h ; '@'; uFlags
0x180009871  mov     rdx, rbx; uBytes
0x180009874  call    cs:__imp_LocalAlloc
0x18000987b  nop     dword ptr [rax+rax+00h]
0x180009880  mov     r8, rbx; Size
0x180009883  xor     edx, edx; Val
0x180009885  mov     rcx, rax; void *
0x180009888  mov     [rsp+0B00h+var_AC8], rax
0x18000988d  mov     r13, rax
  ... truncated ...
```
