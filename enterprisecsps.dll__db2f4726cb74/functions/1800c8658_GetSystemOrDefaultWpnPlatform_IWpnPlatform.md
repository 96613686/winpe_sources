# GetSystemOrDefaultWpnPlatform(IWpnPlatform * *)

- ea: `0x1800c8658`
- end: `0x1800c872a`
- name: `?GetSystemOrDefaultWpnPlatform@@YAJPEAPEAUIWpnPlatform@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800c1fac`
- `0x1800c95dc`
- `0x1800cd574`

## callees

- `0x1800c8658`
- `0x1800cda60`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800c867e`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800c867e`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x1800c8698`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x1800c8698`
- `combase!__imp_CoCreateInstanceAsUser` at `0x1800c871c`
- `combase!__imp_CoCreateInstanceAsUser` at `0x1800c871c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c86c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c86c8`

## pseudocode

```c
HRESULT __fastcall GetSystemOrDefaultWpnPlatform(LPVOID *ppv)
{
  bool v2; // di
  GUID *v3; // rcx
  int DefaultUserContextToken; // eax
  int v6; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  *ppv = 0;
  v6 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v6, 0);
  v2 = (unsigned int)(v6 - 7) <= 1;
  if ( !(unsigned __int8)RtlIsMultiUsersInSessionSku() && !v2 )
  {
    v3 = &GUID_1fd1b5a7_5c96_4711_a7c3_fff6d21f93d9;
    return CoCreateInstance(v3, 0, 0x404u, &GUID_df8e9480_ca73_448e_b8f0_da000f581428, ppv);
  }
  v7 = 0;
  DefaultUserContextToken = _GetDefaultUserContextToken(&v7);
  v3 = &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c;
  if ( DefaultUserContextToken < 0 )
    return CoCreateInstance(v3, 0, 0x404u, &GUID_df8e9480_ca73_448e_b8f0_da000f581428, ppv);
  return CoCreateInstanceAsUser(
           &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
           0,
           1028,
           v7,
           &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
           ppv);
}

```

## disassembly

```asm
0x1800c8658  mov     [rsp+arg_10], rbx
0x1800c865d  push    rdi
0x1800c865e  sub     rsp, 30h
0x1800c8662  mov     rbx, rcx
0x1800c8665  mov     qword ptr [rcx], 0
0x1800c866c  xor     ecx, ecx
0x1800c866e  mov     [rsp+38h+arg_0], 0
0x1800c8676  xor     r8d, r8d
0x1800c8679  lea     rdx, [rsp+38h+arg_0]
0x1800c867e  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800c8685  nop     dword ptr [rax+rax+00h]
0x1800c868a  mov     eax, [rsp+38h+arg_0]
0x1800c868e  add     eax, 0FFFFFFF9h
0x1800c8691  cmp     eax, 1
0x1800c8694  setbe   dil
0x1800c8698  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x1800c869f  nop     dword ptr [rax+rax+00h]
0x1800c86a4  test    al, al
0x1800c86a6  jnz     short loc_1800C86E0
0x1800c86a8  test    dil, dil
0x1800c86ab  jnz     short loc_1800C86E0
0x1800c86ad  lea     rcx, _GUID_1fd1b5a7_5c96_4711_a7c3_fff6d21f93d9; rclsid
0x1800c86b4  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x1800c86bb  mov     [rsp+38h+ppv], rbx; ppv
0x1800c86c0  mov     r8d, 404h; dwClsContext
0x1800c86c6  xor     edx, edx; pUnkOuter
0x1800c86c8  call    cs:__imp_CoCreateInstance
0x1800c86cf  nop     dword ptr [rax+rax+00h]
0x1800c86d4  mov     rbx, [rsp+38h+arg_10]
0x1800c86d9  add     rsp, 30h
0x1800c86dd  pop     rdi
0x1800c86de  retn
0x1800c86e0  lea     rcx, [rsp+38h+arg_8]; unsigned __int64 *
0x1800c86e5  mov     [rsp+38h+arg_8], 0
0x1800c86ee  call    ?_GetDefaultUserContextToken@@YAJPEA_K@Z; _GetDefaultUserContextToken(unsigned __int64 *)
0x1800c86f3  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c
0x1800c86fa  test    eax, eax
0x1800c86fc  js      short loc_1800C86B4
0x1800c86fe  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x1800c8705  mov     [rsp+38h+var_10], rbx
0x1800c870a  mov     [rsp+38h+ppv], r9
0x1800c870f  xor     edx, edx
0x1800c8711  mov     r9, [rsp+38h+arg_8]
0x1800c8716  mov     r8d, 404h
0x1800c871c  call    cs:__imp_CoCreateInstanceAsUser
0x1800c8723  nop     dword ptr [rax+rax+00h]
0x1800c8728  jmp     short loc_1800C86D4
```
