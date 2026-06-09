# ShowLastError

- ea: `0x14000e75c`
- end: `0x14000e792`
- name: `ShowLastError`
- size: `54`
- prototype: ``
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x1400038f8`
- `0x1400040b8`
- `0x140004764`
- `0x14000496c`
- `0x140004cf0`
- `0x140005ef0`
- `0x14000672c`
- `0x140008cbc`
- `0x140009c68`
- `0x140009f80`
- `0x14000a4e4`
- `0x14000e864`

## callees

- `0x14000d610`
- `0x14000e484`
- `0x14000e75c`
- `0x14000e864`

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
0x14000e75c  push    rbx
0x14000e75e  sub     rsp, 20h
0x14000e762  mov     rbx, rcx
0x14000e765  call    SaveLastError
0x14000e76a  test    eax, eax
0x14000e76c  jz      short loc_14000E789
0x14000e76e  call    GetReason
0x14000e773  mov     rdx, rax; lpString
0x14000e776  mov     rcx, rbx; Stream
0x14000e779  call    ShowMessage
0x14000e77e  xor     ecx, ecx
0x14000e780  test    eax, eax
0x14000e782  setnz   cl
0x14000e785  mov     eax, ecx
0x14000e787  jmp     short loc_14000E78B
0x14000e789  xor     eax, eax
0x14000e78b  add     rsp, 20h
0x14000e78f  pop     rbx
0x14000e790  retn
```
