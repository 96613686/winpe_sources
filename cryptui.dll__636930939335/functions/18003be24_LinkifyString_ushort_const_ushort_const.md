# LinkifyString(ushort const *,ushort const *)

- ea: `0x18003be24`
- end: `0x18003bea7`
- name: `?LinkifyString@@YAPEAGPEBG0@Z`
- size: `131`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18003c990`
- `0x18003d7ec`

## callees

- `0x1800153e8`
- `0x18003be24`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003be6d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003be6d`

## pseudocode

```c
unsigned __int16 *__fastcall LinkifyString(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  unsigned __int64 v6; // r14
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rsi

  if ( !a1 || !a2 )
    return 0;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a1[v5] );
  do
    ++v4;
  while ( a2[v4] );
  v6 = (int)v4 + (int)v5 + 19LL;
  v7 = (unsigned __int16 *)LocalAlloc(0, 2 * v6);
  v8 = v7;
  if ( v7 )
    StringCchPrintfW(v7, v6, L"<a id=\"%s\">%s</a>", a1, a2);
  return v8;
}

```

## disassembly

```asm
0x18003be24  push    rbx
0x18003be26  push    rbp
0x18003be27  push    rsi
0x18003be28  push    rdi
0x18003be29  push    r14
0x18003be2b  sub     rsp, 30h
0x18003be2f  xor     ebp, ebp
0x18003be31  mov     rbx, rdx
0x18003be34  mov     rdi, rcx
0x18003be37  test    rcx, rcx
0x18003be3a  jz      short loc_18003BE9A
0x18003be3c  test    rdx, rdx
0x18003be3f  jz      short loc_18003BE9A
0x18003be41  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003be45  mov     rdx, rax
0x18003be48  inc     rdx
0x18003be4b  cmp     [rcx+rdx*2], bp
0x18003be4f  jnz     short loc_18003BE48
0x18003be51  inc     rax
0x18003be54  cmp     [rbx+rax*2], bp
0x18003be58  jnz     short loc_18003BE51
0x18003be5a  movsxd  r14, edx
0x18003be5d  movsxd  rcx, eax
0x18003be60  add     r14, 13h
0x18003be64  add     r14, rcx
0x18003be67  xor     ecx, ecx; uFlags
0x18003be69  lea     rdx, [r14+r14]; uBytes
0x18003be6d  call    cs:__imp_LocalAlloc
0x18003be73  mov     rsi, rax
0x18003be76  test    rax, rax
0x18003be79  jz      short loc_18003BE95
0x18003be7b  mov     r9, rdi
0x18003be7e  mov     [rsp+58h+var_38], rbx
0x18003be83  lea     r8, aAIdSSA; "<a id=\"%s\">%s</a>"
0x18003be8a  mov     rdx, r14; unsigned __int64
0x18003be8d  mov     rcx, rax; unsigned __int16 *
0x18003be90  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003be95  mov     rax, rsi
0x18003be98  jmp     short loc_18003BE9C
0x18003be9a  xor     eax, eax
0x18003be9c  add     rsp, 30h
0x18003bea0  pop     r14
0x18003bea2  pop     rdi
0x18003bea3  pop     rsi
0x18003bea4  pop     rbp
0x18003bea5  pop     rbx
0x18003bea6  retn
```
