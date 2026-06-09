# CompareRegistry

- ea: `0x140008cbc`
- end: `0x1400090a2`
- name: `CompareRegistry`
- size: `998`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
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
- `0x1400080a4`
- `0x140008cbc`
- `0x1400090a8`
- `0x14000957c`
- `0x14000d65c`
- `0x14000d694`
- `0x14000e560`
- `0x14000e75c`
- `0x14000e798`
- `0x14000e864`
- `0x14000eecc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008e68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008e9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008e68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008e9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008ed3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008fe0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008fff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008ed3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008fe0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008fff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008e14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009057`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008e14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009057`

## pseudocode

```c
__int64 __fastcall CompareRegistry(int a1, __int64 a2)
{
  int v4; // r14d
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  FILE *v8; // rax
  HKEY v9; // rcx
  __int64 v10; // rcx
  __int64 ResString2FromModule; // rax
  unsigned int v12; // eax
  unsigned int v13; // eax
  FILE *v14; // rax
  int v16; // eax
  __int64 v17; // rcx
  unsigned int v18; // esi
  __int64 v19; // rdx
  const WCHAR *v20; // rdi
  FILE *v21; // rax
  unsigned int v22; // ecx
  FILE *v23; // rax
  FILE *v24; // rbx
  const WCHAR *ResString; // rax
  FILE *v26; // rax
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  int v29; // [rsp+60h] [rbp-A0h] BYREF
  int v30; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY v31; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v32[4]; // [rsp+70h] [rbp-90h] BYREF
  int v33; // [rsp+74h] [rbp-8Ch]
  HKEY hKey; // [rsp+78h] [rbp-88h]
  int v35; // [rsp+90h] [rbp-70h]
  int v36; // [rsp+A4h] [rbp-5Ch]
  LPCWSTR lpSubKey; // [rsp+C0h] [rbp-40h]
  PCNZWCH lpString1; // [rsp+C8h] [rbp-38h]
  LPCWSTR lpValueName; // [rsp+D0h] [rbp-30h]
  int v40; // [rsp+FCh] [rbp-4h]
  _BYTE v41[4]; // [rsp+110h] [rbp+10h] BYREF
  int v42; // [rsp+114h] [rbp+14h]
  HKEY v43; // [rsp+118h] [rbp+18h]
  LPCWSTR v44; // [rsp+160h] [rbp+60h]
  PCNZWCH lpString2; // [rsp+168h] [rbp+68h]

  phkResult = 0;
  v31 = 0;
  v29 = 0;
  v33 = 0;
  memset_0(v32, 0, 0x94u);
  v42 = 0;
  memset_0(v41, 0, 0x94u);
  v4 = 0;
  LODWORD(v27) = 0;
  v30 = 0;
  if ( a1 && a2 )
  {
    InitGlobalData(8, v32);
    InitGlobalData(8, v41);
    v5 = ParseCompareCmdLine(a1, a2, (unsigned int)v32, (unsigned int)v41, (__int64)&v29);
    v6 = 1;
    if ( !v5 )
    {
LABEL_14:
      v8 = o___acrt_iob_func_0(2u);
      goto LABEL_9;
    }
    if ( v29 == 1 )
    {
      Usage(8);
      v6 = 0;
LABEL_21:
      FreeGlobalData(v32);
      FreeGlobalData(v41);
      return v6;
    }
    if ( !RegConnectMachine((__int64)v32) || !RegConnectMachine((__int64)v41) )
    {
      v7 = 0xFFFFFFFFLL;
LABEL_8:
      SaveErrorMessage(v7);
      v8 = o___acrt_iob_func_0(2u);
LABEL_9:
      ShowLastErrorEx(v8);
      goto LABEL_21;
    }
    v9 = hKey;
    if ( hKey == v43 )
    {
      if ( !(unsigned int)StringCompareW(lpString1, lpString2) )
      {
        SetLastError(0x800401E4);
        ResString2FromModule = GetResString2FromModule(v10, 151, 0);
        SetReason(ResString2FromModule);
        goto LABEL_14;
      }
      v9 = hKey;
    }
    v12 = RegOpenKeyExW(v9, lpSubKey, 0, v40 | 0x20019, &phkResult);
    if ( v12 )
    {
      v7 = v12;
      goto LABEL_8;
    }
    v13 = RegOpenKeyExW(v43, v44, 0, v40 | 0x20019, &v31);
    if ( v13 )
    {
      SaveErrorMessage(v13);
      v14 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v14);
      if ( phkResult )
      {
        RegCloseKey(phkResult);
        phkResult = 0;
      }
      goto LABEL_21;
    }
    if ( lpValueName )
    {
      v16 = CompareValues(phkResult, (__int64)lpString1, v31, (__int64)lpString2, lpValueName, v36, &v27);
    }
    else
    {
      v16 = CompareEnumerateKey(phkResult, lpString1, v31, lpString2, v36, v35, &v27, 0, v40, &v30);
      v4 = v30;
    }
    if ( v16 )
    {
      v18 = 1;
      v22 = 2;
    }
    else
    {
      if ( (_DWORD)v27 == 1 )
      {
        v18 = 2;
        v19 = 511;
      }
      else
      {
        v18 = 0;
        v19 = 512;
      }
      v20 = (const WCHAR *)GetResString2FromModule(v17, v19, 0);
      v21 = o___acrt_iob_func_0(1u);
      ShowMessage(v21, v20);
      SaveErrorMessage(0);
      v22 = 1;
    }
    v23 = o___acrt_iob_func_0(v22);
    ShowLastErrorEx(v23);
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      phkResult = 0;
    }
    if ( v31 )
    {
      RegCloseKey(v31);
      v31 = 0;
    }
    FreeGlobalData(v32);
    FreeGlobalData(v41);
    if ( v4 == 1 )
    {
      v24 = o___acrt_iob_func_0(2u);
      ResString = (const WCHAR *)GetResString(708);
      ShowMessage(v24, ResString);
    }
    return v18;
  }
  else
  {
    SetLastError(0x57u);
    v26 = o___acrt_iob_func_0(2u);
    ShowLastError(v26);
    return 1;
  }
}

