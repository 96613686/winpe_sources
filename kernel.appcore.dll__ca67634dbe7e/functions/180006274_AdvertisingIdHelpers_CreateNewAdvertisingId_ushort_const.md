# AdvertisingIdHelpers::CreateNewAdvertisingId(ushort const *)

- ea: `0x180006274`
- end: `0x18000631d`
- name: `?CreateNewAdvertisingId@AdvertisingIdHelpers@@YAJPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(AdvertisingIdHelpers *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009a20`

## callees

- `0x1800061c4`
- `0x180006274`
- `0x180006324`
- `0x180006354`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800062ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800062f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000630a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800062ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800062f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000630a`

## pseudocode

```c
__int64 __fastcall AdvertisingIdHelpers::CreateNewAdvertisingId(
        AdvertisingIdHelpers *this,
        const unsigned __int16 *a2,
        HKEY *a3)
{
  int v3; // eax
  unsigned __int16 *v4; // rdx
  unsigned int v5; // r8d
  unsigned int v6; // ebx
  HKEY v8; // rbx
  int v9; // eax
  unsigned int v10; // edi
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HKEY hKey; // [rsp+38h] [rbp+10h] BYREF

  hKey = 0;
  v3 = AdvertisingIdHelpers::CreateOrOpenHkcuRootKey((unsigned __int16 *)this, (unsigned __int16 *)&hKey, a3);
  v6 = v3;
  if ( v3 >= 0 )
  {
    v8 = hKey;
    v9 = AdvertisingIdHelpers::GenerateAndWriteNewIdToRegistry(hKey, v4, v5);
    v10 = v9;
    if ( v9 >= 0 )
    {
      if ( v8 )
        RegCloseKey(v8);
      return 0;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2C1,
        (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
        (const char *)(unsigned int)v9,
        v11);
      if ( v8 )
        RegCloseKey(v8);
      return v10;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2C0,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)(unsigned int)v3,
      v11);
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
}

```

## disassembly

```asm
0x180006274  mov     [rsp+arg_0], rbx
0x180006279  push    rdi; int
0x18000627a  sub     rsp, 20h
0x18000627e  lea     rdx, [rsp+28h+hKey]; unsigned __int16 *
0x180006283  mov     [rsp+28h+hKey], 0
0x18000628c  call    ?CreateOrOpenHkcuRootKey@AdvertisingIdHelpers@@YAJPEBGPEAPEAUHKEY__@@@Z; AdvertisingIdHelpers::CreateOrOpenHkcuRootKey(ushort const *,HKEY__ * *)
0x180006291  mov     ebx, eax
0x180006293  test    eax, eax
0x180006295  jns     short loc_1800062C4
0x180006297  mov     rcx, [rsp+28h]; this
0x18000629c  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x1800062a3  mov     r9d, eax; char *
0x1800062a6  mov     edx, 2C0h; void *
0x1800062ab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800062b0  mov     rcx, [rsp+28h+hKey]; hKey
0x1800062b5  test    rcx, rcx
0x1800062b8  jz      short loc_1800062C0
0x1800062ba  call    cs:__imp_RegCloseKey
0x1800062c0  mov     eax, ebx
0x1800062c2  jmp     short loc_180006312
0x1800062c4  mov     rbx, [rsp+28h+hKey]
0x1800062c9  mov     rcx, rbx; hKey
0x1800062cc  call    ?GenerateAndWriteNewIdToRegistry@AdvertisingIdHelpers@@YAJPEAUHKEY__@@@Z; AdvertisingIdHelpers::GenerateAndWriteNewIdToRegistry(HKEY__ *)
0x1800062d1  mov     edi, eax
0x1800062d3  test    eax, eax
0x1800062d5  jns     short loc_180006302
0x1800062d7  mov     rcx, [rsp+28h]; this
0x1800062dc  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x1800062e3  mov     r9d, eax; char *
0x1800062e6  mov     edx, 2C1h; void *
0x1800062eb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800062f0  test    rbx, rbx
0x1800062f3  jz      short loc_1800062FE
0x1800062f5  mov     rcx, rbx; hKey
0x1800062f8  call    cs:__imp_RegCloseKey
0x1800062fe  mov     eax, edi
0x180006300  jmp     short loc_180006312
0x180006302  test    rbx, rbx
0x180006305  jz      short loc_180006310
0x180006307  mov     rcx, rbx; hKey
0x18000630a  call    cs:__imp_RegCloseKey
0x180006310  xor     eax, eax
0x180006312  mov     rbx, [rsp+28h+arg_0]
0x180006317  add     rsp, 20h
0x18000631b  pop     rdi
0x18000631c  retn
```
