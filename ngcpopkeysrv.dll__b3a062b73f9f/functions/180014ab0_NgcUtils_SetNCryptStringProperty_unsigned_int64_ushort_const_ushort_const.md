# NgcUtils::SetNCryptStringProperty(unsigned __int64,ushort const *,ushort const *)

- ea: `0x180014ab0`
- end: `0x180014b11`
- name: `?SetNCryptStringProperty@NgcUtils@@YAJ_KPEBG1@Z`
- size: `97`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014588`
- `0x18001ba2c`

## callees

- `0x18000b0fc`
- `0x180014ab0`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x180014adb`
- `ncrypt!NCryptSetProperty` at `0x180014adb`

## string_xrefs

- `0x180014aec`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::SetNCryptStringProperty(
        NgcUtils *this,
        const WCHAR *a2,
        BYTE *a3,
        const unsigned __int16 *a4)
{
  __int64 v4; // r9
  SECURITY_STATUS v5; // eax
  unsigned int v6; // ebx
  DWORD dwFlags; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !a3 )
    return 0;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)&a3[2 * v4] );
  v5 = NCryptSetProperty((NCRYPT_HANDLE)this, a2, a3, 2 * v4 + 2, 0);
  v6 = v5;
  if ( v5 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x187,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
    (const char *)(unsigned int)v5,
    dwFlags);
  return v6;
}

```

## disassembly

```asm
0x180014ab0  mov     [rsp+arg_0], rbx
0x180014ab5  push    rdi
0x180014ab6  sub     rsp, 30h
0x180014aba  xor     edi, edi
0x180014abc  test    r8, r8
0x180014abf  jz      short loc_180014B04
0x180014ac1  or      r9, 0FFFFFFFFFFFFFFFFh
0x180014ac5  inc     r9
0x180014ac8  cmp     [r8+r9*2], di
0x180014acd  jnz     short loc_180014AC5
0x180014acf  lea     r9d, ds:2[r9*2]; cbInput
0x180014ad7  mov     [rsp+38h+dwFlags], edi; int
0x180014adb  call    cs:__imp_NCryptSetProperty
0x180014ae1  mov     ebx, eax
0x180014ae3  test    eax, eax
0x180014ae5  jns     short loc_180014B04
0x180014ae7  mov     rcx, [rsp+38h]; this
0x180014aec  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180014af3  mov     r9d, eax; char *
0x180014af6  mov     edx, 187h; void *
0x180014afb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014b00  mov     eax, ebx
0x180014b02  jmp     short loc_180014B06
0x180014b04  xor     eax, eax
0x180014b06  mov     rbx, [rsp+38h+arg_0]
0x180014b0b  add     rsp, 30h
0x180014b0f  pop     rdi
0x180014b10  retn
```