```

## disassembly

```asm
0x140008cbc  mov     [rsp-8+arg_10], rbx
0x140008cc1  mov     [rsp-8+arg_18], rsi
0x140008cc6  push    rbp
0x140008cc7  push    rdi
0x140008cc8  push    r14
0x140008cca  lea     rbp, [rsp-0C0h]
0x140008cd2  sub     rsp, 1C0h
0x140008cd9  mov     rax, cs:__security_cookie
0x140008ce0  xor     rax, rsp
0x140008ce3  mov     [rbp+0D0h+var_20], rax
0x140008cea  mov     rbx, rdx
0x140008ced  mov     [rsp+1D0h+var_178], 0
0x140008cf6  mov     edi, ecx
0x140008cf8  mov     [rsp+1D0h+var_168], 0
0x140008d01  xor     eax, eax
0x140008d03  mov     [rsp+1D0h+var_170], 0
0x140008d0b  mov     esi, 94h
0x140008d10  mov     [rsp+1D0h+var_15C], eax
0x140008d14  mov     r8d, esi; Size
0x140008d17  lea     rcx, [rsp+1D0h+var_160]; void *
0x140008d1c  xor     edx, edx; Val
0x140008d1e  call    memset_0
0x140008d23  xor     eax, eax
0x140008d25  lea     rcx, [rbp+0D0h+var_C0]; void *
0x140008d29  mov     r8d, esi; Size
0x140008d2c  mov     [rbp+0D0h+var_BC], eax
0x140008d2f  xor     edx, edx; Val
0x140008d31  call    memset_0
0x140008d36  xor     r14d, r14d
0x140008d39  mov     dword ptr [rsp+1D0h+var_180], 0
0x140008d41  mov     [rsp+1D0h+var_16C], r14d
0x140008d46  test    edi, edi
0x140008d48  jz      loc_140009052
0x140008d4e  test    rbx, rbx
0x140008d51  jz      loc_140009052
0x140008d57  lea     esi, [r14+8]
0x140008d5b  mov     ecx, esi
0x140008d5d  lea     rdx, [rsp+1D0h+var_160]
0x140008d62  call    InitGlobalData
0x140008d67  lea     rdx, [rbp+0D0h+var_C0]
0x140008d6b  mov     ecx, esi
0x140008d6d  call    InitGlobalData
0x140008d72  lea     rax, [rsp+1D0h+var_170]
0x140008d77  mov     rdx, rbx
0x140008d7a  lea     r9, [rbp+0D0h+var_C0]
0x140008d7e  mov     [rsp+1D0h+phkResult], rax
0x140008d83  lea     r8, [rsp+1D0h+var_160]
0x140008d88  mov     ecx, edi
0x140008d8a  call    ParseCompareCmdLine
0x140008d8f  lea     ebx, [rsi-7]
0x140008d92  test    eax, eax
0x140008d94  jz      loc_140008E35
0x140008d9a  cmp     [rsp+1D0h+var_170], ebx
0x140008d9e  jnz     short loc_140008DAE
0x140008da0  mov     ecx, esi
0x140008da2  call    Usage
0x140008da7  xor     ebx, ebx
0x140008da9  jmp     loc_140008EE4
0x140008dae  lea     rcx, [rsp+1D0h+var_160]
0x140008db3  call    RegConnectMachine
0x140008db8  test    eax, eax
0x140008dba  jnz     short loc_140008DE0
0x140008dbc  or      ecx, 0FFFFFFFFh
0x140008dbf  call    SaveErrorMessage
0x140008dc4  mov     ecx, 2; Ix
0x140008dc9  call    _o___acrt_iob_func_0
0x140008dce  mov     edx, 20001h
0x140008dd3  mov     rcx, rax
0x140008dd6  call    ShowLastErrorEx
0x140008ddb  jmp     loc_140008EE4
0x140008de0  lea     rcx, [rbp+0D0h+var_C0]
0x140008de4  call    RegConnectMachine
0x140008de9  test    eax, eax
0x140008deb  jz      short loc_140008DBC
0x140008ded  mov     rcx, [rsp+1D0h+hKey]
0x140008df2  cmp     rcx, [rbp+0D0h+var_B8]
0x140008df6  jnz     short loc_140008E4B
0x140008df8  mov     rdx, [rbp+0D0h+lpString2]; lpString2
0x140008dfc  xor     r9d, r9d
0x140008dff  mov     rcx, [rbp+0D0h+lpString1]; lpString1
0x140008e03  mov     r8d, ebx
0x140008e06  call    StringCompareW
0x140008e0b  test    eax, eax
0x140008e0d  jnz     short loc_140008E46
0x140008e0f  mov     ecx, 800401E4h; dwErrCode
0x140008e14  call    cs:__imp_SetLastError
0x140008e1b  nop     dword ptr [rax+rax+00h]
0x140008e20  xor     r8d, r8d
0x140008e23  mov     edx, 97h
0x140008e28  call    GetResString2FromModule
0x140008e2d  mov     rcx, rax
0x140008e30  call    SetReason
0x140008e35  mov     ecx, 2; Ix
0x140008e3a  call    _o___acrt_iob_func_0
0x140008e3f  mov     edx, 20000h
0x140008e44  jmp     short loc_140008DD3
0x140008e46  mov     rcx, [rsp+1D0h+hKey]; hKey
0x140008e4b  mov     r9d, [rbp+0D0h+var_D4]
0x140008e4f  lea     rax, [rsp+1D0h+var_178]
0x140008e54  mov     rdx, [rbp+0D0h+lpSubKey]; lpSubKey
0x140008e58  mov     edi, 20019h
0x140008e5d  or      r9d, edi; samDesired
0x140008e60  mov     [rsp+1D0h+phkResult], rax; phkResult
0x140008e65  xor     r8d, r8d; ulOptions
0x140008e68  call    cs:__imp_RegOpenKeyExW
0x140008e6f  nop     dword ptr [rax+rax+00h]
0x140008e74  test    eax, eax
0x140008e76  jz      short loc_140008E7F
0x140008e78  mov     ecx, eax
0x140008e7a  jmp     loc_140008DBF
0x140008e7f  mov     r9d, [rbp+0D0h+var_D4]
0x140008e83  lea     rax, [rsp+1D0h+var_168]
0x140008e88  mov     rdx, [rbp+0D0h+var_70]; lpSubKey
0x140008e8c  or      r9d, edi; samDesired
0x140008e8f  mov     rcx, [rbp+0D0h+var_B8]; hKey
0x140008e93  xor     r8d, r8d; ulOptions
0x140008e96  mov     [rsp+1D0h+phkResult], rax; phkResult
0x140008e9b  call    cs:__imp_RegOpenKeyExW
0x140008ea2  nop     dword ptr [rax+rax+00h]
0x140008ea7  test    eax, eax
0x140008ea9  jz      short loc_140008EFE
0x140008eab  mov     ecx, eax
0x140008ead  call    SaveErrorMessage
0x140008eb2  mov     ecx, 2; Ix
0x140008eb7  call    _o___acrt_iob_func_0
0x140008ebc  mov     rcx, rax
0x140008ebf  mov     edx, 20001h
0x140008ec4  call    ShowLastErrorEx
0x140008ec9  mov     rcx, [rsp+1D0h+var_178]; hKey
0x140008ece  test    rcx, rcx
0x140008ed1  jz      short loc_140008EE4
0x140008ed3  call    cs:__imp_RegCloseKey
0x140008eda  nop     dword ptr [rax+rax+00h]
0x140008edf  mov     [rsp+1D0h+var_178], r14
0x140008ee4  lea     rcx, [rsp+1D0h+var_160]
0x140008ee9  call    FreeGlobalData
0x140008eee  lea     rcx, [rbp+0D0h+var_C0]
0x140008ef2  call    FreeGlobalData
0x140008ef7  mov     eax, ebx
0x140008ef9  jmp     loc_14000907A
0x140008efe  mov     rcx, [rbp+0D0h+lpValueName]
0x140008f02  mov     r9, [rbp+0D0h+lpString2]
0x140008f06  mov     r8, [rsp+1D0h+var_168]
0x140008f0b  mov     rdx, [rbp+0D0h+lpString1]
0x140008f0f  test    rcx, rcx
0x140008f12  jz      short loc_140008F36
0x140008f14  lea     rax, [rsp+1D0h+var_180]
0x140008f19  mov     [rsp+1D0h+var_1A0], rax; __int64
0x140008f1e  mov     eax, [rbp+0D0h+var_12C]
0x140008f21  mov     [rsp+1D0h+var_1A8], eax; int
0x140008f25  mov     [rsp+1D0h+phkResult], rcx; lpValueName
0x140008f2a  mov     rcx, [rsp+1D0h+var_178]; hKey
0x140008f2f  call    CompareValues
0x140008f34  jmp     short loc_140008F73
0x140008f36  mov     rcx, [rsp+1D0h+var_178]
0x140008f3b  lea     rax, [rsp+1D0h+var_16C]
0x140008f40  mov     [rsp+1D0h+var_188], rax
0x140008f45  mov     eax, [rbp+0D0h+var_D4]
0x140008f48  mov     [rsp+1D0h+var_190], eax
0x140008f4c  lea     rax, [rsp+1D0h+var_180]
0x140008f51  mov     [rsp+1D0h+var_198], r14d
0x140008f56  mov     [rsp+1D0h+var_1A0], rax
0x140008f5b  mov     eax, [rbp+0D0h+var_140]
0x140008f5e  mov     [rsp+1D0h+var_1A8], eax
0x140008f62  mov     eax, [rbp+0D0h+var_12C]
0x140008f65  mov     dword ptr [rsp+1D0h+phkResult], eax
0x140008f69  call    CompareEnumerateKey
0x140008f6e  mov     r14d, [rsp+1D0h+var_16C]
0x140008f73  test    eax, eax
0x140008f75  jnz     short loc_140008FBB
0x140008f77  xor     r8d, r8d
0x140008f7a  cmp     dword ptr [rsp+1D0h+var_180], ebx
0x140008f7e  jnz     short loc_140008F8A
0x140008f80  lea     esi, [rax+2]
0x140008f83  mov     edx, 1FFh
0x140008f88  jmp     short loc_140008F91
0x140008f8a  xor     esi, esi
0x140008f8c  mov     edx, 200h
0x140008f91  call    GetResString2FromModule
0x140008f96  mov     ecx, ebx; Ix
0x140008f98  mov     rdi, rax
0x140008f9b  call    _o___acrt_iob_func_0
0x140008fa0  mov     rcx, rax; Stream
0x140008fa3  mov     rdx, rdi; lpString
0x140008fa6  call    ShowMessage
0x140008fab  xor     ecx, ecx
0x140008fad  call    SaveErrorMessage
0x140008fb2  mov     ecx, ebx
0x140008fb4  mov     edi, 20000h
0x140008fb9  jmp     short loc_140008FC7
0x140008fbb  mov     esi, ebx
0x140008fbd  mov     edi, 20001h
0x140008fc2  mov     ecx, 2; Ix
0x140008fc7  call    _o___acrt_iob_func_0
0x140008fcc  mov     rcx, rax
0x140008fcf  mov     edx, edi
0x140008fd1  call    ShowLastErrorEx
0x140008fd6  mov     rcx, [rsp+1D0h+var_178]; hKey
0x140008fdb  test    rcx, rcx
0x140008fde  jz      short loc_140008FF5
0x140008fe0  call    cs:__imp_RegCloseKey
0x140008fe7  nop     dword ptr [rax+rax+00h]
0x140008fec  mov     [rsp+1D0h+var_178], 0
0x140008ff5  mov     rcx, [rsp+1D0h+var_168]; hKey
0x140008ffa  test    rcx, rcx
0x140008ffd  jz      short loc_140009014
0x140008fff  call    cs:__imp_RegCloseKey
0x140009006  nop     dword ptr [rax+rax+00h]
0x14000900b  mov     [rsp+1D0h+var_168], 0
0x140009014  lea     rcx, [rsp+1D0h+var_160]
0x140009019  call    FreeGlobalData
0x14000901e  lea     rcx, [rbp+0D0h+var_C0]
0x140009022  call    FreeGlobalData
0x140009027  cmp     r14d, ebx
0x14000902a  jnz     short loc_14000904E
0x14000902c  mov     ecx, 2; Ix
0x140009031  call    _o___acrt_iob_func_0
0x140009036  mov     ecx, 2C4h
0x14000903b  mov     rbx, rax
0x14000903e  call    GetResString
0x140009043  mov     rdx, rax; lpString
0x140009046  mov     rcx, rbx; Stream
0x140009049  call    ShowMessage
0x14000904e  mov     eax, esi
0x140009050  jmp     short loc_14000907A
0x140009052  mov     ecx, 57h ; 'W'; dwErrCode
0x140009057  call    cs:__imp_SetLastError
0x14000905e  nop     dword ptr [rax+rax+00h]
0x140009063  mov     ecx, 2; Ix
0x140009068  call    _o___acrt_iob_func_0
0x14000906d  mov     rcx, rax
0x140009070  call    ShowLastError
0x140009075  mov     eax, 1
0x14000907a  mov     rcx, [rbp+0D0h+var_20]
0x140009081  xor     rcx, rsp; StackCookie
0x140009084  call    __security_check_cookie
0x140009089  lea     r11, [rsp+1D0h+var_10]
0x140009091  mov     rbx, [r11+30h]
0x140009095  mov     rsi, [r11+38h]
0x140009099  mov     rsp, r11
0x14000909c  pop     r14
0x14000909e  pop     rdi
0x14000909f  pop     rbp
0x1400090a0  retn
```
