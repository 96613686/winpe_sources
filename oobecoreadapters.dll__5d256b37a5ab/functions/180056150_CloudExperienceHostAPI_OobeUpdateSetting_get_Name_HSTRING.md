# CloudExperienceHostAPI::OobeUpdateSetting::get_Name(HSTRING__ * *)

- ea: `0x180056150`
- end: `0x1800561a6`
- name: `?get_Name@OobeUpdateSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `86`
- prototype: `int(CloudExperienceHostAPI::OobeUpdateSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180056150`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180056170`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180056170`

## string_xrefs

- `0x180056181`: `shellcommon\shell\oobe\core\components\winrt\oobeupdatesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeUpdateSetting::get_Name(
        CloudExperienceHostAPI::OobeUpdateSetting *this,
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
    (void *)0x39,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobeupdatesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180056150  mov     [rsp+arg_0], rbx
0x180056155  push    rdi; int
0x180056156  sub     rsp, 20h
0x18005615a  mov     rcx, [rcx+48h]; sourceString
0x18005615e  mov     r8, rdx; string
0x180056161  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180056165  xor     edi, edi
0x180056167  inc     rdx; length
0x18005616a  cmp     [rcx+rdx*2], di
0x18005616e  jnz     short loc_180056167
0x180056170  call    cs:__imp_WindowsCreateString
0x180056176  mov     ebx, eax
0x180056178  test    eax, eax
0x18005617a  jns     short loc_180056199
0x18005617c  mov     rcx, [rsp+28h]; this
0x180056181  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\oobe\\core\\compone"...
0x180056188  mov     r9d, eax; char *
0x18005618b  mov     edx, 39h ; '9'; void *
0x180056190  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056195  mov     eax, ebx
0x180056197  jmp     short loc_18005619B
0x180056199  xor     eax, eax
0x18005619b  mov     rbx, [rsp+28h+arg_0]
0x1800561a0  add     rsp, 20h
0x1800561a4  pop     rdi
0x1800561a5  retn
```
