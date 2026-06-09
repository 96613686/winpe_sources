# CloudExperienceHostAPI::OobeSetting::get_ValueOffLabel(HSTRING__ * *)

- ea: `0x180054270`
- end: `0x1800542c9`
- name: `?get_ValueOffLabel@OobeSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `89`
- prototype: `int(CloudExperienceHostAPI::OobeSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180054270`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180054293`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180054293`

## string_xrefs

- `0x1800542a4`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeSetting::get_ValueOffLabel(
        CloudExperienceHostAPI::OobeSetting *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 18);
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
    (void *)0x86,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180054270  mov     [rsp+arg_0], rbx
0x180054275  push    rdi; int
0x180054276  sub     rsp, 20h
0x18005427a  mov     rcx, [rcx+90h]; sourceString
0x180054281  mov     r8, rdx; string
0x180054284  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180054288  xor     edi, edi
0x18005428a  inc     rdx; length
0x18005428d  cmp     [rcx+rdx*2], di
0x180054291  jnz     short loc_18005428A
0x180054293  call    cs:__imp_WindowsCreateString
0x180054299  mov     ebx, eax
0x18005429b  test    eax, eax
0x18005429d  jns     short loc_1800542BC
0x18005429f  mov     rcx, [rsp+28h]; this
0x1800542a4  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800542ab  mov     r9d, eax; char *
0x1800542ae  mov     edx, 86h; void *
0x1800542b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800542b8  mov     eax, ebx
0x1800542ba  jmp     short loc_1800542BE
0x1800542bc  xor     eax, eax
0x1800542be  mov     rbx, [rsp+28h+arg_0]
0x1800542c3  add     rsp, 20h
0x1800542c7  pop     rdi
0x1800542c8  retn
```
