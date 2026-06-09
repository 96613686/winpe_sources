# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180004628`
- end: `0x1800046a4`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006a84`
- `0x180006ea4`

## callees

- `0x180004628`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000466a`
- `msvcrt!memcpy_s` at `0x18000466a`

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
0x180004628  mov     [rsp+arg_0], rbx
0x18000462d  mov     [rsp+arg_8], rsi
0x180004632  push    rdi
0x180004633  sub     rsp, 20h
0x180004637  mov     rbx, r9
0x18000463a  mov     rdi, rcx
0x18000463d  cmp     rcx, rdx
0x180004640  jz      short loc_180004684
0x180004642  test    r8, r8
0x180004645  jz      short loc_180004684
0x180004647  cmp     byte ptr [r8], 0
0x18000464b  jz      short loc_180004684
0x18000464d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004651  inc     rax
0x180004654  cmp     byte ptr [r8+rax], 0
0x180004659  jnz     short loc_180004651
0x18000465b  lea     rsi, [rax+1]
0x18000465f  sub     rdx, rdi; DestinationSize
0x180004662  cmp     rdx, rsi
0x180004665  jb      short loc_180004684
0x180004667  mov     r9, rsi; SourceSize
0x18000466a  call    cs:__imp_memcpy_s
0x180004671  nop     dword ptr [rax+rax+00h]
0x180004676  test    rbx, rbx
0x180004679  jz      short loc_18000467E
0x18000467b  mov     [rbx], rdi
0x18000467e  lea     rax, [rsi+rdi]
0x180004682  jmp     short loc_180004693
0x180004684  test    rbx, rbx
0x180004687  jz      short loc_180004690
0x180004689  mov     qword ptr [r9], 0
0x180004690  mov     rax, rdi
0x180004693  mov     rbx, [rsp+28h+arg_0]
0x180004698  mov     rsi, [rsp+28h+arg_8]
0x18000469d  add     rsp, 20h
0x1800046a1  pop     rdi
0x1800046a2  retn
```
