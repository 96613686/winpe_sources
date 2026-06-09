# AutodialAddressToNetwork

- ea: `0x1800661c4`
- end: `0x1800664d1`
- name: `AutodialAddressToNetwork`
- size: `781`
- prototype: `__int64 __fastcall(HKEY hKey, __int64, BYTE **)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000f7b0`
- `0x18006b110`
- `0x180077fd0`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x1800661c4`
- `0x18006a074`
- `0x18007e5f0`
- `0x1800ded06`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066303`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066303`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006645c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006645c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180066360`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180066419`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180066360`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180066419`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800663a9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800663a9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180066465`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180066477`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180066465`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180066477`

## pseudocode

```c
__int64 __fastcall AutodialAddressToNetwork(HKEY hKey, __int64 a2, BYTE **a3)
{
  WCHAR *v6; // r14
  _QWORD *v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rdx
  BYTE *v10; // rsi
  unsigned int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  BYTE *v14; // rax
  __int64 v15; // r9
  HKEY hKeya; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 672, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, a2);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 673, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
  }
  hKeya = 0;
  Type = 0;
  cbData = 0;
  v6 = (WCHAR *)FormatKey(L"Addresses", a2);
  if ( !v6 )
  {
    v7 = WPP_GLOBAL_Control;
    v8 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 674, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 8);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x800) != 0 && *((_BYTE *)v7 + 25) >= 6u )
      {
        v9 = 675;
LABEL_48:
        WPP_SF_d(v7[2], v9, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v8);
        return v8;
      }
    }
    return v8;
  }
  v10 = 0;
  v11 = RegOpenKeyExW(hKey, v6, 0, 1u, &hKeya);
  v8 = v11;
  if ( v11 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 676;
LABEL_39:
      v15 = v11;
      goto LABEL_40;
    }
  }
  else
  {
    v11 = RegQueryValueExW(hKeya, L"Network", 0, &Type, 0, &cbData);
    v8 = v11;
    if ( v11 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 677;
        goto LABEL_39;
      }
    }
    else
    {
      v14 = (BYTE *)GlobalAlloc(0x40u, cbData + 2LL);
      v10 = v14;
      if ( v14 )
      {
        memset_0(v14, 0, cbData + 2LL);
        v11 = RegQueryValueExW(hKeya, L"Network", 0, &Type, v10, &cbData);
        v8 = v11;
        if ( v11 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v13 = 679;
            goto LABEL_39;
          }
        }
      }
      else
      {
        v8 = 8;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = 678;
          v15 = 8;
LABEL_40:
          WPP_SF_d(v12[2], v13, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v15);
        }
      }
    }
  }
  RegCloseKey(hKeya);
  GlobalFree(v6);
  if ( v8 && v10 )
  {
    GlobalFree(v10);
    v10 = 0;
  }
  *a3 = v10;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v9 = 680;
    goto LABEL_48;
  }
  return v8;
}

