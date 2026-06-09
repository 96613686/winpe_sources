# FwIsNextToken(ushort const *,ushort const *,ushort const * *)

- ea: `0x180012904`
- end: `0x180012958`
- name: `?FwIsNextToken@@YAHPEBG0PEAPEBG@Z`
- size: `84`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 **)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180012288`
- `0x180012508`
- `0x18001287c`
- `0x18002b38c`

## callees

- `0x180012904`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180012930`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180012930`

## pseudocode

```c
__int64 __fastcall FwIsNextToken(const unsigned __int16 *a1, const unsigned __int16 *a2, const unsigned __int16 **a3)
{
  __int64 v4; // rdi
  const unsigned __int16 *v5; // rsi
  unsigned int v6; // ebx

  if ( *a1 == 58 )
  {
    v4 = -1;
    v5 = a1 + 1;
    v6 = 0;
    do
      ++v4;
    while ( a2[v4] );
    if ( !(unsigned int)_o__wcsnicmp(a1 + 1, a2, v4) )
    {
      v6 = 1;
      *a3 = &v5[v4];
    }
  }
  else
  {
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180012904  push    rbx
0x180012906  push    rsi
0x180012907  push    rdi
0x180012908  push    r14
0x18001290a  sub     rsp, 28h
0x18001290e  cmp     word ptr [rcx], 3Ah ; ':'
0x180012912  mov     r14, r8
0x180012915  jnz     short loc_180012954
0x180012917  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001291b  lea     rsi, [rcx+2]
0x18001291f  xor     ebx, ebx
0x180012921  inc     rdi
0x180012924  cmp     [rdx+rdi*2], bx
0x180012928  jnz     short loc_180012921
0x18001292a  mov     r8, rdi
0x18001292d  mov     rcx, rsi
0x180012930  call    cs:__imp__o__wcsnicmp
0x180012936  test    eax, eax
0x180012938  jz      short loc_180012946
0x18001293a  mov     eax, ebx
0x18001293c  add     rsp, 28h
0x180012940  pop     r14
0x180012942  pop     rdi
0x180012943  pop     rsi
0x180012944  pop     rbx
0x180012945  retn
0x180012946  lea     rax, [rsi+rdi*2]
0x18001294a  mov     ebx, 1
0x18001294f  mov     [r14], rax
0x180012952  jmp     short loc_18001293A
0x180012954  xor     ebx, ebx
0x180012956  jmp     short loc_18001293A
```
