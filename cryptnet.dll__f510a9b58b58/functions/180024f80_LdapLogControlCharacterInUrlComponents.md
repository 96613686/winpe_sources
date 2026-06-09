# LdapLogControlCharacterInUrlComponents

- ea: `0x180024f80`
- end: `0x180025002`
- name: `LdapLogControlCharacterInUrlComponents`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800196e0`

## callees

- `0x1800031e8`
- `0x180005980`
- `0x18000a990`
- `0x18001e720`
- `0x180024f80`

## pseudocode

```c
void __fastcall LdapLogControlCharacterInUrlComponents(__int64 a1)
{
  const unsigned __int16 *v1; // rsi
  unsigned __int16 *v3; // rbx
  __int64 v4; // rax
  unsigned __int64 v5; // r14
  unsigned __int16 *v6; // rax

  v1 = &pszUrl;
  v3 = 0;
  if ( a1 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(a1 + 2 * v4) );
    v5 = (int)v4 + 16;
    v6 = (unsigned __int16 *)PkiZeroAlloc(2 * v5);
    v3 = v6;
    if ( v6 )
    {
      if ( (int)StringCchPrintfW(v6, v5, L"Url: <%s>", a1) >= 0 )
        v1 = v3;
    }
  }
  LogCryptnetError(0x1023u, v1, 0x80070057);
  operator delete(v3);
}

```

## disassembly

```asm
0x180024f80  push    rbx
0x180024f82  push    rbp
0x180024f83  push    rsi
0x180024f84  push    rdi
0x180024f85  push    r14
0x180024f87  sub     rsp, 20h
0x180024f8b  xor     ebp, ebp
0x180024f8d  lea     rsi, pszUrl
0x180024f94  mov     rdi, rcx
0x180024f97  mov     ebx, ebp
0x180024f99  test    rcx, rcx
0x180024f9c  jz      short loc_180024FDD
0x180024f9e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024fa2  inc     rax
0x180024fa5  cmp     [rcx+rax*2], bp
0x180024fa9  jnz     short loc_180024FA2
0x180024fab  add     eax, 10h
0x180024fae  movsxd  r14, eax
0x180024fb1  lea     rcx, [r14+r14]; uBytes
0x180024fb5  call    PkiZeroAlloc
0x180024fba  mov     rbx, rax
0x180024fbd  test    rax, rax
0x180024fc0  jz      short loc_180024FDD
0x180024fc2  mov     r9, rdi
0x180024fc5  lea     r8, aUrlS; "Url: <%s>"
0x180024fcc  mov     rdx, r14; unsigned __int64
0x180024fcf  mov     rcx, rax; unsigned __int16 *
0x180024fd2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024fd7  test    eax, eax
0x180024fd9  cmovns  rsi, rbx
0x180024fdd  mov     r8d, 80070057h; unsigned int
0x180024fe3  mov     rdx, rsi; unsigned __int16 *
0x180024fe6  mov     ecx, 1023h; unsigned int
0x180024feb  call    ?LogCryptnetError@@YAXKPEBGK@Z; LogCryptnetError(ulong,ushort const *,ulong)
0x180024ff0  mov     rcx, rbx; hMem
0x180024ff3  add     rsp, 20h
0x180024ff7  pop     r14
0x180024ff9  pop     rdi
0x180024ffa  pop     rsi
0x180024ffb  pop     rbp
0x180024ffc  pop     rbx
0x180024ffd  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
