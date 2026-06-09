# MatchChar

- ea: `0x14000bbf0`
- end: `0x14000bc36`
- name: `MatchChar`
- size: `70`
- prototype: `__int64 __fastcall(__int16)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b54c`
- `0x14000b91c`
- `0x14000bff4`
- `0x14000c1d8`

## callees

- `0x14000b2c4`
- `0x14000bbf0`

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
      LODWORD(qword_140055248) = qword_140055248 - 1;
  }
  return v2;
}

```

## disassembly

```asm
0x14000bbf0  mov     [rsp+arg_0], rbx
0x14000bbf5  push    rdi
0x14000bbf6  sub     rsp, 20h
0x14000bbfa  movzx   edi, cx
0x14000bbfd  xor     eax, eax
0x14000bbff  lea     rcx, [rsp+28h+arg_8]
0x14000bc04  mov     [rsp+28h+arg_8], ax
0x14000bc09  xor     ebx, ebx
0x14000bc0b  call    GetChar
0x14000bc10  test    eax, eax
0x14000bc12  jz      short loc_14000BC28
0x14000bc14  cmp     di, [rsp+28h+arg_8]
0x14000bc19  jnz     short loc_14000BC22
0x14000bc1b  mov     ebx, 1
0x14000bc20  jmp     short loc_14000BC28
0x14000bc22  dec     dword ptr cs:qword_140055248
0x14000bc28  mov     eax, ebx
0x14000bc2a  mov     rbx, [rsp+28h+arg_0]
0x14000bc2f  add     rsp, 20h
0x14000bc33  pop     rdi
0x14000bc34  retn
```
