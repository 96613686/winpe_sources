# TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)

- ea: `0x180034c90`
- end: `0x180034d1e`
- name: `?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z`
- size: `142`
- prototype: `int(TOKEN_KEY *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001d0e0`
- `0x180034bd8`

## callees

- `0x180034c90`
- `0x180035108`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180034cd3`
- `msvcrt!_wcsupr` at `0x180034cd3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180034cc4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180034cc4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180034cad`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180034cad`

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
0x180034c90  push    rbx
0x180034c92  push    rbp
0x180034c93  push    rsi
0x180034c94  push    rdi
0x180034c95  push    r14
0x180034c97  push    r15
0x180034c99  sub     rsp, 28h
0x180034c9d  mov     rdi, rcx
0x180034ca0  mov     esi, r9d
0x180034ca3  add     rcx, 8
0x180034ca7  mov     r14, r8
0x180034caa  mov     rbx, rdx
0x180034cad  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180034cb4  nop     dword ptr [rax+rax+00h]
0x180034cb9  xor     r15d, r15d
0x180034cbc  test    eax, eax
0x180034cbe  js      short loc_180034D10
0x180034cc0  lea     rcx, [rdi+8]
0x180034cc4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180034ccb  nop     dword ptr [rax+rax+00h]
0x180034cd0  mov     rcx, rax; String
0x180034cd3  call    cs:__imp__wcsupr
0x180034cda  nop     dword ptr [rax+rax+00h]
0x180034cdf  lea     r8, [rdi+40h]; struct STRU *
0x180034ce3  mov     rdx, r14; unsigned __int16 *
0x180034ce6  call    ?GeneratePasswordHash@TOKEN_KEY@@QEAAJPEBGPEAVSTRU@@@Z; TOKEN_KEY::GeneratePasswordHash(ushort const *,STRU *)
0x180034ceb  test    eax, eax
0x180034ced  js      short loc_180034D10
0x180034cef  mov     [rdi+78h], esi
0x180034cf2  mov     ecx, r15d
0x180034cf5  jmp     short loc_180034D03
0x180034cf7  imul    ecx, 65h ; 'e'
0x180034cfa  lea     rbx, [rbx+2]
0x180034cfe  movzx   eax, ax
0x180034d01  add     ecx, eax
0x180034d03  movzx   eax, word ptr [rbx]
0x180034d06  test    ax, ax
0x180034d09  jnz     short loc_180034CF7
0x180034d0b  mov     [rdi+7Ch], ecx
0x180034d0e  xor     eax, eax
0x180034d10  add     rsp, 28h
0x180034d14  pop     r15
0x180034d16  pop     r14
0x180034d18  pop     rdi
0x180034d19  pop     rsi
0x180034d1a  pop     rbp
0x180034d1b  pop     rbx
0x180034d1c  retn
```
