# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1400036dc`
- end: `0x140003758`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140008730`
- `0x140008b50`

## callees

- `0x1400036dc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000371e`
- `msvcrt!memcpy_s` at `0x14000371e`

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
0x1400036dc  mov     [rsp+arg_0], rbx
0x1400036e1  mov     [rsp+arg_8], rsi
0x1400036e6  push    rdi
0x1400036e7  sub     rsp, 20h
0x1400036eb  mov     rbx, r9
0x1400036ee  mov     rdi, rcx
0x1400036f1  cmp     rcx, rdx
0x1400036f4  jz      short loc_140003738
0x1400036f6  test    r8, r8
0x1400036f9  jz      short loc_140003738
0x1400036fb  cmp     byte ptr [r8], 0
0x1400036ff  jz      short loc_140003738
0x140003701  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003705  inc     rax
0x140003708  cmp     byte ptr [r8+rax], 0
0x14000370d  jnz     short loc_140003705
0x14000370f  lea     rsi, [rax+1]
0x140003713  sub     rdx, rdi; DestinationSize
0x140003716  cmp     rdx, rsi
0x140003719  jb      short loc_140003738
0x14000371b  mov     r9, rsi; SourceSize
0x14000371e  call    cs:__imp_memcpy_s
0x140003725  nop     dword ptr [rax+rax+00h]
0x14000372a  test    rbx, rbx
0x14000372d  jz      short loc_140003732
0x14000372f  mov     [rbx], rdi
0x140003732  lea     rax, [rsi+rdi]
0x140003736  jmp     short loc_140003747
0x140003738  test    rbx, rbx
0x14000373b  jz      short loc_140003744
0x14000373d  mov     qword ptr [r9], 0
0x140003744  mov     rax, rdi
0x140003747  mov     rbx, [rsp+28h+arg_0]
0x14000374c  mov     rsi, [rsp+28h+arg_8]
0x140003751  add     rsp, 20h
0x140003755  pop     rdi
0x140003756  retn
```
