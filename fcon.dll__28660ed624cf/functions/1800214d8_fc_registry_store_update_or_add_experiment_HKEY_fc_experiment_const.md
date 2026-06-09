# fc::registry_store::update_or_add_experiment(HKEY__ *,fc::experiment const &)

- ea: `0x1800214d8`
- end: `0x18002160a`
- name: `?update_or_add_experiment@registry_store@fc@@AEBAJPEAUHKEY__@@AEBUexperiment@2@@Z`
- size: `306`
- prototype: `int(fc::registry_store *__hidden this, HKEY, const struct fc::experiment *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180021098`

## callees

- `0x180003220`
- `0x180006d1c`
- `0x18000949c`
- `0x180018ab4`
- `0x18001b8ec`
- `0x18001f770`
- `0x1800214d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002159d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002159d`

## string_xrefs

- `0x180021539`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\fc\fc_registry_store.h`
- `0x1800215af`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\fc\fc_registry_store.h`

## pseudocode

```c
__int64 __fastcall fc::registry_store::update_or_add_experiment(
        fc::registry_store *this,
        HKEY a2,
        const struct fc::experiment *a3)
{
  int reg_key_name_for_experiment; // ebx
  unsigned __int64 v6; // r8
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
  reg_key_name_for_experiment = fc::serialize_and_hash_experiment(a3, cbData, &v17);
  if ( reg_key_name_for_experiment < 0 )
  {
    v7 = 995;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_registry_store.h",
      (const char *)(unsigned int)reg_key_name_for_experiment,
      lpData);
    if ( v17 )
      wil::details::FreeProcessHeap((wil::details *)v17, v8);
    return (unsigned int)reg_key_name_for_experiment;
  }
  reg_key_name_for_experiment = fc::registry_store::get_reg_key_name_for_experiment(
                                  *(_DWORD *)a3,
                                  *((_BYTE *)a3 + 4),
                                  v6,
                                  ValueName);
  if ( reg_key_name_for_experiment < 0 )
  {
    v7 = 999;
    goto LABEL_3;
  }
  v10 = v17;
  v11 = RegSetValueExW(a2, ValueName, 0, 3u, v17, cbData[0]);
  if ( v11 )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x3E8,
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
0x1800214d8  mov     [rsp+arg_0], rbx
0x1800214dd  mov     [rsp+arg_18], rsi
0x1800214e2  push    rdi
0x1800214e3  sub     rsp, 250h
0x1800214ea  mov     rax, cs:__security_cookie
0x1800214f1  xor     rax, rsp
0x1800214f4  mov     [rsp+258h+var_18], rax
0x1800214fc  mov     rdi, r8
0x1800214ff  mov     [rsp+258h+var_228], 0
0x180021508  mov     rsi, rdx
0x18002150b  mov     qword ptr [rsp+258h+var_220], 0
0x180021514  mov     rcx, rdi
0x180021517  lea     r8, [rsp+258h+var_228]
0x18002151c  lea     rdx, [rsp+258h+var_220]
0x180021521  call    ?serialize_and_hash_experiment@fc@@YAJAEBUexperiment@1@AEA_KAEAV?$unique_ptr@EUprocess_heap_deleter@wil@@@wistd@@@Z; fc::serialize_and_hash_experiment(fc::experiment const &,unsigned __int64 &,wistd::unique_ptr<uchar,wil::process_heap_deleter> &)
0x180021526  mov     ebx, eax
0x180021528  test    eax, eax
0x18002152a  jns     short loc_18002155E
0x18002152c  mov     edx, 3E3h; void *
0x180021531  mov     rcx, [rsp+258h]; this
0x180021539  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180021540  mov     r9d, ebx; char *
0x180021543  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021548  mov     rcx, [rsp+258h+var_228]; this
0x18002154d  test    rcx, rcx
0x180021550  jz      short loc_180021557
0x180021552  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180021557  mov     eax, ebx
0x180021559  jmp     loc_1800215E5
0x18002155e  mov     dl, [rdi+4]; unsigned __int8
0x180021561  lea     r9, [rsp+258h+ValueName]; unsigned __int16 *
0x180021566  mov     ecx, [rdi]; unsigned int
0x180021568  call    ?get_reg_key_name_for_experiment@registry_store@fc@@SAJIE_KPEAG@Z; fc::registry_store::get_reg_key_name_for_experiment(uint,uchar,unsigned __int64,ushort *)
0x18002156d  mov     ebx, eax
0x18002156f  test    eax, eax
0x180021571  jns     short loc_18002157A
0x180021573  mov     edx, 3E7h
0x180021578  jmp     short loc_180021531
0x18002157a  mov     eax, [rsp+258h+var_220]
0x18002157e  lea     rdx, [rsp+258h+ValueName]; lpValueName
0x180021583  mov     rbx, [rsp+258h+var_228]
0x180021588  mov     r9d, 3; dwType
0x18002158e  mov     [rsp+258h+cbData], eax; cbData
0x180021592  xor     r8d, r8d; Reserved
0x180021595  mov     rcx, rsi; hKey
0x180021598  mov     [rsp+258h+lpData], rbx; unsigned int
0x18002159d  call    cs:__imp_RegSetValueExW
0x1800215a3  test    eax, eax
0x1800215a5  jz      short loc_1800215D6
0x1800215a7  mov     rcx, [rsp+258h]; this
0x1800215af  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x1800215b6  mov     r9d, eax; char *
0x1800215b9  mov     edx, 3E8h; void *
0x1800215be  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800215c3  mov     edi, eax
0x1800215c5  test    rbx, rbx
0x1800215c8  jz      short loc_1800215D2
0x1800215ca  mov     rcx, rbx; this
0x1800215cd  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800215d2  mov     eax, edi
0x1800215d4  jmp     short loc_1800215E5
0x1800215d6  test    rbx, rbx
0x1800215d9  jz      short loc_1800215E3
0x1800215db  mov     rcx, rbx; this
0x1800215de  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800215e3  xor     eax, eax
0x1800215e5  mov     rcx, [rsp+258h+var_18]
0x1800215ed  xor     rcx, rsp; StackCookie
0x1800215f0  call    __security_check_cookie
0x1800215f5  lea     r11, [rsp+258h+var_8]
0x1800215fd  mov     rbx, [r11+10h]
0x180021601  mov     rsi, [r11+28h]
0x180021605  mov     rsp, r11
0x180021608  pop     rdi
0x180021609  retn
```
