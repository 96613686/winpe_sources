# SaveTcpipParam

- ea: `0x18002ebd8`
- end: `0x18002f030`
- name: `SaveTcpipParam`
- size: `1112`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002e92c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002a138`
- `0x18002ebd8`
- `0x18002fbfc`
- `0x180030da4`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18002ec6f`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18002ec6f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ef7a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ef7a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002edf3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ee6b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002eedf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ef33`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002edf3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ee6b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002eedf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ef33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ec98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ecf1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ec98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ecf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eff2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f002`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eff2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f002`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002ed10`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002ed10`

## string_xrefs

- `0x18002ecbd`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002eccc`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002ed36`: `RegCreateKey(%ws) (v4) failed and returned %d`
- `0x18002ed46`: `RegCreateKey(%ws) (v4) failed and returned %d`
- `0x18002ee1c`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18002ef59`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18002ee2f`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18002ef62`: `RegSetValueEx(%ws) failed and returned %d`
- `0x18002ef98`: `RegDeleteValue(%ws) failed and returned %d`
- `0x18002efd6`: `RegDeleteValue(%ws) failed and returned %d`

## pseudocode

```c
__int64 __fastcall SaveTcpipParam(HKEY hKey, __int64 a2)
{
  __int16 v4; // r8
  int v5; // r9d
  char v6; // dl
  unsigned int v7; // eax
  unsigned int v8; // ebx
  const WCHAR *v9; // r8
  const wchar_t *v10; // rdx
  const CHAR *v11; // rcx
  size_t *v12; // r8
  __int64 v13; // rsi
  const BYTE *v14; // r11
  const BYTE *v15; // r14
  size_t *v16; // r8
  __int64 v17; // rax
  __int64 v18; // rax
  const WCHAR *v19; // r14
  bool v20; // zf
  const BYTE *v21; // rcx
  __int64 v22; // rax
  const BYTE *v23; // rcx
  wchar_t phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  const BYTE *phkResultc; // [rsp+20h] [rbp-E0h]
  long double cbData; // [rsp+28h] [rbp-D8h]
  HKEY v30; // [rsp+30h] [rbp-D0h] BYREF
  int v31; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v34[2044]; // [rsp+54h] [rbp-ACh] BYREF

  hKeya = 0;
  v30 = 0;
  v33 = 0;
  memset_0(v34, 0, sizeof(v34));
  if ( gIsIphlpEtwTracingAvailable )
  {
    v6 = qword_18004C648;
    if ( qword_18004C648 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        qword_18004C648,
        L"SaveTcpipParam");
  }
  else
  {
    TraceHlp("SaveTcpipParam");
  }
  o(*(_QWORD *)(a2 + 8), v6, v4, v5, phkResult, cbData);
  v7 = RegOpenKeyExW(hKey, L"Interfaces", 0, 0x20006u, &hKeya);
  v8 = v7;
  if ( v7 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004C640 )
        goto LABEL_62;
      v9 = L"Interfaces";
LABEL_9:
      v10 = L"RegOpenKeyEx(%ws) failed and returned %d";
LABEL_59:
      LOWORD(v33) = 0;
      FormatRRASErrorString(&v33, v10, v9, v7);
      ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004C640, &v33);
      goto LABEL_62;
    }
LABEL_10:
    v11 = "RegOpenKeyEx(%ws) failed and returned %d";
LABEL_61:
    TraceHlp(v11);
    goto LABEL_62;
  }
  v7 = RegOpenKeyExW(hKeya, *(LPCWSTR *)(a2 + 8), 0, 0x20006u, &v30);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 != 2 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !qword_18004C640 )
          goto LABEL_62;
        v9 = *(const WCHAR **)(a2 + 8);
        goto LABEL_9;
      }
      goto LABEL_10;
    }
    v7 = RegCreateKeyW(hKeya, *(LPCWSTR *)(a2 + 8), &v30);
    v8 = v7;
    if ( v7 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !qword_18004C640 )
          goto LABEL_62;
        v9 = *(const WCHAR **)(a2 + 8);
        v10 = L"RegCreateKey(%ws) (v4) failed and returned %d";
        goto LABEL_59;
      }
      v11 = "RegCreateKey(%ws) (v4) failed and returned %d";
      goto LABEL_61;
    }
  }
  v13 = -1;
  if ( *(_DWORD *)a2 == 1 )
  {
    v14 = (const BYTE *)(a2 + 16);
    if ( !*(_WORD *)(a2 + 16) || (v15 = (const BYTE *)(a2 + 58), !*(_WORD *)(a2 + 58)) )
    {
      StringCopyWorkerW((STRSAFE_LPWSTR)(a2 + 16), 0x15u, v12, L"0.0.0.0", (size_t)phkResulta);
      v15 = (const BYTE *)(a2 + 58);
      StringCopyWorkerW((STRSAFE_LPWSTR)(a2 + 58), 0x15u, v16, L"0.0.0.0", (size_t)phkResultb);
    }
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)&v14[2 * v17] );
    v7 = RegSetValueExW(v30, L"DhcpIPAddress", 0, 1u, v14, 2 * v17);
    v8 = v7;
    if ( v7 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !qword_18004C640 )
          goto LABEL_62;
        v9 = L"DhcpIPAddress";
LABEL_32:
        v10 = L"RegSetValueEx(%ws) failed and returned %d";
        goto LABEL_59;
      }
      goto LABEL_33;
    }
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)&v15[2 * v18] );
    phkResultc = v15;
    v19 = L"DhcpSubnetMask";
    v7 = RegSetValueExW(v30, L"DhcpSubnetMask", 0, 1u, phkResultc, 2 * v18);
    v8 = v7;
    if ( v7 )
      goto LABEL_37;
  }
  v20 = *(_QWORD *)(a2 + 120) == 0;
  v21 = (const BYTE *)&v31;
  v31 = 0;
  v22 = -1;
  if ( !v20 )
    v21 = *(const BYTE **)(a2 + 120);
  do
    ++v22;
  while ( *(_WORD *)&v21[2 * v22] );
  v19 = L"Domain";
  v7 = RegSetValueExW(v30, L"Domain", 0, 1u, v21, 2 * v22 + 2);
  v8 = v7;
  if ( v7 )
  {
LABEL_37:
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004C640 )
        goto LABEL_62;
      v9 = v19;
      goto LABEL_32;
    }
LABEL_33:
    v11 = "RegSetValueEx(%ws) failed and returned %d";
    goto LABEL_61;
  }
  v23 = (const BYTE *)&v31;
  if ( *(_QWORD *)(a2 + 104) )
    v23 = *(const BYTE **)(a2 + 104);
  if ( *(_WORD *)v23 == 32 )
  {
    v7 = RegDeleteValueW(v30, L"NameServer");
    v8 = v7;
    if ( !v7 )
      goto LABEL_62;
    if ( !gIsIphlpEtwTracingAvailable )
    {
      v11 = "RegDeleteValue(%ws) failed and returned %d";
      goto LABEL_61;
    }
    if ( !qword_18004C640 )
      goto LABEL_62;
    v10 = L"RegDeleteValue(%ws) failed and returned %d";
    goto LABEL_58;
  }
  do
    ++v13;
  while ( *(_WORD *)&v23[2 * v13] );
  v7 = RegSetValueExW(v30, L"NameServer", 0, 1u, v23, 2 * v13 + 2);
  v8 = v7;
  if ( v7 )
  {
    if ( !gIsIphlpEtwTracingAvailable )
    {
      v11 = "RegSetValueEx(%ws) failed and returned %d";
      goto LABEL_61;
    }
    if ( !qword_18004C640 )
      goto LABEL_62;
    v10 = L"RegSetValueEx(%ws) failed and returned %d";
LABEL_58:
    v9 = L"NameServer";
    goto LABEL_59;
  }
LABEL_62:
  if ( v30 )
    RegCloseKey(v30);
  if ( hKeya )
    RegCloseKey(hKeya);
  return v8;
}

```

