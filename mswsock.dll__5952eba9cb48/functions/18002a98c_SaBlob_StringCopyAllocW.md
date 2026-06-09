# SaBlob_StringCopyAllocW

- ea: `0x18002a98c`
- end: `0x18002a9ea`
- name: `SaBlob_StringCopyAllocW`
- size: `94`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f28`
- `0x180016120`
- `0x18001671c`
- `0x18001f4e0`
- `0x1800205d8`

## callees

- `0x18002a98c`
- `0x180037195`

## import_xrefs

- `DNSAPI!DnsApiAllocZero` at `0x18002a9ba`
- `DNSAPI!DnsApiAllocZero` at `0x18002a9ba`

## pseudocode

```c
void *__fastcall SaBlob_StringCopyAllocW(_WORD *Src)
{
  void *v2; // rdi
  __int64 v3; // rbx
  void *v4; // rax

  v2 = 0;
  if ( Src )
  {
    v3 = -1;
    do
      ++v3;
    while ( Src[v3] );
    if ( v3 )
    {
      v4 = (void *)DnsApiAllocZero((unsigned int)(2 * v3 + 2));
      v2 = v4;
      if ( v4 )
        memcpy_0(v4, Src, 2 * v3);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18002a98c  push    rbx
0x18002a98e  push    rbp
0x18002a98f  push    rsi
0x18002a990  push    rdi
0x18002a991  sub     rsp, 28h
0x18002a995  xor     ebp, ebp
0x18002a997  mov     rsi, rcx
0x18002a99a  mov     edi, ebp
0x18002a99c  test    rcx, rcx
0x18002a99f  jz      short loc_18002A9DD
0x18002a9a1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002a9a5  inc     rbx
0x18002a9a8  cmp     [rcx+rbx*2], bp
0x18002a9ac  jnz     short loc_18002A9A5
0x18002a9ae  test    rbx, rbx
0x18002a9b1  jz      short loc_18002A9DD
0x18002a9b3  lea     ecx, ds:2[rbx*2]
0x18002a9ba  call    cs:__imp_DnsApiAllocZero
0x18002a9c1  nop     dword ptr [rax+rax+00h]
0x18002a9c6  mov     rdi, rax
0x18002a9c9  test    rax, rax
0x18002a9cc  jz      short loc_18002A9DD
0x18002a9ce  lea     r8, [rbx+rbx]; Size
0x18002a9d2  mov     rdx, rsi; Src
0x18002a9d5  mov     rcx, rax; void *
0x18002a9d8  call    memcpy_0
0x18002a9dd  mov     rax, rdi
0x18002a9e0  add     rsp, 28h
0x18002a9e4  pop     rdi
0x18002a9e5  pop     rsi
0x18002a9e6  pop     rbp
0x18002a9e7  pop     rbx
0x18002a9e8  retn
```
