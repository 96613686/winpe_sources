# Microsoft::Windows::MDM::OmadmClient::Utilities::GetTestSettingString(ushort const *,ushort const *,ushort *,uint)

- ea: `0x1400538a0`
- end: `0x140053a11`
- name: `?GetTestSettingString@Utilities@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEBG0PEAGI@Z`
- size: `369`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::Utilities *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b0f4`
- `0x1400538a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005394b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005394b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400539c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400539c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140053903`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140053918`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140053971`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140053986`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400539e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400539fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140053903`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140053918`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140053971`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140053986`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400539e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400539fb`
- `dmEnrollEngine!__imp_OpenEnrollmentsHKEY` at `0x1400538d0`
- `dmEnrollEngine!__imp_OpenEnrollmentsHKEY` at `0x1400538d0`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::Utilities::GetTestSettingString(
        Microsoft::Windows::MDM::OmadmClient::Utilities *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *a4,
        unsigned int a5)
{
  int v8; // eax
  unsigned int v9; // edi
  LSTATUS v11; // eax
  unsigned int v12; // ebx
  bool v13; // cc
  int phkResult; // [rsp+20h] [rbp-30h]
  DWORD Type; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  HKEY v18[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  v18[0] = 0;
  hKey = 0;
  v8 = OpenEnrollmentsHKEY(131103, v18);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\utilities.cpp",
      (const char *)(unsigned int)v8,
      phkResult);
LABEL_3:
    if ( hKey )
      RegCloseKey(hKey);
    if ( v18[0] )
      RegCloseKey(v18[0]);
    return v9;
  }
  v11 = RegOpenKeyExW(v18[0], a2, 0, 0x2001Fu, &hKey);
  v12 = v11;
  v13 = v11 <= 0;
  if ( v11
    || (cbData = 2 * a5,
        Type = 0,
        v11 = RegQueryValueExW(hKey, a3, 0, &Type, a4, &cbData),
        v12 = v11,
        v13 = v11 <= 0,
        v11) )
  {
    if ( !v13 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    if ( hKey )
      RegCloseKey(hKey);
    if ( v18[0] )
      RegCloseKey(v18[0]);
    return v12;
  }
  else
  {
    if ( Type == 1 )
      goto LABEL_3;
    if ( hKey )
      RegCloseKey(hKey);
    if ( v18[0] )
      RegCloseKey(v18[0]);
    return 2147944029LL;
  }
}

```

## disassembly

```asm
0x1400538a0  push    rbp
0x1400538a2  push    rbx
0x1400538a3  push    rsi
0x1400538a4  push    rdi
0x1400538a5  push    r14
0x1400538a7  mov     rbp, rsp
0x1400538aa  sub     rsp, 50h
0x1400538ae  mov     rbx, rdx
0x1400538b1  mov     [rbp+var_10], 0
0x1400538b9  lea     rdx, [rbp+var_10]
0x1400538bd  mov     [rbp+hKey], 0
0x1400538c5  mov     ecx, 2001Fh
0x1400538ca  mov     rsi, r9
0x1400538cd  mov     r14, r8
0x1400538d0  call    cs:__imp_OpenEnrollmentsHKEY
0x1400538d7  nop     dword ptr [rax+rax+00h]
0x1400538dc  mov     edi, eax
0x1400538de  test    eax, eax
0x1400538e0  jns     short loc_140053932
0x1400538e2  mov     rcx, [rbp+28h]; this
0x1400538e6  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x1400538ed  mov     r9d, eax; char *
0x1400538f0  mov     edx, 19Dh; void *
0x1400538f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400538fa  mov     rcx, [rbp+hKey]; hKey
0x1400538fe  test    rcx, rcx
0x140053901  jz      short loc_14005390F
0x140053903  call    cs:__imp_RegCloseKey
0x14005390a  nop     dword ptr [rax+rax+00h]
0x14005390f  mov     rcx, [rbp+var_10]; hKey
0x140053913  test    rcx, rcx
0x140053916  jz      short loc_140053924
0x140053918  call    cs:__imp_RegCloseKey
0x14005391f  nop     dword ptr [rax+rax+00h]
0x140053924  mov     eax, edi
0x140053926  add     rsp, 50h
0x14005392a  pop     r14
0x14005392c  pop     rdi
0x14005392d  pop     rsi
0x14005392e  pop     rbx
0x14005392f  pop     rbp
0x140053930  retn
0x140053932  mov     rcx, [rbp+var_10]; hKey
0x140053936  lea     rax, [rbp+hKey]
0x14005393a  mov     r9d, 2001Fh; samDesired
0x140053940  mov     [rsp+50h+phkResult], rax; phkResult
0x140053945  xor     r8d, r8d; ulOptions
0x140053948  mov     rdx, rbx; lpSubKey
0x14005394b  call    cs:__imp_RegOpenKeyExW
0x140053952  nop     dword ptr [rax+rax+00h]
0x140053957  mov     ebx, eax
0x140053959  test    eax, eax
0x14005395b  jz      short loc_140053996
0x14005395d  jle     short loc_140053968
0x14005395f  movzx   ebx, ax
0x140053962  or      ebx, 80070000h
0x140053968  mov     rcx, [rbp+hKey]; hKey
0x14005396c  test    rcx, rcx
0x14005396f  jz      short loc_14005397D
0x140053971  call    cs:__imp_RegCloseKey
0x140053978  nop     dword ptr [rax+rax+00h]
0x14005397d  mov     rcx, [rbp+var_10]; hKey
0x140053981  test    rcx, rcx
0x140053984  jz      short loc_140053992
0x140053986  call    cs:__imp_RegCloseKey
0x14005398d  nop     dword ptr [rax+rax+00h]
0x140053992  mov     eax, ebx
0x140053994  jmp     short loc_140053926
0x140053996  mov     eax, [rbp+arg_20]
0x140053999  lea     r9, [rbp+Type]; lpType
0x14005399d  mov     rcx, [rbp+hKey]; hKey
0x1400539a1  add     eax, eax
0x1400539a3  mov     [rbp+cbData], eax
0x1400539a6  xor     r8d, r8d; lpReserved
0x1400539a9  lea     rax, [rbp+cbData]
0x1400539ad  mov     [rbp+Type], 0
0x1400539b4  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1400539b9  mov     rdx, r14; lpValueName
0x1400539bc  mov     [rsp+50h+phkResult], rsi; lpData
0x1400539c1  call    cs:__imp_RegQueryValueExW
0x1400539c8  nop     dword ptr [rax+rax+00h]
0x1400539cd  mov     ebx, eax
0x1400539cf  test    eax, eax
0x1400539d1  jnz     short loc_14005395D
0x1400539d3  cmp     [rbp+Type], 1
0x1400539d7  jz      loc_1400538FA
0x1400539dd  mov     rcx, [rbp+hKey]; hKey
0x1400539e1  test    rcx, rcx
0x1400539e4  jz      short loc_1400539F2
0x1400539e6  call    cs:__imp_RegCloseKey
0x1400539ed  nop     dword ptr [rax+rax+00h]
0x1400539f2  mov     rcx, [rbp+var_10]; hKey
0x1400539f6  test    rcx, rcx
0x1400539f9  jz      short loc_140053A07
0x1400539fb  call    cs:__imp_RegCloseKey
0x140053a02  nop     dword ptr [rax+rax+00h]
0x140053a07  mov     eax, 8007065Dh
0x140053a0c  jmp     loc_140053926
```
