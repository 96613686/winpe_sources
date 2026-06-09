# CONTENT_TYPE_ALLOWED_ENTRY::Initialize(ushort const *,int,_LIST_ENTRY *)

- ea: `0x180003a80`
- end: `0x180003c21`
- name: `?Initialize@CONTENT_TYPE_ALLOWED_ENTRY@@QEAAJPEBGHPEAU_LIST_ENTRY@@@Z`
- size: `417`
- prototype: `int __fastcall(CONTENT_TYPE_ALLOWED_ENTRY *this, const unsigned __int16 *, int, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003850`

## callees

- `0x180003a80`

## import_xrefs

- `msvcrt!strchr` at `0x180003b3e`
- `msvcrt!strchr` at `0x180003b6c`
- `msvcrt!strchr` at `0x180003b3e`
- `msvcrt!strchr` at `0x180003b6c`
- `msvcrt!wcschr` at `0x180003aa7`
- `msvcrt!wcschr` at `0x180003ae4`
- `msvcrt!wcschr` at `0x180003aa7`
- `msvcrt!wcschr` at `0x180003ae4`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x180003afb`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x180003afb`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBGK@Z` at `0x180003ace`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBGK@Z` at `0x180005956`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBGK@Z` at `0x180003ace`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBGK@Z` at `0x180005956`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003b32`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003b60`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003b7f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003ba3`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003b32`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003b60`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003b7f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003ba3`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003b1d`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003b51`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003b1d`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003b51`

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
0x180003a80  mov     [rsp+arg_8], rbx
0x180003a85  mov     [rsp+arg_10], rsi
0x180003a8a  push    rdi
0x180003a8b  push    r14
0x180003a8d  push    r15
0x180003a8f  sub     rsp, 20h
0x180003a93  mov     rsi, rdx
0x180003a96  mov     rbx, rcx
0x180003a99  mov     rcx, rsi; Str
0x180003a9c  mov     edx, 2Fh ; '/'; Ch
0x180003aa1  mov     r14, r9
0x180003aa4  mov     r15d, r8d
0x180003aa7  call    cs:__imp_wcschr
0x180003aad  mov     rdi, rax
0x180003ab0  test    rax, rax
0x180003ab3  jz      loc_180005942
0x180003ab9  mov     r8, rax
0x180003abc  mov     [rsp+38h+arg_0], rbp
0x180003ac1  sub     r8, rsi
0x180003ac4  lea     rcx, [rbx+10h]
0x180003ac8  sar     r8, 1
0x180003acb  mov     rdx, rsi
0x180003ace  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBGK@Z; STRA::CopyWTruncate(ushort const *,ulong)
0x180003ad4  test    eax, eax
0x180003ad6  js      loc_180003BE8
0x180003adc  mov     edx, 3Bh ; ';'; Ch
0x180003ae1  mov     rcx, rdi; Str
0x180003ae4  call    cs:__imp_wcschr
0x180003aea  lea     rdx, [rdi+2]
0x180003aee  lea     rcx, [rbx+48h]
0x180003af2  test    rax, rax
0x180003af5  jnz     loc_18000594C
0x180003afb  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBG@Z; STRA::CopyWTruncate(ushort const *)
0x180003b01  test    eax, eax
0x180003b03  js      loc_180003BE8
0x180003b09  xor     edi, edi
0x180003b0b  mov     [rbx+80h], r15d
0x180003b12  lea     rcx, [rbx+10h]
0x180003b16  mov     [rbx+84h], rdi
0x180003b1d  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180003b23  mov     r15d, 2Ah ; '*'
0x180003b29  cmp     eax, 1
0x180003b2c  jbe     short loc_180003B4D
0x180003b2e  lea     rcx, [rbx+10h]
0x180003b32  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180003b38  mov     rcx, rax; Str
0x180003b3b  mov     edx, r15d; Val
0x180003b3e  call    cs:__imp_strchr
0x180003b44  test    rax, rax
0x180003b47  jnz     loc_180005962
0x180003b4d  lea     rcx, [rbx+48h]
0x180003b51  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180003b57  cmp     eax, 1
0x180003b5a  jbe     short loc_180003B7B
0x180003b5c  lea     rcx, [rbx+48h]
0x180003b60  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180003b66  mov     rcx, rax; Str
0x180003b69  mov     edx, r15d; Val
0x180003b6c  call    cs:__imp_strchr
0x180003b72  test    rax, rax
0x180003b75  jnz     loc_180005971
0x180003b7b  lea     rcx, [rbx+10h]
0x180003b7f  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180003b85  movzx   r8d, byte ptr [rax]
0x180003b89  sub     r8d, r15d
0x180003b8c  jnz     short loc_180003B9A
0x180003b8e  movzx   r8d, byte ptr [rax+1]
0x180003b93  movzx   edx, dil
0x180003b97  sub     r8d, edx
0x180003b9a  test    r8d, r8d
0x180003b9d  jz      short loc_180003C01
0x180003b9f  lea     rcx, [rbx+48h]
0x180003ba3  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180003ba9  movzx   edx, byte ptr [rax]
0x180003bac  sub     edx, r15d
0x180003baf  jnz     short loc_180003BBB
0x180003bb1  movzx   edx, byte ptr [rax+1]
0x180003bb5  movzx   ecx, dil
0x180003bb9  sub     edx, ecx
0x180003bbb  test    edx, edx
0x180003bbd  jz      short loc_180003C01
0x180003bbf  cmp     [rbx+84h], edi
0x180003bc5  jnz     short loc_180003C01
0x180003bc7  cmp     [rbx+88h], edi
0x180003bcd  jnz     short loc_180003C01
0x180003bcf  mov     rax, [r14]
0x180003bd2  cmp     [rax+8], r14
0x180003bd6  jnz     short loc_180003C1A
0x180003bd8  mov     [rbx], rax
0x180003bdb  mov     [rbx+8], r14
0x180003bdf  mov     [rax+8], rbx
0x180003be3  mov     [r14], rbx
0x180003be6  xor     eax, eax
0x180003be8  mov     rbp, [rsp+38h+arg_0]
0x180003bed  mov     rbx, [rsp+38h+arg_8]
0x180003bf2  mov     rsi, [rsp+38h+arg_10]
0x180003bf7  add     rsp, 20h
0x180003bfb  pop     r15
0x180003bfd  pop     r14
0x180003bff  pop     rdi
0x180003c00  retn
0x180003c01  mov     rax, [r14+8]
0x180003c05  cmp     [rax], r14
0x180003c08  jnz     short loc_180003C1A
0x180003c0a  mov     [rbx], r14
0x180003c0d  mov     [rbx+8], rax
0x180003c11  mov     [rax], rbx
0x180003c14  mov     [r14+8], rbx
0x180003c18  jmp     short loc_180003BE6
0x180003c1a  mov     ecx, 3
0x180003c1f  int     29h; Win8: RtlFailFast(ecx)
0x180005942  mov     eax, 80070057h
0x180005947  jmp     loc_180003BED
0x18000594c  sub     rax, rdi
0x18000594f  sar     rax, 1
0x180005952  lea     r8d, [rax-1]
0x180005956  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBGK@Z; STRA::CopyWTruncate(ushort const *,ulong)
0x18000595c  nop
0x18000595d  jmp     loc_180003B01
0x180005962  mov     dword ptr [rbx+84h], 1
0x18000596c  jmp     loc_180003B4D
0x180005971  mov     dword ptr [rbx+88h], 1
0x18000597b  jmp     loc_180003B7B
```
