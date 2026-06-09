# TSKCreateKerbCertLogonBuffer

- ea: `0x140022bcc`
- end: `0x140022d91`
- name: `TSKCreateKerbCertLogonBuffer`
- size: `453`
- prototype: `__int64 __fastcall(int, int, int, int, size_t, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140022718`

## callees

- `0x1400102c0`
- `0x1400105c0`
- `0x140020008`
- `0x140022bcc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140022c11`
- `ntoskrnl!ExAllocatePool2` at `0x140022c68`
- `ntoskrnl!ExAllocatePool2` at `0x140022c11`
- `ntoskrnl!ExAllocatePool2` at `0x140022c68`

## pseudocode

```c
__int64 __fastcall TSKCreateKerbCertLogonBuffer(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        const void *a4,
        size_t a5,
        _QWORD *a6)
{
  unsigned int v9; // ebx
  void *Pool2; // rax
  void *v11; // rsi
  _WORD *v12; // rax
  _WORD *v13; // r14
  unsigned int v14; // edi
  size_t v15; // r8
  const void *v16; // rdx
  size_t v17; // r8
  char *v18; // rbx
  const void *v19; // rdx
  size_t v20; // r8
  char *v21; // rbx
  const void *v22; // rdx
  unsigned __int64 v23; // rcx
  unsigned int v25; // [rsp+20h] [rbp-58h]

  v9 = 256;
  if ( TSGlobalPoolType != PagedPool )
    v9 = 64;
  Pool2 = (void *)ExAllocatePool2(v9, 232, 1802531668);
  v11 = Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  memset(Pool2, 0, 0xE8u);
  v25 = a5 + ((*a2 + *a1 + *a3 + 93) & 0xFFFFFFF8);
  v12 = (_WORD *)ExAllocatePool2(v9, v25, 1802531668);
  v13 = v12;
  if ( !v12 )
  {
    TSKFreePrimaryCredentials(v11);
    return (unsigned int)-1073741670;
  }
  v14 = 0;
  memset(v12, 0, v25);
  v15 = *a1;
  v16 = (const void *)*((_QWORD *)a1 + 1);
  *(_DWORD *)v13 = 13;
  v13[20] = v15;
  *((_QWORD *)v13 + 6) = 80;
  v13[21] = v15 + 2;
  memmove(v13 + 40, v16, v15);
  v17 = *a2;
  v18 = (char *)v13 + (unsigned __int16)v13[21] + 80;
  v19 = (const void *)*((_QWORD *)a2 + 1);
  v13[4] = v17;
  v13[5] = v17 + 2;
  *((_QWORD *)v13 + 2) = v18 - (char *)v13;
  memmove(v18, v19, v17);
  v20 = *a3;
  v21 = &v18[(unsigned __int16)v13[5]];
  v22 = (const void *)*((_QWORD *)a3 + 1);
  v13[12] = v20;
  v13[13] = v20 + 2;
  *((_QWORD *)v13 + 4) = v21 - (char *)v13;
  memmove(v21, v22, v20);
  v23 = (unsigned __int64)&v21[(unsigned __int16)v13[13] + 7];
  *((_DWORD *)v13 + 15) = a5;
  v23 &= 0xFFFFFFFFFFFFFFF8uLL;
  *((_QWORD *)v13 + 8) = v23 - (_QWORD)v13;
  memmove((void *)v23, a4, (unsigned int)a5);
  *((_DWORD *)v11 + 40) = v25;
  *((_QWORD *)v11 + 19) = v13;
  *a6 = v11;
  return v14;
}

```

## disassembly

