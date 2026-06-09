# DevAuthValidateHeader

- ea: `0x1800035bc`
- end: `0x180003608`
- name: `DevAuthValidateHeader`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800020e4`
- `0x180002444`

## callees

- `0x1800035bc`
- `0x180003610`

## pseudocode

```c
__int64 __fastcall DevAuthValidateHeader(unsigned __int8 a1, __int64 a2, int a3)
{
  __int64 v3; // r9
  char v4; // r10
  int v5; // r11d
  __int64 result; // rax

  if ( !(unsigned int)DevAuthValidateMessageLength(a1, a3) )
    return 0;
  if ( v4 != *(_BYTE *)v3 )
    return 0;
  result = 1;
  if ( *(_BYTE *)(v3 + 1) != 1
    || v5 - 4 != ((unsigned __int16)(*(_WORD *)(v3 + 2) << 8) | HIBYTE(*(unsigned __int16 *)(v3 + 2))) )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800035bc  sub     rsp, 28h
0x1800035c0  mov     r9, rdx
0x1800035c3  mov     r11d, r8d
0x1800035c6  mov     edx, r8d
0x1800035c9  mov     r10b, cl
0x1800035cc  call    _DevAuthValidateMessageLength
0x1800035d1  test    eax, eax
0x1800035d3  jz      short loc_180003600
0x1800035d5  cmp     r10b, [r9]
0x1800035d8  jnz     short loc_180003600
0x1800035da  mov     eax, 1
0x1800035df  cmp     [r9+1], al
0x1800035e3  jnz     short loc_180003600
0x1800035e5  movzx   ecx, word ptr [r9+2]
0x1800035ea  mov     edx, ecx
0x1800035ec  shl     cx, 8
0x1800035f0  movzx   ecx, cx
0x1800035f3  shr     edx, 8
0x1800035f6  or      edx, ecx
0x1800035f8  lea     ecx, [r11-4]
0x1800035fc  cmp     ecx, edx
0x1800035fe  jz      short loc_180003602
0x180003600  xor     eax, eax
0x180003602  add     rsp, 28h
0x180003606  retn
```
