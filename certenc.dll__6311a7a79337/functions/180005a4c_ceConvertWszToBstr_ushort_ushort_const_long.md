# ceConvertWszToBstr(ushort * *,ushort const *,long)

- ea: `0x180005a4c`
- end: `0x180005ab0`
- name: `?ceConvertWszToBstr@@YAHPEAPEAGPEBGJ@Z`
- size: `100`
- prototype: `int(unsigned __int16 **, const unsigned __int16 *, int)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d20`
- `0x180002580`
- `0x180002d00`
- `0x180002f20`
- `0x180003a30`
- `0x180003d50`
- `0x180004e20`
- `0x180005170`
- `0x180006234`
- `0x180007c60`
- `0x180007eb0`

## callees

- `0x180005a4c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180005a8b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180005a8b`

## pseudocode

```c
__int64 __fastcall ceConvertWszToBstr(unsigned __int16 **a1, const CHAR *a2, UINT a3)
{
  unsigned __int16 *v4; // rax
  __int64 v5; // rax
  unsigned int v6; // ebx

  *a1 = 0;
  v4 = 0;
  if ( !a2 )
    goto LABEL_6;
  v5 = -1;
  v6 = 0;
  if ( a3 == -1 )
  {
    do
      ++v5;
    while ( *(_WORD *)&a2[2 * v5] );
    a3 = 2 * v5;
  }
  v4 = SysAllocStringByteLen(a2, a3);
  if ( v4 )
  {
LABEL_6:
    *a1 = v4;
    return 1;
  }
  return v6;
}

```

## disassembly

```asm
0x180005a4c  mov     [rsp+arg_0], rbx
0x180005a51  mov     [rsp+arg_8], rsi
0x180005a56  push    rdi
0x180005a57  sub     rsp, 20h
0x180005a5b  xor     esi, esi
0x180005a5d  mov     r9, rdx
0x180005a60  mov     [rcx], rsi
0x180005a63  mov     rdi, rcx
0x180005a66  mov     eax, esi
0x180005a68  test    rdx, rdx
0x180005a6b  jz      short loc_180005A96
0x180005a6d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005a71  mov     ebx, esi
0x180005a73  cmp     r8d, eax
0x180005a76  jnz     short loc_180005A85
0x180005a78  inc     rax
0x180005a7b  cmp     [rdx+rax*2], si
0x180005a7f  jnz     short loc_180005A78
0x180005a81  lea     r8d, [rax+rax]
0x180005a85  mov     edx, r8d; len
0x180005a88  mov     rcx, r9; psz
0x180005a8b  call    cs:__imp_SysAllocStringByteLen
0x180005a91  test    rax, rax
0x180005a94  jz      short loc_180005A9E
0x180005a96  mov     [rdi], rax
0x180005a99  mov     ebx, 1
0x180005a9e  mov     rsi, [rsp+28h+arg_8]
0x180005aa3  mov     eax, ebx
0x180005aa5  mov     rbx, [rsp+28h+arg_0]
0x180005aaa  add     rsp, 20h
0x180005aae  pop     rdi
0x180005aaf  retn
```
