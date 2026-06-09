# CompLevelFromPSZ

- ea: `0x140001b04`
- end: `0x140001b7d`
- name: `CompLevelFromPSZ`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002670`
- `0x1400084d8`

## callees

- `0x140001b04`
- `0x140008620`

## import_xrefs

- `msvcrt!atoi` at `0x140001b15`
- `msvcrt!atoi` at `0x140001b24`
- `msvcrt!atoi` at `0x140001b36`
- `msvcrt!atoi` at `0x140001b15`
- `msvcrt!atoi` at `0x140001b24`
- `msvcrt!atoi` at `0x140001b36`

## string_xrefs

- `0x140001b60`: `Compression Level not in range (%1..%2): %3`

## pseudocode

```c
__int64 __fastcall CompLevelFromPSZ(const char *a1, __int64 a2)
{
  int v4; // edi
  int v5; // ebx
  int v6; // eax

  v4 = atoi(a1);
  v5 = atoi("1");
  v6 = atoi("7");
  if ( v5 <= v4 && v4 <= v6 )
    return (unsigned int)v4;
  ErrSet(a2, "Compression Level not in range (%1..%2): %3", "%s%s%s", "1", "7", a1);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x140001b04  push    rbx
0x140001b06  push    rbp
0x140001b07  push    rsi
0x140001b08  push    rdi
0x140001b09  push    r14
0x140001b0b  sub     rsp, 30h
0x140001b0f  mov     rbp, rdx
0x140001b12  mov     rsi, rcx
0x140001b15  call    cs:__imp_atoi
0x140001b1b  lea     rcx, String; "1"
0x140001b22  mov     edi, eax
0x140001b24  call    cs:__imp_atoi
0x140001b2a  lea     r14, a7; "7"
0x140001b31  mov     ebx, eax
0x140001b33  mov     rcx, r14; String
0x140001b36  call    cs:__imp_atoi
0x140001b3c  cmp     ebx, edi
0x140001b3e  jg      short loc_140001B48
0x140001b40  cmp     edi, eax
0x140001b42  jg      short loc_140001B48
0x140001b44  mov     eax, edi
0x140001b46  jmp     short loc_140001B72
0x140001b48  mov     [rsp+58h+var_30], rsi
0x140001b4d  lea     r9, String; "1"
0x140001b54  lea     r8, aSSS; "%s%s%s"
0x140001b5b  mov     [rsp+58h+var_38], r14
0x140001b60  lea     rdx, aCompressionLev; "Compression Level not in range (%1..%2)"...
0x140001b67  mov     rcx, rbp
0x140001b6a  call    ErrSet
0x140001b6f  or      eax, 0FFFFFFFFh
0x140001b72  add     rsp, 30h
0x140001b76  pop     r14
0x140001b78  pop     rdi
0x140001b79  pop     rsi
0x140001b7a  pop     rbp
0x140001b7b  pop     rbx
0x140001b7c  retn
```
