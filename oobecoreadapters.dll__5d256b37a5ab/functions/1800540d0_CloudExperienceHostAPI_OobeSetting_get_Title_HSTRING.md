# CloudExperienceHostAPI::OobeSetting::get_Title(HSTRING__ * *)

- ea: `0x1800540d0`
- end: `0x180054126`
- name: `?get_Title@OobeSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `86`
- prototype: `int(CloudExperienceHostAPI::OobeSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800076d4`
- `0x1800540d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800540f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800540f0`

## string_xrefs

- `0x180054101`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeSetting::get_Title(
        CloudExperienceHostAPI::OobeSetting *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 10);
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
    (void *)0x5E,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x1800540d0  mov     [rsp+arg_0], rbx
0x1800540d5  push    rdi; int
0x1800540d6  sub     rsp, 20h
0x1800540da  mov     rcx, [rcx+50h]; sourceString
0x1800540de  mov     r8, rdx; string
0x1800540e1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800540e5  xor     edi, edi
0x1800540e7  inc     rdx; length
0x1800540ea  cmp     [rcx+rdx*2], di
0x1800540ee  jnz     short loc_1800540E7
0x1800540f0  call    cs:__imp_WindowsCreateString
0x1800540f6  mov     ebx, eax
0x1800540f8  test    eax, eax
0x1800540fa  jns     short loc_180054119
0x1800540fc  mov     rcx, [rsp+28h]; this
0x180054101  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x180054108  mov     r9d, eax; char *
0x18005410b  mov     edx, 5Eh ; '^'; void *
0x180054110  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054115  mov     eax, ebx
0x180054117  jmp     short loc_18005411B
0x180054119  xor     eax, eax
0x18005411b  mov     rbx, [rsp+28h+arg_0]
0x180054120  add     rsp, 20h
0x180054124  pop     rdi
0x180054125  retn
```
