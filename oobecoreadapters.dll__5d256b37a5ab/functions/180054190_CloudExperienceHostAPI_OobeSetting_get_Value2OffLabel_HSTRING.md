# CloudExperienceHostAPI::OobeSetting::get_Value2OffLabel(HSTRING__ * *)

- ea: `0x180054190`
- end: `0x1800541e9`
- name: `?get_Value2OffLabel@OobeSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `89`
- prototype: `int(CloudExperienceHostAPI::OobeSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180054190`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800541b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800541b3`

## string_xrefs

- `0x1800541c4`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeSetting::get_Value2OffLabel(
        CloudExperienceHostAPI::OobeSetting *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 20);
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
    (void *)0x90,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180054190  mov     [rsp+arg_0], rbx
0x180054195  push    rdi; int
0x180054196  sub     rsp, 20h
0x18005419a  mov     rcx, [rcx+0A0h]; sourceString
0x1800541a1  mov     r8, rdx; string
0x1800541a4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800541a8  xor     edi, edi
0x1800541aa  inc     rdx; length
0x1800541ad  cmp     [rcx+rdx*2], di
0x1800541b1  jnz     short loc_1800541AA
0x1800541b3  call    cs:__imp_WindowsCreateString
0x1800541b9  mov     ebx, eax
0x1800541bb  test    eax, eax
0x1800541bd  jns     short loc_1800541DC
0x1800541bf  mov     rcx, [rsp+28h]; this
0x1800541c4  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800541cb  mov     r9d, eax; char *
0x1800541ce  mov     edx, 90h; void *
0x1800541d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800541d8  mov     eax, ebx
0x1800541da  jmp     short loc_1800541DE
0x1800541dc  xor     eax, eax
0x1800541de  mov     rbx, [rsp+28h+arg_0]
0x1800541e3  add     rsp, 20h
0x1800541e7  pop     rdi
0x1800541e8  retn
```
