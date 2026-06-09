# PutChar

- ea: `0x14000c1e8`
- end: `0x14000c245`
- name: `PutChar`
- size: `93`
- prototype: `__int64 __fastcall(WCHAR)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14000bd44`
- `0x14000be00`
- `0x14000c1e8`
- `0x14000c24c`
- `0x14000c2b8`
- `0x14000c2e8`

## callees

- `0x14000ab90`
- `0x14000c1e8`

## pseudocode

```c
__int64 __fastcall PutChar(WCHAR a1)
{
  __int64 result; // rax

  if ( a1 == 10 )
  {
    PutChar(13);
    HIDWORD(qword_140054248) = 0;
  }
  else
  {
    ++HIDWORD(qword_140054248);
  }
  *(&WideCharStr + (int)qword_140054248) = a1;
  result = (unsigned int)(qword_140054248 + 1);
  LODWORD(qword_140054248) = result;
  if ( (_DWORD)result == 0x10000 )
    return FlushIoBuffer();
  return result;
}

```

## disassembly

```asm
0x14000c1e8  push    rbx
0x14000c1ea  sub     rsp, 20h
0x14000c1ee  movzx   ebx, cx
0x14000c1f1  cmp     cx, 0Ah
0x14000c1f5  jz      short loc_14000C1FF
0x14000c1f7  inc     dword ptr cs:qword_140054248+4
0x14000c1fd  jmp     short loc_14000C213
0x14000c1ff  mov     ecx, 0Dh
0x14000c204  call    PutChar
0x14000c209  mov     dword ptr cs:qword_140054248+4, 0
0x14000c213  movsxd  rax, dword ptr cs:qword_140054248
0x14000c21a  lea     rcx, WideCharStr
0x14000c221  mov     [rcx+rax*2], bx
0x14000c225  mov     eax, dword ptr cs:qword_140054248
0x14000c22b  inc     eax
0x14000c22d  mov     dword ptr cs:qword_140054248, eax
0x14000c233  cmp     eax, 10000h
0x14000c238  jnz     short loc_14000C23F
0x14000c23a  call    FlushIoBuffer
0x14000c23f  add     rsp, 20h
0x14000c243  pop     rbx
0x14000c244  retn
```
