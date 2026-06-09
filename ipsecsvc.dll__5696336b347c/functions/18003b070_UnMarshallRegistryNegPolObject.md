# UnMarshallRegistryNegPolObject

- ea: `0x18003b070`
- end: `0x18003b647`
- name: `UnMarshallRegistryNegPolObject`
- size: `1495`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180039ae0`

## callees

- `0x180006f00`
- `0x180006f60`
- `0x18000c828`
- `0x18000e510`
- `0x180039f64`
- `0x18003b070`
- `0x180042d44`
- `0x180042ef8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b363`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b58f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b363`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b58f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b13e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b13e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b627`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b627`

## pseudocode

```c
__int64 __fastcall UnMarshallRegistryNegPolObject(HKEY hKey, __int64 a2, unsigned __int16 *a3, __int64 a4, _QWORD *a5)
{
  __int64 v7; // rdx
  unsigned __int64 v8; // r8
  __int64 v9; // r9
  unsigned int Value; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  _DWORD *v13; // rdi
  unsigned __int16 *v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned __int16 *v18; // r14
  unsigned int v19; // esi
  _WORD *i; // rax
  __int64 v21; // rcx
  _QWORD *v22; // r12
  unsigned __int16 *v23; // rbx
  unsigned int j; // r15d
  unsigned __int16 *v25; // rax
  __int64 v26; // rax
  BYTE Data[4]; // [rsp+30h] [rbp-20h] BYREF
  BYTE v29[4]; // [rsp+34h] [rbp-1Ch] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-18h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-10h]
  SIZE_T v32; // [rsp+48h] [rbp-8h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+50h] BYREF
  DWORD cbData; // [rsp+A8h] [rbp+58h] BYREF

  hKeya = 0;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v29 = 0;
  lpMem = 0;
  v32 = 0;
  if ( !a3 || !*a3 )
  {
    v9 = 13;
    Value = 13;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v12 = 69;
LABEL_82:
    WPP_SF_d(v11[2], v12, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, v9);
    goto LABEL_83;
  }
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(a2 + 2 * v7) );
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  if ( v8 <= (unsigned int)(v7 + 1) )
  {
    v9 = 13;
    Value = 13;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v12 = 70;
    goto LABEL_82;
  }
  Value = RegOpenKeyExW(hKey, &a3[(unsigned int)v7 + 1], 0, 0x20019u, &hKeya);
  if ( Value )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v12 = 71;
    v9 = Value;
    goto LABEL_82;
  }
  v13 = IpsecAllocMem(0x58u);
  if ( !v13 )
  {
    Value = 14;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_83;
    v12 = 72;
    v9 = 14;
    goto LABEL_82;
  }
  v14 = IpsecAllocStr(a3);
  *(_QWORD *)v13 = v14;
  if ( !v14 )
  {
    Value = 14;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_77;
    v16 = 73;
    goto LABEL_23;
  }
  RegstoreQueryValue(hKeya, L"ipsecName", (__int64)&cbData);
  RegstoreQueryValue(hKeya, L"description", (__int64)&cbData);
  Value = RegstoreQueryValue(hKeya, L"ipsecID", (__int64)&cbData);
  if ( Value )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_77;
    v16 = 74;
    goto LABEL_75;
  }
  Value = RegstoreQueryValue(hKeya, L"ipsecNegotiationPolicyAction", (__int64)&cbData);
  if ( Value )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_77;
    v16 = 75;
    goto LABEL_75;
  }
  Value = RegstoreQueryValue(hKeya, L"ipsecNegotiationPolicyType", (__int64)&cbData);
  if ( Value )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_77;
    v16 = 76;
    goto LABEL_75;
  }
  Type = 4;
  cbData = 4;
  Value = RegQueryValueExW(hKeya, L"ipsecDataType", 0, &Type, Data, &cbData);
  if ( Value )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_77;
    v16 = 77;
    goto LABEL_75;
  }
  v13[6] = *(_DWORD *)Data;
  Value = RegstoreQueryValue(hKeya, L"ipsecData", (__int64)(v13 + 10));
  if ( Value )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_77;
    v16 = 78;
    goto LABEL_75;
  }
  if ( (unsigned int)RegstoreQueryValue(hKeya, L"ipsecOwnersReference", (__int64)&cbData) )
  {
LABEL_71:
    Type = 4;
    cbData = 4;
    Value = RegQueryValueExW(hKeya, L"whenChanged", 0, &Type, v29, &cbData);
    if ( !Value )
    {
      v13[19] = *(_DWORD *)v29;
      goto LABEL_84;
    }
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_77;
    v16 = 82;
LABEL_75:
    v17 = Value;
    goto LABEL_76;
  }
  v18 = (unsigned __int16 *)lpMem;
  v19 = 0;
  for ( i = lpMem; *i; i += v21 + 1 )
  {
    v21 = -1;
    do
      ++v21;
    while ( i[v21] );
    ++v19;
  }
  Value = NsuSizeTMultiply(v19, 8, &v32);
  if ( Value )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_77;
    v16 = 79;
    goto LABEL_75;
  }
  v22 = IpsecAllocMem(v32);
  if ( v22 )
  {
    v23 = v18;
    for ( j = 0; ; ++j )
    {
      if ( j >= v19 )
      {
        if ( v18 )
          IpsecFreeMem(v18);
        v13[18] = v19;
        *((_QWORD *)v13 + 8) = v22;
        goto LABEL_71;
      }
      v25 = IpsecAllocStr(v23);
      if ( !v25 )
        break;
      v22[j] = v25;
      v26 = -1;
      do
        ++v26;
      while ( v23[v26] );
      v23 += v26 + 1;
    }
    *((_QWORD *)v13 + 8) = v22;
    v13[18] = j;
    Value = 14;
    if ( v18 )
      IpsecFreeMem(v18);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v16 = 81;
      goto LABEL_23;
    }
    goto LABEL_77;
  }
  Value = 14;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v16 = 80;
LABEL_23:
    v17 = 14;
LABEL_76:
    WPP_SF_d(v15[2], v16, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, v17);
  }
LABEL_77:
  FreeIpsecNegPolObject(v13);
LABEL_83:
  v13 = 0;
LABEL_84:
  *a5 = v13;
  if ( hKeya )
    RegCloseKey(hKeya);
  return Value;
}

```

