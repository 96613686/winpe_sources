# UnMarshallRegistryPolicyObject

- ea: `0x18003b650`
- end: `0x18003bc5d`
- name: `UnMarshallRegistryPolicyObject`
- size: `1549`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180039c80`

## callees

- `0x180006f00`
- `0x180006f60`
- `0x18000c828`
- `0x18000e510`
- `0x180039f64`
- `0x18003b650`
- `0x180042e20`
- `0x180042ef8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b8da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003bb8b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b8da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003bb8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b724`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b724`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bbd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bc3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bbd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bc3d`

## pseudocode

```c
__int64 __fastcall UnMarshallRegistryPolicyObject(HKEY hKey, __int64 a2, unsigned __int16 *a3, __int64 a4, _QWORD *a5)
{
  _DWORD *v7; // rdi
  unsigned __int16 *v8; // rsi
  __int64 v9; // rdx
  unsigned __int64 v10; // r8
  __int64 v11; // r9
  unsigned int Value; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  unsigned __int16 *v15; // rax
  unsigned int v16; // r15d
  _WORD *i; // rax
  __int64 v18; // rcx
  _QWORD *v19; // r12
  unsigned __int16 *v20; // rbx
  unsigned int j; // r14d
  unsigned __int16 *v22; // rax
  __int64 v23; // rax
  HKEY v24; // rcx
  BYTE Data[4]; // [rsp+30h] [rbp-20h] BYREF
  BYTE v27[4]; // [rsp+34h] [rbp-1Ch] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-18h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-10h]
  SIZE_T v30; // [rsp+48h] [rbp-8h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+50h] BYREF
  DWORD cbData; // [rsp+A8h] [rbp+58h] BYREF

  hKeya = 0;
  Type = 0;
  cbData = 0;
  v7 = 0;
  *(_DWORD *)Data = 0;
  v8 = 0;
  *(_DWORD *)v27 = 0;
  lpMem = 0;
  v30 = 0;
  if ( !a3 || !*a3 )
  {
    v11 = 13;
    Value = 13;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v14 = 30;
    goto LABEL_82;
  }
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(a2 + 2 * v9) );
  v10 = -1;
  do
    ++v10;
  while ( a3[v10] );
  if ( v10 <= (unsigned int)(v9 + 1) )
  {
    v11 = 13;
    Value = 13;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v14 = 31;
    goto LABEL_82;
  }
  Value = RegOpenKeyExW(hKey, &a3[(unsigned int)v9 + 1], 0, 0x20019u, &hKeya);
  if ( Value )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v14 = 32;
    goto LABEL_15;
  }
  v7 = IpsecAllocMem(0x98u);
  if ( !v7 )
  {
    v11 = 14;
    Value = 14;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v14 = 33;
    goto LABEL_82;
  }
  v15 = IpsecAllocStr(a3);
  *(_QWORD *)v7 = v15;
  if ( !v15 )
  {
    v11 = 14;
    Value = 14;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v14 = 34;
    goto LABEL_82;
  }
  Value = RegstoreQueryValue(hKeya, L"ipsecName", (__int64)&cbData);
  if ( Value )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v14 = 35;
    goto LABEL_15;
  }
  RegstoreQueryValue(hKeya, L"description", (__int64)&cbData);
  Value = RegstoreQueryValue(hKeya, L"ipsecID", (__int64)&cbData);
  if ( Value )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v14 = 36;
    goto LABEL_15;
  }
  Type = 4;
  cbData = 4;
  Value = RegQueryValueExW(hKeya, L"ipsecDataType", 0, &Type, Data, &cbData);
  if ( Value )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v14 = 37;
    goto LABEL_15;
  }
  v7[6] = *(_DWORD *)Data;
  Value = RegstoreQueryValue(hKeya, L"ipsecData", (__int64)(v7 + 10));
  if ( Value )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v14 = 38;
    goto LABEL_15;
  }
  Value = RegstoreQueryValue(hKeya, L"ipsecISAKMPReference", (__int64)&cbData);
  if ( Value )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v14 = 39;
    goto LABEL_15;
  }
  Value = RegstoreQueryValue(hKeya, L"ipsecNFAReference", (__int64)&cbData);
  if ( Value )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, Value);
    v8 = (unsigned __int16 *)lpMem;
    goto LABEL_83;
  }
  v8 = (unsigned __int16 *)lpMem;
  v16 = 0;
  for ( i = lpMem; *i; i += v18 + 1 )
  {
    v18 = -1;
    do
      ++v18;
    while ( i[v18] );
    ++v16;
  }
  Value = NsuSizeTMultiply(v16, 8, &v30);
  if ( Value )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v14 = 41;
