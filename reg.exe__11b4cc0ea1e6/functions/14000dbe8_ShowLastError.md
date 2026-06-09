# ShowLastError

- ea: `0x14000dbe8`
- end: `0x14000dc1d`
- name: `ShowLastError`
- size: `53`
- prototype: ``
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x14000375c`
- `0x140003ec4`
- `0x140004518`
- `0x140004708`
- `0x140004a38`
- `0x140005bac`
- `0x140006394`
- `0x140008788`
- `0x1400096a8`
- `0x14000998c`
- `0x140009ec0`
- `0x14000dce0`

## callees

- `0x14000ccc4`
- `0x14000d978`
- `0x14000dbe8`
- `0x14000dce0`

## pseudocode

```c
_BOOL8 __fastcall ShowLastError(FILE *Stream)
{
  const WCHAR *Reason; // rax

  if ( !(unsigned int)SaveLastError() )
    return 0;
  Reason = (const WCHAR *)GetReason();
  return (unsigned int)ShowMessage(Stream, Reason) != 0;
}

```

## disassembly

```asm
0x14000dbe8  push    rbx
0x14000dbea  sub     rsp, 20h
0x14000dbee  mov     rbx, rcx
0x14000dbf1  call    SaveLastError
0x14000dbf6  test    eax, eax
0x14000dbf8  jz      short loc_14000DC15
0x14000dbfa  call    GetReason
0x14000dbff  mov     rdx, rax; lpString
0x14000dc02  mov     rcx, rbx; Stream
0x14000dc05  call    ShowMessage
0x14000dc0a  xor     ecx, ecx
0x14000dc0c  test    eax, eax
0x14000dc0e  setnz   cl
0x14000dc11  mov     eax, ecx
0x14000dc13  jmp     short loc_14000DC17
0x14000dc15  xor     eax, eax
0x14000dc17  add     rsp, 20h
0x14000dc1b  pop     rbx
0x14000dc1c  retn
```
