# PutChar

- ea: `0x14000c9dc`
- end: `0x14000ca3a`
- name: `PutChar`
- size: `94`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c500`
- `0x14000c5c0`
- `0x14000c9dc`
- `0x14000ca40`
- `0x14000caac`
- `0x14000cadc`

## callees

- `0x14000b24c`
- `0x14000c9dc`

## pseudocode

```c
void __fastcall PutChar(WCHAR a1)
{
  if ( a1 == 10 )
  {
    PutChar(13);
    HIDWORD(qword_140055248) = 0;
  }
  else
  {
    ++HIDWORD(qword_140055248);
  }
  *(&WideCharStr + (int)qword_140055248) = a1;
  LODWORD(qword_140055248) = qword_140055248 + 1;
  if ( (_DWORD)qword_140055248 == 0x10000 )
    FlushIoBuffer();
}

```

## disassembly

```asm
0x14000c9dc  push    rbx
0x14000c9de  sub     rsp, 20h
0x14000c9e2  movzx   ebx, cx
0x14000c9e5  cmp     cx, 0Ah
0x14000c9e9  jz      short loc_14000C9F3
0x14000c9eb  inc     dword ptr cs:qword_140055248+4
0x14000c9f1  jmp     short loc_14000CA07
0x14000c9f3  mov     ecx, 0Dh
0x14000c9f8  call    PutChar
0x14000c9fd  mov     dword ptr cs:qword_140055248+4, 0
0x14000ca07  movsxd  rax, dword ptr cs:qword_140055248
0x14000ca0e  lea     rcx, WideCharStr
0x14000ca15  mov     [rcx+rax*2], bx
0x14000ca19  mov     eax, dword ptr cs:qword_140055248
0x14000ca1f  inc     eax
0x14000ca21  mov     dword ptr cs:qword_140055248, eax
0x14000ca27  cmp     eax, 10000h
0x14000ca2c  jnz     short loc_14000CA33
0x14000ca2e  call    FlushIoBuffer
0x14000ca33  add     rsp, 20h
0x14000ca37  pop     rbx
0x14000ca38  retn
```