LABEL_15:
    v11 = Value;
LABEL_82:
    WPP_SF_d(v13[2], v14, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, v11);
    goto LABEL_83;
  }
  v19 = IpsecAllocMem(v30);
  if ( !v19 )
  {
    v11 = 14;
    Value = 14;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v14 = 42;
    goto LABEL_82;
  }
  v20 = v8;
  for ( j = 0; j < v16; ++j )
  {
    v22 = IpsecAllocStr(v20);
    if ( !v22 )
    {
      v11 = 14;
      *((_QWORD *)v7 + 8) = v19;
      Value = 14;
      v7[14] = j;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v14 = 43;
        goto LABEL_82;
      }
      goto LABEL_83;
    }
    v19[j] = v22;
    v23 = -1;
    do
      ++v23;
    while ( v20[v23] );
    v20 += v23 + 1;
  }
  if ( v8 )
    IpsecFreeMem(v8);
  *((_QWORD *)v7 + 8) = v19;
  v7[14] = v16;
  Type = 4;
  cbData = 4;
  Value = RegQueryValueExW(hKeya, L"whenChanged", 0, &Type, v27, &cbData);
  if ( !Value )
  {
    v7[32] = *(_DWORD *)v27;
    v24 = hKeya;
    *a5 = v7;
    if ( v24 )
      RegCloseKey(v24);
    return 0;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v14 = 44;
    goto LABEL_15;
  }
LABEL_83:
  *a5 = 0;
  if ( v8 )
    IpsecFreeMem(v8);
  if ( v7 )
    FreeIpsecPolicyObject((LPVOID *)v7);
  if ( hKeya )
    RegCloseKey(hKeya);
  return Value;
}

