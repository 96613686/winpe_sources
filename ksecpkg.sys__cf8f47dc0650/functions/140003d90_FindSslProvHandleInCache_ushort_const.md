# FindSslProvHandleInCache(ushort const *)

- ea: `0x140003d90`
- end: `0x140003e21`
- name: `?FindSslProvHandleInCache@@YA_KPEBG@Z`
- size: `145`
- prototype: `unsigned __int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002510`

## callees

- `0x140003d90`

## pseudocode

```c
unsigned __int64 __fastcall FindSslProvHandleInCache(const unsigned __int16 *a1)
{
  _QWORD *v1; // rbx
  unsigned int v2; // r11d
  unsigned int i; // r9d
  const unsigned __int16 *v5; // rax
  int v6; // ecx
  int v7; // edx

  v1 = &g_rgCachedPagedSslProvs;
  v2 = dword_1400190F8;
  if ( dword_140019528 )
    v2 = g_cCachedPagedSslProvs;
  else
    v1 = &unk_140019100;
  for ( i = 0; i < v2; ++i )
  {
    v5 = a1;
    do
    {
      v6 = *(const unsigned __int16 *)((char *)v5 + v1[2 * i + 1] - (_QWORD)a1);
      v7 = *v5 - v6;
      if ( v7 )
        break;
      ++v5;
    }
    while ( v6 );
    if ( !v7 )
      return v1[2 * i];
  }
  return 0;
}

```

## disassembly

```asm
0x140003d90  mov     [rsp+arg_0], rbx
0x140003d95  mov     [rsp+arg_8], rdi
0x140003d9a  mov     edx, cs:dword_140019528
0x140003da0  lea     rbx, ?g_rgCachedPagedSslProvs@@3PAUCACHED_SSL_PROVIDER@@A; CACHED_SSL_PROVIDER near * g_rgCachedPagedSslProvs
0x140003da7  mov     r11d, cs:dword_1400190F8
0x140003dae  lea     rax, unk_140019100
0x140003db5  test    edx, edx
0x140003db7  mov     rdi, rcx
0x140003dba  cmovnz  r11d, cs:?g_cCachedPagedSslProvs@@3KA; ulong g_cCachedPagedSslProvs
0x140003dc2  cmovz   rbx, rax
0x140003dc6  xor     r9d, r9d
0x140003dc9  nop     dword ptr [rax+00000000h]
0x140003dd0  cmp     r9d, r11d
0x140003dd3  jnb     short loc_140003E1D
0x140003dd5  mov     r10d, r9d
0x140003dd8  mov     rax, rdi
0x140003ddb  add     r10, r10
0x140003dde  mov     r8, [rbx+r10*8+8]
0x140003de3  sub     r8, rdi
0x140003de6  nop     word ptr [rax+rax+00000000h]
0x140003df0  movzx   edx, word ptr [rax]
0x140003df3  movzx   ecx, word ptr [rax+r8]
0x140003df8  sub     edx, ecx
0x140003dfa  jnz     short loc_140003E04
0x140003dfc  add     rax, 2
0x140003e00  test    ecx, ecx
0x140003e02  jnz     short loc_140003DF0
0x140003e04  test    edx, edx
0x140003e06  jz      short loc_140003E0D
0x140003e08  inc     r9d
0x140003e0b  jmp     short loc_140003DD0
0x140003e0d  mov     rax, [rbx+r10*8]
0x140003e11  mov     rbx, [rsp+arg_0]
0x140003e16  mov     rdi, [rsp+arg_8]
0x140003e1b  retn
0x140003e1d  xor     eax, eax
0x140003e1f  jmp     short loc_140003E11
```
