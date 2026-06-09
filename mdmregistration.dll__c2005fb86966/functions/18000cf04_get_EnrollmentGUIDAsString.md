# get_EnrollmentGUIDAsString

- ea: `0x18000cf04`
- end: `0x18000cfad`
- name: `get_EnrollmentGUIDAsString`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013830`

## callees

- `0x1800026d0`
- `0x18000cf04`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000cf76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000cf76`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000cf44`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000cf44`

## pseudocode

```c
__int64 __fastcall get_EnrollmentGUIDAsString(GUID *a1, HSTRING *a2)
{
  GUID v2; // xmm0
  __int64 v5; // rdx
  HRESULT String; // eax
  unsigned int v7; // ecx
  GUID rguid; // [rsp+20h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+30h] [rbp-68h] BYREF

  v2 = *a1;
  sz[0] = 0;
  rguid = v2;
  if ( StringFromGUID2(&rguid, sz, 39) != 39 )
    return 2147549183LL;
  v5 = -1;
  do
    ++v5;
  while ( sz[v5] );
  String = WindowsCreateString(sz, v5, a2);
  v7 = 0;
  if ( String < 0 )
    return (unsigned int)String;
  return v7;
}

```

## disassembly

```asm
0x18000cf04  mov     [rsp+arg_10], rbx
0x18000cf09  push    rdi
0x18000cf0a  sub     rsp, 90h
0x18000cf11  mov     rax, cs:__security_cookie
0x18000cf18  xor     rax, rsp
0x18000cf1b  mov     [rsp+98h+var_18], rax
0x18000cf23  movups  xmm0, xmmword ptr [rcx]
0x18000cf26  xor     edi, edi
0x18000cf28  lea     rcx, [rsp+98h+rguid]; rguid
0x18000cf2d  mov     rbx, rdx
0x18000cf30  mov     [rsp+98h+sz], di
0x18000cf35  lea     rdx, [rsp+98h+sz]; lpsz
0x18000cf3a  movdqu  xmmword ptr [rsp+98h+rguid.Data1], xmm0
0x18000cf40  lea     r8d, [rdi+27h]; cchMax
0x18000cf44  call    cs:__imp_StringFromGUID2
0x18000cf4b  nop     dword ptr [rax+rax+00h]
0x18000cf50  cmp     eax, 27h ; '''
0x18000cf53  jz      short loc_18000CF5C
0x18000cf55  mov     eax, 8000FFFFh
0x18000cf5a  jmp     short loc_18000CF8B
0x18000cf5c  lea     rax, [rsp+98h+sz]
0x18000cf61  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000cf65  inc     rdx; length
0x18000cf68  cmp     [rax+rdx*2], di
0x18000cf6c  jnz     short loc_18000CF65
0x18000cf6e  mov     r8, rbx; string
0x18000cf71  lea     rcx, [rsp+98h+sz]; sourceString
0x18000cf76  call    cs:__imp_WindowsCreateString
0x18000cf7d  nop     dword ptr [rax+rax+00h]
0x18000cf82  test    eax, eax
0x18000cf84  mov     ecx, edi
0x18000cf86  cmovs   ecx, eax
0x18000cf89  mov     eax, ecx
0x18000cf8b  mov     rcx, [rsp+98h+var_18]
0x18000cf93  xor     rcx, rsp; StackCookie
0x18000cf96  call    __security_check_cookie
0x18000cf9b  mov     rbx, [rsp+98h+arg_10]
0x18000cfa3  add     rsp, 90h
0x18000cfaa  pop     rdi
0x18000cfab  retn
```
