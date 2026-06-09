# GetTestSettingDword(ushort const *,ushort const *,ulong *)

- ea: `0x14000fe64`
- end: `0x14000ffe7`
- name: `?GetTestSettingDword@@YAJPEBG0PEAK@Z`
- size: `387`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140013350`

## callees

- `0x140008504`
- `0x14000fe64`

## import_xrefs

- `dmEnrollEngine!__imp_OpenEnrollmentsHKEY` at `0x14000fe8f`
- `dmEnrollEngine!__imp_OpenEnrollmentsHKEY` at `0x14000fe8f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000ff76`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000ff76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000fef6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000fef6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000fec2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ff37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ffb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ffcb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000fec2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ff37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ffb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ffcb`

## pseudocode

```c
__int64 __fastcall GetTestSettingDword(LPCWSTR lpSubKey, const unsigned __int16 *a2, BYTE *a3)
{
  int v5; // eax
  signed int v6; // ebx
  LSTATUS v8; // eax
  __int64 v9; // rdx
  LSTATUS v10; // eax
  int phkResult; // [rsp+20h] [rbp-20h]
  int phkResulta; // [rsp+20h] [rbp-20h]
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  HKEY v14; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  const unsigned __int16 *Type; // [rsp+68h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF

  Type = a2;
  hKey = 0;
  v5 = OpenEnrollmentsHKEY(131103, &hKey);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
      (const char *)(unsigned int)v5,
      phkResult);
LABEL_3:
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v6;
  }
  v14 = 0;
  v8 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x2001Fu, &v14);
  v6 = v8;
  if ( v8 > 0 )
    v6 = (unsigned __int16)v8 | 0x80070000;
  if ( v6 < 0 )
  {
    v9 = 527;
    goto LABEL_10;
  }
  LODWORD(Type) = 0;
  cbData = 4;
  v10 = RegQueryValueExW(v14, L"UserAccountMultiplier", 0, (LPDWORD)&Type, a3, &cbData);
  v6 = v10;
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  if ( v6 < 0 )
  {
    v9 = 537;
    goto LABEL_10;
  }
  if ( (_DWORD)Type != 4 )
  {
    v6 = -2147023267;
    v9 = 539;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
      (const char *)(unsigned int)v6,
      phkResulta);
    if ( v14 )
      RegCloseKey(v14);
    goto LABEL_3;
  }
  if ( v14 )
    RegCloseKey(v14);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x14000fe64  mov     [rsp-18h+arg_0], rbx
0x14000fe69  mov     [rsp-18h+Type], rdx
0x14000fe6e  push    rbp
0x14000fe6f  push    rsi
0x14000fe70  push    rdi
0x14000fe71  mov     rbp, rsp
0x14000fe74  sub     rsp, 40h
0x14000fe78  mov     rdi, rcx
0x14000fe7b  mov     [rbp+hKey], 0
0x14000fe83  mov     ecx, 2001Fh
0x14000fe88  lea     rdx, [rbp+hKey]
0x14000fe8c  mov     rsi, r8
0x14000fe8f  call    cs:__imp_OpenEnrollmentsHKEY
0x14000fe96  nop     dword ptr [rax+rax+00h]
0x14000fe9b  mov     ebx, eax
0x14000fe9d  test    eax, eax
0x14000fe9f  jns     short loc_14000FED5
0x14000fea1  mov     rcx, [rbp+18h]; this
0x14000fea5  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x14000feac  mov     r9d, eax; char *
0x14000feaf  mov     edx, 20Ch; void *
0x14000feb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000feb9  mov     rcx, [rbp+hKey]; hKey
0x14000febd  test    rcx, rcx
0x14000fec0  jz      short loc_14000FECE
0x14000fec2  call    cs:__imp_RegCloseKey
0x14000fec9  nop     dword ptr [rax+rax+00h]
0x14000fece  mov     eax, ebx
0x14000fed0  jmp     loc_14000FFD9
0x14000fed5  mov     rcx, [rbp+hKey]; hKey
0x14000fed9  lea     rax, [rbp+var_8]
0x14000fedd  mov     r9d, 2001Fh; samDesired
0x14000fee3  mov     [rsp+40h+phkResult], rax; int
0x14000fee8  xor     r8d, r8d; ulOptions
0x14000feeb  mov     [rbp+var_8], 0
0x14000fef3  mov     rdx, rdi; lpSubKey
0x14000fef6  call    cs:__imp_RegOpenKeyExW
0x14000fefd  nop     dword ptr [rax+rax+00h]
0x14000ff02  mov     ebx, eax
0x14000ff04  mov     edi, 80070000h
0x14000ff09  test    eax, eax
0x14000ff0b  jle     short loc_14000FF12
0x14000ff0d  movzx   ebx, ax
0x14000ff10  or      ebx, edi
0x14000ff12  test    ebx, ebx
0x14000ff14  jns     short loc_14000FF48
0x14000ff16  mov     edx, 20Fh; void *
0x14000ff1b  mov     rcx, [rbp+18h]; this
0x14000ff1f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x14000ff26  mov     r9d, ebx; char *
0x14000ff29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ff2e  mov     rcx, [rbp+var_8]; hKey
0x14000ff32  test    rcx, rcx
0x14000ff35  jz      short loc_14000FEB9
0x14000ff37  call    cs:__imp_RegCloseKey
0x14000ff3e  nop     dword ptr [rax+rax+00h]
0x14000ff43  jmp     loc_14000FEB9
0x14000ff48  mov     rcx, [rbp+var_8]; hKey
0x14000ff4c  lea     rax, [rbp+cbData]
0x14000ff50  mov     [rsp+40h+lpcbData], rax; lpcbData
0x14000ff55  lea     r9, [rbp+Type]; lpType
0x14000ff59  xor     r8d, r8d; lpReserved
0x14000ff5c  mov     [rsp+40h+phkResult], rsi; lpData
0x14000ff61  lea     rdx, aUseraccountmul; "UserAccountMultiplier"
0x14000ff68  mov     dword ptr [rbp+Type], 0
0x14000ff6f  mov     [rbp+cbData], 4
0x14000ff76  call    cs:__imp_RegQueryValueExW
0x14000ff7d  nop     dword ptr [rax+rax+00h]
0x14000ff82  mov     ebx, eax
0x14000ff84  test    eax, eax
0x14000ff86  jle     short loc_14000FF8D
0x14000ff88  movzx   ebx, ax
0x14000ff8b  or      ebx, edi
0x14000ff8d  test    ebx, ebx
0x14000ff8f  jns     short loc_14000FF98
0x14000ff91  mov     edx, 219h
0x14000ff96  jmp     short loc_14000FF1B
0x14000ff98  cmp     dword ptr [rbp+Type], 4
0x14000ff9c  jz      short loc_14000FFAD
0x14000ff9e  mov     ebx, 8007065Dh
0x14000ffa3  mov     edx, 21Bh
0x14000ffa8  jmp     loc_14000FF1B
0x14000ffad  mov     rcx, [rbp+var_8]; hKey
0x14000ffb1  test    rcx, rcx
0x14000ffb4  jz      short loc_14000FFC2
0x14000ffb6  call    cs:__imp_RegCloseKey
0x14000ffbd  nop     dword ptr [rax+rax+00h]
0x14000ffc2  mov     rcx, [rbp+hKey]; hKey
0x14000ffc6  test    rcx, rcx
0x14000ffc9  jz      short loc_14000FFD7
0x14000ffcb  call    cs:__imp_RegCloseKey
0x14000ffd2  nop     dword ptr [rax+rax+00h]
0x14000ffd7  xor     eax, eax
0x14000ffd9  mov     rbx, [rsp+40h+arg_0]
0x14000ffde  add     rsp, 40h
0x14000ffe2  pop     rdi
0x14000ffe3  pop     rsi
0x14000ffe4  pop     rbp
0x14000ffe5  retn
```
