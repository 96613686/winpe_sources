# CopyRegistry

- ea: `0x1400038f8`
- end: `0x140003c1d`
- name: `CopyRegistry`
- size: `805`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400031f4`

## callees

- `0x140001340`
- `0x140001bb2`
- `0x140001cc6`
- `0x140002004`
- `0x1400022dc`
- `0x140002c20`
- `0x140002ce4`
- `0x140003068`
- `0x1400033d8`
- `0x1400038f8`
- `0x140003e34`
- `0x14000d694`
- `0x14000e560`
- `0x14000e75c`
- `0x14000e798`
- `0x14000eecc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003a85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003a85`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003adb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003adb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003af7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003b80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003b9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003af7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003b80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003b9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003a2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003bd5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003a2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003bd5`

## pseudocode

```c
__int64 __fastcall CopyRegistry(int a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  HKEY v7; // rcx
  __int64 v8; // rcx
  __int64 ResString2FromModule; // rax
  FILE *v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // edi
  int v14; // ebx
  FILE *v15; // rax
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v18; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v20[4]; // [rsp+70h] [rbp-90h] BYREF
  int v21; // [rsp+74h] [rbp-8Ch]
  HKEY hKey; // [rsp+78h] [rbp-88h]
  _BYTE v23[8]; // [rsp+88h] [rbp-78h] BYREF
  int v24; // [rsp+90h] [rbp-70h]
  LPCWSTR lpSubKey; // [rsp+C0h] [rbp-40h]
  PCNZWCH lpString1; // [rsp+C8h] [rbp-38h]
  int v27; // [rsp+FCh] [rbp-4h]
  _BYTE v28[4]; // [rsp+110h] [rbp+10h] BYREF
  int v29; // [rsp+114h] [rbp+14h]
  HKEY v30; // [rsp+118h] [rbp+18h]
  LPCWSTR v31; // [rsp+160h] [rbp+60h]
  PCNZWCH lpString2; // [rsp+168h] [rbp+68h]
  int v33; // [rsp+19Ch] [rbp+9Ch]

  phkResult = 0;
  v18 = 0;
  v17 = 0;
  v21 = 0;
  dwDisposition = 0;
  memset_0(v20, 0, 0x94u);
  v29 = 0;
  memset_0(v28, 0, 0x94u);
  if ( a1 && a2 )
  {
    InitGlobalData(3, v20);
    InitGlobalData(3, v28);
    v4 = ParseCopyCmdLine(a1, a2, (unsigned int)v20, (unsigned int)v28, (__int64)&v17);
    v5 = 1;
    if ( !v4 )
    {
LABEL_12:
      v10 = o___acrt_iob_func_0(2u);
LABEL_21:
      ShowLastErrorEx(v10);
      goto LABEL_22;
    }
    if ( v17 == 1 )
    {
      Usage(3);
      v5 = 0;
LABEL_22:
      FreeGlobalData(v20);
      FreeGlobalData(v28);
      return v5;
    }
    if ( !RegConnectMachine((__int64)v20) || !RegConnectMachine((__int64)v28) )
    {
      v6 = 0xFFFFFFFFLL;
LABEL_20:
      SaveErrorMessage(v6);
      v10 = o___acrt_iob_func_0(2u);
      goto LABEL_21;
    }
    v7 = hKey;
    if ( hKey == v30 )
    {
      if ( !(unsigned int)StringCompareW(lpString1, lpString2) )
      {
        SetLastError(0x800401E4);
        ResString2FromModule = GetResString2FromModule(v8, 131, 0);
        SetReason(ResString2FromModule);
        goto LABEL_12;
      }
      v7 = hKey;
    }
    v11 = RegOpenKeyExW(v7, lpSubKey, 0, v27 | 0x20019, &phkResult);
    if ( v11 )
    {
      v6 = v11;
      goto LABEL_20;
    }
    v12 = RegCreateKeyExW(v30, v31, 0, 0, 0, v33 | 0xF003F, 0, &v18, &dwDisposition);
    if ( v12 )
    {
      if ( phkResult )
      {
        RegCloseKey(phkResult);
        phkResult = 0;
      }
      v6 = v12;
      goto LABEL_20;
    }
    v14 = CopyEnumerateKey(phkResult, lpSubKey, v18, lpSubKey, (__int64)v23, v24, 0, v27);
    if ( v18 )
    {
      RegCloseKey(v18);
      v18 = 0;
    }
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      phkResult = 0;
    }
    FreeGlobalData(v20);
    FreeGlobalData(v28);
    return v14 != 0;
  }
  else
  {
    SetLastError(0x57u);
    v15 = o___acrt_iob_func_0(2u);
    ShowLastError(v15);
    return 1;
  }
}

```

## disassembly

