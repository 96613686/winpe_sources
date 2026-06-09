# CopyRegistry

- ea: `0x14000375c`
- end: `0x140003a52`
- name: `CopyRegistry`
- size: `758`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
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
- `0x14000329c`
- `0x14000375c`
- `0x140003c48`
- `0x14000cd48`
- `0x14000da24`
- `0x14000dbe8`
- `0x14000dc24`
- `0x14000e284`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400038df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400038df`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000392f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000392f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003945`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400039c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400039e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003945`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400039c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400039e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000388f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003a11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000388f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003a11`

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
    if ( !(unsigned int)RegConnectMachine(v20) || !(unsigned int)RegConnectMachine(v28) )
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
0x14000375c  mov     [rsp-8+arg_10], rbx
0x140003761  mov     [rsp-8+arg_18], rdi
0x140003766  push    rbp
0x140003767  lea     rbp, [rsp-0C0h]
0x14000376f  sub     rsp, 1C0h
0x140003776  mov     rax, cs:__security_cookie
0x14000377d  xor     rax, rsp
0x140003780  mov     [rbp+0C0h+var_10], rax
0x140003787  mov     rbx, rdx
0x14000378a  mov     [rsp+1C0h+var_170], 0
0x140003793  mov     edi, ecx
0x140003795  mov     [rsp+1C0h+var_160], 0
0x14000379e  xor     eax, eax
0x1400037a0  mov     [rsp+1C0h+var_168], 0
0x1400037a8  xor     edx, edx; Val
0x1400037aa  mov     [rsp+1C0h+var_14C], eax
0x1400037ae  lea     rcx, [rsp+1C0h+var_150]; void *
0x1400037b3  mov     [rsp+1C0h+dwDisposition], 0
0x1400037bb  mov     r8d, 94h; Size
0x1400037c1  call    memset_0
0x1400037c6  xor     eax, eax
0x1400037c8  lea     rcx, [rbp+0C0h+var_B0]; void *
0x1400037cc  xor     edx, edx; Val
0x1400037ce  mov     [rbp+0C0h+var_AC], eax
0x1400037d1  mov     r8d, 94h; Size
0x1400037d7  call    memset_0
0x1400037dc  test    edi, edi
0x1400037de  jz      loc_140003A0C
0x1400037e4  test    rbx, rbx
0x1400037e7  jz      loc_140003A0C
0x1400037ed  lea     rdx, [rsp+1C0h+var_150]
0x1400037f2  mov     ecx, 3
0x1400037f7  call    InitGlobalData
0x1400037fc  lea     rdx, [rbp+0C0h+var_B0]
0x140003800  mov     ecx, 3
0x140003805  call    InitGlobalData
0x14000380a  lea     rax, [rsp+1C0h+var_168]
0x14000380f  mov     rdx, rbx
0x140003812  lea     r9, [rbp+0C0h+var_B0]
0x140003816  mov     [rsp+1C0h+phkResult], rax
0x14000381b  lea     r8, [rsp+1C0h+var_150]
0x140003820  mov     ecx, edi
0x140003822  call    ParseCopyCmdLine
0x140003827  mov     ebx, 1
0x14000382c  test    eax, eax
0x14000382e  jz      short loc_1400038AA
0x140003830  cmp     [rsp+1C0h+var_168], ebx
0x140003834  jnz     short loc_140003845
0x140003836  lea     ecx, [rbx+2]
0x140003839  call    Usage
0x14000383e  xor     ebx, ebx
0x140003840  jmp     loc_140003972
0x140003845  lea     rcx, [rsp+1C0h+var_150]
0x14000384a  call    RegConnectMachine
0x14000384f  test    eax, eax
0x140003851  jnz     short loc_14000385B
0x140003853  or      ecx, 0FFFFFFFFh
0x140003856  jmp     loc_140003956
0x14000385b  lea     rcx, [rbp+0C0h+var_B0]
0x14000385f  call    RegConnectMachine
0x140003864  test    eax, eax
0x140003866  jz      short loc_140003853
0x140003868  mov     rcx, [rsp+1C0h+hKey]
0x14000386d  cmp     rcx, [rbp+0C0h+var_A8]
0x140003871  jnz     short loc_1400038C3
0x140003873  mov     rdx, [rbp+0C0h+lpString2]; lpString2
0x140003877  xor     r9d, r9d
0x14000387a  mov     rcx, [rbp+0C0h+lpString1]; lpString1
0x14000387e  mov     r8d, ebx
0x140003881  call    StringCompareW
0x140003886  test    eax, eax
0x140003888  jnz     short loc_1400038BE
0x14000388a  mov     ecx, 800401E4h; dwErrCode
0x14000388f  call    cs:__imp_SetLastError
0x140003895  xor     r8d, r8d
0x140003898  mov     edx, 83h
0x14000389d  call    GetResString2FromModule
0x1400038a2  mov     rcx, rax
0x1400038a5  call    SetReason
0x1400038aa  mov     ecx, 2; Ix
0x1400038af  call    _o___acrt_iob_func_0
0x1400038b4  mov     edx, 20000h
0x1400038b9  jmp     loc_14000396A
0x1400038be  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1400038c3  mov     r9d, [rbp+0C0h+var_C4]
0x1400038c7  lea     rax, [rsp+1C0h+var_170]
0x1400038cc  mov     rdx, [rbp+0C0h+lpSubKey]; lpSubKey
0x1400038d0  or      r9d, 20019h; samDesired
0x1400038d7  xor     r8d, r8d; ulOptions
0x1400038da  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1400038df  call    cs:__imp_RegOpenKeyExW
0x1400038e5  test    eax, eax
0x1400038e7  jz      short loc_1400038ED
0x1400038e9  mov     ecx, eax
0x1400038eb  jmp     short loc_140003956
0x1400038ed  mov     eax, [rbp+0C0h+var_24]
0x1400038f3  lea     rcx, [rsp+1C0h+dwDisposition]
0x1400038f8  mov     rdx, [rbp+0C0h+var_60]; lpSubKey
0x1400038fc  or      eax, 0F003Fh
0x140003901  mov     [rsp+1C0h+lpdwDisposition], rcx; lpdwDisposition
0x140003906  xor     r9d, r9d; lpClass
0x140003909  lea     rcx, [rsp+1C0h+var_160]
0x14000390e  xor     r8d, r8d; Reserved
0x140003911  mov     [rsp+1C0h+var_188], rcx; phkResult
0x140003916  mov     rcx, [rbp+0C0h+var_A8]; hKey
0x14000391a  mov     [rsp+1C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140003923  mov     [rsp+1C0h+samDesired], eax; samDesired
0x140003927  mov     dword ptr [rsp+1C0h+phkResult], 0; dwOptions
0x14000392f  call    cs:__imp_RegCreateKeyExW
0x140003935  mov     rcx, [rsp+1C0h+var_170]; hKey
0x14000393a  mov     edi, eax
0x14000393c  test    eax, eax
0x14000393e  jz      short loc_14000398C
0x140003940  test    rcx, rcx
0x140003943  jz      short loc_140003954
0x140003945  call    cs:__imp_RegCloseKey
0x14000394b  mov     [rsp+1C0h+var_170], 0
0x140003954  mov     ecx, edi
0x140003956  call    SaveErrorMessage
0x14000395b  mov     ecx, 2; Ix
0x140003960  call    _o___acrt_iob_func_0
0x140003965  mov     edx, 20001h
0x14000396a  mov     rcx, rax
0x14000396d  call    ShowLastErrorEx
0x140003972  lea     rcx, [rsp+1C0h+var_150]
0x140003977  call    FreeGlobalData
0x14000397c  lea     rcx, [rbp+0C0h+var_B0]
0x140003980  call    FreeGlobalData
0x140003985  mov     eax, ebx
0x140003987  jmp     loc_140003A2E
0x14000398c  mov     eax, [rbp+0C0h+var_C4]
0x14000398f  mov     rdx, [rbp+0C0h+lpSubKey]
0x140003993  mov     r8, [rsp+1C0h+var_160]
0x140003998  mov     r9, rdx
0x14000399b  mov     dword ptr [rsp+1C0h+var_188], eax
0x14000399f  mov     eax, [rbp+0C0h+var_130]
0x1400039a2  mov     dword ptr [rsp+1C0h+lpSecurityAttributes], 0
0x1400039aa  mov     [rsp+1C0h+samDesired], eax
0x1400039ae  lea     rax, [rbp+0C0h+var_138]
0x1400039b2  mov     [rsp+1C0h+phkResult], rax
0x1400039b7  call    CopyEnumerateKey
0x1400039bc  mov     rcx, [rsp+1C0h+var_160]; hKey
0x1400039c1  mov     ebx, eax
0x1400039c3  test    rcx, rcx
0x1400039c6  jz      short loc_1400039D7
0x1400039c8  call    cs:__imp_RegCloseKey
0x1400039ce  mov     [rsp+1C0h+var_160], 0
0x1400039d7  mov     rcx, [rsp+1C0h+var_170]; hKey
0x1400039dc  test    rcx, rcx
0x1400039df  jz      short loc_1400039F0
0x1400039e1  call    cs:__imp_RegCloseKey
0x1400039e7  mov     [rsp+1C0h+var_170], 0
0x1400039f0  lea     rcx, [rsp+1C0h+var_150]
0x1400039f5  call    FreeGlobalData
0x1400039fa  lea     rcx, [rbp+0C0h+var_B0]
0x1400039fe  call    FreeGlobalData
0x140003a03  xor     eax, eax
0x140003a05  test    ebx, ebx
0x140003a07  setnz   al
0x140003a0a  jmp     short loc_140003A2E
0x140003a0c  mov     ecx, 57h ; 'W'; dwErrCode
0x140003a11  call    cs:__imp_SetLastError
0x140003a17  mov     ecx, 2; Ix
0x140003a1c  call    _o___acrt_iob_func_0
0x140003a21  mov     rcx, rax
0x140003a24  call    ShowLastError
0x140003a29  mov     eax, 1
0x140003a2e  mov     rcx, [rbp+0C0h+var_10]
0x140003a35  xor     rcx, rsp; StackCookie
0x140003a38  call    __security_check_cookie
0x140003a3d  lea     r11, [rsp+1C0h+var_s0]
0x140003a45  mov     rbx, [r11+20h]
0x140003a49  mov     rdi, [r11+28h]
0x140003a4d  mov     rsp, r11
0x140003a50  pop     rbp
0x140003a51  retn
```
