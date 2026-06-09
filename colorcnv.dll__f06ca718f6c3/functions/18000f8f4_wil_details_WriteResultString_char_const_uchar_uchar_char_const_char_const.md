# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000f8f4`
- end: `0x18000f964`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001316c`

## callees

- `0x18000f8f4`
- `0x1800130bc`
- `0x180014cf4`

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
0x18000f8f4  mov     [rsp+arg_0], rbx
0x18000f8f9  mov     [rsp+arg_8], rsi
0x18000f8fe  push    rdi
0x18000f8ff  sub     rsp, 20h
0x18000f903  mov     rbx, r9
0x18000f906  mov     rdi, rcx
0x18000f909  cmp     rcx, rdx
0x18000f90c  jz      short loc_18000F945
0x18000f90e  test    r8, r8
0x18000f911  jz      short loc_18000F945
0x18000f913  cmp     byte ptr [r8], 0
0x18000f917  jz      short loc_18000F945
0x18000f919  mov     rcx, r8; this
0x18000f91c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000f921  sub     rdx, rdi; DestinationSize
0x18000f924  mov     rsi, rax
0x18000f927  cmp     rdx, rax
0x18000f92a  jb      short loc_18000F945
0x18000f92c  mov     r9, rax; SourceSize
0x18000f92f  mov     rcx, rdi; Destination
0x18000f932  call    memcpy_s
0x18000f937  test    rbx, rbx
0x18000f93a  jz      short loc_18000F93F
0x18000f93c  mov     [rbx], rdi
0x18000f93f  lea     rax, [rsi+rdi]
0x18000f943  jmp     short loc_18000F954
0x18000f945  test    rbx, rbx
0x18000f948  jz      short loc_18000F951
0x18000f94a  mov     qword ptr [r9], 0
0x18000f951  mov     rax, rdi
0x18000f954  mov     rbx, [rsp+28h+arg_0]
0x18000f959  mov     rsi, [rsp+28h+arg_8]
0x18000f95e  add     rsp, 20h
0x18000f962  pop     rdi
0x18000f963  retn
```
