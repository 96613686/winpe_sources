# tson::output_archive::saveValue(tson::ansistring_tag)

- ea: `0x1800189d0`
- end: `0x180018a65`
- name: `?saveValue@output_archive@tson@@QEAAXUansistring_tag@2@@Z`
- size: `149`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1800067e4`
- `0x180018a6c`
- `0x180019060`
- `0x180019660`
- `0x180019820`

## callees

- `0x18001873c`
- `0x1800189d0`
- `0x18001a160`
- `0x18001a380`

## pseudocode

```c
void __fastcall tson::output_archive::saveValue(tson::write_buffer **a1, __m128i *a2)
{
  void *v3; // rsi
  tson::write_buffer *v4; // rbx
  unsigned __int64 v5; // xmm0_8
  __m128i v6; // [rsp+20h] [rbp-38h]

  v6 = *a2;
  v3 = (void *)a2->m128i_i64[0];
  if ( tson::output_archive::write_name((tson::output_archive *)a1, a2->m128i_i64[0] == 0) )
  {
    v4 = a1[18];
    if ( *((_QWORD *)v4 + 259) < *((_QWORD *)v4 + 260) || tson::write_buffer::reserve(a1[18], 1u) )
      *(_BYTE *)(*((_QWORD *)v4 + 259))++ = 23;
    v5 = _mm_srli_si128(v6, 8).m128i_u64[0];
    tson::output_archive::write_string_bytes((tson::output_archive *)a1, v5, v3, v5);
  }
}

```

## disassembly

```asm
0x1800189d0  mov     [rsp+arg_0], rbx
0x1800189d5  mov     [rsp+arg_8], rsi
0x1800189da  push    rdi
0x1800189db  sub     rsp, 50h
0x1800189df  movaps  xmm1, xmmword ptr [rdx]
0x1800189e2  mov     rdi, rcx
0x1800189e5  movq    rsi, xmm1
0x1800189ea  movaps  [rsp+58h+var_38], xmm1
0x1800189ef  test    rsi, rsi
0x1800189f2  setz    dl; bool
0x1800189f5  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x1800189fa  test    al, al
0x1800189fc  jz      short loc_180018A54
0x1800189fe  mov     rbx, [rdi+90h]
0x180018a05  mov     rax, [rbx+820h]
0x180018a0c  cmp     [rbx+818h], rax
0x180018a13  jb      short loc_180018A26
0x180018a15  mov     edx, 1; unsigned __int64
0x180018a1a  mov     rcx, rbx; this
0x180018a1d  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180018a22  test    al, al
0x180018a24  jz      short loc_180018A37
0x180018a26  mov     rax, [rbx+818h]
0x180018a2d  mov     byte ptr [rax], 17h
0x180018a30  inc     qword ptr [rbx+818h]
0x180018a37  movaps  xmm0, [rsp+58h+var_38]
0x180018a3c  mov     r8, rsi; void *
0x180018a3f  psrldq  xmm0, 8
0x180018a44  mov     rcx, rdi; this
0x180018a47  movq    rdx, xmm0; unsigned __int64
0x180018a4c  mov     r9, rdx; unsigned __int64
0x180018a4f  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x180018a54  mov     rbx, [rsp+58h+arg_0]
0x180018a59  mov     rsi, [rsp+58h+arg_8]
0x180018a5e  add     rsp, 50h
0x180018a62  pop     rdi
0x180018a63  retn
```
