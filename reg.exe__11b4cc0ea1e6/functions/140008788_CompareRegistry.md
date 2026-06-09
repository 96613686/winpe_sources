# CompareRegistry

- ea: `0x140008788`
- end: `0x140008b43`
- name: `CompareRegistry`
- size: `955`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400030b8`

## callees

- `0x140001340`
- `0x140001bb2`
- `0x140001cc6`
- `0x140001fec`
- `0x140002234`
- `0x140002ac8`
- `0x140002b70`
- `0x140002f30`
- `0x140007be0`
- `0x140008788`
- `0x140008b4c`
- `0x140008fe8`
- `0x14000cd10`
- `0x14000cd48`
- `0x14000da24`
- `0x14000dbe8`
- `0x14000dc24`
- `0x14000dce0`
- `0x14000e284`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000892e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000895b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000892e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000895b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000898d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008a94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008aad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000898d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008a94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008aad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400088e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008aff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400088e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008aff`

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
    if ( !(unsigned int)RegConnectMachine(v32) || !(unsigned int)RegConnectMachine(v41) )
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
      v16 = CompareValues(phkResult, lpValueName, v36, (__int64)&v27);
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
0x140008788  mov     [rsp-8+arg_10], rbx
0x14000878d  mov     [rsp-8+arg_18], rsi
0x140008792  push    rbp
0x140008793  push    rdi
0x140008794  push    r14
0x140008796  lea     rbp, [rsp-0C0h]
0x14000879e  sub     rsp, 1C0h
0x1400087a5  mov     rax, cs:__security_cookie
0x1400087ac  xor     rax, rsp
0x1400087af  mov     [rbp+0D0h+var_20], rax
0x1400087b6  mov     rbx, rdx
0x1400087b9  mov     [rsp+1D0h+var_178], 0
0x1400087c2  mov     edi, ecx
0x1400087c4  mov     [rsp+1D0h+var_168], 0
0x1400087cd  xor     eax, eax
0x1400087cf  mov     [rsp+1D0h+var_170], 0
0x1400087d7  mov     esi, 94h
0x1400087dc  mov     [rsp+1D0h+var_15C], eax
0x1400087e0  mov     r8d, esi; Size
0x1400087e3  lea     rcx, [rsp+1D0h+var_160]; void *
0x1400087e8  xor     edx, edx; Val
0x1400087ea  call    memset_0
0x1400087ef  xor     eax, eax
0x1400087f1  lea     rcx, [rbp+0D0h+var_C0]; void *
0x1400087f5  mov     r8d, esi; Size
0x1400087f8  mov     [rbp+0D0h+var_BC], eax
0x1400087fb  xor     edx, edx; Val
0x1400087fd  call    memset_0
0x140008802  xor     r14d, r14d
0x140008805  mov     dword ptr [rsp+1D0h+var_180], 0
0x14000880d  mov     [rsp+1D0h+var_16C], r14d
0x140008812  test    edi, edi
0x140008814  jz      loc_140008AFA
0x14000881a  test    rbx, rbx
0x14000881d  jz      loc_140008AFA
0x140008823  lea     esi, [r14+8]
0x140008827  mov     ecx, esi
0x140008829  lea     rdx, [rsp+1D0h+var_160]
0x14000882e  call    InitGlobalData
0x140008833  lea     rdx, [rbp+0D0h+var_C0]
0x140008837  mov     ecx, esi
0x140008839  call    InitGlobalData
0x14000883e  lea     rax, [rsp+1D0h+var_170]
0x140008843  mov     rdx, rbx
0x140008846  lea     r9, [rbp+0D0h+var_C0]
0x14000884a  mov     [rsp+1D0h+phkResult], rax
0x14000884f  lea     r8, [rsp+1D0h+var_160]
0x140008854  mov     ecx, edi
0x140008856  call    ParseCompareCmdLine
0x14000885b  lea     ebx, [rsi-7]
0x14000885e  test    eax, eax
0x140008860  jz      loc_1400088FB
0x140008866  cmp     [rsp+1D0h+var_170], ebx
0x14000886a  jnz     short loc_14000887A
0x14000886c  mov     ecx, esi
0x14000886e  call    Usage
0x140008873  xor     ebx, ebx
0x140008875  jmp     loc_140008998
0x14000887a  lea     rcx, [rsp+1D0h+var_160]
0x14000887f  call    RegConnectMachine
0x140008884  test    eax, eax
0x140008886  jnz     short loc_1400088AC
0x140008888  or      ecx, 0FFFFFFFFh
0x14000888b  call    SaveErrorMessage
0x140008890  mov     ecx, 2; Ix
0x140008895  call    _o___acrt_iob_func_0
0x14000889a  mov     edx, 20001h
0x14000889f  mov     rcx, rax
0x1400088a2  call    ShowLastErrorEx
0x1400088a7  jmp     loc_140008998
0x1400088ac  lea     rcx, [rbp+0D0h+var_C0]
0x1400088b0  call    RegConnectMachine
0x1400088b5  test    eax, eax
0x1400088b7  jz      short loc_140008888
0x1400088b9  mov     rcx, [rsp+1D0h+hKey]
0x1400088be  cmp     rcx, [rbp+0D0h+var_B8]
0x1400088c2  jnz     short loc_140008911
0x1400088c4  mov     rdx, [rbp+0D0h+lpString2]; lpString2
0x1400088c8  xor     r9d, r9d
0x1400088cb  mov     rcx, [rbp+0D0h+lpString1]; lpString1
0x1400088cf  mov     r8d, ebx
0x1400088d2  call    StringCompareW
0x1400088d7  test    eax, eax
0x1400088d9  jnz     short loc_14000890C
0x1400088db  mov     ecx, 800401E4h; dwErrCode
0x1400088e0  call    cs:__imp_SetLastError
0x1400088e6  xor     r8d, r8d
0x1400088e9  mov     edx, 97h
0x1400088ee  call    GetResString2FromModule
0x1400088f3  mov     rcx, rax
0x1400088f6  call    SetReason
0x1400088fb  mov     ecx, 2; Ix
0x140008900  call    _o___acrt_iob_func_0
0x140008905  mov     edx, 20000h
0x14000890a  jmp     short loc_14000889F
0x14000890c  mov     rcx, [rsp+1D0h+hKey]; hKey
0x140008911  mov     r9d, [rbp+0D0h+var_D4]
0x140008915  lea     rax, [rsp+1D0h+var_178]
0x14000891a  mov     rdx, [rbp+0D0h+lpSubKey]; lpSubKey
0x14000891e  mov     edi, 20019h
0x140008923  or      r9d, edi; samDesired
0x140008926  mov     [rsp+1D0h+phkResult], rax; phkResult
0x14000892b  xor     r8d, r8d; ulOptions
0x14000892e  call    cs:__imp_RegOpenKeyExW
0x140008934  test    eax, eax
0x140008936  jz      short loc_14000893F
0x140008938  mov     ecx, eax
0x14000893a  jmp     loc_14000888B
0x14000893f  mov     r9d, [rbp+0D0h+var_D4]
0x140008943  lea     rax, [rsp+1D0h+var_168]
0x140008948  mov     rdx, [rbp+0D0h+var_70]; lpSubKey
0x14000894c  or      r9d, edi; samDesired
0x14000894f  mov     rcx, [rbp+0D0h+var_B8]; hKey
0x140008953  xor     r8d, r8d; ulOptions
0x140008956  mov     [rsp+1D0h+phkResult], rax; phkResult
0x14000895b  call    cs:__imp_RegOpenKeyExW
0x140008961  test    eax, eax
0x140008963  jz      short loc_1400089B2
0x140008965  mov     ecx, eax
0x140008967  call    SaveErrorMessage
0x14000896c  mov     ecx, 2; Ix
0x140008971  call    _o___acrt_iob_func_0
0x140008976  mov     rcx, rax
0x140008979  mov     edx, 20001h
0x14000897e  call    ShowLastErrorEx
0x140008983  mov     rcx, [rsp+1D0h+var_178]; hKey
0x140008988  test    rcx, rcx
0x14000898b  jz      short loc_140008998
0x14000898d  call    cs:__imp_RegCloseKey
0x140008993  mov     [rsp+1D0h+var_178], r14
0x140008998  lea     rcx, [rsp+1D0h+var_160]
0x14000899d  call    FreeGlobalData
0x1400089a2  lea     rcx, [rbp+0D0h+var_C0]
0x1400089a6  call    FreeGlobalData
0x1400089ab  mov     eax, ebx
0x1400089ad  jmp     loc_140008B1C
0x1400089b2  mov     rcx, [rbp+0D0h+lpValueName]
0x1400089b6  mov     r9, [rbp+0D0h+lpString2]
0x1400089ba  mov     r8, [rsp+1D0h+var_168]
0x1400089bf  mov     rdx, [rbp+0D0h+lpString1]
0x1400089c3  test    rcx, rcx
0x1400089c6  jz      short loc_1400089EA
0x1400089c8  lea     rax, [rsp+1D0h+var_180]
0x1400089cd  mov     [rsp+1D0h+var_1A0], rax; __int64
0x1400089d2  mov     eax, [rbp+0D0h+var_12C]
0x1400089d5  mov     [rsp+1D0h+var_1A8], eax; int
0x1400089d9  mov     [rsp+1D0h+phkResult], rcx; lpValueName
0x1400089de  mov     rcx, [rsp+1D0h+var_178]; hKey
0x1400089e3  call    CompareValues
0x1400089e8  jmp     short loc_140008A27
0x1400089ea  mov     rcx, [rsp+1D0h+var_178]
0x1400089ef  lea     rax, [rsp+1D0h+var_16C]
0x1400089f4  mov     [rsp+1D0h+var_188], rax
0x1400089f9  mov     eax, [rbp+0D0h+var_D4]
0x1400089fc  mov     [rsp+1D0h+var_190], eax
0x140008a00  lea     rax, [rsp+1D0h+var_180]
0x140008a05  mov     [rsp+1D0h+var_198], r14d
0x140008a0a  mov     [rsp+1D0h+var_1A0], rax
0x140008a0f  mov     eax, [rbp+0D0h+var_140]
0x140008a12  mov     [rsp+1D0h+var_1A8], eax
0x140008a16  mov     eax, [rbp+0D0h+var_12C]
0x140008a19  mov     dword ptr [rsp+1D0h+phkResult], eax
0x140008a1d  call    CompareEnumerateKey
0x140008a22  mov     r14d, [rsp+1D0h+var_16C]
0x140008a27  test    eax, eax
0x140008a29  jnz     short loc_140008A6F
0x140008a2b  xor     r8d, r8d
0x140008a2e  cmp     dword ptr [rsp+1D0h+var_180], ebx
0x140008a32  jnz     short loc_140008A3E
0x140008a34  lea     esi, [rax+2]
0x140008a37  mov     edx, 1FFh
0x140008a3c  jmp     short loc_140008A45
0x140008a3e  xor     esi, esi
0x140008a40  mov     edx, 200h
0x140008a45  call    GetResString2FromModule
0x140008a4a  mov     ecx, ebx; Ix
0x140008a4c  mov     rdi, rax
0x140008a4f  call    _o___acrt_iob_func_0
0x140008a54  mov     rcx, rax; Stream
0x140008a57  mov     rdx, rdi; lpString
0x140008a5a  call    ShowMessage
0x140008a5f  xor     ecx, ecx
0x140008a61  call    SaveErrorMessage
0x140008a66  mov     ecx, ebx
0x140008a68  mov     edi, 20000h
0x140008a6d  jmp     short loc_140008A7B
0x140008a6f  mov     esi, ebx
0x140008a71  mov     edi, 20001h
0x140008a76  mov     ecx, 2; Ix
0x140008a7b  call    _o___acrt_iob_func_0
0x140008a80  mov     rcx, rax
0x140008a83  mov     edx, edi
0x140008a85  call    ShowLastErrorEx
0x140008a8a  mov     rcx, [rsp+1D0h+var_178]; hKey
0x140008a8f  test    rcx, rcx
0x140008a92  jz      short loc_140008AA3
0x140008a94  call    cs:__imp_RegCloseKey
0x140008a9a  mov     [rsp+1D0h+var_178], 0
0x140008aa3  mov     rcx, [rsp+1D0h+var_168]; hKey
0x140008aa8  test    rcx, rcx
0x140008aab  jz      short loc_140008ABC
0x140008aad  call    cs:__imp_RegCloseKey
0x140008ab3  mov     [rsp+1D0h+var_168], 0
0x140008abc  lea     rcx, [rsp+1D0h+var_160]
0x140008ac1  call    FreeGlobalData
0x140008ac6  lea     rcx, [rbp+0D0h+var_C0]
0x140008aca  call    FreeGlobalData
0x140008acf  cmp     r14d, ebx
0x140008ad2  jnz     short loc_140008AF6
0x140008ad4  mov     ecx, 2; Ix
0x140008ad9  call    _o___acrt_iob_func_0
0x140008ade  mov     ecx, 2C4h
0x140008ae3  mov     rbx, rax
0x140008ae6  call    GetResString
0x140008aeb  mov     rdx, rax; lpString
0x140008aee  mov     rcx, rbx; Stream
0x140008af1  call    ShowMessage
0x140008af6  mov     eax, esi
0x140008af8  jmp     short loc_140008B1C
0x140008afa  mov     ecx, 57h ; 'W'; dwErrCode
0x140008aff  call    cs:__imp_SetLastError
0x140008b05  mov     ecx, 2; Ix
0x140008b0a  call    _o___acrt_iob_func_0
0x140008b0f  mov     rcx, rax
0x140008b12  call    ShowLastError
0x140008b17  mov     eax, 1
0x140008b1c  mov     rcx, [rbp+0D0h+var_20]
0x140008b23  xor     rcx, rsp; StackCookie
0x140008b26  call    __security_check_cookie
0x140008b2b  lea     r11, [rsp+1D0h+var_10]
0x140008b33  mov     rbx, [r11+30h]
0x140008b37  mov     rsi, [r11+38h]
0x140008b3b  mov     rsp, r11
0x140008b3e  pop     r14
0x140008b40  pop     rdi
0x140008b41  pop     rbp
0x140008b42  retn
```
