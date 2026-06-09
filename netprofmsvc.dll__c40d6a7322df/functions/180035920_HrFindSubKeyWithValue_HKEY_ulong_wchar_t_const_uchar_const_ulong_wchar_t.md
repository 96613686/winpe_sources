# HrFindSubKeyWithValue(HKEY__ *,ulong *,wchar_t const *,uchar const *,ulong,wchar_t * *)

- ea: `0x180035920`
- end: `0x180035c6b`
- name: `?HrFindSubKeyWithValue@@YAJPEAUHKEY__@@PEAKPEB_WPEBEKPEAPEA_W@Z`
- size: `843`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, unsigned int *@<rdx>, const wchar_t *@<r8>, const unsigned __int8 *@<r9>, unsigned int, wchar_t **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180035728`
- `0x180035810`

## callees

- `0x180035920`
- `0x1800a88a0`
- `0x1800aba19`
- `0x1800aba25`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180035b2f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180035b2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800359e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035ad0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800359e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035ad0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035c52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035c60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035c52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035c60`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800359c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800359c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035aa7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035c28`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035aa7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035c28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035b4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035b4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035a68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035a68`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180035a3f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180035a3f`

## pseudocode

```c
__int64 __fastcall HrFindSubKeyWithValue(
        HKEY hKey,
        unsigned int *a2,
        const wchar_t *a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        wchar_t **a6)
{
  BYTE *v7; // r12
  HKEY v8; // r14
  LSTATUS v9; // edi
  SIZE_T v10; // rcx
  WCHAR *v11; // rbx
  BOOL v12; // eax
  DWORD v13; // esi
  LSTATUS v14; // r15d
  HKEY v15; // r13
  LSTATUS v16; // eax
  unsigned int v17; // r14d
  signed int v18; // edi
  BYTE *v19; // rax
  BYTE *v20; // rsi
  DWORD v21; // r14d
  LSTATUS v23; // eax
  BOOL v24; // [rsp+60h] [rbp-A0h]
  DWORD v25; // [rsp+64h] [rbp-9Ch]
  DWORD cbData; // [rsp+88h] [rbp-78h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+8Ch] [rbp-74h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  DWORD Type; // [rsp+98h] [rbp-68h] BYREF
  DWORD cchName; // [rsp+9Ch] [rbp-64h] BYREF
  BYTE Data[208]; // [rsp+A0h] [rbp-60h] BYREF

  *a6 = 0;
  v7 = 0;
  v8 = hKey;
  cbMaxSubKeyLen = 0;
  Type = 0;
  phkResult = 0;
  cchName = 0;
  v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v9 )
    goto LABEL_31;
  v10 = 2LL * ++cbMaxSubKeyLen;
  v11 = (WCHAR *)CoTaskMemAlloc(v10);
  if ( !v11 )
  {
    LOWORD(v9) = 8;
    return (unsigned __int16)v9 | 0x80070000;
  }
  v12 = 0;
  v13 = *a2;
  v24 = 0;
  v25 = *a2;
  do
  {
    if ( v12 )
      goto LABEL_30;
    cchName = cbMaxSubKeyLen;
    v14 = RegEnumKeyExW(v8, v13, v11, &cchName, 0, 0, 0, 0);
    if ( !v14 )
    {
      v14 = RegOpenKeyExW(v8, v11, 0, 0x20019u, &phkResult);
      if ( !v14 )
      {
        v15 = phkResult;
        cbData = 200;
        v16 = RegQueryValueExW(phkResult, L"ProfileGuid", 0, &Type, Data, &cbData);
        v17 = v16;
        if ( v16 > 0 )
          v17 = (unsigned __int16)v16 | 0x80070000;
        v18 = 0;
        if ( v17 != -2147024662 )
          v18 = v17;
        if ( v18 )
        {
          v21 = 0;
LABEL_18:
          if ( v18 >= 0 )
          {
            if ( v21 == 78 )
            {
              if ( Type == 1 )
                v24 = _o__wcsnicmp(v7, a4, 39) == 0;
              else
                v24 = memcmp_0(v7, a4, 0x4Eu) == 0;
            }
            CoTaskMemFree(v7);
          }
          goto LABEL_23;
        }
        v19 = (BYTE *)CoTaskMemAlloc(cbData);
        v20 = v19;
        if ( !v19 )
        {
LABEL_23:
          RegCloseKey(phkResult);
          v13 = v25;
          v7 = 0;
          v8 = hKey;
          goto LABEL_24;
        }
        if ( v17 == -2147024662 )
        {
          v23 = RegQueryValueExW(v15, L"ProfileGuid", 0, &Type, v19, &cbData);
          v18 = v23;
          if ( v23 > 0 )
            v18 = (unsigned __int16)v23 | 0x80070000;
          if ( v18 )
          {
            v21 = 0;
LABEL_16:
            if ( v20 )
              CoTaskMemFree(v20);
            goto LABEL_18;
          }
        }
        else
        {
          memcpy_0(v19, Data, cbData);
        }
        v21 = cbData;
        v7 = v20;
        v20 = 0;
        goto LABEL_16;
      }
    }
LABEL_24:
    v12 = v24;
    v9 = 0;
    if ( v14 != 234 )
      v9 = v14;
    if ( !v24 )
      v25 = ++v13;
  }
  while ( !v9 );
  if ( v24 )
  {
LABEL_30:
    *a6 = v11;
    *a2 = v13;
    goto LABEL_31;
  }
  CoTaskMemFree(v11);
