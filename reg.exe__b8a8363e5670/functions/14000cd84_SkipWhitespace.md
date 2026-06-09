# SkipWhitespace

- ea: `0x14000cd84`
- end: `0x14000cdbd`
- name: `SkipWhitespace`
- size: `57`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b418`
- `0x14000b54c`
- `0x14000b91c`
- `0x14000bff4`
- `0x14000c1d8`

## callees

- `0x14000b2c4`
- `0x14000cd84`

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
      LODWORD(qword_140055248) = qword_140055248 - 1;
      return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000cd84  sub     rsp, 28h
0x14000cd88  xor     eax, eax
0x14000cd8a  mov     [rsp+28h+arg_0], ax
0x14000cd8f  jmp     short loc_14000CDA1
0x14000cd91  cmp     [rsp+28h+arg_0], 20h ; ' '
0x14000cd97  jz      short loc_14000CDA1
0x14000cd99  cmp     [rsp+28h+arg_0], 9
0x14000cd9f  jnz     short loc_14000CDB1
0x14000cda1  lea     rcx, [rsp+28h+arg_0]
0x14000cda6  call    GetChar
0x14000cdab  test    eax, eax
0x14000cdad  jnz     short loc_14000CD91
0x14000cdaf  jmp     short loc_14000CDB7
0x14000cdb1  dec     dword ptr cs:qword_140055248
0x14000cdb7  add     rsp, 28h
0x14000cdbb  retn
```