```asm
0x1400038f8  mov     [rsp-8+arg_10], rbx
0x1400038fd  mov     [rsp-8+arg_18], rdi
0x140003902  push    rbp
0x140003903  lea     rbp, [rsp-0C0h]
0x14000390b  sub     rsp, 1C0h
0x140003912  mov     rax, cs:__security_cookie
0x140003919  xor     rax, rsp
0x14000391c  mov     [rbp+0C0h+var_10], rax
0x140003923  mov     rbx, rdx
0x140003926  mov     [rsp+1C0h+var_170], 0
0x14000392f  mov     edi, ecx
0x140003931  mov     [rsp+1C0h+var_160], 0
0x14000393a  xor     eax, eax
0x14000393c  mov     [rsp+1C0h+var_168], 0
0x140003944  xor     edx, edx; Val
0x140003946  mov     [rsp+1C0h+var_14C], eax
0x14000394a  lea     rcx, [rsp+1C0h+var_150]; void *
0x14000394f  mov     [rsp+1C0h+dwDisposition], 0
0x140003957  mov     r8d, 94h; Size
0x14000395d  call    memset_0
0x140003962  xor     eax, eax
0x140003964  lea     rcx, [rbp+0C0h+var_B0]; void *
0x140003968  xor     edx, edx; Val
0x14000396a  mov     [rbp+0C0h+var_AC], eax
0x14000396d  mov     r8d, 94h; Size
0x140003973  call    memset_0
0x140003978  test    edi, edi
0x14000397a  jz      loc_140003BD0
0x140003980  test    rbx, rbx
0x140003983  jz      loc_140003BD0
0x140003989  lea     rdx, [rsp+1C0h+var_150]
0x14000398e  mov     ecx, 3
0x140003993  call    InitGlobalData
0x140003998  lea     rdx, [rbp+0C0h+var_B0]
0x14000399c  mov     ecx, 3
0x1400039a1  call    InitGlobalData
0x1400039a6  lea     rax, [rsp+1C0h+var_168]
0x1400039ab  mov     rdx, rbx
0x1400039ae  lea     r9, [rbp+0C0h+var_B0]
0x1400039b2  mov     [rsp+1C0h+phkResult], rax
0x1400039b7  lea     r8, [rsp+1C0h+var_150]
0x1400039bc  mov     ecx, edi
0x1400039be  call    ParseCopyCmdLine
0x1400039c3  mov     ebx, 1
0x1400039c8  test    eax, eax
0x1400039ca  jz      loc_140003A50
0x1400039d0  cmp     [rsp+1C0h+var_168], ebx
0x1400039d4  jnz     short loc_1400039E5
0x1400039d6  lea     ecx, [rbx+2]
0x1400039d9  call    Usage
0x1400039de  xor     ebx, ebx
0x1400039e0  jmp     loc_140003B2A
0x1400039e5  lea     rcx, [rsp+1C0h+var_150]
0x1400039ea  call    RegConnectMachine
0x1400039ef  test    eax, eax
0x1400039f1  jnz     short loc_1400039FB
0x1400039f3  or      ecx, 0FFFFFFFFh
0x1400039f6  jmp     loc_140003B0E
0x1400039fb  lea     rcx, [rbp+0C0h+var_B0]
0x1400039ff  call    RegConnectMachine
0x140003a04  test    eax, eax
0x140003a06  jz      short loc_1400039F3
0x140003a08  mov     rcx, [rsp+1C0h+hKey]
0x140003a0d  cmp     rcx, [rbp+0C0h+var_A8]
0x140003a11  jnz     short loc_140003A69
0x140003a13  mov     rdx, [rbp+0C0h+lpString2]; lpString2
0x140003a17  xor     r9d, r9d
0x140003a1a  mov     rcx, [rbp+0C0h+lpString1]; lpString1
0x140003a1e  mov     r8d, ebx
0x140003a21  call    StringCompareW
0x140003a26  test    eax, eax
0x140003a28  jnz     short loc_140003A64
0x140003a2a  mov     ecx, 800401E4h; dwErrCode
0x140003a2f  call    cs:__imp_SetLastError
0x140003a36  nop     dword ptr [rax+rax+00h]
0x140003a3b  xor     r8d, r8d
0x140003a3e  mov     edx, 83h
0x140003a43  call    GetResString2FromModule
0x140003a48  mov     rcx, rax
0x140003a4b  call    SetReason
0x140003a50  mov     ecx, 2; Ix
0x140003a55  call    _o___acrt_iob_func_0
0x140003a5a  mov     edx, 20000h
0x140003a5f  jmp     loc_140003B22
0x140003a64  mov     rcx, [rsp+1C0h+hKey]; hKey
0x140003a69  mov     r9d, [rbp+0C0h+var_C4]
0x140003a6d  lea     rax, [rsp+1C0h+var_170]
0x140003a72  mov     rdx, [rbp+0C0h+lpSubKey]; lpSubKey
0x140003a76  or      r9d, 20019h; samDesired
0x140003a7d  xor     r8d, r8d; ulOptions
0x140003a80  mov     [rsp+1C0h+phkResult], rax; phkResult
0x140003a85  call    cs:__imp_RegOpenKeyExW
0x140003a8c  nop     dword ptr [rax+rax+00h]
0x140003a91  test    eax, eax
0x140003a93  jz      short loc_140003A99
0x140003a95  mov     ecx, eax
0x140003a97  jmp     short loc_140003B0E
0x140003a99  mov     eax, [rbp+0C0h+var_24]
0x140003a9f  lea     rcx, [rsp+1C0h+dwDisposition]
0x140003aa4  mov     rdx, [rbp+0C0h+var_60]; lpSubKey
0x140003aa8  or      eax, 0F003Fh
0x140003aad  mov     [rsp+1C0h+lpdwDisposition], rcx; lpdwDisposition
0x140003ab2  xor     r9d, r9d; lpClass
0x140003ab5  lea     rcx, [rsp+1C0h+var_160]
0x140003aba  xor     r8d, r8d; Reserved
0x140003abd  mov     [rsp+1C0h+var_188], rcx; phkResult
0x140003ac2  mov     rcx, [rbp+0C0h+var_A8]; hKey
0x140003ac6  mov     [rsp+1C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140003acf  mov     [rsp+1C0h+samDesired], eax; samDesired
0x140003ad3  mov     dword ptr [rsp+1C0h+phkResult], 0; dwOptions
0x140003adb  call    cs:__imp_RegCreateKeyExW
0x140003ae2  nop     dword ptr [rax+rax+00h]
0x140003ae7  mov     rcx, [rsp+1C0h+var_170]; hKey
0x140003aec  mov     edi, eax
0x140003aee  test    eax, eax
0x140003af0  jz      short loc_140003B44
0x140003af2  test    rcx, rcx
0x140003af5  jz      short loc_140003B0C
0x140003af7  call    cs:__imp_RegCloseKey
0x140003afe  nop     dword ptr [rax+rax+00h]
0x140003b03  mov     [rsp+1C0h+var_170], 0
0x140003b0c  mov     ecx, edi
0x140003b0e  call    SaveErrorMessage
0x140003b13  mov     ecx, 2; Ix
0x140003b18  call    _o___acrt_iob_func_0
0x140003b1d  mov     edx, 20001h
0x140003b22  mov     rcx, rax
0x140003b25  call    ShowLastErrorEx
0x140003b2a  lea     rcx, [rsp+1C0h+var_150]
0x140003b2f  call    FreeGlobalData
0x140003b34  lea     rcx, [rbp+0C0h+var_B0]
0x140003b38  call    FreeGlobalData
0x140003b3d  mov     eax, ebx
0x140003b3f  jmp     loc_140003BF8
0x140003b44  mov     eax, [rbp+0C0h+var_C4]
0x140003b47  mov     rdx, [rbp+0C0h+lpSubKey]
0x140003b4b  mov     r8, [rsp+1C0h+var_160]
0x140003b50  mov     r9, rdx
0x140003b53  mov     dword ptr [rsp+1C0h+var_188], eax
0x140003b57  mov     eax, [rbp+0C0h+var_130]
0x140003b5a  mov     dword ptr [rsp+1C0h+lpSecurityAttributes], 0
0x140003b62  mov     [rsp+1C0h+samDesired], eax
0x140003b66  lea     rax, [rbp+0C0h+var_138]
0x140003b6a  mov     [rsp+1C0h+phkResult], rax
0x140003b6f  call    CopyEnumerateKey
0x140003b74  mov     rcx, [rsp+1C0h+var_160]; hKey
0x140003b79  mov     ebx, eax
0x140003b7b  test    rcx, rcx
0x140003b7e  jz      short loc_140003B95
0x140003b80  call    cs:__imp_RegCloseKey
0x140003b87  nop     dword ptr [rax+rax+00h]
0x140003b8c  mov     [rsp+1C0h+var_160], 0
0x140003b95  mov     rcx, [rsp+1C0h+var_170]; hKey
0x140003b9a  test    rcx, rcx
0x140003b9d  jz      short loc_140003BB4
0x140003b9f  call    cs:__imp_RegCloseKey
0x140003ba6  nop     dword ptr [rax+rax+00h]
0x140003bab  mov     [rsp+1C0h+var_170], 0
0x140003bb4  lea     rcx, [rsp+1C0h+var_150]
0x140003bb9  call    FreeGlobalData
0x140003bbe  lea     rcx, [rbp+0C0h+var_B0]
0x140003bc2  call    FreeGlobalData
0x140003bc7  xor     eax, eax
0x140003bc9  test    ebx, ebx
0x140003bcb  setnz   al
0x140003bce  jmp     short loc_140003BF8
0x140003bd0  mov     ecx, 57h ; 'W'; dwErrCode
0x140003bd5  call    cs:__imp_SetLastError
0x140003bdc  nop     dword ptr [rax+rax+00h]
0x140003be1  mov     ecx, 2; Ix
0x140003be6  call    _o___acrt_iob_func_0
0x140003beb  mov     rcx, rax
0x140003bee  call    ShowLastError
0x140003bf3  mov     eax, 1
0x140003bf8  mov     rcx, [rbp+0C0h+var_10]
0x140003bff  xor     rcx, rsp; StackCookie
0x140003c02  call    __security_check_cookie
0x140003c07  lea     r11, [rsp+1C0h+var_s0]
0x140003c0f  mov     rbx, [r11+20h]
0x140003c13  mov     rdi, [r11+28h]
0x140003c17  mov     rsp, r11
0x140003c1a  pop     rbp
0x140003c1b  retn
```
