# TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)

- ea: `0x180010bf4`
- end: `0x180010c6f`
- name: `?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z`
- size: `123`
- prototype: `int(TOKEN_KEY *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000c898`
- `0x180010b48`

## callees

- `0x180010bf4`
- `0x180010fa0`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180010c2b`
- `msvcrt!_wcsupr` at `0x180010c2b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010c11`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010c11`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010c22`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010c22`

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
0x180010bf4  push    rbx
0x180010bf6  push    rbp
0x180010bf7  push    rsi
0x180010bf8  push    rdi
0x180010bf9  push    r14
0x180010bfb  push    r15
0x180010bfd  sub     rsp, 28h
0x180010c01  mov     rdi, rcx
0x180010c04  mov     esi, r9d
0x180010c07  add     rcx, 8
0x180010c0b  mov     r14, r8
0x180010c0e  mov     rbx, rdx
0x180010c11  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180010c17  xor     r15d, r15d
0x180010c1a  test    eax, eax
0x180010c1c  js      short loc_180010C62
0x180010c1e  lea     rcx, [rdi+8]
0x180010c22  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180010c28  mov     rcx, rax; String
0x180010c2b  call    cs:__imp__wcsupr
0x180010c31  lea     r8, [rdi+40h]; struct STRU *
0x180010c35  mov     rdx, r14; unsigned __int16 *
0x180010c38  call    ?GeneratePasswordHash@TOKEN_KEY@@QEAAJPEBGPEAVSTRU@@@Z; TOKEN_KEY::GeneratePasswordHash(ushort const *,STRU *)
0x180010c3d  test    eax, eax
0x180010c3f  js      short loc_180010C62
0x180010c41  mov     [rdi+78h], esi
0x180010c44  mov     ecx, r15d
0x180010c47  jmp     short loc_180010C55
0x180010c49  imul    ecx, 65h ; 'e'
0x180010c4c  lea     rbx, [rbx+2]
0x180010c50  movzx   eax, ax
0x180010c53  add     ecx, eax
0x180010c55  movzx   eax, word ptr [rbx]
0x180010c58  test    ax, ax
0x180010c5b  jnz     short loc_180010C49
0x180010c5d  mov     [rdi+7Ch], ecx
0x180010c60  xor     eax, eax
0x180010c62  add     rsp, 28h
0x180010c66  pop     r15
0x180010c68  pop     r14
0x180010c6a  pop     rdi
0x180010c6b  pop     rsi
0x180010c6c  pop     rbp
0x180010c6d  pop     rbx
0x180010c6e  retn
```
