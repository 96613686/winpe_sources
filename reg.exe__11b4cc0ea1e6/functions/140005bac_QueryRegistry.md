# QueryRegistry

- ea: `0x140005bac`
- end: `0x140005e7c`
- name: `QueryRegistry`
- size: `720`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config`

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
- `0x140004bbc`
- `0x1400055f8`
- `0x140005940`
- `0x140005bac`
- `0x140005e84`
- `0x14000c894`
- `0x14000cd48`
- `0x14000dbe8`
- `0x14000dc24`
- `0x14000dce0`
- `0x14000e020`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140005c97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140005c97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005e2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005e2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005e3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005e3b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140005d21`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140005d21`

## pseudocode

```c
__int64 __fastcall QueryRegistry(unsigned int a1, __int64 a2)
{
  FILE *v4; // rax
  unsigned int v5; // esi
  __int64 v6; // rcx
  unsigned int v7; // eax
  FILE *v8; // rax
  FILE *v10; // rax
  BOOL v11; // ebx
  __int64 v12; // rcx
  int EnumKeys; // edi
  FILE *v14; // rax
  BOOL v15; // r14d
  int v16; // edi
  const wchar_t *ResString2FromModule; // rbx
  FILE *v18; // rax
  FILE *v19; // rax
  FILE *v20; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-99h]
  int v22; // [rsp+30h] [rbp-89h] BYREF
  HKEY hkey; // [rsp+38h] [rbp-81h] BYREF
  _BYTE v24[4]; // [rsp+40h] [rbp-79h] BYREF
  int v25; // [rsp+44h] [rbp-75h]
  HKEY hKey; // [rsp+48h] [rbp-71h]
  int v27; // [rsp+60h] [rbp-59h]
  LPCWSTR lpSubKey; // [rsp+90h] [rbp-29h]
  const WCHAR *v29; // [rsp+98h] [rbp-21h]
  LPCWSTR lpString; // [rsp+A0h] [rbp-19h]
  __int64 v31; // [rsp+B8h] [rbp-1h]
  __int64 v32; // [rsp+C0h] [rbp+7h]
  int v33; // [rsp+CCh] [rbp+13h]
  _DWORD v34[6]; // [rsp+E0h] [rbp+27h] BYREF

  hkey = 0;
  v22 = 0;
  v25 = 0;
  memset_0(v24, 0, 0x94u);
  if ( a1 && a2 )
  {
    InitGlobalData(0, v24);
    if ( !(unsigned int)ParseQueryCmdLine(a1, a2, v24, &v22) )
    {
      v4 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v4);
      v5 = 1;
LABEL_12:
      FreeGlobalData(v24);
      return v5;
    }
    v5 = 1;
    if ( v22 == 1 )
    {
      Usage(0);
      v5 = 0;
      goto LABEL_12;
    }
    if ( !(unsigned int)RegConnectMachine(v24) )
    {
      v6 = 0xFFFFFFFFLL;
LABEL_11:
      SaveErrorMessage(v6);
      v8 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v8);
      goto LABEL_12;
    }
    v7 = RegOpenKeyExW(hKey, lpSubKey, 0, v33 | 0x20019, &hkey);
    if ( v7 )
    {
      v6 = v7;
      goto LABEL_11;
    }
    v10 = o___acrt_iob_func_0(1u);
    ShowMessage(v10, L"\n");
    *(_OWORD *)&v34[1] = 0;
    if ( v31 || !lpString || v32 || v27 )
    {
      v34[0] = 1;
      EnumKeys = QueryEnumKeys(hkey, v29, (__int64)v24, v34);
      v11 = v31 || lpString || v32;
    }
    else
    {
      v34[0] = 1;
      if ( !lstrlenW(lpString) || (unsigned int)FindOneOf2(lpString) == -1 )
      {
        EnumKeys = QueryValue(hkey, (__int64)v29, lpString, (__int64)v24, v34);
        v11 = 0;
        v14 = o___acrt_iob_func_0(1u);
        ShowMessage(v14, L"\n");
      }
      else
      {
        v11 = 1;
        EnumKeys = QueryEnumValues(hkey, (__int64)v29, (__int64)v24, v34);
      }
    }
    if ( EnumKeys )
    {
      v15 = 1;
      v19 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v19);
    }
    else
    {
      v15 = 0;
      if ( v11 )
      {
        v16 = v34[4];
        v15 = v34[4] == 0;
        ResString2FromModule = (const wchar_t *)GetResString2FromModule(v12, 521, 0);
        v18 = o___acrt_iob_func_0(1u);
        LODWORD(phkResult) = v16;
        ShowMessageEx(v18, 1, 1, ResString2FromModule, phkResult);
      }
    }
    if ( hkey )
      RegCloseKey(hkey);
    return v15;
  }
  else
  {
    SetLastError(0x57u);
    v20 = o___acrt_iob_func_0(2u);
    ShowLastError(v20);
    return 1;
  }
}

