# CloudExperienceHostAPI::OobeUpdateSetting::get_ValueOnLabel(HSTRING__ * *)

- ea: `0x180056440`
- end: `0x180056496`
- name: `?get_ValueOnLabel@OobeUpdateSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `86`
- prototype: `int(CloudExperienceHostAPI::OobeUpdateSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180056440`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180056460`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180056460`

## string_xrefs

- `0x180056471`: `shellcommon\shell\oobe\core\components\winrt\oobeupdatesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeUpdateSetting::get_ValueOnLabel(
        CloudExperienceHostAPI::OobeUpdateSetting *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 12);
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
    (void *)0x48,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobeupdatesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180056440  mov     [rsp+arg_0], rbx
0x180056445  push    rdi; int
0x180056446  sub     rsp, 20h
0x18005644a  mov     rcx, [rcx+60h]; sourceString
0x18005644e  mov     r8, rdx; string
0x180056451  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180056455  xor     edi, edi
0x180056457  inc     rdx; length
0x18005645a  cmp     [rcx+rdx*2], di
0x18005645e  jnz     short loc_180056457
0x180056460  call    cs:__imp_WindowsCreateString
0x180056466  mov     ebx, eax
0x180056468  test    eax, eax
0x18005646a  jns     short loc_180056489
0x18005646c  mov     rcx, [rsp+28h]; this
0x180056471  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\oobe\\core\\compone"...
0x180056478  mov     r9d, eax; char *
0x18005647b  mov     edx, 48h ; 'H'; void *
0x180056480  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056485  mov     eax, ebx
0x180056487  jmp     short loc_18005648B
0x180056489  xor     eax, eax
0x18005648b  mov     rbx, [rsp+28h+arg_0]
0x180056490  add     rsp, 20h
0x180056494  pop     rdi
0x180056495  retn
```
