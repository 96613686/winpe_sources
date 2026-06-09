# GetL2tpConfigParams

- ea: `0x180030060`
- end: `0x1800302c7`
- name: `GetL2tpConfigParams`
- size: `615`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002175c`

## callees

- `0x180028950`
- `0x180028980`
- `0x18002ee38`
- `0x180030060`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030241`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030241`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030219`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030219`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030147`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003018f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030287`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030147`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003018f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030287`

## pseudocode

```c
__int64 __fastcall GetL2tpConfigParams(HKEY hKey, char a2, __int64 a3, unsigned int a4)
{
  unsigned int v6; // ebx
  bool v8; // cf
  unsigned int i; // edi
  LSTATUS v10; // eax
  __int128 v11; // xmm0
  __int64 v12; // xmm1_8
  __int64 v13; // xmm1_8
  void *v14; // rdi
  HKEY v15; // rcx
  LSTATUS v16; // eax
  void *v17; // rax
  BYTE *lpData; // rsi
  DWORD Type; // [rsp+30h] [rbp-29h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-21h] BYREF
  __int128 v22; // [rsp+40h] [rbp-19h] BYREF
  __int64 v23; // [rsp+50h] [rbp-9h]
  LPCWSTR lpValueName; // [rsp+58h] [rbp-1h]
  LPBYTE v25[6]; // [rsp+60h] [rbp+7h]
  DWORD cbData; // [rsp+C8h] [rbp+6Fh] BYREF

  lpValueName = L"idleTimeout";
  v6 = 0;
  v25[0] = (LPBYTE)&v22;
  v25[1] = (LPBYTE)L"saLifeTime";
  v25[2] = (LPBYTE)&v22 + 8;
  v25[3] = (LPBYTE)L"saDataSize";
  v25[4] = (LPBYTE)&v22 + 12;
  v23 = 0;
  v22 = 0;
  if ( a2 != 1 && a2 != 2 )
  {
    if ( a2 == 3 || a2 == 4 )
    {
      v8 = a4 < 0x18;
    }
    else
    {
      if ( a2 != 5 )
        return 50;
      v8 = a4 < 0x20;
    }
    if ( v8 )
      return 87;
    for ( i = 0; i < 3; ++i )
    {
      cbData = 4;
      Type = 4;
      v6 = RegQueryValueExW(hKey, (LPCWSTR)v25[2 * i - 1], 0, &Type, v25[2 * i], &cbData);
      if ( v6 )
        return v6;
    }
    if ( a2 >= 5
      && (cbData = 4,
          Type = 4,
          v10 = RegQueryValueExW(hKey, L"mmSaLifeTime", 0, &Type, (LPBYTE)(a3 + 24), &cbData),
          (v6 = v10) != 0) )
    {
      if ( v10 != 2 )
        return v6;
      v11 = v22;
      *(_DWORD *)(a3 + 24) = 28800;
      v12 = v23;
      *(_OWORD *)a3 = v11;
      *(_QWORD *)(a3 + 16) = v12;
    }
    else
    {
      v13 = v23;
      *(_OWORD *)a3 = v22;
      *(_QWORD *)(a3 + 16) = v13;
      if ( a2 < 3 )
        return v6;
    }
    v14 = (void *)RtrCfgAlloc(24);
    if ( !v14 )
      return 8;
    v15 = 0;
    phkResult = 0;
    if ( hKey )
    {
      v16 = RegOpenKeyExW(hKey, L"L2TPCustomPolicy", 0, 0x20019u, &phkResult);
      v15 = phkResult;
      v6 = v16;
      if ( !v16 )
      {
        GetCustomPolicyRegParams(phkResult, v14);
        v15 = phkResult;
      }
    }
    else
    {
      v6 = 87;
    }
    if ( v15 )
      RegCloseKey(v15);
    if ( v6 )
    {
      if ( v6 != 2 )
      {
LABEL_34:
        MprCommonFree(v14);
        return v6;
      }
      v17 = 0;
    }
    else
    {
      v17 = v14;
      v14 = 0;
    }
    *(_QWORD *)(a3 + 16) = v17;
    cbData = 4;
    lpData = (BYTE *)(a3 + 4);
    Type = 4;
    v6 = RegQueryValueExW(hKey, L"EncryptionType", 0, &Type, lpData, &cbData);
    if ( v6 == 2 )
    {
      v6 = 0;
      *(_DWORD *)lpData = 1;
    }
    if ( v14 )
      goto LABEL_34;
  }
  return v6;
}

