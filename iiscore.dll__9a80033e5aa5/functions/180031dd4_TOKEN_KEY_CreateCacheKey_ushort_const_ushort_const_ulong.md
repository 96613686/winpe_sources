# TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)

- ea: `0x180031dd4`
- end: `0x180031e4f`
- name: `?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z`
- size: `123`
- prototype: `int __fastcall(TOKEN_KEY *this, const unsigned __int16 *, const BYTE *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001b8a0`
- `0x180031d28`

## callees

- `0x180031dd4`
- `0x180032180`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180031e0b`
- `msvcrt!_wcsupr` at `0x180031e0b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180031e02`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180031e02`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180031df1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180031df1`

## pseudocode

```c
int __fastcall TOKEN_KEY::CreateCacheKey(TOKEN_KEY *this, const unsigned __int16 *a2, const BYTE *a3, int a4)
{
  const unsigned __int16 *v7; // rbx
  int result; // eax
  wchar_t *Str; // rax
  TOKEN_KEY *v10; // rcx
  int i; // ecx
  unsigned __int16 v12; // ax

  v7 = a2;
  result = STRU::Copy((TOKEN_KEY *)((char *)this + 8), a2);
  if ( result >= 0 )
  {
    Str = STRU::QueryStr((TOKEN_KEY *)((char *)this + 8));
    _wcsupr(Str);
    result = TOKEN_KEY::GeneratePasswordHash(v10, a3, (TOKEN_KEY *)((char *)this + 64));
    if ( result >= 0 )
    {
      *((_DWORD *)this + 30) = a4;
      for ( i = 0; ; i = v12 + 101 * i )
      {
        v12 = *v7;
        if ( !*v7 )
          break;
        ++v7;
      }
      *((_DWORD *)this + 31) = i;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180031dd4  push    rbx
0x180031dd6  push    rbp
0x180031dd7  push    rsi
0x180031dd8  push    rdi
0x180031dd9  push    r14
0x180031ddb  push    r15
0x180031ddd  sub     rsp, 28h
0x180031de1  mov     rdi, rcx
0x180031de4  mov     esi, r9d
0x180031de7  add     rcx, 8
0x180031deb  mov     r14, r8
0x180031dee  mov     rbx, rdx
0x180031df1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180031df7  xor     r15d, r15d
0x180031dfa  test    eax, eax
0x180031dfc  js      short loc_180031E42
0x180031dfe  lea     rcx, [rdi+8]
0x180031e02  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180031e08  mov     rcx, rax; String
0x180031e0b  call    cs:__imp__wcsupr
0x180031e11  lea     r8, [rdi+40h]; struct STRU *
0x180031e15  mov     rdx, r14; unsigned __int16 *
0x180031e18  call    ?GeneratePasswordHash@TOKEN_KEY@@QEAAJPEBGPEAVSTRU@@@Z; TOKEN_KEY::GeneratePasswordHash(ushort const *,STRU *)
0x180031e1d  test    eax, eax
0x180031e1f  js      short loc_180031E42
0x180031e21  mov     [rdi+78h], esi
0x180031e24  mov     ecx, r15d
0x180031e27  jmp     short loc_180031E35
0x180031e29  imul    ecx, 65h ; 'e'
0x180031e2c  lea     rbx, [rbx+2]
0x180031e30  movzx   eax, ax
0x180031e33  add     ecx, eax
0x180031e35  movzx   eax, word ptr [rbx]
0x180031e38  test    ax, ax
0x180031e3b  jnz     short loc_180031E29
0x180031e3d  mov     [rdi+7Ch], ecx
0x180031e40  xor     eax, eax
0x180031e42  add     rsp, 28h
0x180031e46  pop     r15
0x180031e48  pop     r14
0x180031e4a  pop     rdi
0x180031e4b  pop     rsi
0x180031e4c  pop     rbp
0x180031e4d  pop     rbx
0x180031e4e  retn
```
