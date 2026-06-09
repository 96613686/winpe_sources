# CloudExperienceHostAPI::OobeUpdateSetting::get_Description(HSTRING__ * *)

- ea: `0x1800560e0`
- end: `0x180056136`
- name: `?get_Description@OobeUpdateSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `86`
- prototype: `int(CloudExperienceHostAPI::OobeUpdateSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800076d4`
- `0x1800560e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180056100`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180056100`

## string_xrefs

- `0x180056111`: `shellcommon\shell\oobe\core\components\winrt\oobeupdatesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeUpdateSetting::get_Description(
        CloudExperienceHostAPI::OobeUpdateSetting *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 11);
  v4 = -1;
  do
    ++v4;
  while ( v2[v4] );
  String = WindowsCreateString(v2, v4, a2);
  v6 = String;
  if ( String >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x43,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobeupdatesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x1800560e0  mov     [rsp+arg_0], rbx
0x1800560e5  push    rdi; int
0x1800560e6  sub     rsp, 20h
0x1800560ea  mov     rcx, [rcx+58h]; sourceString
0x1800560ee  mov     r8, rdx; string
0x1800560f1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800560f5  xor     edi, edi
0x1800560f7  inc     rdx; length
0x1800560fa  cmp     [rcx+rdx*2], di
0x1800560fe  jnz     short loc_1800560F7
0x180056100  call    cs:__imp_WindowsCreateString
0x180056106  mov     ebx, eax
0x180056108  test    eax, eax
0x18005610a  jns     short loc_180056129
0x18005610c  mov     rcx, [rsp+28h]; this
0x180056111  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\oobe\\core\\compone"...
0x180056118  mov     r9d, eax; char *
0x18005611b  mov     edx, 43h ; 'C'; void *
0x180056120  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056125  mov     eax, ebx
0x180056127  jmp     short loc_18005612B
0x180056129  xor     eax, eax
0x18005612b  mov     rbx, [rsp+28h+arg_0]
0x180056130  add     rsp, 20h
0x180056134  pop     rdi
0x180056135  retn
```
