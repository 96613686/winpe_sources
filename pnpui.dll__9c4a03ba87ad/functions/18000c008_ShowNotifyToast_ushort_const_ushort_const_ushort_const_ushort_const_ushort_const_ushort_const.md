# ShowNotifyToast(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000c008`
- end: `0x18000c235`
- name: `?ShowNotifyToast@@YAJPEBG00000@Z`
- size: `557`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b710`
- `0x18000bde4`

## callees

- `0x180003614`
- `0x18000b5f4`
- `0x18000c008`
- `0x18000cd10`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c1bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c1cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c1bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c1cd`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c056`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c056`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c202`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c202`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c087`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c087`

## string_xrefs

- `0x18000c10b`: `<toast scenario='reminder' activationType='protocol' launch='%ws'><visual><binding template='ToastGeneric'><image src='%ws' placement='AppLogoOverride' /><text id='1' hint-style='header'>%ws</text><group><subgroup><text id='2' hint-wrap='true'>%ws</text></subgroup></group></binding></visual></toast>`

## pseudocode

```c
__int64 __fastcall ShowNotifyToast(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v6; // r15d
  HRESULT v7; // ebx
  unsigned __int16 *v8; // rdi
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rsi
  __int64 *v11; // rcx
  __int64 *v12; // rax
  __int64 (__fastcall *v13)(__int64, const wchar_t *, const wchar_t *, _QWORD, _DWORD, unsigned __int16 *, const wchar_t *, _QWORD, __int64 *, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, int *); // rax
  int v15; // [rsp+90h] [rbp-80h] BYREF
  __int64 v16; // [rsp+98h] [rbp-78h] BYREF
  LPVOID ppv; // [rsp+A0h] [rbp-70h] BYREF
  __int64 v18; // [rsp+B0h] [rbp-60h] BYREF
  int v19; // [rsp+B8h] [rbp-58h]
  unsigned __int16 v20[1024]; // [rsp+C0h] [rbp-50h] BYREF

  v6 = 0;
  ppv = 0;
  v16 = 0;
  v15 = 0;
  v7 = CoInitializeEx(0, 0);
  if ( v7 < 0 )
    goto LABEL_20;
  v6 = 1;
  v7 = CoCreateInstance(
         &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
         0,
         4u,
         &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
         &ppv);
  if ( v7 < 0 )
    goto LABEL_20;
  v7 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, &v16);
  if ( v7 < 0 )
    goto LABEL_20;
  v8 = 0;
  if ( a1 )
  {
    v8 = EncodeXmlString(a1);
    if ( !v8 )
    {
      v7 = -2147024882;
      goto LABEL_20;
    }
  }
  if ( !a2 )
  {
    v10 = 0;
    v11 = &qword_18000FDD8;
    goto LABEL_12;
  }
  v9 = EncodeXmlString(a2);
  v10 = v9;
  if ( v9 )
  {
    v11 = (__int64 *)v9;
LABEL_12:
    v12 = &qword_18000FDD8;
    if ( v8 )
      v12 = (__int64 *)v8;
    v7 = StringCchPrintfW(
           v20,
           0x400u,
           L"<toast scenario='reminder' activationType='protocol' launch='%ws'><visual><binding template='ToastGeneric'><i"
            "mage src='%ws' placement='AppLogoOverride' /><text id='1' hint-style='header'>%ws</text><group><subgroup><te"
            "xt id='2' hint-wrap='true'>%ws</text></subgroup></group></binding></visual></toast>",
           &qword_18000FDD8,
           &qword_18000FDD8,
           v12,
           v11);
    if ( v7 >= 0 )
    {
      v13 = *(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, _DWORD, unsigned __int16 *, const wchar_t *, _QWORD, __int64 *, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, int *))(*(_QWORD *)v16 + 64LL);
      v18 = 0;
      v19 = 0;
      v7 = v13(
             v16,
             L"NonImmersivePackage",
             L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
             0,
             0,
             v20,
             L"DeviceNeedsReboot",
             0,
             &v18,
             0,
             0,
             0,
             0,
             0,
             0,
             &v15);
    }
    goto LABEL_16;
  }
  v7 = -2147024882;
LABEL_16:
  if ( v8 )
    LocalFree(v8);
  if ( v10 )
    LocalFree(v10);
LABEL_20:
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v6 )
    CoUninitialize();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000c008  mov     [rsp-8+arg_10], rbx
0x18000c00d  mov     [rsp-8+arg_18], rsi
0x18000c012  push    rbp
0x18000c013  push    rdi
0x18000c014  push    r13
0x18000c016  push    r14
0x18000c018  push    r15
0x18000c01a  lea     rbp, [rsp-7C0h]
0x18000c022  sub     rsp, 8D0h
0x18000c029  mov     rax, cs:__security_cookie
0x18000c030  xor     rax, rsp
0x18000c033  mov     [rbp+7E0h+var_30], rax
0x18000c03a  mov     r14, rdx
0x18000c03d  mov     rsi, rcx
0x18000c040  xor     r15d, r15d
0x18000c043  xor     r13d, r13d
0x18000c046  xor     edx, edx; dwCoInit
0x18000c048  mov     [rbp+7E0h+var_850], r15
0x18000c04c  xor     ecx, ecx; pvReserved
0x18000c04e  mov     [rbp+7E0h+var_858], r15
0x18000c052  mov     [rbp+7E0h+var_860], r13d
0x18000c056  call    cs:__imp_CoInitializeEx
0x18000c05c  mov     ebx, eax
0x18000c05e  test    eax, eax
0x18000c060  js      loc_18000C1D3
0x18000c066  lea     rax, [rbp+7E0h+var_850]
0x18000c06a  xor     edx, edx; pUnkOuter
0x18000c06c  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x18000c073  mov     [rsp+8F0h+ppv], rax; ppv
0x18000c078  lea     r8d, [r13+4]; dwClsContext
0x18000c07c  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x18000c083  lea     r15d, [r13+1]
0x18000c087  call    cs:__imp_CoCreateInstance
0x18000c08d  mov     ebx, eax
0x18000c08f  test    eax, eax
0x18000c091  js      loc_18000C1D3
0x18000c097  mov     rcx, [rbp+7E0h+var_850]
0x18000c09b  lea     rdx, [rbp+7E0h+var_858]
0x18000c09f  mov     rax, [rcx]
0x18000c0a2  mov     rax, [rax+18h]
0x18000c0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0ab  mov     ebx, eax
0x18000c0ad  test    eax, eax
0x18000c0af  js      loc_18000C1D3
0x18000c0b5  xor     edi, edi
0x18000c0b7  test    rsi, rsi
0x18000c0ba  jz      short loc_18000C0D6
0x18000c0bc  mov     rcx, rsi; unsigned __int16 *
0x18000c0bf  call    ?EncodeXmlString@@YAPEAGPEBG@Z; EncodeXmlString(ushort const *)
0x18000c0c4  mov     rdi, rax
0x18000c0c7  test    rax, rax
0x18000c0ca  jnz     short loc_18000C0D6
0x18000c0cc  mov     ebx, 8007000Eh
0x18000c0d1  jmp     loc_18000C1D3
0x18000c0d6  lea     rbx, qword_18000FDD8
0x18000c0dd  test    r14, r14
0x18000c0e0  jz      short loc_18000C101
0x18000c0e2  mov     rcx, r14; unsigned __int16 *
0x18000c0e5  call    ?EncodeXmlString@@YAPEAGPEBG@Z; EncodeXmlString(ushort const *)
0x18000c0ea  mov     rsi, rax
0x18000c0ed  test    rax, rax
0x18000c0f0  jnz     short loc_18000C0FC
0x18000c0f2  mov     ebx, 8007000Eh
0x18000c0f7  jmp     loc_18000C1B7
0x18000c0fc  mov     rcx, rax
0x18000c0ff  jmp     short loc_18000C106
0x18000c101  xor     esi, esi
0x18000c103  mov     rcx, rbx
0x18000c106  mov     [rsp+8F0h+var_8C0], rcx
0x18000c10b  lea     r8, aToastScenarioR; "<toast scenario='reminder' activationTy"...
0x18000c112  test    rdi, rdi
0x18000c115  lea     rcx, [rbp+7E0h+var_830]; unsigned __int16 *
0x18000c119  mov     rax, rbx
0x18000c11c  mov     r9, rbx
0x18000c11f  cmovnz  rax, rdi
0x18000c123  mov     edx, 400h; unsigned __int64
0x18000c128  mov     [rsp+8F0h+var_8C8], rax
0x18000c12d  mov     [rsp+8F0h+ppv], rbx
0x18000c132  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c137  mov     ebx, eax
0x18000c139  test    eax, eax
0x18000c13b  js      short loc_18000C1B7
0x18000c13d  mov     rcx, [rbp+7E0h+var_858]
0x18000c141  lea     rdx, [rbp+7E0h+var_860]
0x18000c145  mov     [rsp+8F0h+var_878], rdx
0x18000c14a  lea     r8, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x18000c151  mov     [rsp+8F0h+var_880], r13d
0x18000c156  lea     rdx, [rbp+7E0h+var_840]
0x18000c15a  mov     [rsp+8F0h+var_888], r13
0x18000c15f  xor     r9d, r9d
0x18000c162  mov     rax, [rcx]
0x18000c165  mov     [rsp+8F0h+var_890], r13
0x18000c16a  mov     [rsp+8F0h+var_898], r13
0x18000c16f  mov     [rsp+8F0h+var_8A0], r13d
0x18000c174  mov     rax, [rax+40h]
0x18000c178  mov     [rsp+8F0h+var_8A8], r13d
0x18000c17d  mov     [rsp+8F0h+var_8B0], rdx
0x18000c182  lea     rdx, aDeviceneedsreb; "DeviceNeedsReboot"
0x18000c189  mov     [rsp+8F0h+var_8B8], r13
0x18000c18e  mov     [rsp+8F0h+var_8C0], rdx
0x18000c193  lea     rdx, [rbp+7E0h+var_830]
0x18000c197  mov     [rsp+8F0h+var_8C8], rdx
0x18000c19c  lea     rdx, aNonimmersivepa; "NonImmersivePackage"
0x18000c1a3  mov     [rbp+7E0h+var_840], r13
0x18000c1a7  mov     [rbp+7E0h+var_838], r13d
0x18000c1ab  mov     dword ptr [rsp+8F0h+ppv], r13d
0x18000c1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1b5  mov     ebx, eax
0x18000c1b7  test    rdi, rdi
0x18000c1ba  jz      short loc_18000C1C5
0x18000c1bc  mov     rcx, rdi; hMem
0x18000c1bf  call    cs:__imp_LocalFree
0x18000c1c5  test    rsi, rsi
0x18000c1c8  jz      short loc_18000C1D3
0x18000c1ca  mov     rcx, rsi; hMem
0x18000c1cd  call    cs:__imp_LocalFree
0x18000c1d3  mov     rcx, [rbp+7E0h+var_858]
0x18000c1d7  test    rcx, rcx
0x18000c1da  jz      short loc_18000C1E8
0x18000c1dc  mov     rax, [rcx]
0x18000c1df  mov     rax, [rax+10h]
0x18000c1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1e8  mov     rcx, [rbp+7E0h+var_850]
0x18000c1ec  test    rcx, rcx
0x18000c1ef  jz      short loc_18000C1FD
0x18000c1f1  mov     rax, [rcx]
0x18000c1f4  mov     rax, [rax+10h]
0x18000c1f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1fd  test    r15d, r15d
0x18000c200  jz      short loc_18000C208
0x18000c202  call    cs:__imp_CoUninitialize
0x18000c208  mov     eax, ebx
0x18000c20a  mov     rcx, [rbp+7E0h+var_30]
0x18000c211  xor     rcx, rsp; StackCookie
0x18000c214  call    __security_check_cookie
0x18000c219  lea     r11, [rsp+8F0h+var_20]
0x18000c221  mov     rbx, [r11+40h]
0x18000c225  mov     rsi, [r11+48h]
0x18000c229  mov     rsp, r11
0x18000c22c  pop     r15
0x18000c22e  pop     r14
0x18000c230  pop     r13
0x18000c232  pop     rdi
0x18000c233  pop     rbp
0x18000c234  retn
```
