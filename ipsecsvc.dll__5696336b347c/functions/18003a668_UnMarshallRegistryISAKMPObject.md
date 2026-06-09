# UnMarshallRegistryISAKMPObject

- ea: `0x18003a668`
- end: `0x18003ab7e`
- name: `UnMarshallRegistryISAKMPObject`
- size: `1302`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180039614`

## callees

- `0x180006f00`
- `0x180006f60`
- `0x18000c828`
- `0x18000e510`
- `0x180039f64`
- `0x18003a668`
- `0x180042bbc`
- `0x180042ef8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003a89a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003aac6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003a89a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003aac6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a736`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a736`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ab5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ab5e`

## pseudocode

```c
__int64 __fastcall UnMarshallRegistryISAKMPObject(HKEY hKey, __int64 a2, unsigned __int16 *a3, __int64 a4, _QWORD *a5)
{
  __int64 v7; // rdx
  unsigned __int64 v8; // r8
  __int64 v9; // r9
  unsigned int Value; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  _DWORD *v13; // rsi
  unsigned __int16 *v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned __int16 *v18; // r14
  unsigned int v19; // edi
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
      goto LABEL_75;
    v12 = 83;
LABEL_74:
    WPP_SF_d(v11[2], v12, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, v9);
    goto LABEL_75;
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
      goto LABEL_75;
    v12 = 84;
    goto LABEL_74;
  }
  Value = RegOpenKeyExW(hKey, &a3[(unsigned int)v7 + 1], 0, 0x20019u, &hKeya);
  if ( Value )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_75;
    v12 = 85;
    v9 = Value;
    goto LABEL_74;
  }
  v13 = IpsecAllocMem(0x40u);
  if ( !v13 )
  {
    Value = 14;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_75;
    v12 = 86;
    v9 = 14;
    goto LABEL_74;
  }
  v14 = IpsecAllocStr(a3);
  *(_QWORD *)v13 = v14;
  if ( !v14 )
  {
    Value = 14;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_69;
    v16 = 87;
    goto LABEL_23;
  }
  RegstoreQueryValue(hKeya, L"ipsecName", (__int64)&cbData);
  Value = RegstoreQueryValue(hKeya, L"ipsecID", (__int64)&cbData);
  if ( Value )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_69;
    v16 = 88;
    goto LABEL_67;
  }
  Type = 4;
  cbData = 4;
  Value = RegQueryValueExW(hKeya, L"ipsecDataType", 0, &Type, Data, &cbData);
  if ( Value )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_69;
    v16 = 89;
    goto LABEL_67;
  }
  v13[6] = *(_DWORD *)Data;
  Value = RegstoreQueryValue(hKeya, L"ipsecData", (__int64)(v13 + 10));
  if ( Value )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_69;
    v16 = 90;
    goto LABEL_67;
  }
  if ( (unsigned int)RegstoreQueryValue(hKeya, L"ipsecOwnersReference", (__int64)&cbData) )
  {
LABEL_63:
    Type = 4;
    cbData = 4;
    Value = RegQueryValueExW(hKeya, L"whenChanged", 0, &Type, v29, &cbData);
    if ( !Value )
    {
      v13[15] = *(_DWORD *)v29;
      goto LABEL_76;
    }
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_69;
    v16 = 94;
LABEL_67:
    v17 = Value;
    goto LABEL_68;
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
      goto LABEL_69;
    v16 = 91;
    goto LABEL_67;
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
        v13[14] = v19;
        *((_QWORD *)v13 + 6) = v22;
        goto LABEL_63;
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
    *((_QWORD *)v13 + 6) = v22;
    v13[14] = j;
    Value = 14;
    if ( v18 )
      IpsecFreeMem(v18);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v16 = 93;
      goto LABEL_23;
    }
    goto LABEL_69;
  }
  Value = 14;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v16 = 92;
LABEL_23:
    v17 = 14;
LABEL_68:
    WPP_SF_d(v15[2], v16, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, v17);
  }
LABEL_69:
  FreeIpsecISAKMPObject(v13);
LABEL_75:
  v13 = 0;
