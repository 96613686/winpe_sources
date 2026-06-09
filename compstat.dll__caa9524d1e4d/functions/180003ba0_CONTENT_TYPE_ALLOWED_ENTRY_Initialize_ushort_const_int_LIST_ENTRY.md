# CONTENT_TYPE_ALLOWED_ENTRY::Initialize(ushort const *,int,_LIST_ENTRY *)

- ea: `0x180003ba0`
- end: `0x180003d41`
- name: `?Initialize@CONTENT_TYPE_ALLOWED_ENTRY@@QEAAJPEBGHPEAU_LIST_ENTRY@@@Z`
- size: `417`
- prototype: `int(CONTENT_TYPE_ALLOWED_ENTRY *__hidden this, const unsigned __int16 *, int, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800036d0`

## callees

- `0x180003ba0`

## import_xrefs

- `msvcrt!strchr` at `0x180003c5e`
- `msvcrt!strchr` at `0x180003c8c`
- `msvcrt!strchr` at `0x180003c5e`
- `msvcrt!strchr` at `0x180003c8c`
- `msvcrt!wcschr` at `0x180003bc7`
- `msvcrt!wcschr` at `0x180003c04`
- `msvcrt!wcschr` at `0x180003bc7`
- `msvcrt!wcschr` at `0x180003c04`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003c3d`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003c71`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003c3d`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003c71`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003c52`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003c80`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003c9f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003cc3`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003c52`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003c80`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003c9f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003cc3`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x180003c1b`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x180003c1b`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBGK@Z` at `0x180003bee`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBGK@Z` at `0x180007264`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBGK@Z` at `0x180003bee`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBGK@Z` at `0x180007264`

## pseudocode

