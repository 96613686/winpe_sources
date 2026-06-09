# CompressedStreamDump::GetPaddingBytes(unsigned __int64,uint)

- ea: `0x18002845c`
- end: `0x180028493`
- name: `?GetPaddingBytes@CompressedStreamDump@@YAI_KI@Z`
- size: `55`
- prototype: `unsigned int(CompressedStreamDump *__hidden this, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001e114`
- `0x18001e8f0`
- `0x180029974`

## callees

- `0x18002845c`
- `0x1800289b8`

## pseudocode

```c
unsigned __int64 __fastcall CompressedStreamDump::GetPaddingBytes(unsigned __int64 this, unsigned int a2)
{
  if ( a2 )
    return (a2 - this % a2) & (unsigned int)-(this % a2 != 0);
  CompressedStreamDump::LogMessage(
    (CompressedStreamDump *)4,
    "GetPaddingBytes: sectorSize parameter cannot be zero.\n",
    0);
  return 0;
}

```

## disassembly

```asm
0x18002845c  sub     rsp, 28h
0x180028460  mov     r8d, edx; char *
0x180028463  mov     rax, rcx
0x180028466  test    edx, edx
0x180028468  jnz     short loc_18002847F
0x18002846a  lea     rdx, aGetpaddingbyte; "GetPaddingBytes: sectorSize parameter c"...
0x180028471  mov     ecx, 4; this
0x180028476  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18002847b  xor     eax, eax
0x18002847d  jmp     short loc_18002848E
0x18002847f  xor     edx, edx
0x180028481  div     r8
0x180028484  sub     r8d, edx
0x180028487  neg     edx
0x180028489  sbb     eax, eax
0x18002848b  and     eax, r8d
0x18002848e  add     rsp, 28h
0x180028492  retn
```
