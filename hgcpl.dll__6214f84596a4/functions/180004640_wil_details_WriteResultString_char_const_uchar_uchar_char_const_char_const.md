# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180004640`
- end: `0x1800046b1`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006124`
- `0x18000893c`

## callees

- `0x180004640`
- `0x180006008`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000467e`
- `msvcrt!memcpy_s` at `0x18000467e`

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
0x180004640  mov     [rsp+arg_0], rbx
0x180004645  mov     [rsp+arg_8], rsi
0x18000464a  push    rdi
0x18000464b  sub     rsp, 20h
0x18000464f  mov     rbx, r9
0x180004652  mov     rdi, rcx
0x180004655  cmp     rcx, rdx
0x180004658  jz      short loc_180004692
0x18000465a  test    r8, r8
0x18000465d  jz      short loc_180004692
0x18000465f  cmp     byte ptr [r8], 0
0x180004663  jz      short loc_180004692
0x180004665  mov     rcx, r8; this
0x180004668  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000466d  sub     rdx, rdi; DestinationSize
0x180004670  mov     rsi, rax
0x180004673  cmp     rdx, rax
0x180004676  jb      short loc_180004692
0x180004678  mov     r9, rax; SourceSize
0x18000467b  mov     rcx, rdi; Destination
0x18000467e  call    cs:__imp_memcpy_s
0x180004684  test    rbx, rbx
0x180004687  jz      short loc_18000468C
0x180004689  mov     [rbx], rdi
0x18000468c  lea     rax, [rsi+rdi]
0x180004690  jmp     short loc_1800046A1
0x180004692  test    rbx, rbx
0x180004695  jz      short loc_18000469E
0x180004697  mov     qword ptr [r9], 0
0x18000469e  mov     rax, rdi
0x1800046a1  mov     rbx, [rsp+28h+arg_0]
0x1800046a6  mov     rsi, [rsp+28h+arg_8]
0x1800046ab  add     rsp, 20h
0x1800046af  pop     rdi
0x1800046b0  retn
```
