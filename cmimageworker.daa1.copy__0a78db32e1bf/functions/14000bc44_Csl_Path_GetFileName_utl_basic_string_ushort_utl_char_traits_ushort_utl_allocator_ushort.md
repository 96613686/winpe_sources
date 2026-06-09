# Csl::Path::GetFileName(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x14000bc44`
- end: `0x14000bd4a`
- name: `?GetFileName@Path@Csl@@QEBA_NAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140006188`

## callees

- `0x140002344`
- `0x14000a7a4`
- `0x14000a84c`
- `0x14000a910`
- `0x14000aa58`
- `0x14000bc44`

## pseudocode

```c
char __fastcall Csl::Path::GetFileName(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  char v8; // bl
  _QWORD *v9; // rax
  _QWORD v11[2]; // [rsp+20h] [rbp-19h] BYREF
  __int128 v12; // [rsp+30h] [rbp-9h] BYREF
  _BYTE v13[16]; // [rsp+40h] [rbp+7h] BYREF
  void *v14[2]; // [rsp+50h] [rbp+17h] BYREF
  __int16 v15; // [rsp+60h] [rbp+27h] BYREF
  __int64 v16; // [rsp+62h] [rbp+29h]
  int v17; // [rsp+6Ah] [rbp+31h]
  __int16 v18; // [rsp+6Eh] [rbp+35h]
  void *v19[2]; // [rsp+70h] [rbp+37h] BYREF
  _WORD v20[8]; // [rsp+80h] [rbp+47h] BYREF

  v19[0] = v20;
  v19[1] = v20;
  v20[0] = 0;
  v5 = (__int64)(a1[1] - *a1) >> 1;
  if ( v5 )
  {
    v11[0] = a1;
    v11[1] = v5;
    v12 = *(_OWORD *)Csl::Path::Iterator::operator--(v11);
    v9 = (_QWORD *)Csl::Path::Iterator::operator*(&v12, v13);
    v8 = Csl::Path::Assign((Csl::Path *)v19, v9);
    if ( !v8 )
      goto LABEL_7;
  }
  else
  {
    v16 = 0;
    v18 = 0;
    v17 = 0;
    v14[0] = &v15;
    v14[1] = &v15;
    v15 = 0;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
      v19,
      v14,
      a3,
      a4);
    if ( v14[0] != &v15 )
      operator delete(v14[0], (const struct std::nothrow_t *)&std::nothrow);
    v8 = 1;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    a2,
    v19,
    v6,
    v7);
LABEL_7:
  if ( v19[0] != v20 )
    operator delete(v19[0], (const struct std::nothrow_t *)&std::nothrow);
  return v8;
}

```

## disassembly

```asm
0x14000bc44  mov     [rsp-8+arg_0], rbx
0x14000bc49  mov     [rsp-8+arg_8], rdi
0x14000bc4e  push    rbp
0x14000bc4f  lea     rbp, [rsp-57h]
0x14000bc54  sub     rsp, 90h
0x14000bc5b  lea     rax, [rbp+57h+var_10]
0x14000bc5f  mov     rdi, rdx
0x14000bc62  mov     [rbp+57h+var_20], rax
0x14000bc66  lea     rax, [rbp+57h+var_10]
0x14000bc6a  mov     [rbp+57h+var_18], rax
0x14000bc6e  xor     eax, eax
0x14000bc70  mov     [rbp+57h+var_10], ax
0x14000bc74  mov     rax, [rcx+8]
0x14000bc78  sub     rax, [rcx]
0x14000bc7b  sar     rax, 1
0x14000bc7e  jnz     short loc_14000BCD5
0x14000bc80  xor     eax, eax
0x14000bc82  mov     [rbp+57h+var_2E], 0
0x14000bc8a  mov     [rbp+57h+var_22], ax
0x14000bc8e  lea     rdx, [rbp+57h+var_40]
0x14000bc92  lea     rax, [rbp+57h+var_30]
0x14000bc96  mov     [rbp+57h+var_26], 0
0x14000bc9d  mov     [rbp+57h+var_40], rax
0x14000bca1  lea     rcx, [rbp+57h+var_20]
0x14000bca5  lea     rax, [rbp+57h+var_30]
0x14000bca9  mov     [rbp+57h+var_38], rax
0x14000bcad  xor     eax, eax
0x14000bcaf  mov     [rbp+57h+var_30], ax
0x14000bcb3  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x14000bcb8  mov     rcx, [rbp+57h+var_40]; void *
0x14000bcbc  lea     rax, [rbp+57h+var_30]
0x14000bcc0  cmp     rcx, rax
0x14000bcc3  jz      short loc_14000BCD1
0x14000bcc5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000bccc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000bcd1  mov     bl, 1
0x14000bcd3  jmp     short loc_14000BD0D
0x14000bcd5  mov     [rbp+57h+var_70], rcx
0x14000bcd9  lea     rcx, [rbp+57h+var_70]
0x14000bcdd  mov     [rbp+57h+var_68], rax
0x14000bce1  call    ??FIterator@Path@Csl@@QEAAAEAV012@XZ; Csl::Path::Iterator::operator--(void)
0x14000bce6  lea     rdx, [rbp+57h+var_50]
0x14000bcea  lea     rcx, [rbp+57h+var_60]
0x14000bcee  movups  xmm0, xmmword ptr [rax]
0x14000bcf1  movdqu  [rbp+57h+var_60], xmm0
0x14000bcf6  call    ??DIterator@Path@Csl@@QEBA?AV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@XZ; Csl::Path::Iterator::operator*(void)
0x14000bcfb  mov     rdx, rax
0x14000bcfe  lea     rcx, [rbp+57h+var_20]; this
0x14000bd02  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14000bd07  mov     bl, al
0x14000bd09  test    al, al
0x14000bd0b  jz      short loc_14000BD19
0x14000bd0d  lea     rdx, [rbp+57h+var_20]
0x14000bd11  mov     rcx, rdi
0x14000bd14  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x14000bd19  mov     rcx, [rbp+57h+var_20]; void *
0x14000bd1d  lea     rax, [rbp+57h+var_10]
0x14000bd21  cmp     rcx, rax
0x14000bd24  jz      short loc_14000BD32
0x14000bd26  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000bd2d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000bd32  lea     r11, [rsp+90h+var_s0]
0x14000bd3a  mov     al, bl
0x14000bd3c  mov     rbx, [r11+10h]
0x14000bd40  mov     rdi, [r11+18h]
0x14000bd44  mov     rsp, r11
0x14000bd47  pop     rbp
0x14000bd48  retn
```
