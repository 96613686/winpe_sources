# CloudExperienceHostAPI::OobeSetting::get_CanonicalName(HSTRING__ * *)

- ea: `0x180053d20`
- end: `0x180053d76`
- name: `?get_CanonicalName@OobeSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `86`
- prototype: `int(CloudExperienceHostAPI::OobeSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180053d20`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053d40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053d40`

## string_xrefs

- `0x180053d51`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeSetting::get_CanonicalName(
        CloudExperienceHostAPI::OobeSetting *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 8);
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
    (void *)0x54,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180053d20  mov     [rsp+arg_0], rbx
0x180053d25  push    rdi; int
0x180053d26  sub     rsp, 20h
0x180053d2a  mov     rcx, [rcx+40h]; sourceString
0x180053d2e  mov     r8, rdx; string
0x180053d31  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180053d35  xor     edi, edi
0x180053d37  inc     rdx; length
0x180053d3a  cmp     [rcx+rdx*2], di
0x180053d3e  jnz     short loc_180053D37
0x180053d40  call    cs:__imp_WindowsCreateString
0x180053d46  mov     ebx, eax
0x180053d48  test    eax, eax
0x180053d4a  jns     short loc_180053D69
0x180053d4c  mov     rcx, [rsp+28h]; this
0x180053d51  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x180053d58  mov     r9d, eax; char *
0x180053d5b  mov     edx, 54h ; 'T'; void *
0x180053d60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053d65  mov     eax, ebx
0x180053d67  jmp     short loc_180053D6B
0x180053d69  xor     eax, eax
0x180053d6b  mov     rbx, [rsp+28h+arg_0]
0x180053d70  add     rsp, 20h
0x180053d74  pop     rdi
0x180053d75  retn
```
