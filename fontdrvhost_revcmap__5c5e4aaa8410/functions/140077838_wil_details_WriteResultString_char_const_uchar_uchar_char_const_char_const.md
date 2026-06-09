# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140077838`
- end: `0x1400778a8`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14007a6b0`
- `0x14007a8d8`

## callees

- `0x140077838`
- `0x14007a544`
- `0x14007bed8`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(
        char *Destination,
        const char *a2,
        wil::details *a3,
        char **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // rdx
  rsize_t v9; // rdx
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_BYTE *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return &Destination[v10];
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
}

```

## disassembly

```asm
0x140077838  mov     [rsp+arg_0], rbx
0x14007783d  mov     [rsp+arg_8], rsi
0x140077842  push    rdi
0x140077843  sub     rsp, 20h
0x140077847  mov     rbx, r9
0x14007784a  mov     rdi, rcx
0x14007784d  cmp     rcx, rdx
0x140077850  jz      short loc_140077889
0x140077852  test    r8, r8
0x140077855  jz      short loc_140077889
0x140077857  cmp     byte ptr [r8], 0
0x14007785b  jz      short loc_140077889
0x14007785d  mov     rcx, r8; this
0x140077860  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140077865  sub     rdx, rdi; DestinationSize
0x140077868  mov     rsi, rax
0x14007786b  cmp     rdx, rax
0x14007786e  jb      short loc_140077889
0x140077870  mov     r9, rax; SourceSize
0x140077873  mov     rcx, rdi; Destination
0x140077876  call    memcpy_s
0x14007787b  test    rbx, rbx
0x14007787e  jz      short loc_140077883
0x140077880  mov     [rbx], rdi
0x140077883  lea     rax, [rsi+rdi]
0x140077887  jmp     short loc_140077898
0x140077889  test    rbx, rbx
0x14007788c  jz      short loc_140077895
0x14007788e  mov     qword ptr [r9], 0
0x140077895  mov     rax, rdi
0x140077898  mov     rbx, [rsp+28h+arg_0]
0x14007789d  mov     rsi, [rsp+28h+arg_8]
0x1400778a2  add     rsp, 20h
0x1400778a6  pop     rdi
0x1400778a7  retn
```