```

## disassembly

```asm
0x140005bac  mov     [rsp-8+arg_10], rbx
0x140005bb1  mov     [rsp-8+arg_18], rsi
0x140005bb6  push    rbp
0x140005bb7  push    rdi
0x140005bb8  push    r14
0x140005bba  lea     rbp, [rsp-47h]
0x140005bbf  sub     rsp, 100h
0x140005bc6  mov     rax, cs:__security_cookie
0x140005bcd  xor     rax, rsp
0x140005bd0  mov     [rbp+57h+var_18], rax
0x140005bd4  mov     rbx, rdx
0x140005bd7  mov     [rsp+110h+hkey], 0
0x140005be0  mov     edi, ecx
0x140005be2  mov     [rsp+110h+var_E0], 0
0x140005bea  xor     eax, eax
0x140005bec  lea     rcx, [rbp+57h+var_D0]; void *
0x140005bf0  xor     edx, edx; Val
0x140005bf2  mov     [rbp+57h+var_CC], eax
0x140005bf5  mov     r8d, 94h; Size
0x140005bfb  call    memset_0
0x140005c00  test    edi, edi
0x140005c02  jz      loc_140005E36
0x140005c08  test    rbx, rbx
0x140005c0b  jz      loc_140005E36
0x140005c11  lea     rdx, [rbp+57h+var_D0]
0x140005c15  xor     ecx, ecx
0x140005c17  call    InitGlobalData
0x140005c1c  lea     r9, [rsp+110h+var_E0]
0x140005c21  mov     rdx, rbx
0x140005c24  lea     r8, [rbp+57h+var_D0]
0x140005c28  mov     ecx, edi
0x140005c2a  call    ParseQueryCmdLine
0x140005c2f  test    eax, eax
0x140005c31  jnz     short loc_140005C4F
0x140005c33  lea     ecx, [rax+2]; Ix
0x140005c36  call    _o___acrt_iob_func_0
0x140005c3b  mov     rcx, rax
0x140005c3e  mov     edx, 20000h
0x140005c43  call    ShowLastErrorEx
0x140005c48  mov     esi, 1
0x140005c4d  jmp     short loc_140005CBF
0x140005c4f  mov     esi, 1
0x140005c54  cmp     [rsp+110h+var_E0], esi
0x140005c58  jnz     short loc_140005C65
0x140005c5a  xor     ecx, ecx
0x140005c5c  call    Usage
0x140005c61  xor     esi, esi
0x140005c63  jmp     short loc_140005CBF
0x140005c65  lea     rcx, [rbp+57h+var_D0]
0x140005c69  call    RegConnectMachine
0x140005c6e  test    eax, eax
0x140005c70  jnz     short loc_140005C77
0x140005c72  or      ecx, 0FFFFFFFFh
0x140005c75  jmp     short loc_140005CA3
0x140005c77  mov     r9d, [rbp+57h+var_44]
0x140005c7b  lea     rax, [rsp+110h+hkey]
0x140005c80  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x140005c84  or      r9d, 20019h; samDesired
0x140005c8b  mov     rcx, [rbp+57h+hKey]; hKey
0x140005c8f  xor     r8d, r8d; ulOptions
0x140005c92  mov     [rsp+110h+phkResult], rax; phkResult
0x140005c97  call    cs:__imp_RegOpenKeyExW
0x140005c9d  test    eax, eax
0x140005c9f  jz      short loc_140005CCF
0x140005ca1  mov     ecx, eax
0x140005ca3  call    SaveErrorMessage
0x140005ca8  mov     ecx, 2; Ix
0x140005cad  call    _o___acrt_iob_func_0
0x140005cb2  mov     edx, 20001h
0x140005cb7  mov     rcx, rax
0x140005cba  call    ShowLastErrorEx
0x140005cbf  lea     rcx, [rbp+57h+var_D0]
0x140005cc3  call    FreeGlobalData
0x140005cc8  mov     eax, esi
0x140005cca  jmp     loc_140005E58
0x140005ccf  mov     ecx, esi; Ix
0x140005cd1  call    _o___acrt_iob_func_0
0x140005cd6  mov     rcx, rax; Stream
0x140005cd9  lea     rdx, asc_140010950; "\n"
0x140005ce0  call    ShowMessage
0x140005ce5  cmp     [rbp+57h+var_58], 0
0x140005cea  xorps   xmm0, xmm0
0x140005ced  movdqu  xmmword ptr [rbp+57h+var_30+4], xmm0
0x140005cf2  jnz     loc_140005D90
0x140005cf8  mov     r8, [rbp+57h+lpString]
0x140005cfc  test    r8, r8
0x140005cff  jz      loc_140005D90
0x140005d05  cmp     [rbp+57h+var_50], 0
0x140005d0a  jnz     loc_140005D90
0x140005d10  cmp     [rbp+57h+var_B0], 0
0x140005d14  jnz     short loc_140005D90
0x140005d16  mov     [rbp+57h+var_30], esi
0x140005d19  test    r8, r8
0x140005d1c  jz      short loc_140005D59
0x140005d1e  mov     rcx, r8; lpString
0x140005d21  call    cs:__imp_lstrlenW
0x140005d27  test    eax, eax
0x140005d29  jz      short loc_140005D55
0x140005d2b  mov     rcx, [rbp+57h+lpString]; lpString
0x140005d2f  call    FindOneOf2
0x140005d34  cmp     eax, 0FFFFFFFFh
0x140005d37  jz      short loc_140005D55
0x140005d39  mov     rdx, [rbp+57h+var_78]
0x140005d3d  lea     r9, [rbp+57h+var_30]
0x140005d41  mov     rcx, [rsp+110h+hkey]; hKey
0x140005d46  lea     r8, [rbp+57h+var_D0]
0x140005d4a  mov     ebx, esi
0x140005d4c  call    QueryEnumValues
0x140005d51  mov     edi, eax
0x140005d53  jmp     short loc_140005DC6
0x140005d55  mov     r8, [rbp+57h+lpString]
0x140005d59  mov     rdx, [rbp+57h+var_78]
0x140005d5d  lea     rax, [rbp+57h+var_30]
0x140005d61  mov     rcx, [rsp+110h+hkey]; hkey
0x140005d66  lea     r9, [rbp+57h+var_D0]
0x140005d6a  mov     [rsp+110h+phkResult], rax; __int64
0x140005d6f  call    QueryValue
0x140005d74  mov     ecx, esi; Ix
0x140005d76  mov     edi, eax
0x140005d78  xor     ebx, ebx
0x140005d7a  call    _o___acrt_iob_func_0
0x140005d7f  mov     rcx, rax; Stream
0x140005d82  lea     rdx, asc_140010950; "\n"
0x140005d89  call    ShowMessage
0x140005d8e  jmp     short loc_140005DC6
0x140005d90  mov     rdx, [rbp+57h+var_78]
0x140005d94  lea     r9, [rbp+57h+var_30]
0x140005d98  mov     rcx, [rsp+110h+hkey]
0x140005d9d  lea     r8, [rbp+57h+var_D0]
0x140005da1  mov     [rbp+57h+var_30], esi
0x140005da4  call    QueryEnumKeys
0x140005da9  cmp     [rbp+57h+var_58], 0
0x140005dae  mov     edi, eax
0x140005db0  jnz     short loc_140005DC4
0x140005db2  cmp     [rbp+57h+lpString], 0
0x140005db7  jnz     short loc_140005DC4
0x140005db9  cmp     [rbp+57h+var_50], 0
0x140005dbe  jnz     short loc_140005DC4
0x140005dc0  xor     ebx, ebx
0x140005dc2  jmp     short loc_140005DC6
0x140005dc4  mov     ebx, esi
0x140005dc6  test    edi, edi
0x140005dc8  jnz     short loc_140005E07
0x140005dca  xor     r14d, r14d
0x140005dcd  test    ebx, ebx
0x140005dcf  jz      short loc_140005E21
0x140005dd1  mov     edi, [rbp+57h+var_30+10h]
0x140005dd4  mov     edx, 209h
0x140005dd9  test    edi, edi
0x140005ddb  cmovz   r14d, esi
0x140005ddf  xor     r8d, r8d
0x140005de2  call    GetResString2FromModule
0x140005de7  mov     ecx, esi; Ix
0x140005de9  mov     rbx, rax
0x140005dec  call    _o___acrt_iob_func_0
0x140005df1  mov     rcx, rax
0x140005df4  mov     dword ptr [rsp+110h+phkResult], edi
0x140005df8  mov     r9, rbx
0x140005dfb  mov     r8d, esi
0x140005dfe  mov     edx, esi
0x140005e00  call    ShowMessageEx
0x140005e05  jmp     short loc_140005E21
0x140005e07  mov     ecx, 2; Ix
0x140005e0c  mov     r14d, esi
0x140005e0f  call    _o___acrt_iob_func_0
0x140005e14  mov     rcx, rax
0x140005e17  mov     edx, 20001h
0x140005e1c  call    ShowLastErrorEx
0x140005e21  mov     rcx, [rsp+110h+hkey]; hKey
0x140005e26  test    rcx, rcx
0x140005e29  jz      short loc_140005E31
0x140005e2b  call    cs:__imp_RegCloseKey
0x140005e31  mov     eax, r14d
0x140005e34  jmp     short loc_140005E58
0x140005e36  mov     ecx, 57h ; 'W'; dwErrCode
0x140005e3b  call    cs:__imp_SetLastError
0x140005e41  mov     ecx, 2; Ix
0x140005e46  call    _o___acrt_iob_func_0
0x140005e4b  mov     rcx, rax
0x140005e4e  call    ShowLastError
0x140005e53  mov     eax, 1
0x140005e58  mov     rcx, [rbp+57h+var_18]
0x140005e5c  xor     rcx, rsp; StackCookie
0x140005e5f  call    __security_check_cookie
0x140005e64  lea     r11, [rsp+110h+var_10]
0x140005e6c  mov     rbx, [r11+30h]
0x140005e70  mov     rsi, [r11+38h]
0x140005e74  mov     rsp, r11
0x140005e77  pop     r14
0x140005e79  pop     rdi
0x140005e7a  pop     rbp
0x140005e7b  retn
```
