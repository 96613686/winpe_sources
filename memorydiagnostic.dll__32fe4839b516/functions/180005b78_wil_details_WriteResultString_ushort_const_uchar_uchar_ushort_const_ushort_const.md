# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180005b78`
- end: `0x180005bf9`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011660`
- `0x18001199c`

## callees

- `0x180005b78`
- `0x18001a6ac`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<unsigned short const *>(char *a1, char *a2, _WORD *a3, _QWORD *a4)
{
  __int64 v6; // rax
  unsigned __int64 v7; // rsi
  rsize_t v8; // rdx

  if ( a1 == a2 )
    goto LABEL_10;
  if ( !a3 )
    goto LABEL_10;
  if ( !*a3 )
    goto LABEL_10;
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  v7 = 2 * v6 + 2;
  v8 = a2 - a1;
  if ( v8 >= v7 )
  {
    memcpy_s(a1, v8, a3, 2 * v6 + 2);
    if ( a4 )
      *a4 = a1;
    return &a1[v7];
  }
  else
  {
LABEL_10:
    if ( a4 )
      *a4 = 0;
    return a1;
  }
}

```

## disassembly

```asm
0x180005b78  mov     [rsp+arg_0], rbx
0x180005b7d  mov     [rsp+arg_8], rbp
0x180005b82  mov     [rsp+arg_10], rsi
0x180005b87  push    rdi
0x180005b88  sub     rsp, 20h
0x180005b8c  xor     ebp, ebp
0x180005b8e  mov     rbx, r9
0x180005b91  mov     rdi, rcx
0x180005b94  cmp     rcx, rdx
0x180005b97  jz      short loc_180005BD8
0x180005b99  test    r8, r8
0x180005b9c  jz      short loc_180005BD8
0x180005b9e  cmp     [r8], bp
0x180005ba2  jz      short loc_180005BD8
0x180005ba4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005ba8  inc     rax
0x180005bab  cmp     [r8+rax*2], bp
0x180005bb0  jnz     short loc_180005BA8
0x180005bb2  lea     rsi, ds:2[rax*2]
0x180005bba  sub     rdx, rdi; DestinationSize
0x180005bbd  cmp     rdx, rsi
0x180005bc0  jb      short loc_180005BD8
0x180005bc2  mov     r9, rsi; SourceSize
0x180005bc5  call    memcpy_s
0x180005bca  test    rbx, rbx
0x180005bcd  jz      short loc_180005BD2
0x180005bcf  mov     [rbx], rdi
0x180005bd2  lea     rax, [rsi+rdi]
0x180005bd6  jmp     short loc_180005BE3
0x180005bd8  test    rbx, rbx
0x180005bdb  jz      short loc_180005BE0
0x180005bdd  mov     [r9], rbp
0x180005be0  mov     rax, rdi
0x180005be3  mov     rbx, [rsp+28h+arg_0]
0x180005be8  mov     rbp, [rsp+28h+arg_8]
0x180005bed  mov     rsi, [rsp+28h+arg_10]
0x180005bf2  add     rsp, 20h
0x180005bf6  pop     rdi
0x180005bf7  retn
```