LABEL_76:
  *a5 = v13;
  if ( hKeya )
    RegCloseKey(hKeya);
  return Value;
}

```

## disassembly

```asm
0x18003a668  mov     [rsp-38h+arg_0], rbx
0x18003a66d  mov     [rsp-38h+cbData], r9d
0x18003a672  push    rbp
0x18003a673  push    rsi
0x18003a674  push    rdi
0x18003a675  push    r12
0x18003a677  push    r13
0x18003a679  push    r14
0x18003a67b  push    r15
0x18003a67d  mov     rbp, rsp
0x18003a680  sub     rsp, 50h
0x18003a684  xor     r13d, r13d
0x18003a687  mov     rdi, r8
0x18003a68a  mov     [rbp+hKey], r13
0x18003a68e  mov     rax, rdx
0x18003a691  mov     [rbp+Type], r13d
0x18003a695  mov     r10, rcx
0x18003a698  mov     [rbp+cbData], r13d
0x18003a69c  mov     dword ptr [rbp+Data], r13d
0x18003a6a0  mov     dword ptr [rbp+var_1C], r13d
0x18003a6a4  mov     [rbp+lpMem], r13
0x18003a6a8  mov     [rbp+var_8], r13
0x18003a6ac  test    r8, r8
0x18003a6af  jz      loc_18003AB15
0x18003a6b5  cmp     [r8], r13w
0x18003a6b9  jz      loc_18003AB15
0x18003a6bf  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003a6c3  mov     rdx, r15
0x18003a6c6  inc     rdx
0x18003a6c9  cmp     [rax+rdx*2], r13w
0x18003a6ce  jnz     short loc_18003A6C6
0x18003a6d0  mov     r8, r15
0x18003a6d3  inc     r8
0x18003a6d6  cmp     [rdi+r8*2], r13w
0x18003a6db  jnz     short loc_18003A6D3
0x18003a6dd  lea     ecx, [rdx+1]
0x18003a6e0  cmp     r8, rcx
0x18003a6e3  ja      short loc_18003A718
0x18003a6e5  mov     r9d, 0Dh
0x18003a6eb  mov     ebx, r9d
0x18003a6ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a6f5  lea     rax, WPP_GLOBAL_Control
0x18003a6fc  cmp     rcx, rax
0x18003a6ff  jz      loc_18003AB4B
0x18003a705  test    byte ptr [rcx+1Ch], 10h
0x18003a709  jz      loc_18003AB4B
0x18003a70f  lea     edx, [r9+47h]
0x18003a713  jmp     loc_18003AB3B
0x18003a718  mov     eax, edx
0x18003a71a  mov     r9d, 20019h; samDesired
0x18003a720  inc     rax
0x18003a723  xor     r8d, r8d; ulOptions
0x18003a726  mov     rcx, r10; hKey
0x18003a729  lea     rdx, [rdi+rax*2]; lpSubKey
0x18003a72d  lea     rax, [rbp+hKey]
0x18003a731  mov     [rsp+50h+phkResult], rax; phkResult
0x18003a736  call    cs:__imp_RegOpenKeyExW
0x18003a73c  mov     ebx, eax
0x18003a73e  test    eax, eax
0x18003a740  jz      short loc_18003A770
0x18003a742  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a749  lea     rax, WPP_GLOBAL_Control
0x18003a750  cmp     rcx, rax
0x18003a753  jz      loc_18003AB4B
0x18003a759  test    byte ptr [rcx+1Ch], 10h
0x18003a75d  jz      loc_18003AB4B
0x18003a763  mov     edx, 55h ; 'U'
0x18003a768  mov     r9d, ebx
0x18003a76b  jmp     loc_18003AB3B
0x18003a770  mov     ecx, 40h ; '@'
0x18003a775  call    IpsecAllocMem
0x18003a77a  mov     rsi, rax
0x18003a77d  test    rax, rax
0x18003a780  jnz     short loc_18003A7B3
0x18003a782  lea     edi, [rax+0Eh]
0x18003a785  mov     ebx, edi
0x18003a787  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a78e  lea     rax, WPP_GLOBAL_Control
0x18003a795  cmp     rcx, rax
0x18003a798  jz      loc_18003AB4B
0x18003a79e  test    byte ptr [rcx+1Ch], 10h
0x18003a7a2  jz      loc_18003AB4B
0x18003a7a8  lea     edx, [rsi+56h]
0x18003a7ab  mov     r9d, edi
0x18003a7ae  jmp     loc_18003AB3B
0x18003a7b3  mov     rcx, rdi; unsigned __int16 *
0x18003a7b6  call    IpsecAllocStr
0x18003a7bb  mov     [rsi], rax
0x18003a7be  test    rax, rax
0x18003a7c1  jnz     short loc_18003A7F4
0x18003a7c3  lea     edi, [rax+0Eh]
0x18003a7c6  mov     ebx, edi
0x18003a7c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a7cf  lea     rax, WPP_GLOBAL_Control
0x18003a7d6  cmp     rcx, rax
0x18003a7d9  jz      loc_18003AB03
0x18003a7df  test    byte ptr [rcx+1Ch], 10h
0x18003a7e3  jz      loc_18003AB03
0x18003a7e9  lea     edx, [rdi+49h]
0x18003a7ec  mov     r9d, edi
0x18003a7ef  jmp     loc_18003AAF3
0x18003a7f4  mov     rcx, [rbp+hKey]; hKey
0x18003a7f8  lea     rax, [rbp+cbData]
0x18003a7fc  mov     r12d, 1
0x18003a802  mov     [rsp+50h+phkResult], rax; __int64
0x18003a807  mov     r8d, r12d
0x18003a80a  lea     r9, [rsi+8]
0x18003a80e  lea     rdx, aIpsecname; "ipsecName"
0x18003a815  call    RegstoreQueryValue
0x18003a81a  mov     rcx, [rbp+hKey]; hKey
0x18003a81e  lea     rax, [rbp+cbData]
0x18003a822  lea     r9, [rsi+10h]
0x18003a826  mov     [rsp+50h+phkResult], rax; __int64
0x18003a82b  mov     r8d, r12d
0x18003a82e  lea     rdx, aIpsecid; "ipsecID"
0x18003a835  call    RegstoreQueryValue
0x18003a83a  mov     ebx, eax
0x18003a83c  test    eax, eax
0x18003a83e  jz      short loc_18003A86B
0x18003a840  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a847  lea     rax, WPP_GLOBAL_Control
0x18003a84e  cmp     rcx, rax
0x18003a851  jz      loc_18003AB03
0x18003a857  test    byte ptr [rcx+1Ch], 10h
0x18003a85b  jz      loc_18003AB03
0x18003a861  lea     edx, [r12+57h]
0x18003a866  jmp     loc_18003AAF0
0x18003a86b  mov     rcx, [rbp+hKey]; hKey
0x18003a86f  lea     rax, [rbp+cbData]
0x18003a873  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18003a878  lea     r9, [rbp+Type]; lpType
0x18003a87c  lea     rax, [rbp+Data]
0x18003a880  mov     edi, 4
0x18003a885  xor     r8d, r8d; lpReserved
0x18003a888  mov     [rsp+50h+phkResult], rax; lpData
0x18003a88d  lea     rdx, aIpsecdatatype; "ipsecDataType"
0x18003a894  mov     [rbp+Type], edi
0x18003a897  mov     [rbp+cbData], edi
0x18003a89a  call    cs:__imp_RegQueryValueExW
0x18003a8a0  mov     ebx, eax
0x18003a8a2  test    eax, eax
0x18003a8a4  jz      short loc_18003A8CF
0x18003a8a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a8ad  lea     rax, WPP_GLOBAL_Control
0x18003a8b4  cmp     rcx, rax
0x18003a8b7  jz      loc_18003AB03
0x18003a8bd  test    byte ptr [rcx+1Ch], 10h
0x18003a8c1  jz      loc_18003AB03
0x18003a8c7  lea     edx, [rdi+55h]
0x18003a8ca  jmp     loc_18003AAF0
0x18003a8cf  mov     eax, dword ptr [rbp+Data]
0x18003a8d2  lea     r9, [rsi+20h]
0x18003a8d6  mov     [rsi+18h], eax
0x18003a8d9  lea     rdx, attr; "ipsecData"
0x18003a8e0  mov     rcx, [rbp+hKey]; hKey
0x18003a8e4  lea     rax, [rsi+28h]
0x18003a8e8  mov     r8d, 3
0x18003a8ee  mov     [rsp+50h+phkResult], rax; __int64
0x18003a8f3  call    RegstoreQueryValue
0x18003a8f8  mov     ebx, eax
0x18003a8fa  test    eax, eax
0x18003a8fc  jz      short loc_18003A929
0x18003a8fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a905  lea     rax, WPP_GLOBAL_Control
0x18003a90c  cmp     rcx, rax
0x18003a90f  jz      loc_18003AB03
0x18003a915  test    byte ptr [rcx+1Ch], 10h
0x18003a919  jz      loc_18003AB03
0x18003a91f  mov     edx, 5Ah ; 'Z'
0x18003a924  jmp     loc_18003AAF0
0x18003a929  mov     rcx, [rbp+hKey]; hKey
0x18003a92d  lea     rax, [rbp+cbData]
0x18003a931  lea     r9, [rbp+lpMem]
0x18003a935  mov     [rsp+50h+phkResult], rax; __int64
0x18003a93a  mov     r8d, 7
0x18003a940  lea     rdx, aIpsecownersref; "ipsecOwnersReference"
0x18003a947  call    RegstoreQueryValue
0x18003a94c  test    eax, eax
0x18003a94e  jnz     loc_18003AA9C
0x18003a954  mov     r14, [rbp+lpMem]
0x18003a958  mov     edi, r13d
0x18003a95b  mov     rax, r14
0x18003a95e  cmp     [r14], r13w
0x18003a962  jz      short loc_18003A982
0x18003a964  mov     rcx, r15
0x18003a967  inc     rcx
0x18003a96a  cmp     [rax+rcx*2], r13w
0x18003a96f  jnz     short loc_18003A967
0x18003a971  lea     rax, [rax+rcx*2]
0x18003a975  add     edi, r12d
0x18003a978  add     rax, 2
0x18003a97c  cmp     [rax], r13w
0x18003a980  jnz     short loc_18003A964
0x18003a982  mov     ecx, edi
0x18003a984  lea     r8, [rbp+var_8]
0x18003a988  mov     edx, 8
0x18003a98d  call    NsuSizeTMultiply
0x18003a992  mov     ebx, eax
0x18003a994  test    eax, eax
0x18003a996  jz      short loc_18003A9C3
0x18003a998  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a99f  lea     rax, WPP_GLOBAL_Control
0x18003a9a6  cmp     rcx, rax
0x18003a9a9  jz      loc_18003AB03
0x18003a9af  test    byte ptr [rcx+1Ch], 10h
0x18003a9b3  jz      loc_18003AB03
0x18003a9b9  mov     edx, 5Bh ; '['
0x18003a9be  jmp     loc_18003AAF0
0x18003a9c3  mov     rcx, [rbp+var_8]
0x18003a9c7  call    IpsecAllocMem
0x18003a9cc  mov     r12, rax
0x18003a9cf  test    rax, rax
0x18003a9d2  jnz     short loc_18003AA02
0x18003a9d4  lea     edi, [rax+0Eh]
0x18003a9d7  mov     ebx, edi
0x18003a9d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a9e0  lea     rax, WPP_GLOBAL_Control
0x18003a9e7  cmp     rcx, rax
0x18003a9ea  jz      loc_18003AB03
0x18003a9f0  test    byte ptr [rcx+1Ch], 10h
0x18003a9f4  jz      loc_18003AB03
0x18003a9fa  lea     edx, [rdi+4Eh]
0x18003a9fd  jmp     loc_18003A7EC
0x18003aa02  mov     rbx, r14
0x18003aa05  mov     r15d, r13d
0x18003aa08  cmp     r15d, edi
0x18003aa0b  jnb     short loc_18003AA83
0x18003aa0d  mov     rcx, rbx; unsigned __int16 *
0x18003aa10  call    IpsecAllocStr
0x18003aa15  test    rax, rax
0x18003aa18  jz      short loc_18003AA3C
0x18003aa1a  mov     ecx, r15d
0x18003aa1d  mov     [r12+rcx*8], rax
0x18003aa21  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003aa25  inc     rax
0x18003aa28  cmp     [rbx+rax*2], r13w
0x18003aa2d  jnz     short loc_18003AA25
0x18003aa2f  lea     rbx, [rbx+rax*2]
0x18003aa33  add     rbx, 2
0x18003aa37  inc     r15d
0x18003aa3a  jmp     short loc_18003AA08
0x18003aa3c  mov     [rsi+30h], r12
0x18003aa40  mov     edi, 0Eh
0x18003aa45  mov     [rsi+38h], r15d
0x18003aa49  mov     ebx, edi
0x18003aa4b  test    r14, r14
0x18003aa4e  jz      short loc_18003AA58
0x18003aa50  mov     rcx, r14; lpMem
0x18003aa53  call    IpsecFreeMem
0x18003aa58  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aa5f  lea     rax, WPP_GLOBAL_Control
0x18003aa66  cmp     rcx, rax
0x18003aa69  jz      loc_18003AB03
0x18003aa6f  test    byte ptr [rcx+1Ch], 10h
0x18003aa73  jz      loc_18003AB03
0x18003aa79  mov     edx, 5Dh ; ']'
0x18003aa7e  jmp     loc_18003A7EC
0x18003aa83  test    r14, r14
0x18003aa86  jz      short loc_18003AA90
0x18003aa88  mov     rcx, r14; lpMem
0x18003aa8b  call    IpsecFreeMem
0x18003aa90  mov     [rsi+38h], edi
0x18003aa93  mov     edi, 4
0x18003aa98  mov     [rsi+30h], r12
0x18003aa9c  mov     rcx, [rbp+hKey]; hKey
0x18003aaa0  lea     rax, [rbp+cbData]
0x18003aaa4  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18003aaa9  lea     r9, [rbp+Type]; lpType
0x18003aaad  lea     rax, [rbp+var_1C]
0x18003aab1  mov     [rbp+Type], edi
0x18003aab4  xor     r8d, r8d; lpReserved
0x18003aab7  mov     [rsp+50h+phkResult], rax; lpData
0x18003aabc  lea     rdx, aWhenchanged; "whenChanged"
0x18003aac3  mov     [rbp+cbData], edi
0x18003aac6  call    cs:__imp_RegQueryValueExW
0x18003aacc  mov     ebx, eax
0x18003aace  test    eax, eax
0x18003aad0  jz      short loc_18003AB0D
0x18003aad2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aad9  lea     rax, WPP_GLOBAL_Control
0x18003aae0  cmp     rcx, rax
0x18003aae3  jz      short loc_18003AB03
0x18003aae5  test    byte ptr [rcx+1Ch], 10h
0x18003aae9  jz      short loc_18003AB03
0x18003aaeb  mov     edx, 5Eh ; '^'
0x18003aaf0  mov     r9d, ebx
0x18003aaf3  mov     rcx, [rcx+10h]
0x18003aaf7  lea     r8, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids
0x18003aafe  call    WPP_SF_d
0x18003ab03  mov     rcx, rsi; lpMem
0x18003ab06  call    FreeIpsecISAKMPObject
0x18003ab0b  jmp     short loc_18003AB4B
0x18003ab0d  mov     eax, dword ptr [rbp+var_1C]
0x18003ab10  mov     [rsi+3Ch], eax
0x18003ab13  jmp     short loc_18003AB4E
0x18003ab15  mov     r9d, 0Dh
0x18003ab1b  mov     ebx, r9d
0x18003ab1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ab25  lea     rax, WPP_GLOBAL_Control
0x18003ab2c  cmp     rcx, rax
  ... truncated ...
```
