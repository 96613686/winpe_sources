# I_CryptSubtractFileTimes

- ea: `0x180019ae0`
- end: `0x180019b22`
- name: `I_CryptSubtractFileTimes`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018350`

## callees

- `0x180019ae0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019af0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019af0`

## pseudocode

```c
__int64 __fastcall I_CryptSubtractFileTimes(const FILETIME *a1, const FILETIME *a2)
{
  if ( CompareFileTime(a1, a2) > 0 )
    return (unsigned int)((*(_QWORD *)a1 - *(_QWORD *)a2) / 0x989680uLL);
  else
    return 0;
}

```

## disassembly

```asm
0x180019ae0  mov     [rsp+arg_0], rbx
0x180019ae5  push    rdi
0x180019ae6  sub     rsp, 20h
0x180019aea  mov     rbx, rdx
0x180019aed  mov     rdi, rcx
0x180019af0  call    cs:__imp_CompareFileTime
0x180019af6  test    eax, eax
0x180019af8  jg      short loc_180019AFE
0x180019afa  xor     eax, eax
0x180019afc  jmp     short loc_180019B17
0x180019afe  mov     rcx, [rdi]
0x180019b01  mov     rax, 0D6BF94D5E57A42BDh
0x180019b0b  sub     rcx, [rbx]
0x180019b0e  mul     rcx
0x180019b11  shr     rdx, 17h
0x180019b15  mov     eax, edx
0x180019b17  mov     rbx, [rsp+28h+arg_0]
0x180019b1c  add     rsp, 20h
0x180019b20  pop     rdi
0x180019b21  retn
```
