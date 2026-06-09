# EnterpriseFeatureControl::RegQueryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x180016bcc`
- end: `0x180016d48`
- name: `?RegQueryDwordValue@EnterpriseFeatureControl@@CAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `380`
- prototype: `static int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18007652c`

## callees

- `0x1800108cc`
- `0x180016bcc`
- `0x180017988`
- `0x180017c80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016cbd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016cbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016c2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016d1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016d38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016c2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016d1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016d38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016c6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016c6b`

## string_xrefs

- `0x180016cb1`: `TemporaryEnterpriseFeatureControlState`

## pseudocode

```c
__int64 __fastcall EnterpriseFeatureControl::RegQueryDwordValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HKEY *v9; // rax
  LSTATUS v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rdx
  HKEY v13; // rcx
  int phkResult; // [rsp+20h] [rbp-20h]
  unsigned int phkResulta; // [rsp+20h] [rbp-20h]
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  int v19; // [rsp+64h] [rbp+24h]
  unsigned int Data; // [rsp+68h] [rbp+28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  int v22; // [rsp+74h] [rbp+34h]

  v22 = HIDWORD(a3);
  v19 = HIDWORD(a1);
  hKey[0] = 0;
  Type = 4;
  cbData = 4;
  Data = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = 118;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v6 = -2147467261;
    v7 = 120;
    goto LABEL_3;
  }
  v9 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 1u, v9);
  v6 = v10;
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( v6 + 2147024894 <= 1 )
      goto LABEL_4;
    v7 = 124;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)v6,
      phkResult);
LABEL_4:
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return v6;
  }
  v11 = RegQueryValueExW(hKey[0], L"TemporaryEnterpriseFeatureControlState", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v11 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x83,
           (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
           (const char *)v11,
           phkResulta);
    goto LABEL_4;
  }
  if ( Type != 4 )
  {
    v12 = 134;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)0x8000FFFFLL,
      phkResulta);
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return 2147549183LL;
  }
  if ( cbData != 4 )
  {
    v12 = 135;
    goto LABEL_20;
  }
  v13 = hKey[0];
  *a4 = Data;
  if ( v13 )
    RegCloseKey(v13);
  return 0;
}

```

## disassembly

```asm
0x180016bcc  mov     qword ptr [rsp-18h+Type], r8
0x180016bd1  mov     qword ptr [rsp-18h+cbData], rcx
0x180016bd6  push    rbp
0x180016bd7  push    rbx
0x180016bd8  push    rdi
0x180016bd9  mov     rbp, rsp
0x180016bdc  sub     rsp, 40h
0x180016be0  mov     [rbp+hKey], 0
0x180016be8  mov     rdi, r9
0x180016beb  mov     [rbp+Type], 4
0x180016bf2  mov     rbx, rdx
0x180016bf5  mov     [rbp+cbData], 4
0x180016bfc  mov     [rbp+Data], 0
0x180016c03  test    rdx, rdx
0x180016c06  jnz     short loc_180016C3B
0x180016c08  mov     ebx, 80070057h
0x180016c0d  mov     edx, 76h ; 'v'; void *
0x180016c12  mov     rcx, [rbp+18h]; this
0x180016c16  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180016c1d  mov     r9d, ebx; char *
0x180016c20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c25  mov     rcx, [rbp+hKey]; hKey
0x180016c29  test    rcx, rcx
0x180016c2c  jz      short loc_180016C34
0x180016c2e  call    cs:__imp_RegCloseKey
0x180016c34  mov     eax, ebx
0x180016c36  jmp     loc_180016D40
0x180016c3b  test    rdi, rdi
0x180016c3e  jnz     short loc_180016C4A
0x180016c40  mov     ebx, 80004003h
0x180016c45  lea     edx, [rdi+78h]
0x180016c48  jmp     short loc_180016C12
0x180016c4a  lea     rcx, [rbp+hKey]
0x180016c4e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180016c53  mov     r9d, 1; samDesired
0x180016c59  mov     [rsp+40h+phkResult], rax; phkResult
0x180016c5e  xor     r8d, r8d; ulOptions
0x180016c61  mov     rdx, rbx; lpSubKey
0x180016c64  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016c6b  call    cs:__imp_RegOpenKeyExW
0x180016c71  mov     ebx, eax
0x180016c73  test    eax, eax
0x180016c75  jle     short loc_180016C80
0x180016c77  movzx   ebx, ax
0x180016c7a  or      ebx, 80070000h
0x180016c80  test    ebx, ebx
0x180016c82  jns     short loc_180016C99
0x180016c84  lea     eax, [rbx+7FF8FFFEh]
0x180016c8a  cmp     eax, 1
0x180016c8d  jbe     short loc_180016C25
0x180016c8f  mov     edx, 7Ch ; '|'
0x180016c94  jmp     loc_180016C12
0x180016c99  mov     rcx, [rbp+hKey]; hKey
0x180016c9d  lea     rax, [rbp+cbData]
0x180016ca1  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180016ca6  lea     r9, [rbp+Type]; lpType
0x180016caa  lea     rax, [rbp+Data]
0x180016cae  xor     r8d, r8d; lpReserved
0x180016cb1  lea     rdx, aTemporaryenter; "TemporaryEnterpriseFeatureControlState"
0x180016cb8  mov     [rsp+40h+phkResult], rax; int
0x180016cbd  call    cs:__imp_RegQueryValueExW
0x180016cc3  test    eax, eax
0x180016cc5  jz      short loc_180016CE6
0x180016cc7  mov     rcx, [rbp+18h]; this
0x180016ccb  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180016cd2  mov     r9d, eax; char *
0x180016cd5  mov     edx, 83h; void *
0x180016cda  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180016cdf  mov     ebx, eax
0x180016ce1  jmp     loc_180016C25
0x180016ce6  cmp     [rbp+Type], 4
0x180016cea  jz      short loc_180016CF3
0x180016cec  mov     edx, 86h
0x180016cf1  jmp     short loc_180016CFE
0x180016cf3  cmp     [rbp+cbData], 4
0x180016cf7  jz      short loc_180016D2A
0x180016cf9  mov     edx, 87h; void *
0x180016cfe  mov     rcx, [rbp+18h]; this
0x180016d02  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180016d09  mov     r9d, 8000FFFFh; char *
0x180016d0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016d14  mov     rcx, [rbp+hKey]; hKey
0x180016d18  test    rcx, rcx
0x180016d1b  jz      short loc_180016D23
0x180016d1d  call    cs:__imp_RegCloseKey
0x180016d23  mov     eax, 8000FFFFh
0x180016d28  jmp     short loc_180016D40
0x180016d2a  mov     rcx, [rbp+hKey]; hKey
0x180016d2e  mov     eax, [rbp+Data]
0x180016d31  mov     [rdi], eax
0x180016d33  test    rcx, rcx
0x180016d36  jz      short loc_180016D3E
0x180016d38  call    cs:__imp_RegCloseKey
0x180016d3e  xor     eax, eax
0x180016d40  add     rsp, 40h
0x180016d44  pop     rdi
0x180016d45  pop     rbx
0x180016d46  pop     rbp
0x180016d47  retn
```
