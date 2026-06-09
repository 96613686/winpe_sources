# GetNumGlyphs

- ea: `0x180019ac4`
- end: `0x180019b0f`
- name: `GetNumGlyphs`
- size: `75`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180007cd4`
- `0x180007fa4`
- `0x18000e214`
- `0x1800175f4`

## callees

- `0x180019a40`
- `0x180019ac4`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall GetNumGlyphs(__int64 a1)
{
  __int64 result; // rax
  _OWORD v2[2]; // [rsp+20h] [rbp-38h] BYREF

  memset(v2, 0, sizeof(v2));
  result = GetGeneric(a1, (__int64)v2, 3u);
  if ( (_DWORD)result )
    return WORD2(v2[0]);
  return result;
}

```

## disassembly

```asm
0x180019ac4  sub     rsp, 58h
0x180019ac8  mov     rax, cs:__security_cookie
0x180019acf  xor     rax, rsp
0x180019ad2  mov     [rsp+58h+var_18], rax
0x180019ad7  xorps   xmm0, xmm0
0x180019ada  lea     rdx, [rsp+58h+var_38]
0x180019adf  mov     r8d, 3
0x180019ae5  movups  [rsp+58h+var_38], xmm0
0x180019aea  movups  [rsp+58h+var_28], xmm0
0x180019aef  call    GetGeneric
0x180019af4  test    eax, eax
0x180019af6  jz      short loc_180019AFD
0x180019af8  movzx   eax, word ptr [rsp+58h+var_38+4]
0x180019afd  mov     rcx, [rsp+58h+var_18]
0x180019b02  xor     rcx, rsp; StackCookie
0x180019b05  call    __security_check_cookie
0x180019b0a  add     rsp, 58h
0x180019b0e  retn
```