```

## disassembly

```asm
0x18003b650  mov     [rsp-38h+arg_0], rbx
0x18003b655  mov     [rsp-38h+cbData], r9d
0x18003b65a  push    rbp
0x18003b65b  push    rsi
0x18003b65c  push    rdi
0x18003b65d  push    r12
0x18003b65f  push    r13
0x18003b661  push    r14
0x18003b663  push    r15
0x18003b665  mov     rbp, rsp
0x18003b668  sub     rsp, 50h
0x18003b66c  xor     r13d, r13d
0x18003b66f  mov     r14, r8
0x18003b672  mov     [rbp+hKey], r13
0x18003b676  mov     rax, rdx
0x18003b679  mov     [rbp+Type], r13d
0x18003b67d  mov     r10, rcx
0x18003b680  mov     [rbp+cbData], r13d
0x18003b684  mov     edi, r13d
0x18003b687  mov     dword ptr [rbp+Data], r13d
0x18003b68b  mov     esi, r13d
0x18003b68e  mov     dword ptr [rbp+var_1C], r13d
0x18003b692  mov     [rbp+lpMem], r13
0x18003b696  mov     [rbp+var_8], r13
0x18003b69a  test    r8, r8
0x18003b69d  jz      loc_18003BBDD
0x18003b6a3  cmp     [r8], r13w
0x18003b6a7  jz      loc_18003BBDD
0x18003b6ad  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003b6b1  mov     rdx, r12
0x18003b6b4  inc     rdx
0x18003b6b7  cmp     [rax+rdx*2], r13w
0x18003b6bc  jnz     short loc_18003B6B4
0x18003b6be  mov     r8, r12
0x18003b6c1  inc     r8
0x18003b6c4  cmp     [r14+r8*2], r13w
0x18003b6c9  jnz     short loc_18003B6C1
0x18003b6cb  lea     ecx, [rdx+1]
0x18003b6ce  cmp     r8, rcx
0x18003b6d1  ja      short loc_18003B706
0x18003b6d3  mov     r9d, 0Dh
0x18003b6d9  mov     ebx, r9d
0x18003b6dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b6e3  lea     rax, WPP_GLOBAL_Control
0x18003b6ea  cmp     rcx, rax
0x18003b6ed  jz      loc_18003BC13
0x18003b6f3  test    byte ptr [rcx+1Ch], 10h
0x18003b6f7  jz      loc_18003BC13
0x18003b6fd  lea     edx, [r9+12h]
0x18003b701  jmp     loc_18003BC03
0x18003b706  mov     eax, edx
0x18003b708  mov     r9d, 20019h; samDesired
0x18003b70e  inc     rax
0x18003b711  xor     r8d, r8d; ulOptions
0x18003b714  mov     rcx, r10; hKey
0x18003b717  lea     rdx, [r14+rax*2]; lpSubKey
0x18003b71b  lea     rax, [rbp+hKey]
0x18003b71f  mov     [rsp+50h+phkResult], rax; phkResult
0x18003b724  call    cs:__imp_RegOpenKeyExW
0x18003b72a  mov     ebx, eax
0x18003b72c  test    eax, eax
0x18003b72e  jz      short loc_18003B75E
0x18003b730  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b737  lea     rax, WPP_GLOBAL_Control
0x18003b73e  cmp     rcx, rax
0x18003b741  jz      loc_18003BC13
0x18003b747  test    byte ptr [rcx+1Ch], 10h
0x18003b74b  jz      loc_18003BC13
0x18003b751  mov     edx, 20h ; ' '
0x18003b756  mov     r9d, ebx
0x18003b759  jmp     loc_18003BC03
0x18003b75e  mov     ecx, 98h
0x18003b763  call    IpsecAllocMem
0x18003b768  mov     rdi, rax
0x18003b76b  test    rax, rax
0x18003b76e  jnz     short loc_18003B7A0
0x18003b770  lea     r9d, [rax+0Eh]
0x18003b774  mov     ebx, r9d
0x18003b777  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b77e  lea     rax, WPP_GLOBAL_Control
0x18003b785  cmp     rcx, rax
0x18003b788  jz      loc_18003BC13
0x18003b78e  test    byte ptr [rcx+1Ch], 10h
0x18003b792  jz      loc_18003BC13
0x18003b798  lea     edx, [rdi+21h]
0x18003b79b  jmp     loc_18003BC03
0x18003b7a0  mov     rcx, r14; unsigned __int16 *
0x18003b7a3  call    IpsecAllocStr
0x18003b7a8  mov     [rdi], rax
0x18003b7ab  test    rax, rax
0x18003b7ae  jnz     short loc_18003B7E1
0x18003b7b0  lea     r9d, [rax+0Eh]
0x18003b7b4  mov     ebx, r9d
0x18003b7b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b7be  lea     rax, WPP_GLOBAL_Control
0x18003b7c5  cmp     rcx, rax
0x18003b7c8  jz      loc_18003BC13
0x18003b7ce  test    byte ptr [rcx+1Ch], 10h
0x18003b7d2  jz      loc_18003BC13
0x18003b7d8  lea     edx, [r9+14h]
0x18003b7dc  jmp     loc_18003BC03
0x18003b7e1  mov     rcx, [rbp+hKey]; hKey
0x18003b7e5  lea     rax, [rbp+cbData]
0x18003b7e9  mov     r14d, 1
0x18003b7ef  mov     [rsp+50h+phkResult], rax; __int64
0x18003b7f4  mov     r8d, r14d
0x18003b7f7  lea     r9, [rdi+8]
0x18003b7fb  lea     rdx, aIpsecname; "ipsecName"
0x18003b802  call    RegstoreQueryValue
0x18003b807  mov     ebx, eax
0x18003b809  test    eax, eax
0x18003b80b  jz      short loc_18003B837
0x18003b80d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b814  lea     rax, WPP_GLOBAL_Control
0x18003b81b  cmp     rcx, rax
0x18003b81e  jz      loc_18003BC13
0x18003b824  test    byte ptr [rcx+1Ch], 10h
0x18003b828  jz      loc_18003BC13
0x18003b82e  lea     edx, [r14+22h]
0x18003b832  jmp     loc_18003B756
0x18003b837  mov     rcx, [rbp+hKey]; hKey
0x18003b83b  lea     rax, [rbp+cbData]
0x18003b83f  lea     r9, [rdi+88h]
0x18003b846  mov     [rsp+50h+phkResult], rax; __int64
0x18003b84b  mov     r8d, r14d
0x18003b84e  lea     rdx, aDescription; "description"
0x18003b855  call    RegstoreQueryValue
0x18003b85a  mov     rcx, [rbp+hKey]; hKey
0x18003b85e  lea     rax, [rbp+cbData]
0x18003b862  lea     r9, [rdi+10h]
0x18003b866  mov     [rsp+50h+phkResult], rax; __int64
0x18003b86b  mov     r8d, r14d
0x18003b86e  lea     rdx, aIpsecid; "ipsecID"
0x18003b875  call    RegstoreQueryValue
0x18003b87a  mov     ebx, eax
0x18003b87c  test    eax, eax
0x18003b87e  jz      short loc_18003B8AB
0x18003b880  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b887  lea     rax, WPP_GLOBAL_Control
0x18003b88e  cmp     rcx, rax
0x18003b891  jz      loc_18003BC13
0x18003b897  test    byte ptr [rcx+1Ch], 10h
0x18003b89b  jz      loc_18003BC13
0x18003b8a1  mov     edx, 24h ; '$'
0x18003b8a6  jmp     loc_18003B756
0x18003b8ab  mov     rcx, [rbp+hKey]; hKey
0x18003b8af  lea     r9, [rbp+Type]; lpType
0x18003b8b3  mov     eax, 4
0x18003b8b8  lea     rdx, aIpsecdatatype; "ipsecDataType"
0x18003b8bf  mov     [rbp+Type], eax
0x18003b8c2  xor     r8d, r8d; lpReserved
0x18003b8c5  mov     [rbp+cbData], eax
0x18003b8c8  lea     rax, [rbp+cbData]
0x18003b8cc  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18003b8d1  lea     rax, [rbp+Data]
0x18003b8d5  mov     [rsp+50h+phkResult], rax; lpData
0x18003b8da  call    cs:__imp_RegQueryValueExW
0x18003b8e0  mov     ebx, eax
0x18003b8e2  test    eax, eax
0x18003b8e4  jz      short loc_18003B911
0x18003b8e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b8ed  lea     rax, WPP_GLOBAL_Control
0x18003b8f4  cmp     rcx, rax
0x18003b8f7  jz      loc_18003BC13
0x18003b8fd  test    byte ptr [rcx+1Ch], 10h
0x18003b901  jz      loc_18003BC13
0x18003b907  mov     edx, 25h ; '%'
0x18003b90c  jmp     loc_18003B756
0x18003b911  mov     eax, dword ptr [rbp+Data]
0x18003b914  lea     r9, [rdi+20h]
0x18003b918  mov     [rdi+18h], eax
0x18003b91b  lea     rdx, attr; "ipsecData"
0x18003b922  mov     rcx, [rbp+hKey]; hKey
0x18003b926  lea     rax, [rdi+28h]
0x18003b92a  mov     r8d, 3
0x18003b930  mov     [rsp+50h+phkResult], rax; __int64
0x18003b935  call    RegstoreQueryValue
0x18003b93a  mov     ebx, eax
0x18003b93c  test    eax, eax
0x18003b93e  jz      short loc_18003B96B
0x18003b940  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b947  lea     rax, WPP_GLOBAL_Control
0x18003b94e  cmp     rcx, rax
0x18003b951  jz      loc_18003BC13
0x18003b957  test    byte ptr [rcx+1Ch], 10h
0x18003b95b  jz      loc_18003BC13
0x18003b961  mov     edx, 26h ; '&'
0x18003b966  jmp     loc_18003B756
0x18003b96b  mov     rcx, [rbp+hKey]; hKey
0x18003b96f  lea     rax, [rbp+cbData]
0x18003b973  lea     r9, [rdi+30h]
0x18003b977  mov     [rsp+50h+phkResult], rax; __int64
0x18003b97c  mov     r8d, r14d
0x18003b97f  lea     rdx, aIpsecisakmpref; "ipsecISAKMPReference"
0x18003b986  call    RegstoreQueryValue
0x18003b98b  mov     ebx, eax
0x18003b98d  test    eax, eax
0x18003b98f  jz      short loc_18003B9BC
0x18003b991  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b998  lea     rax, WPP_GLOBAL_Control
0x18003b99f  cmp     rcx, rax
0x18003b9a2  jz      loc_18003BC13
0x18003b9a8  test    byte ptr [rcx+1Ch], 10h
0x18003b9ac  jz      loc_18003BC13
0x18003b9b2  mov     edx, 27h ; '''
0x18003b9b7  jmp     loc_18003B756
0x18003b9bc  mov     rcx, [rbp+hKey]; hKey
0x18003b9c0  lea     rax, [rbp+cbData]
0x18003b9c4  lea     r9, [rbp+lpMem]
0x18003b9c8  mov     [rsp+50h+phkResult], rax; __int64
0x18003b9cd  mov     r8d, 7
0x18003b9d3  lea     rdx, aIpsecnfarefere; "ipsecNFAReference"
0x18003b9da  call    RegstoreQueryValue
0x18003b9df  mov     ebx, eax
0x18003b9e1  test    eax, eax
0x18003b9e3  jz      short loc_18003BA1F
0x18003b9e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b9ec  lea     rax, WPP_GLOBAL_Control
0x18003b9f3  cmp     rcx, rax
0x18003b9f6  jz      short loc_18003BA16
0x18003b9f8  test    byte ptr [rcx+1Ch], 10h
0x18003b9fc  jz      short loc_18003BA16
0x18003b9fe  mov     rcx, [rcx+10h]
0x18003ba02  lea     r8, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids
0x18003ba09  mov     edx, 28h ; '('
0x18003ba0e  mov     r9d, ebx
0x18003ba11  call    WPP_SF_d
0x18003ba16  mov     rsi, [rbp+lpMem]
0x18003ba1a  jmp     loc_18003BC13
0x18003ba1f  mov     rsi, [rbp+lpMem]
0x18003ba23  mov     r15d, r13d
0x18003ba26  mov     rax, rsi
0x18003ba29  cmp     [rsi], r13w
0x18003ba2d  jz      short loc_18003BA4D
0x18003ba2f  mov     rcx, r12
0x18003ba32  inc     rcx
0x18003ba35  cmp     [rax+rcx*2], r13w
0x18003ba3a  jnz     short loc_18003BA32
0x18003ba3c  lea     rax, [rax+rcx*2]
0x18003ba40  add     r15d, r14d
0x18003ba43  add     rax, 2
0x18003ba47  cmp     [rax], r13w
0x18003ba4b  jnz     short loc_18003BA2F
0x18003ba4d  mov     ecx, r15d
0x18003ba50  lea     r8, [rbp+var_8]
0x18003ba54  mov     edx, 8
0x18003ba59  call    NsuSizeTMultiply
0x18003ba5e  mov     ebx, eax
0x18003ba60  test    eax, eax
0x18003ba62  jz      short loc_18003BA8F
0x18003ba64  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ba6b  lea     rax, WPP_GLOBAL_Control
0x18003ba72  cmp     rcx, rax
0x18003ba75  jz      loc_18003BC13
0x18003ba7b  test    byte ptr [rcx+1Ch], 10h
0x18003ba7f  jz      loc_18003BC13
0x18003ba85  mov     edx, 29h ; ')'
0x18003ba8a  jmp     loc_18003B756
0x18003ba8f  mov     rcx, [rbp+var_8]
0x18003ba93  call    IpsecAllocMem
0x18003ba98  mov     r12, rax
0x18003ba9b  test    rax, rax
0x18003ba9e  jnz     short loc_18003BAD2
0x18003baa0  lea     r9d, [rax+0Eh]
0x18003baa4  mov     ebx, r9d
0x18003baa7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003baae  lea     rax, WPP_GLOBAL_Control
0x18003bab5  cmp     rcx, rax
0x18003bab8  jz      loc_18003BC13
0x18003babe  test    byte ptr [rcx+1Ch], 10h
0x18003bac2  jz      loc_18003BC13
0x18003bac8  lea     edx, [r12+2Ah]
0x18003bacd  jmp     loc_18003BC03
0x18003bad2  mov     rbx, rsi
0x18003bad5  mov     r14d, r13d
0x18003bad8  cmp     r14d, r15d
0x18003badb  jnb     short loc_18003BB47
0x18003badd  mov     rcx, rbx; unsigned __int16 *
0x18003bae0  call    IpsecAllocStr
0x18003bae5  test    rax, rax
0x18003bae8  jz      short loc_18003BB0C
0x18003baea  mov     ecx, r14d
0x18003baed  mov     [r12+rcx*8], rax
0x18003baf1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003baf5  inc     rax
0x18003baf8  cmp     [rbx+rax*2], r13w
0x18003bafd  jnz     short loc_18003BAF5
0x18003baff  lea     rbx, [rbx+rax*2]
0x18003bb03  add     rbx, 2
0x18003bb07  inc     r14d
0x18003bb0a  jmp     short loc_18003BAD8
0x18003bb0c  mov     r9d, 0Eh
0x18003bb12  mov     [rdi+40h], r12
0x18003bb16  mov     ebx, r9d
0x18003bb19  mov     [rdi+38h], r14d
0x18003bb1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bb24  lea     rax, WPP_GLOBAL_Control
0x18003bb2b  cmp     rcx, rax
0x18003bb2e  jz      loc_18003BC13
0x18003bb34  test    byte ptr [rcx+1Ch], 10h
  ... truncated ...
```
