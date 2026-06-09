# CloudExperienceHostAPI::OobeUpdateSetting::get_ValueOffLabel(HSTRING__ * *)

- ea: `0x1800563e0`
- end: `0x180056436`
- name: `?get_ValueOffLabel@OobeUpdateSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `86`
- prototype: `int(CloudExperienceHostAPI::OobeUpdateSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800076d4`
- `0x1800563e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180056400`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180056400`

## string_xrefs

- `0x180056411`: `shellcommon\shell\oobe\core\components\winrt\oobeupdatesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeUpdateSetting::get_ValueOffLabel(
        CloudExperienceHostAPI::OobeUpdateSetting *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 13);
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
    (void *)0x4D,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobeupdatesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x1800563e0  mov     [rsp+arg_0], rbx
0x1800563e5  push    rdi; int
0x1800563e6  sub     rsp, 20h
0x1800563ea  mov     rcx, [rcx+68h]; sourceString
0x1800563ee  mov     r8, rdx; string
0x1800563f1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800563f5  xor     edi, edi
0x1800563f7  inc     rdx; length
0x1800563fa  cmp     [rcx+rdx*2], di
0x1800563fe  jnz     short loc_1800563F7
0x180056400  call    cs:__imp_WindowsCreateString
0x180056406  mov     ebx, eax
0x180056408  test    eax, eax
0x18005640a  jns     short loc_180056429
0x18005640c  mov     rcx, [rsp+28h]; this
0x180056411  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\oobe\\core\\compone"...
0x180056418  mov     r9d, eax; char *
0x18005641b  mov     edx, 4Dh ; 'M'; void *
0x180056420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056425  mov     eax, ebx
0x180056427  jmp     short loc_18005642B
0x180056429  xor     eax, eax
0x18005642b  mov     rbx, [rsp+28h+arg_0]
0x180056430  add     rsp, 20h
0x180056434  pop     rdi
0x180056435  retn
```
