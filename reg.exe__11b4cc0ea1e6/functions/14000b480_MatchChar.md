# MatchChar

- ea: `0x14000b480`
- end: `0x14000b4c5`
- name: `MatchChar`
- size: `69`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ae58`
- `0x14000b1d4`
- `0x14000b86c`
- `0x14000ba40`

## callees

- `0x14000ac00`
- `0x14000b480`

## pseudocode

```c
__int64 __fastcall MatchChar(__int16 a1)
{
  unsigned int v2; // ebx
  __int16 v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  v2 = 0;
  if ( (unsigned int)GetChar(&v4) )
  {
    if ( a1 == v4 )
      return 1;
    else
      LODWORD(qword_140054248) = qword_140054248 - 1;
  }
  return v2;
}

```

## disassembly

```asm
0x14000b480  mov     [rsp+arg_0], rbx
0x14000b485  push    rdi
0x14000b486  sub     rsp, 20h
0x14000b48a  movzx   edi, cx
0x14000b48d  xor     eax, eax
0x14000b48f  lea     rcx, [rsp+28h+arg_8]
0x14000b494  mov     [rsp+28h+arg_8], ax
0x14000b499  xor     ebx, ebx
0x14000b49b  call    GetChar
0x14000b4a0  test    eax, eax
0x14000b4a2  jz      short loc_14000B4B8
0x14000b4a4  cmp     di, [rsp+28h+arg_8]
0x14000b4a9  jnz     short loc_14000B4B2
0x14000b4ab  mov     ebx, 1
0x14000b4b0  jmp     short loc_14000B4B8
0x14000b4b2  dec     dword ptr cs:qword_140054248
0x14000b4b8  mov     eax, ebx
0x14000b4ba  mov     rbx, [rsp+28h+arg_0]
0x14000b4bf  add     rsp, 20h
0x14000b4c3  pop     rdi
0x14000b4c4  retn
```
