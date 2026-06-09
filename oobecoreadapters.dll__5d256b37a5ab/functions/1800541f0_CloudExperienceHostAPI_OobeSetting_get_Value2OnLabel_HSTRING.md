# CloudExperienceHostAPI::OobeSetting::get_Value2OnLabel(HSTRING__ * *)

- ea: `0x1800541f0`
- end: `0x180054249`
- name: `?get_Value2OnLabel@OobeSetting@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `89`
- prototype: `int(CloudExperienceHostAPI::OobeSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800076d4`
- `0x1800541f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180054213`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180054213`

## string_xrefs

- `0x180054224`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeSetting::get_Value2OnLabel(
        CloudExperienceHostAPI::OobeSetting *this,
        HSTRING *a2)
{
  const WCHAR *v2; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (const WCHAR *)*((_QWORD *)this + 19);
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
    (void *)0x8B,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v6;
}

```

## disassembly

```asm
0x1800541f0  mov     [rsp+arg_0], rbx
0x1800541f5  push    rdi; int
0x1800541f6  sub     rsp, 20h
0x1800541fa  mov     rcx, [rcx+98h]; sourceString
0x180054201  mov     r8, rdx; string
0x180054204  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180054208  xor     edi, edi
0x18005420a  inc     rdx; length
0x18005420d  cmp     [rcx+rdx*2], di
0x180054211  jnz     short loc_18005420A
0x180054213  call    cs:__imp_WindowsCreateString
0x180054219  mov     ebx, eax
0x18005421b  test    eax, eax
0x18005421d  jns     short loc_18005423C
0x18005421f  mov     rcx, [rsp+28h]; this
0x180054224  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x18005422b  mov     r9d, eax; char *
0x18005422e  mov     edx, 8Bh; void *
0x180054233  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054238  mov     eax, ebx
0x18005423a  jmp     short loc_18005423E
0x18005423c  xor     eax, eax
0x18005423e  mov     rbx, [rsp+28h+arg_0]
0x180054243  add     rsp, 20h
0x180054247  pop     rdi
0x180054248  retn
```
