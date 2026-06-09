# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1800046b8`
- end: `0x180004720`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006124`
- `0x18000893c`

## callees

- `0x1800046b8`
- `0x180006028`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800046f8`
- `msvcrt!memcpy_s` at `0x1800046f8`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<unsigned short const *>(
        unsigned __int16 *Destination,
        const unsigned __int16 *a2,
        wil::details *a3,
        unsigned __int16 **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // r10
  rsize_t v9; // r10
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_WORD *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return (char *)Destination + v10;
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return (char *)Destination;
  }
}

```

## disassembly

```asm
0x1800046b8  push    rbx
0x1800046ba  push    rbp
0x1800046bb  push    rsi
0x1800046bc  push    rdi
0x1800046bd  sub     rsp, 28h
0x1800046c1  xor     ebp, ebp
0x1800046c3  mov     rbx, r9
0x1800046c6  mov     r10, rdx
0x1800046c9  mov     rdi, rcx
0x1800046cc  cmp     rcx, rdx
0x1800046cf  jz      short loc_18000470C
0x1800046d1  test    r8, r8
0x1800046d4  jz      short loc_18000470C
0x1800046d6  cmp     [r8], bp
0x1800046da  jz      short loc_18000470C
0x1800046dc  mov     rcx, r8; this
0x1800046df  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800046e4  sub     r10, rdi
0x1800046e7  mov     rsi, rax
0x1800046ea  cmp     r10, rax
0x1800046ed  jb      short loc_18000470C
0x1800046ef  mov     r9, rax; SourceSize
0x1800046f2  mov     rdx, r10; DestinationSize
0x1800046f5  mov     rcx, rdi; Destination
0x1800046f8  call    cs:__imp_memcpy_s
0x1800046fe  test    rbx, rbx
0x180004701  jz      short loc_180004706
0x180004703  mov     [rbx], rdi
0x180004706  lea     rax, [rsi+rdi]
0x18000470a  jmp     short loc_180004717
0x18000470c  test    rbx, rbx
0x18000470f  jz      short loc_180004714
0x180004711  mov     [r9], rbp
0x180004714  mov     rax, rdi
0x180004717  add     rsp, 28h
0x18000471b  pop     rdi
0x18000471c  pop     rsi
0x18000471d  pop     rbp
0x18000471e  pop     rbx
0x18000471f  retn
```
