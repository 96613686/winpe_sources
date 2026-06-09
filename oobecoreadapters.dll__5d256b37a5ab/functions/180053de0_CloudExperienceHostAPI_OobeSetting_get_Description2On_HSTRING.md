# CloudExperienceHostAPI::OobeSetting::get_Description2On(HSTRING__ * *)

- ea: `0x180053de0`
- end: `0x180053e36`
- name: `?get_Description2On@OobeSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `86`
- prototype: `int(CloudExperienceHostAPI::OobeSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180053de0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053e00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053e00`

## string_xrefs

- `0x180053e11`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeSetting::get_Description2On(
        CloudExperienceHostAPI::OobeSetting *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 13);
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
    (void *)0x6D,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180053de0  mov     [rsp+arg_0], rbx
0x180053de5  push    rdi; int
0x180053de6  sub     rsp, 20h
0x180053dea  mov     rcx, [rcx+68h]; sourceString
0x180053dee  mov     r8, rdx; string
0x180053df1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180053df5  xor     edi, edi
0x180053df7  inc     rdx; length
0x180053dfa  cmp     [rcx+rdx*2], di
0x180053dfe  jnz     short loc_180053DF7
0x180053e00  call    cs:__imp_WindowsCreateString
0x180053e06  mov     ebx, eax
0x180053e08  test    eax, eax
0x180053e0a  jns     short loc_180053E29
0x180053e0c  mov     rcx, [rsp+28h]; this
0x180053e11  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x180053e18  mov     r9d, eax; char *
0x180053e1b  mov     edx, 6Dh ; 'm'; void *
0x180053e20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053e25  mov     eax, ebx
0x180053e27  jmp     short loc_180053E2B
0x180053e29  xor     eax, eax
0x180053e2b  mov     rbx, [rsp+28h+arg_0]
0x180053e30  add     rsp, 20h
0x180053e34  pop     rdi
0x180053e35  retn
```
