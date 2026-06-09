# CloudExperienceHostAPI::OobeSettingGroup::get_Title(HSTRING__ * *)

- ea: `0x180054130`
- end: `0x180054186`
- name: `?get_Title@OobeSettingGroup@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `86`
- prototype: `int(CloudExperienceHostAPI::OobeSettingGroup *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180054130`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180054150`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180054150`

## string_xrefs

- `0x180054161`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeSettingGroup::get_Title(
        CloudExperienceHostAPI::OobeSettingGroup *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 8);
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
    (void *)0xC5,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180054130  mov     [rsp+arg_0], rbx
0x180054135  push    rdi; int
0x180054136  sub     rsp, 20h
0x18005413a  mov     rcx, [rcx+40h]; sourceString
0x18005413e  mov     r8, rdx; string
0x180054141  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180054145  xor     edi, edi
0x180054147  inc     rdx; length
0x18005414a  cmp     [rcx+rdx*2], di
0x18005414e  jnz     short loc_180054147
0x180054150  call    cs:__imp_WindowsCreateString
0x180054156  mov     ebx, eax
0x180054158  test    eax, eax
0x18005415a  jns     short loc_180054179
0x18005415c  mov     rcx, [rsp+28h]; this
0x180054161  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x180054168  mov     r9d, eax; char *
0x18005416b  mov     edx, 0C5h; void *
0x180054170  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054175  mov     eax, ebx
0x180054177  jmp     short loc_18005417B
0x180054179  xor     eax, eax
0x18005417b  mov     rbx, [rsp+28h+arg_0]
0x180054180  add     rsp, 20h
0x180054184  pop     rdi
0x180054185  retn
```
