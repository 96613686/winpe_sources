# fc::registry_store::update_or_add_config(HKEY__ *,fc::config const &)

- ea: `0x1800213a0`
- end: `0x1800214cf`
- name: `?update_or_add_config@registry_store@fc@@AEBAJPEAUHKEY__@@AEBUconfig@2@@Z`
- size: `303`
- prototype: `int(fc::registry_store *__hidden this, HKEY, const struct fc::config *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180020a74`

## callees

- `0x180003220`
- `0x180006d1c`
- `0x18000949c`
- `0x180018ab4`
- `0x18001b898`
- `0x18001f6c8`
- `0x1800213a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021462`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021462`

## string_xrefs

- `0x180021401`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\fc\fc_registry_store.h`
- `0x180021474`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\fc\fc_registry_store.h`

## pseudocode

```c
__int64 __fastcall fc::registry_store::update_or_add_config(
        fc::registry_store *this,
        HKEY a2,
        const struct fc::config *a3)
{
  unsigned __int64 v5; // rdx
  int reg_key_name_for_config; // ebx
  __int64 v7; // rdx
  void *v8; // rdx
  BYTE *v10; // rbx
  unsigned int v11; // eax
  void *v12; // rdx
  void *v13; // rdx
  unsigned int v14; // edi
  int lpData; // [rsp+20h] [rbp-238h]
  unsigned int lpDataa; // [rsp+20h] [rbp-238h]
  BYTE *v17; // [rsp+30h] [rbp-228h] BYREF
  DWORD cbData[2]; // [rsp+38h] [rbp-220h] BYREF
  WCHAR ValueName[256]; // [rsp+40h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v17 = 0;
  *(_QWORD *)cbData = 0;
  reg_key_name_for_config = fc::serialize_and_hash_config(a3, cbData, &v17);
  if ( reg_key_name_for_config < 0 )
  {
    v7 = 1105;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_registry_store.h",
      (const char *)(unsigned int)reg_key_name_for_config,
      lpData);
    if ( v17 )
      wil::details::FreeProcessHeap((wil::details *)v17, v8);
    return (unsigned int)reg_key_name_for_config;
  }
  reg_key_name_for_config = fc::registry_store::get_reg_key_name_for_config(*(_DWORD *)a3, v5, ValueName);
  if ( reg_key_name_for_config < 0 )
  {
    v7 = 1108;
    goto LABEL_3;
  }
  v10 = v17;
  v11 = RegSetValueExW(a2, ValueName, 0, 3u, v17, cbData[0]);
  if ( v11 )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x455,
            (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_registry_store.h",
            (const char *)v11,
            lpDataa);
    if ( v10 )
      wil::details::FreeProcessHeap((wil::details *)v10, v13);
    return v14;
  }
  else
  {
    if ( v10 )
      wil::details::FreeProcessHeap((wil::details *)v10, v12);
    return 0;
  }
}

```

## disassembly

```asm
0x1800213a0  mov     [rsp+arg_0], rbx
0x1800213a5  mov     [rsp+arg_18], rsi
0x1800213aa  push    rdi
0x1800213ab  sub     rsp, 250h
0x1800213b2  mov     rax, cs:__security_cookie
0x1800213b9  xor     rax, rsp
0x1800213bc  mov     [rsp+258h+var_18], rax
0x1800213c4  mov     rdi, r8
0x1800213c7  mov     [rsp+258h+var_228], 0
0x1800213d0  mov     rsi, rdx
0x1800213d3  mov     qword ptr [rsp+258h+var_220], 0
0x1800213dc  mov     rcx, rdi
0x1800213df  lea     r8, [rsp+258h+var_228]
0x1800213e4  lea     rdx, [rsp+258h+var_220]
0x1800213e9  call    ?serialize_and_hash_config@fc@@YAJAEBUconfig@1@AEA_KAEAV?$unique_ptr@EUprocess_heap_deleter@wil@@@wistd@@@Z; fc::serialize_and_hash_config(fc::config const &,unsigned __int64 &,wistd::unique_ptr<uchar,wil::process_heap_deleter> &)
0x1800213ee  mov     ebx, eax
0x1800213f0  test    eax, eax
0x1800213f2  jns     short loc_180021426
0x1800213f4  mov     edx, 451h; void *
0x1800213f9  mov     rcx, [rsp+258h]; this
0x180021401  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180021408  mov     r9d, ebx; char *
0x18002140b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021410  mov     rcx, [rsp+258h+var_228]; this
0x180021415  test    rcx, rcx
0x180021418  jz      short loc_18002141F
0x18002141a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18002141f  mov     eax, ebx
0x180021421  jmp     loc_1800214AA
0x180021426  mov     ecx, [rdi]; unsigned int
0x180021428  lea     r8, [rsp+258h+ValueName]; unsigned __int16 *
0x18002142d  call    ?get_reg_key_name_for_config@registry_store@fc@@SAJI_KPEAG@Z; fc::registry_store::get_reg_key_name_for_config(uint,unsigned __int64,ushort *)
0x180021432  mov     ebx, eax
0x180021434  test    eax, eax
0x180021436  jns     short loc_18002143F
0x180021438  mov     edx, 454h
0x18002143d  jmp     short loc_1800213F9
0x18002143f  mov     eax, [rsp+258h+var_220]
0x180021443  lea     rdx, [rsp+258h+ValueName]; lpValueName
0x180021448  mov     rbx, [rsp+258h+var_228]
0x18002144d  mov     r9d, 3; dwType
0x180021453  mov     [rsp+258h+cbData], eax; cbData
0x180021457  xor     r8d, r8d; Reserved
0x18002145a  mov     rcx, rsi; hKey
0x18002145d  mov     [rsp+258h+lpData], rbx; unsigned int
0x180021462  call    cs:__imp_RegSetValueExW
0x180021468  test    eax, eax
0x18002146a  jz      short loc_18002149B
0x18002146c  mov     rcx, [rsp+258h]; this
0x180021474  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18002147b  mov     r9d, eax; char *
0x18002147e  mov     edx, 455h; void *
0x180021483  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180021488  mov     edi, eax
0x18002148a  test    rbx, rbx
0x18002148d  jz      short loc_180021497
0x18002148f  mov     rcx, rbx; this
0x180021492  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180021497  mov     eax, edi
0x180021499  jmp     short loc_1800214AA
0x18002149b  test    rbx, rbx
0x18002149e  jz      short loc_1800214A8
0x1800214a0  mov     rcx, rbx; this
0x1800214a3  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800214a8  xor     eax, eax
0x1800214aa  mov     rcx, [rsp+258h+var_18]
0x1800214b2  xor     rcx, rsp; StackCookie
0x1800214b5  call    __security_check_cookie
0x1800214ba  lea     r11, [rsp+258h+var_8]
0x1800214c2  mov     rbx, [r11+10h]
0x1800214c6  mov     rsi, [r11+28h]
0x1800214ca  mov     rsp, r11
0x1800214cd  pop     rdi
0x1800214ce  retn
```
