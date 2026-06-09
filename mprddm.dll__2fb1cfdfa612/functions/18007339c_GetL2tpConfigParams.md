# GetL2tpConfigParams

- ea: `0x18007339c`
- end: `0x180073603`
- name: `GetL2tpConfigParams`
- size: `615`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004950`
- `0x18007eb50`

## callees

- `0x1800729dc`
- `0x18007339c`
- `0x18007360c`
- `0x180073634`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180073555`
- `ADVAPI32!RegOpenKeyExW` at `0x180073555`
- `ADVAPI32!RegQueryValueExW` at `0x180073483`
- `ADVAPI32!RegQueryValueExW` at `0x1800734cb`
- `ADVAPI32!RegQueryValueExW` at `0x1800735c3`
- `ADVAPI32!RegQueryValueExW` at `0x180073483`
- `ADVAPI32!RegQueryValueExW` at `0x1800734cb`
- `ADVAPI32!RegQueryValueExW` at `0x1800735c3`
- `ADVAPI32!RegCloseKey` at `0x18007357d`
- `ADVAPI32!RegCloseKey` at `0x18007357d`

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
    v14 = (void *)MprCommonAlloc(24);
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
0x18007339c  mov     [rsp-8+arg_0], rbx
0x1800733a1  mov     [rsp-8+arg_10], rsi
0x1800733a6  push    rbp
0x1800733a7  push    rdi
0x1800733a8  push    r12
0x1800733aa  push    r14
0x1800733ac  push    r15
0x1800733ae  lea     rbp, [rsp-37h]
0x1800733b3  sub     rsp, 90h
0x1800733ba  lea     rax, aIdletimeout; "idleTimeout"
0x1800733c1  movsx   r15d, dl
0x1800733c5  mov     [rbp+57h+lpValueName], rax
0x1800733c9  mov     r14, rcx
0x1800733cc  lea     rax, [rbp+57h+var_70]
0x1800733d0  xor     ebx, ebx
0x1800733d2  mov     [rbp+57h+var_50], rax
0x1800733d6  mov     ecx, r15d
0x1800733d9  lea     rax, aSalifetime; "saLifeTime"
0x1800733e0  xorps   xmm0, xmm0
0x1800733e3  mov     [rbp+57h+var_48], rax
0x1800733e7  mov     rsi, r8
0x1800733ea  lea     rax, [rbp+57h+var_70+8]
0x1800733ee  mov     [rbp+57h+var_40], rax
0x1800733f2  lea     rax, aSadatasize; "saDataSize"
0x1800733f9  mov     [rbp+57h+var_38], rax
0x1800733fd  lea     rax, [rbp+57h+var_70+0Ch]
0x180073401  mov     [rbp+57h+var_30], rax
0x180073405  xor     eax, eax
0x180073407  mov     [rbp+57h+var_60], rax
0x18007340b  movups  [rbp+57h+var_70], xmm0
0x18007340f  sub     ecx, 1
0x180073412  jz      loc_1800735E5
0x180073418  sub     ecx, 1
0x18007341b  jz      loc_1800735E5
0x180073421  sub     ecx, 1
0x180073424  jz      short loc_180073448
0x180073426  sub     ecx, 1
0x180073429  jz      short loc_180073448
0x18007342b  cmp     ecx, 1
0x18007342e  jz      short loc_180073438
0x180073430  lea     ebx, [rax+32h]
0x180073433  jmp     loc_1800735E5
0x180073438  cmp     r9d, 20h ; ' '
0x18007343c  jnb     short loc_18007344E
0x18007343e  mov     ebx, 57h ; 'W'
0x180073443  jmp     loc_1800735E5
0x180073448  cmp     r9d, 18h
0x18007344c  jmp     short loc_18007343C
0x18007344e  xor     edi, edi
0x180073450  lea     r12d, [rdi+4]
0x180073454  lea     rax, [rbp+57h+cbData]
0x180073458  mov     edx, edi
0x18007345a  add     rdx, rdx
0x18007345d  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x180073462  lea     r9, [rbp+57h+Type]; lpType
0x180073466  mov     [rbp+57h+cbData], r12d
0x18007346a  xor     r8d, r8d; lpReserved
0x18007346d  mov     [rbp+57h+Type], r12d
0x180073471  mov     rcx, r14; hKey
0x180073474  mov     rax, [rbp+rdx*8+57h+var_50]
0x180073479  mov     rdx, [rbp+rdx*8+57h+lpValueName]; lpValueName
0x18007347e  mov     [rsp+0B0h+lpData], rax; lpData
0x180073483  call    cs:__imp_RegQueryValueExW
0x180073489  mov     ebx, eax
0x18007348b  test    eax, eax
0x18007348d  jnz     loc_1800735E5
0x180073493  inc     edi
0x180073495  cmp     edi, 3
0x180073498  jb      short loc_180073454
0x18007349a  cmp     r15b, 5
0x18007349e  jl      short loc_1800734F9
0x1800734a0  lea     rax, [rbp+57h+cbData]
0x1800734a4  mov     [rbp+57h+cbData], r12d
0x1800734a8  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x1800734ad  lea     rdi, [rsi+18h]
0x1800734b1  lea     r9, [rbp+57h+Type]; lpType
0x1800734b5  mov     [rsp+0B0h+lpData], rdi; lpData
0x1800734ba  xor     r8d, r8d; lpReserved
0x1800734bd  mov     [rbp+57h+Type], r12d
0x1800734c1  lea     rdx, aMmsalifetime; "mmSaLifeTime"
0x1800734c8  mov     rcx, r14; hKey
0x1800734cb  call    cs:__imp_RegQueryValueExW
0x1800734d1  mov     ebx, eax
0x1800734d3  test    eax, eax
0x1800734d5  jz      short loc_1800734F9
0x1800734d7  cmp     eax, 2
0x1800734da  jnz     loc_1800735E5
0x1800734e0  movups  xmm0, [rbp+57h+var_70]
0x1800734e4  mov     dword ptr [rdi], 7080h
0x1800734ea  movsd   xmm1, [rbp+57h+var_60]
0x1800734ef  movups  xmmword ptr [rsi], xmm0
0x1800734f2  movsd   qword ptr [rsi+10h], xmm1
0x1800734f7  jmp     short loc_180073514
0x1800734f9  movsd   xmm1, [rbp+57h+var_60]
0x1800734fe  movups  xmm0, [rbp+57h+var_70]
0x180073502  movups  xmmword ptr [rsi], xmm0
0x180073505  movsd   qword ptr [rsi+10h], xmm1
0x18007350a  cmp     r15b, 3
0x18007350e  jl      loc_1800735E5
0x180073514  mov     ecx, 18h
0x180073519  call    MprCommonAlloc
0x18007351e  mov     rdi, rax
0x180073521  test    rax, rax
0x180073524  jnz     short loc_18007352E
0x180073526  lea     ebx, [rax+8]
0x180073529  jmp     loc_1800735E5
0x18007352e  xor     ecx, ecx; hKey
0x180073530  mov     [rbp+57h+phkResult], rcx
0x180073534  test    r14, r14
0x180073537  jz      short loc_180073573
0x180073539  lea     rax, [rbp+57h+phkResult]
0x18007353d  mov     r9d, 20019h; samDesired
0x180073543  xor     r8d, r8d; ulOptions
0x180073546  mov     [rsp+0B0h+lpData], rax; phkResult
0x18007354b  lea     rdx, aL2tpcustompoli; "L2TPCustomPolicy"
0x180073552  mov     rcx, r14; hKey
0x180073555  call    cs:__imp_RegOpenKeyExW
0x18007355b  mov     rcx, [rbp+57h+phkResult]
0x18007355f  mov     ebx, eax
0x180073561  test    eax, eax
0x180073563  jnz     short loc_180073578
0x180073565  mov     rdx, rdi
0x180073568  call    GetCustomPolicyRegParams
0x18007356d  mov     rcx, [rbp+57h+phkResult]
0x180073571  jmp     short loc_180073578
0x180073573  mov     ebx, 57h ; 'W'
0x180073578  test    rcx, rcx
0x18007357b  jz      short loc_180073583
0x18007357d  call    cs:__imp_RegCloseKey
0x180073583  test    ebx, ebx
0x180073585  jz      short loc_180073590
0x180073587  cmp     ebx, 2
0x18007358a  jnz     short loc_1800735DD
0x18007358c  xor     eax, eax
0x18007358e  jmp     short loc_180073595
0x180073590  mov     rax, rdi
0x180073593  xor     edi, edi
0x180073595  mov     [rsi+10h], rax
0x180073599  lea     r9, [rbp+57h+Type]; lpType
0x18007359d  lea     rax, [rbp+57h+cbData]
0x1800735a1  mov     [rbp+57h+cbData], r12d
0x1800735a5  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x1800735aa  lea     rdx, aEncryptiontype; "EncryptionType"
0x1800735b1  add     rsi, r12
0x1800735b4  mov     [rbp+57h+Type], r12d
0x1800735b8  xor     r8d, r8d; lpReserved
0x1800735bb  mov     [rsp+0B0h+lpData], rsi; lpData
0x1800735c0  mov     rcx, r14; hKey
0x1800735c3  call    cs:__imp_RegQueryValueExW
0x1800735c9  mov     ebx, eax
0x1800735cb  cmp     eax, 2
0x1800735ce  jnz     short loc_1800735D8
0x1800735d0  xor     ebx, ebx
0x1800735d2  mov     dword ptr [rsi], 1
0x1800735d8  test    rdi, rdi
0x1800735db  jz      short loc_1800735E5
0x1800735dd  mov     rcx, rdi; lpMem
0x1800735e0  call    MprCommonFree
0x1800735e5  lea     r11, [rsp+0B0h+var_20]
0x1800735ed  mov     eax, ebx
0x1800735ef  mov     rbx, [r11+30h]
0x1800735f3  mov     rsi, [r11+40h]
0x1800735f7  mov     rsp, r11
0x1800735fa  pop     r15
0x1800735fc  pop     r14
0x1800735fe  pop     r12
0x180073600  pop     rdi
0x180073601  pop     rbp
0x180073602  retn
```
