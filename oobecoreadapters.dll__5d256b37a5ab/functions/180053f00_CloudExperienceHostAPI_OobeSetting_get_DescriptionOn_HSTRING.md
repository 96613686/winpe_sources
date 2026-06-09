# CloudExperienceHostAPI::OobeSetting::get_DescriptionOn(HSTRING__ * *)

- ea: `0x180053f00`
- end: `0x180053f56`
- name: `?get_DescriptionOn@OobeSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `86`
- prototype: `int(CloudExperienceHostAPI::OobeSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180053f00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053f20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053f20`

## string_xrefs

- `0x180053f31`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeSetting::get_DescriptionOn(
        CloudExperienceHostAPI::OobeSetting *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 11);
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
    (void *)0x63,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180053f00  mov     [rsp+arg_0], rbx
0x180053f05  push    rdi; int
0x180053f06  sub     rsp, 20h
0x180053f0a  mov     rcx, [rcx+58h]; sourceString
0x180053f0e  mov     r8, rdx; string
0x180053f11  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180053f15  xor     edi, edi
0x180053f17  inc     rdx; length
0x180053f1a  cmp     [rcx+rdx*2], di
0x180053f1e  jnz     short loc_180053F17
0x180053f20  call    cs:__imp_WindowsCreateString
0x180053f26  mov     ebx, eax
0x180053f28  test    eax, eax
0x180053f2a  jns     short loc_180053F49
0x180053f2c  mov     rcx, [rsp+28h]; this
0x180053f31  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x180053f38  mov     r9d, eax; char *
0x180053f3b  mov     edx, 63h ; 'c'; void *
0x180053f40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053f45  mov     eax, ebx
0x180053f47  jmp     short loc_180053F4B
0x180053f49  xor     eax, eax
0x180053f4b  mov     rbx, [rsp+28h+arg_0]
0x180053f50  add     rsp, 20h
0x180053f54  pop     rdi
0x180053f55  retn
```
