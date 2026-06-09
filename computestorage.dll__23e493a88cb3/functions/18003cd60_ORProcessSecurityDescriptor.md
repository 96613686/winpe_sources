# ORProcessSecurityDescriptor

- ea: `0x18003cd60`
- end: `0x18003cea8`
- name: `ORProcessSecurityDescriptor`
- size: `328`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039320`
- `0x18003bac8`

## callees

- `0x180003166`
- `0x180003172`
- `0x1800032b8`
- `0x180003ba9`
- `0x180003bb5`
- `0x180038f40`
- `0x18003cd60`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18003cda6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18003cda6`

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
0x18003cd60  mov     rax, rsp
0x18003cd63  push    rbx
0x18003cd64  push    rbp
0x18003cd65  push    rsi
0x18003cd66  push    rdi
0x18003cd67  push    r12
0x18003cd69  push    r13
0x18003cd6b  push    r14
0x18003cd6d  push    r15
0x18003cd6f  sub     rsp, 28h
0x18003cd73  mov     r13, rdx
0x18003cd76  mov     r14, rcx
0x18003cd79  xor     edi, edi
0x18003cd7b  lea     rdx, [rax+18h]
0x18003cd7f  mov     rcx, r13; pAbsoluteSecurityDescriptor
0x18003cd82  mov     [rax+18h], rdi
0x18003cd86  mov     r12, r8
0x18003cd89  mov     [r8], rdi
0x18003cd8c  call    ORMakeSDRelative
0x18003cd91  mov     rsi, [rsp+68h+pSecurityDescriptor]
0x18003cd99  mov     ebx, eax
0x18003cd9b  test    eax, eax
0x18003cd9d  jnz     loc_18003CE75
0x18003cda3  mov     rcx, rsi; pSecurityDescriptor
0x18003cda6  call    cs:__imp_GetSecurityDescriptorLength
0x18003cdad  nop     dword ptr [rax+rax+00h]
0x18003cdb2  add     r14, 40h ; '@'
0x18003cdb6  mov     ebp, eax
0x18003cdb8  mov     rdi, [r14]
0x18003cdbb  cmp     rdi, r14
0x18003cdbe  jz      short loc_18003CDE5
0x18003cdc0  mov     rcx, [rdi+10h]
0x18003cdc4  cmp     [rcx+10h], ebp
0x18003cdc7  jnz     short loc_18003CDE0
0x18003cdc9  mov     r8, rbp; Size
0x18003cdcc  add     rcx, 14h; Buf1
0x18003cdd0  mov     rdx, rsi; Buf2
0x18003cdd3  call    memcmp_0
0x18003cdd8  test    eax, eax
0x18003cdda  jz      loc_18003CE6D
0x18003cde0  mov     rdi, [rdi]
0x18003cde3  jmp     short loc_18003CDBB
0x18003cde5  mov     r15d, 10h
0x18003cdeb  mov     edx, r15d; Alignment
0x18003cdee  lea     ecx, [r15+18h]; Size
0x18003cdf2  call    _o__aligned_malloc_0
0x18003cdf7  mov     rdi, rax
0x18003cdfa  test    rax, rax
0x18003cdfd  jnz     short loc_18003CE06
0x18003cdff  mov     ebx, 8
0x18003ce04  jmp     short loc_18003CE75
0x18003ce06  lea     eax, [rbp+14h]
0x18003ce09  mov     rdx, r15; Alignment
0x18003ce0c  mov     ecx, eax; Size
0x18003ce0e  mov     ebx, eax
0x18003ce10  call    _o__aligned_malloc_0
0x18003ce15  mov     r8d, ebx; Size
0x18003ce18  xor     edx, edx; Val
0x18003ce1a  mov     rcx, rax; void *
0x18003ce1d  mov     r15, rax
0x18003ce20  call    memset_0
0x18003ce25  test    r15, r15
0x18003ce28  jz      short loc_18003CDFF
0x18003ce2a  mov     r8, rbp; Size
0x18003ce2d  mov     word ptr [r15], 6B73h
0x18003ce33  lea     rcx, [r15+14h]; void *
0x18003ce37  mov     dword ptr [r15+0Ch], 0
0x18003ce3f  mov     rdx, rsi; Src
0x18003ce42  mov     [r15+10h], ebp
0x18003ce46  call    memcpy_0
0x18003ce4b  mov     [rdi+10h], r15
0x18003ce4f  mov     rax, [r14+8]
0x18003ce53  cmp     [rax], r14
0x18003ce56  jz      short loc_18003CE5F
0x18003ce58  mov     ecx, 3
0x18003ce5d  int     29h; Win8: RtlFailFast(ecx)
0x18003ce5f  mov     [rdi], r14
0x18003ce62  mov     [rdi+8], rax
0x18003ce66  mov     [rax], rdi
0x18003ce69  mov     [r14+8], rdi
0x18003ce6d  xor     ebx, ebx
0x18003ce6f  mov     [r12], rdi
0x18003ce73  xor     edi, edi
0x18003ce75  cmp     rsi, r13
0x18003ce78  jz      short loc_18003CE87
0x18003ce7a  test    rsi, rsi
0x18003ce7d  jz      short loc_18003CE87
0x18003ce7f  mov     rcx, rsi; Block
0x18003ce82  call    _aligned_free
0x18003ce87  test    rdi, rdi
0x18003ce8a  jz      short loc_18003CE94
0x18003ce8c  mov     rcx, rdi; Block
0x18003ce8f  call    _aligned_free
0x18003ce94  mov     eax, ebx
0x18003ce96  add     rsp, 28h
0x18003ce9a  pop     r15
0x18003ce9c  pop     r14
0x18003ce9e  pop     r13
0x18003cea0  pop     r12
0x18003cea2  pop     rdi
0x18003cea3  pop     rsi
0x18003cea4  pop     rbp
0x18003cea5  pop     rbx
0x18003cea6  retn
```
