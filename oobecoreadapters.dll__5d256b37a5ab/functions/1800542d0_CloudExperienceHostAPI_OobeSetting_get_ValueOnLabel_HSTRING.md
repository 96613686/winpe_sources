# CloudExperienceHostAPI::OobeSetting::get_ValueOnLabel(HSTRING__ * *)

- ea: `0x1800542d0`
- end: `0x180054329`
- name: `?get_ValueOnLabel@OobeSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `89`
- prototype: `int(CloudExperienceHostAPI::OobeSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800076d4`
- `0x1800542d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800542f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800542f3`

## string_xrefs

- `0x180054304`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeSetting::get_ValueOnLabel(
        CloudExperienceHostAPI::OobeSetting *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 17);
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
    (void *)0x81,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x1800542d0  mov     [rsp+arg_0], rbx
0x1800542d5  push    rdi; int
0x1800542d6  sub     rsp, 20h
0x1800542da  mov     rcx, [rcx+88h]; sourceString
0x1800542e1  mov     r8, rdx; string
0x1800542e4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800542e8  xor     edi, edi
0x1800542ea  inc     rdx; length
0x1800542ed  cmp     [rcx+rdx*2], di
0x1800542f1  jnz     short loc_1800542EA
0x1800542f3  call    cs:__imp_WindowsCreateString
0x1800542f9  mov     ebx, eax
0x1800542fb  test    eax, eax
0x1800542fd  jns     short loc_18005431C
0x1800542ff  mov     rcx, [rsp+28h]; this
0x180054304  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005430b  mov     r9d, eax; char *
0x18005430e  mov     edx, 81h; void *
0x180054313  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054318  mov     eax, ebx
0x18005431a  jmp     short loc_18005431E
0x18005431c  xor     eax, eax
0x18005431e  mov     rbx, [rsp+28h+arg_0]
0x180054323  add     rsp, 20h
0x180054327  pop     rdi
0x180054328  retn
```
