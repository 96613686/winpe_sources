# ORProcessSecurityDescriptor

- ea: `0x140029598`
- end: `0x1400296e0`
- name: `ORProcessSecurityDescriptor`
- size: `328`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140023cb0`
- `0x140025580`

## callees

- `0x1400029c6`
- `0x1400029d2`
- `0x140002b2c`
- `0x1400270ec`
- `0x140029598`
- `0x14002e8c0`
- `0x14002e8cc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1400295de`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1400295de`

## pseudocode

```c
__int64 __fastcall ORProcessSecurityDescriptor(__int64 a1, void *a2, _QWORD *a3)
{
  _QWORD *i; // rdi
  unsigned int v6; // ebx
  _QWORD *v7; // r14
  size_t SecurityDescriptorLength; // rbp
  __int64 v9; // rcx
  _DWORD *v10; // r15
  _QWORD *v11; // rax

  i = 0;
  *a3 = 0;
  v6 = ORMakeSDRelative(a2);
  if ( !v6 )
  {
    v7 = (_QWORD *)(a1 + 64);
    SecurityDescriptorLength = GetSecurityDescriptorLength(0);
    for ( i = (_QWORD *)*v7; i != v7; i = (_QWORD *)*i )
    {
      v9 = i[2];
      if ( *(_DWORD *)(v9 + 16) == (_DWORD)SecurityDescriptorLength
        && !memcmp_0((const void *)(v9 + 20), 0, SecurityDescriptorLength) )
      {
        goto LABEL_13;
      }
    }
    i = o__aligned_malloc_0(0x28u, 0x10u);
    if ( !i
      || (v10 = o__aligned_malloc_0((unsigned int)(SecurityDescriptorLength + 20), 0x10u),
          memset_0(v10, 0, (unsigned int)(SecurityDescriptorLength + 20)),
          !v10) )
    {
      v6 = 8;
      goto LABEL_14;
    }
    *(_WORD *)v10 = 27507;
    v10[3] = 0;
    v10[4] = SecurityDescriptorLength;
    memcpy_0(v10 + 5, 0, SecurityDescriptorLength);
    i[2] = v10;
    v11 = (_QWORD *)v7[1];
    if ( (_QWORD *)*v11 != v7 )
      __fastfail(3u);
    *i = v7;
    i[1] = v11;
    *v11 = i;
    v7[1] = i;
LABEL_13:
    v6 = 0;
    *a3 = i;
    i = 0;
  }
LABEL_14:
  if ( i )
    aligned_free(i);
  return v6;
}

```

## disassembly

```asm
0x140029598  mov     rax, rsp
0x14002959b  push    rbx
0x14002959c  push    rbp
0x14002959d  push    rsi
0x14002959e  push    rdi
0x14002959f  push    r12
0x1400295a1  push    r13
0x1400295a3  push    r14
0x1400295a5  push    r15
0x1400295a7  sub     rsp, 28h
0x1400295ab  mov     r13, rdx
0x1400295ae  mov     r14, rcx
0x1400295b1  xor     edi, edi
0x1400295b3  lea     rdx, [rax+18h]
0x1400295b7  mov     rcx, r13; pAbsoluteSecurityDescriptor
0x1400295ba  mov     [rax+18h], rdi
0x1400295be  mov     r12, r8
0x1400295c1  mov     [r8], rdi
0x1400295c4  call    ORMakeSDRelative
0x1400295c9  mov     rsi, [rsp+68h+pSecurityDescriptor]
0x1400295d1  mov     ebx, eax
0x1400295d3  test    eax, eax
0x1400295d5  jnz     loc_1400296AD
0x1400295db  mov     rcx, rsi; pSecurityDescriptor
0x1400295de  call    cs:__imp_GetSecurityDescriptorLength
0x1400295e5  nop     dword ptr [rax+rax+00h]
0x1400295ea  add     r14, 40h ; '@'
0x1400295ee  mov     ebp, eax
0x1400295f0  mov     rdi, [r14]
0x1400295f3  cmp     rdi, r14
0x1400295f6  jz      short loc_14002961D
0x1400295f8  mov     rcx, [rdi+10h]
0x1400295fc  cmp     [rcx+10h], ebp
0x1400295ff  jnz     short loc_140029618
0x140029601  mov     r8, rbp; Size
0x140029604  add     rcx, 14h; Buf1
0x140029608  mov     rdx, rsi; Buf2
0x14002960b  call    memcmp_0
0x140029610  test    eax, eax
0x140029612  jz      loc_1400296A5
0x140029618  mov     rdi, [rdi]
0x14002961b  jmp     short loc_1400295F3
0x14002961d  mov     r15d, 10h
0x140029623  mov     edx, r15d; Alignment
0x140029626  lea     ecx, [r15+18h]; Size
0x14002962a  call    _o__aligned_malloc_0
0x14002962f  mov     rdi, rax
0x140029632  test    rax, rax
0x140029635  jnz     short loc_14002963E
0x140029637  mov     ebx, 8
0x14002963c  jmp     short loc_1400296AD
0x14002963e  lea     eax, [rbp+14h]
0x140029641  mov     rdx, r15; Alignment
0x140029644  mov     ecx, eax; Size
0x140029646  mov     ebx, eax
0x140029648  call    _o__aligned_malloc_0
0x14002964d  mov     r8d, ebx; Size
0x140029650  xor     edx, edx; Val
0x140029652  mov     rcx, rax; void *
0x140029655  mov     r15, rax
0x140029658  call    memset_0
0x14002965d  test    r15, r15
0x140029660  jz      short loc_140029637
0x140029662  mov     r8, rbp; Size
0x140029665  mov     word ptr [r15], 6B73h
0x14002966b  lea     rcx, [r15+14h]; void *
0x14002966f  mov     dword ptr [r15+0Ch], 0
0x140029677  mov     rdx, rsi; Src
0x14002967a  mov     [r15+10h], ebp
0x14002967e  call    memcpy_0
0x140029683  mov     [rdi+10h], r15
0x140029687  mov     rax, [r14+8]
0x14002968b  cmp     [rax], r14
0x14002968e  jz      short loc_140029697
0x140029690  mov     ecx, 3
0x140029695  int     29h; Win8: RtlFailFast(ecx)
0x140029697  mov     [rdi], r14
0x14002969a  mov     [rdi+8], rax
0x14002969e  mov     [rax], rdi
0x1400296a1  mov     [r14+8], rdi
0x1400296a5  xor     ebx, ebx
0x1400296a7  mov     [r12], rdi
0x1400296ab  xor     edi, edi
0x1400296ad  cmp     rsi, r13
0x1400296b0  jz      short loc_1400296BF
0x1400296b2  test    rsi, rsi
0x1400296b5  jz      short loc_1400296BF
0x1400296b7  mov     rcx, rsi; Block
0x1400296ba  call    _aligned_free
0x1400296bf  test    rdi, rdi
0x1400296c2  jz      short loc_1400296CC
0x1400296c4  mov     rcx, rdi; Block
0x1400296c7  call    _aligned_free
0x1400296cc  mov     eax, ebx
0x1400296ce  add     rsp, 28h
0x1400296d2  pop     r15
0x1400296d4  pop     r14
0x1400296d6  pop     r13
0x1400296d8  pop     r12
0x1400296da  pop     rdi
0x1400296db  pop     rsi
0x1400296dc  pop     rbp
0x1400296dd  pop     rbx
0x1400296de  retn
```
