# ORProcessSecurityDescriptor

- ea: `0x18003045c`
- end: `0x1800305a4`
- name: `ORProcessSecurityDescriptor`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002cdfc`

## callees

- `0x180003542`
- `0x18000354e`
- `0x180003608`
- `0x180003614`
- `0x18000362c`
- `0x18002fb20`
- `0x18003045c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800304a2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800304a2`

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
0x18003045c  mov     rax, rsp
0x18003045f  push    rbx
0x180030460  push    rbp
0x180030461  push    rsi
0x180030462  push    rdi
0x180030463  push    r12
0x180030465  push    r13
0x180030467  push    r14
0x180030469  push    r15
0x18003046b  sub     rsp, 28h
0x18003046f  mov     r13, rdx
0x180030472  mov     r14, rcx
0x180030475  xor     edi, edi
0x180030477  lea     rdx, [rax+18h]
0x18003047b  mov     rcx, r13; pAbsoluteSecurityDescriptor
0x18003047e  mov     [rax+18h], rdi
0x180030482  mov     r12, r8
0x180030485  mov     [r8], rdi
0x180030488  call    ORMakeSDRelative
0x18003048d  mov     rsi, [rsp+68h+pSecurityDescriptor]
0x180030495  mov     ebx, eax
0x180030497  test    eax, eax
0x180030499  jnz     loc_180030571
0x18003049f  mov     rcx, rsi; pSecurityDescriptor
0x1800304a2  call    cs:__imp_GetSecurityDescriptorLength
0x1800304a9  nop     dword ptr [rax+rax+00h]
0x1800304ae  add     r14, 40h ; '@'
0x1800304b2  mov     ebp, eax
0x1800304b4  mov     rdi, [r14]
0x1800304b7  cmp     rdi, r14
0x1800304ba  jz      short loc_1800304E1
0x1800304bc  mov     rcx, [rdi+10h]
0x1800304c0  cmp     [rcx+10h], ebp
0x1800304c3  jnz     short loc_1800304DC
0x1800304c5  mov     r8, rbp; Size
0x1800304c8  add     rcx, 14h; Buf1
0x1800304cc  mov     rdx, rsi; Buf2
0x1800304cf  call    memcmp_0
0x1800304d4  test    eax, eax
0x1800304d6  jz      loc_180030569
0x1800304dc  mov     rdi, [rdi]
0x1800304df  jmp     short loc_1800304B7
0x1800304e1  mov     r15d, 10h
0x1800304e7  mov     edx, r15d; Alignment
0x1800304ea  lea     ecx, [r15+18h]; Size
0x1800304ee  call    _o__aligned_malloc_0
0x1800304f3  mov     rdi, rax
0x1800304f6  test    rax, rax
0x1800304f9  jnz     short loc_180030502
0x1800304fb  mov     ebx, 8
0x180030500  jmp     short loc_180030571
0x180030502  lea     eax, [rbp+14h]
0x180030505  mov     rdx, r15; Alignment
0x180030508  mov     ecx, eax; Size
0x18003050a  mov     ebx, eax
0x18003050c  call    _o__aligned_malloc_0
0x180030511  mov     r8d, ebx; Size
0x180030514  xor     edx, edx; Val
0x180030516  mov     rcx, rax; void *
0x180030519  mov     r15, rax
0x18003051c  call    memset_0
0x180030521  test    r15, r15
0x180030524  jz      short loc_1800304FB
0x180030526  mov     r8, rbp; Size
0x180030529  mov     word ptr [r15], 6B73h
0x18003052f  lea     rcx, [r15+14h]; void *
0x180030533  mov     dword ptr [r15+0Ch], 0
0x18003053b  mov     rdx, rsi; Src
0x18003053e  mov     [r15+10h], ebp
0x180030542  call    memcpy_0
0x180030547  mov     [rdi+10h], r15
0x18003054b  mov     rax, [r14+8]
0x18003054f  cmp     [rax], r14
0x180030552  jz      short loc_18003055B
0x180030554  mov     ecx, 3
0x180030559  int     29h; Win8: RtlFailFast(ecx)
0x18003055b  mov     [rdi], r14
0x18003055e  mov     [rdi+8], rax
0x180030562  mov     [rax], rdi
0x180030565  mov     [r14+8], rdi
0x180030569  xor     ebx, ebx
0x18003056b  mov     [r12], rdi
0x18003056f  xor     edi, edi
0x180030571  cmp     rsi, r13
0x180030574  jz      short loc_180030583
0x180030576  test    rsi, rsi
0x180030579  jz      short loc_180030583
0x18003057b  mov     rcx, rsi; Block
0x18003057e  call    _aligned_free
0x180030583  test    rdi, rdi
0x180030586  jz      short loc_180030590
0x180030588  mov     rcx, rdi; Block
0x18003058b  call    _aligned_free
0x180030590  mov     eax, ebx
0x180030592  add     rsp, 28h
0x180030596  pop     r15
0x180030598  pop     r14
0x18003059a  pop     r13
0x18003059c  pop     r12
0x18003059e  pop     rdi
0x18003059f  pop     rsi
0x1800305a0  pop     rbp
0x1800305a1  pop     rbx
0x1800305a2  retn
```
