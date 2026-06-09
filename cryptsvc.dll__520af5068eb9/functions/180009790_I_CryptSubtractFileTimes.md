# I_CryptSubtractFileTimes

- ea: `0x180009790`
- end: `0x1800097d2`
- name: `I_CryptSubtractFileTimes`
- size: `66`
- prototype: `__int64 __fastcall(const FILETIME *, const FILETIME *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008a10`

## callees

- `0x180009790`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800097a0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800097a0`

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
0x180009790  mov     [rsp+arg_0], rbx
0x180009795  push    rdi
0x180009796  sub     rsp, 20h
0x18000979a  mov     rdi, rdx
0x18000979d  mov     rbx, rcx
0x1800097a0  call    cs:__imp_CompareFileTime
0x1800097a6  test    eax, eax
0x1800097a8  jle     short loc_1800097CE
0x1800097aa  mov     rcx, [rbx]
0x1800097ad  mov     rax, 0D6BF94D5E57A42BDh
0x1800097b7  sub     rcx, [rdi]
0x1800097ba  mul     rcx
0x1800097bd  shr     rdx, 17h
0x1800097c1  mov     eax, edx
0x1800097c3  mov     rbx, [rsp+28h+arg_0]
0x1800097c8  add     rsp, 20h
0x1800097cc  pop     rdi
0x1800097cd  retn
0x1800097ce  xor     eax, eax
0x1800097d0  jmp     short loc_1800097C3
```
