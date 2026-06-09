# CloudExperienceHostAPI::OobeSetting::get_OnGlyph(HSTRING__ * *)

- ea: `0x180054020`
- end: `0x180054076`
- name: `?get_OnGlyph@OobeSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `86`
- prototype: `int(CloudExperienceHostAPI::OobeSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180054020`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180054040`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180054040`

## string_xrefs

- `0x180054051`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeSetting::get_OnGlyph(
        CloudExperienceHostAPI::OobeSetting *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 15);
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
    (void *)0x77,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180054020  mov     [rsp+arg_0], rbx
0x180054025  push    rdi; int
0x180054026  sub     rsp, 20h
0x18005402a  mov     rcx, [rcx+78h]; sourceString
0x18005402e  mov     r8, rdx; string
0x180054031  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180054035  xor     edi, edi
0x180054037  inc     rdx; length
0x18005403a  cmp     [rcx+rdx*2], di
0x18005403e  jnz     short loc_180054037
0x180054040  call    cs:__imp_WindowsCreateString
0x180054046  mov     ebx, eax
0x180054048  test    eax, eax
0x18005404a  jns     short loc_180054069
0x18005404c  mov     rcx, [rsp+28h]; this
0x180054051  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x180054058  mov     r9d, eax; char *
0x18005405b  mov     edx, 77h ; 'w'; void *
0x180054060  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054065  mov     eax, ebx
0x180054067  jmp     short loc_18005406B
0x180054069  xor     eax, eax
0x18005406b  mov     rbx, [rsp+28h+arg_0]
0x180054070  add     rsp, 20h
0x180054074  pop     rdi
0x180054075  retn
```
