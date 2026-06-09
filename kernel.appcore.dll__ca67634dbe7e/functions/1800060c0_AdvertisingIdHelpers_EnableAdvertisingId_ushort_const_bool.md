# AdvertisingIdHelpers::EnableAdvertisingId(ushort const *,bool)

- ea: `0x1800060c0`
- end: `0x1800061bc`
- name: `?EnableAdvertisingId@AdvertisingIdHelpers@@YAJPEBG_N@Z`
- size: `252`
- prototype: `__int64 __fastcall(LPCWSTR StringSid, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009a30`
- `0x180009a50`

## callees

- `0x1800060c0`
- `0x1800061c4`
- `0x180006324`
- `0x180006354`
- `0x1800064d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180006196`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180006196`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006110`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800061a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006110`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800061a4`
- `api-ms-win-privacy-coreprivacysettingsstore-l1-1-0!CPSSPutDwordSetting` at `0x180006154`
- `api-ms-win-privacy-coreprivacysettingsstore-l1-1-0!CPSSPutDwordSetting` at `0x180006154`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180006131`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180006131`

## pseudocode

```c
__int64 __fastcall AdvertisingIdHelpers::EnableAdvertisingId(WCHAR *StringSid, const unsigned __int16 *a2, HKEY *a3)
{
  unsigned int v3; // esi
  int v5; // eax
  unsigned int v6; // ebx
  PSID v8; // rdx
  unsigned int v9; // eax
  HKEY v10; // rdx
  HKEY v11; // rbx
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF
  PSID Sid; // [rsp+58h] [rbp+20h] BYREF

  v3 = (unsigned __int8)a2;
  hKey = 0;
  v5 = AdvertisingIdHelpers::CreateOrOpenHkcuRootKey((HKEY)StringSid, (const unsigned __int16 *)&hKey, a3);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x292,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)(unsigned int)v5,
      v12);
LABEL_3:
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  v8 = 0;
  Sid = 0;
  if ( StringSid )
  {
    ConvertStringSidToSidW(StringSid, &Sid);
    v8 = Sid;
  }
  v9 = CPSSPutDwordSetting(1, v8, L"AdvertisingInfo", v3);
  if ( v9 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x2A2,
           (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
           (const char *)v9,
           0);
    goto LABEL_3;
  }
  v11 = hKey;
  if ( (_BYTE)v3 )
    AdvertisingIdHelpers::GenerateAndWriteNewIdToRegistry(hKey, v10);
  else
    RegDeleteValueW(hKey, L"Id");
  if ( v11 )
    RegCloseKey(v11);
  return 0;
}

```

## disassembly

```asm
0x1800060c0  mov     rax, rsp
0x1800060c3  mov     [rax+8], rbx
0x1800060c7  mov     [rax+10h], rsi
0x1800060cb  push    rdi
0x1800060cc  sub     rsp, 30h
0x1800060d0  movzx   esi, dl
0x1800060d3  mov     rdi, rcx
0x1800060d6  lea     rdx, [rax+18h]; unsigned __int16 *
0x1800060da  mov     qword ptr [rax+18h], 0
0x1800060e2  call    ?CreateOrOpenHkcuRootKey@AdvertisingIdHelpers@@YAJPEBGPEAPEAUHKEY__@@@Z; AdvertisingIdHelpers::CreateOrOpenHkcuRootKey(ushort const *,HKEY__ * *)
0x1800060e7  mov     ebx, eax
0x1800060e9  test    eax, eax
0x1800060eb  jns     short loc_18000611D
0x1800060ed  mov     rcx, [rsp+38h]; this
0x1800060f2  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x1800060f9  mov     r9d, eax; char *
0x1800060fc  mov     edx, 292h; void *
0x180006101  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006106  mov     rcx, [rsp+38h+hKey]; hKey
0x18000610b  test    rcx, rcx
0x18000610e  jz      short loc_180006116
0x180006110  call    cs:__imp_RegCloseKey
0x180006116  mov     eax, ebx
0x180006118  jmp     loc_1800061AC
0x18000611d  xor     edx, edx
0x18000611f  mov     [rsp+38h+Sid], rdx
0x180006124  test    rdi, rdi
0x180006127  jz      short loc_18000613C
0x180006129  lea     rdx, [rsp+38h+Sid]; Sid
0x18000612e  mov     rcx, rdi; StringSid
0x180006131  call    cs:__imp_ConvertStringSidToSidW
0x180006137  mov     rdx, [rsp+38h+Sid]
0x18000613c  mov     r9d, esi
0x18000613f  mov     qword ptr [rsp+38h+var_18], 0; unsigned int
0x180006148  lea     r8, aAdvertisinginf; "AdvertisingInfo"
0x18000614f  mov     ecx, 1
0x180006154  call    cs:__imp_CPSSPutDwordSetting
0x18000615a  test    eax, eax
0x18000615c  jz      short loc_18000617B
0x18000615e  mov     rcx, [rsp+38h]; this
0x180006163  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x18000616a  mov     r9d, eax; char *
0x18000616d  mov     edx, 2A2h; void *
0x180006172  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180006177  mov     ebx, eax
0x180006179  jmp     short loc_180006106
0x18000617b  mov     rbx, [rsp+38h+hKey]
0x180006180  mov     rcx, rbx; hKey
0x180006183  test    sil, sil
0x180006186  jz      short loc_18000618F
0x180006188  call    ?GenerateAndWriteNewIdToRegistry@AdvertisingIdHelpers@@YAJPEAUHKEY__@@@Z; AdvertisingIdHelpers::GenerateAndWriteNewIdToRegistry(HKEY__ *)
0x18000618d  jmp     short loc_18000619C
0x18000618f  lea     rdx, ValueName; "Id"
0x180006196  call    cs:__imp_RegDeleteValueW
0x18000619c  test    rbx, rbx
0x18000619f  jz      short loc_1800061AA
0x1800061a1  mov     rcx, rbx; hKey
0x1800061a4  call    cs:__imp_RegCloseKey
0x1800061aa  xor     eax, eax
0x1800061ac  mov     rbx, [rsp+38h+arg_0]
0x1800061b1  mov     rsi, [rsp+38h+arg_8]
0x1800061b6  add     rsp, 30h
0x1800061ba  pop     rdi
0x1800061bb  retn
```
