# AxiPreScanPathW(ushort const *)

- ea: `0x140008984`
- end: `0x140008a06`
- name: `?AxiPreScanPathW@@YAJPEBG@Z`
- size: `130`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140005188`
- `0x140005630`
- `0x140005b10`
- `0x14000747c`
- `0x140009240`
- `0x1400094a4`

## callees

- `0x140008984`
- `0x140009c48`

## import_xrefs

- `msvcrt!iswascii` at `0x1400089c8`
- `msvcrt!iswascii` at `0x1400089c8`
- `msvcrt!iswcntrl` at `0x1400089dc`
- `msvcrt!iswcntrl` at `0x1400089dc`

## pseudocode

```c
__int64 __fastcall AxiPreScanPathW(const unsigned __int16 *a1)
{
  __int64 result; // rax
  int i; // ebx
  __int64 v4; // rcx
  __int64 v5; // rdx
  int v6; // eax

  result = 0;
  if ( a1 )
  {
    for ( i = 0; ; ++i )
    {
      result = 0;
      v4 = a1[i];
      if ( !(_WORD)v4 )
        return result;
      v5 = (unsigned int)(v4 - 34);
      if ( (_DWORD)v4 == 34
        || (v5 = (unsigned int)(v4 - 42), (_DWORD)v4 == 42)
        || (v5 = (unsigned int)(v4 - 60), (_DWORD)v4 == 60)
        || (v5 = (unsigned int)(v4 - 62), (_DWORD)v4 == 62)
        || (v5 = (unsigned int)(v4 - 63), (_DWORD)v4 == 63)
        || (_DWORD)v4 == 124 )
      {
        v6 = FilenameDisallowCharacter(v4, v5);
      }
      else
      {
        if ( !iswascii(v4) )
          continue;
        v6 = iswcntrl(a1[i]);
      }
      if ( v6 )
        return 2147942487LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140008984  push    rbx
0x140008986  push    rbp
0x140008987  push    rsi
0x140008988  push    rdi
0x140008989  sub     rsp, 28h
0x14000898d  xor     ebp, ebp
0x14000898f  mov     rdi, rcx
0x140008992  mov     eax, ebp
0x140008994  test    rcx, rcx
0x140008997  jz      short loc_1400089FC
0x140008999  mov     ebx, ebp
0x14000899b  mov     esi, ebx
0x14000899d  mov     eax, ebp
0x14000899f  movzx   ecx, word ptr [rdi+rsi*2]; C
0x1400089a3  test    cx, cx
0x1400089a6  jz      short loc_1400089FC
0x1400089a8  mov     edx, ecx
0x1400089aa  sub     edx, 22h ; '"'
0x1400089ad  jz      short loc_1400089EA
0x1400089af  sub     edx, 8
0x1400089b2  jz      short loc_1400089EA
0x1400089b4  sub     edx, 12h
0x1400089b7  jz      short loc_1400089EA
0x1400089b9  sub     edx, 2
0x1400089bc  jz      short loc_1400089EA
0x1400089be  sub     edx, 1
0x1400089c1  jz      short loc_1400089EA
0x1400089c3  cmp     edx, 3Dh ; '='
0x1400089c6  jz      short loc_1400089EA
0x1400089c8  call    cs:__imp_iswascii
0x1400089cf  nop     dword ptr [rax+rax+00h]
0x1400089d4  test    eax, eax
0x1400089d6  jz      short loc_1400089F3
0x1400089d8  movzx   ecx, word ptr [rdi+rsi*2]; C
0x1400089dc  call    cs:__imp_iswcntrl
0x1400089e3  nop     dword ptr [rax+rax+00h]
0x1400089e8  jmp     short loc_1400089EF
0x1400089ea  call    FilenameDisallowCharacter
0x1400089ef  test    eax, eax
0x1400089f1  jnz     short loc_1400089F7
0x1400089f3  inc     ebx
0x1400089f5  jmp     short loc_14000899B
0x1400089f7  mov     eax, 80070057h
0x1400089fc  add     rsp, 28h
0x140008a00  pop     rdi
0x140008a01  pop     rsi
0x140008a02  pop     rbp
0x140008a03  pop     rbx
0x140008a04  retn
```
