# SkipWhitespace

- ea: `0x14000c560`
- end: `0x14000c598`
- name: `SkipWhitespace`
- size: `56`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ad40`
- `0x14000ae58`
- `0x14000b1d4`
- `0x14000b86c`
- `0x14000ba40`

## callees

- `0x14000ac00`
- `0x14000c560`

## pseudocode

```c
__int64 SkipWhitespace()
{
  __int64 result; // rax
  __int16 v1; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  while ( 1 )
  {
    result = GetChar(&v1);
    if ( !(_DWORD)result )
      break;
    if ( v1 != 32 && v1 != 9 )
    {
      LODWORD(qword_140054248) = qword_140054248 - 1;
      return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000c560  sub     rsp, 28h
0x14000c564  xor     eax, eax
0x14000c566  mov     [rsp+28h+arg_0], ax
0x14000c56b  jmp     short loc_14000C57D
0x14000c56d  cmp     [rsp+28h+arg_0], 20h ; ' '
0x14000c573  jz      short loc_14000C57D
0x14000c575  cmp     [rsp+28h+arg_0], 9
0x14000c57b  jnz     short loc_14000C58D
0x14000c57d  lea     rcx, [rsp+28h+arg_0]
0x14000c582  call    GetChar
0x14000c587  test    eax, eax
0x14000c589  jnz     short loc_14000C56D
0x14000c58b  jmp     short loc_14000C593
0x14000c58d  dec     dword ptr cs:qword_140054248
0x14000c593  add     rsp, 28h
0x14000c597  retn
```
