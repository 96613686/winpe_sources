# CloudExperienceHostAPI::OobeUpdateSetting::get_Title(HSTRING__ * *)

- ea: `0x180056370`
- end: `0x1800563c6`
- name: `?get_Title@OobeUpdateSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `86`
- prototype: `int(CloudExperienceHostAPI::OobeUpdateSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180056370`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180056390`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180056390`

## string_xrefs

- `0x1800563a1`: `shellcommon\shell\oobe\core\components\winrt\oobeupdatesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeUpdateSetting::get_Title(
        CloudExperienceHostAPI::OobeUpdateSetting *this,
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
    (void *)0x3E,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobeupdatesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180056370  mov     [rsp+arg_0], rbx
0x180056375  push    rdi; int
0x180056376  sub     rsp, 20h
0x18005637a  mov     rcx, [rcx+50h]; sourceString
0x18005637e  mov     r8, rdx; string
0x180056381  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180056385  xor     edi, edi
0x180056387  inc     rdx; length
0x18005638a  cmp     [rcx+rdx*2], di
0x18005638e  jnz     short loc_180056387
0x180056390  call    cs:__imp_WindowsCreateString
0x180056396  mov     ebx, eax
0x180056398  test    eax, eax
0x18005639a  jns     short loc_1800563B9
0x18005639c  mov     rcx, [rsp+28h]; this
0x1800563a1  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800563a8  mov     r9d, eax; char *
0x1800563ab  mov     edx, 3Eh ; '>'; void *
0x1800563b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800563b5  mov     eax, ebx
0x1800563b7  jmp     short loc_1800563BB
0x1800563b9  xor     eax, eax
0x1800563bb  mov     rbx, [rsp+28h+arg_0]
0x1800563c0  add     rsp, 20h
0x1800563c4  pop     rdi
0x1800563c5  retn
```
