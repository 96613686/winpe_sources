# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180020b58`
- end: `0x180020bc9`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800235f4`

## callees

- `0x180020b58`
- `0x1800234d0`

## import_xrefs

- `ntdll!memcpy_s` at `0x180020b96`
- `ntdll!memcpy_s` at `0x180020b96`

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
0x180020b58  mov     [rsp+arg_0], rbx
0x180020b5d  mov     [rsp+arg_8], rsi
0x180020b62  push    rdi
0x180020b63  sub     rsp, 20h
0x180020b67  mov     rbx, r9
0x180020b6a  mov     rdi, rcx
0x180020b6d  cmp     rcx, rdx
0x180020b70  jz      short loc_180020BAA
0x180020b72  test    r8, r8
0x180020b75  jz      short loc_180020BAA
0x180020b77  cmp     byte ptr [r8], 0
0x180020b7b  jz      short loc_180020BAA
0x180020b7d  mov     rcx, r8; this
0x180020b80  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180020b85  sub     rdx, rdi; DestinationSize
0x180020b88  mov     rsi, rax
0x180020b8b  cmp     rdx, rax
0x180020b8e  jb      short loc_180020BAA
0x180020b90  mov     r9, rax; SourceSize
0x180020b93  mov     rcx, rdi; Destination
0x180020b96  call    cs:__imp_memcpy_s
0x180020b9c  test    rbx, rbx
0x180020b9f  jz      short loc_180020BA4
0x180020ba1  mov     [rbx], rdi
0x180020ba4  lea     rax, [rsi+rdi]
0x180020ba8  jmp     short loc_180020BB9
0x180020baa  test    rbx, rbx
0x180020bad  jz      short loc_180020BB6
0x180020baf  mov     qword ptr [r9], 0
0x180020bb6  mov     rax, rdi
0x180020bb9  mov     rbx, [rsp+28h+arg_0]
0x180020bbe  mov     rsi, [rsp+28h+arg_8]
0x180020bc3  add     rsp, 20h
0x180020bc7  pop     rdi
0x180020bc8  retn
```
