# InitializeDUIDLL

- ea: `0x180018d74`
- end: `0x180018e75`
- name: `InitializeDUIDLL`
- size: `257`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800152b8`
- `0x18001f630`

## callees

- `0x180007564`
- `0x18000c740`
- `0x180018d74`
- `0x18003098c`
- `0x1800311c4`

## import_xrefs

- `WS2_32!__imp_htons` at `0x180018df1`
- `WS2_32!__imp_htons` at `0x180018df1`

## pseudocode

```c
__int64 __fastcall InitializeDUIDLL(__int64 a1)
{
  int v2; // eax
  __int64 *v3; // rsi
  unsigned int v4; // ebp
  __int64 v5; // rbx
  _BYTE *v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // rbx

  if ( !a1 || !*(_QWORD *)(a1 + 80) || !*(_BYTE *)(a1 + 76) || (v2 = *(_DWORD *)(a1 + 88)) == 0 )
  {
    v7 = 87;
    if ( !a1 )
    {
LABEL_16:
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_dJ(1025, 31, WPP_8483b35a6c81311e7498c1c8b1f5bcb4_Traceguids, v7, *(_QWORD *)(a1 + 24));
      return v7;
    }
    v3 = (__int64 *)(a1 + 456);
LABEL_14:
    if ( *v3 )
      DhcpFree(v3);
    goto LABEL_16;
  }
  v3 = (__int64 *)(a1 + 456);
  v4 = v2 + 4;
  if ( *(_QWORD *)(a1 + 456) )
    DhcpFree(a1 + 456);
  v5 = v4;
  v6 = (_BYTE *)DhcpAlloc(v4);
  *v3 = (__int64)v6;
  if ( !v6 )
  {
    v7 = 8;
    goto LABEL_14;
  }
  if ( v4 )
  {
    do
    {
      *v6++ = 0;
      --v5;
    }
    while ( v5 );
  }
  *(_BYTE *)(*v3 + 1) = 3;
  v8 = *v3;
  *(_WORD *)(v8 + 2) = htons(*(unsigned __int8 *)(a1 + 76));
  memcpy_0((void *)(*v3 + 4), *(const void **)(a1 + 80), *(unsigned int *)(a1 + 88));
  v7 = 0;
  *(_DWORD *)(a1 + 464) = v4;
  return v7;
}

```

## disassembly

```asm
0x180018d74  push    rbx
0x180018d76  push    rbp
0x180018d77  push    rsi
0x180018d78  push    rdi
0x180018d79  sub     rsp, 38h
0x180018d7d  mov     rdi, rcx
0x180018d80  test    rcx, rcx
0x180018d83  jz      loc_180018E1F
0x180018d89  cmp     qword ptr [rcx+50h], 0
0x180018d8e  jz      loc_180018E1F
0x180018d94  cmp     byte ptr [rcx+4Ch], 0
0x180018d98  jz      loc_180018E1F
0x180018d9e  mov     eax, [rcx+58h]
0x180018da1  test    eax, eax
0x180018da3  jz      short loc_180018E1F
0x180018da5  lea     rsi, [rcx+1C8h]
0x180018dac  cmp     qword ptr [rsi], 0
0x180018db0  lea     ebp, [rax+4]
0x180018db3  jz      short loc_180018DBD
0x180018db5  mov     rcx, rsi
0x180018db8  call    DhcpFree
0x180018dbd  mov     ecx, ebp
0x180018dbf  mov     ebx, ebp
0x180018dc1  call    DhcpAlloc
0x180018dc6  mov     [rsi], rax
0x180018dc9  test    rax, rax
0x180018dcc  jnz     short loc_180018DD3
0x180018dce  lea     ebx, [rax+8]
0x180018dd1  jmp     short loc_180018E30
0x180018dd3  test    ebp, ebp
0x180018dd5  jz      short loc_180018DE3
0x180018dd7  mov     byte ptr [rax], 0
0x180018dda  inc     rax
0x180018ddd  sub     rbx, 1
0x180018de1  jnz     short loc_180018DD7
0x180018de3  mov     rax, [rsi]
0x180018de6  mov     byte ptr [rax+1], 3
0x180018dea  movzx   ecx, byte ptr [rdi+4Ch]; hostshort
0x180018dee  mov     rbx, [rsi]
0x180018df1  call    cs:__imp_htons
0x180018df8  nop     dword ptr [rax+rax+00h]
0x180018dfd  mov     [rbx+2], ax
0x180018e01  mov     rcx, [rsi]
0x180018e04  mov     r8d, [rdi+58h]; Size
0x180018e08  add     rcx, 4; void *
0x180018e0c  mov     rdx, [rdi+50h]; Src
0x180018e10  call    memcpy_0
0x180018e15  xor     ebx, ebx
0x180018e17  mov     [rdi+1D0h], ebp
0x180018e1d  jmp     short loc_180018E69
0x180018e1f  mov     ebx, 57h ; 'W'
0x180018e24  test    rdi, rdi
0x180018e27  jz      short loc_180018E3E
0x180018e29  lea     rsi, [rcx+1C8h]
0x180018e30  cmp     qword ptr [rsi], 0
0x180018e34  jz      short loc_180018E3E
0x180018e36  mov     rcx, rsi
0x180018e39  call    DhcpFree
0x180018e3e  test    byte ptr cs:xmmword_1800423E0, 2
0x180018e45  jz      short loc_180018E69
0x180018e47  mov     r8, [rdi+18h]
0x180018e4b  mov     edx, 1Fh
0x180018e50  mov     [rsp+58h+var_38], r8
0x180018e55  mov     ecx, 401h
0x180018e5a  lea     r8, WPP_8483b35a6c81311e7498c1c8b1f5bcb4_Traceguids
0x180018e61  mov     r9d, ebx
0x180018e64  call    WPP_SF_dJ
0x180018e69  mov     eax, ebx
0x180018e6b  add     rsp, 38h
0x180018e6f  pop     rdi
0x180018e70  pop     rsi
0x180018e71  pop     rbp
0x180018e72  pop     rbx
0x180018e73  retn
```
