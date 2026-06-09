# FILTERING_RULE::QueryContainsUnescapedPercent(ushort const *)

- ea: `0x180007748`
- end: `0x1800077f2`
- name: `?QueryContainsUnescapedPercent@FILTERING_RULE@@AEAAHPEBG@Z`
- size: `170`
- prototype: `__int64 __fastcall(FILTERING_RULE *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800071f8`

## callees

- `0x180007748`

## import_xrefs

- `msvcrt!iswxdigit` at `0x18000777d`
- `msvcrt!iswxdigit` at `0x18000778b`
- `msvcrt!iswxdigit` at `0x18000779f`
- `msvcrt!iswxdigit` at `0x1800077ad`
- `msvcrt!iswxdigit` at `0x1800077bb`
- `msvcrt!iswxdigit` at `0x1800077c9`
- `msvcrt!iswxdigit` at `0x18000777d`
- `msvcrt!iswxdigit` at `0x18000778b`
- `msvcrt!iswxdigit` at `0x18000779f`
- `msvcrt!iswxdigit` at `0x1800077ad`
- `msvcrt!iswxdigit` at `0x1800077bb`
- `msvcrt!iswxdigit` at `0x1800077c9`

## pseudocode

```c
__int64 __fastcall FILTERING_RULE::QueryContainsUnescapedPercent(FILTERING_RULE *this, const unsigned __int16 *a2)
{
  wint_t v3; // cx

  while ( a2 && *a2 )
  {
    if ( *a2 != 37 )
      goto LABEL_7;
    v3 = a2[1];
    if ( ((v3 - 85) & 0xFFDF) != 0 )
    {
      if ( !iswxdigit(v3) || !iswxdigit(a2[2]) )
        return 1;
LABEL_7:
      ++a2;
    }
    else
    {
      if ( !iswxdigit(a2[2]) || !iswxdigit(a2[3]) || !iswxdigit(a2[4]) || !iswxdigit(a2[5]) )
        return 1;
      a2 += 2;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180007748  mov     [rsp+arg_0], rbx
0x18000774d  mov     [rsp+arg_8], rsi
0x180007752  push    rdi
0x180007753  sub     rsp, 20h
0x180007757  mov     rbx, rdx
0x18000775a  xor     esi, esi
0x18000775c  test    rbx, rbx
0x18000775f  jz      short loc_1800077E0
0x180007761  cmp     [rbx], si
0x180007764  jz      short loc_1800077E0
0x180007766  cmp     word ptr [rbx], 25h ; '%'
0x18000776a  jnz     short loc_180007795
0x18000776c  movzx   ecx, word ptr [rbx+2]; C
0x180007770  mov     edx, 0FFDFh
0x180007775  lea     eax, [rcx-55h]
0x180007778  test    dx, ax
0x18000777b  jz      short loc_18000779B
0x18000777d  call    cs:__imp_iswxdigit
0x180007783  test    eax, eax
0x180007785  jz      short loc_1800077D9
0x180007787  movzx   ecx, word ptr [rbx+4]; C
0x18000778b  call    cs:__imp_iswxdigit
0x180007791  test    eax, eax
0x180007793  jz      short loc_1800077D9
0x180007795  add     rbx, 2
0x180007799  jmp     short loc_18000775C
0x18000779b  movzx   ecx, word ptr [rbx+4]; C
0x18000779f  call    cs:__imp_iswxdigit
0x1800077a5  test    eax, eax
0x1800077a7  jz      short loc_1800077D9
0x1800077a9  movzx   ecx, word ptr [rbx+6]; C
0x1800077ad  call    cs:__imp_iswxdigit
0x1800077b3  test    eax, eax
0x1800077b5  jz      short loc_1800077D9
0x1800077b7  movzx   ecx, word ptr [rbx+8]; C
0x1800077bb  call    cs:__imp_iswxdigit
0x1800077c1  test    eax, eax
0x1800077c3  jz      short loc_1800077D9
0x1800077c5  movzx   ecx, word ptr [rbx+0Ah]; C
0x1800077c9  call    cs:__imp_iswxdigit
0x1800077cf  test    eax, eax
0x1800077d1  jz      short loc_1800077D9
0x1800077d3  add     rbx, 4
0x1800077d7  jmp     short loc_18000775C
0x1800077d9  mov     eax, 1
0x1800077de  jmp     short loc_1800077E2
0x1800077e0  xor     eax, eax
0x1800077e2  mov     rbx, [rsp+28h+arg_0]
0x1800077e7  mov     rsi, [rsp+28h+arg_8]
0x1800077ec  add     rsp, 20h
0x1800077f0  pop     rdi
0x1800077f1  retn
```
