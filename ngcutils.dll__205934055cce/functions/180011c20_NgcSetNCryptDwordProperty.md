# NgcSetNCryptDwordProperty

- ea: `0x180011c20`
- end: `0x180011cb6`
- name: `NgcSetNCryptDwordProperty`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a5b4`
- `0x180011c20`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x180011c65`
- `ncrypt!NCryptSetProperty` at `0x180011c65`

## string_xrefs

- `0x180011c38`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011c92`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011c79`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcSetNCryptDwordProperty(NCRYPT_HANDLE a1, const WCHAR *a2, int a3)
{
  SECURITY_STATUS v4; // eax
  unsigned int v5; // ebx
  DWORD dwFlags; // [rsp+20h] [rbp-18h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-18h]
  DWORD dwFlagsb; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int pbInput; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    pbInput = a3;
    v4 = NCryptSetProperty(a1, a2, (PBYTE)&pbInput, 4u, 0);
    v5 = v4;
    if ( v4 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x160,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
        (const char *)(unsigned int)v4,
        dwFlagsa);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
        (const char *)v5,
        dwFlagsb);
      return v5;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      dwFlags);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180011c20  push    rbx
0x180011c22  sub     rsp, 30h
0x180011c26  test    rdx, rdx
0x180011c29  jnz     short loc_180011C4D
0x180011c2b  mov     rcx, [rsp+38h]; this
0x180011c30  mov     ebx, 80004003h
0x180011c35  mov     r9d, ebx; char *
0x180011c38  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011c3f  mov     edx, 0C1h; void *
0x180011c44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011c49  mov     eax, ebx
0x180011c4b  jmp     short loc_180011CAF
0x180011c4d  mov     [rsp+38h+pbInput], r8d
0x180011c52  mov     [rsp+38h+dwFlags], 0; int
0x180011c5a  mov     r9d, 4; cbInput
0x180011c60  lea     r8, [rsp+38h+pbInput]; pbInput
0x180011c65  call    cs:__imp_NCryptSetProperty
0x180011c6b  mov     ebx, eax
0x180011c6d  test    eax, eax
0x180011c6f  jns     short loc_180011CA7
0x180011c71  mov     rcx, [rsp+38h]; this
0x180011c76  mov     r9d, eax; char *
0x180011c79  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011c80  mov     edx, 160h; void *
0x180011c85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011c8a  mov     rcx, [rsp+38h]; this
0x180011c8f  mov     r9d, ebx; char *
0x180011c92  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011c99  mov     edx, 0C3h; void *
0x180011c9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011ca3  mov     eax, ebx
0x180011ca5  jmp     short loc_180011CAF
0x180011ca7  xor     eax, eax
0x180011ca9  jmp     short loc_180011CAF
0x180011cab  mov     eax, [rsp+38h+pbInput]
0x180011caf  add     rsp, 30h
0x180011cb3  pop     rbx
0x180011cb4  retn
```
