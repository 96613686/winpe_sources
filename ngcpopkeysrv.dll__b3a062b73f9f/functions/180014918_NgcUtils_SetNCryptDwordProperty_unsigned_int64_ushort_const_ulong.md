# NgcUtils::SetNCryptDwordProperty(unsigned __int64,ushort const *,ulong)

- ea: `0x180014918`
- end: `0x180014966`
- name: `?SetNCryptDwordProperty@NgcUtils@@YAJ_KPEBGK@Z`
- size: `78`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, unsigned __int64, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016328`
- `0x1800187a0`
- `0x18001b0b4`

## callees

- `0x18000b0fc`
- `0x180014918`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x180014935`
- `ncrypt!NCryptSetProperty` at `0x180014935`

## string_xrefs

- `0x180014946`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::SetNCryptDwordProperty(NgcUtils *this, const WCHAR *a2, const unsigned __int16 *a3)
{
  SECURITY_STATUS v3; // eax
  unsigned int v4; // ebx
  DWORD dwFlags; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int pbInput; // [rsp+50h] [rbp+18h] BYREF

  pbInput = (int)a3;
  v3 = NCryptSetProperty((NCRYPT_HANDLE)this, a2, (PBYTE)&pbInput, 4u, 0);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x160,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
    (const char *)(unsigned int)v3,
    dwFlags);
  return v4;
}

```

## disassembly

```asm
0x180014918  mov     [rsp+pbInput], r8d
0x18001491d  push    rbx
0x18001491e  sub     rsp, 30h
0x180014922  mov     r9d, 4; cbInput
0x180014928  mov     [rsp+38h+dwFlags], 0; int
0x180014930  lea     r8, [rsp+38h+pbInput]; pbInput
0x180014935  call    cs:__imp_NCryptSetProperty
0x18001493b  mov     ebx, eax
0x18001493d  test    eax, eax
0x18001493f  jns     short loc_18001495E
0x180014941  mov     rcx, [rsp+38h]; this
0x180014946  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001494d  mov     r9d, eax; char *
0x180014950  mov     edx, 160h; void *
0x180014955  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001495a  mov     eax, ebx
0x18001495c  jmp     short loc_180014960
0x18001495e  xor     eax, eax
0x180014960  add     rsp, 30h
0x180014964  pop     rbx
0x180014965  retn
```
