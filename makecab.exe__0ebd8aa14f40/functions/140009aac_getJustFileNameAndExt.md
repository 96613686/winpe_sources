# getJustFileNameAndExt

- ea: `0x140009aac`
- end: `0x140009b2f`
- name: `getJustFileNameAndExt`
- size: `131`
- prototype: `__int64 __fastcall(LPCSTR lpCurrentChar)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140006590`
- `0x140007e18`
- `0x140008f70`

## callees

- `0x140008620`
- `0x140009aac`

## import_xrefs

- `USER32!CharNextExA` at `0x140009aec`
- `USER32!CharNextExA` at `0x140009aec`

## pseudocode

```c
LPCSTR __fastcall getJustFileNameAndExt(LPCSTR lpCurrentChar, __int64 a2)
{
  LPSTR v2; // rax
  const CHAR *v5; // rdx
  LPCSTR v6; // rbx
  __int64 v7; // rcx

  LOBYTE(v2) = *lpCurrentChar;
  if ( *lpCurrentChar )
  {
    v5 = lpCurrentChar;
    v6 = lpCurrentChar;
    do
    {
      LOBYTE(v2) = (_BYTE)v2 - 47;
      if ( (unsigned __int8)v2 <= 0x2Du )
      {
        v7 = 0x200000000801LL;
        if ( _bittest64(&v7, (unsigned __int64)v2) )
          v6 = v5 + 1;
      }
      v2 = CharNextExA(0, v5, 0);
      v5 = v2;
      LOBYTE(v2) = *v2;
    }
    while ( (_BYTE)v2 );
    if ( *v6 )
      return v6;
  }
  ErrSet(a2, (int)"Missing file name: %1", "%s", lpCurrentChar);
  return 0;
}

```

## disassembly

```asm
0x140009aac  mov     [rsp+arg_0], rbx
0x140009ab1  mov     [rsp+arg_8], rsi
0x140009ab6  push    rdi
0x140009ab7  sub     rsp, 20h
0x140009abb  mov     al, [rcx]
0x140009abd  mov     rsi, rdx
0x140009ac0  mov     rdi, rcx
0x140009ac3  test    al, al
0x140009ac5  jz      short loc_140009B04
0x140009ac7  mov     rdx, rcx; lpCurrentChar
0x140009aca  mov     rbx, rcx
0x140009acd  sub     al, 2Fh ; '/'
0x140009acf  cmp     al, 2Dh ; '-'
0x140009ad1  ja      short loc_140009AE7
0x140009ad3  mov     rcx, 200000000801h
0x140009add  bt      rcx, rax
0x140009ae1  jnb     short loc_140009AE7
0x140009ae3  lea     rbx, [rdx+1]
0x140009ae7  xor     ecx, ecx; CodePage
0x140009ae9  xor     r8d, r8d; dwFlags
0x140009aec  call    cs:__imp_CharNextExA
0x140009af2  mov     rdx, rax
0x140009af5  mov     al, [rax]
0x140009af7  test    al, al
0x140009af9  jnz     short loc_140009ACD
0x140009afb  cmp     [rbx], al
0x140009afd  jz      short loc_140009B04
0x140009aff  mov     rax, rbx
0x140009b02  jmp     short loc_140009B1F
0x140009b04  mov     r9, rdi
0x140009b07  lea     r8, aS_4; "%s"
0x140009b0e  lea     rdx, aMissingFileNam; "Missing file name: %1"
0x140009b15  mov     rcx, rsi
0x140009b18  call    ErrSet
0x140009b1d  xor     eax, eax
0x140009b1f  mov     rbx, [rsp+28h+arg_0]
0x140009b24  mov     rsi, [rsp+28h+arg_8]
0x140009b29  add     rsp, 20h
0x140009b2d  pop     rdi
0x140009b2e  retn
```
