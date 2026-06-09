# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140002b60`
- end: `0x140002bd5`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004acc`
- `0x140004ed8`

## callees

- `0x140002b60`
- `0x1400059dc`

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
0x140002b60  mov     [rsp+arg_0], rbx
0x140002b65  mov     [rsp+arg_8], rsi
0x140002b6a  push    rdi
0x140002b6b  sub     rsp, 20h
0x140002b6f  mov     rbx, r9
0x140002b72  mov     rdi, rcx
0x140002b75  cmp     rcx, rdx
0x140002b78  jz      short loc_140002BB5
0x140002b7a  test    r8, r8
0x140002b7d  jz      short loc_140002BB5
0x140002b7f  cmp     byte ptr [r8], 0
0x140002b83  jz      short loc_140002BB5
0x140002b85  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002b89  inc     rax
0x140002b8c  cmp     byte ptr [r8+rax], 0
0x140002b91  jnz     short loc_140002B89
0x140002b93  lea     rsi, [rax+1]
0x140002b97  sub     rdx, rdi; DestinationSize
0x140002b9a  cmp     rdx, rsi
0x140002b9d  jb      short loc_140002BB5
0x140002b9f  mov     r9, rsi; SourceSize
0x140002ba2  call    memcpy_s
0x140002ba7  test    rbx, rbx
0x140002baa  jz      short loc_140002BAF
0x140002bac  mov     [rbx], rdi
0x140002baf  lea     rax, [rsi+rdi]
0x140002bb3  jmp     short loc_140002BC4
0x140002bb5  test    rbx, rbx
0x140002bb8  jz      short loc_140002BC1
0x140002bba  mov     qword ptr [r9], 0
0x140002bc1  mov     rax, rdi
0x140002bc4  mov     rbx, [rsp+28h+arg_0]
0x140002bc9  mov     rsi, [rsp+28h+arg_8]
0x140002bce  add     rsp, 20h
0x140002bd2  pop     rdi
0x140002bd3  retn
```