```asm
0x140022bcc  mov     [rsp+Src], r9
0x140022bd1  push    rbx
0x140022bd2  push    rbp
0x140022bd3  push    rsi
0x140022bd4  push    rdi
0x140022bd5  push    r12
0x140022bd7  push    r13
0x140022bd9  push    r14
0x140022bdb  push    r15
0x140022bdd  sub     rsp, 38h
0x140022be1  cmp     cs:?TSGlobalPoolType@@3W4_POOL_TYPE@@A, 1; _POOL_TYPE TSGlobalPoolType
0x140022be8  mov     r13, rcx
0x140022beb  mov     ecx, 40h ; '@'
0x140022bf0  mov     rbp, r8
0x140022bf3  mov     r15, rdx
0x140022bf6  mov     ebx, 100h
0x140022bfb  cmovnz  ebx, ecx
0x140022bfe  mov     edi, 6B707354h
0x140022c03  mov     r14d, 0E8h
0x140022c09  mov     ecx, ebx
0x140022c0b  mov     r8d, edi
0x140022c0e  mov     edx, r14d
0x140022c11  call    cs:__imp_ExAllocatePool2
0x140022c18  nop     dword ptr [rax+rax+00h]
0x140022c1d  mov     rsi, rax
0x140022c20  test    rax, rax
0x140022c23  jz      loc_140022D78
0x140022c29  mov     r8d, r14d; Size
0x140022c2c  xor     edx, edx; Val
0x140022c2e  mov     rcx, rax; void *
0x140022c31  call    memset
0x140022c36  movzx   eax, word ptr [r15]
0x140022c3a  mov     r8d, edi
0x140022c3d  movzx   edx, word ptr [r13+0]
0x140022c42  mov     ecx, ebx
0x140022c44  mov     r12d, dword ptr [rsp+78h+arg_20]
0x140022c4c  add     edx, eax
0x140022c4e  movzx   eax, word ptr [rbp+0]
0x140022c52  add     eax, 5Dh ; ']'
0x140022c55  add     eax, edx
0x140022c57  and     eax, 0FFFFFFF8h
0x140022c5a  add     eax, r12d
0x140022c5d  mov     edx, eax
0x140022c5f  mov     [rsp+78h+var_58], eax
0x140022c63  mov     [rsp+78h+Size], rax
0x140022c68  call    cs:__imp_ExAllocatePool2
0x140022c6f  nop     dword ptr [rax+rax+00h]
0x140022c74  mov     r14, rax
0x140022c77  test    rax, rax
0x140022c7a  jz      loc_140022D70
0x140022c80  mov     r8, [rsp+78h+Size]; Size
0x140022c85  xor     edx, edx; Val
0x140022c87  mov     rcx, rax; void *
0x140022c8a  xor     edi, edi
0x140022c8c  call    memset
0x140022c91  movzx   r8d, word ptr [r13+0]; Size
0x140022c96  lea     rbx, [r14+50h]
0x140022c9a  mov     rdx, [r13+8]; Src
0x140022c9e  mov     dword ptr [r14], 0Dh
0x140022ca5  mov     [r14+28h], r8w
0x140022caa  lea     ecx, [r8+2]
0x140022cae  mov     qword ptr [r14+30h], 50h ; 'P'
0x140022cb6  mov     [r14+2Ah], cx
0x140022cbb  mov     rcx, rbx; void *
0x140022cbe  call    memmove
0x140022cc3  movzx   eax, word ptr [r14+2Ah]
0x140022cc8  movzx   r8d, word ptr [r15]; Size
0x140022ccc  add     rbx, rax
0x140022ccf  mov     rdx, [r15+8]; Src
0x140022cd3  mov     rcx, rbx; void *
0x140022cd6  mov     [r14+8], r8w
0x140022cdb  lea     eax, [r8+2]
0x140022cdf  mov     [r14+0Ah], ax
0x140022ce4  mov     rax, rbx
0x140022ce7  sub     rax, r14
0x140022cea  mov     [r14+10h], rax
0x140022cee  call    memmove
0x140022cf3  movzx   eax, word ptr [r14+0Ah]
0x140022cf8  movzx   r8d, word ptr [rbp+0]; Size
0x140022cfd  add     rbx, rax
0x140022d00  mov     rdx, [rbp+8]; Src
0x140022d04  mov     rcx, rbx; void *
0x140022d07  mov     [r14+18h], r8w
0x140022d0c  lea     eax, [r8+2]
0x140022d10  mov     [r14+1Ah], ax
0x140022d15  mov     rax, rbx
0x140022d18  sub     rax, r14
0x140022d1b  mov     [r14+20h], rax
0x140022d1f  call    memmove
0x140022d24  movzx   ecx, word ptr [r14+1Ah]
0x140022d29  mov     r8d, r12d; Size
0x140022d2c  mov     rdx, [rsp+78h+Src]; Src
0x140022d34  add     rcx, 7
0x140022d38  add     rcx, rbx
0x140022d3b  mov     [r14+3Ch], r12d
0x140022d3f  and     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x140022d43  mov     rax, rcx
0x140022d46  sub     rax, r14
0x140022d49  mov     [r14+40h], rax
0x140022d4d  call    memmove
0x140022d52  mov     eax, [rsp+78h+var_58]
0x140022d56  mov     [rsi+0A0h], eax
0x140022d5c  mov     rax, [rsp+78h+arg_28]
0x140022d64  mov     [rsi+98h], r14
0x140022d6b  mov     [rax], rsi
0x140022d6e  jmp     short loc_140022D7D
0x140022d70  mov     rcx, rsi; P
0x140022d73  call    TSKFreePrimaryCredentials
0x140022d78  mov     edi, 0C000009Ah
0x140022d7d  mov     eax, edi
0x140022d7f  add     rsp, 38h
0x140022d83  pop     r15
0x140022d85  pop     r14
0x140022d87  pop     r13
0x140022d89  pop     r12
0x140022d8b  pop     rdi
0x140022d8c  pop     rsi
0x140022d8d  pop     rbp
0x140022d8e  pop     rbx
0x140022d8f  retn
```
