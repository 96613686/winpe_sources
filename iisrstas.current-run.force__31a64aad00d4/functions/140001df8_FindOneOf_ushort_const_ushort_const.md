# FindOneOf(ushort const *,ushort const *)

- ea: `0x140001df8`
- end: `0x140001e6a`
- name: `?FindOneOf@@YAPEBGPEBG0@Z`
- size: `114`
- prototype: `const unsigned __int16 *__fastcall(LPCWSTR lpsz, LPCWSTR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002a40`

## callees

- `0x140001df8`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140001e31`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140001e3f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140001e62`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140001e31`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140001e3f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140001e62`

## pseudocode

```c
const unsigned __int16 *__fastcall FindOneOf(LPCWSTR lpsz, WCHAR *a2)
{
  const WCHAR *i; // rbx
  LPWSTR v4; // rax

  for ( i = lpsz; i; i = CharNextW(i) )
  {
    if ( !*i )
      break;
    v4 = a2;
    if ( a2 )
    {
      while ( *v4 )
      {
        if ( *i == *v4 )
          return CharNextW(i);
        v4 = CharNextW(v4);
        if ( !v4 )
          break;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140001df8  mov     [rsp+arg_0], rbx
0x140001dfd  mov     [rsp+arg_8], rsi
0x140001e02  push    rdi
0x140001e03  sub     rsp, 20h
0x140001e07  xor     esi, esi
0x140001e09  mov     rdi, rdx
0x140001e0c  mov     rbx, rcx
0x140001e0f  test    rcx, rcx
0x140001e12  jz      short loc_140001E4D
0x140001e14  cmp     [rbx], si
0x140001e17  jz      short loc_140001E4D
0x140001e19  mov     rax, rdi
0x140001e1c  test    rdi, rdi
0x140001e1f  jz      short loc_140001E3C
0x140001e21  movzx   ecx, word ptr [rax]
0x140001e24  test    cx, cx
0x140001e27  jz      short loc_140001E3C
0x140001e29  cmp     [rbx], cx
0x140001e2c  jz      short loc_140001E5F
0x140001e2e  mov     rcx, rax; lpsz
0x140001e31  call    cs:__imp_CharNextW
0x140001e37  test    rax, rax
0x140001e3a  jnz     short loc_140001E21
0x140001e3c  mov     rcx, rbx; lpsz
0x140001e3f  call    cs:__imp_CharNextW
0x140001e45  mov     rbx, rax
0x140001e48  test    rax, rax
0x140001e4b  jnz     short loc_140001E14
0x140001e4d  xor     eax, eax
0x140001e4f  mov     rbx, [rsp+28h+arg_0]
0x140001e54  mov     rsi, [rsp+28h+arg_8]
0x140001e59  add     rsp, 20h
0x140001e5d  pop     rdi
0x140001e5e  retn
0x140001e5f  mov     rcx, rbx; lpsz
0x140001e62  call    cs:__imp_CharNextW
0x140001e68  jmp     short loc_140001E4F
```
