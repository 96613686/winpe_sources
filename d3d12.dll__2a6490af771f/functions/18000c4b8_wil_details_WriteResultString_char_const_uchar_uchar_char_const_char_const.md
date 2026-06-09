# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000c4b8`
- end: `0x18000c528`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d8e0`
- `0x18000da1c`

## callees

- `0x18000463c`
- `0x18000c4b8`
- `0x18000d834`

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
0x18000c4b8  mov     [rsp+arg_0], rbx
0x18000c4bd  mov     [rsp+arg_8], rsi
0x18000c4c2  push    rdi
0x18000c4c3  sub     rsp, 20h
0x18000c4c7  mov     rbx, r9
0x18000c4ca  mov     rdi, rcx
0x18000c4cd  cmp     rcx, rdx
0x18000c4d0  jz      short loc_18000C509
0x18000c4d2  test    r8, r8
0x18000c4d5  jz      short loc_18000C509
0x18000c4d7  cmp     byte ptr [r8], 0
0x18000c4db  jz      short loc_18000C509
0x18000c4dd  mov     rcx, r8; this
0x18000c4e0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000c4e5  sub     rdx, rdi; DestinationSize
0x18000c4e8  mov     rsi, rax
0x18000c4eb  cmp     rdx, rax
0x18000c4ee  jb      short loc_18000C509
0x18000c4f0  mov     r9, rax; SourceSize
0x18000c4f3  mov     rcx, rdi; Destination
0x18000c4f6  call    memcpy_s
0x18000c4fb  test    rbx, rbx
0x18000c4fe  jz      short loc_18000C503
0x18000c500  mov     [rbx], rdi
0x18000c503  lea     rax, [rsi+rdi]
0x18000c507  jmp     short loc_18000C518
0x18000c509  test    rbx, rbx
0x18000c50c  jz      short loc_18000C515
0x18000c50e  mov     qword ptr [r9], 0
0x18000c515  mov     rax, rdi
0x18000c518  mov     rbx, [rsp+28h+arg_0]
0x18000c51d  mov     rsi, [rsp+28h+arg_8]
0x18000c522  add     rsp, 20h
0x18000c526  pop     rdi
0x18000c527  retn
```
