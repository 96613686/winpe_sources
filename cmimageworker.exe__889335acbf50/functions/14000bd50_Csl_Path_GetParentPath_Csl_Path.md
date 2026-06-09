# Csl::Path::GetParentPath(Csl::Path &)

- ea: `0x14000bd50`
- end: `0x14000beb3`
- name: `?GetParentPath@Path@Csl@@QEBA_NAEAV12@@Z`
- size: `355`
- prototype: `char __fastcall(Csl::Path *this, struct Path *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x14000aa8c`

## callees

- `0x140002344`
- `0x14000a7a4`
- `0x14000a84c`
- `0x14000a910`
- `0x14000a9b8`
- `0x14000bd50`
- `0x14000c390`

## pseudocode

```c
char __fastcall Csl::Path::GetParentPath(Csl::Path *this, struct Path *a2)
{
  __int64 v4; // rax
  unsigned __int64 v5; // rbx
  _QWORD *v6; // rax
  unsigned __int64 v7; // rax
  __int64 v8; // rdx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  _WORD *i; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rax
  Csl::Path *v16; // [rsp+20h] [rbp-50h] BYREF
  unsigned __int64 v17; // [rsp+28h] [rbp-48h]
  Csl::Path *v18; // [rsp+30h] [rbp-40h] BYREF
  __int64 v19; // [rsp+38h] [rbp-38h]
  __int64 v20; // [rsp+40h] [rbp-30h] BYREF
  void *v21[2]; // [rsp+50h] [rbp-20h] BYREF
  _WORD v22[8]; // [rsp+60h] [rbp-10h] BYREF

  v4 = (__int64)(*((_QWORD *)this + 1) - *(_QWORD *)this) >> 1;
  v18 = this;
  v19 = v4;
  Csl::Path::Iterator::operator--((__int64)&v18);
  v16 = this;
  v21[0] = v22;
  v21[1] = v22;
  v5 = 0;
  v22[0] = 0;
  v17 = 0;
  while ( this != v18 || v5 != v19 )
  {
    v6 = Csl::Path::Iterator::operator*((__int64)&v16, &v20);
    if ( !Csl::Path::Append((Csl::Path *)v21, v6) )
    {
      if ( v21[0] != v22 )
        operator delete(v21[0], (const struct std::nothrow_t *)&std::nothrow);
      return 0;
    }
    v7 = Csl::Path::PrefixLength(this);
    if ( v5 >= v7 )
    {
      v8 = *(_QWORD *)this;
      v9 = v5;
      v5 = (__int64)(*((_QWORD *)this + 1) - *(_QWORD *)this) >> 1;
      if ( v5 > v9 )
      {
        v10 = v5 - v9;
        if ( v5 != v9 )
        {
          for ( i = (_WORD *)(v8 + 2 * v9); *i != 92; ++i )
          {
            if ( v10 == 1 )
              goto LABEL_16;
            --v10;
          }
          if ( i )
          {
            v12 = ((__int64)i - v8) >> 1;
            if ( v12 != -1 )
              v5 = v12 + 1;
          }
        }
      }
LABEL_16:
      v17 = v5;
    }
    else
    {
      v5 = v7;
      v17 = v7;
    }
    v13 = *(_QWORD *)this;
    v14 = (__int64)(*((_QWORD *)this + 1) - *(_QWORD *)this) >> 1;
    while ( v5 < v14 && *(_WORD *)(v13 + 2 * v5) == 92 )
      v17 = ++v5;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    (__int64)a2,
    (__int64)v21);
  if ( v21[0] != v22 )
    operator delete(v21[0], (const struct std::nothrow_t *)&std::nothrow);
  return 1;
}

```

## disassembly

