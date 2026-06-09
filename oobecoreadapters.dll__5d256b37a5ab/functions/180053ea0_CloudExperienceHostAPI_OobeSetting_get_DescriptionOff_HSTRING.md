# CloudExperienceHostAPI::OobeSetting::get_DescriptionOff(HSTRING__ * *)

- ea: `0x180053ea0`
- end: `0x180053ef6`
- name: `?get_DescriptionOff@OobeSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `86`
- prototype: `int(CloudExperienceHostAPI::OobeSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180053ea0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053ec0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053ec0`

## string_xrefs

- `0x180053ed1`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeSetting::get_DescriptionOff(
        CloudExperienceHostAPI::OobeSetting *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 12);
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
    (void *)0x68,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180053ea0  mov     [rsp+arg_0], rbx
0x180053ea5  push    rdi; int
0x180053ea6  sub     rsp, 20h
0x180053eaa  mov     rcx, [rcx+60h]; sourceString
0x180053eae  mov     r8, rdx; string
0x180053eb1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180053eb5  xor     edi, edi
0x180053eb7  inc     rdx; length
0x180053eba  cmp     [rcx+rdx*2], di
0x180053ebe  jnz     short loc_180053EB7
0x180053ec0  call    cs:__imp_WindowsCreateString
0x180053ec6  mov     ebx, eax
0x180053ec8  test    eax, eax
0x180053eca  jns     short loc_180053EE9
0x180053ecc  mov     rcx, [rsp+28h]; this
0x180053ed1  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x180053ed8  mov     r9d, eax; char *
0x180053edb  mov     edx, 68h ; 'h'; void *
0x180053ee0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053ee5  mov     eax, ebx
0x180053ee7  jmp     short loc_180053EEB
0x180053ee9  xor     eax, eax
0x180053eeb  mov     rbx, [rsp+28h+arg_0]
0x180053ef0  add     rsp, 20h
0x180053ef4  pop     rdi
0x180053ef5  retn
```