## disassembly

```asm
0x18002ebd8  mov     [rsp-8+arg_10], rbx
0x18002ebdd  push    rbp
0x18002ebde  push    rsi
0x18002ebdf  push    rdi
0x18002ebe0  push    r14
0x18002ebe2  push    r15
0x18002ebe4  lea     rbp, [rsp-760h]
0x18002ebec  sub     rsp, 860h
0x18002ebf3  mov     rax, cs:__security_cookie
0x18002ebfa  xor     rax, rsp
0x18002ebfd  mov     [rbp+780h+var_30], rax
0x18002ec04  xor     r15d, r15d
0x18002ec07  mov     rdi, rdx
0x18002ec0a  mov     rbx, rcx
0x18002ec0d  mov     [rsp+880h+hKey], r15
0x18002ec12  xor     edx, edx; Val
0x18002ec14  mov     [rsp+880h+var_850], r15
0x18002ec19  lea     rcx, [rsp+880h+var_82C]; void *
0x18002ec1e  mov     [rsp+880h+var_830], r15d
0x18002ec23  mov     r8d, 7FCh; Size
0x18002ec29  call    memset_0
0x18002ec2e  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002ec35  jz      short loc_18002EC5F
0x18002ec37  mov     rdx, cs:qword_18004C648
0x18002ec3e  test    rdx, rdx
0x18002ec41  jz      short loc_18002EC6B
0x18002ec43  mov     rcx, cs:gIphlpEtwContext
0x18002ec4a  lea     r8, aSavetcpipparam; "SaveTcpipParam"
0x18002ec51  mov     rax, cs:gIphlpTemplateFunc
0x18002ec58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec5d  jmp     short loc_18002EC6B
0x18002ec5f  lea     rcx, aSavetcpipparam_0; "SaveTcpipParam"
0x18002ec66  call    TraceHlp
0x18002ec6b  mov     rcx, [rdi+8]
0x18002ec6f  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18002ec75  lea     rax, [rsp+880h+hKey]
0x18002ec7a  mov     r14d, 20006h
0x18002ec80  lea     rsi, aInterfaces; "Interfaces"
0x18002ec87  mov     [rsp+880h+phkResult], rax; phkResult
0x18002ec8c  mov     r9d, r14d; samDesired
0x18002ec8f  mov     rdx, rsi; lpSubKey
0x18002ec92  xor     r8d, r8d; ulOptions
0x18002ec95  mov     rcx, rbx; hKey
0x18002ec98  call    cs:__imp_RegOpenKeyExW
0x18002ec9e  mov     ebx, eax
0x18002eca0  test    eax, eax
0x18002eca2  jz      short loc_18002ECD8
0x18002eca4  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002ecab  jz      short loc_18002ECC9
0x18002ecad  cmp     cs:qword_18004C640, r15
0x18002ecb4  jz      loc_18002EFE8
0x18002ecba  mov     r8, rsi
0x18002ecbd  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002ecc4  jmp     loc_18002EFA2
0x18002ecc9  mov     rdx, rsi
0x18002eccc  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002ecd3  jmp     loc_18002EFE0
0x18002ecd8  mov     rdx, [rdi+8]; lpSubKey
0x18002ecdc  lea     rax, [rsp+880h+var_850]
0x18002ece1  mov     rcx, [rsp+880h+hKey]; hKey
0x18002ece6  mov     r9d, r14d; samDesired
0x18002ece9  xor     r8d, r8d; ulOptions
0x18002ecec  mov     [rsp+880h+phkResult], rax; cchToCopy
0x18002ecf1  call    cs:__imp_RegOpenKeyExW
0x18002ecf7  mov     ebx, eax
0x18002ecf9  test    eax, eax
0x18002ecfb  jz      short loc_18002ED7A
0x18002ecfd  cmp     eax, 2
0x18002ed00  jnz     short loc_18002ED52
0x18002ed02  mov     rdx, [rdi+8]; lpSubKey
0x18002ed06  lea     r8, [rsp+880h+var_850]; phkResult
0x18002ed0b  mov     rcx, [rsp+880h+hKey]; hKey
0x18002ed10  call    cs:__imp_RegCreateKeyW
0x18002ed16  mov     ebx, eax
0x18002ed18  test    eax, eax
0x18002ed1a  jz      short loc_18002ED7A
0x18002ed1c  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002ed23  jz      short loc_18002ED42
0x18002ed25  cmp     cs:qword_18004C640, r15
0x18002ed2c  jz      loc_18002EFE8
0x18002ed32  mov     r8, [rdi+8]
0x18002ed36  lea     rdx, aRegcreatekeyWs_1; "RegCreateKey(%ws) (v4) failed and retur"...
0x18002ed3d  jmp     loc_18002EFA2
0x18002ed42  mov     rdx, [rdi+8]
0x18002ed46  lea     rcx, aRegcreatekeyWs; "RegCreateKey(%ws) (v4) failed and retur"...
0x18002ed4d  jmp     loc_18002EFE0
0x18002ed52  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002ed59  jz      short loc_18002ED71
0x18002ed5b  cmp     cs:qword_18004C640, r15
0x18002ed62  jz      loc_18002EFE8
0x18002ed68  mov     r8, [rdi+8]
0x18002ed6c  jmp     loc_18002ECBD
0x18002ed71  mov     rdx, [rdi+8]
0x18002ed75  jmp     loc_18002ECCC
0x18002ed7a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002ed7e  cmp     dword ptr [rdi], 1
0x18002ed81  jnz     loc_18002EE97
0x18002ed87  lea     r11, [rdi+10h]
0x18002ed8b  cmp     r15w, [r11]
0x18002ed8f  jz      short loc_18002ED9B
0x18002ed91  lea     r14, [rdi+3Ah]
0x18002ed95  cmp     r15w, [r14]
0x18002ed99  jnz     short loc_18002EDC6
0x18002ed9b  mov     ebx, 15h
0x18002eda0  lea     r9, a0000; "0.0.0.0"
0x18002eda7  mov     edx, ebx; cchDest
0x18002eda9  mov     rcx, r11; pszDest
0x18002edac  call    StringCopyWorkerW
0x18002edb1  lea     r14, [rdi+3Ah]
0x18002edb5  mov     edx, ebx; cchDest
0x18002edb7  mov     rcx, r14; pszDest
0x18002edba  lea     r9, a0000; "0.0.0.0"
0x18002edc1  call    StringCopyWorkerW
0x18002edc6  mov     rax, rsi
0x18002edc9  inc     rax
0x18002edcc  cmp     [r11+rax*2], r15w
0x18002edd1  jnz     short loc_18002EDC9
0x18002edd3  mov     rcx, [rsp+880h+var_850]; hKey
0x18002edd8  lea     rdx, aDhcpipaddress; "DhcpIPAddress"
0x18002eddf  add     eax, eax
0x18002ede1  mov     r9d, 1; dwType
0x18002ede7  mov     dword ptr [rsp+880h+cbData], eax; cbData
0x18002edeb  xor     r8d, r8d; Reserved
0x18002edee  mov     [rsp+880h+phkResult], r11; lpData
0x18002edf3  call    cs:__imp_RegSetValueExW
0x18002edf9  mov     ebx, eax
0x18002edfb  test    eax, eax
0x18002edfd  jz      short loc_18002EE3B
0x18002edff  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002ee06  jz      short loc_18002EE28
0x18002ee08  cmp     cs:qword_18004C640, r15
0x18002ee0f  jz      loc_18002EFE8
0x18002ee15  lea     r8, aDhcpipaddress; "DhcpIPAddress"
0x18002ee1c  lea     rdx, aRegsetvalueexW; "RegSetValueEx(%ws) failed and returned "...
0x18002ee23  jmp     loc_18002EFA2
0x18002ee28  lea     rdx, aDhcpipaddress; "DhcpIPAddress"
0x18002ee2f  lea     rcx, aRegsetvalueexW_0; "RegSetValueEx(%ws) failed and returned "...
0x18002ee36  jmp     loc_18002EFE0
0x18002ee3b  mov     rax, rsi
0x18002ee3e  inc     rax
0x18002ee41  cmp     [r14+rax*2], r15w
0x18002ee46  jnz     short loc_18002EE3E
0x18002ee48  mov     rcx, [rsp+880h+var_850]; hKey
0x18002ee4d  add     eax, eax
0x18002ee4f  mov     dword ptr [rsp+880h+cbData], eax; cbData
0x18002ee53  mov     r9d, 1; dwType
0x18002ee59  mov     [rsp+880h+phkResult], r14; lpData
0x18002ee5e  xor     r8d, r8d; Reserved
0x18002ee61  lea     r14, aDhcpsubnetmask; "DhcpSubnetMask"
0x18002ee68  mov     rdx, r14; lpValueName
0x18002ee6b  call    cs:__imp_RegSetValueExW
0x18002ee71  mov     ebx, eax
0x18002ee73  test    eax, eax
0x18002ee75  jz      short loc_18002EE97
0x18002ee77  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002ee7e  jz      short loc_18002EE92
0x18002ee80  cmp     cs:qword_18004C640, r15
0x18002ee87  jz      loc_18002EFE8
0x18002ee8d  mov     r8, r14
0x18002ee90  jmp     short loc_18002EE1C
0x18002ee92  mov     rdx, r14
0x18002ee95  jmp     short loc_18002EE2F
0x18002ee97  cmp     [rdi+78h], r15
0x18002ee9b  lea     rcx, [rsp+880h+var_848]
0x18002eea0  mov     [rsp+880h+var_848], r15d
0x18002eea5  mov     rax, rsi
0x18002eea8  cmovnz  rcx, [rdi+78h]
0x18002eead  inc     rax
0x18002eeb0  cmp     [rcx+rax*2], r15w
0x18002eeb5  jnz     short loc_18002EEAD
0x18002eeb7  lea     eax, ds:2[rax*2]
0x18002eebe  mov     r9d, 1; dwType
0x18002eec4  mov     dword ptr [rsp+880h+cbData], eax; cbData
0x18002eec8  lea     r14, aDomain; "Domain"
0x18002eecf  mov     [rsp+880h+phkResult], rcx; lpData
0x18002eed4  xor     r8d, r8d; Reserved
0x18002eed7  mov     rcx, [rsp+880h+var_850]; hKey
0x18002eedc  mov     rdx, r14; lpValueName
0x18002eedf  call    cs:__imp_RegSetValueExW
0x18002eee5  mov     ebx, eax
0x18002eee7  test    eax, eax
0x18002eee9  jnz     short loc_18002EE77
0x18002eeeb  cmp     [rdi+68h], r15
0x18002eeef  lea     rcx, [rsp+880h+var_848]
0x18002eef4  lea     eax, [rbx+20h]
0x18002eef7  cmovnz  rcx, [rdi+68h]
0x18002eefc  cmp     ax, [rcx]
0x18002eeff  jz      short loc_18002EF6B
0x18002ef01  inc     rsi
0x18002ef04  cmp     [rcx+rsi*2], r15w
0x18002ef09  jnz     short loc_18002EF01
0x18002ef0b  lea     eax, ds:2[rsi*2]
0x18002ef12  mov     r9d, 1; dwType
0x18002ef18  mov     dword ptr [rsp+880h+cbData], eax; cbData
0x18002ef1c  lea     rdi, aNameserver; "NameServer"
0x18002ef23  mov     [rsp+880h+phkResult], rcx; lpData
0x18002ef28  xor     r8d, r8d; Reserved
0x18002ef2b  mov     rcx, [rsp+880h+var_850]; hKey
0x18002ef30  mov     rdx, rdi; lpValueName
0x18002ef33  call    cs:__imp_RegSetValueExW
0x18002ef39  mov     ebx, eax
0x18002ef3b  test    eax, eax
0x18002ef3d  jz      loc_18002EFE8
0x18002ef43  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002ef4a  jz      short loc_18002EF62
0x18002ef4c  cmp     cs:qword_18004C640, r15
0x18002ef53  jz      loc_18002EFE8
0x18002ef59  lea     rdx, aRegsetvalueexW; "RegSetValueEx(%ws) failed and returned "...
0x18002ef60  jmp     short loc_18002EF9F
0x18002ef62  lea     rcx, aRegsetvalueexW_0; "RegSetValueEx(%ws) failed and returned "...
0x18002ef69  jmp     short loc_18002EFDD
0x18002ef6b  mov     rcx, [rsp+880h+var_850]; hKey
0x18002ef70  lea     rdi, aNameserver; "NameServer"
0x18002ef77  mov     rdx, rdi; lpValueName
0x18002ef7a  call    cs:__imp_RegDeleteValueW
0x18002ef80  mov     ebx, eax
0x18002ef82  test    eax, eax
0x18002ef84  jz      short loc_18002EFE8
0x18002ef86  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002ef8d  jz      short loc_18002EFD6
0x18002ef8f  cmp     cs:qword_18004C640, r15
0x18002ef96  jz      short loc_18002EFE8
0x18002ef98  lea     rdx, aRegdeletevalue; "RegDeleteValue(%ws) failed and returned"...
0x18002ef9f  mov     r8, rdi
0x18002efa2  mov     r9d, eax
0x18002efa5  mov     word ptr [rsp+880h+var_830], r15w
0x18002efab  lea     rcx, [rsp+880h+var_830]
0x18002efb0  call    FormatRRASErrorString
0x18002efb5  mov     rdx, cs:qword_18004C640
0x18002efbc  lea     r8, [rsp+880h+var_830]
0x18002efc1  mov     rcx, cs:gIphlpEtwContext
0x18002efc8  mov     rax, cs:gIphlpTemplateFunc
0x18002efcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efd4  jmp     short loc_18002EFE8
0x18002efd6  lea     rcx, aRegdeletevalue_2; "RegDeleteValue(%ws) failed and returned"...
0x18002efdd  mov     rdx, rdi
0x18002efe0  mov     r8d, eax
0x18002efe3  call    TraceHlp
0x18002efe8  mov     rcx, [rsp+880h+var_850]; hKey
0x18002efed  test    rcx, rcx
0x18002eff0  jz      short loc_18002EFF8
0x18002eff2  call    cs:__imp_RegCloseKey
0x18002eff8  mov     rcx, [rsp+880h+hKey]; hKey
0x18002effd  test    rcx, rcx
0x18002f000  jz      short loc_18002F008
0x18002f002  call    cs:__imp_RegCloseKey
0x18002f008  mov     eax, ebx
0x18002f00a  mov     rcx, [rbp+780h+var_30]
0x18002f011  xor     rcx, rsp; StackCookie
0x18002f014  call    __security_check_cookie
0x18002f019  mov     rbx, [rsp+880h+arg_10]
0x18002f021  add     rsp, 860h
0x18002f028  pop     r15
0x18002f02a  pop     r14
0x18002f02c  pop     rdi
0x18002f02d  pop     rsi
0x18002f02e  pop     rbp
0x18002f02f  retn
```
