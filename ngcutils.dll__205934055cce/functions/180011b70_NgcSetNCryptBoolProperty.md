# NgcSetNCryptBoolProperty

- ea: `0x180011b70`
- end: `0x180011c0b`
- name: `NgcSetNCryptBoolProperty`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a5b4`
- `0x180011b70`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x180011bba`
- `ncrypt!NCryptSetProperty` at `0x180011bba`

## string_xrefs

- `0x180011b88`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011be7`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011bce`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcSetNCryptBoolProperty(NCRYPT_HANDLE a1, const WCHAR *a2, int a3)
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
    if ( a3 && (v4 = NCryptSetProperty(a1, a2, (PBYTE)&pbInput, 4u, 0), v5 = v4, v4 < 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x173,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
        (const char *)(unsigned int)v4,
        dwFlagsa);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
        (const char *)v5,
        dwFlagsb);
      return v5;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      dwFlags);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180011b70  push    rbx
0x180011b72  sub     rsp, 30h
0x180011b76  test    rdx, rdx
0x180011b79  jnz     short loc_180011B9D
0x180011b7b  mov     rcx, [rsp+38h]; this
0x180011b80  mov     ebx, 80004003h
0x180011b85  mov     r9d, ebx; char *
0x180011b88  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011b8f  mov     edx, 0CBh; void *
0x180011b94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011b99  mov     eax, ebx
0x180011b9b  jmp     short loc_180011C04
0x180011b9d  mov     [rsp+38h+pbInput], r8d
0x180011ba2  test    r8d, r8d
0x180011ba5  jz      short loc_180011BFC
0x180011ba7  mov     [rsp+38h+dwFlags], 0; int
0x180011baf  mov     r9d, 4; cbInput
0x180011bb5  lea     r8, [rsp+38h+pbInput]; pbInput
0x180011bba  call    cs:__imp_NCryptSetProperty
0x180011bc0  mov     ebx, eax
0x180011bc2  test    eax, eax
0x180011bc4  jns     short loc_180011BFC
0x180011bc6  mov     rcx, [rsp+38h]; this
0x180011bcb  mov     r9d, eax; char *
0x180011bce  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011bd5  mov     edx, 173h; void *
0x180011bda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011bdf  mov     rcx, [rsp+38h]; this
0x180011be4  mov     r9d, ebx; char *
0x180011be7  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011bee  mov     edx, 0CDh; void *
0x180011bf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011bf8  mov     eax, ebx
0x180011bfa  jmp     short loc_180011C04
0x180011bfc  xor     eax, eax
0x180011bfe  jmp     short loc_180011C04
0x180011c00  mov     eax, [rsp+38h+pbInput]
0x180011c04  add     rsp, 30h
0x180011c08  pop     rbx
0x180011c09  retn
```