```

## disassembly

```asm
0x1800661c4  mov     [rsp-28h+arg_0], rbx
0x1800661c9  mov     [rsp-28h+arg_10], rsi
0x1800661ce  push    rbp
0x1800661cf  push    rdi
0x1800661d0  push    r12
0x1800661d2  push    r14
0x1800661d4  push    r15
0x1800661d6  mov     rbp, rsp
0x1800661d9  sub     rsp, 40h
0x1800661dd  mov     r12, r8
0x1800661e0  mov     rbx, rdx
0x1800661e3  mov     r15, rcx
0x1800661e6  mov     esi, 800h
0x1800661eb  test    rdx, rdx
0x1800661ee  jz      short loc_180066228
0x1800661f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800661f7  lea     rdi, WPP_GLOBAL_Control
0x1800661fe  cmp     rcx, rdi
0x180066201  jz      short loc_18006625B
0x180066203  test    [rcx+1Ch], esi
0x180066206  jz      short loc_18006625B
0x180066208  cmp     byte ptr [rcx+19h], 6
0x18006620c  jb      short loc_18006625B
0x18006620e  mov     rcx, [rcx+10h]
0x180066212  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180066219  mov     edx, 2A0h
0x18006621e  mov     r9, rbx
0x180066221  call    WPP_SF_S
0x180066226  jmp     short loc_18006625B
0x180066228  mov     rcx, cs:WPP_GLOBAL_Control
0x18006622f  lea     rdi, WPP_GLOBAL_Control
0x180066236  cmp     rcx, rdi
0x180066239  jz      short loc_18006625B
0x18006623b  test    [rcx+1Ch], esi
0x18006623e  jz      short loc_18006625B
0x180066240  cmp     byte ptr [rcx+19h], 6
0x180066244  jb      short loc_18006625B
0x180066246  mov     rcx, [rcx+10h]
0x18006624a  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180066251  mov     edx, 2A1h
0x180066256  call    WPP_SF_
0x18006625b  mov     rdx, rbx
0x18006625e  mov     [rbp+hKey], 0
0x180066266  lea     rcx, aAddresses; "Addresses"
0x18006626d  mov     [rbp+Type], 0
0x180066274  mov     [rbp+cbData], 0
0x18006627b  call    FormatKey
0x180066280  mov     r14, rax
0x180066283  test    rax, rax
0x180066286  jnz     short loc_1800662EB
0x180066288  mov     rcx, cs:WPP_GLOBAL_Control
0x18006628f  lea     ebx, [rax+8]
0x180066292  cmp     rcx, rdi
0x180066295  jz      loc_1800664B6
0x18006629b  test    [rcx+1Ch], esi
0x18006629e  jz      short loc_1800662C5
0x1800662a0  cmp     byte ptr [rcx+19h], 2
0x1800662a4  jb      short loc_1800662C5
0x1800662a6  mov     rcx, [rcx+10h]
0x1800662aa  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x1800662b1  mov     edx, 2A2h
0x1800662b6  mov     r9d, ebx
0x1800662b9  call    WPP_SF_d
0x1800662be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800662c5  cmp     rcx, rdi
0x1800662c8  jz      loc_1800664B6
0x1800662ce  test    [rcx+1Ch], esi
0x1800662d1  jz      loc_1800664B6
0x1800662d7  cmp     byte ptr [rcx+19h], 6
0x1800662db  jb      loc_1800664B6
0x1800662e1  mov     edx, 2A3h
0x1800662e6  jmp     loc_1800664A3
0x1800662eb  lea     rax, [rbp+hKey]
0x1800662ef  xor     esi, esi
0x1800662f1  xor     r8d, r8d; ulOptions
0x1800662f4  mov     [rsp+40h+phkResult], rax; phkResult
0x1800662f9  mov     rdx, r14; lpSubKey
0x1800662fc  mov     rcx, r15; hKey
0x1800662ff  lea     r9d, [rsi+1]; samDesired
0x180066303  call    cs:__imp_RegOpenKeyExW
0x180066309  mov     ebx, eax
0x18006630b  test    eax, eax
0x18006630d  jz      short loc_180066340
0x18006630f  mov     rcx, cs:WPP_GLOBAL_Control
0x180066316  cmp     rcx, rdi
0x180066319  jz      loc_180066458
0x18006631f  test    dword ptr [rcx+1Ch], 800h
0x180066326  jz      loc_180066458
0x18006632c  cmp     byte ptr [rcx+19h], 2
0x180066330  jb      loc_180066458
0x180066336  mov     edx, 2A4h
0x18006633b  jmp     loc_180066445
0x180066340  mov     rcx, [rbp+hKey]; hKey
0x180066344  lea     rax, [rbp+cbData]
0x180066348  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18006634d  lea     r9, [rbp+Type]; lpType
0x180066351  xor     r8d, r8d; lpReserved
0x180066354  mov     [rsp+40h+phkResult], rsi; lpData
0x180066359  lea     rdx, aNetwork; "Network"
0x180066360  call    cs:__imp_RegQueryValueExW
0x180066366  mov     ebx, eax
0x180066368  test    eax, eax
0x18006636a  jz      short loc_18006639D
0x18006636c  mov     rcx, cs:WPP_GLOBAL_Control
0x180066373  cmp     rcx, rdi
0x180066376  jz      loc_180066458
0x18006637c  test    dword ptr [rcx+1Ch], 800h
0x180066383  jz      loc_180066458
0x180066389  cmp     byte ptr [rcx+19h], 2
0x18006638d  jb      loc_180066458
0x180066393  mov     edx, 2A5h
0x180066398  jmp     loc_180066445
0x18006639d  mov     edx, [rbp+cbData]
0x1800663a0  mov     ecx, 40h ; '@'; uFlags
0x1800663a5  add     rdx, 2; dwBytes
0x1800663a9  call    cs:__imp_GlobalAlloc
0x1800663af  mov     rsi, rax
0x1800663b2  test    rax, rax
0x1800663b5  jnz     short loc_1800663E7
0x1800663b7  lea     ebx, [rax+8]
0x1800663ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800663c1  cmp     rcx, rdi
0x1800663c4  jz      loc_180066458
0x1800663ca  test    dword ptr [rcx+1Ch], 800h
0x1800663d1  jz      loc_180066458
0x1800663d7  cmp     byte ptr [rcx+19h], 2
0x1800663db  jb      short loc_180066458
0x1800663dd  mov     edx, 2A6h
0x1800663e2  mov     r9d, ebx
0x1800663e5  jmp     short loc_180066448
0x1800663e7  mov     r8d, [rbp+cbData]
0x1800663eb  xor     edx, edx; Val
0x1800663ed  add     r8, 2; Size
0x1800663f1  mov     rcx, rsi; void *
0x1800663f4  call    memset_0
0x1800663f9  mov     rcx, [rbp+hKey]; hKey
0x1800663fd  lea     rax, [rbp+cbData]
0x180066401  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180066406  lea     r9, [rbp+Type]; lpType
0x18006640a  xor     r8d, r8d; lpReserved
0x18006640d  mov     [rsp+40h+phkResult], rsi; lpData
0x180066412  lea     rdx, aNetwork; "Network"
0x180066419  call    cs:__imp_RegQueryValueExW
0x18006641f  mov     ebx, eax
0x180066421  test    eax, eax
0x180066423  jz      short loc_180066458
0x180066425  mov     rcx, cs:WPP_GLOBAL_Control
0x18006642c  cmp     rcx, rdi
0x18006642f  jz      short loc_180066458
0x180066431  test    dword ptr [rcx+1Ch], 800h
0x180066438  jz      short loc_180066458
0x18006643a  cmp     byte ptr [rcx+19h], 2
0x18006643e  jb      short loc_180066458
0x180066440  mov     edx, 2A7h
0x180066445  mov     r9d, eax
0x180066448  mov     rcx, [rcx+10h]
0x18006644c  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180066453  call    WPP_SF_d
0x180066458  mov     rcx, [rbp+hKey]; hKey
0x18006645c  call    cs:__imp_RegCloseKey
0x180066462  mov     rcx, r14; hMem
0x180066465  call    cs:__imp_GlobalFree
0x18006646b  test    ebx, ebx
0x18006646d  jz      short loc_18006647F
0x18006646f  test    rsi, rsi
0x180066472  jz      short loc_18006647F
0x180066474  mov     rcx, rsi; hMem
0x180066477  call    cs:__imp_GlobalFree
0x18006647d  xor     esi, esi
0x18006647f  mov     [r12], rsi
0x180066483  mov     rcx, cs:WPP_GLOBAL_Control
0x18006648a  cmp     rcx, rdi
0x18006648d  jz      short loc_1800664B6
0x18006648f  test    dword ptr [rcx+1Ch], 800h
0x180066496  jz      short loc_1800664B6
0x180066498  cmp     byte ptr [rcx+19h], 6
0x18006649c  jb      short loc_1800664B6
0x18006649e  mov     edx, 2A8h
0x1800664a3  mov     rcx, [rcx+10h]
0x1800664a7  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x1800664ae  mov     r9d, ebx
0x1800664b1  call    WPP_SF_d
0x1800664b6  lea     r11, [rsp+40h+var_s0]
0x1800664bb  mov     eax, ebx
0x1800664bd  mov     rbx, [r11+30h]
0x1800664c1  mov     rsi, [r11+40h]
0x1800664c5  mov     rsp, r11
0x1800664c8  pop     r15
0x1800664ca  pop     r14
0x1800664cc  pop     r12
0x1800664ce  pop     rdi
0x1800664cf  pop     rbp
0x1800664d0  retn
```
