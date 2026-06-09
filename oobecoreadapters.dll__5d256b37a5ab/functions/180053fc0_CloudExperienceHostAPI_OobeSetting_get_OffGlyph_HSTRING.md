# CloudExperienceHostAPI::OobeSetting::get_OffGlyph(HSTRING__ * *)

- ea: `0x180053fc0`
- end: `0x180054019`
- name: `?get_OffGlyph@OobeSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `89`
- prototype: `int(CloudExperienceHostAPI::OobeSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180053fc0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053fe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053fe3`

## string_xrefs

- `0x180053ff4`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeSetting::get_OffGlyph(
        CloudExperienceHostAPI::OobeSetting *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 16);
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
    (void *)0x7C,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180053fc0  mov     [rsp+arg_0], rbx
0x180053fc5  push    rdi; int
0x180053fc6  sub     rsp, 20h
0x180053fca  mov     rcx, [rcx+80h]; sourceString
0x180053fd1  mov     r8, rdx; string
0x180053fd4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180053fd8  xor     edi, edi
0x180053fda  inc     rdx; length
0x180053fdd  cmp     [rcx+rdx*2], di
0x180053fe1  jnz     short loc_180053FDA
0x180053fe3  call    cs:__imp_WindowsCreateString
0x180053fe9  mov     ebx, eax
0x180053feb  test    eax, eax
0x180053fed  jns     short loc_18005400C
0x180053fef  mov     rcx, [rsp+28h]; this
0x180053ff4  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x180053ffb  mov     r9d, eax; char *
0x180053ffe  mov     edx, 7Ch ; '|'; void *
0x180054003  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054008  mov     eax, ebx
0x18005400a  jmp     short loc_18005400E
0x18005400c  xor     eax, eax
0x18005400e  mov     rbx, [rsp+28h+arg_0]
0x180054013  add     rsp, 20h
0x180054017  pop     rdi
0x180054018  retn
```
