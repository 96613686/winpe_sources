# CloudExperienceHostAPI::OobeSetting::get_Description2Off(HSTRING__ * *)

- ea: `0x180053d80`
- end: `0x180053dd6`
- name: `?get_Description2Off@OobeSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `86`
- prototype: `int(CloudExperienceHostAPI::OobeSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180053d80`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053da0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053da0`

## string_xrefs

- `0x180053db1`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeSetting::get_Description2Off(
        CloudExperienceHostAPI::OobeSetting *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 14);
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
    (void *)0x72,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180053d80  mov     [rsp+arg_0], rbx
0x180053d85  push    rdi; int
0x180053d86  sub     rsp, 20h
0x180053d8a  mov     rcx, [rcx+70h]; sourceString
0x180053d8e  mov     r8, rdx; string
0x180053d91  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180053d95  xor     edi, edi
0x180053d97  inc     rdx; length
0x180053d9a  cmp     [rcx+rdx*2], di
0x180053d9e  jnz     short loc_180053D97
0x180053da0  call    cs:__imp_WindowsCreateString
0x180053da6  mov     ebx, eax
0x180053da8  test    eax, eax
0x180053daa  jns     short loc_180053DC9
0x180053dac  mov     rcx, [rsp+28h]; this
0x180053db1  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x180053db8  mov     r9d, eax; char *
0x180053dbb  mov     edx, 72h ; 'r'; void *
0x180053dc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053dc5  mov     eax, ebx
0x180053dc7  jmp     short loc_180053DCB
0x180053dc9  xor     eax, eax
0x180053dcb  mov     rbx, [rsp+28h+arg_0]
0x180053dd0  add     rsp, 20h
0x180053dd4  pop     rdi
0x180053dd5  retn
```