LABEL_31:
  if ( v9 <= 0 )
    return (unsigned int)v9;
  return (unsigned __int16)v9 | 0x80070000;
}

```

## disassembly

```asm
0x180035920  push    rbp
0x180035922  push    rbx
0x180035923  push    rdi
0x180035924  push    r12
0x180035926  push    r13
0x180035928  push    r14
0x18003592a  lea     rbp, [rsp-88h]
0x180035932  sub     rsp, 188h
0x180035939  mov     rax, cs:__security_cookie
0x180035940  xor     rax, rsp
0x180035943  mov     [rbp+0B0h+var_40], rax
0x180035947  mov     r12, [rbp+0B0h+arg_28]
0x18003594e  lea     rax, [rbp+0B0h+cbMaxSubKeyLen]
0x180035952  mov     [rsp+1B0h+Buf2], r9
0x180035957  mov     r13, rdx
0x18003595a  mov     [rbp+0B0h+var_130], rdx
0x18003595e  xor     r9d, r9d; lpReserved
0x180035961  mov     [rsp+1B0h+var_138], r12
0x180035966  xor     r8d, r8d; lpcchClass
0x180035969  mov     qword ptr [r12], 0
0x180035971  xor     edx, edx; lpClass
0x180035973  xor     r12d, r12d
0x180035976  mov     [rsp+1B0h+var_140], rcx
0x18003597b  mov     [rsp+1B0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180035980  mov     r14, rcx
0x180035983  mov     [rsp+1B0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180035988  mov     [rsp+1B0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18003598d  mov     [rsp+1B0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180035992  mov     [rsp+1B0h+lpcValues], r12; lpcValues
0x180035997  mov     [rsp+1B0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18003599c  mov     [rsp+1B0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800359a1  mov     [rsp+1B0h+lpcSubKeys], r12; lpcSubKeys
0x1800359a6  mov     [rbp+0B0h+cbMaxSubKeyLen], 0
0x1800359ad  mov     [rbp+0B0h+Type], 0
0x1800359b4  mov     [rbp+0B0h+phkResult], 0
0x1800359bc  mov     [rbp+0B0h+cchName], 0
0x1800359c3  call    cs:__imp_RegQueryInfoKeyW
0x1800359c9  mov     edi, eax
0x1800359cb  test    eax, eax
0x1800359cd  jnz     loc_180035BAA
0x1800359d3  mov     eax, [rbp+0B0h+cbMaxSubKeyLen]
0x1800359d6  inc     eax
0x1800359d8  mov     ecx, eax
0x1800359da  add     rcx, rcx; cb
0x1800359dd  mov     [rbp+0B0h+cbMaxSubKeyLen], eax
0x1800359e0  call    cs:__imp_CoTaskMemAlloc
0x1800359e6  mov     rbx, rax
0x1800359e9  test    rax, rax
0x1800359ec  jz      loc_180035BFA
0x1800359f2  mov     [rsp+1B0h+arg_10], rsi
0x1800359fa  mov     eax, r12d
0x1800359fd  mov     esi, [r13+0]
0x180035a01  mov     [rsp+1B0h+var_150], eax
0x180035a05  mov     [rsp+1B0h+var_14C], esi
0x180035a09  mov     [rsp+1B0h+var_30], r15
0x180035a11  test    eax, eax
0x180035a13  jnz     loc_180035B8C
0x180035a19  mov     eax, [rbp+0B0h+cbMaxSubKeyLen]
0x180035a1c  lea     r9, [rbp+0B0h+cchName]; lpcchName
0x180035a20  mov     [rsp+1B0h+lpcValues], r12; lpftLastWriteTime
0x180035a25  mov     r8, rbx; lpName
0x180035a28  mov     [rsp+1B0h+lpcbMaxClassLen], r12; lpcchClass
0x180035a2d  mov     edx, esi; dwIndex
0x180035a2f  mov     [rsp+1B0h+lpcbMaxSubKeyLen], r12; lpClass
0x180035a34  mov     rcx, r14; hKey
0x180035a37  mov     [rsp+1B0h+lpcSubKeys], r12; lpReserved
0x180035a3c  mov     [rbp+0B0h+cchName], eax
0x180035a3f  call    cs:__imp_RegEnumKeyExW
0x180035a45  mov     r15d, eax
0x180035a48  test    eax, eax
0x180035a4a  jnz     loc_180035B60
0x180035a50  lea     rax, [rbp+0B0h+phkResult]
0x180035a54  mov     r9d, 20019h; samDesired
0x180035a5a  xor     r8d, r8d; ulOptions
0x180035a5d  mov     [rsp+1B0h+lpcSubKeys], rax; phkResult
0x180035a62  mov     rdx, rbx; lpSubKey
0x180035a65  mov     rcx, r14; hKey
0x180035a68  call    cs:__imp_RegOpenKeyExW
0x180035a6e  mov     r15d, eax
0x180035a71  test    eax, eax
0x180035a73  jnz     loc_180035B60
0x180035a79  mov     r13, [rbp+0B0h+phkResult]
0x180035a7d  lea     rax, [rbp+0B0h+cbData]
0x180035a81  mov     [rsp+1B0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180035a86  lea     r9, [rbp+0B0h+Type]; lpType
0x180035a8a  lea     rax, [rbp+0B0h+Data]
0x180035a8e  mov     [rbp+0B0h+cbData], 0C8h
0x180035a95  xor     r8d, r8d; lpReserved
0x180035a98  mov     [rsp+1B0h+lpcSubKeys], rax; lpData
0x180035a9d  lea     rdx, aProfileguid; "ProfileGuid"
0x180035aa4  mov     rcx, r13; hKey
0x180035aa7  call    cs:__imp_RegQueryValueExW
0x180035aad  mov     r14d, eax
0x180035ab0  test    eax, eax
0x180035ab2  jg      loc_180035BD5
0x180035ab8  xor     edi, edi
0x180035aba  cmp     r14d, 800700EAh
0x180035ac1  cmovnz  edi, r14d
0x180035ac5  test    edi, edi
0x180035ac7  jnz     loc_180035BCD
0x180035acd  mov     ecx, [rbp+0B0h+cbData]; cb
0x180035ad0  call    cs:__imp_CoTaskMemAlloc
0x180035ad6  mov     rsi, rax
0x180035ad9  test    rax, rax
0x180035adc  jz      short loc_180035B4A
0x180035ade  cmp     r14d, 800700EAh
0x180035ae5  jz      loc_180035C09
0x180035aeb  mov     r8d, [rbp+0B0h+cbData]; Size
0x180035aef  lea     rdx, [rbp+0B0h+Data]; Src
0x180035af3  mov     rcx, rax; void *
0x180035af6  call    memcpy_0
0x180035afb  mov     r14d, [rbp+0B0h+cbData]
0x180035aff  mov     r12, rsi
0x180035b02  xor     esi, esi
0x180035b04  test    rsi, rsi
0x180035b07  jnz     loc_180035C4F
0x180035b0d  test    edi, edi
0x180035b0f  js      short loc_180035B4A
0x180035b11  cmp     r14d, 4Eh ; 'N'
0x180035b15  jnz     short loc_180035B41
0x180035b17  cmp     [rbp+0B0h+Type], 1
0x180035b1b  mov     rcx, r12; Buf1
0x180035b1e  mov     rdx, [rsp+1B0h+Buf2]; Buf2
0x180035b23  mov     r8d, r14d; Size
0x180035b26  jnz     loc_180035BE5
0x180035b2c  shr     r8, 1
0x180035b2f  call    cs:__imp__o__wcsnicmp
0x180035b35  xor     edi, edi
0x180035b37  test    eax, eax
0x180035b39  setz    dil
0x180035b3d  mov     [rsp+1B0h+var_150], edi
0x180035b41  mov     rcx, r12; pv
0x180035b44  call    cs:__imp_CoTaskMemFree
0x180035b4a  mov     rcx, [rbp+0B0h+phkResult]; hKey
0x180035b4e  call    cs:__imp_RegCloseKey
0x180035b54  mov     esi, [rsp+1B0h+var_14C]
0x180035b58  xor     r12d, r12d
0x180035b5b  mov     r14, [rsp+1B0h+var_140]
0x180035b60  mov     eax, [rsp+1B0h+var_150]
0x180035b64  cmp     r15d, 0EAh
0x180035b6b  mov     edi, r12d
0x180035b6e  cmovnz  edi, r15d
0x180035b72  test    eax, eax
0x180035b74  jnz     short loc_180035B7C
0x180035b76  inc     esi
0x180035b78  mov     [rsp+1B0h+var_14C], esi
0x180035b7c  test    edi, edi
0x180035b7e  jz      loc_180035A11
0x180035b84  test    eax, eax
0x180035b86  jz      loc_180035C5D
0x180035b8c  mov     rax, [rsp+1B0h+var_138]
0x180035b91  mov     [rax], rbx
0x180035b94  mov     rax, [rbp+0B0h+var_130]
0x180035b98  mov     [rax], esi
0x180035b9a  mov     r15, [rsp+1B0h+var_30]
0x180035ba2  mov     rsi, [rsp+1B0h+arg_10]
0x180035baa  test    edi, edi
0x180035bac  jg      short loc_180035BFF
0x180035bae  mov     eax, edi
0x180035bb0  mov     rcx, [rbp+0B0h+var_40]
0x180035bb4  xor     rcx, rsp; StackCookie
0x180035bb7  call    __security_check_cookie
0x180035bbc  add     rsp, 188h
0x180035bc3  pop     r14
0x180035bc5  pop     r13
0x180035bc7  pop     r12
0x180035bc9  pop     rdi
0x180035bca  pop     rbx
0x180035bcb  pop     rbp
0x180035bcc  retn
0x180035bcd  xor     r14d, r14d
0x180035bd0  jmp     loc_180035B0D
0x180035bd5  movzx   r14d, ax
0x180035bd9  or      r14d, 80070000h
0x180035be0  jmp     loc_180035AB8
0x180035be5  call    memcmp_0
0x180035bea  xor     ecx, ecx
0x180035bec  test    eax, eax
0x180035bee  setz    cl
0x180035bf1  mov     [rsp+1B0h+var_150], ecx
0x180035bf5  jmp     loc_180035B41
0x180035bfa  mov     edi, 8
0x180035bff  movzx   eax, di
0x180035c02  or      eax, 80070000h
0x180035c07  jmp     short loc_180035BB0
0x180035c09  lea     rax, [rbp+0B0h+cbData]
0x180035c0d  xor     r8d, r8d; lpReserved
0x180035c10  mov     [rsp+1B0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180035c15  lea     r9, [rbp+0B0h+Type]; lpType
0x180035c19  lea     rdx, aProfileguid; "ProfileGuid"
0x180035c20  mov     [rsp+1B0h+lpcSubKeys], rsi; lpData
0x180035c25  mov     rcx, r13; hKey
0x180035c28  call    cs:__imp_RegQueryValueExW
0x180035c2e  mov     edi, eax
0x180035c30  test    eax, eax
0x180035c32  jg      short loc_180035C44
0x180035c34  test    edi, edi
0x180035c36  jz      loc_180035AFB
0x180035c3c  xor     r14d, r14d
0x180035c3f  jmp     loc_180035B04
0x180035c44  movzx   edi, ax
0x180035c47  or      edi, 80070000h
0x180035c4d  jmp     short loc_180035C34
0x180035c4f  mov     rcx, rsi; pv
0x180035c52  call    cs:__imp_CoTaskMemFree
0x180035c58  jmp     loc_180035B0D
0x180035c5d  mov     rcx, rbx; pv
0x180035c60  call    cs:__imp_CoTaskMemFree
0x180035c66  jmp     loc_180035B9A
```
