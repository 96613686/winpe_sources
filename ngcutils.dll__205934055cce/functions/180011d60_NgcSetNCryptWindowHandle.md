# NgcSetNCryptWindowHandle

- ea: `0x180011d60`
- end: `0x180011ddb`
- name: `NgcSetNCryptWindowHandle`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a5b4`
- `0x180011d60`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x180011d8a`
- `ncrypt!NCryptSetProperty` at `0x180011d8a`

## string_xrefs

- `0x180011db7`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011d9e`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcSetNCryptWindowHandle(NCRYPT_HANDLE a1, __int64 a2)
{
  SECURITY_STATUS v2; // eax
  unsigned int v3; // ebx
  DWORD dwFlags; // [rsp+20h] [rbp-18h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 pbInput; // [rsp+48h] [rbp+10h] BYREF

  pbInput = a2;
  if ( !a2 )
    return 0;
  v2 = NCryptSetProperty(a1, L"HWND Handle", (PBYTE)&pbInput, 8u, 0);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x114,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
    (const char *)(unsigned int)v2,
    dwFlags);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB9,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
    (const char *)v3,
    dwFlagsa);
  return v3;
}

```

## disassembly

```asm
0x180011d60  push    rbx
0x180011d62  sub     rsp, 30h
0x180011d66  mov     [rsp+38h+pbInput], rdx
0x180011d6b  test    rdx, rdx
0x180011d6e  jz      short loc_180011DCC
0x180011d70  mov     [rsp+38h+dwFlags], 0; int
0x180011d78  mov     r9d, 8; cbInput
0x180011d7e  lea     r8, [rsp+38h+pbInput]; pbInput
0x180011d83  lea     rdx, aHwndHandle; "HWND Handle"
0x180011d8a  call    cs:__imp_NCryptSetProperty
0x180011d90  mov     ebx, eax
0x180011d92  test    eax, eax
0x180011d94  jns     short loc_180011DCC
0x180011d96  mov     rcx, [rsp+38h]; this
0x180011d9b  mov     r9d, eax; char *
0x180011d9e  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011da5  mov     edx, 114h; void *
0x180011daa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011daf  mov     rcx, [rsp+38h]; this
0x180011db4  mov     r9d, ebx; char *
0x180011db7  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011dbe  mov     edx, 0B9h; void *
0x180011dc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011dc8  mov     eax, ebx
0x180011dca  jmp     short loc_180011DD4
0x180011dcc  xor     eax, eax
0x180011dce  jmp     short loc_180011DD4
0x180011dd0  mov     eax, dword ptr [rsp+38h+pbInput]
0x180011dd4  add     rsp, 30h
0x180011dd8  pop     rbx
0x180011dd9  retn
```