## disassembly

```asm
0x18003b070  mov     [rsp-38h+arg_0], rbx
0x18003b075  mov     [rsp-38h+cbData], r9d
0x18003b07a  push    rbp
0x18003b07b  push    rsi
0x18003b07c  push    rdi
0x18003b07d  push    r12
0x18003b07f  push    r13
0x18003b081  push    r14
0x18003b083  push    r15
0x18003b085  mov     rbp, rsp
0x18003b088  sub     rsp, 50h
0x18003b08c  xor     r13d, r13d
0x18003b08f  mov     rsi, r8
0x18003b092  mov     [rbp+hKey], r13
0x18003b096  mov     rax, rdx
0x18003b099  mov     [rbp+Type], r13d
0x18003b09d  mov     r10, rcx
0x18003b0a0  mov     [rbp+cbData], r13d
0x18003b0a4  mov     dword ptr [rbp+Data], r13d
0x18003b0a8  mov     dword ptr [rbp+var_1C], r13d
0x18003b0ac  mov     [rbp+lpMem], r13
0x18003b0b0  mov     [rbp+var_8], r13
0x18003b0b4  test    r8, r8
0x18003b0b7  jz      loc_18003B5DE
0x18003b0bd  cmp     [r8], r13w
0x18003b0c1  jz      loc_18003B5DE
0x18003b0c7  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003b0cb  mov     rdx, r12
0x18003b0ce  inc     rdx
0x18003b0d1  cmp     [rax+rdx*2], r13w
0x18003b0d6  jnz     short loc_18003B0CE
0x18003b0d8  mov     r8, r12
0x18003b0db  inc     r8
0x18003b0de  cmp     [rsi+r8*2], r13w
0x18003b0e3  jnz     short loc_18003B0DB
0x18003b0e5  lea     ecx, [rdx+1]
0x18003b0e8  cmp     r8, rcx
0x18003b0eb  ja      short loc_18003B120
0x18003b0ed  mov     r9d, 0Dh
0x18003b0f3  mov     ebx, r9d
0x18003b0f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b0fd  lea     rax, WPP_GLOBAL_Control
0x18003b104  cmp     rcx, rax
0x18003b107  jz      loc_18003B614
0x18003b10d  test    byte ptr [rcx+1Ch], 10h
0x18003b111  jz      loc_18003B614
0x18003b117  lea     edx, [r9+39h]
0x18003b11b  jmp     loc_18003B604
0x18003b120  mov     eax, edx
0x18003b122  mov     r9d, 20019h; samDesired
0x18003b128  inc     rax
0x18003b12b  xor     r8d, r8d; ulOptions
0x18003b12e  mov     rcx, r10; hKey
0x18003b131  lea     rdx, [rsi+rax*2]; lpSubKey
0x18003b135  lea     rax, [rbp+hKey]
0x18003b139  mov     [rsp+50h+phkResult], rax; phkResult
0x18003b13e  call    cs:__imp_RegOpenKeyExW
0x18003b144  mov     ebx, eax
0x18003b146  test    eax, eax
0x18003b148  jz      short loc_18003B178
0x18003b14a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b151  lea     rax, WPP_GLOBAL_Control
0x18003b158  cmp     rcx, rax
0x18003b15b  jz      loc_18003B614
0x18003b161  test    byte ptr [rcx+1Ch], 10h
0x18003b165  jz      loc_18003B614
0x18003b16b  mov     edx, 47h ; 'G'
0x18003b170  mov     r9d, ebx
0x18003b173  jmp     loc_18003B604
0x18003b178  mov     ecx, 58h ; 'X'
0x18003b17d  call    IpsecAllocMem
0x18003b182  mov     rdi, rax
0x18003b185  test    rax, rax
0x18003b188  jnz     short loc_18003B1BB
0x18003b18a  lea     esi, [rax+0Eh]
0x18003b18d  mov     ebx, esi
0x18003b18f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b196  lea     rax, WPP_GLOBAL_Control
0x18003b19d  cmp     rcx, rax
0x18003b1a0  jz      loc_18003B614
0x18003b1a6  test    byte ptr [rcx+1Ch], 10h
0x18003b1aa  jz      loc_18003B614
0x18003b1b0  lea     edx, [rdi+48h]
0x18003b1b3  mov     r9d, esi
0x18003b1b6  jmp     loc_18003B604
0x18003b1bb  mov     rcx, rsi; unsigned __int16 *
0x18003b1be  call    IpsecAllocStr
0x18003b1c3  mov     [rdi], rax
0x18003b1c6  test    rax, rax
0x18003b1c9  jnz     short loc_18003B1FC
0x18003b1cb  lea     esi, [rax+0Eh]
0x18003b1ce  mov     ebx, esi
0x18003b1d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b1d7  lea     rax, WPP_GLOBAL_Control
0x18003b1de  cmp     rcx, rax
0x18003b1e1  jz      loc_18003B5CC
0x18003b1e7  test    byte ptr [rcx+1Ch], 10h
0x18003b1eb  jz      loc_18003B5CC
0x18003b1f1  lea     edx, [rsi+3Bh]
0x18003b1f4  mov     r9d, esi
0x18003b1f7  jmp     loc_18003B5BC
0x18003b1fc  mov     rcx, [rbp+hKey]; hKey
0x18003b200  lea     rax, [rbp+cbData]
0x18003b204  mov     r15d, 1
0x18003b20a  mov     [rsp+50h+phkResult], rax; __int64
0x18003b20f  mov     r8d, r15d
0x18003b212  lea     r9, [rdi+8]
0x18003b216  lea     rdx, aIpsecname; "ipsecName"
0x18003b21d  call    RegstoreQueryValue
0x18003b222  mov     rcx, [rbp+hKey]; hKey
0x18003b226  lea     rax, [rbp+cbData]
0x18003b22a  lea     r9, [rdi+50h]
0x18003b22e  mov     [rsp+50h+phkResult], rax; __int64
0x18003b233  mov     r8d, r15d
0x18003b236  lea     rdx, aDescription; "description"
0x18003b23d  call    RegstoreQueryValue
0x18003b242  mov     rcx, [rbp+hKey]; hKey
0x18003b246  lea     rax, [rbp+cbData]
0x18003b24a  lea     r9, [rdi+10h]
0x18003b24e  mov     [rsp+50h+phkResult], rax; __int64
0x18003b253  mov     r8d, r15d
0x18003b256  lea     rdx, aIpsecid; "ipsecID"
0x18003b25d  call    RegstoreQueryValue
0x18003b262  mov     ebx, eax
0x18003b264  test    eax, eax
0x18003b266  jz      short loc_18003B292
0x18003b268  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b26f  lea     rax, WPP_GLOBAL_Control
0x18003b276  cmp     rcx, rax
0x18003b279  jz      loc_18003B5CC
0x18003b27f  test    byte ptr [rcx+1Ch], 10h
0x18003b283  jz      loc_18003B5CC
0x18003b289  lea     edx, [r15+49h]
0x18003b28d  jmp     loc_18003B5B9
0x18003b292  mov     rcx, [rbp+hKey]; hKey
0x18003b296  lea     rax, [rbp+cbData]
0x18003b29a  lea     r9, [rdi+30h]
0x18003b29e  mov     [rsp+50h+phkResult], rax; __int64
0x18003b2a3  mov     r8d, r15d
0x18003b2a6  lea     rdx, aIpsecnegotiati; "ipsecNegotiationPolicyAction"
0x18003b2ad  call    RegstoreQueryValue
0x18003b2b2  mov     ebx, eax
0x18003b2b4  test    eax, eax
0x18003b2b6  jz      short loc_18003B2E3
0x18003b2b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b2bf  lea     rax, WPP_GLOBAL_Control
0x18003b2c6  cmp     rcx, rax
0x18003b2c9  jz      loc_18003B5CC
0x18003b2cf  test    byte ptr [rcx+1Ch], 10h
0x18003b2d3  jz      loc_18003B5CC
0x18003b2d9  mov     edx, 4Bh ; 'K'
0x18003b2de  jmp     loc_18003B5B9
0x18003b2e3  mov     rcx, [rbp+hKey]; hKey
0x18003b2e7  lea     rax, [rbp+cbData]
0x18003b2eb  lea     r9, [rdi+38h]
0x18003b2ef  mov     [rsp+50h+phkResult], rax; __int64
0x18003b2f4  mov     r8d, r15d
0x18003b2f7  lea     rdx, aIpsecnegotiati_1; "ipsecNegotiationPolicyType"
0x18003b2fe  call    RegstoreQueryValue
0x18003b303  mov     ebx, eax
0x18003b305  test    eax, eax
0x18003b307  jz      short loc_18003B334
0x18003b309  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b310  lea     rax, WPP_GLOBAL_Control
0x18003b317  cmp     rcx, rax
0x18003b31a  jz      loc_18003B5CC
0x18003b320  test    byte ptr [rcx+1Ch], 10h
0x18003b324  jz      loc_18003B5CC
0x18003b32a  mov     edx, 4Ch ; 'L'
0x18003b32f  jmp     loc_18003B5B9
0x18003b334  mov     rcx, [rbp+hKey]; hKey
0x18003b338  lea     rax, [rbp+cbData]
0x18003b33c  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18003b341  lea     r9, [rbp+Type]; lpType
0x18003b345  lea     rax, [rbp+Data]
0x18003b349  mov     esi, 4
0x18003b34e  xor     r8d, r8d; lpReserved
0x18003b351  mov     [rsp+50h+phkResult], rax; lpData
0x18003b356  lea     rdx, aIpsecdatatype; "ipsecDataType"
0x18003b35d  mov     [rbp+Type], esi
0x18003b360  mov     [rbp+cbData], esi
0x18003b363  call    cs:__imp_RegQueryValueExW
0x18003b369  mov     ebx, eax
0x18003b36b  test    eax, eax
0x18003b36d  jz      short loc_18003B398
0x18003b36f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b376  lea     rax, WPP_GLOBAL_Control
0x18003b37d  cmp     rcx, rax
0x18003b380  jz      loc_18003B5CC
0x18003b386  test    byte ptr [rcx+1Ch], 10h
0x18003b38a  jz      loc_18003B5CC
0x18003b390  lea     edx, [rsi+49h]
0x18003b393  jmp     loc_18003B5B9
0x18003b398  mov     eax, dword ptr [rbp+Data]
0x18003b39b  lea     r9, [rdi+20h]
0x18003b39f  mov     [rdi+18h], eax
0x18003b3a2  lea     rdx, attr; "ipsecData"
0x18003b3a9  mov     rcx, [rbp+hKey]; hKey
0x18003b3ad  lea     rax, [rdi+28h]
0x18003b3b1  mov     r8d, 3
0x18003b3b7  mov     [rsp+50h+phkResult], rax; __int64
0x18003b3bc  call    RegstoreQueryValue
0x18003b3c1  mov     ebx, eax
0x18003b3c3  test    eax, eax
0x18003b3c5  jz      short loc_18003B3F2
0x18003b3c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b3ce  lea     rax, WPP_GLOBAL_Control
0x18003b3d5  cmp     rcx, rax
0x18003b3d8  jz      loc_18003B5CC
0x18003b3de  test    byte ptr [rcx+1Ch], 10h
0x18003b3e2  jz      loc_18003B5CC
0x18003b3e8  mov     edx, 4Eh ; 'N'
0x18003b3ed  jmp     loc_18003B5B9
0x18003b3f2  mov     rcx, [rbp+hKey]; hKey
0x18003b3f6  lea     rax, [rbp+cbData]
0x18003b3fa  lea     r9, [rbp+lpMem]
0x18003b3fe  mov     [rsp+50h+phkResult], rax; __int64
0x18003b403  mov     r8d, 7
0x18003b409  lea     rdx, aIpsecownersref; "ipsecOwnersReference"
0x18003b410  call    RegstoreQueryValue
0x18003b415  test    eax, eax
0x18003b417  jnz     loc_18003B565
0x18003b41d  mov     r14, [rbp+lpMem]
0x18003b421  mov     esi, r13d
0x18003b424  mov     rax, r14
0x18003b427  cmp     [r14], r13w
0x18003b42b  jz      short loc_18003B44B
0x18003b42d  mov     rcx, r12
0x18003b430  inc     rcx
0x18003b433  cmp     [rax+rcx*2], r13w
0x18003b438  jnz     short loc_18003B430
0x18003b43a  lea     rax, [rax+rcx*2]
0x18003b43e  add     esi, r15d
0x18003b441  add     rax, 2
0x18003b445  cmp     [rax], r13w
0x18003b449  jnz     short loc_18003B42D
0x18003b44b  mov     ecx, esi
0x18003b44d  lea     r8, [rbp+var_8]
0x18003b451  mov     edx, 8
0x18003b456  call    NsuSizeTMultiply
0x18003b45b  mov     ebx, eax
0x18003b45d  test    eax, eax
0x18003b45f  jz      short loc_18003B48C
0x18003b461  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b468  lea     rax, WPP_GLOBAL_Control
0x18003b46f  cmp     rcx, rax
0x18003b472  jz      loc_18003B5CC
0x18003b478  test    byte ptr [rcx+1Ch], 10h
0x18003b47c  jz      loc_18003B5CC
0x18003b482  mov     edx, 4Fh ; 'O'
0x18003b487  jmp     loc_18003B5B9
0x18003b48c  mov     rcx, [rbp+var_8]
0x18003b490  call    IpsecAllocMem
0x18003b495  mov     r12, rax
0x18003b498  test    rax, rax
0x18003b49b  jnz     short loc_18003B4CB
0x18003b49d  lea     esi, [rax+0Eh]
0x18003b4a0  mov     ebx, esi
0x18003b4a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b4a9  lea     rax, WPP_GLOBAL_Control
0x18003b4b0  cmp     rcx, rax
0x18003b4b3  jz      loc_18003B5CC
0x18003b4b9  test    byte ptr [rcx+1Ch], 10h
0x18003b4bd  jz      loc_18003B5CC
0x18003b4c3  lea     edx, [rsi+42h]
0x18003b4c6  jmp     loc_18003B1F4
0x18003b4cb  mov     rbx, r14
0x18003b4ce  mov     r15d, r13d
0x18003b4d1  cmp     r15d, esi
0x18003b4d4  jnb     short loc_18003B54C
0x18003b4d6  mov     rcx, rbx; unsigned __int16 *
0x18003b4d9  call    IpsecAllocStr
0x18003b4de  test    rax, rax
0x18003b4e1  jz      short loc_18003B505
0x18003b4e3  mov     ecx, r15d
0x18003b4e6  mov     [r12+rcx*8], rax
0x18003b4ea  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003b4ee  inc     rax
0x18003b4f1  cmp     [rbx+rax*2], r13w
0x18003b4f6  jnz     short loc_18003B4EE
0x18003b4f8  lea     rbx, [rbx+rax*2]
0x18003b4fc  add     rbx, 2
0x18003b500  inc     r15d
0x18003b503  jmp     short loc_18003B4D1
0x18003b505  mov     [rdi+40h], r12
0x18003b509  mov     esi, 0Eh
0x18003b50e  mov     [rdi+48h], r15d
0x18003b512  mov     ebx, esi
0x18003b514  test    r14, r14
0x18003b517  jz      short loc_18003B521
0x18003b519  mov     rcx, r14; lpMem
0x18003b51c  call    IpsecFreeMem
0x18003b521  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b528  lea     rax, WPP_GLOBAL_Control
0x18003b52f  cmp     rcx, rax
0x18003b532  jz      loc_18003B5CC
0x18003b538  test    byte ptr [rcx+1Ch], 10h
0x18003b53c  jz      loc_18003B5CC
0x18003b542  mov     edx, 51h ; 'Q'
0x18003b547  jmp     loc_18003B1F4
  ... truncated ...
```
