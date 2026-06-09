# I_CryptSubtractFileTimes

- ea: `0x180017d34`
- end: `0x180017d76`
- name: `I_CryptSubtractFileTimes`
- size: `66`
- prototype: `__int64 __fastcall(const FILETIME *, const FILETIME *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008a30`
- `0x18000f140`
- `0x1800105e0`
- `0x18001e95c`

## callees

- `0x180017d34`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017d44`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017d44`

## pseudocode

```c
__int64 __fastcall I_CryptSubtractFileTimes(const FILETIME *a1, const FILETIME *a2)
{
  if ( CompareFileTime(a1, a2) <= 0 )
    return 0;
  else
    return (unsigned int)((*(_QWORD *)a1 - *(_QWORD *)a2) / 0x989680uLL);
}

```

## disassembly

```asm
0x180017d34  mov     [rsp+arg_0], rbx
0x180017d39  push    rdi
0x180017d3a  sub     rsp, 20h
0x180017d3e  mov     rbx, rdx
0x180017d41  mov     rdi, rcx
0x180017d44  call    cs:__imp_CompareFileTime
0x180017d4a  test    eax, eax
0x180017d4c  jle     short loc_180017D72
0x180017d4e  mov     rcx, [rdi]
0x180017d51  mov     rax, 0D6BF94D5E57A42BDh
0x180017d5b  sub     rcx, [rbx]
0x180017d5e  mul     rcx
0x180017d61  shr     rdx, 17h
0x180017d65  mov     eax, edx
0x180017d67  mov     rbx, [rsp+28h+arg_0]
0x180017d6c  add     rsp, 20h
0x180017d70  pop     rdi
0x180017d71  retn
0x180017d72  xor     eax, eax
0x180017d74  jmp     short loc_180017D67
```