```asm
0x14000bd50  push    rbp
0x14000bd52  push    rbx
0x14000bd53  push    rsi
0x14000bd54  push    rdi
0x14000bd55  push    r14
0x14000bd57  mov     rbp, rsp
0x14000bd5a  sub     rsp, 70h
0x14000bd5e  mov     rax, [rcx+8]
0x14000bd62  mov     rdi, rcx
0x14000bd65  sub     rax, [rcx]
0x14000bd68  mov     rsi, rdx
0x14000bd6b  sar     rax, 1
0x14000bd6e  mov     [rbp+var_40], rcx
0x14000bd72  lea     rcx, [rbp+var_40]
0x14000bd76  mov     [rbp+var_38], rax
0x14000bd7a  call    ??FIterator@Path@Csl@@QEAAAEAV012@XZ; Csl::Path::Iterator::operator--(void)
0x14000bd7f  lea     rax, [rbp+var_10]
0x14000bd83  mov     [rbp+var_50], rdi
0x14000bd87  mov     [rbp+var_20], rax
0x14000bd8b  lea     rax, [rbp+var_10]
0x14000bd8f  mov     [rbp+var_18], rax
0x14000bd93  xor     eax, eax
0x14000bd95  xor     ebx, ebx
0x14000bd97  mov     [rbp+var_10], ax
0x14000bd9b  mov     [rbp+var_48], rbx
0x14000bd9f  lea     r14d, [rax+5Ch]
0x14000bda3  cmp     rdi, [rbp+var_40]
0x14000bda7  jnz     short loc_14000BDB3
0x14000bda9  cmp     rbx, [rbp+var_38]
0x14000bdad  jz      loc_14000BE63
0x14000bdb3  lea     rdx, [rbp+var_30]
0x14000bdb7  lea     rcx, [rbp+var_50]
0x14000bdbb  call    ??DIterator@Path@Csl@@QEBA?AV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@XZ; Csl::Path::Iterator::operator*(void)
0x14000bdc0  mov     rdx, rax
0x14000bdc3  lea     rcx, [rbp+var_20]; this
0x14000bdc7  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14000bdcc  test    al, al
0x14000bdce  jz      loc_14000BE8C
0x14000bdd4  mov     rcx, rdi; this
0x14000bdd7  call    ?PrefixLength@Path@Csl@@AEBA_KXZ; Csl::Path::PrefixLength(void)
0x14000bddc  cmp     rbx, rax
0x14000bddf  jnb     short loc_14000BDEA
0x14000bde1  mov     rbx, rax
0x14000bde4  mov     [rbp+var_48], rax
0x14000bde8  jmp     short loc_14000BE39
0x14000bdea  mov     rdx, [rdi]
0x14000bded  mov     rax, rbx
0x14000bdf0  mov     rbx, [rdi+8]
0x14000bdf4  sub     rbx, rdx
0x14000bdf7  sar     rbx, 1
0x14000bdfa  cmp     rbx, rax
0x14000bdfd  jbe     short loc_14000BE35
0x14000bdff  mov     rcx, rbx
0x14000be02  sub     rcx, rax
0x14000be05  jz      short loc_14000BE35
0x14000be07  lea     rax, [rdx+rax*2]
0x14000be0b  jmp     short loc_14000BE1A
0x14000be0d  cmp     rcx, 1
0x14000be11  jz      short loc_14000BE35
0x14000be13  dec     rcx
0x14000be16  add     rax, 2
0x14000be1a  cmp     [rax], r14w
0x14000be1e  jnz     short loc_14000BE0D
0x14000be20  test    rax, rax
0x14000be23  jz      short loc_14000BE35
0x14000be25  sub     rax, rdx
0x14000be28  sar     rax, 1
0x14000be2b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000be2f  jz      short loc_14000BE35
0x14000be31  lea     rbx, [rax+1]
0x14000be35  mov     [rbp+var_48], rbx
0x14000be39  mov     rcx, [rdi]
0x14000be3c  mov     rax, [rdi+8]
0x14000be40  sub     rax, rcx
0x14000be43  sar     rax, 1
0x14000be46  cmp     rbx, rax
0x14000be49  jnb     loc_14000BDA3
0x14000be4f  cmp     r14w, [rcx+rbx*2]
0x14000be54  jnz     loc_14000BDA3
0x14000be5a  inc     rbx
0x14000be5d  mov     [rbp+var_48], rbx
0x14000be61  jmp     short loc_14000BE46
0x14000be63  lea     rdx, [rbp+var_20]
0x14000be67  mov     rcx, rsi
0x14000be6a  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x14000be6f  mov     rcx, [rbp+var_20]; void *
0x14000be73  lea     rdx, [rbp+var_10]
0x14000be77  cmp     rcx, rdx
0x14000be7a  jz      short loc_14000BE88
0x14000be7c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000be83  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000be88  mov     al, 1
0x14000be8a  jmp     short loc_14000BEA7
0x14000be8c  mov     rcx, [rbp+var_20]; void *
0x14000be90  lea     rax, [rbp+var_10]
0x14000be94  cmp     rcx, rax
0x14000be97  jz      short loc_14000BEA5
0x14000be99  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000bea0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000bea5  xor     al, al
0x14000bea7  add     rsp, 70h
0x14000beab  pop     r14
0x14000bead  pop     rdi
0x14000beae  pop     rsi
0x14000beaf  pop     rbx
0x14000beb0  pop     rbp
0x14000beb1  retn
```