```c
int __fastcall CONTENT_TYPE_ALLOWED_ENTRY::Initialize(
        CONTENT_TYPE_ALLOWED_ENTRY *this,
        const unsigned __int16 *a2,
        int a3,
        struct _LIST_ENTRY *a4)
{
  wchar_t *v8; // rax
  const wchar_t *v9; // rdi
  int result; // eax
  wchar_t *v11; // rax
  const unsigned __int16 *v12; // rdx
  STRA *v13; // rcx
  const char *Str; // rax
  const char *v15; // rax
  char *v16; // rax
  int v17; // r8d
  char *v18; // rax
  int v19; // edx
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *Blink; // rax

  v8 = wcschr(a2, 0x2Fu);
  v9 = v8;
  if ( !v8 )
    return -2147024809;
  result = STRA::CopyWTruncate((CONTENT_TYPE_ALLOWED_ENTRY *)((char *)this + 16), a2, v8 - a2);
  if ( result >= 0 )
  {
    v11 = wcschr(v9, 0x3Bu);
    v12 = v9 + 1;
    v13 = (CONTENT_TYPE_ALLOWED_ENTRY *)((char *)this + 72);
    result = v11 ? STRA::CopyWTruncate(v13, v12, v11 - v9 - 1) : STRA::CopyWTruncate(v13, v12);
    if ( result >= 0 )
    {
      *((_DWORD *)this + 32) = a3;
      *(_QWORD *)((char *)this + 132) = 0;
      if ( STRA::QueryCCH((CONTENT_TYPE_ALLOWED_ENTRY *)((char *)this + 16)) > 1 )
      {
        Str = STRA::QueryStr((CONTENT_TYPE_ALLOWED_ENTRY *)((char *)this + 16));
        if ( strchr(Str, 42) )
          *((_DWORD *)this + 33) = 1;
      }
      if ( STRA::QueryCCH((CONTENT_TYPE_ALLOWED_ENTRY *)((char *)this + 72)) > 1 )
      {
        v15 = STRA::QueryStr((CONTENT_TYPE_ALLOWED_ENTRY *)((char *)this + 72));
        if ( strchr(v15, 42) )
          *((_DWORD *)this + 34) = 1;
      }
      v16 = STRA::QueryStr((CONTENT_TYPE_ALLOWED_ENTRY *)((char *)this + 16));
      v17 = (unsigned __int8)*v16 - 42;
      if ( *v16 == 42 )
        v17 = (unsigned __int8)v16[1];
      if ( !v17 )
        goto LABEL_24;
      v18 = STRA::QueryStr((CONTENT_TYPE_ALLOWED_ENTRY *)((char *)this + 72));
      v19 = (unsigned __int8)*v18 - 42;
      if ( *v18 == 42 )
        v19 = (unsigned __int8)v18[1];
      if ( !v19 || *((_DWORD *)this + 33) || *((_DWORD *)this + 34) )
      {
LABEL_24:
        Blink = a4->Blink;
        if ( Blink->Flink == a4 )
        {
          *(_QWORD *)this = a4;
          *((_QWORD *)this + 1) = Blink;
          Blink->Flink = (struct _LIST_ENTRY *)this;
          a4->Blink = (struct _LIST_ENTRY *)this;
          return 0;
        }
      }
      else
      {
        Flink = a4->Flink;
        if ( a4->Flink->Blink == a4 )
        {
          *(_QWORD *)this = Flink;
          *((_QWORD *)this + 1) = a4;
          Flink->Blink = (struct _LIST_ENTRY *)this;
          a4->Flink = (struct _LIST_ENTRY *)this;
          return 0;
        }
      }
      __fastfail(3u);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003ba0  mov     [rsp+arg_8], rbx
0x180003ba5  mov     [rsp+arg_10], rsi
0x180003baa  push    rdi
0x180003bab  push    r14
0x180003bad  push    r15
0x180003baf  sub     rsp, 20h
0x180003bb3  mov     rsi, rdx
0x180003bb6  mov     rbx, rcx
0x180003bb9  mov     rcx, rsi; Str
0x180003bbc  mov     edx, 2Fh ; '/'; Ch
0x180003bc1  mov     r14, r9
0x180003bc4  mov     r15d, r8d
0x180003bc7  call    cs:__imp_wcschr
0x180003bcd  mov     rdi, rax
0x180003bd0  test    rax, rax
0x180003bd3  jz      loc_180007250
0x180003bd9  mov     r8, rax
0x180003bdc  mov     [rsp+38h+arg_0], rbp
0x180003be1  sub     r8, rsi
0x180003be4  lea     rcx, [rbx+10h]
0x180003be8  sar     r8, 1
0x180003beb  mov     rdx, rsi
0x180003bee  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBGK@Z; STRA::CopyWTruncate(ushort const *,ulong)
0x180003bf4  test    eax, eax
0x180003bf6  js      loc_180003D08
0x180003bfc  mov     edx, 3Bh ; ';'; Ch
0x180003c01  mov     rcx, rdi; Str
0x180003c04  call    cs:__imp_wcschr
0x180003c0a  lea     rdx, [rdi+2]
0x180003c0e  lea     rcx, [rbx+48h]
0x180003c12  test    rax, rax
0x180003c15  jnz     loc_18000725A
0x180003c1b  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBG@Z; STRA::CopyWTruncate(ushort const *)
0x180003c21  test    eax, eax
0x180003c23  js      loc_180003D08
0x180003c29  xor     edi, edi
0x180003c2b  mov     [rbx+80h], r15d
0x180003c32  lea     rcx, [rbx+10h]
0x180003c36  mov     [rbx+84h], rdi
0x180003c3d  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180003c43  mov     r15d, 2Ah ; '*'
0x180003c49  cmp     eax, 1
0x180003c4c  jbe     short loc_180003C6D
0x180003c4e  lea     rcx, [rbx+10h]
0x180003c52  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180003c58  mov     rcx, rax; Str
0x180003c5b  mov     edx, r15d; Val
0x180003c5e  call    cs:__imp_strchr
0x180003c64  test    rax, rax
0x180003c67  jnz     loc_180007270
0x180003c6d  lea     rcx, [rbx+48h]
0x180003c71  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180003c77  cmp     eax, 1
0x180003c7a  jbe     short loc_180003C9B
0x180003c7c  lea     rcx, [rbx+48h]
0x180003c80  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180003c86  mov     rcx, rax; Str
0x180003c89  mov     edx, r15d; Val
0x180003c8c  call    cs:__imp_strchr
0x180003c92  test    rax, rax
0x180003c95  jnz     loc_18000727F
0x180003c9b  lea     rcx, [rbx+10h]
0x180003c9f  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180003ca5  movzx   r8d, byte ptr [rax]
0x180003ca9  sub     r8d, r15d
0x180003cac  jnz     short loc_180003CBA
0x180003cae  movzx   r8d, byte ptr [rax+1]
0x180003cb3  movzx   edx, dil
0x180003cb7  sub     r8d, edx
0x180003cba  test    r8d, r8d
0x180003cbd  jz      short loc_180003D21
0x180003cbf  lea     rcx, [rbx+48h]
0x180003cc3  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180003cc9  movzx   edx, byte ptr [rax]
0x180003ccc  sub     edx, r15d
0x180003ccf  jnz     short loc_180003CDB
0x180003cd1  movzx   edx, byte ptr [rax+1]
0x180003cd5  movzx   ecx, dil
0x180003cd9  sub     edx, ecx
0x180003cdb  test    edx, edx
0x180003cdd  jz      short loc_180003D21
0x180003cdf  cmp     [rbx+84h], edi
0x180003ce5  jnz     short loc_180003D21
0x180003ce7  cmp     [rbx+88h], edi
0x180003ced  jnz     short loc_180003D21
0x180003cef  mov     rax, [r14]
0x180003cf2  cmp     [rax+8], r14
0x180003cf6  jnz     short loc_180003D3A
0x180003cf8  mov     [rbx], rax
0x180003cfb  mov     [rbx+8], r14
0x180003cff  mov     [rax+8], rbx
0x180003d03  mov     [r14], rbx
0x180003d06  xor     eax, eax
0x180003d08  mov     rbp, [rsp+38h+arg_0]
0x180003d0d  mov     rbx, [rsp+38h+arg_8]
0x180003d12  mov     rsi, [rsp+38h+arg_10]
0x180003d17  add     rsp, 20h
0x180003d1b  pop     r15
0x180003d1d  pop     r14
0x180003d1f  pop     rdi
0x180003d20  retn
0x180003d21  mov     rax, [r14+8]
0x180003d25  cmp     [rax], r14
0x180003d28  jnz     short loc_180003D3A
0x180003d2a  mov     [rbx], r14
0x180003d2d  mov     [rbx+8], rax
0x180003d31  mov     [rax], rbx
0x180003d34  mov     [r14+8], rbx
0x180003d38  jmp     short loc_180003D06
0x180003d3a  mov     ecx, 3
0x180003d3f  int     29h; Win8: RtlFailFast(ecx)
0x180007250  mov     eax, 80070057h
0x180007255  jmp     loc_180003D0D
0x18000725a  sub     rax, rdi
0x18000725d  sar     rax, 1
0x180007260  lea     r8d, [rax-1]
0x180007264  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBGK@Z; STRA::CopyWTruncate(ushort const *,ulong)
0x18000726a  nop
0x18000726b  jmp     loc_180003C21
0x180007270  mov     dword ptr [rbx+84h], 1
0x18000727a  jmp     loc_180003C6D
0x18000727f  mov     dword ptr [rbx+88h], 1
0x180007289  jmp     loc_180003C9B
```
