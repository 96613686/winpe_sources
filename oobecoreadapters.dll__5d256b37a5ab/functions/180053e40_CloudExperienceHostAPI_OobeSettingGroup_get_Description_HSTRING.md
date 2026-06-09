# CloudExperienceHostAPI::OobeSettingGroup::get_Description(HSTRING__ * *)

- ea: `0x180053e40`
- end: `0x180053e96`
- name: `?get_Description@OobeSettingGroup@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `86`
- prototype: `int(CloudExperienceHostAPI::OobeSettingGroup *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180053e40`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053e60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053e60`

## string_xrefs

- `0x180053e71`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeSettingGroup::get_Description(
        CloudExperienceHostAPI::OobeSettingGroup *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 9);
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
    (void *)0xCA,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180053e40  mov     [rsp+arg_0], rbx
0x180053e45  push    rdi; int
0x180053e46  sub     rsp, 20h
0x180053e4a  mov     rcx, [rcx+48h]; sourceString
0x180053e4e  mov     r8, rdx; string
0x180053e51  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180053e55  xor     edi, edi
0x180053e57  inc     rdx; length
0x180053e5a  cmp     [rcx+rdx*2], di
0x180053e5e  jnz     short loc_180053E57
0x180053e60  call    cs:__imp_WindowsCreateString
0x180053e66  mov     ebx, eax
0x180053e68  test    eax, eax
0x180053e6a  jns     short loc_180053E89
0x180053e6c  mov     rcx, [rsp+28h]; this
0x180053e71  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x180053e78  mov     r9d, eax; char *
0x180053e7b  mov     edx, 0CAh; void *
0x180053e80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053e85  mov     eax, ebx
0x180053e87  jmp     short loc_180053E8B
0x180053e89  xor     eax, eax
0x180053e8b  mov     rbx, [rsp+28h+arg_0]
0x180053e90  add     rsp, 20h
0x180053e94  pop     rdi
0x180053e95  retn
```
