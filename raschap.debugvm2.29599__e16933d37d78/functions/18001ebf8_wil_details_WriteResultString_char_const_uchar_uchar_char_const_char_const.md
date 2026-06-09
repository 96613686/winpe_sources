# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18001ebf8`
- end: `0x18001ec68`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180021c20`
- `0x180021e48`

## callees

- `0x1800118a4`
- `0x18001ebf8`
- `0x180021a90`

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
0x18001ebf8  mov     [rsp+arg_0], rbx
0x18001ebfd  mov     [rsp+arg_8], rsi
0x18001ec02  push    rdi
0x18001ec03  sub     rsp, 20h
0x18001ec07  mov     rbx, r9
0x18001ec0a  mov     rdi, rcx
0x18001ec0d  cmp     rcx, rdx
0x18001ec10  jz      short loc_18001EC49
0x18001ec12  test    r8, r8
0x18001ec15  jz      short loc_18001EC49
0x18001ec17  cmp     byte ptr [r8], 0
0x18001ec1b  jz      short loc_18001EC49
0x18001ec1d  mov     rcx, r8; this
0x18001ec20  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001ec25  sub     rdx, rdi; DestinationSize
0x18001ec28  mov     rsi, rax
0x18001ec2b  cmp     rdx, rax
0x18001ec2e  jb      short loc_18001EC49
0x18001ec30  mov     r9, rax; SourceSize
0x18001ec33  mov     rcx, rdi; Destination
0x18001ec36  call    memcpy_s
0x18001ec3b  test    rbx, rbx
0x18001ec3e  jz      short loc_18001EC43
0x18001ec40  mov     [rbx], rdi
0x18001ec43  lea     rax, [rsi+rdi]
0x18001ec47  jmp     short loc_18001EC58
0x18001ec49  test    rbx, rbx
0x18001ec4c  jz      short loc_18001EC55
0x18001ec4e  mov     qword ptr [r9], 0
0x18001ec55  mov     rax, rdi
0x18001ec58  mov     rbx, [rsp+28h+arg_0]
0x18001ec5d  mov     rsi, [rsp+28h+arg_8]
0x18001ec62  add     rsp, 20h
0x18001ec66  pop     rdi
0x18001ec67  retn
```
