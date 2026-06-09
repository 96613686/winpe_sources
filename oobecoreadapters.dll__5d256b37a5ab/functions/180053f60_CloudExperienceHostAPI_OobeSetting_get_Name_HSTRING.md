# CloudExperienceHostAPI::OobeSetting::get_Name(HSTRING__ * *)

- ea: `0x180053f60`
- end: `0x180053fb6`
- name: `?get_Name@OobeSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `86`
- prototype: `int(CloudExperienceHostAPI::OobeSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180053f60`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053f80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053f80`

## string_xrefs

- `0x180053f91`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeSetting::get_Name(
        CloudExperienceHostAPI::OobeSetting *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 9);
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
    (void *)0x59,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180053f60  mov     [rsp+arg_0], rbx
0x180053f65  push    rdi; int
0x180053f66  sub     rsp, 20h
0x180053f6a  mov     rcx, [rcx+48h]; sourceString
0x180053f6e  mov     r8, rdx; string
0x180053f71  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180053f75  xor     edi, edi
0x180053f77  inc     rdx; length
0x180053f7a  cmp     [rcx+rdx*2], di
0x180053f7e  jnz     short loc_180053F77
0x180053f80  call    cs:__imp_WindowsCreateString
0x180053f86  mov     ebx, eax
0x180053f88  test    eax, eax
0x180053f8a  jns     short loc_180053FA9
0x180053f8c  mov     rcx, [rsp+28h]; this
0x180053f91  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x180053f98  mov     r9d, eax; char *
0x180053f9b  mov     edx, 59h ; 'Y'; void *
0x180053fa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053fa5  mov     eax, ebx
0x180053fa7  jmp     short loc_180053FAB
0x180053fa9  xor     eax, eax
0x180053fab  mov     rbx, [rsp+28h+arg_0]
0x180053fb0  add     rsp, 20h
0x180053fb4  pop     rdi
0x180053fb5  retn
```
