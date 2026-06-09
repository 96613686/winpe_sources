# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800023a8`
- end: `0x180002424`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ff4`

## callees

- `0x1800023a8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800023ea`
- `msvcrt!memcpy_s` at `0x1800023ea`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(char *a1, char *a2, _BYTE *a3, _QWORD *a4)
{
  __int64 v6; // rax
  __int64 v7; // rsi
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
  v7 = v6 + 1;
  v8 = a2 - a1;
  if ( v8 >= v6 + 1 )
  {
    memcpy_s(a1, v8, a3, v6 + 1);
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
0x1800023a8  mov     [rsp+arg_0], rbx
0x1800023ad  mov     [rsp+arg_8], rsi
0x1800023b2  push    rdi
0x1800023b3  sub     rsp, 20h
0x1800023b7  mov     rbx, r9
0x1800023ba  mov     rdi, rcx
0x1800023bd  cmp     rcx, rdx
0x1800023c0  jz      short loc_180002404
0x1800023c2  test    r8, r8
0x1800023c5  jz      short loc_180002404
0x1800023c7  cmp     byte ptr [r8], 0
0x1800023cb  jz      short loc_180002404
0x1800023cd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800023d1  inc     rax
0x1800023d4  cmp     byte ptr [r8+rax], 0
0x1800023d9  jnz     short loc_1800023D1
0x1800023db  lea     rsi, [rax+1]
0x1800023df  sub     rdx, rdi; DestinationSize
0x1800023e2  cmp     rdx, rsi
0x1800023e5  jb      short loc_180002404
0x1800023e7  mov     r9, rsi; SourceSize
0x1800023ea  call    cs:__imp_memcpy_s
0x1800023f1  nop     dword ptr [rax+rax+00h]
0x1800023f6  test    rbx, rbx
0x1800023f9  jz      short loc_1800023FE
0x1800023fb  mov     [rbx], rdi
0x1800023fe  lea     rax, [rsi+rdi]
0x180002402  jmp     short loc_180002413
0x180002404  test    rbx, rbx
0x180002407  jz      short loc_180002410
0x180002409  mov     qword ptr [r9], 0
0x180002410  mov     rax, rdi
0x180002413  mov     rbx, [rsp+28h+arg_0]
0x180002418  mov     rsi, [rsp+28h+arg_8]
0x18000241d  add     rsp, 20h
0x180002421  pop     rdi
0x180002422  retn
```