```

## disassembly

```asm
0x180030060  mov     [rsp-8+arg_0], rbx
0x180030065  mov     [rsp-8+arg_10], rsi
0x18003006a  push    rbp
0x18003006b  push    rdi
0x18003006c  push    r12
0x18003006e  push    r14
0x180030070  push    r15
0x180030072  lea     rbp, [rsp-37h]
0x180030077  sub     rsp, 90h
0x18003007e  lea     rax, aIdletimeout; "idleTimeout"
0x180030085  movsx   r15d, dl
0x180030089  mov     [rbp+57h+lpValueName], rax
0x18003008d  mov     r14, rcx
0x180030090  lea     rax, [rbp+57h+var_70]
0x180030094  xor     ebx, ebx
0x180030096  mov     [rbp+57h+var_50], rax
0x18003009a  mov     ecx, r15d
0x18003009d  lea     rax, aSalifetime; "saLifeTime"
0x1800300a4  xorps   xmm0, xmm0
0x1800300a7  mov     [rbp+57h+var_48], rax
0x1800300ab  mov     rsi, r8
0x1800300ae  lea     rax, [rbp+57h+var_70+8]
0x1800300b2  mov     [rbp+57h+var_40], rax
0x1800300b6  lea     rax, aSadatasize; "saDataSize"
0x1800300bd  mov     [rbp+57h+var_38], rax
0x1800300c1  lea     rax, [rbp+57h+var_70+0Ch]
0x1800300c5  mov     [rbp+57h+var_30], rax
0x1800300c9  xor     eax, eax
0x1800300cb  mov     [rbp+57h+var_60], rax
0x1800300cf  movups  [rbp+57h+var_70], xmm0
0x1800300d3  sub     ecx, 1
0x1800300d6  jz      loc_1800302A9
0x1800300dc  sub     ecx, 1
0x1800300df  jz      loc_1800302A9
0x1800300e5  sub     ecx, 1
0x1800300e8  jz      short loc_18003010C
0x1800300ea  sub     ecx, 1
0x1800300ed  jz      short loc_18003010C
0x1800300ef  cmp     ecx, 1
0x1800300f2  jz      short loc_1800300FC
0x1800300f4  lea     ebx, [rax+32h]
0x1800300f7  jmp     loc_1800302A9
0x1800300fc  cmp     r9d, 20h ; ' '
0x180030100  jnb     short loc_180030112
0x180030102  mov     ebx, 57h ; 'W'
0x180030107  jmp     loc_1800302A9
0x18003010c  cmp     r9d, 18h
0x180030110  jmp     short loc_180030100
0x180030112  xor     edi, edi
0x180030114  lea     r12d, [rdi+4]
0x180030118  lea     rax, [rbp+57h+cbData]
0x18003011c  mov     edx, edi
0x18003011e  add     rdx, rdx
0x180030121  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x180030126  lea     r9, [rbp+57h+Type]; lpType
0x18003012a  mov     [rbp+57h+cbData], r12d
0x18003012e  xor     r8d, r8d; lpReserved
0x180030131  mov     [rbp+57h+Type], r12d
0x180030135  mov     rcx, r14; hKey
0x180030138  mov     rax, [rbp+rdx*8+57h+var_50]
0x18003013d  mov     rdx, [rbp+rdx*8+57h+lpValueName]; lpValueName
0x180030142  mov     [rsp+0B0h+lpData], rax; lpData
0x180030147  call    cs:__imp_RegQueryValueExW
0x18003014d  mov     ebx, eax
0x18003014f  test    eax, eax
0x180030151  jnz     loc_1800302A9
0x180030157  inc     edi
0x180030159  cmp     edi, 3
0x18003015c  jb      short loc_180030118
0x18003015e  cmp     r15b, 5
0x180030162  jl      short loc_1800301BD
0x180030164  lea     rax, [rbp+57h+cbData]
0x180030168  mov     [rbp+57h+cbData], r12d
0x18003016c  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x180030171  lea     rdi, [rsi+18h]
0x180030175  lea     r9, [rbp+57h+Type]; lpType
0x180030179  mov     [rsp+0B0h+lpData], rdi; lpData
0x18003017e  xor     r8d, r8d; lpReserved
0x180030181  mov     [rbp+57h+Type], r12d
0x180030185  lea     rdx, aMmsalifetime; "mmSaLifeTime"
0x18003018c  mov     rcx, r14; hKey
0x18003018f  call    cs:__imp_RegQueryValueExW
0x180030195  mov     ebx, eax
0x180030197  test    eax, eax
0x180030199  jz      short loc_1800301BD
0x18003019b  cmp     eax, 2
0x18003019e  jnz     loc_1800302A9
0x1800301a4  movups  xmm0, [rbp+57h+var_70]
0x1800301a8  mov     dword ptr [rdi], 7080h
0x1800301ae  movsd   xmm1, [rbp+57h+var_60]
0x1800301b3  movups  xmmword ptr [rsi], xmm0
0x1800301b6  movsd   qword ptr [rsi+10h], xmm1
0x1800301bb  jmp     short loc_1800301D8
0x1800301bd  movsd   xmm1, [rbp+57h+var_60]
0x1800301c2  movups  xmm0, [rbp+57h+var_70]
0x1800301c6  movups  xmmword ptr [rsi], xmm0
0x1800301c9  movsd   qword ptr [rsi+10h], xmm1
0x1800301ce  cmp     r15b, 3
0x1800301d2  jl      loc_1800302A9
0x1800301d8  mov     ecx, 18h
0x1800301dd  call    RtrCfgAlloc
0x1800301e2  mov     rdi, rax
0x1800301e5  test    rax, rax
0x1800301e8  jnz     short loc_1800301F2
0x1800301ea  lea     ebx, [rax+8]
0x1800301ed  jmp     loc_1800302A9
0x1800301f2  xor     ecx, ecx; hKey
0x1800301f4  mov     [rbp+57h+phkResult], rcx
0x1800301f8  test    r14, r14
0x1800301fb  jz      short loc_180030237
0x1800301fd  lea     rax, [rbp+57h+phkResult]
0x180030201  mov     r9d, 20019h; samDesired
0x180030207  xor     r8d, r8d; ulOptions
0x18003020a  mov     [rsp+0B0h+lpData], rax; phkResult
0x18003020f  lea     rdx, aL2tpcustompoli; "L2TPCustomPolicy"
0x180030216  mov     rcx, r14; hKey
0x180030219  call    cs:__imp_RegOpenKeyExW
0x18003021f  mov     rcx, [rbp+57h+phkResult]
0x180030223  mov     ebx, eax
0x180030225  test    eax, eax
0x180030227  jnz     short loc_18003023C
0x180030229  mov     rdx, rdi
0x18003022c  call    GetCustomPolicyRegParams
0x180030231  mov     rcx, [rbp+57h+phkResult]
0x180030235  jmp     short loc_18003023C
0x180030237  mov     ebx, 57h ; 'W'
0x18003023c  test    rcx, rcx
0x18003023f  jz      short loc_180030247
0x180030241  call    cs:__imp_RegCloseKey
0x180030247  test    ebx, ebx
0x180030249  jz      short loc_180030254
0x18003024b  cmp     ebx, 2
0x18003024e  jnz     short loc_1800302A1
0x180030250  xor     eax, eax
0x180030252  jmp     short loc_180030259
0x180030254  mov     rax, rdi
0x180030257  xor     edi, edi
0x180030259  mov     [rsi+10h], rax
0x18003025d  lea     r9, [rbp+57h+Type]; lpType
0x180030261  lea     rax, [rbp+57h+cbData]
0x180030265  mov     [rbp+57h+cbData], r12d
0x180030269  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x18003026e  lea     rdx, aEncryptiontype; "EncryptionType"
0x180030275  add     rsi, r12
0x180030278  mov     [rbp+57h+Type], r12d
0x18003027c  xor     r8d, r8d; lpReserved
0x18003027f  mov     [rsp+0B0h+lpData], rsi; lpData
0x180030284  mov     rcx, r14; hKey
0x180030287  call    cs:__imp_RegQueryValueExW
0x18003028d  mov     ebx, eax
0x18003028f  cmp     eax, 2
0x180030292  jnz     short loc_18003029C
0x180030294  xor     ebx, ebx
0x180030296  mov     dword ptr [rsi], 1
0x18003029c  test    rdi, rdi
0x18003029f  jz      short loc_1800302A9
0x1800302a1  mov     rcx, rdi; lpMem
0x1800302a4  call    MprCommonFree
0x1800302a9  lea     r11, [rsp+0B0h+var_20]
0x1800302b1  mov     eax, ebx
0x1800302b3  mov     rbx, [r11+30h]
0x1800302b7  mov     rsi, [r11+40h]
0x1800302bb  mov     rsp, r11
0x1800302be  pop     r15
0x1800302c0  pop     r14
0x1800302c2  pop     r12
0x1800302c4  pop     rdi
0x1800302c5  pop     rbp
0x1800302c6  retn
```
