# FindRegisteredInfo(ushort const *,ushort const *,ushort * *,ushort * *)

- ea: `0x1800129e8`
- end: `0x180012be5`
- name: `?FindRegisteredInfo@@YAJPEBG0PEAPEAG1@Z`
- size: `509`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800105a0`

## callees

- `0x180012674`
- `0x1800129e8`
- `0x1800132fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012ba6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012bb5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012bc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012ba6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012bb5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012bc4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012a81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012af2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012b17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012a81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012af2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012b17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b97`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FindRegisteredInfo(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  WCHAR *v4; // rdi
  unsigned __int16 *v5; // rsi
  unsigned __int16 *v6; // r14
  signed int v9; // ebx
  LSTATUS v10; // eax
  bool v11; // cc
  int StringValue; // eax
  HKEY v14; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int16 *v15; // [rsp+38h] [rbp-28h] BYREF
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  unsigned __int16 *v20; // [rsp+A0h] [rbp+40h] BYREF

  v4 = 0;
  phkResult = 0;
  v5 = 0;
  hKey = 0;
  v6 = 0;
  v14 = 0;
  hMem = 0;
  lpSubKey = 0;
  v20 = 0;
  v15 = 0;
  if ( !a3 || !a4 )
  {
    v9 = -2147024809;
    goto LABEL_18;
  }
  v9 = CombineCTAndAppId(a1, a2, (unsigned __int16 **)&hMem);
  if ( v9 >= 0 )
  {
    v10 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\PushRouter\\Registrations\\ByCTAndAppId",
            0,
            0x20019u,
            &phkResult);
    v9 = v10;
    v11 = v10 <= 0;
    if ( v10 )
      goto LABEL_6;
    StringValue = QueryStringValue(phkResult, (const unsigned __int16 *)hMem, 0, (unsigned __int16 **)&lpSubKey);
    v4 = (WCHAR *)lpSubKey;
    v9 = StringValue;
    if ( StringValue < 0 )
      goto LABEL_18;
    if ( !lpSubKey )
    {
      v9 = -2147024882;
      goto LABEL_18;
    }
    v10 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\PushRouter\\Registrations\\ByGenericId",
            0,
            0x20019u,
            &hKey);
    v9 = v10;
    v11 = v10 <= 0;
    if ( v10 || (v10 = RegOpenKeyExW(hKey, v4, 0, 0x20019u, &v14), v9 = v10, v11 = v10 <= 0, v10) )
    {
LABEL_6:
      if ( !v11 )
        v9 = (unsigned __int16)v10 | 0x80070000;
    }
    else
    {
      v9 = QueryStringValue(v14, 0, L"AppId", &v20);
      if ( v9 >= 0 )
      {
        v9 = QueryStringValue(v14, 0, L"ContentTypes", &v15);
        if ( v9 >= 0 )
        {
          *a4 = v20;
          *a3 = v15;
          goto LABEL_18;
        }
        v6 = v15;
      }
      v5 = v20;
    }
  }
LABEL_18:
  LocalFree(hMem);
  LocalFree(v4);
  LocalFree(v5);
  LocalFree(v6);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v14 )
    RegCloseKey(v14);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800129e8  mov     [rsp-28h+arg_0], rbx
0x1800129ed  mov     [rsp-28h+arg_8], rsi
0x1800129f2  push    rbp
0x1800129f3  push    rdi
0x1800129f4  push    r12
0x1800129f6  push    r14
0x1800129f8  push    r15
0x1800129fa  mov     rbp, rsp
0x1800129fd  sub     rsp, 60h
0x180012a01  xor     edi, edi
0x180012a03  mov     [rbp+var_10], 0
0x180012a0b  xor     esi, esi
0x180012a0d  mov     [rbp+hKey], 0
0x180012a15  xor     r14d, r14d
0x180012a18  mov     [rbp+var_30], 0
0x180012a20  mov     [rbp+hMem], 0
0x180012a28  mov     r15, r9
0x180012a2b  mov     [rbp+lpSubKey], rdi
0x180012a2f  mov     r12, r8
0x180012a32  mov     [rbp+arg_10], rsi
0x180012a36  mov     [rbp+var_28], r14
0x180012a3a  test    r8, r8
0x180012a3d  jnz     short loc_180012A49
0x180012a3f  mov     ebx, 80070057h
0x180012a44  jmp     loc_180012B78
0x180012a49  test    r15, r15
0x180012a4c  jz      short loc_180012A3F
0x180012a4e  lea     r8, [rbp+hMem]; unsigned __int16 **
0x180012a52  call    ?CombineCTAndAppId@@YAJPEBG0PEAPEAG@Z; CombineCTAndAppId(ushort const *,ushort const *,ushort * *)
0x180012a57  mov     ebx, eax
0x180012a59  test    eax, eax
0x180012a5b  js      loc_180012B78
0x180012a61  lea     rax, [rbp+var_10]
0x180012a65  mov     r9d, 20019h; samDesired
0x180012a6b  xor     r8d, r8d; ulOptions
0x180012a6e  mov     [rsp+60h+phkResult], rax; phkResult
0x180012a73  lea     rdx, ?c_szAppRegistrationByCTAndAppId@@3QBGB; "Software\\Microsoft\\PushRouter\\Regist"...
0x180012a7a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012a81  call    cs:__imp_RegOpenKeyExW
0x180012a87  mov     ebx, eax
0x180012a89  test    eax, eax
0x180012a8b  jz      short loc_180012AA1
0x180012a8d  jle     loc_180012B78
0x180012a93  movzx   ebx, ax
0x180012a96  or      ebx, 80070000h
0x180012a9c  jmp     loc_180012B78
0x180012aa1  mov     rdx, [rbp+hMem]; unsigned __int16 *
0x180012aa5  lea     r9, [rbp+lpSubKey]; unsigned __int16 **
0x180012aa9  mov     rcx, [rbp+var_10]; HKEY
0x180012aad  xor     r8d, r8d; unsigned __int16 *
0x180012ab0  call    ?QueryStringValue@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; QueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180012ab5  mov     rdi, [rbp+lpSubKey]
0x180012ab9  mov     ebx, eax
0x180012abb  test    eax, eax
0x180012abd  js      loc_180012B78
0x180012ac3  test    rdi, rdi
0x180012ac6  jnz     short loc_180012AD2
0x180012ac8  mov     ebx, 8007000Eh
0x180012acd  jmp     loc_180012B78
0x180012ad2  lea     rax, [rbp+hKey]
0x180012ad6  mov     r9d, 20019h; samDesired
0x180012adc  xor     r8d, r8d; ulOptions
0x180012adf  mov     [rsp+60h+phkResult], rax; phkResult
0x180012ae4  lea     rdx, ?c_szAppRegistrationByGenId@@3QBGB; "Software\\Microsoft\\PushRouter\\Regist"...
0x180012aeb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012af2  call    cs:__imp_RegOpenKeyExW
0x180012af8  mov     ebx, eax
0x180012afa  test    eax, eax
0x180012afc  jnz     short loc_180012A8D
0x180012afe  mov     rcx, [rbp+hKey]; hKey
0x180012b02  lea     rax, [rbp+var_30]
0x180012b06  mov     r9d, 20019h; samDesired
0x180012b0c  mov     [rsp+60h+phkResult], rax; phkResult
0x180012b11  xor     r8d, r8d; ulOptions
0x180012b14  mov     rdx, rdi; lpSubKey
0x180012b17  call    cs:__imp_RegOpenKeyExW
0x180012b1d  mov     ebx, eax
0x180012b1f  test    eax, eax
0x180012b21  jnz     loc_180012A8D
0x180012b27  mov     rcx, [rbp+var_30]; HKEY
0x180012b2b  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x180012b2f  lea     r8, aAppid; "AppId"
0x180012b36  xor     edx, edx; unsigned __int16 *
0x180012b38  call    ?QueryStringValue@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; QueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180012b3d  mov     ebx, eax
0x180012b3f  test    eax, eax
0x180012b41  js      short loc_180012B74
0x180012b43  mov     rcx, [rbp+var_30]; HKEY
0x180012b47  lea     r9, [rbp+var_28]; unsigned __int16 **
0x180012b4b  lea     r8, ?c_szContentTypes@@3QBGB; "ContentTypes"
0x180012b52  xor     edx, edx; unsigned __int16 *
0x180012b54  call    ?QueryStringValue@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; QueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180012b59  mov     ebx, eax
0x180012b5b  test    eax, eax
0x180012b5d  js      short loc_180012B70
0x180012b5f  mov     rax, [rbp+arg_10]
0x180012b63  mov     [r15], rax
0x180012b66  mov     rax, [rbp+var_28]
0x180012b6a  mov     [r12], rax
0x180012b6e  jmp     short loc_180012B78
0x180012b70  mov     r14, [rbp+var_28]
0x180012b74  mov     rsi, [rbp+arg_10]
0x180012b78  mov     rcx, [rbp+hMem]; hMem
0x180012b7c  call    cs:__imp_LocalFree
0x180012b82  mov     rcx, rdi; hMem
0x180012b85  call    cs:__imp_LocalFree
0x180012b8b  mov     rcx, rsi; hMem
0x180012b8e  call    cs:__imp_LocalFree
0x180012b94  mov     rcx, r14; hMem
0x180012b97  call    cs:__imp_LocalFree
0x180012b9d  mov     rcx, [rbp+var_10]; hKey
0x180012ba1  test    rcx, rcx
0x180012ba4  jz      short loc_180012BAC
0x180012ba6  call    cs:__imp_RegCloseKey
0x180012bac  mov     rcx, [rbp+hKey]; hKey
0x180012bb0  test    rcx, rcx
0x180012bb3  jz      short loc_180012BBB
0x180012bb5  call    cs:__imp_RegCloseKey
0x180012bbb  mov     rcx, [rbp+var_30]; hKey
0x180012bbf  test    rcx, rcx
0x180012bc2  jz      short loc_180012BCA
0x180012bc4  call    cs:__imp_RegCloseKey
0x180012bca  lea     r11, [rsp+60h+var_s0]
0x180012bcf  mov     eax, ebx
0x180012bd1  mov     rbx, [r11+30h]
0x180012bd5  mov     rsi, [r11+38h]
0x180012bd9  mov     rsp, r11
0x180012bdc  pop     r15
0x180012bde  pop     r14
0x180012be0  pop     r12
0x180012be2  pop     rdi
0x180012be3  pop     rbp
0x180012be4  retn
```
